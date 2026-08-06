# HW03 — GUI & Usability Testing on EMS

**Sinh viên:** Phạm Vũ Ngọc Duy — **MSSV:** 23127183
**Nhóm:** 10 — thành viên & phân chia kịch bản xem mục 2
**SUT:** EMS — Event Management System, Khoa CNTT — https://prod-dev.ems-fitus.cloud
**Kịch bản đã chọn:** **B — User đăng ký tham dự sự kiện** (nửa "registration core" của Pool B)
**Kỹ thuật:** GUI Checklist (Nielsen · Norman · Shneiderman) + Usability Testing 5 người thật + Cross-Browser/Cross-Platform Testing
**Google Form nộp finding:** https://forms.gle/CJQFQCAXcsDbXDMM9
**Email dùng khi nộp form & overlay ảnh:** 23127183@student.hcmus.edu.vn

---

## 1. Kịch bản & màn hình đã chọn

**Kịch bản:** **B — User đăng ký tham dự sự kiện.** Nhóm chức năng: khám phá công khai và đăng ký tham dự (Pool B).

| # | Mã | Tên màn hình | Lý do chọn (bắt buộc giải trình) | IA chính được phủ |
|---|---|---|---|---|
| 1 | B1 | Danh sách sự kiện — thẻ sự kiện, ô tìm kiếm, bộ lọc, phân trang | Cửa vào của cả luồng: người dùng phải **tìm được** sự kiện trước khi đăng ký. Là màn hình duy nhất trong bộ có bộ lọc + trạng thái rỗng + danh sách nhiều bản ghi, nên gánh phần lớn IA-03 | IA-03 tìm kiếm, lọc, phân trang, URL state · IA-01 thẻ, ảnh, empty state |
| 2 | B2 | Trang chi tiết sự kiện — banner, lịch trình, **khối Registration roles**, nút Đăng ký / Cancel registration | Điểm ra quyết định **và** nơi thực hiện đăng ký. Chứa nhiều trạng thái khác nhau (còn chỗ / hết chỗ / đã đóng đăng ký / chưa đăng nhập / đã đăng ký) nên là màn hình giàu IA-02 và IA-04 nhất trong bộ | IA-02 chọn vai trò, validation, xác nhận · IA-04 badge trạng thái, hộp thoại huỷ · IA-01 bố cục |
| 3 | B4 | My Profile — khối My Activities | Đầu ra quan sát được của cả luồng, My Activities dùng làm tiêu chí "hoàn thành" cho Task 2 . Có badge trạng thái nhiều màu, empty state, phân trang riêng | IA-04 badge trạng thái · IA-01 empty state · IA-03 phân trang, Filters, Export |


**Giải trình chung:** ba màn hình tạo thành một mạch liền **tìm sự kiện → đăng ký → xem lại đăng ký**, đúng tinh thần tác vụ mà đề nêu làm ví dụ mẫu cho kịch bản B. Nhờ vậy bộ này: (1) gói được thành **một tác vụ hướng mục tiêu duy nhất** cho Task 2; (2) phủ đủ cả bốn khía cạnh IA-01…IA-04 dù phía user không có upload/rich-text/drag-drop; (3) chạy được bằng **tài khoản guest**, không cần tài khoản HCMUS và không phụ thuộc tài khoản admin dùng chung của lớp — điều kiện then chốt để chạy 5 phiên user testing với người ngoài lớp.

**Nhóm item sẽ đánh N/A và lý do:** upload ảnh, trình soạn rich-text, kéo-thả reorder, bảng cấu hình quyền — các widget này chỉ tồn tại ở phía admin, không có trong Pool B. Mọi ô N/A đều ghi lý do trong `01-checklist-execution.md` theo yêu cầu của đề.

> Task 1B, Task 2 và Task 3 đều chạy trên **đúng bộ màn hình này**.

## 2. Nhóm & luật không trùng lặp

**Nhóm 10.** Có **5 người** trong khi đề chỉ có 4 kịch bản ⇒ theo §5 của đề, **một kịch bản được phép đôi**, nhưng hai người dùng chung kịch bản đó **bắt buộc chọn hai bộ màn hình không giao nhau**. Nhóm chốt **Phương án 1 — đôi ở A**: chia Pool A thành nửa *authoring* (A1–A3) và nửa *operation* (A3–A5).

