# Security Engineer — Skill Framework

## Tổng quan
- **Tên role:** Security Engineer
- **Level:** Junior → Mid → Senior → Lead
- **Mô tả:** Bảo vệ hệ thống thông tin, phát hiện và ngăn chặn các mối đe dọa an ninh mạng. Thiết kế, triển khai và duy trì các giải pháp bảo mật cho hạ tầng, ứng dụng và dữ liệu của tổ chức. Bao gồm cả Blue Team (phòng thủ), Red Team (tấn công mô phỏng) và DevSecOps.
- **Tags:** security, cybersecurity, network-security, web-security, pentesting, soc, cloud-security, cryptography, iam, devsecops

## Kỹ năng theo cấp độ

### Level 1: Fresher/Junior (0-2 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Kiến thức nền tảng An ninh mạng | CIA Triad (Confidentiality, Integrity, Availability), các loại tấn công phổ biến (Phishing, Malware, DDoS, Man-in-the-Middle), nguyên lý defense-in-depth, Risk = Threat × Vulnerability × Impact | 20% | cybersecurity-basics, cia-triad, threat-modeling |
| 2 | Network Security cơ bản | TCP/IP, OSI Model, Firewall (stateful/stateless), IDS/IPS khái niệm, VPN (IPSec/SSL VPN), Port scanning, DNS security basics, Network segmentation (VLAN) | 20% | network-security, firewall, vpn, tcp-ip |
| 3 | Web Security cơ bản | OWASP Top 10 tổng quan, HTTP/HTTPS protocol, CORS, Cookie security (HttpOnly, Secure, SameSite), CSP cơ bản | 15% | web-security, owasp, http, cors |
| 4 | Cryptography cơ bản | Symmetric vs Asymmetric encryption, Hashing (MD5, SHA-256, bcrypt, Argon2), PKI concepts (Certificate, CA, Chain of Trust), TLS/SSL handshake | 15% | cryptography, encryption, hashing, tls |
| 5 | OS Security | Linux security basics (permissions, users/groups, iptables, SELinux/AppArmor concept), Windows security basics (NTFS permissions, GPO, Event Viewer), Hardening cơ bản | 10% | os-security, linux, windows, hardening |
| 6 | Security Tools cơ bản | Nmap (port scan, OS detection, version detection), Wireshark (packet capture, traffic analysis cơ bản), Burp Suite cơ bản, Metasploit cơ bản | 10% | tools, nmap, wireshark, burpsuite |
| 7 | Scripting & Automation | Python/Go cho security tasks: network socket, HTTP request automation, file I/O, JSON/XML parsing, subprocess/command execution | 10% | scripting, python, automation |

### Level 2: Junior/Mid (1-4 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Web Security chuyên sâu | OWASP Top 10 chi tiết: SQL Injection (blind, error-based, union), XSS (Stored/Reflected/DOM), CSRF, SSRF, XXE, IDOR, Path Traversal, File Upload bypass, Deserialization attack, Server-Side Template Injection (SSTI) | 25% | web-security, owasp, sqli, xss, csrf, ssrf |
| 2 | Penetration Testing Methodology | PTES (Pre-engagement → Intelligence Gathering → Threat Modeling → Vulnerability Analysis → Exploitation → Post-Exploitation → Reporting), Reconnaissance (passive/active), Enumeration, Exploitation frameworks (Metasploit, Cobalt Strike), Privilege Escalation (Linux/Windows), Lateral Movement | 20% | pentesting, methodology, exploitation, recon |
| 3 | SOC/Blue Team Operations | SIEM fundamentals (Splunk/ELK/Azure Sentinel), Log analysis (syslog, Windows Event Log, web server log), Alert triage, Incident Response cơ bản (Preparation, Identification, Containment, Eradication, Recovery), Basic threat intelligence (IOC, TTP) | 15% | soc, siem, splunk, incident-response, blue-team |
| 4 | Cloud Security cơ bản | Shared Responsibility Model, IAM (User/Role/Policy), VPC Security (Security Group/NACL, subnet isolation), KMS/HSM, WAF, CloudTrail/CloudWatch logging | 15% | cloud-security, aws, iam, kms, waf |
| 5 | Authentication & Authorization | OAuth2 (Authorization Code, Client Credentials, PKCE), OIDC, SAML 2.0, JWT (structure, signature, common attacks), MFA (TOTP, FIDO2/WebAuthn, Push notification), Session management security | 10% | iam, oauth2, oidc, jwt, saml, mfa |
| 6 | Secure SDLC cơ bản | SAST (SonarQube, Semgrep, Checkmarx), DAST (OWASP ZAP, Burp Suite Scanner), Code review for security, Dependency scanning (Snyk, Dependabot, OWASP Dependency-Check) | 10% | secure-sdlc, sast, dast, code-review |
| 7 | Malware Analysis cơ bản | Static analysis (strings, PE header, hashing), Dynamic analysis (sandbox, process monitor), Packers/obfuscation detection, VirusTotal integration | 5% | malware, analysis, reverse-engineering |

