---
stepsCompleted:
  - step-01-init
  - step-02-discovery
  - step-02b-vision
  - step-02c-executive-summary
  - step-03-success
  - step-04-journeys
  - step-05-domain
  - step-06-innovation
  - step-07-project-type
  - step-08-scoping
  - step-09-functional
  - step-10-nonfunctional
  - step-11-polish
  - step-12-complete
inputDocuments:
  - _bmad-output/planning-artifacts/product-brief.md
  - docs/work-orders/WO-2026-002-prd.md
  - .cursor/rules/project-context.md
  - docs/decisions.md
  - docs/raid.md
  - docs/INDEX.md
  - BMAD_SPEAKFIT_WORKFLOW.md
  - PLANNING_QUESTIONS.md
  - IDEA_BRIEF.md
documentCounts:
  briefCount: 1
  researchCount: 0
  brainstormingCount: 0
  projectDocsCount: 6
workflowType: prd
releaseMode: phased
classification:
  projectType: web_app
  domain: edtech
  complexity: medium
  projectContext: brownfield
---

# Product Requirements Document - My-English

**Author:** Longth
**Date:** 2026-05-05

## Executive Summary

SpeakFit English is a desktop-first PWA that helps Vietnamese professionals improve interview and workplace English speaking through a structured daily practice loop. The product serves learners around A2-high to B1/B1+ who already have basic English knowledge but freeze, speak without structure, overthink grammar, or lack confidence when speaking under professional pressure.

The MVP will validate one core behavior: the user opens the app, sees today’s mission, listens or shadows a short prompt/sample, records or submits a speaking attempt, receives concise feedback, retries once, saves useful language, and sees lightweight progress. The MVP is not a full English learning platform, tutor marketplace, social product, pronunciation scoring engine, or real-time interview simulator.

The first learning experience must be optimized for focused desktop/laptop study sessions. Mobile responsive support is required only to keep the app usable on smaller screens; it must not drive MVP UX complexity or introduce phone-first interaction patterns.

### What Makes This Special

SpeakFit is not positioned as “AI conversation.” It is a structured speaking improvement system. Unlike ChatGPT Voice, YouTube, or broad English apps, SpeakFit removes the burden of deciding what to practice, gives a short mission tied to the learner’s professional context, and turns feedback into an immediate retry.

The core product insight is that these users do not primarily need more English content. They need a small, repeatable, private practice loop that makes speaking less intimidating, shows concrete progress, and helps them reuse better phrases in real interview/workplace situations. MVP personalization should stay simple: goal, level, professional track, current mission context, saved phrases, and repeated mistakes when available.

The project also has a portfolio objective: the PRD, UX, Architecture, ADRs, sprint artifacts, and AI work orders must demonstrate disciplined Solo PM + AI agent orchestration and interview-defendable backend/product decisions.

## Project Classification

- **Project Type:** Web app / PWA
- **Domain:** EdTech
- **Complexity:** Medium
- **Project Context:** Brownfield planning project
- **Primary MVP Platform Focus:** Desktop/laptop focused learning sessions
- **Secondary Platform Requirement:** Basic responsive support for mobile, without mobile-first MVP scope expansion

## Success Criteria

### User Success

A user is successful in the MVP if they can complete a focused 5-10 minute speaking practice session without needing to decide what to study, write their own prompt, or manage a learning plan manually.

Within the first 7 days, a successful user should:
- Complete at least 5 daily missions.
- Submit or record at least 5 speaking attempts.
- Complete at least 3 retries after receiving feedback.
- Save or reuse 3-5 useful phrases.
- Review or reuse at least 2 saved phrases in later practice.
- Report that they know what to practice today.
- Report a small confidence improvement after practice.
- See or hear at least one before/after improvement through progress or replay.

The intended user outcome is not “become fluent.” The MVP user outcome is: “I know what to practice, I spoke today, I got one useful correction, I retried, I saved/reused useful language, and I can see I am getting slightly better.”

### Business Success

MVP business success is validation that the daily speaking loop creates enough perceived value to justify continued development. Revenue, subscriptions, tutor marketplace, and paid cohorts are explicitly post-MVP.

The MVP is successful if a 7-14 day dogfood or small-user validation loop shows:
- Users return for repeated missions instead of treating the app as a one-time demo.
- Users complete speaking attempts, not only browse content.
- Users retry after feedback, proving the feedback is actionable enough.
- Users save phrases or better sentences, proving the app creates reusable learning assets.
- Users review or reuse saved phrases, proving saved language does not become dead bookmarks.
- Users can explain why SpeakFit is more useful than blank ChatGPT Voice for focused speaking practice.

For the Solo PM project, business success also includes creating clear evidence that the product wedge is defensible: Vietnamese professionals, interview/workplace speaking, structured daily missions, and private focused practice.

### Technical Success

Technical success means the MVP reliably supports the daily voice coaching loop without overbuilding the system.

The MVP must:
- Support low-friction authentication and one active learning profile.
- Present a daily mission tied to user goal, level, and professional track.
- Support desktop-first listening/shadowing/recording/replay practice.
- Provide concise AI feedback with one strength, one or two improvements, one better phrase/sentence, and one next action.
- Support retry after feedback as a first-class action.
- Save useful phrases or sticky vocabulary.
- Support basic saved phrase review: users can revisit saved phrases, see original context, and mark phrases as reviewed or reused.
- Show lightweight progress: missions completed, attempts, retries, saved/reused phrases, streak/habit signal, and confidence/practice trend where feasible.
- Track usage or quota for AI/TTS/STT calls to prevent cost surprises.
- Handle privacy-sensitive recordings/transcripts with clear storage, access, and deletion expectations to be finalized in Architecture.

