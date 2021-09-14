---
title: "扩容节点"
description: 本小节主要介绍如何扩容 ClickHouse 集群。 
keywords: ClickHouse 扩容节点；
weight: 05
collapsible: false
draft: false
---


ClickHouse 支持对运行中的数据库服务进行在线扩容，调整 CPU、内存、磁盘空间大小。

- 在 AppCenter 集群管理中心，支持对集群节点升级扩容。

> **注意**
> 
> 扩容过程业务中断，请在业务低峰期进行。

本小节主要介绍如何在线扩容 ClickHouse 集群。

## 约束限制

- 不支持降低磁盘大小配置。

## 前提条件

- 已获取 QingCloud 管理控制台登录账号和密码，且已获取集群操作权限。
- 已创建 ClickHouse 集群，且集群状态为**活跃**。

## 操作步骤

1. 登录 QingCloud 管理控制台。
2. 选择**产品与服务** > **数据仓库与 BI** > **ClickHouse**，进入集群管理页面。
3. 点击目标集群 ID，进入集群详情页面。
4. 在**基本属性**模块，点击集群操作下拉菜单。
5. 展开下拉菜单，点击**扩容集群**。
   
   <img src="../../../_images/expansion.png" alt="创建扩容" style="zoom:50%;" />

6. 配置扩容信息。

   勾选需扩容节点类型，并分别配置节点云服务器规格和磁盘大小。

7. 确认配置信息无误后，点击**提交**，返回节点列表页面。

   多个节点逐一扩容更新，待集群状态切换为**活跃**，即扩容完毕。