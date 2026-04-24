---
title: "2026-02-22 주간 회의록 (Notion)"
type: source
status: stable
sources: [raw/2026-02-22-weekly-meeting.md]
updated: 2026-04-24
source_path: raw/2026-02-22-weekly-meeting.md
source_date: 2026-02-22
participants: [이하은, 전민재, 조원영, 손민재, 신유승]
topics: [배포 준비, 문제셋 편집 UX, 카테고리 디자인 단계, 우승자 종료 팝업, 평균 지표, 문제셋 삭제]
---

# 2026-02-22 주간 회의록

3월 말 정기배포와 교육팀 시연을 앞두고, 실제 데모 품질을 끌어올리기 위한 수정 사항을 정리한 회의록이다. 문제셋 생성 직후의 다이렉트 URL, 제목 수정, 미리보기 전환, 객관식/순서형 수정 제한, 주관식 인정답안 처리처럼 편집 UX 전반이 다시 점검됐다. 카테고리 기능은 구현 검토를 끝내고 디자인 단계로 넘길 수 있을 만큼 성숙했다고 보고됐다. 운영 영역에서는 우승자 선정 후 종료 팝업, 평균 지표 노출, 문제셋 삭제 가능 여부가 우선 확인 대상이었다.

## 핵심 takeaway

- 문제셋 생성/수정 UX는 세부 화면 요소 단위로 다시 다듬어야 할 정도로 운영 피드백이 쌓여 있었다. 생성 직후 URL, 제목 수정, 미리보기 전환, 수정 버튼 비활성 조건 등이 모두 후속 보강 포인트다. 근거: [raw/2026-02-22-weekly-meeting.md](../../raw/2026-02-22-weekly-meeting.md) `§원문 스냅샷`, `§AI 후속 블록 스냅샷`. 영향: [문제셋 생성 플로우](../features/problem-set-creation.md)
- 카테고리 기획은 디자인 단계로 넘겨도 되는 수준으로 정리됐고, 교육팀 피드백을 선별해 와이어프레임과 명세에 반영하기로 했다. 근거: [raw/2026-02-22-weekly-meeting.md](../../raw/2026-02-22-weekly-meeting.md) `§원문 스냅샷`, `§AI 후속 블록 스냅샷`. 영향: [카테고리 관리](../features/category-management.md)
- 우승자 선정 후 종료 팝업이 뜨지 않는 문제와 평균 지표 노출 문의는 운영 종료 흐름과 결과 해석 화면이 아직 불안정함을 보여 준다. 근거: [raw/2026-02-22-weekly-meeting.md](../../raw/2026-02-22-weekly-meeting.md) `§원문 스냅샷`, `§AI 후속 블록 스냅샷`. 영향: [진출자 선정](../features/winner-selection.md), [풀이결과 대시보드](../features/result-dashboard.md)
- 문제셋 삭제 가능 여부는 단순 버튼 유무가 아니라 상태별 영향도와 연결된 운영성 이슈로 계속 관리되고 있었다. 근거: [raw/2026-02-22-weekly-meeting.md](../../raw/2026-02-22-weekly-meeting.md) `§원문 스냅샷`, `§AI 후속 블록 스냅샷`. 영향: [문제 셋 라이프사이클](../features/problem-set-lifecycle.md)

## 영향받는 wiki 페이지

- [features/problem-set-creation.md](../features/problem-set-creation.md)
- [features/category-management.md](../features/category-management.md)
- [features/winner-selection.md](../features/winner-selection.md)
- [features/result-dashboard.md](../features/result-dashboard.md)
- [features/problem-set-lifecycle.md](../features/problem-set-lifecycle.md)

