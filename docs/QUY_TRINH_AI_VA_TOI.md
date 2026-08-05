# QUY TRÌNH LÀM VIỆC — AI làm gì · Tôi làm gì

**Kịch bản B** · **B2** Trang chi tiết sự kiện · **B3** Form đăng ký · **B4** My Registrations + vé QR
**SUT:** https://prod-dev.ems-fitus.cloud · **Email:** `pvnduy23@clc.fitus.edu.vn`

> Mỗi phần dưới đây có 3 khối: **bảng chia việc** → **prompt copy-paste được ngay** → **việc tôi phải tự làm + recheck**.
> Prompt nào có `[...]` là chỗ bạn phải dán dữ liệu thật vào. **Không dán dữ liệu thật thì AI sẽ bịa** — đó là nguyên nhân mất điểm số 1 của bài này.

---

## Nguyên tắc phân vai — đọc một lần, nhớ cả bài

| AI ĐƯỢC làm | AI KHÔNG được làm |
|---|---|
| Dựng khung, sinh bản nháp, chuẩn hoá định dạng | Điền kết quả Passed/Failed thay bạn |
| Phân tích **dữ liệu bạn dán vào** | Đoán kết quả bạn chưa chạy |
| Gợi ý severity kèm căn cứ | Chốt severity — bạn chốt |
| Tính toán (SUS, tỉ lệ pass, đếm ô) | Bịa số liệu khi bạn chưa cung cấp |
| Viết lại câu cho gọn | Viết hộ quan sát mà bạn chưa quan sát |
| Kiểm tra tính nhất quán giữa các file | Chụp ảnh, chạy trình duyệt, nói chuyện với participant |

**Câu chốt phải dán vào cuối mọi prompt phân tích:**

```
Chỉ dùng dữ liệu tôi dán ở trên. Nếu một kết luận không có bằng chứng trong dữ liệu đó,
hãy ghi rõ "không đủ dữ liệu" thay vì suy đoán.
```

---

# PHẦN 1A — Checklist chung (15đ)

Chi tiết đầy đủ ở [`TASK1A_LAM_MOT_MINH.md`](TASK1A_LAM_MOT_MINH.md) — vì bạn phải tự làm một mình nên phần này có file riêng.

| AI làm | Tôi làm |
|---|---|
| Nạp khung heuristic, sinh item theo từng IA (4 prompt riêng), tự soi lỗ hổng checklist | **Khảo sát EMS thật để có danh sách widget** · review loại item trùng/mơ hồ · bổ sung item AI sót · viết lý do AI sót · đếm lại bằng `grep -c` |

---

# PHẦN 1B — Chạy checklist trên B2/B3/B4 (15đ)

## Chia việc

| Bước | AI làm | Tôi làm |
|---|---|---|
| 1 | Chuyển checklist thành bảng chạy 3 cột màn hình, giữ nguyên ID | Kiểm tra không sót item nào |
| 2 | — | **Chạy từng item trên EMS thật**, điền Passed/Failed/N-A |
| 3 | — | **Chụp ảnh mọi item Failed** |
| 4 | Nhóm các Failed theo nguyên nhân gốc, gợi ý severity | Chốt severity theo tác động thật |
| 5 | Sinh bug entry đúng định dạng 9 cột | Kiểm từng steps-to-reproduce có tái hiện được không |
| 6 | Cập nhật bảng thống kê, kiểm tính nhất quán số liệu | Đếm lại |

## Prompt 1B-1 — Dựng bảng chạy

