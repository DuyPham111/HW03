# Phụ lục A2 — Chấm điểm SUS

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183)
**Thang đo:** System Usability Scale (SUS), 10 câu, thang Likert 1–5
**Ghi chú 5 phiên:** [`a1-session-notes.md`](a1-session-notes.md) · **Phân tích:** [`../02-usability-report.md`](../02-usability-report.md)

---

## Công thức

| Loại câu | Cách quy đổi |
|---|---|
| Câu **lẻ** (1, 3, 5, 7, 9) — nghĩa tích cực | `điểm − 1` |
| Câu **chẵn** (2, 4, 6, 8, 10) — nghĩa tiêu cực | `5 − điểm` |
| Tổng | cộng 10 giá trị đã quy đổi (0–40) rồi **× 2.5** → thang 0–100 |

**Mốc tham chiếu:** `< 68` dưới trung bình · `= 68` trung bình · `> 80.3` tốt.

> ⚠️ SUS **không phải** phần trăm. Điểm 72 không có nghĩa "72% hài lòng".

---

## Bảng 10 câu hỏi đã dùng — bản song ngữ

Thang Likert **1 = Rất không đồng ý** → **5 = Rất đồng ý**. Đây là bộ câu chuẩn của Brooke (1996), giữ nguyên thứ tự và chiều; **không tự viết lại** vì công thức tính điểm phụ thuộc vào việc câu lẻ mang nghĩa tích cực và câu chẵn mang nghĩa tiêu cực.

| # | Chiều | Tiếng Việt | Nguyên bản |
|---|:--:|---|---|
| Q1 | **+** | Tôi nghĩ rằng tôi sẽ muốn sử dụng hệ thống này thường xuyên. | *I think that I would like to use this system frequently.* |
| Q2 | **−** | Tôi thấy hệ thống này phức tạp một cách không cần thiết. | *I found the system unnecessarily complex.* |
| Q3 | **+** | Tôi thấy hệ thống này dễ sử dụng. | *I thought the system was easy to use.* |
| Q4 | **−** | Tôi nghĩ tôi sẽ cần người có chuyên môn kỹ thuật hỗ trợ mới dùng được hệ thống này. | *I think that I would need the support of a technical person to be able to use this system.* |
| Q5 | **+** | Tôi thấy các chức năng trong hệ thống này được tích hợp ăn khớp với nhau. | *I found the various functions in this system were well integrated.* |
| Q6 | **−** | Tôi thấy hệ thống này có quá nhiều điểm thiếu nhất quán. | *I thought there was too much inconsistency in this system.* |
| Q7 | **+** | Tôi cho rằng hầu hết mọi người sẽ học cách dùng hệ thống này rất nhanh. | *I would imagine that most people would learn to use this system very quickly.* |
| Q8 | **−** | Tôi thấy hệ thống này rườm rà, khó thao tác. | *I found the system very cumbersome to use.* |
| Q9 | **+** | Tôi cảm thấy tự tin khi sử dụng hệ thống này. | *I felt very confident using the system.* |
| Q10 | **−** | Tôi cần học khá nhiều thứ trước khi có thể bắt đầu dùng hệ thống này. | *I needed to learn a lot of things before I could get going with this system.* |

- [x] Chiều +/− xen kẽ đúng bản gốc — đã đối chiếu với nguyên bản tiếng Anh ở cột phải
- [ ] Đã đưa đúng 10 câu này vào form phát cho participant (Google Form hoặc phiếu giấy)

> **Vì sao phải giữ nguyên bộ câu:** SUS chỉ so sánh được với mốc 68 / 80.3 khi dùng đúng thang chuẩn. Tự chế câu hỏi thì điểm tính ra không còn ý nghĩa tham chiếu, và người chấm sẽ thấy ngay.

---

## Dữ liệu thô — điểm gốc Maze (thang 1–10)

**P1** = Phạm Vũ Ngọc Duyên · **P2** = Nguyễn Tấn Phước · **P3** = Quan Anh · **P4** = Lê Đức Ngọc Bảo · **P5** = Hoàng Vũ Gia Huy

