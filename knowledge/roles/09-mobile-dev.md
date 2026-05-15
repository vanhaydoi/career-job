# Mobile Developer — Skill Framework

## Tổng quan
- **Tên role:** Mobile Developer
- **Level:** Fresher → Junior → Mid → Senior → Lead
- **Mô tả:** Phát triển ứng dụng di động trên Android, iOS và cross-platform (React Native, Flutter). Thiết kế UI/UX mobile, tích hợp API, tối ưu hiệu năng, triển khai lên App Store và Google Play.
- **Tags:** mobile, android, ios, kotlin, swift, react-native, flutter, cross-platform

## Kỹ năng theo cấp độ

### Level 1: Fresher/Junior (0-2 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Ngôn ngữ lập trình (Kotlin/Swift/Dart/JS) | Cú pháp cơ bản, OOP, Null safety, Collection/Array, Control flow, String manipulation | 20% | kotlin, swift, dart, core |
| 2 | UI cơ bản (Jetpack Compose/SwiftUI/React Native) | Layout cơ bản (Column/Row/VStack/HStack), Component, State, Props, Style | 20% | compose, swiftui, react-native, ui |
| 3 | Điều hướng & Data Passing | Navigation, Intent (Android), NavigationLink (iOS), Passing data giữa màn hình | 15% | navigation |
| 4 | REST API & Networking | Retrofit/URLSession/fetch, JSON parsing, Error handling, Loading states | 15% | api, networking, rest |
| 5 | Git cơ bản | clone, commit, branch, merge, pull request, .gitignore | 10% | git, version-control |
| 6 | Local Storage cơ bản | SharedPreferences/UserDefaults/AsyncStorage, Room/Core Data cơ bản (CRUD) | 10% | storage, database |
| 7 | Deploy cơ bản | Build APK/IPA, Signing, App Store Connect, Google Play Console | 10% | deployment, app-store |

### Level 2: Junior/Mid (1-4 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Kiến trúc MVVM/MVP/MVI | ViewModel, LiveData/StateFlow, Repository pattern, Clean Architecture layers | 20% | architecture, mvvm, clean-architecture |
| 2 | Dependency Injection | Hilt/Koin (Android), Swinject/Resolver (iOS), Provider/Riverpod (Flutter) | 15% | di, hilt, koin |
| 3 | Reactive Programming | Coroutines/Flow (Kotlin), Combine/AsyncSequence (Swift), RxSwift/RxDart | 15% | coroutines, flow, combine, reactive |
| 4 | Database nâng cao | Room (relations, migration), Core Data (versioning), SQLite optimization | 15% | room, coredata, database |
| 5 | Push Notifications | FCM (Android), APNs (iOS), Deep linking, Rich notifications | 10% | push-notification, fcm, apns |
| 6 | Testing cơ bản | JUnit/MockK (Android), XCTest (iOS), Widget/Component test (Flutter) | 10% | testing, junit, xctest |
| 7 | CI/CD cơ bản | Fastlane, GitHub Actions, Build variants, Automated testing trong CI | 10% | ci-cd, fastlane |
| 8 | Cross-platform cơ bản | React Native hoặc Flutter fundamentals, Bridge/Channel, Platform-specific code | 5% | cross-platform, react-native, flutter |

### Level 3: Mid/Senior (3+ năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Hiệu năng & Tối ưu | Profiling (Android Profiler/Instruments), Memory leak, ANR/Freeze, Render optimization, App startup time, Network optimization (caching, compression) | 20% | performance, profiling, optimization |
| 2 | Bảo mật mobile | Keystore/Keychain, Data encryption, SSL Pinning, ProGuard/R8, Code obfuscation, Biometric auth, Secure storage | 20% | security, encryption, keystore, keychain |
| 3 | Offline-first Architecture | Local-first, Sync engine (Conflict resolution), Background sync (WorkManager/BGTaskScheduler), Queue-based sync, Offline mode UX | 15% | offline, sync, background |
| 4 | CI/CD nâng cao | Fastlane (Match, Gym, Deliver, Screengrab), Code signing tự động, TestFlight/Internal testing, Phased release, Beta distribution | 15% | ci-cd, fastlane, automation |
| 5 | Accessibility & Đa ngôn ngữ | TalkBack/VoiceOver, Content description, Dynamic Type/Font scale, i18n/L10n, RTL support | 10% | accessibility, a11y, localization |
| 6 | Module hóa & Đa module | Multi-module Android, Swift Package Manager, Modularization strategy, Dynamic Feature Modules, Shared module (KMM) | 10% | modularization, multi-module, kmm |
| 7 | Monitoring & Crash Reporting | Firebase Crashlytics, Sentry, Performance monitoring, Custom events, ANR/Exception tracking, Network monitoring | 10% | monitoring, crashlytics, analytics |

