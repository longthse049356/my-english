---
stepsCompleted:
  - step-01-init
  - step-02-context
  - step-03-starter
  - step-04-decisions
  - step-05-patterns
  - step-06-structure
  - step-07-validation
  - step-08-complete
lastStep: 8
status: complete
completedAt: 2026-05-09
inputDocuments:
  - _bmad-output/planning-artifacts/product-brief.md
  - _bmad-output/planning-artifacts/prd.md
  - _bmad-output/planning-artifacts/prd-validation-report.md
  - _bmad-output/planning-artifacts/ux-design-specification.md
  - .cursor/rules/project-context.md
  - docs/decisions.md
  - docs/raid.md
  - docs/ui-ux/shadcn-tailwind-implementation-contract.md
  - docs/ui-ux/speakfit-quiet-studio-reference.md
  - docs/adr/ADR-001-cursor-first-ai-agent-orchestration.md
workflowType: architecture
project_name: My-English
user_name: Longth
date: 2026-05-08
---

# Architecture Decision Document

_This document builds collaboratively through step-by-step discovery. Sections are appended as we work through each architectural decision together._

## Step 1 — Architecture Workflow Initialization

**Purpose:** Initialize the Architecture workflow, confirm source documents, and establish the architecture artifact for collaborative technical decision making.

**Workflow source:** `.claude/skills/bmad-create-architecture/steps/`

**Output artifact:** `_bmad-output/planning-artifacts/architecture.md`

**Input documents:** The source documents listed in the frontmatter provide product scope, PRD requirements, UX constraints, project context, decision history, RAID items, UI implementation contract, and prior ADR grounding for downstream architecture decisions.

**Initialization status:** Complete. The Architecture workflow is ready to continue into project context analysis.

## Project Context Analysis

### Requirements Overview

**Functional Requirements:**
SpeakFit defines 60 functional requirements across 12 areas. Architecturally, they converge on one daily speaking practice loop: onboarding into a default mission, listening or shadowing, recording or submitting manual text, receiving concise feedback, retrying immediately, saving useful phrases, reviewing and reusing saved language, and tracking lightweight progress. Supporting requirements cover profile setup, fallback recovery, privacy trust, usage tracking, and private testing operations.

**Non-Functional Requirements:**
SpeakFit defines 35 non-functional requirements across 7 areas: performance, security/privacy, reliability/resilience, accessibility, scalability/cost control, integration, and maintainability/portfolio evidence. The architecture must support fast time-to-practice, protected learner data, graceful provider failure, WCAG AA-friendly interactions, per-user usage control, and traceable decisions for the Solo PM plus AI-agent workflow.

**Scale & Complexity:**
- Primary domain: full-stack web app / PWA with AI-assisted speaking practice.
- Complexity level: high, but not enterprise.
- Estimated architectural components: 10 major areas.
- Real-time features: low collaboration risk, medium interaction responsiveness demand.
- Multi-tenancy: none for MVP.
- Regulatory pressure: moderate privacy sensitivity, not formal certification-heavy.
- Integration complexity: high because of auth, AI feedback, TTS, STT, recording, storage, and usage tracking.
- User interaction complexity: high because of voice practice, retry, fallback, and reuse flows.
- Data complexity: moderate because of audio, transcripts, saved phrases, progress, and usage metrics.

### Technical Constraints & Dependencies

- Desktop-first browser PWA is core. Mobile support is secondary.
- Core coaching assumes network access. Offline-first speech coaching is out of scope for MVP.
- Browser-based recording, replay, and microphone permission handling must work on supported desktop browsers first.
- Managed LLM, TTS, and STT providers are preferred; no custom speech model training is required for MVP.
- Sensitive learner data includes recordings, transcripts, feedback, saved phrases, and interview/workplace answers.
- Data handling, retention, deletion, and provider disclosure rules must be explicit before implementation.
- Auth, storage, and session handling must support learner artifacts plus lightweight progress and usage tracking.
- Cost and quota tracking for AI/TTS/STT calls is a core dependency, not an afterthought.
- Internal operator tooling must support seeded missions, validation, and dogfood testing.
- Production UI must follow the Quiet Studio shell and the shadcn/Tailwind implementation contract.

### Cross-Cutting Concerns Identified

- Voice pipeline resilience and manual text fallback.
- Privacy, consent, retention, deletion, and provider notice.
- Feedback quality, tone, and retry-loop coherence.
- Saved phrase context, review, and reuse behavior.
- Cost control, quota observability, and provider risk.
- Desktop-first shell layout, navigation, and focused study flow.
- Accessibility and keyboard support.
- Validation signals and traceability for Solo PM plus AI-agent orchestration.

This analysis points to a focused but multi-integration architecture. The core risk is not feature breadth; it is keeping the daily speaking loop fast, private, and resilient while preserving enough traceability for dogfood validation and future interview defense.

## Starter Template Evaluation

### Primary Technology Domain

Full-stack web application / desktop-first PWA with a separate TypeScript frontend and backend-oriented API layer.

SpeakFit is not only a static frontend or generic Next.js app. It needs a focused React PWA shell, browser recording, AI/TTS/STT provider integration, Postgres persistence, Drizzle schema/migrations, R2 audio/object storage, usage/quota tracking, and backend decisions that are explainable for interview portfolio use.

### Starter Options Considered

**Option 1 — Next.js + shadcn/ui starter**

Current setup can use `create-next-app@latest` plus `shadcn@latest`.

Pros:
- Strong React/App Router ecosystem.
- Easy `shadcn/ui` and Tailwind integration.
- Good frontend velocity for Quiet Studio UI.
- Strong deployment path on Vercel.

Cons:
- API/backend can become too framework-hidden for this project's portfolio goal.
- Bun + Hono + Drizzle + R2 stack preference is not naturally centered.
- Server actions/App Router patterns may blur explicit backend architecture learning.

**Assessment:** Good frontend foundation, weaker match for interview-defendable BE learning unless paired with a separate Hono API.

**Option 2 — T3 Stack**

Current setup uses:

```bash
npm create t3-app@latest
```

Pros:
- Strong TypeScript full-stack defaults.
- Optional auth, ORM, tRPC, Tailwind.
- Good patterns for typed app development.

Cons:
- Prisma/tRPC/Next-centric defaults diverge from reconfirmed Bun + Hono + Drizzle direction.
- More opinionated than needed for SpeakFit MVP.
- Does not naturally surface Hono HTTP server, explicit API boundaries, signed URL/object storage, and provider pipeline concepts.

**Assessment:** Technically strong, but not aligned with selected architecture learning goals.

**Option 3 — Vite React TypeScript PWA**

Current setup can use:

```bash
npm create @vite-pwa/pwa@latest
```

Pros:
- Clean frontend PWA base.
- Excellent fit for React + Tailwind + shadcn/ui wrapper layer.
- Keeps frontend separated from backend concerns.
- Good for desktop-first shell and fast iteration.

Cons:
- Backend must be created separately.
- Does not provide auth, Drizzle, Postgres, R2, or provider integration.

**Assessment:** Strong frontend starter if paired with a Bun/Hono backend starter.

**Option 4 — Bun/Hono/React full-stack starter (`bhvr`)**

Current setup:

```bash
bun create bhvr@latest my-app
```

Pros:
- Bun + Hono + React + Vite + TypeScript in one full-stack monorepo.
- Shared types and monorepo ergonomics.
- Good directional fit with chosen backend stack.
- Faster path than hand-assembling separate apps.

Cons:
- Need verify fit with Drizzle/Postgres/R2/auth needs.
- May impose monorepo conventions that need adjustment.
- `shadcn/ui`, Quiet Studio wrappers, PWA support, and backend learning guardrails still need explicit setup.

**Assessment:** Best starter candidate if its structure stays simple and does not hide backend concepts.

**Option 5 — Bun/Hono/Drizzle-focused starter (`vex-app` or similar)**

Current setup:

```bash
bun create vex-app@latest my-app
```

Pros:
- Closer to backend learning goals.
- Includes stronger guardrails around Drizzle, tests, and code quality in some variants.
- Better fit for explicit API/data architecture.

Cons:
- Less proven than broader React/Next starters.
- UI/PWA/shadcn fit may require more work.
- Needs careful vetting before adoption.

**Assessment:** Worth considering if backend scaffold quality beats `bhvr`, but not default choice without deeper repository inspection.

### Selected Starter: Bun/Hono/React monorepo starter, preferably `bhvr`, with SpeakFit-specific architecture hardening

**Rationale for Selection:**

The project already reconfirmed `Bun + Hono + Postgres + Drizzle + R2` because architecture must surface backend concepts for interview defense. A Bun/Hono/React monorepo starter gives the cleanest foundation for that goal while preserving React frontend velocity.

The selected starter should be treated as a scaffold, not as final architecture. First implementation story should initialize the monorepo, then add/verify:

- React + Vite frontend app.
- Tailwind + `shadcn/ui`.
- SpeakFit-owned UI wrappers under `src/components/speakfit/ui/` or app-equivalent frontend path.
- Hono API app with explicit route/service/repository boundaries.
- Drizzle + Postgres.
- R2 or S3-compatible object storage abstraction.
- Auth/session approach.
- AI/TTS/STT provider abstraction.
- Usage/quota tracking.
- PWA shell configuration.
- Test/lint/typecheck commands.
- BE Learning Mode documentation hooks for backend stories.

