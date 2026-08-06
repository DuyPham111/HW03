# Kịch bản quay Video Demo — Skill `hw03-gui-checklist`

> ⚠️ Folder này **nằm ngoài** `23127183_HW03_AI_GUIUsability_EMS_100/` — chỉ để chuẩn bị quay, không tính vào bài nộp. Sau khi quay xong, chỉ cần dán **link video** vào `23127183_HW03_AI_GUIUsability_EMS_100/skills/demo-video-link.md`, không cần nộp folder này.
> Mục tiêu: **1 video ~7 phút**, đủ cho thấy skill `hw03-gui-checklist` chạy từ đầu đến cuối trên một luồng hoàn chỉnh (đúng yêu cầu đề §8), không cần quay thêm Video 2/3.
> Skill gốc: [`../23127183_HW03_AI_GUIUsability_EMS_100/skills/hw03-gui-checklist/SKILL.md`](../23127183_HW03_AI_GUIUsability_EMS_100/skills/hw03-gui-checklist/SKILL.md) — kịch bản này chỉ **chọn lọc và rút gọn** các bước A2, A3, B2, B3, B4 của skill đó cho vừa 7 phút, không bịa thêm bước nào ngoài skill đã viết.
> Prompt dùng sẵn ở file `02-prompt-san-sang.md` cùng thư mục — copy nguyên văn, đừng gõ lại tay lúc quay để đỡ mất thời gian.

---

## Chuẩn bị trước khi bấm Record

- [ ] Mở sẵn 2 cửa sổ: (1) Claude Code / công cụ AI bạn dùng, (2) trình duyệt đã đăng nhập EMS bằng `23127183@student.hcmus.edu.vn`
- [ ] Mở sẵn `skills/hw03-gui-checklist/SKILL.md` ở 1 tab để lát mở ra chỉ
- [ ] Mở sẵn `01-checklist-execution.md`, cuộn tới dòng `G-09` (đã biết kết quả: Failed ở S1)
- [ ] Mở sẵn `04-findings-log.md`, cuộn tới dòng `CL-B1-01` (đã điền sẵn, dùng để đối chiếu — không gõ lại)
- [ ] Phần mềm quay màn hình đã bật, chọn đúng vùng quay có cả 2 cửa sổ
- [ ] Kiểm tra mic rõ tiếng trước khi quay chính thức (quay thử 10 giây, nghe lại)
- [ ] **Chạy thử cả 3 prompt (A2, A3, B3) một lần trước, KHÔNG quay** — để biết trước AI thường trả lời kiểu gì, chọn sẵn trong đầu 1 item cụ thể sẽ chỉ vào lúc quay thật, tránh bị động

> ℹ️ **Folder `video-demo-prep/` này chỉ để bạn tự đọc, không cần AI "thấy" nó.** Ba prompt trong `02-prompt-san-sang.md` được viết tự chứa đầy đủ ngữ cảnh (mô tả SUT, danh sách widget, mô tả bug đều nằm ngay trong prompt) — dán vào **bất kỳ phiên AI nào, kể cả phiên hoàn toàn mới chưa có lịch sử chat**, AI vẫn hiểu và trả lời được, không cần "nhớ" gì từ trước. Bạn có thể mở file này ở 1 màn hình phụ để đọc, không cần hiện trong khung quay.

---

## Kịch bản theo mốc thời gian (tổng ~7 phút)

### 0:00 – 0:40 — Lời chào & giới thiệu skill

**Nói (gần đúng, không cần học thuộc):**

> "Chào thầy/cô và các bạn, mình là Phạm Vũ Ngọc Duy, MSSV 23127183. Đây là video demo Agent Skill `hw03-gui-checklist` cho bài HW03 — GUI & Usability Testing trên hệ thống EMS.
> Skill này giải quyết 2 việc: Phần A giúp dựng checklist GUI có căn cứ heuristic thay vì đoán bừa, Phần B giúp chạy checklist đó trên màn hình thật một cách có hệ thống, không nhảy cóc, và biến kết quả Failed thành bug entry hoàn chỉnh. Mình sẽ demo nhanh cả 2 phần trên đúng dữ liệu thật mình đã dùng khi làm bài."

