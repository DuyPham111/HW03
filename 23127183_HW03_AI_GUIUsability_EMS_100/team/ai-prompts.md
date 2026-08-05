# AI Prompts & Giải trình lượt review — Checklist GUI của nhóm

**Nhóm:** _(TODO)_ · **Bài:** HW03 Task 1A · **Ngày:** _(TODO)_

> Một trong ba sản phẩm nhóm bắt buộc của Task 1A, cùng với [`gui-checklist.md`](gui-checklist.md) và [`references.md`](references.md).
> Đề §6 Task 1 Phần A yêu cầu hai thứ trong file này: **(1)** các AI prompt đã dùng để sinh và tinh chỉnh checklist · **(2)** với mỗi mục người tự thêm, **giải thích vì sao AI bỏ sót nó**.
> Nội dung §2 **cũng phải xuất hiện** trong [`../appendix/a3-ai-audit-report.md`](../appendix/a3-ai-audit-report.md) — đề §10 nói rõ điều này.
> ⚠️ Prompt được phép giống nhau **trong nội bộ nhóm**. Chia sẻ sang nhóm/sinh viên khác = **0 điểm cả hai bên** (đề §18).

---

## 1. Cách nhóm dùng AI cho task này

Đề §2 cấm tường minh cách làm "một prompt chung chung": *"this does not mean issuing a single, generic prompt such as 'generate a GUI checklist and find usability problems in this app'."*

Quy trình nhóm áp dụng — **khảo sát trước, AI sau**:

| Bước | Ai làm | Nội dung |
|---|---|---|
| 1 | **Người** | Khảo sát trực tiếp EMS, lập danh mục widget thật + chụp 10 ảnh · `docs/KHAO_SAT_EMS.md` |
| 2 | AI | Nạp khung heuristic + **dán danh mục widget thật vào**, chưa sinh mục nào |
| 3 | AI | Sinh mục theo **từng khía cạnh IA riêng** (4 lượt), không xin gần 60 mục một lượt |
| 4 | **Người** | Review từng lượt: loại mục trùng nghĩa, sửa mục không kiểm chứng được, sửa mã heuristic bị gán bừa |
| 5 | AI | Tự soi lỗ hổng checklist của chính nó |
| 6 | **Người** | Bổ sung mục AI vẫn không nêu ra + ghi lý do (§3) và **loại bỏ có lý do** những vùng không áp dụng (§4) |

**Nguyên tắc gán nhãn cột *Nguồn gốc*:** một mục chỉ được đánh `RV` khi nó **truy được về một quan sát cụ thể** trong phiếu khảo sát (`docs/KHAO_SAT_EMS.md` §6 và `references.md` §3) — tức là con người cung cấp dữ liệu thực tế mà AI không thể có. Mọi mục khác đánh `AI`, kể cả khi câu chữ đã được người sửa lại.

---

## 2. Nhật ký prompt

> ⚠️ **Bạn phải kiểm tra và bổ sung mục này trước khi nộp:** điền ngày giờ chính xác, và nếu bạn có chạy thêm lượt prompt nào ngoài những lượt dưới đây thì thêm block mới. Đừng để nhật ký thiếu so với thực tế.

### [P-01] — Khảo sát EMS làm nguyên liệu (chưa dùng AI sinh checklist)

- **Tool:** — *(không dùng AI, con người tự thao tác trên EMS)*
- **Ngày & giờ:** 05/08/2026, ~17:35–18:35
- **Việc đã làm:** đăng nhập bằng `23127183@student.hcmus.edu.vn`, dựng 3 sự kiện dữ liệu thử, đi qua màn đăng nhập + B1 danh sách + B2 chi tiết ở 4 trạng thái, chụp 10 ảnh
- **Kết quả:** danh mục widget thật + 14 quan sát nghi vấn — đây là input bắt buộc cho [P-02]
- **Human Review Notes:** _(TODO — bạn tự viết: khảo sát xong thấy điều gì bất ngờ so với hình dung ban đầu?)_

### [P-02] — Nạp khung heuristic + bối cảnh SUT

