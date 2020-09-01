---
title: 检查动画
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: a6970d76f4ff70031ef4cc8c6de119a41d1a5b80
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10983357"
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





# <span data-ttu-id="6c9d2-103">检查动画</span><span class="sxs-lookup"><span data-stu-id="6c9d2-103">Inspect animations</span></span>   



<span data-ttu-id="6c9d2-104">通过 Microsoft Edge DevTools 动画检查器检查和修改动画。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-104">Inspect and modify animations with the Microsoft Edge DevTools Animation Inspector.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png":::
   <span data-ttu-id="6c9d2-106">动画检查器</span><span class="sxs-lookup"><span data-stu-id="6c9d2-106">animation inspector</span></span>  
:::image-end:::  

### <span data-ttu-id="6c9d2-107">摘要</span><span class="sxs-lookup"><span data-stu-id="6c9d2-107">Summary</span></span>  

*   <span data-ttu-id="6c9d2-108">通过打开 "动画检查器" 捕获动画。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-108">Capture animations by opening the Animation Inspector.</span></span>  <span data-ttu-id="6c9d2-109">动画检查器会自动检测动画并将其排序为多个组。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-109">The Animation Inspector automatically detects and sorts animations into groups.</span></span>  
*   <span data-ttu-id="6c9d2-110">通过减速、重放每个动画或查看源代码来检查动画。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-110">Inspect animations by slowing down each one, replaying each one, or viewing the source code.</span></span>  
*   <span data-ttu-id="6c9d2-111">通过更改计时、延迟、持续时间或关键帧偏移来修改动画。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-111">Modify animations by changing the timing, delay, duration, or keyframe offsets.</span></span>  

## <span data-ttu-id="6c9d2-112">概述</span><span class="sxs-lookup"><span data-stu-id="6c9d2-112">Overview</span></span>   

<span data-ttu-id="6c9d2-113">Microsoft Edge DevTools 动画检查器有两个主要用途。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-113">The Microsoft Edge DevTools Animation Inspector has two main purposes.</span></span>  

*   <span data-ttu-id="6c9d2-114">检查动画。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-114">Inspecting animations.</span></span>  <span data-ttu-id="6c9d2-115">你希望减慢、重播或检查动画组的源代码。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-115">You want to slow down, replay, or inspect the source code for an Animation Group.</span></span>  
*   <span data-ttu-id="6c9d2-116">修改动画。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-116">Modifying animations.</span></span>  <span data-ttu-id="6c9d2-117">要修改动画组的计时、延迟、持续时间或关键帧偏移量。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-117">You want to modify the timing, delay, duration, or keyframe offsets of an Animation Group.</span></span>  <span data-ttu-id="6c9d2-118">当前不支持贝塞尔编辑和关键帧编辑。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-118">Bezier editing and keyframe editing are currently not supported.</span></span>  

<span data-ttu-id="6c9d2-119">动画检查器支持 CSS 动画、CSS 转换和 web 动画。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-119">The Animation Inspector supports CSS animations, CSS transitions, and web animations.</span></span>  `requestAnimationFrame` <span data-ttu-id="6c9d2-120">当前不支持动画。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-120">animations are currently not supported.</span></span>  

### <span data-ttu-id="6c9d2-121">什么是动画组？</span><span class="sxs-lookup"><span data-stu-id="6c9d2-121">What is an Animation Group?</span></span>  

