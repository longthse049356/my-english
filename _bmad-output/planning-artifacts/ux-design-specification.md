---
stepsCompleted:
  - "1 - UX workflow init"
  - "2 - Project understanding / discovery"
  - "3 - Core User Experience"
  - "4 - Desired Emotional Response"
  - "5 - UX Pattern Analysis & Inspiration"
  - "6 - Design System Choice"
  - "7 - Defining Core Experience"
inputDocuments:
  - _bmad-output/planning-artifacts/product-brief.md
  - _bmad-output/planning-artifacts/prd.md
  - .cursor/rules/project-context.md
  - docs/INDEX.md
  - docs/decisions.md
  - docs/raid.md
---

# UX Design Specification My-English

**Author:** Longth
**Date:** 2026-05-07

---

<!-- UX design content will be appended sequentially through collaborative workflow steps -->

## Step 1 — UX Workflow Init

**Purpose:** Initialize the BMad UX design workflow, establish this document as the UX specification artifact, and track workflow progress through frontmatter.

**Workflow source:** `.claude/skills/bmad-create-ux-design/steps/`

**Output artifact:** `_bmad-output/planning-artifacts/ux-design-specification.md`

**Input documents:** The source documents listed in the frontmatter provide planning, PRD, project context, decisions, and RAID grounding for downstream UX decisions.

## Step 2 — Project Understanding / Discovery

**Purpose:** Capture the product vision, target users, core UX challenges, and design opportunities so later UX decisions stay anchored to the project context.

## Executive Summary

### Project Vision

SpeakFit English is a desktop-first PWA that helps Vietnamese professionals improve interview and workplace English speaking through a structured daily practice loop. The MVP should validate whether users repeatedly complete a focused mission, speak or shadow, receive concise feedback, retry, save useful language, review or reuse saved phrases, and see lightweight progress.

The UX vision is not a broad course platform, generic AI chat, or mobile-first habit app. It is a private focused study workspace that reduces learner choice at the moment of practice and makes the next speaking action obvious.

### Target Users

The primary users are Vietnamese working professionals around A2-high to B1/B1+ who can understand basic English but struggle to speak with confidence and structure under interview or workplace pressure.

Initial UX priority should support two content tracks:

- Software Engineer: interview self-introduction, project explanation, technical discussion, behavioral answers, teamwork/conflict stories, and workplace communication.
- Purchasing / Business / Garment professional: supplier/vendor communication, negotiation, reporting, meeting language, workplace scenarios, and interview answers.

Users may feel embarrassed speaking English alone or discouraged by overly detailed correction. The UX must be psychologically safe, private, encouraging, accent-tolerant, and oriented toward small visible improvement.

### Key Design Challenges

1. **Fast first value moment** — Users should reach a ready default mission quickly after sign-in/onboarding and begin practice without browsing a course library or writing prompts.
2. **Psychological safety for recording** — Speaking aloud and hearing feedback can feel vulnerable, so the interface must feel private, low-pressure, and retry-oriented.
3. **Desktop practice workspace clarity** — The product must fit mission prompt, sample/transcript, listening/shadowing, recording/replay, feedback, retry, save phrase, and progress actions into a focused workspace without clutter.
4. **Resilient fallback paths** — Mic permission, recording, STT, TTS, AI, and network failures must not break the learning loop; manual text/transcript fallback must remain visible and practical.
5. **Saved phrase reuse** — Saved phrases must re-enter speaking practice through review/reuse flows rather than becoming passive bookmarks.

### Design Opportunities

1. **Guided mission rail** — A clear step-by-step practice flow can make the next action obvious at every moment: listen, shadow, record, review feedback, retry, save, or finish.
2. **Coach-like feedback card** — Feedback can differentiate SpeakFit by being concise, encouraging, Vietnamese-explanatory where useful, and directly tied to one retry action.
3. **Before/after progress moment** — Replay, retry comparison, and confidence-before/after scoring can help users feel small improvement inside a single session.
4. **Personal speaking toolbox** — Saved phrases can become reusable speaking assets with mission context, review status, and prompts to use them in later attempts.
5. **Traceable UX artifact** — Screen and state decisions should map back to PRD requirements so downstream Architecture, Epics/Stories, and portfolio explanation remain aligned.

## Step 3 — Core User Experience

**Purpose:** Define the core SpeakFit experience, MVP promise, platform strategy, speaking/retry loop, saved phrase reuse, failure/privacy behavior, motivation layer, and experience principles.

## Core User Experience

### Defining Experience

The defining experience of SpeakFit English is helping a Vietnamese professional complete one realistic speaking practice moment: see a situation, say something imperfect, receive one clear coaching cue, and make the answer stronger through a short retry.

For MVP UX, the core loop should be reduced to the behavior that must succeed:

```text
Prompt → Speak → Feedback → Retry
```

The broader learning loop still matters, but warm-up, saved phrases, review/reuse, and progress should support this core behavior rather than slow it down. The product should not feel like a generic AI chat, course catalog, grammar app, or testing product. It should feel like a private coach that helps the learner speak one useful answer more clearly than before.

The strongest MVP value moment is the retry improvement moment: the learner tries a first answer, receives one practical improvement, records a short upgraded version, and feels the second attempt is clearer, more confident, or more professional.

### MVP Promise

Every day, SpeakFit should help the learner complete one realistic speaking mission, make one meaningful improvement through retry, and keep or reuse one phrase that can transfer to a real interview or workplace situation.

Activation should not be defined by sign-up or onboarding completion. A user is activated when they complete their first mission with at least one attempt, one feedback cycle, and one retry. A stronger activation signal is first mission completion with one retry and one saved or accepted reusable phrase.

### Platform Strategy

SpeakFit MVP should be designed as a desktop-first browser-based PWA for focused laptop/desktop study sessions. The primary interaction model is mouse/keyboard plus microphone/headset, with visible text and audio controls.

The desktop practice screen should use a focused mission workspace rather than a mobile card flow stretched onto a large screen. A recommended layout is:

- **Left: Mission context** — situation, speaking goal, today’s focus, and up to three helper phrases.
- **Center: Speaking stage** — the main interaction area for prompt, sample/shadowing, recording, replay, and retry. This area should always own the primary action.
- **Right: Coach panel** — feedback and retry guidance after an attempt. This panel should stay quiet or minimal before the first attempt.

Mobile responsive support is secondary. Mobile users should be able to read missions, view feedback, and review saved phrases, but mobile-first recording complexity should not drive MVP UX decisions. Because speaking practice also requires privacy, the desktop experience should include reassurance such as private practice copy, quick mic checks, and short mission options.

Offline-first behavior is out of scope for MVP. The core coaching loop assumes network access for AI/TTS/STT-dependent steps. Offline or poor-network states may support reading cached mission content or reviewing saved phrases, but must not promise new AI feedback unless online processing is available.

### Effortless Interactions

The following interactions should feel effortless:

