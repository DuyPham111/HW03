# Nội dung sẵn sàng nộp Google Form — 39 lần (gộp từ 41 finding)

> ⚠️ Folder này nằm **ngoài** `23127183_HW03_AI_GUIUsability_EMS_100/` — chỉ để chuẩn bị, không nộp kèm bài.
> Form: https://forms.gle/CJQFQCAXcsDbXDMM9 · Đăng nhập bằng email MSSV `23127183@student.hcmus.edu.vn` trước khi nộp.

## Vì sao chỉ giảm được 41 → 39, không hơn

Chỉ có **2 cặp finding thật sự trùng gốc** (cùng một lỗi, hai nguồn phát hiện độc lập xác nhận lẫn nhau):

| Gộp vào | Gộp từ | Lý do gộp được |
|---|---|---|
| `SV-B2-09` | `US-B2-01` | US-B2-01 tự ghi rõ "trùng khớp finding đã có sẵn từ Task 1B" — cùng 1 hiện tượng (đăng ký xong không có phản hồi) |
| `CL-B2-02` | `CP-B2-01` | CP-B2-01 tự ghi rõ "khớp với S-09/CL-B2-02" — CP-B2-01 là bằng chứng cross-platform bổ sung cho đúng lỗi thiếu nhãn múi giờ đã có |

Các cặp "nghe giống nhau" khác (vd `CL-B2-01` vs `SV-B1-04`, `CL-B1-02` vs `CL-B1-03`) **không gộp** vì chính `04-findings-log.md` đã ghi rõ đó là **quan sát mới/biểu hiện khác**, không phải trùng lặp — gộp chúng sẽ làm sai lệch bản chất finding và rủi ro bị TA coi là che giấu số lượng thật.

**Số dòng trong `04-findings-log.md` vẫn giữ nguyên 41** — không xoá bớt dòng nào trong log, chỉ gộp **hành động nộp form**. Khi TA đối chiếu, bạn giải thích đúng như bảng trên nếu được hỏi.

## Cách dùng file này

Mỗi khối dưới đây = 1 lần mở form, tương ứng đúng 7 câu hỏi theo thứ tự. Copy nguyên khối, dán lần lượt vào từng ô, đính kèm đúng ảnh ghi ở cuối khối, bấm Gửi, rồi **ghi lại giờ Submit thật vào cột "Form-submission timestamp" trong `04-findings-log.md`** (bắt buộc, TA đối chiếu số này).

**Câu 1 (Tốc độ tải trang) và Câu 5 (Điều thích nhất)** — đây là 2 câu hỏi về **cảm nhận chung của bạn**, không gắn với từng lỗi cụ thể, nên **không soạn sẵn** ở đây. Bạn tự trả lời **giống nhau, thật lòng** ở cả 39 lần (vd tốc độ bạn thấy là "Bình thường", điều thích nhất là gì tuỳ bạn) — AI không thể tự bịa cảm nhận cá nhân của bạn.

**Câu 2 (Có gặp lỗi không)** — luôn trả lời **Có**, trừ 3 khối đánh dấu ⭐ SEV-0 (đã xác nhận không phải lỗi — bạn tự cân nhắc trả lời Có kèm giải thích "ban đầu tưởng lỗi, đã tự kiểm lại là không phải" để giữ đúng số lượng khớp log, hoặc hỏi TA cách xử lý 3 dòng sev-0 này trước khi nộp).

---

## SV- (27 khối, khảo sát EMS ban đầu)

### 1. SV-B1-01 — Screen B1, Trang chủ
**Mô tả lỗi:** Carousel SPOTLIGHT EVENT ở vị trí nổi bật nhất trang chủ đang hiển thị một sự kiện mang badge "Ended". Heuristic: N1, N2. Severity 2.
**Mong muốn cải thiện:** Lọc carousel chỉ lấy sự kiện PUBLISHED + UPCOMING/ONGOING.
**Ảnh:** `KS_B1_trang-chu-carousel.png`

