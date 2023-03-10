### mixins
mixins是混合的意思 ，通常指的是把两种物品混合在一起；
在less 中，或者在scss中，就有混合的概念，他指的是把两种样式混合到一个样式中；
但是在此处的混合，指的是 vue中的混合，他是用来，把两个Vue中实例的参数进行混合；

```javascript
// 1. 导入Mixin的对象；
import mixin from '@/mixins/mixin.js'
// 2. 挂载在mixins对象中；

// 混合的先后顺序是 先执行mixin ,在执行 Home.vue的实例；
// 通常情况下，mixin 是用来在vue中，进行功能的封装；

// a页面中，要在created中执行 获取用户信息的逻辑；
// b页面也要在created中直接调用 获取用户信息的逻辑；

// mixin的缺点是，如果封装过多的mixin，会导致代码可读性变得恢常差；
// mixin本身设计出来就有非常大的缺陷；
// 他背离了一个方法实现一个功能的逻辑；
// 一个功能封装一个方法； 

// a, b ,c  但是逻辑稍有不同；
// 所以， 三年工作以验以下的人，不要去用这个东西； 你把控不了这个东西；
// 并且在vue3中，用到了组合式，来完美的解决了mixin存在的问题； 



    // Home.vue
    export default {
        mixins: [ userMixin, orderMixin, loginMixin  ],
        data(){
            return {
                username: 'xiaoming'
            }
        },
        created(){
            let num = this.counter(10, 20);
            console.log(num) // 30;
        },
        methods:{
            counter(num1, num2){
                return num1 + num2;
            }
        }
    }
```

```javascript
    // mixin.js
    export default {
        data(){
            return {
                username: 'xiaohong'
                age: 18,
                sex:1,
            }
        },
        created(){
           
        },
        methods:{
            counter(num1, num2){
                return num1 + num2;
            }
        }
    }
```

<!-- 纯函数 -->
// 一个功能封装一个方法； 
// 什么是纯函数；
// 纯函数就是我教你们的函数使用规则 ；  一个方法只实现一个单纯的功能； 并且函数内部不会调用或者改变外部变量的值；

```javascript
    function counter(num1, num2){
        return num1 + num2;
    }
```

```javascript
    let dom = document.getElementById("box");
    function render(){
        dom.innerHTML = 'hello world!'
    }
```

```javascript
    // 是纯函数
    let username = 'hello world'

    function render(name){
        name = 'xiaohong'
    }

    render(username);
```

```javascript
    // 不是纯函数, 因对 obj和object 的内存指向地址是一个地址；
    let obj = {
        username: 'xiaoming'
    }

    function render(object){
        object.username = 'xiaohong'
    }

    render(obj);
```

<!-- 基本数据类型和引用数据类型的区别是什么？ -->
```javascript
    var obj = {
        username: 'xioaming'
    }

    var obj2 = obj;

    obj2.username = 'xiaohong'

    console.log(obj)   // { username:  'xiaohong' }
    console.log(obj2) // { username: 'xiaohong' }
```