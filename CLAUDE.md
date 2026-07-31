# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

# Critical Rules

BEFORE modifying, writing, or refactoring any code files, you MUST ALWAYS:
1. Read the design specification file `02_design_tienganh.md` at the repo root, in full.
2. Ensure the proposed code changes strictly follow the logic and rules defined in `02_design_tienganh.md`.

This is also enforced by an `always_on` agent rule at `.agents/rules/read-design.md` — do not skip step 1 even for a small change.

## What this repository is

Không phải một codebase phần mềm thông thường. Đây là workspace nội dung cho môn **Tiếng Anh** của hệ thống Aiducation: từ kịch bản bài học viết bằng Markdown, AI build ra **file HTML tự chứa (self-contained)** — mỗi module/phần nhỏ của một Unit là 1 file HTML độc lập, nhúng được vào LMS qua iframe.

Không có build system, package manager, test runner hay lint. "Chạy" một sản phẩm = mở file HTML trong trình duyệt (`.vscode/settings.json` đặt Live Server ở cổng 5501). Ngôn ngữ làm việc mặc định là **tiếng Việt**.

Toàn bộ file hiện có ở repo:

- [02_design_tienganh.md](02_design_tienganh.md) — design system + component library (Mục 4.1–4.17) + quy trình build + 2 checklist bàn giao. **Nguồn chân lý duy nhất** cho mọi file HTML sinh ra.
- [Unit_2_Getting_Started.md](Unit_2_Getting_Started.md) — kịch bản đầu vào đã build xong (objectives → bài đăng + bình luận → từ vựng → luyện tập 3 mức → self-assessment). Khối 1 là bài đăng mạng xã hội + bình luận (`renderPost()`, không phải Phone Chat).
- [claude_lam.html](claude_lam.html) — **bản build 1 file hoàn chỉnh nhất hiện có** (~1.1MB): Unit 1 Getting Started · Family Life, gộp Khối 1 + Luyện tập + Self-assessment trong 1 file (`#sec-top`/`#sec-practice`/`#sec-assess`, Top Panel có `switchTopView`), **có 8 ảnh thật nhúng bằng `data:image/jpeg`** trong `vocab[].img`. **Reference implementation cho bản 1 file — đọc trước khi build bài mới.** (Tên file lịch sử, không theo quy ước `Unit_x_...`.)
- [Unit_2_Getting_Started_lesson.html](Unit_2_Getting_Started_lesson.html) + [Unit_2_Getting_Started_practice.html](Unit_2_Getting_Started_practice.html) — Unit 2 tách 2 file theo Mục 8; đối chiếu với kịch bản để thấy đúng ranh giới cắt. (Bản gộp 1 file `Unit_2_Getting_Started.html` từng tồn tại nhưng đã bị xoá — dùng `claude_lam.html` làm mẫu 1 file.)
- [Unit_5_Getting_Started.md](Unit_5_Getting_Started.md) — kịch bản Inventions (hội thoại nhắn tin 1-1 → dùng **Phone Chat 4.3 thật**, không phải Social Post), **đã build** thành cặp [Unit_5_Getting_Started_lesson.html](Unit_5_Getting_Started_lesson.html) + [Unit_5_Getting_Started_practice.html](Unit_5_Getting_Started_practice.html). Lesson dùng `renderNextMessage()`/`buildMsgRow()` — mẫu Phone Chat tham chiếu khi kịch bản là chat 1-1.
- [.agents/rules/read-design.md](.agents/rules/read-design.md) — rule `always_on`.
- [.claude/settings.json](.claude/settings.json) — hook `SessionStart` chạy `cat 02_design_tienganh.md`, tự nạp design file vào context mỗi phiên (output ~98KB nên thường bị lưu ra file tạm, phải đọc lại bằng tool).

**Kịch bản `.md` không chỉ là nội dung thô** — sau khi build, quyết định thiết kế được ghi ngược lại vào chính file kịch bản dưới dạng blockquote/bảng ("đã chốt khi build — dựng lại phải giữ nguyên", VD bố cục thẻ bài đăng ở [Unit_2_Getting_Started.md](Unit_2_Getting_Started.md)). Đọc HẾT file kịch bản, các bảng đó ràng buộc ngang design file. Quy ước trong kịch bản: `[*từ*]` = từ khoá phải tô bằng `.kw-inline`.

Design file có nhắc tới `01_scenario_builder_tienganh.md`, `01_scenario_builder_v4.md`, `02_design_toan_final_v2.md`, `AIDUCATION_UI_REDESIGN_PLAYBOOK.md` — **các file này KHÔNG có trong repo**, đừng mất thời gian đi tìm. Mọi thứ cần thiết (token màu Mục 1, hợp đồng LMS Mục 6) đã được nhúng đầy đủ trong `02_design_tienganh.md` để nó dùng độc lập được.

