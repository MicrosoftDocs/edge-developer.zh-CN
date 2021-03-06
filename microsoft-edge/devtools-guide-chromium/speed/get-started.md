---
description: 了解如何使用 Microsoft Edge DevTools 查找使网站加载速度更快的方法。
title: 使用 Microsoft Edge DevTools 优化网站速度
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 7de97ab27528e89e2373e0a0d1002e8c86e37613
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398110"
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

# <a name="optimize-website-speed-with-microsoft-edge-devtools"></a><span data-ttu-id="feec3-104">使用 Microsoft Edge DevTools 优化网站速度</span><span class="sxs-lookup"><span data-stu-id="feec3-104">Optimize website speed with Microsoft Edge DevTools</span></span>  

## <a name="goal-of-tutorial"></a><span data-ttu-id="feec3-105">教程的目标</span><span class="sxs-lookup"><span data-stu-id="feec3-105">Goal of tutorial</span></span>  

<span data-ttu-id="feec3-106">本教程指导你如何使用 Microsoft Edge DevTools 查找使网站加载速度更快的方法。</span><span class="sxs-lookup"><span data-stu-id="feec3-106">This tutorial teaches you how to use Microsoft Edge DevTools to find ways to make your websites load faster.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="feec3-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="feec3-107">Prerequisites</span></span>  

*   <span data-ttu-id="feec3-108">你应该具有基本的 Web 开发体验，类似于本"Web 开发简介" [类中介绍的内容][CourseraIntroductionWebDevelopmentClass]。</span><span class="sxs-lookup"><span data-stu-id="feec3-108">You should have basic web development experience, similar to what is taught in this [Introduction to Web Development class][CourseraIntroductionWebDevelopmentClass].</span></span>  
*   <span data-ttu-id="feec3-109">无需了解有关加载性能的一切信息。</span><span class="sxs-lookup"><span data-stu-id="feec3-109">You do not need to know anything about load performance.</span></span>  <span data-ttu-id="feec3-110">你将在本教程中了解它。</span><span class="sxs-lookup"><span data-stu-id="feec3-110">You learn about it in this tutorial.</span></span>  

## <a name="introduction"></a><span data-ttu-id="feec3-111">简介</span><span class="sxs-lookup"><span data-stu-id="feec3-111">Introduction</span></span>  

<span data-ttu-id="feec3-112">这是 Tony。</span><span class="sxs-lookup"><span data-stu-id="feec3-112">This is Tony.</span></span>  <span data-ttu-id="feec3-113">Tony 在 cat 2016 中非常有名气。</span><span class="sxs-lookup"><span data-stu-id="feec3-113">Tony is very famous in cat society.</span></span>  <span data-ttu-id="feec3-114">他构建了一个网站，以便他的粉丝能够了解他最喜爱的粉丝。</span><span class="sxs-lookup"><span data-stu-id="feec3-114">He has built a website so that his fans are able to learn about his favorite foods.</span></span>  <span data-ttu-id="feec3-115">他的粉丝喜欢该网站，但 Tony 不断听到有关网站加载缓慢的抱怨。</span><span class="sxs-lookup"><span data-stu-id="feec3-115">His fans love the site, but Tony keeps hearing complaints that the site loads slowly.</span></span>  <span data-ttu-id="feec3-116">Tony 已要求你帮助他加快网站速度。</span><span class="sxs-lookup"><span data-stu-id="feec3-116">Tony has asked you to help him speed the site up.</span></span>  

:::image type="complex" source="../media/speed-tony.msft.png" alt-text="Tony the cat" lightbox="../media/speed-tony.msft.png":::
   <span data-ttu-id="feec3-118">Tony the cat</span><span class="sxs-lookup"><span data-stu-id="feec3-118">Tony the cat</span></span>  
:::image-end:::  

## <a name="step-1-audit-the-site"></a><span data-ttu-id="feec3-119">步骤 1：审核网站</span><span class="sxs-lookup"><span data-stu-id="feec3-119">Step 1: Audit the site</span></span>  

<span data-ttu-id="feec3-120">无论何时开始提高网站的加载性能，始终从 **审核开始**。</span><span class="sxs-lookup"><span data-stu-id="feec3-120">Whenever you set out to improve the load performance of a site, **always start with an audit**.</span></span>  
<span data-ttu-id="feec3-121">审核有两项重要功能：</span><span class="sxs-lookup"><span data-stu-id="feec3-121">The audit has 2 important functions:</span></span>  

*   <span data-ttu-id="feec3-122">它创建一 **个基线** ，用于度量后续更改。</span><span class="sxs-lookup"><span data-stu-id="feec3-122">It creates a **baseline** for you to measure subsequent changes against.</span></span>  
*   <span data-ttu-id="feec3-123">它为你提供 **了有关哪些** 更改影响最大的可操作提示。</span><span class="sxs-lookup"><span data-stu-id="feec3-123">It gives you **actionable tips** on what changes have the most impact.</span></span>  
    
### <a name="set-up"></a><span data-ttu-id="feec3-124">设置</span><span class="sxs-lookup"><span data-stu-id="feec3-124">Set up</span></span>  

<span data-ttu-id="feec3-125">首先，必须设置网站，以便以后能够进行更改。</span><span class="sxs-lookup"><span data-stu-id="feec3-125">First, you must set up the site so that you are able to make changes to it later.</span></span>  

