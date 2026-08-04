# Main Report — HW03 GUI & Usability Testing on EMS

**Họ và tên:** Phạm Vũ Ngọc Duy · **MSSV:** 23127183 · **Nhóm:** _(TODO)_
**Ngày thực hiện:** _(TODO)_ → _(TODO)_
**SUT:** EMS — Event Management System, Khoa CNTT — https://prod-dev.ems-fitus.cloud
**Tài khoản admin:** `admin@gmail.com` (dùng chung toàn lớp) · **Tài khoản user riêng:** _(TODO)_
**Kịch bản đã chọn:** **B — User đăng ký tham dự sự kiện** · **Màn hình:** B2 Trang chi tiết sự kiện · B3 Form đăng ký · B4 My Registrations + vé QR

> **Lưu ý về môi trường:** SUT là môi trường dev (`prod-dev.ems-fitus.cloud`, thay cho link ngrok cũ đã ngừng hoạt động), dữ liệu có thể bị reset định kỳ. Mọi bằng chứng trong báo cáo này được chụp **ngay tại thời điểm quan sát**; trạng thái mô tả có thể không còn tái hiện được ở phiên sau. Thời điểm chụp được ghi kèm mỗi ảnh.

---

## 0. Chuẩn bị — Khảo sát EMS trước khi thiết kế checklist

> Trước khi soạn checklist, tôi khảo sát trực tiếp EMS để lập **danh mục widget thật** của hệ thống. Lý do: checklist GUI sinh từ mô tả chung chung sẽ cho ra item chung chung — chất lượng checklist tỉ lệ thuận với mức chi tiết của khảo sát này. Trong cùng lượt khảo sát, tôi dùng quyền admin **dựng sẵn dữ liệu thử** để ba màn hình B2/B3/B4 bộc lộ đủ trạng thái khi chạy Task 1B, 2 và 3.

| Chỉ số | Giá trị |
|---|---|
| Ngày khảo sát | _(TODO)_ |
| Số màn hình đã đi qua (user / admin) | _(TODO)_ / _(TODO)_ |
| Số widget ghi nhận vào danh mục | _(TODO)_ |
| Số quan sát nghi vấn ghi lại (prefix `SV-`) | _(TODO)_ |
| Sự kiện dữ liệu thử đã dựng | _(TODO)_ / 4 |
| Bằng chứng | `evidence/survey/` · phiếu khảo sát đã điền: `docs/KHAO_SAT_EMS.md` |

**Những quan sát thu được từ khảo sát đã dẫn tới item checklist nào** — đây là bằng chứng cho phần *human review* của Task 1A: các item này được thêm vì **đã thấy thật trên hệ thống**, không phải vì AI gợi ý.

| Quan sát trên EMS | Màn hình | Dẫn tới item checklist |
|---|---|---|
| _(TODO)_ | | |
| | | |

---

## 1. Kịch bản và màn hình đã chọn

### 1.1 Kịch bản

**Kịch bản B — User đăng ký tham dự sự kiện.** Nhóm chức năng: khám phá công khai và đăng ký tham dự (Pool B của đề).

**Lý do chọn:** Task 2 chiếm 25/100 điểm và là hạng mục có rủi ro thực thi cao nhất, vì nó đòi **5 người tham gia thật, ngoài lớp học**, có liên hệ kiểm chứng được và TA có quyền gọi ngẫu nhiên 2 người để xác minh. Kịch bản B là kịch bản duy nhất mà (1) tác vụ giao cho người tham gia — đăng ký một sự kiện và lấy vé — là việc **họ vốn đã hiểu mà không cần giải thích nghiệp vụ**, và (2) mỗi người **tự đăng ký tài khoản riêng** nên năm phiên không đụng dữ liệu của nhau. Các kịch bản phía admin (A, C) buộc phải đưa tài khoản `admin@gmail.com` — vốn dùng chung cho cả lớp — cho người ngoài thao tác, vừa rủi ro về dữ liệu vừa khiến tác vụ kém tự nhiên với người tham gia.

Điểm yếu đã biết của B là mật độ widget thấp hơn phía admin (không có upload ảnh, rich-text, kéo-thả). Điểm yếu này được bù bằng cách chọn bộ màn hình có nhiều **trạng thái** nhất trong Pool B (xem 1.2) và bằng việc **ghi rõ lý do N/A** cho từng item không áp dụng được, thay vì bỏ trống.

### 1.2 Ba màn hình

