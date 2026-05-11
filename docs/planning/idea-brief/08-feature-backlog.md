---
doc_type: idea-brief-shard
stage: discovery
load_policy: on_explicit_request
size_warning: large
source_file: IDEA_BRIEF.md
source_section: "§8 Feature Backlog"
summary: "Comprehensive feature ideation and backlog (beyond MVP scope)."
---

**Related:** [IDEA_BRIEF.md](../../IDEA_BRIEF.md) | [Product Brief](../../_bmad-output/planning-artifacts/product-brief.md)

## 8. Feature Backlog — ghi nhận toàn bộ ý tưởng

### 8.1 Learning Path / Flexible Program Duration

- Lộ trình học linh hoạt theo lựa chọn của user: 30, 45, 60, 90 ngày hoặc dài hơn.
- Chia theo tuần/chủ đề.
- Daily lesson/task.
- Weekly review.
- Mock interview cuối tuần.
- Cá nhân hóa theo ngành/nghề.
- User nên được chỉnh độ khó lesson.
- Level ban đầu lấy từ onboarding, nhưng trong từng lesson có thể có tùy chọn easier/normal/harder.
- AI sẽ điều chỉnh vocab, sentence length, grammar complexity, speaking speed, câu hỏi follow-up và mức feedback theo độ khó.
- App có thể tự gợi ý tăng/giảm độ khó dựa trên practice score, completion và user feedback.
- Sau mỗi lesson nên có lightweight lesson feedback.
- User có thể đánh giá nhanh: Too easy / Good / Too hard, Useful / Not useful.
- Feedback này dùng để cải thiện AI generation, điều chỉnh độ khó, chọn lesson type và cá nhân hóa lộ trình.
- Không nên bắt user điền form dài sau mỗi bài.

- Cá nhân hóa theo thời lượng học mỗi ngày.
- Chế độ học 15 phút/ngày, 30 phút/ngày, 60 phút/ngày.
- Điều chỉnh lộ trình nếu bỏ lỡ ngày học.
- Checklist hằng ngày.
- Dashboard tiến độ.

### 8.2 Onboarding

