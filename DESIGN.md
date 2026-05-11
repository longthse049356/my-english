---
version: final
name: SpeakFit Quiet Studio System
status: draft-for-stitch
created: 2026-05-08
source_context:
  product: SpeakFit English
  product_brief: _bmad-output/planning-artifacts/product-brief.md
  primary_screen: Daily Speaking Mission Workspace
  prior_direction_rejected: Warm cream + serif + terracotta felt outdated / 2015
  new_direction: Quiet Studio — modern private speaking practice cockpit
  target_user: Vietnamese professionals around A2-high to B1/B1+ preparing for interview
    and workplace communication
colors:
  surface: '#FFFFFF'
  surface-dim: '#d9d9e5'
  surface-bright: '#faf8ff'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f3f3fe'
  surface-container: '#ededf9'
  surface-container-high: '#e7e7f3'
  surface-container-highest: '#e1e2ed'
  on-surface: '#191b23'
  on-surface-variant: '#434655'
  inverse-surface: '#2e3039'
  inverse-on-surface: '#f0f0fb'
  outline: '#737686'
  outline-variant: '#c3c6d7'
  surface-tint: '#0053db'
  primary: '#004ac6'
  on-primary: '#ffffff'
  primary-container: '#2563eb'
  on-primary-container: '#eeefff'
  inverse-primary: '#b4c5ff'
  secondary: '#006b5f'
  on-secondary: '#ffffff'
  secondary-container: '#6df5e1'
  on-secondary-container: '#006f64'
  tertiary: '#3e3fcc'
  on-tertiary: '#ffffff'
  tertiary-container: '#585be6'
  on-tertiary-container: '#f1eeff'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#dbe1ff'
  primary-fixed-dim: '#b4c5ff'
  on-primary-fixed: '#00174b'
  on-primary-fixed-variant: '#003ea8'
  secondary-fixed: '#71f8e4'
  secondary-fixed-dim: '#4fdbc8'
  on-secondary-fixed: '#00201c'
  on-secondary-fixed-variant: '#005048'
  tertiary-fixed: '#e1e0ff'
  tertiary-fixed-dim: '#c0c1ff'
  on-tertiary-fixed: '#07006c'
  on-tertiary-fixed-variant: '#2f2ebe'
  background: '#faf8ff'
  on-background: '#191b23'
  surface-variant: '#e1e2ed'
  app-background: '#F7F8FA'
  background-gradient-start: '#F8FAFC'
  background-gradient-end: '#EEF4F7'
  surface-raised: '#F2F5F8'
  surface-muted: '#EEF3F6'
  surface-dark: '#111827'
  private-stage: '#17212B'
  voice-cyan: '#38BDF8'
  progress-emerald: '#34D399'
  encouragement-coral: '#FF6B4A'
  gentle-amber: '#F59E0B'
  text-primary: '#17202A'
  text-secondary: '#51606F'
  text-muted: '#7B8794'
  border-subtle: '#E5E7EB'
  border-strong: '#CBD5E1'
typography:
  display:
    fontFamily: Geist
    fontSize: 36px
    fontWeight: '700'
    lineHeight: '1.08'
    letterSpacing: -0.03em
  page-title:
    fontFamily: Geist
    fontSize: 28px
    fontWeight: '700'
    lineHeight: '1.15'
    letterSpacing: -0.02em
  mission-title:
    fontFamily: Geist
    fontSize: 22px
    fontWeight: '650'
    lineHeight: '1.25'
  prompt:
    fontFamily: Geist
    fontSize: 24px
    fontWeight: '600'
    lineHeight: '1.35'
    letterSpacing: -0.015em
  body:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: '1.55'
  body-small:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '400'
    lineHeight: '1.45'
  label:
    fontFamily: Geist
    fontSize: 12px
    fontWeight: '650'
    lineHeight: '1.2'
    letterSpacing: 0.08em
  button:
    fontFamily: Geist
    fontSize: 15px
    fontWeight: '650'
    lineHeight: '1'
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  gap-main: 24px
  page-padding: 32px
  rail-mission: 300px
  rail-coach: 360px
  stage-max-width: 760px
  unit: 4px
---

# SpeakFit English — DESIGN.md

## 1. Design Thesis

SpeakFit English should feel like a **modern private speaking studio for Vietnamese professionals**.

