---
title: 풀이결과 대시보드 명세서 v7
type: source
status: stable
sources: [raw/2026-05-26-spec-result-dashboard.md]
updated: 2026-05-30
date: 2026-05-26
source_path: raw/2026-05-26-spec-result-dashboard.md
source_url: https://youthing.atlassian.net/wiki/spaces/~712020e8812b2eb985491caedb51d1b356e362/pages/54493186
source_id: "54493186"
source_date: 2026-05-26
participants: []
topics: [풀이결과 대시보드, 우리팀 랭킹, 정답률, 카테고리별 정답률, 오답률, 점수]
---

# 풀이결과 대시보드 명세서 v7

Confluence `풀이결과 대시보드` 문서의 2026-05-26 버전이다. 대시보드는 메인과 상세 2단 구조를 유지하며, 메인에는 전체 랭킹, 개인 정답률, 카테고리별 정답률, 문제셋 정보 카드가 배치된다. 이 버전에서는 메인 전체 랭킹이 실시간 모드만이 아니라 실시간/학습 모드 모두를 모드별 기준으로 집계하는 것으로 적혀 있다. 상세 대시보드는 문제셋별 랭킹, 오답률 top3, 점수, 전체 문제 풀이결과를 제공한다. 점수는 탈락해도 전체 문제 수를 분모로 계산하고, 전체 문제 풀이결과는 복습풀이+해설보기 상태와 동일하게 단순 확인용으로 노출된다.

## 핵심 takeaway

- 메인 `우리팀 랭킹(전체랭킹)`은 선착순 기준/정답수 기준 탭 전환을 제공하고, 실시간 모드는 전체 득점자 순위, 학습 모드는 정답수 기준 순위를 집계한다. 근거: [raw/2026-05-26-spec-result-dashboard.md](../../raw/2026-05-26-spec-result-dashboard.md) `§풀이결과 대시보드 메인 1.1`. 영향: [풀이결과 대시보드](../features/result-dashboard.md)
- 메인 개인 통계는 지금까지 푼 문제셋 개수와 맞은 문제 수로 개인 정답률 원그래프를 만든다. 근거: [raw/2026-05-26-spec-result-dashboard.md](../../raw/2026-05-26-spec-result-dashboard.md) `§풀이결과 대시보드 메인 1.2`. 영향: [풀이결과 대시보드](../features/result-dashboard.md), [핵심 용어](../glossary/core-terms.md)
- 카테고리별 정답률 바는 여전히 `카테고리 = 문제셋의 주제 태그`로 설명되어 있어, 2026-05-14 회의의 주제/카테고리 분리 논의와 정합성 확인이 필요하다. 근거: [raw/2026-05-26-spec-result-dashboard.md](../../raw/2026-05-26-spec-result-dashboard.md) `§풀이결과 대시보드 메인 1.3`. 영향: [풀이결과 대시보드](../features/result-dashboard.md), [카테고리 관리](../features/category-management.md)
- 상세 대시보드 진입점은 메인 문제셋 정보 카드와 풀이 종료 후 우승자 화면의 `풀이결과 보러가기`다. 근거: [raw/2026-05-26-spec-result-dashboard.md](../../raw/2026-05-26-spec-result-dashboard.md) `§풀이결과 대시보드 상세 진입점`. 영향: [풀이결과 대시보드](../features/result-dashboard.md), [풀이관리](../features/play-management.md)
- 상세 점수는 `00점 (00/00)` 형식이며, 중간 탈락으로 뒷 문제를 못 풀어도 전체 문제 개수 기준으로 계산한다. 근거: [raw/2026-05-26-spec-result-dashboard.md](../../raw/2026-05-26-spec-result-dashboard.md) `§2.3 점수`. 영향: [점수 산정 정책](../decisions/score-calculation.md)
- 전체 문제 풀이결과는 복습풀이+해설보기 상태와 동일하고, 다시 풀기 영역이 아니라 내 답안/실제 정답/풀이를 확인하는 영역이다. 근거: [raw/2026-05-26-spec-result-dashboard.md](../../raw/2026-05-26-spec-result-dashboard.md) `§2.4 전체 문제 풀이결과`. 영향: [풀이결과 대시보드](../features/result-dashboard.md), [문제 풀기](../features/play-player.md)

## 영향받는 wiki 페이지

- [features/result-dashboard.md](../features/result-dashboard.md)
- [features/play-management.md](../features/play-management.md)
- [features/play-player.md](../features/play-player.md)
- [decisions/score-calculation.md](../decisions/score-calculation.md)
- [glossary/core-terms.md](../glossary/core-terms.md)

## 미해결

- 2026-05-14 회의의 `학습모드는 본인 점수 중심` 메모와, 2026-05-26 명세의 `학습 모드 → 정답수 기준 순위 집계` 문구의 정합성 확인이 필요하다.
- 카테고리별 정답률의 집계 필드가 주제 태그인지, 2026-05-14 이후의 별도 카테고리 필드인지 확인이 필요하다.
- 상세 대시보드 2.1은 이번 버전에서 실시간 모드 선착순 기준만 명시되어 있어, 학습 모드 상세 랭킹 기준을 계속 정답수로 볼지 확인이 필요하다.
