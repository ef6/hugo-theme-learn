---
title: 原型
weight: 10
---


使用`hugo new [relative new content path]`命令，可以自动设置日期和标题的内容文件。虽然这是一个值得欢迎的功能，但主动编写者需要更多：[原型](https://gohugo.io/content/archetypes/)。

它是预先配置的具有默认前端事件的框架页面。请参阅文档了解页面的类型以了解其差异。

## 章节 {＃archetypes-chapter}

要创建章节页面，请运行以下命令

```
hugo new --kind chapter <name>/_index.md
```

它将创建一个预定义的页面：

```markdown
+++
title = "{{ replace .TranslationBaseName "-" " " | title }}"
date = {{ .Date }}
weight = 5
chapter = true
pre = "<b>X. </b>"
+++

### Chapter X

# Some Chapter title

Lorem Ipsum.
```


## 默认

要创建默认页面，请运行以下任一命令

```
# Either
hugo new <chapter>/<name>/_index.md
# Or
hugo new <chapter>/<name>.md
```

它将创建一个预定义的页面：

```markdown
+++
title = "{{ replace .TranslationBaseName "-" " " | title }}"
date =  {{ .Date }}
weight = 5
+++

Lorem Ipsum.
```