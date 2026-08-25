# 🎮 ENGINE TIẾNG ANH — Pattern Kỹ Thuật Cho Tương Tác Module — v1.11

> **Mới ở v1.11:** khoá cứng giọng đọc TTS `en-GB` ở mọi hàm `speak()`/`SpeechSynthesisUtterance`
> trong file này (không đổi sang `en-US`) — xem ghi chú tại từng hàm; đồng bộ với nguyên tắc 12/13
> (mới) ở `02_design_tiengAnh.md` Mục 0 về giọng đọc + chống lặp pattern khi soạn data câu hỏi.

> **Mới ở v1.10:** thêm 3.6 Vocabulary Word-Mastery Tracking & Recap — pattern đọc nhãn kỹ thuật
> `[Trạm/Bài · Từ]` từ kịch bản Vocabulary (từ `PROMPT_TEMPLATE_VOCABULARY_v5_2.md` trở lên — kiến
> trúc mới "Warm-up → Flashcards → 4 Trạm → Extra Practice → Recap"), tính đúng/sai theo TỪNG TỪ
> xuyên suốt cả 4 Trạm lẫn Extra Practice, và render Recap ĐỘNG cuối bài — thay hẳn cơ chế
> Self-evaluation tĩnh cũ (vốn chỉ áp dụng cho Practice 3 gói NB/TH/VD, nay Vocabulary không còn
> dùng khung đó). Các module KHÁC (Grammar/Reading/Writing...) vẫn dùng Self-evaluation tĩnh như cũ
> — 3.6 CHỈ áp dụng cho module Vocabulary theo kiến trúc mới.

> **Mới ở v1.9:** thêm 1.16 Before/After Comparison Slider — pattern kỹ thuật tương ứng component
> 4.18 ở file `02_design_tiengAnh.md` (fix bắt buộc `touch-action:none` +
> `e.preventDefault()`/`{ passive:false }` để tránh kéo bị cuộn cả trang trên mobile). Đồng thời
> sửa lại 1.3 (trước ghi "Drag & Drop DOM") — mục này còn sót cơ chế kéo-thả bằng pointer events,
> mâu thuẫn với quyết định "không dùng kéo-thả" đã chốt ở `02_design_tiengAnh.md` Nguyên tắc 4 và
> component 4.12 (Tap-to-Match). Xem chi tiết ở 1.3.

> 🚫 **CẢNH BÁO TOÀN CỤC — LỖI THẬT ĐÃ GẶP:** mọi từ/câu ví dụ trong file này (đặc biệt PHẦN 1.10)
> chỉ để MINH HOẠ CẤU TRÚC DỮ LIỆU, KHÔNG PHẢI nội dung bài học — tuyệt đối không copy/tái sử dụng
> khi build. Đã xảy ra lỗi thật: AI build tool đọc ví dụ minh hoạ trong file design/engine rồi tự
> động THAY nội dung bài học người dùng cung cấp bằng chính nội dung ví dụ, khiến bài build ra khác
> hẳn kịch bản gốc. Nội dung thật 100% lấy từ kịch bản/file đính kèm của người dùng — xem chi tiết ở
> `02_design_tiengAnh.md` Mục 0 (cảnh báo toàn cục ngay sau nguyên tắc 10).

> **v1.10** — lịch sử thay đổi đầy đủ qua từng version xem `00_changelog_tiengAnh.md`. File này chỉ giữ quy tắc hiện hành.


> **Mục đích:** Pattern kỹ thuật cho tương tác tiếng Anh — click-reveal, tap-to-match,
> audio/ghi âm, hotspot ảnh, model 3D, before/after slider
> **Dùng kèm:** `01_scenario_builder_tiengAnh.md` + `02_design_tiengAnh.md`
> **Đọc file này khi:** Build tương tác nối cột / audio / ghi âm / hotspot / 3D / before-after slider

---

## 🤖 TRIGGER — AI ĐỌC PHẦN NÀO KHI NÀO

Đọc phần tương ứng khi kịch bản có từ khoá sau — không đọc toàn bộ file mỗi lần:
- **Click-reveal/collocation:** "click để hiện nghĩa", "highlight collocation" → PHẦN 1.1–1.2
- **Nối cột/ghép cặp (từ↔nghĩa):** "nối cột", "ghép cặp", "matching" → PHẦN 1.3 (Tap-to-Match —
  **KHÔNG** dùng kéo-thả, xem cảnh báo trong mục; nếu kịch bản/bản tham khảo ghi "drag", "kéo thả"
  cho dạng nối cột thì vẫn build bằng tap-to-select, không build đúng chữ "drag" theo nghĩa đen)
- **Word order/tiles:** "sắp xếp từ", "word tiles" → PHẦN 1.4
- **Hotspot:** "click vào ảnh", "hotspot", "scene tương tác" → PHẦN 1.5 (điểm nhỏ, marker có sẵn)
  hoặc **1.5b (vùng/box — dùng cho vật hình khối lớn: chai nước, laptop, thùng rác...)**
- **Prediction/Hook dự đoán/Warm-up khảo sát:** "dự đoán", "prediction", "không chấm điểm",
  "warm-up khảo sát", "not right or wrong answer" → PHẦN 1.6
- **Hội thoại nhiều lượt:** "hiện tiếp", "progressive reveal", "chat bubble" → PHẦN 1.7
- **Tìm/đánh dấu từ trong câu:** "mark the blend", "gạch từ trong câu", "tìm từ chứa âm/blend" →
  PHẦN 1.8 (khác 1.2 — 1.8 KHÔNG phản hồi real-time, chấm khi bấm "Kiểm tra")
- **Ảnh Hook mở màn full-screen:** "ảnh hook", "ảnh mở đầu", "full-screen", "fade-out sang canvas/
  Hero", "hình ảnh AI-generated ở đầu module" → PHẦN 1.9 (khác 1.6 — 1.9 KHÔNG có lựa chọn, chỉ là
  màn chuyển cảnh trước khi vào Hero/canvas)
- **Pronunciation Difference/Odd-one-out có "phần gạch chân"/"underlined part":** "chọn từ có phần
  gạch chân", "underlined part", "khác nhóm phụ âm", "cùng nhóm âm" → PHẦN 1.10 (BẮT BUỘC, không
  dùng MCQ thường ở đây — phải gạch chân đúng cụm âm bằng index {start,end}, không đoán substring)
- **Strategy Reveal/dạy chiến thuật đọc hiểu:** "STRATEGY REVEAL", "dạy chiến thuật", "so sánh 2 kỹ
  năng", "worked-example recap" → PHẦN 1.11 (chọn đúng biến thể: 1 kỹ năng → cũng đọc 1.12; nhiều kỹ
  năng song song → cũng đọc 1.13)
- **Auto-scroll + highlight đoạn văn / hiệu ứng quét dòng:** "scrollToAndHighlight", "quét đoạn",
  "scan effect", "liên kết bước với đoạn văn" → PHẦN 1.12
- **2 cột so sánh / compare cards:** "2 cột song song", "compare cards", "so sánh song song 2 kỹ
  năng" (khi KHÔNG có Reference Pane liền mạch) → PHẦN 1.13
- **Summary Card / icon Recap / lật lại xem thông tin cũ:** "Summary Card", "Quick Recap", "icon
  💡", "mang theo được", "lật lại xem lại" → PHẦN 1.14
- **Reveal từ vựng theo Level/từ khó bổ trợ:** "text-reveal", "từ khó bổ trợ", "reveal theo level",
  "nghĩa tiếng Việt dưới popup" → PHẦN 1.15 (mở rộng của 1.1, chỉ dùng ở Practice)
- **Before/After Slider/kéo so sánh:** "before/after", "trước/sau", "kéo so sánh", "slider so sánh",
  "then vs now" → PHẦN 1.16 (khác 1.3 — đây là NGOẠI LỆ DUY NHẤT được phép "kéo" thật, xem cảnh báo
  touch-action trong mục; chỉ dùng làm hook trực quan, không chấm điểm)
- **Demo dẫn dắt gõ chữ dần + sơ đồ mọc dần:** "gõ dần", "typewriter", "demo mẫu trước khi tự làm",
  "mọc thêm nhánh", "cây mọc dần" → PHẦN 1.17 (dùng cùng Idea Diagram — component 4.21 file design;
  chỉ đọc, không chấm điểm, xem `prefers-reduced-motion`)
- **Sơ đồ cây phát triển ý/brainstorm phân tầng:** "mindmap", "sơ đồ tư duy", "sơ đồ cây", "gốc→
  nhánh→lá", "brainstorm diagram" → component 4.21 file design (KHÔNG build bằng SVG/toạ độ JS tự
  do — dùng đúng cấu trúc Flexbox cố định của 4.21)
- **Adaptive/ẩn nhãn mức độ:** "adaptive", "tự chọn mức theo performance", "ẩn Easy/Medium/
  Difficult", "routing ngầm" → PHẦN 3.5 (khác Level Tabs 4.5 chuẩn — chỉ dùng khi kịch bản nêu rõ
  yêu cầu, không tự áp dụng cho module khác)
- **Recap Vocabulary theo từ / "4 Trạm" / Extra Practice:** "Words you've mastered", "Words to
  review", "nhãn Trạm · Từ", "Recap động", "4 Trạm" → PHẦN 3.6 (CHỈ áp dụng cho module Vocabulary
  kiến trúc mới — không áp dụng Self-evaluation tĩnh cũ của module này nữa)
- **Audio:** "audio player", "nghe", "transcript" → PHẦN 2.1
- **Ghi âm:** "ghi âm", "record", "microphone" → PHẦN 2.2
- **AI roleplay:** "AI đóng vai", "hỏi lại", "nhiều lượt" → PHẦN 2.3
- **Đếm item mở khoá:** "xem hết", "mở khoá sau khi xem" → PHẦN 3.4
- **3D:** "model 3D", "model-viewer", "Meshy" → PHẦN 4.1
- **Phát âm từ đơn/Listen-and-Circle:** "phát âm mẫu", "nghe và khoanh", "listen and circle",
  "text-to-speech" → PHẦN 4.2 (dùng cho Pronunciation mức Nhận biết/Thông hiểu — phát 1 từ, học
  sinh chọn đúng từ nghe được trong 3 lựa chọn; KHÔNG dùng cho bài nghe dài/transcript, xem PHẦN 2.1)

Khác với Toán (canvas + physics), tiếng Anh hầu hết dùng **DOM thuần** (div/
button/input), không cần canvas — trừ khi kịch bản có yêu cầu vẽ đặc biệt
(hiếm gặp). Vì vậy KHÔNG áp dụng pattern hit-detection/vector-math của Toán
vào đây — hit detection ở đây đơn giản hơn nhiều vì browser tự lo qua sự kiện
click/touch trên element thật.

---

## PHẦN 1 — INPUT PATTERNS (DOM-based)

### 1.1 Click-Reveal Nghĩa Từ (BẮT BUỘC — pattern nền tảng nhất)

