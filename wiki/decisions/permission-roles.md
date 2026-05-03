---
title: 권한 체계 (owner / maker / player)
type: decision
status: draft
sources: [raw/2026-04-14-spec-team-member-and-category.md, raw/2026-04-14-spec-problem-management.md, raw/2025-12-17-spec-problem-search.md, raw/2025-11-07-weekly-meeting.md, raw/2025-12-10-weekly-meeting.md, raw/2025-12-23-weekly-meeting.md, raw/2026-04-19-weekly-meeting.md]
updated: 2026-05-03
---

# 권한 체계 (owner / maker / player)

mait의 모든 팀·문제셋 권한은 **owner > maker > player** 3단계로 구성된다.

## 권한별 정의

| 권한 | 정의 | 핵심 권한 |
|---|---|---|
| **owner** | 팀 소유자 (1명) | 팀 자체 관리. 멤버 리스트에서 **삭제 불가** (체크박스 없음). maker 영역 하단에 별도 표시 |
| **maker** | 문제 편집자 | 문제셋 생성·편집, 풀이관리, 카테고리 관리, 멤버 초대(권한에 따라) |
| **player** | 문제 풀이자 | 문제 풀기, 채점 결과 확인 |

2026-04-19 회의 기준 OWNER는 팀 탈퇴가 불가능한 것으로 정리됐다. 팀 탈퇴/삭제의 데이터 처리는 [팀 탈퇴/삭제](../features/team-exit-and-deletion.md)에서 별도 추적한다.

## 초대 시 동작 차이

| 권한 | 승인 절차 |
|---|---|
| maker | O / X 선택 가능. O 설정 시 관리자 승인 후 등록 |
| player | **X 고정** — 자동 승인 |

## 권한 전환

- 컬럼 사이 `>>` / `<<` 버튼으로 maker ↔ player 자유 전환.
- owner의 양도 흐름은 명세 누락 (미해결).

## 컨텍스트별 적용

### 풀이
- maker: [풀이관리](../features/play-management.md) — 시작/종료, 토글, 진출자 선정.
- player: [문제 풀기](../features/play-player.md) — 풀이 화면.
- owner: 명세상 maker 권한 포함 (자체 정의 없음 — 검증 필요).

### 검색·북마크
- 비회원: 검색 + 2개 미리보기.
- 회원: + 북마크(컬렉션 저장).
- maker(owner 포함): + 검색에서 "내 그룹에 추가" 가능.

### 공개 범위
- 공개 범위는 권한과 무관 — [decisions/visibility-states.md](./visibility-states.md) 참고.

## 운영 메모

- 2025-11-07 회의에서는 정책 코드리뷰와 정책 API 작업이 같이 남아, 권한 모델이 문서 정의를 넘어 API 수준으로 내려가야 한다는 문제가 드러났다. [2025-11-07 주간 회의록](../sources/2025-11-07-weekly-meeting.md)
- 2025-12-10 회의에서는 `API 권한 관리`가 별도 작업 항목으로 분리됐다. [2025-12-10 주간 회의록](../sources/2025-12-10-weekly-meeting.md)
- 2025-12-23~31 회의에서는 실제 조회 API 권한 이슈와 권한 draft가 함께 언급돼, 정의와 구현 사이의 정합성 문제가 운영 이슈로 이어졌음을 확인할 수 있다. [2025-12-23 ~ 2025-12-31 주간 회의록](../sources/2025-12-23-weekly-meeting.md)
- 2026-04-19 회의에서는 OWNER가 팀 탈퇴할 수 없다는 예외와 탈퇴/삭제 메일 수신 범위가 팀 권한 운영 이슈로 다시 올라왔다. [2026-04-19 주간 회의록](../sources/2026-04-19-weekly-meeting.md)

## 미해결

- owner의 maker 권한 자동 포함 여부 (명시 없이 maker 액션 수행하는 경우 다수)
- owner 양도 흐름
- 한 사용자가 다수 팀에서 다른 권한을 가질 수 있는지 (당연하지만 명시 없음)

## 출처

- [sources/2026-04-14-spec-team-member-and-category.md](../sources/2026-04-14-spec-team-member-and-category.md)
- [sources/2025-12-17-spec-problem-search.md](../sources/2025-12-17-spec-problem-search.md) (회원 검색의 owner 언급)
