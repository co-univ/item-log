---
title: 팀 멤버 권한 관리
type: feature
status: draft
sources: [raw/2026-04-14-spec-team-member-and-category.md]
updated: 2026-04-24
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
- [decisions/permission-roles.md](../decisions/permission-roles.md) — owner/maker/player 권한 정의

## 미해결

- owner 권한 양도 흐름 (owner → 다른 maker로 변경 가능한가)

## 출처

- [sources/2026-04-14-spec-team-member-and-category.md](../sources/2026-04-14-spec-team-member-and-category.md) (1. 멤버 관리)