**Initialization Command:**

```bash
bun create bhvr@latest speakfit-english
```

If deeper inspection shows `bhvr` lacks needed backend guardrails, fallback candidate:

```bash
bun create vex-app@latest speakfit-english
```

If both starters impose too much mismatch, use a custom scaffold:

```bash
bun create vite@latest apps/web --template react-ts
bun init apps/api
```

Then manually add Hono, Drizzle, Tailwind, shadcn/ui, PWA plugin, and workspace tooling.

### Architectural Decisions Provided by Starter

**Language & Runtime:**
TypeScript across frontend/backend, Bun runtime, React frontend, Hono API.

**Styling Solution:**
Tailwind and `shadcn/ui` should be added or verified, then wrapped through SpeakFit-owned UI components to preserve Quiet Studio direction.

**Build Tooling:**
Vite for frontend build/dev flow. Bun for package/runtime workflow. Monorepo scripts should expose dev, build, lint, typecheck, test, db commands.

**Testing Framework:**
Starter may provide limited tests. Architecture should require frontend component/unit tests where valuable and backend route/service tests for auth, recording metadata, attempts, feedback, saved phrases, usage/quota, and fallback paths.

**Code Organization:**
Preferred organization is monorepo with separate frontend and API apps plus shared package/types where useful. Backend should keep explicit route, validation, service, repository, provider, and storage boundaries.

**Development Experience:**
Hot reload for frontend/API, TypeScript strict mode, Drizzle migrations, environment validation, and clear commands for AI agents. The scaffold must stay understandable to the Solo PM for BE interview explanations.

**Note:** Project initialization using this command should be first implementation story, with immediate architecture-hardening follow-up rather than trusting starter defaults.

## Core Architectural Decisions

### Decision Priority Analysis

**Critical Decisions (Block Implementation):**
- Data architecture: PostgreSQL, Drizzle ORM, Drizzle Kit migrations, Docker Compose local development, explicit relational schema, R2/S3-compatible object metadata model, Zod validation, Redis deferred.
- Authentication and security: library-backed auth, invite/email magic link or OTP preferred for MVP, opaque server-side cookie sessions, backend RBAC, CSRF/CORS/rate limiting, private R2 access, deletion/export trust layer.
- API and communication: REST-first Hono API, Zod/OpenAPI contracts, `attempt` as central workflow aggregate, backend speech/AI broker, explicit async state machine, idempotency, signed URL lifecycle, structured error taxonomy.
- Frontend architecture: React/Vite desktop-first PWA, TanStack Router and TanStack Query, `shadcn/ui` through SpeakFit wrappers, Quiet Studio shell, `Today` three-area practice workspace, no TanStack Start for MVP.
- Infrastructure and deployment: managed MVP infrastructure, Railway or equivalent Bun/Hono API hosting, managed Postgres, Cloudflare R2, GitHub Actions CI, typed environment validation, structured redacted observability.

**Important Decisions (Shape Architecture):**
- Provider abstraction for STT/TTS/LLM with dogfood benchmarks before default provider choice.
- Postgres-backed job/status abstraction from MVP even if Redis/BullMQ is deferred.
- Operator route separation, backend gating, and audit logging.
- PWA static-shell caching only; no service-worker/browser caching of audio, transcripts, feedback, prompts, or provider payloads.
- OpenAPI is the external/API contract; Hono RPC typing is internal DX only.

**Deferred Decisions (Post-MVP):**
- Redis/BullMQ or separate worker infrastructure until processing throughput, rate limiting, or reliability demands it.
- WebSocket/SSE until streaming feedback, live pronunciation, or operator monitoring is validated.
- Enterprise auth features such as SSO, organizations, SCIM, device management, and fine-grained permissions.
- Multi-region deployment, Kubernetes, complex CDN routing, analytics warehouse, and heavy admin console.
- Custom speech model training and custom STT/TTS hosting.

### Data Architecture

- Database: PostgreSQL, with current stable major line verified as PostgreSQL 18 in 2026. Managed Postgres may run another supported version depending provider support.
- ORM: Drizzle ORM, current npm version checked as `0.45.2`; Drizzle Kit current npm version checked as `0.31.10`.
- Migrations: Drizzle Kit migrations committed to the repository and run through explicit migration commands.
- Local development: Docker Compose Postgres for reproducible local and AI-agent work.
- Schema style: explicit relational schema, not generic JSON-first storage.
- Core schema areas include users/auth identities, learner profiles, missions, attempts, recordings/audio object metadata, transcripts, feedback, saved phrases, phrase reuse events, progress snapshots/metrics, usage events/quota counters, provider call logs, and operator audit logs.
- Object storage: raw audio artifacts live in R2 or S3-compatible storage only when needed; Postgres stores ownership, retention, and object metadata.
- Retention metadata should include fields such as `audio_retention_until`, `deleted_at`, `provider_request_id`, and `consent_version` where relevant.
- Validation: Zod validates API boundaries, provider inputs/outputs, and LLM structured outputs. Database constraints protect persistence integrity.
- Caching: Redis is deferred for MVP. Start with Postgres, route-level query discipline, and explicit quota/status tables. Add Redis only when rate limiting, queueing, or repeated lookup patterns prove it necessary.

### Authentication & Security

- Authentication will use a boring, library-backed approach. Preferred implementation is Better Auth with Hono integration and Drizzle/Postgres persistence, pending implementation vetting for Bun/Hono/Drizzle compatibility. Auth.js is a fallback only if Better Auth integration introduces excessive glue code. Custom auth is rejected for MVP.
- MVP onboarding will prefer invite-only beta access with email magic link or OTP. Password-based auth and Google OAuth may be added later if product testing shows need, but social-only login is rejected.
- Session management will use backend-owned opaque server-side sessions stored in Postgres and delivered via secure, HttpOnly cookies. JWT in localStorage/sessionStorage is rejected.
- Cookie-authenticated mutating requests require CSRF protection plus strict Origin/Referer validation where applicable. CORS must use explicit allowlists; wildcard CORS with credentials is rejected.
- Authorization will use a minimal backend-enforced role model: learner and operator. Learners can access only their own artifacts. Operator tooling must be server-gated, deny-by-default, audited for sensitive actions, and excluded from learner flows.
- Provider keys, DB credentials, R2 credentials, signing secrets, and auth secrets stay server-side in environment/secret management. Frontend never receives STT/TTS/LLM provider keys.
- R2/audio storage is private by default. Signed upload/read URLs must be short-lived, scoped to authenticated users, size/type/duration limited, and backed by DB ownership checks. Public recording buckets are rejected.
- Sensitive learner data includes recordings, transcripts, feedback, saved phrases, manual text submissions, and workplace/interview answers. Audio retention should be short by default; transcript/progress retention should match product need.
- Delete/export are MVP trust-layer requirements. Deletion must cover DB records and R2 objects where under SpeakFit control. Provider retention and backup purge limits must be disclosed honestly.
- Logs must redact secrets, signed URLs, provider payloads, raw transcripts, and audio references unless explicitly needed for debugging. Provider integrations should prefer no-training/zero-retention modes where available.
- Rate limiting is required for login, magic link/OTP, upload, signed URL generation, STT/TTS broker calls, feedback generation, export, and delete endpoints. Redis can remain deferred, but MVP still needs a production-safe limiter through Postgres, platform, or gateway controls.
- Browser hardening includes secure headers, CSP, frame protection, HSTS in production, microphone-focused Permissions-Policy, no mixed content, and avoiding service-worker/browser caching of audio/transcripts unless explicitly designed later.

### API & Communication Patterns