The product is not a generic English course, not an IELTS dashboard, not a chatbot wrapper, and not a children’s language game. It is a structured daily speaking practice workspace where a user opens the app, sees today’s mission, speaks or shadows, receives one useful coaching correction, retries, and feels a little more ready for real workplace or interview conversations.

The previous warm cream + serif + terracotta direction is rejected because it can feel like a 2015 wellness/editorial learning product. SpeakFit needs to feel more current, more product-native, more career-oriented, and more voice-first.

### Final visual concept

> **Quiet Studio** — a crisp 2026 desktop practice cockpit with cool-neutral surfaces, a focused private rehearsal stage, living voice waveform, concise coaching cards, and subtle confidence-building progress.

### Target feeling

- Private
- Focused
- Modern
- Career-grade
- Calm under pressure
- Youthful but not childish
- AI-assisted but not gimmicky
- Premium but not corporate
- Speaking-first, not dashboard-first

### Core design promise

> One mission. One speaking attempt. One practical improvement. One retry.

Every visual decision should serve that loop.

## 2. Product Context to Preserve

SpeakFit English is for Vietnamese working professionals who already have basic English knowledge but freeze or lose structure when speaking in interviews and workplace situations.

The MVP experience should prove this loop:

```text
Mission -> Warm-up -> Speak/Shadow -> Feedback -> Retry -> Save -> Progress
```

The primary screen is a desktop-first practice workspace. It should help the user answer:

1. What should I practice today?
2. What do I say now?
3. How did I do?
4. What one thing should I retry?

The UI should reduce speaking anxiety, not create performance pressure.

## 3. Design Principles

### 1. Speaking is the center

The microphone, waveform, prompt, phrase chunks, transcript, and retry action should be more prominent than dashboards, charts, lesson libraries, or chat.

### 2. Private before intelligent

Users must feel safe before they care that the app is AI-powered. Recording states, privacy reassurance, transcript control, and retry affordances are trust builders.

### 3. One next action

At every state, one action must dominate:

- Start practice
- Start shadowing
- Record answer
- Stop recording
- Listen back
- Get feedback
- Retry with coach tip
- Save phrase

Avoid showing many equal CTAs.

### 4. Gentle but practical feedback

Feedback should feel like a workplace speaking coach, not an examiner. One genuine strength, one important fix, one better phrase, one retry instruction.

### 5. Modern warmth, not vintage warmth

Warmth should come from microcopy, pacing, coaching tone, subtle encouragement, and small human details — not from beige, serif typography, or terracotta-heavy palettes.

### 6. Portfolio-grade polish

The UI should look strong enough to demo in a portfolio or interview: modern, coherent, defensible, and clearly tied to the product strategy.

## 4. Visual Direction

### Metaphor

Use this metaphor:

> A private voice-practice cockpit for career-focused speaking improvement.

Do not use these metaphors:

- Cozy journal
- Classroom worksheet
- IELTS test center
- Chatbot conversation
- Gamified kids app
- Corporate analytics dashboard
- Wellness meditation app

### Mood words

Use:

- Crisp
- Focused
- Calm-tech
- Private studio
- Voice-first
- Professional confidence
- Fresh neutral
- Subtle energy
- Controlled glow
- Concise coaching

Avoid:

- Cozy
- Vintage
- Earthy
- Handmade
- Literary
- Academic
- Cute
- Magical AI
- Mascot-driven
- Dashboard-heavy

## 5. Color System

### Direction

Use a **cool-neutral modern base** with **fresh blue/teal/indigo accents**. Add warm coral/amber only as a tiny encouragement accent.

The interface should feel cleaner and more 2026-native than cream/editorial UI.

### Recommended palette

```yaml
colors:
  app-background: "#F7F8FA"
  app-background-gradient-start: "#F8FAFC"
  app-background-gradient-end: "#EEF4F7"
  surface: "#FFFFFF"
  surface-raised: "#F2F5F8"
  surface-muted: "#EEF3F6"
  surface-dark: "#111827"
  surface-dark-elevated: "#1E293B"
  private-stage: "#17212B"

  text-primary: "#17202A"
  text-secondary: "#51606F"
  text-muted: "#7B8794"
  text-on-dark: "#F8FAFC"
  text-on-dark-muted: "#B8C4CF"

  primary: "#2563EB"
  primary-hover: "#1D4ED8"
  voice-teal: "#14B8A6"
  voice-cyan: "#38BDF8"
  coach-indigo: "#6366F1"
  progress-emerald: "#34D399"
  encouragement-coral: "#FF6B4A"
  gentle-amber: "#F59E0B"

  border: "#E5E7EB"
  border-strong: "#CBD5E1"
  border-dark: "rgba(248, 250, 252, 0.12)"
  focus-ring: "#38BDF8"
```

