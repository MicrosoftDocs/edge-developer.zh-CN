---
description: Inspect and modify animations with the Microsoft Edge DevTools  Animation Inspector.
title: Inspect animations
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: e867cc373286666f73bee3b8fb886f60fa1b94f6
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015770"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# <span data-ttu-id="69b38-104">Inspect animations</span><span class="sxs-lookup"><span data-stu-id="69b38-104">Inspect animations</span></span>  

<span data-ttu-id="69b38-105">Inspect and modify animations with the Microsoft Edge DevTools Animation Inspector.</span><span class="sxs-lookup"><span data-stu-id="69b38-105">Inspect and modify animations with the Microsoft Edge DevTools Animation Inspector.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png" alt-text="animation inspector" lightbox="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png":::
   <span data-ttu-id="69b38-107">animation inspector</span><span class="sxs-lookup"><span data-stu-id="69b38-107">animation inspector</span></span>  
:::image-end:::  

### <span data-ttu-id="69b38-108">Summary</span><span class="sxs-lookup"><span data-stu-id="69b38-108">Summary</span></span>  

*   <span data-ttu-id="69b38-109">Capture animations by opening the Animation Inspector.</span><span class="sxs-lookup"><span data-stu-id="69b38-109">Capture animations by opening the Animation Inspector.</span></span>  <span data-ttu-id="69b38-110">The Animation Inspector automatically detects and sorts animations into groups.</span><span class="sxs-lookup"><span data-stu-id="69b38-110">The Animation Inspector automatically detects and sorts animations into groups.</span></span>  
*   <span data-ttu-id="69b38-111">Inspect animations by slowing down each one, replaying each one, or viewing the source code.</span><span class="sxs-lookup"><span data-stu-id="69b38-111">Inspect animations by slowing down each one, replaying each one, or viewing the source code.</span></span>  
*   <span data-ttu-id="69b38-112">Modify animations by changing the timing, delay, duration, or keyframe offsets.</span><span class="sxs-lookup"><span data-stu-id="69b38-112">Modify animations by changing the timing, delay, duration, or keyframe offsets.</span></span>  

## <span data-ttu-id="69b38-113">Overview</span><span class="sxs-lookup"><span data-stu-id="69b38-113">Overview</span></span>  

<span data-ttu-id="69b38-114">The Microsoft Edge DevTools Animation Inspector has two main purposes.</span><span class="sxs-lookup"><span data-stu-id="69b38-114">The Microsoft Edge DevTools Animation Inspector has two main purposes.</span></span>  

*   <span data-ttu-id="69b38-115">Inspecting animations.</span><span class="sxs-lookup"><span data-stu-id="69b38-115">Inspecting animations.</span></span>  <span data-ttu-id="69b38-116">You want to slow down, replay, or inspect the source code for an Animation Group.</span><span class="sxs-lookup"><span data-stu-id="69b38-116">You want to slow down, replay, or inspect the source code for an Animation Group.</span></span>  
*   <span data-ttu-id="69b38-117">Modifying animations.</span><span class="sxs-lookup"><span data-stu-id="69b38-117">Modifying animations.</span></span>  <span data-ttu-id="69b38-118">You want to modify the timing, delay, duration, or keyframe offsets of an Animation Group.</span><span class="sxs-lookup"><span data-stu-id="69b38-118">You want to modify the timing, delay, duration, or keyframe offsets of an Animation Group.</span></span>  <span data-ttu-id="69b38-119">Bezier editing and keyframe editing are currently not supported.</span><span class="sxs-lookup"><span data-stu-id="69b38-119">Bezier editing and keyframe editing are currently not supported.</span></span>  

<span data-ttu-id="69b38-120">The Animation Inspector supports CSS animations, CSS transitions, and web animations.</span><span class="sxs-lookup"><span data-stu-id="69b38-120">The Animation Inspector supports CSS animations, CSS transitions, and web animations.</span></span>  `requestAnimationFrame` <span data-ttu-id="69b38-121">animations are currently not supported.</span><span class="sxs-lookup"><span data-stu-id="69b38-121">animations are currently not supported.</span></span>  

### <span data-ttu-id="69b38-122">What is an Animation Group?</span><span class="sxs-lookup"><span data-stu-id="69b38-122">What is an Animation Group?</span></span>  

