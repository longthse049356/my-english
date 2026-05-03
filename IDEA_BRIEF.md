# Idea Brief — Personalized English Coach PWA

## 1. Bối cảnh

Dự án là một trang web/PWA do người dùng tự xây dựng để hỗ trợ bản thân, vợ, và sau này có thể mở rộng cho một vài người bạn cùng cải thiện tiếng Anh.

Mục tiêu ban đầu không phải tạo một app học tiếng Anh đại trà, mà là một công cụ thực dụng giúp người học có vốn tiếng Anh vừa đủ cải thiện khả năng nghe, nói, shadowing, từ vựng, grammar và phản xạ phỏng vấn bằng tiếng Anh trong khoảng 60 ngày.

Dự án bắt đầu từ nhu cầu cá nhân:

- Người dùng là Software Engineer, cần cải thiện khả năng phỏng vấn bằng tiếng Anh.
- Vợ người dùng làm Purchase trong một tập đoàn may mặc lớn của Malaysia, cũng cần cải thiện tiếng Anh cho công việc/phỏng vấn/giao tiếp chuyên nghiệp.
- Sau này có thể mở rộng cho bạn bè có nhu cầu tương tự.

Tinh thần của phase hiện tại là **idea phase**: ghi nhận càng đầy đủ càng tốt tất cả ý tưởng, feature, hướng phát triển, insight và giả định. Sau khi idea phase đủ rõ, mới chuyển sang planning/MVP phase để chọn ra phần tối thiểu cần build trước.

## 2. Vision

Xây dựng một PWA giúp người Việt đã có nền tảng tiếng Anh cải thiện khả năng sử dụng tiếng Anh trong bối cảnh phỏng vấn và công việc thực tế thông qua lộ trình cá nhân hóa theo nhu cầu người dùng. Lộ trình không cố định 60 ngày, mà có thể là 30, 45, 60, 90 ngày hoặc dài hơn tùy option user chọn, với luyện nghe, nói, shadowing, từ vựng, grammar thực dụng, feedback, mock interview và các tips/tricks giúp việc học thú vị hơn.

## 3. Định vị sản phẩm ban đầu

Không nên định vị là:

> App học tiếng Anh tổng hợp.

Nên định vị là:

> 60-day English interview coach cho người Việt đã có nền tảng tiếng Anh nhưng thiếu tự tin khi phỏng vấn/giao tiếp công việc.

Hoặc hẹp hơn:

> 60-day English interview fitness program for Vietnamese professionals.

Lợi thế tiềm năng nằm ở:

- Tập trung vào người Việt.
- Tập trung vào phỏng vấn và workplace English.
- Có lộ trình ngắn hạn/trung hạn rõ ràng theo lựa chọn của user: 30, 45, 60, 90 ngày hoặc dài hơn.
- Nội dung thực dụng, theo ngành/nghề.
- Feedback dễ hiểu, có thể bằng tiếng Việt.
- Core loop hằng ngày đủ nhỏ để duy trì thói quen.

## 4. Persona ban đầu

### 4.1 Persona A — Software Engineer

Người dùng đầu tiên là chính người tạo dự án.

Đặc điểm:

- Là Software Engineer.
- Có nền tảng tiếng Anh nhất định.
- Có thể đọc hiểu tài liệu kỹ thuật.
- Muốn cải thiện khả năng phỏng vấn bằng tiếng Anh.
- Cần luyện cách trả lời các câu hỏi technical, behavioral, project experience, system design/basic architecture, teamwork, conflict, career goal.
- Pain point chính là nghe hiểu câu hỏi, phản xạ trả lời, diễn đạt tự nhiên, dùng đúng vocabulary ngành software, và giữ sự tự tin khi phỏng vấn.

Nhu cầu:

- Luyện self-introduction.
- Luyện project explanation.
- Luyện behavioral questions theo STAR.
- Luyện technical discussion bằng tiếng Anh.
- Luyện follow-up questions.
- Luyện shadowing câu trả lời mẫu.
- Nhận feedback về grammar, clarity, structure, vocabulary, confidence.

### 4.2 Persona B — Purchasing / Garment Industry Professional

Người dùng thứ hai là vợ người tạo dự án.

Đặc điểm:

- Làm Purchase trong tập đoàn may mặc lớn của Malaysia.
- Cần tiếng Anh trong môi trường công việc quốc tế.
- Có thể cần tiếng Anh cho phỏng vấn, meeting, supplier communication, negotiation, reporting, email, workplace conversation.
- Pain point có thể khác Software Engineer: nhiều hơn về business communication, purchasing terms, negotiation, vendor/supplier coordination, garment industry vocabulary.

Nhu cầu:

- Luyện workplace English.
- Luyện purchasing/procurement vocabulary.
- Luyện phỏng vấn cho role purchasing/merchandising/supply chain.
- Luyện email và spoken communication.
- Luyện negotiation scenarios.
- Luyện giải thích kinh nghiệm làm việc, quy trình mua hàng, xử lý supplier, deadline, cost, quality issue.

### 4.3 Persona mở rộng sau này

Sau này có thể mở rộng cho:

- Bạn bè chuẩn bị phỏng vấn tiếng Anh.
- Người Việt đi làm muốn chuyển sang công ty quốc tế.
- Software engineers muốn apply remote/global jobs.
- Business/procurement/supply-chain professionals.
- Người có nền tảng A2/B1/B2 nhưng thiếu phản xạ nói.

## 5. Jobs To Be Done

Khi tôi chuẩn bị phỏng vấn bằng tiếng Anh, tôi muốn luyện câu trả lời theo tình huống thực tế để tự tin hơn và không bị đứng hình.

Khi tôi nghe câu hỏi phỏng vấn, tôi muốn hiểu nhanh ý chính và biết cách trả lời có cấu trúc.

Khi tôi trả lời bằng tiếng Anh, tôi muốn biết mình sai ở đâu: grammar, vocabulary, pronunciation, structure, clarity hay confidence.

Khi tôi học mỗi ngày, tôi muốn app nói rõ hôm nay cần làm gì, thay vì phải tự nghĩ nên học gì.

Khi tôi học từ vựng/grammar, tôi muốn chúng gắn với bối cảnh phỏng vấn và công việc thật, không phải học lý thuyết rời rạc.

