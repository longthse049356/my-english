---
doc_type: idea-brief-shard
stage: discovery
load_policy: on_explicit_request
size_warning: large
source_file: IDEA_BRIEF.md
source_section: "§14 Council Brainstorm"
summary: "Feature-rich AI learning system brainstorm session."
---

**Related:** [IDEA_BRIEF.md](../../IDEA_BRIEF.md) | [Product Brief](../../_bmad-output/planning-artifacts/product-brief.md)

## 14. Council Brainstorm — Feature-Rich AI Learning System

### 14.1 Product Manager Summary

Các feature cluster nên có:

- Persona & learning profile.
- AI daily lesson generator.
- 60-day learning path.
- Lesson structure chuẩn.
- Vocabulary & phrase system.
- TTS & listening practice.
- Shadowing & recording.
- AI feedback.
- Sample answer/script nói.
- Review & spaced repetition.
- Word history.
- Pronunciation per word.
- Prefix/suffix/root tips.
- Mnemonic tips.
- Text-to-video.
- YouTube shadowing.
- Progress tracking.
- Personal notes.
- Content quality control.

PM nhấn mạnh core trước mắt không phải “nhiều tính năng”, mà là một daily learning loop đủ tốt:

1. User chọn mục tiêu/persona.
2. App generate bài theo profile và history.
3. User học context, question/passage, vocab/phrases.
4. User nghe TTS và shadowing.
5. User ghi âm hoặc nhập câu trả lời.
6. AI feedback.
7. User xem sample answer.
8. User lưu note/từ/câu hay.
9. App đưa vào review.

### 14.2 UX Designer Summary

UX đề xuất ideal daily lesson flow:

1. Check-in nhanh: mood/energy/mode học.
2. Warm-up.
3. Context + question.
4. Passage hoặc tình huống chính.
5. Vocab focus: 5–8 từ/cụm quan trọng.
6. Listen & repeat.
7. Shadowing.
8. AI feedback ngắn, chỉ 1–3 điểm cần sửa.
9. Sample answer theo level.
10. Personal answer.
11. Review & save.

Home/dashboard nên tập trung vào:

- Day X/60.
- Chủ đề hôm nay.
- Persona hôm nay.
- CTA chính: bắt đầu bài hôm nay.
- Review queue.
- Progress map 60 ngày.
- Today focus.

Rủi ro UX:

- Quá nhiều feature làm user không biết bắt đầu từ đâu.
- Daily lesson quá dài.
- Feedback quá nhiều gây nản.
- Note/vocab thành kho rác nếu không có review queue.
- YouTube có thể gây distraction nếu không giới hạn đoạn ngắn.
- Recording anxiety: user có thể ngại ghi âm.

### 14.3 Architect Summary

Các domain module chính:

- Onboarding & Persona.
- Learning Plan.
- Lesson Engine.
- AI Content Generation.
- Speaking & Shadowing.
- Vocabulary & Linguistics.
- Media & Transcript.
- Progress & Analytics.
- PWA/Core Platform.

Data entities chính:

- User, UserProfile, Persona, LearningGoal.
- LearningPlan, PlanDay, Lesson, LessonBlock, Exercise.
- Prompt, GeneratedContent, MediaAsset, TTSAsset, VideoAsset.
- Recording, Transcript, TranscriptSegment, ShadowingSession.
- PronunciationFeedback, WritingFeedback.
- VocabularyItem, VocabularyNote, WordAnalysis.
- UserProgress, LessonAttempt, ExerciseAttempt.
- ContentHistory, ContentFingerprint, RecommendationContext.
- AIJob, AIProviderCall, DeduplicationRecord.

AI pipeline gợi ý:

1. Onboarding tạo learner profile.
2. Sinh learning plan 60 ngày.
3. Mỗi ngày build context từ profile + history + weak skills.
4. AI generate lesson outline.
5. Validate schema.
6. Dedup bằng hash/embedding/topic/vocab overlap.
7. Generate lesson blocks.
8. Generate TTS/video nếu cần.
9. User học/record.
10. AI feedback.
11. Update weakness profile và review queue.

Dedup approach:

- Exact dedup bằng normalized text hash.
- Near-duplicate dedup bằng semantic embedding.
- Topic fatigue control.
- Vocabulary overlap control.
- Prompt/exercise format rotation.
- YouTube segment dedup theo videoId/start/end/transcript hash.

### 14.4 Skeptic Summary

Skeptic cảnh báo rủi ro lớn nhất là quá nhiều “đồ chơi” trước khi chứng minh core loop.

Feature dễ làm loãng:

- Multi-persona quá rộng.
- Flexible lesson types quá nhiều.
- YouTube + vocab + IPA + root + feedback + video cùng lúc.
- Text-to-video trong MVP.

Rủi ro cost/kỹ thuật:

- AI text/TTS/video/feedback tốn chi phí và latency.
- Video generation đắt, chậm, khó kiểm soát chất lượng.
- Pronunciation feedback nghiêm túc cần pipeline phức tạp.
- Personalization tăng số nhánh prompt/content/test.

Nguyên tắc để không chết vì scope:

- Idea phase được phép rộng.
- MVP phase phải hẹp.
- Vision có thể là AI English coach 60 ngày.
- MVP nên giữ 1–2 daily loop rõ ràng trước, sau đó mở rộng.

### 14.5 Optimist Summary

Best-case vision:

Một AI Personal English Coach 60 ngày dạng PWA, nơi mỗi người học có lộ trình riêng, persona riêng, giọng nói riêng, nội dung riêng, tốc độ riêng.

Wow moments tiềm năng:

- Paste YouTube link → app biến thành bài shadowing có transcript, dịch, từ vựng, quiz và luyện nói.
- AI phát hiện lỗi lặp lại và tự tạo bài sửa lỗi.
- App tạo hội thoại bằng chính tên, công việc, sở thích của user.
- User nói một câu → app đưa bản native-like và giải thích lỗi.
- Một từ mới có IPA, audio, collocations, root/prefix/suffix, mnemonic và ví dụ cá nhân hóa.
- App tạo crash course 24 giờ nếu user sắp phỏng vấn.
- Cuối tuần app tạo progress summary: số phút nói, lỗi đã giảm, từ đã dùng được.

Định hướng dài hạn:

- Learner profile sống.
- Mistake memory.
- Personal phrasebook.
- Adaptive roadmap.
- Multi-coach persona.
- Life-based learning từ chính công việc/email/cuộc sống của user.
