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
# <a name="use-the-web-app-manifest-to-integrate-your-progressive-web-app-into-the-operating-system"></a><span data-ttu-id="28384-104">使用 Web 应用清单将渐进式 Web 应用集成到操作系统</span><span class="sxs-lookup"><span data-stu-id="28384-104">Use the Web App Manifest to integrate your Progressive Web App into the Operating System</span></span>

<span data-ttu-id="28384-105">网站的 Web 应用清单控制在设备上安装渐进式 Web App \(PWA\) 的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="28384-105">A Web App Manifest of a website governs how your Progressive Web App \(PWA\) looks and behaves when installed on a device.</span></span>  <span data-ttu-id="28384-106">在最基本的级别，清单提供有关应用名称、用于表示系统菜单中应用的图标以及主题颜色（操作系统 \(OS\) 在标题栏中使用）的详细信息。</span><span class="sxs-lookup"><span data-stu-id="28384-106">At the most basic level, the Manifest provides details on the name of your app, icons to use to represent your app in system menus, and the theme colors the operating system \(OS\) uses in the title bar.</span></span>  <span data-ttu-id="28384-107">清单还使你能够解锁强大的功能，使应用能够像系统上的其他本机应用一样运行。</span><span class="sxs-lookup"><span data-stu-id="28384-107">The Manifest also enables you to unlock powerful features that allow your app to behave like other native apps on the system.</span></span>  

## <a name="use-shortcuts-to-provide-quick-access-to-features"></a><span data-ttu-id="28384-108">使用快捷方式快速访问功能</span><span class="sxs-lookup"><span data-stu-id="28384-108">Use shortcuts to provide quick access to features</span></span>  

<span data-ttu-id="28384-109">大多数操作系统都使用连接到应用图标的上下文菜单上的快捷方式快速访问关键应用功能。</span><span class="sxs-lookup"><span data-stu-id="28384-109">Most operating systems provide quick access to key app features using shortcuts on the context menu connected to the icon of the app.</span></span>  <span data-ttu-id="28384-110">若要在 PWA 中使用快捷方式，请包含 `shortcuts` Web 应用清单中的属性。</span><span class="sxs-lookup"><span data-stu-id="28384-110">To use shortcuts in your PWA, include the `shortcuts` property in your Web App Manifest.</span></span>  <span data-ttu-id="28384-111">以下代码段显示如何在 Web 应用清单中定义快捷方式。</span><span class="sxs-lookup"><span data-stu-id="28384-111">The following code snippet displays how to define a shortcut in your web app manifest.</span></span>  

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

<span data-ttu-id="28384-112">添加到完整的 Web 应用清单时，添加前面的代码段可在应用图标上的上下文菜单上启用两个快捷方式。</span><span class="sxs-lookup"><span data-stu-id="28384-112">When added to a complete Web App Manifest, adding the previous code snippet enables two shortcuts on the context menu on the icon of the app.</span></span>  <span data-ttu-id="28384-113">第一个名称已 `Play Later` 命名，并且具有自定义图标。</span><span class="sxs-lookup"><span data-stu-id="28384-113">The first is named `Play Later` and has a custom icon.</span></span>  <span data-ttu-id="28384-114">第二个属性已命名， `Subscriptions` 没有图标， `icons` 因为该属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="28384-114">The second is named `Subscriptions` and does not have an icon because the `icons` property is optional.</span></span>  <span data-ttu-id="28384-115">`description`该属性也是可选的，可用于为辅助功能提供其他信息。</span><span class="sxs-lookup"><span data-stu-id="28384-115">The `description` property is also optional and may be used to provide additional information for accessibility purposes.</span></span>  

## <a name="identify-your-app-as-a-share-target"></a><span data-ttu-id="28384-116">将应用标识为共享目标</span><span class="sxs-lookup"><span data-stu-id="28384-116">Identify your app as a Share Target</span></span>