- **Tool:** _(TODO — ghi rõ tên + model)_
- **Ngày & giờ:** _(TODO)_
- **Prompt:**
```
Bạn là chuyên gia kiểm thử giao diện. Tôi sẽ xây một GUI checklist cho SUT là EMS
(Event Management System — web app quản lý sự kiện của Khoa CNTT, có phía user và phía
admin, hỗ trợ song ngữ EN/VI).

Khung lý thuyết bắt buộc dùng, mỗi mục phải gắn với ít nhất một mã:
- Nielsen 10 usability heuristics (N1..N10)
- Norman 6 design principles (P1..P6)
- Shneiderman 8 golden rules (S1..S8)
- WCAG 2.2 (mã W) cho phần accessibility

Checklist chia theo 4 khía cạnh:
- IA-01 (prefix G-) chuẩn UI chung
- IA-02 (prefix F-) forms
- IA-03 (prefix N-) navigation
- IA-04 (prefix S-) feedback/state

Đây là các widget THẬT tôi đã quan sát trên EMS ngày 05/08/2026:
[DÁN KHỐI "DANH MỤC WIDGET" Ở PHẦN 5 CỦA docs/KHAO_SAT_EMS.md]

CHƯA sinh checklist. Hãy: (1) xác nhận bạn đã hiểu khung; (2) hỏi lại tôi những thông tin
về SUT còn thiếu mà nếu có sẽ giúp checklist bám sát hệ thống này hơn.
```
- **AI Output:** _(TODO — tóm tắt AI hỏi lại những gì)_
- **Human Review Notes:** _(TODO — câu hỏi nào của AI cho thấy mô tả của bạn còn mỏng? bạn bổ sung gì?)_

### [P-03] … [P-06] — Sinh mục theo từng khía cạnh (4 lượt riêng)

- **Tool:** _(TODO)_ · **Ngày & giờ:** _(TODO)_
- **Prompt** *(chạy 4 lần, thay `G-`/`F-`/`N-`/`S-` và số lượng 16/14/9/13)*:
```
Sinh mục checklist cho riêng khía cạnh IA-01 (prefix G-).

Format bảng đúng 4 cột: | ID | Mục kiểm tra | Nguồn | Nguồn gốc |
- ID: G-01, G-02...
- "Mục kiểm tra": viết ở dạng KHẲNG ĐỊNH, đủ cụ thể để nhìn màn hình là kết luận
  Passed hay Failed ngay, KHÔNG cần thêm cột hướng dẫn. Nêu ngưỡng đo được nếu có
  (vd "tương phản >= 4.5:1", "không scroll ngang ở >= 1280px").
- "Nguồn": mã heuristic cụ thể (N4, P2, S6, W SC 1.4.3, SL). Không ghi chung chung.
- "Nguồn gốc": ghi AI cho toàn bộ mục bạn sinh.
- KHÔNG sinh mục trùng nghĩa nhau.
- Mục phải áp dụng được cho ÍT NHẤT một trong các widget tôi đã liệt kê.

Sinh 16 mục cho IA-01.
```
- **AI Output:** _(TODO)_
- **Human Review Notes:** _(TODO — mỗi lượt bạn loại/sửa mục nào? Đây là phần được chấm kỹ)_

### [P-07] — Ép AI tự soi lỗ hổng checklist của chính nó

- **Tool:** _(TODO)_ · **Ngày & giờ:** _(TODO)_
- **Prompt:**
```
Đây là checklist hiện tại sau khi tôi đã review và loại bớt: [DÁN TOÀN BỘ 4 BẢNG]

1) Liệt kê những vùng giao diện mà checklist này CHƯA phủ.
2) Với mỗi vùng thiếu, giải thích vì sao một checklist sinh tự động thường bỏ qua nó.
3) KHÔNG thêm mục mới ở bước này — chỉ liệt kê lỗ hổng.
```
- **AI Output:** _(TODO)_
- **Human Review Notes:** _(TODO — vùng nào AI VẪN không nêu ra? Đó chính là mục bạn tự thêm ở §3)_

### [P-08] — Rà độ phủ heuristic và kiểm đếm

- **Tool:** _(TODO)_ · **Ngày & giờ:** _(TODO)_
- **Prompt:**
```
Đây là checklist đã chốt: [DÁN]
1) Đếm mỗi heuristic (N1..N10, P1..P6, S1..S8, W) được bao nhiêu mục tham chiếu.
2) Chỉ ra heuristic nào đang bằng 0 và đề xuất mục có thể thêm để phủ, kèm lý do.
3) Chỉ ra mục nào gán mã heuristic KHÔNG chính xác, giải thích vì sao và đề xuất mã đúng.
```
- **AI Output:** _(TODO)_
- **Human Review Notes:** _(TODO — bạn đồng ý sửa những mã nào, giữ nguyên mã nào và vì sao)_

