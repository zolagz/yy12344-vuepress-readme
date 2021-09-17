## 自动化？？？
生成文件夹内所有md文件目录
- meta.json 文件智能生成
自己写一个`meta.js`文件，生成对应的侧边栏信息`meat.json`和首页`README.md`

之后补上代码

``` shell
node meta.js
```


## 打包配置
*写一下--2021/09/17*  

## 打包及部署

可以通过参数 `--dest` 自定义打包后的文件位置。[点击查看](https://vuepress.vuejs.org/zh/api/cli.html#build)



github.io

发布到：`https://<USERNAME>.github.io/`

1、新建一个仓库，名称必须是：`[你的GitHub名].github.io`

2、添加运行命令
``` JS
"scripts": {
  "deploy": "bash deploy.sh"
}
```

3、与package.json同级新建一个deploy.sh文件
``` shell
#!/usr/bin/env sh

# 确保脚本抛出遇到的错误
set -e

# 生成静态文件
npm run docs:build

# 进入生成的文件夹
cd docs/.vuepress/dist

git init
git add -A
git commit -m 'deploy'

# 如果发布到 https://<USERNAME>.github.io  填写你刚刚创建的仓库地址
git push -f https://github.com/NicCraver/niccraver.github.io.git master

cd -
```

4、执行 deploy.sh 打包上传
在 package.json 中添加脚本
``` JS
"deploy": "bash deploy.sh",
```

``` shell
 npm run deploy   
```


发布到: `https://<USERNAME>.github.io/` 仓库名称REPO

如果你打算发布到 `https://<USERNAME>.github.io/<REPO>/`（也就是说你的仓库在 `https://github.com/<USERNAME>/<REPO>`）

1、还是先要有 `[你的GitHub名].github.io` 仓库

2、设置 deploy.sh

``` shell
#!/usr/bin/env sh

# 确保脚本抛出遇到的错误
set -e

# 生成静态文件
npm run docs:build

# 进入生成的文件夹
cd docs/.vuepress/dist

git init
git add -A
git commit -m 'deploy'

# 如果发布到 https://<USERNAME>.github.io  填写你刚刚创建的仓库地址
# git push -f git@github.com:youyou12344/youyou12344.github.io.git master

# 如果发布到 https://<USERNAME>.github.io/<REPO>
git push -f git@github.com:youyou12344/vuepress-yy12344.git master:gh-pages

cd -
```

```!
注意： 必须是master:gh-pages，否则无法在仓库中选择GitHub pages
```

3、到路径对应的仓库，进入 settings 的 github pages 设置，选择对应展示分支 gh-pages

<img src="https://user-gold-cdn.xitu.io/2020/4/24/171a7d7c385eba02?w=847&h=731&f=png&s=95787" style="display:block;width: 600px;" />





