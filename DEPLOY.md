# 部署说明

## 现状（已上线）

| 项目 | 值 |
|---|---|
| 正式域名 | https://terry2026.xyz |
| www 域名 | https://www.terry2026.xyz |
| Cloudflare Pages 预览域名 | https://terry2026-site.pages.dev |
| GitHub 仓库 | https://github.com/wayne0612/terrence-site |
| Cloudflare 账号 ID | 54af74d472ee082830e61a3550e9e108 |
| Pages 项目名 | terry2026-site |
| DNS | 根域名与 www 均为 CNAME → terry2026-site.pages.dev（橙色代理） |

## 本地开发

```bash
# 直接双击 index.html，或：
python3 -m http.server 8000
# 打开 http://localhost:8000
```

改完代码后提交并推送：

```bash
git add .
git commit -m "描述你的改动"
git push
```

## 手动部署（当前方式）

```bash
npx wrangler pages deploy . --project-name=terry2026-site
```

wrangler 已用 yangawee463@gmail.com 的 OAuth 登录，可以直接部署。

## 自动部署（可选，未启用）

当前 Pages 项目是 Direct Upload 模式。要实现 push 后自动部署，需要以下任一种：

1. Cloudflare Pages 的 Git 集成（在 Cloudflare Dashboard → Pages → 项目 → Settings → Build → Connect to Git）
2. GitHub Actions + wrangler-action（需要带 `workflow` 权限的 classic token 和 Actions Secrets）

## 清理 API Token

部署时创建的 Cloudflare API Token（`terry2026-site-deploy`）已在 Cloudflare 完成配置，可到
https://dash.cloudflare.com/profile/api-tokens 撤销。日常部署用 wrangler OAuth 即可，不依赖该 token。
