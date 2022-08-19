# 说明

- 兼容性问题，ie9+才支持
- 移动端支持优于pc



# 新特性

## 选择器

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
</style>

<input type="text" value="请输入">
<input type="search">
```

