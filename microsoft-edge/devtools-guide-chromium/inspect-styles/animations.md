---
description: 使用 Microsoft Edge DevTools 动画检查器检查和修改动画。
title: 检查动画
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: dba948087ca06015f686d17ba48584199373805a
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439540"
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

# <a name="inspect-animations"></a><span data-ttu-id="5a75d-104">检查动画</span><span class="sxs-lookup"><span data-stu-id="5a75d-104">Inspect animations</span></span>  

<span data-ttu-id="5a75d-105">使用 Microsoft Edge DevTools 动画检查器检查和修改动画。</span><span class="sxs-lookup"><span data-stu-id="5a75d-105">Inspect and modify animations with the Microsoft Edge DevTools Animation Inspector.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png":::
   <span data-ttu-id="5a75d-107">动画检查器</span><span class="sxs-lookup"><span data-stu-id="5a75d-107">animation inspector</span></span>  
:::image-end:::  

### <a name="summary"></a><span data-ttu-id="5a75d-108">摘要</span><span class="sxs-lookup"><span data-stu-id="5a75d-108">Summary</span></span>  

*   <span data-ttu-id="5a75d-109">打开动画检查器捕获动画。</span><span class="sxs-lookup"><span data-stu-id="5a75d-109">Capture animations by opening the Animation Inspector.</span></span>  <span data-ttu-id="5a75d-110">动画检查器自动检测动画并按组排序。</span><span class="sxs-lookup"><span data-stu-id="5a75d-110">The Animation Inspector automatically detects and sorts animations into groups.</span></span>  
*   <span data-ttu-id="5a75d-111">通过减慢动画的速度、重播每个动画或查看源代码来检查动画。</span><span class="sxs-lookup"><span data-stu-id="5a75d-111">Inspect animations by slowing down each one, replaying each one, or viewing the source code.</span></span>  
*   <span data-ttu-id="5a75d-112">通过更改计时、延迟、持续时间或关键帧偏移来修改动画。</span><span class="sxs-lookup"><span data-stu-id="5a75d-112">Modify animations by changing the timing, delay, duration, or keyframe offsets.</span></span>  

## <a name="overview"></a><span data-ttu-id="5a75d-113">概述</span><span class="sxs-lookup"><span data-stu-id="5a75d-113">Overview</span></span>  

<span data-ttu-id="5a75d-114">Microsoft Edge DevTools 动画检查器有两个主要用途。</span><span class="sxs-lookup"><span data-stu-id="5a75d-114">The Microsoft Edge DevTools Animation Inspector has two main purposes.</span></span>  

*   <span data-ttu-id="5a75d-115">检查动画。</span><span class="sxs-lookup"><span data-stu-id="5a75d-115">Inspecting animations.</span></span>  <span data-ttu-id="5a75d-116">你可以减慢、重播或检查动画组的源代码。</span><span class="sxs-lookup"><span data-stu-id="5a75d-116">You want to slow down, replay, or inspect the source code for an Animation Group.</span></span>  
*   <span data-ttu-id="5a75d-117">修改动画。</span><span class="sxs-lookup"><span data-stu-id="5a75d-117">Modifying animations.</span></span>  <span data-ttu-id="5a75d-118">你可以修改动画组的计时、延迟、持续时间或关键帧偏移。</span><span class="sxs-lookup"><span data-stu-id="5a75d-118">You want to modify the timing, delay, duration, or keyframe offsets of an Animation Group.</span></span>  <span data-ttu-id="5a75d-119">贝塞尔编辑和关键帧编辑当前不受支持。</span><span class="sxs-lookup"><span data-stu-id="5a75d-119">Bezier editing and keyframe editing are currently not supported.</span></span>  