### Level 3: Mid/Senior (3+ năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Cloud Security chuyên sâu | Multi-account strategy, Service Control Policies (SCP), Resource-based policies, Network security (Transit Gateway, VPC peering, PrivateLink), Secrets management (Vault/AWS Secrets Manager), Container/K8s security (Pod Security, Network Policy, Image scanning), Serverless security | 20% | cloud-security, aws, gcp, kubernetes-security, secrets |
| 2 | Threat Hunting | Hypothesis-driven hunting, MITRE ATT&CK framework (Tactics, Techniques, Procedures), Behavioral analysis, Anomaly detection, Threat Intelligence platforms (MISP), YARA rules, Sigma rules, Memory forensics | 20% | threat-hunting, mitre-attck, forensics, sigma, yara |
| 3 | DevSecOps | CI/CD security (pipeline hardening, signed commits, artifact signing), Infrastructure as Code security (Terraform/Terratest, CloudFormation scanning with cfn_nag/Checkov), Container security (Dockerfile best practices, image signing với Cosign, runtime security với Falco), SAST/DAST/IAST tích hợp pipeline, Policy as Code (OPA/Rego) | 20% | devsecops, ci-cd-security, infrastructure-as-code |
| 4 | Advanced Penetration Testing | Active Directory attacks (Kerberoasting, AS-REP Roasting, DCSync, Golden/Silver Ticket, Pass-the-Hash), Web application advanced (Race condition, HTTP Request Smuggling, Prototype Pollution, GraphQL injection), Network attacks (ARP spoofing, DNS poisoning, VLAN hopping), Mobile app testing (Android/iOS), API security testing | 15% | pentesting, active-directory, web-security, api-security |
| 5 | Security Architecture | Zero Trust Architecture (ZTA), Micro-segmentation, Secure by Design principles, Threat Modeling (STRIDE, PASTA, Attack Trees), Security patterns (Gateway, Sidecar, Ambassador), Defense in Depth design | 15% | security-architecture, zero-trust, threat-modeling |
| 6 | Compliance & Governance | ISO 27001 (ISMS, Annex A controls, Statement of Applicability), SOC2 (Trust Services Criteria: Security, Availability, Confidentiality, Processing Integrity, Privacy), PCI-DSS (12 requirements, SAQ, ROC), GDPR (Data Protection, DPO, DPIA, Right to be forgotten), NIST CSF, Audit readiness | 10% | compliance, iso27001, soc2, pci-dss, gdpr |

### Level 4: Senior/Lead (5+ năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Security Strategy & Program | Security roadmap (3-5 năm), Risk management framework, Budget planning & resource allocation, Security metrics (MTTD, MTTR, Risk Score, Coverage %), Board-level reporting, Security OKR | 25% | strategy, program-management, risk-management |
| 2 | Security Team Leadership | Security team structure (Blue/Red/Purple/Product Security), Hiring & retention, Mentoring & career path, Cross-team collaboration (Engineering, IT, Legal, Compliance), Vendor relationship management | 20% | leadership, team-building, mentoring |
| 3 | Incident Command & Crisis Management | Incident Response Plan (IRP), Table-top exercises, Cross-functional incident command, External communication (PR, Legal, Customer notification), Forensics & chain of custody, Post-incident review & improvement | 20% | incident-response, crisis-management, forensics |
| 4 | Red Team Operations | Adversary emulation (APT simulation), C2 infrastructure design, Operational security (OPSEC), Evasion techniques (EDR/XDR bypass, obfuscation), Purple teaming exercises, Breach & Attack Simulation (BAS: AttackIQ, SafeBreach) | 15% | red-team, adversary-emulation, purple-team |
| 5 | Advanced Security Architecture | Security Reference Architecture for enterprise, Identity fabric (CIAM, Workforce IAM, PAM), Data protection strategy (DLP, Classification, Encryption at rest/in transit/in use), Supply chain security (SBOM, vendor risk), Security mesh architecture | 10% | architecture, data-protection, supply-chain |
| 6 | Security Research & Innovation | Vulnerability research (fuzzing, source code audit), Zero-day discovery workflow, Responsible disclosure program, Threat research publication, Conference speaking, Building security tools/internal frameworks | 10% | research, innovation, vulnerability |

