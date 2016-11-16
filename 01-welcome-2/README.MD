上接[`01-welcome`](https://github.com/cestr/webpack-tutorials/tree/master/01-welcome "welcome") 1.2

目录结构说明

```
01-welcome-2
├─bundle.js  # 编译文件, 无需手动创建
├─content.js # 新增文件
├─entry.js   # 修改文件    
├─index.html # 修改文件
```

这个小教程将引导您完成一个简单的例子。
你将学习:
* 如何安装webpack
* 如何使用webpack
* 如何使用加载器
* 如何使用开发服务器

---------------------------------------

续
##1.3 SECOND FILE

Next, we will move some code into an extra file.

add `content.js`

```js
module.exports = "It works from content.js.";
```

update `entry.js`

```javascript
//document.write("It works."); // or delete

document.write(require("./content.js"));
```
And recompile with:

```shell
$ webpack ./entry.js bundle.js
```

Update your browser window and you should see the text `It works from content.js.`. 

<a href="https://cestr.github.io/webpack-tutorials/01-welcome-2/" "index.html demo for welcome-2" target="_blank">`index.html`</a>

```
webpack将分析的入口文件依赖其他文件。这些文件(称为模块)都包含在`bundle.js`中。webpack会给每个模块一个惟一的id,id保存所有模块访问的`bundle.js`文件。只有输入模块是在启动时执行的。一个小的运行时提供了需要函数和在需要时执行的依赖关系。
```