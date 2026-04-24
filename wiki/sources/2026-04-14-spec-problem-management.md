---
title: "문제관리_문제생성 명세서 (Confluence)"
type: source
status: stable
sources: [raw/2026-04-14-spec-problem-management.md]
updated: 2026-04-24
source_url: https://youthing.atlassian.net/wiki/spaces/~712020e8812b2eb985491caedb51d1b356e362/pages/20217857/_
author: 이하은
source_date: 2026-04-14
---

# 문제관리_문제생성 명세서

mait의 문제 셋 생성 플로우 전체를 다루는 maker 측 기능 명세. **문제 관리 → 문제 정보 입력 → 질문 편집** 3단계로 구성된다.

## 핵심 요약

- maker가 문제셋을 만드는 전체 플로우(메인 화면 → 정보 입력 → 편집 → 생성)를 정의.
- 문제셋은 4가지 라이프사이클 상태: **임시저장 / 실시간 풀이(예정·진행·종료) / 학습풀이 / 복습**.
- 풀이 방식은 **실시간 / 학습** 2종, 질문 유형은 **객관식 / 주관식 / 빈칸 / 순서** 4종.
- 생성 방식은 **AI 생성 / 직접 제작** 2종 — AI 생성만 자료 업로드·풀이 대상·보충설명 활성화.
- **임시저장**(수동) + **자동저장**(편집 후 1분 단위) 이중 저장 정책.
- 복습 상태에서만 **공개 범위** 설정 가능 (전체 공개 / 그룹 공개 / 비공개).

## 영향받는 wiki 페이지

- [features/problem-set-creation.md](../features/problem-set-creation.md) — 문제셋 생성 전체 플로우
- [features/problem-set-lifecycle.md](../features/problem-set-lifecycle.md) — 라이프사이클 상태 머신
- [features/question-editor.md](../features/question-editor.md) — 질문 편집기 (4가지 유형)
- [decisions/visibility-states.md](../decisions/visibility-states.md) — 공개 범위 정책
- [decisions/auto-save-behavior.md](../decisions/auto-save-behavior.md) — 임시저장 vs 자동저장
- [glossary/core-terms.md](../glossary/core-terms.md) — maker / player / 문제셋 / 인정답안 등

## 명세에서 미해결로 표시된 부분

- **재시작 데이터 정책**: 1.2 — "재시작: 문제 풀이 다시 시작 (데이터 관련 내용 확정 필요)"
- **전체 공개 시 비-player 사용자의 접근**: 1.3 — "player가 아닌 사용자가 문제를 어떻게 관리 할 수 있는가 (검색을 통해 문제셋에 접근했을 때)"
- **글자수 상한**: 해설 입력은 "최대 00자"로 자리만 잡혀있음 (객관식 3.6 / 주관식 3.7 / 빈칸 3.8)
- **2.5 문제 풀이 대상**: 상세설명 비어있음
- **3.4 질문 입력**: 상세설명 비어있고 "문제→질문 워딩 개선" 디자인 노트만 있음
