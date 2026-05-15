# DevOps Engineer — Skill Framework

## Tổng quan
- **Tên role:** DevOps Engineer
- **Level:** Junior → Mid → Senior → Lead/Architect
- **Mô tả:** Cầu nối giữa development và operations. Tự động hóa CI/CD, quản lý infrastructure as code, monitoring, và đảm bảo reliability của hệ thống.
- **Tags:** devops, ci-cd, cloud, infrastructure, automation, kubernetes, docker, terraform

## Kỹ năng theo cấp độ

### Level 1: Junior (0-2 năm)
| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Linux cơ bản | Command line, Bash scripting, File system, Process management, Permissions | 20% | linux, bash, shell |
| 2 | Git nâng cao | Branch strategy, Rebase vs Merge, Git hooks, Submodules, GitOps | 15% | git |
| 3 | Docker | Dockerfile, Image building, Container lifecycle, Docker Compose, Networking, Volumes | 20% | docker, container |
| 4 | CI/CD cơ bản | GitHub Actions/GitLab CI/Jenkins, Pipeline stages, Automated testing, Artifact management | 20% | ci-cd, github-actions, jenkins |
| 5 | Cloud cơ bản (AWS/GCP/Azure) | EC2/GCE/VM, S3/Blob, IAM, VPC, CloudWatch/Monitoring | 15% | cloud, aws, gcp, azure |
| 6 | Networking cơ bản | TCP/IP, DNS, HTTP/HTTPS, Load Balancer, Firewall, Subnet, CIDR | 10% | networking, dns, tcp |

### Level 2: Mid (2-4 năm)
| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Infrastructure as Code (Terraform/Pulumi) | HCL, State management, Modules, Provider, Provisioner | 20% | iac, terraform, pulumi |
| 2 | Kubernetes | Pod, Deployment, Service, Ingress, ConfigMap, Secret, Helm, Operators | 20% | kubernetes, k8s, helm |
| 3 | Configuration Management | Ansible/Chef/Puppet, Playbook, Role, Inventory, Idempotency | 15% | ansible, config-management |
| 4 | Monitoring & Observability | Prometheus, Grafana, ELK Stack, Alertmanager, SLO/SLI | 15% | monitoring, prometheus, grafana, elk |
| 5 | Cloud nâng cao | Auto Scaling, Load Balancer, CDN (CloudFront/Cloud CDN), Serverless (Lambda/Cloud Functions) | 15% | cloud, aws, serverless |
| 6 | Security cơ bản | Secrets management (Vault/Secrets Manager), IAM Policy, Security Groups, SSL/TLS | 10% | security, vault |
| 7 | Scripting (Python/Go) | Automation scripts, CLI tools, API integration, SDK usage | 5% | python, go, scripting |

### Level 3: Senior (4+ năm)
| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | System Design cho Infrastructure | Multi-region, Disaster Recovery, High Availability, Capacity Planning, Cost Optimization | 25% | system-design, architecture |
| 2 | Kubernetes nâng cao | Service Mesh (Istio), Custom Operators, Cluster API, Multi-cluster, Security Policies | 20% | kubernetes, istio, service-mesh |
| 3 | GitOps & Platform Engineering | ArgoCD/Flux, Internal Developer Platform (IDP), Self-service infrastructure, Backstage | 20% | gitops, platform, argocd |
| 4 | Security & Compliance | SOC2, PCI-DSS, HIPAA, Audit logging, Vulnerability scanning, Image scanning, Policy as Code (OPA) | 15% | security, compliance |
| 5 | SRE Practices | Error Budget, Incident Response, Post-mortem, Chaos Engineering, Capacity Planning, Toil reduction | 20% | sre, reliability, incident |

### Level 4: Lead/Architect (6+ năm)
| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Infrastructure Architecture | Multi-cloud strategy, Hybrid cloud, Edge computing, Global infrastructure design | 25% | architecture, multi-cloud |
| 2 | FinOps & Cost Optimization | Cloud cost management, Reserved/Savings plans, Resource optimization, Showback/Chargeback | 20% | finops, cost, cloud |
| 3 | Organizational DevOps | DevOps transformation, Team topology, Center of Excellence, Inner source | 20% | org-devops, transformation |
| 4 | Vendor Management | Cloud provider relationship, Tool evaluation, Build vs Buy decisions, Enterprise agreements | 15% | vendor, procurement |
| 5 | Technical Leadership | Architecture review, RFC process, Mentoring, Cross-team standards | 20% | leadership |

## Câu hỏi phỏng vấn mẫu theo kỹ năng

### Linux
#### Basic
- "Các lệnh Linux cơ bản: ls, cd, cp, mv, rm, chmod, chown?"
- "Phân biệt absolute path và relative path?"
- "File permissions trong Linux: rwx, chmod 755 có nghĩa là gì?"
- "Process management: ps, top, kill, nice?"

#### Medium
- "Cron job hoạt động thế nào? Crontab syntax?"
- "Làm sao debug process bị treo? strace, lsof, /proc?"
- "Systemd là gì? Tạo một systemd service?"

