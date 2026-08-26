# 🎨 DESIGN SYSTEM — Môn Tiếng Anh (Aiducation Cream · Jade · Sage · Accent) — v2.7

> **v2.7** — lịch sử thay đổi đầy đủ qua từng version xem `00_changelog_tiengAnh.md`. File này chỉ giữ quy tắc hiện hành.
> **Mới ở v2.7 (đúc kết từ QA Writing Unit 2 Lớp 12 — mọi Activity viết bài dùng Submit tường minh):**
> 1. **Mục 9.17 — bổ sung biến thể "Submit tường minh cho textarea tự do":** trước đây Submit tường
>    minh chỉ có 1 dạng (check "đã điền đủ mọi ô trong 1 group" — hợp bảng điền như Read & Extract),
>    chưa có dạng cho 1 ô textarea tự do kèm ngưỡng số từ. Bổ sung hàm mới để dùng khi giáo viên muốn
>    MỌI Activity viết đoạn (không chỉ Activity chặn bước tiếp theo) đều bắt học sinh bấm Submit thay
>    vì tự mở khoá qua sự kiện `input`.
> 2. **Mục 9.17 — định nghĩa rõ khung hiển thị Model answer sau khi mở khoá:** trước đây code mẫu gọi
>    `onclick="openPopup(...)"` nhưng hàm này chưa từng được định nghĩa ở đâu. Từ giờ Model answer tái
>    dùng đúng pattern overlay bottom-sheet đã có ở Mục 1.14 (file engine) — không viết component mới.
> 3. **Component mới 4.15b — Write Hint:** khối 💡 hint tĩnh hiển thị TRƯỚC khi học sinh viết, dùng cho
>    Writing khi bảng scaffold không đủ tự giải thích (VD Guided Writing hỗ trợ giảm không có sentence
>    starter, Independent Writing không có bảng gợi ý). Khác Mục 9.2 (Mục 9.2 chỉ cấm hint cho MCQ).
> 4. **Mục 1 — bổ sung hướng dẫn "màu accent cục bộ theo Unit":** cách khai báo custom property CSS
>    chỉ scope trong 1 component/khối minh hoạ cụ thể, không đụng bảng token toàn cục.
>
> **Mới ở v2.6:**
> 1. **Component mới 4.24 — Timeline Infographic:** mốc thời gian dạng node dọc, BẮT BUỘC cho bài
>    mẫu phân tích (mục D) thuộc thể loại tường thuật theo thời gian (Biography, Blog post) — thay
>    Region Highlight (4.23, chỉ dùng cho thể loại KHÔNG có trục thời gian như Opinion essay). Đúc
>    kết từ lỗi thật: 1 bài Biography (Marie Curie, Writing Unit 1 Lớp 12) vay mượn nhầm cơ chế
>    Region Highlight của Opinion essay, bỏ lỡ điểm mạnh chuỗi mốc thời gian của thể loại.
> 2. **Mục 4.23 — bổ sung bullet 5:** làm rõ ranh giới không dùng Region Highlight cho thể loại có
>    trục thời gian thật.
>
> **Mới ở v2.5:**
> 1. **Component mới 4.23 — Region Highlight:** nhãn bấm tô sáng 1 vùng lớn (đoạn/nhóm câu), loại
>    trừ lẫn nhau — dùng cho bài mẫu Opinion essay (Introduction/Reason 1/Reason 2/Conclusion), khác
>    Interactive Analyzer vốn tô từng câu riêng lẻ. Giải quyết câu hỏi mở treo lại từ kịch bản Writing
>    Unit 2 Lớp 11 ("cơ chế 4-nút highlight — cần xác nhận component trước khi build").
>
> **Mới ở v2.4:**
> 1. **Nguyên tắc 15 (mới, Mục 0):** heading/tiêu đề LUÔN tiếng Anh trước, tiếng Việt nhỏ hơn đặt
>    sau (`.vi-sub`/`.vi-sub-light`/dấu gạch ngang tuỳ ngữ cảnh) — kèm quy tắc nội dung bài tập
>    (đề bài, tên Activity) mặc định 100% tiếng Anh.
> 2. **Nguyên tắc 16 (mới, Mục 0):** Structure/Sequence Labelling — thứ tự câu hỏi không được trùng
>    thứ tự xuất hiện trong bài mẫu gốc (mở rộng Nguyên tắc 13).
> 3. **Mục 4.6 — cảnh báo kỹ thuật mới:** lỗi nút MCQ không bấm được do nhúng text có dấu nháy đơn
>    (VD "school's") vào thuộc tính `onclick=""` — bắt buộc dùng `addEventListener`, áp dụng cho mọi
>    component tự render nút từ text tự do (không riêng MCQ).
> 4. **Mục 9.17 — bổ sung biến thể Submit tường minh:** dùng khi Activity đó cũng là điều kiện mở
>    khoá bước/phase tiếp theo, thay vì chỉ auto-gate qua sự kiện `input`.
>
> **Mới ở v2.3:**
> 1. **Mục 9.17 (mới) — Gated Reveal:** chuẩn hoá nút "Xem model answer/Xem đáp án gợi ý" cho Writing
>    & bài tự luận (khác Mục 9.2 vốn chỉ dành cho MCQ/trắc nghiệm có đúng/sai) — nút luôn bắt đầu
>    `disabled`, chỉ mở khoá sau khi học sinh gõ đủ % số từ mục tiêu hoặc điền đủ toàn bộ ô trống.
> 2. **Checklist 9.15 — bổ sung:** heading/`athena-context.structure.title` luôn tiếng Anh trước
>    (bản Việt đặt trong `.vi-sub` nếu cần); mọi ô viết đoạn hoàn chỉnh phải có Gated Reveal hoặc
>    luồng Nộp bài AI (9.6) — không để activity viết bài xong rồi không có phản hồi gì.
>
> **Mới ở v2.2:**
> 1. **Component mới 4.21 — Idea Diagram (sơ đồ cây phát triển ý, gốc→nhánh→lá, 4 mức hỗ trợ):**
>    dùng cho bài brainstorm ý theo cấu trúc phân tầng trước khi viết/nói (Writing Suggestion &
>    Benefits paragraph...). Dựng thuần bằng CSS Flexbox, KHÔNG dùng SVG/toạ độ JS để vẽ đường nối
>    (dễ vỡ khi mobile xoay màn hình/bàn phím ảo đẩy layout) — xem Mục 4.21.
> 2. **Component mới 4.22 — Auto-collapse Theory Block:** đoạn lý thuyết dài tự gom lại thành thanh
>    tiêu đề gọn khi học sinh chuyển sang phần tiếp theo, bấm lại để mở xem lại — áp dụng cho mọi
>    khối lý thuyết dài (Khung tổng quát, Đi sâu từng phần, Phân tích bài mẫu...). Xem Nguyên tắc 14
>    (Mục 0) và Mục 4.22.
> 3. **Engine 1.17 (file `03_engine_tiengAnh.md`) — Typewriter + Growing Diagram:** hiệu ứng gõ chữ
>    dần + Idea Diagram "mọc" thêm 1 cấp, dùng cho demo GV/AI dẫn dắt tuần tự trước khi học sinh tự
>    làm. Mở rộng từ Progressive Reveal có sẵn (Mục 1.7), không phải component tách rời.
>
> **v2.1:**
> 1. **Component mới 4.20 — Guided Noticing (ô gõ tự do, tự đối chiếu đáp án):** dùng cho bước
>    "học sinh tự tìm cụm từ chức năng ngôn ngữ trong hội thoại mẫu trước khi xem bảng đầy đủ"
>    (Menu B ở Speaking, đã dùng lặp lại từ Unit 4 trở đi). Học sinh gõ tự do vào ô input, KHÔNG
>    auto-chấm đúng/sai — bấm nút "Hiện đáp án" để tự đối chiếu. Xem Mục 4.20, checklist bổ sung
>    ở Mục 9.15.
>
> **Mới ở v2.0:**
> 1. **Bỏ hẳn Task bar/`#progress-tracker`** — xoá toàn bộ code ở Mục 4.1 cũ, thay bằng ghi chú
>    deprecate; dọn mọi tham chiếu còn sót ở Mục 3, Mục 5, Mục 7, Mục 8.
> 2. **Bỏ nút/link điều hướng giữa File Lesson và File Practice khi tách 2 file** (mặc định) — xem
>    Mục 8.2 mục 2/3 cập nhật. Hành vi trong-trang `goToPractice()` ở Mục 4.8 chỉ còn áp dụng cho
>    trường hợp gộp 1 file (ngoại lệ chủ động).
> 3. **Nguyên tắc 12 (mới, Mục 0):** giọng đọc bắt buộc `en-GB`; quy tắc chống lặp pattern ở cấp nội
>    dung soạn bài cho MCQ trọng âm/Cloze/Matching, không chỉ dựa vào random vị trí hiển thị.
>
> **v1.9:** thêm component 4.19 Vietnamese Translation Toggle (nút bật/tắt bản dịch, mặc định
> ẩn) — dùng cho hướng dẫn/mô tả nhiệm vụ dài cần hỗ trợ tiếng Việt mà không hiển thị song ngữ mặc
> định; KHÔNG dùng cho câu hỏi/đề bài (luôn thuần tiếng Anh). Đúc kết từ quá trình build Speaking
> Unit 1 — xem Mục 4.19, checklist bổ sung ở Mục 7.



> **Dùng được cả trên Antigravity (Gemini) lẫn Claude** — file không phụ thuộc tool cụ thể, không
> dùng cú pháp riêng IDE nào. Dán file này (kèm `01_scenario_builder_tienganh.md` nếu đã có) cho
> AI, nói: *"Build simulation Tiếng Anh mới theo design system này."*
>
> **Phạm vi:** dùng cho TOÀN BỘ kỹ năng trong 1 Unit — Getting Started, Pronunciation, Grammar,
> Reading, Speaking, Listening, Writing, Culture, Revision/Diagnostic — không chỉ riêng phần
> "Getting Started". 1 Unit hoàn chỉnh có thể tách thành ~30 file HTML riêng biệt (mỗi module,
> hoặc mỗi phần nhỏ trong module, là 1 file độc lập) — **KHÔNG có 1 sidebar chung điều hướng cả
> 9 module trong 1 file** (khác với 1 bản tham khảo có sidebar 280px liệt kê module — bản đó chỉ
> dùng để tham khảo loại hoạt động, không dùng layout của nó). Mỗi file build ra tuân thủ đúng quy
> tắc "không sidebar/header cố định" như file Toán.
>
> **Dùng CHUNG, không đổi** so với `02_design_toan_final_v2.md`: bộ token màu (Mục 1), font Be
> Vietnam Pro (Mục 2), quy tắc mobile/collapsible-panel, và toàn bộ PHẦN 7 (LMS & Athena Manifest)
> — copy nguyên các mục đó từ file Toán khi build, không viết khác đi.
>
> **Bảng màu:** dùng ĐÚNG token hệ thống (Mục 1) cho mọi module — không tô màu riêng theo từng kỹ
> năng (Reading=xanh lá, Speaking=đỏ...) như 1 số bản tham khảo. `--jade-deep` là màu hành
> động chính xuyên suốt mọi module; các token semantic (`--correct/--wrong/--warning/--info`) dùng
> đúng vai trò phản hồi, không dùng để "phân biệt module".
>
> **Cập nhật quan trọng (bắt buộc áp dụng cho mọi bài có đủ Hội thoại + Từ vựng + Luyện tập):**
> đã đúc kết từ việc build và sửa lỗi thực tế trên 1 bài Getting Started hoàn chỉnh, gồm 3 thay đổi
> lớn so với bản trước:
> 1. Component Phone Chat (4.3) và Vocabulary (4.4) mặc định GỘP chung vào 1 **Top Panel** có tab
>    chuyển đổi + nút Gom + khoá tuần tự (xem 4.8) — không còn là 2 section rời nhau xếp dọc như
>    layout tham khảo cũ ở Mục 3.
> 2. Luyện tập (4.5/4.6) mặc định chạy theo **step-gate tuần tự** (từng dạng bài 1 lúc, có nút
>    "Tiếp theo" chỉ bật khi làm xong bước hiện tại) thay vì hiện hết mọi dạng bài cùng lúc trên
>    1 trang dài — và sau khi xong 1 mức phải có nút bấm thẳng sang mức tiếp theo.
> 3. Bài Matching (4.6) có 1 lỗi dữ liệu rất dễ mắc phải (bảng chữ cái đáp án bị lệch vị trí) —
>    xem khung cảnh báo trong 4.6 để tránh lặp lại.
> 4. **(Mới)** Vocabulary (4.4) trên mobile chuyển hẳn sang **carousel vuốt/bấm mũi tên ngang**
>    (desktop giữ nguyên dạng lưới bình thường), tối ưu cho tối đa **12 thẻ**. Luyện tập (4.5/4.8b)
>    khi gắn với 1 khối bài học phía trên (Hội thoại/Từ vựng/Reading) mặc định có thêm **Practice
>    Reference Pane**: tái hiện lại đúng nội dung bài học đó song song với phần làm bài — desktop
>    chia đôi màn hình theo **chiều dọc** (2 cột trái/phải), mobile chia đôi theo **chiều ngang**
>    (2 khối trên/dưới), có nút chuyển chế độ xem (Chia đôi / chỉ Bài đọc / chỉ Câu hỏi) — xem 4.8b.

---

## 🤖 HƯỚNG DẪN CHO AI — ĐỌC TRƯỚC KHI LÀM BẤT CỨ ĐIỀU GÌ

**Mặc định: upload kịch bản + gõ "build"/"thiết kế" → build thẳng ra file HTML luôn, không hỏi
gì cả, không có bước xác nhận nào chặn giữa đường.** Đây là hành vi ưu tiên số 1 của file này.

Khi người dùng đính kèm 1 file (kịch bản từ `01_scenario_builder_tienganh.md`, hoặc bất kỳ file/
đoạn text nào chứa nội dung bài học) và nói bất kỳ điều nào sau:
- "Thiết kế" / "Design" / "Build" / "Làm giao diện" / tên 1 Unit
- Hoặc chỉ đơn giản đính kèm file mà không nói gì thêm

**→ Đọc file, tự trích xuất mọi thứ cần (Unit, nhân vật, hội thoại, từ vựng, mục tiêu, sai lầm),
build NGAY theo PHẦN 1 bên dưới. Không hỏi lại, không tóm tắt xin xác nhận trước, không hỏi chọn
màu/font/layout (đã cố định 100%). Xuất file xong mới thôi — người dùng xem file để phản hồi, thay
vì phải trả lời câu hỏi mới cho AI build.**

**Chỉ hỏi lại (ngắn gọn, đúng đúng phần thiếu) khi:**
- Không có file đính kèm và tin nhắn không đủ nội dung tối thiểu để build (không có hội thoại/từ
  vựng nào cả) → hỏi 1 câu ngắn xin nội dung, không dùng cả bảng dài.
- File đính kèm thiếu hẳn 1 phần bắt buộc (VD có hội thoại nhưng không có nghĩa tiếng Việt cho từ
  vựng, hoặc không có mục tiêu bài học) → hỏi đúng đúng phần đó, không hỏi lại những gì đã có.

---

## PHẦN 0 — QUY TRÌNH (rút gọn, không phải hội thoại nhiều bước)

```
1. Nhận file/nội dung kịch bản + lệnh "build"
2. Xác định module đang build thuộc loại nào: Getting Started / Pronunciation / Grammar / Reading /
   Speaking / Listening / Writing / Culture / Revision — map vào đúng component ở PHẦN 1 Mục 4
   tương ứng (Getting Started → Mục 4.1-4.8; các loại khác → Mục 4.9-4.17)
2b. **Mặc định LUÔN tách 2 file** — `..._lesson.html` (Khối 1: Hero + Hội thoại/Bài đăng/Reading +
   Vocabulary) và `..._practice.html` (Khối 2: Luyện tập + Practice Reference Pane 4.8b BẮT BUỘC +
   Self-assessment). Xem quy tắc chia đúng ranh giới, đồng bộ dữ liệu, và checklist ở Mục 8 — chỉ
   gộp lại thành 1 file duy nhất khi người dùng CHỦ ĐỘNG yêu cầu ngược lại ("gộp 1 file", "không cần
   tách"). Nếu kịch bản đầu vào đã tự đánh dấu sẵn PHẦN 1/PHẦN 2 (từ `01_scenario_builder_tienganh_v2.md`)
   thì build đúng theo ranh giới đó, không tự suy luận lại.
2c. **Mobile-first bắt buộc mọi module**: build và kiểm tra layout ở khung hẹp (≤480px) trước, rồi
   mới mở rộng lên desktop — đặc biệt Practice Reference Pane (4.8b) phải test đủ 3 chế độ xem trên
   mobile (Chia đôi/Bài đọc/Câu hỏi), không chỉ test ở desktop rồi giả định mobile tự ổn.
3. Nếu thiếu thông tin BẮT BUỘC (không suy luận được) → hỏi đúng đúng phần thiếu, 1 câu ngắn
4. Nếu đủ thông tin → build thẳng theo PHẦN 1, không xác nhận trước
5. Xuất file HTML (2 file nếu đúng mặc định) + tóm tắt ngắn (số collocations, số câu mỗi mức đã
   build) NGAY DƯỚI file, không phải là câu hỏi chờ trả lời — người dùng đọc file trước, muốn chỉnh
   gì thì nói sau
```

Sau khi build xong, chỉ cần 1 dòng ngắn kiểu: *"Đã build xong Unit [X] — [N] collocations, [N]
câu luyện tập mỗi mức. Báo mình nếu cần chỉnh gì."* — không lặp lại bảng tóm tắt to hay hỏi
"muốn duyệt không" như quy trình nhiều bước của môn Toán.

---

## PHẦN 1 — QUY CHUẨN THIẾT KẾ & COMPONENT (tham chiếu khi build)

## 0. Nguyên tắc bắt buộc

1. **Không tạo bảng màu/font riêng cho môn Tiếng Anh** — dùng đúng token ở Mục 1 và font Be Vietnam
   Pro cho toàn bộ, kể cả heading (bản tham khảo có dùng thêm font 'Baloo 2' cho tiêu đề — **bỏ**,
   dùng Be Vietnam Pro weight 700-800 để vẫn có cảm giác vui tươi mà không phá vỡ đồng bộ font).
2. **KHÔNG có layout/cấu trúc cố định theo tên module.** Khung 4 phần ở Mục 3 và các "cấu trúc
   thường gặp" mô tả trong từng component ở Mục 4 (VD "Reading = warm-up → passage → comprehension")
   chỉ là **ví dụ tham khảo phổ biến**, không phải khuôn bắt buộc. 1 bài Getting Started có thể
   không có phần chat (VD dùng video/tranh thay vì hội thoại), 1 bài Reading có thể bỏ warm-up nếu
   kịch bản không cần, 1 bài Speaking có thể không cần shadowing. **Cấu trúc thật của mỗi bài luôn
   xuất phát từ kịch bản/nội dung cụ thể được giao, không phải từ tên module.** Xem quy trình chọn
   component ở Mục 4.0.
3. **Mỗi module (hoặc mỗi phần nhỏ trong module) là 1 file HTML độc lập** — không gộp nhiều module
   vào 1 file có sidebar điều hướng chung. Không dùng sidebar/header cố định điều hướng nhiều bài
   trong 1 file (đúng quy tắc chung của toàn hệ thống).
4. **Không dùng kéo-thả (drag-and-drop)** dưới bất kỳ hình thức nào — không chỉ bài nối (Mục 4.12)
   và sắp xếp câu (Mục 4.13), mà cả bài **phân loại/xếp nhóm** (VD kéo thẻ vào đúng nhóm "hợp
   pháp/không hợp pháp") cũng phải chuyển sang tap-to-select (xem Mục 4.17 — component này hay bị
   quên nhất vì không nằm chung nhóm với "nối từ", dễ bị build lại bằng drag-and-drop theo bản
   năng). Kéo-thả khó thao tác chính xác trên cảm ứng, vi phạm nguyên tắc mobile-first.
   > **Ngoại lệ duy nhất — thanh trượt kéo so sánh (Before/After slider, Mục 4.18):** đây KHÔNG
   > phải "kéo-thả" theo nghĩa bị cấm ở trên (không có việc thả 1 phần tử vào đúng/sai 1 vị trí
   > đích để chấm điểm) — chỉ là kéo 1 tay cầm liên tục trên 1 trục, giống thanh âm lượng. Được
   > phép dùng cho dạng bài so sánh trực quan (VD "Bữa cơm gia đình: Xưa & Nay"), nhưng **bắt buộc**
   > implement đúng theo Mục 4.18 (`touch-action:none` trên container + `e.preventDefault()` trong
   > `touchmove` với listener `{ passive:false }`) — nếu thiếu, kéo trên mobile sẽ bị cuộn cả màn
   > hình thay vì di chuyển thanh trượt.
5. **Mỗi câu hỏi luyện tập PHẢI có phần giải thích** (`explain`) — không chỉ báo đúng/sai. Đây là
   lỗi hay gặp nhất khi build nhanh, vi phạm nguyên tắc "Giải thích kiến thức" ở
   `01_scenario_builder_v4.md` PHẦN 0 Bước 5.
6. Mobile-first, vùng chạm ≥44px, LMS instrumentation đầy đủ — như mọi file khác trong hệ thống.
7. **Vị trí đáp án đúng trong MCQ và Matching PHẢI được xáo ngẫu nhiên khi render, không gán cứng
   trong data.** Đây là lỗi soạn ẩu rất hay gặp và rất khó tự nhận ra khi build từng câu riêng lẻ —
   người soạn vô thức đặt đáp án đúng lệch về 1 vị trí quen tay (thường là B hoặc C) qua hàng chục
   câu hỏi, khiến học sinh tinh ý "đoán mò theo vị trí" vẫn đúng bất thường mà không cần hiểu bài.
   **Bắt buộc dùng hàm xáo trộn dùng chung** (xem `shuffleMCQOptions()` ở Mục 4.6 và
   `.sort(()=>Math.random()-0.5)` ở Mục 4.12/4.17) thay vì viết cứng thứ tự A/B/C/D theo đúng thứ
   tự soạn trong data — xáo NGAY TRONG HÀM RENDER, mỗi lần hiện câu hỏi là 1 lần xáo mới, không xáo
   1 lần cố định rồi lưu lại.
8. **Mọi text tự do (word, nghĩa, ví dụ, tên nhân vật, câu hỏi...) chèn vào `innerHTML` qua template
   string PHẢI qua hàm `esc()` dùng chung** (định nghĩa 1 lần ở đầu `<script>`, xem 4.3):
   `function esc(s){ return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;'); }`
   — tránh ký tự `< > & "` trong nội dung kịch bản phá cấu trúc HTML. Ngoại lệ: field nào bản thân
   đã CHỦ ĐỘNG chứa markup cần giữ (VD `message.text` có sẵn `<span class="kw-inline">`) thì KHÔNG
   esc() field đó, chỉ esc() các field text thuần khác trong cùng object.
   > ⚠️ **`esc()` KHÔNG escape dấu nháy đơn `'`** — vì vậy TUYỆT ĐỐI không dùng text đã qua `esc()`
   > (hay bất kỳ text tự do nào) làm tham số bên trong thuộc tính `onclick="..."` dạng chuỗi
   > (`onclick="fn('${esc(text)}')"`), vì text chứa `'` (VD "school's", "I'd") sẽ làm gãy chuỗi JS.
   > Luôn dùng `addEventListener` khi cần truyền text tự do vào handler — xem cảnh báo đầy đủ + ví
   > dụ sửa lỗi ở Mục 4.6 (ngay sau `shuffleMCQOptions()`).
9. **Cấm đề bài chung mơ hồ kiểu "Choose the correct word" lặp lại giống nhau cho mọi câu, khi tiêu
   chí chọn đúng khác nhau giữa các dạng bài.** Học sinh phải đọc đề là hiểu NGAY tiêu chí chọn, không
   phải đoán hoặc bấm bừa vì "chọn cái nào cũng được". Áp dụng bắt buộc cho mọi dạng bài trắc nghiệm/
   chọn từ (Pronunciation Difference/Odd-one-out, Grammar MCQ, Vocabulary MCQ, Comprehension...):
   > ⚠️ **Ví dụ minh hoạ dưới đây CHỈ để hiểu CẤU TRÚC câu đề (không nói mơ hồ) — không phải nội dung
   > mẫu để copy vào bài build.** Nội dung thật (từ, câu, đáp án) LUÔN LẤY 100% từ kịch bản do người
   > dùng cung cấp, không tự thay/chèn thêm từ trong ví dụ ở tài liệu này dưới bất kỳ hình thức nào —
   > xem cảnh báo toàn cục ở cuối Mục 0.
   - Đề bài (`instruction`/`q`) phải nói rõ **tiêu chí phân biệt đúng/sai** bằng tiếng Anh chuẩn, kèm
     bản dịch tiếng Việt dễ hiểu ngay bên dưới hoặc trong `explain`. Cấu trúc mẫu cho Pronunciation
     Difference (odd-one-out — tìm từ KHÁC nhóm): *"Choose the word whose underlined part is
     pronounced differently from the other three."* / dịch: *"Chọn từ có phần gạch chân được phát âm
     KHÁC 3 từ còn lại."* — không viết chung 1 câu "Choose the correct word." cho toàn bộ set mà
     không nói khác ở tiêu chí nào.
   - Nếu dạng bài là "chọn từ có cách phát âm ĐÚNG với âm mục tiêu của nhóm" (ngược lại odd-one-out),
     đề phải nói rõ theo hướng đó: *"Choose the word that has the same pronunciation as the target
     sound of the group."* — 2 tiêu chí này KHÁC NHAU hoàn toàn, không dùng lẫn 1 câu đề chung.
   - Mỗi câu hỏi trong 1 set nên có `instruction` riêng khi tiêu chí đổi giữa các câu (không mặc định
     áp 1 câu đề tĩnh cho toàn bộ set nếu nội dung từng câu yêu cầu tiêu chí khác nhau); nếu cả set
     dùng chung đúng 1 tiêu chí xuyên suốt thì 1 `instruction` chung ở đầu section là đủ, không cần
     lặp lại mỗi câu.
   - Field `explain` của câu đó phải nêu lại đúng từ/phần được xét (VD gạch chân IPA, hoặc bôi đậm
     phần âm cần so sánh) để học sinh đối chiếu được vì sao đúng/sai, không chỉ nói "Đúng rồi!".
10. **Bài dạng gõ chữ (Gap-fill 4.6, Q&A mở, Error Correction) PHẢI chấp nhận các dạng viết tắt/đầy
   đủ tương đương của học sinh, không so khớp so sánh chuỗi tuyệt đối (`===`).** Dùng hàm so khớp
   dùng chung `checkTextAnswer()` (định nghĩa đầy đủ ở Mục 4.6, ngay sau phần Gap-fill) cho MỌI ô
   nhập `input[type=text]`/`textarea` cần chấm đúng-sai tự động trong toàn hệ thống — không viết
   riêng logic so sánh chuỗi cho từng bài, và **không dùng bảng cặp cứng liệt kê từng chủ ngữ** (VD
   `i will<->i'll`) vì đã kiểm chứng thực tế là cách này thiếu chủ ngữ (bỏ sót `that'll/who'll/
   there'll...`) — hàm chuẩn dùng regex tổng quát khớp mọi từ đứng trước hậu tố viết tắt. Hàm bắt
   buộc xử lý đủ các trường hợp sau (đã test qua 20 tình huống thật, xem chú thích trong code Mục 4.6):
   - Chuẩn hoá khoảng trắng thừa, hoa/thường, dấu câu cuối câu (`. , ! ?`) trước khi so.
   - **Chuẩn hoá dấu nháy đơn về cùng 1 ký tự** (`'` thẳng và `’ ‘ ʼ` cong đều coi là 1) — bàn phím
     điện thoại rất hay tự động đổi `'` thành `’` khi học sinh gõ contraction, nếu không xử lý thì
     học sinh viết ĐÚNG viết tắt vẫn bị chấm sai chỉ vì khác ký tự dấu nháy. Đây là lỗi rất dễ bỏ
     sót vì test trên máy tính (gõ tay `'` thẳng) sẽ KHÔNG bao giờ phát hiện ra, chỉ lộ ra khi học
     sinh thật gõ trên điện thoại.
   - Mở rộng viết tắt ↔ đầy đủ theo QUY TẮC (không theo danh sách cứng), cover MỌI từ đứng trước:
     `n't → not` (isn't/doesn't/haven't/wouldn't/mustn't... — riêng `won't/can't/shan't/ain't` xử lý
     riêng vì biến dạng gốc từ), `'ll → will`, `'re → are`, `'ve → have`, `'m → am` (không mơ hồ, chỉ
     1 nghĩa); riêng `'s` (is/has) và `'d` (would/had) là MƠ HỒ — hàm phải sinh cả 2 khả năng và chấp
     nhận nếu 1 trong 2 khớp đáp án.
   - **Case hay bị bỏ sót nhất — chủ ngữ nằm NGOÀI chỗ trống:** khi câu đề chỉ để trống động từ (VD
     cấu trúc `"[Chủ ngữ] ______ ([động từ])..."` với `ans` chỉ ghi phần động từ, chủ ngữ nằm ngoài
     chỗ trống), học sinh viết tắt tự nhiên sẽ gõ dính chủ ngữ vào 'll/'d vì đó là quy tắc ngữ pháp
     bắt buộc — hàm phải tự bỏ chủ ngữ đứng đầu ở PHÍA INPUT HỌC SINH sau khi mở rộng viết tắt, để so
     khớp được với ans không có chủ ngữ. **Chỉ bỏ chủ ngữ ở phía học sinh, không bỏ ở phía `ans`** —
     nếu bỏ cả 2 phía sẽ gây báo đúng nhầm khi học sinh viết sai chủ ngữ (VD ans có chủ ngữ A, học
     sinh viết chủ ngữ B khác, vẫn phải báo SAI, không được vô tình khớp qua biến thể đã bỏ chủ ngữ
     của cả 2 bên).
   - Nếu đáp án đúng của câu chỉ CHỦ ĐỘNG chấp nhận 1 chiều (VD kịch bản yêu cầu học sinh phải viết
     đúng dạng đầy đủ để luyện ngữ pháp, không chấp nhận viết tắt) thì set field `strictNoContraction:
     true` trong data câu đó để tắt toàn bộ xử lý viết tắt cho riêng câu đó (so sánh nguyên chuỗi đã
     chuẩn hoá) — mặc định (không set field này) là LUÔN chấp nhận cả 2 chiều.
   - Ngoài viết tắt, data câu hỏi có thể khai báo thêm field `altAnswers: [...]` để chấp nhận các
     cách viết đúng khác ngoài viết tắt (đồng nghĩa, thứ tự từ khác nhưng vẫn đúng ngữ pháp) — hàm
     `checkTextAnswer()` phải so với `ans` VÀ toàn bộ `altAnswers` trước khi báo sai.
11. **Sàn cỡ chữ tối thiểu — phân biệt rõ "nội dung ngôn ngữ HS phải đọc để học" và "nhãn UI/meta phụ".**
    Lỗi thật đã gặp: nhiều component để chữ nội dung học (đoạn Reading, tin nhắn hội thoại, IPA, câu
    ví dụ từ vựng, đáp án MCQ...) xuống dưới cả `body` baseline 18px, có chỗ xuống tới 9.5px — đọc rất
    mỏi mắt, đặc biệt trên di động. Áp dụng 2 mức sàn:
    - **≥ 15px** cho mọi nội dung ngôn ngữ chính HS phải đọc/gõ để học hoặc trả lời (đoạn văn Reading,
      tin nhắn hội thoại, câu hỏi + đáp án MCQ/Matching/Gap-fill, IPA, câu ví dụ từ vựng, model text
      Writing...). Ưu tiên 16-17px khi layout còn chỗ (xem `.fill-sentence`/`.fte-sentence` = 17px làm
      chuẩn tham chiếu).
    - **≥ 11px** cho nhãn UI/meta thuần tuý không cần đọc kỹ để hiểu bài (giờ tin nhắn, dấu ✓ nhỏ, nhãn
      trạng thái, số thứ tự...) — KHÔNG áp mức 15px này vì sẽ làm rối giao diện.
    - **Không suy luận cỡ chữ theo "cột hẹp desktop" rồi áp nguyên sang mobile.** Lỗi thật đã gặp ở
      Vocabulary (4.4): class `.compact` thu nhỏ chữ cho lưới nhiều cột trên desktop, nhưng bị kế thừa
      luôn vào carousel mobile — dù mỗi thẻ carousel mobile LUÔN chiếm 84% màn hình bất kể tổng số thẻ
      (xem 4.8/4.4), thừa chỗ chứ không hề hẹp. Mỗi khi 1 class thu nhỏ chữ được tạo ra cho lý do
      "cột/khung hẹp", phải tự hỏi: trên mobile, khung này có thật sự còn hẹp không, hay đã đổi layout
      (VD sang carousel/step-gate 1-lúc-1-khối) khiến chiều rộng thực tế đã rộng rãi trở lại? Nếu rộng
      lại, PHẢI viết đè bằng media query riêng để tăng chữ trở lại mức bình thường, không dùng chung 1
      class cho cả 2 tình huống khác bản chất.
    - Khi tăng cỡ chữ một component, luôn xem lại `line-height`/`padding` đi kèm để bù trừ chiều cao
      tăng thêm (đặc biệt trên mobile) — không tăng chữ mà giữ nguyên khoảng đệm/line-height cũ, dễ gây
      vỡ khung hoặc chữ đè lên nhau.
12. **Giọng đọc TTS bắt buộc `en-GB` (Anh-Anh)** — mọi lần gọi `SpeechSynthesisUtterance`/hàm
    `speak()` ở BẤT KỲ component nào (Flashcard 4.4, Read Aloud 9.4, Listen & Circle...) đều PHẢI
    set `u.lang = 'en-GB'`. **Không được đổi sang `'en-US'` hay để mặc định trống** (mặc định trống
    thường ra giọng theo ngôn ngữ hệ điều hành, hay lệch sang Mỹ) — kể cả khi build component audio
    mới không có trong thư viện Mục 4. Đây là quy tắc cứng áp dụng toàn hệ thống, không tự đổi theo
    "giọng nghe hay hơn" hay theo thiết bị test.
