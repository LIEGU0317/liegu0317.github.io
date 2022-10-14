---
title: 生成随机数|Python点点
tags:
  - 随机数
  - Python
  - Numpy
categories:
  - 经验
  - Python点点
hide: false
description: 使用random模块生成随机数组；使用numpy.random模块来生成随机数组
comment: twikoo
date: 2021-12-24 07:55:31
index_img: https://github.com/LIEGU0317/img/raw/master/Blogimg/202112222052316.png 

---

<img src="https://github.com/LIEGU0317/img/raw/master/Blogimg/202112222052316.png"  />



# **一、使用random模块生成随机数组**

<img src="https://github.com/LIEGU0317/img/raw/master/Blogimg/202112242105953.jpeg" alt="python 生成随机数模块random 常用方法总结" style="zoom:80%;" />

python的random模块中有一些生成随机数字的方法，例如random.randint， random.random, random.uniform, random.randrange,这些函数大同小异，均是在返回指定范围内的一个整数或浮点数，下边简单解释一下这几个函数。

## 1、random.randint(low, hight) -> 返回一个位于[low,hight]之间的*整数*
该函数接受两个参数，这两个参数必须是整数（或者小数位是0的浮点数），并且第一个参数必须不大于第二个参数

```
random.randint
import random
random.randint(1,10)
6
random.randint(1.0, 10.0)
1
```

##  2、random.random() -> 不接受参数，返回一个[0.0, 1.0)之间的*浮点数*
```
random.random()
0.227730775007011
```
## 3、random.uniform(val1, val2) -> 接受两个数字参数，返回两个数字区间的一个*浮点数*，不要求val1小于等于val2
```random.uniform(1,5.0)
random.uniform(9.9, 2)
5.189511116007191
```
## 4、random.randrange(start, stop, step) -> 返回以start开始，stop结束，step为步长的列表中的随机*整数*，同样，三个参数均为*整数（或者小数位为0）*，若start大于stop时 ，setp必须为负数.step不能是0.
```
random.randrange(1, 100, 2)  #返回[1,100]之间的奇数
random.ranrange(100, 1, -2)  #返回[100,1]之间的偶数
2
```

## 5、生成随机数组
下边我们用random.randint来生成一个随机数组

```
import random
def random_int_list(start, stop, length):
    start, stop = (int(start), int(stop)) if start <= stop else (int(stop), int(start))
    length = int(abs(length)) if length else 0
    random_list = []
    for i in range(length):
        random_list.append(random.randint(start, stop))
    return random_list
```

接下来我们就可以用这个函数来生成一个随机的整数序列了

```
random_int_list(1,100,10)
random_int_list(1,100,10)
[54, 13, 6, 89, 87, 39, 60, 2, 63, 61]
```

# **二、使用numpy.random模块来生成随机数组**

![NumPy_logo_2020](https://github.com/LIEGU0317/img/raw/master/Blogimg/202112242135274.svg)

## 1、np.random.rand 用于生成[0.0, 1.0)之间的随机*浮点数*， 当没有参数时，返回一个随机浮点数，当有一个参数时，返回该参数长度大小的一维随机*浮点数数组*，参数建议是*整数型*，因为现有新版的numpy不再支持非整形参数。
```
import numpy as np
import numpy as np
np.random.rand(10)
array([ 0.56911206,  0.99777291,  0.18943144,  0.19387287,  0.75090637,
0.18692814,  0.69804514,  0.48808425,  0.79440667,  0.66959075])
```
当然该函数还可以用于生成多维数组，这里不做详述。


## 2、np.random.randn该函数返回一个样本，具有标准正态分布。
```
np.random.randn(10)
np.random.randn(10)
array([-1.6765704 ,  0.66361856,  0.04029481,  1.19965741, -0.57514593,
-0.79603968,  1.52261545, -2.17401814,  0.86671727, -1.17945975])
```

## 3、np.random.randint(low[, high, size]) 返回随机的整数，位于半开区间 [low, high)。
```
np.random.randint(10,size=10)
np.random.randint(10,size=10)
array([4, 1, 4, 3, 8, 2, 8, 5, 8, 9])
```

## 4、random_integers(low[, high, size]) 返回随机的整数，位于闭区间 [low, high]。
```
np.random.random_integers(5)
np.random.random_integers(5)
4
```

## 5、np.random.shuffle(x) 类似洗牌，打乱顺序；np.random.permutation(x)返回一个随机排列
```
arr = np.arange(10)
arr = np.arange(10)
np.random.shuffle(arr)
arr
[1 7 5 2 9 4 3 6 0 8]

np.random.permutation(10)
array([1, 7, 4, 3, 0, 9, 2, 5, 8, 6])
```



# 参考文献

- [python numpy.random生成随机数组](https://blog.csdn.net/Scarlett_ma/article/details/79173632)

+ [python生成随机数组](https://blog.csdn.net/healthy_coder/article/details/50502643)
