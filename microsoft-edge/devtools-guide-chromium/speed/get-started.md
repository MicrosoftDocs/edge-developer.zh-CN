---
description: 了解如何使用 Microsoft Edge DevTools 查找使网站加载速度更快的方法。
title: 使用 Microsoft Edge DevTools 优化网站速度
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 75c9df5d86ce994cebfda882a0adfa2664b6ec30
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439442"
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

# <a name="optimize-website-speed-with-microsoft-edge-devtools"></a><span data-ttu-id="6661d-104">使用 Microsoft Edge DevTools 优化网站速度</span><span class="sxs-lookup"><span data-stu-id="6661d-104">Optimize website speed with Microsoft Edge DevTools</span></span>  

## <a name="goal-of-tutorial"></a><span data-ttu-id="6661d-105">教程目标</span><span class="sxs-lookup"><span data-stu-id="6661d-105">Goal of tutorial</span></span>  

<span data-ttu-id="6661d-106">本教程指导你如何使用 Microsoft Edge DevTools 查找使网站加载速度更快的方法。</span><span class="sxs-lookup"><span data-stu-id="6661d-106">This tutorial teaches you how to use Microsoft Edge DevTools to find ways to make your websites load faster.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="6661d-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="6661d-107">Prerequisites</span></span>  

*   <span data-ttu-id="6661d-108">您应该具有基本的 Web 开发体验，类似于本 Web 开发简介 [类中介绍的内容][CourseraIntroductionWebDevelopmentClass]。</span><span class="sxs-lookup"><span data-stu-id="6661d-108">You should have basic web development experience, similar to what is taught in this [Introduction to Web Development class][CourseraIntroductionWebDevelopmentClass].</span></span>  
*   <span data-ttu-id="6661d-109">无需了解有关加载性能的一切信息。</span><span class="sxs-lookup"><span data-stu-id="6661d-109">You do not need to know anything about load performance.</span></span>  <span data-ttu-id="6661d-110">在本教程中，你将了解它。</span><span class="sxs-lookup"><span data-stu-id="6661d-110">You learn about it in this tutorial.</span></span>  

## <a name="introduction"></a><span data-ttu-id="6661d-111">简介</span><span class="sxs-lookup"><span data-stu-id="6661d-111">Introduction</span></span>  

<span data-ttu-id="6661d-112">这是 Tony。</span><span class="sxs-lookup"><span data-stu-id="6661d-112">This is Tony.</span></span>  <span data-ttu-id="6661d-113">Tony 在 cat 中非常不和谐。</span><span class="sxs-lookup"><span data-stu-id="6661d-113">Tony is very famous in cat society.</span></span>  <span data-ttu-id="6661d-114">他构建了一个网站，以便他的粉丝能够了解自己最喜爱的粉丝。</span><span class="sxs-lookup"><span data-stu-id="6661d-114">He has built a website so that his fans are able to learn about his favorite foods.</span></span>  <span data-ttu-id="6661d-115">他的粉丝喜欢该网站，但 Tony 不断听到有关网站加载缓慢的抱怨。</span><span class="sxs-lookup"><span data-stu-id="6661d-115">His fans love the site, but Tony keeps hearing complaints that the site loads slowly.</span></span>  <span data-ttu-id="6661d-116">Tony 要求你帮助加快网站速度。</span><span class="sxs-lookup"><span data-stu-id="6661d-116">Tony has asked you to help him speed the site up.</span></span>  

:::image type="complex" source="../media/speed-tony.msft.png" alt-text="Tony the cat" lightbox="../media/speed-tony.msft.png":::
   <span data-ttu-id="6661d-118">Tony the cat</span><span class="sxs-lookup"><span data-stu-id="6661d-118">Tony the cat</span></span>  
:::image-end:::  

## <a name="step-1-audit-the-site"></a><span data-ttu-id="6661d-119">步骤 1：审核网站</span><span class="sxs-lookup"><span data-stu-id="6661d-119">Step 1: Audit the site</span></span>  

<span data-ttu-id="6661d-120">无论何时开始提高网站的负载性能，始终从 **审核开始**。</span><span class="sxs-lookup"><span data-stu-id="6661d-120">Whenever you set out to improve the load performance of a site, **always start with an audit**.</span></span>  
<span data-ttu-id="6661d-121">审核有 2 个重要功能：</span><span class="sxs-lookup"><span data-stu-id="6661d-121">The audit has 2 important functions:</span></span>  

*   <span data-ttu-id="6661d-122">它可创建 **一个** 基准，用于度量后续更改。</span><span class="sxs-lookup"><span data-stu-id="6661d-122">It creates a **baseline** for you to measure subsequent changes against.</span></span>  
*   <span data-ttu-id="6661d-123">它为你提供 **了有关哪些** 更改影响最大的可操作提示。</span><span class="sxs-lookup"><span data-stu-id="6661d-123">It gives you **actionable tips** on what changes have the most impact.</span></span>  
    
### <a name="set-up"></a><span data-ttu-id="6661d-124">设置</span><span class="sxs-lookup"><span data-stu-id="6661d-124">Set up</span></span>  

<span data-ttu-id="6661d-125">首先，必须设置网站，以便以后能够进行更改。</span><span class="sxs-lookup"><span data-stu-id="6661d-125">First, you must set up the site so that you are able to make changes to it later.</span></span>  

1.  <span data-ttu-id="6661d-126">[打开网站的源代码](https://glitch.com/edit/#!/tony)。</span><span class="sxs-lookup"><span data-stu-id="6661d-126">[Open the source code for the site](https://glitch.com/edit/#!/tony).</span></span>  <span data-ttu-id="6661d-127">此选项卡称为"编辑器 **"选项卡**。</span><span class="sxs-lookup"><span data-stu-id="6661d-127">This tab is referred to as the **editor tab**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js.msft.png" alt-text="编辑器选项卡" lightbox="../media/speed-glitch-tony-server-js.msft.png":::
       <span data-ttu-id="6661d-129">编辑器 **选项卡**</span><span class="sxs-lookup"><span data-stu-id="6661d-129">The **editor tab**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-130">选择 **tony**。</span><span class="sxs-lookup"><span data-stu-id="6661d-130">Choose **tony**.</span></span>  <span data-ttu-id="6661d-131">将出现一个菜单。</span><span class="sxs-lookup"><span data-stu-id="6661d-131">A menu appears.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js-remix-project.msft.png" alt-text="选择 tony 后出现的菜单" lightbox="../media/speed-glitch-tony-server-js-remix-project.msft.png":::
       <span data-ttu-id="6661d-133">选择 tony 后出现的 **菜单**</span><span class="sxs-lookup"><span data-stu-id="6661d-133">The menu that appears after choosing **tony**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-134">选择 **"重新混合项目"。**</span><span class="sxs-lookup"><span data-stu-id="6661d-134">Choose **Remix Project**.</span></span>  <span data-ttu-id="6661d-135">项目名称从 **tony** 更改为随机生成的名称。</span><span class="sxs-lookup"><span data-stu-id="6661d-135">The name of the project changes from **tony** to some randomly-generated name.</span></span>  <span data-ttu-id="6661d-136">现在，您具有自己的代码可编辑副本。</span><span class="sxs-lookup"><span data-stu-id="6661d-136">You now have your own editable copy of the code.</span></span>  <span data-ttu-id="6661d-137">稍后，您可以对此代码进行更改。</span><span class="sxs-lookup"><span data-stu-id="6661d-137">Later on, you may make changes to this code.</span></span>  
1.  <span data-ttu-id="6661d-138">选择 **"显示**"，然后选择 **"在新建窗口中"。**</span><span class="sxs-lookup"><span data-stu-id="6661d-138">Choose **Show** and choose **In a New Window**.</span></span>  <span data-ttu-id="6661d-139">演示将在新选项卡中打开。 此选项卡称为"演示 **"选项卡**。 加载网站可能需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="6661d-139">The demo opens in a new tab.  This tab is be referred to as the **demo tab**.  It may take a while for the site to load.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live.msft.png" alt-text=""演示"选项卡" lightbox="../media/speed-glitch-tony-show-live.msft.png":::
       <span data-ttu-id="6661d-141">"演示"选项卡</span><span class="sxs-lookup"><span data-stu-id="6661d-141">The demo tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-142">选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="6661d-142">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="6661d-143">Microsoft Edge DevTools 将在演示旁边打开。</span><span class="sxs-lookup"><span data-stu-id="6661d-143">Microsoft Edge DevTools opens up alongside the demo.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live-console.msft.png" alt-text="DevTools 和演示" lightbox="../media/speed-glitch-tony-show-live-console.msft.png":::
       <span data-ttu-id="6661d-145">DevTools 和演示</span><span class="sxs-lookup"><span data-stu-id="6661d-145">DevTools and the demo</span></span>  
    :::image-end:::  
    
<span data-ttu-id="6661d-146">对于本教程中的其余屏幕截图，DevTools 显示在单独的窗口中。</span><span class="sxs-lookup"><span data-stu-id="6661d-146">For the rest of the screenshots in this tutorial, DevTools is shown in a separate window.</span></span>  <span data-ttu-id="6661d-147">选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) `Undock` \*\*\*\* 打开命令菜单，键入 ，然后选择在单独的窗口中取消停靠。</span><span class="sxs-lookup"><span data-stu-id="6661d-147">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, typing `Undock`, and then selecting **Undock into separate window**.</span></span>  

:::image type="complex" source="../media/speed-console.msft.png" alt-text="Undocked DevTools" lightbox="../media/speed-console.msft.png":::
   <span data-ttu-id="6661d-149">Undocked DevTools</span><span class="sxs-lookup"><span data-stu-id="6661d-149">Undocked DevTools</span></span>  
:::image-end:::  

