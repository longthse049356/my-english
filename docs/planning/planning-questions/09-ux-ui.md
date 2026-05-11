---
doc_type: planning-shard
stage: discovery
load_policy: on_explicit_request
size_warning: normal
source_file: PLANNING_QUESTIONS.md
source_section: "§9 UX / UI"
summary: "UX patterns, UI design decisions, and interaction design principles."
---

**Related:** [PLANNING_QUESTIONS.md](../../PLANNING_QUESTIONS.md) | [Product Brief](../../_bmad-output/planning-artifacts/product-brief.md)

## 10. Data / Privacy / Storage

### Q50. User data gồm những gì?

Gợi ý:

- Profile.
- Goals/level/industry/context.
- Lessons.
- Attempts.
- Recordings.
- Transcripts.
- Feedback.
- Vocab cards.
- Sticky notes.
- Progress.
- AI usage logs.

Trả lời:

> **User data nên được inventory theo nhóm, có sensitivity/retention/delete policy rõ ràng.**
>
> Nhóm dữ liệu chính:
>
> 1. **Account/Auth data**
>    - userId, email, login provider, createdAt.
>
> 2. **Learning profile**
>    - level, goal, native language, industry/role, target situations, daily time, preferred accent/voice, coach tone, feedback language.
>
> 3. **Lesson data**
>    - lessonId, topic, prompt/question, target phrases, sample answer, TTS audio, lesson status.
>
> 4. **Attempt data**
>    - attemptId, lessonId, timestamp, duration, retry count, input mode, completion state.
>
> 5. **Recording data**
>    - user audio, local/cloud location, retention, delete status, backup opt-in.
>
> 6. **Transcript data**
>    - STT transcript, user-corrected transcript, STT provider/model, confidence if available.
>
> 7. **Feedback/score data**
>    - feedback items, better sentence, rubric version, practice score, component scores, next action.
>
> 8. **Vocabulary/notes/review data**
>    - saved phrases, vocab cards, IPA/audio, sticky notes, correction notes, review status, due dates.
>
> 9. **Progress data**
>    - streak, completed lessons, speaking minutes, weak areas, weekly insights, score trends.
>
> 10. **AI/provider logs**
>    - provider/model, task type, prompt version, usage, latency, cost/quota, sanitized input/output summary.
>
> 11. **Privacy settings**
>    - auto-save recording, cloud backup, retention period, delete/export preferences, AI processing consent.
>
> Data minimization rule:
>
> **Lưu đủ để cá nhân hóa và đo tiến bộ, nhưng không lưu raw audio/prompt nhạy cảm lâu hơn mức cần thiết.**

---

### Q51. Audio recording có được coi là dữ liệu nhạy cảm không?

Thông tin hiện tại:

- Trong private app, user đánh giá không quá nhạy cảm.
- Nhưng nếu public, vẫn phải xem là dữ liệu riêng tư cần bảo vệ.

Trả lời:

> **Có. Dù private app, audio recording vẫn nên được xem là dữ liệu cá nhân nhạy cảm/riêng tư.**
>
> Lý do:
>
> - Giọng nói có thể nhận dạng cá nhân.
> - Nội dung nói có thể chứa thông tin công việc, kinh nghiệm, công ty, phỏng vấn, cảm xúc.
> - Audio có thể chứa tiếng nền hoặc thông tin vô tình.
> - Transcript từ audio cũng nhạy cảm gần tương đương audio.
>
> Thiết kế cần:
>
> - micro chỉ bật khi user chủ động record;
> - trạng thái recording rõ ràng;
> - user nghe lại/xóa được;
> - local-first mặc định;
> - cloud backup opt-in;
> - không dùng training nếu chưa có consent riêng.
>
> Product rule:
>
> **Treat voice as private user content even if the first version is for family/friends.**

---

### Q52. Cloud backup recording có bật mặc định không?

Gợi ý:

- Không. Nên opt-in.

Trả lời:

> **Không. Cloud backup cho user recordings không nên bật mặc định.**
>
> Default:
>
> - recording lưu local-first;
> - metadata/transcript/score có thể sync nếu cần progress;
> - audio cloud backup chỉ bật khi user chọn.
>
> Khi user bật cloud backup, UI cần nói rõ:
>
> - dữ liệu nào được backup: audio, transcript, feedback;
> - mục đích: đồng bộ thiết bị, nghe lại lịch sử, phục hồi dữ liệu;
> - thời gian lưu;
> - cách tắt/xóa.
>
> Nên có options:
>
> - Không sao lưu audio.
> - Chỉ lưu transcript/feedback.
> - Sao lưu audio + transcript.
> - Xóa toàn bộ cloud backup.
>
> Product rule:
>
> **Cloud backup is convenience, not default. User must choose it.**

