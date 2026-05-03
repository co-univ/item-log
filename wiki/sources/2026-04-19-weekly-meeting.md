---
title: 2026-04-19 주간 회의록
type: source
status: stable
sources: [raw/2026-04-19-weekly-meeting.md]
updated: 2026-05-03
source_url: https://www.notion.so/34687d592b6e80de8c9efa0ca2304bc4
source_date: 2026-04-19
participants: [신유승, 조원영, 오지연, 이하은, 전민재]
topics: [정기배포, 팀 탈퇴, 팀 삭제, 등수정보, 온보딩, 카테고리, 우승자 선정, 학습모드]
---

# 2026-04-19 주간 회의록

4월 21일 정기배포를 앞두고 작업 아이템과 정상 동작 플로우를 점검한 회의다. 팀 탈퇴는 접근 권한을 제거하되 기존 풀이/생성 데이터를 삭제하지 않는 방향으로, 팀 삭제는 팀·멤버·초대링크·가입 신청·풀이 기록·문제셋/문제까지 완전 삭제하는 방향으로 정리됐다. 등수정보는 maker 전용 관리 화면보다 실시간 풀이 화면에서 player에게 필요한 정보를 직접 노출하는 쪽으로 논의가 이동했다. 온보딩, 카테고리, 우승자 선정 이후 플로우, 학습모드와 문제셋 삭제는 배포 전후 점검 항목으로 남았다.

## 핵심 takeaway

- 팀 탈퇴는 `접근 권한 삭제 -> 유지`와 `데이터는 삭제하지 않고 문구를 변경함`으로 기록되어, 탈퇴 사용자의 팀 접근은 막지만 기존 기록은 보존하는 방향이다. 근거: [raw/2026-04-19-weekly-meeting.md](../../raw/2026-04-19-weekly-meeting.md) `§팀 탈퇴 관련 데이터 변경 체크`. 영향: [팀 탈퇴/삭제](../features/team-exit-and-deletion.md)
- 팀 삭제는 논리 삭제 검토 후, 팀이 만든 문제셋이 남는 것이 더 어색하다는 이유로 완전 삭제 쪽으로 정리됐다. 삭제 범위에는 팀, 팀 멤버, 초대링크, 가입 신청, 풀이 기록, 문제셋과 문제가 포함된다. 근거: [raw/2026-04-19-weekly-meeting.md](../../raw/2026-04-19-weekly-meeting.md) `§팀 삭제 관련 데이터 삭제 범위 문의`. 영향: [팀 탈퇴/삭제](../features/team-exit-and-deletion.md), [문제 셋 라이프사이클](../features/problem-set-lifecycle.md)
- 등수정보는 실시간 참여 인원, 제출 현황, 최초 제출자와의 시간 차이, 정답자에게만 노출할 정보처럼 풀이 중 사용자 경험으로 재정의됐다. 근거: [raw/2026-04-19-weekly-meeting.md](../../raw/2026-04-19-weekly-meeting.md) `§AI 후속 블록 스냅샷`. 영향: [문제 풀기](../features/play-player.md)
- 우승자 선정 화면에는 `x` 버튼을 추가하고, `x` 또는 뒤로가기 시 문제 풀기 탭의 실시간 모드 페이지로 이동하는 플로우가 정리됐다. 근거: [raw/2026-04-19-weekly-meeting.md](../../raw/2026-04-19-weekly-meeting.md) `§기획`. 영향: [진출자 선정](../features/winner-selection.md)
- 온보딩 문구 축소, 순서 정보 표기, 카테고리 명세/디자인, 학습모드와 문제셋 삭제는 배포 전후 계속 따라가야 할 항목으로 남았다. 근거: [raw/2026-04-19-weekly-meeting.md](../../raw/2026-04-19-weekly-meeting.md) `§기획`, `§백엔드`, `§프론트`, `§디자인`. 영향: [로그인/회원가입/마이페이지](../features/auth-and-account.md), [카테고리 관리](../features/category-management.md), [문제 셋 라이프사이클](../features/problem-set-lifecycle.md)

## 영향받는 wiki 페이지

- [features/team-exit-and-deletion.md](../features/team-exit-and-deletion.md)
- [features/problem-set-lifecycle.md](../features/problem-set-lifecycle.md)
- [features/play-player.md](../features/play-player.md)
- [features/winner-selection.md](../features/winner-selection.md)
- [features/category-management.md](../features/category-management.md)
- [features/auth-and-account.md](../features/auth-and-account.md)

## 미해결

- 팀 탈퇴 메일 수신자가 본인+OWNER인지, MAKER까지 포함하는지 최종 문구/수신 범위 확인 필요.
- 팀 삭제 시 실시간 진행 중인 문제셋까지 삭제하는 것으로 적혔지만, 삭제 직전 사용자 경험과 통계 처리의 세부 정책은 별도 검증 필요.
- 등수정보 노출의 문제 유형별 화면, 정답자/오답자/미풀이자별 정보 차등 노출 기준은 아직 구체화 필요.
