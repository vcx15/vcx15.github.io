---
layout: post
title:  "CTF-Wechall_Encoding_I"
date:   2021-03-19 23:16:13 +0000
categories: CTF
tags: 2021-03 CTF ASCII
comments: 0
---
### 知识点  
> ASCII码


### Writeup  
> 将01字符串7个为一组组成ASCII码的7位二进制编码，解码成ASCII字符后即可
- This text is 7-bit encoded ascii. Your password is easystarter.

> flag: easystarter   

### Code/Command
```python
def decode(binStr):
    start = 0
    result = ''
    while start < len(binStr):
        char = chr(int(binStr[start : start + 7], 2)) if start + 7 <= len(binStr) else chr(int(binStr[start:], 2))
        result += char
        start = start + 7

    return result

binStr = '10101001101000110100111100110100\
00011101001100101111100011101000\
10000011010011110011010000001101\
11010110111000101101001111010001\
00000110010111011101100011110111\
11100100110010111001000100000110\
00011110011110001111010011101001\
01011100100000101100111011111110\
10111100100100000111000011000011\
11001111100111110111110111111100\
10110010001000001101001111001101\
00000110010111000011110011111100\
11110011111010011000011110010111\
0100110010111100100101110'

print(decode(binStr))
```