| Thành viên | MSSV | Kịch bản | Bộ màn hình |
|---|---|---|---|
| Phạm Vũ Ngọc Duy | 23127183 | **B** (nửa *registration core*) | B1 Danh sách sự kiện · B2 Trang chi tiết sự kiện · B4 My Profile — QR Code + My Activities |
| Huỳnh Lê Khương Duy | 23127176 | **D** |  |
| Phạm Lê Thái Bảo | 23127159 | **A** ||
| Phạm Chí Bảo Ninh | 23127446 | **C** | |
| Chu Quốc Anh Minh | 23127531 | **A** | |



## 3. Nội dung bài nộp

> **Bắt đầu đọc từ [`00-main-report.md`](00-main-report.md).** Mỗi nội dung chỉ nằm ở **đúng một file**; các file khác dẫn chiếu chứ không chép lại.

```
├── README.md ........................ test summary + tự đánh giá  ← file này
├── 00-main-report.md ................ kịch bản · 3 màn hình & lý do · tóm tắt cả 3 task
├── 01-checklist-execution.md ........ Task 1B — bảng chạy checklist + bug report
├── 02-usability-report.md ........... Task 2 — 5 phiên · chỉ số · findings · khuyến nghị
├── 03-compatibility-matrix.md ....... Task 3 — ma trận cross-browser / cross-platform
├── 04-findings-log.md ............... Task 4 — log hợp nhất, khớp Google Form
│
├── team/ ............................ sản phẩm cấp nhóm (Task 1A)
│   ├── gui-checklist.md ............. checklist > 40 item, phủ IA-01…IA-04
│   ├── references.md ................ nguồn tham khảo + đối chiếu độ phủ heuristic
│   └── ai-prompts.md ................ prompt AI + lý do AI bỏ sót 23 mục
│
├── skills/ .......................... Task 5 — 3 Agent Skill + link video demo
│
├── appendix/ ........................ phụ lục BẮT BUỘC (thiếu = 0 điểm)
│   ├── a1-session-notes.md .......... dòng thời gian & lời thoại 5 phiên
│   ├── a2-sus-scoring.md ............ 10 câu × 5 người, quy đổi, phân tích
│   ├── a3-ai-audit-report.md ........ AI Audit Report
│   ├── a4-ai-critique.md ............ AI Critique 200–300 từ
│   └── git-log.txt .................. lịch sử commit
│
└── evidence/
    ├── task1b/ ...................... ảnh — chỉ cho item Failed
    ├── task2/ ....................... transcript 5 phiên + link bản ghi màn hình
    ├── task3/ ....................... ảnh mọi ô ma trận, có overlay MSSV
    └── survey/ ...................... ảnh khảo sát EMS ban đầu
```

| Hạng mục chấm | File chính |
|---|---|
| 1a (15đ) | `team/gui-checklist.md` · `team/references.md` · `team/ai-prompts.md` |
| 1b (15đ) | `01-checklist-execution.md` + `evidence/task1b/` |
| 2 (25đ) | `02-usability-report.md` + `appendix/a1` · `a2` + `evidence/task2/` |
| 3 (25đ) | `03-compatibility-matrix.md` + `evidence/task3/` |
| 4 (10đ) | `04-findings-log.md` |
| 5 (10đ) | `skills/` |
| Bắt buộc | `README.md` · `00-main-report.md` · `appendix/a3` · `a4` · `git-log.txt` |

> Tài liệu nội bộ (kế hoạch, hướng dẫn, bản dịch đề) nằm ở `docs/` **ngoài** thư mục này — không đi vào file zip nộp.

## 4. Test Summary Report

### 4.1 Checklist (Task 1)

| Chỉ số | Số lượng |
|---|:--:|
| Số item checklist nhóm thiết kế | **61** *(> 40 ✅)* |
| — IA-01 General UI standards (`G-`) | 16 |
| — IA-02 Forms (`F-`) | 16 |
| — IA-03 Navigation (`N-`) | 12 |
| — IA-04 Feedback / state (`S-`) | 17 |
| Số item do AI sinh | 38 |
| Số item do người bổ sung (có giải thích vì sao AI sót) | **23** |
| Số item đã chạy (= 61 × 3 màn) | **183** / 183 ✅ |
| Passed | **69** |
| Failed | **38** |

