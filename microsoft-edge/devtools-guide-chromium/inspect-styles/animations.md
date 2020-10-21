---
description: 通过 Microsoft Edge DevTools 动画检查器检查和修改动画。
title: 检查动画
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: fed686c07acd0648ac512dac131d85a317fb64eb
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11124773"
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

# <span data-ttu-id="6180f-104">检查动画</span><span class="sxs-lookup"><span data-stu-id="6180f-104">Inspect animations</span></span>  

<span data-ttu-id="6180f-105">通过 Microsoft Edge DevTools 动画检查器检查和修改动画。</span><span class="sxs-lookup"><span data-stu-id="6180f-105">Inspect and modify animations with the Microsoft Edge DevTools Animation Inspector.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png":::
   <span data-ttu-id="6180f-107">动画检查器</span><span class="sxs-lookup"><span data-stu-id="6180f-107">animation inspector</span></span>  
:::image-end:::  

### <span data-ttu-id="6180f-108">摘要</span><span class="sxs-lookup"><span data-stu-id="6180f-108">Summary</span></span>  

*   <span data-ttu-id="6180f-109">通过打开 "动画检查器" 捕获动画。</span><span class="sxs-lookup"><span data-stu-id="6180f-109">Capture animations by opening the Animation Inspector.</span></span>  <span data-ttu-id="6180f-110">动画检查器会自动检测动画并将其排序为多个组。</span><span class="sxs-lookup"><span data-stu-id="6180f-110">The Animation Inspector automatically detects and sorts animations into groups.</span></span>  
*   <span data-ttu-id="6180f-111">通过减速、重放每个动画或查看源代码来检查动画。</span><span class="sxs-lookup"><span data-stu-id="6180f-111">Inspect animations by slowing down each one, replaying each one, or viewing the source code.</span></span>  
*   <span data-ttu-id="6180f-112">通过更改计时、延迟、持续时间或关键帧偏移来修改动画。</span><span class="sxs-lookup"><span data-stu-id="6180f-112">Modify animations by changing the timing, delay, duration, or keyframe offsets.</span></span>  

## <span data-ttu-id="6180f-113">概述</span><span class="sxs-lookup"><span data-stu-id="6180f-113">Overview</span></span>  

<span data-ttu-id="6180f-114">Microsoft Edge DevTools 动画检查器有两个主要用途。</span><span class="sxs-lookup"><span data-stu-id="6180f-114">The Microsoft Edge DevTools Animation Inspector has two main purposes.</span></span>  

*   <span data-ttu-id="6180f-115">检查动画。</span><span class="sxs-lookup"><span data-stu-id="6180f-115">Inspecting animations.</span></span>  <span data-ttu-id="6180f-116">你希望减慢、重播或检查动画组的源代码。</span><span class="sxs-lookup"><span data-stu-id="6180f-116">You want to slow down, replay, or inspect the source code for an Animation Group.</span></span>  
*   <span data-ttu-id="6180f-117">修改动画。</span><span class="sxs-lookup"><span data-stu-id="6180f-117">Modifying animations.</span></span>  <span data-ttu-id="6180f-118">要修改动画组的计时、延迟、持续时间或关键帧偏移量。</span><span class="sxs-lookup"><span data-stu-id="6180f-118">You want to modify the timing, delay, duration, or keyframe offsets of an Animation Group.</span></span>  <span data-ttu-id="6180f-119">当前不支持贝塞尔编辑和关键帧编辑。</span><span class="sxs-lookup"><span data-stu-id="6180f-119">Bezier editing and keyframe editing are currently not supported.</span></span>  

<span data-ttu-id="6180f-120">动画检查器支持 CSS 动画、CSS 转换和 web 动画。</span><span class="sxs-lookup"><span data-stu-id="6180f-120">The Animation Inspector supports CSS animations, CSS transitions, and web animations.</span></span>  `requestAnimationFrame` <span data-ttu-id="6180f-121">当前不支持动画。</span><span class="sxs-lookup"><span data-stu-id="6180f-121">animations are currently not supported.</span></span>  

### <span data-ttu-id="6180f-122">什么是动画组？</span><span class="sxs-lookup"><span data-stu-id="6180f-122">What is an Animation Group?</span></span>  

