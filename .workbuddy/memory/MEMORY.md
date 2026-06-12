# 项目记忆 - 二条律师网站

## 项目概况
- 仓库：https://github.com/azrzsthl/azrzsthl.github.io
- 线上地址：https://azrzsthl.github.io
- 域名：ertiao.com（待绑定）
- 技术栈：Hexo 8.1.2 + Fluid 主题
- 部署：GitHub Pages + GitHub Actions（源码 main 分支 → 自动构建部署）

## 内容结构
- / — 首页混排，8 条/页
- /writing/:title — 文章永久链接
- /writing/reload/ — #reload 系列
- /writing/caveman/ — #caveman 系列
- /projects/ — 项目页
- /about/ — 关于页
- /archive/ — 归档页（按年月）
- law/tools 用分类+标签区分，不单独开子路径（精简原则）

## 设计决策
- 首页混排不分类：法律/思考/工具/暴论一体
- 英文 slug：避免中文 URL 编码问题，reload/caveman 保留品牌名
- 归档极简：纯列表，年月分组
- 暂无案例展示页：等执业后加 /cases
- RSS + 本地搜索已启用

## 本地开发
- Hexo CLI 因 npm cache 权限问题无法直接使用 npx hexo
- 用 Node API 直接调用：`node -e "const Hexo=require('hexo'); ... hexo.call('generate')"` 
- 本地预览：`node serve.js`（自定义静态服务器，处理代理风格请求）
- 构建命令：`npm run build` 对应 `hexo generate`

## 待办
- [ ] 关于页内容替换为真实版本
- [ ] 项目页 GitHub 链接替换
- [ ] 绑定自定义域名 ertiao.com（DNS CNAME + GitHub Pages 配置）
- [ ] nijyou.com 域名 301 重定向到 ertiao.com
- [ ] 替换默认头像/图标
- [ ] 关于页"现在在做什么"需要定期更新机制