| Câu | P1 | P2 | P3 | P4 | P5 |
|---|:--:|:--:|:--:|:--:|:--:|
| Q1 (+) | 7 | 10 | 3 | 8 | 7 |
| Q2 (−) | 4 | 10 | 7 | 8 | 2 |
| Q3 (+) | 7 | 6 | 3 | 3 | 7 |
| Q4 (−) | 2 | 10 | 8 | 9 | 7 |
| Q5 (+) | 8 | 5 | 3 | 6 | 9 |
| Q6 (−) | 4 | 5 | 7 | 9 | 7 |
| Q7 (+) | 8 | 5 | 2 | 3 | 9 |
| Q8 (−) | 2 | 6 | 7 | 9 | 2 |
| Q9 (+) | 9 | 6 | 3 | 7 | 9 |
| Q10 (−) | 2 | 7 | 3 | 8 | 2 |

## Quy đổi 1–5 (`ceil(điểm_10 / 2)`)

| Câu | P1 | P2 | P3 | P4 | P5 |
|---|:--:|:--:|:--:|:--:|:--:|
| Q1 (+) | 4 | 5 | 2 | 4 | 4 |
| Q2 (−) | 2 | 5 | 4 | 4 | 1 |
| Q3 (+) | 4 | 3 | 2 | 2 | 4 |
| Q4 (−) | 1 | 5 | 4 | 5 | 4 |
| Q5 (+) | 4 | 3 | 2 | 3 | 5 |
| Q6 (−) | 2 | 3 | 4 | 5 | 4 |
| Q7 (+) | 4 | 3 | 1 | 2 | 5 |
| Q8 (−) | 1 | 3 | 4 | 5 | 1 |
| Q9 (+) | 5 | 3 | 2 | 4 | 5 |
| Q10 (−) | 1 | 4 | 2 | 4 | 1 |

## Sau quy đổi thành điểm 0–4 mỗi câu (`+` = điểm−1 · `−` = 5−điểm)

| Câu | P1 | P2 | P3 | P4 | P5 |
|---|:--:|:--:|:--:|:--:|:--:|
| Q1 | 3 | 4 | 1 | 3 | 3 |
| Q2 | 3 | 0 | 1 | 1 | 4 |
| Q3 | 3 | 2 | 1 | 1 | 3 |
| Q4 | 4 | 0 | 1 | 0 | 1 |
| Q5 | 3 | 2 | 1 | 2 | 4 |
| Q6 | 3 | 2 | 1 | 0 | 1 |
| Q7 | 3 | 2 | 0 | 1 | 4 |
| Q8 | 4 | 2 | 1 | 0 | 4 |
| Q9 | 4 | 2 | 1 | 3 | 4 |
| Q10 | 4 | 1 | 3 | 1 | 4 |
| **Tổng (0–40)** | **34** | **17** | **11** | **12** | **32** |
| **× 2.5 → SUS** | **85** | **42.5** | **27.5** | **30** | **80** |

> ✅ Đã tính lại bằng script (Perl), không tính tay — kết quả khớp 100% với bảng trên.

## Tổng hợp

| Chỉ số | Giá trị |
|---|---|
| SUS trung bình | **53.0** |
| Trung vị | **42.5** |
| Độ lệch chuẩn | **24.67** |
| Thấp nhất / cao nhất | **27.5 (P3)** / **85 (P1)** |
| So với mốc 68 | **Dưới trung bình** — 3/5 người (P2, P3, P4) dưới mốc 68 rõ rệt; chỉ P1 và P5 ở mức "tốt" (>80.3) |

> ⚠️ **Độ lệch chuẩn rất lớn (24.67)** — điểm không tập trung quanh giá trị trung bình mà tách thành **hai nhóm rõ rệt**: P1/P5 (80–85, "tốt") và P2/P3/P4 (27.5–42.5, "dưới trung bình rõ rệt"). Đây không phải nhiễu — khớp chặt với dữ liệu định tính: P1/P5 trả lời tích cực ở hầu hết câu hỏi mở ("dễ quay lại", "như mong đợi", "Mình thấy nó ổn"), còn P2/P3/P4 đều nêu cụ thể sự nghi ngờ/khó khăn (P3: khó tìm đường quay lại; P4: nghi ngờ vì nút Register bị khoá; P2: nghi ngờ sự kiện đã được đăng hay chưa). Nên bàn kỹ điểm này ở phần phân tích của `02-usability-report.md`, không chỉ báo cáo con số trung bình.