<span data-ttu-id="6180f-123">动画组是可能相互关联的一组动画。</span><span class="sxs-lookup"><span data-stu-id="6180f-123">An Animation Group is a group of animations that may be related to each other.</span></span>  <span data-ttu-id="6180f-124">目前，web 没有组动画的真正概念，因此动画设计器和开发人员必须编写和时间单个动画，以便动画呈现为一个连贯的视觉效果。</span><span class="sxs-lookup"><span data-stu-id="6180f-124">Currently, the web has no real concept of a group animation, so motion designers and developers have to compose and time individual animations so that the animations render as one coherent visual effect.</span></span>  <span data-ttu-id="6180f-125">动画检查器将预测哪些动画基于开始时间 \ (不包括延迟，如此 ) 。</span><span class="sxs-lookup"><span data-stu-id="6180f-125">The Animation Inspector predicts which animations are related based on start time \(excluding delays, and so on\).</span></span>  <span data-ttu-id="6180f-126">动画检查器还会并排对动画进行分组。</span><span class="sxs-lookup"><span data-stu-id="6180f-126">The Animation Inspector also groups the animations side-by-side.</span></span>  
<span data-ttu-id="6180f-127">换句话说，在同一脚本块中同时触发的一组动画将组合在一起。</span><span class="sxs-lookup"><span data-stu-id="6180f-127">In other words, a set of animations that are all triggered in the same script block are grouped together.</span></span>  <span data-ttu-id="6180f-128">如果动画是异步的，则将其放置在单独的组中。</span><span class="sxs-lookup"><span data-stu-id="6180f-128">If an animation is asynchronous, it is placed in a separate group.</span></span>  

## <span data-ttu-id="6180f-129">开始行动</span><span class="sxs-lookup"><span data-stu-id="6180f-129">Get started</span></span>  

<span data-ttu-id="6180f-130">可通过两种方式打开 "动画" 检查器：</span><span class="sxs-lookup"><span data-stu-id="6180f-130">There are two ways to open the Animation Inspector:</span></span>  

*   <span data-ttu-id="6180f-131">打开 " **自定义和控制" DevTools** 菜单</span><span class="sxs-lookup"><span data-stu-id="6180f-131">Open the **Customize and Control DevTools** menu</span></span>  
    1.  <span data-ttu-id="6180f-132">导航到 " **更多工具** " 子菜单。</span><span class="sxs-lookup"><span data-stu-id="6180f-132">Navigate to the **More tools** sub-menu.</span></span>  
    1.  <span data-ttu-id="6180f-133">选择 " **动画**"：</span><span class="sxs-lookup"><span data-stu-id="6180f-133">Choose **Animations**:</span></span>  
        
        :::image type="complex" source="../media/inspect-styles-elements-styles-more-tools-animations.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-elements-styles-more-tools-animations.msft.png":::
           <span data-ttu-id="6180f-135">使用主菜单的**动画**</span><span class="sxs-lookup"><span data-stu-id="6180f-135">**Animations** using Main Menu</span></span>  
    :::image-end:::  
        
*   <span data-ttu-id="6180f-136">打开 " **命令" 菜单**</span><span class="sxs-lookup"><span data-stu-id="6180f-136">Open the **Command Menu**</span></span>  
    1.  <span data-ttu-id="6180f-137">键入 `Drawer: Show Animations`。</span><span class="sxs-lookup"><span data-stu-id="6180f-137">Type `Drawer: Show Animations`.</span></span>  

<span data-ttu-id="6180f-138">"动画" 检查器将在控制台抽屉旁边的选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="6180f-138">The Animation Inspector opens up as a tab next to the Console Drawer.</span></span>  <span data-ttu-id="6180f-139">由于动画检查器是一个抽屉选项卡，因此您可以使用任何 DevTools 面板中的动画检查器。</span><span class="sxs-lookup"><span data-stu-id="6180f-139">Since the Animation Inspector is a Drawer tab, you may use the Animation Inspector from any DevTools panel.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations.msft.png":::
   <span data-ttu-id="6180f-141">清空动画检查器</span><span class="sxs-lookup"><span data-stu-id="6180f-141">Empty Animation Inspector</span></span>  
:::image-end:::  

<span data-ttu-id="6180f-142">动画检查器分为四个主要部分，即 " (" 或 "窗格 \ ) "。</span><span class="sxs-lookup"><span data-stu-id="6180f-142">The Animation Inspector is grouped into four main sections \(or panes\).</span></span>  <span data-ttu-id="6180f-143">本指南按如下方式引用每个窗格：</span><span class="sxs-lookup"><span data-stu-id="6180f-143">This guide refers to each pane as follows:</span></span>  