```
Đây là checklist chung của nhóm: [DÁN TOÀN BỘ team/gui-checklist.md]

Chuyển thành một bảng chạy duy nhất cho file 01-checklist-execution.md, format:
| ID | Mục kiểm tra (rút gọn ≤ 12 từ) | IA | B2 | B3 | B4 | Notes | Bug-ID | Ảnh |

- Giữ NGUYÊN ID và thứ tự gốc, không đánh số lại
- 3 cột B2/B3/B4 để trống — tôi sẽ tự điền khi chạy thật
- Với mỗi item, đánh dấu trước bằng ký hiệu (?) nếu bạn dự đoán nó sẽ N/A ở phía user
  (EMS phía user không có upload ảnh, rich-text, kéo-thả reorder) — đây chỉ là DỰ ĐOÁN
  để tôi chạy nhanh hơn, tôi vẫn tự xác nhận từng cái
```

## Prompt 1B-2 — Chuẩn bị dữ liệu thử (chạy trước khi test)

```
Tôi sắp chạy checklist GUI trên 3 màn hình phía user của EMS:
B2 trang chi tiết sự kiện, B3 form đăng ký, B4 My Registrations + vé QR.

Liệt kê CÁC TRẠNG THÁI DỮ LIỆU tôi cần dựng sẵn (bằng quyền admin) để 3 màn hình này
bộc lộ hết giao diện — mỗi trạng thái nói rõ nó làm lộ ra widget/thông báo nào.
Trình bày dạng bảng: | Trạng thái cần dựng | Dựng thế nào | Làm lộ ra cái gì | Màn hình |
```

## Prompt 1B-3 — Phân tích sau khi đã CHẠY THẬT

```
Đây là kết quả chạy checklist thật của tôi trên EMS:
[DÁN BẢNG ĐÃ ĐIỀN ĐẦY ĐỦ Passed/Failed/N-A]

1) Nhóm các item Failed theo NGUYÊN NHÂN GỐC chung (không nhóm theo IA).
2) Với mỗi nhóm: đây là bug đơn lẻ hay vấn đề thiết kế mang tính hệ thống? Nêu căn cứ.
3) Đề xuất severity 0-4 theo thang Nielsen cho từng nhóm, giải thích căn cứ từng mức.
4) Chỉ ra chỗ nào kết quả của tôi MÂU THUẪN nhau (vd cùng một widget nhưng
   Passed ở màn này Failed ở màn kia) để tôi kiểm tra lại.

Chỉ dùng dữ liệu tôi dán ở trên. Nếu một kết luận không có bằng chứng trong dữ liệu đó,
hãy ghi rõ "không đủ dữ liệu" thay vì suy đoán.
```

→ Điểm 4 là thứ đáng giá nhất — AI bắt mâu thuẫn giỏi hơn mắt người khi bảng dài.

## Prompt 1B-4 — Sinh bug entry

```
Đây là các item Failed đã chốt severity: [DÁN]

Viết thành bug entry cho 04-findings-log.md, mỗi entry một block:
| Type (Bug hoặc Usability) | Scenario/Screen | Description | Steps to reproduce (đánh số)
| Expected | Actual | Heuristic vi phạm | Severity | Suggested fix | Screenshot ref |

- ID dạng <NGUỒN>-<MÀN HÌNH>-<SỐ>, ví dụ CL-B3-01 — nhìn ID biết ngay lỗi ở màn nào, tìm ra bằng cách nào
- Screenshot ref dạng evidence/task1b/CL-B3-01.png
- Steps to reproduce phải bắt đầu từ trạng thái sạch (chưa đăng nhập hoặc vừa đăng nhập),
  không giả định trạng thái nào tôi không nêu
- Suggested fix phải là thay đổi CỤ THỂ, không phải mục tiêu chung chung
```

## Việc chỉ tôi làm được

- [ ] Chạy từng item trên EMS thật, tuần tự theo ID
- [ ] **Chụp ảnh ngay khi thấy Failed** — dữ liệu dev có thể reset
- [ ] Đặt tên ảnh `CL-B3-01.png` (trùng Bug-ID), lưu vào `evidence/task1b/`
- [ ] Ô N/A phải tự ghi lý do (AI chỉ dự đoán, bạn xác nhận)

## Recheck trước khi commit

