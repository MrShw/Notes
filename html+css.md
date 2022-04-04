# 前端三件套

1. HTML 是网页结构。
2. CSS 是显示效果。
3. JS 是动作，互动。

HTML 标签不区分大小写，`<h1>`和`<H1>`是一样的，但建议小写，因为大部分程序员都以小写为准。

参考网站：

```
https://developer.mozilla.org/en-US/
https://github.com/Forece/notes/blob/master/CSS.md
```

# HTML

```
<html>

    <head>
        <title>...</title>
        <meta>
        <link>
        <style>...</style>
        <script>...</script>
    </head>

    <body>
        <h1> 文章的标题  </h1>
        <p> 段落文本 </p>
        <q> 引用文本 </q>
        <br/> 换行
        <hr/> 分割线
        <div> 模块 </div>
        <blockquote> 引用文本 </blockquote>

        超链接：
        <a href=”目标网址”> 链接显示的文本 </a>

        插入图片：
        <img src="图片地址" alt="下载失败时的替换文本" title = "提示文本">

        无序列表
        <ul>
          <li> 信息 </li>
          <li> 信息 </li>
        </ul>

        有序列表
        <ol>
           <li> 信息 </li>
           <li> 信息 </li>
        </ol>

        表格



    </body>

</html>
```

<br>
创建表格的五个元素：table、tbody、tr(行)、th(表头)、td(单元格)

<br>

```
<table>
    <thead>
        <tr>
            <th colspan="3">"table header"</th>
        </tr>
        <tr>
            <th>国家</th>
            <th>年份</th>
            <th>熊猫</th>
        </tr>
    </thead>

    <tbody>
        <tr>
            <td>墨西哥</td>
            <td>1975</td>
            <td>迎迎、贝贝</td>
        </tr>
        <tr>
            <td>台湾</td>
            <td>2008</td>
            <td>团团、圆圆</td>
        </tr>
        <tr>
            <td>日本</td>
            <td>2011</td>
            <td>比力、仙女</td>
        </tr>
    </tbody>

    <tfoot>
        <td colspan="3">末行</td>
    </tfoot>
</table>
```

<br>
表单，表单是可以把浏览者输入的数据传送到服务器端，这样服务器端程序就可以处理表单传过来的数据。

```
<form action="服务器文件" method="传送方式"> 表单标签 </form>

<label for="email"> 邮箱 </label>

<input id ="email" type="" name="文本框命名" value="默认显示值，起提示作用" />

<select> 下拉选择 </select>

<datalist> 预设data，可以输入 </datalist>


```

<br>

- type: 当 type="radio"时，控件为单选框；当 type="checkbox"时，控件为复选框
- value：提交数据到服务器的值（后台程序 PHP 使用）
- required="" 要求必须填写

```
<html>

    <head>
        <title> 熊猫问卷调查 </title>
        <meta>
        <link>
        <style>...</style>
        <script>...</script>
    </head>

    <body>
        <form action="服务器文件" method="传送方式">

            输入框设置：
            <label for="email">邮箱</label>
            <input id="email" type="email" name="" value="@163.com" required="">

            不能输入，只能选：
            <label for="occupation">职业</label>
            <select name="occupation" id="occupation" required="">
                <option value="accountant">会计</option>
                <option value="sales">销售</option>
                <option value="management">管理</option>
            </select>


            预设多个data，可以输入：
            <label for="area">地区</label>
            <input type="text" name="area" id="area" value="" list="areaList">
            <datalist id="areaList">
                <option value="北京">北京</option>
                <option value="上海">上海</option>
                <option value="深圳">深圳</option>
            </datalist>



            <button type="submit">提交表格</button>

        </form>
    </body>

</html>
```

# CSS

CSS 全称为“层叠样式表 (Cascading Style Sheets)”，主要是用于定义 HTML 内容在浏览器内的显示样式，如文字大小、颜色、字体加粗等。

css 引入方式

1. 内联样式 (优先级最高)

```
<p style=font-size:30px; color:red;> TTT </p>
```

2. 内部样式

```
<style> </style>

<style>
            table, th, td{
                border-collapse:collapse;
                border: 1px solid black;
            }
            th,
            td{
                padding: 0.25rem;
            }

        </style>
```

3. 外部样式

```
<link> /*引入css文件 后缀.css*/

<link rel="stylesheet" href="./externalStyle.css">
```

css 样式由选择符和声明组成，而声明又由属性和值组成，例如：

```
选择器{
    属性:值;
    属性:值;
    属性:值;
}
```

如下列代码：

```
p{
   font-size:12px;
   color:red;
   font-weight:bold;
}
```

使用 CSS 样式的一个好处是通过定义某个样式，可以让不同网页位置的文字有着统一的字体、字号或者颜色等。

## 文字\段落设置

文字排版

