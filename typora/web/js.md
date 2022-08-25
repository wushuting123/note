# 概念

- js是解释型语言，一边读一边执行

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

- 只有一下五种是false，其他都是true

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

```js
console.log(0.1 + 0.2);
```

输出

```js
0.300000000000004
```



# 通用写法

## 输入

- 能够获取用户输入的内容，获取到的是字符串，就算输入数字也还是字符串

```js
var str = prompt('请输入');
```

