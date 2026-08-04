# [BẢN CHUẨN HOÁ] KỊCH BẢN E2E TEST FLOW — LUỒNG ADMIN

> **Nguồn:** `Kịch-bản-E2E-Test-Flow-Luồng-Admin.md`.
> File gốc **đã là tiếng Việt**, nên đây không phải bản dịch mà là **bản chuẩn hoá để chạy được**: giữ nguyên 100% nội dung yêu cầu, thêm mã test case, checkbox thao tác, và bảng ghi kết quả (Actual / Pass-Fail / Bug-ID / Ảnh).
> **Trạng thái: ĐÃ CHẠY XONG.** Giữ lại làm tham chiếu — các finding thu được nằm ở `04-findings-log.md` với prefix `E2E-`, và bộ sự kiện dựng ra trong lượt này là dữ liệu thử cho kịch bản B.

**WEB:** https://prod-dev.ems-fitus.cloud _(link ngrok ghi trong file gốc đã ngừng hoạt động — đã thay bằng link hiện hành)_
**LƯU Ý:** Tài khoản dùng để test phải có role **ADMIN** trên hệ thống EMS.
**Tài khoản:** `admin@gmail.com` | **Mật khẩu:** `Admin@123`
**Mã luồng test:** `TC_E2E_ADMIN`
**Nộp kết quả:** điền bảng E2E Test Flow → gửi về https://forms.gle/CJQFQCAXcsDbXDMM9
**Nhóm hỗ trợ:** https://zalo.me/g/rupogxlykt3yxd3snodl

**Mục tiêu:** Kiểm thử toàn diện và chi tiết các chức năng quản trị — từ quản lý dữ liệu nền, quản lý người dùng, toàn bộ vòng đời sự kiện (đặc biệt các ràng buộc về validation), xử lý check-in phức tạp, giải quyết Support Requests, đến trích xuất báo cáo chuyên sâu.

---

## Bảng theo dõi kết quả tổng (điền trong lúc chạy)

| Mã | Bước | Giai đoạn | Pass/Fail | Bug-ID | Ảnh bằng chứng |
|---|---|---|:--:|---|---|
| E2E-01 | Đăng nhập & Dashboard | 1 | | | |
| E2E-02 | Quản lý Người dùng | 1 | | | |
| E2E-03 | Dữ liệu nền (Contexts/Categories/Campuses) | 2 | | | |
| E2E-04 | Tạo sự kiện & Validation thời gian | 3 | | | |
| E2E-05 | Cấu hình Đăng ký / Roles / Waitlist | 3 | | | |
| E2E-06 | Publish / Important Update / Delete | 3 | | | |
| E2E-07 | Duyệt Participants & Reviews | 4 | | | |
| E2E-08 | Xử lý Support Requests | 4 | | | |
| E2E-09 | Check-in đa kịch bản | 5 | | | |
| E2E-10 | Analytics & Reviews | 6 | | | |
| E2E-11 | Settings (Featured / Social / System) | 6 | | | |

**Tổng:** ___ / 11 bước Pass · ___ bug phát hiện

---

## GIAI ĐOẠN 1: THIẾT LẬP HỆ THỐNG VÀ QUẢN LÝ NGƯỜI DÙNG

### E2E-01 · Bước 1: Đăng nhập & Kiểm tra Dashboard

**Hành động:**
- [ ] Truy cập hệ thống → Đăng nhập bằng tài khoản Admin
- [ ] Thử chuyển đổi ngôn ngữ **EN/VI** trên thanh header
- [ ] Thử bấm nút **"Quay lại Dashboard người dùng"**

**Kết quả mong đợi:**
- Đăng nhập thành công, chuyển hướng được qua lại giữa Dashboard quản trị và giao diện người dùng.
- Hiển thị **4 thông số tổng quan**: Total Events, Total Checkins, Attendance Rate, Total Users.
- Ngôn ngữ thay đổi **tức thì** và **được lưu lại**.

