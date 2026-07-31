## Kịch bản: Pronunciation — Unit 1 — /br/, /kr/, /tr/

**Nguồn:** `Unit_1_Pronunciation_NB_TH_VD.docx`

**Xác nhận:** Không có nội dung học thuật gốc nào bị sửa — chỉ lược bỏ nhãn `[NB]/[TH]/[VD]`, dòng
tỉ lệ %, ghi chú "*Phiên bản đã chữa...*", và bảng "BẢNG TỔNG HỢP TỈ LỆ..." ở cuối (toàn bộ đều là
ghi chú nội bộ giáo viên — theo Quy tắc mới 1, mục 3, ở `01_scenario_builder_tiengAnh_v2_1.md`).

**Ngoại lệ áp dụng:** KHÔNG dùng Practice Reference Pane (Ngoại lệ 2, Quy tắc mới 2) — mỗi mức
Practice giới thiệu bộ từ mới để luyện nghe/nhận diện, không lặp lại đúng 12 từ ở Phần 1.

---

### PHẦN 1 — LESSON (`Unit_1_Pronunciation_lesson.html`)

**Hero:** Unit 1 · Pronunciation · /br/, /kr/, /tr/ — Objective: Recognise and pronounce the
consonant blends /br/, /kr/, and /tr/ correctly.

**Quy tắc phát âm (nguyên văn từ Word):**