| Màn hình | Items chạy | Passed | Failed | N/A | Bug tạo ra (CL-) |
|---|:--:|:--:|:--:|:--:|:--:|
| B1 Danh sách sự kiện | 61 | 22 | 11 | 28 | 4 |
| B2 Trang chi tiết sự kiện | 61 | 22 | 16 | 23 | 3 |
| B4 My Profile — QR Code + My Activities | 61 | 25 | 11 | 25 | 4 |
| **Tổng** | **183** | **69** | **38** | **76** | **11** |

### 4.2 Usability Testing (Task 2)

| Chỉ số | Giá trị |
|---|---|
| Số participant (bắt buộc 5, ngoài lớp) | **5** (chạy qua Maze thật) |
| Task success rate (completed / partial / failed) | **100% Completed (5/5) / 0 / 0** |
| Thời gian trung bình / tác vụ | **3 phút 32 giây** (nhanh nhất 0m59s, chậm nhất 8m15s) |
| Tổng số lỗi & lần do dự | Errors trung bình **2.4/người** (5, 2, 2, 2, 1) — 3/5 người không tự tìm ra My Activities. Do dự qua lời nói: **≥4/5 người** có ít nhất 1 lần rõ ràng |
| Điểm SUS trung bình | **53.0 / 100** — dưới mốc 68, nhưng tách 2 nhóm rõ rệt (2 người 80–85 "tốt", 3 người 27.5–42.5 "dưới trung bình"), xem `appendix/a2-sus-scoring.md` |

| Severity | 0 | 1 | 2 | 3 | 4 | Tổng |
|---|:--:|:--:|:--:|:--:|:--:|:--:|
| Số usability issue (US-) | 0 | 0 | 1 | 1 | 0 | **2** |

### 4.3 Cross-Platform (Task 3)

| Màn hình | Số ô đã phủ | Pass | Fail | Đủ 3 OS? | Đủ 5 browser? | Đủ 3 device class? |
|---|:--:|:--:|:--:|:--:|:--:|:--:|
| B1 Danh sách sự kiện | 7/7 | 7 | 0 | ✅ | ✅ | ✅ |
| B2 Trang chi tiết sự kiện | 7/7 | 5 | 2 | ✅ | ✅ | ✅ |
| B4 My Profile — QR Code + My Activities | 7/7 | 5 | 2 | ✅ | ✅ | ✅ |
| **Tổng** | **21/21** | **17** | **4** | | | |

### 4.4 Findings (Task 4)

| Nguồn | Tiền tố ID | Bug | Usability | Tổng | Đã submit form |
|---|---|:--:|:--:|:--:|:--:|
| Checklist execution | `CL-` | **6** | **5** | **11** | ⬜ |
| User testing | `US-` | **0** | **2** | **2** | ⬜ |
| Cross-platform | `CP-` | **1** | **0** | **1** | ⬜ |
| Khảo sát EMS | `SV-` | **8** | **19** | **27** | ⬜ |
| **Tổng** | | **15** | **26** | **41** | |

Phân bố severity của 41 finding: **sev 3 — 10 · sev 2 — 15 · sev 1 — 13 · sev 0 — 3** · không có sev 4. Ba finding sev 0 (`SV-B2-08`, `SV-B1-02`, `SV-B2-03`) là ba lần tôi tự sửa lại kết luận sai của chính mình từ đợt khảo sát ban đầu, sau khi kiểm chứng trực tiếp trên EMS. Hai finding `US-` từ Task 2 (`US-B2-01` sev 3, `US-B2-02` sev 2) — `US-B2-01` trùng khớp độc lập với `SV-B2-09`/`S-01`/`S-14` đã có từ trước. Finding `CP-B2-01` (sev 2, Task 3) phát hiện cùng 1 sự kiện hiện giờ lệch 5 tiếng 30 phút giữa desktop và Android thật — mở rộng bằng chứng cho `S-09`/`CL-B2-02` (thiếu nhãn múi giờ) từ "thiếu tiện lợi" thành "gây sai lệch nội dung thật".

> Số dòng trong `04-findings-log.md` **phải bằng** số lần submit Google Form — TA đối chiếu chéo.

## 5. Demo video (Agent Skill)

| Video | Nội dung | Link |
|---|---|---|
| Video  | Demo skill `hw03-gui-checklist` — sinh checklist IA-04, ép AI tự soi lỗ hổng, chạy item `G-09` thật trên EMS, dựng bug entry `CL-B1-01`, commit | https://www.youtube.com/watch?v=hH9GwM8wB8M |