- SpeakFit will use a REST-first Hono API. REST routes and OpenAPI schemas are the official API contract; Hono RPC client typing (`hc()`) is allowed only as an internal monorepo DX layer behind a project-owned frontend API client wrapper.
- API routes will use `/v1` versioning from the first implementation story.
- Zod schemas will validate request bodies, params, query strings, provider inputs, provider outputs, LLM structured outputs, and public response DTOs. Validation errors must not leak sensitive payloads.
- OpenAPI documentation will be generated using `@hono/zod-openapi` or equivalent. `@hono/zod-openapi` current npm version checked as `1.4.0`; `@hono/zod-validator` current npm version checked as `0.8.0`.
- Public OpenAPI excludes operator/internal provider routes; internal docs may include them behind auth. CI should fail if OpenAPI generation breaks.
- Route design will be resource-oriented around the central `attempt` aggregate. Route groups include auth, me/profile, missions, attempts, recordings, phrases, progress, privacy export/delete, and operator. Speech/feedback provider actions must be server-owned broker operations, not arbitrary client prompt/provider endpoints.
- The attempt lifecycle is an explicit API contract, not an implementation detail. MVP statuses include created, upload_pending, uploaded, processing_stt, stt_ready, processing_feedback, feedback_ready, needs_manual_fallback, failed_retryable, failed_final, expired, and cancelled. Illegal transitions return `409 invalid_state_transition`.
- Long-running speech/feedback operations return `202 Accepted` plus attempt/job status. Client polling uses bounded intervals, backoff, max duration, and `Retry-After` where useful. WebSocket/SSE is deferred unless streaming feedback or live pronunciation becomes a validated need.
- Queue infrastructure can be deferred, but job/status abstraction cannot. Provider work expected to exceed short sync timeout must run outside the request lifecycle through an attempt task/job model. Initial workers may run in the same backend process; later workers can move out without changing API contracts.
- Mutating endpoints that browser/network retries can repeat must support idempotency keys scoped by user, route, and operation. Duplicate requests return the original result; conflicting payloads return `409 idempotency_conflict`.
- Audio upload/download uses private R2 objects and short-lived signed URLs. Backend creates recording metadata before upload, generates non-user-controlled object keys, enforces type/size/duration limits, requires upload confirmation, validates object metadata, and cleans orphaned objects.
- API errors use a stable envelope with `code`, user-safe `message`, `requestId`, optional `details`, `retryable`, `retryAfter`, `fieldErrors`, and recovery/fallback hints where useful. Provider errors are normalized into SpeakFit error codes and never leaked raw to the frontend.
- Backend broker interfaces normalize STT/TTS/LLM providers behind capability, timeout, retry, fallback, retention, and cost-attribution contracts. Client requests may reference attempts/missions/recordings but must not send arbitrary provider options or system prompts.
- Rate limits and quotas apply by route class and cost dimension: auth, magic link/OTP, signed URL generation, upload, STT audio minutes, TTS characters, feedback calls, concurrent jobs, retry bursts, export/delete, and operator actions.
- Observability uses structured redacted logs with request ID, user ID/internal hash, attempt ID, recording ID, job ID, provider call ID, operation, provider/model, latency, status, error code, and cost units where available. Logs must redact secrets, signed URLs, raw transcripts, raw prompts, audio references, OTPs, session tokens, and provider keys.
- Operator routes require backend RBAC, audit logging, hard pagination limits, restricted bulk access, and exclusion from learner-facing docs and route graph.
- Privacy workflows for export/delete must be represented as explicit API operations with status tracking, not hidden one-off scripts.

### Speech Provider Strategy

- SpeakFit will not commit to MiniMax-only for MVP. The backend will define `STTProvider`, `TTSProvider`, and later optional `SpeechEvaluationProvider` abstractions with provider selected through environment/configuration.
- MVP may benchmark MiniMax, Deepgram, AssemblyAI, OpenAI, ElevenLabs, Azure Speech, Google Speech, or other providers. Default provider choice must be based on dogfood benchmark evidence, not brand familiarity.
- Benchmark criteria include Vietnamese-accented English accuracy, latency inside the daily mission loop, cost per completed mission, failure/timeout rate, manual fallback rate, provider data-retention terms, developer ergonomics, and debugging clarity.
- Frontend never calls speech providers directly. Hono backend broker/proxy owns API keys, rate limits, quotas, provider routing, audit logs, retries, timeouts, privacy disclosure, and cost attribution.
- Raw provider responses are normalized into SpeakFit transcript, TTS object, and feedback DTOs before reaching the frontend.
- Manual transcript/text fallback is first-class resilience and privacy/cost fallback, not an edge case.
- Custom STT/TTS model training and custom-hosted speech models are rejected for MVP.

### Frontend Architecture

- The frontend will be a React/Vite desktop-first PWA with a persistent SpeakFit shell.
- TanStack Start is not selected as the main application framework for MVP because SpeakFit needs explicit Hono API boundaries for backend learning, provider brokerage, OpenAPI contracts, and interview-defendable architecture. The frontend may use TanStack Router and TanStack Query for type-safe routing and server state while keeping Hono as the backend authority.
- Learner routes include onboarding, today, missions, phrases, progress, and settings. Operator is an internal gated route and must not appear as a normal learner flow.
- Production UI will use `shadcn/ui` primitives through project-owned SpeakFit wrappers under `src/components/speakfit/ui/`. The Canvas reference is visual guidance only and must not be imported or treated as production API.
- The UI must preserve Quiet Studio: compact sidebar, top navbar, focused workspace, cool-neutral surfaces, supportive coach tone, and no generic dashboard/chatbot/exam/gamification feel.
- The Today page remains the primary workspace and keeps the three-area layout: mission rail, central rehearsal stage, and coach panel.
- The mission loop maps to Warm-up, Shadow, Record, Feedback, Fallback, and Complete. Attempt API states drive UI progress and waiting states.
- Frontend organization will use feature folders for onboarding, today/practice, missions, phrases, progress, settings, and operator, plus shared SpeakFit UI wrappers.
- Server state should use TanStack Query or equivalent. Route state belongs in TanStack Router/React Router route/search state. Local component state handles transient UI. Persistent browser storage is limited to non-sensitive preferences.
- Audio recording logic must be isolated behind a dedicated hook/module for microphone permission, MediaRecorder support, duration limits, blob cleanup, and upload handoff.
- The PWA caches static shell assets only. Audio, transcripts, feedback, saved phrases, provider payloads, and sensitive learner data must not be cached in service worker or browser storage unless explicitly designed later.
- Accessibility requirements include keyboard support, visible focus, accessible recording status, clear loading/disabled states, and non-color-only feedback.
- Performance defaults include lazy loading heavy/internal pages, avoiding frontend provider SDKs, cleaning recording blobs, and deferring analytics/chart libraries until needed.

### Infrastructure & Deployment

- MVP infrastructure will use managed services rather than Kubernetes, self-hosted databases, or bespoke ops.
- Preferred first deployment is a simple split: React/Vite PWA on Cloudflare Pages or Vercel, Bun/Hono API on Railway, managed Postgres through Railway Postgres or Neon, and audio/object storage in Cloudflare R2.
- If deployment simplicity is more important for the first implementation story, frontend and API may deploy together on Railway first, then split the static frontend later.
- Cloudflare Workers is not selected as the primary API runtime for MVP because SpeakFit needs an explicit Bun/Hono backend service, longer provider-call control, normal background processing options, and interview-defendable backend boundaries. Cloudflare remains preferred for R2 and possible frontend/static hosting.
- Database hosting will start with Railway Postgres for co-location simplicity or Neon for managed Postgres branching/scale-to-zero. Supabase may be considered only as Postgres hosting, not as the primary auth/storage abstraction. Self-hosted Postgres is rejected for MVP.
- GitHub Actions will run CI with Bun using `oven-sh/setup-bun@v2`: install, lint, typecheck, test, build, OpenAPI generation check, and Drizzle migration checks before deployment.
- Environments will include local, preview/staging, and production. Each environment must use separate database, R2 bucket or prefix, auth secrets, provider keys, allowed origins, cookie config, and quotas.
- Configuration will use typed environment validation at app startup. Production uses platform-managed secrets only; committed `.env` files are forbidden except `.env.example`.
- Drizzle migrations are committed and run through an explicit deployment step. Destructive migrations require backup/snapshot discipline once real learner data exists.
- Observability starts with structured redacted logs plus Sentry for frontend and backend errors/tracing where supported. Logs track request IDs, attempt IDs, provider call IDs, latency, error codes, and cost units while redacting audio, transcripts, prompts, signed URLs, and secrets.
- Scaling will be simple first: one API service, managed Postgres, R2, and optional worker process when async queue/job needs appear. Redis, BullMQ, Kubernetes, multi-region deployment, and complex CDN routing are deferred until validated need.
- Backup and retention policies must cover managed Postgres backups, R2 lifecycle rules for temporary audio, provider retention disclosure, deletion/export job status, and no indefinite raw-audio retention by default.

### Decision Impact Analysis

**Implementation Sequence:**
1. Initialize Bun/Hono/React monorepo and verify scaffold boundaries.
2. Add Tailwind, `shadcn/ui`, SpeakFit wrapper components, TanStack Router, TanStack Query, and PWA shell behavior.
3. Add Hono API route/service/repository/provider/storage boundaries with Zod/OpenAPI.
4. Add Drizzle schema/migrations for auth, missions, attempts, recordings, feedback, phrases, progress, usage, provider logs, and operator audit.
5. Add library-backed auth, opaque cookie sessions, learner/operator RBAC, CSRF/CORS/security headers, and rate limits.
6. Add R2 storage abstraction and signed upload/download lifecycle.
7. Add attempt lifecycle state machine, idempotency, async job/status abstraction, polling, and provider broker interfaces.
8. Add initial STT/TTS/LLM provider adapters and dogfood benchmark logging.
9. Add frontend Today practice workspace wired to attempt states, feedback/fallback/retry, saved phrases, and trust-layer settings.
10. Add GitHub Actions CI, typed env validation, structured logs, Sentry, deployment environments, and migration checks.

**Cross-Component Dependencies:**
- Auth/session decisions drive API middleware, frontend route guards, operator gating, audit logging, and privacy access controls.
- Data schema decisions drive API DTOs, OpenAPI schemas, provider call logs, usage quotas, deletion/export, and progress views.
- Attempt state machine drives frontend waiting states, polling, fallback, retries, and backend async processing.
- Provider abstraction drives cost tracking, observability, privacy disclosure, and fallback behavior.
- R2 signed URL lifecycle depends on auth, recording metadata, ownership checks, upload confirmation, cleanup jobs, and deletion/export workflows.
- Frontend Quiet Studio architecture depends on API state taxonomy and must not invent separate mission/attempt states.
- Infrastructure decisions constrain secrets, CORS/cookie settings, migrations, provider call timeouts, monitoring, and environment separation.