<span data-ttu-id="69b38-123">An Animation Group is a group of animations that may be related to each other.</span><span class="sxs-lookup"><span data-stu-id="69b38-123">An Animation Group is a group of animations that may be related to each other.</span></span>  <span data-ttu-id="69b38-124">Currently, the web has no real concept of a group animation, so motion designers and developers have to compose and time individual animations so that the animations render as one coherent visual effect.</span><span class="sxs-lookup"><span data-stu-id="69b38-124">Currently, the web has no real concept of a group animation, so motion designers and developers have to compose and time individual animations so that the animations render as one coherent visual effect.</span></span>  <span data-ttu-id="69b38-125">The Animation Inspector predicts which animations are related based on start time \(excluding delays, and so on\).</span><span class="sxs-lookup"><span data-stu-id="69b38-125">The Animation Inspector predicts which animations are related based on start time \(excluding delays, and so on\).</span></span>  <span data-ttu-id="69b38-126">The Animation Inspector also groups the animations side-by-side.</span><span class="sxs-lookup"><span data-stu-id="69b38-126">The Animation Inspector also groups the animations side-by-side.</span></span>  
<span data-ttu-id="69b38-127">In other words, a set of animations that are all triggered in the same script block are grouped together.</span><span class="sxs-lookup"><span data-stu-id="69b38-127">In other words, a set of animations that are all triggered in the same script block are grouped together.</span></span>  <span data-ttu-id="69b38-128">If an animation is asynchronous, it is placed in a separate group.</span><span class="sxs-lookup"><span data-stu-id="69b38-128">If an animation is asynchronous, it is placed in a separate group.</span></span>  

## <span data-ttu-id="69b38-129">Get started</span><span class="sxs-lookup"><span data-stu-id="69b38-129">Get started</span></span>  

<span data-ttu-id="69b38-130">There are two ways to open the Animation Inspector:</span><span class="sxs-lookup"><span data-stu-id="69b38-130">There are two ways to open the Animation Inspector:</span></span>  

*   <span data-ttu-id="69b38-131">Open the **Customize and Control DevTools** menu</span><span class="sxs-lookup"><span data-stu-id="69b38-131">Open the **Customize and Control DevTools** menu</span></span>  
    1.  <span data-ttu-id="69b38-132">Navigate to the **More tools** sub-menu.</span><span class="sxs-lookup"><span data-stu-id="69b38-132">Navigate to the **More tools** sub-menu.</span></span>  
    1.  <span data-ttu-id="69b38-133">Select **Animations**:</span><span class="sxs-lookup"><span data-stu-id="69b38-133">Select **Animations**:</span></span>  
        
        :::image type="complex" source="../media/inspect-styles-elements-styles-more-tools-animations.msft.png" alt-text="animation inspector" lightbox="../media/inspect-styles-elements-styles-more-tools-animations.msft.png":::
           <span data-ttu-id="69b38-135">**Animations** using Main Menu</span><span class="sxs-lookup"><span data-stu-id="69b38-135">**Animations** using Main Menu</span></span>  
    :::image-end:::  
        
*   <span data-ttu-id="69b38-136">Open the **Command Menu**</span><span class="sxs-lookup"><span data-stu-id="69b38-136">Open the **Command Menu**</span></span>  
    1.  <span data-ttu-id="69b38-137">Type `Drawer: Show Animations`.</span><span class="sxs-lookup"><span data-stu-id="69b38-137">Type `Drawer: Show Animations`.</span></span>  

<span data-ttu-id="69b38-138">The Animation Inspector opens up as a tab next to the Console Drawer.</span><span class="sxs-lookup"><span data-stu-id="69b38-138">The Animation Inspector opens up as a tab next to the Console Drawer.</span></span>  <span data-ttu-id="69b38-139">Since the Animation Inspector is a Drawer tab, you may use the Animation Inspector from any DevTools panel.</span><span class="sxs-lookup"><span data-stu-id="69b38-139">Since the Animation Inspector is a Drawer tab, you may use the Animation Inspector from any DevTools panel.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations.msft.png" alt-text="animation inspector" lightbox="../media/inspect-styles-elements-styles-drawer-animations.msft.png":::
   <span data-ttu-id="69b38-141">Empty Animation Inspector</span><span class="sxs-lookup"><span data-stu-id="69b38-141">Empty Animation Inspector</span></span>  
:::image-end:::  

<span data-ttu-id="69b38-142">The Animation Inspector is grouped into four main sections \(or panes\).</span><span class="sxs-lookup"><span data-stu-id="69b38-142">The Animation Inspector is grouped into four main sections \(or panes\).</span></span>  <span data-ttu-id="69b38-143">This guide refers to each pane as follows:</span><span class="sxs-lookup"><span data-stu-id="69b38-143">This guide refers to each pane as follows:</span></span>  

