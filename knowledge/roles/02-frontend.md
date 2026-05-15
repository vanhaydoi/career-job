# Frontend Developer — Skill Framework

## Tổng quan
- **Tên role:** Frontend Developer
- **Level:** Fresher → Junior → Mid → Senior → Lead
- **Mô tả:** Phát triển giao diện người dùng trên trình duyệt và mobile web. Xây dựng trải nghiệm tương tác, tối ưu hiệu năng hiển thị, đảm bảo responsive và accessibility. Làm việc với HTML, CSS, JavaScript, TypeScript, React, Vue, Angular, Next.js và các công nghệ phía client.
- **Tags:** frontend, html, css, javascript, typescript, react, vue, angular, nextjs, web-performance, responsive, accessibility, tailwind

## Kỹ năng theo cấp độ

### Level 1: Fresher/Junior (0-2 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | HTML/CSS cơ bản | Semantic HTML (header, nav, main, article, section), CSS selectors, Box Model, Flexbox, Grid, Position (relative/absolute/fixed/sticky), CSS variables, Pseudo-classes/elements | 20% | html, css, semantic, flexbox, grid, layout |
| 2 | JavaScript cơ bản | ES6+ (arrow function, destructuring, spread, template literals), DOM manipulation, Event handling (bubbling/capturing), Async/Await, Promise, Fetch API, Array methods (map/filter/reduce) | 20% | javascript, es6, dom, async, fetch |
| 3 | Framework cơ bản (React/Vue/Angular) | Component, Props, State, Lifecycle/Hooks (useState, useEffect), JSX/Template syntax, Conditional rendering, List rendering, Event binding, Form handling cơ bản | 20% | react, vue, angular, component, hooks |
| 4 | Responsive Design | Mobile-first approach, Media queries, Fluid layout (%, vw/vh), Breakpoint strategy, Viewport meta tag, Relative units (rem/em), Responsive images (srcset, picture) | 15% | responsive, mobile-first, media-query, css |
| 5 | Git cơ bản | clone, add, commit, push, pull, branch, merge, pull request, .gitignore, rebase cơ bản, conflict resolution | 10% | git, version-control |
| 6 | Browser DevTools | Elements inspector, Console, Network tab (XHR/Fetch, status codes), Application tab (LocalStorage, SessionStorage, Cookies), Performance tab cơ bản, Debugging với breakpoint | 10% | devtools, debugging, chrome, browser |
| 7 | REST API consumption | fetch/axios, CRUD operations, Request/Response handling, Error handling (try/catch), Loading states, HTTP status codes, API documentation reading (Swagger/Postman) | 5% | api, rest, axios, fetch |

### Level 2: Junior/Mid (1-4 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | TypeScript | Type system cơ bản (string, number, boolean, array, object), Interface vs Type, Generics cơ bản, Union/Intersection types, Utility types (Partial, Pick, Omit, Record), Enum, Type narrowing | 15% | typescript, types, generics |
| 2 | State Management (Redux/Zustand/Context) | Redux Toolkit (Slice, Store, Dispatch, Selector), Async Thunk/RTK Query, Zustand store pattern, React Context + useReducer, State normalization, Middleware (redux-thunk, redux-saga cơ bản) | 15% | redux, zustand, state-management, context |
| 3 | Testing (Jest, React Testing Library) | Unit test (Jest assertions, matchers), Component test (RTL render, queries, fireEvent, userEvent), Mocking (API mock với MSW, module mock), Snapshot testing, Code coverage | 15% | testing, jest, rtl, unit-test |
| 4 | Next.js / SSR | Pages Router & App Router, SSR/SSG/ISR, API Routes, Server Components (RSC), getServerSideProps/getStaticProps, Image optimization (next/image), Middleware, Dynamic routes | 15% | nextjs, ssr, ssg, rsc, react |
| 5 | Performance Optimization | Code splitting (React.lazy + Suspense, dynamic import), Lazy loading (Intersection Observer), Memoization (useMemo, useCallback, React.memo), Re-render optimization, Bundle analysis, Virtual scrolling cho large lists | 12% | performance, optimization, lazy-loading, memo |
| 6 | CSS-in-JS / Tailwind CSS | Styled-components / CSS Modules / Emotion, Scoped styles, Theming, Utility-first (Tailwind), Responsive classes, Custom design tokens, Tailwind plugins/config | 10% | css, tailwind, styled-components, css-modules |
| 7 | CI/CD cơ bản | GitHub Actions pipeline (lint → test → build → deploy), Netlify/Vercel deploy, Preview deployments, Environment variables management, Automated visual regression testing | 10% | ci-cd, github-actions, vercel, netlify |
| 8 | Webpack / Vite | Module bundling concepts, HMR (Hot Module Replacement), Loaders & Plugins (Webpack), Build optimization (Tree shaking, Code minification, Chunk splitting), Environment variables (.env), Vite config | 8% | webpack, vite, bundler, build-tools |

