# Thư viện Mẫu Phản đề (Adversarial Patterns)

> **Mục đích:** Hỗ trợ pha DECIDE trong Legal OODA Loop. Với mỗi lĩnh vực, liệt kê các bẫy pháp lý đặc thù, ngoại lệ thường bị bỏ sót, và VB phản chiều hay gặp. Agent đọc mục lĩnh vực tương ứng TRƯỚC khi đặt 3 câu hỏi Adversarial.
>
> **Cách dùng:** Trong pha DECIDE, sau khi xác định lĩnh vực từ Issue Graph → đọc mục tương ứng → dùng các pattern dưới đây làm gợi ý cho 3 câu hỏi Adversarial (ngoại lệ / VB phản chiều / án lệ HĐTP).
>
> **Baseline:** 20/07/2026

---

## Cấu trúc mỗi mục

```
### [Tên tình huống phổ biến]
- Bẫy: Điều gì agent dễ bỏ sót khi xây SOT một chiều
- Tra: Cú pháp search Adversarial cụ thể
- VB đối chiếu: VB thường phản chiều kết luận ban đầu
```

---

## 1. Lao động (BLLĐ 2019 + NĐ 145/2020)

### 1.1 Sa thải / Kỷ luật lao động

**Bẫy 1 — Quy trình họp kỷ luật bị bỏ qua:**
BLLĐ Điều 125 cho phép sa thải, nhưng NĐ 145/2020 Điều 70-73 yêu cầu quy trình họp xử lý kỷ luật bắt buộc (thông báo trước 5 ngày làm việc, đủ thành phần, lập biên bản). Sa thải đúng lý do nhưng sai quy trình → vô hiệu.
```
search: site:thuvienphapluat.vn "họp xử lý kỷ luật" "145/2020" "thành phần"
search: site:thuvienphapluat.vn "đơn phương chấm dứt trái pháp luật" "45/2019"
```

**Bẫy 2 — Đối tượng được bảo vệ đặc biệt:**
BLLĐ cấm sa thải NLĐ đang: nghỉ ốm đau/điều dưỡng, nghỉ thai sản, đang nghỉ phép hàng năm, đang thi hành nghĩa vụ công dân (Điều 37). Ngay cả khi có lý do hợp pháp.
```
search: site:thuvienphapluat.vn "cấm" "đơn phương chấm dứt" "thai sản" OR "ốm đau" "45/2019"
```

**Bẫy 3 — Thời hiệu xử lý kỷ luật:**
BLLĐ Điều 123: Thời hiệu xử lý kỷ luật là 6 tháng kể từ ngày xảy ra vi phạm (12 tháng với vi phạm liên quan tài chính, tài sản, tiết lộ bí mật). Nếu quá thời hiệu → không được xử lý dù có bằng chứng.
```
search: site:thuvienphapluat.vn "thời hiệu" "xử lý kỷ luật" "điều 123" "45/2019"
```

---

### 1.2 Chấm dứt hợp đồng lao động

**Bẫy 1 — Thời gian báo trước không đủ:**
BLLĐ Điều 36 K.2: Báo trước ≥45 ngày (HĐLĐ không xác định thời hạn), ≥30 ngày (HĐLĐ xác định thời hạn ≥12 tháng), ≥3 ngày làm việc (HĐLĐ <12 tháng). Nhầm loại HĐ → báo trước sai → trái luật.
```
search: site:thuvienphapluat.vn "báo trước" "ngày" "đơn phương" "điều 36" "45/2019"
```

**Bẫy 2 — Trợ cấp thôi việc vs trợ cấp mất việc:**
Hai khoản khác nhau — BLLĐ Điều 46 (thôi việc: do NLĐ tự nghỉ hoặc đồng thuận) vs Điều 47 (mất việc: do thay đổi cơ cấu/công nghệ). Tính nhầm → thiệt hại một bên.
```
search: site:thuvienphapluat.vn "trợ cấp mất việc" "điều 47" "phương án sử dụng lao động"
```

**Bẫy 3 — HĐ hết hạn nhưng vẫn tiếp tục làm:**
BLLĐ Điều 20 K.2: Nếu hết hạn HĐLĐ xác định thời hạn mà hai bên không ký mới, HĐ tự động chuyển thành không xác định thời hạn sau 30 ngày. Nhiều NSDLĐ không biết điều này.
```
search: site:thuvienphapluat.vn "hết hạn" "tiếp tục làm việc" "điều 20" "45/2019"
```

