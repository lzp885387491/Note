# 微信小程序的js写法

```js
// pages/article/detail.js
// 
const util = require('./util.js')

let sum = util.sum(10, 20);
console.log(sum);
Page({
  /**
   * 页面的初始数据
   */
  data: {
    username: 'xiaoming',
    arr: ['xiaoming', 'xiaohong', 'xiaogang', 'xiaoge']
  },

  /**
   * 生命周期函数--监听页面加载
   */
  onLoad(options) {
    // onLoad     created + keep-alive
    // keep-alive 是数据缓存  你可以理解成， 第一次打开页面的时候会走这个方法； 
    // 如果二次进来以后就不会走这个方法； 
    // 也就是说， 他只会走一次；

    // 通常情况下，  能用onLoad , 绝对不要用 onShow;
    // options 是 页面传参     /pages/detail/index?a=1;
    // options  { a: 1 }  
  },
  // 如何声明方法；
  handleClick() {
    // vue中直接可以用 this.username 来拿到 这个username;
    // 但是在 微信小程序中， 必须用  this.data.username;
    console.log(this.data.username);

    // 如何设置 data中的值 ；
    // vue  this.username = 'xiaohong';
    // 微信小程序  这种设置的方式是抄ｒｅａｃｔ的；
    this.setData({
      username: 'xiaohong'
    })


    //  全局变量
    // vue 的项目的时候  全局变量 ==>  状态管理   vue2.0  vuex     vue3.0中 pinia
    // 微信小程序中   
    let app = getApp();
    console.log(app.globalData.version);  //就是那个 app.js中的那个 实例；
    app.globalData.version = "v1.0.0";

    console.log(app);
  },

  /**
   * 生命周期函数--监听页面初次渲染完成
   */
  onReady() {

  },

  /**
   * 生命周期函数--监听页面显示
   */
  onShow() {
    // created;
    // 你每次看见一次这个页面，他就会走一次这个方法；
  },

  /**
   * 生命周期函数--监听页面隐藏
   */
  onHide() {
    // destory
  },

  /**
   * 生命周期函数--监听页面卸载
   */
  onUnload() {
    // 页面卸载  ？   跳转页面时在讲
  },

  /**
   * 页面相关事件处理函数--监听用户下拉动作
   */
  onPullDownRefresh() {
    // 上拉刷新 会走这个方法；
  },

  /**
   * 页面上拉触底事件的处理函数
   */
  onReachBottom() {
    // 下拉加载
  },

  /**
   * 用户点击右上角分享
   */
  onShareAppMessage() {
    // 点击右上角分享按钮的时候，会走这个方法， return 什么样的值， 就会分享什么样的内容；
  }
})
```

