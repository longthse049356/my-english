---
doc_type: planning-canvas-index
stage: discovery
load_policy: read_index_then_one_shard
size_warning: normal
status: active
summary: "Planning canvas index for SpeakFit English. This file is now a shard map. Load one shard at a time via docs/planning/planning-questions/."
---

# Planning Questions — Personalized English Coach PWA

> **Lưu ý cho AI agents:** File này là **shard index** cho planning canvas. KHÔNG load full file này. Đọc index này để chọn đúng shard cần thiết, sau đó load chỉ 1 shard tại `docs/planning/planning-questions/`. Khi tạo Brief/PRD: ưu tiên §0, §1, §2, §3, §4, §15. Stack/architecture (§11) chỉ dùng làm reference cho Architecture phase, KHÔNG bake vào Brief. Sau khi BMAD Brief approved, file này chuyển sang `status: archived` để tránh decision drift.

## Shard Map

Content đã được chia thành 16 shard files để giảm token waste. Mỗi shard có frontmatter đầy đủ với `load_policy: on_explicit_request`.

| Section | Shard File | Summary | Size |
|---------|-----------|---------|------|
| §0 Tóm tắt hiện trạng | [00-summary.md](docs/planning/planning-questions/00-summary.md) | Product vision, positioning, and product principles | Normal |
| §1 Product Strategy | [01-product-strategy.md](docs/planning/planning-questions/01-product-strategy.md) | Product naming, positioning, differentiation, success metrics | Normal |
| §2 Target Users / Personas | [02-target-users-personas.md](docs/planning/planning-questions/02-target-users-personas.md) | Target user profiles, personas, and user segmentation | Normal |
| §3 MVP Boundary | [03-mvp-boundary.md](docs/planning/planning-questions/03-mvp-boundary.md) | MVP scope definition, feature inclusion/exclusion decisions | Large |
| §4 Core User Journey | [04-core-user-journey.md](docs/planning/planning-questions/04-core-user-journey.md) | End-to-end user journey, daily loop, and key interaction flows | Large |
| §5 Curriculum / Learning Plan | [05-curriculum-learning-plan.md](docs/planning/planning-questions/05-curriculum-learning-plan.md) | Learning curriculum structure, content organization | Normal |
| §6 Speaking / Shadowing | [06-speaking-shadowing.md](docs/planning/planning-questions/06-speaking-shadowing.md) | Speaking practice mechanics, shadowing drills | Normal |
| §7 AI / MiniMax / Feedback | [07-ai-minimax-feedback.md](docs/planning/planning-questions/07-ai-minimax-feedback.md) | AI feedback generation, rubric design, coaching tone | Normal |
| §8 Vocabulary / Notes / Review | [08-vocabulary-notes-review.md](docs/planning/planning-questions/08-vocabulary-notes-review.md) | Vocabulary saving, review queue, spaced repetition | Normal |
| §9 UX / UI | [09-ux-ui.md](docs/planning/planning-questions/09-ux-ui.md) | UX patterns, UI design decisions, interaction design | Normal |
| §10 Data / Privacy / Storage | [10-data-privacy-storage.md](docs/planning/planning-questions/10-data-privacy-storage.md) | Data handling, privacy policies, storage decisions | Normal |
| §11 Technical Architecture | [11-technical-architecture.md](docs/planning/planning-questions/11-technical-architecture.md) | Tech stack, architecture patterns, implementation decisions | Large |
| §12 Admin / Content Ops | [12-admin-content-ops.md](docs/planning/planning-questions/12-admin-content-ops.md) | Content management, admin tools, operational workflows | Normal |
| §13 Validation / Testing | [13-validation-testing.md](docs/planning/planning-questions/13-validation-testing.md) | Validation strategy, testing approach, success metrics | Normal |
| §14 Future Backlog | [14-future-backlog.md](docs/planning/planning-questions/14-future-backlog.md) | Future features, deferred scope, post-MVP considerations | Normal |
| §15 BMAD / Planning Readiness | [15-bmad-planning-readiness.md](docs/planning/planning-questions/15-bmad-planning-readiness.md) | BMAD readiness checklist and planning phase completion | Normal |

## Load Policy

- **For Brief/PRD creation:** Load §0, §1, §2, §3, §4, §15 only.
- **For Architecture phase:** Load §11 as reference.
- **For UX work:** Load §9 as reference.
- **For specific questions:** Load only the relevant shard.
- **DO NOT:** Load all shards in one turn unless explicitly auditing the entire planning canvas.

## Compatibility Note

Old links to `PLANNING_QUESTIONS.md` still work. This file remains at the root as a stable entrypoint and shard router.

## Related

- [Product Brief](_bmad-output/planning-artifacts/product-brief.md) — approved product direction
- [PRD](_bmad-output/planning-artifacts/prd.md) — detailed requirements
- [Architecture](_bmad-output/planning-artifacts/architecture.md) — technical decisions
- [IDEA_BRIEF.md](IDEA_BRIEF.md) — vision/inspiration reference
