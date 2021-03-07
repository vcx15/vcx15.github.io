---
layout: post
title:  "CTF-Wechall-ASCII"
date:   2021-03-07 16:33:13 +0000
categories: CTF
tags: 2021-03 CTF ASCII
comments: 0
---
### 知识点  
> ASCII码: ASCII是基于拉丁字母的一套电脑编码系统。它主要用于显示现代英语，而其扩展版本延伸美国标准信息交换码则可以部分支持其他西欧语言，并等同于国际标准ISO/IEC 646。
<a href="https://zh.wikipedia.org/wiki/ASCII" target="view_window">https://zh.wikipedia.org/wiki/ASCII</a>

### Writeup  
> 将数字列表转换为ASCII码字母列表，结果：The solution is: semfiifidfis

> flag: semfiifidfis  

### Code/Command  

```python
ascNumList = [84, 104, 101, 32, 115, 111, 108, 117, 116, 105, 111, 110, 32, 105, 115, 58, 32, 115, 101, 109, 102, 105, 105, 102, 105, 100, 102, 105, 115]
ascLetterList = []

for num in ascNumList:
    ascLetterList.append(chr(num))

print(''.join(ascLetterList))
```