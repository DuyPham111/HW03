# Cross-Browser / Cross-Platform Report — Task 3

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183) · **Kịch bản:** B — User đăng ký tham dự sự kiện
**Màn hình được test:** B2 Trang chi tiết sự kiện · B3 Form đăng ký · B4 My Registrations + vé QR
**Công cụ:** _(TODO: BrowserStack / LambdaTest / Sauce Labs / thiết bị thật)_ — tài khoản: _(TODO)_
**Email overlay trên mọi ảnh:** pvnduy23@clc.fitus.edu.vn
**Ngày chạy:** _(TODO)_

> **Yêu cầu overlay của đề:** mỗi ảnh phải thấy rõ **email MSSV** + **URL của EMS** + **tên browser / OS / device**. Thiếu overlay = ảnh không được tính.

---

## 1. Yêu cầu độ phủ

| Chiều | Bắt buộc phủ | Đã chọn |
|---|---|---|
| **3 hệ điều hành** | Windows · macOS · Android **hoặc** iOS | _(TODO)_ |
| **5 trình duyệt** | Chrome · Firefox · Safari · Edge · Opera (hoặc Samsung Internet trên mobile) | _(TODO)_ |
| **3 loại thiết bị** | Desktop · Tablet · Phone | _(TODO)_ |

**Luật:** không cần đủ 3×5×3 = 45 ô, **nhưng với TỪNG màn hình** phải chạm **mọi OS ≥ 1 lần, mọi browser ≥ 1 lần, mọi device class ≥ 1 lần**.

### Bộ tổ hợp đã chọn (áp dụng cho cả 3 màn hình)

| Ô | OS | Phiên bản OS | Browser | Phiên bản | Device class | Thiết bị / Độ phân giải | Emulator hay thật? |
|---|---|---|---|---|---|---|---|
| C1 | Windows | 11 | Chrome | | Desktop | 1920×1080 | |
| C2 | Windows | 11 | Edge | | Desktop | 1920×1080 | |
| C3 | Windows | 11 | Firefox | | Desktop | 1366×768 | |
| C4 | macOS | | Safari | | Desktop | | |
| C5 | macOS | | Opera | | Desktop | | |
| C6 | Android / iOS | | Chrome / Safari | | Tablet | | |
| C7 | Android / iOS | | Firefox / Samsung Internet | | Phone | | |
| C8 | _(TODO thêm nếu cần để phủ đủ)_ | | | | | | |

**Kiểm tra độ phủ của bộ tổ hợp trên:**

| Chiều | Giá trị | Ô phủ |
|---|---|---|
| OS | Windows | |
| | macOS | |
| | Android/iOS | |
| Browser | Chrome | |
| | Firefox | |
| | Safari | |
| | Edge | |
| | Opera / Samsung Internet | |
| Device class | Desktop | |
| | Tablet | |
| | Phone | |

---

## 2. Ma trận — Màn hình S1 = B2 Trang chi tiết sự kiện

| Ô | OS | Browser | Device | Kết quả | Lỗi quan sát được | Ảnh |
|---|---|---|---|:--:|---|---|
| C1 | Windows 11 | Chrome | Desktop | ⬜ | | `evidence/task3/S1_C1.png` |
| C2 | Windows 11 | Edge | Desktop | ⬜ | | |
| C3 | Windows 11 | Firefox | Desktop | ⬜ | | |
| C4 | macOS | Safari | Desktop | ⬜ | | |
| C5 | macOS | Opera | Desktop | ⬜ | | |
| C6 | Android/iOS | Chrome/Safari | Tablet | ⬜ | | |
| C7 | Android/iOS | Firefox/Samsung | Phone | ⬜ | | |

**Độ phủ:** OS ✅/❌ · Browser ✅/❌ · Device class ✅/❌ · **Kết quả:** _ Pass / _ Fail

## 3. Ma trận — Màn hình S2 = B3 Form đăng ký
_(bảng như trên)_

## 4. Ma trận — Màn hình S3 = B4 My Registrations + vé QR
_(bảng như trên)_

---

## 5. Chi tiết các ô Fail

> Mỗi Fail → 1 block, kèm ảnh và ghi chú loại lỗi. Loại lỗi thường gặp: **tràn nội dung (overflow) · chồng lấn (overlap) · vỡ layout · chữ không đọc được · control không bấm được / không responsive · font hoặc icon không load · scroll ngang không mong muốn**.

### [CP-001] Màn hình _(TODO)_ · Ô _(TODO)_ — _(loại lỗi)_

| Mục | Nội dung |
|---|---|
| Môi trường | _(OS + phiên bản / Browser + phiên bản / Device + độ phân giải)_ |
| Loại lỗi | _(TODO)_ |
| Mô tả | _(TODO)_ |
| Có tái hiện trên môi trường khác không? | _(TODO — nếu chỉ 1 môi trường ⇒ lỗi tương thích thật; nếu mọi nơi ⇒ là bug chung, không phải lỗi tương thích)_ |
| Severity | _(TODO)_ |
| Ảnh | `evidence/task3/CP-001.png` |

![CP-001](evidence/task3/CP-001.png)

### [CP-002] …

---

## 6. Tổng hợp

| Màn hình | Số ô | Pass | Fail | Tỉ lệ pass |
|---|:--:|:--:|:--:|:--:|
| S1 | | | | |
| S2 | | | | |
| S3 | | | | |
| **Tổng** | | | | |

**Phân bố lỗi theo chiều** — giúp chỉ ra nguyên nhân gốc là do OS, do browser engine, hay do breakpoint responsive:

| Chiều | Giá trị | Số Fail |
|---|---|:--:|
| OS | Windows / macOS / Android-iOS | |
| Browser engine | Blink (Chrome/Edge/Opera) / Gecko (Firefox) / WebKit (Safari) | |
| Device class | Desktop / Tablet / Phone | |

**Kết luận:** _(TODO — lỗi tập trung ở đâu? Có phải chủ yếu ở breakpoint mobile? Ở WebKit? Nêu nhận định có căn cứ từ bảng trên)_

**Giới hạn:** _(TODO — dùng emulator hay thiết bị thật, trial giới hạn bao nhiêu phút, phiên bản OS/browser không chọn được…)_
