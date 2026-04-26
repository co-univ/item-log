---
title: "2025-10-23 주간 회의록 (Notion)"
type: source
status: stable
sources: [raw/2025-10-23-weekly-meeting.md]
updated: 2026-04-25
source_path: raw/2025-10-23-weekly-meeting.md
source_date: 2025-10-23
participants: [신유승, 조원영, 전민재, 손민재, 이하은, 오지연]
topics: [AI 문제 생성 API, Spring-AI 서버 아키텍처, 검색 공개범위, 팀관리, 소셜 로그인]
---

# 2025-10-23 주간 회의록

10월 넷째 주 회의는 AI 문제 생성과 검색 공개 정책이 본격적으로 제품 논의의 중심으로 올라온 시점이다. 백엔드는 파이썬 API와 `Spring -> AI 서버` 아키텍처까지 언급하며 AI 생성 연동을 별도 기술 과제로 보기 시작했다. 기획은 `전체 공개 && 복습모드` 검색 논의를 남겼고, 팀관리 기획도 병행했다. 프론트는 소셜 로그인과 빈칸 생성 로직을 손보며 생성/풀이 경험을 같이 정비하고 있었다.

## 핵심 takeaway

- AI 문제 생성은 단순 UI 옵션이 아니라 별도 API와 서버 아키텍처를 갖는 통합 과제로 인식됐다. 근거: [raw/2025-10-23-weekly-meeting.md](../../raw/2025-10-23-weekly-meeting.md) `§파트별 공유`, `§AI 후속 블록 스냅샷`. 영향: [AI 문제 생성](../features/ai-question-generation.md), [문제셋 생성 플로우](../features/problem-set-creation.md)
- 검색 노출을 `전체 공개 && 복습모드`와 연결해 논의한 흔적이 남아 있으며, 이는 나중의 검색/공개범위 정책과 맞닿는다. 근거: [raw/2025-10-23-weekly-meeting.md](../../raw/2025-10-23-weekly-meeting.md) `§기획 논의`. 영향: [문제 검색](../features/problem-search.md), [공개 범위 정책](../decisions/visibility-states.md)
- 팀관리 기획과 소셜 로그인 논의가 동시에 올라오며 팀 참여/계정 진입 흐름이 함께 움직이기 시작했다. 근거: [raw/2025-10-23-weekly-meeting.md](../../raw/2025-10-23-weekly-meeting.md) `§파트별 공유`, `§기획 논의`. 영향: [팀 멤버 권한 관리](../features/team-member-management.md), [로그인 / 회원가입 / 마이페이지](../features/auth-and-account.md)

## 영향받는 wiki 페이지

- [features/ai-question-generation.md](../features/ai-question-generation.md)
- [features/problem-set-creation.md](../features/problem-set-creation.md)
- [features/problem-search.md](../features/problem-search.md)
- [decisions/visibility-states.md](../decisions/visibility-states.md)
- [features/team-member-management.md](../features/team-member-management.md)
- [features/auth-and-account.md](../features/auth-and-account.md)
