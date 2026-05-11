---
stepsCompleted:
  - step-01-validate-prerequisites
  - step-02-design-epics
inputDocuments:
  - _bmad-output/planning-artifacts/prd.md
  - _bmad-output/planning-artifacts/architecture.md
  - _bmad-output/planning-artifacts/ux-design-specification.md
excludedDocuments:
  - _bmad-output/planning-artifacts/prd-validation-report.md
status: step-02-epics-approved
---

# My-English - Epic Breakdown

## Overview

This document provides the complete epic and story breakdown for My-English, decomposing the requirements from the PRD, UX Design if it exists, and Architecture requirements into implementable stories.

## Requirements Inventory

### Functional Requirements

FR1: Users can sign in with a low-friction authentication method.

FR2: Users can maintain one active learning profile.

FR3: Users can set a primary learning goal for interview or workplace speaking.

FR4: Users can set a self-rated English level suitable for A2-high/B1/B1+ learners.

FR5: Users can select a professional context or track, including Software Engineer and Purchasing/Business/Garment professional.

FR6: Users can update basic learning profile fields when their goal, level, or track changes.

FR7: Users can complete a short onboarding flow before their first mission.

FR8: Users can reach a recommended first daily mission immediately after onboarding.

FR9: Users can understand whether the product is suitable for their current English foundation.

FR10: Users can start a focused desktop/laptop learning session without browsing a course library or writing their own prompt.

FR11: Users can view one primary daily mission tied to their goal, level, and professional track.

FR12: Users can see the purpose, expected time, and speaking task for the current mission.

FR13: Users can access short mission content designed for 5-10 minute focused practice.

FR14: Users can access mission content for interview and workplace speaking scenarios.

FR15: Users can complete a mission through the loop of warm-up, practice, feedback, retry, save, review/reuse, and progress.

FR16: Solo PM or an internal operator can seed or verify a small set of mission templates for private testing.

FR17: Users can listen to sample audio or TTS/pre-generated audio for mission prompts, scripts, or sample answers.

FR18: Users can view sample text or transcript alongside audio where available.

FR19: Users can practice shadowing with chunks, sentences, or full-answer segments where feasible.

FR20: Users can repeat listening or shadowing steps before recording their own attempt.

FR21: Users can record a speaking attempt during a mission on desktop/laptop.

FR22: Users can replay their recorded attempt before or after receiving feedback.

FR23: Users can retry recording when a recording attempt fails or is unsatisfactory.

FR24: Users can submit a manual transcript or text answer when recording or STT is unavailable.

FR25: Users can complete the mission flow even if STT is disabled, unavailable, or too low quality.

FR26: Users can receive concise feedback for a speaking or text attempt.

FR27: Users can see at least one strength, one or two improvement points, one better phrase/sentence, and one next action in feedback.

FR27a: Users can receive feedback explanations in Vietnamese where useful, while better-phrase examples remain in English.

FR28: Users can perform an immediate retry after receiving feedback.

FR29: Users can compare or understand the relationship between an original attempt and a retry.

FR30: Users can complete a mission only after meaningful practice actions, not by passively viewing content.

FR31: Users can save useful phrases, better sentences, or sticky vocabulary from mission content or feedback.

FR32: Users can view saved phrases in a dedicated review area.

FR33: Users can see the original mission or feedback context for each saved phrase.

FR34: Users can mark saved phrases as reviewed.

FR35: Users can mark saved phrases as reused in later practice.

FR36: Users can use saved phrases as learning assets in future speaking attempts.

FR36a: Users can receive a lightweight pre-written quote card or coach note after meaningful lesson completion.

FR36b: Users can save quote cards or coach notes for later review without the quote collection becoming a required practice step.

FR37: Users can see a lightweight progress snapshot.

FR38: Users can see completed mission count.

FR39: Users can see speaking attempt and retry counts.

FR40: Users can see saved phrase and saved phrase review/reuse counts.

FR41: Users can record a self-rated confidence score (1-5) before and after a mission attempt and view their confidence trend over the last 7 days where data is available.

FR42: Users can access prior mission or attempt evidence where feasible to notice before/after improvement.

FR43: Solo PM can inspect basic validation signals for dogfood or small-group testing.

FR44: Users can see clear recovery guidance when microphone permission fails.

FR45: Users can see clear recovery guidance when recording fails.

FR46: Users can continue with manual text/transcript fallback when voice pipeline failure blocks progress.

