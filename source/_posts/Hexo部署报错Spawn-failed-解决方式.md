---
title: Hexo部署Error:Spawn failed 解决方式
date: 2021-12-12 14:40:32
tags: [hexo,Blog]
categories: 
  - 经验
  - Blog进化之路
index_img: https://img-blog.csdnimg.cn/131fe9e2322b418a9005ce3c803a1c07.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16
---

Hexo部署出现一下错误err: Error: Spawn failed解决方式

---
方法一
-
```
进入站点根目录

删除git提交内容文件夹
rm -rf .deploy_git/

执行
git config --global core.autocrlf false

最后
hexo clean && hexo g && hexo d
```

方法二
-
修改 _config.yml 文件，将配置地址http方式切换成ssh方式

```
进入站点根目录

删除git提交内容文件夹
vim _config.yml

修改
deploy:

type: git

repository: https://github.com/Uninfo/blog.github.io.git 
-> git@github.com:Uninfo/blog.github.io.git

branch: master

最后
hexo clean && hexo g && hexo d
```

方法三
-
```
进入站点根目录

进入depoly文件夹
cd .deploy_git/

强制推送
git push -f
```

参考文献：
-

[Hexo部署Error:Spawn failed 解决方式](https://blog.csdn.net/liegu0317/article/details/121886380?spm=1001.2014.3001.5501)

我的CSDN文章
-
[hexo部署报错Spawn failed原因及解决方法](https://blog.csdn.net/liegu0317/article/details/121886380?spm=1001.2014.3001.5501)