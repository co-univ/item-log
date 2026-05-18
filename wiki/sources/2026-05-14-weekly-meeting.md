---
title: 2026-05-14 주간 회의록
type: source
status: stable
sources: [raw/2026-05-14-weekly-meeting.md]
updated: 2026-05-19
date: 2026-05-14
source_path: raw/2026-05-14-weekly-meeting.md
source_url: https://www.notion.so/36087d592b6e80b09fe4cc1a08d75ffb
source_date: 2026-05-14
participants: [신유승, 조원영, 오지연, 이하은, 전민재]
topics: [카테고리, 학습모드, 복습모드, 문제셋 생성, 유형별 제출 현황, 온보딩, 풀이결과 대시보드, 실시간 등수정보, 알림, 다음 배포]
---

# 2026-05-14 주간 회의록

5월 12일 메인 배포 직후 남은 이슈와 다음 배포 항목을 확인한 회의다. 사용자 문의를 통해 카테고리의 의도와 학습/복습/실시간 모드의 차이를 다시 설명했고, 기획 회의에서는 문제 생성 정보 입력 페이지 통일, 유형별 제출 현황, 온보딩, 카테고리 관리 UX를 후속 티켓 단위로 정리했다. 문제 생성은 `MAIT-154` 범위에서 주제와 제목을 통합하고 문제 풀이 대상 필드를 보충 설명으로 흡수하는 방향이 논의됐다. 유형별 제출 현황은 피그마 구조는 확정됐지만 90:10처럼 작은 영역의 텍스트 노출 문제 때문에 퍼센트/개수 기준을 더 정해야 한다. 카테고리 수정 UX는 신규 `MAIT-155`로 만들고, 다음 배포 항목 대부분은 기존 Jira 이슈를 재사용하기로 했다.

## 핵심 takeaway

- 카테고리는 팀별로 자율 설정하는 문제셋 분류 태그에 가깝다. 문제셋별 공통 범위를 담은 해시태그 개념으로 설명됐고, 나중에는 카테고리를 선택해 관련 문제셋을 모아보는 형태도 가능하다고 언급됐다. 근거: [raw/2026-05-14-weekly-meeting.md](../../raw/2026-05-14-weekly-meeting.md) `§[유저] 카테고리가 무엇인가?`. 영향: [카테고리 관리](../features/category-management.md), [핵심 용어](../glossary/core-terms.md)
- 학습모드는 실시간 풀이가 끝난 뒤 자동 복사되는 상태가 아니라 별도 풀이 방식이다. 실시간 모드와 학습 모드에서 풀이 완료된 문제셋을 maker가 복습 모드로 넘길 수 있고, 학습모드는 팀원이 각자 가능한 시간에 문제셋을 한 번에 풀고 제출하는 과제형 모드로 설명됐다. 근거: [raw/2026-05-14-weekly-meeting.md](../../raw/2026-05-14-weekly-meeting.md) `§[유저] 학습모드가 무엇인가?`. 영향: [문제 풀기](../features/play-player.md), [핵심 용어](../glossary/core-terms.md)
- 문제 생성 정보 입력 페이지는 `MAIT-154`에서 통일한다. 주제는 제목과 통합하고, 문제 풀이 대상 필드는 보충 설명에 흡수하며, 직접 제작에서도 자료 업로드·보충 설명 같은 필드는 노출하되 수정 불가 상태를 고려하기로 했다. 공개대상도 디폴트 선택을 없애고 직접 선택하는 항목으로 언급돼 기존 공개범위 결정과의 정합성 확인이 필요하다. 근거: [raw/2026-05-14-weekly-meeting.md](../../raw/2026-05-14-weekly-meeting.md) `§문제 생성 시 정보 입력 페이지 통일`, `§AI의 요약`. 영향: [문제셋 생성 플로우](../features/problem-set-creation.md), [공개 범위 정책](../decisions/visibility-states.md)
- 유형별 제출 현황은 `MAIT-143`의 후속으로 유지한다. 피그마 구조는 확정됐지만 퍼센트 바의 작은 영역에 텍스트를 넣기 어려운 케이스가 있어 퍼센트·개수 노출 기준을 기획과 디자인이 추가로 정해야 한다. 근거: [raw/2026-05-14-weekly-meeting.md](../../raw/2026-05-14-weekly-meeting.md) `§유형별 제출 현황 와이어프레임`. 영향: [문제 풀기](../features/play-player.md), [풀이결과 대시보드](../features/result-dashboard.md)
- 온보딩은 `MAIT-85`와 연결해 디자인 검토를 이어간다. 블러 처리, 전후 이동 버튼, 실시간 랭킹 정보 조회 영역 확대가 논의됐고, 프론트가 실시간 랭킹 정보 영역을 검토해 공유하기로 했다. 근거: [raw/2026-05-14-weekly-meeting.md](../../raw/2026-05-14-weekly-meeting.md) `§온보딩`. 영향: [내비게이션 / 사용자 안내](../features/navigation-and-guidance.md), [문제 풀기](../features/play-player.md)
- 카테고리 관리 UX는 수정 완료를 체크 아이콘으로 처리하고, 취소를 위해 체크/엑스 형태를 두는 방향으로 정리됐다. 목록은 한 번에 하나씩 다루고 최근 추가 항목은 아래로 정렬하며, 신규 `MAIT-155`로 추적한다. 근거: [raw/2026-05-14-weekly-meeting.md](../../raw/2026-05-14-weekly-meeting.md) `§카테고리 관리에서 수정 시 취소가 없음`, `§할일 티켓 정리`. 영향: [카테고리 관리](../features/category-management.md)
- 다음 배포 범위는 기존 Jira 이슈 재사용이 원칙이다. 개인 워크스페이스, 풀이결과 대시보드, 등수 정보, 알림, 팀 삭제, 어드민 페이지는 기존 활성 이슈와 연결해 진행하고, 신규 티켓은 카테고리 관리 수정 UX 1건만 생성됐다. 근거: [raw/2026-05-14-weekly-meeting.md](../../raw/2026-05-14-weekly-meeting.md) `§다음 배포 항목 정리`, `§7. 할일 티켓 정리`.

## 영향받는 wiki 페이지

- [features/problem-set-creation.md](../features/problem-set-creation.md)
- [features/category-management.md](../features/category-management.md)
- [features/play-player.md](../features/play-player.md)
- [features/result-dashboard.md](../features/result-dashboard.md)
- [features/navigation-and-guidance.md](../features/navigation-and-guidance.md)
- [decisions/visibility-states.md](../decisions/visibility-states.md)
- [glossary/core-terms.md](../glossary/core-terms.md)

## 미해결

- 유형별 제출 현황에서 퍼센트/개수 텍스트를 언제, 어디까지 노출할지 기준이 필요하다.
- 문제 카드에 카테고리 값을 노출할지와 문제 카드 UI 개선 범위는 아직 논의 대상으로 남았다.
- 문제 생성 통합 화면에서 주제/제목 통합과 풀이 대상 필드 흡수를 최종 명세에 반영해야 한다.
- 생성 단계 공개대상 직접 선택 언급이 12/10 공개범위 결정과 맞는지 확인해야 한다.
- 온보딩 개선은 6월 말 후보로 언급됐지만 적용 일정과 최종 디자인은 아직 확정되지 않았다.