Khi tôi thiếu động lực, tôi muốn thấy tiến bộ nhỏ mỗi ngày và có cảm giác chương trình 60 ngày đang đưa mình tới mục tiêu.

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

## 7. Nguyên tắc sản phẩm

1. Ghi nhận toàn bộ ý tưởng trong idea phase, không vội cắt.
2. Sau idea phase mới chọn MVP.
3. Mọi feature phải phục vụ mục tiêu cải thiện khả năng phỏng vấn/giao tiếp công việc bằng tiếng Anh.
4. Ưu tiên core loop hằng ngày hơn danh sách feature lớn.
5. Nội dung phải thực dụng, theo ngữ cảnh thật.
6. Người học phải biết hôm nay cần làm gì.
7. Feedback phải giúp người học muốn luyện tiếp, không làm họ sợ nói.
8. Có thể có nhiều track persona khác nhau, nhưng cần bắt đầu bằng 1–2 track thật rõ.

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

## 10. Những thứ chưa nên chốt vội

- Có làm AI feedback ngay MVP không.
- Có cần speech-to-text ngay không.
- Có cần lưu audio lâu dài không.
- Có cần offline mode không.
- Payment/subscription chưa cần ở các phase đầu.
- Phase đầu ưu tiên để user dùng free, đặc biệt khi app còn private/internal hoặc thử nghiệm với nhóm nhỏ.
- Tuy nhiên vì AI/TTS/audio có cost, kiến trúc vẫn nên có khả năng thêm quota, usage tracking và subscription sau này nếu mở rộng public.
- Có cần community không.
- Có cần app public hay chỉ private ban đầu.
- Có cần gamification sâu không.

## 11. Giả định rủi ro

- Người dùng có thể không học đều nếu không có accountability.
- Nếu app quá rộng, sẽ mất focus.
- Nếu không thấy tiến bộ trong 7–14 ngày, người học dễ bỏ.
- Chất lượng content quan trọng hơn số lượng feature.
- Feedback speaking nếu quá kém sẽ làm giảm niềm tin.
- Cạnh tranh với ChatGPT voice rất mạnh.
- Người dùng có thể chỉ cần một workflow tốt với ChatGPT + reminder + tracking, không cần app phức tạp.

## 12. Câu hỏi mở

### 12.1 Quyết định đã chốt tạm thời

- Dự án sẽ không chỉ ưu tiên một track duy nhất.
- Sẽ làm song song nhiều nhóm user/persona ngay từ hướng thiết kế nội dung.
- Lý do: phần lớn nội dung sẽ được generate bằng AI, dự kiến dùng gói MiniMax 2.7, nên hệ thống cần được thiết kế để tạo nội dung theo persona/industry/goal/level thay vì hard-code cho một ngành.
- Idea phase sẽ ghi nhận càng nhiều câu hỏi, feature, learning scenario và content direction càng tốt.
- MVP phase sau này vẫn sẽ lọc lại những gì thật sự cần build trước.
- Sản phẩm ban đầu là private tool cho gia đình/bạn bè, nhưng kiến trúc và content system nên thiết kế đủ tốt để sau này có thể mở public/monetize nếu hiệu quả.
- Trong quá trình grill idea, nếu người dùng trả lời “tiếp tục” thì hiểu là đồng ý với câu trả lời đề xuất gần nhất.
- Mục tiêu theo lộ trình đã chọn: sau 30/45/60/90 ngày hoặc dài hơn, người học có thể tự tin hơn khi tham gia phỏng vấn/giao tiếp công việc bằng tiếng Anh; nghe hiểu câu hỏi phổ biến, trả lời có cấu trúc, dùng được từ vựng theo ngành, và không bị đứng hình.
- App không phục vụ người mất gốc ở giai đoạn đầu. App ưu tiên người đã có nền tảng tối thiểu A2/B1 trở lên, có thể đọc/nghe cơ bản nhưng yếu phản xạ nói, thiếu từ vựng theo ngành và thiếu tự tin khi phỏng vấn/giao tiếp.
- Thời lượng học có thể linh hoạt theo nhu cầu. Thiết kế trung tâm là trung bình 1 bài học/ngày.
- Một bài học có thể là: 1 tình huống thực tế, 1 câu hỏi nhà tuyển dụng có thể hỏi, hoặc 1 đoạn văn ngắn được AI generate theo description/context của user.
- AI có thể tự chọn nội dung random, nhưng phải kiểm tra lịch sử học của user để tránh duplicate câu hỏi/tình huống/nội dung đã học.
- Nội dung bài học sẽ được AI generate theo profile user, mục tiêu, ngành, level và lịch sử học; nhưng vẫn cần template/rubric cố định để bài học luôn có cấu trúc nhất quán.
- Onboarding lần đầu sẽ hỏi user thuộc nhóm nào: nhân viên/người đi làm, học sinh/sinh viên, người làm tự do hoặc nhóm khác.
- Nếu là nhân viên/người đi làm, app sẽ hỏi mô tả công việc, ngành nghề, vai trò hiện tại, nhu cầu tiếng Anh và mục tiêu khi tham gia web học tập.
- Nếu là học sinh/sinh viên, app sẽ hỏi bối cảnh học tập, mục tiêu tiếng Anh, kỳ thi/phỏng vấn/thuyết trình nếu có, và nhu cầu cải thiện kỹ năng.
- Onboarding nên kết hợp form ngắn và AI follow-up.
- Form ngắn dùng để lấy dữ liệu có cấu trúc: loại user, level, mục tiêu, thời lượng/lộ trình mong muốn, ngành nghề, vai trò.
- Sau form, AI hỏi thêm 2–3 câu follow-up để hiểu sâu mục tiêu, ngữ cảnh công việc/học tập và tình huống user muốn luyện.
- Sau onboarding, app nên tạo plan tổng quan cho toàn bộ lộ trình user đã chọn, nhưng chỉ generate chi tiết 3–7 bài đầu.
- Các bài sau nên generate dần dựa trên progress, history, điểm yếu, note/sticky/vocab đã lưu và nội dung đã học để tránh duplicate.
- Core habit quan trọng nhất là luyện nói/shadowing hằng ngày, vì mục tiêu cuối cùng của app là giúp người dùng phỏng vấn/giao tiếp thành công bằng tiếng Anh.
- Một lesson hằng ngày phải phục vụ core habit này: input/context, vocabulary, chatbox, sticky notes và feedback đều nên dẫn về việc user nói tốt hơn, shadowing tốt hơn, hoặc trả lời phỏng vấn/giao tiếp tốt hơn.
- Shadowing nên là phần mặc định của hầu hết lesson, vì core habit là luyện nói/shadowing hằng ngày.
- Shadowing nên hỗ trợ 3 cấp độ: phrase/chunk → sentence → full answer/dialogue.
- Người mới hoặc thiếu tự tin có thể bắt đầu từ chunk ngắn.
- Người khá hơn có thể shadow cả câu, cả đoạn, hoặc roleplay dialogue.
- Đây là điểm rất quan trọng về UI/UX: thiết kế phải làm sao để user dễ dùng, thoải mái, ít áp lực và không sợ nói sai.
- Vì mục tiêu là hỗ trợ học tiếng Anh để đi phỏng vấn/giao tiếp thành công, trải nghiệm luyện nói cần mang cảm giác được hỗ trợ/coached, không bị phán xét.
- UI shadowing nên cho user cảm giác có thể luyện từng bước nhỏ, nghe lại, thử lại, bỏ qua tạm thời, và quay lại sau.

