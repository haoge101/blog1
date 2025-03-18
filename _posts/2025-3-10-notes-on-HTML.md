---
title: HTML 入门笔记
date: 2025-3-10 12:16:40 +0800
categories: [Study] # 目前有 Demo, Tutorial, Tech, Study
tags: [大学, 前端, 笔记]
author: Zwei  # 或 authors: [Zwei, another_author]
description: "2025年重制版HTML笔记"
image:
  path: https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250318220605289.png
permalink: '/w/notes-on-HTM'  # 自定义永久链接
pin: false # 置顶文章
toc: true # 显示目录
comments: true # 允许评论
math: true # 启用数学公式
mermaid: true # 启用 Mermaid 图表
render_with_liquid: false # 禁用 Liquid 渲染
media_subpath: /blog/assets/ # 资源路径前缀
---

### HTML笔记

#### VScode

**VSCode中文语言包安装：**

扩展 → 搜索Chinese → 点击安装

生成浏览器文件`.html`的快捷方式

```js
! + 回车
```

**VSCode常用快捷键列表**

1. 代码格式化：`Shift+Alt+F`
2. 向上或向下移动一行：`Alt+Up 或 Alt+Down`
3. 快速复制一行代码：`Shift+Alt+Up 或 Shift+Alt+Down`
4. 快速保存：`Ctrl + S`
5. 快速查找：`Ctrl + F`
6. 快速替换：`Ctrl + H`



##### VSCode插件

1. <img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250305201206708.png" alt="image-20250305201206708" style="zoom:67%;" />

   快捷键 ` Alt + B`



#### HTML介绍

HTML是超文本标记语言（HyperText Markup Language），markdown也是。

是一种用于创建网页的标准标记语言

> HTML不是编程语言，而是标记语言

#### 创建一个html

编辑器可以选择webstorm或者vscode

大部分编辑器，创建html文件都有默认填充

比如这是Frae的填充

```HTML
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <meta http-equiv='X-UA-Compatible' content='IE=edge'>
    <title>Page Title</title>
    <meta name='viewport' content='width=device-width, initial-scale=1'>
    <link rel='stylesheet' type='text/css' media='screen' href='main.css'>
    <script src='main.js'></script>
</head>
<body>
    
</body>
</html>>
```



#### HTML5介绍


HTML5是用来描述网页的一种语言，被称为超文本标记语言。用HTML5编写的文件，后缀以`.html`结尾

HTML是一种标记语言，标记语言是一套标记标签。标签是由尖括号包围的关键字，例如：`<html>`

标签有两种表现形式：

1. 双标签，例如：`<html></html>`
2. 单标签，例如：`<img>`



#### HTML5的DOCTYPE声明

DOCTYPE是`document type` (文档类型) 的缩写。`<!DOCTYPE html >`是H5的声明位于文档的最前面，处于标签之前。
他是网页必备的组成部分，避免浏览器的怪异模式。

```js
<!DOCTYPE html>
```

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250305194325392.png" alt="image-20250305194325392" style="zoom:80%;" />

#### HTML5基本骨架

##### html标签

定义 HTML 文档，这个元素我们浏览器看到后就明白这是个HTML文档了，所以你的其它元素要包裹在它里面，标签限定了文档的开始点和结束点。

```html
<!DOCTYPE html>
<html>
</html>
```

##### head标签

head标签用于定义文档的头部。

+ 文档的头部描述了文档的各种属性和信息，包括文档的标题、在 Web 中的位置以及和其他文档的关系等。绝大多数文档头部包含的数据都不会真正作为内容显示给读者。

```html
<!DOCTYPE html>
<html>
    <head>
    </head>
</html>
```

##### body标签

body 元素定义文档的主体。

+ body 元素包含文档的所有内容（比如文本、超链接、图像、表格和列表等等。）

+ 它会直接在页面中显示出来，也就是用户可以直观看到的内容

```html
<!DOCTYPE html>
<html>
    <head>
    </head>
    <body>
        我会显示在浏览器中
    </body>
</html>
```

