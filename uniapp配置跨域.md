# 跨域

1、打开uniapp项目目录  找：manifest.json 文件 

2、打开之后有一些配置   选择最下边的源码视图  页面会切换成源码页面

3、在源码里面写

```js
"h5": {
		"devServer": {
			"https": false,
			"port": 8080, //
			"disableHostCheck":true,
			"proxy":{
				"/api":{
					"target":"http://192.168.1.59:3000",
					"pathRewrite":{
						"^/api":""
					}
				}
			}
		}
	},
```

4、在页面中用

``` js
this.getUserInfo('/api/user/info','POST',{})
```

