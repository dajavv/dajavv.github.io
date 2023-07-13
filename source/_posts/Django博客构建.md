---
title: Django博客构建
date: 2023-07-13 23:43:03
tags: [python,Django,]
category: 学习
---

### 视频参考

{% bilicard BV1K94y1B7PC %}

### 使用工具

+ PyCharm 2023.1
+ python3.10版本

### Hexo框架

在使用了一段时间的Hexo博客后，对该框架的感受:

+ #### 优点
    - 具有很多的主题，每一款都非常好看
    - 强大的模板语法
    - 生态完善，具有大量插件，比如:bilibili视频的小卡片
+ #### 缺点
    - **部署不便，要使用命令导入静态文件后部署到github，国内登入网络不稳定(痛点)**
    - 加载缓慢，当文章的数量到达一定程度后加载会很缓慢
    - 缺少后端进行管理
    - 无法对整体文章进行搜索(可以通过插件实现，但比较麻烦，好像是api调用那种。)
    - 缺少与访客的互动
    - 缺少对访客数据的记录

### 解决问题

对于这些问题我决定对博客进行重构，让博客具有更强的功能，我打算对Hexo框架所创建的博客进行重构。
使用python的Django框架进行重构

+ ## 已有功能
+ 导航栏
+ 白天黑夜切换
+ 分类
+ 归档
+ 标签分类
+ 最新文章
+ ## 新功能
+ 发布文章
+ 发布公告
+ 访客数据统计
+ 后台写作
+ 全站搜索

# 开始

1. 使用PyCharm创建项目，conda创建虚拟环境python3.10
2. 创建app命名为post
3. settings中添加post应用
4. 对原html静态文件进行导入拆分
5. 配置路由，检查是否能正常运行显示
6. 创建数据表，对需要进行动态更新的数据创建数据表
7. 配置中文，易读

[//]: # (![图片]&#40;https://img1.8jppeg.com/images/64b01ec53389e89b4aafba34.jpg&#41;)

### 创建应用

使用ctrl+alt+R快捷键打开manage专属控制台

```angular2html
startapp post # 输入代码创建app
```

在settings.py文件INSTALLED_APPS配置项中添加post应用

```angular2html
INSTALLED_APPS = [
'django.contrib.admin',
'django.contrib.auth',
'django.contrib.contenttypes',
'django.contrib.sessions',
'django.contrib.messages',
'django.contrib.staticfiles',
'post' #添加app
]
```

### 对博客网页进行拆分

组件化拆分利于更新与维护

+ 拆解部分
    - 横幅
    - 导航栏
    - 侧边栏
    - 文章选项卡片
    - 底部页脚

```angular2html
{% include 'banner.html' %} #横幅
<div id="main-grid" class="shadow">
  {% include 'head.html' %} #导航栏
  {% include 'right.html' %} #侧边栏
  {% block main %} <!--与app中的index相连--> #文章选项卡片
  {% endblock %}
  {% include 'footer.html' %} #底部页脚
  <div class="back-to-top-wrapper"><!--回到顶部按键-->
    <button id="back-to-top-btn" class="back-to-top-btn" onclick="topFunction()"> #回到顶部的按钮
      <span class="material-symbols-rounded">keyboard_arrow_up</span>
    </button>
  </div>
</div>
```

### 路径配置

在settings.py文件中添加STATICFILES_DIRS配置

```angular2html
STATIC_URL = 'static/'
STATICFILES_DIRS = [
os.path.join(BASE_DIR, 'static', 'css'),  # BASE_DIR根目录
os.path.join(BASE_DIR, 'static', 'js'),
os.path.join(BASE_DIR, 'static', 'fontawesome'),
]
```

这条配置会指定对寻找文件的路径，这里我让他去寻找static文件夹中的css文件夹

```angular2html
<link rel="stylesheet" href="/static/style.css">
其中的href路径，相当于
static/css/style.css
```

```angular2html
<script src="/static/bundle.js"></script>{% comment %}背景白天黑夜变换{% endcomment %}
```
