---
title: "日常用的 Git 命令小抄（够用版）"
description: "提交、分支、撤销、暂存——不背长文档也能干活的一组常用命令。"
keywords: "版本控制,命令行,提交,分支"
cover: "https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=Git%20command%20line%20terminal%20with%20version%20control%20diagram%20and%20code%20snippets&image_size=landscape_16_9"

date: 2026-03-18T10:00:00+08:00
lastmod: 2026-03-18T10:00:00+08:00

math: false
mermaid: false

categories:
  - 技术
tags:
  - 版本控制
  - 备忘清单
---

我记性一般，子命令又多，所以把**最常用**的几条记下来，需要时直接搜这篇。假设你已经配置好用户名与邮箱（`user.name` / `user.email`），远程仓库名叫 `origin`。

<!--more-->

## 日常提交

```bash
git status
git add -p          # 按块挑选要暂存的内容，比直接 add . 更安全
git commit -m "本次修改说明"
git push origin main
```

## 分支

```bash
git switch -c feature/foo    # 新建并切换；把 feature/foo 换成你的分支名
git switch main
git merge feature/foo
git branch -d feature/foo    # 已合并的分支可以删掉
```

## 改错与撤销

```bash
git restore README.md        # 示例：丢弃工作区里对该文件的修改（请换成实际路径）
git restore --staged README.md  # 示例：取消暂存，改动仍保留在工作区
git reset --soft HEAD~1      # 撤销最近一次提交，改动仍留在暂存区
```

## 临时收起未提交改动

```bash
git stash push -m "先收起来"
git stash list
git stash pop
```

## 看历史

```bash
git log --oneline -15
git show HEAD
```

真正复杂的合并冲突、交互式变基（rebase），还是配合图形界面或官方文档更稳。这篇的目标只是：**八成日常操作不用离开终端**。
