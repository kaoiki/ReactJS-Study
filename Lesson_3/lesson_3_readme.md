#Lesson 3#

#第一步
>引入相关的JS文件

```
react.js
react-dom.js  
browser.min.js
```

**browser.min.js用途是将JSX愈发转为JS语法，生产环境时要把使用JSX语法的片段通过Babel编译后再引用**

>例如将src目录下的js文件进行编译并存入build目录下，$ babel src --out-dir build

***

#第二步
**使用React的基本语法`ReactDOM.render`。其功能是讲模板内容转换成HTML标记语言。**

```
var htmlArr = [
	<h1>Hello, KaOiKi!</h1>,
	<h2>This is H2</h2>
];

ReactDOM.render(
	<div>{htmlArr}</div>,
	document.getElementById('react_output')
);

```
>将JS变量自动显示在浏览器页面中，为了展示效果，特地选择了JS数组变量，并自动展开，显示在页面内。

*部分代码解释*

`var htmlArr = [<h1>Hello, KaOiKi!</h1>,<h2>This is H2</h2>]`

**生成一个名字为`htmlArr`的数组，里面保存了两个HTML标签节点**

***

`<div>{htmlArr}</div>`

**`{}`之前说过就是占位操作，自动展开`htmlArr`这个数组变量，并显示在页面上，其实就是自动遍历内容**

***

`document.getElementById('react_output')`

**向ID为`react_output`的节点输出内容**

***


###说明

`
type=text/babel
`

>JSX需要加上该表情，因为JSX语法与JS不兼容，用来告知Browser对其转换。