| # | Mã | Màn hình | Đường dẫn / cách vào | Lý do chọn | IA chính được phủ |
|---|---|---|---|---|---|
| 1 | **B2** | Trang chi tiết sự kiện — banner, lịch trình, nút Đăng ký, thông báo waitlist | Trang chủ → chọn một sự kiện (có deep link riêng) | Điểm ra quyết định của cả luồng; chứa nhiều trạng thái nút khác nhau (còn chỗ / hết chỗ → waitlist / đã đóng đăng ký / chưa đăng nhập) nên là màn hình giàu IA-04 nhất trong bộ | IA-01 · IA-04 · IA-03 |
| 2 | **B3** | Form đăng ký — chọn vai trò, vai trò phụ, xác nhận | B2 → nút **Đăng ký** | Màn hình form **duy nhất** ở phía người dùng; bỏ nó thì gần như toàn bộ nhóm item IA-02 (nhãn, trường bắt buộc, validation, vị trí thông báo lỗi, xác nhận) thành N/A | IA-02 · IA-04 |
| 3 | **B4** | My Registrations + vé QR/barcode — trạng thái đăng ký, mã check-in | Menu tài khoản → **My Registrations** | Đầu ra quan sát được của cả luồng, dùng làm tiêu chí "hoàn thành" cho Task 2; có badge trạng thái nhiều màu, empty state, và phần render mã QR — nơi lỗi hiển thị cross-platform dễ lộ nhất | IA-04 · IA-01 · IA-03 |

**Giải trình chung:** ba màn hình tạo thành một mạch liền **xem sự kiện → đăng ký → nhận vé**, trùng đúng với tác vụ mà đề nêu làm ví dụ mẫu cho kịch bản B (*"register for an upcoming workshop and show me your check-in QR"*). Bộ này được chọn thay vì B1+B2+B3 vì B4 cung cấp **tiêu chí hoàn thành quan sát được từ bên ngoài** cho Task 2 (nhìn thấy mã QR là xong) và là màn hình duy nhất trong Pool B có badge trạng thái nhiều màu — thứ cần thiết để các item IA-04 của checklist không bị rỗng. B1 (trang chủ + carousel + tìm kiếm) vẫn là đường vào của tác vụ và được quan sát trong lúc chạy phiên, nhưng không nằm trong phạm vi chấm để tránh chồng lấn với thành viên khác trong nhóm.

**Điều kiện dữ liệu cần chuẩn bị trước:** để ba màn hình này bộc lộ đủ trạng thái, cần có sẵn trên hệ thống ít nhất: một sự kiện `PUBLISHED` + `UPCOMING` còn chỗ, một sự kiện đã **hết chỗ và bật Waitlist**, và một sự kiện đã **đóng đăng ký**. Các sự kiện này được tạo bằng quyền admin trong lượt chạy E2E ở mục 0 và đặt tiền tố `[23127183]`.

### 1.3 Xác nhận luật không trùng lặp

Nhóm 5 người / 4 kịch bản ⇒ theo §5 của đề, một kịch bản được đôi nhưng hai người phải chọn **bộ màn hình rời nhau**.

| Thành viên | Kịch bản | Màn hình | Trùng với tôi? |
|---|---|---|:--:|
| Phạm Vũ Ngọc Duy (23127183) | B (registration core) | B2 · B3 · B4 | — |
| _(TODO)_ | _(A hoặc B — xem hai phương án dưới)_ | _(TODO)_ | ❌ |
| _(TODO)_ | A | _(TODO)_ | ❌ |
| _(TODO)_ | C | _(TODO)_ | ❌ |
| _(TODO)_ | D | _(TODO)_ | ❌ |

**Phương án 1 (mặc định) — đôi ở A:** nửa *authoring* (A1 · A2 · A3) và nửa *operation* (A4 · A5 · Dashboard KPI). Tôi giữ B một mình.
**Phương án 2 — đôi ở B:** người còn lại lấy nửa *discovery & feedback* (B1 Trang chủ + carousel · trang duyệt danh mục/tìm kiếm · B5 Đánh giá sao), rời hoàn toàn với B2/B3/B4.

---

## 2. Task 1B — Thực thi checklist GUI

> Checklist chung của nhóm: `team/gui-checklist.md` (_(TODO)_ item, IA-01…IA-04).
> Bảng kết quả chi tiết từng item × từng màn hình: `01-checklist-execution.md`.

### 2.1 Tổng hợp kết quả

| Màn hình | Số item chạy | Passed | Failed | Tỉ lệ pass | Bug tạo ra |
|---|:--:|:--:|:--:|:--:|:--:|
| B2 Trang chi tiết sự kiện | | | | | |
| B3 Form đăng ký | | | | | |
| B4 My Registrations + vé QR | | | | | |
| **Tổng** | | | | | |

### 2.2 Kết quả theo khía cạnh giao diện

| IA | Số item | Passed | Failed | Nhận xét |
|---|:--:|:--:|:--:|---|
| IA-01 General UI standards | | | | |
| IA-02 Forms | | | | |
| IA-03 Navigation | | | | |
| IA-04 Feedback / state | | | | |

