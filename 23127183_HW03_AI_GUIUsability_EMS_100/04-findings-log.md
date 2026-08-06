# Bug & Usability Findings Log — HW03

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183) · **Kịch bản:** B — User đăng ký tham dự sự kiện
**Email dùng nộp form:** 23127183@student.hcmus.edu.vn
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

> **Cột Severity dưới đây là ĐỀ XUẤT của AI kèm lý do chấm — bạn phải tự duyệt lại trước khi submit form.** Đề §7 coi việc chấm severity là phán đoán của người kiểm thử, không phải của công cụ.

| ID | Scenario / Screen | Type | Description | Steps / Heuristic | Severity | Suggested fix | Screenshot ref | Form-submission timestamp |
|---|---|---|---|---|:--:|---|---|---|
| `SV-B1-01` | Screen B1 — Trang chủ | Usability | Carousel **SPOTLIGHT EVENT** ở vị trí nổi bật nhất trang chủ đang hiển thị một sự kiện mang badge **`Ended`** | 1. Mở trang chủ khi đã đăng nhập<br>2. Xem carousel trên cùng<br>**Heuristic:** N1 · N2 | **2** | Lọc carousel chỉ lấy sự kiện `PUBLISHED` + `UPCOMING`/`ONGOING`, đúng như tài liệu E2E của đội phát triển mô tả | [KS_B1_trang-chu-carousel.png](evidence/survey/KS_B1_trang-chu-carousel.png) | |
| `SV-B1-02` | Screen B1 — Danh sách sự kiện | Usability | ✅ **Đã sửa lại 06/08/2026, đây là lỗi quan sát của tôi, không phải lỗi EMS.** Kết luận cũ ghi "không nêu lý do và không có nút xoá bộ lọc" — sai. Nhìn lại đúng ảnh gốc `KS_B1_empty-search.png`: trạng thái rỗng **đã có** câu giải thích ("There are no events matching your filters.") **và** một icon xoá bộ lọc cạnh badge `Filters`, chỉ là tôi đọc sót cả hai khi ghi lượt khảo sát đầu. Task 1B (06/08) bấm thử icon đó — **xác nhận nó xoá hết bộ lọc** | 1. Vào danh sách sự kiện, lọc ra 0 kết quả<br>2. Đọc kỹ toàn bộ khối kết quả rỗng, không chỉ dòng chữ to<br>3. Bấm icon cạnh `Filters` — bộ lọc bị xoá hết<br>**Heuristic:** N1 · N3 | **0** | Không cần sửa — hành vi đã đúng, chỉ là quan sát ban đầu của tôi bỏ sót | [KS_B1_empty-search.png](evidence/survey/KS_B1_empty-search.png) · [G-07-S1.png](evidence/task1b/G-07-S1.png) | |
| `SV-B1-03` | Screen B1 / B2 | Usability | Tiêu đề chính của sự kiện hiển thị **chuỗi mã máy** `23127326_UT_510_15:36`, tên thật của sự kiện bị đẩy xuống dòng phụ | 1. Mở danh sách sự kiện<br>2. Đọc tiêu đề các thẻ<br>**Heuristic:** N2 match real world | **2** | Lấy tên do người tạo đặt làm tiêu đề hiển thị; mã nội bộ chỉ dùng ở phía hệ thống | [KS_B2_su-kien-nguoi-khac.png](evidence/survey/KS_B2_su-kien-nguoi-khac.png) | |
| `SV-B1-04` | Screen B1 | Usability | Nhiều thẻ sự kiện hiện **ô ảnh placeholder xám trơn**, không có chữ giải thích vì sao không có ảnh | 1. Mở danh sách sự kiện<br>2. Đếm số thẻ không có ảnh<br>**Heuristic:** N1 · N8 | **1** | Thay ô xám bằng khối giữ chỗ có tên viết tắt hoặc icon kèm nhãn | [KS_B1_the-su-kien.png](evidence/survey/KS_B1_the-su-kien.png) | |
| `SV-B2-01` | Screen B2 | Usability | Vai trò hết chỗ chỉ báo **"Role is full"** và dừng ở đó — **không mời người dùng vào danh sách chờ**, dù ô đếm `Waitlisted` tồn tại ngay bên cạnh | 1. Mở sự kiện đã hết chỗ<br>2. Đọc khối Registration roles<br>**Heuristic:** N1 · N3 | **3** | Nếu có cơ chế waitlist thì phải hiện nút `Join waitlist` ngay tại chỗ báo hết chỗ | [KS_B2_workshop-b-het-cho.png](evidence/survey/KS_B2_workshop-b-het-cho.png) | |
| `SV-B2-02` | Screen B2 + B4 | Bug | Tên vai trò hiển thị bằng **tiếng Việt** ("Người dự", "Sinh viên"...) trong khi toàn bộ giao diện đang ở tiếng Anh. ✅ *Xác nhận 06/08/2026 (Task 1B, `G-12`): không phải lỗi của riêng một sự kiện* — sự kiện `Workshop: CV & Phỏng vấn thực chiến` dùng role **"Sinh viên"**, lặp lại đúng lỗi này ở **cả B2 lẫn B4** (badge `ROLES` trong My Activities cũng hiện tiếng Việt) | 1. Đặt ngôn ngữ EN<br>2. Mở một sự kiện, đọc khối Student roles trên B2<br>3. Đăng ký, vào My Activities (B4) — badge `ROLES` cũng tiếng Việt<br>**Heuristic:** N4 consistency | **2** | Dữ liệu do người dùng nhập (tên vai trò) cần có bản dịch song ngữ, hoặc nêu rõ quy ước là giữ nguyên gốc. Vì lỗi lặp lại ở nhiều sự kiện khác nhau nên đây là **vấn đề hệ thống**, không phải dữ liệu riêng lẻ | [KS_B2_workshop-b-het-cho.png](evidence/survey/KS_B2_workshop-b-het-cho.png) · [G-12-S2.png](evidence/task1b/G-12-S2.png) · [G-12-S3.png](evidence/task1b/G-12-S3.png) | |
| `SV-B2-03` | Screen B2 | Usability | Trang chi tiết **không có breadcrumb hay nút quay lại danh sách** khi đã đăng nhập, người dùng phải dựa vào nút Back của trình duyệt. ⚠️ *Ở chế độ xem công khai chưa đăng nhập thì nút `Back to events` LẠI CÓ — cần kiểm lại xem đây là khác biệt theo trạng thái đăng nhập hay tôi quan sát sót* | 1. Đăng nhập, mở một sự kiện từ danh sách<br>2. Tìm đường quay lại trong giao diện<br>3. So sánh với cùng trang ở cửa sổ ẩn danh<br>**Heuristic:** N3 · S7 | **2** | Hiện nút `Back to events` ở cả hai trạng thái đăng nhập | [KS_B2_public-an-danh.png](evidence/survey/KS_B2_public-an-danh.png) | |
| `SV-B2-04` | Screen B2 | Usability | Khối vai trò **đổi số ô số liệu giữa các sự kiện cùng loại**: Workshop B có 4 ô (`Registered`/`Pending`/`Confirmed`/`Waitlisted`), Workshop C chỉ có 3 ô — bố cục nhảy khiến người dùng phải đọc lại từ đầu ở mỗi trang | 1. Mở lần lượt hai sự kiện khác nhau<br>2. Đếm số ô trong khối Registration roles<br>**Heuristic:** N4 · S1 | **1** | Luôn hiện đủ số ô, ô không áp dụng thì để giá trị 0 hoặc trạng thái rỗng thay vì biến mất | [KS_B2_workshop-b-het-cho.png](evidence/survey/KS_B2_workshop-b-het-cho.png) | |
| `SV-B2-05` | Screen B2 — màn chặn chưa đăng nhập | Usability | Nút trên màn chặn ghi **`login`** chữ thường, trong khi mọi nút khác của hệ thống dùng Title Case (`Save event`, `Register (Student)`, `Sign In`) | 1. Mở link sự kiện không công khai ở cửa sổ ẩn danh<br>2. Đọc nhãn nút<br>**Heuristic:** N4 consistency | **1** | Thống nhất quy ước viết hoa nhãn nút toàn hệ thống | [KS_B2_chua-dang-nhap.png](evidence/survey/KS_B2_chua-dang-nhap.png) | |
| `SV-B2-06` | Screen B2 | Usability | Một số sự kiện **thiếu hẳn tag category và academic context**, chỉ còn tag campus — người dùng không có cách phân loại sự kiện đó | 1. So sánh hàng tag ở đầu trang giữa các sự kiện<br>**Heuristic:** N1 | **1** | Bắt buộc chọn category khi tạo sự kiện, hoặc hiện tag `Uncategorised` thay vì bỏ trống | [KS_B2_workshop-b-het-cho.png](evidence/survey/KS_B2_workshop-b-het-cho.png) | |
| `SV-B4-01` | Screen B4 — My Profile | Usability | ⭐ **Mã QR check-in không gắn với đăng ký nào.** Nó nằm ở một nút riêng trên đầu trang Profile, mã hoá `Student ID` của tài khoản. Ở chỗ đăng ký lẫn trong My Activities **không có đường dẫn nào tới nó**. ✅ **Đã chứng minh:** tài khoản chưa đăng ký sự kiện nào vẫn có sẵn QR đầy đủ | 1. Đăng nhập một tài khoản **chưa đăng ký gì**<br>2. Avatar → View profile → nút `QR Code`<br>3. QR hiện ra bình thường kèm `Student ID`<br>**Heuristic:** N1 · N3 · N6 recognition not recall | **3** | Hiện mã QR ngay tại thẻ đăng ký trong My Activities và trong thông báo xác nhận đăng ký, thay vì bắt người dùng nhớ đường tự đi tới Profile | [KS_B4_empty-qr.png](evidence/survey/KS_B4_empty-qr.png) · [check-in-profile.png](evidence/survey/check-in-profile.png) | |
| `SV-B4-02` | Screen B4 — menu avatar | Usability | Email trong menu avatar bị **cắt cụt** thành `23127183@student.hcmus.edu...` dù vùng hiển thị vẫn còn chỗ trống | 1. Bấm avatar góc phải<br>2. Đọc dòng email<br>**Heuristic:** N1 · S8 | **1** | Nới chiều rộng menu, hoặc cắt ở phần domain thay vì cắt cụt cuối chuỗi | [profile-1.png](evidence/survey/profile-1.png) | |
| `SV-B4-03` | B2 + B4 + tài liệu | Usability | **Ba bộ từ vựng khác nhau cho cùng một khái niệm trạng thái đăng ký:** tài liệu chính thức dùng `Approved`/`Pending Review`/`Rejected`/`Waitlisted`; ô đếm ở B2 dùng `Registered`/`Pending`/`Confirmed`/`Waitlisted`; badge ở B4 dùng `Pending review`/`Student participation`/`Upcoming` | 1. Đọc §4.2.2 tài liệu chính thức<br>2. Đối chiếu 4 ô đếm ở B2<br>3. Đối chiếu badge trên thẻ My Activities<br>**Heuristic:** N4 · S1 | **2** | Chốt một bộ từ vựng trạng thái duy nhất và áp dụng cho cả giao diện lẫn tài liệu | [profile-2.png](evidence/survey/profile-2.png) | |
| `SV-B4-04` | Screen B4 — mã QR | Bug | Mã QR **cố định theo Student ID, không đổi theo sự kiện và không đổi theo thời gian** ⇒ ai chụp lại được màn hình QR là **check-in hộ được ở mọi sự kiện**. ⚠️ *Cần theo dõi cùng một QR qua vài giờ để loại trừ khả năng nó có xoay vòng* | 1. Mở QR, lưu ảnh<br>2. Mở lại sau vài giờ, so sánh<br>3. Đối chiếu QR ở hai sự kiện khác nhau<br>**Heuristic:** N5 error prevention *(vượt sang phạm vi bảo mật)* | **3** | Sinh mã QR theo từng đăng ký, có thời hạn ngắn và chỉ hợp lệ trong khung giờ check-in của đúng sự kiện đó | [check-in-profile.png](evidence/survey/check-in-profile.png) | |
| `SV-ADM-01` | Admin — Create Event | Usability | Ô Attachments ghi đúng một câu **"Supported any file format."** và **không nêu giới hạn dung lượng hay số lượng file** trước khi người dùng chọn — người dùng chỉ biết mình vượt giới hạn sau khi upload hỏng | 1. Admin → Create Event<br>2. Cuộn tới mục Attachments<br>3. Đọc toàn bộ chữ quanh ô upload<br>**Heuristic:** N5 · P3 constraints | **2** | Ghi rõ dung lượng tối đa mỗi file, số file tối đa và danh sách định dạng ngay cạnh ô chọn | [admin-2.png](evidence/survey/admin-2.png) | |
| `SV-ADM-02` | Admin — Dashboard | Bug | **Cả 4 thẻ KPI đều bằng 0** — `Total Events 0`, `Total Check-ins 0`, `Attendance Rate 0%`, `Total Users 0` — trong khi ngay trên cùng màn hình đó badge `Support requests` đang hiện **17**, và hệ thống rõ ràng đang có sự kiện lẫn người dùng | 1. Đăng nhập admin<br>2. Đọc 4 thẻ KPI dưới cùng dashboard<br>3. Đối chiếu với Events Management và Users Management<br>**Heuristic:** N1 visibility of system status | **3** | Nối 4 chỉ số này vào dữ liệu thật; nếu chưa có API thì hiện trạng thái "chưa có dữ liệu" thay vì con số 0 gây hiểu nhầm | [admin-1.png](evidence/survey/admin-1.png) | |
| `SV-ADM-03` | Admin — Create Event *(giao diện tiếng Việt)* | Bug | Hai trường `Check-in Open` / `Check-in Close` được dịch sang tiếng Việt theo nghĩa **nhận phòng khách sạn**: `Quầy lễ tân đã mở cửa` và `Đóng cửa nhận phòng`. Người dùng đọc bản tiếng Việt không thể đoán được đây là giờ mở/đóng check-in của sự kiện | 1. Đăng nhập admin<br>2. Events Management → Create Event<br>3. Đổi ngôn ngữ sang VI<br>4. Đọc nhãn mục *Ngày & Giờ*<br>**Heuristic:** N2 match real world · N4 | **3** | Dịch lại thành `Thời gian mở check-in` / `Thời gian đóng check-in`. Rà toàn bộ chuỗi VI có gốc từ "check-in" — khả năng cao cùng một lỗi máy dịch | [KS_ADM_val-01.png](evidence/survey/KS_ADM_val-01.png) | |
| `SV-ADM-04` | Admin — Create Event | Bug | Thông báo lỗi tự mâu thuẫn: **"Check-in close date must be after check-in close date"** — so sánh một trường với chính nó. Người dùng không thể biết phải sửa gì | 1. Nhập `Check-in Open` = 02:22 07/08, `Check-in Close` = 02:22 06/08<br>2. Bấm Publish<br>3. Đọc lỗi dưới ô Check-in Close<br>**Heuristic:** N9 recover from errors | **3** | Sửa thành "Check-in close date must be after check-in **open** date" | [KS_ADM_val-04_loi-sau-publish.png](evidence/survey/KS_ADM_val-04_loi-sau-publish.png) | |
| `SV-ADM-05` | Admin — Create Event | Bug | Cả 3 cặp trường thời gian đều **nhận giá trị vô lý mà không báo gì trong lúc nhập**; lỗi chỉ hiện sau khi bấm Publish. Ô chọn ngày không giới hạn khoảng chọn theo trường liên quan | 1. Nhập End = 06/08 trong khi Start = 07/08<br>2. Rời khỏi ô — không có lỗi<br>3. Lặp lại với cặp Check-in và cặp Registration — cũng không có lỗi<br>4. Bấm Publish → 3 lỗi hiện cùng lúc<br>**Heuristic:** N5 error prevention · P3 constraints | **2** | Đặt `min` cho ô kết thúc theo giá trị ô bắt đầu, validate ngay khi rời ô thay vì dồn tới lúc submit | [KS_ADM_val-02_checkin-pair.png](evidence/survey/KS_ADM_val-02_checkin-pair.png) · [KS_ADM_val-03_registration-pair.png](evidence/survey/KS_ADM_val-03_registration-pair.png) | |
| `SV-B2-07` | Screen B2 — hộp thoại Cancel registration | Usability | Hộp thoại xác nhận có **hai nút đều bắt đầu bằng chữ "Cancel"**: `Cancel` (đóng hộp thoại) và `Cancel registration` (thực hiện huỷ). Nội dung chỉ hỏi *"Are you sure you want to cancel your registration?"*, **không nêu hậu quả** — trong khi thao tác này không hoàn tác được | 1. Vào sự kiện đã đăng ký<br>2. Cuộn xuống cuối trang, bấm `Cancel registration`<br>3. Đọc hộp thoại<br>**Heuristic:** N4 consistency · N5 · S3 informative feedback | **3** | Đổi nút đóng thành `Keep my registration`, nút huỷ thành `Yes, cancel it`. Thêm câu nêu hậu quả rõ ràng | [KS_B2_cancel-02_dialog.png](evidence/survey/KS_B2_cancel-02_dialog.png) | |
| `SV-B2-08` | Screen B2 | Usability | ✅ **Đã xác nhận lại, không phải bug.** Sau khi huỷ, khối Registration roles trở về đúng trạng thái như chưa từng đăng ký (checkbox bỏ tick, nút `Register (Student)` xuất hiện trở lại) — **và đăng ký lại được bình thường**. Ghi lại dòng này để lưu vết đã kiểm, không phải để báo lỗi | 1. Đăng ký một sự kiện<br>2. Huỷ đăng ký<br>3. Tick lại role và bấm `Register (Student)` — thành công<br>**Heuristic:** N1 visibility of system status | **0** | Không cần sửa — hành vi đúng như kỳ vọng | [KS_B2_cancel-03_sau-huy.png](evidence/survey/KS_B2_cancel-03_sau-huy.png) | |
| `SV-B4-05` | B2 vs B4 — hai màn hình mâu thuẫn | Bug | Cùng một đăng ký đã huỷ nhưng **hai màn hình nói hai điều khác nhau**: B2 xoá sạch mọi dấu vết, còn My Activities ở B4 vẫn giữ nguyên thẻ sự kiện kèm badge `Cancelled` | 1. Huỷ một đăng ký ở B2<br>2. Xem lại B2 — không còn dấu vết<br>3. Vào My Profile → My Activities — vẫn còn thẻ, badge `Cancelled`<br>**Heuristic:** S1 consistency · N1 | **2** | Thống nhất một cách hiển thị: hoặc cả hai đều giữ bản ghi `Cancelled`, hoặc cả hai đều xoá | [KS_B4_sau-huy.png](evidence/survey/KS_B4_sau-huy.png) | |
| `SV-B2-09` | Screen B2 — khối đăng ký | Usability | Đăng ký thành công **không có toast, không có thông báo, không có hướng dẫn bước tiếp theo**. Trang đứng yên tại chỗ, chỉ có badge `Pending review` xuất hiện cạnh tiêu đề khối. Không có bất kỳ chữ nào nhắc tới mã QR hay cách check-in | 1. Tick role, bấm `Register (Student)`<br>2. Quan sát toàn màn hình<br>**Heuristic:** N1 · S4 dialogs yield closure | **3** | Hiện thông báo xác nhận có liên kết trực tiếp tới mã QR check-in và nêu rõ bước tiếp theo | [KS_B3_05_sau-submit.png](evidence/survey/KS_B3_05_sau-submit.png) | |
| `SV-B2-10` | Screen B2 — khối đăng ký | Usability | Câu **"Please tick a role before submitting registration."** hiển thị bằng **màu chữ lỗi ngay khi vừa mở trang**, trước khi người dùng làm bất cứ điều gì sai | 1. Mở một sự kiện đang mở đăng ký<br>2. Cuộn tới khối Registration roles — câu chữ đỏ/cam đã có sẵn<br>**Heuristic:** N1 · N9 | **1** | Trình bày dưới dạng chú thích trung tính (xám) khi chưa thao tác, chỉ chuyển sang màu lỗi sau khi người dùng bấm submit hụt | [KS_B3_02_form-rong.png](evidence/survey/KS_B3_02_form-rong.png) | |
| `SV-B4-06` | Screen B4 — My Profile | Usability | Tên hiển thị của tài khoản là **một địa chỉ email**, và là email **khác** với email ghi ngay bên dưới ở ô EMAIL. Ô STUDENT ID hiện mã nội bộ `G69FC9C62` thay vì một mã số sinh viên. ✅ *Đã xác nhận: tên này do người dùng tự nhập tay khi tạo tài khoản, không phải hệ thống tự sinh — hạ severity vì đây là lỗi nhập liệu của người dùng, hệ thống chỉ không cản trước* | 1. Đăng nhập tài khoản guest<br>2. Avatar → View profile<br>3. So sánh dòng tên với ô EMAIL<br>**Heuristic:** N2 · N4 | **1** | Gợi ý (không bắt buộc): cảnh báo nhẹ khi người dùng nhập một chuỗi giống định dạng email vào ô Tên, để tránh nhầm lẫn khi hệ thống dùng tên này hiển thị công khai | [KS_B4_empty.png](evidence/survey/KS_B4_empty.png) | |
| `SV-NOTIF-01` | Chuông thông báo *(mọi màn hình)* | Bug | Thông báo hiển thị **tiếng Việt trong khi giao diện đang để tiếng Anh**: *"Đăng ký sự kiện được phê duyệt"*. Kèm theo: nội dung phơi thẳng email của admin (`Reviewed by admin@gmail.com`), và nhãn thời gian sai ngữ pháp (`23 second ago`) | 1. Để giao diện ở EN<br>2. Nhờ admin duyệt một đăng ký<br>3. Mở chuông thông báo<br>**Heuristic:** N4 · G-12 | **1** | Dịch chuỗi thông báo theo ngôn ngữ đang chọn; thay email admin bằng vai trò ("Reviewed by an administrator"); sửa số nhiều cho nhãn thời gian | [KS_NOTIF_approved.png](evidence/survey/KS_NOTIF_approved.png) | |
| `SV-UG-01` | User guide *(mọi màn hình)* | Usability | Tài liệu hướng dẫn **chỉ có tiếng Việt** dù giao diện đang ở tiếng Anh và cờ ngôn ngữ đang là cờ Mỹ. Ngoài ra tài liệu **không có chỗ nào nói mã QR check-in nằm ở đâu** | 1. Để giao diện EN<br>2. Header → `User guide`<br>3. Đọc Table of contents và tìm từ khoá QR<br>**Heuristic:** N10 help & documentation · S2 | **2** | Dịch tài liệu theo ngôn ngữ đang chọn; bổ sung một mục nói rõ vị trí mã QR check-in | [KS_UG_01.png](evidence/survey/KS_UG_01.png) | |
| `CL-B1-01` | Screen B1 — Thẻ sự kiện | Bug | Giá trị rỗng dùng **hai ký hiệu khác nhau cho cùng một khái niệm**. Sự kiện `Workshop B — het cho` trên B1 hiện `Location: Updating` và `Organizer: Updating`, nhưng cùng đúng sự kiện đó mở ở B2 và B4 lại hiện `Location: -`. Từ "Updating" còn dễ gây hiểu lầm là dữ liệu **đang được cập nhật/sắp có**, trong khi thực chất là **không có dữ liệu**, khác hẳn nghĩa của dấu `-` | 1. Mở B1, tìm thẻ `Workshop B — het cho`<br>2. Đọc dòng Location và Organizer — thấy chữ "Updating"<br>3. Mở B2 (chi tiết) cùng sự kiện — Location hiện `-`<br>4. Mở B4 (My Activities) cùng sự kiện — Location cũng hiện `-`<br>**Heuristic:** N4 consistency · N2 match real world (chữ "Updating" sai nghĩa) | **2** | Thống nhất một ký hiệu duy nhất (`-`) cho mọi giá trị rỗng trên toàn hệ thống; bỏ chữ "Updating" vì gây hiểu lầm sai bản chất | [G-09-S1.png](evidence/task1b/G-09-S1.png) · [G-09-S2.png](evidence/task1b/G-09-S2.png) | |
| `CL-B2-01` | Screen B2 — Trang chi tiết sự kiện (banner) | Usability | Banner ảnh của sự kiện `23127326_UT_510_15:36` (do sinh viên khác tạo) không tải được, chỉ hiện **icon ảnh chung chung** ở giữa khung, không kèm chữ giải thích — cùng lớp lỗi với `SV-B1-04` (G-06) nhưng đây là **quan sát mới trên B2**, biểu hiện khác (icon thay vì ô xám trơn). Sự kiện này cũng tái xác nhận `SV-B1-03`: tiêu đề chính vẫn là chuỗi mã máy, tên thật `Workshop Kỹ năng nghiên cứu 2026` bị đẩy xuống dòng phụ | 1. Mở B1, tìm sự kiện chưa có banner (`23127326_UT_510_15:36`)<br>2. Bấm vào để mở B2<br>3. Quan sát banner đầu trang<br>**Heuristic:** N1 · N8 | **1** | Cùng hướng sửa với `SV-B1-04`: thay icon chung chung bằng khối giữ chỗ có nhãn chữ (tên viết tắt sự kiện hoặc "No banner uploaded"), áp dụng đồng bộ cho mọi nơi hiển thị ảnh sự kiện | [G-06-S2.png](evidence/task1b/G-06-S2.png) | |
| `CL-B4-01` | Screen B4 — My Activities, khối Filters | Bug | Lọc theo **`Start Date Range` không thực sự lọc dữ liệu**. Đặt khoảng `25/07/2026 – 29/07/2026` — không trùng ngày sự kiện thật của bất kỳ hoạt động nào — nhưng danh sách vẫn hiện đủ 2 thẻ hoạt động có ngày sự kiện nằm hoàn toàn ngoài khoảng đó (`Workshop A`: 06/08/2026, `Workshop B`: 05/08/2026) | 1. Vào My Profile → My Activities<br>2. Bấm `Filters`, nhập `Start Date Range` = 25/07/2026 → 29/07/2026<br>3. Quan sát danh sách kết quả vẫn hiện đủ 2 thẻ, không thu hẹp<br>**Heuristic:** N1 visibility of system status · N4 consistency | **3** | Sửa logic áp dụng điều kiện `Start Date Range` vào truy vấn danh sách hoạt động; thêm test tự động cho trường hợp bộ lọc phải trả về 0 kết quả | [G-07-S3.png](evidence/task1b/G-07-S3.png) | |
| `CL-B4-02` | Screen B4 — My Activities, trạng thái rỗng | Usability | Khi Search ra 0 kết quả (từ khoá `áddsa`), trạng thái rỗng chỉ ghi **"No activities found"** — không nêu lý do (không nói do từ khoá tìm kiếm hay do bộ lọc ngày đang áp dụng), khác với B1 cùng tình huống lại có câu "There are no events matching your filters." Có nút `Clear all` nhưng nằm ở khối Filters phía trên, không gắn liền với thông báo rỗng | 1. Vào My Activities<br>2. Gõ từ khoá vô nghĩa vào ô Search activities<br>3. Đọc toàn bộ nội dung trạng thái rỗng, so với `SV-B1-02` (B1 có nêu lý do, B4 thì không)<br>**Heuristic:** N1 · S1 consistency | **1** | Thêm câu nêu lý do tương tự B1 ("No activities match your search/filters"), và cân nhắc đặt nút xoá bộ lọc/tìm kiếm ngay trong khối thông báo rỗng | [G-07-S3-2.png](evidence/task1b/G-07-S3-2.png) | |
| `US-B2-01` | Screen B2 | | _(dòng mẫu — điền sau 5 phiên user testing)_ | | | | | |
| `CP-B4-01` | Screen B4 | | _(dòng mẫu — điền sau đợt cross-platform)_ | | | | | |

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

