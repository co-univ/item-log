---
title: 2026-04-26 주간 회의록
type: source
status: stable
sources: [raw/2026-04-26-weekly-meeting.md]
updated: 2026-05-03
source_url: https://www.notion.so/34a87d592b6e8008abe1c0fc3b1488f2
source_date: 2026-04-26
participants: [신유승, 조원영, 손민재, 오지연, 이하은, 전민재]
topics: [배포 후속, 학습모드, 팀 탈퇴, 팀 삭제, 카테고리, GA4, 개인 워크스페이스, 지식 베이스]
---

# 2026-04-26 주간 회의록

4월 21일 배포 후속과 5월 12일 배포 범위를 정리한 회의다. 문제셋 삭제, 팀 탈퇴, 팀 삭제는 배포됐지만 관련 데이터 노출과 메일 수신 여부를 추가 확인해야 하는 상태로 남았다. 학습모드는 백엔드 관리 API와 프론트 화면 구현이 진행 중이며, 자동 종료와 제출/채점은 아직 후속 작업으로 적혔다. 카테고리는 최종 디자인 전달 이후 이름 길이 제한과 경고 문구가 명세 업데이트 과제로 남았고, GA4는 AI 생성 시간과 로딩 UI 이탈률 등 실제 화면 기준 지표를 준비하기로 했다. 회의 말미에는 아이템별 논의 히스토리를 잊어버리는 문제가 제기되며 원본 회의록/명세 업데이트를 지식 베이스에 알려야 한다는 운영 원칙도 명시됐다.

## 핵심 takeaway

- 4월 21일 배포 항목 중 문제셋 삭제는 관련 데이터가 안 보이는지 확인해야 하고, 팀 탈퇴/삭제는 메일 수신자 확인이 남았다. 근거: [raw/2026-04-26-weekly-meeting.md](../../raw/2026-04-26-weekly-meeting.md) `§공지사항`. 영향: [팀 탈퇴/삭제](../features/team-exit-and-deletion.md), [문제 셋 라이프사이클](../features/problem-set-lifecycle.md)
- 학습모드는 백엔드에서 `풀이 시작`, `종료` API가 정리됐고 `자동 종료`가 별도 작업으로 남았다. 프론트는 관리/풀이 탭과 풀이 화면을 마쳤지만 제출·채점은 진행 중이다. 근거: [raw/2026-04-26-weekly-meeting.md](../../raw/2026-04-26-weekly-meeting.md) `§백엔드`, `§프론트`. 영향: [풀이관리](../features/play-management.md), [문제 풀기](../features/play-player.md)
- 카테고리는 영어 기준 40자 제한을 두고, 40자를 넘었을 때의 경고 문구와 명세 업데이트가 할 일로 남았다. 근거: [raw/2026-04-26-weekly-meeting.md](../../raw/2026-04-26-weekly-meeting.md) `§카테고리`, `§할일 정리`. 영향: [카테고리 관리](../features/category-management.md)
- GA4는 다음 회의까지 준비할 항목으로 올라왔고, AI 문제 생성 시간은 API 시간이 아니라 화면 기준으로 측정하며 로딩 UI 이탈률과 제목 수정 클릭 수까지 지표 후보로 잡혔다. 근거: [raw/2026-04-26-weekly-meeting.md](../../raw/2026-04-26-weekly-meeting.md) `§GA4`. 영향: [제품 분석 / GA4 이벤트](../features/product-analytics.md), [AI 문제 생성](../features/ai-question-generation.md)
- 개인 워크스페이스는 명세 추가와 디자인 검토, 백엔드 API 작업 시작이 동시에 적혀 있어 아직 독립 명세가 부족한 상태다. 근거: [raw/2026-04-26-weekly-meeting.md](../../raw/2026-04-26-weekly-meeting.md) `§할일 정리`. 영향: [핵심 용어](../glossary/core-terms.md)
- 회의록/명세를 제대로 남기지 않으면 논의 히스토리를 기억하거나 검색하기 어렵고, 업데이트된 기능 명세서를 알려주지 않으면 레포 정리가 불가능하다는 운영 문제가 제기됐다. 근거: [raw/2026-04-26-weekly-meeting.md](../../raw/2026-04-26-weekly-meeting.md) `§언제 얘기했었는데 뭐지?`. 영향: [지식 베이스 ingest 운영 원칙](../decisions/knowledge-base-ingest-process.md)

## 영향받는 wiki 페이지

- [features/team-exit-and-deletion.md](../features/team-exit-and-deletion.md)
- [features/problem-set-lifecycle.md](../features/problem-set-lifecycle.md)
- [features/play-management.md](../features/play-management.md)
- [features/play-player.md](../features/play-player.md)
- [features/category-management.md](../features/category-management.md)
- [features/product-analytics.md](../features/product-analytics.md)
- [features/ai-question-generation.md](../features/ai-question-generation.md)
- [decisions/knowledge-base-ingest-process.md](../decisions/knowledge-base-ingest-process.md)

## 미해결

- Notion 페이지 상태가 `예정`으로 남아 있어, 실제 회의 완료 상태로 바꿔야 하는지 확인 필요.
- 디스코드 스레드에 논의된 내용은 아직 raw/wiki에 반영되지 않았다.
- 알림 기능, 개인 워크스페이스, 등수정보는 명세/디자인 추가 필요 항목으로 남았다.