FR47: Users can see clear loading and failure states for AI, TTS, or STT operations.

FR48: Users can continue or retry when provider-dependent operations fail where feasible.

FR49: Users can understand when recordings, transcripts, feedback, and saved phrases are stored.

FR50: Users can understand whether audio/transcript data may be sent to AI/STT/TTS providers.

FR51: Users can delete practice artifacts where feasible.

FR52: Users can avoid providing unnecessary personal data during onboarding.

FR53: The product can communicate that AI feedback is not a formal certification, hiring evaluation, or guaranteed fluency assessment.

FR54: Solo PM or system operators can track basic usage or quota for AI/TTS/STT calls.

FR55: The product can prevent or surface cost-risk situations during dogfood or small-group testing.

FR56: Solo PM can inspect enough usage information to decide whether provider choices need Architecture follow-up.

FR57: Solo PM or internal operators can prepare or edit a small set of mission templates for private testing.

FR58: Solo PM or internal operators can verify generated or sample mission content before or during private testing.

FR59: Solo PM or internal operators can inspect whether users complete missions, submit attempts, retry, save phrases, and review/reuse phrases.

FR60: Solo PM or internal operators can support a 7-14 day dogfood or small-group validation loop without a complex CMS.

### NonFunctional Requirements

NFR1: Users should reach the daily mission within 5 seconds of sign-in completion on supported desktop browsers with broadband connection.

NFR2: Mission content should reach interactive state within 3 seconds on a typical broadband connection; specific budget to be confirmed in Architecture.

NFR3: Audio playback, recording controls, replay controls, and retry actions should respond within 100ms perceived interaction latency in supported desktop browsers.

NFR4: AI, TTS, and STT operations must show clear loading states when they cannot complete immediately.

NFR5: The system must avoid long blocking flows before the user can begin speaking practice.

NFR6: Architecture must evaluate AI feedback latency, TTS generation/caching, STT latency, and recording upload size before implementation planning.

NFR7: The system must treat recordings, transcripts, feedback, interview answers, workplace examples, and saved phrases as sensitive learner data.

NFR8: Sensitive learner data must be protected in transit.

NFR9: Sensitive learner data storage, retention, deletion, and access boundaries must be defined in Architecture before implementation.

NFR10: Users must be informed when audio/transcript data may be sent to external AI/STT/TTS providers.

NFR11: The system should collect only the minimum onboarding data needed to provide the MVP learning experience.

NFR12: Users should be able to delete practice artifacts where feasible.

NFR13: The product must not present AI feedback as formal certification, hiring evaluation, or guaranteed fluency assessment.

NFR14: The mission practice loop must remain completable when STT is unavailable, too costly, or too low quality.

NFR15: Recording failures must provide clear recovery options, including retry or manual transcript/text fallback.

NFR16: AI/TTS/STT provider failures must provide clear user-facing states and recovery options where feasible.

NFR17: Mission completion should not depend on one perfect provider pipeline if a lower-fidelity fallback can preserve practice behavior.

NFR18: The MVP should prioritize preserving the daily practice behavior over maximizing automation.

NFR19: Core practice actions should be keyboard-accessible where feasible.

NFR20: Recording, replay, retry, save phrase, feedback, and fallback actions should have clear labels.

NFR21: The UI should maintain WCAG 2.1 AA color contrast ratios (4.5:1 for normal text, 3:1 for large text) for focused study.

NFR22: Audio content should have visible text, transcript, or sample text where feasible.

NFR23: Users should not be blocked from learning solely because audio recording or STT fails.

NFR24: Error states should be written in clear, practical language that tells users what to do next.

NFR25: The MVP should support Solo PM dogfood and small-group testing before optimizing for broad public scale.

NFR26: The system must track AI/TTS/STT usage with daily per-user aggregation and surface alerts when daily spend exceeds a configurable threshold.

NFR27: The product should avoid features that multiply provider costs before the daily loop is validated.

NFR28: Architecture must evaluate quota, caching, deduplication, or rate-limit strategies for AI/TTS/STT before broader testing.

NFR29: Authentication, AI feedback, TTS, and optional STT integrations must be designed so provider failures do not silently break the user journey.

NFR30: Integration choices must account for data handling, retention, latency, cost, and quality.

NFR31: The MVP should avoid LMS, payment, tutor marketplace, calendar, video-call, enterprise, or native mobile integrations.