- Chọn mục tiêu: phỏng vấn, công việc, giao tiếp, phát âm, nghe, từ vựng.
- Chọn persona/track: Software Engineer, Purchasing/Business, General Professional.
- Chọn level hiện tại.
- Chọn ngày phỏng vấn dự kiến.
- Chọn thời lượng học mỗi ngày.
- Bài test đầu vào nhẹ.
- Ghi âm self-introduction ban đầu.
- Đánh giá confidence ban đầu.
- Hướng dẫn chức năng sau onboarding.
- User nên được giới thiệu các chức năng chính để dễ làm chủ app: daily lesson, shadowing, recording, AI feedback, chatbox trong lesson, sticky paper, vocabulary cards, review queue, progress, YouTube shadowing nếu có.
- Feature guide nên xuất hiện sau onboarding và sau khi tạo plan đầu tiên.
- Nên hiển thị walkthrough ngắn 3–5 bước để user hiểu app vận hành thế nào.
- App nên cho user chọn coach tone, ví dụ: gentle, direct, strict, funny, professional.
- Mặc định nên là gentle + professional để phù hợp mục tiêu phỏng vấn/giao tiếp và giảm áp lực cho người học.
- Feedback nên mặc định là song ngữ.
- Giải thích chính bằng tiếng Việt để user hiểu nhanh lỗi và cách sửa.
- English correction/sample answer/phrases nên hiển thị bằng tiếng Anh để user học cách diễn đạt tự nhiên.
- User có thể cung cấp CV/resume hoặc mô tả kinh nghiệm để AI tạo câu hỏi phỏng vấn cá nhân hóa.
- Không bắt buộc ở phase đầu.
- Ban đầu nên cho user nhập mô tả text thủ công về kinh nghiệm, dự án, công việc, kỹ năng, mục tiêu phỏng vấn.
- Upload CV/resume nên để feature sau vì liên quan privacy, parsing, lưu trữ dữ liệu nhạy cảm và kiểm soát thông tin cá nhân.
- App nên có project/story bank cho interview prep.
- User có thể lưu các câu chuyện cá nhân như: project khó, bug khó, conflict, achievement, failure, teamwork, leadership, negotiation, supplier issue, deadline pressure.
- AI giúp biến story bank thành câu trả lời theo STAR/PREP/CAR bằng tiếng Anh.
- Story bank có thể liên kết với lesson, mock interview, sticky notes, vocabulary cards và sample answers.
- Story bank nên được xây dựng dần trong quá trình học.
- Onboarding chỉ hỏi 1–2 story quan trọng nếu cần, tránh làm user mệt ngay từ đầu.
- Trong lesson/interview practice, AI có thể phát hiện câu trả lời, kinh nghiệm hoặc ví dụ cá nhân hay và gợi ý lưu vào story bank.
- Mock interview mode để phase sau, chưa ưu tiên ở giai đoạn đầu.
- Giai đoạn đầu tập trung generate các câu hỏi, tình huống hoặc đoạn văn cơ bản trước.
- Lesson đầu tiên không nhất thiết phải cố định một format đặc biệt; vẫn đi theo các chức năng ban đầu của hệ thống: AI-generated lesson, context/question/passage, vocab, TTS/audio, shadowing, recording, feedback, sticky/vocab card nếu cần.
- Trong onboarding, app nên hỏi user có cần hệ thống hỗ trợ tạo các lesson cơ bản ban đầu không.
- Nếu user cần, app generate các lesson cơ bản hợp lý như self-introduction, experience, mục tiêu học, công việc/ngành nghề.
- Khi user tự tạo lesson, có thể cho chọn lesson type đơn giản trước khi generate.
- Tab `Lessons` nên kết hợp thư viện bài học và lịch/lộ trình học.
- Nội dung gồm: current plan/calendar theo lộ trình, recent lessons, saved/generated lessons, lesson history, và nút tạo lesson mới.
- User có thể xem lại lesson cũ, tiếp tục lesson dở, hoặc tạo lesson mới theo topic/lesson type.
- Lessons nên hỗ trợ filter theo profile, lesson type, skill focus, ngày học, trạng thái hoàn thành.
- Mặc định nên có option `AI choose for me` để giảm decision fatigue.
- Nếu user chọn `AI choose for me`, AI nên chọn lesson type/chủ đề dựa trên goal chính, active profile, level, recent history, weak skills, note/vocab chưa ôn và nội dung đã học gần đây để tránh duplicate.
- Với Software Engineer: giới thiệu bản thân, tech stack, kinh nghiệm dự án, vai trò trong team, project nổi bật.
- Với Purchasing/Business: giới thiệu bản thân, kinh nghiệm purchasing/procurement, ngành garment/textile, supplier/vendor experience, achievement hoặc responsibility chính.
- Sau khi user quen với self-intro/experience, mới mở rộng sang behavioral questions, conflict, strengths/weaknesses, negotiation, mock interview.
- Có thể có mục “How this app helps you improve” giải thích core loop: luyện nói/shadowing mỗi ngày → nhận feedback → lưu note/từ → review → thấy tiến bộ.

### 8.3 Interview Practice

- Bộ câu hỏi phỏng vấn phổ biến.
- Câu hỏi theo ngành.
- Câu hỏi technical cho Software Engineer.
- Câu hỏi behavioral.
- Câu hỏi về project experience.
- Câu hỏi về teamwork/conflict.
- Câu hỏi về strengths/weaknesses.
- Câu hỏi về career goals.
- Câu hỏi cho Purchasing/Procurement.
- Câu hỏi về supplier/vendor management.
- Câu hỏi về negotiation/cost/quality/deadline.
- Câu trả lời mẫu.
- Framework trả lời: STAR, CAR, PREP.
- Follow-up questions.
- Mock interview mode.
- Random question mode.
- Timed answer mode.

### 8.4 Speaking / Shadowing

