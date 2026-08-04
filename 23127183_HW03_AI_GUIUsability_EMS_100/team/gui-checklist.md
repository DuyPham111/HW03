# Task 1A — GUI Checklist dùng chung (sản phẩm nhóm)

**SUT:** EMS — https://prod-dev.ems-fitus.cloud
**Phạm vi phủ:** IA-01 chuẩn UI chung · IA-02 forms · IA-03 navigation · IA-04 feedback/state
**Tổng số mục:** _(TODO)_ *(yêu cầu tối thiểu: > 40)*
**Phiên bản:** v1.0 · **Ngày chốt:** _(TODO)_

**Đóng góp:** _(TODO — ghi trung thực ai dựng phần nào. Nếu tự dựng một mình: "Bản v1 (toàn bộ 4 khía cạnh) do Phạm Vũ Ngọc Duy (23127183) dựng ngày __, dựa trên khảo sát trực tiếp EMS ngày __. Đã gửi cả nhóm rà soát ngày __; [kết quả rà soát]")_

> Checklist này **giống hệt nhau giữa các thành viên trong nhóm** — đề §18 nói rõ đây là trường hợp được phép trùng. Mọi thứ khác (chọn màn hình, thực thi, usability, cross-platform, findings) phải riêng của từng người.
> Nguồn tham khảo: [`references.md`](references.md) · Prompt và lý do AI bỏ sót: [`ai-prompts.md`](ai-prompts.md)
> Cách làm chi tiết từng bước: `docs/TASK1A_LAM_MOT_MINH.md`

---

## Phân bổ

| IA | Prefix | Nội dung | Mục tiêu | Thực tế | Do AI | Người bổ sung |
|---|:--:|---|:--:|:--:|:--:|:--:|
| IA-01 | `G-` | Chuẩn UI chung — layout, alignment, typography, màu, nhất quán, i18n EN/VI, empty/loading | ≥ 12 | | | |
| IA-02 | `F-` | Forms — nhãn, validation, vị trí lỗi, trường bắt buộc, upload, rich-text | ≥ 12 | | | |
| IA-03 | `N-` | Navigation — menu, breadcrumb, tab, sidebar, kéo-thả, back/return, deep link | ≥ 8 | | | |
| IA-04 | `S-` | Feedback / State — toast, badge, dialog xác nhận, progress bar, màu trạng thái, real-time | ≥ 10 | | | |
| | | **Tổng** | **> 40** | | | |

## Cách dùng khi chạy (Task 1B)

Mỗi mục đánh **một** trong ba giá trị, **theo từng màn hình**:

| Giá trị | Nghĩa | Bắt buộc kèm |
|---|---|---|
| **Passed** | Đã kiểm, đạt | — |
| **Failed** | Đã kiểm, không đạt | **Notes (lý do) + ảnh chụp** |
| **N/A** | Không áp dụng cho màn hình này | Ghi ngắn lý do |
| *(trống)* | Chưa kiểm — **không được để trống khi nộp** | — |

> Checklist phủ cả 4 IA nên **N/A là bình thường và được dự kiến**: phía user của EMS không có upload ảnh, rich-text, kéo-thả reorder → các mục về những widget đó sẽ N/A.
> Tỉ lệ pass tính trên `Passed / (Passed + Failed)`, **không tính N/A vào mẫu số**.

**Ký hiệu cột Nguồn:** `N1`–`N10` Nielsen · `P1`–`P6` Norman · `S1`–`S8` Shneiderman · `SL` slide môn học · `W` WCAG 2.2 · `E` tài liệu E2E EMS
**Ký hiệu cột Nguồn gốc:** `AI` = AI sinh ở lượt đầu · `RV` = người bổ sung khi review *(bắt buộc có lý do ở [`ai-prompts.md`](ai-prompts.md) mục 3)*

---

## 1. IA-01 — Chuẩn UI chung (`G-`)

