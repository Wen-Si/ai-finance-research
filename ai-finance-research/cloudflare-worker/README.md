# AI金融学术研究平台 - Cloudflare Workers 代理部署指南

## 部署步骤

### 1. 安装 Wrangler CLI
```bash
npm install -g wrangler
```

### 2. 登录 Cloudflare
```bash
wrangler login
```

### 3. 部署 Worker
```bash
cd cloudflare-worker
wrangler deploy
```

### 4. 获取 Worker URL
部署成功后会输出类似：
```
https://ai-finance-proxy.your-account.workers.dev
```

### 5. 更新前端代理地址
将 `ai-finance-research.html` 中的 `ZHIPU_PROXY` 变量更新为你的 Worker URL：
```javascript
const ZHIPU_PROXY = 'https://ai-finance-proxy.your-account.workers.dev';
```

## 说明
- Worker 代理会自动添加 API Key，前端无需暴露密钥
- 免费额度：每天 10 万次请求
- 支持 CORS 跨域访问