| <span data-ttu-id="6180f-144">索引</span><span class="sxs-lookup"><span data-stu-id="6180f-144">Index</span></span> | <span data-ttu-id="6180f-145">窗格</span><span class="sxs-lookup"><span data-stu-id="6180f-145">Pane</span></span> | <span data-ttu-id="6180f-146">描述</span><span class="sxs-lookup"><span data-stu-id="6180f-146">Description</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="6180f-147">raid-1</span><span class="sxs-lookup"><span data-stu-id="6180f-147">1</span></span> | **<span data-ttu-id="6180f-148">控件</span><span class="sxs-lookup"><span data-stu-id="6180f-148">Controls</span></span>** | <span data-ttu-id="6180f-149">你可以从此处清除当前捕获的所有动画组，或更改当前所选动画组的速度。</span><span class="sxs-lookup"><span data-stu-id="6180f-149">From here you may clear all currently captured Animation Groups, or change the speed of the currently selected Animation Group.</span></span> |  
| <span data-ttu-id="6180f-150">ppls-2</span><span class="sxs-lookup"><span data-stu-id="6180f-150">2</span></span> | **<span data-ttu-id="6180f-151">概述</span><span class="sxs-lookup"><span data-stu-id="6180f-151">Overview</span></span>** | <span data-ttu-id="6180f-152">在此处选择一个动画组以在 " **详细信息** " 窗格中检查和修改它。</span><span class="sxs-lookup"><span data-stu-id="6180f-152">Select an Animation Group here to inspect and modify it in the **Details** pane.</span></span> |  
| <span data-ttu-id="6180f-153">三维空间</span><span class="sxs-lookup"><span data-stu-id="6180f-153">3</span></span> | **<span data-ttu-id="6180f-154">时间线</span><span class="sxs-lookup"><span data-stu-id="6180f-154">Timeline</span></span>** | <span data-ttu-id="6180f-155">在此处暂停和启动动画，或跳转到动画中的特定点。</span><span class="sxs-lookup"><span data-stu-id="6180f-155">Pause and start an animation from here, or jump to a specific point in the animation.</span></span> |  
| <span data-ttu-id="6180f-156">第</span><span class="sxs-lookup"><span data-stu-id="6180f-156">4</span></span> | **<span data-ttu-id="6180f-157">详细信息</span><span class="sxs-lookup"><span data-stu-id="6180f-157">Details</span></span>** | <span data-ttu-id="6180f-158">检查和修改当前所选的动画组。</span><span class="sxs-lookup"><span data-stu-id="6180f-158">Inspect and modify the currently selected Animation Group.</span></span> |  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png":::
   <span data-ttu-id="6180f-160">带批注的动画检查器</span><span class="sxs-lookup"><span data-stu-id="6180f-160">Annotated Animation Inspector</span></span>  
:::image-end:::  

<span data-ttu-id="6180f-161">若要捕获动画，只需在动画检查器打开的情况下执行触发动画的交互。</span><span class="sxs-lookup"><span data-stu-id="6180f-161">To capture an animation, just perform the interaction that triggers the animation while the Animation Inspector is open.</span></span>  <span data-ttu-id="6180f-162">如果动画是在页面加载时触发的，请使用动画检查器打开来重新加载页面以检测动画。</span><span class="sxs-lookup"><span data-stu-id="6180f-162">If an animation is triggered on page load, reload the page with the Animation Inspector open to detect the animation.</span></span>  

<!--  old link: <video src="animations/capture-animations.mp4" autoplay loop muted controls></video>  -->  

<!--  import the video to ACOM using https://review.docs.microsoft.com/en-us/help/contribute/contribute-video-publish?branch=master  -->  

<!--  > [!VIDEO animations/capture-animations.mp4]  -->  

## <span data-ttu-id="6180f-163">检查动画</span><span class="sxs-lookup"><span data-stu-id="6180f-163">Inspect animations</span></span>  

<span data-ttu-id="6180f-164">捕获动画后，有几种方法可以重播它：</span><span class="sxs-lookup"><span data-stu-id="6180f-164">After you capture an animation, there are a few ways to replay it:</span></span>  

