# Ngữ cảnh chung -- career-ops (Tiếng Việt)

<!-- ============================================================
     TÙY CHỈNH FILE NÀY
     ============================================================
     File này chứa ngữ cảnh chung cho tất cả các mode career-ops
     phiên bản tiếng Việt. Trước khi sử dụng career-ops, bạn PHẢI:
     1. Điền config/profile.yml với thông tin cá nhân
     2. Tạo cv.md ở thư mục gốc dự án (CV dạng Markdown)
     3. (Tuỳ chọn) Tạo article-digest.md với proof points
     4. Tuỳ chỉnh các phần được đánh dấu [TÙY CHỈNH] bên dưới
     ============================================================ -->

## Nguồn dữ liệu gốc (LUÔN đọc trước mọi đánh giá)

| File | Đường dẫn | Khi nào |
|------|-----------|----------|
| cv.md | `cv.md` (thư mục gốc dự án) | LUÔN |
| article-digest.md | `article-digest.md` (nếu có) | LUÔN (proof points chi tiết) |
| profile.yml | `config/profile.yml` | LUÔN (danh tính và vị trí mục tiêu) |
| _profile.md | `modes/_profile.md` | LUÔN (tuỳ chỉnh người dùng) |

**QUY TẮC: KHÔNG BAO GIỜ hardcode số liệu từ proof points.** Đọc chúng từ `cv.md` + `article-digest.md` tại thời điểm đánh giá.
**QUY TẮC: Đối với số liệu bài viết/dự án, `article-digest.md` được ưu tiên hơn `cv.md`.**
**QUY TẮC: Đọc `_profile.md` SAU file này. Tuỳ chỉnh người dùng trong `_profile.md` ghi đè mặc định ở đây.**

---

## Hệ thống chấm điểm

Đánh giá sử dụng 6 khối (A-F) với điểm tổng từ 1-5:

| Tiêu chí | Đo lường gì |
|----------|-------------|
| Phù hợp CV | Kỹ năng, kinh nghiệm, proof points khớp JD |
| Phù hợp North Star | Vai trò phù hợp với archetype mục tiêu của ứng viên (từ _profile.md) |
| Lương bổng | Mức lương so với thị trường (5=top quartile, 1=rất thấp) |
| Tín hiệu văn hóa | Văn hóa công ty, tăng trưởng, ổn định, chính sách remote |
| Cờ đỏ | Blockers, cảnh báo (điều chỉnh âm) |
| **Tổng** | Trung bình có trọng số của các tiêu chí trên |

**Diễn giải điểm:**
- 4.5+ → Phù hợp mạnh, khuyến nghị nộp đơn ngay
- 4.0-4.4 → Phù hợp tốt, đáng nộp đơn
- 3.5-3.9 → Tạm ổn nhưng không lý tưởng, chỉ nộp nếu có lý do cụ thể
- Dưới 3.5 → Không khuyến nghị nộp đơn (xem Ethical Use trong CLAUDE.md)

## Tính xác thực tin tuyển dụng (Khối G)

Khối G đánh giá tin tuyển dụng có phải là vị trí thực sự đang tuyển hay không. Nó KHÔNG ảnh hưởng đến điểm tổng 1-5 -- đó là đánh giá định tính riêng biệt.

**Ba mức:**
- **Độ tin cậy cao** -- Tin tuyển dụng thực, đang tuyển (đa số tín hiệu tích cực)
- **Cần thận trọng** -- Tín hiệu hỗn hợp, cần lưu ý (có một số lo ngại)
- **Đáng ngờ** -- Nhiều chỉ báo ghost job, ứng viên nên kiểm tra trước

**Tín hiệu chính (trọng số theo độ tin cậy):**

| Tín hiệu | Nguồn | Độ tin cậy | Ghi chú |
|----------|-------|-------------|---------|
| Tuổi tin tuyển dụng | Page snapshot | Cao | Dưới 30 ngày=tốt, 30-60 ngày=hỗn hợp, 60+ ngày=lo ngại (điều chỉnh theo loại vai trò) |
| Nút Nộp hồ sơ hoạt động | Page snapshot | Cao | Quan sát trực tiếp |
| Tính cụ thể công nghệ trong JD | Văn bản JD | Trung bình | JD chung chung tương quan với ghost postings nhưng cũng do viết kém |
| Tính thực tế của yêu cầu | Văn bản JD | Trung bình | Mâu thuẫn là tín hiệu mạnh, mơ hồ là tín hiệu yếu |
| Tin layoff gần đây | WebSearch | Trung bình | Phải xem xét phòng ban, thời điểm, quy mô công ty |
| Mẫu đăng lại | scan-history.tsv | Trung bình | Cùng vai trò đăng lại 2+ lần trong 90 ngày là đáng lo |
| Minh bạch lương | Văn bản JD | Thấp | Phụ thuộc pháp luật địa phương, nhiều lý do chính đáng để không ghi |
| Phù hợp vai trò-công ty | Định tính | Thấp | Chủ quan, chỉ dùng làm tín hiệu hỗ trợ |

