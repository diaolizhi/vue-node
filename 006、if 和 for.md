# v-if 和 v-show

- 如果使用 if，当条件不成立时会变成注释 

```
<!-- -->
```

- 如果使用 v-show，当条件不成立时 style="display: none;" 

```html
<div id="useIf">
	<button v-on:click="y = !y">change</button>
	
	<!-- 这种情况不占位 -->
	<p v-if="y">成功</p>
	<p v-else-if="!y">失败</p>
	
	<!-- 这种情况占位 -->
	<p v-show="y">成功</p>
	<p v-show="!y">失败</p>
</div>
```



# v-for

使用 template 就不会生成一堆 div

```html
<div id="useFor">
	<ul>
		<li v-for="(char, index) in chars">
			{{ index }} - {{ char }}
		</li>
	</ul>
	
	<!-- <div v-for="user in users">
		<h1>{{ user.name }}</h1>
		<p>{{ user.age }}</p>
	</div> -->
	
	<!-- 不会生成一堆 div -->
	<template v-for="user in users">
		<h1>{{ user.name }}</h1>
		<p>{{ user.age }}</p>
	</template>
	
	<!-- 获取键和值 -->
	<template v-for="user in users">
		<div v-for="(index, key, val) in user">
			<!-- 不管关键是是什么，隐含的顺序都是：值、键、索引 -->
			{{ index }} - {{ key }} - {{ val }}
		</div>
	</template>
	
</div>
```

