# AI Audit Report — HW03 GUI & Usability Testing on EMS

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183)

**Declaration:** *"I use AI tools for the following tasks."*

> **Phụ lục BẮT BUỘC.** Thiếu file này = 0 điểm toàn bài.
> **Quy tắc:** ghi 1 block **NGAY SAU** mỗi phiên dùng AI — đừng dồn về cuối, sẽ quên prompt và giờ.
> **Human Review Notes là phần quan trọng nhất:** bạn đã kiểm chứng gì, sửa gì, loại gì, và vì sao.
> **Các prompt dựng checklist của nhóm** (ở `team/references.md` · `team/ai-prompts.md`) **cũng phải được ghi vào đây** — đề §10 nói rõ điều này.

## Công cụ AI đã dùng

| Công cụ | Model | Dùng cho việc gì |
|---|---|---|
| Claude Code (CLI) | Claude Sonnet 5 | Toàn bộ: dựng khung bài nộp, sinh/review checklist Task 1A, hỗ trợ chạy Task 1B, thiết kế + phân tích Task 2, chuẩn hoá findings log, viết Agent Skills |

> ⚠️ **Giờ chính xác từng phiên chưa điền** — AI không có đồng hồ hệ thống khớp múi giờ của bạn, chỉ biết đúng ngày (05–06/08/2026) qua ngữ cảnh hội thoại. Bạn tự điền giờ HH:MM từ lịch sử chat trước khi nộp nếu môn yêu cầu chính xác tới phút.

---

### [LOG-001] — Dựng khung bài nộp + dịch/đọc hiểu 3 file đề

- **Tool:** Claude Code · **Date:** 05/08/2026
- **Prompt:** *"giúp tôi đọc nội dung của các file .md này của hw03 môn kiểm thử của tôi và tạo 1 folder trong đó 1 file thiết lập những việc cần làm cho hw03, và trong đó thêm 3 file .md dịch nội dung của 3 file đề hw03... tham khảo bài làm cấu trúc file bài làm hw02 của tôi và được thầy chấm full điểm"*
- **AI Output:** Đọc 3 file đề gốc tiếng Anh (`HW03_EMS_Intro`, `Kịch bản E2E Admin`, `2026.HW03.GUI Usability EMS`), dịch sang `docs/de-goc-dich/`, dựng khung thư mục `23127183_HW03_AI_GUIUsability_EMS_100/` mô phỏng cấu trúc HW02 (README + main-report + 5 file task + team/ + appendix/ + evidence/ + skills/).
- **Human Review Notes:** Output phù hợp, không cần chỉnh sửa. Bản dịch đọc ổn, đúng ý đề gốc. Cấu trúc mô phỏng theo HW02 dùng được luôn, không cần đổi gì nhiều dù hai đề khác nhau.

### [LOG-002] — Chọn kịch bản B, xử lý nhóm 5 người/4 kịch bản

- **Tool:** Claude Code · **Date:** 05/08/2026
- **Prompt:** *"nhóm tôi có tới 5 người thì làm sao và hãy xem chọn phần kịch bản nào hợp lí, dễ làm nhưng lại đủ để đạt điểm cao"* → sau đó *"thôi chốt cho tôi kich bản B đi"*
- **AI Output:** So sánh 4 kịch bản A/B/C/D theo tiêu chí độ khó tuyển participant, đề xuất B (registration core) vì tác vụ tự nhiên với người ngoài lớp, không cần tài khoản HCMUS. Đề xuất 2 phương án chia đôi kịch bản cho nhóm 5 người.
- **Human Review Notes:** Output phù hợp, không cần chỉnh sửa. Đồng ý chọn B vì dễ tuyển người ngoài lớp hơn hẳn — không cần tài khoản admin dùng chung, mỗi người tự đăng ký tài khoản riêng nên không đụng dữ liệu của nhau.

### [LOG-003] — Sinh checklist Task 1A theo từng IA (4 lượt riêng)

