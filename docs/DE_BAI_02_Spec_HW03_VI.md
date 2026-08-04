# [BẢN DỊCH] HW03 — Đề bài chi tiết: Kiểm thử GUI & Usability trên EMS

> **Nguồn:** `2026.HW03.GUI Usability EMS_En.md` — đây là **bản đề chính thức dùng để chấm điểm**.
> **Bản dịch tiếng Việt để đọc hiểu — khi có tranh chấp nội dung, lấy bản tiếng Anh gốc làm chuẩn.**
> **⚠️ Cập nhật so với bản gốc:** link SUT trong đề (`promoter-starboard-prude.ngrok-free.dev`) **đã ngừng hoạt động**. Link hiện hành: **https://prod-dev.ems-fitus.cloud** — đã thay trong bản dịch này. Do đó câu "phục vụ qua ngrok tunnel" ở §4 giờ không còn đúng về mặt hạ tầng, nhưng **cảnh báo dữ liệu có thể bị reset vẫn giữ nguyên giá trị** vì đây vẫn là môi trường dev.

**CS423 – CSC15003 – Kiểm thử phần mềm (AI-augmented · 2026)**
**BÀI TẬP – PHIÊN BẢN AI-FIRST (2026 v2.0 · EMS)**

---

## 1. Thông tin chung

| | |
|---|---|
| **Mã bài tập** | **HW03-AI (bản EMS)** |
| **Thời lượng** | 10 giờ |
| **Deadline** | Xem link nộp bài trên Moodle |
| **Hình thức** | **Bài tập nhóm** — mỗi nhóm một checklist dùng chung; mỗi thành viên sở hữu riêng một kịch bản |
| **Quy mô nhóm** | 3–4 sinh viên (bốn kịch bản A–D; nhóm 4 người phủ được cả bốn) |
| **Nộp bài** | Moodle (thư mục nhóm + mỗi thành viên một báo cáo) |
| **Giảng viên & TA** | TS. Lâm Quang Vũ / TS. Trần Duy Hoàng / ThS. Trần Thị Bích Hạnh / ThS. Trương Phước Lộc / ThS. Hồ Tuấn Thanh |
| **Liên hệ** | lqvu@fit.hcmus.edu.vn / tdhoang@fit.hcmus.edu.vn / tbhanh@fit.hcmus.edu.vn / tploc@fit.hcmus.edu.vn / hthanh@fit.hcmus.edu.vn |
| **Chính sách AI** | Mở — nhưng **bắt buộc** có phần khai báo và đính kèm AI Audit Report |
| **Mức Bloom-AI yêu cầu** | G9.3 (Phân tích) → G9.4 (Cộng tác với AI để kiểm thử thăm dò) |

---

## 2. Nguyên tắc chỉ đạo

Những nguyên tắc này định nghĩa cách bạn được kỳ vọng làm việc xuyên suốt chuỗi bài tập của môn học. Hãy đọc kỹ trước khi bắt đầu, vì bài nộp của bạn sẽ được đánh giá dựa trên chúng.

- **Chiến lược AI-First.** Bạn bắt buộc phải áp dụng AI vào các kỹ thuật kiểm thử đã học trên lớp. Tuy nhiên, điều này **không** có nghĩa là đưa ra một prompt chung chung duy nhất kiểu *"sinh một checklist GUI và tìm các vấn đề usability trong ứng dụng này."* Thay vào đó, bạn phải dẫn dắt AI đi qua **từng bước** của kỹ thuật đúng như cách nó được dạy, dùng AI như một trợ lý có kỷ luật chứ không phải một hộp đen.

- **Con người review.** Mọi kết quả AI tạo ra đều phải được chính bạn — sinh viên — xem xét cẩn thận. Bạn hoàn toàn chịu trách nhiệm về tính đúng đắn của các kết quả này. Bạn được kỳ vọng thực hiện mọi chỉnh sửa và tinh chỉnh cần thiết — nộp output thô của AI là **không chấp nhận được**.

