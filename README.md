# ⚖️ Kỹ năng Tư vấn Pháp luật Việt Nam (Luật sư AI / Legal OODA Loop)

Kỹ năng chuyên gia (Skill) dành cho trợ lý ảo AI (Hermes Agent / Antigravity) hỗ trợ nghiên cứu, tra cứu và tư vấn đường lối giải quyết vấn đề pháp lý tại Việt Nam theo chuẩn **Legal OODA Loop** (Quan sát – Định hướng – Quyết định – Hành động).

---

## 🌟 Điểm nổi bật & Triết lý Cốt lõi

1. **Pháp luật là bản ghi rời rạc:** Văn bản QPPL Việt Nam phân mảnh với hệ thống Luật, Nghị định, Thông tư có quan hệ sửa đổi, bãi bỏ, thay thế chéo nhau. AI không đoán mò mà tra đúng tọa độ, ghép nối theo thứ bậc hiệu lực.
2. **Nguyên tắc Source of Truth (SOT):** Mọi khẳng định tư vấn đều phải có trích dẫn nguyên văn kèm tọa độ pháp lý chính xác: `Văn bản – Số hiệu – Điều – Khoản – Điểm`.
3. **Phản biện giả định & Bẫy pháp lý (Adversarial Check):** Trước khi kết luận phương án, AI bắt buộc phải tự phản biện bằng tập dữ liệu bẫy thực chiến (Adversarial Patterns) để tìm ra ngoại lệ, loại trừ, điều kiện hủy, hoặc rủi ro hình sự.
4. **Issue Graph toàn cảnh:** Phân tách mọi tình huống phức tạp theo 5 trục tọa độ (*Đối tượng, Hành vi, Tác động, Phạm vi, Thời điểm*) thành đồ thị vấn đề để không bỏ sót các nhánh rủi ro.
5. **Fast Path tối ưu:** Hỗ trợ cơ chế tra cứu siêu tốc (Fast Path) 3 bước cho các câu hỏi kiểm tra hiệu lực văn bản thuần túy (không chạy toàn bộ quy trình OODA, không sinh file rác).

---

## 📂 Cấu trúc Thư mục

```text
luat-su/
├── SKILL.md                          # Bộ chỉ thị cốt lõi cho AI Agent (Legal OODA Loop)
├── README.md                         # Tài liệu giới thiệu & hướng dẫn sử dụng skill
└── resources/                        # Tài nguyên & cơ sở tri thức bổ trợ
    ├── adversarial-patterns.md       # Tổng hợp bẫy pháp lý & kịch bản phản biện (7 nhóm)
    ├── citation-format.md            # Quy chuẩn trích dẫn SOT & cấu trúc tọa độ
    ├── cross-reference-guide.md      # Hướng dẫn tra chéo Luật - Nghị định - Thông tư
    ├── legal-system.md               # Hệ thống văn bản QPPL & nguyên tắc giải quyết xung đột Lex
    ├── search-sources.md             # Chiến lược tìm kiếm, Fast Path & danh mục nguồn chuẩn
    └── domains/                      # Bản đồ quy trình chuyên sâu theo từng lĩnh vực
        ├── 01-dan-su.md              # Dân sự, hợp đồng, hôn nhân, thừa kế
        ├── 02-hinh-su-hanh-chinh.md   # Hình sự, tố tụng, xử phạt VPHC
        ├── 03-doanh-nghiep-lao-dong.md # Doanh nghiệp, đầu tư, lao động, BHXH
        ├── 04-dat-dai-xay-dung.md    # Đất đai, nhà ở, quy hoạch, xây dựng
        ├── 05-thue-tai-chinh.md      # Thuế TNCN, TNDN, VAT, hóa đơn
        ├── 06-chuyen-nganh-khac.md   # Sở hữu trí tuệ, an ninh mạng, môi trường
        ├── 07-dau-thau.md            # Đấu thầu, mua sắm công, E-HSMT, NĐ 214/2025
        └── 08-hanh-chinh-khieu-nai.md # Thủ tục khiếu nại, tố cáo, kiến nghị đấu thầu
```

---

## 🔄 Quy trình Xử lý (Legal OODA Loop)

