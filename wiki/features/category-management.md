---
title: 카테고리 관리
type: feature
status: draft
sources: [raw/2026-04-14-spec-team-member-and-category.md, raw/2026-04-30-spec-team-member-and-category.md, raw/2026-04-14-spec-problem-management.md, raw/2025-02-02-weekly-meeting.md, raw/2025-02-09-weekly-meeting.md, raw/2026-02-22-weekly-meeting.md, raw/2026-03-29-weekly-meeting.md, raw/2026-04-19-weekly-meeting.md, raw/2026-04-26-weekly-meeting.md, raw/2026-05-04-weekly-meeting.md, raw/2026-05-10-weekly-meeting.md, raw/2026-05-10-spec-personal-workspace.md, raw/2026-05-14-weekly-meeting.md, raw/2026-05-26-weekly-meeting.md]
updated: 2026-05-30
---

# 카테고리 관리

팀 단위 카테고리 CRUD. 문제 정보 입력 단계의 카테고리 드롭다운과 연동.

개인 워크스페이스에서는 `팀관리` 명칭을 `카테고리 관리`로 바꾸고, 카테고리 관리 화면은 기존과 동일하게 유지한다. 멤버관리는 비활성화한다. [개인 워크스페이스 명세서](../sources/2026-05-10-spec-personal-workspace.md)

(2/19 명세 추가)

## 주간 회의에서 드러난 맥락

- 초기 기획 단계에서는 카테고리를 문제셋 구조의 핵심 분류축으로 먼저 정의하려는 논의가 있었다. `문제를 어떤 단위로 모으고 분류할지`가 기능 상세보다 앞서는 주제였다. [2025-02-02 주간 회의록](../sources/2025-02-02-weekly-meeting.md), [2025-02-09 주간 회의록](../sources/2025-02-09-weekly-meeting.md)
- 2026-02-22 시점에는 카테고리 기획이 구현 검토를 마치고 디자인 단계로 넘어갈 정도로 성숙했다고 보고됐다. [2026-02-22 주간 회의록](../sources/2026-02-22-weekly-meeting.md)
- 2026-03-29에서는 카테고리를 4월 말~5월 초 반영 후보로 보고, 명세 확정 여부를 먼저 점검하기로 했다. [2026-03-29 주간 회의록](../sources/2026-03-29-weekly-meeting.md)
- 2026-04-19 회의에서는 카테고리 명세서 업데이트와 디자인 공유가 완료/점검 항목으로 기록됐다. [2026-04-19 주간 회의록](../sources/2026-04-19-weekly-meeting.md)
- 2026-04-26 회의에서는 카테고리 최종 디자인 전달 후, 카테고리명은 영어 기준 40자 제한으로 정리하고 40자를 넘겼을 때의 경고 문구와 명세 업데이트가 할 일로 남았다. [2026-04-26 주간 회의록](../sources/2026-04-26-weekly-meeting.md)
- 2026-05-04 회의에서는 카테고리 전달이 완료됐고, 디자인 메모에서 40자 초과 입력도 허용하는 방향이 추가됐다. 따라서 최종 정책은 `40자 제한`과 `초과 허용+표시` 사이의 정리가 필요하다. [2026-05-04 주간 회의록](../sources/2026-05-04-weekly-meeting.md)
- 2026-05-10 회의에서는 카테고리 테이블/API 작업이 체크됐고, 카테고리 추가 후 문제셋 목록이나 문제 카드에 카테고리를 노출할지 여부가 남은 의사결정으로 올라왔다. 현재 디자인에서는 바로 추가가 어려워 보이나 UI 개선 시 함께 검토하는 방향이다. [2026-05-10 주간 회의록](../sources/2026-05-10-weekly-meeting.md)
- 2026-05-14 사용자 문의에서는 카테고리를 팀별로 자유롭게 세팅하는 해시태그/공통 범위 개념으로 설명했다. 코테이토 교육팀 예시로는 `#운영체제`, `#객체지향` 같은 과목명을 넣는 사용 방식이 언급됐고, 나중에는 카테고리 선택으로 관련 문제셋을 모아보는 방향도 가능하다고 답했다. [2026-05-14 주간 회의록](../sources/2026-05-14-weekly-meeting.md)
- 2026-04-30 Confluence v7 명세는 카테고리명 중복 불가, 삭제된 동일 이름 카테고리 복구 모달, 기존 문제셋/대시보드 영향 없음, 신규 생성 후보 제외, 40자 제한을 다시 확인한다. [2026-04-30 팀관리 명세서](../sources/2026-04-30-spec-team-member-and-category.md)
- 2026-05-26 회의에서는 문제 카드 UI 개선 논의 중 카테고리 값을 현재 문제 카드에 노출하지 않는 방향으로 다시 확인했다. 다만 UI 개선 시점에는 카테고리 노출을 함께 재검토할 수 있고, 카테고리 UI 수정은 기존 `MAIT-155` 후속으로 연결했다. [2026-05-26 주간 회의록](../sources/2026-05-26-weekly-meeting.md)