- **AI Audit Report.** Toàn bộ quá trình dùng AI phải được ghi lại thành một log đầy đủ. Bạn được khuyến khích xây dựng các Agent Skills có thể tự động thực hiện những hoạt động này trên các bài tập tương tự. Nếu bạn **không** dùng AI, bạn vẫn phải khai báo điều đó một cách rõ ràng.

- **Tài liệu hoá.** Toàn bộ quá trình làm việc phải được tài liệu hoá ở định dạng văn bản, chẳng hạn Markdown.

- **Chất lượng hơn số lượng hoàn thành.** Bài của bạn được chấm không chỉ dựa trên việc đã làm xong hay chưa, mà dựa trên **số lượng và chất lượng** của các sản phẩm: checklist chung, phần thực thi trên từng màn hình, usability report, ma trận cross-platform, bug report, ảnh chụp màn hình, và các link tham chiếu.

---

## 3. Chuẩn đầu ra

Hoàn thành bài tập này, bạn sẽ có thể:

- Thiết kế, theo nhóm, một **checklist GUI tái sử dụng được**, có cơ sở từ các heuristic UI được công nhận (Nielsen, Norman, Shneiderman) và từ chính giao diện EMS, đồng thời tài liệu hoá các nguồn tham khảo và AI prompt đứng sau nó.
- Áp dụng checklist chung đó lên các màn hình cụ thể của một kịch bản chức năng được giao và báo cáo lỗi.
- Thiết kế một kịch bản user-testing, chạy nó với **5 người dùng thật** trên các trang bạn phụ trách, và phân tích kết quả thành một **Usability Report**.
- Thực hiện kiểm thử cross-browser và cross-platform trên frontend web của EMS trên nhiều hệ điều hành, trình duyệt và loại thiết bị.
- Thể hiện năng lực Bloom-AI ở mức **G9.3 (Phân tích)** và **G9.4 (Cộng tác với AI để kiểm thử thăm dò)**.

---

## 4. Hệ thống được kiểm thử (SUT)

**SUT: EMS — Event Management System, Khoa Công nghệ Thông tin.** Một ứng dụng web để tạo, phát hành và vận hành các sự kiện học thuật, kèm quản trị, đăng ký người tham dự, check-in, yêu cầu hỗ trợ, phân tích số liệu và cấu hình hệ thống.

**Web (SUT):** https://prod-dev.ems-fitus.cloud

**Tài khoản Admin** (cho kịch bản admin A và C, và phía admin của D): `admin@gmail.com` / `Admin@123` — tài khoản phải có role **ADMIN** trên EMS.

**Tài khoản User** (cho phía user của kịch bản B và D): tự đăng ký tài khoản **sinh viên / giảng viên / khách** của riêng bạn qua luồng sign-up của EMS. **Không dùng chung một tài khoản** cho cả nhóm ở các kịch bản phía user — mỗi thành viên cần tài khoản riêng để phân biệt được hành động của mình.

> ⚠️ *Ứng dụng được phục vụ qua ngrok tunnel* [**nguyên văn đề — thực tế nay đã chuyển sang domain `prod-dev.ems-fitus.cloud`**] *và dữ liệu có thể bị reset định kỳ. Hãy chụp ảnh/quay màn hình lấy bằng chứng NGAY trong lúc làm; đừng giả định rằng trạng thái bạn tạo ra hôm nay vẫn còn đó ở phiên sau.*

Các tính năng của EMS được tổ chức thành các **pool** sau, ánh xạ sang bốn kịch bản ở §5:

- **Pool A — Quản trị sự kiện.** KPI trên Dashboard (Total Events, Total Check-ins, Attendance Rate, Total Users); danh sách Events; Add/Edit Event (upload thumbnail 4:3 + banner 24:9, nội dung RichText, validate ngày/giờ); cấu hình đăng ký (toggle student/lecturer/guest, Max Slots, Waitlist, vai trò phụ); Draft / Publish / Preview / Important Update / Delete; duyệt Participants & Reviews; Check-in.
- **Pool B — Trải nghiệm người tham dự.** Trang chủ công khai với carousel sự kiện nổi bật; duyệt theo danh mục và tìm kiếm; chi tiết sự kiện; form đăng ký (chọn vai trò, waitlist); My Registrations và vé barcode/QR; đánh giá sao sau sự kiện.
- **Pool C — Quản trị người dùng.** Danh sách Users (các cột Avatar+Name, Role, Member Code, Active, Audit); Assign Role; Block / Unblock; Reset Password; Export ra Excel; audit log.
- **Pool D — Yêu cầu hỗ trợ.** Phía user: tạo support request (danh mục, nội dung, đính kèm ảnh), danh sách My Requests và trang chi tiết kèm phản hồi chính thức. Phía admin: danh sách Support Requests (tab Pending / Resolved, tìm theo member code hoặc danh mục), chi tiết request với lightbox ảnh, internal note, và phản hồi chính thức.

Ngoài các pool chức năng ở trên, bài tập này tập trung vào **giao diện người dùng**. Các mối quan tâm về giao diện được tổ chức thành bốn **khía cạnh giao diện (interface aspects — IA)** — dùng làm các chiều độ phủ của checklist chung:

- **IA-01: Chuẩn UI tổng quát** (bố cục, căn chỉnh, typography, màu sắc, tính nhất quán, i18n EN/VI, trạng thái rỗng/đang tải).
- **IA-02: Form** (nhãn, validation, vị trí thông báo lỗi, xử lý trường bắt buộc, upload, trình soạn thảo rich-text).
- **IA-03: Điều hướng** (menu, breadcrumb, tab, sidebar, kéo-thả sắp xếp, hành động back/return, deep link).
- **IA-04: Phản hồi / trạng thái** (toast, badge, hộp thoại xác nhận, thanh tiến trình, màu trạng thái, cập nhật real-time).

---

## 5. Chọn phạm vi

Bài tập này làm theo **nhóm** nhưng có **phần lõi cá nhân**.

- **Sản phẩm nhóm (dùng chung):** nhóm thiết kế **một** checklist GUI mà mọi thành viên sẽ dùng (Task 1, Phần A). Nó phải phủ cả bốn khía cạnh giao diện IA-01…IA-04.
- **Sản phẩm cá nhân:** mỗi thành viên chọn **một** trong bốn kịch bản dưới đây và làm nó từ đầu đến cuối (Task 1 Phần B, Task 2, Task 3).

### Các kịch bản (mỗi thành viên chọn đúng một)

- **Kịch bản A — Admin tạo và quản lý sự kiện.** Nhóm chức năng: vòng đời sự kiện ở phía admin.
- **Kịch bản B — User đăng ký tham dự sự kiện.** Nhóm chức năng: khám phá công khai và đăng ký tham dự.
- **Kịch bản C — Admin quản lý người dùng.** Nhóm chức năng: quản trị người dùng.
- **Kịch bản D — User gửi yêu cầu Support và Admin xử lý.** Nhóm chức năng: vòng đời support-request trải qua cả phía user lẫn admin.

Với kịch bản đã chọn, hãy **liệt kê ít nhất ba (3) màn hình** thuộc nhóm chức năng đó và test từng màn hình bằng checklist của nhóm. Màn hình gợi ý (bạn có thể chọn màn khác trong cùng nhóm, nhưng **phải giải trình lý do chọn**):