Technical success does not require advanced pronunciation scoring, real-time interview simulation, native mobile polish, offline-first behavior, payment infrastructure, or complex CMS.

### Measurable Outcomes

Primary MVP validation metrics:
- D1, D3, and D7 return behavior.
- Missions completed per user per week.
- Speaking attempts submitted or recorded per user.
- Retry rate after feedback.
- Saved phrase count and reuse.
- Saved phrase review/reuse count.
- User-rated feedback usefulness.
- Confidence before/after practice.
- Number of users completing at least 5 missions in 7 days.

Portfolio and orchestration metrics:
- BMAD artifacts completed and approved in sequence.
- Scope decisions logged in `docs/decisions.md` or ADRs when appropriate.
- Risks and assumptions captured in `docs/raid.md`.
- Work orders and artifact handoffs show clear Solo PM + AI agent orchestration.
- The final demo clearly shows the daily voice coaching loop.

## Product Scope

### MVP - Minimum Viable Product

The MVP must validate the daily voice coaching loop:

```text
Mission -> Warm-up -> Speak/Shadow -> Feedback -> Retry -> Save -> Review/Re-use -> Progress
```

MVP includes:
- Simple auth.
- One active learning profile per user.
- Basic onboarding: goal, self-rated level, professional context/track.
- Desktop-first daily mission experience.
- Short mission content for focused 5-10 minute practice.
- Listening or sample audio through TTS or pre-generated audio.
- Shadowing flow with chunk/sentence/full-answer practice where feasible.
- Recording and replay on desktop/laptop.
- Transcript-based feedback if STT quality/cost is acceptable; otherwise manual transcript/text fallback.
- Concise AI feedback tied directly to retry.
- Saved phrases with basic review: users can revisit saved phrases, see original context, and mark them as reviewed or reused.
- Lightweight quiet gift layer after meaningful lesson completion: users may receive a pre-written quote card or coach note that can be saved for later, without interrupting the core practice loop.
- Lightweight progress snapshot.
- AI/TTS/STT usage or quota tracking.
- Minimal content/admin operations sufficient for private or small-group testing.

### Growth Features (Post-MVP)

Post-MVP growth features may include:
- Better lesson history and recording history.
- Review queue for saved phrases and repeated mistakes.
- Expanded motivation content such as optional coach videos, broader quote/card collections, and non-essential delight unlocks if they improve return behavior without distracting from speaking practice.
- Spaced repetition or lightweight vocabulary drills if saved phrase behavior proves valuable.
- More professional tracks.
- More robust STT-based feedback.
- Better TTS caching and deduplication.
- Weekly insights.
- Improved mobile polish after desktop-first learning is validated.
- More advanced analytics for retention and learning behavior.
- Manual validation workflow integration if the 7-14 day test proves useful.

### Vision (Future)

Future vision may include:
- A broader 30/45/60/90-day adaptive speaking program.
- Richer personalization based on repeated mistakes, saved phrases, and progress history.
- Interview/workplace scenario libraries by profession.
- Mock interview simulation.
- Advanced pronunciation or fluency scoring if technically and pedagogically justified.
- Payment/subscription or cohort models after retention and value are validated.
- BE depth showcase phases such as auth hardening, observability, and caching after MVP validation, not inside MVP scope.

## User Journeys

### Journey 1 — Software Engineer First Focused Practice Session

A Vietnamese software engineer opens SpeakFit on a laptop after work because an English interview is coming soon. They are not starting from zero; they can read technical docs, but they freeze when asked to explain projects or behavioral examples out loud.

The user signs in, creates one learning profile, selects an interview/workplace speaking goal, chooses Software Engineer as the professional track, and self-rates around A2-high/B1. The app immediately shows a short daily mission instead of a blank chat box or course library.

The mission asks them to practice a project-experience answer. The user listens to a short sample answer, shadows key chunks, then records their own attempt. After replaying, they receive concise feedback: one strength, one or two improvements, one better sentence, and one next action. They retry once using the suggested phrase.

The value moment happens when the second attempt sounds more structured than the first. The user saves a useful phrase, sees the mission marked complete, and sees lightweight progress: one mission completed, one retry, one saved phrase.

This journey reveals requirements for low-friction auth, one active profile, onboarding, desktop-first daily missions, sample audio, shadowing, recording/replay, feedback, retry, saved phrases, and lightweight progress.

### Journey 2 — Purchasing / Business Professional Reusing Saved Language

A Vietnamese purchasing or garment-industry professional wants to speak more confidently in supplier meetings, negotiation, or interviews. They are not interested in grammar theory; they want practical language they can reuse at work.

They open SpeakFit on a laptop during a focused study block. Today’s mission is a workplace scenario: explaining a supplier delay or negotiating a delivery timeline. The app provides useful phrases and a short sample response. The user shadows the sample sentence by sentence, records an answer, and receives feedback that replaces awkward wording with a more professional phrase.

They save two phrases from the feedback. Later in the week, they open the saved phrase review area, see the original mission context, and practice using one saved phrase in a new answer. They mark the phrase as reviewed or reused.

The value moment happens when saved language becomes usable speech rather than a forgotten note. The product helps them build a small personal phrase bank tied to real workplace situations.

