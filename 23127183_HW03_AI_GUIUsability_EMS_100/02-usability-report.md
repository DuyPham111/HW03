# Usability Report — Task 2

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183) · **Kịch bản:** B — User đăng ký tham dự sự kiện
**Màn hình được test:** B1 Danh sách sự kiện · B2 Trang chi tiết sự kiện · B4 My Profile → My Activities
**Thang đo dùng:** _(TODO: SUS hoặc UEQ-S)_
**Thời gian chạy:** _(TODO)_ → _(TODO)_

> ⚠️ **TA có thể gọi ngẫu nhiên 2 trong 5 người tham gia để xác minh. Giả mạo người tham gia = 0 điểm toàn bộ Task 2.**
> Bằng chứng thô (notes từng phiên, phiếu SUS, bản ghi màn hình) lưu ở `evidence/task2/`.

---

## GIAI ĐOẠN 1 — Thiết kế & chuẩn bị

### 1.1 Task scenario

> ⚠️ **Sửa ngày 06/08/2026 — bỏ QR khỏi kịch bản.** Bản trước dùng "tự mở được mã QR" làm tiêu chí hoàn thành. Đã xác minh: QR **là một mã cố định theo tài khoản** (mã hoá `Student ID`), **không đổi theo có đăng ký hay không** — bất kỳ tài khoản nào mở trang Profile cũng thấy QR, kể cả khi **chưa đăng ký sự kiện nào** (`evidence/survey/KS_B4_empty-qr.png`). Dùng nó làm tiêu chí hoàn thành là một phép đo yếu: nó không thực sự xác nhận participant đã đăng ký đúng sự kiện. `SV-B4-01` (QR tách rời khỏi luồng đăng ký) vẫn là một finding hợp lệ trong `04-findings-log.md`, chỉ không còn là thứ kịch bản test nhắm tới.

**Mục tiêu giao cho người dùng (viết dưới dạng MỤC TIÊU, tuyệt đối không liệt kê từng bước bấm):**

> **Bản chốt cho kịch bản B (06/08/2026)** — cấu trúc *vai trò → gạch đầu dòng yêu cầu → khối tài khoản*, tham khảo từ study Maze của một bạn cùng lớp:
> *"Bạn là một người quen của khoa muốn tham dự một workshop sắp diễn ra. Đây là lần đầu bạn dùng hệ thống EMS. Hãy:*
> - *Tìm và đăng ký tham gia một workshop bạn muốn tham dự*
> - *Sau khi đăng ký xong, cho mình xem lại đăng ký đó*
>
> *Tài khoản: mình đã đăng nhập sẵn giúp bạn, không cần tạo hay nhập gì."*

Nội dung y hệt được dán vào Maze — xem `docs/HUONG_DAN_DUNG_MAZE.md` Ô 1/Ô 2 và `evidence/task2/test-request.md` (bản dự phòng giấy).

**Bối cảnh kể cho người dùng:** bạn nghe người quen nhắc tới một workshop của Khoa CNTT mà bạn muốn tham dự. Đây là lần đầu bạn dùng hệ thống EMS.

**Điều kiện coi là hoàn thành (success criteria):** người dùng đăng ký thành công **và** tự tìm được đúng đăng ký đó trong **My Activities** (đúng tên sự kiện, đúng trạng thái badge). Đăng ký được nhưng **không tự tìm ra My Activities / không xác nhận lại được** ⇒ **Partial** *(nhánh đáng quan tâm nhất — đo việc hệ thống có chỉ đường tới xác nhận sau khi đăng ký hay không, xem `S-14`)*. Không hoàn tất đăng ký ⇒ **Failed**.

**Ba màn hình mà tác vụ này đi qua:** B1 Danh sách sự kiện (tìm được sự kiện) → B2 Trang chi tiết sự kiện (đọc thông tin, ra quyết định, và chọn vai trò rồi bấm đăng ký ngay tại đây) → B4 **My Profile** (khối My Activities). Không có màn hình form riêng: EMS đặt khối đăng ký ngay trong trang chi tiết.

> 🔎 **Điểm quan sát then chốt của mỗi phiên:** ghi lại **participant tìm đăng ký ở đâu sau khi bấm nút submit** — họ có tự đoán ra phải vào avatar → View profile không, hay phải được nhắc? Đăng ký xong hệ thống không có toast/thông báo nào (`SV-B2-09`), nên đường đi tìm xác nhận của họ chính là dữ liệu giá trị nhất của Task 2.

