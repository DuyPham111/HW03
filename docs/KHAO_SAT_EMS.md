# PHIẾU KHẢO SÁT EMS — đã điền một phần từ ảnh chụp

**Người khảo sát:** Phạm Vũ Ngọc Duy (23127183) · **Ngày:** 05/08/2026 · **Giờ:** ~17:35 → 18:35
**SUT:** https://prod-dev.ems-fitus.cloud
**Tài khoản EMS đã dùng:** `23127183@student.hcmus.edu.vn` (đăng nhập qua nút **STUDENT**) · avatar hiển thị `DPVN`

> **Tình trạng:** đã có **38 ảnh** trong `docs/khao-sat/` qua 3 đợt khảo sát (05/08 và 06/08). 22 ảnh dùng làm bằng chứng finding đã được chép sang `evidence/survey/`. Những ô có ✅ là **đã xác nhận từ ảnh**. Những ô có ⬜ là **chưa kiểm — bạn phải tự vào EMS xem tiếp**.
> Đừng bỏ qua các ô ⬜: phần lớn nhóm item `F-` (form) và `S-` (feedback/state) phụ thuộc vào chúng.

---

## ⚠️ NĂM VIỆC PHẢI XỬ LÝ TRƯỚC KHI ĐI TIẾP

> Mục 4 và 5 thêm vào ngày 06/08/2026 sau khi đọc **tài liệu hướng dẫn chính thức của hệ thống** (`Hướng dẫn sinh viên | HCMUS EMS`, lấy từ `/manual/student` trên chính SUT). Đây là nguồn đáng tin hơn hẳn suy đoán từ ảnh chụp — sửa theo nguồn này.

### 1. ✅ ĐÃ GIẢI QUYẾT — B2 bị chặn là do CẤU HÌNH, không phải do hệ thống

Ảnh `KS_B2_chua-dang-nhap.png` cho thấy mở deep link tới sự kiện khi chưa đăng nhập thì chỉ hiện:

> 🔒 **Please sign in to view this event.** — nút `login`

> ⚠️ **Sửa lại kết luận của chính tôi (06/08/2026).** Lượt trước tôi kết luận *"B2 không phải màn hình công khai"* — **nói vậy là quá tay**. Ảnh `admin-4.png` cho thấy form tạo sự kiện có công tắc **`Public Event` — "Event is publicly visible"**, và nó **mặc định TẮT**. Nghĩa là: EMS **có** hỗ trợ trang sự kiện công khai; ba workshop thử của bạn bị chặn chỉ vì lúc tạo không bật công tắc đó.

**Đây lại là cơ hội tốt cho bài**, vì bạn kiểm được **cả hai nhánh**:

| Cấu hình | Người chưa đăng nhập thấy gì | Dùng để kiểm |
|---|---|---|
| `Public Event` **TẮT** *(3 workshop hiện tại)* | Chặn cả trang, nút `login` | Hành vi chặn có rõ ràng không, sau khi đăng nhập có quay lại đúng trang không |
| `Public Event` **BẬT** ✅ *(đã thử 06/08)* | **Xem được toàn bộ nội dung**, header hiện nút `Sign In`, có cả nút `Back to events` | Nội dung công khai có đầy đủ không, nút đăng ký hiện gì với người chưa đăng nhập |

- [x] ✅ **Đã dựng `[23127183] Public Event Test` và kiểm ở cửa sổ ẩn danh** → `KS_B2_public-an-danh.png`. Phát hiện kèm theo: ở nhánh công khai **CÓ nút `Back to events`**, trong khi đợt 1 tôi ghi B2 không có đường quay lại (`SV-B2-03`). Cần kiểm lại xem nút đó có ở nhánh đã đăng nhập không.

**Hệ quả cho kế hoạch (giữ nguyên, vì 3 workshop thử đều đang tắt Public Event):**

| Nơi bị ảnh hưởng | Thực tế |
|---|---|
| Task 3 cross-platform | Cả B1/B2/B4 đều cần đăng nhập ⇒ **phải đăng nhập lại ở TỪNG ô** BrowserStack (~7 ô × 3 màn) |
| Task 2 user testing | Participant phải đăng nhập trước, rồi mới bắt đầu bấm giờ |

### 2. ✅ ĐÃ CHỐT — email chính thức của bài

| Email | Vai trò | Ghi vào đâu |
|---|---|---|
| **`23127183@student.hcmus.edu.vn`** | ✅ **Tài khoản chính** — đăng nhập EMS, nộp Google Form, overlay lên mọi ảnh Task 3 | Toàn bộ bài làm |
| `pvnduy23@clc.fitus.edu.vn` | Tài khoản demo tạo riêng cho 5 phiên user testing | Chỉ dùng lúc chạy phiên, **không** dùng nộp form |

Khớp đúng mẫu `MSSV@....edu.vn` mà đề §7 và §12 yêu cầu. Đã đổi trong toàn bộ file (06/08/2026).

> 🔒 **Mật khẩu tài khoản demo KHÔNG được ghi vào repo.** Repo `github.com/DuyPham111/HW03` là **public** — mật khẩu commit vào đó sẽ nằm vĩnh viễn trong lịch sử git kể cả sau khi xoá, và bất kỳ ai cũng đọc được. Giữ mật khẩu ở chỗ riêng (ghi chú cá nhân / trình quản lý mật khẩu), lúc chạy phiên thì tự gõ. Sau khi nộp bài xong nên **đổi mật khẩu** tài khoản demo này.

### 3. ✅ Dữ liệu thử — đã đủ 6 sự kiện

| # | Sự kiện | Trạng thái | Ảnh |
|---|---|---|---|
| 1 | `[23127183] Workshop A — con cho` | ✅ đã dựng · Slot Student **49** · "Event starts in 1 day(s)" | `KS_B2_workshop-a-con-cho.png` |
| 2 | `[23127183] Workshop B — het cho` | ✅ đã dựng · Slot **0** · "Role is full" · Registered **1/1** | `KS_B2_workshop-b-het-cho.png` |
| 3 | `[23127183] Workshop C — dong dang ky` | ✅ đã dựng · "Event registration period has ended" | `KS_B2_workshop-c-dong-dang-ky.png` |
| 4 | `[23127183] Workshop D — da ket thuc` | ✅ đã dựng · "Event has ended" · Registered **0/50** · có khối **Rating summary** (0.0, thanh 5→1 sao đều 0%) · Campus *Linh Trung Campus* | `KS_B2_workshop-d-da-ket-thuc.png` |
| 5 | `[23127183] Public Event Test` | ✅ đã dựng · bật `Public Event` · xem được khi chưa đăng nhập | `KS_B2_public-an-danh.png` |
| 6 | `[23127183] TEST validation` | ✅ đã dựng để thử validation thời gian · Campus *UEH CAMPUS* | `KS_ADM_val-01.png` … `val-04` |

