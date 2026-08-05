# PHIẾU KHẢO SÁT EMS — đã điền một phần từ ảnh chụp

**Người khảo sát:** Phạm Vũ Ngọc Duy (23127183) · **Ngày:** 05/08/2026 · **Giờ:** ~17:35 → 18:35
**SUT:** https://prod-dev.ems-fitus.cloud
**Tài khoản EMS đã dùng:** `23127183@student.hcmus.edu.vn` (đăng nhập qua nút **STUDENT**) · avatar hiển thị `DPVN`

> **Tình trạng:** đã có **10 ảnh** trong `docs/khao-sat/`. Những ô có ✅ là **đã xác nhận từ ảnh**. Những ô có ⬜ là **chưa kiểm — bạn phải tự vào EMS xem tiếp**.
> Đừng bỏ qua các ô ⬜: phần lớn nhóm item `F-` (form) và `S-` (feedback/state) phụ thuộc vào chúng.

---

## ⚠️ BA VIỆC PHẢI XỬ LÝ TRƯỚC KHI ĐI TIẾP

### 1. B2 KHÔNG phải màn hình công khai — kế hoạch Task 2 & 3 phải đổi

Ảnh `KS_B2_chua-dang-nhap.png` cho thấy mở deep link tới sự kiện khi chưa đăng nhập thì chỉ hiện:

> 🔒 **Please sign in to view this event.** — nút `login`

Hệ quả:

| Nơi bị ảnh hưởng | Trước đây tôi ghi | Thực tế |
|---|---|---|
| Task 3 cross-platform | "B2 công khai, không cần đăng nhập ⇒ chạy nhanh" | **Sai.** Cả B2, B3, B4 đều cần đăng nhập ⇒ **phải đăng nhập lại ở TỪNG ô** BrowserStack (~7 ô × 3 màn). Tính thêm thời gian |
| Task 2 user testing | Participant vào thẳng link sự kiện | **Phải tạo tài khoản + đăng nhập trước**, rồi mới bắt đầu bấm giờ |

→ Tôi đã sửa lại các file kế hoạch cho khớp.

### 2. Bạn đang có HAI email — cần chốt dùng cái nào cho bài

| Email | Dùng ở đâu | Khớp mẫu đề `MSSV@....edu.vn`? |
|---|---|:--:|
| `23127183@student.hcmus.edu.vn` | Đăng nhập EMS (ảnh `KS_LOGIN_trang-dang-nhap.png`) | ✅ có chứa MSSV |
| `pvnduy23@clc.fitus.edu.vn` | Đang ghi trong bài làm để nộp form + overlay ảnh | ❌ **không chứa MSSV** |

Đề §7 và §12 yêu cầu **`MSSV@....edu.vn`**. Cái thứ nhất khớp mẫu, cái thứ hai không. **Hỏi TA hoặc nhóm Zalo** xem chấp nhận email `@clc.fitus.edu.vn` không — nếu không thì phải đổi toàn bộ sang `23127183@student.hcmus.edu.vn` (form + overlay ảnh Task 3). Tôi chưa tự đổi vì bạn đã chốt email kia.

- [ ] Đã hỏi và chốt: dùng email `________________`

### 3. Dữ liệu thử mới dựng được 3/4

| # | Sự kiện | Trạng thái | Ảnh |
|---|---|---|---|
| 1 | `[23127183] Workshop A — con cho` | ✅ đã dựng · Slot Student **49** · "Event starts in 1 day(s)" | `KS_B2_workshop-a-con-cho.png` |
| 2 | `[23127183] Workshop B — het cho` | ✅ đã dựng · Slot **0** · "Role is full" · Registered **1/1** | `KS_B2_workshop-b-het-cho.png` |
| 3 | `[23127183] Workshop C — dong dang ky` | ✅ đã dựng · "Event registration period has ended" | `KS_B2_workshop-c-dong-dang-ky.png` |
| 4 | `[23127183] Workshop D — da ket thuc` | ⬜ **CHƯA DỰNG** — cần cho badge trạng thái ở B4 và màn đánh giá B5 | — |

