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
# <span data-ttu-id="e5f8f-104">使用 Web 应用清单将渐进式 Web 应用集成到操作系统中</span><span class="sxs-lookup"><span data-stu-id="e5f8f-104">Use the Web App Manifest to integrate your Progressive Web App into the Operating System</span></span>

<span data-ttu-id="e5f8f-105">网站的 Web 应用清单控制在设备上安装时的渐进式 Web 应用（PWA）的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-105">A Web App Manifest of a website governs how your Progressive Web App \(PWA\) looks and behaves when installed on a device.</span></span>  <span data-ttu-id="e5f8f-106">在最基本的级别上，清单提供有关你的应用的名称、用于在系统菜单中表示你的应用的图标以及操作系统 \ （OS \）在标题栏中使用的主题颜色的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-106">At the most basic level, the Manifest provides details on the name of your app, icons to use to represent your app in system menus, and the theme colors the operating system \(OS\) uses in the title bar.</span></span>  <span data-ttu-id="e5f8f-107">清单还使你能够解锁功能，从而允许你的应用与系统上的其他本机应用的行为类似。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-107">The Manifest also enables you to unlock powerful features that allow your app to behave like other native apps on the system.</span></span>  

## <span data-ttu-id="e5f8f-108">使用快捷方式提供对功能的快速访问</span><span class="sxs-lookup"><span data-stu-id="e5f8f-108">Use shortcuts to provide quick access to features</span></span>  

<span data-ttu-id="e5f8f-109">大多数操作系统通过连接到应用图标的上下文菜单上的快捷方式，提供对关键应用功能的快速访问。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-109">Most operating systems provide quick access to key app features using shortcuts on the context menu connected to the icon of the app.</span></span>  <span data-ttu-id="e5f8f-110">若要在 PWA 中使用快捷方式，请 `shortcuts` 在 Web 应用清单中包含该属性。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-110">To use shortcuts in your PWA, include the `shortcuts` property in your Web App Manifest.</span></span>  <span data-ttu-id="e5f8f-111">以下代码片段显示了如何在 web 应用清单中定义快捷方式。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-111">The following code snippet shows how to define a shortcut in your web app manifest.</span></span>  

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

<span data-ttu-id="e5f8f-112">添加到完整的 Web 应用清单时，添加前面的代码片段可在应用图标上的上下文菜单上启用两个快捷方式。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-112">When added to a complete Web App Manifest, adding the previous code snippet enables two shortcuts on the context menu on the icon of the app.</span></span>  <span data-ttu-id="e5f8f-113">第一个命名 `Play Later` 并具有自定义图标。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-113">The first is named `Play Later` and has a custom icon.</span></span>  <span data-ttu-id="e5f8f-114">第二个命名 `Subscriptions` 和没有图标，因为该 `icons` 属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-114">The second is named `Subscriptions` and does not have an icon because the `icons` property is optional.</span></span>  <span data-ttu-id="e5f8f-115">该 `description` 属性也是可选的，可用于提供辅助功能的其他信息。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-115">The `description` property is also optional and may be used to provide additional information for accessibility purposes.</span></span>  

## <span data-ttu-id="e5f8f-116">将你的应用标识为共享目标</span><span class="sxs-lookup"><span data-stu-id="e5f8f-116">Identify your app as a Share Target</span></span>

<span data-ttu-id="e5f8f-117">许多操作系统使用户能够使用本机应用程序快速共享链接和文件。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-117">Many operating systems enable users to quickly share links and files with native applications.</span></span> <span data-ttu-id="e5f8f-118">累进 Web 应用还可通过 `share_target` Web 应用清单的成员参与此功能。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-118">Progressive Web Apps can participate in this feature as well, via the `share_target` member of the Web App Manifest.</span></span> <span data-ttu-id="e5f8f-119">使用 share_target，定义 "操作" 页（类似于窗体）和预期传递到其中的参数。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-119">Using share_target, you define the "action" page (similar to a form) and the parameters you expect to be passed into it.</span></span> <span data-ttu-id="e5f8f-120">以下代码片段显示了如何使用的示例 `share_target` 。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-120">The following code snippet shows an example of how to use `share_target`.</span></span>

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

<span data-ttu-id="e5f8f-121">添加到 Web 应用部件清单时，会将 "/share.html" 确定为共享的操作页面。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-121">When added to the Web App Manifest, this establishes "/share.html" as the action page for a share.</span></span> <span data-ttu-id="e5f8f-122">此外，它还定义将传递到该操作页面的三个参数： "title"、"text" 和 "url"。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-122">Additionally, it defines three parameters that would be passed to that action page: "title", "text", and "url".</span></span> <span data-ttu-id="e5f8f-123">这些参数将存储在[ShareData](https://wicg.github.io/web-share#dom-sharedata)对象的 "name"、"description" 和 "link" 属性中。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-123">These parameters will be stored in the [ShareData](https://wicg.github.io/web-share#dom-sharedata) object’s "name", "description", and "link" properties.</span></span> <span data-ttu-id="e5f8f-124">默认情况下，操作页面接收这些参数作为 GET 请求的一部分，但你可以 `method` 像处理 web 窗体一样指定请求和编码 \ （as `enctype` \）。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-124">By default, the action page receives these parameters as part of a GET request, but you can specify the request `method` and encoding \(as `enctype`\), just like you would on a web form.</span></span>

## <span data-ttu-id="e5f8f-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5f8f-125">See also</span></span>  

<span data-ttu-id="e5f8f-126">若要了解有关 Web 应用清单的详细信息，请参阅以下相关主题列表。</span><span class="sxs-lookup"><span data-stu-id="e5f8f-126">To learn more about Web App Manifests, see the following list of related topics.</span></span>  

* [<span data-ttu-id="e5f8f-127">Web 应用清单</span><span class="sxs-lookup"><span data-stu-id="e5f8f-127">Web App Manifests</span></span>][MDNWebAppManifests]  
* [<span data-ttu-id="e5f8f-128">Web 共享目标</span><span class="sxs-lookup"><span data-stu-id="e5f8f-128">Web Share Target</span></span>][WICGShareTarget]
* [<span data-ttu-id="e5f8f-129">Web 共享</span><span class="sxs-lookup"><span data-stu-id="e5f8f-129">Web Share</span></span>][WICGShare]

<!-- links -->  

[MDNWebAppManifests]: https://developer.mozilla.org/docs/Web/Manifest "Web 应用清单 |MDN"  
[WICGShareTarget]: https://wicg.github.io/web-share-target/ "Web 共享目标 API |WICG"
[WICGShare]: https://w3c.github.io/web-share/ "Web 共享 API |WICG"
