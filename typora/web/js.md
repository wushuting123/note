# 概念

- js是解释型语言，一边读一边执行，先进行预解析，再执行代码



## 作用域

- 同一个script标签/同一个引入的js文件中定义的变量有效
- 全局变量（函数外定义的），局部变量（函数中定义的），在函数内部，没有用var声明的变量，也属于全局变量
- 全局变量在浏览器关闭的时候才会销毁，比较占资源，局部变量在程序执行完毕就会销毁，比较节约内存资源
- es5没有块级作用域的概念，如果在if里定义的变量，外面还是能用到
- 作用域链：一个变量会查找到最近的作用域来获取值

```js
function test(){
    var a = b = c = 9;
}
```

相当于

```js
function test(){
    var a = 9;
    b = 9;
    c = 9;
}
```

其中，a是var声明的，是函数中的局部变量，b和c没有var声明，是全局变量



## 预解析

- 会把js里所有var和function提升到**当前作用域**最前

### 变量预解析

- 把所有变量声明提升到最前，但**并不执行赋值**

### 函数预解析

- 把所有函数声明提升到最前，但不会执行函数中的内容



# 输入

- 能够获取用户输入的内容，获取到的是字符串，就算输入数字也还是字符串

```js
var str = prompt('请输入');
```



# 函数

## 定义

- 第一种是函数，第二种是变量
- 第二种定义，调用函数的时候，必须在定义之后

```js
function test(){

}

var test2 = function () {
  
}
```



## 参数

### arguments

- 存储了所有传过来的变量
- 伪数组，有length，也可根据索引取内容，但不能增加

```js
function test(){
    console.log(arguments);
}
```



### 形参与实参

- 实参个数<形参个数，没有获取到值的形参就是undefined
- 实参个数>形参个数，会依次取实参的值

```js
function test ( num1,num2 ){
  return num1 + num2;
}

console.log(test(1));
console.log(test(1,2));
console.log(test(1,2,3));
```

输出

```js
NaN
3
3
```



### return

- 没有返回值的话，获取返回值就会得到undefined

```js
function test(){

}

console.log(test());
```

输出

```js
undefined
```



### 嵌套

- 函数中也可以再定义函数



# 数据类型

## 注意点

- 变量类型在赋值的时候才确认，且赋值为其他类型后能自动转化



## 简单数据类型

### 数字型

- 包含整数和小数
- Infinity表示∞，-Infinity表示-∞，NaN表示非数字
- 判断是否非数字：

```js
isNaN('[xxx]');
```



### 字符串型

- 转义符，都是\开头

| 转义符 | 说明    |
| ------ | ------- |
| \n     | 换行    |
| \\     | 斜杠    |
| \'     | 单引号  |
| \"     | 双引号  |
| \t     | tab缩进 |
| \b     | 空格    |



### 布尔型

- 如果和数字相加的话，ture和false分别代表1和0

```js
console.log(true+1);
```

输出

```js
2
```



## 数据转换

### 转为字符串

- 字符串与任何类型相加都是字符串

```js
console.log(parseInt('字符串' + 12));
console.log(parseInt('字符串' + true));
```

输出

```js
'字符串12'
'字符串true'
```



### 转为整数

```js
console.log(parseInt('3.94'));
console.log(parseInt('120px'));
console.log(parseInt('rem120px'));
```

结果

```js
3
120
NaN
```



### 转为数字

```js
console.log(parseFloat('3.94'));
console.log(parseFloat('120px'));
console.log(parseFloat('rem120px'));
```

结果

```js
3.94
120
NaN
```



```js
console.log(Number('123'))
```

输出

```js
123
```



隐式转换，使用- * /才可以，使用+是不可以的

```js
console.log('12' - 0);
```

输出

```js
12
```



### 转为布尔型

- 只有以下五种是false，其他都是true

```js
console.log(Boolean(''));
console.log(Boolean(0));
console.log(Boolean(NaN));
console.log(Boolean(null));
console.log(Boolean(undefined));
```

输出

```js
false
```



## 判断数据类型

```js
console.log(typeof '字符串');
```

输出

```js
'string'
```



# 运算符

- 加+ 减- 乘* 除/ 余%
- 小数计算有误差，尽量不用，整数没问题
- 不要直接判断两个浮点数是否相等
- ==会自动转型，===不会，所以需要数值类型也相等