### Level 3: Mid/Senior (3+ năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Micro-frontend | Module Federation (Webpack 5), Single-SPA, Web Components, Integration patterns (iframe, JavaScript import, Custom Elements), Shared dependencies, Routing orchestration, Communication giữa các micro-app | 15% | micro-frontend, module-federation, single-spa |
| 2 | Web Performance (Core Web Vitals) | LCP (Largest Contentful Paint), INP (Interaction to Next Paint), CLS (Cumulative Layout Shift), Lighthouse audit & scoring, Resource hints (preload, prefetch, preconnect), Critical CSS, Font optimization | 15% | performance, core-web-vitals, lcp, cls, lighthouse |
| 3 | System Design for Frontend | Component architecture (Atomic Design), Data flow patterns (Unidirectional, Flux), State architecture (Client vs Server state), Routing strategy, Error boundaries, Offline-first patterns (Service Worker, Cache API), Real-time data (WebSocket, SSE) | 15% | architecture, system-design, data-flow |
| 4 | Design Systems | Component library (Storybook, Chromatic), Design tokens (Style Dictionary), Component API design (props, slots, composition), Versioning & Breaking changes, Accessibility (a11y) tích hợp sẵn, Documentation (MDX) | 15% | design-system, storybook, component-library, accessibility |
| 5 | Advanced TypeScript | Conditional types (extends, infer), Template literal types, Mapped types, Type guards (is, asserts), Declaration merging, Module augmentation, tsconfig tối ưu (strict, paths, baseUrl) | 15% | typescript, advanced-types, generics |
| 6 | E2E Testing (Cypress/Playwright) | Test strategy (critical path), Cypress commands & assertions, Playwright multi-browser, Visual regression testing (Percy/Chromatic), CI integration, Network stubbing/mocking, API interception | 15% | testing, e2e, cypress, playwright |
| 7 | Web Security (XSS, CSRF, CORS) | XSS prevention (Content Security Policy, sanitization với DOMPurify), CSRF token, CORS configuration, Secure cookie (HttpOnly, Secure, SameSite), Input validation & output encoding, OAuth2/OIDC flow cho SPA | 10% | security, xss, csrf, cors, csp |

### Level 4: Senior/Lead (5+ năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Frontend Architecture | Monorepo strategy (Turborepo, Nx, pnpm workspaces), Module boundary & dependency rules, Tech stack selection & evaluation (adopt/hold/trial), Migration planning (e.g. CRA → Vite, Pages → App Router), Frontend infrastructure (CDN, Edge computing) | 20% | architecture, monorepo, tech-strategy, migration |
| 2 | Team Leadership | Code review culture (PR templates, review checklist), Mentoring & career development, Technical roadmap (RFC process), Hiring (interview design, rubric, assessment), Cross-team collaboration (Backend/Mobile/Design/Product) | 20% | leadership, mentoring, management, hiring |
| 3 | Design System Governance | Contribution workflow (propose → review → publish), Accessibility (a11y) compliance (WCAG 2.1 AA), Breaking change management, Cross-team adoption strategy, Design ↔ Dev handoff (Figma tokens → code), Governance board | 15% | design-system, governance, accessibility |
| 4 | Observability (RUM, Error tracking) | Real User Monitoring (RUM — Core Web Vitals field data), Error tracking (Sentry, LogRocket, Datadog RUM), Custom metrics & dashboards, Error boundaries strategy, Alerting & incident response, Session replay & debugging | 15% | observability, monitoring, rum, sentry, error-tracking |
| 5 | Build Tooling Strategy | Monorepo build orchestration (incremental builds, caching, remote cache), Bundle analysis (Bundle Buddy, Statoscope), Build performance optimization, Module federation vs shared packages trade-off, Deployment pipeline optimization, Preview/review environments | 10% | build-tools, turborepo, nx, monorepo |
| 6 | A/B Testing & Analytics | Feature flags (LaunchDarkly, GrowthBook), Experiment design (sample size, duration, statistical significance), Analytics instrumentation (GA4, Mixpanel, Amplitude), Data-driven product decisions, SEO impact of A/B testing | 10% | ab-testing, analytics, feature-flags, experimentation |
| 7 | Internationalization (i18n) | react-intl / i18next / next-intl, Translation workflow (TMS integration), RTL (Right-to-Left) layout support, Locale-aware formatting (date, number, currency, plural), Dynamic content translation, Pseudo-localization testing | 10% | i18n, internationalization, localization, rtl |

