---
title: makdown的书写(一)
date: 2023-07-09 04:05:13
tags: 
category: md的书写
---
项目结构分为静态和Hexo两部分，静态文章用于部署
### 用的命令
```angular2html
hexo g 生成静态网页
hexo d 部署git
hexo s 启动本地服务器
```

{% asset_img foo.jpg %}

[//]: # ({% bilibili PL9hW1uS6HUfscJ9DHkOSoOX45MjXduUxo 'BV1we4y1Y7qW' %})

### bilibili视频引入标签

your_video_id 是b站的bv号或av号。

```angular2html
{% bilicard your_video_id %} 
```

{% bilicard BV1we4y1Y7qW %}

### 链接

```
[我是内联样式的链接](https://www.google.com)

[我是带有标题的内联样式链接](https://www.google.com "Google's Homepage")

[是参考样式的链接][Arbitrary case-insensitive reference text]

[我是存储库文件的相对引用](../blob/master/LICENSE)

[可以将数字用于引用样式的链接定义][1]

或者将其留空并使用 [这是链接]

[arbitrary case-insensitive reference text]: https://hexo.io
[1]: https://hexo.io/docs/
[这是链接]: https://hexo.io/api/
```

[我是内联样式的链接](https://www.google.com)

[我是带有标题的内联样式链接](https://www.google.com "Google's Homepage")

[是参考样式的链接][Arbitrary case-insensitive reference text]

[我是存储库文件的相对引用](../blob/master/LICENSE)

[可以将数字用于引用样式的链接定义][1]

或者将其留空并使用 [这是链接]


[arbitrary case-insensitive reference text]: https://hexo.io

[1]: https://hexo.io/docs/

[这是链接]: https://hexo.io/api/

### 水平线

---

虚线

***

星号

___

下划线
### 分隔符

Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3
#### 表格
```angular2html
|                |ASCII                          |HTML                         |
|----------------|-------------------------------|-----------------------------|
|Single backticks|`'Isn't this fun?'`            |'Isn't this fun?'            |
|Quotes          |`"Isn't this fun?"`            |"Isn't this fun?"            |
|Dashes          |`-- is en-dash, --- is em-dash`|-- is en-dash, --- is em-dash|
```
|                |ASCII                          |HTML                         |
|----------------|-------------------------------|-----------------------------|
|Single backticks|`'Isn't this fun?'`            |'Isn't this fun?'            |
|Quotes          |`"Isn't this fun?"`            |"Isn't this fun?"            |
|Dashes          |`-- is en-dash, --- is em-dash`|-- is en-dash, --- is em-dash|
### 标签显示
```angular2html
<p>To reboot your computer, press <kbd>ctrl</kbd>+<kbd>alt</kbd>+<kbd>del</kbd>.</p>
```
<p>To reboot your computer, press <kbd>ctrl</kbd>+<kbd>alt</kbd>+<kbd>del</kbd>.</p>

```
<dl>
    <dt>定义列表</dt>
    <dd>小一号的字，这是小一号的字</dd>
    213
    <dt>Markdown in HTML</dt>
    <dd>Does *not* work **very** well. Use HTML <em>tags</em>.</dd>
</dl>
```
<dl>
    <dt>定义列表</dt>
    <dd>小一号的字，这是小一号的字</dd>
    213
    <dt>Markdown in HTML</dt>
    <dd>Does *not* work **very** well. Use HTML <em>tags</em>.</dd>
</dl>
<dl>
  <dt>Definition list</dt>
  <dd>Is something people use sometimes.</dd>

  <dt>Markdown in HTML</dt>
  <dd>Does *not* work **very** well. Use HTML <em>tags</em>.</dd>
</dl>
### 触碰显示提示框
```angular2html
{% hint 'body_text' 'hint_text_1st_line' 'hint_text_2nd_line' ... %}
{% hint '触碰显示' '第一行提示1' '第二行提示2' %}
```

{% hint '触碰显示提示' '第一行提示1' '第二行提示2' %}正常文字

[//]: # ({% imgurgal ryMBU %})

[//]: # ()
[//]: # ({% echarts 400 '85%' %})

[//]: # (\\TODO echarts option goes here)

[//]: # ({% endecharts %})
