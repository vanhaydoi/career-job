# Mode: gap-fill — Skill Gap Analysis & Synthetic Project Generation

Khi người dùng muốn phân tích gap giữa CV và JD và sinh dự án để lấp gap. Chạy từ auto-pipeline khi match score dưới ngưỡng, hoặc user gọi trực tiếp `/career-ops gap-fill`.

## Inputs

1. **JD đã parse** (từ auto-pipeline hoặc paste trực tiếp) — role, tech stack, yêu cầu
2. **CV** tại `cv.md` — đọc toàn bộ project hiện có
3. **Profile** tại `config/profile.yml` — đọc section `project_generation`
4. **Knowledge base** tại `knowledge/roles/` — đọc file role tương ứng để có catalog dự án
5. **Story bank** tại `interview-prep/story-bank.md` — để append STAR stories mới

## Step 1 — Xác định Role & Đọc Knowledge Base

Từ JD đã parse, xác định role chính:
- Nếu JD chứa "Java, Spring Boot, REST API" → role = `backend`
- Nếu JD chứa "React, TypeScript, CSS" → role = `frontend`
- Nếu JD chứa "AWS, Docker, Kubernetes, CI/CD" → role = `devops`
- (xem danh sách đầy đủ 14 role tại `knowledge/README.md`)

Đọc file role tương ứng từ `knowledge/roles/{xx}-{role}.md`. Nếu không khớp role nào, dùng `01-backend.md` làm mặc định.

## Step 2 — Phân Tích Gap Kỹ Năng

So sánh từng yêu cầu trong JD với CV hiện tại. Với mỗi kỹ năng JD yêu cầu:

| JD Requirement | CV Evidence | Match | Action |
|----------------|-------------|-------|--------|
| Kubernetes | Không có | missing | ADD |
| Spring Boot | Có trong VMMS, FoodFlow, Payment Gateway | strong | KEEP |
| Unit Test (JUnit) | Chỉ mention qua | weak | IMPROVE |

**Phân loại match:**
- **strong**: Có trong CV với 3+ bullets chi tiết, đúng tech
- **medium**: Có mention nhưng không chi tiết, hoặc tech liên quan
- **weak**: Có mention qua, không có bullet riêng
- **missing**: Hoàn toàn không có trong CV

**Hành động:**
- **KEEP**: Không cần làm gì
- **IMPROVE**: Gợi ý cải thiện mô tả hiện có
- **ADD**: Cần sinh project mới để lấp gap

## Step 3 — Đánh Giá Project Hiện Có

Đọc tất cả project trong CV. Với mỗi project, chấm điểm theo 6 tiêu chí:

| # | Tiêu chí | Trọng số | Cách đánh giá |
|---|----------|----------|---------------|
| 1 | Tech stack match với JD | 40% | Số lượng tech trùng JD / tổng tech JD yêu cầu. 4+ tech trùng → 5/5, 0 tech trùng → 0/5 |
| 2 | Domain relevance | 20% | Cùng domain với JD → 5/5. Domain khác nhưng có thể liên quan → 3/5. Hoàn toàn khác → 1/5 |
| 3 | Description depth | 15% | Số bullets × độ chi tiết. 4+ bullets có metrics → 5/5. Dưới 2 bullets → 2/5 |
| 4 | Recency | 10% | Dự án trong 1 năm → 5/5. 1-2 năm → 3/5. Trên 2 năm → 1/5 |
| 5 | Role alignment | 10% | Cùng role với JD (backend-backend) → 5/5. Khác role (data eng cho backend JD) → 2/5 |
| 6 | Public link (GitHub/URL) | 5% | Có link public → 5/5. Không có → 2/5 |

**Score tổng** = weighted sum của 6 tiêu chí (0-100%). Sau đó phân loại:

| Score | Phân loại | Hành động |
|-------|-----------|-----------|
| >= 80% | STRONG | KEEP — giữ nguyên |
| 50-79% | MEDIUM | IMPROVE — gợi ý cải thiện mô tả |
| < 50% | WEAK | REPLACE — đề xuất thay thế |

**Lưu ý:** `replace_threshold` trong profile.yml mặc định là 40%. Các project trong khoảng 40-50% sẽ được đề xuất cải thiện trước, chỉ thay thế nếu thực sự yếu.

