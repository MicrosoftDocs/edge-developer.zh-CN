---
ms.assetid: 2ecc762c-11a5-4b16-9aed-22606c1d4994
description: 了解如何使用 Web 通知 API 让网站在 Microsoft Edge 浏览器上下文之外发送用户通知。
title: 开发人员指南-Web 通知 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/18/2017
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: da563a333491ef699925adec6f97b3c21d3e54a0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562971"
---
# Web 通知 API

Web 通知 API 允许网站在 Microsoft Edge 浏览器内的网页上下文之外发送用户通知。 此功能的一个示例是使用 Skype 等消息应用程序。 当用户收到一条新消息时，将在其桌面上显示一条通知，提醒他们显示消息。 Web 通知与 Windows 10 中的通知平台和操作中心完全集成。 

## 创建通知

以下 CodePen 通过将对象设置为 "，" 和 "和" 选项来创建模拟 Skype 通知 [`Notification`](https://msdn.microsoft.com/library/mt710818) [`title`](https://msdn.microsoft.com/library/mt710826) [`icon`](https://msdn.microsoft.com/library/mt710814) [`body`](https://msdn.microsoft.com/library/mt710811) ：


<iframe height='295' scrolling='no' title='Web 通知' src='//codepen.io/MicrosoftEdgeDocumentation/embed/RGbxWW/?height=295&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'> </a> 在 CodePen 上的 Microsoft Edge 文档（ <a href='https://codepen.io/MicrosoftEdgeDocumentation'> @MicrosoftEdgeDocumentation </a> ）中查看 <a href='https://codepen.io'> 笔 Web 通知 </a> 。
</iframe>

强烈建议为 `icon` 每个通知指定一个。 这不仅提高了来自用户界面点的通知，还有助于提醒用户发送通知的位置。

观看以下视频，了解有关创建 web 通知和查看它在 Windows 10 中的行为的演练！


> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Implementing-Web-Notifications/player]

### 通知属性

可通过以下选项设置通知：

属性 | 描述
:-------- | :----------
[正文](https://msdn.microsoft.com/library/mt710811) | 通知的正文文本。
[dir](https://msdn.microsoft.com/library/mt710813) | 通知文本的方向。
[icon](https://msdn.microsoft.com/library/mt710814) | 通知的 URL，用于其图标。
[l](https://msdn.microsoft.com/library/mt710815) | 通知的语言。
[权限](https://msdn.microsoft.com/library/mt670637) | 用户为当前来源授予的当前通知显示权限。
[tag](https://msdn.microsoft.com/library/mt710825) | 通知的标记。
[title](https://msdn.microsoft.com/library/mt710826) | 通知的标题。

### 通知事件

以下事件与对象一起使用 [`Notification`](https://msdn.microsoft.com/library/mt710818) ：

事件 | 说明
:-------- | :----------
[onclick](https://msdn.microsoft.com/library/mt712180) | 当用户单击通知时激发。
[onclose](https://msdn.microsoft.com/library/mt712178) | 当用户关闭通知或自动超时时激发。
[onerror](https://msdn.microsoft.com/library/mt712181) | 在处理通知的过程中发生错误时激发。
[onshow](https://msdn.microsoft.com/library/mt712182) | 在显示通知时激发。

### 通知方法

将以下方法与对象配合使用 [`Notification`](https://msdn.microsoft.com/library/mt710818) ：

方法 | 描述
:-------- | :----------
[close](https://msdn.microsoft.com/library/mt670636) | 关闭显示的通知。
[requestPermission](https://msdn.microsoft.com/library/mt710824) | 请求用户的权限以允许当前来源显示通知。

## 通知权限

Microsoft Edge 允许用户管理每个特定网站域的通知权限。 当域要求用户显示通知时，用户可以选择 "是" 或 "否"。 此 [`requestPermission`](https://msdn.microsoft.com/library/mt710824) 方法用于将权限状态指示为 `granted` 、、 `denied` 或 `default` 。 一个值 `default` 表示用户尚未做出决定，该决策被视为等效项 `denied` 。




## API 参考

[Web 通知](https://msdn.microsoft.com/library/mt710827)

## 书

[Web 通知](https://notifications.spec.whatwg.org)
