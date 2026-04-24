---
title: "문제관리_풀이관리 명세서 (Confluence)"
type: source
status: stable
sources: [raw/2026-04-11-spec-play-management.md]
updated: 2026-04-24
source_url: https://youthing.atlassian.net/wiki/spaces/~712020e8812b2eb985491caedb51d1b356e362/pages/35225603/_
author: 이하은
source_date: 2026-04-11
---

# 문제관리_풀이관리 명세서

maker 측 풀이 진행 화면. **선착순 모드**(실시간)와 **학습 모드** 두 갈래로 구성. 시작하기/문제공개/제출허용 토글, 진출자 선정, 종료 시 복습 전환까지의 maker 권한 동작을 정의.

## 핵심 요약

### 선착순 모드 (실시간)

- **문제 제어 토글**: `문제공개` (player에게 화면 노출) / `제출허용` (제출 버튼 활성화). 문제공개 OFF면 제출허용도 OFF.
- **답안 추가**: 객관식·순서는 수정 불가, 주관식·빈칸은 **인정답안 추가**만 가능. 빈칸 자체 추가/위치 변경 불가.
- **player 정보**: 실명+닉네임 9자 제한, (1) 선착순 / (2) 정답자 / (3) 오답자 탭. 무한 스크롤. 정오답 색상 구분.
- **득점자**: 가장 빠르게 정답 제출한 사람. 인정답안 추가로 정답이 바뀌면 득점자 자동 갱신.
- **진출자 선정**: 선착순 등수 또는 정답자 등수 기준 → 체크박스 선택 또는 "선착순 N등까지" 자동 선택 → 직접 입력도 가능 → 진출자 확정 모달.
- **종료하기**: 우승자 공개 여부 선택 → 공개범위 설정 → 복습으로 전환.

### 학습 모드

- **문제 종료 자동 처리**: 모든 인원이 풀기 완료 시 자동 종료. 풀이 중에 새 player가 들어오면 그 인원까지 다 풀어야 자동 완료.
- **수동 종료**도 가능.
- 마지막 문제에서 "다음문제" 버튼이 "종료하기"로 변경 → 공개범위 설정 → 복습 전환.

## 영향받는 wiki 페이지

- [features/play-management.md](../features/play-management.md) — 신규 (선착순 + 학습 통합)
- [features/winner-selection.md](../features/winner-selection.md) — 신규 (선착순 모드 진출자 선정)
- [decisions/answer-edit-during-play.md](../decisions/answer-edit-during-play.md) — 신규 (풀이 중 답안/인정답안 수정 정책)
- [features/problem-set-lifecycle.md](../features/problem-set-lifecycle.md) — 종료→복습 전환 단계 보강
- [glossary/core-terms.md](../glossary/core-terms.md) — 문제공개, 제출허용, 득점자, 진출자, owner 추가

## 미해결

- 1.4 "오답인 경우: 계속 재제출이 가능하면 풀이관리에서 (+데이터상으로) 해당 플레이어가 정답자, 오답자 모두에 표기되는 것에 대한건…" — **정책 결정 필요**
- 답안 글자수 제한 (1.4 "디자인 확인 후 글자수 제한 필요")
- 학습 모드 1.2/1.3은 "선착순과 동일"이라고만 명시 — 차이점이 있는지 검증 필요
