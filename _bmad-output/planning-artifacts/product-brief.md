# Product Brief: SpeakFit English

**Work Order:** `docs/work-orders/WO-2026-001-product-brief.md`  
**Stage:** Discovery  
**Owner:** Solo PM  
**Primary Agent:** Mary / `bmad-agent-analyst`  
**Status:** Approved by Solo PM  
**Primary Source:** `PLANNING_QUESTIONS.md`  
**Reference Sources:** `.cursor/rules/project-context.md`, `docs/decisions.md`, `BMAD_SPEAKFIT_WORKFLOW.md`, `IDEA_BRIEF.md`

## Executive Summary

SpeakFit English is a personalized English speaking coach PWA for Vietnamese professionals who already have a basic English foundation but lack confidence, fluency, and structure when speaking in interviews or workplace situations.

The wedge is deliberately narrow: a **60-day speaking and interview fitness program for Vietnamese professionals**. The product is not a generic English learning app. It is a structured daily practice system that tells users exactly what to practice today, helps them speak or shadow short real-world prompts, gives concise feedback, and shows progress over time.

For this project, success has two layers. The product should become a working English coach that can be dogfooded and demoed, but it must also produce an interview-defendable portfolio: clear product decisions, BMAD artifacts, ADRs, sprint evidence, and a credible Solo PM + AI agent orchestration story.

## The Problem

Vietnamese professionals often have enough English knowledge to read or understand basic material, but speaking under pressure is different. In interviews and workplace conversations, they may freeze, answer without structure, overthink grammar, lack role-specific phrases, or avoid speaking because they cannot see incremental progress.

Generic tools do not solve this cleanly:

- ChatGPT Voice can converse, but users still need to invent prompts, learning paths, review loops, and progress tracking.
- Broad English apps optimize for general language learning, not interview/workplace readiness.
- Tutors can help, but they are expensive, scheduled, and often too heavy for daily 5-10 minute practice.
- YouTube or self-study content lacks personalization, feedback, and habit continuity.

The practical user need is simple: **open the app, know what to practice, speak, get useful feedback, retry, and feel a little more confident each day**.

## The Solution

SpeakFit English provides a daily voice coaching loop:

```text
Mission -> Warm-up -> Speak/Shadow -> Feedback -> Retry -> Save -> Progress
```

Each day, the user receives a short mission tied to their goal and professional context. A mission may include a question or scenario, useful phrases, a short sample answer, TTS audio, chunk/sentence/full-answer shadowing, user recording or transcript input, concise AI feedback, and one focused retry action.

The MVP should prove the behavior loop, not the entire 60-day vision. The first version should focus on one active learning profile, simple onboarding, daily missions, TTS/sample audio, recording/replay, transcript-based feedback where possible, saved phrases, and a lightweight progress signal.

## What Makes This Different

SpeakFit is not positioned as “AI conversation.” It is positioned as **structured speaking improvement**.

Key differentiators:

1. **Vietnamese learner focus** — feedback can explain issues in Vietnamese, account for common Vietnamese-speaker errors, and use interview/workplace contexts familiar to Vietnamese professionals.
2. **Daily mission, not blank chat** — users do not need to decide what to practice or how to prompt the AI.
3. **Speaking/shadowing-first habit** — users practice active output, not just reading, watching, or quizzing.
4. **Interview and workplace wedge** — the product optimizes for readiness in practical high-stakes situations, not vague fluency.
5. **Memory and progress** — the system can remember repeated mistakes, saved phrases, retries, recordings, and progress signals.
6. **Portfolio-grade build discipline** — the project itself is designed to produce evidence of product thinking, AI orchestration, backend decisions, and engineering trade-offs.

## Who This Serves

### Primary user

Vietnamese working professionals around A2-high to B1/B1+ who need to speak more confidently in interviews or workplace conversations. They are not absolute beginners and do not need a full English foundation course. They need guided practice, confidence, structure, and role-relevant language.

### Initial content tracks

1. **Software Engineer** — interview self-introduction, project explanation, technical discussion, behavioral answers, teamwork/conflict stories, and workplace communication.
2. **Purchasing / Business / Garment professional** — supplier/vendor communication, negotiation, reporting, meeting language, workplace scenarios, and interview answers.

A lightweight **General Professional** option can exist in onboarding, but early content quality should concentrate on the two real tracks above.

## Product Principles

- **Private-first** — speaking practice is personal and potentially sensitive.
- **Desktop-first for focused learning** — MVP should optimize for laptop/desktop study sessions first, because the Solo PM wants fewer mobile distractions and more deliberate practice. Mobile usability remains useful later, but phone-first UX is not the current MVP priority.
- **Daily habit-first** — a small completed speaking loop matters more than a large course library.
- **Speaking/shadowing-first** — every lesson should push toward voice output.
- **Simple AI personalization** — AI should reduce user effort, not create a complex interface.
- **Gentle but practical feedback** — praise one real strength, fix one or two important issues, then give one next action.
- **Interview-defendable decisions** — artifacts and technical choices should be explainable in future interviews.

## MVP Boundary

### In scope for the 4-week MVP

- Simple auth, preferably Google login or another low-friction auth path.
- One active learning profile per user.
- Basic onboarding: goal, self-rated level, professional context/track.
- Daily mission flow designed for 5-10 minutes.
- Core practice loop: listen, shadow, record, replay, feedback, retry.
- TTS or sample audio for short scripts and sample answers.
- Desktop-first recorder and practice layout with simple retry; mobile support can be acceptable/responsive but is not the first optimization target.
- Concise AI feedback: one strength, one or two improvements, one better sentence/phrase, one next action.
- Transcript layer if STT quality/cost is acceptable; otherwise manual transcript/text fallback.
- Saved phrases or sticky vocabulary.
- Lightweight progress snapshot: sessions completed, recordings, retries, streak/habit signal, confidence or practice-score trend.
- Usage/quota tracking for AI/TTS/STT calls to avoid cost surprises.
- Minimal content/admin operations sufficient for private/small-group testing.

