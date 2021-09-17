## enhanceApp 应用配置文件
具体查看: [应用级别的配置/enhanceApp/说明文档](https://vuepress.vuejs.org/zh/guide/basic-config.html#%E5%BA%94%E7%94%A8%E7%BA%A7%E5%88%AB%E7%9A%84%E9%85%8D%E7%BD%AE)
`enhanceApp.js` 客户端的应用增强/应用级别的配置

``` JS
// enhanceApp.js : 应用级别的配置，返回: 钩子函数

// 钩子函数/参数 : 应用级别属性的对象
// 钩子函数/支持/异步函数
export default ({
  Vue, // VuePress 正在使用的 Vue 构造函数
  options, // 附加到根实例的一些选项
  router, // 当前应用的路由实例
  siteData, // 站点元数据
  isServer // 当前应用配置是处于 服务端渲染 或 客户端
}) => {
  /* 做一些其他的应用级别的优化，比如：
        Vue 插件
        注册全局组件 (第三方的)
        路由钩子
   */
}
```
[插件 API 中的 enhanceApp](https://vuepress.vuejs.org/zh/plugin/option-api.html#enhanceappfiles) *还没有看--2021/09/17*  