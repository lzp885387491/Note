~~~ js
class Vue{
	constructor(){
        this.data={
            a:10,
            b:20,
        }
    }
    static use(plugin){
        plugin(Vue);
    }
}

function count(Vue){
    let vm = new Vue();
    let res = vm.data.a + vm.data.b;
    console.log(res);
    return res;
}
// 目前为止，我们只是实现一下use这个方法
// 并不代表着这个count方法有什么意义
Vue.use(count);
~~~

然后呢  官网上给我们说了  这个use方法呢  不光可以传方法  它还可以传对象

那么就需要给我们刚刚写的这个加一个判断了  如下：

~~~ js
class Vue{
	constructor(){
        this.data={
            a:10,
            b:20,
        }
    }
    
    static use(plugin){
        if(isObject(plugin) && isFunction(plugin.install)){
            // 如果是一个对象并且plugin.install它是一个方法的话
            // 就执行这个install并把Vue传过来
            plugin.install(Vue);
        }else if(isFunction(plugin)){
         	// 如果呢 它是一个方法function 那么就执行这个
        	plugin(Vue);   
        }
    }
}

function count(Vue){
    let vm = new Vue();
    let res = vm.data.a + vm.data.b;
    console.log(res);
    return res;
}

// 想要用刚刚优化的判断方法的话  需要这么写 如下
let isObject = isType('Object');
let isFunction = isType('Function');
// 那么现在呢  就可以用了

// function isObject(val){
// return Object.prototype.toString.call(val).slice(8,-1) == "Object"
// }

// function isFuncton(val){
//  return Object.prototype.toString.call(val).slice(8,-1) == "Function"
// }

Vue.use({
    install:count
});

// 然后呢   上边封装的判断是不是对象或者function的方法可以优化一下  优化成一个闭包来写
function isType(type){
    return function(val){
        return Object.prototype.toString.call(val).slice(8,-1) == type
    }
}
// 那 上边的那两个方法就可以删除了  然后呢 用法  如上
~~~