This journey reveals requirements for professional track selection, workplace mission content, practical phrase suggestions, saved phrase storage, saved phrase review with original context, reviewed/reused status, and progress signals for saved language.

### Journey 3 — User Encounters Recording or Transcript Friction

A learner starts a mission but microphone permission fails, recording is noisy, or STT/transcript quality is not good enough for useful feedback. Without a recovery path, the daily loop breaks and the user may quit.

The app should make the failure recoverable. If recording fails, the user sees a clear message and can retry permission or switch to manual text/transcript input. If STT is unavailable or too costly, the user can paste or type their answer and still receive text-based feedback. The product should not block the mission just because the ideal voice pipeline fails.

The value moment happens when the user can still complete the practice loop despite technical friction. The MVP preserves the behavior: speak or submit, receive feedback, retry, and progress.

This journey reveals requirements for clear recording permission/error states, recording retry, manual transcript/text fallback, feedback without perfect STT, progress completion rules that do not overdepend on one provider, and architecture follow-up for provider cost, quality, privacy, and reliability.

### Journey 4 — Solo PM / Internal Operator Preparing Small-Group Testing

The Solo PM wants to dogfood SpeakFit and test it with a spouse, friends, or a small private group. They need enough operational control to seed missions, inspect whether users complete the loop, and avoid runaway AI/TTS/STT costs.

The Solo PM does not need a complex CMS in MVP. They need minimal content/admin operations: prepare or edit a small set of mission templates, verify generated/sample content, monitor basic usage/quota, and inspect whether users are completing missions, recording attempts, retrying, and saving/reusing phrases.

The value moment happens when the Solo PM can run a 7-14 day validation loop without manually editing the database or relying on production hacks.

This journey reveals requirements for minimal mission/content management, ability to seed or verify mission content, basic usage/quota visibility, basic validation metrics, small-group/private testing support, and RAID follow-up for content quality and cost risk.

### Journey 5 — Returning User Checks Progress and Continues

After several days, the user returns because they want to know whether practice is working. They do not need a complex dashboard. They need a simple signal that they are showing up and improving.

The app shows completed missions, speaking attempts, retries, saved/reused phrases, and a lightweight confidence or practice trend if available. The user can replay an earlier recording, compare it with a later attempt, and continue with today’s mission.

The value moment happens when the user can hear or see before/after improvement. This supports the emotional promise: “I am getting slightly better.”

This journey reveals requirements for mission history, recording/replay access where feasible, lightweight progress snapshot, saved/reused phrase count, confidence or practice trend, and continue-today flow.

### Journey Requirements Summary

The user journeys reveal these capability areas for MVP:

1. **Identity and profile** — simple auth, one active learning profile, goal, level, and professional track.
2. **Daily mission** — desktop-first mission experience, short focused mission content, sample answer or useful phrase support.
3. **Practice loop** — listen/shadow, record/replay, manual transcript fallback, feedback, and retry.
4. **Learning assets** — saved phrases or sticky vocabulary, basic review with original context, and reviewed/reused status.
5. **Progress** — completed missions, attempts and retries, saved/reused phrases, and lightweight confidence/practice trend.
6. **Operations** — minimal content/admin operations for private testing, basic usage/quota tracking, and basic validation metrics.
7. **Failure recovery** — microphone permission errors, recording retry, STT fallback, cost/provider limitations, and clear user-facing recovery paths.

## Domain-Specific Requirements

### Compliance & Regulatory

SpeakFit MVP targets adult Vietnamese professionals, not children, schools, universities, or formal credential programs. The MVP does not require K-12 student compliance workflows, gradebook integration, institutional LMS compliance, or certification/assessment accreditation.

The MVP must still treat learning data as sensitive because user recordings, transcripts, interview answers, workplace examples, and saved phrases may reveal personal history, employment context, salary/interview preparation, business situations, or confidence gaps.

Minimum compliance/privacy expectations:
- Users must know when recordings, transcripts, and AI feedback are stored.
- Users must know whether audio/transcript data may be sent to AI/STT/TTS providers.
- Users must be able to delete practice artifacts where feasible.
- The product should avoid collecting unnecessary personal data during onboarding.
- The product must not present AI feedback as formal English certification, hiring evaluation, or guaranteed fluency assessment.

### Technical Constraints

The MVP must preserve the daily practice loop while reducing privacy, cost, and reliability risks.

Technical constraints:
- Recording, transcript, feedback, and saved phrase data require clear ownership and access boundaries.
- Audio/STT/TTS/AI provider choices must be evaluated for data handling, retention, cost, latency, and quality in Architecture.
- Manual transcript/text fallback is required if STT quality, cost, or browser recording reliability blocks useful feedback.
- Desktop/laptop recording and replay should be optimized first; mobile recording edge cases should not drive MVP complexity.
- Feedback must remain concise and behavior-changing, not a long grammar report that discourages practice.
- Usage/quota tracking is required for AI/TTS/STT calls to prevent cost surprises during dogfood or small-group testing.

### Content and Learning Constraints

SpeakFit is an EdTech product, so product quality depends heavily on mission and feedback quality, not just software functionality.

