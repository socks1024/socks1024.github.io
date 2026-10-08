---
title: 你好 Github Pages
date: 2026-10-08 19:41:00 +0800
categories:
  - 其他开发
tags:
---
哇这么好的东西竟然免费，感谢巨硬。

## Github Pages

GitHub Pages 是一种静态站点托管服务，它直接从存储库 GitHub 获取 HTML、CSS 和 JavaScript 文件，可以选择通过生成过程运行文件并发布网站。 这个网站就是使用 Github Pages 发布的。

有关 Github Pages 更详细的内容，可以查看官方文档：[Github Pages 文档](https://docs.github.com/zh/pages)。

## Jekyll

这个网站基于 Jekyll 搭建而成，并通过 Github Actions 发布到 Github Pages。

Jekyll 是一个简单的博客形态的静态站点生产机器。它将原始文本格式的文档转化成一个完整的可发布的静态网站，可以发布在任何你喜爱的服务器上。Jekyll 也可以运行在 GitHub Page 上，也就是说，你可以使用 GitHub 的服务来搭建你的项目页面、博客或者网站，而且是完全免费的。

有关 Jekyll 更详细的内容可以查看官方文档：[Jekyll](https://jekyllcn.com/docs/home/)。

### 项目结构

[Jekyll 的目录结构](https://jekyllcn.com/docs/structure/)

一个基本的 Jekyll 网站的目录结构一般是像这样的：

```
├── _config.yml
├── _drafts
|   ├── begin-with-the-crazy-ideas.textile
|   └── on-simplicity-in-technology.markdown
├── _includes
|   ├── footer.html
|   └── header.html
├── _layouts
|   ├── default.html
|   └── post.html
├── _posts
|   ├── 2007-10-29-why-every-programmer-should-play-nethack.textile
|   └── 2009-04-26-barcamp-boston-4-roundup.textile
├── _site
├── .jekyll-metadata
└── index.html
```

其中 `_posts` 文件夹用于存放要发布、展示的博客文章，而 `_drafts` 文件夹用于存放草稿。

### 主题

这个网站使用了 Jekyll 的 chirpy 主题，详见[chirpy](https://github.com/cotes2020/jekyll-theme-chirpy)。

在实际部署网站时，使用的是 chirpy-starter 包，相比于原始的 chirpy 仓库节省了一定的配置和初始化步骤。

### HTML

Jekyll 通过渲染 Markdown 等基础的标记语言来显示页面，所以也兼容 Markdown 中的 HTML 语法。

下面是一个插入 HTML 语法的例子，我插入了一个简单的 Godot 游戏模板程序。（在 Obsidian 中，这里会显示为一段诡异的空白。你还是太弱小了啊 Obsidian）

<iframe src="/assets/games/GodotProjectTemplate-web-v0.1.0/index.html" width="100%" height="600" frameborder="0"></iframe>

## Markdown

这个项目使用 Obsidian 作为 Markdown 编辑工具，并引入了一些插件来辅助文字工作。

### Templater

为了简化创建符合 Jekyll 规范的文档的步骤，当前工作区使用了 Templater 插件来对 `_posts` 下新建的 Markdown 文件进行初始化，将文件重命名为“日期 + 文件名”的格式，并自动添加基础的 frontmatter。