NFR32: Major product and architecture decisions should be captured in `docs/decisions.md` or ADRs when appropriate.

NFR33: Work orders, artifact handoffs, and phase gates should remain traceable for the Solo PM + AI agent orchestration story.

NFR34: Backend-related implementation tasks must support Amelia's BE Learning Mode before code is written.

NFR35: The MVP should avoid implementation shortcuts that prevent later interview-defendable explanation of auth, storage, data flow, privacy, usage tracking, or provider integration decisions.

### Additional Requirements

- AR1: Starter template must be Bun/Hono/React monorepo, preferably `bhvr`, and Epic 1 Story 1 must initialize or verify this scaffold before product features.
- AR2: If `bhvr` lacks required backend guardrails, implementation must evaluate `vex-app`; if both mismatch, use custom `apps/web` Vite React and `apps/api` Bun/Hono scaffold.
- AR3: First scaffold story must verify or adapt actual folder names to the planned `apps/web`, `apps/api`, and `packages/shared` structure, then document any path mapping.
- AR4: Frontend must use React/Vite desktop-first PWA with TanStack Router and TanStack Query; TanStack Start is not selected for MVP.
- AR5: Frontend learner routes must include onboarding, today, missions, phrases, progress, and settings; operator route must be internal and gated.
- AR6: Production UI must use `shadcn/ui` primitives through SpeakFit-owned wrappers under `apps/web/src/components/speakfit/ui/` or scaffold-equivalent path.
- AR7: The Today page must keep the Quiet Studio three-area workspace: mission rail, central rehearsal stage, and coach panel.
- AR8: Audio recording logic must be isolated behind a dedicated hook/module for microphone permission, MediaRecorder support, duration limits, blob cleanup, and upload handoff.
- AR9: Persistent browser storage is limited to non-sensitive preferences; audio, transcripts, feedback, prompts, signed URLs, saved phrases, sessions, and provider keys must not be stored in localStorage, IndexedDB, or service-worker caches.
- AR10: PWA service worker must cache static shell assets only; no sensitive learner data or provider payloads may be cached.
- AR11: Backend must be Hono REST-first API with `/v1` route versioning from the first implementation story.
- AR12: REST routes and OpenAPI schemas are the official API contract; Hono RPC typing is allowed only inside a project-owned frontend API client wrapper.
- AR13: Every `/v1` endpoint must use Zod request/response schemas and OpenAPI coverage; Drizzle schemas are persistence-only and must not be exposed as public DTOs.
- AR14: API success responses must use `{ data, meta? }`; list responses must include pagination metadata; errors must use the stable `{ error: { code, message, requestId, details?, fieldErrors?, retryable?, retryAfter?, hint? } }` envelope.
- AR15: Backend route flow must follow `Route -> Request ID -> CORS -> Session -> CSRF for mutation -> RBAC/resource ownership -> Zod validation -> Service -> Repository/Provider/Storage -> DTO mapper -> OpenAPI response`.
- AR16: Routes must stay thin; business rules, SQL, provider calls, retention decisions, and attempt state transitions must live in services or domain modules.
- AR17: Attempt must be the central workflow aggregate, with explicit lifecycle statuses: `created`, `upload_pending`, `uploaded`, `processing_stt`, `stt_ready`, `processing_feedback`, `feedback_ready`, `needs_manual_fallback`, `failed_retryable`, `failed_final`, `expired`, and `cancelled`.
- AR18: Attempt status changes must occur only through an attempt state-machine boundary; illegal transitions must return `409 invalid_state_transition` or a more specific stable domain error.
- AR19: Long-running speech/feedback operations must return `202 Accepted` with attempt/job status and support bounded frontend polling with backoff, max duration, and `Retry-After` where useful.
- AR20: Queue infrastructure can be deferred, but job/status abstraction must exist from MVP so provider work can move out of request lifecycle later.
- AR21: Mutating endpoints that browser/network retries can repeat must support idempotency keys scoped by user, route, and operation.
- AR22: PostgreSQL plus Drizzle ORM and Drizzle Kit migrations must be used for relational persistence; migrations must be committed and run through explicit commands.
- AR23: Local development must include reproducible Docker Compose Postgres.
- AR24: Core schema must cover users/auth identities, learner profiles, missions, attempts, recording metadata, transcripts, feedback, saved phrases, phrase reuse events, progress metrics, usage/quota counters, provider call logs, and operator audit logs.
- AR25: Raw audio artifacts must live in private R2/S3-compatible object storage only when needed; Postgres stores ownership, retention, deletion, provider, and object metadata.
- AR26: Object storage must use backend-issued short-lived signed upload/read URLs scoped to authenticated user, object, action, TTL, type, size, duration, and DB ownership checks.
- AR27: Authentication must use a boring library-backed approach, preferably Better Auth with Hono and Drizzle/Postgres after implementation vetting; custom auth is rejected for MVP.
- AR28: MVP auth should prefer invite-only beta access with email magic link or OTP; sessions must be backend-owned opaque server-side cookie sessions stored in Postgres.
- AR29: Cookie-authenticated mutating requests require CSRF protection and strict Origin/Referer validation where applicable; CORS must use explicit allowlists.
- AR30: Authorization must enforce learner/operator roles server-side; learners can access only their own artifacts, and operator routes are deny-by-default and audited.
- AR31: Provider keys, DB credentials, R2 credentials, signing secrets, and auth secrets must remain server-side and use environment/secret management.
- AR32: All AI, STT, TTS, scoring, and feedback-provider calls must go through backend provider broker interfaces; frontend never calls providers directly.
- AR33: Provider broker must own provider selection, timeout, retry, fallback, retention, cost attribution, normalized errors, safe logs, and local/dev/test doubles.
- AR34: STT/TTS/LLM default provider must be selected through dogfood benchmark evidence using Vietnamese-accented English accuracy, latency, cost, failure rate, fallback rate, retention terms, developer ergonomics, and debugging clarity.
- AR35: Custom STT/TTS model training and custom-hosted speech models are rejected for MVP.
- AR36: Usage/quota tracking must aggregate daily per-user AI/TTS/STT usage and surface spend or quota alerts before broad testing.
- AR37: Rate limits are required for login, magic link/OTP, upload, signed URL generation, STT/TTS broker calls, feedback generation, export/delete, and operator actions.
- AR38: Privacy export/delete must be explicit API operations with status tracking and shared privacy service functions, covering database records and R2 objects where under SpeakFit control.
- AR39: Logs must be structured and redacted, including request ID, user hash, attempt ID, recording ID, job ID, provider call ID, provider/model, latency, status, error code, and cost units, while excluding raw sensitive payloads.
- AR40: Observability starts with structured redacted logs plus Sentry for frontend and backend errors/tracing where supported.
- AR41: MVP deployment should use managed services: web on Cloudflare Pages or Vercel, Bun/Hono API on Railway or equivalent, managed Postgres, Cloudflare R2, and separate local/preview/production environments.
- AR42: GitHub Actions CI must run install, lint, typecheck, test, build, OpenAPI generation/check, and Drizzle migration checks.
- AR43: Typed environment validation must run at app startup; committed `.env` files are forbidden except `.env.example`.
- AR44: Backend-related stories must trigger Amelia BE Learning Mode before test/code work.
- AR45: Exact retention durations, signed URL TTL defaults, provider defaults, and quota caps must be set before broader beta use.

