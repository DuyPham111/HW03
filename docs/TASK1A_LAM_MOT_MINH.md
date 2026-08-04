# TASK 1A — Tự làm checklist nhóm một mình

**Tình huống:** nhóm không làm phần checklist chung. Bạn tự làm để không bị kẹt bài của mình.
**Điểm liên quan:** 15đ trực tiếp (Task 1A) **+ chặn 15đ** của Task 1B — không có checklist thì không chạy được gì.
**Thời gian thực tế:** ~3 giờ nếu làm theo đúng 6 bước dưới (trong đó 50 phút là khảo sát EMS — không bỏ qua được).
**File sẽ điền:** `team/gui-checklist.md` · `team/references.md` · `team/ai-prompts.md`

---

## 1. Làm một mình có phạm quy không? — KHÔNG

Đây là điều bạn cần yên tâm trước khi bỏ 2 tiếng vào:

| Lo ngại | Sự thật theo đề |
|---|---|
| "Checklist là sản phẩm nhóm, tôi làm một mình có bị coi là gian lận không?" | Không. Đề §15 chỉ nói checklist **nộp một lần cho cả nhóm**, không quy định phải bao nhiêu người viết |
| "Nếu cả nhóm nộp checklist giống hệt nhau thì có bị 0 điểm copy không?" | Không. Đề §18 nói thẳng: *"The group's shared checklist is **expected to be identical** within the group"* |
| "Prompt của tôi mà bạn cùng nhóm dùng lại thì sao?" | An toàn — đề §15 xếp **AI prompts dựng checklist** vào nhóm *group-level artefacts*, nộp một lần cho cả nhóm |
| "Vậy cái gì mới KHÔNG được giống nhau?" | Chọn màn hình · thực thi checklist · usability · cross-platform · findings. Toàn bộ những thứ này bạn vẫn làm riêng |

**Kết luận:** cứ làm một mình, nộp làm sản phẩm nhóm, và **ghi trung thực ai đóng góp gì** trong phần đầu `team/gui-checklist.md`. Trung thực về đóng góp là điểm cộng cho tính minh bạch, không phải điểm trừ.

**Câu nên nhắn nhóm** (gửi rồi làm luôn, đừng chờ):

> "Mình đang bị kẹt Task 1B vì chưa có checklist chung. Mình sẽ dựng bản v1 trong hôm nay và gửi cả nhóm dùng. Ai rà lại giúp phần IA nào thì báo mình để mình ghi tên vào phần đóng góp, không thì mình ghi là mình tự dựng. Deadline rà: [ngày]."

Gửi tin này có 2 tác dụng: (1) nếu có người nhảy vào thì tốt, (2) nếu không thì bạn có bằng chứng đã chủ động, và ghi vào báo cáo được.

---

## 2. Đổi format checklist cho gọn — làm trước khi bắt đầu

Format cũ 5 cột (có cột "Cách kiểm") làm mỗi dòng dài gấp đôi, đọc rất mệt khi có 50+ item. **Đổi sang 4 cột**, viết câu item đủ cụ thể để tự nó nói luôn cách kiểm:

| ID | Mục kiểm tra | Nguồn | Nguồn gốc |
|---|---|---|---|
| G-01 | Chuyển EN/VI dịch **toàn bộ** text hiển thị — không còn chuỗi lẫn ngôn ngữ trên cùng màn hình | N2, S2 | RV |

**Đổi luôn hệ ID cho ngắn** (ID này sẽ lặp lại hàng trăm lần ở Task 1B):

| Prefix | Khía cạnh | Mục tiêu số item |
|---|---|---:|
| `G-` | IA-01 Chuẩn UI chung | ≥ 12 |
| `F-` | IA-02 Forms | ≥ 12 |
| `N-` | IA-03 Navigation | ≥ 8 |
| `S-` | IA-04 Feedback / State | ≥ 10 |
| | **Tổng** | **> 40** |

**Ký hiệu cột Nguồn:** `N1`–`N10` Nielsen · `P1`–`P6` Norman · `S1`–`S8` Shneiderman · `SL` slide môn học · `W` WCAG 2.2 · `E` tài liệu E2E EMS
**Ký hiệu cột Nguồn gốc:** `AI` = AI sinh ở lượt đầu · `RV` = bạn bổ sung khi review (phải có lý do ở `team/ai-prompts.md`)

---

## 3. Sáu bước làm — có hộp thời gian

### Bước 1 · 50 phút — Khảo sát EMS để có nguyên liệu thật

