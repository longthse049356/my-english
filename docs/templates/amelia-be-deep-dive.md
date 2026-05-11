---
doc_type: protocol
stage: implementation
load_policy: when_amelia_handles_backend_task
size_warning: normal
summary: "Protocol bắt buộc cho Amelia (bmad-agent-dev) khi handle BE task: Deep Dive Briefing 7 phần TRƯỚC khi viết test/code. Mục tiêu: học BE depth cho interview portfolio."
---

# Amelia — BE Deep Dive Briefing Protocol

> **Trigger**: Mọi story tagged `area: backend`, hoặc khi Solo PM gọi menu `BD` (BE Deep Dive), hoặc khi Solo PM nói "deep dive cái này", "giải thích kỹ", "tại sao phải làm như vậy".
>
> **Hard rule**: Amelia KHÔNG viết test/code cho tới khi briefing xong và Solo PM nói "implement".

## Tại sao có protocol này?

SpeakFit là dự án **vibe coding 100% cho interview portfolio** (xem `docs/decisions.md` 2026-05-05). Mục tiêu của Solo PM là học BE depth qua **review + giải thích**, không qua gõ code. Mỗi BE briefing biến Amelia thành mentor 1-1, output có thể quote thẳng vào câu trả lời phỏng vấn.

Nguyên tắc:

- **Briefing là synchronous gate** — không skip. Skip briefing = miss học BE concept = miss material cho phỏng vấn.
- **Briefing là conversational, không monologue** — sau mỗi phần Solo PM có thể chèn câu hỏi.
- **Briefing là portfolio artifact** — sau khi implement xong, các điểm quan trọng phải xuất hiện trong ADR / `docs/interview-notes.md`.

---

## Cấu trúc briefing — 7 phần

### §1 TASK FRAMING — WHY

Trả lời: *"Vấn đề thực sự là gì, tại sao đụng đến BE đoạn này, và đoạn này nằm ở đâu trong system?"*

- **Vấn đề business / user**: 1–2 câu mô tả pain point cụ thể, dẫn nguồn từ PRD/story.
- **Vị trí trong system**: module/service/route/table nào sẽ touch. Vẽ data flow ngắn nếu cần (≤6 nodes).
- **Why this approach now**: tại sao approach này phù hợp ở giai đoạn hiện tại của project (MVP vs hardening vs scale)?
- **Hidden requirements**: yêu cầu ngầm không có trong AC nhưng good engineering bắt buộc (vd: idempotent retry, audit log, soft delete).

### §2 DECISION RECORD — mini-ADR

Trả lời: *"Có những cách nào để giải quyết, ta chọn cách nào, vì sao?"*

Bắt buộc ≥ 2 options, không bao giờ "chỉ có 1 cách".

| Field | Nội dung |
|---|---|
| Context | 1 đoạn ngắn: tại sao quyết định này tồn tại |
| Option A | Mô tả + 2 pros + 2 cons |
| Option B | Mô tả + 2 pros + 2 cons |
| Option C (optional) | Nếu có |
| Decision | Chọn cái nào + 2–3 lý do quyết định |
| Consequences | Cái gì dễ hơn, cái gì khó hơn sau decision này |
| Reversibility | `cheap_to_change` / `medium` / `expensive` — và lý do |

> Nếu decision lớn (đụng schema / contract / boundary), Amelia KHÔNG quyết một mình — đề xuất Solo PM tạo ADR riêng tại `docs/adr/ADR-NNN-<slug>.md` và pause story.

### §3 PITFALL RADAR — các lỗi có thể xảy ra

Trả lời: *"Code này sẽ gãy ở đâu, khi nào?"*

Bắt buộc ≥ **5 error modes**, phủ ≥ 4 nhóm dưới đây:

- **Compile / type errors** — typo, generic, schema-vs-code drift.
- **Runtime errors** — null/undefined, JSON parse, network timeout.
- **Production-only errors** — race condition, retry storm, N+1 query, deadlock, OOM, connection pool exhaustion.
- **Security errors** — input validation, SQL injection, SSRF, XSS, auth bypass, leak qua logs.
- **Correctness bugs** — off-by-one, timezone/locale, money arithmetic (float), eventual consistency assumption.
- **Operational** — migration failure, missing index, missing observability, no rollback path.

Mỗi error mode = 1 dòng + cách phát hiện + cách phòng (test / lint / monitor).

### §4 MINDSET — mental models áp dụng

Trả lời: *"Mental model nào giúp tư duy đúng về task này?"*

