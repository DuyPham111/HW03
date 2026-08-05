# Usability Report — Task 2

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183) · **Kịch bản:** B — User đăng ký tham dự sự kiện
**Màn hình được test:** B2 Trang chi tiết sự kiện · B3 Form đăng ký · B4 My Registrations + vé QR
**Thang đo dùng:** _(TODO: SUS hoặc UEQ-S)_
**Thời gian chạy:** _(TODO)_ → _(TODO)_

> ⚠️ **TA có thể gọi ngẫu nhiên 2 trong 5 người tham gia để xác minh. Giả mạo người tham gia = 0 điểm toàn bộ Task 2.**
> Bằng chứng thô (notes từng phiên, phiếu SUS, bản ghi màn hình) lưu ở `evidence/task2/`.

---

## GIAI ĐOẠN 1 — Thiết kế & chuẩn bị

### 1.1 Task scenario

**Mục tiêu giao cho người dùng (viết dưới dạng MỤC TIÊU, tuyệt đối không liệt kê từng bước bấm):**

> **Bản nháp cho kịch bản B — rà lại sau pilot rồi chốt:**
> *"Khoa sắp có một workshop mà bạn muốn tham dự. Hãy đăng ký tham gia và cho mình xem mã QR check-in của bạn."*

**Bối cảnh kể cho người dùng:** _(TODO — 2–3 câu, đại ý: bạn nghe bạn bè nhắc tới một workshop của khoa; trước giờ việc đăng ký làm qua Google Form, năm nay chuyển sang hệ thống EMS. Đây là lần đầu bạn dùng nó.)_

**Điều kiện coi là hoàn thành (success criteria):** người dùng **tự mở được mã QR/barcode check-in của chính mình** trong màn hình My Registrations, ứng với sự kiện đúng. Đăng ký được nhưng không tìm ra vé ⇒ **Partial**. Không hoàn tất đăng ký ⇒ **Failed**.

**Ba màn hình mà tác vụ này đi qua:** B2 Trang chi tiết sự kiện (đọc thông tin, ra quyết định) → B3 Form đăng ký (chọn vai trò, xác nhận) → B4 My Registrations + vé QR (tìm lại đăng ký và mở mã check-in). Trang chủ B1 là đường vào, được quan sát nhưng không nằm trong phạm vi chấm.

**Biến thể để lộ thêm trạng thái (dùng cho 2/5 participant):** giao sự kiện **đã hết chỗ và có bật Waitlist** thay vì sự kiện còn chỗ — để xem người dùng có hiểu mình đang vào **danh sách chờ** chứ không phải đã được nhận hay không. Đây thường là chỗ hiểu nhầm nặng nhất của luồng đăng ký, và nó chỉ lộ ra khi có người thật thao tác.

**Điểm dừng (khi nào moderator can thiệp):** _(TODO — đề xuất: chỉ can thiệp khi participant bí hoàn toàn quá 2 phút ở cùng một chỗ; ghi lại mọi lần can thiệp)_

**Lưu ý vận hành (thuận lợi của kịch bản B):** mỗi participant **tự đăng ký tài khoản EMS riêng** ngay đầu phiên, nên năm phiên **không đụng dữ liệu của nhau** và có thể chạy linh hoạt về thời gian. Cần chuẩn bị trước bằng quyền admin: ít nhất một sự kiện `PUBLISHED` + `UPCOMING` còn chỗ, một sự kiện hết chỗ + bật Waitlist, đặt tiền tố `[23127183]` để không lẫn với dữ liệu lớp.

> **Việc đăng ký tài khoản có tính vào tác vụ không?** Không — cho participant đăng ký/đăng nhập xong rồi mới bắt đầu bấm giờ, để `time on task` chỉ đo đúng luồng đăng ký sự kiện. Nhưng **vẫn ghi chú lại** mọi khó khăn họ gặp ở bước tạo tài khoản, coi như finding phụ.

