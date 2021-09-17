
## md顶部yaml

md 顶部的 yaml 详细示例如下：
``` yaml
---
# 1、 预定义变量
# (页面head配置吗？) *--2021/09/17*

# 页面标题前缀 / {String} / 默认： h1_title(md的h1) | siteConfig.title(网站标题)
title: 页面标题前缀

# 页面语言 / {String} / 默认： en-US
# (怎么觉得不对，应该是全局的 lang 吧？) *--2021/09/17*
lang: zh-CN

# 页面描述 / {String} / 默认： siteConfig.description
description: 页面描述

# 页面布局组件 / {String} / 默认： Layout
# (怎么自定义布局？怎么指定布局？) *--2021/09/17*
# layout: ?

# 页面永久链接 / {String} / 默认： siteConfig.permalink
# 用于重定向
permalink: /hello-world


# 页面标题 / {String} / 默认： `${page.title} | ${siteConfig.title}`
# metaTitle 优先级高于 `页面标题前缀title + 网站title`
metaTitle: 页面标题

# 页面新增meta标签 / {Array} / 默认： undefined
meta:
  - name: description
    content: 描述少于160字
  - name: keywords
    content: 关键词1,关键词少于3个,用英文逗号分割


# 2、 默认主题的预定义变量
# 导航栏 / {Boolean} / 默认： undefined
# navbar 值 false 时，表示不显示导航栏
navbar: false

# 侧边栏 / {Boolean|String(可选['auto'])} / 默认：undefined
# sidebar: ?

# 上一篇链接 / {Boolean|String} / 默认： undefined
# prev: ?

# 下一篇链接 / {Boolean|String} / 默认： undefined
# next: ?

# 内置搜索 / {Boolean} / 默认： undefined
# (啥时候用？) *--2021/09/17*
# search: ?


# 搜索标签 / {Array} / 默认： undefined
# (tags实现了什么？怎么自动添加tag？什么情况需要添加tag（比如：sl和mp，有必要添加吗？）) *--2021/09/17*
# tags: ?

# 3、自定义变量
---
```

注意 yaml 的语法规则: 
- 变量(没有分号)
- 值/字符串(没有引号)
- 值/数组(`tag`和`-`结合使用)


```?
FIXME  2021/09/17 星期五

description 和 meta.description 有什么区别？
```



具体查看: [md顶部的yaml规则/Front Matter/说明文档](https://vuepress.vuejs.org/zh/guide/frontmatter.html)

```?
FIXME  2021/09/17 星期五

明明已经设置了 lang="zh-CN",
为什么开发时 chrome 浏览器会自动弹出翻译。
看到控制台加载的 渲染的时候 html lang="en" ... 

1、先 选择 一律不翻译本网站
2、右键 还可 选择 翻译
```