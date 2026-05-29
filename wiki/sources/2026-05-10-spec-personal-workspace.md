---
title: 개인 워크스페이스 명세서
type: source
status: stable
sources: [raw/2026-05-10-spec-personal-workspace.md]
updated: 2026-05-30
date: 2026-05-10
source_path: raw/2026-05-10-spec-personal-workspace.md
source_url: https://youthing.atlassian.net/wiki/spaces/~712020e8812b2eb985491caedb51d1b356e362/pages/122519555
source_id: 122519555
source_date: 2026-05-10
participants: []
topics: [개인 워크스페이스, 메인 페이지 플로우, 문제 관리, 문제 풀기, 풀이결과 대시보드, 카테고리 관리]
---

# 개인 워크스페이스 명세서

팀이 없거나 `바로 시작하기`로 진입한 사용자를 위한 개인 워크스페이스 기능 명세다. 개인 워크스페이스는 팀과 달리 멤버를 관리하는 공간이 아니며, 사용자는 maker에 해당하는 것으로 처리되어 항상 문제 관리로 이동한다. 문제 관리에서는 기존 미트볼/버튼 UI를 유지하되 실시간 모드와 풀이 시작/종료 기능을 제외한다. 문제 풀기는 학습 모드와 복습 모드만 제공하고, 풀이 결과 대시보드는 랭킹 영역 없이 정답률을 상단에 둔다. 팀관리 영역은 개인 워크스페이스에서 카테고리 관리로 명칭을 바꾸고, 멤버관리는 비활성화한다.

## 핵심 takeaway

- 팀이 없는 사용자는 로그인 시 개인 워크스페이스가 자동 생성되고 해당 워크스페이스로 이동한다. 로그인 전 `바로 시작하기`를 누른 경우에도 로그인 후 개인 워크스페이스를 생성해 이동한다. 근거: [raw/2026-05-10-spec-personal-workspace.md](../../raw/2026-05-10-spec-personal-workspace.md) `§메인 페이지 플로우`. 영향: [개인 워크스페이스](../features/personal-workspace.md), [내비게이션 / 사용자 안내](../features/navigation-and-guidance.md)
- 팀이 있는 사용자는 최근 방문 팀 기준으로 이동하되, player는 `문제 풀기`, maker는 `문제 관리` 탭으로 이동한다. 개인 워크스페이스는 maker에 해당하므로 항상 `문제 관리`로 이동한다. 근거: [raw/2026-05-10-spec-personal-workspace.md](../../raw/2026-05-10-spec-personal-workspace.md) `§최근 방문 팀 이동`. 영향: [개인 워크스페이스](../features/personal-workspace.md), [권한 체계](../decisions/permission-roles.md)
- 개인 워크스페이스의 문제 관리에서는 본인이 모든 문제 풀이를 완료하면 완료 상태로 바뀌고, 실시간 모드와 풀이 시작/종료 기능은 제외된다. 근거: [raw/2026-05-10-spec-personal-workspace.md](../../raw/2026-05-10-spec-personal-workspace.md) `§문제 관리`. 영향: [개인 워크스페이스](../features/personal-workspace.md), [문제셋 라이프사이클](../features/problem-set-lifecycle.md), [풀이관리](../features/play-management.md)
- 개인 워크스페이스의 문제 풀기는 학습 모드와 복습 모드만 제공하며 실시간 풀이 기능은 제외된다. 근거: [raw/2026-05-10-spec-personal-workspace.md](../../raw/2026-05-10-spec-personal-workspace.md) `§문제 풀기`. 영향: [문제 풀기](../features/play-player.md), [문제셋 생성 플로우](../features/problem-set-creation.md)
- 개인 워크스페이스의 풀이 결과 대시보드는 랭킹 영역을 제외하고 정답률 영역을 상단에 배치한다. 근거: [raw/2026-05-10-spec-personal-workspace.md](../../raw/2026-05-10-spec-personal-workspace.md) `§풀이 결과 대시보드`. 영향: [풀이결과 대시보드](../features/result-dashboard.md)
- 개인 워크스페이스에서는 팀관리 명칭을 카테고리 관리로 바꾸고, 기존 카테고리 관리 화면은 유지하되 멤버관리는 비활성화한다. 근거: [raw/2026-05-10-spec-personal-workspace.md](../../raw/2026-05-10-spec-personal-workspace.md) `§팀관리`. 영향: [카테고리 관리](../features/category-management.md), [팀 멤버 권한 관리](../features/team-member-management.md)

## 영향받는 wiki 페이지

- [features/personal-workspace.md](../features/personal-workspace.md)
- [features/navigation-and-guidance.md](../features/navigation-and-guidance.md)
- [features/problem-set-creation.md](../features/problem-set-creation.md)
- [features/problem-set-lifecycle.md](../features/problem-set-lifecycle.md)
- [features/play-management.md](../features/play-management.md)
- [features/play-player.md](../features/play-player.md)
- [features/result-dashboard.md](../features/result-dashboard.md)
- [features/category-management.md](../features/category-management.md)
- [features/team-member-management.md](../features/team-member-management.md)
- [decisions/permission-roles.md](../decisions/permission-roles.md)
- [glossary/core-terms.md](../glossary/core-terms.md)

## 미해결

- 최근 방문 팀 저장 기준과 개인 워크스페이스가 최근 방문 대상에 포함되는지 확인이 필요하다.
- 개인 워크스페이스 문제 관리에서 `풀이관리`라는 탭명 자체를 숨길지, 기존 UI 안에서 풀이 시작/종료 액션만 제거할지는 명세에 직접 쓰여 있지 않다.
- 개인 워크스페이스의 완료 상태가 복습 전환과 공개 범위 설정을 어떻게 연결하는지는 추가 확인이 필요하다.
