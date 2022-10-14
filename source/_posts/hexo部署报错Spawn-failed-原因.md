---
stitle: Hexo部署Error:Spawn failed 原因
date: 2021-12-12 14:31:51
tags: [hexo,Blog]
categories: 
  - 经验
  - Blog进化之路
index_img: https://cdn.jsdelivr.net/gh/jinzhi0123/image/img/index_img.jpg
---

# 1.问题描述

正常编写发布hexo博客

```
hexo clean && hexo g && hexo d
```

部署修改，遇到名为Spawn failed报错。然后无脑尝试了二次执行，依然报错如下

![](https://img-blog.csdnimg.cn/699e938641aa48509efb10ae92384e3a.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)

# 2.问题原因

询问学长以及在网上通过简单的查询之后发现问题出在.deploy_git文件夹，这是由hexo框架渲染生成的一个Git仓库,hexo d命令就是将其push到github。

这是解决后的截图，更新时间全部为一样的

![](https://img-blog.csdnimg.cn/b4efcdff7ed342aa8717f244e5a80b78.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)


这是github liegu0317.github.io截图

![](https://img-blog.csdnimg.cn/6c1d68b51ad84b6bba33cf40098d0fb4.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)



问题大多是因为git进行push或者hexo d的时候改变了一些.deploy_git文件下的内容，多余本地提交之类的导致了报错。

总之是本地文件的问题，

于是运行了如下解决方法。

# 3.解决办法

```
进入站点根目录
cd E:/hexo

删除git提交内容文件夹
rm -rf .deploy_git/

执行
git config --global core.autocrlf false

最后
hexo clean && hexo g && hexo d
```

还有些回滚的方法，真的麻烦，但也有那样做的好处，各取所需吧。
其他方法可参见我的上一篇文章：‘Hexo部署Error:Spawn failed 解决方式’

# 参考文献：

[Hexo部署Error:Spawn failed 解决方式](https://blog.csdn.net/liegu0317/article/details/121886380?spm=1001.2014.3001.5501)

## 我的CSDN文章

[hexo部署报错Spawn failed原因及解决方法](https://blog.csdn.net/liegu0317/article/details/121886380?spm=1001.2014.3001.5501)