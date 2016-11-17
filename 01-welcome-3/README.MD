上接[`01-welcome-2`](/01-welcome "welcome") 1.3 SECOND FILE

目录结构说明

```
01-welcome-3
├─bundle.js  # 编译文件, 无需手动创建
├─content.js # 无需修改
├─entry.js   # 修改文件    
├─index.html # 无需修改
├─README.MD  # doc
├─style.css  # 新增文件
```

这个小教程将引导您完成一个简单的例子。
你将学习:
* 如何安装webpack
* 如何使用webpack
* 如何使用加载器
* 如何使用开发服务器

---------------------------------------

续
##1.4 THE FIRST LOADER

We want to add a css file to our application.

webpack can only handle JavaScript natively, so we need the `css-loader` to process CSS files. We also need the `style-loader` to apply the styles in the CSS file.

Run `npm install css-loader style-loader` to install the loaders. (They need to be installed locally, without `-g`) This will create a `node_modules` folder for you, in which the loaders will live.

Let’s use them:

add `style.css`

```css
body {
    background: yellow;
}
```

update `entry.js`

```javascript
//document.write("It works."); // or delete
require("!style!css!./style.css"); // new line
document.write(require("./content.js"));
```
And recompile with:

```shell
$ webpack ./entry.js bundle.js
```
Recompile and update your browser to see your application with yellow background.

<a href="https://cestr.github.io/webpack-tutorials/01-welcome-3/" "index.html demo for welcome-3" target="_blank">`index.html`</a>

---------------

next [`01-welcome-4`](/01-welcome-4 "welcome")
