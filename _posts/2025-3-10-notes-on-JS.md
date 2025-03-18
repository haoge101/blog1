---
title: JavaScript 入门笔记
date: 2025-3-10 12:16:40 +0800
categories: [Study] # 目前有 Demo, Tutorial, Tech, Study
tags: [大学, 前端, 笔记]
author: Zwei  # 或 authors: [Zwei, another_author]
description: "2025年重制版JavaScript笔记"
image:
  path: https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250318215918632.png
permalink: '/w/notes-on-JavaScript'  # 自定义永久链接
pin: false # 置顶文章
toc: true # 显示目录
comments: true # 允许评论
math: true # 启用数学公式
mermaid: true # 启用 Mermaid 图表
render_with_liquid: false # 禁用 Liquid 渲染
media_subpath: /blog/assets/ # 资源路径前缀
---

### JavaScript介绍

JavaScript 是一种轻量级的脚本语言。所谓“脚本语言”，指的是它不具备开发操作系统的能力，而是只用来编写控制其他大型应用程序的“脚本”。

JavaScript 是一种嵌入式（embedded）语言。它本身提供的核心语法不算很多

##### 特点

- 操控浏览器的能力
- 广泛的使用领域
- 易学性

##### JavaScript与ECMAScript的关系

ECMAScript和JavaScript的关系是，前者是后者的规格，后者是前者的一种实现。在日常场合，这两个词是可以互换的。

#####  JavaScript版本

![image-20250313161147655](https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250313161147655.png)

#### JavaScript语句、标识符

##### 语句

JavaScript 程序的单位是行（line），也就是一行一行地执行。一般情况下，每一行就是一个语句

```js
var num = 10;
```

语句以分号结尾，一个分号就表示一个语句结束

**定义一个量：**

| 特性     | `var`      | `let`      | `const`    |
| -------- | ---------- | ---------- | ---------- |
| 作用域   | 函数作用域 | 块级作用域 | 块级作用域 |
| 声明提升 | 存在       | TDZ        | TDZ        |
| 可变性   | 可变       | 可变       | 不可变     |
| 重复声明 | 允许       | 不允许     | 不允许     |

##### 标识符

标识符（identifier）指的是用来识别各种值的合法名称。最常见的标识符就是变量名

标识符是由：字母、美元符号($)、下划线(_)和数字组成，其中数字不能开头

>**温馨提示**
>
>中文是合法的标识符，可以用作变量名（不推荐）

##### JavaScript保留关键字

以下关键字不需要强行记忆！

> JavaScript有一些保留字，不能用作标识符：arguments、break、case、catch、class、const、continue、debugger、default、delete、do、else、enum、eval、export、extends、false、finally、for、function、if、implements、import、in、instanceof、interface、let、new、null、package、private、protected、public、return、static、super、switch、this、throw、true、try、typeof、var、void、while、with、yield。



##### 直接定义变量和值

```js
var num = 10; 
```

##### 变量的重新赋值

```js
var num = 10;
num = 20;
```

##### 变量提升

JavaScript 引擎的工作方式是，先解析代码，获取所有被声明的变量，然后再一行一行地运行。这造成的结果，就是所有的变量的声明语句，都会被提升到代码的头部，这就叫做变量提升（hoisting）。

```js
console.log(num);
var num = 10; // 出现变量提升现象
```

**同样的，JS存在函数提升**

##### JavaScript引入到文件

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250313172738222.png" alt="image-20250313172738222" style="zoom:67%;" />

##### 嵌入到HTML文件中

```html
<body>
	<script>
		var age = 20
	</script>
</body>
```

##### 引入本地独立JS文件

```html
<body>
	<script type="text/javascript" src="./hello.js">   		</script>
</body>
```

##### 引入网络来源文件

```html
<body>
	<script src="https://cdn.bootcdn.net/ajax/libs/jquery/3.6.0/jquery.min.js">	</script>
</body>
```

#### JavaScript输出方式

JavaScript有很多种输出方式，都可以让我们更直观的看到程序运行的结果

```js
// 在浏览器中弹出一个对话框,然后把要输出的内容展示出来,alert都是把要输出的内容首先转换为字符串然后在输出的
alert("要输出的内容");

document.write("要输出的内容"); 

// 在控制台输出内容
console.log("要输出的内容");
```

##### 数据类型

JavaScript 语言的每一个值，都属于某一种数据类型。JavaScript 的数据类型，共有六种。（ES6 又新增了第七种 Symbol 类型的值和第八种 BigInt类型，当前课程暂不涉及）

##### 数据类型分类

###### 原始类型(基础类型)

+ **数值**

  ```js
  var a = 1000;
  var b = 0.1;
  ```

+ **布尔值**

  ```js
  var T = true;
  var F = false;
  ```

+ **字符串**

  ```javascript
  var name = "Tom"
  var code = "1024"
  ```

###### 合成类型(复合类型)

**对象**

```js
        var stu = {
            name: '张三',
            age: 18,
            class: '高三一班'
        };
```

---

### 运算符

#### typeof运算符

适用于判断基本数据类型，返回的是**字符串**。

##### 数值返回number

```js
typeof 123 // "number"
```

##### 字符串返回string

```js
typeof '123' // "string
```

##### 布尔值返回boolean

```js
typeof false // "boolean"
```

##### 对象返回object

```js
typeof {} // "object"
```

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250313230039417.png" alt="image-20250313230015237" style="zoom:67%;" />

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250313230105335.png" alt="image-20250313230105335" style="zoom: 67%;" />

null 和 undefined 区别：

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250313230312976.png" alt="image-20250313230312976" style="zoom: 67%;" />

#### 算术运算符

##### 加减乘除运算符

加减乘除运算符就是基本的数学运算符效果

```js
10 + 10; // 20
100 - 10; // 90
10 * 2; //20
10 / 5; 2
```

##### 余数运算符（取模）

余数运算符是比较常用的，因为在逻辑思维上寻找规律，余数运算符是很好用的

```js
13 % 5 // 3
```

##### 自增和自减运算符

自增和自减运算符，是一元运算符，只需要一个运算子。它们的作用是将运算子首先转为数值，然后加上1或者减去1

```js
var x = 1;
var y = 1;
++x // 2
--y // 0
```

自增和自减运算符有一个**需要注意**的地方，就是放在变量之后，会先返回变量操作前的值，再进行自增/自减操作；放在变量之前，会先进行自增/自减操作，再返回变量操作后的值。

```js
var x = 1;
var y = 1;

x++ // 1
++y // 2
```

```js
var x = 10;
var y = 20;
console.log(x++ + y); // 10+20=30
```

#### 赋值运算符

赋值运算符（Assignment Operators）用于给变量赋值

最常见的赋值运算符，当然就是等号（=）

```js
// 将 1 赋值给变量 x
var x = 1;
// 将变量 y 的值赋值给变量 x
var x = y;
```

赋值运算符还可以与其他运算符结合，形成变体。下面是与算术运算符的结合

```js
// 等同于 x = x + y
x += y
// 等同于 x = x - y
x -= y
// 等同于 x = x * y
x *= y
// 等同于 x = x / y
x /= y
// 等同于 x = x % y
x %= y
```

#### 比较运算符

比较运算符用于比较两个值的大小，然后返回一个布尔值，表示是否满足指定的条件。

```js
2 > 1 // true
```

JavaScript 一共提供了8个比较运算符。

| 比较运算符 |         描述         |
| :--------: | :------------------: |
|     <      |      小于运算符      |
|     \>     |      大于运算符      |
|     <=     |   小于或等于运算符   |
|    \>=     |   大于或等于运算符   |
|     ==     |      相等运算符      |
|    ===     |  **严格相等运算符**  |
|     !=     |     不相等运算符     |
|    !==     | **严格不相等运算符** |

严格比较：

```js
        var c = "2";
        console.log(b == c); // true
        console.log(b === c); // false
```

#### 布尔运算符

##### 取反运算符（!）：

1. 布尔值取反

   ```js
   !true // false
   !false // true
   ```

2. 非布尔值取反

   对于非布尔值，取反运算符会将其转为布尔值。可以这样记忆，**以下六个值取反后为true，其他值都为false。**

   + undefined
   + null
   + false
   + 0
   + NaN
   + 空字符串（''）

```js
!undefined // true
!null // true
!0 // true
!NaN // true
!"" // true

!54 // false
!'hello' // false

///也就是说，数字、非空字符串都是 true
```

##### 且运算符（&&）

多个条件都要满足

```js
console.log(10 < 20 && 10 >5); // true
```

##### 或运算符（||）

满足一个条件即可

```js
console.log(10 < 20 || 10 < 5); // true
```

#### 条件语句

##### if

```js
if (布尔值){
   语句; 
}
var m = 3;
// 例子
if (m === 3) {
    m++;
}
console.log(m); // 4
```

##### if...else

```js
if (m === 3) {
  // 满足条件时，执行的语句
} else {
  // 不满足条件时，执行的语句
}

if (m === 0) {
  // ...
} else if (m === 1) {
  // ...
} else if (m === 2) {
  // ...
} else {
  // ...
}
```

##### switch + break

```js
var x = 1;

switch (x) {
  case 1:
    console.log('x 等于1');
    break;
  case 2:
    console.log('x 等于2');
    break;
  default:
    console.log('x 等于其他值');
    break;
}
// x等于1
// x等于2
// x等于其他值
```

\# 不加 break 就会一直往下执行

##### 三目运算符

```js
num % 2 == 0 ? console.log('even') : console.log('odd');
```

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250314102734973.png" alt="image-20250314102734973" style="zoom:67%;" />

#### 循环语句

##### for

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250314103552286.png" alt="image-20250314103552286" style="zoom:67%;" />

for语句就是循环命令，可以指定循环的起点、终点和终止条件。它的格式如下

```js
for (初始化表达式; 条件; 迭代因子) {
  语句
}

var x = 100;
for (var i = 0; i <= x; i++) {
    sum+=i;
}
console.log(sum); // 5050
```

for语句后面的括号里面，有三个表达式。

1. 初始化表达式（initialize）：确定循环变量的初始值，只在循环开始时执行一次。

2. 布尔表达式（test）：每轮循环开始时，都要执行这个条件表达式，只有值为真，才继续进行循环。

3. 迭代因子（increment）：每轮循环的最后一个操作，通常用来递增循环变量。

打印9*9乘法表：

```js
        for (var i = 1; i < 10; i++) {
            for (var j = i; j < 10; j++) {
                document.write(i + '*' + j + '=' + i * j + " ");
            }
            document.write('<br>')
        }
```

##### while

```js
while (条件) {
  语句;
}
// 无限循环会卡死
while (true) {
  console.log('Hello, world');
}

// 合理的例子
var sum = 0;
var i = 1;
while (i <= 10) {
  sum+=i;
  i++;
}
console.log(sum)
```

##### break

break语句用于跳出代码块或循环

```js
for (var i = 0; i < 5; i++) {
    if (i === 3){
        break;
    }
    console.log(i);
}
```

##### continue

continue语句用于立即终止本轮循环，返回循环结构的头部，开始下一轮循环

```js
for (var i = 0; i < 5; i++) {
    if (i === 3){
        continue;
    }
    console.log(i);
}
```

#### 字符串

JavaScript 字符串用于存储和处理文本。字符串可以包含零个或多个字符，用单引号 (`'`) 或双引号 (`"`) 括起来。转义字符用反斜杠`/`。

```javascript
let str1 = 'Hello, world!';
let str2 = "JavaScript";
let str3 = ""; // 空字符串
```

---

#### 字符串的属性和方法

##### 1. 属性

**`length`**

*   **用途：** 返回字符串的长度（字符数）。
*   **示例代码：**

    ```javascript
    'hello'.length; // 5
    ```

---

##### 2. 访问字符

**`charAt(index)`**

*   **用途：** 返回指定索引位置的字符。**如果索引超出范围（包括负数），返回空字符串。**
*   **示例代码：**

    ```javascript
    'hello'.charAt(1); // 'e'
    ```

**`charCodeAt(index)`**

*   **用途：** 返回指定索引位置的字符的 Unicode 编码（UTF-16 代码单元）。如果索引超出范围，返回 `NaN`。
*   **示例代码：**

    ```javascript
    'hello'.charCodeAt(1); // 101 (e 的 Unicode 编码)
    ```

**`str[index]`**

*   **用途：** 使用方括号访问指定索引位置的字符（ES5+）。如果索引超出范围，返回 `undefined`。
*   **示例代码：**

    ```javascript
    'hello'[1]; // 'e'
    ```

---

##### 3. 查找

**`indexOf(searchValue, fromIndex)`**

*   **用途：** **返回指定[子字符串]第一次出现的索引**，从 `fromIndex` 开始搜索（可选，默认为 0）。如果未找到，返回 -1。
*   **示例代码：**

    ```javascript
    'hello world'.indexOf('world'); // 6
    ```

**`lastIndexOf(searchValue, fromIndex)`**

*   **用途：** **返回指定[子字符串]最后一次出现的索引**，从 `fromIndex` 开始*反向*搜索（可选，默认为字符串末尾）。如果未找到，返回 -1。
*   **示例代码：**

    ```javascript
    'hello world world'.lastIndexOf('world'); // 12
    ```

**`startsWith(searchString, position)`**

*   **用途：** **检查字符串是否以指定的[子字符串]开头**，从 `position` 开始（可选，默认为0）。返回 `true` 或 `false`。
*   **示例代码：**

    ```javascript
    'hello world'.startsWith('hello'); // true
    ```

**`endsWith(searchString, length)`**

*   **用途：** **检查字符串是否以指定的[子字符串]结尾**，`length`为检查长度（可选，默认为字符串长度）。返回 `true` 或 `false`。
*   **示例代码：**

    ```javascript
    'hello world'.endsWith('world'); // true
    ```

**`includes(searchString, position)`**

*   **用途：** **检查字符串是否包含指定的[子字符串]**，从 `position` 开始（可选，默认为0）。返回 `true` 或 `false`。
*   **示例代码：**

    ```javascript
    'hello world'.includes('or'); // true
    ```

**`search(regexp)`**

*   **用途**: 使用正则表达式搜索字符串。返回第一个匹配项的索引; 如果未找到匹配项, 则返回 -1。
*  **示例代码：**
    ```javascript
     'hello world'.search(/or/); // 7
    ```

---

##### 4. 截取/提取

**`slice(startIndex, endIndex)`**

*   **用途：** 提取字符串的一部分，从 `startIndex` 到 `endIndex`（不包括 `endIndex`）。如果省略 `endIndex`，则提取到字符串末尾。支持负数索引（从末尾开始计数）。
*   **示例代码：**

    ```javascript
    'hello world'.slice(6, 11); // 'world'
    ```

**`substring(startIndex, endIndex)`**

*   **用途：** 提取字符串的一部分，**从 `startIndex` 到 `endIndex`（不包括 `endIndex`）**。如果省略 `endIndex`，则提取到字符串末尾。***不接受负数索引***。
*   **示例代码：**

    ```javascript
    'hello world'.substring(6, 11); // 'world'
    ```

**`substr(startIndex, length)`**

*   **用途：** 提取字符串的一部分，**从 `startIndex` 开始，提取 `length` 个字符**。如果省略 `length`，则提取到字符串末尾。`startIndex` 可以是负数（从末尾开始计数）。
*   **示例代码：**

    ```javascript
    'hello world'.substr(6, 5); // 'world'
    ```

---

##### 5. 修改

**`toLowerCase()`**

*   **用途：** 将整个字符串转换为小写。
*   **示例代码：**

    ```javascript
    'Hello World'.toLowerCase(); // 'hello world'
    ```

**`toUpperCase()`**

*   **用途：** 将整个字符串转换为大写。
*   **示例代码：**

    ```javascript
    'hello world'.toUpperCase(); // 'HELLO WORLD'
    ```

**`trim()`** 单词意思是“修剪”

*   **用途：** 去除字符串两端的空白字符（空格、制表符、换行符等）。
*   **示例代码：**

    ```javascript
    '  hello world  '.trim(); // 'hello world'
    ```

**`trimStart() / trimLeft()`**

*   **用途：** 去除字符串开头(左侧)的空格
*   **示例代码：**

    ```javascript
    '  hello world  '.trimStart(); // 'hello world  '
    ```

**`trimEnd() / trimRight()`**

*   **用途：** 去除字符串末尾(右侧)的空格。
*   **示例代码：**

    ```javascript
     '  hello world  '.trimEnd(); // '  hello world'
    ```

**`replace(searchValue, newValue)`**

*   **用途：** 将字符串中第一个匹配到的 `searchValue` 替换为 `newValue`。`searchValue` 可以是字符串或正则表达式。如果使用正则表达式，并且带有 `g` 标志，则替换所有匹配项。
*   **示例代码：**

    ```javascript
    'hello world'.replace('world', 'JavaScript'); // 'hello JavaScript'
    ```

**`replaceAll(searchValue, newValue)`**