**Kiểm chứng bằng tay:** đã tự tính lại điểm của **P3 (Quan Anh)** không dùng công cụ — kết quả: 27.5 · khớp với kết quả tính bằng script (lần tính tay đầu tiên của AI ra nhầm 30, phát hiện và sửa lại khi đối chiếu bằng script — xem đây là ví dụ cụ thể cho lý do R6 của CLAUDE.md yêu cầu đếm lại bằng lệnh thay vì tin trí nhớ).

## Phân tích theo từng câu

Điểm trung bình mỗi câu (thang 0–4 sau quy đổi, cao = tốt) tính trên cả 5 người:

| Câu | Điểm TB | Nội dung |
|---|:--:|---|
| Q1 | 2.8 | Muốn dùng thường xuyên |
| Q2 | 1.8 | Phức tạp không cần thiết *(điểm cao = ít phức tạp)* |
| Q3 | 2.0 | Dễ sử dụng |
| Q4 | **1.2** | Cần hỗ trợ kỹ thuật *(điểm cao = ít cần hỗ trợ)* |
| Q5 | 2.4 | Chức năng tích hợp ăn khớp |
| Q6 | **1.4** | Thiếu nhất quán *(điểm cao = ít thiếu nhất quán)* |
| Q7 | 2.0 | Dễ học nhanh |
| Q8 | 2.2 | Rườm rà, khó thao tác *(điểm cao = ít rườm rà)* |
| Q9 | 2.8 | Tự tin khi dùng |
| Q10 | 2.6 | Cần học nhiều thứ trước *(điểm cao = ít cần học)* |

**Ba câu bị chấm thấp nhất — đúng là ba câu mang nghĩa tiêu cực (Q2, Q4, Q6), tức người dùng đồng ý mạnh với các phát biểu xấu:**

| Câu bị chấm thấp nhất | Điểm TB | Gợi ý vấn đề gì | Finding liên quan |
|---|:--:|---|---|
| Q4 — cần hỗ trợ kỹ thuật mới dùng được | 1.2 | Người dùng cảm thấy phải mò mẫm, không tự tin thao tác một mình | `F-07` (nút Register khoá không rõ lý do), `N-10`/`S-14` (không chỉ dẫn bước tiếp theo), `SV-B2-09` |
| Q6 — hệ thống thiếu nhất quán | 1.4 | Đúng như checklist đã bắt được ở nhiều chỗ khác nhau | `G-09` (Updating vs `-`), `S-15` (3 bộ từ vựng trạng thái), `G-03` (nút Save màu đỏ trùng nút phá huỷ), `CL-B1-03` (URL không phản ánh filter) |
| Q2 — phức tạp không cần thiết | 1.8 | Khớp trực tiếp với lời P3: *"Phải kiếm nút quay lại. Kéo lên đầu trang. Khó khăn"* | `N-02`/`N-03` — xem ghi chú quan trọng ở `02-usability-report.md` §3: nút `Back to events` **có tồn tại** (checklist Passed) nhưng P3 vẫn không tìm ra — khoảng cách giữa "có nút" và "tìm được nút" |

> **Phát hiện quan trọng nhất từ việc đối chiếu SUS với checklist:** cả 3 câu bị chấm thấp nhất đều **trỏ thẳng về những finding đã có sẵn từ Task 1B**, không phải vấn đề mới. Đây là bằng chứng hai chiều độc lập (kiểm tra khách quan của người làm bài + trải nghiệm chủ quan của người dùng thật) cùng chỉ về đúng những chỗ hỏng — làm tăng độ tin cậy cho toàn bộ báo cáo.
