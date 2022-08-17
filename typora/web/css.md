# 初始化

```css
/*清除内外边距*/
* {
    margin: 0;
    padding: 0;
}

/*清除斜体*/
em, i {
    font-style: normal;
}

/*去掉小圆点*/
li {
    list-style: none;
}

img {
    /*低版本浏览器，如果图片外面包含链接会有边框*/
    border: 0;
    /*取消图片底侧有空白缝隙的问题*/
    vertical-align: middle;
}

/*鼠标经过按钮时，调整样式*/
button {
    cursor: pointer;
}

/*固定颜色，取消下划线*/
a {
    color: #666;
    text-decoration: none;
}

a:hover {
    color: #c81623;
}

body {
    /*文字抗锯齿*/
    -webkit-font-smoothing: antialiased;
    background-color: #fff;
    color: #666;
}

.hidden {
    display: none;
}

/*清除浮动*/
.clearfix:after {
    visibility: hidden;
    clear: both;
    display: block;
    content: ".";
    height: 0;
}

.clearfix {
    *zoom: 1;
}
```



# 中文转Unicode

用于字体

```css
font-family: "[code]";
```

## 黑体

\9ED1\4F53

## 宋体

\5B8B\4F53

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