*   **用途:** 替换与 `searchValue` 匹配的所有子字符串。
*   **示例代码:**
    ```javascript
    'xxx'.replaceAll('x', 'y');  // 'yyy'
    ```

**`repeat(count)`**

*   **用途:** 返回一个新字符串, 该字符串包含被连接在一起的指定数量的字符串副本。
*   **示例代码:**
```javascript
    'hello'.repeat(3); // 'hellohellohello'
```

**`padStart(targetLength, padString)`**

*  **用途：** 用 `padString`（默认为空格）在字符串的开头填充，直到字符串达到 `targetLength`。
*   **示例代码：**

    ```javascript
    '5'.padStart(3, '0'); // '005'
    ```

**`padEnd(targetLength, padString)`**

*   **用途：** 用 `padString`（默认为空格）在字符串的末尾填充，直到字符串达到 `targetLength`。
*   **示例代码：**

    ```javascript
    '5'.padEnd(3, '0'); // '500'
    ```

---

##### 6. 分割/合并

**`split(separator, limit)`**

*   **用途：** 将字符串分割成一个字符串数组，**根据 `separator`（可以是字符串或正则表达式）进行分割**。`limit` 参数限制返回的数组元素数量（可选）。如果separator是空字符串，那么分割结果是单个的字符。
*   **示例代码：**

    ```javascript
    'hello world'.split(' '); // ['hello', 'world']
    ```

**`concat(str1, str2, ...)`**

*  **用途：** 将一个或多个字符串与原字符串连接，形成一个新的字符串。
*  经典场景：上拉加载，合并数据
*   **示例代码：**

    ```javascript
    'hello'.concat(' ', 'world'); // 'hello world'
    ```

---
##### 7. 转换

**`toString()`**

* **用途：**  所有 JavaScript 对象都有 `toString()` 方法。对于字符串对象，它返回字符串本身的值。对于其他类型的值（如数字、布尔值），`toString()` 会将它们转换为字符串形式
*   **示例代码：**

    ```javascript
         (123).toString(); // "123"
    ```

**`valueOf()`**

*   **用途:** 返回字符串对象的原始值（primitive value）。通常在 JavaScript 内部使用，很少需要显式调用。
*   **示例代码:**
    ```javascript
    'hello'.valueOf();       //'hello'
    ```
---

这个分标题列举的形式，应该更清晰易读。 如果有其他排版方式，欢迎提出！

**重要注意事项**

- **不可变性 (Immutability):** JavaScript 字符串是不可变的。这意味着一旦创建了字符串，就不能直接修改它的内容。所有看似修改字符串的方法（如 `replace`、`toUpperCase` 等）实际上都返回一个*新*的字符串，而原始字符串保持不变。

- **Unicode:** JavaScript 使用 UTF-16 编码来表示字符串。这意味着大多数字符都用一个 16 位代码单元表示，但有些较不常见的字符（如某些表情符号）可能需要两个代码单元。

- **模板字面量 (Template Literals):** ES6 引入了模板字面量（使用反引号 ```），它提供了一种更方便的方式来创建多行字符串和嵌入变量/表达式：

  ```javascript
  let name = "Alice";
  let age = 30;
  let message = `My name is ${name} and I am ${age} years old.
  I can write multi-line strings
  without escaping.`;
  console.log(message)
  ```

---

#### 数组

JavaScript 数组用于存储一组有序的数据。数组可以包含任何类型的数据（数字、字符串、布尔值、对象、甚至其他数组），并且数组的长度是动态的，可以随时添加或删除元素。

```javascript
let arr1 = [1, 2, 3];
let arr2 = ["apple", "banana", "orange"];
let arr3 = [1, "hello", true, { name: "Alice" }];
let arr4 = []; // 空数组
```

如果数组的元素还是数组，就形成了多维数组

```js
var a = [[1, 2], [3, 4]];
a[0][1] // 2
a[1][1] // 4
```

判断对象是否是数组

```javascript
Array.isArray(arr); // 返回 true
typeof array // 返回 object，无法判断 
```

---

#### 数组的属性和方法

##### 1. 属性

**`length`**

*   **用途：** 返回数组的长度（元素的个数）。
*   **示例代码：**

    ```javascript
    [1, 2, 3].length; // 3
    ```

---

##### 2. 访问元素

**`arr[index]`**

*   **用途：** 使用方括号和索引访问数组中的元素。索引从 0 开始。如果索引超出范围，返回 `undefined`。
*   **示例代码：**

    ```javascript
    let arr = ["a", "b", "c"];
    arr[1]; // "b"
    arr[3]; // undefined
    ```

---

##### 3. 添加/删除元素

**`push(element1, ..., elementN)`**

*   **用途：** 在数组的**末尾**添加一个或多个元素，并返回新的数组长度。
*   **示例代码：**

    ```js
    let arr = [1, 2];
    arr.push(3); // 返回 3，arr 变为 [1, 2, 3]
    arr.push(4, 5); // 返回 5, arr 变为 [1, 2, 3, 4, 5]
    console.log(arr.push()) // 返回数组的长度
    ```

**`pop()`**

*   **用途：** 删除数组的**最后一个**元素，并返回该元素的值。如果数组为空，则返回 `undefined`。
*   **示例代码：**

    ```javascript
    let arr = [1, 2, 3];
    arr.pop(); // 返回 3，arr 变为 [1, 2]
    ```

**`unshift(element1, ..., elementN)`**

*   **用途：** 在数组的**开头**添加一个或多个元素，并**返回新的数组长度**。会改变原数组其他元素的索引。
*   **示例代码：**

    ```javascript
    let arr = [1, 2];
    arr.unshift(0); // 返回 3，arr 变为 [0, 1, 2]
    arr.unshift(-2, -1); // 返回 5, arr 变为 [-2, -1, 0, 1, 2]
    ```

**`shift()`**

*   **用途：** 删除数组的**第一个**元素，并**返回该元素的值**。如果数组为空，则返回 `undefined`。会改变原数组其他元素的索引.
*   **示例代码：**

    ```javascript
    let arr = [1, 2, 3];
    arr.shift(); // 返回被删除的元素 1，arr 变为 [2, 3]
    ```

**`splice(start, deleteCount, item1, ..., itemN)`**

*   **用途：** 从数组中**添加/删除/替换**元素。
    *   `start`: 开始修改的索引。
    *   `deleteCount`: 要删除的元素个数。
    *   `item1, ..., itemN`: 要添加到数组中的元素（从 `start` 位置开始）。
*   **返回值:** 由被删除的元素组成的一个新数组。如果只删除了一个元素, 则返回只包含一个元素的数组。如果没有删除元素, 则返回空数组。

*   **示例代码：**

    ```javascript
    let arr = [1, 2, 3, 4, 5];
    
    // 删除元素
    arr.splice(2, 2); // 从索引 2 开始，删除 2 个元素，arr 变为 [1, 2, 5], 返回[3,4]
    
    // 添加元素
    arr.splice(1, 0, "a", "b"); // 从索引 1 开始，删除 0 个元素，添加 "a" 和 "b"，arr 变为 [1, "a", "b", 2, 5]
    
    // 替换元素
    arr.splice(3, 1, "x"); // 从索引 3 开始，删除 1 个元素，添加 "x"，arr 变为 [1, "a", "b", "x", 5]
    ```

---

##### 4. 查找

**`indexOf(searchElement, fromIndex)`**

*   **用途：** 返回指定元素在数组中**第一次出现的索引，从 `fromIndex` 开始搜索（可选，默认为 0）**。**如果未找到，返回 -1。**
*   **示例代码：**

    ```javascript
    [1, 2, 3, 2, 1].indexOf(2); // 1
    [1, 2, 3, 2, 1].indexOf(2, 2); // 3
    ```

**`lastIndexOf(searchElement, fromIndex)`**

*    **用途：** 返回指定元素在数组中**最后一次出现的索引，从 `fromIndex` 开始*反向*搜索（可选，默认为数组末尾）**。**如果未找到，返回 -1。**
*   **示例代码：**

    ```javascript
       [1, 2, 3, 2, 1].lastIndexOf(2); // 3
    ```

**`includes(searchElement, fromIndex)`**

*   **用途：** 检查数组是否包含指定的元素，从 `fromIndex` 开始（可选，默认为 0）。返回 `true` 或 `false`。
*   **示例代码：**

    ```javascript
    [1, 2, 3].includes(2); // true
    ```

**`find(callback(element, index, array), thisArg)`**

*   **用途：** 返回数组中满足测试函数（`callback`）的**第一个元素的值**。否则返回 `undefined`。
    *   `callback`:  测试函数，接受三个参数：
        *   `element`: 当前正在处理的元素。
        *   `index`: 当前元素的索引。
        *   `array`: 调用 `find` 方法的数组。
    *   `thisArg`:  可选，执行 `callback` 时用作 `this` 的值。

*   **示例代码：**

    ```javascript
    let arr = [1, 5, 10, 15, 20];
    arr.find(element => element > 8); // 10
    ```

**`findIndex(callback(element, index, array), thisArg)`**

*   **用途：** 返回数组中满足测试函数（`callback`）的**第一个元素的索引**。否则返回 -1。参数同`find`。
*   **示例代码：**

    ```javascript
       let arr = [1, 5, 10, 15, 20];
       arr.findIndex(element => element > 8); // 2
    ```

---

##### 5. 数组转换

**`join(separator)`**

* **用途：** 将数组的所有元素连接成一个字符串。`separator` 是可选的分隔符，默认为逗号 (`,`)。

  如果数组中元素是undefined或者null，将转换成空字符串。

*   **示例代码：**

    ```javascript
    [1, 2, 3].join(); // "1,2,3"
    [1, 2, 3].join(""); // "123"
    [1, 2, 3].join("-"); // "1-2-3"
    ```

**`toString()`**

*  **用途：** 将数组转换成一个字符串, 数组中的元素之间用逗号分隔。
*  **示例代码：**

  ```javascript
    [1, 2, 'a', 'b'].toString() // "1,2,a,b"
  ```
**`slice(begin, end)`**

*   **用途:** 提取数组的一部分, 返回一个新数组, begin是开始索引, end是结束索引(不包含), 如果省略end, 提取到数组末尾。
*   **示例代码:**

    ```javascript
     const arr = [1,2,3,4,5]
     arr.slice(1,3) // [2,3]
    ```

---

##### 6. 修改

**`reverse()`**

*   **用途：**  颠倒数组中元素的顺序。***会改变原数组***。
*   **示例代码：**

    ```javascript
    let arr = [1, 2, 3];
    arr.reverse(); // arr 变为 [3, 2, 1]
    ```

**`sort(compareFunction)`**

*   **用途：** 对数组元素进行排序。***会改变原数组***。
    *   `compareFunction`: 可选，用于指定排序顺序的函数。
        *   如果省略，元素将转换为字符串，然后按照 Unicode 码点进行升序排序。
        *   如果提供 `compareFunction(a, b)`：
            *   如果 `compareFunction(a, b)` 返回小于 0 的值，则 `a` 排在 `b` 前面。
            *   如果 `compareFunction(a, b)` 返回大于 0 的值，则 `b` 排在 `a` 前面。
            *   如果 `compareFunction(a, b)` 返回 0，则 `a` 和 `b` 的相对位置不变。

*   **示例代码：**

    ```javascript
    let arr = [1, 5, 2, 10, 8];
    arr.sort(); // arr 变为 [1, 10, 2, 5, 8] (按字符串排序)
    
    // 升序排序（数字）
    arr.sort((a, b) => a - b); // arr 变为 [1, 2, 5, 8, 10]
    
    // 降序排序（数字）
    arr.sort((a, b) => b - a); //arr 变为[10, 8, 5, 2, 1]
    ```

**`fill(value, start, end)`**

* **用途：**用静态值填充数组。 从start到end(不包括)的元素, 如果省略, 填充整个数组。 ***会修改原数组。***
*  **示例代码：**
```javascript
    const arr = [1,2,3,4,5];
    arr.fill('a', 1,3);  // arr 变为 [ 1, 'a', 'a', 4, 5 ]
```
---

##### 7. 迭代

**`forEach(callback(currentValue, index, array), thisArg)`**

*   **用途：** 对数组的每个元素执行一次提供的函数（`callback`）。

    *   `callback`: 为数组中每个元素执行的函数，接受三个参数:
        *   `currentValue`: 数组中正在处理的当前元素。
        *   `index`: 数组中正在处理的当前元素的索引。
        *   `array`: `forEach` 遍历的数组
        *   `thisArg`: 可选项。当执行回调函数 `callback` 时，用作 `this` 的值。

*   **注意：** `forEach` 没有返回值 (返回 `undefined`)，它主要用于执行副作用，例如打印每个元素或更新外部变量。`forEach` 不能通过 `break` 或 `return` 提前终止循环。

*   **示例代码：**

    ```javascript
    let arr = [1, 2, 3];
    arr.forEach((value, index) => {
      console.log(`Element at index ${index}: ${value}`);
    });
    ```

**`map(callback(currentValue, index, array), thisArg)`**

*  **用途:** 创建一个新数组, 其结果是该数组中的每个元素都调用一次提供的函数后的返回值。

*  **`arr.map(...)`**

   - 调用数组 `arr` 的 `map()` 方法。`map()` 是一个高阶函数，它会**对数组中的每个元素执行一个提供的函数，并返回一个新的数组**，新数组的元素是原数组元素经过提供的函数处理后的结果。`map()` *不会* 修改原数组。

*   **示例代码：**

    ```javascript
        const array1 = [1, 4, 9, 16];
        const map1 = array1.map(x => x * 2);  // [2, 8, 18, 32]
    ```

**`filter(callback(element, index, array), thisArg)`**

*   **用途:** 创建一个新数组, 其包含通过所提供函数实现的测试的所有元素。

*  **示例代码：**

  ```javascript
        const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];
        const result = words.filter(word => word.length > 6); //  ["exuberant", "destruction", "present"]
  ```
---

##### 8. 归并

**`reduce(callback(accumulator, currentValue, index, array), initialValue)`**

* **用途：**对数组中的每个元素按序执行一个提供的 **reducer** 函数，每一次运行 **reducer** 会将先前元素的计算结果作为参数传入，最后将其结果汇总为单个返回值。
* **参数：**
    * `callback`: reducer 函数, 接受4个参数
      *  `accumulator`：累计器，累计回调的返回值
      *  `currentValue`：当前元素
      * `index`：当前索引
      * `array`: 调用reduce()的数组
     * `initialValue`：可选. 第一次调用 callback函数时的第一个参数的值。 如果没有提供初始值，则将使用数组中的第一个元素。
* **示例：**

  ```javascript
    const arr = [1,2,3,4,5];
    const sum = arr.reduce(
        (accumulator, currentValue) => accumulator + currentValue,
        0
    ); // 15
  ```

**`reduceRight(callback(accumulator, currentValue, index, array), initialValue)`**

* **用途：** 和`reduce`类似，但是从右向左归并。

---
**重要注意事项：**

*   **可变性 (Mutability):**  `push`, `pop`, `shift`, `unshift`, `splice`, `reverse`, `sort`, `fill` 这些方法*会改变原数组*。其他方法通常不会改变原数组 (但要注意, 如果在callback里修改了原数组, 也会造成影响)。
*    **稀疏数组:** JavaScript 允许创建稀疏数组（sparse arrays），即数组中可能存在未定义的元素。
* **多维数组:** 数组可以嵌套, 这就是所谓的多维数组。

这是 JavaScript 数组的详细笔记。如果还有问题，请随时提出！

---

#### 函数 (Function)

在 JavaScript 中，函数是“一等公民”（first-class citizens）。这意味着函数可以像其他任何数据类型（如数字、字符串、对象）一样被对待：

*   可以赋值给变量。
*   可以作为参数传递给其他函数。
*   可以作为其他函数的返回值。
*   可以在运行时创建和修改。

函数用于封装可重用的代码块，可以接受输入（参数），并产生输出（返回值）。

---

##### 1. 定义函数

JavaScript 中有多种定义函数的方式：

**函数声明 (Function Declaration)**

```javascript
function greet(name) {
  return `Hello, ${name}!`;
}
```

*   **特点：** 函数声明会被*提升*（hoisted），这意味着可以在声明之前调用函数。
*   命名小头峰原则，第二个单词开始首字母大写

**函数表达式 (Function Expression)**

```javascript
const greet = function(name) {
  return `Hello, ${name}!`;
};
```

*   **特点：** 函数表达式*不会*被提升。通常将函数表达式赋值给一个变量，然后通过变量名调用函数。

**箭头函数 (Arrow Function) (ES6+)**

```javascript
const greet = (name) => {
  return `Hello, ${name}!`;
};

// 简写形式（只有一个参数，且函数体只有一条 return 语句）
const greet = name => `Hello, ${name}!`;

