# First Story Walkthrough: Story 1.2

## Purpose

Guide a dev agent through Story 1.2 "App/API scaffold and route foundation" without expanding scope into auth, database, storage, or real product flows.

## Required References

1. `_bmad-output/planning-artifacts/epics.md` — Story 1.2 acceptance criteria
2. `_bmad-output/planning-artifacts/architecture.md` — scaffold, monorepo, route/service boundaries, API contract decisions (AR1-AR6, AR11-AR16, AR42)
3. `.cursor/rules/project-context.md` — goal hierarchy and MVP focus
4. `.cursor/rules/context-discipline.md` — file loading discipline
5. `.cursor/rules/speakfit-shadcn-ui-contract.mdc` — only when creating frontend UI shell/wrappers

## Story 1.2 Scope

Build or verify scaffold foundation only:

- `apps/web` frontend app
- `apps/api` Hono API app
- `packages/shared` or scaffold-equivalent shared package
- Learner route placeholders for `Today`, `Onboarding`, `Missions`, `Phrases`, `Progress`, `Settings`
- Calm not-found recovery route
- `/v1/health` endpoint
- Stable success and error envelope examples
- Project-owned API client wrapper location
- Project-owned SpeakFit UI wrapper location
- Basic install/lint/typecheck/test scripts or documented scaffold limitations

## Explicit Non-Scope

Do NOT build:

- Real auth
- Real database schema
- Drizzle migrations
- R2/object storage
- Real onboarding flow
- Real mission generation
- Real recording/STT/TTS/LLM provider flow
- Operator page implementation unless Story 1.2 ACs are updated

## Suggested Execution Steps

1. **Inspect existing repo structure**
   - Check if monorepo already exists
   - Check if `apps/`, `packages/` folders exist
   - Check for existing `package.json`, `bun.lockb`, or other package manager artifacts

2. **Confirm starter choice against architecture**
   - Architecture AR1 prefers `bhvr` template
   - If `bhvr` lacks required backend guardrails, evaluate `vex-app`
   - If both mismatch, use custom `apps/web` Vite React and `apps/api` Bun/Hono scaffold
   - Document choice in story implementation notes

3. **Create or verify monorepo directories**
   - `apps/web` — React/Vite PWA
   - `apps/api` — Bun/Hono REST API
   - `packages/shared` — shared Zod schemas and types

4. **Create frontend route placeholders**
   - Use TanStack Router (AR4)
   - Create routes: `/today`, `/onboarding`, `/missions`, `/phrases`, `/progress`, `/settings`
   - Create 404 not-found page with calm recovery copy
   - Each route can be a simple placeholder component with route name and "Coming soon" message

5. **Create backend health route**
   - Hono app with `/v1/health` endpoint (AR11)
   - Return success envelope: `{ data: { status: "ok", timestamp: Date.now() }, meta: { version: "0.1.0" } }`
   - Implement error envelope structure (AR14): `{ error: { code, message, requestId, details?, fieldErrors?, retryable?, retryAfter?, hint? } }`

6. **Create shared envelope/schema placeholders**
   - Only where needed for Story 1.2
   - Success envelope type
   - Error envelope type
   - Health response schema

7. **Create API client wrapper location**
   - So pages do not scatter ad-hoc fetch
   - Can be a simple wrapper around fetch with base URL and error handling
   - Location: `apps/web/src/lib/api-client.ts` or equivalent

8. **Create SpeakFit UI wrapper directory**
   - Without overbuilding design system
   - Location: `apps/web/src/components/speakfit/ui/` (AR6)
   - Can start with a simple Button wrapper as example
   - Do NOT import `cursor/canvas` (AR6)

9. **Add or document scripts**
   - `install` — install dependencies
   - `dev` — start dev servers
   - `build` — build for production
   - `lint` — run linter
   - `typecheck` — run TypeScript type checking
   - `test` — run tests (can be placeholder if test setup is deferred)
   - Document any scaffold limitations

10. **Verify every Story 1.2 acceptance criterion**
    - See "Acceptance Criteria Trace" section below

11. **Write story implementation notes**
    - Document any scaffold deviation from architecture
    - Document any deferred items
    - Document any decisions made during implementation

## Acceptance Criteria Trace

Copy from `_bmad-output/planning-artifacts/epics.md` Story 1.2:

### AC1: Repository structure verified/created

**Given** empty or unverified project scaffold  
**When** implementation starts  
**Then** repository has verified or created structure for `apps/web`, `apps/api`, and `packages/shared`  
**And** any deviation from planned paths is documented in the story implementation notes

- [ ] Pass/Fail: ___
- Evidence: ___

### AC2: Frontend app serves learner routes

**Given** frontend app starts in local development  
**When** user opens web app  
**Then** TanStack Router can serve learner routes for `Today`, `Onboarding`, `Missions`, `Phrases`, `Progress`, and `Settings`  
**And** unknown learner routes show a calm not-found recovery state

- [ ] Pass/Fail: ___
- Evidence: ___

### AC3: Backend serves health endpoint

**Given** backend app starts in local development  
**When** API health route is requested  
**Then** Hono serves `/v1/health` with `{ data, meta? }` success envelope  
**And** errors follow stable `{ error: { code, message, requestId, details?, fieldErrors?, retryable?, retryAfter?, hint? } }` envelope

- [ ] Pass/Fail: ___
- Evidence: ___

### AC4: Shared contracts exist

**Given** shared app/API contracts are needed  
**When** web calls API client wrapper  
**Then** contracts live in `packages/shared` or scaffold-equivalent shared package  
**And** frontend does not call backend routes through ad-hoc fetch scattered across pages

- [ ] Pass/Fail: ___
- Evidence: ___

### AC5: Frontend UI foundation uses project wrappers

**Given** first frontend UI foundation  
**When** Quiet Studio shell renders  
**Then** app uses project-owned SpeakFit UI wrapper location such as `apps/web/src/components/speakfit/ui/`  
**And** production code does not import `cursor/canvas`

- [ ] Pass/Fail: ___
- Evidence: ___

### AC6: Local validation scripts exist

**Given** local validation runs  
**When** developer executes available project checks  
**Then** install, lint, typecheck, and test scripts exist or are documented as pending scaffold limitations  
**And** failing checks caused by this story are fixed before handoff

- [ ] Pass/Fail: ___
- Evidence: ___

## Common Issues & Fixes

### Issue: bhvr template doesn't match our structure

**Fix:** Document deviation in story implementation notes. Adapt folder names to match planned structure or update architecture.md with actual paths.

### Issue: TanStack Router setup unclear

**Fix:** Check architecture.md AR4 for guidance. Use TanStack Router v1 file-based routing or route configuration.

### Issue: Hono error envelope structure unclear

**Fix:** Check architecture.md AR14 for exact error envelope structure. Implement a helper function to generate error responses.

### Issue: SpeakFit UI wrapper location unclear

**Fix:** Check `.cursor/rules/speakfit-shadcn-ui-contract.mdc` for guidance. Create `apps/web/src/components/speakfit/ui/` folder.

### Issue: Test setup is complex

**Fix:** Document test setup as deferred. Create placeholder test script that passes. Update implementation-readiness.md with test strategy decision.

## Related

- [Epics & Stories](../../_bmad-output/planning-artifacts/epics.md) — Story 1.2 full details
- [Architecture](../../_bmad-output/planning-artifacts/architecture.md) — AR1-AR6, AR11-AR16, AR42
- [Implementation Readiness](../implementation-readiness.md) — gate checklist
- [Project Context](../../.cursor/rules/project-context.md) — goal hierarchy
