# Checklist Execution — Task 1B

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183) · **Kịch bản:** B — User đăng ký tham dự sự kiện
**Checklist nguồn:** `team/gui-checklist.md` v1.0 — _(TODO)_ item
**Ngày chạy:** _(TODO)_ · **Môi trường chạy:** _(TODO: OS + browser + độ phân giải)_

> **Luật của đề:** mọi item phải được đánh **Passed** hoặc **Failed** cho **từng màn hình**. Cột **Notes** bắt buộc điền **lý do fail** với mỗi item Failed. Ảnh chụp **chỉ cần cho item Failed**.
> Ký hiệu: ✅ Passed · ❌ Failed · ➖ N/A (màn hình không có widget đó — **phải ghi rõ lý do ở Notes**, không được để trống)

---

## Bảng tổng hợp

| Màn hình | Tổng item | ✅ Passed | ❌ Failed | ➖ N/A | Tỉ lệ pass |
|---|:--:|:--:|:--:|:--:|:--:|
| S1 — B2 Trang chi tiết sự kiện | | | | | |
| S2 — B3 Form đăng ký | | | | | |
| S3 — B4 My Registrations + vé QR | | | | | |
| **Tổng** | | | | | |

---

## Bảng chạy hợp nhất (khuyến nghị dùng dạng này — dễ so sánh giữa các màn hình)

| ID item | Item (rút gọn) | IA | S1 | S2 | S3 | Notes (lý do Fail — ghi rõ màn nào) | Bug-ID | Ảnh |
|---|---|:--:|:--:|:--:|:--:|---|---|---|
| G-01 | | IA-01 | | | | | | |
| G-02 | | IA-01 | | | | | | |
| G-03 | | IA-01 | | | | | | |
| … | | | | | | | | |
| F-01 | | IA-02 | | | | | | |
| … | | | | | | | | |
| N-01 | | IA-03 | | | | | | |
| … | | | | | | | | |
| S-01 | | IA-04 | | | | | | |
| … | | | | | | | | |

> **Mẹo điền:** copy toàn bộ cột `ID` + `Item` từ `team/gui-checklist.md` sang đây trước khi chạy, để không bị sót item và giữ đúng thứ tự ID giữa hai file.

---

## Chi tiết các item Failed

Mỗi item Failed → 1 block. Đây là nguồn trực tiếp để tạo bug entry trong `04-findings-log.md`.

### [F-01] `G-XX / F-XX / N-XX / S-XX` — _(tên item)_ — Màn hình: _(TODO)_

- **Kết quả:** ❌ Failed
- **Kỳ vọng (theo item checklist):** _(TODO)_
- **Thực tế quan sát:** _(TODO)_
- **Các bước tái hiện:**
  1. _(TODO)_
  2. _(TODO)_
- **Heuristic bị vi phạm:** _(TODO — N?/P?/S?)_
- **Severity:** _(TODO: 0–4)_
- **Bug-ID trong log:** `CL-B2-01`
- **Ảnh:** `evidence/task1b/CL-B2-01.png` _(chụp lúc _(TODO giờ)_)_

![CL-B2-01](evidence/task1b/CL-B2-01.png)

### [F-02] …

---

## Ghi chú độ phủ

- [ ] Mọi item trong checklist chung đều đã được đánh giá trên **cả 3 màn hình** (không còn ô trống)
- [ ] Mọi ô ❌ đều có Notes + Bug-ID + ảnh
- [ ] Mọi ô ➖ N/A đều có lý do ở Notes
- [ ] Số bug tạo ra ở đây khớp với số dòng prefix `CL-` trong `04-findings-log.md`
