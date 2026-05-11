---
doc_type: planning-shard
stage: discovery
load_policy: on_explicit_request
size_warning: large
source_file: PLANNING_QUESTIONS.md
source_section: "§11 Technical Architecture"
summary: "Tech stack, architecture patterns, and implementation decisions."
---

**Related:** [PLANNING_QUESTIONS.md](../../PLANNING_QUESTIONS.md) | [Product Brief](../../_bmad-output/planning-artifacts/product-brief.md)

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
