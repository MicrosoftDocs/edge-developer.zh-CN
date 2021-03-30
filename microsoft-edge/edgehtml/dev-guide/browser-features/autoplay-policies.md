---
description: 确保网站上媒体内容按预期方式运行
title: 自动播放策略 - 开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， media， video， audio， autoplay
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 85b91a8b87d73d6fccc6eac2aa64513f283d7f21
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232308"
---
# <span data-ttu-id="2160c-104">自动播放策略</span><span class="sxs-lookup"><span data-stu-id="2160c-104">Autoplay Policies</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="2160c-105">Microsoft Edge 为客户提供了个性化浏览首选项的能力，这些首选项可以自动播放具有声音的媒体，以便最大程度地减少 Web 上的干扰并节省带宽。</span><span class="sxs-lookup"><span data-stu-id="2160c-105">Microsoft Edge provides customers with the ability to personalize their browsing preferences on websites that autoplay media with sound in order to minimize distractions on the web and conserve bandwidth.</span></span>  <span data-ttu-id="2160c-106">此外，Microsoft Edge 自动禁止在后台选项卡中自动播放媒体。</span><span class="sxs-lookup"><span data-stu-id="2160c-106">Additionally, Microsoft Edge automatically suppresses autoplay of media in background tabs.</span></span>  

