# Hướng dẫn chạy Task 3 — Cross-Browser / Cross-Platform (từng bước)

> Bổ sung chi tiết thao tác cho phần đã có sẵn ở `HUONG_DAN_CHI_TIET_TUNG_PHAN.md` (mục Task 3). File đó nói **làm gì**; file này nói **bấm gì, theo thứ tự nào, để đỡ tốn phút trial nhất**.
> Kết quả cuối cùng điền vào: [`../23127183_HW03_AI_GUIUsability_EMS_100/03-compatibility-matrix.md`](../23127183_HW03_AI_GUIUsability_EMS_100/03-compatibility-matrix.md)
> Ảnh lưu vào: `23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/`

---

## Bước 0 — Chuẩn bị trước khi mở BrowserStack (làm ở máy mình, không tốn phút trial)

1. **Mở sẵn 1 tab EMS thật ở máy mình**, đăng nhập bằng `23127183@student.hcmus.edu.vn`, xác nhận lại 3 URL cần test:
   - B1: `https://prod-dev.ems-fitus.cloud/events`
   - B2: `https://prod-dev.ems-fitus.cloud/events/<id>` — chọn sẵn **1 sự kiện cụ thể còn chỗ** (ví dụ Workshop A), copy URL đầy đủ ra một chỗ để dán nhanh khi ở trong BrowserStack (gõ URL dài trên môi trường mobile giả lập rất chậm và dễ gõ sai)
   - B4: `https://prod-dev.ems-fitus.cloud/profile`
2. **Ghi ra giấy/note thứ tự thao tác chuẩn cho mỗi ô** (để không phải nghĩ lại giữa lúc đồng hồ trial đang chạy):
   `Đăng nhập → mở B1, chụp → bấm vào sự kiện để sang B2, chụp → avatar → View profile để sang B4, chụp`
3. **Chuẩn bị cách overlay email** — xem Bước 2 bên dưới, quyết định trước dùng cách nào để không loay hoay lúc chạy thật.
4. Tạo sẵn thư mục `evidence/task3/` (đã có sẵn trong repo, kiểm tra lại bằng lệnh dưới nếu cần):
   ```bash
   ls "23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/"
   ```

---

## Bước 1 — Đăng ký tài khoản trial

**BrowserStack Live** (khuyến khích — nhiều thiết bị thật hơn LambdaTest ở gói free):

1. Vào `browserstack.com` → **Free Trial** → đăng ký bằng email cá nhân (không cần email trường).
2. Xác nhận email nếu được yêu cầu.
3. Vào mục **Live** (không phải Automate — Automate là chạy script, Live mới là "điều khiển trình duyệt/thiết bị thật bằng tay" mà bạn cần).
4. ⚠️ **Trial thường giới hạn theo phút hoặc theo số ngày dùng thử** — chính sách BrowserStack có thể đổi theo thời gian, nên **mở trang tài khoản (Account → Plan) ngay sau khi đăng ký để xem chính xác còn bao nhiêu phút/ngày**, rồi lên lịch chạy 21 ảnh trong 1 lần ngồi liên tục thay vì rải ra nhiều ngày (mỗi lần mở phiên Live mới đều tính giờ, dù có thể phiên cũ chưa dùng hết).

**Nếu hết trial BrowserStack giữa chừng:** chuyển sang `lambdatest.com` (free trial tương tự) để chạy nốt các ô còn thiếu — đề cho phép, chỉ cần ghi rõ trong `03-compatibility-matrix.md` mục "Công cụ" là **đã dùng 2 công cụ**, ô nào chạy ở đâu.

**Nếu cả hai đều hết:** dùng **thiết bị thật của bạn/bạn bè** (điện thoại Android, iPhone, Mac nếu có) — đề cho phép, chỉ cần ghi rõ "thiết bị thật" thay vì "emulator" ở cột cuối bảng.

---

## Bước 2 — Cách overlay email `23127183@student.hcmus.edu.vn` lên mọi ảnh

Đề bắt buộc **mọi ảnh** phải thấy được email này — thiếu là ảnh không tính. Ba cách, ưu tiên từ mạnh xuống yếu:

| Cách | Làm sao | Khi nào dùng |
|---|---|---|
| **1. Cửa sổ phụ cạnh EMS** | Mở Notepad/ghi chú gõ sẵn dòng `23127183@student.hcmus.edu.vn`, kéo cửa sổ đó ra cạnh khung trình duyệt BrowserStack trước khi chụp toàn màn hình (chụp cả 2 cửa sổ trong 1 ảnh) | Mạnh nhất, luôn ưu tiên cách này |
| **2. Dán vào URL bar / ô tìm kiếm trong khung hình** | Nếu màn hình quá hẹp (mobile) không đủ chỗ cho cửa sổ phụ, dán tạm email vào một ô input còn trống trong khung (vd ô search chưa dùng) trước khi chụp | Khi test trên phone/tablet, không đủ chỗ cho cách 1 |
| **3. Chèn chữ lên ảnh sau khi chụp** | Dùng Paint / Snipping Tool có công cụ Text để gõ đè email lên góc ảnh sau khi đã lưu | Chỉ dùng khi 2 cách trên không khả thi — TA có thể nghi ngờ ảnh bị chỉnh sửa nếu dùng cách này quá nhiều |

**Lưu ý:** BrowserStack Live tự hiển thị sẵn tên OS/browser/thiết bị ở thanh công cụ khung ngoài (không phải trong nội dung trang) — khi chụp, **chụp cả khung ngoài đó** (đừng chỉ chụp riêng nội dung trang web), như vậy cột "browser/OS/device" trong ảnh tự động có sẵn, không cần overlay thêm.

---

## Bước 3 — Thứ tự chạy 7 ô × 3 màn hình (tối ưu số lần đăng nhập)

**Nguyên tắc:** mỗi phiên BrowserStack Live mới = trình duyệt sạch = phải đăng nhập lại từ đầu. Nên **đừng đổi ô sau mỗi màn hình** — chạy hết cả 3 màn hình (B1→B2→B4) trong **cùng một phiên/ô** rồi mới đổi sang ô tiếp theo.

Trình tự đề xuất (đúng theo bộ 7 ô đã có sẵn trong `03-compatibility-matrix.md`):

| Thứ tự | Ô | Môi trường | Việc làm |
|:--:|---|---|---|
| 1 | C1 | Windows 11 + Chrome + Desktop | Mở Live → chọn Windows 11, Chrome → đăng nhập EMS → chụp B1 → sang B2 → chụp → sang B4 → chụp → **đóng phiên** |
| 2 | C2 | Windows 11 + Edge + Desktop | *(lặp lại, đổi trình duyệt)* |
| 3 | C3 | Windows 11 + Firefox + Desktop | *(lặp lại)* |
| 4 | C4 | macOS + Safari + Desktop | *(lặp lại)* |
| 5 | C5 | macOS + Opera + Desktop | *(lặp lại — nếu BrowserStack không có Opera trên macOS, đổi sang Opera trên Windows và ghi rõ lý do đổi)* |
| 6 | C6 | **Android** + **Firefox** + **Tablet** — Galaxy Tab S9 | *(lặp lại, chọn thiết bị tablet Android thật trong danh sách)* |
| 7 | C7 | **Android** + **Chrome** + **Phone** — Galaxy S23 | *(lặp lại, chọn điện thoại Android thật trong danh sách)* |

> Bộ cuối cùng: C6 dùng **Firefox** (Gecko), C7 dùng **Chrome** (Blink) — cả hai engine đều được quan sát trực tiếp trên Android, không chỉ trên Windows như bộ đề xuất ban đầu. Đây là bộ cân bằng tốt hơn, không cần đổi gì thêm.
> Chốt **Android** cho cả C6/C7 (thay vì iOS) vì cả Firefox lẫn Chrome trên Android vẫn giữ đúng engine gốc (Gecko/Blink) — trên iOS mọi trình duyệt đều bị ép chạy WebKit nên không cho thêm thông tin engine mới. Nếu bạn muốn đổi sang iOS (vd không có tablet/phone Android trong danh sách BrowserStack lúc chạy), đổi tên file/bảng tương ứng và ghi chú rõ trong mục Giới hạn.

