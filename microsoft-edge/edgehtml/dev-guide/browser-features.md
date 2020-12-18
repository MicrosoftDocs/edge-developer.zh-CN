---
ms.assetid: 4d3fa934-4fa8-4c02-b9b5-88506c76baac
description: Microsoft Edge 中的浏览器功能指南。
title: 浏览器 - 开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2579fad881496e2197f9f696bb2c12c47c7f723e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232563"
---
# <span data-ttu-id="f7a76-104">浏览器功能</span><span class="sxs-lookup"><span data-stu-id="f7a76-104">Browser features</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

## <span data-ttu-id="f7a76-105">自动播放策略</span><span class="sxs-lookup"><span data-stu-id="f7a76-105">Autoplay policies</span></span>  

 <span data-ttu-id="f7a76-106">Microsoft Edge 为客户提供了个性化浏览首选项的能力，这些首选项可以自动播放具有声音的媒体，以便最大程度地减少 Web 上的干扰并节省带宽。</span><span class="sxs-lookup"><span data-stu-id="f7a76-106">Microsoft Edge provides customers with the ability to personalize their browsing preferences on websites that autoplay media with sound in order to minimize distractions on the web and conserve bandwidth.</span></span>  <span data-ttu-id="f7a76-107">用户可以使用全局和每个站点自动播放控件自定义媒体行为。</span><span class="sxs-lookup"><span data-stu-id="f7a76-107">Users can customize media behavior with both global and per-site autoplay controls.</span></span>  <span data-ttu-id="f7a76-108">此外，Microsoft Edge 自动禁止在后台选项卡中自动播放媒体。</span><span class="sxs-lookup"><span data-stu-id="f7a76-108">Additionally, Microsoft Edge automatically suppresses autoplay of media in background tabs.</span></span>  

<span data-ttu-id="f7a76-109">查看 ["自动播放"](./browser-features/autoplay-policies.md) 策略，了解详细信息和最佳做法，以确保使用网站上托管的媒体获得良好的用户体验。</span><span class="sxs-lookup"><span data-stu-id="f7a76-109">Check out [Autoplay policies](./browser-features/autoplay-policies.md) for details and best practices to ensure a good user experience with media hosted on your site.</span></span>  

## <span data-ttu-id="f7a76-110">Flash</span><span class="sxs-lookup"><span data-stu-id="f7a76-110">Flash</span></span>  

<span data-ttu-id="f7a76-111">如果在页面上使用了 Flash，但用户尚未启用它，Microsoft Edge 通常会在地址栏中显示一个七字形图标。</span><span class="sxs-lookup"><span data-stu-id="f7a76-111">If Flash is used on your page but the user has not enabled it, Microsoft Edge will normally show a puzzle piece icon in the address bar.</span></span>  <span data-ttu-id="f7a76-112">如果你在加载页面后动态添加 Flash 控件，则问题图标可能不会显示，在这种情况下，你需要测试 Flash 是否加载，如果 Flash[](./browser-features/flash.md)不存在，则提供流畅的回退体验。</span><span class="sxs-lookup"><span data-stu-id="f7a76-112">If you are dynamically adding the Flash control after the page is loaded, the puzzle icon may not display, in which case you'll want to [test if Flash is loaded and provide a graceful fallback experience](./browser-features/flash.md) if its not present.</span></span>  

## <span data-ttu-id="f7a76-113">阅读视图</span><span class="sxs-lookup"><span data-stu-id="f7a76-113">Reading view</span></span>  

<span data-ttu-id="f7a76-114">Microsoft Edge 提供了一个阅读 [视图](./browser-features/reading-view.md) ，以便实现更简化、更像书籍的网页阅读体验，而不会分散页面上无关内容或其他辅助内容的干扰。</span><span class="sxs-lookup"><span data-stu-id="f7a76-114">Microsoft Edge provides a [reading view](./browser-features/reading-view.md) for a more streamlined, book-like reading experience of webpages, without the distraction of unrelated or other secondary content on the page.</span></span>  <span data-ttu-id="f7a76-115">下面提供了有关如何确保网站提供出色的阅读视图体验的提示，以及选择网站退出阅读视图的说明。</span><span class="sxs-lookup"><span data-stu-id="f7a76-115">Here are tips on how to ensure a great reading view experience with your site and also instructions for opting your site out of reading view.</span></span>  

## <span data-ttu-id="f7a76-116">搜索提供程序发现</span><span class="sxs-lookup"><span data-stu-id="f7a76-116">Search provider discovery</span></span>  

<span data-ttu-id="f7a76-117">丰富的搜索集成内置于 Microsoft Edge 地址栏中，包括搜索建议、来自 Web 的结果、浏览历史记录和收藏夹。</span><span class="sxs-lookup"><span data-stu-id="f7a76-117">Rich search integration is built into the Microsoft Edge address bar, including search suggestions, results from the web, your browsing history, and favorites.</span></span>  <span data-ttu-id="f7a76-118">[以下是希望为](./browser-features/search-provider-discovery.md) Microsoft Edge 提供支持的搜索提供程序的更多信息。</span><span class="sxs-lookup"><span data-stu-id="f7a76-118">[Here's more info for search providers](./browser-features/search-provider-discovery.md) looking to provide support for Microsoft Edge.</span></span>  
