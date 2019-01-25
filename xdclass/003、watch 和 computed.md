# watch 监听简单变量

`msg` 是一个字符串类型，它与输入框双向绑定。`watch` 一直监听它的值，当它变成 `fuck` 的时候，弹窗。

```html
<div id="app">
    <h1>watch 监听一个变量</h1>
    <input type="text" v-model="simpleMsg">
</div>

<script>
    new Vue({
        el: '#app',
        data: function() {
            return {
                simpleMsg: ''
            }
        },
        // 函数名和变量名一致，第一个参数是新的值，第二个是原来的值
        watch: {
            simpleMsg(newval, oldval) {
                if(newval === 'fuck') {
                    alert("Fuck You!");
                }
            }
        }
    })
</script>
```



# watch 监听对象

监听数组等同理。

```html
<div id="app">
    <h1>watch 监听复杂变量</h1>
    <input type="text" v-model="cmMsg.text">
</div>

<script>
    new Vue({
        el: '#app',
        data: function() {
            return {
                // cmMsg 是一个对象
                cmMsg: {
                    text: ''
                }
            }
        },
        watch: {
            // 注意写法，一个 handler 函数，还有一个 deep 开启深度监听
            cmMsg: {
                handler(newval, oldval) {
                    if(newval.text === 'fuck') {
                        alert("Fuck You!");
                    }
                },
                deep: true
            }
        }
    })
</script>
```



# computed 实现简单计算

**也可以看成是用 computed 监听多个事件。**

```html
<div id="app">
    <h1>computed 简单计算</h1>
    // 计算 (n1 + n2) * n3 的值
    (<input type="text" v-model="n1"> +
    <input type="text" v-model="n2">) * 
    <input type="text" v-model="n3"> = {{ res }}
</div>

<script>
    new Vue({
        el: '#app',
        data: function() {
            return {
                // 定义 n1 n2 n3
                n1: '',
                n2: '',
                n3: '1'
            }
        },
        // 计算属性
        computed: {
            // 这里的 res 跟 html 中的 res 对应
            res() {
                // 当 n1 n2 n3 任意一个发生变化时，res 都会发生变化
                return (Number(this.n1) + Number(this.n2)) * Number(this.n3);
            }
        }
    })
</script>
```

