---
title: C语言学习笔记p3
tags:
  - C语言
  - 笔记
  - 字符串处理
categories:
  - 经验
  - C语言经历
index_img: 'https://img-blog.csdnimg.cn/img_convert/550f2c7db0b5edcf7788a0acc35797e4.png'
hide: false
description: 22/4/18更新|字符数组、scanf与gets、pringf与puts、字符串处理函数
comment: twikoo
date: 2022-04-13 23:39:47
sticky: 

---

![](https://img-blog.csdnimg.cn/img_convert/550f2c7db0b5edcf7788a0acc35797e4.png)

# 字符数组
字符数组是数组元素类型为字符的数组，字符数组中的一个元素存放一个字符。
字符数组说明的一般形式是：
```c
Char数组名[常量表达式]
char ch[10]  
char c[10][20]
char ch[10]=['c.p.r.o.g."ra"m)
```
## 案例1
```c
#include "stdio.h"
int main()
{
    char ch[] = "C program";
    printf("%s \n ", ch);
    return 0;
}
```
## 案例2
```c
#include "stdio.h"
int main()
{
    char ch[10] = {'c',' ', 'p', 'r', 'o', 'g', 'r', 'a', 'm'};
    int i;
    for (i = 0; i < 10; i++)
        printf("ch[%d]=%c \n ", i, ch[i]);
}
```
输出
```c
ch[0]=c 
 ch[1]=  
 ch[2]=p 
 ch[3]=r 
 ch[4]=o 
 ch[5]=g 
 ch[6]=r 
 ch[7]=a 
 ch[8]=m 
 ch[9]= 
```
# scanf() 与 gets()

## scanf()

> 1. scanf的功能是将键盘输入的字符串转换成整数、浮点数、字符或字符串。   
> 1. scanf是一个变参函数。   (参数的数量和类型不确定) scanf的第一个参数是字符串。 scanf的第一个参数是需要输入的字符串以及需要被读取的占位符。   
> 1. scanf的后续参数，是依次被读取并赋值的变量地址。 占位符的类型和数量需要与后续的参数类型和数量对应。   
> 1. 如果用scanf ()读取基本变量类型的值，在变量名前加一个&。 如果用scanf ()把字符串去读到字符数组中，不要使用&。   
> 1. 可以发现scanf是printf的逆向过程。 注意，键盘输入的时候，必须要和scanf的第一个参数的字符串对应。
## 案例
```c
///要求：从键盘输入一个人名，并让其显示在屏幕上
#include "stdio.h"
int main()
{
    char name[20]; // name[20] name2[20]
    printf("Enter your name:");
    scanf("%s", name); // tom Ada
    printf("Hello %s!\n", name);
    scanf("%s", name); //读取输入缓冲区中余下的上次未被读走的字符(3.)
    printf("Hello %s!\n", name);
    return 0;
}
```

输出

```c
Enter your name:tom Ada
Hello tom!
Hello Ada!
```
## gets()

> 与scanf（）区别在于gets（）在键入enter时才视为完成一次输入，可以有空格存在，而scanf（）在空格处便识别为完成一次输入[#scanf](# scanf())

### 案例1
```c
///从键盘输入一个人名，并让其显示在屏幕上
#include "stdio.h"
int main()
{
    char name[20];
    printf("Enter your name:");
    gets(name);
    printf("Hello %s!\n", name);
    return 0;
}
```
输出
```c
Enter your name:tom Ada
Hello tom Ada!
```

# printf() 与 puts()

printf( )的一般格式如下：
```c
printf("格式控制字符串",输出表列)；        //输出表列各项用符号,分隔开
```

puts( )函数是把字符串输出到电脑屏幕上并换行。
```c
puts("Hello World!");                            //屏幕打印字符串消息并换行
```



### C语言中的转化字符输出示例

| 转化字符 | 描述   | 输出示例              | 说明               |
| -------- | ------ | --------------------- | ------------------ |
| %d       | 整数   | printf("%d",16);      | 输出整数 16        |
| %f       | 浮点数 | printf("%f",3.14);    | 输出小数 3.140000  |
| %c       | 字符   | printf("%c",'x');     | 输出字符 'x'       |
| %s       | 字符串 | printf("%s","China"); | 输出字符串 "China" |

### C语言常用的转义序列描述

| 转义序列 | 描述                   | 输出示例                           |
| -------- | ---------------------- | ---------------------------------- |
| \n       | 换行                   | printf("第一行 \n 第二行");        |
| \a       | 警报（电脑响铃）       | printf("电脑响铃一次 \a");         |
| \t       | 制表符                 | printf("\t 首行缩进一个制表符位"); |
| \\       | 反斜杠                 | printf("显示两个反斜杠 \\\\");     |
| \"       | 双引号（英文半角字符） | printf("显示双引号 \" 中国 \"!");  |

# 字符串

```c
char word[] = {'H','e','l','L','o','!','\0'}
```

+ 以0（整数0）结尾的一串字符
+ 0或'\0'是一样的，但是和'0'不同
+ 0标志字符串的结束，但它不是字符串的一部分
+ 计算字符串长度的时候不包含这个0
+ 字符串以数组的形式存在，以数组或指针的形式访问
+ 更多的是以指针的形式
+ string.h里有很多处理字符串的函数

|         |      |
| :-----: | ---- |
| word[0] | H    |
| word[1] | e    |
| word[2] | l    |
| word[3] | L    |
| word[4] | o    |
| word[5] | !    |
| word[6] | \0   |

# 字符串处理函数

```c
#include <string.h>
```

### 1. strcpy

原型：`char *strcpy (char * __dest, const char * __src);`
功能：将一个字符串(`__src`)拷贝到另一个字符串缓冲区中(`__dest`)，并返回拷贝后的字符串指针；
例子：

```
#include <stdio.h>
#include <string.h>

int main(){
    const char* str1 = "abcdefg";
    char str2[32];
    strcpy(str2,str1);
    printf("after copy, str2 = %s\n",str2);
    return 0;
}12345678910
```

运行结果：

```
after copy, str2 = abcdefg1
```

注意：

1. 必须保证拷贝后的缓冲区即上例中str2的大小足够，否则造成内存溢出到未分配的地址，容易产生各种未知错误；
2. 由于该函数原理是逐字节复制，所以如果str1和str2的空间有重叠，则会造成覆盖，可以看下面这个例子：

```
#include <stdio.h>
#include <string.h>

int main(){

    char str1[32]="abcdefg";
    strcpy(str1+3,str1);
    printf("after copy, str1 = %s\n",str1);
    return 0;
}12345678910
```

拷贝后的空间和源字符串的空间是有重合的，则源字符串内容会被修改，运行结果为：

```
after copy, str1 = abcabcdefg1
```

### 2. strncpy

原型：`char *strncpy (char * __dest, const char *__src, size_t __n);`
功能：将一个字符串(`__src`)拷贝到另一个字符串缓冲区中(`__dest`)，拷贝**最多不超过**`__n`字节，并返回拷贝后的字符串指针；
例子：

```
#include <stdio.h>
#include <string.h>

int main(){

    const char* str1 = "allen junyu";
    char str2[32]="anything you can write";
    char* p=strncpy(str2,str1,7);
    printf("p=%s\n",p);
    p[7]=0;
    printf("p=%s\n",p);

    return 0;
}1234567891011121314
```

运行结果：

```
p=allen jg you can write
p=allen j12
```

**注意**: strncpy这个函数并不会自动的在字符串结尾加’\0’，需要我们去增加。

### 3. strcat

原型：`char *strcat (char *__dest, const char *__src);`
功能：将一个字符串(`__src`)拼接到另一个字符串缓冲区中(`__dest`)，并返回拼接后的字符串指针；
例子：

```
#include <stdio.h>
#include <string.h>

int main(){
    char str1[32] = "allen";
    const char* str2 = "junyu";
    char* p=strcat(str1,str2);
    printf("p=%s\n",p);
    return 0;
}12345678910
```

运行结果：

```
p=allenjunyu1
```

**注意**：同样地，需要保证str1有足够的存储空间，否则，程序会顺着内存地址往后写，破坏其他内存数据。

### 4. strncat

原型：`char *strncat (char *__dest, const char *__src, size_t __n);`
功能：将一个字符串(`__src`)拼接到另一个字符串缓冲区中(`__dest`)，**最多不超过**`__n`个字节，并返回拼接后的字符串指针；
例子：

```
#include <stdio.h>
#include <string.h>

int main(){
    char str1[32]="allen ";
    const char* str2="junyu";

    strncat(str1,str2,3);
    printf("str1=%s,length=%d\n",str1,strlen(str1));
    strncat(str1,str2,1000000);
    printf("str1=%s,length=%d\n",str1,strlen(str1));

    return 0;
}1234567891011121314
```

运行结果：

```
str1=allen jun,length=9
str1=allen junjunyu,length=1412
```

### 5. strlen

原型：`size_t strlen (const char *__s);`
功能：返回一个字符串(`__src`)的长度，即字节(符)数，这里仅考虑ASCII字符；

### 6. strcmp

原型： `int strcmp (const char *__s1, const char *__s2);`
功能：比较字符串`__s1`和字符串`__s2`，返回比较结果，如果相等，则返回0；
比较方式：两个字符串自左向右逐个字符相比（按ASCII值大小相比较），直到出现不同的字符或遇’\0’为止；
返回结果：当`s1<s2`时，返回值<0；当`s1=s2`时，返回值=0；当`s1>s2`时，返回值>0；
例子：

```
#include <stdio.h>
#include <string.h>

int main(){

    const char* str1 = "allen junyu";
    char str2[32]="allen junyu";
    int ret = strcmp(str1,str2);
    printf("ret=%d\n",ret);

    return 0;
}123456789101112
```

运行结果：

```
ret=01
```

### 7. strncmp

原型： `int strncmp (const char *__s1, const char *__s2, size_t __n);`
功能：比较字符串`__s1`和字符串`__s2`的`__n`个字符，返回比较结果，如果相等，则返回0；
比较方式：同strcmp；
返回结果：同strcmp；
例子：

```
#include <stdio.h>
#include <string.h>

int main(){
    const char* str1 = "allen junyu";
    char str2[32]="allen bob";
    int ret = strncmp(str1,str2,5);
    printf("ret=%d\n",ret);
    return 0;
}12345678910
```

运行结果：

```
ret=01
```

### 8. strcasecmp

原型： `int strcasecmp (const char *__s1, const char *__s2);`
功能：比较字符串`__s1`和字符串`__s2`，忽略大小写的比较，返回比较结果，如果相等，则返回0；
例子：

```
#include <stdio.h>
#include <string.h>

int main(){

    const char* str1 = "allen";
    char str2[32]="AlleN";

    int ret = strcasecmp(str1,str2);
    printf("strcasecmp ret=%d\n",ret);

    return 0;
}12345678910111213
```

运行结果：

```
strcasecmp ret=01
```

### 9. strncasecmp

原型： `int strncasecmp (const char *__s1, const char *__s2, size_t __n);`
功能：比较字符串`__s1`和字符串`__s2`的`__n`个字符，忽略大小写的比较，返回比较结果，如果相等，则返回0；
例子：

```
#include <stdio.h>
#include <string.h>

int main(){

    const char* str1 = "allen";
    char str2[32]="AlleN junyu";

    int ret = strncasecmp(str1,str2,5);
    printf("strncasecmp ret=%d\n",ret);

    return 0;
}12345678910111213
```

运行结果：

```
strncasecmp ret=0
```
### 10. strupr/strlwr

原型：`char *strupr(char *str);`
功能：将字符小写/大写字母转换成大写/小写  
例子：

```c
#include<stdio.h>
#include<string.h>
int main(){
    char str[] = "liegu0317.top";
    printf("%s\n", strlwr(str));
    printf("%s\n", str);
    return  0;
}
```
## 案例 - 字符串-->整型数

```c
//编写一个程序，将一个有数字构成的字符串转换成一个整型数，例：“1234”-->1234
#include"stdio.h"
#include"string.h"
main()
{
    int i,len,sum = 0;
    char ch[100];
    printf("请输入一个数字字符串：\n");
    gets(ch);
    len=strlen(ch);//"1234" len =4
    for(i = 0; i < len; i++)
    {
        sum = sum + (ch[i] - ‘0’)*pow(10 ,( len- 1- i));
        printf("\"%s\"-->j\"%d\"\n",ch,sum)
    }
    return 0;
}
```