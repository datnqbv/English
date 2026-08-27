## Kịch bản: Writing — Unit 2 (Lớp 10) — Writing

**Nguồn:** `L10-Unit_2_Writing_KichBan.md` (bản kịch bản đã qua QA) · đối chiếu Syllabus Grade 10, Week 4–6, Unit 2 — dòng Writing (SGK Global Success Tiếng Anh 10, SB p.25)
**Tên bài hiển thị cho học sinh:** Humans and the Environment — Suggestion Paragraph (giữ tên gốc, chủ đề tự chọn, không trùng nhan đề SGK)
**Xác nhận:** Không có nội dung học thuật gốc nào bị sửa — chỉ lược bỏ 2 mục ghi chú nội bộ (Bảng kiểm tra số lượng câu hỏi, ghi chú lý giải cách cài lỗi) theo Quy tắc mới 1, quy các mô tả màu mơ hồ về đúng CSS token (đối chiếu file Word gốc `L10Unit2_Writing_Full.docx`), và bổ sung đúng 2 prompt sinh ảnh nguyên văn đã có sẵn trong Word.
**Ảnh cần sinh:**
- Vị trí: Hook — Mission Card, ảnh hero ngang phía trên text | Lý do: minh hoạ chủ đề "trường học xanh" mở đầu nhiệm vụ | Prompt (nguyên văn từ file Word gốc): *"Flat vector illustration, horizontal 16:9 composition, a bright and welcoming Vietnamese high school scene focused on green, eco-friendly details — small potted plants on classroom windowsills, natural sunlight streaming through large windows, a recycling bin and a water refill station visible in a school corridor or courtyard, soft leafy tree branches framing the edges. Warm, optimistic mood, no readable text or signage anywhere in the image. Color palette: soft jade green (#3CA57A, #A9D0BE) and warm cream tones (#FAF7F0, #F0EADD), muted and airy, not saturated. Leave the lower third of the image visually calm/uncluttered (sky, wall, or soft blur) to allow a dark gradient overlay and text to sit on top. No real, identifiable people — if students appear, keep them small, stylized, and faceless/silhouetted, not photorealistic. No logos, no brand names, no readable posters."*
- Vị trí: Hook — card "Winning paragraph", lớp nền hoạ tiết mờ phía sau chữ | Lý do: nền trang trí opacity thấp cho khối "văn bản trang trọng" | Prompt (nguyên văn từ file Word gốc): *"Flat vector illustration, seamless soft background texture/pattern, delicate green leaves and thin plant stems scattered loosely across a plain background, very light and airy, gentle dappled natural light suggestion (soft pale green-gold glow). Minimalist and subtle — designed to be used at low opacity (12–18%) as a decorative backdrop behind text, so avoid busy detail, sharp contrast, or focal points. No text, no people, no objects other than plant/leaf motifs. Color palette: pale jade green (#A9D0BE, #DCEAE1) on a cream base (#FAF7F0). Square or portrait orientation works best since it sits behind a vertical text card."*

*Bối cảnh xuyên suốt: **Environment Speech Contest** — Khoa / Hà / Mai*

> Mọi ghi chú "🎨 Desktop" / "📱 Mobile (responsive)" trong file này là YÊU CẦU HÀNH VI cho người dựng HTML — không phải nội dung học sinh nhìn thấy. Mobile-first bắt buộc: dựng đúng hành vi mobile trước, desktop chỉ mở rộng thêm (không phải ngược lại).

## Objectives

1. Write a paragraph giving suggestions to improve the environment, using a topic sentence, supporting points, and a concluding sentence.
2. Use sequence words (First/Second/Third) and "For example" to organise and support ideas clearly.

---

### PHẦN 1 — LESSON (`kichban_unit2_writing_lesson.html`)

#### Part 1 — Writing Structure

## HOOK — Nhiệm vụ nhận được

**Banner thông báo (trạng thái đóng, hiện đầu tiên):**

> 🔔 Bạn vừa nhận một nhiệm vụ mới!
> Environment Speech Contest — chạm để xem chi tiết

> 🎨 **Desktop:** banner nổi bật, hiệu ứng rung/nảy nhẹ (bounce) để thu hút chú ý, nền jade đậm (`--jade-deep`) chữ trắng, bo góc lớn, đổ bóng nhẹ — kế thừa đúng pattern "Bạn có 1 email mới!" của Unit 1.
> 📱 **Mobile:** banner full-width, chạm toàn bộ diện tích banner để mở (không chỉ chạm vào 1 nút nhỏ) — vùng chạm tối thiểu 44×44px. Hiệu ứng bounce giảm biên độ trên màn hình nhỏ để không đẩy layout dịch chuyển gây khó chịu khi cuộn.

**Mission Card (khi chạm mở):**

> ENVIRONMENT SPEECH CONTEST 🌱
>
> Khoa, Hà and Mai have been chosen to represent Class 10A in the Inter-school Environment Speech Contest. Before writing their own speech, the organisers sent last year's winning paragraph so teams can study how it is organised.
>
> 📌 Your task today: read the winning paragraph carefully, learn how it is built — then write your own speech for the contest.

> 🎨 **Desktop:** mở theo hiệu ứng slide-down/fade-in. Phía trên text đặt 1 ảnh/minh hoạ ngang (hero image) chủ đề "trường học xanh" (cây xanh, ánh sáng tự nhiên, không khí học đường tích cực), full-width trong card, bo góc lớn phía trên khớp card, có lớp gradient tối nhẹ ở đáy ảnh nếu cần đặt chữ đè lên. Cuối khối là nút/label dẫn tiếp: "📄 Xem bài phát biểu đoạt giải năm ngoái ↓".
> 📱 **Mobile:** ảnh hero co theo chiều ngang màn hình (`width:100%; height:auto` hoặc tỉ lệ cố định 16:9), KHÔNG cắt cúp mất chi tiết quan trọng ở giữa ảnh (dùng `object-fit: cover` với `object-position: center`). Text mission card giữ padding ngang 16-20px, cỡ chữ không giảm dưới 15px. Nút dẫn tiếp full-width, dễ chạm.

**Bài mẫu (Winning paragraph) — dùng lại nguyên vẹn ở mục D bên dưới:**

