# Fullstack Developer — Skill Framework

## Tổng quan
- **Tên role:** Fullstack Developer
- **Level:** Fresher → Junior → Mid → Senior → Lead
- **Mô tả:** Phát triển cả frontend và backend của ứng dụng web. Kết hợp kỹ năng frontend (UI/UX) và backend (API, database, server).
- **Tags:** fullstack, web, frontend, backend, javascript, typescript, react, nodejs

## Kỹ năng theo cấp độ

### Level 1: Fresher/Junior (0-2 năm)
| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | HTML/CSS + JavaScript | HTML5, CSS3, Flexbox, Grid, JavaScript ES6+, DOM manipulation | 20% | html, css, javascript, frontend |
| 2 | Frontend Framework (React/Vue/Angular) | Component, Props, State, Hooks, Routing cơ bản | 20% | react, vue, angular, frontend |
| 3 | Backend cơ bản (Node.js/Python/Java) | Express/FastAPI/Spring Boot, REST API, CRUD | 20% | nodejs, python, java, backend, api |
| 4 | SQL cơ bản | SELECT, JOIN, INSERT/UPDATE/DELETE, basic schema design | 15% | sql, database |
| 5 | Git cơ bản | clone, commit, branch, merge, PR | 10% | git |
| 6 | REST API integration | Gọi API từ frontend (fetch/axios), xử lý response, error handling | 10% | api, rest, http |
| 7 | Deployment cơ bản | Deploy lên Vercel/Netlify/Render, environment variables | 5% | deployment, devops |

### Level 2: Junior/Mid (1-4 năm)
| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | TypeScript | Type system, Generics, Utility types, Interface vs Type | 15% | typescript |
| 2 | State Management | Redux/Zustand/Context API, Server state (React Query/SWR) | 15% | state-management, redux, zustand |
| 3 | Next.js / SSR | SSR, SSG, ISR, App Router, API Routes, Middleware | 15% | nextjs, ssr, fullstack |
| 4 | Database nâng cao | ORM (Prisma/TypeORM), Migration, Transaction, Indexing | 15% | database, orm, prisma |
| 5 | Authentication | JWT, OAuth2, Session, Role-based access (RBAC) | 10% | auth, jwt, oauth |
| 6 | Testing (Frontend + Backend) | Jest, React Testing Library, API testing, E2E cơ bản | 10% | testing, jest, e2e |
| 7 | Docker | Dockerfile, Docker Compose, Containerize fullstack app | 10% | docker, container |
| 8 | CI/CD | GitHub Actions, automated testing, deploy preview | 10% | ci-cd, github-actions |

### Level 3: Mid/Senior (3+ năm)
| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | System Design cho Fullstack | Monolith vs Microservices, BFF pattern, API Gateway, caching strategy | 25% | system-design, architecture |
| 2 | Performance Optimization | Bundle size, Code splitting, Lazy loading, Image optimization, Backend query optimization, CDN | 20% | performance, optimization |
| 3 | Cloud Services (AWS/GCP/Vercel) | S3, Lambda, CloudFront, RDS, Vercel Edge, Serverless | 15% | cloud, aws, serverless |
| 4 | Security (Fullstack) | OWASP, XSS, CSRF, SQL Injection, CORS, CSP, Secrets management | 15% | security |
| 5 | Real-time Features | WebSocket, SSE, Socket.io, Live collaboration | 15% | websocket, real-time |
| 6 | Design System + Accessibility | Component library, Design tokens, WCAG 2.1, a11y testing | 10% | design-system, accessibility |

### Level 4: Senior/Lead (5+ năm)
| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Fullstack Architecture | Monorepo (Turborepo/Nx), Micro-frontend, BFF, API versioning | 25% | architecture, monorepo |
| 2 | Platform Engineering | Internal tools, Developer experience (DX), CLI tools, Shared libraries | 20% | platform, dx |
| 3 | Observability | RUM, APM, Error tracking (Sentry), Logging, Distributed tracing | 20% | observability, monitoring |
| 4 | Team Leadership | Code review, Mentoring, Tech roadmap, Cross-team collaboration | 20% | leadership, mentoring |
| 5 | Business & Product Sense | User analytics, A/B testing, Feature flags, Product metrics | 15% | product, analytics |

## Câu hỏi phỏng vấn mẫu theo kỹ năng