<span data-ttu-id="5a75d-120">动画检查器支持 CSS 动画、CSS 过渡和 Web 动画。</span><span class="sxs-lookup"><span data-stu-id="5a75d-120">The Animation Inspector supports CSS animations, CSS transitions, and web animations.</span></span>  `requestAnimationFrame` <span data-ttu-id="5a75d-121">动画当前不受支持。</span><span class="sxs-lookup"><span data-stu-id="5a75d-121">animations are currently not supported.</span></span>  

### <a name="what-is-an-animation-group"></a><span data-ttu-id="5a75d-122">什么是动画组？</span><span class="sxs-lookup"><span data-stu-id="5a75d-122">What is an Animation Group?</span></span>  

<span data-ttu-id="5a75d-123">动画组是一组相互相关的动画。</span><span class="sxs-lookup"><span data-stu-id="5a75d-123">An Animation Group is a group of animations that may be related to each other.</span></span>  <span data-ttu-id="5a75d-124">目前，Web 没有组动画的实际概念，因此动画设计人员和开发人员必须撰写各个动画并设置动画时间，以便动画呈现为一致的视觉效果。</span><span class="sxs-lookup"><span data-stu-id="5a75d-124">Currently, the web has no real concept of a group animation, so motion designers and developers have to compose and time individual animations so that the animations render as one coherent visual effect.</span></span>  <span data-ttu-id="5a75d-125">动画检查器根据开始时间 \（等，不包括延迟）来预测哪些动画是相关的。</span><span class="sxs-lookup"><span data-stu-id="5a75d-125">The Animation Inspector predicts which animations are related based on start time \(excluding delays, and so on\).</span></span>  <span data-ttu-id="5a75d-126">动画检查器还会将动画并排分组。</span><span class="sxs-lookup"><span data-stu-id="5a75d-126">The Animation Inspector also groups the animations side-by-side.</span></span>  
<span data-ttu-id="5a75d-127">换句话说，在同一脚本块中触发的一组动画会被组合在一起。</span><span class="sxs-lookup"><span data-stu-id="5a75d-127">In other words, a set of animations that are all triggered in the same script block are grouped together.</span></span>  <span data-ttu-id="5a75d-128">如果动画是异步动画，它会被放置在单独的组中。</span><span class="sxs-lookup"><span data-stu-id="5a75d-128">If an animation is asynchronous, it is placed in a separate group.</span></span>  

## <a name="get-started"></a><span data-ttu-id="5a75d-129">入门</span><span class="sxs-lookup"><span data-stu-id="5a75d-129">Get started</span></span>  

<span data-ttu-id="5a75d-130">有两种方法可以打开动画检查器：</span><span class="sxs-lookup"><span data-stu-id="5a75d-130">There are two ways to open the Animation Inspector:</span></span>  

*   <span data-ttu-id="5a75d-131">打开“**自定义和控制 DevTools**”菜单</span><span class="sxs-lookup"><span data-stu-id="5a75d-131">Open the **Customize and Control DevTools** menu</span></span>  
    1.  <span data-ttu-id="5a75d-132">导航到“**更多工具**”子菜单。</span><span class="sxs-lookup"><span data-stu-id="5a75d-132">Navigate to the **More tools** sub-menu.</span></span>  
    1.  <span data-ttu-id="5a75d-133">选择“**动画**”：</span><span class="sxs-lookup"><span data-stu-id="5a75d-133">Choose **Animations**:</span></span>  
        
        :::image type="complex" source="../media/inspect-styles-elements-styles-more-tools-animations.msft.png" alt-text="使用主菜单的动画" lightbox="../media/inspect-styles-elements-styles-more-tools-animations.msft.png":::
           <span data-ttu-id="5a75d-135">使用主菜单的**动画**</span><span class="sxs-lookup"><span data-stu-id="5a75d-135">**Animations** using Main Menu</span></span>  
    :::image-end:::  
        
*   <span data-ttu-id="5a75d-136">打开**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="5a75d-136">Open the **Command Menu**</span></span>  
    1.  <span data-ttu-id="5a75d-137">键入 `Drawer: Show Animations`。</span><span class="sxs-lookup"><span data-stu-id="5a75d-137">Type `Drawer: Show Animations`.</span></span>  

