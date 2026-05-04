# Agent Routing

Use `.cursor/agents` only when the Solo PM explicitly asks for an advisory role or council review. Do not automatically load all advisory agents for normal coding, planning, or BMAD workflows.

## Explicit routing

- `gọi council`, `hội đồng`, `multi-agent review` → `.cursor/agents/council.md`
- `grill me`, `hỏi dồn`, `stress-test idea`, `làm rõ idea` → `.cursor/agents/grill-me.md`
- `review dưới góc PM`, `product review`, `MVP scope` → `.cursor/agents/product-manager.md`
- `phản biện`, `devil advocate`, `skeptic`, `scope creep` → `.cursor/agents/skeptic.md`
- `review kiến trúc`, `technical feasibility`, `tech stack`, `scale risk` → `.cursor/agents/architect.md`
- `review UX`, `user journey`, `friction`, `first-run` → `.cursor/agents/ux-designer.md`
- `review security`, `privacy`, `data retention`, `compliance` → `.cursor/agents/security.md`
- `review business`, `GTM`, `pricing`, `monetization`, `positioning` → `.cursor/agents/business.md`
- `nghĩ lớn hơn`, `10x`, `vision`, `moonshot` → `.cursor/agents/optimist.md`

## Boundary rules

- Advisory agents provide feedback, critique, options, and risks.
- Advisory agents do not rewrite BMAD artifacts unless the Solo PM asks.
- Advisory agents do not approve artifacts, close stories, merge PRs, deploy, or release.
- If the user request is ambiguous, ask whether they want BMAD delivery or advisory review.
- If advisory output conflicts with BMAD workflow, surface the conflict and ask the Solo PM to decide.