- Nghe câu hỏi/câu trả lời mẫu.
- Transcript.
- Shadow từng câu/từng cụm.
- Ghi âm câu trả lời.
- Replay bản ghi.
- So sánh với câu mẫu.
- Chế độ slow/normal/interview speed.
- Lưu đoạn khó để luyện lại.
- Lặp lại đến khi tốt hơn.
- Đếm số lần luyện.
- Lưu lịch sử recording.
- AI feedback sau speaking/shadowing nên ngắn gọn, tích cực trước, chỉ sửa 1–3 lỗi quan trọng nhất để user không bị nản.
- Score phần trăm nên được định nghĩa là practice score, không phải điểm tuyệt đối về năng lực tiếng Anh.
- Practice score là điểm tổng hợp để user theo dõi tiến bộ qua từng lần luyện, gồm pronunciation, fluency, clarity và completeness so với target/sample answer.
- Cần truyền đạt rõ trong UI rằng score dùng để luyện tập và cải thiện, không phải đánh giá cố định hay phán xét năng lực của user.
- Có thể hiển thị score tổng và/hoặc score thành phần: pronunciation, fluency, clarity, rhythm, grammar, vocabulary, structure, confidence.
- UI feedback nên highlight trực tiếp các từ, âm, ký tự, phrase hoặc đoạn phát âm/chưa nói tốt để user nhìn vào hiểu ngay cần sửa gì.
- Highlight có thể dùng màu hoặc underline theo mức độ: tốt, cần chú ý, lỗi nghiêm trọng.
- Nếu có transcript từ speech-to-text, app có thể so sánh câu user nói với target/sample answer để chỉ ra từ bị thiếu, nói sai, phát âm chưa rõ hoặc ngắt nhịp chưa tự nhiên.
- Mỗi feedback nên có next action rõ ràng: luyện lại từ này, đọc lại chunk này, thử câu trả lời ngắn hơn, dùng phrase tự nhiên hơn.

### 8.5 Listening

- Bài nghe câu hỏi phỏng vấn.
- Bài nghe workplace conversation.
- Bài nghe theo tốc độ chậm/vừa/thật.
- Transcript bật/tắt.
- Dictation.
- Listening comprehension questions.
- App nên hỗ trợ nhiều accent, nhưng phase đầu chỉ cần 1–2 accent chính.
- Ưu tiên ban đầu: clear international English hoặc US English để dễ nghe, dễ shadowing và phù hợp phỏng vấn.
- Sau này có thể thêm UK, Australian, Singapore/Malaysia, Indian để luyện nghe phỏng vấn/giao tiếp thực tế với nhiều accent khác nhau.
- Accent có thể là setting trong profile hoặc lesson/audio generation.

- Nghe câu hỏi rồi trả lời ngay.
- Lưu câu nghe khó.

### 8.6 Vocabulary

- Từ vựng theo chủ đề phỏng vấn.
- Từ vựng Software Engineer.
- Từ vựng Purchasing/Procurement/Garment industry.
- Collocations.
- Useful phrases.
- Sentence patterns.
- Flashcards.
- Spaced repetition.
- Lưu từ/cụm từ từ bài học.
- Ví dụ dùng trong câu trả lời phỏng vấn.
- Quiz nhanh.
- Review từ vựng hằng ngày.

### 8.7 Grammar

- Ban đầu không nên làm grammar module riêng nặng lý thuyết.
- Grammar nên xuất hiện trong AI feedback, rewrite suggestions, mini-drills và giải thích từ lỗi thật của user.
- Grammar cần gắn với context phỏng vấn/giao tiếp, giúp user nói đúng và tự nhiên hơn thay vì học lý thuyết rời rạc.

- Sửa lỗi grammar trong câu trả lời.
- Lỗi phổ biến của người Việt.
- Tense khi nói về kinh nghiệm.
- Conditionals cho hypothetical questions.
- Modals trong workplace communication.
- Sentence rewriting.
- Grammar mini-drills.
- Không ưu tiên lý thuyết dài.

### 8.8 AI Feedback

- Chấm câu trả lời theo rubric.
- Feedback grammar.
- Feedback vocabulary.
- Feedback structure.
- Feedback clarity.
- Feedback confidence.
- Gợi ý câu trả lời tốt hơn.
- Dịch/giải thích feedback bằng tiếng Việt.
- Đề xuất bài luyện tiếp theo.
- Nhận diện lỗi lặp lại.
- Theo dõi tiến bộ qua thời gian.
- AI feedback sau recording nên dùng speech-to-text ngay phase đầu nếu MiniMax hoặc provider hỗ trợ tốt.
- Transcript giúp chấm completeness, grammar, vocabulary, structure và so sánh với target/sample answer.
- Nếu pronunciation scoring chưa đủ mạnh, phase đầu feedback có thể ở mức transcript + fluency/basic pronunciation.
- Nếu speech-to-text nhận sai do user phát âm chưa rõ, app nên hiển thị transcript để user có thể kiểm tra/sửa lại nếu cần.
- Feedback cần ghi rõ rằng kết quả có thể bị ảnh hưởng bởi transcript/STT quality.
- App nên lưu transcript user nói cùng recording/attempt.
- Transcript phục vụ feedback, search, progress tracking, weekly insight, review queue và so sánh với target/sample answer.
- Transcript cần gắn với lesson, exercise, attempt, score, feedback và audio recording nếu có.
- User nên có thể xoá transcript theo attempt hoặc xoá cùng recording nếu muốn.
- Việc chọn công cụ chấm điểm bài nói/speech scoring cần được nghiên cứu kỹ ở bước planning, không chốt sâu trong idea phase.
- Planning phase nên so sánh MiniMax, Web Speech API, Whisper, Google/Azure Speech, hoặc các provider pronunciation assessment chuyên dụng.

