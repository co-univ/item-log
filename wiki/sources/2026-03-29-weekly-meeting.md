---
title: "2026-03-29 주간 회의록 (Notion)"
type: source
status: stable
sources: [raw/2026-03-29-weekly-meeting.md]
updated: 2026-04-24
source_path: raw/2026-03-29-weekly-meeting.md
source_date: 2026-03-29
participants: [이하은, 전민재, 손민재, 조원영, 신유승]
topics: [실시간 중간 참여, 문제셋 삭제 정책, 온보딩, 학습 모드, 카테고리, 팀 탈퇴/삭제]
---

# 2026-03-29 주간 회의록

3월 31일 정기배포와 4월 5일 대면 회의를 앞두고, 운영 안정성과 남은 정책 이슈를 정리한 주간 회의록이다. 핵심은 실시간 모드 중간 참여 처리, 문제셋 삭제 동선, 학습모드의 범위 재정의, 카테고리 반영 일정 점검이었다. 계정 영역에서는 약관 동의 체크박스 해제 이슈와 로그아웃 이후 무한 로딩 같은 운영성 버그가 다시 언급됐다. 사용자 적응 측면에서는 메인 화면 안내와 기능별 튜토리얼을 분리한 온보딩 개선 방향이 처음 명시적으로 정리됐다.

## 핵심 takeaway

- 실시간 모드 중간 참여자는 `풀 수 없는 상태`를 명확히 안내하는 방향으로 정리됐다. 유저 식별은 닉네임 기준으로 맞추고, 백엔드 알림 토픽과 프론트 토스트/플레이어 뷰가 함께 필요하다. 근거: [raw/2026-03-29-weekly-meeting.md](../../raw/2026-03-29-weekly-meeting.md) `§AI 후속 블록 스냅샷`. 영향: [풀이관리](../features/play-management.md), [문제 풀기](../features/play-player.md)
- 문제셋 삭제는 단순 삭제가 아니라 `풀이 전 / 진행 중 / 완료 후` 상태에 따라 영향이 다르다는 운영 관점이 확인됐다. 특히 실시간 모드 삭제는 대시보드 통계와 플레이어 경험까지 같이 고려해야 한다. 근거: [raw/2026-03-29-weekly-meeting.md](../../raw/2026-03-29-weekly-meeting.md) `§AI 후속 블록 스냅샷`. 영향: [문제 셋 라이프사이클](../features/problem-set-lifecycle.md)
- 온보딩은 메인 화면 가이드와 상세 기능 튜토리얼을 분리하는 방향으로 논의됐지만, 노출 대상과 횟수 기준은 미정으로 남았다. 근거: [raw/2026-03-29-weekly-meeting.md](../../raw/2026-03-29-weekly-meeting.md) `§AI 후속 블록 스냅샷`. 영향: [로그인 / 회원가입 / 마이페이지](../features/auth-and-account.md)
- 학습모드는 실시간모드의 단순 변형이 아니라 개인 학습과 팀 스터디를 함께 담는 더 넓은 흐름으로 봐야 한다는 의견이 정리됐다. 근거: [raw/2026-03-29-weekly-meeting.md](../../raw/2026-03-29-weekly-meeting.md) `§AI 후속 블록 스냅샷`. 영향: [문제 셋 라이프사이클](../features/problem-set-lifecycle.md)
- 카테고리는 4월 말~5월 초 반영 후보로 관리되고 있었고, 구현보다 명세 확정 여부 점검이 선행 과제로 남아 있었다. 근거: [raw/2026-03-29-weekly-meeting.md](../../raw/2026-03-29-weekly-meeting.md) `§AI 후속 블록 스냅샷`. 영향: [카테고리 관리](../features/category-management.md)

## 영향받는 wiki 페이지

- [features/play-management.md](../features/play-management.md)
- [features/play-player.md](../features/play-player.md)
- [features/problem-set-lifecycle.md](../features/problem-set-lifecycle.md)
- [features/category-management.md](../features/category-management.md)
- [features/auth-and-account.md](../features/auth-and-account.md)

