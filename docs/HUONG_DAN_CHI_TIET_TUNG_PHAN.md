# HƯỚNG DẪN CHI TIẾT — Làm gì & Nộp gì cho từng phần HW03

**Sinh viên:** Phạm Vũ Ngọc Duy (23127183) · **Email nộp form / overlay ảnh:** `23127183@student.hcmus.edu.vn`
**SUT:** https://prod-dev.ems-fitus.cloud · **Kịch bản:** **B — User đăng ký tham dự sự kiện**
**Màn hình:** **B1** Danh sách sự kiện · **B2** Trang chi tiết sự kiện · **B4** My Profile — nút QR Code + My Activities

> File này trả lời đúng hai câu cho từng hạng mục: **"phải làm gì?"** và **"nộp cái gì?"**.
> Kế hoạch theo thời gian nằm ở [`KE_HOACH_HW03.md`](KE_HOACH_HW03.md). Nguyên văn đề nằm ở [`DE_BAI_02_Spec_HW03_VI.md`](DE_BAI_02_Spec_HW03_VI.md).

---

## BẢN ĐỒ TỔNG — 100 điểm chia đâu, file nào ứng với hạng mục nào

| Hạng mục | Điểm | Ai làm | File bắt buộc nộp |
|---|---:|---|---|
| **1A** Checklist GUI chung | 15 | **Nhóm** | `team/gui-checklist.md` + `team/references.md` · `team/ai-prompts.md` + `team/references.md` · `team/ai-prompts.md` |
| **1B** Chạy checklist trên 3 màn | 15 | Cá nhân | `01-checklist-execution.md` + `00-main-report.md` (ch.2) + ảnh trong `evidence/task1b/` |
| **2** User testing 5 người | 25 | Cá nhân | `02-usability-report.md` (+PDF) + `evidence/task2/` |
| **3** Cross-browser/platform | 25 | Cá nhân | `03-compatibility-matrix.md` (+PDF) + `evidence/task3/` |
| **4** Nộp finding + log hợp nhất | 10 | Cá nhân | `04-findings-log.md` + các lần submit Google Form |
| **5** Agent Skills + video | 10 | Cá nhân | `skills/*/SKILL.md` + `skills/demo-video-link.md` |

**Bốn thứ KHÔNG có điểm riêng nhưng THIẾU = 0 ĐIỂM TOÀN BÀI:**

| # | Tài liệu | File |
|---|---|---|
| M1 | AI Audit Report (Markdown **+ PDF**) | `appendix/a3-ai-audit-report.md` |
| M2 | AI Critique 200–300 từ (Markdown **+ PDF**) | `appendix/a4-ai-critique.md` |
| M3 | Git commit log (file text) | `appendix/git-log.txt` |
| M4 | README có bảng self-assessment + test summary | `README.md` |

**Main Report** cũng bắt buộc có **cả Markdown lẫn PDF**.

---

# HẠNG MỤC 1A — Checklist GUI chung của nhóm · 15 điểm · NHÓM LÀM

## Đề yêu cầu gì

Nhóm thiết kế **MỘT** checklist GUI **hơn 40 item**, phủ đủ 4 khía cạnh giao diện. Dùng AI sinh bản đầu → **con người review phản biện → thêm item AI bỏ sót**. Với **mỗi item tự thêm** phải giải thích **VÌ SAO AI bỏ sót nó**.

Bốn khía cạnh (IA) bắt buộc phủ:

| Mã | Nội dung |
|---|---|
| **IA-01** | Chuẩn UI tổng quát — bố cục, căn chỉnh, typography, màu, tính nhất quán, i18n EN/VI, trạng thái rỗng/đang tải |
| **IA-02** | Form — nhãn, validation, vị trí thông báo lỗi, trường bắt buộc, upload, rich-text editor |
| **IA-03** | Điều hướng — menu, breadcrumb, tab, sidebar, kéo-thả reorder, back/return, deep link |
| **IA-04** | Phản hồi/trạng thái — toast, badge, dialog xác nhận, progress bar, màu trạng thái, cập nhật real-time |

## Làm gì — 5 bước

**Bước 1. Ôn lý thuyết trước khi mở AI.** Nielsen 10 heuristics (N1–N10) · Norman 6 principles (P1–P6) · Shneiderman 8 golden rules (S1–S8) · checklist theo từng widget trong slide. Không ôn thì không review nổi output của AI.

