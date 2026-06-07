# ☁️ 免费云计算资源（IaaS / PaaS / Serverless）

> 最后更新: 2026-06-07

## 🥇 Tier 1: 永久免费 — 无限时不限量

### 1. Oracle Cloud Always Free（🏆 首选推荐）

| 资源 | 规格 | 说明 |
|------|------|------|
| AMD VM | 2台 × 1/8 OCPU + 1GB RAM | 适合轻量服务 |
| ARM Ampere A1 | **4 OCPU + 24GB RAM**（可分1-4台VM） | **永久免费，最强免费VM** |
| Block Storage | 200GB 总量 | 每台VM最多4块 |
| Object Storage | 20GB | S3兼容 |
| Load Balancer | 1个 | 10Mbps |
| Outbound Data | 10TB/月 | 超额停机不扣费 |

**注册方式**: https://www.oracle.com/cloud/free/
**注意事项**:
- 需要信用卡/ PayPal 验证（不会扣费）
- ARM 实例可能缺货，需要多尝试不同区域（推荐: Frankfurt、Ashburn、Tokyo）
- 用超了只会停机，不会产生费用
- ARM 搭配 Ubuntu 22.04 + Docker 可跑几乎所有服务

**推荐用法**:
- 4 OCPU 24GB RAM 的 ARM VM ≈ 一个小型开发服务器的全部算力
- 可运行: Docker + PostgreSQL + Redis + Nginx + 应用服务
- 搭配 200GB 存储，适合做个人项目、API服务、小型网站