13. **Chống đoán mò theo PATTERN ở cấp nội dung soạn bài — khác với nguyên tắc 7 (random vị trí
    hiển thị lúc render).** Nguyên tắc 7 chỉ đảm bảo vị trí đáp án đúng không cố định qua các LẦN
    RENDER — không tự sửa được nếu bản thân dữ liệu câu hỏi khi SOẠN đã đi theo 1 khuôn lặp cố định
    qua các câu liền kề trong cùng 1 bài/gói. Khi soạn `data` câu hỏi, bắt buộc tự kiểm tra và đảo:
    - **MCQ nhận diện trọng âm/khác biệt âm (Pronunciation):** đáp án đúng (mẫu trọng âm, vị trí từ
      lệch nhóm...) không được lặp theo chu kỳ đều đặn qua các câu (VD "1-2, 1-2, 1-2" liên tục) —
      đảo ngẫu nhiên giữa các khả năng, không theo chu kỳ cố định.
    - **Loại từ/cấu trúc:** không để cả 1 bài chỉ dùng đúng 1 khuôn chuyển loại từ (VD toàn danh
      từ→động từ) hay lặp đúng 1 cấu trúc câu qua nhiều câu liền kề — trộn nhiều biến thể nếu nội
      dung gốc cho phép.
    - **Cloze — danh sách từ cho sẵn:** thứ tự từ trong danh sách hiển thị phía trên đoạn văn KHÔNG
      được trùng thứ tự các chỗ trống cần điền — soạn `data` đã phải xáo trước, không liệt kê từ
      trên xuống dưới đúng theo thứ tự điền.
    - **Matching:** thứ tự cột đáp án trong `data` không được khớp 1-1, 2-2, 3-3... với cột trái —
      soạn data đã đảo trước (không chỉ trông chờ `.sort(()=>Math.random()-0.5)` lúc render, vì có
      component chỉ shuffle 1 lần khi build rồi lưu cố định).
    - Áp dụng cho mọi component có set nhiều câu hỏi liên tiếp (4.6, 4.11, 4.12, 4.13, 4.16, 4.17).
14. **Đoạn lý thuyết dài PHẢI tự gom lại khi chuyển sang nội dung mới — bấm để mở lại khi cần xem
    lại, không xoá mất.** Áp dụng cho mọi khối giải thích/lý thuyết dài đứng TRƯỚC phần luyện tập
    (VD ở Writing: Hook → Khung tổng quát → Đi sâu từng phần → Phân tích bài mẫu → Bảng tín hiệu —
    mỗi khối có thể dài vài đoạn). Khi học sinh cuộn/bấm sang khối tiếp theo, khối vừa đọc xong tự
    thu gọn thành 1 thanh tiêu đề ngắn (giữ đúng tiêu đề gốc + icon mũi tên), không hiện chi tiết —
    bấm lại vào thanh đó để mở ra xem lại, không mất nội dung. Đây là nguyên tắc chung; component
    kỹ thuật cụ thể xem Mục 4.22 — không nhầm với "nút Gom" ở Top Panel (Mục 4.8, chỉ gộp Phone
    Chat + Vocabulary) hay Progressive Unlock (Mục 4.9, chỉ mở khoá tuần tự, không tự gom lại phần
    đã mở). Mục đích: tránh trang lý thuyết dài vô hạn khi có nhiều khối nối tiếp nhau, đồng thời
    không mất khả năng tra cứu lại như nếu ẩn hẳn bằng Progressive Unlock.
15. **Heading/tiêu đề LUÔN tiếng Anh trước, tiếng Việt nhỏ hơn/nhạt hơn đặt sau — không đảo ngược,
    không để heading thuần tiếng Việt thiếu bản tiếng Anh.** Lỗi thật đã gặp: nhiều heading (`<h2>`,
    `<h3>`, `title` trong `athena-context.structure`, tên tab Reference Pane...) viết thuần tiếng
    Việt không kèm bản Anh (VD "A · Khung tổng quát", "🍴 Bài Căng tin") — sai nguyên tắc tiếng Anh
    là ngôn ngữ chính của bài học. 3 cách trình bày tuỳ độ dài, dùng đúng ngữ cảnh:
    - **Heading/tên Section** (h2/h3, tên tab, tên hoạt động): tiếng Anh làm `<h2>`/text chính, tiếng
      Việt đặt trong `<span class="vi-sub">` NGAY SAU, hiển thị nhỏ hơn/nhạt màu hơn, xuống dòng
      riêng nếu cần:
      ```html
      <h2>How to Write a Suggestion Paragraph<span class="vi-sub">Khung cấu trúc 5 phần của đoạn văn đề xuất</span></h2>
      ```
      ```css
      .vi-sub { display:block; font-size:14px; font-weight:500; color:var(--ink-3); margin-top:2px; }
      /* Trên nền màu tối (Hero, Hook banner...) dùng biến thể sáng hơn: */
      .vi-sub-light { display:block; font-size:13px; font-weight:500; color:rgba(255,255,255,.75); margin-top:2px; }
      ```
    - **Nhãn ngắn cùng dòng** (label trong flow-card, pill badge): dùng dấu gạch ngang, không xuống
      dòng riêng: `<span class="flow-vi">— Câu chủ đề</span>` ngay sau tên tiếng Anh.
    - **Nội dung bài tập** (đề bài, tên Activity, tên đoạn văn cụ thể): mặc định 100% tiếng Anh,
      KHÔNG thêm tiếng Việt trừ khi 1 từ/khái niệm quá khó — xem quy tắc "Nội dung bài tập luôn
      tiếng Anh" ở `01_scenario_builder_tiengAnh.md` mục Song ngữ. Không tự dịch chèn giữa tên
      Activity (VD sai: "Passage Arrangement (Bài 1: Tiết kiệm nước)").
    - Đoạn dài hơn (mission brief, level-intro nhiều câu): viết 1 câu tiếng Anh ngắn gọn làm chính,
      tiếng Việt là bản tóm tắt ngắn hơn (không phải dịch nguyên văn dài) đặt ngay dưới cùng class
      `.vi-sub`; không diễn giải thêm khái niệm nội bộ (formative/summative, tên cơ chế kỹ thuật...)
      mà học sinh không cần biết để làm bài.
16. **Structure/Sequence Labelling — thứ tự câu hỏi KHÔNG được trùng thứ tự xuất hiện trong bài mẫu
    gốc.** Mở rộng Nguyên tắc 13 (chống đoán mò cấp nội dung soạn bài) sang 1 dạng đoán mò khác: đoán
    theo VỊ TRÍ CÂU TRONG BÀI MẪU thay vì đoán theo vị trí đáp án. Lỗi thật đã gặp: bài hỏi "câu này
    thuộc phần nào" đưa ra đúng theo trình tự Topic→Suggestion→Example→Result→Suggestion→Concluding
    y hệt thứ tự đọc bài mẫu — học sinh chỉ cần nhớ "câu đầu luôn là Topic, câu cuối luôn là
    Concluding" mà không cần hiểu chức năng câu. Khi build từ kịch bản, nếu phát hiện `data` các câu
    hỏi được liệt kê đúng theo trình tự bài mẫu, phải tự xáo lại thứ tự trước khi render — không chỉ
    xáo thứ tự lựa chọn đáp án A/B/C/D (2 việc khác nhau, Nguyên tắc 7 chỉ lo việc thứ 2).

> 🚫 **CẢNH BÁO TOÀN CỤC — LỖI THẬT ĐÃ GẶP, ĐỌC KỸ TRƯỚC KHI BUILD:** mọi từ/câu/tên/số liệu xuất
> hiện trong file này (Mục 0 nguyên tắc 9-10, Mục 4.6, và file `03_engine_tiengAnh.md` PHẦN 1.10)
> chỉ để MINH HOẠ CẤU TRÚC DỮ LIỆU (field nào, format nào) — **KHÔNG PHẢI nội dung bài học, TUYỆT ĐỐI
> không copy/tái sử dụng/lấy cảm hứng từ ví dụ trong 2 file design/engine này khi build**. Đã xảy ra
> lỗi thật: AI build tool đọc ví dụ minh hoạ trong file này rồi tự động THAY THẾ nội dung bài học mà
> người dùng đã cung cấp trong kịch bản (`01_scenario_builder_tiengAnh.md` hoặc file đính kèm khác)
> bằng chính nội dung ví dụ ở đây — hậu quả là bài build ra hoàn toàn khác kịch bản gốc, dù trước đó
> build đúng với bản design cũ (chưa có các ví dụ mới thêm vào). **Quy tắc bắt buộc:** nội dung thật
> (từ vựng, câu hỏi, câu điền từ, đáp án, tên nhân vật...) 100% phải LẤY từ kịch bản/file đính kèm
> của người dùng — file `02_design_tiengAnh.md` và `03_engine_tiengAnh.md` CHỈ quy định *cách trình
> bày/tương tác/kiểm tra* (component nào, field nào, hàm nào), không bao giờ là nguồn nội dung. Nếu
> kịch bản không có sẵn nội dung cho 1 phần nào, hỏi lại người dùng (theo quy trình ở PHẦN 0), không
> tự lấy ví dụ trong file design/engine để lấp vào.

---

## 1. Bộ màu chuẩn — dùng nguyên token hệ thống (dán để file dùng độc lập được)

```css
:root {
  /* Neutrals · giấy & mực */
  --cream:#FAF7F0; --cream-2:#F0EADD; --cream-3:#E7DECC;
  --paper-line:#E5DECF; --paper-line-2:#D6CCB6;
  --ink:#1A1A1A; --ink-2:#514C44; --ink-3:#7C756A; --ink-faint:#ABA396;

  /* Jade · hành động chính */
  --jade:#3CA57A; --jade-deep:#2D8B6F; --jade-dark:#14432F;
  --jade-text:#1B5E48; --jade-soft:#A9D0BE; --jade-pale:#DCEAE1;

  /* Sage · phụ trợ */
  --sage:#A8C9B8; --sage-deep:#7CA792; --sage-text:#46685A; --sage-pale:#E1ECE4;

  /* Accent · điểm nhấn ấm */
  --accent:#E8A24A; --accent-deep:#CE8A33; --accent-text:#8A551A; --accent-pale:#F7E7CD;

  /* Semantic · phản hồi đúng/sai/cảnh báo/info */
  --correct:#2D8B6F; --correct-bg:#DCEAE1;
  --wrong:#C15F3C;   --wrong-bg:#F3E2D6;
  --warning:#C58A2E; --warning-bg:#F5E7CB;
  --info:#4E7F92;    --info-bg:#DCE7EB;

  --white:#FFFFFF;
  --radius-lg: 22px; --radius: 14px; --radius-sm: 10px;
  --shadow: 0 10px 30px rgba(43,43,40,0.10);
}
```

> **Không dùng alias/tên biến kiểu cũ** (`--primary`, `--bg`, `--surface`, `--text`, `--green`...) —
> luôn viết thẳng tên token gốc (`--jade-deep`, `--cream`, `--white`, `--ink`, `--correct`...) trong
> mọi CSS ở Mục 4, đúng theo quy tắc v2.2 của `02_design_toan_final_v2.md` Mục 1.1. Alias chỉ dùng
> khi vá file cũ đã có sẵn `var(--primary)` rải rác — xem `AIDUCATION_UI_REDESIGN_PLAYBOOK.md`.

#### Màu accent cục bộ theo Unit (mới, v2.7)

Một số Unit có 1-2 màu accent chỉ dùng cho ĐÚNG 1 khối minh hoạ gắn bối cảnh văn hoá/địa lý cụ thể
(VD `--slate` #4E6E7E, `--terracotta` #C1704B cho khối minh hoạ làng bản/lễ hội ở Writing Unit 2
Lớp 12) — theo Bộ lưu ý Kịch bản Writing Mục 9.3. Đây là màu PHỤ, không phải thêm token mới vào bảng
toàn cục ở trên. Cách khai báo đúng:

```css
/* Khai báo NGAY TRONG selector của khối minh hoạ đó — KHÔNG thêm vào :root toàn cục */
.hook-illustration, .part3-banner {
  --slate: #4E6E7E;
  --terracotta: #C1704B;
}
.hook-illustration .fabric-pattern { color: var(--slate); }
.hook-illustration .roof-accent { color: var(--terracotta); }
```

**⚠️ Bắt buộc:**
1. Khai báo `--slate`/`--terracotta` (hoặc tên màu cục bộ khác) ngay trong selector của khối minh
   hoạ/component đó — KHÔNG khai báo trong `:root` (Mục 1 ở trên), tránh rò ra ảnh hưởng toàn hệ
   thống hoặc đụng Unit khác dùng lại đúng tên biến với hex khác.
2. Nền Cream/Jade gốc của toàn hệ thống giữ nguyên không đổi — accent cục bộ chỉ xuất hiện trong
   đúng khối minh hoạ/viền trang trí liên quan, không lan ra nút CTA, badge, hay text thường.
3. Nếu 1 Unit dùng accent cục bộ ở nhiều vị trí (VD Hook + Part 3 cùng dùng `--slate`/`--terracotta`
   để giữ liên kết thị giác), khai báo lại ở selector của MỖI vị trí đó (không dựa vào kế thừa từ 1
   khối cha chung, vì 2 khối có thể ở 2 file HTML khác nhau — Lesson/Practice tách file).

### Ánh xạ theo vai trò UI Tiếng Anh (bám sát bản tham khảo, chỉ đổi hex)

| Vai trò trong UI | Hex bản tham khảo | → Token hệ thống |
|---|---|---|
| Nền trang | `#FBF1E1` | `--cream` |
| Nền phụ (card nhạt) | `#F5E8D3` | `--cream-2` |
| Màu thương hiệu chính (hero, tin nhắn của mình, nút CTA chính) | `#2F6F62` | `--jade-deep` |
| Thương hiệu đậm (header sticky, viền phone) | `#204E45` | `--jade-dark` |
| Thương hiệu nhạt | `#9AC6BA` | `--jade-soft` |
| Điểm nhấn ấm (nút audio, trạng thái đang chọn) | `#E8A33D` (mustard) | `--accent` |
| Trạng thái sai/lỗi | `#E8623D` (coral) | `--wrong` |
| Phụ trợ trung tính (viền, tag) | `#A9C6AE` (sage) | `--sage` |
| Chữ chính / chữ phụ | `#2B2B28` / `#5B5B55` | `--ink` / `--ink-2` |

> **Lưu ý quan trọng:** bản tham khảo dùng "coral" cho **cả** nút CTA chính lẫn trạng thái sai —
> dễ gây hiểu nhầm (nút "Tin tiếp theo" và "bạn trả lời sai" cùng 1 màu). Khi chuyển sang token hệ
> thống, **tách rõ 2 vai trò**: CTA chính/badge số thứ tự/tag → `--jade-deep`; trạng thái sai/lỗi →
> `--wrong`. Trạng thái đúng luôn là `--correct`, đang chọn/hover luôn là `--accent`.

---

## 2. Typography

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Be+Vietnam+Pro:ital,wght@0,400;0,500;0,600;0,700;0,800;1,400&display=swap" rel="stylesheet">
```
```css
body { font-family:'Be Vietnam Pro',sans-serif; font-size:18px; color:var(--ink); background:var(--cream); line-height:1.55; }
h1,h2,h3,.display { font-family:'Be Vietnam Pro',sans-serif; font-weight:800; color:var(--jade-dark); }
```

---

## 3. Layout tham khảo — ví dụ thường gặp cho "Getting Started" (KHÔNG bắt buộc)

> Đây là **1 cách bố cục hay gặp**, không phải khuôn cố định. Ví dụ biến thể khác: bài không có
> hội thoại chat mà mở đầu bằng tranh/video → bỏ hẳn `section#sec-messages`, thay bằng component
> video (Mục 4.14 điều chỉnh cho phù hợp); bài không cần luyện 3 mức mà chỉ có 1 dạng bài duy nhất
> → bỏ Level Tabs (4.5), chỉ giữ 1 khối bài tập. **Luôn đối chiếu với kịch bản thật của bài trước
> khi quyết định giữ/bỏ/thêm phần nào** — xem quy trình chọn ở Mục 4.0.
>
> Điểm chung KHÔNG đổi cho mọi module dù cấu trúc bên trong khác nhau: 1 file HTML độc lập, không
> sidebar/header/Task bar điều hướng hay theo dõi tiến trình dưới bất kỳ hình thức nào — học sinh
> chỉ thấy đúng nội dung bài học, không có thanh trạng thái cố định nào che khuất màn hình (bỏ hẳn
> `#progress-tracker`/"Task bar" từng có ở Mục 4.1 bản cũ — xem ghi chú tại vị trí Mục 4.1 bên dưới).

```
header.hero (TUỲ CHỌN, ẩn được display:none nếu cần — xem quy tắc Mục 3.3/3.6 file Toán)
  eyebrow badge + h1 tên Unit + mô tả ngắn + thẻ nhân vật + mục tiêu bài học

main (ví dụ khi bài có đủ hội thoại + từ vựng + luyện tập + tự đánh giá — CÓ THỂ khác)
  ── KHỐI 1: BÀI HỌC ──────────────────────────────────────────────────────────────────────
  section#sec-top        → Top Panel gộp: Component 4.3 Phone Chat + 4.4 Vocabulary, có tab
                            chuyển đổi + nút Gom + khoá tuần tự (xem 4.8) — KHÔNG tách 2 section
                            rời nhau như bản cũ, vì Vocabulary thường rất dài (nhiều thẻ lật) và
                            xếp dọc trước Luyện tập sẽ đẩy phần bài tập ra ngoài màn hình mobile.
                            Vocabulary (4.4) trên mobile là carousel vuốt ngang có mũi tên; desktop
                            vẫn là lưới bình thường. Đây là khối "học nội dung mới", KHÔNG chấm điểm.

  ── KHỐI 2: LUYỆN TẬP (PRACTICE) ─────────────────────────────────────────────────────────
  section#sec-practice   → Component 4.5 Level Tabs + 4.6 các dạng bài, chạy step-gate tuần tự,
                            khoá tới khi Khối 1 hoàn thành (xem 4.8). NẾU luyện tập này gắn với
                            đúng nội dung bài học ở Khối 1 (hoặc với 1 đoạn Reading Passage — 4.10)
                            → bắt buộc kèm thêm Practice Reference Pane (4.8b): hiện lại bài
                            học/bài đọc đó song song bên cạnh câu hỏi, desktop chia đôi màn hình
                            theo chiều dọc (2 cột), mobile chia đôi theo chiều ngang (2 khối xếp
                            chồng, có nút chuyển "Chia đôi / Bài đọc / Câu hỏi" để gom-ẩn từng pane).
                            NẾU luyện tập không gắn với bài học cụ thể nào (VD bài ngữ pháp độc lập)
                            → bỏ Reference Pane, chỉ giữ Level Tabs + practiceHost như bản gốc.
  section#sec-assess     → Component 4.7 Self-assessment (nếu cần checklist tự đánh giá)

footer
```

> **2 khối luôn tách bạch:** Khối 1 (Bài học) là nơi học sinh TIẾP XÚC nội dung mới (đọc hội
> thoại, lật thẻ từ vựng, đọc bài đọc) — không có chấm điểm. Khối 2 (Luyện tập) là nơi học sinh
> LÀM BÀI có chấm đúng/sai — nội dung bài học chỉ xuất hiện lại ở đây dưới dạng tham chiếu
> read-only (Practice Reference Pane 4.8b), không lặp lại toàn bộ tương tác gốc (không lật thẻ,
> không phát âm lại trong Reference Pane).

---

## 4. Component Library — thư viện tham khảo, tự chọn & ghép theo kịch bản

### 4.0 Cách chọn & ghép component (đọc trước khi build)

Mục 4 là **thư viện**, không phải trình tự bắt buộc. Trước khi build, làm đúng quy trình sau
(giống cách phân tích kịch bản bên môn Toán ở `01_scenario_builder_v4.md` BƯỚC 1):

```
1. Đọc kịch bản/nội dung bài thật — không nhìn vào tên module (VD "Reading") để đoán cấu trúc.
2. Liệt kê CÁC HOẠT ĐỘNG THỰC TẾ bài cần có (VD: "đọc đoạn văn có từ mới cần giải nghĩa",
   "3 câu hỏi hiểu bài mức dễ", "1 bài nối từ", "học sinh tự viết đoạn ngắn"...).
3. Với mỗi hoạt động, chọn đúng component khớp nhất trong Mục 4.1-4.17 (không phải component
   "được gắn nhãn cho đúng tên module này" — 1 bài Speaking hoàn toàn có thể dùng component
   Reading Passage (4.10) nếu kịch bản có đoạn hội thoại mẫu cần đọc trước).
4. Sắp xếp lại theo đúng MẠCH DẠY của kịch bản đó — không nhất thiết theo thứ tự 4.1→4.16.
5. Phần nào kịch bản không cần → bỏ hẳn, không cố nhét cho "đủ khung".
6. Nếu kịch bản cần 1 dạng hoạt động chưa có trong thư viện → tạo component mới bám sát các
   nguyên tắc chung (Mục 0, token màu Mục 1, mobile Mục 5) thay vì ép vào component có sẵn không
   khớp bản chất hoạt động.
```

### 4.1 (ĐÃ BỎ — Task bar/Progress Tracker)

> **Đã bỏ hoàn toàn theo yêu cầu cập nhật mới nhất — không dùng lại dưới bất kỳ hình thức nào.**
> Bản trước Mục 4.1 là `#progress-tracker` (sidebar sticky bên phải desktop / thanh ngang sticky
> trên cùng mobile, liệt kê Tasks Messages/Vocabulary/Practice/Self-Assessment). Component này ĐÃ
> BỊ XOÁ HẲN khỏi hệ thống — không tạo lại `#progress-tracker`, `.pt-item`, `.pt-handle`, hàm
> `markDone()`, hay bất kỳ thanh/box liệt kê tiến trình tương tự nào (kể cả biến thể khác tên) ở
> BẤT KỲ file HTML nào, dù 1-file hay tách 2 file. Học sinh chỉ thấy đúng nội dung bài học; tiến
> trình hoàn thành do nền tảng LMS tự theo dõi qua `LMS().progress()`/`LMS().complete()` gọi ngầm
> trong code (xem PHẦN 7 file Toán), không cần và không được hiển thị bằng UI riêng trong bài.
>
> Số thứ tự Mục 4.1 giữ nguyên chỗ trống (không dồn số các mục 4.2 trở đi) để tránh phá vỡ toàn bộ
> tham chiếu số mục đã dùng xuyên suốt tài liệu này và ở `01_scenario_builder_tiengAnh.md`/
> `03_engine_tiengAnh.md`.

### 4.2 Hero/Header — tuỳ chọn, ẩn được

Dùng đúng quy tắc header ở Mục 3.3/3.6 file Toán: nếu header không chứa id JS cập nhật động, có
thể xoá hẳn khi nhúng platform khác; nếu có (hiếm với môn Anh, thường không có điểm số trong hero),
ẩn bằng `display:none`, giữ nguyên node.

```html
<header class="hero">
  <div class="hero-inner">
    <span class="eyebrow">✅ Unit [N] · [Tên phần]</span>
    <h1>[Tên Unit]<br>[Tên chủ đề phụ]</h1>
    <p class="sub">[Mô tả 1 dòng bằng tiếng Việt]</p>
    <div class="characters">
      <div class="char-card">
        <svg class="avatar" viewBox="0 0 60 60">...</svg>
        <div><div class="char-name">[Tên nhân vật]</div><div class="char-role">[vai trò/mô tả ngắn]</div></div>
      </div>
    </div>
    <div class="objectives">
      <div class="obj-pill"><span class="obj-num">1</span>[Mục tiêu 1]</div>
      <div class="obj-pill"><span class="obj-num">2</span>[Mục tiêu 2]</div>
    </div>
  </div>
</header>
```
```css
.hero { position:relative; background:var(--jade-deep); overflow:hidden; padding:64px 0 90px; }
.hero-inner { position:relative; z-index:2; text-align:center; color:#fff; max-width:640px; margin:0 auto; }
.eyebrow { display:inline-flex; align-items:center; gap:8px; background:rgba(255,255,255,.14);
  border:1px solid rgba(255,255,255,.35); padding:6px 16px; border-radius:999px; font-size:13px;
  text-transform:uppercase; margin-bottom:18px; }
.hero h1 { color:#fff; font-size:clamp(28px,5vw,46px); line-height:1.15; }
.hero p.sub { color:var(--sage); font-size:18px; margin-top:10px; font-weight:600; }
.characters { display:flex; justify-content:center; gap:26px; margin-top:34px; flex-wrap:wrap; }
.char-card { background:rgba(255,255,255,.12); border:1px solid rgba(255,255,255,.3);
  border-radius:18px; padding:14px 20px; display:flex; align-items:center; gap:12px; }
.avatar { width:52px; height:52px; border-radius:50%; }
.char-name { font-weight:700; color:#fff; font-size:16px; }
.char-role { font-size:12.5px; color:var(--cream-2); }
.objectives { margin:34px auto 0; display:flex; gap:12px; flex-wrap:wrap; justify-content:center; }
.obj-pill { background:#fff; color:var(--jade-dark); border-radius:14px; padding:12px 16px;
  font-size:14px; font-weight:600; display:flex; gap:10px; align-items:flex-start;
  box-shadow:var(--shadow); max-width:280px; text-align:left; }
.obj-num { background:var(--jade-deep); color:#fff; border-radius:50%; width:22px; height:22px;
  flex:0 0 auto; display:flex; align-items:center; justify-content:center; font-size:12px; font-weight:700; }

/* Ẩn khi nhúng platform khác đã có sẵn tiêu đề — không xoá node nếu còn id JS tham chiếu */
/* .hero { display: none; } */
```

### 4.3 Phone Chat — hội thoại hiện dần theo nhịp bấm

> **Vị trí thật trong trang:** thường nằm bên trong Top Panel gộp (xem 4.8), không phải section
> riêng độc lập. Nếu bài có cả Vocabulary theo sau, dòng cuối cùng khi hết tin nhắn (`markDone`)
> phải gọi thêm `unlockVocabTab()` (định nghĩa ở 4.8) để mở khoá tab Từ vựng — xem đoạn JS bên dưới.

**Giữ nguyên hành vi:** tin nhắn KHÔNG hiện hết cùng lúc — học sinh bấm "Tin tiếp theo" để hiện
từng tin, có typing-indicator trước khi tin hiện ra (mô phỏng nhắn tin thật, tăng cảm giác theo dõi
hội thoại thay vì đọc 1 khối văn bản).

> **Cách vẽ 1 tin nhắn (bắt buộc):** mỗi dòng tin gồm **avatar nhân vật + bong bóng + dòng meta
> "tên người nói · giờ"**, KHÔNG phải chỉ bong bóng + giờ. Lý do: hội thoại Tiếng Anh luôn có ≥2
> nhân vật và câu hỏi luyện tập hay hỏi thẳng "*What does **Đức's dad** usually do?*" — nếu chỉ
> phân biệt người nói bằng trái/phải + màu bong bóng thì học sinh cuộn lại vẫn phải tự đếm lượt để
> biết ai nói câu nào. Avatar hiện ở CẢ typing-indicator (biết ai đang gõ) lẫn tin đã hiện, và ở cả
> Reference Pane (4.8b) lúc luyện tập. Toàn bộ tên + hình avatar khai báo 1 lần trong map `speaker`
> ở đầu script — không viết cứng tên nhân vật trong hàm render.

```html
<div class="phone-wrap">
  <div class="phone">
    <div class="phone-head">
      <!-- Avatar 2 nhân vật ở đầu khung chat: SVG inline chồng mép nhau (dùng ĐÚNG `shapes` của
           map `speaker` bên dưới). Không dùng <img src="..."> — file phải tự chứa, không có ảnh
           ngoài để trỏ tới (Mục 6). -->
      <div class="avatars">
        <svg viewBox="0 0 60 60" aria-hidden="true"><!-- speaker.a.shapes --></svg>
        <svg viewBox="0 0 60 60" aria-hidden="true"><!-- speaker.b.shapes --></svg>
      </div>
      <div class="who">[Tên nhân vật A] &amp; [Tên nhân vật B]</div>
    </div>
    <div class="phone-body" id="phoneBody"></div>
    <div class="phone-controls">
      <button class="chip-btn ghost" id="btnRestart">↺ Xem lại</button>
      <span class="msg-counter" id="msgCounter">0 / [N]</span>
      <button class="chip-btn" id="btnNext">Tin tiếp theo →</button>
    </div>
  </div>
  <!-- Lối thoát cho học sinh đã đọc rồi / quay lại bài: bấm N lần "Tin tiếp theo" mới qua được
       phần sau là hình phạt, không phải thiết kế học tập. Bấm nút này vẫn tính là đã đọc xong
       (mở khoá Vocabulary bình thường), chỉ bỏ qua hiệu ứng gõ từng tin. -->
  <div class="msg-skip-row">
    <button class="skip-btn" id="btnSkipMsgs">Đã đọc rồi — hiện hết tin nhắn ⏭</button>
  </div>
</div>
```
```css
.phone { width:min(380px,92vw); background:var(--white); border-radius:34px;
  border:8px solid var(--jade-dark); box-shadow:var(--shadow); overflow:hidden; margin:0 auto; }
.phone-head { background:var(--jade-dark); color:#fff; padding:14px 18px; display:flex; align-items:center; gap:10px; }
.phone-head .avatars { display:flex; }
.phone-head .avatars svg { width:34px; height:34px; border-radius:50%; border:2px solid var(--jade-dark); }
.phone-head .avatars svg:last-child { margin-left:-12px; } /* chồng mép -> cụm "2 người trong 1 hội thoại" */
.phone-head .who { font-size:14px; font-weight:700; }
.phone-body { height:400px; overflow-y:auto; padding:18px 14px; background:var(--cream-2);
  display:flex; flex-direction:column; gap:4px; }
.msg-row { display:flex; gap:8px; align-items:flex-end; opacity:0; transform:translateY(6px); animation:pop .35s forwards; }
@keyframes pop { to{opacity:1;transform:translateY(0);} }
.msg-row.left { justify-content:flex-start; }
.msg-row.right { justify-content:flex-end; }
/* Avatar nằm NGANG HÀNG với bong bóng, canh đáy; margin-bottom đẩy avatar lên khỏi dòng meta
   "tên · giờ" để nó thẳng mép dưới bong bóng chứ không tụt xuống ngang dòng chữ nhỏ. */
.msg-avatar { width:30px; height:30px; border-radius:50%; flex:0 0 auto; margin-bottom:16px; }
/* Giới hạn 72% giờ đặt ở KHỐI (bong bóng + meta), không đặt ở .bubble — vì hàng đã có thêm avatar
   chiếm chỗ; để 72% trên .bubble sẽ tính theo chiều rộng khối con, tin dài bị tràn lệch. */
.msg-row > div { max-width:72%; }
.bubble { max-width:100%; padding:10px 14px; border-radius:16px; font-size:15px; line-height:1.5; min-height:20px; }
.msg-row.left .bubble { background:var(--white); border-bottom-left-radius:4px; color:var(--ink); }
.msg-row.right .bubble { background:var(--jade-deep); color:#fff; border-bottom-right-radius:4px; }
.msg-time { font-size:10px; color:var(--ink-3); margin-top:2px; }
.msg-row.left .msg-time { text-align:left; }
.msg-row.right .msg-time { text-align:right; } /* meta bám sát mép bong bóng của phía mình */
.msg-who { font-weight:700; color:var(--ink-2); }
.msg-row.right .msg-who { color:var(--sage-text); }
/* Từ vựng/collocation xuất hiện NGAY TRONG câu chat được tô nổi bật — học sinh nhận ra mặt chữ
   trước khi gặp lại ở thẻ Vocabulary (4.4), không phải học 2 lần từ 2 nguồn rời rạc. */
.kw-inline { background:var(--accent-pale); color:var(--accent-text); border-radius:6px;
  padding:1px 5px; font-weight:700; }
.msg-row.right .kw-inline { background:rgba(255,255,255,.22); color:#fff; }
.typing { display:flex; gap:4px; padding:10px 14px; background:var(--white); border-radius:16px; width:fit-content; }
.typing span { width:6px; height:6px; background:var(--ink-3); border-radius:50%; animation:bounce 1s infinite; }
.typing span:nth-child(2){animation-delay:.15s;} .typing span:nth-child(3){animation-delay:.3s;}
@keyframes bounce{0%,60%,100%{transform:translateY(0);}30%{transform:translateY(-4px);}}
.phone-controls { display:flex; justify-content:space-between; align-items:center; padding:12px 16px;
  background:var(--white); border-top:1px solid var(--cream-2); gap:8px; }
.chip-btn { background:var(--jade-deep); color:#fff; border:none; border-radius:12px; padding:9px 16px;
  font-weight:600; font-size:13.5px; min-height:40px; }
.chip-btn:disabled { background:var(--sage); cursor:default; }
.chip-btn.ghost { background:transparent; color:var(--jade-dark); border:1.5px solid var(--sage); }
@media (max-width: 640px) { .chip-btn { min-height:44px; padding:10px 16px; } }
.msg-skip-row { display:flex; justify-content:center; margin-top:12px; }
.skip-btn { background:transparent; border:1.5px dashed var(--sage); color:var(--ink-2);
  border-radius:999px; padding:8px 16px; min-height:44px; font-size:12.5px; font-weight:600; }
.skip-btn:hover { border-color:var(--jade-deep); color:var(--jade-text); }
```
```javascript
// esc(): dùng ở MỌI nơi chèn text tự do (word, nghia, ex, message.text nếu không có kw-inline...)
// vào innerHTML bằng template string — chặn học sinh/nội dung kịch bản chứa ký tự < > & " phá cấu
// trúc HTML. text đã CHỦ ĐỘNG chèn thẻ <span class="kw-inline"> (như message.text bên dưới) thì
// KHÔNG esc() phần đó — chỉ esc() các trường thuần text khác (word, nghia, ex...).
function esc(s){ return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;'); }

// Danh tính người nói khai báo 1 CHỖ DUY NHẤT — mọi nơi cần tên/avatar (khung chat, Reference Pane
// 4.8b, và cả phone-head) đều đọc từ đây, không viết cứng tên nhân vật rải rác trong hàm render.
// Giữ hình avatar ở dạng "ruột" SVG (`shapes`, chưa có thẻ <svg> bao ngoài) để dùng lại được ở
// nhiều kích cỡ/vị trí khác nhau qua avatarHTML(who, cls) mà không phải chép SVG ra nhiều bản dễ
// lệch nhau — mỗi chỗ tự truyền class riêng (.msg-avatar / .ref-msg-avatar / .avatar...).
// Khoá của map PHẢI trùng đúng giá trị `who` trong messages[]. Quy ước: 'a' = vẽ bên TRÁI (người
// đối thoại), 'b' = vẽ bên PHẢI (nhân vật "mình"). Đặt tên khoá theo nhân vật ('vy'/'duc') cũng
// được, miễn quyết định trái/phải nằm đúng 1 chỗ (hằng isLeft bên dưới), không rải khắp file.
const speaker = {
  a: { name:'[Tên nhân vật A]',
       shapes:'<circle cx="30" cy="30" r="30" fill="#DCEAE1"/><circle cx="30" cy="24" r="11" fill="#2D8B6F"/>'
             + '<path d="M8 56c3-13 11-19 22-19s19 6 22 19z" fill="#14432F"/>' },
  b: { name:'[Tên nhân vật B]',
       shapes:'<circle cx="30" cy="30" r="30" fill="#F7E7CD"/><circle cx="30" cy="24" r="11" fill="#E8A24A"/>'
             + '<path d="M8 56c3-13 11-19 22-19s19 6 22 19z" fill="#CE8A33"/>' }
};
// aria-hidden: avatar là hình trang trí, tên người nói đã có bằng CHỮ ở dòng meta ngay dưới bong
// bóng — để trình đọc màn hình đọc tên 1 lần, không đọc lặp 2 lần cho mỗi tin.
function avatarHTML(who, cls){
  return `<svg class="${cls}" viewBox="0 0 60 60" aria-hidden="true">${speaker[who].shapes}</svg>`;
}

// message.text được soạn sẵn có thể chứa <span class="kw-inline">...</span> quanh đúng
// collocation/từ vựng của bài — bôi trực tiếp trong data, không xử lý bằng JS lúc render.
const messages = [
  { who:'a', time:'18:42', text:'... <span class="kw-inline">set up a club</span> ...' },
  /* ... */
];
let msgIndex = 0;

// 1 hàm dựng dòng tin dùng CHUNG cho cả bấm từng tin lẫn nút "hiện hết" — 2 nhánh tự viết HTML
// riêng là cách chắc chắn nhất để avatar/tên người nói có ở nhánh này mà thiếu ở nhánh kia.
// Avatar đứng TRƯỚC bong bóng khi ở bên trái, đứng SAU khi ở bên phải (đúng chiều nhìn của người
// đọc: người đối thoại ngoài lề trái, mình ngoài lề phải). m.text KHÔNG esc() (đã chủ động chứa
// <span class="kw-inline">), tên + giờ vẫn esc() bình thường.
function buildMsgRow(m){
  const sp = speaker[m.who];
  const isLeft = m.who === 'a';
  const row = document.createElement('div');
  row.className = 'msg-row ' + (isLeft ? 'left' : 'right');
  const body = `<div><div class="bubble">${m.text}</div>`
    + `<div class="msg-time"><span class="msg-who">${esc(sp.name)}</span> · ${esc(m.time)}</div></div>`;
  const av = avatarHTML(m.who, 'msg-avatar');
  row.innerHTML = isLeft ? av + body : body + av;
  return row;
}

function renderNextMessage(){
  if (msgIndex >= messages.length) { btnNext.disabled = true; btnNext.textContent = 'Hết tin nhắn'; markDone('messages'); return; }
  const m = messages[msgIndex];
  const isLeft = m.who === 'a';
  // Typing-indicator cũng mang avatar của đúng người đang gõ — không phải 3 chấm trôi nổi vô danh
  const typing = document.createElement('div');
  typing.className = 'msg-row ' + (isLeft ? 'left' : 'right');
  const dots = `<div class="typing"><span></span><span></span><span></span></div>`;
  const avT = avatarHTML(m.who, 'msg-avatar');
  typing.innerHTML = isLeft ? avT + dots : dots + avT;
  phoneBody.appendChild(typing); phoneBody.scrollTop = phoneBody.scrollHeight; btnNext.disabled = true;
  setTimeout(() => {
    typing.remove();
    phoneBody.appendChild(buildMsgRow(m)); phoneBody.scrollTop = phoneBody.scrollHeight;
    msgIndex++; msgCounter.textContent = `${msgIndex} / ${messages.length}`;
    btnNext.disabled = msgIndex >= messages.length;
    if (msgIndex >= messages.length) { btnNext.textContent = 'Hết tin nhắn'; markDone('messages'); unlockVocabTab(); }
  }, 550);
}
// Bấm "Đã đọc rồi": hiện hết tin nhắn ngay lập tức (không đợi hiệu ứng gõ từng tin), vẫn markDone
// + unlockVocabTab() như hết tin nhắn bình thường.
btnSkipMsgs.addEventListener('click', () => {
  while (msgIndex < messages.length) { phoneBody.appendChild(buildMsgRow(messages[msgIndex])); msgIndex++; }
  phoneBody.scrollTop = phoneBody.scrollHeight;
  msgCounter.textContent = `${msgIndex} / ${messages.length}`;
  btnNext.disabled = true; btnNext.textContent = 'Hết tin nhắn';
  btnSkipMsgs.style.display = 'none';
  markDone('messages'); unlockVocabTab();
});
// Nút "↺ Xem lại": xoá sạch khung chat + reset bộ đếm để đọc lại từ đầu (KHÔNG gọi lại markDone/
// unlock — 2 phần sau đã mở khoá rồi thì giữ nguyên, xem lại hội thoại không phải là làm lại bài).
btnRestart.addEventListener('click', () => {
  phoneBody.innerHTML = ''; msgIndex = 0;
  msgCounter.textContent = `0 / ${messages.length}`;
  btnNext.disabled = false; btnNext.textContent = 'Tin tiếp theo →';
});
```

