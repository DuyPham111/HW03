# HƯỚNG DẪN CHẠY 37 MỤC CÒN LẠI CỦA TASK 1B

**37 dòng chưa có kết quả nào trong `01-checklist-execution.md`** (24 dòng còn lại trong 61 đã điền xong ở đợt trước). File này chỉ nói **cách làm cụ thể từng dòng**, không lặp lại lý thuyết — mở song song với `01-checklist-execution.md` để gõ kết quả trực tiếp vào đó.

> Điền xong dòng nào thì báo tôi đúng theo mẫu: **tên item + màn hình + Passed/Failed/N-A + (ảnh nếu Failed)**. Tôi ghi vào bảng, sinh bug entry, đồng bộ số liệu.

---

## NHÓM 0 — 8 dòng chỉ cần XÁC NHẬN, không cần điều tra (5 phút)

Đây là 8 dòng đã đánh dấu `(?)` — tôi dự đoán N/A vì widget chỉ có ở phía admin. Bạn chỉ cần xác nhận đúng là **không thấy** widget đó trên B1/B2/B4, rồi xoá dấu `(?)`, gõ `N/A` + copy nguyên lý do đã ghi sẵn trong cột Notes vào cả 3 ô S1/S2/S3.

| ID | Xác nhận bằng cách nào |
|---|---|
| F-08, F-09, F-10 | Lướt qua B1/B2/B4 — có ô upload ảnh hay rich-text editor nào không? (Không, vì đây là trang xem/đăng ký, không phải trang tạo sự kiện) |
| F-15, F-16 | Tương tự — có form nhập ngày/upload nào không? Không |
| N-07 | Nhìn 3 màn — có sidebar thu gọn được không, hay chỉ có header ngang? Chỉ có header |
| N-08 | Có danh sách nào kéo-thả sắp xếp được không? Không |
| S-16 | Có dashboard KPI (Total Events, Total Check-ins...) ở đâu trong 3 màn không? Không, đó là trang admin riêng |

Xong 8 dòng này báo tôi một câu "8 dòng N/A đã xác nhận" là tôi cập nhật luôn, không cần chi tiết từng cái.

---

## NHÓM 1 — Test 1 lần, áp dụng cho cả 3 màn (10 phút)

### G-13 — Ngôn ngữ được lưu lại sau reload
1. Đứng ở B1, đổi cờ ngôn ngữ EN→VI (hoặc ngược lại)
2. Bấm F5 reload
3. Điều hướng sang B2, rồi B4 — ngôn ngữ có giữ nguyên không, hay bị trả về mặc định?
→ Passed nếu giữ nguyên ở cả 3 màn, Failed nếu bất kỳ màn nào bị trả về mặc định (ghi rõ màn nào Failed).

### N-01 — Menu chính nhất quán, mục đang xem nổi bật
1. Đứng ở B1 (`/events`) — nhìn menu `Events` trên header có được tô đậm/gạch chân khác các mục còn lại không (dấu hiệu "đang ở đây")
2. Sang B2 — `Events` còn tô đậm không (vì B2 vẫn thuộc nhóm Events)?
3. Sang B4 (`/profile`) — có mục nào trên menu chính tương ứng với Profile được tô đậm không, hay menu không phản ánh gì cả?
→ Đây là 1 item chung cho cả 3 màn, ghi kết quả riêng từng màn.

### N-05 — URL phản ánh trạng thái (filter/tab/trang)
1. Ở B1, áp 1 filter (vd chọn tab `Ongoing`, hoặc nhập từ khoá tìm kiếm)
2. Nhìn thanh địa chỉ — URL có đổi theo (thêm query string) không?
3. Copy URL đó, dán vào tab trình duyệt mới, mở ra — có load đúng đang lọc như vậy không?
→ Chỉ cần test ở S1 vì URL-state thường chỉ áp dụng cho trang danh sách có filter/tab; B2/B4 thường N/A (trang chi tiết không có "trạng thái lọc" để phản ánh lên URL) — bạn tự xác nhận B2/B4 đúng là không có gì để test rồi đánh N/A.