## Implementation Patterns & Consistency Rules

### Pattern Categories Defined

**Critical Conflict Points Identified:**

Step 5 identifies 52 areas where different AI coding agents could otherwise make incompatible choices across naming, folders, API formats, state handling, security boundaries, UI composition, privacy behavior, provider integration, testing, and release discipline.

The goal is not enterprise ceremony. The goal is agent consistency: every vertical slice should look like it belongs to the same product and same backend architecture.

### Party Mode Synthesis

Party Mode reviewed this step from architecture, security/privacy, UX, and skeptic perspectives. The consolidated takeaways are:

- Architecture needs one canonical request flow, not route-by-route invention.
- Zod/OpenAPI contracts must remain the API source of truth; Drizzle schemas stay persistence-only.
- Attempt lifecycle must be an enforced state machine, not ad hoc status updates.
- Provider broker, storage/privacy, auth/session, and UI wrapper boundaries are non-negotiable choke points.
- Security rules must be middleware and service patterns, not repeated manual checks in handlers.
- Quiet Studio UI must be protected through wrapper components, canonical routes, and fixed practice-loop states.
- Patterns must be concrete enough to stop agent drift, but avoid speculative layers that slow the MVP mission loop.

### Naming Patterns

**Database Naming Conventions:**

- PostgreSQL table names use lowercase plural `snake_case`: `users`, `learner_profiles`, `missions`, `attempts`, `recordings`, `saved_phrases`, `provider_call_logs`, `operator_audit_logs`.
- Database columns use `snake_case`: `user_id`, `attempt_id`, `created_at`, `updated_at`, `deleted_at`, `audio_retention_until`, `provider_request_id`, `consent_version`.
- TypeScript properties use `camelCase` even when mapped to `snake_case` database columns through Drizzle: `userId`, `attemptId`, `createdAt`, `audioRetentionUntil`.
- Foreign keys use `<resource>_id` in the database and `<resource>Id` in TypeScript and API DTOs.
- Index names use `idx_<table>_<columns>`. Unique constraints use `uq_<table>_<columns>`. Foreign-key constraints use `fk_<table>_<referenced_table>`.
- Soft-delete fields use `deleted_at` in the database and `deletedAt` in TypeScript. Do not invent `is_deleted`, `removedAt`, or `archived_at` for the same concept.
- State-machine enum values use stable lowercase `snake_case` strings, matching the API contract: `created`, `upload_pending`, `processing_stt`, `feedback_ready`, `needs_manual_fallback`, `failed_retryable`, `failed_final`, `expired`, `cancelled`.

**API Naming Conventions:**

- API routes are versioned under `/v1` from the first implementation story.
- REST resources use lowercase plural path segments: `/v1/missions`, `/v1/attempts`, `/v1/recordings`, `/v1/phrases`, `/v1/progress`, `/v1/operator/audit-logs`.
- Path parameters use Hono `:camelCaseId` style: `/v1/missions/:missionId`, `/v1/attempts/:attemptId`, `/v1/recordings/:recordingId`.
- JSON request, response, and query field names use `camelCase`: `missionId`, `attemptId`, `retryAfter`, `fieldErrors`, `audioRetentionUntil`.
- Machine-readable codes use lowercase `snake_case`: `invalid_state_transition`, `idempotency_conflict`, `provider_timeout`, `audio_upload_expired`.
- Custom request headers use standard title case: `Idempotency-Key`, `X-Request-Id`.
- Command-like behavior must be modeled as resource creation or state-machine events. Prefer `POST /v1/attempts/:attemptId/events` over RPC-style endpoints such as `/v1/analyzeAttempt`, `/v1/submitAndScore`, or `/v1/generateFeedbackForUser`.

**Code Naming Conventions:**

- React components use `PascalCase`: `TodayWorkspace`, `MissionRail`, `RehearsalStage`, `CoachPanel`, `SpeakFitCard`.
- React hooks use `useCamelCase`: `useAudioRecorder`, `useAttemptPolling`, `useSessionUser`.
- Backend services, repositories, brokers, and providers use `PascalCase` type/class names and explicit suffixes: `AttemptService`, `AttemptRepository`, `SpeechProviderBroker`, `SttProvider`, `TtsProvider`, `R2StorageService`.
- Feature and module files use lowercase kebab-case with role suffixes where useful: `attempt.service.ts`, `attempt.repository.ts`, `attempt.schemas.ts`, `speech-provider-broker.ts`, `use-audio-recorder.ts`.
- DTO names describe direction and purpose: `CreateAttemptRequest`, `AttemptResponse`, `SubmitAttemptEventRequest`, `ProviderCallLogResponse`.
- Avoid duplicate terms for the same domain concept. Use `attempt`, not a mix of `submission`, `session`, `practiceRun`, and `try`.

### Structure Patterns

**Project Organization:**

The preferred monorepo shape is:

- `apps/web/` for React/Vite PWA.
- `apps/api/` for Bun/Hono API.
- `packages/shared/` only for stable shared contracts/utilities that are safe for both frontend and backend.

If the selected starter uses different names, the first scaffold story must document the equivalent path mapping before additional feature agents work in the repo.

**Backend Slice Pattern:**

All new backend resource features should follow the canonical slice once created:

- `apps/api/src/routes/v1/<resource>.ts` for HTTP route wiring.
- `apps/api/src/schemas/<resource>.schemas.ts` for Zod request/response schemas.
- `apps/api/src/services/<resource>.service.ts` for business rules.
- `apps/api/src/db/schema.ts` for Drizzle table definitions.
- `apps/api/src/db/queries/<resource>.queries.ts` or `apps/api/src/repositories/<resource>.repository.ts` for database access.
- `apps/api/src/providers/` for provider interfaces and implementations.
- `apps/api/src/storage/` for private object storage abstractions.
- `apps/api/src/jobs/` for async job/status orchestration.
- `apps/api/src/errors/` for domain error types and error translation.
- `apps/api/src/observability/` for request IDs, structured logs, redaction, and tracing helpers.

Canonical backend request flow:

`Route -> Request ID -> CORS -> Session -> CSRF for mutation -> RBAC/resource ownership -> Zod validation -> Service -> Repository/Provider/Storage -> DTO mapper -> OpenAPI response`

Routes must stay thin. Routes validate input, call services, and return typed responses. Business rules, direct SQL, provider calls, retention decisions, and state transitions must not live in route handlers.

**Frontend Slice Pattern:**

Frontend code should organize by product feature and shared platform layer:

- `apps/web/src/routes/` for TanStack Router route definitions.
- `apps/web/src/features/onboarding/`
- `apps/web/src/features/today/`
- `apps/web/src/features/missions/`
- `apps/web/src/features/phrases/`
- `apps/web/src/features/progress/`
- `apps/web/src/features/settings/`
- `apps/web/src/features/operator/`
- `apps/web/src/components/speakfit/ui/` for SpeakFit-owned UI wrappers around `shadcn/ui`.
- `apps/web/src/lib/api/` for the project-owned API client wrapper.
- `apps/web/src/lib/query/` for TanStack Query keys, shared query options, and mutation helpers.
- `apps/web/src/hooks/` for cross-feature browser hooks such as audio recording.

Page code composes feature components and SpeakFit wrappers. It must not become the place where API calls, raw provider payloads, ad hoc UI variants, and business rules accumulate.

**Shared Package Boundary:**

- Shared package code may contain generated API types, DTO helpers, enum constants, and pure utilities that are safe in browser and server.
- Shared package code must not import Drizzle database schemas, provider SDKs, server secrets, Hono app internals, or Better Auth server internals.
- Hono RPC typing is allowed only inside the project-owned frontend API client wrapper. UI components, pages, and query hooks must not import Hono server internals directly.

**Testing Structure:**

- Unit tests may be co-located with modules as `*.test.ts` or placed in a nearby `__tests__/` folder when that improves readability.
- API route/service integration tests should cover auth, RBAC, Zod validation, state transitions, idempotency, provider mocks, and storage edge cases.
- UI tests should focus on practice-loop states, audio permission states, fallback behavior, saved phrase actions, and critical accessibility paths.
- E2E tests can be added after the first stable vertical slice; they should prioritize onboarding into Today, recording/fallback, feedback, retry, phrase save, and privacy settings.

### Format Patterns

**API Response Formats:**

- Successful JSON responses use a consistent envelope: `{ data, meta? }`.
- List responses use `{ data: [...], meta: { nextCursor?, hasMore?, total? } }`. Use cursor pagination for growing lists; avoid unbounded responses.
- Long-running operations return `202 Accepted` with `{ data: { attemptId, jobId?, status, statusUrl? }, meta? }` and may include `Retry-After`.
- Error responses use `{ error: { code, message, requestId, details?, fieldErrors?, retryable?, retryAfter?, hint? } }`.
- Client-visible `message` values must be safe and supportive. They must not include stack traces, SQL details, raw provider errors, signed URLs, secrets, raw transcripts, raw prompts, raw manual text, or raw audio references.
- Validation errors use `422` with `fieldErrors` where possible. Bad JSON, unsupported content types, or malformed requests use `400`.

