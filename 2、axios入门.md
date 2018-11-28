# 安装

```
npm install axios
```



# 导入

```js
import axios from 'axios'
```

- 在哪个文件中要使用 axios 就在那里导入。
- 如果是在 .vue 文件中就再 script 标签中导入。



# 发送请求

```javascript
mounted:function () {
    axios
        .get('http://jsonplaceholder.typicode.com/users')
        .then(response => {
        this.users = response.data;
    })
}
```

