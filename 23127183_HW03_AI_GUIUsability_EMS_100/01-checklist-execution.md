# Checklist Execution — Task 1B

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183) · **Kịch bản:** B — User đăng ký tham dự sự kiện
**Checklist nguồn:** `team/gui-checklist.md` v1.1 — **61 item**
**Ngày chạy:** _(TODO)_ · **Môi trường chạy:** _(TODO: OS + browser + độ phân giải)_

> **Luật của đề:** mọi item phải được đánh **Passed** hoặc **Failed** cho **từng màn hình**. Cột **Notes** bắt buộc điền **lý do fail** với mỗi item Failed. Ảnh chụp **chỉ cần cho item Failed**.
> Ký hiệu: `P` Passed · `F` Failed · `N/A` không áp dụng (**phải ghi lý do ở Notes**, không được để trống) · *(trống)* = chưa chạy — **không được để trống khi nộp**.
> Màn hình: **S1 = B1** Danh sách sự kiện · **S2 = B2** Trang chi tiết sự kiện (gồm khối đăng ký) · **S3 = B4** My Profile — QR Code + My Activities.

---

## Trước khi chạy — 2 việc bắt buộc

1. **Đăng nhập** `23127183@student.hcmus.edu.vn`. Dữ liệu thử đã có sẵn (xem `docs/KHAO_SAT_EMS.md` mục 3): Workshop A (còn chỗ) · B (hết chỗ, có Waitlist) · C (đóng đăng ký) · D (đã kết thúc) · Public Event Test (bật công khai) · TEST validation.
2. **Đọc cột Notes trước khi tự tìm.** Với những item đã có 🔎, tôi đã tra cứu chéo với 27 finding trong `04-findings-log.md` và đợt khảo sát 05–06/08 — chỉ cần **xác nhận lại nhanh** (mở đúng màn hình, nhìn có đúng như mô tả không) thay vì điều tra lại từ đầu. Đây **chỉ là gợi ý tra cứu, không phải kết quả đã chốt** — bạn vẫn phải tự xác nhận Passed/Failed, không được copy thẳng.
   - `(?)` trước ID = tôi dự đoán N/A ở cả 3 màn vì widget đó chỉ có ở phía admin (Create Event, Dashboard) — dự đoán này *chưa chắc đúng*, tự xác nhận rồi mới điền N/A + lý do.

---

## Bảng tổng hợp

| Màn hình | Tổng item | Passed | Failed | N/A | Tỉ lệ pass |
|---|:--:|:--:|:--:|:--:|:--:|
| S1 — B1 Danh sách sự kiện | | | | | |
| S2 — B2 Trang chi tiết sự kiện | | | | | |
| S3 — B4 My Profile — QR Code + My Activities | | | | | |
| **Tổng** | **61×3=183** | | | | |

> Tỉ lệ pass tính trên `Passed / (Passed + Failed)`, **không tính N/A vào mẫu số** — đúng quy ước ở `team/gui-checklist.md`.

---

## Bảng chạy hợp nhất