MVP content requirements:
- Missions must be short enough for focused 5-10 minute practice.
- Missions must tie to interview or workplace speaking, not generic grammar theory.
- Sample answers and useful phrases must be practical, reusable, and appropriate for Vietnamese A2-high/B1/B1+ learners.
- Feedback should follow the product rule: one real strength, one or two important improvements, one better phrase/sentence, and one next action.
- Quiet gift or motivational quote cards, if used, must be pre-written or curated to match the learning journey, appear only after meaningful learning effort, and remain secondary to speaking improvement.
- Feedback explanations may be delivered in Vietnamese where useful to help learners understand improvement points, while keeping better-phrase examples in English.
- Saved phrases should retain original context so users can review and reuse them meaningfully.
- The product should not claim objective pronunciation scoring unless a reliable scoring method is intentionally introduced later.

### Integration Requirements

MVP integration requirements should remain minimal:
- Authentication provider for simple sign-in.
- AI provider for feedback generation.
- TTS or pre-generated audio provider/process for sample audio.
- Optional STT provider if quality and cost are acceptable.
- Storage for recordings/transcripts only if Architecture confirms privacy, cost, and deletion approach.

No LMS, school system, payment, tutor marketplace, calendar, video-call, or enterprise integration is required for MVP.

### Risk Mitigations

Key domain risks and mitigations:
- **Users do not return daily:** keep missions short, focused, and obvious from the first screen.
- **Feedback feels shallow or discouraging:** constrain feedback format and always tie it to a retry.
- **Saved phrases become dead bookmarks:** include basic review/reuse behavior in MVP.
- **Motivation rewards distract from speaking practice:** keep quiet gifts secondary, dismissible, and available only after meaningful practice completion; defer tower/map, reward economy, and hidden core features.
- **Content quality becomes bottleneck:** use seeded mission templates and allow minimal content/admin operations for private testing.
- **AI/STT/TTS cost spikes:** require usage/quota tracking before broad testing.
- **Recording/transcript privacy concerns:** define storage, retention, deletion, and provider data-flow decisions in Architecture.
- **Mobile recording edge cases consume MVP time:** optimize desktop/laptop first and keep mobile responsive support secondary.

## Innovation & Novel Patterns

### Detected Innovation Areas

SpeakFit does not depend on a technical breakthrough. Its differentiated pattern is a constrained learning loop that turns AI feedback into repeated speaking behavior:

```text
Mission -> Speak/Shadow -> Feedback -> Immediate Retry -> Save Phrase -> Review/Reuse -> Progress Evidence
```

The novel product angle is reducing learner choice at the moment of practice. Instead of giving users a blank AI chat or broad content library, SpeakFit gives one focused mission, one concise feedback cycle, one retry action, and one small reusable language asset.

### Market Context & Competitive Landscape

Existing alternatives solve adjacent problems:
- ChatGPT Voice provides conversation but requires users to design prompts, learning paths, and review loops.
- YouTube provides content but lacks personalization, feedback, and progress continuity.
- Broad English apps provide structured learning but are not focused on Vietnamese interview/workplace speaking.
- Tutors provide high-quality feedback but are scheduled, expensive, and heavy for daily practice.

SpeakFit’s differentiation is strongest if users perceive it as a private daily speaking coach, not as another content library or generic AI chat product.

### Validation Approach

The innovation pattern must be validated through behavior, not opinion. The MVP should measure:
- Retry rate after feedback.
- Saved phrase count.
- Saved phrase review/reuse count.
- Five missions completed in 7 days.
- User-rated usefulness of feedback.
- User ability to explain why SpeakFit is easier than prompting ChatGPT Voice.

### Risk Mitigation

If users do not retry or reuse saved phrases, the innovation pattern is not working. In that case, the product should avoid adding advanced review/SRS features and instead improve mission quality, feedback usefulness, and first-session clarity.

## Web App / PWA Specific Requirements

### Project-Type Overview

SpeakFit English is a browser-based PWA optimized for desktop/laptop focused learning sessions. The MVP should behave like a focused study workspace, not a mobile-first habit app or broad content portal.

The product must support the daily voice coaching loop in a modern browser: mission display, sample audio/listening, shadowing, recording/replay, feedback, retry, saved phrase review, and lightweight progress.

### Browser Matrix

MVP browser support should prioritize:
- Latest Chrome on desktop/laptop.
- Latest Edge on desktop/laptop.
- Latest Safari on macOS where feasible.

Mobile browsers should receive basic responsive support only:
- iOS Safari and Chrome mobile should remain usable for reading missions, viewing feedback, and reviewing saved phrases.
- Mobile recording edge cases should not drive MVP scope unless explicitly promoted later.

Unsupported or low-priority for MVP:
- Legacy browsers.
- Native mobile app behavior.
- Offline-first PWA behavior.
- Push notifications.
- Browser extensions.

### Responsive Design

The MVP is desktop-first:
- Primary layouts should optimize for laptop/desktop study sessions.
- The practice screen should reduce distraction and make the next action obvious.
- Recording, replay, feedback, retry, and saved phrase actions should be visible and easy to operate on desktop.

Responsive support should ensure:
- Content remains readable on mobile.
- Core actions do not break on smaller screens.
- Mobile UX does not introduce extra navigation complexity or phone-first patterns.

### Performance Targets

Performance should protect the first learning experience:
- The user should reach today’s mission quickly after login/onboarding.
- Mission content should load fast enough to preserve study momentum.
- Audio playback and recording controls should feel responsive.
- AI/STT/TTS loading states must be explicit and recoverable.
- The system should avoid long blocking flows before the user can practice.

Performance concerns to carry into Architecture:
- TTS generation/caching or pre-generation strategy.
- Recording upload size and storage cost.
- AI feedback latency.
- STT latency and fallback.
- Usage/quota safeguards for dogfood and small-group testing.

