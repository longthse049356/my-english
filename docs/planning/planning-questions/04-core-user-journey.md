---
doc_type: planning-shard
stage: discovery
load_policy: on_explicit_request
size_warning: large
source_file: PLANNING_QUESTIONS.md
source_section: "§4 Core User Journey"
summary: "End-to-end user journey, daily loop, and key interaction flows."
---

**Related:** [PLANNING_QUESTIONS.md](../../PLANNING_QUESTIONS.md) | [Product Brief](../../_bmad-output/planning-artifacts/product-brief.md)

## 5. Curriculum / Learning Plan

### Q22. Lộ trình nên là 30/45/60/90 ngày hay mặc định 60 ngày?

Thông tin hiện tại:

- User muốn linh hoạt.
- Thiết kế trung tâm là 1 lesson/ngày.
- 60 ngày vẫn là định vị tốt.

Trả lời:

> **Nên giữ 60 ngày làm default positioning, nhưng kiến trúc nên hiểu đây là 60 lessons có thể học linh hoạt, không phải lịch cứng bắt buộc.**
>
> Lý do:
>
> - 60 ngày đủ mạnh về mặt marketing: có cảm giác bootcamp/fitness program.
> - Đủ dài để hình thành thói quen speaking/shadowing.
> - Không quá ngắn như crash course, không quá dài như course học tiếng Anh tổng quát.
>
> Tuy nhiên không nên bắt user chọn 30/45/60/90 ngay từ MVP vì làm onboarding và curriculum phức tạp. Phase đầu nên có:
>
> 1. **Default 60-day path**
>    - 1 mission/ngày.
>    - Có thể học chậm hơn mà không bị fail.
>
> 2. **Flexible pace**
>    - Vẫn là 60 missions.
>    - User có thể pause, skip, catch-up, recovery.
>    - App tính `behind schedule` nhẹ, không phạt.
>
> 3. **Crash mode 30 days**
>    - Để backlog.
>    - Phù hợp người sắp phỏng vấn gấp nhưng cần thiết kế riêng.
>
> 4. **90-day/deep mode**
>    - Để sau khi core loop chứng minh retention.
>
> Product rule:
>
> **MVP build một 60-day path nhẹ + flexible pacing, chưa build nhiều curriculum duration riêng.**

---

### Q23. 60 ngày có chia thành 8 tuần không?

Gợi ý tuần:

1. Self-introduction / foundation.
2. Experience / role / responsibility.
3. Project/work story.
4. Behavioral questions.
5. Workplace scenarios.
6. Negotiation/conflict/problem solving.
7. Mock interview.
8. Review/readiness.

Trả lời:

> **Có. Nên chia thành 8 tuần core curriculum + 4 ngày final readiness/catch-up.**
>
> 8 tuần = 56 ngày, nên 60 ngày có thể thiết kế như:
>
> - **Week 1–8:** core learning path.
> - **Days 57–60:** final review, catch-up, before/after comparison, final mock, next plan.
>
> Cấu trúc đề xuất:
>
> 1. **Week 1 — Start Strong / Baseline & Self-introduction**
>    - Dám nói vào mic.
>    - Self-introduction.
>    - Current role/goal.
>    - Speaking baseline.
>    - 5–10 phrase nền.
>
> 2. **Week 2 — Experience, Role & Responsibility**
>    - Nói về công việc hiện tại.
>    - Mô tả trách nhiệm.
>    - Nói về kỹ năng, task, tools/process.
>    - Vocabulary theo role/ngành.
>
> 3. **Week 3 — Project / Work Story**
>    - Giải thích project, case, achievement.
>    - Dùng STAR/PREP đơn giản.
>    - Kể challenge/result.
>    - Tạo story bank nhẹ.
>
> 4. **Week 4 — Behavioral Interview**
>    - Strength/weakness.
>    - Teamwork/conflict.
>    - Failure/challenge.
>    - Career goal.
>
> 5. **Week 5 — Workplace Communication**
>    - Meeting update.
>    - Asking for clarification.
>    - Explaining issues.
>    - Email/spoken phrases theo context.
>
> 6. **Week 6 — Problem Solving / Negotiation / Conflict**
>    - Với engineer: bug, deadline, technical tradeoff, disagreement.
>    - Với purchasing/business: supplier issue, cost, quality, delivery, negotiation.
>
> 7. **Week 7 — Mock Interview & Follow-up Questions**
>    - Mini/full mock.
>    - Follow-up questions.
>    - Timed answer.
>    - Pressure handling.
>
> 8. **Week 8 — Readiness & Personalization**
>    - Refine personal answers.
>    - Review weak points.
>    - Reuse saved phrases/vocab.
>    - Final speaking confidence.
>
> 9. **Days 57–60 — Final Readiness Sprint**
>    - Final mock.
>    - Before/after recordings.
>    - Personal phrasebook review.
>    - Next 30-day recommendation.
>
> Mỗi tuần nên có:
>
> - 5 main missions;
> - 1 review/catch-up day;
> - 1 optional/rest/recovery day.
>
> Không nên claim “8 tuần fluent”. Claim thực tế hơn:
>
> **8 tuần xây thói quen nói, luyện tình huống phổ biến và tăng interview/workplace readiness.**

---

### Q24. Week 1 nên là self-introduction hay assessment/foundation?

Options:

1. Self-introduction ngay.
2. Assessment nhẹ trước.
3. Kết hợp: self-introduction vừa là first mission vừa là baseline.

Trả lời:

> **Week 1 nên kết hợp: self-introduction vừa là first mission vừa là baseline assessment.**
>
> Không nên mở đầu bằng placement test khô cứng vì user cần thấy value ngay. Nhưng cũng cần baseline để cá nhân hóa feedback và progress.
>
> Tên tuần nên thân thiện:
>
> **Week 1: Start Strong — Introduce yourself clearly**
>
> Không nên gọi là “Assessment Week”.
>
> Mục tiêu Week 1:
>
> - user hiểu app hoạt động thế nào;
> - dám nói vào mic;
> - có first recording;
> - nhận feedback nhẹ;
> - lưu vài phrase nền;
> - thấy completion/win đầu tiên;
> - tạo baseline cho fluency, confidence, grammar, vocabulary, pronunciation/basic clarity.
>
> Gợi ý 7 ngày:
>
> 1. **Day 1 — Tell me about yourself**
>    - User nói 30–60 giây.
>    - App lấy baseline.
>    - Feedback cực nhẹ.
>
> 2. **Day 2 — Shadow your self-introduction**
>    - App tạo version tốt hơn.
>    - User shadow theo chunk.
>
> 3. **Day 3 — Current role / current job**
>    - `I work as...`, `I’m responsible for...`
>
> 4. **Day 4 — Why do you want to improve English?**
>    - Gắn với motivation cá nhân.
>
> 5. **Day 5 — Mini challenge**
>    - Nói 30–45 giây không xem full sample trước.
>
> 6. **Day 6 — Review phrases + vocab tips**
>    - Ôn 5–10 phrases/từ đã gặp.
>    - Có memory aids: collocation, word family, prefix/root nếu hữu ích.
>
> 7. **Day 7 — Week 1 mini reflection / mini mock**
>    - 2–3 câu hỏi nhẹ.
>    - So sánh cảm giác với Day 1.
>
> Week 1 không nên có grammar theory dài, vocab list 20 từ, mock interview nặng hoặc scoring gây áp lực.

---

### Q25. Mock interview bắt đầu từ khi nào?

Options:

1. Cuối tuần 1 dạng nhẹ.
2. Từ tuần 3–4.
3. Chỉ phase sau.

Trả lời:

> **Mock interview nên xuất hiện sớm dưới dạng mini mock nhẹ, nhưng full mock nên bắt đầu từ Week 4 hoặc Week 7.**
>
> Nếu đợi tới cuối khóa mới mock, user thiếu cảm giác đang tiến gần mục tiêu. Nhưng nếu mock interview đầy đủ quá sớm, user dễ anxiety và feature dễ scope creep.
>
> Lộ trình đề xuất:
>
> ### Week 1 — Mini baseline mock
>
> - 2–3 câu rất nhẹ.
> - Không chấm nặng.
> - Mục tiêu: baseline và làm quen.
> - Ví dụ:
>   - Tell me about yourself.
>   - What is your current role?
>   - Why do you want to improve English?
>
> ### Week 3–4 — Themed mini mock
>
> - 3–5 câu theo chủ đề.
> - Ví dụ:
>   - project/work story mock;
>   - behavioral mini mock;
>   - workplace situation mock.
> - Feedback theo clarity, structure, vocabulary.
>
> ### Week 7 — Main mock interview
>
> - 8–10 câu.
> - Có follow-up questions.
> - Có timed answer nếu user sẵn sàng.
> - Có practice/readiness score.
>
> ### Days 57–60 — Final mock + before/after
>
> - So sánh với Day 1.
> - Review câu khó.
> - Gợi ý plan tiếp theo.
>
> MVP không nên làm full realtime interview simulator phức tạp. Phase đầu chỉ cần async mock:
>
> **AI hỏi → user record → AI feedback → user retry câu khó.**
>
> Mock interview nên là activity tăng dần độ thật, không phải một feature khổng lồ ngay từ đầu.

---

### Q26. Có rest day/catch-up day không?

Gợi ý:

- Nên có streak mềm.
- Có recovery lesson 3–5 phút khi bỏ lỡ.

Trả lời:

> **Có, nhưng nên thiết kế là light review / catch-up day, không phải một hệ thống lịch học phức tạp.**
>
> Mỗi tuần nên có nhịp:
>
> - 5 ngày main speaking missions;
> - 1 ngày review/catch-up;
> - 1 ngày optional rest/recovery.
>
> Rest day không nên làm user cảm thấy “bỏ học”. Có thể gọi là:
>
> - `Light Review Day`
> - `Catch-up Day`
> - `Recovery Practice`
>
> Khi user bỏ lỡ bài:
>
> - Không dồn tất cả bài miss vào hôm sau.
> - Không phá streak bằng copy tiêu cực.
> - Ưu tiên recovery lesson 3–5 phút: shadow 3 câu dễ, ôn 3 phrase, retry 1 câu cũ.
>
> Copy nên dùng:
>
> `Không sao, hôm nay mình nối lại nhịp bằng một bài ngắn.`
>
> Completion/streak:
>
> - Main speaking mission tăng speaking streak.
> - Light review có thể giữ daily habit streak.
> - Nếu nghỉ thật, không nên phạt nặng.
>
> Product rule:
>
> **Rest/catch-up tồn tại để giữ habit, không phải để tạo thêm complexity lịch học.**

---
