---
layout: post
title:  "CTF-Wechall_Encoding_I"
date:   2021-03-19 23:16:13 +0000
categories: CTF
tags: 2021-03 CTF ASCII
comments: 0
---
---
layout: post
title:  "CTF-Wechall_Programming1"
date:   2021-03-20 16:58 +0000
categories: CTF
tags: 2021-03 CTF WEB
comments: 0
---
### 知识点  
> WEB http访问


### Writeup  
> 使用urllib3工具进行http访问，获取request link的结果，再将结果拼接到answer link上后访问answer link

> flag: W5rPycBUbSTV(每次访问后会变动)  

### Code/Command
```python
import urllib3

url = 'https://www.wechall.net/challenge/training/programming1/index.php'
method = 'GET'
headers = {'Cookie': 'WC=13283134-32518-dErAYNK3u4Ny5Qlb'}
filedsRequest = {'action': 'request'}

http = urllib3.PoolManager()
r = http.request(method, url, filedsRequest, headers)

filedsAnswer = {'answer': r.data.decode('utf-8')}
ra = http.request(method, url, filedsAnswer, headers)
```