---

### 1.3 Thử việc

**Bẫy 1 — Thời hạn thử việc vượt mức:**
BLLĐ Điều 25: Tối đa 180 ngày (nhà quản lý DN per LDN/LĐT), 60 ngày (chức danh cần CĐ trở lên), 30 ngày (khác), 6 ngày làm việc (dưới 1 tháng hoặc thời vụ). Tính "2 tháng" dễ vi phạm nếu tháng có 31 ngày.
```
search: site:thuvienphapluat.vn "thử việc" "thời gian" "điều 25" "45/2019"
```

**Bẫy 2 — Không được thử việc lần 2:**
BLLĐ Điều 24 K.3: Mỗi công việc chỉ được thử việc một lần. Nếu đã ký HĐ thử việc rồi cho nghỉ, tuyển lại vào cùng vị trí → không được thử việc lần nữa.

---

### 1.4 Lương & BHXH

**Bẫy 1 — Lương đóng BHXH khác lương thực nhận:**
Luật BHXH 2024 (41/2024/QH15) quy định tiền lương đóng BHXH bao gồm cả phụ cấp và các khoản bổ sung có tính thường xuyên. Nhiều DN tách phụ cấp để giảm đóng BHXH → vi phạm.
```
search: site:thuvienphapluat.vn "tiền lương đóng bảo hiểm" "phụ cấp" "41/2024"
search: site:thuvienphapluat.vn "trốn đóng bảo hiểm" "xử phạt" "2025"
```

**Bẫy 2 — Nợ lương vs trả chậm lương:**
BLLĐ Điều 97: Trả lương chậm quá 15 ngày phải trả thêm lãi suất tiền gửi không kỳ hạn của NH nơi NSDLĐ mở tài khoản. Không phải "nợ lương" đơn thuần — có chế tài cụ thể.

---

## 2. Doanh nghiệp & Đầu tư

### 2.1 Thành lập & Góp vốn

**Bẫy 1 — Ngành nghề kinh doanh có điều kiện:**
Luật Đầu tư 143/2025 Phụ lục IV liệt kê ngành kinh doanh có điều kiện. Thành lập xong nhưng không đáp ứng điều kiện kinh doanh → bị thu hồi GCN hoặc không được hoạt động. Adversarial: kiểm tra ngành nghề đăng ký có trong danh mục không.
```
search: site:thuvienphapluat.vn "ngành nghề kinh doanh có điều kiện" "143/2025" "phụ lục"
search: site:thuvienphapluat.vn "điều kiện kinh doanh" "[tên ngành]" "2025"
```

**Bẫy 2 — Thời hạn góp vốn điều lệ:**
Luật DN 2020 (sửa bởi 76/2025): CTTNHH và CTCP phải góp đủ vốn điều lệ trong 90 ngày từ ngày cấp GCN. Nếu không góp đủ → phải đăng ký giảm vốn hoặc bị xử phạt.
```
search: site:thuvienphapluat.vn "góp vốn" "90 ngày" "vốn điều lệ" "168/2025"
```

**Bẫy 3 — Nhà đầu tư nước ngoài — tỷ lệ sở hữu:**
Một số ngành giới hạn tỷ lệ sở hữu của nhà đầu tư nước ngoài (VD: phân phối bán lẻ ≤49%, viễn thông...). Không kiểm tra trước → M&A bị từ chối.
```
search: site:thuvienphapluat.vn "tỷ lệ sở hữu nước ngoài" "hạn chế" "[ngành]" "143/2025"
```

---

### 2.2 Chuyển nhượng vốn / Cổ phần

**Bẫy 1 — Quyền ưu tiên mua của thành viên còn lại:**
Luật DN 2020 Điều 52 (CTTNHH 2TV): Thành viên muốn chuyển nhượng phải chào bán cho các thành viên còn lại theo tỷ lệ góp vốn trong 30 ngày. Bỏ qua bước này → chuyển nhượng vô hiệu.
```
search: site:thuvienphapluat.vn "quyền ưu tiên mua" "chuyển nhượng" "điều 52" "công ty TNHH"
```