- Starting today’s realistic speaking prompt without choosing from a course library or writing a prompt.
- Understanding the situation, speaking goal, and expected answer length.
- Beginning a first attempt even if the answer may be imperfect.
- Accessing lightweight help only when needed: starter sentence, idea chips, sample answer, or shadowing.
- Starting, stopping, replaying, discarding, and retrying a recording.
- Switching to manual text/transcript fallback when recording or STT fails.
- Reading feedback as a short coaching card rather than a long evaluation report.
- Taking the recommended retry action directly from feedback.
- Keeping one useful phrase or reusable answer snippet from the mission.
- Seeing mission completion and lightweight evidence of improvement after meaningful practice actions.

Warm-up should be treated as optional inline support, not a mandatory separate stage. The default experience should encourage an attempt before explanation: the learner should be invited to say a rough answer first, then use help if stuck.

### Feedback and Retry Pattern

Feedback is not a report. It is a retry launcher.

The primary feedback card should follow this pattern:

1. **Positive anchor** — confirm what the learner communicated successfully.
2. **One upgrade** — identify the single most useful improvement for the next attempt.
3. **Try this version** — provide one better phrase, sentence, or answer frame the learner can say immediately.
4. **Retry action** — invite a short upgraded attempt with a clear target.

The UX should avoid score-first presentation, harsh grading language, large red error states, long grammar reports, and labels such as “wrong,” “bad,” or “poor pronunciation.” If progress scoring exists later, it should stay secondary to coaching and improvement.

Retry should not feel like punishment. User-facing language should frame retry as making the answer stronger, clearer, or more workplace-ready. Prefer labels such as “Try the stronger version,” “Do a 20-second upgrade,” or “Record improved answer” over “fix mistakes” or “improve score.”

### Saved Phrase Reuse Pattern

Saved phrases should be designed as reusable speaking assets, not passive bookmarks.

The MVP should prefer “save for reuse” over generic saving. Each saved phrase or reusable snippet should retain:

- The phrase or better sentence.
- The original mission context.
- The use case, such as interview intro, project explanation, standup update, supplier negotiation, manager update, or client call.
- A future reuse opportunity where the phrase can return in a later mission.

Review should be a speaking reuse loop, not just flashcard reading. A strong pattern is:

```text
Saved phrase → New prompt → Use it in a new spoken answer
```

The product should avoid encouraging users to collect many phrases without reuse. One or two high-value phrases per mission is enough for MVP.

### Critical Success Moments

The core experience succeeds when these moments happen:

1. **Ready situation moment** — the user quickly sees a realistic interview or workplace prompt relevant to their goal, level, and professional track.
2. **Permission-to-sound-bad moment** — the UI makes it safe to speak an imperfect first answer through supportive copy, starter help, privacy reassurance, and fallback options.
3. **First speaking moment** — the user records or submits an attempt without being blocked by setup, mic confusion, or fear of judgment.
4. **Useful feedback moment** — the user receives one strength, one upgrade, one better phrase/sentence, and one clear retry target.
5. **Retry improvement moment** — the user makes a short upgraded attempt and sees or feels that the second version is clearer, stronger, or more professional.
6. **Reusable language moment** — the user keeps one phrase or answer snippet that can transfer to a real interview or workplace situation.
7. **Progress evidence moment** — the user sees a lightweight signal such as mission completed, retry completed, saved/reused phrase count, or confidence-before/after score.

### Mission Attempt State, Failure, Privacy, and Offline Behavior

UX must define invisible interaction states so the recording and AI feedback flow feels reliable. The mission session should account for states such as:

- `NotStarted`
- `SpeakingReady`
- `Recording`
- `UploadingProcessing`
- `FeedbackReady`
- `RetryReady`
- `Saved`
- `Completed`
- `FailedRecoverable`
- `FailedBlocked`

For each mission state, the UI should make the primary CTA, secondary fallback, and recovery path clear.

Async states must be first-class UX. After recording stops, the user should see meaningful processing copy rather than an indefinite spinner. If feedback takes longer than expected, the UI should reassure the user and offer practical options such as continuing to wait, replaying the attempt, saving the attempt, retrying analysis, or switching to manual transcript/text fallback.

UX must separate browser microphone permission from product consent. Before the first recording, the product should explain that voice may be recorded for speaking feedback, whether audio/transcripts may be sent to AI/STT providers, whether artifacts are saved, and what deletion or non-recording alternatives exist. Browser permission alone is not sufficient product consent.

The UX should distinguish recoverable failures from blocked failures. Recoverable failures include weak network, upload failure, provider timeout, or STT failure while the recording still exists. Blocked failures include denied mic permission, unsupported browser APIs, corrupted recording, or unavailable storage. In both cases, the user should not feel the session is lost.

### Motivation & Quiet Gift Layer

SpeakFit may include a lightweight motivation layer in MVP, but it must act as emotional closure after meaningful speaking effort rather than a standalone gamification system. The motivation layer should reward the courage to speak, not the act of collecting.

After a learner completes a lesson or practice session, the product may show a small quiet gift moment: a pre-written quote card or coach note designed for the learner’s journey. The learner can save the card for later, continue, or practice another sentence.

This layer should support the emotional goal of SpeakFit: private coaching, permission to sound imperfect, one visible improvement, and one reusable sentence. It should not interrupt the core `Prompt → Speak → Feedback → Retry` loop.

MVP may include:

- A small gift or quote card after successful lesson completion.
- Pre-written quote cards mapped to the learning journey, such as a 60-day speaking path.
- A simple saved quote/card collection, such as `Saved Notes` or `Coach Notes`.
- An optional first-login welcome video that can be skipped.
- A small low-energy motivation area with limited coach-style videos if it does not delay practice.

MVP must exclude:

- Game tower/map logic.
- Coins, shops, leaderboards, rarity, or reward economy.
- Hidden core learning features.
- Mandatory video watching.
- Streak punishment or shame-based reminders.
- Strong collect-to-unlock mechanics.

Reward rules:

1. Quiet gifts appear only after meaningful learning effort.
2. Quote cards must not interrupt the core practice loop.
3. The quote card is secondary to the user’s visible speaking improvement.
4. Save and continue actions must be optional and dismissible.
5. Quote/card collection must remain secondary to practice.
6. Motivation copy must be specific, calm, and relevant to the learner’s speaking journey.
7. Future unlocks, if introduced, must be non-essential delight features only.

Recommended copy tone:

- Calm, adult, warm, and private.
- Specific to the user’s effort rather than generic hype.
- Encouraging without implying native-like perfection.
- Focused on the next small action.

Example quiet gift card:

```text
"The headlights only show the next few meters."
You do not need to see the whole journey today. You only needed to take one more step: say one answer out loud.
```

Recommended first-login welcome pattern:

```text
Welcome to SpeakFit
This is a private place to practice English out loud — slowly, imperfectly, and safely.

[Start practice] [Watch welcome] [Skip]
```

### Experience Principles

