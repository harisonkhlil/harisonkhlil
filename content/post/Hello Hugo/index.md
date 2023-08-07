---
image : image1.jpeg
title: Hello Hugo
description: 第一篇博客
date: 2023-07-28
math: true
toc: true
comments : true
tags:
  - "Markdown"
  - "Theme"
  - "Hugo"
categories:
  - "syntax"
  - "themes"
series:
  - "Blog Guide"
---

# Hello Hugo

{{< quote author="Hugo" source="Hugo Website" url="https://gohugo.io/">}}
The world's fastest framework for building website

Hugo is one of the most popular open-source static site generators. With its amazing speed and flexibility, Hugo makes building websites fun again.
{{< /quote >}}


## 阅前提要

### PC 环境

本文的环境是 `macOS Ventura` 芯片是 `Apple Silicon` 

### 工具准备

`Git` 以及 `Homebrew`

```shell
# 出现类似 hugo v0.116.1-3e1ea030a5897addaf9d113d0826709fe07f77c0+extended darwin/arm64 BuildDate=2023-08-01T07:24:54Z VendorInfo=brew 则安装成功 hugo
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" #安装 Homebrew
brew install git
brew install hugo
hugo version
```

### 基础命令

了解基础的 **Git**， **cd** ， **mkdir** 即可

## 创建 GitHub Page 仓库

1. 命名 **GitHub Pages** 仓库，这个仓库必须使用特殊的命名格式 `<username.github.io>`， `<username>` 是自己的GitHub的用户名。
2.  勾选 **Public**，设置为公开仓库。

![CleanShot 2023-08-07 at 16.37.18@2x](https://s2.loli.net/2023/08/07/uI2TiZ9Ar3Vlenz.png)

## 创建 Hugo 博客目录

```shell
cd ~/Documents
mkdir blog
cd blog
hugo new site xxx-blog
cd xxx-blog
```



### 寻找合适的主题

去这里 —> [Hugo Theme](https://themes.gohugo.io/) 找一个自己喜欢的主题

**！！！注意**：不同主题创建文章的方法不同

下面按照我的主题 **Stack**来演示

## 主题设置

**Stack** 的官网：https://stack.jimmycai.com/

点击 **Getting Start** 在 **Installation** 这里：

```shell
git submodule add https://github.com/CaiJimmy/hugo-theme-stack/ themes/hugo-theme-stack
```

基本上所有的主题都会有这几个目录：

- **archetypes**：存放用 hugo 命令新建的 md 文件应用的 front matter 模版
- **content**：存放内容页面，如 Blog
- **layouts**：存放定义网站的样式，写在`layouts`文件下的样式会覆盖安装的主题中的 `layouts`文件同名的样式
- **static**：存放所有静态文件，如图片
- **data**：存放创建站点时 Hugo 使用的其他数据
- **public**：存放 Hugo 生成的静态网页
- **themes**：存放主题文件
- **config.toml**：网站配置文件
- **examplesite**: 网站 demo

阅读主题的配置文件按需修改即可

拿 **Stack** 主题来说， 创建文章的方式有所不同，普通主题的创建方式是 `hugo new xxx.md` 而它则是按照一定的 `layout`来创建文章：

```shell
content
└── post
    └── my-first-post
        ├── index.md
        ├── image1.png
        └── image2.png
```

如果想要实现本博客的效果请前往 https://github.com/harisonkhlil/harisonkhlil 查看目录结构以及相关文件 

## 文章预览

```shell
hugo server # 文章实时预览
hugo #发布文章
```

## 网站同步

```shell
cd public
git init -b main
# 将 public 文件夹关联远程 GitHub Pages 仓库，使用 GitHub Pages 仓库的SSH链接。
git remote add origin git@github.com:harisonkhlil/harisonkhlil.github.io.git # 这里请自行修改
# 推送博客源仓库的 public 文件夹中的 HTML 网页文件到 GitHub Pages 仓库中，在推送仓库内容前要先用 git pull --rebase origin main 和远端仓库同步，否则会报错。
git pull --rebase origin main 
git add .
git commit -m "init blog" 
git push origin main #或者可能为 git push --set-upstream origin main
```

打开 https://username.github.io 看部署是否成功。

## 主题语法

需要在 **index.md** 开头加上：
```markdown
---
image : image1.jpeg
title: Hello Hugo
description: 第一篇博客
date: 2023-07-28
toc: true
comments : true
tags:
  - "Markdown"
  - "Theme"
  - "Hugo"
categories:
  - "syntax"
  - "themes"
series:
  - "Blog Guide"
---
```

具体其他 Frontmatter 请前往 https://stack.jimmycai.com/writing/frontmatter

### 一些富文本支持

#### Twitter

{{< twitter_simple user="chushi_su" id="1684517871983157248" >}}

#### YouTube

{{< youtube ZJthWmvUzzc >}}

#### bilibilibi

{{< bilibili av498363026 >}}

#### Gist Shortcode

{{< gist spf13 7896402 >}}

#### Quote Shortcode

Stack adds a `quote` shortcode.  For example:

{{< quote author="A famous person" source="The book they wrote" url="https://en.wikipedia.org/wiki/Book">}}
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
{{< /quote >}}

## Reference

- [hugo quick start](https://gohugo.io/getting-started/quick-start/)
- [stack theme manual](https://stack.jimmycai.com/guide/getting-started)
- [deploy your using hugo and github action](https://www.pseudoyu.com/en/2022/05/29/deploy_your_blog_using_hugo_and_github_action/)
