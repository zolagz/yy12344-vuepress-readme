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

### 侧边栏/路径

侧边栏，对应的路径写法，如下
``` JS
module.exports = {
  themeConfig: {
    sidebar: {
      '/sl/': [
        {
          title: '使用指南',
          path: '/sl/guide/', /* 对应文件 sl/guide/README.md */
          collapsable: true,
          sidebarDepth: 3,
          children: [
            // 分组/折叠面板/显示项
            '/sl/guide/use', /* 对应文件 sl/guide/use.md */
            '/sl/guide/link', /* 对应文件 sl/guide/link.md */
          ]
        },
        {
          title: '插件应用',
          path: '/sl/plugin/',
        },
      ]
    }
  }
}
```
注意： 
1. README.md 类型的文件 path 需要用 / 结尾表示
2. 所有的文件路径需要写完整，不要相对 侧边栏key 去写 (有坑)

### 复杂的侧边栏示例

侧边栏 支持 多语言 每种语言都包含多个产品的文档 每个产品包含多个功能模块文档

语言
语言/产品
语言/产品/功能
语言/产品/功能/细化

``` JS
// .vuepress/config.js
module.exports = {

  // 自动显示所有页面的标题链接
  displayAllHeaders: false, // 不自动

  themeConfig: {

    // 默认的语言/侧边栏/写在 themeConfig.sidebar 中
    sidebar: {
      // 产品/1
      'p1': [
        {
          title: '产品/1/功能/1',
          path: '/p1/f1/',  /* 对应文件 p1/f1/README.md */
          collapsable: true, /* 有点卡.... */
          sidebarDepth: 3, /* 显示所有页面的标题链接，层级 */
          children: [
            '/p1/f1/t1', /* 对应文件 p1/f1/t1.md */
            '/p1/f1/t2', /* 对应文件 p1/f1/t2.md */
          ]
        },
        {
          title: '产品/1/功能/2',
          path: '/p2/f2/',  /* 对应文件 p1/f2/README.md */
        }
      ],
      // 产品/2
      '/mp/': [
          {
            title: '产品/2/功能/1',
            path: '/p2/f1/',
          }
      ],
    }


    // 别的语言/侧边栏/写在 themeConfig.对应语言 中
    // 默认的语言/侧边栏/写在 themeConfig.对应语言.sidebar 中
    '/en/': {
      sidebar: {
        // 产品/2
        'p1': [
          {
            title: '产品/1/功能/1',
            path: '/en/p1/f1/',  /* 对应文件 en/p1/f1/README.md */
            collapsable: true,
            sidebarDepth: 3,
            children: [
              '/en/p1/f1/t1', /* 对应文件 en/p1/f1/t1.md */
              '/en/p1/f1/t2', /* 对应文件 en/p1/f1/t2.md */
            ]
          },
          {
            title: '产品/1/功能/2',
            path: '/en/p2/f2/',  /* 对应文件 en/p1/f2/README.md */
          }
        ],
        // 产品/2
        '/mp/': [
            {
              title: '产品/2/功能/1',
              path: '/en//p2/f1/',
            }
        ],
      }
    }
  }
}
```





---
## x、修改默认页面

### 修改默认页面/404
404页面自定义修改，新建 `.vuepress/theme/layouts/NotFound.vue`，然后重启服务，就可以看到自定义的404页面了。
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

有如下3中自定义样式的方法，他们有什么区别？
### 特定页面的自定义布局
`特定页面的自定义布局` : 使用默认主题，只是某个页面用自己的 vue
[特定页面的自定义布局](https://vuepress.vuejs.org/zh/theme/default-theme-config.html#%E7%89%B9%E5%AE%9A%E9%A1%B5%E9%9D%A2%E7%9A%84%E8%87%AA%E5%AE%9A%E4%B9%89%E5%B8%83%E5%B1%80)  

场景：自定义首页布局 `.vuepress/components/XmLayoutIndex.vue`

``` shell
# 在某个 md 中使用 XmLayoutIndex 布局
---
layout: XmLayoutIndex
---
```

### 主题的继承
`主题的继承` : 基于默认主题，自己写一整套主题
[主题的继承](https://vuepress.vuejs.org/zh/theme/inheritance.html)

场景：自定义每个页面的导航栏布局

``` JS
// .vuepress/theme/index.js
// 注意： 看到 vuepress 项目中有 `.vuepress/theme/index.js` ，内容如下，表示使用了继承默认主题的自定义主题哈～
export default {
  extend: '@vuepress/theme-default'
}
```

FIXME 可能需要安装相关插件 访问父级组件
[示例/主题的继承](https://github.com/vuejs/vuepress/tree/master/packages/%40vuepress/theme-vue)
[默认主题](https://github.com/vuejs/vuepress/tree/master/packages/%40vuepress/theme-default) *基于默认主题，自己写一整套主题，需要查看*




### 开发主题
`开发主题` : 自己写一整套主题
[开发主题](https://vuepress.vuejs.org/zh/theme/writing-a-theme.html)

场景：大佬...