<span data-ttu-id="6c9d2-122">动画组是可能相互关联的一组动画。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-122">An Animation Group is a group of animations that may be related to each other.</span></span>  <span data-ttu-id="6c9d2-123">目前，web 没有组动画的真正概念，因此动画设计器和开发人员必须编写和时间单个动画，以便动画呈现为一个连贯的视觉效果。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-123">Currently, the web has no real concept of a group animation, so motion designers and developers have to compose and time individual animations so that the animations render as one coherent visual effect.</span></span>  <span data-ttu-id="6c9d2-124">动画检查器将预测哪些动画基于开始时间 \ (不包括延迟，如此 ) 。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-124">The Animation Inspector predicts which animations are related based on start time \(excluding delays, and so on\).</span></span>  <span data-ttu-id="6c9d2-125">动画检查器还会并排对动画进行分组。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-125">The Animation Inspector also groups the animations side-by-side.</span></span>  
<span data-ttu-id="6c9d2-126">换句话说，在同一脚本块中同时触发的一组动画将组合在一起。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-126">In other words, a set of animations that are all triggered in the same script block are grouped together.</span></span>  <span data-ttu-id="6c9d2-127">如果动画是异步的，则将其放置在单独的组中。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-127">If an animation is asynchronous, it is placed in a separate group.</span></span>  

## <span data-ttu-id="6c9d2-128">入门</span><span class="sxs-lookup"><span data-stu-id="6c9d2-128">Get started</span></span>  

<span data-ttu-id="6c9d2-129">可通过两种方式打开 "动画" 检查器：</span><span class="sxs-lookup"><span data-stu-id="6c9d2-129">There are two ways to open the Animation Inspector:</span></span>  

*   <span data-ttu-id="6c9d2-130">打开 " **自定义和控制" DevTools** 菜单</span><span class="sxs-lookup"><span data-stu-id="6c9d2-130">Open the **Customize and Control DevTools** menu</span></span>  
    1.  <span data-ttu-id="6c9d2-131">导航到 " **更多工具** " 子菜单。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-131">Navigate to the **More tools** sub-menu.</span></span>  
    1.  <span data-ttu-id="6c9d2-132">选择 " **动画**"：</span><span class="sxs-lookup"><span data-stu-id="6c9d2-132">Select **Animations**:</span></span>  
        
        :::image type="complex" source="../media/inspect-styles-elements-styles-more-tools-animations.msft.png" alt-text="使用主菜单的动画" lightbox="../media/inspect-styles-elements-styles-more-tools-animations.msft.png":::
           <span data-ttu-id="6c9d2-134">使用主菜单的**动画**</span><span class="sxs-lookup"><span data-stu-id="6c9d2-134">**Animations** using Main Menu</span></span>  
    :::image-end:::  
        
*   <span data-ttu-id="6c9d2-135">打开 " **命令" 菜单**</span><span class="sxs-lookup"><span data-stu-id="6c9d2-135">Open the **Command Menu**</span></span>  
    1.  <span data-ttu-id="6c9d2-136">键入 `Drawer: Show Animations`。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-136">Type `Drawer: Show Animations`.</span></span>  

<span data-ttu-id="6c9d2-137">"动画" 检查器将在控制台抽屉旁边的选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-137">The Animation Inspector opens up as a tab next to the Console Drawer.</span></span>  <span data-ttu-id="6c9d2-138">由于动画检查器是一个抽屉选项卡，因此您可以使用任何 DevTools 面板中的动画检查器。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-138">Since the Animation Inspector is a Drawer tab, you may use the Animation Inspector from any DevTools panel.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations.msft.png" alt-text="清空动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations.msft.png":::
   <span data-ttu-id="6c9d2-140">清空动画检查器</span><span class="sxs-lookup"><span data-stu-id="6c9d2-140">Empty Animation Inspector</span></span>  
:::image-end:::  

<span data-ttu-id="6c9d2-141">动画检查器分为四个主要部分，即 " (" 或 "窗格 \ ) "。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-141">The Animation Inspector is grouped into four main sections \(or panes\).</span></span>  <span data-ttu-id="6c9d2-142">本指南按如下方式引用每个窗格：</span><span class="sxs-lookup"><span data-stu-id="6c9d2-142">This guide refers to each pane as follows:</span></span>  

