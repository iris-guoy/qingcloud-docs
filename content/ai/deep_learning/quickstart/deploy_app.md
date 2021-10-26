---
title: "步骤一：部署 Deep Learning 应用"
description: 本小节主要介绍如何快速部署 Deep Learning 应用。 
keywords: 
weight: 10
collapsible: false
draft: false
---

通过 AppCenter 集群管理控制台，您可以快速部署 Deep Learning 应用。本小节主要介绍如何快速部署 Deep Learning 应用。

<video src="https://appcenter-docs.pek3a.qingstor.com/developer-guide/docs/videos/AppCenter2.0_Training_Fix.mp4" controls="controls">
您的浏览器不支持 video 标签。
</video>

## 前提条件

- 已获取 QingCloud 管理控制台登录账号和密码。
- 已创建 [VPC 网络](https://docsv3.qingcloud.com/network/vpc/manual/vpcnet/10_create_vpc/)和[私有网络](https://docsv3.qingcloud.com/network/vpc/manual/vxnet/05_create_vxnet/)，且私有网络已加入 VPC 网络。

## 操作步骤

1. 登录 QingCloud 管理控制台。
2. 在左上方的控制台导航栏中，选择**产品与服务** > **人工智能（AI）** > **Deep Learnling**，进入 Deep Learnling 集群管理页面。
3. 点击**立即部署**，进入应用部署页面。
4. 选择**区域**。
   根据就近原则，选择实例所在区域。
5. 配置实例基本属性、应用版本、网络信息、环境参数等信息。
   
   a. [基本设置](#基本设置)

   b. [深度学习节点设置](#深度学习节点设置)

   c. [网络设置](#网络设置)

   d. [服务环境参数设置](#服务环境参数设置)

   e. [用户协议](#用户协议)

6. 确认配置和费用信息无误后，点击**提交**，创建集群。
   
   集群创建成功后，可在**集群管理**页面，查看和管理 Deep Learnling 集群。


### 基本设置

集群名称、网络、版本、计费方式等基本信息配置。

| <span style="display:inline-block;width:140px">参数</span> | <span style="display:inline-block;width:520px">参数说明</span> |
| :--------------------------------------------------------- | :----------------------------------------------------------- |
| UUID                                                       | 系统默认分配的全局唯一标识码，不可修改。                     |
| 名称                                                       | （可选）输入深度学习服务的名称。<li>默认为`Deep Learning`。  |
| 描述                                                       | （可选）对深度学习服务的简要描述。                           |
| 系列                                                       | 选择深度学习服务的系列，可选择`入门版`、`基础版`、`企业版`。 |
| 版本                                                       | 选择想要部署的应用版本，根据所选系列不同，可选版本不同。     |
| 计费方式                                                   | 选择计费方式，可选择按**小时**/**月**/**年**或按**合约**计费。<li>合约有效期 ：选择按**合约**计费后，需选择合约可用周期。<li>（可选）自动续约 ：选择按**合约**计费后，在账户余额充足时，可选择周期自动续费，保障业务流畅。 |
| 可用区                                                     | 目前可选择区域有`上海1区`、`广东2区`、`北京3区`。            |

![基本参数配置](../../_images/base_step_1.png)

### 深度学习节点设置

深度学习节点的资源配置，包括节点实例规格、磁盘大小和节点数量等。

| <span style="display:inline-block;width:140px">参数</span> | <span style="display:inline-block;width:520px">参数说明</span> |
| :--------------------------------------------------------- | :----------------------------------------------------------- |
| 规格                                                       | 选择深度学习节点的实例规格。                                 |
| 磁盘类型                                                   | 选择节点实例的存储磁盘类型。 支持`企业级SSD本地盘`、`容量型云盘`和`通用型SSD云盘)`。 |
| 节点容量                                                   | 配置节点实例的存储空间。存储空间大小决定了节点实例的最大容量以及 IOPS 能力，请根据实际需求，可滑动设置或输入数字配置节点容量。 |
| 节点数量                                                   | 输入深度学习集群的节点数量。                                 |

### 网络设置

通过为集群设置独享私有网络，便于网络**过滤控制**，且不影响其它私有网络的设置，可确保数据库的对不同业务进行网络隔离。数据库集群仅可加入已连接路由器的私有网络，且需确保私有网络的 DHCP 处于**打开**状态。 

|<span style="display:inline-block;width:140px">参数</span> |<span style="display:inline-block;width:520px">参数说明</span>|
|:----|:----|
|   私有网络     |  选择私有网络。<li>默认适配同区域已有私有网络。可在下拉框选择已有私有网络。<li>若无可选网络，可点击**创建**，创建依赖网络资源。  |
|   节点 IP   |  配置节点 IP 地址。<li>默认为`自动分配`。<li> 选择`手动配置`需为各节点配置 IP。  |
|   预留 IP      |   配置集群预留高可用 IP 地址。<li>默认为`自动分配`。<li>选择`手动配置`需为集群配置高可用写 IP。   |

> **说明**：
> 
> 配置的**私有网络部署方式**与***集群部署方式**必须一致，即选择的集群部署方式为`多可用区部署`，则该集群仅能选择`多可用区部署`的私有网络。

### 服务环境参数设置

数据库的环境参数配置。

### 用户协议

阅读**云平台 AppCenter 用户协议**，并勾选用户协议。