**Bước 2. Dẫn AI đi từng bước, KHÔNG dồn một prompt.** Đề cấm tường minh prompt kiểu *"generate a GUI checklist and find usability problems"*. Chuỗi prompt đúng:
1. Nạp khung heuristic + mô tả **widget thật quan sát được trên EMS** → bắt AI hỏi lại chỗ nào còn thiếu
2. Sinh item cho **riêng IA-01** → review → riêng IA-02 → riêng IA-03 → riêng IA-04
3. Hỏi ngược AI: *"checklist này còn thiếu vùng nào?"*
4. Người tự bổ sung phần AI vẫn không nêu ra

**Bước 3. Review phản biện.** Loại item trùng nghĩa · sửa item không kiểm chứng được (item kiểu "giao diện đẹp, dễ dùng" là item hỏng) · kiểm tra mã heuristic có gán bừa không.

**Bước 4. Bổ sung item AI bỏ sót + ghi lý do.** Phân loại lý do thành 3 nhóm: **(a)** prompt của mình thiếu ngữ cảnh · **(b)** giới hạn của model · **(c)** đặc thù riêng của EMS mà AI không thể biết nếu không thao tác thật. Vùng AI hay sót (đề nêu đích danh): accessibility · điều hướng bàn phím · dark mode · RTL · **i18n EN/VI** · empty/loading state.

**Bước 5. Đếm lại và chốt.** > 40 item, phân bổ gợi ý: IA-01 ≥ 12 · IA-02 ≥ 12 · IA-03 ≥ 8 · IA-04 ≥ 10.

## Nộp gì

| File | Nội dung phải có |
|---|---|
| `team/gui-checklist.md` | Bảng item với cột: **ID · Item · Cách kiểm · Nguồn heuristic · Nguồn tạo (AI/Người)**. ID dạng `IA01-01` — **dùng lại y nguyên** ở hạng mục 1B |
| `team/references.md` · `team/ai-prompts.md` | Danh sách nguồn: sách, bài báo, tiêu chuẩn, slide môn học. Kèm cột "dùng cho item nào" |
| `team/references.md` · `team/ai-prompts.md` | **Prompt nguyên văn** từng lần + output + human review. Mục 3: bảng item tự thêm kèm lý do AI sót |

> Ba file này **giống hệt nhau giữa 5 thành viên** — đây là trường hợp DUY NHẤT được phép trùng. Nội dung prompt ở đây **cũng phải copy vào `appendix/a3-ai-audit-report.md`** (đề §10 nói rõ).

## Coi như xong khi

- [ ] Đếm được > 40 item
- [ ] Mỗi IA đều có item, không IA nào rỗng
- [ ] Mỗi item trả lời được Passed/Failed khi nhìn màn hình, không mơ hồ
- [ ] Mỗi item có mã heuristic nguồn
- [ ] Mỗi item cột "Nguồn tạo" ghi rõ AI hay Người
- [ ] Mọi item "Người" đều có dòng giải thích vì sao AI sót trong `team/references.md` · `team/ai-prompts.md`

## Bẫy mất điểm

| Bẫy | Hậu quả |
|---|---|
| Nộp thẳng output AI, không thêm item nào | Mất phần lớn 15đ — đề chấm chính ở chỗ "human review" |
| Giải thích "AI sót vì AI không đủ thông minh" | Không được tính — phải nêu lý do **cụ thể** |
| Chia sẻ prompt sang nhóm/sinh viên khác | **0 điểm cả hai bên** |
| Item không kiểm chứng được | Sang 1B sẽ không đánh Passed/Failed nổi, kéo theo mất điểm dây chuyền |

---

# HẠNG MỤC 1B — Chạy checklist trên 3 màn hình · 15 điểm · CÁ NHÂN

## Đề yêu cầu gì

Chạy **toàn bộ** checklist chung lên **từng màn hình** trong 3 màn của mình, đánh **Passed / Failed** cho mỗi cặp (item × màn hình). Thêm cột **Notes** ghi **lý do fail** cho mỗi item Failed. Ảnh chụp **chỉ cần cho item Failed**. Mỗi bug báo cáo đủ: màn hình · steps to reproduce · expected vs actual · severity · ảnh.

## Làm gì

**Bước 1. Chuẩn bị bảng chạy.** Copy cột `ID` + `Item` từ checklist chung sang `01-checklist-execution.md`. Không sửa nội dung item.

**Bước 2. Chuẩn bị dữ liệu trên EMS.** Kịch bản B cần các sự kiện ở đúng trạng thái mới lộ hết giao diện:

| Cần | Dùng để lộ cái gì |
|---|---|
| Sự kiện `PUBLISHED` + `UPCOMING` còn chỗ | Luồng đăng ký chính trên B1 → B2 → B4 |
| Sự kiện **hết chỗ + bật Waitlist** | Trạng thái "vào danh sách chờ" trên B2 + badge waitlist trên B4 |
| Sự kiện **đã đóng đăng ký** | Nút Đăng ký bị vô hiệu hoá trên B2 |
| Sự kiện **đã `ENDED`** | Badge trạng thái trên B4 |
| Tài khoản **chưa có đăng ký nào** | **Empty state** của B4 — rất hay bị bỏ sót |

