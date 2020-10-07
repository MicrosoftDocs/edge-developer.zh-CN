---
description: Ensure media content on your site behaves as intended
title: Autoplay policies - Dev guide
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, media, video, audio, autoplay
ms.custom: seodec18
ms.openlocfilehash: 39c9bd8e9921167dfc3a9ab1a4cc12b2157f0f6f
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942058"
---
# <span data-ttu-id="87f60-104">Autoplay Policies</span><span class="sxs-lookup"><span data-stu-id="87f60-104">Autoplay Policies</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="87f60-105">Microsoft Edge provides customers with the ability to personalize their browsing preferences on websites that autoplay media with sound in order to minimize distractions on the web and conserve bandwidth.</span><span class="sxs-lookup"><span data-stu-id="87f60-105">Microsoft Edge provides customers with the ability to personalize their browsing preferences on websites that autoplay media with sound in order to minimize distractions on the web and conserve bandwidth.</span></span>  <span data-ttu-id="87f60-106">Additionally, Microsoft Edge automatically suppresses autoplay of media in background tabs.</span><span class="sxs-lookup"><span data-stu-id="87f60-106">Additionally, Microsoft Edge automatically suppresses autoplay of media in background tabs.</span></span>  

<span data-ttu-id="87f60-107">Users can customize media behavior with both [global](#global-media-autoplay-settings) and [per-site](#per-site-media-autoplay-settings) autoplay controls, which provide the following options:</span><span class="sxs-lookup"><span data-stu-id="87f60-107">Users can customize media behavior with both [global](#global-media-autoplay-settings) and [per-site](#per-site-media-autoplay-settings) autoplay controls, which provide the following options:</span></span>  

*   `Allow`  <span data-ttu-id="87f60-108">The default and will continue to play videos when a tab is first viewed in the foreground, at the site's discretion.</span><span class="sxs-lookup"><span data-stu-id="87f60-108">The default and will continue to play videos when a tab is first viewed in the foreground, at the site's discretion.</span></span>  

*   `Limit`  <span data-ttu-id="87f60-109">Restricts autoplay to only work when videos are muted, so users are never surprised by sound.</span><span class="sxs-lookup"><span data-stu-id="87f60-109">Restricts autoplay to only work when videos are muted, so users are never surprised by sound.</span></span>  <span data-ttu-id="87f60-110">Once the user clicks anywhere on the page, autoplay is re-enabled, and will continue to be allowed within that domain in that tab.</span><span class="sxs-lookup"><span data-stu-id="87f60-110">Once the user clicks anywhere on the page, autoplay is re-enabled, and will continue to be allowed within that domain in that tab.</span></span>  

*   `Block`  <span data-ttu-id="87f60-111">Prevent sautoplay on all sites until users directly interact with the media content.</span><span class="sxs-lookup"><span data-stu-id="87f60-111">Prevent sautoplay on all sites until users directly interact with the media content.</span></span>  

## <span data-ttu-id="87f60-112">Global media autoplay settings</span><span class="sxs-lookup"><span data-stu-id="87f60-112">Global media autoplay settings</span></span>  

<span data-ttu-id="87f60-113">Users can control the default autoplay behavior for all sites under **Advanced Setting** > **Media autoplay**.</span><span class="sxs-lookup"><span data-stu-id="87f60-113">Users can control the default autoplay behavior for all sites under **Advanced Setting** > **Media autoplay**.</span></span>  

:::image type="complex" source="../media/autoplay_global.png" alt-text="Global media autoplay settings" lightbox="../media/autoplay_global.png":::
   <span data-ttu-id="87f60-115">Global media autoplay settings</span><span class="sxs-lookup"><span data-stu-id="87f60-115">Global media autoplay settings</span></span>  
:::image-end:::  

## <span data-ttu-id="87f60-116">Per-site media autoplay settings</span><span class="sxs-lookup"><span data-stu-id="87f60-116">Per-site media autoplay settings</span></span>  

<span data-ttu-id="87f60-117">Users can control autoplay behavior on a per-site basis under the **Website permissions** section of the website information pane.</span><span class="sxs-lookup"><span data-stu-id="87f60-117">Users can control autoplay behavior on a per-site basis under the **Website permissions** section of the website information pane.</span></span>  <span data-ttu-id="87f60-118">This setting can be found by clicking the information icon or lock icon on the left side of the address bar and clicking on **Media autoplay settings** to get started.</span><span class="sxs-lookup"><span data-stu-id="87f60-118">This setting can be found by clicking the information icon or lock icon on the left side of the address bar and clicking on **Media autoplay settings** to get started.</span></span>  

<span data-ttu-id="87f60-119">Per-site settings override the global setting.</span><span class="sxs-lookup"><span data-stu-id="87f60-119">Per-site settings override the global setting.</span></span>  <span data-ttu-id="87f60-120">For example, if a user has their global setting set to `Allow` but changes a per-site setting to `Block`, autoplay will be blocked for that site.</span><span class="sxs-lookup"><span data-stu-id="87f60-120">For example, if a user has their global setting set to `Allow` but changes a per-site setting to `Block`, autoplay will be blocked for that site.</span></span>  

:::image type="complex" source="../media/autoplay_per-site.png" alt-text="Global media autoplay settings" lightbox="../media/autoplay_per-site.png":::
   <span data-ttu-id="87f60-122">Per-site media autoplay settings</span><span class="sxs-lookup"><span data-stu-id="87f60-122">Per-site media autoplay settings</span></span>  
:::image-end:::  

## <span data-ttu-id="87f60-123">Best Practices for Web Developers</span><span class="sxs-lookup"><span data-stu-id="87f60-123">Best Practices for Web Developers</span></span>  

<span data-ttu-id="87f60-124">Here's how to ensure a good user experience with media hosted on your site:</span><span class="sxs-lookup"><span data-stu-id="87f60-124">Here's how to ensure a good user experience with media hosted on your site:</span></span>  

*   <span data-ttu-id="87f60-125">Assume each use of a media element wil require a user gesture to start the playback \(as users can block autoplay at any point in time\) and plan accordingly.</span><span class="sxs-lookup"><span data-stu-id="87f60-125">Assume each use of a media element wil require a user gesture to start the playback \(as users can block autoplay at any point in time\) and plan accordingly.</span></span>  <span data-ttu-id="87f60-126">Global and per-site autoplay policies apply to all `<audio>` and `<video>` elements, regardless of how they are used on your site</span><span class="sxs-lookup"><span data-stu-id="87f60-126">Global and per-site autoplay policies apply to all `<audio>` and `<video>` elements, regardless of how they are used on your site</span></span>  

*   <span data-ttu-id="87f60-127">Ensure that media controls are always present on both site media and ad content.</span><span class="sxs-lookup"><span data-stu-id="87f60-127">Ensure that media controls are always present on both site media and ad content.</span></span>  <span data-ttu-id="87f60-128">This will give users the ability to restart playback if autoplay is blocked on the page.</span><span class="sxs-lookup"><span data-stu-id="87f60-128">This will give users the ability to restart playback if autoplay is blocked on the page.</span></span>  

*   <span data-ttu-id="87f60-129">Evaluate how autoplay may affect users' experience on your website and consider using autoplay in a way that minimizes unwanted media playback.</span><span class="sxs-lookup"><span data-stu-id="87f60-129">Evaluate how autoplay may affect users' experience on your website and consider using autoplay in a way that minimizes unwanted media playback.</span></span>  <span data-ttu-id="87f60-130">If autoplay is a crucial part of your experience, consider using muted content to start and allowing the user to unmute it.</span><span class="sxs-lookup"><span data-stu-id="87f60-130">If autoplay is a crucial part of your experience, consider using muted content to start and allowing the user to unmute it.</span></span>  <span data-ttu-id="87f60-131">For muted content to autoplay, the audio source must be either explicitly muted or not be set.</span><span class="sxs-lookup"><span data-stu-id="87f60-131">For muted content to autoplay, the audio source must be either explicitly muted or not be set.</span></span>  <span data-ttu-id="87f60-132">Otherwise the element will not be considered as muted.</span><span class="sxs-lookup"><span data-stu-id="87f60-132">Otherwise the element will not be considered as muted.</span></span>  

*   <span data-ttu-id="87f60-133">Unless absolutely necessary to do otherwise, use the native browser controls for media playback.</span><span class="sxs-lookup"><span data-stu-id="87f60-133">Unless absolutely necessary to do otherwise, use the native browser controls for media playback.</span></span>  <span data-ttu-id="87f60-134">This will ensure a consistent experience for users.</span><span class="sxs-lookup"><span data-stu-id="87f60-134">This will ensure a consistent experience for users.</span></span>  <span data-ttu-id="87f60-135">If you are building custom controls instead, ensure that media controls are always present and that your controls properly react to autoplay suppression.</span><span class="sxs-lookup"><span data-stu-id="87f60-135">If you are building custom controls instead, ensure that media controls are always present and that your controls properly react to autoplay suppression.</span></span>  

### <span data-ttu-id="87f60-136">Iframe delegation</span><span class="sxs-lookup"><span data-stu-id="87f60-136">Iframe delegation</span></span>  

<span data-ttu-id="87f60-137">Autoplay in an `<iframe>` will inherit the autoplay permission from the parent page regardless of content origin.</span><span class="sxs-lookup"><span data-stu-id="87f60-137">Autoplay in an `<iframe>` will inherit the autoplay permission from the parent page regardless of content origin.</span></span>  <span data-ttu-id="87f60-138">In a playlist scenario where each media file is hosted by a separate iframe, the user would only need to initiate playback once for the entire playlist.</span><span class="sxs-lookup"><span data-stu-id="87f60-138">In a playlist scenario where each media file is hosted by a separate iframe, the user would only need to initiate playback once for the entire playlist.</span></span>  

### <span data-ttu-id="87f60-139">Detecting when autoplay is allowed</span><span class="sxs-lookup"><span data-stu-id="87f60-139">Detecting when autoplay is allowed</span></span>  

<span data-ttu-id="87f60-140">You can adjust your playback controls to display the correct state when autoplay is blocked by examining the promise returned by the `play()` function on the media element:</span><span class="sxs-lookup"><span data-stu-id="87f60-140">You can adjust your playback controls to display the correct state when autoplay is blocked by examining the promise returned by the `play()` function on the media element:</span></span>  

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
