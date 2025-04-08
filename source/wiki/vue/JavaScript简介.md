---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: JavaScript简介
---

##### JavaScript简介

##### JavaScript 是 web 开发人员必须学习的 3 门语言中的一门：

*   HTML 定义了网页的内容
*   CSS 描述了网页的布局
*   JavaScript 控制了网页的行为

##### JavaScript 是脚本语言

*   JavaScript 是一种轻量级的编程语言（以少量的代码完成高级功能）

1.  语法简单
2.  不用编译（浏览器运行过程中逐步解释）
3.  不依赖ide
4.  调式方便（浏览器调试）

*   JavaScript 是可插入 HTML 页面的编程代码。
*   JavaScript 插入 HTML 页面后，可由所有的现代浏览器执行。
*   JavaScript 容易学习。

##### JavaScript与Java没有关系

为什么起名叫JavaScript？原因是当时Java语言非常红火，网景公司希望借Java的名气来推广，但事实上JavaScript除了语法上有点像Java，其他部分基本上没啥关系。

##### JavaScript版本

由于JavaScript的标准——ECMAScript在不断发展， 最新版ECMAScript 12标准（简称ES12）已经在2021年6月正式发布，所以，讲到JavaScript的版本，实际上就是说它实现了ECMAScript标准的哪个版本。

##### 快速入门

JavaScript代码可以直接嵌在网页的任何地方，不过通常我们都把JavaScript代码放到<head>中：

<head>
<script>
alert('Hello, world');
</script>
</head>

第二种方法是把JavaScript代码放到一个单独的.js文件，然后在HTML中通过<script src="..."></script>引入这个文件：

<head>

<script src="/static/js/abc.js?20210927"></script>

</head>

##### 基本语法

###### 变量

*   使用关键字 **var** 来定义变量
*   使用等号来为变量赋值

###### 语句

*   每个语句以 ; 结束
*   语句块用 {...}

#### 注释

*   //
*   /\* \*/

#### 大小写

JavaScript严格区分大小写，如果弄错了大小写，程序将报错或者运行不正常。

### 数据类型

##### Number

不区分整数和浮点数，统一用Number表示，以下都是合法的Number类型：

123; _// 整数123_

0.456; _// 浮点数0.456_

1.2345e3; _// 科学计数法表示1.2345x1000，等同于1234.5_

\-99; _// 负数_

NaN; _// NaN表示Not a Number，当无法计算结果时用NaN表示_

Infinity; _// Infinity表示无限大，当数值超过了JavaScript的Number所能表示的最大值时，就表示为Infinity_

##### 字符串

字符串是以单引号'或双引号"括起来的任意文本。

##### 多行字符串

