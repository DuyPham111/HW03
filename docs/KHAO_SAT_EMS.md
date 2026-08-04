# PHIẾU KHẢO SÁT EMS — điền trực tiếp vào file này

**Người khảo sát:** Phạm Vũ Ngọc Duy (23127183) · **Ngày:** _(TODO)_ · **Giờ bắt đầu:** _(TODO)_
**SUT:** https://prod-dev.ems-fitus.cloud
**Mục đích:** tạo **danh mục widget thật** làm input cho prompt sinh checklist (Task 1A) + **dựng dữ liệu thử** cho Task 1B/2/3.

> **Cách dùng:** mở file này ở một cửa sổ, EMS ở cửa sổ kia. Đi từ Phần 0 → Phần 6 theo đúng thứ tự. Chỗ nào có ô trống thì điền, chỗ nào có `[ ]` thì tick.
> **Tổng thời gian:** ~50 phút. Đừng làm tắt Phần 5 — đó là thứ duy nhất bạn thực sự dán vào AI.

---

## PHẦN 0 · Chuẩn bị (5 phút)

- [ ] Mở EMS, xác nhận trang chủ load được
- [ ] **Đăng ký một tài khoản sinh viên riêng** cho mình (không dùng chung với nhóm) — ghi lại:
  - Email tài khoản user: `________________`
  - Đây cũng là tài khoản dùng chạy Task 1B và Task 3
- [ ] Đăng nhập được bằng tài khoản admin `admin@gmail.com` / `Admin@123`
- [ ] Tạo thư mục ảnh: `docs/khao-sat/`
- [ ] Mở sẵn 2 tab: một tab **user** (dùng cửa sổ thường), một tab **admin** (dùng **cửa sổ ẩn danh** để không phải đăng xuất qua lại)

### Quy ước chụp ảnh

**Có, phải chụp** — nhưng chụp cho mình dùng, không phải để nộp.

| Loại ảnh | Đặt tên | Lưu ở đâu | Dùng làm gì |
|---|---|---|---|
| Ảnh toàn màn hình mỗi màn hình khảo sát | `KS_B2_tong-quan.png` | `docs/khao-sat/` | Để viết item checklist mà không phải mở lại EMS |
| Ảnh chi tiết một widget lạ | `KS_B2_nut-dang-ky-waitlist.png` | `docs/khao-sat/` | Nguyên liệu mô tả widget cho AI |
| Ảnh chỗ **nghi ngờ có lỗi** | `SV-001.png` | `23127183_HW03_AI_GUIUsability_EMS_100/evidence/survey/` | Bằng chứng finding — dữ liệu dev có thể reset, chụp ngay |

> ⚠️ **Ảnh khảo sát KHÔNG phải bằng chứng Task 1B.** Task 1B đòi ảnh chụp **trong lúc chạy checklist**. Chỗ nào khảo sát thấy nghi ngờ thì lúc chạy 1B phải chụp lại một lần nữa cho đúng ngữ cảnh.

---

## PHẦN 1 · Dựng 4 sự kiện dữ liệu thử (20 phút) — làm bằng tài khoản ADMIN

Không có bộ này thì B2/B3/B4 chỉ lộ được một trạng thái duy nhất, checklist sẽ không kiểm được gì.

| # | Tên sự kiện | Cấu hình cần đặt | Làm lộ ra cái gì | Đã dựng |
|---|---|---|---|:--:|
| 1 | `[23127183] Workshop A — con cho` | PUBLISHED · UPCOMING · mở đăng ký student · Max Slots = 50 · **bật Allow Additional Role** | Luồng đăng ký chính; B3 có thêm phần chọn vai trò phụ | [ ] |
| 2 | `[23127183] Workshop B — het cho` | PUBLISHED · UPCOMING · Max Slots = **1** · **bật Waitlist** · rồi tự đăng ký bằng tài khoản user cho đầy | Trạng thái "vào danh sách chờ" trên B2 + badge waitlist trên B4 | [ ] |
| 3 | `[23127183] Workshop C — dong dang ky` | PUBLISHED · thời gian đóng đăng ký **đã qua** nhưng sự kiện chưa diễn ra | Nút Đăng ký bị vô hiệu hoá trên B2 | [ ] |
| 4 | `[23127183] Workshop D — da ket thuc` | PUBLISHED · thời gian đã qua hoàn toàn (`ENDED`) | Badge trạng thái trên B4; màn đánh giá sao B5 | [ ] |

