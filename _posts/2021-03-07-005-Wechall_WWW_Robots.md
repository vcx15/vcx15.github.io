---
layout: post
title:  "CTF-Wechall-WWW Robots"
date:   2021-03-07 03:11:13 +0000
categories: CTF
tags: 2021-03 CTF 爬虫 WEB
comments: 0
---
### robots.txt是什么
> robots协议也叫robots.txt是一种存放于网站根目录下的ASCII编码的文本文件
### robots.txt的作用
> Robots协议用来告知搜索引擎哪些页面能被抓取，哪些页面不能被抓取；可以屏蔽一些网站中比较大的文件，如：图片，音乐，视频等，节省服务器带宽；可以屏蔽站点的一些死链接。方便搜索引擎抓取网站内容；设置网站地图连接，方便引导蜘蛛爬取页面。
### 访问robots.txt
> robots.txt文件应该放置在网站根目录下。
### Writeup
> 访问<a>https://www.wechall.net/robots.txt</a>，根据robots.txt文件中的内容再访问flag链接即可

> flag: /challenge/training/www/robots/T0PS3CR3T