<span data-ttu-id="2160c-107">用户可以使用全局和每站点自动[](#global-media-autoplay-settings)播放控件[](#per-site-media-autoplay-settings)自定义媒体行为，这提供以下选项：</span><span class="sxs-lookup"><span data-stu-id="2160c-107">Users can customize media behavior with both [global](#global-media-autoplay-settings) and [per-site](#per-site-media-autoplay-settings) autoplay controls, which provide the following options:</span></span>  

*   `Allow`  <span data-ttu-id="2160c-108">默认选项，在首次在前台查看选项卡时将继续播放视频，由网站自行决定。</span><span class="sxs-lookup"><span data-stu-id="2160c-108">The default and will continue to play videos when a tab is first viewed in the foreground, at the site's discretion.</span></span>  

*   `Limit`  <span data-ttu-id="2160c-109">将自动播放限制为仅在视频静音时工作，因此用户永远不会对声音感到意外。</span><span class="sxs-lookup"><span data-stu-id="2160c-109">Restricts autoplay to only work when videos are muted, so users are never surprised by sound.</span></span>  <span data-ttu-id="2160c-110">用户单击页面上的任何位置后，自动播放将重新启用，并且将继续允许该选项卡中的该域中的自动播放。</span><span class="sxs-lookup"><span data-stu-id="2160c-110">Once the user clicks anywhere on the page, autoplay is re-enabled, and will continue to be allowed within that domain in that tab.</span></span>  

*   `Block`  <span data-ttu-id="2160c-111">阻止在所有网站上播放，直到用户直接与媒体内容交互。</span><span class="sxs-lookup"><span data-stu-id="2160c-111">Prevent sautoplay on all sites until users directly interact with the media content.</span></span>  

## <span data-ttu-id="2160c-112">全局媒体自动播放设置</span><span class="sxs-lookup"><span data-stu-id="2160c-112">Global media autoplay settings</span></span>  

<span data-ttu-id="2160c-113">用户可以控制高级设置媒体自动播放下的所有**网站**  >  **的默认自动播放行为**。</span><span class="sxs-lookup"><span data-stu-id="2160c-113">Users can control the default autoplay behavior for all sites under **Advanced Setting** > **Media autoplay**.</span></span>  

:::image type="complex" source="../media/autoplay_global.png" alt-text="全局媒体自动播放设置" lightbox="../media/autoplay_global.png":::
   <span data-ttu-id="2160c-115">全局媒体自动播放设置</span><span class="sxs-lookup"><span data-stu-id="2160c-115">Global media autoplay settings</span></span>  
:::image-end:::  

## <span data-ttu-id="2160c-116">每站点媒体自动播放设置</span><span class="sxs-lookup"><span data-stu-id="2160c-116">Per-site media autoplay settings</span></span>  

<span data-ttu-id="2160c-117">用户可以在网站信息窗格的"网站权限"部分下按网站 控制自动播放行为。</span><span class="sxs-lookup"><span data-stu-id="2160c-117">Users can control autoplay behavior on a per-site basis under the **Website permissions** section of the website information pane.</span></span>  <span data-ttu-id="2160c-118">可以通过单击地址栏左侧的信息图标或锁定图标，然后单击媒体自动播放设置开始找到此设置。 </span><span class="sxs-lookup"><span data-stu-id="2160c-118">This setting can be found by clicking the information icon or lock icon on the left side of the address bar and clicking on **Media autoplay settings** to get started.</span></span>  

<span data-ttu-id="2160c-119">每个站点设置将覆盖全局设置。</span><span class="sxs-lookup"><span data-stu-id="2160c-119">Per-site settings override the global setting.</span></span>  <span data-ttu-id="2160c-120">例如，如果用户已设置其全局设置，但将每个站点设置更改为，则该网站的自动播放将被 `Allow` `Block` 阻止。</span><span class="sxs-lookup"><span data-stu-id="2160c-120">For example, if a user has their global setting set to `Allow` but changes a per-site setting to `Block`, autoplay will be blocked for that site.</span></span>  

:::image type="complex" source="../media/autoplay_per-site.png" alt-text="每站点媒体自动播放设置" lightbox="../media/autoplay_per-site.png":::
   <span data-ttu-id="2160c-122">每站点媒体自动播放设置</span><span class="sxs-lookup"><span data-stu-id="2160c-122">Per-site media autoplay settings</span></span>  
:::image-end:::  

## <span data-ttu-id="2160c-123">Web 开发人员的最佳实践</span><span class="sxs-lookup"><span data-stu-id="2160c-123">Best Practices for Web Developers</span></span>  

<span data-ttu-id="2160c-124">下面是如何确保使用网站上托管的媒体获得良好的用户体验：</span><span class="sxs-lookup"><span data-stu-id="2160c-124">Here's how to ensure a good user experience with media hosted on your site:</span></span>  

*   <span data-ttu-id="2160c-125">假设每次使用媒体元素都需要用户手势才能启动播放 \(因为用户可以在任意时间点阻止自动播放\) 进行相应规划。</span><span class="sxs-lookup"><span data-stu-id="2160c-125">Assume each use of a media element wil require a user gesture to start the playback \(as users can block autoplay at any point in time\) and plan accordingly.</span></span>  <span data-ttu-id="2160c-126">全局和每站点自动播放策略适用于所有和元素，而不管 `<audio>` `<video>` 它们如何用于你的站点</span><span class="sxs-lookup"><span data-stu-id="2160c-126">Global and per-site autoplay policies apply to all `<audio>` and `<video>` elements, regardless of how they are used on your site</span></span>  

*   <span data-ttu-id="2160c-127">确保网站媒体和广告内容上始终存在媒体控件。</span><span class="sxs-lookup"><span data-stu-id="2160c-127">Ensure that media controls are always present on both site media and ad content.</span></span>  <span data-ttu-id="2160c-128">这样，如果用户在页面上自动播放被阻止，则用户可以重新启动播放。</span><span class="sxs-lookup"><span data-stu-id="2160c-128">This will give users the ability to restart playback if autoplay is blocked on the page.</span></span>  

*   <span data-ttu-id="2160c-129">评估自动播放可能会如何影响用户在网站上的体验，并考虑以最大程度减少不需要的媒体播放的方式使用自动播放。</span><span class="sxs-lookup"><span data-stu-id="2160c-129">Evaluate how autoplay may affect users' experience on your website and consider using autoplay in a way that minimizes unwanted media playback.</span></span>  <span data-ttu-id="2160c-130">如果自动播放是体验的重要组成部分，请考虑使用静音内容启动并允许用户取消静音。</span><span class="sxs-lookup"><span data-stu-id="2160c-130">If autoplay is a crucial part of your experience, consider using muted content to start and allowing the user to unmute it.</span></span>  <span data-ttu-id="2160c-131">对于要自动播放的静音内容，必须显式静音或不设置音频源。</span><span class="sxs-lookup"><span data-stu-id="2160c-131">For muted content to autoplay, the audio source must be either explicitly muted or not be set.</span></span>  <span data-ttu-id="2160c-132">否则，不会将元素视为静音。</span><span class="sxs-lookup"><span data-stu-id="2160c-132">Otherwise the element will not be considered as muted.</span></span>  

*   <span data-ttu-id="2160c-133">除非绝对有必要否则，否则请使用本机浏览器控件进行媒体播放。</span><span class="sxs-lookup"><span data-stu-id="2160c-133">Unless absolutely necessary to do otherwise, use the native browser controls for media playback.</span></span>  <span data-ttu-id="2160c-134">这将确保为用户提供一致的体验。</span><span class="sxs-lookup"><span data-stu-id="2160c-134">This will ensure a consistent experience for users.</span></span>  <span data-ttu-id="2160c-135">如果要改为生成自定义控件，请确保媒体控件始终存在，并且控件对自动播放抑制做出正确响应。</span><span class="sxs-lookup"><span data-stu-id="2160c-135">If you are building custom controls instead, ensure that media controls are always present and that your controls properly react to autoplay suppression.</span></span>  

### <span data-ttu-id="2160c-136">Iframe 委派</span><span class="sxs-lookup"><span data-stu-id="2160c-136">Iframe delegation</span></span>  

<span data-ttu-id="2160c-137">无论内容源如何，在 an 中自动播放都将从 `<iframe>` 父页面继承自动播放权限。</span><span class="sxs-lookup"><span data-stu-id="2160c-137">Autoplay in an `<iframe>` will inherit the autoplay permission from the parent page regardless of content origin.</span></span>  <span data-ttu-id="2160c-138">在每个媒体文件由单独的 iframe 托管的播放列表方案中，用户只需为整个播放列表启动播放一次。</span><span class="sxs-lookup"><span data-stu-id="2160c-138">In a playlist scenario where each media file is hosted by a separate iframe, the user would only need to initiate playback once for the entire playlist.</span></span>  

### <span data-ttu-id="2160c-139">检测何时允许自动播放</span><span class="sxs-lookup"><span data-stu-id="2160c-139">Detecting when autoplay is allowed</span></span>  

<span data-ttu-id="2160c-140">通过检查媒体元素上函数返回的承诺，可以调整播放控件，以在自动播放被阻止时 `play()` 显示正确的状态：</span><span class="sxs-lookup"><span data-stu-id="2160c-140">You can adjust your playback controls to display the correct state when autoplay is blocked by examining the promise returned by the `play()` function on the media element:</span></span>  

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