*   <span data-ttu-id="6180f-165">将鼠标悬停在 " **概述** " 窗格的缩略图上以查看它的预览。</span><span class="sxs-lookup"><span data-stu-id="6180f-165">Hover over the thumbnail in the **Overview** pane to view a preview of it.</span></span>  
*   <span data-ttu-id="6180f-166">从 " **概述** " 窗格中选择 "动画" 组 \ (，使其显示在 " **详细信息** " 窗格 \ ) 中，然后按 " **重播** \ (![ 重播" 图标 ][ImageReplayButtonIcon] \ ) 图标。</span><span class="sxs-lookup"><span data-stu-id="6180f-166">Select the Animation Group from the **Overview** pane \(so that it is displayed in the **Details** pane\) and press the **replay** \(![replay icon][ImageReplayButtonIcon]\) icon.</span></span>  <span data-ttu-id="6180f-167">将在视区中重播动画。</span><span class="sxs-lookup"><span data-stu-id="6180f-167">The animation is replayed in the viewport.</span></span>  <span data-ttu-id="6180f-168">单击 " **动画速度** " (![ 动画速度图标 ][ImageAnimationSpeedButtonsIcon] \ ) 图标，以更改当前所选动画组的预览速度。</span><span class="sxs-lookup"><span data-stu-id="6180f-168">Click on the **animation speed** \(![animation speed icons][ImageAnimationSpeedButtonsIcon]\) icons to change the preview speed of the currently selected Animation Group.</span></span>  <span data-ttu-id="6180f-169">您可以使用红色垂直条更改您的当前位置。</span><span class="sxs-lookup"><span data-stu-id="6180f-169">You may use the red vertical bar to change your current position.</span></span>  
*   <span data-ttu-id="6180f-170">单击并拖动红色垂直条以擦除视区动画。</span><span class="sxs-lookup"><span data-stu-id="6180f-170">Click and drag the red vertical bar to scrub the viewport animation.</span></span>  
    
### <span data-ttu-id="6180f-171">查看动画详细信息</span><span class="sxs-lookup"><span data-stu-id="6180f-171">View animation details</span></span>  

<span data-ttu-id="6180f-172">捕获动画组后，从 " **概述** " 窗格中单击它以查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="6180f-172">After you capture an Animation Group, click on it from the **Overview** pane to view the details.</span></span>  <span data-ttu-id="6180f-173">在 " **详细信息** " 窗格中，每个单独的动画都分配有一行。</span><span class="sxs-lookup"><span data-stu-id="6180f-173">In the **Details** pane each individual animation is assigned the a row.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png":::
   <span data-ttu-id="6180f-175">动画组详细信息</span><span class="sxs-lookup"><span data-stu-id="6180f-175">Animation Group details</span></span>  
:::image-end:::  

<span data-ttu-id="6180f-176">将鼠标悬停在某个动画上，将其在视区中突出显示。</span><span class="sxs-lookup"><span data-stu-id="6180f-176">Hover over an animation to highlight it in the viewport.</span></span>  <span data-ttu-id="6180f-177">单击动画以在 " **元素** " 面板中选择它。</span><span class="sxs-lookup"><span data-stu-id="6180f-177">Click on the animation to select it in the **Elements** panel.</span></span>  

:::image type="complex" source="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png":::
   <span data-ttu-id="6180f-179">将鼠标悬停在动画上以在视区中突出显示</span><span class="sxs-lookup"><span data-stu-id="6180f-179">Hover over the animation to highlight it in viewport</span></span>  
:::image-end:::  

<span data-ttu-id="6180f-180">动画最左边、更暗的部分是定义。</span><span class="sxs-lookup"><span data-stu-id="6180f-180">The leftmost, darker section of an animation is the definition.</span></span>  <span data-ttu-id="6180f-181">右侧、更淡出的部分表示迭代。</span><span class="sxs-lookup"><span data-stu-id="6180f-181">The right, more faded section represents iterations.</span></span>  <span data-ttu-id="6180f-182">例如，在下图中，第二部分和第三部分表示第一节的迭代。</span><span class="sxs-lookup"><span data-stu-id="6180f-182">For example, in the following figure, sections two and three represent iterations of section one.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations-highlight.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-glitch-display-animations-highlight.msft.png":::
   <span data-ttu-id="6180f-184">动画迭代图表</span><span class="sxs-lookup"><span data-stu-id="6180f-184">Diagram of animation iterations</span></span>  
:::image-end:::  