## Câu hỏi phỏng vấn mẫu theo kỹ năng

### Web Security
#### Basic
- "Kể tên ít nhất 5 loại tấn công trong OWASP Top 10 và mô tả ngắn gọn từng loại?"
- "SQL Injection hoạt động thế nào? Phân biệt In-band, Blind, Out-of-band SQLi?"
- "XSS (Cross-Site Scripting) là gì? Phân biệt Reflected, Stored, DOM-based XSS?"
- "CSRF hoạt động thế nào? Các cách phòng chống CSRF?"
- "CORS là gì? Tại sao cần CORS? Misconfiguration CORS có thể dẫn đến tấn công gì?"

#### Medium
- "SSRF là gì? Làm sao khai thác SSRF để truy cập metadata service của cloud (AWS 169.254.169.254)?"
- "Phân biệt Authentication vs Authorization? Các lỗ hổng liên quan đến broken authentication?"
- "XXE (XML External Entity) là gì? Làm sao phòng chống XXE trong parser XML?"
- "JWT attack surface? Các kỹ thuật tấn công JWT: none algorithm, HMAC/RSA confusion, kid injection?"
- "CSP (Content Security Policy) là gì? Làm sao bypass CSP? Cấu hình CSP chặt mà vẫn hoạt động?"

#### Advanced
- "HTTP Request Smuggling — giải thích nguyên nhân gốc rễ? CL.TE vs TE.CL vs TE.TE?"
- "Prototype Pollution trong JavaScript — cơ chế và cách khai thác?"
- "Deserialization attack — giải thích gadget chain trong Java (CommonsCollections) hoặc .NET?"
- "OAuth 2.0 attack surface? Các lỗi phổ biến khi implement OAuth2: redirect_uri bypass, CSRF thiếu state, PKCE bypass?"
- "Thiết kế Web Application Firewall (WAF) — core rules, custom rules, và cách bypass WAF phổ biến?"

### Network Security
#### Basic
- "OSI Model 7 lớp? Chức năng từng lớp và protocol tương ứng?"
- "TCP 3-way handshake hoạt động thế nào? SYN flood attack là gì?"
- "Phân biệt Stateful vs Stateless Firewall? Khi nào dùng cái nào?"
- "NAT (Network Address Translation) là gì? SNAT vs DNAT khác gì?"
- "VPN là gì? IPSec VPN vs SSL VPN khác gì?"

#### Medium
- "IDS vs IPS khác gì? Signature-based vs Anomaly-based detection?"
- "DNS hoạt động thế nào? DNS poisoning, tunneling, DGA là gì?"
- "Network Segmentation — VLAN, Subnet, Micro-segmentation khác gì và khi nào áp dụng?"
- "ARP spoofing hoạt động thế nào? Làm sao detect và prevent?"
- "BGP hijacking là gì? Hậu quả và cách phòng ngừa?"

#### Advanced
- "Thiết kế network security cho multi-region cloud deployment: Transit Gateway, Firewall placement, DDoS protection?"
- "Zero Trust Network Architecture — khác gì với perimeter-based security? Các thành phần chính?"
- "Deep Packet Inspection (DPI) và TLS Inspection — trade-off giữa security và privacy?"
- "Làm sao phát hiện C2 (Command & Control) traffic? DNS tunneling, HTTPS beaconing, domain fronting?"
- "SD-WAN security — các vấn đề bảo mật mới khi áp dụng SD-WAN?"

### Cryptography
#### Basic
- "Symmetric vs Asymmetric Encryption khác gì? Cho ví dụ mỗi loại?"
- "Hashing là gì? Tại sao lưu password phải dùng bcrypt/Argon2 thay vì MD5/SHA-256?"
- "TLS/SSL hoạt động thế nào? TLS 1.3 khác TLS 1.2 ở điểm gì?"
- "PKI là gì? Certificate chain of trust hoạt động thế nào?"
- "Encoding vs Encryption vs Hashing — phân biệt và cho ví dụ?"

