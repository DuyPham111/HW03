# Main Report — HW03 GUI & Usability Testing on EMS

**Họ và tên:** Phạm Vũ Ngọc Duy · **MSSV:** 23127183 · **Nhóm:** _(TODO — tên nhóm/mã nhóm trên lớp, mình chưa biết)_
**Ngày thực hiện:** 05/08/2026 → 06/08/2026
**SUT:** EMS — Event Management System, Khoa CNTT — https://prod-dev.ems-fitus.cloud
**Tài khoản admin:** `admin@gmail.com` (dùng chung toàn lớp) · **Tài khoản user riêng:** `23127183@student.hcmus.edu.vn`
**Kịch bản đã chọn:** **B — User đăng ký tham dự sự kiện** · **Màn hình:** B1 Danh sách sự kiện · B2 Trang chi tiết sự kiện · B4 My Profile — QR Code + My Activities

> **Lưu ý về môi trường:** SUT là môi trường dev (`prod-dev.ems-fitus.cloud`, thay cho link ngrok cũ đã ngừng hoạt động), dữ liệu có thể bị reset định kỳ. Mọi bằng chứng trong báo cáo này được chụp **ngay tại thời điểm quan sát**; trạng thái mô tả có thể không còn tái hiện được ở phiên sau. Thời điểm chụp được ghi kèm mỗi ảnh.

---

## 0. Chuẩn bị — Khảo sát EMS trước khi thiết kế checklist

> Trước khi soạn checklist, tôi khảo sát trực tiếp EMS để lập **danh mục widget thật** của hệ thống. Lý do: checklist GUI sinh từ mô tả chung chung sẽ cho ra item chung chung — chất lượng checklist tỉ lệ thuận với mức chi tiết của khảo sát này. Trong cùng lượt khảo sát, tôi dùng quyền admin **dựng sẵn dữ liệu thử** để ba màn hình B1/B2/B4 bộc lộ đủ trạng thái khi chạy Task 1B, 2 và 3.

| Chỉ số | Giá trị |
|---|---|
| Ngày khảo sát | 05/08/2026 (đợt 1) · 06/08/2026 (đợt 2 và đợt 3) |
| Tài khoản user dùng khảo sát | `23127183@student.hcmus.edu.vn` (đăng nhập qua nút **STUDENT**) |
| Số màn hình đã đi qua (user / admin) | 6 / 3 — *đăng nhập · B1 danh sách · B2 chi tiết (5 trạng thái) · B4 My Profile · User guide · thông báo* / *Dashboard · Create Event · Events Management* |
| Số ảnh khảo sát | **38** — 10 (đợt 1) + 9 (đợt 2) + 19 (đợt 3), kèm 1 file Excel xuất từ nút Export |
| Số finding ghi lại (prefix `SV-`) | **27** — 10 Bug / 17 Usability · severity 3: 9, sev 2: 11, sev 1: 7 · chi tiết ở `04-findings-log.md` |
| Sự kiện dữ liệu thử đã dựng | 6 — Workshop A (còn chỗ) · B (hết chỗ) · C (đóng đăng ký) · D (đã kết thúc) · TEST validation · Public Event Test |
| Bằng chứng | phiếu khảo sát đã điền: `docs/KHAO_SAT_EMS.md` · ảnh gốc: `docs/khao-sat/` · ảnh dùng cho finding: `evidence/survey/` |

**⚠️ Phát hiện làm đổi kế hoạch — và một lần tự sửa kết luận.** Đợt 1 tôi thấy trang chi tiết sự kiện bị chặn bằng *"Please sign in to view this event."* và kết luận B2 không phải màn hình công khai. **Kết luận đó sai.** Đợt 2 phát hiện form Create Event có công tắc `Public Event — Event is publicly visible` **mặc định TẮT**; ba sự kiện thử của tôi bị chặn là vì cấu hình, không phải vì EMS không hỗ trợ trang công khai. Đợt 3 dựng một sự kiện bật công tắc này rồi mở ở cửa sổ ẩn danh: **xem được toàn bộ nội dung**, header hiện nút `Sign In` (`evidence/survey/KS_B2_public-an-danh.png`).

Hệ quả: B2 có **hai nhánh phải kiểm riêng** — công khai và không công khai — chứ không phải một. Với Task 2 và Task 3, tôi vẫn dùng nhánh cần đăng nhập vì đó là luồng thật của người đăng ký, nên mỗi phiên trình duyệt sạch ở Task 3 vẫn phải đăng nhập lại.

**Những quan sát thu được từ khảo sát đã dẫn tới item checklist nào** — đây là bằng chứng cho phần *human review* của Task 1A: các item này được thêm vì **đã thấy thật trên hệ thống**, không phải vì AI gợi ý.

