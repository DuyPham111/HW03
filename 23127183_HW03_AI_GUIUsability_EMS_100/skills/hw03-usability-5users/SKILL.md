---
name: hw03-usability-5users
description: >-
  Chạy quy trình user testing 5 người thật theo 3 giai đoạn (thiết kế → chạy phiên
  → phân tích) và kết xuất thành Usability Report có severity 0-4. Dùng khi cần
  viết task scenario hướng mục tiêu, soạn phiếu SUS/UEQ-S, ghi chú phiên
  think-aloud, hoặc phân tích dữ liệu 5 phiên thành finding xếp hạng.
---

# Usability Testing với 5 người thật → Usability Report

## Nguyên tắc

- **Task scenario nêu MỤC TIÊU, không nêu các bước bấm.** Viết "đăng ký một workshop sắp diễn ra và cho tôi xem lại đăng ký đó" — không viết "bấm vào Events, chọn sự kiện, bấm Register", và **không nói địa điểm xem lại nằm ở đâu** (không nói "trong hồ sơ của bạn" — đó chính là thứ cần đo participant có tự tìm ra không). *(Đề dùng ví dụ "cho tôi xem mã QR check-in" — đã đổi sang tiêu chí My Activities vì QR trên EMS thật là mã cố định theo tài khoản, không xác nhận được đã đăng ký hay chưa; xem `02-usability-report.md` §1.1.)*
- **Người tham gia phải là người THẬT, NGOÀI lớp.** TA có thể gọi ngẫu nhiên 2 người xác minh; giả mạo = 0 điểm Task 2.
- **AI không thay được người dùng.** AI dùng để: soạn kịch bản, soạn phiếu, cấu trúc hoá ghi chú, tính điểm, gom nhóm pain point. AI **không** được dùng để bịa dữ liệu phiên.
- **Quan sát trung lập.** Không gợi ý, không giải thích hộ, không bênh sản phẩm. Chỉ can thiệp khi người dùng bí hoàn toàn.
- **Ghi chú verbatim.** Câu nói nguyên văn của người dùng có sức nặng hơn diễn giải của bạn.

---

## GIAI ĐOẠN 1 — Thiết kế & chuẩn bị

### Bước 1.1 — Viết task scenario

```
SUT: EMS, các màn hình tôi phụ trách: [liệt kê 3 màn + mô tả chức năng].
Viết 3 phương án task scenario cho user testing, mỗi phương án:
- Nêu MỤC TIÊU người dùng cần đạt, TUYỆT ĐỐI không liệt kê các bước thao tác
- Bắt buộc đi qua cả 3 màn hình trên
- Có tiêu chí "hoàn thành" quan sát được từ bên ngoài
- Thực tế với người dùng chưa từng thấy hệ thống này
Sau mỗi phương án, nêu rủi ro: chỗ nào người dùng có thể hiểu sai đề bài.
```
→ **Người review:** chọn 1 phương án, tự đọc to lên xem có vô tình lộ bước thao tác không.

### Bước 1.2 — Bộ đo & câu hỏi probe

```
Với task scenario này: [dán].
1) Định nghĩa cụ thể thế nào là Completed / Partial / Failed cho tác vụ này.
2) Định nghĩa thế nào tính là 1 "error" và thế nào tính là 1 "hesitation".
3) Soạn 5 câu hỏi mở phủ 4 chủ đề: clarity, error recovery, speed, trust.
   Câu hỏi phải trung lập, không dẫn dắt (tránh "bạn thấy khó dùng chỗ nào?").
4) Soạn phiếu SUS 10 câu bản tiếng Việt, giữ đúng cấu trúc đảo chiều câu chẵn/lẻ.
```
→ **Người review:** kiểm tra 10 câu SUS có đúng thứ tự dương/âm xen kẽ không — AI hay dịch sai chiều câu, làm hỏng công thức tính điểm.

### Bước 1.3 — Tuyển người & pilot

- 5 người **ngoài lớp**, khớp chân dung người dùng (sinh viên / giảng viên / người đi dự sự kiện).
- Ghi liên hệ, **che 4 số giữa** số điện thoại.
- **Chạy pilot với người thứ 6** trước — mục đích là phát hiện đề bài mơ hồ hoặc luồng bị hỏng, không phải lấy dữ liệu.
- **Commit:** `[task2][phase-1] Design task scenario, metrics, SUS form; run pilot`

---

## GIAI ĐOẠN 2 — Chạy 5 phiên

### Kịch bản mở đầu (đọc nguyên văn cho mọi participant để đồng nhất)

> "Mình đang test **sản phẩm này**, không phải test bạn — bạn không thể làm sai được. Trong lúc làm, bạn nói to những gì đang nghĩ giúp mình nhé: bạn đang tìm gì, bạn mong điều gì xảy ra, chỗ nào làm bạn phân vân. Nếu bạn im lặng lâu mình sẽ nhắc. Mình sẽ không trả lời câu hỏi trong lúc bạn làm, để xem hệ thống tự giải thích được đến đâu."