**Đây là bước quyết định chất lượng cả Task 1A.** AI không nhìn thấy màn hình; checklist chỉ tốt bằng đúng mức chi tiết bạn mô tả cho nó. Bỏ qua bước này thì 4 prompt ở Bước 3 sẽ cho ra toàn item chung chung, và bạn sẽ mất luôn phần "human review" — vốn là chỗ chấm nặng nhất.

> **Làm theo phiếu đã dựng sẵn: [`KHAO_SAT_EMS.md`](KHAO_SAT_EMS.md).**
> Phiếu đó là dạng **điền vào chỗ trống** — mở song song với EMS, tick từng dòng, điền từng ô. Không phải nghĩ xem "cần ghi gì".

Phiếu gồm 7 phần, tổng ~50 phút:

| Phần | Nội dung | Thời gian |
|---|---|---:|
| 0 | Chuẩn bị: tài khoản user riêng, thư mục ảnh, quy ước đặt tên | 5' |
| 1 | **Dựng 4 sự kiện dữ liệu thử** bằng quyền admin (còn chỗ / hết chỗ + waitlist / đã đóng đăng ký / đã ENDED) | 20' |
| 2 | Khảo sát phía **user** — B1…B5, riêng B2/B3/B4 soi kỹ vì là màn chấm điểm | 25' |
| 3 | Khảo sát phía **admin** — chỉ lấy danh mục widget để checklist dùng được cho cả nhóm | 15' |
| 4 | **8 phép thử xuyên suốt** — i18n EN/VI, ngôn ngữ có được nhớ, zoom 200%, bề rộng 375px, mạng chậm, mã trạng thái nội bộ… | 10' |
| 5 | **Danh mục widget** — khối văn bản dán thẳng vào prompt ở Bước 2 | — |
| 6 | Quan sát nghi vấn `SV-xxx` — chụp ảnh ngay, kiểm chứng lại ở Task 1B | — |

**Ba điều dễ làm sai ở bước này:**

1. **Có, phải chụp ảnh** — nhưng phân biệt rõ ba loại: ảnh tổng quan mỗi màn (để viết item mà không phải mở lại EMS) · ảnh widget lạ (nguyên liệu mô tả cho AI) · ảnh chỗ nghi ngờ có lỗi (bằng chứng, chụp ngay vì dữ liệu dev có thể reset). Ảnh khảo sát **không** dùng làm bằng chứng Task 1B — 1B đòi ảnh chụp trong lúc chạy checklist.
2. **Phải khảo sát cả phía admin**, dù bạn chấm điểm phía user. Checklist là sản phẩm chung của cả nhóm, phải dùng được cho cả 4 kịch bản; chỉ khảo sát phía user thì checklist thiếu hẳn nhóm item upload / rich-text / kéo-thả và bạn không giải trình được với nhóm.
3. **Phần 5 là sản phẩm thật của cả buổi.** Nếu khối đó còn chỗ `___` chưa điền thì quay lại EMS xem tiếp — đừng sang Bước 2 vội.

### Bước 2 · 15 phút — Nạp bối cảnh cho AI (chưa sinh item)

```
Bạn là chuyên gia kiểm thử giao diện. Tôi sẽ xây một GUI checklist cho SUT là EMS
(Event Management System — web app quản lý sự kiện của Khoa CNTT, có phía user và phía admin,
hỗ trợ song ngữ EN/VI).

Khung lý thuyết bắt buộc dùng, mỗi item phải gắn với ít nhất một mã:
- Nielsen 10 usability heuristics: N1 Visibility of system status, N2 Match system & real world,
  N3 User control & freedom, N4 Consistency & standards, N5 Error prevention,
  N6 Recognition rather than recall, N7 Flexibility & efficiency, N8 Aesthetic & minimalist design,
  N9 Help recognize/diagnose/recover from errors, N10 Help & documentation
- Norman 6 principles: P1 Visibility, P2 Feedback, P3 Constraints, P4 Mapping, P5 Consistency, P6 Affordance
- Shneiderman 8 golden rules: S1 Consistency, S2 Universal usability, S3 Informative feedback,
  S4 Dialogs yield closure, S5 Prevent errors, S6 Easy reversal, S7 Internal locus of control,
  S8 Reduce short-term memory load
- WCAG 2.2 (mã W) cho phần accessibility

Checklist chia theo 4 khía cạnh:
- IA-01 (prefix G-) chuẩn UI chung: layout, alignment, typography, màu, nhất quán, i18n EN/VI, empty/loading state
- IA-02 (prefix F-) forms: nhãn, validation, vị trí thông báo lỗi, trường bắt buộc, upload, rich-text
- IA-03 (prefix N-) navigation: menu, breadcrumb, tab, sidebar, kéo-thả reorder, back/return, deep link
- IA-04 (prefix S-) feedback/state: toast, badge, dialog xác nhận, progress bar, màu trạng thái, real-time

Đây là các widget THẬT tôi đã quan sát trên EMS:
[DÁN KHỐI "DANH MỤC WIDGET" Ở PHẦN 5 CỦA KHAO_SAT_EMS.md]

CHƯA sinh checklist. Hãy: (1) xác nhận bạn đã hiểu khung; (2) hỏi lại tôi những thông tin
về SUT còn thiếu mà nếu có sẽ giúp checklist bám sát hệ thống này hơn.
```