| Quan sát trên EMS | Màn hình | Dẫn tới item checklist |
|---|---|---|
| Nhiều thẻ sự kiện hiện ô ảnh placeholder xám không giải thích | B1 danh sách | `G-06` |
| Empty state chỉ có câu "No events found", không có nút xoá bộ lọc | B1 sau khi lọc | `G-07` |
| Trường Location bỏ trống hiển thị dấu `-` | B2 chi tiết sự kiện | `G-09` |
| Tiêu đề chính là chuỗi mã `23127326_UT_510_15:36`, tên thật nằm ở dòng phụ | B1, B2 | `G-10` |
| Tên vai trò hiện tiếng Việt "Người dự" trong khi giao diện đang tiếng Anh | B2 khối Registration roles | `G-12` |
| Sự kiện hết chỗ chỉ báo "Role is full", không mời vào waitlist dù ô `Waitlisted` tồn tại | B2 Workshop B | `F-12` |
| Trang chi tiết không có breadcrumb hay nút quay lại danh sách (đợt 1, khi đã đăng nhập) | B2 | `N-02` |
| Mở deep link khi chưa đăng nhập bị chặn cả trang bằng "Please sign in to view this event." | B2 | `N-04` |
| Badge trạng thái dùng cả màu lẫn chữ (Upcoming tím, Ended xám, Pending vàng, Waitlisted tím) | B1, B2 | `S-04` |
| Card `Slot available` đổi nền xanh → hồng khi hết chỗ | B2 Workshop A vs B | `S-05` |
| Khối vai trò có 4 ô số liệu ở Workshop B nhưng chỉ 3 ô ở Workshop C (thiếu `Waitlisted`) | B2 | `S-06` |
| Carousel SPOTLIGHT EVENT ở trang chủ hiển thị một sự kiện có badge "Ended" | B1 | `S-07` |
| Ngày giờ toàn hệ thống dùng `dd/MM/yyyy HH:mm`, không hiển thị múi giờ ở bất kỳ đâu | B1, B2 | `S-09` |
| Màn chặn đăng nhập dùng nút ghi `login` chữ thường, lệch với các nút Title Case khác | B2 | `S-13` |
| Menu `User guide` chỉ có tiếng Việt dù giao diện đang tiếng Anh; không chỗ nào nói mã QR nằm ở đâu | Header B1–B4, sidebar admin | `N-12` |
| Upload ảnh sự kiện bắt buộc 2 tỉ lệ 4:3 và 24:9, không ghi giới hạn dung lượng/định dạng/số lượng | Admin — Create Event | `F-15` |
| 6 trường thời gian phụ thuộc lẫn nhau nhận giá trị vô lý (End trước Start...) lúc nhập, chỉ báo lỗi khi Publish | Admin — Create Event | `F-16` |
| Mã QR check-in nằm ở nút riêng đầu trang Profile, tách hoàn toàn khỏi chỗ đăng ký và My Activities | B2, B4 | `N-10` |
| Phân trang My Activities gồm 4 điều khiển độc lập (Rows per page / kết quả / Go to page / ‹ 1 ›) | B4 | `N-11` |
| Sau khi đăng ký xong: không toast, không thông báo — trang đứng yên, chỉ mọc thêm badge `Pending review` | B2 → B4 | `S-14` |
| Ba bộ từ vựng khác nhau cho cùng khái niệm trạng thái (tài liệu / ô đếm B2 / badge B4) | Tài liệu, B2, B4 | `S-15` |
| Cả 4 thẻ KPI đều bằng 0 trong khi badge `Support requests` cạnh đó hiện 17 | Admin Dashboard | `S-16` |
| Số chỗ còn lại và hạn đăng ký hiển thị ngay trong khối đăng ký của B2 | B2 | `S-17` |

> Bảng đầy đủ kèm số hiệu O1–O23, ngày khảo sát và ảnh nguồn: [`team/references.md`](team/references.md) §3.

---

## 1. Kịch bản và màn hình đã chọn

### 1.1 Kịch bản

**Kịch bản B — User đăng ký tham dự sự kiện.** Nhóm chức năng: khám phá công khai và đăng ký tham dự (Pool B của đề).

**Lý do chọn:** Task 2 chiếm 25/100 điểm và là hạng mục có rủi ro thực thi cao nhất, vì nó đòi **5 người tham gia thật, ngoài lớp học**, có liên hệ kiểm chứng được và TA có quyền gọi ngẫu nhiên 2 người để xác minh. Kịch bản B là kịch bản duy nhất mà (1) tác vụ giao cho người tham gia — đăng ký một sự kiện và lấy vé — là việc **họ vốn đã hiểu mà không cần giải thích nghiệp vụ**, và (2) mỗi người **tự đăng ký tài khoản riêng** nên năm phiên không đụng dữ liệu của nhau. Các kịch bản phía admin (A, C) buộc phải đưa tài khoản `admin@gmail.com` — vốn dùng chung cho cả lớp — cho người ngoài thao tác, vừa rủi ro về dữ liệu vừa khiến tác vụ kém tự nhiên với người tham gia.

