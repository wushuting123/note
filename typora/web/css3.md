# 说明

- 兼容性问题，ie9+才支持
- 移动端支持优于pc



# 新特性

## 选择器

- 权重是10，如果前面加标签选择器（1）就是11，比单纯类名权重（10）高

### 属性选择器

- 可以不借助id或类，来选择元素

```html
<style>
    /* 必须是input，且同时有value属性 */
    input[value] {
        color: red;
    }
  
    /* 必须是input，且有type属性值，值为text */
    input[type=text] {
        color: red;
    }
  
    /* 必须是input，且有class属性值，值以icon开头 */
    input[class^=icon] {
        color: red
    }
  
    /* 必须是input，且有class属性值，值以data结尾 */
    input[class$=data] {
        color: red
    }
  
    /* 必须是input，且有class属性值，值中有data */
    input[class*=data] {
        color: red
    }
</style>

<input class="icon1-data" type="text" value="请输入">
<input class="icon2-data" type="search">
```



### 结构伪类选择器

- *-child获取元素逻辑：先获取到父元素（ul）下对应序号的元素，再匹配子类（li），如果选择第一个元素，而第一个元素不是li，就不会生效了
- *-of-type获取元素逻辑：先获取到父元素（ul）下匹配的子类（li），再匹配对应序号的元素，如果选择第一个元素，而第一个元素不是li，就会继续往下找，直到找到li

```html
<style>
    /* 选择ul里的第一个子元素 */
    ul :first-child {
        color: red;
    }
    ul :first-of-type {
        color: red;
    }
  
    /* 选择ul里的第一个是li的子元素 */
    ul li:first-child {
        color: red;
    }
    ul li:first-of-type {
        color: red;
    }
  
    /* 选择ul里的最后一个子元素 */
    ul :last-child {
        color: red;
    }
    ul :last-of-type {
        color: red;
    }
  
    /* 选择ul里的第2个子元素 */
    ul :nth-child(2) {
        color: red;
    }
  
    /* 选择ul里的第偶数个子元素，奇数是odd */
    ul :nth-child(even) {
        color: red;
    }
    ul :nth-of-type(even) {
        color: red;
    }
  
    /* n从0开始（没有第0个元素，会跳过），效果就是选择ul里的每个子元素 */
    /* 如果是2n，就是选择第0,2,4,6...个元素 */
    /* 如果是2n+1，就是选择第1,3,5,7...个元素 */
    /* 如果是-n+5，就是选择前5个元素 */
    /* 如果是5n，就是选择第0,5,10...个元素，以此类推 */
    ul :nth-child(n) {
        color: red;
    }
    ul :nth-of-type(n) {
        color: red;
    }
</style>

<ul>
    <li></li>
    <li></li>
</ul>
```



### 伪元素选择器

