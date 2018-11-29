# CSS 样式绑定



## 绑定 class

- v-bind:class 后面的引号中间还需要**大括号**
- 第一个 changeColor 是 css 中的一个类
- 第二个 changeColor 是一个布尔值
- 如果为真就绑定这个类，为假就不绑定

```html
<div id="bindClass">
	<!-- 通过设置类名后面的布尔值实现动态绑定 css 样式 -->
	<span v-on:click="changeColor = !changeColor" v-bind:class="{changeColor:changeColor}">Jack</span>
</div>
```



## 绑定 style

activeColor、fontSize 都是属性，可以在需要时改变

```html
<button v-on:click="fontSize+=10">改变下面字体大小</button>
<div v-bind:style="{ color: activeColor, fontSize: fontSize + 'px' }">哈哈</div>
```

```javascript
data: {
  activeColor: 'red',
  fontSize: 30
}
```