1. **One realistic situation, one next action** — users should not need to decide what to study or wonder what to do next.
2. **Attempt before explanation** — the UX should invite output before passive browsing, while offering starter help if the learner is stuck.
3. **Permission to sound imperfect** — the first answer can be rough; the product exists to make it clearer, not to shame the learner.
4. **Coach, do not grade** — feedback should feel encouraging, practical, Vietnamese-explanatory where useful, and tied to immediate improvement.
5. **Retry is the product** — feedback is only valuable if it naturally leads into a short, targeted upgraded attempt.
6. **Every mission ends with one reusable sentence and one visible improvement** — the learner should leave with something they can say better and use again.
7. **Save language for reuse** — saved phrases should return in later speaking contexts instead of becoming passive bookmarks.
8. **Desktop focus without mobile scope creep** — optimize the practice workspace for laptop/desktop while keeping mobile readable and usable for secondary review.
9. **Fallback preserves momentum** — mic, STT, TTS, AI, and network failures should not make the learner feel the session is lost.
10. **Progress measures behavior, not consumption** — progress should emphasize attempts, retries, reusable phrases, phrase reuse, and confidence to use language in real situations.

## Step 4 — Desired Emotional Response

**Purpose:** Define how SpeakFit should make learners feel across the journey, including emotional goals, micro-emotions, design implications, and emotional design principles.

## Desired Emotional Response

### Primary Emotional Goals

SpeakFit should make learners feel privately supported, safe enough to sound imperfect, and visibly more capable after each meaningful practice session. The target emotion is not entertainment, competition, or academic achievement. The target emotion is quiet confidence: “I can say this a little better now, and I can use this sentence in a real interview or workplace moment.”

The primary emotional goals are:

1. **Safe to begin** — before speaking, the learner should feel that an imperfect first attempt is acceptable and expected.
2. **Guided, not judged** — during practice, feedback should feel like a calm coach helping the learner make one useful upgrade, not like a test report exposing failures.
3. **Small visible progress** — after retry, the learner should feel that the second version is clearer, stronger, or more professional than the first.
4. **Language ownership** — after saving or reusing a phrase, the learner should feel they are building a personal speaking toolbox, not collecting passive vocabulary.
5. **Quiet encouragement** — after meaningful effort, the learner may receive a small emotional closure moment that recognizes courage and supports return behavior without distracting from practice.

### Emotional Journey Mapping

The emotional journey should move the learner from hesitation to grounded confidence:

| Journey Moment | Desired Feeling | UX Support |
|---|---|---|
| First discovery | “This is for someone like me.” | Clear positioning around Vietnamese professionals, interview/workplace English, and private speaking practice. |
| First-run/onboarding | “I can start without preparing.” | Ready default mission, minimal setup, optional welcome video, and clear skip/start paths. |
| Before first recording | “It is okay if this sounds rough.” | Private practice reassurance, starter sentence support, short expected answer length, and visible fallback options. |
| During recording | “I know what to do now.” | One primary action, obvious recording state, short mission target, and low-pressure copy. |
| Waiting for feedback | “My effort is being handled; I am not stuck.” | Meaningful processing copy, replay option, retry analysis option, and fallback paths for slow or failed providers. |
| Feedback moment | “This is useful and not harsh.” | Positive anchor, one upgrade, one better phrase or sentence, and one direct retry action. |
| Retry moment | “I can make this stronger immediately.” | Feedback card turns directly into a short upgraded attempt. |
| Completion moment | “I improved one thing today.” | Completion summary, before/after cue, saved phrase or reusable sentence, and optional quiet gift card. |
| Return visit | “I know where to continue.” | Daily mission, saved phrase reuse prompt, lightweight progress evidence, and no shame-based streak pressure. |

When something goes wrong, the desired feeling is resilience rather than frustration: “The session is not lost; I still have a next step.” Error states should preserve the learner’s effort whenever possible and offer practical recovery paths.

### Micro-Emotions

The following micro-emotions are critical to the success of the speaking loop:

- **Permission over anxiety** — the product must lower the emotional barrier to speaking out loud, especially for learners embarrassed by pronunciation, pauses, or grammar mistakes.
- **Trust over skepticism** — users should understand why mic permission is needed, what happens to audio/transcripts, and how AI/STT/TTS failures are handled.
- **Focus over overwhelm** — the practice workspace should reduce choices during the mission and keep the next speaking action obvious.
- **Encouragement over grading** — feedback should avoid harsh error language, score-first layouts, and native-like perfection framing.
- **Accomplishment over consumption** — completing a mission should feel tied to speaking effort, retry, and reusable language, not to watching content or collecting rewards.
- **Warmth over hype** — motivation copy should feel adult, calm, and specific to effort rather than gamified or childish.
- **Momentum over dead ends** — fallback paths should make failures recoverable without making users restart from zero.

### Design Implications

The emotional goals translate into concrete UX choices:

- **Safe to begin → low-pressure first attempt.** Use copy that invites a rough answer, shows expected answer length, and offers starter help without forcing passive preparation.
- **Guided, not judged → coach-like feedback.** Structure feedback as one strength, one upgrade, one better phrase, and one retry CTA. Avoid red-heavy correction UI, long grammar reports, and labels such as “bad” or “wrong.”
- **Small visible progress → retry comparison cues.** After retry, show a lightweight improvement moment such as “clearer answer,” “stronger phrase used,” “retry completed,” or confidence-before/after.
- **Language ownership → save for reuse.** Saved phrases should retain mission context and return in later speaking prompts. The save action should imply future spoken use, not passive bookmarking.
- **Quiet encouragement → post-effort gift, not pre-effort distraction.** Quote cards or coach notes appear only after meaningful learning effort and remain optional, dismissible, and secondary to the speaking loop.
- **Trust → explicit consent and transparent failure states.** Separate browser mic permission from product consent, explain provider use at a human level, and provide deletion or non-recording alternatives where feasible.
- **Focus → desktop workspace with one primary action.** The main stage should always own the next action: listen, shadow, record, review feedback, retry, save, or complete.

### Emotional Design Principles

1. **Make courage visible.** The product should recognize the learner’s act of speaking, not just correctness.
2. **Protect the first attempt.** The first answer is allowed to be rough; UX should make this feel normal.
3. **Turn feedback into action.** Every feedback moment should naturally lead to one short retry.
4. **End with evidence.** Each mission should close with one visible improvement, one reusable sentence, or one small confidence cue.
5. **Reward effort quietly.** Motivation moments should feel like a private coach note, not a game system.
6. **Never shame the learner back into silence.** Avoid punitive streaks, harsh scoring, public comparison, and perfection-oriented language.
7. **Preserve momentum under failure.** Mic, network, AI, TTS, and STT problems should still leave the user with a useful next step.
8. **Design for adult learners.** Tone, visuals, rewards, and guidance should feel mature, respectful, calm, and workplace-relevant.

## Step 5 — UX Pattern Analysis & Inspiration

**Purpose:** Analyze inspiration products and patterns, define what to adopt/adapt/avoid, and turn inspiration into UX, architecture, and validation guardrails.

## UX Pattern Analysis & Inspiration

### Inspiring Products Analysis

SpeakFit should draw inspiration from products that solve adjacent parts of the experience without copying their full product model. The most useful references are ELSA Speak for speaking practice mechanics, Granola for calm desktop AI workspace patterns, and Headspace for emotionally safe coaching tone and quiet motivation.

Together, these sources define a focused inspiration strategy:

```text
ELSA Speak = speaking mechanics, micro-feedback, retry behavior
Granola = calm desktop AI workspace, session artifacts, side-panel intelligence
Headspace = emotional safety, quiet completion, non-shaming return
SpeakFit = career-relevant private speaking improvement loop
```

SpeakFit should not become a pronunciation-score app, a passive transcript tool, a wellness content app, or a generic AI chat tutor. Its differentiated experience is a private desktop speaking coach for Vietnamese professionals who understand English enough to learn, but do not yet feel comfortable saying it out loud in interview or workplace situations.

A guiding UX principle for this inspiration strategy is:

> **Correct the sentence, protect the speaker.**

Feedback may be specific, direct, and useful, but it must never make the learner feel that their voice, accent, or imperfect first attempt is the problem.

#### ELSA Speak

ELSA Speak is the closest direct inspiration because it focuses on non-native English speaking practice, microphone interaction, pronunciation feedback, and repeated attempts. It demonstrates that learners can accept AI-assisted speaking feedback when the interaction is short, clear, and directly connected to a retry action.

Patterns worth adopting or adapting:

- **Microphone-first practice flow** — speaking practice should make recording, listening, repeating, and retrying feel obvious.
- **Model → attempt → feedback → repeat** — SpeakFit can adapt this into its mission loop: prompt, speak, feedback, retry.
- **Actionable feedback units** — feedback should be broken into small, specific improvements rather than long reports.
- **One priority fix per retry** — after each attempt, the learner should know exactly what to change in the next attempt.
- **Encouragement for non-native speakers** — copy should normalize imperfect pronunciation, pauses, and grammar while still helping the learner improve.

Risks to avoid:

- **Score-first anxiety** — pronunciation scores, red marks, or correctness-heavy UI can make Vietnamese A2-high/B1 learners feel judged.
- **Accent-correction identity** — SpeakFit should not imply that the learner’s accent is the problem. The goal is clearer workplace/interview communication, not native-like perfection.
- **Overcorrection** — listing too many pronunciation, grammar, fluency, and vocabulary issues at once can reduce the learner’s willingness to retry.
- **Lesson-path clutter** — too many lessons, streaks, placement paths, and upsells would conflict with SpeakFit’s focused daily mission workspace.

For SpeakFit, ELSA is most useful as a reference for speaking mechanics, micro-feedback, and retry behavior, not as a model for scoring, gamification, or broad lesson-library structure.

#### Granola

Granola is a strong reference for the desktop-first AI workspace. Its value comes from capturing messy human input and transforming it into concise structured output without making the user manage complexity. This is highly relevant to SpeakFit because a learner’s first spoken answer will often be incomplete, hesitant, or messy, and the product must transform that effort into useful coaching.

Patterns worth adopting or adapting:

- **Calm desktop workspace** — the interface should feel focused and spacious, not like a mobile card flow stretched onto a laptop screen.
- **AI as quiet sidekick** — AI should support the learner by structuring feedback and next steps, not dominate the experience as a generic chatbot.
- **Session artifacts** — each practice session can produce useful artifacts: transcript, feedback, retry target, saved phrase, confidence cue, or quiet gift card.
- **Side-panel intelligence** — the coach panel can behave like a calm assistant that appears when feedback is ready, while the speaking stage remains the main focus.
- **Messy input → structured output** — imperfect speech should become one clear improvement, one better phrase, and one concrete retry action.
- **Persistent attempt context** — the product should remember the current attempt, retry, feedback, and saved phrase context without requiring the learner to manage it manually.

Risks to avoid:

- **Passive capture** — SpeakFit must not become a tool that only records and summarizes speech. It must actively guide the learner back into speaking aloud.
- **Transcript over-prioritization** — transcripts are useful, but the product should not shift the learner into reading/editing instead of speaking.
- **Generic AI chat side panel** — the coach panel should not become an open-ended assistant detached from the mission loop.
- **Generic productivity feel** — SpeakFit should remain emotionally warmer and more learning-oriented than a meeting notes tool.

For SpeakFit, Granola is most useful as a reference for layout, artifact handling, and AI calmness in a desktop workspace. The side panel should act as a **coach mirror**, not an infinite chatbot. Its role should stay bounded:

- What I heard.
- What went well.
- One thing to improve.
- Try again with this focus.
- Save this useful phrase.

#### Headspace

Headspace is not a direct language-learning reference, but it is highly relevant for emotional design. It shows how a digital product can make users feel safe, calm, and willing to return to a repeated practice habit without harsh judgment or productivity pressure.

Patterns worth adopting or adapting:

- **Gentle first-run copy** — onboarding should reassure the learner that the experience is private, short, and safe to try imperfectly.
- **Non-judgmental coaching language** — feedback should feel supportive and specific rather than evaluative.
- **Small-session framing** — a short completed practice session should feel valid and worthwhile.
- **Quiet completion moments** — after effort, SpeakFit can offer a small coach note or quote card as emotional closure.
- **Warm return path** — returning users should feel invited to continue, not punished for absence.
- **Effort recognition** — motivation should recognize the act of speaking and retrying, not passive consumption or collection.

Risks to avoid:

- **Wellness vagueness** — SpeakFit should not become too abstract, meditative, or motivational at the expense of workplace/interview speaking progress.
- **Slow pacing** — active speaking practice needs momentum; calm tone should not make the core loop feel sluggish.
- **Content-library sprawl** — SpeakFit should not become a motivation content app or video library.
- **Empty positivity** — quote cards and coach notes should be specific to effort, not generic encouragement.
- **Gamified comfort without skill transfer** — emotional support must remain tied to speaking effort, retry, and reusable language.

For SpeakFit, Headspace is most useful as a reference for tone, safety, completion moments, and the Quiet Gift Layer. Quiet Gift should appear only after meaningful effort, such as completing an attempt and retry, and should remain optional, dismissible, and secondary to practice.

### Transferable UX Patterns

#### Navigation Patterns

- **Daily mission as the default destination**  
  Inspired by ELSA’s direct practice entry and Headspace’s session framing, SpeakFit should bring users quickly to today’s relevant mission instead of making them browse a course catalog.

- **Desktop three-zone workspace**  
  Inspired by Granola’s calm workspace model, SpeakFit should organize the main practice screen around:
  - Mission context
  - Speaking stage
  - Coach panel

- **Session-based navigation**  
  Each practice session should feel like a contained loop with a clear start, middle, and completion moment. Users should know whether they are preparing, speaking, receiving feedback, retrying, saving, or finishing.

- **Attempt-based interaction model**  
  The core unit should be a speaking attempt and retry, not a generic chat session or passive learning page. Each attempt should be traceable to a prompt, transcript or text input, feedback, retry focus, and saved phrase opportunity.

- **Saved phrase return path**  
  Saved phrases should be reachable from review/reuse flows, but they should also reappear naturally inside later missions rather than becoming a separate passive library.

#### Interaction Patterns

- **Model → attempt → feedback → retry**  
  Adapt ELSA’s speaking repetition pattern into SpeakFit’s workplace/interview mission loop.

- **One primary action at a time**  
  The speaking stage should always make the next action obvious: start, listen, shadow, record, stop, replay, retry, save, or complete.