### 12.2 Product Strategy

1. Sản phẩm này trước hết phục vụ cá nhân/gia đình/bạn bè, hay ngay từ đầu đã muốn có khả năng mở rộng thành sản phẩm public?
2. Nếu phải mô tả sản phẩm bằng một câu duy nhất cho người dùng mới, câu đó là gì?
3. Tên tạm thời của sản phẩm là gì?
4. Người dùng nên cảm nhận sản phẩm này giống một app, một coach, một bootcamp, một game học tập, hay một trợ lý cá nhân?
5. Sản phẩm nên nghiêm túc/professional hay vui vẻ/gamified?
6. Lợi thế khác biệt lớn nhất so với ChatGPT voice là gì?
7. Lợi thế khác biệt lớn nhất so với ELSA/Cambly/Duolingo/YouTube là gì?
8. Nếu một người chỉ dùng app trong 7 ngày, điều gì phải xảy ra để họ thấy đáng dùng tiếp?
9. Nếu một người dùng xong 60 ngày, kết quả tối thiểu bạn kỳ vọng là gì?
10. Có muốn sản phẩm tập trung vào “đậu phỏng vấn” hay rộng hơn là “tự tin dùng tiếng Anh trong công việc”?
11. Có muốn sản phẩm có định vị “cho người Việt” thật rõ không?
12. Có muốn sản phẩm hỗ trợ người dùng ngoài Việt Nam sau này không?
13. Có muốn sản phẩm là private tool lâu dài hay eventually monetized?
14. Nếu monetized, bạn muốn bán theo gói 60 ngày, subscription, lifetime, cohort, hay B2B?
15. Có muốn app trở thành nơi lưu lại toàn bộ hành trình học tiếng Anh cá nhân không?

### 12.3 Target Users / Personas

16. Ngoài Software Engineer và Purchasing, những persona nào bạn muốn hỗ trợ ngay trong content system?
17. Có nên có persona “General Professional” cho người đi làm nói chung không?
18. Có nên có persona “Student/Fresher” chuẩn bị phỏng vấn đầu đời không?
19. Có nên có persona “Remote job applicant” không?
20. Có nên có persona “Manager/Team lead” cần tiếng Anh leadership không?
21. Có nên có persona “Sales/Customer support” không?
22. Người dùng đầu vào tối thiểu nên ở level nào: A1, A2, B1, B2?
23. App có phục vụ người mất gốc không?
24. Nếu không phục vụ người mất gốc, app sẽ nói rõ điều đó thế nào?
25. Có cần phân loại user theo ngành nghề ngay onboarding không?
26. Có cần phân loại theo mục tiêu: interview, workplace, presentation, meeting, email không?
27. Có cần phân loại theo deadline: 7 ngày, 14 ngày, 30 ngày, 60 ngày, không deadline không?
28. Người học có thể học một mình hay cần partner/coach?
29. Có nên hỗ trợ nhiều người trong một gia đình dùng chung app không?
30. Có cần profile riêng cho từng người dùng không?

### 12.4 Learning Goals

31. Mục tiêu chính của 60 ngày là gì: nói trôi chảy hơn, nghe tốt hơn, trả lời phỏng vấn tốt hơn, tăng từ vựng, hay tự tin hơn?
32. Có nên cho user chọn một mục tiêu chính và nhiều mục tiêu phụ không?
33. Mục tiêu có nên đo bằng điểm số không?
34. Có nên có pre-test và post-test để so sánh trước/sau không?
35. Sau 60 ngày, user nên trả lời được bao nhiêu câu phỏng vấn?
36. Sau 60 ngày, user nên học được bao nhiêu từ/cụm từ?
37. Sau 60 ngày, user nên có bao nhiêu phút speaking practice?
38. Sau 60 ngày, user nên hoàn thành bao nhiêu mock interviews?
39. Có nên có chứng chỉ/completion report cá nhân không?
40. Có nên tạo “interview readiness score” không?
41. Readiness score nên gồm những thành phần nào: listening, fluency, grammar, vocabulary, structure, pronunciation, confidence?
42. Có nên có mục tiêu theo tuần không?
43. Có nên có mục tiêu theo ngày không?
44. Có nên cho user tự đặt goal cá nhân không?
- Crash course khi user sắp phỏng vấn gấp là future feature, chưa cần vội ở phase đầu.
- Hiện tại app ưu tiên để người học thoải mái lựa chọn thời gian/lộ trình theo nhu cầu.
- Sau này có thể xem xét mode deadline 1/3/7/14 ngày, tập trung self-intro, experience, top questions, shadowing và mock interview.


### 12.5 60-Day Curriculum

