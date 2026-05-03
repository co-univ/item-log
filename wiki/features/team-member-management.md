---
title: 팀 멤버 권한 관리
type: feature
status: draft
sources: [raw/2026-04-14-spec-team-member-and-category.md, raw/2025-10-23-weekly-meeting.md, raw/2025-10-26-weekly-meeting.md, raw/2025-10-30-weekly-meeting.md, raw/2025-11-02-weekly-meeting.md, raw/2025-12-02-weekly-meeting.md, raw/2025-12-07-weekly-meeting.md, raw/2025-12-10-weekly-meeting.md, raw/2026-04-19-weekly-meeting.md, raw/2026-04-26-weekly-meeting.md]
updated: 2026-05-03
---

# 팀 멤버 권한 관리

팀 페이지의 멤버 리스트 + 권한 변경 UI. 권한 정의 자체는 [decisions/permission-roles.md](../decisions/permission-roles.md).

## 1.1 사용자 리스트 표시

- **2 컬럼**: 좌측 `maker`, 우측 `player`.
- 각 컬럼은 권한 보유자 리스트.
- 체크박스로 개별 선택 (삭제·권한 이동에 사용).
- **승인 대기 멤버** — 비활성화 상태, 우측에 승인/거절 버튼, 리스트 최상단.
- **승인 완료 멤버** — 활성화, 우측에 권한 텍스트(owner/maker/player), 하단.
- **owner는 maker 영역 하단에 별도 표시.**

## 1.2 권한 승인/거절

- maker 초대 시 승인 절차가 활성화 가능.
- `승인` 클릭 → 모달: "000님의 maker 권한을 승인/거절하시겠습니까?"
- 확인 → 상태 `승인됨`.
- 거절 → 목록에서 제거.

## 1.3 권한 전환

- 컬럼 사이 `>>` (player로 전환), `<<` (maker로 전환) 버튼.
- 사용자 체크박스 선택 후 버튼 활성화.
- 전환 후 양 리스트 자동 갱신.

## 1.4 사용자 삭제

- 다중 체크박스 선택 + 삭제 버튼.
- 모달: "선택한 계정을 삭제하시겠습니까?"
- **owner는 삭제 불가** → 체크박스 자체가 없음.

## 1.5 로드 방식

- 멤버 수가 많을 때 **무한 스크롤**.

## 관련

- [features/team-invitation.md](./team-invitation.md) — 멤버 추가 흐름
- [features/team-exit-and-deletion.md](./team-exit-and-deletion.md) — 팀 탈퇴/팀 삭제 데이터 처리
- [decisions/permission-roles.md](../decisions/permission-roles.md) — owner/maker/player 권한 정의

## 주간 회의에서 나온 후속 메모

- 2025-10-23 회의부터 팀관리 기획이 별도 과제로 올라와 있었다. [2025-10-23 주간 회의록](../sources/2025-10-23-weekly-meeting.md)
- 2025-10-26 회의에서는 팀관리 초안 안에 계정 제거와 maker/player 권한 변경, 승인/거절 흐름까지 넓은 범위가 이미 포함돼 있었다. [2025-10-26 주간 회의록](../sources/2025-10-26-weekly-meeting.md)
- 2025-10-30 회의에서는 팀관리 기획이 완료 처리되며 제품 범위 안으로 편입됐다. [2025-10-30 주간 회의록](../sources/2025-10-30-weekly-meeting.md)
- 2025-11-02 회의에서는 완성본 공유와 함께 검색 가능 조건, 승인 흐름, 만료 시간처럼 실제 운영 조건이 다시 점검됐다. [2025-11-02 주간 회의록](../sources/2025-11-02-weekly-meeting.md)
- 2025-12-02 회의에서는 `팀 관리에서 팀원 권한 이동`이 실제 작업 항목으로 처리됐다. [2025-12-02 주간 회의록](../sources/2025-12-02-weekly-meeting.md)
- 2025-12-07 회의에서도 팀 역할 이동 문의 문서가 다시 연결돼, 명세와 운영 질문을 함께 관리해야 하는 영역임이 드러났다. [2025-12-07 주간 회의록](../sources/2025-12-07-weekly-meeting.md)
- 2025-12-10 회의에서도 팀원 권한 이동 관련 문의 문서가 다시 연결돼, 명세/문의 정합성이 계속 중요했다. [2025-12-10 주간 회의록](../sources/2025-12-10-weekly-meeting.md)
- 2026-04-19 회의에서는 팀 탈퇴와 팀 삭제가 별도 데이터 처리 정책으로 구체화됐고, 2026-04-26 회의에서는 메일 수신과 삭제 데이터 보정이 배포 후 확인 항목으로 남았다. [2026-04-19 주간 회의록](../sources/2026-04-19-weekly-meeting.md), [2026-04-26 주간 회의록](../sources/2026-04-26-weekly-meeting.md)

## 미해결

- owner 권한 양도 흐름 (owner → 다른 maker로 변경 가능한가)
- 팀 탈퇴/삭제는 [팀 탈퇴/삭제](./team-exit-and-deletion.md)에서 별도 추적

## 출처

- [sources/2026-04-14-spec-team-member-and-category.md](../sources/2026-04-14-spec-team-member-and-category.md) (1. 멤버 관리)
