---
title: Blog重构之路|Blog进化之路
tags:
  - Blog
  - 图床
categories:
  - 经验
  - Blog进化之路
index_img: https://s2.loli.net/2022/08/09/wtCnWMqGUS5D4ik.png
hide: false
description: 佛系进展，随缘操作，随缘写，看不懂很正常
comment: twikoo
date: 2022-08-09 18:18:28
sticky:
---
![](https://s2.loli.net/2022/08/09/wtCnWMqGUS5D4ik.png)
> 佛系进展，随缘操作，随缘写
> 看不懂很正常，[唯一的营养](#图床推荐)

> 2022年8月7日22:28:02
1. 安装Hexo脚手架
然后进入 hexo 目录，依次执行下面命令:
`npm install -g hexo-cli`，安装hexo最新版
> 2022年8月8日08:40:51
1. 初始化Hexo本地环境
`hexo init foldername`
1. 进入博客目录
`cd ./foldername`
1. 安装PDF插件
在线浏览PDF文件需要用得到，不是很好用勉强能用
`npm install --save hexo-pdf`
1. 安装live2d组件看板娘[【GitHub仓库不维护了】](https://github.com/EYHN/hexo-helper-live2d/blob/HEAD/README.zh-CN.md)
就先往后放吧
![](https://s2.loli.net/2022/08/08/EaWgwPNFGdoqfIc.png)
1. 更换主题
之前一直用的是
[hexo-theme-fluid](https://github.com/fluid-dev/hexo-theme-fluid)
![fluid](https://camo.githubusercontent.com/48b250de82787ee8090df0e3a3088e10d09a12b58fe1df55045f2476aca20978/68747470733a2f2f63646e2e6a7364656c6976722e6e65742f67682f666c7569642d6465762f737461746963406d61737465722f6865786f2d7468656d652d666c7569642f73637265656e73686f74732f696e6465782e706e67)
既然决定重构那么换个主题吧
[hexo-theme-butterfly](https://github.com/jerryc127/hexo-theme-butterfly)
![hexo-theme-butterfly](https://camo.githubusercontent.com/cc33313189cc45d475faff9b2c4a9c5d5e4289e48ee333704ba7f105c9d04e95/68747470733a2f2f63646e2e6a7364656c6976722e6e65742f67682f6a65727279633132372f43444e406d322f696d672f7468656d652d627574746572666c792d726561646d652e706e67)
> It supports Hexo 5.0.0 or later
>
> In Hexo site root directory
> `npm i hexo-theme-butterfly`
> 后续步骤查看上文GitHub仓库链接即可

> 2022年8月8日09:27:52

6. 懒，不换主题了
fluid也是看GitHub仓库就好了
7. 对比新旧配置文件保留需要的配置
`_config.yml`
找第一个好看的loading.gif
![](https://s2.loli.net/2022/08/08/PUIVvtwkGAdXsCr.gif)
> 2022年8月8日16:02:37
8. `hexo d`报错`Deployer not found: git`
吼，途次遇见,[解决方法](https://developer.aliyun.com/article/764974)
9. 再次执行hexo d 报错无法获取电子邮箱地址
> 查看当前用户：
> `git config user.name`
> 查看当前邮箱：
> `git config user.email`
> 修改当前用户：
> `git config --global user.name "liegu0317"`
> 修改当前邮箱：
> `git config --global user.email "liegu0317@qq.com"`
10. 生成SSh并配置到Gitee
[如何生成SSH key](https://www.jianshu.com/p/31cbbbc5f9fa/)

## 图床推荐
1. 路过图床 (https://imgtu.com)
高速稳定，单图最大 10 MB

2. ImgURL (https://imgurl.org)
游客每日限 10 次上传，单图最大 5 MB

3. SM.MS (https://sm.ms)
老牌图床，现在游客禁止上传，普通用户单图最大 5 MB， 5 GB 存储空间

4. KinhPicture (https://img.kinh.cc)
岛主的聚合图床，支持阿里、百度、AWS S3 等 15 个接口，单图限制 2 ~ 32 MB

5. Catbox (https://catbox.moe/) & Litterbox
(https://litterbox.catbox.moe/)Catbox 单文件限制 200 MB，永久保存；
Litterbox 单文件限制 1 GB，有时效。