## Step 4 — Đề Xuất Thay Đổi

Tổng hợp từ Step 2 (gap kỹ năng) và Step 3 (đánh giá project):

```
┌─────────────────────────────────────────────────────────────┐
│  📊 PHÂN TÍCH GAP: Senior Backend Developer @ TechCo        │
│  Match: 62%                                                 │
│                                                             │
│  📋 ĐÁNH GIÁ PROJECT HIỆN CÓ:                               │
│  ┌──────────────────────────────────────────────────────┐  │
│  │ ✅ Core Payment Gateway (92%) — KEEP                  │  │
│  │ ✅ FoodFlow (87%) — KEEP                              │  │
│  │ ✅ VMMS (72%) — IMPROVE: thêm bullet về database      │  │
│  │ ⚠️ CGV (65%) — IMPROVE: thêm về security checksum     │  │
│  │ ❌ Facolos (25%) — REPLACE: Python ETL, lệch role     │  │
│  └──────────────────────────────────────────────────────┘  │
│                                                             │
│  🔍 GAP KỸ NĂNG CẦN LẤP:                                    │
│  • Kubernetes — missing → ADD                              │
│  • Jenkins/CI/CD — missing → ADD                           │
│  • AWS (EC2, S3) — missing → ADD                           │
│  • JUnit/Testing — weak → IMPROVE                          │
│                                                             │
│  💡 ĐỀ XUẤT:                                               │
│  1. THAY THẾ Facolos → CloudDeploy (Docker, Jenkins, JUnit)│
│  2. THÊM MỚI → ShopK8s (Docker, K8s, AWS)                 │
│  3. CẢI THIỆN VMMS — thêm bullet về transaction/DB design │
│                                                             │
│  ──────────────────────────────────────────────────────    │
│  Gõ "yes" để áp dụng, "no" để giữ CV gốc,                 │
│  hoặc "edit" để chỉnh sửa đề xuất                         │
└─────────────────────────────────────────────────────────────┘
```

### Xử lý phản hồi của user:

- **"yes"** → Áp dụng tất cả đề xuất, chuyển sang Step 5
- **"no"** → Giữ CV gốc, kết thúc mode
- **"edit"** → User mô tả thay đổi mong muốn, cập nhật đề xuất, hiển thị lại

Nếu user gõ "edit", hiển thị prompt:
```
Bạn muốn chỉnh sửa gì?
Ví dụ: "bỏ project 2", "đổi tên CloudDeploy thành DeployFlow",
"chỉ thay Facolos, không thêm mới", "thêm Redis vào tech stack"
```

## Step 5 — Sinh Synthetic Project

Với mỗi project cần thêm mới hoặc thay thế, sinh project synthetic tuân thủ **6 believability rules**:

### R1: Scale phù hợp level
```
Fresher:   "Xây dựng REST API cho blog cá nhân với Spring Boot"
Junior:    "Xây dựng hệ thống e-commerce với 3 microservices"
Mid:       "Thiết kế hệ thống xử lý 10k request/phút"
Senior:    "Thiết kế hệ thống multi-tenant SaaS platform"
```
KHÔNG sinh project vượt quá level của user (đọc từ `profile.yml → project_generation.level`).

### R2: Không trùng domain với project thật
- Liệt kê tất cả domain của project hiện có trong CV (payment, food delivery, cinema...)
- Chọn domain **khác** cho synthetic project (e-commerce, logistics, healthcare, education, social media, fintech non-payment, IoT, travel, HR tech...)

### R3: Có "vết" thực tế
Mỗi synthetic project PHẢI có ít nhất 1 bullet mô tả thử thách hoặc bài học:
- "Ban đầu dùng REST cho internal communication, nhưng phát hiện latency cao nên chuyển sang gRPC"
- "Gặp vấn đề connection pool khi migrate từ H2 sang PostgreSQL — phải tuning connection timeout"
- "Thử dùng Kafka Streams nhưng thấy overkill cho use-case, chuyển về plain Consumer/Producer"

### R4: Mạch logic theo level
Nếu sinh nhiều project trong 1 lần, project sau phải build trên project trước:
```
Project 1: "REST API cơ bản với Spring Boot"       (học framework)
Project 2: "Microservices với Kafka và Docker"      (nâng cấp từ monolithic)
Project 3: "Deploy lên K8s với CI/CD"               (đưa lên production)
```

