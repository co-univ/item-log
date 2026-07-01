# MAIT Ticket Taxonomy

Use this reference to classify source items before creating or updating Jira tickets.

## Source Roles

| Source | Role |
| --- | --- |
| Meeting note | Decisions, open questions, follow-up history |
| Notion QA/release page | QA input surface and release checklist |
| Confluence/spec/wiki | Product and functional detail |
| Figma | Design source |
| MAIT-PM Jira | Product tracking and release scope |
| MAIT-DEVELOP Jira | Development execution tracking |

## Classification Rules

| Source item | Jira result | Notes |
| --- | --- | --- |
| Opinion, idea, concern, or user feedback without development decision | MAIT-PM backlog candidate or existing backlog update | Prefer existing issue comment/description when the topic already exists. |
| Topic explicitly deferred to next meeting | Existing backlog update or MAIT-PM backlog candidate | Add `다음 결정 필요` in description/comment. |
| Development-confirmed product feature/change | MAIT-PM `큰틀`/Epic | This is the source of truth for goal, scope, links, release, and QA. |
| Concrete FE/BE/AI implementation task under a confirmed product item | MAIT-DEVELOP task/story | Link back to the MAIT-PM issue. Prefix title with `[프론트]`, `[백엔드]`, or `[AI]` when useful. |
| Technical uncertainty or architecture investigation | MAIT-DEVELOP spike/task | Use `[조사]` or `[기술검토]` title prefix. Include expected decision output. |
| QA finding that can block or affect release quality | MAIT-DEVELOP bug/task | P0/P1/P2 only. Link to release and MAIT-PM issue when known. |
| QA opinion or minor improvement idea | MAIT-PM backlog update or Epic comment | Usually P3; do not create a dev bug unless the team asks. |
| Release target or release scope change | Update MAIT-PM issue `fixVersions`/release link | Only if release is confirmed. |
| Pure status update with no action | No Jira action | Summarize only. |

## Development Confirmation

Treat an item as development-confirmed only when the source contains a clear decision such as:

- 개발 확정
- 이번 배포/다음 배포에 포함
- 구현 진행
- 디자인/기획 확정 후 개발 진행
- 담당 개발자 or MAIT-DEVELOP work already exists

Do not infer confirmation from enthusiasm, repeated discussion, or a rough idea.

## QA Severity

| Severity | Meaning | Jira action |
| --- | --- | --- |
| P0 | 배포 불가. 반드시 수정 후 배포. | Create Jira bug immediately and mark as release blocker. |
| P1 | 주요 기능 문제. 원칙적으로 수정 후 배포. | Create Jira bug. Track before release. |
| P2 | 불편하지만 배포 가능. 후속 수정 필요. | Create Jira bug/task for follow-up. |
| P3 | 의견, 개선 제안, 사소한 사용성 피드백. | Prefer Epic comment/backlog update. |

Severity heuristics:

- P0: login impossible, data loss, core flow broken, payment/security/privacy risk, production-only fatal issue, release cannot proceed.
- P1: confirmed feature does not work for an important role/path, serious regression, confusing but core flow can be recovered.
- P2: edge case, copy/UI polish with clear follow-up, non-blocking broken state.
- P3: subjective preference, future improvement, unclear idea, design taste discussion.

## Jira Action Decision Tree

1. Is there a concrete action to track?
   - No: no Jira action.
   - Yes: continue.
2. Is this topic already represented by an existing Jira issue?
   - Yes: update/comment/link the existing issue.
   - No: continue.
3. Is development confirmed?
   - No: create or update MAIT-PM backlog candidate.
   - Yes: continue.
4. Is this product-level scope or user-facing value?
   - Yes: create/update MAIT-PM `큰틀`/Epic.
   - No: continue.
5. Is this implementation work?
   - Yes: create MAIT-DEVELOP task/story and link to the MAIT-PM issue.
6. Is this QA/release defect?
   - P0/P1/P2: create MAIT-DEVELOP bug/task.
   - P3: comment/backlog update.

## Duplicate Search Guidance

Search Jira before creating:

- MAIT-PM by core noun phrases, feature name, and release version.
- MAIT-DEVELOP by implementation terms and linked MAIT issue key.
- Existing QA/release bugs by symptom, page, and affected feature.

If a duplicate exists, prefer:

1. Update description when stable source-of-truth fields changed.
2. Add comment when adding discussion history.
3. Link related issues when a separate implementation ticket is still useful.

## Confidence

- High: explicit decision or clear QA defect with source evidence and target project.
- Medium: actionable but missing owner/release/link details.
- Low: ambiguous wording, duplicate risk, or unclear whether development is confirmed.
