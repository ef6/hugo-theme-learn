---
title: "Hugo learn 主题"
---
# Hugo learn 主题

[Hugo-theme-learn](http://github.com/matcornic/hugo-theme-learn) 是一个 [Hugo](https://gohugo.io/) 的主题，一个快速而现代的静态网站引擎。Hugo 经常用于博客，这种多语言准备主题**完全为文档设计**。

这个主题是部分移植于 [Grav](https://getgrav.org/) 的 [Learn theme](http://learn.getgrav.org/) 主题，这是一个用PHP编写的现代平面文件CMS。

{{% notice tip %}}
本主题使用**页面树结构**来组织内容：所有内容都是属于其他页面的页面。 [阅读更多关于此]({{%relref "cont/pages/_index.md" %}}) 
{{% /notice %}}

## 主要特点

* [自动搜索]({{%relref "basics/configuration/_index.md#activate-search" %}})
* [多语言模式]({{%relref "cont/i18n/_index.md" %}})
* **无限的菜单级别**
* **自动下一个/上一个按钮在菜单条目中导航**
* [图像大小,阴影...]({{%relref "cont/markdown.en.md#images" %}})
* [附件文件]({{%relref "shortcodes/attachments.en.md" %}})
* [子页面列表]({{%relref "shortcodes/children/_index.md" %}})
* [流程图]({{%relref "shortcodes/mermaid.en.md" %}})（流程图，序列，甘特图）
* [可定制的外观和主题变体]({{%relref "basics/style-customization/_index.md"%}})
* [按钮]({{%relref "shortcodes/button.en.md" %}}),  [Tip / Note / Info / Warning 容器]({{%relref "shortcodes/notice.en.md" %}}),  [展开栏]({{%relref "shortcodes/expand.en.md" %}})

![截图](https://github.com/matcornic/hugo-theme-learn/raw/master/images/screenshot.png?width=40pc&classes=shadow) 

## 贡献此文档
随意更新此内容，只需点击每个页面右上方显示的 **编辑此页** 链接，然后请求

{{% notice info %}}
您的修改将在合并时自动部署。
{{% /notice %}}

## 文档网站
这个的文档目前是通过一个简单的命令静态生成的: `hugo -t hugo-theme-learn` -- 源代码[在GitHub上获得](https://github.com/matcornic/hugo-theme-learn) 

{{% notice note %}}
自动发布和托管感谢[Netlify](https://www.netlify.com/)。阅读更多关于[使用Netlify自动化HUGO部署](https://www.netlify.com/blog/2015/07/30/hosting-hugo-on-netlifyinsanely-fast-deploys/)
{{% /notice %}}