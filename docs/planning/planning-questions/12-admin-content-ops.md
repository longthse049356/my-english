---
doc_type: planning-shard
stage: discovery
load_policy: on_explicit_request
size_warning: normal
source_file: PLANNING_QUESTIONS.md
source_section: "§12 Admin / Content Ops"
summary: "Content management, admin tools, and operational workflows."
---

**Related:** [PLANNING_QUESTIONS.md](../../PLANNING_QUESTIONS.md) | [Product Brief](../../_bmad-output/planning-artifacts/product-brief.md)

## 13. Validation / Testing

### Q65. Có chạy test thủ công 7–14 ngày trước khi build đầy đủ không?

Gợi ý:

- Google Sheet + Zalo/Telegram + ChatGPT.
- Mỗi ngày 1 câu hỏi.
- User record 1–2 phút.
- Gửi feedback, điểm, sample answer.
- Đo học 5/7 ngày không.

Trả lời:

> **Có. Nên chạy test thủ công 7–14 ngày trước khi build đầy đủ.**
>
> Đây là cách rẻ nhất để kiểm chứng core assumption:
>
> **User có quay lại luyện nói mỗi ngày, nhận feedback và thấy tiến bộ không?**
>
> Test setup:
>
> - Google Sheet/Notion để quản lý bài.
> - Zalo/Telegram để gửi mission.
> - User record voice 1–2 phút/ngày.
> - AI/ChatGPT/MiniMax hỗ trợ feedback + sample answer.
> - Manual tracking completion/confidence.
>
> Mỗi ngày gửi:
>
> 1. Một câu hỏi/tình huống.
> 2. 3–5 phrases/vocab.
> 3. Một sample answer ngắn.
> 4. User recording.
> 5. Feedback: 1 điểm tốt, 1–2 điểm cần sửa, better sentence, next action.
> 6. Review 1–3 phrase cũ.
>
> Metrics cần đo:
>
> - học >= 5/7 ngày không;
> - số recordings;
> - user có retry không;
> - feedback có được xem là hữu ích không;
> - user có nhớ/dùng lại phrases không;
> - confidence trước/sau;
> - user có muốn tiếp tục sau 7–14 ngày không.
>
> Product rule:
>
> **Validate behavior before building automation. If manual loop không giữ được user, app cũng khó giữ.**

---

### Q66. Ai là 3–5 user test đầu tiên?

Gợi ý:

- Người tạo dự án.
- Vợ.
- 1–3 bạn bè có nhu cầu phỏng vấn/workplace English.

Trả lời:

> **User test đầu tiên nên là 5–8 người thật có pain rõ, bắt đầu từ nhóm gần nhất nhưng đủ đa dạng.**
>
> Nhóm đề xuất:
>
> 1. **Bạn / người tạo dự án**
>    - Software Engineer.
>    - Cần luyện English interview/project explanation.
>    - Là power user kiêm product owner.
>
> 2. **Vợ**
>    - Purchasing/garment/business context.
>    - Cần workplace communication, supplier/vendor, interview.
>
> 3. **1 Software Engineer khác**
>    - Chuẩn bị interview hoặc muốn apply remote/global.
>
> 4. **1 business/procurement/supply-chain professional**
>    - Gần persona của vợ nhưng không phải người nhà để giảm bias.
>
> 5. **1 General Professional A2/B1**
>    - Người đi làm cần nói tiếng Anh công việc nhưng không thuộc 2 ngành chính.
>
> Nếu có thể mở rộng lên 8 người:
>
> - thêm 1 fresher chuẩn bị phỏng vấn;
> - thêm 1 người B1+ để xem app có đủ hữu ích với level cao hơn;
> - thêm 1 người rất ngại speaking để kiểm tra anxiety UX.
>
> Không nên chỉ test với người thân vì feedback dễ thiên vị. Nhưng cũng không cần tuyển rộng ngay.
>
> Test cần quan sát:
>
> - họ có hiểu app dùng để làm gì không;
> - có dám record không;
> - có retry sau feedback không;
> - có quay lại ngày 2/3/7 không;
> - phrase/vocab có được dùng lại không.
>
> Product rule:
>
> **Test with people who feel the pain now, not people who only say “idea hay”.**

