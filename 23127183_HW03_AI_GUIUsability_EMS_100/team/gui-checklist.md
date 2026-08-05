# Task 1A — GUI Checklist dùng chung (sản phẩm nhóm)

**SUT:** EMS — https://prod-dev.ems-fitus.cloud
**Phạm vi phủ:** IA-01 chuẩn UI chung · IA-02 forms · IA-03 navigation · IA-04 feedback/state
**Tổng số mục:** **52** *(yêu cầu tối thiểu: > 40)*
**Phiên bản:** v1.0 · **Ngày chốt:** _(TODO)_

**Đóng góp:** _(TODO — điền trước khi nộp. Nếu tự dựng một mình: "Bản v1 do Phạm Vũ Ngọc Duy (23127183) dựng ngày __, dựa trên khảo sát trực tiếp EMS ngày 05/08/2026. Đã gửi cả nhóm rà soát ngày __; [kết quả]")_

> Checklist này **giống hệt nhau giữa các thành viên trong nhóm** — đề §18 nói rõ đây là trường hợp được phép trùng. Mọi thứ khác (chọn màn hình, thực thi, usability, cross-platform, findings) phải riêng của từng người.
> Nguồn tham khảo: [`references.md`](references.md) · Prompt AI và lý do AI bỏ sót: [`ai-prompts.md`](ai-prompts.md)
> **File này KHÔNG chứa cột kết quả.** Kết quả Passed/Failed/N-A của từng người nằm ở `01-checklist-execution.md` — để file chung luôn giống nhau giữa 5 thành viên.

---

## Phân bổ

| IA | Prefix | Nội dung | Số mục | Do AI sinh | Người bổ sung |
|---|:--:|---|:--:|:--:|:--:|
| IA-01 | `G-` | Chuẩn UI chung — bố cục, typography, màu, ảnh, empty/loading, i18n EN/VI, accessibility | **16** | 11 | 5 |
| IA-02 | `F-` | Forms — nhãn, trường bắt buộc, validation, vị trí lỗi, upload, rich-text, bàn phím | **14** | 13 | 1 |
| IA-03 | `N-` | Navigation — menu, breadcrumb, back, deep link, URL state, tab, sidebar, kéo-thả | **9** | 7 | 2 |
| IA-04 | `S-` | Feedback / State — toast, badge, dialog xác nhận, progress, màu trạng thái, thời gian | **13** | 7 | 6 |
| | | **Tổng** | **52** | **38** | **14** |

## Cách dùng khi chạy (Task 1B)

| Giá trị | Nghĩa | Bắt buộc kèm |
|---|---|---|
| **Passed** | Đã kiểm, đạt | — |
| **Failed** | Đã kiểm, không đạt | **Notes (lý do) + ảnh chụp** |
| **N/A** | Không áp dụng cho màn hình này | Ghi ngắn lý do |
| *(trống)* | Chưa kiểm — **không được để trống khi nộp** | — |

> Checklist phủ cả 4 kịch bản A/B/C/D nên **N/A là bình thường và được dự kiến**. Ví dụ ở phía user (Pool B) không có upload ảnh, rich-text, kéo-thả reorder ⇒ `F-08`, `F-09`, `F-10`, `N-08` sẽ N/A. Ước tính mỗi màn hình thực chạy khoảng **35–42 mục**.
> Tỉ lệ pass tính trên `Passed / (Passed + Failed)`, **không tính N/A vào mẫu số**.

**Ký hiệu cột Nguồn**

| Mã | Nghĩa |
|---|---|
| `N1`–`N10` | 10 heuristic của Nielsen — N1 visibility of system status · N2 match real world · N3 user control & freedom · N4 consistency & standards · N5 error prevention · N6 recognition not recall · N7 flexibility & efficiency · N8 aesthetic & minimalist · N9 recognise/diagnose/recover from errors · N10 help & documentation |
| `P1`–`P6` | 6 nguyên lý Norman — P1 visibility · P2 feedback · P3 constraints · P4 mapping · P5 consistency · P6 affordance |
| `S1`–`S8` | 8 quy tắc vàng Shneiderman — S1 consistency · S2 universal usability · S3 informative feedback · S4 dialogs yield closure · S5 prevent errors · S6 easy reversal · S7 internal locus of control · S8 reduce memory load |
| `W` | WCAG 2.2, kèm mã success criterion |
| `SL` | Slide môn học — *GUI + Usability + Compatibility Testing* |

**Ký hiệu cột Nguồn gốc:** `AI` = do AI sinh ở lượt đầu · `RV` = người bổ sung sau khi khảo sát EMS thật *(lý do AI bỏ sót ghi ở [`ai-prompts.md`](ai-prompts.md) §3)*

