# HƯỚNG DẪN DỰNG STUDY MAZE — từng ô, từng nút

**Dựa trên ảnh chụp thật giao diện Maze bạn gửi** (block "Website Test", trong study `Demo / New study 1`).
**Nội dung dán vào từng ô** lấy nguyên văn từ: `02-usability-report.md` §1 (task scenario, tiêu chí hoàn thành, câu hỏi mở) và `appendix/a2-sus-scoring.md` (10 câu SUS).

> **Ký hiệu dùng trong file này:**
> ✅ = đã thấy đúng giao diện này trong ảnh bạn gửi, làm theo được ngay.
> ⚠️ `[ ]` = **chưa thấy giao diện thật** của phần này — tôi suy ra từ tên block/tab và cách Maze thường làm, có thể lệch chi tiết. Bạn tự đối chiếu, và **chụp ảnh gửi tôi** nếu muốn tôi viết lại chính xác như phần ✅.

---

## Bản đồ toàn bộ study (Build cần có đúng các block này, theo thứ tự)

> ⚠️ **Sửa ngày 06/08/2026, dựa trên ảnh luồng Maze của một bạn cùng lớp (project `FITUS-E... / Software Testing Usability E...`).** Ba điều học được từ đó và áp dụng luôn: (1) thu **Họ và tên + liên hệ** ngay trong Maze bằng 2 block `Simple Input`, không chỉ hỏi miệng — có bản ghi timestamped làm bằng chứng; (2) nội dung mỗi block viết đủ chi tiết để participant tự làm được không cần hỏi lại; (3) bật **Screen recording + Camera recording** trong cài đặt study trước khi Publish. Đồng thời **cắt khối 5 câu hỏi mở** khỏi bản trước — cuộc gọi Zalo/Meet song song đã lấy think-aloud trực tiếp, hỏi lại trong Maze là hỏi trùng và tốn thời gian mỗi phiên khi thời gian chuẩn bị không còn nhiều.

```
1. Welcome                          ✅ đã có sẵn — sửa nội dung
2. [MỚI] Họ và tên (Simple Input)   ⚠️
3. [MỚI] Thông tin liên lạc (Simple Input) ⚠️
4. Website Test                     ✅ đã có sẵn — điền 3 ô còn thiếu
5. [MỚI] Simple Question — outcome tự nhận  ⚠️
6. [MỚI] SUS hoặc 10× Opinion Scale ⚠️
7. Thank you                        ✅ đã có sẵn — sửa nội dung
```

Trạng thái hiện tại của bạn: đã có (1), (4), (7) do Maze tự tạo khi bấm "New study". Việc phải làm: **thêm 2 block thu thông tin** ở (2)(3), **điền nốt 3 ô trống trong block (4)**, rồi **thêm 2 nhóm block mới** ở (5)(6), và **bật recording** trước khi Publish (PHẦN 7b).

---

## PHẦN 1 · Block "Website Test" ✅ (đúng ảnh bạn gửi)

Bạn đang ở đúng màn hình này. Bên trái là danh sách block (Welcome → **Website Test** đang chọn, viền hồng vì còn lỗi → Thank you). Giữa là form điền nội dung. Phải là khung xem trước participant sẽ thấy.

### Ô 1 — `Task*` (bắt buộc, đang trống, đang báo lỗi đỏ)

> Placeholder trong ảnh: *"Write a short sentence that summarizes the task"* — nghĩa là ô này chỉ cần **một câu ngắn tóm tắt**, không phải toàn bộ kịch bản.

**Dán nguyên văn:**
```
Đăng ký tham dự một sự kiện sắp diễn ra và xem lại đăng ký của bạn
```

### Ô 2 — `Description` (không có dấu `*`, không bắt buộc nhưng PHẢI điền)

> Placeholder: *"Give testers details to complete the mission"* — đây mới là chỗ chứa mục tiêu đầy đủ.

⚠️ **Đổi ngày 06/08/2026 — bỏ QR khỏi kịch bản.** QR hoá ra là mã cố định theo tài khoản, không đổi theo có đăng ký hay không, nên dùng nó làm tiêu chí hoàn thành là phép đo yếu. Đổi tiêu chí sang **My Activities** — chỉ hiện đúng khi đăng ký thật sự thành công.

