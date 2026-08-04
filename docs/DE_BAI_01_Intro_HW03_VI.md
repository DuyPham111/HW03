# [BẢN DỊCH] HW03 — Giới thiệu: Kiểm thử GUI & Usability trên EMS

> **Nguồn:** `HW03_EMS_Intro_EN.md` (bản slide giới thiệu HW03)
> **Bản dịch tiếng Việt để đọc hiểu — khi có tranh chấp nội dung, lấy bản tiếng Anh gốc làm chuẩn.**
> **⚠️ Cập nhật:** link SUT ghi trong slide (`promoter-starboard-prude.ngrok-free.dev`) đã chết. Link hiện hành: **https://prod-dev.ems-fitus.cloud** — đã thay trong bản dịch này.

**KIỂM THỬ PHẦN MỀM · PHIÊN BẢN AI-FIRST (2026)**

**HW03 — Kiểm thử GUI & Usability trên Hệ thống Quản lý Sự kiện (EMS)**

Thiết kế một checklist GUI dùng chung · test kịch bản của bạn · đánh giá tính khả dụng · chạy đa nền tảng.

**Nhóm + cá nhân** · **4 kịch bản A–D** · **3 nhiệm vụ** · **AI-first**

```
SUT:  https://prod-dev.ems-fitus.cloud
```

---

## TỔNG QUAN — Bạn sẽ nộp những gì

Bốn nhiệm vụ được chấm điểm, một checklist chung của nhóm, mọi thứ đều được ghi log theo cách AI-first.

| # | Hạng mục | Nội dung | Điểm |
|---|---|---|---:|
| 1 | **GUI Checklist** | Checklist của nhóm (> 40 item) áp dụng lên 3+ màn hình của bạn | **30 điểm** |
| 2 | **Usability Report** | Đánh giá heuristic trên các chức năng bạn phụ trách | **25 điểm** |
| 3 | **Cross-Platform** | 3 hệ điều hành × 5 trình duyệt × 3 loại thiết bị trên 3 màn hình của bạn | **25 điểm** |
| 4 | **Findings + Skills** | Nộp bug lên form; xây dựng Agent Skills tái sử dụng được | **20 điểm** |

---

## HỆ THỐNG ĐƯỢC KIỂM THỬ (SUT)

### EMS — Event Management System

Một ứng dụng web **đang chạy thật** của Khoa CNTT: tạo sự kiện, đăng ký, check-in, hỗ trợ, phân tích số liệu.

https://prod-dev.ems-fitus.cloud

**HỆ THỐNG LÀM GÌ**

- **› Phía Admin —** sự kiện, người dùng, danh mục, check-in, hỗ trợ, cài đặt, phân tích số liệu.
- **› Phía User —** duyệt & đăng ký sự kiện, nhận vé QR, đánh giá sự kiện, gửi yêu cầu hỗ trợ.
- **› Giao diện dày đặc —** form, kéo-thả sắp xếp, upload, rich-text, toast, màu trạng thái, đa ngôn ngữ EN/VI.

**TRUY CẬP**

**Web (SUT)**
```
prod-dev.ems-fitus.cloud
```

**Admin**
```
admin@gmail.com
Admin@123
```

**Phía User**
- Nhóm hỗ trợ: https://zalo.me/g/rupogxlykt3yxd3snodl
- Tự đăng ký tài khoản sinh viên/khách của riêng bạn

---

## CÔNG VIỆC ĐƯỢC CHIA NHƯ THẾ NÀO

### Một checklist chung, mỗi người một kịch bản

Cả nhóm dùng chung checklist; mỗi người sở hữu trọn vẹn một kịch bản từ đầu đến cuối.

**NHÓM · dùng chung**
- **›** Thiết kế MỘT checklist GUI (> 40 item).
- **›** Phủ đủ cả bốn khía cạnh giao diện IA-01…IA-04.
- **›** Nộp checklist + nguồn tham khảo + các AI prompt đã dùng.

**CÁ NHÂN · phần lõi của bạn**
- **›** Chọn MỘT kịch bản: A, B, C hoặc D.
- **›** Liệt kê ≥ 3 màn hình thuộc nhóm chức năng đó.
- **›** Chạy checklist, đánh giá usability và cross-platform trên các màn hình đó.

> **KHÔNG TRÙNG LẶP:** Trong một nhóm, không hai thành viên nào được sở hữu cùng một kịch bản **và** cùng một bộ màn hình.