| ID | Mục kiểm tra | Nguồn | Nguồn gốc |
|---|---|---|---|
| G-01 | _(VÍ DỤ — thay bằng mục thật)_ Chuyển EN/VI dịch **toàn bộ** text hiển thị, kể cả toast, tooltip, placeholder — không còn chuỗi lẫn ngôn ngữ trên cùng màn hình | N2, S2 | RV |
| G-02 | | | |
| … | | | |

## 2. IA-02 — Forms (`F-`)

| ID | Mục kiểm tra | Nguồn | Nguồn gốc |
|---|---|---|---|
| F-01 | _(VÍ DỤ)_ Thông báo lỗi validation hiện **ngay cạnh trường bị lỗi** và **phía trên nút submit**, không chỉ ở một toast tự biến mất | N9 | AI |
| F-02 | | | |
| … | | | |

## 3. IA-03 — Navigation (`N-`)

| ID | Mục kiểm tra | Nguồn | Nguồn gốc |
|---|---|---|---|
| N-01 | _(VÍ DỤ)_ Mở deep link tới một sự kiện khi chưa đăng nhập, sau khi đăng nhập vẫn quay lại đúng trang đó chứ không bị đá về trang chủ | N3, S7 | RV |
| N-02 | | | |
| … | | | |

## 4. IA-04 — Feedback / State (`S-`)

| ID | Mục kiểm tra | Nguồn | Nguồn gốc |
|---|---|---|---|
| S-01 | _(VÍ DỤ)_ Mọi hành động không thể hoàn tác (huỷ đăng ký, xoá) đều có hộp thoại xác nhận nêu rõ hậu quả | N5, S6 | AI |
| S-02 | | | |
| … | | | |

---

## 5. Vùng AI thường bỏ sót — rà trước khi chốt

| # | Vùng | Đã có mục? | ID |
|---|---|:--:|---|
| 1 | Accessibility: tương phản ≥ 4.5:1, alt text, focus nhìn thấy được | ⬜ | |
| 2 | Điều hướng bàn phím: Tab đúng thứ tự, Enter/Esc, không bẫy focus trong modal | ⬜ | |
| 3 | Dark mode | ⬜ | |
| 4 | Bố cục RTL | ⬜ | |
| 5 | **i18n EN/VI** — kể cả toast, tooltip, placeholder, nội dung Excel export | ⬜ | |
| 6 | **Text tiếng Việt dài hơn EN** làm vỡ nút / cắt chữ | ⬜ | |
| 7 | **Ngôn ngữ đã chọn có được lưu lại** sau khi tải lại trang | ⬜ | |
| 8 | Empty state / loading state / skeleton không gây nhảy layout | ⬜ | |
| 9 | Zoom trình duyệt 200% vẫn đọc được, không vỡ layout | ⬜ | |
| 10 | **Không lộ mã trạng thái nội bộ ra giao diện** (vd hiện thẳng `OUTSIDE_CHECKIN_WINDOW`) | ⬜ | |
| 11 | Bảo toàn dữ liệu form khi validate fail — không xoá trắng cái đã nhập | ⬜ | |
| 12 | Nhất quán màu trạng thái giữa các màn hình | ⬜ | |
| 13 | Độ trễ mạng thật (SUT là môi trường dev từ xa) — có phản hồi trong lúc chờ không | ⬜ | |
| 14 | Responsive dưới 768px | ⬜ | |

## 6. Kiểm đếm trước khi chốt

```bash
for p in G F N S; do echo -n "$p: "; grep -c "^| $p-" team/gui-checklist.md; done
```

- [ ] Tổng > 40 · [ ] mỗi IA đạt mục tiêu tối thiểu · [ ] mọi mục có mã nguồn · [ ] mọi mục có `AI` hoặc `RV`
- [ ] Số mục `RV` khớp số dòng giải thích ở [`ai-prompts.md`](ai-prompts.md) mục 3