> **Bài đăng mạng xã hội / diễn đàn thay cho chat 1-1:** nếu kịch bản là bài đăng + bình luận (chứ
> không phải tin nhắn qua lại), giữ NGUYÊN map `speaker` + `avatarHTML()` + nhịp hiện dần + typing
> ở trên, chỉ đổi phần vỏ: thêm `kind:'post'` cho phần tử bài đăng gốc, vẽ nó thành thẻ bài đăng
> rộng hết khung thay vì bong bóng trái/phải, các phần tử còn lại là bình luận. Avatar + tên người
> nói vẫn bắt buộc có ở mọi dòng — chính vì bài đăng có nhiều hơn 2 người tham gia nên càng không
> thể phân biệt người nói bằng trái/phải được nữa.


### 4.4 Vocabulary Flashcard — lật 3D + phát âm, carousel trên mobile, tối ưu tới 12 thẻ

> **Vị trí thật trong trang:** nằm trong Top Panel gộp (xem 4.8), tab "Từ vựng".
>
> **Desktop (≥641px): lưới bình thường, số cột co giãn theo SỐ THẺ THẬT** (tối đa 12) để lưới luôn
> gọn trong 2-3 hàng, không còn giới hạn `max-height` + cuộn nội bộ như bản cũ (bản cũ dùng
> `max-height:52vh` để chặn Top Panel phình dài — nay không cần nữa vì mặt trước thẻ nằm trong
> luồng bình thường, chiều cao tự nhiên theo tỉ lệ ảnh, và số cột đã co giãn đúng theo số thẻ).
>
> **Mobile (≤640px): chuyển hẳn sang carousel vuốt ngang có mũi tên bấm** — KHÔNG xếp lưới dọc.
> Lý do: xếp dọc trên điện thoại với 8-12 thẻ sẽ hoặc quá dài (đẩy Luyện tập ra xa), hoặc quá hẹp
> nếu ép nhiều cột (chữ không đọc nổi). Carousel giữ chiều cao khung cố định dù bài có 1 hay 12 thẻ,
> học sinh vuốt hoặc bấm nút `‹ ›` để chuyển thẻ, có số thứ tự "3/12" theo dõi vị trí.

> ⚠️ **Lỗi đã gặp thật — chữ trên thẻ MỜ NHOÈ khi xem bằng điện thoại.** Chrome/Safari di động vẽ
> cả khối `transform-style: preserve-3d` ra **một ảnh bitmap** rồi mới xoay/phóng ảnh đó, nên chữ
> trong thẻ bị nhoè như ảnh phóng to. **Dấu hiệu nhận ra: chỉ mình cụm thẻ mờ, còn thanh
> `#progress-tracker` và nút bấm ngay cạnh vẫn sắc nét** — nếu mờ đều cả trang thì đó chỉ là ảnh
> chụp bị thu nhỏ, không phải lỗi này. Lộ rõ nhất ở carousel mobile vì thẻ được phóng tới 84% bề
> ngang màn hình; trên desktop thẻ nhỏ nên gần như không nhận ra → **bắt buộc nghiệm thu trên máy
> thật, không tin màn hình desktop.**
>
> **Cách chữa (đã áp dụng, xem CSS `.vcard.settled` + `scheduleSettle()`/`flipCard()` bên dưới):**
> chỉ giữ ngữ cảnh 3D **trong lúc đang lật**; lật xong thì bỏ hẳn 3D và đổi mặt bằng ẩn/hiện, để
> trình duyệt vẽ lại chữ ở đúng độ phân giải màn hình. **Hiệu ứng lật 3D giữ nguyên 100%** — chỉ
> khác là lớp 3D được tháo bỏ khi thẻ đã đứng yên.
>
> ⚠️ **Bẫy kép khi sửa lỗi trên — rất dễ vừa vá vừa làm hỏng hiệu ứng lật.** Ở trạng thái phẳng
> `.settled`, thẻ đang lật hiển thị mặt sau bằng ẩn/hiện nên `transform` là `none`, trong khi mốc
> 3D tương đương của **đúng cảnh đó** lại là `rotateY(180deg)` — hai giá trị KHÁC nhau dù nhìn y
> hệt. Bỏ `.settled` trong lúc transition đang bật sẽ tự khởi động chuyển tiếp 0°→180°, rồi thao
> tác bỏ `.flipped` ngay sau đó kéo đích về 0° → hai đầu bằng nhau → thẻ đứng im.
> **Hậu quả: mất sạch hiệu ứng ở CHIỀU LẬT NGƯỢC, còn chiều lật xuôi vẫn chạy bình thường** (vì cả
> 2 mốc của chiều xuôi đều là `none`) — nên nghiệm thu qua loa 1 chiều là không phát hiện ra.
> → **Khi nghiệm thu PHẢI bấm lật cả 2 chiều** (mặt trước→sau và sau→trước).
>
> Thứ tự bắt buộc trong `flipCard()`: khoá transition → bỏ `.settled` → **chốt mốc bằng
> `getComputedStyle(inner).transform`** → mở lại transition → mới toggle `.flipped`. Đừng chốt mốc
> bằng mẹo quen thuộc `void el.offsetWidth`: nó chỉ ép tính lại **layout**, mà `transform` không
> làm bẩn layout nên lần ép đó bị bỏ qua hoàn toàn và lỗi vẫn còn nguyên.

#### Ảnh minh hoạ mặt trước thẻ — 2 ô `img` / `illus`, luôn chừa sẵn ô dán link

Mỗi phần tử `vocab[]` có **2 ô ảnh**, `img` được ưu tiên, `illus` là bản dự phòng:

| Ô | Kiểu | Dùng khi |
|---|---|---|
| `img` | chuỗi đường dẫn ảnh (`''` nếu chưa có) | **Mặc định khi build** — giáo viên/người soạn dán ảnh thật vào sau |
| `illus` | chuỗi SVG inline (`viewBox="0 0 200 200" preserveAspectRatio="xMidYMid meet"`, KHÔNG rect nền) | Chưa có link, hoặc link tải hỏng — vẽ tạm bằng token màu Mục 1 |

> **Luôn sinh sẵn ô `img: ''` kèm comment `/* ← dán link ảnh "<từ>" vào đây */` cho MỌI thẻ**, kể
> cả khi đã vẽ `illus` đẹp. Người soạn nội dung không đọc code — không thấy chỗ dán link thì phải
> quay lại nhờ sửa. Đồng thời **giữ luôn `illus`** để thẻ không bao giờ trống trong lúc chờ ảnh.
>
> ⚠️ **Sandbox LMS (Mục 6) chỉ cho gọi mạng tới `cdn.jsdelivr.net`, `fonts.googleapis.com`,
> `fonts.gstatic.com`.** Link ảnh từ host khác (Google Drive, Imgur, web trường...) mở bằng Live
> Server thì thấy ảnh, nhưng **nhúng vào LMS sẽ bị chặn** và thẻ rơi về ảnh dự phòng — lỗi này chỉ
> lộ ra lúc bàn giao. Ghi rõ 3 dạng dùng được ngay trong comment trên mảng `vocab`:
> 1. `data:` URI — `img: 'data:image/webp;base64,UklGR...'` (an toàn nhất, không phải gọi mạng)
> 2. jsdelivr — `img: 'https://cdn.jsdelivr.net/gh/<user>/<repo>@<tag>/img/laptop.webp'`
> 3. ảnh cùng thư mục với file HTML — `img: 'img/laptop.webp'` (nếu LMS phục vụ cả thư mục)
>
> Ảnh nên **vuông (1:1)** cho khớp `.illus-box`, nền sáng, ~400×400px. `.illus-box` đã có
> `aspect-ratio` + `object-fit:contain` nên ảnh lệch tỉ lệ vẫn hiện trọn, chỉ bị viền thừa 2 bên.

```html
<div class="vocab-head">
  <span class="vocab-status" id="vocabStatus">Đã lật 0/12 thẻ</span>
  <div class="vocab-nav" id="vocabNav">
    <button class="vnav-btn" id="vocabPrev" aria-label="Thẻ trước">‹</button>
    <span class="vocab-pos" id="vocabPos">1/12</span>
    <button class="vnav-btn" id="vocabNext" aria-label="Thẻ tiếp theo">›</button>
  </div>
</div>
<div class="vocab-grid" id="vocabGrid"></div>
```
```css
.vocab-head { display:flex; justify-content:space-between; align-items:center; gap:12px;
  margin-bottom:12px; flex-wrap:wrap; }
.vocab-status { font-size:12.5px; font-weight:600; color:var(--ink-2); background:var(--cream-2);
  border-radius:999px; padding:6px 14px; }
.vocab-status.done { background:var(--correct-bg); color:var(--jade-text); }
.vocab-nav { display:none; align-items:center; gap:8px; } /* chỉ hiện ở carousel (mobile) */
.vocab-nav.off { display:none !important; } /* ẩn hẳn khi bài chỉ có 1 thẻ — không cần điều hướng */
.vnav-btn { width:44px; height:44px; border-radius:50%; border:2px solid var(--sage);
  background:var(--white); color:var(--jade-dark); font-size:20px; font-weight:800; line-height:1; }
.vnav-btn:disabled { opacity:.35; }
.vocab-pos { font-size:12.5px; font-weight:700; color:var(--jade-dark); min-width:42px; text-align:center; }

/* Desktop: số cột co theo SỐ THẺ THẬT (1-12) để lưới luôn gọn, không tràn quá 3 hàng.
   .compact thu nhỏ chữ/padding khi cột hẹp (4 hoặc 7-8-9-10-11-12 thẻ). */
.vocab-grid { display:grid; gap:16px; grid-template-columns:repeat(auto-fit,minmax(195px,1fr));
  align-items:flex-start; }
.vocab-grid[data-count="1"], .vocab-grid[data-count="2"] {
  grid-template-columns:repeat(auto-fit,240px); justify-content:center; }
.vocab-grid[data-count="4"] { grid-template-columns:repeat(auto-fit,minmax(175px,1fr)); }
.vocab-grid[data-count="7"], .vocab-grid[data-count="8"], .vocab-grid[data-count="9"] {
  grid-template-columns:repeat(auto-fit,minmax(170px,1fr)); }
.vocab-grid[data-count="10"], .vocab-grid[data-count="11"], .vocab-grid[data-count="12"] {
  grid-template-columns:repeat(auto-fit,minmax(150px,1fr)); }
.vocab-grid.compact .vfront .word { font-size:13.5px; }
.vocab-grid.compact .vfront .ipa, .vocab-grid.compact .vfront .hint { font-size:11px; }
.vocab-grid.compact .vfront .label { padding:7px 8px 8px; }
.vocab-grid.compact .vface { padding:14px; }
.vocab-grid.compact .vback .nghia { font-size:14.5px; }
.vocab-grid.compact .vback .ex { font-size:12px; line-height:1.5; }

.vcard { perspective:1200px; }
.vcard-inner { position:relative; width:100%; transition:transform .55s cubic-bezier(.2,.8,.3,1); transform-style:preserve-3d; }
.vcard.flipped .vcard-inner { transform:rotateY(180deg); }

/* ---- .settled — BẮT BUỘC CÓ, chống mờ chữ trên điện thoại (lỗi đã gặp thật) ----
   Chrome/Safari di động vẽ cả khối `transform-style:preserve-3d` ra MỘT ảnh bitmap rồi mới xoay/
   phóng ảnh đó, nên chữ trong thẻ bị nhoè trong khi phần còn lại của trang vẫn nét. Dấu hiệu nhận
   ra: chỉ mình cụm thẻ mờ, thanh Tasks/nút bấm ngay cạnh vẫn sắc. Thấy rõ nhất ở carousel mobile
   vì thẻ được phóng tới 84% bề ngang màn hình.
   Cách chữa: chỉ giữ 3D TRONG LÚC lật; lật xong (JS gắn .settled sau ~620ms) bỏ hẳn 3D, đổi mặt
   bằng ẩn/hiện -> trình duyệt vẽ lại chữ ở đúng độ phân giải màn hình. */
.vcard.settled .vcard-inner { transform:none; transform-style:flat; transition:none; }
.vcard.settled .vface { backface-visibility:visible; }
.vcard.settled .vback { transform:none; display:none; }
/* visibility (không phải display) để mặt trước vẫn giữ chỗ — mặt sau phủ tuyệt đối lên nó, bỏ hẳn
   mặt trước thì thẻ sập chiều cao. */
.vcard.settled.flipped .vfront { visibility:hidden; }
.vcard.settled.flipped .vback { display:flex; }
/* HIỆU ỨNG LẬT GIỮ NGUYÊN 100% — .settled chỉ áp KHI THẺ ĐÃ ĐỨNG YÊN (sau .55s xoay), không đụng
   gì tới lúc đang xoay. Khi nghiệm thu phải bấm lật CẢ 2 CHIỀU: lỗi mất hiệu ứng chỉ lộ ở chiều
   lật ngược (xem cảnh báo trong flipCard bên dưới). */
.vface { backface-visibility:hidden; border-radius:var(--radius-lg);
  padding:18px; display:flex; flex-direction:column; justify-content:center; box-shadow:var(--shadow); }
/* Mặt trước trong luồng (quyết định chiều cao thẻ thật): khung hình trên (hiện TRỌN, không cắt)
   + dải chữ đặc dưới. Mặt sau phủ tuyệt đối lên trên mặt trước. */
.vfront { position:relative; background:var(--white); border:2px solid var(--cream-2); cursor:pointer;
  padding:0; overflow:hidden; justify-content:flex-start; }
.vfront .illus-box { flex:0 0 auto; aspect-ratio:200/200; background:var(--cream-2); padding:6px; }
/* Dùng chung cho <img> (ô `img`) lẫn <svg> (ô `illus`) — object-fit:contain giữ ảnh hiện TRỌN,
   ảnh không vuông chỉ bị viền thừa 2 bên chứ không bị cắt. */
.vfront .card-illus { width:100%; height:100%; object-fit:contain; display:block; }
/* Ô chờ ảnh: hiện khi thẻ chưa có ảnh nào, hoặc link ảnh hỏng/bị sandbox chặn. Vẫn giữ đúng khung
   vuông để lưới không nhảy khi dán link vào sau. */
.vfront .illus-empty { width:100%; height:100%; display:flex; flex-direction:column; align-items:center;
  justify-content:center; gap:4px; border:2px dashed var(--paper-line-2); border-radius:var(--radius-sm);
  color:var(--ink-3); font-size:11.5px; font-weight:600; text-align:center; padding:8px; }
.vfront .illus-empty .ie-icon { font-size:22px; line-height:1; }
.vfront .label { flex:0 0 auto; background:var(--white); border-top:2px solid var(--cream-2);
  padding:9px 10px 10px; text-align:center; }
.vfront .num { position:absolute; top:10px; left:12px; color:#fff; font-size:12px; font-weight:700;
  background:rgba(26,26,26,.45); padding:2px 9px; border-radius:999px; z-index:2; }
/* Thẻ đã lật ở lần học trước (khôi phục từ LMS state khi quay lại bài — xem onResume ở PHẦN 6) —
   đổi màu số thứ tự + thêm dấu ✓ để học sinh biết thẻ nào đã xem rồi mà vẫn ôn lại được bình thường */
.vcard.seen .vfront .num { background:var(--jade-dark); }
.vcard.seen .vfront .num::after { content:' ✓'; }
.vfront .word { font-weight:800; font-size:14.5px; color:var(--jade-dark); line-height:1.25;
  min-height:2.5em; display:flex; align-items:center; justify-content:center; overflow-wrap:anywhere; }
.vfront .ipa { font-size:12px; color:var(--ink-3); margin-top:2px; }
.vfront .hint { font-size:11.5px; color:var(--jade-deep); font-weight:600; margin-top:4px; }
.vback { position:absolute; inset:0; background:var(--jade-dark); color:#fff; transform:rotateY(180deg);
  cursor:pointer; overflow-y:auto; justify-content:flex-start; }
.vback .en { font-size:13px; color:var(--jade-pale); font-weight:700; margin-bottom:4px; margin-top:auto; }
.vback .nghia { font-weight:700; font-size:17px; margin-bottom:8px; }
.vback .ex { font-size:12.5px; color:var(--sage); font-style:italic; line-height:1.5; margin-bottom:auto; }
.audio-btn { position:absolute; top:10px; right:12px; background:var(--accent); border:none;
  width:30px; height:30px; border-radius:50%; display:flex; align-items:center; justify-content:center; }

/* Mobile: CAROUSEL vuốt ngang thay cho lưới dọc — chiều cao khung không đổi dù 1 hay 12 thẻ */
@media (max-width: 640px) {
  .vocab-grid, .vocab-grid[data-count] {
    display:flex; overflow-x:auto; scroll-snap-type:x mandatory; gap:12px;
    padding:2px 2px 8px; justify-content:flex-start; scrollbar-width:none;
    -webkit-overflow-scrolling:touch; }
  .vocab-grid::-webkit-scrollbar { display:none; }
  .vcard, .vocab-grid.compact .vcard { flex:0 0 84%; scroll-snap-align:center; }
  .vocab-grid[data-count="1"] .vcard { flex-basis:100%; }
  .vfront .illus-box { max-height:46vh; } /* chặn trần chiều cao ảnh trên máy hẹp */
  .vocab-nav { display:flex; }
  .audio-btn { width:36px; height:36px; }
  /* Quan trọng: .compact (chữ thu nhỏ) được thiết kế cho CỘT HẸP trên desktop (4 hoặc 7-12 thẻ
     chia lưới). Trên mobile, mỗi thẻ carousel LUÔN chiếm 84% màn hình bất kể tổng số thẻ — không
     hề hẹp — nên phải reset lại cỡ chữ về mức bình thường, không kế thừa mức thu nhỏ của desktop. */
  .vocab-grid.compact .vfront .word { font-size:15px; }
  .vocab-grid.compact .vfront .ipa { font-size:12.5px; }
  .vocab-grid.compact .vfront .hint { font-size:12px; }
  .vocab-grid.compact .vfront .label { padding:9px 10px 10px; }
  .vocab-grid.compact .vface { padding:18px; }
  .vocab-grid.compact .vback .nghia { font-size:17px; }
  .vocab-grid.compact .vback .ex { font-size:13px; line-height:1.55; }
}
```
```javascript
// img: LUÔN sinh sẵn ô này (kể cả rỗng) kèm comment chỉ chỗ dán — xem khung cảnh báo sandbox ở trên.
const vocab = [
  { word:"...", ipa:"...", nghia:"...", ex:"...",
    img:'',                       /* ← dán link ảnh "<từ>" vào đây */
    illus:"<svg class='card-illus' viewBox='0 0 200 200' preserveAspectRatio='xMidYMid meet'>...</svg>" },
  /* tối đa 12 thẻ */
];
const vocabGrid = document.getElementById('vocabGrid');
const vocabStatus = document.getElementById('vocabStatus');
const vocabNav = document.getElementById('vocabNav');
const vocabPos = document.getElementById('vocabPos');
const vocabPrev = document.getElementById('vocabPrev');
const vocabNext = document.getElementById('vocabNext');
const flippedSet = new Set(); // theo dõi số thẻ đã lật để biết khi nào lật đủ hết -> mở khoá Luyện tập

// data-count chọn số cột desktop (xem CSS); .compact thu nhỏ chữ khi cột hẹp (4 hoặc 7-12 thẻ).
vocabGrid.dataset.count = vocab.length;
vocabGrid.classList.toggle('compact', vocab.length === 4 || vocab.length >= 7);
if (vocab.length <= 1) vocabNav.classList.add('off');

function updateVocabStatus(){
  vocabStatus.textContent = `Đã lật ${flippedSet.size}/${vocab.length} thẻ`;
  vocabStatus.classList.toggle('done', flippedSet.size === vocab.length);
}
/* Thẻ là phần tử TƯƠNG TÁC (role="button"), không phải <div> trơ — bàn phím/trình đọc màn hình
   cũng lật được. setFaceState() ẩn mặt đang úp khỏi accessibility tree + khỏi tab-order (focus
   vào phần tử aria-hidden là lỗi a11y); dùng role="button" trên <div> vì bên trong đã có <button>
   loa — <button> lồng <button> là HTML không hợp lệ. */
function setFaceState(card, flipped){
  const front = card.querySelector('.vfront'), back = card.querySelector('.vback');
  front.setAttribute('aria-hidden', String(flipped));
  back.setAttribute('aria-hidden', String(!flipped));
  front.querySelectorAll('button').forEach(b => { b.tabIndex = flipped ? -1 : 0; });
  back.querySelectorAll('button').forEach(b => { b.tabIndex = flipped ? 0 : -1; });
  card.setAttribute('aria-pressed', String(flipped));
}
/* Chọn ảnh mặt trước theo thứ tự ưu tiên: link `img` -> SVG dự phòng `illus` -> ô chờ.
   src PHẢI qua esc(): đây là chuỗi tự do người soạn dán vào, dấu " trong link sẽ phá thuộc tính. */
function illusHTML(v){
  if (v.img) return `<img class="card-illus" src="${esc(v.img)}" alt="Hình minh hoạ: ${esc(v.word)}" loading="lazy">`;
  if (v.illus) return v.illus;
  return '<div class="illus-empty"><span class="ie-icon" aria-hidden="true">🖼️</span>Chưa có ảnh</div>';
}
/* Link hỏng / bị sandbox chặn: <img> vỡ sẽ hiện biểu tượng ảnh lỗi của trình duyệt ngay giữa thẻ.
   Rơi về SVG dự phòng (hoặc ô chờ) để thẻ vẫn học được, không thành thẻ hỏng. Gắn bằng listener,
   KHÔNG dùng onerror inline — file có thể chạy dưới CSP chặn inline handler. */
function wireIllusFallback(card, v){
  const img = card.querySelector('.card-illus');
  if (!img || img.tagName !== 'IMG') return;
  img.addEventListener('error', () => {
    const box = img.closest('.illus-box');
    if (box) box.innerHTML = v.illus || '<div class="illus-empty"><span class="ie-icon" aria-hidden="true">🖼️</span>Ảnh không tải được</div>';
  });
}

/* Gắn .settled khi thẻ đã lật xong để bỏ ngữ cảnh 3D (xem CSS .vcard.settled — chống mờ chữ).
   Dùng hẹn giờ chứ KHÔNG dùng 'transitionend': sự kiện đó không bắn khi transition bị tắt
   (prefers-reduced-motion) hoặc khi thẻ nằm trong tab đang ẩn -> thẻ kẹt vĩnh viễn ở trạng thái mờ. */
const settleTimers = new WeakMap();
function scheduleSettle(card){
  clearTimeout(settleTimers.get(card));
  settleTimers.set(card, setTimeout(() => card.classList.add('settled'), 620));
}

function flipCard(card, i){
  /* ---- Rời trạng thái phẳng .settled đúng cách — 5 dòng dưới đây PHẢI giữ nguyên thứ tự ----
     Thẻ đang lật ở trạng thái .settled hiển thị mặt sau bằng cách ẩn/hiện, `transform` là `none`;
     còn mốc 3D tương đương của đúng cảnh đó lại là `rotateY(180deg)`. Hai giá trị KHÁC nhau dù
     nhìn y hệt. Nếu bỏ .settled khi transition đang bật, chính thao tác đó đã khởi động chuyển
     tiếp 0°→180°; ngay sau đó bỏ .flipped kéo đích về 0° nên 2 đầu bằng nhau -> thẻ đứng im, MẤT
     HẲN hiệu ứng ở CHIỀU LẬT NGƯỢC (chiều xuôi không lộ vì cả 2 mốc đều là none — rất dễ nghiệm
     thu sót). Vì vậy: khoá transition → dựng lại mốc 3D → chốt mốc → mở transition → mới đổi mặt.
     Chốt mốc BẮT BUỘC bằng getComputedStyle().transform, KHÔNG dùng mẹo quen thuộc
     `void el.offsetWidth`: offsetWidth chỉ ép tính lại LAYOUT, mà transform không làm bẩn layout
     nên lần ép đó bị bỏ qua hoàn toàn (đã đo bằng trình duyệt thật, không phải suy đoán). */
  const inner = card.querySelector('.vcard-inner');
  inner.style.transition = 'none';
  card.classList.remove('settled');
  void getComputedStyle(inner).transform;   // chốt mốc: rotateY(180deg) nếu đang lật, none nếu chưa
  inner.style.transition = '';              // trả transition về giá trị trong stylesheet (.55s)
  const flipped = card.classList.toggle('flipped');
  setFaceState(card, flipped);
  scheduleSettle(card);
  if (!flippedSet.has(i)) {
    flippedSet.add(i);
    updateVocabStatus();
    if (flippedSet.size === vocab.length) { markDone('vocab'); unlockPractice(); btnGoPractice.style.display = 'inline-flex'; }
  }
}
vocab.forEach((v, i) => {
  const card = document.createElement('div'); card.className = 'vcard';
  card.setAttribute('role', 'button'); card.tabIndex = 0; card.setAttribute('aria-pressed', 'false');
  card.setAttribute('aria-label', v.word + ' — nhấn để xem nghĩa tiếng Việt');
  card.innerHTML = `<div class="vcard-inner">
    <div class="vface vfront"><div class="num">${String(i+1).padStart(2,'0')}</div>
      <button class="audio-btn" data-word="${esc(v.word)}" aria-label="Nghe phát âm: ${esc(v.word)}">🔊</button>
      <div class="illus-box">${illusHTML(v)}</div>
      <div class="label"><div class="word">${esc(v.word)}</div><div class="ipa">${esc(v.ipa)}</div>
        <div class="hint">Bấm để xem nghĩa →</div></div></div>
    <div class="vface vback"><div class="en">${esc(v.word)}</div><div class="nghia">${esc(v.nghia)}</div>
      <div class="ex">"${esc(v.ex)}"</div>
      <button class="audio-btn" data-word="${esc(v.word)}" aria-label="Nghe phát âm: ${esc(v.word)}">🔊</button></div>
  </div>`;
  card.addEventListener('click', e => { if (!e.target.closest('.audio-btn')) flipCard(card, i); });
  card.addEventListener('keydown', e => {
    if (e.target.closest('.audio-btn')) return;
    if (e.key === 'Enter' || e.key === ' ') { e.preventDefault(); flipCard(card, i); }
  });
  vocabGrid.appendChild(card);
  setFaceState(card, false);
  wireIllusFallback(card, v);
  card.classList.add('settled'); // thẻ vừa dựng đang đứng yên -> vào thẳng trạng thái phẳng
});
updateVocabStatus();

// Điều hướng carousel (mobile): tìm thẻ đang ở giữa khung nhìn, cuộn mượt tới thẻ trước/sau
function currentCardIndex(){
  const gr = vocabGrid.getBoundingClientRect(); const mid = gr.left + gr.width / 2;
  let best = 0, bestD = Infinity;
  Array.from(vocabGrid.children).forEach((c, i) => {
    const r = c.getBoundingClientRect(); const d = Math.abs(r.left + r.width / 2 - mid);
    if (d < bestD) { bestD = d; best = i; }
  });
  return best;
}
function updateVocabNav(){
  const i = currentCardIndex();
  vocabPos.textContent = `${i + 1}/${vocab.length}`;
  vocabPrev.disabled = i === 0;
  vocabNext.disabled = i === vocab.length - 1;
}
function scrollToCard(i){
  const c = vocabGrid.children[i]; if (!c) return;
  const cr = c.getBoundingClientRect(), gr = vocabGrid.getBoundingClientRect();
  vocabGrid.scrollTo({ left: vocabGrid.scrollLeft + (cr.left - gr.left) - (gr.width - cr.width) / 2, behavior:'smooth' });
}
vocabPrev.addEventListener('click', () => scrollToCard(Math.max(0, currentCardIndex() - 1)));
vocabNext.addEventListener('click', () => scrollToCard(Math.min(vocab.length - 1, currentCardIndex() + 1)));
vocabGrid.addEventListener('scroll', () => { clearTimeout(window._vs); window._vs = setTimeout(updateVocabNav, 80); });
updateVocabNav();

vocabGrid.addEventListener('click', e => {
  const btn = e.target.closest('.audio-btn'); if (!btn) return; e.stopPropagation();
  if ('speechSynthesis' in window) {
    const u = new SpeechSynthesisUtterance(btn.dataset.word); u.lang = 'en-GB'; u.rate = 0.9;
    speechSynthesis.cancel(); speechSynthesis.speak(u);
  }
});
```

> **Giới hạn 12 thẻ:** đây là trần tối ưu của layout carousel + lưới `data-count`, không phải giới
> hạn cứng của hệ thống. Nếu kịch bản có nhiều từ vựng hơn 12, tách thành nhiều phần nhỏ (VD 2 tab
> Vocabulary A/B) thay vì nhồi hết vào 1 carousel — carousel dài quá 12 bước khiến học sinh mất
> phương hướng khi vuốt, không biết còn bao xa mới hết.

### 4.5 Level Tabs + Step-gate — chuyển mức độ, chạy tuần tự từng dạng bài

> **Hành vi bắt buộc (khác bản cũ):** trong 1 mức độ, KHÔNG hiện hết mọi dạng bài (T/F, Matching,
> Gap Fill...) cùng lúc trên 1 trang dài. Chỉ hiện **1 dạng bài tại 1 thời điểm**, có nút "Tiếp
> theo →" chỉ bật khi đã làm xong hết bước hiện tại. Bước cuối cùng của mức đổi thành "Hoàn thành
> mức này ✓", bấm vào hiện luôn **2 nút bấm thẳng sang mức Trung bình / Khó** — không bắt học sinh
> phải tự cuộn lên bấm lại tab.