---

## CHỌN MỘT — Bốn kịch bản

Mỗi kịch bản ứng với một nhóm chức năng của EMS. Cả nhóm nên cố gắng phủ hết bốn kịch bản.

| | Kịch bản | Mô tả |
|---|---|---|
| **A** | **Admin tạo & quản lý sự kiện** | Vòng đời sự kiện: tạo, validate, cấu hình, phát hành, duyệt, check-in |
| **B** | **User đăng ký tham dự sự kiện** | Khám phá & đăng ký công khai: duyệt danh sách, chi tiết sự kiện, đăng ký, vé QR |
| **C** | **Admin quản lý người dùng** | Quản trị người dùng: phân quyền, khóa/mở khóa, reset mật khẩu, export |
| **D** | **User gửi yêu cầu hỗ trợ, Admin xử lý** | Vòng đời support-request trải qua cả phía user lẫn phía admin |

---

## PHẠM VI — Liệt kê ít nhất 3 màn hình

Chọn ≥ 3 màn hình từ nhóm chức năng của kịch bản bạn chọn (ví dụ bên dưới).

**A · Events**
- Danh sách sự kiện + bộ lọc trạng thái
- Add/Edit Event (upload, rich-text, validate ngày giờ)
- Cấu hình Registration & Roles
- Duyệt Participants
- Tab Check-in

**B · Register**
- Trang chủ + carousel sự kiện nổi bật
- Trang chi tiết sự kiện
- Form đăng ký (vai trò, danh sách chờ)
- My Registrations + vé QR
- Đánh giá sao sau sự kiện

**C · Users**
- Danh sách người dùng + bộ lọc
- Phân quyền / sửa thông tin người dùng
- Block / Unblock + Reset password
- Export ra Excel

**D · Support**
- User: tạo yêu cầu (+ ảnh)
- User: danh sách yêu cầu của tôi + phản hồi
- Admin: danh sách yêu cầu (Pending/Resolved)
- Admin: chi tiết yêu cầu + trả lời

---

## NHIỆM VỤ 1 · 30 điểm — GUI Checklist

Đặt nền trên Nielsen / Norman / Shneiderman — rồi thực thi nó trên các màn hình của bạn.

**PHẦN A — DÙNG CHUNG (nhóm)**
- **›** > 40 item, trải đều IA-01…IA-04.
- **›** AI viết bản nháp; bạn review và bổ sung item còn thiếu.
- **›** Với mỗi item tự thêm, giải thích **VÌ SAO AI bỏ sót**.
- **›** Nộp checklist + nguồn tham khảo + AI prompts.

**PHẦN B — THỰC THI (cá nhân)**
- **›** Chạy checklist trên từng màn hình trong ≥ 3 màn hình của bạn.
- **›** Đánh dấu mọi item là Passed / Failed cho từng màn hình.
- **›** Cột Notes: lý do cho mỗi item Failed.
- **›** Chụp ảnh cho các item Failed; log lại mọi bug.

---

## NHIỆM VỤ 2 · 25 điểm — User Testing → Usability Report

Thiết kế một kịch bản, chạy nó với 5 người dùng thật, rồi phân tích kết quả.

**QUY TRÌNH 5 NGƯỜI DÙNG**
- **› Thiết kế —** một task scenario hướng mục tiêu trên các màn hình của bạn.
- **› Tuyển 5 người —** người dùng thật ngoài lớp học (thông tin liên hệ được che bớt).
- **› Chạy phiên test —** có người điều phối, yêu cầu nghĩ thành tiếng (think-aloud), quan sát trung lập.
- **› Thu thập —** tỉ lệ thành công, thời gian, lỗi + SUS / UEQ-S + câu hỏi thăm dò.
- **› Phân tích —** xếp hạng theo mức nghiêm trọng → danh sách khuyến nghị có ưu tiên.

**CẦN THU THẬP**
- **›** Tỉ lệ hoàn thành tác vụ
- **›** Thời gian làm tác vụ
- **›** Số lỗi / số lần do dự
- **›** Điểm SUS hoặc UEQ-S
- **›** Câu hỏi mở

---

## NHIỆM VỤ 3 · 25 điểm — Cross-Browser / Cross-Platform

Xây ma trận tương thích cho **từng màn hình trong 3 màn hình** của bạn.