---

## 3. Mười bốn mục do NGƯỜI bổ sung — vì sao AI bỏ sót

> **Đây là phần được chấm kỹ nhất của Task 1A.** Mỗi dòng phải truy được về một quan sát cụ thể trong `docs/KHAO_SAT_EMS.md` — không viết chung chung kiểu "AI không đủ thông minh".
> Ba loại lý do theo đề: **(a)** prompt của mình thiếu ngữ cảnh · **(b)** giới hạn của model · **(c)** đặc thù riêng của EMS.
> ⚠️ **Bạn nên đọc lại và viết lại theo giọng của mình** — đây là phần thể hiện chính bạn đã review, không phải AI.

| ID | Mục (rút gọn) | Loại | Vì sao AI bỏ sót |
|---|---|:--:|---|
| **G-06** | Ảnh lỗi phải có khối giữ chỗ có ý nghĩa, không để ô xám trơn | (b) | AI sinh được mục "ảnh hiển thị đúng", nhưng **không biết trên EMS thật rất nhiều thẻ sự kiện đang không có ảnh** — nó không nhìn thấy màn hình nên không hình dung được trạng thái lỗi này phổ biến đến mức nào. Chỉ khi mở trang chủ và thấy hàng loạt ô xám mới nảy ra mục này |
| **G-07** | Empty state phải nêu lý do **và** gợi ý hành động tiếp theo | (a) + (c) | Prompt ban đầu chỉ ghi "empty/loading states" nên AI hiểu là "có empty state hay không". Sau khi tự lọc ra kết quả rỗng trên EMS và **thấy mình bị kẹt không biết cách xoá bộ lọc**, mới nhận ra tiêu chí đúng phải là "có lối thoát", chứ không phải "có thông báo" |
| **G-09** | Giá trị rỗng dùng cùng một ký hiệu thống nhất | (c) | Đây là quy ước hiển thị riêng của EMS (dùng dấu `-`). AI không thể biết hệ thống này chọn ký hiệu gì, nên không nghĩ tới việc kiểm **tính nhất quán của ký hiệu đó** giữa các màn hình |
| **G-10** | Không phơi mã định danh nội bộ ra làm nhãn hiển thị | (c) | AI có mục chung "dùng ngôn ngữ người dùng", nhưng biểu hiện cụ thể trên EMS — **tiêu đề sự kiện là chuỗi `23127326_UT_510_15:36`, tên thật bị đẩy xuống dòng phụ** — chỉ lộ ra khi mở trang thật |
| **G-12** | Dữ liệu hiển thị cũng phải theo ngôn ngữ đang chọn | (b) | AI mặc định i18n là chuyện của **chuỗi giao diện**. Nó không nghĩ tới việc **dữ liệu do admin nhập** (tên vai trò "Người dự") cũng là bề mặt giao diện và cũng lẫn ngôn ngữ. Phát hiện khi để giao diện ở EN mà vẫn thấy chữ tiếng Việt trong khối vai trò |
| **F-12** | Lựa chọn bị khoá phải nêu lý do và lối đi thay thế | (c) | Đây là **điểm đau nghiệp vụ riêng của EMS**: sự kiện hết chỗ có bật Waitlist, ô `Waitlisted` tồn tại, nhưng giao diện chỉ báo "Role is full" mà **không hề mời người dùng vào danh sách chờ**. AI không biết hệ thống có cơ chế waitlist ở tầng dữ liệu nhưng thiếu ở tầng giao diện |
| **N-02** | Trang chi tiết phải có đường quay lại trong giao diện | (b) | AI có sinh mục về breadcrumb, nhưng ở dạng "breadcrumb hiển thị đúng phân cấp" — giả định là breadcrumb **có tồn tại**. Thực tế EMS **không có breadcrumb lẫn nút back** trên trang chi tiết, nên tiêu chí đúng phải là "có đường quay lại hay không", không phải "breadcrumb đúng hay sai" |
| **N-04** | Sau khi đăng nhập phải quay lại đúng trang đã yêu cầu | (c) | Chỉ phát hiện khi mở deep link tới sự kiện ở cửa sổ ẩn danh và **bị chặn cả trang** bằng "Please sign in to view this event.". AI mặc định trang chi tiết sự kiện là nội dung công khai — đúng với hầu hết web sự kiện, nhưng sai với EMS |
| **S-04** | Badge trạng thái phải có cả màu lẫn nhãn chữ, thống nhất mọi màn | (a) | Prompt có nhắc "status colours" nên AI sinh mục về **màu đúng ngữ nghĩa**, nhưng không nghĩ tới yêu cầu **không được chỉ dựa vào màu** (WCAG SC 1.4.1). Bổ sung sau khi đếm được EMS có ít nhất 6 trạng thái khác nhau và nhận ra người mù màu sẽ không phân biệt được |
| **S-05** | Khối đổi màu theo trạng thái phải kèm nhãn chữ giải thích | (c) | Hành vi rất riêng của EMS: card `Slot available` **đổi nền xanh sang hồng** khi hết chỗ nhưng chữ vẫn chỉ là "Student: 0". AI không thể biết hệ thống dùng cách truyền đạt bằng màu nền như vậy |
| **S-06** | Số ô/số trường của một khối phải giữ nguyên giữa các bản ghi cùng loại | (b) | Đây là lỗi **chỉ thấy khi so sánh hai trang cạnh nhau**: Workshop B có 4 ô số liệu, Workshop C chỉ có 3. AI xem xét từng màn hình một cách độc lập nên không có khái niệm "so sánh chéo giữa các bản ghi cùng loại" |
| **S-07** | Khu vực nổi bật chỉ hiển thị bản ghi còn hiệu lực | (c) | Chỉ phát hiện khi vào trang chủ và thấy **carousel SPOTLIGHT đang đăng một sự kiện có badge "Ended"**. AI không biết EMS có tính năng chọn sự kiện nổi bật thủ công và tính năng đó không tự lọc theo trạng thái thời gian |
| **S-09** | Ngày giờ thống nhất định dạng và nêu rõ múi giờ ở chỗ có hạn chót | (a) | Prompt không nhắc rằng EMS có ba mốc thời gian chồng nhau (Event date / Registration period / Check-in period). Sau khi thấy cả ba đều hiển thị `dd/MM/yyyy HH:mm` **không kèm múi giờ**, mới thấy đây là rủi ro thật với người đăng ký sát hạn |
| **S-13** | Nhãn nút và tiêu đề dùng cùng quy ước viết hoa | (b) | Loại lỗi quá nhỏ để AI ưu tiên đưa vào danh sách 16 mục đầu. Chỉ nảy ra khi nhìn thấy nút ghi **`login`** chữ thường ở màn chặn đăng nhập, trong khi mọi nút khác đều Title Case (`Save event`, `Login`) |