### SEO Strategy

SEO is not a primary MVP requirement.

The MVP may include basic public pages only if needed:
- Landing page or login entry.
- Basic product explanation.
- Privacy/terms style pages if required for testing trust.

The authenticated learning experience does not require SEO. SEO/content marketing should not drive MVP scope.

### Accessibility Level

MVP accessibility should target practical baseline accessibility:
- Keyboard-accessible core actions where feasible.
- Clear labels for recording, replay, retry, save phrase, and feedback actions.
- Sufficient color contrast.
- Text alternatives or visible transcript/sample text for audio content.
- Clear error messages for microphone permission, recording failure, AI/STT/TTS failure, and fallback options.

Accessibility is especially relevant because the product uses audio and speech. Users should not be blocked if audio recording or STT fails; manual transcript/text fallback is part of accessibility and resilience.

### Implementation Considerations

The PRD should not lock architecture, but this project type creates downstream requirements for UX and Architecture:
- UX must design a desktop-first practice workspace.
- Architecture must evaluate browser recording APIs, audio storage, provider latency/cost, and privacy.
- The system should not assume mobile recording reliability in MVP.
- PWA/offline features should remain post-MVP unless explicitly promoted.
- Native app features and CLI/API consumer flows are out of scope.

## Project Scoping & Phased Development

### MVP Strategy & Philosophy

**MVP Approach:** Validated Learning MVP.

The MVP is not intended to prove the full 60-day product vision, monetization, broad content scale, or advanced AI speaking assessment. It exists to validate whether Vietnamese professionals will repeatedly complete a focused daily speaking loop and perceive enough value to continue.

The MVP must prove:

```text
Mission -> Warm-up -> Speak/Shadow -> Feedback -> Retry -> Save -> Review/Re-use -> Progress
```

**Resource Requirements:** Solo PM + AI agents.

The Solo PM owns decisions, review, validation, merge, and release. AI agents produce artifacts, implementation, reviews, and recommendations. For backend implementation work, Amelia must use BE Learning Mode before code.

### MVP Feature Set — Phase 1

**Core User Journeys Supported:**
- Software Engineer first focused practice session.
- Purchasing / Business professional practice and saved phrase reuse.
- Recording/STT/transcript failure recovery.
- Solo PM small-group testing setup.
- Returning user checking progress and continuing.

**Must-Have Capabilities:**
- Simple auth.
- One active learning profile.
- Onboarding for goal, self-rated level, and professional context/track.
- Desktop-first daily mission experience.
- Short focused mission content for 5-10 minute practice.
- Sample audio or TTS/pre-generated audio.
- Shadowing practice where feasible.
- Recording and replay on desktop/laptop.
- Manual transcript/text fallback if STT is not viable.
- Concise AI feedback tied to retry.
- Retry as a first-class action.
- Saved phrases with basic review/reuse.
- Lightweight progress snapshot.
- AI/TTS/STT usage or quota tracking.
- Minimal mission/content operations for private or small-group testing.
- Clear recovery states for microphone, recording, AI/STT/TTS failure.
- Lightweight quiet gift/quote-card acknowledgement after meaningful lesson completion, without game tower/map, reward economy, or hidden core learning features.
- Privacy expectations for recording/transcript storage, provider data flow, and deletion to be finalized in Architecture.

**Explicit MVP Non-Goals:**
- Payment/subscription.
- Social/community/cohort features.
- Tutor marketplace.
- Native mobile app.
- Mobile-first UX.
- Offline-first behavior.
- Push notifications.
- Full course library.
- Broad grammar theory modules.
- Game tower/map logic, reward economy, coins/shops/leaderboards, hidden core learning features, or mandatory motivational video consumption.
- YouTube shadowing.
- Real-time interview simulator.
- Advanced pronunciation or phoneme-level scoring.
- Complex CMS.
- Enterprise/admin features beyond private testing needs.
- BE depth showcase features such as auth hardening, observability, and Redis caching.

### Post-MVP Features — Phase 2

Post-MVP should focus on strengthening the validated loop, not broadening the product too early.

Potential Phase 2 features:
- Better lesson and recording history.
- Review queue for saved phrases and repeated mistakes.
- Expanded motivation content such as optional coach videos, broader quote/card collections, and non-essential delight unlocks if they improve return behavior without distracting from speaking practice.
- Spaced repetition or lightweight vocabulary drills if saved phrase behavior proves valuable.
- More professional tracks.
- More robust STT-based feedback.
- Better TTS caching and deduplication.
- Weekly insights.
- Improved mobile polish after desktop-first learning is validated.
- More advanced analytics for retention and learning behavior.
- Manual validation workflow support if the 7-14 day test proves useful.

### Expansion / Portfolio Phase — Phase 3+

Later phases may include:
- Broader 30/45/60/90-day adaptive speaking programs.
- Richer personalization from mistakes, saved phrases, and progress history.
- Interview/workplace scenario libraries by profession.
- Mock interview simulation.
- Payment/subscription or cohort models after retention and value are validated.
- Backend showcase work: auth hardening, observability, and Redis caching as separate interview-defendable phases after MVP validation.

### Risk Mitigation Strategy

**Technical Risks**
- STT quality/cost may block transcript-based feedback.
  - Mitigation: keep manual transcript/text fallback in MVP.
- Browser recording may have edge cases.
  - Mitigation: optimize desktop/laptop first; keep mobile recording secondary.
