# mait 지식 베이스

이 레포는 mait 제품(실시간 팀 퀴즈/문제해결 플랫폼)의 자기유지 지식 베이스다.
Karpathy의 LLM Wiki 패턴을 따른다: **raw 입력 → 큐레이션된 wiki → Q&A 인터페이스**.

여기는 mait 제품 코드 레포가 **아니다**. 회의록·기획·문의를 정리하고, 사용자 질문에 답하는 용도다.

---

## 디렉터리 구조

```
raw/        새 원본 자료를 그대로 떨궈두는 곳 (immutable)
wiki/       에이전트가 큐레이션한 마크다운
  index.md      모든 wiki 페이지 카탈로그 (한 줄 요약 + 링크)
  log.md        시간순 작업 로그 (append-only)
  sources/      raw 원본 1건당 요약 1페이지
  features/     기능/기획 아이템 페이지
  decisions/    제품·아키텍처 결정 + 근거
  glossary/     용어 사전
  faq/          반복 질문 + 정답
output/     일회성 생성물 (Q&A 답변, 리포트). 버려도 됨
```

빈 하위 폴더는 첫 페이지가 생길 때 만들면 된다. 미리 만들지 말 것.

---

## 세 가지 동작

### 1. Ingest — `raw/`에 새 파일이 들어왔을 때

사용자가 "raw에 새거 정리해줘" / "회의록 위키 반영해줘" / `/ingest <file>` 식으로 부른다.

1. 해당 파일을 끝까지 읽는다. 종류(회의록/기획/문의), 날짜, 참여자, 핵심 주제를 식별.
2. `wiki/sources/<같은-slug>.md` 생성:
   - 프론트매터: `type`, `date`, `source_path`, `participants`, `topics`
   - 3~7문장 요약
   - 핵심 takeaway를 불릿으로. 각 항목은 raw의 어느 부분 근거인지 표시
   - 영향받는 `features/`, `decisions/`, `glossary/`, `faq/` 페이지로 상호링크
3. 영향받은 wiki 페이지를 갱신/신규 생성. **모든 사실은 `sources/` 페이지로 추적 가능해야 한다.**
4. `wiki/index.md` 갱신: 새 항목 추가, 오래된 요약 수정.
5. `wiki/log.md`에 한 줄 추가: `## [YYYY-MM-DD] ingest | <slug>` + 변경 요약 1줄.

### 2. Query — 사용자가 기능/결정에 대해 물을 때

"X 기능 어떻게 동작해?" / "지난 회의 결정 뭐였지?" / "이거 왜 이렇게 정했어?"

1. `wiki/index.md`를 먼저 본다.
2. 관련 페이지를 읽고 cross-link를 따라간다.
3. **wiki에 있는 내용으로만 답한다.** 없으면 "wiki에 없다"라고 명시 — 추측 금지.
4. 답변 안에 근거 페이지를 인용: `(wiki/features/team-rooms.md 참고)`.
5. 답이 재사용 가치가 있으면 `wiki/faq/`에 정리할지 사용자에게 제안.

### 3. Lint — "위키 한번 정리해줘"

1. 페이지간 모순 탐지.
2. orphan 페이지(`index.md` 미등록 또는 어디서도 링크 안 됨) 찾기.
3. stale 클레임(없어진 기능을 참조하는 결정 페이지 등) 찾기.
4. 조사 필요 항목 제안 (예: "3개 source가 X를 언급하는데 `features/X.md`가 없음").
5. 보고만 하고 자동 수정은 하지 말 것. 사용자 확인 후 수정.

---

## 페이지 컨벤션

### 프론트매터 (모든 wiki 페이지 필수)

```yaml
---
title: <사람이 읽는 제목>
type: feature | decision | glossary | faq | source
status: draft | stable | deprecated
sources: [raw/2026-04-15-kickoff.md, raw/2026-04-22-spec.md]
updated: 2026-04-24
---
```

### 파일 이름

- 소문자 + 하이픈. `features/team-rooms.md` (O), `features/TeamRooms.md` (X)
- **하위 폴더 1단계까지만.** `features/team/rooms.md` 같은 중첩 금지.
- raw 파일은 `YYYY-MM-DD-<slug>.md`. 예: `raw/2026-04-22-product-sync.md`

### 링크

- 항상 상대경로: `[팀 룸](../features/team-rooms.md)`
- 백링크는 프론트매터의 `sources:` 배열로 암묵적으로 유지.

### 인용

- 자명하지 않은 모든 사실은 source 페이지나 raw 파일로 링크.
- 예: `세션 타이머는 서버 권위 (raw/2026-04-12-design.md §실시간)`.

---

## 작성 원칙

- **Wiki는 큐레이션이지 받아쓰기가 아니다.** raw를 그대로 복붙하지 말 것. 통합·요약·정규화.
- **언어는 한국어 우선.** raw가 한국어면 wiki도 한국어. 용어는 glossary에서 통일.
- **상태가 바뀌면 페이지를 갱신한다.** 새 결정이 옛 결정을 뒤집으면, 옛 페이지에 `status: deprecated` + 새 페이지 링크.
- **draft → stable 승격은 사용자 확인 필요.** 에이전트가 임의로 stable 마킹 금지.

---

## 이 레포가 아닌 것

- mait 제품 코드가 아니다. 코드는 다른 레포.
- 채팅 로그가 아니다. `raw/`는 *완성된* 자료용 (회의 끝난 회의록, 확정된 스펙).
- 자유 메모장이 아니다. 일단 메모는 `raw/notes-YYYY-MM-DD.md`로 떨군 뒤 ingest.

---

## Claude Code 사용자 참고

`CLAUDE.md`에 gstack skill routing이 있다. 위 워크플로우는 어떤 에이전트(Claude Code, Codex, 기타)에서도 동일하게 적용된다.
