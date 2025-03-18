---
title: CSS 入门笔记
date: 2025-3-10 12:16:40 +0800
categories: [Study] # 目前有 Demo, Tutorial, Tech, Study
tags: [大学, 前端, 笔记]
author: Zwei  # 或 authors: [Zwei, another_author]
description: "2025年重制版CSS笔记"
image:
  path: https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250318220137452.png
permalink: '/w/notes-on-CSS'  # 自定义永久链接
pin: false # 置顶文章
toc: true # 显示目录
comments: true # 允许评论
math: true # 启用数学公式
mermaid: true # 启用 Mermaid 图表
render_with_liquid: false # 禁用 Liquid 渲染
media_subpath: /blog/assets/ # 资源路径前缀
---

### CSS-Notes

#### CSS概念

CSS（Cascading Style Sheets）层叠样式表，又叫级联样式表，简称样式表

CSS文件后缀名为`.css`

CSS用于HTML文档中元素样式的定义

使用css的唯一目的就是让网页具有美观一致的页面



##### 语法

CSS 规则由两个主要的部分构成：**选择器，以及一条或多条声明（样式）**

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250309105930725.png" alt="image-20250309105930725" style="zoom:80%;" />

+ **选择器**通常是需要改变样式的 HTML 元素

+ **每条声明由一个属性和一个值组成**

属性（property）是您希望设置的样式属性（style attribute）。每个属性有一个值。属性和值被冒号分开

```css
<style>
    h1{
        color: blue;
        font-size: 12px;
    }
</style>
```

#### 引入CSS方式

##### 内联样式（行内样式）

要使用内联样式，你需要在相关的标签内使用样式（style）属性。Style 属性可以包含任何 CSS 属性

> **温馨提示**
>
> 缺乏整体性和规划性，不利于维护，维护成本高

```html
<p style="background: orange; font-size: 24px;">CSS<p>
```

##### 内部样式

当单个文档需要特殊的样式时，就应该使用内部样式表。你可以使用 `<style>` 标签在文档头部定义内部样式表

> **温馨提示**
>
> 单个页面内的CSS代码具有统一性和规划性，便于维护，但是在多个页面之间容易混乱

```html
<head>
    <style> 
       h1 { 
           background: red; 
       } 
    </style>
```

##### 外部样式（推荐）

当样式需要应用于很多页面时，外部样式表将是理想的选择。在使用外部样式表的情况下，你可以通过改变一个文件来改变整个站点的外观。每个页面使用 `<link>` 标签链接到样式表。 **`<link>` 标签在（文档的）头部**

```html
<link rel="stylesheet" type="text/css" href="public.css">
```

##### 全局选择器

可以与任何元素匹配，优先级最低，一般做样式初始化

```css
*{
     margin: 0;
     padding: 0;
 }
```

##### 元素选择器

HTML文档中的元素，`p、b、div、a、img、body`等。

标签选择器，选择的是页面上所有这种类型的标签，所以经常描述“共性”，无法描述某一个元素的“个性”

```css
p{
    font-size:14px;
}
```

再比如说，我想让“学完前端，继续学Java”这句话中的“前端”两个变为红色字体，那么我可以用`<span>`标签把“前端”这两个字围起来，然后给`<span>`标签加一个标签选择器

```html
<p>学完了<span>CSS</span>，继续学JS</p>
span{
	color: red;
}
```

> **温馨提示**
>
> 1. 所有的标签，都可以是选择器。比如ul、li、label、dt、dl、input、div等
> 2. 无论这个标签藏的多深，一定能够被选择上
> 3. 选择的所有，而不是一个

##### 类选择器

规定用圆点 `.` 来定义，针对你想要的所有标签使用

> **优点**
>
> 灵活

```html
    <style>
        .red {
            color: red;
        }
        .big {
            font-size: 20px;
        }
    </style>
...
    <p>段落1</p>
    <p class="red">段落2，但是我需要红色</p>
    <p>段落3</p>
    <p class="big">段落4，但是我需要大字体</p>
    <p>段落5</p>
    <p class="red big">段落6，但是我需要红色和大字体</p>
```

> **class属性的特点**
>
> 1. 类选择器可以被多种标签使用
> 2. 类名不能以数字开头
> 3. 同一个标签可以使用多个类选择器。用空格隔开

```html
<h3 class="red big">我是一个h3啊</h3> //正确
<h3 class="red" class="big">我是一个h3啊</h3>  // 错误
```

##### ID选择器

针对某一个特定的标签来使用，只能使用一次。`css`中的`ID选择器`以 `#` 来定义

```html
<h2 id="mytitle">你好</h2>
#mytitle{
    border:3px dashed green;
}
```

> **特别强调**
>
> 1. ID是唯一的
> 2. ID不能以数字开头

##### 交集选择器

语法：`.选择器1.选择器2,...{ }`

同时包含这些类的元素才会应用样式。

```
.header, .footer{
    height:300px;
}
```

##### 合并选择器（并集选择器）

语法：`.选择器1,.选择器2,...{ }`

包含这里面其中一个选择器就可以应用样式

```css
.header, .footer{
    height:300px;
}
```

##### 选择器的优先级

CSS中优先级从高到低：行内样式 > ID选择器 > 类选择器 > 元素选择器>全局选择器



##### 伪类选择器

`hover`： 鼠标触碰触发

`nth-child`：选择列表中的项 `ul li: ntl-child(公式)`

`first-child`

`last-child`

##### 否定伪类选择器

`:not(公式)`

##### 伪元素选择器

`before`

+ ```css
  .classname::before{ 
  content: “内容”
  }
  ```

+ 

`after`

不能被选中

---

##### box-sizing: border-box;

设置元素大小包括边框