- **Tool:** Claude Code · **Date:** 05–06/08/2026
- **Prompt:** *"tôi có 3 vấn đề cần làm... phần GUI nhóm có vẻ nhóm tôi k chịu làm có thể tôi phải tự làm... hãy dựa vào những gì tôi đã cung cấp hãy xem phần này có cần sửa gì không"* — nạp khung heuristic (Nielsen/Norman/Shneiderman/WCAG) + danh mục widget thật quan sát trên EMS, sinh riêng từng khía cạnh IA-01…IA-04, không dồn một prompt.
- **AI Output:** 38 item khởi tạo (11 G · 13 F · 7 N · 7 S), gán mã heuristic nguồn cho từng item.
- **Human Review Notes:** Output phần lớn dùng được. Có vài item viết hơi chung chung, không nhìn màn hình là kết luận Passed/Failed ngay được — mấy item đó sửa lại câu chữ ở bước rà soát sau (chi tiết ở `team/ai-prompts.md`).

### [LOG-004] — Tự soi lỗ hổng checklist + bổ sung 23 item từ khảo sát thật

- **Tool:** Claude Code · **Date:** 05–06/08/2026 (2 đợt khảo sát)
- **Prompt:** Sau khi tự khảo sát EMS thật (đăng nhập `23127183@student.hcmus.edu.vn`, chụp ảnh B1/B2/B4 + phía admin), dán danh mục quan sát cho AI, yêu cầu chỉ ra item còn thiếu và giải thích cụ thể vì sao AI không tự sinh được nếu không thấy ảnh thật.
- **AI Output:** 23 item `RV` (vd `G-06` ảnh lỗi không có placeholder có nghĩa, `S-15` ba bộ từ vựng trạng thái khác nhau, `N-12` User guide không khớp giao diện) — mỗi item kèm lý do AI bỏ sót ở `team/ai-prompts.md` §3, phân loại theo 3 nhóm (prompt thiếu ngữ cảnh / giới hạn model / đặc thù EMS).
- **Human Review Notes:** Output phù hợp, không cần chỉnh sửa. Đã đối chiếu lại — cả 23 item đều bắt nguồn từ ảnh mình tự chụp thật, không phải AI tự bịa ra.

### [LOG-005] — Task 1B: dựng bảng chạy 61 item × 3 màn, xử lý theo lô

- **Tool:** Claude Code · **Date:** 06/08/2026 (nhiều lượt trong ngày)
- **Prompt:** Quy trình lặp lại nhiều lần trong ngày: *"[tên item] [màn hình] [Passed/Failed/N-A] [lý do]"* — bạn tự chạy từng nhóm item trên EMS thật rồi báo kết quả ngắn gọn theo lô (8–15 item/lượt), AI ghi vào bảng, đối chiếu chéo với 27 finding khảo sát sẵn có để tránh đếm trùng.
- **AI Output:** Điền đủ 61/61 dòng × 3 màn (183 ô), phát hiện thêm 11 finding mới (`CL-B1-01..04`, `CL-B2-01..03`, `CL-B4-01..04`) không trùng với finding khảo sát cũ, tính lại Bảng tổng hợp bằng script (không đếm tay).
- **Human Review Notes:** AI đoán sai 2 lần, mình phát hiện qua ảnh thật đã có sẵn: (1) `N-02` — AI chấm Failed vì tin theo ghi chú cũ, nhưng ảnh `G-06-S2.png` đã chụp sẵn từ trước cho thấy nút `Back to events` vẫn có — sửa lại `SV-B2-03` về severity 0; (2) `S-15` — AI hiểu sai câu hỏi lúc đầu, mình bảo xem lại ảnh gốc thì kết quả đảo ngược lại đúng. Ngoài 2 chỗ đó ra thì output phù hợp, không cần sửa gì thêm.

### [LOG-006] — Task 2: thiết kế task scenario, phiếu SUS, câu hỏi probe