**Trong lúc dựng, ghi lại luôn:**

| Câu hỏi | Trả lời |
|---|---|
| Form tạo sự kiện có những trường bắt buộc nào? | |
| Bật/tắt công tắc nào thì form hiện thêm trường? | |
| Hệ thống có chặn khi thời gian không hợp lệ không? Báo lỗi ra sao? | |
| Có bao nhiêu trạng thái sự kiện (DRAFT / PUBLISHED / …)? Mỗi trạng thái màu gì? | |

- [ ] Chụp `KS_ADMIN_form-tao-su-kien.png`

---

## PHẦN 2 · Khảo sát phía USER (25 phút) — dùng tài khoản sinh viên của bạn

> Đây là phần quan trọng nhất vì B2/B3/B4 là bộ màn hình bạn sẽ chấm điểm.
> **Cách làm mỗi màn:** tick từng dòng `[ ]`, vừa làm vừa điền vào bảng ngay bên dưới.

### 2.1 · B1 — Trang chủ *(không thuộc phạm vi chấm, nhưng là đường vào)*

- [ ] Vào trang chủ **khi chưa đăng nhập** → chụp `KS_B1_chua-dang-nhap.png`
- [ ] Đợi tại chỗ 30 giây, xem carousel có tự xoay không, bao nhiêu giây một lần
- [ ] Thử bộ lọc danh mục và ô tìm kiếm
- [ ] Tìm một từ khoá chắc chắn không có kết quả → xem **empty state** hiện gì → chụp `KS_B1_empty-search.png`

| Câu hỏi | Trả lời |
|---|---|
| Carousel có tự xoay không? Bao nhiêu giây/lần? | |
| Trang chủ có những khối nào (kể từ trên xuống)? | |
| Bộ lọc/tìm kiếm: có bao nhiêu control, tên là gì? | |
| Khi không có kết quả, hệ thống hiện gì? (chữ gì, có gợi ý hành động không) | |
| Thẻ sự kiện hiển thị những thông tin gì? | |

### 2.2 · B2 — Trang chi tiết sự kiện ⭐ MÀN CHẤM ĐIỂM

Phải xem **4 lần**, mỗi lần một trạng thái khác nhau:

- [ ] **Lần 1 — chưa đăng nhập**, mở Workshop A → nút Đăng ký hiện gì? → chụp `KS_B2_chua-dang-nhap.png`
- [ ] **Lần 2 — đã đăng nhập**, mở Workshop A (còn chỗ) → chụp `KS_B2_con-cho.png`
- [ ] **Lần 3 —** mở Workshop B (hết chỗ + waitlist) → chụp `KS_B2_waitlist.png`
- [ ] **Lần 4 —** mở Workshop C (đã đóng đăng ký) → chụp `KS_B2_dong-dang-ky.png`
- [ ] Copy URL của trang này, mở ở **cửa sổ ẩn danh** → có vào thẳng đúng sự kiện không, hay bị đá về trang chủ?
- [ ] Bấm nút **Back** của trình duyệt → về đúng chỗ cũ không?

| Câu hỏi | Trả lời |
|---|---|
| Các khối nội dung trên trang, kể từ trên xuống | |
| Nút hành động chính tên chính xác là gì? | |
| **Nhãn nút đổi thế nào ở 4 trạng thái?** (chưa đăng nhập / còn chỗ / hết chỗ / đã đóng) | |
| Khi hết chỗ, hệ thống có nói rõ là "vào danh sách chờ" không? Câu chữ nguyên văn: | |
| Có hiển thị số chỗ còn lại không? Dạng số hay thanh tiến trình? | |
| Thông tin thời gian hiển thị theo định dạng nào? (dd/mm hay mm/dd, có múi giờ không) | |
| Có breadcrumb / nút quay lại danh sách không? | |
| Deep link khi chưa đăng nhập: vào thẳng hay bị đá về trang chủ? | |