46. 60 ngày nên chia thành mấy phase?
47. Có nên chia thành 8 tuần không?
48. Nếu chia 8 tuần, chủ đề từng tuần nên là gì?
49. Week 1 nên tập trung vào self-introduction hay assessment/foundation?
50. Khi nào nên bắt đầu mock interview?
51. Có nên có review day mỗi tuần không?
52. Có nên có rest day không?
53. Có nên có ngày catch-up khi user bỏ lỡ bài không?
54. Mỗi ngày nên học bao lâu là lý tưởng: 15, 20, 30, 45, 60 phút?
55. Mỗi daily lesson nên gồm những phần nào?
56. Daily lesson có nên luôn có speaking không?
57. Daily lesson có nên luôn có listening không?
58. Daily lesson có nên luôn có vocabulary không?
59. Daily lesson có nên có grammar không, hay grammar chỉ xuất hiện khi cần?
60. Có nên có “main mission” và “optional bonus” mỗi ngày không?
61. Có nên có lộ trình riêng cho từng persona không?
62. Có nên có lộ trình riêng theo level không?
63. Có nên có lộ trình riêng theo deadline không?
64. Có nên cho AI generate lộ trình động thay vì dùng lộ trình cố định không?
65. Nếu AI generate lộ trình, có cần lưu version của lộ trình không?

### 12.6 Daily Core Loop

66. Core loop chính xác của một buổi học nên là gì?
67. User mở app lên thì màn hình đầu tiên nên hiển thị gì?
68. Có nên luôn bắt đầu bằng “Today’s mission” không?
69. Một lesson nên bắt đầu bằng câu hỏi phỏng vấn, đoạn nghe, từ vựng, hay mục tiêu ngày?
70. User nên trả lời bằng voice trước khi xem câu mẫu hay xem mẫu trước rồi shadow?
71. Có nên ép user thử trả lời trước để đo khả năng thật không?
72. Có nên cho user skip phần voice nếu đang ở nơi không tiện nói không?
73. Nếu user không tiện nói, có chế độ text practice không?
74. Có nên có quick mode 5 phút không?
75. Có nên có deep mode 30–60 phút không?
76. Có nên có review mode chỉ để ôn lại lỗi cũ không?
77. Có nên có random challenge mỗi ngày không?
78. Có nên có “practice again” cho câu trả lời chưa tốt không?
79. Khi nào một daily lesson được tính là hoàn thành?
80. Có nên cho user tự đánh giá sau mỗi bài không?

### 12.7 Speaking / Shadowing

81. Shadowing là feature trung tâm hay chỉ là một phần phụ?
82. Shadowing nên theo câu, theo cụm, hay theo đoạn?
83. Có cần audio mẫu bằng nhiều giọng không?
84. Audio mẫu nên là native-like, clear international English, hay giọng phù hợp người Việt?
85. Có nên có tốc độ slow/normal/fast không?
86. Có nên highlight transcript theo audio không?
87. Có nên có repeat loop cho từng câu không?
88. Có nên có recording cho từng câu shadowing không?
89. Có nên so sánh waveform/audio không, hay chỉ feedback text?
90. Có nên lưu tất cả recording không?
91. Nếu lưu recording, lưu bao lâu?
92. Có cần user xoá recording không?
93. Có cần privacy warning cho audio không?
94. Có nên cho user nghe lại recording cũ để thấy tiến bộ không?
95. Có nên có speaking streak riêng không?

### 12.8 Interview Practice

96. Interview practice nên theo ngành hay theo skill?
97. Có nên có question bank lớn không?
98. AI có generate question theo CV/resume của user không?
99. User có upload CV/resume không?
100. Nếu có upload CV, dữ liệu đó có nhạy cảm không và xử lý thế nào?
101. Có nên có follow-up questions tự động không?
102. Có nên có mock interview realtime không?
103. Có nên có mock interview dạng async: hỏi → user record → feedback không?
104. Có nên có timer cho câu trả lời không?
105. Câu trả lời nên dài bao lâu: 30s, 1 phút, 2 phút?
106. Có nên training framework STAR/PREP/CAR không?
107. Có nên có câu trả lời mẫu theo level: simple, intermediate, advanced không?
108. Có nên có câu trả lời mẫu theo persona không?
109. Có nên có câu trả lời “bad answer vs good answer” không?
110. Có nên có ngân hàng câu hỏi riêng cho behavioral, technical, HR, salary, culture fit không?

### 12.9 Software Engineer Track

111. Software Engineer track nên nhắm tới frontend, backend, fullstack, mobile, devops hay general?
112. Có cần technical vocabulary theo stack không?
113. Có cần luyện giải thích project không?
114. Có cần luyện system design bằng tiếng Anh không?
115. Có cần luyện thuật toán/data structure bằng tiếng Anh không?
116. Có cần luyện behavioral cho engineer không?
117. Có cần luyện standup/update/status report không?
118. Có cần luyện code review discussion không?
119. Có cần luyện conflict với teammate/PM không?
120. Có cần luyện salary negotiation cho engineer không?
121. Có cần user nhập tech stack để AI cá nhân hóa content không?
122. Có cần user nhập project thật của họ để generate câu hỏi không?
123. Có cần tạo “project story bank” cho user không?
124. Có cần luyện “Tell me about a challenging bug” không?
125. Có cần luyện “Explain technical concept simply” không?

### 12.10 Purchasing / Business Track

126. Purchasing track nên tập trung vào phỏng vấn, workplace communication, hay cả hai?
127. Có cần vocabulary ngành garment/textile không?
128. Có cần luyện supplier negotiation không?
129. Có cần luyện email với supplier không?
130. Có cần luyện meeting/reporting không?
131. Có cần luyện cost/quality/deadline issue scenarios không?
132. Có cần luyện giải thích purchasing process không?
133. Có cần luyện KPI/achievement trong procurement không?
134. Có cần luyện complaint/escalation scenarios không?
135. Có cần luyện cross-cultural communication không?
136. Có cần luyện phone call scripts không?
137. Có cần luyện small talk công sở không?
138. Có cần luyện presentation/report bằng tiếng Anh không?
139. Có cần user nhập industry/company context không?
140. Có cần glossary riêng cho garment purchasing không?

### 12.11 Vocabulary System

141. Từ vựng nên học độc lập hay luôn gắn với lesson?
142. Có cần flashcard không?
143. Có cần spaced repetition không?
144. Có cần phrasebook không?
145. Có cần collocation bank không?
146. Có cần sentence pattern bank không?
147. Có cần phân biệt từ active/passive vocabulary không?
148. Có nên ưu tiên phrase thay vì single word không?
149. Có nên có ví dụ theo ngành nghề không?
150. Có nên có quiz từ vựng mỗi ngày không?
151. Có nên cho user lưu từ/cụm từ yêu thích không?
152. Có nên AI giải thích từ bằng tiếng Việt không?
153. Có nên AI tạo ví dụ mới theo công việc của user không?
154. Có nên có pronunciation audio cho từng phrase không?
155. Có nên tracking từ nào user đã dùng được trong speaking không?