### Level 4: Senior/Lead (5+ năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Kiến trúc tổng thể | Micro-frontend mobile, Plugin architecture, White-label apps, Shared module (KMM), Code sharing strategy, Technical roadmap | 25% | architecture, strategy, kmm |
| 2 | Điều hành đội ngũ | Code review culture, Mentoring, Mobile team scaling, Cross-team collaboration (Design/Backend/QA), Hiring, Tech talks | 20% | leadership, mentoring, management |
| 3 | App Store Optimization & Release | ASO, Phased rollout, Feature flags, Remote config, A/B testing (Firebase Remote Config), Staged rollouts, App rating flow | 15% | aso, release, feature-flags |
| 4 | Chất lượng & Ổn định | Crash-free rate > 99.9%, Automated E2E testing (Maestro/Detox), Regression testing, DevEx (build speed, hot reload), Static analysis (Detekt/SwiftLint) | 15% | quality, stability, e2e-testing |
| 5 | CI/CD ở quy mô lớn | Self-hosted CI runners, Parallel builds, Build caching, Flaky test management, Automated screenshot testing, App size monitoring | 15% | ci-cd, scale, automation |
| 6 | Chiến lược nền tảng | Cross-platform decision (native vs hybrid vs cross-platform), Framework migration, Deprecation strategy, OS update adoption, Backward compatibility | 10% | strategy, platform, decision |

## Câu hỏi phỏng vấn mẫu theo kỹ năng

### Android / Kotlin

#### Basic
- "Phân biệt val và var trong Kotlin? Khi nào dùng cái nào?"
- "Activity Lifecycle trong Android? Mỗi method được gọi khi nào?"
- "RecyclerView hoạt động thế nào? ViewHolder pattern là gì?"
- "Coroutines là gì? Phân biệt launch, async, runBlocking?"
- "Thế nào là Null Safety trong Kotlin? ?. !! ?: khác gì?"

#### Medium
- "Jetpack Compose vs XML-based UI khác gì? Khi nào dùng cái nào?"
- "StateFlow vs LiveData vs SharedFlow? Chọn cái nào cho use case nào?"
- "Room Database: Relations, TypeConverter, Migration strategy?"
- "Hilt vs Koin? Khi nào chọn Hilt thay vì Koin?"
- "WorkManager dùng để làm gì? So với AlarmManager và JobScheduler?"

#### Advanced
- "Thiết kế offline-first app với Room + Remote Mediator?"
- "Làm sao implement multi-module architecture cho app có 50+ màn hình?"
- "Memory leak trong Android: Nguyên nhân phổ biến và cách phát hiện bằng LeakCanary?"
- "Làm sao tối ưu build time cho project Android lớn? Gradle optimization?"
- "Jetpack Compose recomposition: Làm sao tránh recomposition không cần thiết?"

### iOS / Swift

#### Basic
- "Phân biệt Class và Struct trong Swift? Khi nào dùng cái nào?"
- "Optional trong Swift? if let, guard let, optional chaining khác gì?"
- "UIKit vs SwiftUI: Khác biệt cơ bản và khi nào dùng cái nào?"
- "ViewController lifecycle trong iOS? viewDidLoad, viewWillAppear, viewDidAppear?"
- "Protocol trong Swift là gì? Protocol-oriented programming?"

