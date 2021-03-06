## 第一章-JavaScript 基础
#### 如何插入JS
- \<script>标签要成对出现，并把JavaScript代码写在\<script>\</script>之间。
- \<script type="text/javascript">表示在\<script>\</script>之间的是文本类型(text),javascript是为了告诉浏览器里面的文本是属于JavaScript语言。

#### 引用JS外部文件
- 可以把HTML文件和JS代码分开,并单独创建一个JavaScript文件(简称JS文件),其文件后缀通常为.js，然后将JS代码直接写在JS文件中。
- 在JS文件中，不需要\<script>标签,直接编写JavaScript代码就可以了。

#### JS在页面中的位置
- 可以将JavaScript代码放在html文件中任何位置，但是我们一般放在网页的head或者body部分。
- 放在\<head>部分：
最常用的方式是在页面中head部分放置\<script>元素，浏览器解析head部分就会执行这个代码，然后才解析页面的其余部分。
- 放在\<body>部分：
JavaScript代码在网页读取到该语句的时候就会执行。
- javascript作为一种脚本语言可以放在html页面中任何位置，但是浏览器解释html时是按先后顺序的，所以前面的script就先被执行。比如进行页面显示初始化的js必须放在head里面，因为初始化都要求提前进行（如给页面body设置css等）；而如果是通过事件调用执行的function那么对位置没什么要求的。

#### 认识语句和符号
- JavaScript语句是发给浏览器的命令。这些命令的作用是告诉浏览器要做的事情。
- 每一句JavaScript代码格式: **语句;**

#### 注释很重要
- 单行注释，在注释内容前加符号 “//”。
- 多行注释以"/\*"开始，以"\*/"结束。

#### 判断语句（if...else）
```
if(条件)
{ 条件成立时执行的代码 }
else
{ 条件不成立时执行的代码 }
```

## 第二章-常用互动方法
#### 输出内容（document.write）
document.write() 可用于直接向 HTML 输出流写内容。简单的说就是直接在网页中输出内容。
- 第一种:输出内容用""括起，直接输出""号内的内容。
- 第二种:通过变量，输出内容
- 第三种:输出多项内容，内容之间用+号连接。

#### 警告（alert 消息对话框）
在访问网站的时候，有时会突然弹出一个小窗口，上面写着一段提示信息文字。如果你不点击“确定”，就不能对网页做任何操作，这个小窗口就是使用alert实现的。
- alert(字符串或变量);  

#### confirm 消息对话框
confirm 消息对话框通常用于允许用户做选择的动作，如：“你对吗？”等。弹出对话框(包括一个确定按钮和一个取消按钮)。
- confirm(str);
- str：在消息对话框中要显示的文本
- 返回值: Boolean值

#### prompt 消息对话框
prompt弹出消息对话框,通常用于询问一些需要与用户交互的信息。弹出消息对话框（包含一个确定按钮、取消按钮与一个文本输入框）。
- prompt(str1, str2);
- 参数说明：str1: 要显示在消息对话框中的文本，不可修改，str2：文本框中的内容，可以修改
- 返回值:1. 点击确定按钮，文本框中的内容将作为函数返回值，2. 点击取消按钮，将返回null

#### 打开新窗口
open() 方法可以查找一个已经存在或者新建的浏览器窗口。
- window.open([URL], [窗口名称], [参数字符串])

**参数说明:**
- URL：可选参数，在窗口中要显示网页的网址或路径。如果省略这个参数，或者它的值是空字符串，那么窗口就不显示任何文档。
- 窗口名称：可选参数，被打开窗口的名称。
    1.该名称由字母、数字和下划线字符组成。
    2."\_top"、"\_blank"、"\_self"具有特殊意义的名称。
       \_blank：在新窗口显示目标网页
       \_self：在当前窗口显示目标网页
       \_top：框架网页中在上部窗口中显示目标网页
    3.相同 name 的窗口只能创建一个，要想创建多个窗口则 name 不能相同。
   4.name 不能包含有空格。
- 参数字符串：可选参数，设置窗口参数，各参数用逗号隔开。

#### 关闭窗口
- close()关闭窗口
- window.close();   //关闭本窗口
- <窗口对象>.close();   //关闭指定的窗口

## 第三章-DOM操作
#### 认识DOM
文档对象模型DOM（Document Object Model）定义访问和处理HTML文档的标准方法。DOM 将HTML文档呈现为带有元素、属性和文本的树结构（节点树）。

HTML文档可以说由节点构成的集合，三种常见的DOM节点:
- 1. 元素节点：上图中<html>、<body>、<p>等都是元素节点，即标签。
- 2. 文本节点:向用户展示的内容，如<li>...</li>中的JavaScript、DOM、CSS等文本。
- 3. 属性节点:元素属性，如\<a>标签的链接属性href="http://www.imooc.com"。

#### 通过ID获取元素
学过HTML/CSS样式，都知道，网页由标签将信息组织起来，而标签的id属性值是唯一的。那么在网页中，我们通过id先找到标签，然后进行操作。
- document.getElementById(“id”)；
- 获取的元素是一个对象，如想对元素进行操作，我们要通过它的属性或方法。

#### innerHTML 属性
innerHTML 属性用于获取或替换 HTML 元素的内容。
- Object.innerHTML；
- Object是获取的元素对象，如通过document.getElementById("ID")获取的元素。
- 注意书写，innerHTML区分大小写。

#### 改变 HTML 样式
HTML DOM 允许 JavaScript 改变 HTML 元素的样式。
- Object.style.property=new style;
- :Object是获取的元素对象，如通过document.getElementById("id")获取的元素。

#### 显示和隐藏（display属性）
网页中经常会看到显示和隐藏的效果，可通过display属性来设置。
- Object.style.display = value；
- :Object是获取的元素对象，如通过document.getElementById("id")获取的元素。

#### 控制类名（className 属性）
className 属性设置或返回元素的class 属性。
- object.className = classname
- 获取元素的class 属性
- 为网页内的某个元素指定一个css样式来更改该元素的外观
