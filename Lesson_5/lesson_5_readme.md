#Lesson 5#

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
var BrandsList = React.createClass({
	render: function() {
		return (
			<ol>
				{
					React.Children.map(this.props.children, function(child) {
						return <li>{child}</li>
					})
				}
			</ol>
		);
	}
});

ReactDOM.render(
	<BrandsList>
		<span>Apple</span>
		<span>Huawei</span>
		<span>Mi</span>
		<span>Samsung</span>
	</BrandsList>,
	document.getElementById('react_output')
);

```
>自定义了一个HTML显示组件，然后加载到页面指定位置并显示。

*部分代码解释*

`<ol>{}</ol>`

**占位功能，在其中遍历后输出数组内容**

***

`React.Children.map`

**通过这个`React`自带的`map`方法可以快速遍历组件内的节点，并且可以忽略节点的数据类型是`undefined`还是`object`**

***

`<span></span>`

**组件内的节点，自定义也可以**

***


`document.getElementById('react_output')`

**向ID为`react_output`的节点输出内容**

***


###说明

`
type=text/babel
`

>JSX需要加上该表情，因为JSX语法与JS不兼容，用来告知Browser对其转换。

`this.props.children`

>有三种可能，未定义的`undefined`、单一子节点的`object`、多个子节点的`array`。

`React.Children`

>`React`提供了这个方法来方便我们处理`this.props.children`，我们此处使用`React.children.map`来遍历子节点，用这个方法的好处是可以完全忽略`this.props.children`的类型。[官方文档](https://facebook.github.io/react/docs/top-level-api.html#react.children)