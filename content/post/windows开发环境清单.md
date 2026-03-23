---
title: "在 Windows 上搭开发环境：我的最低配置清单"
description: "新机器或重装系统后，我会优先装的几样东西，保证能写代码、跑脚本、做版本管理。"
keywords: "Windows,开发环境,终端,装机备忘"
cover: "https://trae-api-cn.mchost.guru/api/ide/v1/text_to_image?prompt=Windows%20development%20environment%20with%20terminal%20and%20code%20editor&image_size=landscape_16_9"

date: 2026-03-15T14:30:00+08:00
lastmod: 2026-03-15T14:30:00+08:00

math: false
mermaid: false

categories:
  - 技术
tags:
  - 环境配置
  - 操作系统
---

每次换电脑最烦的不是装系统，而是**把顺手的东西一个个装回来**。下面这份是我自己的「最低可行配置」，不追求全家桶，只求能愉快地敲代码。

<!--more-->

## 终端与命令行环境

- **Windows 终端（Windows Terminal）**：多标签、配色、字体都好调。  
- **PowerShell 第七版**：和系统自带的 Windows PowerShell 5 并存，语法和体验更统一。  

习惯类 Unix 命令的话，再装 **Git for Windows**（自带 Git Bash）或 **适用于 Linux 的 Windows 子系统（WSL2）**，二选一即可，不必全装。

## 语言与运行时

按你实际技术栈来，我这边常见组合是：

- **Node.js 长期支持版**（前端、小工具脚本）  
- **Go / Python / .NET** 等按需安装，尽量用官方安装包或系统自带的 **`winget`** 包管理器，少用手动改环境变量 **PATH**。

## 编辑器

**VS Code** 或 **Cursor** 二选一；装几个必备扩展（主题、版本管理、常用语言的智能提示），若支持设置同步就打开，能省很多时间。

## 版本管理工具

**Git** 必装，全局配置示例：

```bash
git config --global user.name "你的名字"
git config --global user.email "你的邮箱"
```

生成好 **SSH** 密钥后，加到 **GitHub**、**GitLab** 等代码托管网站，后面推送、拉取就顺畅了。

## 杂项

- **7-Zip**：解压省心。  
- **浏览器**：日常浏览与前端调试各留一个也行。  

更重的容器（Docker）、虚拟机、数据库，等项目真需要再加，避免「装了一堆半年用一次」的愧疚感。你若有固定清单，也欢迎改成自己的一篇备忘文。
