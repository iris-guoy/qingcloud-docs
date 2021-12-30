---
title: "启动灾备"
description: 本小节主要介绍如何启动 PostgreSQL 灾备。 
keyword: 异地容灾,异地灾备,PostgreSQL,关系型数据库,数据库
weight: 10
collapsible: false
draft: false
---



PostgreSQL 通过在**灾备集群**启动灾备，同步**源集群**数据。当**源集群**所在区域发生突发性状况，集群节点均无法连接时，可将业务切换至**灾备集群**，快速恢复业务访问。

本小节主要介绍如何在**灾备集群**启动灾备。

## 前提条件

- 已获取管理控制台登录账号和密码，且已获取集群操作权限。
- 已创建**灾备集群**且集群状态为`活跃`。
- 已配置**灾备集群**如下配置参数值不小于**源集群**参数值。

  `max_connections`、`max_worker_processes`、`max_wal_senders`、`max_prepared_transactions`、`max_locks_per_transaction`

- **源集群**状态为`活跃`服务正常，且已获取**源集群**高可用 IP 和端口。

## 操作步骤

1. 登录管理控制台。
2. 选择**产品与服务** > **数据库与缓存** > **关系型数据库 PostgreSQL**，进入集群管理页面。
3. 点击目标集群 ID，进入集群详情页面。
4. 在**基本属性**模块，点击集群操作下拉菜单。
5. 展开下拉菜单，点击**启动灾备**。

   <img src="../../../_images/enable_dr.png" alt="启动灾备" style="zoom:50%;" />

6. 配置**源集群**信息，详细请参见[参数说明](#参数说明)。
7. 确认配置信息无误后，点击**提交**，返回节点列表页面。

   待启动灾备执行完成后，可在**灾备参数**页签可查看**源集群**信息和灾备进度。

### 参数说明

|  <span style="display:inline-block;width:120px">参数</span> | <span style="display:inline-block;width:480px">说明</span>  |
|:--- |:--- |
| 角色  |  选择**源集群**节点角色类型，默认为`主实例`。 |
| 源集群端口  | 输入**源集群**的端口号。|
| 描述  | 简要描述**源集群**信息。|
| 同步方式 |  选择是否选用同步方式同步数据。<li>若选择`是`，则使用**同步方式**同步数据，实时同步数据。<li>若选择`否`，则使用**异步方式**同步数据，延时同步数据，可能导致数据丢失。 |
| 源集群地址  | 输入**源集群**的高可用 IP 地址。|