# Backend Developer — Skill Framework

## Tổng quan
- **Tên role:** Backend Developer
- **Level:** Fresher → Junior → Mid → Senior → Lead/Architect
- **Mô tả:** Phát triển logic phía server, thiết kế API, quản lý cơ sở dữ liệu, thiết kế hệ thống. Làm việc với Java, .NET, Python, Node.js, Go, hoặc các ngôn ngữ server-side khác.
- **Tags:** backend, server, api, database, microservices, java, spring, .net, nodejs, python, go

## Kỹ năng theo cấp độ

### Level 1: Fresher/Junior (0-2 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Ngôn ngữ lập trình (Java/C#/Python/Node.js/Go) | Cú pháp cơ bản, OOP, Collection/Array, Exception handling, Package management | 25% | java, csharp, python, nodejs, go, core |
| 2 | SQL cơ bản | SELECT, INSERT, UPDATE, DELETE, JOIN, GROUP BY, subquery, indexing cơ bản | 20% | database, sql, mysql, postgresql, oracle |
| 3 | Framework cơ bản (Spring Boot/Express/Django/.NET) | Dependency Injection, Routing, Controller, Service layer, ORM/ODM cơ bản | 20% | spring, express, django, framework |
| 4 | REST API | HTTP methods (GET/POST/PUT/DELETE), status codes, request/response, validation | 15% | api, rest, http, json |
| 5 | Git cơ bản | clone, commit, branch, merge, pull request, .gitignore | 10% | git, version-control |
| 6 | Testing cơ bản | Unit test (JUnit/xUnit/pytest), test assertion, test coverage cơ bản | 10% | testing, junit, xunit, pytest |

### Level 2: Junior/Mid (1-4 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Framework nâng cao | AOP, Middleware, Interceptor, Security (OAuth2/JWT), Caching, Batch processing | 20% | spring, security, caching, middleware |
| 2 | Database nâng cao | Indexing strategy, Transaction management (ACID), Locking (optimistic/pessimistic), Migration (Flyway/Liquibase), Query optimization | 20% | database, transaction, indexing, migration |
| 3 | Message Queue | Kafka/RabbitMQ/SQS: Producer, Consumer, Topic/Queue, Partition, Offset, Delivery semantics (at-most-once, at-least-once, exactly-once) | 15% | kafka, rabbitmq, messaging, async |
| 4 | Microservices | Service Discovery, API Gateway, Circuit Breaker, Service-to-service communication (REST/gRPC/Message) | 15% | microservices, distributed, gateway |
| 5 | Docker | Dockerfile, Docker Compose, Multi-stage build, Image optimization, Network, Volume | 10% | docker, container, devops |
| 6 | CI/CD cơ bản | Jenkins/GitHub Actions/GitLab CI, Pipeline stages (build → test → deploy), Automated testing in CI | 10% | ci-cd, jenkins, github-actions |
| 7 | Design Patterns | Singleton, Factory, Builder, Strategy, Observer, Repository, Adapter | 10% | design-patterns, architecture |

### Level 3: Mid/Senior (3+ năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | System Design | Scalability (horizontal/vertical), High Availability, CAP theorem, Load Balancing, Caching strategy (Redis/Memcached), Database sharding | 25% | system-design, scalability, architecture |
| 2 | Distributed Systems | Event-Driven Architecture, Saga Pattern (Choreography/Orchestration), CQRS, Event Sourcing, Distributed transaction, Consistency models | 25% | distributed, saga, cqrs, event-driven |
| 3 | Kubernetes | Pod, Service, Deployment, ConfigMap, Secret, Ingress, Helm, Horizontal Pod Autoscaler | 15% | kubernetes, k8s, container-orchestration |
| 4 | Cloud (AWS/GCP/Azure) | EC2/GCE, S3/Blob, RDS/Cloud SQL, Lambda/Cloud Functions, IAM, VPC | 15% | cloud, aws, gcp, azure |
| 5 | Performance Optimization | Profiling (JProfiler/pprof), Connection pooling, Query optimization (EXPLAIN), Caching strategy, Async processing, Batch vs Stream | 10% | performance, optimization, profiling |
| 6 | Security | OWASP Top 10, SQL Injection, XSS, CSRF, Rate Limiting, API authentication (API Key/JWT/OAuth2), Secrets management | 10% | security, owasp, authentication |

