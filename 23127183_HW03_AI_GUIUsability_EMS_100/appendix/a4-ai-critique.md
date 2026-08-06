# AI Critique — HW03

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183)
**Số từ:** 284 *(đếm bằng `wc -w` trên đúng đoạn "Bản viết chính thức" — bạn đếm lại sau khi tự sửa văn phong, vì mọi chỉnh sửa đều đổi số từ)*

> **Yêu cầu của đề (§11):** một đoạn 200–300 từ phê bình AI. AI sai / thiên lệch / thiếu sót ở chỗ nào? Vì sao nó không bắt được vấn đề đó? Bạn học được **nguyên tắc** gì về việc cộng tác với AI?
> **Bắt buộc dùng ví dụ THẬT từ chính bài này** — lấy từ mục "AI Gap Analysis" trong `00-main-report.md` và các dòng Human Review Notes trong `appendix/a3-ai-audit-report.md`. Viết chung chung kiểu "AI đôi khi sai" sẽ bị trừ điểm.

---

Trong bài này AI hỗ trợ dựng checklist ban đầu, xử lý dữ liệu khi kiểm thử, và tính điểm Task 2 — mọi kết luận cuối cùng đều do tôi tự kiểm chứng trên hệ thống thật.

Sai lầm rõ nhất: AI kết luận B2 không có nút quay lại danh sách khi đã đăng nhập (`SV-B2-03`), khiến `N-02` bị đánh Failed. Thực tế ảnh `G-06-S2.png` đã chụp sẵn từ trước cho thấy nút `Back to events` tồn tại. AI đọc tĩnh theo ghi chú khảo sát cũ, không đối chiếu chéo với ảnh khác đã có sẵn cùng thư mục — thiếu thói quen kiểm lại bằng chứng đang có trước khi kết luận.

Vùng AI bỏ sót: QR tách rời khỏi luồng đăng ký (`N-10`) và ba bộ từ vựng trạng thái khác nhau (`S-15`) chỉ lộ ra sau khi tôi tự thao tác nhiều trạng thái thật — AI không có cách nào biết trước vì đây là lỗi cấu hình dữ liệu thực tế, không suy ra được từ mô tả đề.

AI cũng thiên lệch rõ: trong 38 item tự sinh ban đầu, chỉ 1 item chạm tới điều hướng bàn phím (`F-13`), không item nào về screen reader/ARIA — AI ưu tiên heuristic dễ mô tả bằng lời (nhất quán, phản hồi) hơn heuristic cần công cụ hỗ trợ mới kiểm chứng được.

Nguyên tắc rút ra: AI đáng tin khi tổng hợp heuristic có sẵn, nhưng mọi kết luận đụng tới trạng thái thật của một hệ thống cụ thể phải được xác nhận bằng thao tác trực tiếp, không suy diễn từ ảnh cũ hay pattern web app thông thường.

---