### 1.2 Chỉ số đo

| Chỉ số | Cách đo | Ghi chú |
|---|---|---|
| Task success | Completed / Partial / Failed | Định nghĩa rõ "Partial" là gì: _(TODO)_ |
| Time on task | Bấm giờ từ lúc bắt đầu đến lúc đạt success criteria | Trừ thời gian moderator nói chuyện |
| Errors | Số thao tác sai dẫn tới kết quả ngoài mong muốn | |
| Hesitations | Số lần dừng > _ giây hoặc nói ra sự bối rối | |
| SUS / UEQ-S | Điền sau khi xong tác vụ | Bản _(TODO: EN/VI)_ |

### 1.3 Câu hỏi mở (probe questions)

Phủ đủ 4 chủ đề đề yêu cầu: **clarity · error recovery · speed · trust**.

| # | Chủ đề | Câu hỏi |
|---|---|---|
| Q1 | Clarity | _(TODO)_ |
| Q2 | Error recovery | _(TODO)_ |
| Q3 | Speed | _(TODO)_ |
| Q4 | Trust | _(TODO)_ |
| Q5 | Tổng quát | _(TODO — ví dụ: "Nếu được đổi một thứ duy nhất trên màn hình này, bạn đổi gì?")_ |

### 1.4 Người tham gia (5 người, NGOÀI lớp học)

**Chân dung mục tiêu cho kịch bản B:** **sinh viên có đi dự sự kiện/workshop của trường** — đúng nhóm người dùng thật của phía user trong EMS, và khớp với yêu cầu *"students, lecturers, or event-goers as fits your scenario"* của đề. Không cần họ biết trước EMS; ngược lại, người chưa từng dùng mới lộ ra được vấn đề usability.

**Vì sao kịch bản B dễ tuyển hơn hẳn:** tác vụ "đăng ký một workshop" là việc participant **vốn đã hiểu**, không cần giải thích nghiệp vụ; và mỗi người dùng **tài khoản riêng tự tạo** nên không phải mượn tài khoản admin dùng chung của lớp.

> Che 4 chữ số **ở giữa** số điện thoại theo yêu cầu của đề.

| # | Tên | Vai trò / chân dung | Liên hệ (đã che) | Ngày phiên | Thiết bị & trình duyệt |
|---|---|---|---|---|---|
| P1 | | | 09**\*\*\*\***12 | | |
| P2 | | | | | |
| P3 | | | | | |
| P4 | | | | | |
| P5 | | | | | |

**Xác nhận:** ⬜ Cả 5 người đều **không** học lớp này · ⬜ Đều có liên hệ kiểm chứng được · ⬜ Đã xin phép ghi màn hình/âm thanh

### 1.5 Pilot (người thứ 6, KHÔNG tính vào 5 người)

| Mục | Nội dung |
|---|---|
| Người pilot | _(TODO)_ |
| Ngày | _(TODO)_ |
| Vấn đề phát hiện trong kịch bản | _(TODO)_ |
| Đã chỉnh sửa gì trước 5 phiên thật | _(TODO)_ |

---

## GIAI ĐOẠN 2 — Chạy 5 phiên

Dữ liệu thô của từng phiên (dòng thời gian, lời nói nguyên văn, câu trả lời probe, số can thiệp của moderator) nằm ở **[`appendix/a1-session-notes.md`](appendix/a1-session-notes.md)** — không chép lại ở đây để tránh lệch số liệu giữa hai file.

| Bằng chứng | Nơi lưu |
|---|---|
| Ghi chú & dòng thời gian 5 phiên | [`appendix/a1-session-notes.md`](appendix/a1-session-notes.md) |
| Transcript có mốc thời gian | [`evidence/task2/`](evidence/task2/) |
| Link bản ghi màn hình | [`evidence/task2/recordings.md`](evidence/task2/recordings.md) |
| Phiếu SUS thô + cách quy đổi | [`appendix/a2-sus-scoring.md`](appendix/a2-sus-scoring.md) |

