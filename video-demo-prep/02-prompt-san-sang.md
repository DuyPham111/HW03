# Prompt sẵn sàng copy-paste — Demo Video `hw03-gui-checklist`

> Dùng đúng theo thứ tự trong `01-kich-ban-quay-video.md`. Copy nguyên văn, đừng gõ lại tay lúc quay. Lấy nguyên từ [`../23127183_HW03_AI_GUIUsability_EMS_100/skills/hw03-gui-checklist/SKILL.md`](../23127183_HW03_AI_GUIUsability_EMS_100/skills/hw03-gui-checklist/SKILL.md), không đổi nội dung so với skill gốc.

---

## Prompt A2 — Sinh item checklist cho IA-04 (dùng ở mốc 0:40)

```
Sinh các item checklist cho riêng IA-04 (Feedback/State).
Format bảng: | ID | Item | Cách kiểm | Nguồn heuristic |
- ID dạng IA04-01, IA04-02...
- Mỗi item viết ở dạng khẳng định, trả lời được Passed/Failed, KHÔNG mơ hồ
- Cột "Cách kiểm": thao tác cụ thể để xác định kết quả (bấm gì, nhìn vào đâu, đo bằng gì)
- Cột "Nguồn": ghi mã heuristic cụ thể (N4, P3, S6...), không ghi chung chung
- Không sinh item trùng nghĩa với item đã có

Bối cảnh SUT: EMS (Event Management System) — web app quản lý sự kiện của một khoa
CNTT, có phía user (đăng ký sự kiện) và phía admin. Các widget IA-04 thật đã quan sát:
toast/banner thông báo, badge trạng thái nhiều màu (Upcoming/Ongoing/Ended/Pending
review/Waitlisted), dialog xác nhận huỷ đăng ký, progress bar duyệt đăng ký phía admin,
QR code check-in, khối đếm số liệu (Slot available, Registered).

Sinh tối thiểu 10 item cho IA-04.
```

**Sau khi có output — nói gì (gợi ý, chọn 1 item AI vừa sinh để minh hoạ):**
> "Item [đọc tên item] mình sẽ [loại vì trùng với G-XX đã có / viết lại vì không đủ cụ thể để kết luận Passed-Failed ngay]."

---

## Prompt A3 — Ép AI tự soi lỗ hổng (dùng ở mốc 2:10)

```
Đây là checklist hiện tại của tôi cho hệ thống EMS, gồm 4 khía cạnh IA-01 General UI,
IA-02 Forms, IA-03 Navigation, IA-04 Feedback/State, tổng 61 item.

1) Liệt kê những vùng giao diện mà checklist này CHƯA phủ.
2) Với mỗi vùng thiếu, nói rõ vì sao một checklist sinh tự động thường bỏ qua nó.
3) KHÔNG thêm item mới ở bước này — chỉ liệt kê lỗ hổng.
```

**Sau khi có output — nói gì:**
> "Đối chiếu với 23 item mình tự thêm sau khi khảo sát EMS thật, AI vẫn không nêu được [ví dụ: mã QR tách rời khỏi luồng đăng ký, hoặc ba bộ từ vựng trạng thái khác nhau] — vì đây là đặc thù chỉ lộ ra khi thao tác thật, AI không nhìn thấy màn hình."

---

## Prompt B3 — Nhờ AI phân tích cụm lỗi sau khi có dữ liệu Failed thật (dùng ở mốc 5:00)

```
Đây là 1 item checklist vừa chạy Failed thật trên EMS:

Item: G-09 — Giá trị rỗng hiển thị bằng cùng một ký hiệu thống nhất trên mọi màn hình
Kết quả: Failed ở màn B1 (Danh sách sự kiện)
Quan sát: Thẻ sự kiện "Workshop B — het cho" trên B1 hiện "Location: Updating" và
"Organizer: Updating". Mở đúng sự kiện đó ở B2 (chi tiết) và B4 (My Activities),
cùng trường Location lại hiện dấu "-".

1) Đây là bug đơn lẻ hay vấn đề thiết kế mang tính hệ thống? Giải thích.
2) Đề xuất mức severity 0-4 và căn cứ.
3) Đề xuất hướng sửa ngắn gọn.
Chỉ dùng dữ liệu tôi vừa mô tả, không suy diễn thêm chi tiết tôi không cung cấp.
```

**Sau khi có output — nói gì:**
> "AI đề xuất severity [đọc số AI đề xuất]. Mình tự chốt lại là **2** — vì lỗi này không chặn được việc đăng ký, chỉ gây hiểu lầm, không nghiêm trọng bằng mức AI có thể đã đẩy lên."
> *(Nếu AI đề xuất đúng 2, cứ nói "mình đồng ý với mức severity AI đề xuất, vì lý do... " — không cần cố tình bịa ra một chỗ bất đồng nếu thực tế AI trả lời đúng ngay từ đầu, miễn là bạn giải thích được TẠI SAO đồng ý.)*

---

## Ghi chú khi quay

- Không cần đúng y nguyên câu chữ AI trả lời trong output mẫu ở đây — mỗi lần chạy AI ra kết quả hơi khác, cứ dùng đúng output thật hiện lên lúc quay để nói cho tự nhiên.
- Nếu AI trả lời khác với những gì kịch bản dự đoán (ví dụ không đề cập QR/từ vựng trạng thái ở Prompt A3), vẫn ổn — chọn bất kỳ 2 vùng AI liệt kê để đối chiếu với danh sách 23 item RV thật của bạn, miễn là bạn chỉ ra được ít nhất 1 vùng AI **không** nêu ra mà bạn đã tự phát hiện.