### 2.3 · B3 — Form đăng ký ⭐ MÀN CHẤM ĐIỂM

Đây là màn **duy nhất** có form ở phía user → gánh gần hết nhóm item IA-02. Soi kỹ nhất ở đây.

- [ ] Mở form từ Workshop A → chụp `KS_B3_form-trong.png`
- [ ] **Bấm Submit khi chưa điền gì** → lỗi hiện ở đâu? chụp `KS_B3_loi-bo-trong.png`
- [ ] Điền một nửa rồi bấm Submit → **dữ liệu đã nhập có bị xoá trắng không?**
- [ ] Bấm **Tab** liên tục từ đầu form → thứ tự nhảy có hợp lý không? có nhìn thấy viền focus không?
- [ ] Nhấn **Esc** khi form/modal đang mở → có đóng không?
- [ ] Hoàn tất đăng ký một lần → chụp `KS_B3_xac-nhan.png` (thông báo thành công)

| Câu hỏi | Trả lời |
|---|---|
| Form có bao nhiêu trường? Kể tên từng trường | |
| Trường nào bắt buộc? Đánh dấu bắt buộc bằng gì (dấu `*`, chữ, màu)? | |
| Chọn vai trò là dạng gì? (dropdown / radio / checkbox) | |
| Có phần "vai trò phụ" không? Bật lên thì hiện thêm gì? | |
| **Thông báo lỗi hiện ở ĐÂU?** (cạnh trường / trên nút submit / toast góc màn hình) | |
| Câu chữ thông báo lỗi nguyên văn: | |
| Sau khi validate fail, dữ liệu đã nhập **còn giữ** không? | |
| Có bước xác nhận trước khi gửi không? | |
| Sau khi gửi thành công, hệ thống làm gì? (toast / chuyển trang / cả hai) | |
| Nhấn Tab: thứ tự focus có hợp lý không? Có thấy viền focus không? | |
| Nhấn Esc: modal có đóng không? | |

### 2.4 · B4 — My Registrations + vé QR ⭐ MÀN CHẤM ĐIỂM

- [ ] **Trước khi đăng ký gì cả**, mở màn này bằng một tài khoản trắng → **empty state** hiện gì? → chụp `KS_B4_empty.png`
- [ ] Sau khi đã đăng ký Workshop A và B → chụp `KS_B4_danh-sach.png`
- [ ] Mở chi tiết một đăng ký → tìm mã QR/barcode → chụp `KS_B4_ve-qr.png`
- [ ] So sánh badge trạng thái của Workshop A (đã đăng ký) vs Workshop B (waitlist) — **màu và chữ khác nhau thế nào?**
- [ ] Thử **thu nhỏ cửa sổ xuống ~375px** → mã QR có bị méo/cắt không? → chụp `KS_B4_mobile.png`

| Câu hỏi | Trả lời |
|---|---|
| Khi chưa có đăng ký nào, màn hình hiện gì? Có gợi ý hành động tiếp theo không? | |
| Có bao nhiêu trạng thái đăng ký? Kể tên + màu từng cái | |
| Mã check-in là QR hay barcode? Kích thước có đủ lớn để quét không? | |
| Có tải/lưu vé về được không? | |
| Có huỷ đăng ký được không? Có dialog xác nhận không? Nội dung dialog: | |
| Danh sách có phân tab/lọc theo trạng thái không? | |
| Ở bề rộng 375px, layout có vỡ không? | |

### 2.5 · B5 — Đánh giá sao *(chỉ khảo sát nhanh, không thuộc phạm vi chấm)*

