```?
FIXME  2021/09/17 星期五

应该先了解一下都有什么插件吗？
还是在开发中按需去寻找？
```

### 插件/官方

[官网](https://vuepress.vuejs.org/zh/plugin/)

- active-header-links 页面滚动时自动激活侧边栏链接的插件
- back-to-top
- blog
  - 分类、分页、客户端API
- google-analytics
- last-updated
  - 默认主题自带
  - 自定义时，可以用 $page.lastUpdated 访问时间字符串
- medium-zoom
- nprogress
- pwa
- register-components  在这个目录下的所有组件将会被注册为全局组件
- search


## 插件/原理
具体查看: [vuepress/插件/说明文档](https://vuepress.vuejs.org/zh/plugin/)

文章中提到很多插件
[插件/vuepress-plugin-clean-urls/定制/网站路径](https://vuepress.github.io/plugins/clean-urls/) *设置url路径访问规则*  
[插件/vuepress-plugin-container/自定义容器](https://vuepress.github.io/plugins/container/) *类似代码块的自定义容器*

[Prism/代码块/语法高亮](https://prismjs.com/) *`原理`[代码块/合法/类型](https://prismjs.com/#languages-list)* 

[markdown-it/md扩展&渲染](https://github.com/markdown-it/markdown-it) *`原理`*




## 插件/开发问题
注意新添加的插件，需要重新 run 才能看到效果
- 图片缩放 @vuepress/plugin-medium-zoom
- globalUIComponents 用于注册全局组件，在 content 中。

然后，再说说再开发过程中遇到的问题。


