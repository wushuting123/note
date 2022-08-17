# 浮动

1. 浮动不会压住文字，文字会环绕图片--浮动最初就是用于文字环绕效果



# 文字省略

## 单行

```css
white-space:nowrap;
overflow:hidden;
text-overflow:ellipsis;
```



## 多行

ie不兼容

```css
overflow:hidden;
text-overflow:ellipsis;
display:-webkit-box;
-webkit-line-clamp:3;
-webkit-box-orient:vertical;
```

