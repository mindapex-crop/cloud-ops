# ✅ 免费云服务验证报告

> **验证时间**: 2026-06-08
> **验证人**: z-ai agent (page_reader)
> **验证方法**: 通过 `z-ai function page_reader` 抓取各服务定价页面，提取当前免费层信息

---

## 📊 免费云服务验证总表（"无需信用卡"优先级服务）

| # | 服务 | 页面可访问 | 免费层活跃 | 当前免费额度 | 与文档差异 |
|---|------|-----------|-----------|-------------|-----------|
| 1 | **Cloudflare R2** | ✅ | ✅ 活跃 | 10GB存储 + 零出口费 + 1M A类/10M B类操作/月 | ✅ 一致 |
| 2 | **Supabase** | ✅ | ✅ 活跃 | 500MB DB + 5万MAU + 1GB Storage + 5GB egress + 无限API请求 | ⚠️ 有变更 |
| 3 | **Turso** | ✅ | ✅ 活跃 | 100 DBs + 5GB存储 + 5亿行读/月 + 1000万行写/月 + 3GB sync | 🆕 新增 |
| 4 | **Upstash Redis** | ✅ | ✅ 活跃 | 256MB + **500K命令/月**（非10K/天） | ⚠️ 有变更 |
| 5 | **Neon** | ✅ | ✅ 活跃 | 100项目 + 100 CU-hr/月/项目 + 0.5GB/项目 + Auth 60K MAU + 6hr time travel | ⚠️ 有变更 |
| 6 | **Render** | ✅ | ✅ 活跃 | Free $0 Web Services (512MB/0.1CPU) + Postgres **30天限制** + KV 25MB | ⚠️ 有变更 |
| 7 | **Backblaze B2** | ✅ | ✅ 活跃 | 前10GB存储免费 + **3倍存储量免费出口**（通过CDN合作伙伴无限免费） | ⚠️ 有变更 |
| 8 | **Impossible Cloud** | ✅ | ⚠️ 试用 | **免费试用** + $7.99/TB/月 + 零出口费 + 免费API调用 | 🆕 新增 |
| 9 | **Cloudflare Workers** | ✅ | ✅ 活跃 | 10万请求/天 + 10ms CPU/次 + KV 100K读/天 + D1 5GB+5M行读/天 | ⚠️ 有变更 |
| 10 | **MongoDB Atlas** | ✅ | ✅ 活跃 | **M0 永久免费** 512MB + 共享RAM/vCPU + 100 ops/sec | ✅ 一致 |

---

## 🔍 各服务详细验证结果

### 1. Cloudflare R2 ✅ — 无变更

| 项目 | 文档记录 | 当前实际 | 状态 |
|------|---------|---------|------|
| 存储 | 10GB/月 | 10GB/月 | ✅ 一致 |
| A类操作（写/删） | 100万次/月 | 100万次/月 | ✅ 一致 |
| B类操作（读） | 1000万次/月 | 1000万次/月 | ✅ 一致 |
| 出口流量 | $0（零费用） | $0（零费用） | ✅ 一致 |

**结论**: R2 免费层保持不变，零出口费仍是最大亮点。

---

### 2. Supabase ⚠️ — 有变更

| 项目 | 文档记录 | 当前实际 | 状态 |
|------|---------|---------|------|
| PostgreSQL | 500MB | 500MB | ✅ 一致 |
| Auth MAU | 5万 | 5万 | ✅ 一致 |
| Storage | 1GB | 1GB | ✅ 一致 |
| Edge Functions | 50万次/月 | **"Unlimited API requests"** | ⚠️ 升级 |
| Realtime | 200并发 | 未在定价页明确提及 | ❓ |
| Vector | 500MB | 未在定价页明确提及 | ❓ |
| Egress | 未记录 | 5GB + 5GB cached egress | 🆕 |
| 项目限制 | 未记录 | **最多2个活跃项目** | 🆕 |
| 不活跃暂停 | 未记录 | **1周不活跃后暂停** | 🆕 |

