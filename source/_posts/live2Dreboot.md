---
title: 博客live2D/看板娘配置|Blog进化之路
tags:
  - live2D
  - 看板娘
categories:
  - 经验
  - Blog进化之路
index_img: https://s2.loli.net/2022/10/14/2chydDe9WX8bqvE.png
hide: false
description: 博客重构之后live2D看板娘动画丢失，重新构建
comment: twikoo
date: 2022-10-14 00:07:56
sticky:
---



![](https://s2.loli.net/2022/10/14/2chydDe9WX8bqvE.png)

> 此方法仅针对hexo框架博客添加live2D看板娘提供解决方案

## 一、安装hexo的live2D插件

```
npm install --save hexo-helper-live2d
```

## 二、下载喜欢的模型

[点击→可前往GitHub寻找](https://github.com/search?q=live2d)

[这是我使用的模型仓库--live2d-widget-models](https://github.com/xiazeyu/live2d-widget-models),模型展示图只需要Google搜索最后的名称就会有人物形象展示

下载完成后模型连同目录一同复制到本地博客目录

![](https://sm.ms/image/XklSVf8iy1xdZbO)

然后执行指令

```shell
npm install live2d-widget-models\packages\live2d-widget-model-miku
```

*live2d-widget-models\packages\live2d-widget-model-miku*是模型目录相对于博客根目录的路径

## 三、修改_config.yml配置文件

找到你博客的本地存储的根目录，打开_config.yml文件，添加下面的内容

可根据提示修改对应内容

```shell
# Live2D
## https://github.com/EYHN/hexo-helper-live2d
live2d:
  enable: true
  # enable: false
  scriptFrom: local # 默认
  pluginRootPath: live2dw/ # 插件在站点上的根目录(相对路径)，自由设置
  pluginJsPath: lib/ # 脚本文件相对与插件根目录路径
  pluginModelPath: assets/ # 模型文件相对与插件根目录路径
  # scriptFrom: jsdelivr # jsdelivr CDN
  # scriptFrom: unpkg # unpkg CDN
  # scriptFrom: https://cdn.jsdelivr.net/npm/live2d-widget@3.x/lib/L2Dwidget.min.js # 你的自定义 url
  tagMode: false # 标签模式, 是否仅替换 live2d tag标签而非插入到所有页面中
  debug: false # 调试, 是否在控制台输出日志
  model:
    use: live2d-widget-model-wanko # npm-module package name
    # use: wanko # 博客根目录/live2d_models/ 下的目录名
    # use: ./wives/wanko # 相对于博客根目录的路径
    # use: https://cdn.jsdelivr.net/npm/live2d-widget-model-wanko@1.0.5/assets/wanko.model.json # 你的自定义 url
    display:
		position: right //显示的位置
		width: 150 //宽度
		height: 150 //高度
	mobile:
		show: true //移动端是否显示
```

## 五、调试&部署

```
hexo clean 
hexo g
hexo s
```

完成后即可进入`http://localhost:4000/`查看本地部署效果，或者[点击这里跳转](http://localhost:4000/)

## 参考资料

https://github.com/EYHN/hexo-helper-live2d

https://github.com/xiazeyu/live2d-widget-models

https://liegu0317.top/2021/12/10/LieGu%E3%81%AEBlog-%E7%BE%8E%E5%8C%96%E7%AF%87/