### Bảy mục bổ sung sau đợt khảo sát 2 (06/08/2026)

Đợt này khảo sát **form Create Event phía admin**, **trang My Profile** và **Admin Dashboard** — ba nơi lượt 1 chưa chạm tới.

| ID | Mục (rút gọn) | Loại | Vì sao AI bỏ sót |
|---|---|:--:|---|
| **F-15** | Ô upload phải nêu giới hạn dung lượng và số lượng file | (c) | AI có sinh `F-08` về "kiểm tra định dạng và dung lượng", nhưng biểu hiện thật trên EMS ngược lại: ô Attachments ghi đúng một câu **"Supported any file format."** và **không nêu giới hạn nào cả**. Tiêu chí đúng phải là "có nêu giới hạn hay không", chứ không phải "kiểm tra có đúng không" — chỉ nhận ra khi nhìn thấy dòng chữ thật đó |
| **F-16** | Chặn cấu hình vô lý ở các cặp trường thời gian phụ thuộc nhau | (c) | AI có `F-06` về "ngày kết thúc không trước ngày bắt đầu" — một cặp. Thực tế EMS có **ba cặp chồng nhau**: Start–End, Check-in Open–Close, Registration Open–Close, cộng thêm quan hệ chéo giữa Registration Close và End. AI không thể biết form có tới 6 trường thời gian bắt buộc nếu không nhìn thấy mục Date & Time và Registration |
| **N-10** | Chức năng cần ngay sau một thao tác phải nằm trong tầm với của ngữ cảnh đó | (c) | Đây là mục quan trọng nhất của đợt này, sinh ra từ `SV-B4-01`: **mã QR check-in nằm ở nút riêng trên trang Profile, tách hoàn toàn khỏi chỗ đăng ký**. AI không thể biết kiến trúc thông tin của EMS đặt QR ở đâu, nên không có cách nào nghĩ ra tiêu chí "chức năng kế tiếp có nằm đúng chỗ người dùng sẽ tìm không" |
| **N-11** | Danh sách dài có phân trang thống nhất, hiển thị rõ trang mấy trên tổng bao nhiêu | (a) | Prompt ban đầu không hề nhắc EMS có danh sách phân trang. Chỉ khi thấy khối My Activities có `Rows per page: 10` · `1-2 of 2 results` · `Go to page __ / 1` mới thấy đây là một widget riêng cần kiểm tính nhất quán giữa các màn |
| **S-14** | Sau khi hoàn tất thao tác, hệ thống phải chỉ đường tới bước tiếp theo | (c) | Cùng gốc với `N-10` nhưng ở góc phản hồi: đăng ký xong, **không có gì dẫn người dùng tới vé của họ**. AI sinh được mục "có phản hồi sau hành động" nhưng dừng ở mức "có toast hay không", không nghĩ tới "phản hồi đó có chỉ đường đi tiếp không" |
| **S-15** | Một khái niệm trạng thái chỉ dùng một bộ từ vựng duy nhất | (b) | Lỗi này **chỉ lộ ra khi đối chiếu ba nguồn cạnh nhau**: tài liệu chính thức dùng `Approved/Pending Review/Rejected/Waitlisted`, trang B2 dùng `Registered/Pending/Confirmed/Waitlisted`, thẻ My Activities dùng `Pending review/Student participation/Upcoming`. AI xử lý từng màn hình độc lập nên không có khái niệm "đối chiếu từ vựng chéo giữa giao diện và tài liệu" |
| **S-16** | Chỉ số dashboard phải khớp dữ liệu thật | (c) | Quan sát trực tiếp: Admin Dashboard hiện **Total Events 0, Total Check-ins 0, Attendance Rate 0%, Total Users 0** trong khi hệ thống rõ ràng đang có sự kiện và người dùng. AI không có cách nào biết chỉ số của một hệ thống cụ thể đang sai — đây thuần tuý là kết quả của việc mở trang lên và nhìn |