#### Medium
- "Combine framework: Publisher, Subscriber, Operator? So với RxSwift?"
- "Core Data: NSPersistentContainer, NSManagedObjectContext, Concurrency?"
- "ARC hoạt động thế nào? Strong, weak, unowned reference?"
- "Swift Concurrency: async/await, Task, Actor? So với GCD?"
- "Swift Package Manager vs CocoaPods vs Carthage?"
- "Diffable DataSource là gì? Tại sao nên dùng thay vì UITableViewDataSource cũ?"

#### Advanced
- "Làm sao implement custom SwiftUI layout? Layout protocol?"
- "Application thining là gì? App thinning trong iOS deployment?"
- "iOS App Security: Keychain, Biometric Auth, SSL Pinning, Data Protection API?"
- "Làm sao giảm app launch time? Dyld, Static vs Dynamic linking?"
- "SwiftUI: Cách quản lý state phức tạp với @Observable (iOS 17+) và @EnvironmentObject?"

### React Native / Flutter

#### Basic
- "React Native: Component, props, state khác gì? JSX là gì?"
- "Flutter: Widget cơ bản? StatelessWidget vs StatefulWidget?"
- "React Native Bridge hoạt động thế nào? Tại sao cần bridge?"
- "Flutter: Hot Reload vs Hot Restart khác gì?"
- "Làm sao style trong React Native? Flexbox hoạt động thế nào?"
- "Flutter: setState() hoạt động thế nào? Khi nào không nên dùng?"

#### Medium
- "Flutter: BLoC vs Provider vs Riverpod? Chọn cái nào?"
- "React Native: Hermes engine là gì? Tại sao Meta phát triển Hermes?"
- "Làm sao gọi native code (bridge/platform channel) trong React Native?"
- "Flutter: Platform Channel hoạt động thế nào? MethodChannel vs EventChannel?"
- "React Native: New Architecture (Fabric, TurboModules) khác gì Old Architecture?"
- "Quản lý state trong cross-platform app lớn: Redux vs MobX vs BLoC?"

#### Advanced
- "Khi nào nên chọn React Native vs Flutter vs native cho dự án mới?"
- "Flutter: CustomPainter và RenderObject? Khi nào cần custom render?"
- "Làm sao share business logic giữa Android/iOS với Kotlin Multiplatform (KMM)?"
- "React Native performance: Làm sao đạt 60fps animation? JS thread vs UI thread?"
- "Chiến lược code sharing giữa cross-platform team: Monorepo vs multi-repo?"

### Kiến trúc Mobile

#### Basic
- "MVVM là gì? Model, View, ViewModel hoạt động thế nào?"
- "Repository pattern là gì? Tại sao cần Repository layer?"
- "Clean Architecture trên mobile: Domain, Data, Presentation layers?"
- "Dependency Injection là gì? Tại sao cần DI trong mobile?"

#### Medium
- "So sánh MVVM, MVP, MVI, MVC? Khi nào dùng cái nào?"
- "Làm sao handle config changes (screen rotation) trong Android?"
- "UseCase pattern: Có cần thiết không? Khi nào nên có UseCase layer?"
- "Unidirectional Data Flow (UDF) là gì? Implement trong mobile thế nào?"
- "Module hóa mobile app: Chiến lược tách module (feature vs layer)?"

#### Advanced
- "So sánh Clean Architecture vs MVVM+Repository trong dự án thực tế?"
- "Làm sao thiết kế architecture cho app multi-platform (Android + iOS + Web)?"
- "Design system trên mobile: Cách chia sẻ UI components giữa các team?"
- "Navigation architecture cho app 100+ màn hình: Deep link, Deferred deep link?"
- "Khi nào nên dùng micro-frontend pattern trên mobile?"

### Testing Mobile

#### Basic
- "Phân biệt Unit test, Integration test, UI test (E2E) trên mobile?"
- "Viết Unit test cho ViewModel trong Android với JUnit + MockK?"
- "Viết Unit test cho ViewModel trong iOS với XCTest?"
- "Mock vs Stub vs Fake? Dùng thế nào trong mobile testing?"
- "Test Coverage là gì? Nên target bao nhiêu %?"

