### Dom的概念：

```
    Document   Object   Model -- DOM
    文档        对象      模型
    DOM是针对HTML和XML文档的一个API。
    DOM描绘了一个层次化的节点树，即HTML文档中的所有内容都是节点(node)。
    DOM树中的所有节点均可通过JS进行访问，允许开发人员添加、移除、修改和查询页面的某一部分。
```

### 节点类型：

```
1、	整个文档是一个文档节点
	 每个HTML元素是元素节点
	 HTML元素内的文本是文本节点(回车也是文本节点)
	 每个HTML的属性是属性节点
	 注释是注释节点
2、	nodeType属性：返回一个整数，这个数值代表节点的类型
	元素节点  返回1
	文本节点  返回2
	属性节点  返回3
	注释节点  返回8 
	文档节点  返回9
3、 	nodeName属性:返回节点的名称
	元素节点的nodeName是标签名称(大写)
	属性节点的nodeName是属性名称
	文本节点的nodeName永远是#text
	注释节点的nodeName永远是#comment
	文档节点的nodeName永远是#document
4、nodeValue属性:返回节点的值
	对于元素节点：nodeValue返回值是undefined或null
	对于文本节点，nodeValue返回文本内容
	对于属性节点，nodeValue返回属性值
	对于注释节点,nodeValue返回注释内容
	对于文档节点,nodeValue返回null
对于元素节点，用innerHTML/innerText/value设置或取值

	
```

### 节点关系：

```
	节点之间的关系，通常用家庭中的辈分关系来描述。
	祖先 -> 父辈 -> 子女(兄弟姐妹) -> 子孙
	parentNode：父节点
	children：所有元素子节点
	childNodes：所有子节点 ，IE678与高版本浏览器返回值不一样
	回文本节点（回车）
    nextSibling：下一个兄弟节点
    previousSibling：上一个兄弟节点
    
    
    IE678不支持
    nextElementSibling
    previousElementSibling
    firstElementChild
    lastElementChild
```

### 节点方法：

```
	createElement(“标签名”) : 创建元素节点
	createTextNode(“”) : 创建文本节点
	var newNode=document.createElement('div');
	var textNode=document.createTextNode('文本内容');
	
	appendChild(node) : 末尾插入一个节点node
	insertBefore(newNode,target) : target之前插入节点node
	removeChild(node) : 移除某个子节点
	replaceChild(newNode,oldNode) : newNode替换oldNode
	
	document.getElementById('');
	document.getElementsByName('');// input 表单元素
	document.getElementsByTagName('');
	
	//IE678不支持
    document.getElementsByClassName('类名');
    document.querySelector('选择器');
    document.querySelectorAll('选择器');
    
    cloneNode(boolean) : 复制一个节点
    true：深复制，复制节点及其整个子节点树
    false : 浅复制，只复制节点本身。
	注：不会复制添加到DOM节点中的JS属性，例如事件处理程序等
	
	getAttribute(“name”)    获取节点上name属性的值
	setAttribute(“name”,“value”)    设置节点上name属性的值为value
	removeAttribute(“name”)     删除节点上的name属性
	getAttributeNode(“type”)    获取节点上type属性节点 
```

Offset/client系列属性：

```
    offsetLeft：获取对象左侧与定位父级之间的距离(默认是body)
    offsetTop：获取对象上侧与定位父 级之间的距离(默认是body)
    offsetWidth：获取元素自身的宽度（包含边框）
    offsetHeight：获取元素自身的高度（包含边框
    
    clientLeft、clientTop：获取元素内容到边框的距离，效果和边框宽度相同，很少使用
    clientWidth：获取元素自身的宽度（不含边框）
    clientHeight：获取元素自身的高度（不含边框）

    document.body.offsetWidth  body的宽度（包含边框）
    document.body.offsetHeight  body的高度（包含边框）

    document.body.clientWidth  body的宽度（不含边框）
    document.body.clientHeight  body的高度（不含边框）

    document.documentElement.offsetWidth  html文档的宽
    document.documentElement.offsetHeight  html文档高度
    
    document.documentElement.clientWidth  浏览器可视区宽度(不含滚动条位置)
    document.documentElement.clientHeight  浏览器可视区高度(不含滚动条位置)

    window.innerWidth 浏览器可视区宽度(含滚动条位置)
    window.innerHeight 浏览器可视区高度(含滚动条位置)
    document.documentElement.scrollWidth 网页正文全文宽，包括有滚动条时的未见区域document.documentElement.scrollHeight 网页正文全文高，包括有滚动条时的未见区域

```