- **Coach panel appears when useful**  
  The right-side coach panel should stay quiet before the first attempt and become more useful after speech input exists.

- **Coach panel is bounded, not open-ended**  
  The coach panel should not behave like a generic AI chat. It should serve the current mission loop through transcript, positive anchor, one upgrade, better phrase, retry target, and save/reuse prompt.

- **Messy speech becomes a clear next step**  
  Inspired by Granola, the product should transform an imperfect spoken answer into concise feedback and one retry target.

- **One priority fix per retry**  
  The learner should not receive a long list of corrections. The next attempt should focus on one meaningful improvement.

- **Quiet effort recognition**  
  Inspired by Headspace, mission completion can include a small emotional closure moment after meaningful effort, such as a coach note or quote card.

- **Failure states preserve dignity**  
  If the learner is silent, stuck, unclear, or affected by a provider failure, the product should make the task smaller and preserve effort instead of implying the learner failed.

#### Visual Patterns

- **Calm focus over bright gamification**  
  Visual design should feel mature, private, and workplace-relevant. Avoid childish reward systems, noisy badges, or competitive visuals.

- **Feedback as coaching card, not report card**  
  Feedback should be visually compact and structured around one strength, one upgrade, one better phrase, and one retry action.

- **Low-pressure recording states**  
  Recording UI should be clear but not alarming. Avoid visual language that makes speaking feel like a high-stakes test.

- **Small visible improvement**  
  After retry, the product should show a specific improvement cue within seconds, such as “clearer opening,” “more natural ending,” “stronger interview tone,” or “useful phrase saved.”

- **Completion with evidence**  
  Completion screens should show proof of effort: retry completed, phrase saved, answer clearer, confidence changed, or one sentence now reusable.

### Anti-Patterns to Avoid

- **Score-first speaking evaluation**  
  Do not lead with pronunciation scores, fluency grades, red marks, or performance dashboards. These may increase anxiety and reduce willingness to retry.

- **Native-speaker perfection framing**  
  SpeakFit must avoid suggesting that the learner needs to erase their accent. The product should focus on clarity, confidence, structure, and workplace usefulness.

- **Overcorrection after a vulnerable attempt**  
  Do not list every error after a learner speaks. Too much correction can make retry feel like punishment.

- **Generic AI chat as the core experience**  
  Open-ended voice chat can overwhelm B1 learners and weaken the structured learning loop. SpeakFit should remain mission-led.

- **Passive transcript productivity tool**  
  Transcripts and summaries are useful, but the product must not let users avoid speaking by turning the session into reading, editing, or note management.

- **Content-library sprawl**  
  Too many courses, videos, quote cards, paths, or categories will slow the first value moment and dilute the daily speaking loop.

- **Gamification that rewards collecting over speaking**  
  Streaks, coins, maps, shops, rarity, unlock trees, and strong collection mechanics should not define MVP motivation.

- **Wellness tone without practical progress**  
  Calm emotional design should support concrete workplace/interview speaking improvement, not replace it.

- **Quiet Gift as decoration**  
  Quote cards and coach notes should not become empty positivity or collectible content. They should recognize meaningful speaking effort and support return behavior.

- **Failure states that erase effort**  
  Mic, network, AI, STT, or TTS problems should not make the user feel the practice session is lost. Recovery options must preserve momentum where feasible.

- **Failure states that blame the learner**  
  If audio is unclear, STT fails, or the learner says very little, the product should avoid making the learner feel that their voice is the problem.

### Architecture and UX Implications

The selected inspiration sources create several UX constraints that should inform downstream architecture.

1. **Attempt-based architecture**  
   The product should model each speaking attempt and retry explicitly. The UX depends on being able to connect prompt, attempt, transcript or manual text, feedback, retry focus, saved phrase, and completion state.

2. **Transcript and feedback are side-panel artifacts**  
   Transcript, feedback, and suggested rewrite should support the speaking loop. They should not become the product’s primary activity.

3. **Latency is emotional design**  
   Waiting after speaking can feel like being judged. Processing states should be calm, meaningful, and recoverable. The product should show that effort was received, explain what is happening, and offer fallback paths if processing takes too long.

4. **Privacy is visible**  
   Microphone state, recording behavior, audio/transcript storage, delete affordances, and provider-use explanations should be visible enough that learners understand the practice space is private.

5. **Feedback must be specific but non-shaming**  
   The system should prefer practical language such as “clearer,” “more natural,” “easier to understand,” or “stronger for interview” over native-speaker comparison or harsh correction.

6. **AI calls stay bounded**  
   The MVP should avoid AI-everywhere behavior. A structured feedback call per meaningful attempt, with retry suggestion included where feasible, is more aligned with the MVP than always-on open-ended coaching.

7. **Failures preserve effort**  
   The pipeline should avoid losing the whole attempt if one provider step fails. Recording, transcript, feedback, retry suggestion, and quiet gift should be treated as separate stages where feasible.

### Validation Questions

The inspiration strategy should be treated as a set of assumptions to validate, not proven truth.

- Do Vietnamese A2-high/B1 professionals prefer a next-attempt instruction over a visible pronunciation score?
- Does score-first feedback reduce willingness to retry?
- Does a calm desktop workspace increase completed speaking attempts per session?
- Does the coach panel help users speak again, or does it pull them into passive reading?
- Does the Quiet Gift moment increase completion satisfaction and next-day return, or does it feel decorative?
- Does accent-neutral language such as “clearer,” “more natural,” and “easier to understand” reduce anxiety?
- Does desktop-first practice fit interview/workplace preparation, or does it create activation friction compared with mobile?
- Do users understand and trust mic, audio, transcript, and AI-provider handling from the UX copy?

### Design Inspiration Strategy

#### What to Adopt

- From **ELSA Speak**, adopt the short speaking practice loop, microphone clarity, repeat/retry behavior, and small actionable feedback.
- From **Granola**, adopt the calm desktop workspace, AI sidekick behavior, session artifact model, and transformation of messy input into structured output.
- From **Headspace**, adopt emotionally safe copy, low-pressure session framing, warm completion moments, and non-shaming return behavior.

#### What to Adapt

- Adapt ELSA’s pronunciation feedback into a broader workplace/interview communication coach. SpeakFit feedback should include clarity, structure, usefulness, and one better phrase, not only pronunciation accuracy.
- Adapt Granola’s transcript/artifact pattern into learning artifacts: feedback, retry target, saved phrase, reuse prompt, and confidence cue.
- Adapt Headspace’s completion ritual into SpeakFit’s Quiet Gift Layer: a small optional quote or coach note after meaningful speaking effort, never a reward economy.
- Adapt session-based calmness into a faster active practice loop. SpeakFit should feel safe but still action-oriented.

#### What to Avoid

- Avoid copying ELSA’s score-heavy or streak-heavy patterns when they create pressure instead of confidence.
- Avoid copying Granola’s passive capture model too literally; SpeakFit must keep pushing toward spoken retry.
- Avoid copying Headspace’s wellness/content-library model too broadly; SpeakFit must stay practical, career-relevant, and mission-based.
- Avoid any inspiration pattern that hides the core MVP behavior: speak, receive feedback, retry, save/reuse useful language, and see small progress.