## Câu hỏi phỏng vấn mẫu theo kỹ năng

### HTML / CSS
#### Basic
- "Semantic HTML là gì? Tại sao nên dùng `<header>`, `<nav>`, `<main>` thay vì `<div>`?"
- "Phân biệt Flexbox và Grid? Khi nào dùng cái nào? Cho ví dụ cụ thể."
- "Giải thích Box Model trong CSS? `box-sizing: border-box` vs `content-box` khác gì?"
- "CSS Specificity hoạt động thế nào? Tính điểm specificity ra sao?"
- "Position absolute vs relative vs fixed vs sticky khác gì? Cho ví dụ."

#### Medium
- "BEM (Block Element Modifier) là gì? Tại sao cần naming convention cho CSS?"
- "CSS Container Queries khác Media Queries thế nào? Khi nào dùng cái nào?"
- "Làm sao center một div theo chiều ngang và dọc? Kể ít nhất 3 cách khác nhau."
- "CSS Custom Properties (CSS Variables) hoạt động thế nào? So với SCSS variables?"

#### Advanced
- "Làm sao xây dựng một CSS architecture cho dự án lớn, nhiều team? ITCSS? CSS Modules vs CSS-in-JS?"
- "Critical CSS là gì? Làm sao extract và inline Critical CSS để cải thiện LCP?"
- "So sánh các chiến lược styling: CSS Modules, Tailwind, Styled-components, Vanilla Extract?"

### JavaScript / TypeScript
#### Basic
- "Phân biệt `var`, `let`, `const` trong JavaScript? Scope và hoisting khác nhau thế nào?"
- "Closure là gì? Cho ví dụ thực tế về closure trong JavaScript."
- "Event Loop hoạt động thế nào? Call Stack, Task Queue, Microtask Queue là gì?"
- "`==` vs `===` khác gì? Type coercion trong JS hoạt động ra sao?"
- "Promise là gì? Phân biệt Promise.all, Promise.allSettled, Promise.race, Promise.any?"

#### Medium
- "Prototype chain trong JavaScript hoạt động thế nào? `__proto__` vs `prototype` khác gì?"
- "`this` trong JavaScript — giá trị của nó được xác định thế nào? Khác gì giữa arrow function và regular function?"
- "Phân biệt `debounce` và `throttle`? Khi nào dùng cái nào? Cho ví dụ."
- "TypeScript Generics là gì? Cho ví dụ về Generic function và Generic interface?"

#### Advanced
- "TypeScript Utility Types (Partial, Pick, Omit, Record, Exclude, Extract) — giải thích và cho ví dụ?"
- "Conditional Types trong TypeScript: `T extends U ? X : Y`, `infer` keyword dùng để làm gì?"
- "Làm sao tối ưu TypeScript compile time cho monorepo lớn? Project references, incremental builds?"

### React
#### Basic
- "Virtual DOM là gì? React dùng Virtual DOM để cập nhật UI như thế nào?"
- "Component Lifecycle trong React class component và tương đương với Hooks?"
- "`useState` và `useEffect` hoạt động thế nào? Dependency array dùng để làm gì?"
- "Props vs State khác gì? Khi nào dùng cái nào?"
- "Keys trong React list rendering — tại sao cần, không nên dùng index làm key khi nào?"

#### Medium
- "`useMemo` vs `useCallback` vs `React.memo` — khi nào dùng, trade-off là gì?"
- "Custom Hook là gì? Viết một custom hook `useDebounce` hoặc `useLocalStorage`?"
- "React Context vs Redux vs Zustand — khi nào chọn cái nào?"
- "Error Boundary trong React là gì? Làm sao implement?"

