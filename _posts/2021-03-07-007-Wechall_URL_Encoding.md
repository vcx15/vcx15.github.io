---
layout: post
title:  "CTF-Wechall-URL_Encoding"
date:   2021-03-07 16:53:00 +0000
categories: CTF
tags: 2021-03 CTF WEB
comments: 0
---
### 知识点  
> 百分号编码（英语：Percent-encoding），又称：URL编码（URL encoding）是特定上下文的统一资源定位符 （URL）的编码机制，实际上也适用于统一资源标志符（URI）的编码。也用于为 application/x-www-form-urlencoded MIME准备数据，因为它用于通过HTTP的请求操作（request）提交HTML表单数据。  
Ref: <a href="https://zh.wikipedia.org/wiki/%E7%99%BE%E5%88%86%E5%8F%B7%E7%BC%96%E7%A0%81" target="view_window">https://zh.wikipedia.org/wiki/百分号编码</a>

### Writeup  
> 将百分号编码列表转换为字母列表，结果：Yippeh! Your URL is challenge/training/encodings/url/saw_lotion.php?p=cboamsoeemip&cid=52#password=fibre_optics Very well done!

> flag: 访问<a href="https://www.wechall.net/challenge/training/encodings/url/saw_lotion.php?p=cboamsoeemip&cid=52#password=fibre_optics" target="view_window">https://www.wechall.net/challenge/training/encodings/url/saw_lotion.php?p=cboamsoeemip&cid=52#password=fibre_optics</a>

### Code/Command  

```python
from urllib.parse import unquote

quoteStr = '''%59%69%70%70%65%68%21%20%59%6F%75%72%20%55%52%4C%20%69%73%20%63%68%61%6C%6C%65%6E%67%65%2F%74%72%61%69%6E%69%6E%67%2F%65%6E%63%6F%64%69%6E%67%73%2F%75%72%6C%2F%73%61%77%5F%6C%6F%74%69%6F%6E%2E%70%68%70%3F%70%3D%63%62%6F%61%6D%73%6F%65%65%6D%69%70%26%63%69%64%3D%35%32%23%70%61%73%73%77%6F%72%64%3D%66%69%62%72%65%5F%6F%70%74%69%63%73%20%56%65%72%79%20%77%65%6C%6C%20%64%6F%6E%65%21'''
print(unquote(quoteStr))
```