> 🔊 **/br/** — Môi khép nhẹ cho âm /b/ → bật hơi ra → chuyển ngay sang /r/ (đầu lưỡi cong nhẹ lên,
> không chạm vòm miệng). Không dừng giữa hai âm, phát liền một hơi.
> Ví dụ: bread, brave, bridge — Thực hành: /b/ → /br/ → /breɪd/
>
> 🔊 **/kr/** — Phần sau lưỡi nâng lên chạm vòm miệng mềm cho âm /k/ → bật hơi ra → chuyển ngay
> sang /r/ (đầu lưỡi cong nhẹ lên, không chạm vòm miệng). Giữ luồng hơi thoát ra liên tục, không
> tách rời hai âm. Ví dụ: crab, cream, cry — Thực hành: /k/ → /kr/ → /kraɪ/
>
> 🔊 **/tr/** — Đầu lưỡi chạm nhẹ vào vòm miệng trên (ngay sau răng cửa) cho âm /t/ → bật hơi ra →
> chuyển ngay sang /r/ (đầu lưỡi cong nhẹ lên). Không phát âm /t/ và /r/ tách biệt như hai âm riêng
> lẻ. Ví dụ: tree, truck, trip — Thực hành: /t/ → /tr/ → /triː/

**Từ minh hoạ (bảng 3 cột, mỗi từ có nút 🔊 phát âm mẫu qua `speak()` — PHẦN 4.2 `03_engine_tiengAnh.md`):**

| /br/ | /kr/ | /tr/ |
|---|---|---|
| bread /bred/ | crab /kræb/ | tree /triː/ |
| brave /breɪv/ | cream /kriːm/ | truck /trʌk/ |
| bridge /brɪdʒ/ | cry /kraɪ/ | trip /trɪp/ |
| branch /brɑːntʃ/ | crowd /kraʊd/ | treasure /ˈtreʒ.ər/ |

**Read Aloud (component 9.4 — `02_design_tiengAnh.md`):** Nghe và lặp lại từng từ trong bảng
trên. Ghi âm và nộp cho AI chấm.

**Điều hướng cuối Phần 1:** Link thật sang File Practice — "✓ Done practising sounds — Go to
Practice / Đã luyện xong — Sang Luyện tập" (`href="Unit_1_Pronunciation_practice.html"`).

---

### PHẦN 2 — PRACTICE (`Unit_1_Pronunciation_practice.html`)

**Không có Practice Reference Pane** (xem Ngoại lệ ở đầu file) — dùng thẳng Level Tabs (4.5) +
`practiceHost` như cấu trúc gốc, không thêm dual-pane.

**Bài tập (đã lọc sạch — chỉ payload, không nhãn `[NB]/[TH]/[VD]`, không dòng tỉ lệ %):**

#### Mức Easy

**Listen-and-Circle** *(dùng `playPromptWord()` — PHẦN 4.2 `03_engine_tiengAnh.md` — phát đúng 1
từ mục tiêu, học sinh chọn từ nghe được; cho nghe lại không giới hạn)*:
1. Target word phát ra: **bread** — Options: A. bread / B. bed / C. head
   `dap_an_dung`: A — `giai_thich_dung`: Từ gây nhiễu (bed, head) khác âm đầu rõ ràng so với /br/.
2. Target word phát ra: **crab** — Options: A. crab / B. cab / C. lab
   `dap_an_dung`: A — `giai_thich_dung`: Từ gây nhiễu (cab, lab) không có cụm phụ âm /kr/, dễ phân biệt.
3. Target word phát ra: **truck** — Options: A. truck / B. duck / C. luck
   `dap_an_dung`: A — `giai_thich_dung`: Từ gây nhiễu (duck, luck) khác âm đầu rõ ràng so với /tr/.
4. Target word phát ra: **brave** — Options: A. brave / B. wave / C. grave
   `dap_an_dung`: A — `giai_thich_dung`: Từ gây nhiễu (wave, grave) vần giống nhưng khác âm đầu — cần nghe kỹ cụm /br/.
5. Target word phát ra: **cream** — Options: A. cream / B. dream / C. scream
   `dap_an_dung`: A — `giai_thich_dung`: Từ gây nhiễu (dream, scream) có phụ âm gần giống /kr/ hơn, cần phân biệt tinh hơn.
6. Target word phát ra: **tree** — Options: A. tree / B. free / C. three
   `dap_an_dung`: A — `giai_thich_dung`: Từ gây nhiễu (free, three) đều có âm /r/ ở cuối cụm phụ âm — bộ ba dễ nhầm nhất giữa /tr/, /fr/, /θr/.

**Nhận diện khác biệt phát âm — Minimal pairs nâng cao** *(dùng `playPromptWord()` — phát đúng 1
từ mục tiêu, giống Listen-and-Circle Nhận biết ở trên, nhưng distractor gần âm hơn nên đòi hỏi phân
biệt tinh hơn; cho nghe lại không giới hạn. KHÔNG làm "thuần suy luận qua chữ, không audio" như bản
cũ — cách đó buộc phải chọn 1 trong 2 lỗi: hoặc giấu âm mục tiêu (mù mờ, học sinh không có căn cứ
để chọn), hoặc nêu tên âm mục tiêu ngay trong đề (lộ đáp án qua chữ cái đầu, vì chỉ đúng 1 lựa chọn
được viết bằng đúng 2 chữ cái đó — học sinh đoán qua mặt chữ, không cần nghe/hiểu gì cả). Có audio
thì đáp án đến từ việc NGHE, giải quyết được cả hai lỗi cùng lúc.)*:
1. Target word phát ra: **tree** — Options: A. tree / B. three / C. free
   `dap_an_dung`: A — `giai_thich_dung`: "Three" (/θr/) và "free" (/fr/) là âm dễ lẫn nhất với /tr/ vì cùng vần "-ee", cần phân biệt điểm chạm lưỡi khi nghe.
2. Target word phát ra: **crowd** — Options: A. crowd / B. cloud / C. proud
   `dap_an_dung`: A — `giai_thich_dung`: "Cloud" (/kl/) rất gần /kr/ vì cùng bắt đầu bằng "c", chỉ khác âm thứ 2 — cần nghe kỹ.
3. Target word phát ra: **bread** — Options: A. bread / B. dread / C. thread
   `dap_an_dung`: A — `giai_thich_dung`: "Dread" (/dr/) và "thread" (/θr/) cùng vần "-read" với "bread" nhưng khác hẳn âm đầu.
4. Target word phát ra: **truck** — Options: A. truck / B. drum / C. thumb
   `dap_an_dung`: A — `giai_thich_dung`: "Drum" (/dr/) dễ nhầm với /tr/ vì cùng nhóm phụ âm + r; "thumb" không có blend, cần nhận ra sự vắng mặt hoàn toàn của /r/.

**Read Aloud — Short Phrases** *(component 9.4, ghi âm nộp AI chấm)*:
1. a brave crab
2. fresh bread and cream
3. a quick trip

#### Mức Medium

**Listen-and-Circle / Matching âm–từ**:
1. Target word phát ra: **brick** — Options: A. brick / B. trick / C. click
   `dap_an_dung`: A — `giai_thich_dung`: "Trick" (/tr/) và "click" (/kl/) đều có cụm phụ âm nhưng khác hẳn /br/.
2. Target word phát ra: **crown** — Options: A. crown / B. clown / C. brown
   `dap_an_dung`: A — `giai_thich_dung`: "Clown" (/kl/) dễ nhầm với /kr/ nhất trong 3 lựa chọn vì cùng bắt đầu bằng "c".
3. Target word phát ra: **trail** — Options: A. trail / B. rail / C. tail
   `dap_an_dung`: A — `giai_thich_dung`: "Rail" và "tail" không có cụm phụ âm — cần nhận diện sự có mặt của /t/ trước /r/.
4. Target word phát ra: **bright** — Options: A. bright / B. fright / C. light
   `dap_an_dung`: A — `giai_thich_dung`: "Fright" (/fr/) rất gần /br/ về vị trí cấu âm nhưng khác âm đầu.

**Nhận diện khác biệt phát âm** *(Identify the word whose underlined part is pronounced
differently — không cần audio)*:
1. Options: A. chrome / B. chair / C. cheese / D. chicken
   `dap_an_dung`: A — `giai_thich_dung`: "Chrome" phát âm là /kroʊm/ (âm /k/, có blend /kr/), khác với B/C/D đều là /tʃ/ — bẫy chính tả kinh điển của "ch".
2. Options: A. character / B. change / C. cherry / D. teacher
   `dap_an_dung`: A — `giai_thich_dung`: Tương tự, "character" phát âm /k/ dù viết "ch", còn lại đều /tʃ/.
3. Options: A. wrist / B. trust / C. truck / D. trip
   `dap_an_dung`: A — `giai_thich_dung`: "Wrist" có "w" câm, không tạo blend /tr/, trong khi B/C/D đều có /tr/ rõ.
4. Options: A. bring / B. ring / C. cling / D. sing
   `dap_an_dung`: A — `giai_thich_dung`: "Bring" là từ duy nhất có cụm /br/ ở đầu; B/C/D chỉ có 1 phụ âm đơn trước vần "-ing".

**Read Aloud — Full Sentences**:
1. The brave crab crawled across the sandy beach.
2. A big crowd gathered to watch the truck race.
3. She took a quick trip to visit her grandmother.

#### Mức Difficult

**Odd One Out** *(không cần audio, 4 lựa chọn — 3 từ cùng nhóm, 1 từ khác)*:
1. Options: A. crab / B. crowd / C. cloud / D. cream
   `dap_an_dung`: C (cloud = /kl/) — `giai_thich_dung`: "Crab", "crowd", "cream" đều có cụm /kr/; riêng "cloud" là /kl/ (âm thứ 2 là /l/, không phải /r/) — dễ nhầm vì cùng bắt đầu bằng chữ "c" như 3 từ còn lại.
2. Options: A. tree / B. trip / C. truck / D. three
   `dap_an_dung`: D (three = /θr/) — `giai_thich_dung`: "Tree", "trip", "truck" đều có cụm /tr/; riêng "three" là /θr/ (âm đầu /θ/, không phải /t/) — cặp tối thiểu kinh điển dễ gây nhầm lẫn khi đọc.
3. Options: A. bring / B. brave / C. bridge / D. drive
   `dap_an_dung`: D (drive = /dr/) — `giai_thich_dung`: "Bring", "brave", "bridge" đều có cụm /br/; riêng "drive" là /dr/ (âm đầu /d/, không phải /b/) — cần nghe kỹ âm mở đầu vì vị trí cấu âm khá gần nhau.

**Nhận diện khác biệt phát âm — có câu bẫy**:
1. Options: A. chrome / B. crowd / C. character / D. crayon
   `dap_an_dung`: C — `giai_thich_dung`: "Character" là từ duy nhất KHÔNG có blend /kr/ dù viết bằng "cr" giống các từ khác về mặt hình ảnh chữ.
2. Options: A. wrist / B. train / C. trail / D. truck
   `dap_an_dung`: A — `giai_thich_dung`: "Wrist" có "w" câm, hoàn toàn không có âm /r/ nối với /t/.
3. Options: A. bring / B. brave / C. lamb / D. bridge
   `dap_an_dung`: C — `giai_thich_dung`: "Lamb" có "b" câm ở cuối, không liên quan blend /br/ ở đầu từ như 3 từ còn lại — câu bẫy dễ nhầm vì cùng chứa chữ "b".
4. Options: A. crab / B. climb / C. cream / D. cry
   `dap_an_dung`: B — `giai_thich_dung`: "Climb" chứa cụm /kl/ (không phải /kr/) và có "b" câm ở cuối — hai lớp bẫy trong 1 từ.
5. Options: A. tree / B. three / C. trip / D. truck
   `dap_an_dung`: B — `giai_thich_dung`: "Three" lặp lại kiểu bẫy /θr/ vs /tr/ nhưng đặt cạnh nhiều từ /tr/ hơn để tăng độ khó nhận diện.

**Read Aloud — Short Passage (~63 từ, 1 bài duy nhất thay vì nhiều câu rời):**

> Last weekend, my brother and I took a trip to the countryside. We saw a huge crowd gathered near
> an old bridge, watching a group of workers repair a broken truck. My brother bravely offered to
> help carry some bread and cream for the tired workers. By the time we left, everyone was
> smiling, and the crew thanked us warmly for our kindness.

**Self-assessment (giữ nguyên, dán từ Word):**
1. I can recognise the difference between the blends /br/, /kr/, and /tr/ when listening.
2. I can pronounce words, phrases, sentences, or short passages containing /br/, /kr/, and /tr/ clearly.

---

### ⚠️ Lưu ý thiết kế (bắt buộc đọc trước khi build)
- Mobile-first: test ≤480px trước.
- File Practice KHÔNG hero, không lặp tiêu đề Unit.
- KHÔNG có Reference Pane — không cần đồng bộ dữ liệu Phần 1 ↔ Phần 2 (khác Getting Started/Vocab/Reading).
- Nút 🔊 Listen-and-Circle: disable khi đang phát, cho nghe lại không giới hạn số lần (khác giới hạn thử của MCQ chấm điểm thường — vẫn giữ nguyên tắc gợi ý trước khi lộ đáp án khi chọn sai).
- Read Aloud (cả Phần 1 và mức Vận dụng mọi mức): dùng nguyên component 9.4 (`02_design_tiengAnh.md`) — `submitRecording()` để dạng khung, comment `// TODO: nối API chấm giọng nói`, không tự bịa kết quả chấm.
- Vị trí đáp án các câu trắc nghiệm chữ (không phải Listen-and-Circle) vẫn phải random khi build.
- **Sửa lỗi ở mục "Nhận diện khác biệt phát âm — Minimal pairs nâng cao" (Easy):** bản cũ (thuần
  chữ, không audio) buộc phải chọn 1 trong 2 lỗi — giấu âm mục tiêu (mù mờ, không có căn cứ chọn)
  hoặc nêu tên âm mục tiêu trong đề (lộ đáp án qua chữ cái đầu, học sinh đoán qua mặt chữ mà không
  cần nghe/hiểu gì). Đã sửa: chuyển hẳn sang audio `playPromptWord()`, cùng cơ chế Listen-and-Circle
  Nhận biết ở trên nhưng distractor gần âm hơn (đúng tinh thần "Minimal pairs nâng cao" — Thông
  hiểu). KHÔNG build lại theo kiểu "thuần chữ không audio" như bản cũ.

### Ghi chú cho Giai đoạn 2 (Design)
- Đọc `02_design_tiengAnh.md` mục: 4.2 (Hero), 9.4 (Read Aloud/ghi âm — dùng cả Phần 1 lẫn Vận
  dụng mọi mức Phần 2), 4.6 (Practice types — MCQ chuẩn cho Nhận diện khác biệt/Odd One Out), 4.7
  (Self-assessment).
- Đọc `03_engine_tiengAnh.md` mục 4.2 — dùng `playPromptWord()` cho toàn bộ câu Listen-and-Circle
  (Nhận biết) LẪN mục "Nhận diện khác biệt phát âm — Minimal pairs nâng cao" (Thông hiểu, cùng cơ
  chế nhưng distractor khó hơn), KHÔNG dùng `speak()` thường (tốc độ nhanh hơn, không phù hợp bài
  phân biệt minimal pairs).
- KHÔNG dùng 4.8b (Practice Reference Pane) — xem Ngoại lệ ở đầu kịch bản này.