### 4. 🔴 Participant bên ngoài KHÔNG đăng nhập được như bạn đã làm — phải đổi hướng dẫn

Tài liệu chính thức, mục 1.3: *"Trong lần đầu đăng nhập, nhấn nút Microsoft - Student. Đăng nhập bằng tài khoản Microsoft/Office 365 của sinh viên do trường cấp."* Và mục 1.1.1 xác nhận trang Login có **2 nhóm nút khác nhau**, đừng nhầm:

| Nhóm nút | Vị trí | Chức năng |
|---|---|---|
| `LECTURER` (icon Google) / `STUDENT` (icon Microsoft) | Card đăng nhập chính | **Đăng nhập thật** — bắt buộc dùng lần đầu, cần **tài khoản Microsoft/Office 365 do HCMUS cấp** |
| `Create guest account` | Link phụ dưới nút đăng nhập | **Đăng ký tài khoản Guest** — không cần tài khoản HCMUS |
| Nút Lecturer/Student trong khung "Read user guides" | Trên cùng | **CHỈ mở trang manual public**, không đăng nhập, không gọi OAuth |

**Hệ quả:** 5 người tham gia Task 2 là bạn bè ngoài lớp, **không có tài khoản Microsoft/Office 365 của HCMUS** ⇒ họ không đăng nhập được bằng nút STUDENT.

**✅ Giải pháp đã chốt (06/08):** dùng **tài khoản demo `pvnduy23@clc.fitus.edu.vn`** đã tạo sẵn. Participant đăng nhập bằng tài khoản này, không phải tự đăng ký gì.

> 🔴 **NHƯNG có một vấn đề phải xử lý trước khi chạy phiên đầu tiên — 5 người dùng CHUNG 1 tài khoản sẽ hỏng dữ liệu:**
>
> | Vấn đề | Vì sao |
> |---|---|
> | **P2 trở đi không còn trạng thái sạch** | P1 đăng ký xong, sự kiện đó đã nằm trong My Activities. P2 mở lên thấy sẵn → không còn là "lần đầu dùng hệ thống" |
> | **Tác vụ có thể tự hoàn thành sẵn** | Nếu P1 đã đăng ký Workshop A, thì với P2 nút đăng ký đã đổi trạng thái ⇒ **P2 không thực hiện được đúng tác vụ** |
> | **Không tách được dữ liệu từng người** | Cả 5 phiên ghi vào cùng một tài khoản ⇒ không biết ai đăng ký cái gì |
>
> **✅ Đã kiểm ngày 06/08 — và kết quả loại bỏ hai trong ba phương án:**
>
> | Cách | Kết quả kiểm thật | Kết luận |
> |---|---|---|
> | 1. **Huỷ đăng ký sau mỗi phiên** | Trên B2 thì huỷ xong sạch trơn — nhưng **My Activities ở B4 vẫn giữ thẻ sự kiện kèm badge `Cancelled`** (`KS_B4_sau-huy.png`). P2 mở Profile ra vẫn thấy dấu vết của P1 | ❌ **Không trả về trạng thái sạch** |
> | 2. **Dựng 5 sự kiện riêng** | Sự kiện thì tách được, nhưng cả 5 người vẫn chung một tài khoản ⇒ **My Activities của P2 vẫn hiện đăng ký của P1** | ❌ Không giải quyết được gốc |
> | 3. **Tạo 5 tài khoản guest riêng** | Mỗi người một tài khoản, My Activities rỗng thật, QR riêng, dữ liệu tách bạch | ✅ **Cách duy nhất đúng** |
>
> **Khuyến nghị đã đổi: cách 3.** Trước đây tôi khuyên cách 2 khi chưa biết nút Cancel để lại dấu vết gì — giờ biết rồi thì cách 2 không đủ.
>
> **Cách 3 rẻ hơn vẻ ngoài của nó:** tài khoản demo `pvnduy23@clc.fitus.edu.vn` hiện có `Student ID` là **`G69FC9C62`** — tiền tố `G` cho thấy **nó vốn đã là một tài khoản Guest**, tức bạn đã biết đường tạo rồi. Tạo thêm 4 cái nữa qua `Create guest account` là việc lặp lại, khoảng 10–15 phút.
>
> - [ ] Tạo 4 tài khoản guest còn lại, đặt tên dễ nhận: `P2`…`P5`
> - [ ] Ghi lại 5 cặp email/mật khẩu vào **ghi chú cá nhân, KHÔNG ghi vào repo**
> - [ ] Với mỗi tài khoản: chụp `KS_B4_empty_P<n>.png` **trước** khi giao cho participant — ảnh này không chụp lại được sau khi họ đăng ký

**Còn cần kiểm:**
- [ ] Đăng nhập thử tài khoản demo một lần, xác nhận vào được và **thấy đúng vai trò gì** (Student? Guest?) → chụp `KS_LOGIN_tk-demo.png`
- [ ] Ảnh `admin-4.png` cho thấy công tắc **`Allow Guest Registration` — "Guests can register without an account"**. Nếu bật công tắc này thì **participant có thể đăng ký mà KHÔNG cần đăng nhập gì cả** — kiểm thử xem có đúng vậy không. Nếu đúng, đây là phương án sạch nhất cho Task 2 và làm luôn cả vấn đề dùng chung tài khoản biến mất.

### 5. ✅ ĐÃ XÁC MINH — QR CÓ THẬT, nhưng **không phải vé theo sự kiện**

Ảnh `check-in-profile.png` xác nhận: bấm nút **`QR Code`** ở góc phải trên trang **My Profile** → mở modal:

> **Check-in QR Code** · *(ảnh mã QR)* · `Student ID: 23127183` · nút **Download** (xanh) · nút `×` đóng

**Đây là phát hiện quan trọng nhất của cả buổi khảo sát**, vì nó khác hẳn hình dung ban đầu:

| Tôi/đề bài giả định | Thực tế trên EMS |
|---|---|
| Mỗi đăng ký sinh **một vé QR riêng** cho sự kiện đó | Chỉ có **một mã QR duy nhất cho cả tài khoản**, mã hoá **Student ID**, không gắn với sự kiện nào |
| Vé nằm trong "My Registrations", cạnh từng đăng ký | QR nằm ở **nút riêng trên đầu trang Profile**, tách rời hoàn toàn khỏi danh sách My Activities |
| "Xem vé của workshop X" | Không có khái niệm đó — cùng một mã dùng cho mọi sự kiện |

