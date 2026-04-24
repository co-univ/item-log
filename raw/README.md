# raw/

원본 자료를 그대로 떨궈두는 곳. **수정 금지** — 일단 들어오면 immutable.

## 파일 이름

`YYYY-MM-DD-<slug>.md` — 날짜는 자료가 *생성된* 날짜 (오늘 날짜가 아님).

예시:
- `2026-04-15-product-kickoff-meeting.md` — 회의록
- `2026-04-22-team-rooms-spec.md` — 기획 명세서
- `2026-04-23-user-feedback-session-timeout.md` — 사용자 문의
- `2026-04-24-notes-realtime-sync.md` — 자유 메모

## 무엇이 들어가나

- 회의록 (raw transcript 또는 정리된 노트)
- 기획 명세서 / 디자인 doc
- 사용자 문의 / 피드백 / 인터뷰
- 외부 자료 (참고 아티클, 링크 모음 등)

## 무엇이 들어가면 안 되나

- 진행 중인 임시 메모 (Notion이나 다른 곳에서 끝낸 뒤 떨굴 것)
- 비밀 정보 (API 키, 개인정보) — 이 레포는 git에 들어감
- mait 제품 코드 (다른 레포)

## 새 파일 추가 후

에이전트에게 "raw에 새거 정리해줘" 또는 파일명 지정해서 요청. ingest 워크플로우는 [AGENTS.md](../AGENTS.md) 참고.