### Explicitly out of MVP

- Generic English course library.
- YouTube shadowing.
- Text-to-video or roleplay video.
- Payment/subscription.
- Social/community/cohort features.
- Tutor marketplace, live teacher, or video calls.
- Deep gamification, leaderboard, or complex achievement system.
- Multi-profile/family mode as a complete feature.
- Complex CMS or enterprise admin.
- Offline-first architecture.
- Advanced pronunciation or phoneme-level scoring.
- Full real-time interview simulator.
- Broad grammar theory modules detached from speaking context.

## Success Criteria

### User success signals

After 7 days, a user should:

- Complete at least 5 daily missions.
- Record or submit at least 5 speaking attempts.
- Hear or see a small before/after improvement.
- Save or reuse 3-5 useful phrases.
- Feel: “I know what to practice today, and I am getting a little better.”

After the broader 60-day program, the user should be more interview/workplace ready, not promised “fluent English.” Minimum expected outcome:

- Answer 10-20 common interview/workplace questions more confidently.
- Speak 1-2 minutes about self, work, or projects with less freezing.
- Build a small personalized answer/phrase bank.
- Have before/after recordings as progress evidence.

### Product validation metrics

- D1, D3, D7 return behavior.
- Missions completed per week.
- Number of recordings or speaking attempts.
- Retry rate after feedback.
- Saved phrase count and reuse.
- User-rated feedback usefulness.
- Confidence before/after.
- Continued interest after 7-14 days.

### Project/portfolio success signals

- BMAD artifacts are created and approved in sequence.
- Product decisions are captured in `docs/decisions.md` or ADRs where appropriate.
- Architecture choices are defensible for backend interview discussion.
- Sprint reviews and retros show Solo PM + AI agent orchestration discipline.
- The working demo clearly shows the daily voice coaching loop.

## Validation Approach

Before or alongside building the full MVP, run a 7-14 day manual validation loop with 5-8 real users if possible. Start with the Solo PM, spouse, and a few friends or colleagues with clear interview/workplace English pain.

A low-cost validation setup can use Google Sheet/Notion plus Zalo/Telegram and AI-assisted feedback. Each day sends one mission, a few phrases, a sample answer, asks for a 1-2 minute recording, and returns concise feedback. The goal is to validate behavior before automation: **if the manual loop cannot create daily speaking retention, the app is unlikely to fix that by itself**.

## Technical Direction, Kept at Brief Level

The Product Brief should not become an architecture specification. However, existing project decisions create directional constraints for later planning:

- The project is 100% vibe-coded with GPT-5.5; AI agents write code, Solo PM specifies/reviews/decides.
- The current technical direction is Next.js/TypeScript frontend plus custom backend using Bun/Hono, PostgreSQL, Drizzle, and S3-compatible/R2 storage.
- Architecture phase should formalize data model, auth/session strategy, storage, AI/STT/TTS integration, privacy, observability, and deployment.
- Backend work should intentionally surface interview-defendable concepts rather than hide them behind a managed BaaS.

## Open Questions and Risks

### Product risks

- The product may drift into a broad English learning app and lose the sharp speaking/interview wedge.
- Users may like the idea but fail to maintain daily speaking behavior.
- Feedback may feel either too shallow to be useful or too detailed and discouraging.
- Content quality may become the real bottleneck, not UI or AI capability.

### Technical/product dependency risks

- STT quality, cost, and provider choice may affect feedback quality.
- TTS quota/caching strategy must be handled carefully if daily audio is central.
- Recording UX may still have browser/device edge cases; MVP should reduce risk by optimizing the first learning experience for desktop/laptop before expanding to mobile-first polish.
- Privacy expectations are high because recordings, transcripts, and interview answers are sensitive.

### Planning risks

- The PRD may over-expand MVP scope if every good idea from `PLANNING_QUESTIONS.md` is treated as required.
- Architecture may over-optimize for portfolio depth before the daily loop is validated.
- Manual validation may be skipped because building feels more productive.

## Recommended Next BMAD Steps

1. Solo PM reviews and approves or edits this Product Brief.
2. Optionally run PRFAQ or skeptic/product-manager review to stress-test assumptions.
3. Create PRD from the approved Product Brief.
4. Create UX Spec focused on onboarding, daily mission, practice loop, feedback, retry, and progress states.
5. Create Architecture only after PRD/UX boundaries are clear.
6. Create epics and stories; only then move individual stories to development.

## Related

- [[WO-2026-001-product-brief|WO-2026-001 Product Brief]] — work order tạo file này.
- [[PLANNING_QUESTIONS|Planning Questions]] — primary input.
- [[IDEA_BRIEF|Idea Brief]] — vision reference.
- [[prd|PRD]] — downstream requirement boundary.
- [[prd-validation-report|PRD Validation Report]] — coverage validation.
- [[ux-design-specification|UX Design Specification]] — UX flows kế thừa.
- [[architecture|Architecture]] — technical decisions kế thừa.
- [[DESIGN|DESIGN — Quiet Studio]] — design thesis.
- [[BMAD_SPEAKFIT_WORKFLOW|BMAD SpeakFit Workflow]] — phase boundary.
- [[decisions|Decision Log]] — Brief approval (2026-05-05).
- [[raid|RAID Log]] — risks & assumptions.
- [[docs/INDEX|Repo Index]].