### UX Design Requirements

UX-DR1: The default learner destination must be today's daily mission, not a dashboard, blank prompt box, course library, or generic chat.

UX-DR2: The desktop practice workspace must use a three-zone layout: mission context on the left, speaking stage in the center, and coach panel on the right.

UX-DR3: The speaking stage must always own the primary action for the current state: start, listen, shadow, record, stop, replay, get feedback, retry, save, or complete.

UX-DR4: Mission initiation must show situation context, speaking goal, expected answer length, professional track relevance, optional helper phrases or starter sentence, and clear first CTA.

UX-DR5: Users must be invited to try a rough answer first, with optional starter help available without forcing passive preparation.

UX-DR6: The experience must frame SpeakFit as a private rehearsal room with a coach, using supportive copy that normalizes imperfect first attempts.

UX-DR7: Browser microphone permission must be separated from product consent; before first recording, the UI must explain recording, provider use, artifact saving, deletion, and non-recording alternatives.

UX-DR8: The mission session UX must account for states such as `NotStarted`, `SpeakingReady`, `Recording`, `UploadingProcessing`, `FeedbackReady`, `RetryReady`, `Saved`, `Completed`, `FailedRecoverable`, and `FailedBlocked`.

UX-DR9: Each mission state must define visible status, primary CTA, secondary fallback, disabled controls, coach-panel behavior, and recovery path.