<span data-ttu-id="28384-117">许多操作系统使用户能够快速与本机应用程序共享链接和文件。</span><span class="sxs-lookup"><span data-stu-id="28384-117">Many operating systems enable users to quickly share links and files with native applications.</span></span> <span data-ttu-id="28384-118">渐进式 Web 应用也可使用 Web 应用清单的成员参与 `share_target` 此功能。</span><span class="sxs-lookup"><span data-stu-id="28384-118">Progressive Web Apps can participate in this feature as well, using the `share_target` member of the Web App Manifest.</span></span>  <span data-ttu-id="28384-119">使用 `share_target` ，定义 `"action"` 页面 \(类似于 form\) 以及要传入的参数。</span><span class="sxs-lookup"><span data-stu-id="28384-119">Using `share_target`, you define the `"action"` page \(similar to a form\) and the parameters you expect to be passed into it.</span></span>  <span data-ttu-id="28384-120">下面的代码段显示了如何使用的示例 `share_target` 。</span><span class="sxs-lookup"><span data-stu-id="28384-120">The following code snippet displays an example of how to use `share_target`.</span></span>

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

<span data-ttu-id="28384-121">添加到 Web 应用清单时，这将建立 `"/share.html"` 为共享的操作页。</span><span class="sxs-lookup"><span data-stu-id="28384-121">When added to the Web App Manifest, this establishes `"/share.html"` as the action page for a share.</span></span> <span data-ttu-id="28384-122">此外，它还定义了将传递给该操作页的三个参数：和 `"title"` `"text"` `"url"` 。</span><span class="sxs-lookup"><span data-stu-id="28384-122">Additionally, it defines three parameters that would be passed to that action page:`"title"`, `"text"`, and `"url"`.</span></span>  <span data-ttu-id="28384-123">这些参数将存储在 ， 和 `"name"` `"description"` `"link"` [ShareData][GitHubWicgWebShareDomSharedata] 对象的属性中。</span><span class="sxs-lookup"><span data-stu-id="28384-123">These parameters will be stored in the `"name"`, `"description"`, and `"link"` properties of the [ShareData][GitHubWicgWebShareDomSharedata] object.</span></span>  <span data-ttu-id="28384-124">默认情况下，操作页作为 GET 请求的一部分接收参数，但 `method` 您可以将请求和编码 \(指定为 \) ，就像在 Web 表单上一样 `enctype` 。</span><span class="sxs-lookup"><span data-stu-id="28384-124">By default, the action page receives the parameters as part of a GET request, but you can specify the request `method` and encoding \(as `enctype`\), just like you would on a web form.</span></span>

## <a name="see-also"></a><span data-ttu-id="28384-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28384-125">See also</span></span>  

<span data-ttu-id="28384-126">若要了解有关 Web 应用清单的信息，请导航到以下相关主题列表。</span><span class="sxs-lookup"><span data-stu-id="28384-126">To learn more about Web App Manifests, navigate to the following list of related topics.</span></span>  

*   [<span data-ttu-id="28384-127">Web 应用清单</span><span class="sxs-lookup"><span data-stu-id="28384-127">Web App Manifests</span></span>][MDNWebAppManifests]  
*   [<span data-ttu-id="28384-128">Web 共享目标</span><span class="sxs-lookup"><span data-stu-id="28384-128">Web Share Target</span></span>][GitHubWicgWebShareTarget]
*   [<span data-ttu-id="28384-129">Web 共享</span><span class="sxs-lookup"><span data-stu-id="28384-129">Web Share</span></span>][GithubW3cWebShare]
    
<!-- links -->  

[MDNWebAppManifests]: https://developer.mozilla.org/docs/Web/Manifest "Web 应用清单|MDN"  

[GitHubWicgWebShareTarget]: https://wicg.github.io/web-share-target "Web 共享目标 API |WICG"
[GitHubWicgWebShareDomSharedata]: https://wicg.github.io/web-share#dom-sharedata "ShareData 字典 - Web 共享 API |WICG"  

[GithubW3cWebShare]: https://w3c.github.io/web-share/ "Web 共享 API |WICG"
