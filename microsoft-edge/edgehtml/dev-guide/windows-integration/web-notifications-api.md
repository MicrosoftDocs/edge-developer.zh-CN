---
ms.assetid: 2ecc762c-11a5-4b16-9aed-22606c1d4994
description: 了解如何使用 Web 通知 API 让网站在 Microsoft Edge 浏览器上下文之外向用户发送通知。
title: Web 通知 API - 开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2be201a790c6fca1526c8b6eb13e4203e8e53206
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232494"
---
# Web 通知 API  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Web 通知 API 允许网站在 Microsoft Edge 浏览器内的网页上下文之外向用户发送通知。  此功能的一个操作示例是使用 Skype 等邮件应用程序。  当用户收到新邮件时，其桌面上会显示一条通知，提醒他们收到该邮件。  Web 通知与 Windows 10 中的通知平台和操作中心完全集成。  

## 创建通知  

下面的 CodePen 通过设置标题、图标和正文选项的[Notification](https://msdn.microsoft.com/library/mt710818)对象来创建[](https://msdn.microsoft.com/library/mt710814)模拟 Skype[](https://msdn.microsoft.com/library/mt710811)通知： [](https://msdn.microsoft.com/library/mt710826)  

<iframe height='295' scrolling='no' title='Web 通知' src='//codepen.io/MicrosoftEdgeDocumentation/embed/RGbxWW/?height=295&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>请参阅 <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'> CodePen 上的 Microsoft Edge 文档 (@MicrosoftEdgeDocumentation) </a> 笔 <a href='https://codepen.io/MicrosoftEdgeDocumentation'> Web </a> <a href='https://codepen.io'> 通知 </a> 。</iframe>  

强烈建议为每个通知指定一个**** 图标。  这不仅从 UI 角度改进了通知，还有助于提醒用户通知发送位置。  

请观看下面的视频，了解创建 Web 通知的演练，并查看 Windows 10 中的行为！  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Implementing-Web-Notifications/player]  

### 通知属性  

可以使用以下属性设置通知：  

:::row:::
   :::column span="1":::
      [正文](https://developer.mozilla.org/docs/Web/API/Notification/body)  
   :::column-end:::
   :::column span="2":::
      通知的正文文本。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [dir](https://developer.mozilla.org/docs/Web/API/Notification/dir)  
   :::column-end:::
   :::column span="2":::
      通知文本的方向。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [icon](https://developer.mozilla.org/docs/Web/API/Notification/icon)  
   :::column-end:::
   :::column span="2":::
      通知用于其图标的 URL。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [lang](https://developer.mozilla.org/docs/Web/API/Notification/lang)  
   :::column-end:::
   :::column span="2":::
      通知的语言。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [permission](https://developer.mozilla.org/docs/Web/API/Notification/permission)  
   :::column-end:::
   :::column span="2":::
      用户为当前源授予的当前通知显示权限。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [tag](https://developer.mozilla.org/docs/Web/API/Notification/tag)  
   :::column-end:::
   :::column span="2":::
      通知的标记。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [title](https://developer.mozilla.org/docs/Web/API/Notification/title)  
   :::column-end:::
   :::column span="2":::
      通知的标题。  
   :::column-end:::
:::row-end:::  

### 通知事件  

下列事件与 Notification 对象 [一](https://developer.mozilla.org/docs/Web/API/Notification) 同使用：  

:::row:::
   :::column span="1":::
      [onclick](https://developer.mozilla.org/docs/Web/API/Element/click_event)  
   :::column-end:::
   :::column span="2":::
      当用户单击通知时触发。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [onclose](https://developer.mozilla.org/docs/Archive/Mozilla/XUL/Events/close_event)  
   :::column-end:::
   :::column span="2":::
      当用户关闭通知或自动超时时触发。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [onerror](https://developer.mozilla.org/docs/Web/API/Element/error_event)  
   :::column-end:::
   :::column span="2":::
      在处理通知时发生错误时触发。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [onshow](https://developer.mozilla.org/docs/Web/API/Element/show_event)  
   :::column-end:::
   :::column span="2":::
      当显示通知时触发。  
   :::column-end:::
:::row-end:::  

### 通知方法  

下列方法用于 [Notification](https://developer.mozilla.org/docs/Web/API/Notification) 对象：  

:::row:::
   :::column span="1":::
      [close](https://developer.mozilla.org/docs/Web/API/Notification/close)  
   :::column-end:::
   :::column span="2":::
      关闭显示的通知。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [requestPermission](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission)  
   :::column-end:::
   :::column span="2":::
      请求用户的权限以允许当前源显示通知。  
   :::column-end:::
:::row-end:::  

## 通知权限  

Microsoft Edge 允许用户管理每个特定网站域的通知权限。  由用户决定在域要求它显示通知时**** 选择"**** 是"或"否"。  [requestPermission](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission)方法用于将权限状态表示为 ，或 `granted` `denied` `default` 。  值指示用户尚未做出决策， `default` 这被视为等效于 `denied` 。  

## API 参考  

[Web 通知](https://developer.mozilla.org/docs/Web/API/Notifications_API)  

## 规范  

[Web 通知](https://notifications.spec.whatwg.org)  
