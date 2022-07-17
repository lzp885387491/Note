# 面试题

如何只缓存组建中的部分内容？

答：在activated肘子函数中，调用不缓存的方法

说一下activated和deactivated钩子函数的作用？

答：缓存组建被激活时，会调用activated钩子函数，失活时，会调用deactivated

说一下对  keep-alive 的理解？

答：keep-alive 组建是缓存组建，一般情况下，可以缓存在component标签中；除此之外，用处最多的是缓存在<router-view>中去；

该组件接受两个参数，一个是include，另一个是exclude；

include是包含，它的值是字符串，内容是需要缓存的组件名，如果想缓存多个组建则可以用逗号拼接

exclude是不包含哪些组建，他的值是字符串，内容是不需要缓存的组件名，如果想不缓存多个组建，则可以用逗号拼接

该组件是激活时，会调用的activated钩子函数

失活时，会调用deactivate钩子函数

说一下组建如何缓存？

答：利用keep-alive 组建

## keep-alive的应用场景

答：在c端中，上啦加载渲染很多个列表时，会用到组建缓存

## 知识点：

在路由配置中，meta变量不是看你心情来声明的

他是让开者用来存取自己定一点变量的

