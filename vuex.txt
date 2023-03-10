vuex 

1. 说一下对vuex的理解 ？
vuex是一个状态管理工具，他存在于vue2的项目中；
他的作用是适用于复杂的页面及组件传参；

vuex和localStorage的使用场景的区别是， vuex是具有数据双向绑定的；

vuex可以兼听某一个值的变化；

vuex有几个关键的option:  state, mutation, actions, getters, modules;

如果你没只说前4个，没有用； 面试官大概率会问，你们的项目中用vuex的modules吗？ 如果你说不用，你GG了；

state: 存各种状态，你要是不理解这个状态是什么，你就把他理解成一个全局的变量；

mutation:  作用是修改state中的值时，需要用到mutation;

actions:  他是用来调用一些异步的方法；  应用场景，通常情况下， 是基于axios的二次封装之后，再次封装；来达到存取变量的目的；

modules: 模块；
一个项目中，几乎每个页面都需要用到这个状态管理， 所以一个项目中，如果有几十个页面的话，应该有非常多非常多的状态；
此时getters  mutation  actions 都会有非常非常多的东西； 
维护起来就炒鸡炒鸡的麻烦和困难， 为了解决这个问题，就出现了一个Modules; 你可以根据不同的模块，把不同的状态分到不同的模块中去；
项目中，都是这么用的； 没有不用的； 
user 
order 
article

// 现在vuex中有多个 modules，state 是不共用的； 如何在一个storeA中，拿到StoreB的变量；
// 在vuex中，的上下文中，有一个 rooState, 和rootGetters 通过这个属性就可以拿到全局下面的值， 也可以拿到全局下面的某一个模块中的值；
export {
    actions:{
        getOrderInfo({ rooState }){
            ; rootState.userInfo;  { userId: 1, phoneNumber: 1344444 }

            ; 如果你的用户信息是，存在用户模块下面的  user.js中的；
            rootState['user/userInfo']
        }
    }
}



export default Vuex.Store({
    state: {
        userInfo: 'xiaoming'
    },
    mutation: {
        "SET_USERINFO": function(state, payload ){
            console.log(state)  //  { userInfo；  'xiaoming' }

            // payload 就是入参
            state.userInfo = payload;
        }
    }
})

//我看见好多人这么， 这么写是错误的；  不可以通过这种方法去设置；
this.$store.state.userInfo = 'xiaohong'



解构赋值：

const obj = {
    username: 'xiaoming',
    age: 19,
    phoneNumber: 1555555555
}

const { age, ...a } = obj;

console.log(a);  //


