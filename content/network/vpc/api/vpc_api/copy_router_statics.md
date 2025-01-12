---
title: "CopyRouterStatics"
description: 把源 VPC 网络的路由规则复制给目的 VPC 网络。
keyword: QingCloud, 青云, 云计算, VPC,  VPC 网络, 路由规则
weight: 23
draft: false
---

把源 VPC 网络的路由规则复制给目的 VPC 网络。

 如果源 VPC 网络和目的 VPC 网络都属于网络2.0，且自身的网络地址不同，那么复制IPsec隧道规则时， 会修改规则里的目标网络地址，以适配目的 VPC 网络。

**Request Parameters**

[_公共参数_](../../get_api/parameters/)

**Response Elements**

| Name | Type | Description |
| --- | --- | --- |
| action | String | 响应动作 |
| ret_code | Integer | 执行成功与否，0 表示成功，其他值则为错误代码 |

**Example**

_Example Request_:

```
https://api.qingcloud.com/iaas/?action=CopyRouterStatics
&source_router=rtr-srcsrc11
&dest_router=rtr-destdest
&dest_zone=dest
```

_Example Response_:

```
{
  "action":"CopyRouterStaticsResponse",
  "ret_code":0
}
```