**HTTP Status Code Usage:**

- `200 OK` for successful reads and non-created mutations.
- `201 Created` for resource creation.
- `202 Accepted` for accepted async work.
- `204 No Content` only when no body is useful.
- `400 Bad Request` for malformed request shape.
- `401 Unauthorized` for missing/invalid session.
- `403 Forbidden` for authenticated users without permission.
- `404 Not Found` for absent resources or ownership-hidden resources.
- `409 Conflict` for idempotency conflicts, invalid state transitions, and write conflicts.
- `422 Unprocessable Entity` for Zod/domain validation failures.
- `429 Too Many Requests` for rate limits and quotas.
- `500`, `502`, `503`, and `504` for server/provider/runtime failures after normalization.

**Data Exchange Formats:**

- API JSON fields use `camelCase`.
- Database identifiers use `snake_case`.
- Dates and times in APIs use ISO 8601 UTC strings.
- Booleans use JSON booleans, not `0`/`1` or string values.
- Optional fields are omitted when not applicable. Use `null` only when the field is known and intentionally empty.
- Currency/cost/usage units must include explicit unit fields where ambiguity exists: `audioSeconds`, `ttsCharacters`, `feedbackCalls`, `costMicros`.
- Provider raw payloads must be normalized before reaching client DTOs.

**OpenAPI and Schema Source of Truth:**

- Zod request and response schemas are the public API source of truth.
- OpenAPI must be generated from, or mechanically synchronized with, the Zod contract in the same change.
- Frontend DTOs must be generated from, imported from, or mechanically derived from the API contract. Agents must not hand-write duplicate frontend response types that can drift from backend schemas.
- Drizzle schemas are persistence models only. Do not expose Drizzle table schemas directly as public API responses.
- Any `/v1` route without Zod request/response schemas and OpenAPI coverage is incomplete.

### Communication Patterns

**Attempt State Machine Pattern:**

Attempt status must change only through the attempt state-machine transition function or module.

Direct SQL updates to attempt status are forbidden outside that state-machine boundary. Each transition must define:

- source state,
- target state,
- triggering event,
- allowed actor: `learner`, `system`, `provider`, or `operator`,
- idempotency behavior,
- side effects such as storage write, provider job creation, transcript creation, feedback creation, quota update, or audit log,
- retry behavior,
- failure behavior.

Invalid transitions must fail with `409 invalid_state_transition` or a more specific stable domain error. They must not partially write side effects.

**Event Naming and Payloads:**

- Domain event names use lowercase `snake_case`: `recording_uploaded`, `stt_started`, `stt_completed`, `feedback_started`, `feedback_completed`, `manual_fallback_submitted`, `attempt_cancelled`.
- Event payloads use API `camelCase` fields and must include enough identity for observability: `attemptId`, `recordingId?`, `jobId?`, `requestId?`, `occurredAt`.
- Client-submitted events must include an `Idempotency-Key` for repeatable mutations.
- Actor identity is derived from session/backend context, not trusted from client payloads.

**Frontend State Management:**

- TanStack Router owns routes and URL/search state.
- TanStack Query owns server state, caching, invalidation, mutation state, retry, and polling.
- Local React state is for ephemeral UI only: expanded panels, temporary input, local recorder state before upload, and transient visual controls.
- Persistent browser storage is limited to non-sensitive preferences. Do not store sessions, provider keys, audio, transcripts, feedback, saved phrases, prompts, signed URLs, or manual text in `localStorage`, IndexedDB, or service-worker caches.
- Pages must not call `fetch` directly for app API data. Use the shared API client and query/mutation hooks.
- Query keys should be predictable arrays scoped by resource and identity, such as `['missions']`, `['attempt', attemptId]`, `['phrases', filters]`, `['progress', userIdOrScope]`.

**Structured Logging:**

- Logs use structured fields such as `requestId`, `userIdHash`, `route`, `operation`, `attemptId`, `recordingId`, `jobId`, `providerCallId`, `provider`, `model`, `latencyMs`, `status`, `errorCode`, and `costUnits`.
- Logs must redact secrets, cookies, session tokens, OTPs, provider keys, signed URLs, raw transcripts, raw prompts, manual text, raw audio references, and full provider payloads.
- Operator and privacy actions require audit logging, but audit records must avoid raw sensitive content unless explicitly justified.

### Process Patterns

**Auth, Session, CSRF, and RBAC:**

- Better Auth with opaque server-side cookie sessions is the MVP auth mechanism unless architecture is explicitly changed.
- Frontend code must use cookie-based session flow. Do not add localStorage JWTs, custom bearer-token auth, or parallel session systems.
- Protected backend routes must use shared auth middleware. Route-local session parsing is forbidden except inside the auth middleware itself.
- Mutating cookie-authenticated requests require CSRF protection and strict Origin/Referer validation where applicable.
- Learner queries must scope by the authenticated user. Never trust client-submitted `userId` for resource ownership.
- Operator routes live in a separate namespace, require backend RBAC, deny by default, and write audit logs for sensitive actions.

**Provider Broker Boundary:**

All AI, speech, transcription, TTS, scoring, and feedback-provider calls must go through the backend provider broker.

Application code must not import provider SDKs directly outside the broker module/package. The broker owns:

- provider selection,
- retries and fallback,
- timeout and cost limits,
- rate/usage attribution,
- request/response logging policy,
- privacy redaction,
- normalized safe errors,
- local/dev/test doubles.

If a feature needs provider behavior not supported by the broker, extend the broker first. Do not bypass it.

**Storage and Privacy Boundary:**

- User audio, transcripts, feedback artifacts, manual text, saved phrases, prompts, provider payloads, and exports are private data.
- R2 buckets must remain private.
- Access must use short-lived backend-issued signed URLs scoped to authenticated user, action, object, and TTL.
- Signed URL TTL must be explicit at the call site or through a storage wrapper default.
- Public URLs are forbidden for user-generated audio/transcript artifacts.
- Delete/export flows must use shared privacy service functions, not ad hoc storage deletes.
- Deletion must cover database records, private object storage, derived transcripts/feedback, and pending access URLs where practical.
- Export shape and deletion semantics must be defined for each sensitive data class before the feature is considered complete.

**Error Handling Patterns:**

- Backend services should throw or return typed domain errors with `code`, HTTP status, retryability, and safe hint metadata.
- Routes use a centralized error translator to produce the shared error envelope.
- Provider errors are normalized before returning to the frontend.
- Frontend error UI should distinguish user-actionable errors, retryable provider/network failures, auth/session failures, and final failures.
- Today practice errors must offer recovery: retry, use manual text fallback, return to mission, or contact/export/delete where appropriate.

**Loading and Async State Patterns:**

- Async attempt operations use standard job/status behavior and TanStack Query polling with bounded intervals, backoff, max duration, and `Retry-After` support where useful.
- Loading UI must preserve the Quiet Studio layout. Do not collapse Today into a generic full-screen spinner while mission rail, rehearsal stage, or coach panel context is needed.
- Required state templates include first-run mission, no saved phrases, no progress yet, audio permission denied, network slow, provider unavailable, analysis failed, upload expired, and manual text fallback.
- Every empty/error/loading state must provide a clear next action within one click where possible.

**UI/UX Implementation Patterns:**

- Learner-facing UI must preserve the SpeakFit Quiet Studio mental model: a calm desktop-first practice workspace, not a generic dashboard, chatbot, exam tool, or gamified course app.
- Production UI must use project-owned SpeakFit wrappers around `shadcn/ui` primitives from `apps/web/src/components/speakfit/ui/` or the scaffold-equivalent path.
- Page code should not import raw `shadcn/ui` primitives directly unless creating or extending those wrappers.
- Allowed learner page concepts are `Onboarding`, `Today`, `Missions`, `Phrases`, `Progress`, and `Settings`. `Operator` is internal and gated. Do not introduce `Dashboard`, `Chat`, `Courses`, `Scores`, leaderboards, coins, shops, IELTS bands, or report-card flows unless the PRD changes.
- The `Today` route is the core experience and must keep the three-area workspace: mission rail, central rehearsal stage, and coach panel.
- The mission loop must map backend attempt states to UI states: `warmup`, `shadowing`, `recording`, `analyzing`, `feedback`, `fallback`, `complete`, and `error`.
- Each UI state must define visible status, primary CTA, disabled controls, coach-panel behavior, and recovery path.
- Feedback UI always follows: one strength, one fix, one better phrase, and one retry action.
- Audio recording UI must expose state through label, icon, timer/status, and keyboard-accessible controls. Never rely on color alone.
- Saved phrase UI must preserve original context and provide review/reuse actions.
- Progress UI remains lightweight: missions completed, attempts, retries, reused phrases, confidence 1-5, and before/after evidence.

**MVP Abstraction Rule:**

Do not add speculative layers. Add abstractions only when:

- the same pattern appears in at least two real features, or
- the boundary is one of: auth/session, provider broker, storage/privacy, attempt state machine, API contract, observability, or SpeakFit UI wrappers.

Prefer thin vertical slices that complete the learner-visible mission loop over generic frameworks, plugin systems, or future-proofing.

### Enforcement Guidelines

**All AI Agents MUST:**

