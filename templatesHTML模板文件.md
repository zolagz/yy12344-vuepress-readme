docs/.vuepress/templates/dev.html: 用于开发环境的 HTML 模板文件。
docs/.vuepress/templates/ssr.html: 构建时基于 Vue SSR 的 HTML 模板文件。

*知识盲区--2021/09/17*  

当你想要去自定义 `templates/ssr.html` 或 `templates/dev.html` 时，最好基于 [默认的模板文件](https://github.com/vuejs/vuepress/blob/master/packages/%40vuepress/core/lib/client/index.dev.html) (opens new window)来修改，否则可能会导致构建出错。