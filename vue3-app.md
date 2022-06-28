### vue3 + vite

```javascript
1. npm install -g @vue/cli  //全局安装vue-cli命令

//注：
yarn global add @vue/cli
# 或
npm install -g @vue/cli
// 目前市场上，这种包管理工具一共有两个 一个是 npm  另一个是 yarn
// 比较快的是 yarn ,以后遇到这个yarn知道是干啥的就行；
// 知识点： 
// 1. 如果 npm install  中 有 -g   --global 等词，则可以忽略文件夹进行安装
//  -g  --global  是全局的意思
// 2.  npm install -g @vue/cli 在全局安装完以后，会自动在终端中生成一个 vue 开头的关键字
// vue create project-name
// 3. 在npm中，除了-g，常用的有 --save-dev  和 --save 
// --save-dev  ===  -S
// --save === -s
// --global === -g
// 如果你下载的包不包含这些关键字，则默认为 --save
// npm install jquery --save   ===    npm install jquery
// 4. 什么时候用--save ？ 什么时候用--save-dev?
// 5. 在你项目中引入的包都需要用--save,
// 相反，如果项目中页面上不需要引用的包，就必须用--save-dev;
// 6. 用npm install 下载的包 可以通过 package.json中的 dependencies 和devDependencies；

```

2、项目启动流程

``` js
1、cd 《project-name》
2、npm install
3、npm run dev // 在之后的过程中只需要走第三步
```

3、进入APP.vue界面  

1. 删除template，及 style 中不用的样式代码

4、做项目时，要引入common.css 

- common.css 负责全局的公共的样式

- 步骤流程

  1. 在src目录中创建common.css

  2. 在main.js中导入这个全局样式

     ``` js
     import './common.css'
     ```

5、安装路由

1. npm install vue-router@4

6、配置路由

1. 在src文件夹下键一个router文件夹
2. 在router文件夹下键一个index.js

7、vue-cli 中可以用jquery吗？

答：不建议这么使用

``` js
原因：vue不建议操作dom
而jQuery是操作dom
完全相反
```

8、说一下路由的懒加载？

```js
路由懒加载也叫按需加载，在加载路由时，用 import PageName from "../views/pageName/PageName.vue" 实现普通加载
用 import(/*webpackChunkName:'PageName'*/'../views/pageName/PageName.vue')实现懒加载
懒加载可以提升页面加载速度，在用户访问对应的页面时，，才去加载对应的页面模块，实现性能提升
通常情况下，项目中的首页及登录页面是普通加载，其他场景都是懒加载
例如：
var route=[
    {
        path:'/home',
        component:Home
    },
    {
		path:'/activityDetail',
        component:import(/*webpackChunkName:'PageName'*/'../views/pageName/PageName.vue')
    }
]
```

知识点：配置路由相关的规则

``` js
1、配置路由时，path路径要以/开头，通常情况下，使用驼峰命名法
2、通常情况下，path的值和name的值保持一致，只不过name的值 首字母应该大写
3、通常情况下，path值要和该模块的名才能保持一致 比如：path：'activeityDetail'  name:'ActivityDetail' activityDetail.vue
```

9、移动端相关知识点？

```js
1、在开发移动端项目式，应该打开F12 调成移动端；
2、移动端的屏幕的宽应该等于设计稿的整数倍，一般情况下是两倍
3、目前市场上主流的所有的移动端的设计稿宽为：750px
4、设计稿为手机分辨率的两倍  换句话说 我们在开发时 我们的手机屏宽应该调成 375px 也就是 iphoneSE 
```

10、如何适配移动端？

```js
答：利用ali适配方案来解决
// ali适配方案底层采用 rem 布局实现适配
```

11、在前端项目中你做过那些优化？

```js
1、cmd
2、webpack模块中配置路由懒加载
3、图片优化中可以用雪碧图来减少请求
```

12、说一下对rem的理解？

```js
// rem是一个相对单位，它是基于根元素字体大小的变化而变化

```

