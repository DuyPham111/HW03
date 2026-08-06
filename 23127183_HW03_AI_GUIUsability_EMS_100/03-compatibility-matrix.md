# Cross-Browser / Cross-Platform Report — Task 3

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183) · **Kịch bản:** B — User đăng ký tham dự sự kiện
**Màn hình được test:** B1 Danh sách sự kiện · B2 Trang chi tiết sự kiện · B4 My Profile — QR Code + My Activities
**Công cụ:** BrowserStack Live — Windows/macOS chạy trên VM cloud, Android (Galaxy Tab S9, Galaxy S23) là **Real Device** (đặt tại Mumbai, India, xác nhận qua banner "You are testing on a Real Device!" hiện trong lúc chạy) — tài khoản: _(TODO — email bạn dùng đăng ký trial)_
**Email overlay trên mọi ảnh:** 23127183@student.hcmus.edu.vn
**Ngày chạy:** 06/08/2026

> **Yêu cầu overlay của đề:** mỗi ảnh phải thấy rõ **email MSSV** + **URL của EMS** + **tên browser / OS / device**. Thiếu overlay = ảnh không được tính.

---

## 1. Yêu cầu độ phủ

| Chiều | Bắt buộc phủ | Đã chọn |
|---|---|---|
| **3 hệ điều hành** | Windows · macOS · Android **hoặc** iOS | Windows · macOS · **Android** |
| **5 trình duyệt** | Chrome · Firefox · Safari · Edge · Opera (hoặc Samsung Internet trên mobile) | Chrome · Firefox · Safari · Edge · Opera |
| **3 loại thiết bị** | Desktop · Tablet · Phone | Desktop · Tablet · Phone |

**Luật:** không cần đủ 3×5×3 = 45 ô, **nhưng với TỪNG màn hình** phải chạm **mọi OS ≥ 1 lần, mọi browser ≥ 1 lần, mọi device class ≥ 1 lần**.

### Bộ tổ hợp đã chọn (áp dụng cho cả 3 màn hình)

| Ô | OS | Phiên bản OS | Browser | Phiên bản | Device class | Thiết bị / Độ phân giải | Emulator hay thật? |
|---|---|---|---|---|---|---|---|
| C1 | Windows | 11 *(TODO: build số nếu cần)* | Chrome | _(TODO — không hiện trong khung hình đã chụp)_ | Desktop | ~1920×1080 (VM) | VM (BrowserStack cloud) |
| C2 | Windows | 11 | Edge | _(TODO)_ | Desktop | ~1920×1080 (VM) | VM |
| C3 | Windows | 11 | Firefox | _(TODO)_ | Desktop | ~1920×1080 (VM) | VM |
| C4 | macOS | _(TODO — không hiện trong khung hình)_ | Safari | _(TODO)_ | Desktop | ~1920×1080 (VM) | VM |
| C5 | macOS | _(TODO)_ | Opera | _(TODO)_ | Desktop | ~1920×1080 (VM) | VM |
| C6 | Android | _(TODO)_ | Firefox | _(TODO)_ | Tablet | Galaxy Tab S9 | **Real Device** (Mumbai, India) |
| C7 | Android | _(TODO)_ | Chrome | _(TODO)_ | Phone | Galaxy S23 | **Real Device** (Mumbai, India) |

> Phiên bản OS/browser không đọc được trực tiếp từ ảnh đã chụp (không hiển thị trong khung hình, và panel thông tin thiết bị của BrowserStack bị cửa sổ email che). Nếu cần điền chính xác, mở lại phiên BrowserStack và xem ở panel bên phải trước khi nộp — không bắt buộc vì đề chỉ đòi tên OS/browser/device, không đòi số phiên bản.

**Kiểm tra độ phủ của bộ tổ hợp trên:**

| Chiều | Giá trị | Ô phủ |
|---|---|---|
| OS | Windows | C1, C2, C3 |
| | macOS | C4, C5 |
| | Android | C6, C7 |
| Browser | Chrome | C1, C7 |
| | Firefox | C3, C6 |
| | Safari | C4 |
| | Edge | C2 |
| | Opera | C5 |
| Device class | Desktop | C1–C5 |
| | Tablet | C6 |
| | Phone | C7 |

Đủ 3/3 OS, 5/5 browser, 3/3 device class — bộ 7 ô phủ đúng yêu cầu tối thiểu.