- **Kịch bản A (chọn ≥ 3):** (A1) Danh sách Events với bộ lọc trạng thái và chấm thông báo; (A2) Form Add/Edit Event — upload ảnh + Rich-Text + validate ngày/giờ; (A3) Panel cấu hình Registration & Roles — Max Slots / Waitlist / vai trò phụ; (A4) Duyệt Participants & Reviews — màu trạng thái, thanh tiến trình, Export; (A5) Tab Check-in — xử lý các trạng thái quét và log real-time.
- **Kịch bản B (chọn ≥ 3):** (B1) Trang chủ / danh sách sự kiện — carousel nổi bật, danh mục, tìm kiếm/lọc; (B2) Trang chi tiết sự kiện — banner, lịch trình, nút đăng ký, thông báo waitlist; (B3) Form đăng ký — chọn vai trò, vai trò phụ, xác nhận; (B4) My Registrations / vé — trạng thái và barcode/QR; (B5) Đánh giá sau sự kiện — chấm 1–5 sao.
- **Kịch bản C (chọn ≥ 3):** (C1) Danh sách Users — tìm kiếm, bộ lọc role/active, các cột; (C2) Assign Role / sửa user; (C3) Hộp thoại Block-Unblock và Reset-Password — xác nhận + audit; (C4) Export ra Excel — độ đầy đủ của cột và phản hồi khi tải xuống.
- **Kịch bản D (chọn ≥ 3):** (D1) User — form tạo support request có đính kèm ảnh; (D2) User — danh sách My Requests và trang chi tiết kèm phản hồi; (D3) Admin — danh sách Support Requests, tab Pending/Resolved, tìm kiếm; (D4) Admin — chi tiết request — lightbox ảnh, internal note, phản hồi chính thức.

**Luật không trùng lặp.** Trong một nhóm, không hai thành viên nào được sở hữu cùng một kịch bản **và** cùng một bộ màn hình. Nếu nhóm có hơn bốn thành viên và một kịch bản bị dùng chung, những thành viên dùng chung kịch bản đó **phải chọn các màn hình khác nhau** để độ phủ không chồng lên nhau.

---

## 6. Yêu cầu

Với mỗi task dưới đây, hãy tài liệu hoá quy trình của bạn trong báo cáo và đính kèm bằng chứng bắt buộc. **Task 1B, 2 và 3 đều thao tác trên cùng ba (hoặc hơn) màn hình** của kịch bản bạn chọn.

### Task 1 — GUI Checklist

#### Phần A — Checklist dùng chung (sản phẩm nhóm)

- Theo nhóm, **thiết kế một checklist GUI hơn 40 item**, cùng nhau phủ cả bốn khía cạnh giao diện — **chuẩn UI tổng quát (IA-01)**, **form (IA-02)**, **điều hướng (IA-03)**, và **phản hồi/trạng thái (IA-04)**. Hãy ôn lại các bài giảng về GUI checklist (10 heuristic của Nielsen, 6 nguyên lý của Norman, 8 quy tắc vàng của Shneiderman, và các checklist theo từng widget) trước khi bắt đầu.

- Đặt checklist trên nền các **nguồn tham khảo**. Dùng một công cụ AI để sinh bộ item ban đầu, sau đó review nó một cách phản biện và thêm các item của riêng bạn. **Nộp, dưới dạng sản phẩm nhóm:** (1) bản thân checklist, (2) danh sách các nguồn tham khảo đã dùng (sách, bài báo, tiêu chuẩn, slide môn học), và (3) các **AI prompt** bạn đã dùng để sinh và tinh chỉnh nó.

- Với mỗi item bạn thêm vào ngoài output của AI, **giải thích vì sao AI bỏ sót nó** — ví dụ: chất lượng prompt của bạn, giới hạn của model, hoặc một đặc thù riêng của giao diện EMS. Những item mà AI hay bỏ qua bao gồm accessibility, bố cục phải-sang-trái (RTL), dark mode, điều hướng bằng bàn phím, và đa ngôn ngữ EN/VI — nhưng đây chỉ là ví dụ.

#### Phần B — Thực thi trên kịch bản của bạn (sản phẩm cá nhân)