//没有参数
const greet = () => {....};
```

*   **特点：**
    *   更简洁的语法。
    *   没有自己的 `this`、`arguments`、`super` 或 `new.target`。箭头函数中的 `this` 绑定的是定义时的上下文，而不是调用时的上下文。
    * 适合用于匿名函数和回调函数。

**Function 构造函数**
```javascript
    const sum = new Function('a', 'b', 'return a + b');
```
* **特点** 不推荐, 因为存在安全和性能问题。

---

#### 2. 函数参数

*   **形参 (Parameters):** 定义函数时列出的参数。
*   **实参 (Arguments):** 调用函数时传入的实际值。

```javascript
function add(x, y) { // x 和 y 是形参
  return x + y;
}

add(2, 3); // 2 和 3 是实参
```

*   **可选参数和默认值 (ES6+):** 可以为参数指定默认值，如果调用时没有传入该参数，则使用默认值。

    ```javascript
    function greet(name = "Guest") {
      return `Hello, ${name}!`;
    }

    greet("Alice"); // "Hello, Alice!"
    greet(); // "Hello, Guest!"
    ```

*   **剩余参数 (Rest Parameters) (ES6+):**  允许将不定数量的参数表示为一个数组。

    ```javascript
    function sum(...numbers) {
      let total = 0;
      for (const num of numbers) {
        total += num;
      }
      return total;
    }

    sum(1, 2, 3); // 6
    sum(1, 2, 3, 4, 5); // 15
    ```

* **arguments 对象**
  - 在*非箭头函数*中，`arguments` 是一个类数组对象，**包含了所有传入函数的参数**。
  - `arguments` **和传入的实参同步变化**。
  -  不推荐使用 `arguments` 对象；建议使用剩余参数。
  
    ```javascript
    function myFunc(){
        console.log(arguments[0]);
    }
    ```

---

#### 3. 函数返回值

*   函数使用 `return` 语句返回值。
*   如果函数没有 `return` 语句，或者 `return` 语句没有指定值，则返回 `undefined`。

```javascript
function add(x, y) {
  return x + y;
}

let result = add(2, 3); // result 为 5

function doSomething() {
  // 没有 return 语句
}

let value = doSomething(); // value 为 undefined
```

---

#### 4. 作用域 (Scope)

*   **全局作用域 (Global Scope):** 在函数外部声明的变量拥有全局作用域，可以在代码的任何地方访问。
*   **函数作用域 (Function Scope):** 在函数内部声明的变量（使用 `var`）拥有函数作用域，只能在函数内部访问。
*   **块级作用域 (Block Scope) (ES6+):** 使用 `let` 或 `const` 声明的变量拥有块级作用域，只能在声明它们的块（`{}`）中访问。

```javascript
// 全局作用域
let globalVar = "I am global";

function myFunction() {
  // 函数作用域
  var functionVar = "I am local to the function";
  if(true){
    let blockVar = 'I am local to the block';
  }
}
```

---

#### 5. 闭包 (Closure)

*   **定义：** 闭包是指有权访问另一个函数作用域中的变量的函数。
*   **常见创建方式：** 在一个函数内部创建另一个函数。
*   **作用：**
    *   可以读取函数内部的变量。
    *   让这些变量的值始终保存在内存中。

```javascript
function outerFunction() {
  let outerVar = "Hello";

  function innerFunction() {
    console.log(outerVar); // innerFunction 可以访问 outerFunction 的变量
  }

  return innerFunction;
}

let myClosure = outerFunction();
myClosure(); // 输出 "Hello"
```

---
#### 6.  立即执行函数 (IIFE, Immediately Invoked Function Expression)
   - **用途**: 创建一个函数并立即执行, 通常用于创建一个独立的作用域, 避免污染全局命名空间。
   - **示例**:
     ```javascript
        (function() {
        // 代码在这里
        })();
     ```
---

#### 7. 回调函数 (Callback Function)

*   **定义：**  作为参数传递给另一个函数，并在特定事件发生或特定条件满足时被调用的函数。
*  回调函数是异步编程的基础

```javascript
// 示例：setTimeout 的回调函数
setTimeout(function() {
  console.log("This will be executed after 2 seconds.");
}, 2000);
```

---

#### 8. this 关键字

*   `this` 的值取决于函数的调用方式：
    *   **作为对象的方法调用：** `this` 指向该对象。
    *   **作为普通函数调用：**
        *   非严格模式下，`this` 指向全局对象（浏览器中是 `window`）。
        *   严格模式下，`this` 为 `undefined`。
    *   **使用 `call`、`apply` 或 `bind` 调用：**  `this` 指向指定的对象。
    *   **构造函数中：** `this` 指向新创建的对象。
    *   **箭头函数中：** `this` 绑定的是定义时的上下文。

```javascript
const person = {
  name: "Alice",
  greet: function() {
    console.log(`Hello, my name is ${this.name}`);
  }
};

person.greet(); // "Hello, my name is Alice" (this 指向 person)

function sayHello() {
  console.log(`Hello, my name is ${this.name}`);
}

sayHello(); // 非严格模式："Hello, my name is undefined" (this 指向 window，window.name 通常为空)
           // 严格模式： 报错 (this 为 undefined)

const boundSayHello = sayHello.bind(person);
boundSayHello(); // "Hello, my name is Alice" (this 绑定到 person)
```
---

#### 9. 递归函数
* **定义：**  函数调用自身。
* 注意需要有终止条件, 否则会导致无限递归。
* **示例：** 阶乘

  ```javascript
    function factorial(n){
        if(n === 0){
          return 1;
        }else{
           return n * factorial(n-1);
        }
    }
  ```

---

#### 对象 (Object)

JavaScript 对象是键值对 (key-value pairs) 的集合。对象可以包含任何类型的数据（包括原始类型、其他对象和函数）。对象是 JavaScript 中最核心的概念之一，几乎所有的东西都是对象或可以表现得像对象。

```javascript
let person = {
  firstName: "Alice",
  lastName: "Smith",
  age: 30,
  hobbies: ["reading", "hiking"],
  greet: function() {
    console.log(`Hello, my name is ${this.firstName} ${this.lastName}`);
  }
};
```

---

##### 1. 创建对象

**对象字面量 (Object Literal)**

这是最常见的创建对象的方式：

```javascript
let obj = {
  key1: value1,
  key2: value2,
  // ...
};
```

**`new Object()`** **不推荐**，因为对象字面量更简洁。

```javascript
let obj = new Object();
obj.key1 = value1;
obj.key2 = value2;
```

**构造函数 (Constructor Function)**

用于创建具有相同属性和方法的多个对象：

```javascript
function Person(firstName, lastName, age) {
  this.firstName = firstName;
  this.lastName = lastName;
  this.age = age;
  this.greet = function() {
    console.log(`Hello, my name is ${this.firstName} ${this.lastName}`);
  };
}

let person1 = new Person("Alice", "Smith", 30);
let person2 = new Person("Bob", "Jones", 25);
```

**`Object.create()`**

```javascript
const myPrototype = {
    greet: function() {
        console.log('Hello!');
    }
}
const obj = Object.create(myPrototype);  //创建一个新对象，使用现有的对象来提供新创建的对象的__proto__。
```
---

##### 2. 访问属性

**点表示法 (Dot Notation)**

```javascript
console.log(person.firstName); // "Alice"
person.age = 31;
```

**方括号表示法 (Bracket Notation)**

```javascript
console.log(person["lastName"]); // "Smith"
person["age"] = 31;

let keyName = "age";
console.log(person[keyName]);//当属性名是动态的（例如，来自变量）时，必须使用方括号表示法.
```

---

##### 3. 添加/删除属性

**添加属性**

```javascript
person.email = "alice@example.com";
person["phone"] = "123-456-7890";
```

**删除属性**

```javascript
delete person.hobbies;
delete person["phone"];
```

---

##### 4. 对象方法

对象可以包含函数作为其属性，这些函数称为方法。

```javascript
let person = {
    //其他属性
  greet: function() {
    console.log(`Hello, my name is ${this.firstName} ${this.lastName}`);
  }
};

person.greet(); // 调用方法
```

---

##### 5. 遍历对象

**`for...in` 循环**

遍历对象的可枚举属性（包括继承的属性, 通常不希望包含继承的属性）。

```javascript
for (let key in person) {
    if (person.hasOwnProperty(key)) { // 检查是否是对象自身的属性
        console.log(key + ": " + person[key]);
    }
}
```

**`Object.keys(obj)`**

返回一个包含对象自身所有可枚举属性**名称**的数组。

```javascript
let keys = Object.keys(person); // ["firstName", "lastName", "age", "email", "greet"]
```

**`Object.values(obj)`**

返回一个包含对象自身所有可枚举**属性值**的数组。

```javascript
let values = Object.values(person); // ["Alice", "Smith", 31, "alice@example.com", function() { ... }]
```

**`Object.entries(obj)`**

- 返回一个给定对象自身可枚举**属性的键值**对数组
```javascript
  const object1 = {
    a: 'somestring',
    b: 42
  };

  for (const [key, value] of Object.entries(object1)) {
    console.log(`${key}: ${value}`);
  }
```

---

##### 6. `this` 关键字

在对象方法中，`this` 指向调用该方法的对象。

```javascript
let person = {
  name: "Alice",
  greet: function() {
    console.log(`Hello, my name is ${this.name}`); // this 指向 person
  }
};
```

---

##### 7. Getter 和 Setter (ES5+)

可以使用 `get` 和 `set` 关键字定义 getter 和 setter 方法，用于控制对属性的访问和修改。

```javascript
let person = {
  firstName: "Alice",
  lastName: "Smith",

  get fullName() {
    return `${this.firstName} ${this.lastName}`;
  },

  set fullName(value) {
    let parts = value.split(" ");
    this.firstName = parts[0];
    this.lastName = parts[1];
  }
};

console.log(person.fullName); // "Alice Smith" (调用 getter)
person.fullName = "Bob Jones"; // (调用 setter)
console.log(person.firstName); // "Bob"
console.log(person.lastName); // "Jones"
```

---

##### 8. 对象属性描述符 (Property Descriptors)

每个对象属性都有一个关联的属性描述符，它描述了属性的特性（如可写性、可枚举性、可配置性）。

*   **`value`:** 属性的值。
*   **`writable`:**  如果为 `false`，则无法修改属性的值。
*   **`enumerable`:** 如果为 `false`，则该属性不会出现在 `for...in` 循环和 `Object.keys()` 中。
*   **`configurable`:** 如果为 `false`，则无法删除属性，也无法更改属性的特性（除了可以将 `writable` 从 `true` 改为 `false`）。

可以使用 `Object.getOwnPropertyDescriptor(obj, propName)` 获取属性描述符，使用 `Object.defineProperty(obj, propName, descriptor)` 定义或修改属性描述符。

```javascript
let obj = { x: 1 };
let descriptor = Object.getOwnPropertyDescriptor(obj, "x");
/*
descriptor: {
  value: 1,
  writable: true,
  enumerable: true,
  configurable: true
}
*/

Object.defineProperty(obj, "y", {
  value: 2,
  writable: false, // 不可写
  enumerable: false, // 不可枚举
  configurable: false // 不可配置
});
```

---

#####  9. 原型 (Prototype) 和原型链 (Prototype Chain)

- **原型:** 每个 JavaScript 对象都有一个原型（prototype）对象。 原型本身也是一个对象, 因此原型对象也可能有自己的原型, 这样就形成了原型链。
- **原型链:** 当试图访问一个对象的属性时，JavaScript 引擎首先在该对象自身查找，如果找不到，则会沿着原型链向上查找，直到找到该属性或到达原型链的末端（`null`）。
-  `__proto__` (非标准但广泛支持) 和 `Object.getPrototypeOf()`: 用于访问对象的原型。
-  **`Object.create(proto)`:** 创建一个新对象, 并将其原型设置为 `proto`。
- **`prototype` 属性:** 只有函数对象才有 `prototype` 属性。 构造函数的 `prototype` 属性指向一个对象，该对象会被用作通过该构造函数创建的所有实例的原型。

```javascript
function Person(name) {
  this.name = name;
}

// 所有 Person 的实例都将继承 greet 方法
Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name}`);
};

let alice = new Person("Alice");
alice.greet(); // "Hello, my name is Alice" (通过原型链找到 greet 方法)

```

---

##### 10. `Object.assign()`

`Object.assign()` 方法用于将所有可枚举的自有属性的值从一个或多个源对象复制到目标对象。 它将返回目标对象。

```javascript
const target = { a: 1, b: 2 };
const source = { b: 4, c: 5 };

const returnedTarget = Object.assign(target, source);

console.log(target);
// Expected output: Object { a: 1, b: 4, c: 5 }

console.log(returnedTarget);
// Expected output: Object { a: 1, b: 4, c: 5 }

```

---

#### Math 对象

`Math` 是 JavaScript 的一个内置对象，它提供了一组数学常数和数学函数。`Math` 对象**不是构造函数**，因此你**不能创建 `Math` 对象的新实例**。你直接通过 `Math` 对象本身来使用它的属性和方法（例如，`Math.PI`、`Math.sin()`）。

---

##### 1. 常量 (Properties)

`Math` 对象提供了一些常用的数学常量：

*   **`Math.PI`**: 圆周率 π (约为 3.14159)
*   **`Math.E`**: 自然对数的底数 e (约为 2.718)
*   **`Math.LN2`**: 2 的自然对数 (约为 0.693)
*   **`Math.LN10`**: 10 的自然对数 (约为 2.303)
*   **`Math.LOG2E`**: 以 2 为底的 e 的对数 (约为 1.443)
*   **`Math.LOG10E`**: 以 10 为底的 e 的对数 (约为 0.434)
*   **`Math.SQRT2`**: 2 的平方根 (约为 1.414)
*   **`Math.SQRT1_2`**: 1/2 的平方根 (约为 0.707)

```javascript
console.log(Math.PI);
console.log(Math.E);
```

---

#### 2. 常用方法 (Methods)

**舍入方法**

*   **`Math.round(x)`**: 将 x 四舍五入到最接近的整数。
*   **`Math.ceil(x)`**: 将 x 向上舍入到最接近的整数（天花板函数）。
*   **`Math.floor(x)`**: 将 x 向下舍入到最接近的整数（地板函数）。
*   **`Math.trunc(x)`**: (ES6) 返回 x 的整数部分，移除所有小数位。

```javascript
Math.round(4.7); // 5
Math.round(4.4); // 4
Math.ceil(4.2); // 5
Math.floor(4.9); // 4
Math.trunc(4.7); // 4
```

**三角函数**

*   **`Math.sin(x)`**: 正弦 (x 是弧度)。
*   **`Math.cos(x)`**: 余弦 (x 是弧度)。
*   **`Math.tan(x)`**: 正切 (x 是弧度)。
*   **`Math.asin(x)`**: 反正弦 (返回弧度)。
*   **`Math.acos(x)`**: 反余弦 (返回弧度)。
*   **`Math.atan(x)`**: 反正切 (返回弧度)。
*   **`Math.atan2(y, x)`**: 返回从 x 轴到点 (x, y) 的角度 (返回弧度)。

```javascript
Math.sin(0); // 0
Math.cos(Math.PI); // -1
```

**指数和对数**

*   **`Math.pow(x, y)`**: x 的 y 次幂 (x<sup>y</sup>)。
*   **`Math.sqrt(x)`**: x 的平方根。
*   **`Math.cbrt(x)`**: (ES6) x 的立方根。
*   **`Math.exp(x)`**: e<sup>x</sup>.
*   **`Math.log(x)`**: x 的自然对数 (以 e 为底)。
*   **`Math.log10(x)`**: x 的以 10 为底的对数。
*   **`Math.log2(x)`**: (ES6) x 的以 2 为底的对数。

```javascript
Math.pow(2, 3); // 8 (2 * 2 * 2)
Math.sqrt(9); // 3
Math.exp(1);  // 2.718281828459045
```

**最大值、最小值**

*   **`Math.max(x1, x2, ..., xn)`**: 返回参数中的最大值。
*   **`Math.min(x1, x2, ..., xn)`**: 返回参数中的最小值。

```javascript
Math.max(1, 5, 2, 8, 3); // 8
Math.min(1, 5, 2, 8, 3); // 1
```

* 如果没有提供参数, `Math.max()` 返回 `-Infinity`, `Math.min()` 返回 `Infinity`.

**随机数**

*   **`Math.random()`**: 返回一个 0 (包含) 到 1 (不包含) 之间的伪随机数。

```javascript
Math.random(); // 例如：0.123456789
Math.random(); // 每次调用都会返回不同的值
```

* 生成特定范围的随机整数的常用公式：

```javascript
// [min, max)  （包含 min，不包含 max）
function getRandomInt(min, max) {
  return Math.floor(Math.random() * (max - min)) + min;
}

// [min, max] （包含 min 和 max）
function getRandomIntInclusive(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}
```

**绝对值**

*  **`Math.abs(x)`**: 返回 x 的绝对值。

```javascript
Math.abs(-5);  //5
```

