# Context Discipline

Rule cứng để mọi AI agent (parent và sub-agent) tránh đọc file thừa, kiểm soát token và giữ context window gọn cho repo này.

## Nguyên tắc 1 — Search-first, Read-after

- Trước khi `Read` một file, agent PHẢI dùng `Grep`, `Glob` hoặc `SemanticSearch` để xác nhận file có liên quan.
- Không `Read` full file > 400 dòng nếu chỉ cần 1 đoạn. Dùng `offset` + `limit`.
- Không re-read file đã có trong context window của session hiện tại.

## Nguyên tắc 2 — INDEX-first cho file lớn

Khi user yêu cầu task liên quan tới planning, idea, hay BMAD và agent chưa biết file nào liên quan:

1. Đọc `docs/INDEX.md` trước (manifest, ~200 dòng).
2. Dựa vào INDEX để chọn đúng file cần load.
3. Tôn trọng `load_policy` và `size_warning` trong frontmatter của từng file.

**Shard routing for planning files:**

- `PLANNING_QUESTIONS.md` và `IDEA_BRIEF.md` giờ là **shard indexes**, không phải full content files.
- Load index first (~60 dòng), then load ONE shard from `docs/planning/planning-questions/` or `docs/planning/idea-brief/`.
- For Brief/PRD: load PLANNING_QUESTIONS index, then load shards §0, §1, §2, §3, §4, §15 (~800 lines total instead of 3,300).
- For vision/persona: load IDEA_BRIEF index, then load shards §2, §4 (~100 lines total instead of 1,600).
- **DO NOT** load all shards in one turn.

Không tự ý mở full `IDEA_BRIEF.md` hay `PLANNING_QUESTIONS.md` content — chúng giờ là indexes. Không load tất cả shards nếu INDEX chưa chỉ định cần thiết cho task hiện tại.

## Nguyên tắc 3 — Tôn trọng frontmatter `load_policy`

Một số file có YAML frontmatter dạng:

```yaml
---
doc_type: idea-brief | prd | architecture | story | adr | runbook
stage: discovery | planning | implementation | released
load_policy: on_explicit_request | when_in_phase_<X> | always
size_warning: large | normal
summary: "..."
---
```

Quy tắc:

- `load_policy: on_explicit_request` → CHỈ load khi Solo PM nhắc tên file hoặc nói rõ phase tương ứng.
- `load_policy: when_in_phase_<X>` → CHỈ load khi BMAD đang ở phase X.
- `size_warning: large` → bắt buộc dùng `offset/limit` cho `Read` lần đầu, đọc summary + mục lục trước khi đọc nội dung chi tiết.

## Nguyên tắc 4 — Sub-agent context budget

Khi spawn sub-agent qua `Task`:

- Prompt PHẢI liệt kê **danh sách file cụ thể** sub-agent được phép đọc (không quá 5 file).
- Không bao giờ ra lệnh "review repo", "check toàn bộ project", "đọc tất cả docs". Thay bằng "đọc file X, Y, Z và đánh giá …".
- Nếu sub-agent cần thêm file ngoài danh sách, nó PHẢI báo lại parent thay vì tự đi đọc.
- Council mode (gọi nhiều persona song song) chỉ được dùng khi Solo PM yêu cầu rõ; mỗi persona vẫn tuân thủ rule này.

## Nguyên tắc 5 — Tier ưu tiên file

Phân tầng để chọn cái nào load trước:

| Tier | Khi nào load | Ví dụ |
|---|---|---|
| T0 — always-on | Tự động mỗi turn | `.cursor/rules/*.md` |
| T1 — manifest | Khi cần định hướng | `docs/INDEX.md` |
| T2 — working artifact | Phase / story đang active | `docs/prd.md`, story hiện tại |
| T3 — reference / cold | Chỉ khi explicit request | `IDEA_BRIEF.md`, `PLANNING_QUESTIONS.md`, ADR cũ |

Ưu tiên T0 → T1 → T2; chỉ chạm T3 khi Solo PM nhắc đích danh.

## Nguyên tắc 6 — Khi không chắc, hỏi trước

Nếu task của Solo PM mơ hồ và agent thấy có thể phải load > 3 file lớn (T2/T3), agent NÊN hỏi lại 1 câu xác nhận thay vì đọc tất cả.

Câu hỏi mẫu:

> "Task này có thể cần đọc `<file A>`, `<file B>`, `<file C>` (~N dòng). Anh/chị muốn em đọc tất cả hay chỉ summary của từng file trước?"

## Anti-patterns (tuyệt đối tránh)

- Đọc full content của `IDEA_BRIEF.md` hay `PLANNING_QUESTIONS.md` — chúng giờ là shard indexes. Load index, then ONE shard.
- Load tất cả shards trong `docs/planning/` cùng lúc.
- Spawn sub-agent với prompt "review the project" mà không kèm file list.
- Gọi council 7 persona để trả lời 1 câu hỏi nhỏ.
- Re-read cùng 1 file trong cùng 1 turn vì quên đã đọc.
- Tự ý load tất cả file trong `docs/` hoặc `_bmad-output/`.
