# 二条律师个人网站

> 一个律师 + 创作者的个人网站，用来放法律、思考、工具、暴论。

## 在线地址

- **GitHub Pages**: https://azrzsthl.github.io
- **计划主域名**: ertiao.com（待绑定）
- **源码仓库**: https://github.com/azrzsthl/azrzsthl.github.io

## 技术栈

| 项目 | 版本/说明 |
|------|----------|
| 静态站点生成器 | Hexo 8.1.2 |
| 主题 | hexo-theme-fluid 1.9.9 |
| 部署 | GitHub Pages + GitHub Actions |
| 语言 | Markdown / EJS / Stylus |

## 内容结构

| 路径 | 说明 |
|------|------|
| `/` | 首页，混排最新内容，8 条/页 |
| `/writing/:title` | 文章永久链接 |
| `/writing/reload/` | #reload 系列（深度长文） |
| `/writing/caveman/` | #caveman 系列（原始表达/暴论） |
| `/projects/` | 项目页 |
| `/about/` | 关于页 |
| `/archive/` | 按年月归档 |
| `/tags/yearly/` | 年度总结 |

`law` 和 `tools` 使用分类 + 标签区分，不单独开设子路径。

## 本地开发

由于当前环境 Hexo CLI 无法直接使用 `npx hexo`，采用以下方式：

```bash
# 安装依赖
npm install

# 生成静态文件
npm run build

# 本地预览（使用自定义静态服务器）
node serve.js
# 默认监听 http://127.0.0.1:4000
```

> 注意：`npm run dev`（`hexo server`）在部分环境因代理或权限问题可能无法正常工作，推荐使用 `node serve.js`。

## 创建内容

```bash
# 发布新文章
npm run new -- "文章标题"

# 创建草稿
npm run draft -- "草稿标题"

# 发布草稿
npm run publish -- "草稿标题"
```

## 文章 Front Matter 规范

```yaml
---
title: 文章标题
date: 2024-01-01
slug: 英文-url-slug
categories:
  - reload  # 或 caveman / law / tools / thinking
tags:
  - 标签1
  - 标签2
  - yearly  # 年度总结文章加此标签
---
```

## 部署流程

1. 在 `main` 分支修改源码。
2. `git push origin main` 推送到 GitHub。
3. `.github/workflows/deploy.yml` 自动构建并部署到 GitHub Pages。
4. 等待 Actions 完成后，线上地址自动更新。

## 目录说明

```
.
├── _config.yml              # Hexo 主配置
├── _config.fluid.yml        # Fluid 主题覆盖配置
├── package.json             # 项目依赖与脚本
├── serve.js                 # 本地静态服务器
├── source/                  # 站点内容
│   ├── _posts/              # 已发布文章
│   ├── _drafts/             # 草稿
│   ├── about/               # 关于页
│   ├── projects/            # 项目页
│   └── yearly/              # 年度总结入口
├── themes/                  # 主题目录
│   └── fluid/               # Fluid 主题
└── public/                  # 构建输出（自动生成）
```

## 待办

- [ ] 关于页内容替换为真实版本
- [ ] 项目页 GitHub 链接替换
- [ ] 绑定自定义域名 ertiao.com
- [ ] nijyou.com 域名 301 重定向到 ertiao.com
- [ ] 替换默认头像/图标
- [ ] 建立关于页"现在在做什么"的定期更新机制

## License

ISC
