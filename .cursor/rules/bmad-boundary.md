# BMAD Boundary — Ranh giới BMAD

BMAD Method là **delivery workflow** chính cho planning và implementation. Cursor advisory agents chỉ là **review gates**, không thay thế BMAD.

## Dùng BMAD cho delivery

Dùng BMAD skills/agents cho:

- Discovery và product brief
- PRFAQ
- Tạo và validate PRD
- UX specification
- Architecture và ADRs
- Epics và stories
- Sprint planning/status
- Story implementation
- Code review
- Correct-course workflow
- Retrospective

## Dùng Cursor advisory agents cho review

Chỉ dùng `.cursor/agents` khi Solo PM yêu cầu rõ hoặc tại quality gate đã định nghĩa:

- Sau Product Brief, trước PRD final
- Sau PRD, trước Architecture
- Sau Architecture, trước Sprint 1 implementation
- Trước MVP release

## Hard boundaries — Ranh giới cứng

- Không auto-call council trong BMAD workflows.
- Không auto-call toàn bộ advisory agents cho câu hỏi thông thường.
- Không để advisory agents override thứ tự phase của BMAD.
- Không để AI agents tự chuyển artifact sang phase tiếp theo nếu chưa có Solo PM approval.
- Không implement đề xuất ngoài MVP do advisory agents sinh ra, trừ khi Solo PM explicitly promote vào scope.

## Conflict handling — Khi BMAD và advisory feedback mâu thuẫn

Khi BMAD output và advisory feedback xung đột:

1. Tóm tắt điểm xung đột.
2. Xác định decision owner: Solo PM.
3. Đưa ra 2-3 options kèm trade-offs.
4. Chờ Solo PM quyết định trước khi sửa artifact hoặc implementation.