**Làm:** Trỏ chuột vào file `skills/hw03-gui-checklist/SKILL.md` đang mở, lướt nhanh qua mục "Nguyên tắc" (đừng đọc hết, chỉ chỉ tay qua).

---

### 0:40 – 2:10 — Phần A: sinh item checklist cho 1 khía cạnh (Bước A2)

**Nói:**

> "Đầu tiên là Phần A — dựng checklist. Skill yêu cầu sinh item theo từng khía cạnh riêng, không gộp chung một prompt khổng lồ. Mình sẽ demo với IA-04, khía cạnh Feedback/State."

**Làm:** Dán **Prompt A2** (lấy từ `02-prompt-san-sang.md`) vào AI, đợi output.

**Nói khi có output:**

> "AI trả về bảng item kèm cách kiểm và mã heuristic nguồn. Đây là chỗ quan trọng nhất — mình không lấy nguyên xi. Ví dụ [chỉ vào 1 item cụ thể AI vừa sinh], item này mô tả hơi chung chung / trùng với item mình đã có ở G-XX, nên mình sẽ loại nó / viết lại cho cụ thể hơn."

> ⚠️ **Lúc quay:** output thật của AI mỗi lần chạy có thể khác — bạn cứ chọn **1 item bất kỳ** AI vừa sinh ra để minh hoạ việc review (không cần đúng ví dụ tưởng tượng ở đây), miễn là bạn thật sự chỉ ra được lý do sửa/loại. Đây chính là phần "human review" mà người chấm quan tâm nhất.

---

### 2:10 – 3:10 — Phần A: ép AI tự soi lỗ hổng (Bước A3)

**Nói:**

> "Tiếp theo mình ép AI tự chỉ ra checklist còn thiếu vùng nào, để so sánh với những gì mình đã tự bổ sung sau khi khảo sát EMS thật."

**Làm:** Dán **Prompt A3**, đợi output.

**Nói khi có output:**

> "AI liệt kê một số vùng thiếu ở mức chung — ví dụ [đọc 1-2 vùng AI vừa nêu]. Nhưng khi mình đối chiếu với 23 item mình tự thêm sau khi khảo sát EMS thật, thấy AI không nêu được những đặc thù riêng của hệ thống này — ví dụ chuyện mã QR nằm tách biệt hoàn toàn khỏi luồng đăng ký, hay ba bộ từ vựng trạng thái khác nhau giữa các màn hình. Đó là những thứ chỉ lộ ra khi thao tác thật trên hệ thống, AI không nhìn thấy màn hình nên không đoán được."

---

### 3:10 – 5:00 — Phần B: chạy checklist thật trên EMS, bắt Failed (Bước B2)

> ⚠️ **Không cần chụp ảnh gì thêm trong đoạn này.** Chính video đang quay là bằng chứng — camera ghi lại được cả thao tác lẫn nội dung trên màn hình, không cần dừng lại bấm phím chụp ảnh (`Win+Shift+S`...) giữa lúc quay. Ảnh tĩnh `G-09-S1.png`/`G-09-S2.png` bạn đã có sẵn từ lúc làm Task 1B thật — không liên quan tới video này.

**Nói (trước khi chuyển màn hình):**

> "Giờ chuyển sang Phần B — chạy checklist trên màn hình thật. Mình demo lại item `G-09` mà mình đã từng chạy và phát hiện Failed."

**Làm — theo đúng thứ tự, đọc trước khi quay để nhớ đường đi:**

1. **Chuyển tab/cửa sổ sang trình duyệt đã đăng nhập sẵn EMS** (đừng đăng nhập lại lúc quay, mất thời gian).
2. Ở trang chủ (`prod-dev.ems-fitus.cloud/dashboard`), gõ vào ô **Search events by title** chữ `Workshop B` (hoặc tên sự kiện đã hết chỗ bạn dùng khi chạy Task 1B thật — nếu tên khác, dùng đúng tên thật của bạn, không bắt buộc khớp chữ "Workshop B").
3. Trong kết quả tìm được, **di chuột dừng lại 1–2 giây trên dòng chữ "Location: Updating"** của thẻ sự kiện đó (dừng chuột để người xem kịp đọc, đừng lướt qua nhanh).
4. **Bấm vào thẻ sự kiện** để mở sang trang chi tiết (B2).
5. Ở B2, **cuộn tới khối thông tin sự kiện, di chuột dừng trên dòng "Location"** — lúc này hiện dấu `-` thay vì "Updating".
6. *(Tuỳ chọn, chỉ làm nếu còn dư thời gian)* Avatar góc phải → **View profile** → cuộn tới **My Activities**, tìm đúng sự kiện đó, dừng chuột trên ô Location một lần nữa để chỉ dấu `-` xuất hiện lần thứ 3.

