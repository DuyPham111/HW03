# Usability Report — Task 2

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183) · **Kịch bản:** B — User đăng ký tham dự sự kiện
**Màn hình được test:** B1 Danh sách sự kiện · B2 Trang chi tiết sự kiện · B4 Profile → My Activities ⚠️ *(tên + có QR hay không đang chờ xác minh, xem §1.1)*
**Thang đo dùng:** _(TODO: SUS hoặc UEQ-S)_
**Thời gian chạy:** _(TODO)_ → _(TODO)_

> ⚠️ **TA có thể gọi ngẫu nhiên 2 trong 5 người tham gia để xác minh. Giả mạo người tham gia = 0 điểm toàn bộ Task 2.**
> Bằng chứng thô (notes từng phiên, phiếu SUS, bản ghi màn hình) lưu ở `evidence/task2/`.

---

## GIAI ĐOẠN 1 — Thiết kế & chuẩn bị

### 1.1 Task scenario

> ✅ **Đã xác minh trên hệ thống thật (06/08/2026):** mã QR check-in **có tồn tại**, nhưng **không phải vé theo từng sự kiện**. Nó là **một mã cố định cho cả tài khoản**, mã hoá **Student ID**, mở bằng nút **`QR Code`** ở góc phải trên trang **My Profile** — tách hoàn toàn khỏi danh sách đăng ký (ảnh `docs/khao-sat/check-in-profile.png`).
> **Chính điều này làm tác vụ trở nên đáng đo:** người vừa đăng ký xong sẽ tìm vé ở đâu? Ở chỗ đăng ký và trong My Activities **đều không có đường dẫn nào tới QR**. Nếu ≥ 3/5 participant kẹt ở bước này ⇒ finding hệ thống hạng nặng (`SV-B4-01`).

**Mục tiêu giao cho người dùng (viết dưới dạng MỤC TIÊU, tuyệt đối không liệt kê từng bước bấm):**

> **Bản chốt cho kịch bản B:**
> *"Khoa sắp có một workshop mà bạn muốn tham dự. Hãy đăng ký tham gia và cho mình xem mã QR check-in của bạn."*

**Bối cảnh kể cho người dùng:** bạn nghe người quen nhắc tới một workshop của Khoa CNTT mà bạn muốn tham dự. Đây là lần đầu bạn dùng hệ thống EMS.

**Điều kiện coi là hoàn thành (success criteria):** người dùng **tự mở được modal `Check-in QR Code`** (My Profile → nút `QR Code`) **và** hoàn tất đăng ký đúng sự kiện được giao. Đăng ký xong nhưng **không tự tìm ra QR** ⇒ **Partial** *(đây là nhánh đáng quan tâm nhất)*. Không hoàn tất đăng ký ⇒ **Failed**.

**Ba màn hình mà tác vụ này đi qua:** B1 Danh sách sự kiện (tìm được sự kiện) → B2 Trang chi tiết sự kiện (đọc thông tin, ra quyết định, và chọn vai trò rồi bấm đăng ký ngay tại đây) → B4 **My Profile** (nút QR Code + khối My Activities). Không có màn hình form riêng: EMS đặt khối đăng ký ngay trong trang chi tiết.

> 🔎 **Điểm quan sát then chốt của mỗi phiên:** ghi lại **participant tìm QR ở những đâu trước khi ra được Profile** — trong trang sự kiện? trong My Activities? bấm vào thẻ đăng ký? Đường đi sai của họ chính là dữ liệu giá trị nhất của Task 2 này.

**Biến thể để lộ thêm trạng thái (dùng cho 2/5 participant):** giao sự kiện **đã hết chỗ và có bật Waitlist** thay vì sự kiện còn chỗ — để xem người dùng có hiểu mình đang vào **danh sách chờ** chứ không phải đã được nhận hay không. Đây thường là chỗ hiểu nhầm nặng nhất của luồng đăng ký, và nó chỉ lộ ra khi có người thật thao tác.

**Điểm dừng (khi nào moderator can thiệp):** _(TODO — đề xuất: chỉ can thiệp khi participant bí hoàn toàn quá 2 phút ở cùng một chỗ; ghi lại mọi lần can thiệp)_

**Lưu ý vận hành — tài khoản và dữ liệu:** participant **không có tài khoản Microsoft/Office 365 của HCMUS** nên không đăng nhập được bằng nút `STUDENT` (xem `docs/KHAO_SAT_EMS.md` mục ⚠️4). Dùng **tài khoản demo dùng chung** đã tạo sẵn cho cả 5 phiên.

> ⚠️ **Vì 5 người dùng chung một tài khoản, phải tách dữ liệu từng phiên** — nếu không, P1 đăng ký xong thì P2 mở lên đã thấy sự kiện đó nằm sẵn trong My Activities và **không thực hiện được đúng tác vụ**.
> **Cách xử lý đã chọn:** dựng sẵn **5 sự kiện riêng** `[23127183] Workshop P1`…`P5`, mỗi participant làm trên sự kiện của mình. Vừa giữ trạng thái sạch, vừa không phải thao tác gì giữa các phiên (lúc đó đang bận quan sát), vừa tách bạch dữ liệu về sau.
> *(Phương án thay thế: huỷ đăng ký bằng nút `Cancel Registration` sau mỗi phiên — đã xác nhận hoạt động — nhưng nhớ chụp My Activities của từng người TRƯỚC khi huỷ.)*

Ngoài 5 sự kiện trên, cần chuẩn bị thêm bằng quyền admin: một sự kiện **hết chỗ + bật Waitlist** (dùng cho biến thể ở 2/5 phiên), đặt tiền tố `[23127183]` để không lẫn với dữ liệu lớp.

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

Phủ đủ 4 chủ đề đề yêu cầu: **clarity · error recovery · speed · trust**. Câu hỏi trung lập, không dẫn dắt.

| # | Chủ đề | Câu hỏi |
|---|---|---|
| Q1 | Clarity | Trong lúc làm nhiệm vụ, có bước nào bạn không chắc mình cần làm gì tiếp theo không? Đó là bước nào? |
| Q2 | Error recovery | Nếu có lúc bạn bấm nhầm hoặc đi sai hướng, bạn đã nhận ra bằng cách nào, và có dễ quay lại không? |
| Q3 | Speed | Nhiệm vụ này diễn ra nhanh hơn, chậm hơn, hay đúng như bạn mong đợi? |
| Q4 | Trust | Ở thời điểm nào trong lúc làm, bạn cảm thấy tự tin nhất là mình đang làm đúng? Có lúc nào bạn nghi ngờ không? |
| Q5 | Tổng quát | Nếu chỉ được đổi một điều duy nhất trên các màn hình bạn vừa dùng, bạn sẽ đổi gì? |

### 1.4 Người tham gia (5 người, NGOÀI lớp học)

**Chân dung mục tiêu cho kịch bản B:** **người ngoài trường muốn tham dự sự kiện của khoa** (event-goers), đăng ký qua vai trò **Guest** — khớp đúng nghĩa đen với *"students, lecturers, or event-goers as fits your scenario"* của đề, và khớp thực tế kỹ thuật: participant là bạn bè ngoài lớp, không có tài khoản Microsoft/Office 365 của HCMUS nên không đăng nhập được bằng vai trò Student (xem `docs/KHAO_SAT_EMS.md` mục ⚠️4). Không cần họ biết trước EMS; ngược lại, người chưa từng dùng mới lộ ra được vấn đề usability.

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
