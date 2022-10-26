1. **vue**  是一个**渐进式框架**   意思是 渐渐地进入项目    
2. **vue 的核心库**  只关注与视图层  意思就是   我只需要掉接口  然后视图自己就变了  我不需要关注他怎么变  
3. **社区活跃** 意思是 这个vue框架呢  是个开源的    可以引用很多UI框架  可以一键引用  一键安装       就是说   社区活跃 就可以使这个框架能用很多插件    好用  也方便
4. **vue**  结合 **现代化的工具链**     **webpack**  和  **vite**  
5. **webpack**  作用就是 **模块化 ** **vuecli 的底层也是webpack写的** 
6.  **webpack**  和  **vite**  的区别：目前来说   **webpack**  有替换  **vite**  的趋势 原因是 **webpack 是基于node.js写的**，是通过node.js写的模块化，他0这个模块化只是说能让你在webpack里面用引用引出啥的，然后它会自己给你编译成原生**js,html,css**  这就导致它的**性能不太好**。   
7. **vite**  性能至少比 **webpack** **快十倍**
8. 导入和导出是为了模块化，模块化的好处：代码清晰，维护性能高
9. vue  完全能够 用来做单页面应用
10. **vue-cli 脚手架** 也叫  **vue全家桶**



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

