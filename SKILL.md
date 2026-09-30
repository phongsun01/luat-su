---
name: tu-van-phap-luat
description: TƯ VẤN ĐƯỜNG LỐI XỬ LÝ VẤN ĐỀ PHÁP LÝ VIỆT NAM — ĐỊNH DANH VẤN ĐỀ THEO 5 TRỤC, VẼ ISSUE GRAPH TOÀN CẢNH, THU THẬP NGUYÊN VĂN SONG SONG THEO TỪNG NHÁNH, TỰ PHẢN BIỆN TRƯỚC KHI KẾT LUẬN (LEGAL OODA LOOP). Hỗ trợ tra chéo VB gốc-sửa đổi-NĐ-TT, xây SOT với trích dẫn nguyên văn có tọa độ, xử lý xung đột Lex, tự kiểm tra phản đề (ngoại lệ/loại trừ/VB bác phương án), so sánh phương án với điểm Pháp lý/Rủi ro/Khả thi, khuyến nghị đường lối hành động. Kích hoạt khi user đề cập 'pháp luật', 'tư vấn luật', 'tranh chấp', 'bị kiện', 'nghị định'; yêu cầu 'tôi phải làm gì', 'luật quy định thế nào', 'xử lý tình huống này'; nói 'muốn khiếu nại', 'đòi bồi thường', 'thành lập công ty'; trong tình huống gặp vấn đề pháp lý cần đường lối giải quyết. KHÔNG dùng cho nghiên cứu phi pháp lý (→ nghien-cuu-pdca), viết bài (→ viet-chuyen-nghiep). Dùng cho MỌI vấn đề pháp lý — kể cả khi user chỉ nói 'tình huống này xử lý sao' mà không nhắc 'luật'.
---

# Tư Vấn Pháp Luật — Legal OODA Loop

> Khởi tạo Tọa độ & Issue Graph → OBSERVE (Thu thập song song theo nhánh) → ORIENT (Xếp thứ bậc & Giải xung đột) → DECIDE (Tự phản biện phản đề) → ACT (Đóng gói & Tư vấn đường lối).

---

## 1. Triết lý Cốt lõi

1. **Pháp luật VN = bản ghi rời rạc.** Luật, Nghị định, Thông tư là các record riêng lẻ với quan hệ sửa đổi/bổ sung/thay thế/bãi bỏ chồng chéo. Không bao giờ đọc hết — chỉ tra đúng chỗ, ghép đúng thứ tự.
2. **SOT là nền tảng.** Mọi phân tích và tư vấn phải truy ngược được về Source of Truth — tập trích dẫn NGUYÊN VĂN có tọa độ chính xác (VB – Số hiệu – Điều – Khoản – Điểm).
3. **Bắt buộc Hành động & Lưu vết.** Không tự suy luận quá 1 bước mà không gọi tool tra cứu. Mọi hoạt động nghiên cứu pháp lý phải được lưu vết vật lý (Immutable Multi-file Ledger) theo từng giai đoạn (Phase).
4. **Thời điểm quyết định tất cả.** Cùng một vấn đề, cùng một điều luật, nhưng khác thời điểm sẽ khác VB áp dụng (do sửa đổi, thay thế, chuyển tiếp).
5. **Disclaimer.** Skill hỗ trợ nghiên cứu và tư vấn sơ bộ; **không thay thế ý kiến pháp lý chính thức** từ luật sư hoặc cơ quan có thẩm quyền.

---

## 2. Bước 0 — Định danh, Khởi tạo & Issue Graph

Trước khi tra cứu bất cứ điều gì, PHẢI khởi tạo không gian, xác định trục tọa độ và vẽ bản đồ vấn đề.

### 0.1 — Khởi tạo Thư mục & File (Cơ chế N+1 Bắt buộc)
- Tạo thư mục `legal_research_[chủ_đề]/`.
- Kiểm tra xem đã có `legal_phase_X.md` chưa. Đọc file mới nhất để lấy SOT nếu có.
- Tạo file mới `legal_phase_{N+1}.md` — **copy từ `resources/templates/legal_phase_template.md`**, điền vào các ô `[...]`, không tự nghĩ ra format.

### 0.2 — Định danh 5 Trục Pháp lý

