---
layout: post
title:  "CTF-Wechall-Prime-Factory"
date:   2021-03-19 01:16:13 +0000
categories: CTF
tags: 2021-03 CTF 素数
comments: 0
---
### 知识点  
> 素性检验:
- 试除法: <a href="https://zh.wikipedia.org/wiki/%E8%AF%95%E9%99%A4%E6%B3%95" target="view_window">https://zh.wikipedia.org/wiki/试除法</a>
- 费马素性检验: <a href="https://zh.wikipedia.org/wiki/%E8%B4%B9%E9%A9%AC%E7%B4%A0%E6%80%A7%E6%A3%80%E9%AA%8C" target="view_window">https://zh.wikipedia.org/wiki/费马素性检验</a>
- AKS素性测试: <a href="https://zh.wikipedia.org/wiki/AKS%E8%B3%AA%E6%95%B8%E6%B8%AC%E8%A9%A6" target="view_window">https://zh.wikipedia.org/wiki/AKS素性测试</a>
- Miller-Rabin素性检验: <a href="https://zh.wikipedia.org/wiki/%E7%B1%B3%E5%8B%92-%E6%8B%89%E5%AE%BE%E6%A3%80%E9%AA%8C" target="view_window">https://zh.wikipedia.org/wiki/Miller-Rabin素性检验</a>


### Writeup  
> 使用试除法计算大于1000000的奇数中，前两个本身既是素数，各位数字之和也为素数的数

> flag: 10000331000037   

### Code/Command
```python
from math import sqrt

# Trial division
def isPrime(n):
    if n % 2 == 0:
        return False

    for i in range(3, int(sqrt(n)) + 1, 2):
        if n % i == 0:
            return False

    return True

# Calculate the sum of each digit of positive n
def sumDigits(n):
    if n < 0:
        raise Exception('n cannot be a negetive number. n: {}'.format(n))

    sum = 0
    tempN = n
    while tempN > 0:
        sum += tempN % 10
        tempN = int(tempN / 10)

    return sum

def getFlag():
    n = 1000001
    specialPrimeList = []
    count = 0
    while count < 2:
        if isPrime(n) and isPrime(sumDigits(n)):
            count += 1
            specialPrimeList.append(str(n))
        
        n += 2

    return ''.join(specialPrimeList)

print(getFlag())
```