#### Advanced
- "React 18 Concurrent Features (Suspense, useTransition, useDeferredValue) — giải thích và cho ví dụ?"
- "React Server Components (RSC) hoạt động thế nào? Khác gì với SSR truyền thống?"
- "Làm sao tối ưu re-render trong ứng dụng React lớn? Các chiến lược và debugging technique?"

### Next.js
#### Basic
- "SSR vs SSG vs ISR trong Next.js khác gì? Khi nào dùng loại nào?"
- "Pages Router vs App Router khác gì? Ưu/nhược của mỗi loại?"
- "File-based routing trong Next.js hoạt động thế nào? Dynamic routes?"
- "API Routes trong Next.js là gì? So sánh với Express/Node backend?"

#### Medium
- "Middleware trong Next.js 13+ hoạt động thế nào? Use cases phổ biến?"
- "`next/image` tối ưu ảnh như thế nào? Các props quan trọng cần biết?"
- "Làm sao implement Authentication (NextAuth.js) với Next.js App Router?"
- "Incremental Static Regeneration (ISR) — cơ chế và use case?"

#### Advanced
- "React Server Components (RSC) trong Next.js App Router — Server Component vs Client Component boundary?"
- "Caching strategy trong Next.js 14+: Full Route Cache, Data Cache, Router Cache?"
- "Làm sao deploy Next.js app lên edge (Cloudflare Workers, Vercel Edge) và trade-off?"

### Vue / Angular
#### Basic
- "Vue Reactivity System hoạt động thế nào? ref() vs reactive() khác gì?"
- "Vue Composition API vs Options API — ưu/nhược của mỗi loại?"
- "Angular Dependency Injection hoạt động thế nào? providedIn: 'root' là gì?"
- "Angular Change Detection — cơ chế Default vs OnPush?"

#### Medium
- "Vue 3 Teleport và Suspense — dùng trong trường hợp nào?"
- "Angular Signals là gì? So sánh với RxJS Observable?"
- "Vuex vs Pinia trong Vue — khi nào chọn cái nào?"
- "Angular Route Guards (CanActivate, CanDeactivate, Resolve) dùng để làm gì?"

#### Advanced
- "Làm sao scale Vue/React application với Module Federation trong Micro-frontend?"
- "So sánh Vue 3 Composition API với React Hooks — ưu/nhược từng bên?"
- "Angular Standalone Components và signal-based components — tương lai của Angular?"

### Testing
#### Basic
- "Phân biệt Unit test, Integration test, E2E test trong frontend?"
- "Jest matchers cơ bản: toBe, toEqual, toContain, toHaveBeenCalled, toMatchSnapshot?"
- "React Testing Library queries: getBy, queryBy, findBy khác gì?"
- "Mock function trong Jest: jest.fn(), jest.spyOn(), jest.mock() dùng khi nào?"

#### Medium
- "Mock Service Worker (MSW) là gì? Tại sao dùng MSW thay vì mock fetch trực tiếp?"
- "Testing async behavior trong React: waitFor, findBy, act() — dùng thế nào?"
- "Snapshot testing — lợi ích và hạn chế? Khi nào không nên dùng?"
- "Visual Regression Testing là gì? Công cụ: Percy, Chromatic, Storybook?"

#### Advanced
- "Chiến lược testing cho ứng dụng React lớn: bao nhiêu unit test, integration test, E2E test?"
- "Testing trong CI/CD pipeline — làm sao giữ test suite nhanh và ổn định?"
- "Cypress vs Playwright — so sánh và khi nào chọn cái nào cho dự án?"

### Web Performance
#### Basic
- "Core Web Vitals là gì? Giải thích LCP, INP (FID cũ), CLS?"
- "Lazy loading là gì? Cách implement lazy loading cho ảnh, component trong React?"
- "Code Splitting trong React: React.lazy() + Suspense, dynamic import?"
- "Tại sao cần minify và compress (Gzip/Brotli) bundle?"

#### Medium
- "Làm sao phân tích bundle size? Các công cụ: Webpack Bundle Analyzer, Statoscope?"
- "Resource hints: preload, prefetch, preconnect, dns-prefetch — mỗi cái dùng khi nào?"
- "Làm sao tối ưu CLS (Cumulative Layout Shift)? Nguyên nhân phổ biến và cách fix?"
- "Caching strategy cho static assets: Cache-Control, ETag, Service Worker?"

