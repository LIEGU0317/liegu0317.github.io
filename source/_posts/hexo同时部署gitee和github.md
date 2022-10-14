---
title: hexo博客同时部署gitee和github
tags:
  - hexo
  - gitee
  - github
categories:
  - 经验
  - Blog进化之路
index_img: 'https://github.com/LIEGU0317/img/raw/master/Blogimg/202202211154528.png'
hide: false
description: 
comment: twikoo
date: 2022-02-21 23:23:02
---

hexo博客同时部署gitee和github，实现两站内容一致

> 国内github访问速度较慢，gitee可以作为替补方案

![](https://github.com/LIEGU0317/img/raw/master/Blogimg/202202211154528.png)

在搭建自己的Blog请参见[快速搭建简约风格博客](https://liegu0317.top/2021/12/08/LieGu%E3%81%AEBlog-%E6%90%AD%E5%BB%BA%E7%AF%87/)、[Blog美化](https://liegu0317.top/2021/12/10/LieGu%E3%81%AEBlog-%E7%BE%8E%E5%8C%96%E7%AF%87/)

在`_config.yml`将`deploy`下内容作出如下修改

```
deploy:
  - type: git
    repo: https://github.com/LIEGU0317/liegu0317.git
    branch: master
  - type: git
    repo: https://github.com/LIEGU0317/liegu0317.github.io.git
    branch: master
```
按照这种格式修改，程序会按顺序进行提交，从而实现两处内容同步的效果

在github中会自动部署，提交后等待即可，而在gitee中需要手动重新部署

![](https://github.com/LIEGU0317/img/raw/master/Blogimg/202202212319371.png)

>  参考资料
>  [HXEO官方文档](https://hexo.io/zh-cn/docs/)



我的博客  [Github部署](liegu0317.top)       [Gitee部署](https://liegu0317.gitee.io/)


![](https://github.com/LIEGU0317/img/raw/master/Blogimg/202112252216395.gif)