### G-14 — Tương phản màu chữ/nền
1. Bấm F12 mở DevTools
2. Bấm vào biểu tượng con trỏ chọn phần tử (icon mũi tên góc trên trái DevTools), click vào một dòng chữ bất kỳ trên trang (vd tiêu đề sự kiện)
3. Trong tab `Styles` bên phải, tìm dòng `color`, bấm vào ô màu — thường hiện thêm số tỉ lệ tương phản kèm dấu ✓ hoặc ✗ `AA`
4. Lặp lại cho 3-4 chỗ chữ khác nhau (chữ chính, chữ phụ nhạt màu, chữ trên nút màu) ở cả 3 màn
→ Failed nếu bất kỳ chỗ nào dấu ✗, ghi rõ chữ gì màu gì.

### G-15 — Zoom 200% không vỡ bố cục
1. Ở mỗi màn, bấm `Ctrl` + `+` (hoặc `Ctrl` + cuộn chuột) tới khi trình duyệt báo `200%`
2. Nhìn có chữ nào bị cắt, chồng lên nhau, hay nút bị đẩy ra ngoài màn hình không
→ Passed/Failed riêng từng màn.

### S-13 — Quy ước viết hoa nút/tiêu đề nhất quán (ngoài trường hợp `login` đã ghi nhận)
1. Liệt kê nhanh các nút bạn thấy ở mỗi màn: `Save event`, `Register (Student)`, `Cancel registration`, `Export`, `Filters`, `Sign In`...
2. Có nút nào viết thường hết hay UPPERCASE bất thường không (ngoài nút `login` đã biết)?
→ Nếu chỉ có `login` là bất thường (đã có `SV-B2-05`) thì Passed cho phần còn lại, ghi "ngoài SV-B2-05 không thấy thêm bất thường nào".

---

## NHÓM 2 — Riêng cho B1 (15 phút)

### G-04 — Không cuộn ngang ở ≥1280px
Kéo cửa sổ trình duyệt về đúng 1280px (hoặc F12 → icon responsive → nhập 1280×800), nhìn có thanh cuộn ngang dưới đáy không.

### G-05 — Ảnh thẻ sự kiện giữ đúng tỉ lệ
Nhìn 4-5 thẻ sự kiện có ảnh thật (không phải placeholder) — ảnh có bị kéo dài/bẹp, hay bị cắt mất phần quan trọng (mặt người, chữ trên poster) không.

### G-08 — Loading có skeleton/spinner
1. F12 → tab `Network` → đổi tốc độ mạng từ `No throttling` sang `Slow 3G`
2. F5 reload trang `/events`
3. Quan sát trong lúc tải: có khung xám nhấp nháy (skeleton) hoặc spinner không, hay trang trắng trơn rồi hiện ra đột ngột?
4. **Nhớ đổi lại `No throttling`** sau khi xong, không thì các bước sau chậm.

### N-03 — Back giữ nguyên bộ lọc/trang/vị trí cuộn
1. Ở B1, áp 1 filter, cuộn xuống giữa trang, bấm vào 1 sự kiện
2. Bấm nút Back của trình duyệt (không phải nút trong app)
3. Kiểm: filter còn giữ không? Vị trí cuộn có về đúng chỗ cũ không?

### N-09 — Không có liên kết hỏng
Bấm thử 5-6 link/nút điều hướng khác nhau (Calendar, Saved Events, User guide, một vài category ở sidebar, share icon...) — có cái nào ra trang lỗi/trang trắng không.

---

## NHÓM 3 — Riêng cho B2 (10 phút)

> ⚠️ **Lưu ý trước khi làm:** khối đăng ký ở B2 chỉ có **checkbox chọn vai trò**, không có ô nhập chữ tự do nào. Nên nhiều khả năng **F-01 đến F-06 sẽ N/A** (không có "trường nhập" hay "placeholder" để kiểm). Đừng cố tìm cái không tồn tại — nhìn lướt 30 giây, nếu đúng là chỉ có checkbox thì đánh N/A cả 6 dòng, lý do: "khối đăng ký chỉ có checkbox chọn vai trò, không có trường nhập tự do".