→ **Việc của bạn:** đọc câu hỏi AI đặt ra. Chính những câu đó chỉ ra chỗ mô tả của bạn còn mỏng. Trả lời rồi mới sang bước 3.

### Bước 3 · 40 phút — Sinh item theo TỪNG khía cạnh (4 prompt riêng)

Chạy 4 lần, mỗi lần thay `G-`/`F-`/`N-`/`S-` và số lượng:

```
Sinh item checklist cho riêng khía cạnh IA-01 (prefix G-).

Format bảng đúng 4 cột: | ID | Mục kiểm tra | Nguồn | Nguồn gốc |
- ID: G-01, G-02...
- "Mục kiểm tra": viết ở dạng KHẲNG ĐỊNH, đủ cụ thể để nhìn màn hình là kết luận
  Passed hay Failed ngay, KHÔNG cần thêm cột hướng dẫn. Nêu rõ ngưỡng đo được nếu có
  (vd "tương phản ≥ 4.5:1", "không scroll ngang ở ≥ 1280px").
- "Nguồn": mã heuristic cụ thể (N4, P2, S6, W SC 1.4.3, SL). Không ghi chung chung.
- "Nguồn gốc": ghi AI cho toàn bộ item bạn sinh.
- KHÔNG sinh item trùng nghĩa nhau.
- Item phải áp dụng được cho ÍT NHẤT một trong các widget tôi đã liệt kê.

Sinh 14 item cho IA-01.
```

→ **Việc của bạn sau mỗi lượt** (đừng để dồn 4 lượt rồi mới review):
- Gạch item trùng nghĩa
- Sửa item mơ hồ thành item đo được
- Kiểm tra mã heuristic có bị gán bừa không (AI hay gán N4 cho mọi thứ)
- Xoá item nói về widget mà EMS **không có**

### Bước 4 · 20 phút — Ép AI tự soi lỗ hổng

```
Đây là checklist hiện tại sau khi tôi đã review và loại bớt:
[DÁN TOÀN BỘ 4 BẢNG]

1) Liệt kê những vùng giao diện mà checklist này CHƯA phủ.
2) Với mỗi vùng thiếu, giải thích vì sao một checklist sinh tự động thường bỏ qua nó.
3) KHÔNG thêm item mới ở bước này — chỉ liệt kê lỗ hổng.
```

→ **Việc của bạn:** đối chiếu danh sách AI đưa ra với bảng dưới. **Vùng nào AI VẪN không nêu ra chính là item bạn phải tự thêm ở bước 5** — và đó là bằng chứng mạnh nhất cho phần "vì sao AI bỏ sót".

### Bước 5 · 30 phút — Tự bổ sung + ghi lý do AI sót

Rà 10 vùng đề nêu đích danh + đặc thù EMS. **Tick vào ô nào đã có item, ô nào chưa thì viết thêm:**

| # | Vùng | Đã có item? | ID |
|---|---|:--:|---|
| 1 | Accessibility: tương phản ≥ 4.5:1, alt text, focus nhìn thấy được | ⬜ | |
| 2 | Điều hướng bàn phím: Tab đúng thứ tự, Enter/Esc, không bẫy focus trong modal | ⬜ | |
| 3 | Dark mode | ⬜ | |
| 4 | Bố cục RTL | ⬜ | |
| 5 | **i18n EN/VI** — kể cả toast, tooltip, placeholder, nội dung file Excel export | ⬜ | |
| 6 | **Text tiếng Việt dài hơn EN** làm vỡ nút / cắt chữ | ⬜ | |
| 7 | **Ngôn ngữ đã chọn có được lưu lại** sau khi tải lại trang không | ⬜ | |
| 8 | Empty state / loading state / skeleton không gây nhảy layout | ⬜ | |
| 9 | Zoom trình duyệt 200% vẫn đọc được, không vỡ layout | ⬜ | |
| 10 | **Không lộ mã trạng thái nội bộ ra giao diện** (vd hiện thẳng `OUTSIDE_CHECKIN_WINDOW`) | ⬜ | |
| 11 | Bảo toàn dữ liệu form khi validate fail — không xoá trắng cái đã nhập | ⬜ | |
| 12 | Nhất quán màu trạng thái giữa các màn hình | ⬜ | |
| 13 | Độ trễ mạng thật (SUT là môi trường dev từ xa) — có phản hồi trong lúc chờ không | ⬜ | |
| 14 | Responsive dưới 768px (Task 3 sẽ soi lại) | ⬜ | |

