# 笔记说明

[xxx]表示需要根据实际需要替换的内容

# 简介

## 优势

增加了新标签、新表单属性等

## 兼容性

ie9+



# 新特性

## 语义化标签

- 主要针对搜索引擎
- 在页面中可多次使用
- ie9中，需要把这些元素转为块级元素
- 移动端多用，因为没有兼容性问题

```html
<!--头部-->
<header></header>
<!--导航-->
<nav></nav>
<!--侧边栏-->
<aside></aside>
<!--内容-->
<article>
    <!--区域-->
    <section></section>
</article>
<!--尾部-->
<footer></footer>
```



## 多媒体标签

### 视频

- 推荐使用mp4格式
- 不需要插件也可以播放

#### 常规写法

```html
<video scr="[url]" controls="controls"></video>
```

#### 兼容性写法

```html
<video scr="[url]" width="[width]" height="[height]" controls>
    <source src="[url]" type="video/mp4">
    <source src="[url]" type="video/ogg">
    您的浏览器不支持video标签
</video>
```

