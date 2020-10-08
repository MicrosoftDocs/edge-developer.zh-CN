---
description: 在需要 Adobe Flash 的网站上提供无缝的用户体验。
title: Flash-开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、flash
ms.openlocfilehash: 33ee1c782fc969b2251ed075a59d8fa61bf61831
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942033"
---
# Flash  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Adobe Flash 已成为 web 的一个重要部分，在引入 HTML5 之前，在浏览器中启用丰富的内容和动画。  在新式浏览器中，Microsoft、Adobe、Google、Apple、Mozilla 以及其他许多人所采用的 web 标准现在使网站能够在没有 Flash 的情况下超过这些体验，并且提高了性能和安全性。  与其他浏览器供应商和 Adobe 协作，我们强烈鼓励开发人员迁移到 HTML5 标准，包括 [加密媒体扩展](https://developer.microsoft.com/microsoft-edge/platform/status/encryptedmediaextensions)、 [媒体源扩展](https://developer.microsoft.com/microsoft-edge/platform/status/mediasourceextensions)、 [画布](https://developer.microsoft.com/microsoft-edge/platform/status/canvas)、 [Web 音频](https://developer.microsoft.com/microsoft-edge/platform/status/webaudioapi)和 [实时通信](https://developer.microsoft.com/microsoft-edge/platform/status/webrtcobjectrtcapi)。  

在2018年10月推出的 Windows 10 Edge 中，Microsoft Edge 将继续进行 "Flash 弃用" 的工作 [，我们将在 2021](https://blogs.windows.com/msedgedev/2017/07/25) 后继续推出 [Adobe 的支持公告](https://theblog.adobe.com/adobe-flash-update) 。  在 Oct 2018 中，用户将需要在选项卡的生命周期内明确允许 Flash 在网站上运行。 永久的 "始终允许" 选项将不再可用，并且用户将无法管理跨选项卡会话的每个网站 Flash 权限。  

当你向 HTML5 标准过渡时，你可以执行一些简单的操作，以确保你的用户在 Windows 10 创意者更新中使用 Microsoft Edge 访问你的网站时仍有积极的体验。  

如果在页面上使用 Flash，但用户尚未启用，则 Microsoft Edge 通常会在地址栏中显示拼图部分图标，如 [本博客](https://blogs.windows.com/msedgedev/2016/12/14)所示。  如果在加载页面后动态添加 Flash 控件，则可能不会显示此拼图部分图标。  在这种情况下，最好测试是否存在 Flash，并提供如下所述的链接。  

为确保所有用户都有良好的体验，请使用标准机制继续测试是否存在 Flash。  如果 Microsoft Edge 报告该 Flash 不可用，则向用户显示 [flash 下载链接](http://get.adobe.com/flashplayer) 和 [flash 下载图像](http://www.adobe.com/legal/permissions/icons-web-logos.html#flashplayer) 。  当用户单击链接时，Microsoft Edge \ (和其他浏览器 \ ) 将演示为网站启用 Flash Player 所需的提示。  该链接必须出现在要启用 Flash 的主域上。  如果将用户重定向到其他域上的页面，则不起作用。  [下面](https://microsoftedge.github.io/MicrosoftEdge-Documentation/flashclicktorun) 是建议的体验和对应的 [示例代码](https://github.com/MicrosoftEdge/MicrosoftEdge-Documentation/tree/master/docs/flashclicktorun)的演示。  
