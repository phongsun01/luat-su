# Template Mẫu: File Lưu Vết Nghiên Cứu Pháp Lý (legal_phase_X.md)

> File này được tạo tự động bởi Agent trong thư mục `legal_research_[chủ_đề]/` theo cơ chế N+1 bất biến (Immutable Ledger). Mỗi vòng lặp PDCA sẽ ghi nối (append) dữ liệu IPO vào file này.

---

# Nghiên cứu Pháp lý: [Tên chủ đề/vấn đề] — Phase 1

- **Ngày khởi tạo:** DD/MM/YYYY
- **Phiên nghiên cứu:** Phase 1 (Baseline)
- **Agent/Skill:** tvpl (PDCA Cascade)

---

## 1. Tọa độ Định danh 5 Trục Pháp lý

| Trục | Giá trị xác định | Ghi chú / Giả định |
|---|---|---|
| **ĐỐI TƯỢNG** | [Chủ thể, khách thể chính] | Ví dụ: Người lao động & Doanh nghiệp |
| **HÀNH VI** | [Hành vi pháp lý trọng tâm] | Ví dụ: Sa thải, cho thôi việc vì tái cơ cấu |
| **TÁC ĐỘNG** | [Hệ quả pháp lý phát sinh] | Ví dụ: Yêu cầu bồi thường, thanh toán trợ cấp |
| **PHẠM VI** | [Địa bàn, loại hình chủ thể] | Ví dụ: Doanh nghiệp ngoài quốc doanh tại TP.HCM |
| **THỜI ĐIỂM** | [Mốc thời gian xảy ra sự việc] | Ví dụ: 15/03/2025 (xác định VB áp dụng) |

---

## 2. Mục tiêu & Exit Condition

- **Target (Câu hỏi cốt lõi):** [Câu hỏi pháp lý cụ thể cần giải quyết]
- **Exit Condition:** SOT có ≥3 trích dẫn nguyên văn bao phủ: (1) căn cứ hành vi, (2) trình tự thủ tục, (3) chế tài/hệ quả; đã đối chiếu mốc thời điểm và không còn xung đột chưa phân xử.

---

## 3. SOT Thô (Raw SOT từ Domain Module)

*Rút ra từ file domain tương ứng trước khi tiến hành tra cứu sâu:*

| # | Tọa độ pháp lý | Trích dẫn nguyên văn | Trạng thái | Hiệu lực | Vai trò |
|---|---|---|---|---|---|
| 1 | BLLĐ 45/2019/QH14 – Đ.34, K.11 | [Chờ tra cứu nguyên văn] | [Chờ xác minh] | 01/01/2021 | Căn cứ chấm dứt HĐLĐ |
| 2 | BLLĐ 45/2019/QH14 – Đ.42 | [Chờ tra cứu nguyên văn] | [Chờ xác minh] | 01/01/2021 | Thủ tục khi thay đổi cơ cấu |
| 3 | BLLĐ 45/2019/QH14 – Đ.41 | [Chờ tra cứu nguyên văn] | [Chờ xác minh] | 01/01/2021 | Hậu quả vi phạm |

---

## 4. Nhật Ký Thực Thi PDCA Cascade (Lưu Vết IPO)

### 🔄 Vòng 1 — Tra cứu Luật gốc & Thủ tục

- **[P] Plan:** 
  - Đặt câu hỏi: Trình tự cho thôi việc vì thay đổi cơ cấu theo Điều 42 quy định cụ thể thời hạn báo trước và nghĩa vụ gì?
  - Keyword: `"thay đổi cơ cấu" "báo trước" "45/2019" "điều 42"`
- **[D] Do:** 
  - Tool gọi: Tra cứu web (site:thuvienphapluat.vn) $	o$ đọc nội dung chi tiết Điều 42 BLLĐ 2019.
  - Kết quả thô: Trích xuất Điều 42 Khoản 1, 3, 6.
- **[C] Check:** 
  - So khớp: Thấy quy định phải thông báo trước 30 ngày cho UBND cấp tỉnh và NLĐ.
  - Xung đột/Lỗ hổng: Không áp dụng thời hạn 45 ngày của Điều 36. Cần kiểm tra xem có Nghị định hướng dẫn chi tiết không.
- **[A] Act:** 
  - Cập nhật trích dẫn nguyên văn vào SOT.
  - Hướng đi vòng 2: Tra tiếp Nghị định hướng dẫn thi hành Điều 42.

*(Mỗi vòng PDCA tiếp theo được ghi nối tiếp vào đây...)*

---

## 5. Tổng Kết Phase (Đóng gói & Chốt sự thật)

1. **Sự thật (Truth):**
   - Đã xác định rõ căn cứ pháp lý theo Điều 42 BLLĐ 2019. Thủ tục bắt buộc có trao đổi công đoàn và thông báo trước 30 ngày cho UBND tỉnh và NLĐ.
2. **Hành động (Actionable):**
   - Khuyến nghị hướng xử lý: Khiếu nại/khởi kiện yêu cầu bồi thường theo Điều 41 do NSDLĐ vi phạm thời hạn báo trước.
3. **Khoảng trống (Next Gap):**
   - Cần xác minh rõ NLĐ đã nhận tiền trợ cấp mất việc làm theo Điều 47 hay chưa.