UX-DR10: Processing states after recording must use meaningful copy and options instead of indefinite spinners, including replay, retry analysis, wait, or manual transcript fallback where relevant.

UX-DR11: Feedback must appear as a coach-like card, not a report card, and include positive anchor, one upgrade, try-this-version phrase/sentence, retry focus, and retry CTA.

UX-DR12: Feedback UI must avoid score-first presentation, harsh grading, large red correction states, native-speaker comparison, long grammar reports, and labels like wrong, bad, or poor pronunciation.

UX-DR13: Retry must feel immediate and small, with labels such as `Record the stronger version` or `Try a 20-second upgrade` instead of punitive correction language.

UX-DR14: During retry, the UI should foreground the retry focus rather than the full feedback report to reduce cognitive load.

UX-DR15: After retry, the product must show a lightweight improvement cue such as clearer opening, stronger interview tone, more natural sentence, retry completed, or useful phrase saved.

UX-DR16: Mission completion must require meaningful speaking effort, ideally first attempt plus feedback plus retry, and stronger completion includes a saved reusable phrase.

UX-DR17: Completion must summarize mission completed, retry completed, one visible improvement, one reusable phrase/sentence, optional quiet gift, and next suggested action.

UX-DR18: Saved phrase interactions must communicate save-for-reuse, not generic vocabulary bookmarking.

UX-DR19: Each saved phrase must retain phrase text, original mission context, use case, retry or feedback source, and future reuse prompt.

UX-DR20: Saved phrase review must support speaking reuse through a `Saved phrase -> New prompt -> Use it in a new spoken answer` loop.

UX-DR21: The product should avoid encouraging users to collect many phrases without reuse; one or two high-value phrases per mission is enough for MVP.

UX-DR22: Quiet Gift or coach note must appear only after meaningful effort, never before or during the core speak-feedback-retry loop.

UX-DR23: Quiet Gift must remain optional and dismissible with actions such as save note, continue, or practice another sentence.

UX-DR24: MVP motivation must exclude tower/map logic, coins, shops, leaderboards, rarity, reward economy, hidden core learning features, mandatory videos, shame-based streaks, and collect-to-unlock mechanics.

UX-DR25: First-run/welcome UX may include a calm welcome, optional welcome video, and skip/start paths, but must protect time-to-value.

UX-DR26: Recovery states must preserve dignity and effort for silence, hesitation, mic denial, unsupported browser APIs, upload failure, provider timeout, STT failure, AI failure, weak network, and storage problems.

UX-DR27: If the learner is silent or stuck, the UI must make the task smaller by offering starter sentence, shorter prompt, idea chips, shadow sample, or type-first fallback.

UX-DR28: If STT or AI fails, the UI must communicate that effort is saved where true and offer replay, retry analysis, manual transcript, simpler retry prompt, or save attempt for later where feasible.

UX-DR29: Recording controls must be clear, safe, and non-alarming, with visible state, timer/status, labels, and keyboard-accessible controls.

UX-DR30: The design system foundation must be Tailwind CSS plus shadcn/ui/Radix-style primitives plus custom SpeakFit design tokens.

UX-DR31: Design tokens must define color, typography, spacing, radius, elevation/shadow, focus states, motion principles, and semantic state colors.

UX-DR32: Visual direction must be calm professional plus warm coach, with muted neutral base, warm accents, generous desktop spacing, soft professional radius, subtle depth, restrained motion, visible focus, and calm recovery colors.

UX-DR33: Reusable primitives should cover Button, Input, Textarea, Dialog, Popover, Tabs, Tooltip, Card, Badge, Progress, Toast, Dropdown, and form controls.

UX-DR34: Product components should include mission context card, speaking stage, recording control, audio replay control, coach feedback card, retry focus card, saved phrase card, attempt timeline, progress evidence card, quiet gift/coach note card, fallback recovery panel, and mic permission/consent prompt.

UX-DR35: Implementation must create an early SpeakFit UI kit/wrapper layer for shell, card, layout, pill, stat, typography, progress, voice waveform, coach feedback, and mission step navigation before full learner pages.

UX-DR36: Client UI state must stay separate from server state; persisted server data such as missions, attempts, transcripts, feedback, saved phrases, and progress must use TanStack Query or the chosen server-state layer, not duplicated in global UI state.

UX-DR37: Frontend UI must preserve the Quiet Studio mood and avoid generic admin dashboard, chatbot-first, exam/report-card, mobile-first card flow, or gamified course visuals.

