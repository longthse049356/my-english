# Repo Index — Manifest cho AI agents

Mục lục để AI agent (parent + sub-agent) tra cứu nhanh: **file nào dùng ở phase nào, file nào nên load, file nào không**. Đọc file này TRƯỚC khi load các file lớn (>500 dòng).

> Nguyên tắc kèm theo: xem `.cursor/rules/context-discipline.md`.

## 0. Obsidian Knowledge Map

Hub liên kết cho Obsidian Graph view. Mỗi `[[wikilink]]` tạo một cạnh trong graph để các artifact không còn rời rạc. Render nguyên văn `[[…]]` trong các trình Markdown khác là chấp nhận được — bảng manifest bên dưới vẫn là nguồn tra cứu chính.

### Idea & Planning roots

- [[IDEA_BRIEF|Idea Brief]] — vision & persona color (reference, không phải input chính).
- [[PLANNING_QUESTIONS|Planning Questions]] — primary planning canvas cho BMAD.
- [[BMAD_SPEAKFIT_WORKFLOW|BMAD SpeakFit Workflow]] — Solo PM + AI playbook.
- [[DESIGN|DESIGN — Quiet Studio]] — design thesis & visual system.

### BMAD planning artifacts (`_bmad-output/planning-artifacts/`)

- [[product-brief|Product Brief]]
- [[prd|PRD]]
- [[prd-validation-report|PRD Validation Report]]
- [[ux-design-specification|UX Design Specification]]
- [[architecture|Architecture]]

### UI/UX reference

- [[docs/ui-ux/README|UI/UX README]]
- [[speakfit-quiet-studio-reference|Quiet Studio Reference]]
- [[shadcn-tailwind-implementation-contract|Shadcn/Tailwind Implementation Contract]]

### Process & PM office

- [[docs/INDEX|Repo Index]] (file này)
- [[decisions|Decision Log]]
- [[raid|RAID Log]]
- [[ADR-001-cursor-first-ai-agent-orchestration|ADR-001 Cursor-first AI Orchestration]]

### Work orders

- [[WO-2026-001-product-brief|WO-2026-001 Product Brief]]
- [[WO-2026-002-prd|WO-2026-002 PRD]]

### Suggested entry points

- Bắt đầu hiểu sản phẩm → [[product-brief|Product Brief]] → [[prd|PRD]] → [[ux-design-specification|UX Design Specification]] → [[architecture|Architecture]].
- Bắt đầu hiểu cách làm việc → [[BMAD_SPEAKFIT_WORKFLOW|Workflow Playbook]] → [[decisions|Decision Log]] → [[raid|RAID Log]].
- Bắt đầu hiểu UI → [[DESIGN|DESIGN]] → [[speakfit-quiet-studio-reference|Quiet Studio Reference]] → [[shadcn-tailwind-implementation-contract|Shadcn/Tailwind Contract]].

## 1. File định hướng (Tier 0–1, luôn rẻ để load)

| Đường dẫn | Vai trò | Khi nào load |
|---|---|---|
| `.cursor/rules/project-context.md` | Bối cảnh dự án, MVP scope, working style | Auto |
| `.cursor/rules/agent-routing.md` | Mapping lệnh → advisory agent | Auto |
| `.cursor/rules/bmad-boundary.md` | Ranh giới BMAD vs advisory | Auto |
| `.cursor/rules/context-discipline.md` | Quy tắc kiểm soát token/context | Auto |
| `docs/INDEX.md` | (chính file này) Manifest tra cứu | Khi chưa biết file nào liên quan |

## 2. Idea & Planning artifacts

| File | Kích thước | Vai trò | doc_type | load_policy |
|---|---|---|---|---|
| `PLANNING_QUESTIONS.md` | Index (~60 dòng) | **Planning canvas shard index** (Tier 2 — router to 16 shards) | planning-canvas-index | read_index_then_one_shard |
| `docs/planning/planning-questions/` | 16 shards | Planning canvas content shards (§0-§15) | planning-shard | on_explicit_request |
| `IDEA_BRIEF.md` | Index (~60 dòng) | **Vision reference shard index** (Tier 3 — router to 13 shards) | idea-brief-index | vision_reference_only |
| `docs/planning/idea-brief/` | 13 shards | Vision/inspiration content shards (§1-§14, no §9) | idea-brief-shard | on_explicit_request |
| `BMAD_SPEAKFIT_WORKFLOW.md` | ~600 dòng | Operating playbook Solo PM + AI agents | playbook | when_user_asks_about_workflow |

**Shard routing rules:**

- `PLANNING_QUESTIONS.md` is now a **shard index**. Load the index first, then load ONE shard from `docs/planning/planning-questions/`.
- For Brief/PRD: load §0, §1, §2, §3, §4, §15 only (~800 lines total instead of 3,300).
- For Architecture phase: load §11 as reference.
- `IDEA_BRIEF.md` is now a **shard index**. Load the index first, then load ONE shard from `docs/planning/idea-brief/`.
- For vision/persona color: load §2 Vision + §4 Persona only (~100 lines total instead of 1,600).
- **DO NOT** load all shards in one turn unless explicitly auditing entire planning canvas.
- After Brief approved: `PLANNING_QUESTIONS.md` status changes to `archived`, Brief becomes source of truth.