<span data-ttu-id="5a75d-138">动画检查器将在控制台工具旁**打开**。</span><span class="sxs-lookup"><span data-stu-id="5a75d-138">The Animation Inspector opens next to the **Console** tool.</span></span>  <span data-ttu-id="5a75d-139">由于动画检查器是一个箱工具，因此你可以从任何 DevTools 面板使用动画检查器。</span><span class="sxs-lookup"><span data-stu-id="5a75d-139">Since the Animation Inspector is a Drawer tool, you may use the Animation Inspector from any DevTools panel.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations.msft.png" alt-text="空动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations.msft.png":::
   <span data-ttu-id="5a75d-141">空动画检查器</span><span class="sxs-lookup"><span data-stu-id="5a75d-141">Empty Animation Inspector</span></span>  
:::image-end:::  

<span data-ttu-id="5a75d-142">动画检查器分为四个主要部分 \ (或窗格\)。</span><span class="sxs-lookup"><span data-stu-id="5a75d-142">The Animation Inspector is grouped into four main sections \(or panes\).</span></span>  <span data-ttu-id="5a75d-143">本指南按以下方式指代每个窗格：</span><span class="sxs-lookup"><span data-stu-id="5a75d-143">This guide refers to each pane as follows:</span></span>  

| <span data-ttu-id="5a75d-144">索引</span><span class="sxs-lookup"><span data-stu-id="5a75d-144">Index</span></span> | <span data-ttu-id="5a75d-145">窗格</span><span class="sxs-lookup"><span data-stu-id="5a75d-145">Pane</span></span> | <span data-ttu-id="5a75d-146">描述</span><span class="sxs-lookup"><span data-stu-id="5a75d-146">Description</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="5a75d-147">1</span><span class="sxs-lookup"><span data-stu-id="5a75d-147">1</span></span> | **<span data-ttu-id="5a75d-148">控件</span><span class="sxs-lookup"><span data-stu-id="5a75d-148">Controls</span></span>** | <span data-ttu-id="5a75d-149">你可以在此处清除当前捕获的所有动画组，或更改当前选定的动画组的速度。</span><span class="sxs-lookup"><span data-stu-id="5a75d-149">From here you may clear all currently captured Animation Groups, or change the speed of the currently selected Animation Group.</span></span> |  
| <span data-ttu-id="5a75d-150">2</span><span class="sxs-lookup"><span data-stu-id="5a75d-150">2</span></span> | **<span data-ttu-id="5a75d-151">概述</span><span class="sxs-lookup"><span data-stu-id="5a75d-151">Overview</span></span>** | <span data-ttu-id="5a75d-152">在此处选择动画组以检查和修改**详细信息**窗格中的动画组。</span><span class="sxs-lookup"><span data-stu-id="5a75d-152">Choose an Animation Group here to inspect and modify it in the **Details** pane.</span></span> |  
| <span data-ttu-id="5a75d-153">3</span><span class="sxs-lookup"><span data-stu-id="5a75d-153">3</span></span> | **<span data-ttu-id="5a75d-154">时间线</span><span class="sxs-lookup"><span data-stu-id="5a75d-154">Timeline</span></span>** | <span data-ttu-id="5a75d-155">从此处暂停并启动动画，或跳转到动画中的特定点。</span><span class="sxs-lookup"><span data-stu-id="5a75d-155">Pause and start an animation from here, or jump to a specific point in the animation.</span></span> |  
| <span data-ttu-id="5a75d-156">4</span><span class="sxs-lookup"><span data-stu-id="5a75d-156">4</span></span> | **<span data-ttu-id="5a75d-157">详细信息</span><span class="sxs-lookup"><span data-stu-id="5a75d-157">Details</span></span>** | <span data-ttu-id="5a75d-158">检查和修改当前选定的动画组。</span><span class="sxs-lookup"><span data-stu-id="5a75d-158">Inspect and modify the currently selected Animation Group.</span></span> |  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png" alt-text="批注动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png":::
   <span data-ttu-id="5a75d-160">批注动画检查器</span><span class="sxs-lookup"><span data-stu-id="5a75d-160">Annotated Animation Inspector</span></span>  