> There are several things we can do to make our school greener. First, we should turn off the lights and fans when we leave a room. For example, students can check the switches in classrooms before leaving. This can reduce our school's electricity use. Second, the school could set up refill stations for water and hand soap near the canteen. For example, students can refill their own bottles instead of buying new plastic ones. This can cut down on single-use plastic waste. Third, we should encourage students to bring their own water bottles every day. This will help our school produce less plastic waste. In conclusion, making our school greener doesn't need big changes. Small daily habits can already make a real difference.
>
> *(123 words)*

> 🎨 **Desktop:** khối cần đầu tư thiết kế nhất trong Hook — trình bày như MỘT VĂN BẢN TRANG TRỌNG. Bố cục: 1 thẻ (card) riêng biệt tách khỏi nền trang, mô phỏng "tờ giấy dự thi được đóng khung". Lớp nền: 1 ảnh/hoạ tiết chủ đề thiên nhiên (lá cây, ánh sáng xanh dịu) làm MỜ (opacity ~12-18%) hoặc phủ thêm lớp màu cream bán trong suốt lên trên. Viền trang trí: khung viền kép mảnh màu `--jade-soft` hoặc hoạ tiết góc hình lá cây nhỏ ở 4 góc. Góc trên gắn 1 ruy-băng nhỏ (ribbon badge) nền `--jade-deep` chữ trắng ghi "🏆 Bài đoạt giải năm ngoái". Chữ dùng font Be Vietnam Pro, cỡ ~15-16px, line-height ~1.7.
> 📱 **Mobile:** đơn giản hoá lớp viền trang trí — chỉ giữ 1 đường viền mảnh đơn (bỏ viền kép) và hoạ tiết góc thu nhỏ hoặc bỏ hẳn 2 góc dưới, tránh viền trang trí "ăn" vào chiều rộng vốn đã hẹp của khối text. Ruy-băng góc trên thu nhỏ, không che chữ dòng đầu. Ảnh nền mờ giữ nguyên nhưng kiểm tra độ tương phản kỹ hơn (test trên màn hình sáng ngoài trời) vì màn hình điện thoại thường có độ chói cao hơn. Cỡ chữ giữ tối thiểu 15px, không thu nhỏ thêm dù card hẹp — thà cho card cao hơn còn hơn chữ nhỏ khó đọc. KHÔNG có nhãn cấu trúc hay khả năng bấm ở bước này — học sinh chỉ đọc.

---

## A · Khung tổng quát

**HOW TO WRITE A SUGGESTION PARAGRAPH**

| Part | Guiding Question — Câu hỏi định hướng |
|---|---|
| ① Topic Sentence | What is this paragraph about? |
| ② Supporting Point 1 | Suggestion → Example → Expected result |
| ③ Supporting Point 2 | Suggestion → Example → Expected result |
| ④ Supporting Point 3 | Suggestion → Example → Expected result |
| ⑤ Concluding Sentence | How does the paragraph wrap up? |

> 🎨 **Desktop:** trình bày dạng chuỗi khối dọc (vertical flow), mỗi phần 1 thẻ nối bằng mũi tên xuống, ở trạng thái tóm tắt (chỉ tên phần + icon) — bấm vào mới mở rộng hiện câu hỏi định hướng (progressive disclosure). 3 thẻ Point 1/2/3 dùng cùng 1 màu `--jade-pale`; Topic Sentence và Concluding Sentence dùng `--cream-3`.
> 📱 **Mobile:** cấu trúc này vốn đã là 1 cột dọc nên gần như không cần đổi layout — chỉ cần đảm bảo mũi tên nối giữa các thẻ đủ rõ ở màn hình hẹp (dùng icon mũi tên đơn giản, không dùng đường kẻ mảnh dễ mất nét khi nén ảnh). Khoảng cách giữa các thẻ giảm nhẹ (12-16px thay vì 24px trên desktop) để giảm số lần cuộn.

---

## B · Đi sâu từng phần

### B.1 — Topic Sentence

| | |
|---|---|
| Formula | There are several things we can do to + verb... |
| Example ✓ | There are several things we can do to make our school greener. |
| Not good ✗ | Our school has a lot of environmental problems. *(quá chung chung, không báo hiệu sẽ có các đề xuất)* |

### B.2 — Supporting Point (3 layers)

| Layer — Lớp | Formula | Example |
|---|---|---|
| Suggestion | First/Second/Third, + suggestion. | First, we should turn off the lights and fans when we leave a room. |
| Example | For example, + specific action. | For example, students can check the switches in classrooms before leaving. |
| Expected result | This can/will + result. | This can reduce our school's electricity use. |

### B.3 — Concluding Sentence

| | |
|---|---|
| Formula | In conclusion, + restate main idea. |
| Example ✓ | In conclusion, making our school greener doesn't need big changes. Small daily habits can already make a real difference. |
| Not good ✗ | That's all. *(quá cụt, không tổng kết được ý gì)* |

> 🎨 **Desktop:** B.1/B.3 dùng dạng thẻ lật (flip card): mặt trước hiện Formula, chạm để lật sang mặt sau hiện Example. Ví dụ ĐÚNG và SAI đặt CẠNH NHAU trên cùng 1 hàng ngang (contrasting cases) — ví dụ sai có icon ⚠️ viền màu `--warning` (nền `--warning-bg`), ví dụ đúng có icon ✓ viền `--jade-pale`. B.2 dùng hiệu ứng hiện dần theo lớp (layered reveal): Suggestion → chạm "+ Thêm ví dụ" hiện Example → chạm tiếp "+ Thêm kết quả" hiện Result. Mỗi lớp 1 màu nền riêng nhạt (Suggestion: `--cream-2`, Example: `--sage-pale`, Result: `--jade-pale`).
> 📱 **Mobile:** cặp ví dụ ĐÚNG/SAI ở B.1 và B.3 **KHÔNG đặt cạnh nhau nữa — chuyển thành xếp chồng dọc** (Example ✓ ở trên, Not good ✗ ngay bên dưới), vì cạnh nhau trên màn hình ≤480px sẽ làm mỗi ô quá hẹp, chữ bị xuống dòng liên tục và khó so sánh. Giữ nguyên màu viền/icon để vẫn nhận ra ngay là 1 cặp đối chiếu dù xếp dọc. Thẻ lật (flip card) vẫn hoạt động tốt trên mobile qua chạm (tap), không cần hover — đảm bảo vùng chạm toàn bộ thẻ, không chỉ 1 góc nhỏ. B.2 layered reveal giữ nguyên bố cục dọc, chỉ giảm padding mỗi lớp.

