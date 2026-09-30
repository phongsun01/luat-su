# ⚖️ Kỹ năng Tư vấn Pháp luật Việt Nam (Luật sư AI / Legal OODA Loop)

Kỹ năng chuyên gia (Skill) dành cho trợ lý AI (Hermes Agent / Antigravity) hỗ trợ nghiên cứu, tra cứu văn bản quy phạm pháp luật và tư vấn đường lối giải quyết vấn đề pháp lý tại Việt Nam theo chuẩn **Legal OODA Loop** (Quan sát – Định hướng – Quyết định – Hành động).

---

## 🌟 Điểm nổi bật & Triết lý Cốt lõi

1. **Pháp luật là bản ghi rời rạc (Discrete Records):** Hệ thống văn bản QPPL Việt Nam phân mảnh với hàng nghìn Luật, Nghị định, Thông tư có quan hệ sửa đổi, bổ sung, bãi bỏ, thay thế chéo nhau. AI không đọc mò mẫm hay tự suy diễn viển vông mà tra đúng tọa độ, ghép nối theo thứ bậc hiệu lực và quy tắc chuyển tiếp.
2. **Nguyên tắc Source of Truth (SOT) bất biến:** Mọi nhận định, lập luận và đề xuất tư vấn bắt buộc phải truy vết được về SOT — trích dẫn **nguyên văn** kèm tọa độ pháp lý chính xác: `Cấp văn bản – Số hiệu – Điều – Khoản – Điểm`.
3. **Bắt buộc hành động & Lưu vết vật lý (Immutable Multi-file Ledger):** Không tự suy luận quá 1 bước mà không gọi công cụ tra cứu. Mọi dữ kiện phát hiện qua các vòng lặp phải được ghi nối (`Append`) vào các file pha nghiên cứu (`legal_phase_{N}.md`), tuyệt đối không sửa/xóa dữ liệu lịch sử.
4. **Trục Thời điểm quyết định tất cả (Temporal Validity):** Cùng một hành vi, cùng một điều luật nhưng khác mốc thời gian sẽ áp dụng văn bản khác nhau (do hiệu lực thi hành, sửa đổi bổ sung hoặc quy định chuyển tiếp). Mọi phân tích bắt buộc neo chặt vào trục Thời điểm.
5. **Issue Graph toàn cảnh:** Phân tách mọi tình huống phức tạp theo 5 trục tọa độ (*Đối tượng, Hành vi, Tác động, Phạm vi, Thời điểm*) thành đồ thị vấn đề đa nhánh (Điều kiện, Quyền/Nghĩa vụ, Chế tài/Thời hiệu, Rủi ro ẩn) trước khi tìm kiếm, đảm bảo không bỏ sót ngách pháp lý nào.
6. **Tự phản biện phản đề (Adversarial Check):** Trước khi đưa ra kết luận hay đề xuất phương án, AI bắt buộc tự đặt bản thân vào vị trí đối tụng/bên đối lập, tra cứu bẫy pháp lý, ngoại lệ, loại trừ, điều kiện hủy, hoặc rủi ro trách nhiệm hình sự để bịt kín lỗ hổng.
7. **Fast Path tối ưu:** Hỗ trợ quy trình tra cứu nhanh 3 bước cho các câu hỏi kiểm tra hiệu lực văn bản thuần túy (không sinh file phase rác, trả lời trực tiếp trong chat).

---

## 📂 Cấu trúc Thư mục

```text
luat-su/
├── SKILL.md                          # Bộ chỉ thị lõi (Core Prompt) cho AI Agent (Legal OODA Loop)
├── README.md                         # Tài liệu kiến trúc, quy trình & hướng dẫn sử dụng chi tiết
├── bak/                              # Lưu trữ các phiên bản tiền nhiệm để đối chiếu
│   └── SKILL.md                      # Bản sao lưu SKILL-ooda trước khi nâng cấp
└── resources/                        # Tài nguyên & cơ sở tri thức bổ trợ
    ├── templates/                    # Thư viện mẫu chuẩn hóa (Templates) cho Agent
    │   ├── legal_phase_template.md   # Mẫu ghi chép quá trình nghiên cứu OODA (229+ dòng)
    │   └── legal_report_template.md  # Mẫu Báo cáo tư vấn pháp lý chính thức (167+ dòng)
    ├── adversarial-patterns.md       # Cẩm nang bẫy pháp lý & kịch bản phản biện (7 nhóm)
    ├── citation-format.md            # Quy chuẩn trích dẫn SOT & cấu trúc tọa độ pháp lý
    ├── cross-reference-guide.md      # Hướng dẫn tra chéo 3 chiều Luật - Nghị định - Thông tư
    ├── legal-system.md               # Hệ thống văn bản QPPL & nguyên tắc giải quyết xung đột Lex
    ├── search-sources.md             # Chiến lược tìm kiếm, cú pháp tra cứu TVPL & Fast Path
    └── domains/                      # Bản đồ căn cứ pháp lý & quy trình nghiệp vụ chuyên ngành
        ├── 01-dan-su.md              # Dân sự, hợp đồng, hôn nhân gia đình, thừa kế
        ├── 02-hinh-su-hanh-chinh.md   # Hình sự, tố tụng hình sự, xử phạt vi phạm hành chính
        ├── 03-doanh-nghiep-lao-dong.md # Doanh nghiệp, đầu tư, lao động, tiền lương, BHXH
        ├── 04-dat-dai-xay-dung.md    # Đất đai, nhà ở, kinh doanh BĐS, quy hoạch, xây dựng
        ├── 05-thue-tai-chinh.md      # Thuế TNCN, TNDN, GTGT, hóa đơn chứng từ, tài chính
        ├── 06-chuyen-nganh-khac.md   # Sở hữu trí tuệ, an ninh mạng, thương mại điện tử, môi trường
        ├── 07-dau-thau.md            # Đấu thầu, mua sắm công, E-HSMT, KHLCNT, NĐ 214/2025
        └── 08-hanh-chinh-khieu-nai.md # Khiếu nại hành chính, tố cáo, kiến nghị kết quả đấu thầu
```

