---
title: 使用 Web 应用清单将渐进式 Web 应用集成到操作系统
description: 了解如何使用 Web 应用清单将渐进式 Web 应用集成到操作系统中。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: pwa
keywords: 渐进式 Web 应用， PWA， Edge， JavaScript， Windows， UWP， Microsoft Store
ms.openlocfilehash: 0063323b1fde94d84e70df51170726325dd0f2a9
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399097"
---
# <a name="use-the-web-app-manifest-to-integrate-your-progressive-web-app-into-the-operating-system"></a>使用 Web 应用清单将渐进式 Web 应用集成到操作系统

网站的 Web 应用清单控制在设备上安装渐进式 Web App \ (PWA\) 的外观和行为。  在最基本的级别，清单提供有关应用名称、用于表示系统菜单中应用的图标以及主题颜色（操作系统 \ (OS\) 在标题栏中使用）的详细信息。  清单还使你能够解锁强大的功能，使应用能够像系统上的其他本机应用一样运行。  

## <a name="use-shortcuts-to-provide-quick-access-to-features"></a>使用快捷方式快速访问功能  

大多数操作系统都使用连接到应用图标的上下文菜单上的快捷方式快速访问关键应用功能。  若要在 PWA 中使用快捷方式，请包含 `shortcuts` Web 应用清单中的属性。  以下代码段显示如何在 Web 应用清单中定义快捷方式。  

```json
"shortcuts": [
    {
        "name": "Play Later",
        "description": "View the list of podcasts you saved for later",
        "url": "/play-later",
        "icons": [
            {
                "src": "/icons/play-later.svg",
                "type": "image/svg+xml",
                "purpose": "any"
            }
        ]
    },
    {
        "name": "Subscriptions",
        "description": "View the list of podcasts available in your subscription",
        "url": "/subscriptions?sort=desc"
    }
]
```  

添加到完整的 Web 应用清单时，添加前面的代码段可在应用图标上的上下文菜单上启用两个快捷方式。  第一个名称已 `Play Later` 命名，并且具有自定义图标。  第二个属性已命名， `Subscriptions` 没有图标， `icons` 因为该属性是可选的。  `description`该属性也是可选的，可用于为辅助功能提供其他信息。  

## <a name="identify-your-app-as-a-share-target"></a>将应用标识为共享目标

许多操作系统使用户能够快速与本机应用程序共享链接和文件。 渐进式 Web 应用也可使用 Web 应用清单的成员参与 `share_target` 此功能。  使用 `share_target` ，定义 `"action"` 页面 \ (类似于 form\) 以及要传入的参数。  下面的代码段显示了如何使用的示例 `share_target` 。

```json
"share_target": {
    "action": "/share.html",
    "params": {
        "title": "name",
        "text": "description",
        "url": "link"
    }
}
```

添加到 Web 应用清单时，这将建立 `"/share.html"` 为共享的操作页。 此外，它还定义了将传递给该操作页的三个参数：和 `"title"` `"text"` `"url"` 。  这些参数将存储在 ， 和 `"name"` `"description"` `"link"` [ShareData][GitHubWicgWebShareDomSharedata] 对象的属性中。  默认情况下，操作页作为 GET 请求的一部分接收参数，但 `method` 您可以将请求和编码 \ (指定为 \) ，就像在 Web 表单上一样 `enctype` 。

## <a name="see-also"></a>另请参阅  

若要了解有关 Web 应用清单的信息，请导航到以下相关主题列表。  

*   [Web 应用清单][MDNWebAppManifests]  
*   [Web 共享目标][GitHubWicgWebShareTarget]
*   [Web 共享][GithubW3cWebShare]
    
<!-- links -->  

[MDNWebAppManifests]: https://developer.mozilla.org/docs/Web/Manifest "Web 应用清单|MDN"  

[GitHubWicgWebShareTarget]: https://wicg.github.io/web-share-target "Web 共享目标 API |WICG"
[GitHubWicgWebShareDomSharedata]: https://wicg.github.io/web-share#dom-sharedata "ShareData 字典 - Web 共享 API |WICG"  

[GithubW3cWebShare]: https://w3c.github.io/web-share/ "Web 共享 API |WICG"