| 3 Hệ điều hành | 5 Trình duyệt | 3 Loại thiết bị |
|---|---|---|
| Windows · macOS · Android / iOS | Chrome · Firefox · Safari · Edge · Opera | Desktop · Tablet · Phone |

**ĐỘ PHỦ:** Không cần đủ cả 45 tổ hợp — nhưng phải chạm **mọi OS, mọi trình duyệt và mọi loại thiết bị ít nhất một lần, cho từng màn hình**.

**CÔNG CỤ:** Trial BrowserStack / LambdaTest · overlay `MSSV@....edu.vn` lên **mọi** ảnh chụp, đặt cạnh URL của EMS.

---

## BÁO CÁO MỌI THỨ HAI LẦN — Bug & phát hiện usability

Mọi lỗi và mọi đề xuất đều phải vào form **VÀ** vào một file log hợp nhất.

**1 · GOOGLE FORM**
Nộp từng finding tại:
```
forms.gle/CJQFQCAXcsDbXDMM9
```
Dùng email theo MSSV của bạn: `MSSV@....edu.vn`

**2 · LOG HỢP NHẤT**
- **›** Một file duy nhất tổng hợp toàn bộ finding của bạn.
- **›** Các cột: ID · Screen · Type · Severity · Fix · Screenshot · Timestamp.
- **›** Phải **khớp** với những gì bạn đã nộp lên form (TA sẽ đối chiếu chéo).

---

## CÁCH LÀM VIỆC — Các luật AI-first

Dùng AI như một trợ lý có kỷ luật — và chứng minh điều đó.

- **› Dẫn dắt, đừng đổ việc —** dẫn AI đi từng bước qua kỹ thuật, không phải một prompt chung chung duy nhất.
- **› Con người review —** bạn chịu trách nhiệm về tính đúng đắn; không bao giờ nộp output thô của AI.
- **› AI Audit Report —** log mọi lần tương tác AI: công cụ, thời gian, prompt, output (phụ lục bắt buộc).
- **› AI Critique —** 200–300 từ về chỗ AI sai, thiên lệch hoặc thiếu sót.
- **› Chống gian lận —** ảnh EMS thật, ảnh cross-platform thật, người tham gia thật.
- **› Git log —** mỗi bước một commit: thiết kế, thực thi, log bug, đánh giá.

---

## CHẤM ĐIỂM — 100 điểm chia cho năm hạng mục

| # | Hạng mục | Phạm vi | Điểm |
|---|---|---|---:|
| **1a** | Checklist chung (> 40 item) + nguồn + AI prompts | nhóm | **15** |
| **1b** | Chạy checklist trên ≥ 3 màn hình + bug report | cá nhân | **15** |
| **2** | Usability Report (heuristic + severity + đề xuất sửa) | cá nhân | **25** |
| **3** | Ma trận cross-browser / cross-platform | cá nhân | **25** |
| **4** | Nộp finding (form) + log hợp nhất | cá nhân | **10** |
| **5** | Agent Skills + video demo | cá nhân | **10** |
| | **Tổng** | | **100** |

---

## NỘP BÀI — Nộp những gì

File ZIP cá nhân + các sản phẩm chung của nhóm, nộp trên Moodle.

**ZIP CỦA BẠN CHỨA**
- **›** Báo cáo chính (Markdown + PDF).
- **›** Bug & Usability Findings Log.
- **›** Ảnh cross-platform (có email của bạn).
- **›** AI Audit Report + AI Critique.
- **›** Git commit log + Agent Skills + README.

**Tên file**
```
<MSSV>_HW03_AI_GUIUsability_EMS_<grade>.zip
```

**GHI NHỚ**
- Không nộp trễ.
- Thiếu một tài liệu bắt buộc → 0 điểm.
- Chia sẻ prompt giữa các sinh viên → 0 điểm.
- Vấn đáp: chọn ngẫu nhiên 30%.

---

## BẮT ĐẦU — Năm bước đầu tiên của bạn

1. Lập nhóm & chọn ai làm A, B, C, D.
2. Mở SUT và tự đăng ký tài khoản user của riêng bạn.
3. Cùng nhau soạn checklist > 40 item (AI + review).
4. Liệt kê ≥ 3 màn hình của bạn và chạy checklist.
5. Đánh giá usability, chạy cross-platform, log mọi finding.

**Thắc mắc?** lqvu@fit.hcmus.edu.vn · và đội ngũ TA (xem trong đề chi tiết).
