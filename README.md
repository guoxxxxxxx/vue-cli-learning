# 笔记

## ref 属性

1. 被用来给元素或子组件注册引用信息(id的替代者)
2. 应用再html标签上获取的时真实DOM元素, 应用在组件标签上时组件实例对象（vc）
3. 使用方式:

``` js
打标识:
<h1 ref='xxx'>....</h1>
获取:
this.$refs.xxx
```

## 配置项

**功能：** 让组件接受外部传过来的数据

``` js
(1) 传递数据
	<Demo name='xxx'>
(2) 接收数据
    第一种方式(只接收):
    	props:['name']
	
	第二种方式(限制类型):
    	props:{
            name:Number
        }
	第三种方式(限制类型、限制必要性、指定默认值)
		props:{
            name:{
                type:String,
                required:true,
                defalut: 'value'
            }
        }
	
	备注: props时只读的，Vue底层会检测你对props的修改,如果进行了修改,就会发出警告, 
	若业务需求确实需要修改, 则需要赋值props的内容到data中,然后去修改data中的数据.
```



## 插件

``` 
功能: 用于增强Vue
本质: 包含install方法的一个对象, install的一个参数是Vue,第二个以后的参数是插件使用者传递的数据。
定义插件: 
	对象.install = function(Vue, options) {
	// 1. 添加全局过滤器
	Vue.filter(...)
	// 2. 添加全局指令
	Vue.directive(...)
	// 3. 配置全局混入
	Vue.mixin(...)
	// 4. 添加实例方法
	Vue.prototype.$myMethod = function(){...}
	Vue.protoType.$myPrototype = xxxx
	}
	
使用插件: Vue.use
```



## scoped样式

``` 
作用: 让样式再局部生效, 防止冲突
写法: <style scoped>
```



## webStorage

```
1. 存储内容大小一般支持5MB左右
2. 浏览器端通过Window.sessionStorage和Window.localStorage属性来实现本地存储机制。
3. 相关API
	(1). xxxxStorage.setItem('key', 'value');
	该方法接受一个键和值作为参数, 会把键值对添加到存储中，如果键名存在，则更新其对应的值.
	(2). xxxxStorage.getItem('person');
	该方法接受一个键名作为参数， 返回键名对应的值
	(3). xxxxStorage.removeItem('key');
	该方法接受一个键名作为参数， 并把该键名及其数据从存储中删除
	(4). xxxxStorage.clear()
	该方法会清空存储中的所有数据。
	
4. 备注
	1. SessionStorage 存储的内容会随着浏览器窗口关闭而消失
	2. LocalStorage存储的内容需要手动清除才会消失
	3. xxxxStorage.getItem(xxx)如果xxx对应的Value获取不到,那么getItem的返回值是null
	4. JSON.parse(null)的结果依然是null。
```

