# Nguồn tham khảo — Checklist GUI của nhóm

**Nhóm:** 10 · **Bài:** HW03 Task 1A · **Ngày:** 05–06/08/2026

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

Đây là nguồn **quan trọng nhất cho phần human review** — 23 mục `RV` trong checklist đều bắt nguồn từ đây, không đến từ sách vở. Lý do AI bỏ sót từng mục ghi ở [`ai-prompts.md`](ai-prompts.md) §3.

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

**Đợt khảo sát 2 — 06/08/2026**, thêm 9 ảnh (`admin-1..5`, `profile-1/2`, `check-in-profile`, `KS_B2_workshop-d`) và đối chiếu với *Hướng dẫn sinh viên — HCMUS EMS* (R6). Đợt này chạm được vào **form Create Event phía admin**, **trang My Profile** và **Admin Dashboard** — ba vùng mà đợt 1 chưa mở tới.

| # | Quan sát trên EMS | Màn hình | Dẫn tới mục |
|---|---|---|---|
| O15 | Menu `User guide` có mặt cả trên header student lẫn sidebar admin. ✅ Đã mở: tài liệu **chỉ có tiếng Việt** dù giao diện đang ở tiếng Anh, và **không chỗ nào nói mã QR nằm ở đâu** | Header B1–B4, sidebar admin | `N-12` |
| O16 | Upload ảnh sự kiện có **hai tỉ lệ bắt buộc 4:3 và 24:9**, giao diện **không ghi giới hạn dung lượng, định dạng hay số lượng file** ở bất kỳ đâu | Admin — Create Event | `F-15` |
| O17 | Form có **6 trường thời gian phụ thuộc lẫn nhau** (`Start`/`End`, `Check-in Open`/`Close`, `Registration Open`/`Close`) — ✅ đã thử: nhập End trước Start, Check-in Close trước Check-in Open, Registration Close trước Registration Open đều **nhận hết, không báo gì trong lúc nhập**; lỗi chỉ hiện sau khi bấm Publish | Admin — Create Event | `F-16` |
| O18 | Mã QR check-in nằm ở **nút riêng trên đầu trang Profile**, tách hoàn toàn khỏi chỗ đăng ký lẫn danh sách My Activities — không có đường dẫn nào nối hai chỗ | B2, B4 | `N-10` |
| O19 | Phân trang My Activities gồm 4 điều khiển: `Rows per page: 10` · `1-2 of 2 results` · `Go to page __ / 1` · nút `‹ 1 ›` | B4 | `N-11` |
| O20 | Sau khi đăng ký xong, ✅ đã xác nhận: **không toast, không thông báo, không chỉ dẫn** — trang đứng yên, chỉ mọc thêm badge `Pending review` | B2 → B4 | `S-14` |
| O21 | **Ba bộ từ vựng khác nhau cho cùng khái niệm trạng thái**: tài liệu chính thức dùng `Approved`/`Pending Review`/`Rejected`/`Waitlisted`; ô đếm trên B2 dùng `Registered`/`Pending`/`Confirmed`/`Waitlisted`; badge trên B4 dùng `Pending review`/`Student participation`/`Upcoming` | Tài liệu, B2, B4 | `S-15` |
| O22 | ✅ **Cả 4 thẻ KPI đều bằng 0** (`Total Events`, `Total Check-ins`, `Attendance Rate`, `Total Users`) trong khi badge `Support requests` ngay cạnh đó hiện **17** | Admin Dashboard | `S-16` |
| O23 | Số chỗ còn lại và hạn đăng ký hiển thị trên B2 (`Slot available — Student: 49`, `Registered 1/1`) ⚠️ *(khối đăng ký nằm ngay trong B2 nên thông tin vẫn trong tầm mắt — cần kiểm lại khi cuộn trang trên màn hình nhỏ)* | B2 | `S-17` |