- Read the architecture document, PRD, project context, and UI implementation contract before implementation work.
- Follow the canonical request flow and feature slice structure for new backend code.
- Add or update Zod request/response schemas for every `/v1` endpoint.
- Keep OpenAPI synchronized with the Zod API contract.
- Avoid exposing Drizzle persistence models as public DTOs.
- Use shared auth middleware for protected routes and shared RBAC/resource ownership checks.
- Change attempt status only through the attempt state-machine boundary.
- Route all provider calls through the provider broker.
- Route private object storage through the storage/privacy service boundary.
- Use SpeakFit UI wrappers for repeated primitives and Quiet Studio layout patterns.
- Keep sensitive data out of browser storage, service-worker caches, logs, errors, and analytics.
- Write tests for route validation, RBAC/resource ownership, state transitions, idempotency, provider mocks, and critical UI states where relevant.
- Document any intentional deviation in the work order, decision log, or ADR before coding the deviation.

**Pattern Enforcement:**

- CI should run install, lint, typecheck, tests, build, OpenAPI generation/check, and Drizzle migration checks.
- Code review should reject endpoint-local error formats, direct provider calls, direct route SQL, direct attempt status updates, public storage assumptions, raw `shadcn/ui` page sprawl, sensitive browser persistence, and unredacted logs.
- New canonical examples must be documented when the first implementation story creates the initial path shape.
- Pattern changes require updating this architecture section or a new ADR if they affect multiple agents or future stories.

### Pattern Examples

**Good Examples:**

- `POST /v1/attempts` creates an attempt using `CreateAttemptRequest`, returns `AttemptResponse`, writes through `AttemptService`, and documents OpenAPI from Zod schemas.
- `POST /v1/attempts/:attemptId/events` records `recording_uploaded` with `Idempotency-Key`; `AttemptService` validates the transition and starts provider work through the broker.
- `AttemptService` calls `AttemptRepository` for persistence and `SpeechProviderBroker` for transcription. The route does not import Drizzle tables or provider SDKs.
- The frontend `Today` page calls `useAttempt(attemptId)` and `useSubmitAttemptEvent()` hooks, not raw `fetch`.
- `CoachPanel` renders one strength, one fix, one better phrase, and one retry action using SpeakFit wrapper components.
- Audio download uses a short-lived signed URL created after backend ownership checks; the signed URL is never logged or persisted in browser storage.

**Anti-Patterns:**

- Creating `/v1/analyzeAttempt` that calls a provider directly from the route handler.
- Returning raw Drizzle rows as API responses.
- Updating `attempts.status` through direct SQL outside the state-machine function.
- Hand-writing frontend DTOs that duplicate backend response types.
- Importing OpenAI, MiniMax, Deepgram, or other provider SDKs outside the broker.
- Storing JWTs, transcripts, audio blobs, feedback, prompts, manual text, or signed URLs in `localStorage`, IndexedDB, or service-worker caches.
- Building pages from arbitrary raw `shadcn/ui` primitives and one-off Tailwind variants instead of SpeakFit wrappers.
- Adding a generic dashboard, chatbot-first prompt page, leaderboard, coins, IELTS band score, or heavy analytics report without PRD change.
- Logging raw transcripts, full provider payloads, signed URLs, cookies, OTPs, or provider keys.

## Project Structure & Boundaries

### Complete Project Directory Structure

```text
speakfit-english/
├── README.md
├── package.json
├── bun.lock
├── tsconfig.base.json
├── turbo.json
├── biome.json
├── .env.example
├── .gitignore
├── docker-compose.yml
├── drizzle.config.ts
├── .github/
│   └── workflows/
│       └── ci.yml
├── docs/
│   ├── decisions.md
│   ├── raid.md
│   ├── adr/
│   ├── work-orders/
│   ├── templates/
│   └── ui-ux/
├── _bmad-output/
│   └── planning-artifacts/
│       ├── architecture.md
│       ├── prd.md
│       ├── product-brief.md
│       └── ux-design-specification.md
├── apps/
│   ├── web/
│   │   ├── package.json
│   │   ├── index.html
│   │   ├── vite.config.ts
│   │   ├── tsconfig.json
│   │   ├── tailwind.config.ts
│   │   ├── postcss.config.js
│   │   ├── components.json
│   │   ├── public/
│   │   │   ├── manifest.webmanifest
│   │   │   └── icons/
│   │   └── src/
│   │       ├── main.tsx
│   │       ├── app.tsx
│   │       ├── styles/
│   │       │   └── globals.css
│   │       ├── routes/
│   │       │   ├── __root.tsx
│   │       │   ├── index.tsx
│   │       │   ├── onboarding.tsx
│   │       │   ├── today.tsx
│   │       │   ├── missions.tsx
│   │       │   ├── phrases.tsx
│   │       │   ├── progress.tsx
│   │       │   ├── settings.tsx
│   │       │   └── operator.tsx
│   │       ├── components/
│   │       │   └── speakfit/
│   │       │       ├── shell/
│   │       │       └── ui/
│   │       ├── features/
│   │       │   ├── onboarding/
│   │       │   ├── today/
│   │       │   │   ├── components/
│   │       │   │   │   ├── mission-rail.tsx
│   │       │   │   │   ├── rehearsal-stage.tsx
│   │       │   │   │   └── coach-panel.tsx
│   │       │   │   ├── hooks/
│   │       │   │   └── today-workspace.tsx
│   │       │   ├── missions/
│   │       │   ├── phrases/
│   │       │   ├── progress/
│   │       │   ├── settings/
│   │       │   └── operator/
│   │       ├── hooks/
│   │       │   └── use-audio-recorder.ts
│   │       ├── lib/
│   │       │   ├── api/
│   │       │   │   ├── api-client.ts
│   │       │   │   └── api-errors.ts
│   │       │   ├── query/
│   │       │   │   ├── query-client.ts
│   │       │   │   └── query-keys.ts
│   │       │   └── env.ts
│   │       └── test/
│   │           ├── setup.ts
│   │           └── fixtures/
│   └── api/
│       ├── package.json
│       ├── tsconfig.json
│       ├── src/
│       │   ├── index.ts
│       │   ├── app.ts
│       │   ├── config/
│       │   │   └── env.ts
│       │   ├── routes/
│       │   │   ├── health.ts
│       │   │   └── v1/
│       │   │       ├── auth.ts
│       │   │       ├── me.ts
│       │   │       ├── missions.ts
│       │   │       ├── attempts.ts
│       │   │       ├── recordings.ts
│       │   │       ├── phrases.ts
│       │   │       ├── progress.ts
│       │   │       ├── privacy.ts
│       │   │       └── operator.ts
│       │   ├── middleware/
│       │   │   ├── request-id.ts
│       │   │   ├── cors.ts
│       │   │   ├── auth.ts
│       │   │   ├── csrf.ts
│       │   │   ├── rbac.ts
│       │   │   ├── rate-limit.ts
│       │   │   └── secure-headers.ts
│       │   ├── schemas/
│       │   │   ├── common.schemas.ts
│       │   │   ├── auth.schemas.ts
│       │   │   ├── mission.schemas.ts
│       │   │   ├── attempt.schemas.ts
│       │   │   ├── recording.schemas.ts
│       │   │   ├── phrase.schemas.ts
│       │   │   ├── progress.schemas.ts
│       │   │   ├── privacy.schemas.ts
│       │   │   └── operator.schemas.ts
│       │   ├── services/
│       │   │   ├── auth.service.ts
│       │   │   ├── profile.service.ts
│       │   │   ├── mission.service.ts
│       │   │   ├── attempt.service.ts
│       │   │   ├── recording.service.ts
│       │   │   ├── feedback.service.ts
│       │   │   ├── phrase.service.ts
│       │   │   ├── progress.service.ts
│       │   │   ├── usage.service.ts
│       │   │   ├── privacy.service.ts
│       │   │   └── operator.service.ts
│       │   ├── repositories/
│       │   │   ├── user.repository.ts
│       │   │   ├── profile.repository.ts
│       │   │   ├── mission.repository.ts
│       │   │   ├── attempt.repository.ts
│       │   │   ├── recording.repository.ts
│       │   │   ├── feedback.repository.ts
│       │   │   ├── phrase.repository.ts
│       │   │   ├── progress.repository.ts
│       │   │   ├── usage.repository.ts
│       │   │   ├── provider-call-log.repository.ts
│       │   │   └── operator-audit-log.repository.ts
│       │   ├── db/
│       │   │   ├── client.ts
│       │   │   ├── schema.ts
│       │   │   └── migrations/
│       │   ├── auth/
│       │   │   ├── better-auth.ts
│       │   │   └── session.ts
│       │   ├── attempts/
│       │   │   ├── attempt-state-machine.ts
│       │   │   └── attempt-events.ts
│       │   ├── providers/
│       │   │   ├── speech-provider-broker.ts
│       │   │   ├── stt-provider.ts
│       │   │   ├── tts-provider.ts
│       │   │   ├── llm-feedback-provider.ts
│       │   │   └── adapters/
│       │   ├── storage/
│       │   │   ├── object-storage.ts
│       │   │   ├── r2-storage.ts
│       │   │   └── signed-url-policy.ts
│       │   ├── jobs/
│       │   │   ├── job-status.ts
│       │   │   ├── attempt-jobs.ts
│       │   │   └── worker.ts
│       │   ├── errors/
│       │   │   ├── domain-error.ts
│       │   │   └── error-envelope.ts
│       │   ├── observability/
│       │   │   ├── logger.ts
│       │   │   ├── redaction.ts
│       │   │   └── sentry.ts
│       │   └── openapi/
│       │       ├── registry.ts
│       │       └── generate.ts
│       └── test/
│           ├── setup.ts
│           ├── fixtures/
│           ├── routes/
│           ├── services/
│           └── repositories/
└── packages/
    └── shared/
        ├── package.json
        ├── tsconfig.json
        └── src/
            ├── api-contracts/
            ├── constants/
            ├── attempt-status.ts
            └── index.ts
```