**Ba hệ quả — đều tốt cho bài:**

1. **Task 2 giữ nguyên được câu gốc** *"cho mình xem mã QR check-in của bạn"* — hợp lệ, vì QR có thật. Đã khôi phục câu này ở các file.
2. **Đây là một câu hỏi usability rất hay để quan sát:** participant vừa đăng ký xong sẽ **đi tìm vé ở đâu**? Nhiều khả năng họ tìm trong sự kiện hoặc trong danh sách đăng ký — chỗ đó **không có gì**. Phải mò lên Profile → nút QR Code. **Nếu ≥ 3/5 người bị kẹt ở đây thì đó là finding hệ thống hạng nặng**, đúng loại dữ liệu đề Task 2 muốn.
3. **Sinh ra một ứng viên finding mới** — xem `SV-B4-01` ở Phần 6.

**Còn cần kiểm:**
- [ ] Mã QR có **đổi theo thời gian / theo sự kiện** không, hay cố định vĩnh viễn? *(quét thử 2 lần cách nhau, hoặc so ảnh QR trước/sau khi đăng ký thêm sự kiện)* — nếu cố định vĩnh viễn thì còn là vấn đề **bảo mật**: ai chụp được màn hình QR là check-in hộ được
- [ ] Nút **Download** tải về file gì (PNG? PDF?), tên file có ý nghĩa không
- [ ] Ở bề rộng 375px, modal QR có hiển thị đủ và quét được không

---

## PHẦN 1 · Ghi nhận khi dựng sự kiện (admin)

Ảnh: `admin-1.png` (dashboard) · `admin-2.png` `admin-3.png` `admin-4.png` `admin-5.png` (form Create Event, cuộn từ trên xuống)

| Câu hỏi | Trả lời |
|---|---|
| **Trường bắt buộc (có dấu `*`)** | ✅ Đúng **8 trường**: `Event Title` · `Start Date & Time` · `End Date & Time` · `Check-in Open` · `Check-in Close` · `Registration Open` · `Registration Close` · `Campus` |
| **Trường KHÔNG bắt buộc** *(đáng chú ý)* | ✅ `Location` (chú thích *"Physical location or virtual link"*) · `Organizing Unit` · `Event Types` · `Academic Context` (ghi rõ *"optional"*) · `Sub-description` · `Description` · `Album Link` · `Reminder before hours` · Thumbnail · Banner · Attachments |
| Cấu trúc form (trên → dưới) | ✅ (1) **Thumbnail** + **Event Banner** · (2) **Attachments** + **Basic Information** · (3) **Date & Time** · (4) **Categories** · (5) **Registration** · (6) **Location & Organization** · (7) **Additional Options** · (8) 3 nút cuối |
| Upload ảnh | ✅ 2 khung riêng, đều có ô kéo-thả + nút camera tròn góc dưới phải · placeholder *"No thumbnail image"* / *"No banner image"* · chú thích **"Recommended ratio: 4:3"** và **"Recommended ratio: 24:9"** — khớp đúng tài liệu E2E |
| Attachments | ✅ *"Drag and drop files here or click to select"* · chú thích **"Supported any file format."** ⚠️ *(không nêu giới hạn dung lượng/số lượng — ứng viên finding, xem `SV-ADM-01`)* |
| Rich-text editor (`Description`) | ✅ 2 hàng thanh công cụ: hàng 1 — dropdown `P`, **B** *I* U S̶, màu chữ, highlight, x₂ x², căn lề, bullet list, numbered list, quote, đường kẻ ngang, xoá định dạng, link, ảnh, bảng · hàng 2 — dropdown cỡ chữ `16px`, Undo, Redo · có **tooltip** (ảnh bắt được tooltip "Subscript") |
| **Bật/tắt công tắc nào thì hiện thêm trường?** | ⬜ **CHƯA KIỂM** — 5 công tắc ở mục Registration đều đang TẮT trong ảnh. Cần bật từng cái xem hiện thêm gì (đặc biệt `Allow Waitlist` và `Allow Additional Role`) |
| Hệ thống có chặn khi thời gian không hợp lệ không? | ⬜ **CHƯA KIỂM** — cần cố tình nhập End < Start, Check-in Close < Check-in Open, Registration Close > End |
| Có bao nhiêu trạng thái sự kiện? Màu gì? | ✅ Phía user: **Upcoming** (tím) · **Ongoing** (xanh lá) · **Ended** (xám). Phía admin: có **`Save as Draft`** và **`Publish`** ⇒ tồn tại trạng thái DRAFT/PUBLISHED |
| Location để trống thì hiển thị gì? | ✅ Hiện dấu **`-`** (cả 4 workshop đều vậy) |

**5 công tắc mục Registration** ✅ *(đều mặc định TẮT)*

| Công tắc | Chú thích dưới nhãn |
|---|---|
| `Allow Student Registration` | *Students can register to attend* |
| `Allow Lecturer Registration` | *Lecturers can register to attend* |
| **`Allow Guest Registration`** | ***Guests can register without an account*** ← quan trọng cho Task 2, xem mục 4 |
| `Allow Waitlist` | *Allow students to join waitlist when full* |
| **`Public Event`** | ***Event is publicly visible*** ← giải thích vì sao B2 bị chặn, xem mục 1 |

**3 nút cuối form** ✅ `Save as Draft` (viền xám) · **`Publish`** (xanh đậm, nút chính) · `Preview Event` (viền xanh, full width, có icon con mắt)

**Dashboard admin** ✅ `admin-1.png` — sidebar 9 mục: Users Management · Categories · Academic Years · Campuses · Events Management · **Support requests** *(badge đỏ `17`)* · User Guide · Analytics *(có mũi tên xổ)* · Settings *(có mũi tên xổ)* · nút **Collapse** dưới cùng. 4 thẻ KPI: **Total Events** (xanh dương) · **Total Check-ins** (xanh lá) · **Attendance Rate** (tím, hiện `0%`) · **Total Users** (cam). Header: cờ ngôn ngữ · icon lưới · chuông · avatar `TLA`.

⚠️ **Cả 4 KPI đều bằng 0** trong khi hệ thống rõ ràng có sự kiện và người dùng → ứng viên finding `SV-ADM-02`.

---

## PHẦN 2 · Phía USER

### 2.0 · Màn đăng nhập ✅ `KS_LOGIN_trang-dang-nhap.png`