**其他**

*   **`Math.sign(x)`**: (ES6) 返回 x 的符号 (1 表示正数, -1 表示负数, 0 表示 0, -0 表示 -0, NaN 表示 NaN)。
*  **`Math.hypot(...values)`**: (ES6) 返回其所有参数的平方和的平方根

---

**注意事项**

*   `Math` 对象的所有方法都是静态的（直接通过 `Math` 对象调用）。
*   三角函数的参数和返回值都是以弧度 (radians) 为单位，而不是角度 (degrees)。可以使用以下公式进行转换：
    *   弧度 = 角度 \* (Math.PI / 180)
    *   角度 = 弧度 \* (180 / Math.PI)
*   `Math.random()` 返回的是伪随机数，这意味着它们并不是真正随机的，而是通过一个算法生成的。在大多数情况下，这对于一般的应用已经足够了。如果需要更高质量的随机数（例如，用于加密），则应使用 `Web Cryptography API`。

---

#### Date 对象

`Date` 对象用于处理日期和时间。`Date` 对象是 JavaScript 的内置对象，它提供了获取和设置日期、时间、月份、年份等的方法。

---

##### 1. 创建 Date 对象

有几种方式可以创建 `Date` 对象：

*   **`new Date()`**: 创建一个表示当前日期和时间的 `Date` 对象。

    ```javascript
    let now = new Date();
    console.log(now); // 输出当前日期和时间
    ```

*   **`new Date(milliseconds)`**: 创建一个表示自 1970 年 1 月 1 日 00:00:00 UTC（协调世界时）以来经过指定毫秒数的日期和时间的对象。

    ```javascript
    let epoch = new Date(0); // 1970-01-01T00:00:00.000Z
    let someDate = new Date(1678886400000); // 毫秒数
    ```

*   **`new Date(dateString)`**:  解析一个表示日期和时间的字符串，并返回对应的 `Date` 对象。日期字符串的格式有很多种，但建议使用 ISO 8601 格式 (YYYY-MM-DDTHH:mm:ss.sssZ)。

    ```javascript
    let date1 = new Date("2023-10-26");
    let date2 = new Date("October 26, 2023 14:30:00");
    ```

*   **`new Date(year, monthIndex [, day [, hours [, minutes [, seconds [, milliseconds]]]]])`**: 使用指定的年、月、日、时、分、秒和毫秒创建 `Date` 对象。

    *   `year`: 年份（四位数）。
    *   `monthIndex`: 月份 **(0 表示一月, 11 表示十二月)**。
    *   `day` (可选): 日 (1-31)。 默认1。
    *   `hours` (可选): 时 (0-23)。默认0。
    *   `minutes` (可选): 分 (0-59)。默认0。
    *   `seconds` (可选): 秒 (0-59)。默认0。
    *   `milliseconds` (可选): 毫秒 (0-999)。默认0。

    ```javascript
    let date3 = new Date(2023, 9, 26); // 2023 年 10 月 26 日 (月份从 0 开始)
    let date4 = new Date(2023, 9, 26, 14, 30, 0); // 2023 年 10 月 26 日 14:30:00
    ```

---

##### 2. 获取日期和时间的方法

`Date` 对象提供了许多方法来获取日期和时间的各个部分：

*   **`getFullYear()`**: 获取年份 (四位数)。
*   **`getMonth()`**: 获取月份 (0-11，0 表示一月)。
*   **`getDate()`**: 获取月份中的第几天 (1-31)。
*   **`getDay()`**: 获取星期几 (0-6，0 表示星期日)。
*   **`getHours()`**: 获取小时 (0-23)。
*   **`getMinutes()`**: 获取分钟 (0-59)。
*   **`getSeconds()`**: 获取秒 (0-59)。
*   **`getMilliseconds()`**: 获取毫秒 (0-999)。
*   **`getTime()`**: 获取自 1970 年 1 月 1 日 00:00:00 UTC 以来的毫秒数 (时间戳)。
*   **`getTimezoneOffset()`**: 获取本地时间与 UTC 时间之间的时差（以分钟为单位）。

```javascript
let now = new Date();
console.log(now.getFullYear()); // 2023 (当前年份)
console.log(now.getMonth());    // 9 (当前月份，0-11)
console.log(now.getDate());    // 26 (当前日期，1-31)
console.log(now.getDay());     // 4 (当前星期几，0-6)
console.log(now.getTime());    // 1698326400000 (当前时间戳)
```

**UTC 时间**

上述方法都是基于本地时间。还有一组对应的方法用于获取 UTC 时间：

*    `getUTCFullYear()`
*    `getUTCMonth()`
*    `getUTCDate()`
*   `getUTCDay()`
*    `getUTCHours()`
*   `getUTCMinutes()`
*    `getUTCSeconds()`
*	`getUTCMilliseconds()`

---

##### 3. 设置日期和时间的方法

`Date` 对象也提供了设置日期和时间的方法：

*   **`setFullYear(year [, month [, day]])`**: 设置年份。
*   **`setMonth(month [, day])`**: 设置月份。
*   **`setDate(day)`**: 设置月份中的第几天。
*   **`setHours(hour [, min [, sec [, ms]]])`**: 设置小时。
*   **`setMinutes(min [, sec [, ms]])`**: 设置分钟。
*   **`setSeconds(sec [, ms])`**: 设置秒。
*   **`setMilliseconds(ms)`**: 设置毫秒。
*   **`setTime(milliseconds)`**: 设置自 1970 年 1 月 1 日 00:00:00 UTC 以来的毫秒数。

```javascript
let date = new Date();
date.setFullYear(2024); // 设置年份为 2024
date.setMonth(0);   // 设置月份为一月
date.setDate(15);  // 设置日期为 15 号
```

**UTC 时间**
*   `setUTCFullYear(year [, month [, day]])`
*   `setUTCMonth(month [, day])`
*  `setUTCDate(day)`
* `setUTCHours(hour [, min [, sec [, ms]]])`
*   `setUTCMinutes(min [, sec [, ms]])`
*   `setUTCSeconds(sec [, ms])`
*	`setUTCMilliseconds(ms)`

---

##### 4. 日期格式化

JavaScript 没有内置的日期格式化函数，但你可以使用 `Date` 对象的方法手动构建格式化字符串，或者使用一些库（如 Moment.js、date-fns）来简化日期格式化。

```javascript
// 手动格式化
function formatDate(date) {
  let year = date.getFullYear();
  let month = String(date.getMonth() + 1).padStart(2, '0'); // 补零
  let  day = String(date.getDate()).padStart(2, '0');      // 补零

  return `${year}-${month}-${day}`;
}

let now = new Date();
console.log(formatDate(now)); // "2023-10-26"
```

*  可以使用 `Intl.DateTimeFormat` 对象, 这是ECMAScript 国际化 API 的一部分

```javascript
    const date = new Date(Date.UTC(2012, 11, 20, 3, 0, 0));

    // formats below assume the local time zone of the locale;
    // America/Los_Angeles for the US

    // US English uses month-day-year order
    console.log(new Intl.DateTimeFormat('en-US').format(date));
    // Expected output: "12/20/2012"
```

---

##### 5. 日期比较

可以直接使用比较运算符 (`>`、`<`、`>=`、`<=`) 来比较两个 `Date` 对象。比较的是它们的时间戳。

```javascript
let date1 = new Date("2023-10-25");
let date2 = new Date("2023-10-26");

console.log(date1 < date2); // true
```

---

##### 6. 日期计算
*  可以基于毫秒进行加减运算
```javascript
    const today = new Date();
    const nextday = new Date(today.getTime() + (24 * 60 * 60 * 1000));
```
---
##### 7. 静态方法
*   `Date.now()`: 返回当前时间的时间戳。
*   `Date.parse()`: 解析一个表示日期的字符串，并返回相应的自 1970 年 1 月 1 日 00:00:00 UTC 起的毫秒数。
*  `Date.UTC()`: 接受的参数和 `Date` 构造函数一样，返回自 1970-1-1 00:00:00 UTC 到指定日期的的毫秒数。
```javascript
    Date.UTC(year, [month], [date], [hrs], [min], [sec], [ms])
```
---

#### DOM (Document Object Model) 概述

DOM，全称 Document Object Model（文档对象模型），是 W3C（万维网联盟）制定的一套标准，用于表示和操作 HTML、XML 和 SVG 文档。DOM 将文档表示为一个树形结构，其中每个节点都代表文档的一部分（如元素、属性、文本等）。

---

##### 1. DOM 的核心概念

*   **文档 (Document):** 整个 HTML、XML 或 SVG 文档。
*   **节点 (Node):** DOM 树中的任何一个对象。节点有很多类型，最常见的是：
    *   **元素节点 (Element Node):** HTML 标签（如 `<div>`、`<p>`、`<h1>`）。
    *   **文本节点 (Text Node):** 元素节点中的文本内容。
    *   **属性节点 (Attribute Node):** 元素的属性（如 `id`、`class`、`src`）。
    *   **注释节点 (Comment Node):** HTML 注释 (`<!-- ... -->`)。
    *   **文档节点 (Document Node):** 整个文档。
*   **节点树 (Node Tree):** DOM 将文档表示为一棵树，其中节点之间存在层次关系（父子、兄弟等）。
*   **根节点 (Root Node):** 树的最顶层节点。对于 HTML 文档，根节点通常是 `<html>` 元素。

<img src="https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/image-20250315172326839.png" alt="image-20250315172326839" style="zoom:67%;" />

---

##### 2. DOM 的作用

*   **动态修改内容:** DOM 允许 JavaScript 代码动态地创建、添加、删除和修改 HTML 元素、属性和文本。
*   **响应用户交互:** DOM 允许 JavaScript 代码监听用户事件（如点击、鼠标移动、键盘输入），并根据事件做出响应。
*   **构建交互式 Web 应用:** DOM 是构建各种交互式 Web 应用的基础，从简单的表单验证到复杂的单页应用 (SPA)。

---

##### 3. 访问 DOM 节点

JavaScript 提供了多种方法来访问 DOM 树中的节点：

*   **`document.getElementById(id)`:** 通过元素的 `id` 属性获取元素节点（返回单个元素）。
*   **`document.getElementsByClassName(className)`:** 通过元素的 `class` 属性获取元素节点列表（返回 HTMLCollection，类数组对象）。
*   **`document.getElementsByTagName(tagName)`:** 通过元素的标签名获取元素节点列表（返回 HTMLCollection）。
*   **`document.querySelector(selector)`:** 通过 CSS 选择器获取第一个匹配的元素节点（返回单个元素）。
*   **`document.querySelectorAll(selector)`:** 通过 CSS 选择器获取所有匹配的元素节点列表（返回 NodeList，类数组对象）。

```javascript
// 获取 id 为 "myElement" 的元素
let elementById = document.getElementById("myElement");

// 获取 class 为 "myClass" 的所有元素
let elementsByClass = document.getElementsByClassName("myClass");

// 获取所有 <p> 元素
let elementsByTag = document.getElementsByTagName("p");

// 获取第一个 class 为 "myClass" 的元素
let querySelectorElement = document.querySelector(".myClass");

// 获取所有 class 为 "myClass" 的元素(返回一个List)
let querySelectorAllElements = document.querySelectorAll(".myClass");
```

+ ```html
  <!DOCTYPE html>
  <html lang="en">
  
  <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
      <style>
          * {
              margin: 0;
              box-sizing: border-box;
          }
  
          .box {
              width: 200px;
              height: 200px;
              border: 5px solid orange;
              background-color: blue;
              display: block;
              text-align: center;
              margin: 20px;
              padding: 30px;
          }
      </style>
  </head>
  
  <body>
      <div class="box" id="box1">hio</div>
      <script>
          var box = document.getElementById('box1');
          console.log(box.clientHeight);
          console.log(box.clientWidth);
  
          console.log('页面高度是' + document.documentElement.clientHeight);
          console.log('页面宽度是' + document.documentElement.clientWidth);
          console.log('body高度是' + document.body.clientHeight);
          console.log('body宽度是' + document.body.clientWidth);
      </script>
  </body>
  
  </html>
  ```

---

##### 4. 节点关系

DOM 节点之间存在层次关系：

*   **`parentNode`:** 获取节点的父节点。
*   **`childNodes`:** 获取节点的所有子节点（包括文本节点和注释节点）的 NodeList。
*   **`children`:** 获取节点的所有元素子节点（不包括文本节点和注释节点）的 HTMLCollection。
*   **`firstChild`:** 获取节点的第一个子节点。
*   **`lastChild`:** 获取节点的最后一个子节点。
*   **`nextSibling`:** 获取节点的下一个兄弟节点。
*   **`previousSibling`:** 获取节点的前一个兄弟节点。

```javascript
let element = document.getElementById("myElement");
let parent = element.parentNode; // 获取父节点
let children = element.children;   // 获取所有元素子节点
```

---

##### 5. 操作 DOM 节点

JavaScript 提供了多种方法来操作 DOM 节点：

*   **创建节点：**
    
    *   **`document.createElement(tagName)`:** 创建一个新的元素节点。
    *   **`document.createTextNode(text)`:** 创建一个新的文本节点。
    *   **`document.createDocumentFragment()`** 创建一个空的文档片段对象
    
*   **添加节点：**
    
    *   **`parentNode.appendChild(newNode)`:** 将 `newNode` 作为 `parentNode` 的最后一个子节点添加。
    *   **`parentNode.insertBefore(newNode, referenceNode)`:** 将 `newNode` 插入到 `parentNode` 的 `referenceNode` 之前。
    *   **`append()`** (较新, 实验中): 类似于 `appendChild`, 但可以一次添加多个节点, 还可以追加字符串
    *   **`prepend()`** (较新, 实验中): 将节点添加到父节点的第一个子节点之前
    
*   **删除节点：**
    
    *   **`parentNode.removeChild(childNode)`:** 从 `parentNode` 中删除 `childNode`。
    *    **`childNode.remove()`** （较新）从dom中删除自身
    
*   **替换节点：**
    
    *   **`parentNode.replaceChild(newNode, oldNode)`:** 用 `newNode` 替换 `parentNode` 中的 `oldNode`。
    
*   **修改节点属性：**
    
    *   **`element.setAttribute(name, value)`:** 设置元素的属性值。
    *   **`element.getAttribute(name)`:** 获取元素的属性值。
    *   **`element.removeAttribute(name)`:** 删除元素的属性。
    *   **`element.classList`:** (add, remove, toggle, contains) 操作元素的 class 列表。
    
*   **修改节点文本内容：**
    *   **`element.textContent`:** 获取或设置元素的文本内容（包括所有子节点的文本内容，会移除所有 HTML 标签）。
    *   **`element.innerHTML`:** 获取或设置元素的 HTML 内容（包括所有子节点的 HTML 结构）。
    *    **`node.innerText`**: 获取/设置元素的"渲染"文本内容(注意与`textContent`的区别, `innerText` 会受 CSS 样式影响).

*   **修改元素样式：**
    *   **`element.style.property = value`:** 直接设置元素的 CSS 样式。
        
        ```javascript
        //改变背景颜色
        document.getElementById("myDiv").style.backgroundColor = "blue";
        ```

+ **修改CSS :** 

  ```html
  <body>
      <div class="box" id="box1">GOOD</div>
      <script>
          var box = document.getElementById('box1');
          // 方法一
          box.setAttribute('style','width:100px;height:100px;background-color:grey;');
          
          // 方法二
          box.style.width = '100px'; 
          box.style.height = '100px';
          box.style.backgroundColor = 'grey';
          box.style.border = '1px solid red';
          box.style.margin = '10px';
          box.style.padding = '10px';
          
          // 方法三
          box.style.cssText = 'width:100px;height:100px;background-color:grey;border:1px solid red;margin:10px;padding:10px;';
      </script>
  </body>
  ```

---

##### 6. 事件处理 (Event Handling)

DOM 允许 JavaScript 代码对用户交互或其他事件做出响应：

*   **事件监听器 (Event Listener):**  附加到元素上的函数，当指定事件发生时会被触发。

*   **添加事件监听器：**
    *   **`element.addEventListener(event, function, useCapture)`:**
        *   `event`: 事件类型（如 "click"、"mouseover"、"keydown"）。
        *   `function`: 事件处理函数。
        *   `useCapture` (可选):  一个布尔值，指定事件是在捕获阶段还是冒泡阶段处理（默认是 `false`，表示冒泡阶段）。

    ```javascript
    // 添加点击事件监听器
    let button = document.getElementById("myButton");
    button.addEventListener("click", function() {
    alert("Button clicked!");
    });
    ```

*   **移除事件监听器:**
    *   **`element.removeEventListener(event, function, useCapture)`**
        *   注意: `function` 必须与 `addEventListener` 中使用的函数相同(通常需要将事件处理函数存储在变量中)

