#Lesson 4#

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
var SayMessage = React.createClass({
	render: function() {
		return <h1>{this.props.what},{this.props.name}</h1>;
    }
});

ReactDOM.render(
	<SayMessage what="Hey" name="KaOiKi" />,
	document.getElementById('react_output')
);

```
>自定义了一个HTML显示组件，然后加载到页面指定位置并显示。

*部分代码解释*

`var SayMessage = React.createClass`

**生成一个名字为`SayMessage`的显示组件，使用了`React.createClass`语法创建，也可以理解为创建了一个自定义的类**

***

`render: function()`

**我的理解就是为`render`添加一个隐式的函数引用**

***

`return <h1>{this.props.what},{this.props.name}</h1>`

**被引用的函数就是输出如上一段内容，和之前一样，使用了两个`{}`占位操作，其内部用来输出当前组件的两个属性，属性名字分别为`what`和`name`**

***

`<SayMessage what="Hey" name="KaOiKi" />`

**在指定页面节点容器内装载这个自定义组件，分别设定其两个属性`what`和`name`供上述方法读取**

***


`document.getElementById('react_output')`

**向ID为`react_output`的节点输出内容**

***


###说明

`
type=text/babel
`

>JSX需要加上该表情，因为JSX语法与JS不兼容，用来告知Browser对其转换。