## 3. BMAD planning outputs (Tier 2 — working artifacts)

Sinh ra bởi BMAD skills. Khi đang ở phase tương ứng, đây là file ưu tiên.

| Đường dẫn dự kiến | Sinh khi nào | Phase |
|---|---|---|
| `_bmad-output/planning-artifacts/product-brief.md` | Sau `bmad-product-brief` | Discovery |
| `_bmad-output/planning-artifacts/prfaq.md` | Sau `bmad-prfaq` | Discovery |
| `_bmad-output/planning-artifacts/prd.md` | Sau `bmad-create-prd` | Planning |
| `_bmad-output/planning-artifacts/ux-design-specification.md` | Sau `bmad-create-ux-design` | Planning |
| `_bmad-output/planning-artifacts/architecture.md` | Sau `bmad-create-architecture` | Planning |
| `_bmad-output/planning-artifacts/epics.md` | Sau `bmad-create-epics-and-stories` | Planning |
| `_bmad-output/planning-artifacts/stories/<story-id>.md` | Sau `bmad-create-story` | Sprint |
| `_bmad-output/implementation-artifacts/...` | Trong implementation | Sprint |

**Quy tắc khi BMAD chạy:** chỉ load đúng file của phase đang chạy + file của phase ngay trước nó (input). Không load lùi xa hơn nếu không cần.

## 4. PM office (Tier 1–2 — templates & decisions)

Templates rất ngắn (mỗi file < 100 dòng), load thoải mái khi cần fill.

| Folder/File | Mục đích |
|---|---|
| `docs/templates/ai-work-order.md` | Mẫu Solo PM giao việc cho AI |
| `docs/templates/ai-artifact-contract.md` | Mẫu AI bàn giao kết quả |
| `docs/templates/story-template.md` | Mẫu story (BMAD-aligned) |
| `docs/templates/pr-template.md` | Mẫu mô tả PR |
| `docs/templates/adr-template.md` | Mẫu Architecture Decision Record |
| `docs/templates/raid-entry-template.md` | Mẫu entry trong RAID log |
| `docs/templates/sprint-plan-template.md` | Mẫu plan đầu sprint |
| `docs/templates/sprint-review-template.md` | Mẫu review cuối sprint |
| `docs/templates/retro-template.md` | Mẫu retrospective |
| `docs/templates/council-review-template.md` | Mẫu output council multi-persona |
| `docs/templates/amelia-be-deep-dive.md` | **Protocol BE Learning Mode** cho Amelia (`bmad-agent-dev`) — bắt buộc với mọi BE story |
| `docs/interview-notes.md` | Portfolio asset: Amelia append entry sau mỗi BE story Done (lazy create) |
| `docs/raid.md` | Active RAID log (Risks/Assumptions/Issues/Dependencies) |
| `docs/decisions.md` | Decision log (non-architectural) |
| `docs/adr/` | Architecture Decision Records |
| `docs/onboarding/dev.md` | Onboarding cho human dev mới |
| `docs/runbooks/` | Operational runbooks |
| `docs/sprints/` | Sprint plans/reviews/retros theo sprint |
| `docs/council-reviews/` | Output council reviews đã lưu |

### BMAD agent customization (per-agent override)

| Đường dẫn | Mục đích |
|---|---|
| `_bmad/custom/bmad-agent-dev.toml` | Override Amelia: Learning Mode bắt buộc cho BE task, thêm menu code `BD`, persistent facts cho stack §11 + goal hierarchy |
| `_bmad/custom/<other>.toml` | (Tương lai) Override các agent khác khi cần |

Quy tắc: KHÔNG sửa `.claude/skills/bmad-*/customize.toml` (sẽ bị overwrite mỗi lần update). Mọi customize team-level đi qua `_bmad/custom/`.

## 5. Advisory agents (chỉ explicit-call)

| Folder | Vai trò |
|---|---|
| `.cursor/agents/` | 9 personas (architect, business, council, grill-me, optimist, product-manager, security, skeptic, ux-designer) — KHÔNG auto-load. Xem `.cursor/rules/agent-routing.md` để biết khi nào gọi. |

## 6. BMAD skills

| Folder | Vai trò |
|---|---|
| `.claude/skills/bmad-*/` | Skill chính chủ BMAD Method (PRD, architecture, stories, dev, review, retro, …). Kích hoạt khi user nói câu khớp `description` của skill. |

## 7. Quy ước khi thêm file mới

Khi tạo file > 300 dòng hoặc file dùng cross-phase, thêm frontmatter YAML đầu file:

```yaml
---
doc_type: <kind>
stage: <discovery|planning|implementation|released>
load_policy: <always|on_explicit_request|when_in_phase_X>
size_warning: <normal|large>
summary: "1 dòng mô tả mục đích"
---
```

Sau đó cập nhật `docs/INDEX.md` (file này) bổ sung 1 dòng vào bảng tương ứng.

## 8. Maintenance triggers — khi BMAD sinh artifact mới

Mỗi khi BMAD sinh file mới ở `_bmad-output/` (hoặc bạn tạo file > 300 dòng ở chỗ khác), đi qua **3 bước "PRD–IDX–PCX"**:

1. **PRD** = artifact vừa sinh — gắn YAML frontmatter (xem section 7) nếu file > 300 dòng.
2. **IDX** = file này (`docs/INDEX.md`) — thêm/cập nhật 1 dòng trong bảng phù hợp.
3. **PCX** = `.cursor/rules/project-context.md` — chỉ sửa khi artifact mới *thay thế* nguồn-sự-thật cũ (ví dụ: PRD freeze → IDEA_BRIEF chuyển từ "input" sang "reference").

### Ma trận sự kiện BMAD → file cần cập nhật

| Sự kiện | Frontmatter file mới? | INDEX | project-context | Khác |
|---|---|---|---|---|
| Product Brief | Không (thường nhỏ) | + dòng | — | `docs/decisions.md` log |
| PRFAQ | Không | + dòng | — | — |
| **PRD final** | **Có** | + dòng | **Sửa Source of Truth** | `docs/decisions.md` log "PRD freeze" |
| UX Spec | Có nếu > 300 dòng | + dòng | — | — |
| **Architecture** | **Có** | + dòng | **Thêm vào Source of Truth** | `docs/adr/ADR-XXX.md` cho mỗi quyết định lớn |
| Epics & Stories list | Có nếu > 300 dòng | + dòng (1 lần cho thư mục) | — | — |
| Sprint Planning | — | — | — | `docs/sprints/sprint-NN-plan.md` + cập nhật `docs/raid.md` |
| Mỗi Story (create + dev) | Story dùng template, đã có frontmatter | KHÔNG spam từng story | — | PR theo `docs/templates/pr-template.md` |
| **BE Story (`area: backend`)** | — | — | — | **Amelia BẮT BUỘC mở Deep Dive Briefing** theo `docs/templates/amelia-be-deep-dive.md` trước khi code. Sau Done append `docs/interview-notes.md`. |
| Code Review issue | — | — | — | Update story state + `docs/raid.md` |
| Sprint Review | — | — | — | `docs/sprints/sprint-NN-review.md` + đóng/mở RAID |
| Retrospective | — | — | — | `docs/sprints/sprint-NN-retro.md`; nếu retro yêu cầu sửa playbook → patch `BMAD_SPEAKFIT_WORKFLOW.md` |
| Council Review | — | — | — | `docs/council-reviews/<date>-<topic>.md` + `docs/decisions.md` |
| Correct Course | — | — | Có thể đổi `stage` của artifact bị ảnh hưởng | `docs/decisions.md` + `docs/raid.md` |
| **MVP Release** | Đổi `stage:` thành `released` cho artifact ổn định | — | — | Chạy `docs/runbooks/release-qa.md` + `docs/decisions.md` log release |

### Shortcut khi làm việc với AI agent

Sau khi BMAD vừa chạy xong 1 phase, dùng nguyên prompt sau cho agent — nó sẽ tự đi qua bảng trên:

> "BMAD vừa sinh `<đường-dẫn-file>`. Áp dụng quy trình PRD–IDX–PCX: gắn frontmatter cho file mới nếu cần, cập nhật `docs/INDEX.md`, và update `.cursor/rules/project-context.md` nếu artifact này đổi nguồn-sự-thật."

### File hiếm khi đụng (chỉ khi process đổi)

- `.cursor/rules/bmad-boundary.md` — khi đổi quality gate hoặc thêm/bớt advisory agent.
- `.cursor/rules/agent-routing.md` — khi thêm agent mới hoặc đổi phrase trigger.
- `.cursor/rules/context-discipline.md` — khi đổi nguyên tắc kiểm soát context.
- `BMAD_SPEAKFIT_WORKFLOW.md` — khi retrospective ra action sửa playbook.
- `docs/templates/*` — chỉ cập nhật template gốc khi mẫu cũ không còn phù hợp; không clone template mới mỗi sprint.

## 9. Cấm đoán (anti-patterns)

- KHÔNG load full `IDEA_BRIEF.md` hay `PLANNING_QUESTIONS.md` — chúng là shard indexes. Load index, then ONE shard.
- KHÔNG load tất cả shards trong `docs/planning/` cùng lúc.
- KHÔNG load tất cả file trong `_bmad-output/` cùng lúc.
- KHÔNG để sub-agent tự khám phá repo — luôn pass file list rõ ràng.
- KHÔNG bỏ qua `load_policy` của file đã có frontmatter.