```
                       ┌─────────────────────────────────────┐
                       │ User đưa ra tình huống / câu hỏi   │
                       └──────────────────┬──────────────────┘
                                          │
                        [Hỏi hiệu lực thuần túy?]
                               ┌──────────┴──────────┐
                            Có │                     │ Không
                               ▼                     ▼
                     ┌──────────────────┐  ┌─────────────────────────────────┐
                     │   §0 FAST PATH   │  │ Bước 0: Định danh 5 trục        │
                     │  - Search TVPL   │  │         Vẽ Issue Graph          │
                     │  - Đọc banner    │  │         Tạo legal_phase_1.md    │
                     │  - Trả lời chat  │  └────────────────┬────────────────┘
                     └──────────────────┘                   │
                                                            ▼
                                           ┌─────────────────────────────────┐
                                           │ OBSERVE: Thu thập SOT thô       │
                                           │ - Tra cứu song song theo nhánh  │
                                           │ - Trích dẫn nguyên văn          │
                                           └────────────────┬────────────────┘
                                                            ▼
                                           ┌─────────────────────────────────┐
                                           │ ORIENT: Định hướng & Xếp bậc   │
                                           │ - Xử lý xung đột Lex            │
                                           │ - Rà soát mốc Thời điểm         │
                                           └────────────────┬────────────────┘
                                                            ▼
                                           ┌─────────────────────────────────┐
                                           │ DECIDE: Tự phản biện Phản đề    │
                                           │ - Load adversarial-patterns.md  │
                                           │ - Bẫy tố tụng / hợp đồng / thầu │
                                           └────────────────┬────────────────┘
                                                            ▼
                                           ┌─────────────────────────────────┐
                                           │ ACT: Đóng gói Báo cáo Tư vấn    │
                                           │ - Xuất legal_report_[topic].md  │
                                           │ - Đưa khuyến nghị & lộ trình    │
                                           └─────────────────────────────────┘
```

---

## 🛠️ Hướng dẫn Tích hợp & Sử dụng

### 1. Cài đặt vào Hermes Agent / Antigravity
Clone hoặc đặt thư mục `luat-su` vào thư mục skills:
```bash
# Trong config.yaml của Hermes
skills:
  - path: "D:/Antigravity/luat-su"
```

### 2. Kích hoạt trong hội thoại
Skill tự động kích hoạt khi nhận các câu hỏi liên quan đến:
- *"Quy định về thời hiệu khởi kiện tranh chấp hợp đồng đặt cọc đất đai?"*
- *"Hồ sơ dự thầu ký số bằng token cá nhân có bị loại không?"*
- *"Luật Đấu thầu 2023 còn hiệu lực không?"* *(Kích hoạt Fast Path)*
- *"Doanh nghiệp sa thải nhân viên khi mang thai thì bị phạt thế nào?"*

### 3. Quy chuẩn Kết quả đầu ra
- **Nghiên cứu trung gian:** Lưu tại `legal_research_[chủ_đề]/legal_phase_X.md` (lưu vết bất biến).
- **Báo cáo tư vấn chính thức:** Lưu tại `legal_research_[chủ_đề]/legal_report_[chủ_đề].md` gồm 5 phần:
  1. Tóm tắt tình huống & Vấn đề pháp lý cốt lõi.
  2. Bảng căn cứ pháp lý (Source of Truth).
  3. Phân tích so sánh các phương án (Pháp lý – Rủi ro – Khả thi).
  4. Khuyến nghị đường lối hành động & Lộ trình thực hiện.
  5. Cảnh báo rủi ro & Disclaimer.

---

## ⚠️ Tuyên bố Miễn trừ Trách nhiệm (Disclaimer)

Nội dung do Trợ lý AI cung cấp dựa trên hệ thống văn bản quy phạm pháp luật công khai và chỉ mang tính chất nghiên cứu, tham khảo sơ bộ. Trợ lý AI không cung cấp dịch vụ hành nghề luật sư theo Luật Luật sư và không thay thế cho ý kiến pháp lý chính thức từ cơ quan Nhà nước có thẩm quyền hoặc luật sư có chứng chỉ hành nghề trong từng vụ việc cụ thể.
