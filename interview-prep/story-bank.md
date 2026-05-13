# Story Bank — Nguyễn Duy Văn

> 5 câu chuyện gốc. Mỗi câu chuyện có thể xoay cho nhiều câu hỏi khác nhau.
> Format: STAR+R (Situation, Task, Action, Result, Reflection)

---

## 1. Core Payment Gateway — Thiết kế RESTful API & Async Processing

**Tags:** RESTful API, system design, async processing, payment, validation

**S** — VNPAY cần hệ thống payment gateway xử lý thanh toán chéo giữa các ngân hàng và merchant đối tác. Yêu cầu nghiệp vụ phức tạp: kiểm soát tokenKey duy nhất trong ngày, logic khuyến mãi, nhiều định dạng dữ liệu đầu vào.

**T** — Thiết kế và phát triển RESTful API (payment-api) đáp ứng tất cả yêu cầu nghiệp vụ, đảm bảo không có giao dịch trùng lặp, xử lý bất đồng bộ an toàn.

**A** — Thiết kế RESTful API endpoints, validate tokenKey uniqueness bằng Redis (TTL 24h), xây dựng kiến trúc Publisher-Consumer với RabbitMQ giữa API Gateway và payment-core, tích hợp Webhook/Callback để đồng bộ trạng thái giao dịch real-time.

**R** — Hệ thống hoạt động ổn định trong production. Xử lý thành công các giao dịch thanh toán giữa nhiều ngân hàng và merchant.

**Reflection** — Idempotency key là yếu tố sống còn trong payment system. Học được tầm quan trọng của việc validate chặt chẽ ở tầng API thay vì đẩy xuống database.

---

## 2. FoodFlow — Kiến trúc Microservices với Saga Pattern

**Tags:** architecture, microservices, Kafka, design patterns, initiative, self-learning

**S** — Muốn xây dựng một hệ thống backend hoàn chỉnh để học kiến trúc microservices. Chọn bài toán đặt món & giao hàng vì nó có distributed transaction (Order → Payment → Restaurant).

**T** — Thiết kế hệ thống microservices với Event-Driven architecture, xử lý distributed transaction mà không dùng 2PC (quá nặng cho dự án cá nhân).

**A** — Tự học Apache Kafka từ tài liệu. Triển khai Saga Choreography Pattern: mỗi service publish event, service tiếp theo consume và xử lý. Nếu một service fail, event ngược lại trigger compensation. Áp dụng Transactional Outbox Pattern đảm bảo at-least-once delivery. Thiết kế theo Hexagonal Architecture + DDD, package theo Clean Architecture (domain → application → infrastructure → presentation).

**R** — Hệ thống hoạt động: Order → Payment → Restaurant confirmation → Rollback tự động khi fail. Code public trên GitHub (github.com/vanhaydoi/FoodFlow).

**Reflection** — Saga Choreography phù hợp với hệ thống nhỏ nhưng khó debug khi scale. Nếu làm lại với team lớn hơn, sẽ cân nhắc Saga Orchestration. Design pattern không phải giáo điều — quan trọng là hiểu trade-off.

---

## 3. VMMS — Từ Yêu Cầu Nghiệp Vụ Đến Sản Phẩm

**Tags:** requirement analysis, database design, full-cycle, business understanding

**S** — VNPAY cần module "Quản lý thanh toán chặn" trong hệ thống VMMS. Yêu cầu: tìm kiếm giao dịch bị chặn, thêm mới theo lô, cập nhật theo lô, xuất Excel.

**T** — Nhận yêu cầu nghiệp vụ từ stakeholder, phân tích, thiết kế CSDL, phát triển và bàn giao.

**A** — Ngồi với team nghiệp vụ để hiểu flow chặn giao dịch. Thiết kế bảng database (quan hệ Merchant - Bank - Transaction). Phát triển CRUD APIs + chức năng import/export Excel. Viết query tối ưu cho tìm kiếm theo nhiều tiêu chí. Test với dữ liệu thật.

**R** — Module được đưa vào sử dụng nội bộ. Team nghiệp vụ có thể tự quản lý danh sách chặn mà không cần dev can thiệp.

**Reflection** — Quan trọng nhất là hiểu đúng nghiệp vụ trước khi code. Dành 30% thời gian cho phân tích giúp tiết kiệm 70% thời gian sửa sau này.

---

## 4. Check Transaction CGV — API Evolution & Debugging

**Tags:** debugging, optimization, API versioning, security, problem solving

**S** — Hệ thống kiểm tra giao dịch QR Code cho CGV. Cung cấp 3 API: checkTransaction (V1), CheckTrans (V2), CheckTransForBank. Mỗi version có yêu cầu khác nhau về checksum và authorization.

**T** — Maintain và cải thiện 3 phiên bản API đang chạy song song. Đảm bảo tính đúng đắn của xác thực checksum (MD5/SHA256).

**A** — Phân tích logic từng version, hiểu vì sao có 3 version (mỗi version phục vụ loại khách hàng khác nhau). Implement xác thực checksum MD5/SHA256 cho request. Phân quyền accessKey theo bankCode — mỗi ngân hàng chỉ truy cập được giao dịch của mình. Tối ưu response time bằng Redis caching cho checksum verification.

**R** — Cả 3 API hoạt động ổn định. Response time đáp ứng yêu cầu của đối tác.

**Reflection** — API versioning là cần thiết nhưng đau đầu khi maintain. Backward compatibility nên được thiết kế từ đầu. Đôi khi optimization đơn giản nhất (cache) giải quyết được vấn đề phức tạp.

---

## 5. VNPAY Team — Làm Việc Nhóm Trong Môi Trường Production

**Tags:** teamwork, collaboration, code review, production, communication

**S** — Dự án Core Payment Gateway với team 3-5 người. Mỗi người phụ trách một phần: API Gateway, payment-core, tích hợp đối tác, database.

**T** — Phối hợp giữa các thành phần để hệ thống hoạt động đồng bộ. Đảm bảo code của mình không phá vỡ code của người khác.

**A** — Phân chia task rõ ràng theo module. Merge code thường xuyên (daily) để tránh conflict lớn. Review code của teammate, tập trung vào logic nghiệp vụ (thanh toán không được sai). Pair program khi gặp bug khó. Giao tiếp liên tục qua chat + meeting ngắn hàng ngày.

**R** — Hệ thống tích hợp thành công. Không có rollback production do conflict code.

**Reflection** — Communication quan trọng ngang code. Bug thường xảy ra ở ranh giới giữa các module, không phải trong từng module. Code review không phải để bắt lỗi cú pháp — mà để hiểu logic của nhau.