| ID | Item (rút gọn) | IA | S1 | S2 | S3 | Notes | Bug-ID | Ảnh |
|---|---|:--:|:--:|:--:|:--:|---|---|---|
| G-01 | Căn lề & khoảng cách nhất quán giữa các khối | IA-01 | | | | | | |
| G-02 | Font tối đa 2 họ; cỡ chữ phân cấp nhất quán | IA-01 | | | | | | |
| G-03 | Màu đúng ngữ nghĩa; đỏ chỉ dành cho lỗi/phá huỷ | IA-01 | | | | | | |
| G-04 | Không có thanh cuộn ngang ngoài ý muốn ≥1280px | IA-01 | | | | | | |
| G-05 | Ảnh giữ đúng tỉ lệ khung, không méo/cắt mất nội dung | IA-01 | | | | | | |
| G-06 | Ảnh lỗi có khối giữ chỗ có ý nghĩa, không ô xám trơn | IA-01 | Failed | Failed | | S1 = `SV-B1-04` (ô xám trơn, không chữ)<br>S2 = quan sát mới trên banner sự kiện `23127326_UT_510_15:36` — chỉ có icon ảnh chung chung, không nhãn chữ | S1: `SV-B1-04`<br>S2: `CL-B2-01` | S1: [KS_B1_the-su-kien.png](evidence/survey/KS_B1_the-su-kien.png)<br>S2: [G-06-S2.png](evidence/task1b/G-06-S2.png) |
| G-07 | Empty state nêu lý do + gợi ý hành động tiếp theo | IA-01 | ⚠️ chờ xác nhận | N/A | ⚠️ chờ retest | S1: đã nêu lý do ("There are no events matching your filters"), có icon `Filters 3` kèm 1 icon nhỏ cạnh đó **chưa rõ có phải nút xoá bộ lọc không** — bạn bấm thử xem có xoá filter không rồi báo lại, khi đó tôi chốt Passed/Failed và sửa `SV-B1-02` nếu cần.<br>S2: không có tính năng filter trên trang chi tiết sự kiện — N/A hợp lý.<br>S3: **không kiểm chứng được lúc này** — bộ lọc `Start Date Range` không hoạt động (`CL-B4-01`) nên không bao giờ ra kết quả rỗng thật để đánh giá UI của empty state. Thử lại bằng ô `Search activities` với từ khoá vô nghĩa (thay vì lọc ngày) để ép ra được empty state thật, rồi báo tôi. | | S1: [G-07-S1.png](evidence/task1b/G-07-S1.png)<br>S3: [G-07-S3.png](evidence/task1b/G-07-S3.png) |
| G-08 | Loading có skeleton/spinner, bố cục không nhảy khi data về | IA-01 | | | | | | |
| G-09 | Giá trị rỗng dùng cùng 1 ký hiệu thống nhất | IA-01 | | | | 🔎 quan sát O3 (Location "-" trên B2), chưa có SV-ID riêng | | |
| G-10 | Nhãn dùng ngôn ngữ người dùng, không phơi mã định danh nội bộ | IA-01 | | | | 🔎 khớp `SV-B1-03` (B1+B2) | | |
| G-11 | EN/VI dịch toàn bộ text kể cả toast/tooltip/lỗi | IA-01 | | | | | | |
| G-12 | Dữ liệu hiển thị (tên vai trò...) theo đúng ngôn ngữ đang chọn | IA-01 | | | | 🔎 khớp `SV-B2-02` (B2) | | |
| G-13 | Ngôn ngữ đã chọn được lưu, giữ nguyên sau reload | IA-01 | | | | | | |
| G-14 | Tương phản chữ/nền ≥4.5:1 thường, ≥3:1 chữ lớn | IA-01 | | | | | | |
| G-15 | Đọc được, không vỡ bố cục khi zoom 200% | IA-01 | | | | | | |
| G-16 | Text VI dài hơn không vỡ nút/cắt chữ/gãy từ | IA-01 | | | | | | |
| F-01 | Mọi trường có nhãn hiển thị thường trực, không chỉ placeholder | IA-02 | | | | | | |
| F-02 | Trường bắt buộc đánh dấu nhất quán (vd `*`), có chú giải | IA-02 | | | | | | |
| F-03 | Lỗi hiện ngay cạnh trường, trong tầm nhìn, không chỉ toast | IA-02 | | | | | | |
| F-04 | Thông báo lỗi nói rõ cách khắc phục | IA-02 | | | | | | |
| F-05 | Validate fail vẫn giữ nguyên dữ liệu đã nhập | IA-02 | | | | | | |
| F-06 | Ràng buộc chặn ngay tại chỗ nhập, không chỉ sau submit | IA-02 | | | | | | |
| F-07 | Nút submit khoá khi form chưa hợp lệ; bấm đúp không tạo trùng | IA-02 | | | | | | |
| (?) F-08 | Upload kiểm định dạng/dung lượng, báo giới hạn trước | IA-02 | | | | (?) dự đoán N/A cả 3 màn — upload chỉ có ở admin Create Event | | |
| (?) F-09 | Upload có preview đúng tỉ lệ trước khi lưu | IA-02 | | | | (?) dự đoán N/A cả 3 màn — cùng lý do F-08 | | |
| (?) F-10 | Rich-text có đủ nút định dạng, dán không vỡ bố cục | IA-02 | | | | (?) dự đoán N/A cả 3 màn — rich-text chỉ có ở admin | | |
| F-11 | Hành động không hoàn tác có bước xác nhận/tóm tắt trước khi gửi | IA-02 | | | | 🔎 đối chiếu với `S-03` (dialog Cancel registration) | | |
| F-12 | Lựa chọn bị khoá nêu rõ lý do + lựa chọn thay thế | IA-02 | | | | 🔎 khớp `SV-B2-01` (B2, "Role is full" không mời waitlist) | | |
| F-13 | Ô nhập có focus nhìn thấy được; Tab đi đúng thứ tự | IA-02 | | | | | | |
| F-14 | Form/modal đóng bằng Esc, cảnh báo nếu còn dữ liệu chưa lưu | IA-02 | | | | | | |
| (?) F-15 | Upload nêu rõ giới hạn dung lượng/số lượng file | IA-02 | | | | (?) dự đoán N/A cả 3 màn — khớp `SV-ADM-01` nhưng đó là màn admin | | |
| (?) F-16 | Cặp trường thời gian phụ thuộc nhau chặn cấu hình vô lý | IA-02 | | | | (?) dự đoán N/A cả 3 màn — khớp `SV-ADM-03/04/05` nhưng đó là màn admin | | |
| N-01 | Menu chính nhất quán mọi trang, mục đang xem nổi bật | IA-03 | | | | | | |
| N-02 | Trang chi tiết có đường quay lại danh sách (không chỉ dựa Back) | IA-03 | | | | 🔎 khớp `SV-B2-03` (B2) — ⚠️ nhánh Public Event lại CÓ nút `Back to events`, kiểm cả 2 nhánh | | |
| N-03 | Back trình duyệt giữ nguyên bộ lọc/trang/vị trí cuộn | IA-03 | | | | | | |
| N-04 | Sau đăng nhập quay lại đúng trang vừa yêu cầu, không về home | IA-03 | | | | | | |
| N-05 | URL phản ánh trạng thái (tab/lọc/trang) để share/reload đúng | IA-03 | | | | | | |
| N-06 | Đổi tab/lọc tải đúng dữ liệu, giữ trạng thái khi quay lại | IA-03 | | | Failed | S3 = `CL-B4-01` — lọc `Start Date Range` không thu hẹp kết quả, hoạt động ngoài khoảng ngày vẫn hiện | `CL-B4-01` | [G-07-S3.png](evidence/task1b/G-07-S3.png) |
| (?) N-07 | Sidebar thu/mở được, không che nội dung chính | IA-03 | | | | (?) dự đoán N/A cả 3 màn — phía student dùng header, không có sidebar (sidebar chỉ thấy ở admin-1.png) | | |
| (?) N-08 | Kéo-thả có tay cầm rõ, phản hồi thị giác, lưu đúng thứ tự | IA-03 | | | | (?) dự đoán N/A cả 3 màn — kéo-thả chỉ có ở admin | | |
| N-09 | Không có liên kết hỏng, không rơi 404 | IA-03 | | | | | | |
| N-10 | Chức năng cần ngay sau thao tác nằm trong tầm với ngữ cảnh đó | IA-03 | | | | 🔎 khớp `SV-B4-01` (QR tách rời) + `SV-B2-09` (không chỉ dẫn sau đăng ký) | | |
| N-11 | Danh sách dài có phân trang rõ ràng, dùng chung 1 kiểu | IA-03 | | | | 🔎 quan sát O19 (My Activities: `Rows per page` · `Go to page`) — mới mô tả cấu trúc, chưa kết luận | | |
| N-12 | Có đường vào tài liệu hướng dẫn, nội dung khớp giao diện đang chạy | IA-03 | | | | 🔎 khớp `SV-UG-01` (chỉ có tiếng Việt dù UI đang EN, không nói QR ở đâu) | | |
| S-01 | Hành động thay đổi dữ liệu có phản hồi tức thì, vị trí nhất quán | IA-04 | | | | ⚠️ đối chiếu `SV-B2-09` — đăng ký xong KHÔNG có toast, khả năng cao Failed | | |
| S-02 | Toast phân biệt cả màu lẫn icon/chữ, đủ lâu để đọc | IA-04 | | | | | | |
| S-03 | Hành động không hoàn tác có dialog nêu rõ hậu quả | IA-04 | | | | 🔎 khớp `SV-B2-07` (dialog Cancel chỉ hỏi "are you sure", không nêu hậu quả) | | |
| S-04 | Badge trạng thái có cả màu lẫn nhãn chữ, nhất quán mọi màn | IA-04 | | | | 🔎 quan sát O9 — có vẻ **ĐÃ ĐẠT** (Upcoming tím/Ended xám/Pending vàng đều kèm chữ), xác nhận lại | | |
| S-05 | Khối đổi màu theo trạng thái phải kèm nhãn chữ giải thích | IA-04 | | | | 🔎 quan sát O10 (Slot xanh→hồng khi hết chỗ) — chưa rõ có kèm chữ giải thích ý nghĩa màu không | | |
| S-06 | Khối chức năng giữ nguyên số ô giữa các bản ghi cùng loại | IA-04 | | | | 🔎 khớp `SV-B2-04` (Workshop B 4 ô vs Workshop C 3 ô) | | |
| S-07 | Nội dung nổi bật trang chủ chỉ hiện bản ghi còn hiệu lực | IA-04 | | | | 🔎 khớp `SV-B1-01` (carousel hiện sự kiện đã `Ended`) | | |
| S-08 | Tác vụ chạy lâu có progress/spinner kèm chỉ báo bước/thời gian | IA-04 | | | | | | |
| S-09 | Ngày giờ 1 định dạng thống nhất, nêu múi giờ ở hạn chót | IA-04 | | | | 🔎 quan sát O13 (dd/MM/yyyy HH:mm, không có múi giờ ở đâu cả) | | |
| S-10 | Bộ đếm/nhãn trạng thái thời gian khớp dữ liệu ngày giờ cạnh nó | IA-04 | | | | | | |
| S-11 | Mất mạng báo rõ, cho biết thao tác vừa rồi có lưu không | IA-04 | | | | | | |
| S-12 | QR/barcode đủ lớn, sắc nét, không co méo màn hình nhỏ | IA-04 | | N/A | | S2 chắc chắn N/A — QR chỉ ở B4 (S3), không xuất hiện trên B2 | | |
| S-13 | Nhãn nút/tiêu đề dùng cùng 1 quy ước viết hoa toàn hệ thống | IA-04 | | | | 🔎 khớp `SV-B2-05` (nút `login` chữ thường, lệch Title Case) | | |
| S-14 | Sau khi hoàn tất thao tác, hệ thống chỉ đường bước tiếp theo | IA-04 | | | | 🔎 khớp `SV-B2-09` (đăng ký xong không toast, không chỉ dẫn tìm My Activities) | | |
| S-15 | Một khái niệm trạng thái dùng 1 bộ từ vựng duy nhất | IA-04 | | | | 🔎 khớp `SV-B4-03` (3 bộ từ vựng: tài liệu / B2 / B4) | | |
| (?) S-16 | Chỉ số dashboard khớp dữ liệu thật, không hiện 0 sai | IA-04 | | | | (?) dự đoán N/A cả 3 màn — khớp `SV-ADM-02` nhưng đó là màn admin | | |
| S-17 | Thông tin ra quyết định (chỗ còn lại, hạn) hiện ngay tại chỗ quyết định | IA-04 | | | | 🔎 có vẻ **ĐÃ ĐẠT** trên B2 (`Slot available`, `Registration period` hiện ngay tại khối đăng ký), xác nhận lại | | |

