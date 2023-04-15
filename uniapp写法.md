# UniApp

1、第一次进入 uniapp 需要配置一下运行路径：工具 > 设置 > 运行配置 > 浏览器安装路径、运行工具路径、开发工具运行路径等

2、微信小程序也要设置：设置 > 安全设置 > 服务端口（按钮勾选） 不然无法打开微信小程序

3、目录结构

​	pages：页面

​	static：= vue 中的 assets 放静态资源的

4、语法：vue的语法：但是html 的标签要换成小程序的标签

5、app.vue 的作用是：声明全局方法、全局样式

6、封装接口

``` js
    在APP.vue中封装：
在 globalData:{
    baseUrl:'http://localhost:3000',
        getUserInfoApi(data){
        	return new Promise((resolve,reject)=>{
                uni.request({
                    url:baseUrl + '/user/info',
                    data,
                    success(res){
                        resolve(res)
                    }
                })
            })
    }
}
```

7、配置路由 及 编译模式

```js
# 在peges.json文件里配置路由
{
	'pages':[
        {
            'path':'pages/index/index',
        	'style':{
        		'navigationBarTiteText':'uni-app'
        	}
        },
        {
            'path':'pages/index/index',
        	'style':{
        		'navigationBarTiteText':'uni-app'
        	}
        }
    ]
}
# 编译模式
打开uniapp官网   找全局文件  找pages.json页面路由 找condition
进去之后  吧源代码复制   粘贴到 pages.json文件中 修改路径及name即可
```

8、如何打包？

```js
# 打包
1、微信小程序  把你项目的 unpackage/dist/dev/mp-weixin 这个文件夹整体扔到微信开发者工具里打包
2、点击HBuilderX中的发行 选择你要打包的  比如微信小程序  会让你配置一个APPId   然后点击发行
```