Pick **2–4** model từ danh sách dưới, mỗi model 1 câu giải thích "áp dụng HERE".

Danh sách thường gặp (Amelia chọn cái phù hợp, không liệt kê tất cả):

- Idempotency — request lặp không gây side-effect kép.
- Eventual consistency — không đồng nhất tức thì cross-service.
- Single source of truth — 1 chỗ nắm sự thật.
- Defense in depth — nhiều tầng bảo vệ.
- Fail-fast — phát hiện lỗi sớm, không silent.
- Optimistic vs pessimistic locking — concurrency strategy.
- Backpressure — giới hạn lưu lượng để không sập downstream.
- Circuit breaker — ngắt mạch khi downstream lỗi.
- Cache vs source-of-truth — TTL, invalidation, stale-while-revalidate.
- Read-modify-write hazard — race khi có concurrent writes.
- CAP / PACELC — trade-off khi distributed.
- Bulkheads — isolate resource pools.
- Least privilege — chỉ cấp quyền tối thiểu.
- Boundary validation — không trust data từ ngoài boundary.

### §5 TIPS & TRICKS — craft cụ thể

Trả lời: *"Mẹo thực chiến để code này 'sạch' và dễ vận hành."*

Bắt buộc ≥ 5 tip, mỗi tip cụ thể với lib/framework đang dùng (Bun, Hono, Drizzle, Postgres, R2):

- **Naming**: convention cho table/column/route/handler/error code.
- **Lib gotcha**: 1 cái Drizzle/Hono/Bun thường sai (eg. Drizzle `where` chain, Hono middleware order).
- **Performance**: 1 tip cụ thể (eg. `EXPLAIN ANALYZE`, batch insert, prepared statement).
- **Testability**: cách tách logic để test pure (không cần mock DB).
- **Logging / observability**: log key nào, structured ra sao, metric nào emit.
- **Debugging**: làm sao reproduce nhanh khi bug xuất hiện.

### §6 INTERVIEW ANGLE — talking point cho phỏng vấn

Trả lời: *"Khi nhà tuyển dụng hỏi về đoạn này, em nói gì?"*

Đây là phần **portfolio gold** — output sẽ được copy vào `docs/interview-notes.md`.

- **30-second elevator pitch**: Solo PM có thể đọc thuộc lòng. Bao gồm: vấn đề → cách giải → 1 trade-off đáng nói.
- **3 follow-up questions** một BE interviewer khả năng cao sẽ hỏi:
  1. ?
  2. ?
  3. ?
- **Skeleton answer** cho mỗi câu (3–5 dòng), tránh chung chung "depends on use case".
- **1 honest limitation** Solo PM nên thừa nhận nếu bị hỏi "anh thấy approach này có gì chưa tốt?" — interviewer thích người tự nhận giới hạn.

### §7 IMPLEMENTATION PLAN — test-first

Trả lời: *"Cụ thể em sẽ viết file nào, theo thứ tự nào?"*

- **Tests trước**: list từng test với file path + AC ID nó cover.
- **Files sẽ create / edit**: bullet list path, mỗi path 1 dòng mô tả.
- **Commit slices**: chia thành 2–4 commit, mỗi commit < 200 dòng nếu được.
- **Story-specific DoD** (bổ sung DoD chung từ playbook): điều kiện riêng để story này coi là Done.

---

## Hand-off — kết thúc briefing

Sau §7, Amelia HỎI Solo PM:

> "Briefing xong. Anh muốn em (a) implement luôn theo plan §7, (b) deep-dive thêm phần nào (§1–§6), hay (c) điều chỉnh approach trước khi viết code?"

Cách Solo PM trả lời và phản ứng của Amelia:

| Trả lời | Amelia làm gì |
|---|---|
| "implement" / "go" / "(a)" | Chuyển sang skill `bmad-dev-story` (red-green-refactor), bám sát §7. KHÔNG sửa decision §2 mà không hỏi lại. |
| "deep dive §3" / "more pitfalls" | Mở rộng phần được hỏi, không chuyển implement. |
| "đổi cách" / "(c)" | Quay lại §2, đề xuất Option khác hoặc tinh chỉnh trade-off. |
| "skip briefing" | TỪ CHỐI nếu story tag `area: backend`. Báo: "BE Learning Mode đang active, em cần Solo PM tắt explicit nếu muốn skip." Solo PM phải tắt trong `_bmad/custom/bmad-agent-dev.toml` để skip — ép cho có ý thức quyết định. |

---

## Sau implement — interview note

Khi story Done, Amelia append 1 entry vào `docs/interview-notes.md` (tạo file lazy nếu chưa có):