**Bẫy 2 — Hạn chế chuyển nhượng cổ đông sáng lập:**
Luật DN 2020 Điều 120: Cổ đông sáng lập CTCP bị hạn chế chuyển nhượng cổ phần trong 3 năm đầu từ ngày cấp GCN (chỉ được chuyển nhượng cho cổ đông sáng lập khác hoặc người không phải cổ đông sáng lập nếu được ĐHĐCĐ chấp thuận).
```
search: site:thuvienphapluat.vn "cổ đông sáng lập" "hạn chế chuyển nhượng" "3 năm" "điều 120"
```

**Bẫy 3 — Thuế chuyển nhượng vốn:**
Cá nhân chuyển nhượng vốn → TNCN 20% lợi nhuận (hoặc 0.1% doanh thu nếu không xác định được chi phí). Pháp nhân chuyển nhượng → TNDN 20% lợi nhuận. Bên nhận vốn có trách nhiệm khấu trừ.
```
search: site:thuvienphapluat.vn "thuế thu nhập" "chuyển nhượng vốn" "khấu trừ tại nguồn" "2025"
```

---

### 2.3 Phá sản & Giải thể

**Bẫy 1 — Giải thể vs Phá sản — không phải cùng loại:**
Giải thể (Luật DN) là thủ tục hành chính, chỉ được làm khi đã thanh toán hết nợ. Phá sản (Luật 142/2025) là thủ tục tư pháp khi mất khả năng thanh toán. Nhiều DN đang nợ cố giải thể → không được.
```
search: site:thuvienphapluat.vn "điều kiện giải thể" "đã thanh toán" "168/2025"
search: site:thuvienphapluat.vn "mất khả năng thanh toán" "142/2025" "6 tháng"
```

**Bẫy 2 — Trách nhiệm sau phá sản của người quản lý:**
Luật 142/2025: Người quản lý DN có thể bị cấm thành lập/quản lý DN mới trong 1-3 năm nếu phá sản do lỗi của họ.

---

## 3. Đất đai & Bất động sản

### 3.1 Chuyển nhượng QSDĐ

**Bẫy 1 — Điều kiện chuyển nhượng — đất phải "sạch":**
Luật Đất đai 2024 Điều 45: Đất được chuyển nhượng phải có GCN hợp lệ, không có tranh chấp, không bị kê biên, còn trong thời hạn sử dụng. Thiếu 1 điều kiện → chuyển nhượng vô hiệu dù đã công chứng.
```
search: site:thuvienphapluat.vn "điều kiện chuyển nhượng" "điều 45" "31/2024"
search: site:thuvienphapluat.vn "hợp đồng chuyển nhượng vô hiệu" "đất tranh chấp"
```

**Bẫy 2 — Chuyển tiếp Luật Đất đai 2024:**
Luật Đất đai 2024 có hiệu lực 01/08/2024. Tranh chấp/giao dịch phát sinh TRƯỚC ngày này → nhiều điều khoản vẫn áp dụng Luật 2013. Kiểm tra kỹ mốc thời điểm.
```
search: site:thuvienphapluat.vn "điều khoản chuyển tiếp" "31/2024" "luật đất đai"
search: site:thuvienphapluat.vn "tiếp tục thực hiện" "hợp đồng đã ký" "trước ngày" "2024"
```

**Bẫy 3 — Nghĩa vụ tài chính — bên nào chịu:**
Nếu HĐ không ghi rõ → theo luật: bên chuyển nhượng chịu thuế TNCN (2% giá chuyển nhượng), bên nhận chịu lệ phí trước bạ (0.5%). Nhiều bên thỏa thuận miệng → tranh chấp.
```
search: site:thuvienphapluat.vn "thuế thu nhập cá nhân" "chuyển nhượng đất" "2%" "2025"
```

---

### 3.2 Thu hồi đất & Bồi thường

**Bẫy 1 — Đất không đủ điều kiện được bồi thường bằng đất:**
Luật Đất đai 2024 + NĐ 88/2024: Chỉ được bồi thường bằng đất (hoặc nhà) khi đáp ứng điều kiện cụ thể (có GCN, đất ở hợp pháp, diện tích đủ lớn...). Đất không có GCN hoặc đất vi phạm → chỉ được hỗ trợ, không được bồi thường.
```
search: site:thuvienphapluat.vn "không được bồi thường" "điều kiện" "88/2024" "thu hồi đất"
search: site:thuvienphapluat.vn "hỗ trợ" "thay" "bồi thường" "đất không có giấy tờ"
```