**Dán nguyên văn:**
```
Khoa sắp có một workshop mà bạn muốn tham dự. Hãy đăng ký tham gia, rồi cho mình xem lại đăng ký đó trong hồ sơ của bạn.
```

⚠️ **Đừng thêm câu nào kiểu "bước 1 vào Events, bước 2 chọn sự kiện..."** — đề cấm tường minh việc chỉ đường từng bước, chỉ được nêu mục tiêu. Nhưng **được phép mô tả bối cảnh đầy đủ** (ai, muốn gì, vì sao) để participant không phải đoán — đây là điều học được từ luồng của bạn cùng lớp: nội dung càng chi tiết về *bối cảnh*, participant càng ít phải hỏi lại giữa chừng.
🔴 **Không nhắc gì tới My Activities hay đường vào Profile.** Participant tự tìm đường xác nhận đăng ký ở đâu chính là dữ liệu quan trọng nhất của phiên (xem §1.1 trong `02-usability-report.md`) — lộ ra là mất luôn phép đo.

### Ô 3 — `Task link*` (bắt buộc, đang trống, đang báo lỗi đỏ)

Bấm nút **`+ Add link`** → một ô nhập URL sẽ hiện ra → dán:
```
https://prod-dev.ems-fitus.cloud
```

### Mục "Conditions" (cuối form, có công tắc đang tắt)

**Bỏ qua, không bấm.** Đây là logic rẽ nhánh (hiện/ẩn block theo điều kiện) — study của bạn chạy tuyến tính, không cần.

### Sau khi điền đủ 3 ô

- Khung xem trước bên phải sẽ đổi từ hình minh hoạ chung sang đúng nội dung bạn vừa nhập.
- Badge cảnh báo đỏ **"2"** cạnh tên block ở danh sách bên trái sẽ **biến mất**.
- Viền hồng của block chuyển về viền thường.

**Ghi chú quan trọng về đo giờ:** dòng chữ trong khung xem trước — *"This task will open in a new window. Once you're done, close the window and return here to continue the study."* — nghĩa là **Maze tự động đo giờ**: bắt đầu tính từ lúc participant bấm "Start Task" (mở EMS ở cửa sổ mới), kết thúc khi họ **đóng cửa sổ đó và quay lại tab Maze**. Bạn không cần tự bấm giờ tay như bản artifact cũ — nhưng **phải dặn participant nhớ đóng cửa sổ EMS khi xong**, nếu không Maze sẽ tính dư thời gian.

- [ ] Đã điền đủ 3 ô, badge lỗi đã biến mất

---

## PHẦN 2 · Block "Welcome" ⚠️ *(chưa thấy giao diện thật)*

Bấm vào **"Welcome"** ở đầu danh sách bên trái để mở form chỉnh sửa (cấu trúc form nhiều khả năng giống Website Test: có ô tiêu đề + ô mô tả/nội dung, có thể thêm ảnh). **Tên ô có thể khác chút** so với suy đoán dưới — cứ tìm ô có ý nghĩa tương ứng.

**Ô tiêu đề (title):**
```
Trước khi bắt đầu
```

**Ô nội dung/mô tả:**
```
Cảm ơn bạn đã dành khoảng 20–25 phút giúp mình kiểm thử EMS — hệ thống quản lý sự kiện của Khoa CNTT, cho bài tập môn Kiểm thử phần mềm.

Ba điều trước khi bắt đầu:
1. Mình thử nghiệm TRANG WEB, không thử nghiệm bạn — bấm nhầm hay không tìm thấy nút là lỗi của giao diện.
2. Xin bạn nói to những gì đang nghĩ trong lúc làm — mình đang nghe qua cuộc gọi đang mở song song với bạn.
3. Mình sẽ không trả lời câu hỏi trong lúc bạn làm, để xem hệ thống tự giải thích được đến đâu.

Mình đã chuẩn bị sẵn tài khoản demo và sẽ đăng nhập giúp bạn trước khi bắt đầu — bạn không cần tạo tài khoản gì.
```

- [ ] Đã sửa Welcome — ⚠️ đối chiếu lại tên ô thật, báo tôi nếu khác

---

## PHẦN 2b · Thêm 2 block thu Họ và tên + Liên hệ ⚠️ *(theo mẫu của bạn cùng lớp)*