##### title标签

定义文档的标题。

1. 它显示在浏览器窗口的标题栏或状态栏上。
2. `<title>` 标签是 `<head>` 标签中唯一必须要求包含的东西，就是说写head一定要写title
3. `<title>`的增加有利于SEO优化

> SEO是搜索引擎优化的英文缩写。通过对网站内容调整，满足搜索引擎的排名需求


```html
<!DOCTYPE html>
<html>
    <head>
        <title>第一个页面</title>
    </head>
    <body>
        我会显示在浏览器中
    </body>
</html>
```

##### meta标签

meta标签用来描述一个HTML网页文档的属性，关键词等，例如：`charset="utf-8"`是说当前使用的是`utf-8`编码格式，在开发中我们经常会看到`utf-8`，或是`gbk`，这些都是编码格式，通常使用`utf-8`。

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>itbaizhan</title>
    </head>
    <body>
    </body>
</html>
```



#### 标题标签

##### 标题介绍与应用

标题（Heading）是通过 `<h1> - <h6> `标签进行定义的。

`<h1>`定义最大的标题   `<h6>`定义最小的标题

```html
<h1>一级标题</h1>
<h2>二级标题</h2>
<h3>三级标题</h3>
<h4>四级标题</h4>
<h5>五级标题</h5>
<h6>六级标题</h6>
```

> 生成h1~h6快捷键：h$*6

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250305201315995.png" style="zoom:67%;" />

**正确使用标题**

请确保将 HTML 标题标签只用于标题。

不要仅仅是为了生成粗体或大号的文本而使用标题。

正确使用标题有益于SEO

应该将`< h1>` 用作主标题（最重要的），其后是 `<h2>`（次重要的），再其次是 `<h3>`，以此类推

**标题标签位置摆放**

在标签中添加属性：`align="left | center | right"` 默认居左

```html
    <h1 align="left">一级标题</h1>
    <h2 align="center">二级标题</h2>
    <h3 align="right">三级标题</h3>
```

![image-20250305203224885](https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250305203224885.png)



#### 段落标签

段落是通过`<p>`标签定义的

```html
<p>这是一个段落 </p> 
<p>这是另一个段落</p>
```

##### 换行

如果您希望在不产生一个新段落的情况下进行换行（新行），请使用 `<br>`

`<br />` 元素是一个空的 HTML 元素。

```html
<p>这个<br>段落<br>演示了分行的效果</p>
```

##### 水平线

`<hr/>`标签在 HTML 页面中创建水平线

```html
<hr color="" width="" size="" align=""/>
```

属性：

1. color：设置水平线的颜色
2. width：设置水平线的宽度
3. size：设置水平线的高度
4. align：设置水平线的对齐方式（默认居中），可取值left|right



#### 标签之图片

`<img>` 标签定义 HTML 页面中的图像

```html
<img src="" alt="" title="" width="" height="">
```

> **注意事项**
>
> `<img>`是单标签，不需要进行闭合操作

属性：

1. src：路径（图片地址与名字）
2. alt：规定图像的替代文本
3. width：规定图像的宽度
4. height：规定图像的高度
5. title：鼠标悬停在图片上给予提示

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <img src="辛普森.gif" alt="测试图片" width="200" height="auto" title="辛普森">
    <br>
    <img src="../images/辛普森.gif" alt="测试图片" width="300" height="auto" title="辛普森">
    <br>
    <img src="https://s21.ax1x.com/2024/07/02/pkguIN4.md.jpg" alt="" height="200">
</body>
</html>
```

##### 路径

+ 绝对路径
+ 相对路径
  + 子级关系: `/`
  + 父级关系: `../`

  + 同级关系: `./`（可以省略）
+ 网络路径



#### 超文本链接标签

1. HTML使用标签 `<a>`来设置超文本链接

   超链接可以是一个字，一个词，或者一组词，也可以是一幅图像，您可以点击这些内容来跳转到新的文档

   ```html
   <a href="full_url">链接文本</a>
   ```