| Trục | Câu hỏi | Ví dụ |
|---|---|---|
| **ĐỐI TƯỢNG** | Ai? Cái gì? (chủ thể, khách thể) | Người lao động; Hợp đồng thuê nhà |
| **HÀNH VI** | Làm gì? (động từ pháp lý) | Sa thải; Đơn phương chấm dứt |
| **TÁC ĐỘNG** | Hệ quả gì? (quyền/nghĩa vụ/trách nhiệm) | Bồi thường; Truy cứu hình sự |
| **PHẠM VI** | Ở đâu? Loại hình? (không gian, bối cảnh) | TP.HCM; Doanh nghiệp FDI |
| **THỜI ĐIỂM** | Khi nào? ★ Trục quan trọng nhất | 15/03/2025 (xác định VB nào áp dụng) |

Thiếu trục → hỏi user (`ask_question`) trước khi tiếp tục. Ghi 5 trục vào đầu file phase.

### 0.3 — Sinh SOT Thô
- Tra bảng "Danh mục Module" (Mục 7) → đọc file `resources/domains/` tương ứng.
- Lọc cột **"Căn cứ pháp lý"** của các khâu khớp với Hành vi + Đối tượng → rút ra danh sách VB xương sống (Luật gốc + NĐ chính).
- Tạo bảng SOT thô trong file phase: `Tọa độ | Nguyên văn (để trống) | Trạng thái | Ngày hiệu lực`.

### 0.4 — Vẽ Issue Graph ★ (Điểm mới — Bắt buộc)

Đây là bản đồ toàn cảnh vấn đề pháp lý. Vẽ TRƯỚC khi tra bất kỳ VB nào. Mục đích: biết chính xác cần tìm gì, tránh đào sâu một hướng bỏ sót hướng khác.

**Cấu trúc Issue Graph chuẩn:**
```
Vấn đề gốc: [Hành vi] của [Đối tượng] tại [Thời điểm]
├── Nhánh A: Điều kiện áp dụng / Phạm vi điều chỉnh
│     ├── A1: Chủ thể có đủ điều kiện không?
│     └── A2: Hành vi có thuộc phạm vi VB điều chỉnh không?
├── Nhánh B: Quyền và Nghĩa vụ
│     ├── B1: Quyền/nghĩa vụ chính của các bên?
│     └── B2: Thủ tục / Trình tự thực hiện?
├── Nhánh C: Chế tài & Hệ quả
│     ├── C1: Chế tài vi phạm (hành chính / hình sự / dân sự)?
│     └── C2: Thời hiệu xử lý / khởi kiện?
└── Nhánh D: Rủi ro ẩn (điền sau nếu phát sinh)
      └── D1: VB chuyên ngành liên đới? Điều khoản chuyển tiếp?
```

**Quy tắc vẽ Issue Graph:**
- Mỗi nhánh = 1 câu hỏi độc lập cần có nguyên văn SOT riêng.
- Ghi trạng thái từng nhánh: `[ ]` Chưa có SOT / `[~]` SOT thô / `[✓]` Đã có nguyên văn.
- **Exit Condition** = tất cả nhánh A, B, C đạt `[✓]`. Nhánh D là tùy chọn nếu phát sinh.
- Ghi Issue Graph vào đầu file phase ngay sau 5 trục.

---

## 3. Bước 1 — Legal OODA Loop (Xây dựng SOT Hoàn chỉnh)

Đây là **lõi thực thi duy nhất**. Thực thi 4 pha theo thứ tự: OBSERVE → ORIENT → DECIDE → ACT. Mọi dữ kiện phải ghi nối (Append) xuống cuối file `legal_phase_X.md` — không được xóa hay sửa entry cũ.

**BẮT BUỘC** load `resources/search-sources.md` và `resources/cross-reference-guide.md` trước pha OBSERVE — định nghĩa cú pháp search và checklist tra chéo 3 chiều.

---

### [OBSERVE] — Thu thập Nguyên văn Song song theo Nhánh

Nhìn vào Issue Graph (Bước 0.4) → với mỗi nhánh còn trạng thái `[ ]` hoặc `[~]`, đặt câu hỏi thu thập song song:

```
Nhánh A → Q_A: [câu hỏi về điều kiện áp dụng]
Nhánh B → Q_B: [câu hỏi về quyền/nghĩa vụ + thủ tục]
Nhánh C → Q_C: [câu hỏi về chế tài + thời hiệu]
```

Với mỗi Q, thực hiện tra cứu theo cú pháp chuẩn từ `search-sources.md`:
```
search_web: site:thuvienphapluat.vn "[keyword nhánh]" "[số hiệu VB từ SOT thô]"
→ web_fetch URL kết quả → đọc banner hiệu lực + nội dung điều khoản
```

**Bắt buộc trích dẫn máy móc** cho mỗi kết quả tìm được:
- **Tọa độ:** `[Cấp VB] [Số hiệu] – Điều X, Khoản Y, Điểm Z`
- **Nguyên văn:** Copy chính xác, không paraphrase.
- **Trạng thái hiệu lực** tại mốc THỜI ĐIỂM của user.

Sau khi thu thập xong → cập nhật trạng thái Issue Graph: `[ ]` → `[~]` hoặc `[✓]`.
Ghi log OBSERVE vào file phase: `## OBSERVE — [timestamp/vòng N]` + danh sách kết quả theo nhánh.

---

### [ORIENT] — Xếp thứ bậc & Giải xung đột Lex

Nhìn toàn bộ SOT vừa thu thập → thực hiện 3 bước định hướng:

**1. Xếp thứ bậc VB** (load `resources/legal-system.md` nếu cần):
```
Hiến pháp > Luật/Bộ luật > NĐ > QĐ Thủ tướng > TT > VB địa phương
```
Đánh số thứ tự ưu tiên trong bảng SOT.

**2. Kiểm tra tra chéo 3 chiều** (theo `cross-reference-guide.md`):
- **Xuống:** VB gốc có NĐ/TT hướng dẫn chưa? Nếu chưa → thêm vào Q_B của OBSERVE vòng sau.
- **Ngang:** VB gốc đã bị sửa đổi/thay thế/bãi bỏ chưa? Tra: `site:thuvienphapluat.vn "sửa đổi" "[số hiệu VB]"`.
- **Thời gian:** Phiên bản nào áp dụng đúng mốc THỜI ĐIỂM? Kiểm tra điều khoản chuyển tiếp.

**3. Giải xung đột** nếu phát hiện mâu thuẫn giữa các VB trong SOT:

| Xung đột | Quy tắc áp dụng |
|---|---|
| VB cấp cao vs cấp thấp | Lex superior — cấp cao thắng |
| VB mới vs VB cũ (cùng cấp) | Lex posterior — VB mới thắng |
| VB chuyên ngành vs VB chung | Lex specialis — chuyên ngành thắng |

Ghi chú xung đột và kết quả giải quyết vào bảng SOT (cột riêng: `Ghi chú xung đột`).
Ghi log ORIENT vào file phase: `## ORIENT — [timestamp/vòng N]` + kết quả xếp thứ bậc + xung đột đã giải.

---

### [DECIDE] — Tự Phản biện (Adversarial Check) ★

Đây là pha phân biệt tư vấn chuyên nghiệp với tư vấn nghiệp dư. Sau khi có SOT ủng hộ phương án, **bắt buộc chơi vai luật sư đối phương** để tìm phản đề.

**BẮT BUỘC** load `resources/adversarial-patterns.md` → đọc mục lĩnh vực tương ứng với Issue Graph → dùng các pattern trong đó làm gợi ý cụ thể cho 3 câu hỏi dưới đây. Nếu lĩnh vực chưa có trong file → dùng Checklist 5 câu ở cuối file.

**3 câu hỏi bắt buộc:**

```
1. Ngoại lệ / Loại trừ:
   "Có điều khoản nào trong VB loại tình huống này ra khỏi phạm vi áp dụng không?"
   → search: site:thuvienphapluat.vn "[số hiệu VB]" "trừ trường hợp" OR "không áp dụng"

2. VB phản chiều:
   "Có NĐ/TT/Công văn hướng dẫn nào diễn giải theo hướng ngược lại không?"
   → search: site:thuvienphapluat.vn "[keyword vấn đề]" "hướng dẫn" "[năm gần nhất]"

3. Án lệ / Hướng dẫn HĐTP:
   "HĐTP TANDTC có Nghị quyết/Công văn nào hướng dẫn trái chiều không?"
   → search: site:thuvienphapluat.vn "hội đồng thẩm phán" "[keyword vấn đề]"
```

