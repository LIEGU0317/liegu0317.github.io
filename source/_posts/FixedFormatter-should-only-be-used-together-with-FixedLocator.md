---
title: 解决警告 FixedFormatter should only be used together with FixedLocator|Python点点
tags:
  - Python
  - Python3.9.7
  - 代码警告
categories:
  - 经验
  - Python点点
index_img: 'https://github.com/LIEGU0317/img/raw/master/Blogimg/202112222052316.png'
hide: false
description:  UserWarning：FixedFormatter should only be used together with FixedLocator，Python3.9.7
comment: twikoo
date: 2022-02-28 16:43:51
---

![](https://github.com/LIEGU0317/img/raw/master/Blogimg/202112222052316.png)

# 警告内容
当我在给柱状图 添加 x轴标签 时出现了此警告
```python
 UserWarning: FixedFormatter should only be used together with FixedLocator
```
> FixedFormatter(标签数据)只能和FixedLocator(定位器）一起使用

# 运行环境
操作系统：`win11 专业版 21H2`
Python版本：`Python 3.9.7（anaconda）`

# 警告代码（截取）

```python
data = pd.DataFrame(np.random.rand(30,2)*100,
                   columns = ['A_sale','B_sale'],
                   index = pd.period_range('20020317', periods = 30))# 创建模拟数据
x = range(len(data))
y = data["A_sale"] - data['B_sale']

fig = plt.figure(figsize = (20,6)) # 创建图形
plt.subplots_adjust(hspace = 0.3) # 调节水平间距
ax = fig.add_subplot(2,1,2) # 创建子图
plt.plot(x,y,'--go') # 填充子图

ax.set_xtichlabels(data.nadex[0:0:5]) # 将时间戳作为x轴标签
```
# 警告原因
未将FixedFormatter(标签数据)只能和FixedLocator(定位器）一起使用，通俗点讲   就是**即将添加的标签无法找到对应的位置。**这会导致添加的标签出现在非预想的位置

## [matplotlib官网中写到](https://matplotlib.org/3.5.1/api/_as_gen/matplotlib.axes.Axes.set_xticklabels.html)：
> 原文：This method should only be used after fixing the tick positions using Axes.set_xticks. Otherwise, the labels may end up in unexpected positions.

> 翻译：该方法只能在使用axis .set_xticks固定刻度位置之后使用。否则，标签可能会出现在意想不到的位置。

# 解决方案
*由于初学Python对工具认知较浅，加上英语水平极差，我并未在第一时间读透彻官方文档的意思。这使我浪费了很多时间去浏览些对我帮助不大的的文章*

按照matplotlib官方文档所述：
1. 使用axis .set_xticks固定刻度位置  ```ax.set_xticks(x[::5])```
2. 进行标签修改/添加的操作  ```ax.set_xtichlabels(data.nadex[0:0:5])```

# 修改后代码

```python
data = pd.DataFrame(np.random.rand(30,2)*100,
                   columns = ['A_sale','B_sale'],
                   index = pd.period_range('20020317', periods = 30))# 创建模拟数据
x = range(len(data))
y = data["A_sale"] - data['B_sale']
fig = plt.figure(figsize = (20,6)) # 创建图形
plt.subplots_adjust(hspace = 0.3) # 调节水平间距
ax = fig.add_subplot(2,1,2) # 创建子图
plt.plot(x,y,'--go') # 填充子图
ax.set_xticks(x[::5]) # 使用axis.set_xticks固定刻度位置   (新添加内容)
ax.set_xtichlabels(data.nadex[0:0:5]) # 将时间戳作为x轴标签
```
# 经验总结（个人见解）
1. 官方文档是最好的参考书，要学会参见官方文档
2. 学会使用Google搜索，获取更有价值的内容
3. [ Stack**overflow**](https://stackoverflow.com/)，一个值得推荐的程序员交流社区
4. 解决遇到的难题（个人编程水品限制），真的心情舒畅

# 参考文献
1. [matplotlib官方文档](https://matplotlib.org/3.5.1/api/_as_gen/matplotlib.axes.Axes.set_xticklabels.html)
2. [stackoverflow](https://stackoverflow.com/questions/63723514/userwarning-fixedformatter-should-only-be-used-together-with-fixedlocator)