Điểm yếu đã biết của B là mật độ widget thấp hơn phía admin (không có upload ảnh, rich-text, kéo-thả). Điểm yếu này được bù bằng cách chọn bộ màn hình có nhiều **trạng thái** nhất trong Pool B (xem 1.2) và bằng việc **ghi rõ lý do N/A** cho từng item không áp dụng được, thay vì bỏ trống.

### 1.2 Ba màn hình

| # | Mã | Màn hình | Đường dẫn / cách vào | Lý do chọn | IA chính được phủ |
|---|---|---|---|---|---|
| 1 | **B1** | Danh sách sự kiện — thẻ sự kiện, ô tìm kiếm, bộ lọc, phân trang | Header → **Events** (`/events`) | Cửa vào của cả luồng — không tìm được sự kiện thì không có gì để đăng ký. Là màn hình duy nhất trong bộ có bộ lọc, trạng thái rỗng và danh sách nhiều bản ghi | IA-03 · IA-01 |
| 2 | **B2** | Trang chi tiết sự kiện — banner, lịch trình, **khối Registration roles**, nút Đăng ký / Cancel registration | B1 → chọn một sự kiện (`/events/<id>`, có deep link riêng) | Vừa là điểm ra quyết định vừa là nơi thực hiện đăng ký. Nhiều trạng thái nhất trong bộ: còn chỗ / hết chỗ / đã đóng đăng ký / chưa đăng nhập / đã đăng ký / vừa huỷ | IA-02 · IA-04 · IA-01 |
| 3 | **B4** | My Profile — nút **QR Code** + khối **My Activities** | Avatar (header) → **View profile** (`/profile`) | Đầu ra quan sát được của cả luồng; **My Activities** dùng làm tiêu chí "hoàn thành" cho Task 2 (xem ⚠️ dưới), có badge trạng thái nhiều màu, empty state, phân trang riêng | IA-04 · IA-01 · IA-03 |

⚠️ **Sửa ngày 06/08/2026 — bộ màn hình đổi từ B2/B3/B4 sang B1/B2/B4.** Kế hoạch ban đầu coi "B3 Form đăng ký" là một màn hình riêng, dựa trên suy đoán rằng nút Đăng ký sẽ mở ra một form. Khảo sát trực tiếp cho thấy **không phải như vậy**: việc chọn vai trò và bấm đăng ký diễn ra ngay trong khối `Registration roles` trên trang chi tiết, **cùng URL** `/events/<id>`, không điều hướng, không tải lại trang (`evidence/survey/KS_B3_02_form-rong.png`). Nếu giữ nguyên B3 thì bài nộp sẽ có hai "màn hình" trỏ về cùng một URL — không đạt yêu cầu 3 màn hình của đề. B1 thay vào chỗ đó: URL riêng, thuộc đúng hành trình kịch bản B, và phần IA-02 tưởng như mất đi thì thực ra vẫn còn nguyên vì khối đăng ký nằm trong B2.

**Giải trình chung:** ba màn hình tạo thành một mạch liền **tìm sự kiện → đăng ký → xem lại đăng ký**, đúng tinh thần tác vụ mà đề nêu làm ví dụ mẫu cho kịch bản B (*"register for an upcoming workshop and show me your check-in QR"*). B4 cung cấp **tiêu chí hoàn thành quan sát được từ bên ngoài** cho Task 2 và là màn hình duy nhất trong Pool B có badge trạng thái nhiều màu — thứ cần thiết để các item IA-04 của checklist không bị rỗng.

⚠️ **Sửa ngày 06/08/2026 — Task 2 không còn dùng QR làm tiêu chí hoàn thành.** Đề dùng QR làm ví dụ, nhưng khảo sát trực tiếp cho thấy QR trên EMS là **mã cố định theo tài khoản**, không đổi theo có đăng ký hay không (`evidence/survey/KS_B4_empty-qr.png` — tài khoản 0 đăng ký vẫn có QR). Dùng nó đo "đã đăng ký chưa" là một phép đo yếu. Tiêu chí hoàn thành đổi sang **tìm lại được đúng đăng ký trong My Activities** — chỉ hiện đúng khi đăng ký thật sự thành công, nên chặt hơn. Chi tiết ở `02-usability-report.md` §1.1. `SV-B4-01` (QR tách rời khỏi luồng đăng ký) vẫn giữ nguyên là một finding trong `04-findings-log.md`.

**Điều kiện dữ liệu cần chuẩn bị trước:** để ba màn hình này bộc lộ đủ trạng thái, cần có sẵn trên hệ thống ít nhất: một sự kiện `PUBLISHED` + `UPCOMING` còn chỗ, một sự kiện đã **hết chỗ và bật Waitlist**, một sự kiện đã **đóng đăng ký**, và một sự kiện bật **`Public Event`** để kiểm nhánh xem không cần đăng nhập. Các sự kiện này được tạo bằng quyền admin trong đợt khảo sát ở mục 0 và đặt tiền tố `[23127183]`.

