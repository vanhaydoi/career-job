# Mode: new-cv — Interactive CV Creation Wizard

Khi user chưa có CV và muốn tạo CV từ đầu. Chạy tự động khi system detect `cv.md` không tồn tại, hoặc user gọi trực tiếp `/career-ops new-cv`.

## Inputs

1. **Không yêu cầu CV có sẵn** — wizard sẽ tạo mới
2. **Profile tại** `config/profile.yml` — sẽ được tạo/cập nhật từ câu trả lời
3. **Themes tại** `templates/themes/themes.yml` — để user chọn style

## Step 1 — Chào & Xác Nhận

```
┌─────────────────────────────────────────────────────────┐
│  🚀 CAREER-OPS — CV CREATION WIZARD                     │
│                                                         │
│  Tôi sẽ giúp bạn tạo CV từ đầu, tối ưu cho vị trí       │
│  bạn đang target.                                       │
│                                                         │
│  Quy trình:                                             │
│  1. Bạn cung cấp JD (link hoặc text)                    │
│  2. Tôi hỏi bạn một số câu về kinh nghiệm               │
│  3. Bạn chọn style CV                                   │
│  4. Tôi tạo CV tailored cho JD đó                       │
│                                                         │
│  Sẵn sàng chưa? (gõ "yes" để bắt đầu)                   │
└─────────────────────────────────────────────────────────┘
```

## Step 2 — Nhập JD

Yêu cầu user cung cấp JD:

```
📋 BƯỚC 1: Nhập Job Description

Bạn có thể:
- Dán link URL của job (VD: https://careers.company.com/jobs/123)
- Hoặc paste trực tiếp text JD vào đây

→ 
```

**Nếu user paste URL:** Sử dụng Playwright (ưu tiên) hoặc WebFetch để extract JD.

**Nếu user paste text:** Dùng trực tiếp.

Sau khi có JD, parse các thông tin:
- Tên công ty
- Tên vị trí (role)
- Tech stack (các công nghệ yêu cầu)
- Level (Fresher/Junior/Mid/Senior)
- Mô tả công việc chính

Hiển thị lại để user xác nhận:

```
✅ Đã phân tích JD:

Công ty: TechCo
Vị trí: Senior Java Developer
Tech stack: Java 17, Spring Boot, Kafka, Docker, Kubernetes, AWS
Level: Senior

Xác nhận đúng? (yes/no)
→ Nếu "no": cho user sửa thủ công
```

## Step 3 — Lưu JD

Sau khi user xác nhận, lưu JD vào `jds/{company-slug}-{role-slug}.md`:

```markdown
# {Role} @ {Company}

**Source:** {URL hoặc "pasted text"}
**Saved:** {YYYY-MM-DD}
**Tech:** {danh sách tech}
**Level:** {level}

## Job Description
{full JD content}
```

## Step 4 — Phỏng Vấn User

### 4.0 — Kiểm tra CV cũ

Trước khi hỏi, kiểm tra `cv-input/converted/`:

```
🔍 Đang kiểm tra CV cũ...

NẾU có file .md trong cv-input/converted/:
┌─────────────────────────────────────────────────────────┐
│  Tôi thấy bạn có CV cũ đã convert:                       │
│                                                         │
│  cv-input/converted/Backend.md                          │
│                                                         │
│  Bạn muốn:                                              │
│  [1] Dùng CV này làm base → tự động điền thông tin       │
│  [2] Tạo CV mới hoàn toàn                               │
│  [3] Xem nội dung CV cũ trước                           │
│                                                         │
│  Gõ số để chọn...                                       │
└─────────────────────────────────────────────────────────┘

Nếu user chọn [1]: Đọc file, extract thông tin, pre-fill form.
Chỉ hỏi những field CÒN THIẾU.

NẾU không có file nào: Tiếp tục phỏng vấn đầy đủ.
```

### 4.1 — Nhóm 1: Danh tính (5 câu)

```
📝 NHÓM 1/4: Danh tính

Q1. Tên đầy đủ của bạn?
→ 

Q2. Email liên hệ?
→ 

Q3. LinkedIn URL? (có thể bỏ qua — gõ "skip")
→ 

Q4. GitHub URL? (có thể bỏ qua)
→ 

Q5. Portfolio / Website cá nhân? (có thể bỏ qua)
→ 
```

### 4.2 — Nhóm 2: Sự nghiệp (6 câu)