### 2.3 Màn hình B2 — Trang chi tiết sự kiện

**Ảnh tổng quan màn hình:** _(TODO)_

| ID item | Kết quả | Notes (bắt buộc nếu Failed) | Bug-ID | Ảnh |
|---|:--:|---|---|---|
| | | | | |

**Phân tích:** _(TODO — các item fail có liên quan nhau không? có phải cùng một nguyên nhân gốc?)_

### 2.4 Màn hình B3 — Form đăng ký
_(cấu trúc như trên)_

### 2.5 Màn hình B4 — My Registrations + vé QR
_(cấu trúc như trên)_

### 2.6 Bug phát hiện từ Task 1B

> Chi tiết đầy đủ ở `04-findings-log.md` (prefix `CL-`). Dưới đây là bảng tóm tắt.

| Bug-ID | Màn hình | Mô tả ngắn | Severity | Item checklist liên quan | Ảnh |
|---|---|---|:--:|---|---|
| CL-001 | | | | | |

---

## 3. Task 2 — Usability Report (tóm tắt)

> Báo cáo đầy đủ ở `02-usability-report.md`. Mục này chỉ tóm tắt để Main Report đọc liền mạch.

| Chỉ số | Giá trị |
|---|---|
| Task scenario | _(TODO — 1 câu, hướng mục tiêu)_ |
| Số participant | 5 (ngoài lớp) |
| Task success rate | |
| Thời gian trung bình | |
| Điểm SUS / UEQ-S trung bình | |
| Số usability issue theo severity | 0:_ · 1:_ · 2:_ · 3:_ · 4:_ |

**Ba khuyến nghị ưu tiên cao nhất:**
1. _(TODO)_
2. _(TODO)_
3. _(TODO)_

---

## 4. Task 3 — Cross-Platform (tóm tắt)

> Báo cáo đầy đủ ở `03-compatibility-matrix.md`.

| Màn hình | Ô đã phủ | Pass | Fail | 3 OS ✓ | 5 browser ✓ | 3 device class ✓ |
|---|:--:|:--:|:--:|:--:|:--:|:--:|
| B2 Trang chi tiết sự kiện | | | | | | |
| B3 Form đăng ký | | | | | | |
| B4 My Registrations + vé QR | | | | | | |

**Lỗi tương thích nghiêm trọng nhất:** _(TODO)_

---

## 5. Tổng hợp findings

| Nguồn | Prefix | Bug | Usability | Tổng |
|---|---|:--:|:--:|:--:|
| Checklist execution | `CL-` | | | |
| User testing | `US-` | | | |
| Cross-platform | `CP-` | | | |
| Khảo sát EMS | `SV-` | | | |
| **Tổng** | | | | |

Toàn bộ đã được submit lên Google Form (https://forms.gle/CJQFQCAXcsDbXDMM9) bằng email `pvnduy23@clc.fitus.edu.vn` và hợp nhất tại `04-findings-log.md`.

---

## 6. AI Gap Analysis

> Nơi ghi lại các trường hợp AI sai/thiếu **được phát hiện trong quá trình làm bài này**. Nội dung ở đây là nguyên liệu cho `appendix/a4-ai-critique.md`.

| # | AI đề xuất/khẳng định gì | Thực tế khi chạy thật | Vì sao AI sai | Bài học |
|---|---|---|---|---|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |

---

## 7. Kết luận

**Tình trạng chất lượng giao diện EMS ở kịch bản B:** _(TODO — đánh giá tổng thể 1 đoạn)_

**Vấn đề mang tính hệ thống (không phải bug đơn lẻ):**
1. _(TODO)_
2. _(TODO)_

**Giới hạn của đợt kiểm thử này:** _(TODO — ví dụ: dữ liệu bị reset giữa chừng, tài khoản admin dùng chung nên không kiểm soát được trạng thái, trial cross-browser giới hạn số phút…)_

---

## Phụ lục

| Tài liệu | Đường dẫn |
|---|---|
| Checklist chung của nhóm | `team/gui-checklist.md` |
| Nguồn tham khảo | `team/references.md` |
| AI prompts dựng checklist | `team/ai-prompts.md` |
| Bảng thực thi checklist chi tiết | `01-checklist-execution.md` |
| Usability Report | `02-usability-report.md` |
| Cross-Platform Report | `03-compatibility-matrix.md` |
| Bug & Usability Findings Log | `04-findings-log.md` |
| AI Audit Report | `appendix/a3-ai-audit-report.md` |
| AI Critique | `appendix/a4-ai-critique.md` |
| Git commit log | `appendix/git-log.txt` |