**参考**: [OCI Free Tier 官方文档](https://docs.oracle.com/iaas/Content/FreeTier/freetier_topic-Always_Free_Resources.htm)

---

### 2. Google Cloud Platform Always Free

| 资源 | 规格 | 说明 |
|------|------|------|
| e2-micro VM | 1台（非抢占式） | 北美/南美/欧洲区域 |
| Cloud Storage | 5GB | US多区域 |
| Cloud Run | 18万vCPU秒/月 + 36万GiB秒/月 | Serverless 容器 |
| Cloud Functions | 200万次调用/月 | 无服务器函数 |
| Firestore | 1GB存储 + 5万读/2万写/天 | NoSQL数据库 |
| BigQuery | 10GB存储 + 1TB查询/月 | 数据分析 |
| Cloud Load Balancing | 1个 | HTTP(S)负载均衡 |
| Cloud VPN | 1个 | IPsec VPN |

**注册方式**: https://cloud.google.com/free
**额外福利**: 新用户 $300 试用额度（90天）

**推荐用法**:
- e2-micro 跑轻量 API 服务
- Cloud Run 部署容器（按调用计费，免费额度内零成本）
- BigQuery 做数据分析
- Firestore 做 Serverless 应用后端

---

### 3. IBM Cloud Lite（永久免费，无需信用卡）

| 资源 | 规格 | 说明 |
|------|------|------|
| Cloud Object Storage | 25GB + 5GB出站 | S3兼容 |
| Cloud Functions | 500万GB-秒/月 | Serverless |
| Cloudant (NoSQL) | 1GB | CouchDB兼容 |
| Db2 | 200MB | 关系型数据库 |
| Kubernetes | 免费集群 | 有限资源 |

**注册方式**: https://cloud.ibm.com

---

## 🥈 Tier 2: 长期免费（有月度限额但持续可用）

### 4. Cloudflare 全家桶（🏆 最佳综合性价比）

| 服务 | 免费额度 | 说明 |
|------|----------|------|
| Workers | 10万次/天 | Serverless 边缘计算 |
| Pages | 500次构建/月 + 无限带宽 | 静态站点托管 |
| R2 对象存储 | 10GB + 零出口费 | S3兼容 |
| D1 数据库 | 5GB SQLite | 边缘数据库 |
| KV 存储 | 100k读/天 + 1k写/天 | Key-Value |
| CDN + DNS | 无限 | 全球加速 |
| SSL 证书 | 无限 | 自动续签 |
| DDoS 防护 | 无限 | 基础防护 |

**注册方式**: https://dash.cloudflare.com/sign-up
**亮点**: 零出口费是 R2 最大的杀手锏，比 AWS S3 省巨额流量费

---

### 5. Azure 永久免费服务

| 资源 | 免费额度 |
|------|----------|
| App Service | 10个Web/Mobile/API应用 |
| Container Apps | 18万vCPU秒/月 |
| Functions | 100万次/月 |
| Azure DevOps | 5用户 CI/CD |
| Cosmos DB | 400RU/s + 5GB |
| Blob Storage | 5GB LRS热存储 |

**学生福利**: 验证后无需信用卡，$100额度/年，可续订

---

## 🥉 Tier 3: 有期限免费（试用/首年）

### 6. AWS Free Tier（12个月）

| 资源 | 免费额度 | 说明 |
|------|----------|------|
| EC2 | 750小时/月 t2.micro | 12个月 |
| S3 | 5GB + 2000PUT + 20000GET | 12个月后按量付费 |
| Lambda | 100万次/月 | 永久（注意只限1年free tier账户） |
| RDS | 750小时/月 db.t2.micro | 12个月 |

**注意**: AWS 没有费用封顶机制，用超了会扣费！必须设置账单告警。

---

### 7. 腾讯云（国内最便宜）

| 资源 | 免费额度 |
|------|----------|
| 对象存储 COS | 新用户 50GB/半年 |
| 轻量应用服务器 | 新用户限时体验 |
| 学生认证 | 4万额度/半年 |

**超值**: 4核4G 轻量服务器 ¥38/年（老用户续费价）

---

### 8. 阿里云

| 资源 | 免费额度 |
|------|----------|
| 百炼 AI Key | 3个月，每个模型100万Token |
| 学生认证 | ¥300 额度 |

---

## 🔥 Serverless / PaaS 平台

| 平台 | 免费额度 | 商用 | 亮点 |
|------|----------|------|------|
| Vercel | 100GB带宽 + 6000构建分/月 | ❌ 禁止商用 | Next.js 最佳搭档 |
| Netlify | 300构建分/月 + 100GB | ✅ 允许商用 | 支持SSG/SSR |
| Railway | $1/月使用额度 | ✅ | 全栈部署，数据库支持 |
| Deno Deploy | 10万次/月 | ✅ | Deno 原生 |
| Render | 750小时/月 | ✅（免费层有限） | Web Service + DB |
| Fly.io | 3台shared-cpu-1x VM | ❌ | 全球边缘部署 |

---

## 📊 IaaS 免费层对比矩阵

| 指标 | Oracle | GCP | AWS | Azure | IBM |
|------|--------|-----|-----|-------|-----|
| 永久免费VM | ✅ 4核24GB | ✅ e2-micro | ❌ 仅12月 | ✅ App Service | ✅ 有限 |
| 永久免费存储 | ✅ 200GB | ✅ 5GB | ❌ | ✅ 5GB | ✅ 25GB |
| 永久免费Serverless | ❌ | ✅ Cloud Run | ✅ Lambda | ✅ Functions | ✅ |
| 免费容器 | ❌ | ✅ Cloud Run | ✅ Fargate(12月) | ✅ Container Apps | ❌ |
| 免费数据库 | ✅ 2个 | ✅ Firestore | ✅ RDS(12月) | ✅ Cosmos DB | ✅ |
| 信用额度 | $300(30天) | $300(90天) | — | $100(学生) | — |
| 需要信用卡 | ✅ | ✅ | ✅ | 学生免 | ❌ |

## 💡 最佳实践

### Oracle ARM VM 部署方案
```bash
# 推荐配置：Ubuntu 22.04 + Docker
ssh ubuntu@<oracle-ip>

# 安装 Docker
curl -fsSL https://get.docker.com | sh
sudo usermod -aG docker ubuntu

# 运行完整技术栈
docker compose up -d
# PostgreSQL + Redis + Nginx + Node.js/Python App
```

### GCP e2-micro 微服务方案
```bash
# 使用 Cloud Run 部署（免费额度内）
gcloud run deploy my-service \
  --source . \
  --region us-central1 \
  --allow-unauthenticated \
  --memory 512Mi \
  --cpu 1
```

## ⚠️ 风险提示

1. **Oracle**: ARM 实例可能因资源紧张被回收，建议定期备份
2. **AWS**: 超额无预警会扣费，务必设置 Billing Alert
3. **GCP**: e2-micro 仅限美洲和欧洲区域
4. **Azure**: 免费层服务可能被微软取消（历史上有过先例）
5. **所有平台**: 免费政策随时可能变化，建议不要依赖单一平台