1.  <span data-ttu-id="feec3-126">[打开网站的源代码](https://glitch.com/edit/#!/tony)。</span><span class="sxs-lookup"><span data-stu-id="feec3-126">[Open the source code for the site](https://glitch.com/edit/#!/tony).</span></span>  <span data-ttu-id="feec3-127">此选项卡称为编辑器 **选项卡**。</span><span class="sxs-lookup"><span data-stu-id="feec3-127">This tab is referred to as the **editor tab**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js.msft.png" alt-text="编辑器选项卡" lightbox="../media/speed-glitch-tony-server-js.msft.png":::
       <span data-ttu-id="feec3-129">编辑器 **选项卡**</span><span class="sxs-lookup"><span data-stu-id="feec3-129">The **editor tab**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-130">选择 **tony**。</span><span class="sxs-lookup"><span data-stu-id="feec3-130">Choose **tony**.</span></span>  <span data-ttu-id="feec3-131">将出现一个菜单。</span><span class="sxs-lookup"><span data-stu-id="feec3-131">A menu appears.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js-remix-project.msft.png" alt-text="选择 tony 后出现的菜单" lightbox="../media/speed-glitch-tony-server-js-remix-project.msft.png":::
       <span data-ttu-id="feec3-133">选择 tony 后出现的 **菜单**</span><span class="sxs-lookup"><span data-stu-id="feec3-133">The menu that appears after choosing **tony**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-134">选择 **"重新混合项目"。**</span><span class="sxs-lookup"><span data-stu-id="feec3-134">Choose **Remix Project**.</span></span>  <span data-ttu-id="feec3-135">项目名称从 **tony** 更改为一些随机生成的名称。</span><span class="sxs-lookup"><span data-stu-id="feec3-135">The name of the project changes from **tony** to some randomly-generated name.</span></span>  <span data-ttu-id="feec3-136">现在，您具有自己的代码可编辑副本。</span><span class="sxs-lookup"><span data-stu-id="feec3-136">You now have your own editable copy of the code.</span></span>  <span data-ttu-id="feec3-137">稍后，您可以对此代码进行更改。</span><span class="sxs-lookup"><span data-stu-id="feec3-137">Later on, you may make changes to this code.</span></span>  
1.  <span data-ttu-id="feec3-138">选择 **"显示**"，然后选择 **"新建窗口"。**</span><span class="sxs-lookup"><span data-stu-id="feec3-138">Choose **Show** and choose **In a New Window**.</span></span>  <span data-ttu-id="feec3-139">将在新选项卡中打开演示。 此选项卡称为演示 **选项卡**。 加载网站可能需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="feec3-139">The demo opens in a new tab.  This tab is be referred to as the **demo tab**.  It may take a while for the site to load.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live.msft.png" alt-text="演示选项卡" lightbox="../media/speed-glitch-tony-show-live.msft.png":::
       <span data-ttu-id="feec3-141">演示选项卡</span><span class="sxs-lookup"><span data-stu-id="feec3-141">The demo tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-142">选择 `Control` + `Shift` + `J` \ (Windows、Linux\) `Command` + `Option` + `J` 或 \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="feec3-142">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="feec3-143">Microsoft Edge DevTools 将在演示旁边打开。</span><span class="sxs-lookup"><span data-stu-id="feec3-143">Microsoft Edge DevTools opens up alongside the demo.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live-console.msft.png" alt-text="DevTools 和演示" lightbox="../media/speed-glitch-tony-show-live-console.msft.png":::
       <span data-ttu-id="feec3-145">DevTools 和演示</span><span class="sxs-lookup"><span data-stu-id="feec3-145">DevTools and the demo</span></span>  
    :::image-end:::  
    
<span data-ttu-id="feec3-146">对于本教程中的其余屏幕截图，DevTools 显示在单独的窗口中。</span><span class="sxs-lookup"><span data-stu-id="feec3-146">For the rest of the screenshots in this tutorial, DevTools is shown in a separate window.</span></span>  <span data-ttu-id="feec3-147">Select `Control` + `Shift` + `P` \ (Windows， Linux\) or `Command` + `Shift` + `P` \ (macOS\) to open the Command Menu， `Undock` typing， and then selecting **Undock into separate window**.</span><span class="sxs-lookup"><span data-stu-id="feec3-147">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, typing `Undock`, and then selecting **Undock into separate window**.</span></span>  

:::image type="complex" source="../media/speed-console.msft.png" alt-text="已取消停靠的 DevTools" lightbox="../media/speed-console.msft.png":::
   <span data-ttu-id="feec3-149">已取消停靠的 DevTools</span><span class="sxs-lookup"><span data-stu-id="feec3-149">Undocked DevTools</span></span>  
:::image-end:::  

### <a name="establish-a-baseline"></a><span data-ttu-id="feec3-150">建立基线</span><span class="sxs-lookup"><span data-stu-id="feec3-150">Establish a baseline</span></span>  

<span data-ttu-id="feec3-151">基线是网站在做出任何性能改进之前如何执行的记录。</span><span class="sxs-lookup"><span data-stu-id="feec3-151">The baseline is a record of how the site performed before you made any performance improvements.</span></span>  

1.  <span data-ttu-id="feec3-152">选择 **"审核"** 工具。</span><span class="sxs-lookup"><span data-stu-id="feec3-152">Choose the **Audits** tool.</span></span>  <span data-ttu-id="feec3-153">It may be hidden behind the **More Panels** \(![More Panels][ImageMorePanelsIcon]\) button.</span><span class="sxs-lookup"><span data-stu-id="feec3-153">It may be hidden behind the **More Panels** \(![More Panels][ImageMorePanelsIcon]\) button.</span></span>  <span data-ttu-id="feec3-154">此面板上有一个 Lighthouse，因为支持审核面板的项目名为**Lighthouse。**</span><span class="sxs-lookup"><span data-stu-id="feec3-154">There is a Lighthouse on this panel because the project that powers the Audits panel is named **Lighthouse**.</span></span>  
    
    [!INCLUDE [audits-panel-note](../includes/audits-panel-note.md)]  
    
    :::image type="complex" source="../media/speed-audits-performance.msft.png" alt-text="审核工具" lightbox="../media/speed-audits-performance.msft.png":::
       <span data-ttu-id="feec3-156">**审核**工具</span><span class="sxs-lookup"><span data-stu-id="feec3-156">The **Audits** tool</span></span>  
    :::image-end:::  
    
    <!--todo: add link to Lighthouse when section is available  -->  
    <!-- /web/tools/lighthouse  -->  
    
1.  <span data-ttu-id="feec3-157">将审核配置设置与上图中的设置相匹配。</span><span class="sxs-lookup"><span data-stu-id="feec3-157">Match your audit configuration settings to those in the previous figure.</span></span>  <span data-ttu-id="feec3-158">下面是不同选项的说明：</span><span class="sxs-lookup"><span data-stu-id="feec3-158">Here is an explanation of the different options:</span></span>  
    
    *   <span data-ttu-id="feec3-159">**设备**。</span><span class="sxs-lookup"><span data-stu-id="feec3-159">**Device**.</span></span>  <span data-ttu-id="feec3-160">设置为 **"移动** "将更改用户代理字符串并模拟移动视口。</span><span class="sxs-lookup"><span data-stu-id="feec3-160">Set to **Mobile** changes the user agent string and simulates a mobile viewport.</span></span>  <span data-ttu-id="feec3-161">设置为 **桌面** 几乎只是关闭 **移动** 版更改。</span><span class="sxs-lookup"><span data-stu-id="feec3-161">Set to **Desktop** pretty much just turns off the **Mobile** changes.</span></span>  
    *   <span data-ttu-id="feec3-162">**审核**。</span><span class="sxs-lookup"><span data-stu-id="feec3-162">**Audits**.</span></span>  <span data-ttu-id="feec3-163">关闭类别以防止审核面板运行这些\*\*\*\* 审核，并排除报告中的这些审核。</span><span class="sxs-lookup"><span data-stu-id="feec3-163">Turn off a category to prevent the **Audits** panel from running those audits, and excludes those audits from your report.</span></span>  <span data-ttu-id="feec3-164">如果要显示提供的建议类型，请保持其他类别为"打开"。</span><span class="sxs-lookup"><span data-stu-id="feec3-164">Leave the other categories Turned on, if you want to display the types of recommendations that are provided.</span></span>  <span data-ttu-id="feec3-165">关闭类别可稍微加快审核过程。</span><span class="sxs-lookup"><span data-stu-id="feec3-165">Turn off categories to slightly speed up the auditing process.</span></span>  
    *   <span data-ttu-id="feec3-166">**限制**。</span><span class="sxs-lookup"><span data-stu-id="feec3-166">**Throttling**.</span></span>  <span data-ttu-id="feec3-167">设置为 **模拟慢速 4G 时，4 倍 CPU 速度会** 模拟在移动设备上浏览的典型条件。</span><span class="sxs-lookup"><span data-stu-id="feec3-167">Set to **Simulated Slow 4G, 4x CPU Slowdown** simulates the typical conditions of browsing on a mobile device.</span></span>  <span data-ttu-id="feec3-168">它命名为"模拟"，因为审核面板在审核过程中实际上不会限制。</span><span class="sxs-lookup"><span data-stu-id="feec3-168">It is named "simulated" because the Audits panel does not actually throttle during the auditing process.</span></span>  <span data-ttu-id="feec3-169">相反，它只是推断页面在移动条件下加载所花的时间。</span><span class="sxs-lookup"><span data-stu-id="feec3-169">Instead, it just extrapolates how long the page takes to load under mobile conditions.</span></span>  <span data-ttu-id="feec3-170">另 **一** 方面，应用... 设置实际上会限制 CPU 和网络，同时权衡较长的审核过程。</span><span class="sxs-lookup"><span data-stu-id="feec3-170">The **Applied...** setting, on the other hand, actually throttles your CPU and network, with the tradeoff of a longer auditing process.</span></span>  
    *   <span data-ttu-id="feec3-171">**清除存储**。</span><span class="sxs-lookup"><span data-stu-id="feec3-171">**Clear Storage**.</span></span>  <span data-ttu-id="feec3-172">启用复选框，以在每次审核之前清除与页面关联的所有存储。</span><span class="sxs-lookup"><span data-stu-id="feec3-172">Turn on the checkbox to clear all storage associated with the page before every audit.</span></span>  <span data-ttu-id="feec3-173">如果要审核首次访问者对网站的体验，请保留此设置。</span><span class="sxs-lookup"><span data-stu-id="feec3-173">Leave this setting on if you want to audit how first-time visitors experience your site.</span></span>  <span data-ttu-id="feec3-174">在需要重复访问体验时关闭此设置。</span><span class="sxs-lookup"><span data-stu-id="feec3-174">Turn off this setting when you want the repeat-visit experience.</span></span>  
    
1.  <span data-ttu-id="feec3-175">选择 **"运行审核"。**</span><span class="sxs-lookup"><span data-stu-id="feec3-175">Choose **Run Audits**.</span></span>  <span data-ttu-id="feec3-176">10 到 30 秒后\*\*\*\*，审核面板将显示网站性能报告。</span><span class="sxs-lookup"><span data-stu-id="feec3-176">After 10 to 30 seconds, the **Audits** panel displays a report of the performance of the site.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png" alt-text="网站性能的审核面板报告" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png":::
       <span data-ttu-id="feec3-178">网站性能的审核面板报告</span><span class="sxs-lookup"><span data-stu-id="feec3-178">The report for the Audits panel of the performance of the site</span></span>  
    :::image-end:::  
    
#### <a name="handling-report-errors"></a><span data-ttu-id="feec3-179">处理报告错误</span><span class="sxs-lookup"><span data-stu-id="feec3-179">Handling report errors</span></span>  

<span data-ttu-id="feec3-180">如果在审核面板报告中收到错误，请尝试在未打开任何其他选项卡的 **InPrivate** 窗口中运行演示选项卡。</span><span class="sxs-lookup"><span data-stu-id="feec3-180">If you ever get an error in your Audits panel report, try running the demo tab from an **InPrivate** window with no other tabs open.</span></span>  <span data-ttu-id="feec3-181">这可确保你从干净状态运行 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="feec3-181">This ensures that you are running Microsoft Edge from a clean state.</span></span>  <span data-ttu-id="feec3-182">尤其是 Microsoft Edge 扩展通常干扰审核过程。</span><span class="sxs-lookup"><span data-stu-id="feec3-182">Microsoft Edge Extensions in particular often interfere with the auditing process.</span></span>  

<!--todo: add screen capture for error in audit -->  
<!--
:::image type="complex" source="../media/speed-.msft.png" alt-text="A report that errored" lightbox="../media/speed-.msft.png":::
   A report that errored  
:::image-end:::  
-->  

### <a name="understand-your-report"></a><span data-ttu-id="feec3-183">了解报告</span><span class="sxs-lookup"><span data-stu-id="feec3-183">Understand your report</span></span>  

<span data-ttu-id="feec3-184">报告顶部的数字是网站的总体性能分数。</span><span class="sxs-lookup"><span data-stu-id="feec3-184">The number at the top of your report is the overall performance score for the site.</span></span>  <span data-ttu-id="feec3-185">稍后，当您对代码进行更改时，显示的数量应该会上升。</span><span class="sxs-lookup"><span data-stu-id="feec3-185">Later, as you make changes to the code, the number displayed should rise.</span></span>  <span data-ttu-id="feec3-186">分数越高表示性能越好。</span><span class="sxs-lookup"><span data-stu-id="feec3-186">A higher score means better performance.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png" alt-text="总体性能分数" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png":::
   <span data-ttu-id="feec3-188">总体性能分数</span><span class="sxs-lookup"><span data-stu-id="feec3-188">The overall performance score</span></span>  
:::image-end:::  

<span data-ttu-id="feec3-189">" **指标** "部分提供网站性能的量度度量。</span><span class="sxs-lookup"><span data-stu-id="feec3-189">The **Metrics** section provides quantitative measurements of the performance of the site.</span></span>  <span data-ttu-id="feec3-190">每个指标提供对性能不同方面的见解。</span><span class="sxs-lookup"><span data-stu-id="feec3-190">Each metric provides insight into a different aspect of the performance.</span></span>  <span data-ttu-id="feec3-191">例如，"\*\*\*\* 第一个内容绘制"会告知你首次将内容绘制到屏幕的时间，这是用户对页面加载的感知中的一个重要里程碑，而"时间到\*\*\*\* 交互"标记页面显示为足以处理用户交互的点。</span><span class="sxs-lookup"><span data-stu-id="feec3-191">For example, **First Contentful Paint** tells you when content is first painted to the screen, which is an important milestone in the user's perception of the page load, whereas **Time To Interactive** marks the point at which the page appears ready enough to handle user interactions.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png" alt-text=""指标"部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png":::
   <span data-ttu-id="feec3-193">" **指标"** 部分</span><span class="sxs-lookup"><span data-stu-id="feec3-193">The **Metrics** section</span></span>  
:::image-end:::  

<span data-ttu-id="feec3-194">选择下图中突出显示的切换按钮以显示每个指标的说明，然后选择"了解更多 **"来阅读** 有关它的文档。</span><span class="sxs-lookup"><span data-stu-id="feec3-194">Choose the highlighted toggle button in the following figure to display a description for each metric, and choose **Learn More** to read documentation about it.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png" alt-text="选择突出显示的切换按钮以展开指标项" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png":::
   <span data-ttu-id="feec3-196">选择突出显示的切换按钮以展开指标项</span><span class="sxs-lookup"><span data-stu-id="feec3-196">Choose the highlighted toggle button to expand the Metrics items</span></span>  
:::image-end:::  

<span data-ttu-id="feec3-197">下面的指标是显示页面加载时的外观的屏幕截图集合。</span><span class="sxs-lookup"><span data-stu-id="feec3-197">Below Metrics is a collection of screenshots that show you how the page looked as it loaded.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="页面在加载时的外观的屏幕截图" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   <span data-ttu-id="feec3-199">页面在加载时的外观的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="feec3-199">Screenshots of how the page looked while loading</span></span>  
:::image-end:::  

<span data-ttu-id="feec3-200">" **机会** "部分提供了有关如何提高此特定页面的加载性能的特定提示。</span><span class="sxs-lookup"><span data-stu-id="feec3-200">The **Opportunities** section provides specific tips on how to improve the load performance of this specific page.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text=""机会"部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   <span data-ttu-id="feec3-202">" **机会"** 部分</span><span class="sxs-lookup"><span data-stu-id="feec3-202">The **Opportunities** section</span></span>  
:::image-end:::  

<span data-ttu-id="feec3-203">选择一个了解它更多信息的机会。</span><span class="sxs-lookup"><span data-stu-id="feec3-203">Choose an opportunity to learn more about it.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png" alt-text="消除呈现阻止资源机会" lightbox="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png":::
   <span data-ttu-id="feec3-205">**消除呈现阻止资源** 的机会</span><span class="sxs-lookup"><span data-stu-id="feec3-205">**Eliminate render-blocking resources** opportunity</span></span>  
:::image-end:::  

<span data-ttu-id="feec3-206">Choose **Learn More** to display documentation about why an opportunity is important， and specific recommendations on how to fix it.</span><span class="sxs-lookup"><span data-stu-id="feec3-206">Choose **Learn More** to display documentation about why an opportunity is important, and specific recommendations on how to fix it.</span></span>  

:::image type="complex" source="../media/speed-web-dev-performance-audits.msft.png" alt-text="有关消除呈现阻止资源机会的文档" lightbox="../media/speed-web-dev-performance-audits.msft.png":::
   <span data-ttu-id="feec3-208">有关消除 **呈现阻止资源机会** 的文档</span><span class="sxs-lookup"><span data-stu-id="feec3-208">Documentation for the **Eliminate render-blocking resources** opportunity</span></span>  
:::image-end:::  

<span data-ttu-id="feec3-209">" **诊断"** 部分提供了有关影响页面加载时间的因素详细信息。</span><span class="sxs-lookup"><span data-stu-id="feec3-209">The **Diagnostics** section provides more information about factors that contribute to the load time of the page.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png" alt-text=""诊断"部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png":::
   <span data-ttu-id="feec3-211">" **诊断"** 部分</span><span class="sxs-lookup"><span data-stu-id="feec3-211">The **Diagnostics** section</span></span>  
:::image-end:::  

<span data-ttu-id="feec3-212">" **通过审核"** 部分显示网站正在正确执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="feec3-212">The **Passed Audits** section shows you what the site is doing correctly.</span></span>  <span data-ttu-id="feec3-213">选择展开该部分。</span><span class="sxs-lookup"><span data-stu-id="feec3-213">Choose to expand the section.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png" alt-text=""通过审核"部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png":::
   <span data-ttu-id="feec3-215">" **通过审核"** 部分</span><span class="sxs-lookup"><span data-stu-id="feec3-215">The **Passed Audits** section</span></span>  
:::image-end:::  

## <a name="step-2-experiment"></a><span data-ttu-id="feec3-216">步骤 2：试验</span><span class="sxs-lookup"><span data-stu-id="feec3-216">Step 2: Experiment</span></span>  

<span data-ttu-id="feec3-217">审核报告的"机会"部分提供了有关如何提高页面性能的提示。</span><span class="sxs-lookup"><span data-stu-id="feec3-217">The Opportunities section of your audit report gives you tips on how to improve the performance of the page.</span></span>  <span data-ttu-id="feec3-218">在此部分中，您将实现对代码库的建议更改，每次更改后审核网站，以测量更改对网站速度的影响。</span><span class="sxs-lookup"><span data-stu-id="feec3-218">In this section, you implement the recommended changes to the codebase, auditing the site after each change to measure how it affects site speed.</span></span>  

### <a name="enable-text-compression"></a><span data-ttu-id="feec3-219">启用文本压缩</span><span class="sxs-lookup"><span data-stu-id="feec3-219">Enable text compression</span></span>  

<span data-ttu-id="feec3-220">你的报告显示，避免大量网络负载是提升页面性能的一个最大机会。</span><span class="sxs-lookup"><span data-stu-id="feec3-220">Your report says that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="feec3-221">启用文本压缩是提高页面性能的机会。</span><span class="sxs-lookup"><span data-stu-id="feec3-221">Enabling text compression is an opportunity to improve the performance of the page.</span></span>  

<span data-ttu-id="feec3-222">文本压缩是在通过网络发送文本文件之前减小或压缩它的大小时。</span><span class="sxs-lookup"><span data-stu-id="feec3-222">Text compression is when you reduce, or compress, the size of a text file before sending it over the network.</span></span>  <span data-ttu-id="feec3-223">类似于在发送目录之前存档目录以减少大小的方式。</span><span class="sxs-lookup"><span data-stu-id="feec3-223">Similar to how you may archive a directory before sending it to reduce the size.</span></span>  

<span data-ttu-id="feec3-224">在启用压缩之前，有两种方法可以手动检查文本资源是否压缩。</span><span class="sxs-lookup"><span data-stu-id="feec3-224">Before you enable compression, here are a couple of ways to manually check whether text resources are compressed.</span></span>  

1.  <span data-ttu-id="feec3-225">选择 **"网络"** 工具。</span><span class="sxs-lookup"><span data-stu-id="feec3-225">Choose the **Network** tool.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network.msft.png" alt-text="“网络”面板" lightbox="../media/speed-glitch-tony-remix-network.msft.png":::
       <span data-ttu-id="feec3-227">网络**工具**</span><span class="sxs-lookup"><span data-stu-id="feec3-227">The **Network** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-228">选择 **"网络"设置** 图标。</span><span class="sxs-lookup"><span data-stu-id="feec3-228">Choose the **Network setting** icon.</span></span>  
1.  <span data-ttu-id="feec3-229">选中" **使用大型请求行"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="feec3-229">Choose the **Use Large Request Rows** checkbox.</span></span>  <span data-ttu-id="feec3-230">网络请求表中行的高度增加。</span><span class="sxs-lookup"><span data-stu-id="feec3-230">The height of the rows in the table of network requests increases.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png" alt-text="网络请求表中的大型行" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png":::
       <span data-ttu-id="feec3-232">网络请求表中的大型行</span><span class="sxs-lookup"><span data-stu-id="feec3-232">Large rows in the network requests table</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-233">如果未 **显示** 网络请求表中的"大小"列，请选择"大小"> **表标题**。</span><span class="sxs-lookup"><span data-stu-id="feec3-233">If the **Size** column in the table of network requests is not displayed, choose the table header > **Size**.</span></span>  

<span data-ttu-id="feec3-234">每个 **Size** 单元格显示两个值。</span><span class="sxs-lookup"><span data-stu-id="feec3-234">Each **Size** cell shows two values.</span></span>  <span data-ttu-id="feec3-235">顶部值是已下载资源的大小。</span><span class="sxs-lookup"><span data-stu-id="feec3-235">The top value is the size of the downloaded resource.</span></span>  
<span data-ttu-id="feec3-236">底部值是未压缩资源的大小。</span><span class="sxs-lookup"><span data-stu-id="feec3-236">The bottom value is the size of the uncompressed resource.</span></span>  <span data-ttu-id="feec3-237">如果两个值相同，则当通过网络发送资源时，不会压缩资源。</span><span class="sxs-lookup"><span data-stu-id="feec3-237">If the two values are the same, then the resource is not being compressed when it is sent over the network.</span></span>  <span data-ttu-id="feec3-238">例如，在上图中，其顶部和底部值为 `bundle.js` `1.2 MB` `1.2 MB` and。</span><span class="sxs-lookup"><span data-stu-id="feec3-238">For example, in the previous figure, the top and bottom values for `bundle.js` are `1.2 MB` and `1.2 MB`.</span></span>  

<span data-ttu-id="feec3-239">通过检查资源的 HTTP 标头检查压缩：</span><span class="sxs-lookup"><span data-stu-id="feec3-239">Check for compression by inspecting the HTTP headers of a resource:</span></span>  

1.  <span data-ttu-id="feec3-240">选择 `bundle.js` 。</span><span class="sxs-lookup"><span data-stu-id="feec3-240">Choose `bundle.js`.</span></span>  
1.  <span data-ttu-id="feec3-241">选择 **"标题"** 面板。</span><span class="sxs-lookup"><span data-stu-id="feec3-241">Choose the **Headers** panel.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png" alt-text=""标题"面板" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png":::
       <span data-ttu-id="feec3-243">" **标题"** 面板</span><span class="sxs-lookup"><span data-stu-id="feec3-243">The **Headers** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-244">在 **"响应标头"** 部分搜索 `content-encoding` 标头。</span><span class="sxs-lookup"><span data-stu-id="feec3-244">Search the **Response Headers** section for a `content-encoding` header.</span></span>  <span data-ttu-id="feec3-245">不显示 `content-encoding` 标题，这意味着 `bundle.js` 未压缩。</span><span class="sxs-lookup"><span data-stu-id="feec3-245">A `content-encoding` heading is not displayed, meaning that `bundle.js` was not compressed.</span></span>  <span data-ttu-id="feec3-246">压缩资源时，此标头通常设置为 `gzip` ， `deflate` 或 `br` 。</span><span class="sxs-lookup"><span data-stu-id="feec3-246">When a resource is compressed, this header is usually set to `gzip`, `deflate`, or `br`.</span></span>  <span data-ttu-id="feec3-247">有关这些值的说明，请导航到["指令"。][MDNContentEncodingDirectives]</span><span class="sxs-lookup"><span data-stu-id="feec3-247">For an explanation of the values, navigate to [Directives][MDNContentEncodingDirectives].</span></span>  

<span data-ttu-id="feec3-248">与说明一起足够。</span><span class="sxs-lookup"><span data-stu-id="feec3-248">Enough with the explanations.</span></span>  <span data-ttu-id="feec3-249">进行一些更改的时间。</span><span class="sxs-lookup"><span data-stu-id="feec3-249">Time to make some changes.</span></span>  <span data-ttu-id="feec3-250">通过添加几行代码启用文本压缩：</span><span class="sxs-lookup"><span data-stu-id="feec3-250">Enable text compression by adding a couple of lines of code:</span></span>  

1.  <span data-ttu-id="feec3-251">在编辑器选项卡中 \*\* ，选择 \*\*server.js。</span><span class="sxs-lookup"><span data-stu-id="feec3-251">In the editor tab, choose **server.js**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js.msft.png" alt-text="编辑server.js" lightbox="../media/speed-glitch-tony-remix-server-js.msft.png":::
       <span data-ttu-id="feec3-253">编辑</span><span class="sxs-lookup"><span data-stu-id="feec3-253">Edit</span></span> `server.js`  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-254">将以下 \*\* 代码添加到 \*\*server.js。</span><span class="sxs-lookup"><span data-stu-id="feec3-254">Add the following code to **server.js**.</span></span>  <span data-ttu-id="feec3-255">请确保放在 `app.use(compression())` 之前 `app.use(express.static('build'))` 。</span><span class="sxs-lookup"><span data-stu-id="feec3-255">Make sure to put `app.use(compression())` before `app.use(express.static('build'))`.</span></span>  

    ```javascript
    const express = require('express');
    const app = express();
    const fs = require('fs');
    const compression = require('compression');

    app.use(compression());
    app.use(express.static('build'));
    
    const listener = app.listen(process.env.PORT || 1234, function () {
        console.log(`Listening on port ${listener.address().port}`);
    });
    ```  
    
    > [!NOTE]
    > <span data-ttu-id="feec3-256">通常，你必须通过类似内容安装程序包，但已 `compression` `npm i -S compression` 针对你完成此操作。</span><span class="sxs-lookup"><span data-stu-id="feec3-256">Usually, you have to install the `compression` package via something like `npm i -S compression`, but this has already been done for you.</span></span>  
    
1.  <span data-ttu-id="feec3-257">等待 Glitch 部署网站的新内部版本。</span><span class="sxs-lookup"><span data-stu-id="feec3-257">Wait for Glitch to deploy the new build of the site.</span></span>  <span data-ttu-id="feec3-258">工具旁边的奇特动画\*\*\*\* 意味着正在重建和重新部署网站。</span><span class="sxs-lookup"><span data-stu-id="feec3-258">The fancy animation next to **Tools** means that the site is getting rebuilt and redeployed.</span></span>  <span data-ttu-id="feec3-259">当工具旁边的动画消失 **时，更改** 已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="feec3-259">The change is ready when the animation next to **Tools** goes away.</span></span>  <span data-ttu-id="feec3-260">选择 **"显示** "， **然后再次选择"新建窗口** "。</span><span class="sxs-lookup"><span data-stu-id="feec3-260">Choose **Show** and choose **In a New Window** again.</span></span>  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js-edited.msft.png" alt-text="The animation that indicates that the site is getting built" lightbox="../media/speed-glitch-tony-remix-server-js-edited.msft.png":::
       The animation that indicates that the site is getting built  
    :::image-end:::  
    -->  
    
<span data-ttu-id="feec3-261">使用之前了解到的工作流手动检查压缩是否正常工作：</span><span class="sxs-lookup"><span data-stu-id="feec3-261">Use the workflows that you learned earlier to manually check that the compression is working:</span></span>  

1.  <span data-ttu-id="feec3-262">返回到演示选项卡并刷新页面。</span><span class="sxs-lookup"><span data-stu-id="feec3-262">Go back to the demo tab and refresh the page.</span></span>  <span data-ttu-id="feec3-263">" **大小** "列现在应显示 2 个不同的文本资源值，如 `bundle.js` 。</span><span class="sxs-lookup"><span data-stu-id="feec3-263">The **Size** column should now show 2 different values for text resources like `bundle.js`.</span></span>  <span data-ttu-id="feec3-264">在下面的图中，其顶部值为通过网络发送的文件的大小，而其底部值是未 `256 KB` `bundle.js` `1.2 MB` 压缩的文件大小。</span><span class="sxs-lookup"><span data-stu-id="feec3-264">In the figure after the following, the top value of `256 KB` for `bundle.js` is the size of the file that was sent over the network, and the bottom value of `1.2 MB` is the uncompressed file size.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-main.msft.png" alt-text=""大小"列现在显示文本资源的 2 个不同值" lightbox="../media/speed-glitch-tony-remix-network-main.msft.png":::
       <span data-ttu-id="feec3-266">" **大小** "列现在显示文本资源的 2 个不同值</span><span class="sxs-lookup"><span data-stu-id="feec3-266">The **Size** column now shows 2 different values for text resources</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-267">" **响应头"** 部分 `bundle.js` 现在应包含 `content-encoding: gzip` 标头。</span><span class="sxs-lookup"><span data-stu-id="feec3-267">The **Response Headers** section for `bundle.js` should now include a `content-encoding: gzip` header.</span></span>
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png" alt-text=""响应头"部分现在包含内容编码标头" lightbox="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png":::
       <span data-ttu-id="feec3-269">" **响应头"** 部分现在包含内容编码标头</span><span class="sxs-lookup"><span data-stu-id="feec3-269">The **Response Headers** section now contains a content-encoding header</span></span>  
    :::image-end:::  
    
<span data-ttu-id="feec3-270">再次审核页面以测量文本压缩对页面加载性能的影响类型：</span><span class="sxs-lookup"><span data-stu-id="feec3-270">Audit the page again to measure what kind of impact text compression has on the load performance of the page:</span></span>  

1.  <span data-ttu-id="feec3-271">选择 **"审核"** 工具。</span><span class="sxs-lookup"><span data-stu-id="feec3-271">Choose the **Audits** tool.</span></span>  
1.  <span data-ttu-id="feec3-272">Choose **Perform an audit** \ (Perform an audit ![ ][ImagePerformIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="feec3-272">Choose **Perform an audit** \(![Perform an audit][ImagePerformIcon]\).</span></span>  
1.  <span data-ttu-id="feec3-273">保持设置与以前相同。</span><span class="sxs-lookup"><span data-stu-id="feec3-273">Leave the settings the same as before.</span></span>  
1.  <span data-ttu-id="feec3-274">选择 **"运行审核"。**</span><span class="sxs-lookup"><span data-stu-id="feec3-274">Choose **Run audit**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png" alt-text="启用文本压缩后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png":::
       <span data-ttu-id="feec3-276">启用文本压缩后的审核报告</span><span class="sxs-lookup"><span data-stu-id="feec3-276">An Audits report after enabling text compression</span></span>  
    :::image-end:::  
    
<!--  Woohoo!  That looks like progress.  -->  <span data-ttu-id="feec3-277">总体性能分数应该已提高，这意味着网站的速度正在加快。</span><span class="sxs-lookup"><span data-stu-id="feec3-277">Your overall performance score should have increased, meaning that the site is getting faster.</span></span>  

#### <a name="text-compression-in-the-real-world"></a><span data-ttu-id="feec3-278">现实世界中的文本压缩</span><span class="sxs-lookup"><span data-stu-id="feec3-278">Text compression in the real world</span></span>  

<span data-ttu-id="feec3-279">大多数服务器确实具有如下所示的简单修补程序，用于启用压缩！</span><span class="sxs-lookup"><span data-stu-id="feec3-279">Most servers really do have simple fixes like this for enabling compression!</span></span>  <span data-ttu-id="feec3-280">只需搜索如何配置用于压缩文本的任何服务器。</span><span class="sxs-lookup"><span data-stu-id="feec3-280">Just do a search on how to configure whatever server you use to compress text.</span></span>  

### <a name="resize-images"></a><span data-ttu-id="feec3-281">调整图像大小</span><span class="sxs-lookup"><span data-stu-id="feec3-281">Resize images</span></span>  

<span data-ttu-id="feec3-282">你的报告表明，避免大量网络负载是提升页面性能的一个首要机会。</span><span class="sxs-lookup"><span data-stu-id="feec3-282">Your report indicates that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="feec3-283">调整图像大小有助于减小网络有效负载的大小。</span><span class="sxs-lookup"><span data-stu-id="feec3-283">Resizing images helps reduce the size of the network payload.</span></span>  <span data-ttu-id="feec3-284">如果用户在 500 像素宽的移动设备屏幕上查看图像，则发送 1500 像素宽的图像实际上没有意义。</span><span class="sxs-lookup"><span data-stu-id="feec3-284">If your user is viewing your images on a mobile device screen that is 500-pixels-wide, there is really no point in sending a 1500-pixel-wide image.</span></span>  <span data-ttu-id="feec3-285">理想情况下，最多发送 500 像素宽的图像。</span><span class="sxs-lookup"><span data-stu-id="feec3-285">Ideally, you send a 500-pixel-wide image, at most.</span></span>  

1.  <span data-ttu-id="feec3-286">在报告中，选择 **"避免大量网络负载"** 以显示应调整大小的图像。</span><span class="sxs-lookup"><span data-stu-id="feec3-286">In your report, choose **Avoid enormous network payloads** to display which images should be resized.</span></span>  <span data-ttu-id="feec3-287">看起来有 2 个 jpg 文件超过 2000 KB，大于必要。</span><span class="sxs-lookup"><span data-stu-id="feec3-287">It looks like 2 of the jpg files are over 2000 KB, which is bigger than necessary.</span></span>  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png" alt-text="Details about the properly size images opportunity" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png":::
       Details about the properly size images opportunity  
    :::image-end:::  
    -->
    
1.  <span data-ttu-id="feec3-288">返回到编辑器选项卡中，打开 `src/model.js` 。</span><span class="sxs-lookup"><span data-stu-id="feec3-288">Back in the editor tab, open `src/model.js`.</span></span>  
1.  <span data-ttu-id="feec3-289">用 `const dir = 'small'` 取代 `const dir = 'big'`。</span><span class="sxs-lookup"><span data-stu-id="feec3-289">Replace `const dir = 'big'` with `const dir = 'small'`.</span></span>  <span data-ttu-id="feec3-290">此目录包含已调整大小相同的图像的副本。</span><span class="sxs-lookup"><span data-stu-id="feec3-290">This directory contains copies of the same images which have been resized.</span></span>  
1.  <span data-ttu-id="feec3-291">再次审核页面以显示更改如何影响加载性能。</span><span class="sxs-lookup"><span data-stu-id="feec3-291">Audit the page again to display how the change affects load performance.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-compression-small-images-audits-performance.msft.png" alt-text="调整图像大小后的审核报告" lightbox="../media/speed-glitch-compression-small-images-audits-performance.msft.png":::
       <span data-ttu-id="feec3-293">调整图像大小后的审核报告</span><span class="sxs-lookup"><span data-stu-id="feec3-293">An Audits report after resizing images</span></span>  
    :::image-end:::  
    
<span data-ttu-id="feec3-294">更改显示仅对总体性能分数有轻微影响。</span><span class="sxs-lookup"><span data-stu-id="feec3-294">The change displays only has a minor affect on the overall performance score.</span></span>  <span data-ttu-id="feec3-295">但是，该分数未明确显示一点，即保存用户的网络数据数量。</span><span class="sxs-lookup"><span data-stu-id="feec3-295">However, one thing that the score does not show clearly is how much network data you are saving your users.</span></span>  <span data-ttu-id="feec3-296">旧照片的总大小约为 5.3 MB，但现在只有约 0.18 MB。</span><span class="sxs-lookup"><span data-stu-id="feec3-296">The total size of the old photos was around 5.3 megabytes, whereas now it is only about 0.18 megabytes.</span></span>  

#### <a name="resizing-images-in-the-real-world"></a><span data-ttu-id="feec3-297">在现实世界中调整图像大小</span><span class="sxs-lookup"><span data-stu-id="feec3-297">Resizing images in the real world</span></span>  

<span data-ttu-id="feec3-298">对于小型应用，执行一次一次大小调整可能足够好。</span><span class="sxs-lookup"><span data-stu-id="feec3-298">For a small app, doing a one-off resize like this may be good enough.</span></span>  <span data-ttu-id="feec3-299">但对于大型应用，这显然不可伸缩。</span><span class="sxs-lookup"><span data-stu-id="feec3-299">But for a large app, this obviously is not scalable.</span></span>  <span data-ttu-id="feec3-300">下面是用于管理大型应用中图像的一些策略：</span><span class="sxs-lookup"><span data-stu-id="feec3-300">Here are some strategies for managing images in large apps:</span></span>  

*   <span data-ttu-id="feec3-301">在生成过程中调整图像大小。</span><span class="sxs-lookup"><span data-stu-id="feec3-301">Resize images during your build process.</span></span>  
*   <span data-ttu-id="feec3-302">在生成过程中创建每个图像的多个大小，然后在 `srcset` 代码中使用。</span><span class="sxs-lookup"><span data-stu-id="feec3-302">Create multiple sizes of each image during the build process and then use `srcset` in your code.</span></span>  <span data-ttu-id="feec3-303">在运行时，浏览器负责选择最适合设备的大小。</span><span class="sxs-lookup"><span data-stu-id="feec3-303">At runtime, the browser takes care of choosing which size is best for the device.</span></span>  
    <!--Navigate to [Relative-sized images][relative].  -->
    
<!--[relative]: /web/fundamentals/design-and-ux/responsive/images#relative_sized_images  -->  

*   <span data-ttu-id="feec3-304">使用图像 CDN，可让你在请求图像时动态调整其大小。</span><span class="sxs-lookup"><span data-stu-id="feec3-304">Use an image CDN that lets you dynamically resize an image when you request it.</span></span>  
*   <span data-ttu-id="feec3-305">至少优化每个图像。</span><span class="sxs-lookup"><span data-stu-id="feec3-305">At the very least, optimize each image.</span></span>  <span data-ttu-id="feec3-306">这可能会导致大量节省。</span><span class="sxs-lookup"><span data-stu-id="feec3-306">This may create huge savings.</span></span>  
  <span data-ttu-id="feec3-307">优化是通过减少图像文件大小的特殊程序运行图像时。</span><span class="sxs-lookup"><span data-stu-id="feec3-307">Optimization is when you run an image through a special program that reduces the size of the image file.</span></span>  <span data-ttu-id="feec3-308">有关更多提示，请导航到["基本图像优化"。][EssentialImageOptimization]</span><span class="sxs-lookup"><span data-stu-id="feec3-308">For more tips, navigate to [Essential Image Optimization][EssentialImageOptimization].</span></span>  
    
### <a name="eliminate-render-blocking-resources"></a><span data-ttu-id="feec3-309">消除呈现阻止资源</span><span class="sxs-lookup"><span data-stu-id="feec3-309">Eliminate render-blocking resources</span></span>  

<span data-ttu-id="feec3-310">最新报告显示，消除呈现阻止资源现在是最大机会。</span><span class="sxs-lookup"><span data-stu-id="feec3-310">Your latest report says that eliminating render-blocking resources is now the biggest opportunity.</span></span>  

<span data-ttu-id="feec3-311">呈现阻止资源是一个外部 JavaScript 或 CSS 文件，浏览器必须在显示页面之前下载、分析和运行该文件。</span><span class="sxs-lookup"><span data-stu-id="feec3-311">A render-blocking resource is an external JavaScript or CSS file that the browser must download, parse, and run before it displays the page.</span></span>  <span data-ttu-id="feec3-312">目标是仅运行正确显示页面所需的核心 CSS 和 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="feec3-312">The goal is to only run the core CSS and JavaScript code that is required to display the page properly.</span></span>  

<span data-ttu-id="feec3-313">然后，第一个任务是查找无需在页面加载时运行的代码。</span><span class="sxs-lookup"><span data-stu-id="feec3-313">The first task, then, is to find code that you do not need to run on page load.</span></span>  

1.  <span data-ttu-id="feec3-314">选择 **"消除呈现阻止资源** "以显示阻止的资源：</span><span class="sxs-lookup"><span data-stu-id="feec3-314">Choose **Eliminate render-blocking resources** to display the resources that are blocking:</span></span>  
    `lodash.js` <span data-ttu-id="feec3-315">`jquery.js`和 。</span><span class="sxs-lookup"><span data-stu-id="feec3-315">and `jquery.js`.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png" alt-text="有关消除呈现阻止资源机会详细信息" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png":::
       <span data-ttu-id="feec3-317">有关消除 **呈现阻止资源机会** 详细信息</span><span class="sxs-lookup"><span data-stu-id="feec3-317">More information about the **Eliminate render-blocking resources** opportunity</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-318">选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) `Coverage` \*\*\*\* 打开命令菜单，开始键入，然后选择"显示覆盖"。</span><span class="sxs-lookup"><span data-stu-id="feec3-318">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, start typing `Coverage`, and then choose **Show Coverage**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png" alt-text="从"审核"面板中打开命令菜单" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png":::
       <span data-ttu-id="feec3-320">从"审核"面板 **中打开命令** 菜单</span><span class="sxs-lookup"><span data-stu-id="feec3-320">Open the Command Menu from the **Audits** panel</span></span>  
    :::image-end:::  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png" alt-text="覆盖工具" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png":::
       <span data-ttu-id="feec3-322">覆盖**工具**</span><span class="sxs-lookup"><span data-stu-id="feec3-322">The **Coverage** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-323">Choose **Refresh** \ (![ Refresh ][ImageRefreshIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="feec3-323">Choose **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  <span data-ttu-id="feec3-324">" **覆盖** "工具概述了在加载页面时 ，和 中运行 `bundle.js` `jquery.js` `lodash.js` 的代码量。</span><span class="sxs-lookup"><span data-stu-id="feec3-324">The **Coverage** tool provides an overview of how much of the code in `bundle.js`, `jquery.js`, and `lodash.js` runs while the page loads.</span></span>  <span data-ttu-id="feec3-325">在下图中，分别不分别使用大约 76% 和 30% 的 jQuery 和 Lodash 文件。</span><span class="sxs-lookup"><span data-stu-id="feec3-325">In the figure after the following, about 76% and 30% of the jQuery and Lodash files are not used, respectively.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png" alt-text="覆盖报告" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png":::
       <span data-ttu-id="feec3-327">覆盖报告</span><span class="sxs-lookup"><span data-stu-id="feec3-327">The Coverage report</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-328">选择jquery.js\*\* 行 \*\* 。</span><span class="sxs-lookup"><span data-stu-id="feec3-328">Choose the **jquery.js** row.</span></span>  <span data-ttu-id="feec3-329">DevTools 在"源"面板中打开文件。</span><span class="sxs-lookup"><span data-stu-id="feec3-329">DevTools opens the file in the Sources panel.</span></span>  <span data-ttu-id="feec3-330">如果代码行旁边有蓝色条形，代码行将运行。</span><span class="sxs-lookup"><span data-stu-id="feec3-330">A line of code ran if it has a blue bar next to it.</span></span>  <span data-ttu-id="feec3-331">红色条表示它未运行，并且绝对不需要在页面加载时运行。</span><span class="sxs-lookup"><span data-stu-id="feec3-331">A red bar means it was not run, and is definitely not needed on page load.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png" alt-text="在"源"面板中查看 jQuery 文件" lightbox="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png":::
       <span data-ttu-id="feec3-333">在"源"面板 **中查看** jQuery 文件</span><span class="sxs-lookup"><span data-stu-id="feec3-333">Viewing the jQuery file in the **Sources** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-334">在 jQuery 代码中滚动一点。</span><span class="sxs-lookup"><span data-stu-id="feec3-334">Scroll through the jQuery code a bit.</span></span>  <span data-ttu-id="feec3-335">某些获取"run"的行实际上只是注释。</span><span class="sxs-lookup"><span data-stu-id="feec3-335">Some of the lines that get "run" are actually just comments.</span></span>  <span data-ttu-id="feec3-336">通过去除注释的小型程序运行此代码是减小此文件大小的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="feec3-336">Running this code through a minifier that strips comments is another way to reduce the size of this file.</span></span>  

<span data-ttu-id="feec3-337">简而言之，当您使用自己的代码时，"覆盖"工具可帮助\*\*\*\* 你分行分析代码，并仅提供页面加载所需的代码。</span><span class="sxs-lookup"><span data-stu-id="feec3-337">In short, when you are working with your own code, the **Coverage** tool helps you analyze your code, line-by-line, and only ship the code that is needed for page load.</span></span>  

<span data-ttu-id="feec3-338">加载 `jquery.js` 页面 `lodash.js` 是否甚至需要文件和文件？</span><span class="sxs-lookup"><span data-stu-id="feec3-338">Are the `jquery.js` and `lodash.js` files even needed to load the page?</span></span>  <span data-ttu-id="feec3-339">请求 **阻止** 工具显示资源不可用时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="feec3-339">The **Request blocking** tool displays what happens when resources are not available.</span></span>  

1.  <span data-ttu-id="feec3-340">选择 **"网络"** 工具。</span><span class="sxs-lookup"><span data-stu-id="feec3-340">Choose the **Network** tool.</span></span>  
1.  <span data-ttu-id="feec3-341">选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 以再次打开命令菜单。</span><span class="sxs-lookup"><span data-stu-id="feec3-341">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu again.</span></span>  
1.  <span data-ttu-id="feec3-342">开始键入， `blocking` 然后选择"**显示请求阻止"。**</span><span class="sxs-lookup"><span data-stu-id="feec3-342">Start typing `blocking` and then choose **Show Request Blocking**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png" alt-text="请求阻止工具" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png":::
       <span data-ttu-id="feec3-344">请求 **阻止** 工具</span><span class="sxs-lookup"><span data-stu-id="feec3-344">The **Request blocking** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-345">Choose **Add Pattern** \ (Add Pattern ![ ][ImageAddPatternIcon] \) ， `/libs/*` type， and then select to `Enter` confirm.</span><span class="sxs-lookup"><span data-stu-id="feec3-345">Choose **Add Pattern** \(![Add Pattern][ImageAddPatternIcon]\), type `/libs/*`, and then select `Enter` to confirm.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png" alt-text="添加模式以阻止对 libs 目录的任何请求" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png":::
       <span data-ttu-id="feec3-347">添加模式以阻止对目录 `libs` 的任何请求</span><span class="sxs-lookup"><span data-stu-id="feec3-347">Add a pattern to block any request to the `libs` directory</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-348">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="feec3-348">Refresh the page.</span></span>  <span data-ttu-id="feec3-349">jQuery 和 Lodash 请求为红色，表示请求被阻止。</span><span class="sxs-lookup"><span data-stu-id="feec3-349">The jQuery and Lodash requests are red, meaning that the requests were blocked.</span></span>   <span data-ttu-id="feec3-350">页面仍加载并且是交互式的，因此看起来这些资源不需要！</span><span class="sxs-lookup"><span data-stu-id="feec3-350">The page still loads and is interactive, so it looks like these resources are not needed whatsoever!</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png" alt-text=""网络"面板显示请求已被阻止" lightbox="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png":::
       <span data-ttu-id="feec3-352">网络 **工具** 显示请求已被阻止</span><span class="sxs-lookup"><span data-stu-id="feec3-352">The **Network** tool shows that the requests have been blocked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-353">Choose **Remove all patterns** \ (![ Remove all patterns ][ImageRemoveIcon] \) to delete the blocking `/libs/*` pattern.</span><span class="sxs-lookup"><span data-stu-id="feec3-353">Choose **Remove all patterns** \(![Remove all patterns][ImageRemoveIcon]\) to delete the `/libs/*` blocking pattern.</span></span>  
    
<span data-ttu-id="feec3-354">通常，请求 **阻止** 工具可用于模拟页面在任何给定资源不可用时的行为方式。</span><span class="sxs-lookup"><span data-stu-id="feec3-354">In general, the **Request blocking** tool is useful for simulating how your page behaves when any given resource is not available.</span></span>  

<span data-ttu-id="feec3-355">现在，从代码中删除对这些文件的引用，并再次审核页面：</span><span class="sxs-lookup"><span data-stu-id="feec3-355">Now, remove the references to these files from the code and audit the page again:</span></span>  

1.  <span data-ttu-id="feec3-356">返回到编辑器选项卡中，打开 `template.html` 。</span><span class="sxs-lookup"><span data-stu-id="feec3-356">Back in the editor tab, open `template.html`.</span></span>  
1.  <span data-ttu-id="feec3-357">删除 `<script src="/libs/lodash.js">` 和 `<script src="/libs/jquery.js"></script>`。</span><span class="sxs-lookup"><span data-stu-id="feec3-357">Delete `<script src="/libs/lodash.js">` and `<script src="/libs/jquery.js"></script>`.</span></span>  
1.  <span data-ttu-id="feec3-358">等待网站重新构建和重新部署。</span><span class="sxs-lookup"><span data-stu-id="feec3-358">Wait for the site to re-build and re-deploy.</span></span>  
1.  <span data-ttu-id="feec3-359">从审核工具再次 **审核** 页面。</span><span class="sxs-lookup"><span data-stu-id="feec3-359">Audit the page again from the **Audits** tool.</span></span>  <span data-ttu-id="feec3-360">总体分数应该会再次提高。</span><span class="sxs-lookup"><span data-stu-id="feec3-360">Your overall score should have improved again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png" alt-text="删除呈现阻止资源后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png":::
       <span data-ttu-id="feec3-362">删除 **呈现** 阻止资源后的审核报告</span><span class="sxs-lookup"><span data-stu-id="feec3-362">An **Audits** report after removing the render-blocking resources</span></span>  
    :::image-end:::  
    
#### <a name="optimizing-the-critical-rendering-path-in-the-real-world"></a><span data-ttu-id="feec3-363">优化实际中的关键呈现路径</span><span class="sxs-lookup"><span data-stu-id="feec3-363">Optimizing the Critical Rendering Path in the real-world</span></span>  

<span data-ttu-id="feec3-364">关键 **呈现路径** 是指加载页面所需的代码。</span><span class="sxs-lookup"><span data-stu-id="feec3-364">The **Critical Rendering Path** refers to the code that you need to load a page.</span></span>  <span data-ttu-id="feec3-365">通常，只需在页面加载期间交付关键代码，然后延迟加载其他所有内容，来加快页面加载速度。</span><span class="sxs-lookup"><span data-stu-id="feec3-365">In general, speed up page load by only shipping critical code during the page load, and then lazy-loading everything else.</span></span>  

<!--[CRP]: /web/fundamentals/performance/critical-rendering-path/  -->  

*   <span data-ttu-id="feec3-366">您不太可能能够找到能够彻底删除的脚本，但您可能会发现许多脚本不需要在页面加载期间请求，而是可能会异步请求。</span><span class="sxs-lookup"><span data-stu-id="feec3-366">It is unlikely that you are able to find scripts that you are able to remove outright, but you may find many scripts that you do not need to request during the page load, and instead may be requested asynchronously.</span></span>  <!--Navigate to [Using async or defer][async].  -->  
*   <span data-ttu-id="feec3-367">如果使用的是框架，请检查其是否具有生产模式。</span><span class="sxs-lookup"><span data-stu-id="feec3-367">If you are using a framework, check if it has a production mode.</span></span>  <span data-ttu-id="feec3-368">此模式可能使用树状抖动等[][WebpackTreeShaking]功能，以消除阻止关键呈现的不必要代码。</span><span class="sxs-lookup"><span data-stu-id="feec3-368">This mode may use a feature such as [tree shaking][WebpackTreeShaking] in order to eliminate unnecessary code that is blocking the critical render.</span></span>  
    
<!--[async]: /web/fundamentals/performance/optimizing-content-efficiency/loading-third-party-javascript/#use_async_or_defer  -->  

### <a name="do-less-main-thread-work"></a><span data-ttu-id="feec3-369">减少主线程工作</span><span class="sxs-lookup"><span data-stu-id="feec3-369">Do less main thread work</span></span>  

<span data-ttu-id="feec3-370">你的最新报告在"机会"部分显示了一些小的潜在节省，但如果在"诊断"部分向下看，则看起来最大的瓶颈是主线程活动太多。</span><span class="sxs-lookup"><span data-stu-id="feec3-370">Your latest report shows some minor potential savings in the Opportunities section, but if you look down in the Diagnostics section, it looks like the biggest bottleneck is too much main thread activity.</span></span>  

<span data-ttu-id="feec3-371">主线程是浏览器执行显示页面所需的大部分工作（如分析和运行 HTML、CSS 和 JavaScript）的地方。</span><span class="sxs-lookup"><span data-stu-id="feec3-371">The main thread is where the browser does most of the work needed to display a page, such as parsing and running HTML, CSS, and JavaScript.</span></span>  

<span data-ttu-id="feec3-372">目标是使用性能面板来分析主线程在页面加载时所执行的工作，并找到延迟或删除不必要的工作的方法。</span><span class="sxs-lookup"><span data-stu-id="feec3-372">The goal is to use the Performance panel to analyze what work the main thread is doing while the page loads, and find ways to defer or remove unnecessary work.</span></span>  

1.  <span data-ttu-id="feec3-373">选择 **"性能"** 工具。</span><span class="sxs-lookup"><span data-stu-id="feec3-373">Choose the **Performance** tool.</span></span>  
1.  <span data-ttu-id="feec3-374">Choose **Capture Settings** \ (Capture Settings ![ ][ImageCaptureIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="feec3-374">Choose **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\).</span></span>  
1.  <span data-ttu-id="feec3-375">将**网络设置为\*\*\*\*慢速 3G，\*\*\*\*将 CPU**速度设置为**慢 6 倍**。</span><span class="sxs-lookup"><span data-stu-id="feec3-375">Set **Network** to **Slow 3G** and **CPU** to **6x slowdown**.</span></span>  <span data-ttu-id="feec3-376">移动设备通常比笔记本电脑或台式机具有更多的硬件约束，因此这些设置使你可以像使用功能更少的设备一样体验页面负载。</span><span class="sxs-lookup"><span data-stu-id="feec3-376">Mobile devices typically have more hardware constraints than laptops or desktops, so these settings let you experience the page load as if you were using a less powerful device.</span></span>  
1.  <span data-ttu-id="feec3-377">Choose **Refresh** \ (![ Refresh ][ImageRefreshIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="feec3-377">Choose **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  <span data-ttu-id="feec3-378">DevTools 刷新页面，然后生成为加载页面而执行的所有工作的可视化。</span><span class="sxs-lookup"><span data-stu-id="feec3-378">DevTools refreshes the page and then produces a visualization of all the work performed in order to load the page.</span></span>  <span data-ttu-id="feec3-379">此可视化称为**跟踪。**</span><span class="sxs-lookup"><span data-stu-id="feec3-379">This visualization is referred to as the **trace**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png" alt-text="页面加载的性能工具跟踪" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png":::
       <span data-ttu-id="feec3-381">**页面**加载的性能工具跟踪</span><span class="sxs-lookup"><span data-stu-id="feec3-381">The **Performance** tool trace of the page load</span></span>  
    :::image-end:::  
    
<span data-ttu-id="feec3-382">跟踪按时间顺序显示活动，从左到右。</span><span class="sxs-lookup"><span data-stu-id="feec3-382">The trace shows activity chronologically, from left to right.</span></span>  <span data-ttu-id="feec3-383">顶部的 FPS、CPU 和 NET 图表概述了每秒帧数、CPU 活动和网络活动。</span><span class="sxs-lookup"><span data-stu-id="feec3-383">The FPS, CPU, and NET charts at the top give you an overview of frames per second, CPU activity, and network activity.</span></span>  <span data-ttu-id="feec3-384">接下来图中突出显示的黄色块，CPU 完全占用脚本活动。</span><span class="sxs-lookup"><span data-stu-id="feec3-384">The block of yellow highlighted in the figure after the next, the CPU was completely busy with scripting activity.</span></span>  <span data-ttu-id="feec3-385">这就是通过减少 JavaScript 工作来加快页面加载速度的线索。</span><span class="sxs-lookup"><span data-stu-id="feec3-385">This is a clue that you may be able to speed up page load by doing less JavaScript work.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png" alt-text="跟踪的"概述"部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png":::
   <span data-ttu-id="feec3-387">跟踪的"概述"部分</span><span class="sxs-lookup"><span data-stu-id="feec3-387">The Overview section of the trace</span></span>  
:::image-end:::  

<span data-ttu-id="feec3-388">调查跟踪以查找减少 JavaScript 工作的方法：</span><span class="sxs-lookup"><span data-stu-id="feec3-388">Investigate the trace to find ways to do less JavaScript work:</span></span>  

1.  <span data-ttu-id="feec3-389">选择 **"计时"** 部分以展开它。</span><span class="sxs-lookup"><span data-stu-id="feec3-389">Choose the **Timings** section to expand it.</span></span>  <span data-ttu-id="feec3-390">根据 React 中可能有一组 [计时][MDNUserTimingApi] 度量值这一事实，看起来 Tony 的应用正在使用 React 的开发模式。</span><span class="sxs-lookup"><span data-stu-id="feec3-390">Based on the fact that there may be a bunch of [Timings][MDNUserTimingApi] measures from React, it seems like Tony's app is using the development mode of React.</span></span>  <span data-ttu-id="feec3-391">切换到 React 的生产模式可能会获得一些简单的性能提升。</span><span class="sxs-lookup"><span data-stu-id="feec3-391">Switching to the production mode of React may yield some easy performance wins.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png" alt-text=""计时"部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png":::
       <span data-ttu-id="feec3-393">" **计时"** 部分</span><span class="sxs-lookup"><span data-stu-id="feec3-393">The **Timings** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-394">再次 **选择"计时** "以折叠该部分。</span><span class="sxs-lookup"><span data-stu-id="feec3-394">Choose **Timings** again to collapse that section.</span></span>  
1.  <span data-ttu-id="feec3-395">浏览 **"主"** 部分。</span><span class="sxs-lookup"><span data-stu-id="feec3-395">Browse the **Main** section.</span></span>  <span data-ttu-id="feec3-396">本部分显示从左到右的主线程活动的按时间顺序排列的日志。</span><span class="sxs-lookup"><span data-stu-id="feec3-396">This section shows a chronological log of main thread activity, from left to right.</span></span>  <span data-ttu-id="feec3-397">从上到 (的 y 轴) 显示事件发生的原因。</span><span class="sxs-lookup"><span data-stu-id="feec3-397">The y-axis (top to bottom) shows why events occurred.</span></span>  <span data-ttu-id="feec3-398">例如，在下面的图块中，该事件导致函数运行，导致运行，导致运行， `Evaluate Script` `(anonymous)` `(anonymous)` `__webpack__require__` 等等。</span><span class="sxs-lookup"><span data-stu-id="feec3-398">For example, in the figyre after the following, the `Evaluate Script` event caused the `(anonymous)` function to run, which caused `(anonymous)` to run, which caused `__webpack__require__` to run, and so on.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png" alt-text="主要部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png":::
       <span data-ttu-id="feec3-400">**主要**部分</span><span class="sxs-lookup"><span data-stu-id="feec3-400">The **Main** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="feec3-401">向下滚动到" **主"部分** 的底部。</span><span class="sxs-lookup"><span data-stu-id="feec3-401">Scroll down to the bottom of the **Main** section.</span></span>  <span data-ttu-id="feec3-402">使用框架时，大部分上层活动由框架导致，这通常在你的控制范围内。</span><span class="sxs-lookup"><span data-stu-id="feec3-402">When you use a framework, most of the upper activity is caused by the framework, which is usually out of your control.</span></span>  <span data-ttu-id="feec3-403">由应用引起的活动通常位于底部。</span><span class="sxs-lookup"><span data-stu-id="feec3-403">The activity caused by your app is usually at the bottom.</span></span>  <span data-ttu-id="feec3-404">在此应用中，名为的函数似乎导致 `App` 对函数产生大量 `mineBitcoin` 请求。</span><span class="sxs-lookup"><span data-stu-id="feec3-404">In this app, it seems like a function named `App` is causing a lot of requests to a `mineBitcoin` function.</span></span>  <span data-ttu-id="feec3-405">看起来 Tony 可能正在使用其粉丝的设备来挖掘加密货币...</span><span class="sxs-lookup"><span data-stu-id="feec3-405">It sounds like Tony may be using the devices of his fans to mine cryptocurrency...</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png" alt-text="将鼠标悬停在 mineBitcoin 活动上" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png":::
       <span data-ttu-id="feec3-407">将鼠标悬停在 `mineBitcoin` 活动上</span><span class="sxs-lookup"><span data-stu-id="feec3-407">Hover on the `mineBitcoin` activity</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="feec3-408">尽管框架提出的请求通常在你的控制范围内，但有时你可能以会导致框架运行效率低下的方式构建你的应用。</span><span class="sxs-lookup"><span data-stu-id="feec3-408">Although the requests that your framework makes are usually out of your control, sometimes you may structure your app in a way that causes the framework to run inefficiently.</span></span>  <span data-ttu-id="feec3-409">通过重构应用来高效地使用框架，可以减少主线程工作。</span><span class="sxs-lookup"><span data-stu-id="feec3-409">Restructuring your app to use the framework efficiently is a way to do less main thread work.</span></span>  <span data-ttu-id="feec3-410">但是，这需要深入了解框架的工作方式，以及为了更有效地使用框架，在您自己的代码中进行哪种更改。</span><span class="sxs-lookup"><span data-stu-id="feec3-410">However, this requires a deep understanding of how your framework works, and what kind of changes you make in your own code in order to use the framework more efficiently.</span></span>  
    
1.  <span data-ttu-id="feec3-411">展开 **"下向上"** 部分。</span><span class="sxs-lookup"><span data-stu-id="feec3-411">Expand the **Bottom-Up** section.</span></span>  <span data-ttu-id="feec3-412">此选项卡将分解哪些活动所花时间最多。</span><span class="sxs-lookup"><span data-stu-id="feec3-412">This tab breaks down what activities took up the most time.</span></span>  <span data-ttu-id="feec3-413">如果未在"主Bottom-Up中显示任何内容，请选择"主" **部分** 的标签。</span><span class="sxs-lookup"><span data-stu-id="feec3-413">If nothing is displayed in the Bottom-Up section, choose the label for **Main** section.</span></span>  <span data-ttu-id="feec3-414">" **底部向上** "部分只显示当前选择的任何活动或活动组的信息。</span><span class="sxs-lookup"><span data-stu-id="feec3-414">The **Bottom-Up** section only shows information for whatever activity, or group of activity, you have currently selected.</span></span>  <span data-ttu-id="feec3-415">例如，如果选择其中一个活动，则"下向上"部分将只显示该 `mineBitcoin` 活动的信息。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="feec3-415">For example, if you chose one of the `mineBitcoin` activities, the **Bottom-Up** section is only going to show information for that one activity.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png" alt-text=""Bottom-Up"选项卡" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png":::
       <span data-ttu-id="feec3-417">" **下向上"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="feec3-417">The **Bottom-Up** tab</span></span>  
    :::image-end:::  
    
<span data-ttu-id="feec3-418">" **自** 时间"列显示每个活动直接花费的时间。</span><span class="sxs-lookup"><span data-stu-id="feec3-418">The **Self Time** column shows you how much time was spent directly in each activity.</span></span>  <span data-ttu-id="feec3-419">例如，下图中，大约 63% 的主线程时间用于 `mineBitcoin` 函数。</span><span class="sxs-lookup"><span data-stu-id="feec3-419">For example, in the following figure, about 63% of main thread time was spent on the `mineBitcoin` function.</span></span>  

<span data-ttu-id="feec3-420">查看使用生产模式并减少 JavaScript 活动是否可能加快页面加载的时间。</span><span class="sxs-lookup"><span data-stu-id="feec3-420">Time to review whether using production mode and reducing JavaScript activity may speed up the page load.</span></span>  <span data-ttu-id="feec3-421">从生产模式开始：</span><span class="sxs-lookup"><span data-stu-id="feec3-421">Start with production mode:</span></span>  

1.  <span data-ttu-id="feec3-422">在编辑器选项卡中，打开 `webpack.config.js` 。</span><span class="sxs-lookup"><span data-stu-id="feec3-422">In the editor tab, open `webpack.config.js`.</span></span>  
1.  <span data-ttu-id="feec3-423">将 `"mode":"development"` 更改为 `"mode":"production"`。</span><span class="sxs-lookup"><span data-stu-id="feec3-423">Change `"mode":"development"` to `"mode":"production"`.</span></span>  
1.  <span data-ttu-id="feec3-424">等待新内部版本部署。</span><span class="sxs-lookup"><span data-stu-id="feec3-424">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="feec3-425">再次审核页面。</span><span class="sxs-lookup"><span data-stu-id="feec3-425">Audit the page again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png" alt-text="配置 Webpack 以使用生产模式后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png":::
       <span data-ttu-id="feec3-427">配置 Webpack 以使用生产模式后的审核报告</span><span class="sxs-lookup"><span data-stu-id="feec3-427">An Audits report after configuring webpack to use production mode</span></span>  
    :::image-end:::  
    
<span data-ttu-id="feec3-428">通过删除对以下项的请求来减少 JavaScript 活动 `mineBitcoin` ：</span><span class="sxs-lookup"><span data-stu-id="feec3-428">Reduce JavaScript activity by removing the request to `mineBitcoin`:</span></span>  

1.  <span data-ttu-id="feec3-429">在编辑器选项卡中，打开 `src/App.jsx` 。</span><span class="sxs-lookup"><span data-stu-id="feec3-429">In the editor tab, open `src/App.jsx`.</span></span>  
1.  <span data-ttu-id="feec3-430">在 中注释掉 `this.mineBitcoin(1500)` 对 `constructor` 的请求。</span><span class="sxs-lookup"><span data-stu-id="feec3-430">Comment out the request to `this.mineBitcoin(1500)` in the `constructor`.</span></span>  
1.  <span data-ttu-id="feec3-431">等待新内部版本部署。</span><span class="sxs-lookup"><span data-stu-id="feec3-431">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="feec3-432">再次审核页面。</span><span class="sxs-lookup"><span data-stu-id="feec3-432">Audit the page again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png" alt-text="删除不必要的 JavaScript 工作后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png":::
       <span data-ttu-id="feec3-434">删除不必要的 JavaScript 工作后的审核报告</span><span class="sxs-lookup"><span data-stu-id="feec3-434">An Audits report after removing unnecessary JavaScript work</span></span>  
    :::image-end:::  
    
<span data-ttu-id="feec3-435">看起来，最后一次更改导致性能大幅提升！</span><span class="sxs-lookup"><span data-stu-id="feec3-435">Looks like that last change caused a massive jump in performance!</span></span>  

> [!NOTE]
> <span data-ttu-id="feec3-436">本节对性能面板提供了一个相当简短的介绍。</span><span class="sxs-lookup"><span data-stu-id="feec3-436">This section provided a rather brief introduction to the Performance panel.</span></span>  <span data-ttu-id="feec3-437">若要了解有关如何分析页面性能的信息，请导航到["性能分析参考"。][DevtoolsEvaluatePerformanceReference]</span><span class="sxs-lookup"><span data-stu-id="feec3-437">To learn more about how to analyze page performance, navigate to [Performance Analysis Reference][DevtoolsEvaluatePerformanceReference].</span></span>  

<!--todo: add section when available -->  

#### <a name="doing-less-main-thread-work-in-the-real-world"></a><span data-ttu-id="feec3-438">在现实世界中减少主线程工作</span><span class="sxs-lookup"><span data-stu-id="feec3-438">Doing less main thread work in the real world</span></span>  

<span data-ttu-id="feec3-439">通常， **性能** 工具是了解您的网站在加载时执行哪些活动以及查找删除不必要活动的方法的最常见方法。</span><span class="sxs-lookup"><span data-stu-id="feec3-439">In general, the **Performance** tool is the most common way to understand what activity your site does as it loads, and find ways to remove unnecessary activity.</span></span>  

<span data-ttu-id="feec3-440">如果你更喜欢更像的方法，则用户计时 API 使你能够任意标记应用生命周期的某些阶段，以便跟踪每个阶段所花的时间 `console.log()` 。 [][MDNUserTimingApi]</span><span class="sxs-lookup"><span data-stu-id="feec3-440">If you prefer an approach that feels more like `console.log()`, the [User Timing API][MDNUserTimingApi] enables you to arbitrarily mark up certain phases of your app lifecycle, in order to track how long each of those phases takes.</span></span>  

## <a name="summary"></a><span data-ttu-id="feec3-441">摘要</span><span class="sxs-lookup"><span data-stu-id="feec3-441">Summary</span></span>  

*   <span data-ttu-id="feec3-442">无论何时开始优化网站的加载性能，始终从审核开始。</span><span class="sxs-lookup"><span data-stu-id="feec3-442">Whenever you set out to optimize the load performance of a site, always start with an audit.</span></span>  <span data-ttu-id="feec3-443">审核会建立基线，并为你提供有关如何改进的提示。</span><span class="sxs-lookup"><span data-stu-id="feec3-443">The audit establishes a baseline, and gives you tips on how to improve.</span></span>  
*   <span data-ttu-id="feec3-444">一次进行一次更改，每次更改后审核网页，以显示独立更改对性能的影响。</span><span class="sxs-lookup"><span data-stu-id="feec3-444">Make one change at a time, and audit the webpage after each change in order to display how that isolated change affects performance.</span></span>  

<!--
## Next steps  

*   Run audits on your own site!  If you need help interpreting your report, or finding ways to improve your load performance, check out [Feedback](#feedback) for ways to get help from the DevTools community.  Stack Overflow, the mailing list, or Twitter are probably best for these types of questions.  
*   Please leave [feedback](#feedback) on this tutorial.  I really do use the data to make better tutorials for you.  
-->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="feec3-445">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="feec3-445">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAddPatternIcon]: ../media/add-pattern-icon.msft.png  
[ImageCaptureIcon]: ../media/capture-icon.msft.png  
[ImageLargeResourceRowsButtonIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageMorePanelsIcon]: ../media/more-panels-icon.msft.png  
[ImagePerformIcon]: ../media/perform-icon.msft.png  
[ImageRefreshIcon]: ../media/reload-icon.msft.png  
[ImageRemoveIcon]: ../media/remove-icon.msft.png  
<!-- links -->  

[DevtoolsEvaluatePerformanceReference]: ../evaluate-performance/reference.md "性能分析参考|Microsoft Docs"  

[CourseraIntroductionWebDevelopmentClass]: https://www.coursera.org/learn/web-development#syllabus "Web 开发类|Coursera"  

[EssentialImageOptimization]: https://images.guide "基本映像优化"  

[MDNContentEncodingDirectives]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Encoding#Directives "指令 - 内容编码|MDN"  
[MDNUserTimingApi]: https://developer.mozilla.org/docs/Web/API/User_Timing_API "用户计时 API |MDN"  

[WebpackTreeShaking]: https://webpack.js.org/guides/tree-shaking "树状|webpack"  

> [!NOTE]
> <span data-ttu-id="feec3-452">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="feec3-452">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="feec3-453">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/speed/get-started)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="feec3-453">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/speed/get-started) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="feec3-455">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="feec3-455">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
