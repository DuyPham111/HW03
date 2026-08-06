# Usability Report — Task 2

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183) · **Kịch bản:** B — User đăng ký tham dự sự kiện
**Màn hình được test:** B1 Danh sách sự kiện · B2 Trang chi tiết sự kiện · B4 My Profile → My Activities
**Thang đo dùng:** SUS (System Usability Scale, Brooke 1996) — ⚠️ Maze bị cấu hình nhầm thang 1–10 thay vì chuẩn 1–5, đã quy đổi bằng `ceil(điểm/2)`, xem `appendix/a2-sus-scoring.md`
**Thời gian chạy:** 06/08/2026 → 06/08/2026 (cả 5 phiên chạy trong cùng ngày qua study Maze)

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

**Điểm dừng (khi nào moderator can thiệp):** Chỉ can thiệp khi participant bí hoàn toàn quá 2 phút liên tục ở cùng một chỗ (không thao tác, không nói gì thêm khi được nhắc think-aloud); mọi lần can thiệp phải ghi rõ trong `appendix/a1-session-notes.md` — lúc nào, participant nào, can thiệp bằng câu gì. ⚠️ Chưa ghi nhận lần can thiệp nào từ 5 transcript đã xử lý — cần bạn xác nhận lại khi xem video.

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
| Task success | Completed / Partial / Failed | "Partial" = đăng ký thành công nhưng **không tự tìm ra / không xác nhận lại được** đăng ký đó trong My Activities (xem định nghĩa đầy đủ ở §1.1 "Điều kiện coi là hoàn thành") |
| Time on task | Bấm giờ từ lúc bắt đầu đến lúc đạt success criteria | Trừ thời gian moderator nói chuyện |
| Errors | Số thao tác sai dẫn tới kết quả ngoài mong muốn | |
| Hesitations | Số lần dừng > _ giây hoặc nói ra sự bối rối | |
| SUS / UEQ-S | Điền sau khi xong tác vụ | Bản **VI** — dịch từ SUS gốc (Brooke 1996), soạn kèm bản đối chiếu song ngữ khi dựng câu hỏi trong Maze (xem `docs/HUONG_DAN_DUNG_MAZE.md`) |

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
| P1 | Phạm Vũ Ngọc Duyên | Event-goer | 0943\*\*\*\*44 | 06/08/2026 | Mac OS · Chrome 148 |
| P2 | Nguyễn Tấn Phước | Event-goer | phuo\*\*\*\*@gmail.com | 06/08/2026 | Linux · Chrome 149 |
| P3 | Quan Anh | Event-goer | 0988\*\*\*\*54 | 06/08/2026 | iPhone 14 Plus (mobile) · app MazeParticipate |
| P4 | Lê Đức Ngọc Bảo | Event-goer | ldnb\*\*\*\*@clc.fitus.edu.vn | 06/08/2026 | Windows · Chrome 150 |
| P5 | Hoàng Vũ Gia Huy | Event-goer | giah\*\*\*\*@gmail.com | 06/08/2026 | Windows · Brave 151 |

**Xác nhận:** ⬜ Cả 5 người đều **không** học lớp này *(bạn tự xác nhận — AI không kiểm được danh sách lớp)* · ✅ Đều có liên hệ kiểm chứng được (số điện thoại/email thật) · ⬜ Đã xin phép ghi màn hình/âm thanh **và** ghi hình camera qua Maze *(bạn tự xác nhận đã bật đồng ý trước khi participant bắt đầu)*

> ⚠️ Study Maze gốc có **7 người** tham gia — đã loại 2 người khỏi bảng trên: `Nguyễn Minh Khôi` và chính người làm bài (`Duy`, cũng chưa hoàn thành study). Chi tiết ở `evidence/task2/recordings.md`.

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