### Architectural Boundaries

**API Boundaries:**

- Public backend contract lives under `apps/api/src/routes/v1/`.
- `health.ts` is infrastructure-only.
- OpenAPI generated from Zod schemas is official API contract.
- Frontend calls only `apps/web/src/lib/api/api-client.ts` and query hooks.
- Hono RPC may exist only inside API client wrapper, never page/component code.
- Operator API lives under `routes/v1/operator.ts`, with RBAC + audit.

**Component Boundaries:**

- App shell lives in `components/speakfit/shell/`.
- Reusable UI primitives live in `components/speakfit/ui/`.
- Product screens live in `features/<area>/`.
- `Today` owns mission rail, rehearsal stage, coach panel.
- Feature components do not import provider SDKs, DB, Hono app internals, or server auth internals.

**Service Boundaries:**

- Routes wire HTTP only.
- Services own business rules.
- Repositories own persistence.
- Provider broker owns AI/STT/TTS/feedback vendors.
- Storage services own R2 and signed URL policy.
- Privacy service owns export/delete.
- Attempt state machine owns attempt status transitions.

**Data Boundaries:**

- Drizzle schema is persistence model.
- Zod schemas are API DTO source of truth.
- `packages/shared` contains safe constants/types only.
- No secrets or server-only provider types in shared/browser code.
- Sensitive learner data never stored in frontend persistent storage.

### Requirements to Structure Mapping

**Feature Mapping:**

- FR1-FR6 Account/Profile → `routes/v1/auth.ts`, `routes/v1/me.ts`, `auth/`, `profile.service.ts`, `profile.repository.ts`, `features/settings/`, `features/onboarding/`.
- FR7-FR10 Onboarding → `features/onboarding/`, `onboarding.tsx`, `profile.service.ts`, `mission.service.ts`.
- FR11-FR16 Daily Mission → `features/today/`, `features/missions/`, `mission.service.ts`, `attempt.service.ts`, `operator.service.ts`.
- FR17-FR20 Listening/Shadowing → `providers/tts-provider.ts`, `speech-provider-broker.ts`, `features/today/`, `recording.schemas.ts`.
- FR21-FR25 Recording/Fallback → `use-audio-recorder.ts`, `recording.service.ts`, `storage/`, `attempt-state-machine.ts`, `features/today/`.
- FR26-FR30 Feedback/Retry → `feedback.service.ts`, `llm-feedback-provider.ts`, `attempt-events.ts`, `coach-panel.tsx`.
- FR31-FR36 Saved Phrases → `phrase.service.ts`, `phrase.repository.ts`, `features/phrases/`.
- FR37-FR43 Progress/Validation → `progress.service.ts`, `usage.service.ts`, `features/progress/`, `features/operator/`.
- FR44-FR48 Failure Recovery → `errors/`, `jobs/`, `features/today/`, `api-errors.ts`.
- FR49-FR53 Privacy/Consent → `privacy.service.ts`, `routes/v1/privacy.ts`, `features/settings/`.
- FR54-FR56 Usage/Cost → `usage.service.ts`, `provider-call-log.repository.ts`, `operator.service.ts`.
- FR57-FR60 Private Testing Ops → `features/operator/`, `routes/v1/operator.ts`, `operator.service.ts`, `operator-audit-log.repository.ts`.

**Cross-Cutting Concerns:**

- Auth/session → `auth/`, `middleware/auth.ts`, `middleware/csrf.ts`, `middleware/rbac.ts`.
- API validation/OpenAPI → `schemas/`, `openapi/`.
- Observability/redaction → `observability/`.
- Provider resilience → `providers/`, `jobs/`, `errors/`.
- Privacy deletion/export → `privacy.service.ts`, `storage/`, repositories.
- UI consistency → `components/speakfit/ui/`, `components/speakfit/shell/`.
- BE Learning Mode artifacts → `docs/templates/amelia-be-deep-dive.md`, work orders, ADRs.

### Integration Points

**Internal Communication:**

- Web route → feature component → query/mutation hook → API client → `/v1` route.
- API route → middleware chain → Zod validation → service → repository/provider/storage/job.
- Attempt events → state machine → side effects → job/status → frontend polling.
- Provider result → broker normalization → feedback/transcript DTO → service persistence → frontend query refresh.

**External Integrations:**

- Better Auth for auth/session.
- Managed Postgres via Drizzle.
- Cloudflare R2 via storage abstraction.
- STT/TTS/LLM providers via provider broker only.
- Sentry via observability layer.
- GitHub Actions via `.github/workflows/ci.yml`.

**Data Flow:**

1. User signs in via cookie session.
2. Frontend loads profile/current mission via API client.
3. User records or submits manual text.
4. API creates/updates attempt and recording metadata.
5. Storage creates signed upload/read URLs after ownership checks.
6. Attempt job runs STT/feedback through provider broker.
7. State machine advances attempt status.
8. Frontend polls attempt/job state.
9. Feedback arrives in coach panel.
10. User retries, saves phrase, completes mission.
11. Progress, usage, provider logs, and audit logs update.
12. Settings privacy flows export/delete data through privacy service.

### File Organization Patterns

**Configuration Files:**

- Root owns workspace config: `package.json`, `bun.lock`, `tsconfig.base.json`, `turbo.json`, `biome.json`.
- API owns server config: `apps/api/src/config/env.ts`.
- Web owns browser env validation: `apps/web/src/lib/env.ts`.
- `.env.example` documents all required vars. Real `.env` files stay uncommitted.
- `docker-compose.yml` starts local Postgres and optional local dependencies.

**Source Organization:**

- Use feature folders on web.
- Use route/service/repository/provider/storage boundaries on API.
- Put cross-runtime safe contracts in `packages/shared`.
- Do not create generic `utils/` dumping grounds. Prefer domain-owned helpers.

**Test Organization:**

- API tests live under `apps/api/test/`.
- Web tests live under `apps/web/src/**/__tests__/` or `apps/web/src/test/` for shared setup.
- Integration tests cover auth, RBAC, attempt state transitions, idempotency, provider mocks, storage signed URLs, privacy deletion/export.
- UI tests cover Today loop states, mic permission/fallback, coach feedback, saved phrase actions.

**Asset Organization:**

- Static app assets live in `apps/web/public/`.
- UI icons/illustrations used by components live near web source if imported.
- User audio never lives in repo/public assets. It lives in private R2 only.
- Generated exports are temporary private storage artifacts, not static files.

### Development Workflow Integration

**Development Server Structure:**

- `bun run dev` should start web and API together where possible.
- `bun run dev:web` starts `apps/web`.
- `bun run dev:api` starts `apps/api`.
- `docker-compose up` starts local Postgres.
- API startup validates env before serving requests.

**Build Process Structure:**

- `bun run lint` checks workspace.
- `bun run typecheck` checks all apps/packages.
- `bun run test` runs API/web tests.
- `bun run build` builds web/API.
- `bun run openapi:check` verifies OpenAPI generation.
- `bun run db:generate` and `bun run db:migrate` manage Drizzle migrations.

**Deployment Structure:**

- Web can deploy to Cloudflare Pages/Vercel from `apps/web`.
- API can deploy to Railway from `apps/api`.
- Postgres is managed Railway/Neon.
- R2 buckets/prefixes differ by environment.
- Preview/production each need separate DB, R2 scope, auth secret, provider keys, allowed origins, cookie config, and quotas.

## Architecture Validation Results

### Coherence Validation

**Decision Compatibility:**

- Stack is coherent: Bun/Hono API, React/Vite PWA, Postgres/Drizzle, R2 storage, provider broker, and managed deployment work together without architectural conflict.
- Frontend choice is coherent with backend learning goal: TanStack Router and TanStack Query support the PWA without hiding backend architecture behind TanStack Start.
- Auth/security decisions are coherent: Better Auth-compatible opaque cookie sessions, middleware RBAC, CSRF, strict CORS, private storage, and redacted observability support the same trust model.
- Provider architecture is coherent: STT/TTS/LLM vendors sit behind broker interfaces; frontend never receives provider keys or raw provider options.
- Deployment decisions are coherent: managed API hosting, managed Postgres, R2, GitHub Actions, and Sentry fit the MVP scale and avoid premature ops complexity.

**Pattern Consistency:**

- Naming conventions align database `snake_case`, API and TypeScript `camelCase`, machine-readable error codes and states as lowercase `snake_case`, and React components as `PascalCase`.
- Implementation flow aligns routes, middleware, Zod schemas, services, repositories, providers, storage, job/status, and DTO mapping.
- Error envelope, structured logging, redaction, retry hints, and fallback behavior align across API, frontend, observability, and privacy requirements.
- Attempt state machine aligns Today UI states, async jobs, polling, manual fallback, retry, completion, and progress evidence.

