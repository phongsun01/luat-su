# legal_phase_[N].md — Template
# Thư mục: legal_research_[chủ_đề]/legal_phase_[N].md
# Hướng dẫn: Điền vào các ô [...]. Xóa dòng hướng dẫn (in nghiêng) sau khi điền.
# KHÔNG xóa entry cũ — chỉ append xuống cuối.

---

## ═══ KHỞI TẠO (Bước 0) ═══

### 5 Trục Tọa độ Pháp lý

| Trục | Giá trị | Ghi chú / Giả định |
|---|---|---|
| **Đối tượng** | [...] | [...] |
| **Hành vi** | [...] | [...] |
| **Tác động** | [...] | [...] |
| **Phạm vi** | [...] | [...] |
| **Thời điểm ★** | [...] | *Nếu không rõ: ghi `[Giả định: hôm nay DD/MM/YYYY]`* |

**Target (Câu hỏi cốt lõi):** [...]

**Exit Condition:**
- [ ] Tất cả nhánh A, B, C của Issue Graph đạt `[✓]`
- [ ] Đã giải quyết xung đột Lex nếu có
- [ ] Adversarial Check đã chạy đủ 3 câu hỏi

---

### Issue Graph

```
Vấn đề gốc: [Hành vi] của [Đối tượng] tại [Thời điểm]
│
├── Nhánh A [ ] — Điều kiện áp dụng / Phạm vi điều chỉnh
│     ├── A1 [ ] [Câu hỏi về chủ thể đủ điều kiện]
│     └── A2 [ ] [Câu hỏi về hành vi có thuộc phạm vi VB]
│
├── Nhánh B [ ] — Quyền, Nghĩa vụ & Thủ tục
│     ├── B1 [ ] [Câu hỏi về quyền/nghĩa vụ chính của các bên]
│     └── B2 [ ] [Câu hỏi về thủ tục / trình tự thực hiện]
│
├── Nhánh C [ ] — Chế tài & Thời hiệu
│     ├── C1 [ ] [Câu hỏi về chế tài vi phạm]
│     └── C2 [ ] [Câu hỏi về thời hiệu xử lý / khởi kiện]
│
└── Nhánh D [ ] — Rủi ro ẩn (điền khi phát sinh)
      └── D1 [ ] [VB chuyên ngành liên đới / điều khoản chuyển tiếp]
```

*Trạng thái: `[ ]` Chưa có SOT — `[~]` SOT thô — `[✓]` Đã có nguyên văn — `[GAP]` Không tìm được, ghi chú rủi ro*

---

### SOT Thô (Raw Source of Truth)

*Nguồn: đọc domain file tương ứng → cột "Căn cứ pháp lý" → rút danh sách VB xương sống*

| Tọa độ (VB – Số hiệu – Điều – Khoản – Điểm) | Nguyên văn | Trạng thái | Ngày hiệu lực |
|---|---|---|---|
| [Luật/NĐ/TT – Số hiệu] | *(để trống — điền ở OBSERVE)* | SOT thô | [...] |
| [...] | *(để trống)* | SOT thô | [...] |

---

## ═══ LEGAL OODA — VÒNG 1 ═══

### OBSERVE — [Vòng 1 / DD/MM/YYYY]

*Tra song song theo nhánh. Mỗi Q tương ứng một nhánh Issue Graph.*

**Q_A — [Câu hỏi nhánh A]:**
```
search_web: site:thuvienphapluat.vn "[keyword A]" "[số hiệu VB từ SOT thô]"
```
→ Kết quả: [URL / Không tìm thấy]
→ Nguyên văn trích dẫn:
> **[Cấp VB] [Số hiệu] – Điều X, Khoản Y, Điểm Z**
> "[Copy nguyên văn chính xác]"
> Trạng thái: [Còn hiệu lực / Hết hiệu lực / Hết một phần] tại [Thời điểm]

**Q_B — [Câu hỏi nhánh B]:**
```
search_web: site:thuvienphapluat.vn "[keyword B]" "[số hiệu VB]"
```
→ Kết quả: [...]
→ Nguyên văn trích dẫn:
> **[Tọa độ đầy đủ]**
> "[Nguyên văn]"
> Trạng thái: [...]

**Q_C — [Câu hỏi nhánh C]:**
```
search_web: site:thuvienphapluat.vn "[keyword C]" "[số hiệu VB]"
```
→ Kết quả: [...]
→ Nguyên văn trích dẫn:
> **[Tọa độ đầy đủ]**
> "[Nguyên văn]"
> Trạng thái: [...]

**Cập nhật Issue Graph sau OBSERVE vòng 1:**
```
Nhánh A [~] / [✓] / [ ]
Nhánh B [~] / [✓] / [ ]
Nhánh C [~] / [✓] / [ ]
```

---

### ORIENT — [Vòng 1 / DD/MM/YYYY]

**1. Thứ bậc VB trong SOT:**