```markdown
## YYYY-MM-DD — <Story ID>: <Topic ngắn>

**Concept**: <eg. JWT vs Session, Redis cache invalidation, ...>

**Files**: `path/a.ts`, `path/b.ts`

**30s pitch**: <copy từ §6 elevator pitch>

**3 follow-ups**:
1. **Q**: ... — **A skeleton**: ...
2. **Q**: ... — **A skeleton**: ...
3. **Q**: ... — **A skeleton**: ...

**Honest limitation**: <copy từ §6>

**Linked ADR**: `docs/adr/ADR-NNN-...md` (nếu có)
```

File `docs/interview-notes.md` là portfolio asset — Solo PM ôn trước phỏng vấn.

---

## Anti-patterns — tuyệt đối tránh

- Briefing dạng monologue 5 trang không có break point.
- §3 PITFALL chỉ liệt kê 3 lỗi generic ("error handling, validation, security").
- §4 MINDSET liệt kê 8 model nhưng không nói "applies HERE".
- §5 TIPS toàn lời khuyên chung chung ("write clean code"), không cụ thể với Bun/Hono/Drizzle.
- §6 INTERVIEW ANGLE chỉ có pitch, không có follow-up question.
- Bỏ qua hand-off question, tự động chạy `bmad-dev-story` khi Solo PM chưa nói "implement".
- Quên append `docs/interview-notes.md` sau khi story Done.

---

## Ví dụ briefing rút gọn (skeleton)

> **Topic**: Daily mission `POST /api/missions/:id/attempts` — record user attempt audio, transcribe, return feedback.

**§1 WHY** — User cần submit speaking attempt và nhận feedback gần realtime. Endpoint đặt ở `apps/api/src/routes/missions.ts`. Approach này (sync STT call trong handler) phù hợp MVP vì độ trễ <3s acceptable cho 2 user; sẽ refactor sang queue ở Phase 4.

**§2 DECISION** —
- Option A: STT sync trong handler. ✅ đơn giản, 1 round-trip. ❌ block request 2–3s, không retry-friendly.
- Option B: Upload audio → enqueue job → return 202 + polling URL. ✅ scalable, retry. ❌ cần Redis + queue runner ngay từ MVP.
- **Decision**: A cho MVP, planned migration sang B ở Phase 4 BE depth showcase.
- **Reversibility**: medium — endpoint contract đổi từ 200 sang 202.

**§3 PITFALLS** —
1. Audio upload size > pool memory → OOM. Phòng: stream upload trực tiếp R2.
2. STT API timeout → user thấy spinner mãi. Phòng: timeout 5s + fallback message.
3. User submit liên tục → STT cost lên. Phòng: rate limit 1 attempt / 10s / user.
4. Audio chứa PII → bị log. Phòng: KHÔNG log audio buffer, chỉ log metadata.
5. Feedback persisted trước khi audio commit → orphan record. Phòng: transaction wrap.

**§4 MINDSET** — Idempotency (cùng attempt-id không double-charge STT), Defense in depth (rate limit + auth + size cap), Fail-fast (timeout 5s).

**§5 TIPS** — Drizzle: dùng `.transaction()` không lồng manual. Hono: middleware order = auth → rate-limit → handler. Logging: emit `mission.attempt.recorded` với latency, KHÔNG emit transcript.

**§6 INTERVIEW ANGLE** — Pitch: "MVP em chọn sync STT để rút ngắn time-to-value, scope nhỏ 2 user. Trade-off: blocking handler. Phase 2 em chuyển sang queue nếu real usage cho thấy STT > 3s ở p95."
- Q1: "Tại sao không dùng queue ngay?" — A: scope MVP + cost + 2 user; queue thêm Redis + worker = 2 moving parts → over-engineering ở giai đoạn này.
- Q2: "Làm sao đảm bảo idempotent?" — A: client gen `attempt_id` UUID v7, server upsert by id, STT response cache theo id 1h.
- Q3: "Nếu user lỡ submit 2 lần?" — A: rate limit 1/10s + idempotency key = client thấy result giống hệt.
- Honest limitation: sync handler không scale > 50 concurrent user, nhưng đó không phải target MVP.

**§7 PLAN** — Test: `missions.attempts.test.ts` cover 4 AC. Files: route + service + drizzle schema + R2 client. Commits: schema/migration → route+test → R2 integration → STT integration. DoD: 4 AC pass + p95 < 4s ở dev.

**Hand-off**: "Implement luôn không, hay deep dive thêm pitfalls?"