### <a name="establish-a-baseline"></a><span data-ttu-id="6661d-150">建立基线</span><span class="sxs-lookup"><span data-stu-id="6661d-150">Establish a baseline</span></span>  

<span data-ttu-id="6661d-151">基线是网站在做出任何性能改进之前如何执行的记录。</span><span class="sxs-lookup"><span data-stu-id="6661d-151">The baseline is a record of how the site performed before you made any performance improvements.</span></span>  

1.  <span data-ttu-id="6661d-152">选择 **"审核"** 工具。</span><span class="sxs-lookup"><span data-stu-id="6661d-152">Choose the **Audits** tool.</span></span>  <span data-ttu-id="6661d-153">它可能隐藏在更多 **面板** \ (更多面板 ![ ](../media/more-panels-icon.msft.png) \) 按钮后面。</span><span class="sxs-lookup"><span data-stu-id="6661d-153">It may be hidden behind the **More Panels** \(![More Panels](../media/more-panels-icon.msft.png)\) button.</span></span>  <span data-ttu-id="6661d-154">此面板上有一个"灯楼"，因为支持审核面板的项目名为 **"Lighthouse"。**</span><span class="sxs-lookup"><span data-stu-id="6661d-154">There is a Lighthouse on this panel because the project that powers the Audits panel is named **Lighthouse**.</span></span>  
    
    [!INCLUDE [audits-panel-note](../includes/audits-panel-note.md)]  
    
    :::image type="complex" source="../media/speed-audits-performance.msft.png" alt-text="审核工具" lightbox="../media/speed-audits-performance.msft.png":::
       <span data-ttu-id="6661d-156">**审核**工具</span><span class="sxs-lookup"><span data-stu-id="6661d-156">The **Audits** tool</span></span>  
    :::image-end:::  
    
    <!--todo: add link to Lighthouse when section is available  -->  
    <!-- /web/tools/lighthouse  -->  
    
1.  <span data-ttu-id="6661d-157">将审核配置设置与上图中的设置相匹配。</span><span class="sxs-lookup"><span data-stu-id="6661d-157">Match your audit configuration settings to those in the previous figure.</span></span>  <span data-ttu-id="6661d-158">以下是不同选项的说明：</span><span class="sxs-lookup"><span data-stu-id="6661d-158">Here is an explanation of the different options:</span></span>  
    
    *   <span data-ttu-id="6661d-159">**设备**。</span><span class="sxs-lookup"><span data-stu-id="6661d-159">**Device**.</span></span>  <span data-ttu-id="6661d-160">设置为 **"移动** "将更改用户代理字符串并模拟移动视口。</span><span class="sxs-lookup"><span data-stu-id="6661d-160">Set to **Mobile** changes the user agent string and simulates a mobile viewport.</span></span>  <span data-ttu-id="6661d-161">设置为 **桌面** 几乎可以关闭 **移动** 版更改。</span><span class="sxs-lookup"><span data-stu-id="6661d-161">Set to **Desktop** pretty much just turns off the **Mobile** changes.</span></span>  
    *   <span data-ttu-id="6661d-162">**审核**。</span><span class="sxs-lookup"><span data-stu-id="6661d-162">**Audits**.</span></span>  <span data-ttu-id="6661d-163">关闭类别以防止审核 **面板** 运行这些审核，并且从你的报告中排除这些审核。</span><span class="sxs-lookup"><span data-stu-id="6661d-163">Turn off a category to prevent the **Audits** panel from running those audits, and excludes those audits from your report.</span></span>  <span data-ttu-id="6661d-164">如果要显示提供的建议类型，请保留其他类别"打开"。</span><span class="sxs-lookup"><span data-stu-id="6661d-164">Leave the other categories Turned on, if you want to display the types of recommendations that are provided.</span></span>  <span data-ttu-id="6661d-165">关闭类别可稍微加快审核过程。</span><span class="sxs-lookup"><span data-stu-id="6661d-165">Turn off categories to slightly speed up the auditing process.</span></span>  
    *   <span data-ttu-id="6661d-166">**限制**。</span><span class="sxs-lookup"><span data-stu-id="6661d-166">**Throttling**.</span></span>  <span data-ttu-id="6661d-167">设置为 **模拟慢速 4G 时，4x CPU 速度将** 模拟在移动设备上浏览的典型条件。</span><span class="sxs-lookup"><span data-stu-id="6661d-167">Set to **Simulated Slow 4G, 4x CPU Slowdown** simulates the typical conditions of browsing on a mobile device.</span></span>  <span data-ttu-id="6661d-168">它命名为"模拟"，因为审核面板在审核过程中实际上并没有限制。</span><span class="sxs-lookup"><span data-stu-id="6661d-168">It is named "simulated" because the Audits panel does not actually throttle during the auditing process.</span></span>  <span data-ttu-id="6661d-169">相反，它只是推断页面在移动条件下加载所花的时间。</span><span class="sxs-lookup"><span data-stu-id="6661d-169">Instead, it just extrapolates how long the page takes to load under mobile conditions.</span></span>  <span data-ttu-id="6661d-170">另 **一** 方面，应用...设置实际上会限制你的 CPU 和网络，同时权衡较长的审核过程。</span><span class="sxs-lookup"><span data-stu-id="6661d-170">The **Applied...** setting, on the other hand, actually throttles your CPU and network, with the tradeoff of a longer auditing process.</span></span>  
    *   <span data-ttu-id="6661d-171">**清除存储**。</span><span class="sxs-lookup"><span data-stu-id="6661d-171">**Clear Storage**.</span></span>  <span data-ttu-id="6661d-172">打开复选框以在审核前清除与页面关联的所有存储。</span><span class="sxs-lookup"><span data-stu-id="6661d-172">Turn on the checkbox to clear all storage associated with the page before every audit.</span></span>  <span data-ttu-id="6661d-173">如果希望审核首次访问者对网站的体验，请保留此设置。</span><span class="sxs-lookup"><span data-stu-id="6661d-173">Leave this setting on if you want to audit how first-time visitors experience your site.</span></span>  <span data-ttu-id="6661d-174">在需要重复访问体验时关闭此设置。</span><span class="sxs-lookup"><span data-stu-id="6661d-174">Turn off this setting when you want the repeat-visit experience.</span></span>  
    
1.  <span data-ttu-id="6661d-175">选择 **"运行审核"。**</span><span class="sxs-lookup"><span data-stu-id="6661d-175">Choose **Run Audits**.</span></span>  <span data-ttu-id="6661d-176">10 到 30 秒后\*\*\*\*，"审核"面板将显示网站性能报告。</span><span class="sxs-lookup"><span data-stu-id="6661d-176">After 10 to 30 seconds, the **Audits** panel displays a report of the performance of the site.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png" alt-text="网站性能的审核面板报告" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png":::
       <span data-ttu-id="6661d-178">网站性能的审核面板报告</span><span class="sxs-lookup"><span data-stu-id="6661d-178">The report for the Audits panel of the performance of the site</span></span>  
    :::image-end:::  
    
#### <a name="handling-report-errors"></a><span data-ttu-id="6661d-179">处理报告错误</span><span class="sxs-lookup"><span data-stu-id="6661d-179">Handling report errors</span></span>  

<span data-ttu-id="6661d-180">如果你在审核面板报告中收到错误，请尝试在未打开其他选项卡的 **InPrivate** 窗口中运行演示选项卡。</span><span class="sxs-lookup"><span data-stu-id="6661d-180">If you ever get an error in your Audits panel report, try running the demo tab from an **InPrivate** window with no other tabs open.</span></span>  <span data-ttu-id="6661d-181">这可确保从干净状态运行 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="6661d-181">This ensures that you are running Microsoft Edge from a clean state.</span></span>  <span data-ttu-id="6661d-182">尤其是 Microsoft Edge 扩展通常会干扰审核过程。</span><span class="sxs-lookup"><span data-stu-id="6661d-182">Microsoft Edge Extensions in particular often interfere with the auditing process.</span></span>  

<!--todo: add screen capture for error in audit -->  
<!--
:::image type="complex" source="../media/speed-.msft.png" alt-text="A report that errored" lightbox="../media/speed-.msft.png":::
   A report that errored  
:::image-end:::  
-->  

### <a name="understand-your-report"></a><span data-ttu-id="6661d-183">了解报告</span><span class="sxs-lookup"><span data-stu-id="6661d-183">Understand your report</span></span>  

<span data-ttu-id="6661d-184">报告顶部的数字是网站的总体性能分数。</span><span class="sxs-lookup"><span data-stu-id="6661d-184">The number at the top of your report is the overall performance score for the site.</span></span>  <span data-ttu-id="6661d-185">稍后，当您对代码进行更改时，显示的数量应该会上升。</span><span class="sxs-lookup"><span data-stu-id="6661d-185">Later, as you make changes to the code, the number displayed should rise.</span></span>  <span data-ttu-id="6661d-186">分数越高表示性能越好。</span><span class="sxs-lookup"><span data-stu-id="6661d-186">A higher score means better performance.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png" alt-text="总体性能分数" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png":::
   <span data-ttu-id="6661d-188">总体性能分数</span><span class="sxs-lookup"><span data-stu-id="6661d-188">The overall performance score</span></span>  
:::image-end:::  

<span data-ttu-id="6661d-189">" **指标** "部分提供网站性能的测量指标。</span><span class="sxs-lookup"><span data-stu-id="6661d-189">The **Metrics** section provides quantitative measurements of the performance of the site.</span></span>  <span data-ttu-id="6661d-190">每个指标提供对性能不同方面的见解。</span><span class="sxs-lookup"><span data-stu-id="6661d-190">Each metric provides insight into a different aspect of the performance.</span></span>  <span data-ttu-id="6661d-191">例如，第\*\*\*\* 一个内容绘制会告知你何时将内容首次绘制到屏幕，这是用户对页面加载的感知中的一个重要里程碑，而"时间到交互"\*\*\*\* 标记页面显示为足以处理用户交互的点。</span><span class="sxs-lookup"><span data-stu-id="6661d-191">For example, **First Contentful Paint** tells you when content is first painted to the screen, which is an important milestone in the user's perception of the page load, whereas **Time To Interactive** marks the point at which the page appears ready enough to handle user interactions.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png" alt-text=""指标"部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png":::
   <span data-ttu-id="6661d-193">" **指标"** 部分</span><span class="sxs-lookup"><span data-stu-id="6661d-193">The **Metrics** section</span></span>  