```
📝 NHÓM 2/4: Sự nghiệp

Q6. Bạn đang ở đâu? (Thành phố, Quốc gia)
→ 

Q7. Role bạn target? Có thể liệt kê nhiều role.
   VD: Backend Java Developer, Java Software Engineer
→ 

Q8. Level hiện tại của bạn?
   [1] Fresher — mới tốt nghiệp, < 1 năm kinh nghiệm
   [2] Junior — 1-3 năm
   [3] Mid-level — 3-5 năm
   [4] Senior — 5+ năm
→ 

Q9. Mô tả bản thân trong 1 câu (headline):
   VD: "Backend Java Developer with payment gateway & microservices experience"
→ 

Q10. Tech skills của bạn? Liệt kê các công nghệ bạn thành thạo.
    VD: Java, Spring Boot, MySQL, Docker, Git, REST API, Kafka
→ 

Q11. Điểm mạnh nhất của bạn? (superpower)
    Điều gì khiến bạn khác biệt với ứng viên khác?
    VD: "Payment system development", "Microservices architecture"
→ 
```

### 4.3 — Nhóm 3: Kinh nghiệm (3 câu)

```
📝 NHÓM 3/4: Kinh nghiệm

Q12. Kinh nghiệm làm việc — nhập từng job một:

─────────────────────────────────────────────
Job 1:
  Tên công ty? → VNPAY
  Vị trí? → Backend Java Developer
  Thời gian? (VD: 08/2025 - nay) → 08/2025 - nay
  Địa điểm? → Hà Nội
  Mô tả công việc (3-5 ý chính, mỗi ý 1 dòng):
  → Phát triển Core Payment Gateway xử lý thanh toán chéo
  → Xây dựng kiến trúc async với RabbitMQ
  → Tích hợp API đối tác bên thứ ba

  Thêm job nữa? (y/n) → y

Job 2:
  Tên công ty? → Cole
  Vị trí? → Data Engineer
  Thời gian? → 01/2025 - 08/2025
  Địa điểm? → Hà Nội
  Mô tả:
  → Xây dựng ETL pipeline thu thập và làm sạch dữ liệu
  → Xây dựng Dashboard real-time

  Thêm job nữa? (y/n) → n
─────────────────────────────────────────────

Q13. Dự án cá nhân / Portfolio? (có thể bỏ qua)
    Nếu có, kể tên và mô tả ngắn.
    VD: FoodFlow — Hệ thống đặt món với Kafka, Saga Pattern
→ 

Q14. Học vấn & Chứng chỉ?
    VD: ĐH Thương Mại, HTQL Thông tin, 2022-2026 | TOEIC 600
→ 
```

### 4.4 — Nhóm 4: Ưu tiên & Ràng buộc (4 câu)

```
📝 NHÓM 4/4: Ưu tiên

Q15. Mức lương mong muốn? (USD/tháng)
→ 

Q16. Có yêu cầu đặc biệt gì về công việc không?
    VD: "Chỉ làm remote", "Không làm công ty outsource",
    "Không làm Java Swing", "Muốn công ty có product"
    (có thể bỏ qua — gõ "skip")
→ 

Q17. Bạn thích làm dự án về lĩnh vực gì?
    VD: Payment, E-Commerce, Logistics, Healthcare...
    (Dùng để gợi ý project khi chạy gap-fill)
→ 

Q18. CV của bạn nên viết bằng ngôn ngữ nào?
    [1] Tiếng Việt
    [2] English
→ 
```

## Step 5 — Chọn Template Style

```
🎨 BƯỚC 5: Chọn phong cách CV

┌─────────────────────────────────────────────────────────┐
│  [1] Harvard Classic                                     │
│      Serif, đen trắng, truyền thống                      │
│      → Finance, Consulting, Law                          │
│                                                         │
│  [2] MIT Modern                                          │
│      Sans-serif, clean, technical                        │
│      → Tech, Engineering, CS                             │
│                                                         │
│  [3] Stanford Minimal                                    │
│      Tối giản, nhiều white space                         │
│      → Startup, Product, Design                          │
│                                                         │
│  [4] MBA Compact                                         │
│      Dày đặc, chuyên nghiệp                              │
│      → Business, Management                              │
│                                                         │
│  [5] ATS Modern ★ (mặc định)                             │
│      Gradient, hiện đại, tối ưu ATS                      │
│      → All-purpose                                       │
│                                                         │
│  Gõ số để chọn...                                       │
└─────────────────────────────────────────────────────────┘
```

Sau khi chọn, lưu vào `config/profile.yml → cv_preferences.template_style`.

## Step 6 — Sinh CV

### 6.1 — Tạo cv.md

Từ câu trả lời của user, sinh `cv.md` với format chuẩn:

```markdown
# CV — {Full Name}

**Địa chỉ:** {Location}
**Email:** {Email}
**LinkedIn:** {LinkedIn}
**GitHub:** {GitHub}
**Portfolio:** {Portfolio nếu có}

## Tóm tắt chuyên môn
(tự sinh từ skills + headline + JD keywords)

## Kinh nghiệm làm việc
### {Company} — {Location}
**{Role}**
{start} - {end}
- {bullet 1}
- {bullet 2}

## Dự án
(các project user đã nhập, có thể trống)

## Học vấn
- {Degree}, {School} ({years})

## Chứng chỉ
- {Cert}, {Issuer} ({year})

## Kỹ năng
- **Ngôn ngữ:** {list}
- **Framework:** {list}
- **Message Queue:** {list}
- **Cơ sở dữ liệu:** {list}
- **Công cụ:** {list}
```

