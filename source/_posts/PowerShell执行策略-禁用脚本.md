---
title: PowerShell：因为在此系统上禁止运行脚本，解决方法
tags:
  - PowerShell
  - about_Execution_Policies
categories:
  - 经验
  - 错误总结
index_img: https://s2.loli.net/2022/10/13/xED35QMTcA9UClV.png
hide: false
description: 以管理员身份打开PowerShell 输入 set-executionpolicy remotesigned
comment: twikoo
date: 2022-10-13 22:36:04
sticky:
---

![powershell.png](https://s2.loli.net/2022/10/13/xED35QMTcA9UClV.png)

# 问题描述

> Problem Description

在使用WebStom的终端里使用PowerShell是出现这个报错

```shell
hexo : 无法加载文件 C:\Users\shuan\AppData\Roaming\npm\hexo.ps1，因为在此系统上禁止运行脚本。有关详细信息，请参阅 https:/go.microsoft.com/fwlink/?LinkI
D=135170 中的 about_Execution_Policies。
所在位置 行:1 字符: 1
+ hexo s
+ ~~~~
    + CategoryInfo          : SecurityError: (:) []，PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

```

# 报错原因

> Reason for error report

根据提示内容进入[powershell](https:/go.microsoft.com/fwlink/?LinkI
D=135170)官网，阅读后发现是[执行策略](https://learn.microsoft.com/zh-cn/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.2)默认设置[Restricted](https://learn.microsoft.com/zh-cn/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.2#restricted)的问题

> ### Restricted
>
> - Windows 客户端计算机的默认执行策略。
> - 允许单个命令，但不允许脚本。
> - 防止运行所有脚本文件，包括格式化和配置文件 () `.ps1xml` 、模块脚本文件 (`.psm1`) ，以及 powerShell 配置文件 (`.ps1`) 。

# 解决方案

> Solutions

**查询当前执行策略**

```
Get-ExecutionPolicy
```

**更改执行策略**

更改为remotesigned

> ### RemoteSigned
>
> - Windows 服务器计算机的默认执行策略。
> - 脚本可以运行。
> - 需要来自受信任的发布者对从 Internet 下载的脚本和配置文件（包括电子邮件和即时消息程序）的数字签名。
> - 不需要对在本地计算机上编写的脚本（而不是从 Internet 下载）进行数字签名。
> - 如果脚本被取消阻止，则运行从 Internet 下载且未签名的脚本，例如使用 `Unblock-File` cmdlet。
> - 从 Internet 以外的源运行未签名脚本的风险，以及可能是恶意的签名脚本。

以**管理员身份**打开**PowerShell** 输入如下命令

```
set-executionpolicy remotesigned
```

选择`A`或者`Y`即可在电脑上执行第三方脚本

# 参考文档

> Reference

#[ about_Execution_Policies](https://learn.microsoft.com/zh-cn/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.2#restricted)
