# Nguồn Tra cứu & Chiến lược Tìm kiếm

> **Mục đích:** Danh sách nguồn chính thống để tra cứu VBQPPL VN + cú pháp tìm kiếm hiệu quả + cách xác minh nhanh.

---

## 0. Fast Path — Kiểm tra Hiệu lực VB (Không cần khởi động OODA)

**Trigger:** User hỏi dạng `"[VB X] còn hiệu lực không?"` / `"NĐ X đã bị thay chưa?"` / `"TT Y còn áp dụng không?"` — đơn thuần kiểm tra hiệu lực, **không kèm tình huống pháp lý cần phân tích**.

**Quy trình — 3 bước, trả lời thẳng lên chat, không tạo file phase, không tạo report:**

```
Bước 1 — Search
  search_web: site:thuvienphapluat.vn "[số hiệu VB]"
  → Lấy URL kết quả đầu tiên khớp số hiệu

Bước 2 — Fetch & Đọc banner
  web_fetch [URL]
  → Đọc banner đầu trang:
      🟢 "Còn hiệu lực"        → Trả lời: Còn hiệu lực + ngày có hiệu lực
      🟡 "Hết hiệu lực một phần" → Trả lời: Còn hiệu lực một phần + liệt kê điều/khoản đã hết
      🔴 "Hết hiệu lực"        → Trả lời: Đã hết hiệu lực từ [ngày] + VB thay thế là gì

Bước 3 — Nếu "Hết hiệu lực": đọc thêm tab "Lịch sử hiệu lực"
  → Xác định VB nào thay thế / sửa đổi / bãi bỏ VB này
  → Trả lời kèm: "Thay thế bởi [số hiệu VB mới] có hiệu lực từ [ngày]"
```

**Đầu ra:** Trả lời trực tiếp trên chat, không quá 3-4 dòng. Không tạo file. Không chạy PDCA/OODA.

**Khi nào KHÔNG dùng Fast Path:**
- User hỏi hiệu lực kèm tình huống ("NĐ X còn hiệu lực không? Tôi đang bị tranh chấp...") → chuyển sang OODA bình thường
- VB là QĐ UBND tỉnh địa phương → thuvienphapluat.vn có thể không có, thông báo user tra cổng tỉnh

---

## 1. Nguồn Chính thống

### Ưu tiên 1 — Cơ sở dữ liệu pháp luật

| Nguồn | URL | Điểm mạnh | Lưu ý |
|---|---|---|---|
| **Thư Viện Pháp Luật** | thuvienphapluat.vn | Đầy đủ nhất, có "Lịch sử hiệu lực", "VB liên quan", bản hợp nhất | Một số tính năng yêu cầu tài khoản |
| **Luật Việt Nam** | luatvietnam.vn | Giao diện sạch, có bản dịch Anh, tóm tắt VB | Ít VB hơn TVPL |
| **Công báo Chính phủ** | congbao.chinhphu.vn | Văn bản chính thức, có giá trị pháp lý cao nhất | Chỉ có VB trung ương, khó tìm kiếm |
| **Cổng TTĐT Chính phủ** | chinhphu.vn | Tin tức, chính sách, VB mới nhất | Không phải CSDL tra cứu chuyên dụng |

### Ưu tiên 2 — Trang chuyên ngành

| Nguồn | URL | Chuyên ngành |
|---|---|---|
| Bộ Tư pháp | moj.gov.vn | VB pháp luật, rà soát, hệ thống hóa |
| Tòa án nhân dân tối cao | toaan.gov.vn | Án lệ, nghị quyết HĐTP |
| Bộ Tài chính | mof.gov.vn | Thuế, phí, tài chính |
| Bộ LĐTB&XH | molisa.gov.vn | Lao động, BHXH |
| Bộ TN&MT | monre.gov.vn | Đất đai, môi trường |
| Bộ Xây dựng | moc.gov.vn | Xây dựng, quy hoạch, BĐS |

### Ưu tiên 3 — Hỏi đáp chính sách thực tiễn

| Nguồn | URL | Điểm mạnh | Lưu ý |
|---|---|---|---|
| **Chính sách Online** | chinhsachonline.chinhphu.vn | Câu hỏi thực tế + trả lời chính thức từ Bộ/ngành; có chuyên mục đấu thầu, thuế, tài chính, lao động | Render JS — không fetch được toàn bộ; dùng search_web để tìm, sau đó web_fetch URL cụ thể |

**Cú pháp tìm trên chinhsachonline:**
```
site:chinhsachonline.chinhphu.vn "[keyword]"
site:chinhsachonline.chinhphu.vn "[keyword đấu thầu]" OR "[keyword tài chính]"
```

**Khi nào dùng Ưu tiên 3:**
- Cần hướng dẫn thực tiễn cho tình huống cụ thể mà VBQPPL không quy định rõ
- Cần biết Bộ/ngành diễn giải điều luật như thế nào trong thực tế
- Adversarial Check: tìm cách Bộ đã trả lời tình huống tương tự

