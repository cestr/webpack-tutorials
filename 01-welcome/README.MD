#1. WELCOME

目录结构说明

```
01-welcome
    |-entry.js # 新增文件
    |-index.html # 新增文件
    |-bundle.js # 编译文件
```

这个小教程将引导您完成一个简单的例子。
你将学习:
* 如何安装webpack
* 如何使用webpack
* 如何使用加载器
* 如何使用开发服务器

##1.1 全局安装webpack

```shell
$ npm install webpack -g
```
    全局安装使得webpack命令可用。

##1.2 js编译

在一个空目录里创建如下文件：
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
接写来终端执行:

```shell
$ webpack ./entry.js bundle.js
```