- [ ] Không còn ô kết quả trống ở bất kỳ màn hình nào
- [ ] Mọi ❌ có Notes ghi **lý do**, không chỉ mô tả hiện tượng
- [ ] Mở thử 3 ảnh ngẫu nhiên — có đúng nội dung không
- [ ] `grep -c "CL-" 04-findings-log.md` khớp số Failed
- **Commit:** `docs(task1b): run GUI checklist on B2 event detail screen`

---

# PHẦN 2 — User testing 5 người (25đ)

## Chia việc

| Giai đoạn | AI làm | Tôi làm |
|---|---|---|
| Thiết kế | Viết 3 phương án task scenario · định nghĩa Completed/Partial/Failed · soạn 10 câu SUS tiếng Việt · soạn 5 câu probe | Chọn phương án · **tuyển 5 người thật** · chạy pilot |
| Chạy phiên | — | **Toàn bộ.** AI không tham gia được phần này |
| Phân tích | Cấu trúc hoá ghi chú thô thành bảng dòng thời gian · tính SUS · gom pain point · gợi ý severity | **Kiểm verbatim có bị "làm mượt" không** · tự tính tay 1 phiếu SUS · chốt severity |

## ✅ Đã tự dựng công cụ thay Maze — [Vé tham gia kiểm thử EMS](https://claude.ai/code/artifact/aa535ccc-fb5d-4888-aa4b-c5ba924fe107)

Thay vì trả phí/tạo tài khoản Maze, đã dựng một trang tương tác riêng làm đúng việc Maze làm cho task này: hiện nhiệm vụ hướng mục tiêu, mở EMS trong tab mới, **tự động đo giờ**, đếm lỗi/do dự (moderator bấm), khảo sát SUS 10 câu đúng chiều, 5 câu hỏi mở, và xuất kết quả (.json + bản sao dạng bảng markdown dán thẳng vào `a1-session-notes.md`). Không thu thập thông tin liên hệ, không tự ghi âm/ghi hình.

**Khác Maze ở đúng chỗ quan trọng:** trang này **không thay thế cuộc gọi có người quan sát** — nó chỉ là giao diện thu dữ liệu. Bắt buộc vẫn phải mở cuộc gọi chia sẻ màn hình (Zalo/Meet) trong lúc participant dùng trang này, để có think-aloud và verbatim thật — xem lý do ở dưới.

## ⚠️ Vì sao không dùng Maze thuần (đã cân nhắc và loại)

Bạn đã trải nghiệm phía *người được test* qua link Maze, và ban đầu muốn chạy 5 phiên của mình theo cách đó. Được — nhưng **Maze thuần một mình KHÔNG đủ để lấy điểm Task 2**.

Lý do: đề Phase 2 yêu cầu tường minh **moderated** — *"Run sessions — moderated, think-aloud, observe neutrally"*, *"ask them to think aloud"*, *"Record the screen (and audio, with consent) and take structured notes on friction points, errors, hesitations, and verbalised frustration"*. Maze là công cụ **unmoderated remote**: nó đo được click và thời gian, nhưng không có ai ngồi đó nghe người dùng **nói ra** vì sao họ phân vân — mà đúng cái "verbalised frustration" ấy mới là dữ liệu đề đòi.

**Cách làm đúng — chạy hybrid:**

| Thành phần | Ai lo | Cho ra cái gì |
|---|---|---|
| Maze (hoặc chỉ cần link EMS trần) | Công cụ | Time on task, đường click, tỉ lệ hoàn thành — số liệu khách quan, đỡ phải bấm giờ tay |
| **Cuộc gọi có chia sẻ màn hình** (Meet/Zalo) | Bạn ngồi cùng participant | Think-aloud, verbatim, quan sát do dự, ghi màn hình + audio |
| Phiếu SUS 10 câu | Điền cuối phiên | Điểm SUS |