> **Đếm nhanh:** G 16 · F 16 · N 12 · S 17 = **61 dòng**, khớp `team/gui-checklist.md`. Đếm lại bằng `grep -cE "^\| (\(\?\) )?[GFNS]-" 01-checklist-execution.md` trước khi nộp.

---

## Chi tiết các item Failed

Mỗi item Failed → 1 block. Đây là nguồn trực tiếp để tạo bug entry trong `04-findings-log.md`. Với item đã trùng một finding `SV-` có sẵn — **không tạo Bug-ID `CL-` mới**, ghi thẳng `= SV-xxx` ở Notes của bảng trên và **không submit Google Form lần hai** (xem cảnh báo chống đếm trùng ở `04-findings-log.md`).

### [F-01] `G-06` — Ảnh lỗi không có khối giữ chỗ có ý nghĩa — Màn hình: S2 (B2)

- **Kết quả:** ❌ Failed
- **Kỳ vọng (theo item checklist):** Ảnh không tải được phải hiện khối giữ chỗ có ý nghĩa (tên viết tắt, icon kèm nhãn chữ), không để ô xám trơn/icon chung chung không giải thích.
- **Thực tế quan sát:** Banner đầu trang chi tiết sự kiện `23127326_UT_510_15:36` (sự kiện của sinh viên khác, không có ảnh upload) chỉ hiện một icon hình ảnh generic ở giữa khung viền nét đứt, không có chữ giải thích nào đi kèm.
- **Các bước tái hiện:**
  1. Mở `https://prod-dev.ems-fitus.cloud/events/114`
  2. Nhìn banner ngay dưới nút `Back to events`