**Bước 3. Chạy tuần tự theo ID, không nhảy cóc.** Nhảy cóc là sót.

**Bước 4. Xử lý item không áp dụng được.** Kịch bản B không có upload ảnh / rich-text / kéo-thả reorder. Những item đó đánh **➖ N/A và GHI LÝ DO** — tuyệt đối không để trống. Đề chấp nhận N/A có giải trình; ô trống mới bị trừ.

**Bước 5. Thấy Failed → chụp ảnh NGAY.** SUT là môi trường dev, dữ liệu có thể bị reset. Đặt tên file đúng bằng Bug-ID sẽ dùng: `CL-B2-01.png`.

**Bước 6. Biến mỗi Failed thành một bug entry** trong `04-findings-log.md`, prefix `CL-`.

## Nộp gì

| File / thư mục | Nội dung |
|---|---|
| `01-checklist-execution.md` | Bảng hợp nhất: mỗi dòng 1 item, 3 cột kết quả cho B1/B2/B4, cột Notes, cột Bug-ID, cột Ảnh. Kèm block chi tiết cho từng item Failed |
| `00-main-report.md` chương 2 | Bảng tổng hợp theo màn hình + theo IA, phân tích cụm lỗi, bảng tóm tắt bug |
| `evidence/task1b/` `evidence/task1b/` `evidence/task1b/` | Ảnh cho **item Failed** — không cần ảnh cho item Passed |

## Coi như xong khi

- [ ] Không còn ô kết quả trống ở bất kỳ màn hình nào
- [ ] Mọi ❌ Failed có Notes ghi **lý do** (không chỉ mô tả hiện tượng)
- [ ] Mọi ➖ N/A có lý do
- [ ] Mọi Failed có ảnh và ảnh mở lên đúng nội dung
- [ ] Số bug prefix `CL-` khớp giữa `01-checklist-execution.md` và `04-findings-log.md`

## Bẫy mất điểm

| Bẫy | Hậu quả |
|---|---|
| Chỉ chạy checklist trên 1 màn rồi suy ra 2 màn kia | TA đối chiếu ảnh sẽ thấy ngay |
| Notes ghi "không đạt" | Không phải lý do — phải nói **vì sao** không đạt |
| Ô N/A bỏ trống | Bị coi là chưa chạy hết checklist |
| Ảnh chụp không thấy màn hình EMS thật | Vi phạm §12 chống gian lận |

---

# HẠNG MỤC 2 — User testing 5 người thật · 25 điểm · CÁ NHÂN ⚠️ NẶNG NHẤT

## Đề yêu cầu gì

**Không tự mình phán xét usability.** Phải thiết kế kịch bản, chạy với **5 người dùng thật NGOÀI LỚP**, thu số liệu, phân tích thành Usability Report. **TA có quyền gọi ngẫu nhiên 2 người để xác minh — giả mạo = 0 điểm toàn bộ hạng mục này.**

## Giai đoạn 1 — Thiết kế & chuẩn bị

**Viết task scenario theo MỤC TIÊU, không phải từng bước bấm.**

> Bản nháp cho kịch bản B: *"Khoa sắp có một workshop mà bạn muốn tham dự. Hãy đăng ký tham gia và cho mình xem mã QR check-in của bạn."*

**Định nghĩa tiêu chí hoàn thành** (phải quan sát được từ bên ngoài):
- **Completed** — đăng ký xong đúng sự kiện **và** tự mở được modal `Check-in QR Code` (My Profile → nút `QR Code`)
- **Partial** — đăng ký được nhưng không tìm ra vé
- **Failed** — không hoàn tất đăng ký

**Chốt 4 nhóm số liệu bắt buộc đo:**

| Chỉ số | Cách đo |
|---|---|
| Task success | Completed / Partial / Failed theo định nghĩa trên |
| Time on task | Bấm giờ từ lúc chạm chuột đến khi đạt tiêu chí hoàn thành (trừ thời gian moderator nói) |
| Errors / hesitations | Định nghĩa rõ trước: thế nào là 1 lỗi, thế nào là 1 lần do dự (vd dừng > 5 giây) |
| **SUS hoặc UEQ-S** | Điền **ngay sau tác vụ, trước khi hỏi câu mở** |

**Soạn 5 câu hỏi mở** phủ 4 chủ đề đề yêu cầu: **clarity · error recovery · speed · trust**. Câu hỏi phải trung lập, tránh dẫn dắt kiểu "bạn thấy khó dùng chỗ nào?".