- **Thực thi checklist chung** trên từng màn hình trong **≥ 3 màn hình bạn chọn**, đánh dấu mọi item là **Passed** hoặc **Failed** cho từng màn hình. Thêm một cột **Notes** ghi lại, với mỗi item **Failed**, lý do nó fail. Đính kèm ảnh chụp **chỉ cho các item Failed**.

- Báo cáo mọi bug phát hiện được cả trong báo cáo của bạn lẫn qua kênh nộp ở §7. Với mỗi bug, ghi rõ: màn hình, các bước tái hiện, kết quả mong đợi vs thực tế, mức nghiêm trọng, và một ảnh chụp màn hình.

### Task 2 — User Testing với 5 người dùng thật → Usability Report

Thay vì tự mình phán xét tính khả dụng, hãy **thiết kế một kịch bản user-testing, chạy nó với năm (5) người dùng thật** trên ≥ 3 màn hình thuộc gói của bạn, rồi **thu thập và phân tích kết quả** thành một **Usability Report** về các trang web đó. Ôn lại bài giảng về usability testing trước khi bắt đầu.

#### Giai đoạn 1 — Thiết kế & chuẩn bị

- **Viết task scenario.** Biến gói màn hình của bạn thành một tác vụ thực tế, hướng mục tiêu mà người dùng phải hoàn thành trên các màn hình của bạn — đưa ra một **mục tiêu**, **không phải** từng bước bấm chuột (ví dụ Kịch bản B: *"đăng ký một workshop sắp diễn ra và cho tôi xem mã QR check-in của bạn"*; Kịch bản D: *"báo rằng việc đăng ký bị lỗi và theo dõi cho đến khi nó được giải quyết"*).
- **Xác định bạn sẽ đo gì.** Tối thiểu: **mức độ hoàn thành tác vụ** (xong / một phần / thất bại), **thời gian làm tác vụ**, **số lỗi / số lần do dự**, và một điểm **SUS** hoặc **UEQ-S** sau tác vụ. Thêm một bộ câu hỏi mở ngắn về độ rõ ràng, khả năng khắc phục lỗi, tốc độ, và độ tin cậy.
- **Tuyển năm (5) người tham gia thật** khớp với chân dung người dùng mục tiêu (sinh viên, giảng viên, hoặc người đi dự sự kiện — tuỳ kịch bản), có thông tin liên hệ kiểm chứng được (Zalo / email / điện thoại, **che 4 chữ số ở giữa**). Người tham gia **phải là người ngoài lớp học này**.
- **Chạy pilot** với một người thứ sáu để phát hiện tác vụ mơ hồ hoặc luồng bị hỏng, rồi tinh chỉnh trước các phiên thật.

#### Giai đoạn 2 — Chạy 5 phiên (mỗi người một phiên)

- **Dẫn nhập.** Nói với người tham gia rằng bạn đang test **sản phẩm**, không phải test họ; đề nghị họ **nghĩ thành tiếng (think aloud)**.
- **Quan sát trung lập.** Không gợi ý dẫn dắt; chỉ can thiệp khi họ bí hoàn toàn. Ghi màn hình (và âm thanh, nếu được đồng ý) và ghi **chú thích có cấu trúc** về các điểm ma sát, lỗi, do dự, và những bực bội được nói ra.
- **Kết thúc mỗi phiên.** Cho người tham gia điền thang đo **SUS / UEQ-S**, rồi hỏi các câu hỏi thăm dò của bạn.

#### Giai đoạn 3 — Thu thập, phân tích & báo cáo

