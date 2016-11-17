#1. WELCOME

目录结构说明

```
01-welcome
├─bundle.js  # 编译文件, 无需手动创建
├─entry.js   # 新增文件
├─index.html # 新增文件
    
```

这个小教程将引导您完成一个简单的例子

你将学习到如下技能:
* [x]如何安装webpack
* [x]如何使用webpack
* []如何使用加载器
* []如何使用开发服务器

---------------------------------------

##1.1 全局安装webpack

```shell
npm install webpack -g
```
    全局安装使得webpack命令可用

##1.2 js编译

在一个空目录（`01-welocme-1`）里创建如下文件：

添加`entry.js`

```js
document.write("It works.");
```

添加`index.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>WELCOME</title>
</head>
<body>
    <script type="text/javascript" src="bundle.js" charset="UTF-8"></script>
</body>
</html>    
``` 
接下来在（`01-welocme-1`里打开）终端执行:

```shell
webpack ./entry.js bundle.js
```

它将编译文件,并创建一个包文件(`bundle.js`)

如果成功它显示是这样的:

```shell
Version: webpack 1.13.3
Time: 119ms
    Asset     Size  Chunks             Chunk Names
bundle.js  1.42 kB       0  [emitted]  main
   [0] ./entry.js 28 bytes {0} [built]
```

在浏览器打开目录中的 [`index.html`](https://cestr.github.io/webpack-tutorials/01-welcome-1/ "这是一个例子") 文件. 将显示 `It works.`

---------------

next [`01-welcome-2`](/01-welcome-2 "welcome")