---

#### 字体属性

##### color

规定文本的颜色

```css
div{ color:red;}
div{ color:#ff0000;}
div{ color:rgb(255,0,0);}
div{ color:rgba(255,0,0,.5);}
```

##### font-size

设置文本的大小

能否管理文字的大小，在网页设计中是非常重要的。但是，你不能通过调整字体大小使段落看上去像标题，或者使标题看上去像段落。

```css
h1 {font-size:40px;}
h2 {font-size:30px;}
p {font-size:14px;}
```

> **温馨提示**
>
> chrome浏览器接受最小字体是12px

##### font-weight

设置文本的粗细

| 值      | 描述                                       |
| ------- | ------------------------------------------ |
| bold    | 定义粗体字符                               |
| bolder  | 定义更粗的字符                             |
| lighter | 定义更细的字符                             |
| 100~900 | 定义由细到粗  400等同默认，而700等同于bold |

```css
H1 {font-weight:normal;}
div{font-weight:bold;}
p{font-weight:900;}
```

##### font-style

指定文本的字体样式

| 值     | 描述       |
| ------ | ---------- |
| normal | 默认值     |
| italic | 定义斜体字 |

##### font-family

font-family属性指定一个元素的字体

> **温馨提示**
>
> 每个值用逗号分开
>
> 如果字体名称包含空格，它必须加上引号

```css
font-family:"Microsoft YaHei","Simsun","SimHei";
```

##### 导入字体

使用@font-face进行导入

```CSS
@font-face {
    src: url("./ZiXiaoHunLiLiangCuHeiTi(ShangYongXuShouQuan)-2.ttf");
    font-family: "xxx";
}

.line {
    font-family: "xxx";
}
```

百度搜免费字体，很多都可以免费下载的

**CSS背景属性**

| 属性                | 描述                 |
| ------------------- | -------------------- |
| background-color    | 设置背景颜色         |
| background-image    | 设置背景图片         |
| background-position | 设置背景图片显示位置 |
| background-repeat   | 设置背景图片如何填充 |
| background-size     | 设置背景图片大小属性 |

##### background-color属性

该属性设置背景颜色

```css
<div class="box"></div>
.box{
    width: 300px;
    height: 300px;
    background-color: palevioletred;
}
```

##### background-image属性

设置元素的背景图像

元素的背景是元素的总大小，包括填充和边界（不包括外边距）。默认情况下background-image属性放置在元素的左上角，如果图像不够大的话会在垂直和水平方向平铺图像，如果图像大小超过元素大小从图像的左上角显示元素大小的那部分

```css
<div class="box"></div>
.box{
    width: 600px;
    height: 600px;
    background-image: url("images/img1.jpg");
}
```

##### background-repeat属性

该属性设置如何平铺背景图像

| 值        | 说明             |
| --------- | ---------------- |
| repeat    | 默认值           |
| repeat-x  | 只向水平方向平铺 |
| repeat-y  | 只向垂直方向平铺 |
| no-repeat | 不平铺           |

```css
.box{
    width: 600px;
    height: 600px;
    background-color: #fcc;
    background-image: url("images/img1.jpg");
    background-repeat: no-repeat;
}
```

##### background-size属性

该属性设置背景图像的大小

| 值         | 说明                                                         |
| ---------- | ------------------------------------------------------------ |
| length     | 设置背景图片的宽度和高度，第一个值宽度，第二个值高度，如果只是设置一个，第二个值auto |
| percentage | 计算相对位置区域的百分比，第一个值宽度，第二个值高度，如果只是设置一个，第二个值auto |
| cover      | 保持图片纵横比并将图片缩放成完全覆盖背景区域的最小大小       |
| contain    | 保持图片纵横比并将图像缩放成适合背景定位区域的最大大小       |

```css
.box{
    width: 600px;
    height: 600px;
    background-image: url("images/img1.jpg");
    background-repeat: no-repeat;
    background-size: 100% 100%;
}
```

##### background-position属性

该属性设置**背景图像的起始位置**，其默认值是：0% 0%（左上角）

| 值            | 说明                                                         |
| ------------- | ------------------------------------------------------------ |
| left  top     | 左上角                                                       |
| left center   | 左 中                                                        |
| left bottom   | 左 下                                                        |
| right top     | 右上角                                                       |
| right center  | 右 中                                                        |
| right bottom  | 右 下                                                        |
| center top    | 中 上                                                        |
| center center | 中 中                                                        |
| center bottom | 中 下                                                        |
| x%  y%        | 第一个值是水平位置，第二个值是垂直位置，左上角是0%  0%，右下角是100%  100% 。如果只指定了一个值，其他值默认是50%。默认是0%  0% |
| xpos ypos     | 单位是像素                                                   |

```css
.box{
    width: 600px;
    height: 600px;
    background-color: #fcc;
    background-image: url("images/img1.jpg");
    background-repeat: no-repeat;
    background-position: center;
}
```

#### 渐变

##### 线性渐变

```CSS
background-image: linear-gradient(渐变方向, 颜色1[位置1], 颜色2[位置2], 颜色3[位置3]...);
```

使用表示方位的单词

```CSS
to top 表示从下往上的方式进行渐变
to bottom 表示从上往下的方式进行渐变
to right 表示从左往右的方式进行渐变
to left 表示从右往左的方式进行渐变
to top left 表示从右下向左上进行渐变(top和left可以交换位置，下同)
to top right 表示从左下向右上进行渐变
to bottom left 表示从右上向左下进行渐变
to bottom right 表示从左上向右下进行渐变
```

+ `vh`是CSS中的一个相对长度单位，代表“视口高度”（viewport height）。它用于根据视口的高度来定义元素的尺寸或位置。1个`vh`等于视口高度的1%。视口高度是指浏览器窗口的高度，不包括浏览器的工具栏和滚动条等。