## Hành vi mặc định khi được giao kịch bản

Người dùng đính kèm file kịch bản (hoặc chỉ nói "build"/"thiết kế"/tên Unit) → **build thẳng ra HTML, không hỏi lại, không xin xác nhận, không hỏi chọn màu/font/layout** (đã cố định 100%). Xong thì báo 1 dòng ngắn (số collocations, số câu mỗi mức). Chỉ hỏi lại khi thiếu hẳn một phần bắt buộc (VD có hội thoại nhưng không có nghĩa tiếng Việt của từ vựng) — hỏi đúng phần thiếu, một câu ngắn.

**Mặc định build 1 file HTML duy nhất.** Chỉ tách thành Lesson file + Practice file (Mục 8) khi người dùng chủ động yêu cầu — không tự ý tách vì thấy file dài.

## Kiến trúc một file HTML sinh ra

Quy trình chọn cấu trúc (Mục 4.0): đọc kịch bản thật → liệt kê các hoạt động thực tế → map mỗi hoạt động vào component ở Mục 4.1–4.17 → sắp theo mạch dạy. **Không suy cấu trúc từ tên module** ("Reading" không bắt buộc phải là warm-up → passage → comprehension); phần nào kịch bản không cần thì bỏ hẳn.

Nguyên tắc chia khối xuyên suốt: **Khối 1 = Bài học** (tiếp xúc nội dung mới, KHÔNG chấm điểm) tách bạch **Khối 2 = Luyện tập** (làm bài có đúng/sai). Nội dung Khối 1 chỉ được xuất hiện lại trong Khối 2 dưới dạng tham chiếu read-only, không lặp lại tương tác gốc (không lật thẻ, không phát âm trong Reference Pane).

Khung hay gặp cho bài có đủ hội thoại + từ vựng + luyện tập:

```
#progress-tracker (sticky; desktop = cột phải, mobile = thanh ngang cuộn ngang)
header.hero (tuỳ chọn, ẩn được bằng display:none)
#sec-top      → KHỐI 1. Top Panel gộp: Phone Chat (4.3) + Vocabulary (4.4), có tab + nút Gom + khoá tuần tự (4.8)
#sec-practice → KHỐI 2. #practiceLock / #practiceInner:
                  Practice Reference Pane (4.8b, nếu luyện tập gắn với Khối 1)
                  + Level Tabs (4.5) + các dạng bài (4.6), chạy step-gate tuần tự
#sec-assess   → Self-assessment + Finale (4.7)
```

Component Khối 1 do hoạt động thật quyết định, không do tên module: Unit 2 là bài đăng mạng xã hội + bình luận (`renderPost()`, `#commentList`, `#cmtCount`) chứ không phải Phone Chat, nhưng vẫn giữ nguyên hành vi bắt buộc của 4.3 (hiện dần theo nhịp bấm, typing-indicator, nút "hiện hết", đọc hết → `markDone('messages')` + `unlockVocabTab()`).

Luồng khoá tuần tự: đọc hết tin nhắn (hoặc bấm "Đã đọc rồi — hiện hết tin nhắn ⏭") → `unlockVocabTab()` → lật hết thẻ từ vựng → `unlockPractice()` (chỉ ở đây mới gọi `populatePracticeRef()` rồi `renderLevel('easy')`, không dựng Luyện tập sớm hơn). Mỗi phần xong gọi `markDone(key)` + `LMS().progress()`.

## Hình dạng data trong `<script>` (theo Unit 2 — bám đúng khi build bài mới)

Toàn bộ nội dung khai báo thành 4–5 mảng/object ở đầu script, phía trên mọi hàm; UI dựng từ đó, không hard-code HTML nội dung.

