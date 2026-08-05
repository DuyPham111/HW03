# Nguồn tham khảo — Checklist GUI của nhóm

**Nhóm:** _(TODO)_ · **Bài:** HW03 Task 1A · **Ngày:** _(TODO)_

> Một trong ba sản phẩm nhóm bắt buộc của Task 1A, cùng với [`gui-checklist.md`](gui-checklist.md) và [`ai-prompts.md`](ai-prompts.md).
> Đề §6 Task 1 Phần A: *"the list of reference sources you drew on (books, articles, standards, the course slides)"*.

---

## 1. Nguồn nền tảng — đề chỉ đích danh

| # | Nguồn | Loại | Mã dùng trong checklist | Dùng cho mục nào |
|---|---|---|---|---|
| **R1** | Nielsen, J. — *10 Usability Heuristics for User Interface Design*, Nielsen Norman Group.<br>https://www.nngroup.com/articles/ten-usability-heuristics/ | Heuristic | `N1`–`N10` | G-02, G-03, G-06, G-07, G-08, G-09, G-10, G-11, F-01…F-14, N-01…N-09, S-01…S-13 |
| **R2** | Norman, D. — *The Design of Everyday Things* (bản hiệu đính 2013), 6 nguyên lý thiết kế | Nguyên lý | `P1`–`P6` | G-03, G-08, F-02, F-06, F-08, N-08 |
| **R3** | Shneiderman, B. — *Eight Golden Rules of Interface Design*.<br>https://www.cs.umd.edu/users/ben/goldenrules.html | Quy tắc | `S1`–`S8` | G-01, G-09, G-11, G-14, G-16, F-05, F-11, F-14, N-02, N-04, N-05, N-07, S-01, S-03, S-04, S-06, S-08, S-13 |
| **R4** | Slide môn học — *GUI + Usability + Compatibility Testing (AI-First, Combined)*, chương checklist theo từng widget | Slide | `SL` | G-01, G-02, G-04, G-05, F-01, S-12 |
| **R5** | ISTQB Foundation Level Syllabus (phiên bản mới nhất) | Tiêu chuẩn | — | Thuật ngữ defect, phân mức severity dùng ở `04-findings-log.md` |

**Chi tiết mã heuristic** — chép lại ở đây để khi chạy checklist không phải tra ngược:

| Nielsen | | Norman | | Shneiderman | |
|---|---|---|---|---|---|
| N1 | Visibility of system status | P1 | Visibility | S1 | Strive for consistency |
| N2 | Match between system and the real world | P2 | Feedback | S2 | Seek universal usability |
| N3 | User control and freedom | P3 | Constraints | S3 | Offer informative feedback |
| N4 | Consistency and standards | P4 | Mapping | S4 | Design dialogs to yield closure |
| N5 | Error prevention | P5 | Consistency | S5 | Prevent errors |
| N6 | Recognition rather than recall | P6 | Affordance | S6 | Permit easy reversal of actions |
| N7 | Flexibility and efficiency of use | | | S7 | Support internal locus of control |
| N8 | Aesthetic and minimalist design | | | S8 | Reduce short-term memory load |
| N9 | Help users recognize, diagnose, and recover from errors | | | | |
| N10 | Help and documentation | | | | |

## 2. Nguồn bổ sung do nhóm thêm

| # | Nguồn | Loại | Mã | Dùng cho mục nào |
|---|---|---|---|---|
| **R6** | W3C — *Web Content Accessibility Guidelines (WCAG) 2.2*.<br>https://www.w3.org/TR/WCAG22/ | Tiêu chuẩn | `W` | G-14 (SC 1.4.3 Contrast Minimum) · G-15 (SC 1.4.4 Resize Text) · F-13 (SC 2.4.7 Focus Visible) · S-02, S-04, S-05 (SC 1.4.1 Use of Color) |
| **R7** | Tài liệu *Kịch bản E2E Test Flow — Luồng Admin* của đội phát triển EMS | Tài liệu SUT | `E` | Căn cứ mô tả widget phía admin: upload 4:3 + 24:9, RichTextEditor, kéo-thả reorder, progress bar duyệt đăng ký, màu trạng thái participant |
| **R8** | _(TODO — thêm nếu nhóm dùng thêm nguồn nào, ví dụ Material Design guidelines hoặc bài NN/g về empty state)_ | | | |

## 3. Nguồn quan sát từ chính EMS

Đây là nguồn **quan trọng nhất cho phần human review** — 14 mục `RV` trong checklist đều bắt nguồn từ đây, không đến từ sách vở. Lý do AI bỏ sót từng mục ghi ở [`ai-prompts.md`](ai-prompts.md) §3.