- **Heuristic bị vi phạm:** N1 (visibility of system status) · N8 (aesthetic and minimalist — nhưng thiếu thông tin cần thiết)
- **Severity:** 1 — cùng mức với `SV-B1-04`, chỉ ảnh hưởng thẩm mỹ/rõ ràng, không chặn tác vụ
- **Bug-ID trong log:** `CL-B2-01`
- **Ảnh:** `evidence/task1b/G-06-S2.png`

![CL-B2-01](evidence/task1b/G-06-S2.png)

> Ghi chú thêm: ảnh này cũng tái xác nhận `SV-B1-03` — tiêu đề chính vẫn là chuỗi mã máy `23127326_UT_510_15:36`, tên thật `Workshop Kỹ năng nghiên cứu 2026` bị đẩy xuống dòng phụ. Không tạo entry riêng vì đã trùng `SV-B1-03`.

### [F-02] `N-06` (đối chiếu chéo với `G-07`) — Bộ lọc `Start Date Range` không lọc dữ liệu thật — Màn hình: S3 (B4)

- **Kết quả:** ❌ Failed
- **Kỳ vọng (theo item checklist):** Đổi bộ lọc phải tải đúng dữ liệu tương ứng với điều kiện đã chọn.
- **Thực tế quan sát:** Đặt `Start Date Range` = `25/07/2026` → `29/07/2026` trên khối Filters của My Activities. Danh sách vẫn hiện đủ 2 thẻ hoạt động (`Workshop A` ngày sự kiện `06/08/2026`, `Workshop B` ngày sự kiện `05/08/2026`) — cả hai đều nằm **hoàn toàn ngoài** khoảng đã lọc. Bộ lọc không thu hẹp kết quả chút nào.
- **Các bước tái hiện:**
  1. Đăng nhập, vào My Profile → tab My Activities
  2. Bấm `Filters`
  3. Nhập `Start Date Range` = `25/07/2026` đến `29/07/2026`
  4. Quan sát danh sách bên dưới — vẫn hiện đủ các thẻ không khớp khoảng ngày