- **Tính điểm** SUS / UEQ-S trên cả 5 người tham gia và lập bảng các chỉ số tác vụ (tỉ lệ thành công, thời gian trung bình, số lỗi).
- **Phân tích tính khả dụng của các trang web liên quan:** gom nhóm các điểm đau tương tự nhau, **tách bug đơn lẻ ra khỏi vấn đề thiết kế mang tính hệ thống**, và xếp hạng các finding theo **mức nghiêm trọng (0–4)**.
- **Báo cáo.** Tạo một **Usability Report** gồm: kịch bản, bảng người tham gia (5 người, che thông tin), bảng chỉ số, các finding đã xếp hạng kèm mỗi finding một ảnh chụp, và một danh sách khuyến nghị cụ thể có ưu tiên. Log các bug thật qua kênh ở §7.
- TA có thể **gọi ngẫu nhiên hai (2)** người tham gia để xác minh. Giả mạo dẫn đến **0 điểm cho Task 2**.

### Task 3 — Cross-Browser / Cross-Platform

Kiểm thử cách **ba chức năng/màn hình** của bạn hiển thị và hoạt động trên một ma trận tương thích rộng. Ôn lại bài giảng về compatibility testing (phân biệt emulator/simulator/thiết bị thật và các "rung" — nấc thang — của BrowserStack) trước khi bắt đầu.

- **Độ phủ yêu cầu — với từng màn hình, xây một ma trận tương thích phủ:**
  - **3 hệ điều hành** — ví dụ Windows, macOS, và Android **hoặc** iOS.
  - **5 trình duyệt** — ví dụ Chrome, Firefox, Safari, Edge, và Opera (hoặc Samsung Internet trên di động).
  - **3 loại thiết bị** — desktop, tablet, và phone.

- Ma trận của bạn **không cần** đủ cả 3×5×3 tổ hợp, nhưng nó **phải chạy qua mọi hệ điều hành ít nhất một lần, mọi trình duyệt ít nhất một lần, và mọi loại thiết bị ít nhất một lần, cho từng màn hình trong ba màn hình.** Nêu rõ bạn đã phủ những ô nào và đánh dấu mỗi ô **Pass / Fail**.

- Dùng trial **BrowserStack** hoặc **LambdaTest** (rất khuyến khích). Nếu trial đã hết hạn, hãy thay bằng công cụ cloud khác (Sauce Labs, CrossBrowserTesting) hoặc thiết bị vật lý thật, miễn là mỗi ảnh chụp thể hiện rõ tên **trình duyệt / OS / thiết bị** bên cạnh URL của EMS. **Bạn tự chịu trách nhiệm xin quyền truy cập trial của mình.**

- Chụp một ảnh cho **mọi ô** trong ma trận; mỗi ảnh phải overlay tên đăng nhập của bạn dưới dạng **`MSSV@....edu.vn`** (email theo MSSV). Đính kèm ảnh cho bất kỳ **Fail** nào về hiển thị/bố cục, kèm ghi chú ngắn về lỗi (tràn nội dung, chồng lấn, vỡ layout, chữ không đọc được, control không phản hồi, v.v.).

---

## 7. Bug & Usability Findings — Kênh nộp

Mọi lỗi và mọi cải tiến usability bạn đề xuất xuyên suốt Task 1–3 đều phải được báo cáo **hai lần**:

1. **Nộp từng finding lên Google Form:** https://forms.gle/CJQFQCAXcsDbXDMM9 — dùng **email theo MSSV** (`MSSV@....edu.vn`, hoặc địa chỉ mà form yêu cầu) để các bài nộp của bạn quy được về đúng bạn.

2. **Tổng hợp toàn bộ finding vào một file** — **Bug & Usability Findings Log** — và đính kèm nó trong bài nộp. Log phải hợp nhất mọi thứ bạn đã gửi lên form, với tối thiểu các cột sau: *ID · Scenario/Screen · Type (Bug | Usability) · Description · Steps/Heuristic · Severity · Suggested fix · Screenshot ref · Form-submission timestamp.*

File tổng hợp và các lần nộp form **phải nhất quán với nhau**; TA có thể đối chiếu chéo số lượng.

---

## 8. Agent Skill

