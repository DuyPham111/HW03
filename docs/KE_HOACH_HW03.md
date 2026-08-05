# KẾ HOẠCH LÀM HW03 — GUI & Usability Testing trên EMS

**Sinh viên:** Phạm Vũ Ngọc Duy — **MSSV:** 23127183
**Môn:** CS423 / CSC15003 — Kiểm thử phần mềm (AI-First 2026)
**SUT:** https://prod-dev.ems-fitus.cloud
**Tài khoản Admin:** `admin@gmail.com` / `Admin@123`
**Nhóm Zalo hỗ trợ:** https://zalo.me/g/rupogxlykt3yxd3snodl
**Google Form nộp finding:** https://forms.gle/CJQFQCAXcsDbXDMM9
**Thời lượng đề ra:** 10 giờ · **Deadline:** xem link nộp trên Moodle

> File này là **bảng điều khiển** của cả bài (làm gì, theo thứ tự nào, khi nào). Cần biết **chi tiết từng hạng mục phải làm gì và nộp gì** → xem [`HUONG_DAN_CHI_TIET_TUNG_PHAN.md`](HUONG_DAN_CHI_TIET_TUNG_PHAN.md).
> Mỗi lần làm xong một việc thì tick `[x]` và commit.
> Thư mục `docs/` nằm **ngoài** thư mục nộp — là tài liệu nội bộ để đọc/hiểu đề, không đi vào file zip.

---

## 0. Bốn quyết định — ĐÃ CHỐT

| # | Quyết định | Trạng thái | Nội dung |
|---|---|---|---|
| D1 | Chọn kịch bản A / B / C / D | ✅ CHỐT | **Kịch bản B — User đăng ký tham dự sự kiện** |
| D2 | Chọn ≥ 3 màn hình | ✅ CHỐT | **B2 Trang chi tiết sự kiện · B3 Form đăng ký · B4 My Profile — QR Code + My Activities** (nửa *registration core* của Pool B) |
| D3 | Nhóm 5 người + phân chia | ⬜ CHỜ NHÓM XÁC NHẬN | Nhóm 5 người ⇒ **một kịch bản bị đôi**, hai người đó phải chọn **bộ màn hình rời nhau** — xem D3 bên dưới |
| D4 | Email MSSV overlay ảnh | ⚠️ **MỞ LẠI** | Đang ghi `23127183@student.hcmus.edu.vn`, nhưng email đăng nhập EMS là `23127183@student.hcmus.edu.vn`. Đề đòi mẫu `MSSV@....edu.vn` — chỉ cái thứ hai khớp. **Hỏi TA rồi chốt**, xem `KHAO_SAT_EMS.md` mục ⚠️ 2 |

**SUT đã đổi link:** link ngrok cũ đã chết, link hiện hành là **https://prod-dev.ems-fitus.cloud** (đã cập nhật trong toàn bộ file). Đây là môi trường dev từ xa nên **dữ liệu vẫn có thể bị reset** — nguyên tắc "chụp ảnh liền tay" giữ nguyên.

---

### D1 — Vì sao chọn B

Cách đọc bảng: hạng mục nặng điểm nhất **và** rủi ro nhất của HW03 là **Task 2 (25đ) — 5 người thật ngoài lớp, TA có quyền gọi xác minh 2 người**. Kịch bản nào làm Task 2 khả thi thì kịch bản đó thắng, vì Task 1B và Task 3 đều có thể bù bằng công sức, còn Task 2 hỏng là mất trắng 25 điểm.

| Kịch bản | Task 2 (25đ) — tuyển & chạy 5 người | Task 1B (15đ) — độ dày widget | Task 3 (25đ) — tái lập trên mọi thiết bị |
|---|---|---|---|
| **B — User đăng ký sự kiện** ✅ | **Dễ nhất.** Tác vụ "đăng ký workshop, xem xác nhận" ai cũng hiểu ngay; mỗi người **tự tạo tài khoản Guest riêng** (không cần tài khoản HCMUS) ⇒ 5 phiên không đụng dữ liệu nhau | Mỏng hơn admin (không upload / rich-text / drag-drop) — bù bằng cách chọn màn nhiều **trạng thái** và ghi rõ lý do N/A | Trung bình: cả B2/B3/B4 đều cần đăng nhập (đã kiểm 05/08/2026) ⇒ phải đăng nhập lại ở từng ô BrowserStack. Bù lại không cần dựng trạng thái phức tạp như A5 Check-in |
| A — Admin quản lý sự kiện | Phải đưa `admin@gmail.com` (dùng chung cả lớp) cho người ngoài thao tác; tác vụ kém tự nhiên | Dày nhất | A5 Check-in cần mã hợp lệ + đúng khung giờ ⇒ rất khó lặp trên 7+ ô |
| C — Admin quản lý user | Tệ nhất: người ngoài Block/Reset password trên tài khoản thật của lớp | Trung bình | Trung bình |
| D — Support request | Khá: phía user dễ nhờ, nhưng phải chờ admin phản hồi mới khép được luồng | Mỏng | Trung bình |