---

## C · Suggestion Builder — Process for building 1 Supporting Point

1. **Choose varied ideas:** pick 2-3 suggestions that are genuinely different from each other (not repeating the same angle)
2. **Brainstorm for each idea:** ask yourself "How exactly? (Example)" and "What result? (Expected result)"
3. **Build the sentence using the Formula:** combine all 3 layers into one complete chunk, using the correct sequence word
4. **Re-read the whole thing:** check all 3 layers are present — don't skip Example or Result
5. **Common mistakes:** forgetting "For example,"; a Suggestion that's too vague; an Expected result that just repeats the Suggestion word-for-word

> 🎨 **Bản dịch tiếng Việt (ẩn mặc định, hiện qua nút toggle — đúng Nguyên tắc 15 song ngữ):**
> 1. **Chọn ý đa dạng:** chọn 2-3 suggestion khác loại nhau (không lặp cùng 1 hướng)
> 2. **Brainstorm cho từng ý:** "Làm cụ thể ra sao? (Example)" và "Kết quả gì? (Expected result)"
> 3. **Ráp câu theo Formula:** ghép 3 lớp thành 1 cụm hoàn chỉnh, dùng đúng sequence word
> 4. **Đọc lại toàn bộ:** kiểm tra đủ 3 lớp, không thiếu Example hoặc Result
> 5. **Lỗi thường gặp:** quên "For example,"; Suggestion quá mơ hồ; Expected result lặp lại y nguyên Suggestion

> 🎨 **Desktop:** dạng scroll-stack (có thể cuộn ngang), mỗi bước 1 thẻ lớn có chấm tiến trình (progress dots) phía trên. Bước 1 minh hoạ bằng vài thẻ ý tưởng, 3 thẻ khoanh nổi bật (đã chọn), còn lại mờ đi. Bước 5 dùng contrasting cases như mục B.
> 📱 **Mobile:** đổi scroll-stack sang **cuộn dọc** thay vì cuộn ngang — cuộn ngang trên điện thoại dễ xung đột với cử chỉ vuốt-để-quay-lại (swipe-back) của hệ điều hành và dễ bị bỏ sót bước nếu học sinh không nhận ra còn nội dung ở bên phải. Nếu vẫn muốn giữ cảm giác "từng bước" thì dùng carousel dọc có chấm tiến trình bên cạnh (không phải bên trên) và snap-scroll (`scroll-snap-type: y mandatory`) để mỗi lần cuộn dừng đúng 1 bước. Bước 5 (contrasting cases) áp dụng đúng quy tắc xếp dọc như B.1/B.3 ở trên.

---

## D · Phân tích bài mẫu hoàn chỉnh

**Winning paragraph — Environment Speech Contest** *(đúng bài đã dùng ở Hook)*

> There are several things we can do to make our school greener. First, we should turn off the lights and fans when we leave a room. For example, students can check the switches in classrooms before leaving. This can reduce our school's electricity use. Second, the school could set up refill stations for water and hand soap near the canteen. For example, students can refill their own bottles instead of buying new plastic ones. This can cut down on single-use plastic waste. Third, we should encourage students to bring their own water bottles every day. This will help our school produce less plastic waste. In conclusion, making our school greener doesn't need big changes. Small daily habits can already make a real difference.

| Part | Corresponding excerpt | Function |
|---|---|---|
| ① Topic Sentence | "There are several things we can do to make our school greener." | Introduces the topic |
| ② Point 1 | "First, we should turn off the lights...electricity use." | Suggestion + Example + Result |
| ③ Point 2 | "Second, the school could set up...plastic waste." | Suggestion + Example + Result |
| ④ Point 3 | "Third, we should encourage...plastic waste." | Suggestion + Example + Result |
| ⑤ Concluding Sentence | "In conclusion...real difference." | Summarises and closes the paragraph |

> 🎨 **Desktop:** mỗi câu là 1 hotspot bấm được — chạm câu → sáng màu theo đúng chức năng (Topic/Suggestion/Example/Result/Conclusion, mỗi chức năng 1 màu cố định xuyên suốt) + hiện nhãn nổi bật phía trên câu đó. Có nút "🔍 Phân tích tự động" chạy tuần tự. Sau khi phân tích xong, hiện sơ đồ tóm tắt dọc "Notice the pattern": Topic → (Suggestion→Example→Result) ×3 → Conclusion.
> 📱 **Mobile:** vùng chạm mỗi câu (hotspot) cần đủ lớn theo chiều cao dòng — câu ngắn trên 1 dòng vẫn phải có padding trên/dưới để dễ chạm trúng, tránh chạm nhầm sang câu liền kề. Nhãn hiện ra khi chạm nên xuất hiện NGAY TRÊN câu đó dạng tooltip nhỏ có mũi tên chỉ xuống (không hiện ở vị trí cố định 1 chỗ trên cùng màn hình, vì học sinh sẽ phải liên tục nhìn lên xuống xa nhau). Nút "Phân tích tự động" nên full-width để dễ bấm. Sơ đồ "Notice the pattern" xếp dọc 1 cột (đã đúng hướng mobile sẵn), chỉ cần cỡ chữ và khoảng cách dòng đủ thoáng.

---

## E · Bảng tín hiệu nhận diện

| Function | Signal |
|---|---|
| First suggestion | First, |
| Second suggestion | Second, |
| Third suggestion | Third, |
| Give an example | For example, |
| Finish the paragraph | In conclusion, |
| *(pattern riêng của Expected result)* | This will.../This can... |

*(Optional, không chấm điểm: "Which suggestion do you like the most? Why?")*