**结论**: Supabase 免费层基本保持，但增加了一些限制（2项目上限、1周不活跃暂停），同时 API 请求变为无限。Realtime/Vector 免费额度在定价页未明确显示，可能已调整。

---

### 3. Turso 🆕 — 新增（文档未覆盖）

| 项目 | 当前实际 |
|------|---------|
| 数据库数 | **100个** |
| 存储 | **5GB** |
| 行读取 | **5亿/月** |
| 行写入 | **1000万/月** |
| Sync流量 | **3GB/月** |
| Point-in-Time Restore | 1天 |
| 审计日志 | 3天保留 |
| 信用卡 | **不需要** |
| 类型 | SQLite (embedded replicas) |

**结论**: Turso 提供**极其慷慨**的免费层（5亿行读/月），特别适合嵌入式 SQLite 场景。文档中未覆盖，建议新增。

---

### 4. Upstash Redis ⚠️ — 有变更

| 项目 | 文档记录 | 当前实际 | 状态 |
|------|---------|---------|------|
| 数据大小 | 256MB | 256MB | ✅ 一致 |
| 命令数 | **10K命令/天** | **500K命令/月**（≈16.6K/天） | ⚠️ 变更大 |
| 额外计费 | 未记录 | $0.20/100K命令 + $0.25/GB存储（首个1GB免费） | 🆕 |
| Fixed 计划 | 未记录 | Fixed 250MB $10/月起 | 🆕 |
| Prod Pack | 未记录 | +$200/月/数据库 (HA/SOC2等) | 🆕 |
| 最大QPS | 未记录 | 10,000 | 🆕 |
| 信用卡 | 不需要 | 不需要（免费层） | ✅ 一致 |

**结论**: 免费层命令数从 "10K/天" 改为 "500K/月"（总量略有增加，但不均衡）。付费层计费方式变更为 $0.20/100K命令。存储首个1GB免费。

---

### 5. Neon ⚠️ — 有变更

| 项目 | 文档记录 | 当前实际 | 状态 |
|------|---------|---------|------|
| 项目数 | 100个 | **100个** | ✅ 一致 |
| 计算时间 | 100 CU-hr/项目/月 | **100 CU-hr/项目/月** | ✅ 一致 |
| 存储 | 0.5 GB | **0.5 GB** | ✅ 一致 |
| 分支 | 无限制 | **10分支/项目**（免费层） | ⚠️ 变更 |
| 逻辑复制 | 支持 | 免费层有 | ✅ |
| Auth | 未记录 | **60K MAU**（Neon Auth） | 🆕 |
| Time Travel | 未记录 | **6小时** | 🆕 |
| Compute Size | 未记录 | **最大 2 CU (8GB RAM)** | 🆕 |
| Egress | 未记录 | **5GB included** | 🆕 |
| 信用卡 | 不需要 | **不需要** | ✅ 一致 |
| Paid plan egress | 未记录 | **500 GB/月（Launch plan）** | 🆕 |

**结论**: Neon 免费层核心指标不变，但新增了 Neon Auth (60K MAU) 和更多细节。分支从 "无限制" 变为 "10个/项目"。Launch plan 提供了大幅增加的 egress (500GB)。

---

### 6. Render ⚠️ — 有变更

| 项目 | 文档记录 | 当前实际 | 状态 |
|------|---------|---------|------|
| Web Service (Free) | 750小时/月 | **$0/月, 512MB RAM, 0.1 CPU** | ⚠️ 模式变更 |
| Postgres Free | 90天试用 | **Free, 256MB, 0.1CPU, 100连接, 30天限制** | ⚠️ 更详细 |
| Key-Value (Redis) | 未记录 | **Free, 25MB, 50连接** | 🆕 |
| Static Sites | 未记录 | **$0/月, CDN, 自定义域名** | 🆕 |
| Workspace Hobby | 未记录 | **$0/月 + compute, 最多25服务, 5GB带宽** | 🆕 |
| 信用卡 | 不需要 | **不需要**（Hobby plan） | ✅ 一致 |