- `messages[]` — `{ who: 'a'|'b', kind?: 'post', time, text }`. Phần tử `kind:'post'` là bài đăng gốc, phần còn lại là bình luận (`totalComments = messages.length - 1`). `text` là field DUY NHẤT không `esc()` (chứa sẵn `<span class="kw-inline">`).
- `vocab[]` — `{ word, ipa, nghia, ex, img, illus }`. **Luôn sinh sẵn ô `img: ''` kèm comment `/* ← dán link ảnh "<từ>" vào đây */` cho MỌI thẻ** để người soạn dán ảnh thật vào sau; `illus` (chuỗi SVG inline `viewBox="0 0 200 200" preserveAspectRatio="xMidYMid meet"`, **không có rect nền** — nền do `.illus-box` lo) là bản dự phòng khi `img` trống hoặc link tải hỏng. `illusHTML(v)` chọn theo thứ tự `img` → `illus` → ô chờ `.illus-empty`; `wireIllusFallback()` bắt sự kiện `error`. Link `img` chỉ được thuộc 3 dạng sandbox cho phép: `data:` URI, `cdn.jsdelivr.net`, hoặc đường dẫn tương đối — link Drive/Imgur mở Live Server thì thấy nhưng nhúng LMS bị chặn. `illus` là chỗ duy nhất được ghi mã hex trực tiếp.
- `matchPairs[]` — `{ term, def, why }`. **Dùng object ghép cặp sẵn, KHÔNG dùng mảng song song + `correctLetters`** — cách này triệt tiêu hẳn lỗi lệch thứ tự bên dưới; `why` là giải thích hiện sau khi nối.
- `practiceData = { easy, medium, hard }` — mỗi mức là object với các key TUỲ CHỌN: `tf`, `mcq`, `matching`, `categorize`, `sequencing`, `oddone`, `gapfill`, `paraGapfill`, `writing`. `buildStepsForLevel()` đẩy step theo đúng thứ tự đó, chỉ khi key tồn tại → mức nào không có dạng nào thì bỏ key, không để mảng rỗng. Thêm dạng bài mới = thêm nhánh ở CẢ `buildStepsForLevel()` VÀ `isStepComplete()`.
- `assessItems[]` — chuỗi "I can…" cho self-assessment.
- Câu TF/MCQ: `explain` (giải thích chung, bắt buộc) + `explainWrong` (tuỳ chọn, câu bồi thêm khi học sinh chọn sai) — Unit 2 chỉ dùng `explainWrong` cho TF.

## Ràng buộc cứng (vi phạm là phải sửa)

- **Token màu Mục 1 nguyên bản** — `--cream/--jade-deep/--ink/--correct/--wrong/...`. Không alias kiểu `--primary`, `--bg`, `--surface`. Không tô màu riêng theo kỹ năng (Reading=xanh, Speaking=đỏ). `--jade-deep` là màu hành động chính ở mọi module; `--wrong` chỉ dùng cho trạng thái sai, không dùng cho CTA; `--accent` cho trạng thái đang chọn/hover.
- **Font duy nhất Be Vietnam Pro**, kể cả heading (weight 700–800). `body { font-size: 18px }`.
- **1 file HTML = 1 module độc lập.** Không sidebar/header điều hướng nhiều module trong cùng file.
- **Cấm drag-and-drop hoàn toàn** — nối từ (4.12), sắp xếp câu (4.13) và cả **phân loại/xếp nhóm (4.17)** đều phải là tap-to-select. 4.17 hay bị quên nhất vì trực giác "phân loại = kéo vào ô".
- **Mỗi câu hỏi phải có field `explain`** (giải thích tiếng Việt), hiện sau khi trả lời. Không chỉ báo đúng/sai.
- **Xáo vị trí đáp án khi render, không gán cứng trong data.** MCQ dùng `shuffleMCQOptions()` (đáp án đúng luôn viết ở `options[0]` khi soạn data, so khớp bằng TEXT không bằng index). Matching/Categorize xáo bằng `.sort(() => Math.random() - 0.5)` — Matching xáo cả 2 cột. Xáo mỗi lần render, không xáo một lần rồi lưu.
- **Mọi text tự do chèn vào `innerHTML` phải qua `esc()`** (định nghĩa 1 lần ở đầu `<script>`, xem 4.3). Ngoại lệ duy nhất: field đã chủ động chứa markup cần giữ, VD `message.text` có sẵn `<span class="kw-inline">` — không esc field đó, vẫn esc các field text thuần khác trong cùng object.
- **Vocabulary (4.4) tối đa 12 thẻ.** Desktop = lưới, số cột co theo `vocabGrid.dataset.count` + class `.compact`; mobile ≤640px = **carousel vuốt ngang** có nút `‹ ›` và bộ đếm "3/12", KHÔNG xếp lưới dọc. Nhiều hơn 12 từ → tách thành 2 tab Vocabulary A/B, không nhồi 1 carousel.
- **Practice Reference Pane (4.8b) là bắt buộc** khi Luyện tập gắn trực tiếp với nội dung Khối 1 (hội thoại/từ vựng/Reading Passage): desktop chia đôi theo chiều dọc (2 cột, `≥992px`), mobile chia đôi theo chiều ngang + thanh `.mobile-pane-controls` (Chia đôi / Bài đọc / Câu hỏi) đổi thật `max-height` từng pane. Nếu Luyện tập độc lập (VD ngữ pháp thuần) → **bỏ hẳn**, không nhét pane rỗng cho có. Nội dung pane dựng từ chính mảng `messages`/`vocab` của Khối 1, không soạn data riêng.
- **Nhãn giai đoạn/tab bằng tiếng Anh** (`Messages`/`Vocabulary`/`Practice`/`Easy`/`Medium`/`Hard`); nút thao tác UI giữ tiếng Việt ("Tin tiếp theo →", "Gom lại").
- **Step-gate**: trong 1 mức chỉ hiện 1 dạng bài tại một thời điểm; nút "Tiếp theo →" chỉ bật khi làm xong bước hiện tại (`isStepComplete()` phải có nhánh cho mọi dạng bài đang dùng); bước cuối đổi thành "Hoàn thành mức này ✓" và hiện nút nhảy thẳng sang mức còn lại.
- **Sandbox LMS**: chỉ được gọi mạng tới `cdn.jsdelivr.net`, `fonts.googleapis.com`, `fonts.gstatic.com`. Không `localStorage`/cookie — state lưu qua `LMS().state()`. Không build step, không `import`, không `eval`.
- Mobile-first, mọi vùng chạm ≥ 44px (`chip-btn`, `level-tab`, `audio-btn`, `top-tab`, `vnav-btn`, `mpc-btn`, `pref-tab`...), test ở 375 / 768 / 1280px.

