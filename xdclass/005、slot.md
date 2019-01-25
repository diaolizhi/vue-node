# slot 的使用场景

- 定义了一个组件
- 使用这个组件
- 想在这个组件中再插入标签



```html
<div id="app">
</div>

<script src="./js/vue.js"></script>

<script>

    // 自定义组件
    var MyCom = {
        template: `<div>我是自定义组件<slot></solt></div>`
    }

    new Vue({
        el: '#app',
        data: function() {
            return {

            }
        },
        // 注册自定义组件
        components: {
            MyCom
        },
        // 想在自定义组件中间插入其他标签
        // 如果自定义组件中没有 <slot></solt> 那么插入的标签是无法显示的
        template: `<div><MyCom><h1>测试</h1></MyCom></div>`
    })
</script>
```



# 设置 slot 的 name 

`slot` 有点像给标签留坑位，设置 `name` 的话就相当于给指定的标签留坑位。

```javascript
var MyCom = {
	// 给 slot 设置 name
	template: `<div>我是自定义组件<slot name="s1"></slot></div>`
}
```

最终只会显示名字一致的：

（显示 `S1` 而不会显示 `测试`）

```javascript
template: `<div><MyCom><h1>测试</h1><h1 slot="s1">S1</h1></MyCom></div>`
```

