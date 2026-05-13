# Interview Intel: Viettel — Java Developer

**Report:** [001](reports/001-viettel-2026-05-13.md)
**Researched:** 2026-05-13
**Sources:** ITviec (45 reviews, 3.7★), JD analysis, CV analysis
**⚠️ Low web intel:** Glassdoor blocked, TopDev no relevant articles. Most data below is [inferred from JD] + general Viettel knowledge.

---

## Process Overview

- **Rounds:** 2-3 vòng (dự kiến) — [inferred from JD: vị trí junior]
- **Format:** Test kỹ thuật → Phỏng vấn technical → Phỏng vấn HR — [inferred, typical Viettel process]
- **Difficulty:** ~3/5 — [inferred, vị trí mở cho fresh grad]
- **Positive experience rate:** ITviec 3.7/5 (45 reviews — toàn Viettel Group, không riêng mảng tech)
- **Known quirks:** Viettel có bài test IQ/GMAT cho một số vị trí — [inferred, chưa xác nhận cho role này]
- **Sources:** ITviec (company page), JD Google Docs

---

## Round-by-Round Breakdown

### Round 1: Test kỹ thuật (dự kiến)
- **Duration:** 45-90 phút — [inferred]
- **Conducted by:** Bộ phận tuyển dụng / technical team
- **What they evaluate:** Java Core, OOP, SQL, giải thuật cơ bản
- **Likely topics [inferred from JD]:**
  - Java cơ bản: OOP (4 tính chất), Abstract class vs Interface, Collection Framework
  - SQL: JOIN, GROUP BY, subquery
  - Thuật toán cơ bản: sắp xếp, tìm kiếm, độ phức tạp
  - Design Pattern: Singleton, Factory, Strategy (JD ghi "Design Patterns")
- **How to prepare:** Ôn Java Core + làm 5-10 bài SQL trên HackerRank

### Round 2: Phỏng vấn technical
- **Duration:** 30-45 phút — [inferred]
- **Conducted by:** Tech lead / Senior developer
- **What they evaluate:** Kinh nghiệm thực tế, cách giải quyết vấn đề, kiến trúc
- **Reported questions [inferred from JD requirements]:**
  - "Bạn đã thiết kế RESTful API như thế nào?" — [inferred from JD: RESTful API]
  - "Kinh nghiệm với CSDL Oracle/MySQL?" — [inferred from JD: Oracle, MySQL]
  - "Cách bạn xử lý transaction trong hệ thống phân tán?" — [inferred from JD: hệ thống viễn thông]
  - "Bạn hiểu gì về Spring MVC và Hibernate?" — [inferred from JD: Spring MVC, Hibernate]
  - "Kể về một lần bạn debugging lỗi production?" — [inferred from JD: sửa lỗi, unit test]
- **How to prepare:** Chạy lại 6 câu chuyện STAR+R trong report Block F

### Round 3: Phỏng vấn HR
- **Duration:** 20-30 phút — [inferred]
- **Conducted by:** HR Viettel
- **What they evaluate:** Cultural fit, mức lương, cam kết lâu dài
- **Likely questions:**
  - "Tại sao bạn chọn Viettel?"
  - "Bạn thấy mình ở đâu trong 2 năm tới?"
  - "Mức lương mong muốn?"
  - "Bạn đang đi học, sắp xếp thời gian thế nào?"
- **How to prepare:** Chuẩn bị câu trả lời ngắn gọn, research về văn hóa Viettel

---

## Likely Questions — Toàn bộ

### Technical