#### Medium
- "TDD trên mobile: Red-Green-Refactor cycle? Có phù hợp không?"
- "Làm sao test Room Database/dao? In-memory database trong test?"
- "Test Coroutines/Flow: TestDispatcher, runTest, turbine?"
- "UI testing với Espresso vs Compose testing vs detekt?"
- "Snapshot testing là gì? Ưu nhược điểm so với UI test truyền thống?"

#### Advanced
- "Chiến lược testing cho app có 50+ module? Test pyramid vs testing trophy?"
- "Làm sao setup CI pipeline để chạy E2E test tự động cho mobile?"
- "Flaky test trong mobile: Nguyên nhân và cách xử lý?"
- "Maestro vs Detox vs Appium? So sánh cho cross-platform E2E testing?"
- "Contract testing giữa mobile app và backend API? Pact testing?"

### Hiệu năng Mobile

#### Basic
- "ANR là gì? Nguyên nhân gây ANR và cách phòng tránh?"
- "Làm sao tối ưu RecyclerView/UICollectionView performance?"
- "Image loading: Glide vs Coil vs Kingfisher vs SDWebImage?"
- "App startup time: Cold start vs Warm start vs Hot start?"
- "Làm sao đo memory usage của mobile app?"

#### Medium
- "Android Profiler vs Xcode Instruments: Dùng analyze cái gì?"
- "ProGuard/R8 code shrinking và obfuscation hoạt động thế nào?"
- "Network optimization: Caching, GZIP, HTTP/2, GraphQL vs REST?"
- "Làm sao giảm APK/IPA size? App Bundle, App Thinning, On-demand resources?"
- "ListView/LazyVStack vs RecyclerView/LazyColumn: Cơ chế recycling?"

#### Advanced
- "Render performance: Làm sao đạt 120fps trên ProMotion display?"
- "Battery optimization: Background task, Location, Network? Doze mode/Background Tasks?"
- "Memory management: Cách detect và fix retain cycle, memory leak trên mobile?"
- "Làm sao implement performance monitoring pipeline để phát hiện regression?"
- "Jank stats, Frame metrics? Làm sao đo và cải thiện frame rendering?"

### Triển khai & CI/CD

#### Basic
- "Quy trình build và upload app lên Google Play/App Store?"
- "Code signing là gì? Tại sao cần ký APK/IPA?"
- "Build types (Debug/Release) và Product Flavors là gì?"
- "TestFlight và Internal Testing là gì? Cách phân phối bản test?"
- "Version code vs Version name trên Android? Build number trên iOS?"

#### Medium
- "Fastlane là gì? Các action cơ bản: gym, deliver, match, snapshot?"
- "Làm sao tự động hóa screenshot cho App Store listing với Fastlane?"
- "CI/CD cho mobile: GitHub Actions vs Bitrise vs CircleCI?"
- "Làm sao quản lý environment (dev/staging/prod) trong mobile CI/CD?"
- "Firebase App Distribution vs TestFlight cho internal testing?"

#### Advanced
- "Self-hosted CI runner cho mobile: Thiết lập macOS runner cho iOS build?"
- "Làm sao implement automated E2E testing trong CI pipeline cho mobile?"
- "Phased release và staged rollout: Chiến lược release cho app 10M+ users?"
- "Code signing automation: Cách quản lý certificate/profile trong team lớn?"
- "App Bundle vs APK: Tại sao Google Play yêu cầu App Bundle?"

### Bảo mật Mobile

#### Basic
- "Keystore (Android) và Keychain (iOS) là gì? Dùng để lưu gì?"
- "HTTPS và SSL Pinning là gì? Tại sao cần SSL Pinning?"
- "Encrypt SharedPreferences và DataStore thế nào?"
- "ProGuard/R8: Obfuscation khác gì encryption?"

#### Medium
- "Biometric Authentication: Fingerprint/FaceID? Cách implement an toàn?"
- "Root/Jailbreak detection: Có nên implement? Cách làm?"
- "Secure storage cho token và secret key trên mobile?"
- "Man-in-the-middle attack là gì? Làm sao phòng chống trên mobile?"
- "Android: Network Security Config, Cleartext traffic policy?"

