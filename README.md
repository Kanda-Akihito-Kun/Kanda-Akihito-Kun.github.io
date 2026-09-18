# Kanda Akihito Kun Blog

这是一个只生成静态文件的 Hexo 博客，使用 yilia-plus 主题，发布到 GitHub Pages。

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

发布前建议检查构建输出中没有 `ERROR`，并打开首页、文章页、归档页、标签页和 `atom.xml`。

## 部署到 GitHub Pages

```bash
npm run deploy
```

部署插件会把 `public/` 推送到 `gh-pages` 分支。然后在 GitHub 仓库的 **Settings → Pages** 中选择 **Deploy from a branch**，分支选择 `gh-pages`，目录选择 `/ (root)`。

首次发布还需要把源码提交到 `main` 分支，并确认 GitHub Pages 使用 `gh-pages` 分支的根目录。

首次发布还需要把源码提交到 `main` 分支，并确认 GitHub Pages 使用 `gh-pages` 分支的根目录。