**\#** 在标签`<a> `中使用了**`href`**属性来描述链接的地址

默认情况下，链接将以，以下形式出现在浏览器中：

1. 一个**未访问**过的链接显示为**蓝色**字体并带有下划线。

2. **访问过**的链接显示为**紫色**并带有下划线。

3. **点击链接时**，链接显示为**红色**并带有下划线。

##### 属性：

target：

- _blank表示在新标签页中打开目标网页
- _self表示在当前标签页中打开目标网页

download：用于下载



#### 常用文本标签

|    标签    |        描述        |
| :--------: | :----------------: |
|   `<em>`   |    定义着重文字    |
|   `<b>`    |    定义粗体文本    |
|   `<i>`    |     定义斜体字     |
| `<strong>` |    定义加重语气    |
|  `<del>`   |     定义删除字     |
|  `<span>`  | 元素没有特定的含义 |

> **特别提示**
>
> 常用文本标签和段落<p></p>是不同的，段落代表一段文本，而文本标签一般表示文本词汇

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250308205856842.png" alt="image-20250308205856842" style="zoom:80%;" />

#### 有序列表标签

有序列表是一列项目，列表项目使用数字进行标记。 有序列表始于` <ol>` 容器标签。每个列表项始于 `<li> `标签。

```html
    <ol>
        <!-- 有序列表 -->
        <li>iphone</li>
        <li>huawei</li>
        <li>xiaomi</li>
        <li>vivo</li>
        <li>oppo</li>
        <li>oneplus</li>
    </ol>
```

##### type属性

`<ol>`的属性type 拥有的选项

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250308210826466.png" alt="image-20250308210826466" style="zoom:67%;" />

1. 1   表示列表项目用数字标号（1,2,3...）
2. a   表示列表项目用小写字母标号（a,b,c...）
3. A  表示列表项目用大写字母标号（A,B,C...）
4. i   表示列表项目用小写罗马数字标号（i,ii,iii...）
5. I   表示列表项目用大写罗马数字标号（I,II,III...）



##### 有序列表嵌套

列表是可以进行嵌套的

```html
    <ol type="A">
        <li>水果
            <ol>
                <li>苹果</li>
                <li>香蕉</li>
                <li>橘子</li>
            </ol>
        </li>
        <li>蔬菜
            <ol>
                <li>白菜</li>
                <li>萝卜</li>
            </ol>
        </li>
        <li>其他</li>
    </ol>
```

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250308211414682.png" style="zoom:50%;" />

#### 无序列表

无序列表是一个项目的列表，此列项目使用粗体圆点（典型的小黑圆圈）进行标记

无序列表始于 `<ul>` 标签。每个列表项始于` <li>` 标签。

```html
    <ul tyep="disc">
        <li>苹果</li>
        <li>香蕉</li>
        <li>橘子</li>
    </ul>
```

##### type属性

`<ul>`的属性type 拥有的选项

- disc 默认实心圆

- circle 空心圆

- square 小方块

- none 不显示

##### 无序列表嵌套

列表是可以进行嵌套的

```html
    <ul>
        <li>组1
            <ul type="square">
                <li>苹果</li>
                <li>香蕉</li>
                <li>橘子</li>
            </ul>
        </li>
        <li>组2
            <ul type="circle">
                <li>苹果</li>
                <li>香蕉</li>
                <li>橘子</li>
            </ul>
        </li>
    </ul>
```

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250308213458842.png" alt="image-20250308213458842" style="zoom:67%;" />

##### 常见应用场景

1. 无序的列表效果
2. **导航效果**

**快捷键**

快速生成ul+li的布局：ul>li*3（数字根据自己的需要的li数量修改）

```html
<!-- ul>li*5 -->
</body><ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ul>
```



#### 表格标签

表格在数据展示方面非常简单，并且表现优秀

**表格组成与特点**

+ 行、列、单元格 

+ 单元格特点：同行等高、同列等宽

**表格标签**

+ 表格：`<table>`
+ 行：`<tr>`