#### Advanced
- "Thiết kế hệ thống bảo mật end-to-end cho mobile banking app?"
- "Reverse engineering mobile app: Cách bảo vệ code native (C/C++)?"
- "OWASP Mobile Top 10: Các lỗ hổng bảo mật phổ biến nhất?"
- "Runtime Application Self-Protection (RASP) trên mobile?"
- "Key attestation và SafetyNet/Play Integrity: Kiểm tra device integrity?"

## Dự án mẫu để lấp gap

### Level Junior — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "Weather App với OpenWeather API" | REST API, JSON parsing, MVVM cơ bản, UI layout | 2-3 tuần | Kotlin/Compose hoặc Swift/SwiftUI, Retrofit/URLSession |
| 2 | "Todo App với Local Storage" | CRUD, Room/Core Data, Navigation, State management | 2 tuần | Kotlin (Room + Compose) hoặc Swift (Core Data + SwiftUI) |
| 3 | "News Reader App với NewsAPI" | RecyclerView/LazyVStack, Image loading, Pagination, Search | 3-4 tuần | Kotlin/Compose + Coil hoặc Swift/SwiftUI + Kingfisher |
| 4 | "Calculator App với Multi-platform" | Cross-platform basics, UI layout, State management, Conditional rendering | 2-3 tuần | Flutter hoặc React Native, Provider/Riverpod |
| 5 | "App đặt lịch hẹn đơn giản" | Form validation, Date picker, Local notification, Room/Core Data | 3-4 tuần | Kotlin (Compose + Room) hoặc Swift (SwiftUI + Core Data) |

### Level Mid — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "E-Commerce App với nhiều module" | Multi-module, DI (Hilt/Koin), Navigation, Payment flow, Cart management | 6-8 tuần | Kotlin, Compose, Hilt, Retrofit, Room, Stripe SDK |
| 2 | "Chat App Real-time với Firebase" | Firestore, Push Notification (FCM/APNs), Offline persistence, Image upload | 4-6 tuần | Kotlin/Swift, Firebase, Glide/Kingfisher, CameraX |
| 3 | "Cross-platform Social Feed App" | Cross-platform UI, State management, Infinite scroll, Image caching, Video player | 6-8 tuần | Flutter (BLoC) hoặc React Native (Redux), Fastlane |
| 4 | "Fitness Tracker với Wearable" | Sensor data, HealthKit/Google Fit, Charts, Background service, WorkManager | 6-8 tuần | Kotlin (Compose + Wear OS) hoặc Swift (SwiftUI + watchOS) |
| 5 | "Mini CI/CD Pipeline cho Mobile App" | Fastlane automation, Code signing, Automated testing, Beta distribution | 3-4 tuần | Fastlane, GitHub Actions, Firebase App Distribution, XCTest/JUnit |

### Level Senior — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "Mobile Banking App Offline-first" | Offline-first, Encryption, Biometric auth, Secure storage, Background sync, Anti-tampering | 10-12 tuần | Kotlin/Compose, Room, Hilt, Security Crypto, WorkManager |
| 2 | "Super App với Mini-app Architecture" | Micro-frontend, Plugin system, Dynamic feature modules, Module federation, Hot update | 12-16 tuần | Kotlin, Dynamic Features, KMM hoặc React Native (Micro-frontend) |
| 3 | "White-label Mobile App Platform" | Multi-tenant, Branding system, Remote config, Feature flags, CI/CD cho nhiều variant | 10-12 tuần | Flutter/Kotlin, Firebase Remote Config, Fastlane, App Bundle |
| 4 | "Video Streaming App Hiệu năng cao" | ExoPlayer/AVPlayer, Adaptive bitrate, Offline download, DRM, PiP, Background play | 8-12 tuần | Kotlin/Compose (ExoPlayer) hoặc Swift/SwiftUI (AVPlayer), ExoPlayer DRM |
| 5 | "Mobile Observability Platform" | Crash reporting, Custom metrics, Performance monitoring, Network logging, User session replay | 8-10 tuần | Kotlin Multiplatform, Firebase/Sentry, OpenTelemetry, Custom analytics |
