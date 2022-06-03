#  props 使组件更加灵活

### 1、用组件的地方

~~~ vue
<template>
	<div>
    	<el-title>
    		<span>角色管理</span>
    	</el-title>
        <!-- 上边这个呢 是没有icon图的  下边封装的组件里有一个v-if判断  有icon的话就渲染这个；没有就不		  渲染 -->
        <el-title icon="el-icon-user">
    		<span>任务中心</span>
    	</el-title>
    </div>
</template>

<script>
export default {
    props:['icon'],
    created(){
        console.log(this.icon);// el-icon-user 这个呢就是 props传过来的icon图
    }
}
</script>
~~~

### 2、组件

~~~ vue
<template>
	<div>
    	<h1>
        	<span v-if=”icon“ class="icon" :class="icon"></span> // icon 图
            <slot></slot> // 插槽  这个slot插槽可以让这个组件里插入标签 
    	</h1>
    </div>
</template>

<script>
export default {
    props:['icon'],
    created(){
        console.log(this.icon);// el-icon-user 这个呢就是 props传过来的icon图
    }
}
</script>
~~~

## 总结

####       父子组件传参	利用什么来传？

父组件 通过 在组件标签上 声明属性；然后子组件呢 通过props属性来声明；

然后子组件就可以通过this.propsName来获取到那个值