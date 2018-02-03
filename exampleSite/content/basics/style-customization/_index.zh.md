---
date: 2016-04-09T16:50:16+02:00
title: 风格定制
weight: 25
---

**Hugo-theme-learn** 通过定义多个[偏好](https://gohugo.io/templates/partials/)构建为尽可能可配置。

在 `themes/hugo-theme-learn/layouts/partials/` 中，你会发现为这个主题定义的所有部分。如果您需要覆盖某些内容，请不要直接更改代码。而不是[按照这个页面](https://gohugo.io/themes/customizing/)。您将在本地项目的`layouts/partials`文件夹中创建一个新的部分。这部分将具有优先权。

这个主题定义了以下部分：

- **header**：内容页面的标题（包含面包屑）。 **不意味着被覆盖**
- **custom-header**：在页面自定义标题。意味着在添加CSS导入时被覆盖。不要忘记在你的文件中包含`style` HTML标签指令
- **footer**：内容页面的页脚（包含箭头）。 **不意味着被覆盖**
- **custom-footer**：页面中的自定义页脚。意味着在添加Javacript时被覆盖。不要忘记在你的文件中包含`javascript` HTML标签指令
- **favicon**：the favicon
- **logo**：左上角的标志。
- **meta**：HTML元标记，如果你想改变默认行为
- **menu**：左侧菜单。 **不意味着被覆盖**
- **menu-footer**：左侧菜单的页脚
- **search**：搜索框
- **toc**：目录

## 更改logo

在`layouts/partials/`中创建一个名为`logo.html`新文件。然后写你想要的任何HTML。
您可以使用`img` HTML标记并引用在 *static* 文件夹下创建的图像，或者可以粘贴SVG定义！

{{% notice note %}}
logo的大小将自动适应
{{% /notice %}}

## 更改favicon

如果你的图标是PNG，只需把你的图像放在你的本地 `static/images/` 文件夹中，并命名为`favicon.png`

如果您需要更改此默认行为，请在`layouts/partials/`中创建一个名为`favicon.html`新文件。然后写这样的东西：

```html
<link rel="shortcut icon" href="/images/favicon.png" type="image/x-icon" />
```

## 更改默认颜色{＃theme-variant}

**Hugo Learn theme** 让你选择3原生的色彩方案变种，但随时添加一个！默认配色方案基于[Grav Learn Theme]（https://learn.getgrav.org/）。

### 红色的变种

```toml
[params]
  # Change default color scheme with a variant one. Can be "red", "blue", "green".
  themeVariant = "red"
```

![Red variant](/basics/style-customization/images/red-variant.png?width=60pc)

### 蓝色变种

```toml
[params]
  # Change default color scheme with a variant one. Can be "red", "blue", "green".
  themeVariant = "blue"
```

![Blue variant](/basics/style-customization/images/blue-variant.png?width=60pc)

### 绿色变种

```toml
[params]
  # Change default color scheme with a variant one. Can be "red", "blue", "green".
  themeVariant = "green"
```

### '你的'变种

首先，在本地`static/css`文件夹创建一个新的以`theme`为前缀的CSS文件(例如_mine_主题`static/css/theme-mine.css`)。复制以下内容并在CSS变量中修改颜色。

```css

:root{
    
    --MAIN-TEXT-color:#323232; /* Color of text by default */
    --MAIN-TITLES-TEXT-color: #5e5e5e; /* Color of titles h2-h3-h4-h5 */
    --MAIN-LINK-color:#1C90F3; /* Color of links */
    --MAIN-LINK-HOVER-color:#167ad0; /* Color of hovered links */
    --MAIN-ANCHOR-color: #1C90F3; /* color of anchors on titles */

    --MENU-HEADER-BG-color:#1C90F3; /* Background color of menu header */
    --MENU-HEADER-BORDER-color:#33a1ff; /*Color of menu header border */ 

    --MENU-SEARCH-BG-color:#167ad0; /* Search field background color (by default borders + icons) */
    --MENU-SEARCH-BOX-color: #33a1ff; /* Override search field border color */
    --MENU-SEARCH-BOX-ICONS-color: #a1d2fd; /* Override search field icons color */

    --MENU-SECTIONS-ACTIVE-BG-color:#20272b; /* Background color of the active section and its childs */
    --MENU-SECTIONS-BG-color:#252c31; /* Background color of other sections */
    --MENU-SECTIONS-LINK-color: #ccc; /* Color of links in menu */
    --MENU-SECTIONS-LINK-HOVER-color: #e6e6e6;  /* Color of links in menu, when hovered */
    --MENU-SECTION-ACTIVE-CATEGORY-color: #777; /* Color of active category text */
    --MENU-SECTION-ACTIVE-CATEGORY-BG-color: #fff; /* Color of background for the active category (only) */

    --MENU-VISITED-color: #33a1ff; /* Color of 'page visited' icons in menu */
    --MENU-SECTION-HR-color: #20272b; /* Color of <hr> separator in menu */
    
}

body {
    color: var(--MAIN-TEXT-color) !important;
}

textarea:focus, input[type="email"]:focus, input[type="number"]:focus, input[type="password"]:focus, input[type="search"]:focus, input[type="tel"]:focus, input[type="text"]:focus, input[type="url"]:focus, input[type="color"]:focus, input[type="date"]:focus, input[type="datetime"]:focus, input[type="datetime-local"]:focus, input[type="month"]:focus, input[type="time"]:focus, input[type="week"]:focus, select[multiple=multiple]:focus {
    border-color: none;
    box-shadow: none;
}

h2, h3, h4, h5 {
    color: var(--MAIN-TITLES-TEXT-color) !important;
}

a {
    color: var(--MAIN-LINK-color);
}

.anchor {
    color: var(--MAIN-ANCHOR-color);
}

a:hover {
    color: var(--MAIN-LINK-HOVER-color);
}

#sidebar ul li.visited > a .read-icon {
	color: var(--MENU-VISITED-color);
}

#body a.highlight:after {
    display: block;
    content: "";
    height: 1px;
    width: 0%;
    -webkit-transition: width 0.5s ease;
    -moz-transition: width 0.5s ease;
    -ms-transition: width 0.5s ease;
    transition: width 0.5s ease;
    background-color: var(--MAIN-LINK-HOVER-color);
}
#sidebar {
	background-color: var(--MENU-SECTIONS-BG-color);
}
#sidebar #header-wrapper {
    background: var(--MENU-HEADER-BG-color);
    color: var(--MENU-SEARCH-BOX-color);
    border-color: var(--MENU-HEADER-BORDER-color);
}
#sidebar .searchbox {
	border-color: var(--MENU-SEARCH-BOX-color);
    background: var(--MENU-SEARCH-BG-color);
}
#sidebar ul.topics > li.parent, #sidebar ul.topics > li.active {
    background: var(--MENU-SECTIONS-ACTIVE-BG-color);
}
#sidebar .searchbox * {
    color: var(--MENU-SEARCH-BOX-ICONS-color);
}

#sidebar a {
    color: var(--MENU-SECTIONS-LINK-color);
}

#sidebar a:hover {
    color: var(--MENU-SECTIONS-LINK-HOVER-color);
}

#sidebar ul li.active > a {
    background: var(--MENU-SECTION-ACTIVE-CATEGORY-BG-color);
    color: var(--MENU-SECTION-ACTIVE-CATEGORY-color) !important;
}

#sidebar hr {
    border-color: var(--MENU-SECTION-HR-color);
}
```
然后，使用自定义主题文件的名称设置`themeVariant`值。

```toml
[params]
  # Change default color scheme with a variant one. Can be "red", "blue", "green".
  themeVariant = "mine"
```