由于多行字符串用\\n写起来比较费事，所以最新的ES6标准新增了一种多行字符串的表示方法，用反引号\`...\`表示：

\`这是一个

多行

字符串\`;

##### 布尔

ture/false

##### Null和undefined

null表示一个“空”的值，它和0以及空字符串''不同，0是一个数值，''表示长度为0的字符串，而null表示“空”。

JavaScript的设计者希望用null表示一个空的值，而undefined表示值未定义。事实证明，这并没有什么卵用，区分两者的意义不大。大多数情况下，我们都应该用null。undefined仅仅在判断函数参数是否传递的情况下有用。

##### 数组

JavaScript的数组可以包括任意数据类型。例如：

var arr = \[1, 2, 3.14, 'Hello', null, true\];

越界访问索引是被允许的：

var arr = \[1, 2, 3.14, 'Hello', null, true\];//length=6

arr\[7\] = 5;

// arr会改变

arr = \[1, 2, 3.14, 'Hello', null, true, undefined, 5\];

##### 对象

JavaScript的对象是一组由键-值组成的无序集合，例如：

**var** person = {

name: 'Bob',

age: 20,

city: 'Beijing',

hasCar: true,

zipcode: null

};

JavaScript对象的键都是字符串类型，值可以是任意数据类型。上述person对象一共定义了5个键值对。

##### 函数

##### 定义和调用

##### 定义函数

定义函数的方式如下：

**function** abs(x) {

**if** (x >= 0) { **return** x; }

**else** { **return** -x; }

}

上述abs()函数的定义如下：

*   function指出这是一个函数定义；
*   abs是函数的名称；
*   (x)括号内列出函数的参数，多个参数以,分隔；
*   { ... }之间的代码是函数体，可以包含若干语句，甚至可以没有任何语句。

第二种定义函数的方式如下：

**var** abs = **function** (x) {

**if** (x >= 0) { **return** x; }

**else** { **return** -x; }

};

在这种方式下，function (x) { ... }是一个匿名函数，它没有函数名。但是，这个匿名函数赋值给了变量abs，所以，通过变量abs就可以调用该函数。

#### 调用函数

abs(10);//返回10

#### 参数

由于JavaScript允许传入任意个参数而不影响调用，因此传入的参数比定义的参数多没有问题，传入的参数比定义的少也没有问题：此时abs(x)函数的参数x将收到undefined，计算结果为NaN。

#### arguments

JavaScript还有一个免费赠送的关键字arguments，它只在函数内部起作用，并且永远指向当前函数的调用者传入的所有参数。

利用arguments，你可以获得调用者传入的所有参数。也就是说，即使函数不定义任何参数，还是可以拿到参数的值：

实际上arguments最常用于判断传入参数的个数。

_// foo(a\[, b\], c)_

_// 接收2~3个参数，b是可选参数，如果只传2个参数，b默认为null：_

**function** foo(a, b, c) {

**if** (arguments.length === 2) {

_// 实际拿到的参数是a和b，c为undefined_

c = b; _// 把b赋给c_

b = null; _// b变为默认值_

}

_// ..._

}

#### rest参数

ES6标准引入了rest参数，获取除了已定义参数a、b之外的参数：

function foo(a, b, ...rest) {
console.log('a = ' + a);
console.log('b = ' + b);
console.log(rest);
}
foo(1, 2, 3, 4, 5);
foo(1, 2, 3, 4, 5);
foo(1);

_// 结果:_

_// a = 1_

_// b = undefined_

_// Array \[ \]_

rest参数只能写在最后，前面用...标识

如果传入的参数连正常定义的参数都没填满，也不要紧，rest参数会接收一个空数组（注意不是undefined）。

### 作用域

#### 全局作用域

不在任何函数内定义的变量就具有全局作用域。

JavaScript默认有一个全局对象window，全局作用域的变量实际上被绑定到window的一个属性

#### 局部作用域

由于JavaScript的变量作用域实际上是函数内部，我们在for循环等语句块中是无法定义具有局部作用域的变量的：

**function** foo() {

**for** (**var** i=0; i<100; i++) {

_//_

}

i += 100; _// 仍然可以引用变量i_

}

为了解决块级作用域，ES6引入了新的关键字let，用let替代var可以申明一个块级作用域的变量：

**function** foo() {

**var** sum = 0;

**for** (**let** i=0; i<100; i++) {

sum += i;

}

i += 1; _// SyntaxError:_

}

### 常量

由于var和let申明的是变量，如果要申明一个常量，在ES6之前是不行的，我们通常用全部大写的变量来表示“这是一个常量，不要修改它的值”：

**var** PI = 3.14;

ES6标准引入了新的关键字const来定义常量，const与let都具有块级作用域：

**const** PI = 3.14;

PI = 3; _// 某些浏览器不报错，但是无效果！_

PI; _// 3.14_

### 解构赋值

从ES6开始，JavaScript引入了解构赋值，可以同时对一组变量进行赋值。

什么是解构赋值？我们先看看传统的做法，如何把一个数组的元素分别赋值给几个变量：

**var** **array** = \['hello', 'JavaScript', 'ES6'\];

**var** x = **array**\[0\];

**var** y = **array**\[1\];

**var** z = **array**\[2\];

现在，在ES6中，可以使用解构赋值，直接对多个变量同时赋值：

Top of Form

// 如果浏览器支持解构赋值就不会报错:

var \[x, y, z\] = \['hello', 'JavaScript', 'ES6'\];

注意，对数组元素进行解构赋值时，多个变量要用\[...\]括起来。

如果数组本身还有嵌套，也可以通过下面的形式进行解构赋值，注意嵌套层次和位置要保持一致：

**let** \[x, \[y, z\]\] = \['hello', \['JavaScript', 'ES6'\]\];

解构赋值还可以忽略某些元素：

**let** \[, , z\] = \['hello', 'JavaScript', 'ES6'\]; _// 忽略前两个元素，只对z赋值第三个元素_

Bottom of Form

#### 使用场景

解构赋值在很多时候可以大大简化代码。例如，交换两个变量x和y的值，可以这么写，不再需要临时变量：

**var** x=1, y=2;

\[x, y\] = \[y, x\]

快速获取当前页面的域名和路径：

**var** {hostname:domain, pathname:path} = location;

### 方法

在一个对象中绑定函数，称为这个对象的方法。

在JavaScript中，对象的定义是这样的：

**var** xiaoming = {

name: '小明',

birth: 1990

};

但是，如果我们给xiaoming绑定一个函数，就可以做更多的事情。比如，写个age()方法，返回xiaoming的年龄：

**var** xiaoming = {

name: '小明',

birth: 2000,

age: **function** () {

**var** y = **new** Date().getFullYear();

**return** y - **this**.birth;

}

};

xiaoming.age; _// function xiaoming.age()_

xiaoming.age(); _// 今年调用是21,明年调用就变成22了_

绑定到对象上的函数称为方法，和普通函数也没啥区别，但是它在内部使用了一个this关键字。

在一个方法内部，this是一个特殊变量，它始终指向当前对象，也就是xiaoming这个变量。所以，this.birth可以拿到xiaoming的birth属性。

### 高阶函数

JavaScript的函数其实都指向某个变量。既然变量可以指向函数，函数的参数能接收变量，那么一个函数就可以接收另一个函数作为参数，这种函数就称之为高阶函数。

一个最简单的高阶函数：

**function** add(x, y, f) {

**return** f(x) + f(y);

}

当我们调用add(-5, 6, Math.abs)时，参数x，y和f分别接收-5，6和函数Math.abs，根据函数定义，我们可以推导计算过程为：

x = -5;

y = 6;

f = Math.abs;

f(x) + f(y) ==> Math.abs(-5) + Math.abs(6) ==> 11;

**return** 11;

### 箭头函数

ES6标准新增了一种新的函数：Arrow Function（箭头函数）。

为什么叫Arrow Function？因为它的定义用的就是一个箭头：

x => x \* x

上面的箭头函数相当于：

**function** (x) {

**return** x \* x;

}

箭头函数相当于匿名函数，并且简化了函数定义。箭头函数有两种格式，一种像上面的，只包含一个表达式，连{ ... }和return都省略掉了。还有一种可以包含多条语句，这时候就不能省略{ ... }和return：

x => {

**if** (x > 0) { **return** x \* x; }

**else** { **return** - x \* x; }

}

如果参数不是一个，就需要用括号()括起来：

_// 两个参数:_

(x, y) => x \* x + y \* y

##### 标准对象

### Date

Date对象用来表示日期和时间。

获取当前系统时间：

var now = new Date();//

now.getFullYear(); //年份

now.getMonth(); //月份

now.getDate(); //几号

now.getDay(); //星期几

now.getMinutes(); //分钟

now.getSeconds(); //秒

now.getMilliseconds(); //毫秒

now.getTime(); //时间戳

创建指定日期的Date对象:

Var d = new Date(2021,8,26,15,30,20,123);//注意8表示9月，这是因为设计问题，月份从0开始

### JSON

JSON是JavaScript Object Notation(JavaScript对象表示法)的缩写，它是一种数据交换格式。

JSON实际上是JavaScript的一个子集。在JSON中，一共就这么几种数据类型：

*   number：和JavaScript的number完全一致；
*   boolean：就是JavaScript的true或false；
*   string：就是JavaScript的string；
*   null：就是JavaScript的null；
*   array：就是JavaScript的Array表示方式——\[\]；
*   object：就是JavaScript的{ ... }表示方式。

以及上面的任意组合。

JSON还定死了字符集必须是UTF-8，表示多语言就没有问题了。为了统一解析，JSON的字符串规定必须用双引号""，Object的键也必须用双引号""。

### 序列化

把任何JavaScript对象变成JSON，就是把这个对象序列化成一个JSON格式的字符串

var xiaoming = {

name: '小明',

age: 14,

gender: true,

height: 1.70,

grade: null,

'middle-school': '\\"W3C\\" Middle School',

skills: \['JavaScript', 'Java', 'Python', 'Lisp'\]

};

JSON.stringify(xiaoming);

要输出得好看一些，可以加上参数，按缩进输出：

JSON.stringify(xiaoming, null, ' ');

第二个参数用于控制如何筛选对象的键值，如果我们只想输出指定的属性，可以传入Array：

JSON.stringify(xiaoming, \['name', 'skills'\], ' ');

如果我们还想要精确控制如何序列化小明，可以给xiaoming定义一个toJSON()的方法，直接返回JSON应该序列化的数据：

var xiaoming = {
name: '小明',
age: 14,
gender: true,
height: 1.65,
grade: null,
'middle-school': '\\"W3C\\" Middle School',
skills: \['JavaScript', 'Java', 'Python', 'Lisp'\],
toJSON: function () {
return { // 只输出name和age，并且改变了key：
'Name': this.name,
'Age': this.age };
}
};
JSON.stringify(xiaoming); // '{"Name":"小明","Age":14}'

还可以传入一个函数，这样对象的每个键值对都会被函数先处理：

**function** convert(key, value) {

**if** (**typeof** value === 'string') {

**return** value.toUpperCase();

}

**return** value;

}

JSON.stringify(xiaoming, convert, ' ');

上面的代码把所有string类型的属性值都变成大写：

{

"name": "小明",

"age": 14,

"gender": true,

"height": 1.65,

"grade": null,

"middle-school": "\\"W3C\\" MIDDLE SCHOOL",

"skills": \[

"JAVASCRIPT",

"JAVA",

"PYTHON",

"LISP"

\]

}

### 反序列化

拿到一个JSON格式的字符串，我们直接用JSON.parse()把它变成一个JavaScript对象：
```
JSON.parse('\[1,2,3,true\]'); // \[1, 2, 3, **true**\]

JSON.parse('{"name":"小明","age":14}'); // Object {name: '小明', age: 14}

JSON.parse('true'); // **true**

JSON.parse('123.45'); // 123.45

JSON.parse()还可以接收一个函数，用来转换解析出的属性：

Var obj = JSON.parse('{{"name":"小明"}', function(key,value){

If(key==='name'){ return value+'同学';}

Return value;

});

Console.log(JSON.stringify(obj));//{name: '小明同学'}
```