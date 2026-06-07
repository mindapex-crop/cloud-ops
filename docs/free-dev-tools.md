# 🛠️ 免费开发工具（IDE / CI-CD / 域名 / DNS）

> 最后更新: 2026-06-07

## 💻 云端 IDE / 开发环境

| 平台 | 免费额度 | 说明 |
|------|----------|------|
| **GitHub Codespaces** | 60小时/月 | VS Code 云端版 |
| **Gitpod** | 50小时/月 | VS Code 云端版 |
| **Cloud Studio** | 免费 | 腾讯，服务器在上海 |
| **InsCode** | 1核2G | CSDN |
| **Goorm IDE** | 5个工作区 | 可SSH |
| **Replit** | 有限免费 | 2024年后收费 |
| **StackBlitz** | 免费 | 浏览器内Node.js |
| **CodeSandbox** | 有限免费 | 浏览器内开发 |

### 推荐: GitHub Codespaces + Dev Container
```json
// .devcontainer/devcontainer.json
{
  "image": "mcr.microsoft.com/devcontainers/typescript-node:22",
  "postCreateCommand": "npm install",
  "features": {
    "ghcr.io/devcontainers/features/docker-in-docker:2": {}
  }
}
```

---

## 📦 CI/CD

| 服务 | 免费额度 | 亮点 |
|------|----------|------|
| **GitHub Actions** | 2000分钟/月（公开无限） | 与GitHub深度集成 |
| **GitLab CI** | 400分钟/月 | 自托管可无限 |
| **CircleCI** | 6000分钟/月 | Docker支持好 |
| **Cloudflare Pages** | 500构建/月 | 边缘部署 |

---

## 🌐 域名

| 服务 | 免费额度 | 说明 |
|------|----------|------|
| **Freenom** | .tk/.ml/.ga/.cf/.gq | 域名注册（不确定当前是否开放） |
| **GitHub Pages** | username.github.io | 免费 |
| **.is-a.dev** | yourname.is-a.dev | 开发者域名 |
| **.me** | GitHub Student Pack | 1年免费 |
| **eu.org** | yourname.eu.org | 永久免费 |
| ** DuckDNS** | yourname.duckdns.org | 动态DNS |

---

## 🔤 DNS

| 服务 | 免费额度 | 说明 |
|------|----------|------|
| **Cloudflare DNS** | 无限 | 全球Anycast，推荐 |
| **ClouDNS** | 4个Anycast服务器 | 免费 |
| **Google DNS** | — | 仅解析，不托管 |
| **Namecheap** | 免费 | 购买域名时 |
| **Hurricane Electric** | 免费 | DNS托管 |

---

## 📝 代码/文档协作

| 服务 | 免费额度 |
|------|----------|
| **GitHub** | 公开仓库无限 |
| **GitLab** | 公开仓库无限 |
| **Notion** | 有限免费 |
| **Obsidian Publish** | 发布付费 |

---

## 🎨 静态站点托管

| 服务 | 免费额度 | 亮点 |
|------|----------|------|
| **GitHub Pages** | 无限带宽 | 与GitHub集成 |
| **Cloudflare Pages** | 500构建 + 无限带宽 | 全球CDN |
| **Vercel** | 100GB带宽 | Next.js 最佳 |
| **Netlify** | 100GB带宽 | 自动HTTPS |
| **Surge.sh** | 免费 | 快速部署 |

---

## 🔑 密钥/配置管理

| 服务 | 免费额度 |
|------|----------|
| **GitHub Secrets** | 仓库级，免费 |
| **Doppler** | 5人团队免费 |
| **Infisical** | 开源，自建免费 |
| **1Password** | — | Developer Program |

---

## 🔍 搜索引擎/API

| 服务 | 免费额度 |
|------|----------|
| **Algolia** | 1万请求/月 |
| **Meilisearch** | 自建免费，开源 |
| **Typesense** | 自建免费，开源 |

---

## 📊 GitHub Student Developer Pack（🎓 教育邮箱必备）

| 福利 | 额度 |
|------|------|
| DigitalOcean | $200 credit / 12个月 |
| Azure | $100 / 年 |
| GitHub Copilot | 免费 |
| .me 域名 | 1年免费 |
| JetBrains IDE | 1年免费 |
| Namecheap SSL | 1年免费 |
| SendGrid | 15K邮件/月 |
| 80+ 其他福利 | 工具/服务/SaaS |

**注册**: https://education.github.com/pack
**要求**: 教育邮箱验证（.edu.cn 等）
