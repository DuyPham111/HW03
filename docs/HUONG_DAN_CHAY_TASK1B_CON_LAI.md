# HƯỚNG DẪN CHẠY 19 MỤC CÒN LẠI CỦA TASK 1B

**Cập nhật 06/08/2026 — bản rút gọn.** 42/61 dòng đã xong hoàn toàn (cả 3 màn). Chỉ còn đúng 19 dòng dưới đây, chia làm 2 nhóm.

> Điền xong dòng nào thì báo tôi theo mẫu cũ: **tên item + màn hình + Passed/Failed/N-A + (ảnh nếu Failed)**.

---

## NHÓM A — 8 dòng chỉ cần XÁC NHẬN N/A (3 phút)

Đã dự đoán `(?)` từ đầu vì widget chỉ có ở phía admin. Lướt qua B1/B2/B4 xác nhận đúng là không thấy, rồi báo tôi một câu **"nhóm A đã xác nhận"** — không cần trả lời riêng từng dòng.

| ID | Lý do N/A đã ghi sẵn |
|---|---|
| F-08, F-09, F-10 | Không có ô upload ảnh / rich-text editor ở B1/B2/B4 |
| F-15, F-16 | Không có form ngày/upload nào ở B1/B2/B4 |
| N-07, N-08 | Không có sidebar hay danh sách kéo-thả ở phía student |
| S-16 | Không có dashboard KPI ở B1/B2/B4 |

---

## NHÓM B — 11 dòng cần nhìn thật (15–20 phút)

### Nhìn nhanh, không cần thao tác đặc biệt (5 dòng)

- **G-01** — Căn lề & khoảng cách: các khối trên cùng 1 màn có thẳng hàng nhau không, khoảng cách giữa chúng có đều không. Kiểm cả 3 màn.
- **G-02** — Font & cỡ chữ: toàn hệ thống có dùng quá 2 họ font không; tiêu đề/nội dung/chú thích có phân cấp cỡ chữ rõ ràng và giữ nguyên giữa các trang không.
- **G-03** — Màu đúng ngữ nghĩa: màu đỏ có bị dùng cho thứ không phải lỗi/phá huỷ không (vd nút thường, thông tin trung tính bị tô đỏ nhầm).
- **G-16** — Chữ tiếng Việt dài (menu, tên nút, tiêu đề) có bị vỡ dòng xấu, cắt bằng `…`, hay đẩy layout không.
- **S-02** — Mở lại 1 toast bất kỳ đã từng thấy (vd sau khi Save event, hoặc sau khi admin duyệt — xem lại `KS_NOTIF_approved.png` nếu cần) — toast đó có phân biệt được loại (thành công/lỗi) bằng **cả màu lẫn icon/chữ**, không chỉ màu; và có đứng đủ lâu để đọc hết không.

Cả 5 dòng trên áp dụng chung cho cả 3 màn — nhìn 1 lượt, ghi kết quả riêng từng màn nếu khác nhau.

### F-01 đến F-06 (6 dòng) — nhiều khả năng N/A hết, xác nhận nhanh

> ⚠️ Đã cảnh báo trước: khối đăng ký ở B2 chỉ có **checkbox chọn vai trò**, không có ô nhập chữ tự do nào. Các item này (nhãn trường nhập, dấu `*` bắt buộc, vị trí lỗi cạnh trường, giữ dữ liệu khi lỗi, chặn ràng buộc tại chỗ nhập) đều giả định có **ô nhập text/số** — mà B2 không có.

Mở lại B2, nhìn khối `Registration roles` 10 giây: có ô nhập chữ/số nào không, hay chỉ có checkbox? Nếu đúng chỉ có checkbox thì đánh N/A cả 6 dòng (F-01, F-02, F-03, F-04, F-05, F-06) cho cả 3 màn, lý do chung: *"Không có trường nhập tự do nào trên B1/B2/B4 — khối đăng ký chỉ có checkbox chọn vai trò"*. Báo tôi 1 câu xác nhận, tôi điền hàng loạt.

Nếu bạn thấy có ô nhập nào tôi chưa biết (vd ô ghi chú khi đăng ký?) thì báo riêng, tôi sẽ hướng dẫn test cụ thể cho ô đó.

---

## Sau khi xong Nhóm A + B

Bảng chạy checklist coi như **hoàn tất 61/61 dòng × 3 màn**. Việc còn lại:

1. Chạy lệnh đếm cuối cùng (đã có sẵn trong `01-checklist-execution.md`) để lấy số Passed/Failed/N-A chính xác, điền vào **Bảng tổng hợp** đầu file.
2. Đối chiếu `04-findings-log.md` — hiện có **37 finding**, kiểm lại severity một lượt (đề nói rõ severity là AI đề xuất, bạn phải tự duyệt).
3. Bắt đầu Task 2 (nếu chưa xong) hoặc Task 3 (cross-platform matrix) — cả hai đều dùng lại đúng 61-item checklist này.
