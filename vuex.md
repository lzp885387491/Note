1. 上传功能是如何做出来的？
2. 你项目中用到了formData吗？
3. 对formData的理解？
4. vuex的作用？关键key？
5. 项目有多少个页面呢？
6. vuex使用的价值？
7. vuex和localstorage的区别？
8. vuex的持久化？
9. mutations / action 区别？
10. vuex的辅助有哪些？
11. state和gettters的区别？
12. 项目中vuex的架构目录？
13. 导出功能做过吗？

new XLSL({
    el:document.querySelector('#out-table'),
    excludes:[3,5,8]
})

1. vuex常用的几个属性？
state, mutation, action,  getter, module
2. vuex几个属性的作用？
state:存取状态;
mutation: 修改（设置）状态
action: 异步方法，通常用来返回异步接口的api;
getter: 相当于state中状态的计算属性
module: 模块化,作用是把各种状态存取到各个命名空间中，方全管理;
3. vuex模块化的目录结构？
-| store
    -| modules
        moduleName1.js
        moduleName2.js
        moduleName3.js
        moduleName4.js
    index.js    // index.js是vuex的入口，需要把modules中的模块导入到index.js中;
4. vuex的作用及理解？
    vuex是用来存取各种状态的，适用于复杂组件之间的传参;
5. vuex中辅助函数有哪些？及他们的作用？
    mapState, mapMutations, mapActions, mapGetters;
    map:映射
    把map后面的单词中的方法映射到当前vue实例的this上;

迈普丝嘚特

迈普米欧ten深

迈普艾克神丝

迈普该特儿斯

map是映射  



  // actions中的方法和mutations中的方法一样

  // 只不过mutations中定义的方法不能写异步

  // 而actions中可以写异步

  // 能写异步方法

  // 在项目中，通常情况下，actions用来二次封装接口

  // 什么时候用actions ？

  // 如果你调用一个api接口后，一定会将其返回的值放入到cuex中时，

  // 则就要使用actions方法

  // 通常情况下，该方法会利用promise的 .then 方法进行链式调用，

  // 在链式调用中，进行vuex状态存取



 # 模块化

 // 把不同的变量放在不同的模块中

 // -|src

 //   -|store

 //   -|modules   该文件夹下每一个文件都有单独的：state,getters,actions等

 //    -|user.js

 //    -|task.js

 //    -|route.js

 //   index.js  负责把所有的模块化聚集起来





/ mapState 两种入参

  // array 则 接收的每一项都是字符串,该字符串指向的是 vuex中state对应的key

  // 如果没有用到模块化时，一般都会用数组当做入参

  // object 则 接收一个回调函数,该回调函数有一个入参,

  // 入参是state;通常情况下，如果使用vuex模块化就会使用object作为入参