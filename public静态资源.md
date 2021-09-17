具体查看: [静态资源/public/说明文档](https://vuepress.vuejs.org/zh/guide/assets.html)

## 图片路径设置须知
注意：`图片的相对路径`受到 `网站的路径` 的影响，要使用 `$withBase` 去获取正确的路径，且 md,vue 文件都可以使用该函数。

``` JS
$withBase('/foo.png')
```

图片是不是直接网络地址更方便？



## public 静态资源

- 定义：(可选的) 静态资源目录。
- 常识：public 中的文件最终会被复制到生成的静态文件夹中。

Q：使用静态资源需要注意什么？
A：第一，尽量使用**相对路**径引用静态资源
A：第二，使用 `～` 明确表示**使用 webpack 的模块**

Q：如何设置路径别名？
A：如下代码所示。
``` JS
configureWebpack: {
  resolve: {
    alias: {
      '@alias': 'path/to/some/dir'
    }
  }
}
```