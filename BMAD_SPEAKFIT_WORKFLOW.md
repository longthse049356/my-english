# BMAD Method Workflow cho SpeakFit English

Tài liệu này hướng dẫn cách dùng BMAD Method cùng các agents hiện có trong `.opencode/agents` để triển khai dự án **SpeakFit English — Personalized English Coach PWA** như một dự án outsource thật.

Nguồn đầu vào chính: `PLANNING_QUESTIONS.md`.

---

## 1. Quyết định sử dụng agent

Nên ưu tiên **agents của BMAD** cho delivery chính vì BMAD đã có workflow chuẩn từ discovery đến implementation.

Các agents trong `.opencode/agents` vẫn hữu ích, nhưng nên dùng như **advisory / review council**, không thay thế BMAD delivery flow.

```text
BMAD agents = team thực thi chính
.opencode council agents = hội đồng phản biện / steering committee
```

---

## 2. Vai trò BMAD trong dự án

| BMAD Agent | Skill | Vai trò trong SpeakFit |
|---|---|---|
| Analyst / Mary | `bmad-agent-analyst` | Brainstorm, research, Product Brief, PRFAQ, phân tích thị trường và user |
| PM / John | `bmad-agent-pm` | PRD, MVP scope, epics, stories, readiness check |
| Architect / Winston | `bmad-agent-architect` | Architecture, ADR, data model, integration, implementation readiness |
| UX Designer / Sally | `bmad-agent-ux-designer` | UX spec cho onboarding, Home, Daily Mission, practice loop |
| Developer / Amelia | `bmad-agent-dev` | Implement story, test, code review, dev loop |
| Technical Writer / Paige | `bmad-agent-tech-writer` | Chuẩn hóa docs, standards, onboarding tài liệu |

---

## 3. Vai trò `.opencode/agents`

| Local Agent | Vai trò phù hợp |
|---|---|
| `council` | Điều phối review đa góc nhìn trước milestone lớn |
| `product-manager` | Review PRD/MVP scope nếu muốn góc nhìn ngoài BMAD PM |
| `architect` | Review architecture độc lập |
| `ux-designer` | Review UX flow độc lập |
| `security` | Review privacy, audio, auth, data retention |
| `business` | Review positioning, GTM, monetization |
| `skeptic` | Tìm scope creep, risk, assumption sai |
| `optimist` | Mở rộng vision/future roadmap |

Không nên dùng local agents để tạo toàn bộ PRD/Architecture nếu đã dùng BMAD. Dùng chúng để phản biện và quality gate.

---

## 4. Cấu trúc artifact đề xuất

BMAD đã tạo thư mục:

```text
_bmad-output/
  planning-artifacts/
  implementation-artifacts/
docs/
```

Quy ước dùng cho SpeakFit:

```text
PLANNING_QUESTIONS.md                         # Source of truth hiện tại
_bmad-output/planning-artifacts/product-brief.md
_bmad-output/planning-artifacts/prfaq.md
_bmad-output/planning-artifacts/prd.md
_bmad-output/planning-artifacts/ux-spec.md
_bmad-output/planning-artifacts/architecture.md
_bmad-output/planning-artifacts/epics-and-stories.md
_bmad-output/implementation-artifacts/stories/
docs/                                         # Project knowledge / standards
```

---

## 5. Workflow tối ưu cho SpeakFit

### Phase 0 — Align input

Mục tiêu: biến `PLANNING_QUESTIONS.md` thành nguồn đầu vào gọn cho BMAD.

Dùng:

```text
bmad-agent-analyst
bmad-product-brief
bmad-prfaq
```

Output:

```text
product-brief.md
prfaq.md
open-questions.md nếu còn câu hỏi lớn
```

Tiêu chí done:

- ICP rõ: người Việt A2/B1, professional, interview/workplace speaking.
- MVP boundary rõ: daily voice coaching loop.
- Non-goals rõ: payment, community, YouTube shadowing, full CMS, native app.

---

### Phase 1 — PRD

Dùng:

```text
bmad-agent-pm
bmad-create-prd
bmad-validate-prd
```

Input:

```text
PLANNING_QUESTIONS.md
product-brief.md
prfaq.md
```

Output:

```text
prd.md
```

PRD phải chốt:

- Product vision.
- Personas.
- Core user journey.
- MVP features.
- Non-goals.
- Success metrics: D1/D3/D7, recordings, completion, retry rate.
- Acceptance criteria cấp product.