### 2. ⭐ SV-B1-02 — Screen B1 (SEV-0, đã xác nhận KHÔNG phải lỗi)
**Mô tả lỗi:** Ban đầu tưởng trạng thái rỗng không nêu lý do và không có nút xoá bộ lọc — đã tự kiểm lại: trạng thái rỗng **có sẵn** câu giải thích và icon xoá bộ lọc, chỉ là quan sát đầu bị sót. Xác nhận icon xoá bộ lọc hoạt động đúng. Severity 0 — không phải lỗi.
**Mong muốn cải thiện:** Không cần sửa gì, hành vi đã đúng.
**Ảnh:** `KS_B1_empty-search.png`

### 3. SV-B1-03 — Screen B1/B2
**Mô tả lỗi:** Trường bắt buộc "Event Title" chứa chuỗi mã nội bộ (vd `23127326_UT_510_15:36`) và được dùng làm tiêu đề chính; tên dễ đọc thật sự nằm ở trường Description, bị đẩy xuống phụ. Xác nhận lặp lại ở cả B1 và My Activities (B4). Heuristic: N2. Severity 2.
**Mong muốn cải thiện:** Không bắt buộc nhập chuỗi mã vào Title; tách riêng một trường "tên hiển thị" đọc được, không dùng Title làm heading khi nó là mã.
**Ảnh:** `KS_B2_su-kien-nguoi-khac.png`

### 4. SV-B1-04 — Screen B1
**Mô tả lỗi:** Nhiều thẻ sự kiện hiện ô ảnh placeholder xám trơn, không có chữ giải thích vì sao không có ảnh. Heuristic: N1, N8. Severity 1.
**Mong muốn cải thiện:** Thay ô xám bằng khối giữ chỗ có tên viết tắt hoặc icon kèm nhãn.
**Ảnh:** `KS_B1_the-su-kien.png`

### 5. SV-B2-01 — Screen B2
**Mô tả lỗi:** Vai trò hết chỗ chỉ báo "Role is full" và dừng ở đó — không mời vào danh sách chờ dù ô đếm Waitlisted tồn tại ngay cạnh. Heuristic: N1, N3. Severity 3.
**Mong muốn cải thiện:** Nếu có cơ chế waitlist thì phải hiện nút "Join waitlist" ngay tại chỗ báo hết chỗ.
**Ảnh:** `KS_B2_workshop-b-het-cho.png`

### 6. SV-B2-02 — Screen B2 + B4
**Mô tả lỗi:** Tên vai trò hiển thị bằng tiếng Việt ("Người dự", "Sinh viên") trong khi giao diện đang ở tiếng Anh. Xác nhận lặp lại ở nhiều sự kiện khác nhau, cả B2 lẫn B4 — vấn đề hệ thống, không phải dữ liệu riêng lẻ. Heuristic: N4. Severity 2.
**Mong muốn cải thiện:** Dữ liệu do người dùng nhập (tên vai trò) cần có bản dịch song ngữ, hoặc nêu rõ quy ước giữ nguyên gốc.
**Ảnh:** `G-12-S2.png`

### 7. ⭐ SV-B2-03 — Screen B2 (SEV-0, đã xác nhận KHÔNG phải lỗi)
**Mô tả lỗi:** Ban đầu tưởng B2 không có nút quay lại khi đã đăng nhập — đã tự kiểm lại: nút "← Back to events" tồn tại thật ở cả hai trạng thái đăng nhập, chỉ là chưa đối chiếu ảnh đã có sẵn. Severity 0 — không phải lỗi.
**Mong muốn cải thiện:** Không cần sửa gì, nút đã tồn tại.
**Ảnh:** `G-06-S2.png`

### 8. SV-B2-04 — Screen B2
**Mô tả lỗi:** Khối vai trò đổi số ô số liệu giữa các sự kiện cùng loại (Workshop B có 4 ô, Workshop C chỉ có 3 ô) — bố cục nhảy khiến người dùng phải đọc lại từ đầu. Heuristic: N4, S1. Severity 1.
**Mong muốn cải thiện:** Luôn hiện đủ số ô, ô không áp dụng thì để giá trị 0 hoặc trạng thái rỗng thay vì biến mất.
**Ảnh:** `KS_B2_workshop-b-het-cho.png`