**Tổng kết:** 21 mục `RV` / 59 mục — **36%** checklist đến từ quan sát trực tiếp trên EMS, không có mục nào trong số đó sinh ra được nếu chỉ mô tả hệ thống bằng lời cho AI.

---

## 4. Vùng đã cân nhắc và CHỦ ĐỘNG loại bỏ

> Loại bỏ có lý do cũng là một hành động review. Đề nêu RTL và dark mode như ví dụ những vùng AI hay bỏ sót — nhóm đã kiểm và kết luận không áp dụng, thay vì thêm mục sẽ N/A với cả 5 thành viên.

| Vùng | Quyết định | Lý do |
|---|---|---|
| Bố cục RTL | Loại | EMS chỉ hỗ trợ EN và VI, cả hai viết trái-sang-phải. Thêm mục RTL sẽ N/A trên **mọi** màn hình của **mọi** thành viên |
| Dark mode | Loại *(tạm thời)* | Khảo sát 05/08/2026 không thấy công tắc chế độ tối. ⚠️ **Cần xác nhận lại ở đợt khảo sát 2** — nếu có thì bổ sung 1 mục về tương phản chế độ tối |
| Autofill của trình duyệt | Loại | Là hành vi của trình duyệt, không phải giao diện của SUT — không kết luận Passed/Failed cho ứng dụng được |
| Real-time update | Gộp vào `S-08` | Phía user không có luồng real-time quan sát được; phía admin chỉ có ở tab Check-in, thuộc phạm vi của một thành viên khác |

---

## 5. Tổng kết định lượng

| Chỉ số | Số lượng |
|---|:--:|
| Số lượt prompt đã dùng | _(TODO — đếm lại sau khi điền §2)_ |
| Số mục AI sinh ra ban đầu | _(TODO)_ |
| Số mục bị loại sau human review (trùng nghĩa / mơ hồ / không kiểm chứng được) | _(TODO)_ |
| Số mục người bổ sung | **21** |
| Số vùng chủ động loại bỏ có lý do | **4** |
| **Tổng mục cuối cùng** | **59** |