## Hợp đồng LMS (dán nguyên, không viết khác đi — Mục 6)

- Safe accessor `function LMS(){...}` đặt đầu `<script>` đầu tiên.
- `<script type="application/json" id="athena-context">` trong `<head>`; `structure[].id` phải khớp id thật đang dùng (không cố định `messages/vocab/practice/assess`). `athenaGuidance` gồm đủ 3 phần: (a) module dạy gì; (b) đánh số từng câu hỏi kèm lựa chọn nguyên văn **+ nghĩa của toàn bộ từ vựng/collocations** (riêng Tiếng Anh); (c) không bao giờ lộ đáp án đúng.
- `LMS().complete({...})` bắn **đúng 1 lần**, guard bằng boolean; `items[]` chỉ gồm câu học sinh thực sự đã làm (chỉ làm mức Dễ → chỉ có câu mức Dễ).
- `reportHeight()` + `ResizeObserver`; bỏ hẳn `body{min-height:100vh}`/`height:100vh`.

## Lỗi đã gặp thật, dễ lặp lại

- **Matching `correctLetters` lệch thứ tự**: học sinh nối đúng nghĩa nhưng bị báo sai. Code chạy không lỗi cú pháp vẫn map sai. **Cách phòng đã áp dụng ở Unit 2: bỏ hẳn `correctLetters`, dùng `matchPairs[] = {term, def, why}` rồi xáo 2 cột lúc render** — cặp đúng nằm ngay trong 1 object nên không thể lệch. Nếu vì lý do nào đó vẫn phải dùng mảng song song, bắt buộc in bảng đối chiếu term ↔ định nghĩa và đọc lại bằng mắt cho **cả 3 mức**; 3 mức dùng chung bộ term thì thứ tự A–H phải giống hệt nhau ở cả 3 mảng.
- **Matching sai cặp + `setTimeout`**: phải chụp `const wrongTerm = selectedTerm` **trước** khi `selectedTerm = null`, nếu không callback 350ms sau sẽ chạm `null.classList`.
- **Top Panel phình dài**: `.cp-body` để `overflow:visible`, KHÔNG đặt `max-height` lên nó. Chiều cao Vocabulary được khống chế bằng `data-count` (desktop) và carousel (mobile), không bằng cuộn nội bộ như bản cũ.
- **Thẻ từ vựng mờ chữ trên điện thoại**: Chrome/Safari di động vẽ cả khối `transform-style:preserve-3d` ra 1 bitmap rồi mới xoay/phóng, làm chữ trong thẻ nhoè trong khi thanh Tasks/nút bấm ngay cạnh vẫn nét (rõ nhất ở carousel mobile, thẻ rộng 84% màn hình). Bắt buộc có class `.settled`: chỉ giữ 3D TRONG LÚC lật, lật xong (`setTimeout` ~620ms, KHÔNG dùng `transitionend` vì không bắn khi tắt animation/tab ẩn) thì `transform-style:flat` + đổi mặt bằng ẩn/hiện. Trong `flipCard()` phải theo ĐÚNG thứ tự: `inner.style.transition='none'` → `remove('settled')` → `void getComputedStyle(inner).transform` → `inner.style.transition=''` → toggle `.flipped`. Bỏ `.settled` khi transition đang bật sẽ tự khởi động chuyển tiếp 0°→180° rồi bị kéo ngược về 0° → **mất hiệu ứng ở CHIỀU LẬT NGƯỢC** (chiều xuôi vẫn chạy nên rất dễ nghiệm thu sót — phải bấm lật cả 2 chiều). Không dùng `void el.offsetWidth` để chốt mốc: nó chỉ ép tính lại layout, mà transform không làm bẩn layout nên bị bỏ qua.
- **Thẻ từ vựng phải truy cập được**: `.vcard` là `role="button"` + `tabIndex=0`, và `setFaceState()` phải chạy sau mỗi lần lật để set `aria-hidden` + `tabIndex` cho mặt đang úp (focus vào node `aria-hidden` là lỗi a11y). Không lồng `<button>` trong `<button>` — nút loa nằm trong `<div role="button">`.
- Bấm "Sang Luyện tập" phải tự Gom Top Panel lại để bài tập lọt màn hình ngay.

