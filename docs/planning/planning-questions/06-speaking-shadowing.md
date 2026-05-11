---
doc_type: planning-shard
stage: discovery
load_policy: on_explicit_request
size_warning: normal
source_file: PLANNING_QUESTIONS.md
source_section: "§6 Speaking / Shadowing"
summary: "Speaking practice mechanics, shadowing drills, and audio interaction patterns."
---

**Related:** [PLANNING_QUESTIONS.md](../../PLANNING_QUESTIONS.md) | [Product Brief](../../_bmad-output/planning-artifacts/product-brief.md)

## 7. AI / MiniMax / Feedback

### Q33. MiniMax dùng cho những capability nào phase đầu?

Thông tin hiện tại:

- User có gói Max-Highspeed.
- M2.7-highspeed quota rộng cho text/chat/lesson generation.
- Speech 2.8 có 19,000 chars/day nên TTS phải cache kỹ.

Options:

1. Text generation only.
2. Text + TTS.
3. Text + TTS + feedback.
4. Text + TTS + STT + feedback nếu provider hỗ trợ.

Trả lời:

> **Phase đầu nên dùng MiniMax cho text generation, TTS, chat/coach explanation và feedback text generation; STT tùy chất lượng/provider.**
>
> Khuyến nghị capability:
>
> 1. **Text generation**
>    - Daily lesson.
>    - Prompt/question.
>    - Sample answer.
>    - Rewrite/better answer.
>    - Vocabulary/tips/mnemonic theo lesson.
>
> 2. **TTS**
>    - Câu hỏi chính.
>    - Sample answer/script shadowing.
>    - Key phrases/vocabulary quan trọng.
>    - Không TTS mọi giải thích dài để tiết kiệm quota.
>
> 3. **AI feedback text**
>    - Tạo feedback ngắn dựa trên transcript + rubric.
>    - Song ngữ: giải thích tiếng Việt, câu mẫu tiếng Anh.
>
> 4. **Lesson chatbox**
>    - Chỉ trong context lesson.
>    - Giải thích từ, grammar, câu mẫu, tips.
>
> 5. **STT**
>    - Nếu MiniMax hỗ trợ tốt thì dùng.
>    - Nếu chưa chắc, có thể so sánh Whisper/Web Speech/Google/Azure.
>
> Product rule:
>
> **Dùng MiniMax mạnh cho text + TTS trước; STT/pronunciation scoring cần validate riêng, không khóa MVP vào một provider nếu chưa chắc.**

---

### Q34. STT/transcript có bắt buộc trong MVP không?

Gợi ý:

- Nếu có STT, feedback tốt hơn nhiều.
- Nếu chưa chắc provider/cost, MVP có thể feedback dựa trên text input/manual transcript.

Trả lời:

> **Nên có STT/transcript trong MVP nếu chất lượng/provider/cost chấp nhận được. Nếu chưa ổn, phải có fallback text/manual transcript.**
>
> Lý do STT rất quan trọng:
>
> - Feedback grammar/vocabulary/structure cần transcript.
> - Progress tracking cần dữ liệu text.
> - Review queue/weekly insight cần lỗi và phrase từ attempt.
> - User có thể nhìn thấy mình thực sự đã nói gì.
>
> MVP tối thiểu nếu có STT:
>
> - record audio;
> - STT ra transcript;
> - hiển thị transcript để user kiểm tra/sửa nếu sai;
> - AI feedback dựa trên transcript;
> - lưu transcript cùng attempt;
> - ghi chú rằng feedback có thể bị ảnh hưởng bởi STT quality.
>
> Nếu STT chưa ổn:
>
> - cho user gõ câu trả lời;
> - cho user sửa transcript thủ công;
> - feedback dựa trên text + recording metadata đơn giản;
> - pronunciation/audio feedback để phase sau.
>
> Product rule:
>
> **STT không nhất thiết phải hoàn hảo, nhưng transcript layer rất quan trọng cho feedback và memory.**

---

### Q35. AI feedback dựa trên gì?

Options:

1. User text answer.
2. STT transcript từ recording.
3. Audio analysis trực tiếp.
4. Hybrid: transcript + user correction + recording metadata.

Trả lời:

> **Nên dùng hybrid: transcript + target/sample answer + lesson rubric + user profile + attempt metadata.**
>
> Phase đầu không nên phụ thuộc vào audio analysis phức tạp. Feedback đủ tốt có thể dựa trên:
>
> - STT transcript;
> - user-corrected transcript nếu STT sai;
> - prompt/question của lesson;
> - target/sample answer;
> - lesson focus: clarity, STAR, past tense, supplier negotiation, project explanation, v.v.;
> - user level/goal/persona;
> - attempt metadata: duration, retry count, word count, pause/filler nếu có;
> - lịch sử lỗi/vocab cũ nếu có.
>
> Feedback MVP nên tập trung:
>
> - grammar;
> - vocabulary;
> - clarity;
> - structure;
> - completeness/relevance;
> - better sentence/sample answer;
> - next best action.
>
> Audio/pronunciation feedback phase đầu nên ở mức basic:
>
> - nói quá nhanh/chậm;
> - thiếu âm cuối nếu phát hiện được;
> - fluency/pause cơ bản;
> - không chấm phoneme-level quá sớm.
>
> Product rule:
>
> **Transcript is the base, rubric gives direction, user history makes it personal, audio analysis comes later.**

---

### Q36. Feedback nên chi tiết hay ngắn gọn?

Thông tin hiện tại:

- Nên ngắn gọn.
- 1 điểm tốt.
- 1–3 điểm cần sửa.
- 1 next action.
- Song ngữ.

