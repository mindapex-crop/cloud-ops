# 🗄️ 免费存储资源（对象存储 / 文件存储 / CDN）

> 最后更新: 2026-06-07

## 🏆 对象存储（S3 Compatible）

### 1. Cloudflare R2（🏆 首选推荐）

| 项目 | 免费额度 | 说明 |
|------|----------|------|
| 存储 | 10GB/月 | — |
| A类操作（写/删） | 100万次/月 | — |
| B类操作（读） | 1000万次/月 | — |
| **出口流量** | **$0.00（零费用）** | **最大亮点** |
| 入口流量 | 免费 | — |

**S3兼容**: ✅ 完全兼容 AWS S3 API
**注册**: https://dash.cloudflare.com → R2

**杀手锏**: 零出口费。对比 AWS S3 出口 $0.09/GB，如果每月流出 1TB 数据：
- AWS S3: $90 出口费
- Cloudflare R2: $0

**适用场景**: 静态资源托管、图片/视频存储、备份、CDN 源站

---

### 2. Backblaze B2

| 项目 | 免费额度 | 说明 |
|------|----------|------|
| 存储 | 10GB | — |
| 出口流量 | 10GB/天（通过Cloudflare免费） | 需绑定Cloudflare |
| 下载费用 | $0.01/GB | 低于10GB免费 |
| API | S3兼容 | — |

**注册**: https://www.backblaze.com/cloud-storage
**技巧**: 绑定 Cloudflare 做中转，出口完全免费

---

### 3. IBM Cloud Object Storage

| 项目 | 免费额度 |
|------|----------|
| 存储 | 25GB |
| 出站流量 | 5GB/月 |

**亮点**: IBM Cloud Lite 不需要信用卡，永久免费

---

### 4. Oracle Cloud Object Storage

| 项目 | 免费额度 |
|------|----------|
| 存储 | 20GB |
| API | S3兼容 |

---

### 5. 腾讯云 COS

| 项目 | 免费额度 |
|------|----------|
| 存储 | 50GB（新用户，半年） |
| 流量 | 部分免费 |

---

### 6. Bitiful 对象存储（国产）

| 项目 | 免费额度 |
|------|----------|
| 存储 | 50GB |
| 流量 | 30GB/月 |

**注册**: https://www.bitiful.com

---

## 📊 对象存储对比矩阵

| 平台 | 免费存储 | 出口费用 | S3兼容 | 需信用卡 | 推荐 |
|------|----------|----------|--------|----------|------|
| **Cloudflare R2** | 10GB | **$0** | ✅ | ❌ | ⭐⭐⭐⭐⭐ |
| **Backblaze B2** | 10GB | $0（绑定CF） | ✅ | ❌ | ⭐⭐⭐⭐ |
| **IBM COS** | 25GB | 5GB/月免费 | ✅ | ❌ | ⭐⭐⭐⭐ |
| **Oracle COS** | 20GB | 含在10TB/月 | ✅ | ✅ | ⭐⭐⭐ |
| **AWS S3** | 5GB（12月） | $0.09/GB | ✅ | ✅ | ⭐⭐ |
| **腾讯云 COS** | 50GB/半年 | 部分免费 | ✅ | ❌ | ⭐⭐⭐ |

## 🌐 CDN

### Cloudflare（业界标杆 — 免费）

| 功能 | 免费版 | 说明 |
|------|--------|------|
| CDN | 全球节点 | 无限带宽 |
| SSL/TLS | 自动 | Universal/Full/Flexible |
| DDoS防护 | 无限 | Layer 3/4/7 |
| DNS | 免费 | 全球 Anycast |
| Page Rules | 3条 | 基础路由规则 |
| WAF | 基础规则集 | 有限 |
| Bot管理 | 基础 | — |
| Workers | 10万次/天 | 边缘计算 |

**替代方案**:
- **ClouDNS**: 免费DNS托管，4个Anycast服务器
- **DuckDNS**: 免费动态DNS（适合家庭宽带）

## 🔗 对象存储最佳实践

### 方案 A: Cloudflare R2 + Workers（全免费架构）
```javascript
// Cloudflare Worker 做图片处理 + R2 存储
export default {
  async fetch(request, env) {
    const url = new URL(request.url);
    const key = url.pathname.slice(1);

    if (request.method === 'PUT') {
      await env.MY_BUCKET.put(key, request.body);
      return new Response('OK', { status: 200 });
    }

    const object = await env.MY_BUCKET.get(key);
    if (!object) return new Response('Not Found', { status: 404 });

    return new Response(object.body, {
      headers: { 'Content-Type': object.httpMetadata.contentType }
    });
  }
}
```

### 方案 B: Backblaze B2 + Cloudflare CDN
```
B2 Bucket → Cloudflare CNAME → 全球CDN加速 → 零成本
```

### 方案 C: Oracle + R2 混合
```
热数据 → Cloudflare R2（零出口费，全球加速）
冷数据 → Oracle Object Storage（20GB永久免费）
```

## 🗂️ 自建存储方案（完全免费，无限量）

| 方案 | 说明 | 适用场景 |
|------|------|----------|
| MinIO | S3兼容，自建对象存储 | 有闲置服务器时 |
| Nextcloud | 自建网盘 | 个人/小团队文件共享 |
| FileBrowser | 轻量Web文件管理器 | 快速搭建文件服务器 |
| Rclone | 统一多云存储管理 | 跨云备份/迁移 |

**MinIO on Oracle ARM**:
```bash
# Oracle ARM 4核24GB 跑 MinIO
docker run -d \
  -p 9000:9000 -p 9001:9001 \
  -v /data/minio:/data \
  minio/minio server /data --console-address ":9001"
```