**Tuyển 5 người:**
- Chân dung: **sinh viên có đi dự sự kiện/workshop của trường**
- **Bắt buộc ngoài lớp học này**
- Liên hệ kiểm chứng được (Zalo / email / SĐT), **che 4 chữ số ở GIỮA**
- Mỗi người **tự đăng ký tài khoản EMS riêng** — đề cấm dùng chung tài khoản ở kịch bản phía user

**Chạy pilot với người thứ 6** — mục đích là phát hiện đề bài mơ hồ, không phải lấy dữ liệu. Ghi lại đã sửa gì sau pilot.

## Giai đoạn 2 — Chạy 5 phiên

| Việc | Cách làm |
|---|---|
| Mở đầu (đọc nguyên văn cho cả 5 người) | *"Mình đang test **sản phẩm này**, không phải test bạn — bạn không thể làm sai được. Bạn nói to những gì đang nghĩ giúp mình nhé."* |
| Trong phiên | Quan sát **trung lập**, không gợi ý. Bị hỏi thì trả lại: *"Bạn nghĩ nó sẽ làm gì?"* |
| Khi participant bí | Đợi đủ ngưỡng đã định (vd 2 phút) mới gợi ý mức tối thiểu, **ghi lại là đã can thiệp** |
| Ghi chú | Bảng dòng thời gian: `thời điểm · hành động · lời nói nguyên văn · phân loại · màn hình` |
| Ghi màn hình | Có xin phép (+ audio nếu được đồng ý) |
| Kết phiên | SUS/UEQ-S **trước**, câu hỏi mở **sau** |

**Biến thể nên dùng cho 2/5 người:** giao sự kiện **đã hết chỗ + có Waitlist** thay vì sự kiện còn chỗ — để xem người dùng có hiểu mình đang vào **danh sách chờ** chứ không phải đã được nhận. Đây thường là chỗ hiểu nhầm nặng nhất và chỉ lộ ra khi có người thật thao tác.

## Giai đoạn 3 — Phân tích

1. **Tính SUS.** Câu lẻ (1,3,5,7,9): `điểm − 1`. Câu chẵn (2,4,6,8,10): `5 − điểm`. Cộng lại **× 2.5** → thang 0–100. Mốc: **< 68** dưới trung bình · **68** trung bình · **> 80.3** tốt. → **Tự tính tay ít nhất 1 phiếu** để kiểm chứng.
2. **Lập bảng metric** 5 dòng + dòng trung bình.
3. **Gom pain point** giống nhau, ghi rõ **mấy trên 5 người** gặp phải + trích lời nguyên văn làm bằng chứng.
4. **Tách bug đơn lẻ khỏi vấn đề thiết kế hệ thống** — yêu cầu tường minh của đề. Tiêu chí: 1 người gặp + do trạng thái dữ liệu đặc thù ⇒ bug đơn lẻ; ≥ 3/5 người gặp hoặc lặp ở nhiều màn ⇒ vấn đề hệ thống.
5. **Xếp severity 0–4** (thang Nielsen): 0 không phải vấn đề · 1 cosmetic · 2 minor · 3 major · 4 catastrophe.
6. **Viết khuyến nghị** — mỗi cái phải là **thay đổi cụ thể**, không phải mục tiêu. Viết "gộp 2 bước đăng ký thành 1 màn", không viết "cải thiện trải nghiệm đăng ký".

## Nộp gì

| File / thư mục | Nội dung |
|---|---|
| `02-usability-report.md` **+ PDF** | Task scenario · bảng 5 participant (liên hệ đã che) · bảng metric · findings xếp severity **kèm mỗi finding 1 ảnh** · danh sách khuyến nghị có ưu tiên |
| `evidence/task2/` | Bằng chứng **thô**: ghi chú từng phiên, ảnh/scan phiếu SUS-UEQ-S, bản ghi màn hình nếu có |
| `00-main-report.md` chương 3 | Bảng tóm tắt để đọc liền mạch |
| `04-findings-log.md` | Bug thật phát hiện trong phiên, prefix `US-` |

## Coi như xong khi

- [ ] Đúng **5** participant, **đều ngoài lớp**, liên hệ che 4 số giữa
- [ ] Có pilot người thứ 6 + ghi rõ đã sửa gì sau pilot
- [ ] Bảng metric đủ 5 dòng + dòng trung bình
- [ ] Có điểm SUS/UEQ-S của cả 5 người và điểm trung bình, kèm diễn giải mốc
- [ ] Mỗi finding có: số người gặp / severity / heuristic vi phạm / ảnh / khuyến nghị
- [ ] Có mục tách rõ **bug đơn lẻ vs vấn đề hệ thống**
- [ ] Bằng chứng thô đã nằm trong `evidence/task2/`