- Pronunciation feedback sau này.

### 8.9 Gamification / Motivation

- App nên có streak nhưng là streak mềm.
- Streak dùng để khuyến khích luyện nói/shadowing đều đặn, không tạo cảm giác bị phạt nặng khi mất ngày.
- Nếu user làm bài quá tệ, score thấp hoặc bỏ giữa chừng, app không nên phạt hoặc làm user thấy thất bại.
- App nên gợi ý bài dễ hơn, chia nhỏ lesson thành chunk, hoặc chuyển sang quick recovery lesson 3–5 phút.
- Recovery UX nên dùng tone khích lệ: `Mình luyện lại từng bước nhỏ nhé` thay vì `Bạn làm sai`.
- App có thể tự động giảm độ khó tạm thời hoặc gợi ý shadowing theo phrase/chunk ngắn hơn.
- Streak nên gắn với core habit speaking/shadowing hơn là chỉ mở app.
- Daily win.
- Badge đơn giản.
- Điểm hoàn thành.
- Weekly progress summary.
- Milestones: 7 ngày, 14 ngày, 30 ngày, 60 ngày.
- Confidence score trước/sau.
- Số câu đã luyện.
- Số phút speaking.
- App nên có reminder/notification nhưng phải opt-in.
- Giai đoạn đầu có thể dùng browser/PWA notification hoặc email.
- Nội dung reminder nên gợi ý mission cụ thể, ví dụ: `Hôm nay luyện 7 phút câu Tell me about yourself`, không chỉ nhắc chung chung `hãy học bài`.
- Reminder nên ưu tiên giúp user quay lại core habit speaking/shadowing.
- Recovery mode khi bỏ lỡ vài ngày.

### 8.10 Content Management

- Admin/content dashboard là feature hay và nên có ở phase sau nếu app có nhiều user.
- Dashboard có thể dùng để xem generated lessons, prompt templates, regenerate content, mark quality, quản lý tags/lesson types và theo dõi chất lượng AI output.
- Phase đầu user chưa cần tự custom AI coach/prompt sâu.
- Dev sẽ tự cấu hình prompt/settings trong hệ thống để đảm bảo chất lượng và giảm complexity.
- Sau này khi có Admin/content dashboard, có thể setup manual prompt templates, coach styles, lesson templates và content constraints.
- User-facing customization ban đầu chỉ nên ở mức đơn giản: goal, difficulty, accent/voice, lesson type, coach tone nếu cần.
- Phase đầu chưa cần dashboard phức tạp; có thể bắt đầu bằng cấu hình/prompt templates đơn giản trong code hoặc internal tool.

- Admin thêm/sửa câu hỏi.
- Admin thêm/sửa vocabulary.
- Admin thêm/sửa transcript/audio.
- Import/export content.
- Gắn content với persona/track/level/day.
- User nên có thể regenerate lesson nếu AI tạo bài không đúng ý.
- Có thể regenerate toàn bài hoặc từng phần: passage/question, vocabulary, sample answer, TTS/audio, tips, exercise.
- Hệ thống cần lưu version lesson/audio để tránh mất dữ liệu đã học và tránh nhầm cache TTS.
- Nếu user đã học/ghi note/recording trên version cũ, cần giữ liên kết với version đó.

- AI-generated content cần có content safety/quality check trước khi hiển thị.
- Kiểm tra gồm: schema validation, đúng level, không quá dài, không duplicate, đúng ngữ cảnh/profile, không nội dung nhạy cảm/không phù hợp.
- Với nội dung technical/business, cần hạn chế hallucination và ưu tiên câu hỏi/tình huống thực tế.
- Nếu output không đạt, hệ thống nên retry/regenerate hoặc fallback về template an toàn.