**Đợt khảo sát 1 — 05/08/2026**, tài khoản `23127183@student.hcmus.edu.vn`, 10 ảnh lưu tại `docs/khao-sat/`. Phiếu khảo sát đầy đủ: `docs/KHAO_SAT_EMS.md`.

| # | Quan sát trên EMS | Màn hình | Dẫn tới mục |
|---|---|---|---|
| O1 | Nhiều thẻ sự kiện hiện ô ảnh placeholder xám không giải thích | B1 danh sách | `G-06` |
| O2 | Empty state chỉ có câu "No events found", không có nút xoá bộ lọc | B1 sau khi lọc | `G-07` |
| O3 | Trường Location bỏ trống hiển thị dấu `-` | B2 chi tiết sự kiện | `G-09` |
| O4 | Tiêu đề chính của sự kiện là chuỗi mã `23127326_UT_510_15:36`, tên thật nằm ở dòng phụ | B1, B2 | `G-10` |
| O5 | Tên vai trò hiện "Người dự" (tiếng Việt) trong khi giao diện đang tiếng Anh | B2 khối Registration roles | `G-12` |
| O6 | Sự kiện hết chỗ chỉ báo "Role is full", không mời vào danh sách chờ dù ô `Waitlisted` tồn tại | B2 Workshop B | `F-12` |
| O7 | Trang chi tiết không có breadcrumb hay nút quay lại danh sách | B2 cả 4 trạng thái | `N-02` |
| O8 | Mở deep link khi chưa đăng nhập bị chặn cả trang bằng "Please sign in to view this event." | B2 | `N-04` |
| O9 | Badge trạng thái dùng cả màu lẫn chữ (Upcoming tím, Ended xám, Pending vàng, Waitlisted tím) | B1, B2 | `S-04` |
| O10 | Card `Slot available` đổi nền xanh → hồng khi hết chỗ | B2 Workshop A vs B | `S-05` |
| O11 | Khối vai trò có 4 ô số liệu ở Workshop B nhưng chỉ 3 ô ở Workshop C (thiếu `Waitlisted`) | B2 | `S-06` |
| O12 | Carousel SPOTLIGHT EVENT ở trang chủ đang hiển thị một sự kiện có badge "Ended" | B1 | `S-07` |
| O13 | Ngày giờ toàn hệ thống dùng `dd/MM/yyyy HH:mm`, không hiển thị múi giờ ở bất kỳ đâu | B1, B2 | `S-09` |
| O14 | Màn chặn đăng nhập dùng nút ghi `login` chữ thường, lệch với các nút Title Case khác | B2 | `S-13` |

## 4. Đối chiếu độ phủ heuristic

Kiểm tra checklist không dồn hết vào vài heuristic dễ.

| Heuristic | Số mục | Heuristic | Số mục |
|---|:--:|---|:--:|
| N1 Visibility of system status | 9 | S1 Consistency | 4 |
| N2 Match real world | 4 | S2 Universal usability | 3 |
| N3 User control and freedom | 5 | S3 Informative feedback | 2 |
| N4 Consistency and standards | 10 | S4 Dialogs yield closure | 1 |
| N5 Error prevention | 5 | S5 Prevent errors | 0 ⚠️ |
| N6 Recognition not recall | 3 | S6 Easy reversal | 3 |
| N7 Flexibility and efficiency | 4 | S7 Internal locus of control | 4 |
| N8 Aesthetic and minimalist | 3 | S8 Reduce memory load | 0 ⚠️ |
| N9 Recover from errors | 5 | Norman P1–P6 | 5 |
| N10 Help and documentation | 0 ⚠️ | WCAG | 6 |

⚠️ **Ba heuristic đang bằng 0** — cần quyết định trước khi chốt v1.0:
- **N10 Help & documentation** — EMS có mục `User guide` trên header. Cân nhắc thêm 1 mục: *"Có đường vào tài liệu hướng dẫn từ mọi màn hình, và nội dung hướng dẫn khớp với giao diện hiện tại."*
- **S5 Prevent errors** — trùng ý với N5, có thể chấp nhận để trống và ghi chú là cố ý.
- **S8 Reduce memory load** — cân nhắc thêm 1 mục: *"Thông tin cần để ra quyết định (số chỗ còn lại, hạn đăng ký) hiển thị ngay tại chỗ ra quyết định, không bắt người dùng nhớ từ trang trước."*

> Nếu thêm 2 mục trên thì tổng thành **54** — vẫn nằm trong khoảng đã chốt. **Cần bạn quyết định.**