> 🎨 **Desktop:** dạng thẻ tròn (pill badge) nền `--jade-deep` chữ trắng, lưới 2 cột. Chạm/hover từng thẻ hiện tooltip câu ví dụ minh hoạ.
> 📱 **Mobile:** giữ lưới 2 cột (màn hình ~380px vẫn đủ chỗ cho 2 pill/hàng, không co xuống 1 cột vì sẽ tạo danh sách quá dài phải cuộn nhiều). **Bắt buộc đổi tương tác hover → tap**, vì điện thoại không có trạng thái hover — tooltip phải bật/tắt bằng chạm (chạm lần 1 mở, chạm lại hoặc chạm ra ngoài để đóng), không dùng `:hover` trong CSS làm cơ chế chính. Tooltip nên đẩy các pill khác giãn ra thay vì đè lên nội dung phía dưới, tránh che mất pill kế tiếp.

---

## Ghi chú thiết kế chung (Part 1)

- Mobile-first — test khung ≤480px trước khi mở rộng desktop.
- Mỗi màn hình chỉ 1 tương tác chính — không để Analyzer và Suggestion Builder cùng hiện đồng thời trên 1 khung nhìn.
- Không auto-reveal — mọi lớp ẩn chỉ hiện sau hành động chủ động của học sinh.
- Giữ nguyên bảng màu Cream/Jade và font Be Vietnam Pro như Unit 1.
- Đồng bộ dữ liệu: bài mẫu ở Hook và ở mục D PHẢI là cùng 1 bài.
- **Practice Reference Pane (đúng chuẩn `02_design_tiengAnh.md` Mục 4.8b, KHÔNG dùng cơ chế "khay sticky" tự chế):** xem chi tiết mapping đầy đủ ở "Lưu ý thiết kế" cuối file.

**Điều hướng cuối Part 1:** Không có — File Lesson kết thúc tự nhiên sau mục "Ghi chú thiết kế chung (Part 1)", không có nút/link sang File Practice (theo Quy tắc mới 3).

---

### PHẦN 2 — PRACTICE (`kichban_unit2_writing_practice.html`)

#### Part 2 — Practice

## [Identify · Structure labelling]

Read the paragraph below, then decide which part of the structure each sentence belongs to.

> There are several ways our canteen can reduce food waste. First, the canteen should use real trays instead of foam boxes for lunch. For example, students can return their trays to a collection point after eating. This can create less rubbish every day. Second, the school should set up a bin for food waste. For example, we can turn the food waste into fertiliser for the school garden. This can turn waste into something useful. Third, we should encourage students to bring their own lunch boxes from home instead of buying packed meals. This can also cut down on plastic and foam waste. In conclusion, small changes to how we eat at school can make a real difference.
>
> *(118 words)*

1. "There are several ways our canteen can reduce food waste." (A. Topic Sentence / B. Suggestion / C. Example / D. Expected result / E. Concluding Sentence)
2. "First, the canteen should use real trays instead of foam boxes for lunch." (A/B/C/D/E)
3. "For example, students can return their trays to a collection point after eating." (A/B/C/D/E)
4. "This can create less rubbish every day." (A/B/C/D/E)
5. "Second, the school should set up a bin for food waste." (A/B/C/D/E)
6. "In conclusion, small changes to how we eat at school can make a real difference." (A/B/C/D/E)

**Answer: 1.A / 2.B / 3.C / 4.D / 5.B / 6.E**

Giải thích câu 1: Nêu chủ đề chung, chưa đi vào đề xuất cụ thể → Topic Sentence.
Giải thích câu 2: Có "First," và nêu 1 đề xuất → Suggestion.
Giải thích câu 3: Có "For example," và mô tả hành động cụ thể → Example.
Giải thích câu 4: "This can..." nêu kết quả của hành động vừa nêu → Expected result.
Giải thích câu 5: Có "Second," và nêu đề xuất mới → Suggestion (lặp lại đúng chức năng như câu 2, khác Point).
Giải thích câu 6: Có "In conclusion," và câu tổng kết → Concluding Sentence.

> 📱 **Mobile:** mỗi câu hỏi hiện dạng 1 thẻ riêng (không phải danh sách text liền mạch) với 5 nút lựa chọn A-E xếp thành lưới 2 cột (không xếp ngang 1 hàng 5 nút vì sẽ quá nhỏ để chạm chính xác trên màn hình hẹp). Sau khi chọn, feedback đúng/sai + giải thích hiện NGAY DƯỚI câu đó, không hiện ở cuối trang.
> 🎨 **Desktop:** nút **Submit** (`submitAndUnlock`) — mở khi cả 6 câu đã chọn đáp án, bấm mới hiện đúng/sai + giải thích.

## [Identify · Read & Extract]

Read the same paragraph above and complete the table.

| Suggestion | Example | Expected result |
|---|---|---|
| (1) ___________ | (2) ___________ | (3) ___________ |
| Set up a bin for food waste | (4) ___________ | Turn waste into something useful |
| (5) ___________ | *(không có Example riêng)* | (6) ___________ |

**Answer:**
1. Use real trays instead of foam boxes for lunch
2. Return trays to a collection point after eating
3. Create less rubbish every day
4. Turn the food waste into fertiliser for the school garden
5. Encourage students to bring their own lunch boxes from home instead of buying packed meals
6. Cut down on plastic and foam waste

Giải thích: Point 3 không có câu "For example," tách riêng — Suggestion đã đủ cụ thể nên bài mẫu gộp Example vào ngay trong câu Suggestion. Không phải Point nào cũng bắt buộc có 3 câu tách bạch.

> 📱 **Mobile:** bảng 3 cột (Suggestion/Example/Expected result) sẽ QUÁ HẸP nếu giữ nguyên dạng bảng ngang trên màn hình ≤480px — chuyển mỗi hàng của bảng thành **1 thẻ dọc** gồm 3 dòng nhãn-giá trị xếp chồng (Suggestion: ... / Example: ... / Expected result: ...) thay vì 3 cột song song. Giữ đúng thứ tự 3 Point như trên, chỉ đổi hướng trình bày.
> 🎨 **Desktop:** nút **Submit** (`submitAndUnlock`) — mở khi đủ 6 ô có nội dung, bấm mới hiện đáp án.

---

## [Structure · Passage Arrangement — Bài 1]