The guiding strategy is to make SpeakFit feel like a private desktop speaking coach: as practical as a speaking tool, as calm as a focused AI workspace, and as emotionally safe as a gentle coaching product.

## Step 6 — Design System Choice

**Purpose:** Choose the design system foundation, frontend UI/state support boundaries, customization strategy, and implementation guardrails for AI agents.

## Design System Foundation

### Design System Choice

SpeakFit should use a themeable design system foundation:

**Tailwind CSS + shadcn/ui/Radix-style primitives + custom SpeakFit design tokens.**

This approach provides a strong balance between implementation speed, accessibility, consistency, and emotional differentiation. SpeakFit should not build a fully custom design system for MVP, and it should avoid adopting a visually heavy established system such as Ant Design or default Material Design without significant customization.

The recommended brand direction is:

**Hybrid: calm professional + warm coach.**

The interface should feel like a focused desktop learning workspace for adults, while still carrying the warmth and psychological safety of a private coach. It should not feel like a children’s gamified learning app, a generic admin dashboard, a high-pressure testing platform, or a vague wellness product.

### Rationale for Selection

#### Why a themeable system fits SpeakFit

SpeakFit needs to move quickly through MVP while preserving enough visual and emotional control to support its core promise: private workplace/interview speaking practice that feels safe, focused, and actionable.

A themeable foundation is the best fit because it supports:

1. **MVP speed**  
   Tailwind and shadcn-style components allow AI coding agents to implement screens quickly without designing every primitive from scratch.

2. **Accessibility foundation**  
   Radix-style primitives provide a better base for dialogs, popovers, tabs, dropdowns, focus management, and keyboard interactions than fully custom components.

3. **Desktop-first workspace flexibility**  
   Tailwind works well for the three-zone practice layout:
   - Mission context
   - Speaking stage
   - Coach panel

4. **Emotional differentiation**  
   Custom tokens can make SpeakFit feel calm, private, warm, and professional rather than generic SaaS or enterprise software.

5. **AI-agent consistency**  
   A clear component and token strategy reduces UI drift when AI agents implement multiple screens. Agents should reuse shared primitives instead of inventing new visual patterns per feature.

6. **Portfolio defensibility**  
   The choice is easy to explain in an interview: it balances speed, accessibility, maintainability, and brand expression for a solo PM + AI-agent MVP.

#### Why not a fully custom design system for MVP

A fully custom design system would provide maximum uniqueness, but it is not the right trade-off for the MVP. It would increase implementation time, component maintenance, accessibility risk, and agent inconsistency before the core speaking loop is validated.

SpeakFit should reserve deeper custom component work for patterns that are genuinely product-defining, such as the recording control, coach feedback card, retry comparison, saved phrase card, and quiet gift card.

#### Why not a default established system

Established systems such as Ant Design or default Material Design provide speed and component coverage, but their default visual language may conflict with SpeakFit’s desired emotional response.

Risks include:

- Looking like an admin dashboard or enterprise tool.
- Feeling too generic or transactional for vulnerable speaking practice.
- Carrying default visual density that conflicts with a calm learning workspace.
- Making the product harder to differentiate in portfolio screenshots.

SpeakFit can borrow proven interaction patterns from established systems, but it should not inherit their default visual identity.

### Implementation Approach

The implementation approach should separate five layers:

1. **Design tokens**  
   Define the base visual language:
   - Color tokens
   - Typography scale
   - Spacing scale
   - Radius
   - Elevation/shadow
   - Focus states
   - Motion principles
   - Semantic state colors

2. **Primitive components**  
   Use accessible shadcn/Radix-style primitives for:
   - Button
   - Input
   - Textarea
   - Dialog
   - Popover
   - Tabs
   - Tooltip
   - Card
   - Badge
   - Progress
   - Toast
   - Dropdown
   - Form controls

3. **SpeakFit product components**  
   Create domain-specific components only where the product needs them:
   - Mission context card
   - Speaking stage
   - Recording control
   - Audio replay control
   - Coach feedback card
   - Retry focus card
   - Saved phrase card
   - Attempt timeline
   - Progress evidence card
   - Quiet gift / coach note card
   - Fallback recovery panel
   - Mic permission and consent prompt

4. **Client UI state**  
   If the frontend stack uses React, lightweight client/global UI state can be managed with **Zustand** where appropriate.

   Zustand is suitable for local or cross-component UI state such as:
   - Current mission UI state
   - Recording state
   - Coach panel visibility
   - Current attempt and retry UI flow
   - Onboarding/welcome modal state
   - User interface preferences
   - Temporary non-server state during a practice session

5. **Client server-state fetching and caching**  
   Use **React Query / TanStack Query** for client-side data fetching, caching, synchronization, invalidation, and mutation state where the React frontend needs server data.

   React Query / TanStack Query is suitable for:
   - Fetching missions
   - Loading attempts and retry history
   - Fetching transcripts and feedback status
   - Managing saved phrases
   - Loading progress history
   - Handling mutation states for save phrase, submit attempt, retry feedback, delete attempt, or mark phrase reused
   - Refetching and cache invalidation after practice actions

   Client/server-state boundaries should remain clear: Zustand should not become the primary store for persisted server data. Server-fetched data such as missions, attempts, transcripts, feedback, saved phrases, and progress history should be managed through React Query / TanStack Query or the chosen server-state layer rather than duplicated in global client state.

### Customization Strategy

#### Visual Direction

SpeakFit should use a **calm professional + warm coach** visual direction.

The interface should communicate:

- Private practice space.
- Adult learner respect.
- Calm focus.
- Workplace/interview relevance.
- Gentle encouragement.
- Clear next action.

It should avoid:

- Childish gamification.
- Harsh test-prep visuals.
- Enterprise dashboard coldness.
- Wellness vagueness.
- Overly bright reward UI.
- Dense analytics-first layouts.

#### Design Token Direction

Recommended token direction:

- **Color:** muted neutral base with warm accent colors. Use color to guide attention, not decorate heavily.
- **Typography:** highly readable, adult, calm. Avoid playful or overly academic type choices.
- **Spacing:** generous desktop spacing around the speaking stage to reduce pressure and clutter.
- **Radius:** soft but not childish. Cards should feel approachable and professional.
- **Elevation:** subtle depth for mission cards, coach panels, and quiet gift cards.
- **Motion:** restrained and purposeful. Use motion for state changes, recording transitions, feedback arrival, and completion moments, not for entertainment.
- **Focus states:** visible and accessible, especially for recording, retry, save phrase, and fallback actions.
- **Semantic colors:** avoid red-heavy correction. Use calm warning/error states that explain recovery instead of signaling failure.

#### Component Tone

Core components should express the emotional principles from previous steps:

- **Recording controls** should feel clear and safe, not alarming.
- **Feedback cards** should look like coaching guidance, not report cards.
- **Retry CTAs** should feel like a small next step, not a retest.
- **Saved phrase cards** should feel like personal speaking assets, not vocabulary collectibles.
- **Quiet gift cards** should feel optional and private, not like gamified rewards.
- **Error/fallback panels** should preserve dignity and momentum.