**Actual:**
> _(điền sau khi chạy)_

---

### E2E-02 · Bước 2: Quản lý Người dùng (Users)

**Hành động:** Truy cập **Users** từ thanh bên.
- [ ] Thử **Assign Role** (đổi vai trò tài khoản thành giảng viên / sinh viên)
- [ ] Thử **Block / Unblock** một tài khoản đang hoạt động
- [ ] Thử **Reset Password** cho một tài khoản
- [ ] Bấm **Export** xuất danh sách ra file Excel

**Kết quả mong đợi:**
- Thao tác thành công. Tài khoản bị **Block không thể truy cập** hệ thống.
- Các thay đổi được ghi nhận trong **audit log**.
- File Excel tải xuống đầy đủ các cột: **Avatar + Name, Role, Member Code, Active, Audit**.

**Actual:**
> _(điền sau khi chạy)_

---

## GIAI ĐOẠN 2: QUẢN LÝ DỮ LIỆU NỀN (CATEGORIES, CONTEXTS, CAMPUSES)

### E2E-03 · Bước 3: Khởi tạo & Ràng buộc dữ liệu nền

**Hành động:**
- **Academic Contexts:**
  - [ ] Tạo cấu trúc **3 cấp** (Program → Year → Semester)
  - [ ] Dùng chuột **kéo thả (Reorder)** để đổi thứ tự
  - [ ] Thử tạo nhanh danh mục con từ chính dòng cha
- **Categories:**
  - [ ] Tạo danh mục **cha** và **con**
  - [ ] Chọn Icon từ bộ **Icon Picker (~80 icon)**
  - [ ] Thử kéo thả reorder danh mục cha và con **độc lập** với nhau
- **Campuses:**
  - [ ] Tạo cơ sở mới
  - [ ] Thử **xóa một Campus đang được tham chiếu** bởi một sự kiện đã có trong hệ thống

**Kết quả mong đợi:**
- Tính năng **kéo-thả (Reorder)** hoạt động mượt: dòng đang kéo bị mờ (`opacity-50`), các nút khác bị vô hiệu hóa; lưu **đúng thứ tự** sau khi Save.
- **Hệ thống chặn (báo lỗi) không cho xóa** Campus / Category / Academic Context nếu đang được sự kiện tham chiếu — chỉ có thể tắt cờ `isEnabled`.

**Actual:**
> _(điền sau khi chạy)_

---

## GIAI ĐOẠN 3: TẠO VÀ CẤU HÌNH SỰ KIỆN CHUYÊN SÂU

### E2E-04 · Bước 4: Tạo sự kiện & Validation Thời gian

**Hành động:** Vào **Events** → bấm **Add Event**.
- [ ] Tải lên **Thumbnail (4:3)** và **Banner (24:9)**
- [ ] Soạn Content bằng **RichTextEditor**
- [ ] Tại mục DateTime, **cố tình nhập sai logic**:
  - [ ] Ngày kết thúc sự kiện **trước** ngày bắt đầu
  - [ ] Thời gian đóng đăng ký **sau khi** sự kiện kết thúc

**Kết quả mong đợi:**
- Upload ảnh thành công, preview rõ nét.
- Hệ thống **bắt lỗi validation (báo đỏ)**, **không cho phép lưu** nếu ràng buộc thời gian không hợp lý.

**Actual:**
> _(điền sau khi chạy)_

---

### E2E-05 · Bước 5: Cấu hình Đăng ký, Vai trò (Roles) & Waitlist

**Hành động:** Tại form tạo sự kiện:
- [ ] Bật **allowStudentRegistration**, **allowLecturerRegistration**, **allowGuestRegistration**
- [ ] Tắt **isUnlimited** (cho phép không giới hạn) → **cố tình không nhập Max Slots** rồi bấm lưu
- [ ] Sau đó nhập Max Slots **cho từng vai trò**
- [ ] Bật công tắc **Waitlist** (danh sách chờ)
- [ ] Bật **Allow Additional Role** (vai trò phụ) và nhập tên