- Bạn được khuyến khích xây dựng các **Agent Skills** áp dụng cho: việc thực thi GUI-checklist, việc đánh giá usability theo heuristic, và các lần chạy ma trận tương thích — để có thể tái sử dụng trên các màn hình và luồng EMS khác.
- Nộp các skill kèm **video demo** (link YouTube) cho thấy, từ đầu đến cuối, cách bạn đã dùng skill trên một màn hình hoặc luồng hoàn chỉnh.

---

## 9. Công cụ được phép và mức Bloom-AI

Bạn có thể dùng các công cụ sau, và **phải khai báo chúng trong AI Audit Report**:

- Bất kỳ công cụ AI nào bạn chọn (ví dụ: ChatGPT, Claude, Gemini, Copilot, Cursor).
- Trial BrowserStack hoặc LambdaTest (hoặc công cụ cross-browser cloud khác / thiết bị thật).
- Google Forms (kênh nộp finding ở §7).

Mức Bloom-AI yêu cầu cho bài này là **G9.3 (Phân tích)** và **G9.4 (Cộng tác)**.

---

## 10. AI Audit Report (Phụ lục bắt buộc)

Đính kèm AI Audit Report như một phụ lục. Dùng nội dung của các AI Template được cấp nếu cần.

- Nếu bạn **không** dùng AI, hãy khai báo: *"I do not use any AI help in this exercise."*
- Nếu bạn **có** dùng AI, hãy khai báo: *"I use AI tools for the following tasks,"* và với **mỗi lần tương tác**, ghi: tên công cụ AI, ngày và giờ, prompt của bạn, và output của AI.

Để đơn giản hoá, bạn được khuyến khích tạo một skill hoặc rule tự động trích xuất các thông tin trên sau mỗi phiên AI. **Các prompt dựng checklist của nhóm (§6, Task 1 Phần A) cũng thuộc về đây.**

---

## 11. AI Critique (200–300 từ, bắt buộc)

Viết một đoạn 200–300 từ phê bình AI. AI đã sai, thiên lệch, hoặc thiếu sót ở chỗ nào? Vì sao nó không bắt được vấn đề đó? Bạn học được nguyên tắc gì về việc cộng tác với AI trong bài tập này? Dùng nội dung của các AI Template được cấp nếu cần.

---

## 12. Ràng buộc chống gian lận bằng AI

Bài tập này dựa trên các lần chạy thật trên EMS đang sống và các ảnh cross-platform thật. Những thứ sau **không được** do AI sinh ra hoặc bịa ra, và TA sẽ kiểm chứng khi chấm:

- **Bằng chứng thực thi theo từng màn hình** — ảnh chụp các màn hình EMS thật mà bạn đã test, thể hiện trạng thái thật.
- **Ảnh cross-platform**, phải hiển thị overlay email theo MSSV (**MSSV@....edu.vn**) bên cạnh URL của EMS và danh tính browser/OS/device.
- **Năm (5) người tham gia user-testing** (tên kèm Zalo / số điện thoại, che 4 chữ số ở giữa) và dữ liệu phiên thô của họ. TA có thể gọi ngẫu nhiên tối đa hai người; giả mạo làm **mất trắng Task 2**.

---

## 13. Git Commit Log

- Tạo một Git commit mới cho **mỗi bước** của quy trình kiểm thử (ví dụ: thiết kế checklist, thực thi checklist trên từng màn hình, log bug, đánh giá heuristic, và mỗi lần chạy cross-platform).
- Cung cấp Git commit log ở định dạng file văn bản.

---

## 14. Vấn đáp

**30% sinh viên được chọn ngẫu nhiên** có thể được mời vấn đáp 5–7 phút trong tuần sau deadline, để giải thích cách họ đã hoàn thành bài tập này.

---

## 15. Quy định nộp bài

- **Định dạng tên file:** `<MSSV>_HW03_AI_GUIUsability_EMS_<ĐiểmTựChấm>.zip`
  - *ĐiểmTựChấm:* số 3 chữ số trong khoảng [000, 100].
  - *Ví dụ:* `25127001_HW03_AI_GUIUsability_EMS_090.zip`

