---
title: OpenCV-python安装|计算机视觉库
date: 2021-12-19 00:05:34
tags: [OpenCV-Python,pip,contrib]
categories: 
- 经验
- Tools
index_img: https://s2.loli.net/2021/12/18/OkWFomyTA6qN3jS.png
hide: false
comment: 'twikoo'
---





![](https://s2.loli.net/2021/12/18/OkWFomyTA6qN3jS.png)

# 工具简介

> OpenCV的全称是Open Source Computer Vision Library，是一个跨平台的计算机视觉库。OpenCV是由英特尔公司发起并参与开发，以BSD许可证授权发行，可以在商业和研究领域中免费使用。OpenCV可用于开发实时的图像处理、计算机视觉以及模式识别程序。该程序库也可以使用英特尔公司的IPP进行加速处理。

# 安装简述

**建议配合`Anaconda`配置Python开发环境**

简单的说一下`OpenCV-Python`在`Windows`环境下的安装

*在`3.4.2`版本后部分（sift,surf）算法申请了专利，后续的开源版本部分功能不方便应用*

>下面两个版本各取所需

## 使用pip进行安装最新版

打开`Anaconda`的`Anaconda Prompt`

![](https://s2.loli.net/2021/12/18/bZPUsmv7pSRjMfn.png)

运行命令

```
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple/ opencv-python

pip install -i https://pypi.tuna.tsinghua.edu.cn/simple/ opencv-contrib-python
```

来安装`OpenCV-Python`最新版

> 因为OpenCV官方镜像源在国外，速度极慢（在我的网络环境仅有几十KB），因此这里是使用的`清华大学开源软件镜像站`


## OpenCV-Python装3.4.1.15版本（最后一个含有sift,surf的版本）

Anaconda要装Anaconda3 5.2.0，对应python3.6版本

依旧推荐[清华大学开源软件镜像站-anaconda/archive](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/)



![image-20211220235037549](https://github.com/LIEGU0317/img/raw/master/Blogimg/202112202350676.png)



安装OpenCV-python

```
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple opencv-python==3.4.1.15
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple opencv-contrib-python==3.4.1.15
```

若失效，不存在的请自行更换镜像源 [^1]


注

```
 -i https://pypi.tuna.tsinghua.edu.cn/simple --使用源

 -contrib- --添加模块
```



## 查看已安装opencv版本

```
python  
```
```
cv2.__version__
```





# 参考文献

+ [opencv-维基百科](https://zh.wikipedia.org/zh-cn/OpenCV)

![](https://s2.loli.net/2021/12/19/9OxY3cKsAdXRjNb.png)

[^1]: 常见国内镜像源  
		http://pypi.douban.com/simple/ 豆瓣 
		http://mirrors.aliyun.com/pypi/simple/ 阿里 
		http://pypi.hustunique.com/simple/ 华中理工大学 
		http://pypi.sdutlinux.org/simple/ 山东理工大学 
		http://pypi.mirrors.ustc.edu.cn/simple/ 中国科学技术大学