#### Medium
- "Diffie-Hellman key exchange hoạt động thế nào? Man-in-the-Middle tấn công DH thế nào?"
- "AES-GCM vs AES-CBC: khác gì, khi nào dùng cái nào? Padding Oracle Attack trên CBC?"
- "RSA hoạt động thế nào? Tại sao RSA an toàn? Tấn công Bleichenbacher là gì?"
- "Digital Signature hoạt động thế nào? RSA-PSS vs ECDSA?"
- "Quantum computing đe dọa cryptography hiện tại thế nào? Post-quantum cryptography là gì?"

#### Advanced
- "Thiết kế Key Management System (KMS) cho enterprise: key rotation, HSM, envelope encryption?"
- "Forward Secrecy là gì? Tại sao TLS 1.3 bắt buộc Forward Secrecy?"
- "Zero-Knowledge Proof là gì? Ứng dụng thực tế trong security?"
- "Side-channel attack: timing attack, power analysis, cache attack — cơ chế và cách phòng?"
- "So sánh các post-quantum algorithm: Kyber, Dilithium, SPHINCS+?"

### Penetration Testing
#### Basic
- "Phases của một penetration test theo PTES? Mô tả từng phase?"
- "Phân biệt Black-box, Gray-box, White-box testing?"
- "Information Gathering / Reconnaissance — passive vs active recon?"
- "Nmap scan types: SYN scan, TCP connect scan, UDP scan, ACK scan?"
- "Sau khi chiếm được shell, các bước post-exploitation cơ bản?"

#### Medium
- "Privilege Escalation trên Linux — các kỹ thuật phổ biến (SUID, cron job, kernel exploit)?"
- "Privilege Escalation trên Windows — token manipulation, service misconfiguration, potato attacks?"
- "Active Directory enumeration: BloodHound, PowerView, SharpHound — cách dùng?"
- "Lateral movement trong mạng nội bộ — Pass-the-Hash, Pass-the-Ticket, PsExec?"
- "Pivoting và tunneling — SSH tunneling, Chisel, Ligolo khác gì và khi nào dùng?"

#### Advanced
- "Khai thác Kerberos trong AD: Kerberoasting, AS-REP Roasting, Golden/Silver Ticket là gì?"
- "Bypass EDR/AV — unhooking, direct syscall, process injection, DLL sideloading?"
- "C2 (Command & Control) infrastructure — thiết kế redirector, domain fronting, Cobalt Strike malleable C2 profile?"
- "Web Application Firewall (WAF) bypass techniques: encoding, case variation, HTTP parameter pollution?"
- "Làm sao viết báo cáo pentest chuyên nghiệp? Cấu trúc, cách mô tả finding, risk rating (CVSS)?"

### Cloud Security
#### Basic
- "Shared Responsibility Model trong AWS/Azure/GCP là gì? Customer responsible for what?"
- "IAM là gì? User vs Role vs Policy? Least Privilege principle?"
- "Security Group vs NACL trong AWS VPC khác gì?"
- "CloudTrail / Activity Log là gì? Tại sao quan trọng cho security?"
- "S3 bucket security — common misconfigurations và hậu quả?"

#### Medium
- "KMS hoạt động thế nào? Envelope encryption, CMK vs data key, key rotation?"
- "WAF (Web Application Firewall) trên cloud — AWS WAF vs Cloudflare vs Azure Front Door?"
- "Container Security trong ECS/EKS/AKS: image scanning, network policy, Pod Security Admission?"
- "Serverless security (Lambda/Azure Functions) — các attack vector đặc thù?"
- "Cloud Security Posture Management (CSPM) là gì? Các công cụ: Prisma Cloud, Wiz, Orca?"

#### Advanced
- "Thiết kế multi-account security strategy: SCPs, GuardDuty, Security Hub, Control Tower?"
- "Data perimeters trong cloud — làm sao ngăn dữ liệu rò rỉ ra ngoài (VPC Endpoint, S3 bucket policy)?"
- "Identity Federation — SAML/OIDC integration giữa IdP và cloud provider?"
- "Cloud Incident Response — khác on-premise thế nào? Các bước điều tra forensic trên cloud?"
- "Compliance as Code — tự động hóa audit evidence collection cho PCI-DSS/SOC2 trên cloud?"

### SOC / Blue Team
#### Basic
- "Incident Response (IR) lifecycle? NIST IR Framework: Preparation → Detection → Containment → Eradication → Recovery → Lessons Learned?"
- "SIEM là gì? Splunk vs ELK vs Azure Sentinel — khác gì?"
- "Log sources quan trọng cho SOC: Windows Event Log, Syslog, DNS log, Proxy log, Authentication log?"
- "Phân biệt False Positive, True Positive, False Negative, True Negative trong alert?"
- "IOC (Indicators of Compromise) là gì? IOA (Indicators of Attack) khác IOC thế nào?"