| Quan sát | Nội dung |
|---|---|
| Bố cục | 2 cột: trái là logo EMS + tên hệ thống, phải là card đăng nhập |
| Trường | `Email` và `Password`, **đều có dấu `*` đỏ** đánh dấu bắt buộc, có icon (phong bì / ổ khoá) |
| Widget | Nút **con mắt** hiện/ẩn mật khẩu · nút **Login** xanh full-width |
| Link phụ | `Forgot password?` · `Create guest account` |
| Đăng nhập ngoài | Dải "OR CONTINUE WITH" → 2 nút **LECTURER** (icon Google) · **STUDENT** (icon Microsoft) |
| i18n | Cờ Mỹ ở góc phải trên = công tắc ngôn ngữ, đang ở **EN** |
| Khác | Khối `Read user guides` · **nút share tròn nổi** góc phải dưới |

### 2.1 · B1 — Trang chủ / danh sách sự kiện ✅

Ảnh: `KS_B1_trang-chu-carousel.png` · `KS_B1_the-su-kien.png` · `KS_B1_empty-search.png` · `KS_B1_filters.png`

| Câu hỏi | Trả lời |
|---|---|
| Header có gì | ✅ `fit@hcmus` \| **EVENT MANAGEMENT SYSTEM** / *Faculty of Information technology* \| menu **Events · Calendar · Saved Events · User guide** \| cờ ngôn ngữ \| chuông thông báo \| avatar chữ viết tắt (`DPVN`) |
| Trang chủ có những khối nào (trên → dưới) | ✅ (1) Carousel **SPOTLIGHT EVENT** · (2) thanh `Events` + ô tìm kiếm + 3 tab + nút Filters · (3) sidebar trái Categories + Academic Context · (4) lưới thẻ sự kiện |
| Carousel hiển thị gì | ✅ Badge **SPOTLIGHT EVENT** + badge trạng thái · tiêu đề · mô tả · địa điểm + thời gian · link **View details →** |
| Carousel có tự xoay không? Mấy giây/lần? | ⬜ **CHƯA ĐO** — cần đứng yên 30 giây đếm |
| Bộ lọc/tìm kiếm có bao nhiêu control | ✅ Ô `Search events by title...` · 3 tab **Upcoming / Ongoing / Ended** · nút **Filters** · nút icon lọc phụ. Mở Filters ra có: **Event Date** (From/To, `dd/mm/yyyy`, có date-picker) · **Campus** (dropdown "All campuses") · **Registration available** (nút "All") |
| Sidebar có gì | ✅ **Categories**: Movement & Campaign…, Culture & Performing Arts, Physical Education & Sports, Volunteering & Community Service, Academic Competitions, Career Orientation… · **Academic Context**: Standard Program → 2025-2026 → Semester 1 / Semester 2 · nút **Collapse** |
| Empty state khi không có kết quả | ✅ Icon lịch có dấu ✕ + **"No events found"** + "There are no events matching your filters." — **KHÔNG có nút xoá bộ lọc / gợi ý hành động** → xem `SV-B1-02` |
| Thẻ sự kiện hiển thị gì | ✅ Ảnh · badge đếm ngược cam (`Opens in 4d 13h`) · badge trạng thái tím (`Upcoming`) · tên · tên phụ · **Event time** · **Location** · các tag · 2 ô **Lecturer** / **Student `0 / 30`** · nút **Save** |
| Widget nổi | ✅ Nút **share** tròn + nút **cuộn lên đầu trang** ở góc phải dưới |

### 2.2 · B2 — Trang chi tiết sự kiện ⭐ MÀN CHẤM ĐIỂM

Ảnh: 4 trạng thái đã có đủ — `chua-dang-nhap` · `workshop-a-con-cho` · `workshop-b-het-cho` · `workshop-c-dong-dang-ky` · thêm `su-kien-nguoi-khac` (có Important update).

| Câu hỏi | Trả lời |
|---|---|
| Các khối nội dung (trên → dưới) | ✅ (1) Tiêu đề + nút **Save event** · (2) *khối **Important update** nền hồng — chỉ hiện khi admin gửi* · (3) hàng **tag** · (4) 3 card **Event date** / **Registration period** / **Check-in period** · (5) 2 card **Location** / **Slot available** · (6) khối **Registration roles** |
| Nút hành động chính | ✅ **Save event** (góc phải trên). Nút đăng ký nằm trong khối **Registration roles** phía dưới, dạng **checkbox chọn vai trò** chứ không phải một nút "Đăng ký" đơn lẻ |
| Nhãn/trạng thái đổi thế nào ở 4 trạng thái | ✅ **Chưa đăng nhập** → chặn cả trang: "Please sign in to view this event." + nút `login`<br>✅ **Còn chỗ** → Slot available nền xanh, `Student: 49`<br>✅ **Hết chỗ** → Slot available **đổi sang nền hồng**, `Student: 0`, thêm chữ đỏ **"Role is full"**, checkbox vai trò bị vô hiệu<br>✅ **Đã đóng đăng ký** → banner cam **"Event registration period has ended"** |
| Khi hết chỗ có nói rõ "vào danh sách chờ" không? | ⚠️ **KHÔNG thấy ngay tại chỗ** — Workshop B có ô `Waitlisted 0` nhưng giao diện chỉ báo "Role is full". *Cập nhật 06/08: tài liệu chính thức §4.3 nói cơ chế đúng là — hệ thống âm thầm đưa vào waitlist, rồi gửi **Waitlist Invitation qua thông báo** khi có chỗ trống, người dùng vào thông báo bấm **Accept/Decline Invitation**. Vậy có thể KHÔNG PHẢI bug — có thể đúng thiết kế là "im lặng lúc đăng ký, báo sau qua thông báo". Vẫn cần kiểm: lúc BẤM ĐĂNG KÝ một role đã đầy, có dòng chữ nào xác nhận "bạn đã được đưa vào danh sách chờ" không, hay chỉ thấy role bị khoá không phản hồi gì?* → cập nhật lại `SV-B2-01` sau khi kiểm |
| Hiển thị số chỗ còn lại | ✅ Dạng **số** trong card `Slot available` → `Student: 49`. Trong khối Registration roles còn có `Registered 1/1`, `0/50` |
| Định dạng thời gian | ✅ `dd/MM/yyyy HH:mm` — ví dụ `25/08/2026 08:00`. **Không hiển thị múi giờ** |
| Đếm ngược | ✅ "Event starts in 1 day(s)" / "Event starts in 20 day(s)" / "Event is happening now" |
| Breadcrumb / nút quay lại danh sách | ⚠️ **KHÔNG thấy** trên cả 5 ảnh → xem `SV-B2-03` |
| Deep link khi chưa đăng nhập | ⚠️ Bị **chặn hoàn toàn**, không vào được nội dung |
| Sau khi đăng nhập có quay lại đúng sự kiện không? | ✅ **CÓ — về đúng sự kiện.** Dự đoán item `N-04` sẽ **Passed** *(vẫn phải tự chạy lại và chụp lúc làm Task 1B, không dùng dòng này thay bằng chứng)* |
| Bấm Back của trình duyệt | ✅ **Trở lại đúng cửa sổ/trang trước.** Dự đoán `N-03` Passed — ⬜ còn phải kiểm phần **giữ nguyên bộ lọc + vị trí cuộn** khi quay lại từ trang chi tiết |
| Nút **Cancel Registration** | ✅ **Hoạt động — huỷ xong không còn đăng ký nữa.** ⬜ Còn cần ghi: nút nằm ở đâu trên B2, **có dialog xác nhận không và nội dung dialog là gì** (đây mới là phần cho item `S-03`), sau khi huỷ My Activities cập nhật ngay hay phải tải lại → chụp `KS_B2_cancel-registration.png` |
| **Tệp đính kèm** + **Organizing Unit** ⚠️ *mới, theo tài liệu bảng "Xem chi tiết sự kiện"* | ⬜ **CHƯA KIỂM** — tài liệu liệt kê B2 còn có nhóm "Địa điểm: Location **và Organizing Unit**" (tôi mới chỉ ghi Location) và nhóm "Tệp đính kèm: tài liệu liên quan hoặc album link" — kiểm xem 2 sự kiện thử của mình có hiện các khối này không |
| Nút **Save/Saved** ⚠️ *mới, theo tài liệu mục 2.1* | ⬜ **CHƯA KIỂM** — B2 còn có tính năng lưu sự kiện (khác nút đăng ký), đổi trạng thái Save↔Saved. Đã thấy trên ảnh nhưng chưa test hành vi (click, toast, có đồng bộ với B1 không) |