```javascript
// Toggle 1 ô nghĩa
function togM(i) {
  const el = document.getElementById('mean-' + i);
  el.classList.toggle('m-blur');
  el.classList.toggle('m-clear');
}

// Toggle tất cả — dùng cho nút "Hiện tất cả nghĩa"
let allRevealed = false;
function toggleAllM() {
  allRevealed = !allRevealed;
  document.querySelectorAll('.m-blur, .m-clear').forEach(el => {
    el.classList.toggle('m-blur', !allRevealed);
    el.classList.toggle('m-clear', allRevealed);
  });
  document.getElementById('vtoggle-btn').textContent =
    allRevealed ? 'Ẩn tất cả nghĩa' : 'Hiện tất cả nghĩa';
}
```
```css
.m-blur{filter:blur(4px);cursor:pointer;user-select:none}
.m-clear{cursor:default}
```
Đếm "X/Y từ đã xem" (dùng ở Reading tooltip): tăng biến đếm mỗi lần `togM`
chuyển từ `.m-blur` → `.m-clear` lần đầu tiên (dùng `Set` lưu index đã xem,
không đếm trùng khi click lại).

### 1.2 Click-Timed-Game — Chọn Cụm Từ Đúng/Sai Trong Đoạn Văn

```
Nguồn: Getting Started M1 — highlight collocation, timer 60s.
Pattern:
  1. Đoạn văn được tách thành các <span class="kw" data-correct="true/false">
     bao quanh MỖI cụm từ có thể click (không phải toàn bộ câu)
  2. Timer đếm ngược, hết giờ tự khoá input
  3. Click đúng → class .ok (xanh) + tăng counter đúng
     Click sai → class .no (đỏ) + tăng counter sai, KHÔNG khoá cụm đó lại
     (cho phép học sinh nhận ra và click tiếp cụm khác)
  4. Hết giờ hoặc hết cụm → hiện result-box (đúng/sai/bỏ qua)
```
```javascript
let timeLeft = 60, timerInt = null;
function startHL() {
  timerInt = setInterval(() => {
    timeLeft--;
    document.getElementById('hl-bar').style.width = (timeLeft/60*100) + '%';
    if (timeLeft <= 0) { clearInterval(timerInt); lockHL(); showResultHL(); }
  }, 1000);
}
function clickKW(el, isCorrect) {
  if (el.classList.contains('done')) return; // đã click rồi thì bỏ qua
  el.classList.add('done', isCorrect ? 'ok' : 'no');
  isCorrect ? okCount++ : badCount++;
}
```
> ⚠️ Luôn có nút "Reveal đáp án" sau khi hết giờ/hoàn thành — hiện rõ cụm nào
> đúng/sai/bỏ qua, đúng nguyên tắc "giải thích kiến thức" ở file 01, không
> chỉ hiện số điểm.

### 1.3 Tap-to-Match — Nối 2 Cột (KHÔNG dùng Drag & Drop)

> 🚫 **Đã sửa ở v1.9 — mục này trước đây ghi "Drag & Drop DOM" kèm code kéo-thả bằng pointer
> events.** Đó là pattern CŨ, đã bị chốt bỏ khi file design ban hành Nguyên tắc 4 (Mục 0) và
> component 4.12: **không dùng kéo-thả dưới bất kỳ hình thức nào**, kể cả bản pointer-events "giả
> lập kéo" như code cũ ở đây — vì vẫn giữ nguyên nhược điểm gốc (ngón tay che mất điểm thả, dễ thả
> nhầm trên màn hình nhỏ). Nếu kịch bản hoặc bản tham khảo ghi "kéo thả", "drag", "nối cột" cho
> dạng bài này, **vẫn build bằng tap-to-select** — chạm 1 chip cột trái, rồi chạm chip tương ứng
> cột phải để ghép cặp.
>
> Code kỹ thuật đầy đủ (HTML/CSS/JS) đã có sẵn ở `02_design_tiengAnh.md` component **4.12** — dùng
> nguyên khối đó, không viết lại phiên bản khác ở đây để tránh 2 nguồn code lệch nhau. Phần dưới chỉ
> là lưu ý kỹ thuật bổ sung không có trong 4.12.

```
Khác Toán (kéo-thả trên canvas, cần tự tính hitbox) — tiếng Anh không có bài nối nào dùng kéo-thả
nữa, kể cả dạng DOM. Tap-to-match hoạt động giống hệt nhau trên chuột lẫn cảm ứng nên không cần xử
lý touch riêng như pattern kéo-thả cũ (không còn `pointerdown`/`pointermove`/`pointerup`, không còn
"ghost" đi theo ngón tay) — đơn giản hơn hẳn về code lẫn thao tác học sinh.
```

