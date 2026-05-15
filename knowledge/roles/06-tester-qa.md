# Tester / QA Engineer — Skill Framework

## Tổng quan
- **Tên role:** Tester / QA Engineer
- **Level:** Manual Tester → Automation Tester → Senior QA → QA Lead
- **Mô tả:** Đảm bảo chất lượng phần mềm thông qua manual testing và automation testing. Thiết kế test case, thực thi test, báo cáo bug, và xây dựng automation framework.
- **Tags:** tester, qa, automation, selenium, manual-testing, api-testing, performance, playwright, cypress, jmeter

## Kỹ năng theo cấp độ

### Level 1: Manual Tester / Fresher (0-2 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Test Case Design | Test case template chuẩn, Test scenario design, Boundary value analysis, Equivalence partitioning, Decision table, Positive/Negative test case | 25% | test-case, test-design, technique |
| 2 | Manual Testing | Black-box testing, Functional testing, Regression testing, Smoke testing, Sanity testing, Exploratory testing, UAT support | 25% | manual-testing, functional, regression |
| 3 | Bug Reporting & Management | Bug lifecycle, Severity vs Priority, Bug report template, Steps to reproduce, Root cause hypothesis, Bug triage process | 20% | bug-reporting, bug-lifecycle, jira |
| 4 | SQL cơ bản để test | SELECT, JOIN, WHERE, GROUP BY, Verify data trong database, Data integrity check | 10% | sql, database, verification |
| 5 | API Testing cơ bản | Postman, Request/Response validation, Status code check, Schema validation cơ bản, Collection runner | 10% | api-testing, postman, rest |
| 6 | Agile Testing | Scrum testing lifecycle, Sprint test planning, In-sprint testing, Definition of Done, Test report | 10% | agile, scrum, methodology |

### Level 2: Automation Tester / Mid (2-4 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Automation Framework cơ bản (Selenium/Cypress/Playwright) | Page Object Model, Locator strategy (XPath, CSS), Wait strategy (implicit/explicit/fluent), TestNG/JUnit/Mocha, Assertions | 25% | selenium, cypress, playwright, pom |
| 2 | API Automation Testing | RestAssured/SuperTest/Postman Newman, Request chaining, Data-driven API test, Schema validation (JSON Schema), Authentication handling | 20% | api-automation, rest-assured, postman |
| 3 | Test Data Management | Test data strategy, Data factory pattern, Fixtures, Data-driven testing (Excel/CSV/JSON), Database seeding | 15% | test-data, data-driven, factory |
| 4 | CI/CD Integration cho Test | Jenkins/GitHub Actions/GitLab CI pipeline, Scheduled test runs, Test report integration (Allure/Extent), Git hooks trigger | 15% | ci-cd, jenkins, github-actions |
| 5 | Performance Testing cơ bản | JMeter/K6 cơ bản, Thread Group, HTTP Request sampler, Listener, Load test vs Stress test cơ bản | 10% | performance, jmeter, k6, load-testing |
| 6 | Mobile Testing cơ bản | Appium cơ bản, Emulator/Simulator, Real device testing, Mobile-specific test case (network, orientation, interrupt) | 10% | mobile-testing, appium, android, ios |
| 7 | Code Review & Git nâng cao | Git branching strategy, Code review best practice, Pull request review, Merge conflict resolution | 5% | git, code-review, version-control |

### Level 3: Senior QA / Advanced (4-6 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Automation Architecture | Custom automation framework design, Hybrid framework, Keyword-driven/Data-driven, BDD (Cucumber/SpecFlow), Cross-browser testing (Selenium Grid/Docker) | 25% | automation-architecture, bdd, cucumber |
| 2 | Performance & Load Testing nâng cao | JMeter nâng cao (correlation, parameterization, distributed), K6 scripting, Gatling, Performance bottleneck analysis, Capacity planning, NFR definition | 20% | performance, jmeter, k6, bottleneck |
| 3 | Security Testing | OWASP Top 10 testing, SQL Injection, XSS, CSRF, Authentication bypass, Authorization testing, Basic penetration testing, Burp Suite/ZAP | 15% | security-testing, owasp, penetration |
| 4 | Contract & Integration Testing | Contract testing (Pact), Integration test strategy, End-to-End test, Service virtualization, Consumer-driven contract | 15% | contract-testing, pact, integration |
| 5 | Test Environment Management | Docker/Testcontainers, Environment provisioning, Service virtualization (WireMock/Mountebank), Test data management at scale | 10% | environment, docker, wiremock |
| 6 | CI/CD Pipeline nâng cao | Parallel execution, Test sharding, Flaky test detection, Test result analytics, Canary deployment testing | 10% | ci-cd, devops, flakiness |
| 7 | Non-Functional Testing | Reliability testing, Failover testing, Disaster recovery testing, Compatibility testing, Accessibility testing (WCAG) | 5% | nft, reliability, accessibility |