Với **mỗi item bạn tự thêm**, ghi ngay một dòng vào `team/ai-prompts.md` mục 3, chọn 1 trong 3 loại lý do:

| Loại | Nghĩa | Ví dụ cách viết |
|---|---|---|
| **(a)** Prompt của tôi thiếu ngữ cảnh | Nêu rõ thiếu thông tin gì | *"AI không sinh item về độ trễ mạng vì prompt không nhắc SUT là môi trường dev từ xa. Sau khi bổ sung thông tin này AI mới sinh được nhóm item skeleton/loading."* |
| **(b)** Giới hạn của model | Nêu rõ giới hạn nào | *"AI không thấy được màn hình nên không biết avatar dạng chữ viết tắt bị tràn với tên nhiều từ."* |
| **(c)** Đặc thù riêng của EMS | Nêu rõ chi tiết nào chỉ lộ khi thao tác thật | *"AI mặc định i18n là chuyện của màn hình, không nghĩ tới việc dữ liệu Excel xuất ra cũng là bề mặt giao diện. Chỉ phát hiện sau khi bấm Export và mở file."* |

> **Đây là phần được chấm kỹ nhất của Task 1A.** Viết chung chung kiểu "AI không đủ thông minh" là mất điểm.

### Bước 6 · 15 phút — Chốt và kiểm đếm

- [ ] Đếm bằng lệnh, không đếm bằng mắt: `grep -c "^| G-" team/gui-checklist.md` (làm tương tự cho F-, N-, S-)
- [ ] Tổng **> 40**
- [ ] Mỗi khía cạnh đạt mục tiêu tối thiểu (12/12/8/10)
- [ ] Mọi item có mã nguồn heuristic
- [ ] Mọi item có `AI` hoặc `RV` ở cột Nguồn gốc
- [ ] Số item `RV` khớp với số dòng giải thích ở `team/ai-prompts.md`
- [ ] Điền `team/references.md`: nguồn nào dùng cho item nào
- [ ] Ghi mọi lượt prompt vào `appendix/a3-ai-audit-report.md`
- **Commit:** `docs(task1a): add shared GUI checklist (N items across IA-01..IA-04)`

---

## 4. Ghi phần đóng góp cho trung thực

Thêm vào đầu `team/gui-checklist.md`:

```markdown
**Đóng góp:** bản v1 (toàn bộ 4 khía cạnh) do Phạm Vũ Ngọc Duy (23127183) dựng ngày [ngày],
dựa trên khảo sát trực tiếp EMS ngày [ngày]. Đã gửi cả nhóm rà soát ngày [ngày].
[Nếu có người rà: ghi tên + phần họ rà. Nếu không: ghi "Không nhận được phản hồi rà soát
tính đến ngày [ngày]; bản này được dùng làm checklist chung."]
```

Đồng thời nhắc đến việc này một câu trong `00-main-report.md` mục 1 — người chấm thấy bạn chủ động chứ không phải ăn theo.

---

## 5. Ba lỗi khiến 2 tiếng đổ sông đổ biển

| Lỗi | Hậu quả | Cách tránh |
|---|---|---|
| Sinh 40 item bằng **một** prompt duy nhất | Đề cấm tường minh cách làm này (§2 "Guide, don't dump"); item sẽ chung chung, nhiều cái trùng nghĩa | Chạy đúng 4 prompt riêng cho 4 khía cạnh |
| Viết item mơ hồ kiểu "giao diện phải trực quan" | Sang Task 1B không đánh Passed/Failed nổi → hỏng dây chuyền 15đ tiếp theo | Mỗi item phải trả lời được bằng **có/không** khi nhìn màn hình |
| Chỉ có item `AI`, không có item `RV` | Mất phần lớn 15đ — đề chấm chính ở chỗ human review | Bước 5 phải cho ra ít nhất 10–15 item `RV` |