### Level 4: Senior/Lead (5+ năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Architecture Decision | ADR (Architecture Decision Records), Trade-off analysis (build vs buy, monolith vs microservices), Technical strategy, RFC process | 25% | architecture, leadership, strategy |
| 2 | Team Leadership | Code review culture, Mentoring, Technical roadmap, Cross-team collaboration, Hiring & interviewing | 20% | leadership, mentoring, management |
| 3 | System Reliability | SLO/SLI/SLA, Incident response, Post-mortem, Chaos engineering, Disaster recovery, Multi-region deployment | 20% | reliability, sre, incident |
| 4 | Cost Optimization | Cloud cost analysis, Resource right-sizing, Reserved instances, Storage tiering, Data transfer optimization | 15% | cost, cloud, optimization |
| 5 | Compliance & Governance | GDPR, SOC2, Data privacy, Audit logging, Access control (RBAC/ABAC), Change management | 10% | compliance, governance, security |
| 6 | Technical Communication | Architecture documentation, Technical blog posts, Conference talks, Stakeholder presentations | 10% | communication, documentation |

## Câu hỏi phỏng vấn mẫu theo kỹ năng

### Java Core
#### Basic
- "Phân biệt Abstract Class và Interface trong Java? Khi nào dùng cái nào?"
- "HashMap hoạt động như thế nào? Tại sao cần override hashCode() và equals()?"
- "Checked Exception vs Unchecked Exception khác nhau thế nào? Cho ví dụ."
- "Phân biệt String, StringBuilder và StringBuffer?"
- "Giải thích 4 tính chất của OOP: Encapsulation, Inheritance, Polymorphism, Abstraction."

#### Medium
- "Giải thích Java Memory Model: Stack vs Heap? Một object được lưu ở đâu?"
- "Cơ chế hoạt động của Garbage Collector trong Java? Các loại GC?"
- "CompletableFuture dùng để làm gì? So sánh với Future và Thread?"
- "Generics trong Java là gì? Type Erasure hoạt động thế nào?"
- "Làm sao để tạo một Immutable Class trong Java?"

#### Advanced
- "Thiết kế một hệ thống xử lý 1 triệu request/giây bằng Java. Cần lưu ý gì?"
- "So sánh Virtual Threads (Java 21) với Reactive Programming (WebFlux)?"
- "Làm sao tối ưu GC cho ứng dụng low-latency? Các GC tuning flags quan trọng?"

### SQL / Database
#### Basic
- "Viết query lấy top 5 khách hàng có tổng đơn hàng cao nhất?"
- "Phân biệt INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL OUTER JOIN?"
- "INDEX là gì? Tại sao cần index? Khi nào không nên dùng index?"
- "GROUP BY và HAVING khác WHERE thế nào?"

#### Medium
- "Giải thích ACID trong database transaction? Mỗi chữ có ý nghĩa gì?"
- "Optimistic Locking vs Pessimistic Locking khác gì? Khi nào dùng cái nào?"
- "Làm sao tối ưu một query chạy chậm? Các bước phân tích?"
- "Database Sharding là gì? Các chiến lược sharding phổ biến?"

#### Advanced
- "Thiết kế schema cho hệ thống e-commerce xử lý 10k orders/giờ?"
- "So sánh SQL vs NoSQL? Khi nào chọn cái nào cho microservices?"
- "Eventual Consistency là gì? Làm sao xử lý conflict trong distributed database?"

### Spring Boot
#### Basic
- "Dependency Injection là gì? Các loại injection trong Spring?"
- "@Component, @Service, @Repository, @Controller khác gì nhau?"
- "Spring Bean lifecycle hoạt động thế nào?"
- "@Autowired hoạt động thế nào? Các cách inject dependency?"

#### Medium
- "Spring AOP là gì? Dùng để làm gì? Cho ví dụ thực tế?"
- "Cách Spring xử lý transaction với @Transactional? Propagation levels?"
- "Spring Security hoạt động thế nào? JWT authentication flow?"
- "Làm sao implement caching trong Spring Boot? @Cacheable, @CacheEvict?"

#### Advanced
- "So sánh Spring WebFlux (reactive) với Spring MVC (servlet)? Khi nào dùng cái nào?"
- "Làm sao xử lý distributed tracing trong hệ thống Spring Boot microservices?"
- "Circuit Breaker pattern trong Spring Cloud? Resilience4j vs Hystrix?"

### Message Queue (Kafka / RabbitMQ)
#### Basic
- "Message Queue là gì? Tại sao cần dùng message queue?"
- "Kafka vs RabbitMQ khác gì? Khi nào dùng cái nào?"
- "Producer, Consumer, Topic, Partition trong Kafka là gì?"

#### Medium
- "Làm sao đảm bảo message không bị mất trong Kafka? Các cấu hình liên quan?"
- "Delivery semantics: at-most-once, at-least-once, exactly-once khác gì?"
- "Consumer Group trong Kafka hoạt động thế nào? Rebalancing là gì?"
- "Làm sao xử lý duplicate message trong consumer?"

#### Advanced
- "Thiết kế hệ thống event-driven với Kafka cho bài toán order processing?"
- "Kafka Streams vs Kafka Connect vs plain Consumer/Producer?"
- "Làm sao monitoring và troubleshoot Kafka cluster bị lag?"