---

### Q67. Tiêu chí thành công sau 7 ngày là gì?

Gợi ý:

- User học >= 5/7 ngày.
- Record >= 5 câu trả lời.
- Confidence tăng nhẹ.
- User nói muốn dùng tiếp.

Trả lời:

> **Sau 7 ngày, success là hình thành được hành vi luyện nói ngắn và user thấy feedback có ích.**
>
> Không tính active day là “mở app”. Active day phải là:
>
> **User hoàn thành ít nhất 1 speaking/shadowing loop: nghe → nói/shadow → nhận feedback → xem/sửa → optionally retry.**
>
> Metrics đề xuất cho small test 5–8 người:
>
> - 60% user học ít nhất 4/7 ngày.
> - 40% user học ít nhất 5/7 ngày.
> - Mỗi user engaged record/shadow ít nhất 5 attempts trong tuần.
> - Ít nhất 50% attempts có feedback được xem.
> - Ít nhất 30% attempts có retry sau feedback.
> - Ít nhất 50% user lưu hoặc dùng lại 3+ phrases/vocab.
> - Ít nhất 50% user nói feedback “cụ thể và biết sửa gì”.
>
> Qualitative signals tốt:
>
> - `Mỗi ngày làm 1 bài như vậy được.`
> - `Feedback giúp tôi biết cần sửa gì.`
> - `Tôi thấy nói đỡ ngại hơn.`
> - `Tôi muốn bài ngày mai đúng công việc của tôi hơn.`
> - `Tôi muốn nghe lại recording cũ để so sánh.`
>
> Red flags:
>
> - User chỉ dùng ngày 1 rồi bỏ.
> - User đọc feedback nhưng không retry.
> - User thấy feedback chung chung.
> - User không biết hôm sau nên học gì.
> - User thấy record voice quá áp lực.
>
> Product rule:
>
> **7 ngày validate activation + early habit, không phải long-term retention.**

---

### Q68. Tiêu chí thành công sau 14 ngày là gì?

Gợi ý:

- User vẫn quay lại.
- Có ít nhất 8–10 speaking sessions.
- Có phrase/vocab dùng lại được.
- User cảm thấy app giúp biết hôm nay luyện gì.

Trả lời:

> **Sau 14 ngày, success là user bắt đầu xem SpeakFit như một routine luyện speaking đáng tin cậy.**
>
> Metrics đề xuất:
>
> - 40–50% user active ít nhất 6/14 ngày.
> - 25–30% user active ít nhất 8/14 ngày.
> - 25% user hoàn thành 10+ speaking/shadowing loops.
> - 20–30% user có retry behavior đều đặn.
> - 50% user có ít nhất 5 phrases/vocab được review lại.
> - 30% user dùng lại phrase/vocab đã học trong attempt mới.
> - 50% user nói app giúp họ biết “hôm nay nên luyện gì”.
> - 30% user nói họ muốn tiếp tục thêm 2 tuần.
>
> Strong traction signals:
>
> - User tự học khi không bị nhắc.
> - User hỏi “có plan 30/60 ngày không?”.
> - User muốn thêm topic theo công việc của họ.
> - User rủ người khác học cùng.
> - User nói sẵn sàng trả tiền cho feedback/mock interview.
>
> Learning signals:
>
> - User nói dài hơn Day 1.
> - Ít pause/filler hơn.
> - Dùng được phrase đã review.
> - Confidence self-rating tăng.
> - User nhận ra lỗi lặp lại của mình.
>
> Vanity metrics cần tránh:
>
> - total signups;
> - số bài đã mở;
> - số phút online;
> - số feedback generated nhưng user không đọc/retry;
> - số vocab lưu nhưng không review/dùng lại.
>
> Product rule:
>
> **14 ngày validate perceived progress + willingness to continue. Nếu user quay lại vì muốn nói tốt hơn hôm qua, hướng đi đúng.**

---