### Usage rules

- Default shell: cool near-white or mist gradient.
- Cards: white surfaces with cool-gray borders.
- Rehearsal stage: can use a deep navy/slate private studio surface.
- Primary actions: blue, teal, or indigo.
- Recording state: cyan/teal glow, not red-dominant.
- Progress: emerald/teal.
- Encouragement: coral or amber sparingly.
- Errors: muted and technical only.

### Hard constraints

- Do not use terracotta as the primary CTA.
- Do not use cream/beige as the dominant identity.
- Do not use full-page rainbow gradients.
- Do not use pastel wellness palettes.
- Do not use harsh red/green correction visuals for language mistakes.

## 6. Typography

### Direction

Use a modern sans-serif product typography system. Avoid serif as the primary brand or UI voice.

Recommended fonts:

- Inter
- Geist
- Plus Jakarta Sans
- Manrope
- Satoshi
- IBM Plex Sans

Best practical default:

> **Geist or Inter** for the whole app, with Plus Jakarta Sans as an optional display flavor.

### Type hierarchy

```yaml
typography:
  display:
    fontSize: "36px"
    fontWeight: 700
    lineHeight: 1.08
    letterSpacing: "-0.03em"
  page-title:
    fontSize: "28px"
    fontWeight: 700
    lineHeight: 1.15
    letterSpacing: "-0.02em"
  mission-title:
    fontSize: "22px"
    fontWeight: 650
    lineHeight: 1.25
  prompt:
    fontSize: "24px"
    fontWeight: 600
    lineHeight: 1.35
    letterSpacing: "-0.015em"
  body:
    fontSize: "16px"
    fontWeight: 400
    lineHeight: 1.55
  body-small:
    fontSize: "14px"
    fontWeight: 400
    lineHeight: 1.45
  label:
    fontSize: "12px"
    fontWeight: 650
    lineHeight: 1.2
    letterSpacing: "0.08em"
    textTransform: uppercase
  button:
    fontSize: "15px"
    fontWeight: 650
    lineHeight: 1
```

### Prompt typography

The speaking prompt should be large, readable, and speakable — not literary.

Good prompt treatment:

- Sans-serif.
- 22–26px desktop.
- Break long text into phrase chunks.
- Use gentle emphasis for key phrases.
- Keep enough whitespace around the prompt.

Avoid:

- Decorative serif prompt.
- Long paragraph prompt.
- Tiny instruction text.
- Academic/exam wording.

## 7. Surface and Material System

### Overall feel

Modern, matte, spacious, and crisp.

Use:

- White cards.
- Cool-gray borders.
- Minimal shadows.
- Clear active states.
- Controlled voice glow only around speaking/recording areas.

Avoid:

- Huge soft shadows everywhere.
- 2015 floating card stacks.
- Heavy glassmorphism.
- Neumorphism.
- Paper/notebook textures.
- Faux classroom materials.

### Recommended radii

```yaml
radius:
  small: "8px"
  medium: "12px"
  large: "16px"
  stage: "24px"
  pill: "9999px"
```

Rules:

- Normal cards: 12–16px.
- Major stage container: 20–24px.
- Buttons: 12–14px or pill only for compact chips.
- Avoid giant 32px radius on every card.

### Recommended shadows

```yaml
shadow:
  card: "0 8px 24px rgba(15, 23, 42, 0.05)"
  stage: "0 24px 60px rgba(15, 23, 42, 0.14)"
  active-ring: "0 0 0 1px rgba(56, 189, 248, 0.45), 0 0 40px rgba(20, 184, 166, 0.18)"
```

Shadows should support hierarchy, not decoration.

## 8. Desktop Layout

### Core layout

Use a desktop-first three-area workspace where the center rehearsal area clearly dominates.

```text
┌─────────────────────────────────────────────────────────────┐
│ Top bar: SpeakFit / Interview English / Private mode / User │
├───────────────┬───────────────────────────────┬─────────────┤
│ Today / Track │     Rehearsal Stage           │ Coach Panel │
│ Mission       │     Prompt / Waveform / CTA   │ Feedback    │
│ Progress      │     Transcript / Retry        │ Phrase Tip  │
└───────────────┴───────────────────────────────┴─────────────┘
```

