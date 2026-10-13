# Chuẩn Trích dẫn Máy móc & Template SOT

> **Mục đích:** Format trích dẫn nguyên văn VBQPPL và template bảng Source of Truth (SOT). Trích dẫn chính xác là nền tảng — thiếu tọa độ hoặc sai nguyên văn thì toàn bộ tư vấn mất giá trị.

---

## 1. Format Trích dẫn Đơn lẻ

Mỗi trích dẫn từ VBQPPL phải có đủ 4 thành phần:

### Tọa độ pháp lý

```
[Cấp VB] [Số hiệu] – Điều X, Khoản Y, Điểm Z
```

Ví dụ:
- `Luật 45/2019/QH14 – Điều 36, Khoản 1, Điểm a`
- `NĐ 145/2020/NĐ-CP – Điều 12, Khoản 3`
- `TT 10/2021/TT-BXD – Điều 5`

Quy ước viết tắt cấp VB:
| Viết đầy đủ | Viết tắt |
|---|---|
| Bộ luật | BL |
| Luật | Luật |
| Nghị định | NĐ |
| Thông tư | TT |
| Quyết định | QĐ |
| Nghị quyết | NQ |

### Nguyên văn (Verbatim)

Copy chính xác từ nguồn. Giữ nguyên:
- Dấu câu gốc (dấu chấm, phẩy, hai chấm)
- Chữ hoa/thường
- Số thứ tự (a, b, c hoặc 1, 2, 3)

Nếu đoạn dài, trích phần liên quan trực tiếp. Dùng `[...]` để đánh dấu phần bỏ qua.

Ví dụ đúng:
```
"Người sử dụng lao động phải báo trước cho người lao động biết trước ít nhất 
45 ngày đối với hợp đồng lao động không xác định thời hạn [...]"
```

### Trạng thái hiệu lực

| Trạng thái | Ý nghĩa | Khi nào dùng |
|---|---|---|
| `đang hiệu lực` | VB/điều khoản còn nguyên vẹn, chưa bị sửa | VB gốc chưa sửa |
| `đã sửa đổi bởi [VB]` | Nội dung đã thay đổi, cần đọc bản sửa | VB gốc bị sửa 1 phần |
| `hết hiệu lực` | Toàn bộ VB/điều khoản không còn áp dụng | VB bị thay thế/bãi bỏ |
| `chuyển tiếp` | Áp dụng theo điều khoản chuyển tiếp | Giai đoạn chuyển giao |

### Ngày hiệu lực

Format: DD/MM/YYYY. Ghi ngày VB bắt đầu có hiệu lực, không phải ngày ban hành.

---

## 2. Template Bảng SOT

SOT là bảng tổng hợp TẤT CẢ trích dẫn đã thu thập, sắp theo thứ bậc VB.

### Format Markdown

```markdown
## Source of Truth (SOT)

**Vấn đề:** [Mô tả vấn đề pháp lý]
**Mốc thời điểm:** [DD/MM/YYYY]
**Lĩnh vực:** [Tên lĩnh vực]

| # | Tọa độ pháp lý | Trích dẫn nguyên văn | Trạng thái | Hiệu lực | Vai trò |
|---|---|---|---|---|---|
| 1 | [Cấp] [Số hiệu] – Đ.X, K.Y | "[copy nguyên văn]" | [trạng thái] | [DD/MM/YYYY] | [vai trò trong vấn đề] |
| 2 | ... | ... | ... | ... | ... |

### Xung đột (nếu có)
⚠️ Trích dẫn #X và #Y mâu thuẫn về [nội dung]. 
Áp dụng [lex superior/posterior/specialis] → ưu tiên #[X/Y].
Lý do: [giải thích].
```

### Cột "Vai trò"

Ghi ngắn gọn trích dẫn này đóng vai trò gì trong vấn đề đang phân tích:
- "Quy định điều kiện [X]"
- "Xác định thẩm quyền [cơ quan]"
- "Quy định thời hạn [Y ngày]"
- "Chế tài nếu vi phạm"
- "Sửa đổi điều kiện tại #[trích dẫn gốc]"

---

## 3. Ví dụ SOT Hoàn chỉnh

**Vấn đề:** Doanh nghiệp cho NLĐ thôi việc vì lý do "tái cơ cấu tổ chức" — không thông báo trước 30 ngày cho UBND cấp tỉnh và NLĐ.
**Mốc thời điểm:** 15/03/2025
**Lĩnh vực:** Lao động