- **Sản phẩm cấp nhóm** (nộp một lần cho cả nhóm; mỗi thành viên cũng giữ một bản copy):
  - **Checklist GUI dùng chung** (Excel hoặc Markdown, > 40 item phủ IA-01…IA-04).
  - **Danh sách nguồn tham khảo** và các **AI prompt** đã dùng để dựng checklist.

- **File `.zip` cá nhân — nội dung bắt buộc:**
  - Báo cáo chính (Markdown + PDF): kịch bản đã chọn, ≥ 3 màn hình **và lý do chọn**, kết quả thực thi checklist theo từng màn hình, Usability Report, và báo cáo cross-platform.
  - **Bằng chứng user-testing:** task scenario, bảng 5 người tham gia (liên hệ đã che), ghi chú quan sát từng phiên, các phản hồi SUS / UEQ-S, bảng chỉ số, và bản ghi màn hình nếu có.
  - **Bug & Usability Findings Log** (file tổng hợp ở §7), nhất quán với các lần nộp Google Form.
  - Ảnh cross-browser / cross-platform (có overlay MSSV).
  - AI Critique và AI Audit Report (Markdown + PDF).
  - Git commit log (file text).
  - Agent Skills + link video demo.
  - Một `README.md` chứa **bảng tự đánh giá** (bên dưới) và tóm tắt kiểm thử: kịch bản đã chọn; các màn hình đã test; số item checklist đã thiết kế / đã chạy / pass / fail; số bug; số người tham gia user-testing (5) và các vấn đề usability theo mức nghiêm trọng; số ô compatibility đã phủ; video demo.
  - Bất kỳ tài liệu hỗ trợ nào khác.

- Nộp lên Moodle. Deadline xem ở link nộp bài.

---

## 16. Bảng tự đánh giá

| No. | Tiêu chí | Điểm | Điểm tự chấm |
|---|---|---:|---:|
| **1a** | Task 1A — Checklist chung (> 40 item, IA-01…IA-04) + nguồn tham khảo + AI prompts *(nhóm)* | 15 | |
| **1b** | Task 1B — Thực thi checklist trên ≥ 3 màn hình + bug report *(cá nhân)* | 15 | |
| **2** | Task 2 — User testing với 5 người dùng thật (kịch bản + 5 phiên + phân tích → Usability Report) | 25 | |
| **3** | Task 3 — Ma trận Cross-Browser / Cross-Platform (3 OS × 5 trình duyệt × 3 loại thiết bị) | 25 | |
| **4** | Nộp Bug & Usability Findings (Google Form) + log tổng hợp | 10 | |
| **5** | Agent Skills | 10 | |
| | **Tổng** | **100** | |

---

## 17. Tài liệu tham khảo

- ISTQB Foundation Level Syllabus (phiên bản mới nhất).
- Nielsen, J. *10 Usability Heuristics for User Interface Design.*
- Norman, D. *The Design of Everyday Things* (6 nguyên lý).
- Shneiderman, B. *Eight Golden Rules of Interface Design.*
- Slide môn học: *GUI + Usability + Compatibility Testing (AI-First, Combined).*
- Tài liệu BrowserStack / LambdaTest — cross-browser & cross-platform testing.
- Hardman, P. (2025). *A Post-AI Learning Taxonomy.*

---

## 18. Quy định khác

- **Không được nộp trễ.**
- **Thiếu bất kỳ tài liệu bắt buộc nào → 0 điểm.**
- **Sao chép giữa các sinh viên — bao gồm cả prompt — dẫn đến 0 điểm cho cả hai bên.** Checklist chung của nhóm được phép giống nhau trong nội bộ nhóm; mọi thứ còn lại (chọn màn hình, thực thi, usability, cross-platform, findings) phải là của riêng bạn.
