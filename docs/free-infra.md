# 🔧 免费基础设施（消息队列 / K8s / 监控 / 邮件）

> 最后更新: 2026-06-07

## 📨 消息队列

### 1. Aiven（🏆 免费 Kafka）

| 服务 | 免费额度 |
|------|----------|
| Apache Kafka | 1个免费集群 |
| PostgreSQL | 1个实例 |
| MySQL | 1个实例 |
| OpenSearch | 1个实例 |
| Redis | 1个实例 |

**注册**: https://aiven.io
**亮点**: 全托管 Kafka，$0/月，无需信用卡

---

### 2. Amazon SQS（Serverless 消息队列）

| 项目 | 免费额度 |
|------|----------|
| 标准队列 | 100万请求/月（永久免费） |
| FIFO队列 | — |

**亮点**: 无需管理基础设施，AWS 永久免费层

---

### 3. RabbitMQ（自建 — 完全免费）

```bash
# Oracle ARM VM 上自建
docker run -d --name rabbitmq \
  -p 5672:5672 -p 15672:15672 \
  rabbitmq:3-management
```

---

### 4. Redis Streams（免费替代方案）

```bash
# 用 Redis 做轻量消息队列
docker run -d --name redis -p 6379:6379 redis:7
```

**适用**: 低流量场景，已经用 Redis 的项目

---

## ☸️ Kubernetes

### 1. GKE Free Tier

| 项目 | 免费额度 |
|------|----------|
| zonal集群 | $74.40/月 credit |
| Autopilot | $74.40/月 credit |

**注意**: 免费的是控制面，节点费用另算（可用 e2-micro 免费VM）

---

### 2. IBM Cloud Kubernetes

| 项目 | 免费额度 |
|------|----------|
| 集群 | 免费 Lite 版 |

**注册**: https://www.ibm.com/products/cloud/free/kubernetes

---

### 3. Okteto（免费 K8s）

| 项目 | 免费额度 |
|------|----------|
| CPU | 2核 |
| 内存 | 4GB |
| 存储 | 10GB |

**注册**: https://okteto.com

---

### 4. vCluster（虚拟 K8s — 免费）

| 项目 | 说明 |
|------|------|
| 类型 | 在任意K8s上创建虚拟集群 |
| 费用 | 永久免费，无时间限制 |
| 亮点 | 企业级多租户 |

**注册**: https://www.vcluster.com

---

### 5. K3s（自建 — 完全免费）

```bash
# Oracle ARM VM 上自建轻量 K8s
curl -sfL https://get.k3s.io | sh
```

---

## 📊 监控与可观测性

### 1. Grafana Cloud（🏆 推荐）

| 项目 | 免费额度 |
|------|----------|
| Metrics | 10K series |
| Logs | 50GB/月 |
| Traces | 免费 |
| Dashboard | 无限 |
| Alert | 免费 |

**注册**: https://grafana.com/products/cloud/
**亮点**: 业界标杆，Prometheus + Loki + Tempo 全家桶

---

### 2. Uptime Kuma（自建 — 完全免费）

```bash
docker run -d --name uptime-kuma \
  -p 3001:3001 \
  -v uptime-kuma:/app/data \
  louislam/uptime-kuma:1
```

**亮点**: 漂亮的监控面板，支持 HTTP/TCP/DNS/Ping 等多种探测

---

### 3. Better Stack（原 Logtail）

| 项目 | 免费额度 |
|------|----------|
| 日志 | 1GB/月 |
| 监控 | 5个心跳 |
| 状态页 | 免费 |

**注册**: https://betterstack.com

---

## 📧 邮件服务

### 1. Resend（🏆 首选 — 开发者友好）

| 项目 | 免费额度 |
|------|----------|
| 邮件 | 100封/天 |
| 域名 | 免费 |
| SDK | React Email |

**注册**: https://resend.com

---

### 2. Amazon SES

| 项目 | 免费额度 |
|------|----------|
| 邮件 | 62000封/月（EC2托管） |
| — | 3200封/月（非EC2） |

**注意**: 需要先在沙盒模式验证

---

### 3. Mailgun

| 项目 | 免费额度 |
|------|----------|
| 邮件 | 前3个月1000封/月 |

---

### 4. SendGrid

| 项目 | 免费额度 |
|------|----------|
| 邮件 | 100封/天 |
| Email Marketing | 无限联系人 |

**注册**: https://sendgrid.com

---

## 🔐 Auth 服务

### 1. Clerk

| 项目 | 免费额度 |
|------|----------|
| MAU | 10,000/月 |
| Social Login | 支持 |
| MFA | 支持 |

### 2. Auth0

| 项目 | 免费额度 |
|------|----------|
| MAU | 7,500/月 |
| Social Login | 支持 |

### 3. Supabase Auth

| 项目 | 免费额度 |
|------|----------|
| MAU | 50,000/月 |
| 方式 | 邮箱/手机/社交 |

## 📋 CI/CD

| 服务 | 免费额度 |
|------|----------|
| GitHub Actions | 2000分钟/月（公开仓库无限） |
| GitLab CI | 400分钟/月 |
| CircleCI | 6000分钟/月（Docker） |
| Travis CI | 1000次/月 |
| Vercel | 6000构建分/月 |
| Netlify | 300构建分/月 |
| Cloudflare Pages | 500次构建/月 |

## 🔗 VPN / 网络

| 服务 | 免费额度 |
|------|----------|
| Tailscale | 3用户/100设备免费 |
| WireGuard | 自建完全免费 |
| Cloudflare Tunnel | 免费，无需公网IP |

**Cloudflare Tunnel 用法**:
```bash
cloudflared tunnel --url http://localhost:3000
# 获得一个公网URL访问本地服务
```

## 📊 基础设施免费对比矩阵

| 类别 | 首选 | 次选 | 自建 |
|------|------|------|------|
| 消息队列 | Aiven Kafka | AWS SQS | RabbitMQ/Redis |
| Kubernetes | Okteto | GKE Free | K3s |
| 监控 | Grafana Cloud | Better Stack | Uptime Kuma |
| 日志 | Grafana Loki | — | — |
| 邮件 | Resend | SendGrid | 自建SMTP |
| Auth | Supabase Auth | Clerk | — |
| CI/CD | GitHub Actions | CircleCI | — |
| VPN/隧道 | Cloudflare Tunnel | Tailscale | WireGuard |