:::image-end:::  

<span data-ttu-id="5a75d-161">若要捕获动画，只需执行在动画检查器打开时触发动画的交互。</span><span class="sxs-lookup"><span data-stu-id="5a75d-161">To capture an animation, just perform the interaction that triggers the animation while the Animation Inspector is open.</span></span>  <span data-ttu-id="5a75d-162">如果在页面加载时触发了动画，请刷新页面，同时打开动画检查器以检测动画。</span><span class="sxs-lookup"><span data-stu-id="5a75d-162">If an animation is triggered on page load, refresh the page with the Animation Inspector open to detect the animation.</span></span>  

<!--  old link: <video src="animations/capture-animations.mp4" autoplay loop muted controls></video>  -->  

<!--  import the video to ACOM using https://review.docs.microsoft.com/en-us/help/contribute/contribute-video-publish?branch=master  -->  

<!--  > [!VIDEO animations/capture-animations.mp4]  -->  

## <a name="inspect-animations"></a><span data-ttu-id="5a75d-163">检查动画</span><span class="sxs-lookup"><span data-stu-id="5a75d-163">Inspect animations</span></span>  

<span data-ttu-id="5a75d-164">捕获动画后，有多种方式可以重播它：</span><span class="sxs-lookup"><span data-stu-id="5a75d-164">After you capture an animation, there are a few ways to replay it:</span></span>  

*   <span data-ttu-id="5a75d-165">将鼠标悬停在“**概述**”窗格中的缩略图上，查看缩略图的预览。</span><span class="sxs-lookup"><span data-stu-id="5a75d-165">Hover on the thumbnail in the **Overview** pane to view a preview of it.</span></span>  
*   <span data-ttu-id="5a75d-166">从“**概述**”窗格选择动画组，\(以便它显示在“**详细信息**”窗格中\) 并选择”**重播**” \(![重播图标](../media/replay-button-icon.msft.png)\) 图标。</span><span class="sxs-lookup"><span data-stu-id="5a75d-166">Choose the Animation Group from the **Overview** pane \(so that it is displayed in the **Details** pane\) and choose the **replay** \(![replay icon](../media/replay-button-icon.msft.png)\) icon.</span></span>  <span data-ttu-id="5a75d-167">动画会在视区中重播。</span><span class="sxs-lookup"><span data-stu-id="5a75d-167">The animation is replayed in the viewport.</span></span>  <span data-ttu-id="5a75d-168">选择“**动画速度** \(![动画速度图标](../media/animation-speed-buttons-icon.msft.png)\)” 图标可更改当前选定的动画组的预览速度。</span><span class="sxs-lookup"><span data-stu-id="5a75d-168">Choose the **animation speed** \(![animation speed icons](../media/animation-speed-buttons-icon.msft.png)\) icons to change the preview speed of the currently selected Animation Group.</span></span>  <span data-ttu-id="5a75d-169">可以使用红色竖线更改当前位置。</span><span class="sxs-lookup"><span data-stu-id="5a75d-169">You may use the red vertical bar to change your current position.</span></span>  
*   <span data-ttu-id="5a75d-170">选择并拖动红色竖线以清理视区动画。</span><span class="sxs-lookup"><span data-stu-id="5a75d-170">Choose and drag the red vertical bar to scrub the viewport animation.</span></span>  
    
### <a name="view-animation-details"></a><span data-ttu-id="5a75d-171">查看动画详细信息</span><span class="sxs-lookup"><span data-stu-id="5a75d-171">View animation details</span></span>  

