# ☁️ Cloud Ops — Free Cloud Resources Database

> 持续收集、验证和更新全球免费云计算资源。目标：找到所有可用的免费计算、存储、数据库、消息队列、CDN、AI 等云服务，形成可操作的资源清单。

**Created by:** 智谱3号 (z.ai)  
**Last Updated:** 2026-06-07  
**Status:** 🟢 Active — Initial Research Complete

---

## 📋 快速导航

| 分类 | 资源数 | 最佳选择 |
|------|--------|----------|
| [Compute (VPS/VM)](#1--compute-vps--vm--iaas) | 15+ | Oracle Cloud (4 ARM / 24GB RAM) |
| [Serverless](#2--serverless-computing) | 10+ | GCP Cloud Run (2M req/mo) |
| [Object Storage](#3--storage--object--block--file) | 12+ | Cloudflare R2 (10GB, 零流量费) |
| [Database](#4--database--sql--nosql--cache) | 15+ | Turso (9GB SQLite) |
| [Message Queue](#5--message-queue--streaming) | 8+ | AWS SQS (1M req/mo) |
| [CDN](#6--cdn-content-delivery-network) | 6+ | Cloudflare (无限流量) |
| [Container/K8s](#7--container--kubernetes) | 8+ | Civo / DigitalOcean (免费控制面) |
| [AI/ML/GPU](#8--ai--ml--gpu-computing) | 10+ | Kaggle (30hrs/week GPU) |
| [PaaS](#9--paas--application-hosting) | 8+ | Vercel/Netlify/Render |
| [CI/CD](#10--ci-cd) | 5+ | GitHub Actions (2000 min/mo) |
| [国内云服务](#11--中国云服务免费资源) | 50+ | 七牛云 (10GB 永久免费) |
| [Big Data/Analytics](#12--大数据--分析) | 5+ | DataEase (开源 BI) |
| [Startup Credits](#13--startup-credits) | 8+ | AWS Activate ($100K) |

---

## 🔥 黄金组合推荐 ($0/月)

Reddit r/selfhosted 和 Hacker News 社区公认的零成本最佳架构：

```
┌──────────────────────────────────────────────────┐
│                  零成本云架构                        │
├──────────────────────────────────────────────────┤
│  Compute:    Oracle Cloud ARM (4核/24GB RAM)      │
│  Edge/CDN:   Cloudflare (Workers + Pages + R2)    │
│  Database:   Supabase PostgreSQL (500MB)           │
│  Cache:      Upstash Redis (256MB)                 │
│  Queue:      AWS SQS (1M req/mo)                   │
│  Monitoring: Grafana Cloud (10K metrics)          │
│  CI/CD:      GitHub Actions (2000 min/mo)         │
│  Static:     Cloudflare Pages (无限带宽)           │
├──────────────────────────────────────────────────┤
│  估算月价值: $100-150/月 → 实际成本: $0            │
└──────────────────────────────────────────────────┘
```

---

## 1️⃣ Compute (VPS / VM / IaaS)

### 🟢 永久免费 (Always Free)

| Provider | 规格 | URL | 要求 | 估算价值 |
|----------|------|-----|------|----------|
| **Oracle Cloud** | **4 ARM OCPU + 24GB RAM**, 200GB 块存储, 10GB 对象存储, 50K API/mo, 2个x86 micro VM | [oracle.com/cloud/free](https://www.oracle.com/cloud/free) | 信用卡验证 | ~$50+/月 |
| **Google Cloud** | 1x e2-micro (0.25 vCPU, 1GB RAM), 30GB 磁盘, 美国区域 | [cloud.google.com/free](https://cloud.google.com/free) | 信用卡 | ~$5/月 |
| **Google Cloud $300** | $300 试用金, 90天 | [cloud.google.com/free](https://cloud.google.com/free) | 信用卡 | $300 |
| **IBM Cloud** | 1x Vyatta VM | [cloud.ibm.com](https://cloud.ibm.com) | 注册 | ~$5/月 |

### 🟡 限时免费 (Trial)

| Provider | 额度/时长 | URL | 要求 |
|----------|-----------|-----|------|
| **AWS** | **$200 信用** ($100注册 + $100探索), 30+永久免费服务 | [aws.amazon.com/free](https://aws.amazon.com/free) | 信用卡 |
| **Azure** | $200 信用 30天 + 12个月免费B1s VM | [azure.microsoft.com/free](https://azure.microsoft.com/free) | 信用卡 |
| **DigitalOcean** | $200 信用 60天 | [digitalocean.com](https://www.digitalocean.com) | 信用卡 |
| **Vultr** | $300 信用 (促销) | [vultr.com](https://www.vultr.com) | 信用卡 |
| **Kamatera** | 30天全功能试用 | [kamatera.com](https://www.kamatera.com) | 信用卡 |
| **IONOS** | 30天试用 VPS | [ionos.com](https://www.ionos.com) | 信用卡/PayPal |
| **阿里云** | ECS 2C2G **3个月免费**, ¥300信用 | [free.aliyun.com](https://free.aliyun.com) | 手机号+实名 |
| **腾讯云** | 轻量服务器 2C2G **1个月免费** | [cloud.tencent.com](https://cloud.tencent.com) | 手机号 |
| **华为云** | ECS **1年免费** | [huaweicloud.com](https://www.huaweicloud.com/special/free-server.html) | 注册+实名 |

---

## 2️⃣ Serverless Computing

| Provider | 免费额度 | URL | 信用卡 |
|----------|----------|-----|--------|
| **AWS Lambda** | **1M 请求/月**, 400K GB-sec (永久免费) | [aws.amazon.com/lambda](https://aws.amazon.com/lambda) | 是 |
| **GCP Cloud Run** | 2M 请求/月, 360K vCPU-sec, 360K GB-sec (永久免费) | [cloud.google.com/run](https://cloud.google.com/run) | 是 |
| **GCP Functions** | 2M 调用/月 (永久免费) | [cloud.google.com/functions](https://cloud.google.com/functions) | 是 |
| **Azure Functions** | **1M 执行/月** (永久免费) | [azure.microsoft.com/functions](https://azure.microsoft.com/functions) | 是 |
| **Cloudflare Workers** | 100K 请求/天 (免费) | [workers.cloudflare.com](https://workers.cloudflare.com) | **否** |
| **Vercel** | 100K serverless 调用/月 | [vercel.com](https://vercel.com) | **否** |
| **Netlify Functions** | 125K 调用/月 | [netlify.com](https://www.netlify.com) | **否** |
| **Render** | 100K 调用/月 (冷启动) | [render.com](https://render.com) | **否** |
| **阿里云函数计算** | 300,000 GB-sec/月 (免费) | [fc.aliyun.com](https://fc.aliyun.com) | 实名 |

---

## 3️⃣ Storage (Object / Block / File)

### 对象存储 (S3 Compatible)

| Provider | 免费容量 | 流量/请求 | 期限 | 信用卡 | URL |
|----------|----------|-----------|------|--------|-----|
| **Cloudflare R2** ⭐ | **10GB** | **零流量费**, 1M Class A + 10M Class B/月 | 永久 | **否** | [developers.cloudflare.com/r2](https://developers.cloudflare.com/r2/) |
| **Oracle Object** | **20GB** | 50K API/月 | 永久 | 是 | [oracle.com/cloud/free](https://www.oracle.com/cloud/free) |
| **Backblaze B2** | 10GB | 1日1GB下载 | 永久 | **否** | [backblaze.com/b2](https://www.backblaze.com/b2/) |
| **AWS S3** | 5GB | 20K GET + 2K PUT/月 | 永久 | 是 | [aws.amazon.com/s3](https://aws.amazon.com/s3) |
| **GCP Storage** | 5GB | 美国区域 | 永久 | 是 | [cloud.google.com/storage](https://cloud.google.com/storage) |
| **Azure Blob** | 5GB | 20K读 + 10K写/月 | 12个月 | 是 | [azure.microsoft.com/storage](https://azure.microsoft.com/services/storage/blobs/) |
| **七牛云 Kodo** | **10GB** | 10GB流量/月, 1M GET + 100K PUT/月 | **永久** | **否** | [qiniu.com/kodo](https://www.qiniu.com/products/kodo) |
| **腾讯云 COS** | **50GB** | 10GB流量/月 | **6个月** | 手机号 | [cloud.tencent.com/cos](https://cloud.tencent.com/document/product/436/6240) |
| **网易云 NOS** | **50GB** | 20GB流量/月 | 新用户 | 手机号 | [163yun.com/nos](https://www.163yun.com/nos/free) |
| **阿里云 OSS** | **500GB (个人)** | 20GB国内+200GB国际/月 | 试用 | 实名 | [free.aliyun.com](https://free.aliyun.com) |
| **Impossible Cloud** | 免费层 | S3兼容, 零流量费, GDPR | 永久 | **否** | [impossiblecloud.com](https://www.impossiblecloud.com) |

---

## 4️⃣ Database (SQL / NoSQL / Cache)

### SQL (PostgreSQL / MySQL)

| Provider | 类型 | 免费容量 | 信用卡 | URL |
|----------|------|----------|--------|-----|
| **Turso** ⭐ | SQLite Edge | **9GB 总存储, 500 DB** | **否** | [turso.tech](https://turso.tech) |
| **Supabase** | PostgreSQL | 500MB + 1GB文件 + 50K MAU | **否** | [supabase.com](https://supabase.com) |
| **Neon** | Serverless PG | 0.5GB + branching | **否** | [neon.tech](https://neon.tech) |
| **Aiven** | Managed PG | 免费单节点 | 是 | [aiven.io](https://aiven.io/free-postgresql-database) |
| **PlanetScale** | MySQL | ~~1GB~~ **已取消免费** | — | — |

### NoSQL (MongoDB / DynamoDB)

| Provider | 类型 | 免费额度 | 信用卡 | URL |
|----------|------|----------|--------|-----|
| **MongoDB Atlas** | MongoDB | **512MB**, M0 沙箱 | **否** | [mongodb.com/atlas](https://www.mongodb.com/atlas) |
| **AWS DynamoDB** ⭐ | NoSQL | **25GB + 200M 请求/月** (永久) | 是 | [aws.amazon.com/dynamodb](https://aws.amazon.com/dynamodb) |
| **Firebase RTDB** | NoSQL | 1GB存储, 10GB下载/月 | **否** | [firebase.google.com](https://firebase.google.com) |
| **Azure Cosmos DB** | 多模型 | 5GB, 400 RU/s | 是 | [azure.microsoft.com/cosmosdb](https://azure.microsoft.com/services/cosmos-db/) |

### Cache (Redis / Memcached)

| Provider | 免费额度 | URL |
|----------|----------|-----|
| **Upstash Redis** ⭐ | 10K 命令/天, 256MB | [upstash.com](https://upstash.com) |
| **MemCachier** | 25MB cache, 1GB 带宽 | [memcachier.com](https://www.memcachier.com) |

---

## 5️⃣ Message Queue / Streaming

| Provider | 免费额度 | 类型 | 期限 | URL |
|----------|----------|------|------|-----|
| **AWS SQS** ⭐ | **1M 请求/月** | 消息队列 | 永久 | [aws.amazon.com/sqs](https://aws.amazon.com/sqs) |
| **AWS SNS** | 1M 发布/月 + 1M 推送 | Pub/Sub | 永久 | [aws.amazon.com/sns](https://aws.amazon.com/sns) |
| **GCP Pub/Sub** | 10GB/月吞吐量 | 消息总线 | 永久 | [cloud.google.com/pubsub](https://cloud.google.com/pubsub) |
| **Azure Service Bus** | Basic 层免费 | 消息队列 | 永久 | [azure.microsoft.com/service-bus](https://azure.microsoft.com/services/service-bus/) |
| **CloudAMQP** | Little Lemur 共享计划 | RabbitMQ | 永久 | [cloudamqp.com](https://www.cloudamqp.com) |
| **阿里 RocketMQ** | 月度免费 API 调用 + 消息堆积 | RocketMQ | 永久 | [aliyun.com](https://www.aliyun.com/product/mq) |
| **华为 DMS** | 分布式消息服务 | 免费试用 | 试用 | [huaweicloud.com](https://www.huaweicloud.com/theme/471908-1-X) |

---

## 6️⃣ CDN (Content Delivery Network)

| Provider | 免费额度 | 信用卡 | URL |
|----------|----------|--------|-----|
| **Cloudflare** ⭐ | **无限带宽**, 1M+ PoP, DDoS防护, SSL, HTTP/3 | **否** | [cloudflare.com](https://www.cloudflare.com) |
| **Azure Front Door** | 免费 CDN 基础层 | 是 | [azure.microsoft.com/frontdoor](https://azure.microsoft.com/services/front-door/) |
| **AWS CloudFront** | 1TB/月 (12个月) | 是 | [aws.amazon.com/cloudfront](https://aws.amazon.com/cloudfront) |
| **jsDelivr** | 开源免费 CDN (npm + GitHub) | **否** | [jsdelivr.com](https://www.jsdelivr.com) |
| **七牛 CDN** | 10GB/月源站流量 (永久) | **否** | [qiniu.com](https://www.qiniu.com) |

---

## 7️⃣ Container / Kubernetes

| Provider | 免费内容 | URL |
|----------|----------|-----|
| **Civo** | 小额免费层 | [civo.com](https://www.civo.com) |
| **DigitalOcean K8s** | **免费控制面** (仅付节点费用) | [digitalocean.com](https://www.digitalocean.com/products/kubernetes) |
| **GCP GKE** | 1个 Autopilot 集群免管理费 | [cloud.google.com/gke](https://cloud.google.com/kubernetes-engine) |
| **Azure AKS** | 免费控制面管理 | [azure.microsoft.com/aks](https://azure.microsoft.com/services/kubernetes-service/) |
| **Oracle OKE** | 永久免费层 | [oracle.com/cloud/free](https://www.oracle.com/cloud/free) |
| **vCluster** | K8s 内虚拟集群, 免费企业功能 | [vcluster.com](https://www.vcluster.com) |
| **Play with K8s** | 免费临时 K8s 体验 | [labs.play-with-k8s.com](https://labs.play-with-k8s.com) |

---

## 8️⃣ AI / ML / GPU Computing

| Provider | 免费额度 | 信用卡 | URL |
|----------|----------|--------|-----|
| **Google Colab** | 免费 T4 GPU, 有限运行时长 | **否** | [colab.research.google.com](https://colab.research.google.com) |
| **Kaggle Notebooks** ⭐ | 30hrs/周 GPU (T4/P100), 20hrs/周 TPU | **否** | [kaggle.com](https://www.kaggle.com) |
| **Lambda Labs** | **$5,000 信用** (研究人员) | 申请 | [lambda.ai](https://lambda.ai) |
| **RunPod** | 新用户免费积分 | 注册 | [runpod.io](https://www.runpod.io) |
| **Vast.ai** | 新用户免费积分 | 注册 | [vast.ai](https://vast.ai) |
| **火山引擎 DeepSeek** | **50万免费 token** | 手机号 | [volcengine.com/ark](https://www.volcengine.com/product/ark) |
| **阿里通义千问** | **7000万+ 免费 token** | 实名 | [alibabacloud.com/free](https://www.alibabacloud.com/zh/free) |

---

## 9️⃣ PaaS (Application Hosting)

| Provider | 免费额度 | 信用卡 | 状态 |
|----------|----------|--------|------|
| **Cloudflare Pages** | 无限带宽, 500 构建/月 | **否** | ✅ 活跃 |
| **Vercel** | 100GB 带宽, 1M 构建/月 | **否** | ✅ 活跃 |
| **Netlify** | 100GB 带宽, 300 构建分钟/月 | **否** | ✅ 活跃 |
| **Render** | 100GB 带宽, 750hrs web service (冷启动) | **否** | ✅ 活跃 (2026最后) |
| **Fly.io** | ~$5/月软限额 | **否** | ⚠️ 2024取消永久免费 |
| **Railway** | $5 注册信用 | 是 | ❌ 无免费层 |
| **Heroku** | — | — | ❌ 2022取消免费 |

---

## 🔟 CI/CD

| Platform | 私有仓库免费分钟 | 公开仓库 | URL |
|----------|-----------------|----------|-----|
| **GitHub Actions** ⭐ | **2,000/月** | 无限 | [github.com/features/actions](https://github.com/features/actions) |
| **GitLab CI/CD** | 400/月 | 无限 | [about.gitlab.com](https://about.gitlab.com) |
| **Azure DevOps** | 1,800/月 (1并行) | 无限 | [azure.microsoft.com/devops](https://azure.microsoft.com/devops/) |
| **Bitbucket** | 50/月 | 无限 | [bitbucket.org](https://bitbucket.org) |

---

## 1️⃣1️⃣ 中国云服务免费资源

### 阿里云 (Alibaba Cloud)

| 资源 | 免费额度 | 期限 | 要求 |
|------|----------|------|------|
| ECS 云服务器 | 2C2G | **3个月** (新用户) | 实名 |
| OSS 对象存储 | 500GB (个人) / 1TB (企业) | 试用 | 实名 |
| NAS 文件存储 | 50GB | 3个月 | 实名 |
| RDS PostgreSQL | 2C4G 高可用 | 试用 | 实名 |
| 通义千问 AI | **7000万+ token** | 新用户 | 实名 |
| 函数计算 | 300K GB-sec/月 | 永久 | 实名 |
| RocketMQ | 月度免费API + 消息堆积 | 永久 | 实名 |
| 80+ 云产品 | 各类试用 | 不等 | 实名 |

### 腾讯云 (Tencent Cloud)

| 资源 | 免费额度 | 期限 | 要求 |
|------|----------|------|------|
| 轻量云服务器 | 2C2G / 2C4G / 4C8G | **1-3个月** | 手机号 |
| COS 对象存储 | **50GB** + 10GB流量/月 | **6个月** | 手机号 |
| Elasticsearch | 免费试用 | 1个月 | 手机号 |
| 国际版信用 | $90 credit | 新用户 | 手机号 |

### 华为云 (Huawei Cloud)

| 资源 | 免费额度 | 期限 | 要求 |
|------|----------|------|------|
| ECS 弹性云服务器 | 多种配置 | **1年免费** (学生) | 学生认证 |
| RDS MySQL/PG | 免费试用 | 试用 | 实名 |
| OBS 对象存储 | 分层定价试用 | 试用 | 实名 |
| DMS 分布式消息 | 免费试用 | 试用 | 实名 |
| 新用户国际版 | **$100 信用** | 60天 | 注册 |
| DeepSeek AI | 免费全版体验 | 限时 | 实名 |

### 火山引擎 (Volcengine / ByteDance)

| 资源 | 免费额度 | 期限 |
|------|----------|------|
| DeepSeek R1 满血版 | **50万免费 token** | 用完即止 |
| 联网插件 | 20,000 调用/月 | 每月 |
| 深度思考模型 | 免费版本 | 持续 |
| 新用户代金券 | ~¥145 | 限时 |

### 其他国内服务商

| Provider | 免费资源 | 期限 | URL |
|----------|----------|------|-----|
| **七牛云** | 10GB 存储 + 10GB流量/月 | **永久** | [qiniu.com](https://www.qiniu.com) |
| **网易云** | 50GB NOS + 20GB流量 | 新用户 | [163yun.com](https://www.163yun.com/nos/free) |
| **百度云** | 200+ 产品免费试用 | 新用户 | [cloud.baidu.com](https://cloud.baidu.com/campaign/free/index.html) |
| **天翼云** | 4C8G ECS + 云盘 + 对象存储 | 试用 | [ctyun.cn](https://www.ctyun.cn/act/trial/central) |
| **移动云** | 1TB 云盘 | 活动 | [feixin.10086.cn](https://caiyun.feixin.10086.cn) |
| **青云** | RabbitMQ 等服务 | 试用 | [qingcloud.com](https://www.qingcloud.com) |

---

## 1️⃣2️⃣ 大数据 / 分析

| Platform | 免费内容 | 类型 | URL |
|----------|----------|------|-----|
| **DataEase** | 全功能开源 BI | 自托管 | [dataease.cn](https://dataease.cn) |
| **Apache Superset** | 开源数据可视化 | 自托管 | [superset.apache.org](https://superset.apache.org) |
| **DataGear** | 开源数据可视化平台 | 自托管 | [datagear.tech](http://www.datagear.tech) |
| **GCP BigQuery** | **1TB 查询/月** (永久免费) | 托管 | [cloud.google.com/bigquery](https://cloud.google.com/bigquery) |
| **AWS Athena** | 与 S3 免费层配合使用 | 托管 | [aws.amazon.com/athena](https://aws.amazon.com/athena) |

---

## 1️⃣3️⃣ Startup Credits

| Program | 额度 | 期限 | URL |
|---------|------|------|-----|
| **AWS Activate** | **$100K** | 2年 | [aws.amazon.com/activate](https://aws.amazon.com/activate) |
| **Google for Startups** | **$200K** | 2年 | [cloud.google.com/startup](https://cloud.google.com/startup) |
| **Microsoft for Startups** | **$150K** Azure | 持续 | [microsoft.com/startups](https://www.microsoft.com/startups) |
| **Oracle for Startups** | **$300K** | 持续 | [oracle.com/startups](https://www.oracle.com/startups) |
| **GitHub Student Pack** | 80+ 工具, $100 Azure, JetBrains | 学生期 | [education.github.com/pack](https://education.github.com/pack) |

---

## 🎓 GitHub Student Developer Pack

| 福利 | 详情 |
|------|------|
| Microsoft Azure | 25+ 服务 + **$100 信用** |
| JetBrains IDEs | 全套 IDE 免费许可 |
| GitHub Copilot | **200 AI credits/月** |
| Heroku | $13/月 × 24个月 = **$312** |
| 域名 | 免费 .me 域名 |
| Canva Pro | 免费教育版 |
| **总计 80+ 工具** | [education.github.com/pack](https://education.github.com/pack) |

---

## 💳 无需信用卡的服务汇总

以下服务**完全不需要信用卡**即可使用免费层：

| Service | Category | URL |
|---------|----------|-----|
| Cloudflare (全栈) | CDN/Workers/R2/Pages/D1/KV | [cloudflare.com](https://www.cloudflare.com) |
| Vercel | PaaS/Serverless | [vercel.com](https://vercel.com) |
| Netlify | PaaS/Functions | [netlify.com](https://www.netlify.com) |
| Render | PaaS/DB | [render.com](https://render.com) |
| Supabase | PostgreSQL/Auth/Storage | [supabase.com](https://supabase.com) |
| Neon | Serverless PostgreSQL | [neon.tech](https://neon.tech) |
| Turso | Edge SQLite (9GB) | [turso.tech](https://turso.tech) |
| Upstash | Redis | [upstash.com](https://upstash.com) |
| MongoDB Atlas | MongoDB | [mongodb.com/atlas](https://www.mongodb.com/atlas) |
| Backblaze B2 | Object Storage | [backblaze.com/b2](https://www.backblaze.com/b2/) |
| 七牛云 | Object Storage (中国) | [qiniu.com](https://www.qiniu.com) |
| GitHub Actions | CI/CD | [github.com](https://github.com) |
| Google Colab | GPU/TPU | [colab.research.google.com](https://colab.research.google.com) |
| Kaggle | GPU 30hrs/周 | [kaggle.com](https://www.kaggle.com) |
| Impossible Cloud | S3 Storage (EU) | [impossiblecloud.com](https://www.impossiblecloud.com) |

---

## 📌 源文章解读

### CodeWhale (Hmbown/CodeWhale)

CodeWhale 是一个基于 DeepSeek V4 的终端代码助手，使用 Rust 编写。特点包括：

- **三种模式**: Plan (只读), Agent (审批门控), YOLO (自动批准)
- **17个 API 提供商**: DeepSeek, OpenRouter, SiliconFlow, Fireworks, NVIDIA NIM, OpenAI, HuggingFace, 以及小米 MiMo, Arcee AI 等
- **子代理**: 支持最多20个并发子代理
- **LSP 支持**: Rust/Python/TypeScript/Go/C++/Java/Vue
- **MCP 协议**: Model Context Protocol 支持
- **定价**: DeepSeek V4 Pro: $0.435/1M input, $0.87/1M output; Flash: $0.14/1M input, $0.28/1M output

### Gist 免费云资源清单 (imba-tjd)

该 Gist 收集了大量免费资源，包括 40+ 虚拟主机、4个免费 VPS、6个 WordPress 主机、8个临时短信服务、7个临时邮箱服务，以及虚拟电话/地址/信用卡工具。其中部分资源已过时，但作为入口参考仍有价值。

---

## ⚠️ 重要注意事项

1. **免费 ≠ 永久**: 大多数免费层有使用限制或可能随时变更
2. **信用卡验证**: 即使标注免费，部分服务需要信用卡但不扣费
3. **实名认证**: 国内云服务均需实名认证
4. **数据安全**: 免费服务可能降低数据持久性保证
5. **冷启动**: Serverless/Render 等免费层有冷启动延迟
6. **流量限制**: 注意免费层是否包含出站流量

---

## 📁 项目结构

```
cloud-ops/
├── README.md              # 本文件 - 完整资源清单
├── docs/
│   ├── VERIFICATION.md     # 验证结果记录
│   └── RESEARCH_NOTES.md   # 调研笔记
├── scripts/
│   ├── verify-services.sh  # 自动验证脚本
│   └── monitor-quotas.py  # 配额监控
└── verification/
    └── results/            # 验证结果 JSON
```

---

## 🔄 更新日志

| 日期 | 更新内容 |
|------|----------|
| 2026-06-07 | 初始版本: 150+ 免费资源, 13个分类, 3个源URL分析 |