:::image-end:::  

<span data-ttu-id="6661d-194">Choose the highlighted toggle button in the following figure to display a description for each metric， and choose **Learn More** to read documentation about it.</span><span class="sxs-lookup"><span data-stu-id="6661d-194">Choose the highlighted toggle button in the following figure to display a description for each metric, and choose **Learn More** to read documentation about it.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png" alt-text="选择突出显示的切换按钮以展开"指标"项" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png":::
   <span data-ttu-id="6661d-196">选择突出显示的切换按钮以展开"指标"项</span><span class="sxs-lookup"><span data-stu-id="6661d-196">Choose the highlighted toggle button to expand the Metrics items</span></span>  
:::image-end:::  

<span data-ttu-id="6661d-197">下面的"指标"是显示页面加载时的外观的屏幕截图集合。</span><span class="sxs-lookup"><span data-stu-id="6661d-197">Below Metrics is a collection of screenshots that show you how the page looked as it loaded.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="页面在加载时的外观的屏幕截图" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   <span data-ttu-id="6661d-199">页面在加载时的外观的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="6661d-199">Screenshots of how the page looked while loading</span></span>  
:::image-end:::  

<span data-ttu-id="6661d-200">" **机会** "部分提供了有关如何提高此特定页面的加载性能的特定提示。</span><span class="sxs-lookup"><span data-stu-id="6661d-200">The **Opportunities** section provides specific tips on how to improve the load performance of this specific page.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text=""机会"部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   <span data-ttu-id="6661d-202">" **机会"** 部分</span><span class="sxs-lookup"><span data-stu-id="6661d-202">The **Opportunities** section</span></span>  
:::image-end:::  

<span data-ttu-id="6661d-203">选择一个了解它更多信息的机会。</span><span class="sxs-lookup"><span data-stu-id="6661d-203">Choose an opportunity to learn more about it.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png" alt-text="消除呈现阻止资源的机会" lightbox="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png":::
   <span data-ttu-id="6661d-205">**消除呈现阻止资源** 的机会</span><span class="sxs-lookup"><span data-stu-id="6661d-205">**Eliminate render-blocking resources** opportunity</span></span>  
:::image-end:::  

<span data-ttu-id="6661d-206">选择 **"了解** 更多"可显示有关机会为什么很重要的文档，以及如何修复它的特定建议。</span><span class="sxs-lookup"><span data-stu-id="6661d-206">Choose **Learn More** to display documentation about why an opportunity is important, and specific recommendations on how to fix it.</span></span>  

:::image type="complex" source="../media/speed-web-dev-performance-audits.msft.png" alt-text="有关消除呈现阻止资源机会的文档" lightbox="../media/speed-web-dev-performance-audits.msft.png":::
   <span data-ttu-id="6661d-208">有关消除 **呈现阻止资源机会** 的文档</span><span class="sxs-lookup"><span data-stu-id="6661d-208">Documentation for the **Eliminate render-blocking resources** opportunity</span></span>  
:::image-end:::  

<span data-ttu-id="6661d-209">**诊断部分**提供了有关导致页面加载时间的因素详细信息。</span><span class="sxs-lookup"><span data-stu-id="6661d-209">The **Diagnostics** section provides more information about factors that contribute to the load time of the page.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png" alt-text="诊断部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png":::
   <span data-ttu-id="6661d-211">诊断**部分**</span><span class="sxs-lookup"><span data-stu-id="6661d-211">The **Diagnostics** section</span></span>  
:::image-end:::  

<span data-ttu-id="6661d-212">" **通过审核"** 部分显示网站正确执行的内容。</span><span class="sxs-lookup"><span data-stu-id="6661d-212">The **Passed Audits** section shows you what the site is doing correctly.</span></span>  <span data-ttu-id="6661d-213">选择展开部分。</span><span class="sxs-lookup"><span data-stu-id="6661d-213">Choose to expand the section.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png" alt-text=""通过审核"部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png":::
   <span data-ttu-id="6661d-215">" **通过审核"** 部分</span><span class="sxs-lookup"><span data-stu-id="6661d-215">The **Passed Audits** section</span></span>  
:::image-end:::  

## <a name="step-2-experiment"></a><span data-ttu-id="6661d-216">步骤 2：试验</span><span class="sxs-lookup"><span data-stu-id="6661d-216">Step 2: Experiment</span></span>  

<span data-ttu-id="6661d-217">审核报告的"机会"部分提供了有关如何提高页面性能的提示。</span><span class="sxs-lookup"><span data-stu-id="6661d-217">The Opportunities section of your audit report gives you tips on how to improve the performance of the page.</span></span>  <span data-ttu-id="6661d-218">在此部分中，将实现对基本代码的建议更改，并审核每次更改后的网站，以测量更改对网站速度的影响。</span><span class="sxs-lookup"><span data-stu-id="6661d-218">In this section, you implement the recommended changes to the codebase, auditing the site after each change to measure how it affects site speed.</span></span>  

### <a name="enable-text-compression"></a><span data-ttu-id="6661d-219">启用文本压缩</span><span class="sxs-lookup"><span data-stu-id="6661d-219">Enable text compression</span></span>  

<span data-ttu-id="6661d-220">你的报告显示，避免大量网络负载是提升页面性能的一个首要机会。</span><span class="sxs-lookup"><span data-stu-id="6661d-220">Your report says that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="6661d-221">启用文本压缩是提高页面性能的机会。</span><span class="sxs-lookup"><span data-stu-id="6661d-221">Enabling text compression is an opportunity to improve the performance of the page.</span></span>  

<span data-ttu-id="6661d-222">文本压缩是在通过网络发送文本文件之前减小或压缩文本文件的大小时。</span><span class="sxs-lookup"><span data-stu-id="6661d-222">Text compression is when you reduce, or compress, the size of a text file before sending it over the network.</span></span>  <span data-ttu-id="6661d-223">类似于在发送目录以减小大小之前对目录进行存档的方式。</span><span class="sxs-lookup"><span data-stu-id="6661d-223">Similar to how you may archive a directory before sending it to reduce the size.</span></span>  

<span data-ttu-id="6661d-224">在启用压缩之前，下面是手动检查文本资源是否压缩的几种方法。</span><span class="sxs-lookup"><span data-stu-id="6661d-224">Before you enable compression, here are a couple of ways to manually check whether text resources are compressed.</span></span>  

1.  <span data-ttu-id="6661d-225">选择" **网络"** 工具。</span><span class="sxs-lookup"><span data-stu-id="6661d-225">Choose the **Network** tool.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network.msft.png" alt-text="“网络”面板" lightbox="../media/speed-glitch-tony-remix-network.msft.png":::
       <span data-ttu-id="6661d-227">网络**工具**</span><span class="sxs-lookup"><span data-stu-id="6661d-227">The **Network** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-228">选择" **网络"设置** 图标。</span><span class="sxs-lookup"><span data-stu-id="6661d-228">Choose the **Network setting** icon.</span></span>  
1.  <span data-ttu-id="6661d-229">选中" **使用大型请求行"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="6661d-229">Choose the **Use Large Request Rows** checkbox.</span></span>  <span data-ttu-id="6661d-230">网络请求表中行的高度将增加。</span><span class="sxs-lookup"><span data-stu-id="6661d-230">The height of the rows in the table of network requests increases.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png" alt-text="网络请求表中的大行" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png":::
       <span data-ttu-id="6661d-232">网络请求表中的大行</span><span class="sxs-lookup"><span data-stu-id="6661d-232">Large rows in the network requests table</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-233">如果未 **显示** 网络请求表中的"大小"列，请选择"大小"> **表标题**。</span><span class="sxs-lookup"><span data-stu-id="6661d-233">If the **Size** column in the table of network requests is not displayed, choose the table header > **Size**.</span></span>  

<span data-ttu-id="6661d-234">每个 **Size** 单元格显示两个值。</span><span class="sxs-lookup"><span data-stu-id="6661d-234">Each **Size** cell shows two values.</span></span>  <span data-ttu-id="6661d-235">顶部值是已下载资源的大小。</span><span class="sxs-lookup"><span data-stu-id="6661d-235">The top value is the size of the downloaded resource.</span></span>  
<span data-ttu-id="6661d-236">底部值是未压缩资源的大小。</span><span class="sxs-lookup"><span data-stu-id="6661d-236">The bottom value is the size of the uncompressed resource.</span></span>  <span data-ttu-id="6661d-237">如果这两个值相同，则当通过网络发送资源时，不会压缩该资源。</span><span class="sxs-lookup"><span data-stu-id="6661d-237">If the two values are the same, then the resource is not being compressed when it is sent over the network.</span></span>  <span data-ttu-id="6661d-238">例如，在上图中，的顶部和底部值为 `bundle.js` `1.2 MB` 和 `1.2 MB` 。</span><span class="sxs-lookup"><span data-stu-id="6661d-238">For example, in the previous figure, the top and bottom values for `bundle.js` are `1.2 MB` and `1.2 MB`.</span></span>  

<span data-ttu-id="6661d-239">通过检查资源的 HTTP 标头检查压缩：</span><span class="sxs-lookup"><span data-stu-id="6661d-239">Check for compression by inspecting the HTTP headers of a resource:</span></span>  

