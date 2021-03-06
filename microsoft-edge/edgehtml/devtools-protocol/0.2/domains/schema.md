---
description: DevTools 协议版本 0.2 (EdgeHTML) 架构域参考。 提供有关协议架构的信息。
title: '架构域 - DevTools 协议版本 0.2 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 6844939f452bc96980d6d67d4652adcc7c078c7a
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398145"
---
# <a name="schema-domain---devtools-protocol-version-02-edgehtml"></a>架构域 - DevTools 协议版本 0.2 (EdgeHTML)   

提供有关协议架构的信息。  

| 分类 | 成员 |  
|:--- |:--- |  
| [方法](#methods) | [getDomains](#getdomains) |  
| [类型](#types) | [Domain 对象](#domain) |  

## <a name="methods"></a>方法  

### <a name="getdomains"></a>getDomains  

返回支持的域。  

| 返回 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| 域 | [域[]](#domain) | 受支持的域列表。 |  

---  

## <a name="types"></a>类型  

### <a name="domain-object"></a>Domain 对象  

<a name="domain"></a>  

协议域的说明。  

| 属性 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| name | `string` | 域名。 |  
| version | `string` | 域版本。 |  

---  