### 12.12 Grammar System

156. Grammar nên là module riêng hay chỉ là feedback theo ngữ cảnh?
157. Có nên có mini grammar lessons không?
158. Có nên tập trung vào lỗi phổ biến của người Việt không?
159. Có nên sửa grammar trong câu trả lời speaking transcript không?
160. Có nên giải thích lỗi bằng tiếng Việt không?
161. Có nên tạo bài tập từ lỗi cá nhân của user không?
162. Có nên có grammar score không?
163. Có nên có rewrite suggestions không?
164. Có nên so sánh “your sentence” vs “better sentence” không?
165. Có nên lưu lỗi grammar lặp lại không?
166. Có nên có grammar drills theo interview context không?
167. Có nên tránh grammar theory dài không?
168. Có nên có “grammar for confidence” thay vì academic grammar không?
169. Có nên có grammar priority: lỗi nào ảnh hưởng meaning thì sửa trước?
170. Có nên có chế độ chỉ sửa 1–2 lỗi quan trọng để user không nản không?

### 12.13 Listening System

171. Listening nên dùng audio AI-generated hay video/audio nguồn ngoài?
172. Có cần nhiều accent không?
173. Accent ưu tiên là US, UK, Singapore/Malaysia, Indian, Australian?
174. Có cần luyện nghe interviewer nói nhanh không?
175. Có cần transcript interactive không?
176. Có cần dictation không?
177. Có cần comprehension questions không?
178. Có cần listen-and-repeat không?
179. Có cần nghe câu hỏi rồi trả lời ngay không?
180. Có cần lưu câu nghe khó không?
181. Có cần phân loại listening theo level không?
182. Có cần audio speed control không?
183. Có cần chunking theo phrase không?
184. Có cần shadowing từ listening passage không?
185. Có cần luyện nghe trong bối cảnh meeting/workplace không?

### 12.14 AI Content Generation / MiniMax 2.7

186. MiniMax 2.7 sẽ dùng cho những việc gì: text generation, voice, speech, feedback, roleplay, hay tất cả?
187. Có API key sẵn chưa?
188. Có giới hạn chi phí/tháng không?
189. Có cần fallback provider không?
190. Có cần cache nội dung AI generate không?
191. Có cần review/approve nội dung AI trước khi user học không?
192. Có cần content versioning không?
193. AI generate content theo prompt template hay tự do?
194. Có cần prompt library riêng không?
195. Có cần lưu prompt đã dùng để generate mỗi lesson không?
196. Có cần regenerate lesson nếu user đổi mục tiêu/level không?
197. Có cần batch-generate 60 ngày trước hay generate từng ngày?
198. Có cần generate audio luôn không?
199. Có cần kiểm tra chất lượng/correctness của nội dung AI không?
200. Có cần chống hallucination trong technical/business content không?
201. Có cần dùng AI để chấm speaking không?
202. Có cần dùng speech-to-text trước khi chấm không?
203. Có cần AI đóng vai interviewer không?
204. Có cần AI đóng vai coach nghiêm khắc/thân thiện không?
205. Có cần nhiều coach persona không?

### 12.15 Feedback / Scoring

206. Feedback nên bằng tiếng Việt, tiếng Anh, hay song ngữ?
207. Feedback nên chi tiết hay ngắn gọn?
208. Có nên giới hạn mỗi lần feedback chỉ 3 điểm chính không?
209. Rubric chấm điểm gồm những gì?
210. Có nên có điểm tổng không?
211. Có nên có điểm từng phần không?
212. Có nên cho user xem tiến bộ qua chart không?
213. Có nên feedback ngay sau mỗi câu trả lời không?
214. Có nên có delayed weekly report không?
215. Có nên có feedback tích cực trước rồi mới sửa lỗi không?
216. Có nên có “next best action” sau mỗi feedback không?
217. Có nên tạo bài tập cá nhân hóa từ lỗi vừa mắc không?
218. Có nên lưu lịch sử lỗi không?
219. Có nên phát hiện lỗi lặp lại theo tuần không?
220. Có nên có coach tone: gentle, direct, strict?

### 12.16 Motivation / Habit

221. Điều gì khiến bạn và vợ bạn dễ bỏ học nhất?
222. Thời điểm học tốt nhất trong ngày là khi nào?
223. Có cần reminder không?
224. Reminder qua app, email, Telegram, Zalo, hay browser notification?
225. Có cần streak không?
226. Streak mất có gây nản không?
227. Có nên có recovery plan khi bỏ 3 ngày?
228. Có nên có weekly celebration không?
229. Có nên có milestone rewards không?
230. Có nên có accountability giữa 2 vợ chồng không?
231. Có nên thấy progress của nhau không?
232. Có nên có partner challenge không?
233. Có nên có “study together” mode không?
234. Có nên có leaderboard nếu thêm bạn bè không?
235. Có nên gamify bằng XP/level không?

### 12.17 UX / UI

236. App dùng chủ yếu trên mobile hay desktop?
237. Có cần mobile-first không?
238. Có cần dark mode không?
239. Màn hình home nên gồm những gì?
240. Lesson page nên layout thế nào?
241. Speaking recorder nên đơn giản đến mức nào?
242. Có cần waveform không?
243. Có cần transcript side-by-side không?
244. Có cần player mini không?
245. Có cần dashboard không?
246. Có cần calendar view 60 ngày không?
247. Có cần kanban/progress map không?
248. Có cần onboarding đẹp không?
249. Có cần empty states/motivational copy không?
250. Có cần app dùng được tốt trên iPhone Safari không?

### 12.18 Data / Privacy / Security

251. User data gồm những gì?
252. Audio recording có được coi là dữ liệu nhạy cảm không?
253. Có lưu CV/resume không?
254. Có lưu thông tin công ty/ngành nghề không?
255. Có cần mã hóa audio không?
256. Có cần xóa dữ liệu vĩnh viễn không?
257. Có cần export dữ liệu cá nhân không?
258. Có cần privacy policy không nếu chỉ dùng private?
259. Nếu mở public, cần compliance gì?
260. Có được gửi audio/text sang MiniMax không?
261. Có cần thông báo rõ cho user là dữ liệu được xử lý bởi AI provider không?
262. Có cần ẩn thông tin cá nhân khi gửi prompt không?
263. Có cần audit log cho admin không?
264. Có cần role/permission không?
265. Có cần chống lộ API key không?