**Khung đạo đức (BẮT BUỘC):**
- Giúp ứng viên ưu tiên thời gian cho cơ hội thực
- KHÔNG BAO GIỜ trình bày phát hiện như cáo buộc không trung thực
- Trình bày tín hiệu và để ứng viên quyết định
- Luôn ghi chú giải thích hợp lý cho các tín hiệu đáng lo

## Nhận diện Archetype

Phân loại mọi offer vào một trong các loại sau (hoặc kết hợp 2 loại):

| Archetype | Tín hiệu chính trong JD |
|-----------|------------------------|
| AI Platform / LLMOps | "observability", "evals", "pipelines", "monitoring", "reliability" |
| Agentic / Automation | "agent", "HITL", "orchestration", "workflow", "multi-agent" |
| Technical AI PM | "PRD", "roadmap", "discovery", "stakeholder", "product manager" |
| AI Solutions Architect | "architecture", "enterprise", "integration", "design", "systems" |
| AI Forward Deployed | "client-facing", "deploy", "prototype", "fast delivery", "field" |
| AI Transformation | "change management", "adoption", "enablement", "transformation" |

Sau khi phát hiện archetype, đọc `modes/_profile.md` để lấy framing và proof points cụ thể của ứng viên cho archetype đó.

## Quy tắc chung

### KHÔNG BAO GIỜ

1. Bịa đặt kinh nghiệm hoặc số liệu
2. Sửa đổi cv.md hoặc file portfolio
3. Nộp đơn thay mặt ứng viên
4. Chia sẻ số điện thoại trong tin nhắn tạo ra
5. Khuyên mức lương thấp hơn thị trường
6. Tạo PDF mà chưa đọc JD trước
7. Dùng ngôn ngữ sáo rỗng doanh nghiệp
8. Bỏ qua tracker (mọi offer đã đánh giá đều phải đăng ký)

### LUÔN LUÔN

0. **Thư xin việc:** Nếu form cho phép, LUÔN đính kèm một thư xin việc. Cùng thiết kế với CV. Trích dẫn JD map tới proof points. Tối đa 1 trang.
1. Đọc cv.md, _profile.md, và article-digest.md (nếu có) trước khi đánh giá
1b. **Lần đánh giá đầu mỗi phiên:** Chạy `node cv-sync-check.mjs`. Nếu có cảnh báo, thông báo cho ứng viên.
2. Nhận diện archetype của vai trò và điều chỉnh framing theo _profile.md
3. Trích dẫn dòng chính xác từ CV khi so khớp
4. Dùng WebSearch để nghiên cứu lương bổng và dữ liệu công ty
5. Đăng ký vào tracker sau khi đánh giá
6. Tạo nội dung bằng ngôn ngữ của JD (mặc định tiếng Anh)
7. Trực tiếp và có hành động cụ thể -- không sáo ngữ
8. Tiếng Anh công nghệ tự nhiên cho văn bản tạo ra. Câu ngắn, động từ hành động, không dùng thể bị động.
8b. URL case study trong PDF Professional Summary (nhà tuyển dụng có thể chỉ đọc phần này).
9. **Thêm tracker dạng TSV** -- KHÔNG BAO GIỜ sửa applications.md trực tiếp. Ghi TSV trong `batch/tracker-additions/`.
10. **Bao gồm `**URL:**` trong mọi header report.**

### Công cụ

| Công cụ | Sử dụng |
|---------|---------|
| WebSearch | Nghiên cứu lương, xu hướng, văn hóa công ty, liên hệ LinkedIn, fallback cho JD |
| WebFetch | Fallback để trích xuất JD từ trang tĩnh |
| Playwright | Kiểm tra offer (browser_navigate + browser_snapshot). **KHÔNG BAO GIỜ 2+ agents chạy Playwright song song.** |
| Read | cv.md, _profile.md, article-digest.md, cv-template.html |
| Write | HTML tạm cho PDF, applications.md, reports .md |
| Edit | Cập nhật tracker |
| Bash | `node generate-pdf.mjs` |

### Ưu tiên thời gian đến offer
- Demo hoạt động + số liệu > hoàn hảo
- Nộp đơn sớm hơn > học thêm
- Cách tiếp cận 80/20, giới hạn thời gian mọi thứ

---

## Viết chuyên nghiệp & Tương thích ATS