Mỗi ô = 1 lần đăng nhập + 3 lần chụp (B1, B2, B4) = **21 ảnh tổng cộng**, đúng số tối thiểu.

**Ràng buộc kỹ thuật cần nhớ khi chọn thiết bị trong danh sách BrowserStack:**
- Safari **chỉ chọn được** trên macOS hoặc iOS, không có trên Windows/Android.
- Samsung Internet **chỉ có trên Android**.
- **Trên iOS, mọi trình duyệt (kể cả "Chrome") đều chạy engine WebKit** — nếu C6/C7 chọn iOS, phải ghi chú rõ điều này trong báo cáo, đừng tính nó vào cột "Blink" ở bảng phân bố lỗi theo engine.
- B2 cần chọn **đúng 1 sự kiện cụ thể** giống nhau ở cả 7 ô (dùng URL đã chuẩn bị ở Bước 0) để 7 kết quả so sánh được với nhau — đừng mỗi ô bấm vào một sự kiện khác nhau.

---

## Bước 4 — Chụp và đặt tên file

Đặt tên theo mẫu: `<Màn>_<browser>_<os>_<device>.png`. Danh sách đủ **21 file** cho 7 ô × 3 màn hình — copy nguyên khối dưới đây, đổi tên khi chụp xong từng cái (đường dẫn đã tính sẵn từ thư mục gốc repo):

**Ô C1 — Windows 11 + Chrome + Desktop**
```
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B1_chrome_windows_desktop.png
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B2_chrome_windows_desktop.png
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B4_chrome_windows_desktop.png
```

**Ô C2 — Windows 11 + Edge + Desktop**
```
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B1_edge_windows_desktop.png
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B2_edge_windows_desktop.png
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B4_edge_windows_desktop.png
```

**Ô C3 — Windows 11 + Firefox + Desktop**
```
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B1_firefox_windows_desktop.png
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B2_firefox_windows_desktop.png
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B4_firefox_windows_desktop.png
```

**Ô C4 — macOS + Safari + Desktop**
```
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B1_safari_macos_desktop.png
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B2_safari_macos_desktop.png
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B4_safari_macos_desktop.png
```

**Ô C5 — macOS + Opera + Desktop**
```
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B1_opera_macos_desktop.png
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B2_opera_macos_desktop.png
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B4_opera_macos_desktop.png
```

**Ô C6 — Android + Firefox + Tablet (Galaxy Tab S9)**
```
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B1_firefox_android_tablet.png
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B2_firefox_android_tablet.png
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B4_firefox_android_tablet.png
```

**Ô C7 — Android + Chrome + Phone (Galaxy S23)**
```
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B1_chrome_android_phone.png
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B2_chrome_android_phone.png
23127183_HW03_AI_GUIUsability_EMS_100/evidence/task3/B4_chrome_android_phone.png
```

⚠️ Nếu lúc chạy thật bạn phải đổi sang trình duyệt/thiết bị khác (vd BrowserStack không có đúng thiết bị này), đổi tên file cho khớp thực tế — tên file phải phản ánh đúng môi trường đã chạy, không giữ tên cũ.

Ô nào **Fail** thì lưu thêm 1 bản đặt tên theo Bug-ID sẽ tạo ở Bước 6, ví dụ `evidence/task3/CP-B2-01.png` — có thể là cùng file, chỉ cần đủ cả 2 tên hoặc ghi rõ trong bảng ảnh nào ứng với Bug-ID nào.

---

## Bước 5 — Điền `03-compatibility-matrix.md` (theo đúng thứ tự các mục có sẵn)

