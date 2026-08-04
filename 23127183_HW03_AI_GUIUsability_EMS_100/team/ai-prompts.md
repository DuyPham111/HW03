# AI Prompts — dựng checklist GUI của nhóm

**Nhóm:** _(TODO)_ · **Bài:** HW03 Task 1A · **Ngày:** _(TODO)_

> Sản phẩm nhóm bắt buộc thứ 3 của Task 1A. Đề yêu cầu nộp **các AI prompt đã dùng để sinh và tinh chỉnh checklist**, và với **mỗi item người tự thêm** phải **giải thích vì sao AI bỏ sót**.
> Nội dung file này **cũng phải xuất hiện trong `appendix/a3-ai-audit-report.md`** (§10 của đề: *"The group's checklist prompts belong here as well"*).
> ⚠️ Prompt của nhóm được phép giống nhau **trong nội bộ nhóm**. Chia sẻ prompt **sang nhóm/sinh viên khác = 0 điểm cả hai bên**.

---

## 1. Nguyên tắc dùng AI cho task này

Đề cấm dùng một prompt chung chung kiểu *"generate a GUI checklist and find usability problems in this app"*. Phải **dẫn AI đi từng bước** như kỹ thuật được dạy. Chuỗi prompt gợi ý:

1. **Nạp nền lý thuyết** — cho AI biết chính xác khung heuristic sẽ dùng (Nielsen 10 / Norman 6 / Shneiderman 8) và bắt nó gắn mỗi item với một heuristic cụ thể.
2. **Nạp bối cảnh SUT** — mô tả EMS và 4 khía cạnh IA-01…IA-04, kèm danh sách widget thật quan sát được (upload 4:3 / 24:9, RichTextEditor, drag-drop reorder, toast, badge, progress bar, EN/VI switch…).
3. **Sinh theo từng IA một** — không xin cả 40 item một lượt; xin riêng IA-01, rồi IA-02, IA-03, IA-04 để kiểm soát chất lượng từng cụm.
4. **Ép tiêu chí chất lượng** — mỗi item phải kiểm chứng được (Passed/Failed rõ ràng), không trùng nghĩa, có cột "cách kiểm".
5. **Bắt AI tự soi lỗ hổng** — hỏi ngược: "checklist này còn thiếu vùng nào?" rồi **so với thực tế quan sát được trên EMS** để tìm chỗ AI vẫn sót.
6. **Người review & bổ sung** — chốt danh sách item tự thêm và ghi lý do AI sót.

---

## 2. Log prompt

### [P-01] — _(TODO: mục đích, ví dụ: nạp khung heuristic + bối cảnh EMS)_

- **Tool:** _(ChatGPT / Claude / Gemini / …, ghi rõ model)_
- **Ngày & giờ:** _(TODO)_
- **Prompt (nguyên văn):**
```
(TODO — dán nguyên văn, không tóm tắt)
```
- **AI Output (tóm tắt + phần chính):**
```
(TODO)
```
- **Human review — đã sửa/loại gì và vì sao:**
> _(TODO)_

### [P-02] — _(TODO: sinh item cho IA-01)_

- **Tool:** · **Ngày & giờ:**
- **Prompt (nguyên văn):**
```
(TODO)
```
- **AI Output:**
```
(TODO)
```
- **Human review:**
> _(TODO)_

### [P-03] — _(TODO: sinh item cho IA-02)_
### [P-04] — _(TODO: sinh item cho IA-03)_
### [P-05] — _(TODO: sinh item cho IA-04)_
### [P-06] — _(TODO: yêu cầu AI tự chỉ ra lỗ hổng của chính checklist)_
### [P-07] — _(TODO: tinh chỉnh câu chữ / gộp item trùng / chuẩn hoá ID)_

---

## 3. Item do NGƯỜI bổ sung — vì sao AI bỏ sót

Đây là phần được chấm kỹ nhất trong Task 1A. Mỗi dòng phải có lý do **cụ thể**, không viết chung chung kiểu "AI không đủ thông minh".

**Ba loại lý do đề gợi ý:** (a) chất lượng prompt của mình chưa đủ · (b) giới hạn của model · (c) đặc thù riêng của giao diện EMS mà AI không thể biết nếu không thao tác thật.

| ID item | Nội dung item (rút gọn) | IA | Loại lý do | Giải thích cụ thể |
|---|---|---|---|---|
| _(TODO)_ | | | (a)/(b)/(c) | |
| | | | | |
| | | | | |

**Ví dụ minh hoạ cách viết cột "Giải thích cụ thể"** *(thay bằng trường hợp thật của nhóm)*:

> *Loại (c) — đặc thù EMS:* AI không đề xuất item kiểm tra "nội dung file Excel export có được dịch theo ngôn ngữ đang chọn không", vì trong prompt nhóm chỉ mô tả EMS có công tắc EN/VI ở header. AI mặc định i18n là chuyện của màn hình, không nghĩ tới việc **dữ liệu xuất ra ngoài** cũng là bề mặt giao diện. Nhóm chỉ phát hiện được sau khi thật sự bấm Export ở màn Users và mở file lên xem.

> *Loại (a) — prompt chưa đủ:* AI không sinh item nào về **trạng thái mạng chậm** vì prompt không hề nhắc rằng SUT là môi trường dev từ xa, có độ trễ mạng thật. Sau khi bổ sung thông tin này vào prompt ở [P-06], AI mới sinh được nhóm item về skeleton/loading state.

---

## 4. Tổng kết

| Chỉ số | Số lượng |
|---|:--:|
| Số prompt đã dùng | |
| Số item AI sinh ra ban đầu | |
| Số item bị loại sau human review (trùng / mơ hồ / không kiểm chứng được) | |
| Số item người bổ sung | |
| **Tổng item cuối cùng** (phải > 40) | |