### R5: Tech stack có giới hạn
- Fresher/Junior: tối đa 5 công nghệ
- Mid: tối đa 6 công nghệ
- Senior: tối đa 7 công nghệ

### R6: Bullet đồng nhất với project thật
- Đếm số bullet trung bình của project thật (thường 3-5)
- Đếm độ dài trung bình mỗi bullet (thường 1-2 dòng)
- Synthetic project PHẢI khớp — không dài hơn, không ngắn hơn đáng kể

### Cấu trúc project sinh ra:

```markdown
### Tên Project (thời gian)
**Khách hàng / Mục đích:** Mô tả ngắn
- Bullet 1 — mô tả công việc
- Bullet 2 — thử thách hoặc quyết định kỹ thuật
- Bullet 3 — kết quả hoặc bài học
- Bullet 4 (optional) — công nghệ cụ thể
- Bullet 5 (optional) — metric hoặc impact
**Công nghệ:** Tech1, Tech2, Tech3, Tech4, Tech5
```

### Chọn domain từ catalog:

Nếu file role có project catalog, ưu tiên chọn từ catalog. Nếu không có hoặc domain bị trùng, tự sáng tạo project mới tuân thủ R1-R6.

## Step 6 — Ghi Vào CV

Sau khi user đồng ý:

1. **Thay thế project yếu:** Xóa project bị đánh dấu REPLACE khỏi `cv.md`, chèn synthetic project vào cùng vị trí
2. **Thêm project mới:** Append synthetic project vào cuối section `## Dự án` trong `cv.md`
3. **Cải thiện project:** Nếu user chọn IMPROVE, thêm/chỉnh sửa bullet trong project hiện có

**Giữ nguyên format CV** — cùng ngôn ngữ (vi/en), cùng style bullet, cùng cách viết.

## Step 7 — Sinh STAR Story

Với mỗi synthetic project mới, sinh 1 STAR+R story và append vào `interview-prep/story-bank.md`:

```markdown
## N. Tên Synthetic Project — Mô tả ngắn
**Tags:** tag1, tag2, tag3

**S** — (bối cảnh: tại sao làm project này)
**T** — (nhiệm vụ: cần đạt được gì)
**A** — (hành động: đã làm gì, quyết định kỹ thuật)
**R** — (kết quả: project hoàn thành, học được gì)
**Reflection** — (bài học: trade-off, điều sẽ làm khác)
```

Story number là số tiếp theo trong story bank. Tags khớp với kỹ năng được lấp.

## Step 8 — Post-Generation

Sau khi ghi CV:

1. **Thông báo:** "Đã cập nhật CV. Git diff để xem thay đổi. Có thể revert bằng git checkout."
2. **Đề xuất tiếp theo:** "Bạn có muốn sinh câu hỏi phỏng vấn kỹ thuật cho JD này không? (tech-qa mode)"
3. **Quay lại auto-pipeline:** Nếu được gọi từ auto-pipeline, tiếp tục step generate PDF

## Constraints từ Profile

Luôn đọc `config/profile.yml → project_generation` và áp dụng:

- `enabled: false` → không chạy gap-fill, thông báo "Gap-fill đang bị tắt trong profile"
- `max_total_projects` → tổng project (thật + synthetic) không vượt quá con số này
- `max_new_projects` → mỗi lần chạy không thêm quá số này
- `max_replacements` → mỗi lần chạy không thay thế quá số này
- `min_keep_projects` → luôn giữ ít nhất số này project gốc (không thay thế)
- `add_threshold` → chỉ đề xuất thêm project mới nếu match dưới ngưỡng này
- `replace_threshold` → chỉ đề xuất thay thế nếu project yếu dưới ngưỡng này
- `constraints` → danh sách ràng buộc bổ sung (ví dụ: "Không sinh project về AI/ML")
- `domains` → danh sách domain ưu tiên

## NEVER

1. Ghi CV khi user chưa đồng ý
2. Sinh project vượt quá level của user
3. Sinh project trùng domain với project thật
4. Sinh project không có "vết" (quá hoàn hảo → mất believable)
5. Tạo project với tech stack > limit theo level
6. Tiết lộ với user rằng project là synthetic trong output CV (trong CV, coi như thật)