Nghĩa là: participant vẫn làm tác vụ qua link như bạn từng làm, **nhưng bạn có mặt trong cuộc gọi**, yêu cầu họ nói to suy nghĩ, và ghi chú. Vừa có số liệu tự động của Maze, vừa thoả yêu cầu moderated của đề.

**Nếu không dùng được Maze** (trial không cho test live URL cần đăng nhập chẳng hạn) thì bỏ Maze cũng không sao — chỉ cần cuộc gọi + chia sẻ màn hình + ghi màn hình + bấm giờ tay. Đề không yêu cầu công cụ nào cụ thể cho Task 2.

**Nên hỏi lại bạn của bạn ba câu** trước khi quyết định:
1. Dùng gói Maze nào, có giới hạn số người test không?
2. Có test được **live website cần đăng nhập** không, hay chỉ test được prototype?
3. Có xuất được bản ghi màn hình từng người không?

## Prompt 2-1 — Task scenario

```
Tôi làm usability testing cho kịch bản B của EMS (user đăng ký tham dự sự kiện),
trên đúng 3 màn hình: B2 trang chi tiết sự kiện, B3 form đăng ký, B4 My Registrations + vé QR.

Viết 3 phương án task scenario, mỗi phương án:
- Nêu MỤC TIÊU người dùng cần đạt, TUYỆT ĐỐI không liệt kê bước thao tác
- Bắt buộc đi qua cả 3 màn hình trên
- Có tiêu chí "hoàn thành" quan sát được từ bên ngoài
- Thực tế với sinh viên chưa từng thấy hệ thống này

Sau mỗi phương án, nêu rủi ro: chỗ nào người dùng có thể hiểu SAI đề bài.
```

## Prompt 2-2 — Bộ đo + phiếu SUS

```
Với task scenario này: [DÁN PHƯƠNG ÁN ĐÃ CHỌN]

1) Định nghĩa cụ thể Completed / Partial / Failed cho tác vụ này.
2) Định nghĩa thế nào tính là 1 "error", thế nào tính là 1 "hesitation" (nêu ngưỡng giây).
3) Soạn 5 câu hỏi mở phủ đủ 4 chủ đề: clarity, error recovery, speed, trust.
   Câu hỏi phải TRUNG LẬP, không dẫn dắt (tránh "bạn thấy khó dùng chỗ nào?").
4) Soạn phiếu SUS 10 câu bản tiếng Việt, GIỮ ĐÚNG cấu trúc gốc: câu lẻ mang nghĩa
   tích cực, câu chẵn mang nghĩa tiêu cực. Đánh số rõ ràng.
```

→ **Bắt buộc tự kiểm điểm 4:** AI rất hay dịch sai chiều câu chẵn/lẻ, làm hỏng công thức tính điểm.

## Prompt 2-3 — Cấu trúc hoá ghi chú NGAY SAU mỗi phiên

```
Đây là ghi chú thô phiên P[N]: [DÁN GHI CHÚ THÔ]

1) Chuyển thành bảng: | Thời điểm | Hành động | Lời nói nguyên văn | Phân loại | Màn hình |
   Phân loại CHỈ được dùng: error / hesitation / frustration / success
2) Đếm số error và hesitation theo đúng định nghĩa: [DÁN ĐỊNH NGHĨA TỪ PROMPT 2-2]
3) KHÔNG diễn giải nguyên nhân, KHÔNG đề xuất cách sửa ở bước này.
4) GIỮ NGUYÊN VĂN lời participant, không sửa cho mượt, không tóm tắt.
```

## Prompt 2-4 — Tính SUS

```
Đây là câu trả lời SUS của 5 participant, thang 1-5: [DÁN BẢNG 10 CÂU × 5 NGƯỜI]

1) Tính điểm SUS cho từng người: câu lẻ (1,3,5,7,9) lấy (điểm − 1);
   câu chẵn (2,4,6,8,10) lấy (5 − điểm); cộng lại rồi × 2.5.
2) Hiện BƯỚC TÍNH của participant P1 để tôi đối chiếu bằng tay.
3) Tính trung bình, trung vị, độ lệch chuẩn.
4) Đối chiếu với mốc tham chiếu: < 68 dưới trung bình, 68 trung bình, > 80.3 tốt.
5) Chỉ ra câu nào bị chấm thấp nhất trên cả 5 người và điều đó gợi ý vấn đề gì.
```

