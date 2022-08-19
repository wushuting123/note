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

- 推荐使用mp4格式，大部分浏览器都支持
- 不需要插件也可以播放
- 默认的视频控件样式在各个浏览器不同，如果需要统一，不写controls属性，通过js来实现

#### 常规写法

```html
<video scr="vedio/apple.mp4" controls="controls" autoplay="autoplay" muted="muted" width="100%" loop="loop"></video>
```

#### 兼容性写法

```html
<video scr="[url]" width="[width]" height="[height]" controls>
    <source src="[url]" type="video/mp4">
    <source src="[url]" type="video/ogg">
    您的浏览器不支持video标签
</video>
```

#### 常用属性

| 属性名   | 属性值     | 用途                                         |
| -------- | ---------- | -------------------------------------------- |
| autoplay | autoplay   | 自动播放（谷歌浏览器禁用了）                 |
| muted    | muted      | 静音播放（可解决谷歌浏览器不自动播放的问题） |
| controls | controls   | 向用户显示播放控件                           |
| width    |            | 宽度                                         |
| height   |            | 高度                                         |
| loop     | loop       | 循环播放                                     |
| src      |            | 视频地址                                     |
| preload  | auto\|none | 是否预加载，如果有了autoplay，这个属性忽略   |
| poster   |            | 加载等待的画面图片地址                       |



### 音频

- 推荐使用mp3格式，大部分浏览器都支持

#### 常规写法

```html
<audio src="audio/apple.mp3" controls="controls" autoplay="autoplay"></audio>
```

#### 兼容性写法

```html
<audio controls>
    <source src="horse.ogg" type="audio/ogg">
    <source src="horse.mps" type="audio/mpeg">
    您的浏览器不支持audio元素
</audio>
```

#### 常用属性

| 属性值   | 属性名   | 备注                               |
| -------- | -------- | ---------------------------------- |
| autoplay | autoplay | 自动播放（谷歌禁用了，通过js处理） |
| controls | controls | 向用户展示播放控件                 |
| loop     | loop     | 循环播放                           |
| muted    | muted    | 静音                               |



## input类型

| 属性值        | 说明                                 |
| ------------- | ------------------------------------ |
| type="email"  | 限制输入类型为邮箱                   |
| type="url"    | 限制输入类型为url                    |
| type="date"   | 限制输入类型为日期，可以直接选择日期 |
| type="time"   | 限制输入类型为时间，可以直接选择时间 |
| type="month"  | 限制输入类型为月                     |
| type="week"   | 限制输入类型为周                     |
| type="number" | 限制输入类型为数字                   |
| type="tel"    | 限制输入类型为电话号码               |
| type="search" | 代表搜索框                           |
| type="color"  | 颜色选择控件，可以选择颜色           |



## 表单属性

#### 必填

```html
<input type="text" required="required">
```

#### 提示信息

- 颜色可变

```html
<style>
    input::placeholder {
        color: red;
    }
</style>

<input type="search" placeholder="提示信息">
```

#### 自动获取焦点

```html
<input type="search" autofocus="true">
```

#### 显示历史提交记录

- 属性值：on｜off，默认打开
- 需要放在表单内，加上name属性，并提交成功
- 为了安全性，像密码之类的输入框就需要关闭这个功能

```html
<input type="search" autocomplet="on" name="search">
```

#### 多选文件提交

- 有了这个属性，才能按住ctrl键多选文件上传

```html
<input type="file" multiple="multiple">
```