### 12.19 Technical Architecture

266. Bạn muốn dùng stack nào: Next.js, React/Vite, Remix, Nuxt, hay khác?
267. Backend muốn dùng Supabase, Firebase, self-hosted, hay serverless riêng?
268. Có cần database relational không?
269. Có cần auth ngay không?
270. Có cần multi-user ngay không?
271. Có cần admin CMS ngay không?
272. Content lưu trong DB, markdown files, JSON, hay headless CMS?
273. Audio lưu ở đâu?
274. Có cần CDN không?
275. Có cần queue/background jobs để generate content/audio không?
276. Có cần cron jobs cho reminder không?
277. Có cần analytics event tracking không?
278. Có cần feature flags không?
279. Có cần offline-first không?
280. Có cần sync conflict handling không?

### 12.20 Admin / Content Ops

281. Ai là người tạo/chỉnh content?
282. Có cần giao diện admin thân thiện không?
283. Có cần bulk generate lessons không?
284. Có cần bulk import/export CSV/JSON không?
285. Có cần duyệt nội dung trước khi publish không?
286. Có cần trạng thái draft/published/archived không?
287. Có cần tag content theo level/persona/skill/day không?
288. Có cần tái sử dụng content giữa các track không?
289. Có cần content template không?
290. Có cần lesson preview không?
291. Có cần regenerate từng phần: question, answer, vocab, audio không?
292. Có cần đánh dấu content chất lượng kém không?
293. Có cần user feedback về lesson không?
294. Có cần A/B test content không?
295. Có cần library prompts cho admin không?

### 12.21 Testing / Validation

296. Có muốn chạy test thủ công 7–14 ngày trước khi build đầy đủ không?
297. Ai sẽ là 3–5 user test đầu tiên?
298. Test đầu tiên đo cái gì?
299. Tiêu chí thành công sau 7 ngày là gì?
300. Tiêu chí thành công sau 14 ngày là gì?
301. User phải học bao nhiêu ngày/tuần thì coi là có traction?
302. User phải record bao nhiêu câu trả lời thì coi là engaged?
303. Có hỏi user confidence trước/sau không?
304. Có thu qualitative feedback không?
305. Có đo willingness-to-pay không?
306. Có muốn bán thử cohort thủ công không?
307. Có muốn landing page waitlist không?
308. Có muốn prototype Figma trước không?
309. Có muốn clickable prototype trước code không?
310. Có muốn dùng chính app nội bộ trước khi mở cho ai khác không?

### 12.22 MVP Boundary — sẽ chốt sau idea phase

311. Feature nào bạn chắc chắn muốn có trong MVP?
312. Feature nào bạn chắc chắn không cần trong MVP?
313. Nếu chỉ build trong 2 tuần, bạn chọn gì?
314. Nếu chỉ build trong 4 tuần, bạn chọn gì?
315. Nếu chỉ build trong 8 tuần, bạn chọn gì?
316. AI feedback có bắt buộc trong MVP không?
317. Audio recording có bắt buộc trong MVP không?
318. Admin CMS có bắt buộc trong MVP không?
319. Multi-user có bắt buộc trong MVP không?
320. PWA installable có bắt buộc trong MVP không?
321. Offline có bắt buộc trong MVP không?
322. Payment có bắt buộc trong MVP không?
323. Community có bắt buộc trong MVP không?
324. Gamification mức nào là đủ cho MVP?
325. Điều gì nếu không có thì sản phẩm mất linh hồn?

### 12.23 Open Discussion Prompts

326. Bạn muốn sản phẩm này thay đổi thói quen học tiếng Anh của hai vợ chồng như thế nào?
327. Trải nghiệm học tiếng Anh trước đây của bạn thất bại vì lý do gì?
328. Trải nghiệm học tiếng Anh trước đây của vợ bạn thất bại vì lý do gì?
329. Bạn ghét điều gì nhất ở các app học tiếng Anh hiện tại?
330. Bạn thích điều gì nhất ở các app học tiếng Anh hiện tại?
331. Bạn muốn app này có cảm giác “chỉ dành riêng cho mình” ở điểm nào?
332. Nếu app này thành công, 6 tháng nữa nó trông như thế nào?
333. Nếu app này thất bại, lý do khả năng cao nhất là gì?
334. Bạn muốn tránh build nhầm thứ gì nhất?
335. Bạn muốn chúng ta thảo luận sâu nhất nhánh nào trước: curriculum, AI feedback, speaking/shadowing, content generation, UX, hay architecture?

### 12.24 Deep Dive Needed — Recording Storage & UX

Câu hỏi cần phân tích sâu với agents:

- App có nên lưu recording để user nghe lại và so sánh tiến bộ không?
- Nếu lưu, nên lưu ở đâu: local device, server storage, cloud storage, hay hybrid?
- Lưu bao lâu?
- Có nên auto-delete không?
- User có thể tắt lưu tự động không?
- User có thể xóa từng recording hoặc toàn bộ recording không?
- Recording có nên gắn với lesson/attempt/score/feedback không?
- FE nên hiển thị recording history thế nào để user thấy tiến bộ mà không bị quá tải?
- BE nên thiết kế media storage, metadata, permission và cleanup thế nào?
- Audio là dữ liệu riêng tư/nhạy cảm nên cần privacy-by-design.
- Cần Architect, UX và Security cùng phân tích trước khi chốt.

### 12.25 Decision — Audio Storage Direction

Quyết định tạm thời từ user:

- App nên tự lưu audio thay vì chỉ xử lý tạm rồi xoá ngay.
- Lý do: audio phục vụ học tiếng Anh và chỉ user đó mới xem/nghe được.
- User đánh giá dữ liệu này không quá nhạy cảm trong bối cảnh private learning app.
- Việc lưu audio giúp tránh gọi lại API text-to-speech nhiều lần, giảm chi phí MiniMax khi user mở lại bài cũ.

Cần tách rõ 2 loại audio:

1. **AI-generated audio / TTS audio**
   - Audio được generate từ text bài học, câu hỏi, câu trả lời mẫu, vocabulary, phrase và script shadowing.
   - Nên cache/lưu lại mặc định để tiết kiệm chi phí API.
   - Có thể lưu server/cloud/object storage vì đây không phải giọng cá nhân của user.
   - Có thể reuse khi user học lại lesson cũ.

