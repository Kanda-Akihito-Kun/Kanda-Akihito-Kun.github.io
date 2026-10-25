# Kanda Akihito Kun Blog

这是一个只生成静态文件的 Hexo 博客，使用 yilia-plus 主题，发布到 GitHub Pages。

## 本地预览

```bash
npm install
npm run server
```

浏览器访问 <http://localhost:4000/>。

新建文章：

```bash
npx hexo new post "文章标题"
```

文章文件位于 `source/_posts/`，可在文章头部使用 `tags`、`categories` 和 `comments: false`。

## 生成纯静态文件

```bash
npm run build
```

生成结果位于 `public/`，其中只有 HTML、CSS、JavaScript 和图片等静态资源。

发布前建议检查构建输出中没有 `ERROR`，并打开首页、文章页、归档页、标签页和 `atom.xml`。

## 部署到 GitHub Pages

```bash
npm run clean
npm run build
npm run deploy
```

部署插件会把 `public/` 推送到 `gh-pages` 分支。然后在 GitHub 仓库的 **Settings → Pages** 中选择 **Deploy from a branch**，分支选择 `gh-pages`，目录选择 `/ (root)`。

每次发布都需要先构建再部署，`deploy` 不会重新生成页面。部署网页后，还需将源码提交并推送到 `main` 分支。提交前检查 `git status`，避免把其他未完成的改动一起提交。

首次发布还需要把源码提交到 `main` 分支，并确认 GitHub Pages 使用 `gh-pages` 分支的根目录。

## 发布连载文章

当前文章位于 `source/_posts/对B站CDN的简单探索/`。第二期、第三期各写一篇 Markdown，放在这个目录即可。目录用于管理文件，不会自动生成系列导航。

第二期头部示例，日期请填写实际发布时间：

```yaml
---
title: 对 B 站 CDN 的简单探索（第二期）
date: 2026-10-27 08:00:00
permalink: 2026/10/27/bilibili-cdn-part-2/
tags:
  - B站
  - CDN
  - 网络
---
```

使用 `permalink` 明确指定文章网址；发布后保持此字段不变，避免原链接失效。第二期、第三期分别使用自己的日期和 `part-2`、`part-3` 标识。

每期图片分别放在 `source/images/bilibili-cdn/part-1/`、`part-2/`、`part-3/` 中，引用时使用从网站根目录开始的路径：

```html
<img width="720" src="/images/bilibili-cdn/part-2/示意图.png" />
```

引言后加 `<!-- more -->`，首页只展示前面的摘要。正文中可加入 `[系列目录](/series/bilibili-cdn/)`。

发布新一期时，更新 `source/series/bilibili-cdn/index.md` 中的文章链接，并把上一期末尾的“下一期：待发布”替换为新一期链接。未发布的期数只保留文字，不提前添加链接。

未完成的文章放在 `source/_drafts/`，避免在部署整站时一起发布。