**Bẫy 2 — Thời hạn khiếu nại quyết định thu hồi:**
Luật Khiếu nại 2011 Điều 9: 90 ngày kể từ ngày nhận được QĐ hành chính. Nếu quá hạn không có lý do chính đáng → không được khiếu nại.
```
search: site:thuvienphapluat.vn "thời hiệu khiếu nại" "90 ngày" "quyết định hành chính"
```

---

### 3.3 Kinh doanh BĐS

**Bẫy 1 — Bán nhà hình thành trong tương lai — điều kiện tiên quyết:**
Luật KDBĐS 2023 Điều 24: Chủ đầu tư phải có: (1) GCN quyền SDĐ, (2) bảo lãnh ngân hàng, (3) thông báo đủ điều kiện từ Sở Xây dựng TRƯỚC khi ký HĐ. Ký HĐ khi chưa đủ điều kiện → vô hiệu.
```
search: site:thuvienphapluat.vn "điều kiện" "bán nhà ở hình thành trong tương lai" "điều 24" "2023"
search: site:thuvienphapluat.vn "bảo lãnh ngân hàng" "nhà ở hình thành" "bắt buộc"
```

**Bẫy 2 — Giới hạn tiến độ thanh toán:**
Luật KDBĐS 2023: Không được thu quá 70% giá trị HĐ trước khi bàn giao nhà, không quá 95% trước khi cấp GCN. Nhiều CĐT thu vượt → vi phạm, phải hoàn trả.

---

## 4. Dân sự & Hợp đồng

### 4.1 Hợp đồng vô hiệu

**Bẫy 1 — Vô hiệu do giả tạo:**
BLDS 2015 Điều 124: Hợp đồng xác lập giả tạo (VD: ký HĐ mua bán che giấu việc tặng cho để tránh thuế) → vô hiệu. HĐ che giấu (tặng cho) có thể có hiệu lực nếu đủ điều kiện.
```
search: site:thuvienphapluat.vn "giao dịch giả tạo" "điều 124" "BLDS 2015" "vô hiệu"
```

**Bẫy 2 — Thời hiệu yêu cầu tuyên bố vô hiệu:**
BLDS 2015 Điều 132: Thời hiệu khởi kiện tuyên bố HĐ vô hiệu do nhầm lẫn, lừa dối, đe dọa là 2 năm kể từ ngày biết/phải biết. Sau thời hiệu → HĐ được coi là có hiệu lực dù có khuyết tật.
```
search: site:thuvienphapluat.vn "thời hiệu" "yêu cầu tuyên bố vô hiệu" "điều 132" "2 năm"
```

**Bẫy 3 — Hợp đồng thiếu công chứng — không tự động vô hiệu ngay:**
BLDS 2015 Điều 129: Nếu HĐ bắt buộc công chứng mà không công chứng, nhưng một bên đã thực hiện ≥2/3 nghĩa vụ → Tòa có thể công nhận hiệu lực. Không phải luôn vô hiệu.
```
search: site:thuvienphapluat.vn "điều 129" "đã thực hiện" "công nhận hiệu lực" "BLDS"
```

---

### 4.2 Bồi thường thiệt hại ngoài hợp đồng

**Bẫy 1 — Lỗi hỗn hợp giảm mức bồi thường:**
BLDS 2015 Điều 585 K.4: Nếu người bị thiệt hại cũng có lỗi → bồi thường giảm tương ứng. Bên yêu cầu bồi thường toàn bộ khi mình cũng có lỗi → không được chấp nhận.
```
search: site:thuvienphapluat.vn "lỗi hỗn hợp" "giảm bồi thường" "điều 585" "BLDS"
```

**Bẫy 2 — Thời hiệu khởi kiện bồi thường:**
BLDS 2015 Điều 588: Thời hiệu 3 năm từ ngày người bị thiệt hại biết/phải biết quyền lợi bị xâm phạm. Riêng thiệt hại do tính mạng, sức khỏe → không áp dụng thời hiệu.
```
search: site:thuvienphapluat.vn "thời hiệu khởi kiện" "bồi thường thiệt hại" "điều 588"
```

---

## 5. Thuế & Tài chính

### 5.1 Thuế thu nhập