### 1.3 Xác nhận luật không trùng lặp

Nhóm 5 người / 4 kịch bản ⇒ theo §5 của đề, một kịch bản được đôi nhưng hai người phải chọn **bộ màn hình rời nhau**.

| Thành viên | Kịch bản | Màn hình | Trùng với tôi? |
|---|---|---|:--:|
| Phạm Vũ Ngọc Duy (23127183) | B (registration core) | B1 · B2 · B4 | — |
| _(TODO)_ | _(A hoặc B — xem hai phương án dưới)_ | _(TODO)_ | ❌ |
| _(TODO)_ | A | _(TODO)_ | ❌ |
| _(TODO)_ | C | _(TODO)_ | ❌ |
| _(TODO)_ | D | _(TODO)_ | ❌ |

**Phương án 1 (mặc định) — đôi ở A:** nửa *authoring* (A1 · A2 · A3) và nửa *operation* (A4 · A5 · Dashboard KPI). Tôi giữ B một mình.
**Phương án 2 — đôi ở B:** ⚠️ đã hẹp lại sau khi tôi lấy B1 vào bộ của mình. Người còn lại chọn 3 trong 4: **Trang chủ công khai + carousel SPOTLIGHT** *(khác B1 danh sách sự kiện)* · **Calendar** · **Saved Events** · **B5 Đánh giá sao**. Hai bên phải đối chiếu **URL**, không chỉ đối chiếu tên màn hình.

---

## 2. Task 1B — Thực thi checklist GUI

> Checklist chung của nhóm: `team/gui-checklist.md` (**61** item, IA-01…IA-04).
> Bảng kết quả chi tiết từng item × từng màn hình: `01-checklist-execution.md`.

### 2.1 Tổng hợp kết quả

| Màn hình | Số item chạy | Passed | Failed | Tỉ lệ pass | Bug tạo ra |
|---|:--:|:--:|:--:|:--:|:--:|
| B1 Danh sách sự kiện | 61 (33 áp dụng) | 22 | 11 | 66.7% (22/33) | 4 (`CL-B1-01..04`) |
| B2 Trang chi tiết sự kiện | 61 (38 áp dụng) | 22 | 16 | 57.9% (22/38) | 3 (`CL-B2-01..03`) |
| B4 My Profile — QR Code + My Activities | 61 (36 áp dụng) | 25 | 11 | 69.4% (25/36) | 4 (`CL-B4-01..04`) |
| **Tổng** | **183 (107 áp dụng)** | **69** | **38** | **64.5% (69/107)** | **11** |

> N/A không tính vào mẫu số tỉ lệ pass, theo quy ước ở `team/gui-checklist.md`. Số liệu đếm lại bằng `awk` trên chính bảng ở `01-checklist-execution.md`, không đếm tay.

### 2.2 Kết quả theo khía cạnh giao diện

> Passed/Failed dưới đây là **tổng số lượt** trên cả 3 màn hình (số item × 3), không phải số item riêng biệt.

| IA | Số item | Passed | Failed | Nhận xét |
|---|:--:|:--:|:--:|---|
| IA-01 General UI standards | 16 | 33 | 14 | Gần hết Failed dồn vào 2 item lặp lại nhiều màn: `G-03` (nút màu đỏ dùng cho hành động trung tính, trùng tông với cảnh báo/phá huỷ) và `G-06` (ảnh lỗi/placeholder không có ý nghĩa) |
| IA-02 Forms | 16 | 8 | 1 | Phần lớn N/A (39/48 lượt) vì widget form (upload ảnh, rich-text, kéo-thả) chỉ tồn tại phía admin, không có trong Pool B; Failed duy nhất là `F-12` (hết chỗ không mời vào waitlist) |
| IA-03 Navigation | 12 | 10 | 12 | Khía cạnh **yếu nhất** — hơn nửa số Failed liên quan một nguyên nhân gốc: trạng thái điều hướng (bộ lọc, scroll, URL) không được giữ khi back (`N-03`, `N-05`, `N-06`), cộng thêm User guide lệch giao diện thật (`N-12`) |
| IA-04 Feedback / state | 17 | 18 | 11 | Nhiều lượt Failed nhất về số tuyệt đối nhưng phân tán nguyên nhân: thiếu múi giờ hiển thị (`S-09`, lặp cả 3 màn), hành vi khi offline không phản hồi (`S-11`), và ba bộ từ vựng trạng thái khác nhau (`S-15`) |

### 2.3 Màn hình B1 — Danh sách sự kiện

**Ảnh tổng quan màn hình:**
- [ ] ⚠️ Chưa có sẵn — chèn 1 ảnh chụp toàn màn hình B1 (đề nghị lưu tại `evidence/task1b/B1-overview.png`), overlay email MSSV + URL theo đúng quy định đề