**Kết luận:** chọn **B**. Nó tối ưu hạng mục rủi ro nhất, và điểm yếu duy nhất (widget mỏng) là thứ **kiểm soát được bằng cách chọn màn hình đúng** — xem D2.

**Rủi ro đã biết và cách xử lý:**

| Rủi ro | Xử lý |
|---|---|
| Nhiều item checklist về upload / rich-text / kéo-thả sẽ N/A ở phía user | **Đánh ➖ N/A kèm lý do**, tuyệt đối không bỏ trống. Đề chấp nhận N/A có giải trình; bỏ trống mới bị trừ. Bù lại bằng cách chọn B2/B3/B4 — bộ màn hình nhiều **trạng thái** nhất Pool B |
| Cần sự kiện ở đúng trạng thái mới lộ đủ giao diện (hết chỗ → waitlist, đã đóng đăng ký, đã kết thúc) | Dùng quyền admin `admin@gmail.com` tự dựng sẵn 4 sự kiện ở đúng trạng thái cần, đặt tiền tố `[23127183]` — làm trong bước khảo sát EMS |
| Mỗi participant cần một tài khoản EMS | Cho họ tự đăng ký ngay đầu phiên, **bấm giờ chỉ tính từ lúc bắt đầu luồng đăng ký sự kiện**; khó khăn ở bước tạo tài khoản vẫn ghi lại làm finding phụ |

### D2 — Vì sao là B2 + B3 + B4 (chứ không phải B1 + B2 + B3)

| Màn | Vai trò trong bộ | IA gánh chính |
|---|---|---|
| **B2** Trang chi tiết sự kiện — banner, lịch trình, nút Đăng ký, thông báo waitlist | Điểm ra quyết định; nhiều trạng thái nút (còn chỗ / hết chỗ → waitlist / đã đóng / chưa đăng nhập) | IA-01 · IA-04 · IA-03 deep link |
| **B3** Form đăng ký — chọn vai trò, vai trò phụ, xác nhận | **Màn hình form DUY NHẤT phía user** — bỏ nó là mất gần hết IA-02 | IA-02 · IA-04 |
| **B4** My Profile — nút **QR Code** + **My Activities** (badge trạng thái, empty state, Export, phân trang) | Đầu ra quan sát được, dùng làm tiêu chí "hoàn thành" cho Task 2 | IA-04 · IA-01 · IA-03 |

⚠️ **06/08:** tên/đường vào B4 sửa theo tài liệu chính thức EMS (Profile → My Activities, không phải "My Registrations"); QR chưa xác nhận có thật — xem `KHAO_SAT_EMS.md` ⚠️5.

**Ba lý do:**

1. **B4 cho Task 2 một tiêu chí hoàn thành nhìn thấy được.** "Cho mình xem xác nhận đăng ký của bạn" — người quan sát biết ngay xong hay chưa, không phải suy diễn. Bộ B1+B2+B3 kết thúc ở màn xác nhận, mơ hồ hơn nhiều.
2. **B4 là màn duy nhất trong Pool B có badge trạng thái nhiều màu** (chờ duyệt / đã duyệt / danh sách chờ / bị từ chối) + empty state. Không có nó, nhóm item IA-04 gần như rỗng — đúng cái điểm yếu của kịch bản B.
3. **B3 phải có mặt** vì đó là form duy nhất phía user; thiếu nó thì IA-02 (12+ item) chết gần hết.

> **B1 (trang chủ + carousel + tìm kiếm)** vẫn là đường vào của tác vụ, vẫn quan sát trong lúc chạy phiên, nhưng **để ngoài phạm vi chấm** — vừa tránh chồng lấn với người thứ hai nếu nhóm đôi ở B, vừa giữ khối lượng Task 3 ở mức 3 màn × ~7 ô. Nếu cuối cùng **không ai đôi ở B**, thêm B1 làm màn thứ 4 — vẫn phải đăng nhập như 3 màn kia, nhưng rẻ vì không cần dựng trạng thái dữ liệu riêng.