**Biến thể để lộ thêm trạng thái (dùng cho 2/5 participant):** giao sự kiện **đã hết chỗ và có bật Waitlist** thay vì sự kiện còn chỗ — để xem người dùng có hiểu mình đang vào **danh sách chờ** chứ không phải đã được nhận hay không. Đây thường là chỗ hiểu nhầm nặng nhất của luồng đăng ký, và nó chỉ lộ ra khi có người thật thao tác.

**Điểm dừng (khi nào moderator can thiệp):** _(TODO — đề xuất: chỉ can thiệp khi participant bí hoàn toàn quá 2 phút ở cùng một chỗ; ghi lại mọi lần can thiệp)_

**Lưu ý vận hành — tài khoản và dữ liệu:** participant **không có tài khoản Microsoft/Office 365 của HCMUS** nên không đăng nhập được bằng nút `STUDENT` (xem `docs/KHAO_SAT_EMS.md` mục ⚠️4). Dùng **tài khoản demo dùng chung** đã tạo sẵn cho cả 5 phiên.

> ⚠️ **Sửa ngày 06/08/2026 — quay lại phương án 1 tài khoản, KHÔNG cần 5 sự kiện riêng.** Bản trước lo "P1 đăng ký xong thì P2 sẽ thấy sự kiện đó sẵn trong My Activities" và né bằng cách dựng 5 sự kiện. Đã kiểm thật: nút `Cancel Registration` hoạt động đúng — sau khi huỷ, khối đăng ký ở B2 trở về trạng thái sạch và **đăng ký lại được bình thường** (`SV-B2-08`, đã xác nhận không phải bug). Vậy chỉ cần **một tài khoản, một sự kiện** (`Workshop A`, đang còn chỗ): giữa mỗi phiên, vào B2 bấm **Cancel Registration** một lần trước khi gọi người tiếp theo.
>
> **Đánh đổi phải ghi rõ trong báo cáo, không giấu:** sau khi huỷ, thẻ sự kiện của người trước **vẫn còn** trong My Activities với badge `Cancelled` (`SV-B4-05`) — không tự xoá. Người sau có thể thấy dấu vết đó nếu họ cuộn tới My Activities trước khi đăng ký xong. Không chặn tác vụ (nút Register vẫn hoạt động), chỉ hơi làm mất khung "lần đầu dùng hệ thống" nếu họ soi kỹ trước khi đăng ký. Chấp nhận đánh đổi này để tiết kiệm ~15 phút so với dựng 5 sự kiện hoặc 5 tài khoản riêng — quyết định đưa ra khi thời gian chuẩn bị không còn nhiều.
> - [ ] Trước phiên đầu tiên: chụp `KS_B4_empty.png` xác nhận trạng thái sạch *(đã có sẵn)*
> - [ ] Giữa mỗi phiên: B2 → Cancel Registration → xác nhận dialog → chờ badge biến mất khỏi khối Registration roles rồi mới gọi người tiếp theo

Ngoài `Workshop A`, cần chuẩn bị thêm bằng quyền admin: một sự kiện **hết chỗ + bật Waitlist** (dùng cho biến thể ở 2/5 phiên) — `Workshop B` đã có sẵn từ đợt khảo sát, đặt tiền tố `[23127183]` để không lẫn với dữ liệu lớp.

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

> ✅ **Nguồn dữ liệu 06/08/2026:** ngoài hỏi miệng qua cuộc gọi, Maze study tự thu **Họ và tên** + **Thông tin liên lạc** thành 2 block `Simple Input` ngay đầu study (xem `docs/HUONG_DAN_DUNG_MAZE.md` PHẦN 2b) — có bản ghi timestamped trong tab `Analyze`, không chỉ dựa vào ghi chú tay. Bảng dưới đây điền lại từ dữ liệu Maze, **che 4 số giữa trước khi đưa vào file này**; bản đầy đủ chưa che giữ riêng ngoài repo để đối chiếu khi TA gọi xác minh.

| # | Tên | Vai trò / chân dung | Liên hệ (đã che) | Ngày phiên | Thiết bị & trình duyệt |
|---|---|---|---|---|---|
| P1 | | | 09**\*\*\*\***12 | | |
| P2 | | | | | |
| P3 | | | | | |
| P4 | | | | | |
| P5 | | | | | |

**Xác nhận:** ⬜ Cả 5 người đều **không** học lớp này · ⬜ Đều có liên hệ kiểm chứng được · ⬜ Đã xin phép ghi màn hình/âm thanh **và** ghi hình camera qua Maze

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