| Participant | Success | Time on task | Errors | Hesitations | SUS |
|---|---|---:|---:|---:|---:|
| P1 | Completed | 8m15s | 5 *(làm đầy đủ, không thiếu bước nào)* | ≥2 *(lặp đọc "Campus", "Back to event")* | **85** |
| P2 | Completed | 0m59s | 2 *(thiếu View Activity — không tự tìm ra My Activities)* | 0 rõ ràng — hoàn thành rất nhanh | **42.5** |
| P3 | Completed | 2m06s | 2 *(không tìm thấy View Activity trong View Profile, giống P2/P4)* | ≥1 *(không tìm ra đường quay lại danh sách)* | **27.5** |
| P4 | Completed | 1m38s | 2 *(cũng thiếu View Activity, cùng dạng lỗi với P2/P3)* | ≥1 *(nghi ngờ khi nút Register bị khoá)* | **30** |
| P5 | Completed | 4m40s | 1 | Gặp vấn đề ở phần đăng ký/đăng nhập tài khoản, sau đó làm đầy đủ | **80** |
| **Trung bình / Tỉ lệ** | **100% completed (5/5)** | 3m32s | 2.4 | 3/5 người không tự tìm ra My Activities (P2, P3, P4) | **53.0** |

> Cột **Errors** đếm theo số lần bấm sai/thao tác sai bạn quan sát được khi xem lại 5 video. Điểm chung nổi bật: **3/5 người (P2, P3, P4) đều thiếu đúng 1 loại thao tác — không tự tìm ra My Activities/View Activity** để xác nhận lại đăng ký, đây là cùng gốc với `SV-B2-09`/`US-B2-01` (không có phản hồi/chỉ dẫn sau khi đăng ký xong).

**Diễn giải điểm SUS:** trung bình **53.0** — **dưới mốc 68 (dưới trung bình)**. Nhưng số trung bình này **gây hiểu lầm** nếu đọc một mình: dữ liệu tách thành hai nhóm rõ rệt (xem `appendix/a2-sus-scoring.md`) — P1/P5 đạt mức "tốt" (80, 85 — trên mốc 80.3 hoặc sát mốc), còn P2/P3/P4 đều dưới trung bình rõ rệt (27.5–42.5). Độ lệch chuẩn 24.67 lớn bất thường so với một hệ thống đồng nhất — đáng bàn kỹ ở phần khuyến nghị thay vì chỉ báo cáo một con số duy nhất.

### 3.2 Nhóm các điểm đau (pain points)

| Nhóm vấn đề | Số participant gặp | Màn hình | Bằng chứng (trích lời) |
|---|:--:|---|---|
| Nghi ngờ hành động đã thành công hay chưa (không có phản hồi/xác nhận) | **2/5** (P2, P4) | B2 | P2: *"Tôi nghi ngờ sự kiện đã được đưa lên chưa"* · P4: *"Có. Nghi ngờ khi nút đăng kí bị disable"* |
| Không tìm ra đường quay lại danh sách sự kiện | **1/5** (P3) | B2 | *"Không. Phải kiếm nút quay lại. Kéo lên đầu trang. Khó khăn"* |
| Bố cục một khối chiếm quá nhiều không gian màn hình | **1/5** (P1) | B2 *(chưa xác định chính xác khối nào, cần xem video)* | *"ô hiển thị nằm ngang, ô hiển thị hiện tại quá to, 2 ô đã chiếm hết màn hình"* |

### 3.3 Tách bug đơn lẻ vs vấn đề thiết kế hệ thống

> Đây là yêu cầu tường minh của đề: *"separate isolated bugs from systemic design issues"*.

| Loại | Finding | Vì sao xếp vào loại này |
|---|---|---|
| Vấn đề hệ thống | **Thiếu phản hồi sau hành động** (US-B2-01) | Không phải quan sát đơn lẻ — **trùng khớp với 3 finding đã có sẵn từ Task 1B** (`SV-B2-09` không toast sau đăng ký, `S-01`/`S-14` Failed cùng lý do). Hai nguồn độc lập (kiểm tra khách quan + người dùng thật) cùng chỉ về một nguyên nhân gốc: hệ thống không bao giờ xác nhận hành động bằng toast/thông báo, thấy lặp lại ở nhiều mục |
| Bug đơn lẻ *(cần thêm bằng chứng)* | **Nút quay lại khó tìm trên mobile** (US-B2-02) | Chỉ 1/5 người gặp (P3, dùng iPhone) — có thể do trạng thái màn hình mobile cụ thể (nút bị đẩy dưới fold) chứ không hẳn là lỗi trên mọi thiết bị. Task 1B đã Passed mục này trên desktop (`N-02`). Cần Task 3 (cross-platform) xác nhận có lặp lại trên các thiết bị mobile khác không mới nâng lên "vấn đề hệ thống" |
| Bug đơn lẻ *(chưa đủ bằng chứng)* | **Bố cục 1 khối chiếm hết màn hình** (P1) | Chỉ 1/5 người nhắc tới, chưa rõ khối nào — cần xem lại video P1 trước khi quyết định có phải bug thật hay chỉ là ý kiến cá nhân về gu thẩm mỹ |