**Xử lý kết quả Adversarial:**
- Tìm thấy phản đề có giá trị → bổ sung vào SOT, điều chỉnh phương án tư vấn, cập nhật Issue Graph Nhánh D.
- Không tìm thấy phản đề → ghi rõ: `"Adversarial Check: không tìm thấy VB phản chiều — phương án được củng cố"`.
- Không được bỏ qua pha này dù SOT có vẻ đã đủ.

Ghi log DECIDE vào file phase: `## DECIDE — [timestamp/vòng N]` + kết quả 3 câu hỏi + điều chỉnh SOT nếu có.

---

### [ACT] — Đánh giá Coverage & Quyết định tiếp theo

Nhìn lại Issue Graph:
- Tất cả nhánh A, B, C đạt `[✓]` → **Chuyển sang Bước 2** (Đóng gói).
- Còn nhánh `[ ]` hoặc `[~]` → **Quay lại OBSERVE** với các Q còn thiếu.
- Nếu 2 vòng OODA liên tiếp không bổ sung được nguyên văn mới → dừng, ghi `[GAP]` vào nhánh đó, chuyển sang Bước 2 với cảnh báo.

Ghi log ACT: `## ACT — [timestamp/vòng N]` + trạng thái Issue Graph + quyết định tiếp theo.

---

## 4. Bước 2 — Đóng gói Phase & Xuất Báo cáo Tư vấn (Report)

Chỉ khi Issue Graph đạt Exit Condition (tất cả nhánh A, B, C = `[✓]`, hoặc có `[GAP]` được ghi chú rõ), mới chuyển sang tư vấn. Tư vấn khi còn nhánh `[ ]` là tư vấn thiếu căn cứ.

### Đóng gói Phase (Chốt file vật lý)
Agent BẮT BUỘC tổng kết vào cuối file `legal_phase_X.md`:
1. **Sự thật (Truth):** Phát hiện có SOT đối chứng — kèm tọa độ.
2. **Hành động (Actionable):** Giải pháp tư vấn thực tế rút ra từ SOT.
3. **Phản đề (Adversarial):** Kết quả Adversarial Check — phản đề tìm thấy hoặc xác nhận không có.
4. **Khoảng trống (Next Gap):** Nhánh `[GAP]` còn tồn đọng, rủi ro chưa rõ.

### Xuất Báo cáo Tư vấn (Tạo file Report)
Tuyệt đối KHÔNG xuất toàn bộ nội dung tư vấn dài dòng lên khung chat. Agent BẮT BUỘC phải tạo một file báo cáo chính thức mang tên `legal_report_[chủ_đề].md` nằm trong cùng thư mục `legal_research_[chủ_đề]/` — **copy từ `resources/templates/legal_report_template.md`**, điền vào các ô `[...]` từ Tổng kết phase file. Khung chat chỉ dùng để thông báo hoàn thành và tóm tắt ngắn gọn (1 đoạn) kèm link trỏ đến file Report.

**Cấu trúc 5 phần bắt buộc trong file `legal_report_[chủ_đề].md`:**

**(1) Tóm tắt tình huống & Vấn đề pháp lý**
- Xác nhận lại 5 trục (đối tượng, hành vi, tác động, phạm vi, thời điểm)
- Vấn đề pháp lý cốt lõi cần giải quyết
- `[Giả định]` kèm tác động nếu có thông tin chưa xác nhận

**(2) Căn cứ pháp lý — Bảng SOT**
- Bảng SOT đầy đủ (format ở §4)
- Sắp theo thứ bậc, ghi trạng thái, đánh dấu xung đột

