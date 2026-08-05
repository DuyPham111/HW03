# Bug & Usability Findings Log — HW03

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183) · **Kịch bản:** B — User đăng ký tham dự sự kiện
**Email dùng nộp form:** pvnduy23@clc.fitus.edu.vn
**Google Form:** https://forms.gle/CJQFQCAXcsDbXDMM9

> **Luật của đề (§7):** mọi defect và mọi đề xuất cải tiến usability phải được báo cáo **HAI LẦN** — (1) submit từng cái lên Google Form, (2) hợp nhất vào file này.
> **File này và các lần nộp form phải nhất quán — TA đối chiếu số lượng.**

---

## Quy ước ID

Dạng `<NGUỒN>-<MÀN HÌNH>-<SỐ>` — nhìn ID là biết ngay lỗi tìm ra ở đâu và bằng cách nào.

| Nguồn | Prefix | Task | Ví dụ |
|---|---|---|---|
| Chạy checklist GUI | `CL-` | 1B | `CL-B3-01` |
| 5 phiên user testing | `US-` | 2 | `US-B2-01` |
| Cross-browser / cross-platform | `CP-` | 3 | `CP-B4-01` |
| Khảo sát EMS ban đầu | `SV-` | phụ trợ | `SV-B1-01` |

## Thang Severity

| Mức | Tên | Nghĩa |
|:--:|---|---|
| 4 | Catastrophe | Chặn hoàn toàn tác vụ / mất dữ liệu / lộ thông tin — bắt buộc sửa trước khi phát hành |
| 3 | Major | Cản trở nghiêm trọng, người dùng phải tự tìm cách lách — ưu tiên cao |
| 2 | Minor | Gây khó chịu, vẫn hoàn thành được tác vụ — ưu tiên thấp |
| 1 | Cosmetic | Chỉ về mặt thẩm mỹ — sửa nếu dư thời gian |
| 0 | Not a problem | Ghi nhận nhưng kết luận không phải vấn đề usability |

---

## Bảng hợp nhất — 9 cột bắt buộc

> Mỗi finding **một dòng duy nhất**, không tách block riêng để tránh lệch số liệu.
> Xuống dòng trong ô dùng `<br>`. Ảnh dùng link `[Xem ảnh](evidence/task1b/…)`.

| ID | Scenario / Screen | Type | Description | Steps / Heuristic | Severity | Suggested fix | Screenshot ref | Form-submission timestamp |
|---|---|---|---|---|:--:|---|---|---|
| `CL-B2-01` | Screen B2 — Trang chi tiết sự kiện | Bug | _(mô tả lỗi, 1–2 câu, nêu hiện tượng quan sát được)_ | 1. …<br>2. …<br>3. …<br>**Heuristic:** N? | | _(thay đổi cụ thể, không phải mục tiêu chung chung)_ | [Xem ảnh](evidence/task1b/CL-B2-01.png) | |
| `CL-B3-01` | Screen B3 — Form đăng ký | Usability | | | | | | |
| `US-B2-01` | Screen B2 | | | | | | | |
| `CP-B4-01` | Screen B4 | | | | | | | |
| `SV-B1-01` | Screen B1 | | | | | | | |

**Cột bắt buộc theo đề:** *ID · Scenario/Screen · Type (Bug \| Usability) · Description · Steps/Heuristic · Severity · Suggested fix · Screenshot ref · Form-submission timestamp.*
**Timestamp:** thời điểm bấm Submit trên Google Form, định dạng `YYYY-MM-DD HH:MM` — để TA đối chiếu được với bản ghi của họ.

---

## Ảnh nhúng cho các finding nặng

> Chỉ nhúng ảnh cho finding **severity ≥ 3** hoặc finding cần nhìn ảnh mới hiểu. Còn lại đã có link trong bảng, không nhúng để file không phình.

### `CL-B?-0?` — _(tên ngắn)_

![CL-B?-0?](evidence/task1b/CL-B2-01.png)

_(Ghi 1 câu chỉ ra chỗ cần nhìn trong ảnh.)_

---

## Thống kê

### Theo nguồn và loại

| Nguồn | Bug | Usability | Tổng | Đã submit form |
|---|:--:|:--:|:--:|:--:|
| `CL-` Checklist (Task 1B) | | | | |
| `US-` User testing (Task 2) | | | | |
| `CP-` Cross-platform (Task 3) | | | | |
| `SV-` Khảo sát EMS | | | | |
| **Tổng** | | | | |

### Theo severity

| Severity | 4 | 3 | 2 | 1 | 0 | Tổng |
|---|:--:|:--:|:--:|:--:|:--:|:--:|
| Số finding | | | | | | |

### Theo màn hình

| Màn hình | Số finding | Severity cao nhất |
|---|:--:|:--:|
| B2 Trang chi tiết sự kiện | | |
| B3 Form đăng ký | | |
| B4 My Registrations + vé QR | | |
| Khác (B1…) | | |

---

## Đối chiếu cuối cùng trước khi nộp

```bash
# đếm số finding trong bảng hợp nhất
grep -cE "^\| \`(CL|US|CP|SV)-" 04-findings-log.md
# đối chiếu ảnh có thật
ls evidence/task1b evidence/task3
```

- [ ] Số dòng trong bảng hợp nhất = số lần submit Google Form
- [ ] Mọi finding có `Screenshot ref` trỏ tới file **có thật**
- [ ] Mọi finding có `Form-submission timestamp`
- [ ] Đã dùng **đúng email MSSV** cho toàn bộ lần submit (không lẫn email cá nhân)
- [ ] Không có ID trùng hoặc nhảy cóc trong cùng một nhóm prefix
- [ ] Số liệu ở 3 bảng thống kê khớp với `README.md` mục 4.4 và `00-main-report.md` mục 5
