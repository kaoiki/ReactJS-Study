#Lesson 1#

#第一步
>引入相关的JS文件

```
react.js
react-dom.js  
browser.min.js
```

**browser.min.js用途是将JSX语法转为JS语法，生产环境时要把使用JSX语法的片段通过Babel编译后再引用**

>例如将src目录下的js文件进行编译并存入build目录下，$ babel src --out-dir build

***

#第二步
**使用React的基本语法`ReactDOM.render`。其功能是讲模板内容转换成HTML标记语言。**

```
ReactDOM.render(
	<h1>Hello, KaOiKi!</h1>,
	document.getElementById('react_output')
);

```
>上述语法就是最简单的应用，往ID为`react_output`的HTML节点内插入一段内容，内容为`h1`标题，具体涉及HTML语法的内容这里不赘述。

###说明

`
type=text/babel
`

>JSX需要加上该表情，因为JSX语法与JS不兼容，用来告知Browser对其转换。