Bấm **`+ Add block`** ngay dưới "Welcome" (trước "Website Test"). Tìm loại block **`Simple Input`** (ô nhập chữ ngắn, một dòng) — đúng loại bạn cùng lớp dùng trong ảnh gửi.

**Block 1 — Họ và tên:**
```
Bạn tên gì?
```

**Block 2 — Thông tin liên lạc:**
```
Cho mình xin số điện thoại hoặc Zalo/email để liên hệ nếu cần xác minh (không công khai)
```

**Vì sao thêm 2 block này thay vì chỉ hỏi miệng:** Maze tự lưu câu trả lời kèm timestamp trong tab `Analyze`, thành **bằng chứng có mốc thời gian** rằng đây là người thật — mạnh hơn ghi chú tay khi TA gọi ngẫu nhiên xác minh (đề §12). Dữ liệu này **nhạy cảm**, xử lý theo đúng quy tắc đã có: bảng participant trong `02-usability-report.md` §1.4 chỉ ghi **bản đã che 4 số giữa**; bản đầy đủ giữ ngoài repo.

- [ ] Đã thêm 2 block, đặt đúng vị trí SAU Welcome, TRƯỚC Website Test
- [ ] Đã đối chiếu đúng tên loại block ("Simple Input" hay tên khác) — sửa lại nếu Maze gọi khác

---

## PHẦN 3 · Thêm block mới — chọn kết quả tự nhận ⚠️ *(chưa thấy giao diện thật)*

Ở danh sách bên trái, bấm **`+ Add block`** ngay dưới block "Website Test" (không phải dưới Thank you — thứ tự block quyết định thứ tự participant làm). Maze sẽ hiện một danh sách loại block để chọn.

**Tìm và chọn loại block:** `Simple Question` hoặc `Multiple Choice` (câu hỏi trắc nghiệm một lựa chọn). ⚠️ Tên chính xác trong menu có thể khác — tìm loại nào cho phép **chọn 1 trong nhiều lựa chọn có sẵn**, không phải ô nhập chữ tự do.

**Ô câu hỏi:**
```
Bạn đã hoàn thành nhiệm vụ đến đâu?
```

**3 lựa chọn** (đúng định nghĩa đã chốt ở `02-usability-report.md` §1.1 — dán mô tả vào phần phụ/subtitle của từng lựa chọn nếu block có chỗ cho việc đó):

| Lựa chọn | Mô tả kèm theo |
|---|---|
| Hoàn thành | Tôi đăng ký được và tự tìm ra đúng đăng ký đó trong hồ sơ của mình |
| Một phần | Tôi đăng ký được nhưng không tìm ra xác nhận trong hồ sơ |
| Không hoàn thành | Tôi không đăng ký xong được |

- [ ] Đã thêm block chọn kết quả — ⚠️ chưa xác nhận đúng loại block

---

## PHẦN 4 · Thêm khảo sát SUS ⚠️ *(chưa thấy giao diện thật)*

### Cách 1 — nếu Maze có sẵn block SUS (thử trước)

Bấm `+ Add block` → gõ tìm `SUS` hoặc `System Usability Scale` trong ô tìm loại block. Nếu có, chọn nó — Maze sẽ tự tạo đủ 10 câu và tự tính điểm theo đúng công thức chuẩn, đỡ phải làm bước dưới.

### Cách 2 — nếu KHÔNG có block SUS sẵn (dự phòng)

Thêm **10 block riêng**, mỗi block một loại cho phép chọn thang điểm 1–5 (Maze có thể gọi là `Opinion Scale` hoặc `Rating Scale`). Với mỗi block, dán đúng 1 câu theo bảng dưới — **giữ đúng thứ tự Q1→Q10, đừng đảo**, vì công thức tính điểm SUS phụ thuộc vào đúng câu nào là câu thuận/nghịch:

| # | Dán vào ô câu hỏi |
|---|---|
| Q1 | Tôi nghĩ rằng tôi sẽ muốn sử dụng hệ thống này thường xuyên. |
| Q2 | Tôi thấy hệ thống này phức tạp một cách không cần thiết. |
| Q3 | Tôi thấy hệ thống này dễ sử dụng. |
| Q4 | Tôi nghĩ tôi sẽ cần người có chuyên môn kỹ thuật hỗ trợ mới dùng được hệ thống này. |
| Q5 | Tôi thấy các chức năng trong hệ thống này được tích hợp ăn khớp với nhau. |
| Q6 | Tôi thấy hệ thống này có quá nhiều điểm thiếu nhất quán. |
| Q7 | Tôi cho rằng hầu hết mọi người sẽ học cách dùng hệ thống này rất nhanh. |
| Q8 | Tôi thấy hệ thống này rườm rà, khó thao tác. |
| Q9 | Tôi cảm thấy tự tin khi sử dụng hệ thống này. |
| Q10 | Tôi cần học khá nhiều thứ trước khi có thể bắt đầu dùng hệ thống này. |

Nếu block có ô "thang đo" (scale), đặt **1 đến 5**, nhãn đầu **"Rất không đồng ý"**, nhãn cuối **"Rất đồng ý"**.

- [ ] Đã thêm SUS — ghi rõ đã dùng Cách 1 hay Cách 2: _______
- [ ] Nếu Cách 2: đã kiểm tra lại đúng thứ tự 10 câu, không câu nào bị đảo

---

> ⚠️ **Bỏ ngày 06/08/2026 — không còn "PHẦN 5 · 5 câu hỏi mở" trong Maze.** Bốn chủ đề bắt buộc của đề (clarity · error recovery · speed · trust) vẫn được hỏi đủ, nhưng chuyển hẳn sang hỏi miệng trong cuộc gọi Zalo/Meet song song — xem `02-usability-report.md` §1.3, ghi lại ở `appendix/a1-session-notes.md`. Lý do: cuộc gọi đã có think-aloud trực tiếp, hỏi lại 5 câu này trong Maze là hỏi trùng dữ liệu, tốn thêm ~5 phút mỗi phiên mà không thêm góc nhìn mới.

## PHẦN 6 · Block "Thank you" ⚠️ *(chưa thấy giao diện thật)*

Bấm vào **"Thank you"** ở cuối danh sách bên trái.

**Ô tiêu đề:**
```
Cảm ơn bạn rất nhiều!
```

**Ô nội dung:**
```
Vậy là xong rồi. Cảm ơn bạn đã dành thời gian giúp mình. Quay lại cuộc gọi để mình hỏi thêm vài câu nhé!
```

- [ ] Đã sửa Thank you

---

## PHẦN 7 · Trước khi Publish

Nhìn lên góc trên bên phải màn hình:

- **Dấu tròn xanh có dấu tick** (cạnh nút Preview) = study đã hợp lệ, đủ điều kiện Publish. Nếu vẫn còn dấu cảnh báo, mở lại từng block xem còn ô nào báo lỗi đỏ.
- **Nút `Preview`** (nút xám, cạnh Publish) — bấm để tự chạy thử toàn bộ study **một mình bạn**, không tính vào pilot hay 5 người. Kiểm tra:
  - [ ] Bấm "Start Task" có mở đúng `prod-dev.ems-fitus.cloud` ở cửa sổ mới không
  - [ ] Đăng nhập/đăng ký EMS trong cửa sổ đó có bình thường không (site yêu cầu đăng nhập — xem đã hoạt động đúng trong luồng Maze chưa)
  - [ ] Đóng cửa sổ EMS quay lại Maze — thời gian đo được có hợp lý không (không phải 0 giây hay vài phút vô lý)
  - [ ] 2 block Họ và tên/Liên hệ + Simple Question outcome + cả 10 câu SUS đều hiện đúng, đúng thứ tự
- **Nút `Publish study`** (nút tím đậm) — chỉ bấm sau khi Preview không có gì bất thường.

- [ ] Đã Preview và tự chạy thử một lượt, không có lỗi

### PHẦN 7b · Bật Screen recording + Camera recording ⚠️ *(theo mẫu của bạn cùng lớp — chưa thấy giao diện thật của phần này)*

Ảnh của bạn cùng lớp cho thấy tab `Analyze` có clip video kèm thời lượng cho mỗi response — nghĩa là study của họ có bật ghi hình. Vị trí bật thường nằm trong **cài đặt study** (icon bánh răng hoặc menu `Settings`/`Study settings`, thường ở góc trên cùng bên trong màn hình Build, tách biệt với từng block) — tìm mục có tên gần với `Screen recording` và `Camera recording` (hoặc gộp chung `Recording`), bật cả hai.