**Đợt khảo sát 3 — 06/08/2026 (đêm).** Chín quan sát trên được kiểm lại bằng thao tác thật, thêm 14 ảnh. Tám trong chín đã chuyển từ ⚠️ sang ✅ và trở thành finding chính thức trong [`../04-findings-log.md`](../04-findings-log.md). Đợt này cũng lật lại một giả định của chính tôi: `O7` ghi B2 không có nút quay lại, nhưng ở chế độ xem công khai chưa đăng nhập thì nút `Back to events` LẠI CÓ — chưa rõ là khác biệt theo trạng thái đăng nhập hay tôi quan sát sót ở đợt 1, cần kiểm lại khi chạy `N-02`.

## 4. Đối chiếu độ phủ heuristic

Kiểm tra checklist không dồn hết vào vài heuristic dễ. Số liệu dưới đây **đếm lại bằng lệnh** trên cột `Nguồn` của [`gui-checklist.md`](gui-checklist.md) ngày 06/08/2026 — một mục trích nhiều nguồn thì được tính cho từng nguồn, nên tổng cột lớn hơn 61.

| Nielsen | Số mục | Shneiderman | Số mục | Khác | Số mục |
|---|:--:|---|:--:|---|:--:|
| N1 Visibility of system status | 18 | S1 Consistency | 6 | P1 Visibility | 0 ◇ |
| N2 Match real world | 4 | S2 Universal usability | 3 | P2 Feedback | 2 |
| N3 User control and freedom | 6 | S3 Informative feedback | 2 | P3 Constraints | 5 |
| N4 Consistency and standards | 12 | S4 Dialogs yield closure | 2 | P4 Mapping | 0 ◇ |
| N5 Error prevention | 7 | S5 Prevent errors | 0 ◇ | P5 Consistency | 1 |
| N6 Recognition not recall | 5 | S6 Easy reversal | 3 | P6 Affordance | 1 |
| N7 Flexibility and efficiency | 4 | S7 Internal locus of control | 5 | WCAG 2.2 | 6 |
| N8 Aesthetic and minimalist | 2 | S8 Reduce memory load | 1 | Slide môn học | 6 |
| N9 Recover from errors | 5 | | | | |
| N10 Help and documentation | 1 | | | | |

**Đọc bảng này thế nào**

- **Không heuristic nào của Nielsen bị bỏ trống.** N10 từng bằng 0; đã đóng bằng `N-12` sau khi khảo sát thấy `User guide` nằm trên header cả phía student lẫn sidebar admin (`admin-1.png`, quan sát O15).
- **S8 cũng từng bằng 0**, đã đóng bằng `S-17` — thông tin ra quyết định (số chỗ còn lại, hạn đăng ký) phải nằm ngay tại chỗ ra quyết định.
- **Ba ô còn 0 là cố ý**, ký hiệu ◇ chứ không phải ⚠️. `P1 visibility` và `P4 mapping` của Norman, cùng `S5 prevent errors` của Shneiderman, **trùng nghĩa** với `N1` (18 mục), `N2`/`N6` (9 mục) và `N5` (7 mục). Thêm mục chỉ để lấp ô sẽ tạo mục trùng nội dung — làm loãng checklist chứ không tăng độ phủ thật. Nhóm chọn ghi rõ lý do thay vì nhồi số.
- **N1 chiếm 18/61 là có chủ ý, không phải lệch.** IA-04 *feedback / state* là một trong bốn khía cạnh bắt buộc, và bản chất của nó là "hệ thống có cho tôi biết chuyện gì đang xảy ra không" — tức chính N1.

> ⚠️ **Cần verify:** đã thấy mục `User guide` trên header nhưng **chưa mở nội dung bên trong**. Trước khi chạy `N-12` ở Task 1B phải mở thật để đối chiếu tài liệu với giao diện đang chạy.
> - [ ] Đã mở `User guide` và đối chiếu nội dung
