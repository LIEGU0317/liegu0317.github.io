---
title: LieGuのBlog_美化篇-Theme DIY
date: 2021-12-10 22:07:34
tags: [Blog,hexo,Blog美化]
categories: 
  - 经验
  - Blog进化之路
index_img: https://github.com/LIEGU0317/img/raw/master/Blogimg/202112211144947.png
---

hexo作为一个快速、简洁高速的博客框架,拥有众多用户,也因此theme也非常丰富

直接在GitHub上搜索 [hexo theme](https://github.com/search?q=hexo+theme)就可以找到许多好看的主题 

这里我使用的是名叫  [Fluid](https://github.com/fluid-dev/hexo-theme-fluid)  的主题，他和其他使用量比较大的theme一样其  [官方文档](https://hexo.fluid-dev.com/docs)  是相当丰富

---



1.[主题安装](https://hexo.fluid-dev.com/docs/start/#%E5%AE%89%E8%A3%85%E4%B8%BB%E9%A2%98)
-

Hexo 5.0.0 版本以上，通过 npm 直接安装，进入博客目录执行命令：


```npm install --save hexo-theme-fluid```

然后在博客目录下创建 _config.fluid.yml，将主题的 _config.yml 内容复制过去


[点击查阅官方文档](https://hexo.fluid-dev.com/docs/start/#%E5%AE%89%E8%A3%85%E4%B8%BB%E9%A2%98)

补充: 可以在博客根目录右击 Git Bash Here 利用```hexo -v```查看hexo 版本

![](https://img-blog.csdnimg.cn/b3e0a004680242fcbdea9a9936e854c5.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_17,color_FFFFFF,t_70,g_se,x_16)

---

2.theme DIY
-

2.整理门面

包括：页头和首页

[![](https://img-blog.csdnimg.cn/e26e0d76d39c4241bfb733222c511878.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)](https://liegu0317.github.io/)

打开博客目录下_config.fluid.yml文件

这里我用的是sublime,也可以用 记事本 或 VS Code 等打开编辑都是可以的

ctrl+F 进入搜索 页头

![](https://img-blog.csdnimg.cn/6f53f93046a14a3a84bafa903ef84a11.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)

 顺路开启了导航栏毛玻璃特效

![](https://img-blog.csdnimg.cn/f87975b0077144d7b02c7b329dd35c3c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_19,color_FFFFFF,t_70,g_se,x_16)

 首页

![](https://img-blog.csdnimg.cn/f293047f97f0415b92a3f33608eca7fc.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)

根据喜好做出修改

这里的相对路径就是 相对于.\themes\fluid\source的路径

注意：在文件里编写路径是反斜线  /  或双斜线  \ \

学会这个后我还修改了post的封面，美观了许多

![](https://img-blog.csdnimg.cn/7f0fa088cf144260a517f6cbbe734110.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)

![](https://img-blog.csdnimg.cn/a591ec62f7ce48a28f59fd4f98e66d9d.png)

 在编写文章时丰富下文章信息可以使文章更有序

2.2修改About Page

ctrl+F 进入搜索 about page

![](https://img-blog.csdnimg.cn/1294927b313c46deb117cb5b347a7ae8.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)

把需要的内容做出修改即可   图片内容可供参考

这个主题提供了许多图标可供使用

![](https://img-blog.csdnimg.cn/a2ac999a602443059823bf68ca901aaf.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)

[点击查看](https://hexo.fluid-dev.com/docs/icon/)

根据图标名称（图标下第一行）下面的 代号（图标下第二行）填入到 icons后面的class中，即可完成修改

在这里我增加了友链页

这是我修改后的效果

[![](https://img-blog.csdnimg.cn/92971de32f6e4fa3b646d895c9fd455d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)](https://liegu0317.github.io/about)

[![](https://img-blog.csdnimg.cn/bbb0aef4d60441c49f08a016a4efd81c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)](https://liegu0317.github.io/links)


个人认为还蛮不错的 

建议先在本地查看无误后在部署到远端

```hexo clean && hexo g && hexo s```

最后执行命令部署到远端
---

```hexo clean && hexo g && hexo d```

end...

---

我的CSDN文章→[hexo Blog 美化篇_1](https://blog.csdn.net/liegu0317/article/details/121866375)
---

参考资料：
---

[Fluid配置指南](https://hexo.fluid-dev.com/docs/guide/#%E5%85%B3%E4%BA%8E%E6%8C%87%E5%8D%97)