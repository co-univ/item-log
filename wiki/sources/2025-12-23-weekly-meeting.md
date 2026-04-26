---
title: "2025-12-23 ~ 2025-12-31 주간 회의록 (Notion)"
type: source
status: stable
sources: [raw/2025-12-23-weekly-meeting.md]
updated: 2026-04-25
source_path: raw/2025-12-23-weekly-meeting.md
source_date: 2025-12-23
participants: [신유승, 조원영, 손민재, 오지연, 남기훈, 이하은, 전민재]
topics: [복습 정오답 노출 정책, AI 생성 장애, API 권한 이슈, 재채점 문의, 운영 채널]
---

# 2025-12-23 ~ 2025-12-31 주간 회의록

연말 배치 회의록은 기능 기획보다 운영 체계 정비와 복습 모드 세부 동작 점검이 더 강하게 드러난다. 복습 정답 제출 API 이후 어떤 정오답/해설을 어디까지 보여줄지, 마지막 문제 조회 API 권한 이슈와 권한 draft를 어떻게 연결할지, AI 문제 생성 간헐 실패를 어떻게 안정화할지가 동시에 남았다. 디스코드 문의 채널, Jira 사용, 재채점 문의 응답 같은 운영 메모도 많아 제품 개발과 사용자 지원 프로세스가 함께 정리되던 시기라는 점이 특징이다.

## 핵심 takeaway

- 복습 모드는 이 시점에 `정오답 노출 제거`, `해설 필드 제거`, `어떤 답이 맞고 틀렸는지`처럼 결과 노출 정책을 더 세밀하게 다듬는 단계로 들어갔다. 근거: [raw/2025-12-23-weekly-meeting.md](../../raw/2025-12-23-weekly-meeting.md) `§파트별 공유`, `§AI 후속 블록 스냅샷`. 영향: [문제 풀기 (player 측)](../features/play-player.md), [채점 / 정답 표시 정책](../decisions/scoring-display.md)
- AI 문제 생성은 기능 연결 이후에도 `간헐 실패`가 운영 이슈로 남아 있어 안정화 과제가 별도로 필요했다. 근거: [raw/2025-12-23-weekly-meeting.md](../../raw/2025-12-23-weekly-meeting.md) `§파트별 공유`. 영향: [AI 문제 생성](../features/ai-question-generation.md)
- API 권한 이슈는 실제 조회 버그와 draft 문서가 함께 언급될 정도로 구현/정책 사이의 작업축이 분리돼 있었다. 근거: [raw/2025-12-23-weekly-meeting.md](../../raw/2025-12-23-weekly-meeting.md) `§파트별 공유`. 영향: [권한 체계](../decisions/permission-roles.md)

## 영향받는 wiki 페이지

- [features/play-player.md](../features/play-player.md)
- [decisions/scoring-display.md](../decisions/scoring-display.md)
- [features/ai-question-generation.md](../features/ai-question-generation.md)
- [decisions/permission-roles.md](../decisions/permission-roles.md)