| | <span data-ttu-id="6c9d2-143">窗格</span><span class="sxs-lookup"><span data-stu-id="6c9d2-143">Pane</span></span> | <span data-ttu-id="6c9d2-144">描述</span><span class="sxs-lookup"><span data-stu-id="6c9d2-144">Description</span></span> |  
| --- |:--- |:--- |  
| <span data-ttu-id="6c9d2-145">raid-1</span><span class="sxs-lookup"><span data-stu-id="6c9d2-145">1</span></span> | **<span data-ttu-id="6c9d2-146">控件</span><span class="sxs-lookup"><span data-stu-id="6c9d2-146">Controls</span></span>** | <span data-ttu-id="6c9d2-147">你可以从此处清除当前捕获的所有动画组，或更改当前所选动画组的速度。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-147">From here you may clear all currently captured Animation Groups, or change the speed of the currently selected Animation Group.</span></span> |  
| <span data-ttu-id="6c9d2-148">ppls-2</span><span class="sxs-lookup"><span data-stu-id="6c9d2-148">2</span></span> | **<span data-ttu-id="6c9d2-149">概述</span><span class="sxs-lookup"><span data-stu-id="6c9d2-149">Overview</span></span>** | <span data-ttu-id="6c9d2-150">在此处选择一个动画组以在 " **详细信息** " 窗格中检查和修改它。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-150">Select an Animation Group here to inspect and modify it in the **Details** pane.</span></span> |  
| <span data-ttu-id="6c9d2-151">三维空间</span><span class="sxs-lookup"><span data-stu-id="6c9d2-151">3</span></span> | **<span data-ttu-id="6c9d2-152">时间线</span><span class="sxs-lookup"><span data-stu-id="6c9d2-152">Timeline</span></span>** | <span data-ttu-id="6c9d2-153">在此处暂停和启动动画，或跳转到动画中的特定点。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-153">Pause and start an animation from here, or jump to a specific point in the animation.</span></span> |  
| <span data-ttu-id="6c9d2-154">第</span><span class="sxs-lookup"><span data-stu-id="6c9d2-154">4</span></span> | **<span data-ttu-id="6c9d2-155">详细信息</span><span class="sxs-lookup"><span data-stu-id="6c9d2-155">Details</span></span>** | <span data-ttu-id="6c9d2-156">检查和修改当前所选的动画组。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-156">Inspect and modify the currently selected Animation Group.</span></span> |  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png" alt-text="带批注的动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png":::
   <span data-ttu-id="6c9d2-158">带批注的动画检查器</span><span class="sxs-lookup"><span data-stu-id="6c9d2-158">Annotated Animation Inspector</span></span>  
:::image-end:::  

<span data-ttu-id="6c9d2-159">若要捕获动画，只需在动画检查器打开的情况下执行触发动画的交互。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-159">To capture an animation, just perform the interaction that triggers the animation while the Animation Inspector is open.</span></span>  <span data-ttu-id="6c9d2-160">如果动画是在页面加载时触发的，请使用动画检查器打开来重新加载页面以检测动画。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-160">If an animation is triggered on page load, reload the page with the Animation Inspector open to detect the animation.</span></span>  

<!--  old link: <video src="animations/capture-animations.mp4" autoplay loop muted controls></video>  -->  

<!--  import the video to ACOM using https://review.docs.microsoft.com/en-us/help/contribute/contribute-video-publish?branch=master  -->  

<!--  > [!VIDEO animations/capture-animations.mp4]  -->  

## <span data-ttu-id="6c9d2-161">检查动画</span><span class="sxs-lookup"><span data-stu-id="6c9d2-161">Inspect animations</span></span>   

<span data-ttu-id="6c9d2-162">捕获动画后，有几种方法可以重播它：</span><span class="sxs-lookup"><span data-stu-id="6c9d2-162">After you capture an animation, there are a few ways to replay it:</span></span>  

