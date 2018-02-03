---
date: 2016-04-09T16:50:16+02:00
title: 页面组织结构
weight: 5
---

在 **Hugo** 中，网页是您网站的核心。配置完成后，页面肯定是文档网站的附加值。

## 文件夹

像[其他 Hugo 项目](https://gohugo.io/content/organization/)组织您的网站。通常情况下，您的所有网页都会有一个 **content** 文件夹。


    content
    ├── level-one 
    │   ├── level-two
    │   │   ├── level-three
    │   │   │   ├── level-four
    │   │   │   │   ├── _index.md       <-- /level-one/level-two/level-three/level-four
    │   │   │   │   ├── page-4-a.md     <-- /level-one/level-two/level-three/level-four/page-4-a
    │   │   │   │   ├── page-4-b.md     <-- /level-one/level-two/level-three/level-four/page-4-b
    │   │   │   │   └── page-4-c.md     <-- /level-one/level-two/level-three/level-four/page-4-c
    │   │   │   ├── _index.md           <-- /level-one/level-two/level-three
    │   │   │   ├── page-3-a.md         <-- /level-one/level-two/level-three/page-3-a
    │   │   │   ├── page-3-b.md         <-- /level-one/level-two/level-three/page-3-b
    │   │   │   └── page-3-c.md         <-- /level-one/level-two/level-three/page-3-c
    │   │   ├── _index.md               <-- /level-one/level-two
    │   │   ├── page-2-a.md             <-- /level-one/level-two/page-2-a
    │   │   ├── page-2-b.md             <-- /level-one/level-two/page-2-b
    │   │   └── page-2-c.md             <-- /level-one/level-two/page-2-c
    │   ├── _index.md                   <-- /level-one
    │   ├── page-1-a.md                 <-- /level-one/page-1-a
    │   ├── page-1-b.md                 <-- /level-one/page-1-b
    │   └── page-1-c.md                 <-- /level-one/page-1-c
    ├── _index.md                       <-- /
    └── page-top.md                     <-- /page-top

{{% notice note %}}
`_index.md` 是每个文件夹所必需的，它是你的“文件夹主页”
{{% /notice %}}

## 类型

**Hugo-theme-learn** 定义了两种类型的页面。**默认-Default** 和 **章节-Chapter**。两者都可以在文档的任何级别使用，唯一的区别是布局显示。

**章节** 页面，用来作为一组子页面的介绍。通常，它包含一个简单的标题和一个分割行来定义可以在其下找到的内容。
您可以将任何HTML定义为菜单的前缀。在下面的例子中，这只是一个数字，但可能是一个[图标](https://fortawesome.github.io/Font-Awesome/).

![章节页](/cont/pages/images/pages-chapter.png?width=50pc)

```markdown
+++
title = "Basics"
chapter = true
weight = 5
pre = "<b>1. </b>"
+++

### Chapter 1

# Basics

Discover what this Hugo theme is all about and the core-concepts behind it.
```

要告诉 **Hugo-theme-learn** 将页面视为一个章节，请在页面的前端设置 `chapter=true`。

**默认** 页面是任何其他内容页面。

![默认页面](/cont/pages/images/pages-default.png?width=50pc)

```toml
+++
title = "Installation"
weight = 15
+++
```

以下步骤可帮助您初始化您的新网站。如果你根本不认识 Hugo ，我们强烈建议你按照这个[伟大的初学者文档](https://gohugo.io/overview/quickstart/)进行学习。

## 创建你的项目

Hugo 提供了一个 `new` 命令来创建一个新的网站。

```
hugo new site <new_project>
```

**Hugo-theme-learn** 提供 [archetypes]({{< relref "cont/archetypes.zh.md" >}})  来帮助您创建这种页面。

## 前端配置

每个 Hugo 页面都必须在 *yaml*, *toml* or *json* 中定义一个 [Front Matter](https://gohugo.io/content/front-matter/)

**Hugo-theme-learn** 在Hugo上使用以下参数：

```toml
+++
＃内容表（toc）默认启用。将此参数设置为true将其禁用。
＃注意：Toc对于章节页面始终是禁用的
disableToc =“false”

＃如果设置，这将用于页面的菜单项（而不是`title`属性）
menuTitle =“”

＃菜单中的页面标题将以此HTML内容为前缀
pre =“”

＃菜单中的页面标题将由此HTML内容进行后缀
post =“”

＃将页面设置为一个章节，改变它的显示方式
chapter = false

＃通过设置为true来隐藏菜单项
隐藏= false

＃显示此页面修饰符的名称。如果设置，它将显示在页脚中。
LastModifierDisplayName =“”

＃此页面修改器的电子邮件。如果使用LastModifierDisplayName进行设置，它将显示在页脚中
LastModifierEmail =“”
+++
```

### 将图标添加到菜单项

在页面的前面，添加一个 `pre` 参数来在菜单标签之前插入任何HTML代码。下面的例子使用Github图标。

```toml
+++
title = "Github repo"
pre = "<i class='fa fa-github'></i> "
+++
```

![带图标的标题](/cont/pages/images/frontmatter-icon.png)

### 排列同级菜单/页面条目

雨果提供了一个[灵活的方式](https://gohugo.io/content/ordering/) 来处理您的网页的顺序。

最简单的方法是将`weight`参数设置为一个数字。

```toml
+++
title = "My page"
weight = 5
+++
```

### 为菜单条目使用自定义标题

默认情况下， **Hugo-theme-learn** 将为菜单项使用页面的`title`属性（或者定义的`linkTitle`）。

但是页面的标题必须是自己描述的，而菜单是一个层次结构。
我们为此添加了 `menuTitle` 参数：

例如（对于名为`content/install/linux.md`的页面）：

```toml
+++
title = "Install on Linux"
menuTitle = "Linux"
+++
```

## 主页

要配置您的主页，您基本上有三个选择：

1. 在`content`文件夹中创建一个`_index.md`文件，并用**Markdown内容填充文件**
2. 在`static`文件夹中创建一个`index.html`文件，并用**HTML内容填充文件**
3. 配置您的服务器自动将主页重定向到您的文档页面