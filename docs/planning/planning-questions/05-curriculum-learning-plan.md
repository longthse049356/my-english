---
doc_type: planning-shard
stage: discovery
load_policy: on_explicit_request
size_warning: normal
source_file: PLANNING_QUESTIONS.md
source_section: "§5 Curriculum / Learning Plan"
summary: "Learning curriculum structure, content organization, and progression design."
---

**Related:** [PLANNING_QUESTIONS.md](../../PLANNING_QUESTIONS.md) | [Product Brief](../../_bmad-output/planning-artifacts/product-brief.md)

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
