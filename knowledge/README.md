# Career-Ops — Knowledge Base

Bộ khung kiến thức dành cho tất cả các role trong lĩnh vực Công nghệ thông tin.

## Mục lục

- [Giới thiệu](#giới-thiệu)
- [Cấu trúc thư mục](#cấu-trúc-thư-mục)
- [Danh sách role](#danh-sách-role)
- [Cách sử dụng](#cách-sử-dụng)
- [Cách tùy chỉnh](#cách-tùy-chỉnh)
- [Dành cho người mới](#dành-cho-người-mới)

## Giới thiệu

Knowledge Base là trung tâm kiến thức của Career-Ops. Nó được sử dụng bởi 2 chức năng chính:

1. **Gap-Fill (`/career-ops gap-fill`)** — Phân tích CV của bạn so với JD, tìm ra những kỹ năng còn thiếu, và tự động sinh dự án mẫu để lấp gap. Knowledge base cung cấp danh sách **dự án mẫu** theo từng role và level.

2. **Tech-QA (`/career-ops tech-qa`)** — Sinh câu hỏi phỏng vấn kỹ thuật theo đúng role, đúng level, và **cá nhân hóa câu trả lời** dựa trên CV của bạn. Knowledge base cung cấp **ngân hàng câu hỏi** theo từng kỹ năng.

## Cấu trúc thư mục

```
knowledge/
├── README.md                        ← File này
├── roles/                           ← Bộ khung kỹ năng cho 14 role IT
│   ├── 01-backend.md               ← Backend Developer
│   ├── 02-frontend.md              ← Frontend Developer
│   ├── 03-fullstack.md             ← Fullstack Developer
│   ├── 04-devops.md                ← DevOps Engineer
│   ├── 05-business-analyst.md      ← Business Analyst
│   ├── 06-tester-qa.md             ← Tester / QA
│   ├── 07-data-engineer.md         ← Data Engineer
│   ├── 08-data-analyst.md          ← Data Analyst
│   ├── 09-mobile-dev.md            ← Mobile Developer
│   ├── 10-embedded.md              ← Embedded Engineer
│   ├── 11-security.md              ← Security Engineer
│   ├── 12-ai-ml.md                 ← AI/ML Engineer
│   ├── 13-project-manager.md       ← Project Manager IT
│   └── 14-product-manager.md       ← Product Manager IT
└── topics/                          ← Kiến thức cá nhân của bạn
    ├── .gitkeep
    └── _TEMPLATE.md                ← Template để bạn tự tạo file
```

## Danh sách role

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

## Cách sử dụng

### 1. Gap-Fill: Tự động lấp gap kỹ năng

Khi bạn paste 1 JD và hệ thống đánh giá CV của bạn bị thiếu kỹ năng, gap-fill mode sẽ:

1. Đọc JD → xác định role (Backend, Frontend, DevOps...)
2. Đọc file role tương ứng trong `knowledge/roles/`
3. So sánh kỹ năng yêu cầu với CV của bạn
4. Tìm gap → chọn dự án mẫu phù hợp từ catalog
5. Sinh project synthetic (mô tả + tech stack + timeline) theo believability rules
6. Ghi thẳng vào `cv.md` và sinh STAR story vào `story-bank.md`

**Ví dụ:** Bạn là Backend Developer, JD yêu cầu Docker + K8s + Jenkins. Hệ thống đọc `01-backend.md`, thấy bạn thiếu 3 kỹ năng này, và sinh ra dự án "CloudDeploy — CI/CD Pipeline cho Spring Boot" để lấp gap.

### 2. Tech-QA: Sinh câu hỏi phỏng vấn kỹ thuật

Khi bạn cần chuẩn bị phỏng vấn, tech-qa mode sẽ:

1. Đọc JD → xác định tech stack cần hỏi (Java, Spring Boot, Kafka...)
2. Đọc file role trong `knowledge/roles/` → lấy ngân hàng câu hỏi
3. Lọc câu hỏi theo:
   - **Kỹ năng:** Chỉ hỏi những skill có trong JD
   - **Level:** Theo cấu hình của bạn (basic/medium/advanced)
   - **Số lượng:** Theo cấu hình (mặc định 30 câu)
4. Với mỗi câu hỏi, sinh **câu trả lời gợi ý** gắn với dự án thật trong CV của bạn

**Ví dụ:** JD yêu cầu Kafka. Hệ thống đọc câu hỏi về Kafka trong `01-backend.md`:
- Q: "Làm sao đảm bảo message không bị duplicate trong Kafka?"
- A: "Em đã implement Transactional Outbox Pattern trong dự án FoodFlow..."

### 3. Tra cứu thủ công

Bạn cũng có thể tự đọc file role để:
- Xem 1 Backend Developer cần biết những gì ở mỗi level
- Chuẩn bị kiến thức trước khi phỏng vấn
- Tự đánh giá CV của mình so với chuẩn ngành

## Cách tùy chỉnh

### Thêm kỹ năng mới vào role

Mở file role tương ứng, thêm dòng vào bảng kỹ năng:

```markdown
| 7 | Tên kỹ năng mới | Mô tả | 10% | tag1, tag2 |
```

Nhớ điều chỉnh trọng số các kỹ năng khác để tổng ~100%.

### Thêm câu hỏi mới vào ngân hàng

Trong section "Câu hỏi phỏng vấn mẫu", thêm câu hỏi dưới mức độ phù hợp:

```markdown
#### Basic
- "Câu hỏi mới của bạn?"
```

### Tạo file kiến thức cá nhân

Vào thư mục `topics/`, tạo file markdown mới. Tham khảo `_TEMPLATE.md`.

Các file trong `topics/` sẽ **không bị hệ thống ghi đè** khi cập nhật — an toàn để bạn tùy chỉnh.

### Tạo role mới (nếu chưa có)

Nếu bạn cần 1 role chưa có trong 14 role trên (ví dụ: Game Developer, Blockchain Developer, UI/UX Designer...):

1. Copy 1 file role có sẵn (ví dụ `01-backend.md`)
2. Đổi tên, đánh số tiếp theo
3. Sửa nội dung cho phù hợp với role mới
4. File mới sẽ được hệ thống tự động đọc

## Dành cho người mới

### Tôi là Backend Developer, tôi nên làm gì?

1. Đọc file `knowledge/roles/01-backend.md` để hiểu Backend Developer cần những gì
2. So sánh với CV của bạn — bạn đang ở level nào? Thiếu kỹ năng gì?
3. Dùng gap-fill mode để hệ thống tự sinh dự án lấp gap
4. Dùng tech-qa mode để luyện câu hỏi phỏng vấn

### Tôi muốn chuyển sang role khác (ví dụ từ Backend sang DevOps)?

1. Đọc file của role mới (`04-devops.md`)
2. So sánh kỹ năng hiện tại với yêu cầu của role mới
3. Xác định gap cần lấp
4. Dùng gap-fill mode để sinh dự án cho role mới

### Các file role có được cập nhật không?

Có. Các file trong `knowledge/roles/` thuộc system layer — sẽ được cập nhật khi có phiên bản career-ops mới. Các file trong `knowledge/topics/` là của bạn — không bao giờ bị ghi đè.

---

**Career-Ops** — AI Job Search Pipeline. Xem thêm tại [README.md](../README.md).