- [ ] Mở Workshop D (đã ENDED) → có hiện phần đánh giá không? → chụp `KS_B5_danh-gia.png`

| Câu hỏi | Trả lời |
|---|---|
| Chấm sao bằng widget gì? Có cho nhập nhận xét không? | |
| Đánh giá rồi có sửa lại được không? | |

---

## PHẦN 3 · Khảo sát phía ADMIN (15 phút) — chỉ để lấy DANH MỤC WIDGET

> Bạn **không** chấm điểm phía admin. Mục đích duy nhất ở đây: checklist là **sản phẩm chung của cả nhóm**, phải dùng được cho cả 4 kịch bản A/B/C/D. Nếu chỉ khảo sát phía user thì checklist sẽ thiếu hẳn nhóm item về upload, rich-text, kéo-thả — và bạn không giải trình được với nhóm.
> **Chỉ nhìn và ghi, đừng lưu/xoá dữ liệu của người khác.**

| Nơi cần vào | Cần ghi lại widget gì | Ảnh | Xong |
|---|---|---|:--:|
| Dashboard admin | 4 chỉ số KPI tên gì; có biểu đồ không | `KS_ADMIN_dashboard.png` | [ ] |
| Events → danh sách | Bộ lọc trạng thái · badge màu · chấm đỏ thông báo · phân trang | `KS_ADMIN_events-list.png` | [ ] |
| Events → Add Event | **Upload ảnh mấy loại tỉ lệ** · trình soạn rich-text có nút gì · cách chọn ngày giờ | `KS_ADMIN_upload-richtext.png` | [ ] |
| Categories *(hoặc Academic Contexts)* | **Kéo-thả reorder**: dòng đang kéo trông thế nào, các nút khác có bị mờ đi không · icon picker có bao nhiêu icon | `KS_ADMIN_keo-tha.png` | [ ] |
| Users | Các cột của bảng · nút Export · dialog xác nhận khi làm hành động phá huỷ | `KS_ADMIN_users.png` | [ ] |
| Participants của một sự kiện | **Progress bar** · số màu trạng thái · bộ lọc | `KS_ADMIN_participants.png` | [ ] |

| Câu hỏi tổng | Trả lời |
|---|---|
| Toast thông báo hiện ở góc nào? Tự tắt sau bao lâu? | |
| Dialog xác nhận có mấy nút? Nút phá huỷ màu gì? | |
| Có tổng cộng bao nhiêu màu trạng thái khác nhau trên toàn hệ thống? | |

---

## PHẦN 4 · Tám phép thử xuyên suốt (10 phút)

Làm trên **một màn hình bất kỳ trong B2/B3/B4** — đây là nguồn ra nhiều item checklist nhất, và cũng là những vùng AI hay bỏ sót.

| # | Phép thử | Cách làm | Kết quả quan sát |
|---|---|---|---|
| 1 | **Chuyển EN/VI** | Bấm công tắc ngôn ngữ ở header → quét **toàn bộ** màn hình | Còn chữ nào chưa dịch? Kể tên: |
| 2 | **i18n chỗ khuất** | Kiểm cả toast, tooltip, placeholder, nút, thông báo lỗi | |
| 3 | **Ngôn ngữ có được nhớ** | Đổi sang VI → F5 tải lại trang | Còn giữ VI hay quay về EN? |
| 4 | **Text tiếng Việt dài hơn** | Ở chế độ VI, xem nút và nhãn | Có bị cắt chữ / vỡ nút không? |
| 5 | **Zoom 200%** | `Ctrl` + `+` đến 200% | Có vỡ layout / mất nội dung không? |
| 6 | **Bề rộng mobile** | Thu cửa sổ xuống ~375px | Menu có thu gọn không? Có scroll ngang thừa không? |
| 7 | **Mạng chậm** | F12 → Network → Throttling → *Slow 3G* → F5 | Có skeleton/spinner không, hay trắng trang? Layout có nhảy khi dữ liệu về? |
| 8 | **Mã trạng thái nội bộ** | Ở mọi thông báo lỗi/trạng thái | Có chỗ nào hiện thẳng mã kiểu `OUTSIDE_CHECKIN_WINDOW` ra giao diện không? |

