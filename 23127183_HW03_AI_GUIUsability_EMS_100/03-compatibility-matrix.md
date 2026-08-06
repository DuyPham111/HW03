# Cross-Browser / Cross-Platform Report — Task 3

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183) · **Kịch bản:** B — User đăng ký tham dự sự kiện
**Màn hình được test:** B1 Danh sách sự kiện · B2 Trang chi tiết sự kiện · B4 My Profile — QR Code + My Activities
**Công cụ:** BrowserStack Live — Windows/macOS chạy trên VM cloud, Android (Galaxy Tab S9, Galaxy S23) là **Real Device** (đặt tại Mumbai, India, xác nhận qua banner "You are testing on a Real Device!" hiện trong lúc chạy) — tài khoản: `duypham150805@gmail.com`
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

| Ô | OS | Browser | Device class | Thiết bị / Độ phân giải | Emulator hay thật? | Tên file ảnh (3 màn) |
|---|---|---|---|---|---|---|
| C1 | Windows | Chrome | Desktop | ~1920×1080 (VM) | VM (BrowserStack cloud) | `B1/B2/B4_chrome_windows_desktop.png` |
| C2 | Windows | Edge | Desktop | ~1920×1080 (VM) | VM | `B1/B2/B4_edge_windows_desktop.png` |
| C3 | Windows | Firefox | Desktop | ~1920×1080 (VM) | VM | `B1/B2/B4_firefox_windows_desktop.png` |
| C4 | macOS | Safari | Desktop | ~1920×1080 (VM) | VM | `B1/B2/B4_safari_macos_desktop.png` |
| C5 | macOS | Opera | Desktop | ~1920×1080 (VM) | VM | `B1/B2/B4_opera_macos_desktop.png` |
| C6 | Android | Firefox | Tablet | Galaxy Tab S9 | **Real Device** (Mumbai, India) | `B1/B2/B4_firefox_android_tablet.png` |
| C7 | Android | Chrome | Phone | Galaxy S23 | **Real Device** (Mumbai, India) | `B1/B2/B4_chrome_android_phone.png` |

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
| C6 | Android | Firefox | Tablet | ❌ **Fail** | Cùng lỗi lệch giờ thiết bị như B2 — xem `CP-B2-01` | `evidence/task3/B4_firefox_android_tablet.png` |
| C7 | Android | Chrome | Phone | ❌ **Fail** | Cùng lỗi lệch giờ thiết bị như B2 — xem `CP-B2-01` | `evidence/task3/B4_chrome_android_phone.png` |

**Độ phủ:** OS ✅ · Browser ✅ · Device class ✅ · **Kết quả:** 5 Pass / 2 Fail

---

## 5. Chi tiết các ô Fail

> Mỗi Fail → 1 block, kèm ảnh và ghi chú loại lỗi. Loại lỗi thường gặp: **tràn nội dung (overflow) · chồng lấn (overlap) · vỡ layout · chữ không đọc được · control không bấm được / không responsive · font hoặc icon không load · scroll ngang không mong muốn**.

### [CP-B2-01] Màn hình B2 và B4 · Ô C6, C7 — giờ hiển thị sai lệch theo thiết bị (nội dung sai, không phải overflow/vỡ layout)