- AI/TTS/STT costs may spike during testing.
  - Mitigation: require usage/quota tracking before broad testing.
- Recording/transcript privacy may be sensitive.
  - Mitigation: Architecture must define storage, retention, deletion, provider data flow, and access boundaries.

**Market/Product Risks**
- Users may not return daily.
  - Mitigation: keep first session short, obvious, and focused.
- Feedback may not drive behavior change.
  - Mitigation: require concise feedback tied to immediate retry.
- Saved phrases may become dead bookmarks.
  - Mitigation: include basic review/reuse and measure reuse.
- Product may drift into a generic English app.
  - Mitigation: enforce interview/workplace speaking wedge and desktop-first focused study scope.
- Motivation rewards may become a distracting gamification layer.
  - Mitigation: keep quote cards or coach notes lightweight, post-completion, optional, and secondary to speaking improvement; defer tower/map mechanics and reward economy until after loop validation.

**Resource Risks**
- Solo PM + AI agents may overbuild.
  - Mitigation: enforce work orders, phase gates, and explicit non-goals.
- Planning may become too heavy.
  - Mitigation: only carry forward requirements that support the daily loop, validation, privacy, or portfolio evidence.

## Functional Requirements

### User Account and Learning Profile

- FR1: Users can sign in with a low-friction authentication method.
- FR2: Users can maintain one active learning profile.
- FR3: Users can set a primary learning goal for interview or workplace speaking.
- FR4: Users can set a self-rated English level suitable for A2-high/B1/B1+ learners.
- FR5: Users can select a professional context or track, including Software Engineer and Purchasing/Business/Garment professional.
- FR6: Users can update basic learning profile fields when their goal, level, or track changes.

### Onboarding and First Session

- FR7: Users can complete a short onboarding flow before their first mission.
- FR8: Users can reach a recommended first daily mission immediately after onboarding.
- FR9: Users can understand whether the product is suitable for their current English foundation.
- FR10: Users can start a focused desktop/laptop learning session without browsing a course library or writing their own prompt.

### Daily Mission

- FR11: Users can view one primary daily mission tied to their goal, level, and professional track.
- FR12: Users can see the purpose, expected time, and speaking task for the current mission.
- FR13: Users can access short mission content designed for 5-10 minute focused practice.
- FR14: Users can access mission content for interview and workplace speaking scenarios.
- FR15: Users can complete a mission through the loop of warm-up, practice, feedback, retry, save, review/reuse, and progress.
- FR16: Solo PM or an internal operator can seed or verify a small set of mission templates for private testing.

### Listening and Shadowing Practice

- FR17: Users can listen to sample audio or TTS/pre-generated audio for mission prompts, scripts, or sample answers.
- FR18: Users can view sample text or transcript alongside audio where available.
- FR19: Users can practice shadowing with chunks, sentences, or full-answer segments where feasible.
- FR20: Users can repeat listening or shadowing steps before recording their own attempt.

### Speaking Attempt, Recording, and Replay

- FR21: Users can record a speaking attempt during a mission on desktop/laptop.
- FR22: Users can replay their recorded attempt before or after receiving feedback.
- FR23: Users can retry recording when a recording attempt fails or is unsatisfactory.
- FR24: Users can submit a manual transcript or text answer when recording or STT is unavailable.
- FR25: Users can complete the mission flow even if STT is disabled, unavailable, or too low quality.

### Feedback and Retry

- FR26: Users can receive concise feedback for a speaking or text attempt.
- FR27: Users can see at least one strength, one or two improvement points, one better phrase/sentence, and one next action in feedback.
- FR27a: Users can receive feedback explanations in Vietnamese where useful, while better-phrase examples remain in English.
- FR28: Users can perform an immediate retry after receiving feedback.
- FR29: Users can compare or understand the relationship between an original attempt and a retry.
- FR30: Users can complete a mission only after meaningful practice actions, not by passively viewing content.

### Saved Phrases and Review

- FR31: Users can save useful phrases, better sentences, or sticky vocabulary from mission content or feedback.
- FR32: Users can view saved phrases in a dedicated review area.
- FR33: Users can see the original mission or feedback context for each saved phrase.
- FR34: Users can mark saved phrases as reviewed.
- FR35: Users can mark saved phrases as reused in later practice.
- FR36: Users can use saved phrases as learning assets in future speaking attempts.
- FR36a: Users can receive a lightweight pre-written quote card or coach note after meaningful lesson completion.
- FR36b: Users can save quote cards or coach notes for later review without the quote collection becoming a required practice step.

### Progress and Validation Signals

- FR37: Users can see a lightweight progress snapshot.
- FR38: Users can see completed mission count.
- FR39: Users can see speaking attempt and retry counts.
- FR40: Users can see saved phrase and saved phrase review/reuse counts.
- FR41: Users can record a self-rated confidence score (1–5) before and after a mission attempt and view their confidence trend over the last 7 days where data is available.
- FR42: Users can access prior mission or attempt evidence where feasible to notice before/after improvement.
- FR43: Solo PM can inspect basic validation signals for dogfood or small-group testing.

### Failure Recovery and User Guidance

- FR44: Users can see clear recovery guidance when microphone permission fails.
- FR45: Users can see clear recovery guidance when recording fails.
- FR46: Users can continue with manual text/transcript fallback when voice pipeline failure blocks progress.
- FR47: Users can see clear loading and failure states for AI, TTS, or STT operations.
- FR48: Users can continue or retry when provider-dependent operations fail where feasible.

