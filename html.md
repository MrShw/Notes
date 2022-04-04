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
