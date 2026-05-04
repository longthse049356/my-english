# Project Context

This repo is for developing SpeakFit English: a personalized English coach PWA for Vietnamese professionals who want to improve interview and workplace speaking.

## Source of truth

- `IDEA_BRIEF.md` is the idea-phase source of truth.
- `BMAD_SPEAKFIT_WORKFLOW.md` is the operating playbook for Solo PM + AI agents.
- `_bmad-output/planning-artifacts/` contains planning outputs produced by BMAD workflows.
- `.cursor/agents/` contains explicit advisory agents.
- `.claude/skills/` contains BMAD skills and customization; keep it unless deliberately migrated.

## Working style

- Default planning language: Vietnamese.
- Product artifacts may be drafted in English when the Solo PM explicitly asks.
- Do not jump from idea/planning into implementation unless the Solo PM asks for implementation.
- Treat the Solo PM as the only accountable decision maker.
- AI agents execute, analyze, and propose; they do not approve scope, merge PRs, or release.

## MVP focus

The MVP validates the daily voice coaching loop:

```text
User opens app daily → sees mission → speaks/shadows → receives feedback → retries → sees progress.
```

Anything outside this loop should be treated as backlog unless the Solo PM explicitly promotes it into MVP scope.
