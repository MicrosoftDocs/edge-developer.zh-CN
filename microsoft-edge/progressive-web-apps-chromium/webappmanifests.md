---
title: 使用 Web 应用清单将渐进式 Web 应用集成到操作系统中
description: 了解如何使用 Web 应用清单将渐进式 Web 应用集成到操作系统中。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/15/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: pwa
keywords: 渐进式 web 应用、PWA、Edge、JavaScript、Windows、UWP、Microsoft Store
ms.openlocfilehash: f493ae0c3cef3a1950b2207d66fef65055b2d959
ms.sourcegitcommit: d9cc829deb709b0866f6b43a5f4733682ddae5ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "10659291"
---
# 使用 Web 应用清单将渐进式 Web 应用集成到操作系统中

网站的 Web 应用清单控制在设备上安装时的渐进式 Web 应用（PWA）的外观和行为。  在最基本的级别上，清单提供有关你的应用的名称、用于在系统菜单中表示你的应用的图标以及操作系统 \ （OS \）在标题栏中使用的主题颜色的详细信息。  清单还使你能够解锁功能，从而允许你的应用与系统上的其他本机应用的行为类似。  

## 使用快捷方式提供对功能的快速访问  

大多数操作系统通过连接到应用图标的上下文菜单上的快捷方式，提供对关键应用功能的快速访问。  若要在 PWA 中使用快捷方式，请 `shortcuts` 在 Web 应用清单中包含该属性。  以下代码片段显示了如何在 web 应用清单中定义快捷方式。  

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

添加到完整的 Web 应用清单时，添加前面的代码片段可在应用图标上的上下文菜单上启用两个快捷方式。  第一个命名 `Play Later` 并具有自定义图标。  第二个命名 `Subscriptions` 和没有图标，因为该 `icons` 属性是可选的。  该 `description` 属性也是可选的，可用于提供辅助功能的其他信息。  

## 将你的应用标识为共享目标

许多操作系统使用户能够使用本机应用程序快速共享链接和文件。 累进 Web 应用还可通过 `share_target` Web 应用清单的成员参与此功能。 使用 share_target，定义 "操作" 页（类似于窗体）和预期传递到其中的参数。 以下代码片段显示了如何使用的示例 `share_target` 。

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

添加到 Web 应用部件清单时，会将 "/share.html" 确定为共享的操作页面。 此外，它还定义将传递到该操作页面的三个参数： "title"、"text" 和 "url"。 这些参数将存储在[ShareData](https://wicg.github.io/web-share#dom-sharedata)对象的 "name"、"description" 和 "link" 属性中。 默认情况下，操作页面接收这些参数作为 GET 请求的一部分，但你可以 `method` 像处理 web 窗体一样指定请求和编码 \ （as `enctype` \）。

## 另请参阅  

若要了解有关 Web 应用清单的详细信息，请参阅以下相关主题列表。  

* [Web 应用清单][MDNWebAppManifests]  
* [Web 共享目标][WICGShareTarget]
* [Web 共享][WICGShare]

<!-- links -->  

[MDNWebAppManifests]: https://developer.mozilla.org/docs/Web/Manifest "Web 应用清单 |MDN"  
[WICGShareTarget]: https://wicg.github.io/web-share-target/ "Web 共享目标 API |WICG"
[WICGShare]: https://w3c.github.io/web-share/ "Web 共享 API |WICG"