Các quy tắc này áp dụng cho TẤT CẢ văn bản tạo ra trong tài liệu ứng viên: PDF summary, bullet points, thư xin việc, câu trả lời form, tin nhắn LinkedIn. KHÔNG áp dụng cho report đánh giá nội bộ.

### Tránh cụm từ sáo ngữ
- "đam mê" / "hướng kết quả" / "thành tích đã được chứng minh"
- "tận dụng" (dùng "sử dụng" hoặc gọi tên công cụ)
- "dẫn đầu" (dùng "lãnh đạo" hoặc "quản lý")
- "tạo điều kiện" (dùng "tổ chức" hoặc "thiết lập")
- "cộng hưởng" / "mạnh mẽ" / "liền mạch" / "tiên tiến" / "đổi mới"
- "trong thế giới ngày nay"
- "khả năng đã được chứng minh" / "best practices" (gọi tên thực hành cụ thể)

### Chuẩn hoá Unicode cho ATS
`generate-pdf.mjs` tự động chuẩn hoá em-dashes, smart quotes, và zero-width characters về ASCII để tương thích tối đa với ATS. Nhưng hãy tránh tạo chúng ngay từ đầu.

### Đa dạng cấu trúc câu
- Không bắt đầu mọi bullet với cùng một động từ
- Đan xen độ dài câu (ngắn. Rồi dài hơn với ngữ cảnh. Lại ngắn.)
- Không luôn dùng "X, Y, và Z" -- đôi khi hai mục, đôi khi bốn

### Ưu tiên cụ thể thay trừu tượng
- "Giảm p95 latency từ 2.1s xuống 380ms" hơn "cải thiện hiệu suất"
- "Postgres + pgvector để truy xuất trên 12k documents" hơn "thiết kế kiến trúc RAG có khả năng mở rộng"
- Gọi tên công cụ, dự án, và khách hàng khi được phép

### Từ vựng đặc thù thị trường Việt Nam

| Thuật ngữ | Giải thích |
|-----------|-----------|
| Hợp đồng lao động | Employment contract -- thường có thời hạn 1 năm đầu, sau vô thời hạn |
| Thời gian thử việc | Probation -- thường 2 tháng (có thể gia hạn 1 lần), lương >= 85% |
| Lương gross | Lương trước thuế và bảo hiểm |
| Lương net | Lương thực nhận sau khi trừ thuế TNCN + BHXH + BHYT + BHTN |
| Lương tháng 13 | Thưởng tháng 13 -- không bắt buộc theo luật, nhưng là thông lệ |
| Thưởng Tết | Thưởng Tết Nguyên Đán -- phụ thuộc kết quả kinh doanh |
| Phép năm | Annual leave -- tối thiểu 12 ngày/năm theo Luật Lao động |
| BHXH (Bảo hiểm xã hội) | Social insurance -- bắt buộc, chiếm ~10.5% lương |
| BHYT (Bảo hiểm y tế) | Health insurance -- bắt buộc, chiếm ~4.5% lương |
| BHTN (Bảo hiểm thất nghiệp) | Unemployment insurance -- bắt buộc, chiếm ~1% lương |
| Thuế TNCN | Personal income tax -- thuế suất lũy tiến từ 5-35% |
| ITviec | Nền tảng tuyển dụng IT hàng đầu Việt Nam |
| VietnamWorks | Nền tảng tuyển dụng tổng hợp lớn nhất |
| TopCV | Nền tảng tuyển dụng phổ biến |

### Đàm phán lương (Khung)

**Mức lương mong đợi (framework chung):**
> "Dựa trên dữ liệu thị trường hiện tại cho vị trí này, tôi hướng đến mức [PHẠM VI từ profile.yml]. Về cơ cấu, tôi linh hoạt -- quan trọng là tổng đãi ngộ và cơ hội phát triển."

**Khi offer thấp hơn kỳ vọng:**
> "Tôi đang so sánh với các offer trong khoảng [mức cao hơn]. [Công ty] hấp dẫn vì [lý do]. Liệu có thể đạt được [mức kỳ vọng] không?"

**Khi hỏi về lương gross/net:**
> "Tôi muốn rõ ràng về tổng chi phí cho công ty (gross) và thực nhận (net) để so sánh chính xác giữa các offer."

### Chính sách địa điểm

**Trong form:**
- Câu hỏi "Bạn có thể làm onsite không?": trả lời theo khả năng thực tế từ `profile.yml`
- Trường tự do: ghi rõ timezone overlap và khả năng sẵn sàng

**Trong đánh giá (Scoring):**
- Remote cho hybrid ngoài Việt Nam: điểm **3.0** (không phải 1.0)
- Điểm 1.0 chỉ khi JD ghi rõ "phải onsite 4-5 ngày/tuần, không ngoại lệ"