**Item Failed** (danh sách đầy đủ 61 item × Passed/Failed/N/A/Notes/Ảnh nằm ở [`01-checklist-execution.md`](01-checklist-execution.md) — bảng dưới chỉ tóm tắt 11 item Failed để tránh trùng lặp dữ liệu):

| ID item | Finding/Bug liên kết | Ảnh |
|---|---|---|
| G-03 | `CL-B1-04` | [G-06-S2.png](evidence/task1b/G-06-S2.png) |
| G-06 | `SV-B1-04` | |
| G-09 | `CL-B1-01` | [G-09-S1.png](evidence/task1b/G-09-S1.png) |
| G-10 | `= SV-B1-03` | |
| G-11 | `= SV-NOTIF-01` | |
| N-03 | `CL-B1-02` | |
| N-05 | `CL-B1-03` | [N-05-S1.png](evidence/task1b/N-05-S1.png) |
| N-06 | `CL-B1-02` | [N-06-S1-before.png](evidence/task1b/N-06-S1-before.png) · [N-06-S1-after.png](evidence/task1b/N-06-S1-after.png) |
| N-12 | `= SV-UG-01` | |
| S-07 | `= SV-B1-01` | |
| S-09 | `CL-B2-02` | |

**Phân tích:** 11 Failed của B1 nhóm về 2 nguyên nhân gốc rõ rệt, không phải 11 lỗi rời rạc. (1) **Mất trạng thái điều hướng** — `N-03`, `N-06` đều là hệ quả của cùng một hành vi: quay lại từ B2 làm mất bộ lọc/scroll (`CL-B1-02`), phóng to ra thành `CL-B1-03` khi phát hiện URL không bao giờ phản ánh filter. (2) **Nhất quán trực quan/nội dung dùng chung với các màn khác** — `G-03` (màu nút đỏ), `G-06` (ảnh lỗi), `G-10`/`G-11`/`N-12`/`S-09` đều là finding `SV-`/`CL-` đã ghi nhận trùng lặp trên cả B2 và/hoặc B4, tức là lỗi ở tầng component dùng chung, không phải đặc thù riêng của B1. Chỉ `G-09` và `S-07` là lỗi cục bộ chỉ thấy ở B1.

### 2.4 Màn hình B2 — Trang chi tiết sự kiện (gồm khối đăng ký)

**Ảnh tổng quan màn hình:**
- [ ] ⚠️ Chưa có sẵn — chèn 1 ảnh chụp toàn màn hình B2 (đề nghị lưu tại `evidence/task1b/B2-overview.png`), overlay email MSSV + URL

**Item Failed** (chi tiết đầy đủ ở [`01-checklist-execution.md`](01-checklist-execution.md)):

| ID item | Finding/Bug liên kết | Ảnh |
|---|---|---|
| G-03 | `CL-B1-04` | [G-06-S2.png](evidence/task1b/G-06-S2.png) |
| G-06 | `CL-B2-01` | [G-06-S2.png](evidence/task1b/G-06-S2.png) |
| G-10 | `= SV-B1-03` | |
| G-11 | `= SV-NOTIF-01` | |
| G-12 | `= SV-B2-02` | [G-12-S2.png](evidence/task1b/G-12-S2.png) |
| F-12 | `= SV-B2-01` | |
| N-04 | `CL-B2-03` | |
| N-10 | `= SV-B2-09` | |
| N-12 | `= SV-UG-01` | |
| S-01 | `= SV-B2-09` | |
| S-03 | `= SV-B2-07` | |
| S-06 | `= SV-B2-04` | |
| S-09 | `CL-B2-02` | |
| S-11 | `CL-B4-04` | |
| S-14 | `= SV-B2-09` | |
| S-15 | `= SV-B4-03` | |

**Phân tích:** B2 có tỉ lệ pass thấp nhất (57.9%) trong 3 màn — hợp lý vì đây là màn hình giàu trạng thái nhất (còn chỗ / hết chỗ / đóng đăng ký / chưa đăng nhập / đã đăng ký). Cụm Failed lớn nhất xoay quanh **một nguyên nhân gốc duy nhất**: đăng ký xong hệ thống hoàn toàn im lặng — không toast, không banner xác nhận (`N-10`, `S-01`, `S-14` đều quy về `SV-B2-09`), đây cũng là finding được người dùng thật xác nhận độc lập ở Task 2 (`US-B2-01`). Cụm thứ hai là bộ đếm số liệu không nhất quán giữa các sự kiện (`S-06` thiếu cột Waitlisted ở một số sự kiện) và giữa các nguồn từ vựng trạng thái (`S-15`). Còn lại (`G-03`, `G-06`, `G-10`, `G-11`, `N-12`, `S-09`) là các finding dùng-chung-component đã nêu ở B1.

### 2.5 Màn hình B4 — My Profile (QR Code + My Activities)

**Ảnh tổng quan màn hình:**
- [ ] ⚠️ Chưa có sẵn — chèn 1 ảnh chụp toàn màn hình B4 (đề nghị lưu tại `evidence/task1b/B4-overview.png`), overlay email MSSV + URL

