---
description: 确保网站上的媒体内容按预期运行
title: 自动播放策略 - 开发用户指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、媒体、视频、音频、自动播放
ms.custom: seodec18
ms.openlocfilehash: 39c9bd8e9921167dfc3a9ab1a4cc12b2157f0f6f
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942058"
---
# <span data-ttu-id="d1735-104">自动播放策略</span><span class="sxs-lookup"><span data-stu-id="d1735-104">Autoplay Policies</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="d1735-105">Microsoft Edge 为客户提供了在网站上个性化其浏览首选项的功能，这些媒体可自动播放媒体，以便最大程度地减少 Web 上的分词并节约带宽。</span><span class="sxs-lookup"><span data-stu-id="d1735-105">Microsoft Edge provides customers with the ability to personalize their browsing preferences on websites that autoplay media with sound in order to minimize distractions on the web and conserve bandwidth.</span></span>  <span data-ttu-id="d1735-106">此外，Microsoft Edge 会自动断放背景选项卡中的媒体自动播放。</span><span class="sxs-lookup"><span data-stu-id="d1735-106">Additionally, Microsoft Edge automatically suppresses autoplay of media in background tabs.</span></span>  

<span data-ttu-id="d1735-107">用户可以使用全局和每个站点的自动播放控件[global](#global-media-autoplay-settings)自定义媒体行为[per-site](#per-site-media-autoplay-settings)，这些控件提供以下选项：</span><span class="sxs-lookup"><span data-stu-id="d1735-107">Users can customize media behavior with both [global](#global-media-autoplay-settings) and [per-site](#per-site-media-autoplay-settings) autoplay controls, which provide the following options:</span></span>  

*   `Allow`  <span data-ttu-id="d1735-108">当在前台查看选项卡时，默认状态，并继续播放视频。</span><span class="sxs-lookup"><span data-stu-id="d1735-108">The default and will continue to play videos when a tab is first viewed in the foreground, at the site's discretion.</span></span>  

*   `Limit`  <span data-ttu-id="d1735-109">仅在视频静音时限制自动播放功能才能正常工作，因此用户绝对不会被声音所打扰。</span><span class="sxs-lookup"><span data-stu-id="d1735-109">Restricts autoplay to only work when videos are muted, so users are never surprised by sound.</span></span>  <span data-ttu-id="d1735-110">用户单击页面上任意位置后，将重新启用自动播放，并且将继续允许在该选项卡上该域内进行允许。</span><span class="sxs-lookup"><span data-stu-id="d1735-110">Once the user clicks anywhere on the page, autoplay is re-enabled, and will continue to be allowed within that domain in that tab.</span></span>  

*   `Block`  <span data-ttu-id="d1735-111">禁止在所有网站上进行无关播放，直到用户直接与媒体内容进行交互。</span><span class="sxs-lookup"><span data-stu-id="d1735-111">Prevent sautoplay on all sites until users directly interact with the media content.</span></span>  

## <span data-ttu-id="d1735-112">全局媒体自动播放设置</span><span class="sxs-lookup"><span data-stu-id="d1735-112">Global media autoplay settings</span></span>  

<span data-ttu-id="d1735-113">用户可以控制"高级设置媒体自动播放"下的所有**网站的默认自动播放**  >  **行为**。</span><span class="sxs-lookup"><span data-stu-id="d1735-113">Users can control the default autoplay behavior for all sites under **Advanced Setting** > **Media autoplay**.</span></span>  

:::image type="complex" source="../media/autoplay_global.png" alt-text="全局媒体自动播放设置" lightbox="../media/autoplay_global.png":::
   <span data-ttu-id="d1735-115">全局媒体自动播放设置</span><span class="sxs-lookup"><span data-stu-id="d1735-115">Global media autoplay settings</span></span>  
:::image-end:::  

## <span data-ttu-id="d1735-116">站点媒体自动播放设置</span><span class="sxs-lookup"><span data-stu-id="d1735-116">Per-site media autoplay settings</span></span>  

<span data-ttu-id="d1735-117">用户可以基于网站共享信息窗格的" **网站权限"** 部分控制自动播放操作。</span><span class="sxs-lookup"><span data-stu-id="d1735-117">Users can control autoplay behavior on a per-site basis under the **Website permissions** section of the website information pane.</span></span>  <span data-ttu-id="d1735-118">可通过单击地址栏左侧的信息图标或锁图标并单击媒体自动播放设置以开始设置 **，找到** 此设置。</span><span class="sxs-lookup"><span data-stu-id="d1735-118">This setting can be found by clicking the information icon or lock icon on the left side of the address bar and clicking on **Media autoplay settings** to get started.</span></span>  

<span data-ttu-id="d1735-119">每网站设置将覆盖全局设置。</span><span class="sxs-lookup"><span data-stu-id="d1735-119">Per-site settings override the global setting.</span></span>  <span data-ttu-id="d1735-120">例如，如果用户已将其全局设置设为"全局"， `Allow` 但将针对该网站将阻止 `Block` 自动播放。</span><span class="sxs-lookup"><span data-stu-id="d1735-120">For example, if a user has their global setting set to `Allow` but changes a per-site setting to `Block`, autoplay will be blocked for that site.</span></span>  

:::image type="complex" source="../media/autoplay_per-site.png" alt-text="站点媒体自动播放设置" lightbox="../media/autoplay_per-site.png":::
   <span data-ttu-id="d1735-122">站点媒体自动播放设置</span><span class="sxs-lookup"><span data-stu-id="d1735-122">Per-site media autoplay settings</span></span>  
:::image-end:::  

## <span data-ttu-id="d1735-123">Web 开发人员的最佳实践</span><span class="sxs-lookup"><span data-stu-id="d1735-123">Best Practices for Web Developers</span></span>  

<span data-ttu-id="d1735-124">下面介绍如何确保网站上托管的媒体获得良好用户体验：</span><span class="sxs-lookup"><span data-stu-id="d1735-124">Here's how to ensure a good user experience with media hosted on your site:</span></span>  

*   <span data-ttu-id="d1735-125">假设媒体元素的每个使用都要求用户手势才能启动播放 \ (，可能是用户随时在任何时间\) 阻止自动播放并相应地进行相应规划。</span><span class="sxs-lookup"><span data-stu-id="d1735-125">Assume each use of a media element wil require a user gesture to start the playback \(as users can block autoplay at any point in time\) and plan accordingly.</span></span>  <span data-ttu-id="d1735-126">全局和每网站自动播放策略适用于所有和元素，无受这些策略 `<audio>` 在您的网站 `<video>` 上的使用方式</span><span class="sxs-lookup"><span data-stu-id="d1735-126">Global and per-site autoplay policies apply to all `<audio>` and `<video>` elements, regardless of how they are used on your site</span></span>  

*   <span data-ttu-id="d1735-127">确保媒体控件始终显示在网站媒体和广告内容上。</span><span class="sxs-lookup"><span data-stu-id="d1735-127">Ensure that media controls are always present on both site media and ad content.</span></span>  <span data-ttu-id="d1735-128">如果在页面上已被阻止了自动播放，这将使用户可以重新启动播放。</span><span class="sxs-lookup"><span data-stu-id="d1735-128">This will give users the ability to restart playback if autoplay is blocked on the page.</span></span>  

*   <span data-ttu-id="d1735-129">评估自动播放如何影响您的网站上的用户体验，并考虑使用减少不需要的媒体播放的方式使用自动播放功能。</span><span class="sxs-lookup"><span data-stu-id="d1735-129">Evaluate how autoplay may affect users' experience on your website and consider using autoplay in a way that minimizes unwanted media playback.</span></span>  <span data-ttu-id="d1735-130">如果自动播放是体验的关键部分，请考虑使用静音内容以启动，并允许用户取消静音。</span><span class="sxs-lookup"><span data-stu-id="d1735-130">If autoplay is a crucial part of your experience, consider using muted content to start and allowing the user to unmute it.</span></span>  <span data-ttu-id="d1735-131">若要使内容自动播放，音频源必须显式静音或未设置。</span><span class="sxs-lookup"><span data-stu-id="d1735-131">For muted content to autoplay, the audio source must be either explicitly muted or not be set.</span></span>  <span data-ttu-id="d1735-132">否则，将不会视为静音元素。</span><span class="sxs-lookup"><span data-stu-id="d1735-132">Otherwise the element will not be considered as muted.</span></span>  

*   <span data-ttu-id="d1735-133">除非绝对必要执行其他操作，否则请使用本机浏览器控件执行媒体播放。</span><span class="sxs-lookup"><span data-stu-id="d1735-133">Unless absolutely necessary to do otherwise, use the native browser controls for media playback.</span></span>  <span data-ttu-id="d1735-134">这样会确保用户体验的一致。</span><span class="sxs-lookup"><span data-stu-id="d1735-134">This will ensure a consistent experience for users.</span></span>  <span data-ttu-id="d1735-135">如果要改建自定义控件，请确保始终显示媒体控件，并且你的控件能正确地对自动播放来弹出内容进行正确反应。</span><span class="sxs-lookup"><span data-stu-id="d1735-135">If you are building custom controls instead, ensure that media controls are always present and that your controls properly react to autoplay suppression.</span></span>  

### <span data-ttu-id="d1735-136">Iframe 委发</span><span class="sxs-lookup"><span data-stu-id="d1735-136">Iframe delegation</span></span>  

<span data-ttu-id="d1735-137">自动播放 `<iframe>` 功能将从父页面落后，无管内容来源是如何的。</span><span class="sxs-lookup"><span data-stu-id="d1735-137">Autoplay in an `<iframe>` will inherit the autoplay permission from the parent page regardless of content origin.</span></span>  <span data-ttu-id="d1735-138">在一个被单独的 iframe 托管的播放列表方案中，用户只需为整个播放列表启动一次播放。</span><span class="sxs-lookup"><span data-stu-id="d1735-138">In a playlist scenario where each media file is hosted by a separate iframe, the user would only need to initiate playback once for the entire playlist.</span></span>  

### <span data-ttu-id="d1735-139">检测允许自动播放何时</span><span class="sxs-lookup"><span data-stu-id="d1735-139">Detecting when autoplay is allowed</span></span>  

<span data-ttu-id="d1735-140">通过检查媒体元素上返回的承诺，你可以调整播放控件以在自动播放被阻止 `play()` 时显示正确的状态：</span><span class="sxs-lookup"><span data-stu-id="d1735-140">You can adjust your playback controls to display the correct state when autoplay is blocked by examining the promise returned by the `play()` function on the media element:</span></span>  

```javascript
var promise = document.querySelector('video').play();

if (promise !== undefined) { 
    promise.catch(_error => { 
        // Autoplay was blocked
        // Show user media controls to manually start playback
    }).then(() => { 
        // Autoplay started
    }); 
}
```  