```js
console.log(0.1 + 0.2);
console.log(1 == '1');
console.log(1 === '1');
```

输出

```js
0.300000000000004
true
false
```



## 运算顺序

| 优先级 | 运算符     | 顺序          |
| ------ | ---------- | ------------- |
| 1      | 小括号     | ()            |
| 2      | 一元运算符 | ++ -- !       |
| 3      | 算数运算符 | 先* / % 后+   |
| 4      | 关系运算符 | > >= < <=     |
| 5      | 相等运算符 | == != === !== |
| 6      | 逻辑运算符 | 先&&后\|\|    |
| 7      | 赋值运算符 | =             |
| 8      | 逗号运算符 | ,             |



# 逻辑判断

- 表达式参与逻辑运算时
- 为假的结果：'' 0 undefined null NaN
- 表达式1&&表达式2
  - 表达式1为真，则返回表达式2
  - 表达式1为假，则返回表达式1
- 表达式1||表达式2
  - 表达式1为真，则返回表达式1
  - 表达式1为假，则返回表达式2

```js
console.log(123 && 456);
console.log(123 || 456);
```

输出

```js
456
123
```



# 数组

- 不能给数组赋值，否则会直接覆盖掉数组中的内容
- 同一个数组中数据类型可以不同

## 创建

```js
/*写法一*/
var arr = [];
/*写法二*/
var arr2 = new Array();
```



## 常见写法

- 生成新数组的时候，可以直接用数组的length来作为下标

```js
var arr = [1, 2, 3];
var newArr = [];
for (var i = 0; i < arr.length; i++) {
    if (arr[i] > 1) {
        newArr[newArr.length] = arr[i];
    }
}
```



## 新增

- 新增的长度，如果没赋值，都是undefined

```js
var arr = [1, 2, 3];
/*写法一*/
arr.length = 5;
/*写法二*/
arr[7] = 8;
```



# 对象

- 对象是指定某一个，而不是某一类

## 自定义对象

### 创建

```js
/*第一种*/
var obj = {};
/*第二种*/
var obj = new Object();
/*第三种*/
function Obj(){
  
}
```



### 格式

- 键值对形式
- 方法冒号后面跟的是匿名函数
- 构造函数首字母大写

```js
/*第一种*/
var obj = {
    name : 'xxx',
    age : 18,
    start: function(){
        console.log('111');
    }
};
/*调用*/
console.log(obj.name);
console.log(obj['age']);
obj.start();

/*第二种*/
var obj2 = new Object();
obj2.name = 'xxx',
obj2.age = 18,
obj2.start= function(){
    console.log('111');
}
/*调用*/
console.log(obj.name);
console.log(obj['age']);
obj.start();

/*第三种*/
function Obj3(name,start){
    this.name = name;
    this.start = function(e){
        console.log(e);
    }
}
/*调用*/
var result = new Obj3('xxx');
result.start('123');
```



### 遍历

```js
var obj = {
    name : 'xxx'
};
for(var k in obj){
  console.log(k);
  console.log(k.name);
}
```

输出

```js
name
'xxx'
```



## 内置对象

- js语言自带的对象，方便开发者使用

### 文档

[mdn]: https://developer.mozilla.org/zh-CN/docs/Web/JavaScript



### Math

- 不是构造函数，都是静态方法，直接调用，不需要new

#### 文档

[Math]: https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math



### Date

- 是构造函数，必须使用new来创建日期对象

#### 文档

[Date]: https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date



#### 常用写法

```js
/*不传参返回当前时间*/
var today = new Date();
/*传数字的时候，注意月份要比实际-1*/
var day = new Date(2022,9,3);
/*支持多种格式*/
var day2 = new Date('2022-9-3');
var day3 = new Date('2022-9-3 23:7:8');
var day4 = new Date('2022/9/3 23:7:8');
/*******格式化*******/
var year = today.getFullYear();
/*月份会比实际-1*/
var month = today.getMonth() + 1;
var date = today.getDate();
/*周日返回是0，其他正常*/
var day = today.getDay();
var hour = today.getHours();
var minute = today.getMinutes();
var second = today.getSeconds();
/*******格式化*******/
```