### 6.2 — Tạo cvs/base.md

Copy `cv.md` vừa tạo thành `cvs/base.md`. Đây là CV gốc — chỉ chứa dữ liệu thật, không keyword injection, không synthetic projects.

### 6.3 — Kiểm tra base.md conflict

Nếu `cvs/base.md` ĐÃ tồn tại:

```
⚠️  cvs/base.md đã tồn tại.

Bạn muốn:
[1] Ghi đè base.md bằng CV mới
[2] Dùng base.md hiện tại → chỉ tạo tailored CV
[3] Backup base.md cũ vào _archive/ rồi tạo mới

Gõ số để chọn...
```

### 6.4 — Tạo tailored CV

Từ `cvs/base.md`, tạo CV tailored cho JD này:

1. Rewrite Professional Summary — inject keywords từ JD
2. Sắp xếp lại Projects theo relevance với JD
3. Sắp xếp lại Experience bullets theo relevance
4. Tạo competency grid từ JD requirements (6-8 keyword phrases)
5. Lưu thành `cvs/{company-slug}-{role-slug}.md`

### 6.5 — Kích hoạt CV

Copy `cvs/{company}-{role}.md` → `cv.md` (active pointer).

### 6.6 — Generate PDF

Gọi `modes/pdf.md` để sinh PDF từ CV vừa tạo. PDF lưu vào `output/cv-{candidate}-{company}-{YYYY-MM-DD}.pdf`.

## Step 7 — Post-Generation

Hiển thị tổng kết và offer các bước tiếp theo:

```
✅ CV ĐÃ SẴN SÀNG!

📄 CV gốc: cvs/base.md
📄 CV tailored: cvs/{company}-{role}.md
📄 CV active: cv.md
📄 PDF: output/cv-{candidate}-{company}-{date}.pdf
📋 JD: jds/{company}-{role}.md

─────────────────────────────────────────────

Bạn có muốn:

[1] Phân tích gap & thêm project synthetic? (gap-fill)
    → Đặc biệt hữu ích nếu CV của bạn còn thiếu kỹ năng

[2] Chuẩn bị câu hỏi phỏng vấn kỹ thuật? (tech-qa)
    → Sinh câu hỏi + câu trả lời cá nhân hóa

[3] Chuẩn bị interview intel đầy đủ? (interview-prep)
    → Company research + STAR stories + tech Q&A

[4] Kết thúc — CV đã đủ dùng

Gõ số để chọn (có thể chọn nhiều, VD: "1,2")
```

**Nếu user chọn [1]:** Chạy `modes/gap-fill.md` với JD và CV hiện tại. Sau đó hỏi lại menu này (vì CV đã thay đổi).

**Nếu user chọn [2]:** Chạy `modes/tech-qa.md`.

**Nếu user chọn [3]:** Chạy `modes/tech-qa.md` + `modes/interview-prep.md`.

**Nếu user chọn [4]:** Kết thúc.

## Ghi Dữ Liệu Vào Profile

Sau khi user trả lời tất cả câu hỏi, cập nhật `config/profile.yml`:

```yaml
candidate:
  full_name: "{Q1}"
  email: "{Q2}"
  location: "{Q6}"
  linkedin: "{Q3}"  # hoặc bỏ qua nếu skip
  github: "{Q4}"    # hoặc bỏ qua nếu skip
  portfolio: "{Q5}" # hoặc bỏ qua nếu skip

target_roles:
  primary: "{Q7 — parse thành list}"
  archetypes:
    - name: "{primary role}"
      level: "{Q8 mapped}"
      fit: "primary"

narrative:
  headline: "{Q9}"
  superpowers: "{Q11 — parse thành list}"

compensation:
  target_range: "${Q15}"
  currency: "USD"

job_constraints:
  preferences: "{Q16 — parse thành list}"

project_generation:
  domains: "{Q17 — parse thành list}"

cv_preferences:
  template_style: "{Step 5 selection}"
  language: "{Q18 mapped: 1=vi, 2=en}"
```

## NEVER

1. Sinh synthetic project trong wizard — đó là việc của gap-fill mode
2. Ghi đè `cvs/base.md` khi user chưa xác nhận
3. Bỏ qua câu hỏi nếu user chưa trả lời — hỏi lại hoặc dùng giá trị mặc định
4. Tạo CV mà không có JD — JD là bắt buộc
5. Tự động submit application — user luôn có quyền quyết định cuối cùng
