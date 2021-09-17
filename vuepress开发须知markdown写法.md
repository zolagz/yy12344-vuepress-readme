```?
FIXME  2021/09/17 星期五

感觉 md/使用/注意事项 可以写一片汇总文章！这个是每一次开发前应该温故的知识点！
```


我记得好像： md 命名/不能有中文





[md/最后更新时间](https://vuepress.vuejs.org/zh/theme/default-theme-config.html#%E6%9C%80%E5%90%8E%E6%9B%B4%E6%96%B0%E6%97%B6%E9%97%B4)












---
## x、 md/网址链接

### md/网址链接/目录结构
每一个 md 文件，都代表一个页面。
每个目录下的 `README.md` 文件，代表一个路径的首页（相当于index.html）。




### md/网址链接/永久链接
具体查看: 
[永久链接/说明文档](https://vuepress.vuejs.org/zh/guide/permalinks.html)
[链接失效/link rot/wiki](https://en.wikipedia.org/wiki/Link_rot)

什么是 `永久链接` *--2021/09/17*  
什么时候要用 `永久链接`? *--2021/09/17*  (希望文章的链接更加灵活，而不是局限于vuepress的docs目录结构)







---
## x、 md/页面配置

### Front Matter
具体查看: 
[前言/Front Matter/说明文档](https://vuepress.vuejs.org/zh/guide/frontmatter.html) *作用：`html页面head配置`/`SEO(TKD)`*

[gray-matter/处理md顶部的yaml](https://github.com/jonschlinkert/gray-matter)
[YAML front matter](https://jekyllrb.com/docs/frontmatter/)


`Front Matter` 是什么？ *--2021/09/17* 
- 中文翻译： `前言`
- 作用/预定义变量/页面配置(SEO)
- 作用/默认主题的预定义变量(侧边栏/上下篇链接/搜索)

[vuepress示例md顶部yaml详细版](./vuepress示例md顶部yaml详细版.md)












---
## x、 md/vue组件
具体查看: [md中使用Vue/说明文档](https://vuepress.vuejs.org/zh/guide/using-vue.html)

### vuepress/内置的组件
``` shell
OutboundLink    图标组件(表示/外部链接)
ClientOnly      容器组件(包裹/仅在客户端渲染的vue组件)
Content         布局组件(<Content/>)
Badge           徽章组件(<Badge text="beta" type="warning"/>)
```

### md/vue组件/使用
md 中怎么使用 vue 组件文件？
md 中可以写 vue 组件的标签

*导入组件/要全局导入组件吗？--2021/09/17*  
``` shell
# 场景: 只想在当前页面应用一些 JavaScript 或者 CSS

# 内联脚本渲染
你可以直接在 Markdown 文件中使用原生的 <script> 或者 <style> 标签，
它们将会从编译后的 HTML 文件中提取出来，
并作为生成的 Vue 单文件组件的 <script> 和 <style> 标签。
```

#### md/vue组件/使用/插槽
具体查看: [Markdown 插槽](https://vuepress.vuejs.org/zh/guide/markdown-slot.html) 
啥时候要用 `Markdown 插槽` ？*--2021/09/17*  

vuepress 和 Vue 本身提供的 slot 机制不太相同
- `slot 内容`外层自动包裹一个 `div`
- `div` 会有自动的 class="`content` `_slotName`"
- `_slotName` 需要唯一

#### md/vue组件/使用/md标题中
```?
FIXME  2021/09/17 星期五

待思考
```
*标题中使用组件，对vuepress的侧边栏和文档标题产生什么影响？--2021/09/17*  

[使用组件/在标题中使用组件](https://vuepress.vuejs.org/zh/guide/using-vue.html#%E4%BD%BF%E7%94%A8%E7%BB%84%E4%BB%B6)


#### md/vue组件/使用/组件库
so-ui的文档是怎么生成的？在markdown中使用demo







---
## md/style和script

```?
FIXME  2021/09/17 星期五

具体怎么用呢？
```


md 中怎么使用 style 和 script ？
*可以在md中添加style？--2021/09/17*  
[使用组件/使用预处理器/sass](https://vuepress.vuejs.org/zh/guide/using-vue.html#%E4%BD%BF%E7%94%A8%E7%BB%84%E4%BB%B6)



更多查看: [vuepress/md/自定义样式](./vuepress开发高级自定义样式.md)








---
## x、 md/获取变量

###  md/获取变量/全局计算属性
具体查看: 
[vuepress/md/网站的元数据/说明文档](https://vuepress.vuejs.org/zh/theme/writing-a-theme.html#网站和页面的元数据) 
[vuepress/全局计算属性/说明文档](https://vuepress.vuejs.org/zh/guide/global-computed.html)*

每个md文件，可以获取到如下变量
`$route`
`$router`
`$site`
`$page`
`$frontmatter` = `$page.frontmatter` 当前页面头部 yaml 变量
`$lang` 当前页面的语言
`$localePath` 当前页面的 locale 路径前缀，默认值为 /
`$title` 当前页面的 `<title>` 标签的值
`$description` 用于当前页面的 `<meta name="description" content="...">` 的 content 值
`$themeConfig` 即 `siteConfig.themeConfig`




### 元数据???

```?
FIXME  2021/09/17 星期五

啥是 元数据 ？
```

普通数据类型的元数据 (frontmatter 中定义)
复杂元数据 

``` shell
# 下面这段化理解起来/难
Markdown 文件是元数据（页面内容、配置等）的提供者，而布局组件负责消费他们。
我们可以通过 frontmatter 来定义一些普通数据类型的元数据，
但对于 Markdown / HTML 这种涉及到编译前后差异的复杂元数据，frontmatter 却无能能力。
```






---
## x、 md/导入代码段
具体查看: [导入代码段/说明文档](https://vuepress.vuejs.org/zh/guide/markdown.html#%E5%AF%BC%E5%85%A5%E4%BB%A3%E7%A0%81%E6%AE%B5)

`导入代码段` 好高级的样子，有机会试试～ *--2021/09/17* 











---
## x、 md/块级容器

具体查看: 
[Escaping/v-pre/说明文档](https://vuepress.vuejs.org/zh/guide/using-vue.html#escaping)
[插件/vuepress-plugin-container/自定义容器](https://vuepress.github.io/plugins/container/) *类似代码块的自定义容器*