⚠️ **Nếu KHÔNG thấy công tắc này** — nhiều khả năng là giới hạn gói (recording thường thuộc gói trả phí, không có ở Free tier). Trước khi kết luận là không làm được: hỏi bạn cùng lớp xem study của họ có nằm trong **cùng một Maze workspace/team** (project tên `FITUS-E...` gợi ý có thể là workspace chung của lớp/khoa) hay là tài khoản Free cá nhân — nếu là workspace chung thì bạn có thể đã có sẵn quyền truy cập mà chưa biết, hoặc cần được thêm vào workspace đó.

**Nếu bật được:** cập nhật lại câu xin phép ở Welcome và ở `evidence/task2/test-request.md` — hiện đang chỉ xin phép "ghi màn hình và giọng nói" qua cuộc gọi, cần thêm rõ **Maze cũng tự ghi màn hình + camera trong lúc làm task**, dùng cho cùng mục đích (chấm điểm, không công khai, xoá sau khi chấm).

**Nếu không bật được:** không sao — cuộc gọi Zalo/Meet vẫn là nguồn ghi hình chính, đã đủ đáp ứng đề §12. Recording của Maze chỉ là bằng chứng bổ sung, không bắt buộc.

- [ ] Đã tìm và bật (hoặc xác nhận không có quyền bật) Screen recording + Camera recording
- [ ] Nếu bật được: đã sửa lại câu xin phép ở Welcome và `test-request.md`

---

## PHẦN 8 · Sau khi Publish — lấy link, chạy phiên, lấy kết quả ⚠️ *(chưa thấy giao diện thật)*

Thanh trên cùng có 4 bước: `Build` (vừa xong) → `Recruit` → `Analyze` → `Report`.

- **Tab `Recruit`:** nhiều khả năng có nút dạng "Share link" hoặc "Copy link" — đây là link gửi cho 5 người + người pilot. Thêm `?p=P1`, `?p=P2`... vào cuối link nếu Maze hỗ trợ tham số URL (không chắc Maze đọc được tham số này như bản artifact cũ — nếu không, cứ hỏi miệng mã participant qua cuộc gọi rồi tự ghi chú, không ảnh hưởng gì).
- **Tab `Analyze`:** nơi xem kết quả từng người sau khi họ làm xong — mở sau mỗi phiên, copy dữ liệu (thời gian, kết quả outcome, câu trả lời SUS + probe) dán vào `appendix/a1-session-notes.md` theo đúng bảng đã có sẵn ở đó.
- **Tab `Report`** (có icon mở tab mới): báo cáo tổng hợp dạng trình bày sẵn — có thể dùng làm phụ lục tham khảo, nhưng **không thay thế** `02-usability-report.md` — báo cáo chính vẫn phải tự viết theo đúng khung đã có.

- [ ] Đã lấy được link chia sẻ từ tab Recruit
- [ ] ⚠️ Đã kiểm tra Analyze hiển thị đủ dữ liệu cần (thời gian, outcome, SUS, probe) — nếu thiếu gì, báo tôi để tính phương án bù (vd merge với dữ liệu ghi tay từ cuộc gọi)

---

## Nhắc lại điều quan trọng nhất

**Maze KHÔNG thay được cuộc gọi có người quan sát**, kể cả khi có bật Screen recording + Camera recording. Camera ghi lại được mặt và màn hình, nhưng không có ai chủ động nhắc "nói to lên" khi participant im lặng, và không hỏi được câu follow-up ngay tại chỗ khi thấy họ do dự. Recording của Maze là **bằng chứng bổ sung** cho `evidence/task2/`, không phải nguồn think-aloud chính — phần đó vẫn chỉ có được khi bạn ngồi trong cuộc gọi Zalo/Meet cùng participant lúc họ làm task. Xem đầy đủ lý do ở `docs/QUY_TRINH_AI_VA_TOI.md` Phần 2.

## Việc cần gửi lại cho tôi

Nếu muốn phần ⚠️ ở trên chính xác như PHẦN 1 (dựa trên ảnh thật thay vì suy đoán), chụp gửi tôi màn hình của: Welcome screen, menu chọn loại block khi bấm `+ Add block`, một block Simple Question / Opinion Scale / Open Question bất kỳ, và tab Recruit. Tôi sẽ viết lại đúng theo ảnh, thay các đoạn ⚠️ thành ✅.