*   **事件对象 (Event Object):** 当事件发生时，事件处理函数会自动接收一个事件对象作为参数，该对象包含有关事件的详细信息。
    *   `event.target`: 触发事件的元素。
    *   `event.type`: 事件类型。
    *   `event.preventDefault()`: 阻止事件的默认行为。
    *   `event.stopPropagation()`: 阻止事件冒泡。

*   **事件流 (Event Flow):**
    *   **捕获阶段 (Capturing Phase):**  事件从根节点向下传播到目标元素。
    *   **目标阶段 (Target Phase):** 事件到达目标元素。
    *   **冒泡阶段 (Bubbling Phase):** 事件从目标元素向上冒泡到根节点。

---

##### 7. DocumentFragment

-   `DocumentFragment` 接口表示一个没有父级文件的最小文档对象.
-   它被当做一个轻量版的 `Document` 使用，用于存储已排好版的或尚未打理好格式的 XML 片段。
-   最大的区别在于: `DocumentFragment` 不是真实 DOM 树的一部分，它的变化不会触发 DOM 树的重新渲染，且不会导致性能等问题。
- `DocumentFragment` 继承自 `Node`

```javascript
    const list = document.querySelector('#list');
    const fruits = ['Apple', 'Orange', 'Banana', 'Melon'];

    const fragment = new DocumentFragment();

    fruits.forEach(fruit => {
        const li = document.createElement('li');
        li.textContent = fruit;
        fragment.appendChild(li);
    });

    list.appendChild(fragment);
```

---

#### 事件

事件处理程序分为：

1. HTML事件处理
2. DOM0级事件处理
3. DOM2级事件处理

##### HTML事件（不推荐）

```html
<body>
    <button id = "btn_Hello" onclick="clickHandler()">
        点击我弹出Hello
    </button>
    <script>
        var btn_Hello = document.getElementById('btn_Hello');
        function clickHandler(){
            alert('Hello');
        }
    </script>
</body>
```

##### DOM0级事件处理

```html
<body>
    <button id = "btn_Hello">
        点击我
    </button>
    <script>
        var btn_Hello = document.getElementById('btn_Hello');
        btn_Hello.onclick = function(){
            alert('Hello');
        }
        btn_Hello.onclick = function(){
            alert('Hello Dear');
        }
    </script>
</body>
```

+ 优点是相比 HTML 事件，DOM0级事件JS和HTML分离
+ 缺点是无法添加多个事件，出现覆盖的情况

##### DOM2级事件处理

```html
<body>
    <button id = "btn_Hello">
        点击我弹出Hello
    </button>
    <script>
        var btn_Hello = document.getElementById('btn_Hello');
        btn_Hello.addEventListener('click', function(){
            alert('Hello');
        });
        btn_Hello.addEventListener('click', function(){
            alert('Hello dear');
        });
    </script>
</body>
```

+ 可以同时添加多个事件函数

##### 鼠标事件

鼠标事件指与鼠标相关的事件，具体的事件主要有以下一些

1. **click：按下鼠标时触发（单击）**
2. **dblclick：在同一个元素上双击鼠标时触发**
3. **mousedown：按下鼠标键时触发**
4. **mouseup：释放按下的鼠标键时触发**
5. **mousemove：当鼠标在节点内部移动时触发。当鼠标持续移动时，该事件会连触发。**
6. **mouseenter：鼠标进入一个节点时触发，进入子节点不会触发这个事件**
7. **mouseleave：鼠标离开一个节点时触发，离开父节点不会触发这个事件**
8. **mouseover：鼠标进入一个节点时触发，进入子节点会再一次触发这个事件**
9. **mouseout：鼠标离开一个节点时触发，离开父节点也会触发这个事件**
10. **wheel：滚动鼠标的滚轮时触发**

```js
var btn1 = document.getElementById("btn1");
btn1.onclick = function(){
    console.log("click事件");
}
```

> **温馨提示**
>
> 这些方法在使用的时候，除了DOM2级事件，都需要添加前缀`on`

---

##### Event 对象

**Event.preventDefault**

Event.preventDefault方法取消浏览器对当前事件的默认行为。比如点击链接后，浏览器默认会跳转到另一个页面，使用这个方法以后，就不会跳转了

```js
btn.onclick = function(e){
    e.preventDefault(); // 阻止默认事件
    console.log("点击A标签");
}
form1.addEventListener('submit', function(e){
    e.preventDefault(); // 阻止默认事件
    console.log('submit');
    form1.reset();
```

**Event.stopPropagation()**

stopPropagation方法**阻止事件在 DOM 中继续传播（阻止事件冒泡）**，防止再触发定义在别的节点上的监听函数，但是不包括在当前节点上其他的事件监听函数。

```js
btn.onclick = function(e){
    e.stopPropagation(); // 阻止事件冒泡
    console.log("btn");
}
```

##### 键盘事件

键盘事件由用户击打键盘触发，主要有keydown、keypress、keyup三个事件

1. keydown：按下键盘时触发。
2. keypress：按下有值的键时触发，即按下 Ctrl、Alt、Shift、Meta 这样无值的键，这个事件不会触发。对于有值的键，按下时先触发keydown事件，再触发这个事件。
3. keyup：松开键盘时触发该事件

```js
username.onkeypress = function(e){
    console.log("keypress事件");
}

password.onkeyup = function(e){
    console.log(e.target.value);
}
```

##### 表单事件

表单事件是在使用表单元素及输入框元素可以监听的一系列事件

1. input事件
2. select事件
3. Change事件
4. reset事件
5. submit事件

**input事件**

input事件当`<input>、<select>、<textarea>`的值发生变化时触发。对于复选框（`<input type=checkbox>`）或单选框（`<input type=radio>`），用户改变选项时，也会触发这个事件

input事件的一个特点，就是会连续触发，比如用户每按下一次按键，就会触发一次input事件。

```js
var username = document.getElementById("username");
username.oninput = function(e){
    console.log(e.target.value);
}
```

**select事件**

select事件当在`<input>、<textarea>`里面选中文本时触发

```js
// HTML 代码如下
// <input id="test" type="text" value="Select me!" />

var elem = document.getElementById('test');
elem.addEventListener('select', function (e) {
  console.log(e.type); // "select"
}, false);
```

**Change 事件**

Change事件当`<input>、<select>、<textarea>`的值发生变化时触发。它与input事件的最大不同，就是不会连续触发，只有当全部修改完成时才会触发

```js
var email = document.getElementById("email");
email.onchange = function(e){
    console.log(e.target.value);
}
```

**reset 事件，submit 事件**

这两个事件发生在表单对象`<form>`上，而不是发生在表单的成员上。

reset事件当表单重置（所有表单成员变回默认值）时触发。

submit事件当表单数据向服务器提交时触发。注意，submit事件的发生对象是`<form>`元素，而不是`<button>`元素，因为提交的是表单，而不是按钮

```html
<form id="myForm" onsubmit="submitHandle">
    <button onclick="resetHandle">重置数据</button>
    <button>提交</button>
</form>
```

```js
var myForm = document.getElementById("myForm")
function resetHandle(){
    myForm.reset();
}
function submitHandle(){
    console.log("提交");
}
```

```js
        var form1 = document.getElementById('form1');
        form1.name1.addEventListener('change', function(e){
            console.log(e.target.value);
        });

        form1.addEventListener('submit', function(e){
            e.preventDefault();
            console.log('submit');
            form1.reset();
        });
```

##### 事件代理

由于事件会在冒泡阶段向上传播到父节点，因此可以把**子节点的监听函数定义在父节点上，由父节点的监听函数统一处理多个子元素的事件**。这种方法叫做事件的代理（delegation）

```js
var ul = document.querySelector('ul');

ul.addEventListener('click', function (e) {
  if (e.target.tagName.toLowerCase() === 'li') {
    // some code
  }
});

        var ul = document.querySelector('ul');
        ul.addEventListener('click', function(e){
            if(e.target.tagName === 'LI'){
                console.log("点击了 " + e.target.innerHTML);
            }
        });
```

---

JavaScript 提供定时执行代码的功能，叫做定时器（timer），主要由`setTimeout()`和`setInterval()`这两个函数来完成。它们向任务队列添加定时任务

##### 定时器 setTimeout()

`setTimeout`函数用来指定某个函数或某段代码，在多少毫秒之后执行。它返回一个整数，表示定时器的编号，以后可以用来取消这个定时器。

```js
var timerId = setTimeout(func|code, delay);
```

`setTimeout`函数接受两个参数，第一个参数`func|code`是将要推迟执行的函数名或者一段代码，第二个参数`delay`是推迟执行的毫秒数

```js
setTimeout(function(){
    console.log("定时器")
},1000)
```

> **温馨提示**
>
> 还有一个需要注意的地方，如果回调函数是对象的方法，那么`setTimeout`使得方法内部的`this`关键字指向全局环境，而不是定义时所在的那个对象

```js
var name = "Anx";
var user = {
    name: "Vee",
    getName: function () {
        setTimeout(function(){
            console.log(this.name);
        },1000) // 打印 Anx
    }
};
user.getName(); // 打印 Vee
```

解决方案

```js
var name = "Anx";
var user = {
    name: "Vee",
    getName: function () {
        var that = this;
        setTimeout(function(){
            console.log(that.name);
        },1000)
    }
};
user.getName();
```

定时器可以进行取消

```js
var id = setTimeout(f, 1000);
clearTimeout(id);
```

##### setInterval() 定时器

`setInterval`函数的用法与`setTimeout`完全一致，区别仅仅在于`setInterval`指定某个任务每隔一段时间就执行一次，也就是无限次的定时执行

```js
var timer = setInterval(function() {
  console.log(2);
}, 1000)
```

通过setInterval方法实现网页动画

```js
        var div = document.querySelector('div');

        var i = 0;
        div.style.opacity = 1;
        var timer = setInterval(function(){
            console.log(i++);
            div.style.opacity -= 0.05;
            if(div.style.opacity < 0 ){
                clearInterval(timer);
            }
        }, 50);
```

定时器可以进行取消

```js
var id = setInterval(f, 1000);
clearInterval(id);
```

---

#### 防抖 (debounce)

防抖严格算起来应该属于性能优化的知识，但实际上遇到的频率相当高，处理不当或者放任不管就容易引起浏览器卡死。

在第一次触发事件时，不立即执行函数，而是给出一个期限值比如200ms，然后

1. 如果在200ms内没有再次触发滚动事件，那么就执行函数
2. 如果在200ms内再次触发滚动事件，那么当前的计时取消，重新开始计时

效果：如果短时间内大量触发同一事件，只会执行一次函数

实现：关键就在于setTimeout这个函数，由于还需要一个变量来保存计时，考虑维护全局纯净，可以借助闭包来实现

```js
// DEBOUNCE 检查当前有没有timer，有则清除，然后设置  timer = setTimeout(打印, 200ms)
DEBOUNCE = function(fn, delay){
            var timer = null;
            return function(){
                if (timer){
                    clearTimeout(timer);
                }
                timer = setTimeout(fn, delay);
            }
        }
// fn_debounce 传递打印函数和时间间隔200ms
        fn_debounce = DEBOUNCE(function(){
            console.log(window.scrollY);
        }, 200);

// 滚动时都会触发  fn_debounce
window.addEventListener('scroll', fn_debounce); 
```

> **防抖定义**
>
> 对于短时间内连续触发的事件（上面的滚动事件），防抖的含义就是让某个时间期限内，事件处理函数只执行一次

#### 节流(throttle)

上面的代码中，如果在限定时间段内，不断触发滚动事件（比如某个用户闲着无聊，按住滚动不断的拖来拖去），只要不停止触发，理论上就永远不会输出当前距离顶部的距离。

我们可以设计一种类似控制阀门一样定期开放的函数，也就是让函数执行一次后，在某个时间段内暂时失效，过了这段时间后再重新激活（类似于技能冷却时间）

效果：如果短时间内大量触发同一事件，那么在函数执行一次之后，该函数在指定的时间期限内不再工作，直至过了这段时间才重新生效。

```js
  function throttle(fn, delay) {
            let last = 0; // 初始时间设置为0
            return function () {
                const now = Date.now();
                if (now - last < delay) {
                    // 冷却中，不执行
                    return;
                }
                last = now; // 更新上次执行时间
                fn(); // 执行函数
            };
        }

        printY = function () {
            console.log(window.scrollY);
        };

        window.addEventListener('scroll', throttle(printY, 2000));
```

---

#### ES6+

##### 前置环境

先安装 node.js 用 `node -v` 检查；

检查 `npm -v`。

可以选择npm的国内镜像 cnpm，安装 cnpm：

```bash
npm install -g cnpm --registry=https://registry.npmmirror.com
```

##### Babel 转码器

ES6转换为ES5代码，从而在旧版本浏览器可以执行。

https://babeljs.io/

安装babel：

```bash
npm install --save-dev @babel/core @babel/cli @babel/preset-env
```

使用：

```
npx babel .\origin_file.js -o new file.js
```

#### 新命令

##### let、const

| 特性       | `var`      | `let`          | `const`        |
| ---------- | ---------- | -------------- | -------------- |
| 作用域     | 函数作用域 | **块级**作用域 | **块级**作用域 |
| 变量提升   | 存在       | 暂时性死区     | 暂时性死区     |
| 重新赋值   | 可以       | 可以           | 不可以         |
| 声明时赋值 | 可选       | 可选           | 必须           |
| 重复声明   | 可         | 不可           | 不可           |

**最佳实践**

- 优先使用 `const`（常量）：如果一个变量在声明后不需要重新赋值，就应该使用 `const`。这有助于提高代码的可读性和可维护性，并减少意外的变量修改。
- 其次使用 `let`：如果一个变量需要重新赋值（例如，循环计数器），则使用 `let`。
- 避免使用 `var`：由于 `var` 的函数作用域和变量提升特性更容易导致意外的错误和混乱，因此在现代 JavaScript 开发中应尽量避免使用 `var`。
- 在需要变量作用域穿透到循环外部的场景下， 可以选择使用`var`.

示例：let 和 var 效果不同

```js
var a = [];
for (var i = 0; i < 10; i++) {
  a[i] = function () {
    console.log(i);
  };
}
a[6](); // 10 (因为 var 的作用域，所有闭包都引用同一个 i，最终值为 10)

var a = [];
for (let i = 0; i < 10; i++) {
  a[i] = function () {
    console.log(i); // 10
  };
}
a[6](); // 6
```

#### 对象解构赋值 (Object Destructuring)

对象解构赋值是一种方便的语法，可以从对象中提取属性值并赋给变量。

```javascript
const person = {
  firstName: 'Alice',
  lastName: 'Smith',
  age: 30
};

// 传统方式
const firstName = person.firstName;
const age = person.age;

// 解构赋值
const { firstName, age } = person; // 变量名需要与对象属性名相同
//相当于 const firstName = person.firstName; const age = person.age;

console.log(firstName); // "Alice"
console.log(age); // 30

// 可以使用不同的变量名
const { firstName: fName, age: personAge } = person;
console.log(fName); // "Alice"
console.log(personAge); // 30

// 可以设置默认值
const { country = 'USA' } = person;
console.log(country); // "USA" (因为 person 对象中没有 country 属性)

// 嵌套对象解构
const student = {
    name: "Bob",
    score: {
        math: 90,
        english: 80
    }
}
const {score: {math}} = student;
```

---

#### 字符串扩展 (String Extensions)