```html
<div class="level-tabs">
  <button class="level-tab active" data-level="easy">🟢 Easy</button>
  <button class="level-tab" data-level="medium">🟡 Medium</button>
  <button class="level-tab" data-level="difficult">🔴 Difficult</button>
</div>
<div id="practiceHost"></div>
```
```css
.level-tabs { display:flex; justify-content:center; gap:10px; margin-bottom:30px; flex-wrap:wrap; }
.level-tab { background:var(--white); border:2px solid var(--cream-2); border-radius:var(--radius);
  padding:12px 22px; font-weight:700; font-size:15px; color:var(--ink-2); min-height:44px; }
.level-tab.active { background:var(--jade-deep); color:#fff; border-color:var(--jade-deep); box-shadow:var(--shadow); }

.step-counter { font-size:12.5px; color:var(--ink-2); font-weight:600; }
.step-nav { display:flex; justify-content:space-between; align-items:center; gap:12px; padding:14px 4px 6px; }
.step-nav .chip-btn { min-height:44px; padding:10px 20px; }
.step-done-card { text-align:center; background:var(--white); border:2px solid var(--jade-soft);
  border-radius:var(--radius-lg); padding:22px; box-shadow:var(--shadow); }
.step-done-card b { color:var(--jade-dark); font-size:16px; }
.step-done-card p { color:var(--ink-2); font-size:13.5px; margin-top:6px; }
.next-level-row { display:flex; gap:10px; justify-content:center; flex-wrap:wrap; margin-top:14px; }
.next-level-btn { background:var(--white); border:2px solid var(--jade-deep); color:var(--jade-dark);
  border-radius:var(--radius); padding:10px 18px; font-weight:700; font-size:13.5px; min-height:44px; }
```
```javascript
const levelLabel = { easy:'Easy', medium:'Medium', difficult:'Difficult' };
const levelOrder = ['easy', 'medium', 'difficult']; // thứ tự để biết mức "tiếp theo" là gì
let currentLevel = 'easy';
let currentSteps = [];
let currentStepIndex = 0;
const completedLevels = new Set();

// Mỗi mức độ = 1 mảng bước tuần tự. Tự xây dựng theo dạng bài THẬT bài đó có (không cố định phải
// là T/F -> Matching -> Gapfill — có thể là QA -> Matching -> Gapfill, Error Correction -> ..., v.v.)
function buildStepsForLevel(level) {
  const d = practiceData[level];
  const steps = [];
  // Đẩy lần lượt từng dạng bài THẬT có trong data của mức này, VD:
  if (d.tf) steps.push({ type:'tf', total:d.tf.length, build:() => buildTF(d.tf) });
  if (d.qa) steps.push({ type:'qa', total:d.qa.length, build:() => buildQA(d.qa) });
  if (d.error) steps.push({ type:'error', total:d.error.length, build:() => buildError(d.error) });
  if (d.matching) steps.push({ type:'matching', total: matchTerms.length, build:() => buildMatching(level) });
  if (d.gapfill) steps.push({ type:'gapfill', total:d.gapfill.length, build:() => buildGapfill(d.gapfill) });
  return steps;
}

function renderLevel(level) {
  currentLevel = level;
  currentSteps = buildStepsForLevel(level);
  currentStepIndex = 0;
  renderStep();
}

function renderStep() {
  const step = currentSteps[currentStepIndex];
  const isLast = currentStepIndex === currentSteps.length - 1;
  practiceHost.innerHTML = step.build() + `
    <div class="step-nav">
      <span class="step-counter">Bước ${currentStepIndex + 1}/${currentSteps.length}</span>
      <button class="chip-btn" id="btnStepNext" disabled>${isLast ? 'Hoàn thành mức này ✓' : 'Tiếp theo →'}</button>
    </div>`;
  wireStep(step);
}

// Kiểm tra bước hiện tại đã làm xong hết chưa — viết thêm nhánh nếu có dạng bài mới ngoài 4 loại này
function isStepComplete(step) {
  if (step.type === 'tf') return practiceHost.querySelectorAll('.tf-opts button.selected').length === step.total;
  if (step.type === 'qa' || step.type === 'error') return practiceHost.querySelectorAll('.answer-box.show').length === step.total;
  if (step.type === 'matching') return practiceHost.querySelectorAll('.match-opt.term.matched').length === step.total;
  if (step.type === 'gapfill') return practiceHost.querySelectorAll('.explain[data-exp-gf].show').length === step.total;
  return false;
}
function refreshNextBtn(step) {
  const btn = document.getElementById('btnStepNext');
  if (btn) btn.disabled = !isStepComplete(step);
}

// wireStep(step): gắn event listener cho TỪNG dạng bài của bước hiện tại (TF/QA/Error/Matching/Gapfill),
// mỗi lần học sinh tương tác thì gọi refreshNextBtn(step) — xem code đầy đủ ở Mục 4.6 (Matching)
// cho phần dễ sai nhất. Cuối wireStep(), gắn listener cho nút "Tiếp theo":
function wireStep(step) {
  // ... gắn listener riêng cho từng dạng bài (TF/QA/Error/Matching/Gapfill) ở đây ...

  document.getElementById('btnStepNext').addEventListener('click', () => {
    if (currentStepIndex < currentSteps.length - 1) {
      currentStepIndex++;
      renderStep();
      practiceHost.scrollIntoView({ behavior:'smooth', block:'start' });
    } else {
      completedLevels.add(currentLevel);
      markDone('practice');
      const nextLevels = levelOrder.filter(l => l !== currentLevel && !completedLevels.has(l));
      practiceHost.insertAdjacentHTML('beforeend', `
        <div class="step-done-card">
          <b>🎉 Bạn đã hoàn thành mức ${levelLabel[currentLevel]}!</b>
          <p>${nextLevels.length ? 'Muốn thử sức thêm không?' : 'Bạn đã hoàn thành cả 3 mức — tuyệt vời!'}</p>
          ${nextLevels.length ? `<div class="next-level-row">
            ${nextLevels.map(l => `<button class="next-level-btn" onclick="goToLevel('${l}')">${levelLabel[l] === 'Medium' ? '🟡' : '🔴'} Sang mức ${levelLabel[l]} →</button>`).join('')}
          </div>` : ''}
        </div>`);
      document.getElementById('btnStepNext').remove();
      document.querySelector('.step-counter').textContent = `Bước ${currentSteps.length}/${currentSteps.length} · Hoàn tất`;
    }
  });
  refreshNextBtn(step);
}

// Bấm nút "Sang mức Medium/Difficult →" ở step-done-card: đổi tab active + dựng lại nội dung mức mới
function goToLevel(level) {
  document.querySelectorAll('.level-tab').forEach(t => t.classList.toggle('active', t.dataset.level === level));
  renderLevel(level);
}

document.querySelectorAll('.level-tab').forEach(tab => {
  tab.addEventListener('click', () => {
    document.querySelectorAll('.level-tab').forEach(t => t.classList.remove('active'));
    tab.classList.add('active');
    renderLevel(tab.dataset.level);
  });
});
// KHÔNG gọi renderLevel('easy') ngay khi tải trang nếu Luyện tập đang bị khoá (xem 4.8) — chỉ
// gọi bên trong unlockPractice() đúng lúc mở khoá. Nếu bài không cần khoá tuần tự (không có Top
// Panel/Vocabulary đứng trước), gọi renderLevel('easy') ngay ở cuối script như bình thường.
```

### 4.6 Các dạng bài luyện tập chuẩn — bắt buộc có `explain` cho mỗi câu

> **Quy tắc cứng:** mỗi phần tử trong data câu hỏi phải có field `explain` (giải thích tiếng Việt
> vì sao đúng/sai), hiển thị SAU khi học sinh trả lời. Không được chỉ hiện "Đúng/Sai" hay điểm số.

> ⚠️ **Chống soạn ẩu (bắt buộc — xem nguyên tắc 7 ở Mục 0):** viết data câu hỏi với đáp án đúng ở
> BẤT KỲ vị trí nào (thường tiện tay để đáp án đúng luôn ở đầu mảng `options[0]`), rồi dùng hàm
> dưới đây để xáo vị trí hiển thị MỖI LẦN RENDER — không tự tay rải đáp án đúng vào các vị trí A/B/
> C/D khác nhau cho "có vẻ ngẫu nhiên", vì làm tay vẫn dễ lệch thống kê qua hàng chục câu.

```javascript
// Dùng chung cho MỌI câu hỏi MCQ trong bài — nhận mảng options (phần tử đầu tiên LUÔN là đáp án
// đúng khi soạn data, cho dễ đọc/dễ sửa), trả về mảng đã xáo + object đáp án đúng (text) để so khớp
function shuffleMCQOptions(options) {
  const correctText = options[0];
  const shuffled = [...options].sort(() => Math.random() - 0.5);
  return { shuffled, correctText };
}
// Soạn data kiểu: { q:"...", options:["đáp án đúng luôn viết trước", "nhiễu 1", "nhiễu 2", "nhiễu 3"], explain:"..." }
// Khi render: const { shuffled, correctText } = shuffleMCQOptions(q.options);
// So khớp đúng/sai bằng cách so TEXT (shuffled[j] === correctText), không so theo index cố định —
// vì index đáp án đúng giờ đổi mỗi lần render, không còn cố định theo data nữa.
```

> ⚠️ **Lỗi thật đã gặp — nút KHÔNG bấm được vì dấu nháy đơn trong đáp án:** KHÔNG BAO GIỜ render nút
> bằng cách nhét text động vào chuỗi thuộc tính `onclick="..."`:
> ```javascript
> // ❌ SAI — sẽ gãy nếu optText chứa dấu nháy đơn (VD "school's", "I'd", "don't")
> `<button onclick="answerMCQ('${qid}', this, '${esc(optText)}')">${esc(optText)}</button>`
> ```
> `esc()` (Nguyên tắc 8, Mục 0) chỉ escape `& < > "`, KHÔNG escape dấu nháy đơn `'` — nếu `optText`
> chứa `'` (rất hay gặp: "school's", "I'd", "don't", "I've"), dấu nháy đó sẽ kết thúc sớm chuỗi JS
> trong thuộc tính `onclick`, làm gãy toàn bộ nút đó (và có thể cả các nút sau trong cùng câu) —
> học sinh bấm không có phản ứng gì, rất khó nhận ra khi test nhanh vì phần lớn câu KHÔNG có dấu
> nháy đơn nên vẫn hoạt động bình thường, chỉ riêng câu có từ như "school's" mới lộ lỗi.
> **Bắt buộc dùng `addEventListener` — không đưa text động vào bất kỳ thuộc tính `onclick=""` nào:**
> ```javascript
> // ✅ ĐÚNG
> wrap.innerHTML = shuffled.map(optText => `<button class="q-opt">${esc(optText)}</button>`).join('');
> Array.from(wrap.children).forEach((btn, i) => {
>   btn.addEventListener('click', () => answerMCQ(qid, btn, shuffled[i]));
> });
> ```
> Quy tắc này áp dụng cho MỌI component tự render nút/phần tử tương tác từ text tự do trong data
> (MCQ 4.6, Matching 4.12, Ordering/Word-Tile 4.13, Tap-to-Categorize 4.17...) — không riêng bài
> Writing đã phát hiện lỗi này. Nếu component đã lỡ dùng `onclick=""` với text nhúng, chuyển toàn bộ
> sang `addEventListener` khi sửa, không chỉ vá thêm escape dấu nháy đơn (dễ sót các ký tự đặc biệt
> khác sau này).

**True/False:**
```javascript
{ q: "...", a: true, explain: "..." }
```
```css
.tf-item { display:flex; justify-content:space-between; align-items:center; gap:14px; padding:14px 0;
  border-bottom:1px solid var(--cream-2); }
.tf-opts button { border:1.5px solid var(--sage); background:transparent; border-radius:var(--radius-sm);
  padding:7px 14px; min-height:40px; font-weight:600; color:var(--ink-2); }
.tf-opts button.selected.correct { background:var(--correct); color:#fff; border-color:var(--correct); }
.tf-opts button.selected.wrong { background:var(--wrong); color:#fff; border-color:var(--wrong); }
.explain { font-size:12.5px; color:var(--ink-2); margin-top:6px; background:var(--cream-2);
  padding:8px 12px; border-radius:var(--radius-sm); display:none; width:100%; }
.explain.show { display:block; }
```

**Matching:**
```javascript
{ terms:[...], defs:[...], correctLetters:[...], explain: "..." /* giải thích chung hoặc theo từng cặp */ }
```
```css
.match-wrap { display:grid; grid-template-columns:1fr 1fr; gap:22px; }
@media (max-width:600px){ .match-wrap{grid-template-columns:1fr;} }
.match-opt { background:var(--cream-2); border:2px solid transparent; border-radius:var(--radius);
  padding:10px 14px; margin-bottom:8px; font-size:15px; min-height:44px; display:flex; align-items:center; }
.match-opt.active { border-color:var(--accent); background:var(--accent-pale); }
.match-opt.matched { background:var(--correct-bg); border-color:var(--correct); color:var(--jade-text); }
.match-opt.shake { animation:shake .35s; }
@keyframes shake{20%,60%{transform:translateX(-5px);}40%,80%{transform:translateX(5px);}}
```

> ⚠️ **Chống soạn ẩu — xáo vị trí hiển thị (xem nguyên tắc 7 ở Mục 0):** cả 2 cột (term bên trái,
> định nghĩa bên phải) đều phải xáo thứ tự hiển thị bằng `.sort(() => Math.random() - 0.5)` MỖI LẦN
> render — không hiện đúng thứ tự soạn trong data (dễ tạo thói quen xấu "nối theo hàng ngang" mà
> không cần đọc nghĩa). Việc xáo vị trí hiển thị này KHÁC với lỗi `correctLetters` map sai ở dưới —
> xáo vị trí không đổi *nghĩa* của cặp đúng/sai, chỉ đổi *chỗ hiện* trên màn hình.

> ⚠️ **Lỗi dữ liệu rất dễ mắc phải — đã gặp thực tế:** mảng `correctLetters` (chữ cái A-H gán cho
> từng term, dùng để đối chiếu với chữ cái của định nghĩa đúng) rất dễ bị NHẦM THỨ TỰ khi soạn tay
> — hậu quả là học sinh nối đúng theo nghĩa (VD "do the cooking" ↔ "to prepare and cook meals")
> nhưng hệ thống báo sai, vì đang so với đáp án của 1 từ KHÁC. **Bắt buộc kiểm tra lại bằng cách in
> bảng đối chiếu term ↔ định nghĩa đã map theo `correctLetters`, đọc bằng mắt xem có khớp nghĩa
> không** — không tin tưởng mù quáng vào code chạy được (code có thể chạy hoàn hảo, không lỗi cú
> pháp, nhưng vẫn map SAI nếu bảng chữ cái bị lệch). Nếu bài có nhiều mức độ dùng chung 1 bộ term
> nhưng định nghĩa diễn đạt khác nhau theo mức (dễ/trung bình/khó), PHẢI giữ đúng cùng 1 thứ tự
> A-H xuyên suốt cả 3 mảng định nghĩa của 3 mức — lệch thứ tự ở bất kỳ mức nào cũng gây lỗi tương tự.

**JS click-để-nối — chú ý đoạn `setTimeout` xử lý khi bấm SAI cặp:**
```javascript
let selectedTerm = null;
practiceHost.querySelectorAll('.match-opt.term').forEach(el => {
  el.addEventListener('click', () => {
    if (el.classList.contains('matched')) return;
    practiceHost.querySelectorAll('.match-opt.term').forEach(t => t.classList.remove('active'));
    el.classList.add('active');
    selectedTerm = el;
  });
});
practiceHost.querySelectorAll('.match-opt.def').forEach(el => {
  el.addEventListener('click', () => {
    if (!selectedTerm || el.classList.contains('matched')) return;
    if (selectedTerm.dataset.letter === el.dataset.letter) {
      selectedTerm.classList.add('matched'); selectedTerm.classList.remove('active');
      el.classList.add('matched');
      selectedTerm = null;
      refreshNextBtn(step); // xem 4.5 — cập nhật trạng thái nút Tiếp theo
    } else {
      const wrongTerm = selectedTerm; // BẮT BUỘC chụp lại tham chiếu TRƯỚC khi reset selectedTerm
      wrongTerm.classList.remove('active'); // bỏ ngay để tránh hiểu nhầm "vẫn đang chọn"
      el.classList.add('shake'); wrongTerm.classList.add('shake');
      selectedTerm = null;
      setTimeout(() => { el.classList.remove('shake'); wrongTerm.classList.remove('shake'); }, 350);
    }
  });
});
```
> ⚠️ **Lỗi runtime dễ mắc:** nếu set `selectedTerm = null` NGAY LẬP TỨC (đồng bộ) rồi mới dùng biến
> đó bên trong `setTimeout` (bất đồng bộ, chạy 350ms sau), lúc callback chạy thì `selectedTerm` đã
> là `null` → `null.classList` crash ngầm, khiến ô vừa bấm bị kẹt ở trạng thái "trông như đang chọn"
> nhưng hệ thống đã quên mất. Luôn chụp biến vào 1 hằng cục bộ (`wrongTerm`) TRƯỚC khi reset, như
> code mẫu trên.

**Gap-fill:**

**🆕 HTML markup bắt buộc — cùng nguyên tắc "1 câu liền mạch" như Find the Error (9.16):** trước
đây mục này chỉ có data + CSS cho ô input, KHÔNG có ví dụ ghép "câu văn + input" thành khối liền
mạch — đúng lỗ hổng đã gây lỗi Find the Error. Chuỗi `sent` chứa `________` PHẢI được tách và render
thành **1 khối `<p>` duy nhất**, input chèn xen giữa 2 nửa câu bằng chính `<input>` (vốn đã là
`display:inline-block` mặc định, chảy tự nhiên trong dòng văn bản) — KHÔNG bọc riêng nửa câu trước/
sau input thành các `<span>`/`<div>` có border/background riêng, KHÔNG tách câu thành nhiều dòng
cố định:

```html
<div class="fill-item">
  <p class="fill-sentence">
    <span class="fill-num">1.</span> Recycling bins
    <input type="text" class="fill-blank" data-idx="0" placeholder="______">
    around the school last month.
  </p>
  <button class="check-btn">Kiểm tra</button>
</div>
```
```javascript
// altAnswers: tuỳ chọn — các cách viết đúng khác ngoài viết tắt/đầy đủ (xem nguyên tắc 10, Mục 0).
// strictNoContraction: true — chỉ set khi CHỦ ĐỘNG không muốn chấp nhận viết tắt cho câu này.
{ sent: "... ________ ...", ans: "...", altAnswers: [], explain: "..." }
```
```css
.fill-sentence { display:inline; font-size:17px; line-height:1.9; color:var(--ink); }
.fill-item input[type=text] { border:2px solid var(--cream-2); border-radius:var(--radius-sm);
  padding:8px 12px; font-size:15px; width:220px; max-width:60%; min-height:40px; }
.fill-item input[type=text].correct { border-color:var(--correct); background:var(--correct-bg); }
.fill-item input[type=text].wrong { border-color:var(--wrong); background:var(--wrong-bg); }
.check-btn { background:var(--jade-deep); color:#fff; border:none; border-radius:var(--radius-sm);
  padding:8px 16px; min-height:40px; font-weight:600; margin-left:8px; }
```
> ⚠️ Áp dụng ĐÚNG nguyên tắc này cho cả **Sentence Completion** (chỗ trống nằm giữa câu, không có
> word box) — cùng 1 lỗi tiềm ẩn, cùng 1 cách sửa: 1 khối `<p>` liền mạch, input chảy tự nhiên trong
> dòng văn bản.

> ⚠️ **Hàm chấm đáp án dùng CHUNG cho mọi ô nhập chữ trong toàn hệ thống** (Gap-fill, Q&A mở, Error
> Correction, và bất kỳ `input[type=text]`/`textarea` nào cần tự chấm đúng-sai) — định nghĩa 1 lần
> ở đầu `<script>` của file Practice, không viết lại logic so sánh riêng cho từng dạng bài:

```javascript
// ⚠️ ĐÃ SỬA LỖI THẬT PHÁT HIỆN KHI TEST: bảng cặp cứng theo chủ ngữ (kiểu "i will"<->"i'll",
// "[chủ ngữ B] will"<->"[chủ ngữ B]'ll"...) có 2 lỗi nặng:
//   1. Không cover hết chủ ngữ (that'll/who'll/there'll/what'll... bị bỏ sót).
//   2. QUAN TRỌNG NHẤT: khi câu đề chỉ để trống ĐỘNG TỪ, chủ ngữ nằm NGOÀI chỗ trống (VD sentence
//      "[Chủ ngữ] ______ ([động từ])..." với ans chỉ là "will [động từ]"), học sinh viết tắt tự nhiên PHẢI dính
//      chủ ngữ vào 'll ("[Chủ ngữ]'ll [động từ]") vì đó là quy tắc ngữ pháp — nhưng ans lại không có chủ ngữ để
//      so khớp, khiến học sinh viết ĐÚNG vẫn bị chấm sai. Đây chính là lỗi "[chủ ngữ]'ll không được chấm đúng"
//      đã gặp thực tế. Thuật toán dưới đây dùng regex tổng quát (không liệt kê từng chủ ngữ) +
//      xử lý riêng case chủ ngữ nằm ngoài chỗ trống, đã test qua 20 tình huống thật (đúng, sai,
//      is/has và would/had mơ hồ, dấu nháy cong điện thoại, chủ ngữ lệch nhau phải báo SAI).
function normalizeText(s) {
  // Chuẩn hoá dấu nháy cong (’ ‘ ʼ) mà bàn phím điện thoại tự đổi khi gõ contraction — KHÔNG bỏ
  // dòng replace này dù trông dư thừa, vì gõ thử trên máy tính sẽ không bao giờ lộ ra lỗi này.
  return String(s).trim().toLowerCase()
    .replace(/[\u2018\u2019\u02BC`]/g, "'")
    .replace(/\s+/g, ' ').replace(/[.,!?;:]+$/, '');
}

