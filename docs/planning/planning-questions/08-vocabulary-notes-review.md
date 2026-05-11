---
doc_type: planning-shard
stage: discovery
load_policy: on_explicit_request
size_warning: normal
source_file: PLANNING_QUESTIONS.md
source_section: "§8 Vocabulary / Notes / Review"
summary: "Vocabulary saving, review queue, and spaced repetition mechanics."
---

**Related:** [PLANNING_QUESTIONS.md](../../PLANNING_QUESTIONS.md) | [Product Brief](../../_bmad-output/planning-artifacts/product-brief.md)

## 9. UX / UI

### Q45. Mobile-first có phải bắt buộc không?

Thông tin hiện tại:

- Ban đầu nghĩ mobile-first.
- Sau khi cân nhắc lại, desktop nên là trải nghiệm chính cho phase đầu.
- Mobile vẫn cần responsive tốt, nhưng không quyết định core UX.

Trả lời:

> **Không. Với SpeakFit phase đầu, nên chuyển sang desktop-first hoặc desktop-primary, mobile-friendly.**
>
> Lý do:
>
> - User học speaking/interview/workplace English nghiêm túc sẽ dễ tập trung hơn trên desktop.
> - Desktop thao tác tốt hơn cho các function core: đọc prompt, nghe audio, record, xem transcript, xem feedback, sửa câu, lưu phrase/vocab, mở notes.
> - Interview practice tự nhiên hơn trên laptop vì giống bối cảnh phỏng vấn online thật.
> - User có thể dùng tai nghe/micro tốt hơn, ít bị gián đoạn hơn điện thoại.
> - Desktop cho phép layout nhiều panel: lesson content, recorder, feedback, vocab/notes, progress.
> - Giai đoạn MVP cần validate core learning loop trước; desktop giúp giảm friction UI và dễ debug/test hơn.
>
> Mobile vẫn phải dùng tốt cho:
>
> - review vocab/phrases ngắn;
> - nghe lại audio;
> - xem feedback cũ;
> - quick shadowing;
> - daily reminder/continue lesson;
> - PWA access khi không ngồi máy tính.
>
> Nguyên tắc desktop-primary:
>
> - Core lesson/practice screen tối ưu cho laptop trước.
> - Layout nên có không gian cho transcript + feedback + notes cùng lúc.
> - Recorder/audio controls phải rõ, ổn định, không bị che bởi mobile UI constraint.
> - Keyboard/mouse flow phải nhanh.
> - Desktop không được biến thành dashboard phức tạp; vẫn cần một action chính mỗi màn hình.
> - Mobile là responsive companion, không phải experience chính trong MVP.
>
> Product rule:
>
> **Build the best focused desktop learning loop first, then make mobile excellent for review and lightweight practice.**

---

### Q46. Bottom navigation có chốt là Home · Lessons · Review · Notes · Coach không?

Thông tin hiện tại:

- Đây là nav đang được đề xuất.

Trả lời:

> **Có thể chốt: Home · Lessons · Review · Notes · Coach.**
>
> Đây là cấu trúc phù hợp với mental model của SpeakFit:
>
> 1. **Home**
>    - Today’s Mission.
>    - Progress snapshot.
>    - Practice queue nhỏ.
>
> 2. **Lessons**
>    - Current plan.
>    - Recent/generated lessons.
>    - Continue unfinished lesson.
>    - Create lesson nếu cần.
>
> 3. **Review**
>    - Vocab/phrases due.
>    - Weak phrases.
>    - Speaking corrections.
>    - Sticky notes cần ôn.
>
> 4. **Notes**
>    - Saved phrases.
>    - Vocabulary cards.
>    - Sticky/correction notes.
>    - AI chat insights.
>
> 5. **Coach**
>    - Coach settings.
>    - Learning profile.
>    - Weekly insight.
>    - Next recommended focus.
>    - Privacy/data controls.
>
> Không nên đổi `Lessons` thành `Practice` quá sớm nếu tab này còn chứa plan/history/library. `Review` nên tách riêng vì đây là retention loop quan trọng.
>
> Product rule:
>
> **Home dẫn vào action hôm nay; Lessons lưu lộ trình; Review giữ trí nhớ; Notes lưu ký ức học; Coach cá nhân hóa.**

---

### Q47. Coach tab phase đầu làm gì?

Gợi ý:

- Coach settings.
- Coach tone.
- Active learning profile.
- AI guidance/history.
- General learning suggestions.
- Không nhất thiết là chat tự do toàn app.

Trả lời:

> **Phase đầu Coach tab nên là control center + guidance surface, không phải chat tự do toàn app.**
>
> Coach tab nên gồm:
>
> 1. **Active learning profile**
>    - goal;
>    - level;
>    - industry/role;
>    - current track;
>    - session length;
>    - preferred accent/voice.
>
> 2. **Coach settings**
>    - tone: gentle/professional/direct;
>    - feedback language: Vietnamese/bilingual;
>    - feedback detail level;
>    - reminder preference.
>
> 3. **Guidance / insights**
>    - this week focus;
>    - recurring mistakes;
>    - recommended lesson/review;
>    - progress encouragement.
>
> 4. **Privacy/data controls**
>    - auto-save recording;
>    - cloud backup opt-in;
>    - retention setting;
>    - delete recordings/transcripts/feedback.
>
> Chatbox tự do toàn app nên để sau. Phase đầu chatbox chủ yếu nằm trong lesson context để tránh loãng UX và giảm cost.
>
> Product rule:
>
> **Coach là nơi user hiểu và kiểm soát cách app cá nhân hóa việc học, không phải chatbot tổng quát.**

---

### Q48. Lesson page layout nên gồm các block nào?

Gợi ý:

1. Goal/context.
2. Main question/passage.
3. Vocab/phrases.
4. Audio player.
5. Shadowing chunks.
6. Recorder.
7. Feedback.
8. Sample answer.
9. Save/review actions.

Trả lời:

> **Lesson page nên là block-based flow, tập trung vào một phiên luyện nói cụ thể.**
>
> Layout đề xuất:
>
> 1. **Goal / Context block**
>    - Hôm nay luyện gì.
>    - Liên quan gì đến goal của user.
>    - Thời lượng/difficulty.
>
> 2. **Main prompt / situation block**
>    - Interview question, workplace situation, passage hoặc roleplay prompt.
>
> 3. **Key phrases / vocab block**
>    - 3–7 phrases/từ quan trọng.
>    - Có Save, Listen, Speak.
>    - Có tips/mnemonic nếu phù hợp.
>
> 4. **Audio player block**
>    - Nghe câu hỏi/sample/chunks.
>    - Slow/normal speed.
>
> 5. **Shadowing block**
>    - Chunk → sentence → full answer.
>    - Repeat/retry.
>
> 6. **Recorder block**
>    - Record attempt.
>    - Replay.
>    - Retry.
>    - Privacy copy ngắn.
>
> 7. **Transcript block**
>    - STT transcript.
>    - User sửa nếu sai.
>    - Ghi rõ feedback dựa trên transcript.
>
> 8. **Feedback block**
>    - 1 điểm tốt.
>    - 1–2 điểm cần củng cố.
>    - Better sentence.
>    - Next action.
>
> 9. **Sample / better answer block**
>    - Với interview lesson, nên show sau first attempt hoặc sau scaffold.
>
> 10. **Save / review / completion block**
>    - Save phrase.
>    - Save correction.
>    - Add to review.
>    - Mission completed/prepared.
>
> Architecture nên lưu lesson dưới dạng `LessonBlock[]` để dễ personalize, A/B test, regenerate từng phần và analytics theo block.

---

### Q49. Feedback hiển thị thế nào để không gây nản?

Gợi ý:

- Positive first.
- Short.
- One next action.
- Avoid words like failed/wrong/weak.
- Use “củng cố”, “luyện thêm”, “gần thành thạo”.

Trả lời:

> **Feedback UI nên tích cực trước, ngắn, cụ thể, và luôn dẫn tới retry.**
>
> Format mặc định:
>
> 1. **Điểm tốt**
>    - `Bạn trả lời đúng ý chính.`
>    - `Bạn dùng được phrase “I was responsible for...” khá tự nhiên.`
>
> 2. **Cần củng cố**
>    - Dùng từ: `củng cố`, `luyện thêm`, `nói tự nhiên hơn`, `gần đúng rồi`.
>    - Tránh: `wrong`, `failed`, `bad`, `weak`, `sai quá nhiều`.
>
> 3. **Better sentence**
>    - Your sentence → Better sentence.
>    - Giải thích tiếng Việt ngắn.
>
> 4. **Next action**
>    - `Thử nói lại câu này một lần nữa.`
>    - `Lần retry chỉ cần sửa past tense.`
>    - `Hãy dùng phrase này trong câu trả lời mới.`
>
> Score nếu có nên nhỏ, không để điểm đỏ lớn chiếm spotlight. Có thể dùng state nhẹ:
>
> - Needs practice
> - Improving
> - Good
> - Strong
>
> Product rule:
>
> **Feedback không phải để chứng minh user sai; feedback để user biết lần nói tiếp theo cần làm gì.**

---
