# Wiki Index

mait 지식 베이스의 모든 페이지 카탈로그. 새 페이지가 생기거나 요약이 바뀔 때마다 갱신.

## Sources (원본 요약)

- [2025-10-24 로그인/회원가입/마이페이지 명세서 (전민재)](sources/2025-10-24-spec-auth-mypage.md)
- [2025-12-17 문제 검색 명세서 (이하은)](sources/2025-12-17-spec-problem-search.md)
- [2026-01-28 풀이결과 대시보드 명세서 (이하은)](sources/2026-01-28-spec-result-dashboard.md)
- [2026-04-11 문제관리_풀이관리 명세서 (이하은)](sources/2026-04-11-spec-play-management.md) — maker 측 풀이 진행 화면
- [2026-04-11 (player뷰) 문제 풀기 명세서 (이하은)](sources/2026-04-11-spec-player-view-play.md) — player 측 풀이 화면 + 12/10 기획논의
- [2026-04-14 문제관리_문제생성 명세서 (이하은)](sources/2026-04-14-spec-problem-management.md) — 문제셋 생성 maker 측 전체 플로우
- [2026-04-14 팀관리 (멤버 + 카테고리) 명세서 (이하은)](sources/2026-04-14-spec-team-member-and-category.md)

## Features (기능 / 기획 아이템)

### 인증 / 계정
- [로그인 / 회원가입 / 마이페이지](features/auth-and-account.md)

### 문제 셋
- [문제셋 생성 플로우](features/problem-set-creation.md) — 메인 화면 → 정보 입력 → 편집 → 생성하기
- [문제셋 라이프사이클](features/problem-set-lifecycle.md) — 임시저장 / 실시간(예정·진행·종료) / 학습풀이 / 복습 상태 머신
- [질문 편집기](features/question-editor.md) — 객관식·주관식·빈칸·순서 4가지 유형
- [문제 검색](features/problem-search.md) — 비회원/회원 흐름, 북마크, 내 그룹에 추가

### 풀이
- [풀이관리 (maker 측)](features/play-management.md) — 선착순/학습 모드 진행 화면
- [진출자 선정 (선착순)](features/winner-selection.md) — 다음 라운드 진출자 결정
- [문제 풀기 (player 측)](features/play-player.md) — 실시간/학습/복습 3가지 모드
- [풀이결과 대시보드](features/result-dashboard.md) — 메인(전체 통계) + 상세(셋별 결과)

### 팀 / 카테고리
- [팀 멤버 권한 관리](features/team-member-management.md)
- [팀 사용자 초대](features/team-invitation.md) — 직접 추가 + 초대 링크
- [카테고리 관리](features/category-management.md)

## Decisions (제품·아키텍처 결정)

- [공개 범위 정책](decisions/visibility-states.md) — 전체/그룹/비공개. 복습에서만 설정. 검색은 복습+전체공개만. 12/10 기획논의 충돌 표시
- [임시저장 / 자동저장 정책](decisions/auto-save-behavior.md) — 수동 임시저장 + 1분 단위 자동저장
- [계정 정책](decisions/account-policies.md) — 비밀번호/닉네임/전화번호/이름/이메일/약관
- [권한 체계](decisions/permission-roles.md) — owner/maker/player 정의와 차이
- [풀이 중 답안 수정 정책](decisions/answer-edit-during-play.md) — 인정답안만 추가 가능
- [채점/정답 표시 정책](decisions/scoring-display.md) — 복습 모드 부분 채점
- [점수 산정 정책](decisions/score-calculation.md) — 탈락해도 분모는 전체 문제 수

## Glossary (용어)

- [핵심 용어](glossary/core-terms.md) — 권한·콘텐츠·모드·저장·검색·결과·계정 용어 통합

## FAQ (반복 질문)

_아직 없음. 사용자 질문이 반복되면 여기 정리._