**Item Failed** (chi tiết đầy đủ ở [`01-checklist-execution.md`](01-checklist-execution.md)):

| ID item | Finding/Bug liên kết | Ảnh |
|---|---|---|
| G-07 | `CL-B4-02` | |
| G-10 | `= SV-B1-03` | |
| G-11 | `= SV-NOTIF-01` | |
| G-12 | `= SV-B2-02` | [G-12-S3.png](evidence/task1b/G-12-S3.png) |
| N-01 | `CL-B4-03` | [N-01-S3.png](evidence/task1b/N-01-S3.png) |
| N-03 | `CL-B1-03` | |
| N-05 | `CL-B1-03` | [N-05-S3.png](evidence/task1b/N-05-S3.png) |
| N-06 | `CL-B4-01` | |
| N-12 | `= SV-UG-01` | |
| S-09 | `CL-B2-02` | |
| S-11 | `CL-B4-04` | |

**Phân tích:** Duy nhất trong 3 màn, B4 có 2 finding **chỉ xảy ra khi offline** (`CL-B4-04` — Export/Filters/Register không phản hồi gì khi mất mạng, không cả thông báo lỗi), phát hiện được vì đây là màn hình được kiểm thêm nhánh offline. `N-01` (không có điểm nhấn nav-highlight ở Profile) và `G-07` (empty state yếu) là 2 lỗi cục bộ của B4. Còn lại (`G-10`, `G-11`, `G-12`, `N-03`, `N-05`, `N-12`, `S-09`) trùng với các finding dùng-chung-component đã phân tích ở B1/B2 — xác nhận thêm rằng đây thực sự là lỗi ở tầng thiết kế chung, không phải đặc thù một màn.

### 2.6 Bug phát hiện từ Task 1B

> Chi tiết đầy đủ (mô tả, cách tái hiện, đề xuất sửa, ảnh) ở [`04-findings-log.md`](04-findings-log.md) (prefix `CL-`). Dưới đây là bảng tóm tắt 11 finding.

| Bug-ID | Màn hình | Loại | Mô tả ngắn | Severity | Item checklist gốc |
|---|---|:--:|---|:--:|---|
| CL-B1-01 | B1 | Usability | Trường trống hiện "Updating" gây hiểu nhầm đang tải, thay vì dấu `-` | 1 | `G-09` |
| CL-B1-02 | B1 | Bug | Quay lại từ B2 mất bộ lọc + vị trí scroll đã chọn | 2 | `N-03`, `N-06` |
| CL-B1-03 | B1/B4 | Bug | URL không bao giờ phản ánh trạng thái filter đang áp dụng | 2 | `N-05` |
| CL-B1-04 | B1 | Usability | Nút Save viền đỏ, cùng tông với cảnh báo/hành động phá huỷ | 1 | `G-03` |
| CL-B2-01 | B2 | Bug | Banner chỉ dùng icon, không có text mô tả loại thông báo | 1 | `G-06` |
| CL-B2-02 | B2 | Usability | Không hiển thị múi giờ ở bất kỳ đâu trong hệ thống | 2 | `S-09` |
| CL-B2-03 | B2 | Bug | Sau khi đăng nhập, bị đẩy về trang chủ thay vì quay lại đúng sự kiện đã yêu cầu | 2 | `N-04` |
| CL-B4-01 | B4 | Bug | Bộ lọc trên My Activities không hoạt động (chọn nhưng không lọc) | 2 | `N-06` |
| CL-B4-02 | B4 | Usability | Empty state của My Activities quá yếu, không có call-to-action | 1 | `G-07` |
| CL-B4-03 | B4 | Usability | Không có nav-highlight khi đang ở trang Profile | 1 | `N-01` |
| CL-B4-04 | B4 | Bug | Khi offline: Export lỗi im lặng; Filters/Register hiện spinner rồi treo vô thời hạn | 2 | `S-11` |

---

## 3. Task 2 — Usability Report (tóm tắt)

> Báo cáo đầy đủ ở `02-usability-report.md`. Mục này chỉ tóm tắt để Main Report đọc liền mạch.

| Chỉ số | Giá trị |
|---|---|
| Task scenario | *"Bạn là người quen của khoa muốn tham dự một workshop sắp diễn ra. Hãy tìm và đăng ký tham gia, rồi cho mình xem lại đăng ký đó."* |
| Số participant | 5 (ngoài lớp, chạy qua study Maze thật) |
| Task success rate | **100% Completed (5/5)** |
| Thời gian trung bình | **3 phút 32 giây** |
| Điểm SUS trung bình | **53.0/100** — dưới mốc 68, nhưng tách 2 nhóm rõ rệt (xem `appendix/a2-sus-scoring.md`) |
| Số usability issue theo severity | 0:0 · 1:0 · 2:1 · 3:1 · 4:0 |

