---
description: 在需要 Adobe Flash 的网站上提供无缝用户体验。
title: Flash - 开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， flash
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 9a81fb0808897e1763a55c3e97bc604d276a7b9f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232571"
---
# Flash  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

自 HTML5 引入以来，Adobe Flash 已成为 Web 的一个完整组成部分，自 HTML5 引入以来，在浏览器中启用丰富的内容和动画。  在新式浏览器中，Microsoft、Adobe、Google、Apple、Mozilla 和其他许多浏览器所规范的 Web 标准现在使网站无需 Flash 即可超过这些体验，并改进了性能和安全性。  与其他浏览器供应商和 Adobe 合作，我们强烈建议开发人员迁移到 HTML5 标准，包括加密媒体扩展[](https://developer.microsoft.com/microsoft-edge/platform/status/encryptedmediaextensions)、媒体源扩展、[画布](https://developer.microsoft.com/microsoft-edge/platform/status/canvas)[、Web](https://developer.microsoft.com/microsoft-edge/platform/status/webaudioapi)音频和实时[通信](https://developer.microsoft.com/microsoft-edge/platform/status/webrtcobjectrtcapi)。 [](https://developer.microsoft.com/microsoft-edge/platform/status/mediasourceextensions)  

随着 Windows 10 Microsoft Edge 的 2018 年 10 月[](https://blogs.windows.com/msedgedev/2017/07/25)版本继续我们作为[Adobe](https://theblog.adobe.com/adobe-flash-update) 2021 后停止提供支持公告的一部分涵盖的 Flash 弃用工作。  在 2018 年 10 月版本中，用户需要明确允许 Flash 在选项卡的生命周期内在站点上运行。 永久"始终允许"选项将不再可用，用户将无法管理跨选项卡会话的按站点 Flash 权限。  

当你过渡到 HTML5 标准时，你可以执行一些简单的操作，以确保你的用户仍可在 Windows 10 创意者更新中通过 Microsoft Edge 访问你的网站获得积极体验。  

如果在页面上使用 Flash，但用户尚未启用它，Microsoft Edge 通常会在地址栏中显示一个七字形图标，如此 [博客所示](https://blogs.windows.com/msedgedev/2016/12/14)。  如果在加载页面后动态添加 Flash 控件，可能不会显示此问题块图标。  在这种情况下，最好测试是否存在 Flash 并提供链接，如下所述。  

若要确保所有用户都有良好的体验，请继续使用标准机制测试是否存在 Flash。  如果 Microsoft Edge 报告 Flash 不可用，请向用户显示 [Flash 下载链接](http://get.adobe.com/flashplayer) 和 [Flash](http://www.adobe.com/legal/permissions/icons-web-logos.html#flashplayer) 下载映像。  当用户单击链接时，Microsoft Edge \ (以及其他浏览器\) 将显示为站点启用 Flash Player 所需的提示。  该链接必须显示在要启用 Flash 的主域上。  如果将用户重定向到其他域上的页面，它将不起作用。  [下面是建议体验和](https://microsoftedge.github.io/MicrosoftEdge-Documentation/flashclicktorun) 相应示例代码 [的演示](https://github.com/MicrosoftEdge/MicrosoftEdge-Documentation/tree/master/docs/flashclicktorun)。  