*   <span data-ttu-id="6c9d2-163">将鼠标悬停在 " **概述** " 窗格的缩略图上以查看它的预览。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-163">Hover over the thumbnail in the **Overview** pane to view a preview of it.</span></span>  
*   <span data-ttu-id="6c9d2-164">从 " **概述** " 窗格中选择 "动画" 组 \ (，使其显示在 " **详细信息** " 窗格 \ ) 中，然后按 " **重播** \ (![ 重播" 图标 ][ImageReplayButtonIcon] \ ) 图标。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-164">Select the Animation Group from the **Overview** pane \(so that it is displayed in the **Details** pane\) and press the **replay** \(![replay icon][ImageReplayButtonIcon]\) icon.</span></span>  <span data-ttu-id="6c9d2-165">将在视区中重播动画。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-165">The animation is replayed in the viewport.</span></span>  <span data-ttu-id="6c9d2-166">单击 " **动画速度** " (![ 动画速度图标 ][ImageAnimationSpeedButtonsIcon] \ ) 图标，以更改当前所选动画组的预览速度。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-166">Click on the **animation speed** \(![animation speed icons][ImageAnimationSpeedButtonsIcon]\) icons to change the preview speed of the currently selected Animation Group.</span></span>  <span data-ttu-id="6c9d2-167">您可以使用红色垂直条更改您的当前位置。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-167">You may use the red vertical bar to change your current position.</span></span>  
*   <span data-ttu-id="6c9d2-168">单击并拖动红色垂直条以擦除视区动画。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-168">Click and drag the red vertical bar to scrub the viewport animation.</span></span>  
    
### <span data-ttu-id="6c9d2-169">查看动画详细信息</span><span class="sxs-lookup"><span data-stu-id="6c9d2-169">View animation details</span></span>  

<span data-ttu-id="6c9d2-170">捕获动画组后，从 " **概述** " 窗格中单击它以查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-170">After you capture an Animation Group, click on it from the **Overview** pane to view the details.</span></span>  <span data-ttu-id="6c9d2-171">在 " **详细信息** " 窗格中，每个单独的动画都分配有一行。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-171">In the **Details** pane each individual animation is assigned the a row.</span></span>  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="动画组详细信息" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png":::
   <span data-ttu-id="6c9d2-173">动画组详细信息</span><span class="sxs-lookup"><span data-stu-id="6c9d2-173">Animation Group details</span></span>  
:::image-end:::  

<span data-ttu-id="6c9d2-174">将鼠标悬停在某个动画上，将其在视区中突出显示。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-174">Hover over an animation to highlight it in the viewport.</span></span>  <span data-ttu-id="6c9d2-175">单击动画以在 " **元素** " 面板中选择它。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-175">Click on the animation to select it in the **Elements** panel.</span></span>  

:::image type="complex" source="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="将鼠标悬停在动画上以在视区中突出显示" lightbox="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png":::
   <span data-ttu-id="6c9d2-177">将鼠标悬停在动画上以在视区中突出显示</span><span class="sxs-lookup"><span data-stu-id="6c9d2-177">Hover over the animation to highlight it in viewport</span></span>  
:::image-end:::  

<span data-ttu-id="6c9d2-178">动画最左边、更暗的部分是定义。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-178">The leftmost, darker section of an animation is the definition.</span></span>  <span data-ttu-id="6c9d2-179">右侧、更淡出的部分表示迭代。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-179">The right, more faded section represents iterations.</span></span>  <span data-ttu-id="6c9d2-180">例如，在下图中，第二部分和第三部分表示第一节的迭代。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-180">For example, in the following figure, sections two and three represent iterations of section one.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations-highlight.msft.png" alt-text="动画迭代图表" lightbox="../media/inspect-styles-glitch-display-animations-highlight.msft.png":::
   <span data-ttu-id="6c9d2-182">动画迭代图表</span><span class="sxs-lookup"><span data-stu-id="6c9d2-182">Diagram of animation iterations</span></span>  
:::image-end:::  