### HTML/CSS
#### Basic
- "Phân biệt block, inline, inline-block? Khi nào dùng?"
- "Flexbox vs Grid khác gì? Khi nào dùng cái nào?"
- "CSS specificity hoạt động thế nào?"
- "Position: relative, absolute, fixed, sticky khác gì?"

#### Medium
- "Responsive design: mobile-first vs desktop-first? Breakpoint strategy?"
- "Làm sao tối ưu CSS cho performance? Critical CSS, unused CSS?"
- "CSS Container Queries là gì? Khác Media Queries thế nào?"

#### Advanced
- "Thiết kế 1 design system với CSS custom properties?"
- "Làm sao xử lý CSS trong micro-frontend architecture?"

### JavaScript / TypeScript
#### Basic
- "var, let, const khác gì? Hoisting là gì?"
- "Callback, Promise, async/await khác gì?"
- "Array methods: map, filter, reduce, forEach?"
- "Closure là gì? Cho ví dụ thực tế?"

#### Medium
- "Event Loop hoạt động thế nào? Microtask vs Macrotask?"
- "Prototype và Prototypal Inheritance trong JS?"
- "TypeScript: Interface vs Type? Generics dùng khi nào?"

#### Advanced
- "Memory leak trong JavaScript? Cách phát hiện và fix?"
- "Design pattern trong TypeScript: Builder, Factory, Observer?"
- "Làm sao xử lý 100k items trong browser mà không bị lag?"

### React / Next.js
#### Basic
- "Component lifecycle trong React? useEffect cleanup?"
- "useState, useEffect, useContext, useRef, useMemo, useCallback?"
- "Virtual DOM là gì? React reconciliation hoạt động thế nào?"
- "SSR vs SSG vs ISR trong Next.js?"

#### Medium
- "React Server Components là gì? Khác gì client components?"
- "State management: Context vs Redux vs Zustand? Khi nào dùng cái nào?"
- "Next.js App Router vs Pages Router? Middleware trong Next.js?"

#### Advanced
- "Performance: Code splitting, Lazy loading, Bundle analysis?"
- "React 19 có gì mới? Server Actions, use(), useOptimistic?"
- "Thiết kế real-time dashboard với Next.js + WebSocket?"

### Testing
#### Basic
- "Unit test vs Integration test vs E2E test khác gì?"
- "Viết unit test cho React component với Jest + Testing Library?"
- "Mock API call trong test thế nào?"

#### Medium
- "Cypress vs Playwright? Khi nào dùng cái nào?"
- "Test coverage: nên target bao nhiêu %?"
- "Visual regression testing là gì?"

### Performance
#### Basic
- "Core Web Vitals là gì? LCP, FID, CLS?"
- "Làm sao đo performance của web app? Lighthouse, WebPageTest?"
- "Image optimization: lazy loading, WebP, srcset, CDN?"

#### Medium
- "Bundle size optimization: Tree shaking, Code splitting, Dynamic import?"
- "Caching strategy: Service Worker, HTTP caching, CDN caching?"
- "Làm sao debug render performance trong React?"

## Dự án mẫu để lấp gap

### Level Junior
| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "Personal Blog với Next.js" | React, Next.js, SSR, Markdown, Tailwind | 2-3 tuần | Next.js, TypeScript, Tailwind, Vercel |
| 2 | "Task Management App Fullstack" | React, Node.js, REST API, PostgreSQL, Auth | 4 tuần | Next.js, Prisma, PostgreSQL, NextAuth.js |
| 3 | "E-Commerce Product Page" | React, Responsive, API integration, Cart state | 3 tuần | React, TypeScript, Tailwind, Zustand |
| 4 | "Admin Dashboard" | React, Chart.js, Table, Form, API CRUD | 3-4 tuần | React, TypeScript, Ant Design/Shadcn, Node.js |

### Level Mid
| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "Real-time Chat App" | WebSocket, Real-time, Next.js, Auth, File upload | 4-6 tuần | Next.js, Socket.io, Prisma, PostgreSQL, S3 |
| 2 | "Multi-tenant SaaS Dashboard" | RBAC, Multi-tenancy, Data isolation, Billing | 8 tuần | Next.js, Prisma, PostgreSQL, Stripe, Redis |
| 3 | "Microservices E-Commerce Fullstack" | Backend services, API Gateway, Frontend BFF | 8 tuần | Next.js, Node.js, Kafka, PostgreSQL, Docker |