**结论**: Render 从 "750小时/月" 模式改为纯粹的 Free tier 模式。Web Service 有 512MB/0.1CPU 免费额度（持续运行），Postgres 限制为30天（非90天），新增 Key-Value 免费层。带宽限制5GB/月。

---

### 7. Backblaze B2 ⚠️ — 有变更

| 项目 | 文档记录 | 当前实际 | 状态 |
|------|---------|---------|------|
| 存储 | 10GB | **前10GB始终免费** | ✅ 一致 |
| 出口流量 | 10GB/天(绑定CF免费) | **3倍月均存储量免费出口**（超限$0.01/GB） | ⚠️ 变更 |
| 下载费用 | $0.01/GB | **通过CDN合作伙伴无限免费出口** | ⚠️ 更优惠 |
| API调用 | 未记录 | **Class A/B/C 免费付费用户；Class D $0.004/万次** | 🆕 |
| B2 Reserve | 未记录 | **$26/TB/月, 最低25TB/年, 含免费出口** | 🆕 |
| B2 Overdrive | 未记录 | **$15/TB/月, 无限免费出口, AI/HPC专用** | 🆕 |

**结论**: Backblaze 大幅改进了免费出口策略，现在提供 3 倍存储量的免费出口（之前仅10GB/天绑定CF免费），CDN合作伙伴可获无限免费出口。API 调用现在大部分免费。

---

### 8. Impossible Cloud 🆕 — 新增（文档未覆盖）

| 项目 | 当前实际 |
|------|---------|
| 类型 | S3 兼容对象存储 |
| Pay-as-you-go | **$7.99/TB/月**（约 €7.99） |
| 免费试用 | **免费试用**（需联系获取） |
| 出口流量 | **$0** |
| API 调用 | **$0** |
| 最小文件大小 | 无费用 |
| 最低保留期 | 无费用 |
| Reserved | 最低25TB, 1-3年承诺 |
| 区域 | US, EU (DE, NL) |
| 合规 | GDPR |
| 迁移 | 辅助数据迁移 |

**结论**: Impossible Cloud 是 S3 兼容的欧洲云存储，零出口费策略类似 Cloudflare R2，但价格略高（$7.99/TB vs R2 免费10GB）。无免费永久层，仅有免费试用。适合欧洲合规需求。

---

### 9. Cloudflare Workers ⚠️ — 有变更

| 项目 | 文档记录 | 当前实际 | 状态 |
|------|---------|---------|------|
| Workers 请求 | 10万次/天 | **10万次/天** | ✅ 一致 |
| CPU 时间 | 未记录 | **10ms/请求** | 🆕 |
| Pages 构建 | 500次/月 | 500次/月 (Pages plan) | ✅ |
| KV 读取 | 100K读/天 | **100K读/天** | ✅ 一致 |
| KV 写入 | 1K写/天 | **1K写/天** | ✅ 一致 |
| KV 存储 | 未记录 | **1GB** | 🆕 |
| D1 存储 | 5GB SQLite | **5GB (总计)** | ✅ 一致 |
| D1 行读 | 未记录 | **500万行/天** | 🆕 |
| D1 行写 | 未记录 | **10万行/天** | 🆕 |
| Queues | 未记录 | **1万操作/天** | 🆕 |
| Hyperdrive | 未记录 | **10万DB查询/天** | 🆕 |
| Workers Logs | 未记录 | **20万事件/天, 3天保留** | 🆕 |
| Paid plan | $5/月 | **$5/月, 1000万请求 + 30M CPU ms** | 🆕 |
| 信用卡 | 不需要 | **不需要（免费层）** | ✅ 一致 |

**结论**: Workers 核心免费额度不变（10万请求/天），但文档缺失大量子产品细节（KV/D1/Queues/Hyperdrive 的免费额度），现已补充。Paid plan 仍为 $5/月，包含更多资源。

