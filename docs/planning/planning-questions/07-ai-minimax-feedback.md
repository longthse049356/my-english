---
doc_type: planning-shard
stage: discovery
load_policy: on_explicit_request
size_warning: normal
source_file: PLANNING_QUESTIONS.md
source_section: "§7 AI / MiniMax / Feedback"
summary: "AI feedback generation, rubric design, and coaching tone decisions."
---

**Related:** [PLANNING_QUESTIONS.md](../../PLANNING_QUESTIONS.md) | [Product Brief](../../_bmad-output/planning-artifacts/product-brief.md)

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
