# SpeakFit Shadcn/Tailwind Implementation Contract

This document translates the frozen Cursor Canvas reference into production UI guidance for `shadcn/ui` + Tailwind CSS. Future agents do not need to know the internal implementation of `cursor/canvas`; they must preserve the visual hierarchy, spacing, interaction intent, and tone by using this contract.

## Source of truth order

Before implementing or changing UI, read these in order:

1. `_bmad-output/planning-artifacts/prd.md` — product scope and MVP boundaries.
2. `DESIGN.md` — Quiet Studio visual language and design principles.
3. `docs/ui-ux/speakfit-quiet-studio-reference.md` — frozen Canvas reference and interaction model.
4. `docs/ui-ux/shadcn-tailwind-implementation-contract.md` — this production mapping contract.
5. `.cursor/rules/speakfit-ui-ux-reference.mdc` and `.cursor/rules/speakfit-shadcn-ui-contract.mdc` — persistent agent rules.

## Core principle

The Canvas file is a reference prototype, not a component API. Production implementation should use project-owned UI wrapper components built on `shadcn/ui` primitives and Tailwind tokens. Do not import `cursor/canvas` in app code.

The required fidelity is **visual and interaction fidelity**, not pixel-perfect Canvas fidelity. Future implementation should preserve the UI direction, color mood, visual hierarchy, page layout shape, practice flow, and emotional tone. Exact pixel dimensions from the Cursor Canvas preview are not binding because the production web app will run in a different viewport, rendering environment, and responsive layout system.

Use the Canvas component names as semantic design roles:

- `Stack` means vertical rhythm.
- `Row` means aligned horizontal grouping.
- `Grid` means page or section layout.
- `Card`, `CardHeader`, `CardBody` mean quiet, rounded content surfaces.
- `Pill` means compact status, category, or state metadata.
- `Stat` means lightweight progress or operational metric.
- `H1`, `H2`, `H3`, `Text` mean a controlled typography scale.
- `Button` means one of the production button variants below.
- `useCanvasState` means normal React state, route state, persisted preference, or server state depending on the feature.
- `useHostTheme` means app theme tokens, not a runtime Canvas dependency.

## Fidelity target

This contract is not a pixel specification. Do not copy Canvas dimensions mechanically.

Preserve:

- Quiet Studio visual direction: calm professional + warm coach.
- Color mood: warm neutral surfaces, deep readable ink, calm blue active states, soft success/warning accents.
- Layout shape: compact sidebar, top navbar, and focused desktop practice workspace.
- Visual hierarchy: daily mission and rehearsal stage are primary; coach feedback supports the retry loop.
- Interaction model: guided mission loop, private recording, fallback path, phrase saving, review/reuse, lightweight progress.
- Emotional tone: private, safe, adult, encouraging, non-gamified.

Flexible in production:

- exact pixel widths, heights, padding, and border radii,
- exact Canvas preview proportions,
- exact responsive breakpoints,
- exact component internals,
- exact copy when product writing changes later.

Production developers should adapt spacing and sizing to the real web viewport while preserving the same perceived layout, mood, and flow.

## Recommended production UI kit

Create project-specific wrappers before building full pages. Suggested location:

- `src/components/speakfit/ui/`

Recommended wrapper components:

- `SpeakFitShell`
- `SpeakFitSidebar`
- `SpeakFitTopNav`
- `SpeakFitCard`
- `SpeakFitCardHeader`
- `SpeakFitCardBody`
- `SpeakFitStack`
- `SpeakFitRow`
- `SpeakFitGrid`
- `SpeakFitPill`
- `SpeakFitStat`
- `SpeakFitHeading`
- `SpeakFitText`
- `SpeakFitProgressBar`
- `SpeakFitVoiceWaveform`
- `SpeakFitCoachFeedback`
- `SpeakFitMissionStepNav`

These wrappers may be thin, but they make the visual system explicit and prevent each page from inventing its own Tailwind classes.

## Component mapping

| Canvas role | Production mapping | Required behavior |
| --- | --- | --- |
| `Button` | `shadcn/ui` `Button` with SpeakFit variants | Primary actions are calm ink/blue, secondary actions are soft neutral, destructive actions are rare and explicit. |
| `Card` | `shadcn/ui` `Card` via `SpeakFitCard` | Rounded quiet surface, subtle border, soft shadow, no heavy dashboard chrome. |
| `CardHeader` | `CardHeader` via `SpeakFitCardHeader` | Compact section title + optional metadata row. |
| `CardBody` | `CardContent` via `SpeakFitCardBody` | Consistent inner padding and vertical rhythm. |
| `Grid` | CSS grid/Tailwind via `SpeakFitGrid` | Desktop-first app shell and three-area workspace layouts. |
| `Row` | Flex row via `SpeakFitRow` | Aligned inline groups, actions, status clusters. |
| `Stack` | Flex column via `SpeakFitStack` | Vertical rhythm; avoid ad-hoc margin stacking. |
| `Pill` | Badge-like wrapper, optionally `shadcn/ui` `Badge` | Low-noise state labels such as `Warm-up`, `Private`, `Retry`. |
| `Stat` | Project wrapper using card/text primitives | Small metric with label, value, and optional supporting note. |
| `H1/H2/H3` | `SpeakFitHeading` variants | Controlled type scale; do not switch to generic landing-page hero typography. |
| `Text` | `SpeakFitText` variants | Muted coaching copy, readable line length, supportive tone. |
| `useCanvasState` | React state, URL state, persisted settings, or server state | Preserve interaction flow; choose persistence based on product requirement. |
| `useHostTheme` | Tailwind theme tokens and app theme provider | Preserve Quiet Studio tokens without Canvas runtime. |

