# node.js

1、安装

在公司中  node.js版本不能随便下，要根据项目的需求去下载，不然会导致项目运行不起来

2、安装结束后

node.js会在命令行（cmd）中多了两个命令

一个是 node   一个是 npm

node 运行js代码用的

npm           node package manage包管理工具 通过npm去下载各种依赖包(三方的一个插件、jQuery等等)

你可以理解成 npm 就是 软件管理

```` html
例如：比如说这里有一个index.html

你只要引用一下它   那他就可以用

<script src=".index.js"></script>

再比如 你想在node环境中运行一段js脚本

你可以这样写 

​			1.新建一个  index.js  文件 文件中写你需要的代码

​			2.在当前的js文件的cmd中输入 node index.js 回车

它就能运行！  
````

node.js的安装和node两条命令的作用：node  npm



3、node.js 和 web中的 js 的区别？

答：

1、规范不一样。

​	这里说的 JavaScript 遵循的是 ECMA规范

​	nodeJs 遵循的是CommonJs

``` js
JavaScript 的规范是 ecmascript  这种规范简称：es5、es6、包括现在的ECMA2022

​		那么ecmascript  的缩写：es；

​        现在市场上的es6 指的是：ECMA 2015 之后所有的规范 统称：ES6
```

## 初学者理解：

CommonJs 和 JavaScript的不一样的地方：语法上的不同

```js
# 语法上的不同：
// 比如：模块化   导入  和  导出
// JavaScript：import  export
// node.js中： 导出：module.exports
//			  导入: require
```

2作用不一样。

​		js  是在浏览器（web）中运行的

​	    node  js  是在非浏览器中运行的

​           这个东西告诉我们：

​				没有dom可言      为什么？   答：Dom是html中的东西  

​				没有Bom可言      为什么？   答：Bom是浏览器相关的东西

 			运行环境中都没有这些概念  

​			 那么nodeJs是什么？ 写后端的语言

​			后端能干什么？能写服务器，能访问数据库等

# 模块话是 nodejs 和 JavaScript 的区别？
``` js
// JavaScript   web中 的全局变量叫 window
// nade中  全局变量叫 global；
// 另一个区别是 node.js 中 自带很多个模块

```

---

vite 用的是基于nodejs环境来开发的   说明vite是运行在node中的

我们的项目用的是 vite + vue3 + ts 的一个技术栈

在启动项目时，地址是 localhost:5173

nodejs 中的http是创建服务器的

得出结论：vue3-cli 帮我们用了node中的http模块来创建了一个服务器

``` js
// 创建服务器
const http = require("http");


// req 的全称 == request
// req 中包含了哪些东西呢？ 指的就是 浏览器传过来的相关参数，全部都包含在了req中
// res 是服务端准备传给前端的 内容 及 相关http协议的设置
// res：response 其实叫 响应

const app = http.createServer((req, res) => {
    console.log(req.url)
    // end  是 结束，其实就是给前端发送的内容
    if (req.url == '/mine') {
        // 这里的 end 方法中的标签 在web开发中会自动给你转成html标签元素
        // 但是要是其他语言就不会  比如java   java是自动转成字符串
        
        // 但是如果有一天我们有个需求  这里呢 我就是要传一个字符串  那该怎么办？
        // 服务端去告诉浏览器 这是一个字符串，而不是一个页面
        // 那么如何告诉浏览器？
        // 为了解决这个问题
        // 浏览器就和服务端遵循了一个协议：这个协议叫做：http协议
        // http协议是做什么的？
        // 他就是告诉服务器 和 浏览器之间通讯的一个数据结构 到底是什么样子

        // res.end 是服务端数据 发送给前端
        // 'content-type':'text/html'  //! 这个的意思是：把内容用文本来解析  如果发现html 就解析成html
        // res.setHeader('Content-Type', 'text/plain');
        res.end('<h1>this is mine page</h1>');
    } else if (req.url == '/' || req.url == '/home') {
        res.end('this is home page');
    }
})

// nodejs 运行代码完成之后 代码就消失了
// 如果不用 listen  你的服务器就关闭了
// listen 是监听 
app.listen(3000, function () {
    console.log('服务器已经启动啦！哈哈哈哈！')
})
// 请求头中设置的相关参数都是 http中的配置   协议的数据结构
// request
// headers
// user-agents ：代表的是你用的是那种浏览器的内核，他通常使用兰判断你是手机端访问还是PC端 是微信还是支付宝  是火狐还是chrome还是IE
// Host 是前端访问的路由地址
// method 请求方法
//  response ： 响应体中常用的值
// content-type：‘text/html’
// content-type：'application/json'
```

# 路由映射

``` js
const http = require("http");
const fs = require('fs');

const app = http.createServer((req, res) => {
    if (req.url == '/mine') {
        // 'content-type':'text/html'  //! 这个的意思是：把内容用文本来解析  如果发现html 就解析成html
        // res.setHeader('Content-Type', 'text/plain');
        //? 需求: 如果用户访问的是 /mine 页面  我们就把 dist/mine.html 发给客户端
        // 1、如何拿到mine.html的内容
        // 2、
        //! fs 模块
        // FileStstem 文件操作系统 他可以用来对文件的增删改查

        fs.readFile('./dist/mine.html', (err, data) => {
            if (err) {
                res.end('404,没有此页面！');
            } else {
                res.end(data);
            }
        })
    } else if (req.url == '/' || req.url == '/home') {
        res.end('this is home page');
    }
})

app.listen(3000, function () {
    console.log('服务器已经启动啦！哈哈哈哈！')
})

// 请求头中设置的相关参数都是 http中的配置   协议的数据结构

// request
// headers
// user-agents ：代表的是你用的是那种浏览器的内核，他通常使用兰判断你是手机端访问还是PC端 是微信还是支付宝  是火狐还是chrome还是IE
// Host 是前端访问的路由地址
// method 请求方法
//  response ： 响应体中常用的值
// content-type：‘text/html’
// content-type：'application/json'

/**
 *! 创建了一个服务器
 *? 访问一个服务器  是如何访问的？
 *  一个服务器是一个ip地址
 * 访问一个服务的全路径为：
 * 协议 + 域名 + 端口号
 * 协议：http://
 * 域名：localhost  localhost => 指的是：当前设备的ip地址的简写
 * 端口号: 默认端口号是：80   数据库的默认端口号是：3306
 * 如果你的服务器端端口号是 80  则 这个端口号可以不写
 * 结合起来就是：http://localhost
 *! 你的服务器启动成功后，别人还是不可以使用 http://localhost:5173 来访问你的这个地址的
 *? 想让别人访问的话?
 * 需要你查询一下你的ip地址  然后把 localhost 替换成你的ip地址发给对方  那么他就可以访问了
 * 前提是 他连的网和你的网是同一个网  也就是 局域网才可以 外网不行
 * 
 * ? 端口号的作用是什么？
 * 如果没有端口号 一个电脑 只能启动 一个项目
 */
```

