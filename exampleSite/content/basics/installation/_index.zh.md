---
title: 安装
weight: 15
---

以下步骤可帮助您初始化您的新网站。如果你根本不认识 Hugo ，我们强烈建议你按照这个[伟大的初学者文档](https://gohugo.io/overview/quickstart/)进行学习。

## 创建你的项目

 Hugo 提供了一个 `new` 命令来创建一个新的网站。

```
hugo new site <new_project>
```

## 安装主题

按照[本文档](https://gohugo.io/themes/installing/)安装 **Hugo-theme-learn** 主题

主题的存储库是：https://github.com/matcornic/hugo-theme-learn.git

或者，您可以[下载主题为.zip](https://github.com/matcornic/hugo-theme-learn/archive/master.zip)文件并将其解压到themes目录

## 基本配置

建立网站时，可以使用'--theme`选项来设置主题。我们建议您编辑您的配置文件并默认设置主题。顺便说一句，添加要启用搜索功能的要求。

```toml
＃更改在使用Hugo构建站点时要使用的默认主题
theme = "hugo-theme-learn"

＃用于搜索功能
[outputs]
home = [ "HTML", "RSS", "JSON"]
```

## 创建你的第一章页面

章节是包含其他子页面的页面。它有一个特殊的布局风格，通常只包含 **章节名** **标题** **内容摘要**

```
### Chapter 1

# Basics

Discover what this Hugo theme is all about and the core-concepts behind it.
```

呈现为

![A Chapter](/basics/installation/images/chapter.png?classes=shadow&width=60pc)

**Hugo-theme-learn** 提供了原型为您的网站创建骨架。首先使用以下命令创建您的第一章页面

```
hugo new --kind chapter basics/_index.md
```

通过打开给定的文件，你应该在上面看到“chapter = true”属性，这意味着这个页面是一个_chapter_。

默认情况下，所有的章节和页面都被创建为草稿。如果要渲染这些页面，请从元数据中删除 `draft: true`属性。

## 创建你的第一个内容页面

然后，在上一章中创建内容页面。以下是在本章中创建内容的两种方法：

```
hugo new basics/first-content.md
hugo new basics/second-content/_index.md
```

随意编辑这些文件，通过添加一些示例内容并替换文件开头的`title`值。

## 在本地启动网站

启动以下命令：

```
hugo serve
```

转到 `http://localhost:1313`

你应该注意三件事情：

1. 您左边有一个 **Basics** 菜单，其中包含两个子菜单，其名称与以前创建的文件中的 `title` 属性相同。
2. 主页向您介绍如何定制它。按照说明。
3. 使用 `hugo serve` 命令，只要保存文件，页面就会刷新。整洁！

## 建立网站

当您的站点准备好部署时，启动以下命令：

```
hugo
```

已生成一个 `public` 文件夹，其中包含您网站的所有静态内容和资产。它现在可以部署在任何Web服务器上！

{{% notice note %}}
本网站可以自动发布和托管[Netlify](https://www.netlify.com/) (阅读更多关于[自动HUGO部署与Netlify](https://www.netlify.com/blog/2015/07/30/hosting-hugo-on-netlifyinsanely-fast-deploys/)).或者，您可以使用[Github页面](https://gohugo.io/hosting-and-deployment/hosting-on-github/)
{{% /notice %}}