**Ba khuyến nghị ưu tiên cao nhất:**
1. Thêm toast xác nhận sau mọi hành động thay đổi dữ liệu, và giải thích lý do khi nút bị khoá — xác nhận độc lập bởi cả checklist (`SV-B2-09`) lẫn 2/5 người dùng thật (`US-B2-01`)
2. Tăng độ nổi bật nút quay lại danh sách trên màn hình mobile (`US-B2-02`)
3. Thống nhất một bộ từ vựng trạng thái duy nhất trên toàn hệ thống — câu SUS về tính nhất quán bị chấm thấp thứ nhì trong 10 câu (`S-15`)

**Link video 5 phiên** *(theo yêu cầu của giảng viên — dẫn thẳng ở đây, không chỉ trong `evidence/task2/`)*:

| Phiên | Người tham gia | Link video |
|---|---|---|
| P1 | Phạm Vũ Ngọc Duyên | https://youtu.be/W0gLMibEf_o |
| P2 | Nguyễn Tấn Phước | https://youtu.be/QWDMooa5skY |
| P3 | Quan Anh | https://youtu.be/w-VrYQdr4fM |
| P4 | Lê Đức Ngọc Bảo | https://youtu.be/xzQHMVQjX_E |
| P5 | Hoàng Vũ Gia Huy | https://youtu.be/k7Gr5r9RCI4 |

> Danh sách đầy đủ kèm thời lượng, transcript có mốc thời gian: [`evidence/task2/recordings.md`](evidence/task2/recordings.md). ⬜ Bạn tự kiểm lại cả 5 link có mở được **khi chưa đăng nhập YouTube** không (chế độ Unlisted).

---

## 4. Task 3 — Cross-Platform (tóm tắt)

> Báo cáo đầy đủ ở `03-compatibility-matrix.md`.

| Màn hình | Ô đã phủ | Pass | Fail | 3 OS ✓ | 5 browser ✓ | 3 device class ✓ |
|---|:--:|:--:|:--:|:--:|:--:|:--:|
| B1 Danh sách sự kiện | | | | | | |
| B2 Trang chi tiết sự kiện | | | | | | |
| B4 My Profile — QR Code + My Activities | | | | | | |

**Lỗi tương thích nghiêm trọng nhất:** _(TODO — Task 3 chưa chạy, điền sau khi có ma trận thật)_

---

## 5. Tổng hợp findings

| Nguồn | Prefix | Bug | Usability | Tổng |
|---|---|:--:|:--:|:--:|
| Checklist execution | `CL-` | 6 | 5 | 11 |
| User testing | `US-` | 0 | 2 | 2 |
| Cross-platform | `CP-` | _(chưa chạy Task 3)_ | | 0 |
| Khảo sát EMS | `SV-` | 8 | 19 | 27 |
| **Tổng** | | **14** | **26** | **40** |

> Đếm bằng lệnh trên `04-findings-log.md`, khớp với bảng ở §"Thống kê" của chính file đó — không đếm tay.

