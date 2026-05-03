---
title: AI 문제 생성
type: feature
status: draft
sources: [raw/2026-04-14-spec-problem-management.md, raw/2025-10-23-weekly-meeting.md, raw/2025-10-26-weekly-meeting.md, raw/2025-11-12-weekly-meeting.md, raw/2025-12-23-weekly-meeting.md, raw/2026-04-26-weekly-meeting.md]
updated: 2026-05-03
---

# AI 문제 생성

mait 문제셋 생성 플로우 안에 포함된 AI 생성 기능. UI 선택지만 있는 수준이 아니라, 별도 API/서버 연동과 운영 안정화 이슈를 가진 기능 축으로 반복 언급됐다.

## 생성 플로우 안에서의 위치

- [문제셋 생성 플로우](./problem-set-creation.md) 2.1에서 생성 방식으로 `AI 생성 / 직접 제작`을 선택한다.
- `질문 만들기`를 누르면 AI 생성 결과를 받아 3단계 편집으로 진입한다.

## 회의록 기준으로 드러난 기술 과제

### 2025-10-23

- `AI 문제 생성 파이썬 API 작업`
- `스프링 -> AI 서버 아키텍처 고려`

이 시점부터 AI 문제 생성은 단순 UI 후속이 아니라 백엔드 통합 구조를 별도 검토해야 하는 기능으로 다뤄졌다.

### 2025-11-12

- `AI 문제 생성 API 설명 및 대응`
- `AI 문제 생성 API 연결을 위한 준비`

백엔드 설명/대응과 프론트 연결 준비가 동시에 남아 있어, API 계약과 화면 연결이 함께 움직이는 기능이라는 점이 확인된다.

### 2025-10-26

- `AI 생성 요청 시 대기 시간이 조금 있는데`
- `별도로 공통으로 쓸 로딩중...`
- `에러 페이지`

AI 생성은 연동 성공 여부만의 문제가 아니라, 처리 중 대기와 실패 상황을 어떻게 보여줄지까지 함께 설계해야 하는 기능으로 인식됐다.

### 2025-12-23 ~ 12-31

- `AI 문제 생성이 간헐적으로 실패하던 이슈 수정`

연동 이후에는 생성 실패 자체가 운영 이슈로 전환돼 안정화와 관측이 필요해졌다.

### 2026-04-26

- GA4에서 **AI 문제 생성 시간**을 측정하되, API 처리 시간이 아니라 사용자가 화면에서 체감하는 시간을 기준으로 보자는 논의가 있었다.
- 로딩 UI에 들어왔다가 나가는 사람 수를 팔로우하는 이탈률 지표도 후보로 올라왔다.

이 시점부터 AI 문제 생성은 호출 성공/실패뿐 아니라, 생성 대기 UX와 이탈 관측까지 연결되는 기능으로 다뤄진다. [2026-04-26 주간 회의록](../sources/2026-04-26-weekly-meeting.md)

## 현재까지 읽히는 성격

- 문제 생성 경험의 일부이지만, 구현 난이도는 별도 외부/내부 서비스 연동 과제에 가깝다.
- 초기에는 `파이썬 API`와 `Spring -> AI 서버` 연결 구조가 핵심이었고, 이후에는 `설명/대응`, `프론트 연결`, `간헐 실패 수정`으로 운영 안정화 단계까지 이어졌다.

## 관련

- [문제셋 생성 플로우](./problem-set-creation.md)
- [제품 분석 / GA4 이벤트](./product-analytics.md)

## 미해결

- AI 서버 호출 구조의 최종 형태
- 대기/실패 상태를 사용자에게 어떤 공통 패턴으로 보여줄지
- 실패 시 사용자 안내/재시도 정책
- 연동 장애를 어떤 로그/지표로 관측하는지
- 화면 기준 AI 생성 시간 측정의 시작/종료 지점

## 출처

- [sources/2025-10-23-weekly-meeting.md](../sources/2025-10-23-weekly-meeting.md)
- [sources/2025-11-12-weekly-meeting.md](../sources/2025-11-12-weekly-meeting.md)
- [sources/2025-12-23-weekly-meeting.md](../sources/2025-12-23-weekly-meeting.md)
- [sources/2026-04-14-spec-problem-management.md](../sources/2026-04-14-spec-problem-management.md)
- [sources/2026-04-26-weekly-meeting.md](../sources/2026-04-26-weekly-meeting.md)