---

### 10. MongoDB Atlas ✅ — 无变更

| 项目 | 文档记录 | 当前实际 | 状态 |
|------|---------|---------|------|
| 存储 | 512MB M0 集群 | **512MB M0, Free forever** | ✅ 一致 |
| RAM | 共享 | 共享 | ✅ 一致 |
| vCPU | 共享 | 共享 | ✅ 一致 |
| Ops/sec | 未记录 | **100 ops/sec** | 🆕 |
| Sort memory | 未记录 | **32MB** | 🆕 |
| Flex plan | 未记录 | **$0.011/hr起 (~$8/月)** | 🆕 |
| M2 | 未记录 | **2GB, $9/月** | 🆕 |

**结论**: MongoDB Atlas M0 免费层完全不变，仍为 512MB 永久免费。新增 Flex plan ($8/月起) 和 M2 ($9/月, 2GB) 作为入门付费选项。

---

## 📈 变更汇总

### 与文档一致（无需更新）✅
- **Cloudflare R2**: 完全一致
- **MongoDB Atlas**: 完全一致

### 有变更需更新文档 ⚠️
- **Supabase**: 新增限制（2项目上限、不活跃暂停），API 请求变为无限
- **Upstash**: 命令数从 10K/天 改为 500K/月，新增详细计费
- **Neon**: 分支限制（10个），新增 Auth/Time Travel 等功能
- **Render**: 计费模式变更（从小时改为固定 Free tier），Postgres 改为30天
- **Backblaze B2**: 出口费策略大幅改善（3倍存储免费出口）
- **Cloudflare Workers**: 文档需补充 KV/D1/Queues/Hyperdrive 免费额度细节

### 文档未覆盖需新增 🆕
- **Turso**: SQLite 数据库，100 DBs + 5GB + 5亿行读/月，极其慷慨
- **Impossible Cloud**: 欧洲对象存储，$7.99/TB，零出口费（仅试用无永久免费）

---

## 🏆 推荐更新优先级

| 优先级 | 服务 | 行动 |
|--------|------|------|
| 🔴 高 | Supabase | 更新限制（2项目、不活跃暂停），确认 Realtime/Vector 状态 |
| 🔴 高 | Upstash | 更新命令计数（500K/月），新增计费细节 |
| 🟡 中 | Backblaze B2 | 更新出口费策略（3倍存储免费出口） |
| 🟡 中 | Render | 更新计费模式，Postgres 改为30天 |
| 🟡 中 | Neon | 补充分支限制(10个)，新增 Auth/Time Travel |
| 🟡 中 | Cloudflare Workers | 补充 KV/D1/Queues/Hyperdrive 细节 |
| 🟢 低 | Turso | 新增服务条目（免费层非常慷慨） |
| 🟢 低 | Impossible Cloud | 新增服务条目（仅试用，非永久免费） |
| ⬜ 无 | Cloudflare R2 | 无需更新 |
| ⬜ 无 | MongoDB Atlas | 无需更新 |

---

## 📋 原始数据文件

所有验证原始 JSON 文件保存在 `/home/z/my-project/download/` 目录:

| 文件 | 服务 | 大小 |
|------|------|------|
| `verify-cloudflare-r2.json` | Cloudflare R2 | 156KB |
| `verify-supabase.json` | Supabase | 396KB |
| `verify-turso.json` | Turso | 148KB |
| `verify-upstash.json` | Upstash | 235KB |
| `verify-neon.json` | Neon | 694KB |
| `verify-render.json` | Render | 775KB |
| `verify-backblaze.json` | Backblaze B2 | 382KB |
| `verify-impossiblecloud.json` | Impossible Cloud | 287KB |
| `verify-cloudflare-workers.json` | Cloudflare Workers | 474KB |
| `verify-mongodb-atlas.json` | MongoDB Atlas | 1.5MB |
