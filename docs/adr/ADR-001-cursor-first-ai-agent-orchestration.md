# ADR-001: Cursor-first AI Agent Orchestration

**ADR ID:** ADR-001
**Title:** Use Cursor as the primary orchestration environment for SpeakFit AI agents
**Status:** Accepted
**Date:** 2026-05-04
**Owner:** Solo PM

## Context

SpeakFit previously used OpenCode and Claude CLI folders for agent prompts and BMAD workflow support. The Solo PM wants to manage planning and implementation from Cursor IDE to reduce context switching and improve code/project management.

## Decision

Use Cursor IDE as the primary orchestration environment. Clone OpenCode advisory agents into `.cursor/agents`, keep BMAD delivery skills in `.claude/skills`, and define boundary rules in `.cursor/rules`.

## Consequences

### Positive

- Cursor becomes the main workspace for planning, review, and implementation.
- Advisory agents are explicit-only and less likely to pollute BMAD context.
- BMAD remains the delivery method while Cursor advisory agents act as review gates.

### Negative / Trade-offs

- `.claude/skills` remains for BMAD compatibility, so there are still two AI-related folders.
- Cursor advisory agents must be maintained manually if prompts evolve.

## Alternatives Considered

- Keep `.opencode` active: rejected because it preserves external CLI coupling.
- Move all prompts into global Cursor rules: rejected because it would create too much default context noise.

## Follow-up

- Delete `.opencode` after clone and workflow verification.