UX-DR38: Accessibility must be baseline: keyboard support, visible focus, clear labels, sufficient contrast, text alongside audio where feasible, non-color-only feedback, and clear recovery copy.

UX-DR39: Mobile responsive support must keep reading missions, viewing feedback, and reviewing saved phrases usable without introducing mobile-first recording complexity or phone-first navigation.

UX-DR40: Implementation agents must treat `docs/ui-ux/speakfit-quiet-studio-reference.md` as visual/interaction source of truth and `docs/ui-ux/shadcn-tailwind-implementation-contract.md` as the production mapping contract; `cursor/canvas` internals must never be imported into app code.

### FR Coverage Map

FR1: Epic 1 - Low-friction sign-in for private daily practice.
FR2: Epic 1 - One active learner profile.
FR3: Epic 1 - Primary interview/workplace speaking goal.
FR4: Epic 1 - Self-rated A2-high/B1/B1+ level.
FR5: Epic 1 - Professional track selection.
FR6: Epic 1 - Basic profile updates.
FR7: Epic 1 - Short onboarding before first mission.
FR8: Epic 1 - Recommended first daily mission after onboarding.
FR9: Epic 1 - Suitability guidance for current English foundation.
FR10: Epic 1 - Focused desktop/laptop start without course browsing or prompt writing.
FR11: Epic 2 - Primary daily mission tied to profile.
FR12: Epic 2 - Mission purpose, expected time, and speaking task.
FR13: Epic 2 - Short 5-10 minute mission content.
FR14: Epic 2 - Interview/workplace mission scenarios.
FR15: Epic 2/Epic 3/Epic 4/Epic 5 - End-to-end mission loop across rehearsal, feedback, save/reuse, and progress.
FR16: Epic 1/Epic 6 - Seeded mission templates early; editable/verified operator templates later.
FR17: Epic 2 - Sample audio or TTS/pre-generated audio.
FR18: Epic 2 - Sample text/transcript alongside audio.
FR19: Epic 2 - Chunk/sentence/full-answer shadowing where feasible.
FR20: Epic 2 - Repeat listening or shadowing before recording.
FR21: Epic 2 - Desktop/laptop speaking attempt recording.
FR22: Epic 2 - Recorded attempt replay.
FR23: Epic 2 - Recording retry when failed or unsatisfactory.
FR24: Epic 2 - Manual transcript/text fallback.
FR25: Epic 2 - Mission flow completable without STT.
FR26: Epic 3 - Concise feedback for speaking or text attempt.
FR27: Epic 3 - Feedback structure with strength, improvements, better phrase, next action.
FR27a: Epic 3 - Vietnamese explanations where useful with English better phrases.
FR28: Epic 3 - Immediate retry after feedback.
FR29: Epic 3 - Original attempt and retry relationship/comparison.
FR30: Epic 3 - Mission completion only after meaningful practice.
FR31: Epic 4 - Save useful phrases, better sentences, or sticky vocabulary.
FR32: Epic 4 - Dedicated saved phrase review area.
FR33: Epic 4 - Original mission/feedback context for saved phrases.
FR34: Epic 4 - Mark saved phrases reviewed.
FR35: Epic 4 - Mark saved phrases reused.
FR36: Epic 4 - Use saved phrases in future speaking attempts.
FR36a: Epic 4 - Lightweight pre-written quote card or coach note after meaningful completion.
FR36b: Epic 4 - Save quote cards/coach notes without making them required practice.
FR37: Epic 5 - Lightweight progress snapshot.
FR38: Epic 5 - Completed mission count.
FR39: Epic 5 - Speaking attempt and retry counts.
FR40: Epic 5 - Saved phrase and review/reuse counts.
FR41: Epic 5 - Confidence 1-5 before/after and 7-day trend where data exists.
FR42: Epic 5 - Prior mission/attempt evidence where feasible.
FR43: Epic 5/Epic 6 - Learner progress evidence and operator dogfood validation signals.
FR44: Epic 2 - Mic permission recovery guidance.
FR45: Epic 2 - Recording failure recovery guidance.
FR46: Epic 2 - Manual fallback when voice pipeline blocks progress.
FR47: Epic 2/Epic 3 - Loading and failure states for AI, TTS, or STT.
FR48: Epic 2/Epic 3 - Continue or retry provider-dependent operations where feasible.
FR49: Epic 1 - Explain stored recordings, transcripts, feedback, and saved phrases.
FR50: Epic 1 - Explain external AI/STT/TTS provider data flow.
FR51: Epic 1 - Delete practice artifacts where feasible.
FR52: Epic 1 - Minimize onboarding personal data.
FR53: Epic 1 - AI feedback disclaimer: not certification, hiring evaluation, or guaranteed fluency.
FR54: Epic 6 - Track basic AI/TTS/STT usage or quota.
FR55: Epic 6 - Surface or prevent cost-risk situations.
FR56: Epic 6 - Usage information for provider architecture follow-up.
FR57: Epic 6 - Prepare or edit mission templates for private testing.
FR58: Epic 6 - Verify generated or sample mission content.
FR59: Epic 6 - Inspect mission, attempt, retry, phrase save, and phrase reuse behavior.
FR60: Epic 6 - Support 7-14 day dogfood without complex CMS.

