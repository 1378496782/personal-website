# Personal Website — FreeZ 的小站

FreeZ 的个人网站（博客）：复盘、方案、分享。基于 [Fuwari](https://github.com/saicaca/fuwari) 主题（Astro 5 + Svelte + Tailwind）。

## 常用命令

```bash
pnpm dev      # 开发服务器 http://localhost:4321
pnpm build    # 构建 + pagefind 索引，产物在 dist/
pnpm new-post # 新建文章脚手架
```

包管理器用 pnpm（preinstall 有 only-allow pnpm 限制）。

## 结构速览

- `src/config.ts` — 站点配置：标题/副标题/作者/社交链接/导航
- `src/content/posts/` — 博客文章（Markdown，frontmatter: title/published/description/tags/category/draft）
- `src/content/spec/about.md` — 关于页内容
- `src/assets/images/avatar-freez.png` — 侧栏头像
- `astro.config.mjs` — `site` 已配置为 https://xjtuzfw.top/

## 已知事项

- **构建 bug 修复**：`src/styles/markdown.css` 头部有一行 `@import './main.css';`，是修 Fuwari 上游 issue #528/#766 的间歇性构建失败（`link` class does not exist）。升级主题时注意保留。
- 站名「FreeZ 的小站」，作者署名 FreeZ。网站不放个人手机号/邮箱等敏感信息。

## 部署（已上线 2026-11-14）

- GitHub：https://github.com/1378496782/personal-website（Public，main 分支，push 即自动部署）
- Cloudflare Pages Git 集成，Node 22（仓库有 .node-version）
- 线上地址：https://xjtuzfw.top 和 https://www.xjtuzfw.top（DNS 已迁 Cloudflare：macy/hugh.ns.cloudflare.com，SSL 由 CF 自动签发，火山引擎旧证书/旧 A 记录已废弃）
- 发文流程：在 `src/content/posts/` 写 Markdown → git commit & push → 约 1~2 分钟自动上线

## 内容约定

- 栏目规划：复盘 / 方案 / 分享（category 字段）
- 内容比例约 7 成职业方向（Go 服务端、AI 工程化），3 成生活
- 更新节奏：每周一篇或每两周一篇，宁可慢不可断