> ⚠️ **Lưu ý khác biệt với 1.8 (Tap-to-Select-in-Sentence) mà AI cần cân nhắc khi soạn kịch bản:**
> code mẫu ở 4.12 chấm đúng/sai **NGAY khi tap** từng cặp (real-time, không gate bằng nút "Kiểm
> tra"), khác với nguyên tắc "chống dò mù — chấm khi bấm Kiểm tra" áp dụng ở 1.8. Đây
> là lựa chọn có chủ đích cho matching 1-1 (mỗi lần tap là 1 phán đoán độc lập, không dò được đáp án
> của các cặp còn lại từ phản hồi), nhưng CHƯA được ghi thành quy tắc rõ ràng ở file design — nếu
> thấy kịch bản nào có vẻ dễ bị "dò mù" qua matching nhiều cặp liên tiếp, hỏi lại người soạn thay vì
> tự quyết.

### 1.4 Click-to-Order — Word Tiles Xây Câu

```
Khác kéo-thả tự do: học sinh CLICK các từ theo đúng thứ tự (không kéo) —
đơn giản hơn trên mobile, và tự nhiên hạn chế "dò mù" vì phải chọn tuần tự.

Pattern:
  1. Render các "tile" từ ở trạng thái xáo trộn thứ tự ban đầu
  2. Click 1 tile → chuyển vào "câu đang xây" (hàng trên), tile gốc mờ đi
  3. Click tile trong câu đang xây → trả về vị trí gốc (cho phép sửa)
  4. Đủ hết tile → tự động enable nút "Kiểm tra"
```
```javascript
let builtSentence = [];
function tapTile(word, idx) {
  builtSentence.push({word, idx});
  document.getElementById('tile-' + idx).classList.add('used');
  renderBuiltSentence();
  if (builtSentence.length === totalTiles) enableCheck();
}
function untapTile(pos) {
  const removed = builtSentence.splice(pos, 1)[0];
  document.getElementById('tile-' + removed.idx).classList.remove('used');
  renderBuiltSentence();
}
```

### 1.5 Hotspot Trên Ảnh Scene (Hình thức B — file 01)

```
BẮT BUỘC dùng % thay vì px cho vị trí hotspot — ảnh scale theo màn hình,
hotspot đặt bằng px sẽ lệch vị trí trên mobile/tablet.
```
```html
<div class="scene-wrap" style="position:relative;width:100%">
  <img src="scene.jpg" style="width:100%;display:block;border-radius:var(--radius-lg)">
  <button class="hotspot" style="left:32%;top:48%" onclick="revealHotspot(0)">1</button>
</div>
```
```css
.scene-wrap{position:relative}
.hotspot{
  position:absolute; transform:translate(-50%,-50%);
  width:28px;height:28px;border-radius:50%;
  background:var(--accent); color:#fff; border:2px solid var(--cream);
  box-shadow:0 2px 8px rgba(20,67,47,.18); cursor:pointer; font-weight:700;
}
.hotspot.done{background:var(--jade-deep)}
```
```javascript
function revealHotspot(i) {
  document.getElementById('hotspot-' + i).classList.add('done');
  document.getElementById('hotspot-panel-' + i).style.display = 'block';
  hotspotSeen.add(i);
  updateHotspotCounter(); // "đã khám phá X/Y điểm"
}
```

> ⚠️ **Dùng hotspot điểm (nút tròn 28px) CHỈ khi ảnh có sẵn 1 marker/icon nhỏ đặt lộ ra trên scene**
> (VD 1 dấu chấm số thứ tự đặt sẵn trên ảnh). **KHÔNG dùng hotspot điểm cho vật có hình khối lớn**
> (chai nước, laptop, thùng rác...) — học sinh sẽ tap vào bất kỳ đâu trên thân vật (theo trực giác
> tự nhiên), nếu vùng tap chỉ là 1 điểm 28px thì phần lớn diện tích vật KHÔNG bấm được, gây cảm
> giác "tap đúng vật mà không phản hồi gì". Với vật có hình khối rõ (đa số case Reading/Speaking
> dùng scene minh hoạ phòng/môi trường), dùng biến thể **Hotspot Vùng (Box)** ngay dưới đây.

#### 1.5b Hotspot Vùng (Box) — cho vật có hình khối lớn trên scene

```
Thay 1 điểm bằng 1 vùng chữ nhật vô hình phủ đúng khung vật (bounding box, đo % left/top/width/
height trực tiếp trên ảnh thật — không đoán). Tap bất kỳ đâu trong vùng đều tính là chọn đúng vật
đó. Không cần nút marker hiện ra (giữ ảnh sạch, không lộ đáp án bằng vị trí nút) — thêm 1 hiệu ứng
highlight nhẹ (outline sáng lên 300ms) ngay khi tap để xác nhận "đã bấm đúng vùng này", tránh cảm
giác tap vào "không khí".
```
```html
<div class="scene-wrap" style="position:relative;width:100%">
  <img src="scene.jpg" style="width:100%;display:block;border-radius:var(--radius-lg)">
  <div class="hotspot-zone" data-id="0"
       style="left:22%;top:35%;width:28%;height:27%"
       onclick="revealZone(this)"></div>
</div>
```
```css
.hotspot-zone {
  position: absolute; cursor: pointer;
  /* để trong suốt hoàn toàn ở trạng thái nghỉ — KHÔNG viền/nền, giữ ảnh sạch */
  background: transparent;
}
.hotspot-zone.tapped {
  outline: 3px solid var(--accent); border-radius: 8px;
  animation: zoneFlash .3s ease;
}
@keyframes zoneFlash { from { outline-color: rgba(255,255,255,.9); } to { outline-color: var(--accent); } }
```
```javascript
function revealZone(el) {
  el.classList.add('tapped');
  const id = el.dataset.id;
  document.getElementById('zone-panel-' + id).style.display = 'block';
  zonesSeen.add(id);
  updateZoneCounter();
}
```
> ⚠️ Vùng tap PHẢI phủ RỘNG HƠN 1 chút so với rìa vật trong ảnh (thêm ~4-6% mỗi chiều), không phủ
> đúng khít viền — học sinh tap gần rìa vật vẫn nên tính là đúng, tap sát khít dễ bị "hụt" 1-2%.
> ⚠️ Nếu 2 vùng hotspot gần nhau có nguy cơ chồng lấn sau khi nới rộng, ưu tiên thu nhỏ lại đúng
> khung gốc ở phần chồng lấn, không để 1 tap kích hoạt nhầm 2 vùng.
> ⚠️ Test kỹ trên mobile ≤480px — vùng % giữ đúng tỉ lệ khi ảnh scale nhỏ, nhưng vùng quá nhỏ
> (dưới ~8% chiều rộng ảnh) vẫn khó tap chính xác bằng ngón tay dù đã tính đúng %; nếu vật trong
> ảnh quá nhỏ, nới thêm biên nhiều hơn mức 4-6% khuyến nghị ở trên.

---

### 1.6 Prediction Picker — MCQ Ghi Nhận Lựa Chọn, KHÔNG Chấm Điểm

```
Khác MCQ chấm điểm thường (không dùng cho bài kiểm tra kiến thức) — dùng
riêng cho lựa chọn dự đoán ở Hook (Challenge/Discovery). Chọn xong CHỈ ghi
nhận + mở khoá bước tiếp theo, KHÔNG hiện đúng/sai ngay (đáp án được "kiểm
chứng" tự nhiên qua nội dung đọc/nghe sau đó, không phải qua chấm điểm tại
chỗ) — nếu chấm ngay sẽ vô tình biến Hook thành 1 dạng callback, có thể đi
ngược quyết định đã chốt riêng cho module đó ở file 01 Bước 2.
```
```javascript
function pickOpt(el){
  document.querySelectorAll('.pred-opt').forEach(o => o.classList.remove('picked'));
  el.classList.add('picked');
  el.querySelector('input').checked = true;
  document.getElementById('btn-continue').disabled = false; // chỉ mở khoá, không chấm
}
```
HTML/CSS tương ứng: xem `02_design_tiengAnh.md` mục 1.10.

### 1.7 Progressive Reveal Hội Thoại (nút "Show more / Hiện tiếp")

```
Dùng cho hội thoại nhiều lượt (Getting Started, Speaking Everyday English)
khi không muốn hiện hết 1 lúc — tạo nhịp đọc + tò mò từng lượt, đỡ chiếm
màn hình mobile. Đã kiểm chứng qua build test Unit 3 Music (8 lượt thoại).
```
```javascript
let turnIdx = 0;
function revealNextTurn(dialogue, wrapId, btnId, onDone){
  if (turnIdx >= dialogue.length) return;
  const t = dialogue[turnIdx];
  const row = document.createElement('div');
  row.className = 'bubble-row ' + t.who;
  row.innerHTML = `
    <div class="avatar ${t.who}">${t.who[0].toUpperCase()}</div>
    <div class="bubble"><div class="who">${t.who}</div>${t.text}</div>`;
  document.getElementById(wrapId).appendChild(row);
  turnIdx++;
  if (turnIdx >= dialogue.length) onDone(); // đổi nút "Hiện tiếp" thành nút bước kế
}
```
> Mỗi bubble nên có animation `fadeUp` nhẹ khi xuất hiện (xem CSS
> `@keyframes fadeUp` trong code mẫu) — giúp phân biệt lượt mới vừa hiện
> với các lượt cũ, tránh học sinh bị rối khi danh sách dài dần.

### 1.8 Đánh Dấu Từ Trong Câu — Tap-to-Select-in-Sentence (chấm khi bấm Kiểm tra, KHÔNG real-time)

```
Dùng cho dạng bài "tìm (các) từ mục tiêu trong câu" (VD "Mark the Blend" — Pronunciation Unit 2:
nghe/đọc câu, xác định từ nào chứa blend đang học; có thể có 0 từ mục tiêu — câu bẫy).

KHÁC 1.2 (Click-Timed-Game): 1.2 cho phản hồi đúng/sai NGAY khi click từng cụm — học sinh có thể
"dò" đáp án bằng cách click thử lần lượt. Pattern 1.8 này KHÔNG cho phản hồi khi tap — chỉ đổi
trạng thái "đã chọn" (tương tự chọn nhiều đáp án MCQ), học sinh phải chủ động chọn xong toàn bộ rồi
mới bấm "Kiểm tra" mới biết đúng/sai — đúng nguyên tắc chống dò mù (áp dụng khi 1 lần chấm gộp
nhiều lựa chọn trong cùng 1 câu — khác matching 1-1 ở 1.3, xem lưu ý ở cuối mục 1.3).

Pattern:
  1. Câu được tách theo từ (giữ dấu câu dính liền từ trước, tránh tách nhầm "class." thành 2 token)
     thành các <span class="word-tok" data-word="..."> tappable.
  2. Tap 1 từ → toggle class .selected (đổi màu nền, KHÔNG báo đúng/sai) — tap lại để bỏ chọn.
  3. Cho phép chọn 0 từ (khi câu là câu bẫy, không có từ mục tiêu) — có nút phụ "Không có từ nào"
     để xác nhận rõ ý định (tránh học sinh chỉ đơn giản quên chọn).
  4. Bấm nút "Kiểm tra" mới chấm: so khớp tập từ đã chọn với tập từ đúng (`correctWords`) →
     .selected.correct (xanh, chọn đúng) / .selected.wrong (đỏ, chọn nhầm) / .missed (vàng, đúng
     nhưng không chọn) — rồi hiện `giai_thich_dung`.
  5. Khoá tương tác sau khi bấm Kiểm tra, có nút "Làm lại" riêng nếu muốn thử lại câu đó.
```
```javascript
let selectedWords = new Set();

function tokenizeSentence(sentence) {
  // Tách theo khoảng trắng, giữ dấu câu dính liền — đủ dùng cho câu tiếng Anh chuẩn SGK
  return sentence.split(' ');
}

function renderTappableSentence(sentence, wrapId) {
  const tokens = tokenizeSentence(sentence);
  const wrap = document.getElementById(wrapId);
  wrap.innerHTML = tokens.map((tok, i) =>
    `<span class="word-tok" data-idx="${i}" onclick="toggleWord(${i}, this)">${tok}</span>`
  ).join(' ');
}
function toggleWord(idx, el) {
  if (el.classList.contains('locked')) return; // đã bấm Kiểm tra thì khoá, không tap được nữa
  el.classList.toggle('selected');
  selectedWords.has(idx) ? selectedWords.delete(idx) : selectedWords.add(idx);
}
function checkMarkedWords(correctIdxSet, wrapId) {
  document.querySelectorAll(`#${wrapId} .word-tok`).forEach((el, i) => {
    el.classList.add('locked');
    const isSelected = selectedWords.has(i);
    const isCorrect = correctIdxSet.has(i);
    if (isSelected && isCorrect) el.classList.add('correct');       // chọn đúng
    else if (isSelected && !isCorrect) el.classList.add('wrong');   // chọn nhầm
    else if (!isSelected && isCorrect) el.classList.add('missed');  // bỏ sót
  });
  // Sau đó hiện .giai_thich_dung tương ứng câu này — dùng chung khối feedback như MCQ (4.6)
}
```
```css
.word-tok { display:inline-block; padding:3px 5px; border-radius:6px; cursor:pointer;
  min-height:32px; /* đủ vùng chạm ngón tay trên mobile, không cần zoom */ }
.word-tok.selected { background:var(--accent); color:#fff; }
.word-tok.selected.correct { background:var(--correct); }
.word-tok.selected.wrong { background:var(--wrong); }
.word-tok.missed { background:var(--cream-2); outline:2px dashed var(--wrong); }
```
> Vùng chạm mỗi từ (`min-height:32px` + padding ngang) quan trọng trên mobile — từ ngắn (2-3 ký
> tự) dễ bấm trượt nếu không đủ vùng chạm, khác hẳn click chuột trên desktop.

---

### 1.9 Ảnh Hook Full-Screen + Fade Transition (mở màn trước Hero/Canvas)

```
Dùng cho ảnh AI-generated mở đầu module (VD "sim1a_hook_data_analyst.png" ở Toán, hoặc ảnh Hook
Chore Dilemma ở Reading) — hiển thị full-screen CHE TOÀN BỘ nội dung bài học, sau đó tự fade-out
để lộ Hero/canvas bên dưới. Khác 1.6 (Prediction Picker) — 1.9 KHÔNG có lựa chọn/MCQ, chỉ là màn
chuyển cảnh; nếu ảnh có kèm câu hỏi dự đoán ngay trên đó, đó là 1.6 gắn sau khi 1.9 fade xong, hai
pattern không gộp chung 1 lớp.

Cơ chế:
  1. Overlay full-screen (z-index cao nhất) chứa ảnh + caption ngắn (nếu có lời dẫn).
  2. Học sinh tap vào bất kỳ đâu trên overlay → fade ngay, KHÔNG cần chờ.
  3. Nếu học sinh không tap → tự fade sau khoảng chờ định sẵn (khác nhau theo module — có lời
     thoại robot cần đọc thì chờ dài hơn, VD Module 1A; không có lời thoại thì chờ ngắn ~400ms).
  4. Sau khi fade xong, remove hẳn overlay khỏi DOM (không chỉ ẩn) để tránh chặn tap chuột/scroll
     phía dưới bằng lớp trong suốt còn sót lại.
```
```html
<div id="hook-overlay" class="hook-overlay" onclick="dismissHook()">
  <img src="unit_hook_image.png" alt="">
  <p class="hook-caption">Sound familiar? / Nghe quen không?</p>
</div>
```
```javascript
let hookDismissed = false;
function initHook(waitMs = 400) {
  setTimeout(() => dismissHook(), waitMs);
}
function dismissHook() {
  if (hookDismissed) return; // tránh double-fire khi tap trùng lúc timeout chạy
  hookDismissed = true;
  const overlay = document.getElementById('hook-overlay');
  if (!overlay) return;
  overlay.classList.add('fade-out');
  overlay.addEventListener('transitionend', () => overlay.remove(), { once: true });
}
window.addEventListener('DOMContentLoaded', () => initHook(400)); // đổi waitMs tuỳ module
```
```css
.hook-overlay {
  position: fixed; inset: 0; z-index: 9999;
  display: flex; align-items: center; justify-content: center;
  background: var(--cream); cursor: pointer;
  transition: opacity .3s ease;
}
.hook-overlay img { width: 100%; height: 100%; object-fit: cover; }
.hook-overlay .hook-caption {
  position: absolute; bottom: 24px; right: 24px;
  color: #fff; font-weight: 600; text-shadow: 0 1px 6px rgba(0,0,0,.4);
}
.hook-overlay.fade-out { opacity: 0; pointer-events: none; }
```
> ⚠️ `object-fit: cover` bắt buộc — ảnh AI-generated thường tỉ lệ 16:9, không cover sẽ méo/để dải
> trắng trên mobile ≤480px (màn hình dọc). Test ảnh thật ở khung hẹp trước khi chốt.
> ⚠️ Thời gian chờ (`waitMs`) và thời gian transition CSS là 2 thông số KHÁC NHAU — đừng nhầm khi
> đọc kịch bản ghi "fade 400ms": xác định rõ đó là thời gian *chờ trước khi bắt đầu fade* hay thời
> gian *chạy transition* trước khi build, vì cách viết trong 2 kịch bản khác nhau có thể dùng cùng
> con số 400ms cho 2 ý khác nhau.
> ⚠️ Nếu overlay có lời thoại robot/nhân vật (kiểu Module 1A) thay vì chỉ 1 dòng caption ngắn, tăng
> `waitMs` đủ để đọc hết câu (ước lượng ~50ms/từ tiếng Việt, tối thiểu 1.5s) trước khi tự fade.

### 1.10 Gạch Chân Đúng Cụm Âm — Pronunciation Difference/Odd-one-out (BẮT BUỘC khi đề nói "phần
gạch chân")

```
⚠️ Lỗi thật đã gặp: đề bài viết "Chọn từ có phần gạch chân phát âm khác/giống nhóm với [các cụm phụ
âm mục tiêu]..." nhưng khi build ra HTML, các từ lựa chọn hiện TRƠN, không có chữ nào được gạch chân
thật — học sinh không biết đang so sánh phần nào của từ, click chọn cả từ nguyên khối là SAI về mặt
sư phạm (bài này kiểm tra khả năng nhận diện ĐÚNG cụm phụ âm, không phải chọn từ theo cảm tính/
spelling tổng thể). Bắt buộc dùng pattern dưới đây cho MỌI câu Pronunciation Difference/Odd-one-out
có đề bài nhắc "underlined part"/"phần gạch chân" — nếu đề không nhắc gạch chân (VD chỉ so IPA cả
từ) thì không cần pattern này, dùng MCQ thường (Mục 4.6 file 02).

