---
title: type(), dtype(), astype()的区别|Python点点
tags:
  - Python
  - type
  - dtype
  - astype
categories:
  - 经验
  - Python点点
hide: false
description: 
comment: twikoo
date: 2021-12-22 20:47:45
index_img: https://github.com/LIEGU0317/img/raw/master/Blogimg/202112222052316.png

---

![](https://github.com/LIEGU0317/img/raw/master/Blogimg/202112222052135.png)



| 函数 | 说明 |
| ---- | :--- |
| type() | 返回数据结构类型（list、dict、numpy.ndarray 等） |
|dtype()|返回数据元素的数据类型（int、float等）<br />备注：1）由于 list、dict 等可以包含不同的数据类型，因此不可调用dtype()函数<br />2）np.array 中要求所有元素属于同一数据类型，因此可调用dtype()函数|
|astype()|改变np.array中所有数据元素的数据类型。<br />备注：能用dtype() 才能用 astype()|





