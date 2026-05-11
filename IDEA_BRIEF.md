---
doc_type: idea-brief-index
stage: discovery
load_policy: vision_reference_only
size_warning: normal
status: reference
summary: "Vision/inspiration reference index for SpeakFit. This file is now a shard map. Load one shard at a time via docs/planning/idea-brief/. NOT primary BMAD input."
---

# Idea Brief — Personalized English Coach PWA

> **Lưu ý cho AI agents:** File này là **shard index** cho vision/inspiration reference. KHÔNG phải primary input cho BMAD. Primary input là `PLANNING_QUESTIONS.md` và BMAD artifacts. Chỉ load section cụ thể của file này khi cần "color" cho persona/vision/council brainstorm — và phải load chỉ 1 shard tại `docs/planning/idea-brief/`.

## Shard Map

Content đã được chia thành 13 shard files. **Note:** Section §9 intentionally absent in source.

| Section | Shard File | Summary | Size |
|---------|-----------|---------|------|
| §1 Bối cảnh | [01-context.md](docs/planning/idea-brief/01-context.md) | Project background, initial motivation, personal context | Normal |
| §2 Vision | [02-vision.md](docs/planning/idea-brief/02-vision.md) | Product vision and long-term aspirations | Normal |
| §3 Định vị sản phẩm ban đầu | [03-positioning.md](docs/planning/idea-brief/03-positioning.md) | Initial product positioning and differentiation | Normal |
| §4 Persona ban đầu | [04-personas.md](docs/planning/idea-brief/04-personas.md) | Initial persona profiles and user archetypes | Normal |
| §5 Jobs To Be Done | [05-jobs-to-be-done.md](docs/planning/idea-brief/05-jobs-to-be-done.md) | User jobs, needs, and desired outcomes | Normal |
| §6 Insight từ Council vòng 1 | [06-council-round-1-insights.md](docs/planning/idea-brief/06-council-round-1-insights.md) | First council review insights and feedback | Large |
| §7 Nguyên tắc sản phẩm | [07-product-principles.md](docs/planning/idea-brief/07-product-principles.md) | Core product principles and design philosophy | Normal |
| §8 Feature Backlog | [08-feature-backlog.md](docs/planning/idea-brief/08-feature-backlog.md) | Comprehensive feature ideation (beyond MVP scope) | Large |
| §10 Những thứ chưa nên chốt vội | [10-not-yet-fixed.md](docs/planning/idea-brief/10-not-yet-fixed.md) | Open decisions requiring further validation | Normal |
| §11 Giả định rủi ro | [11-risk-assumptions.md](docs/planning/idea-brief/11-risk-assumptions.md) | Key assumptions and identified risks | Normal |
| §12 Câu hỏi mở | [12-open-questions.md](docs/planning/idea-brief/12-open-questions.md) | Unresolved questions and exploration areas | Large |
| §13 Quy trình đề xuất tiếp theo | [13-next-process.md](docs/planning/idea-brief/13-next-process.md) | Recommended next steps and process flow | Normal |
| §14 Council Brainstorm | [14-council-brainstorm.md](docs/planning/idea-brief/14-council-brainstorm.md) | Feature-rich AI learning system brainstorm | Large |

## Load Policy

- **Vision/persona color:** Load §2 Vision + §4 Persona only (~100 lines total).
- **Council insights:** Load §6 or §14 as needed.
- **Feature exploration:** Load §8 Feature Backlog (note: most features are beyond MVP).
- **DO NOT:** Load all shards or treat this as primary planning input.

## Source of Truth

After Product Brief approval, this file is **reference only**. Current source of truth:
- [Product Brief](_bmad-output/planning-artifacts/product-brief.md)
- [PRD](_bmad-output/planning-artifacts/prd.md)
- [PLANNING_QUESTIONS.md](PLANNING_QUESTIONS.md) (planning canvas index)

## Compatibility Note

Old links to `IDEA_BRIEF.md` still work. This file remains at the root as a stable entrypoint and shard router.

## Related

- [PLANNING_QUESTIONS.md](PLANNING_QUESTIONS.md) — primary planning canvas
- [Product Brief](_bmad-output/planning-artifacts/product-brief.md) — approved product direction
- [PRD](_bmad-output/planning-artifacts/prd.md) — detailed requirements
