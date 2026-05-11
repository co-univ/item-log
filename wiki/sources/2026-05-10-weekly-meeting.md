---
title: 2026-05-10 주간 회의록
type: source
status: stable
sources: [raw/2026-05-10-weekly-meeting.md]
updated: 2026-05-11
date: 2026-05-10
source_path: raw/2026-05-10-weekly-meeting.md
source_url: https://www.notion.so/35987d592b6e808fb739ea4cdec4fefb
source_date: 2026-05-10
participants: [신유승, 조원영, 손민재, 전민재]
topics: [정기배포, 메인페이지 앵커링, 문제셋 생성, 학습모드, 복습모드, 이모지, 제출 답안 현황, 카테고리, 개인 워크스페이스, GA4, 위키 lint]
---

# 2026-05-10 주간 회의록

5월 12일 정기배포와 5월 17일 대면 회의를 앞두고, 전주에 열린 등수정보·알림·학습모드 개선 논의를 실제 화면/티켓 단위로 더 쪼갠 회의다. 메인페이지는 `MAIT 사용법`과 `주요 기능` 두 섹션에 각각 `#guide`, `#features` 앵커를 붙이기로 했고, 문제셋 생성은 문제 정보 입력 화면을 통일하면서 학습/실시간 모드 선택을 앞쪽에 배치하는 방향으로 정리됐다. 학습모드·복습모드 풀이 화면은 LNB가 있으므로 별도 나가기 버튼이나 브레드크럼을 두지 않아도 된다는 의견이 우세했다. 풀이 중 반응은 기본 이모지 5개와 유형별 제출 답안 현황 UI로 나뉘었고, 객관식 버블 UI·주관식 워드 클라우드·순서 맞추기 Path UI가 후보로 남았다. 카테고리는 목록/문제 카드에 노출할지 디자인 제약을 보고 판단하기로 했으며, Wiki Repo 모순점 정리는 회의 중 공유됐지만 사용자가 별도 요청한 대로 이번 제품 팔로우업 대상에서는 제외됐다.

## 핵심 takeaway

