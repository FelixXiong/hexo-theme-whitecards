# hexo-theme-whitecards
Based on hexo theme light

基于Light主要样式进行自定义修改，部分中国服务代码来源于light-cn，在此列出他们的地址。

Light theme on github:[hexo-theme-light](https://github.com/hexojs/hexo-theme-light)

Light-CN theme cn on github:[Hexo-theme-light_cn](https://github.com/pengloo53/Hexo-theme-light_cn)

## Preview：

![](https://i.loli.net/2018/05/04/5aebf563bfaa2.png)

## Introduction

目前此主题**需要修改**之后才可使用，如果觉得好看，欢迎star，fock修改以及PR。
这是我在hexo主题上的一次自定义的尝试。

## 已知issue

1.菜单错误：

- 点击Archives，Tags，Categories，WechatPubilc,Portfolio,About,地址栏会直接以该单词为开头例如archives/，之后如果在国内环境下则进入域名纠错系统。

- 点击Page会出现```https://page/```

- 点击GitHub会出现“Cannot GET /https://github.com/……”

2,右侧Widgets失效

- search失效

- calader没有相应的json文件 issus：[请问Calendar模块在本地显示正常，但是发布到github上看不见日历了](https://github.com/pengloo53/Hexo-theme-light_cn/issues/4)

- 微博小部件报错，报错代码：Partial ../_widget/weibo does not exist. (in _partial/sidebar.ejs)

文件themes/hexo-theme-whitecards/layout/_widgetweibo.ejs中：
```
<div class="widget">
<h3 class="title">我的微博</h3>
<ul class="weibo">
<iframe width="100%" height="550" class="share_self"  frameborder="0" scrolling="no" src="<%- http://widget.weibo.com/weiboshow/…… %>"></iframe>
</ul>
</div>
```
```src="<%- http://widget.weibo.com/weiboshow/…… %>"```可能为你的微博秀挂件链接，在此需要确认。


我开的issue：

light:[Cannot read property 'height' of undefined & TypeError](https://github.com/hexojs/hexo-theme-light/issues/71)

light_cn:[我的微博 小部件出现问题](https://github.com/pengloo53/Hexo-theme-light_cn/issues/7)


3,文章错误

Read more点击依然是Read more。

## Install

With git：

```$ git clone https://github.com/FelixXiong/hexo-theme-whitecards```

## Config

使用了非常简单的```# func -----```进行区分。

```
# Blog _config.yml

# Menu settings --------------------------------------------

menu:
Home:
Archives: /archives
Tags: /tags
Categories: /categories
Page: /page
Post: /post
#Schedule: /schedule
#Sitemap: /sitemap.xml
#Commonweal: /404
WechatPubilc: /wechatpubilcaccount # Account
Portfolio: /portfolio
Github: #https://github.com/yourmname
About: /about
#RSS: /rss
#Preview: /preview

widgets:
- search
- recent_posts
- category
- tagcloud
- tag
- calendar
- links
- twitter
- weibo
- weixin

# Article settings --------------------------------------------

## toc settings --------------------------------------------

toc:

# Table Of Contents in the Sidebar
enable: true

# Automatically add list number to toc.
number: false

# If true, all words will placed on next lines if header width longer then sidebar width.
wrap: false

## Comment settings--------------------------------------------

##这里如果需要添加评论服务需要添加ejs文件，路径位于：你的hexo目录/themes/light/layout/_partial

comment_provider: gitment
# Facebook comment
facebook:
appid: 123456789012345
comment_count: 5
comment_width: 840
comment_colorscheme: light

## Share settings--------------------------------------------

# baidu share

baidu_share: false

excerpt_link: Read More
#comment_link: Comments

#Header settings --------------------------------------------

# header
avatar: /img/default/avatar.png
# header右侧图片展示
ad:

# 请到after_footer.ejs中替换百度统计代码

baidu_tongji: false

# Sidebar Settings --------------------------------------------


## Widget settings --------------------------------------------

# 微博: height小挂件高度；url替换成自己的微博挂件地址，同步修改url中height的值
weibo:
height: 550
url: http://widget.weibo.com/weiboshow/index.php?……
#tweet_count: 5

twitter:
username:
show_replies: false
tweet_count: 5

# Calendar
calendar:
language: zh-CN
root: calendar

# Wechat
Wechat:
qrcode: /img/default/qrcode.jpg
alt: 欢迎关注个人公众账号

# friendly links
links:
#: http://

addthis:
enable: true
pubid:
facebook: true
twitter: true
google: true
pinterest: true

fancybox: true

google_analytics:

rss:

```