### 2.3 · Khối đăng ký — **nằm trong B2, không phải màn hình riêng** ⭐ MÀN CHẤM ĐIỂM

> ✅ **Đã giải quyết ngày 06/08/2026 — và kết quả làm đổi cả bộ màn hình.** Mục này trước đây tên là *"B3 — Form đăng ký"*, viết dựa trên giả định rằng nút Đăng ký sẽ mở ra một form riêng. **Không có form riêng nào cả.** Việc chọn vai trò và bấm đăng ký diễn ra ngay trong khối `Registration roles` trên trang chi tiết sự kiện, **cùng URL** `/events/<id>`, không điều hướng, không tải lại trang.
>
> Hệ quả: bộ 3 màn hình đổi từ **B2/B3/B4** sang **B1/B2/B4**. Lý do đầy đủ ở [`KE_HOACH_HW03.md`](KE_HOACH_HW03.md) mục D2. Nhóm item `F-` không mất đi — nó vẫn nằm nguyên trong B2.
>
> Ảnh: `KS_B3_01_b2-truoc.png` · `KS_B3_02_form-rong.png` · `KS_B3_03_nut-disabled.png` · `KS_B3_05_sau-submit.png` *(tên file giữ tiền tố `KS_B3_` vì đã đặt trước khi phát hiện; nội dung là khối đăng ký trong B2)*.

> ✅ **Xác nhận từ tài liệu chính thức §4.2.2:** *"Student chỉ chọn đúng một role khi tham gia waitlist; giới hạn nhiều role chỉ áp dụng cho đăng ký thông thường nếu event cấu hình cho phép."* — khớp với ảnh (`Selected 0/1 student roles`). Cũng xác nhận 4 trạng thái đăng ký chính thức: **Approved · Pending Review · Rejected · Waitlisted** (đây là **thuật ngữ phía người đăng ký nhìn thấy**, khác với 4 ô đếm số `Registered/Pending/Confirmed/Waitlisted` tôi thấy trên trang chi tiết — hai bộ từ khác nhau cho hai chỗ khác nhau, kiểm xem có nhất quán không, khả năng là một item `S-04` finding thật).

Những gì **đã suy ra được** từ khối *Registration roles* trong ảnh Workshop B/C:

| Quan sát | Nội dung |
|---|---|
| Cấu trúc | ✅ Khối **Registration roles** + badge trạng thái (`Pending review`, vàng) + nhãn xanh **"Selected 0/1 student roles"** |
| Nhóm vai trò | ✅ **Student roles** — mỗi vai trò là một **checkbox** |
| Tên vai trò | ⚠️ **"Người dự"** — tiếng Việt, trong khi toàn bộ giao diện đang EN → lỗi i18n, xem `SV-B2-02` |
| Ô số liệu theo vai trò | ✅ Workshop B có **4 ô**: `Registered 1/1` · `Pending 1` (nền vàng) · `Confirmed 0` · `Waitlisted 0` (nền tím)<br>⚠️ Workshop C chỉ có **3 ô**, thiếu `Waitlisted` → số ô đổi theo cấu hình, xem `SV-B2-04` |
| Chặn khi hết chỗ | ✅ Chữ đỏ **"Role is full"** dưới nhóm ô |

**✅ Đã trả lời xong (06/08/2026)** — mỗi dòng là input cho ≥ 1 item `F-`:

| Câu hỏi | Kết quả thật |
|---|---|
| Bấm gửi khi **chưa tick vai trò** nào | **Không bấm được.** Nút `Register (Student)` bị **disabled xám** ngay từ đầu, kèm câu `Please tick a role before submitting registration.` in **màu chữ lỗi ngay khi vừa mở trang**, trước khi người dùng làm gì sai → `SV-B2-10` |
| Có bước **xác nhận** trước khi gửi không | **Không.** Tick vai trò → bấm là gửi thẳng |
| Sau khi gửi có **toast** không | **Không có toast, không có thông báo, không có chỉ dẫn gì.** Trang đứng yên tại chỗ, chỉ mọc thêm badge `Pending review` cạnh tiêu đề khối và nút `Cancel registration` ở cuối → `SV-B2-09` |
| Có nhắc tới **mã QR** hay bước tiếp theo không | **Không một chữ nào.** Đây là căn cứ trực tiếp cho tác vụ Task 2 |
| Trang có **reload** không, URL có đổi không | Không reload, không đổi URL — vẫn `/events/157`, giữ nguyên vị trí cuộn |
| Sau khi admin **approve** | Badge đổi sang `Approved` (xanh lá), có thông báo ở chuông — nhưng thông báo viết **tiếng Việt** trong giao diện tiếng Anh → `SV-NOTIF-01` |