## Bẫy mất điểm

| Bẫy | Hậu quả |
|---|---|
| Nhờ bạn cùng lớp làm participant | Vi phạm "outside this class" |
| Bịa participant | TA gọi xác minh → **0 điểm cả hạng mục 25đ** |
| Task scenario liệt kê từng bước bấm | Không đo được usability, mất phần lớn điểm |
| Điền SUS sau khi đã trò chuyện | Điểm bị nhiễu bởi cuộc nói chuyện |
| Chỉ có kết luận, không có dữ liệu thô | Không chứng minh được đã chạy thật |
| Để AI "đoán" pain point mà 5 người không hề gặp | Sai bản chất của hạng mục này |

---

# HẠNG MỤC 3 — Cross-Browser / Cross-Platform · 25 điểm · CÁ NHÂN

## Đề yêu cầu gì

Với **TỪNG màn hình trong 3 màn**, xây ma trận tương thích phủ **3 OS × 5 browser × 3 loại thiết bị**. **Không cần đủ 45 tổ hợp**, nhưng phải chạm **mọi OS ≥ 1 lần, mọi browser ≥ 1 lần, mọi device class ≥ 1 lần — cho từng màn hình**. Chụp ảnh **MỌI ô**, không chỉ ô Fail.

| Chiều | Giá trị bắt buộc phủ |
|---|---|
| 3 OS | Windows · macOS · Android **hoặc** iOS |
| 5 browser | Chrome · Firefox · Safari · Edge · Opera (hoặc Samsung Internet trên mobile) |
| 3 device class | Desktop · Tablet · Phone |

## Làm gì

**Bước 1. Thiết kế bộ tổ hợp tối thiểu.** 7 ô là đủ phủ cả 3 chiều. Bộ gợi ý sẵn trong `03-compatibility-matrix.md`:

| Ô | OS | Browser | Device |
|---|---|---|---|
| C1 | Windows 11 | Chrome | Desktop |
| C2 | Windows 11 | Edge | Desktop |
| C3 | Windows 11 | Firefox | Desktop |
| C4 | macOS | Safari | Desktop |
| C5 | macOS | Opera | Desktop |
| C6 | Android/iOS | Chrome/Safari | Tablet |
| C7 | Android/iOS | Firefox/Samsung Internet | Phone |

**Ràng buộc kỹ thuật phải biết trước:** Safari chỉ có trên macOS/iOS · Samsung Internet chỉ trên Android · **trên iOS mọi trình duyệt đều chạy WebKit** (Chrome iOS không phải Blink) — nếu dùng iOS thì phải nêu rõ giới hạn này trong báo cáo.

**Bước 2. Chuẩn bị công cụ + overlay.** Trial **BrowserStack** hoặc **LambdaTest** (tự lo tài khoản). Ghi lại số phút trial còn để không hết giữa chừng.

Ba cách overlay email `23127183@student.hcmus.edu.vn`, ưu tiên từ trên xuống:
1. Mở cửa sổ phụ hiển thị email, đặt cạnh cửa sổ EMS trước khi chụp — **mạnh nhất về mặt bằng chứng**
2. Dán email vào ô tìm kiếm/URL bar trong khung hình
3. Chèn text lên ảnh sau khi chụp — yếu nhất, dùng cuối cùng

**Bước 3. Chạy từng ô × từng màn hình.** Kiểm 3 nhóm:

| Nhóm | Kiểm gì |
|---|---|
| Hiển thị | Layout không vỡ · không scroll ngang ngoài ý muốn · chữ đọc được · ảnh/icon load đủ |
| Hành vi | Nút bấm được · form nhập được · dropdown/modal mở đúng · toast hiện đúng chỗ |
| Responsive | Ở tablet/phone: menu có thu gọn không · bảng có scroll trong khung riêng không |

**Lưu ý riêng cho bộ màn hình B — kiểm chứng 05/08, sửa lại 06/08/2026:** B1 và B4 chặn khi chưa đăng nhập. **B2 thì tuỳ cấu hình sự kiện** — sự kiện bật `Public Event` xem được mà không cần đăng nhập, sự kiện không bật thì hiện "Please sign in to view this event." Kết luận cũ *"cả ba màn đều chặn"* là quá tay. Với Task 3 vẫn tính là phải đăng nhập, vì luồng đăng ký thật bắt buộc có tài khoản. Mỗi phiên BrowserStack là một trình duyệt sạch ⇒ **phải đăng nhập lại ở TỪNG ô** — 7 ô × 3 màn nghĩa là ~7 lần đăng nhập, không phải 0. Cộng thêm ~15–20 phút vào ước tính Task 3, và cân nhắc chạy cả 3 màn trong **cùng một phiên** trước khi đổi sang tổ hợp khác. **B4 chứa mã QR** — chỗ lỗi render dễ lộ nhất trên WebKit/mobile, soi kỹ.