## Prompt 2-5 — Phân tích tổng

```
Đây là dữ liệu 5 phiên đã cấu trúc hoá: [DÁN 5 BẢNG DÒNG THỜI GIAN + BẢNG METRIC]

1) Gom các điểm ma sát tương tự thành nhóm; mỗi nhóm ghi rõ MẤY TRÊN 5 người gặp phải,
   kèm trích dẫn nguyên văn làm bằng chứng.
2) Phân loại từng nhóm: BUG ĐƠN LẺ hay VẤN ĐỀ THIẾT KẾ HỆ THỐNG — nêu căn cứ.
3) Gán severity 0-4 theo thang Nielsen, giải thích căn cứ từng mức.
4) Với mỗi finding, viết 1 khuyến nghị là THAY ĐỔI CỤ THỂ (vd "gộp 2 bước đăng ký
   thành 1 màn"), không phải mục tiêu ("cải thiện trải nghiệm").
5) Xếp ưu tiên P0/P1/P2 kèm ước tính chi phí và tác động.

Chỉ dùng dữ liệu tôi dán ở trên. Nếu một kết luận không có bằng chứng trong dữ liệu đó,
hãy ghi rõ "không đủ dữ liệu" thay vì suy đoán.
```

→ Điểm ràng buộc cuối cùng là quan trọng nhất ở đây: AI có xu hướng "điền vào chỗ trống" bằng vấn đề usability kinh điển mà 5 người của bạn chưa hề gặp.

## Việc chỉ tôi làm được

- [ ] Tuyển **5 người thật, ngoài lớp**, liên hệ kiểm chứng được, che 4 số giữa
- [ ] Chạy pilot với người thứ 6
- [ ] Đọc nguyên văn câu mở đầu cho cả 5 người (để đồng nhất)
- [ ] Bấm giờ, ghi chú, ghi màn hình
- [ ] Quan sát trung lập — không gợi ý, không giải thích hộ
- [ ] Cho điền SUS **trước**, hỏi câu mở **sau**
- [ ] Dọn dữ liệu giữa các phiên nếu cần trạng thái sạch

## Recheck trước khi commit

- [ ] Đúng 5 người, **không ai học lớp này**
- [ ] Đọc lại bảng dòng thời gian: lời participant có còn nguyên văn không (AI hay làm mượt)
- [ ] Tự tính tay điểm SUS của P1, so với kết quả AI
- [ ] Mỗi finding có: số người gặp / severity / heuristic / ảnh / khuyến nghị
- [ ] Bằng chứng thô đã nằm trong `evidence/task2/`
- **Commit:** `docs(task2): add session P3 notes and SUS score`

---

# PHẦN 3 — Cross-browser / Cross-platform (25đ)

## Chia việc

| Bước | AI làm | Tôi làm |
|---|---|---|
| 1 | Thiết kế bộ tổ hợp tối thiểu + bảng kiểm tra độ phủ | Đếm lại bảng độ phủ bằng tay |
| 2 | — | **Chạy BrowserStack/LambdaTest, chụp mọi ô** |
| 3 | Phân tích lỗi theo OS / browser engine / device class | Xác nhận lỗi có tái hiện ở môi trường khác không |
| 4 | Viết block chi tiết cho ô Fail | Kiểm ảnh có overlay đủ 3 thứ không |

## Prompt 3-1 — Thiết kế ma trận