<span data-ttu-id="6c9d2-183">如果两个元素应用了相同的动画，则动画检查器会为元素分配相同的颜色。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-183">If two elements have the same animation applied, the Animation Inspector assigns the same color to the elements.</span></span>  <span data-ttu-id="6c9d2-184">颜色是随机的，没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-184">The color is random and has no significance.</span></span>  <span data-ttu-id="6c9d2-185">例如，下图中，这两个元素 `div.cwccw.earlier` `div.cwccw.later` 具有相同的动画 \ (`spinrightleft` \ ) 应用，就像执行 `div.ccwcw.earlier` 和元素一样 `div.ccwcw.later` 。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-185">For example, in the following figure, the two elements `div.cwccw.earlier` and `div.cwccw.later` have the same animation \(`spinrightleft`\) applied, as do the `div.ccwcw.earlier` and `div.ccwcw.later` elements.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations.msft.png" alt-text="颜色编码的动画" lightbox="../media/inspect-styles-glitch-display-animations.msft.png":::
   <span data-ttu-id="6c9d2-187">颜色编码的动画</span><span class="sxs-lookup"><span data-stu-id="6c9d2-187">Color-coded animations</span></span>  
:::image-end:::  

## <span data-ttu-id="6c9d2-188">修改动画</span><span class="sxs-lookup"><span data-stu-id="6c9d2-188">Modify animations</span></span>   

<span data-ttu-id="6c9d2-189">你可以通过三种方式使用动画检查器修改动画。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-189">There are three ways you are able to modify an animation with the Animation Inspector.</span></span>  

*   <span data-ttu-id="6c9d2-190">动画持续时间。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-190">Animation duration.</span></span>  
*   <span data-ttu-id="6c9d2-191">关键帧计时。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-191">Keyframe timings.</span></span>  
*   <span data-ttu-id="6c9d2-192">开始时间延迟。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-192">Start time delay.</span></span>  
    
<span data-ttu-id="6c9d2-193">在下图中，表示原始动画。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-193">In the following figure, the original animation is represented.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png" alt-text="修改前的原始动画" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png":::
   <span data-ttu-id="6c9d2-195">修改前的原始动画</span><span class="sxs-lookup"><span data-stu-id="6c9d2-195">Original animation before modification</span></span>  
:::image-end:::  

<span data-ttu-id="6c9d2-196">若要更改动画的持续时间，请单击并拖动第一个或最后一个圆。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-196">To change the duration of an animation, click and drag the first or last circle.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png" alt-text="已修改工期" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png":::
   <span data-ttu-id="6c9d2-198">已修改工期</span><span class="sxs-lookup"><span data-stu-id="6c9d2-198">Modified duration</span></span>  
:::image-end:::  

<span data-ttu-id="6c9d2-199">如果动画定义了任何关键帧规则，则这些规则表示为白色内圆圈。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-199">If the animation defines any keyframe rules, then these are represented as white inner circles.</span></span>  <span data-ttu-id="6c9d2-200">单击并拖动其中一个以更改关键帧的计时。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-200">Click and drag one of these to change the timing of the keyframe.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png" alt-text="修改的关键帧" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png":::
   <span data-ttu-id="6c9d2-202">修改的关键帧</span><span class="sxs-lookup"><span data-stu-id="6c9d2-202">Modified keyframe</span></span>  
:::image-end:::  

<span data-ttu-id="6c9d2-203">若要向动画添加延迟，请单击并将其拖动到除圆圈外的任意位置。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-203">To add a delay to an animation, click and drag it anywhere except the circles.</span></span>  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png" alt-text="修改后的延迟" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png":::
   <span data-ttu-id="6c9d2-205">修改后的延迟</span><span class="sxs-lookup"><span data-stu-id="6c9d2-205">Modified delay</span></span>  
:::image-end:::  

<!--  
  


-->  

<!-- image links -->  

[ImageAnimationSpeedButtonsIcon]: ../media/animation-speed-buttons-icon.msft.png  
[ImageReplayButtonIcon]: ../media/replay-button-icon.msft.png  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="6c9d2-206">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-206">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6c9d2-207">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-207">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="6c9d2-209">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="6c9d2-209">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
