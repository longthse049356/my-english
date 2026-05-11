---
doc_type: idea-brief-shard
stage: discovery
load_policy: on_explicit_request
size_warning: large
source_file: IDEA_BRIEF.md
source_section: "§6 Insight từ Council vòng 1"
summary: "First council review insights and feedback."
---

**Related:** [IDEA_BRIEF.md](../../IDEA_BRIEF.md) | [Product Brief](../../_bmad-output/planning-artifacts/product-brief.md)

## 6. Insight từ Council vòng 1

### 6.1 Product Manager

PM cho rằng nên tập trung vào một chương trình **Interview English bootcamp 60 ngày**, không làm app học tiếng Anh tổng quát.

MVP nên có:

- Onboarding: level, ngành nghề, mục tiêu phỏng vấn, thời gian học mỗi ngày.
- Daily plan 60 ngày.
- Interview question practice.
- Shadowing: nghe mẫu, lặp lại, ghi âm.
- Vocabulary theo chủ đề phỏng vấn/công việc.
- Grammar correction cho câu trả lời.
- Progress tracking: streak, ngày hoàn thành, số câu đã luyện.
- Content admin đơn giản.

Không nên đưa vào MVP quá sớm:

- Social/community.
- Quá nhiều grammar theory.
- Gamification phức tạp.
- Marketplace tutor.
- AI scoring phát âm quá chi tiết nếu chưa chắc khả thi.

Success metrics gợi ý:

- Hoàn thành onboarding và bài đầu tiên.
- Số ngày học mỗi tuần.
- Tỷ lệ hoàn thành 7 ngày, 30 ngày, 60 ngày.
- Số câu trả lời được ghi âm/luyện speaking.
- Confidence trước/sau.
- Mock interview score.
- Người dùng có cảm giác “tôi biết phải trả lời thế nào” hay không.

### 6.2 Architect

Architect đánh giá khả thi kỹ thuật cao nếu MVP tập trung vào học có cấu trúc, tracking, audio/shadowing cơ bản.

Stack gợi ý:

- Frontend/PWA: Next.js hoặc React + Vite.
- UI: Tailwind CSS + shadcn/ui.
- Backend/Auth/DB/Storage: Supabase hoặc Firebase.
- PWA/offline: Workbox hoặc vite-plugin-pwa.
- Audio recording/playback: Web Audio API / MediaRecorder.
- Speech-to-text sau này: Whisper API, Google Speech-to-Text hoặc Web Speech API.
- AI feedback sau này: OpenAI API / Claude API.

Module chính:

- Learning plan 60 ngày.
- Vocabulary.
- Listening.
- Speaking/shadowing.
- Grammar for interview.
- Interview practice.
- Gamification.
- Admin/content management.

Rủi ro kỹ thuật:

- Speech recognition/AI feedback tốn chi phí và khó chính xác.
- PWA audio recording trên iOS/Android có khác biệt.
- Content management có thể tốn công hơn code.
- Offline mode làm sync phức tạp.
- Copyright content audio/video.

### 6.3 Skeptic

Skeptic cảnh báo ý tưởng dễ thất bại nếu biến thành app học tiếng Anh tổng hợp.

Rủi ro chính:

- Người học bỏ cuộc nhanh.
- Pain point chưa đủ sắc nếu nói chung là nghe/nói/vocab/grammar.
- Cạnh tranh với ChatGPT, YouTube, ELSA, Duolingo, Anki, Cambly, Preply.
- Không rõ lợi thế nếu chỉ gom nhiều feature.
- Chất lượng nội dung là nút thắt.
- Feedback speaking khó làm tốt.
- PWA không phải vấn đề chính; người dùng quan tâm họ có tiến bộ không.

Gợi ý core loop hẹp:

1. Mỗi ngày 1 tình huống/câu hỏi phỏng vấn.
2. Người học nghe câu hỏi.
3. Người học trả lời bằng giọng nói.
4. App/AI chấm theo rubric: clarity, grammar, vocabulary, structure, confidence.
5. Gợi ý câu trả lời tốt hơn.
6. Shadow câu mẫu.
7. Lặp lại.

Test rẻ trước khi build:

- Google Sheet + Zalo/Telegram + ChatGPT trong 7–14 ngày.
- Mỗi ngày gửi 1 câu hỏi.
- Người học record câu trả lời 1–2 phút.
- Gửi feedback, điểm số, lỗi chính, câu mẫu, bài shadowing.
- Đo xem người dùng có học 5/7 ngày không, có thấy giá trị không, có muốn tiếp tục không.

### 6.4 UX Designer

UX đề xuất core journey 60 ngày chia thành 8 tuần chủ đề:

- Self-introduction.
- Experience.
- Strengths/weaknesses.
- Projects.
- Behavioral.
- Negotiation.
- Mock interview.
- Review.

Mỗi ngày nên có 1 nhiệm vụ chính 15–25 phút:

- Nghe.
- Shadowing.
- Ghi âm.
- Nhận phản hồi.
- Lưu câu/từ hay.

Nguyên tắc UX:

- Màn hình chính trả lời ngay: “Hôm nay tôi cần làm gì?”
- Onboarding tối giản: trình độ, ngành/nghề, ngày phỏng vấn, thời lượng học mỗi ngày.
- Feedback không quá nhiều để tránh làm người học nản.
- Có chế độ slow → normal → interview speed.
- Hiển thị tiến bộ cụ thể.
- Streak mềm, không phạt nặng khi bỏ lỡ.

### 6.5 Business

Business đánh giá niche tốt nếu tập trung vào English interview prep cho người Việt đã có nền tảng nhưng thiếu phản xạ phỏng vấn.

Positioning nên là:

> 60-day English interview fitness program for Vietnamese professionals.

Wedge ban đầu:

- Một nhóm cụ thể.
- Ví dụ: Software Engineers hoặc Business/Purchasing roles chuẩn bị phỏng vấn tiếng Anh.

Monetization sau này:

- Gói 60 ngày.
- Subscription thấp.
- Cohort nhỏ.
- Mock interview trả phí.
- B2B cho trung tâm/bootcamp/công ty tuyển dụng.

Dấu hiệu có thể thành sản phẩm thật:

- Người dùng quay lại mỗi ngày.
- Hoàn thành bài nói.
- Thấy tiến bộ trong 2 tuần.
- Rủ người khác dùng.
- Sẵn sàng trả tiền cho feedback/mock interview.