**Bẫy 1 — Cá nhân cư trú vs không cư trú:**
Luật Thuế TNCN: Cá nhân cư trú (≥183 ngày/năm tại VN) chịu thuế toàn bộ thu nhập. Cá nhân không cư trú chỉ chịu thuế thu nhập phát sinh tại VN, thuế suất khác. Xác định sai tư cách → tính thuế sai.
```
search: site:thuvienphapluat.vn "cá nhân cư trú" "183 ngày" "thuế TNCN" "2025"
search: site:thuvienphapluat.vn "cá nhân không cư trú" "thuế suất" "thu nhập tại Việt Nam"
```

**Bẫy 2 — Hoàn thuế — điều kiện bị từ chối:**
Luật Quản lý Thuế 108/2025: Hoàn thuế trước kiểm tra sau áp dụng với DN rủi ro thấp. DN mới thành lập, DN có vi phạm thuế trong 2 năm gần nhất → kiểm tra trước hoàn sau.
```
search: site:thuvienphapluat.vn "hoàn thuế trước" "kiểm tra sau" "điều kiện" "108/2025"
```

---

### 5.2 Đấu thầu (Luật ĐT 2023 & NĐ 214/2025)

**Bẫy 1 — Tiêu chí HSMT hạn chế cạnh tranh:**
Luật ĐT 2023 Điều 44: HSMT không được đặt điều kiện hạn chế nhà thầu tham gia (ưu tiên thương hiệu cụ thể, yêu cầu kinh nghiệm quá cao so với quy mô gói thầu). Nếu bị phát hiện → HSMT vô hiệu, phải làm lại.
```
search: site:thuvienphapluat.vn "hạn chế cạnh tranh" "tiêu chí" "22/2023" "điều 44"
search: site:thuvienphapluat.vn "yêu cầu kỹ thuật" "không phù hợp" "214/2025"
```

**Bẫy 2 — Thông thầu / Liên kết nhà thầu:**
NĐ 214/2025: Các nhà thầu có quan hệ (cùng người đại diện pháp luật, cùng địa chỉ trụ sở, có quan hệ công ty mẹ-con) không được đồng thời tham dự cùng gói thầu. Vi phạm → hủy KQLCNT, cấm tham dự.
```
search: site:thuvienphapluat.vn "liên kết" "nhà thầu" "cùng gói thầu" "214/2025"
search: site:thuvienphapluat.vn "thông thầu" "xử lý" "hình sự" "22/2023"
```

**Bẫy 3 — Điều chỉnh HĐ vượt quy định:**
Luật ĐT 2023 Điều 61: HĐ chỉ được điều chỉnh giá trong các trường hợp cụ thể (trượt giá, thay đổi khối lượng, thay đổi pháp luật). Điều chỉnh ngoài phạm vi → vi phạm, có thể bị coi là thất thoát NSNN.
```
search: site:thuvienphapluat.vn "điều chỉnh hợp đồng" "điều kiện" "điều 61" "22/2023"
```

**Bẫy 4 — Bảo lãnh không đúng mẫu/hết hiệu lực:**
NĐ 214/2025: Bảo lãnh dự thầu và bảo lãnh thực hiện HĐ phải theo mẫu quy định, còn hiệu lực tại thời điểm mở thầu/ký HĐ. Bảo lãnh hết hạn trước thời điểm quy định → HSDT không hợp lệ.
```
search: site:thuvienphapluat.vn "bảo lãnh dự thầu" "mẫu" "hiệu lực" "214/2025"
```

**Bẫy 5 — Kinh nghiệm tương tự bị tính sai:**
NĐ 214/2025: Kinh nghiệm tương tự phải là HĐ đã hoàn thành (không phải đang thực hiện), trong vòng X năm trước thời điểm đóng thầu, có quy mô và tính chất tương đương. Nhà thầu khai sai → bị loại, có thể bị cấm tham dự.
```
search: site:thuvienphapluat.vn "kinh nghiệm tương tự" "hợp đồng tương tự" "điều kiện" "214/2025"
```

**Bẫy 6 — E-HSDT ký số không đúng quy định:**
Đấu thầu qua mạng: HSDT phải được ký số bởi người đại diện theo pháp luật hoặc người được ủy quyền hợp lệ. Ký số bằng chữ ký cá nhân thay vì chữ ký tổ chức → HSDT không hợp lệ.
```
search: site:thuvienphapluat.vn "chữ ký số" "hồ sơ dự thầu" "đại diện hợp pháp" "214/2025"
```

---

