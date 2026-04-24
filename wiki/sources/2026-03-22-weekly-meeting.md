---
title: "2026-03-22 주간 회의록 (Notion)"
type: source
status: stable
sources: [raw/2026-03-22-weekly-meeting.md]
updated: 2026-04-24
source_path: raw/2026-03-22-weekly-meeting.md
source_date: 2026-03-22
participants: [신유승, 조원영, 손민재]
topics: [우승자 선정 팝업, 중간 참여, 사이드바 자동 접힘, 로그아웃 드랍다운, 대시보드 닉네임 노출, 반응형]
---

# 2026-03-22 주간 회의록

정기배포 직전 운영 화면의 세부 동작과 표현을 집중 점검한 주간 회의록이다. 우승자 선정 팝업과 종료하기 흐름, 실시간 중간 참여 처리, 사이드바 자동 접힘 기준처럼 실제 사용 중 바로 부딪히는 인터랙션 문제가 핵심 의제였다. 동시에 개인 워크스페이스 진입, 팀명/이름 길이 처리, 문제 풀이 화면 반응형 같은 공통 UX 문제가 하나의 정보 구조 문제로 연결된다는 인식도 드러났다. 결과 화면 쪽에서는 대시보드에 닉네임만 보여 주는 방향이 명시됐다.

## 핵심 takeaway

- 우승자 선정 팝업과 종료하기 플로우는 실제 운영 검증이 더 필요하다는 회고가 남았다. 기능이 있다고 끝나는 것이 아니라, 종료 직전/직후 동선이 안정적으로 동작하는지 확인해야 한다. 근거: [raw/2026-03-22-weekly-meeting.md](../../raw/2026-03-22-weekly-meeting.md) `§원문 스냅샷`, `§AI 후속 블록 스냅샷`. 영향: [진출자 선정](../features/winner-selection.md), [풀이관리](../features/play-management.md)
- 실시간 중간 참여, 진출자/우승자 워딩, 닉네임만 노출 같은 항목은 플레이어가 보는 운영 화면의 표현 규칙을 정교화하는 후속 작업으로 정리됐다. 근거: [raw/2026-03-22-weekly-meeting.md](../../raw/2026-03-22-weekly-meeting.md) `§AI 후속 블록 스냅샷`. 영향: [문제 풀기](../features/play-player.md), [풀이결과 대시보드](../features/result-dashboard.md)
- 사이드바 자동 접힘 기준은 단순 반응형 문제가 아니라, 어떤 상황에서 조작을 감추거나 유지할지에 대한 규칙 정의가 필요하다는 논점으로 정리됐다. 근거: [raw/2026-03-22-weekly-meeting.md](../../raw/2026-03-22-weekly-meeting.md) `§AI 후속 블록 스냅샷`. 영향: [풀이관리](../features/play-management.md)
- 팀이 없는 경우의 진입 플로우, 최근 방문 팀 저장, 이름 길이 처리 같은 문제는 팀/워크스페이스 단위 UX를 따로 다뤄야 함을 보여준다. 근거: [raw/2026-03-22-weekly-meeting.md](../../raw/2026-03-22-weekly-meeting.md) `§AI 후속 블록 스냅샷`. 영향: [핵심 용어](../glossary/core-terms.md)

## 영향받는 wiki 페이지

- [features/play-management.md](../features/play-management.md)
- [features/winner-selection.md](../features/winner-selection.md)
- [features/play-player.md](../features/play-player.md)
- [features/result-dashboard.md](../features/result-dashboard.md)
- [glossary/core-terms.md](../glossary/core-terms.md)