### 9. SV-B2-05 — Screen B2, màn chặn chưa đăng nhập
**Mô tả lỗi:** Nút trên màn chặn ghi "login" chữ thường, trong khi mọi nút khác dùng Title Case. Heuristic: N4. Severity 1.
**Mong muốn cải thiện:** Thống nhất quy ước viết hoa nhãn nút toàn hệ thống.
**Ảnh:** `KS_B2_chua-dang-nhap.png`

### 10. SV-B2-06 — Screen B2
**Mô tả lỗi:** Một số sự kiện thiếu hẳn tag category và academic context, chỉ còn tag campus — không có cách phân loại sự kiện đó. Heuristic: N1. Severity 1.
**Mong muốn cải thiện:** Bắt buộc chọn category khi tạo sự kiện, hoặc hiện tag "Uncategorised" thay vì bỏ trống.
**Ảnh:** `KS_B2_workshop-b-het-cho.png`

### 11. SV-B4-01 — Screen B4, My Profile
**Mô tả lỗi:** Mã QR check-in không gắn với đăng ký nào — nằm ở nút riêng đầu trang Profile, mã hoá Student ID của tài khoản. Đã chứng minh: tài khoản chưa đăng ký sự kiện nào vẫn có sẵn QR đầy đủ. Heuristic: N1, N3, N6. Severity 3.
**Mong muốn cải thiện:** Hiện mã QR ngay tại thẻ đăng ký trong My Activities và trong thông báo xác nhận đăng ký.
**Ảnh:** `KS_B4_empty-qr.png`

### 12. SV-B4-02 — Screen B4, menu avatar
**Mô tả lỗi:** Email trong menu avatar bị cắt cụt thành "23127183@student.hcmus.edu..." dù vùng hiển thị vẫn còn chỗ trống. Heuristic: N1, S8. Severity 1.
**Mong muốn cải thiện:** Nới chiều rộng menu, hoặc cắt ở phần domain thay vì cắt cụt cuối chuỗi.
**Ảnh:** `profile-1.png`

### 13. SV-B4-03 — B2 + B4 + tài liệu
**Mô tả lỗi:** B2 tự mâu thuẫn với chính nó: badge tiêu đề khối Registration roles ghi "Pending review", nhưng ô đếm ngay bên dưới lại ghi "Pending" (khác chữ). B4 thực ra khớp tài liệu chính thức hơn B2. Heuristic: N4, S1. Severity 2.
**Mong muốn cải thiện:** Đổi nhãn 4 ô đếm ở B2 sang đúng thuật ngữ tài liệu (Approved/Pending Review/Rejected/Waitlisted).
**Ảnh:** `profile-2.png`

### 14. SV-B4-04 — Screen B4, mã QR
**Mô tả lỗi:** Mã QR cố định theo Student ID, không đổi theo sự kiện và không đổi theo thời gian — ai chụp lại được màn hình QR là check-in hộ được ở mọi sự kiện. Heuristic: N5 (phạm vi bảo mật). Severity 3.
**Mong muốn cải thiện:** Sinh mã QR theo từng đăng ký, có thời hạn ngắn và chỉ hợp lệ trong khung giờ check-in đúng sự kiện.
**Ảnh:** `check-in-profile.png`

### 15. SV-ADM-01 — Admin, Create Event
**Mô tả lỗi:** Ô Attachments ghi đúng một câu "Supported any file format." và không nêu giới hạn dung lượng hay số lượng file trước khi chọn. Heuristic: N5, P3. Severity 2.
**Mong muốn cải thiện:** Ghi rõ dung lượng tối đa mỗi file, số file tối đa và danh sách định dạng ngay cạnh ô chọn.
**Ảnh:** `admin-2.png`