**Còn lại chưa kiểm:**

- [ ] Workshop A đã bật **Allow Additional Role** — bật lên thì khối đăng ký hiện thêm gì?
- [ ] Nhấn **Tab** liên tục: thứ tự focus hợp lý? có thấy viền focus không? *(cho `F-13`, `F-14`)*
- [ ] Sau khi huỷ, **tick lại vai trò và bấm Register** thì chuyện gì xảy ra? *(đây là phần chưa rõ của `SV-B2-08` — giao diện mời đăng ký lại nhưng theo quan sát thì không được)*
- [ ] Nhấn **Esc**: có đóng modal/khối đang mở không?
- [ ] Validate fail xong, lựa chọn đã tick **có còn giữ** không?

### 2.4 · B4 — My Profile (QR Code + My Activities) ⭐ MÀN CHẤM ĐIỂM

Ảnh: `profile-1.png` (menu avatar) · `profile-2.png` (toàn trang) · `check-in-profile.png` (modal QR)

**Đường vào đã xác minh:**
```
Avatar (góc phải header) → View profile
```
✅ Menu avatar có đúng 4 mục: tên + email (`DUY PHẠM VŨ NGỌC` / `23127183@student.hcmus.edu...` — ⚠️ email bị **cắt cụt bằng `...`**, xem `SV-B4-02`) · **Support requests** · **View profile** · **Logout**.

**Cấu trúc trang My Profile — đã xác minh** ✅

| Khu vực | Nội dung |
|---|---|
| Tiêu đề + 3 nút góc phải | **My Profile** · nút **`QR Code`** · **`Edit Profile`** · **`Change Password`** |
| Thẻ hồ sơ | Avatar chữ viết tắt `DPVN` + nút camera nhỏ · tên **DUY PHẠM VŨ NGỌC** + badge **`Student`** (xanh) |
| 3 ô thông tin | **STUDENT ID** `23127183` · **EMAIL** `23127183@student.hcmus.edu.vn` · **PHONE** `Not updated` |
| 3 thẻ thống kê | **Registered Activities** `2` (xanh dương) · **Participated Activities** `0` (xanh lá) · **Upcoming Activities** `1` (tím) |
| Khối **My Activities** | Ô `Search activities...` · nút **`Filters`** · nút **`Export`** (xanh lá) |
| Mỗi thẻ hoạt động | Ảnh **"NO IMAGE"** (xám) · tiêu đề · **3 badge**: `Pending review` (hồng) + `Student participation` (tím) + `Upcoming`/`Ongoing` · khoảng thời gian + location `-` · **`Registered at:`** ngày giờ · **`Checked in at: Not checked in`** · **`ROLES:`** `Người dự` |
| Phân trang | `Rows per page: 10` · `1-2 of 2 results` · `Go to page __ / 1` · nút ‹ 1 › |

**Modal QR** ✅ tiêu đề **Check-in QR Code** · ảnh QR · dòng `Student ID: 23127183` · nút **Download** · nút `×`.

**4 quan sát nghi vấn thu được ngay từ ảnh này** *(đã đưa vào Phần 6)*:
- Ảnh sự kiện lại là placeholder **"NO IMAGE"** → củng cố `SV-B1-04` là lỗi **hệ thống**, không phải cá biệt
- `ROLES: Người dự` — tiếng Việt trong giao diện EN → củng cố `SV-B2-02`
- Location lại hiện `-` → củng cố `G-09`
- Bộ badge ở đây (`Pending review`, `Student participation`, `Upcoming`) **khác** bộ từ trong tài liệu chính thức (`Approved`/`Pending Review`/`Rejected`/`Waitlisted`) và **khác** 4 ô đếm trên B2 (`Registered`/`Pending`/`Confirmed`/`Waitlisted`) → **ba bộ từ vựng cho cùng một khái niệm trạng thái**, xem `SV-B4-03`

**Còn phải làm:**
- [ ] Tài khoản **chưa đăng ký gì** → My Activities hiện empty state gì → `KS_B4_empty.png` *(dùng tài khoản demo trước khi cho participant dùng)*
- [ ] Bấm **Export** — tải về file gì, nội dung có đủ cột không
- [ ] Bấm **Filters** — lọc được theo gì
- [ ] Thu cửa sổ xuống ~375px → thẻ hoạt động và modal QR có vỡ không → `KS_B4_mobile.png`
- [ ] Đăng ký Workshop B (hết chỗ + waitlist) → badge ở đây đổi thành gì

### 2.5 · B5 — Đánh giá sao

✅ Workshop D đã dựng (`KS_B2_workshop-d-da-ket-thuc.png`) — trang chi tiết sự kiện đã kết thúc **có khối `Rating summary`**: điểm `0.0` + số lượt `(0)`, kèm 5 thanh ngang từ `5 ★` xuống `1 ★`, mỗi thanh hiện `0 (0%)`.

- [ ] ⬜ Đây mới là **phần xem tổng hợp đánh giá**. Chỗ **gửi** đánh giá thì theo tài liệu §9 nằm ở **Profile → My Activities → nút đánh giá bên phải dòng sự kiện**, và chỉ hiện khi trạng thái là **Checked-in**. Tài khoản hiện đang `Not checked in` ⇒ **chưa test được** — cần admin check-in cho mình trước, hoặc chấp nhận đánh dấu N/A có lý do (B5 nằm ngoài phạm vi chấm nên không bắt buộc)

---

## PHẦN 3 · Phía ADMIN — danh mục widget

> Cần cho checklist dùng chung của nhóm. **Chưa có ảnh nào.**

| Nơi cần vào | Cần ghi | Xong |
|---|---|:--:|
| Dashboard admin | 4 chỉ số KPI tên gì | ⬜ |
| Events → Add Event | Upload mấy loại tỉ lệ ảnh · RichTextEditor có nút gì · cách chọn ngày giờ | ⬜ |
| Categories / Academic Contexts | **Kéo-thả reorder**: dòng đang kéo trông thế nào · icon picker bao nhiêu icon | ⬜ |
| Users | Các cột bảng · nút Export · dialog xác nhận hành động phá huỷ | ⬜ |
| Participants của sự kiện | Progress bar · số màu trạng thái · bộ lọc | ⬜ |
| Toàn cục | Toast ở góc nào, tự tắt sau bao lâu · dialog xác nhận mấy nút | ⬜ |

---

## PHẦN 4 · Tám phép thử xuyên suốt

