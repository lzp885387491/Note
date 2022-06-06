# Axios 拦截器 

```js
// 添加请求拦截器  请求拦截器是在请求服务之前进入这个方法
axios.interceptors.request.use(function (config) {
    // 在发送请求之前做些什么
    return config;
  }, function (error) {
    // 对请求错误做些什么
    return Promise.reject(error);
  });

// 添加响应拦截器 
axios.interceptors.response.use(function (response) {
    // 对响应数据做点什么
    return response;
  }, function (error) {
    // 对响应错误做点什么
    return Promise.reject(error);
  });
总结：
一个拦截器是请求拦截器
一个拦截器是响应拦截器
请求拦截器是在请求服务端接口之前调用
响应拦截器是在.then()方法执行之前调用；

请求拦截器通常可以用来设置请求头，实现授权登录的功能
响应拦截器通常可以用来做一些未登录时的统一操作；

```

