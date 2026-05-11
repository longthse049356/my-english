# SpeakFit Quiet Studio UI/UX Reference

This folder stores the canonical UI/UX reference prototype for SpeakFit English.

## Reference files

- `speakfit-quiet-studio-reference.md` — frozen UI/UX reference copied from the Cursor preview canvas.
- `shadcn-tailwind-implementation-contract.md` — production mapping from Canvas roles to `shadcn/ui` + Tailwind wrappers.

## How AI agents should use this reference

Before creating or modifying learner-facing UI, read these files in order:

1. `_bmad-output/planning-artifacts/prd.md`
2. `DESIGN.md`
3. `docs/ui-ux/speakfit-quiet-studio-reference.md`
4. `docs/ui-ux/shadcn-tailwind-implementation-contract.md`
5. `.cursor/rules/speakfit-ui-ux-reference.mdc`
6. `.cursor/rules/speakfit-shadcn-ui-contract.mdc`

The canvas is not production code. It is the visual and interaction reference for UI direction, color mood, layout shape, and product flow — not a pixel-perfect sizing specification for the production web app.

- app shell with compact sidebar and top navbar
- Quiet Studio visual direction
- desktop-first practice workspace
- onboarding, today mission loop, seeded missions, phrases, progress, settings, and operator views
- warm-up / shadow / record / feedback / fallback / complete mission states
- coach-style feedback, safe private practice tone, and saved phrase review/reuse

When implementing real UI, preserve the UX intent and visual hierarchy rather than copying Canvas SDK components directly. Use `shadcn-tailwind-implementation-contract.md` as the bridge from Canvas roles to production `shadcn/ui` + Tailwind components.

## Related

- [[speakfit-quiet-studio-reference|Quiet Studio Reference]] — frozen Canvas reference.
- [[shadcn-tailwind-implementation-contract|Shadcn/Tailwind Implementation Contract]] — production mapping.
- [[DESIGN|DESIGN — Quiet Studio]] — design thesis & visual system.
- [[prd|PRD]] — product scope & MVP boundary.
- [[ux-design-specification|UX Design Specification]] — UX flows & states.
- [[architecture|Architecture]] — frontend stack decisions.
- [[docs/INDEX|Repo Index]].
