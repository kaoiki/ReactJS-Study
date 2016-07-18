#Lesson 2#

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
var brands = ['APPLE','MI','HUAWEI','OPPO','SAMSUNG'];

ReactDOM.render(
	<div>
		{
			brands.map(function (brand) {
				return <div> Brand is {brand}!</div>
            })
        }
    </div>,
    document.getElementById('react_output')
);
```
>上述功能就是讲遍历手动生成的数组并显示在浏览器界面上。

*部分代码解释*

`var brands = ['APPLE','MI','HUAWEI','OPPO','SAMSUNG'];`

**生成一个名字为brands的数组**

***


`brands.map(function (brand) {})`

**解析`brands`，遍历其内容并通过隐式调用函数方法进行显示，显示部分下部代码会说明，`function`中的`brand`则为遍历出来的数组节点内容**

***

`return <div> Brand is {brand}!</div>`

**基于遍历方法触发显示，`{}`为占位操作，并显示函数传入的参数`brand`的值**

***


`document.getElementById('react_output')`

**向ID为`react_output`的节点输出内容**

***


###说明

`
type=text/babel
`

>JSX需要加上该表情，因为JSX语法与JS不兼容，用来告知Browser对其转换。