### Level 4: QA Lead / Manager (6+ năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | QA Strategy & Process | Quality strategy definition, QA maturity assessment, Shift-left/Shift-right testing, Risk-based testing, Test policy & governance, QA metrics (KPI/OKR) | 25% | strategy, governance, maturity |
| 2 | Team Leadership | QA team building, Hiring & interviewing, Mentoring, Career development, Performance review, Resource planning, Conflict resolution | 20% | leadership, mentoring, management |
| 3 | Test Automation Strategy | Automation pyramid/Trophy, ROI analysis for automation, Tool evaluation & selection, Proof of Concept, Automation coverage target | 20% | automation-strategy, roi, tooling |
| 4 | DevOps & Quality Engineering | Continuous Testing, Quality Gates, Shift-left testing, Test infrastructure as code, Observability for testing, Production monitoring | 15% | devops, quality-engineering, continuous-testing |
| 5 | Release Management | Release criteria, Go/No-Go decision, Risk assessment, Rollback strategy, Change management, CAB (Change Advisory Board) | 10% | release, go-live, risk |
| 6 | Budget & Vendor Management | QA budget planning, Tool licensing, Vendor evaluation (testing services), Outsourcing strategy | 10% | budget, vendor, outsourcing |

## Câu hỏi phỏng vấn mẫu theo kỹ năng

### Test Design & Manual Testing
#### Basic
- "Phân biệt Test Case, Test Scenario, và Test Script? Cho ví dụ."
- "Boundary Value Analysis và Equivalence Partitioning là gì? Cho ví dụ."
- "Severity và Priority khác gì? Cho 1 bug high severity nhưng low priority."
- "Smoke Testing vs Sanity Testing vs Regression Testing khác gì?"
- "Exploratory Testing là gì? Khi nào nên dùng?"
- "Positive Test vs Negative Test: viết đủ bao nhiêu là đủ?"

#### Medium
- "Làm sao thiết kế test case cho 1 form đăng ký có 15 fields?"
- "Decision Table Testing là gì? Cho ví dụ thực tế."
- "Test coverage: làm sao biết bạn đã test đủ? Metrc nào để đo?"
- "State Transition Testing là gì? Áp dụng cho bài toán login thế nào?"
- "Làm sao test khi requirement không rõ ràng hoặc thiếu?"

#### Advanced
- "Chiến lược test cho hệ thống có 50+ microservices?"
- "Làm sao estimate test effort cho dự án 6 tháng với 80% feature mới?"
- "Risk-based testing: làm sao xác định risk và phân bổ test effort?"
- "Làm sao thiết kế regression test suite hiệu quả khi chỉ có 2 ngày test?"

### Automation (Selenium / Cypress / Playwright)
#### Basic
- "Selenium WebDriver hoạt động thế nào? Kiến trúc của Selenium?"
- "XPath vs CSS Selector: cái nào nhanh hơn? Khi nào dùng XPath?"
- "Page Object Model là gì? Tại sao cần dùng POM?"
- "Implicit Wait vs Explicit Wait vs Fluent Wait khác gì?"
- "Cypress vs Selenium: điểm mạnh/yếu của mỗi tool?"

#### Medium
- "Làm sao handle dynamic element trong Selenium?"
- "Data-driven testing trong automation framework thế nào?"
- "Làm sao handle popup, alert, iframe, new tab trong Selenium/Cypress?"
- "Playwright auto-waiting hoạt động thế nào? Khác gì Selenium?"
- "TestNG vs JUnit? Annotations quan trọng trong TestNG?"

#### Advanced
- "Thiết kế hybrid automation framework cho web app với 500+ test case?"
- "Làm sao giảm flaky test? Chiến lược retry và fail analysis?"
- "Parallel execution trong Selenium Grid vs Docker Selenium?"
- "BDD với Cucumber: pros/cons? Khi nào không nên dùng BDD?"

### API Testing
#### Basic
- "API Testing là gì? Khác gì UI Testing?"
- "HTTP methods: GET, POST, PUT, PATCH, DELETE — dùng khi nào?"
- "Status codes: 2xx, 3xx, 4xx, 5xx — kể 3 ví dụ mỗi loại?"
- "Postman: Environment, Variable, Collection, Pre-request script?"
- "Làm sao test API không có authentication? Và có authentication?"