| # | Câu hỏi | Source | Strong answer từ CV |
|---|---------|--------|---------------------|
| 1 | "Thiết kế RESTful API cần lưu ý gì?" | [inferred from JD] | Core Payment Gateway: payment-api, validate tokenKey bằng Redis, idempotency |
| 2 | "Phân biệt Abstract Class vs Interface trong Java?" | [inferred: Java interview chuẩn] | Dùng Interface trong FoodFlow (port-adapter), Abstract class cho base repository |
| 3 | "Kinh nghiệm với Hibernate/JPA?" | [inferred from JD] | Dùng Spring Boot + JPA trong các dự án VNPAY (mặc dù CV không liệt kê riêng) |
| 4 | "Bạn đã tối ưu SQL query thế nào?" | [inferred from JD: Oracle, MySQL] | VMMS: tìm kiếm theo lô, xuất Excel — cần query hiệu quả trên Oracle |
| 5 | "Giải thích cách hoạt động của HashMap?" | [inferred: Java interview kinh điển] | Ôn lại — chưa có câu chuyện trực tiếp từ CV |
| 6 | "REST vs SOAP khác nhau thế nào?" | [inferred from JD: SOAP/RESTful] | Dùng RESTful trong tất cả dự án, chưa dùng SOAP |

### Behavioral

| # | Câu hỏi | Source | Story từ CV |
|---|---------|--------|-------------|
| 7 | "Kể về dự án khó nhất bạn từng làm" | [inferred: phổ biến] | FoodFlow: tự học Kafka, Saga Pattern, Clean Architecture từ con số 0 |
| 8 | "Làm sao bạn xử lý khi bất đồng với team?" | [inferred: teamwork] | VNPAY: phối hợp API Gateway ↔ payment-core, merge code, code review |
| 9 | "Dự án thất bại hoặc bug nghiêm trọng?" | [inferred: phổ biến] | Check Transaction CGV: 3 phiên bản API, các lỗi checksum/authorization |
| 10 | "Bạn tự học công nghệ mới thế nào?" | [inferred: JD ghi 'tự nghiên cứu'] | FoodFlow: tự học Kafka, Docker, DDD qua tài liệu + thực hành |

### Role-Specific (từ JD Viettel)

| # | Câu hỏi | Tại sao họ hỏi | Góc trả lời |
|---|---------|---------------|-------------|
| 11 | "Bạn có kinh nghiệm viết unit test không?" | JD: "Viết và thực hiện unit test" | Thừa nhận ít KN, nhưng sẵn sàng học + đã test thủ công API bằng Postman |
| 12 | "Bạn đã thiết kế CSDL thế nào?" | JD: "Thiết kế CSDL" | VMMS: phân tích yêu cầu → thiết kế bảng → implement |
| 13 | "Bạn biết gì về viễn thông?" | Domain fit | Chưa có KN trực tiếp, nhưng payment gateway cũng là hệ thống high-throughput tương tự |

### Background Red Flags

| # | Red flag | Câu hỏi dự kiến | Cách trả lời |
|---|----------|----------------|-------------|
| 14 | Chưa tốt nghiệp | "Bạn sắp xếp thời gian thế nào?" | "Em tốt nghiệp 03/2026, lịch học hiện tại rất nhẹ. Em sẵn sàng làm full-time ngay." |
| 15 | Chưa có chứng chỉ Oracle | "Bạn có chứng chỉ Oracle Java không?" | "Em chưa thi. Nhưng JD ghi 'ưu tiên', không bắt buộc. Em có 1.5 năm KN thực tế thay vì chứng chỉ. Nếu công ty hỗ trợ, em sẵn sàng thi." |
| 16 | Kinh nghiệm < 2 năm | "Bạn nghĩ mình đủ khả năng không?" | "Em tuy ít năm nhưng đã làm hệ thống production phức tạp (payment gateway). Em học nhanh và có portfolio chứng minh." |

---

## Story Bank Mapping