## 6. Hành chính & Khiếu nại

### 6.1 Khiếu nại quyết định hành chính

**Bẫy 1 — Thời hiệu khiếu nại lần 1:**
Luật Khiếu nại 2011 Điều 9: 90 ngày kể từ ngày nhận được QĐ hành chính hoặc biết được hành vi hành chính. Đặc biệt: nếu có lý do chính đáng (đau ốm, thiên tai...) thì không tính thời gian đó.
```
search: site:thuvienphapluat.vn "thời hiệu khiếu nại" "90 ngày" "lý do chính đáng" "02/2011"
```

**Bẫy 2 — Khiếu nại lần 2 hoặc khởi kiện — chọn một:**
Luật Khiếu nại 2011 Điều 7: Người khiếu nại có quyền lựa chọn khiếu nại lần 2 HOẶC khởi kiện hành chính ra Tòa — không được làm cả hai đồng thời. Nếu đã nộp đơn khởi kiện thì không được khiếu nại lần 2 và ngược lại.
```
search: site:thuvienphapluat.vn "lựa chọn" "khiếu nại lần hai" "khởi kiện" "không đồng thời"
```

**Bẫy 3 — Thời hiệu khởi kiện hành chính:**
Luật TTHC 2015 Điều 116: 1 năm kể từ ngày nhận được QĐ hành chính hoặc biết được hành vi hành chính. Nếu đã khiếu nại lần 1 thì tính từ ngày nhận QĐ giải quyết khiếu nại lần 1.
```
search: site:thuvienphapluat.vn "thời hiệu khởi kiện" "1 năm" "quyết định hành chính" "93/2015"
```

---

## 7. Giao thoa Lĩnh vực — Bẫy thường gặp khi hai luật cùng áp dụng

### 7.1 Lao động × Hình sự

**Chiếm đoạt tài sản qua quan hệ lao động:**
Hành vi NLĐ lấy tiền công quỹ có thể vừa là vi phạm kỷ luật lao động (→ sa thải) vừa là tội phạm hình sự (→ truy cứu). Hai con đường xử lý độc lập, không loại trừ nhau. Sa thải đúng luật không có nghĩa là thoát khỏi truy cứu hình sự và ngược lại.
```
search: site:thuvienphapluat.vn "vừa xử lý kỷ luật vừa truy cứu hình sự" OR "không loại trừ"
```

### 7.2 Dân sự × Đất đai

**Thừa kế QSDĐ — áp dụng cả BLDS lẫn Luật Đất đai:**
Thừa kế QSDĐ: phần nội dung (ai được hưởng, tỷ lệ) → BLDS 2015. Phần thủ tục (đăng ký, cấp GCN) → Luật Đất đai 2024. Hai VB phải được áp dụng đồng thời, không dùng riêng từng cái.
```
search: site:thuvienphapluat.vn "thừa kế quyền sử dụng đất" "đăng ký" "31/2024" "BLDS"
```

### 7.3 Doanh nghiệp × Thuế

**Giải thể DN nhưng còn nợ thuế:**
Luật DN 2020: DN phải hoàn thành nghĩa vụ thuế trước khi được giải thể. Cơ quan thuế có quyền từ chối xác nhận hoàn thành nghĩa vụ thuế → không thể giải thể. Nhiều DN "giải thể" mà thực ra chỉ bỏ hoạt động → chủ DN vẫn chịu trách nhiệm cá nhân với nợ thuế.
```
search: site:thuvienphapluat.vn "hoàn thành nghĩa vụ thuế" "điều kiện giải thể" "168/2025"
```

---

## Checklist Adversarial nhanh — Trước khi kết luận

Với mọi lĩnh vực, luôn kiểm tra 5 câu này trước khi chuyển sang ACT:

- [ ] **Ngoại lệ:** Có đối tượng/trường hợp nào bị loại khỏi phạm vi áp dụng VB chính không?
- [ ] **Quy trình:** Có đủ quy trình thủ tục bắt buộc không (không chỉ có đủ lý do)?
- [ ] **Thời hiệu:** Còn trong thời hạn xử lý/khiếu nại/khởi kiện không?
- [ ] **Chuyển tiếp:** Mốc thời điểm có rơi vào giai đoạn chuyển tiếp giữa hai VB không?
- [ ] **Giao thoa:** Có VB chuyên ngành khác cùng điều chỉnh tình huống này không?
