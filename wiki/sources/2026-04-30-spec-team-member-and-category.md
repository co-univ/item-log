---
title: 팀관리 (멤버 + 카테고리) 명세서 v7
type: source
status: stable
sources: [raw/2026-04-30-spec-team-member-and-category.md]
updated: 2026-05-30
date: 2026-04-30
source_path: raw/2026-04-30-spec-team-member-and-category.md
source_url: https://youthing.atlassian.net/wiki/spaces/~712020e8812b2eb985491caedb51d1b356e362/pages/44433411
source_id: "44433411"
source_date: 2026-04-30
participants: []
topics: [팀관리, 멤버관리, 권한관리, 사용자 초대, 초대 링크, 카테고리 관리]
---

# 팀관리 (멤버 + 카테고리) 명세서 v7

Confluence `팀관리 - 멤버관리, 카테고리 관리` 문서의 2026-04-30 버전이다. 명세는 멤버 관리와 사용자 초대, 초대 링크 관리, 카테고리 관리로 구성된다. 멤버 관리는 maker/player 2컬럼 리스트와 owner 별도 표시, 승인 대기/승인 완료 상태, 권한 전환, 사용자 삭제, 무한 스크롤을 정의한다. 사용자 초대는 직접 계정 추가와 초대 링크 생성/관리로 나뉘며, maker 초대는 승인 절차를 둘 수 있고 player 초대는 자동 승인으로 고정된다. 카테고리 관리는 중복 금지, 삭제 카테고리 복구 모달, 기존 문제셋/대시보드 유지와 신규 생성 후보 제외를 핵심 규칙으로 둔다.

## 핵심 takeaway

- 멤버 관리는 좌측 maker, 우측 player 두 컬럼으로 권한 보유자 리스트를 표시한다. 승인 대기 멤버는 비활성화 상태로 최상단에 두고, owner는 maker 영역 하단에 별도로 표시하며 삭제할 수 없다. 근거: [raw/2026-04-30-spec-team-member-and-category.md](../../raw/2026-04-30-spec-team-member-and-category.md) `§1.1 사용자 리스트 표시`, `§1.4 사용자 삭제`. 영향: [팀 멤버 권한 관리](../features/team-member-management.md), [권한 체계](../decisions/permission-roles.md)
- maker 초대는 승인 절차가 존재할 수 있고, 승인 시 상태가 `승인됨`으로 바뀌며 거절 시 목록에서 제거된다. 근거: [raw/2026-04-30-spec-team-member-and-category.md](../../raw/2026-04-30-spec-team-member-and-category.md) `§1.2 권한 승인/거절`. 영향: [팀 멤버 권한 관리](../features/team-member-management.md), [팀 사용자 초대](../features/team-invitation.md)
- 직접 계정 추가는 정확한 이메일로 MAIT 가입자를 검색한 뒤 maker/player 권한을 선택해 초대하고, 성공 시 해당 권한 리스트에 즉시 반영한다. 근거: [raw/2026-04-30-spec-team-member-and-category.md](../../raw/2026-04-30-spec-team-member-and-category.md) `§2.1 직접 계정 추가`. 영향: [팀 사용자 초대](../features/team-invitation.md)
- 초대 링크는 권한 유형, 유효기간 1/3/7일, 승인 절차 여부를 설정해 발급한다. player 초대 링크는 승인 절차가 항상 `X`로 고정된다. 근거: [raw/2026-04-30-spec-team-member-and-category.md](../../raw/2026-04-30-spec-team-member-and-category.md) `§2.2 초대 링크 생성`, `§2.5 승인 절차 동작 조건`. 영향: [팀 사용자 초대](../features/team-invitation.md)
- 초대 링크 접속 화면은 링크 상태, 로그인 여부, 승인 필요 여부에 따라 로그인/회원가입/참여/확인/홈 이동 버튼을 다르게 보여준다. 근거: [raw/2026-04-30-spec-team-member-and-category.md](../../raw/2026-04-30-spec-team-member-and-category.md) `§2.6 초대 링크 접속 화면`. 영향: [팀 사용자 초대](../features/team-invitation.md)
- 카테고리명은 중복 불가이고, 삭제한 동일 이름 카테고리를 다시 생성하려 하면 복구 모달을 띄운다. 카테고리 삭제는 기존 문제셋/대시보드에는 영향을 주지 않고, 삭제 이후 신규 문제셋 생성 후보에서 제외하는 방식이다. 근거: [raw/2026-04-30-spec-team-member-and-category.md](../../raw/2026-04-30-spec-team-member-and-category.md) `§2. 카테고리 관리`. 영향: [카테고리 관리](../features/category-management.md)

## 영향받는 wiki 페이지

- [features/team-member-management.md](../features/team-member-management.md)
- [features/team-invitation.md](../features/team-invitation.md)
- [features/category-management.md](../features/category-management.md)
- [decisions/permission-roles.md](../decisions/permission-roles.md)
- [glossary/core-terms.md](../glossary/core-terms.md)

## 미해결

- 직접 계정 추가의 정확한 이메일 검색이 부분 검색/자동완성을 의도적으로 막는 정책인지 확인이 필요하다.
- 초대 링크 승인 대기 상태에서 안내하는 `4번 페이지`의 본문은 이 명세 안에 없다.
- 카테고리명 40자 제한이 2026-05-04 회의의 `초과 입력 허용` 디자인 메모와 어떻게 정리되는지 확인이 필요하다.