2. **User recording audio**
   - Giọng nói của user khi luyện shadowing/speaking.
   - Có thể lưu mặc định để user nghe lại, so sánh tiến bộ và xem practice history.
   - Vẫn cần private-by-default: chỉ chủ tài khoản truy cập được, có nút xóa, có setting bật/tắt lưu, không public/share mặc định.
   - Nếu sau này mở public, vẫn nên xem user recording là dữ liệu riêng tư cần bảo vệ.

Hướng thiết kế đã được Architect khuyến nghị:

- Chọn **hybrid local + cloud**.
- **AI-generated/TTS audio**: cloud/object storage là source of truth, cache thêm ở local device để playback nhanh/offline và tiết kiệm chi phí.
- **User recording audio**: local-first mặc định, cloud backup/sync là opt-in.
- **Metadata/score/feedback/transcript**: nên lưu server để theo dõi tiến bộ dài hạn.
- TTS audio cần hash theo normalized text + voice + speed + model + version để tránh gọi lại MiniMax khi nội dung không đổi.
- Client nên cache TTS bằng Cache Storage/Service Worker; user recordings nên lưu local bằng IndexedDB.
- Nếu user bật cloud backup, user recordings upload vào private object storage với signed URL, access control và quyền xóa rõ ràng.
- Local storage không được xem là bền vững tuyệt đối trên mobile browser, đặc biệt iOS Safari; cần cảnh báo nếu recording chỉ lưu local.
- App cần đăng nhập ngay từ đầu vì phải lưu profile, lesson history, score, sticky notes, vocab cards, audio cache/recording metadata và tiến độ học theo từng user.
- Ưu tiên đăng nhập bằng Google để tiện, giảm friction và tránh phải tạo tài khoản/password riêng.


### 12.26 Deep Dive Needed — Multi Learning Profiles / Personas

Ý tưởng quan trọng:

- Một user/account có thể có nhiều learning profiles/personas.
- Ví dụ: một người có thể có profile `Software Engineer Interview`, `Daily Communication`, `Business English`; hoặc một gia đình có thể dùng nhiều profile khác nhau cho từng người.
- Mỗi profile có thể có mục tiêu, level, ngành nghề, lộ trình, lesson history, vocab cards, sticky notes, score, recording history và chat context riêng.
- Đây là feature rất hay nhưng có nhiều issue cần cover kỹ khi define function cụ thể.

Các vấn đề cần thảo luận sâu sau:

- Một Google account tương ứng một người hay có thể chứa nhiều người/profile?
- Profile là “người học” hay “mục tiêu học”?
- Một user có thể học nhiều profile song song không?
- Có switch profile trong UI không?
- Có profile mặc định không?
- Có thể clone/copy profile không?
- Có thể archive/delete profile không?
- Notes/vocab/sticky có tách riêng theo profile hay có global knowledge base chung?
- Recording/audio có tách riêng theo profile không?
- Progress/streak tính theo account hay theo profile?
- Chatbox context lấy theo lesson/profile hiện tại hay toàn bộ account?
- Obsidian export theo từng profile hay toàn bộ account?
- Nếu sau này public/monetize, pricing tính theo account hay số profile?
- Nếu một gia đình dùng chung account, privacy giữa các profile xử lý thế nào?

- Tạm thời chỉ tập trung cho cá nhân, không ưu tiên family mode ở giai đoạn đầu.
- Profile nên đại diện cho một mục tiêu học/persona của chính user đang đăng nhập.
- Family/shared account để sau vì không phải trọng tâm hiện tại của app.
- Một user cá nhân có thể tạo nhiều profile theo mục tiêu/persona học khác nhau.
- Tuy nhiên phase đầu nên ưu tiên 1 active profile chính để tránh loãng lộ trình và giảm độ phức tạp UX.
- Các profile khác có thể tạo sau, switch khi cần, hoặc archive nếu không còn học.

### 12.27 UX Decision — Mobile Home Screen

UX Designer đề xuất Home screen mobile-first nên trả lời trong 3 giây câu hỏi:

> “Hôm nay mình nên luyện gì?”

Home không nên là dashboard nặng, mà là **Daily Coach Desk**.

Thứ tự ưu tiên Home mobile:

1. **Header nhỏ, cá nhân hóa**: greeting, active profile, streak/trạng thái học, settings.
2. **Hero card — Today’s Mission**: mission luyện nói/shadowing hôm nay, focus, thời lượng, CTA `Start practice`.
3. **Quick actions tối đa 4 nút**: `Generate lesson`, `Continue`, `Review vocab`, `Ask AI Coach`.
4. **Practice queue card**: next small step như pronunciation retry, vocab cards, sticky cần xem lại.
5. **Progress snapshot ngắn**: 2–3 chỉ số như speaking days, fluency improvement, weak sound.
6. **Recent lessons / recommendations**: gợi ý lesson phù hợp với profile/history.

Bottom navigation đã chọn:

- `Home · Lessons · Review · Notes · Coach`

- Phase đầu, tab `Coach` không nhất thiết là chat tự do toàn app.
- Vì chatbox ưu tiên nằm trong context từng lesson, tab `Coach` có thể là nơi quản lý coach settings, coach tone, active learning profile, AI guidance/history, và các gợi ý học tập tổng quan.
- Chat tự do toàn app có thể để phase sau nếu thật sự cần.

Moment of delight nên đến từ tiến bộ cá nhân hóa:

- `You sounded more confident today.`
- `Yesterday you paused 7 times. Today: 4 times.`
- `Best sentence: “I’m especially proud of...”`

Nguyên tắc giảm friction:

- Luôn có Today’s Mission để user không phải nghĩ nên học gì.
- Không đưa quá nhiều lựa chọn ngay Home.
- Recording cần microcopy rõ: `Record privately. You can delete anytime.`
- Review queue chỉ hiển thị next small step.
- Feedback sau speaking nên ngắn: 1 điểm tốt, 1 điểm cần sửa, 1 phrase nên dùng lại.

Empty state/first-run:

- Không show dashboard trống.
- Sau onboarding, tạo ngay first mission.
- Ví dụ: `Your first mission is ready — Shadow a 45-sec answer: Tell me about yourself.`

Idea UX táo bạo:

- Coach mở đầu bằng voice/live session preview thay vì dashboard tĩnh.
- Home hiển thị: `Today we’ll practice your answer to...` với nút `Play coach demo`, `Start shadowing`, `Change mission`.

### 12.28 Future Feature — Weekly Insights / Điểm cần củng cố

Sau khi trao đổi với PM, UX và Architect, hướng tạm chốt:

- Nên có feature AI tự động phát hiện các điểm user cần củng cố theo tuần, nhưng không cần làm quá sớm.
- Feature này chỉ nên triển khai khi app đã có đủ dữ liệu luyện nói/shadowing, feedback, transcript, score và lỗi được chuẩn hóa.
- Không nên gọi là “lỗi lặp lại” trong UI vì dễ tạo cảm giác bị phán xét.
- Nên gọi là:
  - `Điểm cần củng cố tuần này`
  - `Luyện nhanh cá nhân hóa`
  - `Practice boost`

Product value:

- Giúp user biết tuần này nên tập trung sửa gì.
- Giảm học lan man.
- Tạo cảm giác app giống coach thật: nhớ điểm yếu, theo dõi tiến bộ, gợi ý bài luyện phù hợp.
- Giúp review queue thông minh hơn.

MVP level cho feature này:

- Chạy theo tuần, không cần realtime.
- Chỉ hiển thị top 1–3 điểm cần củng cố.
- Gợi ý 1–2 bài luyện ngắn cho mỗi điểm.
- Ưu tiên rule-based + LLM summary thay vì AI phức tạp toàn bộ.
- Chỉ generate weekly insight nếu user có đủ activity trong tuần, ví dụ >= 2 speaking/shadowing sessions.

UX placement:

- **Home**: hiện 1 card nhỏ nhắc nhẹ, ví dụ `Luyện nhanh hôm nay: dùng a/an/the tự nhiên hơn`.
- **Review**: là nơi user thực sự luyện bài ngắn 3–7 phút.
- **Progress**: hiển thị trend cải thiện, không show bảng lỗi nặng nề.
- **Coach**: chỉ giải thích thêm nếu user hỏi.

Tone/microcopy:

- Dùng từ: củng cố, luyện thêm, gần thành thạo, mẫu hay gặp, luyện nhanh, tiến bộ.
- Tránh từ: lỗi, sai nhiều, yếu, thất bại, worst, failed.

Data foundation cần có:

- Practice sessions.
- Transcripts.
- Feedback items chuẩn hóa.
- Error category/sub-category/pattern key.
- Weekly metrics.
- Weekly mistake/learning patterns.
- Weekly AI insight summary.

Metrics nên lưu:

- Sessions/week.
- Total speaking minutes.
- Average practice score.
- Pronunciation/fluency/grammar/vocab score trends.
- Feedback item category.
- Pattern frequency.
- Severity.
- Trend: new, recurring, improving, worsening, resolved candidate.
- User có click/làm bài luyện đề xuất không.

Architecture recommendation:

- Sau mỗi practice session, lưu feedback items đã chuẩn hóa.
- Weekly cron/worker aggregate dữ liệu.
- Rule-based detection tìm pattern lặp lại.
- LLM chỉ dùng để viết summary/action plan thân thiện.
- Không gửi toàn bộ transcript nếu không cần; ưu tiên gửi aggregate + examples để giảm cost và privacy risk.

Tạm thời đưa vào backlog sau khi core speaking/shadowing + feedback + review queue đã ổn định.

### 12.29 MiniMax Plan / Usage Quota Context

User hiện đang dùng gói **Max-Highspeed** của MiniMax.

Quota hiện có theo thông tin user cung cấp:

| Capability | Max-Highspeed quota |
|---|---:|
| M2.7-highspeed | 15,000 requests / 5 hours |
| Speech 2.8 | 19,000 characters / day |
| image-01 | 200 images / day |
| Hailuo-2.3-Fast 768P 6s | 3 videos / day |
| Hailuo-2.3 768P 6s | 3 videos / day |
| Music-2.6 | 100 songs / day, free for 2 weeks, <=5min each |

Implication cho thiết kế:

- M2.7-highspeed request quota khá rộng cho text/chat/lesson generation trong giai đoạn private/small group.
- Speech 2.8 giới hạn 19,000 characters/day nên TTS cần được cache/dedupe mạnh.
- TTS không nên generate lại nếu normalized text + voice + speed + model/version giống nhau.
- Với quota Speech 2.8 giới hạn 19,000 characters/day, TTS cần được dùng có chọn lọc.
- Ưu tiên TTS cho sample answer/script shadowing, câu hỏi chính, vocab/phrases quan trọng.
- Theo quyết định của user, phase đầu TTS tập trung cho đoạn script được AI generate ra để phục vụ nghe, shadowing và speaking practice.
- Không cần TTS toàn bộ mọi nội dung dài trong lesson.
- Script TTS mặc định nên dài khoảng 45–90 giây audio.
- Script cần được chia thành chunks 5–15 giây để user dễ shadowing theo phrase/sentence/full answer.
- Các nội dung như giải thích dài, chatbox, metadata, hoặc notes không cần generate TTS mặc định.
- image-01 có 200 images/day nhưng image generation chưa phải core phase đầu.
- Video generation quota rất thấp, chỉ 3 videos/day nên text-to-video nên để future/experimental, không dùng trong core flow.
- Cần usage tracking nội bộ theo user/day/capability để tránh vượt quota.
- Dù chưa có payment, vẫn nên có daily quota mềm cho lesson generation, TTS, chatbox và feedback để kiểm soát cost/quota.
- Ưu tiên cache TTS, reuse generated audio, batch/pre-generate hợp lý, và giới hạn độ dài lesson/audio.

## 13. Quy trình đề xuất tiếp theo

1. Tiếp tục idea phase để liệt kê thêm feature, use case, learning flow, content structure.
2. Dùng `grill-me` để hỏi sâu từng nhánh: persona, core loop, learning path, feedback, content, motivation.
3. Khi đủ rõ, gọi `council` thêm một vòng để phản biện bản brief.
4. Sau idea phase, cài/áp dụng BMAD-lite để chuyển sang planning:
   - PRD.
   - Architecture.
   - Epics/stories.
   - MVP scope.
   - Roadmap.
5. Chỉ sau đó mới bắt đầu build.

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