### 3.4 Findings xếp hạng theo Severity (0–4)

**Thang severity (Nielsen):** 0 = không phải vấn đề usability · 1 = cosmetic, chỉ sửa nếu dư thời gian · 2 = minor, ưu tiên thấp · 3 = major, ưu tiên cao · 4 = catastrophe, bắt buộc sửa trước khi phát hành

| # | Finding | Màn hình | Heuristic vi phạm | Số người gặp | Severity | Finding-ID |
|---|---|---|---|:--:|:--:|---|
| 1 | Không có phản hồi/xác nhận sau khi đăng ký | B2 | N1 visibility of system status | **2/5** | **3** | `US-B2-01` |
| 2 | Nút quay lại danh sách khó tìm trên mobile | B2 | N3 user control and freedom | **1/5** | **2** | `US-B2-02` |

**Chi tiết từng finding:**

#### US-B2-01 — Người dùng nghi ngờ hành động đã thành công hay chưa · Severity 3

- **Mô tả:** Sau khi đăng ký (hoặc khi thấy nút bị khoá chờ điều kiện), hệ thống không đưa ra bất kỳ phản hồi/xác nhận rõ ràng nào. Người dùng phải tự suy đoán liệu thao tác của họ có được ghi nhận không.
- **Bằng chứng từ phiên:** P2 — *"Tôi nghi ngờ sự kiện đã được đưa lên chưa"* (câu trả lời Q4-Trust). P4 — *"Có. Nghi ngờ khi nút đăng kí bị disable"* (câu trả lời Q4-Trust).
- **Heuristic vi phạm:** N1 (visibility of system status)
- **Đối chiếu Task 1B:** trùng khớp hoàn toàn với `SV-B2-09`, `S-01`, `S-14` — đã Failed từ trước khi chạy Task 2. Đây là **bằng chứng hai chiều độc lập** cho cùng một finding, không phải phát hiện trùng lặp cần loại bỏ.
- **Khuyến nghị sửa:** Thêm toast xác nhận ngay sau khi bấm Register ("Đăng ký thành công, đang chờ duyệt"), và với nút bị khoá (chưa tick vai trò) thêm dòng chữ giải thích ngay cạnh nút thay vì chỉ đổi màu xám.

#### US-B2-02 — Nút quay lại danh sách không được tìm thấy trên mobile · Severity 2

- **Mô tả:** Nút `Back to events` tồn tại thật trên B2 (đã xác nhận `Passed` ở Task 1B, mục `N-02`, ảnh `G-06-S2.png`), nhưng một người dùng thật trên iPhone không tìm ra, phải tự cuộn lên đầu trang.
- **Bằng chứng từ phiên:** P3 — *"Không. Phải kiếm nút quay lại. Kéo lên đầu trang. Khó khăn"* (câu trả lời Q2-Error recovery).
- **Heuristic vi phạm:** N3 (user control and freedom)
- **Vì sao severity chỉ 2, không cao hơn:** đây là khoảng cách giữa "nút có tồn tại" (Task 1B khẳng định) và "nút có được nhận ra" (Task 2 khẳng định ngược lại) — khả năng cao là vấn đề **độ nổi bật trên màn hình nhỏ** (mobile), không phải nút hoàn toàn vắng mặt. Cần Task 3 xác nhận có lặp lại trên các thiết bị mobile khác không.
- **Khuyến nghị sửa:** Tăng độ tương phản/kích thước nút `Back to events` trên viewport hẹp (< 480px), hoặc ghim cố định (sticky) ở đầu trang khi cuộn xuống thay vì chỉ nằm ở vị trí tĩnh trên cùng.

### 3.5 Danh sách khuyến nghị có ưu tiên