## 6. Self-Assessment

| No. | Criteria | Grade | Self-Assessed | Minh chứng — mở đúng file này để chấm |
|---|---|:--:|:--:|---|
| **1a** | Task 1A — Shared checklist (> 40 items, IA-01…IA-04) + sources + AI prompts *(group)* | 15 | 15 | [team/gui-checklist.md](team/gui-checklist.md)<br>[team/references.md](team/references.md) · [team/ai-prompts.md](team/ai-prompts.md) |
| **1b** | Task 1B — Checklist execution on ≥ 3 screens + bug reports *(individual)* | 15 | 15 | [01-checklist-execution.md](01-checklist-execution.md)<br>[00-main-report.md](00-main-report.md) §2 · ảnh: [evidence/task1b/](evidence/task1b/) |
| **2** | Task 2 — User testing với 5 người thật → Usability Report | 25 | 25 | [02-usability-report.md](02-usability-report.md)<br>[appendix/a1-session-notes.md](appendix/a1-session-notes.md) · [appendix/a2-sus-scoring.md](appendix/a2-sus-scoring.md) · [evidence/task2/](evidence/task2/) |
| **3** | Task 3 — Cross-Browser / Cross-Platform matrix | 25 | 25 | [03-compatibility-matrix.md](03-compatibility-matrix.md)<br>ảnh: [evidence/task3/](evidence/task3/) |
| **4** | Bug & Usability Findings submission (Google Form) + aggregated log | 10 | 10 | [04-findings-log.md](04-findings-log.md) |
| **5** | Agent Skills + demo video | 10 | 10 | [skills/](skills/) · [skills/demo-video-link.md](skills/demo-video-link.md) |
| | **Total** | **100** | 100 | |

**Căn cứ tự chấm** *(mỗi mục chấm dưới điểm tối đa phải nêu lý do có thật, không viết chung chung)*:
- _(TODO — điền sau khi tự chấm từng mục ở bảng trên)_

**Tên file nộp:** `23127183_HW03_AI_GUIUsability_EMS_<điểm tự chấm>.zip` — số này **phải khớp** tổng ở bảng trên.

## 6b. Trạng thái hoàn thành

| # | Hạng mục | Trạng thái |
|---|---|---|
| 0 | Khảo sát EMS + dựng dữ liệu thử | ✅ |
| 1a | Checklist chung > 40 item | ✅ (61 item) |
| 1b | Chạy checklist trên B1/B2/B4 | ✅ (183/183 ô) |
| 2 | 5 phiên user testing + SUS | ✅ |
| 3 | Ma trận cross-platform | ✅ 21/21 ảnh, 17 Pass/4 Fail, 1 finding `CP-B2-01` (nguyên nhân gốc đã xác nhận: đồng hồ thiết bị Android thật lệch múi giờ 7 tiếng) |
| 4 | Findings log khớp Google Form | ✅ nội dung (41 finding) · ⬜ bạn tự submit + xác nhận Google Form khớp số dòng |
| 5 | Agent Skills + video demo | ✅ 3 skill viết xong, Video 1 đã quay và có link |
| — | AI Audit Report | ✅ đủ 12 log (LOG-001…012) |
| — | AI Critique 200–300 từ *(đếm bằng `wc -w`)* | ✅ nháp 284 từ · ⬜ bạn đọc lại, đếm lại sau khi sửa văn phong |
| — | Git commit log | ✅ 34 commit đã dán vào `appendix/git-log.txt` — sẽ còn thêm commit mới cho tới lúc nộp, nhớ chạy lại lệnh lần cuối |
| — | PDF cho mọi file `.md` chính | ⬜ chưa xuất |

> 🔴 Đề §18: **thiếu bất kỳ tài liệu bắt buộc nào → 0 điểm cả bài.**
> ✅ ở trên nghĩa là **nội dung đã viết đầy đủ dựa trên dữ liệu thật đã thu thập** — không đồng nghĩa với "đã nộp"/"đã có PDF"/"TA đã xác minh". Các việc nộp-thật (submit form, xuất PDF, chụp ảnh còn thiếu) vẫn là việc của bạn theo mục 3 của `CLAUDE.md`.

## 7. Khai báo AI

> *"I use AI tools for the following tasks"* — chi tiết đầy đủ ở `appendix/a3-ai-audit-report.md`, phê bình ở `appendix/a4-ai-critique.md`.
