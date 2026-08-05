# PHIẾU HƯỚNG DẪN DÀNH CHO NGƯỜI THAM GIA THỬ NGHIỆM

> Đây là bản gửi cho participant trước/đầu phiên. Lưu ở đây làm **bằng chứng quy trình tuyển và dẫn phiên** (đề §12 yêu cầu dữ liệu phiên thô).
> Kịch bản đầy đủ + tiêu chí chấm: [`../../02-usability-report.md`](../../02-usability-report.md) · Ghi chú phiên: [`../../appendix/a1-session-notes.md`](../../appendix/a1-session-notes.md)

> **Công cụ chạy phiên:** study Maze (`app.maze.co`) — Live website testing trên `https://prod-dev.ems-fitus.cloud`, kèm block nhiệm vụ + trạng thái kết quả + SUS 10 câu + 5 câu hỏi mở. Cách dựng chi tiết: `docs/QUY_TRINH_AI_VA_TOI.md` Phần 2. **Dùng SONG SONG với cuộc gọi có chia sẻ màn hình** (Zalo/Meet) — Maze không thay được người quan sát trực tiếp think-aloud.
> _(TODO: dán link Maze study ở đây sau khi publish)_
> Dự phòng nếu Maze trục trặc: [Vé tham gia kiểm thử EMS](https://claude.ai/code/artifact/aa535ccc-fb5d-4888-aa4b-c5ba924fe107) — trang tự dựng làm việc tương tự, không cần tài khoản.
> Nội dung markdown bên dưới vẫn giữ lại làm **bản dự phòng giấy** (đọc miệng qua điện thoại) nếu participant không mở được link, và làm bằng chứng quy trình cho đề §12.

---

**Xin chào bạn,**

Cảm ơn bạn đã dành khoảng **20–25 phút** tham gia buổi thử nghiệm khả năng sử dụng (usability testing) cho **EMS — hệ thống quản lý sự kiện của Khoa CNTT**. Đây là bài tập môn Kiểm thử phần mềm của mình.

## Ba điều cần biết trước khi bắt đầu

1. **Mình đang thử nghiệm TRANG WEB, không thử nghiệm bạn.** Nếu bạn không tìm thấy nút, bấm nhầm chỗ, hay thấy khó hiểu — đó là lỗi của giao diện, không phải của bạn. Đúng ra thì bạn càng gặp khó, dữ liệu của mình càng có giá trị.
2. **Xin bạn nói to những gì đang nghĩ** *(think aloud)*: bạn đang tìm gì, bạn nghĩ nút này sẽ làm gì, chỗ nào làm bạn phân vân. Nếu bạn im lặng lâu mình sẽ nhắc nhẹ.
3. **Mình sẽ không trả lời câu hỏi trong lúc bạn làm.** Không phải mình khó tính — mình cần xem hệ thống tự giải thích được đến đâu. Nếu bạn bí hẳn quá 2 phút thì mình sẽ gợi ý.

**Ghi hình:** mình xin phép ghi lại **màn hình và giọng nói** trong lúc bạn thao tác. Bản ghi chỉ dùng cho bài tập, không đăng công khai, và mình sẽ xoá sau khi chấm xong.
Bạn đồng ý ghi hình? ⬜ Có ⬜ Không *(không đồng ý cũng không sao — mình chỉ ghi chú tay)*

---

## Bối cảnh

Một người quen báo bạn có một buổi workshop học thuật ở Khoa CNTT mà bạn muốn tham dự (bạn không phải sinh viên trường này). Khoa dùng hệ thống EMS để nhận đăng ký, cho phép khách ngoài trường tham gia với vai trò **Guest**. **Đây là lần đầu bạn dùng hệ thống này.**

## Nhiệm vụ

> **Khoa sắp tổ chức một workshop mà bạn muốn tham dự. Hãy đăng ký tham gia, rồi cho mình xem xác nhận đăng ký của bạn.**

⚠️ *(Nguyên văn đang ghi "cho mình xem mã QR check-in" trong file gốc — đang xác minh lại xem hệ thống thật có hiển thị mã QR cho sinh viên không, xem `docs/KHAO_SAT_EMS.md` mục ⚠️5. Câu ở trên đã đổi sang bản an toàn "xem xác nhận đăng ký" cho tới khi xác nhận xong. Nếu xác nhận CÓ QR thì đổi lại nguyên câu cũ.)*

Xong việc thì bạn báo mình một tiếng. Cứ thao tác tự nhiên như bạn vẫn dùng web hằng ngày.

> ⚠️ **Lưu ý cho người dẫn phiên (không đưa cho participant đọc):** đề bài phải nêu **mục tiêu**, tuyệt đối **không** liệt kê các bước bấm. Nếu phiếu này ghi kiểu *"bước 1 đăng nhập, bước 2 tìm kiếm, bước 3 chọn vai trò…"* thì participant chỉ làm theo chỉ dẫn, và buổi test **không còn đo được usability** — mất phần lớn điểm Task 2.

**Điều kiện hệ thống — QUAN TRỌNG:** bạn cần một tài khoản EMS. Ở trang đăng nhập, **bấm link `Create guest account`** (KHÔNG bấm nút `STUDENT` — nút đó yêu cầu tài khoản Microsoft/Office 365 do HCMUS cấp mà bạn không có). Việc tạo tài khoản **không tính giờ**, nhưng nếu bạn thấy vướng gì ở bước này thì cứ nói, mình vẫn ghi lại — xem lý do ở `docs/KHAO_SAT_EMS.md` mục ⚠️4.

---

## Sau khi xong

1. **Phiếu SUS — 10 câu, ~2 phút.** Bạn cho điểm từ 1 (rất không đồng ý) đến 5 (rất đồng ý). Không có đáp án đúng/sai, cứ theo cảm nhận thật.
2. **Vài câu hỏi nhanh** về độ rõ ràng, khả năng sửa sai, tốc độ và mức độ tin tưởng.

---

## Thông tin liên hệ (mình ghi, bạn không cần điền)

| Trường | Giá trị |
|---|---|
| Mã participant | P_ |
| Tên | |
| Liên hệ *(che 4 số giữa khi đưa vào báo cáo)* | |
| Ngày & giờ phiên | |
| Thiết bị / trình duyệt | |
| Đồng ý ghi hình | ⬜ |

**Cảm ơn bạn rất nhiều!**
