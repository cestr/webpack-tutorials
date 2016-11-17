上接[`01-welcome-4`](/01-welcome-4 "welcome") 1.5 BINDING LOADERS

目录结构说明

```
01-welcome-5
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
* 如何安装webpack
* 如何使用webpack
* 如何使用加载器
* 如何使用开发服务器

---------------------------------------

续
##1.6 A CONFIG FILE

We want to move the config options into a config file:

add `webpack.config.js`

```js
module.exports = {
    entry: "./entry.js",
    output: {
        path: __dirname,
        filename: "bundle.js"
    },
    module: {
        loaders: [
            {
                test: /\.css$/,
                loader: "style!css"
            }
        ]
    }
};
```

Now we can just run:

```shell
webpack
```

to compile:

```shell
Version: webpack 1.13.1
Time: 528ms
    Asset     Size  Chunks             Chunk Names
bundle.js  11.8 kB       0  [emitted]  main
   [0] ./entry.js 67 bytes {0} [built]
   [5] ./content.js 43 bytes {0} [built]
    + 4 hidden modules
```

>The webpack command-line will try to load the file `webpack.config.js` in the current directory.

---------------

next [`01-welcome-6`](/01-welcome-6 "welcome")
