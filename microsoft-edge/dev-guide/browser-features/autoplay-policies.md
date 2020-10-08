---
description: 确保您的网站上的媒体内容按预期方式工作
title: 自动播放策略-开发人员指南
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
# <span data-ttu-id="4ec0e-104">自动播放策略</span><span class="sxs-lookup"><span data-stu-id="4ec0e-104">Autoplay Policies</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="4ec0e-105">Microsoft Edge 使客户能够在通过自动播放媒体和声音的网站上个性化浏览首选项，从而最大限度地减少 web 上的干扰并节省带宽。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-105">Microsoft Edge provides customers with the ability to personalize their browsing preferences on websites that autoplay media with sound in order to minimize distractions on the web and conserve bandwidth.</span></span>  <span data-ttu-id="4ec0e-106">此外，Microsoft Edge 会自动取消自动播放后台选项卡中的媒体。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-106">Additionally, Microsoft Edge automatically suppresses autoplay of media in background tabs.</span></span>  

<span data-ttu-id="4ec0e-107">用户可以自定义 [全局](#global-media-autoplay-settings) 自动播放控件和 [每个网站](#per-site-media-autoplay-settings) 的媒体行为，这些控件提供以下选项：</span><span class="sxs-lookup"><span data-stu-id="4ec0e-107">Users can customize media behavior with both [global](#global-media-autoplay-settings) and [per-site](#per-site-media-autoplay-settings) autoplay controls, which provide the following options:</span></span>  

*   `Allow`  <span data-ttu-id="4ec0e-108">默认情况下，当首次在前台查看选项卡时，将继续播放视频，具体取决于网站的决定。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-108">The default and will continue to play videos when a tab is first viewed in the foreground, at the site's discretion.</span></span>  

*   `Limit`  <span data-ttu-id="4ec0e-109">将 "自动播放" 限制为仅在视频静音时工作，因此用户永远不会因声音而感到惊讶。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-109">Restricts autoplay to only work when videos are muted, so users are never surprised by sound.</span></span>  <span data-ttu-id="4ec0e-110">一旦用户单击页面上的任意位置，"自动播放" 将重新启用，并将在该选项卡中的该域内继续允许。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-110">Once the user clicks anywhere on the page, autoplay is re-enabled, and will continue to be allowed within that domain in that tab.</span></span>  

*   `Block`  <span data-ttu-id="4ec0e-111">在用户直接与媒体内容交互之前，防止所有网站上的 sautoplay。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-111">Prevent sautoplay on all sites until users directly interact with the media content.</span></span>  

## <span data-ttu-id="4ec0e-112">全局媒体自动播放设置</span><span class="sxs-lookup"><span data-stu-id="4ec0e-112">Global media autoplay settings</span></span>  

<span data-ttu-id="4ec0e-113">用户可以在 "**高级设置**  >  **媒体自动播放**" 下控制所有网站的默认自动播放行为。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-113">Users can control the default autoplay behavior for all sites under **Advanced Setting** > **Media autoplay**.</span></span>  

:::image type="complex" source="../media/autoplay_global.png" alt-text="全局媒体自动播放设置" lightbox="../media/autoplay_global.png":::
   <span data-ttu-id="4ec0e-115">全局媒体自动播放设置</span><span class="sxs-lookup"><span data-stu-id="4ec0e-115">Global media autoplay settings</span></span>  
:::image-end:::  

## <span data-ttu-id="4ec0e-116">每个网站的媒体自动播放设置</span><span class="sxs-lookup"><span data-stu-id="4ec0e-116">Per-site media autoplay settings</span></span>  

<span data-ttu-id="4ec0e-117">用户可以在 "网站信息" 窗格的 " **网站权限** " 部分的每个网站上控制 "自动播放" 行为。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-117">Users can control autoplay behavior on a per-site basis under the **Website permissions** section of the website information pane.</span></span>  <span data-ttu-id="4ec0e-118">单击地址栏左侧的 "信息" 图标或 "锁定" 图标，然后单击 " **媒体自动播放设置** " 以开始，可找到此设置。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-118">This setting can be found by clicking the information icon or lock icon on the left side of the address bar and clicking on **Media autoplay settings** to get started.</span></span>  

<span data-ttu-id="4ec0e-119">按网站设置将覆盖全局设置。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-119">Per-site settings override the global setting.</span></span>  <span data-ttu-id="4ec0e-120">例如，如果用户的全局设置设置为 `Allow` "将每个网站设置更改为 `Block` "，则将阻止该网站的自动播放。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-120">For example, if a user has their global setting set to `Allow` but changes a per-site setting to `Block`, autoplay will be blocked for that site.</span></span>  

:::image type="complex" source="../media/autoplay_per-site.png" alt-text="全局媒体自动播放设置" lightbox="../media/autoplay_per-site.png":::
   <span data-ttu-id="4ec0e-122">每个网站的媒体自动播放设置</span><span class="sxs-lookup"><span data-stu-id="4ec0e-122">Per-site media autoplay settings</span></span>  
:::image-end:::  

## <span data-ttu-id="4ec0e-123">Web 开发人员的最佳做法</span><span class="sxs-lookup"><span data-stu-id="4ec0e-123">Best Practices for Web Developers</span></span>  

<span data-ttu-id="4ec0e-124">下面介绍了如何确保你的网站上托管的媒体具有良好的用户体验：</span><span class="sxs-lookup"><span data-stu-id="4ec0e-124">Here's how to ensure a good user experience with media hosted on your site:</span></span>  

*   <span data-ttu-id="4ec0e-125">假设媒体元素的每个用途都需要用户笔势来启动播放 \ (，因为用户可以在任何时间点阻止自动播放 \ ) 并相应地计划。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-125">Assume each use of a media element wil require a user gesture to start the playback \(as users can block autoplay at any point in time\) and plan accordingly.</span></span>  <span data-ttu-id="4ec0e-126">全局和每网站自动播放策略适用于所有 `<audio>` 和 `<video>` 元素，无论它们在网站上的使用方式</span><span class="sxs-lookup"><span data-stu-id="4ec0e-126">Global and per-site autoplay policies apply to all `<audio>` and `<video>` elements, regardless of how they are used on your site</span></span>  

*   <span data-ttu-id="4ec0e-127">确保媒体控件始终显示在网站媒体和广告内容中。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-127">Ensure that media controls are always present on both site media and ad content.</span></span>  <span data-ttu-id="4ec0e-128">这将使用户能够在页面上阻止自动播放时重启播放。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-128">This will give users the ability to restart playback if autoplay is blocked on the page.</span></span>  

*   <span data-ttu-id="4ec0e-129">评估自动播放如何影响用户在您的网站上的体验，并考虑以最小化不需要的媒体播放的方式使用 "自动播放"。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-129">Evaluate how autoplay may affect users' experience on your website and consider using autoplay in a way that minimizes unwanted media playback.</span></span>  <span data-ttu-id="4ec0e-130">如果 "自动播放" 是你的体验的重要部分，请考虑使用静音内容启动，并允许用户取消静音。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-130">If autoplay is a crucial part of your experience, consider using muted content to start and allowing the user to unmute it.</span></span>  <span data-ttu-id="4ec0e-131">对于静音内容以自动播放，音频源必须显式静音或不进行设置。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-131">For muted content to autoplay, the audio source must be either explicitly muted or not be set.</span></span>  <span data-ttu-id="4ec0e-132">否则，该元素将不会被视为静音。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-132">Otherwise the element will not be considered as muted.</span></span>  

*   <span data-ttu-id="4ec0e-133">除非绝对必要，否则使用本机浏览器控件进行媒体播放。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-133">Unless absolutely necessary to do otherwise, use the native browser controls for media playback.</span></span>  <span data-ttu-id="4ec0e-134">这将确保用户体验的一致性。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-134">This will ensure a consistent experience for users.</span></span>  <span data-ttu-id="4ec0e-135">如果你改为生成自定义控件，请确保媒体控件始终存在，并且你的控件对 "自动播放" 抑制做出正确反应。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-135">If you are building custom controls instead, ensure that media controls are always present and that your controls properly react to autoplay suppression.</span></span>  

### <span data-ttu-id="4ec0e-136">Iframe 委派</span><span class="sxs-lookup"><span data-stu-id="4ec0e-136">Iframe delegation</span></span>  

<span data-ttu-id="4ec0e-137">中的 "自动播放" `<iframe>` 将从父页面继承自动播放权限，而不管内容来源。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-137">Autoplay in an `<iframe>` will inherit the autoplay permission from the parent page regardless of content origin.</span></span>  <span data-ttu-id="4ec0e-138">在每个媒体文件由单独的 iframe 托管的播放列表方案中，用户只需为整个播放列表启动一次播放。</span><span class="sxs-lookup"><span data-stu-id="4ec0e-138">In a playlist scenario where each media file is hosted by a separate iframe, the user would only need to initiate playback once for the entire playlist.</span></span>  

### <span data-ttu-id="4ec0e-139">在允许自动播放时检测</span><span class="sxs-lookup"><span data-stu-id="4ec0e-139">Detecting when autoplay is allowed</span></span>  

<span data-ttu-id="4ec0e-140">你可以通过检查媒体元素上的函数返回的承诺，调整播放控件以在自动播放被阻止时显示正确状态 `play()` ：</span><span class="sxs-lookup"><span data-stu-id="4ec0e-140">You can adjust your playback controls to display the correct state when autoplay is blocked by examining the promise returned by the `play()` function on the media element:</span></span>  

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
