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
| 1 | B1 | Danh sách sự kiện — thẻ sự kiện, ô tìm kiếm, bộ lọc, phân trang | Cửa vào của cả luồng: người dùng phải **tìm được** sự kiện trước khi đăng ký. Là màn hình duy nhất trong bộ có bộ lọc + trạng thái rỗng + danh sách nhiều bản ghi, nên gánh phần lớn IA-03 | IA-03 tìm kiếm, lọc, phân trang, URL state · IA-01 thẻ, ảnh, empty state |
| 2 | B2 | Trang chi tiết sự kiện — banner, lịch trình, **khối Registration roles**, nút Đăng ký / Cancel registration | Điểm ra quyết định **và** nơi thực hiện đăng ký. Chứa nhiều trạng thái khác nhau (còn chỗ / hết chỗ / đã đóng đăng ký / chưa đăng nhập / đã đăng ký) nên là màn hình giàu IA-02 và IA-04 nhất trong bộ | IA-02 chọn vai trò, validation, xác nhận · IA-04 badge trạng thái, hộp thoại huỷ · IA-01 bố cục |
| 3 | B4 | My Profile — khối My Activities | Đầu ra quan sát được của cả luồng, My Activities dùng làm tiêu chí "hoàn thành" cho Task 2 (xem ⚠️ dưới). Có badge trạng thái nhiều màu, empty state, phân trang riêng | IA-04 badge trạng thái · IA-01 empty state · IA-03 phân trang, Filters, Export |

⚠️ **Sửa ngày 06/08/2026 — bộ màn hình đã đổi từ B2/B3/B4 sang B1/B2/B4.** Lý do: khảo sát trực tiếp cho thấy **EMS không có form đăng ký như một màn hình riêng**. Việc chọn vai trò và bấm đăng ký diễn ra ngay trong khối `Registration roles` nằm trên trang chi tiết, **cùng URL** `/events/<id>`, không điều hướng và không tải lại trang (xem `evidence/survey/KS_B3_02_form-rong.png`). Giữ nguyên "B3 Form đăng ký" sẽ thành hai màn hình trùng URL, không đạt yêu cầu "3 màn hình" của đề. B1 được đưa vào thay thế: nó là một URL riêng, thuộc đúng hành trình của kịch bản B, và phần IA-02 mất đi được bù lại bởi chính khối đăng ký trên B2.

⚠️ **Cũng sửa ngày 06/08/2026 — Task 2 không còn dùng QR làm tiêu chí hoàn thành.** Đề dùng QR làm ví dụ (*"register for an upcoming workshop and show me your check-in QR"*), nhưng QR trên EMS hoá ra là **mã cố định theo tài khoản**, không đổi theo có đăng ký hay không — một tài khoản 0 đăng ký vẫn mở được QR bình thường (`evidence/survey/KS_B4_empty-qr.png`). Dùng nó đo "đã đăng ký chưa" là phép đo yếu. Đổi sang **tìm lại được đúng đăng ký trong My Activities** — chặt hơn vì chỉ hiện đúng khi đăng ký thật thành công. `SV-B4-01` (QR tách rời khỏi luồng đăng ký) vẫn còn nguyên là một finding.

**Giải trình chung:** ba màn hình tạo thành một mạch liền **tìm sự kiện → đăng ký → xem lại đăng ký**, đúng tinh thần tác vụ mà đề nêu làm ví dụ mẫu cho kịch bản B. Nhờ vậy bộ này: (1) gói được thành **một tác vụ hướng mục tiêu duy nhất** cho Task 2; (2) phủ đủ cả bốn khía cạnh IA-01…IA-04 dù phía user không có upload/rich-text/drag-drop; (3) chạy được bằng **tài khoản guest**, không cần tài khoản HCMUS và không phụ thuộc tài khoản admin dùng chung của lớp — điều kiện then chốt để chạy 5 phiên user testing với người ngoài lớp.

**Nhóm item sẽ đánh N/A và lý do:** upload ảnh, trình soạn rich-text, kéo-thả reorder, bảng cấu hình quyền — các widget này chỉ tồn tại ở phía admin, không có trong Pool B. Mọi ô N/A đều ghi lý do trong `01-checklist-execution.md` theo yêu cầu của đề.

