## vuepress/自定义/配置
具体查看: [vuepress/基本配置](https://vuepress.vuejs.org/zh/guide/basic-config.html)
- vuepress/配置文件(config.js)
- vuepress/主题配置(theme)
- vuepress/应用级别配置(enhanceApp.js)


## vuepress 说明文档
根据官网/教学步骤/说明文档/汇总
[官网指南/vuepress/说明文档](https://vuepress.vuejs.org/zh/guide/)
[配置/config/说明文档](https://vuepress.vuejs.org/zh/config/)
[主题/theme](./theme/本地主题.md)
[静态资源/public](./public/静态资源.md)
[vuepress中markdown的使用&拓展/说明文档](https://vuepress.vuejs.org/zh/guide/markdown.html) *`重要` 一定要看！讲述了vuepress对`md的自动化处理`(router自动生成,路径访问重定向,md打包生成文件类型)，`md特殊语法规则`(emoji,自定义容器,代码块)*
[Vue/服务端渲染SSR/说明文档](https://ssr.vuejs.org/zh/) *(当年写nuxt时，怎么没有看到这个！相见恨晚)*
[md中使用Vue/说明文档](https://vuepress.vuejs.org/zh/guide/using-vue.html#%E6%B5%8F%E8%A7%88%E5%99%A8%E7%9A%84-api-%E8%AE%BF%E9%97%AE%E9%99%90%E5%88%B6) *看起来高级，用不到，但是应该知道*

[vuepress/国际化/多语言支持/说明文档](https://vuepress.vuejs.org/zh/guide/i18n.html)

[vuepress/部署/说明文档](https://vuepress.vuejs.org/zh/guide/deploy.html)

[vuepress/插件](https://vuepress.vuejs.org/zh/plugin/)

[vuepress/术语](https://vuepress.vuejs.org/zh/miscellaneous/glossary.html) *不知道从哪里进去*











---
## 开发技巧
如果有些问题你在 github.issues 中找不到，可以去 [stackoverflow](https://stackoverflow.com) 上带上关键字 vuepress 搜查。









---
## vueprees/原理
1、每一个 Markdown 文件将首先被编译成 HTML，
输出html原理： [markdown-it](https://github.com/markdown-it/markdown-it)

2、接着作为一个 Vue 组件传入 vue-loader (支持vue的 `{{ v }}` 写法)
```?
FIXME  2021/09/17 星期五

这里html怎么作为vue组件的？
```

VuePress 实现了一套针对 Markdown 的内容分发 API。通过这个特性，你可以将你的文档分割成多个片段，以便于在布局组件中灵活组合。 
[Markdown 插槽](https://vuepress.vuejs.org/zh/guide/markdown-slot.html) 










下面的忽略

---
## vueprees/介绍
> 我眼里的它：有直接开箱就用的`技术文档主题`，可以直接搭建自己的技术博客/说明文档

### 1、介绍
使用插件 [vue-press](https://vuepress.vuejs.org/zh/guide)，描述如下：
- 可以用来开发以内容为中心的静态网站
- 预渲染好HTML，加载性能好，对SEO（搜索引擎优化）友好。
- 页面是按需加载。
- 一个 VuePress 网站是一个由 Vue、Vue Router 和 webpack 驱动的单页应用。

### 2、特点/功能
- 内置的 Markdown 拓展
- 在 Markdown 中 使用 Vue
- Vue驱动的自定义主题系统
- 默认主题
- 博客主题
- Plugin

### 3、其他的 vue 构建工具
- nuxt：为构建应用程序而生的（多用于官网）
- Docsify / Docute：运行时驱动，对 SEO 不友好
- Hexo （多用于博客）
- GitBook （多用于静态说明文档）



## 暂存

- [vuepress 官网](https://vuepress.vuejs.org/zh/guide)
- [山月行.vuepress服务器搭建.2020/05/11](https://shanyue.tech/) 
- [搭建Vuepress博客/文档系统：搭建，PDF导出，SEO，自动编译，自动部署，域名，HTTPS，备案等](https://segmentfault.com/a/1190000020971477?utm_source=tag-newest)