```
p{
    font-family:"宋体";
    font-weight:bold;
    font-size:12px;
    font-size:2rem; //2倍相对大小文字
    text-algin:center;
    text-decoration:underline;
    text-indent:15px; //p的留白
    color:#666
}

/* <span>是一个行内标签，用来组合行内的多个元素 */
```

<br>

背景设置

```
body{
    background-image: url("图片路径");
}

h1.heading{
background-color: brown;
color: white;
padding: 1rem 2rem;
border: 10px solid blue;/_solid 实线，dash 虚线_/
}

```

## 选择器

CSS 选择器的解析是从上到下，从右向左解析，为了避免对所有元素进行解析

- 可继承的样式：font-size, font-family, color，ul，li，dl，dt，dd；
- 不可继承的样式：border, padding, margin, width, height

<br>
选择器包括：

```

通用选择器 它使用一个（\*）号指定
标签选择器 p{font-size:12px}
类选择器 .类选器名称 h1.reText
ID 选择器 #id 名称
分组选择器 h1, h2
子选择器 父标签.类 子标签
属性选择器 input[type = "text"]
伪选择器 textarea:hover p::first-letter

```

在选择使用哪个配置上，与特定度（specificity）有关，其中，优先级由高到低为

```

!important > 内联 style > ID 选择器 > 类(class)选择器 > 标签(tag)选择器 > 通配符选择器 > 继承

```

子选择器

> 按标签等级划分，例如< body>是< h1>的父级， < div> 是 < a> 的父级

例如

```

div.link1 a{
color:red;
}

<div class="link1">
    <a href="./myForm.html">熊猫问卷调查</a>
</div>

```

分组选择器

```

h1,
h2{
color:red;
}

```

属性选择器

```

input[type="text"]{
color:red;
}

```

伪选择器

> 如果需要添加新元素加以标识的，就是伪元素，反之，如果只需要在既有元素上添加类别的，就是伪类

```

:hover
:active
:focus
:first-child

::first-letter 选择元素中的第一个字符
::before 在元素在该元素之前添加内容
::after 在元素在该元素之后添加内容

```

> pseudo-class is a keyword added to a selector that specifies a special state of the selected element(s). For example, :hover can be used to change a button's color when the user's pointer hovers over it.
> 代码如：

```

/_ Any textarea over which the user's pointer is hovering _/
textarea:hover{
background:red;
}

```

> pseudo-element is a keyword added to a selector that lets you style a specific 【part】 of the selected element(s). For example, ::first-line can be used to change the font of the first line of a paragraph.

```

/_ The first line of every <p> element. _/
p::first-line {
color: blue;
text-transform: uppercase;
}

```

子标签会继承父级标签的设定，如果有子标签有单独设置，则不会继承。

---

## 盒模型

在讲解 CSS 布局之前，我们需要提前知道一些知识，在 CSS 中，html 中的标签元素大体被分为三种不同的类型：块状元素、内联元素和内联块状元素。

常用的块状元素有：

```

<div>、<p>、<h1>...<h6>、<ol>、<ul>、<dl>、<table>、<address>、<blockquote> 、<form>
```

常用的内联元素有：

```
<a>、<span>、<br>、<i>、<em>、<strong>、<label>、<q>、<var>、<cite>、<code>
```

常用的内联块状元素有：

```
<img>、<input>
```

所有 html 的元素都是 box，有：width，height，content，padding，boarder，margin 六个要素
margin 框距离页面边界，padding 内容距离框边界，boarder 外框（Excel 那种边框）

![盒模式](https://flomo.oss-cn-shanghai.aliyuncs.com/file/2022-04-02/146821/228531dd81ef23f5c8304f8862ff8ec2.png?OSSAccessKeyId=LTAI4G9PcaGksWVKCPrE1TVL&Expires=1649102322&Signature=v%2Bf%2BrSIOKDdwF2D1QmcUws4DCs8%3D "盒模式")

```
button.example{
    /* content, border, width, height, padding, margin */

    padding-top: 150px;
    padding-right: 50px;
    padding-bottom: 120px;
    padding-left: 20px;


    padding: 150px 50px 120px 20px; /*上 右 下 左*/

    padding: 20px 150px; /*上下 左右*/

    padding: 200px; /*上下左右*/
}


div.pic{
    width: 500px;
    height: 2000px;

    margin:1rem 2rem; //上下1rem 左右2rem

    border:10px solid black;

    background-color: green;
    position: relative;

    /* bottom: 100px; */
    top: 200px;
    left: 200px;
    z-index: 2; /*数字大的在上面 */

}
```

relative units 设置：1）% 相对于 parent element；2）vw,viewport width，90；3）vh，viewport height，20

## position 定位

常规取值： 1.static(静态） 2.Relative(相对） 3.Absolute(绝对) 4.fixed(固定)

## display 布局

CSS 包含 3 种基本的布局模型，用英文概括为：Flow、Layer 和 Float。
