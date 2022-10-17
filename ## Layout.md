## Layout

1、组合式函数的应用场景及解决问题？

2、命名空间组件纬度的使用

3、util公共方法的封装

## useTabbar.ts

1、ref

2、如何声明json对象的数据结构及应用场景

3、vue-router中的 router 和 router

## Tabbar.Wrapper.vue

1、torefs 通常情况下是用在props传参的时候

2、provide 爷孙传参 

3、defineEmits

4、defineProps

## Tabbar.Item.vue

1、inject

2、computed 应用场景：如果你的页面中需要使用三元表达式来判断一些逻辑，为了代码更加的清晰，我们通常情况下会用computed计算属性来代替；

3、在你的项目中，在那些场景中需要用到断言？
答：在我封装组件的时候，用provide和inject时，ts无法判断是什么类型，此时我们必须用断言

4、v-bind设置css