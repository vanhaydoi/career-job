# Career-Ops — Hướng Dẫn Sử Dụng

> AI-powered job search pipeline. Đánh giá JD, tạo CV tailored, lấp gap kỹ năng,
> chuẩn bị phỏng vấn — tất cả trong CLI.

---

## Mục Lục

- [PHẦN 1: BẮT ĐẦU](#phần-1-bắt-đầu)
  - [1. Giới Thiệu](#1-giới-thiệu)
  - [2. Cài Đặt](#2-cài-đặt)
  - [3. Onboarding — Lần Đầu Sử Dụng](#3-onboarding--lần-đầu-sử-dụng)
- [PHẦN 2: CORE WORKFLOWS](#phần-2-core-workflows)
  - [4. Tạo CV](#4-tạo-cv)
    - [4.1 Wizard Tạo CV Mới](#41-wizard-tạo-cv-mới-career-ops-new-cv)
    - [4.2 Convert CV Cũ](#42-convert-cv-cũ-career-ops-convert)
    - [4.3 Chọn Template CV](#43-chọn-template-cv)
    - [4.4 Quản Lý Thư Viện CV](#44-quản-lý-thư-viện-cv)
  - [5. Đánh Giá Job](#5-đánh-giá-job)
    - [5.1 Auto-Pipeline](#51-auto-pipeline-career-ops-hoặc-paste-jd)
    - [5.2 Hiểu Báo Cáo Đánh Giá](#52-hiểu-báo-cáo-đánh-giá)
    - [5.3 So Sánh Offer](#53-so-sánh-offer-career-ops-compare)
  - [6. Cải Thiện CV — Gap-Fill](#6-cải-thiện-cv--gap-fill-career-ops-gap-fill)
  - [7. Chuẩn Bị Phỏng Vấn](#7-chuẩn-bị-phỏng-vấn)
    - [7.1 Tech-QA](#71-tech-qa-career-ops-tech-qa)
    - [7.2 Interview-Prep](#72-interview-prep-career-ops-interview-prep)
    - [7.3 Story Bank](#73-story-bank)
  - [8. Nộp Đơn & Theo Dõi](#8-nộp-đơn--theo-dõi)
    - [8.1 Điền Form Ứng Tuyển](#81-điền-form-ứng-tuyển-career-ops-apply)
    - [8.2 Theo Dõi Trạng Thái](#82-theo-dõi-trạng-thái-career-ops-tracker)
    - [8.3 Follow-up](#83-follow-up-career-ops-followup)
    - [8.4 LinkedIn Outreach](#84-linkedin-outreach-career-ops-contact)
- [PHẦN 3: THAM KHẢO](#phần-3-tham-khảo)
  - [9. Tất Cả Lệnh](#9-tất-cả-lệnh)
  - [10. Cấu Hình — profile.yml](#10-cấu-hình--profileyml)
  - [11. Knowledge Base](#11-knowledge-base)
- [PHẦN 4: NÂNG CAO & XỬ LÝ SỰ CỐ](#phần-4-nâng-cao--xử-lý-sự-cố)
  - [12. Tính Năng Nâng Cao](#12-tính-năng-nâng-cao)
  - [13. Xử Lý Sự Cố](#13-xử-lý-sự-cố)
  - [14. Câu Hỏi Thường Gặp](#14-câu-hỏi-thường-gặp)
- [PHẦN 5: PHỤ LỤC](#phần-5-phụ-lục)
  - [15. Phụ Lục](#15-phụ-lục)

---

# PHẦN 1: BẮT ĐẦU

## 1. Giới Thiệu

Career-Ops là một **CLI pipeline tìm việc tích hợp AI**, chạy trên Claude Code hoặc OpenCode. Thay vì bạn phải tự đọc JD, tự chỉnh CV, tự nghiên cứu công ty, Career-Ops tự động hóa toàn bộ pipeline — từ lúc bạn paste một link tuyển dụng cho đến khi có CV tailored, báo cáo đánh giá chi tiết, và câu hỏi phỏng vấn cá nhân hóa.

Hệ thống hoạt động như một **"trợ lý tuyển dụng cá nhân"** chạy ngay trong terminal của bạn. Bạn paste JD, hệ thống sẽ:
- **Đánh giá** mức độ phù hợp giữa CV của bạn và JD (theo thang điểm 1-5, 7 block A-G)
- **Phân tích gap** kỹ năng — những thứ JD yêu cầu mà CV bạn đang thiếu
- **Sinh CV tailored** — rewrite summary, sắp xếp lại project/experience, inject keywords ATS
- **Tạo PDF** chuẩn ATS, sẵn sàng nộp
- **Sinh câu hỏi phỏng vấn** kỹ thuật + behavioral, cá nhân hóa theo CV của bạn
- **Theo dõi** toàn bộ tiến trình ứng tuyển trong tracker

Tất cả dữ liệu của bạn (CV, profile, tracker, reports) được lưu **local** — không gửi đi đâu. Bạn hoàn toàn kiểm soát.

### Career-Ops KHÔNG làm gì

Career-Ops tuân thủ các nguyên tắc đạo đức nghiêm ngặt:

- **KHÔNG tự động nộp đơn.** Hệ thống có thể điền form, draft câu trả lời, nhưng LUÔN dừng trước nút Submit. Bạn là người quyết định cuối cùng.
- **KHÔNG spam.** Mục tiêu là chất lượng, không phải số lượng. 5 đơn chất lượng > 50 đơn generic.
- **KHÔNG bịa kinh nghiệm.** Synthetic projects (dự án mẫu để lấp gap) được sinh theo 6 believability rules nghiêm ngặt: scale phù hợp level, không trùng domain với project thật, có "vết" thực tế, mạch logic, giới hạn tech stack, và bullet đồng nhất.
- **KHÔNG gửi dữ liệu ra ngoài.** Mọi thứ chạy local.

### Kiến Trúc Hệ Thống

```
┌─────────────────────────────────────────────────────────────────────┐
│                        CAREER-OPS SYSTEM                             │
│                                                                      │
│  ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌───────────────┐ │
│  │  User    │    │  Claude  │    │ Playwright│    │  Zero-Token   │ │
│  │  Input   │───▶│  Code /  │───▶│  Browser  │    │  Scanner      │ │
│  │ (JD/URL) │    │  OpenCode│    │  (fetch)  │    │  (scan.mjs)   │ │
│  └──────────┘    └────┬─────┘    └──────────┘    └───────┬───────┘ │
│                       │                                   │         │
│                       ▼                                   ▼         │
│  ┌─────────────────────────────────────────────────────────────┐   │
│  │                     MODE ROUTER                              │   │
│  │  auto-pipeline │ oferta │ pdf │ gap-fill │ tech-qa │ ...     │   │
│  └─────────────────────────────────────────────────────────────┘   │
│           │              │              │              │            │
│           ▼              ▼              ▼              ▼            │
│  ┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────────┐   │
│  │ Reports  │   │  PDFs    │   │  Tracker │   │  Interview   │   │
│  │ (A-G)    │   │ (output) │   │  (data)  │   │  Prep        │   │
│  └──────────┘   └──────────┘   └──────────┘   └──────────────┘   │
│                                                                      │
│  ┌─────────────────────────────────────────────────────────────┐   │
│  │                   DATA LAYERS                                │   │
│  │  User Layer (KHÔNG auto-update):  cv.md, profile.yml,       │   │
│  │    _profile.md, tracker, reports, story-bank, portals.yml   │   │
│  │  System Layer (auto-updatable): modes/*, knowledge/roles/*, │   │
│  │    templates/*, scripts, fonts                               │   │
│  └─────────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 2. Cài Đặt

### Yêu Cầu

| Thành phần | Phiên bản tối thiểu |
|-------------|---------------------|
| **Node.js** | 18+ |
| **Claude Code** hoặc **OpenCode** | Phiên bản mới nhất |
| **Git** | 2.0+ |
| **npm** | 9+ |

### Cài Đặt Từng Bước

**Bước 1: Clone repository**

```bash
git clone https://github.com/anomalyco/career-ops.git
cd career-ops
```

**Bước 2: Cài dependencies**

```bash
npm install
```

**Bước 3: Cài Playwright browser**

```bash
npx playwright install chromium
```

**Bước 4: Kiểm tra cài đặt**

```bash
node doctor.mjs
```

Kết quả mong đợi:

```
🔍 CAREER-OPS DOCTOR
──────────────────────────────────────────
✅ Node.js >= 18 (v20.11.0)
✅ Dependencies installed
✅ Playwright chromium installed
✅ Required directories exist
✅ Templates found
✅ Knowledge base loaded (14 roles)
✅ Fonts available
──────────────────────────────────────────
✅ All checks passed. Career-Ops is ready.
```

**Bước 5: (Tuỳ chọn) Cài OpenCode slash commands**

Nếu bạn dùng OpenCode, các lệnh slash được định nghĩa sẵn trong `.opencode/commands/`. Không cần cấu hình thêm.

### Cài Đặt Claude Code

Nếu dùng Claude Code, ensure `claude` CLI đã được cài đặt và xác thực. Các lệnh được định nghĩa qua skill system trong `.claude/skills/career-ops/`.

---

## 3. Onboarding — Lần Đầu Sử Dụng

Khi bạn mở Career-Ops lần đầu, hệ thống sẽ tự động phát hiện các file còn thiếu và hướng dẫn bạn từng bước. Đây là flow onboarding:

```
┌─────────────────────────────────────────────────────────────────┐
│                     ONBOARDING FLOW                              │
│                                                                  │
│  ┌─────────┐    ┌─────────┐    ┌─────────┐    ┌─────────┐      │
│  │ Bước 1  │    │ Bước 2  │    │ Bước 3  │    │ Bước 4  │      │
│  │ Tạo CV  │───▶│ Điền    │───▶│ Thiết   │───▶│ Sẵn     │      │
│  │ (wizard)│    │ Profile │    │ lập     │    │ sàng!   │      │
│  │         │    │         │    │ Portals │    │         │      │
│  └─────────┘    └─────────┘    └─────────┘    └─────────┘      │
│       │              │              │              │            │
│       ▼              ▼              ▼              ▼            │
│  cv.md           profile.yml    portals.yml    Ready to use     │
│  cvs/base.md     _profile.md                    /career-ops     │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

### Bước 1: Tạo CV

Hệ thống detect `cv.md` chưa tồn tại → tự động đề xuất chạy new-cv wizard:

> "Tôi chưa có CV của bạn. Bạn có thể:
> 1. Paste CV của bạn ở đây, tôi sẽ convert sang markdown
> 2. Paste LinkedIn URL, tôi sẽ extract thông tin chính
> 3. Để tôi phỏng vấn bạn và draft CV
>
> Bạn chọn cách nào?"

Chi tiết wizard xem [Mục 4.1](#41-wizard-tạo-cv-mới-career-ops-new-cv).

### Bước 2: Điền Profile

Hệ thống copy `config/profile.example.yml` → `config/profile.yml` và hỏi:

> "Tôi cần một vài thông tin để cá nhân hóa hệ thống:
> - Họ tên đầy đủ và email
> - Địa điểm và múi giờ
> - Role bạn đang target (VD: 'Junior Java Backend Developer')
> - Mức lương mong muốn
>
> Tôi sẽ điền mọi thứ cho bạn."

Chi tiết từng field xem [Mục 10](#10-cấu-hình--profileyml).

### Bước 3: Thiết Lập Portals

Hệ thống copy `templates/portals.example.yml` → `portals.yml` với 45+ công ty được cấu hình sẵn:

> "Tôi sẽ thiết lập job scanner với 45+ công ty. Bạn muốn tôi tùy chỉnh từ khóa tìm kiếm cho role của bạn không?"

### Bước 4: Sẵn Sàng!

Sau khi tất cả file đã sẵn sàng:

> "Bạn đã sẵn sàng! Bây giờ bạn có thể:
> - Paste link JD để đánh giá
> - Chạy `/career-ops scan` để quét portal tìm việc mới
> - Chạy `/career-ops` để xem tất cả lệnh
>
> Mọi thứ đều có thể tùy chỉnh — chỉ cần bảo tôi.
>
> Tip: Có portfolio cá nhân sẽ cải thiện đáng kể cơ hội của bạn."

---

# PHẦN 2: CORE WORKFLOWS

## 4. Tạo CV

### 4.1 Wizard Tạo CV Mới (`/career-ops new-cv`)

Wizard 7 bước giúp bạn tạo CV từ con số 0, tối ưu cho một JD cụ thể.

```
┌──────────────────────────────────────────────────────────────┐
│                  NEW-CV WIZARD FLOW                            │
│                                                               │
│  ┌────────┐  ┌────────┐  ┌────────┐  ┌────────┐  ┌────────┐ │
│  │ Step 1 │  │ Step 2 │  │ Step 3 │  │ Step 4 │  │ Step 5 │ │
│  │ Chào & │─▶│ Nhập   │─▶│ Lưu JD │─▶│ Phỏng  │─▶│ Chọn   │ │
│  │ Xác    │  │ JD     │  │        │  │ vấn    │  │ Theme  │ │
│  │ nhận   │  │        │  │        │  │ User   │  │        │ │
│  └────────┘  └────────┘  └────────┘  └────────┘  └────────┘ │
│                                                      │       │
│  ┌────────┐  ┌────────┐                              │       │
│  │ Step 7 │◀─│ Step 6 │◀─────────────────────────────┘       │
│  │ Tổng   │  │ Sinh   │                                       │
│  │ kết    │  │ CV     │                                       │
│  └────────┘  └────────┘                                       │
└──────────────────────────────────────────────────────────────┘
```

#### Walkthrough Đầy Đủ

Giả sử Nguyễn Văn A — Junior Java Backend Developer, lần đầu dùng Career-Ops.

**Step 1 — Chào & Xác Nhận**

```
Bạn gõ: /career-ops new-cv

System:
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

Bạn gõ: yes
```

**Step 2 — Nhập JD**

```
System:
📋 BƯỚC 1: Nhập Job Description

Bạn có thể:
- Dán link URL của job (VD: https://careers.company.com/jobs/123)
- Hoặc paste trực tiếp text JD vào đây

→

Bạn paste:
https://careers.techco.com/jobs/senior-java-developer

System:
✅ Đã phân tích JD:

Công ty: TechCo
Vị trí: Senior Java Developer
Tech stack: Java 17, Spring Boot, Kafka, Docker, Kubernetes, AWS
Level: Senior

Xác nhận đúng? (yes/no)

Bạn gõ: yes
```

**Step 3 — Lưu JD**

```
System:
💾 Đã lưu JD vào jds/techco-senior-java-developer.md
```

**Step 4 — Phỏng Vấn User (4 nhóm, 18 câu)**

```
System:
🔍 Đang kiểm tra CV cũ...
Không tìm thấy CV cũ nào. Tiến hành phỏng vấn đầy đủ.

📝 NHÓM 1/4: Danh tính

Q1. Tên đầy đủ của bạn?
→ Nguyễn Văn A

Q2. Email liên hệ?
→ anh.nguyen@email.com

Q3. LinkedIn URL? (có thể bỏ qua — gõ "skip")
→ linkedin.com/in/nguyenvana

Q4. GitHub URL? (có thể bỏ qua)
→ github.com/nguyenvana

Q5. Portfolio / Website cá nhân? (có thể bỏ qua)
→ skip

────────────────────────────────────

📝 NHÓM 2/4: Sự nghiệp

Q6. Bạn đang ở đâu? (Thành phố, Quốc gia)
→ Hà Nội, Việt Nam

Q7. Role bạn target? Có thể liệt kê nhiều role.
   VD: Backend Java Developer, Java Software Engineer
→ Junior Java Backend Developer, Java Software Engineer

Q8. Level hiện tại của bạn?
   [1] Fresher — mới tốt nghiệp, < 1 năm kinh nghiệm
   [2] Junior — 1-3 năm
   [3] Mid-level — 3-5 năm
   [4] Senior — 5+ năm
→ 2

Q9. Mô tả bản thân trong 1 câu (headline):
   VD: "Backend Java Developer with payment gateway & microservices experience"
→ "Junior Java Developer with hands-on experience in payment systems & REST APIs"

Q10. Tech skills của bạn? Liệt kê các công nghệ bạn thành thạo.
     VD: Java, Spring Boot, MySQL, Docker, Git, REST API, Kafka
→ Java, Spring Boot, MySQL, PostgreSQL, REST API, Git, Docker, JUnit

Q11. Điểm mạnh nhất của bạn? (superpower)
     Điều gì khiến bạn khác biệt với ứng viên khác?
→ Payment system integration, Clean code discipline

────────────────────────────────────

📝 NHÓM 3/4: Kinh nghiệm

Q12. Kinh nghiệm làm việc — nhập từng job một:

─────────────────────────────────────────────
Job 1:
  Tên công ty? → VNPAY
  Vị trí? → Backend Java Developer
  Thời gian? (VD: 08/2025 - nay) → 08/2025 - nay
  Địa điểm? → Hà Nội
  Mô tả công việc (3-5 ý chính, mỗi ý 1 dòng):
  → Phát triển Core Payment Gateway xử lý thanh toán chéo ngân hàng
  → Xây dựng kiến trúc async với RabbitMQ cho xử lý giao dịch
  → Tích hợp API đối tác bên thứ ba (Momo, ZaloPay)
  → Viết unit test với JUnit, đạt coverage 85%

  Thêm job nữa? (y/n) → y

Job 2:
  Tên công ty? → Cole
  Vị trí? → Data Engineer Intern
  Thời gian? → 01/2025 - 08/2025
  Địa điểm? → Hà Nội
  Mô tả:
  → Xây dựng ETL pipeline thu thập và làm sạch dữ liệu sản phẩm
  → Xây dựng Dashboard real-time với Metabase
  → Viết SQL query phức tạp cho báo cáo business

  Thêm job nữa? (y/n) → n
─────────────────────────────────────────────

Q13. Dự án cá nhân / Portfolio? (có thể bỏ qua)
→ FoodFlow — Hệ thống đặt món online với Kafka, Saga Pattern, Redis

Q14. Học vấn & Chứng chỉ?
→ ĐH Thương Mại, Hệ thống Thông tin Quản lý, 2022-2026
   TOEIC 650

────────────────────────────────────

📝 NHÓM 4/4: Ưu tiên

Q15. Mức lương mong muốn? (USD/tháng)
→ 800

Q16. Có yêu cầu đặc biệt gì về công việc không?
→ Không làm công ty outsource, muốn công ty có product

Q17. Bạn thích làm dự án về lĩnh vực gì?
→ Payment, E-Commerce, Logistics

Q18. CV của bạn nên viết bằng ngôn ngữ nào?
     [1] Tiếng Việt
     [2] English
→ 2
```

**Step 5 — Chọn Template Style**

```
System:
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

Bạn gõ: 2  (chọn MIT Modern — hợp với dân tech)
```

**Step 6 — Sinh CV**

Hệ thống tự động:
1. Tạo `cv.md` với format chuẩn (Summary, Experience, Projects, Education, Skills)
2. Copy → `cvs/base.md` (CV gốc, chỉ chứa dữ liệu thật)
3. Tạo tailored CV tại `cvs/techco-senior-java-developer.md`
4. Kích hoạt tailored CV làm `cv.md` hiện tại
5. Generate PDF

**Step 7 — Tổng Kết**

```
System:
✅ CV ĐÃ SẴN SÀNG!

📄 CV gốc: cvs/base.md
📄 CV tailored: cvs/techco-senior-java-developer.md
📄 CV active: cv.md
📄 PDF: output/cv-nguyen-van-a-techco-2026-05-15.pdf
📋 JD: jds/techco-senior-java-developer.md

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

### 4.2 Convert CV Cũ (`/career-ops convert`)

Bạn đã có CV cũ ở định dạng PDF, DOCX, ảnh, LinkedIn, hoặc text? Convert mode sẽ chuyển đổi sang format markdown chuẩn của Career-Ops.

**Định dạng hỗ trợ:**

| Định dạng | Cách nhận diện | Phương pháp extract |
|-----------|---------------|---------------------|
| `.pdf` | File extension | Read tool (native PDF) |
| `.docx` | File extension | Read tool hoặc minimax-docx skill |
| `.png`, `.jpg` | File extension | Vision analysis (OCR + cấu trúc) |
| `.txt` | File extension | Đọc trực tiếp |
| LinkedIn URL | URL chứa `linkedin.com` | WebFetch |
| HTML URL | URL | WebFetch |

**Walkthrough: Convert PDF → Markdown**

```
Bạn gõ: /career-ops convert cv-input/my-old-cv.pdf

System:
CV Conversion Complete
━━━━━━━━━━━━━━━━━━━━━━━━
Source: cv-input/my-old-cv.pdf
Format: pdf
Language: VI
Output: cv-input/converted/my-old-cv.md

Sections found: Header, Summary, Experience, Education, Skills
Sections missing: Projects
Issues flagged: 3
  - ⚠️ Missing dates on experience — bạn có thể thêm sau
  - ⚠️ No metrics/numbers in bullets — gợi ý thêm số liệu
  - 💡 Projects section trống — cân nhắc thêm personal projects

→ Review cv-input/converted/my-old-cv.md
→ Copy sang cv.md khi sẵn sàng: cp cv-input/converted/my-old-cv.md cv.md
```

**Lưu ý:** Converted CV trong `cv-input/converted/` sẽ được new-cv wizard tự động phát hiện. Nếu sau này bạn chạy `/career-ops new-cv`, wizard sẽ offer pre-fill từ các file này.

### 4.3 Chọn Template CV

Career-Ops có 5 theme CV được định nghĩa trong `templates/themes/themes.yml`. Mỗi theme kiểm soát fonts, màu sắc, layout, và typography.

| Theme | Font | Màu chính | Layout | Phù hợp ngành |
|-------|------|-----------|--------|---------------|
| **Harvard Classic** | Times New Roman, Georgia | Đen trắng | Căn giữa, serif | Finance, Consulting, Law |
| **MIT Modern** | Helvetica Neue, Arial | #1a1a1a | Căn trái, sans-serif | Tech, Engineering, CS |
| **Stanford Minimal** | Inter, Source Sans Pro | #2d2d2d, accent đỏ | Tối giản, white space | Startup, Product, Design |
| **MBA Compact** | Calibri, Lato | #0a0a0a | Dày đặc, chuyên nghiệp | Business, Management |
| **ATS Modern** ★ | Space Grotesk, DM Sans | Gradient xanh-tím | Hiện đại, gradient | All-purpose (mặc định) |

**Cách chọn theme:**
- Trong new-cv wizard: chọn ở Step 5
- Trong profile.yml: set `cv_preferences.template_style` (giá trị: `harvard`, `mit`, `stanford`, `mba`, `ats`)

**Ví dụ đổi theme sau khi đã cài đặt:**

```yaml
# config/profile.yml
cv_preferences:
  template_style: "stanford"
  language: "en"
```

### 4.4 Quản Lý Thư Viện CV

Thư mục `cvs/` chứa toàn bộ thư viện CV của bạn:

```
cvs/
├── base.md                              ← CV gốc (chỉ dữ liệu thật)
├── techco-senior-java-developer.md      ← Tailored cho TechCo
├── vnpay-backend-developer.md           ← Tailored cho VNPAY
├── fpt-java-fresher.md                  ← Tailored cho FPT
└── _archive/                            ← CV cũ đã archive
    └── old-company-2025.md
```

- **`base.md`**: CV gốc, chỉ chứa dữ liệu thật — không keyword injection, không synthetic projects. Đây là source of truth.
- **Tailored CVs**: Mỗi file là CV được tối ưu cho một JD cụ thể. Rewrite summary, sắp xếp lại project, inject keywords.
- **`cv.md`** tại project root: Luôn là bản copy của CV đang active (pointer).

**Switch CV — `/career-ops cv-switch`**

```
Bạn gõ: /career-ops cv-switch

System:
┌─────────────────────────────────────────────────────────┐
│  📂 CV LIBRARY — Chọn CV để kích hoạt                    │
│                                                         │
│  ┌──────────────────────────────────────────────────┐  │
│  │  [1] base.md                      (CV gốc)        │  │
│  │  [2] techco-senior-java.md    ★ active             │  │
│  │  [3] vnpay-backend-dev.md        (15/05/2026)     │  │
│  │  [4] fpt-java-fresher.md         (10/05/2026)     │  │
│  └──────────────────────────────────────────────────┘  │
│                                                         │
│  CV đang active: techco-senior-java.md                  │
│                                                         │
│  Gõ số để chọn, hoặc "q" để thoát...                   │
└─────────────────────────────────────────────────────────┘

Bạn gõ: 3

System:
✅ Đã kích hoạt: vnpay-backend-dev.md

cv.md hiện tại là bản sao của cvs/vnpay-backend-dev.md

💡 Gợi ý:
- CV này có thể chưa tailored cho JD cụ thể.
  Paste JD để tôi đánh giá và tạo CV tailored.
- Hoặc chạy /career-ops gap-fill để phân tích gap.
```

---

## 5. Đánh Giá Job

### 5.1 Auto-Pipeline (`/career-ops` hoặc paste JD)

Đây là tính năng **cốt lõi** của Career-Ops. Bạn paste JD (text hoặc URL), hệ thống tự động chạy toàn bộ pipeline 7 bước:

```
┌──────────────────────────────────────────────────────────────────┐
│                      AUTO-PIPELINE FLOW                            │
│                                                                   │
│  ┌────────┐  ┌────────┐  ┌────────┐  ┌────────┐  ┌────────┐     │
│  │ Step 0 │  │ Step 1 │  │ Step 2 │  │ Step 3 │  │ Step 4 │     │
│  │ Extract│─▶│ Đánh   │─▶│ Gap    │─▶│ Lưu    │─▶│ Gen    │     │
│  │ JD     │  │ giá A-G│  │ Gate   │  │ Report │  │ PDF    │     │
│  └────────┘  └────────┘  └────────┘  └────────┘  └────────┘     │
│                                                │                  │
│  ┌────────┐  ┌────────┐  ┌────────┐           │                  │
│  │ Step 7 │◀─│ Step 6 │◀─│ Step 5 │◀──────────┘                  │
│  │ Offer  │  │ Update │  │ Draft  │                                │
│  │ Prep   │  │ Tracker│  │ Apply  │                                │
│  └────────┘  └────────┘  └────────┘                                │
└──────────────────────────────────────────────────────────────────┘
```

#### Walkthrough

```
Bạn paste JD URL (hoặc text):
/career-ops https://careers.techco.com/jobs/senior-java-developer

System bắt đầu pipeline:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[Step 0] Đang extract JD từ URL...
✅ Đã lấy JD thành công qua Playwright.
   TechCo — Senior Java Developer
   Tech: Java 17, Spring Boot, Kafka, Docker, K8s, AWS, PostgreSQL, JUnit, CI/CD

[Step 1] Đánh giá A-G...

# Đánh Giá: TechCo — Senior Java Developer

**Ngày:** 2026-05-15
**Score:** 3.2/5
**Legitimacy:** High Confidence

---

## A) Tóm tắt Role

| Field | Value |
|-------|-------|
| Archetype | AI Platform / Backend |
| Domain | Platform — Payment Infrastructure |
| Function | Build |
| Seniority | Senior |
| Remote | Hybrid (Hà Nội) |
| Team size | 8-12 engineers |
| **TL;DR** | Xây dựng và vận hành hệ thống thanh toán phân tán trên Java/Spring Boot với Kafka, triển khai trên AWS EKS. |

## B) Match với CV

| JD Requirement | CV Evidence | Match |
|----------------|-------------|-------|
| Java 17 | ✅ Có — VNPAY Core Payment Gateway, FoodFlow | strong |
| Spring Boot | ✅ Có — Tất cả project | strong |
| Kafka | ⚠️ Có trong FoodFlow, nhưng ít chi tiết | medium |
| Docker | ✅ Có — Sử dụng trong tất cả project | strong |
| Kubernetes | ❌ Không có | missing |
| AWS | ❌ Không có | missing |
| PostgreSQL | ✅ Có — VNPAY, FoodFlow | strong |
| JUnit | ✅ Có — VNPAY (85% coverage) | strong |
| CI/CD (Jenkins) | ❌ Không có | missing |

**Đánh giá project hiện có:**

| # | Project | Score | Action |
|---|---------|-------|--------|
| 1 | Core Payment Gateway (VNPAY) | 85% | KEEP |
| 2 | FoodFlow | 72% | IMPROVE |
| 3 | ETL Pipeline (Cole) | 30% | REPLACE |

**Match tổng: 62%** — Dưới ngưỡng, có gap cần lấp.

---

[Step 2] Gap Gate...
Match CV với JD này là 62%. Bạn có gaps trong: Kubernetes, AWS, CI/CD, Kafka (yếu).
Bạn có muốn tôi chạy gap-fill mode để phân tích gaps và sinh projects synthetic?
(yes/no)

→ (Xem tiếp mục 6 để biết gap-fill hoạt động thế nào)

[Step 3] Đã lưu report: reports/042-techco-2026-05-15.md

[Step 4] Đang generate PDF...
✅ PDF: output/cv-nguyen-van-a-techco-2026-05-15.pdf (2 trang, 85% keyword coverage)

[Step 5] Score < 4.5 — skip draft application answers

[Step 6] Đã cập nhật tracker:
| 42 | 2026-05-15 | TechCo | Senior Java Developer | 3.2/5 | Evaluated | ✅ | ✅ |

[Step 7] Bạn có muốn tôi chuẩn bị câu hỏi phỏng vấn không?
- tech-qa: Câu hỏi kỹ thuật cá nhân hóa
- full: Tech Q&A + Company research + STAR stories
- no: Bỏ qua
```

### 5.2 Hiểu Báo Cáo Đánh Giá

Mỗi báo cáo gồm 7 block (A-G), lưu trong `reports/{###}-{company-slug}-{YYYY-MM-DD}.md`.

#### Block A — Tóm Tắt Role

Bảng tổng quan nhanh về vị trí: archetype, domain, function, seniority, remote policy, team size, TL;DR. Giúp bạn quyết định trong 10 giây xem role này có đáng đọc tiếp không.

#### Block B — Match với CV

Đây là block quan trọng nhất. Hệ thống:

1. **So sánh từng JD requirement** với CV của bạn. Mỗi skill được gán: `strong`, `medium`, `weak`, hoặc `missing`.
2. **Đánh giá từng project** trong CV theo 6 tiêu chí (Tech match 40%, Domain relevance 20%, Description depth 15%, Recency 10%, Role alignment 10%, Public link 5%). Điểm ≥80% → KEEP, 50-79% → IMPROVE, <50% → REPLACE.
3. **Phân tích gap** — mỗi gap được đánh giá: hard blocker hay nice-to-have? Có kinh nghiệm liên quan không? Có thể lấp bằng project portfolio không? Plan mitigation cụ thể.

#### Block C — Level & Chiến Lược

- Level detect từ JD vs level hiện tại của bạn
- Plan "bán mình" không nói dối: câu cụ thể để position kinh nghiệm
- Plan nếu bị downlevel: chấp nhận không, negotiate thế nào

#### Block D — Lương & Thị Trường

WebSearch để tìm:
- Mức lương hiện tại cho role này (Glassdoor, Levels.fyi, ITviec)
- Reputation về lương của công ty
- Xu hướng demand của role

#### Block E — Plan Cá Nhân Hóa

Bảng các thay đổi cụ thể cho CV và LinkedIn:
- Section nào cần sửa → sửa thành gì → tại sao
- Top 5 thay đổi CV + Top 5 thay đổi LinkedIn

#### Block F — Plan Phỏng Vấn

- 6-10 STAR+R stories map với JD requirements
- Mỗi story: Situation, Task, Action, Result, **Reflection** (bài học rút ra)
- 1 case study recommended
- Red-flag questions và cách trả lời

#### Block G — Posting Legitimacy (Tính Xác Thực Của Tin)

Phân tích xem JD này có phải là tin thật không:
- **Freshness**: Ngày đăng, trạng thái nút Apply
- **Description quality**: JD có cụ thể không? Có mâu thuẫn không?
- **Company hiring signals**: Có layoff gần đây không? Có hiring freeze không?
- **Reposting detection**: Role này đã được đăng lại bao nhiêu lần?

Kết quả: **High Confidence** / **Proceed with Caution** / **Suspicious**

Block G KHÔNG ảnh hưởng đến score 1-5 — đây là đánh giá riêng để bạn ưu tiên thời gian.

### 5.3 So Sánh Offer (`/career-ops compare`)

Khi bạn có nhiều offer hoặc nhiều JD đã đánh giá, compare mode giúp so sánh và xếp hạng:

```
Bạn gõ: /career-ops compare

System:
So sánh các offer đã đánh giá...

| # | Company | Role | Score | Comp | Remote | Legitimacy |
|---|---------|------|-------|------|--------|------------|
| 1 | TechCo | Senior Java Dev | 3.2/5 | ~$1200 | Hybrid | High |
| 2 | VNPAY | Backend Developer | 4.5/5 | ~$800 | On-site | High |
| 3 | FPT | Java Fresher | 3.8/5 | ~$500 | Hybrid | Caution |

🏆 Top pick: VNPAY — Backend Developer (4.5/5)
   - Match CV tốt nhất, đúng tech stack
   - Công ty product, đúng tiêu chí của bạn
   - Cân nhắc: on-site, lương khởi điểm thấp hơn TechCo
```

---

## 6. Cải Thiện CV — Gap-Fill (`/career-ops gap-fill`)

Gap-fill là tính năng **độc đáo nhất** của Career-Ops: phân tích gap giữa CV và JD, sau đó sinh **synthetic projects** (dự án mẫu) để lấp gap kỹ năng — tuân thủ 6 believability rules nghiêm ngặt.

### Decision Tree

```
┌──────────────────────────────────────────────────────────┐
│                    GAP-FILL DECISION TREE                  │
│                                                           │
│                        ┌─────────┐                        │
│                        │  JD vs  │                        │
│                        │  CV     │                        │
│                        └────┬────┘                        │
│                             │                             │
│              ┌──────────────┼──────────────┐              │
│              ▼              ▼              ▼              │
│         ┌────────┐    ┌────────┐    ┌──────────┐         │
│         │ KEEP   │    │IMPROVE │    │ REPLACE  │         │
│         │ ≥80%   │    │ 50-79% │    │ <50%     │         │
│         │ match  │    │ match  │    │ match    │         │
│         └────────┘    └───┬────┘    └────┬─────┘         │
│                           │              │                │
│                           ▼              ▼                │
│                      ┌────────┐    ┌──────────┐          │
│                      │ Thêm   │    │ Sinh     │          │
│                      │ bullet │    │ project  │          │
│                      │ chi    │    │ synthetic│          │
│                      │ tiết   │    │ mới      │          │
│                      └────────┘    └──────────┘          │
│                                                           │
└──────────────────────────────────────────────────────────┘
```

### 6 Believability Rules (R1-R6)

| Rule | Mô tả | Ví dụ |
|------|-------|-------|
| **R1: Scale phù hợp level** | Project không vượt quá level của bạn | Junior: "Xây dựng REST API cho blog với Spring Boot". KHÔNG: "Thiết kế multi-tenant SaaS platform" |
| **R2: Không trùng domain** | Synthetic project phải khác domain với project thật | CV có payment → synthetic chọn e-commerce, logistics, healthcare |
| **R3: Có "vết" thực tế** | Mỗi project phải có ít nhất 1 bullet mô tả thử thách/bài học | "Ban đầu dùng REST, phát hiện latency cao → chuyển sang gRPC" |
| **R4: Mạch logic** | Project sau build trên project trước | Project 1: REST API → Project 2: Microservices → Project 3: K8s deploy |
| **R5: Tech stack giới hạn** | Giới hạn số công nghệ theo level | Fresher/Junior: ≤5, Mid: ≤6, Senior: ≤7 |
| **R6: Bullet đồng nhất** | Synthetic bullets phải khớp style với project thật | Cùng số bullet, cùng độ dài, cùng giọng văn |

### Walkthrough Đầy Đủ

Giả sử Nguyễn Văn A vừa paste JD TechCo, system detect match 62% và offer gap-fill:

```
System:
┌─────────────────────────────────────────────────────────────┐
│  📊 PHÂN TÍCH GAP: Senior Java Developer @ TechCo           │
│  Match: 62%                                                 │
│                                                             │
│  📋 ĐÁNH GIÁ PROJECT HIỆN CÓ:                               │
│  ┌──────────────────────────────────────────────────────┐  │
│  │ ✅ Core Payment Gateway (85%) — KEEP                  │  │
│  │ ✅ FoodFlow (72%) — IMPROVE: thêm bullet về Kafka     │  │
│  │ ❌ ETL Pipeline (30%) — REPLACE: Python ETL, lệch role│  │
│  └──────────────────────────────────────────────────────┘  │
│                                                             │
│  🔍 GAP KỸ NĂNG CẦN LẤP:                                    │
│  • Kubernetes — missing → ADD                              │
│  • Jenkins/CI/CD — missing → ADD                           │
│  • AWS (EC2, S3) — missing → ADD                           │
│  • Kafka (chi tiết) — weak → IMPROVE                       │
│                                                             │
│  💡 ĐỀ XUẤT:                                               │
│  1. THAY THẾ ETL Pipeline → CloudDeploy                    │
│     (Spring Boot, Docker, Jenkins, JUnit, AWS EC2)         │
│  2. THÊM MỚI → ShopK8s                                     │
│     (Spring Boot, Docker, Kubernetes, AWS EKS, Kafka)      │
│  3. CẢI THIỆN FoodFlow — thêm bullet về Kafka implementation│
│                                                             │
│  ──────────────────────────────────────────────────────    │
│  Gõ "yes" để áp dụng, "no" để giữ CV gốc,                 │
│  hoặc "edit" để chỉnh sửa đề xuất                          │
└─────────────────────────────────────────────────────────────┘

Bạn gõ: yes

System:
✅ ĐÃ ÁP DỤNG GAP-FILL

Đã thay đổi CV:
  - REPLACE: ETL Pipeline → CloudDeploy (Spring Boot CI/CD Pipeline)
  - ADD: ShopK8s (E-Commerce Microservices trên Kubernetes)
  - IMPROVE: FoodFlow — thêm 2 bullets về Kafka implementation

Đã append 2 STAR+R stories vào interview-prep/story-bank.md

📄 CV đã cập nhật. Git diff để xem thay đổi.
   Có thể revert bằng git checkout.

Bạn có muốn sinh câu hỏi phỏng vấn kỹ thuật cho JD này không? (tech-qa mode)
```

**CV Before → After:**

```
BEFORE:                          AFTER:
───────                          ──────
## Dự án                         ## Dự án

### FoodFlow                     ### FoodFlow
- Xây dựng REST API...           - Xây dựng REST API...
- Tích hợp Redis cache...        - Tích hợp Redis cache...
                                 - Implement Idempotent Consumer
                                   pattern với Kafka → đảm bảo
                                   exactly-once processing
                                 - Xử lý 1000 order/giây với
                                   Kafka partitioning strategy

### ETL Pipeline (Cole)          ### CloudDeploy — CI/CD Pipeline
- Python script...               - Setup Jenkins pipeline tự động
- Metabase dashboard...            build Docker image từ GitHub
                                 - Chạy JUnit test + generate
                                   coverage report (85%+)
                                 - Deploy lên AWS EC2 với
                                   Docker Compose

                                 ### ShopK8s — E-Commerce
                                 Microservices Platform
                                 - Thiết kế 3 microservices
                                   (Order, Payment, Inventory)
                                 - Message queue với Kafka cho
                                   async communication
                                 - Deploy lên Kubernetes cluster
                                   (local minikube → AWS EKS)
                                 - Gặp vấn đề connection pool khi
                                   scale lên 5 pods → tuning
                                   HikariCP connection timeout
```

---

## 7. Chuẩn Bị Phỏng Vấn

### 7.1 Tech-QA (`/career-ops tech-qa`)

Sinh câu hỏi phỏng vấn kỹ thuật từ knowledge base, cá nhân hóa theo CV của bạn.

#### Walkthrough

```
Bạn gõ: /career-ops tech-qa

System:
📋 Sinh câu hỏi phỏng vấn cho JD gần nhất:
   TechCo — Senior Java Developer

Đang đọc knowledge base: 01-backend.md
Đang phân tích CV: 5 projects, 8 kỹ năng

Đã sinh 30 câu hỏi (17 basic, 13 medium)
Lưu vào: interview-prep/techco-senior-java-developer-tech-qa.md

────────────────────────────────────────

Preview 3 câu đầu:

### Câu 1: Phân biệt Abstract Class vs Interface trong Java?
**Mức độ:** Basic

📎 **Từ CV của bạn:**
Trong Core Payment Gateway tại VNPAY, em sử dụng Interface
`PaymentGateway` để define contract cho các phương thức thanh toán
khác nhau (Momo, ZaloPay, VNPay), và Abstract Class
`BasePaymentService` để chứa shared logic như logging, validation.

💡 **Gợi ý trả lời:**
Em phân biệt qua 3 điểm chính:
1. Interface hỗ trợ multiple inheritance, Abstract Class thì không
2. Interface chỉ có abstract methods (trước Java 8), Abstract Class
   có thể có cả abstract và concrete methods
3. Dùng Interface khi muốn define contract (vd: PaymentGateway),
   dùng Abstract Class khi có shared state/behavior (vd:
   BasePaymentService chứa logging)

### Câu 2: Dependency Injection trong Spring Boot hoạt động thế nào?
**Mức độ:** Basic

📎 **Từ CV của bạn:**
Tất cả project đều dùng Spring Boot với constructor injection.
Trong FoodFlow, em inject OrderService vào OrderController qua
constructor.

💡 **Gợi ý trả lời:**
Spring Boot quản lý beans qua IoC Container. Có 3 cách inject:
1. Constructor Injection (recommended) — em dùng trong tất cả project
2. Field Injection (@Autowired) — Spring khuyên không nên dùng
3. Setter Injection — dùng cho optional dependencies
Constructor injection giúp code dễ test hơn vì có thể mock
dependencies khi unit test.

### Câu 3: Kafka Consumer Group hoạt động thế nào?
**Mức độ:** Medium
...
```

**Output mẫu:** File `interview-prep/techco-senior-java-developer-tech-qa.md` chứa:

```
# Tech Q&A: TechCo — Senior Java Developer

**JD:** https://careers.techco.com/jobs/senior-java-developer
**Ngày sinh:** 2026-05-15
**Knowledge base:** 01-backend.md
**Số câu hỏi:** 30
**Level:** basic, medium

---

## Java Core

### Câu 1: Phân biệt Abstract Class vs Interface?
### Câu 2: HashMap hoạt động thế nào?
...

## Spring Boot

### Câu 8: Dependency Injection là gì?
### Câu 9: @Transactional hoạt động thế nào?
...

## Kafka

### Câu 15: Consumer Group hoạt động thế nào?
### Câu 16: Làm sao đảm bảo message không bị mất?
...

## Docker

### Câu 22: Docker Image vs Container khác gì?
...

## Database

### Câu 27: Index trong PostgreSQL hoạt động thế nào?
...

---

## Tổng kết

| Kỹ năng | Basic | Medium | Advanced | Tổng |
|---------|-------|--------|----------|------|
| Java Core | 5 | 4 | 0 | 9 |
| Spring Boot | 4 | 3 | 0 | 7 |
| Kafka | 3 | 4 | 0 | 7 |
| Docker | 3 | 2 | 0 | 5 |
| Database | 2 | 0 | 0 | 2 |
| **Tổng** | **17** | **13** | **0** | **30** |
```

### 7.2 Interview-Prep (`/career-ops interview-prep`)

Research chuyên sâu về công ty + quy trình phỏng vấn + câu hỏi dự đoán + STAR stories.

```
Bạn gõ: /career-ops interview-prep

System yêu cầu: "Bạn muốn prep cho công ty nào?"
Bạn gõ: TechCo

System thực hiện:
- WebSearch: "TechCo interview questions Glassdoor"
- WebSearch: "TechCo interview process Blind"
- WebSearch: "TechCo engineering blog"
- Đọc report đánh giá reports/042-techco-2026-05-15.md
- Đọc story-bank.md
- Cross-reference với tech-qa file (nếu có)

Output lưu vào: interview-prep/techco-senior-java-developer.md

## Nội dung file:

# Interview Intel: TechCo — Senior Java Developer

**Report:** [042](reports/042-techco-2026-05-15.md)
**Researched:** 2026-05-15
**Sources:** 12 Glassdoor reviews, 3 Blind posts, TechCo blog

---

## Process Overview
- **Rounds:** 4 rounds, ~14 ngày end-to-end
- **Format:** Phone screen → Technical (live coding) → System Design → Culture fit
- **Difficulty:** 3.8/5 (Glassdoor avg, 12 reviews)
- **Known quirks:** Không LeetCode, thiên về practical problem-solving

## Round-by-Round Breakdown

### Round 1: Phone Screen (30 phút)
- **Conducted by:** HR / Talent Acquisition
- **What they evaluate:** Communication, motivation, basic tech knowledge
- **How to prepare:** Ôn lại câu chuyện career của bạn, lý do chọn TechCo

### Round 2: Technical Coding (60 phút)
- **Conducted by:** Senior Engineer
- **What they evaluate:** Java proficiency, problem-solving, code quality
- **Reported questions:**
  - "Build a simple payment processing system" — [Glassdoor 2026-Q1]
  - "Design a rate limiter" — [Blind]
- **How to prepare:** Luyện Core Payment Gateway + FoodFlow scenarios

### Round 3: System Design (60 phút)
...

## Company Signals
- **Values they screen for:** Ownership, Customer focus, Technical excellence
- **Vocabulary to use:** "payment orchestration", "idempotency", "event-driven"
- **Things to avoid:** Không nói xấu ngân hàng/đối tác cũ
- **Questions to ask them:**
  - "TechCo đang migrate từ monolith sang microservices — team mình đang ở phase nào?"
  - "Làm sao team đo lường reliability của payment system?"
```

### 7.3 Story Bank

Story bank (`interview-prep/story-bank.md`) là kho lưu trữ STAR+R stories được tích lũy qua mỗi lần evaluation và gap-fill. Mỗi story theo format:

```markdown
## 1. Core Payment Gateway — Xử lý thanh toán cross-bank
**Tags:** Java, Spring Boot, RabbitMQ, Payment, Integration

**S** — VNPAY cần xây dựng Core Payment Gateway xử lý thanh toán
     giữa 30+ ngân hàng, mỗi ngân hàng có API format khác nhau.

**T** — Cần một hệ thống thống nhất để tích hợp nhanh ngân hàng
     mới mà không phải sửa code core.

**A** — Em áp dụng Strategy Pattern: mỗi ngân hàng là một
     implementation của interface PaymentGateway. Dùng Factory
     Pattern để chọn đúng strategy dựa trên bank code. Tích hợp
     RabbitMQ để xử lý giao dịch async.

**R** — Rút ngắn thời gian tích hợp ngân hàng mới từ 2 tuần
     xuống 2 ngày. Hệ thống xử lý 5000+ giao dịch/ngày.

**Reflection** — Nếu làm lại, em sẽ đầu tư circuit breaker pattern
     sớm hơn. Có lần API ngân hàng bị timeout khiến toàn bộ queue
     bị tắc — exponential backoff đã giải quyết vấn đề này.
```

**Cách dùng:** Khi bạn chạy interview-prep, hệ thống tự động map các câu hỏi dự đoán với stories trong bank. Nếu thiếu story cho một câu hỏi, hệ thống sẽ gợi ý bạn xây dựng story mới.

---

## 8. Nộp Đơn & Theo Dõi

### 8.1 Điền Form Ứng Tuyển (`/career-ops apply`)

Khi bạn đang ở trang apply của công ty, apply mode sẽ đọc form và sinh câu trả lời cá nhân hóa:

```
Bạn gõ: /career-ops apply

System:
🔍 Đang đọc form ứng tuyển từ Chrome...

Đã phát hiện form: TechCo — Senior Java Developer
Đã tìm thấy report: reports/042-techco-2026-05-15.md

📋 Các câu hỏi trong form:

Q1: "Why are you interested in this role?"
────────────────────────────────────────
💡 Gợi ý trả lời:
"Your payment infrastructure role maps directly to what I've built
at VNPAY — a Core Payment Gateway processing cross-bank transactions.
Your JD mentions Kafka and event-driven architecture, which I've applied
in my FoodFlow project. This role is where I want to deepen that expertise."

────────────────────────────────────────

Q2: "Tell us about a relevant project"
💡 Gợi ý trả lời:
"At VNPAY, I built a Core Payment Gateway that unified 30+ bank APIs
into a single integration layer. I used Strategy + Factory patterns to
make new bank integrations take 2 days instead of 2 weeks..."

[... tiếp tục với các câu hỏi còn lại ...]

⚠️  QUAN TRỌNG: Tôi sẽ KHÔNG tự động submit. Bạn hãy review,
chỉnh sửa nếu cần, và tự nhấn nút Submit.
```

### 8.2 Theo Dõi Trạng Thái (`/career-ops tracker`)

```
Bạn gõ: /career-ops tracker

System:
# Applications Tracker — 2026-05-15

| # | Date | Company | Role | Score | Status | PDF | Report |
|---|------|---------|------|-------|--------|-----|--------|
| 41 | 05-14 | VNPAY | Backend Developer | 4.5/5 | Applied | ✅ | [041] |
| 42 | 05-15 | TechCo | Senior Java Developer | 3.2/5 | Evaluated | ✅ | [042] |
| 40 | 05-10 | FPT | Java Fresher | 3.8/5 | Rejected | ✅ | [040] |
| 39 | 05-08 | Momo | Backend Engineer | 4.0/5 | Interview | ✅ | [039] |
| 38 | 05-05 | VNG | Java Developer | 2.8/5 | SKIP | ❌ | [038] |

Active: 2 | Interviews: 1 | Offers: 0 | Rejected: 1
```

**Canonical states:** `Evaluated` → `Applied` → `Responded` → `Interview` → `Offer` | `Rejected` | `Discarded` | `SKIP`

### 8.3 Follow-up (`/career-ops followup`)

Theo dõi cadence follow-up cho các đơn đã nộp:

```
Bạn gõ: /career-ops followup

System:
Follow-up Cadence Dashboard — 2026-05-15
12 applications tracked, 3 actionable

⚠️  URGENT (quá hạn > 3 ngày):
  - VNPAY Backend Developer — Applied 14 ngày trước, chưa follow-up
    → Gợi ý: "Hi, I applied for the Backend Developer role 2 weeks ago
    and wanted to check in. I've been following VNPAY's expansion into..."

⏰ OVERDUE (đến hạn):
  - Momo Backend Engineer — Applied 8 ngày trước
    → Gợi ý: "I wanted to follow up on my application..."

⏳ WAITING (chưa đến hạn):
  - FPT Java Fresher — Applied 5 ngày trước, follow-up sau 2 ngày nữa
```

### 8.4 LinkedIn Outreach (`/career-ops contact`)

Tìm người để contact trên LinkedIn và draft message:

```
Bạn gõ: /career-ops contact

System yêu cầu: "Công ty và role?"
Bạn gõ: TechCo Senior Java Developer

System:
🔍 Đang tìm người liên hệ tại TechCo...

Tìm thấy 3 người:
1. Trần Văn B — Engineering Manager @ TechCo
   → LinkedIn: linkedin.com/in/tranvanb
   → Có thể là hiring manager cho role này

2. Lê Thị C — Senior Java Developer @ TechCo
   → LinkedIn: linkedin.com/in/lethic
   → Peer — có thể hỏi về team culture

3. Phạm Văn D — Tech Recruiter @ TechCo
   → LinkedIn: linkedin.com/in/phamvand
   → Người phụ trách tuyển dụng role này

💡 Draft message cho Trần Văn B:

"Chào anh B,

Em là Nguyễn Văn A, hiện đang là Backend Developer tại VNPAY.
Em vừa apply vị trí Senior Java Developer tại TechCo và rất ấn
tượng với hệ thống payment infrastructure của team mình.

Em có kinh nghiệm xây dựng Core Payment Gateway xử lý thanh toán
cross-bank, và đang tìm hiểu thêm về Kafka + event-driven
architecture — đúng hướng team mình đang làm.

Anh có 10 phút để chia sẻ thêm về team và những thử thách kỹ
thuật team đang giải quyết không ạ?

Cảm ơn anh,
Nguyễn Văn A"
```

---

# PHẦN 3: THAM KHẢO

## 9. Tất Cả Lệnh

| Command | Mô tả | Ví dụ |
|---------|-------|-------|
| `/career-ops {JD}` | Auto-pipeline: đánh giá + report + PDF + tracker | `/career-ops https://careers.techco.com/jobs/123` |
| `/career-ops new-cv` | Wizard tạo CV mới từ đầu | `/career-ops new-cv` |
| `/career-ops cv-switch` | Chuyển đổi CV đang active | `/career-ops cv-switch` |
| `/career-ops convert` | Convert CV từ PDF/DOCX/ảnh/LinkedIn | `/career-ops convert cv-input/my-cv.pdf` |
| `/career-ops oferta` | Đánh giá A-F (không tự động PDF) | `/career-ops oferta` |
| `/career-ops ofertas` | So sánh và xếp hạng nhiều offer | `/career-ops ofertas` |
| `/career-ops gap-fill` | Phân tích gap kỹ năng + sinh synthetic projects | `/career-ops gap-fill` |
| `/career-ops tech-qa` | Sinh câu hỏi phỏng vấn kỹ thuật | `/career-ops tech-qa` |
| `/career-ops interview-prep` | Research công ty + STAR stories + prep | `/career-ops interview-prep` |
| `/career-ops pdf` | Generate PDF từ CV (không evaluate) | `/career-ops pdf` |
| `/career-ops scan` | Quét portal tìm việc mới | `/career-ops scan` |
| `/career-ops batch` | Xử lý hàng loạt với parallel workers | `/career-ops batch` |
| `/career-ops apply` | Trợ lý điền form ứng tuyển | `/career-ops apply` |
| `/career-ops tracker` | Xem trạng thái tất cả applications | `/career-ops tracker` |
| `/career-ops patterns` | Phân tích pattern rejections để cải thiện | `/career-ops patterns` |
| `/career-ops followup` | Theo dõi cadence follow-up | `/career-ops followup` |
| `/career-ops contact` | LinkedIn outreach — tìm người + draft message | `/career-ops contact` |
| `/career-ops deep` | Research chuyên sâu về công ty | `/career-ops deep` |
| `/career-ops training` | Đánh giá khóa học/chứng chỉ | `/career-ops training` |
| `/career-ops project` | Đánh giá ý tưởng portfolio project | `/career-ops project` |
| `/career-ops pipeline` | Xử lý pending URLs từ inbox | `/career-ops pipeline` |

**Lưu ý:** Khi dùng OpenCode, tên lệnh có format `/career-ops-{mode}` (VD: `/career-ops-newcv`, `/career-ops-gapfill`). Xem file `AGENTS.md` và `docs/CODEX.md`.

---

## 10. Cấu Hình — profile.yml

File `config/profile.yml` là **single source of truth** cho toàn bộ dữ liệu cá nhân của bạn. Dưới đây là giải thích từng field.

### Cấu Trúc Đầy Đủ

```yaml
# Career-Ops Profile Configuration
# Đây là file cấu hình cá nhân của bạn.
# System updates sẽ KHÔNG BAO GIỜ ghi đè file này.

# ── THÔNG TIN ỨNG VIÊN ──────────────────────────────
candidate:
  full_name: "Nguyễn Văn A"              # Họ tên đầy đủ — dùng trong CV, PDF, tracker
  email: "anh.nguyen@email.com"          # Email liên hệ
  phone: "+84-123-456-789"               # SĐT (tuỳ chọn)
  location: "Hà Nội, Việt Nam"           # Địa điểm hiện tại
  linkedin: "linkedin.com/in/nguyenvana" # LinkedIn URL (tuỳ chọn)
  portfolio_url: ""                       # Portfolio/website cá nhân (tuỳ chọn)
  github: "github.com/nguyenvana"         # GitHub URL (tuỳ chọn)
  # twitter: ""                           # X/Twitter URL (tuỳ chọn)
  # canva_resume_design_id: ""            # Canva design ID cho visual CV (tuỳ chọn)

# ── ROLE MỤC TIÊU ──────────────────────────────────
target_roles:
  # Role chính — thứ bạn đang optimize
  primary:
    - "Junior Java Backend Developer"
    - "Java Software Engineer"
  # Archetypes giúp hệ thống đánh giá mức độ fit
  archetypes:
    - name: "Backend Developer"
      level: "Junior"
      fit: "primary"        # primary = dream role, secondary = good fit, adjacent = stretch
    - name: "Data Engineer"
      level: "Junior"
      fit: "secondary"
    - name: "Fullstack Developer"
      level: "Junior"
      fit: "adjacent"

# ── NARRATIVE (CÂU CHUYỆN CÁ NHÂN) ────────────────
narrative:
  headline: "Junior Java Developer with hands-on experience in payment systems & REST APIs"
  exit_story: ""                        # Lý do nghỉ việc cũ (nếu có)
  superpowers:                           # Điểm mạnh khác biệt
    - "Payment system integration"
    - "Clean code discipline"
    - "Fast learner — self-taught Kafka, Docker in 3 tháng"
  proof_points:                          # Dự án/bài viết có measurable impact
    - name: "Core Payment Gateway"
      url: ""
      hero_metric: "Xử lý 5000+ giao dịch/ngày, tích hợp 30+ ngân hàng"
    - name: "FoodFlow"
      url: "https://github.com/nguyenvana/foodflow"
      hero_metric: "Xử lý 1000 order/giây với Kafka partitioning"

# ── LƯƠNG & COMPENSATION ──────────────────────────
compensation:
  target_range: "$800-1200"             # Mức lương mong muốn (USD/tháng cho VN)
  currency: "USD"
  minimum: "$600"                       # Mức thấp nhất chấp nhận được

# ── ĐỊA ĐIỂM ───────────────────────────────────────
location:
  country: "Việt Nam"
  city: "Hà Nội"
  timezone: "ICT"                       # Asia/Ho_Chi_Minh = ICT (UTC+7)
  visa_status: "Không cần sponsorship"

# ── PROJECT GENERATION (GAP-FILL) ─────────────────
project_generation:
  enabled: true                         # Bật/tắt gap-fill
  max_total_projects: 6                 # Tổng project (thật + synthetic) tối đa
  max_new_projects: 2                   # Mỗi lần gap-fill thêm tối đa 2 project
  max_replacements: 1                   # Mỗi lần gap-fill thay thế tối đa 1 project
  min_keep_projects: 2                  # Luôn giữ ít nhất 2 project gốc
  add_threshold: 70                     # Chỉ đề xuất thêm nếu match dưới 70%
  replace_threshold: 40                 # Chỉ đề xuất thay thế nếu project dưới 40%
  level: "junior"                       # fresher | junior | mid | senior
  domains:                              # Domain ưu tiên cho synthetic projects
    - "Payment"
    - "E-Commerce"
    - "Logistics"
  constraints:                          # Ràng buộc bổ sung
    - "Không sinh project về AI/ML"
    - "Không sinh project về Blockchain"
  project_format: "standard"            # Format mô tả project

# ── INTERVIEW PREP ─────────────────────────────────
interview_prep:
  question_count: 30                    # Số câu hỏi tối đa mỗi lần tech-qa
  levels:                               # Level câu hỏi
    - basic
    - medium
  contextualized: true                  # true = cá nhân hóa câu trả lời theo CV

# ── CV PREFERENCES ─────────────────────────────────
cv_preferences:
  template_style: "mit"                 # harvard | mit | stanford | mba | ats
  language: "en"                        # vi | en

# ── JOB CONSTRAINTS ────────────────────────────────
job_constraints:
  preferences:                          # Tiêu chí lọc job
    - "Không công ty outsource"
    - "Công ty có product"
    - "Không làm Java Swing"
    - "Ưu tiên công ty có lộ trình thăng tiến rõ ràng"
```

### Giải Thích Chi Tiết Từng Section

#### `candidate`
Thông tin nhận diện cơ bản. Được dùng trong CV, PDF header, LinkedIn outreach, và tracker. `full_name` và `email` là bắt buộc. Các field còn lại là optional — nếu không có, hệ thống sẽ bỏ qua.

#### `target_roles`
Định nghĩa role bạn đang target. `primary` là North Star — mọi đánh giá sẽ optimize cho role này. `archetypes` giúp hệ thống phân loại JD: `primary` fit = ưu tiên cao nhất, `secondary` = good fit, `adjacent` = stretch role. Bạn có thể định nghĩa nhiều archetype với level khác nhau.

#### `narrative`
Câu chuyện cá nhân giúp hệ thống hiểu bạn là ai. `headline` xuất hiện trong CV và PDF. `superpowers` dùng để match với JD requirements. `proof_points` là bằng chứng cụ thể — dùng trong Block B (match evaluation) và interview-prep.

#### `compensation`
Khung lương để hệ thống đánh giá Block D (comp). `target_range` là mức bạn muốn, `minimum` là mức thấp nhất. Đơn vị: nên thống nhất (USD/tháng cho thị trường Việt Nam).

#### `project_generation`
Điều khiển hành vi của gap-fill mode. Đây là section quan trọng nhất để kiểm soát synthetic projects:
- `enabled: false` → tắt hoàn toàn gap-fill
- `level` xác định scale project (R1)
- `domains` xác định lĩnh vực ưu tiên
- `constraints` là hard rules (VD: không sinh project về AI)
- Các threshold quyết định khi nào hệ thống đề xuất thêm/thay thế

#### `interview_prep`
Điều khiển tech-qa mode. `contextualized: true` (recommended) sinh câu trả lời gắn với CV của bạn; `false` chỉ sinh câu hỏi.

#### `cv_preferences`
Theme mặc định và ngôn ngữ CV. Có thể override trong new-cv wizard.

#### `job_constraints`
Bộ lọc cứng — những job không phù hợp sẽ bị gắn cờ trong evaluation.

---

## 11. Knowledge Base

Knowledge Base (`knowledge/`) là trung tâm kiến thức cho 14 role IT, được sử dụng bởi gap-fill và tech-qa.

### 14 Role IT

| # | Role | File | Mô tả ngắn |
|---|------|------|------------|
| 1 | Backend Developer | `01-backend.md` | Java, .NET, Python, Node.js, Go — API, Database, Microservices |
| 2 | Frontend Developer | `02-frontend.md` | React, Vue, Angular, Next.js — UI/UX, Performance, Accessibility |
| 3 | Fullstack Developer | `03-fullstack.md` | Frontend + Backend — Next.js, Node.js, TypeScript |
| 4 | DevOps Engineer | `04-devops.md` | CI/CD, Docker, Kubernetes, Terraform, Cloud, Monitoring |
| 5 | Business Analyst | `05-business-analyst.md` | Requirements, UML, Agile, Stakeholder, SQL |
| 6 | Tester / QA | `06-tester-qa.md` | Manual Testing, Automation (Selenium/Cypress), API Testing |
| 7 | Data Engineer | `07-data-engineer.md` | ETL, Spark, Airflow, dbt, Data Warehouse, Data Lake |
| 8 | Data Analyst | `08-data-analyst.md` | SQL, Python/R, Tableau/PowerBI, Statistics, A/B Testing |
| 9 | Mobile Developer | `09-mobile-dev.md` | Android (Kotlin), iOS (Swift), React Native, Flutter |
| 10 | Embedded Engineer | `10-embedded.md` | C/C++, RTOS, ARM, IoT, Firmware |
| 11 | Security Engineer | `11-security.md` | Pentest, SOC, Cloud Security, Cryptography, Compliance |
| 12 | AI/ML Engineer | `12-ai-ml.md` | Python, PyTorch/TensorFlow, NLP, CV, MLOps, LLM |
| 13 | Project Manager IT | `13-project-manager.md` | Agile/Scrum, Risk, Stakeholder, Budget, Scheduling |
| 14 | Product Manager IT | `14-product-manager.md` | Discovery, Roadmap, Analytics, Growth, Strategy |

### Cách Gap-Fill Dùng Knowledge Base

1. Đọc JD → xác định role (Backend, Frontend, DevOps...)
2. Đọc file role tương ứng trong `knowledge/roles/`
3. So sánh kỹ năng yêu cầu với CV → tìm gap
4. Chọn dự án mẫu phù hợp từ catalog trong file role
5. Sinh synthetic project theo believability rules

### Cách Tech-QA Dùng Knowledge Base

1. Đọc JD → trích xuất tech stack cần hỏi
2. Đọc file role → lấy ngân hàng câu hỏi theo kỹ năng
3. Lọc câu hỏi theo level (basic/medium/advanced)
4. Sinh câu trả lời cá nhân hóa gắn với CV

### Tự Thêm Kiến Thức

1. **Thêm kỹ năng vào role có sẵn:** Mở file role, thêm dòng vào bảng kỹ năng
2. **Thêm câu hỏi:** Trong section "Câu hỏi phỏng vấn mẫu", thêm câu hỏi mới
3. **Tạo file kiến thức cá nhân:** Tạo file `.md` trong `knowledge/topics/` — các file này KHÔNG bị ghi đè khi update
4. **Tạo role mới:** Copy file role có sẵn, đổi tên, sửa nội dung

---

# PHẦN 4: NÂNG CAO & XỬ LÝ SỰ CỐ

## 12. Tính Năng Nâng Cao

### 12.1 Quét Portal Tự Động (`/career-ops scan`)

Scanner là zero-token — gọi trực tiếp Greenhouse/Ashby/Lever APIs, không tốn LLM cost.

```bash
# Quét tất cả công ty đã cấu hình
node scan.mjs

# Dry-run — preview không ghi file
node scan.mjs --dry-run

# Quét 1 công ty
node scan.mjs --company TechCo
```

Scanner hoạt động 3 tầng:
1. **Playwright direct** — navigate đến careers page từng công ty, đọc tất cả job listings
2. **ATS APIs** — gọi Greenhouse/Ashby/Lever JSON APIs trực tiếp
3. **WebSearch fallback** — tìm qua search engine nếu 2 cách trên thất bại

Kết quả: URLs mới được append vào `data/pipeline.md` để xử lý sau. Scanner tự động dedup với `data/scan-history.tsv`.

### 12.2 Xử Lý Hàng Loạt (`/career-ops batch`)

Khi bạn có nhiều URL trong `data/pipeline.md`, batch mode xử lý song song với multiple workers:

```bash
# Xử lý tất cả pending URLs
node batch/batch-runner.sh

# Hoặc dùng slash command
/career-ops batch
```

Mỗi worker chạy auto-pipeline cho 1 JD. Sau khi hoàn tất, chạy `node merge-tracker.mjs` để merge kết quả.

### 12.3 Dashboard TUI

Dashboard terminal UI trong `dashboard/` — xem nhanh trạng thái tất cả applications.

### 12.4 Phân Tích Pattern (`/career-ops patterns`)

Phân tích tất cả applications đã tracked để tìm pattern:

```
Bạn gõ: /career-ops patterns

System:
📊 Pattern Analysis — 12 applications analyzed

Funnel:
  Evaluated: 12 → Applied: 8 → Responded: 3 → Interview: 1 → Offer: 0

🔍 Phát hiện:
  - Conversion rate cao nhất: Backend Developer roles (75% → interview)
  - Blocker phổ biến nhất: "Yêu cầu 5+ năm kinh nghiệm" (3 rejections)
  - Score trung bình của rejected: 3.1/5
  - Score trung bình của interviewed: 4.3/5

💡 Recommendations:
  1. Focus vào Junior/Mid-level Backend roles (score > 3.8)
  2. Tránh apply Senior roles — bạn chưa đủ năm kinh nghiệm
  3. Cân nhắc thêm chứng chỉ AWS để tăng match score
```

### 12.5 Đàm Phán Lương (Block D trong oferta)

Khi chạy `/career-ops oferta`, Block D cung cấp dữ liệu lương thị trường:

```
## D) Comp & Demand

| Nguồn | Mức lương | Ghi chú |
|-------|-----------|---------|
| Glassdoor | $800-1500/tháng | Java Developer tại Hà Nội, 1-3 năm KN |
| ITviec | $600-1200/tháng | Backend Developer, Junior-Mid |
| Levels.fyi | N/A | Không có dữ liệu cho thị trường VN |

**Reputation:** TechCo được đánh giá trả lương top 30% thị trường (theo Glassdoor).
**Demand trend:** Java Backend demand tăng 15% YoY tại VN.

**Negotiation strategy:**
- Mở: $1000/tháng (dựa trên Glassdoor median + kinh nghiệm payment system)
- Sàn cứng: $600/tháng (minimum trong profile)
- Nếu họ offer $800: counter $950 — lý do: "Kinh nghiệm Core Payment Gateway
  là asset trực tiếp cho role này, giảm onboarding time"
```

---

## 13. Xử Lý Sự Cố

### Lỗi 1: "cv.md not found"

```
Nguyên nhân: Bạn chưa tạo CV, hoặc file cv.md bị xóa.
Cách fix:
  1. Chạy /career-ops new-cv để tạo CV mới từ wizard
  2. Hoặc chạy /career-ops convert để convert CV cũ
  3. Hoặc tạo thủ công: tạo file cv.md ở project root
```

### Lỗi 2: "profile.yml parse error"

```
Nguyên nhân: File YAML bị sai syntax (thường là sai indent).
Cách fix:
  1. Kiểm tra indent — YAML dùng 2 spaces, KHÔNG dùng tab
  2. Kiểm tra dấu ":" phải có space phía sau
  3. Chạy: node -e "require('js-yaml').load(require('fs').readFileSync('config/profile.yml','utf8'))"
     để validate syntax
  4. Nếu vẫn lỗi, copy từ config/profile.example.yml và điền lại
```

### Lỗi 3: "Playwright not installed"

```
Nguyên nhân: Chromium browser chưa được cài cho Playwright.
Cách fix:
  npx playwright install chromium
  Sau đó kiểm tra lại: node doctor.mjs
```

### Lỗi 4: "Pipeline integrity warnings"

```
Nguyên nhân: Có sự không nhất quán giữa tracker, reports, và batch files.
Cách fix:
  1. Chạy: node verify-pipeline.mjs
     → Xem danh sách các vấn đề cụ thể
  2. Chạy: node normalize-statuses.mjs
     → Chuẩn hóa tất cả status về canonical states
  3. Chạy: node dedup-tracker.mjs
     → Loại bỏ entries trùng lặp
  4. Chạy: node merge-tracker.mjs
     → Merge batch tracker additions nếu có file pending
```

### Lỗi 5: "Update conflicts"

```
Nguyên nhân: File system layer bị modified local, không merge được update.
Cách fix:
  1. git status — xem files nào bị modified
  2. node update-system.mjs check — kiểm tra version hiện tại vs remote
  3. Backup các file user layer quan trọng (cv.md, profile.yml, tracker)
  4. node update-system.mjs apply — áp dụng update
  5. Nếu vẫn lỗi: node update-system.mjs rollback để quay về version cũ
```

### Lỗi 6: "Fonts not loading in PDF"

```
Nguyên nhân: Thư mục fonts/ thiếu file font tự host.
Cách fix:
  1. Kiểm tra fonts/ có đủ file không (SpaceGrotesk, DMSans variants)
  2. Nếu thiếu, chạy lại npm install (fonts được include trong dependencies)
  3. Nếu dùng theme "stanford": cần Google Fonts Inter — đảm bảo có internet
  4. Fallback: đổi sang theme "mit" hoặc "ats" (dùng system fonts)
```

### Công Cụ Chẩn Đoán

| Command | Chức năng |
|---------|-----------|
| `node doctor.mjs` | Kiểm tra toàn bộ prerequisites |
| `node verify-pipeline.mjs` | Kiểm tra tính toàn vẹn của pipeline |
| `node cv-sync-check.mjs` | Kiểm tra đồng bộ giữa cv.md và cvs/ |
| `node update-system.mjs check` | Kiểm tra update version |
| `node merge-tracker.mjs` | Merge batch tracker additions |
| `node normalize-statuses.mjs` | Chuẩn hóa status về canonical states |
| `node dedup-tracker.mjs` | Loại bỏ entries trùng lặp |
| `node check-liveness.mjs` | Kiểm tra JD còn active không |

---

## 14. Câu Hỏi Thường Gặp

### Q1: Career-Ops có dùng được với OpenCode không?

**Có.** Career-Ops hỗ trợ cả Claude Code và OpenCode. Khi dùng OpenCode, các lệnh slash có format `/career-ops-{mode}` (VD: `/career-ops-newcv`, `/career-ops-gapfill`). Xem chi tiết tại `AGENTS.md` và `docs/CODEX.md`.

### Q2: Dữ liệu của tôi có an toàn không? Có bị gửi đi đâu không?

**An toàn tuyệt đối.** Tất cả dữ liệu của bạn (CV, profile, tracker, reports, story bank) được lưu **local** trong project folder. Không có telemetry, không gửi dữ liệu ra ngoài. Bạn có thể kiểm tra: toàn bộ source code nằm trong repo này, không có external API calls cho dữ liệu cá nhân.

File `DATA_CONTRACT.md` phân định rõ 2 layers:
- **User Layer:** KHÔNG BAO GIỜ bị auto-update ghi đè (cv.md, profile.yml, tracker, reports...)
- **System Layer:** Có thể được update an toàn (modes/, templates/, scripts...)

### Q3: Career-Ops hỗ trợ ngôn ngữ nào?

**Tiếng Việt và Tiếng Anh.** Mặc định modes bằng tiếng Anh. Để dùng tiếng Việt, set trong `config/profile.yml`:

```yaml
cv_preferences:
  language: "vi"
```

Career-Ops cũng có modes tiếng Việt đầy đủ trong `modes/vi/` — bao gồm các thuật ngữ đặc thù thị trường Việt Nam (hợp đồng lao động, thử việc, BHXH/BHYT/BHTN, lương gross/net, tháng lương 13, thưởng Tết, ITviec, VietnamWorks, TopCV...).

Ngoài ra còn có bản dịch tiếng Đức (`modes/de/`), tiếng Pháp (`modes/fr/`), và tiếng Nhật (`modes/ja/`).

### Q4: Career-Ops có tự động nộp đơn không?

**KHÔNG.** Đây là nguyên tắc đạo đức cốt lõi. Hệ thống có thể:
- Điền form ứng tuyển với câu trả lời cá nhân hóa
- Draft email/LinkedIn message
- Generate PDF CV sẵn sàng nộp

Nhưng LUÔN dừng trước nút Submit/Send/Apply. **Bạn là người quyết định cuối cùng.**

### Q5: Tôi muốn đổi role mục tiêu (VD: từ Backend sang DevOps) thì làm sao?

1. Sửa `config/profile.yml`:
   ```yaml
   target_roles:
     primary:
       - "Junior DevOps Engineer"
     archetypes:
       - name: "DevOps Engineer"
         level: "Junior"
         fit: "primary"
   ```
2. Đọc file role mới trong knowledge base: `knowledge/roles/04-devops.md`
3. Chạy `/career-ops gap-fill` với 1 JD DevOps để hệ thống phân tích gap
4. Hệ thống sẽ sinh synthetic projects phù hợp với DevOps
5. Nếu cần, thêm kiến thức cá nhân vào `knowledge/topics/`

### Q6: CV synthetic (gap-fill) có bị nhà tuyển dụng phát hiện không?

Career-Ops áp dụng **6 believability rules** để giảm thiểu rủi ro:
- **R1:** Scale project đúng level (Junior không có project "thiết kế hệ thống 1M users")
- **R2:** Domain khác với project thật (tránh trùng lặp đáng ngờ)
- **R3:** Có "vết" thực tế (thử thách, sai lầm, bài học — không hoàn hảo)
- **R4:** Mạch logic tiến hóa (project sau build trên project trước)
- **R5:** Tech stack có giới hạn (không nhồi nhét 10 công nghệ vào 1 project)
- **R6:** Bullet đồng nhất style với project thật

**Quan trọng:** Synthetic projects là công cụ để bạn **học và thực hành** kỹ năng mới, không phải để "giả mạo" kinh nghiệm. Nếu được hỏi về synthetic project trong phỏng vấn, hãy trả lời như một dự án thật — vì bạn đã thực sự dành thời gian tìm hiểu và có kiến thức về nó qua quá trình gap-fill.

### Q7: Làm sao để cập nhật Career-Ops lên version mới?

```bash
# Kiểm tra version
node update-system.mjs check

# Nếu có update:
node update-system.mjs apply   # Áp dụng update

# Nếu muốn quay lại version cũ:
node update-system.mjs rollback

# Nếu không muốn update bản này:
node update-system.mjs dismiss
```

**Lưu ý quan trọng:** System update CHỈ ghi đè System Layer files (modes/, templates/, scripts...). User Layer files (cv.md, profile.yml, tracker, reports...) KHÔNG BAO GIỜ bị ảnh hưởng.

---

# PHẦN 5: PHỤ LỤC

## 15. Phụ Lục

### Sơ Đồ Thư Mục Đầy Đủ

```
career-ops/
│
├── cv.md                          ← CV active (pointer đến file trong cvs/)
├── article-digest.md              ← Proof points từ portfolio (optional)
│
├── config/
│   ├── profile.yml                ← YOUR PROFILE — single source of truth
│   └── profile.example.yml        ← Template tham khảo
│
├── cvs/                           ← Thư viện CV
│   ├── base.md                    ← CV gốc (chỉ dữ liệu thật)
│   ├── techco-senior-java.md      ← Tailored CV cho từng JD
│   ├── vnpay-backend-dev.md
│   └── _archive/                  ← CV cũ đã archive
│
├── cv-input/                      ← CV cũ để convert
│   ├── my-old-cv.pdf
│   └── converted/                 ← Output sau convert
│       └── my-old-cv.md
│
├── data/                          ← Dữ liệu ứng tuyển
│   ├── applications.md            ← Application tracker
│   ├── pipeline.md                ← URL inbox (pending)
│   ├── follow-ups.md              ← Follow-up history
│   └── scan-history.tsv           ← Scanner dedup
│
├── jds/                           ← Job Descriptions đã lưu
│   └── techco-senior-java-developer.md
│
├── reports/                       ← Báo cáo đánh giá A-G
│   └── 042-techco-2026-05-15.md
│
├── output/                        ← PDF đã generate (gitignored)
│   ├── cv-nguyen-van-a-techco-2026-05-15.pdf
│   └── cv-nguyen-van-a-techco-2026-05-15.md  ← Snapshot MD
│
├── interview-prep/                ← Tài liệu phỏng vấn
│   ├── story-bank.md              ← STAR+R stories tích lũy
│   ├── techco-senior-java-developer.md          ← Interview intel
│   └── techco-senior-java-developer-tech-qa.md  ← Tech Q&A
│
├── knowledge/                     ← Knowledge Base
│   ├── README.md
│   ├── roles/                     ← 14 role IT (system layer)
│   │   ├── 01-backend.md
│   │   ├── 02-frontend.md
│   │   └── ...
│   └── topics/                    ← Kiến thức cá nhân (user layer)
│       └── _TEMPLATE.md
│
├── modes/                         ← Mode instructions (system layer)
│   ├── _shared.md                 ← Scoring system, global rules
│   ├── _profile.template.md       ← Template cho _profile.md
│   ├── auto-pipeline.md
│   ├── new-cv.md
│   ├── gap-fill.md
│   ├── tech-qa.md
│   ├── interview-prep.md
│   ├── oferta.md
│   ├── pdf.md
│   ├── apply.md
│   ├── scan.md
│   ├── batch.md
│   ├── convert.md
│   ├── cv-switch.md
│   ├── patterns.md
│   ├── followup.md
│   ├── contacto.md
│   └── ... (và các mode khác)
│
├── .claude/skills/career-ops/     ← Claude Code skill definition
│   └── SKILL.md
│
├── .opencode/commands/            ← OpenCode slash commands
│
├── templates/                     ← Templates (system layer)
│   ├── cv-template.html
│   ├── portals.example.yml
│   ├── states.yml
│   ├── README.md
│   └── themes/
│       └── themes.yml
│
├── fonts/                         ← Font tự host cho PDF
│
├── batch/                         ← Batch processing (system layer)
│   ├── batch-prompt.md
│   ├── batch-runner.sh
│   └── tracker-additions/         ← TSV files để merge
│
├── *.mjs                          ← Scripts (system layer)
│   ├── doctor.mjs
│   ├── scan.mjs
│   ├── generate-pdf.mjs
│   ├── verify-pipeline.mjs
│   ├── merge-tracker.mjs
│   ├── normalize-statuses.mjs
│   ├── dedup-tracker.mjs
│   ├── cv-sync-check.mjs
│   ├── analyze-patterns.mjs
│   ├── followup-cadence.mjs
│   ├── check-liveness.mjs
│   ├── update-system.mjs
│   └── test-all.mjs
│
├── dashboard/                     ← Go TUI dashboard
├── docs/                          ← Tài liệu chuyên sâu
│   └── CODEX.md
│
├── package.json
├── package-lock.json
├── CLAUDE.md                      ← Agent instructions
├── AGENTS.md                      ← Codex instructions
├── DATA_CONTRACT.md               ← Phân định User vs System layer
├── LEGAL_DISCLAIMER.md
├── LICENSE
├── README.md                      ← File này
└── VERSION
```

### Quy Ước Đặt Tên File

| Loại file | Format | Ví dụ |
|-----------|--------|-------|
| Reports | `{###}-{company-slug}-{YYYY-MM-DD}.md` | `042-techco-2026-05-15.md` |
| PDFs | `cv-{candidate-slug}-{company-slug}-{YYYY-MM-DD}.pdf` | `cv-nguyen-van-a-techco-2026-05-15.pdf` |
| CV tailored | `cvs/{company-slug}-{role-slug}.md` | `cvs/techco-senior-java-developer.md` |
| JDs | `jds/{company-slug}-{role-slug}.md` | `jds/techco-senior-java-developer.md` |
| Tech-QA | `interview-prep/{company-slug}-{role-slug}-tech-qa.md` | `interview-prep/techco-senior-java-developer-tech-qa.md` |
| Interview intel | `interview-prep/{company-slug}-{role-slug}.md` | `interview-prep/techco-senior-java-developer.md` |
| Tracker additions | `batch/tracker-additions/{###}-{company-slug}.tsv` | `batch/tracker-additions/042-techco.tsv` |

**Quy tắc:**
- `{###}`: số thứ tự 3 chữ số, zero-padded, tăng dần từ reports hiện có
- `{company-slug}`: tên công ty lowercase, thay spaces bằng dấu gạch ngang
- `{role-slug}`: tên role lowercase, thay spaces bằng dấu gạch ngang
- `{candidate-slug}`: tên ứng viên kebab-case từ `profile.yml` (VD: "Nguyễn Văn A" → `nguyen-van-a`)
- `{YYYY-MM-DD}`: ngày hiện tại

### Data Contract Tóm Tắt

| Layer | Files | Ai sở hữu | Bị update ghi đè? |
|-------|-------|-----------|-------------------|
| **User** | `cv.md`, `config/profile.yml`, `modes/_profile.md`, `article-digest.md`, `portals.yml`, `data/*`, `reports/*`, `output/*`, `jds/*`, `cvs/*`, `cv-input/*`, `interview-prep/*`, `knowledge/topics/*` | **Bạn** | **KHÔNG BAO GIỜ** |
| **System** | `modes/_shared.md`, `modes/*.md` (trừ `_profile.md`), `CLAUDE.md`, `*.mjs`, `templates/*`, `fonts/*`, `dashboard/*`, `batch/*`, `knowledge/roles/*`, `.claude/*`, `docs/*`, `VERSION` | **Career-Ops** | Có (khi update) |

**Nguyên tắc vàng:** Nếu bạn muốn customize bất cứ gì (archetypes, narrative, negotiation scripts, scoring, thêm role mới...), LUÔN ghi vào **User Layer**:
- `config/profile.yml` cho cấu hình
- `modes/_profile.md` cho narrative và archetypes
- `knowledge/topics/` cho kiến thức cá nhân
- Không sửa `modes/_shared.md` — nó sẽ bị ghi đè khi update.

### Liên Kết Đến Tài Liệu Chuyên Sâu

| Tài liệu | Nội dung |
|----------|----------|
| `CLAUDE.md` | Agent instructions đầy đủ (scoring, canonical states, pipeline integrity, ethical rules) |
| `AGENTS.md` | Hướng dẫn cho Codex / OpenCode |
| `DATA_CONTRACT.md` | Phân định chi tiết User Layer vs System Layer |
| `docs/CODEX.md` | OpenCode-specific setup |
| `LEGAL_DISCLAIMER.md` | Khuyến cáo pháp lý |
| `knowledge/README.md` | Hướng dẫn sử dụng Knowledge Base |
| `modes/_profile.template.md` | Template để tạo `modes/_profile.md` |
| `config/profile.example.yml` | Template profile đầy đủ |

---

**Career-Ops** — Built for developers, by developers. Không spam, không bịa đặt, không tự động nộp đơn. Chỉ chất lượng.