### 16. SV-ADM-02 — Admin, Dashboard
**Mô tả lỗi:** Cả 4 thẻ KPI đều bằng 0 (Total Events, Total Check-ins, Attendance Rate, Total Users) trong khi badge Support requests cùng màn hình hiện 17, và hệ thống rõ ràng đang có dữ liệu thật. Heuristic: N1. Severity 3.
**Mong muốn cải thiện:** Nối 4 chỉ số vào dữ liệu thật; nếu chưa có API thì hiện "chưa có dữ liệu" thay vì số 0 gây hiểu nhầm.
**Ảnh:** `admin-1.png`

### 17. SV-ADM-03 — Admin, Create Event (giao diện tiếng Việt)
**Mô tả lỗi:** Hai trường Check-in Open/Close bị dịch sang tiếng Việt theo nghĩa nhận phòng khách sạn ("Quầy lễ tân đã mở cửa", "Đóng cửa nhận phòng"), không đoán được là giờ check-in sự kiện. Heuristic: N2, N4. Severity 3.
**Mong muốn cải thiện:** Dịch lại thành "Thời gian mở/đóng check-in"; rà toàn bộ chuỗi VI gốc "check-in" vì khả năng cao cùng lỗi máy dịch.
**Ảnh:** `KS_ADM_val-01.png`

### 18. SV-ADM-04 — Admin, Create Event
**Mô tả lỗi:** Thông báo lỗi tự mâu thuẫn: "Check-in close date must be after check-in close date" — so sánh một trường với chính nó. Heuristic: N9. Severity 3.
**Mong muốn cải thiện:** Sửa thành "...must be after check-in open date".
**Ảnh:** `KS_ADM_val-04_loi-sau-publish.png`

### 19. SV-ADM-05 — Admin, Create Event
**Mô tả lỗi:** Cả 3 cặp trường thời gian đều nhận giá trị vô lý mà không báo gì lúc nhập; lỗi chỉ hiện sau khi bấm Publish. Heuristic: N5, P3. Severity 2.
**Mong muốn cải thiện:** Đặt min cho ô kết thúc theo giá trị ô bắt đầu, validate ngay khi rời ô thay vì dồn tới lúc submit.
**Ảnh:** `KS_ADM_val-02_checkin-pair.png`

### 20. SV-B2-07 — Screen B2, hộp thoại Cancel registration
**Mô tả lỗi:** Hộp thoại xác nhận có hai nút đều bắt đầu bằng chữ "Cancel", không nêu hậu quả, trong khi thao tác không hoàn tác được. Heuristic: N4, N5, S3. Severity 3.
**Mong muốn cải thiện:** Đổi nút đóng thành "Keep my registration", nút huỷ thành "Yes, cancel it"; thêm câu nêu hậu quả rõ ràng.
**Ảnh:** `KS_B2_cancel-02_dialog.png`

### 21. ⭐ SV-B2-08 — Screen B2 (SEV-0, đã xác nhận KHÔNG phải lỗi)
**Mô tả lỗi:** Sau khi huỷ đăng ký, khối Registration roles trở về đúng trạng thái như chưa từng đăng ký và đăng ký lại được bình thường — đã kiểm chứng, không phải bug. Severity 0.
**Mong muốn cải thiện:** Không cần sửa, hành vi đúng như kỳ vọng.
**Ảnh:** `KS_B2_cancel-03_sau-huy.png`

### 22. SV-B4-05 — B2 vs B4, hai màn hình mâu thuẫn
**Mô tả lỗi:** Cùng một đăng ký đã huỷ nhưng B2 xoá sạch mọi dấu vết, còn My Activities ở B4 vẫn giữ nguyên thẻ sự kiện kèm badge "Cancelled". Heuristic: S1, N1. Severity 2.
**Mong muốn cải thiện:** Thống nhất một cách hiển thị — cả hai đều giữ bản ghi Cancelled, hoặc cả hai đều xoá.
**Ảnh:** `KS_B4_sau-huy.png`