> Số liệu dưới đây **đếm bằng lệnh** trên chính bảng hợp nhất, không đếm tay. Lệnh ở mục *Đối chiếu cuối cùng*.

| Nguồn | Bug | Usability | Tổng | Đã submit form |
|---|:--:|:--:|:--:|:--:|
| `CL-` Checklist (Task 1B) | **2** | **2** | **4** | _(TODO)_ |
| `US-` User testing (Task 2) | | | | |
| `CP-` Cross-platform (Task 3) | | | | |
| `SV-` Khảo sát EMS | **8** | **19** | **27** | _(TODO)_ |
| **Tổng** | **10** | **21** | **31** | |

### Theo severity

| Severity | 4 | 3 | 2 | 1 | 0 | Tổng |
|---|:--:|:--:|:--:|:--:|:--:|:--:|
| Số finding | 0 | **9** | **10** | **10** | **2** | **31** |

Không có finding severity 4. Chín finding severity 3 tập trung vào bốn nhóm — **không tìm được vé sau khi đăng ký** (`SV-B4-01`, `SV-B2-09`), **thao tác không hoàn tác được nhưng cảnh báo mơ hồ** (`SV-B2-07`), **hệ thống nói sai về chính nó** (`SV-ADM-02`, `SV-ADM-03`, `SV-ADM-04`), và **bộ lọc không thực sự lọc** (`CL-B4-01`, phát hiện khi chạy Task 1B — mục `G-07`). Hai finding severity 0 (`SV-B2-08`, `SV-B1-02`) ghi lại những điều **đã kiểm và xác nhận là đúng** — cả hai đều là chỗ tôi từng kết luận sai từ ảnh khảo sát ban đầu, giữ lại để lưu vết đã kiểm chứ không phải báo lỗi.

