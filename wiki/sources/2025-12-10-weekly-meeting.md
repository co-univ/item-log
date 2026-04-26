---
title: "2025-12-10 주간 회의록 (Notion)"
type: source
status: stable
sources: [raw/2025-12-10-weekly-meeting.md]
updated: 2026-04-25
source_path: raw/2025-12-10-weekly-meeting.md
source_date: 2025-12-10
participants: [신유승, 전민재, 남기훈, 이하은, 손민재, 오지연]
topics: [복습모드 기획, 검색 구체화, 로그아웃, API 권한 관리, 제거된 유저 제출 차단]
---

# 2025-12-10 주간 회의록

12월 둘째 주 회의는 교육팀 사용을 앞두고 복습/검색/권한/로그아웃 관련 잔여 이슈를 한데 정리한 기록이다. 기획은 복습모드, 문제 생성 플로우, 검색 기획을 정리해 명세서로 넘기려 했고, 백엔드는 제거된 유저 제출 차단, 검색 로직, 로그아웃, STOMP, API 권한 관리를 후속으로 남겼다. 상단에는 도메인 변경, OG 태그, 문의 문서 링크도 함께 있어 운영/대외 사용 준비 성격이 짙다.

## 핵심 takeaway

- 복습모드와 검색 기획은 12월 둘째 주에 `명세서 정리 후 공유` 단계까지 구체화됐다. 근거: [raw/2025-12-10-weekly-meeting.md](../../raw/2025-12-10-weekly-meeting.md) `§기획 논의`, `§AI 후속 블록 스냅샷`. 영향: [문제 검색](../features/problem-search.md), [문제 풀기 (player 측)](../features/play-player.md), [공개 범위 정책](../decisions/visibility-states.md)
- `API 권한 관리`는 이 시점부터 별도 작업 축으로 남아 있었다. 근거: [raw/2025-12-10-weekly-meeting.md](../../raw/2025-12-10-weekly-meeting.md) `§파트별 공유`. 영향: [권한 체계](../decisions/permission-roles.md)
- 로그아웃과 제거된 유저 제출 차단은 모두 실제 사용 안정성 관점의 운영 이슈로 남아 있었다. 근거: [raw/2025-12-10-weekly-meeting.md](../../raw/2025-12-10-weekly-meeting.md) `§파트별 공유`. 영향: [로그인 / 회원가입 / 마이페이지](../features/auth-and-account.md), [문제 셋 라이프사이클](../features/problem-set-lifecycle.md)

## 영향받는 wiki 페이지

- [features/problem-search.md](../features/problem-search.md)
- [features/play-player.md](../features/play-player.md)
- [decisions/visibility-states.md](../decisions/visibility-states.md)
- [decisions/permission-roles.md](../decisions/permission-roles.md)
- [features/auth-and-account.md](../features/auth-and-account.md)
- [features/problem-set-lifecycle.md](../features/problem-set-lifecycle.md)
