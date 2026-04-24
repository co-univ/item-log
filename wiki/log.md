# Log

시간순 작업 로그. append-only. `## [YYYY-MM-DD] <op> | <slug>` 형식.
`<op>`: `ingest` | `update` | `lint` | `bootstrap`

## [2026-04-24] bootstrap | wiki 초기화

- AGENTS.md / CLAUDE.md / README.md 작성
- `wiki/index.md`, `wiki/log.md` 생성
- 첫 ingest 대기 중

## [2026-04-24] ingest | 2026-04-14-spec-problem-management

- Confluence "문제관리_문제생성" 명세 (이하은, 4/14 수정) 반영
- 신규 페이지 7개:
  - sources/2026-04-14-spec-problem-management.md
  - features/problem-set-creation.md
  - features/problem-set-lifecycle.md
  - features/question-editor.md
  - decisions/visibility-states.md
  - decisions/auto-save-behavior.md
  - glossary/core-terms.md
- index.md 갱신 (Sources/Features/Decisions/Glossary 섹션 채움)
- 미해결 이슈 5건 표시 (재시작 데이터 정책, 비-player 접근, 해설 글자수 등)

## [2026-04-24] ingest | 5건 일괄 (검색/인증/풀이관리/팀관리/플레이어뷰)

Confluence 5개 페이지 일괄 ingest:
- raw/2025-10-24-spec-auth-mypage.md (전민재)
- raw/2025-12-17-spec-problem-search.md (이하은)
- raw/2026-04-11-spec-play-management.md (이하은)
- raw/2026-04-11-spec-player-view-play.md (이하은)
- raw/2026-04-14-spec-team-member-and-category.md (이하은)

신규 sources 5개. 신규 wiki 페이지 11개:
- features/auth-and-account.md
- features/problem-search.md
- features/play-management.md
- features/winner-selection.md
- features/play-player.md
- features/team-member-management.md
- features/team-invitation.md
- features/category-management.md
- decisions/account-policies.md
- decisions/permission-roles.md
- decisions/scoring-display.md
- decisions/answer-edit-during-play.md

기존 페이지 갱신:
- glossary/core-terms.md — 권한/풀이 제어/검색/북마크/계정 용어 추가
- decisions/visibility-states.md — 검색 노출 조건, 12/10 기획논의 결정과 충돌 표시
- features/problem-set-creation.md — 12/10 결정과의 충돌 경고 추가
- features/problem-set-lifecycle.md — 종료→복습 전환 흐름 보강 (우승자 공개, 학습 모드 자동 종료)

발견한 주요 충돌 / lint 항목:
- 12/10 기획논의 (player뷰 source) vs 4/14 명세 (문제관리_문제생성): 생성하기 모달의 공개대상 입력 — 12/10에서 삭제 결정했으나 4/14 명세에 여전히 존재
- 1.4 (풀이관리) 오답 재제출 시 정답자/오답자 동시 표기 처리 미정
- 학습 모드 1.2/1.3은 "선착순과 동일"이라 명시 — 차이점 검증 필요

미해결 이슈 누적: 약 20건. 다음 lint 시 정리.

장애:
- tiny link `AoA-Aw` (id 54427650) → 404, 페이지 없음. 사용자 확인 필요.

## [2026-04-24] ingest | 2026-01-28-spec-result-dashboard

- 사용자가 새 page id (54493186) 제공 — "풀이결과 대시보드" 명세 (이하은, 1/28)
- (앞서 404였던 `AoA-Aw`의 대체 문서)
- 신규 페이지 4개:
  - sources/2026-01-28-spec-result-dashboard.md
  - features/result-dashboard.md
  - decisions/score-calculation.md
  - (raw) raw/2026-01-28-spec-result-dashboard.md
- 기존 페이지 갱신:
  - glossary/core-terms.md — 결과/통계 용어 추가 (우승자 화면, 정답률, 점수 등)
  - features/play-management.md — 종료 후 "풀이결과 보러가기" 진입점 보강
  - index.md — Sources/Features/Decisions에 신규 항목 추가
- 미해결 이슈: 학습 모드 결과의 종합 위치, "전체 평균" 단위, 우승자 화면 본 명세 누락, 카테고리=주제 태그 정합성

## [2026-04-24] ingest | weekly-meetings-2026-03-29-to-2025-02-02

- raw에 고정한 주간 회의록 10건을 source 페이지로 ingest
- 신규 페이지 11개:
  - sources/2026-03-29-weekly-meeting.md
  - sources/2026-03-22-weekly-meeting.md
  - sources/2026-02-22-weekly-meeting.md
  - sources/2026-01-25-weekly-meeting.md
  - sources/2026-01-11-weekly-meeting.md
  - sources/2026-01-03-weekly-meeting.md
  - sources/2025-03-01-weekly-meeting.md
  - sources/2025-02-16-weekly-meeting.md
  - sources/2025-02-09-weekly-meeting.md
  - sources/2025-02-02-weekly-meeting.md
  - decisions/early-product-direction.md
- 기존 페이지 갱신:
  - features/category-management.md — 초기 카테고리 기획 맥락 + 2026년 반영 일정 메모 추가
  - features/problem-set-creation.md — 편집 UX 후속 이슈 추가
  - features/problem-set-lifecycle.md — 삭제/학습모드/복습 운영 메모 추가
  - features/play-management.md — 중간 참여/종료 팝업/사이드바 규칙 메모 추가
  - features/play-player.md — 중간 참여/복습 불편 메모 추가
  - features/winner-selection.md — 워딩/종료 팝업 후속 메모 추가
  - features/result-dashboard.md — 닉네임 노출/평균 지표 후속 메모 추가
  - features/auth-and-account.md — 로그아웃/약관/온보딩 후속 메모 추가
  - decisions/visibility-states.md — 비공개 문제셋 접근 이슈 반영
  - glossary/core-terms.md — 문제 신뢰성/개인 워크스페이스/온보딩 용어 추가
  - index.md — Sources/Decisions 카탈로그 갱신
- 미해결 이슈:
  - 온보딩은 방향만 있고 별도 상세 명세 페이지 없음
  - 팀 탈퇴/팀 삭제/개인 워크스페이스는 회의에서 반복 언급되지만 독립 명세 페이지가 아직 없음