⚠️ Ví dụ code bên dưới CHỈ minh hoạ CẤU TRÚC field/hàm (word/start/end/oddIdx/explain) — các từ
placeholder [wordA]/[wordB]... KHÔNG phải nội dung thật. Nội dung câu hỏi/từ vựng thật PHẢI lấy 100%
từ kịch bản người dùng cung cấp — xem cảnh báo toàn cục ở Mục 0 file 02.

QUYẾT ĐỊNH KỸ THUẬT — dùng INDEX {start,end}, KHÔNG dùng substring đoán vị trí:
  Nhiều từ có cụm chữ target xuất hiện >1 lần trong chính từ đó (VD 1 từ có cùng 2 chữ cái xuất hiện
  ở cả đầu và cuối) — nếu chỉ khai báo substring rồi tự tìm .indexOf() để gạch chân, hệ thống sẽ gạch
  nhầm vị trí (luôn ăn vị trí đầu tiên tìm được) mà không ai biết, vì không có gì báo lỗi. Bắt buộc
  tác giả khai báo rõ {start, end} theo index ký tự trong từ — không suy luận tự động từ substring.
```

```javascript
// Data mỗi câu: options là mảng { word, start, end } — start/end là INDEX ký tự (0-based, end
// KHÔNG bao gồm) của đúng phần cần gạch chân trong TỪ ĐÓ. oddIdx: chỉ số phần tử là đáp án đúng
// (từ khác nhóm/đúng nhóm tuỳ đề) TRƯỚC khi xáo — dùng shuffleMCQOptions-style xáo vị trí hiển thị
// (nguyên tắc 7, Mục 0 file 02) khi render, không gán cứng vị trí A/B/C.
// ⚠️ Chống đoán mò theo pattern (nguyên tắc 13, Mục 0 file 02): khi soạn NHIỀU câu trong 1 mảng
// pronQuestions, giá trị oddIdx của TỪNG CÂU không được rơi vào 1 chu kỳ đều đặn (VD câu 1 oddIdx=1,
// câu 2 oddIdx=2, câu 3 oddIdx=1, câu 4 oddIdx=2... lặp lại "1-2, 1-2"). shuffleMCQOptionsObj() chỉ
// xáo VỊ TRÍ HIỂN THỊ lúc render — không sửa được pattern nếu oddIdx trong DATA gốc đã đi theo chu
// kỳ cố định. Soạn data xong, tự rà lại dãy oddIdx của cả set trước khi giao.
const pronQuestions = [
  {
    instruction: "Choose the word whose underlined part is pronounced differently from the other three.",
    instructionVi: "Chọn từ có phần gạch chân phát âm KHÁC 3 từ còn lại.",
    options: [
      // ⚠️ [wordA]/[wordB]/[wordC]/[wordD] dưới đây là PLACEHOLDER minh hoạ cấu trúc — build thật
      // phải thay bằng đúng từ vựng trong kịch bản, không giữ nguyên placeholder hoặc tự nghĩ từ khác.
      { word: "[wordA]", start: 0, end: 2 },  // cụm phụ âm mục tiêu 1
      { word: "[wordB]", start: 0, end: 2 },  // <- ví dụ vị trí đáp án đúng (âm khác nhóm)
      { word: "[wordC]", start: 0, end: 2 },  // cụm phụ âm mục tiêu 1
      { word: "[wordD]", start: 0, end: 2 },  // cụm phụ âm mục tiêu 1
    ],
    oddIdx: 1,
    explain: "[wordB] có phần gạch chân phát âm khác hẳn 3 từ còn lại — nêu rõ IPA/lý do theo đúng nội dung kịch bản thật."
  },
];

// ⚠️ VALIDATE ngay lúc load data (chạy 1 lần, KHÔNG chờ học sinh tương tác mới phát hiện lỗi) —
// báo lỗi rõ câu nào/từ nào sai ngay trên console để tác giả soạn sửa TRƯỚC khi giao bài, tránh
// học sinh gặp phần gạch chân sai mà không ai biết.
function validatePronData(questions) {
  questions.forEach((q, qi) => {
    q.options.forEach((opt, oi) => {
      const { word, start, end } = opt;
      if (start == null || end == null || start < 0 || end > word.length || start >= end) {
        console.error(`Câu ${qi + 1}, option ${oi + 1} ("${word}"): index [${start},${end}] không hợp lệ.`);
      }
    });
  });
}

function renderUnderlinedWord(word, start, end) {
  // esc() dùng chung — xem nguyên tắc 8, Mục 0 file 02 — áp cho từng đoạn tách riêng
  return esc(word.slice(0, start)) + '<u class="pron-u">' + esc(word.slice(start, end)) + '</u>' + esc(word.slice(end));
}

function renderPronOptions(q, wrapId) {
  const { shuffled, correctText } = shuffleMCQOptionsObj(q.options, q.oddIdx); // xem chú thích dưới
  document.getElementById(wrapId).innerHTML = shuffled.map((opt, i) =>
    `<button class="pron-opt" onclick="pickPronOpt(${i}, this)">${renderUnderlinedWord(opt.word, opt.start, opt.end)}</button>`
  ).join('');
  // lưu lại correctText (chính là opt.word của đáp án đúng) trong closure/data-attribute để chấm
}

// Biến thể của shuffleMCQOptions (Mục 4.6 file 02) cho mảng OBJECT thay vì mảng string — nguyên
// tắc xáo vị trí hiển thị vẫn giữ nguyên, chỉ đổi kiểu phần tử đang xáo.
function shuffleMCQOptionsObj(options, correctIdx) {
  const correctText = options[correctIdx].word;
  const shuffled = [...options].sort(() => Math.random() - 0.5);
  return { shuffled, correctText };
}

let pronSelected = null;
function pickPronOpt(i, el) {
  document.querySelectorAll('.pron-opt').forEach(o => o.classList.remove('picked'));
  el.classList.add('picked');
  pronSelected = { idx: i, el };
}
```
```css
.pron-opt { border:1.5px solid var(--sage); background:transparent; border-radius:var(--radius-sm);
  padding:8px 16px; min-height:44px; font-weight:600; color:var(--ink-2); font-size:14px; }
.pron-opt .pron-u { text-decoration:underline; text-decoration-color:var(--accent);
  text-decoration-thickness:2.5px; text-underline-offset:3px; }
