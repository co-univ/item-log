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

## [2026-04-25] ingest | scrum-weeklies-2025-10-to-2025-12

- `공작시 스크럼` Notion DB의 2025-10 ~ 2025-12 주간 회의록 9건을 raw/source로 ingest
- 신규 페이지 10개:
  - sources/2025-10-01-weekly-meeting.md
  - sources/2025-10-16-weekly-meeting.md
  - sources/2025-10-23-weekly-meeting.md
  - sources/2025-10-30-weekly-meeting.md
  - sources/2025-11-07-weekly-meeting.md
  - sources/2025-11-12-weekly-meeting.md
  - sources/2025-12-02-weekly-meeting.md
  - sources/2025-12-10-weekly-meeting.md
  - sources/2025-12-23-weekly-meeting.md
  - features/ai-question-generation.md
- 기존 페이지 갱신:
  - features/auth-and-account.md
  - features/problem-search.md
  - features/problem-set-creation.md
  - features/problem-set-lifecycle.md
  - features/play-management.md
  - features/play-player.md
  - features/result-dashboard.md
  - features/team-member-management.md
  - features/team-invitation.md
  - decisions/auto-save-behavior.md
  - decisions/permission-roles.md
  - decisions/scoring-display.md
  - decisions/visibility-states.md
  - index.md
- Jira 신규 백로그 4건 생성:
  - MAIT-129 문제 풀이 시 제거된 유저 제출 차단
  - MAIT-130 팀 초대 승락 및 초대 세부사항 전달 흐름 구현
  - MAIT-131 AI 문제 생성 API 연동 및 운영 안정화
  - MAIT-132 API 권한 관리 정책 정리 및 반영

## [2026-04-25] ingest | mait-main-weeklies-2025-10-to-2025-12

- 메인 `MAIT 회의록` Notion DB의 2025-10-12 ~ 2025-12-21 주간 회의록 9건을 raw/source로 ingest
- 신규 페이지 9개:
  - sources/2025-10-12-weekly-meeting.md
  - sources/2025-10-19-weekly-meeting.md
  - sources/2025-10-26-weekly-meeting.md
  - sources/2025-11-02-weekly-meeting.md
  - sources/2025-11-09-weekly-meeting.md
  - sources/2025-11-16-weekly-meeting.md
  - sources/2025-11-23-weekly-meeting.md
  - sources/2025-12-07-weekly-meeting.md
  - sources/2025-12-21-weekly-meeting.md
- 기존 페이지 갱신:
  - features/problem-search.md
  - decisions/visibility-states.md
  - features/problem-set-creation.md
  - features/play-management.md
  - features/winner-selection.md
  - features/team-member-management.md
  - features/team-invitation.md
  - features/auth-and-account.md
  - features/result-dashboard.md
  - features/ai-question-generation.md
  - decisions/auto-save-behavior.md
  - features/play-player.md
  - index.md
- Jira 신규 백로그 3건 생성:
  - MAIT-133 풀이결과 대시보드 통계 요구사항 정리 및 반영
  - MAIT-134 공통 로딩/에러 상태 화면 정리
  - MAIT-135 OG 태그 적용 및 대외 공유 메타데이터 정리
- 정정 메모:
  - 같은 날짜대의 `공작시 스크럼` DB 배치는 별도 기록으로 유지
  - 메인 `MAIT 회의록` 보드 누락분은 이번 ingest로 별도 보강 완료

## [2026-05-03] ingest | 2026-04-19-weekly-meeting

- `raw/2026-04-19-weekly-meeting.md`를 source/wiki에 반영
- 신규 페이지:
  - sources/2026-04-19-weekly-meeting.md
  - features/team-exit-and-deletion.md
- 기존 페이지 갱신:
  - features/team-member-management.md
  - features/problem-set-lifecycle.md
  - features/play-player.md
  - features/winner-selection.md
  - features/category-management.md
  - features/auth-and-account.md
  - decisions/permission-roles.md
  - glossary/core-terms.md
  - index.md
- 주요 반영: 팀 탈퇴 데이터 유지, 팀 삭제 완전 삭제 방향, 등수정보 노출 방향, 우승자 선정 후 닫기/뒤로가기 플로우

## [2026-05-03] ingest | 2026-04-26-weekly-meeting

- Notion 페이지 `34a87d59-2b6e-8008-abe1-c0fc3b1488f2`를 `raw/2026-04-26-weekly-meeting.md`로 스냅샷 저장 후 wiki에 반영
- 신규 페이지:
  - sources/2026-04-26-weekly-meeting.md
  - features/product-analytics.md
  - decisions/knowledge-base-ingest-process.md
- 기존 페이지 갱신:
  - features/team-exit-and-deletion.md
  - features/problem-set-lifecycle.md
  - features/play-management.md
  - features/play-player.md
  - features/category-management.md
  - features/ai-question-generation.md
  - features/auth-and-account.md
  - glossary/core-terms.md
  - index.md
- 주요 반영: 4/21 배포 후속, 학습모드 API/프론트 진행상황, 카테고리명 40자 제한, GA4 지표 후보, 지식 베이스 운영 원칙
- 주의: Notion 상태 속성은 아직 `예정`으로 남아 있으나, 실제 회의 내용이 작성되어 있어 사용자 요청에 따라 ingest
