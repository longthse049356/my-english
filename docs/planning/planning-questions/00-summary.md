---
doc_type: planning-shard
stage: discovery
load_policy: on_explicit_request
size_warning: normal
source_file: PLANNING_QUESTIONS.md
source_section: "§0 Tóm tắt hiện trạng"
summary: "Product vision, positioning, and product principles for SpeakFit English MVP."
---

## 0. Tóm tắt hiện trạng

**Related:** [PLANNING_QUESTIONS.md](../../PLANNING_QUESTIONS.md) | [Product Brief](_bmad-output/planning-artifacts/product-brief.md)

### Product Vision tạm thời

Xây dựng một **Personalized English Coach PWA** cho người Việt đã có nền tảng tiếng Anh tối thiểu A2/B1, nhưng thiếu phản xạ nghe-nói, thiếu tự tin khi phỏng vấn hoặc giao tiếp công việc.

Sản phẩm không phải app học tiếng Anh tổng hợp, mà là một AI English coach theo lộ trình cá nhân hóa, giúp user luyện mỗi ngày qua tình huống thực tế, interview/workplace questions, listening, shadowing, recording, feedback, vocabulary/phrases theo ngành và review cá nhân hóa.

### Định vị tạm thời

**Option rộng:**

> AI English Interview & Workplace Coach for Vietnamese Professionals.

**Option hẹp cho phase đầu:**

> 60-day English speaking & interview fitness program for Vietnamese professionals.

### Nguyên tắc sản phẩm tạm thời

- Private-first.
- Mobile-first.
- Daily habit-first.
- Speaking/shadowing-first.
- AI-personalized nhưng UX phải đơn giản.
- Home phải trả lời ngay: “Hôm nay mình nên luyện gì?”
- Feedback phải giúp user muốn luyện tiếp, không làm user sợ nói sai.

---

## 1. Product Strategy

### Q1. Tên tạm thời của sản phẩm là gì?

Gợi ý:

- Tên tiếng Anh hay tiếng Việt?
- Nghiêm túc/professional hay thân thiện?
- Có gắn với interview/speaking/coach không?

Trả lời:

> **SpeakFit English**
>
> Lý do: tên ngắn, dễ nhớ, gợi cảm giác luyện nói đều đặn như fitness, đủ rộng để bao phủ cả interview và workplace English. Nếu sau này muốn tập trung rất hẹp vào phỏng vấn, có thể dùng nhánh/campaign name là **InterviewFit English**.
>
> Tagline tạm thời: **Your daily English speaking coach for interviews and work.**

---

### Q2. Định vị chính nên là gì?

Options:

1. English Interview Coach.
2. Workplace English Coach.
3. Speaking Confidence Coach.
4. AI English Coach cho interview + workplace.
5. 60-day English fitness program.

Trả lời:

> **60-day speaking & interview fitness program for Vietnamese professionals.**
>
> Đây là định vị đủ hẹp để khác app học tiếng Anh tổng hợp, có thời hạn rõ, có outcome rõ và phù hợp với core loop daily practice. Bên dưới có thể mở rộng thành workplace English, nhưng phase đầu nên dùng interview/speaking làm wedge chính.

---

### Q3. Có muốn nhấn mạnh “cho người Việt” ngay từ đầu không?

Thông tin hiện tại:

- Lợi thế lớn là feedback bằng tiếng Việt, hiểu lỗi phổ biến của người Việt, context người Việt đi làm/phỏng vấn.
- Nếu mở rộng quốc tế sau này vẫn có thể đổi định vị.

Trả lời:

> **Có. Nên nhấn mạnh ngay từ đầu.**
>
> Đây là lợi thế khác biệt quan trọng so với ChatGPT, ELSA, Duolingo, Cambly: app hiểu người Việt, giải thích bằng tiếng Việt, tập trung lỗi phổ biến của người Việt và context phỏng vấn/giao tiếp công việc của người Việt. Không nên lo mở rộng quốc tế quá sớm; phase đầu cần thắng một niche rõ trước.

---

### Q4. Sản phẩm nên tạo cảm giác giống gì nhất?

Options:

1. App học tập.
2. AI coach.
3. Bootcamp 30/60 ngày.
4. Trợ lý cá nhân.
5. Hybrid: app + coach + bootcamp.

Trả lời:

> **Hybrid: app + coach + bootcamp.**
>
> User cần cảm giác có người dẫn đường mỗi ngày, có lộ trình rõ như bootcamp, nhưng vẫn riêng tư và linh hoạt như app cá nhân. Trong copy nên ưu tiên cách gọi **daily coach** và **60-day program**, tránh nhồi quá nhiều concept khiến sản phẩm khó hiểu.

---

### Q5. Tone sản phẩm nên là gì?

Options:

1. Gentle + professional.
2. Direct + practical.
3. Strict coach.
4. Funny/gamified.
5. User chọn coach tone.

Thông tin hiện tại:

- Mặc định nên là gentle + professional.
- Feedback nên tích cực trước, sửa ít lỗi quan trọng.

Trả lời:

> **Mặc định: gentle + professional, nhưng feedback cần direct + practical.**
>
> Không nên dùng strict coach mặc định vì người học dễ sợ nói sai và bỏ cuộc. Không nên gamified/funny quá nhiều vì mục tiêu interview/workplace cần sự tin cậy. Công thức feedback nên là: khen 1 điểm thật, sửa tối đa 1–2 điểm quan trọng, đưa 1 câu/next action dùng được ngay.

---

### Q6. Lợi thế khác biệt lớn nhất so với ChatGPT Voice là gì?

Gợi ý:

- Có lộ trình rõ ràng.
- Có daily mission.
- Có tracking tiến độ.
- Có review queue.
- Có memory về lỗi, vocab, sticky notes.
- Có content theo profile/ngành/nghề.
- Không cần user tự nghĩ prompt mỗi ngày.

Trả lời:

> **SpeakFit không bán “AI nói chuyện”, mà bán một lộ trình luyện nói có cấu trúc, có đo tiến bộ và có memory cá nhân hóa cho người Việt.**
>
> Khác biệt chính so với ChatGPT Voice:
>
> - User không phải tự nghĩ hôm nay học gì hoặc prompt gì.
> - App có daily mission 5–10 phút/ngày.
> - Có curriculum theo interview/workplace context.
> - Có shadowing drills, recording, replay và feedback ngắn.
> - Có rubric theo fluency, clarity, grammar, vocabulary, structure, confidence.
> - Có memory về lỗi lặp lại, vocab, sticky notes, progress và review queue.
> - Có feedback bằng tiếng Việt, hiểu lỗi phổ biến của người Việt.
>
> Câu định vị nội bộ: **ChatGPT Voice là conversation tool; SpeakFit là structured speaking improvement program.**

---

### Q7. Nếu user chỉ dùng app 7 ngày, điều gì phải xảy ra để họ muốn dùng tiếp?

Gợi ý:

- Học được ít nhất 5/7 ngày.
- Record được vài câu trả lời.
- Cảm thấy biết cách trả lời phỏng vấn hơn.
- Thấy tiến bộ nhỏ về confidence/fluency.
- Có vài phrase dùng được ngay.

Trả lời:

> **User phải cảm thấy mình nói tốt hơn một chút và nhìn/nghe được tiến bộ đó.**
>
> Success moment sau 7 ngày:
>
> - Học ít nhất 5/7 ngày.
> - Record ít nhất 5 câu trả lời hoặc shadowing attempts.
> - Nghe lại recording ngày 1 và ngày 7 thấy ít ngập ngừng hơn.
> - Có 3–5 phrase/câu mẫu dùng được ngay cho interview/workplace.
> - Thấy một progress signal rõ: pause giảm, câu dài hơn, confidence score tăng, hoặc practice score tăng.
> - Cảm giác quan trọng nhất: **“Mình biết hôm nay luyện gì và thấy mình đang khá lên.”**
>
> Không nên chỉ đo “app hay/AI thông minh”; phải đo activation và retention: D1, D3, D7, số speaking sessions, số recording, số ngày quay lại.

---

### Q8. Nếu user dùng xong 60 ngày, kết quả tối thiểu kỳ vọng là gì?

Gợi ý:

- Tự tin hơn khi phỏng vấn/giao tiếp.
- Nghe hiểu câu hỏi phổ biến.
- Trả lời có cấu trúc hơn.
- Có bộ câu trả lời cá nhân hóa.
- Có vốn phrase/vocab theo ngành.
- Không bị đứng hình khi gặp câu hỏi quen thuộc.

Trả lời:

> **Không hứa fluent sau 60 ngày. Hứa user xử lý tốt hơn các tình huống interview/workplace phổ biến và tự tin nói 1–2 phút về bản thân/công việc.**
>
> Outcome tối thiểu sau 60 ngày:
>
> - Trả lời được 10–20 câu hỏi/tình huống interview/workplace phổ biến.
> - Nói 1–2 phút về bản thân, kinh nghiệm, công việc hoặc project ít ngập ngừng hơn.
> - Có bộ sample answers cá nhân hóa theo profile/ngành nghề.
> - Có vốn phrase/vocab thực dụng theo ngành.
> - Shadowing được các đoạn ngắn với nhịp và phát âm tốt hơn.
> - Có before/after recordings để nghe lại tiến bộ.
> - Không bị đứng hình khi gặp các câu hỏi quen thuộc.
>
> Outcome nên diễn đạt là **interview/workplace readiness**, không phải “fluent English”.

---

