---
name: hw03-gui-checklist
description: >-
  Thiết kế và thực thi GUI checklist cho một màn hình web theo 4 khía cạnh giao
  diện IA-01..IA-04, đặt nền trên Nielsen/Norman/Shneiderman. Dùng khi cần soạn
  checklist GUI, hoặc chạy checklist có sẵn trên một màn hình EMS và đánh
  Passed/Failed từng item kèm lý do.
---

# GUI Checklist — thiết kế & thực thi (EMS, UI-first)

## Nguyên tắc

- **Dẫn AI theo từng bước của kỹ thuật**, không hỏi một câu chung chung. Mỗi bước một prompt, review xong mới sang bước sau.
- **Item phải kiểm chứng được:** nhìn vào màn hình là kết luận được Passed hay Failed. Item kiểu "giao diện đẹp và dễ dùng" là item hỏng.
- **Mỗi item gắn với một heuristic nguồn** (Nielsen N1–N10 / Norman P1–P6 / Shneiderman S1–S8 / slide môn học) — không có nguồn thì không đưa vào.
- **AI không nhìn thấy màn hình.** Nó chỉ sinh được item từ mô tả bạn cung cấp. Chất lượng checklist tỉ lệ thuận với độ chi tiết bạn mô tả widget thật của SUT.
- **Kết quả Passed/Failed do người chạy điền**, AI không được đoán hộ. AI chỉ dựng khung và giúp phân tích sau khi có dữ liệu thật.

---

## PHẦN A — Thiết kế checklist (Task 1A, sản phẩm nhóm)

### Bước A1 — Nạp khung lý thuyết + bối cảnh SUT

```
Bạn là chuyên gia kiểm thử giao diện. Tôi sẽ xây một GUI checklist cho SUT là EMS
(Event Management System, web app quản lý sự kiện của một khoa CNTT).

Khung lý thuyết bắt buộc dùng:
- Nielsen 10 usability heuristics (N1..N10)
- Norman 6 design principles (P1..P6)
- Shneiderman 8 golden rules (S1..S8)

Checklist được tổ chức theo 4 khía cạnh giao diện:
- IA-01 General UI standards: layout, alignment, typography, colour, consistency,
  i18n EN/VI, empty/loading states
- IA-02 Forms: labels, validation, error placement, required fields, uploads, rich-text editor
- IA-03 Navigation: menus, breadcrumbs, tabs, sidebar, drag-and-drop reorder,
  back/return actions, deep links
- IA-04 Feedback/state: toasts, badges, confirmation dialogs, progress bars,
  status colours, real-time updates

Các widget THẬT tôi quan sát được trên EMS: [liệt kê cụ thể — upload thumbnail 4:3
và banner 24:9, RichTextEditor, drag-drop reorder có hiệu ứng mờ dòng đang kéo,
icon picker ~80 icon, toggle bật/tắt làm form hiện thêm trường, progress bar duyệt
đăng ký, 6 màu trạng thái participant, công tắc EN/VI ở header, carousel tự xoay,
DateRangeFilter phải bấm Apply mới fetch, export Excel...]

Chưa sinh checklist. Hãy xác nhận bạn đã hiểu khung và hỏi lại tôi những gì
còn thiếu để checklist bám sát SUT này.
```
→ **Người review:** AI hỏi lại gì? Câu hỏi của nó chính là chỗ bạn mô tả SUT còn thiếu — bổ sung rồi mới sang A2.

### Bước A2 — Sinh item theo TỪNG khía cạnh (4 prompt riêng)

```
Sinh các item checklist cho riêng IA-0X.
Format bảng: | ID | Item | Cách kiểm | Nguồn heuristic |
- ID dạng IA0X-01, IA0X-02...
- Mỗi item viết ở dạng khẳng định, trả lời được Passed/Failed, KHÔNG mơ hồ
- Cột "Cách kiểm": thao tác cụ thể để xác định kết quả (bấm gì, nhìn vào đâu, đo bằng gì)
- Cột "Nguồn": ghi mã heuristic cụ thể (N4, P3, S6...), không ghi chung chung
- Không sinh item trùng nghĩa với item đã có
Sinh tối thiểu [12/12/8/10] item cho IA-0X.
```
→ **Người review sau mỗi IA:** loại item trùng nghĩa; sửa item không kiểm chứng được; kiểm tra mã heuristic có gán bừa không.