| # | Chủ đề | Story | Fit | Note |
|---|--------|-------|-----|------|
| 1 | RESTful API / System design | Core Payment Gateway | **strong** | Có sẵn trong Block F |
| 2 | CSDL / Thiết kế | VMMS | **strong** | Có sẵn trong Block F |
| 3 | Distributed transaction | FoodFlow Saga | **strong** | Có sẵn trong Block F |
| 4 | Teamwork | VNPAY team | **strong** | Có sẵn trong Block F |
| 5 | OOP / Design Pattern | FoodFlow Clean Arch | **strong** | Có sẵn trong Block F |
| 6 | Debugging / Tối ưu | Check Transaction CGV | **strong** | Có sẵn trong Block F |
| 7 | HashMap / Collection | — | **none** | Cần ôn lý thuyết, không có story từ CV |
| 8 | SOAP vs REST | — | **partial** | Biết REST, chưa biết SOAP — cần đọc thêm |
| 9 | Unit test | — | **none** | Gap. Có thể thêm JUnit vào FoodFlow trước interview |

**Gaps cần lấp:**
- **Unit test:** Viết 2-3 unit test cho FoodFlow bằng JUnit + Mockito. Mất 1 buổi.
- **HashMap/Collection:** Ôn lại Java Collection Framework. Mất 1-2 giờ.
- **SOAP:** Đọc khái niệm cơ bản, phân biệt với REST. Mất 30 phút.

---

## Technical Prep Checklist

- [ ] Java Core: OOP, Collection, Exception handling — **JD ghi rõ: OOP, Design Patterns**
- [ ] SQL: JOIN, GROUP BY, subquery, indexing — **JD ghi: Oracle, MySQL, SQL Server**
- [ ] Spring Boot / Spring MVC: lifecycle, annotation, dependency injection — **JD ghi: Spring MVC**
- [ ] RESTful API: design principles, HTTP methods, status codes — **JD ghi: Web Services, RESTful**
- [ ] Hibernate/JPA: entity mapping, relationships, lazy vs eager — **JD ghi: Hibernate, JPA**
- [ ] Design Patterns: Singleton, Factory, Strategy, Observer — **JD ghi: Design Patterns**
- [ ] Unit test cơ bản với JUnit — **JD ghi: Viết unit test**
- [ ] Git cơ bản: clone, commit, branch, merge — **JD ghi: làm việc nhóm, merge code**
- [ ] SOAP cơ bản (biết khái niệm là đủ) — **JD ghi: SOAP**
- [ ] TOEIC: đã có 600, không cần ôn thêm

---

## Company Signals

### Values they screen for [inferred from JD + Viettel brand]:
- **Kỷ luật & trách nhiệm** — Viettel là tập đoàn quân đội, văn hóa disciplined
- **Tự học, tự nghiên cứu** — ghi rõ trong JD: "có khả năng tự nghiên cứu"
- **Chịu áp lực cao** — ghi rõ trong JD
- **Làm việc nhóm** — ghi rõ trong JD

### Vocabulary to use:
- "Hệ thống viễn thông", "high-throughput", "ổn định", "bảo mật"
- Viettel tự hào về "Make in Vietnam" — nhấn mạnh sản phẩm nội địa

### Things to avoid:
- ❌ Phàn nàn về áp lực — JD đã ghi "chịu áp lực cao"
- ❌ Tỏ ra chỉ muốn làm remote — Viettel onsite tại Keangnam
- ❌ Nói xấu công ty cũ
- ❌ Tỏ ra không cam kết lâu dài

### Questions to ask them:
1. "Team hiện tại có bao nhiêu người? Em sẽ làm việc trực tiếp với ai?" — [thể hiện quan tâm đến team structure]
2. "Dự án sắp tới team đang làm gì? Công nghệ nào đang được ưu tiên?" — [thể hiện hứng thú kỹ thuật]
3. "Lộ trình phát triển cho vị trí này trong 1-2 năm tới?" — [thể hiện cam kết lâu dài]

---

## Quick Prep Timeline (nếu có 3 ngày trước interview)

```
Ngày 1: Ôn Java Core + SQL         (4h)
        └─ Collection, OOP, JOIN, GROUP BY

Ngày 2: Luyện STAR stories         (3h)
        └─ Tập nói to 6 câu chuyện, mỗi câu 2-3 phút

Ngày 3: Mock interview             (2h)
        └─ Tự hỏi 16 câu trên, trả lời thành tiếng
        └─ Viết 2 unit test cho FoodFlow
```
