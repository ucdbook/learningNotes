### Webpack

webpack 是一个现代 JavaScript 应用程序的静态模块打包器\(module bundler\)

#### **它的功能：**

1. 通过loader、plugins等配置进行模块代码打包

2. 构建一个模块依赖关系图

3. 通过webpack-dev-server启动本地服务

#### **四个核心概念：**

**一、入口\(entry\):**

webpack 应该使用哪个模块，来作为构建其内部依赖图的开始。进入入口起点后，webpack 会找出有哪些模块和库是入口起点（直接和间接）依赖的。

**二、输出\(output\)**

属性告诉 webpack 在哪里输出它所创建的 bundles，以及如何命名这些文件，默认值为 ./dist。

**三、loader**

让 webpack 能够去处理那些非 JavaScript 文件（webpack 自身只理解 JavaScript）。loader 可以将所有类型的文件转换为 webpack 能够处理的有效模块，然后你就可以利用 webpack 的打包能力，对它们进行处理。

如：对ES6中浏览器还未支付的属生进行编译、把jsx语法编译成js语法、less编译成Css, 等...

**四、插件\(plugins\)**

loader 被用于转换某些类型的模块，而插件则可以用于执行范围更广的任务。插件的范围包括，从打包优化和压缩，一直到重新定义环境中的变量。插件接口功能极其强大，可以用来处理各种各样的任务。

中文文档：[https://www.webpackjs.com/concepts/](https://www.webpackjs.com/concepts/)

