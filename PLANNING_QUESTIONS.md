# Planning Questions — Personalized English Coach PWA

Mục tiêu của file này là gom thông tin đã tổng hợp từ `IDEA_BRIEF.md` và danh sách câu hỏi cần trả lời tuần tự trước khi chuyển sang BMAD/planning.

---

## 0. Tóm tắt hiện trạng

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

## 2. Target Users / Personas

### Q9. Persona phase đầu gồm những ai?

Thông tin hiện tại:

- Software Engineer.
- Purchasing / Business / Garment professional.
- General Professional có thể cần.
- Student/Fresher có thể để sau hoặc hỗ trợ nhẹ.

Options:

1. Chỉ Software Engineer trước.
2. Software Engineer + Purchasing/Business.
3. Software Engineer + Purchasing/Business + General Professional.
4. Multi-persona ngay từ content system, nhưng UI phase đầu chỉ đơn giản.

Trả lời:

> **Phase đầu nên chọn: người Việt đi làm A2/B1 muốn nói tiếng Anh tự tin hơn trong phỏng vấn và công việc.**
>
> Về product/content system, nên hỗ trợ 2 track cụ thể trước:
>
> 1. **Software Engineer** — interview, project explanation, technical/workplace communication.
> 2. **Purchasing / Business / Garment professional** — workplace communication, supplier/vendor, negotiation, reporting, interview.
>
> Có thể có option **General Professional** ở onboarding để không khóa user ngoài 2 ngành, nhưng nội dung tốt nhất ban đầu vẫn nên tối ưu cho 2 track thật. Không nên mở rộng ngay sang student, travel English, sales, manager, community quá sớm.

---

### Q10. Level đầu vào tối thiểu là gì?

Thông tin hiện tại:

- App không phục vụ người mất gốc ở giai đoạn đầu.
- Ưu tiên A2/B1 trở lên.

Options:

1. A2 trở lên.
2. B1 trở lên.
3. A2/B1 trở lên, nhưng onboarding tự điều chỉnh độ khó.

Trả lời:

> **A2 high đến B1/B1+ là sweet spot.**
>
> App không nên phục vụ người mất gốc/A1 ở phase đầu vì họ thiếu vốn câu, cần nhiều foundation và dễ bỏ cuộc. B2+ có kỳ vọng cao hơn và dễ so sánh trực tiếp với ChatGPT Voice hoặc tutor thật.
>
> Cách diễn đạt nên là: **Phù hợp nhất với người đã có nền tảng tiếng Anh cơ bản, đọc/nghe được câu đơn giản, nhưng thiếu phản xạ nói và thiếu tự tin khi phỏng vấn/giao tiếp công việc.**
>
> Onboarding nên có quick check: đọc/nghe vài câu + trả lời 1 câu hỏi 30 giây để app điều chỉnh độ khó.

---

### Q11. Có cần nói rõ app không dành cho người mất gốc không?

Gợi ý:

- Nên nói mềm: “Phù hợp nhất với người đã có nền tảng cơ bản và muốn luyện phản xạ nói/phỏng vấn.”

Trả lời:

> **Có, cần nói rõ nhưng dùng cách diễn đạt mềm.**
>
> Không nên viết “app không dành cho người mất gốc” như một câu loại trừ trực diện. Nên viết:
>
> **SpeakFit phù hợp nhất nếu bạn đã có nền tảng tiếng Anh cơ bản, có thể hiểu/nói câu đơn giản, và muốn luyện phản xạ nói trong phỏng vấn hoặc công việc.**
>
> Lý do: nếu nhận cả người mất gốc/A0-A1, scope sẽ bị kéo sang phát âm cơ bản, từ vựng nền, grammar nhập môn và placement dài. Đây là scope creep lớn, không phù hợp MVP.
>
> Onboarding nên có self-check nhẹ: nghe/lặp lại 1 câu + trả lời 1 câu hỏi 30 giây. Nếu user chưa sẵn sàng, app có thể gợi ý học foundation trước thay vì tạo trải nghiệm thất bại.

---

### Q12. Một account có nhiều learning profiles không?

Thông tin hiện tại:

- Ý tưởng multi-profile rất hay nhưng phức tạp.
- Tạm thời nên tập trung 1 active profile chính.
- Profile nên đại diện cho mục tiêu học/persona của chính user, không phải family mode.

Options:

1. MVP chỉ 1 profile.
2. MVP có 1 active profile, chuẩn bị data model cho nhiều profile sau.
3. MVP hỗ trợ nhiều profile đầy đủ.

Trả lời:

> **MVP nên có 1 active profile chính, nhưng data model nên chuẩn bị `profileId` để mở rộng nhiều profile sau.**
>
> Không nên làm multi-profile/family mode đầy đủ trong MVP vì tăng complexity UX, progress, notes, audio, streak, pricing và privacy. Phase đầu chỉ cần một learner chính với một mục tiêu chính.
>
> Kiến trúc nên thiết kế theo hướng:
>
> `User -> LearningProfile -> Lesson/PracticeSession -> Attempt/Recording -> Feedback/Notes`
>
> Như vậy sau này có thể thêm nhiều profile, archive/switch profile hoặc family mode mà không phải refactor lớn.

---

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

## 4. Core User Journey

### Q17. User mở app lên thì màn hình đầu tiên hiển thị gì?

Đề xuất hiện tại:

- Daily Coach Desk.
- Today’s Mission card.
- CTA Start practice.
- Practice queue nhỏ.
- Progress snapshot ngắn.

Trả lời:

> **Màn hình đầu tiên nên là Daily Coach Desk, tập trung vào Today’s Mission, không phải dashboard hay lesson library.**
>
> Câu hỏi Home phải trả lời trong 3 giây:
>
> **“Hôm nay mình nên luyện gì?”**
>
> Cấu trúc đề xuất:
>
> ### 1. Header nhỏ
>
> Ví dụ:
>
> `Hi Long · Software Engineer Interview · Day 8/60`
>
> Hiển thị nhẹ:
>
> - active profile/goal;
> - streak mềm;
> - settings/profile switch nếu cần, nhưng không nổi bật.
>
> ### 2. Hero card — Today’s Mission
>
> Đây là phần quan trọng nhất.
>
> Ví dụ:
>
> **Today’s Mission**  
> Answer: `Tell me about a project you are proud of.`  
> Goal: trả lời rõ trong 60–90 giây  
> Focus: STAR structure + past tense  
> Time: 7 phút  
> CTA: **Start Practice**
>
> Card này nên có:
>
> - mission title;
> - context;
> - skill focus;
> - thời lượng;
> - difficulty;
> - CTA chính rõ ràng.
>
> ### 3. Mini preview để giảm anxiety
>
> Trước khi user bấm Start, có thể show 2–3 phrase sẽ học:
>
> - `I was responsible for...`
> - `The main challenge was...`
> - `As a result...`
>
> Điều này giúp user cảm thấy “mình có đường vào”, không bị ném thẳng vào mic.
>
> ### 4. Practice queue nhỏ
>
> Không nên chiếm spotlight. Chỉ hiển thị 1–3 item:
>
> - Retry yesterday’s answer.
> - Review phrase: `I’m confident that...`
> - Shadowing 30s sample answer.
>
> ### 5. Progress snapshot ngắn
>
> Chỉ cần 2–3 chỉ số dễ hiểu:
>
> - `5-day streak`
> - `12 answers recorded`
> - `Confidence +8% this week`
>
> Không nên show dashboard đầy chart ở Home.
>
> ### 6. Secondary actions
>
> Để nhỏ hơn CTA chính:
>
> - Review saved phrases.
> - Generate new lesson.
> - Continue unfinished lesson.
> - Quiet mode.
>
> Không nên để AI Chat là CTA chính vì sẽ làm sản phẩm giống chatbot và loãng core loop.
>
> **First-run đặc biệt:** nếu user chưa onboarding, có thể cho trải nghiệm nhanh `Bắt đầu luyện 3 phút` hoặc `Try a speaking mission`, sau đó mới hỏi profile sâu hơn. Không nên bắt form dài trước khi user thấy value.

