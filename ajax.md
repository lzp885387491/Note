### 说一下对ajax的理解？
ajax是用来请求服务端接口数据的,它是基于XMLHttpRequest来实现的，

### 你封装过ajax吗？
```javascript
// get请求
    var xhr = new XMLHttpRequest();

    xhr.open("get", 'www.xxxx.com/user/info', true)

    xhr.onload = function(){
        if(xhr.status == 200){
            return JSON.parse(  xhr.responseText )
        }
    }

    xhr.send()
```

```javascript
// POST
    var xhr = new XMLHttpRequest();

    xhr.open("POST", 'www.xxxx.com/user/login', true)

    xhr.onload = function(){
        if(xhr.status == 200){
            return JSON.parse(  xhr.responseText )
        }
    }

    let urlSearchParams = new URLSearchParams();
    urlSearchParams.append('username', 'xiaoming')
    urlSearchParams.append('password', '999999')

    xhr.send(urlSearchParams)
```


## 分支一

### 说一下ajax和axios的区别？
ajax是异步函数，在项目中会造成地狱回调；axios基于异步函数的解决方案解决并实现了这个问题；


### 那你知道解决异步函数的方案是什么吗？
答： 在ES6中，出来了promise， await ,async ,来解决这个问题；


### 那你能说一下对promise的理解吗？
答： promise是一个构造函数，该构造函数接收一个回调函数，该回调函数接收两个参数，一个是resolve,一个是reject，如果执行了resolve(), 则会走promise下面的.then方法， 如果是调用了reject方法，则会走Promise中的.catch方法；


### promise是可逆的吗？
答： promise是不可逆的； promise的状态，要不成功，要不是失败，失败之后不可以逆转成成功;


### 你知道哪些Promise的常用方法呢？
Promise.resolve() 成功
Promise.reject() 失败
Promise.all() 所有promise对象执行完后会拿到该结果  
Promise.some() 某些函数执行完之后 
Promise.race() 哪一个方法执行的快，就返回哪一个回调；


### 请说一下 await, async 的理解 ？
await async 是基于promise的一个语法糖；


## 分支二

### http协议常用的状态码有哪些？
200, 201, 301, 304, 400,  401 ,402, 403 ,404 , 405
500, 501 502 
如果你说不出来；你可以这么说：
2开头是成功；
3开头是重定向  304是缓存
4开头是 客户端错误，  接口名写错了，或者参数写错了；  403没有权限  401 没有登录；
5开头是服务错误 ， 服务端代码报错； 服务器甭了；

### 说一下浏览器请求服务器的交互过程？
1. 解析域名   dns;  他会把域名解析成 ip 地址；   www.wfish.com => 8.131.89.181:3000
2. 三次握手，四次挥手；