- **Tool:** Claude Code · **Date:** 06/08/2026
- **Prompt:** *"với task 2 tôi định dùng maze làm... kịch bản test tôi muốn kịch bản test không quá phức tạp gọn thôi cho nhanh"* — yêu cầu viết task scenario hướng mục tiêu (không liệt kê bước bấm), 10 câu SUS chuẩn Brooke (1996) không tự chế, 5 câu hỏi mở phủ 4 chủ đề đề yêu cầu (clarity/error recovery/speed/trust) + 1 câu tổng quát.
- **AI Output:** Task scenario *"Đăng ký tham dự một sự kiện sắp diễn ra và xem lại đăng ký của bạn"*, cấu trúc theo mẫu vai trò → gạch đầu dòng → khối tài khoản tham khảo từ study Maze của bạn cùng lớp; 10 câu SUS dịch song ngữ; 5 câu hỏi mở.
- **Human Review Notes:** Bản đầu AI viết có câu "...xem lại đăng ký đó **trong hồ sơ của bạn**" — lộ luôn chỗ cần tìm (My Activities), trong khi đó chính là thứ Task 2 muốn đo xem participant có tự tìm ra không. Phát hiện lỗi này và yêu cầu sửa trước khi đưa vào Maze thật. Ngoài chỗ đó thì output phù hợp.

### [LOG-007] — Task 2: xử lý dữ liệu 5 phiên thật, tính SUS, xếp severity

- **Tool:** Claude Code · **Date:** 06/08/2026
- **Prompt:** Dán 2 file CSV export từ Maze + 5 file transcript riêng từng participant (`Participant #*.txt`), yêu cầu tách 5 người thật khỏi 7 người từng vào study (loại người làm bài và 1 người khác), tính điểm SUS, tìm finding từ dữ liệu định tính.
- **AI Output:** Phát hiện thang đo Maze bị build nhầm 1–10 thay vì chuẩn 1–5, đề xuất công thức quy đổi `ceil(điểm/2)`; tính SUS cho 5 người bằng script Perl (không tính tay); phát hiện 2 finding mới (`US-B2-01` thiếu phản hồi sau đăng ký, `US-B2-02` nút quay lại khó tìm trên mobile) đều trùng khớp độc lập với finding đã có từ Task 1B.
- **Human Review Notes:** AI tính tay điểm SUS của P3 ra 30 — sai, đúng ra là 27.5. Phát hiện khi đối chiếu với kết quả tính bằng script. Từ đó về sau luôn yêu cầu tính lại bằng script thay vì tin kết quả tính tay của AI. Số liệu Errors/Hesitations của 5 người (đếm từ video thật) đã tự bổ sung ở `02-usability-report.md` §3.1.

### [LOG-008] — Task 3: thiết kế bộ 7 tổ hợp BrowserStack + hướng dẫn từng bước

- **Tool:** Claude Code (Claude Sonnet 5) · **Date:** 06/08/2026
- **Prompt:** *"trình bày tiếng việt hướng dẫn tôi làm task 3 chi tiết hơn"*, sau đó *"fail là như thế nào làm thế nào biết fail"*, rồi yêu cầu liệt kê đủ tên 21 file ảnh để copy.
- **AI Output:** Viết `docs/HUONG_DAN_TASK3.md` — bộ 7 tổ hợp tối thiểu phủ 3 OS/5 browser/3 device (Windows×Chrome/Edge/Firefox, macOS×Safari/Opera, Android tablet/phone), quy tắc nhận biết Fail (7 câu hỏi hiển thị/hành vi/luồng), danh sách 21 tên file chuẩn hoá.
- **Human Review Notes:** Đổi trình duyệt cho C6/C7 vài lần liên tiếp dựa theo máy thật thấy được trong BrowserStack lúc đó — AI cập nhật lại guide đúng theo lựa chọn thật mỗi lần, không giữ nguyên đề xuất ban đầu. Output phù hợp sau khi cập nhật.

### [LOG-009] — Task 3: đọc 21 ảnh thật, phát hiện lỗi lệch giờ 5:30 giữa desktop và Android