| Ưu tiên | Khuyến nghị | Finding liên quan | Chi phí ước tính | Tác động ước tính |
|:--:|---|---|---|---|
| P0 | Thêm toast xác nhận sau mọi hành động thay đổi dữ liệu (đăng ký, huỷ đăng ký), và giải thích lý do khi nút bị khoá | `US-B2-01`, `SV-B2-09`, `S-01`, `S-14` | Thấp — chỉ thêm UI phản hồi, không đổi luồng nghiệp vụ | Cao — xoá bỏ nguồn nghi ngờ lớn nhất được cả kiểm tra khách quan lẫn người dùng thật xác nhận |
| P1 | Tăng độ nổi bật của nút quay lại trên màn hình hẹp/mobile | `US-B2-02`, `N-02` | Thấp — chỉnh CSS responsive | Trung bình — ảnh hưởng riêng nhóm dùng mobile |
| P2 | Thống nhất một bộ từ vựng trạng thái duy nhất (Approved/Pending Review/Rejected/Waitlisted) trên toàn hệ thống, sửa lại 4 ô đếm ở B2 | `S-15`, `SV-B4-03` | Trung bình — cần đổi tên field ở nhiều nơi | Trung bình — câu SUS Q6 (thiếu nhất quán) bị chấm thấp nhất trong 10 câu, xác nhận đây là vấn đề người dùng cảm nhận rõ |

---

## Kết luận

Luồng đăng ký sự kiện **khả dụng** — cả 5/5 người dùng thật hoàn thành tác vụ (100% Completed), không ai bị chặn hoàn toàn. Nhưng khả dụng không đồng nghĩa với dễ dùng: điểm SUS trung bình 53.0 (dưới mốc trung bình 68) và độ lệch chuẩn 24.67 bất thường cho thấy trải nghiệm **không đồng đều** — một nửa nhóm đánh giá tốt (P1=85, P5=80), nửa còn lại đánh giá kém (P2=42.5, P3=27.5, P4=30). Rào cản lớn nhất, xuất hiện lặp lại trong cả dữ liệu định lượng lẫn định tính, là **sự im lặng của hệ thống sau khi đăng ký** — không toast, không banner, chỉ một badge nhỏ mọc thêm — khiến 2/5 người trực tiếp nói ra sự nghi ngờ liệu thao tác đã thành công hay chưa (`US-B2-01`). Nếu chỉ sửa được một thứ, đó là thêm phản hồi rõ ràng ngay sau hành động đăng ký/huỷ đăng ký (khuyến nghị P0 ở bảng trên) — đây là điểm duy nhất được xác nhận độc lập bởi cả checklist Task 1B (`SV-B2-09`) và người dùng thật.

**Giới hạn của nghiên cứu:**
- Cỡ mẫu **5** là mức tối thiểu theo đề, đủ để phát hiện vấn đề usability phổ biến (theo Nielsen, 5 người phát hiện được ~85% vấn đề) nhưng không đủ để suy rộng tỉ lệ chính xác — con số 53.0 và độ lệch chuẩn lớn nên đọc như "tín hiệu có vấn đề", không phải ước lượng chính xác cho toàn bộ người dùng EMS.
- Cả 5 participant đều dùng chung **một tài khoản demo** (không phải tài khoản HCMUS thật), và giữa mỗi phiên có thao tác Cancel Registration để dọn dữ liệu (xem §1.1) — đánh đổi đã ghi rõ, nhưng đồng nghĩa 5 phiên không hoàn toàn độc lập về mặt trạng thái dữ liệu như 5 tài khoản thật.
- Nghiên cứu chạy **không đồng bộ, tự dẫn dắt qua study Maze** (participant tự làm theo hướng dẫn văn bản, không có moderator quan sát trực tiếp thời gian thực) — nghĩa là số liệu "Errors"/"Hesitations" phụ thuộc vào việc xem lại video sau, và không có cơ hội hỏi thêm ngay tại chỗ khi participant nói điều mơ hồ.
- Thang SUS trên Maze bị cấu hình nhầm 1–10 thay vì chuẩn 1–5, phải quy đổi (`ceil(điểm/2)`) — quy đổi này là suy diễn hợp lý, không phải phép đo trực tiếp trên thang chuẩn.
- SUT là môi trường dev dùng chung với cả lớp, dữ liệu có thể bị người khác chỉnh hoặc reset ngoài tầm kiểm soát giữa lúc chuẩn bị và lúc chạy 5 phiên thật.