> Task 1B, Task 2 và Task 3 đều chạy trên **đúng bộ màn hình này**.

## 2. Nhóm & luật không trùng lặp

Nhóm có **5 người** trong khi đề chỉ có 4 kịch bản ⇒ theo §5 của đề, **một kịch bản được phép đôi**, nhưng hai người dùng chung kịch bản đó **bắt buộc chọn hai bộ màn hình không giao nhau**.

| Thành viên | MSSV | Kịch bản | Bộ màn hình |
|---|---|---|---|
| Phạm Vũ Ngọc Duy | 23127183 | **B** (nửa *registration core*) | B1 Danh sách sự kiện · B2 Trang chi tiết sự kiện · B4 My Profile — QR Code + My Activities |
| _(TODO)_ | | _(xem 2 phương án dưới)_ | _(TODO)_ |
| _(TODO)_ | | A | _(chọn 3 trong A1–A5)_ |
| _(TODO)_ | | C | _(chọn 3 trong C1–C4)_ |
| _(TODO)_ | | D | _(chọn 3 trong D1–D4)_ |

**Phương án 1 (mặc định) — đôi ở A.** Hai người chia Pool A: nửa *authoring* (A1 Events list · A2 Add/Edit Event · A3 Registration & Roles config) và nửa *operation* (A4 Participants approval · A5 Check-in · Dashboard KPI). Tôi giữ B một mình.

**Phương án 2 — đôi ở B.** ⚠️ **Đã hẹp lại sau khi tôi đổi bộ màn hình sang B1/B2/B4.** Trước đây tôi để người còn lại lấy `B1 Trang chủ + carousel`, nhưng giờ B1 nằm trong bộ của tôi nên phải bỏ khỏi phần của họ. Bộ còn rời được với tôi: **Trang chủ công khai + carousel SPOTLIGHT** *(khác với B1 danh sách sự kiện)* · **Calendar** · **Saved Events** · **B5 Đánh giá sao sau sự kiện** — chọn 3 trong 4. Lưu ý: B5 cần một sự kiện đã `ENDED` mà người đó từng tham dự và **đã check-in** (theo tài liệu chính thức §9, nút đánh giá chỉ hiện khi trạng thái là Checked-in) — cần chuẩn bị trước, không tự dựng được trong ngày.

> Nếu nhóm chọn **Phương án 2**, hai người phải ngồi đối chiếu URL với nhau chứ không chỉ đối chiếu tên màn hình — bài học rút ra từ chính việc B3 hoá ra trùng URL với B2.

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
| Số item đã chạy (= 61 × 3 màn) | _(TODO)_ / 183 |
| Passed | |
| Failed | |

| Màn hình | Items chạy | Passed | Failed | Bug tạo ra |
|---|:--:|:--:|:--:|:--:|
| B1 Danh sách sự kiện | | | | |
| B2 Trang chi tiết sự kiện | | | | |
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
| B1 Danh sách sự kiện | | | | ⬜ | ⬜ | ⬜ |
| B2 Trang chi tiết sự kiện | | | | ⬜ | ⬜ | ⬜ |
| B4 My Profile — QR Code + My Activities | | | | ⬜ | ⬜ | ⬜ |
| **Tổng** | | | | | | |

### 4.4 Findings (Task 4)

| Nguồn | Tiền tố ID | Bug | Usability | Tổng | Đã submit form |
|---|---|:--:|:--:|:--:|:--:|
| Checklist execution | `CL-` | **3** | **2** | **5** | _(TODO)_ |
| User testing | `US-` | | | | |
| Cross-platform | `CP-` | | | | |
| Khảo sát EMS | `SV-` | **8** | **19** | **27** | _(TODO)_ |
| **Tổng** | | **11** | **21** | **32** | |

Phân bố severity của 32 finding: **sev 3 — 9 · sev 2 — 10 · sev 1 — 10 · sev 0 — 3** · không có sev 4. Ba finding sev 0 (`SV-B2-08`, `SV-B1-02`, `SV-B2-03`) là ba lần tôi tự sửa lại kết luận sai của chính mình từ đợt khảo sát ban đầu, sau khi kiểm chứng trực tiếp trên EMS.

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
| 1b | Chạy checklist trên B1/B2/B4 | ⬜ |
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
