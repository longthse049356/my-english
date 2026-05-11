# AI Work Order

**ID:** WO-2026-001
**Sprint:** Phase 1 / Week 1 — Discovery
**Primary Agent:** Mary / `bmad-agent-analyst`
**Supporting Agents:** Optional: `product-manager`, `skeptic` for review after draft
**Status:** Done

## Goal

Create the first BMAD Product Brief for SpeakFit English from the existing planning canvas, so the Solo PM can approve a clear Discovery artifact before PRD work begins.

## Input Artifacts

- `PLANNING_QUESTIONS.md` — primary planning canvas and source of truth for current Discovery decisions.
- `.cursor/rules/project-context.md` — project context, goal hierarchy, MVP loop, and working mode.
- `docs/decisions.md` — decision log for committed product/process/stack direction.
- `BMAD_SPEAKFIT_WORKFLOW.md` — Solo PM + AI agent operating playbook and BMAD boundaries.
- `IDEA_BRIEF.md` — vision/persona color reference only; do not treat it as primary source of truth.
- `docs/INDEX.md` — context loading policy and artifact maintenance rules.

## Expected Output

- `_bmad-output/planning-artifacts/product-brief.md`
- Brief handoff summary in chat for Solo PM review.
- List of open questions, assumptions, and risks that should feed PRD or RAID.

## Acceptance Criteria

- [ ] Product Brief clearly defines target user, problem, product promise, positioning, MVP boundary, non-goals, and success signals.
- [ ] Brief preserves the MVP center: daily voice coaching loop — user sees mission, speaks/shadows, receives feedback, retries, and sees progress.
- [ ] Brief uses `PLANNING_QUESTIONS.md` as the primary source of truth and uses `IDEA_BRIEF.md` only for vision/persona color when needed.
- [ ] Brief reflects the real goal hierarchy: interview portfolio and AI agent orchestration story are first-class goals, with working English coach as a practical demo outcome.
- [ ] Brief avoids scope creep into a generic English learning app, social/community features, tutor marketplace, heavy gamification, or broad grammar theory.
- [ ] Brief does not over-lock architecture details that belong to Architecture phase, while acknowledging committed directional constraints already logged in `docs/decisions.md`.
- [ ] Brief identifies risky assumptions and open questions explicitly enough for PRD, PRFAQ, or RAID follow-up.
- [ ] Output is concise enough to be reviewable but complete enough to feed BMAD PRD creation.

## Constraints

- Scope: Discovery / Product Brief only.
- Format: Markdown BMAD planning artifact.
- Length: Prefer concise, structured sections over exhaustive transcript-style detail.
- Language: English for the output artifact unless Solo PM explicitly requests Vietnamese.
- Source discipline: Do not load the full `PLANNING_QUESTIONS.md` or `IDEA_BRIEF.md`; read only the sections needed for Product Brief.
- Non-goals: No implementation, no UI code, no database schema, no sprint stories, no architecture specification, no feature expansion beyond MVP.

## Deadline

Phase 1 / Day 1.

## Risk Hints

- The brief may drift into “generic English learning app” instead of the narrower speaking/interview fitness wedge.
- The AI may overuse old `IDEA_BRIEF.md` brainstorm content and override newer decisions in `PLANNING_QUESTIONS.md` or `docs/decisions.md`.
- The brief may prematurely lock implementation details that should wait for PRD, UX, or Architecture phase.
- The brief may understate the portfolio/orchestration goal, even though this is a primary success criterion for the Solo PM.
- The brief may include too many MVP features and weaken the 4-week MVP boundary.

## Success Signal

The Solo PM can read `_bmad-output/planning-artifacts/product-brief.md`, approve it as the Discovery source for PRD creation, and clearly see what is in MVP, what is out, what assumptions remain risky, and why the project is interview-defendable.

## Related

- [[product-brief|Product Brief]] — output artifact.
- [[PLANNING_QUESTIONS|Planning Questions]] — primary input.
- [[IDEA_BRIEF|Idea Brief]] — vision color reference.
- [[BMAD_SPEAKFIT_WORKFLOW|BMAD SpeakFit Workflow]] — playbook.
- [[decisions|Decision Log]] — Brief approval entry.
- [[WO-2026-002-prd|WO-2026-002 PRD]] — work order kế tiếp.
- [[docs/INDEX|Repo Index]].
