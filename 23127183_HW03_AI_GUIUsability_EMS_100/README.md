# HW03 — GUI & Usability Testing on EMS

**Sinh viên:** Phạm Vũ Ngọc Duy — **MSSV:** 23127183
**Nhóm:** _(TODO)_ — thành viên & phân chia kịch bản xem mục 2
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
| 1 | B2 | Trang chi tiết sự kiện — banner, lịch trình, nút Đăng ký, thông báo waitlist | Điểm ra quyết định của cả luồng. Chứa nhiều trạng thái nút khác nhau (còn chỗ / hết chỗ → waitlist / đã đóng đăng ký / chưa đăng nhập) nên là màn hình giàu IA-04 nhất trong bộ | IA-01 bố cục & typography · IA-04 trạng thái nút + thông báo waitlist · IA-03 deep link & quay lại |
| 2 | B3 | Form đăng ký — chọn vai trò, vai trò phụ, xác nhận | Màn hình form **duy nhất** ở phía người dùng: bỏ nó thì gần như toàn bộ nhóm item IA-02 (nhãn, trường bắt buộc, validation, vị trí thông báo lỗi, xác nhận) thành N/A và mất điểm Task 1B | IA-02 (toàn bộ phần áp dụng được cho user side) · IA-04 xác nhận & toast |
| 3 | B4 | Profile → My Activities — trạng thái đăng ký (+ mã check-in ⚠️ nếu có, đang xác minh) | Đầu ra quan sát được của cả luồng, dùng làm tiêu chí "hoàn thành" cho Task 2. Có badge trạng thái nhiều màu (Approved/Pending Review/Rejected/Waitlisted theo tài liệu chính thức), empty state | IA-04 badge trạng thái · IA-01 empty state · IA-03 điều hướng vào chi tiết |

⚠️ **06/08/2026:** tên/đường vào B4 đã sửa theo tài liệu hướng dẫn chính thức của EMS (Profile → My Activities, không phải "My Registrations"); tài liệu đó không nhắc tới mã QR. Xem `docs/KHAO_SAT_EMS.md` mục ⚠️5 để biết việc cần xác minh.

**Giải trình chung:** ba màn hình tạo thành một mạch liền **xem sự kiện → đăng ký → xem xác nhận**, đúng bằng tác vụ mà đề nêu làm ví dụ mẫu cho kịch bản B (*"register for an upcoming workshop and show me your check-in QR"* — đề gốc ghi vậy, đang xác minh hệ thống thật có đúng thế không). Nhờ vậy bộ này: (1) gói được thành **một tác vụ hướng mục tiêu duy nhất** cho Task 2; (2) phủ đủ cả bốn khía cạnh IA-01…IA-04 dù phía user không có upload/rich-text/drag-drop; (3) chạy được bằng **tài khoản riêng của từng người** (vai trò Guest, không cần tài khoản HCMUS), không phụ thuộc tài khoản admin dùng chung của lớp — điều kiện then chốt để chạy 5 phiên user testing với người ngoài lớp mà không đụng dữ liệu nhau.

**Nhóm item sẽ đánh N/A và lý do:** upload ảnh, trình soạn rich-text, kéo-thả reorder, bảng cấu hình quyền — các widget này chỉ tồn tại ở phía admin, không có trong Pool B. Mọi ô N/A đều ghi lý do trong `01-checklist-execution.md` theo yêu cầu của đề.

> Task 1B, Task 2 và Task 3 đều chạy trên **đúng bộ màn hình này**.

## 2. Nhóm & luật không trùng lặp

Nhóm có **5 người** trong khi đề chỉ có 4 kịch bản ⇒ theo §5 của đề, **một kịch bản được phép đôi**, nhưng hai người dùng chung kịch bản đó **bắt buộc chọn hai bộ màn hình không giao nhau**.

