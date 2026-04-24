---
title: "2026-01-11 주간 회의록 (Notion)"
type: source
status: stable
sources: [raw/2026-01-11-weekly-meeting.md]
updated: 2026-04-24
source_path: raw/2026-01-11-weekly-meeting.md
source_date: 2026-01-11
participants: [신유승, 전민재, 이하은, 오지연, 남기훈, 조원영]
topics: [비공개 문제셋 접근, 복습 해설, 재채점, 생성 화면 placeholder, 문제셋 제목 노출, 사이드바 스크롤]
---

# 2026-01-11 주간 회의록

출시 직후 드러난 권한·규칙 문제와 세부 UX 불편을 묶어 정리한 회의록이다. 비공개 문제셋이 풀이 가능한 상태였는지, 복습에서 해설을 어떻게 볼지, 재채점을 어떻게 안내할지가 우선 검토 대상이었다. 동시에 문제 생성 보충설명 placeholder, 문제 수정 페이지의 문제셋 제목 노출, 팀 선택 창/사이드바 스크롤 동작 같은 편집 화면 보완 요구도 나왔다. 학습모드, 개인 대시보드, PDF 다운로드, AI 추천 같은 중장기 개선 주제는 아이디어 수준으로 보관됐다.

## 핵심 takeaway

- 비공개 문제셋의 풀이 가능 여부가 운영 이슈로 올라오면서 공개 범위 정책이 실제 구현과 어긋나지 않는지 다시 확인해야 하는 상황이 드러났다. 근거: [raw/2026-01-11-weekly-meeting.md](../../raw/2026-01-11-weekly-meeting.md) `§원문 스냅샷`, `§AI 후속 블록 스냅샷`. 영향: [문제셋 공개 범위 정책](../decisions/visibility-states.md)
- 복습 해설, 재채점, 완료된 문제셋 확인성 같은 항목은 단순 UI가 아니라 채점 경험과 운영 규칙을 함께 조정해야 하는 문제로 쌓이고 있었다. 근거: [raw/2026-01-11-weekly-meeting.md](../../raw/2026-01-11-weekly-meeting.md) `§원문 스냅샷`, `§AI 후속 블록 스냅샷`. 영향: [문제 풀기](../features/play-player.md), [문제 셋 라이프사이클](../features/problem-set-lifecycle.md)
- 생성 화면의 보충설명 placeholder, 수정 페이지의 문제셋 제목, 사이드바 스크롤은 편집 화면 맥락 유지와 탐색성 개선 요구로 볼 수 있다. 근거: [raw/2026-01-11-weekly-meeting.md](../../raw/2026-01-11-weekly-meeting.md) `§원문 스냅샷`, `§AI 후속 블록 스냅샷`. 영향: [문제셋 생성 플로우](../features/problem-set-creation.md)

## 영향받는 wiki 페이지

- [decisions/visibility-states.md](../decisions/visibility-states.md)
- [features/play-player.md](../features/play-player.md)
- [features/problem-set-lifecycle.md](../features/problem-set-lifecycle.md)
- [features/problem-set-creation.md](../features/problem-set-creation.md)