### Theo màn hình

| Màn hình | Số finding | Severity cao nhất |
|---|:--:|:--:|
| B1 Trang chủ / Danh sách sự kiện | **5** | 2 |
| B2 Trang chi tiết sự kiện *(gồm cả khối đăng ký)* | **11** | 3 |
| B4 My Profile — QR Code + My Activities | **8** | 3 |
| Admin — Create Event / Dashboard | **5** | 3 |
| Thông báo & User guide *(xuyên màn hình)* | **2** | 2 |

---

## Đối chiếu cuối cùng trước khi nộp

```bash
cd 23127183_HW03_AI_GUIUsability_EMS_100
# đếm finding thật (bỏ 3 dòng mẫu CL-/US-/CP-)
grep -cE "^\| \`SV-[A-Z0-9]+-[0-9]+\`" 04-findings-log.md
# phân bố severity
grep -E "^\| \`SV-[A-Z0-9]+-[0-9]+\`" 04-findings-log.md | awk -F'|' '{gsub(/[ *]/,"",$7); print $7}' | sort | uniq -c
# phân bố Bug / Usability
grep -E "^\| \`SV-[A-Z0-9]+-[0-9]+\`" 04-findings-log.md | awk -F'|' '{gsub(/ /,"",$4); print $4}' | sort | uniq -c
# mọi link ảnh đều trỏ tới file có thật
grep -oE '\(evidence/[^)]+\)' 04-findings-log.md | tr -d '()' | sort -u | while read f; do [ -f "$f" ] || echo "THIẾU: $f"; done
```

> ⚠️ **Tránh đếm trùng khi submit form.** 27 finding `SV-` đã tồn tại **trước** khi chạy Task 1B. Khi chạy checklist, một item Failed trùng nội dung với finding `SV-` nào thì ở cột Notes ghi *"= SV-xxx"* và **không tạo ID `CL-` mới, không submit form lần hai**. Nếu không, số dòng trong file này sẽ vượt số lần submit và TA sẽ thấy lệch.

- [ ] Số dòng trong bảng hợp nhất = số lần submit Google Form
- [ ] Mọi finding có `Screenshot ref` trỏ tới file **có thật**
- [ ] Mọi finding có `Form-submission timestamp`
- [ ] Đã dùng **đúng email MSSV** cho toàn bộ lần submit (không lẫn email cá nhân)
- [ ] Không có ID trùng hoặc nhảy cóc trong cùng một nhóm prefix
- [ ] Số liệu ở 3 bảng thống kê khớp với `README.md` mục 4.4 và `00-main-report.md` mục 5