---

## 📑 Chi tiết 2 Templates Mới (`resources/templates/`)

Nhằm loại bỏ hoàn toàn tình trạng Agent tự sáng tạo cấu trúc file hoặc bỏ quên các bước phân tích rủi ro, hệ thống sử dụng 2 template chuẩn mực:

### 1. `legal_phase_template.md` (Nhật ký nghiên cứu OODA)
- **Cơ chế hoạt động:** Agent chỉ cần copy nguyên mẫu sang `legal_research_[chủ_đề]/legal_phase_{N}.md` và điền vào các vị trí đánh dấu `[...]` theo thứ tự.
- **5 Trục Tọa độ & Issue Graph:** Định danh ngay ở đầu file với các nhánh A (Điều kiện), B (Quyền/Nghĩa vụ/Thủ tục), C (Chế tài/Thời hiệu), D (Rủi ro ẩn).
- **Cột "Nhánh" trong bảng SOT:** Cho phép liên kết trực tiếp từng điều khoản đã tra cứu ngược về câu hỏi cụ thể trong Issue Graph (`Nhánh A`, `Nhánh B`,...).
- **Cấu trúc nhật ký OODA theo vòng:** Các vòng nghiên cứu được phân định bằng header rõ ràng `## ═══ OBSERVE — [Vòng N] ═══`, `## ═══ ORIENT — [Vòng N] ═══`,... Giúp việc ghi nối (`Append`) diễn ra tuần tự, không bị đè hay lẫn lộn dữ liệu giữa các vòng lặp.
- **Bảng Next Gap:** Theo dõi sát sao các khoảng trống thông tin còn lại sau mỗi vòng để quyết định dừng hay tiếp tục lặp.

### 2. `legal_report_template.md` (Báo cáo tư vấn chính thức)
- **Đầu ra chuyên nghiệp:** Cung cấp cấu trúc 5 phần hoàn chỉnh gửi cho người dùng, chuyển hóa dữ liệu kỹ thuật từ file phase thành báo cáo đường lối hành động thực tế.
- **Ma trận chấm điểm phương án (1–5) /15:** Trong Phần 3, mỗi phương án giải quyết (Phương án An toàn, Cân bằng, Quyết liệt) được chấm điểm chi tiết theo 3 tiêu chí:
  - **Điểm Pháp lý (1–5):** Mức độ vững chắc của căn cứ luật, không vi phạm điều cấm.
  - **Điểm Rủi ro (1–5):** Khả năng bị xử phạt, bị kiện, tranh chấp hoặc vô hiệu hợp đồng (điểm càng cao rủi ro càng thấp).
  - **Điểm Khả thi (1–5):** Mức độ dễ dàng khi triển khai trên thực tế, thời gian và chi phí.
  - *Tổng điểm /15* kèm bảng so sánh trực quan giúp người dùng ra quyết định sáng suốt.
- **Không bao giờ bỏ sót rủi ro tồn đọng:** Phần 5 tích hợp bảng "Rủi ro còn tồn đọng" lấy trực tiếp từ mục `Next Gap` chưa giải quyết được ở file phase, nêu rõ điều kiện kích hoạt rủi ro và biện pháp giảm thiểu tương ứng.

---

## 🔄 Quy trình Xử lý Toàn diện (Legal OODA Loop Workflow)

