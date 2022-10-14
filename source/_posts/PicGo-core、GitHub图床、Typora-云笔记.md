---
title: Linux环境下PicGo-core、GitHub图床、Typora|inux云笔记
tags:
  - PicGo-core
  - github
  - typora
  - 图床
categories:
  - 经验
  - Blog进化之路
index_img: 'https://cdn.jsdelivr.net/gh/liegu0317/img/Blogimgpicgo-core-github-typora.png'
hide: false
description: 下利用PicGo-Core上传图片到github图床，通过typora实现自动上传。搭建个人在线云笔记
comment: twikoo
date: 2022-05-24 21:13:27
sticky:
---


![](https://cdn.jsdelivr.net/gh/liegu0317/img/Blogimgpicgo-core-github-typora.png)

> 重复造车？不可能  以下内容截取、翻译自[上床图片 -typora支持](https://support.typora.io/Upload-Image/#option-1-edit-the-config-file)  并做出注释。（注释以引用块形式出现）

### PicGo-Core（命令行）（开源） 

[PicGo-Core ](https://github.com/PicGo/PicGo-Core)是一个支持图片上传的开源节点模块。 它还支持插件来扩展其功能。 

由于它是一个节点模块，我们提供了两种安装和使用方式。 

> 安装方式1

#### 安装 PicGo-Core 的预编译二进制文件 (Linux / Windows) 

Typora 提供了 PicGo 的预构建二进制文件，使用 nexe 将节点模块打包成一个文件二进制文件。  您只需单击“下载”按钮即可安装 PicGo 二进制文件，Typora 将开始下载并将其直接放在 Typora 的支持文件夹下。 

<details>
<summary><a name="picgo-location"></a><font style="vertical-align: inherit;">下载的 PicGo-Core 二进制文件的位置 </font></summary>二进制文件将放在“%AppData/Typora/picgo”下，“%AppData”在 Linux 上是“~/.config”，在 Windows 上是“C:/User/[username]/Roaming/AppData”。<br>您也可以尝试在 Typora 的首选项面板中单击“打开主题文件夹”，然后打开其父文件夹，其中将包含“picgo”文件夹。 </details>

由于 macOS Catalina 的安全规则，预构建的二进制文件在 Catalina 上不起作用，因此您可以尝试以下选项： 

> 安装方式2

#### 通过节点包管理器安装 PicGo-Core（需要提前安装 [NodeJS](https://liegu0317.top/2021/12/08/LieGu%E3%81%AEBlog-%E6%90%AD%E5%BB%BA%E7%AF%87/#2-%E4%B8%8B%E8%BD%BD%E5%AE%89%E8%A3%85node-js) ） 

如果您安装了节点或纱线，您可以在终端中运行以下命令。 

```
npm install picgo -g

# or

yarn global add picgo
```

> 基于debin的发行版，如[统信UOS](https://home.uniontech.com/)、ubuntu，用`npm install picgo -g`

然后你可以在终端输入“which  picgo”得到它的实际安装位置，然后，选择“Custom Command”作为“Image Uploader”功能，输入`“[your  node path] [your picgo-core path] upload”`作为命令。  

> 比如 /home/liegu/applications/node/bin/node /home/liegu/applications/node/bin/picgo upload
>
> 注意空格的书写

 如果你在系统PATH中直接安装了“node”和“picgo”，也可以直接填写“picgo upload”作为自定义命令。 



![安装-picgo](https://support.typora.io/media/image-upload/install-picgo.png)

![风俗](https://support.typora.io/media/image-upload/custom.png)

#### 配置 PicGo-Core 

##### 选项 1：编辑配置文件 

请编辑 `config.json`在以下位置 

- Linux / macOS → `~/.picgo/config.json`. 
- 窗户 → `C:\Users\[your user name]\.picgo\config.json`. 

详情请参阅 [本文档（只有中文） ](https://picgo.github.io/PicGo-Core-Doc/zh/guide/config.html#默认配置文件)。 

> 省流：
>
> ```json
> {
>   "picBed": {
>     "uploader": "github",
>     "current": "github",
>     "transformer": "path",
> 	"github":{
> 	  "repo": "", // 仓库名，格式是username/reponame
> 	  "token": "", // github token
> 	  "path": "", // 自定义存储路径，比如img/
> 	  "customUrl": "", // 自定义域名，注意要加http://或者https://
> 	}
> 
>   },
>   "picgoPlugins": {}
> }
> ```
>
> 自定义域名可以写为如下格式，使用[jscdn加速图床访问](https://liegu0317.top/2022/03/29/Gitee%E5%9B%BE%E5%BA%8A%E5%B4%A9%E4%BA%86-%E6%88%91%E5%8F%88%E8%BD%AC%E5%88%B0%E4%BA%86Github/#GitHub-%E5%9B%BE%E5%BA%8A%E7%9A%84%E6%AD%A3%E7%A1%AE%E7%94%A8%E6%B3%95%EF%BC%8C%E9%80%9A%E8%BF%87-jsDelivr-CDN-%E5%85%A8%E7%90%83%E5%8A%A0%E9%80%9F)
>
> ```
> https://cdn.jsdelivr.net/gh/{username}/{reponame}
> ```

#####  选项 2：通过 CLI 配置 

如果你是通过 node 安装 pico-core，请输入 `picgo -h`显示 picgo 的帮助，并按照它的帮助进行配置。 

如果您使用从 Typora 的首选项面板安装的 PicGo-Core 的预构建二进制文件，请从文件夹中找到二进制文件（请参阅 [此处 ](https://support.typora.io/Upload-Image/#picgo-location)），然后在终端中打开该文件夹，并通过 ( `./picgo -h`). 

您可以在 https://github.com/PicGo/PicGo-Core#use-in-cli 中找到它的 CLI 用法。 
