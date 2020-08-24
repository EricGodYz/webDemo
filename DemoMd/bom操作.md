### BOM：

```
BOM的概念与作用:
    Browser Object Model -- BOM
    浏览器  对象    模型
    BOM提供了独立于内容而与浏览器窗口进行交互的对象，核心对象是window。
    JavaScript语法的标准化组织是ECMA，DOM的标准化组织是W3C，BOM缺乏标准
    BOM最初是Netscape浏览器标准的一部分。直到HTML5发布，W3C将 BOM 主要内容纳入了 HTML5 规范之中。
    BOM是为了操作浏览器对象出现的API，window是其核心对象
    
```

### 原生对象与宿主对象:

```
   原生对象（本地对象）：native object
    ECMA所定义的对象
    Number、String、Boolean、Object、Array、Function、Date、RegExp、内置对象(如 Math不需要实例化)、Error .....
    
    宿主对象：host object（ 如 window、BOM、DOM ）
    什么是宿主？web的运行环境，即操作系统、浏览器,宿主提供的对象 -> 宿主对象
```

### window对象：

```javascript
window对象是浏览器中的Global对象
 
    var newWindow = window.open(URL,name,specs);  返回一个新窗口
    URL：打开页面的URL，没有指定URL将打开新的空白窗口
    name：_blank  新窗口打开，默认
          _self  当前页面打开
          .....
    specs：一个逗号分隔的项目列表。支持以下值：
                width=pixels    height=pixels  最小值为100
                left=pixels     top=pixels    ......
    示例 window.open('','','left=200,top=100,width=400,height=200');

    window.close() 方法用于关闭浏览器窗口(新打开的);

    调整窗口大小  window.resizeTo(width,height);
    调整窗口大小 window.resizeBy(width,height);
    注：此功能在一些标签型浏览器中无效。
    
    window.scrollTo(x,y) 方法可把页面内容滚动到指定的坐标。
    window.scrollX  页面水平方向滚动的像素值
    window.scrollY  页面垂直方向滚动的像素值

    window.screenLeft 属性返回窗口相对于屏幕的X坐标
    window.screenTop 属性返回窗口相对于屏幕的Y坐标
    window.screenX 属性返回窗口相对于屏幕的X坐标
    window.screenY 属性返回窗口相对于屏幕的Y坐标

    window.setInterval ( 函数/名称 , 毫秒数 )
    表示每经过一定的毫秒后，执行一次相应的函数(重复)
    window.setTimeout ( 函数/名称 , 毫秒数 )
    表示经过一定的毫秒后，只执行一次相应的函数(不重复)
    清除计时器：clearInterval( );      clearTimeout( );

    提示框 alert (“ ”);
    用户必须先关闭该消息框然后才能继续进行操作
    确认框 confirm(“ ”);
    confirm(“需要确认的内容”);
    选择“确定”返回true        选择“取消”返回false
    输入框 prompt(“ ”,“ ”);
    prompt(“对话框的提示文本”,"默认的输入文本");
    单击取消，则返回 null；单击确认，则返回输入的文本
```

### history对象：

```
    history对象包含有关用户的访问历史记录
    length 返回浏览器历史列表中的 URL 数量
    forward() 加载 history 列表中的下一个 URL
    back() 加载 history 列表中的上一个 URL
    go() 加载 history 列表中的某个具体页面
    history.go(-1)    后退一页
    history.go(1)    前进一页
```

### location对象：

```
    location对象包含有关当前页面的URL信息
    host 属性设置或返回主机名和当前 URL 的端口号
    port 属性设置或返回当前 URL 的端口号
    href 属性设置或返回完整的 URL    ……
    assign() 方法加载新的文档
    reload() 方法重新加载当前文档（刷新）
    replace() 方法用新的文档替换当前文档
```

### navigator对象：

```
	   navigator对象用于提供与用户浏览器相关的信息
        appCodeName 属性返回浏览器的代码名
        appName 属性返回浏览器的名称
        cookieEnabled 属性返回指明浏览器中是否启用cookie的布尔值
        platform 属性返回运行浏览器的操作系统平台
        appVersion 属性返回浏览器的平台和版本信息
        userAgent 属性返回用户浏览器发送服务器的user-agent头部的值

        识别浏览器
        var str1=window.navigator.userAgent;
        var str2=window.navigator.appVersion;
        结合indexOf( )和toLowerCase( )方法可识别用户浏览器
```

### screen对象：

```
    screen对象包含有关客户端显示屏幕的信息
    width 属性返回显示器屏幕的宽度
    height 属性返回显示器屏幕的高度
    availHeight 属性返回显示屏幕的高度 (除 Windows 任务栏之外)
    availWidth 属性返回显示屏幕的宽度 (除 Windows 任务栏之外)
```

### document对象：

```
    Document 对象是 Window 对象的一部分，可通过 window.document 属性对其进行访问
    每个载入浏览器的 HTML 文档都会成为 Document 对象
    document 对象与它所包含的各种节点构成了早期的文档对象模型（DOM 0级）
    document：包含整个 HTML 文档，可被用来访问文档内容及其所有页面元素
```