---

### Q18. Core loop chính xác của một buổi học là gì?

Đề xuất hiện tại:

1. Today’s mission.
2. Context/question/passage.
3. Key vocab/phrases.
4. Listen TTS.
5. Shadowing chunk/sentence/full answer.
6. User record hoặc text practice.
7. AI feedback ngắn.
8. Sample answer/better answer.
9. Save vocab/sticky.
10. Update review/progress.

Trả lời:

> **Core loop nên là: Mission → Warm-up → Speak/Shadow → Feedback → Retry → Save → Progress.**
>
> Mục tiêu là hoàn thành trong 5–10 phút, nhưng mỗi vòng nói nhỏ có thể chỉ 1–2 phút. Không nên biến lesson thành chuỗi đọc/xem/quiz dài rồi cuối cùng mới nói.
>
> Flow chi tiết:
>
> ### Step 1. Today’s Mission
>
> User thấy nhiệm vụ rõ:
>
> `Practice answering: Tell me about yourself.`
>
> Hiển thị:
>
> - goal;
> - context;
> - time estimate;
> - skill focus;
> - success criteria.
>
> Ví dụ:
>
> `Goal: trả lời trong 60 giây, rõ cấu trúc, ít ngập ngừng.`
>
> ### Step 2. Quick warm-up
>
> 30–60 giây, giảm áp lực trước khi nói.
>
> Có thể gồm:
>
> - nghe 2–3 phrases;
> - lặp lại 1 câu ngắn;
> - chọn ý chính muốn nói;
> - xem outline ngắn.
>
> Ví dụ phrases:
>
> - `I have experience in...`
> - `I was responsible for...`
> - `The main challenge was...`
>
> ### Step 3. Prompt / Question
>
> Hiển thị câu hỏi chính:
>
> `Tell me about a project you are proud of.`
>
> Microcopy:
>
> `Try to answer in 45–60 seconds. Don’t worry about mistakes.`
>
> ### Step 4. First attempt
>
> CTA chính:
>
> `Record my answer`
>
> CTA phụ:
>
> `I need help first` hoặc `Quiet mode`
>
> First attempt giúp app lấy dữ liệu thật: fluency, pause, vocab, grammar, confidence.
>
> ### Step 5. AI feedback ngắn
>
> Feedback nên có cấu trúc cố định:
>
> 1. Encouragement.
> 2. One thing you did well.
> 3. 1–2 things to improve.
> 4. Better sentence/phrase.
> 5. Next retry instruction.
>
> Ví dụ:
>
> `Bạn trả lời khá rõ ý. Điểm tốt: bạn nêu được vai trò của mình. Cần cải thiện: mở đầu nên ngắn hơn. Thử câu này: “I worked on a payment feature where I was responsible for the backend API.”`
>
> ### Step 6. Sample / better answer
>
> Sau feedback mới show sample answer đầy đủ.
>
> Nên có 2 version:
>
> - Simple version cho A2/B1.
> - Better version cho B1+.
>
> ### Step 7. Shadowing
>
> User nghe TTS và shadow theo 3 cấp:
>
> - phrase/chunk;
> - sentence;
> - full answer/dialogue.
>
> MVP chỉ cần playback, chunking, repeat, record/retry cơ bản. Không cần pronunciation scoring quá chi tiết.
>
> ### Step 8. Retry
>
> Đây là moment quan trọng.
>
> CTA:
>
> `Try again with better structure`
>
> App nên so sánh nhẹ:
>
> `Lần 2 rõ hơn: bạn dùng được phrase “I was responsible for...”`
>
> ### Step 9. Save phrase / sticky
>
> Cho user lưu 1–3 thứ:
>
> - phrase hay;
> - lỗi cần nhớ;
> - better sentence;
> - personal note.
>
> Không bắt lưu quá nhiều để tránh note trở thành kho rác.
>
> ### Step 10. Completion + next action
>
> Kết thúc bằng progress nhỏ:
>
> `Mission completed. You recorded 2 attempts today. Tomorrow: follow-up question about project challenges.`
>
> Core principle:
>
> **Speak early, correct lightly, retry quickly, save only what matters.**

---

### Q19. User nên trả lời trước khi xem sample answer không?

Options:

1. Luôn trả lời trước để đo khả năng thật.
2. Cho user chọn: Try first / Learn first.
3. Mặc định learn first để giảm anxiety.

Trả lời:

> **Nên mặc định Try first, nhưng không ép cứng. Có escape hatch: I need help first / Learn first.**
>
> Lý do nên Try first:
>
> - App lấy được năng lực thật, lỗi thật, mức ngập ngừng thật.
> - User không chỉ copy sample answer.
> - Feedback cá nhân hóa tốt hơn.
> - Tạo before/after rõ sau khi user retry.
>
> Nhưng nếu ép tất cả user nói trước, đặc biệt ngày đầu, một số người A2/B1 sẽ lo, bí, xấu hổ và thoát app. Vì vậy cần thiết kế mềm.
>
> ### Product rule đề xuất
>
> - **Default:** Try first.
> - **Fallback:** I need help first.
> - **Không show full sample answer ngay từ đầu.**
> - Nếu user cần giúp, show scaffold/outline/phrase starters trước, rồi mời user nói.
>
> ### UX đề xuất
>
> Màn prompt:
>
> `Hãy thử trả lời bằng tiếng Anh trước. Không cần đúng hoàn toàn — coach sẽ giúp bạn sửa.`
>
> CTA chính:
>
> `Record my answer`
>
> CTA phụ:
>
> `I need help first`
>
> Nếu user bấm `I need help first`, show:
>
> - outline;
> - key phrases;
> - sentence starters;
> - sample rất ngắn nếu cần.
>
> Ví dụ scaffold:
>
> 1. Project: `I worked on...`
> 2. Role: `I was responsible for...`
> 3. Challenge: `The main challenge was...`
> 4. Result: `As a result...`
>
> Sau đó mời:
>
> `Now try with your own words.`
>
> ### Ngoại lệ
>
> - First session/day 1 có thể cho `Learn first` nổi bật hơn để giảm anxiety.
> - Từ ngày 2–3 trở đi, default nên chuyển dần sang `Try first`.
> - Với shadowing lesson, sample-first là hợp lý vì mục tiêu là bắt chước audio.
> - Với interview answer/practice lesson, try-first nên là default.
>
> Kết luận:
>
> **Sample answer không nên là thứ user thấy đầu tiên. Thứ user thấy đầu tiên nên là câu hỏi, encouragement và scaffold nếu cần.**

---

### Q20. Có cho skip voice practice khi user không tiện nói không?

Gợi ý:

- Nên có text practice hoặc save for later.
- Nhưng core habit vẫn là speaking/shadowing.

Trả lời:

> **Có, nhưng phải là Quiet Mode / Prepare Mode, không phải skip trắng và không tính là completed speaking mission.**
>
> Lý do cần cho skip mềm:
>
> - User có thể đang ở văn phòng, trên xe, quán cà phê, nơi ồn.
> - User có thể ngại nói trước người khác.
> - User có thể chưa muốn cấp quyền micro.
> - Nếu ép voice 100%, retention sẽ giảm.
>
> Nhưng nếu cho skip quá dễ và vẫn tính completed, app sẽ dạy user tránh speaking. Đây là rủi ro phá core habit.
>
> ### Thiết kế 3 mode
>
> #### 1. Speak Now
>
> Mode chính.
>
> User:
>
> - record answer;
> - shadow chunks;
> - retry after feedback.
>
> Được tính:
>
> - mission completed;
> - speaking streak;
> - speaking progress.
>
> #### 2. Quiet Mode / Prepare Mode
>
> Khi user không tiện nói.
>
> User có thể:
>
> - nghe audio;
> - đọc transcript;
> - xem nghĩa tiếng Việt;
> - chọn key phrases;
> - gõ draft answer;
> - sắp xếp outline;
> - lưu phrase;
> - đặt reminder để nói sau.
>
> Status nên là:
>
> - `Prepared`
> - không phải `Completed`
>
> Daily streak có thể giữ nhẹ, nhưng speaking streak không tăng.
>
> #### 3. Save for later
>
> Khi user quá bận.
>
> CTA:
>
> - `Remind me tonight`
> - `Add to practice queue`
> - `Do voice later`
>
> ### Completion logic đề xuất
>
> - Nghe/đọc/lưu phrase nhưng không nói: **Prepared**.
> - Record ít nhất 1 lần hoặc shadow ít nhất 3 chunks: **Completed**.
> - Retry sau feedback: **Strong completion** hoặc bonus.
>
> ### Microcopy nên dùng
>
> Khi user không tiện nói:
>
> `Không tiện nói bây giờ? Bạn có thể chuẩn bị trước trong Quiet Mode và luyện nói lại sau.`
>
> Sau Quiet Mode:
>
> `Bạn đã chuẩn bị xong bài hôm nay. Để hoàn thành speaking mission, hãy record ít nhất 1 lần khi tiện nói.`
>
> Khi mic lỗi hoặc user im lặng:
>
> `Mình chưa nghe thấy gì. Bạn có thể thử lại, hoặc gõ câu trước.`
>
> ### Product rule
>
> **Voice is primary. Text is fallback. Skip is guided. Speaking progress only counts when user actually speaks.**

---

### Q21. Khi nào daily lesson được tính là completed?

Options:

1. Nghe + shadowing + record ít nhất 1 lần.
2. Hoàn thành main mission, optional bonus không bắt buộc.
3. User tự mark complete.
4. App tính theo checklist tối thiểu.

Trả lời:

> **Daily lesson nên được tính theo checklist tối thiểu, không cho user tự mark complete đơn thuần.**
>
> Completion phải đủ dễ để user không nản, nhưng đủ thật để không biến app thành nơi bấm qua bài. Với SpeakFit, điều kiện cốt lõi là user phải có một hành động speaking/shadowing thật.
>
> Đề xuất 4 trạng thái:
>
> 1. **Not started**
>    - User chưa mở lesson.
>
> 2. **Prepared**
>    - User đã nghe audio, đọc transcript, xem vocab/tips, gõ draft, lưu phrase.
>    - Chưa record hoặc chưa shadowing đủ.
>    - Có thể giữ daily learning streak nhẹ, nhưng không tính speaking streak.
>
> 3. **Completed**
>    - User hoàn thành main mission tối thiểu:
>      - với speaking/interview lesson: record ít nhất 1 answer attempt;
>      - với shadowing lesson: shadow ít nhất 3 chunks/sentences;
>      - đã xem feedback hoặc completion summary ngắn.
>    - Được tính lesson completed và speaking activity.
>
> 4. **Strong completed**
>    - User retry sau feedback, hoặc record lần 2, hoặc dùng được phrase/vocab mới trong câu trả lời.
>    - Đây là completion chất lượng cao, nên dùng làm progress signal tích cực.
>
> Vocabulary/tips nên là phần phụ trợ quan trọng nhưng không phải điều kiện bắt buộc để complete speaking mission. Tuy nhiên sau lesson nên có “vocab capture” nhẹ: user chọn 1–3 từ/cụm từ mới để lưu vào review queue.
>
> Rule ngắn:
>
> **Prepared khi user học nội dung; Completed khi user nói thật; Strong completed khi user nói lại tốt hơn.**

---

## 5. Curriculum / Learning Plan

### Q22. Lộ trình nên là 30/45/60/90 ngày hay mặc định 60 ngày?

Thông tin hiện tại:

- User muốn linh hoạt.
- Thiết kế trung tâm là 1 lesson/ngày.
- 60 ngày vẫn là định vị tốt.

Trả lời:

> **Nên giữ 60 ngày làm default positioning, nhưng kiến trúc nên hiểu đây là 60 lessons có thể học linh hoạt, không phải lịch cứng bắt buộc.**
>
> Lý do:
>
> - 60 ngày đủ mạnh về mặt marketing: có cảm giác bootcamp/fitness program.
> - Đủ dài để hình thành thói quen speaking/shadowing.
> - Không quá ngắn như crash course, không quá dài như course học tiếng Anh tổng quát.
>
> Tuy nhiên không nên bắt user chọn 30/45/60/90 ngay từ MVP vì làm onboarding và curriculum phức tạp. Phase đầu nên có:
>
> 1. **Default 60-day path**
>    - 1 mission/ngày.
>    - Có thể học chậm hơn mà không bị fail.
>
> 2. **Flexible pace**
>    - Vẫn là 60 missions.
>    - User có thể pause, skip, catch-up, recovery.
>    - App tính `behind schedule` nhẹ, không phạt.
>
> 3. **Crash mode 30 days**
>    - Để backlog.
>    - Phù hợp người sắp phỏng vấn gấp nhưng cần thiết kế riêng.
>
> 4. **90-day/deep mode**
>    - Để sau khi core loop chứng minh retention.
>
> Product rule:
>
> **MVP build một 60-day path nhẹ + flexible pacing, chưa build nhiều curriculum duration riêng.**

---

### Q23. 60 ngày có chia thành 8 tuần không?

Gợi ý tuần:

1. Self-introduction / foundation.
2. Experience / role / responsibility.
3. Project/work story.
4. Behavioral questions.
5. Workplace scenarios.
6. Negotiation/conflict/problem solving.
7. Mock interview.
8. Review/readiness.

Trả lời:

> **Có. Nên chia thành 8 tuần core curriculum + 4 ngày final readiness/catch-up.**
>
> 8 tuần = 56 ngày, nên 60 ngày có thể thiết kế như:
>
> - **Week 1–8:** core learning path.
> - **Days 57–60:** final review, catch-up, before/after comparison, final mock, next plan.
>
> Cấu trúc đề xuất:
>
> 1. **Week 1 — Start Strong / Baseline & Self-introduction**
>    - Dám nói vào mic.
>    - Self-introduction.
>    - Current role/goal.
>    - Speaking baseline.
>    - 5–10 phrase nền.
>
> 2. **Week 2 — Experience, Role & Responsibility**
>    - Nói về công việc hiện tại.
>    - Mô tả trách nhiệm.
>    - Nói về kỹ năng, task, tools/process.
>    - Vocabulary theo role/ngành.
>
> 3. **Week 3 — Project / Work Story**
>    - Giải thích project, case, achievement.
>    - Dùng STAR/PREP đơn giản.
>    - Kể challenge/result.
>    - Tạo story bank nhẹ.
>
> 4. **Week 4 — Behavioral Interview**
>    - Strength/weakness.
>    - Teamwork/conflict.
>    - Failure/challenge.
>    - Career goal.
>
> 5. **Week 5 — Workplace Communication**
>    - Meeting update.
>    - Asking for clarification.
>    - Explaining issues.
>    - Email/spoken phrases theo context.
>
> 6. **Week 6 — Problem Solving / Negotiation / Conflict**
>    - Với engineer: bug, deadline, technical tradeoff, disagreement.
>    - Với purchasing/business: supplier issue, cost, quality, delivery, negotiation.
>
> 7. **Week 7 — Mock Interview & Follow-up Questions**
>    - Mini/full mock.
>    - Follow-up questions.
>    - Timed answer.
>    - Pressure handling.
>
> 8. **Week 8 — Readiness & Personalization**
>    - Refine personal answers.
>    - Review weak points.
>    - Reuse saved phrases/vocab.
>    - Final speaking confidence.
>
> 9. **Days 57–60 — Final Readiness Sprint**
>    - Final mock.
>    - Before/after recordings.
>    - Personal phrasebook review.
>    - Next 30-day recommendation.
>
> Mỗi tuần nên có:
>
> - 5 main missions;
> - 1 review/catch-up day;
> - 1 optional/rest/recovery day.
>
> Không nên claim “8 tuần fluent”. Claim thực tế hơn:
>
> **8 tuần xây thói quen nói, luyện tình huống phổ biến và tăng interview/workplace readiness.**