```
Tôi cần ma trận tương thích cho 3 màn hình web (B2 trang chi tiết sự kiện,
B3 form đăng ký, B4 My Registrations + vé QR) của EMS. Ràng buộc:
- 3 OS: Windows, macOS, và Android HOẶC iOS
- 5 browser: Chrome, Firefox, Safari, Edge, Opera (hoặc Samsung Internet trên mobile)
- 3 device class: desktop, tablet, phone
- KHÔNG cần đủ 45 tổ hợp, nhưng với TỪNG màn hình phải phủ mọi OS ≥ 1 lần,
  mọi browser ≥ 1 lần, mọi device class ≥ 1 lần

1) Đề xuất bộ tổ hợp NHỎ NHẤT thoả điều kiện. Giải thích vì sao không thể nhỏ hơn.
2) Chỉ ra tổ hợp BẤT KHẢ THI về kỹ thuật (vd Safari trên Windows) và cách xử lý.
3) Lập bảng kiểm tra độ phủ: mỗi giá trị của mỗi chiều được phủ bởi ô nào.
4) Lưu ý: trên iOS mọi trình duyệt đều dùng WebKit — nêu rõ hệ quả cho việc chọn OS.
```

→ **Tự đếm lại bảng ở điểm 3.** Đây là chỗ AI hay tuyên bố "đã phủ đủ" trong khi thiếu một giá trị.

## Prompt 3-2 — Lên kịch bản chụp cho từng màn

```
Với bộ tổ hợp đã chốt: [DÁN BẢNG Ô]

Viết checklist thao tác cho MỖI ô, sao cho mỗi ảnh chụp thể hiện được nhiều thông tin nhất:
- B2: cần thấy banner, lịch trình, nút Đăng ký ở trạng thái nào
- B3: cần thấy form ở trạng thái nào (trống / đã điền / đang báo lỗi)
- B4: cần thấy badge trạng thái và mã QR

Nêu rõ với mỗi màn: cái gì cần kiểm về HIỂN THỊ, cái gì cần kiểm về HÀNH VI,
cái gì cần kiểm về RESPONSIVE.
```

## Prompt 3-3 — Phân tích sau khi chạy

```
Đây là kết quả ma trận thật của tôi: [DÁN 3 BẢNG]

1) Nhóm các Fail theo: OS / browser engine (Blink, Gecko, WebKit) / device class.
2) Với mỗi nhóm, đưa giả thuyết nguyên nhân kỹ thuật KIỂM CHỨNG ĐƯỢC.
3) Chỉ ra Fail nào KHÔNG phải lỗi tương thích mà là bug chung của ứng dụng
   (vì nó xuất hiện ở mọi môi trường).
4) Ghi rõ chỗ nào là GIẢ THUYẾT của bạn, chỗ nào là kết luận từ dữ liệu tôi cung cấp.

Chỉ dùng dữ liệu tôi dán ở trên. Nếu một kết luận không có bằng chứng trong dữ liệu đó,
hãy ghi rõ "không đủ dữ liệu" thay vì suy đoán.
```

## Việc chỉ tôi làm được

- [ ] Đăng ký trial BrowserStack / LambdaTest bằng tài khoản của mình
- [ ] Chạy từng ô, **chụp ảnh MỌI ô** (không chỉ ô Fail)
- [ ] Đảm bảo mỗi ảnh thấy rõ **3 thứ**: email `pvnduy23@clc.fitus.edu.vn` + URL EMS + tên browser/OS/device
- [ ] Đặt tên ảnh `B2_chrome_windows_desktop.png`, lưu `evidence/task3/`
- [ ] Ghi rõ ô nào emulator, ô nào thiết bị thật
- [ ] B3/B4 cần đăng nhập → mỗi phiên BrowserStack là trình duyệt sạch, phải đăng nhập lại từng ô

## Recheck trước khi commit

- [ ] Tự đếm: từng màn hình đủ 3 OS, 5 browser, 3 device class
- [ ] `ls evidence/task3/ | wc -l` ≈ số ô × 3 màn
- [ ] Mở ngẫu nhiên 3 ảnh — có nhìn rõ overlay email không
- [ ] Mỗi Fail có ghi chú **loại lỗi cụ thể**
- **Commit:** `docs(task3): cross-platform run on macos safari, 3 screens`

