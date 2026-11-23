# Terrence's Site

极简静态首页：`Hi，Terry！`。域名：[terry2026.xyz](https://terry2026.xyz)

## 本地预览

直接双击 `index.html`，或在本目录运行：

```bash
python3 -m http.server 8000
# 浏览器打开 http://localhost:8000
```

## 部署

- 托管：Cloudflare Pages
- 构建命令：无（纯静态）
- 输出目录：`.`（仓库根目录）
- 自定义域名：`terry2026.xyz`

每次 `git push` 到 `main` 分支会自动触发 Cloudflare Pages 重新部署。