<span data-ttu-id="5a75d-172">捕获动画组后，从“**概述**”窗格中选择它以查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="5a75d-172">After you capture an Animation Group, choose on it from the **Overview** pane to view the details.</span></span>  <span data-ttu-id="5a75d-173">在“**详细信息**”窗格中，将为每个单独的动画分配一行。</span><span class="sxs-lookup"><span data-stu-id="5a75d-173">In the **Details** pane each individual animation is assigned the a row.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="动画组详细信息" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png":::
   <span data-ttu-id="5a75d-175">动画组详细信息</span><span class="sxs-lookup"><span data-stu-id="5a75d-175">Animation Group details</span></span>  
:::image-end:::  

<span data-ttu-id="5a75d-176">将鼠标悬停在动画上以在视区中突出显示它。</span><span class="sxs-lookup"><span data-stu-id="5a75d-176">Hover on an animation to highlight it in the viewport.</span></span>  <span data-ttu-id="5a75d-177">选择动画以在“**元素**”工具中选择它。</span><span class="sxs-lookup"><span data-stu-id="5a75d-177">Choose the animation to select it in the **Elements** tool.</span></span>  

:::image type="complex" source="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="将鼠标悬停在动画上以在视区中突出显示它" lightbox="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png":::
   <span data-ttu-id="5a75d-179">将鼠标悬停在动画上以在视区中突出显示它</span><span class="sxs-lookup"><span data-stu-id="5a75d-179">Hover on the animation to highlight it in viewport</span></span>  
:::image-end:::  

<span data-ttu-id="5a75d-180">动画最左侧较暗的部分就是定义。</span><span class="sxs-lookup"><span data-stu-id="5a75d-180">The leftmost, darker section of an animation is the definition.</span></span>  <span data-ttu-id="5a75d-181">右侧更淡出的部分表示迭代。</span><span class="sxs-lookup"><span data-stu-id="5a75d-181">The right, more faded section represents iterations.</span></span>  <span data-ttu-id="5a75d-182">例如，在下图中，第二节和第三节表示第一节的迭代。</span><span class="sxs-lookup"><span data-stu-id="5a75d-182">For example, in the following figure, sections two and three represent iterations of section one.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations-highlight.msft.png" alt-text="动画迭代关系图" lightbox="../media/inspect-styles-glitch-display-animations-highlight.msft.png":::
   <span data-ttu-id="5a75d-184">动画迭代关系图</span><span class="sxs-lookup"><span data-stu-id="5a75d-184">Diagram of animation iterations</span></span>  
:::image-end:::  

<span data-ttu-id="5a75d-185">如果两个元素应用了相同的动画，则动画检查器会向这些元素分配相同的颜色。</span><span class="sxs-lookup"><span data-stu-id="5a75d-185">If two elements have the same animation applied, the Animation Inspector assigns the same color to the elements.</span></span>  <span data-ttu-id="5a75d-186">颜色是随机的，没有意义。</span><span class="sxs-lookup"><span data-stu-id="5a75d-186">The color is random and has no significance.</span></span>  <span data-ttu-id="5a75d-187">例如，在下图中，这两个元素 `div.cwccw.earlier` 和 `div.cwccw.later` 应用了相同的动画 \(`spinrightleft`\)， `div.ccwcw.earlier` 和 `div.ccwcw.later` 元素也是。</span><span class="sxs-lookup"><span data-stu-id="5a75d-187">For example, in the following figure, the two elements `div.cwccw.earlier` and `div.cwccw.later` have the same animation \(`spinrightleft`\) applied, as do the `div.ccwcw.earlier` and `div.ccwcw.later` elements.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations.msft.png" alt-text="颜色编码动画" lightbox="../media/inspect-styles-glitch-display-animations.msft.png":::
   <span data-ttu-id="5a75d-189">颜色编码动画</span><span class="sxs-lookup"><span data-stu-id="5a75d-189">Color-coded animations</span></span>  
:::image-end:::  