### 23. SV-B2-09 — Screen B2, khối đăng ký *(gộp thêm US-B2-01)*
**Mô tả lỗi:** Đăng ký thành công không có toast, không thông báo, không hướng dẫn bước tiếp theo — trang đứng yên, chỉ có badge "Pending review" xuất hiện. **Xác nhận độc lập bởi 2/5 người dùng thật ở Task 2** (P2: "Tôi nghi ngờ sự kiện đã được đưa lên chưa"; P4: "Nghi ngờ khi nút đăng kí bị disable") — hai nguồn khác nhau (checklist + user testing) cùng chỉ ra một lỗ hổng. Heuristic: N1, S4. Severity 3.
**Mong muốn cải thiện:** Hiện thông báo xác nhận có liên kết trực tiếp tới mã QR check-in và nêu rõ bước tiếp theo; thêm toast xác nhận ngay sau khi đăng ký; giải thích lý do khi nút bị khoá.
**Ảnh:** `KS_B3_05_sau-submit.png`

### 24. SV-B2-10 — Screen B2, khối đăng ký
**Mô tả lỗi:** Câu "Please tick a role before submitting registration." hiển thị bằng màu chữ lỗi ngay khi vừa mở trang, trước khi người dùng làm gì sai. Heuristic: N1, N9. Severity 1.
**Mong muốn cải thiện:** Trình bày dưới dạng chú thích trung tính (xám) khi chưa thao tác, chỉ chuyển màu lỗi sau khi bấm submit hụt.
**Ảnh:** `KS_B3_02_form-rong.png`

### 25. SV-B4-06 — Screen B4, My Profile
**Mô tả lỗi:** Tên hiển thị tài khoản là một địa chỉ email, khác với email ghi ở ô EMAIL bên dưới. Đã xác nhận: do người dùng tự nhập tay, không phải hệ thống tự sinh. Heuristic: N2, N4. Severity 1.
**Mong muốn cải thiện:** Cảnh báo nhẹ khi người dùng nhập chuỗi giống định dạng email vào ô Tên.
**Ảnh:** `KS_B4_empty.png`

### 26. SV-NOTIF-01 — Chuông thông báo (mọi màn hình)
**Mô tả lỗi:** Thông báo hiển thị tiếng Việt trong khi giao diện đang tiếng Anh ("Đăng ký sự kiện được phê duyệt"), kèm phơi thẳng email admin và nhãn thời gian sai ngữ pháp ("23 second ago"). Heuristic: N4. Severity 1.
**Mong muốn cải thiện:** Dịch chuỗi thông báo theo ngôn ngữ đang chọn; thay email admin bằng vai trò; sửa số nhiều cho nhãn thời gian.
**Ảnh:** `KS_NOTIF_approved.png`

### 27. SV-UG-01 — User guide (mọi màn hình)
**Mô tả lỗi:** Tài liệu hướng dẫn chỉ có tiếng Việt dù giao diện đang tiếng Anh; không có chỗ nào nói mã QR check-in nằm ở đâu. Heuristic: N10, S2. Severity 2.
**Mong muốn cải thiện:** Dịch tài liệu theo ngôn ngữ đang chọn; bổ sung mục nói rõ vị trí mã QR check-in.
**Ảnh:** `KS_UG_01.png`

---

## CL- (11 khối, Task 1B — chạy checklist thật)

### 28. CL-B1-01 — Screen B1, thẻ sự kiện
**Mô tả lỗi:** Giá trị rỗng dùng hai ký hiệu khác nhau: B1 hiện "Location: Updating" cho một sự kiện, nhưng cùng sự kiện đó mở ở B2/B4 lại hiện "-". Chữ "Updating" gây hiểu lầm là đang cập nhật, thực chất là không có dữ liệu. Heuristic: N4, N2. Severity 2.
**Mong muốn cải thiện:** Thống nhất một ký hiệu duy nhất (-) cho mọi giá trị rỗng toàn hệ thống.
**Ảnh:** `G-09-S1.png`