| # | Phép thử | Kết quả |
|---|---|---|
| 1 | Chuyển EN/VI | ⚠️ **Đã thấy dấu hiệu lỗi:** giao diện đang EN nhưng tên vai trò hiện **"Người dự"** (tiếng Việt). Cần bấm công tắc và quét lại toàn màn hình để liệt kê đủ → ⬜ |
| 2 | i18n chỗ khuất (toast, tooltip, placeholder, lỗi) | ⬜ |
| 3 | Ngôn ngữ có được nhớ sau F5 | ⬜ |
| 4 | Text tiếng Việt dài hơn có vỡ nút không | ⬜ |
| 5 | Zoom 200% | ⬜ |
| 6 | Bề rộng 375px | ⬜ |
| 7 | Mạng chậm (DevTools → Slow 3G) | ⬜ |
| 8 | Lộ mã trạng thái nội bộ | ⬜ — nhưng đã thấy tên sự kiện dạng mã máy `23127326_UT_510_15:36` hiển thị làm tiêu đề chính, xem `SV-B1-03` |

---

## PHẦN 5 · DANH MỤC WIDGET — dán vào prompt AI ⭐

> Phần đã điền dựa trên ảnh. **Chỗ còn `___` phải bổ sung sau khi làm xong Phần 3** rồi mới dán vào AI.

```
Các widget THẬT tôi đã quan sát trên EMS ngày 05/08/2026:

TOÀN CỤC
- Header: logo + tên hệ thống 2 dòng · menu ngang 4 mục (Events, Calendar, Saved Events,
  User guide) · công tắc ngôn ngữ dạng CỜ QUỐC GIA (không phải chữ EN/VI) · chuông thông báo
  · avatar dạng chữ viết tắt 4 ký tự
- Nút nổi góc phải dưới: nút share tròn + nút cuộn lên đầu trang
- Định dạng thời gian toàn hệ thống: dd/MM/yyyy HH:mm, KHÔNG hiển thị múi giờ
- Giá trị rỗng hiển thị bằng dấu gạch ngang "-"

MÀN ĐĂNG NHẬP
- 2 trường Email/Password có dấu * đỏ đánh dấu bắt buộc, có icon trong ô
- Nút con mắt hiện/ẩn mật khẩu · nút Login full-width
- Đăng nhập ngoài: 2 nút LECTURER (Google) và STUDENT (Microsoft)
- Link phụ: Forgot password / Create guest account / Read user guides

B1 — TRANG CHỦ / DANH SÁCH
- Carousel "SPOTLIGHT EVENT" có badge trạng thái, mô tả, link View details
- Ô tìm kiếm theo tiêu đề + 3 tab lọc trạng thái (Upcoming/Ongoing/Ended)
- Panel Filters: 2 ô ngày dd/mm/yyyy có date-picker · dropdown Campus · nút Registration available
- Sidebar 2 nhóm cây phân cấp: Categories (~8 mục có icon màu) và
  Academic Context (Program → Năm học → Học kỳ), có nút Collapse
- Thẻ sự kiện: ảnh · badge đếm ngược cam · badge trạng thái tím · tên · Event time
  · Location · tag nhiều màu · 2 ô sức chứa Lecturer/Student dạng "0 / 30" · nút Save
- Empty state: icon lịch có dấu X + "No events found" + một câu giải thích,
  KHÔNG có nút hành động tiếp theo

B2 — CHI TIẾT SỰ KIỆN
- Chặn toàn trang khi chưa đăng nhập: card icon ổ khoá + "Please sign in to view this event."
  + nút "login" (chữ thường)
- Nút Save event ở góc phải trên
- Khối cảnh báo "Important update" nền hồng, chỉ hiện khi admin gửi
- Hàng tag nhiều màu: category (cam) · academic context (xanh dương) · campus (xanh lá)
- 3 card thời gian: Event date / Registration period / Check-in period, mỗi card có From-To
- Card Event date có dòng đếm ngược: "Event starts in N day(s)" / "Event is happening now"
- Card Slot available ĐỔI MÀU theo trạng thái: nền xanh khi còn chỗ, nền hồng khi hết chỗ
- Khối Registration roles: badge trạng thái (Pending review, vàng) + nhãn "Selected 0/1 student roles"
  + checkbox từng vai trò + nhóm ô số liệu (Registered / Pending / Confirmed / Waitlisted)
  + chữ đỏ "Role is full" khi đầy
- SỐ Ô SỐ LIỆU THAY ĐỔI theo cấu hình sự kiện: có Waitlist thì 4 ô, không có thì 3 ô
- Banner cam "Event registration period has ended" khi hết hạn đăng ký

KHỐI ĐĂNG KÝ (trong B2)
- ___ (chưa khảo sát: vị trí thông báo lỗi, bước xác nhận, toast sau khi gửi,
  vai trò phụ, thứ tự Tab, hành vi Esc)

B4 — MY REGISTRATIONS + VÉ QR
- ___ (chưa khảo sát: đường vào, empty state, badge trạng thái, dạng mã check-in,
  dialog huỷ đăng ký)

PHÍA ADMIN
- ___ (chưa khảo sát: upload ảnh, rich-text, kéo-thả reorder, icon picker,
  progress bar, toast, dialog xác nhận)

HÀNH VI ĐẶC THÙ ĐÁNG CHÚ Ý
- Trang chi tiết sự kiện KHÔNG xem được khi chưa đăng nhập
- Tên vai trò hiển thị tiếng Việt ("Người dự") ngay cả khi giao diện đang tiếng Anh
- Carousel SPOTLIGHT đang hiển thị một sự kiện đã ở trạng thái "Ended"
- Nhiều thẻ sự kiện không có ảnh, hiện ô placeholder xám
```

---

## PHẦN 6 · Quan sát nghi vấn → đã thành finding chính thức

> ✅ **Cập nhật 06/08/2026:** 27 quan sát dưới đây **đã được chuyển hết** sang [`../23127183_HW03_AI_GUIUsability_EMS_100/04-findings-log.md`](../23127183_HW03_AI_GUIUsability_EMS_100/04-findings-log.md) với đủ 9 cột, kèm severity đề xuất và ảnh trong `evidence/survey/`.
>
> 🔴 **File findings log là nguồn duy nhất — bảng dưới đây chỉ giữ lại để tra nhanh.** Nếu sửa nội dung finding thì sửa ở findings log, không sửa ở đây, tránh hai bản lệch nhau.

