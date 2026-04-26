---
title: "2025-11-12 주간 회의록 (Notion)"
type: source
status: stable
sources: [raw/2025-11-12-weekly-meeting.md]
updated: 2026-04-25
source_path: raw/2025-11-12-weekly-meeting.md
source_date: 2025-11-12
participants: [신유승, 조원영, 남기훈, 전민재, 이하은]
topics: [AI 문제 생성 API, 팀 초대 세부 안내, 자동저장, 팀관리 명세, 대시보드 명세]
---

# 2025-11-12 주간 회의록

11월 둘째 주 회의는 AI 문제 생성, 초대 흐름, 자동저장/팀관리/대시보드 문서 보강이 한데 묶인 정리 회의다. 백엔드는 AI 문제 생성 API 설명과 대응, 풀이관리 API 수정, 문제셋 검색, 팀 초대 승락과 세부사항 전달을 남겼다. 프론트는 AI 문제 생성 API 연결 준비를 별도로 잡고 있었고, 기획은 자동저장/팀관리/대시보드 명세서 업데이트를 동시에 진행했다. 문서와 구현이 서로 따라붙던 시기라는 점이 뚜렷하다.

## 핵심 takeaway

- AI 문제 생성은 이 시점에 백엔드 API 대응과 프론트 연결 준비가 동시에 필요한 통합 과제가 됐다. 근거: [raw/2025-11-12-weekly-meeting.md](../../raw/2025-11-12-weekly-meeting.md) `§파트별 공유`, `§AI 후속 블록 스냅샷`. 영향: [AI 문제 생성](../features/ai-question-generation.md), [문제셋 생성 플로우](../features/problem-set-creation.md)
- 팀 초대는 단순 승인 여부를 넘어서 `세부사항 전달`까지 포함한 온보딩 문제로 확대됐다. 근거: [raw/2025-11-12-weekly-meeting.md](../../raw/2025-11-12-weekly-meeting.md) `§파트별 공유`. 영향: [팀 사용자 초대](../features/team-invitation.md)
- 자동저장, 팀관리, 대시보드 명세서 업데이트가 동시 후속으로 남아 구현 속도에 맞춰 문서를 맞추는 흐름이 확인된다. 근거: [raw/2025-11-12-weekly-meeting.md](../../raw/2025-11-12-weekly-meeting.md) `§기획 논의`. 영향: [임시저장 / 자동저장 정책](../decisions/auto-save-behavior.md), [팀 멤버 권한 관리](../features/team-member-management.md), [풀이결과 대시보드](../features/result-dashboard.md)

## 영향받는 wiki 페이지

- [features/ai-question-generation.md](../features/ai-question-generation.md)
- [features/problem-set-creation.md](../features/problem-set-creation.md)
- [features/team-invitation.md](../features/team-invitation.md)
- [decisions/auto-save-behavior.md](../decisions/auto-save-behavior.md)
- [features/team-member-management.md](../features/team-member-management.md)
- [features/result-dashboard.md](../features/result-dashboard.md)