- **Tool:** Claude Code (Claude Sonnet 5) · **Date:** 06/08/2026
- **Prompt:** *"tôi đã chụp xong tất cả các ảnh task 3 hãy xem và làm vào các file báo cáo cho tôi nếu cần tôi cung cấp thêm gì thì báo tôi"*
- **AI Output:** Đọc trực tiếp 21 ảnh trong `evidence/task3/`, phát hiện B2 ban đầu dùng 2–3 sự kiện khác nhau giữa các ô (không so sánh công bằng được) và 6 ảnh mobile thiếu overlay tên trình duyệt — báo lại cho bạn thay vì tự điền liều. Sau khi bạn xác nhận C1 đã sửa đúng event và C6 cùng event với desktop, AI phát hiện giờ Event/Registration/Check-in trên Android thật lệch đúng 5:30 ở cả 6 mốc so với desktop — ghi thành `CP-B2-01`, điền đủ `03-compatibility-matrix.md` (7 ô × 3 màn = 21 dòng kết quả) và cập nhật `04-findings-log.md`/`README.md`/`00-main-report.md` theo số liệu mới (41 finding, sev 2 tăng lên 15).
- **Human Review Notes:** Tự kiểm tra đồng hồ hệ thống của thiết bị Android thật lúc còn phiên: máy hiện 14:36 trong khi giờ Việt Nam thật là 21:36 — lệch 7 tiếng, xác nhận đúng nguyên nhân AI nghi ngờ, không phải lỗi ngẫu nhiên. Cũng tự kiểm tra B4 trên mobile — xác nhận cùng bị lệch giờ như B2, nên đã yêu cầu mở rộng `CP-B2-01` sang cả B4. Quyết định không chụp lại 6 ảnh mobile thiếu tên browser trong khung — chấp nhận rủi ro đó. Output phù hợp sau khi cập nhật.
### [LOG-010] — Task 4 — Chuẩn hoá findings log, đồng bộ số liệu

- **Tool:** Claude Code · **Date:** 06/08/2026 (xuyên suốt, nhiều lượt đồng bộ)
- **Prompt:** Sau mỗi lần thêm finding mới, yêu cầu đếm lại bằng lệnh (`grep -c`) thay vì tin số liệu cũ, đồng bộ `04-findings-log.md` ↔ `README.md` ↔ `00-main-report.md`.
- **AI Output:** 41 finding cuối cùng (27 khảo sát + 11 Task 1B + 2 Task 2 + 1 Task 3), phát hiện và tự sửa 1 lần số liệu bị lệch (cột CL- từng ghi nhầm 7 Bug/4 Usability, đếm lại đúng là 6/5).
- **Human Review Notes:** Yêu cầu đếm lại bằng lệnh mỗi lần đồng bộ vì thấy AI để lọt số sai ít nhất 1 lần (cột CL-) — đọc bằng mắt một bảng dài rất dễ bỏ sót chênh lệch nhỏ. Dùng lại nguyên tắc này suốt phần còn lại của bài, không riêng Task 4.

### [LOG-011] — Task 5: viết 3 Agent Skills + quay video demo

- **Tool:** Claude Code (Claude Sonnet 5) · **Date:** 06/08/2026
- **Prompt:** Yêu cầu viết skill tái sử dụng được cho 3 kỹ thuật của bài (GUI checklist, usability 5 người, cross-platform matrix), sau đó *"tạo folder mới để quay demo riêng không ảnh hưởng bài làm, trong đó 1 file kịch bản chi tiết... file 2 là file prompt chi tiết có sẵn cho từng phần"*, chỉ cần 1 video ~7 phút.
- **AI Output:** 3 file `skills/*/SKILL.md` (gui-checklist, usability-5users, crossplatform-matrix). Riêng cho video: folder `video-demo-prep/` (nằm ngoài thư mục chấm điểm) gồm kịch bản theo mốc thời gian và 3 prompt copy-paste sẵn, rút gọn từ skill `hw03-gui-checklist` xuống vừa 7 phút.
- **Human Review Notes:** Hỏi lại AI 2 chỗ trước khi quay: mở folder kịch bản có ảnh hưởng gì tới AI không (không — prompt tự chứa đủ ngữ cảnh), và đoạn bắt lỗi trực tiếp trên EMS có cần chụp ảnh thêm không (không cần — video tự nó là bằng chứng). Sau khi rõ 2 điểm đó thì quay được luôn, không cần chỉnh lại kịch bản. Video: https://www.youtube.com/watch?v=hH9GwM8wB8M

