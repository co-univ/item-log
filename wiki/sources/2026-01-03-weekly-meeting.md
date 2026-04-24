---
title: "2026-01-03 주간 회의록 (Notion)"
type: source
status: stable
sources: [raw/2026-01-03-weekly-meeting.md]
updated: 2026-04-24
source_path: raw/2026-01-03-weekly-meeting.md
source_date: 2026-01-03
participants: [조원영, 손민재, 남기훈, 이하은, 전민재, 오지연]
topics: [복습모드, 재채점, 로그아웃, 서버비, AI 문제 생성 테스트, 정기배포 점검]
---

# 2026-01-03 주간 회의록

코테이토 사용과 정기배포 점검을 앞두고, 실제 운영에 바로 영향을 주는 항목을 우선순위로 재정렬한 회의록이다. 재채점, 복습모드 동선, 완료된 문제셋 확인 가능성, 로그아웃 기능, 서버비 같은 운영성 이슈가 핵심으로 다뤄졌다. 기획 측에서는 향후 3~6개월 기능 아이디어도 꺼냈지만, 이 회의의 중심은 알파 배포와 현재 진행분 마감이었다. 배포 준비 회의답게 규칙 재정의보다 현행 불편 해소에 무게가 실렸다.

## 핵심 takeaway

- 복습모드에서 맞고 틀림을 알기 어렵거나 완료된 문제셋을 다시 확인하기 어렵다는 점은 채점 결과 확인 흐름이 아직 거칠다는 신호였다. 근거: [raw/2026-01-03-weekly-meeting.md](../../raw/2026-01-03-weekly-meeting.md) `§원문 스냅샷`, `§AI 후속 블록 스냅샷`. 영향: [문제 풀기](../features/play-player.md), [문제 셋 라이프사이클](../features/problem-set-lifecycle.md)
- 로그아웃 기능은 운영 직전까지 별도 점검 대상이었고, 이후 버튼 위치/드랍다운 정리로 이어지는 흐름의 시작점으로 볼 수 있다. 근거: [raw/2026-01-03-weekly-meeting.md](../../raw/2026-01-03-weekly-meeting.md) `§원문 스냅샷`, `§AI 후속 블록 스냅샷`. 영향: [로그인 / 회원가입 / 마이페이지](../features/auth-and-account.md)

## 영향받는 wiki 페이지

- [features/play-player.md](../features/play-player.md)
- [features/problem-set-lifecycle.md](../features/problem-set-lifecycle.md)
- [features/auth-and-account.md](../features/auth-and-account.md)