// Mở rộng viết tắt bằng REGEX tổng quát — khớp với BẤT KỲ từ đứng trước ('ll/'re/'ve/'m/'s/'d/n't),
// không cần liệt kê cứng từng chủ ngữ như bảng cũ.
function expandGeneric(text) {
  const variants = new Set([text]);
  const add = fn => { [...variants].forEach(v => { const r = fn(v); if (r !== v) variants.add(r); }); };
  // won't/can't/shan't/ain't biến dạng gốc từ, phải xử lý riêng TRƯỚC quy tắc n't chung
  add(v => v.replace(/\bwon't\b/g, 'will not'));
  add(v => v.replace(/\bcan't\b/g, 'cannot').replace(/\bcan't\b/g, 'can not'));
  add(v => v.replace(/\bshan't\b/g, 'shall not'));
  add(v => v.replace(/\bain't\b/g, 'is not'));
  add(v => v.replace(/\blet's\b/g, 'let us'));            // đặc biệt: 's ở đây KHÔNG phải is/has
  add(v => v.replace(/(\w)n't\b/g, '$1 not'));            // isn't/doesn't/haven't/wouldn't/mustn't...
  // 'll/'re/'ve/'m — không mơ hồ, cover MỌI từ đứng trước (that'll, who'll, there'll, my dog's...)
  add(v => v.replace(/\b(\w+)'ll\b/g, '$1 will'));
  add(v => v.replace(/\b(\w+)'re\b/g, '$1 are'));
  add(v => v.replace(/\b(\w+)'ve\b/g, '$1 have'));
  add(v => v.replace(/\bi'm\b/g, 'i am'));
  // 's/'d — MƠ HỒ (is/has, would/had) -> sinh cả 2 khả năng, chấp nhận khả năng nào khớp
  add(v => v.replace(/\b(\w+)'s\b/g, '$1 is'));
  add(v => v.replace(/\b(\w+)'s\b/g, '$1 has'));
  add(v => v.replace(/\b(\w+)'d\b/g, '$1 would'));
  add(v => v.replace(/\b(\w+)'d\b/g, '$1 had'));
  return variants;
}

const SUBJECT_WORDS = new Set(['i','you','he','she','it','we','they','that','who','there','what','here']);
// Bỏ chủ ngữ đứng đầu — CHỈ áp dụng phía input học sinh (xem giải thích ở checkTextAnswer), để so
// khớp được với ans dạng "will [động từ]" (không có chủ ngữ) khi học sinh viết tắt "[chủ ngữ]'ll [động từ]".
function stripLeadingSubject(text) {
  const parts = text.split(' ');
  return (parts.length > 1 && SUBJECT_WORDS.has(parts[0])) ? parts.slice(1).join(' ') : null;
}

// ans/altAnswers: CHỈ mở rộng viết tắt<->đầy đủ, KHÔNG tự bỏ chủ ngữ — nếu giáo viên ghi rõ chủ
// ngữ trong ans (VD "[Chủ ngữ A] will"), phải giữ đúng chủ ngữ đó, không được lẫn với chủ ngữ khác ("[Chủ ngữ B]'ll").
function buildAcceptedSet(rawAnswer) {
  return expandGeneric(normalizeText(rawAnswer));
}
// input học sinh: mở rộng viết tắt<->đầy đủ, RỒI MỚI thêm biến thể bỏ chủ ngữ đứng đầu — chỉ áp
// dụng phía học sinh, để so khớp được khi ans không có chủ ngữ (blank chỉ để trống động từ).
function buildUserVariantSet(rawInput) {
  const expanded = expandGeneric(normalizeText(rawInput));
  const all = new Set(expanded);
  [...expanded].forEach(v => { const s = stripLeadingSubject(v); if (s) all.add(s); });
  return all;
}

// Hàm chấm chính — dùng cho MỌI ô nhập chữ cần tự chấm đúng/sai trong toàn hệ thống.
// q: object câu hỏi có { ans, altAnswers?, strictNoContraction? }
function checkTextAnswer(userInput, q) {
  if (q.strictNoContraction) {
    return normalizeText(userInput) === normalizeText(q.ans)
      || (q.altAnswers || []).some(a => normalizeText(userInput) === normalizeText(a));
  }
  const acceptedRaw = [q.ans, ...(q.altAnswers || [])];
  const accepted = new Set();
  acceptedRaw.forEach(a => buildAcceptedSet(a).forEach(v => accepted.add(v)));
  const userVariants = buildUserVariantSet(userInput);
  return [...userVariants].some(v => accepted.has(v));
}
```

```javascript
// Gắn vào nút "Kiểm tra" của từng Gap-fill item:
document.querySelectorAll('.fill-item').forEach((item, i) => {
  item.querySelector('.check-btn').addEventListener('click', () => {
    const input = item.querySelector('input[type=text]');
    const q = fillQuestions[i]; // mảng data tương ứng
    const isCorrect = checkTextAnswer(input.value, q);
    input.classList.remove('correct', 'wrong');
    input.classList.add(isCorrect ? 'correct' : 'wrong');
    const explainEl = item.querySelector('.explain');
    explainEl.textContent = q.explain;
    explainEl.classList.add('show');
    if (isCorrect) markDone('fill'); // hoặc key tương ứng dạng bài đang dùng
  });
});
```

**Q&A mở (tự luận, học sinh gõ câu trả lời rồi tự đối chiếu gợi ý):**
```javascript
// altAnswers/strictNoContraction: xem giải thích ở Gap-fill ngay trên — dùng chung checkTextAnswer().
{ q: "...", ans: "...", altAnswers: [], explain: "..." }
```
```css
.reveal-btn { background:transparent; color:var(--accent-text); border:1.5px dashed var(--accent);
  border-radius:var(--radius-sm); padding:6px 12px; min-height:40px; font-weight:600; margin-left:8px; }
.answer-box { margin-top:8px; font-size:13px; background:var(--cream-2); border-radius:var(--radius-sm);
  padding:10px 14px; display:none; }
.answer-box.show { display:block; }
```
> Dạng "tự luận mở" (gõ rồi tự đối chiếu) không cần chấm đúng/sai tự động — chỉ hiện gợi ý khi bấm
> `.reveal-btn`, học sinh tự so. Nếu dạng bài đổi sang chấm tự động (có nút "Kiểm tra" thật) thì bắt
> buộc dùng `checkTextAnswer()` giống Gap-fill, không tự viết so sánh `=== ans` riêng.

**Error Correction (mức Khó):**
```javascript
{ wrong: "\"...\"", ans: "...", altAnswers: [], explain: "..." }
```
Dùng lại đúng `.answer-box` / `.reveal-btn` ở trên — chỉ khác nội dung câu sai cần sửa. Nếu dạng bài
có ô nhập để học sinh gõ câu đã sửa và chấm tự động, dùng `checkTextAnswer()` như Gap-fill (câu dài
hơn nên cân nhắc thêm `altAnswers` cho các cách sửa đúng khác nhau, vì lỗi ngữ pháp có thể sửa theo
nhiều cách đều đúng).

### 4.7 Self-assessment + Finale

```html
<div class="assess-list" id="assessList"></div>
<div class="finale" id="finale">
  <h3>🎉 Tuyệt vời!</h3>
  <p>Bạn đã hoàn thành [tên phần]. Hẹn gặp lại ở phần tiếp theo nhé!</p>
</div>
```
```css
.assess-item { display:flex; align-items:flex-start; gap:14px; background:var(--white);
  border:2px solid var(--cream-2); border-radius:var(--radius); padding:16px 18px; margin-bottom:12px;
  cursor:pointer; min-height:44px; }
.assess-item.checked { border-color:var(--jade-deep); background:var(--jade-pale); }
.assess-box { width:24px; height:24px; border-radius:8px; border:2px solid var(--sage); flex:0 0 auto; }
.assess-item.checked .assess-box { background:var(--jade-deep); border-color:var(--jade-deep); }
.finale { text-align:center; margin-top:26px; padding:24px; background:var(--jade-deep);
  border-radius:var(--radius-lg); color:#fff; display:none; }
.finale.show { display:block; }
```
```javascript
// Khi tick đủ toàn bộ assess-item: markDone('assess'); document.getElementById('finale').classList.add('show');
// Đây cũng là điểm gọi LMS().complete({...}) — xem PHẦN 7 file Toán, results.items lấy từ toàn bộ
// câu hỏi đã làm ở Mục 4.6 (cả 3 mức nếu học sinh làm nhiều mức).
```

### 4.8 Top Panel — gộp Phone Chat + Vocabulary, có tab, nút Gom, khoá tuần tự

Dùng khi bài có ĐỦ cả Hội thoại (4.3) và Từ vựng (4.4) đứng trước Luyện tập (4.5). Đây là
Collapsible Panel (kỹ thuật gốc y hệt Mục 3.7 file `02_design_toan_final_v2.md`) nhưng có thêm
2 tính năng riêng cho Tiếng Anh: **tab chuyển đổi nội dung bên trong** (Tin nhắn ↔ Từ vựng) và
**khoá tuần tự** (đọc xong tin nhắn mới mở Từ vựng; học xong Từ vựng mới mở Luyện tập).

> **Vì sao cần khoá tuần tự:** học sinh bình thường sẽ không tự giác đọc hết tin nhắn/học hết từ
> vựng nếu có thể bấm thẳng qua phần Luyện tập. Khoá + nút "Sang phần tiếp theo" rõ ràng ép đúng
> trình tự học (đọc hội thoại → học từ vựng → luyện tập), đồng thời cho Athena biết chắc học sinh
> đã tiếp xúc đủ nội dung trước khi làm bài.

```html
<section class="block" id="sec-top">
  <div class="collapsible-panel" id="topPanel">
    <div class="cp-toggle-row">
      <div class="top-tabs">
        <button class="top-tab active" data-view="messages" onclick="switchTopView('messages')">💬 Messages</button>
        <button class="top-tab locked" id="vocabTabBtn" data-view="vocab" onclick="switchTopView('vocab')">🔒 Vocabulary</button>
      </div>
      <button class="cp-toggle" id="cpToggleBtn" onclick="toggleTopPanel()" aria-expanded="true">
        Gom lại <i class="cp-chevron">▲</i>
      </button>
    </div>
    <div class="cp-body" id="topPanelBody">
      <div id="messagesView" class="top-view active">
        <!-- Component 4.3 Phone Chat ở đây -->
        <button class="chip-btn unlock-btn" id="btnGoVocab" onclick="goToVocab()">✓ Đã đọc xong — Sang Từ vựng →</button>
      </div>
      <div id="vocabView" class="top-view">
        <!-- Component 4.4 Vocabulary ở đây -->
        <!-- ⚠️ btnGoPractice/goToPractice() CHỈ dùng khi người dùng CHỦ ĐỘNG yêu cầu gộp lại 1 file
             (xem Mục 8, ngoại lệ). Với mặc định TÁCH 2 file (Lesson/Practice riêng), KHÔNG có
             section#sec-practice trong cùng file này để nhảy tới — bỏ hẳn nút này, Vocabulary
             view kết thúc tự nhiên, không có CTA nào (đúng Quy tắc mới 3 ở 01_scenario_builder). -->
        <button class="chip-btn unlock-btn" id="btnGoPractice" onclick="goToPractice()">✓ Đã học xong — Sang Luyện tập →</button>
      </div>
    </div>
  </div>
</section>

<section class="block" id="sec-practice">
  <div class="lock-overlay" id="practiceLock">
    <div class="lock-icon">🔒</div>
    <b>Luyện tập đang bị khoá</b>
    Hoàn thành đọc tin nhắn và học hết từ vựng ở phần trên để mở khoá phần này nhé.
  </div>
  <div id="practiceInner" style="display:none;">
    <!-- Component 4.5 Level Tabs + practiceHost ở đây -->
  </div>
</section>
```
```css
.collapsible-panel { margin-top:8px; }
.cp-toggle-row { display:flex; justify-content:space-between; align-items:center; gap:10px; flex-wrap:wrap; margin-bottom:18px; }
.top-tabs { display:flex; gap:8px; flex-wrap:wrap; }
.top-tab { min-height:44px; padding:8px 18px; border-radius:999px; border:2px solid var(--cream-2);
  background:var(--white); font-weight:700; font-size:13.5px; color:var(--ink-2); }
.top-tab.active { background:var(--jade-deep); color:#fff; border-color:var(--jade-deep); box-shadow:var(--shadow); }
.top-tab.locked { opacity:.5; cursor:not-allowed; }
.cp-toggle { min-height:44px; display:inline-flex; align-items:center; gap:6px; background:var(--white);
  color:var(--jade-dark); border:1.5px solid var(--sage); border-radius:var(--radius); padding:8px 16px;
  font-weight:600; font-size:13.5px; }
.cp-chevron { display:inline-block; transition:transform .25s ease; }
.collapsible-panel.collapsed .cp-chevron { transform:rotate(180deg); }
/* Không giới hạn max-height mặc định cho cp-body — chỉ .vocab-grid bên trong mới cần cuộn (xem 4.4) */
.cp-body { overflow:visible; transition:max-height .35s ease, opacity .25s ease, margin-top .35s ease; }
.collapsible-panel.collapsed .cp-body { max-height:0; opacity:0; margin-top:0; overflow:hidden; }
.top-view { display:none; }
.top-view.active { display:block; animation:fadein .3s; }
.unlock-btn { display:none; margin:16px auto 0; background:var(--jade-deep); align-items:center; justify-content:center; gap:8px; }
.lock-overlay { text-align:center; background:var(--white); border:2px dashed var(--sage);
  border-radius:var(--radius-lg); padding:34px 20px; color:var(--ink-2); }
.lock-overlay .lock-icon { font-size:26px; margin-bottom:8px; }
.lock-overlay b { display:block; color:var(--jade-dark); font-size:16px; margin-bottom:4px; }
```
```javascript
const topPanel = document.getElementById('topPanel');
const cpToggleBtn = document.getElementById('cpToggleBtn');
const vocabTabBtn = document.getElementById('vocabTabBtn');
const btnGoVocab = document.getElementById('btnGoVocab');
const btnGoPractice = document.getElementById('btnGoPractice');
const practiceLock = document.getElementById('practiceLock');
const practiceInner = document.getElementById('practiceInner');
let vocabUnlocked = false;

function switchTopView(view) {
  if (view === 'vocab' && !vocabUnlocked) return; // chặn khi chưa đọc xong tin nhắn
  document.querySelectorAll('.top-view').forEach(v => v.classList.remove('active'));
  document.getElementById(view + 'View').classList.add('active');
  document.querySelectorAll('.top-tab').forEach(t => t.classList.toggle('active', t.dataset.view === view));
  if (topPanel.classList.contains('collapsed')) toggleTopPanel(); // đang gom mà đổi tab -> tự mở lại
}
function toggleTopPanel() {
  const collapsed = topPanel.classList.toggle('collapsed');
  cpToggleBtn.setAttribute('aria-expanded', String(!collapsed));
  cpToggleBtn.innerHTML = collapsed ? 'Mở lại <i class="cp-chevron">▲</i>' : 'Gom lại <i class="cp-chevron">▲</i>';
}
function unlockVocabTab() {
  vocabUnlocked = true;
  vocabTabBtn.classList.remove('locked');
  vocabTabBtn.textContent = '🧠 Vocabulary';
  btnGoVocab.style.display = 'inline-flex';
}
function goToVocab() { switchTopView('vocab'); }

function unlockPractice() {
  practiceLock.style.display = 'none';
  practiceInner.style.display = 'block';
  renderLevel('easy'); // dựng nội dung Luyện tập (xem 4.5) đúng lúc vừa mở khoá, không dựng sớm hơn
}
function goToPractice() {
  switchTopView('messages'); // quay lại Tin nhắn — Vocab (thường rất dài) không cần hiện mặc định nữa
  if (!topPanel.classList.contains('collapsed')) toggleTopPanel(); // gom lại luôn -> bài tập lọt màn hình ngay, khỏi cuộn thêm
  document.getElementById('sec-top').scrollIntoView({ behavior:'smooth', block:'start' });
}
```

> `unlockVocabTab()` gọi từ trong JS của 4.3 (đúng lúc đọc xong tin nhắn), `unlockPractice()` gọi
> từ trong JS của 4.4 (đúng lúc lật hết thẻ từ vựng) — xem đoạn code đã tích hợp sẵn ở 2 mục đó.
> Nếu bài KHÔNG có Vocabulary (chỉ có Hội thoại + Luyện tập), bỏ hẳn phần tab/khoá Vocab, giữ lại
> Collapsible Panel đơn giản như bản gốc file Toán cho riêng phần Hội thoại.

---

### 4.8b Practice Reference Pane — dual-pane, tái dùng bài học song song với Luyện tập

> **Khi nào dùng (v1.2 — BẮT BUỘC, không còn tuỳ chọn):** vì Mục 8 giờ mặc định LUÔN tách file
> Lesson/Practice, File Practice không còn Khối 1 phía trên để cuộn lên xem lại — nên bất kỳ module
> nào có Khối 1 (Hội thoại/Bài đăng/Từ vựng ở 4.8, hoặc Reading Passage ở 4.10) đều BẮT BUỘC có
> Reference Pane này ở File Practice, để học sinh không phải mở lại File Lesson giữa chừng làm bài.
> Chỉ bỏ component này khi Luyện tập hoàn toàn độc lập với nội dung phía trên — 2 ví dụ thật đã gặp:
> **Grammar** (mỗi câu tự đứng độc lập, không tra lại 1 đoạn hội thoại/bài đọc cụ thể nào — xem
> thêm ngoại lệ "không có Khối 1" ở Mục 8) và **Pronunciation** (mỗi mức Practice giới thiệu bộ từ
> luyện nghe/nói mới, không lặp lại đúng bộ từ minh hoạ ở Khối 1). Khi rơi vào trường hợp này, giữ
> nguyên `#practiceInner` với Level Tabs (4.5) + `practiceHost` như bản gốc, không thêm Reference
> Pane.
>
> **Bố cục:** desktop chia đôi màn hình theo **chiều dọc** — 2 cột trái/phải, cột trái là Reference
> Pane (sticky, cuộn riêng), cột phải là câu hỏi. Mobile chia đôi theo **chiều ngang** — Reference
> Pane sticky ở trên, câu hỏi cuộn ở dưới, kèm thanh nút chuyển chế độ xem (Chia đôi / chỉ Bài đọc /
> chỉ Câu hỏi) để gom-ẩn bớt 1 bên khi màn hình quá hẹp cho cả 2.

```html
<div id="practiceInner" style="display:none;">
  <!-- Thanh chuyển chế độ xem — chỉ hiện trên mobile (≤991px) -->
  <div class="mobile-pane-controls">
    <span class="mpc-title">Chế độ xem:</span>
    <button class="mpc-btn active" data-mode="split" onclick="setMobileViewMode('split')">⚖️ Chia đôi</button>
    <button class="mpc-btn" data-mode="ref" onclick="setMobileViewMode('ref')">🔍 Bài đọc</button>
    <button class="mpc-btn" data-mode="q" onclick="setMobileViewMode('q')">📝 Câu hỏi</button>
  </div>

  <div class="practice-split-container" id="practiceSplit">
    <!-- Cột/khối trái-trên: Reference Pane — đọc lại nội dung bài học, KHÔNG lặp tương tác gốc
         (không lật thẻ, không phát âm lại) — chỉ hiển thị read-only -->
    <div class="practice-ref-pane" id="practiceRefPane">
      <div class="pref-head">
        <div class="pref-tabs">
          <button class="pref-tab active" data-pref="messages" onclick="switchRefTab('messages')">💬 Messages</button>
          <button class="pref-tab" data-pref="vocab" onclick="switchRefTab('vocab')">🧠 Vocabulary</button>
        </div>
      </div>
      <div class="pref-body">
        <div id="refMessagesView" class="pref-view active"><div id="refChatBox"></div></div>
        <div id="refVocabView" class="pref-view"><div id="refVocabList"></div></div>
      </div>
    </div>

    <!-- Cột/khối phải-dưới: câu hỏi — Level Tabs (4.5) + practiceHost như bản gốc -->
    <div class="practice-questions-pane" id="practiceQuestionsPane">
      <div class="level-tabs">
        <button class="level-tab active" data-level="easy">🟢 Easy</button>
        <button class="level-tab" data-level="medium">🟡 Medium</button>
        <button class="level-tab" data-level="difficult">🔴 Difficult</button>
      </div>
      <div id="practiceHost"></div>
      <!-- Q-Nav Bar: theo dõi câu đã làm trong bước hiện tại, tương tự bảng câu hỏi IELTS online -->
      <div class="q-nav-bar" id="qNavBar">
        <div class="q-nav-label">Questions:</div>
        <div class="q-nav-items" id="qNavItems"></div>
      </div>
    </div>
  </div>
</div>
```
```css
.mobile-pane-controls { display:none; margin-bottom:14px; align-items:center; gap:6px; flex-wrap:nowrap;
  background:var(--cream-2); padding:6px 10px; border-radius:var(--radius); width:100%;
  overflow-x:auto; scrollbar-width:none; }
.mobile-pane-controls::-webkit-scrollbar { display:none; }
.mpc-title { font-size:11.5px; font-weight:700; color:var(--jade-dark); flex:0 0 auto; white-space:nowrap; margin-right:2px; }
.mpc-btn { background:var(--white); border:1.5px solid var(--sage); border-radius:999px; padding:6px 10px;
  font-size:11.5px; font-weight:600; color:var(--ink-2); min-height:34px; flex:1 1 0; white-space:nowrap; text-align:center; }
.mpc-btn.active { background:var(--jade-deep); color:#fff; border-color:var(--jade-deep); }

.practice-split-container { display:flex; flex-direction:column; gap:16px; } /* mặc định mobile: xếp chồng = chia ngang */

.practice-ref-pane { background:var(--white); border:2px solid var(--cream-2); border-radius:var(--radius-lg);
  padding:14px; box-shadow:var(--shadow); display:flex; flex-direction:column; gap:10px; }
.pref-head { display:flex; align-items:center; border-bottom:1.5px solid var(--cream-2); padding-bottom:8px; }
.pref-tabs { display:flex; gap:8px; width:100%; }
.pref-tab { background:var(--cream-2); border:1.5px solid transparent; border-radius:999px; padding:6px 14px;
  font-size:13px; font-weight:700; color:var(--ink-2); min-height:36px; flex:1; text-align:center; white-space:nowrap; }
.pref-tab.active { background:var(--jade-deep); color:#fff; border-color:var(--jade-deep); }
.pref-body { flex:1; overflow-y:auto; max-height:480px; }
.pref-view { display:none; }
.pref-view.active { display:block; animation:fadein .25s; }

/* Nội dung read-only bên trong Reference Pane — bản rút gọn của Phone Chat/Vocabulary, không có
   nút bấm tương tác gốc (không nút "Tin tiếp theo", không lật thẻ) */
.ref-chat-list { display:flex; flex-direction:column; gap:10px; background:var(--cream-2); padding:12px; border-radius:var(--radius); }
.ref-msg-item { display:flex; gap:8px; align-items:flex-start; background:var(--white); border-radius:12px;
  padding:8px 10px; border:1px solid var(--paper-line); }
.ref-msg-item.right { background:var(--jade-pale); border-color:var(--sage); }
.ref-msg-avatar { width:30px; height:30px; border-radius:50%; flex:0 0 auto; margin-top:2px; }
.ref-msg-content { flex:1; font-size:13px; line-height:1.45; color:var(--ink); }
.ref-msg-author { font-size:10.5px; font-weight:700; color:var(--jade-dark); margin-bottom:2px; }
.ref-vocab-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(180px,1fr)); gap:10px; }
.ref-vocab-card { background:var(--cream-2); border:1.5px solid var(--paper-line); border-radius:var(--radius-sm); padding:10px 12px; }
.ref-vocab-card .w { font-weight:800; font-size:13.5px; color:var(--jade-dark); }
.ref-vocab-card .m { font-size:12px; color:var(--jade-text); font-weight:600; margin-top:2px; }
.ref-vocab-card .e { font-size:12px; color:var(--ink-2); font-style:italic; margin-top:4px; line-height:1.4; }

.q-nav-bar { background:var(--white); border:2px solid var(--cream-2); border-radius:var(--radius);
  padding:10px 14px; margin-top:18px; display:flex; align-items:center; gap:10px; flex-wrap:wrap;
  box-shadow:0 4px 12px rgba(0,0,0,0.04); }
.q-nav-label { font-size:12px; font-weight:800; color:var(--jade-dark); text-transform:uppercase; letter-spacing:.03em; }
.q-nav-items { display:flex; gap:6px; flex-wrap:wrap; align-items:center; }
.q-nav-btn { width:34px; height:34px; border-radius:8px; border:1.5px solid var(--sage); background:var(--cream-2);
  font-size:12px; font-weight:700; color:var(--ink-2); display:flex; align-items:center; justify-content:center; }
.q-nav-btn.active { background:var(--jade-deep); color:#fff; border-color:var(--jade-deep); transform:scale(1.06); }
.q-nav-btn.done { background:var(--correct-bg); border-color:var(--correct); color:var(--jade-text); }
.q-nav-btn.done::after { content:'✓'; font-size:9px; margin-left:2px; font-weight:900; }

/* ===== Desktop (≥992px): chia đôi theo CHIỀU DỌC — 2 cột trái/phải ===== */
@media (min-width: 992px) {
  .practice-split-container { display:grid; grid-template-columns:minmax(320px,1fr) minmax(420px,1.25fr);
    gap:20px; align-items:start; }
  .practice-ref-pane { position:sticky; top:70px; max-height:calc(100vh - 90px); }
  .practice-questions-pane { min-width:0; }
}

/* ===== Mobile (≤991px): chia đôi theo CHIỀU NGANG — 2 khối trên/dưới, có nút gom-ẩn ===== */
@media (max-width: 991px) {
  .mobile-pane-controls { display:flex; position:sticky; top:42px; z-index:85; box-shadow:0 4px 10px rgba(0,0,0,0.05); }
  .practice-ref-pane { position:sticky; top:84px; z-index:80; max-height:38vh;
    box-shadow:0 8px 24px rgba(42,129,103,0.15); border-bottom:3px solid var(--jade-deep); }
  .pref-body { max-height:calc(38vh - 55px); overflow-y:auto; }
  /* 3 chế độ do nút mpc-btn điều khiển: split = mặc định 38vh/62vh, ref = phóng to Bài đọc,
     q = thu nhỏ Bài đọc còn 1 dải mỏng để nhường chỗ cho Câu hỏi */
  .practice-split-container.mode-split .practice-ref-pane { max-height:38vh; }
  .practice-split-container.mode-split .pref-body { max-height:calc(38vh - 55px); }
  .practice-split-container.mode-ref .practice-ref-pane { max-height:60vh; }
  .practice-split-container.mode-ref .pref-body { max-height:calc(60vh - 55px); }
  .practice-split-container.mode-q .practice-ref-pane { max-height:18vh; }
  .practice-split-container.mode-q .pref-body { max-height:calc(18vh - 55px); }
  .q-nav-bar { position:sticky; bottom:0; z-index:90; border-radius:var(--radius) var(--radius) 0 0;
    margin-top:14px; border-bottom:none; background:var(--white); box-shadow:0 -4px 16px rgba(0,0,0,0.1); }
}
```
```javascript
// Dựng nội dung read-only cho Reference Pane từ CHÍNH data đã dùng ở Khối 1 (messages/vocab) —
// không tạo data riêng, tránh lệch nội dung giữa bài học và phần tham chiếu lúc luyện tập.
function populatePracticeRef() {
  const refChatBox = document.getElementById('refChatBox');
  const refVocabList = document.getElementById('refVocabList');
  if (!refChatBox || refChatBox.children.length > 0) return; // chỉ dựng 1 lần

  let chatHtml = '<div class="ref-chat-list">';
  messages.forEach(m => {
    const sp = speaker[m.who]; const isLeft = m.who === 'a';
    // Dùng lại đúng map `speaker` + avatarHTML() của 4.3, chỉ truyền class khác (.ref-msg-avatar)
    // — không chép lại SVG avatar ra đây, tránh 2 bản hình lệch nhau khi đổi nhân vật.
    chatHtml += `<div class="ref-msg-item ${isLeft ? 'left' : 'right'}">${avatarHTML(m.who, 'ref-msg-avatar')}
      <div class="ref-msg-content"><div class="ref-msg-author">${esc(sp.name)} · ${esc(m.time)}</div><div>${m.text}</div></div></div>`;
  });
  chatHtml += '</div>';
  refChatBox.innerHTML = chatHtml;

  let vocabHtml = '<div class="ref-vocab-grid">';
  vocab.forEach(v => {
    vocabHtml += `<div class="ref-vocab-card"><div class="w">${esc(v.word)}</div>
      <div class="m">${esc(v.nghia)}</div><div class="e">"${esc(v.ex)}"</div></div>`;
  });
  vocabHtml += '</div>';
  refVocabList.innerHTML = vocabHtml;
}

function switchRefTab(tab) {
  document.querySelectorAll('.pref-view').forEach(v => v.classList.remove('active'));
  document.getElementById(tab === 'messages' ? 'refMessagesView' : 'refVocabView').classList.add('active');
  document.querySelectorAll('.pref-tab').forEach(t => t.classList.toggle('active', t.dataset.pref === tab));
}

function setMobileViewMode(mode) {
  const container = document.getElementById('practiceSplit'); if (!container) return;
  container.classList.remove('mode-split', 'mode-ref', 'mode-q');
  container.classList.add('mode-' + mode);
  document.querySelectorAll('.mpc-btn').forEach(b => b.classList.toggle('active', b.dataset.mode === mode));
}

// Gọi populatePracticeRef() bên trong unlockPractice() (xem 4.8), TRƯỚC renderLevel('easy') —
// Reference Pane phải có sẵn nội dung ngay khi Luyện tập vừa mở khoá.
```

> **Reading Passage thay cho Chat/Vocab:** nếu Khối 1 là Reading Passage (4.10) thay vì Hội thoại +
> Từ vựng, Reference Pane chỉ cần 1 pane duy nhất (bỏ hẳn `.pref-tabs`), nội dung là bản sao đoạn
> văn ở 4.10 (giữ nguyên từ khoá gạch chân, bỏ tương tác tap-hiện-nghĩa vì đây là bản tham chiếu
> read-only).
>
> **Q-Nav Bar (thanh câu hỏi):** tuỳ chọn, hữu ích khi 1 bước có từ 4 câu trở lên để học sinh nhảy
> nhanh tới câu chưa làm — dựng lại mỗi khi `renderStep()` (4.5) chạy, đánh dấu `.done` cho câu đã
> trả lời. Nếu bước chỉ có 1-2 câu, có thể bỏ hẳn `#qNavBar` cho gọn.

---

### 4.9 Progressive Unlock Section — mở khoá dần từng phần

Dùng cho Reading (warm-up → bài đọc → câu hỏi), Speaking (từng bước luyện tập), hoặc bất kỳ module
nào cần học sinh hoàn thành phần trước mới thấy phần sau. **Tap-based, không phụ thuộc kéo-thả.**

```html
<div class="unlock-notice" id="secB-lock">
  <i class="ti ti-lock"></i><span>Hoàn thành phần trên để mở khoá</span>
</div>
<div class="unlock-body" id="secB-body"><!-- nội dung phần B, ẩn tới khi mở khoá --></div>
```
```css
.unlock-notice { display:flex; align-items:center; gap:8px; padding:0.65rem 1rem;
  background:var(--cream-2); border-radius:var(--radius); font-size:13px; color:var(--ink-2); }
.unlock-body.locked { display:none; }
.unlock-body.locked + .unlock-notice { display:flex; }
```
```javascript
function unlockSection(bodyId, lockId){
  document.getElementById(bodyId).classList.remove('locked');
  document.getElementById(lockId).style.display = 'none';
}
```

### 4.10 Reading Passage — từ khoá gạch chân, tap hiện nghĩa

```html
<div class="reading-box" id="passageBox">
  Every family has <span class="kw" data-mean="chia việc nhà" onclick="toggleKw(this)">household chores<span class="kw-tip">chia việc nhà</span></span> to do...
</div>
<div class="stats-row"><span class="stat-pill" id="kwStat">0/8 từ đã xem</span>
  <button class="rev-btn" onclick="revealAllKw()">Hiện tất cả nghĩa</button></div>
```
```css
.reading-box { background:var(--white); border:1px solid var(--paper-line); border-radius:var(--radius-lg);
  padding:1.5rem; font-size:16px; line-height:2; color:var(--ink); }
.kw { cursor:pointer; border-bottom:2px dashed var(--jade-soft); position:relative; }
.kw:hover, .kw.on { background:var(--jade-pale); }
.kw-tip { display:none; position:absolute; bottom:calc(100% + 8px); left:50%; transform:translateX(-50%);
  background:var(--jade-dark); color:#fff; font-size:11px; padding:5px 10px; border-radius:6px;
  white-space:nowrap; z-index:100; }
.kw.on .kw-tip { display:block; }
.stat-pill { font-size:12px; padding:3px 10px; border-radius:99px; background:var(--cream-2);
  border:1px solid var(--paper-line); color:var(--ink-2); }
.rev-btn { font-size:12px; padding:5px 12px; min-height:32px; border-radius:99px; border:1px solid var(--paper-line);
  background:var(--white); color:var(--ink-2); }
@media (max-width:640px) { .reading-box { padding:0.9rem 0.85rem; font-size:16px; line-height:1.8; } }
```
```javascript
function toggleKw(el){ el.classList.toggle('on'); updateKwStat(); }
function revealAllKw(){ document.querySelectorAll('.kw').forEach(k=>k.classList.add('on')); updateKwStat(); }
function updateKwStat(){
  const total = document.querySelectorAll('.kw').length;
  const seen = document.querySelectorAll('.kw.on').length;
  document.getElementById('kwStat').textContent = `${seen}/${total} từ đã xem`;
}
```

### 4.11 Comprehension Question Card — T/F hoặc MCQ, có `explain`

Dùng chung 1 kiểu thẻ cho cả câu hỏi T/F lẫn trắc nghiệm (nhất quán khi trộn nhiều loại trong 1
bài đọc/nghe):

```html
<div class="q-card" id="q1">
  <div class="q-num">Câu 1 / 6</div>
  <div class="q-text">[nội dung câu hỏi]</div>
  <div class="q-opts" id="q1-opts"><!-- render nút đáp án, hoặc 2 nút True/False --></div>
  <div class="q-explain" id="q1-exp"></div>
</div>
```
```css
.q-card { background:var(--white); border:1px solid var(--paper-line); border-radius:var(--radius-lg);
  padding:1.25rem; margin-bottom:0.75rem; transition:border-color .2s; }
.q-card.ok { border-color:var(--correct); background:var(--correct-bg); }
.q-card.no { border-color:var(--wrong); background:var(--wrong-bg); }
.q-num { font-size:11px; font-weight:600; color:var(--ink-3); text-transform:uppercase; margin-bottom:6px; }
.q-text { font-size:16px; color:var(--ink); margin-bottom:0.5rem; line-height:1.65; }
.q-opts { display:flex; flex-direction:column; gap:6px; margin-top:0.75rem; }
.q-opts button { min-height:44px; padding:10px 14px; border-radius:var(--radius); border:1px solid var(--paper-line);
  background:var(--white); font-size:15px; text-align:left; color:var(--ink); }
.q-opts button.correct { border-color:var(--correct); background:var(--correct-bg); color:var(--jade-text); }
.q-opts button.wrong { border-color:var(--wrong); background:var(--wrong-bg); color:var(--wrong); }
.q-explain { font-size:13px; padding:8px 12px; border-radius:var(--radius-sm); margin-top:0.75rem;
  display:none; line-height:1.6; background:var(--cream-2); color:var(--ink-2); }
.q-explain.show { display:block; }
```

### 4.12 Tap-to-Match — nối từ với nghĩa (KHÔNG dùng kéo-thả)

> **Quyết định thiết kế quan trọng:** bản tham khảo dùng drag-and-drop (`draggable`, kéo thả bằng
> chuột). **Không dùng cho hệ thống này** — kéo-thả rất khó thao tác chính xác trên màn hình cảm
> ứng (ngón tay che mất điểm thả, dễ thả nhầm). Thay bằng **tap-to-select**: chạm 1 từ ở cột trái,
> rồi chạm nghĩa tương ứng ở cột phải để ghép cặp — hoạt động tốt như nhau trên chuột lẫn cảm ứng.
>
> ⚠️ Cả 2 cột PHẢI xáo thứ tự hiển thị bằng `.sort(() => Math.random() - 0.5)` mỗi lần render —
> xem nguyên tắc 7 ở Mục 0 và cảnh báo chi tiết ở Mục 4.6 (Matching).

```html
<div class="match-cols">
  <div><div class="col-label">Từ / Cụm từ</div><div id="matchTerms"></div></div>
  <div><div class="col-label">Nghĩa</div><div id="matchDefs"></div></div>
</div>
```
```css
.match-cols { display:grid; grid-template-columns:1fr 1fr; gap:16px; margin-bottom:1rem; }
@media (max-width:600px){ .match-cols{grid-template-columns:1fr;} }
.match-chip { display:flex; align-items:center; padding:10px 14px; min-height:44px; border-radius:var(--radius);
  border:2px solid var(--paper-line); background:var(--white); font-size:15px; margin-bottom:8px; color:var(--ink); }
.match-chip.active { border-color:var(--accent); background:var(--accent-pale); }
.match-chip.matched { background:var(--correct-bg); border-color:var(--correct); color:var(--jade-text); }
.match-chip.wrong { animation:shake .35s; border-color:var(--wrong); }
@keyframes shake{20%,60%{transform:translateX(-5px);}40%,80%{transform:translateX(5px);}}
```
```javascript
let selectedTerm = null;
function tapTerm(el, key){
  document.querySelectorAll('.match-chip.term').forEach(c=>c.classList.remove('active'));
  el.classList.add('active'); selectedTerm = key;
}
function tapDef(el, key){
  if(!selectedTerm) return;
  if(key === selectedTerm){
    document.querySelector(`.term[data-key="${selectedTerm}"]`).classList.add('matched');
    el.classList.add('matched');
  } else {
    el.classList.add('wrong'); setTimeout(()=>el.classList.remove('wrong'), 400);
  }
  selectedTerm = null;
}
```

### 4.13 Word-Tile Sentence Builder — sắp xếp từ thành câu (tap theo thứ tự)

```html
<div class="tile-bank" id="tileBank"></div>
<div class="tile-answer" id="tileAnswer"></div>
<button class="btn" onclick="resetTiles()">Làm lại</button>
```
```css
.tile-bank, .tile-answer { display:flex; flex-wrap:wrap; gap:6px; min-height:46px;
  padding:8px; border-radius:var(--radius); }
.tile-bank { background:var(--cream-2); }
.tile-answer { border:2px dashed var(--paper-line); background:var(--white); }
.word-tile { display:inline-flex; padding:8px 16px; min-height:40px; align-items:center;
  border-radius:var(--radius); border:1px solid var(--paper-line); background:var(--white);
  font-size:15px; color:var(--ink); cursor:pointer; }
.word-tile.used { opacity:.3; pointer-events:none; }
```
```javascript
// Click tile trong bank → thêm vào answer theo đúng thứ tự click (không cần kéo)
// Click tile trong answer → trả lại bank (undo)
```

### 4.14 Audio Chunk / Shadowing Player

Thường gặp ở Speaking (nghe & luyện theo chunk) và Listening, nhưng dùng được ở bất kỳ bài nào cần
phát âm mẫu. Ưu tiên `speechSynthesis` (miễn phí, không cần hosting audio) trừ khi giáo viên có
file audio thật cần phát đúng giọng.

```html
<div class="chunk-row">
  <button class="audio-btn" onclick="speak('[câu tiếng Anh]')"><i class="ti ti-volume"></i></button>
  <span class="chunk-text">[câu tiếng Anh hiển thị]</span>
</div>
```
```css
.chunk-row { display:flex; align-items:center; gap:10px; padding:10px 0; border-bottom:1px solid var(--cream-2); }
.chunk-text { font-size:16px; color:var(--ink); }
```
```javascript
function speak(text, lang='en-GB'){
  if(!('speechSynthesis' in window)) return;
  const u = new SpeechSynthesisUtterance(text); u.lang = lang; u.rate = 0.9;
  speechSynthesis.cancel(); speechSynthesis.speak(u);
}
// Ghi âm học sinh (shadowing): dùng MediaRecorder API nếu cần — ghi rõ trong kịch bản nếu bắt
// buộc, vì cần xin quyền micro (không tự ý bật khi chưa có yêu cầu rõ trong kịch bản).
```

### 4.15 Writing — đọc mẫu, điền khung gợi ý, viết tự do

```html
<div class="model-text" id="modelText"><!-- đoạn văn/email mẫu --></div>

<div class="frame-row">
  <span>Every [<input class="frame-inp" placeholder="thời gian…">] my family</span>
  <select class="frame-inp"><option>does the cooking</option><option>does the laundry</option></select>
</div>

<textarea class="write-area" placeholder="Viết bài của bạn ở đây..." oninput="trackWriting()"></textarea>
<div class="word-count" id="wordCount">0 từ</div>
```
```css
.model-text { background:var(--cream-2); border-left:4px solid var(--jade-deep); border-radius:0 var(--radius) var(--radius) 0;
  padding:1rem 1.25rem; font-size:16px; line-height:1.75; margin-bottom:1rem; }
.frame-row { padding:10px 0; font-size:16px; line-height:2; }
.frame-inp { border:2px solid var(--paper-line); border-radius:var(--radius-sm); padding:6px 10px;
  font-size:14px; min-width:120px; min-height:36px; background:var(--white); }
.write-area { width:100%; min-height:160px; border:2px solid var(--paper-line); border-radius:var(--radius);
  padding:12px 14px; font-size:15px; font-family:inherit; resize:vertical; }
.write-area:focus { outline:none; border-color:var(--jade-deep); }
.word-count { font-size:12px; color:var(--ink-3); margin-top:4px; text-align:right; }
```

### 4.15b Write Hint — khối 💡 hint tĩnh, hiển thị TRƯỚC khi học sinh viết (mới, v2.7)

> **KHÁC Mục 9.2:** Mục 9.2 ("Không có gợi ý (hint)") chỉ áp dụng cho MCQ/trắc nghiệm — mục đích là
> chặn đoán mò trước khi trả lời có đúng/sai. Writing không có đúng/sai tuyệt đối, và hint ở đây
> không phải "gợi ý đáp án" mà là hướng dẫn CÁCH bắt đầu — chỉ dùng khi bảng scaffold (Reason/
> Example/Explain, Period/Event/Significance...) không còn đủ để tự giải thích nhiệm vụ (VD: Guided
> Writing hỗ trợ giảm không còn sentence starter, Independent Writing không có bảng gợi ý nào).
> KHÔNG thêm Write Hint vào Activity đã có bảng scaffold đầy đủ — thừa và làm loãng "kịch bản sạch".

```html
<div class="write-hint">💡 <span class="write-hint-text">[nội dung hint tiếng Anh, viết như 1 lời nhắc trực tiếp cho học sinh]</span></div>
```
```css
.write-hint { background:var(--cream-2); border-left:3px solid var(--jade-deep); border-radius:0 var(--radius-sm) var(--radius-sm) 0;
  padding:10px 14px; font-size:14.5px; line-height:1.6; color:var(--ink-2); margin-bottom:12px; }
.write-hint-text { font-style:italic; }
```

**⚠️ Bắt buộc:**
1. Nội dung hint LUÔN tiếng Anh (đúng Nguyên tắc 15, Mục 0) — đây là nội dung học sinh đọc trực
   tiếp, không phải ghi chú thiết kế.
2. Đặt ngay TRÊN ô `textarea`/khung điền, không đặt trong popup/tooltip cần thêm 1 lượt tap mới
   thấy — hint phải hiện sẵn, không ẩn thêm 1 lớp.
3. 1 Activity chỉ có TỐI ĐA 1 khối Write Hint — không lặp lại hint ở nhiều vị trí trong cùng 1 bài.

### 4.16 Diagnostic / Revision — câu hỏi trộn nhiều category, chấm điểm theo nhóm

Thường gặp ở bài Revision/Ôn tập cuối Unit, nhưng dùng được bất cứ khi nào cần trộn nhiều loại
kiến thức trong 1 bài kiểm tra. Câu hỏi gắn nhãn category (`vocab`/`grammar`/`reading`...), kết
quả chia theo từng nhóm để học sinh biết đang yếu phần nào.

```javascript
const diagQuestions = [
  { cat:'vocab',   q:'...', /* ...options, answer, explain... */ },
  { cat:'grammar', q:'...', /* ... */ },
  { cat:'reading', q:'...', /* ... */ },
];
function scoreByCategory(answered){
  const cats = {};
  diagQuestions.forEach((q,i) => {
    cats[q.cat] = cats[q.cat] || {ok:0, total:0};
    cats[q.cat].total++;
    if (answered[i]?.isCorrect) cats[q.cat].ok++;
  });
  return cats; // { vocab:{ok,total}, grammar:{ok,total}, reading:{ok,total} }
}
```
```html
<div class="cat-badges">
  <span class="badge" id="badge-vocab">📘 Vocab: 0/0</span>
  <span class="badge" id="badge-grammar">📗 Grammar: 0/0</span>
  <span class="badge" id="badge-reading">📕 Reading: 0/0</span>
</div>
```
```css
.cat-badges { display:flex; gap:8px; flex-wrap:wrap; margin:1rem 0; }
.badge { font-size:12.5px; padding:5px 12px; border-radius:99px; background:var(--info-bg); color:var(--info); font-weight:600; }
.badge.weak { background:var(--wrong-bg); color:var(--wrong); }
.badge.strong { background:var(--correct-bg); color:var(--jade-text); }
```

> Nhóm nào đạt <70% → gắn class `.weak`, gợi ý học sinh ôn lại đúng module tương ứng (VD:
> "Grammar còn yếu — xem lại Module 3 nhé").

### 4.17 Tap-to-Categorize — phân loại/xếp nhóm (KHÔNG dùng kéo-thả)

> Dùng khi bài cần học sinh xếp 1 danh sách thẻ vào đúng nhóm (VD: xếp hành vi vào "Hợp pháp/Không
> hợp pháp", xếp từ vào "Danh từ/Động từ/Tính từ", xếp việc nhà vào "Trong nhà/Ngoài trời"...).
> **Đây chính là dạng dễ bị build nhầm bằng kéo-thả nhất** — trực giác thường nghĩ "phân loại =
> kéo vào ô", nhưng thao tác đúng chuẩn ở đây vẫn là tap-to-select 2 bước: chạm 1 thẻ cần phân loại
> → chạm nút tên nhóm muốn xếp vào, y hệt tinh thần Tap-to-Match ở Mục 4.12.

```html
<div class="cat-item-list" id="catItems"></div>
<div class="cat-buckets">
  <button class="cat-bucket-btn" data-bucket="legal" onclick="assignBucket('legal')">✅ Hợp pháp</button>
  <button class="cat-bucket-btn" data-bucket="illegal" onclick="assignBucket('illegal')">🚫 Không hợp pháp</button>
</div>
```
```css
.cat-item-list { display:flex; flex-wrap:wrap; gap:8px; margin-bottom:16px; }
.cat-item { min-height:44px; padding:9px 16px; border-radius:var(--radius); border:2px solid var(--paper-line);
  background:var(--white); font-size:15px; color:var(--ink); }
.cat-item.selected { border-color:var(--accent); background:var(--accent-pale); }
.cat-item.placed { opacity:.4; pointer-events:none; }
.cat-buckets { display:flex; gap:10px; flex-wrap:wrap; }
.cat-bucket-btn { min-height:44px; padding:10px 18px; border-radius:var(--radius); border:2px dashed var(--paper-line);
  background:var(--cream-2); font-weight:600; font-size:13.5px; color:var(--ink-2); }
.cat-bucket-btn.correct-flash { border-color:var(--correct); background:var(--correct-bg); }
.cat-bucket-btn.wrong-flash { border-color:var(--wrong); background:var(--wrong-bg); }
```
```javascript
// items: [{ id, text, correctBucket }] — xáo thứ tự hiển thị .catItems mỗi lần render (nguyên tắc 7)
let selectedItem = null;
function tapCatItem(el, id) {
  if (el.classList.contains('placed')) return;
  document.querySelectorAll('.cat-item').forEach(i => i.classList.remove('selected'));
  el.classList.add('selected');
  selectedItem = { el, id };
}
function assignBucket(bucketKey) {
  if (!selectedItem) return;
  const item = items.find(i => i.id === selectedItem.id);
  const btn = document.querySelector(`.cat-bucket-btn[data-bucket="${bucketKey}"]`);
  const ok = item.correctBucket === bucketKey;
  btn.classList.add(ok ? 'correct-flash' : 'wrong-flash');
  setTimeout(() => btn.classList.remove('correct-flash', 'wrong-flash'), 400);
  if (ok) { selectedItem.el.classList.add('placed'); selectedItem.el.classList.remove('selected'); }
  // Sai: KHÔNG khoá thẻ, để học sinh chọn lại nhóm khác — chỉ hiện explain (bắt buộc, xem Mục 0.5)
  selectedItem = null;
}
```

### 4.18 Before/After Comparison Slider — kéo so sánh Trước/Sau (Warm-up/hook trực quan)

> **Dùng khi nào:** kịch bản cần học sinh tự kéo để đối chiếu 2 trạng thái đối lập của cùng 1
> cảnh/chủ đề (VD "bữa cơm gia đình 20 năm trước vs hiện tại", "before/after" 1 thói quen, 1 không
> gian...) làm hook mở bài trước khi vào Getting Started. **Không dùng cho bài luyện tập chấm
> điểm** — đây thuần là công cụ khám phá trực quan, không có đúng/sai.
>
> **Xem lại Nguyên tắc 4 (Mục 0):** đây là ngoại lệ DUY NHẤT được phép "kéo" trong toàn hệ thống,
> vì bản chất khác drag-and-drop-vào-đích — chỉ là 1 tay cầm trượt liên tục trên 1 trục ngang,
> không có khái niệm "thả đúng chỗ". Nhưng chính vì là thao tác kéo, nó **rất dễ vỡ trên mobile**
> nếu thiếu 2 dòng bắt buộc bên dưới: trình duyệt mobile mặc định coi mọi cử chỉ kéo dọc/ngang
> trong vùng đó là để **cuộn trang**, nên nếu không chặn rõ ràng, học sinh chạm vào thanh trượt sẽ
> bị cuộn cả màn hình thay vì di chuyển được thanh.

```css
.comparison-container {
  position: relative;
  width: 100%;
  height: 100%;
  cursor: col-resize;
  touch-action: none; /* BẮT BUỘC — không có dòng này, kéo trên mobile = cuộn trang, không di
                          chuyển được thanh trượt. Báo cho trình duyệt biết vùng này do JS xử lý
                          toàn bộ cử chỉ chạm, không nhường lại cho hành vi cuộn mặc định. */
}
.img-after-wrapper {
  position: absolute; inset: 0; overflow: hidden;
  clip-path: polygon(var(--slider-pos) 0, 100% 0, 100% 100%, var(--slider-pos) 100%);
}
```
```javascript
// sliderPos: 0-100, lưu vào CSS var --slider-pos để clip-path ảnh "after" theo đúng vị trí kéo
function handleMove(e) {
  if (!isDragging) return;
  if (e.touches) e.preventDefault(); // BẮT BUỘC — chặn cuộn trang khi ngón tay đang kéo thanh.
                                      // Chỉ có tác dụng NẾU listener touchmove đăng ký
                                      // { passive: false } bên dưới — thiếu 1 trong 2 là hỏng.
  const rect = container.getBoundingClientRect();
  const clientX = e.touches ? e.touches[0].clientX : e.clientX;
  const percentage = ((clientX - rect.left) / rect.width) * 100;
  setSliderPosition(Math.max(0, Math.min(100, percentage)));
}

container.addEventListener('mousedown', (e) => { isDragging = true; handleMove(e); });
window.addEventListener('mousemove', handleMove);
window.addEventListener('mouseup', () => { isDragging = false; });

container.addEventListener('touchstart', (e) => { isDragging = true; handleMove(e); }, { passive: true });
// { passive: false } BẮT BUỘC ở touchmove — mặc định trình duyệt đăng ký passive:true để tối ưu
// hiệu năng cuộn, khiến preventDefault() ở handleMove bị trình duyệt ÂM THẦM BỎ QUA (không báo lỗi
// gì cả, chỉ đơn giản là không có tác dụng) nếu thiếu khai báo này.
window.addEventListener('touchmove', handleMove, { passive: false });
window.addEventListener('touchend', () => { isDragging = false; });
```

> **Lỗi thường gặp nếu bỏ sót:** kéo thanh trượt trên desktop (chuột) chạy đúng 100%, chỉ lộ ra khi
> **mở bằng điện thoại thật** — kéo phát là cả trang cuộn theo, không di chuyển được vạch chia
> ảnh. Vì lỗi chỉ hiện trên touch, dễ lọt qua nghiệm thu nếu chỉ test bằng DevTools responsive mode
> trên desktop (chuột vẫn giả lập là mousedown, không kích hoạt đúng nhánh touchmove/passive).
> **Bắt buộc test bằng ngón tay thật trên điện thoại**, không chỉ resize cửa sổ trình duyệt.

---

### 4.19 Vietnamese Translation Toggle — nút bật/tắt bản dịch, mặc định ẩn

> **Dùng khi nào:** mọi module (đặc biệt Speaking) khi cần đưa 1 đoạn hướng dẫn/mô tả nhiệm vụ
> DÀI hoặc có khái niệm khó sang tiếng Việt hỗ trợ, nhưng KHÔNG được hiển thị song song 2 thứ
> tiếng cùng lúc theo mặc định (làm rối mắt, học sinh lười đọc bản tiếng Anh). Đây là component
> thay thế cho việc viết thẳng song ngữ trong nội dung.
>
> **Không dùng cho:** câu hỏi/đề bài (Practice, MCQ, Task...) — nội dung câu hỏi PHẢI luôn thuần
> tiếng Anh, không được có bản dịch kèm theo dưới bất kỳ hình thức nào, kể cả toggle. Không dùng
> cho nhãn nút/tiêu đề ngắn, đơn giản (những chỗ đó chỉ cần viết tiếng Anh, không cần dịch).
> Không dùng cho dòng "Giải thích" sau khi trả lời — dòng đó vẫn viết thẳng tiếng Việt như quy tắc
> chung, không bọc qua toggle.

```html
<p>...nội dung tiếng Anh cần hỗ trợ dịch...</p>
<button class="vi-toggle" onclick="toggleVi(this,'vi-xxx')">🇻🇳 Show translation</button>
<div class="vi-text" id="vi-xxx">...bản dịch tiếng Việt...</div>
```
```css
.vi-toggle { background:none; border:none; color:var(--jade-text); font-size:11.5px; font-weight:700;
  cursor:pointer; padding:3px 0; margin-top:4px; display:inline-flex; align-items:center; gap:4px; }
.vi-toggle:hover { text-decoration:underline; }
.vi-text { display:none; font-size:12.5px; color:var(--ink-3); font-style:italic; margin:4px 0 0; line-height:1.5; }
.vi-text.show { display:block; }
```
```javascript
function toggleVi(btn, id) {
  const vi = document.getElementById(id);
  const showing = vi.classList.toggle('show');
  btn.textContent = showing ? '🇻🇳 Hide translation' : '🇻🇳 Show translation';
}
```

> **Mỗi `id` phải DUY NHẤT trong toàn file** — kể cả khi 1 trang có nhiều khối `.vi-toggle` (VD
> nhiều bước Production khác nhau), không được trùng `id` giữa các khối, nếu không nút bấm sau sẽ
> điều khiển nhầm sang khối `.vi-text` đầu tiên có cùng id.
>
> **Lỗi thật đã gặp:** khi viết nội dung cho toggle, nếu chuỗi tiếng Anh có dấu nháy đơn
> (don't/isn't/you'll...) và JS bọc chuỗi bằng `'...'`, PHẢI escape thành `\'` — thiếu escape làm
> đóng chuỗi JS sớm, gây lỗi cú pháp âm thầm (không hiện lỗi trên giao diện, chỉ làm toàn bộ nút
> bấm sau đó ngừng hoạt động). Ưu tiên viết câu trong chuỗi JS tránh contraction, hoặc bọc bằng
> `"..."` nếu nội dung không chứa dấu `"`.

### 4.20 Guided Noticing — ô gõ tự do, tự đối chiếu đáp án (KHÔNG auto-chấm)

> **Dùng khi nào:** bước "học sinh tự tìm cụm từ chức năng ngôn ngữ trong hội thoại/văn bản mẫu
> TRƯỚC KHI xem bảng Useful Expressions đầy đủ" (kịch bản Speaking gọi là "Menu B — Guided
> Noticing", dùng lặp lại từ Unit 4 trở đi ở Bước 1). Mục đích là để học sinh chủ động quan sát/
> suy luận trước, không phải để chấm điểm đúng-sai — vì câu trả lời có thể diễn đạt khác chữ với
> đáp án gợi ý mà vẫn đúng ý (VD học sinh chép đúng 1 phần câu, hoặc diễn đạt lại bằng từ khác).
>
> **Khác với Gap-fill/Cloze (4.6):** Gap-fill chấm đúng/sai tự động bằng `checkTextAnswer()` vì
> đáp án là 1 từ/cụm từ cố định, không có chỗ diễn giải. Guided Noticing thì NGƯỢC LẠI — không
> gọi `checkTextAnswer()`, không có trạng thái đúng/sai, chỉ có 2 trạng thái: "đang gõ" và "đã xem
> đáp án". Không dùng nhầm 2 component này cho nhau.

```html
<div class="notice-box">
  <p class="notice-q">1 cách diễn đạt ĐỒNG Ý mà nhân vật đã dùng:</p>
  <textarea class="notice-input" id="notice-1" placeholder="Gõ câu trả lời của bạn ở đây..."></textarea>
</div>
<button class="reveal-btn" onclick="revealNotice(['notice-1','notice-2','notice-3'], 'notice-ans-block')">
  Hiện đáp án
</button>
<div class="notice-ans-block" id="notice-ans-block" hidden>
  <p><b>Đáp án gợi ý:</b> "I totally agree that..."</p>
  <p class="notice-note">Câu trả lời của bạn không cần giống hệt — chỉ cần đúng ý là được.</p>
</div>
```
```css
.notice-box { margin-bottom:14px; }
.notice-q { font-size:15px; font-weight:600; color:var(--ink); margin-bottom:8px; }
.notice-input { width:100%; min-height:44px; border:2px solid var(--paper-line); border-radius:var(--radius-sm);
  padding:10px 12px; font-size:15px; font-family:inherit; resize:vertical; }
.notice-input:focus { outline:none; border-color:var(--jade-deep); }
.reveal-btn { background:var(--white); color:var(--jade-text); border:2px solid var(--jade-soft);
  border-radius:999px; padding:10px 22px; font-weight:700; font-size:14px; min-height:44px; margin-top:4px; }
.reveal-btn:hover { background:var(--jade-pale); }
.notice-ans-block { margin-top:14px; background:var(--cream-2); border-radius:var(--radius);
  padding:14px 16px; font-size:14.5px; color:var(--ink-2); }
.notice-ans-block p { margin:0 0 6px; }
.notice-note { font-style:italic; color:var(--ink-3); font-size:13px; }
```
```javascript
// KHÔNG so sánh nội dung textarea với đáp án — chỉ hiện khối đáp án khi bấm nút.
// Không gọi checkTextAnswer(), không gọi recordMistake() — bước này không tính điểm.
function revealNotice(inputIds, ansBlockId) {
  document.getElementById(ansBlockId).hidden = false;
  document.getElementById(ansBlockId).scrollIntoView({behavior:'smooth', block:'nearest'});
}
```

> **⚠️ Bắt buộc:**
> 1. KHÔNG gọi `checkTextAnswer()` hay bất kỳ hàm so khớp chuỗi nào cho `.notice-input` — đây là
>    điểm khác biệt cốt lõi với Gap-fill (4.6).
> 2. KHÔNG gọi `recordMistake()` khi bấm "Hiện đáp án" — mở đáp án không tính là làm sai, không
>    ảnh hưởng adaptive routing (giống nguyên tắc Recap ở Mục 9.13 của Engine).
> 3. Nút "Hiện đáp án" hiện đủ TẤT CẢ đáp án gợi ý của cả khối Guided Noticing đó cùng lúc (không
>    tách riêng từng câu 1 nút, trừ khi kịch bản có ghi rõ tách riêng).
> 4. Sau khi hiện đáp án, KHÔNG khoá/disable lại ô `.notice-input` — học sinh vẫn có thể sửa/gõ
>    thêm nếu muốn, vì đây không phải bài chấm điểm.
> 5. Đề bài của khối này (`.notice-q`) viết tiếng Việt bình thường (không phải nội dung
>    câu hỏi/đề luyện tập chính thức phải thuần tiếng Anh như Mục 4.19 quy định) — vì đây là
>    hướng dẫn hoạt động, không phải đề bài chấm điểm.

### 4.21 Idea Diagram — sơ đồ cây phát triển ý (gốc → nhánh → lá), 4 mức hỗ trợ

> **Dùng khi nào:** bài cần học sinh brainstorm ý theo cấu trúc phân tầng trước khi viết/nói (Writing
> Suggestion & Benefits paragraph, thảo luận có lập luận...). Thay thế hoàn toàn ý tưởng "vẽ mindmap
> tự do" bằng 1 cấu trúc CỐ ĐỊNH (gốc → N nhánh → M lá/nhánh) — không cho học sinh tự kéo/định vị
> node, vì bất kỳ thao tác "đặt node ở đâu tuỳ ý" nào cũng khó chấm và dễ vỡ trên mobile.
>
> **Quyết định thiết kế quan trọng — không dùng SVG vẽ đường nối:** đường nối cây thường được dựng
> bằng SVG/absolute-position tính toạ độ bằng JS — cách này CỰC DỄ VỠ khi mobile xoay ngang/dọc hoặc
> khi bàn phím ảo đẩy layout (phải tính lại toạ độ mỗi lần). Thay vào đó, dùng thuần CSS Flexbox +
> border để gợi ý đường nối (không phải đường nối thật), tự động responsive không cần JS đo lại gì.

```html
<div class="idea-diagram" data-state="partial">
  <div class="idea-root">Benefits of Viet Nam's participation in international organisations</div>
  <div class="idea-branches">
    <div class="idea-branch" style="--branch-color: var(--jade-deep)">
      <div class="idea-branch-title">Cultural exchange</div>
      <ul class="idea-leaves">
        <li class="idea-leaf filled">promote Vietnamese culture abroad</li>
        <li class="idea-leaf blank"><input class="idea-leaf-input" placeholder="✏️ your idea..."></li>
      </ul>
    </div>
    <div class="idea-branch" style="--branch-color: var(--accent)">
      <div class="idea-branch-title">Educational opportunities</div>
      <ul class="idea-leaves">
        <li class="idea-leaf blank"><input class="idea-leaf-input" placeholder="✏️ your idea..."></li>
        <li class="idea-leaf blank"><input class="idea-leaf-input" placeholder="✏️ your idea..."></li>
      </ul>
    </div>
  </div>
  <button class="idea-suggest-btn" onclick="toggleSuggestion(this)">💡 So sánh gợi ý</button>
  <div class="idea-suggestion" hidden><!-- nội dung gợi ý, không phải đáp án đúng/sai --></div>
</div>
```
```css
.idea-diagram { padding: 4px 0; }
.idea-root {
  background: var(--jade-deep); color: #fff; font-weight: 700; text-align: center;
  border-radius: var(--radius); padding: 14px 18px; margin-bottom: 4px; font-size: 15px;
}
/* Gợi ý đường nối: 1 vạch ngắn thuần CSS, không phải SVG — không cần tính lại khi resize */
.idea-root::after {
  content: ""; display: block; width: 2px; height: 14px; background: var(--paper-line);
  margin: 0 auto;
}
.idea-branches {
  display: flex; gap: 14px; flex-wrap: wrap; /* desktop: hàng ngang, tự xuống dòng nếu chật */
}
.idea-branch {
  flex: 1 1 220px; /* mobile ≤480px: mỗi nhánh chiếm trọn hàng vì flex-basis > nửa màn hình nhỏ */
  background: var(--cream-2); border-top: 4px solid var(--branch-color);
  border-radius: 0 0 var(--radius) var(--radius); padding: 12px 14px;
}
.idea-branch-title { font-weight: 700; color: var(--ink); margin-bottom: 8px; font-size: 14.5px; }
.idea-leaves { display: flex; flex-direction: column; gap: 6px; } /* LUÔN dọc, kể cả desktop —
  danh sách lá vốn hẹp, không cần layout ngang, tránh mọi rủi ro responsive ở tầng này */
.idea-leaf { background: var(--white); border-radius: var(--radius-sm); padding: 8px 10px;
  font-size: 14px; min-height: 40px; display: flex; align-items: center; }
.idea-leaf.filled::before { content: "✓ "; color: var(--jade-deep); font-weight: 700; }
.idea-leaf-input { width: 100%; border: 2px dashed var(--paper-line); border-radius: var(--radius-sm);
  padding: 8px 10px; font-size: 14px; min-height: 40px; background: var(--white); }
.idea-leaf-input:focus { outline: none; border-color: var(--jade-deep); border-style: solid; }
.idea-suggest-btn { margin-top: 12px; min-height: 44px; padding: 10px 18px; border-radius: var(--radius-sm);
  background: var(--cream-2); border: 2px solid var(--paper-line); font-weight: 600; }
.idea-suggestion { margin-top: 10px; background: var(--jade-pale); border-radius: var(--radius); padding: 12px 16px; }

/* Mobile ≤480px: ép mỗi nhánh xuống 1 hàng riêng, KHÔNG dùng flex-wrap tự nhiên vì item cuối có
   thể kẹt cạnh item trước nếu vừa đủ 2 cột hẹp — ép rõ ràng để chắc chắn luôn xếp dọc */
@media (max-width: 480px) {
  .idea-branches { flex-direction: column; }
  .idea-branch { flex-basis: auto; }
}
```

**4 mức hỗ trợ, đặt qua `data-state`:**

| `data-state` | Root/Branch | Leaf |
|---|---|---|
| `full` | text tĩnh | toàn bộ `.idea-leaf.filled` (✓, đọc/phân tích) |
| `partial` | text tĩnh | mix `.filled` + `.idea-leaf-input` (viền nét đứt) |
| `guided` | text tĩnh | thay `<ul>` bằng 1 đoạn `<p class="idea-guiding-q">` (câu hỏi gợi mở, in nghiêng) + 1 `<textarea>` |
| `blank` | root/branch title cũng là `<input>` | toàn bộ `.idea-leaf-input`; có thêm nút `+ Add branch` (JS clone `.idea-branch` rỗng) |

> **Không auto-chấm bất kỳ ô nào** (đúng tinh thần Guided Noticing 4.20) — nút "💡 So sánh gợi ý"
> chỉ hiện khối gợi ý bên cạnh, không khoá ô input, không đánh giá đúng/sai.
> **📱 Mobile:** đã ép `flex-direction: column` ở `.idea-branches` — không cần accordion thu gọn vì
> mỗi branch vốn đã ngắn (title + 2-3 leaf); nếu nội dung 1 branch quá dài (>4 leaf), bọc thêm
> `<details>`/`<summary>` gốc HTML thay vì tự viết JS toggle (nhẹ hơn, có accessibility mặc định).

### 4.22 Auto-collapse Theory Block — tự gom lý thuyết dài khi chuyển sang phần mới

> **Dùng khi nào:** khối lý thuyết/giải thích dài đứng nối tiếp nhau trước phần luyện tập (VD chuỗi
> Hook → Khung tổng quát → Đi sâu từng phần → Phân tích bài mẫu → Bảng tín hiệu ở Writing) — xem
> Nguyên tắc 14 (Mục 0). Dùng `<details>`/`<summary>` gốc HTML thay vì tự viết JS toggle riêng — nhẹ
> hơn, có accessibility mặc định (đọc được bằng screen reader, hoạt động cả khi JS lỗi).

```html
<details class="theory-block" open data-block="hook">
  <summary class="theory-block-title">🌍 Hook — Viet Nam's Blue Berets</summary>
  <div class="theory-block-body">
    <!-- toàn bộ nội dung Hook -->
  </div>
</details>
<details class="theory-block" data-block="tool">
  <summary class="theory-block-title">🧠 A thinking tool: Diagrams for developing ideas</summary>
  <div class="theory-block-body"><!-- ... --></div>
</details>
```
```css
.theory-block { background: var(--white); border-radius: var(--radius); margin-bottom: 10px;
  border: 1px solid var(--paper-line); overflow: hidden; }
.theory-block-title { min-height: 44px; padding: 12px 16px; font-weight: 700; font-size: 15px;
  color: var(--ink); cursor: pointer; list-style: none; display: flex; align-items: center;
  gap: 8px; }
.theory-block-title::-webkit-details-marker { display: none; } /* ẩn tam giác mặc định, tự vẽ mũi tên */
.theory-block-title::before { content: "▸"; transition: transform .2s; color: var(--jade-deep); }
.theory-block[open] > .theory-block-title::before { transform: rotate(90deg); }
.theory-block-body { padding: 0 16px 16px; font-size: 15px; line-height: 1.7; }
```
```javascript
// Tự gom khối trước khi mở khối kế tiếp — gắn theo thứ tự đọc, KHÔNG gọi khi học sinh tự bấm mở
// lại 1 khối cũ (chỉ auto-collapse theo tiến trình đọc xuôi, không ép đóng khi học sinh chủ động mở)
function autoCollapsePrev(nextBlockEl) {
  const blocks = [...document.querySelectorAll('.theory-block')];
  const idx = blocks.indexOf(nextBlockEl);
  if (idx > 0) blocks[idx - 1].open = false;
  nextBlockEl.open = true;
}
```

> **⚠️ Bắt buộc:**
> 1. Chỉ auto-collapse khối LIỀN TRƯỚC khi học sinh chủ động mở khối MỚI (cuộn tới hoặc bấm) — không
>    gom ngược các khối đã mở trước đó xa hơn, tránh học sinh mất dấu đang đọc tới đâu.
> 2. Bấm vào `<summary>` của khối đã gom LUÔN mở lại được, không giới hạn số lần mở/đóng.
> 3. KHÔNG dùng cho khối luyện tập có chấm điểm (Practice/Write) — chỉ dùng cho khối lý thuyết đọc/
>    phân tích thuần tuý; khối luyện tập dùng đúng Progressive Unlock (4.9) hoặc Step-gate (4.5).
> 4. `open` mặc định chỉ đặt `true` cho khối ĐẦU TIÊN — các khối sau mặc định đóng, tự mở khi học
>    sinh cuộn tới hoặc bấm, không hiện sẵn hết gây trang dài vô hạn ngay từ đầu.

---

### 4.23 Region Highlight — nhãn bấm tô sáng 1 VÙNG lớn (đoạn/nhóm câu), loại trừ lẫn nhau

> **Khác với Interactive Analyzer/Hotspot-từng-câu** (đã dùng ở Writing Unit 1 Lớp 11 — mỗi CÂU là
> 1 hotspot riêng, có nút "Phân tích tự động" chạy tuần tự): component này dùng khi bài mẫu cần chia
> thành các VÙNG LỚN hơn (cả 1 Reason gồm Point+Example+Explain tô chung 1 màu, không tách 3 màu con)
> — phù hợp thể loại có ít mốc chức năng lớn (Opinion essay: Introduction/Reason 1/Reason 2/
> Conclusion) hơn là nhiều câu chức năng nhỏ lặp lại. Không cần nút "Phân tích tự động" vì số vùng
> ít, hiển thị tĩnh 4 nút nhãn là đủ.

```html
<div class="region-highlight-wrap">
  <div class="region-labels">
    <button class="region-label" data-region="intro" onclick="highlightRegion(this,'intro')">Introduction</button>
    <button class="region-label" data-region="r1" onclick="highlightRegion(this,'r1')">Reason 1</button>
    <button class="region-label" data-region="r2" onclick="highlightRegion(this,'r2')">Reason 2</button>
    <button class="region-label" data-region="concl" onclick="highlightRegion(this,'concl')">Conclusion</button>
  </div>
  <p class="region-text">
    <span class="region-span" data-region="intro">Should teenagers be allowed to choose their own bedtime? ...</span>
    <span class="region-span" data-region="r1">First of all, many teenagers do not get enough sleep...</span>
    <span class="region-span" data-region="r2">In addition, a regular bedtime helps teenagers stay focused...</span>
    <span class="region-span" data-region="concl">In conclusion, although teenagers are growing more independent...</span>
  </p>
</div>
```
```css
.region-labels { display:grid; grid-template-columns:repeat(4,1fr); gap:8px; margin-bottom:14px; }
@media (max-width:600px){ .region-labels{grid-template-columns:1fr 1fr;} }
.region-label { background:var(--cream-2); border:1.5px solid var(--paper-line-2); border-radius:var(--radius-sm);
  padding:9px 10px; font-size:13px; font-weight:700; color:var(--ink-2); min-height:44px; }
.region-label.active-intro { background:var(--accent-pale); border-color:var(--accent); color:var(--accent-text); }
.region-label.active-r1 { background:var(--jade-pale); border-color:var(--jade); color:var(--jade-text); }
.region-label.active-r2 { background:var(--sage-pale); border-color:var(--sage); color:var(--sage-text); }
.region-label.active-concl { background:var(--accent-pale); border-color:var(--accent-deep); color:var(--accent-text); }
.region-text { font-size:16px; line-height:1.8; }
.region-span { transition:background .2s ease; border-radius:4px; padding:1px 2px; }
.region-span.lit-intro { background:var(--accent-pale); }
.region-span.lit-r1 { background:var(--jade-pale); }
.region-span.lit-r2 { background:var(--sage-pale); }
.region-span.lit-concl { background:var(--accent-pale); }
```
```javascript
function highlightRegion(btn, regionKey) {
  // CHỈ 1 vùng sáng tại 1 thời điểm — xoá màu vùng trước đó, không cộng dồn
  document.querySelectorAll('.region-label').forEach(b => b.classList.remove(...b.classList.value.split(' ').filter(c => c.startsWith('active-'))));
  document.querySelectorAll('.region-span').forEach(s => s.classList.remove(...s.classList.value.split(' ').filter(c => c.startsWith('lit-'))));
  btn.classList.add('active-' + regionKey);
  document.querySelectorAll(`.region-span[data-region="${regionKey}"]`).forEach(s => s.classList.add('lit-' + regionKey));
}
```

**⚠️ Bắt buộc:**
1. Mỗi lần bấm 1 nhãn CHỈ tô sáng đúng vùng đó, xoá màu vùng đang tô trước — không cộng dồn nhiều
   vùng sáng cùng lúc.
2. Nếu 1 vùng (VD Reason) gồm nhiều lớp con (Point/Example/Explain) nhưng kịch bản chỉ định "1 màu
   duy nhất" cho cả vùng, KHÔNG tách thêm màu con — dùng đúng 1 `data-region`/1 màu cho toàn vùng.
3. Nhãn xếp lưới 2×2 trên mobile (không xếp 1 hàng ngang 4 nút gây chữ quá nhỏ).
4. Dùng khi số vùng cố định và ít (3-5 vùng lớn); nếu bài mẫu cần chỉ ra CHỨC NĂNG TỪNG CÂU riêng lẻ
   (nhiều hơn 5-6 điểm chạm), dùng Interactive Analyzer/hotspot-từng-câu thay vì component này.
5. **KHÔNG dùng Region Highlight cho thể loại tường thuật theo thời gian** (Biography, Blog post) —
   thể loại đó có trục thời gian thật, dùng đúng Timeline Infographic (Mục 4.24) để không bỏ lỡ điểm
   mạnh chuỗi mốc thời gian của thể loại. Region Highlight chỉ dùng cho thể loại KHÔNG có trục thời
   gian (Opinion essay, For-and-against...).

---

### 4.24 Timeline Infographic — mốc thời gian dạng node dọc, dùng cho Biography/Blog post

> **Bắt buộc cho mọi bài mẫu phân tích (mục D) thuộc thể loại tường thuật theo thời gian** (Biography,
> Blog post kể chuyện quá khứ) — THAY THẾ Region Highlight (4.23)/bảng nút bấm thường. Lỗi thật đã
> gặp: 1 bài mẫu Biography dùng nguyên cơ chế "nút bấm tô vùng" vay mượn từ Opinion essay (thể loại
> không có trục thời gian) — bỏ lỡ đúng điểm mạnh của Biography (chuỗi mốc năm tháng rõ ràng, khớp
> thẳng trọng tâm ngữ pháp Past simple/Past continuous hay đi kèm thể loại này).

```html
<div class="timeline-wrap">
  <div class="timeline-line"></div>
  <div class="timeline-node" data-node="n1">
    <button class="node-head" onclick="toggleTimelineNode(this)">
      <span class="node-dot">📍</span>
      <span class="node-year">1867</span>
      <span class="node-headline">Born in Warsaw, Poland</span>
    </button>
    <div class="node-detail">She was born in Warsaw, Poland, in 1867.</div>
  </div>
  <!-- Lặp lại .timeline-node cho từng mốc còn lại -->
</div>
```
```css
.timeline-wrap { position:relative; padding-left:28px; }
.timeline-line { position:absolute; left:9px; top:6px; bottom:6px; width:2px; background:var(--jade-soft); }
.timeline-node { position:relative; margin-bottom:18px; }
.node-head { display:flex; align-items:center; gap:10px; background:var(--white); border:1.5px solid var(--paper-line);
  border-radius:var(--radius); padding:10px 14px; width:100%; text-align:left; min-height:44px; }
.node-dot { position:absolute; left:-28px; width:18px; height:18px; border-radius:50%; background:var(--jade-deep);
  display:flex; align-items:center; justify-content:center; font-size:10px; }
.node-year { font-weight:800; color:var(--jade-dark); font-size:13.5px; white-space:nowrap; }
.node-headline { font-weight:600; color:var(--ink); font-size:14.5px; }
.node-detail { display:none; margin:8px 0 0 0; padding:12px 14px; background:var(--cream-2);
  border-radius:var(--radius-sm); font-size:15px; line-height:1.7; }
.timeline-node.open .node-head { border-color:var(--jade-deep); background:var(--jade-pale); }
.timeline-node.open .node-detail { display:block; }
.timeline-node.open .node-dot { transform:scale(1.25); }
```
```javascript
// Cho phép mở nhiều node cùng lúc (khác Region Highlight — timeline không loại trừ lẫn nhau, học
// sinh có thể so sánh 2-3 mốc song song)
function toggleTimelineNode(btn) {
  btn.closest('.timeline-node').classList.toggle('open');
}
```

**⚠️ Bắt buộc:**
1. Timeline LUÔN dọc (kể cả desktop) — hợp mobile-first, không dùng timeline ngang.
2. Icon ở `.node-dot` dùng line-art đơn sắc (1 màu jade, cùng độ dày nét) — KHÔNG dùng icon màu mè/
   clipart nhiều màu khác nhau giữa các node.
3. Node mặc định thu gọn (chỉ hiện năm + headline ngắn); chạm để bung đoạn văn đầy đủ tương ứng —
   KHÔNG hiện sẵn hết mọi đoạn văn cùng lúc (sẽ mất tác dụng "dòng thời gian dẫn dắt").
4. Có thể mở nhiều node cùng lúc (không loại trừ lẫn nhau như Region Highlight 4.23) — mục đích khác
   nhau: Region Highlight so sánh CHỨC NĂNG các phần trong 1 lúc nhìn 1 phần; Timeline cho học sinh
   tự do so sánh nhiều mốc thời gian song song.
5. Đi kèm khuyến nghị (không bắt buộc kỹ thuật, nhưng nên có): 1 chân dung minh hoạ nhân vật
   (silhouette/flat-illustration, 1-2 màu phẳng theo bảng Cream/Jade, giữ 1-2 đặc điểm nhận diện tối
   giản, KHÔNG ảnh chụp thật/tả thực khuôn mặt) đặt ngay phía trên khối Timeline.

---

## 5. Mobile & Responsive — checklist

- [ ] Không có Task bar/`#progress-tracker` hay bất kỳ thanh theo dõi tiến trình nào hiển thị trên
      trang (đã bỏ hẳn — xem ghi chú tại Mục 4.1)
- [ ] `.phone`: `width:min(380px,92vw)` — không tràn ngang trên màn hình hẹp
- [ ] Vocabulary (4.4) desktop: `.vocab-grid` số cột co theo `data-count` (1-12 thẻ); mobile
      (≤640px): carousel vuốt ngang (`display:flex; overflow-x:auto; scroll-snap-type:x mandatory`),
      KHÔNG còn xếp lưới dọc — mũi tên `#vocabPrev/#vocabNext` chỉ hiện trên mobile, ẩn nếu ≤1 thẻ
- [ ] *(chỉ áp dụng khi gộp 1 file theo yêu cầu chủ động — xem Mục 8)* Bấm "Sang Luyện tập" (4.8) tự
      động Gom Top Panel lại — bài tập lọt màn hình ngay, không bắt học sinh cuộn thêm 1 lần nữa;
      với bản mặc định TÁCH 2 file, nút này không tồn tại (bỏ hẳn — xem ghi chú tại Mục 4.8)
- [ ] Practice Reference Pane (4.8b, nếu có): desktop chia đôi CHIỀU DỌC (2 cột, `grid-template-columns`
      ở ≥992px); mobile chia đôi CHIỀU NGANG (2 khối xếp chồng, `.practice-ref-pane` sticky trên,
      câu hỏi cuộn dưới); `.mobile-pane-controls` (Chia đôi/Bài đọc/Câu hỏi) chỉ hiện ≤991px và
      thật sự đổi được `max-height` của từng pane khi bấm
- [ ] Mọi nút (`chip-btn`, `level-tab`, `check-btn`, `audio-btn`, `top-tab`, `next-level-btn`,
      `vnav-btn`, `mpc-btn`, `pref-tab`, `q-nav-btn`...) ≥44px trên mobile
- [ ] `.match-wrap` 2 cột → 1 cột dưới 600px
- [ ] Before/After Slider (4.18, nếu có): `.comparison-container` có `touch-action:none`;
      `touchmove` đăng ký `{ passive:false }` và `handleMove` gọi `e.preventDefault()` khi
      `e.touches` tồn tại — đã **kéo thử bằng ngón tay trên điện thoại thật**, không chỉ DevTools
      responsive mode (chuột không lộ được lỗi cuộn trang này)
- [ ] Test ở 375px, 768px, 1280px

---

## 6. LMS & Athena Manifest

> Dùng đúng 1 contract cho MỌI file trong toàn hệ thống (Toán lẫn Tiếng Anh) — dán nguyên khối
> dưới đây, không viết khác đi. Nhúng đầy đủ ở đây (không chỉ tham chiếu file Toán) để file này
> dùng độc lập được khi chỉ upload 1 mình nó lên Antigravity/Claude.

**Ràng buộc sandbox (không được phá vỡ):** không gọi mạng ngoài `cdn.jsdelivr.net`,
`fonts.googleapis.com`, `fonts.gstatic.com`; không dùng `localStorage`/cookie — lưu qua
`LMS().state()`; 1 file HTML tự chứa, không build step/import/eval.

**Safe accessor** — dán đầu `<script>` đầu tiên:
```javascript
function LMS(){return window.AiducationLMS||{ready:function(){},progress:function(){},event:function(){},state:function(){},complete:function(){},resize:function(){}};}
```

**Athena Manifest** — dán trong `<head>`. `structure[].id` PHẢI khớp id thật đang dùng trong module
(không cố định `messages/vocab/practice/assess` — tuỳ cấu trúc thật đã chọn theo Mục 4.0):
```html
<script type="application/json" id="athena-context">
{
  "title": "...", "subject": "Tiếng Anh", "grade": "10",
  "objectives": ["...", "..."],
  "structure": [ { "id": "...", "title": "..." } ],
  "athenaGuidance": "..."
}
</script>
```

`athenaGuidance` phải liệt kê ĐỦ theo đúng 3 phần (a)(b)(c) như quy tắc gốc: (a) 1-2 câu module
dạy gì; (b) đánh số TỪNG câu hỏi/từ vựng kèm lựa chọn/nghĩa nguyên văn — với môn Tiếng Anh phải có
thêm **nghĩa của toàn bộ từ vựng/collocations** (không chỉ đáp án câu hỏi) vì Athena cần trả lời
được khi học sinh hỏi nghĩa 1 từ giữa chừng; (c) quy tắc đứng — không bao giờ lộ đáp án đúng.

**Progress + Events:**
```javascript
LMS().progress({ done, total });
LMS().event('answered', { id:'q2', chosen:'B', correct:false });
```

**Completion — bắn ĐÚNG 1 LẦN (guard bằng boolean):**
```javascript
LMS().complete({
  summary: "...", score: 0, max: 0,
  items: [ { id:"q1", prompt:"...", options:["A) …","B) …"], chosen:"...", correct:"...", isCorrect:true } ]
});
```
`items[]` build từ TOÀN BỘ câu học sinh đã làm ở mức đã chọn (chỉ làm mức Dễ → chỉ gồm câu mức Dễ).

**Live State + resume:**
```javascript
LMS().state({ activeTab:"Luyện tập", currentStep:3, totalSteps:5, answeredSoFar:{q1:"B",q2:null}, lastAction:"..." });
if (window.AiducationLMS) window.AiducationLMS.onResume = function(state){ /* áp lại state */ };
```

**Resize (tránh khoảng trắng thừa khi nhúng iframe LMS):**
```javascript
function reportHeight(){ LMS().resize({ height: document.documentElement.scrollHeight }); }
window.addEventListener('load', reportHeight);
const ro = new ResizeObserver(() => { clearTimeout(window._rz); window._rz = setTimeout(reportHeight, 100); });
ro.observe(document.body);
```
Đồng thời bỏ hẳn `body{min-height:100vh}`/`height:100vh` nếu có — chi tiết đầy đủ xem PHẦN 7 file
`02_design_toan_final_v2.md` (giống hệt, không có gì khác biệt riêng cho Tiếng Anh ngoài nội dung
`athenaGuidance` nêu trên).

---

## 7. Checklist trước khi giao file

- [ ] Không dùng font nào khác ngoài Be Vietnam Pro (kể cả heading)
- [ ] `body` có `font-size:18px` (không để mặc định trình duyệt)
- [ ] Không còn alias token cũ (`grep -n "var(--primary\|var(--surface)\|var(--bg)\|var(--text)\|var(--border)"`) — chỉ dùng tên token gốc
- [ ] Toàn bộ màu tra đúng bảng Mục 1 — không còn hex `#2F6F62`, `#E8623D`, `#E8A33D` gốc từ bản tham khảo
- [ ] Mỗi câu hỏi ở Mục 4.6 có `explain`, không câu nào chỉ báo đúng/sai suông
- [ ] Bài Matching: đã in bảng đối chiếu term↔định nghĩa theo `correctLetters` và đọc lại bằng mắt
      cho CẢ 3 mức độ — không chỉ mức Dễ (xem khung cảnh báo ở 4.6)
- [ ] Luyện tập chạy step-gate tuần tự (không hiện hết mọi dạng bài cùng lúc), và sau khi hoàn
      thành 1 mức có nút bấm thẳng sang mức còn lại (xem 4.5)
- [ ] Nếu bài có cả Hội thoại + Từ vựng: đã dùng Top Panel gộp có khoá tuần tự (4.8), không tách
      2 section xếp dọc tự do
- [ ] Nếu bài có chuỗi nhiều khối lý thuyết dài nối tiếp (Writing Hook → Khung tổng quát → Đi sâu
      từng phần → Phân tích bài mẫu...): đã dùng Auto-collapse Theory Block (4.22), không để tất cả
      hiện cùng lúc thành 1 trang dài vô hạn
- [ ] Nếu bài có brainstorm ý phân tầng (Writing Suggestion & Benefits...): đã dùng Idea Diagram
      (4.21) đúng 1 trong 4 `data-state`, không tự vẽ mindmap tự do bằng SVG/toạ độ JS
- [ ] Mỗi tin nhắn (4.3) vẽ đủ **avatar + tên người nói + giờ**, avatar có ở CẢ typing-indicator,
      nhánh "hiện hết tin nhắn" và Reference Pane (4.8b) — không chỉ bong bóng + giờ; tên/hình
      nhân vật lấy từ đúng 1 map `speaker` + `avatarHTML()`, không viết cứng rải rác
- [ ] Vocabulary (4.4) không quá 12 thẻ trong 1 carousel; mobile chuyển đúng sang carousel vuốt
      ngang có mũi tên, desktop vẫn là lưới bình thường (không carousel hoá desktop)
- [ ] Thẻ từ vựng có class `.settled` chống mờ chữ (4.4), và đã **mở bằng điện thoại thật** kiểm:
      chữ trên thẻ sắc nét như chữ ngoài thẻ; bấm lật **CẢ 2 CHIỀU** (trước→sau và sau→trước) đều
      còn đủ hiệu ứng xoay — mất hiệu ứng chỉ lộ ở chiều lật ngược, nghiệm thu 1 chiều sẽ sót
- [ ] MỌI thẻ từ vựng đều có sẵn ô `img: ''` kèm comment chỉ chỗ dán link (kể cả khi đã vẽ `illus`),
      và mọi link `img` đã điền đều thuộc 3 dạng sandbox cho phép (`data:` URI / `cdn.jsdelivr.net` /
      đường dẫn tương đối) — link Drive/Imgur xem trên máy vẫn thấy nhưng nhúng LMS sẽ bị chặn
- [ ] Nếu Luyện tập gắn với bài học/Reading phía trên: đã thêm Practice Reference Pane (4.8b) —
      desktop chia đôi theo chiều dọc, mobile chia đôi theo chiều ngang kèm nút chuyển chế độ xem
      (Chia đôi/Bài đọc/Câu hỏi); nếu Luyện tập KHÔNG gắn bài học nào → đã bỏ hẳn 4.8b, không nhét
      Reference Pane trống cho có
- [ ] Nội dung trong Reference Pane (4.8b) lấy đúng từ data của Khối 1 (`messages`/`vocab`/đoạn
      Reading), không soạn lại data riêng gây lệch nội dung giữa 2 khối
- [ ] Không có Task bar/`#progress-tracker` hay component tương tự nào trong file; `LMS().progress()`
      vẫn được gọi ngầm trong code khi học sinh hoàn thành từng phần (không cần UI riêng)
- [ ] Hero (nếu có) ẩn được bằng `display:none` không gãy JS
- [ ] Không dùng kéo-thả (drag-and-drop) — bài nối/sắp xếp/phân loại dùng tap-to-select
      (Mục 4.12/4.13/4.17). Ngoại lệ Before/After Slider (4.18, nếu có) đã đúng chuẩn
      `touch-action:none` + `preventDefault()`/`passive:false` — xem checklist Mục 5
- [ ] Mọi MCQ/Matching đã xáo vị trí đáp án đúng khi render bằng hàm dùng chung (Mục 0 nguyên tắc
      7, `shuffleMCQOptions()` ở Mục 4.6) — không gán cứng đáp án đúng lệch về 1 vị trí quen tay
- [ ] Nếu có dùng Vietnamese Translation Toggle (4.19): chỉ đặt ở đoạn hướng dẫn/mô tả dài, KHÔNG
      đặt ở câu hỏi/đề bài (câu hỏi luôn thuần tiếng Anh); mỗi `id` của `.vi-text` duy nhất trong
      toàn file; chuỗi JS chứa dấu nháy đơn (don't/isn't/you'll...) đã escape `\'` đúng cách
- [ ] File là 1 module độc lập, không có sidebar/header/Task bar điều hướng hay theo dõi tiến trình
      nào trong 1 file
- [ ] Đạt checklist Mobile ở Mục 5 và checklist LMS ở PHẦN 7 file Toán

---

## 8. Tách 1 module thành nhiều file HTML — Lesson file + Practice file

> **Mặc định v1.2 (không nói gì thêm): LUÔN tách 2 file** — `..._lesson.html` (Khối 1) và
> `..._practice.html` (Khối 2 + Reference Pane 4.8b bắt buộc). Đây là đổi ngược lại so với v1.1 (khi
> đó mặc định 1 file, tách là ngoại lệ) — lý do: kịch bản từ `01_scenario_builder_tienganh_v2.md`
> giờ tự chia sẵn PHẦN 1/PHẦN 2, và việc tách file giúp học sinh mobile không phải tải/cuộn 1 trang
> quá dài. **Chỉ gộp lại 1 file duy nhất khi người dùng CHỦ ĐỘNG yêu cầu** (VD "gộp lại 1 file",
> "không cần tách file lần này") — khi đó bỏ Reference Pane 4.8b, dùng thẳng nội dung Khối 1 đã có
> sẵn trên cùng trang.
>
> **Ngoại lệ v1.3 — module không có Khối 1 (kịch bản đánh dấu "bỏ PHẦN 1"):** ví dụ đã gặp là
> Grammar — lý thuyết được build sẵn ở sản phẩm/pipeline khác, kịch bản chỉ có PHẦN 2 — PRACTICE.
> Khi đó **build đúng 1 file Practice duy nhất**, KHÔNG tạo file Lesson rỗng chỉ để giữ quy ước 2
> file. File Practice này cũng KHÔNG có Reference Pane (xem ghi chú "BẮT BUỘC, trừ ngoại lệ" ở
> 4.8b) vì không có Khối 1 nào để tham chiếu lại.

### 8.1 Cách chia — đúng ranh giới 2 khối đã nêu ở Mục 3

- **File 1 — Lesson** (`..._lesson.html` hoặc tên tương đương): `header.hero` (nếu có) + Khối 1
  (Top Panel 4.8: Phone Chat 4.3 + Vocabulary 4.4, hoặc Reading Passage 4.10). KHÔNG có Luyện tập.
- **File 2 — Practice** (`..._practice.html`): Khối 2 (Level Tabs 4.5 + Practice Reference Pane
  4.8b nếu có + Self-assessment 4.7 + Finale). KHÔNG có Hội thoại/Vocabulary gốc (chỉ có bản
  tham chiếu read-only trong 4.8b nếu cần).

### 8.2 5 vấn đề thật sự phát sinh khi tách — và cách xử lý

1. **Dữ liệu `messages`/`vocab` phải trùng lặp ở CẢ 2 file.** Sandbox không cho `import`/build step
   (xem ràng buộc ở Mục 6), nên Practice Reference Pane (4.8b) ở File 2 không thể "gọi lại" data từ
   File 1 — phải copy y nguyên mảng `messages`/`vocab` sang File 2. Bắt buộc đánh dấu bằng comment
   `// ĐỒNG BỘ với file Lesson — sửa nội dung phải sửa CẢ 2 nơi` ngay trên khai báo mảng ở cả 2 file,
   để người sau maintain không sửa lệch 1 bên.
2. **Khoá tuần tự (4.8) KHÔNG hoạt động xuyên file.** Biến `vocabUnlocked`/`practiceUnlocked` chỉ
   tồn tại trong phiên DOM của 1 file — File 2 mở lên không biết học sinh đã đọc hết File 1 chưa.
   3 phương án, chọn 1 theo yêu cầu thực tế của bài (mặc định dùng phương án a nếu không nói gì):
   - **(a) Bỏ khoá cứng (khuyến nghị mặc định):** File 2 hiện Luyện tập ngay khi mở, không lock —
     hợp lý vì trong LMS, File 1 và File 2 thường đã tự nằm ở 2 bước riêng trong lộ trình học (học
     sinh không thể mở File 2 ngoài ý muốn trước File 1 nếu nền tảng đã sắp xếp thứ tự bước).
   - **(b) Dựa vào `LMS().state()` của nền tảng thật:** CHỈ dùng nếu đã xác nhận với đội LMS rằng
     state được lưu chung theo học sinh + đọc được xuyên nhiều file/module (không phải mặc định của
     mọi nền tảng) — không tự ý giả định, dễ tạo khoá "chết" nếu nền tảng không hỗ trợ.
   - ~~(c) Banner nhắc nhẹ~~ — **ĐÃ BỎ.** Bản trước dùng banner "Đã đọc hết Bài học ở phần trước
     chưa? [Quay lại Bài học →]" — banner này chứa 1 link ngược sang File Lesson nên vi phạm quy
     tắc mới "không liên kết Lesson ↔ Practice" (xem điểm 3 ngay dưới). Không dùng lại phương án
     này dưới bất kỳ hình thức nào, kể cả không phải hard-lock.
3. **KHÔNG có nút/link điều hướng nào giữa 2 file (đổi so với bản trước).** File 1 không còn nút
   "Sang Luyện tập" trỏ sang File 2 (`location.href='...'`/thẻ `<a>`); File 2 không còn nút/banner
   "Quay lại Bài học" trỏ ngược sang File 1. Mỗi file kết thúc/bắt đầu tự nhiên bằng nội dung của
   chính nó — học sinh chuyển bước qua danh sách bài học của nền tảng LMS, không qua nút trong bài.
   (Ghi chú: hành vi trong-trang `switchTopView`/`toggleTopPanel` ở bản 1-file — khi KHÔNG tách file
   theo yêu cầu chủ động của người dùng — không thuộc phạm vi quy tắc này vì đó là cuộn/gom trong
   cùng 1 trang, không phải điều hướng sang file khác.)
4. *(đã gộp vào ghi chú Task bar ở Mục 4.1 — không còn nội dung riêng ở đây, xem lý do bỏ hẳn
   `#progress-tracker` tại vị trí Mục 4.1.)*
5. **`LMS().complete()` chỉ bắn ở File 2** (nơi thật sự chấm điểm) — File 1 chỉ gọi
   `LMS().progress()`/`LMS().event()` khi đọc xong tin nhắn/lật xong thẻ, KHÔNG gọi `complete()` vì
   chưa có gì để chấm. Athena Manifest cũng tách 2 bản riêng theo đúng `structure[]` của từng file,
   nhưng `athenaGuidance` của CẢ 2 file vẫn nên liệt kê đủ nghĩa từ vựng (File 1 để trả lời khi học
   từ, File 2 để trả lời khi học sinh hỏi lại nghĩa từ lúc đang làm bài) — vì Athena không đọc được
   manifest của file kia.

### 8.3 Checklist riêng khi tách file (thêm vào Mục 7)

- [ ] `messages`/`vocab` giống hệt nhau ở 2 file, có comment "ĐỒNG BỘ" đánh dấu
- [ ] Đã chọn 1 trong 2 phương án khoá tuần tự còn hiệu lực ở 8.2 mục 2 (a hoặc b — phương án (c)
      banner đã bỏ vì chứa link ngược sang File Lesson, vi phạm quy tắc không liên kết 2 file)
- [ ] **Không có bất kỳ nút/link nào điều hướng giữa 2 file** — không còn `location.href=`, thẻ
      `<a href="..._practice.html">`/`<a href="..._lesson.html">`, hay các hàm chỉ có nghĩa trong
      bản 1-file (`switchTopView`, `toggleTopPanel`, `goToPractice`) bị sót lại khi tách file
- [ ] Không có Task bar/`#progress-tracker` ở bất kỳ file nào (đã bỏ hẳn — xem Mục 4.1)
- [ ] `LMS().complete()` chỉ xuất hiện đúng 1 lần, ở File 2

---

## PHẦN 9 — BỔ SUNG (v1.1 — đối chiếu với bộ Prompt Template sinh nội dung)

> Toàn bộ mục này bổ sung/ghi đè lên PHẦN 1 phía trên khi có xung đột — không xoá nội dung cũ, chỉ thêm/làm rõ hơn.

### 9.1 Thống nhất thuật ngữ: LUÔN dùng "Difficult", không dùng "Hard"

Toàn bộ hệ thống (9 module Practice lẫn Extended Practice của Revision) giờ dùng thống nhất **Easy /
Medium / Difficult** — đã sửa Mục 4.5 và 4.16 phía trên (`level-tab`, `levelLabel`, `levelOrder`).
Nếu thấy bất kỳ chỗ nào trong kịch bản/file nguồn còn ghi "Hard" (từ bản Master Prompt Revision cũ),
**tự động đổi thành "Difficult"** khi build — không hỏi lại, không giữ nguyên "Hard" theo đúng chữ
trong file nguồn.

### 9.2 Không có gợi ý (hint); đáp án LUÔN tiếng Anh, chỉ "Giải thích" mới được tiếng Việt

> ⚠️ Áp dụng cho MỌI component có câu hỏi (4.6, 4.11, 4.12, 4.13, 4.16, 4.17) — quy tắc cứng, không
> có ngoại lệ theo module.

- **KHÔNG hiển thị bất kỳ gợi ý (hint) nào trước khi học sinh trả lời** — không có nút "Xem gợi ý",
  không có chữ mờ placeholder gợi đáp án, không tự động bôi đậm từ khoá trong câu hỏi để "gợi ý".
  Học sinh chỉ có đúng 2 trạng thái: CHƯA trả lời (không thông tin thêm) → ĐÃ trả lời (hiện đáp án +
  giải thích).
- **Đáp án (`ans`/`correctText`/nội dung field đáp án đúng) LUÔN LUÔN là tiếng Anh** — dù câu hỏi
  thuộc module nào. Không dịch đáp án sang tiếng Việt, không viết đáp án song ngữ.
- **Text hiển thị của MỌI lựa chọn MCQ, câu True/False, ô nhập Gap-fill, thẻ Matching (cả 2 cột)**
  đều phải tiếng Anh — không lẫn tiếng Việt vào bất kỳ đâu trong nội dung câu hỏi/lựa chọn.
- **CHỈ field `explain` được phép tiếng Việt** (và chỉ hiện SAU khi học sinh đã trả lời — không hiện
  trước, không hiện cùng lúc với câu hỏi).
- Khi component nhận dữ liệu từ file nguồn: nếu phát hiện field câu hỏi/lựa chọn/đáp án có tiếng
  Việt xen vào, đó là lỗi dữ liệu nguồn — build đúng phần tiếng Anh có sẵn, KHÔNG tự dịch giúp,
  KHÔNG tự bịa thêm bản tiếng Anh thay thế.

### 9.3 Tô đậm & gạch chân từ vựng trong Reading Passage / Phone Chat — 2 quy ước KHÁC NHAU

Nội dung nguồn (file Word từ Prompt Template) đánh dấu chữ theo 2 cách có **ý nghĩa khác nhau** —
không được gộp chung 1 kiểu hiển thị:

| Đánh dấu trong file Word | Ý nghĩa | Cách hiển thị trong HTML |
|---|---|---|
| **Chữ đậm** (`**word**`/`<strong>`) | Từ vựng/collocation CHÍNH THỨC đang dạy trong bài (đã có trong Flashcard/Vocabulary) | `font-weight:700` rõ ràng, có thể kèm nền màu nhạt (`.vocab-bold`, xem CSS dưới) — LUÔN hiện đậm ngay từ đầu, không cần tap mới thấy |
| _Chữ gạch chân_ (`<u>word</u>`) | Từ được đánh dấu riêng trong file Word (thường là từ MỚI học sinh cần đoán nghĩa qua ngữ cảnh — dạng bài "Guess meaning from context" — KHÁC với từ vựng chính đang dạy) | `text-decoration: underline` thật, KHÔNG tô nền màu, KHÔNG lẫn với kiểu tap-tooltip của `.kw` (4.10) |

> ⚠️ **Không được biến cả 2 loại thành cùng 1 kiểu `.kw` tap-để-hiện-nghĩa như bản gốc Mục 4.10.**
> `.kw` (tap-tooltip, viền chấm) chỉ nên dùng cho trường hợp bài yêu cầu tương tác "chạm để xem
> nghĩa" — còn khi file nguồn đã ghi rõ đậm/gạch chân, đó là 2 tín hiệu trực quan TĨNH, hiện sẵn
> luôn, không cần chạm.

```css
/* Từ vựng/collocation chính thức — đậm + nền nhạt, không cần tap */
.vocab-bold { font-weight: 700; color: var(--jade-text); background: var(--jade-pale);
  padding: 1px 5px; border-radius: 6px; }
.msg-row.right .vocab-bold { background: rgba(255,255,255,.22); color: #fff; } /* trên nền jade-deep của tin nhắn bên phải */

/* Từ được đánh dấu gạch chân riêng trong file Word (VD: target của Guess meaning from context) */
.vocab-underline { text-decoration: underline; text-decoration-color: var(--accent);
  text-decoration-thickness: 2px; text-underline-offset: 2px; font-weight: 600; }
```

```javascript
// Khi parse nội dung từ file nguồn: giữ nguyên 2 thẻ `<strong>`/`<b>` (-> map class .vocab-bold)
// và `<u>` (-> map class .vocab-underline) nếu đã có sẵn trong text. KHÔNG tự ý thêm bold/underline
// cho từ mà file nguồn không đánh dấu, và KHÔNG bỏ sót từ đã đánh dấu (rà lại toàn bộ Reading
// Passage/Phone Chat trước khi build, đối chiếu đúng danh sách từ vựng ở Kế hoạch).
// esc() vẫn áp dụng cho phần TEXT thuần, không áp cho các thẻ <strong>/<u> đã chủ động giữ lại —
// đúng nguyên tắc ở Mục 0.8 (ngoại lệ field đã chủ động chứa markup).
```

Mục 4.10 (Reading Passage) cập nhật: thêm `font-weight:700` cho `.kw` nếu bản thân từ đó VỪA là từ
vựng chính thức VỪA cần tap xem nghĩa (2 quy ước có thể chồng nhau trên cùng 1 từ) —
`class="kw vocab-bold"` dùng chung được.

### 9.4 Component mới — Ghi âm & nộp cho AI chấm (Pronunciation Read Aloud, Speaking Shadowing/Production)

> Dùng `MediaRecorder` API — cần xin quyền micro. Ghi rõ trong UI lý do xin quyền, không bật ẩn.

```html
<div class="record-box" id="recordBox">
  <div class="record-target">[câu/đoạn cần đọc — có thể có .vocab-bold]</div>
  <div class="record-controls">
    <button class="rec-btn" id="btnRecord" aria-label="Bắt đầu ghi âm">🎙️ Ghi âm</button>
    <button class="rec-btn stop" id="btnStopRecord" style="display:none;" aria-label="Dừng ghi âm">⏹ Dừng</button>
    <span class="rec-timer" id="recTimer">00:00</span>
  </div>
  <div class="record-playback" id="recPlayback" style="display:none;">
    <audio id="recAudio" controls></audio>
    <button class="chip-btn ghost" id="btnReRecord">↺ Ghi lại</button>
    <button class="chip-btn" id="btnSubmitRecord">✓ Nộp bài</button>
  </div>
  <div class="record-feedback" id="recFeedback" style="display:none;"></div>
</div>
```
```css
.record-box { background:var(--white); border:2px solid var(--cream-2); border-radius:var(--radius-lg);
  padding:20px; text-align:center; }
.record-target { font-size:16px; font-weight:600; color:var(--ink); margin-bottom:16px; line-height:1.6; }
.record-controls { display:flex; align-items:center; justify-content:center; gap:14px; }
.rec-btn { background:var(--accent); color:#fff; border:none; border-radius:999px; padding:12px 24px;
  font-weight:700; font-size:14px; min-height:48px; display:inline-flex; align-items:center; gap:8px; }
.rec-btn.stop { background:var(--wrong); }
.rec-btn:disabled { background:var(--sage); }
.rec-timer { font-size:13px; font-weight:700; color:var(--ink-2); font-variant-numeric:tabular-nums; }
.record-playback { margin-top:16px; display:flex; align-items:center; justify-content:center; gap:10px; flex-wrap:wrap; }
.record-feedback { margin-top:14px; text-align:left; background:var(--cream-2); border-radius:var(--radius);
  padding:14px 16px; font-size:13.5px; color:var(--ink-2); }
.record-feedback.pending::before { content:"⏳ Đang chấm..."; display:block; font-weight:700; color:var(--accent-text); }
```
```javascript
let mediaRecorder, audioChunks = [], recStartTime;

async function startRecording() {
  const stream = await navigator.mediaDevices.getUserMedia({ audio: true }); // xin quyền micro NGAY LÚC bấm, không xin trước
  mediaRecorder = new MediaRecorder(stream);
  audioChunks = [];
  mediaRecorder.ondataavailable = e => audioChunks.push(e.data);
  mediaRecorder.onstop = () => {
    const blob = new Blob(audioChunks, { type: 'audio/webm' });
    document.getElementById('recAudio').src = URL.createObjectURL(blob);
    document.getElementById('recPlayback').style.display = 'flex';
    stream.getTracks().forEach(t => t.stop()); // tắt hẳn mic sau khi dừng, không giữ quyền chạy ngầm
  };
  mediaRecorder.start();
  recStartTime = Date.now();
  document.getElementById('btnRecord').style.display = 'none';
  document.getElementById('btnStopRecord').style.display = 'inline-flex';
  tickTimer();
}
function tickTimer() {
  if (mediaRecorder?.state !== 'recording') return;
  const s = Math.floor((Date.now() - recStartTime) / 1000);
  document.getElementById('recTimer').textContent = `${String(Math.floor(s/60)).padStart(2,'0')}:${String(s%60).padStart(2,'0')}`;
  requestAnimationFrame(tickTimer);
}
function stopRecording() {
  mediaRecorder.stop();
  document.getElementById('btnStopRecord').style.display = 'none';
  document.getElementById('btnRecord').style.display = 'inline-flex';
}
function submitRecording() {
  // Gửi blob lên endpoint chấm AI của nền tảng (endpoint thật do đội backend cung cấp — không tự
  // bịa API). Trong lúc chờ: hiện .record-feedback.pending; nhận kết quả xong: đổi nội dung feedback
  // + gọi markDone()/LMS().event('recorded', {...}) tương ứng.
  const fb = document.getElementById('recFeedback');
  fb.style.display = 'block'; fb.classList.add('pending'); fb.textContent = '';
  // await fetch(...) -> fb.classList.remove('pending'); fb.innerHTML = "..."; 
}
document.getElementById('btnRecord').addEventListener('click', startRecording);
document.getElementById('btnStopRecord').addEventListener('click', stopRecording);
document.getElementById('btnReRecord').addEventListener('click', () => {
  document.getElementById('recPlayback').style.display = 'none';
  document.getElementById('recFeedback').style.display = 'none';
});
document.getElementById('btnSubmitRecord').addEventListener('click', submitRecording);
```

> Nếu nền tảng LMS chưa có endpoint chấm giọng nói thật, để `submitRecording()` ở dạng khung placeholder,
> ghi rõ comment `// TODO: nối API chấm giọng nói của nền tảng` — KHÔNG tự bịa kết quả chấm giả.

### 9.5 Component mới — Sắp xếp cấp ĐOẠN (paragraph/chunk ordering, khác 4.13 cấp từ)

> Dùng cho "Phần Sắp xếp" của Revision Unit Check (sắp xếp 5 phần email/hội thoại) và các bài Reading
> cần sắp xếp đoạn văn. Tap theo đúng thứ tự muốn xếp — không kéo-thả.

```html
<div class="chunk-bank" id="chunkBank"></div>
<div class="chunk-answer" id="chunkAnswer"></div>
<div class="chunk-controls">
  <button class="chip-btn ghost" onclick="resetChunks()">↺ Làm lại</button>
  <button class="chip-btn" id="btnCheckChunks" disabled>Kiểm tra</button>
</div>
```
```css
.chunk-bank, .chunk-answer { display:flex; flex-direction:column; gap:10px; min-height:60px;
  padding:12px; border-radius:var(--radius); margin-bottom:12px; }
.chunk-bank { background:var(--cream-2); }
.chunk-answer { border:2px dashed var(--paper-line-2); background:var(--white); }
.chunk-tile { display:flex; align-items:flex-start; gap:10px; padding:12px 16px; border-radius:var(--radius);
  border:1.5px solid var(--paper-line); background:var(--white); font-size:15px; line-height:1.55;
  color:var(--ink); cursor:pointer; min-height:44px; }
.chunk-tile:hover { border-color:var(--accent); }
.chunk-tile.placed { opacity:.35; pointer-events:none; }
.chunk-answer .chunk-tile { background:var(--jade-pale); border-color:var(--jade-soft); cursor:default; }
.chunk-order-num { flex:0 0 auto; width:26px; height:26px; border-radius:50%; background:var(--jade-deep);
  color:#fff; font-weight:800; font-size:12.5px; display:flex; align-items:center; justify-content:center; }
.chunk-result-row { display:flex; gap:8px; align-items:center; margin-top:4px; }
.chunk-result-row.correct { color:var(--jade-text); } .chunk-result-row.wrong { color:var(--wrong); }
```
```javascript
// chunks: [{ id, text /* có thể chứa .vocab-bold đã dựng sẵn */ }] — thứ tự ĐÚNG là thứ tự trong
// mảng; xáo vị trí hiển thị ở chunkBank khi render (nguyên tắc 7, Mục 0).
const chunks = [ /* ...5 phần email/hội thoại... */ ];
let placedOrder = [];

function renderChunkBank() {
  const shuffled = [...chunks].sort(() => Math.random() - 0.5);
  chunkBank.innerHTML = '';
  shuffled.forEach(c => {
    const el = document.createElement('div');
    el.className = 'chunk-tile'; el.dataset.id = c.id;
    el.innerHTML = c.text; // text đã dựng sẵn markup (.vocab-bold...), không esc() lại ở đây
    el.addEventListener('click', () => placeChunk(c.id, el));
    chunkBank.appendChild(el);
  });
}
function placeChunk(id, bankEl) {
  bankEl.classList.add('placed');
  placedOrder.push(id);
  const c = chunks.find(x => x.id === id);
  const row = document.createElement('div');
  row.className = 'chunk-tile';
  row.innerHTML = `<span class="chunk-order-num">${placedOrder.length}</span><div>${c.text}</div>`;
  chunkAnswer.appendChild(row);
  document.getElementById('btnCheckChunks').disabled = placedOrder.length !== chunks.length;
}
function resetChunks() {
  placedOrder = []; chunkAnswer.innerHTML = '';
  document.getElementById('btnCheckChunks').disabled = true;
  renderChunkBank();
}
document.getElementById('btnCheckChunks').addEventListener('click', () => {
  const correctOrder = chunks.map(c => c.id);
  const isCorrect = JSON.stringify(placedOrder) === JSON.stringify(correctOrder);
  // Hiện kết quả đúng/sai theo TỪNG vị trí (không chỉ đúng/sai cả bài) — học sinh biết đoạn nào lệch:
  Array.from(chunkAnswer.children).forEach((row, i) => {
    row.classList.add(placedOrder[i] === correctOrder[i] ? 'correct' : 'wrong');
  });
  if (isCorrect) markDone('practice'); // hoặc key tương ứng dạng bài đang dùng
  // explain tổng (bắt buộc, Mục 0 nguyên tắc 5): hiện lý do thứ tự đúng ngay dưới, ví dụ giải thích
  // mốc liên kết đã dùng để xác định thứ tự (xem field `explainOrder` trong data nếu có).
});
renderChunkBank();
```

### 9.6 Component mới — Writing: nộp bài & phản hồi rubric AI

> Bổ sung cho Mục 4.15 (hiện chỉ có `<textarea>` + đếm từ, chưa có luồng nộp bài).

```html
<textarea class="write-area" id="writeArea" placeholder="Viết bài của bạn ở đây..." oninput="trackWriting()"></textarea>
<div class="write-footer">
  <div class="word-count" id="wordCount">0 từ / mục tiêu [X]-[Y] từ</div>
  <button class="chip-btn" id="btnSubmitWriting">✓ Nộp bài</button>
</div>
<div class="write-feedback" id="writeFeedback" style="display:none;">
  <div class="rubric-grid" id="rubricGrid"></div>
  <div class="write-comment" id="writeComment"></div>
</div>
```
```css
.write-footer { display:flex; justify-content:space-between; align-items:center; margin-top:8px; gap:10px; flex-wrap:wrap; }
.write-feedback { margin-top:16px; background:var(--white); border:2px solid var(--jade-soft);
  border-radius:var(--radius-lg); padding:18px; }
.rubric-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(160px,1fr)); gap:10px; margin-bottom:14px; }
.rubric-item { background:var(--cream-2); border-radius:var(--radius); padding:10px 12px; text-align:center; }
.rubric-item .rlabel { font-size:11px; color:var(--ink-2); font-weight:700; text-transform:uppercase; }
.rubric-item .rscore { font-size:22px; font-weight:800; color:var(--jade-dark); margin-top:2px; }
.rubric-item .rscore small { font-size:12px; color:var(--ink-3); font-weight:600; }
.write-comment { font-size:14px; color:var(--ink-2); line-height:1.6; background:var(--cream-2);
  border-radius:var(--radius); padding:12px 14px; }
```
```javascript
// Rubric 4 tiêu chí cố định — đúng khớp Prompt Template Writing: Task Achievement / Organisation /
// Language Use / Length & Fluency, thang 1-4 mỗi tiêu chí.
function renderRubric(scores /* {task:3, org:4, lang:2, length:3} */, commentVi) {
  const labels = { task:'Task Achievement', org:'Organisation', lang:'Language Use', length:'Length & Fluency' };
  document.getElementById('rubricGrid').innerHTML = Object.entries(scores).map(([k,v]) =>
    `<div class="rubric-item"><div class="rlabel">${labels[k]}</div><div class="rscore">${v}<small>/4</small></div></div>`
  ).join('');
  document.getElementById('writeComment').textContent = commentVi; // nhận xét AI — TIẾNG VIỆT, đúng quy tắc 9.2
  document.getElementById('writeFeedback').style.display = 'block';
}
document.getElementById('btnSubmitWriting').addEventListener('click', () => {
  const text = document.getElementById('writeArea').value.trim();
  if (!text) return;
  // await fetch(...) tới endpoint chấm Writing của nền tảng, nhận về {scores, commentVi} rồi renderRubric(...)
  // TODO: nối API chấm Writing thật — KHÔNG tự bịa điểm/nhận xét giả khi chưa có endpoint.
});
```

### 9.7 `diagQuestions` (4.16) — bổ sung trục MỨC ĐỘ, phục vụ Proficiency Assessment

> Bản gốc Mục 4.16 chỉ phân loại theo `cat` (kỹ năng). Cần thêm trục `level` (NB/TH/VD) để hệ thống
> tổng hợp đúng "Proficiency Assessment" như Prompt Template Revision yêu cầu — biết học sinh yếu
> ở ĐÚNG kỹ năng NÀO, ĐÚNG mức độ NÀO, không chỉ yếu kỹ năng chung chung.

```javascript
const diagQuestions = [
  { cat:'vocab',    level:'nb', q:'...', /* options, answer, explain... */ },
  { cat:'grammar',  level:'th', q:'...', /* ... */ },
  { cat:'reading',  level:'vd', q:'...', /* ... */ },
  { cat:'ordering', level:'vd', q:'...', /* Phần Sắp xếp — luôn level:'vd' theo đúng quy tắc Prompt */ },
];
function scoreByCategoryAndLevel(answered) {
  const byCat = {}, byLevel = {};
  diagQuestions.forEach((q, i) => {
    byCat[q.cat] = byCat[q.cat] || { ok:0, total:0 };
    byLevel[q.level] = byLevel[q.level] || { ok:0, total:0 };
    byCat[q.cat].total++; byLevel[q.level].total++;
    if (answered[i]?.isCorrect) { byCat[q.cat].ok++; byLevel[q.level].ok++; }
  });
  return { byCat, byLevel };
  // LMS().complete({...}) nên gửi kèm cả 2 object này trong `summary`/field riêng, để backend tổng
  // hợp Proficiency Assessment mà không cần tính lại từ items[] thô.
}
```
```html
<div class="cat-badges" id="catBadges"></div>
<div class="cat-badges" id="levelBadges"></div>
```
```javascript
const catLabel = { vocab:'📘 Vocab', grammar:'📗 Grammar', reading:'📕 Reading', ordering:'🔀 Ordering' };
const levelLabelVN = { nb:'Nhận biết', th:'Thông hiểu', vd:'Vận dụng' };
function renderBadges(byCat, byLevel) {
  document.getElementById('catBadges').innerHTML = Object.entries(byCat).map(([k,v]) =>
    `<span class="badge ${v.ok/v.total < 0.7 ? 'weak' : 'strong'}">${catLabel[k]}: ${v.ok}/${v.total}</span>`).join('');
  document.getElementById('levelBadges').innerHTML = Object.entries(byLevel).map(([k,v]) =>
    `<span class="badge ${v.ok/v.total < 0.7 ? 'weak' : 'strong'}">${levelLabelVN[k]}: ${v.ok}/${v.total}</span>`).join('');
}
```

### 9.8 Nhãn `[Mức độ · Dạng bài]` từ file Word nguồn — LUÔN loại bỏ khi build HTML

> ⚠️ Mọi Prompt Template sinh nội dung đều có nhãn dạng `[Nhận biết · Matching từ – nghĩa]` in ngay
> phía trên mỗi câu hỏi TRONG FILE WORD (để giáo viên kiểm duyệt) — đây là quy tắc bắt buộc ở phía
> soạn nội dung, KHÔNG liên quan đến hiển thị cho học sinh.

**Khi build HTML từ nội dung có sẵn nhãn này: tự động lược bỏ hoàn toàn, không hỏi lại, không giữ
lại dưới bất kỳ hình thức nào** (không hiện chữ, không hiện badge, không hiện trong `data-*`/tooltip
lộ ra ngoài DOM mà học sinh xem được). Nhãn chỉ dùng NỘI BỘ khi map câu hỏi vào đúng `cat`/`level`
ở Mục 9.7 lúc parse dữ liệu — sau khi map xong thì bỏ, không đưa vào bất kỳ chỗ nào của HTML output.

### 9.10 Nhãn kỹ thuật nội bộ nói chung (`level`/`cat`/`skill`...) — LUÔN ẩn khỏi HTML, KHÁC hướng
dẫn thao tác (LUÔN phải hiện)

> Tổng quát hoá Mục 9.8 — không chỉ nhãn `[Mức độ · Dạng bài]`, mà **MỌI nhãn/tag dùng để phân loại
> câu hỏi nội bộ** đều theo đúng 1 quy tắc: dữ liệu giữ lại để component chấm đúng nhóm, nhưng KHÔNG
> BAO GIỜ lộ ra bất kỳ đâu học sinh nhìn thấy (không text, không badge, không tooltip, không
> `data-*` lộ trong DOM). Ví dụ đã gặp thật: `level` (easy/medium/difficult), `cat` (nhan_biet/
> thong_hieu/van_dung), và mới nhất — **`skill`** (main_idea/detail ở Unit 2 Reading, dùng để rải
> đúng tỉ lệ câu hỏi theo từng kỹ năng nhưng học sinh không cần biết câu nào "thuộc loại" gì).

**⚠️ PHÂN BIỆT QUAN TRỌNG — dễ nhầm lẫn giữa 2 loại nội dung trong kịch bản:**

| Loại | Ví dụ | Có hiện trong HTML không? |
|---|---|---|
| **Nhãn/tag phân loại nội bộ** | `level: easy`, `cat: thong_hieu`, `skill: main_idea` | ❌ KHÔNG BAO GIỜ — chỉ dùng để code chấm đúng nhóm/rải đúng tỉ lệ |
| **Tên kỹ năng trong Strategy Reveal** | "Reading for Specific Information", bảng so sánh Main Idea vs Details (Mục 9.12) | ✅ CÓ — đây là nội dung dạy học sinh, không phải nhãn phân loại |
| **Câu hướng dẫn thao tác** | "Tap the sentence that gives real evidence.", "Tap an item first, then tap the correct bin." | ✅ BẮT BUỘC CÓ — xem Mục 9.14, KHÔNG được bỏ dù có vẻ "tự nhiên đoán ra được" |

Khi đọc kịch bản, tự hỏi đúng 2 câu để phân loại 1 dòng text: *(1) Dòng này có tồn tại chỉ để giáo
viên/hệ thống phân loại câu hỏi không, hay là nội dung học sinh cần đọc để hiểu/làm bài?* → nếu là
(1) thì ẩn; nếu là nội dung cần đọc thì LUÔN hiện, kể cả khi nó "nghe giống nhãn" (VD tên kỹ năng
"Main Idea" xuất hiện *trong* Strategy Reveal là nội dung dạy, không phải nhãn ẩn — chỉ riêng field
`skill: main_idea` gắn ở dữ liệu câu hỏi Practice mới là nhãn ẩn).

### 9.11 Reveal Từ Vựng 2 Tầng (Core/Support) + Nghĩa Song Ngữ Bắt Buộc

> Đúc kết từ Unit 1 + Unit 2 Reading — chuẩn hoá thành component dùng lại được cho mọi Unit sau.
> Code kỹ thuật đầy đủ (data structure, CSS 2 style) ở `03_engine_tiengAnh.md` mục 1.15 — mục này
> chỉ nêu QUY TẮC THIẾT KẾ, không lặp code.

- **MỌI popup nghĩa từ vựng** (kể cả từ vựng chính thức của bài lẫn từ khó bổ trợ, kể cả ở Lesson
  lẫn Practice) **PHẢI có thêm nghĩa tiếng Việt ngắn ngay dưới định nghĩa tiếng Anh** — không chỉ
  hiện định nghĩa Anh-Anh. Hỗ trợ học sinh học yếu hơn, áp dụng đồng nhất, không phải tuỳ chọn.
- **2 tầng từ, khác nhau cả kiểu highlight lẫn hành vi khi tap:**
  - **Tầng "core"** (từ vựng chính thức, đã dạy có gap-fill ở Lesson): highlight vàng đậm có viền.
  - **Tầng "support"** (từ khó KHÁC, chỉ để gỡ rào cản đọc hiểu, KHÔNG dạy chính thức): gạch chân
    chấm, màu xám nhạt.
- **Reveal CHỈ áp dụng ở Practice, KHÔNG áp dụng ở Lesson** — Lesson đã có kịch bản giảng/dịch trực
  tiếp qua từng bước/scene; thêm reveal vào Lesson làm loãng phần dạy kỹ năng (Strategy Reveal).
- **Số từ reveal GIẢM DẦN theo Level** — mặc định tham khảo (co giãn theo độ dài bài thật, không
  phải số cứng): Easy reveal đủ cả 2 tầng, Medium chỉ reveal 1-2 từ khó nhất của tầng support,
  Difficult không reveal gì (đúng điều kiện đọc độc lập hoàn toàn, gần với đề thi thật).
- Ở tầng "core", tap ở Practice **KHÔNG gap-fill, KHÔNG tính vào Word Collection** (khác lúc học ở
  Lesson) — đây là tra cứu lại, không phải học lần đầu.

### 9.12 Strategy Reveal — Thẻ Dạy Chiến Thuật Đọc Hiểu Ngay Trong Bài

> Đúc kết từ Unit 1 ("Spot the Real Evidence" — 1 kỹ năng) + Unit 2 ("Two Ways to Read" — 2 kỹ năng
> song song). Code kỹ thuật đầy đủ ở `03_engine_tiengAnh.md` mục 1.11 (cấu trúc bước + data), 1.12
> (biến thể 1 kỹ năng — Split-view + `scrollToAndHighlight`), 1.13 (biến thể nhiều kỹ năng — 2 Cột
> So Sánh). Mục này nêu QUY TẮC THIẾT KẾ/VỊ TRÍ, không lặp code.

- **Vị trí chèn cố định:** ngay SAU khi học sinh tự hoàn thành phần khám phá nội dung chính (hết
  Card/Discovery/Mission/Stage), TRƯỚC phần tổng kết cuối Lesson (Vocab Collection/Kết đoạn). Không
  chèn ở đầu bài (học sinh chưa có worked-example để dùng) hay tách rời cuối Practice (quá muộn,
  mất tác dụng "chèn ngay sau lúc vừa trải nghiệm").
- **Chọn biến thể theo cấu trúc Lesson có sẵn, KHÔNG phải theo sở thích:**
  - Lesson có Reference Pane với 1 khối đoạn văn liền mạch (VD Reading Passage chia Card theo đoạn)
    → biến thể 1 kỹ năng, Split-view (9.12 + engine 1.12).
  - Lesson dạng Mission/Stage rải nội dung qua nhiều màn, KHÔNG có 1 khối đoạn văn hiển thị liên
    tục → biến thể nhiều kỹ năng, 2 Cột So Sánh (engine 1.13) — kể cả khi chỉ dạy 1 kỹ năng, không
    ép dùng Split-view nếu Lesson không có sẵn khối đoạn văn phù hợp.
- **Worked-example PHẢI tái dùng nội dung học sinh vừa tương tác** (câu evidence vừa chọn, tip vừa
  tìm...) — không bịa ví dụ minh hoạ mới ở bước Recap. Quick check (bước 5) thì NGƯỢC LẠI — bắt
  buộc dùng ngữ liệu MỚI để kiểm tra hiểu bản chất, không chỉ nhớ ví dụ cũ.
- **Nếu Quick check phải mượn 1 đoạn có sẵn nhưng đoạn đó không tự nhiên khớp quy tắc gốc** (từng
  gặp thật: đoạn kết luận không có cặp câu "cụ thể/chung chung" rõ như các đoạn khác) — được phép
  **đổi khung câu hỏi Quick check** cho khớp bản chất đoạn đó, miễn giữ đúng tinh thần kỹ năng đang
  dạy, không cần ép nguyên xi luật của bước Rule callout vào mọi đoạn.
- Với bài Vận dụng ở Practice yêu cầu kỹ năng KHÁC/CAO HƠN những gì Strategy Reveal vừa dạy (VD kết
  hợp bằng chứng từ 2 đoạn, trong khi Strategy Reveal chỉ dạy tìm trong phạm vi 1 đoạn) — thêm 1
  dòng ghi chú nhỏ (không phải bước riêng) ngay cuối phần quy trình, nhắc học sinh luật vẫn áp dụng
  được, chỉ cần lặp lại nhiều lần.

### 9.13 Summary Card + Icon 💡 Recap

> Code kỹ thuật đầy đủ ở `03_engine_tiengAnh.md` mục 1.14. Mục này nêu QUY TẮC THIẾT KẾ.

- Summary Card là bước CUỐI CÙNG bắt buộc của MỌI Strategy Reveal — không phải tuỳ chọn.
- Icon 💡 Recap đặt cạnh **MỌI câu hỏi ở Practice, không giới hạn theo dạng bài/mức độ** (kể cả
  Difficult) — không có lý do sư phạm để giới hạn chỉ 1 vài dạng bài, vì mọi câu hỏi đều có thể cần
  nhắc lại chiến thuật, không chỉ dạng bài "dễ quên" hơn.
- Overlay Recap PHẢI nổi đè lên trên, KHÔNG được thay thế/che khuất vĩnh viễn Reference Pane bên
  dưới — đóng popup phải về đúng y trạng thái (tab/chế độ xem/vị trí cuộn) trước khi mở, không đổi
  layout hay làm mất tiến trình làm bài.
- Mở popup Recap KHÔNG được tính là sai, KHÔNG gọi hàm ghi nhận lỗi dưới bất kỳ hình thức nào.
- Nội dung popup chỉ nhắc lại Rule/quy trình đã học — không thêm ví dụ minh hoạ mới trùng câu học
  sinh đang làm, tránh biến thành gợi ý đáp án trá hình.

### 9.14 Hướng Dẫn Thao Tác On-Screen — BẮT BUỘC Cho Mọi Tương Tác Tuỳ Biến

> Lỗi thật đã gặp: nhiều tương tác tuỳ biến (không phải MCQ/T-F quen thuộc) trong kịch bản chỉ có
> GHI CHÚ KỸ THUẬT mô tả cơ chế cho người build (VD "Tap chọn câu chứa evidence (2 lựa chọn, tap
> không kéo):", "tap-to-classify (KHÔNG kéo-thả)") — nhưng KHÔNG có câu hướng dẫn thật nào hiện ra
> cho học sinh biết phải làm gì. Ghi chú kỹ thuật đó CHỈ dành cho người build đọc, không tự động
> biến thành UI copy — nếu kịch bản không viết rõ câu hướng dẫn, học sinh nhìn màn hình sẽ không
> biết bước tiếp theo là gì.

**Quy tắc bắt buộc:** MỌI tương tác không thuộc nhóm "hiển nhiên tự đoán được" (MCQ tiêu chuẩn, T/F
tiêu chuẩn, gap-fill có chỗ trống rõ ràng) — cụ thể là **tap-to-select nhiều bước, tap-to-classify,
causal chain, tap-select-pairs, hotspot tuỳ biến** — PHẢI có **1 dòng hướng dẫn hiện THẬT trên UI**,
song ngữ (Anh trước, Việt sau), viết ở thì mệnh lệnh ngắn gọn kiểu:

```
> *Tap an item first, then tap the correct bin.*
> Tap vào 1 vật trước, sau đó tap vào đúng thùng rác tương ứng.
```

Dòng này KHÁC nhãn kỹ thuật ở Mục 9.10 (nhãn kỹ thuật luôn ẩn) — đây là nội dung PHẢI hiện, đặt
ngay phía trên/cạnh khu vực tương tác đó. Khi soạn kịch bản, mỗi lần viết "(tap không kéo)" hay
tương tự trong ngoặc mô tả cơ chế, tự kiểm tra thêm: đã có dòng hướng dẫn thật cho học sinh đi kèm
chưa — nếu chưa, thêm ngay, không để mặc định "học sinh tự đoán ra".

### 9.15 Checklist bổ sung (thêm vào Mục 7)

- [ ] Toàn hệ thống dùng "Difficult", không còn "Hard" ở bất kỳ file nào (kể cả nội dung copy từ
      Master Prompt Revision cũ)
- [ ] Không có gợi ý (hint) hiện trước khi trả lời ở bất kỳ component nào; đáp án/lựa chọn/câu hỏi
      100% tiếng Anh; chỉ `explain` tiếng Việt
- [ ] Từ vựng/collocation chính thức: đậm (`.vocab-bold`), hiện sẵn không cần tap. Từ đánh dấu gạch
      chân riêng trong file Word: gạch chân thật (`.vocab-underline`), không lẫn kiểu tap-tooltip `.kw`
- [ ] Nếu bài có Read Aloud/Shadowing/Production ghi âm: đã dùng component 9.4, xin quyền micro đúng
      lúc bấm ghi âm (không xin trước), tắt mic sau khi dừng
- [ ] Phần Sắp xếp cấp đoạn (Revision Unit Check): dùng component 9.5, KHÔNG dùng nhầm Word-Tile
      (4.13, chỉ dành cho sắp xếp từ trong 1 câu)
- [ ] Writing (Guided/Free): có nút Nộp bài + hiển thị rubric 4 tiêu chí + nhận xét tiếng Việt (9.6)
- [ ] `diagQuestions`/Revision: có đủ field `cat` VÀ `level`, badge hiển thị cả 2 trục (9.7)
- [ ] Đã lược bỏ hoàn toàn nhãn `[Mức độ · Dạng bài]` khỏi mọi nơi học sinh nhìn thấy được (9.8)
- [ ] Đã lược bỏ hoàn toàn MỌI nhãn kỹ thuật nội bộ khác (`skill`, hoặc tag mới phát sinh sau này)
      khỏi mọi nơi học sinh nhìn thấy được — không chỉ riêng `level`/`cat` (9.10)
- [ ] Mọi popup nghĩa từ vựng (Lesson lẫn Practice, core lẫn support) có đủ nghĩa tiếng Việt (9.11)
- [ ] Nếu Lesson có Strategy Reveal: đã chọn đúng biến thể theo cấu trúc Lesson thật (Split-view
      hay 2 Cột So Sánh), có đủ Summary Card ở bước cuối (9.12)
- [ ] Icon 💡 Recap ở Practice không giới hạn theo dạng bài/mức độ, không gọi hàm ghi nhận lỗi khi
      mở, không chứa ví dụ minh hoạ mới trùng câu đang làm (9.13)
- [ ] Mọi tương tác tuỳ biến (tap-to-classify, causal chain, tap-select-pairs, hotspot...) đều có
      dòng hướng dẫn thao tác hiện thật trên UI, song ngữ — không chỉ có ghi chú kỹ thuật (9.14)
- [ ] Guided Noticing (4.20): `.notice-input` KHÔNG gọi `checkTextAnswer()`/`recordMistake()`; nút
      "Hiện đáp án" chỉ hiện khối đáp án, không khoá lại ô input, không đánh giá đúng/sai (4.20)
- [ ] Idea Diagram (4.21): dựng thuần CSS Flexbox, KHÔNG dùng SVG/toạ độ JS vẽ đường nối; đúng 1
      trong 4 `data-state` (full/partial/guided/blank); mobile ép `flex-direction:column` ở
      `.idea-branches`; không auto-chấm ô `.idea-leaf-input`
- [ ] Auto-collapse Theory Block (4.22): dùng `<details>/<summary>` gốc HTML; chỉ gom khối LIỀN
      TRƯỚC khi mở khối mới; không dùng cho khối luyện tập có chấm điểm; khối đầu tiên mới `open`
      mặc định
- [ ] Typewriter + Growing Diagram (engine 1.17, nếu có demo dẫn dắt): tôn trọng
      `prefers-reduced-motion`, có nút/tap bỏ qua hiệu ứng, dùng `.hidden-grow{display:none}` thay
      vì `opacity:0` để tránh layout nhảy giật trên mobile
- [ ] Find the Error (Error Identification): 4 lựa chọn A/B/C/D render **inline liền mạch trong 1
      câu duy nhất** (giống văn bản thường, browser tự wrap), TUYỆT ĐỐI không phải 4 "card"/pill
      riêng có border-box ép xuống dòng riêng; không có bảng Easy/Medium/Difficult checkbox debug
      lộ ra ngoài UI học sinh (9.16)
- [ ] Gap-fill/Sentence Completion: câu + ô input nằm trong ĐÚNG 1 khối `<p>` liền mạch (Mục 4,
      ngay trên Bài Gap-fill), không tách nửa câu trước/sau input thành card/span riêng có border
- [ ] Nội dung ngôn ngữ chính (Reading, chat bubble, câu hỏi/đáp án, IPA, ví dụ từ vựng, model text)
      đạt sàn ≥15px; nhãn UI/meta phụ ≥11px (0, nguyên tắc 11). Không có class thu-nhỏ-chữ nào bị
      "kế thừa nhầm" từ ngữ cảnh cột hẹp desktop sang layout mobile đã đổi (carousel/step-gate) mà
      chưa được viết đè lại bằng media query riêng.
- [ ] Mọi `<h2>`/`<h3>`/`<h4>` và mọi `title` trong `athena-context.structure` dùng làm heading/tên
      section đều viết tiếng Anh trước — nếu cần bản dịch, đặt trong `<span class="vi-sub">` hoặc
      tương đương NGAY SAU tiêu đề Anh, không đảo ngược thứ tự, không để heading thuần tiếng Việt
      không kèm bản Anh (0, xem lỗi thật đã gặp — heading "Bài phát biểu mẫu..." không có bản Anh)
- [ ] Mọi Activity có ô viết đoạn/câu hoàn chỉnh (Practice lẫn Production) đều có Gated Reveal (9.17)
      hoặc luồng Nộp bài AI (9.6) — không có ô nào viết xong rồi không có phản hồi gì
- [ ] Nút "Xem model answer"/"Xem đáp án gợi ý" bắt đầu `disabled`, chỉ mở khoá sau khi học sinh đã
      thử (đủ % số từ mục tiêu, hoặc điền đủ toàn bộ ô trống) — không bấm xem được ngay từ đầu (9.17)
- [ ] Mọi nút render từ text tự do (MCQ, Matching, Ordering, Tap-to-Categorize...) dùng
      `addEventListener`, KHÔNG nhúng text vào thuộc tính `onclick=""` — tránh lỗi gãy nút khi text
      chứa dấu nháy đơn như "school's"/"I'd" (0 Nguyên tắc 8, 4.6)
- [ ] Structure/Sequence Labelling: thứ tự câu hỏi đã được xáo, không trùng thứ tự xuất hiện trong
      bài mẫu gốc (0 Nguyên tắc 16)
- [ ] Activity nào là điều kiện mở khoá bước/phase tiếp theo đã dùng Submit tường minh (9.17 biến
      thể), không chỉ auto-gate qua sự kiện `input`

### 9.16 Find the Error (Error Identification trong câu) — layout dạng câu liền mạch, KHÔNG phải
card rời

> Phát hiện qua ảnh chụp bản build thật (Grammar · Passive Voice — Practice, dạng "Tìm phần lỗi sai
> A/B/C/D"): 4 lựa chọn đang render thành 4 "card" riêng — mỗi cái có viền chấm + nền + bo góc +
> chiều rộng cố định, xếp trong flex-wrap. Kết quả: câu bị vỡ thành từng mảnh rời rạc, xuống dòng
> lộn xộn (A+B chung 1 dòng, C tự xuống dòng riêng dù còn thừa chỗ, D lại xuống dòng khác), khoảng
> trắng thừa lớn, đọc như 1 chuỗi nhãn dán chứ không phải 1 câu văn. Đây là lỗi vì **không có pattern
> nào trong file này định nghĩa component "Find the Error" trước đó** — người build phải tự bịa
> layout, và bịa sai. Mục này bổ sung pattern chuẩn để không lặp lại.

**Nguyên tắc cốt lõi: cả câu (kể cả 4 phần A/B/C/D) PHẢI nằm trong 1 khối `<p>` duy nhất, dùng
`display:inline` cho từng lựa chọn — KHÔNG dùng `inline-block`/card/border-box ép chiều rộng cố
định.** Để trình duyệt tự ngắt dòng theo đúng cách 1 đoạn văn bản thường ngắt — không tự chia dòng
theo từng lựa chọn.

```html
<div class="fte-item">
  <p class="fte-sentence">
    <span class="fte-num">1.</span> The new recycling bins
    <span class="fte-choice" data-choice="A" tabindex="0">(A) were install</span>
    <span class="fte-choice" data-choice="B" tabindex="0">(B) in the school</span>
    <span class="fte-choice" data-choice="C" tabindex="0">(C) by the staff</span>
    <span class="fte-choice" data-choice="D" tabindex="0">(D) last week</span>.
  </p>
  <button class="fte-confirm">✓ Xác nhận lỗi</button>
  <div class="fte-feedback correct" hidden>
    <b>Chính xác!</b> Phần A sai. Đúng phải là "were installed" (thiếu đuôi -ed của quá khứ phân từ
    trong câu bị động quá khứ đơn).
  </div>
</div>
```
```css
.fte-item { background:var(--white); border-radius:var(--radius); padding:20px 22px; margin-bottom:16px; }
.fte-num { font-weight:700; color:var(--ink-2); margin-right:4px; }
.fte-sentence { display:inline; font-size:17px; line-height:1.9; color:var(--ink); }
/* Quan trọng: KHÔNG inline-block, KHÔNG border, KHÔNG background mặc định — chỉ gạch chân chấm để
   báo hiệu "đây là phần có thể tap", không phá vỡ dòng chảy của câu */
.fte-choice { display:inline; border-bottom:2px dashed var(--ink-3); padding:0 1px; cursor:pointer;
  border-radius:3px; transition:background .15s; }
.fte-choice:hover, .fte-choice:focus-visible { background:var(--accent-pale); }
.fte-choice.selected { background:var(--accent-pale); border-bottom-color:var(--accent);
  color:var(--accent-text); font-weight:700; }
.fte-choice.marked-wrong { background:var(--wrong-bg); border-bottom-color:var(--wrong);
  color:var(--wrong); font-weight:700; } /* hiện sau khi Xác nhận, đánh dấu đúng phần sai thật */
.fte-confirm { margin-top:14px; background:var(--correct); color:#fff; border:none;
  border-radius:var(--radius-sm); padding:10px 20px; font-weight:700; min-height:44px; }
.fte-feedback { margin-top:12px; padding:12px 16px; border-radius:var(--radius-sm); font-size:14.5px; }
.fte-feedback.correct { background:var(--correct-bg); color:var(--jade-text); }
.fte-feedback.wrong { background:var(--wrong-bg); color:var(--wrong); }
```

**⚠️ Bắt buộc:**
1. Cả câu — kể cả text dẫn không tappable ("The new recycling bins") lẫn 4 lựa chọn A-D — nằm
   trong ĐÚNG 1 thẻ `<p class="fte-sentence">`, không tách rời ra các div/card con.
2. `.fte-choice` là `display:inline`, không đặt `width`/`min-width` cố định, không `border` bao
   quanh toàn khối — chỉ `border-bottom` (gạch chân) để giữ cảm giác "đọc câu văn bình thường, có
   4 chỗ gạch chân để chọn", đúng chuẩn đề thi tìm lỗi sai in trên giấy.
3. Nhãn "(A)"/"(B)"/"(C)"/"(D)" nằm NGAY TRONG span đó (đầu câu chữ), không tách thành 1 badge
   riêng phía trước — tránh việc badge và text bị trôi lệch dòng với nhau khi wrap.
4. **KHÔNG hiện bất kỳ debug control nào** (checkbox Easy/Medium/Difficult Level, nút preview mức
   độ...) trong bản học sinh nhìn thấy — nếu cần công cụ dev để xem trước từng mức, đặt sau 1 flag
   `?debug=1` trên URL hoặc build riêng bản QA, không lẫn vào component chính.

### 9.17 Gated Reveal — chuẩn hoá MỌI nút "Xem model answer / Xem đáp án gợi ý" trong Writing & bài
tự luận (KHÔNG áp dụng cho MCQ/trắc nghiệm, đã có quy tắc riêng ở 9.2)

> Phát hiện qua QA thật (Writing Unit 2 Lớp 10): mỗi Activity tự bịa 1 kiểu hint khác nhau — có bài
> nút "Xem model answer" bấm được ngay từ đầu (chưa viết chữ nào), có bài không có nút gì cả (viết
> xong không biết đúng sai), có bài dùng popup, có bài dùng model answer ẩn trong footer. Mục 9.2 chỉ
> quy định cho câu hỏi có đáp án đúng/sai (MCQ...); mục này bổ sung pattern riêng cho các trường hợp
> **không có đúng/sai tuyệt đối** — model answer, đáp án gợi ý cho Read & Extract, gợi ý ý tưởng cho
> bài viết tự do — nơi Mục 9.2 không áp dụng thẳng được nhưng vẫn cần 1 chuẩn chung, không để mỗi
> Activity tự bịa.

**Nguyên tắc cốt lõi:** mọi nút "Xem model answer"/"Xem đáp án gợi ý"/"Xem gợi ý ý tưởng" gắn với 1
ô viết/điền cụ thể LUÔN bắt đầu ở trạng thái `disabled`, chỉ mở khoá SAU KHI học sinh đã thật sự thử
— không bao giờ để học sinh xem được trước khi tự làm, kể cả với bài không chấm đúng/sai.

**2 điều kiện mở khoá, chọn đúng loại theo bản chất Activity:**

| Loại Activity | Điều kiện mở khoá | Ví dụ |
|---|---|---|
| Viết đoạn/câu tự do (textarea) | Đã gõ đủ **~30-50% số từ mục tiêu** của Activity đó (không cần đạt đủ 100%, chỉ cần chứng minh đã thử) | Guided Writing hỗ trợ đầy đủ, Independent Writing, Guided Writing Production |
| Điền bảng/ô trống có đáp án cụ thể (input rời rạc) | Đã điền **đủ TẤT CẢ ô** (không cần đúng) | Read & Extract |

```html
<textarea class="write-area" id="[id]" oninput="checkRevealGate('[id]','[btnId]',[minWords])"></textarea>
<button class="reveal-btn" id="[btnId]" disabled data-unlocked-label="Xem model answer"
        onclick="openModelAnswerSheet('[modelAnswerId]')">🔒 Viết ít nhất [minWords] từ để mở khoá (0/[minWords])</button>
```

> ⚠️ **Không dùng `openPopup(...)` mơ hồ** — hàm cụ thể là `openModelAnswerSheet(modelAnswerId)`,
> tái dùng ĐÚNG pattern overlay bottom-sheet đã có ở Mục 1.14 file engine (`#recap-popup`), chỉ đổi
> id/nội dung sang Model answer — xem code đầy đủ ở Mục 1.18 file engine. Không viết popup/modal
> riêng cho Model answer, tránh có 2 kiểu overlay khác nhau trong cùng 1 file.
```
```javascript
function checkRevealGate(textareaId, btnId, minWords) {
  const text = document.getElementById(textareaId).value.trim();
  const count = text ? text.split(/\s+/).filter(Boolean).length : 0;
  const btn = document.getElementById(btnId);
  if (count >= minWords) { btn.disabled = false; btn.textContent = btn.dataset.unlockedLabel; }
  else { btn.disabled = true; btn.textContent = `🔒 Viết ít nhất ${minWords} từ để mở khoá (${count}/${minWords})`; }
}
```
```css
.reveal-btn:disabled { background:var(--cream-2); border-color:var(--paper-line); color:var(--ink-faint);
  cursor:not-allowed; opacity:.75; }
```

Với Activity điền bảng, thay `checkRevealGate` bằng kiểm tra "tất cả `.re-input` cùng nhóm đã có
giá trị" (gắn `data-re-group` cho từng input, lặp `querySelectorAll` để check `every`).

**Biến thể — Submit tường minh (khi Activity đó CŨNG là điều kiện mở khoá bước/phase tiếp theo):**

> Phát hiện qua QA thật (Writing Unit 2 Lớp 10, Activity Read & Extract): nếu chỉ tự động mở khoá
> ngay khi điền đủ ô (không cần bấm gì), học sinh có thể điền qua loa rồi lướt sang bước sau mà
> không thật sự dừng lại đối chiếu đáp án. Khi Activity đó là "cửa" bắt buộc trước khi sang
> phase/bước tiếp theo (không chỉ là 1 bài luyện độc lập), dùng nút **Submit tường minh** thay vì tự
> động mở khoá qua sự kiện `input`:

```html
<button class="an-btn" id="submitBtn" onclick="submitAndUnlock()">✓ Submit</button>
<span class="word-count" id="warnMsg" style="color:var(--wrong);display:none;">Điền đủ trước khi Submit nhé.</span>
<button class="reveal-btn" id="revealBtn" disabled data-unlocked-label="Xem đáp án gợi ý">🔒 Submit bài để mở đáp án</button>
...
<button class="next-level-btn" id="nextBtn" disabled onclick="goToLevel('phase-1')">Next &rarr;</button>
```
```javascript
function submitAndUnlock() {
  const inputs = document.querySelectorAll('.re-input[data-re-group="[group]"]');
  const filled = Array.from(inputs).every(inp => inp.value.trim().length > 0);
  const warn = document.getElementById('warnMsg');
  if (!filled) { warn.style.display = 'inline'; return; }
  warn.style.display = 'none';
  const revealBtn = document.getElementById('revealBtn');
  revealBtn.disabled = false;
  revealBtn.textContent = revealBtn.dataset.unlockedLabel;
  document.getElementById('submitBtn').disabled = true;
  document.getElementById('nextBtn').disabled = false; // khoá cả nút chuyển bước cho tới khi Submit
}
```

Dùng auto-gate (`checkRevealGate`/`input` listener) khi Activity chỉ là luyện tập độc lập, không
chặn đường đi tiếp; dùng Submit tường minh khi Activity đó là mốc bắt buộc trước khi mở bước sau.

**Biến thể — Submit tường minh cho TEXTAREA tự do (mới, v2.7):**

> Khác với biến thể Submit tường minh ở trên (chỉ hợp bảng điền nhiều ô rời rạc), biến thể này dùng
> khi giáo viên muốn MỌI Activity viết đoạn/câu — kể cả Activity KHÔNG chặn bước tiếp theo, chỉ là
> luyện tập độc lập — đều bắt học sinh chủ động bấm Submit thay vì tự mở khoá qua sự kiện `input`.
> Đây là lựa chọn thiết kế của giáo viên (áp dụng khi kịch bản Writing ghi rõ "mọi bài viết đều có
> nút Submit"), không phải mặc định bắt buộc thay thế auto-gate — nếu kịch bản không nói rõ, vẫn
> dùng auto-gate (`checkRevealGate`) như bảng ở trên.

```html
<textarea class="write-area" id="essay1" oninput="updateWordCount('essay1','wc1')"></textarea>
<div class="word-count" id="wc1">0/[minWords] từ</div>
<button class="an-btn" id="submitBtn1" onclick="submitByWords('essay1',[minWords],'submitBtn1','revealBtn1')">✓ Submit</button>
<span class="word-count" id="warnMsg1" style="color:var(--wrong);display:none;">Viết thêm trước khi Submit nhé.</span>
<button class="reveal-btn" id="revealBtn1" disabled data-unlocked-label="Xem model answer">🔒 Submit bài để mở model answer</button>
```

Xem hàm `submitByWords()` đầy đủ ở Mục 1.18 file engine — cùng họ với `submitAndUnlock()` (bảng
điền) nhưng check điều kiện theo số từ trong 1 textarea, không phải "mọi ô đã điền".

**⚠️ Bắt buộc:**
1. **Mọi ô viết đoạn/câu hoàn chỉnh trong file (kể cả Practice formative, không chỉ Production)** đều
   phải có MỘT trong 2 dạng phản hồi sau khi hoàn thành — không được để trống hoàn toàn như một
   "hộp thư đen" (viết xong không có bất kỳ phản hồi nào): (a) Gated Reveal model answer/gợi ý (mục
   này), hoặc (b) luồng Nộp bài AI Athena thật (Mục 9.6) nếu là bài được chấm điểm chính thức.
2. Ngưỡng số từ mở khoá (`minWords`) tính theo % độ dài mục tiêu thật của Activity đó (Mục 3 Prompt
   Template Writing) — không dùng 1 con số cứng cho mọi bài khác độ dài.
3. Text nút ở trạng thái khoá PHẢI hiện rõ điều kiện + tiến độ hiện tại (VD "Viết ít nhất 40 từ để
   mở khoá (12/40)") — không chỉ hiện mờ đi không rõ lý do.
4. KHÔNG áp dụng gate này cho nút "Xem đáp án" của MCQ/trắc nghiệm có đúng/sai rõ ràng — những
   component đó dùng đúng quy tắc 9.2 (hiện đáp án SAU khi học sinh đã chọn/trả lời, không phải sau
   khi gõ đủ số từ).
5. Nếu Activity là điều kiện mở khoá bước/phase tiếp theo, dùng biến thể Submit tường minh ở trên —
   không dùng auto-gate qua `input` cho trường hợp này.

