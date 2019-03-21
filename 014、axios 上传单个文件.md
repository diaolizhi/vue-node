# 参考资料

> https://serversideup.net/uploading-files-vuejs-axios/



# 效果

在网页中不使用表单，提交 `<input type="file">` 中的文件。



# 准备

- 引入 axios
- 引入 Vue
- 准备好 `<input type="file">`



# 关键代码

关键点：

- 通过 ref 找到 `<input type="file">` 元素后，要访问 `files` 数组的 **0 号元素**。
- `Content-Type` 设置为 `multipart/form-data`

```javascript
let formData = new FormData();

// 通过 Vue.js 中的 ref 获取到 HTML 元素
formData.append('file', this.$refs.recordInput.files[0]);

// 提交录音文件4
7axios.post("提交的路径", formData, {
    headers: {
        'Content-Type': 'multipart/form-data'
    }
}).then((msg) = >{
    console.log(msg);
}).
catch(function(errorMsg) {
    console.log(errorMsg);
});
```



# 链接

[axios - GitHub](https://github.com/axios/axios)