## Epic List

### Epic 1: Private First Practice Setup

Users can sign in, create one private learning profile, understand the trust boundary, and land on a ready first mission without browsing a course library or writing their own prompt.

**FRs covered:** FR1-FR10, FR16, FR49-FR53

**Notes:** Includes scaffold, app shell, mission seed/read API, trust-layer copy, and default mission entry. It must avoid shipping an empty dashboard.

### Epic 2: Rehearsal Workspace and Capture

Users can rehearse inside the Quiet Studio Today workspace, listen or shadow mission content, record/replay a rough answer, and use manual text fallback when voice capture or provider support fails.

**FRs covered:** FR11-FR25, FR44-FR48

**Notes:** Includes attempt state-machine foundation, fake provider broker, three-area workspace, listening/shadowing, recording/upload/replay, and manual fallback as a first-class path.

### Epic 3: Coaching Cue and Immediate Retry

Users can receive concise supportive feedback, understand one useful upgrade, retry immediately, compare the retry safely, and complete a mission through meaningful practice.

**FRs covered:** FR26-FR30, FR27a, FR47-FR48

**Notes:** Uses structured feedback contracts and deterministic fake LLM/provider mode before real provider calls. Feedback remains coach-like, not score/report-card based.

### Epic 4: Saved Phrases and Reuse

Users can save useful phrases with original context, review and reuse them in later speaking attempts, and optionally keep quiet coach notes after meaningful practice.

**FRs covered:** FR31-FR36, FR36a, FR36b

**Notes:** Saved language must return to speaking practice; Quiet Gift remains optional, dismissible, and secondary.

### Epic 5: Progress Evidence and Confidence Tracking

Users can see lightweight progress evidence, including completed missions, attempts, retries, phrase reuse, confidence trend, and before/after proof where feasible.

**FRs covered:** FR37-FR43

**Notes:** Progress derives from attempts/events. No heavy analytics dashboard or report-card scoring.

### Epic 6: Internal Operator and Usage Control

Solo PM/internal operator can manage private testing needs: mission templates, provider usage/quota, dogfood validation signals, and gated internal inspection without complex CMS.

**FRs covered:** FR16, FR43, FR54-FR60

**Notes:** Operator UI can arrive later, but usage ledger, provider guardrails, redacted logs, and route gating must be introduced before real provider-heavy dogfood.

## Epic 1: Private First Practice Setup

Users can sign in, create one private learning profile, understand the trust boundary, and land on a ready first mission without browsing a course library or writing their own prompt.

**FRs covered:** FR1-FR10, FR16, FR49-FR53

**Notes:** Includes scaffold, app shell, mission seed/read API, trust-layer copy, and default mission entry. It must avoid shipping an empty dashboard.

### Story 1.1: Private shell and ready first mission

As a new learner,  
I want to open SpeakFit and see a private practice workspace with a ready mission,  
So that I can start speaking practice quickly without browsing a course library or figuring out setup first.

**Acceptance Criteria:**

**Given** first visit or empty session state  
**When** user opens app  
**Then** user lands on `Today` route in Quiet Studio shell, not blank page or generic dashboard  
**And** screen shows mission context, speaking stage, and coach panel areas

**Given** no profile or attempt data yet  
**When** `Today` loads  
**Then** user sees default mission preview with purpose, expected time, and speaking task  
**And** user sees clear next action to start practice

**Given** private-first practice context  
**When** shell renders  
**Then** user sees trust copy that this is private speaking practice  
**And** user sees no score-first or chatbot-first UI