**Giá trị pháp lý:** Câu trả lời của Bộ/ngành là **ý kiến giải đáp hành chính**, không phải VBQPPL — dùng để bổ trợ SOT và Adversarial Check, **không dùng làm căn cứ pháp lý chính** trong phần 2 của legal_report.

---

## 2. Cú pháp Tìm kiếm

### Tìm VB theo keyword (search_web)

```
site:thuvienphapluat.vn "[keyword chính]" "[năm]"
site:thuvienphapluat.vn "[tên luật]" "điều [X]"
site:thuvienphapluat.vn "[số hiệu VB]"
```

### Tìm VB sửa đổi

```
site:thuvienphapluat.vn "sửa đổi" "[số hiệu VB gốc]"
site:thuvienphapluat.vn "thay thế" "[số hiệu VB gốc]"
site:thuvienphapluat.vn "bãi bỏ" "[số hiệu VB gốc]"
```

### Tìm NĐ hướng dẫn Luật

```
site:thuvienphapluat.vn "quy định chi tiết" "[tên luật]" "nghị định"
site:thuvienphapluat.vn "hướng dẫn thi hành" "[số hiệu luật]"
```

### Tìm VB theo lĩnh vực + thời gian

```
site:thuvienphapluat.vn "[lĩnh vực]" "2025" "nghị định"
site:thuvienphapluat.vn "[lĩnh vực]" "có hiệu lực" "2025"
```

### Đọc nội dung VB cụ thể (web_fetch)

Sau khi search_web tìm được URL → dùng `web_fetch` để đọc nội dung chi tiết điều/khoản. URL thuvienphapluat.vn thường có format:
```
https://thuvienphapluat.vn/van-ban/[linh-vuc]/[ten-van-ban]-[so-hieu]-[nam]-[so-id]
```

---

## 3. Xác minh Nhanh Hiệu lực

Trước khi trích dẫn bất kỳ VB nào, PHẢI kiểm tra hiệu lực:

### Trên thuvienphapluat.vn

1. Mở trang VB → nhìn **banner đầu trang**:
   - 🟢 "Còn hiệu lực" → OK, dùng được
   - 🟡 "Hết hiệu lực một phần" → Cần kiểm tra điều/khoản nào hết
   - 🔴 "Hết hiệu lực" → KHÔNG dùng (trừ khi mốc user nằm trước ngày hết hiệu lực)

2. Tab **"Lịch sử hiệu lực"** → xem timeline:
   - Ngày ban hành
   - Ngày có hiệu lực
   - Ngày bị sửa đổi / thay thế (nếu có)

3. Mục **"Văn bản liên quan"** → kiểm tra:
   - "Văn bản sửa đổi": VB nào đã sửa VB này?
   - "Văn bản thay thế": VB nào thay thế VB này?
   - "Văn bản được hướng dẫn": VB này hướng dẫn cái gì?

---

## 4. Cách đọc Số hiệu VB

Hiểu số hiệu giúp nhanh chóng phân loại VB:

| Pattern | Ý nghĩa | Ví dụ |
|---|---|---|
| `xx/yyyy/QHzz` | Luật, kỳ họp QH khóa zz | 45/2019/QH14 (BLLĐ 2019) |
| `xx/yyyy/NĐ-CP` | Nghị định Chính phủ | 145/2020/NĐ-CP |
| `xx/yyyy/TT-[Bộ]` | Thông tư của Bộ | 10/2021/TT-BXD |
| `xx/QĐ-TTg` | Quyết định Thủ tướng | 1579/QĐ-TTg |
| `xx/yyyy/QĐ-UBND` | Quyết định UBND | 15/2024/QĐ-UBND |

- **xx**: Số thứ tự VB
- **yyyy**: Năm ban hành
- **QHzz**: Quốc hội khóa zz (VD: QH15 = khóa 15, 2021-2026)
- **CP**: Chính phủ
- **TTg**: Thủ tướng
- **[Bộ]**: Tên viết tắt Bộ ban hành (BXD, BTC, BGTVT...)

---

## 5. Red Flags — Dấu hiệu Nguồn Không Đáng Tin

| Red flag | Hành động |
|---|---|
| Blog/website cá nhân trích dẫn luật không kèm số hiệu | Tra lại trên TVPL để xác minh |
| VB trên trang không chính thống, không có banner hiệu lực | Bỏ qua, tìm trên TVPL |
| Nội dung VB không có ngày hiệu lực | Kiểm tra trên congbao.chinhphu.vn |
| Kết quả search cho bài viết "phân tích" thay vì VB gốc | Dùng bài phân tích làm gợi ý keyword, nhưng trích dẫn phải từ VB gốc |
| VB có format cũ (trước 2015) mà không có bản cập nhật | Kiểm tra đã bị thay thế chưa |