### Privacy, Consent, and Data Control

- FR49: Users can understand when recordings, transcripts, feedback, and saved phrases are stored.
- FR50: Users can understand whether audio/transcript data may be sent to AI/STT/TTS providers.
- FR51: Users can delete practice artifacts where feasible.
- FR52: Users can avoid providing unnecessary personal data during onboarding.
- FR53: The product can communicate that AI feedback is not a formal certification, hiring evaluation, or guaranteed fluency assessment.

### Usage and Cost Control

- FR54: Solo PM or system operators can track basic usage or quota for AI/TTS/STT calls.
- FR55: The product can prevent or surface cost-risk situations during dogfood or small-group testing.
- FR56: Solo PM can inspect enough usage information to decide whether provider choices need Architecture follow-up.

### Minimal Operations for Private Testing

- FR57: Solo PM or internal operators can prepare or edit a small set of mission templates for private testing.
- FR58: Solo PM or internal operators can verify generated or sample mission content before or during private testing.
- FR59: Solo PM or internal operators can inspect whether users complete missions, submit attempts, retry, save phrases, and review/reuse phrases.
- FR60: Solo PM or internal operators can support a 7-14 day dogfood or small-group validation loop without a complex CMS.

## Non-Functional Requirements

### Performance

- NFR1: Users should reach the daily mission within 5 seconds of sign-in completion on supported desktop browsers with broadband connection.
- NFR2: Mission content should reach interactive state within 3 seconds on a typical broadband connection; specific budget to be confirmed in Architecture.
- NFR3: Audio playback, recording controls, replay controls, and retry actions should respond within 100ms perceived interaction latency in supported desktop browsers.
- NFR4: AI, TTS, and STT operations must show clear loading states when they cannot complete immediately.
- NFR5: The system must avoid long blocking flows before the user can begin speaking practice.
- NFR6: Architecture must evaluate AI feedback latency, TTS generation/caching, STT latency, and recording upload size before implementation planning.

### Security and Privacy

- NFR7: The system must treat recordings, transcripts, feedback, interview answers, workplace examples, and saved phrases as sensitive learner data.
- NFR8: Sensitive learner data must be protected in transit.
- NFR9: Sensitive learner data storage, retention, deletion, and access boundaries must be defined in Architecture before implementation.
- NFR10: Users must be informed when audio/transcript data may be sent to external AI/STT/TTS providers.
- NFR11: The system should collect only the minimum onboarding data needed to provide the MVP learning experience.
- NFR12: Users should be able to delete practice artifacts where feasible.
- NFR13: The product must not present AI feedback as formal certification, hiring evaluation, or guaranteed fluency assessment.

### Reliability and Resilience

- NFR14: The mission practice loop must remain completable when STT is unavailable, too costly, or too low quality.
- NFR15: Recording failures must provide clear recovery options, including retry or manual transcript/text fallback.
- NFR16: AI/TTS/STT provider failures must provide clear user-facing states and recovery options where feasible.
- NFR17: Mission completion should not depend on one perfect provider pipeline if a lower-fidelity fallback can preserve practice behavior.
- NFR18: The MVP should prioritize preserving the daily practice behavior over maximizing automation.

### Accessibility

- NFR19: Core practice actions should be keyboard-accessible where feasible.
- NFR20: Recording, replay, retry, save phrase, feedback, and fallback actions should have clear labels.
- NFR21: The UI should maintain WCAG 2.1 AA color contrast ratios (4.5:1 for normal text, 3:1 for large text) for focused study.
- NFR22: Audio content should have visible text, transcript, or sample text where feasible.
- NFR23: Users should not be blocked from learning solely because audio recording or STT fails.
- NFR24: Error states should be written in clear, practical language that tells users what to do next.

### Scalability and Cost Control

- NFR25: The MVP should support Solo PM dogfood and small-group testing before optimizing for broad public scale.
- NFR26: The system must track AI/TTS/STT usage with daily per-user aggregation and surface alerts when daily spend exceeds a configurable threshold (exact cap to be set in Architecture).
- NFR27: The product should avoid features that multiply provider costs before the daily loop is validated.
- NFR28: Architecture must evaluate quota, caching, deduplication, or rate-limit strategies for AI/TTS/STT before broader testing.

### Integration

- NFR29: Authentication, AI feedback, TTS, and optional STT integrations must be designed so provider failures do not silently break the user journey.
- NFR30: Integration choices must account for data handling, retention, latency, cost, and quality.
- NFR31: The MVP should avoid LMS, payment, tutor marketplace, calendar, video-call, enterprise, or native mobile integrations.

### Maintainability and Portfolio Evidence

- NFR32: Major product and architecture decisions should be captured in `docs/decisions.md` or ADRs when appropriate.
- NFR33: Work orders, artifact handoffs, and phase gates should remain traceable for the Solo PM + AI agent orchestration story.
- NFR34: Backend-related implementation tasks must support Amelia’s BE Learning Mode before code is written.
- NFR35: The MVP should avoid implementation shortcuts that prevent later interview-defendable explanation of auth, storage, data flow, privacy, usage tracking, or provider integration decisions.

## MVP Handoff Clarifications from Party Mode Review

This section captures the Step 11 Party Mode polish comments from John, Skeptic, Winston, and Sally. These clarifications do not expand MVP scope; they tighten handoff boundaries for UX, Architecture, Epics/Stories, and Sprint Planning.

### Product Clarifications