**Bước 4. Phân biệt lỗi tương thích với bug chung.** Lỗi xuất hiện ở **mọi** môi trường **không phải** lỗi tương thích — đó là bug ứng dụng. Chỉ ghi là lỗi tương thích khi nó **chỉ** xảy ra ở một số ô. Ghi rõ điều này vào cột "có tái hiện ở môi trường khác không".

## Nộp gì

| File / thư mục | Nội dung |
|---|---|
| `03-compatibility-matrix.md` **+ PDF** | 3 bảng ma trận (1 bảng/màn hình) · bảng kiểm tra độ phủ 3 chiều · block chi tiết mỗi ô Fail · bảng phân bố lỗi theo OS/engine/device · mục giới hạn |
| `evidence/task3/` | Ảnh **mọi ô** (3 màn × 7 ô ≈ 21 ảnh), đặt tên `B2_chrome_windows_desktop.png`. Ô Fail thêm bản đặt theo Bug-ID `CP-B2-01.png` |
| `04-findings-log.md` | Lỗi tương thích, prefix `CP-` |

## Coi như xong khi

- [ ] Với **từng màn hình**: tự đếm lại đủ 3 OS, đủ 5 browser, đủ 3 device class
- [ ] Có ảnh cho **mọi ô**, không chỉ ô Fail
- [ ] **Mọi ảnh** thấy rõ: email `23127183@student.hcmus.edu.vn` + URL EMS + tên browser/OS/device
- [ ] Mỗi ô Fail có ghi chú **loại lỗi cụ thể** (overflow / overlap / vỡ layout / chữ không đọc được / control không phản hồi)
- [ ] Đã ghi rõ ô nào chạy **emulator** và ô nào **thiết bị thật**
- [ ] Có mục giới hạn (số phút trial, phiên bản không chọn được, iOS dùng chung WebKit…)

## Bẫy mất điểm

| Bẫy | Hậu quả |
|---|---|
| Ảnh thiếu overlay email | **Ảnh không được tính** — coi như ô đó chưa chạy |
| Chỉ chụp ô Fail | Đề đòi ảnh **mọi ô** |
| Phủ đủ 3 chiều nhưng chỉ trên 1 màn hình | Đề đòi **từng màn hình** đều phủ đủ |
| Dùng DevTools responsive mode gọi là "test trên phone" | Không phải cross-platform testing; phải ghi rõ emulator/simulator/thiết bị thật |
| Báo bug chung là lỗi tương thích | Sai bản chất hạng mục |

---

# HẠNG MỤC 4 — Nộp finding + log hợp nhất · 10 điểm · CÁ NHÂN

## Đề yêu cầu gì

**Mọi** defect và **mọi** đề xuất cải tiến usability phát hiện xuyên suốt hạng mục 1–3 phải báo cáo **HAI LẦN**:
1. Submit **từng cái một** lên Google Form https://forms.gle/CJQFQCAXcsDbXDMM9 bằng email `23127183@student.hcmus.edu.vn`
2. Hợp nhất tất cả vào **một file**

**Hai bên phải nhất quán — TA đối chiếu số lượng.**

## Làm gì

**Quy ước ID theo nguồn** (giúp truy được nguồn gốc mỗi finding):

| Prefix | Từ đâu |
|---|---|
| `CL-` | Chạy checklist (hạng mục 1B) |
| `US-` | 5 phiên user testing (hạng mục 2) |
| `CP-` | Cross-platform (hạng mục 3) |
| `SV-` | Khảo sát EMS ban đầu (trước khi thiết kế checklist) |

**9 cột bắt buộc theo đề:**
`ID · Scenario/Screen · Type (Bug \| Usability) · Description · Steps/Heuristic · Severity · Suggested fix · Screenshot ref · Form-submission timestamp`

**Timestamp** ghi theo thời điểm bấm Submit trên form, định dạng `YYYY-MM-DD HH:MM`.

**Nộp form ngay khi tìm ra**, đừng dồn cuối — dồn thì quên timestamp và dễ lệch số lượng.

## Nộp gì

| File | Nội dung |
|---|---|
| `04-findings-log.md` | Bảng hợp nhất đủ 9 cột + block chi tiết từng finding có nhúng ảnh + 3 bảng thống kê (theo nguồn / theo severity / theo màn hình) |

## Coi như xong khi

