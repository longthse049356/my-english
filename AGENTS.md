# AI Agent Rules Hub

## Purpose

Fast routing hub for AI agents working on SpeakFit. This file points to required rules and source-of-truth docs; it does not replace them.

**IMPORTANT:** This hub does NOT override always-on Cursor rules, BMAD boundary, or UI/UX required reading. It is a navigation aid only.

## Core Rules (read first)

1. `.cursor/rules/project-context.md` — project context, goal hierarchy, MVP scope, working mode
2. `.cursor/rules/context-discipline.md` — token/context control, shard routing discipline
3. `.cursor/rules/bmad-boundary.md` — BMAD vs advisory-agent boundaries
4. `docs/INDEX.md` — file manifest and load routing

## Domain Rules (read when relevant)

- **UI/UX or frontend work** → `.cursor/rules/speakfit-shadcn-ui-contract.mdc` and `.cursor/rules/speakfit-ui-ux-reference.mdc`
- **BMAD workflow work** → `.cursor/rules/bmad-boundary.md` plus relevant BMAD skill instructions
- **Backend story work** → `docs/templates/amelia-be-deep-dive.md` when Amelia/dev agent handles BE-tagged tasks

## Source of Truth Order

1. User instruction in current chat
2. Always-on Cursor rules (`.cursor/rules/*`)
3. BMAD planning artifacts in `_bmad-output/planning-artifacts/`
4. `docs/INDEX.md` routing
5. Planning shards under `docs/planning/` only when needed

## Current Product Direction

- **Goal #1:** Interview portfolio and defendable BE decisions
- **Goal #1 (ngang):** AI agent orchestration story
- **Goal #2:** Working English coach MVP
- **Goal #3:** Backend depth through decision-making and review
- **MVP focus:** Desktop-first daily voice loop
- **Avoid:** Chatbot-first UI, heavy gamification, course marketplace, IELTS/report-card scoring

## Planning File Routing

**PLANNING_QUESTIONS.md** and **IDEA_BRIEF.md** are now **shard indexes**, not full content files.

- Load the index first (~60 lines)
- Then load ONE shard from `docs/planning/planning-questions/` or `docs/planning/idea-brief/`
- For Brief/PRD: load PLANNING_QUESTIONS shards §0, §1, §2, §3, §4, §15 (~800 lines total instead of 3,300)
- For vision/persona: load IDEA_BRIEF shards §2, §4 (~100 lines total instead of 1,600)
- **DO NOT** load all shards in one turn

## Implementation Readiness

Before starting Story 1.2 or any implementation work:

1. Read `docs/implementation-readiness.md` to check gate status
2. Read `docs/onboarding/first-story-walkthrough.md` for Story 1.2 guidance
3. Confirm MUST items are satisfied or explicitly deferred by Solo PM

## Quick Reference

- **Working mode:** 100% vibe coding, no premature optimization
- **Stack:** Bun/Hono/React monorepo, Postgres/Drizzle, R2, TanStack Router/Query, shadcn/ui wrappers
- **Design system:** Quiet Studio — calm professional + warm coach
- **Auth:** Better Auth (preferred, needs vetting)
- **Providers:** STT/TTS/LLM via backend broker, fake mode first

## Related

- [Project Context](.cursor/rules/project-context.md)
- [Context Discipline](.cursor/rules/context-discipline.md)
- [INDEX](docs/INDEX.md)
- [Implementation Readiness](docs/implementation-readiness.md)
- [First Story Walkthrough](docs/onboarding/first-story-walkthrough.md)
