# 🗃️ 免费数据库资源

> 最后更新: 2026-06-07

## 🐘 关系型数据库（PostgreSQL）

### 1. Neon（🏆 首选 — Serverless Postgres）

| 项目 | 免费额度 |
|------|----------|
| 项目数 | 100个 |
| 计算时间 | 100 CU-hours/项目/月 |
| 存储 | 0.5 GB |
| 分支 | 无限制 |
| 逻辑复制 | 支持 |

**注册**: https://neon.tech
**亮点**: Serverless 架构，自动挂起（不用不收费），支持 Prisma/Drizzle
**适用**: Next.js/Supabase/Railway 项目

---

### 2. Supabase（🏆 推荐 — Postgres + 生态全包）

| 项目 | 免费额度 |
|------|----------|
| PostgreSQL | 500MB |
| Auth | 5万MAU |
| Storage | 1GB |
| Edge Functions | 50万次/月 |
| Realtime | 200并发连接 |
| Vector | 500MB |

**注册**: https://supabase.com
**亮点**: Postgres + Auth + Storage + Realtime + Edge Functions 全家桶
**替代 PlanetScale 的最佳选择**

---

### 3. Aiven（PostgreSQL + MySQL）

| 项目 | 免费额度 |
|------|----------|
| PostgreSQL | 1个实例 |
| MySQL | 1个实例 |
| Kafka | 免费 |
| OpenSearch | 免费 |
| Redis | 免费 |

**注册**: https://aiven.io
**亮点**: 多种数据库统一管理，永久免费层，无需信用卡

---

### 4. Vercel Postgres

| 项目 | 免费额度 |
|------|----------|
| 存储 | 256MB |
| 计算时间 | 60小时/月 |

**限制**: 仅限 Vercel 部署的项目

---

### 5. Render Postgres

| 项目 | 免费额度 |
|------|----------|
| PostgreSQL | 90天试用 |

**注意**: 免费数据库会在90天后删除

---

### 6. Crunchy Bridge

| 项目 | 免费额度 |
|------|----------|
| PostgreSQL | 试用credits |

---

## 🍃 NoSQL / 键值数据库

### 1. Redis

| 服务 | 免费额度 | 说明 |
|------|----------|------|
| **Upstash** | 10K命令/天 + 256MB | Serverless Redis，按请求计费 |
| **Redis Cloud** | 30MB | 官方托管 |
| **StackExchange.Redis** | 免费开发者层 | 基础 |

**Upstash 注册**: https://upstash.com
**亮点**: Serverless Redis + REST API，适合 Serverless 架构

---

### 2. MongoDB

| 服务 | 免费额度 |
|------|----------|
| MongoDB Atlas | 512MB M0 集群 |

**注册**: https://www.mongodb.com/atlas
**亮点**: 免费集群，支持 Mongoose/Prisma

---

### 3. Firebase

| 服务 | 免费额度 |
|------|----------|
| Firestore | 1GB存储 + 5万读/2万写/天 |
| Realtime DB | 1GB + 10G下行/月 |
| Auth | 免费邮箱/密码认证 |
| Storage | 5GB |
| Hosting | 10GB |

**亮点**: Google 生态，前端全栈方案

---

### 4. Supabase（见上文，已含 NoSQL 能力）

---

## 🔍 向量数据库

### 1. Zilliz Cloud（🏆 Milvus 托管版）

| 项目 | 免费额度 |
|------|----------|
| 存储 | 1GB |
| 向量数 | ~100万（768维） |
| 请求 | 限速免费 |

**注册**: https://zilliz.com.cn
**亮点**: Milvus 官方云服务，国产，RAG必备

---

### 2. Pinecone

| 项目 | 免费额度 |
|------|----------|
| 向量数 | 10万 |
| 命名空间 | 1个 |
| 存储 | 有限 |

**注册**: https://www.pinecone.io

---

### 3. Weaviate Cloud

| 项目 | 免费额度 |
|------|----------|
| 存储 | 1GB |
| 向量数 | 有限 |

**注册**: https://weaviate.io

---

### 4. Qdrant Cloud

| 项目 | 免费额度 |
|------|----------|
| 存储 | 1GB |
| 集群 | 1个 |

**注册**: https://cloud.qdrant.io

---

### 5. Chroma（自建，完全免费）

| 项目 | 说明 |
|------|------|
| 部署 | Docker 一键启动 |
| 存储 | 无限（取决于磁盘） |
| 限制 | 需自己维护 |

```bash
docker run -d -p 8000:8000 chromadb/chroma
```

---

## 📊 数据库对比矩阵

| 服务 | 类型 | 免费额度 | 永久免费 | Serverless | 推荐度 |
|------|------|----------|----------|------------|--------|
| **Neon** | Postgres | 0.5GB + 100CU-hr | ✅ | ✅ | ⭐⭐⭐⭐⭐ |
| **Supabase** | Postgres+ | 500MB + Auth | ✅ | ✅ | ⭐⭐⭐⭐⭐ |
| **Aiven** | 多类型 | PG+MySQL+Kafka | ✅ | ❌ | ⭐⭐⭐⭐ |
| **Upstash** | Redis | 256MB + 10K/天 | ✅ | ✅ | ⭐⭐⭐⭐ |
| **MongoDB Atlas** | MongoDB | 512MB | ✅ | ❌ | ⭐⭐⭐⭐ |
| **Zilliz Cloud** | 向量 | 1GB | ✅ | ❌ | ⭐⭐⭐⭐ |
| **Pinecone** | 向量 | 10万向量 | ✅ | ✅ | ⭐⭐⭐ |
| **Chroma** | 向量 | 无限 | ✅ | ❌ | ⭐⭐⭐⭐⭐ |
| **Firebase** | Firestore | 1GB | ✅ | ✅ | ⭐⭐⭐⭐ |
| **Render** | Postgres | 90天试用 | ❌ | ❌ | ⭐⭐ |

## 💡 最佳实践

### Serverless 应用数据库选型
```
前端/全栈项目 → Neon（Postgres）或 Supabase（全家桶）
AI/RAG项目 → Zilliz Cloud（向量）+ Neon（元数据）
缓存层 → Upstash Redis
实时同步 → Supabase Realtime 或 Firebase
```

### 零成本全栈方案
```
Cloudflare Pages (前端)
+ D1/KV (存储)
+ Workers (后端)
= 完全免费的全栈应用
```

### 生产级零成本方案
```
Oracle ARM VM (免费VM)
+ Docker Compose
  - PostgreSQL (自建)
  - Redis (自建)
  - Chroma (向量数据库)
  - MinIO (对象存储)
= 完全自控的基础设施
```