**Kết quả mong đợi:**
- Form **hiển thị động** đúng theo từng công tắc.
- Hệ thống **chặn Publish** nếu thiếu Max Slots khi `isUnlimited = false`.

**Actual:**
> _(điền sau khi chạy)_

---

### E2E-06 · Bước 6: Phát hành, Cập nhật quan trọng & Xóa sự kiện

**Hành động:**
- [ ] Bấm **Save Draft** → kiểm tra list có trạng thái **DRAFT**
- [ ] Bấm **Edit** → **Publish**; bấm **Preview** xem trước
- [ ] Nhấn nút **Important Update**, nhập nội dung đổi địa điểm và gửi
- [ ] Thử **Delete** sự kiện **đã có người đăng ký**

**Kết quả mong đợi:**
- Sự kiện chuyển sang **PUBLISHED**.
- Cảnh báo **Important Update** xuất hiện và **gửi thông báo tới người đăng ký**.
- Hệ thống **chặn việc xóa** sự kiện nếu đã có dữ liệu đăng ký quan trọng.

**Actual:**
> _(điền sau khi chạy)_

---

## GIAI ĐOẠN 4: DUYỆT ĐĂNG KÝ VÀ XỬ LÝ YÊU CẦU HỖ TRỢ

### E2E-07 · Bước 7: Phê duyệt danh sách đăng ký (Participants & Reviews)

**Hành động:**
- [ ] Tìm sự kiện có **chấm đỏ** thông báo trên icon View → mở tab **Lecturer/Student Review**
- [ ] Duyệt **Approve / Reject** một số đăng ký
- [ ] **Bẫy có chủ đích:** cố tình chỉ duyệt **1 role** trong đăng ký giảng viên có nhiều role rồi bấm **Apply**; sau đó quyết định **hết** các role rồi Apply lại
- [ ] Thử tính năng **Approve All**
- [ ] Vào tab **Participants**: kiểm tra **màu sắc trạng thái** (Xanh lá, Vàng, Đỏ, Xanh dương, Tím, Xám) và bộ lọc **Target Type**
- [ ] Thử **Export** file Excel

**Kết quả mong đợi:**
- **Progress bar** cập nhật đúng.
- **Phải duyệt/từ chối TẤT CẢ các role** của một giảng viên trong cùng 1 đăng ký thì mới được Apply.
- File Excel danh sách người tham gia xuất ra chuẩn xác.

**Actual:**
> _(điền sau khi chạy)_

---

### E2E-08 · Bước 8: Xử lý Support Requests

**Hành động:**
- [ ] Vào **Support requests** trên sidebar. Lọc theo tab **Pending**; search theo **mã số thành viên** hoặc **Category**
- [ ] Bấm vào một request để xem; kiểm tra **ảnh đính kèm (lightbox)**
- [ ] Nhập **Internal note** (ghi chú nội bộ) và **nội dung phản hồi chính thức** → bấm **Gửi phản hồi**
- [ ] Ra ngoài danh sách, chuyển sang tab **Resolved** kiểm tra

**Kết quả mong đợi:**
- Request chuyển từ **PENDING → RESOLVED**.
- Phản hồi được lưu và **thông báo cho người dùng**; **internal note chỉ Admin nhìn thấy**.

**Actual:**
> _(điền sau khi chạy)_

---

## GIAI ĐOẠN 5: VẬN HÀNH CHECK-IN ĐA KỊCH BẢN

### E2E-09 · Bước 9: Test luồng quét Barcode / Mã số (tab Checkin)

