---
doc_type: planning-shard
stage: discovery
load_policy: on_explicit_request
size_warning: normal
source_file: PLANNING_QUESTIONS.md
source_section: "§2 Target Users / Personas"
summary: "Target user profiles, personas, and user segmentation for SpeakFit English."
---

**Related:** [PLANNING_QUESTIONS.md](../../PLANNING_QUESTIONS.md) | [Product Brief](../../_bmad-output/planning-artifacts/product-brief.md)

## 3. MVP Boundary

### Q13. Nếu chỉ build trong 4 tuần, bắt buộc có gì?

Core đề xuất:

- Google login.
- 1 active learning profile.
- Onboarding cơ bản.
- AI-generated daily lesson.
- TTS script ngắn.
- Shadowing chunks.
- User recording + replay.
- Feedback ngắn.
- Vocabulary/sticky save cơ bản.
- Progress snapshot.

Trả lời:

> **MVP 4 tuần phải cực hẹp: chứng minh daily speaking/shadowing loop có giá trị.**
>
> Bắt buộc có:
>
> 1. Google login hoặc auth đơn giản.
> 2. 1 active learning profile.
> 3. Onboarding 3 bước: goal, level tự đánh giá, context nghề/ngành.
> 4. Daily mission 5–10 phút.
> 5. Một flow luyện chính: listen → shadow → record → replay → feedback → retry.
> 6. TTS/audio mẫu cho script ngắn.
> 7. Recorder mobile-first, nút lớn, retry 1 chạm.
> 8. Feedback AI ngắn: 1 điểm tốt, 1–2 điểm cần sửa, 1 next action.
> 9. Progress rất đơn giản: ngày đã học, số recordings, streak mềm.
> 10. Một bộ lesson seed nhỏ hoặc AI-generated lesson theo template cố định.
>
> Không nên cố nhồi đầy đủ interview library, workplace library, dashboard lớn, review queue phức tạp hay multi-profile trong 4 tuần.

---

### Q14. Nếu chỉ build trong 8 tuần, thêm gì?

Gợi ý:

- Review queue.
- STT/transcript.
- Better AI feedback.
- Lesson history.
- TTS cache tốt hơn.
- Usage tracking.
- Notes tab.
- Basic weekly insight nếu đủ data.

Trả lời:

> **MVP 8 tuần có thể thêm chiều sâu cho loop, không mở rộng quá nhiều chiều ngang.**
>
> Nên thêm:
>
> 1. STT/transcript nếu provider/cost ổn.
> 2. Lesson history và recording history cơ bản.
> 3. Review queue đơn giản cho vocab/phrases/feedback cũ.
> 4. Notes hoặc saved phrases cơ bản.
> 5. Better feedback dựa trên transcript: grammar, clarity, vocabulary, structure, filler words nếu có.
> 6. TTS cache/dedup nghiêm túc.
> 7. Usage tracking cho MiniMax text/TTS/feedback.
> 8. Lộ trình 7 ngày hoặc 14 ngày theo goal, chưa cần generate toàn bộ 60 ngày chi tiết.
> 9. Analytics cơ bản: activation, D1/D3/D7 retention, recording completion, lesson completion, AI cost/user.
>
> Chỉ nên mở thêm 1–2 use case rõ, ví dụ interview hoặc workplace. Không nên mở rộng cả mọi persona và mọi lesson type nếu core loop chưa chứng minh retention.

---

### Q15. Feature nào chắc chắn không cần trong MVP?

Gợi ý nên loại khỏi MVP:

- YouTube shadowing.
- Text-to-video.
- Obsidian export.
- Payment/subscription.
- Community.
- Advanced pronunciation scoring.
- Multi-profile/family mode đầy đủ.
- Admin CMS phức tạp.
- Offline-first.
- Leaderboard/gamification sâu.

Trả lời:

> **Loại khỏi MVP để tránh scope creep:**
>
> - YouTube shadowing.
> - Text-to-video / roleplay video.
> - Obsidian export/sync.
> - Payment/subscription.
> - Social/community/cohort.
> - Marketplace tutor/live teacher/video call.
> - Leaderboard/gamification sâu.
> - Multi-profile/family mode đầy đủ.
> - Admin CMS phức tạp.
> - Enterprise/B2B/classroom admin.
> - Offline-first hoàn chỉnh.
> - Native iOS/Android app.
> - Pronunciation scoring quá chi tiết ở word/phoneme level.
> - AI tự sinh toàn bộ curriculum không kiểm soát.
> - Placement test dài.
> - Dashboard nhiều số liệu.
>
> Nguyên tắc: MVP chỉ cần chứng minh user có quay lại mỗi ngày để luyện nói, nhận feedback và thấy tiến bộ không.

---

### Q16. Điều gì nếu không có thì sản phẩm mất linh hồn?

Gợi ý:

- Daily mission.
- Speaking/shadowing.
- Personalized lesson.
- Feedback giúp user nói tốt hơn.
- Progress cảm nhận được.

Trả lời:

> **Linh hồn của SpeakFit là daily voice coaching loop: mỗi ngày user nói thật, được sửa nhẹ, thử lại, và thấy mình tiến bộ.**
>
> Nếu thiếu vòng lặp này, SpeakFit sẽ dễ trở thành một app học tiếng Anh tổng hợp hoặc một chatbot AI khác. Linh hồn không nằm ở số lượng lesson, AI chat, kho từ vựng, grammar explanation hay dashboard đẹp. Linh hồn nằm ở khoảnh khắc:
>
> **User nói lần 1 → app chỉ ra 1 điểm cần sửa → user nói lại → lần 2 nghe tốt hơn thật.**
>
> 5 thành phần không được thiếu:
>
> 1. **Daily Mission**
>    - User mở app lên phải biết ngay hôm nay luyện gì.
>    - Mission ngắn, rõ, có context thật: phỏng vấn, công việc, project, supplier, meeting.
>    - Không để user tự browse quá nhiều.
>
> 2. **Voice-first practice**
>    - User phải nói thành tiếng, record, nghe lại hoặc shadow.
>    - Text chỉ là fallback hoặc bước chuẩn bị, không phải core.
>    - Nếu user chỉ đọc/nghe/xem sample, app mất bản chất speaking coach.
>
> 3. **Feedback ngắn, song ngữ, không phán xét**
>    - 1 điểm tốt.
>    - 1–2 điểm cần sửa.
>    - 1 câu/cụm từ thay thế dùng được ngay.
>    - Tránh feedback dài kiểu bài chấm thi vì dễ làm user sợ nói.
>
> 4. **Retry / nói lại**
>    - Đây là điểm tạo cảm giác tiến bộ tức thì.
>    - Sau feedback, app nên mời user nói lại một câu/cụm nhỏ, không bắt record lại cả bài dài.
>
> 5. **Progress memory**
>    - App phải nhớ user đang luyện gì, đã nói gì, hay sai gì, đã lưu phrase nào, score/confidence thay đổi ra sao.
>    - Nếu không có memory, user sẽ hỏi: “Sao không dùng ChatGPT Voice?”
>
> Công thức linh hồn:
>
> **One useful speaking mission per day → speak → get one helpful correction → retry → feel progress.**

---