| <span data-ttu-id="69b38-144">Index</span><span class="sxs-lookup"><span data-stu-id="69b38-144">Index</span></span> | <span data-ttu-id="69b38-145">Pane</span><span class="sxs-lookup"><span data-stu-id="69b38-145">Pane</span></span> | <span data-ttu-id="69b38-146">Description</span><span class="sxs-lookup"><span data-stu-id="69b38-146">Description</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="69b38-147">1</span><span class="sxs-lookup"><span data-stu-id="69b38-147">1</span></span> | **<span data-ttu-id="69b38-148">Controls</span><span class="sxs-lookup"><span data-stu-id="69b38-148">Controls</span></span>** | <span data-ttu-id="69b38-149">From here you may clear all currently captured Animation Groups, or change the speed of the currently selected Animation Group.</span><span class="sxs-lookup"><span data-stu-id="69b38-149">From here you may clear all currently captured Animation Groups, or change the speed of the currently selected Animation Group.</span></span> |  
| <span data-ttu-id="69b38-150">2</span><span class="sxs-lookup"><span data-stu-id="69b38-150">2</span></span> | **<span data-ttu-id="69b38-151">Overview</span><span class="sxs-lookup"><span data-stu-id="69b38-151">Overview</span></span>** | <span data-ttu-id="69b38-152">Select an Animation Group here to inspect and modify it in the **Details** pane.</span><span class="sxs-lookup"><span data-stu-id="69b38-152">Select an Animation Group here to inspect and modify it in the **Details** pane.</span></span> |  
| <span data-ttu-id="69b38-153">3</span><span class="sxs-lookup"><span data-stu-id="69b38-153">3</span></span> | **<span data-ttu-id="69b38-154">Timeline</span><span class="sxs-lookup"><span data-stu-id="69b38-154">Timeline</span></span>** | <span data-ttu-id="69b38-155">Pause and start an animation from here, or jump to a specific point in the animation.</span><span class="sxs-lookup"><span data-stu-id="69b38-155">Pause and start an animation from here, or jump to a specific point in the animation.</span></span> |  
| <span data-ttu-id="69b38-156">4</span><span class="sxs-lookup"><span data-stu-id="69b38-156">4</span></span> | **<span data-ttu-id="69b38-157">Details</span><span class="sxs-lookup"><span data-stu-id="69b38-157">Details</span></span>** | <span data-ttu-id="69b38-158">Inspect and modify the currently selected Animation Group.</span><span class="sxs-lookup"><span data-stu-id="69b38-158">Inspect and modify the currently selected Animation Group.</span></span> |  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png" alt-text="animation inspector" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png":::
   <span data-ttu-id="69b38-160">Annotated Animation Inspector</span><span class="sxs-lookup"><span data-stu-id="69b38-160">Annotated Animation Inspector</span></span>  
:::image-end:::  

<span data-ttu-id="69b38-161">To capture an animation, just perform the interaction that triggers the animation while the Animation Inspector is open.</span><span class="sxs-lookup"><span data-stu-id="69b38-161">To capture an animation, just perform the interaction that triggers the animation while the Animation Inspector is open.</span></span>  <span data-ttu-id="69b38-162">If an animation is triggered on page load, reload the page with the Animation Inspector open to detect the animation.</span><span class="sxs-lookup"><span data-stu-id="69b38-162">If an animation is triggered on page load, reload the page with the Animation Inspector open to detect the animation.</span></span>  

<!--  old link: <video src="animations/capture-animations.mp4" autoplay loop muted controls></video>  -->  

<!--  import the video to ACOM using https://review.docs.microsoft.com/en-us/help/contribute/contribute-video-publish?branch=master  -->  

<!--  > [!VIDEO animations/capture-animations.mp4]  -->  

## <span data-ttu-id="69b38-163">Inspect animations</span><span class="sxs-lookup"><span data-stu-id="69b38-163">Inspect animations</span></span>  

<span data-ttu-id="69b38-164">After you capture an animation, there are a few ways to replay it:</span><span class="sxs-lookup"><span data-stu-id="69b38-164">After you capture an animation, there are a few ways to replay it:</span></span>  