Put the sentences in the correct order to form a complete paragraph.

A. This can stop a lot of clean water from going to waste.
B. Second, the school should install automatic taps and put up posters to remind everyone to save water.
C. There are two simple ways our school can save water every day.
D. In conclusion, saving water only takes a few simple changes from everyone at school.
E. First, we should fix the leaking taps in the toilets and the science lab.

**Answer: C → E → A → B → D**

Giải thích: C giới thiệu chủ đề và số lượng ý ("two simple ways") → mở đầu. E có "First," → đứng ngay sau C. A dùng "This" quy chiếu lại hành động sửa vòi rò ở E → đứng ngay sau E. B có "Second," → đề xuất thứ hai. D có "In conclusion," → luôn đứng cuối.

## [Structure · Passage Arrangement — Bài 2]

Put the sentences in the correct order to form a complete paragraph.

A. Traffic around our school gate causes noise and air pollution every morning.
B. One idea is to encourage more students to walk or cycle to school instead of coming by motorbike.
C. A covered bike parking area near the gate can make this easier for everyone.
D. Another idea is a "no-motorbike day" once a month, and everyone should walk, cycle, or take the bus.
E. In conclusion, small changes to how we travel to school can make the area around the gate quieter and cleaner.

**Answer: A → B → C → D → E**

Giải thích: A nêu vấn đề chung (chưa phải đề xuất) → mở đầu. B nêu giải pháp đầu tiên nhưng KHÔNG dùng "First," mà dùng "One idea is" — tinh tế hơn Bài 1. C dùng "this" quy chiếu lại ý đi bộ/đạp xe ở B → đứng ngay sau B. D dùng "Another idea" — ngầm hiểu đã có 1 ý trước đó → chỉ đứng sau C. E có "In conclusion," → luôn đứng cuối.

*(Bài 2 khó hơn Bài 1: không có "Second/Third" tường minh, cue phải suy luận qua "this"/"another idea" thay vì sequence word trực tiếp.)*

> 🎨 **Desktop:** kéo-thả (drag-and-drop) các khối câu vào đúng thứ tự, có thanh tiến trình hiện số khối đã đặt đúng.
> 📱 **Mobile:** kéo-thả bằng ngón tay trên màn hình nhỏ dễ thao tác sai (kéo nhầm sang cuộn trang thay vì di chuyển thẻ). Đề xuất **thay drag-and-drop bằng tap-to-order**: học sinh chạm lần lượt các câu theo đúng thứ tự mong muốn (câu được chọn hiện số thứ tự 1,2,3... ngay trên thẻ), có nút "Reset" để chọn lại. Nếu vẫn giữ drag-and-drop, bắt buộc thêm `touch-action: none` lên thẻ đang kéo để chặn cuộn trang ngoài ý muốn, đồng thời phóng to thẻ đang kéo (scale nhẹ 1.05) kèm bóng đổ rõ để học sinh thấy rõ đang cầm thẻ nào.

---

## [Write · Sentence building]

Put the words in the correct order to make a complete sentence.

1. lights / the / off / in / turn / classrooms / should / we / First
2. bring / reusable / can / for example / bags / students / shopping
3. our / can / school's / this / save / energy
4. plant / the / more / could / trees / around / school / Second / playground
5. help / can / make / cleaner / this / air / the
6. recycle / should / to / encourage / we / students / Third

**Answer:**
1. First, we should turn off the lights in the classrooms.
2. For example, students can bring reusable shopping bags.
3. This can save our school's energy.
4. Second, the school could plant more trees around the playground.
5. This can help make the air cleaner.
6. Third, we should encourage students to recycle.

> 🎨 **Desktop:** các từ hiện dạng thẻ rời (word chips) để kéo-thả ráp thành câu.
> 📱 **Mobile:** tương tự Passage Arrangement — ưu tiên **tap-to-insert** (chạm từng chip theo đúng thứ tự để chúng tự nối vào dòng đáp án phía trên) thay vì kéo-thả tự do. Cho phép chạm vào 1 chip đã đặt để gỡ nó ra khỏi câu (thay vì phải kéo ngược lại đúng vị trí cũ). Chip đủ lớn (tối thiểu 36px chiều cao) để chạm chính xác.
> 🎨 **Desktop:** nút **Submit** (`submitAndUnlock`) — mở khi đủ 6 câu đã ráp, bấm mới hiện đúng/sai.

## [Write · Guided Writing — hỗ trợ đầy đủ]

Task: Your class wants to make the classroom greener. Use the information below to complete the paragraph.

| Suggestion | Example | Expected result |
|---|---|---|
| Grow small plants in reused plastic bottles | Place them on the classroom windowsill | Make the classroom look fresher and greener |
| Set up a small "class plant corner" | Students take turns watering and caring for the plants every week | Help students feel more responsible for their shared space |
| Use a digital notice board instead of paper notices | Share announcements on a screen or in the group chat | Reduce the amount of paper the class uses |

> There are three things our class can do to make our classroom greener. First, ________________________________________________ Second, ________________________________________________ Third, ________________________________________________ In conclusion, ________________________________________________

*Target: 100-130 words. Complete the paragraph and read through the whole thing.*

**Model answer (shown after submission):**

> There are three things our class can do to make our classroom greener. First, we should grow small plants in reused plastic bottles. For example, we can place them on the classroom windowsill. This can make our classroom look fresher and greener. Second, we could set up a small "class plant corner". For example, students can take turns watering and caring for the plants every week. This can help students feel more responsible for their shared space. Third, we should use a digital notice board instead of paper notices. For example, we can share announcements on a screen or in the group chat. This can reduce the amount of paper our class uses. In conclusion, these small habits can make our classroom a greener place to learn.
>
> *(127 words)*

> 📱 **Mobile:** bảng 3 cột chuyển thành thẻ dọc như đã nêu ở Read & Extract. Textarea/blank-fill nên tự giãn chiều cao theo nội dung gõ (auto-grow) thay vì cố định chiều cao rồi phải cuộn bên trong 1 khung nhỏ — cuộn lồng bên trong 1 ô nhỏ trên mobile rất khó chịu.
> 🎨 **Desktop:** nút **Submit** (`submitByWords`) — mở khi đã gõ đủ ~30-50% số từ mục tiêu (30-40 từ). Bấm Submit mới hiện Model answer qua `openModelAnswerSheet()`.

