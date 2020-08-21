---
ms.assetid: 2ecc762c-11a5-4b16-9aed-22606c1d4994
description: 了解可如何使用 Web 通知 API 让网站在 Microsoft Edge 浏览器的上下文之外发送用户通知。
title: Web 通知 API - 开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.openlocfilehash: 24b8a7b25fb3e0f0221f6d81b105d5d0374ea423
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941799"
---
# Web 通知 API  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Web 通知 API 允许网站在 Microsoft Edge 浏览器内网页上下文之外发送用户通知。  此功能的操作示例将是一个消息应用程序（如 Skype）。  当用户收到新消息时，其桌面上会显示通知，通知他们收到消息。  Web 通知与通知平台及 Windows 10 内的操作中心完全集成。  

## 创建通知  

以下代码Pen 可通过将通知对象设置为标题、图标和[正文选项集来创建](https://msdn.microsoft.com/library/mt710811)Mock [icon](https://msdn.microsoft.com/library/mt710814)Skype 通知： [Notification](https://msdn.microsoft.com/library/mt710818) [title](https://msdn.microsoft.com/library/mt710826)  

<iframe height='295' scrolling='no' title='Web 通知' src='//codepen.io/MicrosoftEdgeDocumentation/embed/RGbxWW/?height=295&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>在 <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'> CodePen 上使用 </a> Microsoft Edge 来 <a href='https://codepen.io/MicrosoftEdgeDocumentation'> (@MicrosoftEdgeDocumentation </a>) @MicrosoftEdgeDocumentation Pen 来查看 Pen Web <a href='https://codepen.io'> 通知 </a> 。</iframe>  

强烈建议为每个 **通知** 指定一个图标。  这不仅仅能改进 UI 点中的通知，还有助于提高通知用户发送通知的位置。  

观看下面的视频，了解创建 Web 通知并查看其在 Windows 10 中行为的演练！  

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
      通知的文本的方向。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [icon](https://developer.mozilla.org/docs/Web/API/Notification/icon)  
   :::column-end:::
   :::column span="2":::
      通知的 URL 用于其图标。  
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
      [权限](https://developer.mozilla.org/docs/Web/API/Notification/permission)  
   :::column-end:::
   :::column span="2":::
      向用户授予当前原点的当前通知显示权限。  
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

以下事件与 Notification 对象一 [起](https://developer.mozilla.org/docs/Web/API/Notification) 使用：  

:::row:::
   :::column span="1":::
      [onclick](https://developer.mozilla.org/docs/Web/API/Element/click_event)  
   :::column-end:::
   :::column span="2":::
      当用户单击某个通知时触发。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [close](https://developer.mozilla.org/docs/Archive/Mozilla/XUL/Events/close_event)  
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
      处理通知时触发错误。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [onshow](https://developer.mozilla.org/docs/Web/API/Element/show_event)  
   :::column-end:::
   :::column span="2":::
      当通知显示时触发。  
   :::column-end:::
:::row-end:::  

### 通知方法  

以下方法与 Notification 对象一 [起使用](https://developer.mozilla.org/docs/Web/API/Notification) ：  

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
      请求用户的权限，以允许当前来源显示通知。  
   :::column-end:::
:::row-end:::  

## 通知权限  

Microsoft Edge 允许用户管理每个特定网站域的通知权限。  如果域要求显示通知，用户可以**选择"** 是"或**No**"否" 以使其显示通知。  [requestPermission](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission)方法用于对权限状态进行签名，或者 `granted` `denied` `default` 。  一个值，指示用户尚未做出决定，该决策 `default` 被视为相当于等效项 `denied` 。  

## API 参考  

[Web 通知](https://developer.mozilla.org/docs/Web/API/Notifications_API)  

## 规范  

[Web 通知](https://notifications.spec.whatwg.org)  
