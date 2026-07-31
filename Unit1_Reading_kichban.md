## Kịch bản: Reading — Unit 1 (Family life) — Reading

**Nguồn:** Unit1_Reading_v2.docx · đối chiếu Syllabus Unit 1, Week 1–3, dòng Lesson "Reading" (SB p11)
**Xác nhận:** Không có nội dung học thuật gốc nào bị sửa (đáp án/giải thích/6 từ vựng/12 câu × 3
mức giữ nguyên 100%). Chỉ thay đổi: (a) thứ tự/thời điểm trình bày (Hook + progressive reveal +
vocab-in-context thay cho khối tĩnh), (b) đổi mọi tương tác kéo-thả trong đề xuất gốc sang
tap-to-select (đúng Mục 0.4 design system), (c) thêm lớp "Prove it" (chọn câu chứng minh) chỉ cho
8/36 câu (True/False + Yes/No/Not Given) — không thêm/bớt đáp án đúng của các câu này, (d) **🆕 thêm
khối Strategy Reveal "Spot the Real Evidence"** (sau Discovery #3, trước Kết đoạn) dạy kỹ năng
Stated Details/Reading for Specific Information, dùng lại 100% câu đã có sẵn trong bài (không thêm
ngữ liệu mới ngoài cách phân vai 2 câu ở đoạn 6 cho Quick Check), cùng icon 💡 Recap ở Phần 2 tái
dùng cùng nội dung, (e) **🆕 sửa caption Hook** ("Bạn thấy quen không?" thay vì "Nghe quen không?")
và **nêu rõ đây là blog post** trong mission text Hook Stage 1 ("...in her blog post today"), (f)
**🆕 thêm text-reveal cho từ khó ở Reference Pane của Phần 2** (Practice) theo Level — Easy reveal
đủ 6 từ vựng chính thức + 4 từ khó bổ trợ, Medium chỉ reveal 2 từ khó nhất, Difficult không reveal
gì — KHÔNG áp dụng ở Phần 1 (Lesson) vì đã có kịch bản giảng/dịch trực tiếp, (g) **🆕 thay 1 câu
Easy MCQ Vận dụng lệch mục tiêu** (áp dụng tình huống mới → đổi thành câu kết hợp 2 đoạn, đúng
phạm vi Stated Details) và thêm dòng nhắc "kết hợp 2 đoạn" vào Strategy Reveal, (h) **🆕 mở rộng
icon 💡 Recap sang cả Difficult** (không chỉ 8 câu Prove-it) + 2 ràng buộc kỹ thuật (không
`recordMistake()`, không ví dụ mới trong popup), (i) **🆕 thêm nghĩa tiếng Việt vào toàn bộ 6 popup
từ vựng**, (j) **🆕 thêm dòng hướng dẫn on-screen** cho 3 tương tác tap-to-select (Card 1, Card 2
causal chain, Card 3) vốn trước đó chỉ có ghi chú kỹ thuật, chưa có câu hướng dẫn thật cho học
sinh.

---

### PHẦN 1 — LESSON (`unit1_reading_lesson.html`)

**Ảnh AI-generated (Hook mở đầu, trước cả Hero — theo đúng pattern Module 1A):**
`unit1_reading_hook_chore_dilemma.png` — hiển thị full-screen trước khi vào canvas bài học. Cảnh
phòng khách gia đình lúc chiều tối, một bạn nữ tuổi teen đứng lưỡng lự giữa chồng bát đĩa chưa rửa
và điện thoại trên sofa (đúng bối cảnh Stage 0 bên dưới). Không có lời thoại robot ở đây (khác
Module 1A — bài Reading không có nhân vật robot xuyên suốt); thay bằng 1 dòng dẫn ngắn song ngữ đè
lên góc dưới ảnh: *"Sound familiar? / Bạn thấy quen không?"* rồi tự fade-out 400ms sang Hero + Stage 0.
Học sinh có thể tap vào bất kỳ đâu trên ảnh để fade sớm hơn (không bắt buộc chờ hết 400ms).

**Hero:** Family Life — Benefits of Doing Housework / Lợi ích của việc làm việc nhà
Objectives: Understand and use vocabulary related to family life · Read for specific information
in a text about the benefits of doing housework for teenagers.

**Hook — Stage 0: Chore Dilemma** (Prediction Picker, không chấm điểm, pattern 1.6)
> Your parents are busy tonight. You finally have 30 minutes free.
Tap chọn 1 trong 3 card: 🧹 Clean the room / 🍽️ Do the dishes / 📱 "Pretend I didn't see anything"
— không đúng sai, chỉ ghi nhận.

Tiếp theo: **What do you actually get from doing chores?**
Tap chọn 1–2 trong: `Clean house` · `Life skills` · `Responsibility` · `Closer family` · `Nothing`
— không reveal đáp án, lưu lại prediction để dùng ở cuối bài (Back to You).

**Hook — Stage 1: The Mystery** (progressive reveal, pattern 1.7 áp dụng cho đoạn văn)
Hiện riêng đoạn (1), highlight câu: *"I've started to see chores in a different way."*
Hỏi (Prediction Picker, không chấm điểm): **Something changed Vy's mind. What do you predict
happened?** — tap chọn 1 trong: `She became better at chores` / `She understood her parents` /
`She discovered chores had other benefits` / `No idea yet`
Sau khi chọn → hiện mission: **Find 3 things that changed Vy's mind in her blog post today.** → hiện tiếp đoạn (2), rồi
mở khoá Benefit Hunt.

**Khối nội dung gốc — Reading Passage** (nguyên văn, chia thành 3 Evidence Card thay vì hiện 1 lần)

> **(1)** Hi everyone! Today let's talk about something most teenagers try to avoid — housework.
> I know many people don't enjoy doing the dishes or the laundry. But I've started to see chores
> in a different way.
> **(2)** Here are three things I've learned from doing housework.

**CARD 1 — Practical Skills** (đoạn 3)
> **(3)** First, it teaches me practical skills for real life. No one teaches you how to cook a
> simple meal or keep a room clean in class. You learn these things by doing them at home, again
> and again, until you can do them well.

**🆕 Dòng hướng dẫn thao tác, hiện on-screen (không chỉ ghi chú kỹ thuật):**
> *Tap the sentence that gives real evidence.*
> Tap vào câu có bằng chứng thật.

Tap chọn câu chứa evidence (2 lựa chọn, tap không kéo):
- ✅ "No one teaches you how to cook a simple meal or keep a room clean in class."
- ❌ "Here are three things I've learned from doing housework."

Sau đó: **Which example supports this?** (tap chọn 1/3) 🍳 cook a meal / 🧹 keep a room clean /
📚 pass an exam → chọn đúng 1 trong 2 đầu → mở khoá **DISCOVERY #1 — PRACTICAL SKILLS 🔓**

*Vocab-in-context ngay tại đây (giữ nguyên câu gap-fill gốc, chỉ đổi thời điểm hiện):*
Tap từ **responsibility** khi gặp ở Card 2 bên dưới (xem tiếp).

**CARD 2 — Responsibility** (đoạn 4)
> **(4)** Second, chores help me build **responsibility**. When a task belongs to me, there is no
> one else to do it instead. This makes me more careful and reliable, not only at home but in
> other parts of my life too.

Tap từ **responsibility** → popup nghĩa: *A duty to deal with or take care of something* — trách nhiệm, bổn phận phải lo liệu việc gì đó → hiện
ngay câu gap-fill gốc để check: "Second, chores help me build ______." → đáp án: *responsibility*.

**🆕 Dòng hướng dẫn thao tác, hiện on-screen (không chỉ ghi chú kỹ thuật):**
> *Tap the sentence that completes the chain.*
> Tap vào câu hoàn thành đúng chuỗi lý do.

Causal chain (tap-to-select, KHÔNG kéo-thả):
`A task belongs to me` → [tap chọn 1 trong 3 câu bên dưới] → `I become more careful & reliable`
- ✅ "There is no one else to do it instead"
- ❌ "My parents remind me every day"
- ❌ "I get paid for it"

Chọn đúng → mở khoá **DISCOVERY #2 — RESPONSIBILITY 🔓**

**CARD 3 — Family Bond** (đoạn 5)
> **(5)** Third, and this surprised me the most, chores can bring a family closer together. My
> parents work hard every day, and helping them shows me how much effort they put into taking
> care of our home. This gives me a lot of **gratitude** for them. Doing tasks together also
> helps **strengthen** the **bond** between family members in a way that just talking does not.

Tap từ **gratitude** → popup nghĩa: *The feeling of being thankful* — lòng biết ơn → gap-fill gốc: "This gives me
a lot of ______ for them." → đáp án: *gratitude*.
Tap từ **strengthen** → popup nghĩa: *To make something stronger* — làm cho vững chắc/mạnh hơn → gap-fill gốc: "Doing tasks
together also helps ______ the bond between family members." → đáp án: *strengthen*.
Tap từ **bond** → popup nghĩa: *A close connection between people* — mối liên kết gắn bó giữa người với người → gap-fill gốc: "...strengthen
the ______ between family members." → đáp án: *bond*.

**🆕 Dòng hướng dẫn thao tác, hiện on-screen (không chỉ ghi chú kỹ thuật):**
> *Tap the 2 sentences that give real evidence.*
> Tap vào 2 câu có bằng chứng thật.

Tap chọn 2 câu evidence trong đoạn (không kéo):
- ✅ "how much effort they put into taking care of our home"
- ✅ "strengthen the bond between family members"
- ❌ "chores can bring a family closer together" (đây là câu dẫn, không phải evidence)

Chọn đủ 2 câu đúng → hiện chuỗi: SEE THEIR EFFORT → ❤️ GRATITUDE → 👨‍👩‍👧 STRONGER BOND → mở khoá
**DISCOVERY #3 — FAMILY BOND 🔓**

---

### 🆕 STRATEGY REVEAL — "Spot the Real Evidence"
*(chèn ngay sau khi mở khoá đủ 3 Discovery, trước Kết đoạn — dạy kỹ năng Unit 1: Stated Details /
Reading for Specific Information)*

**Layout: Split view — tái dùng Reference Pane (mục 4.8b), KHÔNG bịa layout mới.**
Trái: đoạn văn liên quan (đánh dấu màu) · Phải: các bước Strategy, tap "Next" để chuyển bước → mỗi
bước active **auto-scroll + highlight đúng câu tương ứng bên trái** (liên kết động, không phải 2
khối tĩnh độc lập). Mobile ≤480px: dùng lại 3 chế độ xem sẵn có của Reference Pane (Chia đôi/Bài
đọc/Câu hỏi), mặc định mở "Chia đôi" thu gọn (passage ~40% màn hình phía trên, steps phía dưới).

**Bước 0 — Intro** (phải: text; trái: chưa highlight, hiện nguyên đoạn 3-4-5 vừa đọc)
> *Nice work! You found 3 pieces of real evidence. Let's see what they have in common. They're the
> foundation for Reading for Specific Information.*
> Bạn vừa tìm đúng 3 bằng chứng. Cùng xem điểm chung của chúng nhé — chúng chính là nền tảng của kỹ
> năng **Đọc tìm thông tin chi tiết (Reading for Specific Information)**, kỹ năng bạn sẽ dùng xuyên
> suốt phần Luyện tập.

**Bước 1 — Worked-example recap** (phải: bảng 3 cặp câu; trái: auto-scroll lần lượt đến đoạn 3 → 4
→ 5, mỗi lần scroll tới, câu ✅ sáng màu xanh lá + khung viền, câu ❌ tương ứng mờ đi/gạch nhẹ — đồng
bộ với đúng dòng phải đang hiển thị. Tap từng dòng bên phải → trái tự nhảy đúng đoạn + highlight
đúng cặp câu đó, không bắt buộc theo thứ tự)

| Card | ✅ Evidence | ❌ Câu bị loại |
|---|---|---|
| 1 (đoạn 3) | "No one teaches you how to cook a simple meal or keep a room clean in class." | "Here are three things I've learned from doing housework." |
| 2 (đoạn 4) | "There is no one else to do it instead." | "My parents remind me every day." |
| 3 (đoạn 5) | "how much effort they put into taking care of our home" | "chores can bring a family closer together" |

**Bước 2 — Rule callout** (phải: text quy tắc; trái: giữ nguyên cả 3 cặp cùng sáng màu 1 lúc để học
sinh nhìn tổng quan điểm chung)
> *Notice something? The ✅ sentences always have a specific action or reason. The ❌ sentences just
> introduce the idea — general, no real detail.*
> Câu ✅ luôn có hành động hoặc lý do cụ thể. Câu ❌ chỉ là câu dẫn ý — chung chung, không có chi tiết
> thật.

**Bước 3 — 2-step process** (phải: quy trình 2 bước dạng số; trái: khi tap "Bước 2: Quét đoạn" →
chạy hiệu ứng quét nhẹ — dòng sáng di chuyển từ trên xuống dưới qua đoạn 3-4-5, mô phỏng động tác
scan thật, dừng lại đúng tại 3 câu ✅)
1. Đọc câu hỏi → xác định đang cần tìm loại chi tiết gì (hành động? lý do? con số?)
2. Quét đoạn liên quan → tìm đúng câu có chi tiết đó, bỏ qua câu chỉ dẫn ý chung chung

*Dòng nhỏ thêm cuối Bước 3 (không phải bước riêng, chỉ 1 câu ghi chú nhỏ hơn, màu nhạt hơn 2 bước
trên):*
> 💡 *Với câu hỏi khó hơn, đôi khi bằng chứng nằm ở 2 đoạn khác nhau — vẫn dùng đúng luật này, chỉ
> cần lặp lại 2 lần rồi ghép câu trả lời lại.*

**Bước 4 — Quick check** (phải: câu hỏi tap-to-match; trái: auto-scroll xuống đoạn (6), cả đoạn hiện
rõ, chưa highlight gì cho tới khi học sinh tap — dùng luật đã đổi vì đoạn 6 không có cặp "cụ thể vs
chung chung" rõ như Card 1-3)
> *Read paragraph (6) again. Which sentence gives Vy's overall conclusion, and which is just her
> personal opinion added on top?*

Tap chọn vai trò cho từng câu (tap-to-match, không kéo) — khi tap đúng, câu đó sáng màu tương ứng
ngay trên đoạn (6) bên trái làm feedback trực quan:
- "The benefits of doing housework go far beyond having a clean house." → tap gán ✅ **Kết luận
  chính** → sáng xanh lá bên trái
- "I truly believe every teenager should try it." → tap gán 🗣️ **Ý kiến cá nhân thêm vào** → sáng
  vàng nhạt bên trái

→ Feedback ngắn: *"Same rule — the sentence that sums up real evidence is the main point, not the
sentence that only shares a feeling."*

**Bước 5 — Summary Card** (full-width, không cần Split view nữa — card tổng hợp để "mang theo",
không gắn với đoạn văn cụ thể)
> 📌 **Quick Recap — Spot the Real Evidence**
>
> **Rule:** Hành động/lý do cụ thể = ✅ Evidence · Câu dẫn ý/quan điểm chung chung = ❌ Not evidence
>
> **2 steps:**
> 1️⃣ Đọc câu hỏi → xác định loại chi tiết cần tìm
> 2️⃣ Quét đoạn liên quan → chọn câu có chi tiết đó, bỏ câu chỉ dẫn ý

Nút bên dưới card: **"Got it — let's continue"** (tap để đóng, chuyển tiếp sang đoạn kết + Word
Collection như luồng cũ).
*Nội dung Summary Card này là 1 component/nguồn dữ liệu duy nhất, được tái sử dụng ở Phần 2 —
xem icon 💡 "Recap" trong Practice bên dưới. Sửa nội dung ở đây thì bên Practice tự cập nhật theo,
không viết 2 bản riêng.*

**Bước 6 — Câu chốt nối sang Practice**
> *You'll use this exact skill in Practice — look for "Prove it" and pick the sentence with real
> evidence.*
> Bạn sẽ dùng đúng kỹ năng này ở phần Luyện tập — để ý mục "Prove it" và chọn câu có bằng chứng
> thật.

---

**Kết đoạn** (đoạn 6, hiện sau khi mở khoá đủ 3 Discovery + qua hết Strategy Reveal)
> **(6)** So here is my honest opinion. The **benefits** of doing housework go far beyond having a
> clean house. It also helps build **character**, and I truly believe every teenager should try
> it.
> *(228 words)*

Tap từ **benefit** → popup nghĩa: *An advantage or good result* — lợi ích, điều tốt đẹp mang lại → gap-fill gốc: "The ______ of
doing housework go far beyond having a clean house." → đáp án: *benefits*.
Tap từ **character** → popup nghĩa: *The qualities that make a person who they are* — tính cách, những phẩm chất tạo nên con người → gap-fill
gốc: "It also helps build ______." → đáp án: *character*.

**YOUR WORD COLLECTION** (thu thập đủ 6 từ đã tap qua trong hành trình đọc — đúng 6 cặp
word-definition của Bài 1 Matching gốc, chỉ đổi cách trình bày):
responsibility ✓ · gratitude ✓ · strengthen ✓ · bond ✓ · character ✓ · benefit ✓

**Điều hướng cuối Phần 1:** Link thật sang File Practice (`href="unit1_reading_practice.html"`),
text song ngữ: "✓ Found all the evidence — Go to Practice / Đã tìm đủ evidence — Sang Luyện tập"

---

### PHẦN 2 — PRACTICE (`unit1_reading_practice.html`)

**Practice Reference Pane:** Có — 1 pane không tab (Reading Passage, giữ nguyên đoạn đánh số +
từ khoá bôi đậm, bỏ tương tác Evidence Card của Phần 1, chỉ hiển thị để tra cứu). Pane này **giữ
nguyên xuyên suốt cả Phần 2** — học sinh luôn thấy bài đọc song song lúc làm câu hỏi, theo đúng 3
chế độ xem sẵn có (Chia đôi mặc định / Bài đọc / Câu hỏi, học sinh tự tap đổi chế độ).

**🆕 Text-reveal theo Level (thay cho quyết định cũ "bỏ hẳn tap-hiện-nghĩa" — nới lại có kiểm soát,
chỉ áp dụng ở Practice, KHÔNG áp dụng ở Lesson vì Lesson đã có kịch bản giảng/dịch trực tiếp):**

Tách 2 loại reveal, khác nhau cả về hình thức lẫn hành vi, để học sinh phân biệt được "từ đã học" và
"từ mới chỉ để đỡ vướng":

| | Từ vựng chính thức (6 từ: responsibility, gratitude, strengthen, bond, character, benefit) | Từ khó bổ trợ (4 từ: avoid, practical, reliable, far beyond) |
|---|---|---|
| Kiểu highlight | Vàng đậm, có viền (giữ nguyên style đã dùng ở Phần 1) | Gạch chân chấm, màu xám nhạt |
| Tap → | Popup nghĩa ngắn 1 dòng | Popup nghĩa ngắn 1 dòng |
| Có gap-fill / vào Word Collection? | Không (khác Phần 1 — ở đây chỉ tra cứu lại, không kiểm tra) | Không |

**Bảng bật/tắt theo Level** (đổi tab Level → Reference Pane tự đổi danh sách từ được reveal, dùng
chung 1 pane, KHÔNG tách 3 bản passage riêng):

| Level | 6 từ vựng chính thức | 4 từ khó bổ trợ |
|---|---|---|
| Easy | ✅ Reveal cả 6 | ✅ Reveal cả 4 (avoid, practical, reliable, far beyond) |
| Medium | ❌ Không reveal | ✅ Reveal 2 (reliable, far beyond) |
| Difficult | ❌ Không reveal | ❌ Không reveal |

**🆕 Icon 💡 "Recap" cạnh mỗi câu có Prove-it** — áp dụng cho **cả 3 mức, không chỉ 8 câu T/F +
Y/N/NG**: 4 True/False ở Easy, 4 Yes/No/Not Given ở Medium, **và cả 4 câu Matching Information ở
Difficult** (Difficult là mức học sinh ít lỗi nhất ở Mission, nhưng không có nghĩa Matching
Information dễ hơn T/F — vẫn cần điểm tựa Recap). Icon cố định, nhỏ, đặt cạnh nút Prove-it/nút chọn
đáp án của câu đó. Tap → mở **1 popup/bottom-sheet nhỏ nổi đè lên trên cùng** (overlay, không phải
đổi tab hay đổi chế độ xem của Reference Pane), hiển thị đúng nội dung **Summary Card** (Bước 5,
Strategy Reveal ở Phần 1). **Reference Pane (bài đọc bên trái) vẫn giữ nguyên state phía dưới lớp
overlay** — dù học sinh đang ở chế độ Chia đôi, Bài đọc, hay Câu hỏi lúc tap 💡, tap "Đóng" popup thì
quay lại đúng y chế độ + vị trí scroll đó, không bị đổi layout hay mất tiến trình làm bài. Trên
mobile ≤480px, popup hiện dạng bottom-sheet trượt lên từ dưới (không full-screen), để góc trên vẫn
thấy được đang ở câu nào.
Dùng chung 1 component/nguồn dữ liệu với Summary Card ở Phần 1, không viết nội dung riêng cho popup
này.

**⚠️ 2 ràng buộc kỹ thuật bắt buộc cho popup Recap** (dễ bị hiểu nhầm khi build nên ghi rõ):
1. Mở popup Recap **KHÔNG được gọi `recordMistake()`** — không tính là sai, không bị trừ điểm hay
   ảnh hưởng bất kỳ thống kê nào của học sinh, kể cả khi hệ thống có adaptive routing ở unit khác.
2. Nội dung popup **chỉ nhắc lại Rule + quy trình 2 bước, KHÔNG được thêm ví dụ minh hoạ mới**
   trùng với câu học sinh đang làm — tránh biến Recap thành gợi ý đáp án trá hình.

**Bài tập — Easy**

- level: easy | cat: nhan_biet
  statement: "Vy says most teenagers enjoy doing housework."
  dap_an_dung: false
  giai_thich_dung: Đối lập trực tiếp với câu mở đầu đoạn 1.
  prove: chọn câu chứng minh — ✅ "I know many people don't enjoy doing the dishes or the
    laundry." | ❌ "Here are three things I've learned from doing housework."

- level: easy | cat: thong_hieu
  statement: "According to paragraph 3, the practical skills Vy mentions, such as cooking and
    cleaning, are not taught in class."
  dap_an_dung: true
  giai_thich_dung: Diễn giải lại "No one teaches you... in class" (đoạn 3) — phạm vi câu hỏi đã
    thu hẹp đúng với những gì đoạn 3 thực sự nói.
  prove: ✅ "No one teaches you how to cook a simple meal or keep a room clean in class." | ❌
    "This makes me more careful and reliable, not only at home but in other parts of my life too."

- level: easy | cat: nhan_biet
  statement: "Vy believes chores help her become more responsible."
  dap_an_dung: true
  giai_thich_dung: Trực tiếp từ đoạn 4.
  prove: ✅ "chores help me build responsibility" | ❌ "helping them shows me how much effort they
    put into taking care of our home"

- level: easy | cat: thong_hieu
  statement: "Doing chores with her family only creates extra work for Vy, with no emotional
    benefit."
  dap_an_dung: false
  giai_thich_dung: Đoạn 5 phủ định điều này (gratitude, bond được nhắc tới).
  prove: ✅ "This gives me a lot of gratitude for them." | ❌ "First, it teaches me practical
    skills for real life."

- level: easy | cat: nhan_biet | dạng: MCQ
  question: "According to Vy, how does she learn practical skills?"
  options: A. By watching videos online | B. By asking her teacher | C. By doing them at home
    again and again | D. By reading books about housework
  dap_an_dung: C
  giai_thich_dung: Trực tiếp từ đoạn 3.

- level: easy | cat: nhan_biet | dạng: MCQ
  question: "What happens when a task belongs only to Vy?"
  options: A. Her parents always help her finish it | B. There is no one else to do it instead |
    C. She can ask her friends to do it | D. She usually forgets about it
  dap_an_dung: B
  giai_thich_dung: Trực tiếp từ đoạn 4.

- level: easy | cat: thong_hieu | dạng: MCQ
  question: "According to the passage, which of the three things did Vy find the most
    surprising?"
  options: A. That chores can bring a family closer together | B. That her parents do not work
    hard | C. That chores are easy to finish | D. That cooking is difficult to learn
  dap_an_dung: A
  giai_thich_dung: Đoạn 5 nêu rõ "this surprised me the most", cần liên kết với chi tiết cụ thể
    phía sau.

- level: easy | cat: van_dung | dạng: MCQ
  question: "Based on paragraphs 3 and 6, what does Vy learn from housework besides practical
    skills?"
  options: A. How to cook more difficult meals | B. Something that helps shape her character |
    C. A reason to stop doing chores once she is skilled | D. A way to avoid helping her parents
  dap_an_dung: B
  giai_thich_dung: Kết hợp thông tin từ đoạn 3 (kỹ năng thực hành) và đoạn 6 (xây dựng tính cách) —
    cùng dạng "kết hợp 2 đoạn" với các câu Vận dụng khác trong bộ này, thay cho câu áp dụng tình
    huống mới không có trong bài (đã gỡ vì lệch phạm vi Stated Details).

- level: easy | cat: nhan_biet | dạng: gap-fill
  question: "Chores help Vy build ______."
  dap_an_dung: responsibility
  giai_thich_dung: Lấy trực tiếp từ đoạn 4.

- level: easy | cat: nhan_biet | dạng: gap-fill
  question: "Helping them shows me their effort — this gives me a lot of ______ for them."
  dap_an_dung: gratitude
  giai_thich_dung: Lấy trực tiếp từ đoạn 5.

- level: easy | cat: thong_hieu | dạng: gap-fill
  question: "Working on tasks with family, rather than just talking, tends to make the family
    feel more ______."
  dap_an_dung: connected
  giai_thich_dung: Cần diễn giải lại ý "strengthen the bond... in a way that just talking does
    not" — từ "connected" không xuất hiện nguyên văn.

- level: easy | cat: van_dung | dạng: gap-fill
  question: "Summarising the whole post, doing housework can benefit a teenager's skills,
    relationships, and ______."
  dap_an_dung: character
  giai_thich_dung: Cần tổng hợp cả 3 điều được nhắc đến xuyên suốt bài (đoạn 3, 5, 6).

**Bài tập — Medium**

- level: medium | cat: thong_hieu
  statement: "Vy has always enjoyed doing housework."
  dap_an_dung: NO
  giai_thich_dung: Đoạn 1 — cô "đã bắt đầu" nhìn nhận khác đi, ngụ ý trước đó không thích.
  prove: ✅ "But I've started to see chores in a different way." | ❌ "Here are three things I've
    learned from doing housework."

- level: medium | cat: nhan_biet
  statement: "Vy has brothers or sisters."
  dap_an_dung: NOT GIVEN
  giai_thich_dung: Bài không hề nhắc đến anh chị em của Vy.
  prove: ✅ "There is no evidence in the text." | ❌ "My parents work hard every day, and helping
    them shows me how much effort they put into taking care of our home."

- level: medium | cat: nhan_biet
  statement: "Being responsible for a task makes a person more reliable in other areas of life
    too, according to Vy."
  dap_an_dung: YES
  giai_thich_dung: Đoạn 4 — "not only at home but in other parts of my life too."
  prove: ✅ "not only at home but in other parts of my life too" | ❌ "chores can bring a family
    closer together"

- level: medium | cat: thong_hieu
  statement: "Vy thinks doing chores is a waste of time."
  dap_an_dung: NO
  giai_thich_dung: Ngược lại — giọng văn tích cực xuyên suốt cả bài, không có câu phủ định trực
    tiếp nào.
  prove: ✅ "I truly believe every teenager should try it." | ❌ "No one teaches you how to cook a
    simple meal or keep a room clean in class."

- level: medium | cat: nhan_biet | dạng: MCQ
  question: "According to paragraph 3, how does Vy learn practical skills like cooking?"
  options: A. By taking classes at school | B. By watching videos online | C. By doing them at
    home again and again | D. By asking her parents to explain each step
  dap_an_dung: C
  giai_thich_dung: Trực tiếp từ đoạn 3 — "you learn these things by doing them at home, again and
    again."

- level: medium | cat: thong_hieu | dạng: MCQ
  question: "What does the phrase 'there is no one else to do it instead' suggest about Vy's
    chores?"
  options: A. Vy's parents complete the chores for her | B. Vy is the only person responsible for
    that task | C. Vy can ask her friends to help | D. Vy often forgets to do the task
  dap_an_dung: B
  giai_thich_dung: Diễn giải ý đoạn 4 — không có ai khác làm thay.

- level: medium | cat: thong_hieu | dạng: MCQ
  question: "Why does helping her parents give Vy a feeling of gratitude?"
  options: A. Because her parents pay her for the housework | B. Because her parents praise her
    every day | C. Because she no longer has to do chores alone | D. Because she realises how
    much effort they put into the home
  dap_an_dung: D
  giai_thich_dung: Suy luận nguyên nhân-kết quả từ đoạn 5.

- level: medium | cat: van_dung | dạng: MCQ
  question: "Which sentence best combines TWO benefits of housework that Vy mentions in the
    post?"
  options: A. Chores teach useful skills and help her feel closer to her family | B. Chores are
    required by parents and take a lot of free time | C. Chores are boring but keep the house
    clean | D. Chores replace the need to study at school
  dap_an_dung: A
  giai_thich_dung: Kết hợp thông tin từ đoạn 3 (kỹ năng thực hành) và đoạn 5 (gắn kết gia đình).

- level: medium | cat: nhan_biet | dạng: summary-completion (word box: practical skills · careful
  and reliable · connected · character · hard-working · popular)
  question: "Vy shares three things she has learned from doing housework. First, doing housework
    teaches her (9)______ that she cannot learn in the classroom."
  dap_an_dung: practical skills
  giai_thich_dung: Gần nguyên văn đoạn 3.

- level: medium | cat: nhan_biet | dạng: summary-completion
  question: "Second, having a task of her own makes her more (10)______, since there is no one
    else to rely on."
  dap_an_dung: careful and reliable
  giai_thich_dung: Gần nguyên văn đoạn 4.

- level: medium | cat: thong_hieu | dạng: summary-completion
  question: "Third, helping with chores at home fills her with gratitude and makes the family
    feel more (11)______ than talking alone can."
  dap_an_dung: connected
  giai_thich_dung: Diễn giải "strengthen the bond... in a way that just talking does not" (đoạn
    5) — từ "connected" không xuất hiện nguyên văn.

- level: medium | cat: van_dung | dạng: summary-completion
  question: "Overall, Vy believes housework brings more than a clean house — it also helps build
    a teenager's (12)______."
  dap_an_dung: character
  giai_thich_dung: Cần tổng hợp cả 3 điều xuyên suốt bài (đoạn 3, 4, 5).

**Bài tập — Difficult**

- level: difficult | cat: nhan_biet | dạng: Matching Information (tap Evidence Card → tap
  Paragraph, KHÔNG kéo-thả)
  question: "A mention of a chore that many teenagers dislike doing"
  dap_an_dung: Paragraph 1
  giai_thich_dung: Đoạn (1) nhắc đến việc nhiều người không thích rửa bát/giặt đồ.

- level: difficult | cat: nhan_biet | dạng: Matching Information
  question: "A skill gained only through repeated practice at home, not through lessons"
  dap_an_dung: Paragraph 3
  giai_thich_dung: Đoạn (3) — "again and again... No one teaches you... in class".

- level: difficult | cat: nhan_biet | dạng: Matching Information
  question: "A comparison suggesting that working together builds a stronger connection than
    conversation alone"
  dap_an_dung: Paragraph 5
  giai_thich_dung: Đoạn (5) — "in a way that just talking does not".

- level: difficult | cat: nhan_biet | dạng: Matching Information
  question: "A claim that the value of housework is not limited to having a tidy home"
  dap_an_dung: Paragraph 6
  giai_thich_dung: Đoạn (6) — "goes far beyond having a clean house".

- level: difficult | cat: thong_hieu | dạng: Short Answer (NO MORE THAN SIX WORDS)
  question: "According to paragraph 3, what is true about the practical skills Vy mentions in
    relation to school lessons?"
  dap_an_dung: not taught in class
  giai_thich_dung: Suy luận từ "No one teaches you... in class" (đoạn 3).

- level: difficult | cat: thong_hieu | dạng: Short Answer
  question: "Why does Vy feel more careful and reliable when a task belongs only to her?"
  dap_an_dung: there is no one else (to rely on)
  giai_thich_dung: Suy luận nguyên nhân từ đoạn 4.

- level: difficult | cat: van_dung | dạng: Short Answer
  question: "Apart from bringing the family closer together, what TWO other benefits of housework
    does Vy mention in the post?"
  dap_an_dung: practical skills and character
  giai_thich_dung: Kết hợp thông tin từ đoạn 3 và đoạn 6 — loại trừ đoạn 5 đã nêu sẵn trong câu
    hỏi.

- level: difficult | cat: van_dung | dạng: Short Answer
  question: "According to the whole post, in what TWO ways does housework affect Vy's life
    besides teaching her useful skills?"
  dap_an_dung: responsibility and family bond
  giai_thich_dung: Kết hợp thông tin từ đoạn 4 và đoạn 5 — loại trừ đoạn 3 đã nêu sẵn trong câu
    hỏi.

- level: difficult | cat: thong_hieu | dạng: Sentence Completion
  question: "Because there is no one to share the task with, Vy learns to depend more on
    ______."
  dap_an_dung: herself
  giai_thich_dung: Suy luận từ "there is no one else to do it instead" (đoạn 4).

- level: difficult | cat: thong_hieu | dạng: Sentence Completion
  question: "Vy realises how much time and effort her parents give to the family by ______ them
    with housework."
  dap_an_dung: helping
  giai_thich_dung: Khái quát từ đoạn 5.

- level: difficult | cat: thong_hieu | dạng: Sentence Completion
  question: "Vy believes that working on shared tasks builds a stronger bond than ______ alone
    can."
  dap_an_dung: talking
  giai_thich_dung: Cấu trúc so sánh trong đoạn 5.

- level: difficult | cat: van_dung | dạng: Sentence Completion
  question: "Besides bringing the family closer together, Vy believes housework also helps shape
    a teenager's ______."
  dap_an_dung: character
  giai_thich_dung: Câu hỏi đã loại trừ sẵn "gắn kết gia đình" (đoạn 5) — học sinh phải kết hợp
    đoạn 3 và đoạn 6 mới ra đáp án.

**Back to You** (Closing — quay lại prediction ở Hook Stage 0, không phải bài chấm điểm)
Hiện lại lựa chọn ban đầu của học sinh ("What do you actually get from doing chores?") cạnh bản đồ
tự xây: 🧹 HOUSEWORK → 🍳 Practical skills / 🎯 Responsibility / ❤️ Family bond → 🌱 Character.
Hỏi: **Did Vy change your mind?** (tap chọn) `Yes` / `A little` / `No`
Rồi: **Choose ONE piece of evidence that best supports your answer.** — tap chọn 1 câu bất kỳ
trong 6 câu evidence đã unlock ở Phần 1 (không chấm đúng/sai, chỉ yêu cầu chọn evidence để kết
thúc bằng 1 hành động phản tư có căn cứ).

**Self-assessment:**
1. I can recognise and read 6 key words about family life
2. I understand the meaning of each word through the blog post
3. I can identify specific information in the text (True/False, Yes/No/Not Given, Matching
   Information)
4. I can complete a summary/sentence using specific information from the text

---

### ⚠️ Lưu ý thiết kế (bắt buộc đọc trước khi build)
- Mobile-first: test ≤480px trước, Reference Pane đủ 3 chế độ xem (Chia đôi/Bài đọc/Câu hỏi).
- File Practice KHÔNG hero, không lặp tiêu đề Unit.
- **🆕 Mọi popup nghĩa từ vựng (cả từ vựng chính thức lẫn từ khó bổ trợ) PHẢI có thêm nghĩa tiếng
  Việt ngắn bên dưới định nghĩa tiếng Anh** — không chỉ hiện định nghĩa Anh-Anh, để hỗ trợ học sinh
  học yếu hơn. Áp dụng cho toàn bộ popup trong cả Phần 1 và Phần 2, không riêng 1-2 từ.
- **🆕 Mọi tương tác tap-to-select/tap-to-classify/causal chain PHẢI có 1 dòng hướng dẫn hiện
  on-screen cho học sinh** (song ngữ, giống style "Before leaving for school, spot something you
  could change." ở Unit 2 Stage 1) — không được để chỉ có ghi chú kỹ thuật trong ngoặc (VD: "tap
  không kéo") mà không có câu hướng dẫn thật hiện ra cho học sinh biết phải làm gì tiếp theo.
- **KHÔNG dùng kéo-thả ở đâu cả** — mọi chỗ trong bản đề xuất gốc có "kéo/drag" (causal chain Card
  2, Evidence Board Difficult) đã được viết lại thành tap-to-select ở kịch bản này; khi build giữ
  đúng cơ chế tap, không tự đổi lại thành drag vì "trông đẹp hơn".
- Prove-it chỉ áp dụng cho 8 câu (4 True/False ở Easy + 4 Yes/No/Not Given ở Medium) — các câu MCQ/
  gap-fill/Short Answer/Summary/Sentence Completion khác giữ nguyên cơ chế chấm trực tiếp + giải
  thích như bản gốc, KHÔNG thêm bước Prove-it cho chúng.
- Vị trí đáp án đúng trong mọi MCQ/Matching phải xáo ngẫu nhiên khi render (dùng `shuffleMCQOptions()`
  chung của hệ thống), không giữ thứ tự A/B/C/D như liệt kê ở trên (thứ tự trên chỉ để giáo viên
  đối chiếu, không phải thứ tự render).
- Đồng bộ dữ liệu: nội dung passage/vocab phải giống hệt ở cả 2 file (đánh dấu comment "ĐỒNG BỘ").
- **🆕 Popup 💡 Recap (Phần 2) PHẢI là overlay nổi, KHÔNG được thay thế/che khuất Reference Pane** —
  học sinh vẫn cần đọc song song bài đọc bên trái lúc làm câu hỏi bên phải xuyên suốt Phần 2; popup
  chỉ mở tạm lớp trên cùng rồi đóng lại về đúng state cũ, không đổi chế độ xem hay cuộn lại pane bài
  đọc về đầu.
- **🆕 Text-reveal ở Practice CHỈ áp dụng trong Reference Pane của Phần 2, KHÔNG thêm vào Phần 1
  (Lesson)** — ở Lesson đã có kịch bản giảng/dịch trực tiếp nên không cần chữ reveal; thêm vào sẽ làm
  loãng phần dạy kỹ năng Strategy Reveal. Số lượng từ reveal PHẢI đổi theo Level đang active (Easy 10
  từ / Medium 2 từ / Difficult 0 từ — xem bảng chi tiết ở mục Practice Reference Pane), không hiện cố
  định 1 danh sách cho cả 3 mức.
- KHÔNG dùng adaptive routing (tự chọn Easy/Medium/Difficult theo performance) cho bài này — học
  sinh vẫn chọn tường minh qua Level Tabs như thiết kế gốc; ý tưởng adaptive được gác lại làm đề
  xuất nâng cấp hệ thống riêng, không áp vào bài Unit 1 Reading này.

### Ghi chú cho Giai đoạn 2 (Design)
- Đọc `02_design_tiengAnh.md` mục: 4.10 (Reading Passage), 4.11 (Comprehension 3 mức), 4.8b
  (Reference Pane, ref = passage, 1 pane không tab), 4.7 (Self-assessment).
- Đọc `03_engine_tiengAnh_v1_2.md` mục: 1.6 (Prediction Picker — Hook Stage 0/1 và Back to You),
  1.7 (progressive reveal, áp dụng cho đoạn văn thay vì hội thoại), 1.8 (tap-to-select-in-sentence
  — dùng cho "tìm câu chứa evidence" ở Benefit Hunt và causal chain Card 2), 1.1/1.2 (click-reveal —
  vocab-in-context).
- Evidence Board (Difficult, Matching Information) và Prove-it (8 câu T-F/YNNG) là biến thể mới
  của component match/MCQ có sẵn — không có pattern riêng trong `03_engine` hiện tại, cần build
  thêm 1 hàm nhỏ "tap-select-pair" (Evidence Card ↔ Paragraph) và 1 UI 2 bước (Answer → Prove it)
  khi lên code, dựa trên cơ chế click/tap chuẩn đã có, không phải viết engine hoàn toàn mới.
- **🆕 Bổ sung mục 1.10 — Strategy Reveal** vào `03_engine_tiengAnh_v1_2.md`: khối worked-example
  recap + rule callout + quick check + Summary Card, gắn với Reference Pane (4.8b) qua 1 hàm mới
  `scrollToAndHighlight(paragraphId, sentenceIndex, color)` gọi mỗi khi đổi bước bên phải — tái
  dùng khung Reference Pane làm layout, không viết lại từ đầu.
- **🆕 Icon 💡 Recap (Phần 2):** popup nhỏ mở đúng nội dung Summary Card (1.10) từ 1 nguồn dữ liệu
  chung với Phần 1 — không phải component riêng, chỉ là 1 cách hiển thị khác của cùng 1 data.
- **🆕 Text-reveal theo Level (Reference Pane, Phần 2):** Reference Pane cần đọc `currentLevelTab`
  để quyết định render reveal-tag cho từ nào, cấu trúc data đề xuất (đã thêm field `vi` — nghĩa
  tiếng Việt, bắt buộc cho mọi popup theo lưu ý thiết kế ở trên):
  ```javascript
  const revealWords = {
    easy: [
      {word: 'responsibility', en: 'A duty to deal with or take care of something',
       vi: 'trách nhiệm, bổn phận phải lo liệu việc gì đó', type: 'core'},
      // ... 5 từ core còn lại + 4 từ support (avoid, practical, reliable, far beyond),
      // mỗi từ đều có đủ 3 field: en, vi, type
    ],
    medium: [ /* chỉ 2 từ support: reliable, far beyond */ ],
    difficult: []
  };
  ```
  Không viết 3 component Reference Pane riêng — chỉ 1 pane, render tag theo mảng tương ứng
  `currentLevelTab`. 2 style khác nhau (vàng đậm cho 6 từ chính thức / gạch chấm xám cho 4 từ bổ
  trợ) phân biệt bằng field `type: 'core' | 'support'` trong cùng cấu trúc data trên, không phải
  2 hệ thống tag tách biệt. Field `vi` áp dụng đồng nhất cho MỌI popup nghĩa trong cả file — kể cả
  popup ở Phần 1 (Lesson) cũng cần field này, không chỉ riêng Text-reveal ở Phần 2.

**⚠️ Engine chưa có pattern cho Ảnh Hook full-screen + fade-out** (đã kiểm tra `03_engine_tiengAnh_v1_2.md`
toàn file — chỉ có `fadeUp` cho chat bubble ở mục 1.7, KHÔNG có pattern cho ảnh full-screen chuyển
cảnh như mô tả ở Module 1A). Đây là phần thật sự cần thêm code mới trước khi build được đúng hiệu
ứng "ảnh full-screen → tap hoặc chờ 400ms → fade-out → vào Hero". Đề xuất bổ sung 1 mục mới vào
`03_engine_tiengAnh_v1_2.md`, ví dụ **PHẦN 1.9 — Full-screen Hook Image + Fade Transition**:

```javascript
// HTML: 1 lớp phủ full-screen đè lên toàn bộ nội dung bài học, z-index cao nhất
// <div id="hook-overlay" class="hook-overlay" onclick="dismissHook()">
//   <img src="unit1_reading_hook_chore_dilemma.png" alt="">
//   <p class="hook-caption">Sound familiar? / Bạn thấy quen không?</p>
// </div>

function initHook() {
  setTimeout(dismissHook, 400); // tự fade sau 400ms nếu học sinh không tap
}
function dismissHook() {
  const overlay = document.getElementById('hook-overlay');
  if (!overlay || overlay.classList.contains('hidden')) return; // tránh gọi 2 lần
  overlay.classList.add('fade-out');
  overlay.addEventListener('transitionend', () => overlay.remove(), { once: true });
}
```
```css
.hook-overlay {
  position: fixed; inset: 0; z-index: 9999;
  display: flex; align-items: center; justify-content: center;
  background: var(--cream); cursor: pointer;
  transition: opacity .4s ease;
}
.hook-overlay img { width: 100%; height: 100%; object-fit: cover; }
.hook-overlay .hook-caption {
  position: absolute; bottom: 24px; right: 24px;
  color: #fff; font-weight: 600; text-shadow: 0 1px 6px rgba(0,0,0,.4);
}
.hook-overlay.fade-out { opacity: 0; pointer-events: none; }
```
Lưu ý khi build: 400ms trong mô tả Module 1A là thời gian fade-out (transition), KHÔNG phải thời
gian chờ trước khi fade — ở bài Reading này mình để 400ms là thời gian CHỜ trước khi tự fade (vì
không có lời thoại robot cần đọc), transition CSS riêng có thể ngắn hơn (~300ms) để cảm giác
nhanh, dứt khoát. Test kỹ trên mobile ≤480px: ảnh phải `object-fit: cover` để không méo tỉ lệ trên
màn hình dọc.

---
**Kịch bản đã sẵn sàng! Bạn muốn:**
- ✅ **Duyệt** — chuyển sang `02_design_tiengAnh.md` để build
- ✏️ **Chỉnh** — nói rõ phần nào cần thay đổi