<span data-ttu-id="6180f-185">如果两个元素应用了相同的动画，则动画检查器会为元素分配相同的颜色。</span><span class="sxs-lookup"><span data-stu-id="6180f-185">If two elements have the same animation applied, the Animation Inspector assigns the same color to the elements.</span></span>  <span data-ttu-id="6180f-186">颜色是随机的，没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="6180f-186">The color is random and has no significance.</span></span>  <span data-ttu-id="6180f-187">例如，下图中，这两个元素 `div.cwccw.earlier` `div.cwccw.later` 具有相同的动画 \ (`spinrightleft` \ ) 应用，就像执行 `div.ccwcw.earlier` 和元素一样 `div.ccwcw.later` 。</span><span class="sxs-lookup"><span data-stu-id="6180f-187">For example, in the following figure, the two elements `div.cwccw.earlier` and `div.cwccw.later` have the same animation \(`spinrightleft`\) applied, as do the `div.ccwcw.earlier` and `div.ccwcw.later` elements.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-glitch-display-animations.msft.png":::
   <span data-ttu-id="6180f-189">颜色编码的动画</span><span class="sxs-lookup"><span data-stu-id="6180f-189">Color-coded animations</span></span>  
:::image-end:::  

## <span data-ttu-id="6180f-190">修改动画</span><span class="sxs-lookup"><span data-stu-id="6180f-190">Modify animations</span></span>  

<span data-ttu-id="6180f-191">你可以通过三种方式使用动画检查器修改动画。</span><span class="sxs-lookup"><span data-stu-id="6180f-191">There are three ways you are able to modify an animation with the Animation Inspector.</span></span>  

*   <span data-ttu-id="6180f-192">动画持续时间。</span><span class="sxs-lookup"><span data-stu-id="6180f-192">Animation duration.</span></span>  
*   <span data-ttu-id="6180f-193">关键帧计时。</span><span class="sxs-lookup"><span data-stu-id="6180f-193">Keyframe timings.</span></span>  
*   <span data-ttu-id="6180f-194">开始时间延迟。</span><span class="sxs-lookup"><span data-stu-id="6180f-194">Start time delay.</span></span>  
    
<span data-ttu-id="6180f-195">在下图中，表示原始动画。</span><span class="sxs-lookup"><span data-stu-id="6180f-195">In the following figure, the original animation is represented.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png":::
   <span data-ttu-id="6180f-197">修改前的原始动画</span><span class="sxs-lookup"><span data-stu-id="6180f-197">Original animation before modification</span></span>  
:::image-end:::  

<span data-ttu-id="6180f-198">若要更改动画的持续时间，请单击并拖动第一个或最后一个圆。</span><span class="sxs-lookup"><span data-stu-id="6180f-198">To change the duration of an animation, click and drag the first or last circle.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png":::
   <span data-ttu-id="6180f-200">已修改工期</span><span class="sxs-lookup"><span data-stu-id="6180f-200">Modified duration</span></span>  
:::image-end:::  

<span data-ttu-id="6180f-201">如果动画定义了任何关键帧规则，则这些规则表示为白色内圆圈。</span><span class="sxs-lookup"><span data-stu-id="6180f-201">If the animation defines any keyframe rules, then these are represented as white inner circles.</span></span>  <span data-ttu-id="6180f-202">单击并拖动其中一个以更改关键帧的计时。</span><span class="sxs-lookup"><span data-stu-id="6180f-202">Click and drag one of these to change the timing of the keyframe.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png":::
   <span data-ttu-id="6180f-204">修改的关键帧</span><span class="sxs-lookup"><span data-stu-id="6180f-204">Modified keyframe</span></span>  
:::image-end:::  

<span data-ttu-id="6180f-205">若要向动画添加延迟，请单击并将其拖动到除圆圈外的任意位置。</span><span class="sxs-lookup"><span data-stu-id="6180f-205">To add a delay to an animation, click and drag it anywhere except the circles.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png":::
   <span data-ttu-id="6180f-207">修改后的延迟</span><span class="sxs-lookup"><span data-stu-id="6180f-207">Modified delay</span></span>  
:::image-end:::  

## <span data-ttu-id="6180f-208">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="6180f-208">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAnimationSpeedButtonsIcon]: ../media/animation-speed-buttons-icon.msft.png  
[ImageReplayButtonIcon]: ../media/replay-button-icon.msft.png  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="6180f-209">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="6180f-209">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6180f-210">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="6180f-210">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="6180f-212">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="6180f-212">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
