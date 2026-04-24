---
title: 문제 검색
type: feature
status: draft
sources: [raw/2025-12-17-spec-problem-search.md, raw/2026-04-11-spec-player-view-play.md]
updated: 2026-04-24
---

# 문제 검색

서비스 전체 문제셋 탐색. **전체공개 + 복습모드** 문제셋만 검색 대상이다.

## 검색 대상 / 키

| 항목 | 값 |
|---|---|
| 검색 가능 키 | 제목 / 팀명 / 문제셋의 질문 |
| 노출 가능 조건 | `공개범위 = 전체공개` AND `라이프사이클 = 복습` |
| UI 형태 | 카드 → **리스트** |

## 결과 리스트 노출 정보

- 제목, 팀명, 문제수
- 매칭 노출:
  - 검색어가 질문에 있으면 → 그 **질문** 노출
  - 검색어가 질문에 없으면 → **1번 질문** 노출
- 북마크 수

## 비회원 흐름

| 단계 | 동작 |
|---|---|
| 검색바 | 자유 검색 |
| 결과 리스트 | 위 정보 노출 |
| 상세 진입 | 제목·팀명·날짜 + **문제 2개**까지 미리보기 (풀이 불가, 확인만) |
| 그 이후 | 문제 노출 X → **로그인 화면 유도** |

## 회원 흐름

비회원 흐름의 모든 항목 + 다음 추가 액션.

### 북마크 (회원 전용)

- 정의: 컬렉션에 문제셋을 저장·열람만 가능. **팀(개인 학습공간 포함)으로 가져오거나 편집은 불가.**
- 흐름: 북마크 아이콘 클릭 → 컬렉션 선택 (또는 컬렉션 추가) → 저장하기 → 북마크 아이콘 채워짐.

### 내 그룹에 추가

- 상세에서 각 문제별 체크박스 + 전체 선택.
- 하나라도 선택해야 "내 그룹에 추가" 버튼 활성화.
- 클릭 시 추가 가능한 팀 노출 — **개인 학습 공간 + maker(owner 포함)인 팀** 다중 선택 가능.

## 관련

- [decisions/visibility-states.md](../decisions/visibility-states.md) — 검색 노출 조건의 근거
- [features/problem-set-lifecycle.md](../features/problem-set-lifecycle.md) — 복습 상태가 검색 가능한 유일한 상태
- [glossary/core-terms.md](../glossary/core-terms.md) — 북마크, 컬렉션, 개인 학습 공간

## 미해결

- 비회원이 2개 미리보기 후 로그인 유도되는 UX (모달? 풀스크린?)
- 컬렉션 자체의 정의·CRUD 흐름 — 별도 명세 필요
- "개인 학습 공간"의 정의 (개인용 default 팀? 별도 개념?) — 명세 누락

## 출처

- [sources/2025-12-17-spec-problem-search.md](../sources/2025-12-17-spec-problem-search.md)
- [sources/2026-04-11-spec-player-view-play.md](../sources/2026-04-11-spec-player-view-play.md) (자유 노트 검색 섹션)
