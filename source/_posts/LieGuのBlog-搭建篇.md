---
title: LieGuのBlog_搭建篇-快速搭建简约风格博客
date: 2021-12-08 22:01:23
tags: [Blog,hexo,node.js]
categories: 
  - 经验
  - Blog进化之路
index_img: https://cdn.jsdelivr.net/gh/jinzhi0123/image/img/index_img.jpg
---



这里我用的是 [hexo](https://hexo.io/zh-cn/index.html) 框架 远端部署到 [github](https://github.com/)

# 1.下载安装Git

[Git官网下载界面](https://git-scm.com/)
![安装界面](https://img-blog.csdnimg.cn/d47ea00990424a1ab10f59fb41874dba.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)

我这里已经装过了，就不演示了

注意勾选：Use Git from the Windows Command Prompt

其他遵循 默认的就是符合大众的，所以一路next就好了

# 2.下载安装node.js

[Node.js官网下载界面](http://nodejs.cn/download/)
![Node.js官网下载界面](https://img-blog.csdnimg.cn/5f72cf63dccc436caaa09d0107535bab.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)
选择LTS版本下载就好

  安装一路 next

# 3.npm安装hexo

## 3.1任意位置  推荐新建 E:/Blog 
鼠标右击  Git Bush Here

若在1.2步骤中勾选了 Use Git from the Windows Command Prompt 则 点击在终端中打开可以实现相同的操作

![](https://img-blog.csdnimg.cn/eb359ffff1cc4530a5684bfb7d2eba6d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)

## 3.2因为npm包管理器镜像源在国内比较慢
所以在这里换为淘宝镜像源

继续在上步窗口运行代码，忽略warn就好

```npm install -g cnpm --registry=https://registry.npm.taobao.org```

![忽略warn](https://img-blog.csdnimg.cn/f81147eb66384e8ca521c71241994992.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)

## 3.3 输入cnpm install -g hexo-cli回车  /  复制后在下图空白（黑）右击 paste
```cnpm install -g hexo-cli```
 运行后：成功演示

![成功演示](https://img-blog.csdnimg.cn/e6733180d5f34ac98eb36aae58dd520e.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)

 进行都这  搭建环境就完整了

# 4.生成博客

相当简单啊，一段代码就好了   

这里先搭建起来，所有都使用默认，后期可以更换或自己编辑具体内容的

```hexo init```

![hexo init](https://img-blog.csdnimg.cn/5406bc7435cd4367a84c5f6603273d6b.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)
然后运行hexo s 启动博客本地查看效果

![hexo s](https://img-blog.csdnimg.cn/cb15953cea55418a9f2ac40c9025a8dc.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)

 直接在浏览器打开这个网址就行

 ```http://localhost:4000```

![默认theme](https://img-blog.csdnimg.cn/0f5ec7b0bc014b1f91730585ab8f8d47.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)

这里使用的时默认的theme，后面可以更换

 新建博客文章

```hexo new "我的第一篇博客文章"```
然后就可以 进入这个文件夹的 /source/*里面找到“我的第一篇博客文章”

![我的第一篇博客文章](https://img-blog.csdnimg.cn/9670f1393c324149854f31f3f39bcbc4.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)

可以使用sublime，VS Code或markdown等编辑。

 编辑后保存

# 5.部署到Github


 在 [GitHub](https://github.com/LIEGU0317) 创建仓库

注册登录账号后，在任何页面的右上角，使用 + 下拉菜单选择New repository（新建仓库）


![](https://img-blog.csdnimg.cn/img_convert/93f3fe27cd8bc9824d3f56692754c762.png)

![](https://img-blog.csdnimg.cn/c41a138dd5fc4be081b0c268ee779d6f.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_13,color_FFFFFF,t_70,g_se,x_16)

注意这里名字必须是name.github.io

图中的liegu0317是我的Github昵称

 描述随便写

然后  Create repository 

复制库地址

![](https://img-blog.csdnimg.cn/cc868874836c475db37582c984dbd4ea.jpg?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)

返回命令行

去安装hexo-deployer-git自动部署发布工具

```cnpm install --save hexo-deployer-git```

编辑E:/bolg/_config.ylm 

![](https://img-blog.csdnimg.cn/33f4524f85fc435aa6a0b38078f40c69.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)


 最底部

![](https://img-blog.csdnimg.cn/0dbe3cf961a54621a87f590f69fd45e7.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)

修改为

 ![](https://img-blog.csdnimg.cn/b58dee1885d74fff98c2400fba9273d6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_20,color_FFFFFF,t_70,g_se,x_16)

  

```
type: git
repo: https://github.com/liegu0317/liegu0317.github.io.git
branch: master
```

注意将`liegu0317`更换为你的GitHub用户名

## 0. 然后，部署到远端


在 E:/bloge文件夹内 右击选择 Git Bush Here

 ![](https://img-blog.csdnimg.cn/7a1188a2ab32426ba3d6e7e266ae91c4.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54ix5ZCD6LGG55qu,size_12,color_FFFFFF,t_70,g_se,x_16)

让Git知道你是谁

```git config --global user.name "liegu0317"```
```git config --global user.email "liegu0317@qq.com"```

## 1. 先清除缓存文件db.jios 和以生成的静态文件public


```hexo clean```

- 网站显示异常时可以执行这条命令

## 2. 生成网站静态文件到默认设置的public文件夹

```hexo g```

- 便于查看网站生成的静态文件或者手动部署网站；
- 如果使用自动部署，不需要先执行该命令；
- hexo g 是 hexo generate 的缩写，命令效果一致。

## 3. 自动生成网站静态文件，并部署到设定的仓库。

```hexo d```
- hexo d 是 hexo deploy 的缩写，命令效果一致

> 第一次部署会要求输入账号（GitHub用户名）和密码或[Token](https://github.com/settings/tokens)

## 4. 部署到远端也可以直接运行这个命令

```hexo clean && hexo g && hexo d```

其中```&&```是成功后执行的意思

实际效果与原理与1-3相同

## 5. 直接访问仓库名，就可以看见搭建部署完成

## 6. [Hexo 好看的主题推荐(附安装教程)](https://blog.csdn.net/zgd826237710/article/details/99671027)

---
## 我の博客

[有时间的话，一起学习吧!](https://liegu0317.github.io/)←Blog

我的CSDN文章→[【hexo】+【github】搭建bloge 一路畅通 无坑版](https://blog.csdn.net/liegu0317/article/details/121798595?spm=1001.2014.3001.5501)