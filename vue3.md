1. **vue**  是一个**渐进式框架**   意思是 渐渐地进入项目    
2. **vue 的核心库**  只关注与视图层  意思就是   我只需要掉接口  然后视图自己就变了  我不需要关注他怎么变  
3. **社区活跃** 意思是 这个vue框架呢  是个开源的    可以引用很多UI框架  可以一键引用  一键安装       就是说   社区活跃 就可以使这个框架能用很多插件    好用  也方便
4. **vue**  结合 **现代化的工具链**     **webpack**  和  **vite**  
5. **webpack**  作用就是 **模块化 ** **vuecli 的底层也是webpack写的** 
6.  **webpack**  和  **vite**  的区别：目前来说   **webpack**  有替换  **vite**  的趋势 原因是 **webpack 是基于node.js写的**，是通过node.js写的模块化，他这个模块化只是说能让你在webpack里面用引用引出啥的，然后它会自己给你编译成原生**js,html,css**  这就导致它的**性能不太好**。   
7. **vite**  性能至少比 **webpack** **快十倍**
8. 导入和导出是为了模块化，模块化的好处：代码清晰，维护性能高
9. vue  完全能够 用来做单页面应用
10. **vue-cli 脚手架** 也叫  **vue全家桶**

**面试题：说一下对前端模块化的了解?**

**答案问的就是  webpack 和 viet 的了解**

单页面   多页面

- 一个项目只有一个html的项目  就叫单页面应用 应用场景：移动端
-  多页面应用是有多个主页面   所有能百度搜出来的东西   都是多页面

搜索引擎叫 SEO

# 安装vue3

- CDN  又叫 网路分发 是用来做性能优化的  

  ​		 cdn呢就相当于移动联通的那些信号塔，总公司在北京  信号塔呢 遍布全国  你要打电话啥的  需要发信号给信号塔  然后因为有cdn呢  就会找到离你最近的一个信号塔直接用  所以就快

  **CDN 的缺点** ：cdn是有延迟的    **也有风险   万一cdn官网崩了   我项目要是用的cdn的方式做的   也会连带这崩！**

- 下载js文件源码  自行托管    意思就是说 你把vue的源码下载到本地  然后引用到项目中  就叫自行托管

-   npm install  基于Node 

  -  n代表node.js 
  -  p代表 package 包
  - m mage    管理

- cli 代表命令行创

- gui 代表 图修改

1. 命名 不能有中文   大小写    因为GitHub编译不了中文

2. 项目目录

   ##### 传统型多页面开发项目目录结构说明（一）推荐

   ``` html
   -| project-name
   	-| src
   		-| pages
   			-| pageName
   				pageName.html
   				pageName.css
   				pageName.js
   			-| assets
   				-| images   or imgs
   				-| lib  // 库  jQuery   vue.js  library
   				-| utils // 公共的js
   				-| css // 公共的css
   					common.css
   	README.md  // 必读文件
   ```

   ##### 传统型多页面开发项目目录结构说明（二）

   ``` html
   -| project-name
   	-| src
   		-| pages
   			pageName.html
   			pageName.css
   			pageName.js
   		-| assets
   			-| images   or imgs
   			-| lib  // 库  jQuery   vue.js  library
   			-| utils // 公共的js
   			-| css // 公共的css
   				common.css
   	README.md  // 必读文件
   ```

   #### 传统型多页面开发+模块化项目目录结构说明（一）推荐

   ~~~ html
   
   <!-- 因为项目是基于node环境开发的，当打包完成后，需要打包一份浏览器识别的文件，这个dist文件就是浏览器可以访问的html地址文件；dist文件夹通常是通npm run build自动生成的，不需要手动改任何东西 -->
   ~~~

### Vue 3.0

1. vue 3 的核心思想 是  万物皆组件  
2. 表示一个功能用一个组件
3. 实例data是一个方法   这样就不会造成组件之间的变量冲突

1  响应式的底层实现原理是基于什么实现的？

答：object.defineProperty   V2.0

​		vue3.0  js底层有一个累  new Proxy()

2、你知道vue2.0和vue3.0 有什么区别？

答：一个是基于Object.defineProperty

​	   另一个是基于Proxy（）来实现的   Proxy代理的意思

3、vue-cli 中如何解决跨域？

答   在vue.config.js中 配置proxy

4、在开发的时候是配置vue.comfig.js 那你项目上线时是怎么解决跨域的/

答：后端解决

5、vue中的钩子函数有哪些？生命周期有哪些

答：

6、通常情况下，打开页面时需要的逻辑写到那个钩子函数里？

created  或者  mounted

7、created   和   mounted的区别？

答：created是挂赞了this。data

mounted是  渲染了dom

8、v-bind 的作用？和  ：有什么区别？

答：给元素属性绑定动态的值

​		：是v-bind的简写

9、说一下自定义属性的实现原理是什么？

答：获取当前元素的attribute属性；看看是否为v-开头，如果是，就利用正则表达式，取值并写出对应的逻辑。

10、MVVM 中的VM是什么意思？说一下对数据双向绑定的理解

答：VM 指的是数据变视图变  视图变数据变   

11、v-bind  和  v-model  的区别 ？

答：v-model 作用于form表单 ，应用于视图改变数据

​		v-bind  是绑定动态的值    是数据变，这个值变

12、v-if    和  v-show 的区别?

v-if是  是否创建元素

v-show是   display:none;

应用场景：  如果需要频繁切换   可以用v-show  否则就用v-if

v-show  可以用在tab切换

13、v-if  可以和  v-for  同时使用吗、？

答：可以   但是 不能这么用

14、v-if 和v-fof 的执行顺序是什么？优先级   

答：vue2：v-for 高于  v-if 

​		vue3：v-if  高于   v-for 

那如何解决此类问题？

答：如果渲染一个list，你需要处理一下list数据，将list数据处理后再渲染

15、为什么再v-for中要加一个key ？

答：   在底层中vue通过这个key来找这个元素；而不是元素的id

​		在底层中，vue列表数据被修改时，是根据这个元素的key来判断是否需要修改哪一个元素

## 组件封装的维度？

1、业务组件  和  非业务组件  两种

> 注释：  非业务组件又叫公共组件，就是这种组件是可以复用到其他项目中的，
>
> 业务组件是只有当前项目中可以使用。

2、组建的封装，

- 组件的命名：建议用至少两个单词   每个单词之间用  -   划分  