## Tailwind visual tokens

Use these semantic token directions when defining Tailwind classes or CSS variables:

- App background: warm off-white / quiet neutral, not pure stark white.
- Primary ink: deep navy/charcoal for high readability.
- Accent: calm blue for active states and primary actions.
- Support accents: soft mint/sage for positive feedback, amber for gentle attention, muted rose only for destructive or sensitive warnings.
- Borders: low-contrast neutral lines.
- Shadows: soft, shallow, studio-like; avoid ecommerce/card-heavy shadows.
- Radius: medium-large rounded surfaces, typically `rounded-2xl` for cards and `rounded-full` for pills.
- Spacing: dense enough for productivity, calm enough for private practice. Prefer consistent `gap-*` over one-off margins.

## Layout contract

Production UI must preserve the Canvas app shape without copying exact Canvas preview dimensions:

1. Desktop-first PWA shell.
2. Compact left sidebar for product areas.
3. Top navbar for page title, status, and light account/context actions.
4. `Today` page as the main practice workspace.
5. Three-area `Today` layout:
   - mission rail on the left,
   - rehearsal stage in the center,
   - coach panel on the right.
6. Learner pages:
   - `Onboarding`
   - `Today`
   - `Missions`
   - `Phrases`
   - `Progress`
   - `Settings`
7. Internal/private testing page:
   - `Operator`, kept separate from learner flows.

## Mission loop contract

The `Today` experience must preserve this loop:

1. `Warm-up` — low-pressure setup and context.
2. `Shadow` — listen/read/repeat preparation.
3. `Record` — private speaking attempt.
4. `Feedback` — one strength, one fix, one better phrase, one retry action.
5. `Fallback` — manual text path when microphone/STT fails.
6. `Complete` — quiet closure, saved phrase prompt, confidence check.

Avoid replacing this with a chatbot-first blank prompt, a generic course page, or an exam/report-card flow.

## Page-level contracts

### Onboarding

Capture only enough to personalize early practice:

- user goal,
- confidence level,
- speaking context,
- preferred reminder or practice rhythm,
- privacy/provider notice.

### Today

Prioritize daily practice. The center of the page is the rehearsal stage, not analytics or navigation. Feedback must be supportive and actionable.

### Missions

Show seeded MVP missions and categories. Do not expand into a full course marketplace or infinite library unless the PRD changes.

### Phrases

Saved phrases must include:

- original context,
- better phrase,
- review action,
- reuse action.

### Progress

Keep progress lightweight:

- missions completed,
- attempts,
- retries,
- reused phrases,
- confidence 1–5,
- before/after evidence.

Avoid heavy scores, leaderboards, coins, streak pressure, or IELTS-style grading unless explicitly added to PRD.

### Settings

Include the MVP trust layer:

- microphone/data controls,
- provider notice,
- export/delete data,
- fallback/manual input preference.

### Operator

Keep this as an internal/private testing surface for mission templates, usage/cost visibility, and operational checks. Do not surface it as a normal learner page in production navigation unless gated.

## Suggested wrapper implementation style

When production code exists, implement wrappers using `cn()` and shadcn primitives. Example style direction:

```tsx
export function SpeakFitCard({ className, ...props }: React.ComponentProps<typeof Card>) {
  return (
    <Card
      className={cn(
        'rounded-2xl border border-slate-200/80 bg-white/85 shadow-sm shadow-slate-200/60',
        className,
      )}
      {...props}
    />
  );
}
```

This example is illustrative. Match actual project paths, theme tokens, and existing conventions when implementation begins.

## Agent checklist before FE implementation

Before coding a learner-facing UI change, confirm:

- The work reads PRD, `DESIGN.md`, Canvas reference, and this contract.
- The implementation uses project UI wrappers, not direct Canvas imports.
- The app shell, mission loop, visual mood, and page contracts remain intact unless the PRD explicitly changes.
- Exact Canvas pixel dimensions are not required; production sizing should fit the real web app viewport while preserving the same perceived layout and hierarchy.
- Any new Tailwind classes reinforce the Quiet Studio visual direction.
- Any deviation from the Canvas reference is documented as an intentional product/design decision.

## Related

- [[speakfit-quiet-studio-reference|Quiet Studio Reference]] — frozen Canvas source.
- [[DESIGN|DESIGN — Quiet Studio]] — design thesis & tokens.
- [[ux-design-specification|UX Design Specification]] — UX flows.
- [[prd|PRD]] — product scope.
- [[architecture|Architecture]] — frontend stack & wrappers location.
- [[docs/ui-ux/README|UI/UX README]] — folder entry point.
- [[docs/INDEX|Repo Index]].
