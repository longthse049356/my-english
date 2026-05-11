---
doc_type: idea-brief-shard
stage: discovery
load_policy: on_explicit_request
size_warning: large
source_file: IDEA_BRIEF.md
source_section: "§12 Câu hỏi mở"
summary: "Unresolved questions and areas needing exploration."
---

**Related:** [IDEA_BRIEF.md](../../IDEA_BRIEF.md) | [Product Brief](../../_bmad-output/planning-artifacts/product-brief.md)

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