**Structure Alignment:**

- Monorepo structure supports the selected split between `apps/web`, `apps/api`, and `packages/shared`.
- Web structure maps directly to learner pages, the internal Operator page, the Quiet Studio shell, SpeakFit UI wrappers, and the Today three-area workspace.
- API structure maps to Hono route/service/repository/provider/storage/job boundaries and avoids route-heavy business logic.
- Shared package boundary avoids leaking Drizzle schemas, provider SDKs, Hono internals, Better Auth internals, or secrets into browser code.
- CI/build/deploy structure supports the selected infrastructure and required checks.

### Requirements Coverage Validation

**Epic/Feature Coverage:**

The PRD does not yet provide an epics/stories breakdown, so validation uses FR categories and UX journeys. Each major product area maps to one or more concrete web/API modules in Step 6.

**Functional Requirements Coverage:**

- FR1-FR6 account/profile are supported by auth, profile, onboarding, settings, session middleware, and learner-owned data boundaries.
- FR7-FR10 onboarding/first session are supported by onboarding routes/features, profile service, mission selection, and Today entry flow.
- FR11-FR16 daily mission are supported by missions, Today workspace, attempt aggregate, operator seeding/verification, and mission route/service boundaries.
- FR17-FR20 listening/shadowing are supported by TTS/provider broker, mission content, Today rehearsal stage, and transcript/sample text patterns.
- FR21-FR25 recording/replay/manual fallback are supported by audio recorder hook, recording service, R2 storage, signed URLs, attempt state machine, and manual fallback states.
- FR26-FR30 feedback/retry are supported by feedback service, LLM provider adapter, coach panel pattern, attempt events, and retry transitions.
- FR31-FR36 saved phrases/review/reuse are supported by phrase route/service/repository and Phrases feature.
- FR37-FR43 progress/validation signals are supported by progress service, usage service, operator feature, provider call logs, and lightweight progress UI.
- FR44-FR48 failure recovery are supported by error envelopes, jobs, fallback states, provider broker normalization, and Today recovery UI.
- FR49-FR53 privacy/consent/data control are supported by privacy service, settings, provider notice, retention metadata, delete/export, and storage/privacy boundary.
- FR54-FR56 usage/cost control are supported by usage service, provider call logs, quotas/rate limits, and operator inspection.
- FR57-FR60 private testing ops are supported by Operator route/feature/service, mission management, validation signals, and audit logs.

**Non-Functional Requirements Coverage:**

- Performance is addressed through Vite PWA shell, static asset caching only, async provider jobs, polling, lightweight UI, and no frontend provider SDKs.
- Security and privacy are addressed through opaque cookie sessions, CSRF/CORS/RBAC, private R2, signed URLs, redaction, retention metadata, deletion/export, and provider broker boundaries.
- Reliability and resilience are addressed through manual fallback, retryable/final error taxonomy, provider broker timeouts/fallback, job/status abstraction, and attempt state machine.
- Accessibility is addressed through keyboard support, visible focus, labeled audio controls, non-color-only feedback, text alongside audio where feasible, and clear recovery copy.
- Scalability and cost control are addressed through managed services, usage/quota tracking, provider logs, cost units, deferred Redis/BullMQ, and dogfood-first scale assumptions.
- Integration requirements are addressed through REST `/v1`, Zod/OpenAPI, provider broker, R2 abstraction, Better Auth integration, and external provider isolation.
- Maintainability and portfolio evidence are addressed through ADRs, decisions, work orders, BE Learning Mode, explicit backend boundaries, and AI-agent consistency rules.

### Implementation Readiness Validation

**Decision Completeness:**

- Critical decisions are documented and tied to product constraints.
- Current package versions were recorded for key architecture choices where checked during Step 4.
- Deferred decisions are explicitly labeled and do not block MVP implementation.
- Provider default selection is intentionally benchmark-based rather than hardcoded before evidence.

**Structure Completeness:**

- Project tree is complete enough to guide the first scaffold and architecture-hardening stories.
- Web/API/shared boundaries are explicit.
- Route, service, repository, provider, storage, job, error, observability, and OpenAPI locations are defined.
- Requirements-to-structure mapping covers all FR categories.

**Pattern Completeness:**

- Naming, structure, format, communication, process, security/privacy, UI, loading/error, provider, storage, and state-machine patterns are defined.
- Good examples and anti-patterns identify what agents should and should not do.
- Enforcement guidance is strong enough for code review and future work orders.

### Gap Analysis Results

**Critical Gaps:**

- None currently blocking implementation.

**Important Gaps:**

- First scaffold story must confirm actual starter folder names against the planned `apps/web`, `apps/api`, and `packages/shared` structure, then document any path mapping.
- Better Auth integration must be implementation-vetted with Bun/Hono/Drizzle. If glue code becomes excessive, architecture should record fallback to Auth.js or another library-backed option.
- Exact provider defaults must be selected only after dogfood benchmark evidence.
- Exact retention durations, signed URL TTL defaults, and quota caps must be set before broader beta use.

**Nice-to-Have Gaps:**

- Add a Mermaid data-flow or sequence diagram after the first vertical slice exists.
- Add exact OpenAPI generation command after scaffold scripts are known.
- Add an E2E test matrix after first stable practice loop implementation.
- Add ADRs for final scaffold, auth library fallback outcome, and provider defaults once implementation evidence exists.

### Validation Issues Addressed

- Duplicate Step 6 content produced during save was removed before validation completion.
- Step 6 status was accepted as structure guidance, not a committed physical repo scaffold. First implementation story must verify actual starter shape before agents rely on paths.
- Validation status is set to `READY FOR IMPLEMENTATION` because all checklist items are satisfied and remaining gaps are non-blocking implementation follow-ups.

### Architecture Completeness Checklist

**Requirements Analysis**

- [x] Project context thoroughly analyzed
- [x] Scale and complexity assessed
- [x] Technical constraints identified
- [x] Cross-cutting concerns mapped

**Architectural Decisions**

- [x] Critical decisions documented with versions
- [x] Technology stack fully specified
- [x] Integration patterns defined
- [x] Performance considerations addressed

**Implementation Patterns**

- [x] Naming conventions established
- [x] Structure patterns defined
- [x] Communication patterns specified
- [x] Process patterns documented

**Project Structure**

- [x] Complete directory structure defined
- [x] Component boundaries established
- [x] Integration points mapped
- [x] Requirements to structure mapping complete

### Architecture Readiness Assessment

**Overall Status:** READY FOR IMPLEMENTATION

**Confidence Level:** high

**Key Strengths:**

- Strong backend boundary story for interview defense.
- Explicit AI-agent consistency rules reduce multi-agent drift.
- Privacy, security, retention, and provider disclosure are architectural concerns, not afterthoughts.
- Today mission loop remains the architecture center.
- Provider risk is isolated behind broker interfaces.
- MVP avoids enterprise overbuild while preserving necessary choke points.
- Project structure maps product requirements to implementation locations.

**Areas for Future Enhancement:**

- Provider benchmark results and default provider choice.
- Exact retention/quota policy values.
- Data-flow and sequence diagrams after first vertical slice.
- E2E test matrix after the loop stabilizes.
- ADRs for final scaffold, auth implementation outcome, and provider defaults.

### Implementation Handoff

**AI Agent Guidelines:**

- Follow all architectural decisions exactly as documented.
- Use implementation patterns consistently across all components.
- Respect project structure and boundaries.
- Refer to this document for architectural questions before inventing new patterns.
- Do not bypass auth/session, provider broker, storage/privacy, attempt state machine, OpenAPI/Zod contracts, or SpeakFit UI wrappers.
- Backend stories must trigger Amelia BE Learning Mode before test/code work.

**First Implementation Priority:**

```bash
bun create bhvr@latest speakfit-english
```

Then immediately verify or adapt scaffold to the documented `apps/web`, `apps/api`, and `packages/shared` structure before building product features.

## Related

- [[prd|PRD]] — requirement source of truth.
- [[prd-validation-report|PRD Validation Report]] — PRD gate.
- [[product-brief|Product Brief]] — Discovery boundary.
- [[ux-design-specification|UX Design Specification]] — UX flows kèm theo.
- [[DESIGN|DESIGN — Quiet Studio]] — design thesis.
- [[speakfit-quiet-studio-reference|Quiet Studio Reference]] — UI/UX prototype.
- [[shadcn-tailwind-implementation-contract|Shadcn/Tailwind Implementation Contract]] — production UI bridge.
- [[ADR-001-cursor-first-ai-agent-orchestration|ADR-001 Cursor-first AI Orchestration]].
- [[BMAD_SPEAKFIT_WORKFLOW|BMAD SpeakFit Workflow]] — phase playbook + Amelia BE Learning Mode.
- [[PLANNING_QUESTIONS|Planning Questions]] — §11 stack reconfirmed.
- [[decisions|Decision Log]] — stack reconfirm + Phase 4 BE depth.
- [[raid|RAID Log]].
- [[docs/INDEX|Repo Index]].