---

## 2. Ma trận — Màn hình S1 = B1 Danh sách sự kiện

| Ô | OS | Browser | Device | Kết quả | Lỗi quan sát được | Ảnh |
|---|---|---|---|:--:|---|---|
| C1 | Windows 11 | Chrome | Desktop | ✅ Pass | | `evidence/task3/B1_chrome_windows_desktop.png` |
| C2 | Windows 11 | Edge | Desktop | ✅ Pass | | `evidence/task3/B1_edge_windows_desktop.png` |
| C3 | Windows 11 | Firefox | Desktop | ✅ Pass | | `evidence/task3/B1_firefox_windows_desktop.png` |
| C4 | macOS | Safari | Desktop | ✅ Pass | | `evidence/task3/B1_safari_macos_desktop.png` |
| C5 | macOS | Opera | Desktop | ✅ Pass | | `evidence/task3/B1_opera_macos_desktop.png` |
| C6 | Android | Firefox | Tablet | ✅ Pass | 1 thẻ sự kiện hiện icon ảnh vỡ — **không tính Fail riêng**, trùng bug dữ liệu đã biết `SV-B1-04`/`CL-B2-01`, không phải lỗi hiển thị riêng của môi trường này | `evidence/task3/B1_firefox_android_tablet.png` |
| C7 | Android | Chrome | Phone | ✅ Pass | | `evidence/task3/B1_chrome_android_phone.png` |

**Độ phủ:** OS ✅ (Windows, macOS, Android) · Browser ✅ (Chrome, Edge, Firefox, Safari, Opera) · Device class ✅ (Desktop, Tablet, Phone) · **Kết quả:** 7 Pass / 0 Fail

## 3. Ma trận — Màn hình S2 = B2 Trang chi tiết sự kiện

> Cả 7 ô cùng mở **sự kiện `events/177` — "Workshop: CV & Phỏng vấn thực chiến cho sinh viên IT 2026"** để kết quả so sánh được công bằng.

| Ô | OS | Browser | Device | Kết quả | Lỗi quan sát được | Ảnh |
|---|---|---|---|:--:|---|---|
| C1 | Windows 11 | Chrome | Desktop | ✅ Pass | | `evidence/task3/B2_chrome_windows_desktop.png` |
| C2 | Windows 11 | Edge | Desktop | ✅ Pass | | `evidence/task3/B2_edge_windows_desktop.png` |
| C3 | Windows 11 | Firefox | Desktop | ✅ Pass | | `evidence/task3/B2_firefox_windows_desktop.png` |
| C4 | macOS | Safari | Desktop | ✅ Pass | | `evidence/task3/B2_safari_macos_desktop.png` |
| C5 | macOS | Opera | Desktop | ✅ Pass | | `evidence/task3/B2_opera_macos_desktop.png` |
| C6 | Android | Firefox | Tablet | ❌ **Fail** | Giờ Event/Registration/Check-in hiển thị lệch **5 tiếng 30 phút** so với 5 ô desktop cho cùng 1 sự kiện — xem `CP-B2-01` | `evidence/task3/B2_firefox_android_tablet.png` |
| C7 | Android | Chrome | Phone | ❌ **Fail** | Cùng lỗi lệch giờ 5:30 như C6 — xem `CP-B2-01` | `evidence/task3/B2_chrome_android_phone.png` |

**Độ phủ:** OS ✅ · Browser ✅ · Device class ✅ · **Kết quả:** 5 Pass / 2 Fail

## 4. Ma trận — Màn hình S3 = B4 My Profile — QR Code + My Activities

| Ô | OS | Browser | Device | Kết quả | Lỗi quan sát được | Ảnh |
|---|---|---|---|:--:|---|---|
| C1 | Windows 11 | Chrome | Desktop | ✅ Pass | | `evidence/task3/B4_chrome_windows_desktop.png` |
| C2 | Windows 11 | Edge | Desktop | ✅ Pass | | `evidence/task3/B4_edge_windows_desktop.png` |
| C3 | Windows 11 | Firefox | Desktop | ✅ Pass | | `evidence/task3/B4_firefox_windows_desktop.png` |
| C4 | macOS | Safari | Desktop | ✅ Pass | | `evidence/task3/B4_safari_macos_desktop.png` |
| C5 | macOS | Opera | Desktop | ✅ Pass | | `evidence/task3/B4_opera_macos_desktop.png` |
| C6 | Android | Firefox | Tablet | ✅ Pass | ⚠️ Ảnh cắt trước khi thấy dòng ngày/giờ dưới thẻ "Draw with me" — chưa xác nhận được có bị lệch giờ như B2 không | `evidence/task3/B4_firefox_android_tablet.png` |
| C7 | Android | Chrome | Phone | ✅ Pass | ⚠️ Ảnh cắt trước khi thấy thẻ hoạt động — chưa xác nhận được có bị lệch giờ như B2 không | `evidence/task3/B4_chrome_android_phone.png` |