---

## PHẦN 5 · DANH MỤC WIDGET — đoạn này dán thẳng vào prompt AI ⭐

> Đây là **sản phẩm chính** của cả buổi khảo sát. Viết lại thành văn xuôi gạch đầu dòng, càng cụ thể càng tốt. Prompt Bước 2 của `TASK1A_LAM_MOT_MINH.md` sẽ dán nguyên khối này vào.

```
Các widget THẬT tôi đã quan sát trên EMS ngày ____:

PHÍA USER
- Trang chủ: [carousel — tự xoay ___ giây/lần] · [bộ lọc danh mục dạng ___]
  · [ô tìm kiếm] · [thẻ sự kiện hiển thị ___]
- Trang chi tiết sự kiện: [banner tỉ lệ ___] · [khối lịch trình] · [nút Đăng ký đổi nhãn
  theo ___ trạng thái: ___] · [thông báo waitlist với câu chữ ___] · [hiển thị số chỗ dạng ___]
- Form đăng ký: [___ trường, gồm ___] · [chọn vai trò dạng ___] · [vai trò phụ bật lên hiện ___]
  · [thông báo lỗi hiện ở ___] · [bước xác nhận ___]
- My Registrations: [___ trạng thái, màu ___] · [empty state hiện ___] · [mã ___ kích thước ___]
  · [dialog huỷ đăng ký ___]
- Toàn cục: [công tắc EN/VI ở header] · [toast ở góc ___, tự tắt sau ___ giây]

PHÍA ADMIN (để checklist dùng được cho cả nhóm)
- [Upload ảnh ___ loại tỉ lệ: ___] · [RichTextEditor với các nút ___]
- [Kéo-thả reorder: dòng đang kéo ___, các nút khác ___] · [icon picker ~___ icon]
- [Progress bar duyệt đăng ký] · [___ màu trạng thái participant] · [export Excel]
- [Dialog xác nhận ___ nút, nút phá huỷ màu ___]

HÀNH VI ĐẶC THÙ ĐÁNG CHÚ Ý
- [Ngôn ngữ ___ được nhớ sau khi tải lại trang]
- [Ở mạng chậm hệ thống hiện ___]
- [Ở 375px ___]
- [___ những gì bạn thấy lạ]
```

---

## PHẦN 6 · Quan sát nghi vấn — có thể thành finding

> Chưa cần kết luận đúng/sai. Chỉ ghi lại + chụp ảnh. Lúc chạy Task 1B sẽ kiểm chứng lại đàng hoàng rồi mới đưa vào findings log.

| ID | Màn hình | Quan sát | Nghi ngờ vi phạm | Ảnh |
|---|---|---|---|---|
| SV-001 | | | | `evidence/survey/SV-001.png` |
| SV-002 | | | | |
| SV-003 | | | | |

---

## Đóng khảo sát

- [ ] Phần 1: đã dựng đủ 4 sự kiện dữ liệu thử
- [ ] Phần 2: đã đi qua B1–B5, mọi bảng đã điền
- [ ] Phần 3: đã ghi widget của 6 nơi phía admin
- [ ] Phần 4: đã chạy đủ 8 phép thử
- [ ] **Phần 5: khối danh mục widget đã viết xong, không còn `___`** ← nếu còn chỗ trống thì quay lại EMS xem tiếp
- [ ] Phần 6: mọi quan sát nghi vấn đều đã chụp ảnh
- [ ] Ảnh khảo sát nằm ở `docs/khao-sat/`, ảnh nghi vấn nằm ở `evidence/survey/`
- [ ] Điền số liệu vào `00-main-report.md` mục 0
- **Commit:** `docs(task1a): add EMS survey notes and widget inventory`

**Giờ kết thúc:** _(TODO)_ · **Tổng thời gian:** _(TODO)_