### 29. CL-B1-02 — Screen B1, danh sách sự kiện
**Mô tả lỗi:** Bấm Back của trình duyệt sau khi mở một sự kiện không giữ nguyên bộ lọc đã áp và không giữ vị trí cuộn — quay về B1 nhưng danh sách hiện lại toàn bộ, trang cuộn về đầu. Heuristic: N3, N4. Severity 2.
**Mong muốn cải thiện:** Lưu trạng thái filter vào URL hoặc session, khôi phục đúng khi quay lại bằng Back.
**Ảnh:** `N-06-S1-before.png`

### 30. CL-B1-04 — Screen B1 + B2, nút Save
**Mô tả lỗi:** Đỏ dùng cho hành động trung tính (lưu/bookmark) — nút Save trên B1 và Save event trên B2 đều viền đỏ, cùng tông với nút Cancel registration (không hoàn tác) và cảnh báo lỗi. Heuristic: N4. Severity 1.
**Mong muốn cải thiện:** Đổi màu nút Save sang màu trung tính, chỉ giữ đỏ cho hành động phá huỷ và lỗi thật.
**Ảnh:** `G-06-S2.png`

### 31. CL-B1-03 — Screen B1 + B4, bộ lọc
**Mô tả lỗi:** URL không phản ánh bộ lọc/tìm kiếm đang áp dụng ở B1 lẫn B4 — không share/bookmark được kết quả đã lọc, reload là mất hết. Hệ quả kéo theo cả Back của trình duyệt cũng không khôi phục được bộ lọc trên B4. Heuristic: N4, S7. Severity 2.
**Mong muốn cải thiện:** Đưa trạng thái filter vào query string ở cả hai trang.
**Ảnh:** `N-05-S1.png`

### 32. CL-B2-02 — Toàn hệ thống, hiển thị ngày giờ *(gộp thêm CP-B2-01)*
**Mô tả lỗi:** Không có múi giờ hiển thị ở bất kỳ đâu trong hệ thống — mọi ngày giờ đều đúng định dạng dd/MM/yyyy HH:mm nhưng không ghi rõ theo múi nào. **Xác nhận bằng bằng chứng cross-platform ở Task 3:** cùng 1 sự kiện hiện giờ Event/Registration/Check-in lệch tới 5–7 tiếng giữa 5 môi trường desktop và 2 thiết bị Android thật (nguyên nhân: đồng hồ thiết bị Android không đặt đúng múi giờ Việt Nam) — chứng minh lỗi thiếu nhãn múi giờ này **thực sự gây sai lệch nội dung**, không chỉ là thiếu tiện lợi. Heuristic: N2, N9. Severity 2.
**Mong muốn cải thiện:** Cố định hiển thị theo 1 múi giờ server (UTC+7) cho mọi client, hoặc ghi rõ múi giờ cạnh mỗi mốc thời gian.
**Ảnh:** `B2_firefox_android_tablet.png` (evidence/task3/)

### 33. CL-B4-04 — Screen B2 (Register) + B4 (Filters, Export)
**Mô tả lỗi:** Mất mạng không được báo — Export ở B4 thất bại hoàn toàn không thông báo; Filters (B4) và Register (B2) hiện spinner rồi treo vô thời hạn, không báo thành công cũng không báo lỗi. Heuristic: N1, N9. Severity 2.
**Mong muốn cải thiện:** Bắt sự kiện offline của trình duyệt để hiện banner cảnh báo; đặt timeout cho mọi request.
**Ảnh:** *(chưa có ảnh riêng, mô tả bằng lời)*

### 34. CL-B4-03 — Screen B4, My Profile, menu chính
**Mô tả lỗi:** Khi đứng ở trang My Profile, không có mục nào trên menu chính được tô nổi để chỉ vị trí hiện tại. Heuristic: N1. Severity 1.
**Mong muốn cải thiện:** Thêm chỉ báo trạng thái hiện tại cho avatar/menu người dùng khi đang ở nhóm trang tài khoản.
**Ảnh:** `N-01-S3.png`

