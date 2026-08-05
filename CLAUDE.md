# CLAUDE.md — Quy tắc thường trực khi làm HW03

Đọc file này đầu mỗi phiên. Các quy tắc ở §2 **tự động áp dụng**, không cần được nhắc lại.

---

## 1. Biến cố định — không được đoán

| Trường | Giá trị |
|---|---|
| MSSV | `23127183` |
| Họ tên | `Phạm Vũ Ngọc Duy` |
| Email MSSV | `pvnduy23@clc.fitus.edu.vn` |
| Kịch bản | **B — User đăng ký tham dự sự kiện** |
| 3 màn hình | **B2** Trang chi tiết sự kiện · **B3** Form đăng ký · **B4** My Registrations + vé QR |
| SUT | https://prod-dev.ems-fitus.cloud *(link ngrok trong đề đã chết)* |
| Tài khoản admin | `admin@gmail.com` / `Admin@123` — dùng chung cả lớp |
| Google Form findings | https://forms.gle/CJQFQCAXcsDbXDMM9 |
| Repo | https://github.com/DuyPham111/HW03 |
| Nhóm | 5 người / 4 kịch bản → một kịch bản được đôi, hai người phải chọn màn hình rời nhau |

Gặp `_(TODO)_` mà cần dùng giá trị đó → **hỏi**, không tự suy ra, không dùng giá trị ví dụ.

---

## 2. Quy tắc thường trực

**R1 — Log mọi tương tác AI.** *(đề §10)*
Mỗi prompt làm thay đổi bài làm → thêm một block vào `appendix/a3-ai-audit-report.md`: tool · ngày giờ · **prompt nguyên văn** · output · Human Review Notes (sinh viên tự điền).
*Thiếu AI Audit Report → 0 điểm cả bài.*

**R2 — Commit theo từng bước.** *(đề §13)*
Xong một bước có ý nghĩa (một màn hình chạy xong, một phiên user test, một đợt cross-platform, một lần sửa checklist) → đề xuất commit message, commit khi người dùng đồng ý.

Định dạng — Conventional Commits, viết bằng tiếng Anh:
```
<type>(<scope>): <mô tả ngắn, thức mệnh lệnh, không viết hoa đầu, không chấm cuối>
```
- `type` ∈ `docs` · `feat` · `fix` · `chore` · `refactor`
- `scope` ∈ `task1a` · `task1b` · `task2` · `task3` · `findings` · `skills` · `appendix` · `repo`
- Ví dụ: `docs(task1b): run GUI checklist on B3 registration form`

**Trailer `Co-Authored-By`:** commit do AI hỗ trợ có kèm trailer, nhất quán với việc đề bắt buộc khai báo dùng AI (§10). Nếu sinh viên muốn git log chỉ đứng tên mình thì nói rõ để bỏ trailer — khi đó việc dùng AI vẫn được khai đầy đủ ở `appendix/a3-ai-audit-report.md`.

**R3 — Mọi phát hiện vào findings log.** *(đề §7)*
Bất kỳ lỗi hay vấn đề usability nào xuất hiện trong hội thoại → thêm ngay vào `04-findings-log.md` đủ 9 cột, kèm đề xuất severity 0–4 và lý do chấm. Prefix theo nguồn: `CL-` checklist · `US-` user testing · `CP-` cross-platform · `SV-` khảo sát EMS ban đầu.

Cột `Form-submission timestamp` để trống cho tới khi sinh viên tự submit form — **không tự điền**.

**R4 — Giữ README đúng.** *(đề §15, §18)*
Số liệu nào đổi → cập nhật bảng test summary và bảng trạng thái trong `README.md` ngay.

**R5 — Đánh dấu phần chưa kiểm chứng.** *(đề §2)*
Mọi nội dung sinh ra mà chưa được kiểm trên EMS thật phải có ⚠️ và ô `[ ]` để sinh viên verify. Nói rõ trong câu trả lời, không im lặng.
*"Nộp thẳng output thô của AI là không chấp nhận được."*

**R6 — Số liệu phải nhất quán.** Khi số item checklist / số findings / số ô ma trận thay đổi → cập nhật **đồng thời** mọi nơi trích số đó, và **đếm lại bằng lệnh** (`grep -c`), không tin trí nhớ.

**R7 — Không bịa dữ liệu.** Không điền Passed/Failed, không điền Actual, không tạo participant, không tạo kết quả cross-platform. Những ô này chỉ sinh viên điền sau khi chạy thật.

---

## 3. Việc sinh viên tự làm — không làm hộ, không nhắc mỗi phiên

Chạy checklist trên EMS · chụp ảnh · tuyển và chạy 5 phiên user testing · chạy BrowserStack · submit Google Form · quay video · xuất PDF · đóng gói zip.

---

## 4. Ràng buộc khi tạo nội dung

**Chung** — bài viết bằng Markdown. Công việc không được trùng với thành viên khác trong nhóm.

**Task 1A** — checklist > 40 item, phủ IA-01…IA-04. Mỗi item phải kiểm chứng được (nhìn màn hình kết luận Passed/Failed ngay) và có mã heuristic nguồn. Item do người bổ sung phải có lý do "vì sao AI sót" ở `team/references.md` · `team/ai-prompts.md`.

**Task 1B** — mỗi ô phải có `Passed` / `Failed` / `N/A`, **không để trống**. Ảnh **chỉ** cho mục Failed. Ô N/A phải ghi lý do. Tỉ lệ pass không tính N/A vào mẫu số.

**Task 2** — task scenario hướng **mục tiêu**, không chỉ đường. Pilot chạy trước và **không tính** vào 5 người. Liên hệ che 4 số giữa. Participant phải ngoài lớp. Severity thang Nielsen 0–4, kèm cột số người gặp phải.

**Task 3** — mỗi OS ≥ 1, mỗi browser ≥ 1, mỗi device class ≥ 1, **cho từng màn hình**. Ảnh **mọi ô**, mỗi ảnh phải thấy email MSSV + URL EMS + tên browser/OS/device. Ghi rõ emulator hay thiết bị thật.

**Phụ lục** — AI Critique **200–300 từ**, đếm bằng `wc -w` trước khi kết luận là đạt.

---

## 5. Tra cứu

| Cần gì | Ở đâu |
|---|---|
| Kế hoạch tổng, lộ trình 6 giai đoạn | `docs/KE_HOACH_HW03.md` |
| Từng hạng mục làm gì & nộp gì | `docs/HUONG_DAN_CHI_TIET_TUNG_PHAN.md` |
| AI làm gì / tôi làm gì + prompt sẵn | `docs/QUY_TRINH_AI_VA_TOI.md` |
| Làm checklist nhóm một mình | `docs/TASK1A_LAM_MOT_MINH.md` |
| Phiếu khảo sát EMS (điền vào chỗ trống) | `docs/KHAO_SAT_EMS.md` |
| Danh sách commit các bước tiếp theo | `docs/COMMIT_PLAN.md` |
| Đề chi tiết (bản chấm điểm) | `docs/DE_BAI_02_Spec_HW03_VI.md` |
| Đề gốc tiếng Anh | `docs/de-goc/` |
| Cấu trúc bài nộp, trạng thái, self-assessment | `23127183_HW03_AI_GUIUsability_EMS_100/README.md` |

**Lưu ý môi trường:** EMS là hệ thống **dùng chung với sinh viên khác** và dữ liệu có thể bị reset — chụp bằng chứng ngay khi làm; dữ liệu tự tạo đặt tiền tố `[23127183]`.
