---
title: "2025-10-12 주간 회의록 (Notion)"
type: source
status: stable
sources: [raw/2025-10-12-weekly-meeting.md]
updated: 2026-04-25
source_path: raw/2025-10-12-weekly-meeting.md
source_date: 2025-10-12
participants: [신유승, 손민재, 조원영, 남기훈]
topics: [풀이관리 와이어프레임, validation fail 처리, 실시간 풀이 중 정보 변경, 문제 검색 공개범위]
---

# 2025-10-12 주간 회의록

10월 둘째 주 회의는 아직 기능 명세가 완전히 굳기 전, 운영 중 문제가 될 수 있는 어색한 지점을 빠르게 드러내고 정리한 기록이다. 문제 생성 validation fail 처리와 풀이관리 와이어프레임이 함께 올라왔고, 실시간 풀이 중 문제 내용이 바뀌는 상황을 허용할지에 대한 우려도 분명하게 드러났다. 같은 회의에서 문제 검색 공개범위 논의까지 붙어 있어, 생성과 운영, 공개 정책이 따로 놀지 않도록 맞춰 보려는 시기였음을 알 수 있다. 완성된 결정문보다 방향 정리와 위험 식별의 성격이 강하다.

## 핵심 takeaway

- 생성하기 validation fail은 단순 에러 문구가 아니라, 어떤 문제와 필드를 먼저 보여줄지까지 포함한 UX 이슈로 다뤄졌다. 근거: [raw/2025-10-12-weekly-meeting.md](../../raw/2025-10-12-weekly-meeting.md) `§원문 스냅샷`, `§AI 후속 블록 스냅샷`. 영향: [문제셋 생성 플로우](../features/problem-set-creation.md)
- 실시간 풀이 중 이미 보고 있는 문제 내용이 바뀌는 것은 부자연스럽다는 우려가 명시돼, 이후 공개범위와 검색 정책을 복습 상태 중심으로 묶는 방향과도 연결된다. 근거: [raw/2025-10-12-weekly-meeting.md](../../raw/2025-10-12-weekly-meeting.md) `§원문 스냅샷`. 영향: [풀이관리 (maker 측)](../features/play-management.md), [문제셋 공개 범위 정책](../decisions/visibility-states.md)
- 검색 노출 기준은 자기 그룹/전체 공개/복습 상태 조합을 정교하게 정리해야 할 후속 과제로 남아 있었다. 근거: [raw/2025-10-12-weekly-meeting.md](../../raw/2025-10-12-weekly-meeting.md) `§AI 후속 블록 스냅샷`. 영향: [문제 검색](../features/problem-search.md)

## 영향받는 wiki 페이지

- [features/problem-set-creation.md](../features/problem-set-creation.md)
- [features/play-management.md](../features/play-management.md)
- [features/problem-search.md](../features/problem-search.md)
- [decisions/visibility-states.md](../decisions/visibility-states.md)