### 35. CL-B2-03 — Screen B2, luồng đăng nhập bắt buộc
**Mô tả lỗi:** Sau khi đăng nhập xong (từ deep link một sự kiện không công khai), hệ thống KHÔNG đưa người dùng quay lại đúng sự kiện họ vừa yêu cầu — bị đẩy về trang chủ. Heuristic: N3. Severity 2.
**Mong muốn cải thiện:** Lưu URL đích trước khi chuyển hướng sang màn đăng nhập, điều hướng lại đúng URL đó ngay sau khi xác thực.
**Ảnh:** *(chưa có ảnh riêng, mô tả bằng lời)*

### 36. CL-B2-01 — Screen B2, banner sự kiện
**Mô tả lỗi:** Banner ảnh của một sự kiện không tải được, chỉ hiện icon ảnh chung chung không kèm chữ giải thích — quan sát mới trên B2 (khác biểu hiện với lỗi ảnh vỡ đã ghi ở B1). Heuristic: N1, N8. Severity 1.
**Mong muốn cải thiện:** Thay icon chung chung bằng khối giữ chỗ có nhãn chữ, áp dụng đồng bộ mọi nơi hiển thị ảnh sự kiện.
**Ảnh:** `G-06-S2.png`

### 37. CL-B4-01 — Screen B4, My Activities, khối Filters
**Mô tả lỗi:** Lọc theo Start Date Range không thực sự lọc dữ liệu — đặt khoảng ngày không trùng sự kiện nào nhưng danh sách vẫn hiện đủ. Heuristic: N1, N4. Severity 3.
**Mong muốn cải thiện:** Sửa logic áp dụng điều kiện Start Date Range vào truy vấn danh sách hoạt động.
**Ảnh:** `G-07-S3.png`

### 38. CL-B4-02 — Screen B4, My Activities, trạng thái rỗng
**Mô tả lỗi:** Khi Search ra 0 kết quả, trạng thái rỗng chỉ ghi "No activities found" — không nêu lý do, khác với B1 cùng tình huống có nêu lý do. Heuristic: N1, S1. Severity 1.
**Mong muốn cải thiện:** Thêm câu nêu lý do tương tự B1, đặt nút xoá bộ lọc ngay trong khối thông báo rỗng.
**Ảnh:** `G-07-S3-2.png`

---

## US- (1 khối còn lại — US-B2-01 đã gộp vào SV-B2-09 ở trên)

### 39. US-B2-02 — Screen B2, nút quay lại (mobile)
**Mô tả lỗi:** Nút "Back to events" tồn tại thật (đã Passed ở checklist) nhưng participant dùng iPhone không tìm ra, phải tự cuộn lên đầu trang — khoảng cách giữa "nút có tồn tại" và "nút được nhận ra" trên màn hình nhỏ. Xác nhận từ người dùng thật: "Không. Phải kiếm nút quay lại. Kéo lên đầu trang. Khó khăn." Heuristic: N3. Severity 2.
**Mong muốn cải thiện:** Tăng độ nổi bật nút trên viewport hẹp (dưới 480px), cân nhắc ghim cố định khi cuộn.
**Ảnh:** *(dùng ảnh chụp màn hình mobile nếu có, hoặc mô tả bằng lời — nguồn là transcript P3, không phải ảnh)*

---

## Sau khi nộp xong cả 39 lần

- [ ] Đã ghi giờ Submit thật vào cột "Form-submission timestamp" cho cả 41 dòng trong `04-findings-log.md` (2 dòng `US-B2-01`/`CP-B2-01` ghi **cùng giờ** với dòng đã gộp — `SV-B2-09`/`CL-B2-02` — kèm chú thích "nộp gộp cùng lần với SV-B2-09" để TA hiểu vì sao trùng giờ)
- [ ] Đếm lại: số ô "Form-submission timestamp" đã điền = 41 (không phải 39 — vì 2 dòng gộp vẫn cần đánh dấu đã nộp, chỉ là trùng thời điểm)
- [ ] Nếu bị TA hỏi vì sao 2 dòng trùng giờ nộp, giải thích đúng theo bảng lý do gộp ở đầu file này
