---
title: "2025-11-07 주간 회의록 (Notion)"
type: source
status: stable
sources: [raw/2025-11-07-weekly-meeting.md]
updated: 2026-04-25
source_path: raw/2025-11-07-weekly-meeting.md
source_date: 2025-11-07
participants: [신유승, 남기훈, 손민재, 조원영]
topics: [출시 전 블로커, 문제 검색, 팀 초대 승락, 정책 API, 학습/복습 준비, 배포]
---

# 2025-11-07 주간 회의록

11월 첫째 주 회의는 출시 직전 남은 블로커를 백엔드/프론트 기준으로 한꺼번에 펼쳐 본 회의다. 문제 생성, 풀이관리, 학습/복습 준비, 검색, 팀 초대 승락, 메인 서버 배포, 로그 서버 세팅, 정책 API 작업이 동시에 남아 있었다. 정책 코드리뷰와 SQL 메모까지 붙어 있어 문서 논의가 API 수준으로 내려오던 시기임이 드러난다. 전체적으로 제품 기능과 운영 준비가 압축된 릴리스 직전 점검 회의다.

## 핵심 takeaway

- 문제 검색, 풀이관리, 팀 초대 승락은 출시 직전 해결해야 할 핵심 블로커로 같이 묶여 있었다. 근거: [raw/2025-11-07-weekly-meeting.md](../../raw/2025-11-07-weekly-meeting.md) `§백엔드/프론트 블로커`, `§AI 후속 블록 스냅샷`. 영향: [문제 검색](../features/problem-search.md), [풀이관리 (maker 측)](../features/play-management.md), [팀 사용자 초대](../features/team-invitation.md)
- 정책 관련 코드리뷰와 정책 API 작업은 권한/정책 논의가 실제 API 규칙 정리 단계로 옮겨갔다는 신호다. 근거: [raw/2025-11-07-weekly-meeting.md](../../raw/2025-11-07-weekly-meeting.md) `§백엔드/프론트 블로커`. 영향: [권한 체계](../decisions/permission-roles.md)
- 학습/복습 모드는 이 시점에 이미 `준비해야 할 제품 영역`으로 따로 분리되어 있었다. 근거: [raw/2025-11-07-weekly-meeting.md](../../raw/2025-11-07-weekly-meeting.md) `§백엔드/프론트 블로커`. 영향: [문제 셋 라이프사이클](../features/problem-set-lifecycle.md), [문제 풀기 (player 측)](../features/play-player.md)

## 영향받는 wiki 페이지

- [features/problem-search.md](../features/problem-search.md)
- [features/play-management.md](../features/play-management.md)
- [features/team-invitation.md](../features/team-invitation.md)
- [decisions/permission-roles.md](../decisions/permission-roles.md)
- [features/problem-set-lifecycle.md](../features/problem-set-lifecycle.md)
- [features/play-player.md](../features/play-player.md)