1.  <span data-ttu-id="6661d-240">选择 `bundle.js` 。</span><span class="sxs-lookup"><span data-stu-id="6661d-240">Choose `bundle.js`.</span></span>  
1.  <span data-ttu-id="6661d-241">选择 **"标题"** 面板。</span><span class="sxs-lookup"><span data-stu-id="6661d-241">Choose the **Headers** panel.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png" alt-text=""标题"面板" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png":::
       <span data-ttu-id="6661d-243">" **标题"** 面板</span><span class="sxs-lookup"><span data-stu-id="6661d-243">The **Headers** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-244">在 **"响应头"** 部分搜索 `content-encoding` 标头。</span><span class="sxs-lookup"><span data-stu-id="6661d-244">Search the **Response Headers** section for a `content-encoding` header.</span></span>  <span data-ttu-id="6661d-245">`content-encoding`不显示标题，这意味着 `bundle.js` 未进行压缩。</span><span class="sxs-lookup"><span data-stu-id="6661d-245">A `content-encoding` heading is not displayed, meaning that `bundle.js` was not compressed.</span></span>  <span data-ttu-id="6661d-246">压缩资源时，此标头通常设置为 、 或 `gzip` `deflate` `br` 。</span><span class="sxs-lookup"><span data-stu-id="6661d-246">When a resource is compressed, this header is usually set to `gzip`, `deflate`, or `br`.</span></span>  <span data-ttu-id="6661d-247">有关这些值的说明，请导航到"指令["。][MDNContentEncodingDirectives]</span><span class="sxs-lookup"><span data-stu-id="6661d-247">For an explanation of the values, navigate to [Directives][MDNContentEncodingDirectives].</span></span>  

<span data-ttu-id="6661d-248">与说明一起足够。</span><span class="sxs-lookup"><span data-stu-id="6661d-248">Enough with the explanations.</span></span>  <span data-ttu-id="6661d-249">进行一些更改的时间。</span><span class="sxs-lookup"><span data-stu-id="6661d-249">Time to make some changes.</span></span>  <span data-ttu-id="6661d-250">通过添加几行代码启用文本压缩：</span><span class="sxs-lookup"><span data-stu-id="6661d-250">Enable text compression by adding a couple of lines of code:</span></span>  

1.  <span data-ttu-id="6661d-251">在"编辑器"选项卡中，选择 \*\*"server.js"。 \*\*</span><span class="sxs-lookup"><span data-stu-id="6661d-251">In the editor tab, choose **server.js**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js.msft.png" alt-text="编辑server.js" lightbox="../media/speed-glitch-tony-remix-server-js.msft.png":::
       <span data-ttu-id="6661d-253">编辑</span><span class="sxs-lookup"><span data-stu-id="6661d-253">Edit</span></span> `server.js`  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-254">将以下代码添加到 **server.js**。</span><span class="sxs-lookup"><span data-stu-id="6661d-254">Add the following code to **server.js**.</span></span>  <span data-ttu-id="6661d-255">请确保放在 `app.use(compression())` 之前 `app.use(express.static('build'))` 。</span><span class="sxs-lookup"><span data-stu-id="6661d-255">Make sure to put `app.use(compression())` before `app.use(express.static('build'))`.</span></span>  

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
    > <span data-ttu-id="6661d-256">通常，你必须通过 类似 的内容安装程序包，但此操作 `compression` `npm i -S compression` 已针对你完成。</span><span class="sxs-lookup"><span data-stu-id="6661d-256">Usually, you have to install the `compression` package via something like `npm i -S compression`, but this has already been done for you.</span></span>  
    
1.  <span data-ttu-id="6661d-257">等待 Glitch 部署网站的新内部版本。</span><span class="sxs-lookup"><span data-stu-id="6661d-257">Wait for Glitch to deploy the new build of the site.</span></span>  <span data-ttu-id="6661d-258">工具 **旁边的奇特** 动画意味着正在重建和重新部署网站。</span><span class="sxs-lookup"><span data-stu-id="6661d-258">The fancy animation next to **Tools** means that the site is getting rebuilt and redeployed.</span></span>  <span data-ttu-id="6661d-259">当"工具"旁边的动画消失时， **更改** 已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="6661d-259">The change is ready when the animation next to **Tools** goes away.</span></span>  <span data-ttu-id="6661d-260">选择 **"显示**"，然后**再次选择"在新建窗口中"。**</span><span class="sxs-lookup"><span data-stu-id="6661d-260">Choose **Show** and choose **In a New Window** again.</span></span>  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js-edited.msft.png" alt-text="The animation that indicates that the site is getting built" lightbox="../media/speed-glitch-tony-remix-server-js-edited.msft.png":::
       The animation that indicates that the site is getting built  
    :::image-end:::  
    -->  
    
<span data-ttu-id="6661d-261">使用之前了解到的工作流手动检查压缩是否正常工作：</span><span class="sxs-lookup"><span data-stu-id="6661d-261">Use the workflows that you learned earlier to manually check that the compression is working:</span></span>  

1.  <span data-ttu-id="6661d-262">返回到演示选项卡并刷新页面。</span><span class="sxs-lookup"><span data-stu-id="6661d-262">Go back to the demo tab and refresh the page.</span></span>  <span data-ttu-id="6661d-263">现在 **，"** 大小"列应显示文本资源（如 ）的 2 个不同值 `bundle.js` 。</span><span class="sxs-lookup"><span data-stu-id="6661d-263">The **Size** column should now show 2 different values for text resources like `bundle.js`.</span></span>  <span data-ttu-id="6661d-264">在下图中，的顶级值为 通过网络发送的文件的大小，而 的底值是未 `256 KB` `bundle.js` `1.2 MB` 压缩的文件大小。</span><span class="sxs-lookup"><span data-stu-id="6661d-264">In the figure after the following, the top value of `256 KB` for `bundle.js` is the size of the file that was sent over the network, and the bottom value of `1.2 MB` is the uncompressed file size.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-main.msft.png" alt-text=""大小"列现在显示文本资源的 2 个不同值" lightbox="../media/speed-glitch-tony-remix-network-main.msft.png":::
       <span data-ttu-id="6661d-266">" **大小** "列现在显示文本资源的 2 个不同值</span><span class="sxs-lookup"><span data-stu-id="6661d-266">The **Size** column now shows 2 different values for text resources</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-267">的 **"响应头"** `bundle.js` 部分现在应包含 `content-encoding: gzip` 标头。</span><span class="sxs-lookup"><span data-stu-id="6661d-267">The **Response Headers** section for `bundle.js` should now include a `content-encoding: gzip` header.</span></span>
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png" alt-text=""响应头"部分现在包含内容编码标头" lightbox="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png":::
       <span data-ttu-id="6661d-269">" **响应头"** 部分现在包含内容编码标头</span><span class="sxs-lookup"><span data-stu-id="6661d-269">The **Response Headers** section now contains a content-encoding header</span></span>  
    :::image-end:::  
    
<span data-ttu-id="6661d-270">再次审核页面，以测量文本压缩对页面的加载性能的影响类型：</span><span class="sxs-lookup"><span data-stu-id="6661d-270">Audit the page again to measure what kind of impact text compression has on the load performance of the page:</span></span>  

1.  <span data-ttu-id="6661d-271">选择 **"审核"** 工具。</span><span class="sxs-lookup"><span data-stu-id="6661d-271">Choose the **Audits** tool.</span></span>  
1.  <span data-ttu-id="6661d-272">Choose **Perform an audit** \ (Perform an audit ![ ](../media/perform-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="6661d-272">Choose **Perform an audit** \(![Perform an audit](../media/perform-icon.msft.png)\).</span></span>  
1.  <span data-ttu-id="6661d-273">保持设置与以前相同。</span><span class="sxs-lookup"><span data-stu-id="6661d-273">Leave the settings the same as before.</span></span>  
1.  <span data-ttu-id="6661d-274">选择 **"运行审核"。**</span><span class="sxs-lookup"><span data-stu-id="6661d-274">Choose **Run audit**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png" alt-text="启用文本压缩后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png":::
       <span data-ttu-id="6661d-276">启用文本压缩后的审核报告</span><span class="sxs-lookup"><span data-stu-id="6661d-276">An Audits report after enabling text compression</span></span>  
    :::image-end:::  
    
<!--  Woohoo!  That looks like progress.  -->  <span data-ttu-id="6661d-277">总体性能分数应已提高，这意味着网站速度将加快。</span><span class="sxs-lookup"><span data-stu-id="6661d-277">Your overall performance score should have increased, meaning that the site is getting faster.</span></span>  

#### <a name="text-compression-in-the-real-world"></a><span data-ttu-id="6661d-278">现实中的文本压缩</span><span class="sxs-lookup"><span data-stu-id="6661d-278">Text compression in the real world</span></span>  

<span data-ttu-id="6661d-279">大多数服务器确实有如下所示的简单修补程序，用于启用压缩！</span><span class="sxs-lookup"><span data-stu-id="6661d-279">Most servers really do have simple fixes like this for enabling compression!</span></span>  <span data-ttu-id="6661d-280">只需搜索如何配置用于压缩文本的服务器。</span><span class="sxs-lookup"><span data-stu-id="6661d-280">Just do a search on how to configure whatever server you use to compress text.</span></span>  

### <a name="resize-images"></a><span data-ttu-id="6661d-281">调整图像大小</span><span class="sxs-lookup"><span data-stu-id="6661d-281">Resize images</span></span>  

<span data-ttu-id="6661d-282">你的报告指示避免大量网络负载是提升页面性能的一个首要机会。</span><span class="sxs-lookup"><span data-stu-id="6661d-282">Your report indicates that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="6661d-283">调整图像大小有助于减小网络有效负载的大小。</span><span class="sxs-lookup"><span data-stu-id="6661d-283">Resizing images helps reduce the size of the network payload.</span></span>  <span data-ttu-id="6661d-284">如果用户在 500 像素宽的移动设备上查看图像，则发送 1500 像素宽的图像实际上没有意义。</span><span class="sxs-lookup"><span data-stu-id="6661d-284">If your user is viewing your images on a mobile device screen that is 500-pixels-wide, there is really no point in sending a 1500-pixel-wide image.</span></span>  <span data-ttu-id="6661d-285">理想情况下，你最多发送一个 500 像素宽的图像。</span><span class="sxs-lookup"><span data-stu-id="6661d-285">Ideally, you send a 500-pixel-wide image, at most.</span></span>  

1.  <span data-ttu-id="6661d-286">在你的报告中，选择 **"避免大量网络负载** "以显示应调整大小的图像。</span><span class="sxs-lookup"><span data-stu-id="6661d-286">In your report, choose **Avoid enormous network payloads** to display which images should be resized.</span></span>  <span data-ttu-id="6661d-287">看起来有 2 个 jpg 文件超过 2000 KB，这比必要的文件大。</span><span class="sxs-lookup"><span data-stu-id="6661d-287">It looks like 2 of the jpg files are over 2000 KB, which is bigger than necessary.</span></span>  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png" alt-text="Details about the properly size images opportunity" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png":::
       Details about the properly size images opportunity  
    :::image-end:::  
    -->
    
1.  <span data-ttu-id="6661d-288">返回到编辑器选项卡中，打开 `src/model.js` 。</span><span class="sxs-lookup"><span data-stu-id="6661d-288">Back in the editor tab, open `src/model.js`.</span></span>  
1.  <span data-ttu-id="6661d-289">用 `const dir = 'small'` 取代 `const dir = 'big'`。</span><span class="sxs-lookup"><span data-stu-id="6661d-289">Replace `const dir = 'big'` with `const dir = 'small'`.</span></span>  <span data-ttu-id="6661d-290">此目录包含已调整大小的相同图像的副本。</span><span class="sxs-lookup"><span data-stu-id="6661d-290">This directory contains copies of the same images which have been resized.</span></span>  
1.  <span data-ttu-id="6661d-291">再次审核页面以显示更改如何影响加载性能。</span><span class="sxs-lookup"><span data-stu-id="6661d-291">Audit the page again to display how the change affects load performance.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-compression-small-images-audits-performance.msft.png" alt-text="调整图像大小后的审核报告" lightbox="../media/speed-glitch-compression-small-images-audits-performance.msft.png":::
       <span data-ttu-id="6661d-293">调整图像大小后的审核报告</span><span class="sxs-lookup"><span data-stu-id="6661d-293">An Audits report after resizing images</span></span>  
    :::image-end:::  
    
<span data-ttu-id="6661d-294">更改显示仅对总体性能分数产生细微影响。</span><span class="sxs-lookup"><span data-stu-id="6661d-294">The change displays only has a minor affect on the overall performance score.</span></span>  <span data-ttu-id="6661d-295">但是，该分数没有明确显示的是保存用户的网络数据数量。</span><span class="sxs-lookup"><span data-stu-id="6661d-295">However, one thing that the score does not show clearly is how much network data you are saving your users.</span></span>  <span data-ttu-id="6661d-296">旧照片的总大小约为 5.3 MB，而现在只有大约 0.18 MB。</span><span class="sxs-lookup"><span data-stu-id="6661d-296">The total size of the old photos was around 5.3 megabytes, whereas now it is only about 0.18 megabytes.</span></span>  

#### <a name="resizing-images-in-the-real-world"></a><span data-ttu-id="6661d-297">在现实世界中调整图像大小</span><span class="sxs-lookup"><span data-stu-id="6661d-297">Resizing images in the real world</span></span>  

<span data-ttu-id="6661d-298">对于小型应用，执行一次一次大小调整可能足够好。</span><span class="sxs-lookup"><span data-stu-id="6661d-298">For a small app, doing a one-off resize like this may be good enough.</span></span>  <span data-ttu-id="6661d-299">但对于大型应用，这显然不可缩放。</span><span class="sxs-lookup"><span data-stu-id="6661d-299">But for a large app, this obviously is not scalable.</span></span>  <span data-ttu-id="6661d-300">下面是在大型应用中管理映像的一些策略：</span><span class="sxs-lookup"><span data-stu-id="6661d-300">Here are some strategies for managing images in large apps:</span></span>  

*   <span data-ttu-id="6661d-301">在生成过程中调整图像大小。</span><span class="sxs-lookup"><span data-stu-id="6661d-301">Resize images during your build process.</span></span>  
*   <span data-ttu-id="6661d-302">在生成过程中创建每个图像的多个大小，然后在 `srcset` 代码中使用。</span><span class="sxs-lookup"><span data-stu-id="6661d-302">Create multiple sizes of each image during the build process and then use `srcset` in your code.</span></span>  <span data-ttu-id="6661d-303">在运行时，浏览器会负责选择最适合设备的大小。</span><span class="sxs-lookup"><span data-stu-id="6661d-303">At runtime, the browser takes care of choosing which size is best for the device.</span></span>  
    <!--Navigate to [Relative-sized images][relative].  -->
    
<!--[relative]: /web/fundamentals/design-and-ux/responsive/images#relative_sized_images  -->  

*   <span data-ttu-id="6661d-304">使用图像 CDN，可以在请求时动态调整图像大小。</span><span class="sxs-lookup"><span data-stu-id="6661d-304">Use an image CDN that lets you dynamically resize an image when you request it.</span></span>  
*   <span data-ttu-id="6661d-305">至少，优化每个图像。</span><span class="sxs-lookup"><span data-stu-id="6661d-305">At the very least, optimize each image.</span></span>  <span data-ttu-id="6661d-306">这可能会节省大量资金。</span><span class="sxs-lookup"><span data-stu-id="6661d-306">This may create huge savings.</span></span>  
  <span data-ttu-id="6661d-307">优化是当你通过减小图像文件大小的特殊程序运行图像时。</span><span class="sxs-lookup"><span data-stu-id="6661d-307">Optimization is when you run an image through a special program that reduces the size of the image file.</span></span>  <span data-ttu-id="6661d-308">有关更多提示，请导航到["基本图像优化"。][EssentialImageOptimization]</span><span class="sxs-lookup"><span data-stu-id="6661d-308">For more tips, navigate to [Essential Image Optimization][EssentialImageOptimization].</span></span>  
    
### <a name="eliminate-render-blocking-resources"></a><span data-ttu-id="6661d-309">消除呈现阻止资源</span><span class="sxs-lookup"><span data-stu-id="6661d-309">Eliminate render-blocking resources</span></span>  

<span data-ttu-id="6661d-310">你的最新报告显示，消除呈现阻止资源现在是最大机会。</span><span class="sxs-lookup"><span data-stu-id="6661d-310">Your latest report says that eliminating render-blocking resources is now the biggest opportunity.</span></span>  

<span data-ttu-id="6661d-311">呈现阻止资源是一个外部 JavaScript 或 CSS 文件，浏览器必须在显示页面之前下载、分析和运行该文件。</span><span class="sxs-lookup"><span data-stu-id="6661d-311">A render-blocking resource is an external JavaScript or CSS file that the browser must download, parse, and run before it displays the page.</span></span>  <span data-ttu-id="6661d-312">目标是仅运行正确显示页面所需的核心 CSS 和 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="6661d-312">The goal is to only run the core CSS and JavaScript code that is required to display the page properly.</span></span>  

<span data-ttu-id="6661d-313">然后，第一个任务是查找无需在页面加载时运行的代码。</span><span class="sxs-lookup"><span data-stu-id="6661d-313">The first task, then, is to find code that you do not need to run on page load.</span></span>  

1.  <span data-ttu-id="6661d-314">选择 **"消除呈现阻止资源** "以显示阻止的资源：</span><span class="sxs-lookup"><span data-stu-id="6661d-314">Choose **Eliminate render-blocking resources** to display the resources that are blocking:</span></span>  
    `lodash.js` <span data-ttu-id="6661d-315">和 `jquery.js` 。</span><span class="sxs-lookup"><span data-stu-id="6661d-315">and `jquery.js`.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png" alt-text="有关消除呈现阻止资源机会详细信息" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png":::
       <span data-ttu-id="6661d-317">有关消除 **呈现阻止资源机会** 详细信息</span><span class="sxs-lookup"><span data-stu-id="6661d-317">More information about the **Eliminate render-blocking resources** opportunity</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-318">选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 打开命令菜单，开始键入 `Coverage` ，然后选择显示**覆盖**。</span><span class="sxs-lookup"><span data-stu-id="6661d-318">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, start typing `Coverage`, and then choose **Show Coverage**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png" alt-text="从审核面板中打开命令菜单" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png":::
       <span data-ttu-id="6661d-320">从审核面板中打开 **命令** 菜单</span><span class="sxs-lookup"><span data-stu-id="6661d-320">Open the Command Menu from the **Audits** panel</span></span>  
    :::image-end:::  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png" alt-text="覆盖工具" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png":::
       <span data-ttu-id="6661d-322">覆盖**工具**</span><span class="sxs-lookup"><span data-stu-id="6661d-322">The **Coverage** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-323">Choose **Refresh** \ (![ Refresh ](../media/reload-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="6661d-323">Choose **Refresh** \(![Refresh](../media/reload-icon.msft.png)\).</span></span>  <span data-ttu-id="6661d-324">覆盖 **工具** 概述了在加载页面时 、 和 `bundle.js` `jquery.js` `lodash.js` 中运行的代码量。</span><span class="sxs-lookup"><span data-stu-id="6661d-324">The **Coverage** tool provides an overview of how much of the code in `bundle.js`, `jquery.js`, and `lodash.js` runs while the page loads.</span></span>  <span data-ttu-id="6661d-325">在下图中，分别不使用大约 76% 和 30% 的 jQuery 和 Lodash 文件。</span><span class="sxs-lookup"><span data-stu-id="6661d-325">In the figure after the following, about 76% and 30% of the jQuery and Lodash files are not used, respectively.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png" alt-text="覆盖报告" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png":::
       <span data-ttu-id="6661d-327">覆盖报告</span><span class="sxs-lookup"><span data-stu-id="6661d-327">The Coverage report</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-328">选择 \*\* "jquery.js\*\* 行"</span><span class="sxs-lookup"><span data-stu-id="6661d-328">Choose the **jquery.js** row.</span></span>  <span data-ttu-id="6661d-329">DevTools 在"源"面板中打开文件。</span><span class="sxs-lookup"><span data-stu-id="6661d-329">DevTools opens the file in the Sources panel.</span></span>  <span data-ttu-id="6661d-330">如果代码行旁边有一个蓝色条，将运行该代码行。</span><span class="sxs-lookup"><span data-stu-id="6661d-330">A line of code ran if it has a blue bar next to it.</span></span>  <span data-ttu-id="6661d-331">红色条表示它未运行，并且绝对不需要页面加载。</span><span class="sxs-lookup"><span data-stu-id="6661d-331">A red bar means it was not run, and is definitely not needed on page load.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png" alt-text="在"源"面板中查看 jQuery 文件" lightbox="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png":::
       <span data-ttu-id="6661d-333">在"源"面板 **中查看** jQuery 文件</span><span class="sxs-lookup"><span data-stu-id="6661d-333">Viewing the jQuery file in the **Sources** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-334">滚动一下 jQuery 代码。</span><span class="sxs-lookup"><span data-stu-id="6661d-334">Scroll through the jQuery code a bit.</span></span>  <span data-ttu-id="6661d-335">某些"运行"行实际上只是注释。</span><span class="sxs-lookup"><span data-stu-id="6661d-335">Some of the lines that get "run" are actually just comments.</span></span>  <span data-ttu-id="6661d-336">通过去除注释的微型程序运行此代码是减小此文件大小的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="6661d-336">Running this code through a minifier that strips comments is another way to reduce the size of this file.</span></span>  

<span data-ttu-id="6661d-337">简而言之，当你使用自己的代码时，覆盖工具可帮助你分\*\*\*\* 行分析代码，并仅提供页面加载所需的代码。</span><span class="sxs-lookup"><span data-stu-id="6661d-337">In short, when you are working with your own code, the **Coverage** tool helps you analyze your code, line-by-line, and only ship the code that is needed for page load.</span></span>  

<span data-ttu-id="6661d-338">是否 `jquery.js` `lodash.js` 甚至需要 和 文件才能加载页面？</span><span class="sxs-lookup"><span data-stu-id="6661d-338">Are the `jquery.js` and `lodash.js` files even needed to load the page?</span></span>  <span data-ttu-id="6661d-339">请求 **阻止** 工具显示资源不可用时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="6661d-339">The **Request blocking** tool displays what happens when resources are not available.</span></span>  

1.  <span data-ttu-id="6661d-340">选择" **网络"** 工具。</span><span class="sxs-lookup"><span data-stu-id="6661d-340">Choose the **Network** tool.</span></span>  
1.  <span data-ttu-id="6661d-341">选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 以再次打开命令菜单。</span><span class="sxs-lookup"><span data-stu-id="6661d-341">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu again.</span></span>  
1.  <span data-ttu-id="6661d-342">开始键入， `blocking` 然后选择"显示**请求阻止"。**</span><span class="sxs-lookup"><span data-stu-id="6661d-342">Start typing `blocking` and then choose **Show Request Blocking**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png" alt-text="请求阻止工具" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png":::
       <span data-ttu-id="6661d-344">请求 **阻止** 工具</span><span class="sxs-lookup"><span data-stu-id="6661d-344">The **Request blocking** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-345">Choose **Add Pattern** \ (Add Pattern ![ ](../media/add-pattern-icon.msft.png) \) ， type ， and then select to `/libs/*` `Enter` confirm.</span><span class="sxs-lookup"><span data-stu-id="6661d-345">Choose **Add Pattern** \(![Add Pattern](../media/add-pattern-icon.msft.png)\), type `/libs/*`, and then select `Enter` to confirm.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png" alt-text="添加模式以阻止对 libs 目录的任何请求" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png":::
       <span data-ttu-id="6661d-347">添加模式以阻止对目录的任何 `libs` 请求</span><span class="sxs-lookup"><span data-stu-id="6661d-347">Add a pattern to block any request to the `libs` directory</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-348">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="6661d-348">Refresh the page.</span></span>  <span data-ttu-id="6661d-349">jQuery 和 Lodash 请求为红色，这意味着请求已被阻止。</span><span class="sxs-lookup"><span data-stu-id="6661d-349">The jQuery and Lodash requests are red, meaning that the requests were blocked.</span></span>   <span data-ttu-id="6661d-350">页面仍加载并且是交互式的，因此看起来这些资源并不是所需的！</span><span class="sxs-lookup"><span data-stu-id="6661d-350">The page still loads and is interactive, so it looks like these resources are not needed whatsoever!</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png" alt-text=""网络"面板显示请求已被阻止" lightbox="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png":::
       <span data-ttu-id="6661d-352">**Network**工具显示请求已被阻止</span><span class="sxs-lookup"><span data-stu-id="6661d-352">The **Network** tool shows that the requests have been blocked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-353">Choose **Remove all patterns** \ (![ Remove all patterns ](../media/remove-icon.msft.png) \) to delete the blocking `/libs/*` pattern.</span><span class="sxs-lookup"><span data-stu-id="6661d-353">Choose **Remove all patterns** \(![Remove all patterns](../media/remove-icon.msft.png)\) to delete the `/libs/*` blocking pattern.</span></span>  
    
<span data-ttu-id="6661d-354">通常，请求 **阻止** 工具可用于模拟页面在任何给定资源不可用时的行为方式。</span><span class="sxs-lookup"><span data-stu-id="6661d-354">In general, the **Request blocking** tool is useful for simulating how your page behaves when any given resource is not available.</span></span>  

<span data-ttu-id="6661d-355">现在，从代码中删除对这些文件的引用并再次审核页面：</span><span class="sxs-lookup"><span data-stu-id="6661d-355">Now, remove the references to these files from the code and audit the page again:</span></span>  

1.  <span data-ttu-id="6661d-356">返回到编辑器选项卡中，打开 `template.html` 。</span><span class="sxs-lookup"><span data-stu-id="6661d-356">Back in the editor tab, open `template.html`.</span></span>  
1.  <span data-ttu-id="6661d-357">删除 `<script src="/libs/lodash.js">` 和 `<script src="/libs/jquery.js"></script>`。</span><span class="sxs-lookup"><span data-stu-id="6661d-357">Delete `<script src="/libs/lodash.js">` and `<script src="/libs/jquery.js"></script>`.</span></span>  
1.  <span data-ttu-id="6661d-358">等待网站重新构建和重新部署。</span><span class="sxs-lookup"><span data-stu-id="6661d-358">Wait for the site to re-build and re-deploy.</span></span>  
1.  <span data-ttu-id="6661d-359">从审核工具 **再次审核** 页面。</span><span class="sxs-lookup"><span data-stu-id="6661d-359">Audit the page again from the **Audits** tool.</span></span>  <span data-ttu-id="6661d-360">总体分数应再次提高。</span><span class="sxs-lookup"><span data-stu-id="6661d-360">Your overall score should have improved again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png" alt-text="删除呈现阻止资源后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png":::
       <span data-ttu-id="6661d-362">删除 **呈现** 阻止资源后的审核报告</span><span class="sxs-lookup"><span data-stu-id="6661d-362">An **Audits** report after removing the render-blocking resources</span></span>  
    :::image-end:::  
    
#### <a name="optimizing-the-critical-rendering-path-in-the-real-world"></a><span data-ttu-id="6661d-363">优化实际中的关键呈现路径</span><span class="sxs-lookup"><span data-stu-id="6661d-363">Optimizing the Critical Rendering Path in the real-world</span></span>  

<span data-ttu-id="6661d-364">关键 **呈现路径** 是指加载页面所需的代码。</span><span class="sxs-lookup"><span data-stu-id="6661d-364">The **Critical Rendering Path** refers to the code that you need to load a page.</span></span>  <span data-ttu-id="6661d-365">通常，只需在页面加载期间交付关键代码，然后延迟加载其他所有内容，加快页面加载速度。</span><span class="sxs-lookup"><span data-stu-id="6661d-365">In general, speed up page load by only shipping critical code during the page load, and then lazy-loading everything else.</span></span>  

<!--[CRP]: /web/fundamentals/performance/critical-rendering-path/  -->  

*   <span data-ttu-id="6661d-366">你不太可能能够找到能够彻底删除的脚本，但你可能会发现许多脚本不需要在页面加载期间请求，而是可能会异步请求。</span><span class="sxs-lookup"><span data-stu-id="6661d-366">It is unlikely that you are able to find scripts that you are able to remove outright, but you may find many scripts that you do not need to request during the page load, and instead may be requested asynchronously.</span></span>  <!--Navigate to [Using async or defer][async].  -->  
*   <span data-ttu-id="6661d-367">如果你使用的是框架，请检查其是否具有生产模式。</span><span class="sxs-lookup"><span data-stu-id="6661d-367">If you are using a framework, check if it has a production mode.</span></span>  <span data-ttu-id="6661d-368">此模式可能使用树状 [抖动][WebpackTreeShaking] 等功能，以消除阻止关键呈现的不必要的代码。</span><span class="sxs-lookup"><span data-stu-id="6661d-368">This mode may use a feature such as [tree shaking][WebpackTreeShaking] in order to eliminate unnecessary code that is blocking the critical render.</span></span>  
    
<!--[async]: /web/fundamentals/performance/optimizing-content-efficiency/loading-third-party-javascript/#use_async_or_defer  -->  

### <a name="do-less-main-thread-work"></a><span data-ttu-id="6661d-369">减少主线程工作</span><span class="sxs-lookup"><span data-stu-id="6661d-369">Do less main thread work</span></span>  

<span data-ttu-id="6661d-370">你的最新报告在"机会"部分显示了一些小的潜在节省，但如果你在"诊断"部分向下看，它看起来最大的瓶颈是主线程活动太多。</span><span class="sxs-lookup"><span data-stu-id="6661d-370">Your latest report shows some minor potential savings in the Opportunities section, but if you look down in the Diagnostics section, it looks like the biggest bottleneck is too much main thread activity.</span></span>  

<span data-ttu-id="6661d-371">主线程是浏览器执行显示页面所需的大部分工作（如分析和运行 HTML、CSS 和 JavaScript）的地方。</span><span class="sxs-lookup"><span data-stu-id="6661d-371">The main thread is where the browser does most of the work needed to display a page, such as parsing and running HTML, CSS, and JavaScript.</span></span>  

<span data-ttu-id="6661d-372">目标是使用性能面板来分析主线程在页面加载时所执行的工作，并找到延迟或删除不必要的工作的方法。</span><span class="sxs-lookup"><span data-stu-id="6661d-372">The goal is to use the Performance panel to analyze what work the main thread is doing while the page loads, and find ways to defer or remove unnecessary work.</span></span>  

1.  <span data-ttu-id="6661d-373">选择 **"性能"** 工具。</span><span class="sxs-lookup"><span data-stu-id="6661d-373">Choose the **Performance** tool.</span></span>  
1.  <span data-ttu-id="6661d-374">Choose **Capture Settings** \ (Capture Settings ![ ](../media/capture-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="6661d-374">Choose **Capture Settings** \(![Capture Settings](../media/capture-icon.msft.png)\).</span></span>  
1.  <span data-ttu-id="6661d-375">将**网络设置为\*\*\*\*慢速 3G，\*\*\*\*将 CPU**速度设置为**慢 6 倍**。</span><span class="sxs-lookup"><span data-stu-id="6661d-375">Set **Network** to **Slow 3G** and **CPU** to **6x slowdown**.</span></span>  <span data-ttu-id="6661d-376">移动设备通常比笔记本电脑或台式机具有更多的硬件约束，因此这些设置让你可以像使用功能更少的设备一样体验页面负载。</span><span class="sxs-lookup"><span data-stu-id="6661d-376">Mobile devices typically have more hardware constraints than laptops or desktops, so these settings let you experience the page load as if you were using a less powerful device.</span></span>  
1.  <span data-ttu-id="6661d-377">Choose **Refresh** \ (![ Refresh ](../media/reload-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="6661d-377">Choose **Refresh** \(![Refresh](../media/reload-icon.msft.png)\).</span></span>  <span data-ttu-id="6661d-378">DevTools 刷新页面，然后生成为加载页面而执行的所有工作的可视化。</span><span class="sxs-lookup"><span data-stu-id="6661d-378">DevTools refreshes the page and then produces a visualization of all the work performed in order to load the page.</span></span>  <span data-ttu-id="6661d-379">此可视化 **称为跟踪**。</span><span class="sxs-lookup"><span data-stu-id="6661d-379">This visualization is referred to as the **trace**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png" alt-text="页面加载的性能工具跟踪" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png":::
       <span data-ttu-id="6661d-381">**页面**加载的性能工具跟踪</span><span class="sxs-lookup"><span data-stu-id="6661d-381">The **Performance** tool trace of the page load</span></span>  
    :::image-end:::  
    
<span data-ttu-id="6661d-382">跟踪按时间顺序显示从左到右的活动。</span><span class="sxs-lookup"><span data-stu-id="6661d-382">The trace shows activity chronologically, from left to right.</span></span>  <span data-ttu-id="6661d-383">顶部的 FPS、CPU 和 NET 图表概述了每秒帧数、CPU 活动和网络活动。</span><span class="sxs-lookup"><span data-stu-id="6661d-383">The FPS, CPU, and NET charts at the top give you an overview of frames per second, CPU activity, and network activity.</span></span>  <span data-ttu-id="6661d-384">接下来，CPU 完全忙于脚本活动，图中突出显示了黄色块。</span><span class="sxs-lookup"><span data-stu-id="6661d-384">The block of yellow highlighted in the figure after the next, the CPU was completely busy with scripting activity.</span></span>  <span data-ttu-id="6661d-385">通过减少 JavaScript 工作，您可以加快页面加载速度。</span><span class="sxs-lookup"><span data-stu-id="6661d-385">This is a clue that you may be able to speed up page load by doing less JavaScript work.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png" alt-text="跟踪的概述部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png":::
   <span data-ttu-id="6661d-387">跟踪的概述部分</span><span class="sxs-lookup"><span data-stu-id="6661d-387">The Overview section of the trace</span></span>  
:::image-end:::  

<span data-ttu-id="6661d-388">调查跟踪以查找减少 JavaScript 工作的方法：</span><span class="sxs-lookup"><span data-stu-id="6661d-388">Investigate the trace to find ways to do less JavaScript work:</span></span>  

1.  <span data-ttu-id="6661d-389">选择 **"计时"** 部分以展开它。</span><span class="sxs-lookup"><span data-stu-id="6661d-389">Choose the **Timings** section to expand it.</span></span>  <span data-ttu-id="6661d-390">根据 React 中可能有一组计时度量，[][MDNUserTimingApi]看起来 Tony 的应用正在使用 React 的开发模式。</span><span class="sxs-lookup"><span data-stu-id="6661d-390">Based on the fact that there may be a bunch of [Timings][MDNUserTimingApi] measures from React, it seems like Tony's app is using the development mode of React.</span></span>  <span data-ttu-id="6661d-391">切换到 React 的生产模式可能会获得一些简单的性能收益。</span><span class="sxs-lookup"><span data-stu-id="6661d-391">Switching to the production mode of React may yield some easy performance wins.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png" alt-text=""计时"部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png":::
       <span data-ttu-id="6661d-393">" **计时"** 部分</span><span class="sxs-lookup"><span data-stu-id="6661d-393">The **Timings** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-394">再次 **选择"** 计时"以折叠该部分。</span><span class="sxs-lookup"><span data-stu-id="6661d-394">Choose **Timings** again to collapse that section.</span></span>  
1.  <span data-ttu-id="6661d-395">浏览 **"主"** 部分。</span><span class="sxs-lookup"><span data-stu-id="6661d-395">Browse the **Main** section.</span></span>  <span data-ttu-id="6661d-396">本部分显示主线程活动按时间顺序排列的日志，从左到右。</span><span class="sxs-lookup"><span data-stu-id="6661d-396">This section shows a chronological log of main thread activity, from left to right.</span></span>  <span data-ttu-id="6661d-397">从上到 (y 轴) 显示事件发生的原因。</span><span class="sxs-lookup"><span data-stu-id="6661d-397">The y-axis (top to bottom) shows why events occurred.</span></span>  <span data-ttu-id="6661d-398">例如，在下面的图块中，事件导致函数运行，导致运行，导致运行， `Evaluate Script` `(anonymous)` `(anonymous)` `__webpack__require__` 等等。</span><span class="sxs-lookup"><span data-stu-id="6661d-398">For example, in the figyre after the following, the `Evaluate Script` event caused the `(anonymous)` function to run, which caused `(anonymous)` to run, which caused `__webpack__require__` to run, and so on.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png" alt-text="主要部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png":::
       <span data-ttu-id="6661d-400">**主要**部分</span><span class="sxs-lookup"><span data-stu-id="6661d-400">The **Main** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6661d-401">向下滚动到"主" **部分** 的底部。</span><span class="sxs-lookup"><span data-stu-id="6661d-401">Scroll down to the bottom of the **Main** section.</span></span>  <span data-ttu-id="6661d-402">使用框架时，大部分上面的活动由框架导致，该框架通常无法控制。</span><span class="sxs-lookup"><span data-stu-id="6661d-402">When you use a framework, most of the upper activity is caused by the framework, which is usually out of your control.</span></span>  <span data-ttu-id="6661d-403">你的应用引起的活动通常位于底部。</span><span class="sxs-lookup"><span data-stu-id="6661d-403">The activity caused by your app is usually at the bottom.</span></span>  <span data-ttu-id="6661d-404">在此应用中，似乎名为 的函数导致对函数 `App` 提出大量 `mineBitcoin` 请求。</span><span class="sxs-lookup"><span data-stu-id="6661d-404">In this app, it seems like a function named `App` is causing a lot of requests to a `mineBitcoin` function.</span></span>  <span data-ttu-id="6661d-405">这听起来 Tony 可能正在使用其粉丝的设备来挖掘加密货币...</span><span class="sxs-lookup"><span data-stu-id="6661d-405">It sounds like Tony may be using the devices of his fans to mine cryptocurrency...</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png" alt-text="将鼠标悬停在 mineBitcoin 活动上" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png":::
       <span data-ttu-id="6661d-407">将鼠标悬停在 `mineBitcoin` 活动上</span><span class="sxs-lookup"><span data-stu-id="6661d-407">Hover on the `mineBitcoin` activity</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="6661d-408">尽管你的框架提出的请求通常无法控制，但有时你可能以导致框架运行效率低下的方式构建你的应用。</span><span class="sxs-lookup"><span data-stu-id="6661d-408">Although the requests that your framework makes are usually out of your control, sometimes you may structure your app in a way that causes the framework to run inefficiently.</span></span>  <span data-ttu-id="6661d-409">通过重构应用来高效地使用框架，可以减少主线程工作。</span><span class="sxs-lookup"><span data-stu-id="6661d-409">Restructuring your app to use the framework efficiently is a way to do less main thread work.</span></span>  <span data-ttu-id="6661d-410">但是，这需要深入了解框架的工作方式，以及你在自己的代码中进行哪种更改，以便更有效地使用该框架。</span><span class="sxs-lookup"><span data-stu-id="6661d-410">However, this requires a deep understanding of how your framework works, and what kind of changes you make in your own code in order to use the framework more efficiently.</span></span>  
    
1.  <span data-ttu-id="6661d-411">展开" **底部向上"** 部分。</span><span class="sxs-lookup"><span data-stu-id="6661d-411">Expand the **Bottom-Up** section.</span></span>  <span data-ttu-id="6661d-412">此选项卡将分解哪些活动所花时间最多。</span><span class="sxs-lookup"><span data-stu-id="6661d-412">This tab breaks down what activities took up the most time.</span></span>  <span data-ttu-id="6661d-413">如果未在"主Bottom-Up中显示任何内容，请选择"主 **"部分** 的标签。</span><span class="sxs-lookup"><span data-stu-id="6661d-413">If nothing is displayed in the Bottom-Up section, choose the label for **Main** section.</span></span>  <span data-ttu-id="6661d-414">" **底部向上** "部分只显示当前选择的任何活动或活动组的信息。</span><span class="sxs-lookup"><span data-stu-id="6661d-414">The **Bottom-Up** section only shows information for whatever activity, or group of activity, you have currently selected.</span></span>  <span data-ttu-id="6661d-415">例如，如果选择其中一个活动，则"底部向上"部分将只 `mineBitcoin` 显示该活动的信息。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6661d-415">For example, if you chose one of the `mineBitcoin` activities, the **Bottom-Up** section is only going to show information for that one activity.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png" alt-text=""Bottom-Up"选项卡" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png":::
       <span data-ttu-id="6661d-417">" **下向上"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="6661d-417">The **Bottom-Up** tab</span></span>  
    :::image-end:::  
    
<span data-ttu-id="6661d-418">" **自时间** "列显示每个活动直接花费的时间。</span><span class="sxs-lookup"><span data-stu-id="6661d-418">The **Self Time** column shows you how much time was spent directly in each activity.</span></span>  <span data-ttu-id="6661d-419">例如，在下图中，大约 63% 的主线程时间用于 `mineBitcoin` 函数。</span><span class="sxs-lookup"><span data-stu-id="6661d-419">For example, in the following figure, about 63% of main thread time was spent on the `mineBitcoin` function.</span></span>  

<span data-ttu-id="6661d-420">查看使用生产模式和减少 JavaScript 活动是否可能加快页面加载的时间。</span><span class="sxs-lookup"><span data-stu-id="6661d-420">Time to review whether using production mode and reducing JavaScript activity may speed up the page load.</span></span>  <span data-ttu-id="6661d-421">从生产模式开始：</span><span class="sxs-lookup"><span data-stu-id="6661d-421">Start with production mode:</span></span>  

1.  <span data-ttu-id="6661d-422">在编辑器选项卡中，打开 `webpack.config.js` 。</span><span class="sxs-lookup"><span data-stu-id="6661d-422">In the editor tab, open `webpack.config.js`.</span></span>  
1.  <span data-ttu-id="6661d-423">将 `"mode":"development"` 更改为 `"mode":"production"`。</span><span class="sxs-lookup"><span data-stu-id="6661d-423">Change `"mode":"development"` to `"mode":"production"`.</span></span>  
1.  <span data-ttu-id="6661d-424">等待新内部版本部署。</span><span class="sxs-lookup"><span data-stu-id="6661d-424">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="6661d-425">再次审核页面。</span><span class="sxs-lookup"><span data-stu-id="6661d-425">Audit the page again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png" alt-text="配置 Webpack 以使用生产模式后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png":::
       <span data-ttu-id="6661d-427">配置 Webpack 以使用生产模式后的审核报告</span><span class="sxs-lookup"><span data-stu-id="6661d-427">An Audits report after configuring webpack to use production mode</span></span>  
    :::image-end:::  
    
<span data-ttu-id="6661d-428">通过删除 对 的请求减少 JavaScript 活动 `mineBitcoin` ：</span><span class="sxs-lookup"><span data-stu-id="6661d-428">Reduce JavaScript activity by removing the request to `mineBitcoin`:</span></span>  

1.  <span data-ttu-id="6661d-429">在编辑器选项卡中，打开 `src/App.jsx` 。</span><span class="sxs-lookup"><span data-stu-id="6661d-429">In the editor tab, open `src/App.jsx`.</span></span>  
1.  <span data-ttu-id="6661d-430">在 中注释掉 `this.mineBitcoin(1500)` 对 `constructor` 的请求。</span><span class="sxs-lookup"><span data-stu-id="6661d-430">Comment out the request to `this.mineBitcoin(1500)` in the `constructor`.</span></span>  
1.  <span data-ttu-id="6661d-431">等待新内部版本部署。</span><span class="sxs-lookup"><span data-stu-id="6661d-431">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="6661d-432">再次审核页面。</span><span class="sxs-lookup"><span data-stu-id="6661d-432">Audit the page again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png" alt-text="删除不必要的 JavaScript 工作后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png":::
       <span data-ttu-id="6661d-434">删除不必要的 JavaScript 工作后的审核报告</span><span class="sxs-lookup"><span data-stu-id="6661d-434">An Audits report after removing unnecessary JavaScript work</span></span>  
    :::image-end:::  
    
<span data-ttu-id="6661d-435">看起来最后一次更改导致性能大幅提升！</span><span class="sxs-lookup"><span data-stu-id="6661d-435">Looks like that last change caused a massive jump in performance!</span></span>  

> [!NOTE]
> <span data-ttu-id="6661d-436">本节简要介绍了性能面板。</span><span class="sxs-lookup"><span data-stu-id="6661d-436">This section provided a rather brief introduction to the Performance panel.</span></span>  <span data-ttu-id="6661d-437">若要了解有关如何分析页面性能的信息，请导航到"[性能分析参考"。][DevtoolsEvaluatePerformanceReference]</span><span class="sxs-lookup"><span data-stu-id="6661d-437">To learn more about how to analyze page performance, navigate to [Performance Analysis Reference][DevtoolsEvaluatePerformanceReference].</span></span>  

<!--todo: add section when available -->  

#### <a name="doing-less-main-thread-work-in-the-real-world"></a><span data-ttu-id="6661d-438">在现实世界中减少主线程工作</span><span class="sxs-lookup"><span data-stu-id="6661d-438">Doing less main thread work in the real world</span></span>  

<span data-ttu-id="6661d-439">通常， **性能** 工具是了解您的网站在加载时执行哪些活动以及查找删除不必要活动的方法的最常用方法。</span><span class="sxs-lookup"><span data-stu-id="6661d-439">In general, the **Performance** tool is the most common way to understand what activity your site does as it loads, and find ways to remove unnecessary activity.</span></span>  

<span data-ttu-id="6661d-440">如果你更喜欢更像 的方法，则用户计时 API 使你能够任意标记应用生命周期的某些阶段，以便跟踪每个阶段所花 `console.log()` 的时间。 [][MDNUserTimingApi]</span><span class="sxs-lookup"><span data-stu-id="6661d-440">If you prefer an approach that feels more like `console.log()`, the [User Timing API][MDNUserTimingApi] enables you to arbitrarily mark up certain phases of your app lifecycle, in order to track how long each of those phases takes.</span></span>  

## <a name="summary"></a><span data-ttu-id="6661d-441">摘要</span><span class="sxs-lookup"><span data-stu-id="6661d-441">Summary</span></span>  

*   <span data-ttu-id="6661d-442">无论何时开始优化网站的负载性能，始终从审核开始。</span><span class="sxs-lookup"><span data-stu-id="6661d-442">Whenever you set out to optimize the load performance of a site, always start with an audit.</span></span>  <span data-ttu-id="6661d-443">审核建立基线，并为你提供有关如何改进的提示。</span><span class="sxs-lookup"><span data-stu-id="6661d-443">The audit establishes a baseline, and gives you tips on how to improve.</span></span>  
*   <span data-ttu-id="6661d-444">一次进行一次更改，并审核每次更改后的网页，以显示独立更改对性能的影响。</span><span class="sxs-lookup"><span data-stu-id="6661d-444">Make one change at a time, and audit the webpage after each change in order to display how that isolated change affects performance.</span></span>  

<!--
## Next steps  

*   Run audits on your own site!  If you need help interpreting your report, or finding ways to improve your load performance, check out [Feedback](#feedback) for ways to get help from the DevTools community.  Stack Overflow, the mailing list, or Twitter are probably best for these types of questions.  
*   Please leave [feedback](#feedback) on this tutorial.  I really do use the data to make better tutorials for you.  
-->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="6661d-445">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="6661d-445">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsEvaluatePerformanceReference]: ../evaluate-performance/reference.md "性能分析参考|Microsoft Docs"  

[CourseraIntroductionWebDevelopmentClass]: https://www.coursera.org/learn/web-development#syllabus "Web 开发类简介|Coursera"  

[EssentialImageOptimization]: https://images.guide "基本映像优化"  

[MDNContentEncodingDirectives]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Encoding#Directives "指令 - 内容编码|MDN"  
[MDNUserTimingApi]: https://developer.mozilla.org/docs/Web/API/User_Timing_API "用户计时 API |MDN"  

[WebpackTreeShaking]: https://webpack.js.org/guides/tree-shaking "树状|webpack"  

> [!NOTE]
> <span data-ttu-id="6661d-452">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="6661d-452">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6661d-453">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/speed/get-started)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="6661d-453">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/speed/get-started) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="6661d-455">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="6661d-455">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