- 메인페이지는 `MAIT 사용법`과 `주요 기능` 섹션에 고정 앵커를 둔다. `MAIT 사용법`은 `#guide`, `주요 기능`은 `#features`이고 FE가 두 태그를 반영한다. 근거: [raw/2026-05-10-weekly-meeting.md](../../raw/2026-05-10-weekly-meeting.md) `§메인페이지 2개 섹션 앵커링 정하기`. 영향: [내비게이션 / 사용자 안내](../features/navigation-and-guidance.md)
- 문제셋 생성 정보 입력 화면은 문제 정보 입력과 문제셋 생성 시 정보 입력을 통일하는 방향으로 정리됐다. 학습모드/실시간모드 선택은 초기 화면 앞쪽에 배치하고, 자료 업로드나 보충 설명처럼 노출은 필요하지만 수정하면 안 되는 필드는 읽기 전용으로 보여야 한다. 근거: [raw/2026-05-10-weekly-meeting.md](../../raw/2026-05-10-weekly-meeting.md) `§문제셋 생성 시 모드선택 기본값 개선 고려`, `§4. 할일 정리`. 영향: [문제셋 생성 플로우](../features/problem-set-creation.md)
- 학습모드와 복습모드 풀이 화면에서는 별도 나가기 버튼이나 브레드크럼을 두지 않는 방향으로 의견이 모였다. LNB가 있으므로 문제풀이 뷰는 NavBar/LNB 기반으로 이동을 처리하고, 브레드크럼 필요여부는 완료 처리됐다. 근거: [raw/2026-05-10-weekly-meeting.md](../../raw/2026-05-10-weekly-meeting.md) `§학습모드 뒤로가기 없는 건에 대한 의견`, `§4. 할일 정리`. 영향: [문제 풀기](../features/play-player.md), [내비게이션 / 사용자 안내](../features/navigation-and-guidance.md)
- 풀이 중 반응과 제출 답안 현황은 분리해서 검토한다. 기본 이모지는 5개로 정리하는 쪽이고, 제출 답안 현황은 객관식 버블 UI, 주관식 워드 클라우드, 순서 맞추기 Path UI를 후보로 둔다. 근거: [raw/2026-05-10-weekly-meeting.md](../../raw/2026-05-10-weekly-meeting.md) `§이모지 고정`, `§정답자 → 제출한 답안 목록 노출하는것`. 영향: [문제 풀기](../features/play-player.md), [핵심 용어](../glossary/core-terms.md)
- 카테고리 추가 후 문제셋 목록이나 문제 카드에 카테고리를 노출할지 여부는 디자인 제약 때문에 확정되지 않았다. 현재 디자인에서는 바로 추가가 어려워 보이나, UI 개선 시 기존/신규 문제셋 노출 영역에서 함께 고려하기로 했다. 근거: [raw/2026-05-10-weekly-meeting.md](../../raw/2026-05-10-weekly-meeting.md) `§문제 셋 카테고리 추가에 따른 문제 셋 목록 조회 시 카테고리 노출 여부`, `§4. 할일 정리`. 영향: [카테고리 관리](../features/category-management.md), [문제셋 생성 플로우](../features/problem-set-creation.md)
- 신규 기능 안내는 업데이트 후 최초 진입 시 현재 온보딩과 같은 형식으로 간단히 안내하고, 상세 설명이 필요하면 기능 설명 페이지 링크를 붙이는 방향이다. 최근 방문 탭, 메인 페이지 앵커링, LNB 쉽게 펼치기도 별도 후속 티켓으로 정리됐다. 근거: [raw/2026-05-10-weekly-meeting.md](../../raw/2026-05-10-weekly-meeting.md) `§새로운 기능 추가 시 안내 방법 고려`, `§7. 할일 티켓 정리`. 영향: [내비게이션 / 사용자 안내](../features/navigation-and-guidance.md)
- Jira 후속은 신규 6건(`MAIT-141`~`MAIT-146`)과 기존 13건 재사용으로 정리됐다. Wiki Repo 모순점 정리 결과는 회의록에 포함됐지만 메잇 팔로우업 제외 메모가 있어 제품 티켓으로는 만들지 않았다. 근거: [raw/2026-05-10-weekly-meeting.md](../../raw/2026-05-10-weekly-meeting.md) `§Wiki Repo 모순점 정리 결과 공유`, `§7. 할일 티켓 정리`.

## 영향받는 wiki 페이지

- [features/navigation-and-guidance.md](../features/navigation-and-guidance.md)
- [features/problem-set-creation.md](../features/problem-set-creation.md)
- [features/play-player.md](../features/play-player.md)
- [features/play-management.md](../features/play-management.md)
- [features/result-dashboard.md](../features/result-dashboard.md)
- [features/category-management.md](../features/category-management.md)
- [features/product-analytics.md](../features/product-analytics.md)
- [features/team-exit-and-deletion.md](../features/team-exit-and-deletion.md)
- [glossary/core-terms.md](../glossary/core-terms.md)

## 미해결

- 통일된 문제 정보 입력 화면의 상세 UI와 저장 시 화면 구성은 아직 확정 필요하다.
- 학습모드 대시보드 동선과 관련 API의 최종 범위는 기존 대시보드/학습모드 티켓에서 계속 검토한다.
- 카테고리를 문제셋 목록/문제 카드에 실제로 노출할지, 노출한다면 어떤 UI 개선과 함께 넣을지 결정이 필요하다.
- 제출 답안 현황의 유형별 UI는 방향 후보만 있고, 데이터 제공 방식과 화면 와이어프레임이 필요하다.
- Wiki Repo 모순점 중 학습모드 결과 위치, 인정답안 실시간 반영, 팀 삭제 데이터 보존 같은 항목은 공유만 되었고 이번 팔로우업 티켓에서는 제외됐다.