| # | Tọa độ pháp lý | Trích dẫn nguyên văn | Trạng thái | Hiệu lực | Vai trò |
|---|---|---|---|---|---|
| 1 | BLLĐ 45/2019/QH14 – Đ.34, K.11 | "Các trường hợp chấm dứt hợp đồng lao động: [...] 11. Người sử dụng lao động cho người lao động thôi việc theo quy định tại Điều 42 và Điều 43 của Bộ luật này." | đang hiệu lực | 01/01/2021 | Cơ sở pháp lý chấm dứt HĐLĐ khi thay đổi cơ cấu |
| 2 | BLLĐ 45/2019/QH14 – Đ.42, K.1 | "Những trường hợp sau đây được coi là thay đổi cơ cấu, công nghệ: a) Thay đổi cơ cấu tổ chức, tổ chức lại lao động; b) Thay đổi quy trình, công nghệ, máy móc, thiết bị sản xuất, kinh doanh gắn với ngành, nghề sản xuất, kinh doanh của người sử dụng lao động; c) Thay đổi sản phẩm hoặc cơ cấu sản phẩm." | đang hiệu lực | 01/01/2021 | Định nghĩa các trường hợp thay đổi cơ cấu, công nghệ |
| 3 | BLLĐ 45/2019/QH14 – Đ.42, K.3 | "Trong trường hợp người sử dụng lao động không thể giải quyết được việc làm mà phải cho người lao động thôi việc thì phải trả trợ cấp mất việc làm theo quy định tại Điều 47 của Bộ luật này." | đang hiệu lực | 01/01/2021 | Nghĩa vụ trả trợ cấp mất việc làm |
| 4 | BLLĐ 45/2019/QH14 – Đ.42, K.6 | "Việc cho người lao động thôi việc theo quy định tại Điều này chỉ được tiến hành sau khi đã trao đổi ý kiến với tổ chức đại diện người lao động tại cơ sở đối với nơi có tổ chức đại diện người lao động tại cơ sở mà người lao động là thành viên và thông báo trước 30 ngày cho Ủy ban nhân dân cấp tỉnh và cho người lao động." | đang hiệu lực | 01/01/2021 | Trình tự thủ tục bắt buộc: trao đổi công đoàn và thông báo trước 30 ngày |
| 5 | BLLĐ 45/2019/QH14 – Đ.41, K.1 | "Khi đơn phương chấm dứt hợp đồng lao động trái pháp luật thì người sử dụng lao động [...] phải trả tiền lương, đóng bảo hiểm xã hội, bảo hiểm y tế, bảo hiểm thất nghiệp trong những ngày người lao động không được làm việc [...]" | đang hiệu lực | 01/01/2021 | Hệ quả xử lý cho thôi việc trái quy định pháp luật |

### Xung đột
Không có xung đột trong SOT này.

### Kết luận từ SOT
- Cho thôi việc vì lý do "tái cơ cấu tổ chức" được điều chỉnh bởi Điều 42 BLLĐ 2019 (khoản 11 Điều 34), **không phải** quyền đơn phương chấm dứt theo Điều 36 (báo trước 45 ngày).
- NSDLĐ phải trao đổi với tổ chức đại diện người lao động tại cơ sở và **thông báo trước 30 ngày cho UBND cấp tỉnh và cho NLĐ** (Đ.42 K.6), đồng thời chi trả trợ cấp mất việc làm (Đ.42 K.3, Đ.47).
- Nếu tự ý cho thôi việc mà không thông báo trước 30 ngày hoặc vi phạm trình tự Điều 42 $	o$ chấm dứt trái pháp luật, phải chịu trách nhiệm bồi thường và khôi phục quyền lợi theo Điều 41.

---

## 4. Lỗi Trích dẫn Phổ biến (Tránh)

| Lỗi | Tại sao sai | Cách đúng |
|---|---|---|
| Tóm tắt thay vì copy nguyên văn | Mất chi tiết quan trọng, có thể diễn giải sai | Copy verbatim, dùng `[...]` nếu dài |
| Thiếu Khoản/Điểm | 1 Điều có nhiều Khoản quy định khác nhau | Ghi đủ Điều-Khoản-Điểm |
| Không ghi trạng thái | Có thể trích VB đã sửa đổi | Luôn kiểm tra + ghi trạng thái |
| Trích VB hết hiệu lực | Tư vấn dựa trên luật cũ = sai | Kiểm tra "Tình trạng hiệu lực" trước |
| Nhầm ngày ban hành ↔ ngày hiệu lực | Nhiều VB ban hành trước nhưng có hiệu lực sau | Ghi ngày hiệu lực, không phải ngày ban hành |
