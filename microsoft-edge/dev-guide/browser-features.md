---
ms.assetid: 4d3fa934-4fa8-4c02-b9b5-88506c76baac
description: Microsoft Edge 中浏览器功能的指南。
title: 浏览器 - 开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.openlocfilehash: 854b0e8ac057db3cc8b53af6205404d0841dfdb4
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942042"
---
# <span data-ttu-id="e2cce-104">浏览器功能</span><span class="sxs-lookup"><span data-stu-id="e2cce-104">Browser features</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

## <span data-ttu-id="e2cce-105">自动播放策略</span><span class="sxs-lookup"><span data-stu-id="e2cce-105">Autoplay policies</span></span>  

 <span data-ttu-id="e2cce-106">Microsoft Edge 为客户提供了在网站上个性化其浏览首选项的功能，这些媒体可自动播放媒体，以便最大程度地减少 Web 上的分词并节约带宽。</span><span class="sxs-lookup"><span data-stu-id="e2cce-106">Microsoft Edge provides customers with the ability to personalize their browsing preferences on websites that autoplay media with sound in order to minimize distractions on the web and conserve bandwidth.</span></span>  <span data-ttu-id="e2cce-107">用户可以使用全局和每个站点自动播放控件自定义媒体行为。</span><span class="sxs-lookup"><span data-stu-id="e2cce-107">Users can customize media behavior with both global and per-site autoplay controls.</span></span>  <span data-ttu-id="e2cce-108">此外，Microsoft Edge 会自动断放背景选项卡中的媒体自动播放。</span><span class="sxs-lookup"><span data-stu-id="e2cce-108">Additionally, Microsoft Edge automatically suppresses autoplay of media in background tabs.</span></span>  

<span data-ttu-id="e2cce-109">有关详细信息 [和最佳做法](./browser-features/autoplay-policies.md) ，请参阅"自动播放"策略以确保获得网站中托管媒体的良好用户体验。</span><span class="sxs-lookup"><span data-stu-id="e2cce-109">Check out [Autoplay policies](./browser-features/autoplay-policies.md) for details and best practices to ensure a good user experience with media hosted on your site.</span></span>  

## <span data-ttu-id="e2cce-110">Flash</span><span class="sxs-lookup"><span data-stu-id="e2cce-110">Flash</span></span>  

<span data-ttu-id="e2cce-111">如果在页面上使用 Flash，但用户尚未启用它，则 Microsoft Edge 通常会在地址栏中显示一个拼图饼图标。</span><span class="sxs-lookup"><span data-stu-id="e2cce-111">If Flash is used on your page but the user has not enabled it, Microsoft Edge will normally show a puzzle piece icon in the address bar.</span></span>  <span data-ttu-id="e2cce-112">如果要在页面加载页面后动态地添加 Flash 控件，可能不会显示拼图图标，在这种情况下，你将需要 [测试是否加载 Flash，并且在](./browser-features/flash.md) 未出现时提供优美的回退体验。</span><span class="sxs-lookup"><span data-stu-id="e2cce-112">If you are dynamically adding the Flash control after the page is loaded, the puzzle icon may not display, in which case you'll want to [test if Flash is loaded and provide a graceful fallback experience](./browser-features/flash.md) if its not present.</span></span>  

## <span data-ttu-id="e2cce-113">阅读视图</span><span class="sxs-lookup"><span data-stu-id="e2cce-113">Reading view</span></span>  

<span data-ttu-id="e2cce-114">Microsoft Edge 提供了 [阅读视图，可](./browser-features/reading-view.md) 更简化、更类似于书页的阅读体验，在页面上不会分不分发不相关或其他辅助内容的分开。</span><span class="sxs-lookup"><span data-stu-id="e2cce-114">Microsoft Edge provides a [reading view](./browser-features/reading-view.md) for a more streamlined, book-like reading experience of webpages, without the distraction of unrelated or other secondary content on the page.</span></span>  <span data-ttu-id="e2cce-115">下面是有关如何确保网站出色阅读视图体验的提示以及选择网站出阅读视图的说明。</span><span class="sxs-lookup"><span data-stu-id="e2cce-115">Here are tips on how to ensure a great reading view experience with your site and also instructions for opting your site out of reading view.</span></span>  

## <span data-ttu-id="e2cce-116">搜索提供程序发现</span><span class="sxs-lookup"><span data-stu-id="e2cce-116">Search provider discovery</span></span>  

<span data-ttu-id="e2cce-117">丰富搜索集成内置在 Microsoft Edge 地址栏中，包括搜索建议、来自 Web 的结果、浏览历史记录和收藏夹。</span><span class="sxs-lookup"><span data-stu-id="e2cce-117">Rich search integration is built into the Microsoft Edge address bar, including search suggestions, results from the web, your browsing history, and favorites.</span></span>  <span data-ttu-id="e2cce-118">[下面是关于需要向 Microsoft](./browser-features/search-provider-discovery.md) Edge 提供支持的搜索提供商的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e2cce-118">[Here's more info for search providers](./browser-features/search-provider-discovery.md) looking to provide support for Microsoft Edge.</span></span>  