Trả lời:

> **Feedback nên ngắn gọn mặc định, có tầng chi tiết khi user muốn xem thêm.**
>
> Sau mỗi lượt nói, user cần phản hồi nhanh để luyện tiếp, không cần một bài phân tích dài như giáo viên chấm thi.
>
> Mặc định nên có 4 phần:
>
> 1. **Điểm tốt**
>    - Một điểm cụ thể user làm được.
>
> 2. **Điểm cần sửa chính**
>    - 1–2 lỗi quan trọng nhất.
>    - Không liệt kê mọi lỗi.
>
> 3. **Better sentence / phrase**
>    - Câu sửa mẫu bằng tiếng Anh.
>
> 4. **Next action**
>    - Một hành động nhỏ: nói lại câu này, dùng phrase này, giảm tốc độ, chia câu ngắn hơn.
>
> Có thể có nút:
>
> `Xem phân tích chi tiết`
>
> Trong đó mới hiển thị grammar, vocabulary, structure, fluency, pronunciation/basic clarity.
>
> Product rule:
>
> **Feedback chính phải giúp user muốn retry ngay, không làm user thấy mình sai quá nhiều.**

---

### Q37. Rubric feedback gồm những gì?

Gợi ý:

- Clarity.
- Grammar.
- Vocabulary.
- Structure.
- Fluency.
- Pronunciation/basic pronunciation.
- Completeness.
- Confidence.

Trả lời:

> **Rubric nên có internal version đầy đủ, nhưng user-facing phải đơn giản và dễ hiểu.**
>
> Rubric đề xuất cho speaking/interview MVP:
>
> 1. **Clarity**
>    - Người nghe có hiểu ý chính không?
>
> 2. **Fluency**
>    - Có nói liền mạch không, pause/filler có quá nhiều không?
>
> 3. **Structure**
>    - Câu trả lời có mở đầu, ý chính, ví dụ/kết quả không?
>
> 4. **Grammar**
>    - Lỗi có ảnh hưởng meaning không?
>
> 5. **Vocabulary / Phrase use**
>    - Dùng từ/cụm từ có đúng context và tự nhiên không?
>
> 6. **Pronunciation / Intelligibility**
>    - Phát âm có đủ rõ để hiểu không?
>    - Không chấm accent native-like.
>
> 7. **Task completion / Relevance**
>    - Có trả lời đúng câu hỏi/tình huống không?
>
> User-facing có thể hiển thị 4–5 mục đơn giản:
>
> - Độ rõ ràng
> - Độ trôi chảy
> - Cấu trúc câu trả lời
> - Từ vựng/cụm từ
> - Ngữ pháp/phát âm cần củng cố
>
> Architecture rule:
>
> - Rubric phải có version.
> - Attempt phải lưu rubric version.
> - Không overwrite score cũ khi đổi rubric.

---

### Q38. Có practice score không?

Thông tin hiện tại:

- Có thể có.
- Phải nói rõ là practice score, không phải điểm năng lực cố định.

Trả lời:

> **Có, nên có practice score, nhưng phải framing rất rõ: đây là điểm luyện tập, không phải điểm năng lực tiếng Anh tuyệt đối.**
>
> Practice score dùng để:
>
> - theo dõi tiến bộ qua thời gian;
> - tạo động lực retry;
> - phát hiện weak points;
> - gợi ý review/next lesson.
>
> Không nên gọi là IELTS score hoặc English level score ở MVP.
>
> Wording đề xuất:
>
> - `Practice score`
> - `Speaking practice result`
> - `Estimated practice band` nếu cần benchmark, nhưng phải có disclaimer.
>
> UI nên ưu tiên trend hơn điểm tuyệt đối:
>
> - `Lần 2 rõ hơn lần 1`
> - `Fluency improved`
> - `Bạn dùng được 2 phrase mới`
>
> Có thể lưu:
>
> - overall score 0–100;
> - component scores: fluency, clarity, vocabulary, grammar, structure, pronunciation/basic clarity;
> - mastery state: `needs practice / improving / good / strong`.
>
> Product rule:
>
> **Score để luyện tốt hơn, không phải để phán xét user.**

---

### Q39. Có lưu prompt/provider call logs không?

Gợi ý:

- Nên lưu ở mức cần thiết cho debug, cost tracking, versioning.
- Tránh lưu dữ liệu nhạy cảm quá mức.

Trả lời:

> **Có, nên lưu logs ở mức cần thiết cho debug, quality, cost và versioning; nhưng phải sanitize/minimize dữ liệu nhạy cảm.**
>
> Nên lưu:
>
> - provider;
> - model;
> - task type: generate lesson, TTS, STT, feedback, vocab tips;
> - prompt template version;
> - rubric version;
> - response schema version;
> - latency;
> - token/character usage;
> - estimated cost/quota;
> - status/error;
> - input hash;
> - output summary hoặc sanitized payload nếu cần debug.
>
> Không nên lưu bừa bãi:
>
> - full raw audio;
> - API keys/secrets;
> - thông tin cá nhân không cần thiết;
> - raw prompt chứa CV/nội dung nhạy cảm nếu không có lý do rõ.
>
> Logs không nên user-facing. User chỉ cần thấy feedback dễ hiểu. Admin/dev dùng logs để:
>
> - debug feedback sai;
> - so sánh provider;
> - tối ưu prompt;
> - kiểm soát quota MiniMax;
> - audit lỗi.
>
> Architecture rule:
>
> **Prompt, rubric, provider response đều cần versioning để sau này biết feedback được tạo bằng logic nào.**

---