| Mục | Nội dung |
|---|---|
| Môi trường | Android (Real Device, Mumbai India) — Galaxy Tab S9 + Firefox (C6) và Galaxy S23 + Chrome (C7), so với baseline Windows 11/macOS Desktop (C1–C5) |
| Loại lỗi | Nội dung sai lệch giữa các môi trường (không phải lỗi hiển thị/bố cục) |
| Mô tả | Trên **B2**: cùng 1 sự kiện (`events/177`) — desktop hiện Event date 22/08 07:00–10:00, Android thật hiện 01:30–04:30, lệch đều 5:30 ở cả 6 mốc thời gian. Trên **B4**: cùng dữ liệu My Activities, cùng hiện tượng lệch giờ giữa desktop và 2 thiết bị Android thật. Không có nhãn múi giờ nào trên trang để giải thích chênh lệch. |
| Có tái hiện trên môi trường khác không? | Chỉ ở **Android thật** (C6, C7), cả 2 màn B2 và B4 — 5 môi trường desktop luôn khớp nhau ⇒ lỗi tương thích thật, không phải bug chung |
| Nguyên nhân gốc — **đã xác minh** | Kiểm tra đồng hồ hệ thống của thiết bị Android thật: máy hiện **14:36** trong khi giờ Việt Nam thật là **21:36** — lệch 7 tiếng, thiết bị không đặt đúng múi giờ Việt Nam. EMS lấy giờ hệ thống của thiết bị để hiển thị thay vì cố định theo 1 múi giờ server — đây là gốc rễ của `S-09`/`CL-B2-02` |
| Severity | **2** — không chặn được đăng ký, nhưng gây hiểu sai thông tin thời gian, rủi ro người dùng đến sai giờ hoặc bỏ lỡ hạn đăng ký |
| Ảnh | `evidence/task3/B2_firefox_android_tablet.png` · `evidence/task3/B2_chrome_android_phone.png` · `evidence/task3/B4_firefox_android_tablet.png` · `evidence/task3/B4_chrome_android_phone.png` (đối chiếu với `evidence/task3/B2_edge_windows_desktop.png` làm baseline) |

---

## 6. Tổng hợp

| Màn hình | Số ô | Pass | Fail | Tỉ lệ pass |
|---|:--:|:--:|:--:|:--:|
| S1 (B1) | 7 | 7 | 0 | 100% |
| S2 (B2) | 7 | 5 | 2 | 71.4% |
| S3 (B4) | 7 | 5 | 2 | 71.4% |
| **Tổng** | **21** | **17** | **4** | **81.0%** |

**Phân bố lỗi theo chiều** — giúp chỉ ra nguyên nhân gốc là do OS, do browser engine, hay do breakpoint responsive:

| Chiều | Giá trị | Số Fail |
|---|---|:--:|
| OS | Windows | 0 |
| | macOS | 0 |
| | **Android** | **4** |
| Browser engine | Blink (Chrome/Edge/Opera) | **2** *(Chrome trên Android — C7)* |
| | **Gecko (Firefox — C6)** | **2** |
| | WebKit (Safari) | 0 |
| Device class | Desktop | 0 |
| | **Tablet** | **2** |
| | **Phone** | **2** |

**Kết luận:** Cả 4 Fail đều tập trung ở **Android**, không phân biệt engine (Firefox/Gecko lẫn Chrome/Blink trên cùng nền Android đều Fail như nhau, trong khi Chrome/Blink trên Windows lại Pass) — nguyên nhân gốc **không nằm ở engine trình duyệt**, mà ở tầng **thiết bị**: đã xác minh đồng hồ hệ thống của thiết bị Android thật lệch 7 tiếng so với giờ Việt Nam thật (14:36 thay vì 21:36), và EMS lấy giờ hệ thống thiết bị để hiển thị thay vì cố định theo 1 múi giờ server (xem `CP-B2-01`). Lỗi xuất hiện ở cả B2 và B4 — hai màn hình duy nhất hiển thị mốc thời gian tuyệt đối; B1 chỉ hiện đếm ngược tương đối ("Opens in 3d 11h") nên không lộ ra lỗi này. Điều này xác nhận lỗi nằm ở cách EMS xử lý **thời gian tuyệt đối theo múi giờ thiết bị**, không phải lỗi hiển thị/bố cục chung của Android.

**Giới hạn:**
- 5/7 ô (Windows, macOS) chạy trên **VM cloud** của BrowserStack; 2/7 ô (Android) là **Real Device** đặt tại Mumbai, Ấn Độ — không phải giả lập.
- Không xác định được chính xác phiên bản OS/browser cho từng ô (không hiển thị trong khung đã chụp).
- Không dùng iOS/Safari trên mobile (chỉ dùng Android cho cả 2 ô di động) — chưa kiểm được WebKit trên thiết bị di động thật, chỉ kiểm WebKit trên macOS Desktop (Safari, C4).