**Hành động:** Vào tab **Checkin**, lần lượt test các kịch bản:
- [ ] Quét mã **hợp lệ** → trả về **SUCCESS**
- [ ] **Quét lại** mã vừa quét → trả về **ALREADY_CHECKED_IN**
- [ ] **Đổi giờ hệ thống** để quét ngoài khung giờ → trả về **OUTSIDE_CHECKIN_WINDOW**
- [ ] Quét mã người **chưa đăng ký nhưng có trong hệ thống** → trả về **PENDING_REVIEW**; Admin bấm **Accept** (duyệt cho vào) hoặc **Decline** (kèm lý do)

**Kết quả mong đợi:**
- Hệ thống bắt **đúng** các logic trạng thái.
- **Nhật ký quét cập nhật realtime**.
- Nút **xuất Excel lịch sử quét** hoạt động.

**Actual:**
> _(điền sau khi chạy)_

---

## GIAI ĐOẠN 6: BÁO CÁO THỐNG KÊ VÀ CẤU HÌNH GIAO DIỆN

### E2E-10 · Bước 10: Phân tích số liệu (Analytics) & Đánh giá (Reviews)

**Hành động:**
- **Analytics:**
  - [ ] Kiểm tra **Overview**
  - [ ] **Events Stats** — test sub-tab **CAMPUS**
  - [ ] **Checkins Stats** — kiểm tra breakdown **nguồn check-in** và **Waitlist conversion rate**
  - [ ] Test bộ lọc **DateRangeFilter** ở tab **User Growth**
- **Reviews:**
  - [ ] Mở sự kiện có `TimeStatus = ENDED` → vào tab **Reviews** → lọc thử **số sao (1–5)**

**Kết quả mong đợi:**
- Biểu đồ **Recharts** hiển thị đúng.
- Bộ lọc **DateRangeFilter phải bấm Apply mới fetch dữ liệu**.
- Tab Reviews **read-only** hiển thị chính xác.

**Actual:**
> _(điền sau khi chạy)_

---

### E2E-11 · Bước 11: Cài đặt hệ thống (Settings)

**Hành động:**
- **Featured Event:**
  - [ ] Chọn sự kiện đưa lên **Carousel trang chủ**
  - [ ] Thử nút **"Disable all"**
- **Social Media:**
  - [ ] Thêm 1 nền tảng tùy chỉnh (tự đặt key)
  - [ ] Nhập **URL sai định dạng** để test lỗi
  - [ ] Thử **kéo thả Reorder**
- **System Settings:**
  - [ ] Sửa nội dung **Footer/Contact (EN/VI)** bằng RichTextEditor
  - [ ] Chỉnh sửa **Footer Links**

**Kết quả mong đợi:**
- **Carousel xoay tự động sau 7 giây** (chỉ hiển thị event `PUBLISHED` + `UPCOMING/ONGOING`).
- Social Media **chặn URL sai**, **chặn trùng key**.
- **Footer cập nhật đúng trên toàn hệ thống.**

**Actual:**
> _(điền sau khi chạy)_

---

## Ghi chú khi chạy

1. **Chụp ảnh ngay tại chỗ.** Đây là môi trường dev (`prod-dev`) và dữ liệu có thể bị reset — trạng thái bạn tạo hôm nay có thể biến mất ở phiên sau.
2. **Tài khoản admin là dùng chung cả lớp.** Đặt tên sự kiện/danh mục bạn tạo có tiền tố dễ nhận, ví dụ `[23127183] Test Event ...`, để không lẫn với dữ liệu của người khác và dễ dọn dẹp.
3. **Cẩn thận với Bước 2 và Bước 6.** Block tài khoản / Reset password / Delete event tác động lên dữ liệu chung — ưu tiên thao tác trên tài khoản và sự kiện **do chính bạn tạo ra**.
4. **Bước 9 yêu cầu đổi giờ hệ thống** để test `OUTSIDE_CHECKIN_WINDOW` — nhớ chỉnh giờ máy trở lại sau khi test xong.
5. Mọi lỗi phát hiện được → ghi thẳng vào `04-findings-log.md` với tiền tố `E2E-` để phân biệt với bug tìm ra từ checklist HW03.