| Thứ tự ưu tiên | VB | Cấp | Ngày HL |
|---|---|---|---|
| 1 | [...] | Luật/Bộ luật | [...] |
| 2 | [...] | Nghị định | [...] |
| 3 | [...] | Thông tư | [...] |

**2. Tra chéo 3 chiều:**
- Xuống: [VB gốc] → NĐ hướng dẫn: [...] / Chưa tìm thấy → thêm vào Q_B vòng sau
- Ngang: [VB gốc] đã bị sửa đổi bởi: [...] / Không có VB sửa đổi
- Thời gian: Phiên bản áp dụng tại [Thời điểm]: [...] / Điều khoản chuyển tiếp: [...]

**3. Xung đột Lex (nếu có):**

| VB A | VB B | Loại xung đột | Giải quyết theo |
|---|---|---|---|
| [...] | [...] | Lex superior/posterior/specialis | [...] thắng vì [...] |

*Nếu không có xung đột: "Không phát hiện xung đột Lex trong SOT hiện tại."*

---

### DECIDE — Adversarial Check [Vòng 1 / DD/MM/YYYY]

*Load `resources/adversarial-patterns.md` → đọc mục lĩnh vực tương ứng trước khi đặt 3 câu hỏi.*

**Câu hỏi 1 — Ngoại lệ / Loại trừ:**
```
search_web: site:thuvienphapluat.vn "[số hiệu VB chính]" "trừ trường hợp" OR "không áp dụng"
```
→ Kết quả: [Tìm thấy / Không tìm thấy]
→ Nội dung (nếu có): "[...]"
→ Tác động đến phương án: [Điều chỉnh phương án / Không ảnh hưởng]

**Câu hỏi 2 — VB phản chiều:**
```
search_web: site:thuvienphapluat.vn "[keyword vấn đề]" "hướng dẫn" "[năm gần nhất]"
```
→ Kết quả: [...]
→ Tác động: [...]

**Câu hỏi 3 — Án lệ / Hướng dẫn HĐTP:**
```
search_web: site:thuvienphapluat.vn "hội đồng thẩm phán" "[keyword vấn đề]"
```
→ Kết quả: [...]
→ Tác động: [...]

**Kết quả Adversarial vòng 1:**
- [ ] Tìm thấy phản đề → bổ sung vào SOT + cập nhật Nhánh D Issue Graph
- [x] Không tìm thấy phản đề → "Adversarial Check vòng 1: không tìm thấy VB phản chiều — phương án được củng cố."

---

### ACT — [Vòng 1 / DD/MM/YYYY]

**Trạng thái Issue Graph hiện tại:**
```
Nhánh A [?] — [mô tả ngắn]
Nhánh B [?] — [mô tả ngắn]
Nhánh C [?] — [mô tả ngắn]
Nhánh D [?] — [mô tả ngắn / N/A]
```

**Quyết định:**
- [ ] Đạt Exit Condition → chuyển sang Bước 2 (Đóng gói)
- [ ] Còn nhánh `[ ]`/`[~]` → quay lại OBSERVE vòng 2 với Q còn thiếu: [liệt kê]
- [ ] 2 vòng không có dữ liệu mới → ghi `[GAP]`, chuyển Bước 2 với cảnh báo

---

## ═══ LEGAL OODA — VÒNG 2 ═══ (nếu cần)

### OBSERVE — [Vòng 2 / DD/MM/YYYY]

*Chỉ tra các nhánh còn `[ ]` hoặc `[~]` từ ACT vòng 1.*

[... điền tương tự vòng 1 ...]

### ORIENT — [Vòng 2 / DD/MM/YYYY]
[...]

### DECIDE — Adversarial Check [Vòng 2 / DD/MM/YYYY]
[...]

### ACT — [Vòng 2 / DD/MM/YYYY]
[...]

---

## ═══ TỔNG KẾT PHASE ═══

*Điền sau khi đạt Exit Condition. Đây là đầu vào cho legal_report.*

### Bảng SOT Hoàn chỉnh

| # | Tọa độ (VB – Số hiệu – Điều – Khoản – Điểm) | Nguyên văn | Trạng thái | Ngày HL | Nhánh |
|---|---|---|---|---|---|
| 1 | [...] | "[...]" | Còn HLực | [...] | A1 |
| 2 | [...] | "[...]" | Còn HLực | [...] | B1 |
| 3 | [...] | "[...]" | Còn HLực | [...] | C1 |

### Truth (Sự thật pháp lý có SOT đối chứng)
- [...] — căn cứ: [Tọa độ #N]
- [...] — căn cứ: [Tọa độ #N]

### Actionable (Hướng giải quyết thực tế)
- [...] 
- [...]

### Adversarial (Kết quả tự phản biện)
- Phản đề tìm thấy: [...] / Không có
- Điều chỉnh phương án: [...] / Không cần điều chỉnh

### Next Gap (Rủi ro / Điểm mờ còn tồn đọng)
- `[GAP]` Nhánh [...]: [mô tả rủi ro] — khuyến nghị: [tham vấn luật sư / tra thêm VB X]
- *Nếu không có: "Không có GAP tồn đọng."*