### Suggested proportions

- Left mission rail: 240–300px.
- Center rehearsal stage: 600–760px.
- Right coach panel: 320–380px.
- Max width: 1360–1440px.
- Main gap: 20–24px.
- Page padding: 24–32px.

### Hierarchy rules

- The center stage is the visual anchor.
- Side panels are supportive and quieter.
- Initial state should not show too much feedback before the user speaks.
- A user should understand the next action within 3 seconds.
- Avoid equal-weight dashboard columns.

### Navigation

Prefer a compact product shell:

- Left/top: SpeakFit logo.
- Track label: Interview English.
- Private mode indicator.
- Today’s mission status.
- Minimal settings/profile.

Avoid prominent tabs like a generic admin dashboard unless necessary.

## 9. Signature Moment: Private Voice Aura

The “wow” should come from making speaking practice feel alive, safe, and immediate — not from decorative gradients or mascots.

### Concept

When the user starts recording or shadowing, the center stage becomes a **private voice studio**:

- Deep slate/navy stage surface.
- Soft teal/cyan waveform aura.
- Large but calm mic control.
- Clear timer.
- Prompt remains visible in phrase chunks.
- Privacy reassurance stays near the action.
- Side panels visually quiet down.

### Idle state

- Light shell with central dark or elevated rehearsal card.
- Prompt visible.
- CTA: `Start practice` or `Record answer`.
- Microcopy: `Private practice. Retry before finishing.`

### Recording state

- Cyan/teal waveform responds visually.
- Timer visible but not stressful.
- CTA: `Stop when ready`.
- Copy: `Keep going — structure matters more than perfection.`
- Avoid red as the emotional anchor.

### Processing state

Use specific staged copy:

- `Transcribing your answer…`
- `Checking clarity and structure…`
- `Preparing one retry focus…`

Use skeleton feedback cards instead of a generic spinner.

### Feedback-ready state

Coach panel activates with:

1. What worked
2. One fix
3. Better phrase
4. Retry action

### Retry state

The stage should center the retry focus:

> This time: add one specific project result.

The previous answer is not shamed. The retry feels achievable.

## 10. Core Components

### Mission card

Purpose: tell the user why they are here today.

Content:

- Today’s mission title.
- Scenario.
- Goal.
- Skill focus.
- Estimated time.
- One useful phrase or sample opener.

Style:

- White or muted cool surface.
- 12–16px radius.
- Thin border.
- No heavy shadow.

### Rehearsal stage

Purpose: main speaking area.

Must include:

- Speaking prompt.
- Phrase chunks or shadowing lines.
- Mic/record control.
- Waveform or voice activity indicator.
- Timer.
- Transcript or answer area.
- Privacy reassurance.
- One dominant CTA.

### Recorder module

Use:

- Large circular mic button or modern rounded control.
- Teal/cyan active ring.
- Waveform bars or calm voice aura.
- Timer.
- Replay control after recording.

Avoid:

- Red emergency-style record button.
- Karaoke visual style.
- Podcast editor complexity.

### Coach feedback cards

Structure:

1. **What worked**  
   “Your answer had a clear beginning.”
2. **Fix one thing**  
   “Make the project result more specific.”
3. **Better phrase**  
   “I helped reduce onboarding time by creating a checklist for new team members.”
4. **Retry focus**  
   “Try again in 45 seconds. Include one measurable result.”

Style:

- Compact structured cards.
- Blue/teal/indigo accents.
- Amber only for gentle retry guidance.
- No red-heavy correction report.

### Phrase chips

Use for saved or suggested phrases:

- `I’m currently working as…`
- `My main strength is…`
- `In my last project…`

Style:

- Pill or compact chip.
- Light cool or warm-tinted surface.
- Context tag optional: `opening`, `strength`, `project`.
- Should feel like a professional toolkit, not flashcards for kids.

### Progress snapshot

Keep progress lightweight:

- Missions completed.
- Recordings made.
- Retries completed.
- Saved phrases.
- Confidence trend.

Avoid:

- Big grades.
- IELTS band score styling.
- Leaderboards.
- Complex charts on the main screen.

## 11. Feedback Tone and Copy

### Voice

Clear, supportive, practical, and non-judgmental.

Use:

- `Try this next.`
- `Good start — your answer has a clear direction.`
- `Make the example more specific.`
- `Repeat just this phrase.`
- `Your rhythm is close.`
- `Private practice. You can retry before finishing.`

Avoid:

- `Incorrect.`
- `Poor pronunciation.`
- `Low score.`
- `You failed to...`
- `Submit for evaluation.`
- `AI will grade your answer.`

### Bilingual support

Because the target user is Vietnamese professionals around A2-high/B1/B1+, the UI may use simple English for practice content and optional Vietnamese explanations for feedback clarity.

Keep bilingual support practical, not cluttered.

## 12. Motion and Micro-interactions

Use motion only where it supports the speaking loop.

Good motion:

- Waveform responds while recording.
- Active mic ring pulses gently.
- Feedback cards appear one by one.
- Saved phrase gives a small satisfying confirmation.
- Daily completion has a subtle progress glow.

Avoid:

- Confetti-heavy celebration.
- Mascot animation.
- Constant AI sparkles.
- Full-screen animated gradients.
- Distracting Lottie loops.

Motion should be calm, short, and optional for reduced-motion users.

## 13. Accessibility and Trust

### Anxiety-aware design

- Recording state must be obvious but not scary.
- User can retry without penalty.
- Typing fallback is always available.
- Feedback focuses on one improvement.
- Avoid public/social comparison.

### Technical trust

- Show privacy reassurance near recording.
- Allow edit transcript.
- Preserve work if STT or feedback fails.
- Use clear microphone permission states.
- Show audio quality gently:
  - `We can hear you.`
  - `Your room is a bit noisy, but you can continue.`

### Accessibility requirements

- WCAG 2.1 AA contrast.
- Keyboard-accessible recording controls.
- Visible focus states.
- Text labels for recording state, not color alone.
- Transcript visible and editable.
- Reduced-motion alternative.
- Body text at least 16px where possible.

## 14. Anti-patterns

Do not create:

- Generic SaaS analytics dashboard.
- Chatbot-first interface.
- IELTS/exam-prep dashboard.
- Children’s gamified language app.
- Mascot-heavy product.
- Corporate LMS.
- Wellness journal.
- Beige productivity dashboard.
- Course library as the main screen.
- Dense charts and scorecards.
- Red error-heavy correction UI.
- Robot mascot.
- AI sparkles as the main identity.
- Floating chat bubbles as the primary interaction.
- Stock illustrations of people speaking.
- Serif-led editorial styling.
- Terracotta primary buttons.
- Cream-heavy background.
- Huge soft shadows on every card.
- Glassmorphism overload.

## 15. Required Primary Mockup Content

### Top shell

- SpeakFit wordmark.
- Track: Interview English.
- Private mode indicator.
- Today’s mission status.
- Profile/settings minimal.

### Left mission area

**Today’s Mission**

**Interview: Tell me about yourself**

Scenario:

> You are speaking with a hiring manager in a first-round interview.

Goal:

> Give a clear 60-second answer about your background and strengths.

Focus:

> Past experience → key strength → role fit

Estimated time:

> 7 minutes

Useful phrases:

- “I’m currently working as…”
- “My main strength is…”
- “In my last project…”

### Center rehearsal stage

Prompt:

> Tell me about yourself and why this role is a good fit for you.

Support copy:

> Try a 45–60 second answer. Focus on being clear, not perfect.

Primary CTA:

> Record answer

Secondary:

> Can’t speak right now? Type your answer.

Privacy:

> Private practice. You can retry before finishing.

Recording state copy:

> Keep going — structure matters more than perfection.

Processing copy:

> Checking clarity and structure…

### Right coach panel empty state

> After your first attempt, your coach will give one useful improvement and a retry focus.

Today’s focus:

> Add one concrete project result.

### Right coach panel after attempt

**What worked**

> Your answer had a clear beginning.

**Fix one thing**

> Make the example more specific.

**Better phrase**

> In my last project, I helped reduce onboarding time by creating a checklist for new team members.

**Retry focus**

> Try again in 45 seconds. Include one measurable result.

CTA:

> Retry with this focus

Secondary actions:

- Edit transcript
- Save phrase
- Show details

### Small progress moment

> Small win: Your retry included a clearer project result.

## 16. Stitch Prompt — Full Screen Generation

Use this prompt when asking Stitch to create the updated UI:

```text
Design a desktop-first PWA screen for SpeakFit English, a private AI speaking rehearsal coach for Vietnamese professionals preparing for interviews and workplace English.

The interface should feel like a crisp 2026 private speaking studio: focused, modern, premium, calm under pressure, and career-oriented. It should not feel cozy, vintage, academic, classroom-like, wellness-oriented, or like a beige productivity dashboard.

Create a three-area desktop layout where the center rehearsal stage is dominant. Left side shows today's mission, track, goal, useful phrases, and lightweight progress. Center shows the active speaking prompt, phrase chunks, recorder, waveform, timer, transcript/answer area, and one primary CTA. Right side shows a concise coach panel with one strength, one improvement, one better phrase, and one retry instruction.

Visual style:
- Cool neutral app background, white surfaces, strong charcoal/navy text
- Fresh 2026 accents: electric blue, teal/cyan, or focused indigo
- Optional tiny coral/amber accent only for encouragement or retry guidance
- Modern sans-serif typography such as Inter, Geist, Plus Jakarta Sans, Manrope, or Satoshi
- No serif-led editorial styling
- 12–16px card radius, subtle cool-gray borders, minimal shadows
- Center rehearsal area may use a premium dark navy/slate private studio surface
- Speaking state should include a beautiful but restrained teal/cyan waveform or voice aura
- Spacious desktop layout with one obvious next action

Product details:
- Today’s mission: Interview: Tell me about yourself
- Prompt: Tell me about yourself and why this role is a good fit for you.
- Primary action: Record answer
- Privacy copy: Private practice. You can retry before finishing.
- Coach feedback structure: What worked, Fix one thing, Better phrase, Retry focus

Avoid:
- Cream or beige as dominant identity
- Terracotta primary buttons
- Decorative serif typography
- Robot mascot
- AI sparkles
- Floating gradient blobs
- Generic person illustrations
- Chatbot-first interface
- Dense equal-column dashboard
- IELTS/exam dashboard
- Children’s gamification, badges, coins, confetti, leaderboards
- Huge soft shadows or glassmorphism overload
- Red-heavy grammar correction visuals

The wow should come from making speaking practice feel alive and safe: a focused private rehearsal stage, responsive waveform, clear phrase chunks, smooth feedback cards, and a satisfying retry moment.
```

## 17. Stitch Prompt — Incremental Refinement

Use this if Stitch already has a screen and should not regenerate from scratch:

```text
Refine the existing SpeakFit screen without changing the core product flow. Keep the desktop three-area structure, but modernize the visual language away from the previous warm cream / serif / terracotta style.

Make it feel like a crisp 2026 private speaking studio for Vietnamese professionals preparing for workplace/interview English. Use a cool neutral app shell, white cards, charcoal/navy text, modern sans-serif typography, and fresh blue/teal/indigo accents. The center rehearsal stage should dominate and may use a premium dark navy/slate private studio surface with a restrained teal/cyan waveform aura.

Preserve the content hierarchy: mission context on the left, speaking prompt/recorder/waveform in the center, concise coach feedback on the right. Make the microphone, waveform, phrase chunks, transcript, and retry action more visually important than dashboards or navigation.

Avoid cream/beige dominance, terracotta CTA, decorative serif styling, chatbot layout, exam dashboard, gamification, mascot, AI sparkles, heavy glassmorphism, and dense analytics. The result should feel modern, private, focused, premium, career-oriented, and safe to speak in.
```

## 18. Quality Bar

If the UI looks like a “nice English learning app,” it is not enough.

It should look like:

- “I can rehearse an interview answer here.”
- “This is modern enough to trust with AI feedback.”
- “This is private and focused.”
- “This app understands speaking practice.”
- “This will help me improve before my next career opportunity.”

The new direction optimizes for credibility, momentum, and action — not just taste.

## Related

- [[product-brief|Product Brief]] — Discovery direction sản phẩm.
- [[prd|PRD]] — MVP boundary và functional requirements.
- [[ux-design-specification|UX Design Specification]] — UX flows, mission loop, fallback states.
- [[speakfit-quiet-studio-reference|Quiet Studio Reference]] — frozen Canvas reference.
- [[shadcn-tailwind-implementation-contract|Shadcn/Tailwind Implementation Contract]] — production mapping.
- [[docs/ui-ux/README|UI/UX README]] — entry point cho UI/UX folder.
- [[decisions|Decision Log]] — Quiet Gift, desktop-first và các quyết định liên quan UI.
- [[docs/INDEX|Repo Index]].