## <a name="modify-animations"></a><span data-ttu-id="5a75d-190">修改动画</span><span class="sxs-lookup"><span data-stu-id="5a75d-190">Modify animations</span></span>  

<span data-ttu-id="5a75d-191">有三种方法可以使用动画检查器修改动画。</span><span class="sxs-lookup"><span data-stu-id="5a75d-191">There are three ways you are able to modify an animation with the Animation Inspector.</span></span>  

*   <span data-ttu-id="5a75d-192">动画持续时间。</span><span class="sxs-lookup"><span data-stu-id="5a75d-192">Animation duration.</span></span>  
*   <span data-ttu-id="5a75d-193">关键帧计时。</span><span class="sxs-lookup"><span data-stu-id="5a75d-193">Keyframe timings.</span></span>  
*   <span data-ttu-id="5a75d-194">开始时间延迟。</span><span class="sxs-lookup"><span data-stu-id="5a75d-194">Start time delay.</span></span>  
    
<span data-ttu-id="5a75d-195">下图中显示了原始动画。</span><span class="sxs-lookup"><span data-stu-id="5a75d-195">In the following figure, the original animation is represented.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png" alt-text="修改前的原始动画" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png":::
   <span data-ttu-id="5a75d-197">修改前的原始动画</span><span class="sxs-lookup"><span data-stu-id="5a75d-197">Original animation before modification</span></span>  
:::image-end:::  

<span data-ttu-id="5a75d-198">若要更改动画的持续时间，请选择并拖动第一个或最后一个圆。</span><span class="sxs-lookup"><span data-stu-id="5a75d-198">To change the duration of an animation, choose and drag the first or last circle.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png" alt-text="修改持续时间" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png":::
   <span data-ttu-id="5a75d-200">修改持续时间</span><span class="sxs-lookup"><span data-stu-id="5a75d-200">Modified duration</span></span>  
:::image-end:::  

<span data-ttu-id="5a75d-201">如果动画定义任何关键帧规则，则这些规则表示为白色内部圆。</span><span class="sxs-lookup"><span data-stu-id="5a75d-201">If the animation defines any keyframe rules, then these are represented as white inner circles.</span></span>  <span data-ttu-id="5a75d-202">选择并拖动其中一个以更改关键帧的计时。</span><span class="sxs-lookup"><span data-stu-id="5a75d-202">Choose and drag one of these to change the timing of the keyframe.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png" alt-text="修改后的关键帧" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png":::
   <span data-ttu-id="5a75d-204">修改后的关键帧</span><span class="sxs-lookup"><span data-stu-id="5a75d-204">Modified keyframe</span></span>  
:::image-end:::  

<span data-ttu-id="5a75d-205">若要向动画添加延迟，请选择并将其拖动到除圆形之外的任何位置。</span><span class="sxs-lookup"><span data-stu-id="5a75d-205">To add a delay to an animation, choose and drag it anywhere except the circles.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png" alt-text="修改后的延迟" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png":::
   <span data-ttu-id="5a75d-207">修改后的延迟</span><span class="sxs-lookup"><span data-stu-id="5a75d-207">Modified delay</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="5a75d-208">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="5a75d-208">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

<span data-ttu-id="5a75d-209">(../media/animation-speed-buttons-icon.msft.png): ../media/animation-speed-buttons-icon.msft.png</span><span class="sxs-lookup"><span data-stu-id="5a75d-209">(../media/animation-speed-buttons-icon.msft.png): ../media/animation-speed-buttons-icon.msft.png</span></span>  
<span data-ttu-id="5a75d-210">(../media/replay-button-icon.msft.png): ../media/replay-button-icon.msft.png</span><span class="sxs-lookup"><span data-stu-id="5a75d-210">(../media/replay-button-icon.msft.png): ../media/replay-button-icon.msft.png</span></span>  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="5a75d-211">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="5a75d-211">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5a75d-212">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="5a75d-212">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="5a75d-214">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="5a75d-214">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