#### Advanced
- "Làm sao thiết lập Performance Budget? Cách enforce trong CI?"
- "Streaming SSR và Partial Hydration — cơ chế và lợi ích cho performance?"
- "RUM (Real User Monitoring) — làm sao collect, analyze Core Web Vitals field data?"

### Architecture / State Management
#### Basic
- "Flux pattern là gì? Redux implement Flux như thế nào?"
- "React Context vs Redux — khi nào dùng Context, khi nào cần Redux?"
- "Prop drilling là gì? Các cách giải quyết prop drilling?"

#### Medium
- "Server State vs Client State khác gì? React Query/TanStack Query giải quyết vấn đề gì?"
- "Zustand vs Redux Toolkit vs Jotai vs Recoil — so sánh và khi nào dùng cái nào?"
- "Event-driven state management (ví dụ: RxJS) trong frontend — use case?"
- "Atomic Design pattern là gì? Áp dụng thế nào trong React?"

#### Advanced
- "Thiết kế state management cho ứng dụng collaborative (Google Docs style) — Conflict Resolution (CRDT/OT)?"
- "Module Federation vs Monorepo shared packages — trade-off và quyết định kiến trúc?"
- "Offline-first architecture: Service Worker, IndexedDB, Sync strategy?"

## Dự án mẫu để lấp gap

### Level Junior — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "Landing Page Responsive cho sản phẩm SaaS" | HTML/CSS, Responsive Design, CSS Flexbox/Grid, Animation cơ bản | 2-3 tuần | HTML, CSS, SCSS, JavaScript, Netlify |
| 2 | "Todo App với React + REST API" | React cơ bản, CRUD, State management cơ bản, API consumption | 2-3 tuần | React, Axios, CSS Modules, JSONPlaceholder API |
| 3 | "Weather Dashboard với JavaScript thuần" | JavaScript, Fetch API, DOM manipulation, Geolocation API | 1-2 tuần | Vanilla JS, OpenWeatherMap API, CSS Variables |
| 4 | "Portfolio cá nhân với React + Responsive" | React, Responsive Design, React Router, Dark Mode toggle | 2-3 tuần | React, React Router, Tailwind CSS, Vercel |
| 5 | "Product Listing với Filter + Sort + Pagination" | React, Filter logic, URL query params, Loading/Empty/Error states | 2-3 tuần | React, React Router, FakeStore API, CSS |

### Level Mid — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "E-Commerce Frontend với Next.js SSR" | Next.js, SSR/SSG/ISR, SEO, TypeScript, Image optimization | 4-6 tuần | Next.js 14, TypeScript, Tailwind CSS, Zustand, Stripe |
| 2 | "Dashboard Admin với Data Visualization" | State management, Chart.js/D3.js, Testing (Jest + RTL), Responsive data tables | 4-6 tuần | React, Redux Toolkit, Recharts, Jest, React Testing Library |
| 3 | "Micro-frontend Dashboard với Module Federation" | Micro-frontend, Module Federation, Shared components, Inter-app communication | 4-6 tuần | React, Webpack 5 Module Federation, TypeScript, Tailwind |
| 4 | "Design System cơ bản với Storybook" | Component library, Storybook, Design tokens, Accessibility, Testing | 4-6 tuần | React, Storybook, Tailwind CSS, Jest, Chromatic |

### Level Senior — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "Monorepo Frontend Platform (TurboRepo)" | Monorepo architecture, Shared packages, Build optimization, CI/CD pipeline | 6-8 tuần | Turborepo, Next.js, React, TypeScript, Tailwind, GitHub Actions |
| 2 | "Real-Time Collaboration App (Google Docs Clone)" | System Design, WebSocket/CRDT, State sync, Conflict resolution, Performance | 6-8 tuần | Next.js, TypeScript, Yjs/CRDT, Zustand, WebSocket, Playwright |
| 3 | "Observability Dashboard cho Frontend Apps" | RUM, Error tracking, Core Web Vitals dashboard, Alerting setup, Session replay | 4-6 tuần | React, Sentry, Grafana, Prometheus, TypeScript |
| 4 | "i18n Migration cho SaaS Platform" | Internationalization, RTL, Translation workflow, Locale routing, Testing | 4-6 tuần | Next.js, next-intl, TypeScript, Playwright, Crowdin/GitLocalize |