### F-07 — Submit khoá khi chưa hợp lệ, bấm đúp không tạo trùng
1. Mở 1 sự kiện đang mở đăng ký, **chưa tick vai trò** — nút `Register` có bị mờ/khoá không? *(đã biết trước: có, theo ảnh cũ)*
2. Tick vai trò, bấm `Register` **thật nhanh 2 lần liên tiếp** — có bị tạo 2 đăng ký trùng không (kiểm bằng cách xem My Activities có 1 hay 2 dòng)

### N-04 — Redirect đúng trang sau khi đăng nhập
1. Mở cửa sổ ẩn danh, dán thẳng link một sự kiện **không bật Public Event** (vd Workshop A)
2. Bị chặn, hiện màn đăng nhập
3. Đăng nhập xong — có quay lại đúng sự kiện đó không, hay bị đẩy về trang chủ `/events`?

### F-13 — Focus & Tab order trong khối đăng ký
1. Click vào khoảng trắng đầu trang B2, bấm phím `Tab` liên tục
2. Theo dõi viền sáng (focus ring) có nhảy tuần tự qua checkbox vai trò → nút Register không, hay nhảy lộn xộn/biến mất

### F-14 — Esc đóng dialog Cancel registration
Mở dialog Cancel registration, bấm phím `Esc` — có đóng không.

---

## NHÓM 4 — Riêng cho B4 (10 phút)

### S-08 — Export có progress/spinner
Bấm nút `Export` trên My Activities — trong lúc file đang tạo có spinner/progress bar không, hay bấm xong im lặng rồi tự nhiên tải file về.

### S-10 — Nhãn trạng thái thời gian khớp dữ liệu ngày giờ
Nhìn 1 thẻ hoạt động: badge `Upcoming`/`Ongoing`/`Ended` có khớp với khoảng ngày giờ hiển thị ngay cạnh nó không (vd badge `Ongoing` nhưng ngày sự kiện đã qua thì đó là Failed).

### S-11 — Mất mạng báo rõ
1. F12 → Network → chọn `Offline`
2. Thử bấm `Export` hoặc `Filters` trên My Activities
3. Hệ thống có báo lỗi rõ ràng không, hay im lặng/treo?
4. **Bật lại mạng ngay sau khi test.**

### F-13 / F-14 (áp dụng cho modal QR)
1. Bấm nút `QR Code`, mở modal
2. Tab xem focus có vào được nút `Download` và nút đóng `×` không
3. Bấm `Esc` — modal có đóng không

### N-09 — Không có liên kết hỏng
Bấm avatar, nút `Edit Profile`, `Change Password` — có ra trang lỗi không (không cần đổi mật khẩu thật, chỉ cần xem trang có load được không rồi thoát ra).

---

## Bảng tổng hợp: item nào chưa xếp vào nhóm nào

Kiểm lại: G-01, G-02, G-03 (căn lề/font/màu — quan sát mắt thường, không cần kỹ thuật gì đặc biệt, nhìn 3 màn thấy nhất quán thì Passed) và G-16 (chữ tiếng Việt dài — nhìn các nút/tiêu đề tiếng Việt có bị vỡ dòng xấu không) chưa có nhóm riêng vì chúng chỉ cần **nhìn và so sánh**, không cần thao tác đặc biệt — làm xen kẽ trong lúc chạy các nhóm trên, không cần dành riêng thời gian.

- [ ] Nhóm 0 xong (8 dòng N/A)
- [ ] Nhóm 1 xong (6 dòng dùng chung)
- [ ] Nhóm 2 xong (4 dòng B1)
- [ ] Nhóm 3 xong (4 dòng B2, có thể 6/10 N/A)
- [ ] Nhóm 4 xong (5 dòng B4)
- [ ] G-01/G-02/G-03/G-16 nhìn xen kẽ trong lúc làm các nhóm trên
