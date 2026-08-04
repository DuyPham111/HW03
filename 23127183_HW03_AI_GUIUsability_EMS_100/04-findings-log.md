# Bug & Usability Findings Log — HW03

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183) · **Kịch bản:** B — User đăng ký tham dự sự kiện
**Email dùng nộp form:** pvnduy23@clc.fitus.edu.vn
**Google Form:** https://forms.gle/CJQFQCAXcsDbXDMM9

> **Luật của đề (§7):** mọi defect và mọi đề xuất cải tiến usability phải được báo cáo **HAI LẦN** — (1) submit từng cái lên Google Form, (2) hợp nhất vào file này.
> **File này và các lần nộp form phải nhất quán — TA đối chiếu số lượng.**

---

## Quy ước ID theo nguồn phát hiện

| Prefix | Nguồn | Task |
|---|---|---|
| `CL-` | Từ việc chạy checklist GUI trên các màn hình | 1B |
| `US-` | Từ 5 phiên user testing | 2 |
| `CP-` | Từ chạy cross-browser / cross-platform | 3 |
| `E2E-` | Từ lượt chạy E2E Admin (exploratory pass — đã hoàn thành trước khi làm HW03) | phụ trợ |

## Thang Severity

| Mức | Tên | Nghĩa |
|:--:|---|---|
| 4 | Catastrophe | Chặn hoàn toàn tác vụ / mất dữ liệu / lộ thông tin — bắt buộc sửa trước khi phát hành |
| 3 | Major | Cản trở nghiêm trọng, người dùng phải tự tìm cách lách — ưu tiên cao |
| 2 | Minor | Gây khó chịu, vẫn hoàn thành được tác vụ — ưu tiên thấp |
| 1 | Cosmetic | Chỉ về mặt thẩm mỹ — sửa nếu dư thời gian |
| 0 | Not a problem | Ghi nhận nhưng kết luận không phải vấn đề usability |

---

## Bảng hợp nhất

| ID | Scenario / Screen | Type | Description | Steps / Heuristic | Severity | Suggested fix | Screenshot ref | Form-submission timestamp |
|---|---|---|---|---|:--:|---|---|---|
| CL-001 | | Bug | | | | | | |
| CL-002 | | Usability | | | | | | |
| US-001 | | | | | | | | |
| CP-001 | | | | | | | | |
| E2E-001 | | | | | | | | |

> **Cột bắt buộc theo đề:** *ID · Scenario/Screen · Type (Bug \| Usability) · Description · Steps/Heuristic · Severity · Suggested fix · Screenshot ref · Form-submission timestamp.*
> **Timestamp** ghi theo thời điểm bấm Submit trên Google Form (định dạng `YYYY-MM-DD HH:MM`), để đối chiếu được với bản ghi của TA.

---

## Chi tiết từng finding

> Mỗi finding 1 block, có nhúng ảnh để hiện được khi xuất PDF.

### [CL-001] _(tên ngắn)_

| Mục | Nội dung |
|---|---|
| **Type** | Bug / Usability |
| **Scenario / Screen** | |
| **Item checklist / Heuristic** | |
| **Severity** | |
| **Môi trường** | _(OS + browser + ngày giờ quan sát)_ |
| **Steps to reproduce** | 1. …<br>2. …<br>3. … |
| **Expected** | |
| **Actual** | |
| **Suggested fix** | |
| **Đã submit form lúc** | |

![CL-001](evidence/task1b/CL-001.png)

### [CL-002] …

---

## Thống kê

### Theo nguồn và loại

| Nguồn | Bug | Usability | Tổng | Đã submit form |
|---|:--:|:--:|:--:|:--:|
| `CL-` Checklist | | | | |
| `US-` User testing | | | | |
| `CP-` Cross-platform | | | | |
| `E2E-` Exploratory | | | | |
| **Tổng** | | | | |

### Theo severity

| Severity | 4 | 3 | 2 | 1 | 0 | Tổng |
|---|:--:|:--:|:--:|:--:|:--:|:--:|
| Số finding | | | | | | |

### Theo màn hình

| Màn hình | Số finding | Severity cao nhất |
|---|:--:|:--:|
| S1 | | |
| S2 | | |
| S3 | | |

---

## Đối chiếu cuối cùng trước khi nộp

- [ ] Số dòng trong bảng hợp nhất = số lần submit Google Form
- [ ] Mọi finding đều có `Screenshot ref` trỏ tới file có thật
- [ ] Mọi finding đều có `Form-submission timestamp`
- [ ] Đã dùng **đúng email MSSV** cho toàn bộ lần submit (không lẫn email cá nhân)
- [ ] Không có ID bị trùng hoặc bị nhảy cóc