### 8.11 PWA / Technical Features

- Tối ưu mobile-first là yêu cầu quan trọng vì nhu cầu dùng mobile của user khá lớn.
- UI/UX cần ưu tiên thao tác nhanh trên điện thoại: mở bài, nghe audio, shadowing, record, xem feedback, lưu note/vocab card.
- Các component như recorder, audio player, transcript, chatbox, sticky note và vocabulary card phải dùng tốt trên màn hình nhỏ.
- Cần đặc biệt test trên iPhone Safari/PWA và Android Chrome vì audio recording/playback/cache có thể khác nhau.
- Desktop vẫn cần hỗ trợ tốt, nhưng mobile là trải nghiệm chính.
- Installable PWA.
- Offline mode sau này.
- Push notification sau này.
- Auth multi-user.
- User progress riêng biệt.
- Audio recording.
- Audio storage.
- Data backup/export.
- Role admin/user.
- Analytics học tập.

### 8.13 AI Multimedia / MiniMax Features

- Generate text bài học bằng MiniMax 2.7 theo profile, nhu cầu, level, ngành nghề và lịch sử học của user.
- Generate text-to-speech cho câu hỏi, đoạn văn, câu trả lời mẫu, vocabulary, phrase và script shadowing.
- Text-to-video của MiniMax nên để future/experimental, chưa ưu tiên trong core phase đầu.
- Ưu tiên TTS/audio trước vì mục tiêu chính là shadowing, nghe-nói và luyện phỏng vấn.
- Video generation có thể dùng sau cho roleplay, tình huống hội thoại hoặc lesson sinh động khi core flow đã ổn định.
- Generate script nói cho từng bài học để user có thể nghe, shadowing và luyện nói theo.
- App nên cho user chọn một số tùy chọn TTS/audio cơ bản.
- Phase đầu: hỗ trợ tốc độ slow/normal và 1–2 voice mặc định.
- Sau này có thể mở rộng voice lab: nam/nữ, accent, emotion, interview voice, coach voice, native-like voice.
- TTS config cần được đưa vào audio hash/version để cache đúng và tránh generate trùng.

- Generate interviewer voice cho câu hỏi phỏng vấn.
- Generate coach voice cho feedback hoặc tips.
- Generate roleplay script: interviewer ↔ candidate, supplier ↔ purchaser, engineer ↔ hiring manager.
- Cache nội dung/audio/video đã generate để tiết kiệm chi phí.
- Kiểm tra history của user để tránh generate duplicate câu hỏi, tình huống hoặc nội dung đã học.

### 8.14 Vocabulary Notes / Word Intelligence

