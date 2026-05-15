# Mode: tech-qa — Technical Interview Question Generation

Khi user muốn sinh câu hỏi phỏng vấn kỹ thuật từ knowledge base. Chạy từ auto-pipeline (sau gap-fill) hoặc user gọi trực tiếp `/career-ops tech-qa`.

## Inputs

1. **JD đã parse** — tech stack, role, seniority level
2. **CV** tại `cv.md` — đọc tất cả project (thật + synthetic)
3. **Profile** tại `config/profile.yml` — đọc section `interview_prep`
4. **Knowledge base** tại `knowledge/roles/` — đọc file role tương ứng
5. **Story bank** tại `interview-prep/story-bank.md` — đọc STAR stories để map câu hỏi behavioral
6. **Existing tech-qa file** (nếu có) — `interview-prep/{company-slug}-{role-slug}-tech-qa.md`

## Step 1 — Xác Định Role & Đọc Knowledge Base

Từ JD, xác định role (backend, frontend, devops, ...) — xem danh sách đầy đủ 14 role tại `knowledge/README.md`.

Đọc file role tương ứng từ `knowledge/roles/{xx}-{role}.md`. Nếu JD khớp nhiều role, đọc tất cả nhưng ưu tiên role chính.

## Step 2 — Lọc Kỹ Năng Cần Hỏi

Từ JD, trích xuất danh sách tech stack và kỹ năng yêu cầu:

```
JD yêu cầu: Java Core, Spring Boot, Kafka, Docker, PostgreSQL, JUnit, REST API
```

Đối chiếu với knowledge base role file — chỉ sinh câu hỏi cho những kỹ năng CÓ trong cả JD và knowledge base:

| JD Requirement | In Knowledge Base? | In CV? | Generate Questions? |
|----------------|-------------------|--------|---------------------|
| Java Core | ✅ (trong 01-backend.md) | ✅ | YES |
| Spring Boot | ✅ | ✅ | YES |
| Kafka | ✅ | ✅ | YES |
| Docker | ✅ | ✅ | YES |
| PostgreSQL | ✅ | ✅ | YES |
| JUnit | ✅ | ✅ | YES |
| REST API | ✅ | ✅ | YES |

**Kỹ năng bị loại:**
- Có trong JD nhưng không có trong knowledge base → ghi chú "outside scope of knowledge base"
- Có trong knowledge base nhưng không có trong JD → không hỏi (không liên quan)

## Step 3 — Chọn Level Câu Hỏi

Đọc `config/profile.yml → interview_prep.levels`. Mặc định: `[basic, medium]`.

| Level | Mô tả | Khi nào dùng |
|-------|-------|-------------|
| basic | Kiến thức nền tảng, định nghĩa, so sánh | Fresher, Junior |
| medium | Áp dụng, giải thích cơ chế, trade-off | Junior, Mid |
| advanced | System design, tối ưu, kiến trúc | Mid, Senior |

Nếu user có `level: "senior"` trong profile, tự động thêm `advanced`.

## Step 4 — Sinh Câu Hỏi & Câu Trả Lời

Với mỗi kỹ năng được chọn, đọc câu hỏi từ knowledge base role file (section "Câu hỏi phỏng vấn mẫu theo kỹ năng"). Lọc theo level đã chọn.

### Với mỗi câu hỏi, sinh:

```markdown
### Câu {N}: {nội dung câu hỏi}

**Mức độ:** Basic / Medium / Advanced

**📎 Từ CV của bạn:**
{Đoạn mô tả mapping câu hỏi với project/experience thực tế trong CV}

**💡 Gợi ý trả lời:**
{2-4 câu trả lời mẫu, dùng "Em đã..." thay vì "Bạn đã..." vì đây là câu trả lời cá nhân hóa}
```

### Quy tắc contextualization (gắn với CV):

**Khi CV có project liên quan:**
```
❓ "Làm sao đảm bảo message không bị duplicate trong Kafka?"

📎 Từ CV của bạn:
FoodFlow — "Em đã implement Transactional Outbox Pattern để đảm bảo 
at-least-once delivery giữa Database và Kafka. Cụ thể: mỗi khi Order 
Service tạo order, thay vì gọi trực tiếp Kafka, em ghi event vào bảng 
outbox trong cùng transaction với order..."

💡 Gợi ý trả lời:
Em đã gặp vấn đề này khi xây dựng FoodFlow. Có 3 cách chính:
1. Idempotent Consumer — consumer kiểm tra unique key trước khi xử lý
2. Transactional Outbox — ghi event + business data trong cùng DB transaction
3. Kafka Idempotent Producer — enable idempotence + transactional producer

Em chọn Transactional Outbox vì guarantee mạnh nhất, phù hợp với bài toán 
order processing. Chi tiết: [kể về implementation trong FoodFlow]...
```