#### Medium
- "Schema validation trong API test: JSON Schema dùng thế nào?"
- "RestAssured vs Postman vs SuperTest: so sánh?"
- "Làm sao test API cần authentication (Bearer Token, OAuth2, API Key)?"
- "Data-driven API test: test cùng endpoint với 100 bộ data khác nhau?"
- "Làm sao mock API dependency khi service chưa sẵn sàng?"

#### Advanced
- "Contract Testing với Pact: hoạt động thế nào? Dùng khi nào?"
- "Thiết kế API automation framework cho 200+ endpoints?"
- "Làm sao test API trong môi trường microservices với distributed tracing?"
- "gRPC API testing khác REST testing thế nào?"

### Performance Testing
#### Basic
- "Performance Testing vs Load Testing vs Stress Testing khác gì?"
- "JMeter: Thread Group, Sampler, Listener là gì?"
- "Response Time, Throughput, Error Rate — ý nghĩa từng metric?"
- "Làm sao tạo 1 script JMeter đơn giản test API login?"
- "Khi nào cần performance test? Bắt buộc phải làm trước release không?"

#### Medium
- "Correlation trong JMeter: dùng để làm gì? Làm sao extract dynamic value?"
- "Parameterization trong JMeter: CSV Data Set Config dùng thế nào?"
- "Distributed load testing với JMeter: master-slave setup?"
- "K6 vs JMeter: điểm mạnh/yếu của mỗi tool?"
- "Làm sao phân tích kết quả performance test để tìm bottleneck?"

#### Advanced
- "Thiết kế performance test plan cho hệ thống chịu 10k concurrent users?"
- "Làm sao simulate realistic user behavior (think time, pacing, ramp-up)?"
- "Performance testing trong CI/CD pipeline: làm sao tự động hóa?"
- "Server-side monitoring trong khi load test: CPU, memory, DB connection, thread pool?"

### Security Testing
#### Basic
- "QA có cần test security không? Phạm vi test của QA cho security?"
- "OWASP Top 10 là gì? Kể 5 loại phổ biến nhất."
- "SQL Injection là gì? Test thế nào? Input đơn giản để phát hiện?"
- "XSS là gì? Phân biệt Stored XSS, Reflected XSS, DOM-based XSS?"

#### Medium
- "Làm sao test Authentication và Authorization? Các test case quan trọng?"
- "CSRF là gì? Làm sao test? Làm sao bảo vệ?"
- "Burp Suite cơ bản: dùng để làm gì? Intercept, Repeater, Intruder?"
- "File upload vulnerability: test những gì? (extension, content-type, size, malware)"

#### Advanced
- "Thiết kế security test plan cho hệ thống thanh toán online?"
- "Penetration testing vs Vulnerability scanning khác gì?"
- "API security testing: JWT attack, rate limiting, mass assignment?"

### Process & Agile Testing
#### Basic
- "QA trong Scrum: tham gia những event nào? Vai trò của QA trong sprint?"
- "Definition of Done từ góc độ QA bao gồm những gì?"
- "Test Plan gồm những phần gì? Ai viết? Bao giờ viết?"
- "Bug lifecycle: từ khi phát hiện đến khi closed?"

#### Medium
- "Shift-left testing là gì? Làm sao implement?"
- "Khi sprint chỉ có 2 tuần, làm sao đảm bảo quality?"
- "Retrospective: QA nên raise những vấn đề gì?"
- "Làm sao estimate test effort trong planning?"

#### Advanced
- "QA metrics: ngoài bug count còn metric nào quan trọng?"
- "Làm sao build quality culture trong team không có QA mindset?"
- "Test strategy cho team phân tán (distributed team)?"

### Mobile Testing
#### Basic
- "Mobile testing khác web testing thế nào? Cần chú ý gì thêm?"
- "Emulator vs Simulator vs Real device: khi nào dùng cái nào?"
- "Test trên Android vs iOS: khác biệt chính?"
- "Các loại test trên mobile: Installation, Interrupt, Network, Orientation?"

#### Medium
- "Appium: kiến trúc, cách hoạt động, Desired Capabilities?"
- "Làm sao test push notification trên mobile?"
- "Mobile performance: đo memory, battery, network usage thế nào?"
- "Làm sao test trên nhiều devices cùng lúc? Device farm (BrowserStack/Sauce Labs)?"

#### Advanced
- "Thiết kế mobile automation framework với Appium + TestNG?"
- "Làm sao test deep link và app-to-app communication?"
- "Biometric authentication (FaceID/Fingerprint): test như thế nào?"

