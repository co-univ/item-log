---
title: 문제셋 공개 범위 정책 (전체/그룹/비공개)
type: decision
status: draft
sources: [raw/2026-04-14-spec-problem-management.md, raw/2025-12-17-spec-problem-search.md, raw/2025-10-12-weekly-meeting.md, raw/2025-10-19-weekly-meeting.md, raw/2025-10-23-weekly-meeting.md, raw/2025-12-10-weekly-meeting.md, raw/2026-04-11-spec-player-view-play.md, raw/2026-04-11-spec-play-management.md, raw/2026-01-11-weekly-meeting.md]
updated: 2026-04-25
---

# 문제셋 공개 범위 정책

문제셋의 노출·풀이·편집 권한을 결정하는 3단계 공개 범위. **복습 상태에서만 설정 가능**.

## 3단계 정의

| 상태 | 노출 | player 풀이 | maker 편집 |
|---|---|---|---|
| **전체 공개** | 서비스 전 사용자 | 그룹 초대 player | 그룹 초대 maker |
| **그룹 공개** | 그룹 멤버 | 그룹 초대 player | 그룹 초대 maker |
| **비공개** | (그룹 멤버) | — | 그룹 초대 maker |

## 핵심 규칙

- **풀이/편집 권한은 항상 "그룹에 초대된 사용자"에 묶인다.** 공개 범위는 노출 범위만 확장.
- 메인 화면에서 전체/그룹/비공개 **필터링** 가능.
- 공개 범위는 모달로 변경.

## 검색 가시성

[features/problem-search.md](../features/problem-search.md) 검색은 **`전체공개` AND `복습`** 인 문제셋만 노출.

→ 즉 실시간/학습 모드에서 진행 중인 셋은 검색 불가.

## 12/10 기획 논의 결정 (이전 명세 변경)

근거: **풀이 중에 제3자가 들어오면 안 됨. 풀이 중 문제 정보가 변경될 수 있기 때문.**

1. **공개 대상 선택을 생성 단계에서 삭제** — 학습/실시간 모드 생성 시 그룹공개 default 고정.
2. **종료됨 → 복습 전환 시에만 공개 대상 정함.**
3. 따라서 검색은 복습 + 전체공개만.

> ⚠ **충돌 점검**: 4/14 [문제관리_문제생성 명세](../sources/2026-04-14-spec-problem-management.md) §3.12에는 여전히 "생성하기 모달에서 공개대상(그룹공개 default) 선택" 흐름이 남아있음. 12/10 결정이 명세에 반영되지 않았는지 / 4/14 명세가 우선인지 확인 필요. → [features/problem-set-creation.md](../features/problem-set-creation.md) "생성하기" 섹션 참고.

## 초기 논의 흔적

- 2025-10-12 회의에서는 검색에 어떤 공개 범위 조합을 허용할지 기준이 아직 흐릿하다는 메모가 남아 있었다. [2025-10-12 주간 회의록](../sources/2025-10-12-weekly-meeting.md)
- 2025-10-19 회의에서는 `전체공개 && 복습모드`를 검색 노출의 구체 조건으로 다시 확인했다. [2025-10-19 주간 회의록](../sources/2025-10-19-weekly-meeting.md)
- 2025-10-23 회의에서도 검색 대상을 `전체 공개 && 복습모드`와 묶어 보는 논의가 이미 존재했다. 12/10 결정은 갑자기 나온 규칙이 아니라, 10월부터 이어진 방향의 정리로 볼 수 있다. [2025-10-23 주간 회의록](../sources/2025-10-23-weekly-meeting.md)

## 종료하기 → 복습 전환 시 공개 범위 모달

- **선착순 모드 종료**: 우승자 공개 옵션 → 공개범위 설정 모달 (기존 셋 설정으로 default 체크) → 확인 → 복습 화면.
- **학습 모드 종료**: 마지막 문제 → 종료하기 → 공개범위 설정(전체/그룹/비공개) → 확인 → 복습 화면.

## 운영 중 확인된 이슈

- 2026-01-11 주간 회의에서는 `비공개 문제 셋의 풀이가 가능한 이슈`가 실제 운영 문제로 언급됐다. 정책 문서와 구현 상태가 어긋났을 가능성이 있어, 비공개 상태의 진입/풀이 가능 여부를 재검증해야 한다. [2026-01-11 주간 회의록](../sources/2026-01-11-weekly-meeting.md)

## 미해결

- 전체공개 상태에서 비-player(검색 진입자)의 관리 흐름 — PDF 다운 → "내 문제셋으로 가져옴" 흐름의 정확한 UX 정의 필요.
- 12/10 결정과 4/14 명세의 정합성.

## 관련

- [features/problem-set-lifecycle.md](../features/problem-set-lifecycle.md) — 라이프사이클 상태 머신
- [features/problem-set-creation.md](../features/problem-set-creation.md) — 생성 플로우
- [features/problem-search.md](../features/problem-search.md) — 검색 노출 조건

## 출처

- [sources/2026-04-14-spec-problem-management.md](../sources/2026-04-14-spec-problem-management.md) (1.3 복습)
- [sources/2026-04-11-spec-player-view-play.md](../sources/2026-04-11-spec-player-view-play.md) (12/10 기획논의)
- [sources/2025-12-17-spec-problem-search.md](../sources/2025-12-17-spec-problem-search.md) (검색 노출 조건)
- [sources/2026-04-11-spec-play-management.md](../sources/2026-04-11-spec-play-management.md) (1.8, 1.4 종료 시 공개범위 모달)
