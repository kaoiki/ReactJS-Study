#Lesson 4#

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

**被引用的函数就是输出如上一段内容，和之前一样，使用了两个`{}`占位操作，其内部用来输出当前组件的两个属性，属性名字分别为`what`和`name`，通过`this.props`对象获取属性内容**

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

`SayMessage`

>组件名称首字母必须大写，每个组件都需要有自己的render方法，用以输出。

`<SayMessage />`

>使用该语句后，会自动生成一个`SayMessage`的实例，记得此时必须有`/`关闭该组件，否则会无法输出

`className`及`htmlFor`

>`class`属性及`for`属性要写成`className`及`htmlFor`，因为`class`及`for`为JS保留字，具体写法后续课程会写到，此处只是有个概念