- The PRD is ready to complete after a light polish pass; no major rewrite or reopened discovery is recommended.
- MVP validation must measure habit and learning value, not vanity activation alone. The key signals remain D1/D3/D7 return behavior, completed missions, retry rate after feedback, saved phrase count, saved phrase review/reuse count, and user-rated feedback usefulness.
- The first-session experience must be concrete enough for UX to design without inventing the core flow: the user should reach a default mission quickly, listen or shadow, speak or submit an attempt, receive concise feedback, retry, and save/reuse useful language.
- MVP feedback must not be a vague “AI feedback” box. It should prioritize a small number of improvement axes and produce one clear next action.
- Saved phrases are MVP learning assets only if they re-enter the speaking loop. Basic review/reuse means users can revisit saved phrases, see original mission/feedback context, mark them reviewed or reused, and use them in later practice. It is not a complex SRS or vocabulary mini-app.

### Product Risk and Validation Assumptions

- The riskiest product assumption is not that AI/STT/TTS can work; it is that a learner will repeatedly open a desktop/laptop session, speak out loud, accept feedback, and retry without social pressure or a live teacher.
- The desktop-first focus supports deliberate study, but it may create activation or habit risk because many learners discover and practice English on mobile. MVP validation must watch whether desktop-first improves focus or reduces usage.
- Feedback may fail if it is too generic, too long, too judgmental, or not tied to an immediate retry. The MVP must validate whether users perceive feedback as useful enough to speak again.
- Saved phrases may become dead bookmarks. The MVP must validate review/reuse behavior before investing in spaced repetition or a larger vocabulary system.
- If users do not retry or reuse saved phrases, the response should be to improve mission quality, feedback usefulness, and first-session clarity before adding more features.

### Architecture Handoff Notes

- MVP voice processing should assume browser-based recording for supported desktop browsers first.
- Architecture should evaluate managed STT, TTS, and LLM providers first; no custom speech model training is required for MVP.
- Manual transcript/text fallback is part of the MVP resilience strategy and should remain available if STT quality, cost, latency, or browser recording reliability blocks useful feedback.
- MVP should minimize raw audio retention where feasible. Architecture must define whether raw audio is stored, for how long, who can access it, and how users can delete practice artifacts.
- MVP should store only the learning artifacts needed for the validated loop: transcripts where needed, feedback, saved phrases, progress, and usage/quota signals.
- User audio or transcripts must not be used for model training unless explicitly opted in.
- PWA expectations must be bounded: installability and responsive web behavior are acceptable, but core coaching requires network access. Offline-first speech coaching is out of scope for MVP; any offline support should be limited to shell caching or recent review content if Architecture later chooses it.

### UX Handoff Notes

- Desktop-first means a focused study workspace, not a mobile card flow stretched onto a larger screen. The primary practice layout should make mission prompt, sample/transcript, recording controls, feedback, retry, and save/reuse actions visible without losing context.
- The MVP should optimize for a 10-20 minute focused desktop/laptop study session with mic/headphones, while still allowing the first value moment to happen quickly.
- The first-run experience should protect time-to-value: avoid heavy configuration, provide a ready default mission, explain microphone permission through user benefit, and help the learner speak, receive useful correction, and retry within roughly 60 seconds where feasible.
- Feedback UX should feel like a coach, not a report card. Each feedback cycle should limit itself to 1-3 improvement points, include “what to retry next,” and make the next action obvious.
- Saved phrases should be framed as a personal speaking toolbox: phrases the learner wants to say naturally in future interview/workplace contexts, grouped or contextualized by mission where feasible.
- The experience must be psychologically safe for Vietnamese learners who may feel embarrassed speaking English alone. Feedback tone should be encouraging, accent-tolerant, non-judgmental, and oriented toward improvement rather than native-like perfection.
- Mic, network, AI, TTS, and STT failures should recover gracefully without making the user feel that the practice session is lost.

## Workflow Completion

The PRD workflow is complete. This document now contains the project classification, executive summary, success criteria, product scope, user journeys, domain-specific requirements, innovation analysis, web/PWA requirements, phased scoping, functional requirements, non-functional requirements, and Party Mode handoff clarifications.

This PRD is ready to serve as the foundation for downstream UX design, technical architecture, epics/stories, sprint planning, and implementation readiness validation. All downstream artifacts should trace back to this PRD and update it only when requirements materially change.

## Related

- [[WO-2026-002-prd|WO-2026-002 PRD]] — work order tạo file này.
- [[product-brief|Product Brief]] — Discovery source of truth.
- [[prd-validation-report|PRD Validation Report]] — validation gate cho PRD này.
- [[ux-design-specification|UX Design Specification]] — UX flows downstream.
- [[architecture|Architecture]] — technical decisions downstream.
- [[DESIGN|DESIGN — Quiet Studio]] — design system reference.
- [[speakfit-quiet-studio-reference|Quiet Studio Reference]] — frozen UI/UX prototype.
- [[shadcn-tailwind-implementation-contract|Shadcn/Tailwind Implementation Contract]] — production UI mapping.
- [[BMAD_SPEAKFIT_WORKFLOW|BMAD SpeakFit Workflow]] — phase playbook.
- [[PLANNING_QUESTIONS|Planning Questions]] — fallback detail (archived after Brief approval).
- [[IDEA_BRIEF|Idea Brief]] — vision color reference.
- [[decisions|Decision Log]].
- [[raid|RAID Log]].
- [[docs/INDEX|Repo Index]].