上接[`01-welcome-3`](/01-welcome-3 "welcome") 1.4 THE FIRST LOADER

目录结构说明

```
01-welcome-4
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
##1.5 BINDING LOADERS

We don’t want to write such long requires `require("!style!css!./style.css");`.

We can bind file extensions to loaders so we just need to write: `require("./style.css")`

update `entry.js`

```js
//require("!style!css!./style.css");  // remove
require("./style.css"); // add new

document.write(require("./content.js"));
```

Run the compilation with:

~~webpack ./entry.js bundle.js --module-bind 'css=style!css'~~

```shell
# window 环境需要使用双引号，否则会报错！
webpack ./entry.js bundle.js --module-bind "css=style!css"
```
> Some environments may require double quotes: –module-bind “css=style!css”

You should see the same result:

<a href="https://cestr.github.io/webpack-tutorials/01-welcome-4/" "index.html demo for welcome-3" target="_blank">`index.html`</a>

---------------

next [`01-welcome-5`](/01-welcome-5 "welcome")
