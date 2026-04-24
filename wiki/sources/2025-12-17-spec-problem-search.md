---
title: "문제 검색 명세서 (Confluence)"
type: source
status: stable
sources: [raw/2025-12-17-spec-problem-search.md]
updated: 2026-04-24
source_url: https://youthing.atlassian.net/wiki/spaces/~712020e8812b2eb985491caedb51d1b356e362/pages/24772643
author: 이하은
source_date: 2025-12-17
---

# 문제 검색 명세서

검색바를 통한 문제셋 탐색 흐름. 비회원 / 회원 두 트랙으로 분기하며, 검색 가능 대상은 **전체공개 + 복습모드** 문제셋만.

## 핵심 요약

- 검색 키: 제목 / 팀명 / 문제셋 질문
- 결과 노출: 제목, 팀명, 문제수, 매칭된 질문 또는 1번 질문, 북마크 수
- UI: 카드 → 리스트로 변경
- 비회원 — 상세에서 문제 2개까지만 미리보기, 그 이후 로그인 유도
- 회원 — 북마크(컬렉션 저장) + 내 그룹에 추가(maker/owner인 팀에 다중 선택)

## 영향받는 wiki 페이지

- [features/problem-search.md](../features/problem-search.md) — 신규
- [glossary/core-terms.md](../glossary/core-terms.md) — 북마크, 컬렉션 추가
- [decisions/visibility-states.md](../decisions/visibility-states.md) — "검색은 복습+전체공개만" 규칙 보강

## 미해결

- 비회원이 문제 2개를 본 다음 어떻게 로그인 화면으로 유도되는지 UX 디테일
- 컬렉션 정의/관리 흐름은 별도 명세 필요 (북마크 대상 컬렉션 추가/관리 UI)