#### Guardrails for AI Agents

To prevent UI drift during implementation, future coding agents should follow these guardrails:

1. Reuse shared primitives before creating new UI.
2. Use design tokens instead of one-off colors or spacing.
3. Keep the speaking stage as the visual priority during practice.
4. Keep coach panel content bounded to the mission loop.
5. Avoid score-first or red-error-heavy visual treatment.
6. Avoid adding gamified reward components unless explicitly promoted into scope.
7. Treat accessibility and keyboard interaction as baseline requirements.
8. Keep desktop-first layout quality high while preserving readable responsive behavior.

#### Canvas-to-Production UI Contract Update

A preferred visual direction has now been captured as a frozen Cursor Canvas reference and a production mapping contract:

- `docs/ui-ux/speakfit-quiet-studio-reference.md` preserves the desired Quiet Studio app shell, page structure, mission loop, and interaction states.
- `docs/ui-ux/shadcn-tailwind-implementation-contract.md` translates the Canvas roles into production `shadcn/ui` + Tailwind wrapper guidance.
- `.cursor/rules/speakfit-ui-ux-reference.mdc` and `.cursor/rules/speakfit-shadcn-ui-contract.mdc` make this guidance persistent for future AI agents.

This means implementation agents do not need to know `cursor/canvas` internals. They should treat Canvas component names as semantic roles and recreate them with project-owned production wrappers built on `shadcn/ui`, Tailwind tokens, and the SpeakFit design language.

The implementation plan should therefore include an early frontend foundation story for a SpeakFit UI kit before building full learner pages. That story should create the wrapper layer for shell, card, layout, pill, stat, typography, progress, voice waveform, coach feedback, and mission step navigation components so later stories can preserve the approved UI/UX consistently.

## Step 7 — Defining Core Experience

**Purpose:** Define the product-defining interaction, user mental model, success criteria, novel UX patterns, and detailed mechanics for the retry improvement moment.

## 2. Core User Experience

### 2.1 Defining Experience

The defining experience of SpeakFit is helping a learner complete one realistic speaking rehearsal:

```text
Real prompt → rough spoken answer → one safe coaching cue → immediate retry → clearer reusable sentence
```

In user language, the experience should be easy to describe:

> “It gives me a real interview/workplace prompt, I answer out loud, and it helps me say it better.”

If SpeakFit gets one thing perfectly right, it should be the **retry improvement moment**: the learner says an imperfect first answer, receives one specific and non-shaming upgrade, retries immediately, and feels the second version is clearer, stronger, more natural, or more workplace-ready.

The product should make the learner feel:

```text
I said it once.
I understood one thing to improve.
I said it better.
I can use this sentence again.
```

This is more important than lesson volume, pronunciation scoring, AI chat flexibility, content library depth, gamification, or visual polish. The MVP should be designed around making this moment happen quickly and repeatedly.

A concise interaction promise for SpeakFit is:

```text
Speak one rough answer. Retry one stronger version.
```

Or, in a more complete form:

```text
Say it once → get one useful upgrade → say it better → keep the sentence.
```

### 2.2 User Mental Model

The target mental model is:

```text
Private rehearsal room with a coach.
```

This mental model combines three expectations:

1. **Private** — the learner can practice vulnerable speaking moments without social judgment, public comparison, or pressure to sound perfect.
2. **Rehearsal room** — the prompts should feel like realistic preparation for interviews, meetings, vendor conversations, project explanations, standups, updates, or workplace situations.
3. **Coach** — the product should not merely record, score, or chat. It should listen to an attempt, identify one useful improvement, and help the learner try again.

Users may currently solve this problem by:

- Practicing alone with written notes.
- Watching YouTube lessons passively.
- Asking ChatGPT for sample answers but not saying them out loud.
- Using pronunciation apps that focus on sounds and scores.
- Taking classes or tutoring sessions, which may be expensive, scheduled, or socially stressful.
- Avoiding speaking practice until a real interview or meeting forces them to speak.

The mental gap SpeakFit must close is that many learners understand English better than they can speak it under pressure. They do not only need more content; they need a safe loop that turns passive knowledge into spoken output.

The expected user thought process should become:

```text
I do not need to prepare a perfect answer.
I just need to try one rough version.
The coach will help me improve one thing.
Then I can say it again better.
```

Potential confusion or frustration points include:

- Not knowing what prompt to practice.
- Feeling embarrassed before the first recording.
- Thinking feedback is judging pronunciation rather than helping communication.
- Receiving too many corrections at once.
- Waiting too long for AI/STT feedback after speaking.
- Seeing transcript or analysis but not knowing exactly what to retry.
- Saving phrases without knowing when to reuse them.
- Feeling that failure states are caused by the learner’s bad speaking rather than system limitations.

The UX should resolve these with a ready mission, low-pressure recording, explicit privacy reassurance, concise coaching, one retry target, visible improvement, and clear fallback paths.

### 2.3 Success Criteria

The core experience succeeds when a learner can move from hesitation to an improved spoken answer in one focused session.

Success criteria:

1. **Fast start**  
   The learner reaches a relevant default mission quickly without browsing a large course library or writing their own prompt.

2. **Safe first attempt**  
   The learner understands that a rough answer is expected and acceptable. The UI makes speaking feel private, short, and low-pressure.

3. **Clear speaking action**  
   The learner always knows the next action: listen, shadow, record, stop, replay, get feedback, retry, save, or finish.

4. **Specific coaching cue**  
   Feedback identifies one useful improvement instead of overwhelming the learner with a long report.

5. **Immediate retry**  
   The retry action is directly connected to the feedback. The learner should not need to interpret the feedback and invent the next step alone.

6. **Visible improvement**  
   After retry, the learner sees or feels that the second version improved in a specific way, such as clearer opening, stronger interview tone, more natural sentence, better structure, or more useful phrase.

7. **Reusable language**  
   The session should produce at least one sentence, phrase, or answer snippet that can be saved and reused in a future interview/workplace situation.

8. **Dignified recovery**  
   If mic, STT, AI, TTS, network, or user hesitation causes problems, the product should preserve momentum and avoid making the learner feel at fault.

9. **Return motivation**  
   The learner should leave with a reason to return: a saved phrase to reuse, a next mission, a quiet coach note, or visible evidence of practice progress.

The user should say “this just works” when:

```text
I did not need to know what to practice.
I spoke one answer.
The app told me exactly how to make it better.
I retried immediately.
I left with a sentence I can actually use.
```

### 2.4 Novel UX Patterns

SpeakFit mostly combines established UX patterns in a product-specific way rather than requiring a completely novel interaction model.

Established patterns to adopt:

- **Guided practice prompt** — familiar from language learning and interview prep.
- **Voice recording and replay** — familiar from speaking apps and messaging tools.
- **Coach feedback card** — familiar from learning products, but adapted away from score-first reporting.
- **Side-panel assistant** — familiar from modern AI workspaces, but bounded to the mission loop.
- **Save for later** — familiar from bookmarks and notes, but reframed as save for spoken reuse.
- **Completion moment** — familiar from habit and wellness products, but tied to meaningful speaking effort.