---

## 1. IA-01 — Chuẩn UI chung (`G-`, 16 mục)

| ID | Mục kiểm tra | Nguồn | Nguồn gốc |
|---|---|---|:--:|
| G-01 | Các khối cùng cấp căn lề thẳng hàng nhau; khoảng cách giữa các khối theo cùng một thang, không lúc rộng lúc hẹp tuỳ chỗ | S1, SL | AI |
| G-02 | Toàn hệ thống dùng tối đa 2 họ font; cỡ chữ theo thang phân cấp rõ ràng (tiêu đề / nội dung / chú thích) và giữ nguyên giữa các trang | N4, SL | AI |
| G-03 | Màu được dùng đúng ngữ nghĩa: một màu chính cho hành động chính, **đỏ chỉ dành cho lỗi và hành động phá huỷ**, không dùng đỏ cho thông tin trung tính | N4, P5 | AI |
| G-04 | Nội dung không tạo thanh cuộn ngang ngoài ý muốn ở bề rộng cửa sổ ≥ 1280px | SL | AI |
| G-05 | Ảnh giữ đúng tỉ lệ khung đã quy định (thumbnail 4:3, banner 24:9), không bị kéo méo và không bị cắt mất phần nội dung quan trọng | N8, SL | AI |
| G-06 | Ảnh không tải được phải hiện khối giữ chỗ **có ý nghĩa** (tên viết tắt, icon kèm nhãn), không để ô xám trơn không giải thích | N1, N8 | **RV** |
| G-07 | Trạng thái rỗng nêu **lý do vì sao rỗng** và **gợi ý hành động tiếp theo** (ví dụ nút xoá bộ lọc), không dừng ở một câu thông báo suông | N1, N3 | **RV** |
| G-08 | Trạng thái đang tải có skeleton hoặc spinner; khi dữ liệu về, bố cục **không nhảy** khiến người dùng bấm nhầm | N1, P2 | AI |
| G-09 | Giá trị rỗng hiển thị bằng **cùng một ký hiệu thống nhất** trên mọi màn hình (ví dụ dấu `-`), không chỗ để trắng chỗ dùng ký hiệu khác | N4, S1 | **RV** |
| G-10 | Nhãn hiển thị cho người dùng dùng **ngôn ngữ của người dùng**, không phơi mã định danh nội bộ hay chuỗi sinh tự động ra làm tiêu đề chính | N2 | **RV** |
| G-11 | Chuyển EN/VI dịch **toàn bộ** text giao diện — kể cả toast, tooltip, placeholder, nhãn nút và thông báo lỗi | N2, S2 | AI |
| G-12 | **Dữ liệu hiển thị** (tên vai trò, tên trạng thái, tên danh mục) cũng theo ngôn ngữ đang chọn hoặc có cơ chế xử lý rõ ràng — không lẫn tiếng Việt trong giao diện tiếng Anh | N4 | **RV** |
| G-13 | Ngôn ngữ đã chọn được **lưu lại** và giữ nguyên sau khi tải lại trang hoặc mở trang khác | N1, S7 | AI |
| G-14 | Tỉ lệ tương phản chữ trên nền đạt ≥ 4.5:1 với chữ thường và ≥ 3:1 với chữ lớn | W SC 1.4.3, S2 | AI |
| G-15 | Nội dung vẫn đọc được và bố cục không vỡ khi zoom trình duyệt lên **200%** | W SC 1.4.4 | AI |
| G-16 | Text tiếng Việt (dài hơn tiếng Anh) không làm vỡ nút, cắt chữ bằng dấu `…`, hay xuống dòng gãy giữa từ | S2, N4 | AI |

## 2. IA-02 — Forms (`F-`, 14 mục)