Quality gate bằng local agents:

```text
council + skeptic + business + ux-designer
```

Mục tiêu review:

- Có bị scope creep không?
- MVP có đủ chứng minh daily speaking loop không?
- Có quá giống ChatGPT Voice không?

---

### Phase 2 — UX Specification

Dùng:

```text
bmad-agent-ux-designer
bmad-create-ux-design
```

Output:

```text
ux-spec.md
```

UX cần ưu tiên:

1. Onboarding 3 bước.
2. Daily Coach Desk.
3. Today’s Mission card.
4. Practice flow: Mission → Warm-up → Speak/Shadow → Feedback → Retry → Save → Progress.
5. Quiet Mode / Prepare Mode.
6. Recording/replay mobile-first.
7. Feedback nhẹ, song ngữ.

Quality gate bằng local agents:

```text
ux-designer + skeptic
```

---

### Phase 3 — Architecture

Dùng:

```text
bmad-agent-architect
bmad-create-architecture
bmad-check-implementation-readiness
```

Output:

```text
architecture.md
adr/*.md nếu cần
```

Architecture phải xử lý:

- Auth.
- LearningProfile model.
- Lesson / Mission.
- PracticeSession / Attempt.
- Recording local-first.
- Transcript / Feedback / SavedPhrase.
- TTS cache.
- MiniMax integration.
- STT fallback.
- Privacy and retention.
- Cost/usage tracking.

Data model hướng gợi ý:

```text
User
  → LearningProfile
    → LessonMission
      → PracticeSession
        → Attempt
          → RecordingMetadata
          → Transcript
          → Feedback
    → SavedPhrase
    → ProgressSnapshot
```

Quality gate bằng local agents:

```text
architect + security + skeptic
```

---

### Phase 4 — Epics & Stories

Dùng:

```text
bmad-agent-pm
bmad-create-epics-and-stories
bmad-create-story
bmad-sprint-planning
```

Epic đề xuất cho MVP:

```text
Epic 1 — Project foundation & auth
Epic 2 — Onboarding & learning profile
Epic 3 — Daily Coach Desk / Today’s Mission
Epic 4 — Lesson generation & TTS
Epic 5 — Voice practice / recording / replay
Epic 6 — Transcript & AI feedback
Epic 7 — Saved phrases / notes / progress
Epic 8 — Privacy, retention, usage tracking
Epic 9 — QA, polish, deployment readiness
```

Story phải có:

- User story.
- Context.
- Acceptance criteria.
- Technical notes.
- Dependencies.
- Test expectations.
- Definition of Done.

Quality gate:

```text
bmad-check-implementation-readiness
```

---

### Phase 5 — Implementation

Dùng:

```text
bmad-agent-dev
bmad-dev-story
bmad-quick-dev nếu task nhỏ
bmad-code-review
```

Quy tắc implement:

1. Chỉ implement story đã ready.
2. Không tự thêm feature ngoài story.
3. Mỗi story phải có test hoặc verification rõ.
4. Sau mỗi story chạy lint/typecheck/test nếu project có lệnh.
5. Không commit nếu chưa được yêu cầu.

Local council chỉ review ở milestone, không review từng story nhỏ.

---

## 6. Sprint plan đề xuất

### Sprint 0 — BMAD Planning

Output:

```text
product-brief.md
prd.md
ux-spec.md
architecture.md
epics-and-stories.md
```

### Sprint 1 — Foundation

- Auth cơ bản.
- User model.
- Learning profile.
- Onboarding.
- App shell mobile-first.

### Sprint 2 — Daily Mission

- Daily Coach Desk.
- Today’s Mission.
- Lesson seed/template.
- Basic mission state.

### Sprint 3 — Voice Practice

- Audio player.
- TTS integration/cache.
- Shadowing chunk/sentence/full.
- Recording/replay local-first.

### Sprint 4 — Feedback & Memory

- Transcript/STT fallback.
- AI feedback rubric.
- Retry flow.
- Saved phrases.
- Progress snapshot.

### Sprint 5 — Privacy & Hardening

- Recording retention settings.
- Delete audio/data.
- Usage tracking.
- Error states.
- QA.
- Deployment readiness.

---

## 7. Khi nào dùng Council?

Dùng `council` ở 4 thời điểm:

```text
1. Sau Product Brief / trước PRD final
2. Sau PRD / trước Architecture
3. Sau Architecture / trước Sprint 1
4. Trước MVP release
```

Không dùng council cho mọi quyết định nhỏ vì sẽ chậm delivery.

Format yêu cầu council nên là:

```text
Hãy review artifact X cho SpeakFit theo các góc nhìn:
PM, architect, UX, security, business, skeptic.
Output gồm: điểm đồng thuận, rủi ro, scope creep, quyết định cần chốt, recommendation.
```

---

## 8. Mapping giữa BMAD và local agents

| Nhu cầu | Dùng BMAD trước | Dùng local agent để review |
|---|---|---|
| Product discovery | Analyst / Mary | business, skeptic |
| PRD | PM / John | council, product-manager |
| UX flow | UX Designer / Sally | ux-designer, skeptic |
| Architecture | Architect / Winston | architect, security |
| Implementation | Developer / Amelia | không cần council, dùng code review |
| Documentation | Technical Writer / Paige | council nếu docs ảnh hưởng strategy |
| Risk review | PM/Architect readiness | skeptic, security |

---

## 9. Lệnh / skill BMAD nên dùng nhiều

Các skills đã được cài trong `.claude/skills`:

```text
bmad-help
bmad-agent-analyst
bmad-agent-pm
bmad-agent-architect
bmad-agent-dev
bmad-agent-ux-designer
bmad-agent-tech-writer
bmad-product-brief
bmad-prfaq
bmad-create-prd
bmad-validate-prd
bmad-create-ux-design
bmad-create-architecture
bmad-create-epics-and-stories
bmad-create-story
bmad-check-implementation-readiness
bmad-sprint-planning
bmad-sprint-status
bmad-dev-story
bmad-code-review
bmad-correct-course
bmad-retrospective
```

Nếu không chắc bước tiếp theo:

```text
Dùng bmad-help và hỏi: Tôi đang ở bước nào, tiếp theo nên chạy skill nào?
```

---

## 10. Quy tắc chống scope creep cho SpeakFit

MVP chỉ chứng minh:

```text
User mở app mỗi ngày → thấy mission → nói/shadow → nhận feedback → retry → thấy progress.
```

Không đưa vào MVP:

- Payment/subscription.
- Community.
- Tutor marketplace.
- YouTube shadowing.
- Native app.
- Full CMS.
- Full pronunciation scoring phoneme-level.
- Multi-profile đầy đủ.
- Enterprise/B2B admin.
- Dashboard nhiều chart.

Mỗi story nếu không phục vụ daily voice coaching loop thì đưa vào backlog.

---

## 11. Definition of Ready

Một story chỉ được đưa cho Developer khi có đủ:

```text
- User value rõ
- Acceptance criteria rõ
- UX state đủ rõ
- Data/API impact rõ
- Privacy impact nếu có audio/user data
- Test/verification rõ
- Không còn dependency blocker
```

Nếu thiếu, quay lại PM/Architect/UX trước khi code.

---

## 12. Definition of Done

Một story chỉ done khi:

```text
- Acceptance criteria pass
- Không phá core flow
- Có xử lý loading/error/empty state phù hợp
- Có verification/test phù hợp
- Lint/typecheck/test pass nếu project có lệnh
- Docs/story status được cập nhật
```

---

## 13. Workflow khuyến nghị ngay bây giờ

Bước tiếp theo nên làm:

```text
1. Dùng bmad-agent-analyst + bmad-product-brief để tạo Product Brief từ PLANNING_QUESTIONS.md
2. Dùng bmad-prfaq để kiểm tra narrative sản phẩm
3. Dùng bmad-agent-pm + bmad-create-prd để tạo PRD
4. Dùng council review PRD
5. Dùng bmad-agent-ux-designer tạo UX spec
6. Dùng bmad-agent-architect tạo Architecture
7. Dùng bmad-create-epics-and-stories tạo backlog triển khai
8. Dùng bmad-check-implementation-readiness trước khi code
```

---

## 14. Nguyên tắc vận hành như outsource team

```text
PM owns scope.
Architect owns technical feasibility.
UX owns user flow.
Security owns privacy and risk.
Developer owns implementation quality.
Tech Writer owns project knowledge.
Council owns milestone-level challenge and alignment.
```

Không agent nào tự ý mở rộng scope. Mọi thay đổi lớn phải đi qua PM + Architect + Council checkpoint.