- [ ] **Số dòng trong log = số lần submit Google Form**
- [ ] Mọi finding có `Screenshot ref` trỏ tới file **có thật**
- [ ] Mọi finding có `Form-submission timestamp`
- [ ] Toàn bộ lần submit dùng **đúng email MSSV**, không lẫn email cá nhân
- [ ] Không có ID trùng hoặc nhảy cóc

## Bẫy mất điểm

| Bẫy | Hậu quả |
|---|---|
| Submit form bằng Gmail cá nhân | Không quy được về mình → coi như chưa nộp |
| Log có 20 finding nhưng form chỉ 12 lần submit | TA cross-check ra ngay |
| Chỉ báo bug, bỏ qua đề xuất usability | Đề đòi **cả hai loại** (`Type = Bug \| Usability`) |

---

# HẠNG MỤC 5 — Agent Skills + video demo · 10 điểm · CÁ NHÂN

## Đề yêu cầu gì

Xây **Agent Skills** áp dụng cho: thực thi GUI-checklist · đánh giá usability theo heuristic · chạy ma trận tương thích — sao cho **tái sử dụng được** trên màn hình/luồng EMS khác. Nộp kèm **video demo (link YouTube)** cho thấy **từ đầu đến cuối** cách dùng skill trên một màn hình hoặc luồng hoàn chỉnh.

## Làm gì

Ba skill đã có sẵn khung trong `skills/`, việc còn lại là **dùng chúng thật trong lúc làm bài rồi tinh chỉnh lại theo trải nghiệm thực tế**:

| Skill | Dùng ở hạng mục |
|---|---|
| `hw03-gui-checklist` | 1A + 1B |
| `hw03-usability-5users` | 2 |
| `hw03-crossplatform-matrix` | 3 |

**Quay ít nhất 1 video** (khuyến nghị quay skill `hw03-gui-checklist` vì nó dễ demo end-to-end nhất). Kịch bản quay chi tiết đã có trong `skills/demo-video-link.md`. Điểm mấu chốt của video: **phải cho thấy rõ ít nhất một chỗ mình sửa/loại output của AI** — đó là bằng chứng human review, thứ người chấm quan tâm nhất.

## Nộp gì

| File | Nội dung |
|---|---|
| `skills/hw03-gui-checklist/SKILL.md` | Frontmatter `name` + `description`, quy trình từng bước, prompt mẫu, checklist review |
| `skills/hw03-usability-5users/SKILL.md` | như trên |
| `skills/hw03-crossplatform-matrix/SKILL.md` | như trên |
| `skills/demo-video-link.md` | Bảng link YouTube + mô tả nội dung từng video |

## Coi như xong khi

- [ ] 3 file SKILL.md hoàn chỉnh, **phản ánh đúng cách mình đã thực sự làm bài** (không phải lý thuyết suông)
- [ ] Có ít nhất 1 link YouTube **mở được mà không cần đăng nhập** (Unlisted là được)
- [ ] Video có cảnh sửa/loại output AI
- [ ] Video có hiện email MSSV ít nhất một lần

## Bẫy mất điểm

| Bẫy | Hậu quả |
|---|---|
| Skill viết chung chung, không dùng được lại | Mất phần lớn 10đ |
| Không có video | Đề nói rõ "submit the skills **together with** demonstration videos" |
| Video để Private | TA mở không được = như không nộp |
| Trong video lộ dữ liệu cá nhân người dùng khác trên EMS | Vấn đề riêng tư |

---

# BỐN TÀI LIỆU BẮT BUỘC — không có điểm riêng, thiếu là 0

## M1 · AI Audit Report — `appendix/a3-ai-audit-report.md` (+ PDF)

**Khai báo:** *"I use AI tools for the following tasks."*

**Mỗi lần dùng AI = 1 block**, gồm 5 phần:

| Phần | Nội dung |
|---|---|
| Tool | Tên công cụ + model cụ thể |
| Date & Time | Ngày giờ |
| Prompt | **Nguyên văn**, không tóm tắt |
| AI Output | Tóm tắt đủ để người chấm hiểu AI tạo ra gì |
| **Human Review Notes** | **Phần được chấm kỹ nhất** — bạn kiểm chứng gì, sửa gì, loại gì, vì sao |

**Ghi ngay sau mỗi phiên**, đừng dồn cuối — dồn thì quên prompt và giờ.
**Prompt dựng checklist của nhóm cũng phải nằm ở đây** (đề §10).

## M2 · AI Critique — `appendix/a4-ai-critique.md` (+ PDF)

**200–300 từ. Đếm từ trước khi nộp.** Phải có **ví dụ thật từ chính bài này**, không viết chung chung.