##### 使用示例：

- **`height: 50vh;`** ：
  - 这意味着元素的高度将是视口高度的一半（50%）。
- **`margin-top: 10vh;`** ：
  - 这表示元素的顶部外边距是视口高度的10%。

+ 使用角度表示，例如0deg等同于to top， 90deg等同于to right

```CSS
background-image: linear-gradient(to top, #a18cd1 0%, #fbc2eb 100%);
```

![img](https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/20240618143216.png)



##### 径向渐变

```CSS
background-image: radial-gradient(颜色1 覆盖区域大小, 颜色2 覆盖区域大小, … );
```

圆形

```CSS
background-image: radial-gradient(circle, red, blue);
```

![img](https://image.fengfengzhidao.com/rj_0731/20240618143523.png)



椭圆形

```CSS
background-image: radial-gradient(ellipse, red, blue);
```

![img](https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/20240618143548.png)



重复

```CSS
background-image: repeating-radial-gradient(red, yellow 10%, green 20%);
```

![img](https://image.fengfengzhidao.com/rj_0731/20240618143648.png)



##### 边框渐变

```CSS
border-image: linear-gradient(方向，颜色1，颜色2 …) 内向偏移量;
border-image: linear-gradient(to bottom right, yellow, green) 1 1 1 1;
```

后面四个数字就是显示那一边的边框颜色

+ 好看的渐变色网站	https://color.oulu.me/

##### 文字渐变

```CSS
display: inline-block; /* 宽度调整为合适 */
background-image: linear-gradient(to right, green, rosybrown);
background-clip: text;
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
font-size: 30px;
```

#### 文本属性

##### text-align

指定元素文本的水平对齐方式

| 值     | 描述                 |
| ------ | -------------------- |
| left   | 文本居左排列，默认值 |
| right  | 把文本排列到右边     |
| center | 把文本排列到中间     |

```css
h1 {text-align:center}
h2 {text-align:left}
h3 {text-align:right}
```

##### text-decoration

text-decoration 属性规定添加到文本的修饰，下划线、上划线、删除线等

| 值           | 描述       |
| ------------ | ---------- |
| underline    | 定义下划线 |
| overline     | 定义上划线 |
| line-through | 定义删除线 |

```css
h1 {text-decoration:overline} 
h2 {text-decoration:line-through} 
h3 {text-decoration:underline}
```

##### text-transform

text-transform 属性控制文本的大小写

| 值         | 描述                 |
| ---------- | -------------------- |
| captialize | 定义每个单词开头大写 |
| uppercase  | 定义全部大写字母     |
| lowercase  | 定义全部小写字母     |

```css
h1 {text-transform:uppercase;}
h2 {text-transform:capitalize;}
p {text-transform:lowercase;}
```

##### text-indent

text-indent 属性规定文本块中首行文本的缩进

```css
p{
	text-indent:30px;
    text-indent:2rem; /* 缩进两个字符 */
}
```

> **温馨提示**
>
> 负值是允许的。如果值是负数，将第一行左缩进

##### 字体间距

+ line-height 行距

+ letter-spacing  字符间距

+ word-spacing 单词间距、

#### white-space

`white-space`是一个CSS属性，用于控制元素中文本的空白处理方式。它影响文本的换行和空白字符（如空格和制表符）的显示。以下是`white-space`属性的常见值及其含义：

1. **`normal`** ：
   - **功能**：默认值。合并连续的空白字符（例如，多个空格被视为一个空格），并在必要时自动换行。
   - **效果**：文本在遇到容器边界时会自动换行，空格和换行符会被缩减。
   - **应用场景**：适用于大多数正常文本场景，特别是在希望文本能够根据容器大小自动调整时。
2. **`nowrap`** ：
   - **功能**：文本不换行，所有文本都在同一行显示。
   - **效果**：文本会在同一行中显示，直到遇到显式的换行符或达到容器末尾，这可能导致出现水平滚动条。
   - **应用场景**：适用于需要文本保持在同一行的场景，比如导航栏或某些表格单元格。
3. **`pre`** ：
   - **功能**：保留文本中的所有空白字符（包括空格和换行符），并且文本以其在源代码中的格式显示。
   - **效果**：文本不会自动换行，空格和换行符都被保留。
   - **应用场景**：适用于需要显示格式化文本的场景，例如代码片段或保留特定排版格式的文本。

#### 超出显示省略号

单行

```CSS
/*不换行*/
white-space: nowrap; 
/*溢出隐藏*/
overflow: hidden;
/*显示省略号*/
text-overflow: ellipsis;
```

多行

```CSS
/*溢出隐藏*/
overflow: hidden;
/*显示省略号*/
text-overflow: ellipsis;
display: -webkit-box;
-webkit-box-orient: vertical;
/*设置显示文本的行数*/
-webkit-line-clamp: 4;
width: 200px
```

#### 表格属性

##### 表格边框

指定CSS表格边框，使用border属性

```css
table, td { 
    border: 1px solid black; 
}
```

##### 折叠边框

border-collapse 属性设置表格的边框是否被折叠成一个单一的边框或隔开

```css
table { border-collapse:collapse; } //表格边框折叠
table,td { border: 1px solid black; } //边框的颜色、粗细设置
```

##### 表格宽度和高度

width 和 height 属性定义表格的宽度和高度

```css
table { width:100%; } 
td { height:50px; }
```

##### 表格文字对齐

表格中的文本对齐和垂直对齐属性

text-align属性设置**水平对齐**方式，左，右，或中心

```css
td { text-align:right; }
```

垂直对齐属性设置**垂直对齐**

```css
td { height:50px; vertical-align:bottom; }
```

##### 表格填充

如果在表的内容中控制空格之间的边框，应使用td和th元素的填充属性

```css
td { padding:15px; }
```

##### 表格颜色

下面的例子指定边框的颜色，和th元素的文本和背景颜色

```css
table, td, th { border:1px solid green; } 
td { background-color:green; color:white; } //背景绿色；文字白色
```



#### **关系选择器**

1. 后代选择器
2. 子代选择器
3. 相邻兄弟选择器
4. 通用兄弟选择器

##### 后代选择器

选择所有被E元素包含的F元素，中间用空格隔开

**语法**

```css
E F{}
```

```html
<ul>
     <li>宝马</li>
     <li>奔驰</li>
</ul>
 <ol>
     <li>奥迪</li>
</ol>
```

```css
ul li{
    color:green;
}
```

##### 子代选择器

选择所有作为E元素的直接子元素F，对更深一层的元素不起作用，用>表示

**语法**

```css
E>F{}
```

```html
<div> 
    <a href="#">子元素1</a>
    <p> <a href="#">孙元素</a> </p>
    <a href="#">子元素2</a>
</div>
```

```css
div>a{
    color:red
}
```

##### 相邻兄弟选择器（兄弟指的是同级别）

选择紧跟E元素后的F元素，用加号表示，选择相邻的第一个兄弟元素，只能向下选择

**语法**

```css
E+F{}
```

```html
<h1>h1元素</h1> 
<p>第一个元素</p> 
<p>第二个元素</p>
```

```css
h1+p{
    color:red;
}
```

##### 通用兄弟选择器（兄弟指的是同级别）

选择E元素之后的所有兄弟元素F，作用于多个元素，用~隔开，只能向下选择

**语法**

```css
E~F{}
```

```html
<h1>h1元素</h1>
<p>第一个元素</p>
<p>第二个元素</p>
```

```css
h1~p{
    color:red;
}
```



#### 盒模型

所有HTML元素可以看作盒子，在CSS中，"box model"这一术语是用来设计和布局时使用

CSS盒模型本质上是一个盒子，封装周围的HTML元素，它包括：

外边距（margin），边框（border），内边距（padding），和实际内容（content）

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20211202151036771.png" alt="image-20211202151036771" style="zoom:50%;" />



1. Margin(外边距) - 清除边框外的区域，外边距是透明的（两个值：第一个值上下，第二个值左右）
2. Border(边框) - 围绕在内边距和内容外的边框
3. Padding(内边距) - 清除内容周围的区域（两个值：第一个值上下，第二个值左右）
4. Content(内容) - 盒子的内容，显示文本和图像

```html
<div></div>
```

```css
div{
    width: 100px;
    height: 100px;
    padding: 10px;
    border: 2px solid red;
    margin: 10px;
    background: green;
    border-sizing: border-box; 或者 content-box（默认） 
}
```

#### CSS3弹性盒子-Flexbox

弹性盒子由弹性容器（Flex container）和弹性子元素（Flex item）组成

弹性容器通过设置 `display `属性的值为 `flex `将其定义为弹性容器

**弹性容器内包含了一个或多个弹性子元素**

> 弹性容器外及弹性子元素内是正常渲染的。弹性盒子只定义了弹性子元素如何在弹性容器内布局

```html
<div class="flex-container">
    <div class="flex-item">flex item 1</div>
    <div class="flex-item">flex item 2</div>
    <div class="flex-item">flex item 3</div> 
</div>
<style>
    .flex-container {
        display: flex;
        width: 400px;
        height: 250px;
        background-color: lightgrey;
    }
    .flex-item {
        background-color: cornflowerblue;
        width: 100px;
        height: 100px;
        margin: 10px;
    }
</style>
```

> 默认弹性盒里内容横向摆放

##### 父元素上的属性

##### **display 属性**

`display:flex;`开启弹性盒，属性设置后子元素默认水平排列

##### **flex-direction属性**

flex-direction 属性指定了弹性子元素在父容器中的位置

| 属性值         | 含义                                                         |
| -------------- | ------------------------------------------------------------ |
| row            | 默认值，主轴为水平方向（水平布局），起点在左端，从左向右排列 |
| row-reverse    | 主轴为水平方向（水平布局），起点在右端，从右向左排列         |
| column         | 主轴为垂直方向（垂直布局），起点在上沿，从上往下排列         |
| column-reverse | 主轴为垂直方向（垂直布局），起点在下沿，从下往上排列         |


```css
.flex-container {
    display: flex;
    flex-direction: column;
    width: 400px;
    height: 250px;
    background-color: lightgrey;
}
```

##### justify-content 属性

justify-content属性定义了项目在主轴上的对齐方式。

| 属性值        | 含义                                                         |
| ------------- | ------------------------------------------------------------ |
| flex-start    | 默认值，左对齐                                               |
| flex-end      | 右对齐                                                       |
| center        | 居中                                                         |
| space-between | 两端对齐，项目之间的间隔都相等                               |
| space-around  | 每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍 |
| space-evenly  | 均匀排列每个元素                                             |

##### align-items 属性

`align-items` 设置或检索弹性盒子元素在纵轴方向上的对齐方式

| 属性值     | 含义                                                         |
| ---------- | ------------------------------------------------------------ |
| flex-start | 交叉轴的起点对齐                                             |
| flex-end   | 交叉轴的终点对齐                                             |
| center     | 交叉轴的中点对齐                                             |
| baseline   | 项目的第一行文字的基线对齐                                   |
| stretch    | （默认值） 如果项目未设置高度或设为auto，将占满整个容器的高度 |

##### align-content

定义**多行内容在纵轴上各行对齐方式**，属性和align-items一样，但是多了space-的设置

##### flex-wrap

默认情况下，项目都排在一条线（又称"轴线"）上。`flex-wrap`属性定义，如果一条轴线排不下，如何换行。

| 属性值       | 含义               |
| ------------ | ------------------ |
| nowrap       | 默认值，表示不换行 |
| wrap         | 换行               |
| wrap-reverse | 换行，第一行在下方 |

##### flex-flow

flex-flow 属性是 flex-direction 和 flex-wrap 属性的复合属性。

```CSS
flex-flow: row wrap;
```

#### **Flexbox子元素上的属性**

##### order

`order`属性用来定义项目的排列顺序。数值越小，排列越靠前，**默认为 0** 。

##### flex-grow

`flex-grow`属性定义项目的放大比例，**默认为 0** ，即如果存在剩余空间，也不放大。

##### flex-shrink

`flex-shrink`属性定义了项目的缩小比例，**默认为 1** ，**即如果空间不足，该项目将缩小**，如果不想元素被压缩，设置为0。

##### flex-basis

`flex-basis`属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为`auto`，即项目的本来大小。

它的初始值是 auto，此时浏览器会检查元素是否设置了 width 属性值。

如果有，则使用 width 的值作为 flex-basis 的值；

如果没有，则用元素内容自身的大小。

如果 flex-basis 的值不是 auto，width 属性会被忽略。

##### flex

`flex`属性是`flex-grow`, `flex-shrink` 和 `flex-basis`的简写，默认值为`0 1 auto`。后两个属性可选。

如果只有一个子元素设置，那么按扩展因子转化的百分比对其分配剩余空间。0.1即10%，1即100%，超出按100%

```css
        .box1 {
            flex: 2;
            height: 100px;
            background-color: violet;
        }

        .box2 {
            flex: 2;
            height: 100px;
            background-color: green;
        }

        .box3 {
            flex: 1;
            height: 100px;
            background-color: yellow;
        }
```

<img src="C:/Users/%E6%9B%BE%E7%BB%B4/AppData/Roaming/Typora/typora-user-images/image-20250309190505422.png" alt="image-20250309190505422" style="zoom:67%;" />

##### align-self

`align-self`属性允许单个项目有与其他项目不一样的对齐方式，可覆盖`align-items`属性。默认值为`auto`，表示继承父元素的`align-items`属性，如果没有父元素，则等同于`stretch`。

##### flex与margin auto

设置元素margin的时候，它有一个auto属性需要到flex才能用到.

---

#### grid 布局

#### grid容器属性

##### grid-template-columns

划分列数

固定宽度

```CSS
grid-template-columns: 40px 40px;
```

百分比

```CSS
grid-template-columns: 40% 60%;
```

比例

```CSS
grid-template-columns: 1fr 2fr;
```

重复

```CSS
grid-template-columns: repeat(5, 1fr);  /*5列，每列等宽*/
```

自动计算列

```CSS
grid-template-columns: repeat(auto-fill, 600px); /*每列固定600px，自动算多少列*/
grid-template-columns: repeat(auto-fit, 600px); /*每列固定600px，自动算多少列*/
```

auto

```CSS
grid-template-columns: 100px auto 100px;
```

##### grid-template-rows、grid-auto-rows

###### **`grid-template-rows`**

- **作用**：显式定义网格容器中每一行的高度。

- **适用场景**：**当你知道网格的行数和每行的高度时使用。**

  ```css
  grid-template-rows: <track-size> ...;
  ```

  - `<track-size>` 可以是固定值（如 `100px`）、百分比（如 `50%`）、弹性单位（如 `1fr`）或函数（如 `minmax(100px, auto)`）。

  ```css
  grid-template-rows: 100px 200px 1fr; /* 3 行，高度分别为 100px、200px 和剩余空间 */
  grid-template-rows: repeat(3, 1fr); /* 3 行，每行高度相等 */
  grid-template-rows: minmax(100px, auto); /* 行高度至少 100px，最大由内容决定 */
  ```

------

###### **`grid-auto-rows`**

- **作用**：定义网格容器中未显式指定高度的行的高度（即隐式创建的行）。

- **适用场景**：**当网格的行数不确定（例如动态添加行）时使用。**

  ```css
  grid-auto-rows: <track-size>;
  ```

  - `<track-size>` 可以是固定值、百分比、弹性单位或函数。

  ```css
  grid-auto-rows: 50px; /* 所有隐式行的高度为 50px */
  grid-auto-rows: min-content; /* 隐式行高度由内容的最小高度决定 */
  grid-auto-rows: minmax(100px, auto); /* 隐式行高度至少 100px，最大由内容决定 */
  ```

------

##### 行列间距

```CSS
grid-template-columns: repeat(3,1fr);
/*grid-template-rows: repeat(3,1fr);*/
row-gap: 20px;
column-gap: 20px;
```

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/20240622105702.png" alt="img" style="zoom:50%;" />

gap是row-gap和column-gap是简写

##### 容器对齐方式

justify-content

水平对齐方式

```CSS
justify-content: center;
```

垂直对齐方式

```CSS
align-content: center;
```

place-content

是`align-content`属性和`justify-content`属性的合并简写形式。

```CSS
place-content: end end;
```

##### 单元格对齐方式

justify-items

align-items

place-items

是`align-items`属性和`justify-items`属性的合并简写形式。

```CSS
justify-items: end;
align-items: end;
```

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/20240622113054.png" alt="img" style="zoom:50%;" />



##### 项目内单元格对齐方式

用法和justify-items类似，但是是在项目属性上写的

```CSS
<div class="item" style="place-self: end end">1</div>
```

<img src="https://image.fengfengzhidao.com/pic/20240622113415.png" alt="img" style="zoom:50%;" />



#### grid项目属性

##### 合并单元格

```CSS
.item-8{
    grid-column-start: 2;
    grid-column-end: 4;
}
```

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/20240622114114.png" alt="img" style="zoom:50%;" />



```CSS
.item-5{
  grid-column-start: 2;
  grid-column-end: 4;
  grid-row-start: 2;
  grid-row-end: 4;
}
```

可简写为

```CSS
grid-row: 2/4;
grid-column: 2/4;
```

<img src="https://image.fengfengzhidao.com/pic/20240622114240.png" alt="img" style="zoom:67%;" />

---

#### 文档流

文档流是文档中可显示对象在排列时所占用的位置/空间

例如：块元素自上而下摆放，内联元素，从左到右摆放 

标准流里面的限制非常多，导致很多页面效果无法实现

1. 高矮不齐，底边对齐
2. 空白折叠现象
   1. 无论多少个空格、换行、tab，都会折叠为一个空格
   2. 如果我们想让img标签之间没有空隙，必须紧密连接

##### 文档流产生的问题

##### 高矮不齐，底边对齐

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250309191834884.png" alt="image-20250309191834884" style="zoom: 50%;" />

##### 空格折叠

```
    <p>这是   p标签</p>
```

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250309191929849.png" alt="image-20250309191929849" style="zoom:67%;" />

##### 元素无空隙

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250309191856252.png" alt="image-20250309191856252" style="zoom:67%;" />

##### 脱离文档流

使⼀个元素脱离标准文档流有三种方式

1. 浮动
2. 绝对定位
3. 固定定位 

---

#### 浮动

`float `属性定义元素在哪个方向浮动，任何元素都可以浮动。

| 值    | 描述         |
| ----- | ------------ |
| left  | 元素向左浮动 |
| right | 元素向右浮动 |

##### 浮动的原理

1. 浮动以后使元素脱离了文档流
2. 浮动只有左右浮动，没有上下浮动

##### 元素向左浮动

脱离文档流之后，元素相当于在页面上面增加一个浮层来放置内容。此时可以理解为有两层页面，一层是底层的原页面，一层是脱离文档流的上层页面，所以会出现折叠现象

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250309194519822.png" alt="image-20250309194519822" style="zoom: 50%;" />

```html
<div class="box"></div>
<div class="container"></div>
```

```css
.container{
    width: 200px;
    height: 200px;
    background-color: #81c784;
}

.box{
    width: 100px;
    height: 100px;
    background-color: #fff176;
    float: left;
}
```

##### 元素向右浮动

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250309194545787.png" alt="image-20250309194545787" style="zoom: 50%;" />

##### 所有元素浮动

当所有元素同时浮动的时候，会变成水平摆放，向左或者向右，没有间隙（如果不定义元素边距）

![image-20250309194710250](https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250309194710250.png)

**当容器宽度不足时**，会在下一行摆放

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250309195230223.png" alt="image-20250309195230223" style="zoom:67%;" />



##### 浮动副作用

当元素设置float浮动后，该元素就会脱离文档流并向左/向右浮动，

1. 浮动元素会造成父元素高度塌陷
2. 后续元素会受到影响

#### 清除浮动

1. 父元素设置高度
2. 受影响的元素增加`clear: both;`属性
3. overflow清除浮动
4. 伪对象方式

##### 父元素设置高度

如果父元素高度塌陷，可以给父元素设置高度，撑开元素本身大小

```css
.container{
    height: 300px;
    width: 350px;
    border: 1px solid red;
}
.box{
    width: 100px;
    height: 100px;
    background-color: #fff176;
    float: left;
    margin: 5px;
}
```

##### overflow清除浮动

如果有父级塌陷，并且同级元素也收到了影响，可以使用`overflow`清除浮动

这种情况下，父布局不能设置高度

```css
        .text {
            width: 100px;
            height: 100px;
            background-color: bisque;
            overflow: hidden;
        }
```

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250309210929544.png" style="zoom: 50%;" />

#### Clear

```
        .text {
            width: 100px;
            height: 100px;
            background-color: bisque;
            clear: both;
        }
```



<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250309210753370.png" style="zoom:50%;" />

#### 伪对象方式

如果有父级塌陷，并且同级元素也收到了影响，还可以使用伪对象方式处理

为父标签添加伪类`after`,设置空的内容，并且使用`clear:both`;

这种情况下，父布局不能设置高度

```html
<div class="container">
    <div class="box"></div>
    <div class="box"></div>
    <div class="box"></div>
</div>
<div class="text"></div>
```

```css
.container {
    width: 350px;
    border: 1px solid red;
}
.container::after {
    content: "";
    display: block;
    clear: both;
}
.box {
    width: 100px;
    height: 100px;
    background-color: #fff176;
    float: left;
    margin: 5px;
}
.text {
    width: 100px;
    height: 100px;
    background-color: red;
}
```



#### 定位

`position `属性指定了元素的定位类型

| 值       | 描述                                                 |
| -------- | ---------------------------------------------------- |
| relative | 相对定位(相对原本的位置的变化，某个方向留空多少距离) |
| absolute | 绝对定位                                             |
| fixed    | 固定定位                                             |
| sticky   | 粘性定位                                             |

其中，绝对定位和固定定位会脱离文档流

+ **设置定位之后：可以使用四个方向值进行调整位置：`left、top、right、bottom`** ，上和下、左和右不能同时出现，会覆盖

+ 设置定位之后，**相对定位和绝对定位他是相对于具有定位的父级元素进行位置调整**，如果父级元素不存在定位，则继续向上逐级寻找，直到顶层文档

+ 固定定位，固定在页面某个位置，不随页面滚动而运动

#### Z-index

`z-index`属性设置元素的堆叠顺序。拥有更高堆叠顺序的元素总是会处于堆叠顺序较低的元素的前面。

默认值是0，可以设置成负数。

---

#### CSS3特性

##### 圆角

使用 CSS3 `border-radius` 属性，你可以给任何元素制作 "圆角"

`border-radius` 属性，可以使用以下规则：

1. 四个值: 第一个值为左上角，第二个值为右上角，第三个值为右下角，第四个值为左下角
2. 三个值: 第一个值为左上角, 第二个值为右上角和左下角，第三个值为右下角
3. 两个值: 第一个值为左上角与右下角，第二个值为右上角与左下角
4. 一个值： 四个圆角值相同

##### 阴影

`box-shadow`是CSS中的一个属性，用于给元素增加阴影效果。它的语法由多个属性值组成，分别用于定义阴影的偏移、模糊程度、扩展范围及颜色。

1. **水平偏移（horizontal offset）** ：
   - 第一个值（例如 `3px`）：表示阴影在水平方向上的偏移量。正值表示阴影在元素的右侧，负值则在左侧。
2. **垂直偏移（vertical offset）** ：
   - 第二个值（例如 `5px`）：表示阴影在垂直方向上的偏移量。正值表示阴影在元素的下方，负值则在上方。
3. **模糊半径（blur radius）** ：
   - 第三个值（例如 `5px`）：用于设置阴影的模糊程度。值越大，阴影越模糊和扩散；如果是0，则阴影是锐利的。模糊半径不能为负值。
4. **扩展半径（spread radius）（可选）** ：
   - 第四个值（例如 `5px`）：用于设置阴影的大小。正值会使阴影膨胀，负值会使其缩小。
5. **颜色（color）** ：
   - 最后一个值（例如 `rgba(0, 0, 0, 0.5)`）：定义阴影的颜色。可以使用任何有效的CSS颜色值，如十六进制、RGB、RGBA等。`rgba`中的`0.5`表示颜色的不透明度（50%透明）。

```css
            background-color: rgba(255, 0, 204, 0.647);
            box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.5);
```

<img src="C:/Users/%E6%9B%BE%E7%BB%B4/AppData/Roaming/Typora/typora-user-images/image-20250310173658464.png" alt="image-20250310173658464" style="zoom:67%;" />

#### 变换

使用变换之后，这个原来的位置还在文档流里，可以用伪类触发

+ 只作用与块盒和行内块

+ 可以多个属性共存

##### 平移 translate

```CSS
translate(x, y);
```

##### 旋转 rotate

deg是角度，顺时针方向

```CSS
rotate(60deg);
```

##### 缩放 scale

```CSS
scale(1.2);
```

使用缩放，可以破除浏览器12px最小字体大小的限制

##### 锚点

主要这对于缩放和旋转

```CSS
transform-origin: left top;
```

##### 过渡

`transition`属性包括以下几个子属性：

- **`transition-property`**：指定要过渡的CSS属性名称，可以使用通配符 `all` 表示所有属性都要过渡。
- **`transition-duration`**：指定过渡的持续时间，单位可以是秒（s）或毫秒（ms）。
- **`transition-timing-function`**：指定过渡的时间函数，用于控制过渡的速度曲线，常见的值有 `ease`、`linear`、`ease-in`、`ease-out`、`ease-in-out` 等。
- **`transition-delay`**：指定过渡的延迟时间，即过渡开始前等待的时间，单位可以是秒（s）或毫秒（ms）。

```CSS
.line{
    display: inline-block;
    transition: all 1s;
    transform-origin: right top;
}
.line:hover{
    transform: scale(1.2);
}
```

#### 动画

动画是使元素从一种样式逐渐变化为另一种样式的效果

您可以改变任意多的样式任意多的次数

请用百分比来规定变化发生的时间，或用关键词 "from" 和 "to"，等同于 0% 和 100%

0% 是动画的开始，100% 是动画的完成。

##### @keyframes创建动画

使用`@keyframes`规则，你可以创建动画

```css
@keyframes name {
    0%{css样式}
    N%{css样式}
    100%{css样式}
}
```

+ name：动画名称，开发人员自己命名；

##### animation执行动画

```css
animation: name duration timing-function delay iteration-count direction;
```

| 属性值               | 描述                                                      |
| -------------------- | --------------------------------------------------------- |
| name                 | 设置动画的名称                                            |
| duration             | 设置动画的持续时间                                        |
| timing-function      | 设置动画效果的速率（如下）                                |
| delay                | 设置动画的开始时间（延时执行）                            |
| iteration-count      | 设置动画循环的次数，infinite为无限次数的循环              |
| direction            | 设置动画播放的方向（如下）                                |
| animation-play-state | 控制动画的播放状态：running代表播放，而paused代表停止播放 |

| timing-function值 | 描述             |
| ----------------- | ---------------- |
| ease              | 逐渐变慢（默认） |
| linear            | 匀速             |
| ease-in           | 加速             |
| ease-out          | 减速             |
| ease-in-out       | 先加速后减速     |

| direction值       | 描述                                             |
| ----------------- | ------------------------------------------------ |
| normal            | 默认值为normal表示向前播放                       |
| alternate(交替的) | 动画播放在第偶数次向前播放，第奇数次向反方向播放 |

**切换背景颜色**

```html
<div class="animation"></div>
```

```css
.animation {
    width: 300px;
    height: 300px;
    background-color: red;
    animation: anima 5s linear 5s infinite;
}
.animation:hover {
    animation-play-state: paused;
}
@keyframes anima {
    0% {
        background-color: red;
    }
    50% {
        background-color: green;
    }
    100% {
        background-color: blueviolet;
    }
}
```

##### DEMO

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250311161202921.png" alt="image-20250311161202921" style="zoom: 33%;" />

```html
<div class="box"></div>
```

```css
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        @keyframes identifier {
            0% {
                left: 0;
                top: 0;
            }

            25% {
                left: calc(100% - 20px);
                top: 0;
            }

            50% {
                left: calc(100% - 20px);
                top: calc(100% - 20px);
            }

            75% {
                left: 0;
                top: calc(100% - 20px);
            }

            100% {
                left: 0;
                top: 0;
            }

        }

        .container {
            border-radius: 10px;
            background-color: brown;
            align-items: center;
            justify-content: center;
            display: flex;
            width: 500px;
            height: 500px;
            position: relative;
            margin: 0 auto;
            margin-top: 100px;
        }

        .box {
            border-radius: 1px;
            width: 460px;
            height: 460px;
            background-image: linear-gradient(45deg, red, yellow, blue, green);
            position: absolute;
        }

        .sub {
            width: 20px;
            height: 20px;
            background-color: rgba(0, 247, 255, 0.788);
            position: absolute;
            border-radius: 50%;
            animation: identifier 5s infinite;
        }
    </style>
</head>

<body>
    <div class="container">
        <div class="sub"></div>
        <div class="box">

        </div>
    </div>
</body>

</html>
```

#### 媒体查询

媒体查询能使页面在不同在终端设备下达到不同的效果，媒体查询会根据设备的大小自动识别加载不同的样式

##### 设置meta标签

使用设备的宽度作为视图宽度并禁止初始的缩放。在`<head>`标签里加入这个meta标签。 

```css
<meta name="viewport" content="width=device-width, initial-scale=1,maximum-scale=1, user-scalable=no">
```

**参数解释**

1. `width = device-width` 宽度等于当前设备的宽度
2. `initial-scale` 初始的缩放比例（默认设置为1.0）
3. `maximum-scale` 允许用户缩放到的最大比例（默认设置为1.0）
4. `user-scalable` 用户是否可以手动缩放（默认设置为no）

##### 媒体查询语法

```css
        .box {
            width: 300px;
            height: 300px;
            background-color: red;
        }

        @media screen and (max-width: 768px) {
            .box {
                background-color: rgba(0, 255, 255, 0.658);
            }
        }

        @media screen and (min-width: 768px) and (max-width: 996px) {
            .box {
                background-color: rgba(9, 181, 64, 0.541);
            }
        }

        @media screen and (min-width: 996px) {
            .box {
                background-color: rgba(255, 0, 0, 0.658);
            }
        }
```

#### 雪碧图

CSS Sprite也叫CSS精灵图、CSS雪碧图，是一种网页图片应用处理方式。它允许你将一个页面涉及到的所有零星图片都包含到一张大图中去

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250310202416064.png" alt="image-20250310202416064" style="zoom:50%;" />

##### 优点

1. 减少图片的字节
2. 减少网页的http请求，从而大大的提高页面的性能

##### 原理

1. 通过background-image引入背景图片
2. 通过background-position把背景图片移动到自己需要的位置

##### 实例

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250310202323694.png" alt="image-20250310202323694" style="zoom:50%;" />

```html
    <span id="icon1"></span>
    <span id="icon2"></span>
```

```css
    <style>
        #icon1 {
            display: block;
            width: 45px;
            height: 70px;
            background-image: url("1.png");
            border: 1px solid #000;
            background-position: -21px -12px;
        }
        #icon2 {
            display: block;
            width: 45px;
            height: 70px;
            background-image: url("1.png");
            border: 1px solid #000;
            background-position: -93px -156px;
        }
    </style>
</head>

```



#### 字体图标

![image-20250310202703715](https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250310202703715.png)

我们会经常用到一些图标。但是我们在使用这些图标时，往往会遇到失真的情况，而且图片数量很多的话，页面加载就越慢。所以，我们可以使用字体图标的方式来显示图标，既解决了失真的问题，也解决了图片占用资源的问题

常用字体图标库：

+ [阿里字体图标库](https://iconfont.cn/)

+ https://icones.js.org/
+ https://iconscout.com/

##### 优点

1. 轻量性：加载速度快，减少http请求
2. 灵活性：可以利用CSS设置大小颜色等
3. 兼容性：网页字体支持所有现代浏览器，包括IE低版本

##### 使用字体图标（阿里）

1. 注册账号并登录
2. 选取图标或搜索图标
3. 添加购物车
4. 下载代码
5. 选择`font-class`引用

```html
<span class="iconfont icon-add-circle"></span>
```

```css
<link rel="stylesheet" href="./css/iconfont.css">
.iconfont{
    font-size: 35px;
    color: red;
}
```

---

#### css栅格化

UI组件库的基石

整个css布局的核心知识

```CSS
.row {
    display: flex;
    height: 100px;
}

.col {
    height: 100%;
}

.col-1 {
    flex: 0 0 10%;
}

.col-2 {
    flex: 0 0 20%;
}

.col-3 {
    flex: 0 0 30%;
}

.col-4 {
    flex: 0 0 40%;
}

.col-5 {
    flex: 0 0 50%;
}

.col-6 {
    flex: 0 0 60%;
}

.col-7 {
    flex: 0 0 70%;
}

.col-8 {
    flex: 0 0 80%;
}

.col-9 {
    flex: 0 0 90%;
}

.col-10 {
    flex: 0 0 100%;
}
```

#### Bootstrap

1. 比较早使用css栅格化的ui组件库
2. 它可以单独使用，不挑前端框架

官方文档

https://v4.bootcss.com/
