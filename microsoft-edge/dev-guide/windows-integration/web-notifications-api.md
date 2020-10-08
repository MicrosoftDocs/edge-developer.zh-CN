---
ms.assetid: 2ecc762c-11a5-4b16-9aed-22606c1d4994
description: 了解如何使用 Web 通知 API 让网站在 Microsoft Edge 浏览器上下文之外发送用户通知。
title: Web 通知 API-开发指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 24b8a7b25fb3e0f0221f6d81b105d5d0374ea423
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941799"
---
# Web 通知 API  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Web 通知 API 允许网站在 Microsoft Edge 浏览器内的网页上下文之外发送用户通知。  此功能的一个示例是使用 Skype 等消息应用程序。  当用户收到一条新消息时，将在其桌面上显示一条通知，提醒他们显示消息。  Web 通知与 Windows 10 中的通知平台和操作中心完全集成。  

## 创建通知  

以下 CodePen 通过使用 "[标题](https://msdn.microsoft.com/library/mt710826)"、"[图标](https://msdn.microsoft.com/library/mt710814)" 和 "[正文](https://msdn.microsoft.com/library/mt710811)" 选项设置的[通知](https://msdn.microsoft.com/library/mt710818)对象来创建模拟 Skype 通知：  

<iframe height='295' scrolling='no' title='Web 通知' src='//codepen.io/MicrosoftEdgeDocumentation/embed/RGbxWW/?height=295&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'> </a> 在 CodePen 上查看 Microsoft Edge 文档 (@MicrosoftEdgeDocumentation) 的 Web 通知 <a href='https://codepen.io/MicrosoftEdgeDocumentation'> </a> <a href='https://codepen.io'> </a> 。</iframe>  

强烈建议为每个通知指定一个 **图标** 。  这不仅提高了来自用户界面点的通知，还有助于提醒用户发送通知的位置。  

观看以下视频，了解有关创建 web 通知和查看它在 Windows 10 中的行为的演练！  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Implementing-Web-Notifications/player]  

### 通知属性  

可通过以下属性设置通知：  

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
      通知的 URL，用于其图标。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [l](https://developer.mozilla.org/docs/Web/API/Notification/lang)  
   :::column-end:::
   :::column span="2":::
      通知的语言。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [权限](https://developer.mozilla.org/docs/Web/API/Notification/permission)  
   :::column-end:::
   :::column span="2":::
      用户为当前来源授予的当前通知显示权限。  
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

以下事件与 [通知](https://developer.mozilla.org/docs/Web/API/Notification) 对象一起使用：  

:::row:::
   :::column span="1":::
      [onclick](https://developer.mozilla.org/docs/Web/API/Element/click_event)  
   :::column-end:::
   :::column span="2":::
      当用户单击通知时激发。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [onclose](https://developer.mozilla.org/docs/Archive/Mozilla/XUL/Events/close_event)  
   :::column-end:::
   :::column span="2":::
      当用户关闭通知或自动超时时激发。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [onerror](https://developer.mozilla.org/docs/Web/API/Element/error_event)  
   :::column-end:::
   :::column span="2":::
      在处理通知的过程中发生错误时激发。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [onshow](https://developer.mozilla.org/docs/Web/API/Element/show_event)  
   :::column-end:::
   :::column span="2":::
      在显示通知时激发。  
   :::column-end:::
:::row-end:::  

### 通知方法  

将以下方法与 [通知](https://developer.mozilla.org/docs/Web/API/Notification) 对象结合使用：  

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
      请求用户的权限以允许当前来源显示通知。  
   :::column-end:::
:::row-end:::  

## 通知权限  

Microsoft Edge 允许用户管理每个特定网站域的通知权限。  当域要求您选择 "是" 或 "否" 以让其显示通知时，由用户选择 **"是" 或 "** **否** "。  [RequestPermission](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission)方法用于将权限状态指示为 `granted` 、、 `denied` 或 `default` 。  一个值 `default` 表示用户尚未做出决定，该决策被视为等效项 `denied` 。  

## API 参考  

[Web 通知](https://developer.mozilla.org/docs/Web/API/Notifications_API)  

## 书  

[Web 通知](https://notifications.spec.whatwg.org)  
