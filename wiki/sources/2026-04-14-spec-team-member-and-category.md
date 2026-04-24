---
title: "팀관리 (멤버 + 카테고리) 명세서 (Confluence)"
type: source
status: stable
sources: [raw/2026-04-14-spec-team-member-and-category.md]
updated: 2026-04-24
source_url: https://youthing.atlassian.net/wiki/spaces/~712020e8812b2eb985491caedb51d1b356e362/pages/44433411/-
author: 이하은
source_date: 2026-04-14
---

# 팀관리 (멤버 + 카테고리) 명세서

팀 단위 권한·초대 관리 + 카테고리 관리. owner / maker / player 3단계 권한 체계.

## 핵심 요약

### 멤버 관리
- **3단계 권한**: owner(팀 소유자, 삭제 불가) > maker(편집) > player(풀이).
- **권한 전환**: maker ↔ player 자유 전환. owner는 별도 표시.
- **초대 2가지**:
  - 직접 계정 추가 — 이메일로 MAIT 가입자 검색 후 권한 지정 → 즉시 등록.
  - 초대 링크 — 권한·유효기간(1/3/7일)·승인 절차 설정 후 링크 발급.
- **승인 절차**: maker만 승인 절차 선택 가능. **player는 무조건 자동 승인**.

### 카테고리 관리
- 카테고리명 중복 불가. 동일 이름 삭제 카테고리 재생성 시 **복구 모달** 노출.
- 카테고리 삭제해도 **사용 중인 문제셋/대시보드에는 영향 없음**. 신규 생성 시 후보에서만 제외.

## 영향받는 wiki 페이지

- [features/team-member-management.md](../features/team-member-management.md) — 신규
- [features/team-invitation.md](../features/team-invitation.md) — 신규 (직접 추가 + 초대 링크)
- [features/category-management.md](../features/category-management.md) — 신규
- [decisions/permission-roles.md](../decisions/permission-roles.md) — 신규 (owner/maker/player 정의)
- [glossary/core-terms.md](../glossary/core-terms.md) — owner, 컬렉션 등 갱신

## 미해결

- 2.1에 "정확한 이메일을 입력한 경우에만 검색됨" — 부분 검색/자동완성 방지 의도인지 검증
- 2.6 "4번 페이지 안내" — 4번 항목이 명세에 없음 (원본 문서 추가 필요?)
- 카테고리 복구 모달의 "복구" 액션 결과 (복구된 카테고리는 어떤 상태로?) 명세 누락
- 권한 전환 시 owner → maker/player로의 전환은 가능한지 (owner 양도 흐름) 명세 없음