Toàn bộ đã được submit lên Google Form (https://forms.gle/CJQFQCAXcsDbXDMM9) bằng email `23127183@student.hcmus.edu.vn` và hợp nhất tại `04-findings-log.md`.

---

## 6. AI Gap Analysis

> Nơi ghi lại các trường hợp AI sai/thiếu **được phát hiện trong quá trình làm bài này**. Nội dung ở đây là nguyên liệu cho `appendix/a4-ai-critique.md`.

| # | AI đề xuất/khẳng định gì | Thực tế khi chạy thật | Vì sao AI sai | Bài học |
|---|---|---|---|---|
| 1 | Kết luận B2 không có nút quay lại danh sách khi đã đăng nhập (`N-02` → Failed, ghi ở `SV-B2-03`) | Ảnh `G-06-S2.png` đã chụp sẵn từ trước cho thấy rõ nút `Back to events` tồn tại | AI kết luận dựa trên quan sát đợt khảo sát 1 mà không tự đối chiếu chéo với ảnh khác đã có sẵn trong cùng thư mục evidence — thiếu bước "tự kiểm lại bằng chứng đã có trước khi kết luận" | Trước khi chốt Failed, phải quét lại toàn bộ ảnh evidence liên quan đến đúng màn hình đó, không chỉ dựa vào ghi chú khảo sát ban đầu |
| 2 | Đề xuất S1/S2 Passed, S3 Failed cho `S-15` (nhất quán từ vựng trạng thái) dựa trên diễn giải ban đầu của câu hỏi | Sau khi tự xem lại đúng 3 ảnh gốc: thực chất mâu thuẫn nằm **trong nội bộ B2** (badge "Pending review" khác ô đếm "Pending"), không phải giữa 3 màn hình như khung câu hỏi ban đầu ngụ ý | AI suy diễn cấu trúc so sánh (3 màn với nhau) thay vì đọc đúng nội dung ảnh được cung cấp | Với item so sánh nhất quán, phải liệt kê rõ **đang so sánh cái gì với cái gì** trước khi gán Passed/Failed, không suy đoán từ tên item |
| 3 | Dùng thời lượng của riêng khối Website Test trong Maze (vd P1 = 8m15s) làm "thời lượng video" trong `evidence/task2/recordings.md` | Ảnh danh sách video thật cho thấy độ dài file (P1 = 12:45) dài hơn nhiều vì còn bao gồm lúc điền 10 câu SUS + 5 câu hỏi mở sau task | AI không phân biệt "thời lượng của block Website Test" (Maze đo riêng) với "thời lượng toàn bộ video ghi hình" (gồm mọi block) — hai khái niệm dễ nhầm vì cùng nằm trong 1 report Maze | Khi Maze (hay công cụ tương tự) trả về nhiều loại "duration" khác nhau, phải xác nhận rõ đơn vị đo trước khi đưa vào báo cáo, đặc biệt với số liệu quyết định tiêu chí đạt/không đạt |

---

## 7. Kết luận

**Tình trạng chất lượng giao diện EMS ở kịch bản B:** Ba màn hình B1/B2/B4 dùng được cho luồng chính (tìm sự kiện → đăng ký → xem lại đăng ký) và không có lỗi chặn hoàn toàn (severity 4 = 0/40), nhưng tỉ lệ pass checklist chỉ 64.5% (69/107) và điểm SUS thực đo từ 5 người dùng thật chỉ 53.0/100 — dưới mốc trung bình 68. Phần lớn vấn đề không phải lỗi hiển thị vặt mà là **thiếu phản hồi hệ thống**: sau đăng ký, sau lọc, sau khi offline, giao diện thường "im lặng" thay vì xác nhận hoặc báo lỗi rõ ràng — đúng loại lỗi khiến người dùng bấm lại nhiều lần hoặc nghi ngờ thao tác đã thành công hay chưa, được cả checklist (`SV-B2-09`) lẫn 2/5 người dùng thật (`US-B2-01`) xác nhận độc lập.

**Vấn đề mang tính hệ thống (không phải bug đơn lẻ):**
1. **Không có phản hồi trạng thái sau hành động thay đổi dữ liệu** — đăng ký (`SV-B2-09`/`US-B2-01`), lọc trên My Activities (`CL-B4-01`), thao tác lúc offline (`CL-B4-04`) đều cùng một dạng: hệ thống nhận thao tác nhưng không nói gì về kết quả. Đây là nguyên nhân gốc của ít nhất 5 finding riêng lẻ trong 04-findings-log.md, không phải 5 lỗi độc lập.
2. **Trạng thái điều hướng/bộ lọc không được giữ khi quay lại** — URL không bao giờ phản ánh filter (`CL-B1-03`), quay lại từ B2 mất cả bộ lọc lẫn vị trí scroll (`CL-B1-02`) — khiến hành trình tìm-sự-kiện phải làm lại từ đầu mỗi lần rời khỏi B1.

**Giới hạn của đợt kiểm thử này:**
- SUT là môi trường **dev dùng chung** với sinh viên khác trong lớp; dữ liệu (sự kiện thử, đăng ký) có thể bị người khác chỉnh hoặc bị reset giữa các đợt khảo sát — mọi kết luận chỉ đảm bảo đúng tại đúng thời điểm chụp ảnh ghi kèm.
- Tài khoản admin `admin@gmail.com` dùng chung toàn lớp nên không kiểm soát được trạng thái phía admin lúc kiểm thử (không loại trừ khả năng người khác đang thao tác song song).
- Task 2 dùng thang SUS bị cấu hình nhầm 1–10 thay vì chuẩn 1–5 trên Maze, phải quy đổi bằng công thức `ceil(điểm/2)` — quy đổi này là suy diễn hợp lý chứ không phải phép đo trực tiếp, xem giải trình đầy đủ ở `appendix/a2-sus-scoring.md`.
- Task 3 (cross-platform) chưa chạy tại thời điểm viết mục này — kết luận trên chỉ dựa trên Task 1B + Task 2, chưa tính lỗi tương thích trình duyệt/thiết bị.

---

## Phụ lục

| Tài liệu | Đường dẫn |
|---|---|
| Checklist chung của nhóm | `team/gui-checklist.md` |
| Nguồn tham khảo | `team/references.md` · `team/ai-prompts.md` |
| AI prompts dựng checklist | `team/references.md` · `team/ai-prompts.md` |
| Bảng thực thi checklist chi tiết | `01-checklist-execution.md` |
| Usability Report | `02-usability-report.md` |
| Cross-Platform Report | `03-compatibility-matrix.md` |
| Bug & Usability Findings Log | `04-findings-log.md` |
| AI Audit Report | `appendix/a3-ai-audit-report.md` |
| AI Critique | `appendix/a4-ai-critique.md` |
| Git commit log | `appendix/git-log.txt` |