- **Heuristic bị vi phạm:** N1 (visibility of system status — kết quả không phản ánh đúng điều kiện lọc) · N4 (consistency)
- **Severity:** 3 (đề xuất) — người dùng không thể tin vào kết quả lọc, nhưng không chặn hẳn tác vụ chính (vẫn xem được toàn bộ My Activities). **Bạn tự duyệt lại severity này.**
- **Bug-ID trong log:** `CL-B4-01`
- **Ảnh:** `evidence/task1b/G-07-S3.png`

![CL-B4-01](evidence/task1b/G-07-S3.png)

> Hệ quả phụ: vì bộ lọc không bao giờ trả về 0 kết quả, không thể quan sát được trạng thái rỗng thật ở S3 để chấm `G-07`. Xem ghi chú ở dòng `G-07` trong bảng — cần thử lại bằng ô Search với từ khoá vô nghĩa để ép ra empty state thật.

### [F-03] `G-XX / F-XX / N-XX / S-XX` — _(tên item)_ — Màn hình: _(TODO)_

- **Kết quả:** ❌ Failed
- **Kỳ vọng (theo item checklist):** _(TODO)_
- **Thực tế quan sát:** _(TODO)_
- **Các bước tái hiện:**
  1. _(TODO)_
  2. _(TODO)_
- **Heuristic bị vi phạm:** _(TODO — N?/P?/S?)_
- **Severity:** _(TODO: 0–4)_
- **Bug-ID trong log:** `CL-B?-0?` *(chỉ tạo mới nếu KHÔNG trùng finding `SV-` nào có sẵn)*
- **Ảnh:** `evidence/task1b/CL-B?-0?.png`

---

## Ghi chú độ phủ

- [ ] Mọi item trong checklist chung đều đã được đánh giá trên **cả 3 màn hình** (không còn ô trống)
- [ ] Mọi ô Failed đều có Notes + Bug-ID (hoặc `= SV-xxx`) + ảnh
- [ ] Mọi ô N/A đều có lý do ở Notes — kể cả 8 item đã dự đoán `(?)`, phải tự xác nhận rồi xoá dấu `(?)`
- [ ] Số bug tạo mới ở đây (không tính `= SV-xxx`) khớp với số dòng `CL-` mới trong `04-findings-log.md`
- [ ] Đã đếm lại `S1/S2/S3` cột Passed/Failed/N-A bằng lệnh, không tính tay, điền vào Bảng tổng hợp