### SQL / Database Testing
#### Basic
- "Tại sao tester cần biết SQL?"
- "Viết query kiểm tra record đã được insert đúng vào DB chưa?"
- "JOIN để verify relationship giữa các bảng sau 1 transaction phức tạp?"
- "Làm sao check data integrity sau khi migration?"

#### Medium
- "Test data preparation: làm sao tạo test data hiệu quả?"
- "Transaction rollback test: làm sao verify data không bị save khi có lỗi?"
- "Làm sao test stored procedure và trigger?"
- "Database performance test: query chạy chậm, index hiệu quả?"

#### Advanced
- "Thiết kế data comparison strategy giữa source và target sau ETL?"
- "Làm sao test database migration với zero downtime?"
- "Data masking cho môi trường test: kỹ thuật và tool?"

## Dự án mẫu để lấp gap

### Level Manual Tester / Junior — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Công cụ |
|---|-----------|-------------|----------|---------|
| 1 | "Test Plan & Test Case cho Website E-Commerce" | Test plan, Test case design, Boundary testing, Decision table | 3 tuần | Excel, TestRail/Xray, Jira |
| 2 | "End-to-End Manual Test cho Mobile App đặt đồ ăn" | Manual testing, Bug reporting, Regression test, Exploratory test | 4 tuần | Jira, Postman, Charles Proxy |
| 3 | "API Testing cho REST API với Postman" | Postman collection, Environment variable, Schema validation, Newman CLI | 2-3 tuần | Postman, Newman, Swagger |
| 4 | "SQL Data Verification cho Hệ thống Ngân hàng" | SQL query, Data integrity check, Test data creation, Report validation | 2 tuần | SQL (MySQL/PostgreSQL), Excel |

### Level Automation Tester / Mid — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Công cụ |
|---|-----------|-------------|----------|---------|
| 1 | "Web Automation Framework với Selenium + Java" | POM, TestNG, Data-driven, Parallel execution, Reporting (Allure) | 6-8 tuần | Java, Selenium, TestNG, Maven, Allure |
| 2 | "API Automation với RestAssured + CI/CD" | RestAssured, Jenkins pipeline, Allure report, Data-driven test | 4-6 tuần | Java, RestAssured, Jenkins, Docker |
| 3 | "Modern Web Automation với Playwright + TypeScript" | Playwright, Fixtures, Page Object, GitHub Actions CI, Trace viewer | 4-6 tuần | TypeScript, Playwright, GitHub Actions |
| 4 | "Performance Test cho Hệ thống E-Commerce" | JMeter script, Load test, Stress test, Bottleneck analysis, Report | 4-6 tuần | JMeter, Grafana, InfluxDB/Prometheus |
| 5 | "Mobile Automation Test với Appium" | Appium, Page Object, Parallel execution, Device farm integration | 4-6 tuần | Java/Python, Appium, TestNG, BrowserStack |

### Level Senior QA — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Công cụ |
|---|-----------|-------------|----------|---------|
| 1 | "Full Automation Framework from Scratch" | Hybrid framework, BDD, Cross-browser, CI/CD integration, Reporting dashboard | 8-12 tuần | Java/TypeScript, Selenium/Playwright, Cucumber, Jenkins, Docker, K8s |
| 2 | "Performance & Chaos Engineering Platform" | Distributed load test, Chaos testing, Monitoring, Capacity planning | 8 tuần | JMeter, K6, Chaos Monkey, Grafana, Prometheus |
| 3 | "Security Testing Pipeline cho CI/CD" | OWASP ZAP automation, DAST, SAST integration, Vulnerability management | 6-8 tuần | OWASP ZAP, SonarQube, Jenkins, DefectDojo |
| 4 | "Contract Testing Strategy cho Microservices" | Pact broker, Consumer-driven contract, CI/CD integration, Provider verification | 6 tuần | Pact, Docker, Jenkins, Kubernetes |

### Level QA Lead — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Công cụ |
|---|-----------|-------------|----------|---------|
| 1 | "QA Transformation: Manual → Automation" | Strategy, Tool evaluation, Team building, ROI analysis, Process redesign | 12-24 tuần | Custom framework, CI/CD, Test management tools |
| 2 | "Quality Engineering Platform" | Continuous testing, Quality gates, Observability, Test data management, Self-service test env | 12-16 tuần | K8s, Docker, CI/CD, Monitoring stack, Test tools |
| 3 | "QA Maturity Assessment & Roadmap" | Assessment framework, Gap analysis, Roadmap, Executive presentation, Budget planning | 6-8 tuần | Assessment templates, Excel, PowerPoint |
