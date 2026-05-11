---
doc_type: planning-shard
stage: discovery
load_policy: on_explicit_request
size_warning: large
source_file: PLANNING_QUESTIONS.md
source_section: "§3 MVP Boundary"
summary: "MVP scope definition, feature inclusion/exclusion decisions, and phase boundaries."
---

**Related:** [PLANNING_QUESTIONS.md](../../PLANNING_QUESTIONS.md) | [Product Brief](../../_bmad-output/planning-artifacts/product-brief.md)

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