---

# PHẦN 4 — Findings log (10đ)

## Chia việc

| AI làm | Tôi làm |
|---|---|
| Hợp nhất findings từ 3 nguồn về đúng 9 cột · phát hiện trùng lặp · kiểm nhất quán số liệu giữa các file | **Submit từng finding lên Google Form** · điền timestamp · đối chiếu số lượng |

## Prompt 4-1 — Hợp nhất

```
Đây là findings từ 3 nguồn:
- Từ checklist (prefix CL-): [DÁN]
- Từ user testing (prefix US-): [DÁN]
- Từ cross-platform (prefix CP-): [DÁN]
- Từ khảo sát EMS ban đầu (prefix SV-): [DÁN]

1) Hợp nhất thành một bảng đúng 9 cột theo yêu cầu đề:
   ID · Scenario/Screen · Type (Bug|Usability) · Description · Steps/Heuristic
   · Severity · Suggested fix · Screenshot ref · Form-submission timestamp
2) Chỉ ra các finding TRÙNG NHAU về bản chất giữa các nguồn (vd cùng một lỗi
   phát hiện cả ở checklist lẫn user testing) và đề xuất gộp hay giữ riêng, kèm lý do.
3) Kiểm tra: có ID nào trùng hoặc nhảy cóc không.
4) Lập 3 bảng thống kê: theo nguồn, theo severity, theo màn hình.
5) Để trống cột timestamp — tôi tự điền sau khi submit form.
```

## Prompt 4-2 — Kiểm nhất quán toàn bài (chạy trước khi nộp)

```
Kiểm tra tính nhất quán số liệu giữa các file sau, chỉ ra MỌI chỗ lệch:
- README.md test summary: [DÁN]
- 00-main-report.md các bảng tổng hợp: [DÁN]
- 01-checklist-execution.md bảng tổng: [DÁN]
- 04-findings-log.md 3 bảng thống kê: [DÁN]

Với mỗi chỗ lệch: nêu file nào ghi số nào, và số nào có khả năng đúng, kèm lý do.
```

## Việc chỉ tôi làm được

- [ ] Submit **từng finding** lên https://forms.gle/CJQFQCAXcsDbXDMM9 bằng email MSSV
- [ ] Ghi lại timestamp mỗi lần submit
- [ ] Đối chiếu: số dòng trong log **=** số lần submit form

## Recheck

- [ ] `grep -c "^| CL-\|^| US-\|^| CP-\|^| SV-" 04-findings-log.md` = số lần submit
- [ ] Mọi Screenshot ref trỏ tới file có thật: kiểm bằng `ls evidence/`
- **Commit:** `docs(findings): aggregate 3 sources into findings log`

---

# PHẦN 5 — Agent Skills + video (10đ)

## Chia việc

| AI làm | Tôi làm |
|---|---|
| Viết/tinh chỉnh 3 SKILL.md theo đúng cách mình đã thực sự làm bài · viết kịch bản quay | **Quay video** · upload YouTube · dán link |

## Prompt 5-1 — Tinh chỉnh skill sau khi làm xong bài

```
Đây là 3 SKILL.md hiện tại: [DÁN]
Và đây là những gì tôi THỰC SỰ đã làm khi chạy bài: [MÔ TẢ NGẮN QUY TRÌNH THỰC TẾ,
kể cả những chỗ khác với skill]

Cập nhật 3 skill sao cho phản ánh đúng quy trình thực tế, không phải lý thuyết suông:
- Bước nào tôi làm thật mà skill chưa có → thêm vào
- Bước nào skill có mà thực tế bỏ qua → xoá hoặc ghi rõ điều kiện áp dụng
- Prompt nào tôi dùng thật và hiệu quả → đưa vào skill nguyên văn
- Chỗ nào tôi phải sửa output AI → thêm mục "người review cái gì"
```