### D3 — Nhóm 5 người thì chia thế nào

Đề chỉ có 4 kịch bản cho 5 người. Luật ở §5 của đề nói rõ:

> *"Where a group has more than four members and a scenario is shared, the members sharing it must choose **different** screens so their coverage does not overlap."*

Nghĩa là: **một kịch bản sẽ có 2 người cùng làm, và hai người đó bắt buộc phải chọn hai bộ màn hình KHÔNG giao nhau.** Không phải "cấm trùng kịch bản" — cấm trùng *cả kịch bản lẫn bộ màn hình*.

**Đôi ở đâu được?** Đếm màn hình đề liệt kê sẵn: A có 5 (A1–A5), B có 5 (B1–B5), C có 4, D có 4. Mỗi người cần ≥ 3 màn rời nhau ⇒ cần ≥ 6 màn ⇒ **chỉ A hoặc B khả thi**. **Tuyệt đối tránh đôi ở C hoặc D.**

**Phương án 1 — MẶC ĐỊNH: đôi ở A, tôi giữ B một mình**

| SV | Kịch bản | Bộ màn hình |
|---|---|---|
| **Duy (23127183)** | **B** | **B2** Trang chi tiết sự kiện · **B3** Form đăng ký · **B4** My Profile — QR Code + My Activities *(có thể thêm B1 làm màn thứ 4)* |
| SV2 | A — nửa *authoring* | A1 Events list · A2 Add/Edit Event · A3 Registration & Roles config |
| SV3 | A — nửa *operation* | A4 Participants approval · A5 Check-in · Dashboard KPI |
| SV4 | C | chọn 3 trong C1–C4 |
| SV5 | D | chọn 3 trong D1–D4 |

**Phương án 2 — đôi ở B (nếu không ai chịu nhận nửa còn lại của A)**

| SV | Kịch bản | Bộ màn hình |
|---|---|---|
| **Duy (23127183)** | **B** — nửa *registration core* | **B2** · **B3** · **B4** |
| SV2 | **B** — nửa *discovery & feedback* | **B1** Trang chủ + carousel · **trang duyệt danh mục / kết quả tìm kiếm** · **B5** Đánh giá sao sau sự kiện |
| SV3 | A | chọn 3 trong A1–A5 |
| SV4 | C | chọn 3 trong C1–C4 |
| SV5 | D | chọn 3 trong D1–D4 |

Căn cứ tách được B thành 6 màn: mô tả Pool B trong đề liệt kê **"public home with the featured-event carousel"** và **"category browsing and search"** thành **hai mục riêng biệt**, nên tính là hai màn hình là hợp lệ.
Cảnh báo cho SV2 ở phương án 2: **B5 cần một sự kiện đã `ENDED` mà chính họ từng đăng ký** — phải nhờ admin dựng dữ liệu trước, đừng để sát deadline mới phát hiện không test được.

**Việc cần làm với nhóm:**
- [ ] Chốt phương án 1 hay 2
- [ ] Ghi bảng phân công vào `README.md` mục 2 và `00-main-report.md` mục 1.3
- [ ] Cả 5 người **dùng chung một checklist duy nhất** ở `team/gui-checklist.md`
- [ ] Nhắc cả nhóm: **mỗi người tự đăng ký tài khoản user riêng**, đề cấm dùng chung tài khoản ở các kịch bản phía user

---

## 1. Bài này chấm cái gì (100 điểm)

| # | Hạng mục | Ai làm | Điểm | File kết quả |
|---|---|---|---:|---|
| 1a | Checklist GUI chung > 40 item phủ IA-01…IA-04 + nguồn tham khảo + AI prompts | **Nhóm** | 15 | `team/gui-checklist.md` + `team/references.md` · `team/ai-prompts.md` |
| 1b | Chạy checklist trên ≥ 3 màn hình + bug report | Cá nhân | 15 | `00-main-report.md` (Chương 2) + `01-checklist-execution.md` |
| 2 | User testing 5 người thật → Usability Report | Cá nhân | 25 | `02-usability-report.md` + `evidence/task2/` |
| 3 | Ma trận cross-browser / cross-platform (3 OS × 5 browser × 3 device class) | Cá nhân | 25 | `03-compatibility-matrix.md` + `evidence/task3/` |
| 4 | Nộp finding qua Google Form + log tổng hợp | Cá nhân | 10 | `04-findings-log.md` |
| 5 | Agent Skills + video demo | Cá nhân | 10 | `skills/` |

