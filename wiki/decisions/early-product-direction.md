---
title: 초기 제품 방향과 검증 전략
type: decision
status: draft
sources: [raw/2025-02-02-weekly-meeting.md, raw/2025-02-09-weekly-meeting.md, raw/2025-02-16-weekly-meeting.md, raw/2025-03-01-weekly-meeting.md]
updated: 2026-04-24
---

# 초기 제품 방향과 검증 전략

2025년 2~3월 초기 주간 회의에서 드러난 제품 방향 메모. 아직 확정 명세라기보다, 무엇을 먼저 검증해야 하는지에 대한 팀의 공통 전제를 정리한 페이지다.

## 핵심 방향

- mait는 초기에 `CS 문제 셋을 모은 플랫폼`에 가까운 문제 공간을 상정했다. 단순 문항 저장소가 아니라, 그룹/팀 단위로 문제를 만들고 풀이하게 하는 구조를 기본 축으로 봤다.
- 문제 공급 전략에서 중요한 것은 단순 수량보다 `문제 신뢰성`이었다. 출처가 납득 가능하고 시스템적으로 채점 가능한 문제여야 사용자 설득력이 생긴다고 봤다.
- 제품 기획 초반에는 기능을 많이 고정하기보다, 교육팀 출신 사용자 대상 설문/인터뷰와 사용성 테스트로 실제 페인 포인트를 먼저 확인해야 한다는 의견이 강했다.
- 디자인 컨셉과 서비스 이름, 그룹형 사용자 흐름은 구현 이후 포장 요소가 아니라 제품 정체성을 결정하는 선행 항목으로 다뤄졌다.

## 카테고리 / 그룹 개념의 초기 위치

- 카테고리는 초기부터 문제셋 분류의 핵심 구조로 거론됐다.
- 그룹/팀/역할 언어도 함께 논의됐지만, 당시에는 용어 경계가 아직 고정되지 않았다.
- 이 흐름은 이후 [카테고리 관리](../features/category-management.md), [권한 체계](./permission-roles.md), [핵심 용어](../glossary/core-terms.md) 정리에 영향을 줬다.

## 미해결

- 초기 타깃 사용자를 교육팀 맥락에 얼마나 강하게 묶을지
- 문제 신뢰성을 운영상 어떻게 보증할지
- 그룹과 팀을 같은 개념으로 볼지, 다른 개념으로 나눌지

## 관련

- [features/category-management.md](../features/category-management.md)
- [glossary/core-terms.md](../glossary/core-terms.md)

## 출처

- [sources/2025-02-02-weekly-meeting.md](../sources/2025-02-02-weekly-meeting.md)
- [sources/2025-02-09-weekly-meeting.md](../sources/2025-02-09-weekly-meeting.md)
- [sources/2025-02-16-weekly-meeting.md](../sources/2025-02-16-weekly-meeting.md)
- [sources/2025-03-01-weekly-meeting.md](../sources/2025-03-01-weekly-meeting.md)