#### Advanced
- "Linux kernel tuning cho high-throughput application?"
- "Troubleshoot server bí ẩn: CPU 100%, memory leak, disk full?"

### Docker
#### Basic
- "Docker là gì? Container khác VM thế nào?"
- "Dockerfile các instruction: FROM, RUN, COPY, CMD, ENTRYPOINT?"
- "Docker Compose dùng để làm gì?"

#### Medium
- "Multi-stage build là gì? Lợi ích?"
- "Docker networking: bridge, host, overlay?"
- "Làm sao optimize Docker image size?"

#### Advanced
- "Docker security best practices?"
- "Container orchestration: Docker Swarm vs Kubernetes?"

### Kubernetes
#### Basic
- "Kubernetes là gì? Master node vs Worker node?"
- "Pod, Service, Deployment, ConfigMap, Secret là gì?"
- "kubectl các lệnh cơ bản: get, describe, logs, exec?"

#### Medium
- "Helm là gì? Tạo một Helm chart?"
- "Service types: ClusterIP, NodePort, LoadBalancer?"
- "K8s networking: CNI, Ingress, Network Policy?"

#### Advanced
- "Service Mesh (Istio/Linkerd) giải quyết vấn đề gì?"
- "Custom Operator pattern? Tạo một operator với Operator SDK?"
- "Multi-cluster Kubernetes: federation, service mesh?"

### CI/CD
#### Basic
- "CI/CD là gì? Continuous Integration vs Continuous Delivery vs Continuous Deployment?"
- "GitHub Actions: workflow, job, step?"
- "Jenkins pipeline: declarative vs scripted?"

#### Medium
- "Blue-Green vs Canary vs Rolling deployment?"
- "Làm sao implement automated testing trong CI pipeline?"
- "Artifact management: Docker registry, Nexus, Artifactory?"

#### Advanced
- "Thiết kế CI/CD pipeline cho microservices (50+ services)?"
- "GitOps với ArgoCD/Flux?"

### Infrastructure as Code
#### Basic
- "Infrastructure as Code là gì? Tại sao cần?"
- "Terraform: provider, resource, data source, variable?"

#### Medium
- "Terraform state management: local vs remote? State locking?"
- "Terraform modules: tạo và sử dụng module?"

#### Advanced
- "Terraform vs Pulumi vs Crossplane?"
- "Managing multi-account AWS với Terraform?"

### Monitoring / Observability
#### Basic
- "Monitoring vs Observability khác gì?"
- "Prometheus: metric types (Counter, Gauge, Histogram, Summary)?"

#### Medium
- "Grafana dashboard: panel, variable, alert?"
- "ELK Stack: Elasticsearch, Logstash, Kibana hoạt động thế nào?"
- "Alerting strategy: cảnh báo gì, cho ai, qua kênh nào?"

#### Advanced
- "Thiết kế observability stack cho 100+ microservices?"
- "Distributed tracing với Jaeger/Zipkin?"

### Cloud (AWS)
#### Basic
- "EC2, S3, RDS, ELB là gì? Dùng khi nào?"
- "IAM: User, Role, Policy?"

#### Medium
- "VPC: Subnet, Route Table, NAT Gateway, Internet Gateway?"
- "Auto Scaling Group hoạt động thế nào?"

#### Advanced
- "Multi-region architecture: khi nào cần? DR strategy?"
- "Cost optimization strategy cho AWS?"

## Dự án mẫu để lấp gap

### Level Junior
| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "CI/CD Pipeline cho Web App" | GitHub Actions, Docker, Automated testing, Deploy | 2 tuần | GitHub Actions, Docker, Docker Hub |
| 2 | "Infrastructure Monitoring Setup" | Prometheus, Grafana, Node Exporter, Alerting | 2-3 tuần | Prometheus, Grafana, Docker |
| 3 | "AWS Static Website Hosting" | S3, CloudFront, Route53, ACM, Terraform | 2 tuần | AWS, Terraform, GitHub Actions |
| 4 | "Dockerize Fullstack App" | Docker, Docker Compose, Multi-container, Networking | 1-2 tuần | Docker, Docker Compose, Nginx |

### Level Mid
| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "K8s Cluster cho Microservices" | Kubernetes, Helm, Ingress, Monitoring | 4-6 tuần | K8s, Helm, Prometheus, Grafana, Istio |
| 2 | "GitOps Deployment Pipeline" | ArgoCD, Helm, GitHub Actions, GitOps | 3-4 tuần | ArgoCD, Helm, K8s, GitHub Actions |
| 3 | "Multi-Environment AWS với Terraform" | Terraform, AWS, Remote state, Workspaces | 3-4 tuần | Terraform, AWS, GitHub Actions |
| 4 | "Centralized Logging với ELK" | ELK Stack, Filebeat, Log parsing, Dashboard | 3-4 tuần | Elasticsearch, Logstash, Kibana, Docker |
