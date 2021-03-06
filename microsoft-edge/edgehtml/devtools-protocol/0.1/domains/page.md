---
description: DevTools 协议版本 0.1 (EdgeHTML) 页面域参考。 与检查的页面相关的操作和事件属于页面域。
title: '页面域 - DevTools 协议版本 0.1 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b04b0685a6b465d40e999a2a48d370573a3058d8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399146"
---
# <a name="page-domain---devtools-protocol-version-01-edgehtml"></a>页面域 - DevTools 协议版本 0.1 (EdgeHTML)   

与检查的页面相关的操作和事件属于页面域。  

| 分类 | 成员 |  
|:--- |:--- |  
| [**方法**](#methods) | [启用](#enable)， [禁用](#disable)， [导航](#navigate) |  
| [**类型**](#types) | [FrameId](#frameid) |  

## <a name="methods"></a>方法  

### <a name="enable"></a>“启用”  

启用页面域通知。  

&nbsp;  

---  

### <a name="disable"></a>“禁用”  

禁用页面域通知。  

&nbsp;  

---  

### <a name="navigate"></a>导航  

将当前页面导航到给定 URL。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| url | `string` | 要导航到页面的 URL。 |  

| 返回 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| frameId | [FrameId](#frameid) | **实验**性 。  将导航的帧 ID。 |  

---  

## <a name="types"></a>类型  

### <a name="frameid-string"></a>FrameId 字符串  

<a name="frameid"></a>  

唯一的帧标识符。  

&nbsp;  

---  