*   <span data-ttu-id="69b38-165">Hover over the thumbnail in the **Overview** pane to view a preview of it.</span><span class="sxs-lookup"><span data-stu-id="69b38-165">Hover over the thumbnail in the **Overview** pane to view a preview of it.</span></span>  
*   <span data-ttu-id="69b38-166">Select the Animation Group from the **Overview** pane \(so that it is displayed in the **Details** pane\) and press the **replay** \(![replay icon][ImageReplayButtonIcon]\) icon.</span><span class="sxs-lookup"><span data-stu-id="69b38-166">Select the Animation Group from the **Overview** pane \(so that it is displayed in the **Details** pane\) and press the **replay** \(![replay icon][ImageReplayButtonIcon]\) icon.</span></span>  <span data-ttu-id="69b38-167">The animation is replayed in the viewport.</span><span class="sxs-lookup"><span data-stu-id="69b38-167">The animation is replayed in the viewport.</span></span>  <span data-ttu-id="69b38-168">Click on the **animation speed** \(![animation speed icons][ImageAnimationSpeedButtonsIcon]\) icons to change the preview speed of the currently selected Animation Group.</span><span class="sxs-lookup"><span data-stu-id="69b38-168">Click on the **animation speed** \(![animation speed icons][ImageAnimationSpeedButtonsIcon]\) icons to change the preview speed of the currently selected Animation Group.</span></span>  <span data-ttu-id="69b38-169">You may use the red vertical bar to change your current position.</span><span class="sxs-lookup"><span data-stu-id="69b38-169">You may use the red vertical bar to change your current position.</span></span>  
*   <span data-ttu-id="69b38-170">Click and drag the red vertical bar to scrub the viewport animation.</span><span class="sxs-lookup"><span data-stu-id="69b38-170">Click and drag the red vertical bar to scrub the viewport animation.</span></span>  
    
### <span data-ttu-id="69b38-171">View animation details</span><span class="sxs-lookup"><span data-stu-id="69b38-171">View animation details</span></span>  

<span data-ttu-id="69b38-172">After you capture an Animation Group, click on it from the **Overview** pane to view the details.</span><span class="sxs-lookup"><span data-stu-id="69b38-172">After you capture an Animation Group, click on it from the **Overview** pane to view the details.</span></span>  <span data-ttu-id="69b38-173">In the **Details** pane each individual animation is assigned the a row.</span><span class="sxs-lookup"><span data-stu-id="69b38-173">In the **Details** pane each individual animation is assigned the a row.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="animation inspector" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png":::
   <span data-ttu-id="69b38-175">Animation Group details</span><span class="sxs-lookup"><span data-stu-id="69b38-175">Animation Group details</span></span>  
:::image-end:::  

<span data-ttu-id="69b38-176">Hover over an animation to highlight it in the viewport.</span><span class="sxs-lookup"><span data-stu-id="69b38-176">Hover over an animation to highlight it in the viewport.</span></span>  <span data-ttu-id="69b38-177">Click on the animation to select it in the **Elements** panel.</span><span class="sxs-lookup"><span data-stu-id="69b38-177">Click on the animation to select it in the **Elements** panel.</span></span>  

:::image type="complex" source="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="animation inspector" lightbox="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png":::
   <span data-ttu-id="69b38-179">Hover over the animation to highlight it in viewport</span><span class="sxs-lookup"><span data-stu-id="69b38-179">Hover over the animation to highlight it in viewport</span></span>  
:::image-end:::  

<span data-ttu-id="69b38-180">The leftmost, darker section of an animation is the definition.</span><span class="sxs-lookup"><span data-stu-id="69b38-180">The leftmost, darker section of an animation is the definition.</span></span>  <span data-ttu-id="69b38-181">The right, more faded section represents iterations.</span><span class="sxs-lookup"><span data-stu-id="69b38-181">The right, more faded section represents iterations.</span></span>  <span data-ttu-id="69b38-182">For example, in the following figure, sections two and three represent iterations of section one.</span><span class="sxs-lookup"><span data-stu-id="69b38-182">For example, in the following figure, sections two and three represent iterations of section one.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations-highlight.msft.png" alt-text="animation inspector" lightbox="../media/inspect-styles-glitch-display-animations-highlight.msft.png":::
   <span data-ttu-id="69b38-184">Diagram of animation iterations</span><span class="sxs-lookup"><span data-stu-id="69b38-184">Diagram of animation iterations</span></span>  
:::image-end:::  