| ID | Mục kiểm tra | Nguồn | Nguồn gốc |
|---|---|---|:--:|
| F-01 | Mọi trường nhập có **nhãn hiển thị thường trực**, không chỉ dựa vào placeholder biến mất khi gõ | N6, SL | AI |
| F-02 | Trường bắt buộc được đánh dấu trực quan nhất quán (ví dụ dấu `*`) và ký hiệu đó được chú giải ít nhất một lần trong form | P3, N6 | AI |
| F-03 | Thông báo lỗi hiện **ngay cạnh trường bị lỗi** và nằm trong tầm nhìn hiện tại, không chỉ ở một toast tự tắt | N9 | AI |
| F-04 | Thông báo lỗi nói rõ **cách khắc phục**, không dừng ở "giá trị không hợp lệ" | N9 | AI |
| F-05 | Sau khi validate thất bại, **dữ liệu người dùng đã nhập được giữ nguyên**, không bị xoá trắng bắt nhập lại | N3, S6 | AI |
| F-06 | Ràng buộc được chặn **ngay tại chỗ nhập** thay vì chỉ báo lỗi sau khi submit — ví dụ ô ngày kết thúc không cho chọn ngày trước ngày bắt đầu | N5, P3 | AI |
| F-07 | Nút submit bị vô hiệu hoá hoặc chặn gửi khi form chưa hợp lệ; **bấm đúp không tạo bản ghi trùng** | N5 | AI |
| F-08 | Upload ảnh kiểm tra định dạng và dung lượng, và **báo giới hạn cho người dùng biết trước** khi họ chọn file | P3, N5 | AI |
| F-09 | Upload ảnh có **preview đúng tỉ lệ yêu cầu** trước khi lưu, để người dùng thấy phần nào sẽ bị cắt | N1 | AI |
| F-10 | Trình soạn rich-text có đủ nút định dạng cơ bản, và nội dung dán từ nơi khác vào không mang theo định dạng làm vỡ bố cục | N7 | AI |
| F-11 | Với hành động không hoàn tác được, form có **bước xác nhận hoặc bảng tóm tắt** trước khi gửi | N5, S4 | AI |
| F-12 | Khi một lựa chọn bị khoá (hết chỗ, hết hạn), hệ thống **nêu rõ lý do khoá và lựa chọn thay thế nếu có** — không chỉ làm mờ nó đi một cách im lặng | N1, N9 | **RV** |
| F-13 | Ô nhập có **trạng thái focus nhìn thấy được**; phím `Tab` đi qua các trường theo thứ tự khớp với thứ tự nhìn thấy trên màn hình | W SC 2.4.7, N7 | AI |
| F-14 | Form hoặc modal đóng được bằng phím `Esc` và bằng nút thoát rõ ràng; nếu còn dữ liệu chưa lưu thì có cảnh báo trước khi đóng | N3, S6 | AI |

## 3. IA-03 — Navigation (`N-`, 9 mục)

| ID | Mục kiểm tra | Nguồn | Nguồn gốc |
|---|---|---|:--:|
| N-01 | Menu điều hướng chính hiển thị nhất quán ở mọi trang, và **mục đang xem được làm nổi bật** | N1, N6 | AI |
| N-02 | Trang chi tiết có **đường quay lại danh sách** (breadcrumb hoặc nút back trong giao diện), không bắt người dùng phải dựa vào nút Back của trình duyệt | N3, S7 | **RV** |
| N-03 | Nút Back của trình duyệt đưa về đúng trang trước đó và **giữ nguyên bộ lọc, trang phân trang, vị trí cuộn** | N3 | AI |
| N-04 | Với trang yêu cầu đăng nhập: sau khi đăng nhập xong, người dùng được đưa lại **đúng trang họ vừa yêu cầu**, không bị đẩy về trang chủ | N3, S7 | **RV** |
| N-05 | URL phản ánh trạng thái đang xem (tab, bộ lọc, số trang) để **chia sẻ link và tải lại trang** đều ra đúng nội dung đó | N4, S7 | AI |
| N-06 | Chuyển tab hoặc đổi bộ lọc tải đúng dữ liệu tương ứng, và trạng thái được giữ khi quay lại từ trang chi tiết | N4 | AI |
| N-07 | Sidebar thu gọn / mở rộng được, và ở trạng thái mở không che khuất nội dung chính | N7, S7 | AI |
| N-08 | Kéo-thả sắp xếp có **tay cầm rõ ràng**, dòng đang kéo có phản hồi thị giác, các thao tác khác tạm khoá để tránh xung đột, và thứ tự mới được lưu đúng | P2, P6 | AI |
| N-09 | Không có liên kết hỏng; mọi liên kết và nút điều hướng dẫn tới đích tồn tại, không rơi vào trang 404 | N9 | AI |

## 4. IA-04 — Feedback / State (`S-`, 13 mục)