### Bước A3 — Ép AI tự soi lỗ hổng

```
Đây là checklist hiện tại: [dán toàn bộ].
1) Chỉ ra những vùng giao diện mà checklist này CHƯA phủ.
2) Với mỗi vùng thiếu, nói rõ vì sao một checklist sinh tự động thường bỏ qua nó.
3) Không thêm item mới ở bước này — chỉ liệt kê lỗ hổng.
```
→ **Người review:** đối chiếu danh sách lỗ hổng của AI với danh sách vùng-AI-hay-sót trong `team/gui-checklist.md`. Những gì AI **vẫn** không nêu ra chính là item bạn phải tự thêm.

### Bước A4 — Người bổ sung item + ghi lý do AI sót

Với mỗi item tự thêm, ghi vào `team/references-and-prompts.md` mục 3, phân loại lý do:
- **(a) prompt của mình thiếu ngữ cảnh** → nêu rõ thiếu thông tin gì
- **(b) giới hạn của model** → nêu rõ giới hạn nào (không thấy màn hình, không biết dữ liệu, không chạy được app)
- **(c) đặc thù riêng của EMS** → nêu rõ chi tiết nào chỉ lộ ra khi thao tác thật

### Bước A5 — Chốt

- [ ] > 40 item · [ ] phủ đủ 4 IA · [ ] mỗi item có nguồn heuristic · [ ] đánh dấu AI/Người
- **Commit:** `[task1a] Add shared GUI checklist (>40 items, IA-01..IA-04) + sources + AI prompts`

---

## PHẦN B — Thực thi trên màn hình (Task 1B, cá nhân)

### Bước B1 — Chuẩn bị bảng chạy

Copy cột `ID` + `Item` từ checklist chung sang `01-checklist-execution.md`, thêm cột cho từng màn hình. **Không sửa nội dung item ở bước này** — checklist phải giống hệt giữa các thành viên nhóm.

### Bước B2 — Chạy từng item trên màn hình thật

Nguyên tắc chạy:
- Đi tuần tự theo ID, không nhảy cóc — nhảy cóc là sót.
- Item không áp dụng cho màn hình đó → đánh `➖ N/A` và **ghi lý do**, không để trống.
- Thấy Failed → **chụp ảnh ngay** (SUT là môi trường dev, dữ liệu có thể bị reset).
- Ảnh đặt tên đúng bằng Bug-ID sẽ dùng: `CL-B3-01.png` (nguồn-màn hình-số).

### Bước B3 — Nhờ AI phân tích cụm lỗi (sau khi đã có dữ liệu thật)

```
Đây là kết quả chạy checklist thật trên 3 màn hình EMS: [dán bảng đã điền].
1) Nhóm các item Failed theo nguyên nhân gốc chung (không phải theo IA).
2) Chỉ ra đâu là bug đơn lẻ, đâu là vấn đề thiết kế mang tính hệ thống, kèm lý do.
3) Đề xuất mức severity 0-4 cho từng nhóm và giải thích căn cứ.
Chỉ dùng dữ liệu tôi dán, không suy diễn thêm kết quả mà tôi không cung cấp.
```
→ **Người review:** AI hay đẩy severity lên cao. Tự chỉnh lại theo tác động thật lên người dùng.

### Bước B4 — Sinh bug entry

Mỗi Failed → 1 block trong `04-findings-log.md`: màn hình · steps to reproduce · expected vs actual · severity · suggested fix · ảnh. Submit lên Google Form rồi điền `Form-submission timestamp`.

- **Commit (1 commit / 1 màn hình):** `[task1b][screen-XX] Execute checklist on <tên màn>, N passed / M failed`

---

## Checklist review trước khi đóng bước

- [ ] Không còn ô kết quả trống trên bất kỳ màn hình nào
- [ ] Mọi Failed đều có Notes ghi **lý do**, không chỉ mô tả hiện tượng
- [ ] Mọi Failed đều có ảnh và ảnh mở lên đúng nội dung
- [ ] Số bug `CL-` khớp giữa `01-checklist-execution.md` và `04-findings-log.md`
- [ ] Đã ghi phiên AI vào `appendix/a3-ai-audit-report.md`