**Bắt buộc kèm, thiếu 1 cái = 0 điểm:** AI Audit Report · AI Critique 200–300 từ · Git commit log · README.md có bảng self-assessment · ảnh chụp thật (không được AI-generate).

---

## 2. Lộ trình 6 giai đoạn (tick khi xong)

> ⚡ **Cho phép chạy song song:** Giai đoạn 3 (Task 2 — tuyển & chạy 5 người) **không phụ thuộc** vào Giai đoạn 1/2 xong hay chưa. Task scenario, phiếu SUS, câu hỏi mở đã chốt xong (xem `02-usability-report.md` §1) — có thể **gửi lời mời ngay bây giờ** để không mất thời gian chờ người. Chỉ cần đã xong Giai đoạn 0 (dữ liệu thử B2/B3/B4 còn sống) là chạy phiên được.
> **Công cụ:** study Maze (`app.maze.co`, Live website testing) + cuộc gọi chia sẻ màn hình song song — cách dựng ở `docs/QUY_TRINH_AI_VA_TOI.md` Phần 2 (⚠️ **bạn tự đăng nhập và dựng study**, AI không log in hộ được). Dự phòng nếu Maze trục trặc: [Vé tham gia kiểm thử EMS](https://claude.ai/code/artifact/aa535ccc-fb5d-4888-aa4b-c5ba924fe107).

### GIAI ĐOẠN 0 — Chuẩn bị (~30 phút)
- [~] ⭐ **Khảo sát EMS theo phiếu [`KHAO_SAT_EMS.md`](KHAO_SAT_EMS.md)** — **ĐANG DỞ (~60%)**: đã có 10 ảnh, xong màn đăng nhập + B1 + B2 (4 trạng thái), dựng được 3/4 sự kiện thử. **Còn thiếu: Workshop D · toàn bộ B3 · toàn bộ B4 · phía admin · 8 phép thử.** Ước tính 35 phút nữa
- [ ] Vào SUT https://prod-dev.ems-fitus.cloud, xác nhận hệ thống còn sống (môi trường dev, dữ liệu có thể bị reset → **chụp ảnh liền tay, đừng để dành**)
- [ ] Tự đăng ký 1 tài khoản **user riêng** (student/guest) — bắt buộc, không dùng chung với nhóm
- [ ] **Kiểm tra bộ dữ liệu thử cho kịch bản B còn sống không** — cần ít nhất: 1 sự kiện `PUBLISHED`+`UPCOMING` còn chỗ · 1 sự kiện hết chỗ + bật **Waitlist** · 1 sự kiện đã đóng đăng ký · 1 sự kiện đã `ENDED`. Nếu dữ liệu đã bị reset → dùng lại quyền admin dựng lại, đặt tiền tố `[23127183]`
- [ ] **Bắt đầu nhắn tuyển 5 người ngoài lớp NGAY từ bây giờ** (Task 2 là nút thắt thời gian, không phải nút thắt kỹ thuật)
- [ ] `git init` trong thư mục bài nộp + commit skeleton đầu tiên
- [ ] Chốt D1–D4 ở mục 0
- **Commit:** `[setup] Init HW03 submission skeleton and lock scenario/screens`

### GIAI ĐOẠN 1 — Task 1A: Checklist GUI chung của nhóm (~1.5 giờ, làm cùng nhóm)
- [ ] Ôn lại slide: Nielsen 10 heuristics · Norman 6 principles · Shneiderman 8 golden rules · per-widget checklist
- [ ] Dùng AI sinh bản nháp checklist (**lưu nguyên văn prompt + output** vào `team/references.md` · `team/ai-prompts.md`)
- [ ] Con người review: bỏ item trùng, sửa item mơ hồ, **thêm item AI bỏ sót**
- [ ] Với **mỗi item tự thêm**: ghi rõ **VÌ SAO AI bỏ sót** (prompt kém / giới hạn model / đặc thù EMS). Gợi ý vùng AI hay sót: accessibility, keyboard navigation, dark mode, RTL, **i18n EN/VI (rất đặc thù EMS)**, empty/loading state, độ trễ mạng thật
- [ ] Đếm lại: **> 40 item**, phủ đủ IA-01 / IA-02 / IA-03 / IA-04, mỗi aspect ≥ 8 item
- [ ] Ghi danh sách nguồn tham khảo vào `team/references.md` · `team/ai-prompts.md`
- **Commit:** `[task1a] Add shared GUI checklist (>40 items, IA-01..IA-04) + sources + AI prompts`

### GIAI ĐOẠN 2 — Task 1B: Chạy checklist trên ≥ 3 màn hình (~2 giờ)
- [ ] Với **từng màn hình**, chạy **từng item** → đánh Passed / Failed
- [ ] Cột Notes: với mỗi **Failed**, ghi lý do fail (không được để trống)
- [ ] Chụp ảnh **chỉ cho item Failed** → `evidence/task1b/`, `evidence/task1b/`, `evidence/task1b/`
- [ ] Mỗi Failed → tạo 1 bug entry: màn hình · steps to reproduce · expected vs actual · severity · ảnh
- [ ] Đổ toàn bộ bug vào `04-findings-log.md`
- **Commit (1 commit / 1 màn hình):** `[task1b][screen-B3] Execute checklist on registration form, log N failures`

### GIAI ĐOẠN 3 — Task 2: User testing 5 người thật (~2.5 giờ) ⚠️ TỐN THỜI GIAN NHẤT, ĐẶT LỊCH SỚM
> **Đáng lẽ đã bắt đầu tuyển từ Giai đoạn 0**, đừng để đến lúc này mới đi tìm.
- **Phase 1 — Thiết kế & chuẩn bị**
  - [x] Viết **task scenario theo mục tiêu**, KHÔNG chỉ từng bước bấm — đã chốt (bản an toàn, chờ xác minh QR — xem `KHAO_SAT_EMS.md` ⚠️5): *"Khoa sắp có một workshop mà bạn muốn tham dự. Hãy đăng ký tham gia, rồi cho mình xem xác nhận đăng ký của bạn."*
  - [x] Chốt số liệu đo + 5 câu hỏi mở — xem `02-usability-report.md` §1
  - [ ] **Dựng study Maze** theo 8 bước ở `docs/QUY_TRINH_AI_VA_TOI.md` Phần 2 — tự đăng nhập `app.maze.co`, chỉ có **1 slot study/tháng** ở gói Free nên dựng đúng 1 lần
  - [ ] Tuyển **5 người NGOÀI LỚP**, có liên hệ kiểm chứng được (Zalo/email/phone, **che 4 số giữa**)
  - [ ] Chạy **pilot** với người thứ 6 để sửa kịch bản trước khi chạy thật (dùng chung 1 study Maze, không tính vào 5 người)
- **Phase 2 — Chạy 5 phiên**
  - [ ] Mở đầu: nói rõ "đang test **sản phẩm**, không test bạn"; yêu cầu **think-aloud**
  - [ ] Quan sát trung lập, không gợi ý; chỉ can thiệp khi bí hoàn toàn
  - [ ] Mở cuộc gọi chia sẻ màn hình song song với link Maze (Maze không tự đủ — xem lý do ở `QUY_TRINH_AI_VA_TOI.md`); ghi màn hình (+ audio nếu có consent) + ghi chú có cấu trúc
  - [ ] Kết phiên: xem kết quả Maze của người đó, copy vào `appendix/a1-session-notes.md`
- **Phase 3 — Phân tích**
  - [ ] Tính điểm SUS/UEQ-S cho 5 người; lập bảng metric (success rate, mean time, errors)
  - [ ] Gom pain point giống nhau; **tách bug đơn lẻ ra khỏi vấn đề thiết kế hệ thống**
  - [ ] Xếp hạng **severity 0–4**; mỗi finding 1 ảnh
  - [ ] Viết danh sách khuyến nghị **cụ thể, có ưu tiên**
- [ ] ⚠️ TA có thể **gọi ngẫu nhiên 2 participant** để xác minh — giả mạo = **0 điểm Task 2**
- **Commit:** `[task2] Add usability report: 5 sessions, SUS scores, ranked findings`

### GIAI ĐOẠN 4 — Task 3: Cross-browser / Cross-platform (~2 giờ)
- [ ] Đăng ký trial **BrowserStack** hoặc **LambdaTest** (tự lo tài khoản; hết trial → Sauce Labs / CrossBrowserTesting / máy thật)
- [ ] Với **mỗi màn hình trong 3 màn**, phủ tối thiểu: **3 OS** (Windows · macOS · Android *hoặc* iOS) × **5 browser** (Chrome · Firefox · Safari · Edge · Opera/Samsung Internet) × **3 device class** (desktop · tablet · phone)
- [ ] KHÔNG cần đủ 45 ô — nhưng **mỗi OS ≥ 1 lần, mỗi browser ≥ 1 lần, mỗi device class ≥ 1 lần, cho TỪNG màn hình**
- [ ] Ghi rõ ô nào đã phủ, đánh **Pass / Fail** từng ô
- [ ] Chụp ảnh **mọi ô** trong ma trận; ảnh phải thấy rõ: **email MSSV overlay + URL EMS + tên browser/OS/device**
- [ ] Ô Fail: kèm ghi chú loại lỗi (overflow / overlap / vỡ layout / chữ không đọc được / control không bấm được…)
- **Commit (1 commit / 1 đợt chạy):** `[task3][win-chrome] Cross-platform run on 3 screens, N fails`

### GIAI ĐOẠN 5 — Task 4 + 5: Nộp finding & Agent Skills (~1 giờ)
- [ ] **Submit TỪNG finding** (bug + đề xuất usability) lên Google Form bằng email MSSV
- [ ] Hợp nhất tất cả vào `04-findings-log.md` với đủ cột: *ID · Scenario/Screen · Type (Bug|Usability) · Description · Steps/Heuristic · Severity · Suggested fix · Screenshot ref · Form-submission timestamp*
- [ ] **Đối chiếu số lượng**: số dòng trong log **phải khớp** số lần submit form (TA cross-check)
- [ ] Hoàn thiện 3 Agent Skill trong `skills/`
- [ ] Quay **video demo** end-to-end dùng skill trên 1 màn hình/luồng hoàn chỉnh → upload YouTube → dán link vào `skills/demo-video-link.md`
- **Commit:** `[task4][task5] Aggregate findings log, finalize agent skills + demo videos`

### GIAI ĐOẠN 6 — Đóng gói nộp (~45 phút)
- [ ] Viết `appendix/a3-ai-audit-report.md`: **mỗi lần dùng AI = 1 block** (tool · ngày giờ · prompt nguyên văn · output · **Human Review Notes**)
- [ ] Viết `appendix/a4-ai-critique.md`: **200–300 từ** (đếm từ!) — AI sai/thiên lệch/thiếu ở đâu, vì sao, học được nguyên tắc gì
- [ ] Xuất `appendix/git-log.txt`
- [ ] Điền đầy đủ `README.md`: scenario · màn hình đã test · số item checklist thiết kế/chạy/pass/fail · số bug · 5 participant + usability issue theo severity · số ô compatibility · link video · **bảng self-assessment**
- [ ] Xuất PDF cho: `00-main-report` · `02-usability-report` · `03-compatibility-matrix` · `appendix/a3-ai-audit-report` · `appendix/a4-ai-critique`
- [ ] Rà lại checklist nộp bài ở mục 4
- [ ] Zip đúng tên: `23127183_HW03_AI_GUIUsability_EMS_<điểm tự chấm 3 chữ số>.zip`
- **Commit:** `[final] Complete AI audit, critique, README self-assessment, export PDFs`

---

## 3. Luật AI-First bắt buộc tuân thủ (vi phạm là mất điểm nặng)

| Luật | Nghĩa là gì trong thực tế |
|---|---|
| **Guide, don't dump** | Không được 1 prompt kiểu *"tạo checklist GUI và tìm lỗi usability"*. Phải dẫn AI đi **từng bước của kỹ thuật** như học trên lớp |
| **Human review** | Không nộp output thô của AI. Bạn chịu trách nhiệm về tính đúng đắn |
| **AI Audit Report** | Log **mọi** lần tương tác AI: tool, ngày giờ, prompt, output. Ghi **ngay sau mỗi phiên**, đừng dồn cuối |
| **AI Critique** | 200–300 từ, phải có **ví dụ thật** trong bài này |
| **Anti-cheat** | Ảnh EMS thật · ảnh cross-platform thật có overlay email · **5 người thật** |
| **Git log** | 1 bước = 1 commit (design · execution · bug logging · evaluation · mỗi lần chạy cross-platform) |
| **Chống copy** | Chia sẻ prompt giữa các sinh viên = **0 điểm cả hai bên**. Chỉ mình checklist chung của nhóm được phép giống nhau |

---

## 4. Checklist nộp bài (rà trước khi zip)

**Nhóm nộp 1 lần (mỗi thành viên giữ 1 bản copy):**
- [ ] Checklist GUI chung (> 40 item, phủ IA-01…IA-04)
- [ ] Danh sách nguồn tham khảo
- [ ] Bộ AI prompts dùng để dựng checklist

**File zip cá nhân — `23127183_HW03_AI_GUIUsability_EMS_<grade>.zip`:**
- [ ] Main report (**Markdown + PDF**): kịch bản đã chọn · ≥ 3 màn hình **và lý do chọn** · kết quả chạy checklist từng màn · Usability Report · Cross-platform report
- [ ] Bằng chứng user testing: task scenario · bảng 5 participant (che liên hệ) · ghi chú từng phiên · phiếu SUS/UEQ-S · bảng metric · bản ghi màn hình (nếu có)
- [ ] Bug & Usability Findings Log (khớp với Google Form)
- [ ] Ảnh cross-browser/cross-platform (có overlay MSSV)
- [ ] AI Critique + AI Audit Report (**Markdown + PDF**)
- [ ] Git commit log (file text)
- [ ] Agent Skills + link video demo
- [ ] `README.md` có bảng self-assessment + test summary

**Nhắc:** Không nộp trễ · Thiếu tài liệu bắt buộc = 0 · 30% sinh viên bị gọi vấn đáp 5–7 phút tuần sau deadline.

---

## 5. Bản đồ file ↔ hạng mục chấm

```
HW03/                                    ← repo git (github.com/DuyPham111/HW03)
├── CLAUDE.md ........................... quy tắc thường trực khi làm việc với AI
├── docs/ ............................... KHÔNG đi vào zip nộp
│   ├── KE_HOACH_HW03.md ................ file này — làm gì, thứ tự nào, khi nào
│   ├── HUONG_DAN_CHI_TIET_TUNG_PHAN.md . từng hạng mục: làm gì & NỘP GÌ
│   ├── TASK1A_LAM_MOT_MINH.md .......... làm checklist nhóm một mình
│   ├── KHAO_SAT_EMS.md ................. phiếu khảo sát EMS — điền vào chỗ trống
│   ├── QUY_TRINH_AI_VA_TOI.md .......... AI làm gì (prompt sẵn) / tôi làm gì
│   ├── DE_BAI_0*_*_VI.md ............... 3 bản dịch đề
│   └── de-goc/ ......................... đề gốc EN + kịch bản E2E gốc
│
└── 23127183_HW03_AI_GUIUsability_EMS_100/   ← ĐÚNG PHẦN NỘP, zip từ đây
    ├── README.md ....................... test summary + self-assessment (BẮT BUỘC)
    ├── 00-main-report.md ............... kịch bản · 3 màn hình & lý do · tóm tắt 3 task
    ├── 01-checklist-execution.md ....... Task 1B (15đ) — bảng chạy checklist
    ├── 02-usability-report.md .......... Task 2 (25đ)
    ├── 03-compatibility-matrix.md ...... Task 3 (25đ)
    ├── 04-findings-log.md .............. Task 4 (10đ)
    ├── team/ ........................... Task 1A (15đ) — sản phẩm nhóm
    │   ├── gui-checklist.md · references.md · ai-prompts.md
    ├── skills/ ......................... Task 5 (10đ) — 3 SKILL.md + link video
    ├── appendix/ ....................... phụ lục BẮT BUỘC
    │   ├── a1-session-notes.md ......... ghi chú 5 phiên user testing
    │   ├── a2-sus-scoring.md ........... bảng chấm SUS 10 câu × 5 người
    │   ├── a3-ai-audit-report.md ....... AI Audit (thiếu = 0 điểm)
    │   ├── a4-ai-critique.md ........... AI Critique 200–300 từ (thiếu = 0 điểm)
    │   └── git-log.txt ................. git log (thiếu = 0 điểm)
    └── evidence/
        ├── task1b/ ..................... ảnh item Failed
        ├── task2/ ...................... transcript + phiếu SUS + link ghi màn hình
        ├── task3/ ...................... ảnh mọi ô ma trận (có overlay MSSV)
        └── survey/ ..................... ảnh khảo sát EMS ban đầu
```