<span data-ttu-id="69b38-185">If two elements have the same animation applied, the Animation Inspector assigns the same color to the elements.</span><span class="sxs-lookup"><span data-stu-id="69b38-185">If two elements have the same animation applied, the Animation Inspector assigns the same color to the elements.</span></span>  <span data-ttu-id="69b38-186">The color is random and has no significance.</span><span class="sxs-lookup"><span data-stu-id="69b38-186">The color is random and has no significance.</span></span>  <span data-ttu-id="69b38-187">For example, in the following figure, the two elements `div.cwccw.earlier` and `div.cwccw.later` have the same animation \(`spinrightleft`\) applied, as do the `div.ccwcw.earlier` and `div.ccwcw.later` elements.</span><span class="sxs-lookup"><span data-stu-id="69b38-187">For example, in the following figure, the two elements `div.cwccw.earlier` and `div.cwccw.later` have the same animation \(`spinrightleft`\) applied, as do the `div.ccwcw.earlier` and `div.ccwcw.later` elements.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations.msft.png" alt-text="animation inspector" lightbox="../media/inspect-styles-glitch-display-animations.msft.png":::
   <span data-ttu-id="69b38-189">Color-coded animations</span><span class="sxs-lookup"><span data-stu-id="69b38-189">Color-coded animations</span></span>  
:::image-end:::  

## <span data-ttu-id="69b38-190">Modify animations</span><span class="sxs-lookup"><span data-stu-id="69b38-190">Modify animations</span></span>  

<span data-ttu-id="69b38-191">There are three ways you are able to modify an animation with the Animation Inspector.</span><span class="sxs-lookup"><span data-stu-id="69b38-191">There are three ways you are able to modify an animation with the Animation Inspector.</span></span>  

*   <span data-ttu-id="69b38-192">Animation duration.</span><span class="sxs-lookup"><span data-stu-id="69b38-192">Animation duration.</span></span>  
*   <span data-ttu-id="69b38-193">Keyframe timings.</span><span class="sxs-lookup"><span data-stu-id="69b38-193">Keyframe timings.</span></span>  
*   <span data-ttu-id="69b38-194">Start time delay.</span><span class="sxs-lookup"><span data-stu-id="69b38-194">Start time delay.</span></span>  
    
<span data-ttu-id="69b38-195">In the following figure, the original animation is represented.</span><span class="sxs-lookup"><span data-stu-id="69b38-195">In the following figure, the original animation is represented.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png" alt-text="animation inspector" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png":::
   <span data-ttu-id="69b38-197">Original animation before modification</span><span class="sxs-lookup"><span data-stu-id="69b38-197">Original animation before modification</span></span>  
:::image-end:::  

<span data-ttu-id="69b38-198">To change the duration of an animation, click and drag the first or last circle.</span><span class="sxs-lookup"><span data-stu-id="69b38-198">To change the duration of an animation, click and drag the first or last circle.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png" alt-text="animation inspector" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png":::
   <span data-ttu-id="69b38-200">Modified duration</span><span class="sxs-lookup"><span data-stu-id="69b38-200">Modified duration</span></span>  
:::image-end:::  

<span data-ttu-id="69b38-201">If the animation defines any keyframe rules, then these are represented as white inner circles.</span><span class="sxs-lookup"><span data-stu-id="69b38-201">If the animation defines any keyframe rules, then these are represented as white inner circles.</span></span>  <span data-ttu-id="69b38-202">Click and drag one of these to change the timing of the keyframe.</span><span class="sxs-lookup"><span data-stu-id="69b38-202">Click and drag one of these to change the timing of the keyframe.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png" alt-text="animation inspector" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png":::
   <span data-ttu-id="69b38-204">Modified keyframe</span><span class="sxs-lookup"><span data-stu-id="69b38-204">Modified keyframe</span></span>  
:::image-end:::  

<span data-ttu-id="69b38-205">To add a delay to an animation, click and drag it anywhere except the circles.</span><span class="sxs-lookup"><span data-stu-id="69b38-205">To add a delay to an animation, click and drag it anywhere except the circles.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png" alt-text="animation inspector" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png":::
   <span data-ttu-id="69b38-207">Modified delay</span><span class="sxs-lookup"><span data-stu-id="69b38-207">Modified delay</span></span>  
:::image-end:::  

## <span data-ttu-id="69b38-208">Getting in touch with the Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="69b38-208">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAnimationSpeedButtonsIcon]: ../media/animation-speed-buttons-icon.msft.png  
[ImageReplayButtonIcon]: ../media/replay-button-icon.msft.png  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="69b38-209">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="69b38-209">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="69b38-210">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="69b38-210">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="69b38-212">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="69b38-212">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
