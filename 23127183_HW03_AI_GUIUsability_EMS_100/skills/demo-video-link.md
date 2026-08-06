# Demo video — Agent Skills (HW03)

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183)

> Đề §8: nộp Agent Skills **kèm video demo (link YouTube)** cho thấy **từ đầu đến cuối** cách bạn dùng skill trên **một màn hình hoặc luồng hoàn chỉnh**. Không có video → mất phần lớn 10 điểm Task 5.

| Video | Skill demo | Nội dung | Link |
|---|---|---|---|
| Video 1 | `hw03-gui-checklist` | Demo Phần A (sinh item IA-04, ép AI tự soi lỗ hổng) + Phần B (chạy item `G-09` thật trên B1/B2, dựng bug entry `CL-B1-01`, commit) — theo kịch bản `../../video-demo-prep/01-kich-ban-quay-video.md` | https://www.youtube.com/watch?v=hH9GwM8wB8M |
| Video 2 | `hw03-usability-5users` | _(TODO, nếu có)_ | |
| Video 3 | `hw03-crossplatform-matrix` | _(TODO, nếu có)_ | |

---

## Kịch bản quay Video 1 — `hw03-gui-checklist` (~6–10 phút)

1. **(0:00–0:30)** Mở `skills/hw03-gui-checklist/SKILL.md`, nói skill này giải quyết việc gì và vì sao chia thành Phần A / Phần B.
2. **(0:30–2:30)** Dán prompt **Bước A1** (nạp khung heuristic + mô tả widget thật của EMS) → cho xem AI hỏi ngược lại gì → bổ sung thông tin còn thiếu.
3. **(2:30–4:00)** Dán prompt **Bước A2** cho một IA cụ thể → cho xem output → **chỉ ra ít nhất 1 item mình phải sửa/loại** và giải thích vì sao (đây là phần thể hiện human review, người chấm quan tâm nhất).
4. **(4:00–6:00)** Chuyển sang Phần B: mở một màn hình EMS thật, chạy vài item của checklist trực tiếp trên màn hình, **bắt được một item Failed** → chụp ảnh ngay tại chỗ.
5. **(6:00–7:30)** Đưa Failed đó thành bug entry trong `04-findings-log.md` → submit Google Form → điền timestamp.
6. **(7:30–8:00)** `git commit` theo đúng quy ước, cho xem log.

## Kịch bản quay Video 2 — `hw03-usability-5users` (~5–8 phút, nếu quay)

1. Mở SKILL.md, giải thích 3 giai đoạn.
2. Dán prompt Bước 1.1 → cho xem 3 phương án task scenario → **chọn 1 và nói vì sao loại 2 cái kia**.
3. Cho xem phiếu SUS đã soạn → **tự tính tay 1 phiếu** để đối chiếu với kết quả AI tính (thể hiện kiểm chứng).
4. Dán một đoạn ghi chú thô của phiên thật → cho xem AI cấu trúc hoá thành bảng dòng thời gian → chỉ ra chỗ AI "làm mượt" lời participant và mình phải sửa lại theo verbatim.
5. Kết: finding xếp severity + 1 khuyến nghị cụ thể.

## Kịch bản quay Video 3 — `hw03-crossplatform-matrix` (~5–8 phút, nếu quay)

1. Mở SKILL.md, giải thích khác biệt "phủ theo chiều" vs "phủ theo tích".
2. Dán prompt Bước 1 → cho xem bộ tổ hợp tối thiểu AI đề xuất → **tự đếm lại bảng độ phủ trên màn hình** và chỉ ra nếu AI thiếu một giá trị.
3. Mở BrowserStack/LambdaTest, chạy 1 ô thật → cho thấy overlay email + URL + tên OS/browser trong khung hình.
4. Bắt được một lỗi hiển thị → phân loại (overflow/overlap/…) → kiểm chứng nó **không** xuất hiện ở môi trường khác để chứng minh đúng là lỗi tương thích.
5. Ghi vào report + commit.

---

## Lưu ý khi quay

- **Để chế độ Unlisted** trên YouTube nếu không muốn công khai, nhưng phải đảm bảo link mở được mà không cần đăng nhập.
- Trong video có màn hình EMS thật → tránh để lộ thông tin cá nhân của người dùng khác trên hệ thống (danh sách Users, số điện thoại, email).
- Nói tiếng Việt được, nhưng thuật ngữ kỹ thuật giữ nguyên tiếng Anh cho khớp báo cáo.
- Quay màn hình có hiện **email MSSV** ít nhất một lần để chứng minh danh tính.
