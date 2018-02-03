---
date: 2016-04-09T16:50:16+02:00
title: 配置
weight: 20
---

## 网站全局参数

在[Hugo全局配置](https://gohugo.io/overview/configuration/)上，**Hugo-theme-learn** 可以让你在 `config.toml` 中定义以下参数（这里的值是默认）。

请注意，其中一些参数在本文档的其他章节中有详细说明。

```toml
[params]
  ＃前缀URL来编辑当前页面。将在每页的右上角显示“编辑此页”按钮。
  ＃有用的机会让人们创建您的文档的合并请求。
  ＃请参阅本文档站点中的config.toml文件以获取示例。
  editURL = ""
  ＃该网站的作者，将用于元信息
  author = ""
  ＃网站描述，将被用于元信息
  description = ""
  ＃在菜单上显示访问页面的复选标记
  showVisitedLinks = false
  ＃禁用搜索功能。它会隐藏搜索栏
  disableSearch = false
  ＃生成新版本的站点时，Javascript和CSS缓存会自动分发。
  ＃将其设置为true以禁用此行为（某些代理不能很好地处理此优化）
  disableAssetsBusting = false
  ＃将其设置为true以禁用内联代码的“复制到剪贴板”按钮。
  disableInlineCopyToClipBoard = false
  ＃菜单中快捷方式的标题是默认设置的。将其设置为true将其禁用。
  disableShortcutsTitle = false
  ＃使用多语言网站时，禁用切换语言按钮。
  disableLanguageSwitchingButton = false
  ＃通过"weight" or "title"在菜单中对菜单进行排序。默认为"weight"
  orderectionsby =“weight”
  ＃更改一个变体的默认颜色方案。可以是"red", "blue", "green"。
  themeVariant =“”
```

## 激活搜索

如果尚未出现，请在相同的`config.toml`文件中添加以下行。

```toml
[outputs]
home = [ "HTML", "RSS", "JSON"]
```

学习主题使用hugo版本20+中的最后一个改进来生成一个json索引文件，供lunr.js javascript搜索引擎使用。

> Hugo在公用文件夹的根目录下生成lunrjs index.json。
> 当你用“hugo server”建立网站时，hugo会在内部生成它，当然它不会显示在文件系统中