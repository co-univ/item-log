# MAIT Jira Templates

Use these templates when drafting Jira issue descriptions. Keep unknown fields blank or mark `미정`; do not invent details.

## MAIT-PM 큰틀/Epic

```md
## 목표

## 배경 / 문제

## 이번 범위

## 이번에 안 하는 것

## 성공 기준 / Acceptance Criteria
- [ ]

## 기획 문서

## 디자인 링크

## 관련 회의록

## 연결된 MAIT-DEVELOP 티켓
-

## 목표 릴리스

## QA 체크리스트
- [ ] 알파 배포 확인
- [ ] 핵심 플로우 확인
- [ ] 권한/역할별 확인
- [ ] 회귀 위험 확인

## 배포 후 확인 항목
- [ ] 주요 기능 정상 동작
- [ ] 기존 주요 이슈 재발 없음
- [ ] 에러/문의 모니터링
```

## MAIT-PM Backlog Candidate

```md
## 제안 / 의견

## 배경

## 기대 효과

## 현재 판단
- 상태: 개발 미확정
- 다음 결정 시점:

## 논의 히스토리
-

## 관련 링크
-

## 확정 전 필요한 것
- [ ] 문제 정의 확인
- [ ] 범위 확인
- [ ] 디자인/기획 필요 여부 확인
- [ ] 목표 릴리스 필요 여부 확인
```

## MAIT-DEVELOP Task/Story

```md
## 작업 목표

## 연결된 MAIT-PM 이슈

## 작업 범위
- [ ]

## 제외 범위

## 참고 링크
-

## 완료 기준
- [ ] 구현 완료
- [ ] 리뷰 완료
- [ ] 알파 확인 가능
- [ ] 관련 QA 이슈 없음 또는 후속 티켓 생성
```

Title prefix guidance:

- `[프론트]` for FE UI/client tasks.
- `[백엔드]` for API, DB, auth, batch, server behavior.
- `[AI]` for AI service/model/prompt/pipeline work.
- `[조사]` or `[기술검토]` for spikes.

## MAIT-DEVELOP QA Bug

```md
## QA 심각도
P0/P1/P2

## 현상

## 기대 결과

## 재현 경로
1.

## 발생 환경
- 알파/리얼:
- 계정/권한:
- 브라우저/디바이스:

## 연결된 MAIT-PM 이슈

## 연결된 릴리스

## 근거
- Notion QA:
- 영상/이미지:
- 회의록:

## 완료 기준
- [ ] 원인 수정
- [ ] 알파 재확인
- [ ] 회귀 확인
- [ ] 릴리스 차단 여부 해소
```

## Jira Proposal Format

When asking for approval before live changes, summarize operations like this:

```md
## 실행 예정 Jira 작업
- 생성: MAIT-PM 큰틀 `[개선] ...`
- 업데이트: MAIT-123 설명에 회의록 히스토리 추가
- 생성: MAIT-DEVELOP 버그 `[P1][온보딩] ...`
- 링크: EDU-000 implements MAIT-000
```