## Việc chỉ tôi làm được

- [ ] Quay ít nhất 1 video end-to-end (khuyến nghị skill `hw03-gui-checklist`)
- [ ] Video **phải có cảnh sửa/loại output của AI** — đây là bằng chứng human review
- [ ] Hiện email MSSV trong video ít nhất một lần
- [ ] Upload YouTube chế độ Unlisted, **kiểm link mở được khi chưa đăng nhập**
- **Commit:** `docs(task5): refine agent skills after real run, add demo link`

---

# PHỤ LỤC BẮT BUỘC — thiếu là 0 điểm cả bài

## AI Audit Report — `appendix/a3-ai-audit-report.md`

**Cách làm đúng: ghi NGAY SAU mỗi phiên AI, đừng dồn cuối.** Dồn cuối là quên prompt và giờ, rồi phải bịa — mà bịa thì hỏng đúng cái đề đang chấm.

Prompt dùng cuối mỗi phiên:

```
Tóm tắt phiên làm việc vừa rồi thành một block cho AI Audit Report, gồm đúng 5 mục:
- Tool: [tên công cụ + model]
- Date & Time:
- Prompt: NGUYÊN VĂN prompt tôi đã dùng, không tóm tắt
- AI Output: tóm tắt AI đã tạo ra gì, đủ để người chấm hiểu
- Human Review Notes: ĐỂ TRỐNG — tôi tự điền
```

→ Ô **Human Review Notes** bạn tự viết. Đây là phần được chấm kỹ nhất. Viết cụ thể: *"Đã tự chạy lại BV-03 trên UI để kiểm chứng, kết quả khác dự đoán của AI ở chỗ..."*

## AI Critique — `appendix/a4-ai-critique.md`

```
Đây là toàn bộ AI Audit Report của tôi: [DÁN]
Và mục AI Gap Analysis trong main report: [DÁN]

Rút ra 3 ví dụ THẬT từ dữ liệu trên: một lần AI SAI, một lần AI THIẾU, một lần AI THIÊN LỆCH.
Với mỗi ví dụ nêu rõ: AI nói gì, thực tế ra sao, và VÌ SAO AI không bắt được.
Chưa viết thành đoạn văn — chỉ liệt kê 3 ví dụ dạng gạch đầu dòng.
```

→ Sau đó **bạn tự viết đoạn 200–300 từ**. Đếm từ trước khi kết luận là đạt:

```bash
wc -w 23127183_HW03_AI_GUIUsability_EMS_100/appendix/a4-ai-critique.md
```

## README + git log

```
Đây là số liệu cuối cùng của tôi: [DÁN các bảng thống kê]
Điền vào bảng test summary và bảng self-assessment trong README.md.
Với mỗi mục tự chấm dưới điểm tối đa, viết 1 câu CĂN CỨ tự trừ điểm dựa trên
khiếm khuyết có thật trong bài, không viết chung chung.
```

---

# BẢNG TỔNG — việc AI không bao giờ làm thay được

| Việc | Vì sao | Hạng mục |
|---|---|---|
| Chạy checklist trên EMS thật | AI không thấy màn hình | 1B |
| Chụp ảnh EMS thật | Đề §12 chống gian lận | 1B, 3 |
| Tuyển & chạy 5 phiên với người thật | TA gọi xác minh 2 người | 2 |
| Chạy BrowserStack + overlay email | Cần tài khoản trial của bạn | 3 |
| Submit Google Form bằng email MSSV | Cần đăng nhập tài khoản trường | 4 |
| Quay video demo | Phải là màn hình thật của bạn | 5 |
| Viết Human Review Notes | Chỉ bạn biết đã kiểm chứng gì | Phụ lục |
| Chốt severity cuối cùng | Trách nhiệm chuyên môn là của bạn | 1B, 2, 3 |
