---
name: meeting-to-jira-tickets
description: MAIT 회의록, Notion QA 문서, Confluence 기획, raw/wiki source를 읽고 Jira 티켓 후보를 분류, 생성, 업데이트하는 워크플로우. Use when the user asks to turn meeting notes or product sources into MAIT-PM backlog/큰틀, MAIT-DEVELOP FE/BE/QA tasks, QA bugs, or release-linked tickets.
---

# Meeting To Jira Tickets

## Purpose

Use this MAIT-specific skill to convert a meeting note or product source into Jira-ready ticket actions. Treat Notion/raw/wiki/Confluence as context and Jira as the execution tracker.

Default to a staged proposal. Do not create or update Jira issues unless the user explicitly asked for live Jira changes or approves the proposed actions.

## Workflow

1. Read the source completely.
   - For repo files, follow the repository `AGENTS.md` rules: preserve raw files, prefer wiki context, and cite source paths.
   - For Notion QA/release pages, fetch page content and discussions when available.
   - For Jira-originated context, fetch the referenced issue and linked issues.
   - If the source already contains an AI-generated or human-written ticket summary, treat it as a hint, not authority. Re-scan the full source for missing product, QA, release, and development items.
2. Extract atomic items. Split mixed notes into one item per decision, feature candidate, development task, QA finding, release action, or follow-up question.
3. Read `references/ticket-taxonomy.md` before classification.
4. Search Jira for duplicates before proposing a new ticket. Prefer updating an existing backlog/큰틀 issue when discussion continues.
5. Classify each item into one Jira action:
   - no Jira action
   - update existing issue
   - create MAIT-PM backlog candidate
   - create MAIT-PM 큰틀/Epic
   - create MAIT-DEVELOP task/story
   - create MAIT-DEVELOP bug
   - attach/link to release
6. Read `references/jira-templates.md` before drafting issue descriptions.
7. Present a proposal table first. Include source evidence, action, project, issue type, title, links, priority/severity, missing information, and confidence.
8. If approved, apply the Jira changes with the Atlassian tools. After changes, report created/updated keys and unresolved manual follow-ups.

## Jira Conventions

- `MAIT` / `MAIT-PM`: product source of truth. Use `큰틀` as the feature-level Epic/candidate issue unless the project configuration requires another issue type.
- `EDU` / `MAIT-DEVELOP`: development execution. Use stories/tasks/bugs for FE, BE, AI, QA fixes, and technical spikes.
- Link development work back to the MAIT-PM issue. Prefer the existing implementation link type when available; otherwise use a relationship link and mention the parent key in the description.
- Use `fixVersions`/Release only for confirmed release targets.

## Output Contract

For proposal mode, return a compact table with these columns:

- source
- extracted item
- classification
- Jira action
- project / issue type
- proposed title
- priority or QA severity
- link target
- missing info
- confidence

End with a short "approval request" section listing the exact create/update operations that would be performed.

## Safety Rules

- Do not turn every sentence into a ticket. Create tickets only for decisions, execution work, QA findings, or trackable follow-ups.
- Do not create a new issue when a relevant existing issue should receive a comment or description update.
- Do not create MAIT-DEVELOP tickets before there is a MAIT-PM owner issue for confirmed product work, unless the item is a standalone bug, spike, or operational task.
- Do not move QA fully out of Notion by default. Treat Notion as the comfortable input surface and Jira as the tracker for P0/P1/P2 issues.
- If a required source, project key, or release target is ambiguous, ask or mark it as missing instead of guessing.

## References

- Read `references/ticket-taxonomy.md` when deciding how to classify items.
- Read `references/jira-templates.md` when creating or updating Jira descriptions.