---

### Q53. Transcript có lưu mặc định không?

Gợi ý:

- Nên lưu vì phục vụ feedback, search, progress, weekly insight.
- User phải có quyền xóa.

Trả lời:

> **Có thể lưu transcript mặc định cho learning progress, nhưng phải minh bạch và cho user xóa/tắt.**
>
> Transcript rất hữu ích vì:
>
> - AI feedback cần transcript;
> - progress tracking cần dữ liệu text;
> - review queue/weekly insight cần lỗi và phrase;
> - user có thể search lại câu/lỗi/vocab.
>
> Nhưng transcript cũng nhạy cảm, nên cần:
>
> - privacy copy rõ;
> - quyền xóa transcript theo attempt;
> - quyền xóa cùng audio;
> - option tắt lưu transcript dài hạn nếu user muốn;
> - ghi rõ transcript do AI tạo có thể sai.
>
> Đề xuất:
>
> - Transcript được tạo và lưu cùng attempt để phục vụ feedback/progress.
> - Nếu user xóa attempt, có thể xóa transcript + feedback liên quan.
> - Nếu user bật privacy mode, transcript chỉ dùng tạm để feedback rồi xóa sau TTL ngắn.
>
> Product rule:
>
> **Transcript is core learning memory, but user owns and can delete it.**

---

### Q54. Có cần privacy copy rõ trong UI không?

Gợi ý:

- Có.
- Ví dụ: “Record privately. You can delete anytime.”

Trả lời:

> **Có. Privacy copy phải xuất hiện ngay tại điểm user record/upload, không chỉ trong Privacy Policy.**
>
> Copy nên ngắn, cụ thể, không legalese.
>
> Ví dụ ở recorder:
>
> `Recording is private. You can delete it anytime.`
>
> Tiếng Việt:
>
> `Bản ghi của bạn chỉ dùng để tạo feedback luyện nói. Bạn có thể xóa bất cứ lúc nào.`
>
> Trước khi xin quyền mic:
>
> `SpeakFit cần micro để nghe bạn luyện nói. Bạn cũng có thể gõ trước nếu chưa tiện nói.`
>
> Khi dùng AI provider:
>
> `Audio/transcript có thể được xử lý bởi nhà cung cấp AI để tạo transcript và feedback.`
>
> Trong settings:
>
> - auto-save recording;
> - cloud backup;
> - retention;
> - delete/export data.
>
> Product rule:
>
> **Privacy copy should answer: what is recorded, why, where it goes, how to delete.**

---

### Q55. Có gửi audio/text sang MiniMax không và thông báo ra sao?

Gợi ý:

- Nếu dùng AI provider để generate/feedback/STT, cần thông báo rõ.
- Có thể có privacy note trong onboarding/settings.

Trả lời:

> **Có thể gửi audio/text/transcript sang MiniMax hoặc provider AI khác nếu cần STT/TTS/feedback, nhưng phải thông báo rõ và chỉ gửi dữ liệu tối thiểu.**
>
> Luồng nên là:
>
> `App → SpeakFit backend → MiniMax/STT/LLM/TTS provider → SpeakFit → App`
>
> Không nên gửi:
>
> - email;
> - tên thật;
> - payment info;
> - device ID;
> - dữ liệu profile không cần thiết.
>
> Nên dùng pseudonymous user/session ID.
>
> Copy gợi ý:
>
> `Để tạo transcript, audio hoặc feedback, SpeakFit có thể gửi audio/văn bản của bạn đến nhà cung cấp AI như MiniMax. Dữ liệu này chỉ dùng để cung cấp tính năng học tập và được xử lý theo chính sách bảo mật của nhà cung cấp.`
>
> Privacy Policy nên liệt kê:
>
> - provider nào;
> - dùng cho task gì: STT, TTS, feedback, lesson generation;
> - retention/vendor policy nếu biết;
> - có dùng training không;
> - cách user xóa dữ liệu.
>
> Product rule:
>
> **No hidden AI data sharing. Tell user at the point of use and in settings/privacy policy.**

---