---

### Q24. Week 1 nên là self-introduction hay assessment/foundation?

Options:

1. Self-introduction ngay.
2. Assessment nhẹ trước.
3. Kết hợp: self-introduction vừa là first mission vừa là baseline.

Trả lời:

> **Week 1 nên kết hợp: self-introduction vừa là first mission vừa là baseline assessment.**
>
> Không nên mở đầu bằng placement test khô cứng vì user cần thấy value ngay. Nhưng cũng cần baseline để cá nhân hóa feedback và progress.
>
> Tên tuần nên thân thiện:
>
> **Week 1: Start Strong — Introduce yourself clearly**
>
> Không nên gọi là “Assessment Week”.
>
> Mục tiêu Week 1:
>
> - user hiểu app hoạt động thế nào;
> - dám nói vào mic;
> - có first recording;
> - nhận feedback nhẹ;
> - lưu vài phrase nền;
> - thấy completion/win đầu tiên;
> - tạo baseline cho fluency, confidence, grammar, vocabulary, pronunciation/basic clarity.
>
> Gợi ý 7 ngày:
>
> 1. **Day 1 — Tell me about yourself**
>    - User nói 30–60 giây.
>    - App lấy baseline.
>    - Feedback cực nhẹ.
>
> 2. **Day 2 — Shadow your self-introduction**
>    - App tạo version tốt hơn.
>    - User shadow theo chunk.
>
> 3. **Day 3 — Current role / current job**
>    - `I work as...`, `I’m responsible for...`
>
> 4. **Day 4 — Why do you want to improve English?**
>    - Gắn với motivation cá nhân.
>
> 5. **Day 5 — Mini challenge**
>    - Nói 30–45 giây không xem full sample trước.
>
> 6. **Day 6 — Review phrases + vocab tips**
>    - Ôn 5–10 phrases/từ đã gặp.
>    - Có memory aids: collocation, word family, prefix/root nếu hữu ích.
>
> 7. **Day 7 — Week 1 mini reflection / mini mock**
>    - 2–3 câu hỏi nhẹ.
>    - So sánh cảm giác với Day 1.
>
> Week 1 không nên có grammar theory dài, vocab list 20 từ, mock interview nặng hoặc scoring gây áp lực.

---

### Q25. Mock interview bắt đầu từ khi nào?

Options:

1. Cuối tuần 1 dạng nhẹ.
2. Từ tuần 3–4.
3. Chỉ phase sau.

Trả lời:

> **Mock interview nên xuất hiện sớm dưới dạng mini mock nhẹ, nhưng full mock nên bắt đầu từ Week 4 hoặc Week 7.**
>
> Nếu đợi tới cuối khóa mới mock, user thiếu cảm giác đang tiến gần mục tiêu. Nhưng nếu mock interview đầy đủ quá sớm, user dễ anxiety và feature dễ scope creep.
>
> Lộ trình đề xuất:
>
> ### Week 1 — Mini baseline mock
>
> - 2–3 câu rất nhẹ.
> - Không chấm nặng.
> - Mục tiêu: baseline và làm quen.
> - Ví dụ:
>   - Tell me about yourself.
>   - What is your current role?
>   - Why do you want to improve English?
>
> ### Week 3–4 — Themed mini mock
>
> - 3–5 câu theo chủ đề.
> - Ví dụ:
>   - project/work story mock;
>   - behavioral mini mock;
>   - workplace situation mock.
> - Feedback theo clarity, structure, vocabulary.
>
> ### Week 7 — Main mock interview
>
> - 8–10 câu.
> - Có follow-up questions.
> - Có timed answer nếu user sẵn sàng.
> - Có practice/readiness score.
>
> ### Days 57–60 — Final mock + before/after
>
> - So sánh với Day 1.
> - Review câu khó.
> - Gợi ý plan tiếp theo.
>
> MVP không nên làm full realtime interview simulator phức tạp. Phase đầu chỉ cần async mock:
>
> **AI hỏi → user record → AI feedback → user retry câu khó.**
>
> Mock interview nên là activity tăng dần độ thật, không phải một feature khổng lồ ngay từ đầu.

---

### Q26. Có rest day/catch-up day không?

Gợi ý:

- Nên có streak mềm.
- Có recovery lesson 3–5 phút khi bỏ lỡ.

Trả lời:

> **Có, nhưng nên thiết kế là light review / catch-up day, không phải một hệ thống lịch học phức tạp.**
>
> Mỗi tuần nên có nhịp:
>
> - 5 ngày main speaking missions;
> - 1 ngày review/catch-up;
> - 1 ngày optional rest/recovery.
>
> Rest day không nên làm user cảm thấy “bỏ học”. Có thể gọi là:
>
> - `Light Review Day`
> - `Catch-up Day`
> - `Recovery Practice`
>
> Khi user bỏ lỡ bài:
>
> - Không dồn tất cả bài miss vào hôm sau.
> - Không phá streak bằng copy tiêu cực.
> - Ưu tiên recovery lesson 3–5 phút: shadow 3 câu dễ, ôn 3 phrase, retry 1 câu cũ.
>
> Copy nên dùng:
>
> `Không sao, hôm nay mình nối lại nhịp bằng một bài ngắn.`
>
> Completion/streak:
>
> - Main speaking mission tăng speaking streak.
> - Light review có thể giữ daily habit streak.
> - Nếu nghỉ thật, không nên phạt nặng.
>
> Product rule:
>
> **Rest/catch-up tồn tại để giữ habit, không phải để tạo thêm complexity lịch học.**

---

## 6. Speaking / Shadowing

### Q27. Shadowing là feature trung tâm hay phụ?

Thông tin hiện tại:

- Đã tạm chốt: shadowing là core habit trung tâm.

Trả lời:

> **Shadowing nên là feature trung tâm, nhưng không phải feature duy nhất.**
>
> Với người Việt A2/B1, shadowing rất quan trọng vì giúp:
>
> - có mẫu câu để bắt chước;
> - luyện rhythm/stress/intonation;
> - giảm áp lực phải tự nghĩ câu ngay;
> - tăng confidence trước khi trả lời tự do;
> - chuyển phrase/vocab từ passive sang active speaking.
>
> Tuy nhiên không nên biến SpeakFit thành pronunciation lab. Shadowing phải phục vụ mục tiêu lớn hơn: **nói rõ hơn trong interview/workplace context**.
>
> Flow chuẩn:
>
> 1. Nghe hiểu.
> 2. Shadow chậm theo chunk.
> 3. Shadow câu hoàn chỉnh.
> 4. Nói lại theo ý của mình.
>
> MVP không cần waveform, karaoke timing hoặc phoneme-level scoring. Chỉ cần audio mẫu, chunking, repeat, record/replay và feedback ngắn.

---

### Q28. Shadowing nên theo chunk, sentence hay full answer?

Đề xuất hiện tại:

- Hỗ trợ cả 3 cấp: phrase/chunk → sentence → full answer/dialogue.

Trả lời:

> **Nên hỗ trợ cả 3 cấp, nhưng theo progression mặc định: chunk → sentence → full answer.**
>
> Không nên bắt user tự cấu hình quá nhiều. App nên tự dẫn theo độ khó.
>
> 1. **Chunk mode**
>    - Dành cho người mới/ngại nói.
>    - Cụm 3–8 từ.
>    - Mục tiêu: phát âm rõ, bắt nhịp, nhớ phrase.
>    - Ví dụ: `I was responsible for...`
>
> 2. **Sentence mode**
>    - Câu hoàn chỉnh.
>    - Mục tiêu: grammar, word order, rhythm tự nhiên.
>    - Ví dụ: `I was responsible for building the backend API.`
>
> 3. **Full answer mode**
>    - Câu trả lời 30–90 giây hoặc dialogue ngắn.
>    - Mục tiêu: coherence, fluency, speaking under pressure.
>
> UX có thể có segmented control:
>
> `Chunk | Sentence | Full`
>
> Nhưng default nên theo user level:
>
> - A2/high anxiety: Chunk trước.
> - B1: Sentence trước.
> - B1+: Full answer sau khi warm-up.
>
> Product rule:
>
> **Start small, then combine. User không cần nói cả đoạn nếu chưa nói nổi từng cụm.**

---

### Q29. Audio mẫu nên dùng accent nào phase đầu?

Thông tin hiện tại:

- Ưu tiên clear international English hoặc US English.
- Sau này thêm UK, Australian, Singapore/Malaysia, Indian.

Trả lời:

> **Phase đầu nên dùng clear international English hoặc neutral US English.**
>
> Tiêu chí quan trọng nhất không phải native-like tuyệt đối, mà là:
>
> - rõ;
> - dễ nghe;
> - dễ shadow;
> - phù hợp interview/workplace;
> - không gây áp lực phải nói giống native.
>
> Không nên mở quá nhiều accent ở MVP vì làm UI rối, tăng TTS cache variants và làm user phân tâm.
>
> Phase đầu:
>
> - Default: neutral US / clear international English.
> - 1–2 voice mặc định: một nam, một nữ nếu quota/cost cho phép.
> - Copy: `Không cần nói giống 100%, chỉ cần rõ và tự nhiên.`
>
> Future:
>
> - UK, Australian.
> - Singapore/Malaysia, Indian English để luyện workplace thực tế.
> - Accent setting theo profile hoặc lesson.
>
> Product rule:
>
> **Optimize for intelligibility, not accent perfection.**

---

### Q30. Có cần slow/normal/interview speed không?

Gợi ý:

- Phase đầu nên có ít nhất slow + normal.

Trả lời:

> **Có. Phase đầu nên có ít nhất slow + normal; interview speed có thể để advanced/unlock dần.**
>
> Speed modes giúp giảm anxiety và hỗ trợ shadowing tốt hơn.
>
> Đề xuất MVP:
>
> 1. **Slow / Practice speed**
>    - Khoảng 0.75x–0.8x.
>    - Dùng để nghe rõ, bắt chunk, luyện pronunciation/rhythm.
>
> 2. **Normal speed**
>    - 1.0x.
>    - Dùng cho shadowing chính và sample answer.
>
> Future/optional:
>
> 3. **Interview speed**
>    - 1.1x–1.2x hoặc natural faster delivery.
>    - Dùng trong mock interview hoặc khi user đã quen.
>
> UX:
>
> - Nút speed đặt gần audio player.
> - Nhớ speed gần nhất của user.
> - Nếu user retry/fail nhiều, app gợi ý: `Thử slow speed để bắt nhịp dễ hơn.`
>
> Technical note:
>
> - MVP có thể dùng client-side playback speed để tiết kiệm TTS.
> - Với audio quan trọng, có thể generate TTS riêng cho slow/normal để giọng tự nhiên hơn.
> - TTS cache key cần gồm text + voice + speed + model/version.
>
> Product rule:
>
> **Speed phục vụ clarity và confidence, không phải ép user nói nhanh.**

---

### Q31. Có lưu tất cả user recordings không?

Thông tin hiện tại:

- User muốn app tự lưu audio.
- User recording local-first mặc định.
- Cloud backup opt-in.
- User có thể xóa.

Trả lời:

> **Không nên lưu tất cả recordings lên cloud mặc định. Nên local-first mặc định, cloud backup/sync là opt-in.**
>
> Recording là dữ liệu giọng nói cá nhân, nên cần private-by-default. Tuy app ban đầu là private tool, kiến trúc vẫn nên thiết kế đúng từ đầu.
>
> Quyết định đề xuất:
>
> - **AI/TTS audio:** lưu cloud/object storage + cache local, vì đây không phải giọng cá nhân và giúp tiết kiệm quota.
> - **User recording:** lưu local-first bằng IndexedDB/device storage.
> - **Cloud backup user recording:** chỉ bật khi user opt-in.
> - **Metadata/transcript/score/feedback:** lưu server để tracking tiến bộ.
>
> User phải có quyền:
>
> - nghe lại recording;
> - xóa từng recording;
> - xóa toàn bộ recording history;
> - tắt auto-save recording;
> - bật/tắt cloud backup.
>
> Không dùng recording để train model hoặc chia sẻ với admin/người khác nếu chưa có consent riêng.
>
> Product rule:
>
> **Record privately. Save locally by default. Cloud only with explicit opt-in.**

---

### Q32. Recording lưu bao lâu?

Options:

1. Lưu local cho tới khi user xóa.
2. Auto-delete sau X ngày.
3. Lưu metadata lâu dài, audio có thể xóa.
4. User chọn retention policy.

Trả lời:

> **Nên cho user chọn retention policy, với default an toàn và dễ hiểu.**
>
> Đề xuất:
>
> ### Local recording
>
> - Mặc định lưu cho tới khi user xóa hoặc browser/device tự dọn storage.
> - UI cần nói rõ local storage trên mobile browser không bền vững tuyệt đối.
>
> ### Cloud recording opt-in
>
> - Default: auto-delete sau 90 ngày.
> - Options: 30 ngày / 90 ngày / 180 ngày / giữ cho tới khi tôi xóa.
> - User có thể đổi trong settings.
>
> ### Transcript / score / feedback
>
> - Có thể lưu lâu hơn vì phục vụ progress, review, weekly insight.
> - Nhưng user vẫn phải có quyền xóa theo attempt hoặc xóa toàn bộ data.
>
> ### Khi user xóa
>
> Nên cho chọn:
>
> - xóa audio only;
> - xóa audio + transcript + feedback của attempt;
> - xóa toàn bộ practice history.
>
> Product rule:
>
> **Audio có retention ngắn/tuỳ chọn; metadata học tập có thể giữ lâu hơn nhưng user kiểm soát được.**

---

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

## 8. Vocabulary / Notes / Review

### Q40. Vocabulary nên học độc lập hay luôn gắn với lesson?

Gợi ý:

- Phase đầu nên gắn với lesson.
- Review queue giúp ôn lại.

Trả lời:

> **Phase đầu vocabulary nên gắn chặt với lesson, sau đó được đưa vào personal vocabulary notebook/review queue.**
>
> Không nên làm một module học từ vựng độc lập kiểu app flashcard riêng ngay từ đầu, vì sẽ làm loãng speaking loop. Nhưng vocabulary là phần rất quan trọng để user nói tốt hơn.
>
> Flow đề xuất:
>
> 1. Lesson có 3–7 target words/phrases theo context.
> 2. User gặp từ/cụm từ mới trong câu hỏi, sample answer, transcript hoặc feedback.
> 3. User bấm lưu từ/cụm từ.
> 4. App tạo vocabulary card:
>    - word/phrase;
>    - nghĩa tiếng Việt;
>    - ví dụ theo lesson;
>    - audio/IPA nếu có;
>    - collocation;
>    - memory tip/mnemonic nếu hữu ích.
> 5. Card đi vào Review queue.
> 6. Các lesson sau gợi ý dùng lại phrase đã học.
>
> Vocabulary không nên chỉ là “biết nghĩa”, mà phải chuyển thành active speaking:
>
> - user đã nghe từ đó;
> - shadow từ đó;
> - dùng từ đó trong câu trả lời;
> - review lại sau.
>
> Product rule:
>
> **Vocabulary là lesson memory layer, không phải module rời làm user xa core speaking habit.**