+ 单元格(列)：`<td>`

```html
    <table>
        <thead>
            <td>表头1</td>
            <td>表头2</td>
            <td>表头3</td>
        </thead>
        <tbody>
        <tr>
            <td>a</td>
            <td>b</td>
            <td>c</td>
        </tr>
        <tr>
            <td>1</td>
            <td>2</td>
            <td>3</td>
        </tr>
        </tbody>
    </table>
```

![image-20250308223125716](https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250308223125716.png)

**快捷键**

快速生成表格结构：table>tr*N>td\*n{单元格文本}

##### 表格属性

1. border：设置表格的边框
2. width：设置表格的宽度
3. height：设置表格的高度
4. thead：表头
5. tbody：表身

##### 单元格合并属性

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250308224709848.png" alt="image-20250308224709848" style="zoom:80%;" />

- **水平合并（n列）：colspan=“n” **合并右侧
- **垂直合并（n行）：rowspan=“n”** 合并下方

```html
<table border="1" width="500px" height="200px">
    <tr>
        <td colspan="3">单元格1单元格2单元格3</td>
        <td>单元格4</td>
        <td>单元格5</td>
    </tr>
    <tr>
        <td rowspan="2">单元格6-11</td>
        <td>单元格7</td>
        <td rowspan="3">单元格81318</td>
        <td colspan="2" rowspan="2">单元格9101415</td>
    </tr>
    <tr>
        <td>单元格12</td>
    </tr>
    <tr>
        <td>单元格16</td>
        <td>单元格17</td>
        <td>单元格19</td>
        <td>单元格20</td>
    </tr>
</table>
```

#### input标签（用户输入交互）

| type属性值 | 表现形式     | 对应代码                                    |
| ---------- | ------------ | ------------------------------------------- |
| text       | 单行输入文本 | \<input type=text" />                       |
| password   | 密码输入框   |                                             |
| date       | 日期输入框   |                                             |
| checkbox   | 复选框       | \<input type="checkbox" name="fluit"> apple |
| radio      | 单选框       | \<input type="radio" name="fluit"> apple    |
| submit     | 提交按钮     |                                             |
| reset      | 重置按钮     |                                             |
| disabled   | 禁用         | disabled                                    |
| button     | 普通按钮     |                                             |
| hidden     | 隐藏输入框   |                                             |
| file       | 文本选择框   |                                             |

属性说明：

- name：表单提交时的“键”，注意和id的区别
- value：表单提交时对应项的值
  - type="button", "reset", "submit"时，为按钮上显示的文本内容
  - type="text","password","hidden"时，为输入框的初始值
  - type="checkbox", "radio", "file"，为输入相关联的值
- checked：radio和checkbox默认被选中的项
- readonly：text和password设置只读
- disabled：禁用，所有input均适用

#### label标签

##### label标签中的for属性会和input中的id关联。也就是说，其他input标签要设置一个 id 属性，用 label 标签的 for = “id” 进行关联，然后，label 起到了 input 相同的功能。

```HTML
<label for="user">
    用户名
</label>
<input placeholder="请输入用户名" id="user">
```

### select

属性：mutiple 多选

```
<select name="选择1">
    <option value="1">选择1</option>
    <option value="2">选择2</option>
    <option value="3">选择3</option>
   
   </select>
```


![image-20250309103707807](https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250309103707807.png)

#### Form表单

表单在 Web 网页中用来给用户填写信息，从而能采集用户信息，使网页具有交互的功能。

所有的用户输入内容的地方都用表单来写，如登录注 册、搜索框

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250308225937165.png" alt="image-20250308225937165" style="zoom: 50%;" />

表单是由容器和控件组成的,一个表单一般应该包含用户填写信息的输入框,按钮等，这些输入框,按钮叫做控件,表单就是容器,它能够容纳各种各样的控件

```html
<form action="url" method="get|post" name="myform"></form>

```

