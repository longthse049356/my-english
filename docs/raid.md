# RAID Log

Theo dõi **Risks, Assumptions, Issues, Dependencies** cho SpeakFit English. Đây là log vận hành của Solo PM; cập nhật khi có rủi ro mới, giả định cần kiểm chứng, issue đang chặn, hoặc dependency quan trọng.

| ID | Loại | Mô tả | Owner | Ưu tiên | Mitigation / Next Step | Trạng thái | Cập nhật lần cuối |
|---|---|---|---|---|---|---|---|
| RAID-001 | Risk | AI agents có thể gây scope creep bằng cách đề xuất feature nằm ngoài MVP daily voice coaching loop. | Solo PM | High | Dùng `skeptic` review cho đề xuất feature mới; tách backlog ngoài MVP riêng. | Open | 2026-05-04 |
| RAID-002 | Risk | Artifact do AI sinh ra có thể drift khỏi `IDEA_BRIEF.md` hoặc BMAD artifacts đã được duyệt. | Solo PM | High | Bắt buộc dùng AI Work Order và AI Artifact Contract; review ở phase gates. | Open | 2026-05-04 |
| RAID-003 | Assumption | MVP có thể validate value bằng daily speaking/shadowing loop trước khi làm payment/community/full CMS. | Solo PM | Medium | Kiểm chứng qua PRD success metrics và early usage tests. | Monitoring | 2026-05-04 |
| RAID-004 | Risk | Quiet Gift / quote-card motivation layer có thể làm scope drift sang gamification/content app nếu collection, video, tower hoặc unlock mechanics lấn át speaking loop. | Solo PM | Medium | MVP chỉ cho phép quote/coach note sau meaningful lesson completion; quote save optional; no tower/map, reward economy, hidden core features, mandatory video. Validate reward supports return behavior without lowering retry/reuse rates. | Open | 2026-05-07 |

## Related

- [[decisions|Decision Log]] — quyết định liên quan đến RAID entries.
- [[product-brief|Product Brief]] — open questions feeding RAID.
- [[prd|PRD]] — risks chính thức trong NFR/scope.
- [[ux-design-specification|UX Design Specification]] — RAID-004 Quiet Gift drift.
- [[architecture|Architecture]] — risks về STT/TTS provider, cost.
- [[BMAD_SPEAKFIT_WORKFLOW|BMAD SpeakFit Workflow]] — vai trò RAID trong sprint cadence.
- [[docs/INDEX|Repo Index]].