```
                       ┌─────────────────────────────────────┐
                       │  Người dùng gửi tình huống/câu hỏi  │
                       └──────────────────┬──────────────────┘
                                          │
                         [Kiểm tra hiệu lực thuần túy?]
                                ┌─────────┴─────────┐
                            Có  │                   │ Không
                                ▼                   ▼
                      ┌──────────────────┐  ┌─────────────────────────────────┐
                      │   §0 FAST PATH   │  │ BƯỚC 0: ĐỊNH DANH & ISSUE GRAPH │
                      │  - Search TVPL   │  │  - Xác định 5 trục tọa độ       │
                      │  - Đọc banner    │  │  - Khởi tạo legal_phase_{N}.md  │
                      │  - Trả lời chat  │  │  - Vẽ Issue Graph (A, B, C, D)  │
                      └──────────────────┘  └────────────────┬────────────────┘
                                                             │
                                                             ▼
                                            ┌─────────────────────────────────┐
                                            │ [OBSERVE] Thu thập SOT Song song│
                                            │  - Tra cứu song song theo nhánh │
                                            │  - Trích NGUYÊN VĂN có tọa độ   │
                                            │  - Ghi nhận trạng thái hiệu lực │
                                            └────────────────┬────────────────┘
                                                             │
                                                             ▼
                                            ┌─────────────────────────────────┐
                                            │ [ORIENT] Xếp bậc & Xử lý Lex   │
                                            │  - Áp dụng Lex Superior         │
                                            │  - Áp dụng Lex Specialis        │
                                            │  - Rà soát mốc thời điểm        │
                                            └────────────────┬────────────────┘
                                                             │
                                                             ▼
                                            ┌─────────────────────────────────┐
                                            │ [DECIDE] Phản biện & Chấm điểm  │
                                            │  - Kiểm tra 3 câu hỏi phản đề   │
                                            │  - Tra cứu bẫy pháp lý thực tế  │
                                            │  - Chấm điểm phương án (/15)    │
                                            └────────────────┬────────────────┘
                                                             │
                                               [Còn Gap & chưa đạt Exit?]
                                                    ┌────────┴────────┐
                                                Có  │                 │ Không (Đủ SOT)
                                                    ▼                 ▼
                                            (Lặp vòng OODA N+1) ┌───────────────────────────┐
                                                                │ [ACT] Đóng gói Báo cáo    │
                                                                │  - Xuất legal_report_*.md │
                                                                │  - Trình bày tóm tắt chat │
                                                                │  - Kèm Disclaimer         │
                                                                └───────────────────────────┘
```

---

## 🧩 Cơ chế Giải quyết Xung đột Pháp luật (Lex Rules)

Khi hai hoặc nhiều văn bản quy phạm pháp luật cùng điều chỉnh một quan hệ nhưng có quy định khác nhau, AI áp dụng nghiêm ngặt theo Điều 156 Luật Ban hành văn bản QPPL 2015 (sửa đổi 2020):

1. **Lex Superior (Thứ bậc hiệu lực):** Văn bản có hiệu lực pháp lý cao hơn có giá trị áp dụng cao hơn (`Hiến pháp > Luật > Nghị định > Thông tư`).
2. **Lex Posterior (Thời điểm ban hành):** Trong các văn bản cùng cơ quan ban hành và cùng hiệu lực, áp dụng văn bản ban hành sau.
3. **Lex Specialis (Luật chung vs. Luật chuyên ngành):** Văn bản chuyên ngành được ưu tiên áp dụng trừ khi văn bản ban hành sau có quy định bãi bỏ hoặc dẫn chiếu khác.

---

## 🛠️ Hướng dẫn Cài đặt & Sử dụng

### 1. Cài đặt vào Hermes Agent / Antigravity
Cấu hình đường dẫn skill trong file `~/.hermes/config.yaml`:
```yaml
skills:
  - path: "D:/Antigravity/luat-su"
```

### 2. Kích hoạt trong hội thoại
Skill tự động kích hoạt khi nhận diện các câu hỏi hoặc tình huống pháp lý:
- *"Hợp đồng mua bán nhà đất công chứng xong thì bên bán qua đời, hợp đồng có hiệu lực không?"*
- *"Công ty muốn đơn phương chấm dứt hợp đồng lao động với nhân viên thử việc thì báo trước bao nhiêu ngày?"*
- *"Hồ sơ đề xuất tài chính ghi giá bằng chữ khác giá bằng số thì xử lý thế nào theo Nghị định 214/2025/NĐ-CP?"*
- *"Luật Đất đai 2024 có hiệu lực từ ngày nào?"* *(Tự động chạy Fast Path)*

---

## ⚠️ Tuyên bố Miễn trừ Trách nhiệm (Legal Disclaimer)

> **LƯU Ý QUAN TRỌNG:**
> Toàn bộ nội dung, phân tích, trích dẫn và đề xuất do Hệ thống Trợ lý AI cung cấp dựa trên việc tra cứu dữ liệu văn bản quy phạm pháp luật công khai tại thời điểm rà soát và **chỉ mang tính chất nghiên cứu, tham khảo sơ bộ**. 
> Trợ lý AI **không** cung cấp dịch vụ hành nghề luật sư theo quy định của Luật Luật sư Việt Nam. Thông tin này **không cấu thành quan hệ luật sư - khách hàng** và **không thay thế** cho ý kiến pháp lý chính thức, văn bản tư vấn có ký tên đóng dấu của luật sư có chứng chỉ hành nghề hoặc quyết định từ cơ quan Nhà nước có thẩm quyền trong từng tình huống thực tế cụ thể.