> **属性说明**
>
> action服务器地址
>
> name表单名称
>
> **method中Get和Post的区别**
>
> 1. 数据提交方式，get把提交的数据url可以看到，post看不到
> 2. get一般用于提交少量数据，post用来提交大量数据

##### 表单元素

一个完整的表单包含三个基本组成部分：表单标签、表单域、表单按钮

1. 表单标签
2. 表单域
3. 表单按钮

```html
        用户名 <input type="text">
        <br>
        邮箱 <input type="text">
        <br>
        密码 <input type="password">
        <br>
        <input type="submit">
    </form>
```

| 属性           | 描述                                                     |
| -------------- | -------------------------------------------------------- |
| placeholder    | 替代文字，输入框中提示                                   |
| accept-charset | 规定在被提交表单中使用的字符集（默认：页面字符集）       |
| action         | 规定向何处提交表单的地址（URL）（提交页面）              |
| autocomplete   | 规定浏览器应该自动完成表单（默认：开启）                 |
| enctype        | 规定被提交数据的编码（默认：url-encoded）                |
| method         | 规定在提交表单时所用的 HTTP 方法（默认：GET）            |
| name           | 规定识别表单的名称（对于 DOM 使用：document.forms.name） |
| novalidate     | 规定浏览器不验证表单                                     |
| target         | 规定 action 属性中地址的目标（默认：_self）              |

表单里面一般会有一个submit的input标签，用于提交



#### 块元素与行内元素（内联元素）

HTML5出现之前，经常把元素按照块级元素和内联元素来区分。在HTML5中，元素不再按照这种⽅式来区分， 而是按照内容模型来区分，分为元数据型(metadata content)、区块型(sectioning content)、标题型(heading content)、文档流型(flow content)、语句型(phrasing content)、内嵌型(embedded content)、交互型 (interactive content)。元素不属于任何⼀个类别，被称为穿透的，元素可能属于不止⼀个类别，称为混合的

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250309093456372.png" alt="image-20250309093456372" style="zoom:67%;" />

虽然到了HTML5的版本，元素分类更细致了，但是这对初学者并不友好,所以我们仍然按照块元素和内联元素做区分，这对我们的布局起到了至关重要的作用



**内联元素和块级元素的区别**

|                   块级元素                   |                   内联元素                   |
| :------------------------------------------: | :------------------------------------------: |
| 块元素会在页面中独占一行（自上向下垂直排列） | 行内元素不会独占页面中的一行，只占自身的大小 |
|          可以设置width，height属性           |      行内元素设置width，height属性无效       |
|  ⼀般块级元素可以包含行内元素和其他块级元素  |    ⼀般内联元素包含内联元素不包含块级元素    |

常见块级元素

+ div、form、h1~h6、hr、p、table、ul、等

常见内联元素（行内元素）

+ a、b、em、i、span、strong等 

行内块级元素（特点：不换行、能够识别宽高）

+ button、img、input等 



#### HTML5新增标签

`HTML5`是`HTML`最新的修订版本，2014年10月由万维网联盟`（W3C）`完成标准制定

在`HTML5`出现之前，我们一般采用`DIV+CSS`布局我们的页面。但是这样的布局方式不仅使我们的文档结构不够清晰，而且**不利于搜索引擎爬虫对我们页面的爬取**。为了解决上述缺点，`HTML5`新增了很多新的语义化标签

**`div`容器元素，也是页面中见到的最多的元素**

span是行内标签中的默认标签

div是块级标签中的默认标签

方便去通过css设置样式

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250309095131852.png" alt="image-20250309095131852" style="zoom:67%;" />

H5实现 div 容器的效果

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250309095138912.png" alt="image-20250309095138912" style="zoom:67%;" />

**H5新标签**

1. `<header></header>`  头部
2. `<nav></nav>`  导航
3. `<section></section>`定义文档中的节,比如章节、页眉、页脚
4. `<aside></aside>`  侧边栏
5. `<footer></footer>` 脚部
6. `<article></article>`  代表一个独立的、完整的相关内容块,例如一篇完整的论坛帖子，一篇博客文章，一个用户评论等
