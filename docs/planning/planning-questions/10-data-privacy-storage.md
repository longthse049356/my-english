---
doc_type: planning-shard
stage: discovery
load_policy: on_explicit_request
size_warning: normal
source_file: PLANNING_QUESTIONS.md
source_section: "§10 Data / Privacy / Storage"
summary: "Data handling, privacy policies, storage decisions, and retention rules."
---

**Related:** [PLANNING_QUESTIONS.md](../../PLANNING_QUESTIONS.md) | [Product Brief](../../_bmad-output/planning-artifacts/product-brief.md)

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