**Given** desktop viewport  
**When** workspace renders  
**Then** primary CTA and mission content remain visible without horizontal clutter  
**And** three-area layout stays intact

**Given** smaller responsive viewport  
**When** workspace renders  
**Then** content remains readable  
**And** core action still visible without switching to mobile-first card flow

**Given** mission content is missing in dev or seed path  
**When** `Today` loads  
**Then** app falls back to safe placeholder mission copy  
**And** user still knows what to do next

Covers: `FR8`, `FR9`, `FR10`, `FR16`, `FR49`, `FR50`, `FR52`, `FR53`, `UX-DR1`, `UX-DR2`, `UX-DR3`, `UX-DR4`, `UX-DR5`, `UX-DR6`, `UX-DR25`, `UX-DR37`, `UX-DR39`.

### Story 1.2: App/API scaffold and route foundation

As a developer preparing the MVP foundation,
I want a Bun/Hono/React monorepo with learner and API route foundations,
So that future product stories can be implemented on stable app, API, shared contract, and test structure.

**Acceptance Criteria:**

**Given** empty or unverified project scaffold
**When** implementation starts
**Then** repository has verified or created structure for `apps/web`, `apps/api`, and `packages/shared`
**And** any deviation from planned paths is documented in the story implementation notes

**Given** frontend app starts in local development
**When** user opens web app
**Then** TanStack Router can serve learner routes for `Today`, `Onboarding`, `Missions`, `Phrases`, `Progress`, and `Settings`
**And** unknown learner routes show a calm not-found recovery state

**Given** backend app starts in local development
**When** API health route is requested
**Then** Hono serves `/v1/health` with `{ data, meta? }` success envelope
**And** errors follow stable `{ error: { code, message, requestId, details?, fieldErrors?, retryable?, retryAfter?, hint? } }` envelope

**Given** shared app/API contracts are needed
**When** web calls API client wrapper
**Then** contracts live in `packages/shared` or scaffold-equivalent shared package
**And** frontend does not call backend routes through ad-hoc fetch scattered across pages

**Given** first frontend UI foundation
**When** Quiet Studio shell renders
**Then** app uses project-owned SpeakFit UI wrapper location such as `apps/web/src/components/speakfit/ui/`
**And** production code does not import `cursor/canvas`

**Given** local validation runs
**When** developer executes available project checks
**Then** install, lint, typecheck, and test scripts exist or are documented as pending scaffold limitations
**And** failing checks caused by this story are fixed before handoff

Covers: `AR1`, `AR2`, `AR3`, `AR4`, `AR5`, `AR6`, `AR11`, `AR12`, `AR13`, `AR14`, `AR15`, `AR16`, `AR42`, `UX-DR30`, `UX-DR33`, `UX-DR35`, `UX-DR36`, `UX-DR40`.

Scope: nền kỹ thuật đầu tiên. Không làm auth thật, DB thật, onboarding thật.

### Story 1.3: Low-friction sign-in and private session

As a new learner,
I want to sign in with a low-friction method and keep a private session,
So that I can return to my practice without heavy account setup.

**Acceptance Criteria:**

**Given** first-time or returning learner
**When** sign-in is opened
**Then** user sees invite-only or beta-access friendly auth entry
**And** sign-in flow does not ask for unnecessary profile details

**Given** successful authentication
**When** session is created
**Then** backend owns opaque server-side session state
**And** browser receives secure cookie-based session only

**Given** signed-in learner enters app
**When** session is valid
**Then** user remains in private learner area with learner-only route access
**And** operator routes stay denied by default

**Given** auth-related mutation requests happen
**When** browser submits them
**Then** CSRF and Origin/Referer protections apply where required
**And** API follows explicit allowlisted CORS behavior

**Given** authentication provider or session setup fails
**When** user retries sign-in
**Then** app shows clear recovery copy and retry path
**And** user is not trapped in blank or broken state

**Given** login or session data is handled
**When** system logs or stores related events
**Then** secrets, provider keys, and sensitive payloads remain server-side only
**And** logs stay structured and redacted

Covers: `FR1`, `FR2`, `FR52`, `AR27`, `AR28`, `AR29`, `AR30`, `AR31`, `AR39`, `UX-DR6`, `UX-DR7`, `UX-DR26`, `UX-DR29`, `UX-DR38`.

Scope: signin path only. No profile form, no mission builder, no UI polish beyond safe recovery.