**(3) Phân tích phương án**
- Liệt kê ≥2 phương án xử lý (nếu có)
- Mỗi phương án: căn cứ pháp lý (trỏ về # trong SOT) + ưu/nhược + rủi ro
- Nếu ≥2 phương án: so sánh đánh giá:
  - Pháp lý (1–5): Căn cứ chắc chắn đến đâu?
  - Rủi ro (1–5): Khả năng bất lợi?
  - Khả thi (1–5): Thực hiện được không?

**(4) Khuyến nghị đường lối + Lộ trình**
- Phương án được khuyến nghị + lý do
- Lộ trình bước tiếp cụ thể (hồ sơ cần chuẩn bị, cơ quan thụ lý, thời hạn)
- Các mốc quan trọng cần lưu ý

**(5) Cảnh báo & Bước tiếp theo**
- Rủi ro pháp lý cần lưu ý
- Trường hợp cần ý kiến luật sư/chuyên gia
- Nguồn ngoài web đánh dấu `[Web]`
- **Disclaimer**: "Nội dung tư vấn mang tính tham khảo, không thay thế ý kiến pháp lý chính thức."

---

## 5. Quality Gate — 15 điểm

Trước khi xuất đầu ra, kiểm tra toàn bộ:

**Khởi tạo:**
1. ✅ Đã tạo thư mục `legal_research_...` và file `legal_phase_X.md` chưa?
2. ✅ 5 trục đã xác định đầy đủ (đặc biệt THỜI ĐIỂM)?
3. ✅ File phase đã có SOT thô (VB xương sống từ domain file) ở đầu chưa?
4. ✅ Issue Graph đã được vẽ với đủ nhánh A, B, C chưa?

**OBSERVE:**
5. ✅ SOT có ≥3 trích dẫn nguyên văn bao phủ đủ nhánh A, B, C?
6. ✅ Mỗi trích dẫn có tọa độ đầy đủ (VB–Số hiệu–Điều–Khoản–Điểm)?
7. ✅ Trạng thái hiệu lực đúng với mốc THỜI ĐIỂM user?

**ORIENT:**
8. ✅ Đã tra chéo đủ 3 chiều (xuống/ngang/thời gian) cho VB chính?
9. ✅ Xung đột Lex đã được giải quyết và ghi vào SOT?

**DECIDE:**
10. ✅ Adversarial Check đã chạy đủ 3 câu hỏi (ngoại lệ / VB phản chiều / án lệ HĐTP)?
11. ✅ Kết quả Adversarial đã ghi vào file phase (dù không tìm thấy phản đề)?

**Đóng gói & Report:**
12. ✅ Tổng kết Truth/Actionable/Adversarial/Gap ở cuối file phase?
13. ✅ Đã tạo file `legal_report_[chủ_đề].md` với cấu trúc 5 phần?
14. ✅ Phương án xử lý đã đánh giá điểm Pháp lý/Rủi ro/Khả thi?
15. ✅ Khung chat chỉ chứa tóm tắt 1 đoạn + link file Report?

---

## 6. Khung Pháp luật VN (Tham chiếu nhanh)

Load `resources/legal-system.md` khi cần tra cứu chi tiết. Tóm tắt:

### Thứ bậc VBQPPL (Luật Ban hành VBQPPL 2025)

```
① Hiến pháp
② Bộ luật / Luật / Nghị quyết (Quốc hội)
③ Pháp lệnh / Nghị quyết (UBTVQH); NQ liên tịch UBTVQH-MTTQ
④ Lệnh / Quyết định (Chủ tịch nước)
⑤ Nghị định / Nghị quyết (Chính phủ); NQ liên tịch CP-MTTQ
⑥ Quyết định (Thủ tướng)
⑦ Nghị quyết (Hội đồng Thẩm phán TANDTC)
⑧ Thông tư (Bộ trưởng, Chánh án TANDTC, Viện trưởng VKSNDTC, TKTNN)
⑨ Thông tư liên tịch
⑩–⑮ Văn bản địa phương (HĐND/UBND tỉnh → huyện → xã)
```

### Xung đột

| Quy tắc | Áp dụng khi |
|---|---|
| **Lex superior** | VB cấp cao > VB cấp thấp |
| **Lex posterior** | VB mới > VB cũ (cùng cấp) |
| **Lex specialis** | VB chuyên ngành > VB chung (cùng cấp, cùng thời điểm) |

---

## 7. Danh mục Module Lĩnh vực & Keyword (SOT Baseline 07/2026)

Trước khi tra cứu, Agent phải rà soát xem yêu cầu thuộc nhóm nào dưới đây, sau đó đọc (`view_file`) trực tiếp file module tương ứng trong `resources/domains/`.

**Cách đọc file domain:** Lọc các hàng trong bảng "Vòng đời / Khâu kỹ thuật" có liên quan đến 5 trục đã xác định → rút ra danh sách VB từ cột **"Căn cứ pháp lý"** → đưa vào bảng SOT thô (chỉ lấy tên VB + số hiệu, chưa cần nguyên văn). Không đọc hết file nếu không liên quan — domain files có nhiều vòng đời, chỉ lấy phần khớp với Hành vi và Đối tượng của tình huống.

| Nhóm lĩnh vực | File Module Cần Đọc | Keyword nhận diện |
|---|---|---|
| Dân sự & Gia đình | `resources/domains/01-dan-su.md` | hợp đồng, vay mượn, bồi thường, thừa kế, di chúc, ly hôn, tài sản chung, cấp dưỡng, chia tài sản, án phí. |
| Hình sự & Hành chính | `resources/domains/02-hinh-su-hanh-chinh.md` | tội phạm, khởi tố, án treo, tham nhũng, phạt vi phạm, khiếu nại, tố cáo, giấy phép, phạt giao thông, căn cước. |
| Doanh nghiệp & Lao động | `resources/domains/03-doanh-nghiep-lao-dong.md` | thành lập công ty, cổ đông, vốn, phá sản, đầu tư, sa thải, lương, BHXH, hợp đồng lao động, kỷ luật. |
| Đất đai & Xây dựng | `resources/domains/04-dat-dai-xay-dung.md` | sổ đỏ, đền bù, chuyển nhượng, tiền SDĐ, giá đất, giấy phép xây dựng, chung cư, nhà ở xã hội, dự án BĐS. |
| Thuế & Tài chính | `resources/domains/05-thue-tai-chinh.md` | khai thuế, hoàn thuế, truy thu, TNCN, TNDN, VAT, hóa đơn, đấu thầu, nhà thầu. |
| Chuyên ngành Khác | `resources/domains/06-chuyen-nganh-khac.md` | an ninh mạng, dữ liệu, AI, chữ ký số, nhãn hiệu, bản quyền, ĐTM, ô nhiễm, GPLX, điện lực, năng lượng. |

---

## 8. Bản đồ Resources bổ trợ

| File | Nội dung | Load khi nào |
|---|---|---|
| `resources/legal-system.md` | Thứ bậc, hiệu lực, xung đột, quan hệ VB | Bước 0.2 (phân loại) + ORIENT (xếp thứ bậc) |
| `resources/cross-reference-guide.md` | Tra chéo 3 chiều: xuống-ngang-thời gian | **BẮT BUỘC** trước OBSERVE vòng đầu + ORIENT |
| `resources/citation-format.md` | Chuẩn trích dẫn + template SOT | OBSERVE (trích dẫn) + ACT (ghép SOT) |
| `resources/search-sources.md` | Nguồn tin cậy + cú pháp tìm kiếm | **BẮT BUỘC** trước OBSERVE vòng đầu |
| `resources/adversarial-patterns.md` | Thư viện bẫy pháp lý + cú pháp search phản đề theo 7 lĩnh vực | **BẮT BUỘC** đầu pha DECIDE |
| `resources/templates/legal_phase_template.md` | Template file nhật ký phase — 5 trục, Issue Graph, SOT, log OODA, tổng kết | Copy khi khởi tạo phase mới (§0.1) |
| `resources/templates/legal_report_template.md` | Template báo cáo tư vấn 5 phần — SOT bảng, phương án, lộ trình, disclaimer | Copy khi tạo report (§4) |

---

## 9. Nguyên tắc Vận hành

- Mọi kết luận kèm **tọa độ pháp lý** trỏ về SOT
- Thiếu dữ kiện → `[Giả định]` kèm tác động, hoặc hỏi user
- Nguồn tra web → `[Web]` kèm URL
- Ngày tháng: DD/MM/YYYY
- Không tự bịa nội dung VB — phải copy nguyên văn từ nguồn
- Skill hỗ trợ nghiên cứu và tư vấn sơ bộ; **không thay thế ý kiến pháp lý chính thức**
