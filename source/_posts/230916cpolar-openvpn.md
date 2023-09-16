---
title: Cpolar与OpenVPN实现任意内网接入|随时随地连接内网
tags:
  - 中国知网
  - cpolar
  - openvpn
categories:
  - 经验
  - Tools
index_img: https://img-blog.csdnimg.cn/img_convert/7cdcb2ed1797a308f8a2bb48cc38d662.png
hide: false
description: 随时随地连接内网、校园网
comment: twikoo
date: 2023-09-16 10:07:01
sticky:
---

![](https://img-blog.csdnimg.cn/img_convert/7cdcb2ed1797a308f8a2bb48cc38d662.png#pic_center)

# Cpolar与OpenVPN实现任意内网接入

该经验帖依赖于**cpolar官方教程**：[cpolar与OpenVPN实现任意内网接入](https://www.cpolar.com/blog/cpolar-and-openvpn-any-intranet-access)，补充一部分小细节以及常见问题。

> 请按照官方教程操作，以下内容同其标题一致。

#### 2.2 添加公网TCP固定端口

> 此步骤是整个解决方案中唯一需要消费的地方，免费套餐端口不固定，最长使用到过将近两个月
>
> 偶尔使用选择免费套餐即可。

#### 2.3 cpolar客户端的部署

> 该部分建议按照[文档-入门指南](https://www.cpolar.com/docs#expose-a-local-web-server-to-the-internet)进行操作，学习使用[Cpolar web UI](https://www.cpolar.com/docs#cpolar_web_ui_management-interface)后期维护会简单很多。

## 常见问题

1. 无法连接到openvpn server端

   > 1. **检查服务器是否正在运行**：首先，请确保 OpenVPN 服务器正在运行并且没有崩溃。您可以通过在服务器上运行 `sudo systemctl status openvpn@server`（如果您使用 systemd）或 `sudo service openvpn status`（如果您使用 init.d）来检查 OpenVPN 服务器的状态。
   >
   > 2. **检查服务器配置文件**：确保您的 OpenVPN 服务器配置文件 (`server.conf` 或类似的文件) 中没有语法错误或配置问题。请检查文件路径是否正确，并且配置是否按照需要设置。
   >
   > 3. **检查防火墙规则|最大可能性问题**：确保服务器上的防火墙规则允许 OpenVPN 流量通过。您需要确保服务器的防火墙配置允许 OpenVPN 端口（默认是 UDP 1194）的流量。
   >
   >    > **1. 查看当前防火墙规则：**
   >    >
   >    > 在服务器上打开终端，以管理员权限运行以下命令来查看当前的防火墙规则：
   >    >
   >    > ```
   >    > bashCopy code
   >    > sudo iptables -L
   >    > ```
   >    >
   >    > 这将列出当前的防火墙规则。您应该查找有关 OpenVPN 端口（默认是 UDP 1194）的规则。
   >    >
   >    > **2. 添加允许 OpenVPN 流量的规则：**
   >    >
   >    > 如果没有看到与 OpenVPN 端口相关的规则，或者规则中没有允许流量通过，您需要添加规则以允许 OpenVPN 流量。以下是如何添加规则的示例：
   >    >
   >    > ```
   >    > bashCopy code# 允许UDP 1194端口上的OpenVPN流量
   >    > sudo iptables -A INPUT -p udp --dport 1194 -j ACCEPT
   >    > ```
   >    >
   >    > 上述命令将添加一条规则，允许UDP协议的流量通过1194端口。
   >    >
   >    > **3. 保存防火墙规则：**
   >    >
   >    > 一旦添加了规则，您需要确保它们在系统重启后仍然有效。您可以使用以下命令将当前的防火墙规则保存到永久配置中：
   >    >
   >    > ```
   >    > bashCopy code
   >    > sudo iptables-save > /etc/iptables/rules.v4
   >    > ```
   >    >
   >    > **4. 重新加载防火墙规则：**
   >    >
   >    > 最后，重新加载防火墙规则以使更改生效：
   >    >
   >    > ```
   >    > bashCopy code
   >    > sudo iptables-restore < /etc/iptables/rules.v4
   >    > ```
   >    >
   >    > **5. 检查 OpenVPN 连接：**
   >    >
   >    > 现在，您可以尝试重新连接到 OpenVPN 服务器并查看是否已解决连接问题。
   >
   > 4. **网络连接**：检查客户端的网络连接，确保您的计算机能够访问服务器的 IP 地址。如果您尝试在不同网络（例如，从家庭网络连接到公司网络）上连接，请确保网络设置正确。
   >
   > 5. **客户端配置**：确保您的 OpenVPN 客户端配置正确，包括服务器地址和端口。客户端配置文件应该与服务器配置相匹配。
   >
   > 6. **更新 OpenVPN**：如果您的 OpenVPN 版本较旧，请考虑升级到最新版本，以确保安全性和兼容性。

2. 连接后只能访问运行openvpn主机（服务器端）上运行的内容

   > 1. **路由设置问题|最大可能性问题|使用路由系统如OpenWrt可以避免此问题**：您的 OpenVPN 服务器可能没有正确配置路由，导致客户端只能访问服务器本身。这通常通过配置服务器的路由表和防火墙规则来实现。
   > 2. **防火墙问题**：服务器的防火墙规则可能阻止了从 VPN 客户端到服务器以外的网络的流量。您需要检查服务器上的防火墙规则，并确保它们允许通过 VPN 访问服务器以外的网络。
   > 3. **NAT (网络地址转换) 设置**：如果服务器配置了 NAT，它可能会导致只有服务器本身可以访问外部网络。您需要检查服务器上的 NAT 配置，并确保它允许 VPN 客户端的流量通过。
   > 4. **DNS 配置问题**：如果 DNS 配置不正确，客户端可能无法解析服务器以外的域名。请检查 DNS 设置，确保客户端可以正确解析外部域名。
   > 5. **OpenVPN 配置问题**：最后，确保您的 OpenVPN 服务器和客户端配置正确。您可能需要检查配置文件，确保它们没有限制流量或访问。

## 免责声明 - Cpolar 和 OpenVPN 内网接入
1. 使用 Cpolar 和 OpenVPN 工具（以下简称 "工具"）进行内网接入，需要遵守所有适用的法律和法规。用户必须确保他们的使用方式合法且符合适用法律。

1. 用户明白，工具仅供合法目的使用，例如远程办公、合法的网络连接或安全测试等。工具的滥用或非法用途将不受支持。

1. 使用工具涉及安全和隐私风险。用户必须自行采取适当的安全措施，包括但不限于使用强密码、加密通信以及遵循网络安全最佳实践。

1. Cpolar 和 OpenVPN 工具的使用是基于用户自行决策的，用户对其后果负全部责任。

1. 使用工具之前，用户必须获得适用的许可或授权，包括但不限于网络管理员的批准。用户必须遵循所有内部政策和规定。

1. 通过使用 Cpolar 和 OpenVPN 工具，用户确认已阅读、理解并同意本免责声明的所有条款和条件。如有任何疑问或疑虑，用户应在使用工具之前咨询法律或网络安全专业人士。