### Docker / Kubernetes
#### Basic
- "Docker là gì? Container khác VM thế nào?"
- "Dockerfile, Image, Container khác gì nhau?"
- "Các lệnh Docker cơ bản: build, run, ps, stop, logs?"

#### Medium
- "Docker Compose dùng để làm gì? Multi-container app setup?"
- "Multi-stage build trong Docker là gì? Lợi ích?"
- "Kubernetes Pod, Service, Deployment là gì?"

#### Advanced
- "Làm sao debug container đang chạy? exec, logs, inspect?"
- "Thiết kế CI/CD pipeline deploy lên Kubernetes với rolling update?"
- "Làm sao scale application trên Kubernetes? HPA hoạt động thế nào?"

### System Design
#### Basic
- "Thiết kế URL shortener như bit.ly?"
- "Thiết kế hệ thống chat 1-1?"
- "REST API design best practices?"

#### Medium
- "Thiết kế hệ thống e-commerce cơ bản: User, Product, Order?"
- "Làm sao xử lý distributed transaction trong microservices?"
- "Database nào cho bài toán gì? SQL vs NoSQL vs Cache vs Search?"

#### Advanced
- "Thiết kế hệ thống thanh toán xử lý 10k TPS?"
- "Thiết kế hệ thống real-time notification cho 10M users?"
- "Đánh đổi giữa Consistency, Availability, Partition Tolerance (CAP)?"

### Design Patterns
#### Basic
- "Singleton Pattern là gì? Các cách implement thread-safe Singleton?"
- "Factory Pattern vs Abstract Factory Pattern khác gì?"
- "Strategy Pattern là gì? Cho ví dụ thực tế?"

#### Medium
- "Observer Pattern vs Pub/Sub Pattern? Implement trong Java thế nào?"
- "Decorator Pattern vs Proxy Pattern khác gì?"
- "Repository Pattern và DAO Pattern khác gì?"

#### Advanced
- "Khi nào dùng CQRS? Trade-off so với CRUD truyền thống?"
- "Event Sourcing là gì? Khi nào phù hợp?"
- "Hexagonal Architecture vs Clean Architecture vs Traditional Layered?"

## Dự án mẫu để lấp gap

### Level Junior — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "REST API cho Blog cá nhân" | Spring Boot, JPA, REST API, Validation | 2-3 tuần | Java, Spring Boot, MySQL, JUnit |
| 2 | "Task Management API với Authentication" | Spring Security, JWT, CRUD, Role-based access | 3-4 tuần | Java, Spring Boot, Spring Security, PostgreSQL, Docker |
| 3 | "CI/CD Pipeline cho Spring Boot App" | Jenkins, Docker, JUnit, Automated testing | 2 tuần | Java, Spring Boot, Jenkins, Docker, JUnit, GitHub Actions |
| 4 | "E-Commerce REST API" | RESTful design, JPA relationships, pagination, file upload | 4 tuần | Java, Spring Boot, MySQL, Redis, Docker |
| 5 | "Notification Service với RabbitMQ" | Message Queue, Async processing, Email/SMS integration | 3 tuần | Java, Spring Boot, RabbitMQ, PostgreSQL, Docker |

### Level Mid — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "Microservices Order Management" | Service discovery, API Gateway, Circuit Breaker, Inter-service communication | 6-8 tuần | Java, Spring Boot, Spring Cloud, Kafka, Docker, PostgreSQL |
| 2 | "Event-Driven Payment Processing" | Kafka, Saga Pattern, Transactional Outbox, CQRS | 6-8 tuần | Java, Spring Boot, Kafka, PostgreSQL, MongoDB, Docker |
| 3 | "API Gateway với Rate Limiting" | Rate limiting, Authentication, Routing, Monitoring | 3-4 tuần | Java, Spring Cloud Gateway, Redis, Prometheus, Grafana |
| 4 | "Deploy Microservices lên AWS" | AWS EC2, RDS, S3, Docker Compose, CI/CD | 4 tuần | Java, Spring Boot, Docker, AWS (EC2/RDS/S3), GitHub Actions |
| 5 | "Real-time Analytics Dashboard Backend" | WebSocket, SSE, Time-series DB, Caching | 4-6 tuần | Java, Spring Boot, WebSocket, Redis, InfluxDB, Docker |

### Level Senior — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "Multi-tenant SaaS Platform" | Multi-tenancy, Database per tenant, Row-level security | 8-12 tuần | Java, Spring Boot, PostgreSQL, Redis, Docker, K8s |
| 2 | "High-Throughput API Gateway" | 10k+ TPS, Circuit breaker, Distributed rate limiting, Observability | 8 tuần | Java, Spring Cloud, Redis Cluster, K8s, Prometheus, Grafana |
| 3 | "Distributed Job Scheduler" | Leader election, Job distribution, Retry, Monitoring | 6 tuần | Java, Spring Boot, Kafka, ZooKeeper, PostgreSQL, K8s |