Dàn ý gợi ý: 1 câu mở (~20 từ) → ví dụ AI **SAI** (~70 từ) → ví dụ AI **THIẾU** (~70 từ) → ví dụ AI **THIÊN LỆCH** (~60 từ) → nguyên tắc rút ra (~60 từ). Mỗi ví dụ phải trả lời được câu **"vì sao AI không bắt được?"**.

Nguyên liệu lấy từ: mục "AI Gap Analysis" trong `00-main-report.md` + các dòng Human Review Notes trong `appendix/a3-ai-audit-report.md`.

## M3 · Git commit log — `appendix/git-log.txt`

Đề đòi **1 bước = 1 commit**. Quy ước message:

```
[setup]              khoi tao skeleton, chot scenario/screens
[task1a]             thiet ke checklist chung
[task1b][screen-XX]  chay checklist tren tung man hinh
[bug]                log bug + anh bang chung
[task2][phase-N]     thiet ke / chay phien / phan tich usability
[task3][os-browser]  moi dot chay cross-platform
[task4]              tong hop findings log
[task5]              agent skills + video demo
[final]              AI audit, critique, README, xuat PDF
```

Xuất log:

```bash
git log --pretty=format:"%h | %ad | %s" --date=format:"%Y-%m-%d %H:%M" > appendix/git-log.txt
```

## M4 · README — `README.md`

Phải có **bảng self-assessment** (6 dòng theo §16 của đề) **và** test summary gồm: kịch bản đã chọn · màn hình đã test · số item checklist thiết kế/chạy/pass/fail · số bug · 5 participant + usability issue theo severity · số ô compatibility đã phủ · link video demo.

---

# THỨ TỰ LÀM & THỜI GIAN (đề cho 10 giờ)

| # | Việc | Giờ | Vì sao ở vị trí này |
|---|---|---:|---|
| 0 | Chuẩn bị: kiểm tra SUT, tài khoản user riêng, dữ liệu thử, **bắt đầu nhắn tuyển 5 người** | 0.5 | Tuyển người là nút thắt **thời gian**, phải khởi động sớm nhất |
| 1 | **1A** — Checklist nhóm | 1.5 | Mọi thứ sau đều phụ thuộc checklist |
| 2 | **1B** — Chạy checklist trên B1/B2/B4 | 2.0 | Làm trước Task 2 để **biết trước hệ thống hỏng chỗ nào**, quan sát phiên sắc hơn |
| 3 | **2** — 5 phiên user testing | 2.5 | Nặng nhất; lịch phụ thuộc người khác |
| 4 | **3** — Cross-platform | 2.0 | Độc lập, có thể chen vào lúc chờ lịch participant |
| 5 | **4 + 5** — Findings log + skills + video | 1.0 | Gom lại cuối |
| 6 | Đóng gói: AI Audit, Critique, git log, README, xuất PDF, zip | 0.75 | |

**Việc chạy song song được:** hạng mục 3 (cross-platform) không phụ thuộc ai, cứ chen vào những lúc chờ lịch participant của hạng mục 2.

---

# CHECKLIST CUỐI CÙNG TRƯỚC KHI ZIP

**Nhóm nộp 1 lần (mỗi người giữ 1 bản copy):**
- [ ] `team/gui-checklist.md` (> 40 item, IA-01…IA-04)
- [ ] `team/references.md` · `team/ai-prompts.md`
- [ ] `team/references.md` · `team/ai-prompts.md`

**Zip cá nhân — `23127183_HW03_AI_GUIUsability_EMS_<điểm 3 chữ số>.zip`:**
- [ ] `00-main-report.md` **+ PDF**
- [ ] `02-usability-report.md` **+ PDF** + `evidence/task2/` (bằng chứng thô)
- [ ] `03-compatibility-matrix.md` **+ PDF** + `evidence/task3/` (có overlay MSSV)
- [ ] `01-checklist-execution.md` + `evidence/task1b/`
- [ ] `04-findings-log.md` (khớp Google Form)
- [ ] `appendix/a3-ai-audit-report.md` **+ PDF**
- [ ] `appendix/a4-ai-critique.md` **+ PDF** (200–300 từ)
- [ ] `git_commit_log.txt`
- [ ] `skills/` + link video demo
- [ ] `README.md` có self-assessment + test summary

**Quy định cứng:**
- ❌ **Không nộp trễ**
- ❌ **Thiếu 1 tài liệu bắt buộc = 0 điểm**
- ❌ **Chia sẻ prompt giữa sinh viên = 0 điểm cả hai bên** (chỉ checklist chung của nhóm được phép giống nhau)
- ⚠️ **30% sinh viên bị gọi vấn đáp 5–7 phút** trong tuần sau deadline