## Khi được yêu cầu tách 2 file (Mục 8)

Chỉ làm khi người dùng nói rõ. Ranh giới cắt = đúng ranh giới Khối 1 / Khối 2. Mẫu đã làm: `Unit_2_Getting_Started_lesson.html` + `_practice.html` (đặt tên `<tên kịch bản>_lesson/_practice.html`). Điểm dễ sai:

- `messages`/`vocab` phải copy y nguyên sang file Practice (sandbox không cho `import`), kèm comment `/* ĐỒNG BỘ với file <tên file kia> — sửa nội dung phải sửa CẢ 2 NƠI */` ở cả 2 file.
- Khoá tuần tự không chạy xuyên file → mặc định **bỏ khoá cứng** ở file Practice; không để vừa banner nhắc vừa lock dựa trên biến không tồn tại.
- Nút chuyển file dùng `location.href`/`<a>` thật, không gọi `switchTopView`/`toggleTopPanel`/`goToPractice`. File Lesson: lật hết thẻ → `unlockNextFile()` hiện `#nextFileRow` chứa `<a href="..._practice.html">`; file Practice có `.fn-back` quay lại Lesson.
- `#progress-tracker` mỗi file chỉ liệt kê đúng phần có trong file đó; `LMS().complete()` chỉ bắn ở file Practice.
- `athenaGuidance` phải **lặp lại đầy đủ nghĩa từ vựng ở CẢ 2 file** (Athena không đọc được manifest của file kia), và nói rõ đây là file 1/2 hay 2/2 kèm tên file còn lại.

## Trước khi giao file

Chạy hết checklist Mục 7 của [02_design_tienganh.md](02_design_tienganh.md) (+ Mục 8.3 nếu tách file). Kiểm nhanh phần dễ sót:

```powershell
Select-String -Path *.html -Pattern 'var\(--primary|var\(--surface\)|var\(--bg\)|var\(--text\)|var\(--border\)'
Select-String -Path *.html -Pattern '#2F6F62|#E8623D|#E8A33D'      # hex gốc bản tham khảo, phải = 0 kết quả
Select-String -Path *.html -Pattern 'draggable|dragstart|dragover' # kéo-thả, phải = 0 kết quả
Select-String -Path *.html -Pattern 'localStorage|sessionStorage'  # phải = 0 kết quả
Select-String -Path *.html -Pattern 'min-height:\s*100vh|height:\s*100vh'
Select-String -Path *.html -Pattern 'LMS\(\)\.complete\('           # xem TỪNG dòng, xem mục dưới
```

Lưu ý khi đọc kết quả:

- **Không grep hex chung chung.** Mã hex trong `illus` SVG của thẻ từ vựng là hợp lệ (Unit 2 có ~32 mã) — chỉ 3 hex bản tham khảo ở trên mới phải = 0.
- **`LMS().complete(` được phép ra >1 kết quả** vì comment cũng khớp (Unit 2 ra 2 dòng: 1 comment + 1 call thật). Phải mở từng dòng, xác nhận **đúng 1 call site thật** nằm trong `sendComplete()` có guard `completeSent`.
- Đếm thủ công: số object câu hỏi = số field `explain` (`explainWrong` là field phụ, đếm riêng, không tính vào đây).

Xem sản phẩm: mở file HTML bằng Live Server (cổng 5501) hoặc `start Unit_2_Getting_Started.html`. Test ở 375 / 768 / 1280px.