**Khi CV KHÔNG có project liên quan:**
```
❓ "Kubernetes Pod, Service, Deployment khác gì?"

📎 Từ CV của bạn:
Chưa có kinh nghiệm thực tế với Kubernetes. Đây là kiến thức lý thuyết 
cần nắm khi phỏng vấn.

💡 Gợi ý trả lời:
- Pod: đơn vị nhỏ nhất trong K8s, chứa 1 hoặc nhiều container
- Service: expose Pod ra network, load balancing, service discovery
- Deployment: quản lý Pod lifecycle, rolling update, rollback
...
```

**Khi câu hỏi liên quan đến synthetic project (vừa được gap-fill thêm vào):**
```
❓ "Làm sao setup CI/CD pipeline với Jenkins?"

📎 Từ CV của bạn:
CloudDeploy — "Em đã setup Jenkins pipeline để tự động build Docker image 
từ GitHub, chạy unit test với JUnit, và deploy lên AWS EC2..."

💡 Gợi ý trả lời:
Em đã làm điều này trong dự án CloudDeploy. Pipeline gồm 3 stage:
1. Build — checkout code, build JAR với Maven
2. Test — chạy JUnit test, generate coverage report
3. Deploy — build Docker image, push lên registry, SSH deploy lên EC2
[tiếp tục với implementation detail từ synthetic project]...
```

**QUAN TRỌNG:** Câu trả lời cho synthetic project phải tự tin và nhất quán như project thật. Không được có dấu hiệu "đây là project fake".

## Step 5 — Tổ Chức Output

Nhóm câu hỏi theo kỹ năng, trong mỗi nhóm sắp xếp basic trước, medium sau, advanced cuối:

```markdown
# Tech Q&A: {Company} — {Role}

**JD:** {link hoặc "paste"}
**Ngày sinh:** {YYYY-MM-DD}
**Knowledge base:** {tên file role}
**Số câu hỏi:** {N}
**Level:** {basic, medium}

---

## Java Core

### Câu 1: Phân biệt Abstract Class vs Interface?
**Mức độ:** Basic
**📎 Từ CV của bạn:** ...
**💡 Gợi ý trả lời:** ...

### Câu 2: HashMap hoạt động như thế nào?
...

## Spring Boot

### Câu 8: Dependency Injection là gì?
...

## Kafka

### Câu 15: Làm sao đảm bảo message không bị mất?
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

## Step 6 — Lưu Output

1. Tạo thư mục `interview-prep/` nếu chưa có
2. Lưu file: `interview-prep/{company-slug}-{role-slug}-tech-qa.md`
   - `{company-slug}` = tên công ty lowercase, không dấu cách, dùng dấu gạch ngang
   - `{role-slug}` = tên role lowercase, không dấu cách, dùng dấu gạch ngang
3. Nếu file đã tồn tại, hỏi user: "File tech-qa cho company này đã tồn tại. Overwrite hay append?"

## Step 7 — Post-Generation

Sau khi lưu:

1. **Thông báo:** "Đã sinh {N} câu hỏi cho {role} tại {company}. File: `interview-prep/{file}.md`"
2. **Đề xuất:** "Bạn có muốn tôi chạy thêm interview-prep mode để kết hợp với company research và STAR stories không?"
3. **Quick review:** Hiển thị 3 câu hỏi đầu tiên để user xem chất lượng

## Constraints từ Profile

Luôn đọc `config/profile.yml → interview_prep`:

- `question_count` → số câu hỏi tối đa (mặc định 30)
- `levels` → chỉ sinh câu hỏi ở các level này (ví dụ: `[basic, medium]`)
- `contextualized: true` → luôn sinh câu trả lời cá nhân hóa (Option B)
- `contextualized: false` → chỉ sinh câu hỏi, không sinh câu trả lời (Option A — nhanh hơn nhưng ít giá trị)

## NEVER

1. Sinh câu hỏi cho kỹ năng không có trong JD
2. Sinh câu hỏi cho kỹ năng không có trong knowledge base (trừ khi user tự thêm vào `knowledge/topics/`)
3. Sinh câu trả lời có vẻ "máy móc" hoặc "AI-written" — phải tự nhiên, dùng "Em đã..."
4. Tiết lộ project synthetic trong câu trả lời — coi như thật
5. Vượt quá `question_count` trong profile
