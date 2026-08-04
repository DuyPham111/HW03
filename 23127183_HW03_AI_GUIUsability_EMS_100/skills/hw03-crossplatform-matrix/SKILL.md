---
name: hw03-crossplatform-matrix
description: >-
  Thiết kế và chạy ma trận tương thích cross-browser/cross-platform (3 OS × 5
  browser × 3 device class) cho một tập màn hình web, kèm quy tắc chụp ảnh có
  overlay danh tính. Dùng khi cần chọn bộ tổ hợp tối thiểu phủ đủ 3 chiều, chạy
  BrowserStack/LambdaTest, hoặc phân tích lỗi tương thích theo browser engine.
---

# Cross-Browser / Cross-Platform Matrix

## Nguyên tắc

- **Phủ theo chiều, không phủ theo tích.** Đề không đòi 45 ô; đề đòi **mỗi OS ≥ 1 lần, mỗi browser ≥ 1 lần, mỗi device class ≥ 1 lần — cho TỪNG màn hình**. Thiết kế bộ tổ hợp tối thiểu thoả điều kiện đó rồi nhân lên cho 3 màn hình.
- **Mọi ảnh phải có overlay danh tính:** email `MSSV@....edu.vn` + URL EMS + tên browser/OS/device. Ảnh thiếu overlay coi như không có.
- **Phân biệt lỗi tương thích với bug chung.** Lỗi xuất hiện ở **mọi** môi trường không phải lỗi tương thích — đó là bug của ứng dụng. Chỉ ghi là lỗi tương thích khi nó **chỉ** xảy ra ở một số ô.
- **Ghi rõ emulator/simulator hay thiết bị thật.** Đây là điểm đề nhấn mạnh trong bài giảng compatibility testing.
- **AI không chạy được BrowserStack thay bạn.** AI dùng để thiết kế ma trận, kiểm tra độ phủ, và phân tích kết quả — phần chạy và chụp là của bạn.

---

## Bước 1 — Thiết kế bộ tổ hợp tối thiểu

```
Tôi cần một ma trận tương thích cho 3 màn hình web, ràng buộc:
- 3 OS: Windows, macOS, và Android HOẶC iOS
- 5 browser: Chrome, Firefox, Safari, Edge, Opera (hoặc Samsung Internet trên mobile)
- 3 device class: desktop, tablet, phone
- KHÔNG cần đủ 45 tổ hợp, nhưng với TỪNG màn hình phải phủ mọi OS ít nhất 1 lần,
  mọi browser ít nhất 1 lần, mọi device class ít nhất 1 lần.

1) Đề xuất bộ tổ hợp NHỎ NHẤT thoả điều kiện trên. Giải thích vì sao không thể nhỏ hơn.
2) Chỉ ra tổ hợp nào là BẤT KHẢ THI về mặt kỹ thuật (vd Safari trên Windows) và
   cách xử lý ràng buộc đó.
3) Lập bảng kiểm tra độ phủ: mỗi giá trị của mỗi chiều được phủ bởi (những) ô nào.
```
→ **Người review:** tự đếm lại bảng độ phủ. Đây là chỗ AI hay tuyên bố "đã phủ đủ" trong khi thiếu một giá trị.

**Ràng buộc thực tế cần nhớ:** Safari chỉ có trên macOS/iOS · Edge trên macOS có nhưng ít dùng · Opera trên mobile khác Opera desktop · Samsung Internet chỉ trên Android · trên iOS **mọi** trình duyệt đều chạy WebKit (Chrome iOS không phải Blink) — nếu dùng iOS thì "5 browser" trên đó thực chất là cùng một engine, phải nêu rõ giới hạn này trong báo cáo.

## Bước 2 — Chuẩn bị công cụ & overlay

- [ ] Đăng ký trial BrowserStack / LambdaTest (**tự lo tài khoản** — đề nói rõ)
- [ ] Ghi lại số phút trial còn lại → lên kế hoạch chạy để không hết giữa chừng
- [ ] Chuẩn bị cách overlay email lên ảnh. Ba cách, ưu tiên từ trên xuống:
  1. Mở một tab/cửa sổ phụ hiển thị email, đặt cạnh cửa sổ EMS trước khi chụp
  2. Dán email vào ô tìm kiếm/URL bar trong khung hình
  3. Chèn text lên ảnh sau khi chụp (yếu nhất về mặt bằng chứng — dùng cuối cùng)
- [ ] Quy ước tên file: `S<số màn>_C<số ô>.png`, ví dụ `S1_C4.png`; ô Fail đặt thêm bản `CP-00X.png`

## Bước 3 — Chạy & chụp

Với mỗi ô × mỗi màn hình:

| Việc | Chi tiết |
|---|---|
| Kiểm tra hiển thị | Layout không vỡ · không scroll ngang ngoài ý muốn · chữ đọc được · ảnh/icon load đủ |
| Kiểm tra hành vi | Nút bấm được · form nhập được · dropdown/modal mở đúng · toast hiện đúng chỗ |
| Kiểm tra responsive | Ở tablet/phone: menu có chuyển sang dạng thu gọn không · bảng có scroll trong khung riêng không |
| Chụp ảnh | **Mọi ô đều chụp**, không chỉ ô Fail |
| Ghi kết quả | Pass/Fail + loại lỗi nếu Fail |

**Commit sau mỗi đợt:** `[task3][<os>-<browser>] Run 3 screens, N pass / M fail`

## Bước 4 — Phân tích lỗi theo chiều

```
Đây là kết quả ma trận tương thích của tôi: [dán 3 bảng].
1) Nhóm các Fail theo: OS / browser engine (Blink, Gecko, WebKit) / device class.
2) Với mỗi nhóm, đưa ra giả thuyết nguyên nhân kỹ thuật có thể kiểm chứng được.
3) Chỉ ra Fail nào KHÔNG phải lỗi tương thích mà là bug chung của ứng dụng
   (vì nó xuất hiện ở mọi môi trường).
4) Không suy diễn nguyên nhân nếu dữ liệu tôi cung cấp không đủ để kết luận.
```
→ **Người review:** giả thuyết của AI về nguyên nhân kỹ thuật là **giả thuyết**, không phải kết luận. Trong báo cáo phải ghi rõ là suy đoán trừ khi bạn kiểm chứng được.

## Bước 5 — Kết xuất

Điền `03-compatibility-matrix.md`: bảng ma trận từng màn hình · bảng kiểm tra độ phủ · block chi tiết cho mỗi Fail · bảng phân bố lỗi theo chiều · mục giới hạn.
Bug tương thích → `04-findings-log.md` với prefix `CP-` và submit Google Form.

---

## Checklist review trước khi đóng Task 3

- [ ] Với **từng màn hình**: đủ 3 OS, đủ 5 browser, đủ 3 device class (tự đếm lại, đừng tin bảng tự động)
- [ ] Có ảnh cho **mọi ô**, không chỉ ô Fail
- [ ] **Mọi ảnh** có overlay email MSSV + URL EMS + tên browser/OS/device
- [ ] Mỗi ô Fail có ghi chú **loại lỗi cụ thể** (overflow / overlap / vỡ layout / chữ không đọc được / control không phản hồi)
- [ ] Đã ghi rõ ô nào chạy trên **emulator** và ô nào trên **thiết bị thật**
- [ ] Đã nêu giới hạn (số phút trial, phiên bản không chọn được, iOS dùng chung WebKit…)
- [ ] Đã ghi phiên AI vào `appendix/a3-ai-audit-report.md`
