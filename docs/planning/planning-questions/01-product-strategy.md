---
doc_type: planning-shard
stage: discovery
load_policy: on_explicit_request
size_warning: normal
source_file: PLANNING_QUESTIONS.md
source_section: "§1 Product Strategy"
summary: "Product naming, positioning, differentiation, success metrics, and strategic decisions."
---

**Related:** [PLANNING_QUESTIONS.md](../../PLANNING_QUESTIONS.md) | [Product Brief](../../_bmad-output/planning-artifacts/product-brief.md)

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