| ID | Màn | Quan sát | Nghi ngờ vi phạm | Ảnh hiện có |
|---|---|---|---|---|
| `SV-B1-01` | B1 | Carousel **SPOTLIGHT EVENT** đang hiển thị sự kiện có badge **"Ended"** | N1 — sự kiện đã kết thúc thì không nên chiếm chỗ nổi bật nhất trang chủ. *(Tài liệu E2E ghi carousel chỉ nên hiện PUBLISHED + UPCOMING/ONGOING)* | `KS_B1_trang-chu-carousel.png` |
| `SV-B1-02` | B1 | Empty state chỉ có chữ "No events found", **không có nút xoá bộ lọc** | N1, N3 — người dùng lọc nhầm phải tự mò cách quay lại | `KS_B1_empty-search.png` |
| `SV-B1-03` | B1/B2 | Tiêu đề sự kiện hiển thị **mã máy** `23127326_UT_510_15:36`, tên thật nằm ở dòng phụ | N2 — ngôn ngữ hệ thống lấn át ngôn ngữ người dùng | `KS_B2_su-kien-nguoi-khac.png` |
| `SV-B1-04` | B1 | Nhiều thẻ sự kiện hiện **ô ảnh placeholder xám**, không có ảnh | N1, N8 | `KS_B1_the-su-kien.png` |
| `SV-B2-01` | B2 | Hết chỗ: chỉ báo **"Role is full"**, **không có lời mời vào danh sách chờ** dù ô `Waitlisted` tồn tại | N1, N3 — người dùng không biết mình còn lựa chọn nào | `KS_B2_workshop-b-het-cho.png` |
| `SV-B2-02` | B2 | Tên vai trò **"Người dự"** hiện tiếng Việt trong giao diện tiếng Anh | N4 — i18n không nhất quán | `KS_B2_workshop-b-het-cho.png` |
| `SV-B2-03` | B2 | **Không có breadcrumb / nút quay lại danh sách** | N3 — user control & freedom | cả 4 ảnh B2 |
| `SV-B2-04` | B2 | Số ô số liệu vai trò **đổi giữa các sự kiện** (4 ô có Waitlisted vs 3 ô không) | N4 — bố cục không ổn định giữa các trang cùng loại | `workshop-b` vs `workshop-c` |
| `SV-B2-05` | B2 | Màn chặn chưa đăng nhập: nút ghi **`login`** chữ thường, lệch với các nút khác Title Case | N4 | `KS_B2_chua-dang-nhap.png` |
| `SV-B2-06` | B2 | Workshop B **thiếu tag category và academic context**, chỉ còn tag campus | N1 | `KS_B2_workshop-b-het-cho.png` |
| `SV-B4-01` | B4 | ⭐ **Mã QR check-in nằm ở nút riêng trên đầu trang Profile, tách hoàn toàn khỏi danh sách đăng ký.** Vừa đăng ký xong, ở ngay chỗ đăng ký lẫn trong My Activities đều **không có đường dẫn nào tới vé** | N1, N6, N3 — người dùng phải **nhớ** rằng QR nằm ở Profile chứ không được hệ thống chỉ đường. Đây là ứng viên finding **severity cao nhất** hiện có, và là thứ 5 phiên user testing sẽ đo được trực tiếp | `check-in-profile.png` · `profile-2.png` |
| `SV-B4-02` | B4 | Email trong menu avatar bị **cắt cụt** thành `23127183@student.hcmus.edu...` dù còn chỗ trống | N1, S8 | `profile-1.png` |
| `SV-B4-03` | B2 + B4 | **Ba bộ từ vựng khác nhau cho cùng khái niệm trạng thái đăng ký:** tài liệu chính thức dùng `Approved/Pending Review/Rejected/Waitlisted` · trang B2 dùng 4 ô đếm `Registered/Pending/Confirmed/Waitlisted` · thẻ trong My Activities dùng badge `Pending review/Student participation/Upcoming` | N4, S1 — người dùng không map được ba bộ từ này với nhau | `profile-2.png` vs `KS_B2_workshop-b-het-cho.png` |
| `SV-B4-04` | B4 | Mã QR **cố định theo Student ID, không đổi theo sự kiện** ⇒ ai chụp được màn hình QR là **check-in hộ được** ở mọi sự kiện. ⬜ *cần xác nhận QR có xoay vòng theo thời gian không rồi mới kết luận* | N5 (error prevention) — nếu đúng là cố định vĩnh viễn thì đây là vấn đề **bảo mật**, không chỉ usability | `check-in-profile.png` |
| `SV-ADM-01` | Admin | Ô Attachments ghi **"Supported any file format."** nhưng **không nêu giới hạn dung lượng hay số lượng file** trước khi người dùng chọn | N5, P3 | `admin-2.png` `admin-3.png` |
| `SV-ADM-02` | Admin | 4 KPI trên Admin Dashboard đều hiện **0** (Total Events 0, Total Check-ins 0, Attendance Rate 0%, Total Users 0) trong khi hệ thống rõ ràng đang có sự kiện và người dùng | N1 — chỉ số sai làm mất niềm tin vào toàn bộ trang thống kê | `admin-1.png` |

⚠️ **Việc còn lại với các finding này:** khi chạy Task 1B, mỗi item checklist bị Failed mà trùng nội dung với một finding `SV-` thì ghi ở cột Notes là *"= SV-xxx"* và **không tạo ID `CL-` mới, không submit Google Form lần hai** — nếu không thì số dòng trong findings log sẽ vượt số lần submit và TA thấy lệch.

---

## Việc còn lại của buổi khảo sát

Ước tính **~35 phút** nữa là xong. Ba đợt khảo sát đã giải quyết phần lớn danh sách này.

- [x] ✅ **Mục 5 — mã QR**: có thật, nằm ở nút riêng đầu trang Profile, cố định theo tài khoản — xong 06/08
- [ ] 🔴 **Mục 4 — tạo thêm 4 tài khoản guest** cho P2…P5 qua `Create guest account` — 15' · **đây là việc chặn Task 2**
- [x] ✅ Dựng **Workshop D** (`ENDED`) — xong
- [x] **Khối đăng ký trong B2**: đã chạy, 4 ảnh — xong 06/08
- [x] ✅ **B4**: đã chụp đủ (empty state, QR, sau huỷ, Filters, Export) — xong 06/08
- [ ] **Phần 3 admin**: 6 nơi, chụp 6 ảnh — 15'
- [ ] **Phần 4**: chạy 8 phép thử — 10'
- [ ] Điền nốt các chỗ `___` ở Phần 5
- [x] ✅ Chốt email: `23127183@student.hcmus.edu.vn`
- **Commit:** `docs(task1a): add EMS survey notes, widget inventory and test fixtures`