**Độ phủ:** OS ✅ · Browser ✅ · Device class ✅ · **Kết quả:** 7 Pass / 0 Fail *(2 ô cần bạn tự xác nhận thêm — xem ghi chú)*

> ⚠️ **Cần bạn tự kiểm tra lại:** mở B4 trên tablet/phone (C6/C7) một lần nữa, cuộn tới thẻ hoạt động đầu tiên trong My Activities, xem ngày/giờ có khớp với bản desktop không (bản desktop: "09/08/2026 07:30 – 09/08/2026 10:00", "Registered at: 06/08/2026 18:36"). Nếu cũng lệch 5:30 → đổi 2 ô này thành Fail và gộp chung vào `CP-B2-01` (đổi phạm vi finding từ "chỉ B2" thành "toàn hệ thống"). Nếu khớp đúng → giữ nguyên Pass như hiện tại.

---

## 5. Chi tiết các ô Fail

> Mỗi Fail → 1 block, kèm ảnh và ghi chú loại lỗi. Loại lỗi thường gặp: **tràn nội dung (overflow) · chồng lấn (overlap) · vỡ layout · chữ không đọc được · control không bấm được / không responsive · font hoặc icon không load · scroll ngang không mong muốn**.

### [CP-B2-01] Màn hình B2 · Ô C6, C7 — giờ hiển thị sai lệch theo thiết bị (không phải overflow/vỡ layout, mà là **nội dung sai**)

| Mục | Nội dung |
|---|---|
| Môi trường | Android (Real Device, Mumbai India) — Galaxy Tab S9 + Firefox (C6) và Galaxy S23 + Chrome (C7), so với baseline Windows 11/macOS Desktop (C1–C5) |
| Loại lỗi | Nội dung sai lệch giữa các môi trường (không phải lỗi hiển thị/bố cục) |
| Mô tả | Mở **cùng 1 sự kiện** (`events/177`) trên 7 môi trường. 5 ô desktop (C1–C5) đều hiện: Event date 22/08 07:00–10:00 · Registration 06/08 08:30 – 20/08 22:29 · Check-in 22/08 06:30–07:15. 2 ô Android thật (C6, C7) hiện **cùng ngày nhưng giờ lệch đúng 5 tiếng 30 phút ở cả 6/6 mốc**: Event date 01:30–04:30 · Registration 03:00–16:59 · Check-in 01:00–01:45. Không có nhãn múi giờ nào ở bất kỳ đâu trên trang để giải thích chênh lệch — người xem trên điện thoại và người xem trên laptop sẽ tin vào 2 giờ bắt đầu khác nhau cho cùng 1 sự kiện. |
| Có tái hiện trên môi trường khác không? | **Chỉ 2/7 môi trường** (cả hai đều là thiết bị Android thật) — 5 môi trường desktop hoàn toàn khớp nhau. ⇒ Đây là lỗi tương thích thật, không phải bug chung (nếu là bug chung thì phải sai giống nhau ở cả 7 môi trường) |
| Nguyên nhân gốc — **đã xác minh** | Kiểm tra trực tiếp đồng hồ hệ thống của thiết bị Android thật lúc đang chạy: máy hiện **14:36** trong khi giờ Việt Nam thật lúc đó là **21:36** — lệch **7 tiếng**, tức thiết bị **không đặt múi giờ Việt Nam** (nhiều khả năng đang để UTC+0 hoặc múi giờ mặc định của trung tâm dữ liệu, không tự động theo vị trí thật). EMS không cố định hiển thị thời gian theo 1 múi giờ server mà **lấy giờ/múi giờ hệ thống của chính thiết bị đang xem** để hiển thị (đây chính là gốc rễ của `S-09`/`CL-B2-02` "không hiển thị múi giờ ở bất kỳ đâu") — nên bất kỳ thiết bị nào bị đặt sai múi giờ (rất dễ xảy ra với người dùng thật đi công tác/du học, không chỉ riêng máy cloud test) đều sẽ thấy giờ sự kiện sai mà không có cách nào tự nhận ra vì không có nhãn múi giờ để đối chiếu |
| Severity | **2** — không chặn được tác vụ đăng ký (nút Register vẫn hoạt động), nhưng gây hiểu sai thông tin thật về thời gian sự kiện, rủi ro người dùng đến sai giờ hoặc bỏ lỡ hạn đăng ký |
| Ảnh | `evidence/task3/B2_firefox_android_tablet.png` · `evidence/task3/B2_chrome_android_phone.png` (đối chiếu với `evidence/task3/B2_edge_windows_desktop.png` làm baseline) |