---

## PHẦN 1 · Ghi nhận khi dựng sự kiện (admin)

| Câu hỏi | Trả lời |
|---|---|
| Form tạo sự kiện có những trường bắt buộc nào? | ⬜ chưa ghi |
| Bật/tắt công tắc nào thì form hiện thêm trường? | ⬜ chưa ghi |
| Hệ thống có chặn khi thời gian không hợp lệ không? Báo lỗi ra sao? | ⬜ chưa ghi |
| Có bao nhiêu trạng thái sự kiện? Màu gì? | ✅ Quan sát được ở phía user: **Upcoming** (tím) · **Ongoing** · **Ended** (xám). Phía admin ⬜ chưa ghi (DRAFT/PUBLISHED) |
| Location để trống thì hiển thị gì? | ✅ Hiện dấu **`-`** (cả 3 workshop A/B/C đều vậy vì không nhập location) |

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
| Khi hết chỗ có nói rõ "vào danh sách chờ" không? | ⚠️ **KHÔNG.** Workshop B có ô `Waitlisted 0` (⇒ Waitlist có bật) nhưng giao diện chỉ báo "Role is full", **không có lời mời/nút vào danh sách chờ** → xem `SV-B2-01` |
| Hiển thị số chỗ còn lại | ✅ Dạng **số** trong card `Slot available` → `Student: 49`. Trong khối Registration roles còn có `Registered 1/1`, `0/50` |
| Định dạng thời gian | ✅ `dd/MM/yyyy HH:mm` — ví dụ `25/08/2026 08:00`. **Không hiển thị múi giờ** |
| Đếm ngược | ✅ "Event starts in 1 day(s)" / "Event starts in 20 day(s)" / "Event is happening now" |
| Breadcrumb / nút quay lại danh sách | ⚠️ **KHÔNG thấy** trên cả 5 ảnh → xem `SV-B2-03` |
| Deep link khi chưa đăng nhập | ⚠️ Bị **chặn hoàn toàn**, không vào được nội dung |
| Sau khi đăng nhập có quay lại đúng sự kiện không? | ⬜ **CHƯA KIỂM** — bấm nút `login` ở màn chặn rồi xem có về đúng trang sự kiện không. Đây là item `N-` quan trọng |
| Bấm Back của trình duyệt | ⬜ **CHƯA KIỂM** |

### 2.3 · B3 — Form đăng ký ⭐ MÀN CHẤM ĐIỂM

> ⚠️ **Đây là màn hình yếu nhất về dữ liệu khảo sát.** Chưa có ảnh nào chụp lúc form ở trạng thái điền/lỗi. Mà B3 gánh gần hết nhóm item `F-` (≥ 12 item) — thiếu phần này thì checklist sẽ hỏng nặng nhất ở đúng chỗ đề chấm kỹ.

Những gì **đã suy ra được** từ khối *Registration roles* trong ảnh Workshop B/C:

| Quan sát | Nội dung |
|---|---|
| Cấu trúc | ✅ Khối **Registration roles** + badge trạng thái (`Pending review`, vàng) + nhãn xanh **"Selected 0/1 student roles"** |
| Nhóm vai trò | ✅ **Student roles** — mỗi vai trò là một **checkbox** |
| Tên vai trò | ⚠️ **"Người dự"** — tiếng Việt, trong khi toàn bộ giao diện đang EN → lỗi i18n, xem `SV-B2-02` |
| Ô số liệu theo vai trò | ✅ Workshop B có **4 ô**: `Registered 1/1` · `Pending 1` (nền vàng) · `Confirmed 0` · `Waitlisted 0` (nền tím)<br>⚠️ Workshop C chỉ có **3 ô**, thiếu `Waitlisted` → số ô đổi theo cấu hình, xem `SV-B2-04` |
| Chặn khi hết chỗ | ✅ Chữ đỏ **"Role is full"** dưới nhóm ô |

**Còn phải làm** — mỗi dòng dưới đây là input cho ≥ 1 item `F-`:

- [ ] Tick vai trò rồi bấm nút gửi → chụp `KS_B3_form-da-chon.png`
- [ ] **Bấm gửi khi CHƯA tick vai trò nào** → lỗi hiện ở đâu? câu chữ gì? → chụp `KS_B3_loi-bo-trong.png`
- [ ] Có bước **xác nhận** trước khi gửi không? → chụp `KS_B3_xac-nhan.png`
- [ ] Sau khi gửi: có **toast** không? nội dung? nằm góc nào? tự tắt sau bao lâu?
- [ ] Workshop A đã bật **Allow Additional Role** — bật lên thì form hiện thêm gì?
- [ ] Nhấn **Tab** liên tục: thứ tự focus hợp lý? có thấy viền focus không?
- [ ] Nhấn **Esc**: có đóng modal/khối đang mở không?
- [ ] Validate fail xong, lựa chọn đã tick **có còn giữ** không?

### 2.4 · B4 — My Registrations + vé QR ⭐ MÀN CHẤM ĐIỂM

> ⚠️ **Chưa có ảnh nào.** Cần cả 4 trạng thái dưới đây — đặc biệt **empty state** và **mã QR**, vì đó là hai thứ gánh nhóm item `S-` và là tiêu chí "hoàn thành" của Task 2.

- [ ] Tìm đường vào màn này (menu avatar? `Saved Events`? mục riêng?) → ghi lại đường dẫn: `________`
- [ ] Tài khoản **chưa đăng ký gì** → empty state hiện gì → `KS_B4_empty.png`
- [ ] Sau khi đăng ký Workshop A và B → `KS_B4_danh-sach.png`
- [ ] Mở chi tiết một đăng ký → tìm **mã QR/barcode** → `KS_B4_ve-qr.png`
- [ ] So sánh badge: Workshop A (`Pending`?) vs Workshop B (`Waitlisted`?) — màu và chữ khác nhau thế nào?
- [ ] Thu cửa sổ xuống ~375px → mã QR có méo/cắt không → `KS_B4_mobile.png`
- [ ] Có huỷ đăng ký được không? Có dialog xác nhận không? Nội dung dialog?

### 2.5 · B5 — Đánh giá sao

- [ ] Cần Workshop D (`ENDED`) — **chưa dựng**. Dựng xong rồi mở xem có phần đánh giá không → `KS_B5_danh-gia.png`

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

> Phần đã điền dựa trên ảnh. **Chỗ còn `___` phải bổ sung sau khi làm xong B3, B4 và Phần 3** rồi mới dán vào AI.

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

B3 — FORM ĐĂNG KÝ
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

## PHẦN 6 · Quan sát nghi vấn — kiểm chứng lại ở Task 1B

> Chưa kết luận đúng/sai. Ảnh gốc đang ở `docs/khao-sat/`; khi nào xác nhận thành finding thật thì **chụp lại trong lúc chạy checklist** và lưu vào `evidence/task1b/`.

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

⚠️ **Quan trọng:** 10 dòng trên **chưa phải finding chính thức**. Trước khi đưa vào `04-findings-log.md` phải: (1) tái hiện lại được, (2) chụp ảnh mới trong lúc chạy checklist, (3) đối chiếu xem có phải là item checklist nào bị Failed không.

---

## Việc còn lại của buổi khảo sát

Ước tính **~35 phút** nữa là xong.

- [ ] Dựng **Workshop D** (`ENDED`) — 5'
- [ ] **B3**: chạy 8 thao tác ở mục 2.3, chụp 3 ảnh — 12'
- [ ] **B4**: tìm đường vào, chụp 4 ảnh (đặc biệt **empty state** và **mã QR**) — 10'
- [ ] **Phần 3 admin**: 6 nơi, chụp 6 ảnh — 15'
- [ ] **Phần 4**: chạy 8 phép thử — 10'
- [ ] Điền nốt các chỗ `___` ở Phần 5
- [ ] Chốt việc chọn email (mục ⚠️ số 2 đầu file)
- **Commit:** `docs(task1a): add EMS survey notes, widget inventory and test fixtures`