* **模板字面量 (Template Literals)**:  使用反引号 (`) 创建字符串，支持多行字符串和变量插值。

  ```js
  // 创建一个动态标签
  var herf = 'https://www.google.com';
  var text = 'Google';
  var welcome = `<a href="${herf}">welcome to ${text}</a>`;
  testdiv.innerHTML = welcome;
  ```

* **Unicode 支持增强**:  更好地处理 Unicode 字符，包括新的 Unicode 字面量表示法 (`\u{...}`)。

  ```js
  console.log('\u0061'); // a
  ```

* **`for of`**: 遍历字符串；

  ```js
  for (let l of str) {
       console.log(l);
   }
  ```

---

#### 字符串新增方法 (New String Methods)

ES5 只有**` indexOf()`** 可以判定字符串之间的包含关系，ES6新增了几个方法：

*   **`includes(substring, start?)`**: 判断字符串是否包含指定的子字符串 (返回 `true`/`false`)。`start` 参数可选，表示开始搜索的位置。
*   **`startsWith(substring, start?)`**: 判断字符串是否以指定的子字符串开头 (返回 `true`/`false`)。
*   **`endsWith(substring, length?)`**: 判断字符串是否以指定的子字符串结尾 (返回 `true`/`false`)。`length` 参数可选，表示把前 length 个字符当作字符串。
*   **`repeat(count)`**: 将字符串重复指定次数，返回一个新字符串。

```javascript
const str = "Hello, world!";

console.log(str.includes("world")); // true
console.log(str.startsWith("Hello")); // true
console.log(str.endsWith("!")); // true
console.log("abc".repeat(3)); // "abcabcabc"
```

+ **`padStart(targetLength, padString)`**

  + **用途：** 用 `padString`（默认为空格）在字符串的开头填充，直到字符串达到 `targetLength`。

  + **示例代码：**

    ```js
    'hello'.padStart(10, 'ab'); // 'ababahello'
    ```

+ **`padEnd(targetLength, padString)`**

  + **用途：** 用 `padString`（默认为空格）在字符串的末尾填充，直到字符串达到 `targetLength`。

  + **示例代码：**

    ```js
    '5'.padEnd(3, '0'); // '500'
    ```

+ **`at()`**

  + **用途：** 接受一个整数，返回指定索引的字符。超出范围返回` undefined`

  + **示例代码：**

    ```js
    const str_greet = 'Guten Morgen'
    str_greet.at(1) // 'u'
    str_greet.at(-1) //'n'
    ```

---

#### 数组扩展 - 扩展运算符 (Spread Operator)

扩展运算符 (`...`) 可以将一个数组（或类数组对象、可迭代对象）**展开成多个元素**。

```javascript
// 数组合并
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const arr3 = [...arr1, ...arr2]; // [1, 2, 3, 4, 5, 6]

// 数组复制 (浅拷贝)
const original = [1, 2, 3];
const copy = [...original];

// 函数调用时传递参数
function sum(x, y, z) {
  return x + y + z;
}
const numbers = [1, 2, 3];
console.log(sum(...numbers)); // 6

// 将类数组对象转换为数组
const nodeList = document.querySelectorAll('div');
const divArray = [...nodeList]; // nodeList 现在是一个真正的数组
```

---

#### 数组新增方法 (New Array Methods)

*   **`Array.from(arrayLike, mapFn?, thisArg?)`**:  **将类数组对象或可迭代对象转换为真正的数组**。  `mapFn` 可选，用于对每个元素进行处理。`thisArg` 可选，用于设置 `mapFn` 的 `this` 值。

    ```javascript
    const arrayLike = { 0: 'a', 1: 'b', length: 2 };
    const arr = Array.from(arrayLike); // ['a', 'b']
    const arr2 = Array.from(arrayLike, x=> x + x); //['aa', 'bb']
    ```

*   **`Array.of(...items)`**:  **创建一个包含任意数量参数的新数组**，类似于数组字面量，但没有 `[]` 在只有一个数字参数时的特殊行为。

    ```javascript
    const arr1 = Array.of(1, 2, 3); // [1, 2, 3]
    const arr2 = Array.of(7);     // [7]   (对比: new Array(7) 创建长度为 7 的空数组)
    ```

*   **`find(callback, thisArg?)`**: 找出第一个满足测试函数的元素，并返回该元素的值，如果没有找到则返回 `undefined`。

    ```javascript
    const array1 = [5, 12, 8, 130, 44];
    const found = array1.find(element => element > 10);
    console.log(found);// Expected output: 12
    ```

*   **`findIndex(callback, thisArg?)`**: 找出第一个满足测试函数的元素的索引，如果没有找到则返回 -1。

    ```javascript
      const array1 = [5, 12, 8, 130, 44];
      const isLargeNumber = (element) => element > 13;
      console.log(array1.findIndex(isLargeNumber));// Expected output: 3
    ```

*   **`fill(value, start?, end?)`**: 使用指定的值填充数组。`start` 可选，表示填充的起始位置（包含）。`end` 可选，表示填充的结束位置（不包含）。

    ```javascript
     const array1 = [1, 2, 3, 4];
     console.log(array1.fill(0, 2, 4));// fill with 0 from position 2 until position 4
    // Expected output: Array [1, 2, 0, 0]
    ```

*   **`copyWithin(target, start?, end?)`**:  浅复制数组的一部分到同一数组的另一个位置，并返回修改后的数组（不改变原数组长度）。`target` 表示要复制到的目标位置。 `start` 可选。`end` 可选.

    ```javascript
    const array1 = [1, 2, 3, 4, 5];
    console.log(array1.copyWithin(0, 3, 4));// copy to index 0 the element at index 3
    // Expected output: Array [4, 2, 3, 4, 5]
    ```

*   **`entries()`**:  返回一个包含数组中每个索引的键/值对的 `Array Iterator` 对象。

    ```javascript
       const array1 = ['a', 'b', 'c'];
       const iterator1 = array1.entries();
       console.log(iterator1.next().value);// Expected output: Array [0, "a"]
    ```

*   **`keys()`**: 返回一个包含数组中每个索引的键的 `Array Iterator` 对象。

    ```javascript
      const array1 = ['a', 'b', 'c'];
      const iterator1 = array1.keys();

      for (const key of iterator1) {
        console.log(key);
      }

      // Expected output: 0
      // Expected output: 1
      // Expected output: 2
    ```

*   **`values()`**:  返回一个包含数组中每个索引的值的 `Array Iterator` 对象。 (注意，某些旧浏览器可能不支持)

    ```javascript
       const array1 = ['a', 'b', 'c'];
       const iterator1 = array1.values();
    
        for (const value of iterator1) {
          console.log(value);
        }
    
        // Expected output: "a"
        // Expected output: "b"
        // Expected output: "c"
    ```
---

#### 对象的扩展 (Object Enhancements)

*   **属性简写 (Property Shorthand)**:  如果属性名和变量名相同，可以省略属性名。

    ```javascript
    const name = "Alice";
    const age = 30;

    // 传统方式
    const person1 = {
      name: name,
      age: age
    };

    // 属性简写
    const person = { name, age };  // 等同于 { name: name, age: age }
    ```

* **方法简写 (Method Shorthand)**:  在对象字面量中定义方法时，可以省略 `function` 关键字和冒号。

  ```javascript
    // 传统方式
  const obj1 = {
    greet: function() {
      console.log("Hello");
    }
  };
  
  // 方法简写
  const obj = {
    greet() {
      console.log("Hello");
    }
  };
  
  
  function loc(){
       let x = 1.21
       let y = 2.96
        return {x, y}
  }
  console.log(loc().x)
  ```

*   **计算属性名 (Computed Property Names)**: 允许在对象字面量中使用方括号 `[]` 来动态计算属性名。

    ```javascript
    const key = 'name';
    const obj = {
      [key]: 'Alice', // 属性名是变量 key 的值
      ['age' + 10]: 40  //属性名是表达式的结果
    };
    console.log(obj.name); // "Alice
    ```
* **`Object.is(value1, value2)`**: 判断两个值是否严格相等, 类似于 `===` 运算符，但修复了  `NaN === NaN` 为 `false`, 以及 `+0 === -0` 为 `true`的情况。
*  **`Object.assign()`**: 前面讲过了。
* **`__proto__`**:  可以直接在对象字面中设置 `__proto__` 属性。
```javascript
    const obj2 = {
        __proto__: myPrototype, //不推荐。 推荐Object.create()
        //...
    }
```
---

#### 函数扩展 - 箭头函数 (Arrow Functions)

箭头函数是一种更简洁的函数表达式语法。

```javascript
// 传统函数表达式
const add1 = function(x, y) {
  return x + y;
};

// 箭头函数
const add = (x, y) => x + y; // 单行表达式，隐式返回

// 如果函数体有多条语句，需要使用花括号，并显式返回
const greet = (name) => {
  console.log(`Hello, ${name}!`);
  return `Hi, ${name}`; //需要显示的 return, 因为使用了花括号
};

// 如果只有一个参数，可以省略参数的括号
const square = x => x * x;

// 如果没有参数，必须使用空括号
const sayHello = () => console.log("Hello");
```

**箭头函数的特点:**

*   更简洁的语法。
*   没有自己的 `this`、`arguments`、`super` 或 `new.target`。**箭头函数内部的 `this` 值继承自外层作用域。**
*   不能用作构造函数 (不能使用 `new` 关键字)。
*   没有 `prototype` 属性。

###### 最大用途：简化回调函数（匿名函数）

```js

```

---

#### Set 对象笔记

1.  **定义：**

    *   `Set` 是 ECMAScript 6 (ES6) 引入的一种新的数据结构。
    *   它类似于数组，但有一个关键区别：`Set` 中的 *成员值都是唯一的*，没有重复的值。
    *   `Set` 对象允许你存储任何类型的唯一值，无论是原始值（如字符串、数字、布尔值）还是对象引用。

2. **创建 Set：**

   ```javascript
   const mySet = new Set(); // 创建一个空的 Set
   
   // 使用可迭代对象初始化 Set
   const mySet2 = new Set([1, 2, 3, 2, 1]); // mySet2 包含 {1, 2, 3}
   const mySet3 = new Set("hello");        
   // 字符串是可迭代的，mySet3 包含 {'h', 'e', 'l', 'o'}
   ```

3.  **基本方法：**

    *   **`add(value)`:** 向 `Set` 中添加一个值。如果该值已存在，则不进行任何操作。返回 `Set` 对象本身（因此可以链式调用）。
    *   **`delete(value)`:** 从 `Set` 中删除指定的值。如果删除成功（即，`Set` 中存在该值），返回 `true`；否则返回 `false`。
    *   **`has(value)`:** 检查 `Set` 中是否包含指定的值。如果存在，返回 `true`；否则返回 `false`。
    *   **`clear()`:** 清空 `Set` 中的所有值。
    *   **`size`:**  （属性）返回 `Set` 中值的数量。

    ```javascript
    const mySet = new Set();
    mySet.add(1);
    mySet.add(2).add(3); // 链式调用
    console.log(mySet.size); // 输出 3
    console.log(mySet.has(2)); // 输出 true
    mySet.delete(2);
    console.log(mySet.has(2)); // 输出 false
    mySet.clear();
    console.log(mySet.size); // 输出 0
    ```

4.  **遍历 Set：**

   `Set` 对象是可迭代的，可以使用多种方式遍历：
    *   **`for...of` 循环：**  （最常用）

        ```javascript
        const mySet = new Set([1, 2, 3]);
        for (const value of mySet) {
          console.log(value);
        }
        // 输出：
        // 1
        // 2
        // 3
        ```

    *   **`forEach()` 方法：**

        ```javascript
        const mySet = new Set([1, 2, 3]);
        mySet.forEach(value => {
          console.log(value);
        });
        // 输出：
        // 1
        // 2
        // 3
        ```

    *   **`keys()`、`values()`、`entries()` 方法：**
        *   `keys()` 和 `values()`：都返回一个 *迭代器*（Iterator），包含 `Set` 中的值（因为 `Set` 中键和值相同）。
        *    `entries()`: 返回一个 *迭代器*，包含 `Set` 中的键值对 `[value, value]`（同样，键和值相同）。
         ```javascript
            const mySet = new Set(['a', 'b', 'c']);
            console.log(mySet.keys()) 
            //SetIterator {'a', 'b', 'c'}
            console.log(mySet.values())
            //SetIterator {'a', 'b', 'c'}
            console.log(mySet.entries())
            //SetIterator {'a' => 'a', 'b' => 'b', 'c' => 'c'}
         ```

5.  **Set 与数组的转换：**

    *   **数组转 Set：** 使用 `new Set(array)`
    *   **Set 转数组：** 使用扩展运算符 (`...`) 或 `Array.from()`

    ```javascript
    const myArray = [1, 2, 2, 3, 4, 4, 5];

    // 数组转 Set (去重)
    const mySet = new Set(myArray); // mySet 包含 {1, 2, 3, 4, 5}

    // Set 转数组
    const uniqueArray = [...mySet]; // uniqueArray 为 [1, 2, 3, 4, 5]
    const uniqueArray2 = Array.from(mySet); // 另一种方式
    ```

6.  **Set 的应用场景：**
    *   **数组去重：**  这是 `Set` 最常见的用途。
    *   **存储唯一值：**  确保集合中不会有重复的元素（例如，用户 ID 的集合）。
    *   **快速查找：**  `has()` 方法通常比数组的 `includes()` 方法更快（特别是当集合很大时）。
    *   **集合运算：**  虽然原生 `Set` 没有直接提供并集、交集、差集等运算，但你可以使用循环和 `Set` 的方法来实现这些运算。

7. **集合运算**
   * **并集**
   ```javascript
    let a = new Set([1, 2, 3]);
    let b = new Set([4, 3, 2]);
    let union = new Set([...a, ...b]);
    // {1, 2, 3, 4}
   ```
   * **交集**
   ```javascript
   let a = new Set([1, 2, 3]);
   let b = new Set([4, 3, 2]);
   let intersect = new Set([...a].filter(x => b.has(x)));
   ```
   * **差集**
  ```javascript
  let a = new Set([1, 2, 3]);
  let b = new Set([4, 3, 2]);
  let difference = new Set([...a].filter(x => !b.has(x)));
  // {1}
  ```

8.  **WeakSet (补充)**

    还有一个和`Set`非常相关的名叫`WeakSet`的类型.
    它和`Set`有以下区别:
     * `WeakSet` 的成员只能是 *对象*，而不能是其他类型的值。
     * `WeakSet` 中的对象都是 *弱引用*（weak reference）。这意味着，如果没有其他地方引用 `WeakSet` 中的对象，垃圾回收机制可能会自动回收这些对象，即使它们还在 `WeakSet` 中。
     * 由于是弱引用，`WeakSet` *不可迭代*（没有 `keys()`、`values()`、`entries()`、`forEach()` 方法），也 *没有 `size` 属性*。你只能用 `add()`、`delete()` 和 `has()`。

    ```javascript
    const ws = new WeakSet();
    const obj1 = {};
    const obj2 = {};
    
    ws.add(obj1);
    ws.add(obj2);
    
    console.log(ws.has(obj1)); // 输出 true
    
    // obj1 不再被其他地方引用
    // 垃圾回收可能会在某个时刻自动回收 obj1，即使它还在 ws 中
    ```
    `WeakSet` 主要用于存储 *不希望影响垃圾回收* 的对象引用。

**总结**

`Set` 是一种非常有用的数据结构，用于存储唯一值。它提供了快速的查找和去重功能,以及一系列方便的方法。理解 `Set` 的特性以及与数组的转换，可以帮助你更有效地处理数据。`WeakSet` 则提供了更特殊的弱引用集合。

---

#### Promise 对象笔记

1.  **什么是 Promise？**

    *   `Promise` 是 JavaScript 中用于处理 *异步操作* 的一种机制。
    *   它代表一个 *最终可能完成（或失败）* 的异步操作，并返回一个结果值（或失败原因）。
    *   `Promise` 可以避免传统的回调函数（callback）方式导致的“回调地狱”（callback hell）问题，使异步代码更易于阅读、理解和维护。

2.  **Promise 的三种状态：**

    一个 `Promise` 对象必然处于以下三种状态之一：

    *   **Pending（进行中）：** 初始状态，表示异步操作尚未完成（既没有成功，也没有失败）。
    *   **Fulfilled（已成功）：** 异步操作成功完成，并且 `Promise` 携带了一个值（value）。
    *   **Rejected（已失败）：** 异步操作失败，`Promise` 携带了一个失败原因（reason，通常是一个错误对象）。

    **状态转换：**

    *   `Promise` 的状态只能从 *Pending* 转换到 *Fulfilled*，或者从 *Pending* 转换到 *Rejected*。
    *   一旦 `Promise` 的状态变为 *Fulfilled* 或 *Rejected*，就 *不能再改变* 了。

3.  **创建 Promise：**

    ```javascript
    const myPromise = new Promise((resolve, reject) => {
      // 执行异步操作 (例如：setTimeout, fetch, XMLHttpRequest, 读取文件等)

      // 异步操作成功:
      if (/* 操作成功 */) {
        resolve(resultValue); // 将 Promise 的状态变为 Fulfilled，并传递结果值
      } else {
        // 异步操作失败:
        reject(errorReason); // 将 Promise 的状态变为 Rejected，并传递失败原因
      }
    });
    ```

    *   `new Promise(...)`：创建一个新的 `Promise` 对象。
    *   `executor` 函数：`new Promise()` 接收一个 *executor* 函数作为参数。这个函数会被 *立即* 执行。
    *   `resolve` 和 `reject`：`executor` 函数接收两个参数，`resolve` 和 `reject`，它们都是函数。
        *   `resolve(value)`：用于将 `Promise` 的状态从 *Pending* 变为 *Fulfilled*，并传递一个 *值*（value）。
        *   `reject(reason)`：用于将 `Promise` 的状态从 *Pending* 变为 *Rejected*，并传递一个 *失败原因*（reason），通常是一个 `Error` 对象。

4.  **`then()` 方法：**

    `then()` 方法用于处理 `Promise` 的结果（成功或失败）。

    ```javascript
    myPromise.then(
      (value) => {
        // 当 Promise 状态变为 Fulfilled 时执行 (成功回调)
        console.log("成功:", value);
      },
      (reason) => {
        // 当 Promise 状态变为 Rejected 时执行 (失败回调)
        console.error("失败:", reason);
      }
    );
    ```

    *   **`then()` 方法接收 *两个* 参数：**
        *   **第一个参数（可选）：`onFulfilled` 函数，当 `Promise` 变为 *Fulfilled* 时调用，并接收 `Promise` 的 *值* 作为参数。**
        *   **第二个参数（可选）：`onRejected` 函数，当 `Promise` 变为 *Rejected* 时调用，并接收 `Promise` 的 *失败原因* 作为参数。**

    *   `then()` 方法 *返回一个新的 Promise*。这使得 `Promise` 可以链式调用。

5.  **链式调用：**

    ```javascript
    fetch("https://api.example.com/data") // fetch 返回一个 Promise
      .then(response => {
        // 处理 HTTP 响应
        if (!response.ok) {
          throw new Error("网络请求失败"); // 抛出错误，会进入下一个 .catch()
        }
        return response.json(); // 解析 JSON，返回一个新的 Promise
      })
      .then(data => {
        // 处理 JSON 数据
        console.log("数据:", data);
      })
      .catch(error => {
        // 处理错误 (前面任何一个 .then() 中抛出的错误，都会在这里被捕获)
        console.error("错误:", error);
      });
    ```

    *   每个 `.then()` 返回一个新的 `Promise`，可以继续链式调用。
    *   如果 `then()` 的 `onFulfilled` 或 `onRejected` 函数 *返回一个值*，这个值会成为下一个 `then()` 的 `onFulfilled` 的参数。
    *   如果 `then()` 的 `onFulfilled` 或 `onRejected` 函数 *抛出一个错误*，或者 *返回一个 rejected 的 Promise*，这个错误会成为下一个 `.catch()` 的参数。
    *   如果 `then()` 的 `onFulfilled` 或 `onRejected` 函数中 *return 了一个pending状态的Promise*, 那么下一个`then`会等待这个Promise的状态改变。

6.  **`catch()` 方法：**

    `catch()` 方法是 `.then(null, onRejected)` 的简写，专门用于处理 `Promise` 的 *Rejected* 状态。

    ```javascript
    myPromise.catch(error => {
      console.error("捕获到错误:", error);
    });
    ```

7.  **`finally()` 方法：**

    `finally()` 方法无论 `Promise` 的状态是 *Fulfilled* 还是 *Rejected*，都会执行。它通常用于进行一些清理工作，例如关闭文件、释放资源等。

    ```javascript
    myPromise
      .then(value => { /* ... */ })
      .catch(error => { /* ... */ })
      .finally(() => {
        // 无论成功还是失败，都会执行
        console.log("Promise 操作完成");
      });
    ```

    *   `finally()` 不接收任何参数，因为它不关心 `Promise` 的结果或失败原因。
    *   `finally()` *返回一个 Promise*，通常情况下它会“传递”上一个 `Promise` 的结果或失败原因，不会改变链式调用的流程。

8.  **`Promise` 的静态方法：**

    *   **`Promise.resolve(value)`:**

        *   创建一个 *立即* 变为 *Fulfilled* 状态的 `Promise`，并携带指定的值。
        *   如果 `value` 本身就是一个 `Promise`，`Promise.resolve()` 会直接返回这个 `Promise`。
        *   如果 `value` 是一个 *thenable* 对象（即，有一个 `then` 方法的对象），`Promise.resolve()` 会将这个对象转换成 `Promise`。

        ```javascript
        const promise1 = Promise.resolve(123);
        promise1.then(value => {
          console.log(value); // 输出 123
        });
        ```

    *   **`Promise.reject(reason)`:**

        *   创建一个 *立即* 变为 *Rejected* 状态的 `Promise`，并携带指定的失败原因。

        ```javascript
        const promise2 = Promise.reject(new Error("出错了"));
        promise2.catch(error => {
          console.error(error.message); // 输出 "出错了"
        });
        ```

    *   **`Promise.all(iterable)`:**

        *   接收一个 *可迭代对象*（如数组）作为参数，其中包含多个 `Promise`。
        *   返回一个新的 `Promise`，这个 `Promise` 在 *所有* 传入的 `Promise` 都变为 *Fulfilled* 时才变为 *Fulfilled*，并且返回一个包含所有 `Promise` 结果的数组（按传入的顺序）。
        *   如果 *任何一个* 传入的 `Promise` 变为 *Rejected*，则返回的 `Promise` 立即变为 *Rejected*，并携带第一个 rejected 的 `Promise` 的失败原因。

        ```javascript
        const promise1 = Promise.resolve(1);
        const promise2 = Promise.resolve(2);
        const promise3 = Promise.resolve(3);

        Promise.all([promise1, promise2, promise3])
          .then(values => {
            console.log(values); // 输出 [1, 2, 3]
          })
          .catch(error => {
            // 如果有任何一个 Promise rejected，都不会执行到这里
          });
        ```

    *   **`Promise.race(iterable)`:**

        *   接收一个包含多个 `Promise` 的可迭代对象。
        *   返回一个新的 `Promise`，这个 `Promise` 的状态和值/原因与 *第一个* 完成（Fulfilled 或 Rejected）的 `Promise` 相同。

        ```javascript
        const promise1 = new Promise(resolve => setTimeout(resolve, 500, 'one'));
        const promise2 = new Promise(resolve => setTimeout(resolve, 100, 'two'));

        Promise.race([promise1, promise2])
          .then(value => {
            console.log(value); // 输出 "two" (因为 promise2 更快)
          });
        ```

    *   **`Promise.allSettled(iterable)`:** (ES2020 新增）

        *   接收一个包含多个 `Promise` 的可迭代对象。
        *   返回一个新的 `Promise`，这个 `Promise` 在 *所有* 传入的 `Promise` 都 *settled*（即，要么 Fulfilled，要么 Rejected）后才变为 Fulfilled。
        *   返回的 `Promise` 的值是一个数组，数组的每个元素都是一个对象，表示对应 `Promise` 的结果：
            *   `{ status: 'fulfilled', value: ... }`：如果对应的 `Promise` 是 fulfilled。
            *   `{ status: 'rejected', reason: ... }`：如果对应的 `Promise` 是 rejected。

        ```javascript
        const promise1 = Promise.resolve(3);
        const promise2 = new Promise((resolve, reject) => setTimeout(reject, 100, 'foo'));
        const promises = [promise1, promise2];
        
        Promise.allSettled(promises).
        then((results) => results.forEach((result) => console.log(result)));
        
        // Expected output:
        // "fulfilled" , value:3
        //       // "rejected", reason:"foo"
        ```

         *   **`Promise.any(iterable)`:** (ES2021 新增）

           *   接收一个包含多个 `Promise` 的可迭代对象。
           *   只要有一个Promise变成fulfilled, 就返回那个fulfilled的Promise
           *   如果所有的Promise都rejected, 那么返回一个rejected的Promise, 并且reason是一个AggregateError对象.(AggregateError 是一种特殊的 Error 对象，它包含了多个错误信息。)

9.  **错误处理：**

    *   使用 `.catch()` 捕获链式调用中的错误。
    *   在 `then()` 的第二个参数（`onRejected`）中处理错误。
    *   确保在 `Promise` 链的 *末尾* 有一个 `.catch()`，以捕获任何未处理的错误。
    *   在 `async/await` 中，使用 `try...catch` 捕获错误。

10. **`async/await`**

    `async/await` 是 ES2017 引入的，是基于 `Promise` 的 *语法糖*，**使异步代码更像同步代码**。它提供了更清晰、更简洁的方式来处理 Promise。

    ```javascript
    function timeout(ms) {
    //resolve 是一个函数
      return new Promise((resolve) => {
        setTimeout(resolve, ms);
      });
    }
    
    async function asyncPrint(ms, value) {
    // 把具有异步操作的代码前面放入： await
      await timeout(ms);
      console.log(value);
    }
    
    asyncPrint(100, 'hello');
    ```

    *   **`async` 关键字：**
        *   `async` 用于声明一个异步函数。
        *   异步函数 *隐式地* 返回一个 `Promise`。即使你在 `async` 函数中没有显式地 `return` 一个值，它也会自动返回一个 resolved 的 `Promise`（值为 `undefined`）。如果 `return` 了一个值，则返回一个 resolved 的 `Promise`，携带这个值。如果 `async` 函数内部抛出异常，则返回一个 rejected 的 `Promise`。

    *   **`await` 关键字：**
        *   `await` 只能在 `async` 函数内部使用。
        *   `await` 后面通常跟着一个 `Promise` 对象（但也可以是任何值，如果不是 `Promise`，会自动转换为 resolved 的 `Promise`）。
        *   `await` 会 *暂停* 异步函数的执行，*等待* 后面的 `Promise` 对象的状态变为 settled（fulfilled 或 rejected）。
        *   如果 `await` 后面的 `Promise` 变为 *fulfilled*，`await` 表达式会返回 `Promise` 的 *值*。
        *     如果 `await` 后面的 `Promise` 变为 *rejected*，`await` 表达式会 *抛出* `Promise` 的 *失败原因*（通常需要用 `try...catch` 捕获）。

    **`async/await` 的错误处理 (使用 `try...catch`)**

    ```js
    async function fetchData() {
      try {
        const response = await fetch('https://api.example.com/data');
        if (!response.ok) {
          throw new Error('Network response was not ok');
        }
        const data = await response.json();
        return data;
      } catch (error) {
        console.error('There has been a problem with your fetch operation:', error);
        // 可以选择在这里 return 一个默认值，或者 re-throw 错误
         throw error; //如果不进行throw error, 那么会返回一个 resolved 状态的Promise, 值为undefined.
      }
    }
    
    fetchData().then(data => {
      console.log(data)
    }).catch(error => {
      // 也可以选择在这里处理错误
    })
    ```

    *   将可能出错的 `await` 表达式放在 `try` 块中。
    *   在 `catch` 块中捕获错误。
    *   可以在 `catch` 块中处理错误，或者重新抛出错误（`throw error`），以便在外层继续处理。

    **`async/await` 与 传统 Promise 链的对比:**

    ```javascript
     // 使用 Promise 链
    function getData() {
        return fetch('https://api.example.com/data')
        .then(response => {
            if (!response.ok) {
            throw new Error('Network response was not ok.');
            }
            return response.json();
        })
        .then(data => {
            return data;
        })
        .catch(error => {
            console.error('Error:', error);
        });
    }
    
    // 使用 async/await
    async function getData() {
        try {
            const response = await fetch('https://api.example.com/data');
            if (!response.ok) {
                throw new Error('Network response was not ok.');
            }
            const data = await response.json();
                return data;
         } catch (error) {
             console.error('Error:', error);
         }
    }
    ```

    `async/await` 版本的代码更像同步代码，更易于阅读和理解。

11. **Ajax**

    *   **Ajax (Asynchronous JavaScript and XML)** 是一种用于创建 *异步* Web 应用的技术。
    *   Ajax 允许网页在 *不刷新整个页面* 的情况下，与服务器进行 *部分* 数据交换。
    *   核心是 `XMLHttpRequest` 对象（现代浏览器中更多使用 `fetch` API，`fetch` API 基于 Promise）。

    **使用 `XMLHttpRequest` 发送 Ajax 请求 (传统方式，了解即可):**

    ```javascript
    function getSomeThing(url, resolve, reject){
      const xhr = new XMLHttpRequest();
    
      xhr.open('GET', url); // 配置请求 (方法, URL)
    
      xhr.onload = () => { // 请求完成（但不一定是成功）
        if (xhr.status >= 200 && xhr.status < 300) {
          resolve(xhr.response); // 成功，解析响应数据
        } else {
          reject(new Error(xhr.statusText)); // 失败，创建错误对象
        }
      };
      xhr.onerror = () => {
        reject(new Error('Network Error'))
      }
    
      xhr.send(); // 发送请求
    }
    
     const myPromise = new Promise((resolve, reject) => {
        getSomeThing("https://api.example.com/data", resolve, reject)
     });
    ```
    
    *   `new XMLHttpRequest()`: 创建 `XMLHttpRequest` 对象。
    *   `xhr.open(method, url, async?)`:  配置请求。
        *   `method`: HTTP 请求方法 (GET, POST, PUT, DELETE 等)。
        *   `url`: 请求的 URL。
        *   `async`: 是否异步 (默认为 `true`，即异步)。
    *   `xhr.onload`:  *事件处理程序*，当请求 *完成* 时触发（无论成功或失败）。
    *   `xhr.status`:  HTTP 状态码 (200 表示成功, 404 表示未找到等)。
    *   `xhr.response`:  服务器返回的响应数据。
    *   `xhr.onerror`: *事件处理程序*，当发生 *网络错误* 时触发
    *   `xhr.send(data?)`:  发送请求。`data` 可选，用于 POST 请求发送数据。
    *   `xhr.setRequestHeader()`：设置 HTTP 请求头。
    
    **使用 `fetch` API 发送 Ajax 请求 (现代方式，推荐):**
    
    ```js
       fetch('https://api.example.com/data')
         .then(response => {
           if (!response.ok) {
             throw new Error('Network response was not ok');
           }
           return response.json(); // 将响应解析为 JSON
         })
         .then(data => {
           console.log(data); // 处理数据
         })
         .catch(error => {
           console.error('There has been a problem with your fetch operation:', error);
         });
    ```

*   `fetch(url, options?)`:  发起网络请求。js
    *   `url`: 请求的 URL。
    *   `options`: 可选，配置对象，可以设置请求方法、请求头、请求体等。
*   `fetch` 返回一个 `Promise`，可以使用 `.then()` 和 `.catch()` 处理结果。
*   `response.ok`:  属性，表示请求是否成功 (状态码在 200-299 范围内)。
*   `response.json()`:  方法，将响应体解析为 JSON (返回一个 Promise)。
*   `response.text()`: 方法，将响应体解析为文本 (返回一个 Promise)。
*   `response.blob()`: 方法，将响应体解析为 Blob 对象 (返回一个 Promise)。
*    `response.formData()`: 方法，将响应体解析为 FormData 对象 (返回一个 Promise).

**总结：**

`Promise` 是 JavaScript 异步编程的核心。`async/await` 让 `Promise` 的使用更加简洁。Ajax 技术（无论是传统的 `XMLHttpRequest` 还是现代的 `fetch` API）都依赖于异步操作，而 `Promise` 是处理这些异步操作的关键。

---

#### Class (类)

`class` 关键字是 ES6 引入的，提供了一种更清晰、更面向对象的语法来创建对象和处理继承。虽然 JavaScript 的 `class` 实际上是基于原型（prototype）的“语法糖”，但它使代码更易于组织和理解，尤其对于熟悉面向对象编程（OOP）概念的开发者来说。

##### 类的定义

使用 `class` 关键字定义一个类：

```javascript
class Person {
  // 构造函数 (constructor)
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  // 方法 (method)
  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}
```

*   **`class` 关键字:**  用于声明一个类。
*   **`constructor` 方法:**  一个特殊的 *构造函数* 方法，用于创建和初始化类的实例。当使用 `new` 关键字创建类的实例时，`constructor` 方法会被自动调用。
*   **实例属性:**  在 `constructor` 中，使用 `this` 关键字给实例添加属性。
*   **方法 (method):**  定义在类中的函数，可以访问实例属性 (通过 `this`)。

---

##### 创建类的实例

使用 `new` 关键字创建类的实例：

```javascript
const person1 = new Person('Alice', 30);
const person2 = new Person('Bob', 25);

person1.greet(); // "Hello, my name is Alice and I am 30 years old."
person2.greet(); // "Hello, my name is Bob and I am 25 years old."
```

*   `new` 关键字:  创建类的新实例。
*   调用 `constructor` 方法:  `new` 关键字会自动调用类的 `constructor` 方法，并将传入的参数传递给 `constructor`。
*   `this`: 在 `constructor` 和方法中，`this` 关键字引用当前创建的实例。

---

##### 静态方法 (Static Methods)

**静态方法是属于类本身的方法，而不是类的实例的方法。**使用 `static` 关键字定义静态方法。静态方法通常用于工具函数或与特定实例无关的功能。**静态方法和静态属性通过类名调用。**

```javascript
class MathHelper {
  static square(x) {
    return x * x;
  }
  static PI = 3.14159; //静态属性
}

console.log(MathHelper.square(5)); // 25  (直接通过类名调用)
//不能通过实例调用静态方法
// const helper = new MathHelper
// console.log(helper.square(5)) //错误
console.log(MathHelper.PI)
```

*   `static` 关键字:  声明一个静态方法或静态属性。
*   通过类名调用:  静态方法和静态属性直接通过类名调用（`ClassName.staticMethod()`），而不是通过类的实例调用。
*   静态方法的 this 指向类，而不是类的对象

---

##### 继承 (Inheritance)

使用 `extends` 关键字实现类的继承。子类（subclass）可以继承父类（superclass）的属性和方法，并可以添加自己的属性和方法，或覆盖父类的方法。

```javascript
// 父类 (基类)
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a sound.`);
  }
}

// 子类 (派生类)
class Dog extends Animal {
  constructor(name, breed) {
    super(name); // 调用父类的 constructor
    this.breed = breed;
  }

  speak() { // 方法覆盖 (override)
    console.log(`${this.name} barks.`);
  }

  fetch() {
    console.log(`${this.name} fetches a ball.`);
  }
}

const myDog = new Dog('Buddy', 'Golden Retriever');
myDog.speak(); // "Buddy barks."  (调用子类的方法)
myDog.fetch(); // "Buddy fetches a ball."
```

*   **`extends` 关键字:**  指定子类继承的父类。
*   **`super` 关键字:**
    *   在 `constructor` 中：`super(...)` 用于 *调用父类的 constructor*。必须在使用 `this` 之前调用 `super()`。
    *   在方法中：`super.methodName(...)` 用于 *调用父类的方法*。

---

##### Getter 和 Setter

可以使用 `get` 和 `set` 关键字定义属性的 getter 和 setter。Getter 和 setter 允许你以属性访问的方式执行函数。

```javascript
  class Circle{
    constructor(radius){
      this.radius = radius;
    }
    get diameter(){
      return this.radius * 2
    }
    set diameter(value){
      this.radius = value /2 ;
    }
  }

  const circle1 = new Circle(5)
  console.log(circle1.diameter)
  circle1.diameter = 20;
  console.log(circle1.radius)
```

---

##### 注意事项
*   类声明不会被提升 (hoisting)。
*   类内部默认是严格模式 ('use strict')。
*   在 `constructor` 中给实例设置属性时，如果未使用 `this.` 前缀，则会设置到类的原型上。

---

好的，下面是关于 JavaScript Modules (模块) 的笔记：

#### JavaScript Modules (模块)

JavaScript 模块是一种将代码组织成独立、可重用单元的方式。模块化有助于：

*   **代码组织:** 将大型项目分解成更小、更易于管理的部分。
*   **避免命名冲突:** 每个模块都有自己的作用域，避免了变量和函数的命名冲突。
*   **代码重用:** 可以在多个地方导入和使用同一个模块。
*   **依赖管理:** 清晰地定义模块之间的依赖关系。

---

##### 模块的基本概念

*   **模块 (Module):** 一个包含 JavaScript 代码的文件。
*   **导出 (Export):** 模块可以将自己的变量、函数、类等 *导出*，以便其他模块使用。
*   **导入 (Import):** 模块可以 *导入* 其他模块导出的内容。
*  一个文件就是一个模块, 模块内的变量是私有的.

---

##### ES6 模块 (ESM)

ES6 (ECMAScript 2015) 引入了原生的模块系统，现在是 JavaScript 中推荐的模块化方式.

需要设置`<script type="module" src = "main.js"></script>`

**导出 (export)**

*   **命名导出 (Named Exports):** 导出多个具名的变量、函数或类。

    ```javascript
    // module.js
    export const name = "Alice";
    export function greet(name) {
      console.log(`Hello, ${name}!`);
    }
    export class Person {
      // ...
    }
    // 也可以：
    const age = 30;
    export {age};
    // 导出时，可以对变量进行重命名
    export {age as myAge};
    ```

*   **默认导出 (Default Export):** 每个模块可以有一个默认导出 (通常是一个主要的类或函数)。

    ```javascript
    // myModule.js
    export default function sayHello() {
      console.log("Hello!");
    }
    
    // 或者，先定义，再导出：
    class MyClass{
        //...
    }
    export default MyClass;
    ```

**导入 (import)**

*   **导入命名导出:**

    ```javascript
    // main.js
    import { name, greet, Person, age, myAge} from './module.js';
    // 使用 * as moduleName 来导入所有
    import * as myModule from './module.js'
    ```

*   **导入默认导出:**

    ```javascript
    // main.js
    import sayHello from './myModule.js';
    // 导入默认导出时，可以自己指定名称，不需要和导出时的名称相同
    // 可以同时导入命名导出和默认导出, 默认导出必须放在前面
    import myDefault, {name, age} from './module.js';

    ```

* **注意事项：**

  * 导入语句中的路径是相对于当前模块文件的路径。
  * `.js` 扩展名通常可以省略（但不总是，取决于环境）。
  * 导入是“只读”的，不能修改导入的变量的值（但如果导入的是对象，可以修改对象的属性）。

**导入和导出重命名**

*   可以在导入或导出时使用 `as` 关键字重命名：

    ```javascript
    // 导出时重命名
    export { myFunction as myFunc };
    
    // 导入时重命名
    import { myFunc as anotherFunc } from './module.js';
    ```

**`import()` 动态导入（按需加载）**

  * `import()` 函数可以在运行时动态加载模块, 返回一个Promise

```javascript
  btnElt.onclick = function(){
      import('./hello.js').then( module => {
          module.hello();
      })
  }
```

##### 模块的特点和注意事项:

*   **模块代码只在第一次导入时执行。**
*   **模块是单例的。**  多次导入同一个模块，实际上得到的是同一个模块实例。
*   **模块内的顶层 `this` 是 `undefined`，而不是全局对象。**
*   **模块有自己的作用域，不会污染全局作用域。**
*   **`import` 和 `export` 必须位于模块的顶层，不能在块级作用域（如 `if` 语句、函数内部）中使用。**

#####  浏览器环境

*   要在浏览器中使用 ES6 模块，需要在 `<script>` 标签中添加 `type="module"` 属性：

    ```html
    <script type="module" src="main.js"></script>
    ```

* 对于没有type="module"的script, 即使是inline script, 其中的代码也会被当做传统脚本来执行

##### CommonJS (了解)

CommonJS 是 Node.js 中使用的模块化规范（在浏览器中通常不直接使用）。

*   **导出:** `module.exports = ...` 或 `exports.myVar = ...`
*   **导入:** `const myModule = require('./myModule.js')`

CommonJS 使用 `require()` 函数同步加载模块，而 ES6 模块的加载可以是异步的。
在 Node.js 的较新版本中，也可以使用 ES6 模块（通过 `.mjs` 文件扩展名或在 `package.json` 中设置 `"type": "module"`）。

##### 模块打包工具 (Webpack, Rollup, Parcel 等)

在实际开发中，通常会使用模块打包工具：

*   **将多个模块打包成一个或几个文件**，减少 HTTP 请求。
*   **处理模块之间的依赖关系**。
*   **转换代码** (例如，将 ES6+ 代码转换成 ES5，以便兼容旧的浏览器)。
*   **处理非 JavaScript 资源** (例如，CSS, 图片)。

---

### 进阶

#### 预编译 (Pre-compilation / Hoisting)

**1. 什么是预编译？**

   JavaScript 在真正执行代码之前，会有一个预编译阶段。在这个阶段，JavaScript 引擎会：

   *   **找出所有的变量声明（`var`、`let`、`const`）和函数声明（`function`）。**
   *   **将这些声明 "提升" 到它们所在作用域的顶部。**

   **重要：**
   *   只有声明被提升，**赋值或其他逻辑不会被提升**。
   *    `let` 和 `const` 也有提升，但存在“暂时性死区”（Temporal Dead Zone, TDZ），在 TDZ 中访问这些变量会报错。

**2. 预编译的 "四步骤" (经典总结)**

   这四个步骤主要针对 *函数* 的预编译过程，更准确地描述了函数声明和函数内部变量的提升：

   **全局的预编译**
      1.  **创建 GO(Global Object) 对象 (浏览器里面是 Window)**
      2.  找**变量声明**，将变量名作为 GO 对象的属性名，**值为 `undefined`**
      3.  **查找函数声明**，作为 GO 对象的属性名，**值赋予函数体**(function)
          + 函数执行时，出现未声明就赋值的对象，添加到GO中，浏览器中属于 window。

\# **函数的预编译（发生在函数执行之前）**

   1.  **创建 AO (Activation Object) 对象：**
       *   AO 对象是函数执行时的上下文，它包含了函数内部的所有局部变量、参数、`this` 等。

   2.  **寻找形参和变量声明，将变量和形参名作为 AO 对象的属性名，值为 `undefined`：**
       *   注意：这一步包括了 `var` 声明的变量，以及函数的形参。

   3.  **将实参值和形参统一：**
       *   将传入的实参值赋值给对应的形参。

   4.  **在函数体里面找函数声明，值赋予函数体：**
        *   这一步是函数声明提升的关键。**如果函数体内有多个同名的函数声明，后面的会覆盖前面的。**
        *   注意，函数声明可以提升，函数表达式、箭头函数不提升。

**3. 示例与详细解释**

```javascript
function test(a, b) {
  console.log(a); // function a() {}
  console.log(b); // undefined

  var b = 123;
  console.log(b); // 123

  function a() {}
  var a;

  console.log(a); // function a() {}
}

test(1);
```

**预编译过程分析：**

1.  **创建 AO 对象：** `AO = {}`

2.  **找形参和变量声明，值为 `undefined`：**
    *   `AO = { a: undefined, b: undefined }`

3.  **实参和形参统一：**
    *   `AO = { a: 1, b: undefined }`

4.  **找函数声明，值为函数体：**
    *   `AO = { a: function a() {}, b: undefined }` (函数声明 `a` 覆盖了变量 `a`)

**执行过程分析：**

*   `console.log(a);` // 输出 `function a() {}` (因为 AO 中 `a` 是函数)
*   `console.log(b);` // 输出 `undefined` (AO 中 `b` 还是 `undefined`)
*   `var b = 123;` // 执行赋值，`AO.b` 变为 123
*   `console.log(b);` // 输出 123
*   `var a;` // 这行声明在预编译阶段已经处理过了，这里不会产生任何效果。
*   `console.log(a);` // 输出 `function a() {}` (AO 中 `a` 仍然是函数)

**4. `let` 和 `const` 的提升**

   `let` 和 `const` 声明的变量也存在提升，但与 `var` 不同：

   *   `let` 和 `const` 声明的变量被提升到块级作用域（`{}`）的顶部。
   *   在声明语句之前访问这些变量会抛出 `ReferenceError`，这种现象称为“暂时性死区”（TDZ）。
     * 变量已经提升, 但是不能使用

```javascript
function example() {
  // TDZ 开始
  console.log(x); // ReferenceError: Cannot access 'x' before initialization
  // TDZ 结束
  let x = 10; 
  console.log(x); // 10
}

```

---

#### 连等

好的，关于 JavaScript 中“连等” (Chained Assignment) 的知识点，我为你整理如下：

**1. 什么是连等？**

   连等是指在一条语句中，将同一个值连续赋值给多个变量。

   ```javascript
   let a, b, c;
   a = b = c = 10; 
   console.log(a, b, c); // 输出: 10 10 10
   ```

**2. 连等赋值的执行顺序：从右向左**

   *   最右边的表达式或值 (`10`) 先被计算。
   *   然后这个值被赋给最右边的变量 (`c`)。
   *   接着，`c` 的值（现在是 `10`）被赋给 `b`。
   *   最后，`b` 的值（也是 `10`）被赋给 `a`。

   **重要提示：** 理解执行顺序非常关键，尤其是在更复杂的表达式中。

**3. 连等与变量声明**

   *   **推荐的写法 (使用 `let` 或 `const` 分别声明每个变量):**

       ```javascript
       let a, b, c; // 先分别声明
       a = b = c = 10;
       ```
   *   不推荐的写法 (在连等中隐式创建全局变量)

     ```javascript
       a = b = c = 10;
       // 等同于
       c = 10;
       b = c;
       window.a = b; // 如果不在函数里面, a会变成全局变量., 极其不推荐
     ```
     
   * **为什么不推荐?**

     如果 `a`、`b`、`c` 中任何一个变量 *没有* 事先用 `let`、`const` （或在旧代码中的 `var`）声明，那么在非严格模式下，**它会被隐式地创建为全局变量**。在严格模式下，会报错（ReferenceError）。 这通常不是你想要的结果，还容易导致难以排查的 bug。

**4. 最佳实践和注意事项**

*   **优先使用独立的赋值语句：**  为了代码的清晰度和可维护性，通常最好将每个变量的赋值分开写：
    ```javascript
     let a = 10;
     let b = 10;
     let c = 10;
    ```
*   **避免在连等中隐式创建全局变量:** 永远记得用 let 或 const 声明变量
    ```javascript
       let a,b,c; // 这样写是最好的
       a = b = c = 10;
    ```

*   **如果一定要用连等，确保所有变量都已声明：**

*   **不要在连等中使用复杂的表达式：**  这会让代码难以理解和调试。

---

#### 数字与其他类型运算

**1. 核心原则：类型转换**

   当数字与其他类型的值进行运算时，JavaScript 通常会尝试将非数字类型的值 *隐式转换* 为数字，然后再进行运算。这种类型转换遵循一些规则，理解这些规则至关重要。

**2. 与字符串 (String) 运算**

   *   **`+` (加号) 的特殊性：**
       *   如果 `+` 的操作数中 *有任何一个是字符串*，那么 `+` 执行的是 *字符串拼接*，而不是数值加法。
           *   其他类型会被隐式转换为字符串。

       ```javascript
       let num = 10;
       let str = "20";
       let result = num + str; // 结果是 "1020" (字符串拼接)
       
       console.log(1 + "2");        // "12" (加号变身字符串连接符)
       console.log(1 + 2 + "3");    // "33" (先算 1+2，再和 "3" 拼接)
       console.log("1" + 2 + 3);    // "123" (从左到右，都是字符串拼接)
       ```

   *   **`-`、`*`、`/`、`%` (减、乘、除、取余)：**
       *   这些运算符会尝试将字符串 *转换* 为数字，然后进行数值运算。
       *   如果字符串不能被转换为有效的数字（例如 "abc"），结果将是 `NaN` (Not a Number)。

       ```javascript
       let num = 10;
       let str = "20";
       let result1 = num * str;   // 结果是 200 (字符串 "20" 被转换为数字 20)
       let result2 = num - str;  // -10
       let result3 = num / str;  // 0.5
       console.log(10 * "2");         // 20
       console.log(10 / "a");        // NaN (因为 "a" 不能转换为数字)
       console.log(10 % "3");        // 1
       ```

**3. 与布尔值 (Boolean) 运算**

   *   布尔值 `true` 会被转换为数字 `1`。
   *   布尔值 `false` 会被转换为数字 `0`。

   ```javascript
   let num = 5;
   console.log(num + true);   // 6 (true 被转换为 1)
   console.log(num * false);  // 0 (false 被转换为 0)
   ```

**4. 与 `null` 和 `undefined` 运算**

   *   `null` 会被转换为数字 `0`。
   *   `undefined` 会被转换为 `NaN`。

   ```javascript
   let num = 7;
   console.log(num + null);       // 7 (null 被转换为 0)
   console.log(num * undefined);  // NaN (undefined 被转换为 NaN)
   ```

**5. 与对象 (Object) 运算**

   * **通常不直接运算**： 对象 (除了Date) 在与数字运算前，通常会先被转换为原始值（primitive value）：
     1.  会尝试调用对象的VauleOf，返回如果是基本类型，就参与运算
     ```javascript
       let obj1 = { valueOf: () => 5 };
       console.log(10 + obj1);   //15
     ```
     2.  如果valueOf 返回的不是基本类型, 会继续调用toString().
     
     ```javascript
       let obj2 = {valueOf: () => ({}), toString: ()=>"6"};
       console.log(obj2 + 4);     // "64" , 注意这里字符串拼接
       console.log(obj2 * 6)      // 36  , 这里是数字乘法, 因为 `*` 没有字符串拼接的行为.
     ```
     
   *   **特例：Date 对象** Date 对象valueOf()方法返回时间戳（number）

**6. 显式类型转换 (更推荐的做法)**

   为了避免隐式类型转换带来的困惑和潜在错误，强烈建议使用以下方法进行显式类型转换：

   *   **`Number()`:** 将任何类型的值转换为数字。
   *   **`parseInt()`:** 将字符串转换为整数。
   *   **`parseFloat()`:** 将字符串转换为浮点数。
   *   **`String()`:** 将任何类型的值转换为字符串。

   ```javascript
   let str = "123.45";
   let num1 = Number(str);     // 123.45
   let num2 = parseInt(str);   // 123
   let num3 = parseFloat(str); // 123.45
   let str2 = String(45)       //"45"
   ```

**7. 最佳实践和注意事项**

*   **尽量避免依赖隐式类型转换：**  显式地转换类型，使代码更清晰、更可预测。
*   **注意 `+` 运算符的二义性：**  当有字符串参与时，`+` 是字符串拼接。
*   **了解 `NaN`：**
    *   `NaN` 是一个特殊的数字值，表示“不是一个数字”。
    *   任何与 `NaN` 进行的运算，结果都是 `NaN`。
    *   `NaN` 与任何值（包括它自己）都不相等： `NaN === NaN` 的结果是 `false`。需要用 `isNaN()` 函数来判断一个值是否是 `NaN`。

```javascript
console.log(NaN + 5);       // NaN
console.log(NaN === NaN);   // false
console.log(isNaN(NaN));     // true. 需要isNaN() 来判断
```