| Thành viên | MSSV | Kịch bản | Bộ màn hình |
|---|---|---|---|
| Phạm Vũ Ngọc Duy | 23127183 | **B** (nửa *registration core*) | B2 Trang chi tiết sự kiện · B3 Form đăng ký · B4 My Profile — QR Code + My Activities |
| _(TODO)_ | | _(xem 2 phương án dưới)_ | _(TODO)_ |
| _(TODO)_ | | A | _(chọn 3 trong A1–A5)_ |
| _(TODO)_ | | C | _(chọn 3 trong C1–C4)_ |
| _(TODO)_ | | D | _(chọn 3 trong D1–D4)_ |

**Phương án 1 (mặc định) — đôi ở A.** Hai người chia Pool A: nửa *authoring* (A1 Events list · A2 Add/Edit Event · A3 Registration & Roles config) và nửa *operation* (A4 Participants approval · A5 Check-in · Dashboard KPI). Tôi giữ B một mình.

**Phương án 2 — đôi ở B.** Người còn lại lấy nửa *discovery & feedback* của Pool B: **B1 Trang chủ + carousel** · **trang duyệt danh mục / kết quả tìm kiếm** · **B5 Đánh giá sao sau sự kiện**. Bộ này rời hoàn toàn với B2/B3/B4 của tôi. (Đề tách "public home with the featured-event carousel" và "category browsing and search" thành hai mục riêng trong mô tả Pool B nên tính là hai màn hình được. Lưu ý: B5 cần một sự kiện đã `ENDED` mà người đó từng tham dự — cần chuẩn bị trước.)

Xác nhận: dù chọn phương án nào, **không có hai thành viên nào trùng cả kịch bản lẫn bộ màn hình**. ⬜

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
│   └── ai-prompts.md ................ prompt AI + lý do AI bỏ sót 21 mục
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
| Số item checklist nhóm thiết kế | **59** *(> 40 ✅)* |
| — IA-01 General UI standards (`G-`) | 16 |
| — IA-02 Forms (`F-`) | 16 |
| — IA-03 Navigation (`N-`) | 11 |
| — IA-04 Feedback / state (`S-`) | 16 |
| Số item do AI sinh | 38 |
| Số item do người bổ sung (có giải thích vì sao AI sót) | **21** |
| Số item đã chạy (= 59 × 3 màn) | _(TODO)_ / 177 |
| Passed | |
| Failed | |

| Màn hình | Items chạy | Passed | Failed | Bug tạo ra |
|---|:--:|:--:|:--:|:--:|
| B2 Trang chi tiết sự kiện | | | | |
| B3 Form đăng ký | | | | |
| B4 My Profile — QR Code + My Activities | | | | |
| **Tổng** | | | | |

### 4.2 Usability Testing (Task 2)

| Chỉ số | Giá trị |
|---|---|
| Số participant (bắt buộc 5, ngoài lớp) | |
| Task success rate (completed / partial / failed) | |
| Thời gian trung bình / tác vụ | |
| Tổng số lỗi & lần do dự | |
| Điểm SUS trung bình (hoặc UEQ-S) | |

| Severity | 0 (không phải vấn đề) | 1 (cosmetic) | 2 (minor) | 3 (major) | 4 (catastrophe) | Tổng |
|---|:--:|:--:|:--:|:--:|:--:|:--:|
| Số usability issue | | | | | | |

### 4.3 Cross-Platform (Task 3)

| Màn hình | Số ô đã phủ | Pass | Fail | Đủ 3 OS? | Đủ 5 browser? | Đủ 3 device class? |
|---|:--:|:--:|:--:|:--:|:--:|:--:|
| B2 Trang chi tiết sự kiện | | | | ⬜ | ⬜ | ⬜ |
| B3 Form đăng ký | | | | ⬜ | ⬜ | ⬜ |
| B4 My Profile — QR Code + My Activities | | | | ⬜ | ⬜ | ⬜ |
| **Tổng** | | | | | | |

### 4.4 Findings (Task 4)

