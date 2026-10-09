---
title: 你好 Github Pages
date: 2026-10-08 19:41:00 +0800
categories:
  - 程序开发
tags:
---
哇这么好的东西竟然免费，感谢巨硬。

下文列出了在搭建本站时用到的各种技术和外部库，非常简单好用，推荐大家尝试。（顺便还要感谢 Claude 大人帮我选择这套好用的技术栈）

## Github Pages

GitHub Pages 是一种静态站点托管服务，它直接从存储库 GitHub 获取 HTML、CSS 和 JavaScript 文件，可以选择通过生成过程运行文件并发布网站。 这个网站就是使用 Github Pages 发布的。

只要网站的源仓库是 public 的，就可以免费使用 Github Pages 的服务。话说我只需要把别人的代码拼拼凑凑就可以免费用 Github 的服务器吗，这太棒了（）

有关 Github Pages 更详细的内容，可以查看官方文档：[Github Pages 文档](https://docs.github.com/zh/pages)。

## Jekyll

这个网站基于 Jekyll 搭建而成，并通过 Github Actions 发布到 Github Pages。

Jekyll 是一个简单的博客形态的静态站点生产机器。它将原始文本格式的文档转化成一个完整的可发布的静态网站，可以发布在任何你喜爱的服务器上。Jekyll 也可以运行在 GitHub Page 上，也就是说，你可以使用 GitHub 的服务来搭建你的项目页面、博客或者网站，而且是完全免费的。

有关 Jekyll 更详细的内容可以查看官方文档：[Jekyll](https://jekyllcn.com/docs/home/)。

### 项目结构

一个基本的 Jekyll 网站的目录结构一般是像这样的：

[Jekyll 的目录结构](https://jekyllcn.com/docs/structure/)

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

本网站的源仓库位于 [socks1024/socks1024.github.io](https://github.com/socks1024/socks1024.github.io)，可以作为参考。因为是使用 Github Actions 构建和部署的，所以文件结构会略有差异（没有 `_site` 等构建产生的中间文件）。

### 主题

这个网站使用了 Jekyll 的 chirpy 主题，详见[chirpy](https://github.com/cotes2020/jekyll-theme-chirpy)。

在实际部署网站时，使用的是 chirpy-starter 包，相比于原始的 chirpy 仓库节省了一定的配置和初始化步骤。

[2019-08-08-text-and-typography.md](https://github.com/cotes2020/jekyll-theme-chirpy/blob/master/_posts/2019-08-08-text-and-typography.md) 是 chirpy 官方的 Markdown 文档及可用语法的示例，非常全面，包括很多 Markdown 基础渲染器没有的功能，比如脚注、图片语法等等。

### HTML

Jekyll 通过渲染 Markdown 等基础的标记语言来显示页面，所以也兼容 Markdown 中的 HTML 语法。

下面是一个插入 HTML 语法的例子，我插入了一个简单的 Godot 程序。

<iframe src="/assets/games/GodotProjectTemplate-web-v0.1.0/index.html" width="100%" height="600" frameborder="0"></iframe>

非文本格式的文件也可以作为附件跟随网站一起发布，Jekyll 完全兼容，唯一问题是 Github 的容量限制。

## Giscus

chirpy 主题还提供了使用 giscus 来为网站提供评论区的功能。

[giscus](https://giscus.app/zh-CN) 是一个利用 [GitHub Discussions](https://docs.github.com/en/discussions) 实现的评论系统，可以让访客借助 GitHub 在你的网站上留下评论和反应。

这种方法的优点在于简单快捷、无需后端数据库；缺点在于评论者需要先有一个 Github 账号。

## Obsidian

这个网站在本地使用 Obsidian 作为 Markdown 编辑工具，并引入了一些插件来辅助文字工作。

由于 Obsidian 无法正确的渲染一部分 HTML 功能（这不是废话吗， Obsidian 又不是浏览器），Obsidian 自身的排版、主题等功能也无法套用到 Jekyll 中，所以文章的最终展示形式仍需以实际网页为准。

### Templater

为了简化创建符合 Jekyll 规范的文档的步骤，本地工作区使用了 Templater 插件来对 `_posts` 下新建的 Markdown 文件进行初始化，将文件重命名为“日期 + 文件名”的格式，并自动添加基础的 frontmatter。真不错啊（）