- User có thể note từ/cụm từ quan trọng trong bài học.
- Mỗi note có thể lưu: word/phrase, nghĩa tiếng Việt, IPA, pronunciation audio, ví dụ, ngữ cảnh xuất hiện, ngành nghề liên quan.
- Hỗ trợ phát âm từng từ hoặc từng cụm từ.
- Hiển thị IPA cho từ/cụm từ.
- Giải thích tiếng Việt dễ hiểu để user không cần dùng Google Translate.
- AI tạo ví dụ mới theo công việc/context của user.
- Lưu lịch sử từ vựng đã note.
- Tạo word family: noun, verb, adjective, adverb nếu có.
- Gợi ý tiền tố/hậu tố/root liên quan.
- Gợi ý các từ có cùng prefix/suffix/root.
- Gợi ý collocations và phrases thường dùng.
- Gợi ý từ đồng nghĩa/trái nghĩa theo context.
- Phân biệt nghĩa theo ngữ cảnh thay vì dịch máy từng từ.
- Theo dõi từ nào user đã học, đã ôn, đã dùng trong speaking/writing.
- Có thể tạo bài ôn tập tự động từ các note đã lưu.
- Hỗ trợ tạo vocabulary cards/flashcards cho từ vựng mới.
- Vocabulary card có thể gồm: từ/cụm từ, nghĩa tiếng Việt, IPA, audio phát âm, ví dụ theo context, collocations, word family, prefix/suffix/root nếu có.
- Phase đầu, vocabulary cards nên dùng visual cue/icon/placeholder hoặc ảnh gợi ý đơn giản để hỗ trợ liên tưởng.
- AI image generation cho vocabulary cards để phase sau vì có thể tốn chi phí và không phải core của app.
- Quan trọng hơn hình ảnh là context, ví dụ cá nhân hóa, audio phát âm, IPA, collocation và mnemonic dễ nhớ.
- Có thể có mnemonic/hình ảnh/câu chuyện ngắn giúp user nhớ từ lâu hơn.
- Vocab cards phase đầu nên hỗ trợ flashcard cơ bản và spaced repetition đơn giản.
- Các kiểu học ban đầu: nhìn English đoán Vietnamese/context, nghe audio chọn từ, điền từ/cụm từ vào câu.
- Game nâng cao hoặc visual-heavy vocabulary games để phase sau.
- Card nên gắn với lesson gốc để user biết từ này xuất hiện trong tình huống nào.
- Review queue nên ưu tiên: lỗi speaking lặp lại, vocabulary cards chưa nhớ, sticky notes quan trọng, và các câu/phrases user đã lưu từ lesson gần đây.
- Tab `Review` nên là nơi ôn theo queue thông minh.
- Nội dung review gồm: vocabulary cards, weak phrases, speaking mistakes, sticky notes quan trọng, story bank cần luyện lại, lesson insights cần nhớ.
- Review nên ưu tiên bài ôn ngắn 3–7 phút để phù hợp mobile và giảm ma sát.
- Review queue cần được cá nhân hóa theo lỗi lặp lại, lịch sử học, mức độ quên, profile hiện tại và mục tiêu speaking/interview.
- Trong mỗi lesson, nếu có nội dung liên quan từ bài cũ, nên có phần `Review from previous lessons` để nhắc lại lỗi/từ/câu/sticky có liên quan.
- Review cần hỗ trợ core habit speaking/shadowing, không nên biến thành một module học rời rạc quá nặng.

### 8.15 Tips & Tricks / Memory Aids

- Cung cấp tips/tricks giúp học từ vựng dễ nhớ hơn.
- Giải thích prefix/suffix/root như một cách ghi nhớ từ.
- Ví dụ: `ex-` với nghĩa cũ/cựu khi có gạch nối như ex-lover, ex-wife, ex-teacher.
- Phân biệt `ex-` và `ex` trong các từ như explain, exit, export.
- Giải thích các prefix/root như tele, trans, de, inter, post, pre.
- Có thể tạo các bài mini lesson dạng “word story” để giúp nhớ từ lâu hơn.
- Có thể lưu tip vào vocabulary note.
- Có thể liên kết tip với nhiều từ liên quan.
- Có thể tạo quiz từ một tip.
- Cần kiểm tra tính đúng/sai của etymology/tip vì một số mẹo ghi nhớ có thể không chính xác về mặt học thuật nhưng vẫn hữu ích về mặt mnemonic.
- App nên phân biệt rõ: “mẹo ghi nhớ” khác với “nguồn gốc từ chính xác”.

### 8.16 External Content / YouTube Shadowing

