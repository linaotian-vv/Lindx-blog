---
title: "雨果静态站点发到哪里：几种常见做法"
description: "构建出公开目录之后，代码托管自带的页面、云平台一键部署、自己服务器上的网页服务，各适合什么人。"
keywords: "静态网站,托管,部署,上线"
cover: "https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=Static%20website%20deployment%20workflow%20with%20Hugo%20and%20cloud%20services&image_size=landscape_16_9"

date: 2026-03-05T16:00:00+08:00
lastmod: 2026-03-05T16:00:00+08:00

math: false
mermaid: false

categories:
  - 技术
tags:
  - 静态博客
  - 上线部署
---

用雨果（Hugo）写好站点后，本地会看到 **`public/`** 目录——**那就是整站静态文件**。接下来只差把它放到一台能对外提供网页访问（超文本传输协议）的服务上。下面按「省心程度」大致排个序，方便你对号入座。

<!--more-->

## 一、托管在 GitHub 提供的站点服务上

适合：仓库已经在 **GitHub**、想免费、访问量不大。

典型做法：用 **GitHub Actions（自动化流水线）** 在推送代码时执行 `hugo`，把生成结果推到 `gh-pages` 分支，或同一仓库的 `docs` 目录，再在仓库设置里打开 Pages。注意 **`hugo.toml`** 里的 **`baseURL`** 要和你实际域名（或 `用户名.github.io/仓库名`）一致，否则样式和链接容易错位。

## 二、云平台：Cloudflare / Netlify / Vercel 等

适合：想要 **自动构建、加密传输（HTTPS）、内容分发网络（CDN）** 一条龙，且愿意接持续集成（CI）。

绑定 **Git** 仓库，指定构建命令 `hugo`、输出目录 `public`，推送即部署。换主题或改文章一般几分钟内生效。

## 三、自己的云主机加上 Nginx

适合：已有服务器、要完全自控，或顺带跑别的服务。

把 `public/` 用 `rsync` 或 `scp` 同步到机器上，**Nginx** 的网站根目录指过去即可。记得配好证书（例如 Let's Encrypt）和缓存策略；更新流程可以写成一条脚本，减少手工操作。

## 小结

静态站的好处是**部署简单、抗并发、几乎没有服务端脚本，安全性相对省心**。先选一种最省事的托管方式跑起来，等访问量或需求变了再迁移，`public/` 始终是通用格式。
