// 面试题：onclick 和 addEventListener 的应用场景？
// 答: 如果你的页面中需要写一些正常的业务逻辑时，可以用onclick
// 如果你封装一些公共的插件时，建议写addEventListener
// 因为插件中写的addEventListener不会影响用户的其他操作
// 用户声明的onclick事件，不会覆盖掉你的插件的事件。
/**
 * 构造函数中的this指向是slider
 * Slider构造函数中才会有这些方法：createDots createDot initDots getContainerCssText
 * 在构造函数中，有一个prototype属性：通常情况下，该属性会挂载一些原型方法；
 * 在构造函数的实例中，有一个__proto__属性，该属性会指向该构造函数的 prototype;
 * 类中的this：slider.createDots() // =>slier.__proto__.createDots  ==  Slider.prototype.createDots;
 * onclick中的this：谁调用 就指向谁
 * 面试题：说一下箭头函数和普通函数的一个区别？
 * 区别是：this指向不一样
 * 普通函数中的this是谁调用 就指向谁
 * 箭头函数中的this是 指向当前方法体的父级
 * 方法体重没有this，所以该函数终究没有arguments这个属性；
 * 但是在项目中，通常不会去用到这个箭头函数
 * 因为通常情况下，我们会在事件中设置这个元素的一个相关操作
 * 所以为了灵活性 通常不会去动这个this的指向
 */
