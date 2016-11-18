上接[`01-welcome-5`](/01-welcome-5 "welcome") 1.6 A CONFIG FILE

目录结构说明

```
01-welcome-6
├─bundle.js  # 编译文件, 无需手动创建
├─content.js # 无需修改
├─entry.js   # 无需修改    
├─index.html # 无需修改
├─README.MD  # doc
├─style.css  # 无需修改
├─webpack.config.js #新增文件
```

这个小教程将引导您完成一个简单的例子。
你将学习:
* [x] 如何安装webpack
* [x] 如何使用webpack
* [x] 如何使用加载器
* [x] 如何使用开发服务器

---------------------------------------

续
## 1.7 A PRETTIER OUTPUT（人性化输出）

If the project grows the compilation may take a bit longer. So we want to display some kind of progress bar. And we want colors…
（如果项目编译可能需要很长一段时间。因此我们希望显示进度条。和我们想要的颜色…）

We can achieve this with
（我们可以这样实现）

```shell
webpack --progress --colors
```

## 1.8 WATCH MODE（观察模式）

We don’t want to manually recompile after every change…
（每次修改文件后不需要手动编译...）

```shell
webpack --progress --colors --watch
```

Webpack can cache unchanged modules and output files between compilations.

> When using watch mode, webpack installs file watchers to all files, which were used in the compilation process. If any change is detected, it’ll run the compilation again. When caching is enabled, webpack keeps each module in memory and will reuse it if it isn’t changed.

## 1.9 DEVELOPMENT SERVER（开发服务器）
The development server is even better.

```shell
npm install webpack-dev-server -g
```

```shell
webpack-dev-server --progress --colors
```

* * *

> 也可以把命令行写入`package.json`文件中

修改`package.json`文件：

```json
  // 上文省略...
  "scripts": {
    "dev": "webpack-dev-server --progress --colors"
  },
  // 下文省略...
```

然后命令行运行：

```shell
npm run dev
```

等价

```shell
webpack-dev-server --progress --colors
```
* * *

This binds a small express server on localhost:8080 which serves your static assets as well as the bundle (compiled automatically). It automatically updates the browser page when a bundle is recompiled (SockJS). Open [`http://localhost:8080/webpack-dev-server/`](http://localhost:8080/webpack-dev-server/ "DEVELOPMENT SERVER") in your browser.

>The dev server uses webpack’s watch mode. It also prevents webpack from emitting the resulting files to disk. Instead it keeps and serves the resulting files from memory.