1. **Header đầu file:** điền công cụ đã dùng (BrowserStack/LambdaTest), tài khoản (chỉ cần ghi email đăng ký trial, không cần mật khẩu), ngày chạy.
2. **§1 Bảng tổ hợp (C1–C7):** điền phiên bản OS/browser thật (BrowserStack hiện rõ số phiên bản khi bạn chọn thiết bị — copy nguyên số đó), và cột cuối ghi **"thật" hay "emulator"** — trên BrowserStack Live, phần lớn thiết bị mobile là **thiết bị thật từ xa** (real device cloud), không phải emulator; máy desktop (Windows/macOS) trên BrowserStack **là máy ảo**, ghi rõ "VM" cho khác với "real device".
3. **Bảng kiểm tra độ phủ** ngay dưới đó: đánh dấu ô nào phủ chiều nào — làm xong bảng C1–C7 là bảng này tự khớp, chỉ cần tick lại cho khớp.
4. **§2/§3/§4 — 3 ma trận theo từng màn hình:** dán kết quả Pass/Fail của từng ô cho B1, rồi B2, rồi B4. Ảnh dẫn vào đúng file đã lưu ở Bước 4.
5. **§5 — Chi tiết ô Fail:** mỗi Fail lập 1 block `[CP-Bx-xx]` — xem Bước 6.
6. **§6 — Tổng hợp:** đếm Pass/Fail mỗi màn hình + bảng phân bố lỗi theo OS/engine/device — có thể đếm tay vì tối đa 21 dòng (nếu muốn chắc chắn không đếm sai, dán bảng vào và nhờ mình đếm lại bằng lệnh, giống cách đã làm ở Task 1B).
7. **Kết luận + Giới hạn** ở cuối — viết sau khi đã có số liệu thật, đừng viết trước.

---

## Bước 6 — Khi gặp Fail: phân loại và ghi log

Với mỗi ô Fail, tự hỏi: **"lỗi này có xuất hiện ở ô khác không (kể cả khác màn hình)?"**

- **Chỉ xuất hiện ở 1–2 môi trường cụ thể** (vd chỉ Safari, hoặc chỉ ở độ phân giải phone) → đây là **lỗi tương thích thật**, tạo mới `CP-Bx-xx` trong `04-findings-log.md`.
- **Xuất hiện ở mọi/hầu hết môi trường** → đây là **bug chung của ứng dụng**, khả năng cao đã trùng với một `SV-`/`CL-` finding đã ghi ở Task 1B — ghi `= SV-xxx` hoặc `= CL-xxx` vào cột liên quan thay vì tạo `CP-` mới, tránh đếm trùng (đúng nguyên tắc đã áp dụng xuyên suốt bài này).

Khi báo lại cho mình các ô Fail (mô tả ngắn + môi trường + có lặp lại ở ô khác không), mình sẽ giúp viết đầy đủ block `[CP-Bx-xx]`, cập nhật `04-findings-log.md` và fold số liệu vào `00-main-report.md` §4 — đúng quy trình đã làm với Task 1B/2.

---

## Mẹo tiết kiệm phút trial

- Làm hết **Bước 0** ở máy mình trước, không mở BrowserStack cho tới khi đã sẵn sàng thao tác liên tục.
- Chạy đúng theo thứ tự Bước 3 — gộp 3 màn hình vào 1 phiên, đừng mở/đóng phiên nhiều lần cho cùng 1 ô.
- Nếu BrowserStack cho phép "extend session" thay vì mở phiên mới khi đổi màn hình trong cùng ô, dùng tính năng đó.
- Chụp ảnh bằng phím tắt hệ thống (`Win+Shift+S` trên Windows) thay vì tìm nút chụp ảnh riêng của BrowserStack — nhanh hơn và không tốn thao tác thêm trong phiên.

## Checklist trước khi coi Task 3 xong

- [ ] Đủ 7 ô × 3 màn hình = 21 ảnh, **mọi ảnh** (không chỉ Fail) đều có email + URL + browser/OS/device nhìn thấy được
- [ ] Với **từng màn hình riêng**: tự đếm lại đủ 3 OS, đủ 5 browser, đủ 3 loại thiết bị
- [ ] Mỗi ô Fail có block chi tiết + đã phân loại tương thích thật hay bug chung
- [ ] Đã ghi rõ ô nào chạy trên VM/emulator, ô nào thiết bị thật
- [ ] `04-findings-log.md` đã có các `CP-` mới (nếu có) và tổng số đã cập nhật ở `00-main-report.md` §5
- [ ] Mục "Giới hạn" đã ghi rõ trial dùng bao nhiêu phút, có đổi công cụ giữa chừng không, có ô nào phải thay thế do thiết bị không có trong danh sách