### Trong phiên

| Việc | Cách làm |
|---|---|
| Bấm giờ | Bắt đầu khi participant chạm chuột lần đầu, dừng khi đạt success criteria |
| Ghi chú | Dùng bảng dòng thời gian: `thời điểm · làm gì · nói gì (verbatim) · phân loại · màn hình` |
| Khi bị hỏi | Trả lại câu hỏi: "Bạn nghĩ nó sẽ làm gì?" — không giải thích |
| Khi bí | Đợi đủ ngưỡng đã định (vd 2 phút) rồi mới gợi ý mức tối thiểu, **ghi lại là đã can thiệp** |
| Kết phiên | Điền SUS/UEQ-S **trước** khi hỏi câu mở, để không bị ảnh hưởng bởi cuộc trò chuyện |

### Sau mỗi phiên (làm ngay, đừng dồn)

```
Đây là ghi chú thô phiên P[N]: [dán].
1) Chuyển thành bảng dòng thời gian: | Thời điểm | Hành động | Verbatim | Phân loại | Màn hình |
   Phân loại chỉ được dùng: error / hesitation / frustration / success.
2) Đếm số error và số hesitation theo đúng định nghĩa: [dán định nghĩa ở bước 1.2].
3) KHÔNG diễn giải nguyên nhân, KHÔNG đề xuất sửa ở bước này.
```
→ **Người review:** kiểm lại từng dòng verbatim có đúng lời participant không. AI hay "làm mượt" câu nói — làm mất tín hiệu.

- **Commit sau mỗi phiên:** `[task2][phase-2] Session P[N]: <success status>, SUS <điểm>`

---

## GIAI ĐOẠN 3 — Phân tích & báo cáo

### Bước 3.1 — Tính điểm & lập bảng metric

Công thức **SUS**: câu lẻ (1,3,5,7,9) lấy `điểm − 1`; câu chẵn (2,4,6,8,10) lấy `5 − điểm`; cộng lại rồi **× 2.5** → thang 0–100.
Mốc tham chiếu: **< 68** dưới trung bình · **68** trung bình · **> 80.3** tốt.

→ **Tự tính tay ít nhất 1 phiếu** để kiểm chứng kết quả AI tính — đây là chỗ AI sai rất dễ mà lại khó nhìn ra.

### Bước 3.2 — Gom nhóm và tách bug vs vấn đề hệ thống

```
Đây là dữ liệu 5 phiên đã cấu trúc hoá: [dán 5 bảng dòng thời gian + metric].
1) Gom các điểm ma sát tương tự nhau thành nhóm; mỗi nhóm ghi rõ có mấy trên 5
   participant gặp phải, kèm trích dẫn verbatim làm bằng chứng.
2) Với mỗi nhóm, phân loại: BUG ĐƠN LẺ hay VẤN ĐỀ THIẾT KẾ HỆ THỐNG — nêu căn cứ.
3) Gán severity 0-4 theo thang Nielsen, giải thích căn cứ cho từng mức.
4) Chỉ dùng dữ liệu tôi dán. Nếu một nhận định không có bằng chứng trong dữ liệu,
   nói rõ là "không đủ dữ liệu" thay vì suy đoán.
```
→ **Người review:** ràng buộc quan trọng nhất là điểm 4. AI có xu hướng "điền vào chỗ trống" bằng vấn đề usability kinh điển mà 5 người của bạn chưa hề gặp.

### Bước 3.3 — Viết khuyến nghị

Mỗi khuyến nghị phải: (1) trỏ tới finding cụ thể, (2) mô tả **thay đổi cụ thể** chứ không phải mục tiêu ("gộp 2 bước đăng ký thành 1 màn", không phải "cải thiện trải nghiệm đăng ký"), (3) có ưu tiên P0/P1/P2.

- **Commit:** `[task2][phase-3] Score SUS, rank findings by severity, write recommendations`

---

## Checklist review trước khi đóng Task 2

- [ ] Đúng 5 participant, đều ngoài lớp, liên hệ đã che 4 số giữa
- [ ] Có pilot với người thứ 6, ghi rõ đã sửa gì sau pilot
- [ ] Bảng metric đủ 5 dòng, có dòng trung bình
- [ ] Mỗi finding có: số người gặp / severity / heuristic / ảnh / khuyến nghị
- [ ] Có tách rõ bug đơn lẻ vs vấn đề hệ thống
- [ ] Bằng chứng thô đã lưu vào `evidence/task2/`
- [ ] Bug thật đã submit Google Form và vào `04-findings-log.md` (prefix `US-`)