---

### Q41. Ưu tiên phrase hay single word?

Gợi ý:

- Nên ưu tiên phrase/collocation/sentence pattern vì phục vụ speaking/interview tốt hơn.

Trả lời:

> **Nên ưu tiên phrase/chunk/collocation trước single word.**
>
> Vì SpeakFit phục vụ speaking/interview/workplace, user cần “bật ra được cụm dùng thật”, không chỉ biết nghĩa từng từ.
>
> Ví dụ nên học:
>
> - `I was responsible for...` thay vì chỉ học `responsible`.
> - `make a decision` thay vì chỉ học `decision`.
> - `Could you clarify that?` thay vì chỉ học `clarify`.
> - `The main challenge was...` thay vì chỉ học `challenge`.
>
> Single word vẫn cần khi:
>
> - từ đó là keyword ngành nghề;
> - user không biết nghĩa;
> - cần IPA/audio/phát âm;
> - cần word family/root/prefix/suffix để nhớ lâu hơn.
>
> UX nên mặc định lưu phrase, nhưng cho phép tap vào từng từ trong phrase để xem nghĩa/tip riêng.
>
> Product rule:
>
> **Phrase is the speaking unit; word is the explanation layer.**

---

### Q42. Vocab card phase đầu gồm gì?

Gợi ý:

- Word/phrase.
- Nghĩa tiếng Việt.
- Example theo context.
- Lesson source.
- Audio/IPA nếu khả thi.
- Status review đơn giản.

Trả lời:

> **Vocab card phase đầu nên phục vụ mục tiêu “nghe được, hiểu được, nói lại được, dùng lại được”.**
>
> Field tối thiểu:
>
> - phrase/word chính;
> - nghĩa tiếng Việt ngắn;
> - ví dụ theo context lesson;
> - audio pronunciation/TTS;
> - lesson source;
> - tag topic/persona/level;
> - review status: `new / learning / review / mastered`.
>
> Field nên có nếu khả thi:
>
> - IPA hoặc pronunciation hint;
> - collocation;
> - word family;
> - prefix/suffix/root nếu hữu ích;
> - mnemonic/tip dễ nhớ;
> - user note;
> - button `Listen`, `Speak`, `Review later`.
>
> Mobile card không nên nhồi quá nhiều. Layout chính:
>
> 1. Phrase lớn.
> 2. Nghĩa tiếng Việt.
> 3. Audio + Speak.
> 4. Example.
> 5. Review buttons: Again / Hard / Good / Easy.
>
> Các phần nâng cao như IPA, word family, mnemonic, similar phrases nên để trong `More details`.

---

### Q43. Notes tab phase đầu gồm gì?

Gợi ý:

- Sticky Papers.
- Vocabulary Cards.
- Saved phrases.
- Grammar/mistake notes.
- AI chat insights.

Trả lời:

> **Notes tab nên là learning memory hub, nhưng phase đầu phải rất nhẹ.**
>
> Không nên biến Notes thành Notion/Obsidian mini trong MVP. Notes nên gom các artifact phát sinh từ lesson.
>
> Phase đầu Notes gồm:
>
> 1. **Saved phrases / Vocabulary cards**
>    - Từ/cụm từ user lưu từ lesson.
>
> 2. **Sticky notes**
>    - Ghi chú ngắn: phrase hay, lỗi cần nhớ, tip quan trọng.
>
> 3. **Correction notes**
>    - Your sentence → Better sentence → giải thích tiếng Việt.
>
> 4. **Grammar/mistake notes**
>    - Lỗi lặp lại, ví dụ: thiếu `s`, sai tense, dùng word chưa tự nhiên.
>
> 5. **AI chat insights**
>    - Những giải thích user lưu từ chatbox trong lesson.
>
> UX nên hỗ trợ quick note/template hơn là bắt user gõ dài:
>
> - `Useful`
> - `Difficult`
> - `Use at work`
> - `Interview phrase`
> - `Need review`
>
> Product rule:
>
> **Notes không phải nơi ghi chép lan man; Notes là nơi lưu thứ giúp user nói tốt hơn ở lần sau.**

---

### Q44. Review queue phase đầu nên ôn gì?

Gợi ý:

- Vocabulary cards.
- Weak phrases.
- Sticky notes quan trọng.
- Speaking mistakes.
- Lesson insights.

Trả lời:

> **Review queue nên ưu tiên những thứ giúp user dùng lại được khi nói, không chỉ nhận diện nghĩa.**
>
> Thứ tự ưu tiên:
>
> 1. **Weak phrases**
>    - Phrase đã học nhưng user chưa dùng được khi speaking.
>
> 2. **Speaking mistakes / correction notes**
>    - Lỗi user vừa mắc hoặc lặp lại nhiều lần.
>
> 3. **Due vocabulary cards**
>    - Từ/cụm từ đến hạn ôn theo spaced repetition.
>
> 4. **Saved phrases từ lesson gần đây**
>    - Phrase liên quan đến current goal/profile.
>
> 5. **Sticky notes quan trọng**
>    - Tips, grammar note, pronunciation reminder.
>
> Review modes phase đầu:
>
> - Nhìn tiếng Việt → nói tiếng Anh.
> - Nghe audio → nhớ nghĩa/context.
> - Điền phrase vào câu.
> - Shadow phrase/chunk.
> - Nói lại corrected sentence.
>
> Không nên làm review queue quá học thuật. Nên gọi là:
>
> - `5-minute speaking review`
> - `Practice boost`
> - `Review phrases for today`
>
> Product rule:
>
> **Review queue là cầu nối giữa lesson hôm qua và speaking hôm nay.**

---

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

## 11. Technical Architecture

### Q56. Stack chính là gì?

Options:

1. Next.js + Supabase.
2. React/Vite + Supabase.
3. Next.js + Firebase.
4. Khác.

Gợi ý từ brief:

- Next.js/React + Tailwind + shadcn/ui.
- Supabase hoặc Firebase.
- User muốn học và làm chủ backend, nên ưu tiên tự handle các chức năng BE thay vì phụ thuộc Supabase.

Trả lời:

> **Khuyến nghị MVP mới: Next.js + TypeScript + Tailwind + shadcn/ui + custom Bun backend + PostgreSQL + Drizzle + S3/R2 storage.**
>
> Đây là lựa chọn phù hợp hơn nếu mục tiêu không chỉ là build app nhanh, mà còn là **học và làm chủ backend engineering**.
>
> Lý do:
>
> - Next.js vẫn phù hợp cho frontend web app/PWA, routing, UI, deploy nhanh.
> - Custom Bun backend giúp tự thiết kế API, auth, database schema, business logic, quota, jobs, storage flow.
> - PostgreSQL phù hợp hơn SQLite cho MVP cloud multi-user vì cần user data, lessons, attempts, feedback, vocab, review, usage tracking, billing/quota sau này.
> - Drizzle giúp học SQL/schema rõ ràng hơn, ít magic hơn ORM nặng.
> - S3-compatible storage hoặc Cloudflare R2 phù hợp cho audio files, TTS cache, user recordings nếu user opt-in cloud backup.
> - Stack này giúp hiểu thật các bài toán production: auth/session, migration, indexing, background jobs, file upload, signed URL, privacy/delete/export data.
>
> Stack đề xuất:
>
> - Frontend/PWA: Next.js + TypeScript.
> - UI: Tailwind CSS + shadcn/ui.
> - Backend API: Bun + Hono hoặc Elysia.
> - Database: PostgreSQL.
> - ORM/query builder: Drizzle.
> - Auth: Better Auth hoặc tự build email/password/session tối giản; Google OAuth có thể thêm sau.
> - Storage: Cloudflare R2 hoặc S3-compatible storage.
> - AI: MiniMax cho text/TTS/feedback; STT provider validate riêng.
> - Background jobs: queue table MVP, sau đó nâng cấp BullMQ/Trigger.dev/Inngest nếu cần.
> - Deploy frontend: Vercel.
> - Deploy backend: Fly.io / Render / Railway.
>
> Không nên chọn SQLite thuần cho MVP cloud nếu có nhiều user thật, audio metadata, review queue, progress, quota và sync. Nếu rất muốn SQLite-style để học, có thể cân nhắc Turso/libSQL, nhưng PostgreSQL vẫn là lựa chọn an toàn hơn.
>
> Trade-off:
>
> - Supabase nhanh hơn cho MVP.
> - Custom backend học được nhiều hơn và kiểm soát tốt hơn.
> - Với mục tiêu cá nhân là làm chủ BE, custom backend là lựa chọn đúng, miễn là scope MVP được giữ nhỏ.
>
> Product rule:
>
> **Chọn custom backend để học và kiểm soát hệ thống, nhưng đừng để backend scope làm chậm validation core learning loop.**

---

### Q57. Có cần auth ngay từ đầu không?

Thông tin hiện tại:

- Có vẻ nên có ngay vì cần profile, history, progress, notes, metadata.
- Ưu tiên Google login.
- Vì stack chuyển sang custom backend, auth sẽ do backend tự quản lý thay vì Supabase Auth.

Trả lời:

> **Có, nên có auth ngay từ MVP. Phase đầu nên dùng Google Login là chính để giảm friction đăng ký.**
>
> Lý do:
>
> - Cần learning profile.
> - Cần lesson history/progress.
> - Cần saved phrases/vocab/notes.
> - Cần attempts/transcripts/feedback gắn với user.
> - Cần usage tracking/quota MiniMax.
> - Cần privacy controls và delete/export data.
>
> Auth MVP nên đơn giản:
>
> - Google OAuth là cách đăng nhập chính.
> - Không cần email/password trong phase đầu nếu muốn giảm scope.
> - Không cần magic link nếu Google Login đã đủ cho user test.
> - Backend tự tạo internal user record sau khi Google OAuth thành công.
> - Role tối thiểu: user/admin.
>
> Backend auth flow đề xuất:
>
> 1. User bấm `Continue with Google`.
> 2. Google trả OAuth callback về backend.
> 3. Backend verify Google profile/email.
> 4. Backend tạo hoặc tìm user trong PostgreSQL.
> 5. Backend tạo session cookie HTTP-only, secure, sameSite.
> 6. Frontend gọi `/me` để lấy profile hiện tại.
>
> Nên lưu trong DB:
>
> - `users`: internal user id, email, display name, avatar, status.
> - `oauth_accounts`: provider, provider user id, linked user id.
> - `sessions`: session token hash, user id, expires at, revoked at.
> - `user_roles`: user/admin nếu cần.
>
> Có thể dùng Better Auth để giảm rủi ro tự build sai OAuth/session. Nếu mục tiêu học BE sâu hơn, vẫn có thể tự implement nhưng phải giữ scope tối giản và cẩn thận phần security.
>
> Admin/support access phải có audit nếu sau này có.
>
> Product rule:
>
> **Use Google Login for low-friction onboarding, but keep user/session ownership inside the custom backend.**

---

### Q58. Audio lưu ở đâu?

Quyết định tạm thời:

- TTS audio: cloud/object storage source of truth + local cache.
- User recording: local-first bằng IndexedDB.
- Cloud backup/sync: opt-in.
- Metadata/score/transcript: custom backend PostgreSQL.

Trả lời:

> **Không lưu audio trong database. Dùng object storage + local cache, DB chỉ lưu metadata.**
>
> Với stack custom BE, backend Bun sẽ chịu trách nhiệm tạo signed URL, kiểm tra quyền truy cập, ghi metadata và xử lý lifecycle/delete.
>
> Thiết kế đề xuất:
>
> ### TTS / AI-generated audio
>
> - Source of truth: Cloudflare R2 hoặc S3-compatible object storage.
> - Client cache: Cache Storage/Service Worker.
> - Dedup bằng hash: normalized text + voice + speed + model + version.
> - Backend tạo/generate TTS, upload lên R2/S3, lưu metadata vào PostgreSQL.
>
> ### User recording
>
> - Local-first bằng IndexedDB/device storage.
> - Cloud backup opt-in vào private bucket.
> - Truy cập cloud bằng signed URL ngắn hạn do backend cấp.
> - Không public URL.
> - User có quyền xóa recording local/cloud.
>
> ### DB metadata
>
> Lưu:
> - storageKey/audioPath;
> - provider/bucket;
> - duration;
> - size;
> - mimeType;
> - lessonId/attemptId;
> - transcriptId;
> - ownerUserId;
> - retention policy;
> - delete status;
> - createdAt.
>
> Security:
>
> - private bucket;
> - signed URLs;
> - backend authorization trước khi cấp URL;
> - encryption at rest/in transit;
> - lifecycle auto-delete nếu cần;
> - không expose object key đoán được.
>
> Product rule:
>
> **Audio files live in R2/S3; learning memory lives in PostgreSQL; access is controlled by the custom backend.**

---

### Q59. Có cần queue/background jobs không?

Gợi ý:

- Có thể cần cho TTS generation, AI generation, weekly insight.
- MVP có thể đơn giản trước, nhưng architecture nên chuẩn bị.
- Với custom Bun backend, có thể bắt đầu bằng queue table + worker riêng.

Trả lời:

> **Có, nên chuẩn bị background job architecture từ đầu, dù MVP có thể triển khai đơn giản bằng PostgreSQL queue table + Bun worker.**
>
> Không nên xử lý STT/TTS/AI feedback dài trực tiếp trong request vì dễ timeout và UX kém.
>
> Jobs cần có:
>
> - generate lesson;
> - generate TTS;
> - upload/process audio;
> - transcribe audio;
> - generate feedback;
> - update usage quota;
> - generate weekly insight sau này;
> - cleanup/retention auto-delete.
>
> MVP options theo custom BE:
>
> - Đơn giản nhất: `jobs` table trong PostgreSQL + Bun worker poll theo interval.
> - Tốt hơn: worker process riêng deploy cùng backend.
> - Sau này: BullMQ + Redis / SQS / Trigger.dev nếu job volume tăng.
>
> Job cần:
>
> - type;
> - payload JSON;
> - status: queued/processing/completed/failed;
> - retry count/retry limit;
> - idempotency key;
> - priority nếu cần;
> - lockedBy/lockedUntil để tránh 2 worker xử lý cùng job;
> - error logging;
> - không log raw sensitive data bừa bãi.
>
> Product rule:
>
> **Start with a simple backend-owned queue, but make AI/audio work async, retryable, observable, and quota-aware.**

---

### Q60. Có cần usage tracking/quota không?

Thông tin hiện tại:

- Có. Dù private/free, vẫn cần tracking MiniMax text/TTS/chat/feedback để tránh vượt quota.

Trả lời:

> **Có, bắt buộc cần usage tracking/quota ngay từ MVP nếu dùng AI/TTS/STT.**
>
> Lý do:
>
> - MiniMax Speech quota giới hạn theo chars/day.
> - AI feedback/STT/TTS đều có cost/quota.
> - Cần tránh regenerate audio trùng.
> - Sau này dễ thêm paid plan/subscription.
>
> Nên track:
>
> - lesson generation calls;
> - TTS characters;
> - TTS audio generated/reused;
> - STT audio minutes;
> - AI feedback calls;
> - chatbox calls;
> - token/request count;
> - cost estimate;
> - errors/retries.
>
> Bảng/event gợi ý:
>
> - `usage_events`;
> - `user_quotas`;
> - `ai_provider_calls`;
> - `tts_assets`;
> - `deduplication_records`.
>
> MVP quota có thể mềm:
>
> - daily lesson generation limit;
> - daily TTS char limit;
> - daily feedback attempts;
> - admin/test user override.
>
> Product rule:
>
> **Track usage before monetization, otherwise AI/audio cost will be invisible until it hurts.**

---

### Q61. Có cần content versioning không?

Thông tin hiện tại:

- Có, nhất là lesson/audio regenerate.
- Nếu user đã học version cũ, recording/note/feedback phải gắn đúng version.

Trả lời:

> **Có, cần content versioning ngay từ MVP, nhưng làm đơn giản.**
>
> Lý do:
>
> - AI-generated lesson có thể regenerate.
> - User có thể đã học/record/note trên version cũ.
> - TTS audio cache phụ thuộc text/voice/speed/model/version.
> - Không được sửa đè lesson đã publish nếu đã có attempts.
>
> MVP versioning tối thiểu:
>
> - `lesson_id`
> - `version_id` hoặc `version_number`
> - `status`: draft / approved / published / archived
> - `created_by`: ai / admin
> - `prompt_version`
> - `model/provider`
> - `created_at`
> - `change_reason`
>
> Rule:
>
> - Không sửa trực tiếp bản đã publish.
> - Regenerate/chỉnh tay → tạo draft version mới.
> - User đang học version nào thì attempts/notes/recordings gắn với version đó.
> - User mới hoặc lesson chưa bắt đầu có thể nhận version mới.
>
> Product rule:
>
> **Version enough to protect learner history; don’t build a full Git-like CMS yet.**

---

## 12. Admin / Content Ops

### Q62. Phase đầu có cần Admin CMS không?

Gợi ý:

- Không cần dashboard phức tạp.
- Prompt/config/templates có thể để trong code/internal tool.
- Với custom backend, admin nên là internal route/page đơn giản dùng cùng DB/API.

Trả lời:

> **Phase đầu chỉ cần Admin/content tool tối giản, không cần full CMS.**
>
> MVP admin cần:
>
> - xem danh sách lessons;
> - xem lesson theo version;
> - edit text thủ công;
> - regenerate từng block;
> - approve/reject/publish;
> - ghi chú lỗi content;
> - xem prompt/model/version cơ bản;
> - xem job trạng thái lỗi cơ bản;
> - xem usage/quota theo user để debug cost.
>
> Không cần trong MVP:
>
> - drag-drop lesson builder;
> - role/workflow nhiều cấp;
> - analytics dashboard lớn;
> - campaign/content calendar;
> - A/B testing phức tạp;
> - enterprise CMS.
>
> Cách làm phù hợp custom BE:
>
> - Tạo `/admin` trong Next.js, chỉ user role `admin` truy cập được.
> - Admin page gọi custom backend API.
> - Backend kiểm tra session + role trước mọi admin action.
> - Prompt/config/templates có thể để trong code hoặc DB table đơn giản.
> - Mọi action publish/regenerate/delete cần audit log tối thiểu.
>
> Content ops loop cần chạy được:
>
> **AI draft → human review → edit/regenerate → publish → collect feedback.**

---

### Q63. Có cần regenerate từng phần lesson không?

Gợi ý:

- Có ích nhưng có thể sau MVP.
- Nếu làm, cần versioning.

Trả lời:

> **Có, nên hỗ trợ regenerate từng phần/block thay vì chỉ regenerate toàn bài.**
>
> Lý do:
>
> - Giảm rủi ro AI phá phần đang tốt.
> - Tiết kiệm cost.
> - Dễ review.
> - Dễ cải thiện prompt theo block.
>
> Lesson nên chia block:
>
> - objective/context;
> - main prompt/question;
> - vocabulary/phrases;
> - sample answer;
> - shadowing script;
> - grammar/tip;
> - speaking practice;
> - quiz/review;
> - feedback rubric.
>
> Regenerate flow:
>
> 1. Admin chọn block.
> 2. Chọn lý do: too hard, too easy, unnatural, wrong level, duplicate, not useful.
> 3. AI tạo alternative.
> 4. Admin chọn/save as draft.
> 5. Approve/publish version mới.
>
> Mỗi regenerate cần log prompt input/output, model, reason, admin decision.
>
> Product rule:
>
> **Regenerate the broken block, not the whole lesson by default.**

---

### Q64. Có cần review/approve AI content trước khi user học không?

Options:

1. Không, private app nên generate trực tiếp.
2. Có schema validation + quality check tự động.
3. Có manual review cho content published/shared.

Trả lời:

> **MVP nên có schema validation + quality check tự động; content published/shared nên có human approval.**
>
> Vì app ban đầu private/small group, có thể cho AI generate trực tiếp một số lesson cá nhân hóa. Nhưng vẫn cần guardrails.
>
> Tầng kiểm tra đề xuất:
>
> 1. **Schema validation**
>    - Đúng format block.
>    - Có required fields.
>
> 2. **Automatic quality check**
>    - đúng level;
>    - không quá dài;
>    - không duplicate;
>    - đúng persona/goal;
>    - không nội dung nhạy cảm;
>    - grammar/câu mẫu ổn.
>
> 3. **Human review**
>    - Với content seed/published/shared.
>    - Với lesson template quan trọng.
>    - Với nội dung dùng cho nhiều user.
>
> Status đề xuất:
>
> - ai_generated;
> - ai_checked;
> - needs_review;
> - approved;
> - published;
> - rejected.
>
> Không nên auto-publish AI content hàng loạt cho public users khi chưa có validation.
>
> Product rule:
>
> **Personal AI lessons can be fast; reusable/published content must be reviewed.**

---

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

## 14. Future Backlog đã ghi nhận

Các feature này có giá trị nhưng chưa nên đưa vào MVP nếu chưa chốt lại:

- YouTube shadowing.
- Text-to-video / roleplay video.
- Obsidian export/sync.
- Weekly insights nâng cao.
- Advanced pronunciation scoring.
- Word-level pronunciation highlight.
- Semantic search notes.
- Multi-profile/family mode đầy đủ.
- Admin CMS đầy đủ.
- Payment/subscription.
- Community/cohort.
- Mock interview realtime.
- Crash course 1/3/7/14 ngày.
- Visual vocabulary cards bằng AI image.
- Leaderboard/partner challenge.

---

## 15. BMAD / Planning Readiness Checklist

Trước khi tạo PRD/BMAD artifacts, nên trả lời tối thiểu các câu sau:

- Q1: Tên tạm thời.
- Q2: Định vị chính.
- Q9: Persona phase đầu.
- Q10: Level đầu vào.
- Q13: MVP 4 tuần.
- Q15: Những thứ không làm trong MVP.
- Q18: Core loop.
- Q22: Lộ trình mặc định.
- Q33: MiniMax dùng cho gì.
- Q34: STT có bắt buộc không.
- Q56: Stack chính.
- Q57: Auth có ngay không.
- Q60: Usage tracking/quota.
- Q65: Có test thủ công trước không.

Sau đó có thể tạo:

1. `PRD.md`
2. `MVP_SCOPE.md`
3. `ARCHITECTURE.md`
4. `EPICS.md`
5. `ROADMAP.md`
