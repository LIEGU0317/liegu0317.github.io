---
title: C语言学习笔记P2|7-10课
tags:
  - C语言
  - 笔记
categories:
  - 经验
  - C语言经历
index_img: 'https://img-blog.csdnimg.cn/img_convert/550f2c7db0b5edcf7788a0acc35797e4.png'
hide: false
sticky: 
description: C语言课程同步笔记
comment: twikoo
date: 2022-03-18 08:31:56
---

![](https://img-blog.csdnimg.cn/img_convert/550f2c7db0b5edcf7788a0acc35797e4.png)

[点击此处跳转至最近更新](#最新更新)

# 第七课



## printf使用
> printf函数称为格式输出函数，其关键字最末一个字母f即为“格式”(format)之意。其功能是按用户指定的格式，把指定的数据显示到显示器屏幕上。  
* [C语言格式输出函数printf()详解](http://c.biancheng.net/cpp/html/33.html)
  
|一语句，两个参数，三个选项|格式控制|操作对象列表|
|:-----|:-----|:-----|
|printf("格式控制",输出列表);<br>功能：按照“格式控制”格式输出一个或多个任意数据|1 格式字符；<br>2 有提示串原样输出；<br>3 转义字符用于输出操作行为，如退格、换行、回车|可以是常量，变量，表达式，其个数与格式控制参数中的格式字符数相同|
|scanf("格式控制",地址列表);<br>功能：按照“格式控制”格式从键盘接收若干个数据，依次存入“地址列表“对应的变量|1 格式字符<br>2 有提示串，则输入数据时原样输入；<br>3 输入数据可用空格、回车和跳格键Tab作为间隔|是变量的地址而不是变量|


## [1. **局部变量与全局变量**](http://c.biancheng.net/view/1858.html)
> 在《C语言形参和实参的区别》中提到，形参变量要等到函数被调用时才分配内存，调用结束后立即释放内存。这说明形参变量的作用域非常有限，只能在函数内部使用，离开该函数就无效了。所谓作用域（Scope），就是变量的有效范围。

> 不仅对于形参变量，C语言中所有的变量都有自己的作用域。决定变量作用域的是变量的定义位置。

> 自定义函数和主函数中变量不相干扰，可以使用相同字符


### 案例-jiojio表

```
#include"stdio.h"
void main()
{
	int m, n;
	for (m = 1; m < 10; m++)
	{
		for (n = 1; n <= m; n++)
			printf("%d*%d=%d ", m, n, m * n);
		printf("\n");
	}printf("\n");
}
```
### 案例_2

```c
#include <stdio.h>
int a = 100, b = 10; //外部变量
int main()           //变量的定义在所有函数外部
{
    int a = 1, c;
    c = a + b;
    printf("%d,", c);
    {
        int a = 2, b = 2; //内部变量
        c = a + b;        //变量的定义在函数内部或复合语句内部
        printf("%d,", c);
    }
    printf("%d\n", a + b); // 11,4,11
}
```
### 案例_auto

```c
#include <stdio.h>
int f(int a)
{
    auto int b = 0;   /*自动，auto可省*/
    static int c = 3; /*静态，值保留*/
    b++;
    c++;
    return (a + b + c);
}
int main()
{
    int a = 2, l;
    for (l = 0; l < 3; l++)
        printf("%d", f(a));
}
```


# 第八课

## [函数的调用过程](https://liegu0317.github.io/2022/02/28/C%E8%AF%AD%E8%A8%80%E5%AD%A6%E4%B9%A0%E7%AC%94%E8%AE%B0-%E9%95%BF%E6%9C%9F%E6%9B%B4%E6%96%B0/#%E5%87%BD%E6%95%B0%E7%9A%84%E8%B0%83%E7%94%A8%E8%BF%87%E7%A8%8Bv)

## 变量的存储属性
```c
#include <stdio.h>
int f(int a);//首先声明函数
int main()
{
    int a = 2, i;
    /*自动,默认auto*/
    for (i = 1; i <= 3; i++)
        printf("%d ", f(a));
}

int f(int a)
{
    auto int b = 0;   /*自动,auto可省*/
    static int c = 3; /*静态，值保留*/
    //做一次定义，c对应的存储单元一直存在
    b++;
    c++;
    return (a + b + c);
}
```


![](https://github.com/LIEGU0317/img/raw/master/Blogimg/202203161644389.png)

## 递归调用-小循环

### 求n的递推公式
```mathematica
a(n) = n*a(n-1)(n>1)
```
【n为1或0时值为1】
```c
int f(int n)
{
int v;
if(n == 0 || n == 1)v = 1;
    else v = n*f(n-1);//直接或间接调用自己
    return(v);
}
```

# 一维数组

## 定义

+ 迄今为止，使用的变主都是单一的变量，相互之间没有联系，这样的变旦又叫离散性变量。当需要大量相同数据类型的变量时，必然想到变量的组合，数组就是这样一种结构。

+ 数组是具有相同数据类型的元素所组成的有序集合，而每1个数组元素就是1个类型相同的变量。每个数组是用1个统一的名称表示数组元素的集合，数组中的每一元素具有惟一索引号（即下标），可以用数组名及下标惟一地识别1个数组元素，下标的个数决定数练的维数，1个下标的数组称为一维数组，两个下标的数组称为二维数组。

## 数组的创建

+ 数组是一种容器（放东西的东西），特点是：所有的元素具有相同的数据类型。

+ 数组的声明并不是声明一个个单独的变量，比如 runoob0、runoob1、…、runoob99，而是声明一个数组变量，比如 runoob，然后使用 runoob[0]、runoob[1]、、...、runoob[99]来代表一个个单独的变量。(下表索引)

+ 在 C �����要声明一个数组，需要指定元素的类型和元素的数量，一旦声明后续不可更改，如下所示：

+ <类型> 变量名称[元素数量]; int runoob[100]; double balance [10]

+ 所有的数组都是由连续的内存位置组成。最低的地址对应第一个元素，最高的地址对应最后一个元素。

```c
int runoob[3]={223,666,888};
```

## 数组的输出

### 下标、索引

**规定下标从0开始  0,1,2,3,4...**

[0]代表第一个元素

```c
printf(plants[0])
```

+ 定义数组后元素数小于数组容量，自动补0

## 输入月份返回天数

```c
#inclue"studio.h"
int getmonthdays(int month,int year);
main()
{
    int days;
    days = getmonthdays(3,2022);
    printf("总共天数",days);
}
```

```c
//输入一个月份，返回这个月天数
int gatmonthdays(int month,int year)
{
    int days_arry[12] = {31,28,31,30,31,30,31,31,30,31,30,31}
    return days_arry[month - 1]
}
```

# 二维数组

## 二维数组一般形式

<类型> 变量名称[常量表达式1(行数)]\[常量表达式2(列数)]

```int a[6][6]   double b[6][3]```

## 二维数组的访问

```数组名[下标][下标] ```

```int a[3][3]  0-2 0-4```

> C语言**下标越界**无警告，输出垃圾值

### 遍历

```c
#include <stdio.h>
int main()
{
    int a[3][4] = {{1}, {5}, {9}};
    int i, j;
    for (i = 0; i <= 3; i++)
    {
        for (j = 0; j <= 4; j++)
        {
            printf("%5d", a[i][j]);
        }
        printf("\n");
    }
}
```



## 二维数组的初始化

1. ```c
   int a[3]\[4]={1,2,3,4,5,6,7,8,9,10,11,12};
   ```

2. ```c
   int b[3]\[4]={{1,2,3,4},{5,6,7,8},{9,10,11,12}};
   ```

3. ```cint b[3][4]=
      {
          {1,2,3,4},
          {5,6,7,8},
          {9,10,11,12}
      };
      
   ```

4. ```c
   int d[3]\[4]={{1},{5},{9}};
   ```

> 结果
>
> ```c
> 	1    0    0    0    5
> 	5    0    0    0    9
> 	9    0    0    0686177312
> ```
>

5. ```c
   int e[][4] = {1,2,3,4,5,6,7,8,9,10,11,12}
   ```

自动识别为  `e[3][4]`

## 案例
```c
#include"stdio.h"
main()
{
	int a[4][4] = { {12,76,4,1},{-19,28,55,-6},{2,10,13,-2},{3,-9,112,111} };
	int i,j,min,row = 0,column = 0;
	min = a[0][0];
	for (i = 0; i < 4; i++)
	{
		for (j = 0; j < 4; j++)
		{
			printf("%5d", a[i][j]);
			if (a[i][j] < min) {
				min = a[i][j];
				row = i;
				column = j;
			}
		}
		printf("\n");
	}
	printf("最小值=%d，位于矩阵第%d行，第%d列", min, row + 1, column + 1);
	return 0;
}
```
## 经典案例1 - 矩阵的转置

![矩阵的转置](https://img-blog.csdnimg.cn/9c93f39b6d5d4a93abbf97a72ae2868c.png#pic_center)

```c
a[0][j] ---→ b[j][0]
```



```c
// 经典案例1 - 矩阵的转置
#include"stdio.h"
main()
{
	int a[2][3], b[3][2];
	int j, i;
	printf("请输入A矩阵元素，一个元素一个回车\n");
	for (i = 0; i <= 1; i++)
	{
		for (j = 0; j <= 2; j++)
		{
			scanf_s("%d", &a[i][j]);
		};
	}
	printf("A矩阵：\n");
	for (i = 0; i <= 1; i++)
	{
		for (j = 0; j <= 2; j++)
		{
			printf("%d ",a[i][j]); //输出矩阵
			b[j][i] = a[i][j];  //矩阵A转置给B
		};
		printf("\n");
	}
	printf("B矩阵：\n");
	for (i = 0; i < 3; i++)
	{
		for (j = 0; j < 2; j++)
			printf("%5d", b[i][j]);
		printf("\n");
	}return 0;
}
```

## 经典案例1 - 成绩均值计算

![成绩均值计算](https://img-blog.csdnimg.cn/e22d38a8d5304cadaf7fb5ac4a61b871.png#pic_center)

```c
#include "stdio.h"
main()
{
    int i, j, score[5][3], sum, aver[5];

    printf("请依次输入每名同学的各科成绩：");
    for (i = 0; i < 5; i++) // if代表的是学生的序号：
    {
        sum = 0;                //在每名同学成锁输入前，让其总成锁赋初值为0
        for (j = 0; j < 3; j++) // J理解为课程
        {
            scanf("%d", &score[i][j]); //输入第i号学生第j门成绩
            sum += score[i][j];
        }
    }
    return 0;
}
```

# 第九课-我划水了

> 无

# 第十课-优先级与结合性

## 案例

```c
int a= 5;
a-=a+=a;
```

## [C语言中文网](http://c.biancheng.net/cpp/html/462.html)

<div id="art-body">C语言的运算符众多，具有不同的优先级和结合性，我们将它们全部列了出来，方便大家对比和记忆：
<table>
<tbody>
<tr>
<th>
<p>
优先级</p>
</th>
<th>
<p>
运算符</p>
</th>
<th>
<p>
名称或含义</p>
</th>
<th>
<p>
使用形式</p>
</th>
<th>
<p>
结合方向</p>
</th>
<th>
<p>
说明</p>
</th>
</tr>
<tr>
<td rowspan="4">
<p>
1</p>
</td>
<td>
<p>
[]</p>
</td>
<td>
<p>
数组下标</p>
</td>
<td>
<p>
数组名[常量表达式]</p>
</td>
<td rowspan="4">
<p>
左到右</p>
</td>
<td>
 </td>
</tr>
<tr>
<td>
<p>
()</p>
</td>
<td>
<p>
圆括号</p>
</td>
<td>
<p>
（表达式）/函数名(形参表)</p>
</td>
<td>
 </td>
</tr>
<tr>
<td>
<p>
.</p>
</td>
<td>
<p>
成员选择（对象）</p>
</td>
<td>
<p>
对象.成员名</p>
</td>
<td>
 </td>
</tr>
<tr>
<td>
<p>
-></p>
</td>
<td>
<p>
成员选择（指针）</p>
</td>
<td>
<p>
对象指针->成员名</p>
</td>
<td>
 </td>
</tr>
<tr>
<td rowspan="9">
<p>
2</p>
</td>
<td>
<p>
-</p>
</td>
<td>
<p>
负号运算符</p>
</td>
<td>
<p>
-表达式</p>
</td>
<td rowspan="9">
<p>
右到左</p>
</td>
<td>
<p>
单目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
(类型)</p>
</td>
<td>
<p>
强制类型转换</p>
</td>
<td>
<p>
(数据类型)表达式</p>
</td>
<td>
 </td>
</tr>
<tr>
<td>
<p>
++</p>
</td>
<td>
<p>
自增运算符</p>
</td>
<td>
<p>
++变量名/变量名++</p>
</td>
<td>
<p>
单目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
--</p>
</td>
<td>
<p>
自减运算符</p>
</td>
<td>
<p>
--变量名/变量名--</p>
</td>
<td>
<p>
单目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
*</p>
</td>
<td>
<p>
取值运算符</p>
</td>
<td>
<p>
*指针变量</p>
</td>
<td>
<p>
单目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
&</p>
</td>
<td>
<p>
取地址运算符</p>
</td>
<td>
<p>
&变量名</p>
</td>
<td>
<p>
单目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
!</p>
</td>
<td>
<p>
逻辑非运算符</p>
</td>
<td>
<p>
!表达式</p>
</td>
<td>
<p>
单目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
~</p>
</td>
<td>
<p>
按位取反运算符</p>
</td>
<td>
<p>
~表达式</p>
</td>
<td>
<p>
单目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
sizeof</p>
</td>
<td>
<p>
长度运算符</p>
</td>
<td>
<p>
sizeof(表达式)</p>
</td>
<td>
 </td>
</tr>
<tr>
<td rowspan="3">
<p>
3</p>
</td>
<td>
<p>
/</p>
</td>
<td>
<p>
除</p>
</td>
<td>
<p>
表达式/表达式</p>
</td>
<td rowspan="3">
<p>
左到右</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
*</p>
</td>
<td>
<p>
乘</p>
</td>
<td>
<p>
表达式*表达式</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
%</p>
</td>
<td>
<p>
余数（取模）</p>
</td>
<td>
<p>
整型表达式/整型表达式</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td rowspan="2">
<p>
4</p>
</td>
<td>
<p>
+</p>
</td>
<td>
<p>
加</p>
</td>
<td>
<p>
表达式+表达式</p>
</td>
<td rowspan="2">
<p>
左到右</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
-</p>
</td>
<td>
<p>
减</p>
</td>
<td>
<p>
表达式-表达式</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td rowspan="2">
<p>
5</p>
</td>
<td>
<p>
<<</p>
</td>
<td>
<p>
左移</p>
</td>
<td>
<p>
变量<<表达式</p>
</td>
<td rowspan="2">
<p>
左到右</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
>></p>
</td>
<td>
<p>
右移</p>
</td>
<td>
<p>
变量>>表达式</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td rowspan="4">
<p>
6</p>
</td>
<td>
<p>
></p>
</td>
<td>
<p>
大于</p>
</td>
<td>
<p>
表达式>表达式</p>
</td>
<td rowspan="4">
<p>
左到右</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
>=</p>
</td>
<td>
<p>
大于等于</p>
</td>
<td>
<p>
表达式>=表达式</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
<</p>
</td>
<td>
<p>
小于</p>
</td>
<td>
<p>
表达式<表达式</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
<=</p>
</td>
<td>
<p>
小于等于</p>
</td>
<td>
<p>
表达式<=表达式</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td rowspan="2">
<p>
7</p>
</td>
<td>
<p>
==</p>
</td>
<td>
<p>
等于</p>
</td>
<td>
<p>
表达式==表达式</p>
</td>
<td rowspan="2">
<p>
左到右</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
!=</p>
</td>
<td>
<p>
不等于</p>
</td>
<td>
<p>
表达式!= 表达式</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
8</p>
</td>
<td>
<p>
&</p>
</td>
<td>
<p>
按位与</p>
</td>
<td>
<p>
表达式&表达式</p>
</td>
<td>
<p>
左到右</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
9</p>
</td>
<td>
<p>
^</p>
</td>
<td>
<p>
按位异或</p>
</td>
<td>
<p>
表达式^表达式</p>
</td>
<td>
<p>
左到右</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
10</p>
</td>
<td>
<p>
|</p>
</td>
<td>
<p>
按位或</p>
</td>
<td>
<p>
表达式|表达式</p>
</td>
<td>
<p>
左到右</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
11</p>
</td>
<td>
<p>
&&</p>
</td>
<td>
<p>
逻辑与</p>
</td>
<td>
<p>
表达式&&表达式</p>
</td>
<td>
<p>
左到右</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
12</p>
</td>
<td>
<p>
||</p>
</td>
<td>
<p>
逻辑或</p>
</td>
<td>
<p>
表达式||表达式</p>
</td>
<td>
<p>
左到右</p>
</td>
<td>
<p>
双目运算符</p>
</td>
</tr>
<tr>
<td>
<p>
13</p>
</td>
<td>
<p>
?:</p>
</td>
<td>
<p>
条件运算符</p>
</td>
<td>
<p>
表达式1? 表达式2: 表达式3</p>
</td>
<td>
<p>
右到左</p>
</td>
<td>
<p>
三目运算符</p>
</td>
</tr>
<tr>
<td rowspan="11">
<p>
14</p>
</td>
<td>
<p>
=</p>
</td>
<td>
<p>
赋值运算符</p>
</td>
<td>
<p>
变量=表达式</p>
</td>
<td rowspan="11">
<p>
右到左</p>
</td>
<td>
 </td>
</tr>
<tr>
<td>
<p>
/=</p>
</td>
<td>
<p>
除后赋值</p>
</td>
<td>
<p>
变量/=表达式</p>
</td>
<td>
 </td>
</tr>
<tr>
<td>
<p>
*=</p>
</td>
<td>
<p>
乘后赋值</p>
</td>
<td>
<p>
变量*=表达式</p>
</td>
<td>
 </td>
</tr>
<tr>
<td>
<p>
%=</p>
</td>
<td>
<p>
取模后赋值</p>
</td>
<td>
<p>
变量%=表达式</p>
</td>
<td>
 </td>
</tr>
<tr>
<td>
<p>
+=</p>
</td>
<td>
<p>
加后赋值</p>
</td>
<td>
<p>
变量+=表达式</p>
</td>
<td>
 </td>
</tr>
<tr>
<td>
<p>
-=</p>
</td>
<td>
<p>
减后赋值</p>
</td>
<td>
<p>
变量-=表达式</p>
</td>
<td>
 </td>
</tr>
<tr>
<td>
<p>
<<=</p>
</td>
<td>
<p>
左移后赋值</p>
</td>
<td>
<p>
变量<<=表达式</p>
</td>
<td>
 </td>
</tr>
<tr>
<td>
<p>
>>=</p>
</td>
<td>
<p>
右移后赋值</p>
</td>
<td>
<p>
变量>>=表达式</p>
</td>
<td>
 </td>
</tr>
<tr>
<td>
<p>
&=</p>
</td>
<td>
<p>
按位与后赋值</p>
</td>
<td>
<p>
变量&=表达式</p>
</td>
<td>
 </td>
</tr>
<tr>
<td>
<p>
^=</p>
</td>
<td>
<p>
按位异或后赋值</p>
</td>
<td>
<p>
变量^=表达式</p>
</td>
<td>
 </td>
</tr>
<tr>
<td>
<p>
|=</p>
</td>
<td>
<p>
按位或后赋值</p>
</td>
<td>
<p>
变量|=表达式</p>
</td>
<td>
 </td>
</tr>
<tr>
<td>
<p>
15</p>
</td>
<td>
<p>
,</p>
</td>
<td>
<p>
逗号运算符</p>
</td>
<td>
<p>
表达式,表达式,…</p>
</td>
<td>
<p>
左到右</p>
</td>
<td>
<p>
从左向右顺序运算</p>
</td>
</tr>
</tbody>
</table>
<br>
<span style="color:#a52a2a;">注：同一优先级的运算符，运算次序由结合方向所决定。</span><br>
<br>
上面的表无需死记硬背，很多运算符的规则和数学中是相同的，用得多，看得多自然就记得了。如果你是在记不住，可以使用( )。<br>
<h2>
一些容易出错的优先级问题</h2>
上表中，优先级同为1 的几种运算符如果同时出现，那怎么确定表达式的优先级呢？这是很多初学者迷糊的地方。下表就整理了这些容易出错的情况：
<div style="text-align: center; ">
<img alt="" src="http://c.biancheng.net/cpp/uploads/allimg/120205/1-120205192420113.jpg" style="width: 500px; height: 318px; "></div>
这些容易出错的情况，希望读者好好在编译器上调试调试，这样印象会深一些。一定要多调试，光靠看代码，水平是很难提上来的。调试代码才是最长水平的。</div>

# 参考资料

http://c.biancheng.net/cpp/html/33.html