### [LOG-012] — Hoàn thiện README, AI Critique, đồng bộ số liệu cuối cùng

- **Tool:** Claude Code (Claude Sonnet 5) · **Date:** 06/08/2026
- **Prompt:** Yêu cầu rà lại toàn bộ file còn TODO, viết nháp AI Critique 200–300 từ dùng ví dụ thật, đơn giản hoá tất cả Human Review Notes bằng giọng văn dễ đọc, điền thông tin nhóm 10 vào các bảng, sửa 1 vài chỗ theo yêu cầu cụ thể (bỏ mục pilot tự test, gộp lỗi B4 vào cùng finding với B2...).
- **AI Output:** AI Critique nháp 284 từ (đã đếm bằng `wc -w`), toàn bộ file chính hết TODO trừ những phần chỉ sinh viên tự làm được (chấm điểm, submit form, xuất PDF...).
- **Human Review Notes:** Phần AI Critique và các Human Review Notes khác là AI viết nháp từ dữ liệu thật của chính bài — mình đọc lại thấy hợp lý, chỗ nào đúng thì giữ nguyên, không cần viết lại toàn bộ từ đầu.

---

## Tổng kết phiên làm việc với AI

| Chỉ số | Số lượng |
|---|:--:|
| Tổng số phiên AI (log ở trên) | **12 log** — đủ từ dựng khung bài nộp tới hoàn thiện cuối cùng |
| Số lần AI đưa thông tin **sai** phải sửa | **4 lần đã xác nhận:** `N-02` (kết luận sai theo finding cũ), `S-15` (hiểu sai câu hỏi), tính tay SUS P3 sai (30 thay vì 27.5), đếm nhầm cột CL- (7/4 thay vì 6/5) |
| Số lần AI **bỏ sót** phải bổ sung | 23 item checklist (`RV`) + các finding chỉ phát hiện được sau khi có ảnh/dữ liệu thật (vd `CL-B1-04` màu nút đỏ, phát hiện nhờ đối chiếu ảnh đã chụp cho mục khác) |
| Số output AI bị **loại bỏ hoàn toàn** | 0 — mọi output sai đều được **sửa lại có căn cứ**, không có trường hợp AI tạo ra nội dung phải xoá bỏ hoàn toàn không dùng được |

> Các trường hợp cụ thể ở đây là nguyên liệu để viết `appendix/a4-ai-critique.md`. Ghi cả những lần AI đúng nhưng bạn vẫn phải kiểm chứng lại bằng tay — đó là bằng chứng cho nguyên tắc "human review".

## Những việc AI KHÔNG làm được trong bài này

> Ghi rõ ranh giới để người chấm thấy bạn hiểu giới hạn của công cụ.

| Việc | Vì sao AI không làm được | Ai làm |
|---|---|---|
| Chạy 5 phiên user testing với người thật | Cần con người thật, think-aloud, quan sát trực tiếp | Sinh viên (qua study Maze) |
| Chụp ảnh EMS thật có overlay MSSV | Ràng buộc chống gian lận của đề; ảnh phải là ảnh thật | Sinh viên |
| Chạy BrowserStack/LambdaTest bằng tài khoản cá nhân | AI không có quyền truy cập tài khoản trial | Sinh viên |
| Submit Google Form bằng email MSSV | Cần đăng nhập tài khoản trường | Sinh viên |
| Đăng nhập EMS, dựng dữ liệu thử, thao tác trên trình duyệt thật | AI không có quyền truy cập trực tiếp SUT, không nhìn thấy màn hình thật | Sinh viên |
| Nghe/xem lại 5 video để đếm chính xác số lỗi thao tác, số lần do dự | AI chỉ đọc được transcript văn bản (đôi khi lỗi), không "xem" được nội dung hình ảnh chuyển động | Sinh viên |
| Xác nhận 5 participant thật sự ngoài lớp học | AI không kiểm tra được danh sách lớp | Sinh viên |
| Quyết định severity cuối cùng cho từng finding | Đề yêu cầu đây là phán đoán của người kiểm thử; AI chỉ đề xuất kèm lý do | Sinh viên tự duyệt lại |