- User có thể dùng nguồn ngoài như YouTube để luyện shadowing.
- YouTube shadowing nên hỗ trợ cả hai hướng: user nhập link video bất kỳ và app gợi ý video/segment phù hợp.
- User nhập link giúp linh hoạt, không bị bó buộc vào nội dung của app.
- Curated/gợi ý video giúp người học không chọn nội dung quá khó, quá dài hoặc không phù hợp level/topic.
- Video YouTube có thể dài tùy ý, nhưng app không nên bắt user shadowing toàn bộ video.
- App nên cắt video/transcript thành các segment ngắn để luyện shadowing.
- Segment mặc định nên khoảng 15–60 giây.
- Người mới có thể luyện segment 10–20 giây; người khá hơn có thể luyện 30–60 giây.
- Với video dài, app có thể tự gợi ý một số đoạn đáng luyện nhất, ví dụ video 10 phút → chọn 5 đoạn, mỗi đoạn 30 giây.
- Với YouTube, app nên ưu tiên lưu segment user học và metadata video thay vì lưu toàn bộ transcript.
- Metadata có thể gồm video URL/id, title, channel, selected segment start/end, transcript đoạn đã học, vocab/note/feedback phát sinh từ đoạn đó.
- Cách này giúp giảm storage, giảm rủi ro copyright và tránh lưu quá nhiều dữ liệu không cần thiết.
- Trích xuất hoặc nhập transcript nếu có.
- Tạo shadowing segments từ transcript.
- Cho phép user chọn đoạn muốn luyện.
- AI rút từ vựng/cụm từ quan trọng từ đoạn video.
- AI tạo câu hỏi comprehension từ video.
- AI tạo bài tập shadowing theo đoạn.
- AI tạo summary song ngữ.
- YouTube shadowing không phải core đầu tiên, nhưng nên thêm ngay sau khi các main functions đã hoàn thành.
- Lý do: nhiều người thích shadowing video trên YouTube, và đây là nguồn nội dung thực tế/phong phú.
- Có thể dùng transcript text của video qua công cụ/API phù hợp như youtube-dl/yt-dlp hoặc transcript extraction để kết hợp với các function hiện có.
- Sau khi có transcript, app có thể tạo shadowing segments, vocab cards, sticky notes, comprehension questions, summary và AI chat context.
- Cần cân nhắc kỹ vấn đề bản quyền, transcript availability, chất lượng auto-caption, và giới hạn kỹ thuật khi tích hợp YouTube.
- Tránh làm user cảm thấy bị bó buộc trong nội dung app; app nên hỗ trợ cả nội dung do AI tạo và nội dung user tự mang vào.

### 8.17 Flexible Lesson Types

- Bài học dạng interview question.
- Bài học dạng workplace situation.
- Bài học dạng short AI-generated passage.
- Bài học dạng roleplay dialogue.
- Bài học dạng vocabulary story.
- Bài học dạng grammar-in-context.
- Bài học dạng YouTube/video shadowing.
- Bài học dạng mock interview.
- Bài học dạng review lỗi cũ.
- Bài học dạng note review từ vựng.
- Bài học dạng tips/tricks mini lesson.

### 8.18 AI Chatbox / Learning Assistant

- Có một cửa sổ chatbox trong app để user hỏi thêm khi đang học.
- Chatbox gọi MiniMax API để giải thích thêm nội dung bài học, từ vựng, grammar, câu mẫu, tình huống, hoặc bất cứ thông tin liên quan nào user muốn tìm hiểu.
- Chatbox không phải chat tự do toàn app ở phase đầu; chỉ xuất hiện trong logic của từng bài học.
- Chatbox ưu tiên hiểu context lesson hiện tại trước: bài học nào, đoạn nào, từ nào, câu hỏi nào, persona nào, level nào.
- Các page khác tạm thời không có chatbox để tránh loãng UX và giảm scope.
- User có thể hỏi bằng tiếng Việt hoặc tiếng Anh.
- Chatbox có thể giải thích lại theo nhiều mức: đơn giản, chi tiết, ví dụ thực tế, ví dụ theo ngành nghề.
- Chatbox có thể tạo thêm ví dụ, câu thay thế, câu trả lời mẫu, roleplay mini, hoặc bài tập nhỏ.
- Chatbox có thể giúp user hiểu sâu hơn mà không phải rời app sang Google/ChatGPT/Google Translate.
- Chatbox trong lesson chủ yếu là quick search/quick ask cho user.
- User thích hỏi gì thì hỏi, miễn là đang trong context bài học.
- Chatbox không cần bị bó quá cứng theo quick prompts ở phase đầu.
- Khi lưu thông tin từ chatbox, user có thể chọn lưu thành: Sticky note, Vocabulary card, Saved phrase, Grammar note, hoặc General note.
- Mặc định AI có thể gợi ý loại note phù hợp dựa trên nội dung chat.
- Quick prompts có thể là enhancement sau để hỗ trợ mobile UX, nhưng bản chất chatbox vẫn là nơi user hỏi tự do khi muốn tìm hiểu thêm.

### 8.19 Sticky Papers / Lesson Memory Notes