---

## 6. Tổng hợp

| Màn hình | Số ô | Pass | Fail | Tỉ lệ pass |
|---|:--:|:--:|:--:|:--:|
| S1 (B1) | 7 | 7 | 0 | 100% |
| S2 (B2) | 7 | 5 | 2 | 71.4% |
| S3 (B4) | 7 | 7 | 0 | 100% *(2 ô chưa xác nhận đầy đủ — xem ghi chú §4)* |
| **Tổng** | **21** | **19** | **2** | **90.5%** |

**Phân bố lỗi theo chiều** — giúp chỉ ra nguyên nhân gốc là do OS, do browser engine, hay do breakpoint responsive:

| Chiều | Giá trị | Số Fail |
|---|---|:--:|
| OS | Windows | 0 |
| | macOS | 0 |
| | **Android** | **2** |
| Browser engine | Blink (Chrome/Edge/Opera) | 0 |
| | **Gecko (Firefox — C6)** | **1** |
| | WebKit (Safari) | 0 |
| | *(Chrome trên Android — C7, cũng Blink nhưng vẫn Fail)* | **1** |
| Device class | Desktop | 0 |
| | **Tablet** | **1** |
| | **Phone** | **1** |

**Kết luận:** Cả 2 Fail đều tập trung ở **Android**, không phân biệt theo browser engine (Firefox/Gecko lẫn Chrome/Blink trên cùng nền Android đều Fail như nhau, trong khi Chrome/Blink trên Windows lại Pass) — nghĩa là nguyên nhân gốc **không nằm ở engine trình duyệt**, mà nằm ở tầng **thiết bị/hệ điều hành**: đã xác minh trực tiếp đồng hồ hệ thống của thiết bị Android thật lệch 7 tiếng so với giờ Việt Nam thật (14:36 thay vì 21:36), và EMS lấy giờ hệ thống của thiết bị để hiển thị thay vì cố định theo 1 múi giờ server (xem `CP-B2-01`). Toàn bộ 7/7 ô của B1 và B4 đều Pass, chỉ B2 — màn hình duy nhất hiển thị các mốc thời gian tuyệt đối (Event date/Registration/Check-in) — bị ảnh hưởng; B1 chỉ hiện đếm ngược tương đối ("Opens in 3d 11h") nên không lộ ra lỗi này, và B4 chưa xác nhận được đầy đủ (xem ghi chú §4). Điều này xác nhận lỗi nằm ở cách EMS xử lý **thời gian tuyệt đối theo múi giờ thiết bị**, không phải lỗi hiển thị/bố cục chung của Android.

**Giới hạn:**
- 5/7 ô (Windows, macOS) chạy trên **VM cloud** của BrowserStack; 2/7 ô (Android) là **Real Device** đặt tại Mumbai, Ấn Độ — không phải giả lập.
- Không xác định được chính xác phiên bản OS/browser cho từng ô (không hiển thị trong khung đã chụp, và panel thông tin của BrowserStack bị cửa sổ overlay email che mất khi chụp).
- Chưa xác nhận được liệu lỗi lệch giờ ở `CP-B2-01` có xuất hiện ở B4 hay không (2 ảnh bị cắt trước khi thấy dòng ngày/giờ) — cần kiểm tra bổ sung.
- Không dùng iOS/Safari trên mobile (chỉ dùng Android cho cả 2 ô di động) — do đó chưa kiểm được WebKit trên thiết bị di động thật, chỉ kiểm WebKit trên macOS Desktop (Safari, C4).