## [Write · Guided Writing — hỗ trợ giảm]

Task: Use the keywords below to write the SAME paragraph — this time without sentence starters.

| Suggestion | Example | Expected result |
|---|---|---|
| grow plants / reused bottles | windowsill | greener classroom |
| class plant corner | take turns watering | more responsible |
| digital notice board | screen / group chat | less paper |

> 💡 Turn each row into a full sentence, following the same 4-part structure as the guided version above (Topic Sentence → 3 Supporting Points → Concluding Sentence).

*Target: 100-130 words.*

**Model answer (shown after submission)** — cùng bài với bản hỗ trợ đầy đủ:

> There are three things our class can do to make our classroom greener. First, we should grow small plants in reused plastic bottles. For example, we can place them on the classroom windowsill. This can make our classroom look fresher and greener. Second, we could set up a small "class plant corner". For example, students can take turns watering and caring for the plants every week. This can help students feel more responsible for their shared space. Third, we should use a digital notice board instead of paper notices. For example, we can share announcements on a screen or in the group chat. This can reduce the amount of paper our class uses. In conclusion, these small habits can make our classroom a greener place to learn.
>
> *(127 words)*

*(Trước đó block này chỉ có bảng từ khoá — không có textarea/Model answer/Submit nào. Đã bổ sung đầy đủ theo đúng chuẩn Gated Reveal.)*

> 🎨 **Desktop:** 1 textarea trống hoàn toàn (không có khung câu dẫn). Nút **Submit** (`submitByWords`) — mở khi đã gõ đủ ~30-50% số từ mục tiêu (30-40 từ). Bấm Submit mới hiện Model answer qua `openModelAnswerSheet()`.
> 📱 **Mobile:** textarea auto-grow, Model answer dạng bottom-sheet.

## [Write · Correct the mistake]

Find and correct 6 mistakes in the paragraph below.

> There is [1] three things our class can do to make our classroom greener. First we should [2] grow small plant [3] in reused plastic bottles. Students can place them on the classroom windowsill. This make [4] our classroom look fresher and greener. Second, we could set up a small "class plant corner," students could take turns watering and caring for the plants every week [5]. Third, we should used [6] a digital notice board instead of paper notices.

> ⚠️ **QUY TẮC BẮT BUỘC — định dạng MCQ khi build (đã từng bị build sai, gây lỗi hiển thị nặng — xem
> ghi chú cuối mục này):** Mỗi số lỗi `[1]`-`[6]` trong đoạn văn trên KHI TAP VÀO chỉ mở đúng 1 câu
> hỏi MCQ theo cấu trúc bảng dưới đây — hiển thị đúng NGUYÊN VĂN cột "Câu hỏi hiển thị" (tiếng Anh
> thuần, KHÔNG có nhãn "Lỗi [X]:" hay bất kỳ nhãn tiếng Việt nào đứng trước). Cột "Đáp án" (4 lựa
> chọn, tất cả bằng tiếng Anh, bao gồm 1 phương án "No change needed") lấy đúng nguyên văn, không tự
> viết lại bằng tiếng Việt. Cột "Giải thích" hiển thị SAU khi học sinh chọn — cột này mới được viết
> tiếng Việt, đúng quy tắc chung của toàn bộ hệ thống (Answer bằng tiếng Anh, Explain bằng tiếng Việt).

| # | Câu hỏi hiển thị (tiếng Anh, KHÔNG có nhãn "Lỗi [X]:") | 4 lựa chọn (tiếng Anh) | Đáp án đúng | Giải thích (tiếng Việt) |
|---|---|---|---|---|
| 1 | "There is three things our class can do to make our classroom greener." | There is → There are · There is → There was · There is → There have · No change needed | There is → There are | Chủ ngữ phía sau "three things" là danh từ số nhiều → dùng "There are". |
| 2 | "First we should grow small plants..." | First we should → First, we should · First we should → First of we should · First we should → Firstly, should we · No change needed | First we should → First, we should | Thiếu dấu phẩy sau từ nối trình tự "First,". |
| 3 | "...grow small plant in reused plastic bottles." | small plant → small plants · small plant → a small plant · small plant → small planted · No change needed | small plant → small plants | Trồng nhiều cây trong các chai nhựa → dùng danh từ số nhiều "small plants". |
| 4 | "This make our classroom look fresher..." | This make → This can make · This make → This making · This make → This made · No change needed | This make → This can make | Theo công thức kết quả kỳ vọng "This can/will + V" → sửa thành "This can make". |
| 5 | "...class plant corner," students could take turns watering..." | Add "For example," before "students could take turns..." · Change the comma to a question mark · Remove the word "students" · No change needed | Add "For example," before "students could take turns..." | Lỗi comma splice nối 2 mệnh đề độc lập mà thiếu từ dẫn chứng → tách câu và thêm "For example,". |
| 6 | "...we should used a digital notice board..." | we should used → we should use · we should used → we should using · we should used → we should to use · No change needed | we should used → we should use | Sau động từ khuyết thiếu modal verb "should" đi với động từ nguyên mẫu không chia → "should use". |

> 🐞 **Lỗi đã xảy ra thực tế khi build (ghi lại để không lặp lại):** Bản build trước đã tự chế thêm
> nhãn `"Lỗi [5]: "` (và tương tự cho cả 6 câu) đứng trước phần trích dẫn tiếng Anh trong câu hỏi —
> nhãn nội bộ này không được phép xuất hiện trong nội dung học sinh nhìn thấy, đúng "Quy tắc kịch bản
> sạch" (không đưa nhãn/ghi chú nội bộ vào output). Cùng bản build đó còn tự viết lại 3 lựa chọn của
> câu 5 bằng tiếng Việt ("Thêm...", "Đổi...", "Bỏ từ...") thay vì tiếng Anh như 5 câu còn lại — vi
> phạm quy tắc "câu hỏi/đề bài tuyệt đối chỉ tiếng Anh, không trộn Anh-Việt trong 1 câu". Bảng ở trên
> đã viết tường minh đủ cả 6 câu để loại trừ khả năng người build phải tự suy diễn định dạng.