#### Medium
- "Alert triage process? Các bước phân tích một alert: verify, context, scope, escalation?"
- "MITRE ATT&CK framework — cấu trúc (Tactics, Techniques, Sub-techniques, Procedures)? Áp dụng thế nào trong SOC?"
- "Threat Intelligence: chiến lược (Pyramid of Pain), nguồn feed (MISP, OTX), tích hợp với SIEM?"
- "Phân tích email phishing: SPF/DKIM/DMARC checks, header analysis, attachment sandbox?"
- "Digital Forensics basics: order of volatility, chain of custody, timeline analysis, memory dump?"

#### Advanced
- "Xây dựng SOC từ đầu: people, process, technology roadmap? Chọn SIEM, SOAR, EDR?"
- "Threat Hunting methodology: hypothesis-driven vs data-driven hunting? Pepsi vs SANS hunting model?"
- "SOAR (Security Orchestration, Automation and Response) — playbook automation, SOAR vs SIEM?"
- "Kỹ thuật phát hiện advanced threat: behavioral analytics, UEBA, anomaly detection bằng ML?"
- "Supply chain attack (SolarWinds style) — làm sao detect và respond? SBOM có giúp ích gì?"

## Dự án mẫu để lấp gap

### Level Junior — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "Web Application Pentest Lab cá nhân" | Web Security cơ bản, OWASP Top 10, Nmap, Burp Suite | 3-4 tuần | Burp Suite, Nmap, Docker (DVWA/BWAPP), OWASP ZAP |
| 2 | "Home SOC với ELK Stack" | SIEM cơ bản, Log analysis, Ubuntu security | 3-4 tuần | ELK (Elasticsearch, Logstash, Kibana), Linux, Suricata |
| 3 | "Scan tự động với Python + Nmap" | Python scripting, Network scanning tự động, Báo cáo | 2-3 tuần | Python, python-nmap, ReportLab, JSON |
| 4 | "Setup VPN Server + Security Audit" | VPN, Network security, Hardening Linux | 2-3 tuần | WireGuard/OpenVPN, Ubuntu, iptables, RSA certificates |
| 5 | "Password Manager CLI (học Cryptography)" | Hashing, AES encrypt/decrypt, PBKDF2, Python | 2-3 tuần | Python, cryptography library, SQLite, bcrypt |

### Level Mid — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "Vulnerable Network Lab + Full Pentest" | Pentesting methodology, Active Directory, Internal network exploitation | 6-8 tuần | VirtualBox/VMware, Windows Server, Kali Linux, Metasploit, BloodHound |
| 2 | "Cloud Security Assessment Tool" | Cloud security, IAM audit, S3 scanner, Python | 4-6 tuần | Python (boto3), Terraform, AWS/Azure, Prowler/ScoutSuite |
| 3 | "DevSecOps Pipeline cho CI/CD" | SAST, DAST, Container scanning, GitHub Actions | 4-6 tuần | GitHub Actions, Trivy, SonarQube, OWASP ZAP, Docker, Cosign |
| 4 | "SOC Lab với Splunk + ELK + SOAR" | SIEM, Alert tuning, Threat intelligence, Playbook automation | 6-8 tuần | Splunk/ELK, TheHive, Cortex, MISP, Sigma, Suricata |
| 5 | "Threat Intelligence Platform cơ bản" | CTI, MISP, IOC management, YARA rules | 4-6 tuần | MISP, Python, YARA, Cortex, API integration |

### Level Senior — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "Zero Trust Architecture Implementation" | Zero Trust, Micro-segmentation, IAM advanced, IdP integration | 8-12 tuần | Okta/Azure AD, Zscaler, Kubernetes Network Policy, HashiCorp Vault |
| 2 | "Enterprise Cloud Security Reference Architecture" | Multi-account, Security Hub, SCPs, GuardDuty, Control Tower | 8-12 tuần | AWS Organizations, Control Tower, Security Hub, Terraform, KMS |
| 3 | "Advanced Threat Detection Pipeline" | UEBA, Machine Learning cho anomaly detection, MITRE ATT&CK mapping | 8-10 tuần | Python ML stack, ELK, Kafka, Airflow, Sigma, Jupyter |
| 4 | "Security Compliance Automation Platform" | Compliance as Code, Audit evidence, ISO 27001/SOC2/GDPR | 8-12 tuần | OpenSCAP, InSpec, Terraform, Python, FastAPI, React dashboard |