**Cách chạy đã áp dụng:** đọc nguyên văn lời thoại mở đầu cho cả 5 người · yêu cầu think-aloud · quan sát trung lập, chỉ can thiệp khi bí quá 2 phút và có ghi lại · điền SUS **trước** rồi mới hỏi câu mở.

---

## GIAI ĐOẠN 3 — Phân tích

### 3.1 Bảng chỉ số tổng hợp

| Participant | Success | Time on task | Errors | Hesitations | SUS/UEQ-S |
|---|---|---:|---:|---:|---:|
| P1 | | | | | |
| P2 | | | | | |
| P3 | | | | | |
| P4 | | | | | |
| P5 | | | | | |
| **Trung bình / Tỉ lệ** | ___% completed | | | | |

**Diễn giải điểm SUS:** _(TODO — SUS < 68 là dưới trung bình; > 80.3 là tốt. Ghi rõ điểm của bạn nằm ở đâu và nghĩa là gì)_

### 3.2 Nhóm các điểm đau (pain points)

| Nhóm vấn đề | Số participant gặp | Màn hình | Bằng chứng (trích lời) |
|---|:--:|---|---|
| _(TODO)_ | /5 | | |

### 3.3 Tách bug đơn lẻ vs vấn đề thiết kế hệ thống

> Đây là yêu cầu tường minh của đề: *"separate isolated bugs from systemic design issues"*.

| Loại | Finding | Vì sao xếp vào loại này |
|---|---|---|
| Bug đơn lẻ | _(TODO)_ | chỉ 1 người gặp / do trạng thái dữ liệu đặc thù / lỗi kỹ thuật rõ ràng |
| Vấn đề hệ thống | _(TODO)_ | ≥ 3/5 người gặp / lặp lại trên nhiều màn hình / bắt nguồn từ quyết định thiết kế |

### 3.4 Findings xếp hạng theo Severity (0–4)

**Thang severity (Nielsen):** 0 = không phải vấn đề usability · 1 = cosmetic, chỉ sửa nếu dư thời gian · 2 = minor, ưu tiên thấp · 3 = major, ưu tiên cao · 4 = catastrophe, bắt buộc sửa trước khi phát hành

| # | Finding | Màn hình | Heuristic vi phạm | Số người gặp | Severity | Ảnh | Finding-ID |
|---|---|---|---|:--:|:--:|---|---|
| 1 | | | | /5 | | | US-B2-01 |
| 2 | | | | /5 | | | US-B3-01 |
| 3 | | | | /5 | | | US-B4-01 |

**Chi tiết từng finding:**

#### US-B2-01 — _(tên)_ · Severity _(0–4)_

- **Mô tả:** _(TODO)_
- **Bằng chứng từ phiên:** _(TODO — trích lời + participant nào)_
- **Heuristic vi phạm:** _(TODO)_
- **Ảnh:** ![US-B2-01](evidence/task2/US-B2-01.png)
- **Khuyến nghị sửa:** _(TODO — cụ thể, làm được ngay, không viết chung chung)_

### 3.5 Danh sách khuyến nghị có ưu tiên

| Ưu tiên | Khuyến nghị | Finding liên quan | Chi phí ước tính | Tác động ước tính |
|:--:|---|---|---|---|
| P0 | | | | |
| P1 | | | | |
| P2 | | | | |

---

## Kết luận

_(TODO — 1–2 đoạn: giao diện của kịch bản này khả dụng đến đâu, rào cản lớn nhất với người dùng thật là gì, và nếu chỉ sửa được 1 thứ thì nên sửa gì)_

**Giới hạn của nghiên cứu:** _(TODO — cỡ mẫu 5, chân dung người tham gia lệch về nhóm nào, môi trường test, dữ liệu SUT bị reset…)_
