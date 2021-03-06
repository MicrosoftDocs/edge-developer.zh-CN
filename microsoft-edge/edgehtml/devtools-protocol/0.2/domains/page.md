---
description: DevTools 协议版本 0.2 (EdgeHTML) 页面域参考。 与检查的页面相关的操作和事件属于页面域。
title: '页面域 - DevTools 协议版本 0.2 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d969dd100164ace61445a4618174cfa943dcfd2b
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398845"
---
# <a name="page-domain---devtools-protocol-version-02-edgehtml"></a>页面域 - DevTools 协议版本 0.2 (EdgeHTML)   

与检查的页面相关的操作和事件属于页面域。  

| 分类 | 成员 |  
|:--- |:--- |  
| [方法](#methods) | [enable](#enable)， [disable](#disable)， [navigate](#navigate)， [getFrameTree](#getframetree) |  
| [事件](#events) | [frameAttached](#frameattached)， [frameDetached](#framedetached)， [frameNavigated](#framenavigated)， [loadEventFired](#loadeventfired)， [domContentEventFired](#domcontenteventfired) |  
| [类型](#types) | [FrameId](#frameid)、 [Frame](#frame)、 [FrameTree](#frametree) |  

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
| url | `string` | 导航到页面的 URL。 |  
| frameId \ (optional\)  | [FrameId](#frameid) | 要导航的框架 ID。  如果未指定，将导航顶部页面。 |  

| 返回 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| frameId | [FrameId](#frameid) | 将导航的帧 ID。 |  

---  

### <a name="getframetree"></a>getFrameTree  

返回当前框架树结构。  

| 返回 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| frameTree | [FrameTree](#frametree) | 显示框架树结构。 |  

---  

## <a name="events"></a>事件  

### <a name="frameattached"></a>frameAttached  

当框架已连接到其父级时触发。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| frameId | [FrameId](#frameid) | 已附加的帧的 ID。 |  
| parentFrameId | [FrameId](#frameid) | 父帧标识符。 |  
| stack \ (optional\)  | [Runtime.StackTrace](./runtime.md#stacktrace) | 框架的附加时间 JavaScript 堆栈跟踪，仅在框架从脚本启动时设置。 |  

---  

### <a name="framedetached"></a>frameDetached  

当框架与父级分离时触发。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| frameId | [FrameId](#frameid) | 已分离的帧的 ID。 |  

---  

### <a name="framenavigated"></a>frameNavigated  

帧导航完成后触发。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| frame | [帧](#frame) | Frame 对象。 |  

---  

### <a name="loadeventfired"></a>loadEventFired  

对应于 `window.onload` 事件。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| timestamp | `number` | 自纪元以来的毫秒数。 |  

---  

### <a name="domcontenteventfired"></a>domContentEventFired  

对应于 `document.onDOMContentLoaded` 事件。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| timestamp | `number` | 自纪元以来的毫秒数。 |  

---  

## <a name="types"></a>类型  

### <a name="frameid-string"></a>FrameId 字符串  

<a name="frameid"></a>  

唯一的帧标识符。  

&nbsp;  

---  

### <a name="frame-object"></a>Frame 对象  

<a name="frame"></a>  

有关页面上框架的信息。  

| 属性 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| id | [FrameId](#frameid) | 帧唯一标识符。 |  
| parentId \ (optional\)  | [FrameId](#frameid) | 父帧唯一标识符。 |  
| name \ (optional\)  | `string` | 标记中指定的框架名称。 |  
| url | `string` | 框架文档的 URL。 |  
| securityOrigin | `string` | 框架文档的安全来源。 |  
| mimeType | `string` | 框架文档的 mimeType，由浏览器确定。 |  

---  

### <a name="frametree-object"></a>FrameTree 对象  

<a name="frametree"></a>  

有关 Frame 层次结构的信息。  

| 属性 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| frame | [帧](#frame) | 此树项的框架信息。 |  
| childFrames \ (optional\)  | [FrameTree[]](#frametree) | 子框架。 |  

---  
