---
title: 2026-05-04 주간 회의록
type: source
status: stable
sources: [raw/2026-05-04-weekly-meeting.md]
updated: 2026-05-08
source_url: https://www.notion.so/35587d592b6e807c9d36f6cd61f85c1d
source_date: 2026-05-04
participants: [신유승, 조원영, 손민재, 오지연, 이하은, 전민재]
topics: [배포 준비, 학습모드, 등수정보, 알림, 카테고리, 개인 워크스페이스, GA4, 인증]
---

# 2026-05-04 주간 회의록

5월 12일 배포와 5월 15일 코테이토 사용을 앞두고 남은 작업과 사용자 흐름의 빈틈을 점검한 회의다. 등수정보 노출은 1등과의 시간 차이, 실시간 참여 인원, 제출 답안 목록, 이모지 리액션처럼 player가 풀이 중 체감할 정보로 구체화됐다. 알림은 owner/maker/player별 수신자와 클릭 후 이동 위치를 나눠 정리했고, 인정답안 추가로 오답이 정답이 된 player에게 학습모드 채점 화면으로 보내는 알림도 논의됐다. 학습모드는 배포 전 남은 제출/채점과 별개로, 완료 후 나가기/결과 재확인/관리자뷰/대시보드 API가 개선 후보로 남았다. 카테고리는 40자 초과 입력을 막기보다 허용하면서 초과 상태를 보여주는 방향이 디자인 메모로 추가됐고, 토큰 재발급 실패는 신규 유지보수 티켓으로 추적하기로 했다.

## 핵심 takeaway

- 5월 12일 배포 후보는 카테고리, 복습모드 제출 동선 수정, 개인 워크스페이스로 정리됐다. 근거: [raw/2026-05-04-weekly-meeting.md](../../raw/2026-05-04-weekly-meeting.md) `§3. 기획 회의`, `§4. 할일 정리`. 영향: [카테고리 관리](../features/category-management.md), [문제 풀기](../features/play-player.md), [핵심 용어](../glossary/core-terms.md)
- 등수정보는 정답자/오답자별 제출 현황, 1등과의 시간 차이, 실시간 참여 인원, 제출 답안 목록, 이모지 리액션을 포함하는 player 화면 정보로 구체화됐다. 우선 작업은 `1등과 몇 초 차이인지`와 `실시간 참여 인원 표기`다. 근거: [raw/2026-05-04-weekly-meeting.md](../../raw/2026-05-04-weekly-meeting.md) `§등수정보 노출`. 영향: [문제 풀기](../features/play-player.md)
- 알림은 역할과 상황별 이동 규칙이 정리됐다. owner의 팀 초대 완료/팀 탈퇴 알림은 멤버관리로 이동하고, maker/player의 팀 삭제 또는 본인 탈퇴 알림은 이동 없이 안내하며, 인정답안 추가로 오답이 정답 처리된 player는 학습모드 채점 화면으로 이동한다. 근거: [raw/2026-05-04-weekly-meeting.md](../../raw/2026-05-04-weekly-meeting.md) `§알림`. 영향: [알림](../features/user-notifications.md), [팀 탈퇴/삭제](../features/team-exit-and-deletion.md), [문제 풀기](../features/play-player.md)
- 학습모드는 배포 후 사용자가 나가면 결과를 다시 못 볼 수 있다는 인지 문제, 풀이 완료 결과 재확인, 채점 이후 디자인, 관리자뷰의 팀원 풀이 현황, 대시보드 API가 개선 후보로 남았다. 근거: [raw/2026-05-04-weekly-meeting.md](../../raw/2026-05-04-weekly-meeting.md) `§학습모드 배포건`, `§백엔드`. 영향: [풀이관리](../features/play-management.md), [문제 풀기](../features/play-player.md), [풀이결과 대시보드](../features/result-dashboard.md)
- 카테고리명은 4월 26일에는 영어 기준 40자 제한으로 기록됐지만, 5월 4일 디자인 메모에서는 40자 초과 입력도 허용하는 방향이 추가됐다. 최종 규칙은 제한과 초과 표시 사이에서 정리가 필요하다. 근거: [raw/2026-05-04-weekly-meeting.md](../../raw/2026-05-04-weekly-meeting.md) `§디자인`, `§기획`. 영향: [카테고리 관리](../features/category-management.md)
- 토큰 재발급 실패는 신규 `MAIT-137`, 이모지 리액션은 `MAIT-138`, 문제 제목 기본값 삭제는 `MAIT-139`, 새 기능 출시 안내 방식은 `MAIT-140`으로 생성됐다. 근거: [raw/2026-05-04-weekly-meeting.md](../../raw/2026-05-04-weekly-meeting.md) `§7. 할일 티켓 정리`. 영향: [로그인 / 회원가입 / 마이페이지](../features/auth-and-account.md), [문제셋 생성 플로우](../features/problem-set-creation.md), [문제 풀기](../features/play-player.md)

## 영향받는 wiki 페이지

- [features/auth-and-account.md](../features/auth-and-account.md)
- [features/play-player.md](../features/play-player.md)
- [features/play-management.md](../features/play-management.md)
- [features/problem-set-lifecycle.md](../features/problem-set-lifecycle.md)
- [features/category-management.md](../features/category-management.md)
- [features/product-analytics.md](../features/product-analytics.md)
- [features/team-exit-and-deletion.md](../features/team-exit-and-deletion.md)
- [features/user-notifications.md](../features/user-notifications.md)
- [features/team-invitation.md](../features/team-invitation.md)
- [features/team-member-management.md](../features/team-member-management.md)
- [features/result-dashboard.md](../features/result-dashboard.md)
- [features/problem-set-creation.md](../features/problem-set-creation.md)
- [glossary/core-terms.md](../glossary/core-terms.md)

## 미해결

- Notion 페이지 상태 속성은 아직 `예정`으로 남아 있다.
- 자동 종료 엣지 케이스는 "안대로 진행"으로 정리됐지만, 그 안의 상세 내용은 디스코드 스레드에 있어 raw/wiki에 직접 반영되지 않았다.
- 카테고리명 40자 정책은 제한인지 초과 허용+표시인지 최종 문안이 필요하다.
- 알림의 실시간모드 인정답안 변경 케이스는 상세 흐름이 비어 있다.
