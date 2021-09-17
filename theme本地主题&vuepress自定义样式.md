具体查看: 
[主题/theme/说明文档](https://vuepress.vuejs.org/zh/theme/)
[默认主题配置/说明文档](https://vuepress.vuejs.org/zh/theme/default-theme-config.html)
[自定义主题/说明文档](https://vuepress.vuejs.org/zh/theme/)

通过上面的说明文档，就可以配置主题了！
- 导航栏: 页面标题、搜索框、 导航栏链接、多语言切换、仓库链接
- 侧边栏: 自动生成侧边栏、多侧边栏、无侧边栏
- 搜索框
- 最后更新时间
- 上/下一篇链接
- 个别页面设置自定义样式及布局

技巧： 看文档配置多试试就会了。



```?
FIXME  2021/09/17 星期五

侧边栏 displayAllHeaders 的效果没有看出来？

如何自定义主题？待看
```










---
## x、 侧边栏

一个文件夹中有多个文件，如何设置在一个侧边栏中？
侧边栏可以是数组对象表示有多个分组，侧边栏是对象表示有多个侧边栏。





---
## x、修改默认页面

### 修改默认页面/404
404页面自定义修改，新建 theme/layouts/NotFound.vue，然后重启服务，就可以看到自定义的404页面了。
emm...404的页面是变了，但是别的页面也全都变化了...
因为这个操作等于使用了一个新的主题，该主题应该继承一下默认主题，所以需要新建 theme/index.js。
``` JS
module.exports = {
  extend: '@vuepress/theme-default'
}
```
但是，发现 本地 / github.io 访问一个不存在的路径，可以正常显示404页面，不是重定向，而是在当前页面直接显示。
线上展示的却是 404 Not Found | nginx，应该是直接按照资源路径寻找没有找到，但是 vue 的 404 没有生效的感觉，需要配置 nginx 404 时指向 404.html。

备注：url没有变化，可能是访问的不存在的资源时，直接返回了 404.html 的内容。

<img src="https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c2685eb9611a4f5e87a2647bcd771efd~tplv-k3u1fbpfcp-zoom-1.image" style="display:block;width: 600px;" />











---
## x、 首页/自定义样式
如何自定义首页样式？ *--2021/09/17* 

参考微信官方文档：https://developers.weixin.qq.com/doc/









---
## x、 网站icon
如何自定义网站的标签页icon？ *--2021/09/17* 
[设置icon](https://vuepress.vuejs.org/zh/config/#head)










---
## x、 导航栏

你可以通过 [开发主题/网站的元数据](https://vuepress.vuejs.org/zh/theme/writing-a-theme.html#%E7%BD%91%E7%AB%99%E5%92%8C%E9%A1%B5%E9%9D%A2%E7%9A%84%E5%85%83%E6%95%B0%E6%8D%AE) 来对用户开放一些自定义主题的配置 -- 比如指定目录或者页面的顺序，你也可以结合 $site.pages 来动态地构建导航链接。



### 导航栏/隐藏

1、首页没有显示导航栏

```?
FIXME  2021/09/17 星期五

2、下滑导航栏自动隐藏 ？ (微信文档)
```
theme
自定义导航栏（navbar）、 侧边栏（sidebar）和 首页（homepage） 等













---
## x、 md/自定义样式
```?
FIXME  2021/09/17 星期五

怎么自定义样式？
```