The unique SpeakFit combination is:

```text
Private rehearsal prompt
+ voice attempt
+ one non-shaming coaching cue
+ immediate retry
+ reusable workplace sentence
```

This combination should feel familiar enough to learn quickly, but distinct enough to differentiate SpeakFit from pronunciation-score apps, generic AI tutors, passive video lessons, and note-taking tools.

Novel or product-defining patterns:

1. **Retry as the main value moment**  
   Feedback is not the endpoint. Feedback is a launcher for a better spoken attempt.

2. **Coach mirror side panel**  
   The coach panel reflects what the learner said, what worked, what to improve, and what to try next. It is not a generic chatbot.

3. **Save for spoken reuse**  
   Saved phrases are not vocabulary collectibles. They are personal speaking assets meant to return in later missions.

4. **Quiet Gift after effort**  
   Motivation appears as emotional closure after meaningful practice, not as a reward economy or content destination.

5. **Failure states that protect the speaker**  
   When speech is unclear, silence happens, or providers fail, the system should make the task smaller and preserve dignity.

The guiding principle remains:

> **Correct the sentence, protect the speaker.**

### 2.5 Experience Mechanics

#### 1. Initiation

The learner begins from a ready mission rather than a blank prompt box.

The mission should show:

- Situation context.
- Speaking goal.
- Expected answer length.
- Professional track relevance.
- Optional helper phrases or starter sentence.
- Clear primary CTA to start speaking or listen/shadow first.

The initiation moment should answer:

```text
What am I practicing?
Why is this useful?
How long should I speak?
What should I do first?
```

Recommended primary entry:

```text
Start today’s mission
```

Secondary supports may include:

- Listen to sample.
- Shadow first.
- Use starter sentence.
- Type instead if mic is unavailable.

#### 2. Interaction

The learner records or submits a first attempt.

During the attempt, the UI should:

- Keep the speaking stage visually central.
- Show clear recording state.
- Avoid intimidating timers or performance language.
- Make stop/retry/replay controls obvious.
- Keep helper text visible but not distracting.
- Support manual text fallback if recording or STT fails.

The first attempt should be framed as a rough rehearsal, not a test.

Example copy direction:

```text
Try a rough version first. We’ll make it stronger after.
```

After recording, the system processes the attempt and prepares feedback. Processing should feel calm and practical:

```text
Got it. I’m finding one useful upgrade for your next attempt.
```

#### 3. Feedback

The coach panel becomes active after an attempt exists.

The feedback card should include:

1. **Positive anchor** — what the learner communicated successfully.
2. **One upgrade** — the single most useful improvement for the next attempt.
3. **Try this version** — a better phrase, sentence, or answer frame.
4. **Retry focus** — a concrete instruction for the next spoken attempt.
5. **Retry CTA** — the next action to record the improved version.

Example feedback structure:

```text
You communicated the main idea: your project helped users save time.

One upgrade:
Make the result more specific.

Try this version:
“In my last project, I improved the checkout flow so users could complete payment with fewer steps.”

Retry focus:
Say it again with the result at the end.
```

Feedback should avoid:

- Long grammar reports.
- Red-error-heavy layouts.
- Native-speaker comparison.
- Too many corrections.
- Score-first presentation.
- Vague AI encouragement without a retry instruction.

#### 4. Retry

Retry should be immediate and small.

The retry CTA should make the action feel achievable:

```text
Record the stronger version
```

or:

```text
Try a 20-second upgrade
```

During retry, the user should see the retry focus, not the full feedback report. The goal is to reduce cognitive load and guide one concrete improvement.

After retry, the product should show a small visible improvement cue:

```text
Clearer result statement
```

```text
Stronger interview tone
```

```text
More natural closing sentence
```

```text
Useful phrase saved
```

The product does not need a complex score dashboard for MVP. The key is that the learner can feel one improvement.

#### 5. Completion

A mission can complete when the learner has made meaningful speaking effort, ideally:

```text
First attempt + feedback + retry
```

A stronger completion includes:

```text
First attempt + feedback + retry + saved/reusable phrase
```

Completion should show:

- Mission completed.
- Retry completed.
- One visible improvement.
- One reusable phrase or sentence.
- Optional quiet gift / coach note.
- Next suggested action.

The completion moment should not distract from learning. It should close the loop emotionally:

```text
You made one answer clearer today.
```

The user should leave with a sense of ownership:

```text
This is now a sentence I can use.
```

#### 6. Recovery

Recovery mechanics are part of the defining experience because speaking practice is vulnerable and technically fragile.

If the learner is silent or stuck:

```text
That was a hard prompt. Let’s make it smaller.
```

Then offer:

- Starter sentence.
- Shorter prompt.
- Idea chips.
- Shadow sample.
- Type-first fallback.

If STT or AI fails:

```text
Your effort is saved. Detailed coaching is taking longer than expected.
```

Then offer:

- Replay attempt.
- Retry analysis.
- Use manual transcript.
- Continue with a simpler retry prompt.
- Save attempt for later.

If mic permission is denied:

- Explain why mic access helps.
- Offer browser permission guidance.
- Provide manual text fallback.
- Avoid blocking all learning.

The recovery rule:

```text
Never let a technical failure or hesitant first attempt make the learner feel personally judged.
```

#### 7. Saved Reuse

When a useful phrase appears, the product should offer save-for-reuse.

Saved phrase context should include:

- Phrase or improved sentence.
- Original mission context.
- Use case.
- Retry or feedback source.
- Future reuse prompt.

The save interaction should communicate:

```text
Keep this for a future answer.
```

Not:

```text
Add to vocabulary list.
```

Saved phrases should return in later missions as prompts to speak, not just as passive review items.

#### 8. Quiet Gift

Quiet Gift should appear only after meaningful effort, not before or during the core loop.

Appropriate triggers:

- Completed first attempt + retry.
- Saved a reusable phrase.
- Completed a short mission after hesitation.
- Returned and completed another session.

The quiet gift should feel like a private coach note:

```text
You stayed with the sentence until it became yours.
```

It should remain optional and dismissible:

- Save note.
- Continue.
- Practice another sentence.

Quiet Gift must not become the defining experience. The defining experience is still the retry improvement moment.

## Related

- [[product-brief|Product Brief]] — Discovery boundary.
- [[prd|PRD]] — requirement source of truth.
- [[architecture|Architecture]] — technical decisions kế thừa UX này.
- [[DESIGN|DESIGN — Quiet Studio]] — design thesis.
- [[speakfit-quiet-studio-reference|Quiet Studio Reference]] — frozen Canvas reference.
- [[shadcn-tailwind-implementation-contract|Shadcn/Tailwind Implementation Contract]] — production mapping.
- [[docs/ui-ux/README|UI/UX README]] — entry cho UI/UX folder.
- [[BMAD_SPEAKFIT_WORKFLOW|BMAD SpeakFit Workflow]].
- [[decisions|Decision Log]] — Quiet Gift, desktop-first.
- [[raid|RAID Log]] — RAID-004 Quiet Gift drift.
- [[docs/INDEX|Repo Index]].