| ID | Mục kiểm tra | Nguồn | Nguồn gốc |
|---|---|---|:--:|
| S-01 | Mọi hành động làm thay đổi dữ liệu đều có phản hồi tức thì (toast hoặc thông báo tại chỗ), xuất hiện ở **vị trí nhất quán** trên toàn hệ thống | N1, S3 | AI |
| S-02 | Toast phân biệt bằng **cả màu lẫn icon/chữ**, không chỉ bằng màu; và ở lại đủ lâu để đọc hết trước khi tự tắt | N1, W SC 1.4.1 | AI |
| S-03 | Hành động không hoàn tác được (huỷ đăng ký, xoá, khoá tài khoản) có **hộp thoại xác nhận nêu rõ hậu quả**, không chỉ hỏi "bạn có chắc không" | N5, S6 | AI |
| S-04 | Trạng thái của một bản ghi được thể hiện bằng badge có **cả màu lẫn nhãn chữ**, và cùng một trạng thái dùng cùng một màu trên mọi màn hình | N4, W SC 1.4.1 | **RV** |
| S-05 | Khối hiển thị sức chứa / số lượng có đổi màu theo trạng thái thì **phải kèm nhãn chữ giải thích**, không để người dùng tự đoán ý nghĩa qua màu | N1, W SC 1.4.1 | **RV** |
| S-06 | Một khối chức năng giữ **nguyên số ô / số trường** giữa các bản ghi cùng loại; trường không áp dụng thì hiện trạng thái rỗng thay vì biến mất khiến bố cục đổi | N4, S1 | **RV** |
| S-07 | Khu vực nội dung nổi bật ở trang chủ chỉ hiển thị bản ghi **còn hiệu lực**; bản ghi đã kết thúc không chiếm vị trí ưu tiên nhất | N1, N2 | **RV** |
| S-08 | Tác vụ chạy lâu có thanh tiến trình hoặc spinner, kèm chỉ báo **đang ở bước nào hoặc còn bao lâu** | N1, S3 | AI |
| S-09 | Ngày giờ hiển thị theo **một định dạng thống nhất** toàn hệ thống, và nêu rõ múi giờ ở những chỗ liên quan tới hạn chót | N2, N4 | **RV** |
| S-10 | Bộ đếm ngược hoặc nhãn trạng thái thời gian ("còn N ngày", "đang diễn ra", "đã kết thúc") **khớp với dữ liệu ngày giờ** hiển thị ngay cạnh nó | N1 | AI |
| S-11 | Khi mất kết nối mạng, hệ thống báo rõ và **cho biết thao tác vừa rồi có được lưu hay không** | N1, N9 | AI |
| S-12 | Mã QR / barcode hiển thị **đủ lớn và sắc nét** để quét được bằng camera điện thoại thông thường, không bị co méo trên màn hình nhỏ | N1, SL | AI |
| S-13 | Nhãn nút, tiêu đề và tên mục dùng **cùng một quy ước viết hoa** trên toàn hệ thống | N4, S1 | **RV** |

---

## 5. Vùng đã cân nhắc nhưng KHÔNG đưa vào — có lý do

> Đây cũng là một phần của lượt review. Đề nêu RTL và dark mode như ví dụ những vùng AI hay bỏ sót; nhóm đã kiểm và **chủ động loại** thay vì thêm mục sẽ N/A với mọi người.

| Vùng | Quyết định | Lý do |
|---|---|---|
| Bố cục RTL | ❌ Không đưa vào | EMS chỉ hỗ trợ EN và VI — cả hai đều viết trái-sang-phải. Thêm mục RTL sẽ N/A trên **mọi** màn hình của **cả 5 thành viên**, không tạo giá trị kiểm thử nào |
| Dark mode | ❌ Không đưa vào | Khảo sát ngày 05/08/2026 không thấy công tắc chế độ tối ở bất kỳ đâu trong header hay trang cá nhân. ⚠️ **Cần xác nhận lại** — nếu tìm thấy thì bổ sung 1 mục về tương phản ở chế độ tối |
| Trình duyệt tự động điền (autofill) | ❌ Không đưa vào | Đây là hành vi của trình duyệt, không phải giao diện của SUT — không kết luận Passed/Failed cho ứng dụng được |
| Cập nhật real-time không cần reload | ⚠️ Gộp vào `S-08` | Phía user không có luồng nào cập nhật real-time quan sát được; phía admin có ở tab Check-in nhưng chỉ 1 người trong nhóm chạm tới |

## 6. Kiểm đếm trước khi chốt

```bash
cd 23127183_HW03_AI_GUIUsability_EMS_100
for p in G F N S; do echo -n "$p: "; grep -c "^| $p-" team/gui-checklist.md; done
echo -n "RV: "; grep -c '| \*\*RV\*\* |' team/gui-checklist.md
```

Kết quả mong đợi: `G: 16 · F: 14 · N: 9 · S: 13` → tổng **52** · `RV: 14`

- [ ] Tổng > 40 ✅ (52)
- [ ] Mỗi IA đều có mục, không IA nào rỗng ✅
- [ ] Mọi mục có mã nguồn heuristic ✅
- [ ] Mọi mục có `AI` hoặc `RV` ✅
- [ ] Số mục `RV` (14) khớp số dòng giải trình ở [`ai-prompts.md`](ai-prompts.md) §3
- [ ] **Bạn đã tự đọc lại 52 mục** và sửa/thêm/bớt theo ý mình trước khi chốt v1.0