**Nói trong lúc thao tác (đọc đúng lúc chuột đang dừng ở bước 3 và bước 5):**

> *(lúc dừng ở bước 3)* "Đây, thẻ sự kiện trên B1 hiện chữ 'Updating' cho ô Location — chữ này gây hiểu lầm là dữ liệu đang được xử lý."
> *(lúc dừng ở bước 5)* "Nhưng mở đúng sự kiện này ở B2, cùng ô Location lại hiện dấu gạch ngang. Hai ký hiệu khác nhau cho cùng một khái niệm 'không có dữ liệu' — đây chính là item G-09 bị Failed theo đúng heuristic N4 tính nhất quán."

---

### 5:00 – 6:10 — Phần B: dựng bug entry từ kết quả Failed (Bước B3 + B4)

**Nói:**

> "Sau khi có kết quả Failed thật, mình nhờ AI phân tích cụm lỗi trước khi tự chốt severity."

**Làm:** Chuyển sang cửa sổ AI, dán **Prompt B3** (thuần văn bản — mô tả bug đã viết sẵn trong chính prompt, **không cần đính kèm ảnh gì**), đợi output ngắn.

**Nói:**

> "AI đề xuất mức severity, nhưng mình tự điều chỉnh lại theo tác động thật — item này không chặn được việc đăng ký, chỉ gây hiểu lầm, nên mình chốt severity 2, không lấy nguyên đề xuất của AI nếu nó đẩy cao hơn." *(Nếu AI đề xuất đúng 2 luôn thì đổi câu thoại — xem ghi chú ở cuối `02-prompt-san-sang.md`.)*

**Làm:** Chuyển sang cửa sổ đã mở sẵn `04-findings-log.md` (mở từ trước, không mất công tìm), cuộn tới dòng `CL-B1-01` đã điền sẵn, **di chuột chỉ lần lượt từng cột** khi nhắc tới: mô tả · steps to reproduce · severity · suggested fix · ảnh.

**Nói:**

> "Đây là bug entry hoàn chỉnh — CL-B1-01 — đã submit lên Google Form và điền timestamp. Ảnh đính kèm là ảnh tĩnh mình chụp lúc chạy checklist thật ban đầu, đặt tên đúng theo Bug-ID."

---

### 6:10 – 6:50 — Commit & kết

**Làm:** Mở terminal, gõ (hoặc show sẵn) lệnh:
```bash
git log --oneline -3
```
Chỉ vào 1 dòng commit thật liên quan tới checklist/finding.

**Nói:**

> "Cuối cùng, mọi thay đổi được commit theo từng bước có ý nghĩa, đúng quy ước Conventional Commits. Đó là toàn bộ demo skill `hw03-gui-checklist` — từ dựng checklist có căn cứ, tới chạy thật trên hệ thống, tới ghi nhận bug hoàn chỉnh. Cảm ơn thầy/cô và các bạn đã theo dõi."

---

## Sau khi quay xong

- [ ] Xem lại 1 lần, cắt bớt nếu vượt quá ~8 phút (không cần chỉnh sửa cầu kỳ)
- [ ] Upload YouTube, chế độ **Unlisted**, kiểm tra mở được khi chưa đăng nhập
- [ ] Dán link vào bảng "Video 1" ở `23127183_HW03_AI_GUIUsability_EMS_100/skills/demo-video-link.md`
- [ ] Xoá hoặc giữ folder `video-demo-prep/` tuỳ ý — không ảnh hưởng bài nộp vì nằm ngoài thư mục chấm điểm
