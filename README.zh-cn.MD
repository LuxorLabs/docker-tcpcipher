Luxor 加密挖矿程序
=========== 
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/LuxorLabs/docker-tcpcipher.svg?style=for-the-badge
[contributors-url]: https://github.com/LuxorLabs/docker-tcpcipher/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/LuxorLabs/docker-tcpcipher.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/LuxorLabs/docker-tcpcipher.svg?style=for-the-badge
[stars-url]: https://github.com/LuxorLabs/docker-tcpcipher/stargazers
[issues-shield]: https://img.shields.io/github/issues/LuxorLabs/docker-tcpcipher.svg?style=for-the-badge
[issues-url]: https://github.com/LuxorLabs/docker-tcpcipher/issues

此文档的多语言版本: [English](README.MD), [简体中文](README.zh-cn.MD)

---------------
***luxor-tcpcipher*** 是一个用于挖矿的加密挖矿代理程序. 在矿机和矿池之间加入此程序, 可以确保挖矿的数据是加密的. 

本程序有以下的功能:
- 通过对流量加密的方式, 绕过了对矿机与矿池之间的网络限制 (防火墙或者其他网络限制).
- 简单易用, 只需要在本地电脑上安装 ***docker*** 程序, 然后执行`docker compose up`即可.
- 很低的内存占用, 适用于绝大多数的设备. 

准备工作
---------------
为了能使用***luxor-tcpcipher***, 需要在计算机上安装一些必须的工具. 我们强烈建议您在矿厂内部中, 单独部署一台专用的服务器来运行本程序.

第一步, 我们必须安装 ***Docker***. 您可以在 [这里](https://www.docker.com/get-started) 找到说明文档.

在某些操作系统中, 最新版本的 ***Docker*** 默认自带了 ***docker-compose*** . 但是有些有些系统中的 ***docker-compose*** 是需要单独安装的. 您可以根据您的系统类型, 查看相应指导文档, 您可以在 [这里](https://docs.docker.com/compose/install/) 找到.

一旦 ***Docker*** 安装完成, 您应当下载本代码仓库到您的本地服务器中. 您可以运行以下命令来下载:

```
git clone https://github.com/LuxorLabs/docker-tcpcipher.git
```

然后通过`cd`命令进入本代码仓库的根目录. 运行以下命令:

```
cd docker-tcpcipher
```

最后, 您可以使用 ***docker-compose*** 来启动整个 ***luxor-tcpcipher*** 加密挖矿代理程序了.

如果您的 ***Docker*** 内置了 ***compose*** 组件, 您可以运行以下命令:

```
docker compose up
```
如果您的  ***Docker*** 与 ***docker-compose*** 组件是分开安装的, 您可以运行以下命令:

```
docker-compose up
```

**注意**: 主要的区别是`-`，它指定了我们正在使用哪一种可执行程序来启动。

如果您想停止 ***luxor-tcpcipher*** 的运行, 您可以运行以下命令(取决于您的系统设置):

```
docker compose down
```

或者

```
docker-compose down
``` 

您也可以让本程序在后台运行, 执行以下命令即可:

```
docker compose up -d
```

修改矿机的配置
---------------

***luxor-tcpcipher*** 已经设置为: 收到矿机传来数据后, 先加密, 然后发送加密后的信息到矿池的服务器, 最后由矿池的服务器解密. 您无需修改本程序的配置.

如果要将矿机切到加密代理上来挖矿, 您需要修改矿机的 ***矿池地址*** 为如下地址:

```
stratum+tcp://<本程序运行的电脑的局域网IP地址>:8383
```

配置要求
---------------
您的电脑至少要满足如下的配置要求:
- 最少为本程序的镜像, 预留100MB的硬盘空间
- 至少为本程序的运行, 预留250MB的内存空间

祝您挖矿愉快!