> 📱 **Mobile:** các số lỗi [1]-[6] cần đủ tương phản màu để nhìn thấy giữa đoạn text dài trên màn hình nhỏ (dùng nền `--cream-3` highlight thay vì chỉ số nhỏ trong ngoặc). Khi chạm vào số lỗi, hiện popup sửa lỗi dạng bottom-sheet (trượt lên từ đáy màn hình) thay vì popup giữa màn hình — thao tác quen thuộc hơn trên mobile và không che mất phần văn bản đang đọc.

## [Write · Write a paragraph]

Task: Write a COMPLETE paragraph (Topic Sentence + 3 Supporting Points with First/Second/Third + For example + Expected result + Concluding Sentence) giving suggestions to improve the environment in YOUR OWN school or neighbourhood.

**Idea prompts:**
- Think about a problem you notice at your school or in your neighbourhood (e.g. litter, wasted electricity, plastic use, lack of green spaces, noise).
- What could people do about it?
- What would happen if they did?

> 💡 There's no table to guide you this time. Before you start, note down: the problem, your first suggestion + example + result, and your second suggestion + example + result.

*Target: 100-130 words.*

**Model answer (shown after submission):**

> There are two things people in my neighbourhood can do to reduce litter. First, the local shops could stop giving out free plastic bags. For example, they could sell cheap reusable bags at the counter instead. This can reduce the amount of plastic waste on the street. Second, the neighbourhood committee could set up more rubbish bins along the main road. For example, they could place a bin every 100 metres near the market and bus stop. This can encourage people to throw litter in the right place instead of on the ground. In conclusion, a few simple changes could make our neighbourhood much cleaner.
>
> *(103 words)*

*(Trước đó block này ghi "No model answer — this is independent writing" — đã bổ sung Model answer mới theo đúng chuẩn Gated Reveal.)*

> 🎨 **Desktop:** textarea trống, word counter trực tiếp. Nút **Submit** (`submitByWords`) — mở khi đã gõ đủ ~30-50% số từ mục tiêu (30-40 từ). Bấm Submit mới hiện Model answer qua `openModelAnswerSheet()`.
> 📱 **Mobile:** textarea auto-grow, Model answer dạng bottom-sheet.

---

#### Part 3 — Production Writing

*Bài đánh giá cuối unit — độc lập với Free Writing đã có ở Practice (Mục 8 template). Chủ đề dùng ở đây là chủ đề HOÀN TOÀN MỚI, không trùng bất kỳ chủ đề nào đã dùng ở Part 1 hay Part 2.*

## Guided Writing

Task: Your school library wants to become greener. Use the information below to complete the paragraph.

| Suggestion | Example | Expected result |
|---|---|---|
| Use e-books instead of printing paper handouts | Students can read their lessons on a tablet or a laptop | Save a lot of paper every semester |
| Start a book-sharing corner | Students can donate old books and borrow books from classmates for free | Help the school buy fewer new books |
| Add a few small plants to the reading corner | Put the plants on the windowsill near the bookshelves | Make the library a nicer, greener place to read |

> There are three things our library can do to become greener. First, ________________________________________________ Second, ________________________________________________ Third, ________________________________________________ In conclusion, ________________________________________________

*Target: 100-130 words.*

**Model answer (shown after submission):**

> There are three things our library can do to become greener. First, we should use e-books instead of printing paper handouts. For example, students can read their lessons on a tablet or a laptop. This can save a lot of paper every semester. Second, the library could start a book-sharing corner. For example, students can donate old books and borrow books from classmates for free. This can help the school buy fewer new books. Third, we should add a few small plants to the reading corner. For example, we can put the plants on the windowsill near the bookshelves. This can make the library a nicer, greener place to read. In conclusion, a few simple changes could turn our library into a much greener space.
>
> *(125 words)*

**Self-check (không phải Athena chấm — tự đối chiếu sau khi viết):**
- Have I included 3 Supporting Points, each with a Suggestion + Example + Expected result?
- Have I used First/Second/Third and For example correctly?
- Do I have a clear Topic Sentence and Concluding Sentence?

> 🎨 **Desktop:** giữ nguyên dạng outline điền khuyết + textarea. Nút **Submit** (`submitByWords`) — mở khi đã gõ đủ ~30-50% số từ mục tiêu (30-40 từ). Bấm Submit mới hiện Model answer qua `openModelAnswerSheet()`, sau đó hiện Self-check ngay dưới (dạng checklist tick thật, không tự động chấm điểm).
> 📱 **Mobile:** bảng 3 cột → thẻ dọc như các mục trước. Textarea auto-grow. Checklist tick dùng ô vuông đủ lớn (tối thiểu 24×24px) để chạm chính xác bằng ngón tay.

## Free Writing — gửi Athena chấm

Task: Choose ONE place near you (your street, a local park, a market, a bus stop area...) and write a COMPLETE paragraph (Topic Sentence + 3 Supporting Points with First/Second/Third + For example + Expected result + Concluding Sentence) giving suggestions to make it greener.

**Idea prompts:**
- Choose ONE place near you (your street, a local park, a market, a bus stop area...).
- What environmental problem does this place have?
- What can someone do about it? What will happen if they do?

*Target: 100-130 words. (Không có model answer — đây là bài viết độc lập, chấm bằng Athena.)*