| Nguồn | Tiền tố ID | Bug | Usability | Tổng | Đã submit form |
|---|---|:--:|:--:|:--:|:--:|
| Checklist execution | `CL-` | | | | |
| User testing | `US-` | | | | |
| Cross-platform | `CP-` | | | | |
| Khảo sát EMS | `SV-` | | | | |
| **Tổng** | | | | | |

> Số dòng trong `04-findings-log.md` **phải bằng** số lần submit Google Form — TA đối chiếu chéo.

## 5. Demo video (Agent Skill)

| Video | Nội dung | Link |
|---|---|---|
| Video 1 | _(TODO: demo skill chạy checklist end-to-end trên 1 màn hình)_ | |
| Video 2 | _(TODO, nếu có)_ | |

## 6. Self-Assessment

| No. | Criteria | Grade | Self-Assessed | Minh chứng — mở đúng file này để chấm |
|---|---|:--:|:--:|---|
| **1a** | Task 1A — Shared checklist (> 40 items, IA-01…IA-04) + sources + AI prompts *(group)* | 15 | | [team/gui-checklist.md](team/gui-checklist.md)<br>[team/references.md](team/references.md) · [team/ai-prompts.md](team/ai-prompts.md) |
| **1b** | Task 1B — Checklist execution on ≥ 3 screens + bug reports *(individual)* | 15 | | [01-checklist-execution.md](01-checklist-execution.md)<br>[00-main-report.md](00-main-report.md) §2 · ảnh: [evidence/task1b/](evidence/task1b/) |
| **2** | Task 2 — User testing với 5 người thật → Usability Report | 25 | | [02-usability-report.md](02-usability-report.md)<br>[appendix/a1-session-notes.md](appendix/a1-session-notes.md) · [appendix/a2-sus-scoring.md](appendix/a2-sus-scoring.md) · [evidence/task2/](evidence/task2/) |
| **3** | Task 3 — Cross-Browser / Cross-Platform matrix | 25 | | [03-compatibility-matrix.md](03-compatibility-matrix.md)<br>ảnh: [evidence/task3/](evidence/task3/) |
| **4** | Bug & Usability Findings submission (Google Form) + aggregated log | 10 | | [04-findings-log.md](04-findings-log.md) |
| **5** | Agent Skills + demo video | 10 | | [skills/](skills/) · [skills/demo-video-link.md](skills/demo-video-link.md) |
| | **Total** | **100** | | |

**Căn cứ tự chấm** *(mỗi mục chấm dưới điểm tối đa phải nêu lý do có thật, không viết chung chung)*:
- _(TODO — ví dụ: "Task 2 tự trừ 2 điểm vì không đo được số lần do dự ở phiên P4 do participant nói liên tục không có khoảng lặng; đã tự khai ở `02-usability-report.md` §3.1")_

**Tên file nộp:** `23127183_HW03_AI_GUIUsability_EMS_<điểm tự chấm>.zip` — số này **phải khớp** tổng ở bảng trên.

## 6b. Trạng thái hoàn thành

| # | Hạng mục | Trạng thái |
|---|---|---|
| 0 | Khảo sát EMS + dựng dữ liệu thử | ⬜ |
| 1a | Checklist chung > 40 item | ⬜ |
| 1b | Chạy checklist trên B2/B3/B4 | ⬜ |
| 2 | 5 phiên user testing + SUS | ⬜ |
| 3 | Ma trận cross-platform | ⬜ |
| 4 | Findings log khớp Google Form | ⬜ |
| 5 | Agent Skills + video demo | ⬜ |
| — | AI Audit Report | ⬜ |
| — | AI Critique 200–300 từ *(đếm bằng `wc -w`)* | ⬜ |
| — | Git commit log | ⬜ |
| — | PDF cho mọi file `.md` chính | ⬜ |

> 🔴 Đề §18: **thiếu bất kỳ tài liệu bắt buộc nào → 0 điểm cả bài.**

## 7. Khai báo AI

> *"I use AI tools for the following tasks"* — chi tiết đầy đủ ở `appendix/a3-ai-audit-report.md`, phê bình ở `appendix/a4-ai-critique.md`.
