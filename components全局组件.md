自定义组件名/命名规则: `kebab-case连接符` / `PascalCase大驼峰`

``` shell
命名不规范，自定义组件名将会被视为一个内联元素，并被包裹在一个 <p> 标签中，这将会导致 HTML 渲染紊乱(服务端渲染异常)，因为 HTML 标准规定， <p> 标签中不允许放置任何块级元素。
```

## 开发须知

### window 的限制
vue 组件中，如果需要访问 window ，只能在 created 生命周期之后执行。
*动态导入/需要访问window的库*

### 动态注册组件
```?
FIXME  2021/09/17 星期五

不理解
```
``` shell
如果你的模块通过 export default 导出一个 Vue 组件，那么你可以动态注册它：
```
*[这个](https://vuepress.vuejs.org/zh/guide/using-vue.html#%E6%B5%8F%E8%A7%88%E5%99%A8%E7%9A%84-api-%E8%AE%BF%E9%97%AE%E9%99%90%E5%88%B6)不是很理解*




## md 中使用 vue
```?
FIXME  2021/09/17 星期五

这个和  vuepress开发须知markdown写法.md 有些重合。 要思考一下
```

直接在 docs/.vuepress/components 中创建新建组件， 如 conact.vue 。然后，组件会自动被注册。

若要在 App.vue 中使用，则在 config.js 中声明为全局UI，会自动注入到 content 中。
``` JS
  globalUIComponents: [
    'conact'
  ],
```

如果要 markdown 中单独使用，就直接写入标签就好。
``` JS
## 组件conact
<conact>内容{{1+1}}</conact>
```
这里还涉及到插槽等，[详细查看](https://vuepress.vuejs.org/zh/guide/using-vue.html)。