.pron-opt.picked { border-color:var(--accent); background:var(--accent-pale); }
.pron-opt.picked.correct { background:var(--correct); color:#fff; border-color:var(--correct); }
.pron-opt.picked.wrong { background:var(--wrong); color:#fff; border-color:var(--wrong); }
```

> ⚠️ **Tương tác vẫn là chọn CẢ NÚT (cả từ), không phải quệt/chọn riêng từng chữ cái** — điều SỬA ở
> đây không phải đổi cách bấm (bấm cả từ vẫn đúng, vì học sinh trả lời "từ nào khác nhóm" chứ không
> phải "kéo chọn chữ nào"), mà là bắt buộc PHẦN CHỮ ĐƯỢC GẠCH CHÂN trong mỗi nút phải hiện đúng, thật
> (`<u>`), để học sinh nhìn thấy chính xác đang so sánh phần nào — không phải đoán mò cả từ. Nút bấm
> to hơn phần gạch chân nhiều (đủ `min-height:44px` theo mobile-first, nguyên tắc 6 Mục 0 file 02),
> nên không cần lo học sinh phải "bấm trúng đúng 2 chữ" trên mobile — bấm vào bất kỳ đâu trong nút
> đều tính là chọn cả từ đó, đúng bản chất câu hỏi.
> ⚠️ Chấm đúng/sai + `explain` dùng lại đúng nguyên tắc MCQ thường (Mục 4.6 file 02, so theo
> `correctText` chứ không theo index cố định vì vị trí đã xáo).
> ⚠️ Field `instructionVi` hiển thị ngay dưới `instruction` gốc tiếng Anh — đúng nguyên tắc 9 (Mục 0
> file 02): đề phải nói rõ tiêu chí (KHÁC nhóm hay ĐÚNG nhóm), không dùng chung 1 câu mơ hồ cho mọi
> dạng.

### 1.11 Strategy Reveal — Dạy Chiến Thuật Đọc Hiểu Ngay Trong Bài

```
Dùng khi kịch bản có khối "🆕 STRATEGY REVEAL" — 1 thẻ chèn GIỮA phần khám phá nội dung (Card/
Discovery/Mission) và phần tổng kết (Vocab Collection/Kết đoạn), dạy học sinh 1 hoặc nhiều kỹ năng
đọc hiểu bằng chính worked-example vừa trải qua — KHÔNG phải lý thuyết trừu tượng chèn cứng.

2 BIẾN THỂ (xác định theo kịch bản ghi rõ "1 kỹ năng" hay "so sánh song song 2 kỹ năng"):
  (a) 1 KỸ NĂNG — dùng layout Split-view gắn với Reference Pane (4.8b file 02): trái = đoạn văn,
      phải = các bước Strategy. Cần PHẦN 1.12 (scrollToAndHighlight) để link 2 cột.
  (b) NHIỀU KỸ NĂNG SONG SONG — dùng layout 2 Cột So Sánh (PHẦN 1.13) khi Lesson không có 1 khối
      đoạn văn liền mạch để link (VD Mission/Stage rải rác nội dung qua nhiều màn).

CẤU TRÚC BƯỚC CHUẨN (dùng chung cho cả 2 biến thể, số bước có thể co giãn ±1 tuỳ nội dung):
  1. Intro — nêu TÊN kỹ năng tường minh (VD "Reading for Specific Information", không chỉ nói
     "cùng ôn lại nhé" chung chung).
  2. Worked-example recap — dùng lại CHÍNH NỘI DUNG học sinh vừa tương tác (câu evidence vừa chọn,
     item vừa tìm...), KHÔNG bịa ví dụ mới ở bước này.
  3. Rule callout — khái quát hoá quy tắc từ worked-example, 1-2 câu ngắn.
  4. (biến thể a) 2-step process dạng số — cách áp dụng quy tắc | (biến thể b) Bảng so sánh song
     song 2 kỹ năng.
  5. Quick check — 1 câu hỏi áp dụng ngay, dùng NGỮ LIỆU MỚI (khác hẳn bước 2) để kiểm tra học sinh
     hiểu quy tắc chứ không chỉ nhớ ví dụ cũ.
  6. Summary Card — xem PHẦN 1.14, bắt buộc có ở MỌI Strategy Reveal.
  7. Câu chốt nối sang Practice — nhắc học sinh sẽ dùng đúng kỹ năng này ở phần luyện tập.

⚠️ Toàn bộ text hướng dẫn/câu hỏi/nhãn kỹ năng trong Strategy Reveal đều là NỘI DUNG THẬT hiện cho
học sinh (khác nhãn `level`/`cat`/`skill` ở Mục 9.10 file 02 — những nhãn đó CHỈ dùng nội bộ, không
bao giờ lộ ra HTML). Tên kỹ năng ở Bước 1 và bảng so sánh ở Bước 4 PHẢI hiện thật trên UI — đây
không phải nhãn ẩn.
```

```javascript
// Cấu trúc data đề xuất — 1 object cho toàn bộ Strategy Reveal, KHÔNG tách rời từng bước thành
// biến riêng (dễ đồng bộ với Summary Card + icon Recap ở Practice, xem 1.14):
const strategyReveal = {
  skillName: { en: "Reading for Specific Information", vi: "Đọc tìm thông tin chi tiết" },
  variant: "single", // "single" | "compare" — quyết định dùng layout 1.12 hay 1.13
  steps: [
    { type: "intro", en: "...", vi: "..." },
    { type: "recap", pairs: [ { good: "...", bad: "..." } ] }, // liên kết paragraphId nếu variant=single
    { type: "rule", en: "...", vi: "..." },
    { type: "process", items: ["...", "..."] }, // hoặc { type: "compareTable", rows: [...] }
    { type: "quickcheck", question: "...", options: [...] },
  ],
  summaryCard: { title: "Quick Recap — ...", rule: "...", steps: ["...", "..."] } // dùng chung cho 1.14
};
```

### 1.12 Scan-Reveal Effect + `scrollToAndHighlight()` — Liên Kết Bước ↔ Đoạn Văn

```
Dùng cho biến thể (a) của Strategy Reveal (1 kỹ năng, Split-view + Reference Pane) — khi học sinh
tap vào 1 bước bên cột phải, cột trái (đoạn văn) TỰ auto-scroll tới đúng câu + highlight, để học
sinh không phải tự tìm lại bằng mắt. Cũng dùng cho hiệu ứng "quét" mô phỏng động tác đọc quét thật
(scan effect) ở bước 2-step process — 1 dải sáng chạy từ trên xuống dưới qua đoạn văn rồi dừng lại
đúng ở câu đáp án, KHÁC với highlight tĩnh (bật màu ngay lập tức không hiệu ứng).
```

```javascript
// paragraphId: id của khối đoạn văn trong Reference Pane. sentenceIndex: thứ tự câu trong đoạn
// (0-based). color: 'good' | 'bad' | 'neutral' — map ra class CSS tương ứng.
function scrollToAndHighlight(paragraphId, sentenceIndex, color = 'good') {
  const para = document.getElementById(paragraphId);
  if (!para) return;
  const sentence = para.querySelectorAll('.sentence')[sentenceIndex];
  if (!sentence) return;
  para.closest('.ref-pane-scroll').scrollTo({
    top: sentence.offsetTop - 40, // chừa khoảng trống phía trên, không dí sát mép
    behavior: 'smooth'
  });
  document.querySelectorAll('.sentence.sr-active').forEach(s => s.classList.remove('sr-active', 'sr-good', 'sr-bad'));
  sentence.classList.add('sr-active', color === 'good' ? 'sr-good' : color === 'bad' ? 'sr-bad' : '');
}

// Scan effect: dải sáng chạy qua N câu liên tiếp trong đoạn, dừng lại đúng ở targetIndexes.
function runScanEffect(paragraphId, targetIndexes, { speedMs = 120, onDone } = {}) {
  const sentences = document.getElementById(paragraphId).querySelectorAll('.sentence');
  let i = 0;
  const timer = setInterval(() => {
    sentences.forEach(s => s.classList.remove('sr-scanning'));
    if (i >= sentences.length) {
      clearInterval(timer);
      targetIndexes.forEach(ti => sentences[ti]?.classList.add('sr-good'));
      onDone?.();
      return;
    }
    sentences[i].classList.add('sr-scanning');
    i++;
  }, speedMs);
}
```
```css
.sentence.sr-active, .sentence.sr-scanning { transition: background-color .25s ease; }
.sentence.sr-scanning { background: var(--accent-pale); }
.sentence.sr-good { background: var(--correct-pale, #e3f5e8); border-left: 3px solid var(--correct); }
.sentence.sr-bad { background: var(--wrong-pale, #fbeaea); text-decoration: line-through; opacity: .7; }
```
> ⚠️ Đoạn văn trong Reference Pane PHẢI được đánh dấu sẵn từng câu bằng `<span class="sentence">`
> (hoặc tương đương) ngay từ lúc render — không parse tách câu bằng regex lúc runtime, dễ sai với
> câu có dấu chấm trong số/viết tắt (VD "Mr. Smith", "3.5 km").
> ⚠️ `runScanEffect` chỉ dùng cho hiệu ứng minh hoạ trong Strategy Reveal (bước 2-step process) —
> KHÔNG dùng làm cơ chế chấm điểm; chấm điểm vẫn theo tap-to-select chuẩn (1.8).

### 1.13 2 Cột So Sánh (Compare Cards) — Biến Thể Strategy Reveal Nhiều Kỹ Năng

```
Dùng cho biến thể (b) của Strategy Reveal — khi Lesson KHÔNG có 1 khối đoạn văn liền mạch để link
scroll-highlight (VD Mission/Stage rải nội dung qua nhiều màn, như Green Day Mission). Layout
full-width, 2 cột đặt cạnh nhau (mobile: xếp chồng theo chiều dọc, cột dưới có thể cần tap "Reveal"
để tránh dài quá 1 màn hình), KHÔNG cần Reference Pane — dùng lại chính item/kết quả học sinh đã
thu thập ở Lesson (Word Collection, Discovery đã mở khoá...) làm nội dung cột, không hiển thị lại
đoạn văn gốc.
```

```html
<div class="compare-cards">
  <div class="compare-col" data-skill="detail">
    <h4>🔍 DETAILS</h4>
    <ul class="compare-list"><!-- render từ item đã thu thập ở Lesson --></ul>
  </div>
  <div class="compare-col" data-skill="main_idea">
    <h4>🌍 MAIN IDEA</h4>
    <button class="reveal-btn" onclick="revealCompareCol(this)">Reveal</button>
    <p class="compare-reveal-content hidden"><!-- câu kết/ý chính, ẩn tới khi tap Reveal --></p>
  </div>
</div>
```
```javascript
function revealCompareCol(btn) {
  const content = btn.nextElementSibling;
  content.classList.remove('hidden');
  btn.remove(); // tap 1 lần, không cần ẩn lại
}
```
```css
.compare-cards { display: flex; gap: 16px; }
.compare-col { flex: 1; border-radius: var(--radius-sm); padding: 16px; background: var(--panel-bg, #fafafa); }
@media (max-width: 480px) { .compare-cards { flex-direction: column; } }
.compare-reveal-content.hidden { display: none; }
```
> ⚠️ Không dùng cho biến thể (a) 1 kỹ năng — nếu Lesson có sẵn Reference Pane với đoạn văn liền
> mạch, luôn ưu tiên 1.12 (Split-view + scrollToAndHighlight), vì cho học sinh liên hệ trực tiếp về
> đúng vị trí trong bài đọc, không chỉ liệt kê lại bằng trí nhớ.

### 1.14 Summary Card + Icon 💡 Recap — Lật Lại Xem Thông Tin Cũ

```
Summary Card là bước CUỐI CÙNG bắt buộc của mọi Strategy Reveal (xem 1.11 bước 6) — 1 card
full-width tóm tắt Rule + quy trình/bảng so sánh thành dạng "mang theo được", có nút "Got it —
let's continue" để đóng.

Icon 💡 Recap là cách "mang" Summary Card đó SANG Practice — đặt cạnh MỌI câu hỏi (không giới hạn
theo dạng bài, xem changelog thật Unit 1/Unit 2: ban đầu chỉ định giới hạn 8 câu Prove-it, sau mở
rộng ra cả Difficult/toàn bộ câu vì không có lý do sư phạm để giới hạn — Difficult không có nghĩa
là học sinh ít cần nhắc lại chiến thuật hơn). Tap icon → mở popup/bottom-sheet OVERLAY nổi đè lên
trên (KHÔNG đổi tab/chế độ xem của Reference Pane bên dưới), hiển thị ĐÚNG same content với Summary
Card gốc — dùng chung 1 nguồn dữ liệu (`strategyReveal.summaryCard` ở 1.11), không viết 2 bản nội
dung riêng.
```

```javascript
function openRecapPopup(summaryCardData) {
  const popup = document.getElementById('recap-popup');
  popup.querySelector('.recap-title').textContent = summaryCardData.title;
  popup.querySelector('.recap-rule').textContent = summaryCardData.rule;
  popup.querySelector('.recap-steps').innerHTML = summaryCardData.steps.map(s => `<li>${s}</li>`).join('');
  popup.classList.add('open');
  // KHÔNG gọi recordMistake() ở đây — mở Recap không tính là sai, không ảnh hưởng adaptive routing (3.5)
}
function closeRecapPopup() {
  document.getElementById('recap-popup').classList.remove('open');
  // Không reset scroll/tab của Reference Pane bên dưới — overlay chỉ che tạm, đóng ra là về nguyên trạng
}
```
```css
#recap-popup { position: fixed; inset: 0; z-index: 500; display: none;
  align-items: flex-end; justify-content: center; background: rgba(0,0,0,.3); }
#recap-popup.open { display: flex; }
#recap-popup .recap-sheet { background: #fff; border-radius: 16px 16px 0 0; padding: 20px;
  width: 100%; max-width: 480px; max-height: 60vh; overflow-y: auto; }
@media (min-width: 481px) {
  #recap-popup { align-items: center; }
  #recap-popup .recap-sheet { border-radius: 16px; }
}
```
> ⚠️ **2 ràng buộc bắt buộc** (dễ hiểu nhầm khi build): (1) mở popup Recap KHÔNG gọi
> `recordMistake()` dưới bất kỳ hình thức nào; (2) nội dung popup CHỈ nhắc lại Rule + quy trình,
> KHÔNG thêm ví dụ minh hoạ mới trùng với câu học sinh đang làm — tránh biến Recap thành gợi ý đáp
> án trá hình.
> ⚠️ Đây cũng là pattern chung cho MỌI nhu cầu "lật lại xem thông tin cũ" khác trong hệ thống (không
> riêng Strategy Reveal) — VD xem lại định nghĩa 1 từ đã tap qua ở Word Collection: dùng cùng cơ chế
> overlay không phá state, không tính là sai.

### 1.15 Reveal Từ Vựng Theo Level — 2 Tầng Core/Support, Song Ngữ Bắt Buộc

```
Mở rộng 1.1 (Click-Reveal Nghĩa Từ) cho riêng file Practice — số từ được tap-reveal GIẢM DẦN theo
Level đang active (Easy nhiều nhất, Difficult không có), và tách 2 TẦNG từ khác nhau cả về hình
thức lẫn hành vi:

  TẦNG "core" — từ vựng chính thức của bài (đã dạy có gap-fill ở Lesson): highlight vàng đậm có
    viền. Tap ở Practice → CHỈ hiện popup nghĩa ngắn (Anh+Việt), KHÔNG gap-fill, KHÔNG tính vào Word
    Collection (khác Lesson) — đây là tra cứu lại, không phải học lần đầu.
  TẦNG "support" — từ khó KHÁC (chưa từng dạy, chỉ để gỡ rào cản đọc hiểu ở Practice): gạch chân
    chấm, màu xám nhạt. Tap → popup nghĩa ngắn (Anh+Việt), không gắn gì thêm.

⚠️ Reveal từ khó CHỈ áp dụng ở Practice — KHÔNG áp dụng ở Lesson, vì Lesson đã có kịch bản giảng/
dịch trực tiếp qua từng bước/scene, thêm reveal vào đó sẽ làm loãng phần dạy kỹ năng.
⚠️ MỌI popup nghĩa (cả 2 tầng, cả ở Lesson lẫn Practice) PHẢI có nghĩa tiếng Việt ngắn ngay dưới
định nghĩa tiếng Anh — không chỉ định nghĩa Anh-Anh, hỗ trợ học sinh học yếu hơn.
```

```javascript
// 1 nguồn data duy nhất cho cả 2 tầng, field `type` quyết định style, field `levels` quyết định
// Level nào được reveal từ đó (không viết 3 component Reference Pane riêng cho 3 Level).
const revealWords = [
  { word: 'sustainable', en: 'able to continue without harming the environment',
    vi: 'bền vững, không gây hại môi trường', type: 'core', levels: ['easy'] },
  { word: 'appliances', en: 'electrical machines used at home, like a fridge or a fan',
    vi: 'thiết bị điện gia dụng', type: 'support', levels: ['easy'] },
  { word: 'add up', en: 'to become significant when combined',
    vi: 'cộng dồn lại, tích luỹ thành điều đáng kể', type: 'support', levels: ['easy', 'medium'] },
];

function renderRevealWords(currentLevelTab) {
  return revealWords.filter(w => w.levels.includes(currentLevelTab));
}
```
```css
.reveal-core { background: var(--accent-pale); border-bottom: 2px solid var(--accent); cursor: pointer; }
.reveal-support { border-bottom: 1.5px dotted var(--ink-3, #999); cursor: pointer; }
```
> ⚠️ Icon 💡 Recap (1.14) và Reveal Từ Vựng (1.15) là 2 cơ chế KHÁC NHAU, dùng chung layout overlay
> nhưng khác mục đích — đừng gộp 1 popup cho cả 2 (Recap nhắc chiến thuật đọc hiểu, Reveal nhắc nghĩa
> từ vựng), giữ riêng để học sinh không nhầm lẫn 2 loại hỗ trợ.

### 1.16 Before/After Comparison Slider — tay cầm kéo trục ngang (component 4.18 file design)

```
Khác 1.3 (Tap-to-Match nối 2 cột — tap 2 lần, không có khái niệm "kéo"): đây là 1 tay cầm DUY NHẤT trượt liên
tục trên 1 trục ngang, không có khái niệm đích thả đúng/sai — dùng cho Warm-up hook trực quan
kiểu "kéo để so sánh Trước/Sau" (xem component 4.18 file 02_design_tiengAnh).

⚠️ Lỗi nền tảng nhất của pattern này: mặc định trình duyệt mobile diễn giải MỌI cử chỉ kéo trong
vùng đó là để CUỘN TRANG, không phải để di chuyển tay cầm. Chuột trên desktop không bao giờ lộ lỗi
này (DevTools responsive mode cũng KHÔNG lộ vì vẫn giả lập bằng sự kiện chuột) — chỉ hiện khi kéo
bằng ngón tay thật trên điện thoại thật. 2 dòng bắt buộc để chặn hành vi cuộn mặc định:
  1. CSS: `touch-action: none` trên container chứa tay cầm.
  2. JS: listener `touchmove` đăng ký `{ passive: false }`, VÀ trong handler gọi `e.preventDefault()`.
     Thiếu (2) mà chỉ có (1) → vẫn cuộn, vì `preventDefault()` trong listener `passive: true`
     (mặc định của trình duyệt) bị ÂM THẦM bỏ qua, không báo lỗi console.
```

```javascript
function handleMove(e) {
  if (!isDragging) return;
  if (e.touches) e.preventDefault(); // chỉ có tác dụng nếu touchmove đăng ký passive:false bên dưới
  const rect = container.getBoundingClientRect();
  const clientX = e.touches ? e.touches[0].clientX : e.clientX;
  const percentage = ((clientX - rect.left) / rect.width) * 100;
  setSliderPosition(Math.max(0, Math.min(100, percentage)));
}

container.addEventListener('mousedown', e => { isDragging = true; handleMove(e); });
window.addEventListener('mousemove', handleMove);
window.addEventListener('mouseup', () => { isDragging = false; });

container.addEventListener('touchstart', e => { isDragging = true; handleMove(e); }, { passive: true });
window.addEventListener('touchmove', handleMove, { passive: false }); // bắt buộc passive:false
window.addEventListener('touchend', () => { isDragging = false; });
```
```css
.comparison-container { touch-action: none; cursor: col-resize; } /* bắt buộc, xem giải thích trên */
```
> Nghiệm thu: bắt buộc kéo thử bằng ngón tay trên điện thoại thật, không chỉ resize cửa sổ trình
> duyệt hoặc DevTools responsive mode — cả 2 cách đó đều dùng sự kiện chuột nên không lộ được lỗi.

### 1.17 Typewriter + Growing Diagram — demo dẫn dắt tuần tự (dùng cùng Idea Diagram 4.21 file design)

```
Dùng cho khối "demo GV/AI dẫn" trước khi học sinh tự làm (VD demo phân tích 1 văn bản mẫu ở Writing
trước khi học sinh tự làm với văn bản khác) — câu hỏi hiện trước, chữ trả lời gõ dần, rồi 1 cấp của
Idea Diagram (4.21) "mọc" thêm. Đây là bản MỞ RỘNG của Progressive Reveal (Mục 1.7 — hiện dần từng
khối) — thêm hiệu ứng gõ ký tự + đồng bộ với việc mở khoá 1 phần trong .idea-diagram, không phải
component tách rời. Khối này CHỈ ĐỌC, không chấm điểm — không gắn recordMistake()/checkTextAnswer()
dưới bất kỳ hình thức nào, đúng tinh thần Strategy Reveal (Mục 1.11-1.13).
```

```javascript
// Dùng [...text] thay vì text.length/charAt — tránh cắt sai ký tự có dấu tổ hợp (Unicode)
function typeText(el, text, speed = 28, onDone) {
  const chars = [...text];
  let i = 0;
  el.textContent = '';
  // Tôn trọng prefers-reduced-motion — hiện ngay lập tức, không ép hiệu ứng lên người dùng nhạy cảm
  if (window.matchMedia('(prefers-reduced-motion: reduce)').matches) {
    el.textContent = text; onDone?.(); return;
  }
  const timer = setInterval(() => {
    el.textContent += chars[i]; i++;
    if (i >= chars.length) { clearInterval(timer); onDone?.(); }
  }, speed);
  // Bấm để bỏ qua hiệu ứng — BẮT BUỘC, không ép học sinh phải đợi hết animation nếu đã đọc kịp
  el.closest('.demo-qa-step')?.addEventListener('click', () => {
    clearInterval(timer); el.textContent = text; onDone?.();
  }, { once: true });
}

// Gọi sau khi 1 câu hỏi gõ xong → mở khoá 1 cấp trong Idea Diagram (thêm class hiện dần)
function growBranch(diagramEl, branchIndex, level) {
  const branch = diagramEl.querySelectorAll('.idea-branch')[branchIndex];
  const target = level === 'branch' ? branch : branch.querySelector('.idea-leaf:last-child');
  target.classList.remove('hidden-grow');
  target.classList.add('fadeUp'); // tái dùng keyframe fadeUp đã có ở Mục 1.7
}
```
```css
.hidden-grow { display: none; } /* ẩn trước khi "mọc" — KHÔNG dùng visibility:hidden để không giữ
  chỗ trống, tránh layout nhảy giật trên khung hẹp mobile */
```

> **📱 Mobile — 3 lưu ý bắt buộc:**
> 1. Tốc độ gõ giữ 25-35ms/ký tự — nhanh hơn dễ giật trên máy yếu, chậm hơn học sinh sốt ruột (đã có
>    nút bấm-để-bỏ-qua, nhưng vẫn nên mặc định vừa phải).
> 2. Vì diagram "mọc" thêm nội dung real-time, dùng `.hidden-grow{display:none}` (không chiếm layout)
>    thay vì `opacity:0` — nếu dùng opacity, khung rỗng vẫn chiếm chỗ trên màn hình hẹp, đẩy nút
>    "Reveal" lệch vị trí gây khó chạm lại.
> 3. Test bằng `prefers-reduced-motion` bật (DevTools → Rendering → Emulate CSS media feature) VÀ
>    bằng cách bấm-để-bỏ-qua giữa chừng — cả 2 đường đều phải hiện đủ text, không kẹt nửa chừng.

### 2.1 Audio Player Chuẩn

```javascript
function apToggle(id) {
  const audio = document.getElementById('audio-' + id);
  const btn = document.getElementById('ap-' + id + '-icon');
  if (audio.paused) { audio.play(); btn.className = 'ti ti-player-pause'; }
  else { audio.pause(); btn.className = 'ti ti-player-play'; }
}
function apSeek(e, id) {
  const audio = document.getElementById('audio-' + id);
  const wrap = document.getElementById('ap-' + id + '-barwrap');
  const pct = (e.clientX - wrap.getBoundingClientRect().left) / wrap.offsetWidth;
  audio.currentTime = pct * audio.duration;
}
function apSpeed(id) {
  const audio = document.getElementById('audio-' + id);
  const speeds = [1, 1.25, 0.75];
  audio.playbackRate = speeds[(speeds.indexOf(audio.playbackRate) + 1) % speeds.length];
  document.getElementById('ap-' + id + '-speed').textContent = audio.playbackRate + '×';
}
```
> ⚠️ **iOS Safari**: audio KHÔNG thể autoplay hay `.play()` gọi ngoài user
> gesture trực tiếp (click). Nếu logic có gọi play() từ 1 hàm khác (VD sau
> khi fetch xong dữ liệu), phải gọi trong CÙNG call stack với sự kiện click,
> không qua `await`/`setTimeout` ở giữa.

### 2.2 Ghi Âm Học Sinh (MediaRecorder API)

```javascript
let mediaRecorder, audioChunks = [];

async function startRecording() {
  try {
    const stream = await navigator.mediaDevices.getUserMedia({ audio: true });
    mediaRecorder = new MediaRecorder(stream);
    audioChunks = [];
    mediaRecorder.ondataavailable = e => audioChunks.push(e.data);
    mediaRecorder.onstop = () => {
      const blob = new Blob(audioChunks, { type: 'audio/webm' });
      const url = URL.createObjectURL(blob);
      document.getElementById('playback-audio').src = url;
      document.getElementById('recording-done').style.display = 'block';
      stream.getTracks().forEach(t => t.stop()); // tắt mic sau khi xong
    };
    mediaRecorder.start();
    document.getElementById('rec-status').textContent = '🔴 Đang ghi âm...';
  } catch (err) {
    // Học sinh từ chối quyền mic, hoặc trình duyệt không hỗ trợ
    showRecordError('Không truy cập được microphone. Kiểm tra quyền truy cập trình duyệt.');
  }
}
function stopRecording() {
  mediaRecorder?.stop();
  document.getElementById('rec-status').textContent = '✅ Đã ghi xong';
}
```
> ⚠️ Ghi âm KHÔNG lưu lên server ở bản HTML standalone này — chỉ phát lại
> tại chỗ qua `URL.createObjectURL`. Nếu cần lưu, đó là việc của hệ thống
> backend riêng (ngoài phạm vi file này).
> ⚠️ Luôn xin quyền mic bằng 1 nút bấm rõ ràng — không tự động gọi
> `getUserMedia` khi trang vừa load, trình duyệt sẽ chặn hoặc gây khó chịu.

### 2.3 AI-Roleplay Ghi Âm Nhiều Lượt (Speaking Production)

```
Pattern (dùng đúng cho Bước 3 Production ở Speaking — Vy/cô Vân/thầy Đức
hỏi lại nhiều lượt):

State machine đơn giản — turn = 0,1,2...
  turn 0: hiện câu hỏi/tình huống mở đầu của nhân vật AI → học sinh ghi âm
  sau khi ghi âm xong (2.2) → hiện nút "Nghe câu hỏi tiếp theo"
  → hiện lời thoại AI turn tiếp theo → học sinh ghi âm lượt mới
  ... lặp lại đến hết số lượt đã định (2 cho mức TB, 3-4 cho mức Khó)
  → hiện toàn bộ model answer CHO TỪNG LƯỢT (không gộp 1 cục ở cuối)
```
```javascript
let currentTurn = 0;
const dialogueScript = [ /* mảng lời thoại AI theo turn, từ kịch bản đã duyệt */ ];

function nextTurn() {
  currentTurn++;
  if (currentTurn >= dialogueScript.length) { showAllModelAnswers(); return; }
  document.getElementById('ai-line-' + currentTurn).style.display = 'block';
  document.getElementById('record-turn-' + currentTurn).style.display = 'block';
  document.getElementById('record-turn-' + currentTurn)
    .scrollIntoView({behavior:'smooth', block:'nearest'});
}
```
> Model answer của mỗi lượt PHẢI ẩn cho đến khi học sinh ghi âm xong lượt đó
> — không hiện trước, đúng nguyên tắc đã có sẵn trong kịch bản Speaking gốc.

---

## PHẦN 3 — FEEDBACK & PROGRESS (áp dụng chung mọi module)

### 3.1 Progressive Unlock (`.slocked` / `.ulock`)

```javascript
function unlockSection(sectionId, lockNoticeId) {
  document.getElementById(sectionId).classList.remove('slocked');
  document.getElementById(lockNoticeId).style.display = 'none';
}
```
```css
.slocked{opacity:0.4;pointer-events:none}
.ulock{display:flex;align-items:center;gap:8px;padding:0.65rem 1rem;
  background:var(--cream-2);border-radius:var(--radius);font-size:13px;
  color:var(--ink-2)}
```

### 3.2 Score & Module-Done Tracking (`doneMod`)

```javascript
const modDone = {};
function doneMod(id, next) {
  modDone[id] = true;
  document.getElementById('st-' + id).textContent = '✓';
  document.getElementById('nav-' + id).classList.add('done');
  const doneCount = Object.keys(modDone).length;
  document.getElementById('uprg').style.width = (doneCount / 10 * 100) + '%';
  document.getElementById('uprg-txt').textContent = doneCount + ' / 10 modules hoàn thành';
  if (next) { showMod(next); }
}
```

### 3.3 Quy Tắc Next Button — KHÔNG Auto-Advance

*(Áp dụng y hệt nguyên tắc gốc từ Toán — không đổi)*
Sau khi học sinh trả lời đúng/hoàn thành 1 bước, KHÔNG tự động chuyển sang
bước tiếp theo ngay lập tức — luôn có 1 khoảng dừng (hiện giải thích/kết quả
trước), rồi học sinh tự bấm nút "Tiếp tục" khi sẵn sàng. Tự động chuyển làm
học sinh không kịp đọc giải thích.

### 3.4 Đếm Item Đã Xem Để Mở Khoá (Set-based)

```
Dùng khi cần "xem hết N item mới mở khoá bước tiếp" — VD vocab card grid
(1.9 file 02): phải click xem hết 5 collocation mới mở nút "Continue".
Dùng Set thay vì đếm số (number) để tránh đếm trùng khi học sinh click lại
item đã xem.
```
```javascript
const seenItems = new Set();
function revealItem(i, total, onAllSeen){
  // ...logic hiện nghĩa/nội dung của item i...
  seenItems.add(i);
  if (seenItems.size >= total) onAllSeen(); // vd: enable nút Continue
}
```

---

### 3.5 Adaptive Level Routing — Tự Chọn Easy/Medium/Difficult Theo Performance (KHÔNG hiện tên mức)

```
Dùng khi kịch bản yêu cầu ẨN nhãn Easy/Medium/Difficult khỏi học sinh và để hệ thống tự gán mức
dựa trên performance ở phần trước (VD Mission/Hook có tương tác chấm được đúng-sai/số lần thử) —
khác hẳn Level Tabs chuẩn (4.5 ở 02_design, học sinh tự bấm chọn tường minh). Đây là pattern MỚI,
chỉ dùng khi kịch bản NÊU RÕ muốn adaptive — không tự áp dụng cho module khác nếu kịch bản không
yêu cầu, vì mặc định toàn hệ thống vẫn là chọn tường minh qua Level Tabs.

Nguyên tắc:
  1. Đếm "mistakeScore" xuyên suốt phần Mission/Hook phía trước — mỗi lần chọn sai/thử lại 1 câu
     tính +1 (dùng đúng cơ chế đã có ở gợi_ý_khi_sai/retry, không tạo cơ chế chấm mới).
  2. Sau khi Mission hoàn tất, map mistakeScore → 1 trong 3 mức, dùng NGƯỠNG rõ ràng (chỉnh theo
     độ dài Mission, không cứng số 0/2/4 cho mọi module):
       0-1 lỗi  → mức khó nhất (Difficult)
       2-3 lỗi  → mức trung (Medium)
       4+ lỗi   → mức dễ nhất (Easy)
  3. Hiện mức đã gán bằng TÊN THEO NARRATIVE của module (không hiện chữ "Easy/Medium/Difficult"),
     kèm 1 nút override nhỏ để học sinh tự đổi nếu muốn — KHÔNG ép buộc tuyệt đối, tôn trọng quyền
     tự chọn của học sinh, chỉ đổi hành vi mặc định.
  4. `cat`/`level` bên trong dữ liệu câu hỏi vẫn giữ đúng easy/medium/difficult như mọi module khác
     (đây là dữ liệu kỹ thuật cho việc chấm & phân tích, KHÔNG phải nhãn hiển thị) — chỉ đổi TÊN
     HIỂN THỊ ở UI, không đổi cấu trúc dữ liệu 3 mức đã có.
```
```javascript
let mistakeScore = 0;
function recordMistake() { mistakeScore++; } // gọi ở đúng chỗ đang gọi retry/gợi ý khi sai

function routeToLevel() {
  let level;
  if (mistakeScore <= 1) level = 'difficult';
  else if (mistakeScore <= 3) level = 'medium';
  else level = 'easy';
  return level; // dùng để tự load đúng bộ câu hỏi, KHÔNG hiện chữ 'difficult' ra UI
}

function showAssignedLevel(level, narrativeNames) {
  // narrativeNames = {easy: '🌱 Quick check', medium: '🌿 Dig deeper', difficult: '🌳 Full investigation'}
  document.getElementById('assigned-level-label').textContent = narrativeNames[level];
  document.getElementById('override-panel').dataset.currentLevel = level;
}
function overrideLevel(newLevel) {
  // học sinh bấm nút đổi mức — ghi đè lựa chọn tự động, vẫn dùng chung bộ dữ liệu 3 mức có sẵn
  loadQuestionSet(newLevel);
}
```
> ⚠️ Ngưỡng mistakeScore ở trên là VÍ DỤ — mỗi module cần tính lại theo số điểm chấm được thực tế
> có trong Mission phía trước (VD Mission có 4 mini-check thì ngưỡng nên chia theo /4, không copy
> nguyên 0-1/2-3/4+ nếu Mission khác có ít/nhiều điểm chấm hơn).
> ⚠️ KHÔNG lộ số mistakeScore hay chữ "Easy/Medium/Difficult" ra UI dưới bất kỳ hình thức nào (kể
> cả tooltip/debug) — mục tiêu là học sinh cảm thấy mức độ do "câu chuyện" quyết định, không phải
> bị dán nhãn năng lực.
> ⚠️ Luôn có nút override — thiếu nút này biến adaptive thành ép buộc, vi phạm nguyên tắc tôn trọng
> quyền tự quyết của học sinh.

---

### 3.6 Vocabulary Word-Mastery Tracking & Recap (chỉ module Vocabulary, kiến trúc mới)

```
Dùng khi build module Vocabulary theo PROMPT_TEMPLATE_VOCABULARY_v5_2 trở lên (kiến trúc "Warm-up →
Flashcards → 4 Trạm → Extra Practice → Recap") — module này KHÔNG còn Self-evaluation tĩnh, thay
bằng Recap ĐỘNG tính theo từng từ, xuyên suốt cả 4 Trạm lẫn Extra Practice.

Nguồn dữ liệu: kịch bản có nhãn [Trạm: X · Từ: word1, word2] hoặc [Extra Practice — Bài N · Từ: ...]
ngay phía trên mỗi câu hỏi — nhãn này ẨN khỏi UI học sinh (đúng quy tắc chung "nhãn kỹ thuật không
hiển thị" của toàn hệ thống), nhưng dữ liệu `words` + `station` PHẢI được giữ lại làm field kỹ thuật
trong object câu hỏi khi build HTML — cùng nguyên tắc với field `cat`/`level` ở 3.5 (dữ liệu chấm &
phân tích, không phải nhãn hiển thị).

Nguyên tắc tính mastery — theo TRẠNG THÁI CUỐI CÙNG, không phải lần trả lời đầu tiên:
  - Học sinh sửa lại câu trả lời (retry) → ghi đè trạng thái đúng/sai của câu đó cho từ liên quan,
    không cộng dồn/trừ điểm qua các lần thử (khác 3.5 — 3.5 đếm SỐ LẦN sai để routing độ khó, còn
    đây chỉ quan tâm KẾT QUẢ CUỐI CÙNG của mỗi câu để biết từ đó đã "thuộc" chưa).
  - 1 từ được xem là "mastered" khi TẤT CẢ câu hỏi gắn nhãn từ đó (ở mọi Trạm + Extra Practice) đều
    ở trạng thái đúng — chỉ cần 1 câu còn sai là từ đó rơi vào "review".
  - 1 câu có thể gắn nhiều từ cùng lúc (thường gặp ở Extra Practice Bài 3) — cập nhật trạng thái cho
    TẤT CẢ từ trong nhãn đó, không chỉ từ đầu tiên.
```

```javascript
// wordTrack: { word: { answers: {questionId: bool}, wrongStations: Set } }
const wordTrack = {};

// Gọi 1 lần khi render mỗi câu hỏi, lấy dữ liệu words/station từ field kỹ thuật (không phải nhãn UI)
function registerWordQuestion(questionId, words, stationLabel) {
  words.forEach(w => {
    if (!wordTrack[w]) wordTrack[w] = { answers: {}, wrongStations: new Set() };
  });
}

// Gọi mỗi khi học sinh chấm/sửa 1 câu — dùng chung điểm gọi với cơ chế chấm sẵn có của từng dạng bài
// (MCQ click, gap-fill so khớp text không phân biệt hoa/thường + trim khoảng trắng thừa, bảng điền
// từ ở Trạm 3 dùng cùng cơ chế so khớp text như gap-fill)
function recordWordAnswer(questionId, words, stationLabel, isCorrect) {
  words.forEach(w => {
    if (!wordTrack[w]) wordTrack[w] = { answers: {}, wrongStations: new Set() };
    wordTrack[w].answers[questionId] = isCorrect;
    if (isCorrect) wordTrack[w].wrongStations.delete(stationLabel);
    else wordTrack[w].wrongStations.add(stationLabel);
  });
}

function buildRecap() {
  const mastered = [];
  const review = {}; // { word: [stationLabel, ...] }
  Object.entries(wordTrack).forEach(([word, data]) => {
    const answered = Object.values(data.answers);
    const allCorrect = answered.length > 0 && answered.every(Boolean);
    if (allCorrect) mastered.push(word);
    else review[word] = [...data.wrongStations];
  });
  return { mastered, review };
}

// Gọi ở màn Recap cuối bài — SAU khi hoàn thành Extra Practice Bài 3, đúng quy tắc Next Button (3.3)
// không auto-advance, học sinh tự bấm vào màn Recap.
function renderRecap() {
  const { mastered, review } = buildRecap();
  const reviewWords = Object.keys(review);

  document.getElementById('recap-mastered').textContent = mastered.length ? mastered.join(', ') : '—';

  if (reviewWords.length === 0) {
    document.getElementById('recap-tip').textContent =
      "You've got all the words down! Ready for the next lesson.";
    document.getElementById('recap-review-row').style.display = 'none';
  } else {
    document.getElementById('recap-review-row').style.display = 'flex';
    document.getElementById('recap-review').textContent = reviewWords.join(', ');
    const stationsToRevisit = [...new Set(Object.values(review).flat())];
    document.getElementById('recap-tip').textContent =
      `Tip: go back to ${stationsToRevisit.join(', ')} to practice these again.`;
  }
}
```
> ⚠️ **3 ràng buộc bắt buộc** (dễ sai khi build): (1) `registerWordQuestion`/`recordWordAnswer` dùng
> field `words`/`station` lấy TỪ nhãn kỹ thuật trong kịch bản — không tự suy luận từ nội dung câu
> hỏi nếu kịch bản không gắn nhãn rõ; (2) `renderRecap()` chỉ gọi SAU khi học sinh đã hoàn thành toàn
> bộ Extra Practice (đủ dữ liệu để tính), không gọi giữa chừng khi còn Trạm chưa làm — Recap giữa
> chừng sẽ cho kết quả sai vì thiếu dữ liệu; (3) KHÔNG viết nội dung Recap tĩnh cố định thay cho hàm
> này dưới bất kỳ hình thức nào, kể cả khi kịch bản có sẵn câu mẫu — câu mẫu trong kịch bản CHỈ là
> template có placeholder `{mastered_words}`/`{review_words}`, không phải nội dung cuối.
> ⚠️ Nếu 1 Unit có nhiều bài Vocabulary khác nhau (nhiều bộ key words khác nhau trong cùng Unit),
> `wordTrack` reset về rỗng khi bắt đầu bài Vocabulary mới — không cộng dồn từ vựng của bài trước.

---

### 4.1 Model 3D — `<model-viewer>` (Hình thức D — file 01)

```html
<script type="module" src="https://unpkg.com/@google/model-viewer/dist/model-viewer.min.js"></script>

<model-viewer
  src="[ten-file].glb"
  auto-rotate camera-controls
  loading="lazy"
  poster="[anh-thumbnail-tam-thoi].jpg"
  style="width:100%;height:280px;background:var(--cream-2);border-radius:var(--radius-lg)">
  <div slot="progress-bar"></div>
</model-viewer>
```
```javascript
// Xử lý lỗi load model — fallback về ảnh 2D nếu .glb lỗi/quá nặng
document.querySelectorAll('model-viewer').forEach(mv => {
  mv.addEventListener('error', () => {
    mv.outerHTML = `<img src="${mv.dataset.fallback}" style="width:100%;border-radius:var(--radius-lg)">`;
  });
});
```
> `loading="lazy"` + `poster` bắt buộc — model 3D thường vài trăm KB đến vài
> MB, không nên tải ngay khi trang mở nếu học sinh chưa cuộn tới. Luôn có
> ảnh fallback 2D phòng khi model lỗi hoặc mạng chậm.

### 4.2 Text-to-Speech Phát Âm Từ Đơn

> ⚠️ **`utter.lang = 'en-GB'` là bắt buộc, không tự đổi** (xem `02_design_tiengAnh.md` Mục 0
> nguyên tắc 12) — mọi biến thể hàm `speak()` khác trong file này/component mới đều phải giữ đúng
> `'en-GB'`, không dùng `'en-US'` hay để mặc định trống.

```javascript
function speak(text) {
  const utter = new SpeechSynthesisUtterance(text);
  utter.lang = 'en-GB';
  utter.rate = 0.9;
  speechSynthesis.speak(utter);
}
```
> Không hoạt động tốt trên tất cả trình duyệt/thiết bị (chất lượng giọng
> khác nhau) — chỉ dùng cho phát âm từ đơn nhanh, KHÔNG thay thế audio file
> thật đã thu sẵn cho các bài nghe chính (Listening, Speaking model answer).

**Dùng cho bài "Listen and Circle" (Pronunciation, mức Nhận biết/Thông hiểu):** mỗi câu có 1 nút
🔊 phát đúng 1 từ mục tiêu qua `speak()`, học sinh chọn từ nghe được trong 3 lựa chọn hiển thị
bằng chữ (options là các từ minh hoạ/gây nhiễu âm gần giống — dữ liệu này lấy nguyên từ kịch bản,
không tự sinh). Đây vẫn là MCQ chấm điểm bình thường (không dùng pattern "ghi nhận không chấm điểm"
ở 1.6) — chỉ khác phần đề bài là audio thay vì chữ.

```javascript
function playPromptWord(word, btnId) {
  const btn = document.getElementById(btnId);
  btn.disabled = true; // chặn double-click trong lúc đang phát
  const utter = new SpeechSynthesisUtterance(word);
  utter.lang = 'en-GB'; utter.rate = 0.85; // chậm hơn nhẹ so với speak() thường vì học sinh cần nghe rõ để phân biệt minimal pairs
  utter.onend = () => { btn.disabled = false; };
  speechSynthesis.speak(utter);
}
```
> Cho phép bấm lại nút 🔊 nhiều lần (không giới hạn số lần nghe) — khác Read Aloud/Ghi âm (9.4 file
> 02) vốn giới hạn số lượt thử; nghe lại không phải "gian lận" ở dạng bài nhận diện âm.

---

## PHẦN 5 — GIỚI HẠN VÒNG LẶP

```
- Nếu sau 2 lần fix lỗi vẫn không đúng: dừng và hỏi lại 3 câu:
  1. "Bạn thấy gì trên màn hình?" (yêu cầu upload ảnh/video ngắn)
  2. "Bạn mong muốn nó hoạt động thế nào?"
  3. "Lỗi xảy ra khi làm thao tác gì, trên thiết bị/trình duyệt nào?"

- Lỗi hay gặp:
  → Before/After Slider (1.16) kéo bị cuộn cả trang trên mobile: kiểm tra
    `.comparison-container` có `touch-action:none`, và `touchmove` đăng ký
    `{ passive:false }` kèm `e.preventDefault()` trong handler — thiếu 1 trong 2 là hỏng, và
    chuột/DevTools responsive mode KHÔNG lộ được lỗi này, phải test bằng ngón tay thật
  → Audio không play được: kiểm tra gọi play() có nằm trong user gesture
    trực tiếp không (đặc biệt iOS Safari)
  → Ghi âm không xin được quyền mic: kiểm tra trang chạy trên HTTPS
    (getUserMedia bị chặn trên HTTP, trừ localhost)
  → Hotspot lệch vị trí trên mobile: kiểm tra dùng % không phải px
  → model-viewer không hiện: kiểm tra định dạng đúng .glb, dung lượng dưới
    ~5MB cho web, và script CDN đã load trước khi element render
  → Tap-to-Match (1.3) tap không ăn trên mobile: kiểm tra vùng chạm mỗi chip ≥44px (Mục 0 nguyên
    tắc 6) — khác lỗi kéo-thả cũ, đây thường chỉ là thiếu padding chứ không phải lỗi event
  → Vocabulary Recap (3.6) hiện sai/thiếu từ: kiểm tra (1) mọi câu hỏi đều có field `words` khớp
    CHÍNH XÁC chính tả với key word gốc trong Flashcards (lệch 1 ký tự = tính thành 2 từ khác nhau
    trong `wordTrack`), (2) `renderRecap()` không bị gọi trước khi học sinh làm xong Extra Practice
    Bài 3, (3) nếu 1 câu gắn nhiều từ, cả mảng `words` đã được truyền đủ vào `recordWordAnswer` chứ
    không chỉ từ đầu tiên

- Mỗi phiên chỉ build 1 file HTML cho 1 module.
```