- User có thể lưu các ghi chú nhỏ dạng sticky paper trong từng lesson.
- Tab `Notes` nên là nơi tập trung các ghi chú học tập cá nhân.
- Nội dung gồm: Sticky Papers, Vocabulary Cards, saved phrases, story bank, grammar/mistake notes, AI chat insights.
- Notes nên có global search.
- Search theo từ khóa, tag, lesson, active profile, note type, skill focus và ngày học.
- Sau này có thể thêm semantic search bằng AI để tìm theo ý nghĩa, ví dụ user hỏi “những lỗi phát âm tôi hay mắc khi giới thiệu bản thân”.
- Notes cũng là nền tảng để sau này export/sync sang Obsidian.
- Sticky note có thể do user tự viết hoặc do AI đề xuất.
- Sau mỗi lesson, AI có thể gợi ý 1–3 sticky đáng lưu, ví dụ: lỗi cần nhớ, phrase hay, tip quan trọng, pronunciation focus, hoặc insight từ chatbox.
- User có quyền chọn lưu, chỉnh sửa hoặc bỏ qua sticky AI đề xuất.
- Sticky có thể lưu: insight, lỗi cần nhớ, câu hay, mẹo học, từ/cụm từ quan trọng, reminder cá nhân.
- Sticky gắn với lesson, lesson block, từ vựng, đoạn transcript hoặc câu trả lời của user.
- Sticky có thể có màu/label: grammar, vocab, pronunciation, idea, mistake, personal note.
- Progress nên ưu tiên đo speaking/shadowing vì đây là core habit.
- Chỉ số quan trọng: số ngày luyện nói, số phút nói, practice score trend, lỗi phát âm/fluency giảm, số phrases đã dùng lại được.
- Progress phụ: lesson completed, vocab cards reviewed/mastered, sticky notes reviewed, streak, review queue completion.
- Không nên biến progress thành quá nhiều dashboard phức tạp; Home chỉ hiển thị snapshot ngắn, chi tiết để trong Progress/Lessons/Review.
- Có thể đưa sticky vào review queue để nhắc lại sau.
- Sticky giúp biến mỗi lesson thành một trang học có ký ức cá nhân, không chỉ là nội dung AI generate dùng một lần.

### 8.20 Obsidian / Personal Knowledge Management

- Obsidian là một hướng tích hợp rất phù hợp cho phần ghi chú và quản lý kiến thức cá nhân.
- Obsidian export không phải MVP core.
- Tuy nhiên data/note format nên được thiết kế theo Markdown-friendly ngay từ đầu.
- Export zip/vault, sync một chiều hoặc import ngược lại để phase sau.
- App có thể lưu sticky paper, vocabulary note, grammar note, AI chat insight, lesson summary và personal reflection theo cấu trúc Markdown.
- Mỗi lesson có thể export thành một file `.md` riêng.
- Mỗi từ/cụm từ quan trọng có thể export thành note riêng hoặc section trong lesson note.
- Sticky papers có thể được export thành callout/blockquote/task trong Markdown.
- Nên hỗ trợ tags như `#lesson`, `#vocab`, `#grammar`, `#pronunciation`, `#interview`, `#software-engineer`, `#purchasing`, `#mistake`, `#review`.
- Nên hỗ trợ backlinks giữa:
  - lesson ↔ vocabulary note
  - lesson ↔ sticky paper
  - vocabulary ↔ related prefix/suffix/root
  - mistake ↔ review lesson
  - chat insight ↔ source lesson
- Có thể tạo folder structure tương thích Obsidian:
  - `Lessons/`
  - `Vocabulary/`
  - `Sticky Notes/`
  - `Mistakes/`
  - `Reviews/`
  - `Prompts/`
  - `Progress/`
- Future feature: export toàn bộ learning vault thành zip để mở trong Obsidian.
- Future feature: sync một chiều từ app sang Obsidian vault.
- Future feature: import note từ Obsidian ngược lại vào app.
- Future feature: dùng Obsidian như personal English knowledge base, nơi user lưu lại toàn bộ hành trình học, lỗi sai, từ vựng, câu mẫu, lesson insight và tiến bộ.
- Design principle: ngay cả khi chưa tích hợp Obsidian, mọi note nên có cấu trúc rõ ràng, portable, exportable và không bị khóa trong app.



Những thứ có khả năng thuộc MVP, nhưng sẽ chốt sau idea phase:

- Onboarding cơ bản.
- 2 track ban đầu: Software Engineer và Purchasing/Business.
- Lộ trình 60 ngày dạng đơn giản.
- Daily lesson/task.
- Interview question practice.
- Câu trả lời mẫu.
- Shadowing + ghi âm + replay.
- Vocabulary theo bài.
- Progress/streak cơ bản.
- Feedback cơ bản, có thể manual/AI-lite.
- Admin/content seed đơn giản.
