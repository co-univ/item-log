---
title: "2025-10-19 주간 회의록 (Notion)"
type: source
status: stable
sources: [raw/2025-10-19-weekly-meeting.md]
updated: 2026-04-25
source_path: raw/2025-10-19-weekly-meeting.md
source_date: 2025-10-19
participants: [신유승, 조원영, 이하은, 손민재, 전민재]
topics: [로그인/회원가입 흐름, 문제 검색 조건, 풀이 중 정답 수정, 문제 생성 내비게이션]
---

# 2025-10-19 주간 회의록

10월 셋째 주 회의는 인증 진입, 검색 공개 조건, 풀이 중 정답 수정처럼 사용자 체감이 큰 세부 규칙을 다듬은 기록이다. 검색은 `전체공개 && 복습모드` 쪽으로 기준이 더 선명해졌고, 자기 그룹과 타 그룹에서 어떤 셋이 보이는지 구분이 시작됐다. 동시에 풀이 중 정답 수정은 문제 유형마다 허용 범위를 다르게 봐야 한다는 공감대가 확인됐다. 문제 생성 화면의 뒤로가기 동선과 AI 추천 버튼 위치도 같이 보였다는 점에서, 이 시기엔 화면 단위 상호작용을 세밀하게 손보는 단계였다.

## 핵심 takeaway

- 검색은 이 회의에서 `전체공개 && 복습모드` 중심으로 기준이 구체화되기 시작했다. 근거: [raw/2025-10-19-weekly-meeting.md](../../raw/2025-10-19-weekly-meeting.md) `§원문 스냅샷`, `§AI 후속 블록 스냅샷`. 영향: [문제 검색](../features/problem-search.md), [문제셋 공개 범위 정책](../decisions/visibility-states.md)
- 풀이 중 정답 수정은 유형별 허용 범위가 다르며, 이미 제출한 사용자 처리 규칙은 별도 운영 판단이 필요하다는 점이 드러났다. 근거: [raw/2025-10-19-weekly-meeting.md](../../raw/2025-10-19-weekly-meeting.md) `§원문 스냅샷`. 영향: [풀이관리 (maker 측)](../features/play-management.md)
- 회원가입/로그인 진입 방식과 문제 생성 내비게이션이 같은 회의에서 다뤄져, 사용자가 처음 들어와 문제를 만들기까지의 연속 경험을 같이 본 흔적이 남아 있다. 근거: [raw/2025-10-19-weekly-meeting.md](../../raw/2025-10-19-weekly-meeting.md) `§AI 후속 블록 스냅샷`. 영향: [로그인 / 회원가입 / 마이페이지](../features/auth-and-account.md), [문제셋 생성 플로우](../features/problem-set-creation.md)

## 영향받는 wiki 페이지

- [features/problem-search.md](../features/problem-search.md)
- [decisions/visibility-states.md](../decisions/visibility-states.md)
- [features/play-management.md](../features/play-management.md)
- [features/auth-and-account.md](../features/auth-and-account.md)
- [features/problem-set-creation.md](../features/problem-set-creation.md)
