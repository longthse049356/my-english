# Project Context — Bối cảnh dự án

Repo này dùng để phát triển **SpeakFit English**: một **Personalized English Coach PWA** cho người Việt muốn cải thiện interview speaking và workplace speaking.

## Source of truth — Nguồn sự thật

- `PLANNING_QUESTIONS.md` là **planning canvas shard index** đã chốt phần lớn quyết định cho SpeakFit English. File này giờ là router tới 16 shard files tại `docs/planning/planning-questions/`. Đây là input chính cho BMAD ở phase Discovery → Planning. Load index first, then ONE shard only.
- `IDEA_BRIEF.md` là **vision/inspiration reference shard index**. File này giờ là router tới 13 shard files tại `docs/planning/idea-brief/`. KHÔNG dùng làm input chính cho BMAD, chỉ bổ sung khi cần thêm context vision. Load index first, then ONE shard only.
- `BMAD_SPEAKFIT_WORKFLOW.md` là operating playbook cho mô hình Solo PM + AI agents.
- `_bmad-output/planning-artifacts/` chứa planning outputs do BMAD workflows sinh ra. Sau khi Product Brief approved, các artifact tại đây trở thành source of truth, `PLANNING_QUESTIONS.md` chuyển sang `status: archived`.
- `.cursor/agents/` chứa explicit advisory agents.
- `.claude/skills/` chứa BMAD skills và customization; giữ lại trừ khi chủ động migrate.

## Working mode — Chế độ làm việc

- **Working mode: 100% vibe coding với GPT-5.5.** AI agents WRITE code; Solo PM specifies, decides, reviews, validates — **không gõ code tay**.
- 8h/ngày × 7 ngày/tuần dành cho project. Một giờ "vibe" = một giờ thực: prompt + review + verify + debug khi AI hallucinate.
- Stack choice ưu tiên: **giảm friction vibe coding** + **surface BE concepts cho interview portfolio**, KHÔNG ưu tiên "managed BaaS giấu BE".

## Goal hierarchy — Thứ tự ưu tiên mục tiêu

Mọi artifact (Brief, PRD, Architecture, ADR, sprint review, retro, code review) PHẢI tự hỏi: *"Cái này có showable trong phỏng vấn không?"*

| Hạng | Mục tiêu | Hệ quả |
|---|---|---|
| #1 | **Interview portfolio** — ADRs + decisions.md + retros + code defendable khi bị grill BE | Architecture phải defensible; mỗi quyết định lớn cần ADR |
| #1 (ngang) | **AI agent orchestration story** — bằng chứng cách Solo PM quản lý AI (Work Order, Artifact Contract, RAID, council gate, retro) | BMAD artifacts đầy đủ, không skip phase |
| #2 | **Working English coach** — đủ để dogfood + screenshot/demo cho phỏng vấn | Không polish quá; daily voice loop là đủ |
| #3 | **Học BE concepts depth** — bằng cách decision-make + review code AI viết, không học manual coding | Phase 4 (Tuần 8–10) showcase 3 BE concept lớn |

## Solo PM profile — Profile người vận hành

- **Level**: Senior FE đã có BE mindset. Không cần học BE từ đầu, học depth + experience để trả lời phỏng vấn.
- **Hard deadline**: ~3 tháng (~12 tuần) tính từ 2026-05-05.
- **MVP target**: 4 tuần (Phase 2, S1–S4).
- **Sau MVP**: 2 tuần dogfood + 3 tuần BE depth showcase + 2 tuần interview polish.

## Working style — Cách làm việc

- Ngôn ngữ planning mặc định: tiếng Việt.
- Product artifacts có thể viết bằng tiếng Anh khi Solo PM yêu cầu rõ.
- Không nhảy từ idea/planning sang implementation nếu Solo PM chưa yêu cầu implementation.
- Luôn xem Solo PM là decision owner/accountable duy nhất.
- AI agents thực thi, phân tích và đề xuất; AI agents không approve scope, merge PRs, hoặc release.
- MVP focus: **desktop-first for focused learning**. Optimize the first learning experience for laptop/desktop sessions to reduce phone distraction and support deliberate interview/workplace speaking practice. Mobile responsive support is secondary until explicitly promoted.
- **BE task → Learning Mode bắt buộc.** Khi `bmad-agent-dev` (Amelia) handle bất kỳ task nào tag `area: backend`, PHẢI mở Deep Dive Briefing trước khi viết test/code (xem `docs/templates/amelia-be-deep-dive.md`). Solo PM dùng briefing này để học BE concepts cho phỏng vấn.

## MVP focus — Phạm vi MVP

MVP chỉ validate daily voice coaching loop:

```text
User opens app daily → sees mission → speaks/shadows → receives feedback → retries → sees progress.
```

Mọi thứ ngoài loop này phải được đưa vào backlog, trừ khi Solo PM explicitly promote vào MVP scope.