> 🎨 **Desktop:** giao diện gồm: (1) 1 ô textarea lớn để học sinh viết trực tiếp; (2) bộ đếm từ trực tiếp (live word counter) cập nhật theo từng ký tự gõ, hiển thị dạng "XX từ / mục tiêu 100-130 từ"; (3) nút "✓ Nộp bài" — khi bấm, nút chuyển trạng thái disabled và toàn bộ khối phản hồi hiện lên với trạng thái chờ "⏳ Đang gửi cho Athena..."; (4) sau khi Athena trả kết quả, thay khối chờ bằng 1 lưới 4 ô rubric (Task Achievement / Organisation / Language Use / Length & Fluency, mỗi ô hiển thị điểm dạng "X/4") và 1 khối nhận xét ngắn bằng tiếng Việt bên dưới lưới điểm.
> 📱 **Mobile:** textarea auto-grow theo nội dung, KHÔNG cuộn lồng bên trong khung cố định. Bộ đếm từ nên đặt sticky ngay phía trên bàn phím ảo (hoặc ngay dưới textarea, không đặt tít cuối trang) để học sinh luôn thấy được tiến độ mà không phải cuộn xuống kiểm tra. Nút "Nộp bài" full-width, đặt ngay dưới bộ đếm từ để thao tác 1 tay thuận tiện. Lưới 4 ô rubric trên màn hình ≤480px xếp **2×2** (không xếp 1 hàng 4 ô sẽ quá nhỏ) — đúng nguyên tắc "tối đa 2 cột trên mobile". Khối nhận xét tiếng Việt hiện ngay dưới lưới điểm, đủ dòng để không bị cắt.
> 🎨 **NGUYÊN TẮC BẮT BUỘC** (đúng tinh thần đã áp dụng ở Unit 1): KHÔNG được tự bịa điểm số hay nhận xét giả trong lúc chưa nối API chấm thật của Athena — nút Nộp bài chỉ dừng ở trạng thái "Đang gửi" cho đến khi có phản hồi thật từ hệ thống. Khi dựng HTML, để lại điểm nối API rõ ràng (TODO) đúng như file Unit 1 đã làm, không hard-code sẵn 1 bộ điểm mẫu để hiển thị ngay.
> Word count mục tiêu lấy đúng theo Mục 3 (100-130, không phải 40-70 như ví dụ Unit 1) — khi dựng HTML nhớ đổi lại hằng số `WRITE_TARGET_MIN`/`WRITE_TARGET_MAX` cho khớp Unit 2.

## Writing Rubric (Athena chấm Free Writing)

| Criteria | Scale | Description |
|---|---|---|
| 1. Task Achievement | 1-4 | Includes 3 suggestions, each with an example and a result/benefit |
| 2. Organisation | 1-4 | Clear topic sentence and concluding sentence; correct use of sequence words (First/Second/Third) and "For example" |
| 3. Language Use | 1-4 | Accurate grammar, appropriate use of the vocabulary/structures taught |
| 4. Length & Fluency | 1-4 | Reaches 100-130 words, sentences are natural and well-connected |

## Self-evaluation

- ☐ I can identify the different parts of a suggestion paragraph (Topic Sentence/Supporting Points/Concluding Sentence).
- ☐ I can complete sentences using suitable sequence words and examples (First/Second/Third, For example).
- ☐ I can arrange sentences into a well-structured suggestion paragraph.
- ☐ I can write a complete paragraph giving suggestions to improve the environment, using sequence words and examples.
- ☐ My writing reaches the required word count (100-130 words) and reads naturally.

> 📱 **Mobile:** checklist dùng ô vuông tick đủ lớn (≥24×24px), mỗi mục đủ khoảng cách dòng (line-height ≥1.6) để tránh chạm nhầm sang mục kế bên.

---

### ⚠️ Lưu ý thiết kế (bắt buộc đọc trước khi build)
- Mobile-first: build/test ở khung ≤480px trước khi mở rộng desktop.
- **BẮT BUỘC có Practice Reference Pane chuẩn** (đã sửa lỗi — bản trước tự chế cơ chế "khay sticky ở đáy màn hình" thay vì dùng đúng component đã chốt; Writing không thuộc diện ngoại lệ bỏ Reference Pane, xem `PROMPT_TEMPLATE_WRITING` Mục 0 v8.0). Chia đôi màn hình: desktop 2 cột trái/phải, mobile 2 khối trên/dưới có 3 nút chuyển chế độ xem + nút "Gom lại" (⟨⟨). **Mapping tab theo từng phase (đúng `02_design_tiengAnh.md` Mục 4.8b v3.4):**
  - **Identify + Structure:** 2 tab — **Tab "📄 Bài đọc"** (dùng lại ĐÚNG bài "School Canteen Passage" — bài đọc chính của Identify, KHÔNG phải bài mẫu Part 1 "Winning paragraph" về trường học xanh nói chung) + **Tab "🔗 Bảng tín hiệu"** (mục E ở Part 1).
  - **Write + Production:** bỏ hẳn tab Bài đọc, **CHỈ còn Tab "🔗 Bảng tín hiệu"** — vì từ đây học sinh tự viết, không còn bài đọc cụ thể để đối chiếu.
- File Lesson (PHẦN 1) kết thúc tự nhiên sau "Ghi chú thiết kế chung (Part 1)" — không có nút/link sang File Practice.
- File Practice bắt đầu tự nhiên từ Identify — không có nút "Quay lại Bài học".
- Đồng bộ dữ liệu: bài mẫu "Winning paragraph" ở Hook và ở mục D phải là cùng 1 bài (đã đúng trong bản gốc).
- **Token màu cảnh báo (viền ví dụ SAI ở mục B.1/B.3, icon ⚠️):** ĐÃ có sẵn trong hệ thống — dùng đúng `--warning`/`--warning-bg` (không cần tự đặt `--warning-soft` như TODO trước đây, hệ Jade/Cream đã có token cảnh báo chính thức từ trước, chỉ là kịch bản bản trước chưa tra đúng bảng token).

### Ghi chú cho Giai đoạn 2 (Design)
- Đọc `02_design_tiengAnh.md` mục: 4.15 (Writing components), 9.6 (Athena rubric chấm Free Writing), 4.7 (Self-assessment), **9.17 (Gated Reveal — bắt buộc cho MỌI nút "Xem model answer" trong file này: Guided Writing hỗ trợ đầy đủ/hỗ trợ giảm, Write a paragraph, Production Guided Writing — khoá đến khi học sinh đã gõ đủ ~30-50% số từ mục tiêu 100-130 từ)**; xem code mẫu `submitByWords()`/`openModelAnswerSheet()` tại `03_engine_tiengAnh.md` Mục 1.18.
- Mục 4.8b (Reference Pane): 2 tab, mapping theo phase — xem chi tiết ở "Lưu ý thiết kế" phía trên, KHÔNG dùng lại cơ chế "khay sticky" của bản trước.