## 1.1 카테고리 추가

- 카테고리명 **중복 불가** → 안내: "이미 존재하는 카테고리입니다."
- 삭제한 동일 이름 카테고리를 다시 생성하려 할 때 → **복구 모달**: "삭제된 동일 이름 카테고리가 있습니다. 기존 카테고리를 복구할까요?"

## 1.2 카테고리 삭제

- 삭제 가능.
- **이미 사용 중인 문제셋·대시보드는 영향 없음** (그대로 카테고리 표시 유지).
- 단, 삭제 이후 신규 문제셋 생성 시 카테고리 후보에서 제외.

> 즉 카테고리 삭제는 "신규 사용 차단"이지 "기존 데이터 회수"가 아님.

## 문제 정보 입력 단계와의 연동

- 카테고리 드롭다운 형식.
- 다중 선택 가능 (개수 제한 없음).
- 리스트 내 검색 또는 직접 선택.
- 선택한 카테고리는 상단으로 이동, 하단 리스트에서 제거.
- **존재하지 않는 카테고리 검색 시 직접 추가(생성) 가능** — 이때 추가된 카테고리도 카테고리 관리 페이지에 반영됨.

## 카테고리명 제한

- 2026-04-26 회의 기준으로 카테고리명은 **영어 기준 40자 제한**을 두는 방향으로 기록됐다.
- 2026-05-04 디자인 메모에서는 **40자 넘는 입력도 허용**한다고 적혀 있다.
- 따라서 현재 wiki 기준 최종 정책은 미정이다. 구현/문구는 제한을 강제할지, 입력은 허용하되 초과 상태를 보여줄지 확인해야 한다.

## 카테고리 수정 UX

- 카테고리 수정 완료는 체크 아이콘으로 처리하는 방향이다.
- 취소 동작을 위해 체크/엑스 형태를 둔다.
- 목록은 한 번에 하나씩 다루고, 최근 추가 항목은 아래로 정렬하는 방향이다.
- 이 후속은 신규 `MAIT-155`로 생성됐다.

근거: [2026-05-14 주간 회의록](../sources/2026-05-14-weekly-meeting.md).

## 관련

- [features/problem-set-creation.md](./problem-set-creation.md) — 카테고리 입력 진입점
- [sources/2026-04-14-spec-problem-management.md](../sources/2026-04-14-spec-problem-management.md) — 2.2 카테고리 항목

## 미해결

- 복구 모달의 "복구" 액션 결과 — 복구된 카테고리는 어떤 상태로 나오는지 (사용 이력 포함? 빈 상태?)
- 카테고리명 40자 제한을 한글/영문/공백/특수문자에서 어떻게 계산할지
- 40자 초과 시 입력 차단인지 초과 허용+경고인지, 그리고 경고 문구의 최종 문안
- 문제셋 목록/문제 카드에 카테고리 값을 노출할지, 노출한다면 어떤 카드 UI 개선과 함께 처리할지
- 카테고리 기반 문제셋 모아보기의 실제 제공 여부와 진입점
- 개인 워크스페이스 카테고리와 팀 카테고리의 데이터 분리/이관 기준
- 상태 기반 문제 카드 UI로 개편할 때 카테고리 값을 계속 미노출할지, 필터/검색/모아보기에서만 사용할지.

## 출처

- [sources/2026-04-14-spec-team-member-and-category.md](../sources/2026-04-14-spec-team-member-and-category.md) (2. 카테고리 관리)
- [sources/2026-04-30-spec-team-member-and-category.md](../sources/2026-04-30-spec-team-member-and-category.md)
- [sources/2025-02-02-weekly-meeting.md](../sources/2025-02-02-weekly-meeting.md)
- [sources/2025-02-09-weekly-meeting.md](../sources/2025-02-09-weekly-meeting.md)
- [sources/2026-02-22-weekly-meeting.md](../sources/2026-02-22-weekly-meeting.md)
- [sources/2026-03-29-weekly-meeting.md](../sources/2026-03-29-weekly-meeting.md)
- [sources/2026-04-19-weekly-meeting.md](../sources/2026-04-19-weekly-meeting.md)
- [sources/2026-04-26-weekly-meeting.md](../sources/2026-04-26-weekly-meeting.md)
- [sources/2026-05-04-weekly-meeting.md](../sources/2026-05-04-weekly-meeting.md)
- [sources/2026-05-10-weekly-meeting.md](../sources/2026-05-10-weekly-meeting.md)
- [sources/2026-05-14-weekly-meeting.md](../sources/2026-05-14-weekly-meeting.md)
- [sources/2026-05-26-weekly-meeting.md](../sources/2026-05-26-weekly-meeting.md)
