```
<link> /*引入css文件 后缀.css*/
<link rel="stylesheet" href="./externalStyle.css">
```

```
选择器{
    属性:值;
    属性:值;
    属性:值;
}
```
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

子选择器

> 按标签等级划分，例如< body>是< h1>的父级， < div> 是 < a> 的父级


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

伪类

```
:hover
:active
:focus
:first-child

/_ Any textarea over which the user's pointer is hovering _/

textarea:hover{
                background:red;
}
```

伪元素
```
::first-letter 选择元素中的第一个字符
::before 在元素在该元素之前添加内容
::after 在元素在该元素之后添加内容

/_ The first line of every <p> element. _/

p::first-line {
                color: blue;
                text-transform: uppercase;
}
```
