---
description: 了解如何使用 Microsoft Edge 开发人员工具找到加快网站加载速度的方法。
title: 使用 Microsoft Edge 开发人员工具优化网站速度
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 75c9df5d86ce994cebfda882a0adfa2664b6ec30
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
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

# <a name="optimize-website-speed-with-microsoft-edge-devtools"></a><span data-ttu-id="9993b-104">使用 Microsoft Edge 开发人员工具优化网站速度</span><span class="sxs-lookup"><span data-stu-id="9993b-104">Optimize website speed with Microsoft Edge DevTools</span></span>  

## <a name="goal-of-tutorial"></a><span data-ttu-id="9993b-105">教程目标</span><span class="sxs-lookup"><span data-stu-id="9993b-105">Goal of tutorial</span></span>  

<span data-ttu-id="9993b-106">本教程将指导你如何使用 Microsoft Edge 开发人员工具找到加快网站加载速度的方法。</span><span class="sxs-lookup"><span data-stu-id="9993b-106">This tutorial teaches you how to use Microsoft Edge DevTools to find ways to make your websites load faster.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="9993b-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="9993b-107">Prerequisites</span></span>  

*   <span data-ttu-id="9993b-108">你应具备基本的 Web 开发体验，类似此[Web 开发类简介][CourseraIntroductionWebDevelopmentClass]中所教授的内容。</span><span class="sxs-lookup"><span data-stu-id="9993b-108">You should have basic web development experience, similar to what is taught in this [Introduction to Web Development class][CourseraIntroductionWebDevelopmentClass].</span></span>  
*   <span data-ttu-id="9993b-109">你无需了解加载性能的任何信息。</span><span class="sxs-lookup"><span data-stu-id="9993b-109">You do not need to know anything about load performance.</span></span>  <span data-ttu-id="9993b-110">本教程中将帮助你了解。</span><span class="sxs-lookup"><span data-stu-id="9993b-110">You learn about it in this tutorial.</span></span>  

## <a name="introduction"></a><span data-ttu-id="9993b-111">简介</span><span class="sxs-lookup"><span data-stu-id="9993b-111">Introduction</span></span>  

<span data-ttu-id="9993b-112">这是 Tony。</span><span class="sxs-lookup"><span data-stu-id="9993b-112">This is Tony.</span></span>  <span data-ttu-id="9993b-113">Tony 在猫界很有名。</span><span class="sxs-lookup"><span data-stu-id="9993b-113">Tony is very famous in cat society.</span></span>  <span data-ttu-id="9993b-114">他生成了一个网站，让粉丝能够了解他最喜爱的食物。</span><span class="sxs-lookup"><span data-stu-id="9993b-114">He has built a website so that his fans are able to learn about his favorite foods.</span></span>  <span data-ttu-id="9993b-115">虽然粉丝们很喜欢这个网站，但 Tony 不断听到有关网站加载缓慢的抱怨。</span><span class="sxs-lookup"><span data-stu-id="9993b-115">His fans love the site, but Tony keeps hearing complaints that the site loads slowly.</span></span>  <span data-ttu-id="9993b-116">Tony 要求你帮忙加快站点速度。</span><span class="sxs-lookup"><span data-stu-id="9993b-116">Tony has asked you to help him speed the site up.</span></span>  

:::image type="complex" source="../media/speed-tony.msft.png" alt-text="Tony 猫" lightbox="../media/speed-tony.msft.png":::
   <span data-ttu-id="9993b-118">Tony 猫</span><span class="sxs-lookup"><span data-stu-id="9993b-118">Tony the cat</span></span>  
:::image-end:::  

## <a name="step-1-audit-the-site"></a><span data-ttu-id="9993b-119">步骤 1：审核站点</span><span class="sxs-lookup"><span data-stu-id="9993b-119">Step 1: Audit the site</span></span>  

<span data-ttu-id="9993b-120">无论何时开始改进站点的加载性能，**始终都从审核开始**。</span><span class="sxs-lookup"><span data-stu-id="9993b-120">Whenever you set out to improve the load performance of a site, **always start with an audit**.</span></span>  
<span data-ttu-id="9993b-121">审核包含 2 个重要功能：</span><span class="sxs-lookup"><span data-stu-id="9993b-121">The audit has 2 important functions:</span></span>  

*   <span data-ttu-id="9993b-122">创建**基线**，便于参照并测量后续更改。</span><span class="sxs-lookup"><span data-stu-id="9993b-122">It creates a **baseline** for you to measure subsequent changes against.</span></span>  
*   <span data-ttu-id="9993b-123">提供有关哪些更改最具影响的**可操作提示**。</span><span class="sxs-lookup"><span data-stu-id="9993b-123">It gives you **actionable tips** on what changes have the most impact.</span></span>  
    
### <a name="set-up"></a><span data-ttu-id="9993b-124">设置</span><span class="sxs-lookup"><span data-stu-id="9993b-124">Set up</span></span>  

<span data-ttu-id="9993b-125">首先，你必须设置站点，便于之后进行更改。</span><span class="sxs-lookup"><span data-stu-id="9993b-125">First, you must set up the site so that you are able to make changes to it later.</span></span>  

1.  <span data-ttu-id="9993b-126">[打开站点的源代码](https://glitch.com/edit/#!/tony)。</span><span class="sxs-lookup"><span data-stu-id="9993b-126">[Open the source code for the site](https://glitch.com/edit/#!/tony).</span></span>  <span data-ttu-id="9993b-127">此选项卡称为**编辑器选项卡**。</span><span class="sxs-lookup"><span data-stu-id="9993b-127">This tab is referred to as the **editor tab**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js.msft.png" alt-text="编辑器选项卡" lightbox="../media/speed-glitch-tony-server-js.msft.png":::
       <span data-ttu-id="9993b-129">**编辑器选项卡**</span><span class="sxs-lookup"><span data-stu-id="9993b-129">The **editor tab**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-130">选择 **tony**。</span><span class="sxs-lookup"><span data-stu-id="9993b-130">Choose **tony**.</span></span>  <span data-ttu-id="9993b-131">将显示菜单。</span><span class="sxs-lookup"><span data-stu-id="9993b-131">A menu appears.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js-remix-project.msft.png" alt-text="选择 tony 后显示的菜单" lightbox="../media/speed-glitch-tony-server-js-remix-project.msft.png":::
       <span data-ttu-id="9993b-133">选择**tony**后显示的菜单</span><span class="sxs-lookup"><span data-stu-id="9993b-133">The menu that appears after choosing **tony**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-134">选择**合成项目**。</span><span class="sxs-lookup"><span data-stu-id="9993b-134">Choose **Remix Project**.</span></span>  <span data-ttu-id="9993b-135">项目名称从**tony** 更改为随机生成的名称。</span><span class="sxs-lookup"><span data-stu-id="9993b-135">The name of the project changes from **tony** to some randomly-generated name.</span></span>  <span data-ttu-id="9993b-136">现在，你拥有了自己的可编辑代码副本。</span><span class="sxs-lookup"><span data-stu-id="9993b-136">You now have your own editable copy of the code.</span></span>  <span data-ttu-id="9993b-137">稍后，你可以对此代码进行更改。</span><span class="sxs-lookup"><span data-stu-id="9993b-137">Later on, you may make changes to this code.</span></span>  
1.  <span data-ttu-id="9993b-138">选择**显示**，然后选择**在新窗口中**。</span><span class="sxs-lookup"><span data-stu-id="9993b-138">Choose **Show** and choose **In a New Window**.</span></span>  <span data-ttu-id="9993b-139">演示将在新选项卡中打开。 此选项卡称为**演示选项卡**。 站点加载可能需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="9993b-139">The demo opens in a new tab.  This tab is be referred to as the **demo tab**.  It may take a while for the site to load.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live.msft.png" alt-text="演示选项卡" lightbox="../media/speed-glitch-tony-show-live.msft.png":::
       <span data-ttu-id="9993b-141">演示选项卡</span><span class="sxs-lookup"><span data-stu-id="9993b-141">The demo tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-142">选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\)。</span><span class="sxs-lookup"><span data-stu-id="9993b-142">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="9993b-143">Microsoft Edge 开发人员工具将在演示旁边打开。</span><span class="sxs-lookup"><span data-stu-id="9993b-143">Microsoft Edge DevTools opens up alongside the demo.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live-console.msft.png" alt-text="开发人员工具和演示" lightbox="../media/speed-glitch-tony-show-live-console.msft.png":::
       <span data-ttu-id="9993b-145">开发人员工具和演示</span><span class="sxs-lookup"><span data-stu-id="9993b-145">DevTools and the demo</span></span>  
    :::image-end:::  
    
<span data-ttu-id="9993b-146">对于本教程中的其余屏幕截图，开发人员工具显示在单独窗口中。</span><span class="sxs-lookup"><span data-stu-id="9993b-146">For the rest of the screenshots in this tutorial, DevTools is shown in a separate window.</span></span>  <span data-ttu-id="9993b-147">选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\)，打开“命令菜单”，键入`Undock` ，然后选择**移除进单独窗口**。</span><span class="sxs-lookup"><span data-stu-id="9993b-147">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, typing `Undock`, and then selecting **Undock into separate window**.</span></span>  

:::image type="complex" source="../media/speed-console.msft.png" alt-text="移除的开发人员工具" lightbox="../media/speed-console.msft.png":::
   <span data-ttu-id="9993b-149">移除的开发人员工具</span><span class="sxs-lookup"><span data-stu-id="9993b-149">Undocked DevTools</span></span>  
:::image-end:::  

### <a name="establish-a-baseline"></a><span data-ttu-id="9993b-150">建立基线</span><span class="sxs-lookup"><span data-stu-id="9993b-150">Establish a baseline</span></span>  

<span data-ttu-id="9993b-151">基线是指在改进性能之前有关站点执行情况的记录。</span><span class="sxs-lookup"><span data-stu-id="9993b-151">The baseline is a record of how the site performed before you made any performance improvements.</span></span>  

1.  <span data-ttu-id="9993b-152">选择**审核**工具。</span><span class="sxs-lookup"><span data-stu-id="9993b-152">Choose the **Audits** tool.</span></span>  <span data-ttu-id="9993b-153">它可能隐藏在**更多面板** \(![More Panels](../media/more-panels-icon.msft.png)\) 按钮的后面。</span><span class="sxs-lookup"><span data-stu-id="9993b-153">It may be hidden behind the **More Panels** \(![More Panels](../media/more-panels-icon.msft.png)\) button.</span></span>  <span data-ttu-id="9993b-154">此面板包含"灯塔"，因为支持“审核”面板的项目名为**灯塔**。</span><span class="sxs-lookup"><span data-stu-id="9993b-154">There is a Lighthouse on this panel because the project that powers the Audits panel is named **Lighthouse**.</span></span>  
    
    [!INCLUDE [audits-panel-note](../includes/audits-panel-note.md)]  
    
    :::image type="complex" source="../media/speed-audits-performance.msft.png" alt-text="“审核”工具" lightbox="../media/speed-audits-performance.msft.png":::
       <span data-ttu-id="9993b-156">**审核**工具</span><span class="sxs-lookup"><span data-stu-id="9993b-156">The **Audits** tool</span></span>  
    :::image-end:::  
    
    <!--todo: add link to Lighthouse when section is available  -->  
    <!-- /web/tools/lighthouse  -->  
    
1.  <span data-ttu-id="9993b-157">将审核配置设置与上图中的设置相匹配。</span><span class="sxs-lookup"><span data-stu-id="9993b-157">Match your audit configuration settings to those in the previous figure.</span></span>  <span data-ttu-id="9993b-158">以下是不同选项的说明：</span><span class="sxs-lookup"><span data-stu-id="9993b-158">Here is an explanation of the different options:</span></span>  
    
    *   <span data-ttu-id="9993b-159">**设备**。</span><span class="sxs-lookup"><span data-stu-id="9993b-159">**Device**.</span></span>  <span data-ttu-id="9993b-160">设置为**移动**，更改用户代理字符串并模拟移动视口。</span><span class="sxs-lookup"><span data-stu-id="9993b-160">Set to **Mobile** changes the user agent string and simulates a mobile viewport.</span></span>  <span data-ttu-id="9993b-161">设置为**桌面**，几乎可以关闭**移动**更改。</span><span class="sxs-lookup"><span data-stu-id="9993b-161">Set to **Desktop** pretty much just turns off the **Mobile** changes.</span></span>  
    *   <span data-ttu-id="9993b-162">**审核**。</span><span class="sxs-lookup"><span data-stu-id="9993b-162">**Audits**.</span></span>  <span data-ttu-id="9993b-163">关闭类别可以防止**审核**面板运行这些审核，并在报告中相应排除。</span><span class="sxs-lookup"><span data-stu-id="9993b-163">Turn off a category to prevent the **Audits** panel from running those audits, and excludes those audits from your report.</span></span>  <span data-ttu-id="9993b-164">如果希望显示提供的建议类型，请保留其他类别为"打开"。</span><span class="sxs-lookup"><span data-stu-id="9993b-164">Leave the other categories Turned on, if you want to display the types of recommendations that are provided.</span></span>  <span data-ttu-id="9993b-165">关闭类别可以略微加快审核流程。</span><span class="sxs-lookup"><span data-stu-id="9993b-165">Turn off categories to slightly speed up the auditing process.</span></span>  
    *   <span data-ttu-id="9993b-166">**限制**。</span><span class="sxs-lookup"><span data-stu-id="9993b-166">**Throttling**.</span></span>  <span data-ttu-id="9993b-167">设置为**模拟慢速 4G、4x CPU 减速**，模拟在移动设备上浏览的典型条件。</span><span class="sxs-lookup"><span data-stu-id="9993b-167">Set to **Simulated Slow 4G, 4x CPU Slowdown** simulates the typical conditions of browsing on a mobile device.</span></span>  <span data-ttu-id="9993b-168">命名为"模拟"是因为“审核”面板在审核流程中实际上并未进行限制。</span><span class="sxs-lookup"><span data-stu-id="9993b-168">It is named "simulated" because the Audits panel does not actually throttle during the auditing process.</span></span>  <span data-ttu-id="9993b-169">相反，它只是推断移动条件下加载页面花费的时间。</span><span class="sxs-lookup"><span data-stu-id="9993b-169">Instead, it just extrapolates how long the page takes to load under mobile conditions.</span></span>  <span data-ttu-id="9993b-170">另一方面，**应用...** 设置实际上会限制 CPU 和网络，折衷了较长的审核流程。</span><span class="sxs-lookup"><span data-stu-id="9993b-170">The **Applied...** setting, on the other hand, actually throttles your CPU and network, with the tradeoff of a longer auditing process.</span></span>  
    *   <span data-ttu-id="9993b-171">**清除存储**。</span><span class="sxs-lookup"><span data-stu-id="9993b-171">**Clear Storage**.</span></span>  <span data-ttu-id="9993b-172">打开复选框，在每次审核前清除与页面相关的所有存储。</span><span class="sxs-lookup"><span data-stu-id="9993b-172">Turn on the checkbox to clear all storage associated with the page before every audit.</span></span>  <span data-ttu-id="9993b-173">如果希望审核站点首次访问者的体验，请保留此设置。</span><span class="sxs-lookup"><span data-stu-id="9993b-173">Leave this setting on if you want to audit how first-time visitors experience your site.</span></span>  <span data-ttu-id="9993b-174">希望重复访问体验时，请关闭此设置。</span><span class="sxs-lookup"><span data-stu-id="9993b-174">Turn off this setting when you want the repeat-visit experience.</span></span>  
    
1.  <span data-ttu-id="9993b-175">选择**运行审核**。</span><span class="sxs-lookup"><span data-stu-id="9993b-175">Choose **Run Audits**.</span></span>  <span data-ttu-id="9993b-176">10 到 30 秒后，**审核**面板将显示站点性能报告。</span><span class="sxs-lookup"><span data-stu-id="9993b-176">After 10 to 30 seconds, the **Audits** panel displays a report of the performance of the site.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png" alt-text="站点性能审核面板报告" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png":::
       <span data-ttu-id="9993b-178">站点性能审核面板报告</span><span class="sxs-lookup"><span data-stu-id="9993b-178">The report for the Audits panel of the performance of the site</span></span>  
    :::image-end:::  
    
#### <a name="handling-report-errors"></a><span data-ttu-id="9993b-179">处理报告错误</span><span class="sxs-lookup"><span data-stu-id="9993b-179">Handling report errors</span></span>  

<span data-ttu-id="9993b-180">如果你曾在“审核”面板报告中收到错误，请尝试从**InPrivate**窗口运行演示选项卡，且不打开其他选项卡。</span><span class="sxs-lookup"><span data-stu-id="9993b-180">If you ever get an error in your Audits panel report, try running the demo tab from an **InPrivate** window with no other tabs open.</span></span>  <span data-ttu-id="9993b-181">这可以确保在干净状态运行 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="9993b-181">This ensures that you are running Microsoft Edge from a clean state.</span></span>  <span data-ttu-id="9993b-182">尤其是，Microsoft Edge 扩展经常会干扰审核流程。</span><span class="sxs-lookup"><span data-stu-id="9993b-182">Microsoft Edge Extensions in particular often interfere with the auditing process.</span></span>  

<!--todo: add screen capture for error in audit -->  
<!--
:::image type="complex" source="../media/speed-.msft.png" alt-text="A report that errored" lightbox="../media/speed-.msft.png":::
   A report that errored  
:::image-end:::  
-->  

### <a name="understand-your-report"></a><span data-ttu-id="9993b-183">了解报告</span><span class="sxs-lookup"><span data-stu-id="9993b-183">Understand your report</span></span>  

<span data-ttu-id="9993b-184">报告顶部的数字是站点的总体性能分数。</span><span class="sxs-lookup"><span data-stu-id="9993b-184">The number at the top of your report is the overall performance score for the site.</span></span>  <span data-ttu-id="9993b-185">稍后，当你对代码进行更改时，显示的数字应上升。</span><span class="sxs-lookup"><span data-stu-id="9993b-185">Later, as you make changes to the code, the number displayed should rise.</span></span>  <span data-ttu-id="9993b-186">分数越高表示性能越好。</span><span class="sxs-lookup"><span data-stu-id="9993b-186">A higher score means better performance.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png" alt-text="总体性能分数" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png":::
   <span data-ttu-id="9993b-188">总体性能分数</span><span class="sxs-lookup"><span data-stu-id="9993b-188">The overall performance score</span></span>  
:::image-end:::  

<span data-ttu-id="9993b-189">**指标**部分提供站点性能的定量测量。</span><span class="sxs-lookup"><span data-stu-id="9993b-189">The **Metrics** section provides quantitative measurements of the performance of the site.</span></span>  <span data-ttu-id="9993b-190">每个指标提供对性能不同方面的见解。</span><span class="sxs-lookup"><span data-stu-id="9993b-190">Each metric provides insight into a different aspect of the performance.</span></span>  <span data-ttu-id="9993b-191">例如，**首次内容绘制**会告知内容首次绘制到屏幕的时间，这是用户感知页面加载的重要里程碑，而**可交互时间**则会标记页面似乎准备就绪，足以处理用户交互的时间点。</span><span class="sxs-lookup"><span data-stu-id="9993b-191">For example, **First Contentful Paint** tells you when content is first painted to the screen, which is an important milestone in the user's perception of the page load, whereas **Time To Interactive** marks the point at which the page appears ready enough to handle user interactions.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png" alt-text=""指标"部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png":::
   <span data-ttu-id="9993b-193">**指标**部分</span><span class="sxs-lookup"><span data-stu-id="9993b-193">The **Metrics** section</span></span>  
:::image-end:::  

<span data-ttu-id="9993b-194">选择下图中突出显示的切换按钮，显示每个指标的说明，然后选择 **了解更多信息**，阅读相关文档。</span><span class="sxs-lookup"><span data-stu-id="9993b-194">Choose the highlighted toggle button in the following figure to display a description for each metric, and choose **Learn More** to read documentation about it.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png" alt-text="选择突出显示的切换按钮，展开"指标"项" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png":::
   <span data-ttu-id="9993b-196">选择突出显示的切换按钮，展开"指标"项</span><span class="sxs-lookup"><span data-stu-id="9993b-196">Choose the highlighted toggle button to expand the Metrics items</span></span>  
:::image-end:::  

<span data-ttu-id="9993b-197">以下"指标"是页面加载外观屏幕截图的集合。</span><span class="sxs-lookup"><span data-stu-id="9993b-197">Below Metrics is a collection of screenshots that show you how the page looked as it loaded.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="页面加载外观屏幕截图" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   <span data-ttu-id="9993b-199">页面加载外观屏幕截图</span><span class="sxs-lookup"><span data-stu-id="9993b-199">Screenshots of how the page looked while loading</span></span>  
:::image-end:::  

<span data-ttu-id="9993b-200">**机会**部分提供如何改进此特定页面加载性能的特定提示。</span><span class="sxs-lookup"><span data-stu-id="9993b-200">The **Opportunities** section provides specific tips on how to improve the load performance of this specific page.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text=""机会"部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   <span data-ttu-id="9993b-202">**机会**部分</span><span class="sxs-lookup"><span data-stu-id="9993b-202">The **Opportunities** section</span></span>  
:::image-end:::  

<span data-ttu-id="9993b-203">选择某个机会，了解更多相关信息。</span><span class="sxs-lookup"><span data-stu-id="9993b-203">Choose an opportunity to learn more about it.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png" alt-text="消除阻止渲染资源机会" lightbox="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png":::
   <span data-ttu-id="9993b-205">**消除阻止渲染资源**机会</span><span class="sxs-lookup"><span data-stu-id="9993b-205">**Eliminate render-blocking resources** opportunity</span></span>  
:::image-end:::  

<span data-ttu-id="9993b-206">选择 **了解更多信息**，显示说明机会为什么重要的文档，以及如何修复机会的特定建议。</span><span class="sxs-lookup"><span data-stu-id="9993b-206">Choose **Learn More** to display documentation about why an opportunity is important, and specific recommendations on how to fix it.</span></span>  

:::image type="complex" source="../media/speed-web-dev-performance-audits.msft.png" alt-text="消除阻止渲染资源机会的文档" lightbox="../media/speed-web-dev-performance-audits.msft.png":::
   <span data-ttu-id="9993b-208">消除**阻止渲染资源机会**的文档</span><span class="sxs-lookup"><span data-stu-id="9993b-208">Documentation for the **Eliminate render-blocking resources** opportunity</span></span>  
:::image-end:::  

<span data-ttu-id="9993b-209">**诊断**部分提供影响页面加载时间的因素的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9993b-209">The **Diagnostics** section provides more information about factors that contribute to the load time of the page.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png" alt-text="“诊断”部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png":::
   <span data-ttu-id="9993b-211">**诊断**部分</span><span class="sxs-lookup"><span data-stu-id="9993b-211">The **Diagnostics** section</span></span>  
:::image-end:::  

<span data-ttu-id="9993b-212">**通过审核**部分显示站点正确执行的内容。</span><span class="sxs-lookup"><span data-stu-id="9993b-212">The **Passed Audits** section shows you what the site is doing correctly.</span></span>  <span data-ttu-id="9993b-213">选择并展开此部分。</span><span class="sxs-lookup"><span data-stu-id="9993b-213">Choose to expand the section.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png" alt-text=""通过审核"部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png":::
   <span data-ttu-id="9993b-215">**通过审核** 部分</span><span class="sxs-lookup"><span data-stu-id="9993b-215">The **Passed Audits** section</span></span>  
:::image-end:::  

## <a name="step-2-experiment"></a><span data-ttu-id="9993b-216">步骤 2：试验</span><span class="sxs-lookup"><span data-stu-id="9993b-216">Step 2: Experiment</span></span>  

<span data-ttu-id="9993b-217">审核报告中的"机会"部分提供如何改进页面性能的提示。</span><span class="sxs-lookup"><span data-stu-id="9993b-217">The Opportunities section of your audit report gives you tips on how to improve the performance of the page.</span></span>  <span data-ttu-id="9993b-218">在此部分，你将对基本代码实施建议性更改，并在每次更改后审核站点，从而测量更改对站点速度的影响。</span><span class="sxs-lookup"><span data-stu-id="9993b-218">In this section, you implement the recommended changes to the codebase, auditing the site after each change to measure how it affects site speed.</span></span>  

### <a name="enable-text-compression"></a><span data-ttu-id="9993b-219">启用文本压缩</span><span class="sxs-lookup"><span data-stu-id="9993b-219">Enable text compression</span></span>  

<span data-ttu-id="9993b-220">你的报告表明，避免大量网络负载是改进页面性能的一个首要机会。</span><span class="sxs-lookup"><span data-stu-id="9993b-220">Your report says that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="9993b-221">启用文本压缩是改进页面性能的机会。</span><span class="sxs-lookup"><span data-stu-id="9993b-221">Enabling text compression is an opportunity to improve the performance of the page.</span></span>  

<span data-ttu-id="9993b-222">文本压缩是指在网络上发送文本文件之前，减少或压缩文本文件的大小。</span><span class="sxs-lookup"><span data-stu-id="9993b-222">Text compression is when you reduce, or compress, the size of a text file before sending it over the network.</span></span>  <span data-ttu-id="9993b-223">类似于如何在发送目录前进行存档，从而减少目录大小。</span><span class="sxs-lookup"><span data-stu-id="9993b-223">Similar to how you may archive a directory before sending it to reduce the size.</span></span>  

<span data-ttu-id="9993b-224">在启用压缩前，以下是手动检查文本资源是否压缩的几种方法。</span><span class="sxs-lookup"><span data-stu-id="9993b-224">Before you enable compression, here are a couple of ways to manually check whether text resources are compressed.</span></span>  

1.  <span data-ttu-id="9993b-225">选择**网络**工具。</span><span class="sxs-lookup"><span data-stu-id="9993b-225">Choose the **Network** tool.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network.msft.png" alt-text="“网络”面板" lightbox="../media/speed-glitch-tony-remix-network.msft.png":::
       <span data-ttu-id="9993b-227">**网络**工具</span><span class="sxs-lookup"><span data-stu-id="9993b-227">The **Network** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-228">选择**网络设置**图标。</span><span class="sxs-lookup"><span data-stu-id="9993b-228">Choose the **Network setting** icon.</span></span>  
1.  <span data-ttu-id="9993b-229">选择**使用大请求行**复选框。</span><span class="sxs-lookup"><span data-stu-id="9993b-229">Choose the **Use Large Request Rows** checkbox.</span></span>  <span data-ttu-id="9993b-230">网络请求表中行的高度将增加。</span><span class="sxs-lookup"><span data-stu-id="9993b-230">The height of the rows in the table of network requests increases.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png" alt-text="网络请求表中的大行" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png":::
       <span data-ttu-id="9993b-232">网络请求表中的大行</span><span class="sxs-lookup"><span data-stu-id="9993b-232">Large rows in the network requests table</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-233">如果网络请求表中的**大小**未显示，请选择表头 > **大小**。</span><span class="sxs-lookup"><span data-stu-id="9993b-233">If the **Size** column in the table of network requests is not displayed, choose the table header > **Size**.</span></span>  

<span data-ttu-id="9993b-234">每个**大小** 单元格将显示两个值。</span><span class="sxs-lookup"><span data-stu-id="9993b-234">Each **Size** cell shows two values.</span></span>  <span data-ttu-id="9993b-235">顶部值是已下载资源的大小。</span><span class="sxs-lookup"><span data-stu-id="9993b-235">The top value is the size of the downloaded resource.</span></span>  
<span data-ttu-id="9993b-236">底部值是未压缩资源的大小。</span><span class="sxs-lookup"><span data-stu-id="9993b-236">The bottom value is the size of the uncompressed resource.</span></span>  <span data-ttu-id="9993b-237">如果这两个值相同，则表示在网络中发送资源时，资源未被压缩。</span><span class="sxs-lookup"><span data-stu-id="9993b-237">If the two values are the same, then the resource is not being compressed when it is sent over the network.</span></span>  <span data-ttu-id="9993b-238">例如，在上图中，`bundle.js`顶部和底部的值为`1.2 MB`和`1.2 MB`。</span><span class="sxs-lookup"><span data-stu-id="9993b-238">For example, in the previous figure, the top and bottom values for `bundle.js` are `1.2 MB` and `1.2 MB`.</span></span>  

<span data-ttu-id="9993b-239">通过检查资源的 HTTP 标头检查压缩：</span><span class="sxs-lookup"><span data-stu-id="9993b-239">Check for compression by inspecting the HTTP headers of a resource:</span></span>  

1.  <span data-ttu-id="9993b-240">选择`bundle.js`。</span><span class="sxs-lookup"><span data-stu-id="9993b-240">Choose `bundle.js`.</span></span>  
1.  <span data-ttu-id="9993b-241">选择**标头**面板。</span><span class="sxs-lookup"><span data-stu-id="9993b-241">Choose the **Headers** panel.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png" alt-text=""标头"面板" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png":::
       <span data-ttu-id="9993b-243">**标头**面板</span><span class="sxs-lookup"><span data-stu-id="9993b-243">The **Headers** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-244">在**响应标头**部分搜索`content-encoding` 标头。</span><span class="sxs-lookup"><span data-stu-id="9993b-244">Search the **Response Headers** section for a `content-encoding` header.</span></span>  <span data-ttu-id="9993b-245">`content-encoding`标头不显示，意味着`bundle.js`未被压缩。</span><span class="sxs-lookup"><span data-stu-id="9993b-245">A `content-encoding` heading is not displayed, meaning that `bundle.js` was not compressed.</span></span>  <span data-ttu-id="9993b-246">压缩资源时，此标头通常设置为 `gzip`、`deflate`或`br`。</span><span class="sxs-lookup"><span data-stu-id="9993b-246">When a resource is compressed, this header is usually set to `gzip`, `deflate`, or `br`.</span></span>  <span data-ttu-id="9993b-247">有关这些值的说明，请导航到[指令][MDNContentEncodingDirectives]。</span><span class="sxs-lookup"><span data-stu-id="9993b-247">For an explanation of the values, navigate to [Directives][MDNContentEncodingDirectives].</span></span>  

<span data-ttu-id="9993b-248">说明已经足够。</span><span class="sxs-lookup"><span data-stu-id="9993b-248">Enough with the explanations.</span></span>  <span data-ttu-id="9993b-249">现在开始进行更改。</span><span class="sxs-lookup"><span data-stu-id="9993b-249">Time to make some changes.</span></span>  <span data-ttu-id="9993b-250">通过添加几行代码启用文本压缩：</span><span class="sxs-lookup"><span data-stu-id="9993b-250">Enable text compression by adding a couple of lines of code:</span></span>  

1.  <span data-ttu-id="9993b-251">在编辑器选项卡中，选择**server.js**。</span><span class="sxs-lookup"><span data-stu-id="9993b-251">In the editor tab, choose **server.js**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js.msft.png" alt-text="编辑 server.js" lightbox="../media/speed-glitch-tony-remix-server-js.msft.png":::
       <span data-ttu-id="9993b-253">编辑</span><span class="sxs-lookup"><span data-stu-id="9993b-253">Edit</span></span> `server.js`  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-254">将以下代码添加到**server.js**。</span><span class="sxs-lookup"><span data-stu-id="9993b-254">Add the following code to **server.js**.</span></span>  <span data-ttu-id="9993b-255">请确保将 `app.use(express.static('build'))`置于`app.use(compression())`之前。</span><span class="sxs-lookup"><span data-stu-id="9993b-255">Make sure to put `app.use(compression())` before `app.use(express.static('build'))`.</span></span>  

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
    > <span data-ttu-id="9993b-256">通常，你必须通过`npm i -S compression`等方式安装`compression`包，但此操作已为你完成。</span><span class="sxs-lookup"><span data-stu-id="9993b-256">Usually, you have to install the `compression` package via something like `npm i -S compression`, but this has already been done for you.</span></span>  
    
1.  <span data-ttu-id="9993b-257">等待 Glitch 部署站点的新内部版本。</span><span class="sxs-lookup"><span data-stu-id="9993b-257">Wait for Glitch to deploy the new build of the site.</span></span>  <span data-ttu-id="9993b-258">**工具**旁边的奇特动画意味着正在重新生成和部署站点。</span><span class="sxs-lookup"><span data-stu-id="9993b-258">The fancy animation next to **Tools** means that the site is getting rebuilt and redeployed.</span></span>  <span data-ttu-id="9993b-259">当**工具**旁边的动画消失时， 更改已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="9993b-259">The change is ready when the animation next to **Tools** goes away.</span></span>  <span data-ttu-id="9993b-260">选择**显示**，然后再次选择**在新窗口中**。</span><span class="sxs-lookup"><span data-stu-id="9993b-260">Choose **Show** and choose **In a New Window** again.</span></span>  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js-edited.msft.png" alt-text="The animation that indicates that the site is getting built" lightbox="../media/speed-glitch-tony-remix-server-js-edited.msft.png":::
       The animation that indicates that the site is getting built  
    :::image-end:::  
    -->  
    
<span data-ttu-id="9993b-261">按照你之前了解的工作流，手动检查压缩是否工作：</span><span class="sxs-lookup"><span data-stu-id="9993b-261">Use the workflows that you learned earlier to manually check that the compression is working:</span></span>  

1.  <span data-ttu-id="9993b-262">返回到演示选项卡并刷新页面。</span><span class="sxs-lookup"><span data-stu-id="9993b-262">Go back to the demo tab and refresh the page.</span></span>  <span data-ttu-id="9993b-263">现在，**大小**列应显示`bundle.js`等文本资源的 2 个不同值。</span><span class="sxs-lookup"><span data-stu-id="9993b-263">The **Size** column should now show 2 different values for text resources like `bundle.js`.</span></span>  <span data-ttu-id="9993b-264">在下图中，`bundle.js``256 KB`的顶部值是在网络中发送的文件的大小，而`1.2 MB`的底部值是未压缩文件的大小。</span><span class="sxs-lookup"><span data-stu-id="9993b-264">In the figure after the following, the top value of `256 KB` for `bundle.js` is the size of the file that was sent over the network, and the bottom value of `1.2 MB` is the uncompressed file size.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-main.msft.png" alt-text="现在，大小列显示文本资源的 2 个不同值" lightbox="../media/speed-glitch-tony-remix-network-main.msft.png":::
       <span data-ttu-id="9993b-266">现在，**大小**列显示文本资源的 2 个不同值</span><span class="sxs-lookup"><span data-stu-id="9993b-266">The **Size** column now shows 2 different values for text resources</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-267">现在，`bundle.js`的**响应标头**部分应包含`content-encoding: gzip`标头。</span><span class="sxs-lookup"><span data-stu-id="9993b-267">The **Response Headers** section for `bundle.js` should now include a `content-encoding: gzip` header.</span></span>
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png" alt-text="现在，“响应标头"部分包含 content-encoding 标头" lightbox="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png":::
       <span data-ttu-id="9993b-269">现在，**响应标头**部分包含 content-encoding 标头</span><span class="sxs-lookup"><span data-stu-id="9993b-269">The **Response Headers** section now contains a content-encoding header</span></span>  
    :::image-end:::  
    
<span data-ttu-id="9993b-270">再次审核页面，测量文本压缩对页面加载性能的影响类型：</span><span class="sxs-lookup"><span data-stu-id="9993b-270">Audit the page again to measure what kind of impact text compression has on the load performance of the page:</span></span>  

1.  <span data-ttu-id="9993b-271">选择**审核**工具。</span><span class="sxs-lookup"><span data-stu-id="9993b-271">Choose the **Audits** tool.</span></span>  
1.  <span data-ttu-id="9993b-272">选择**执行审核** \(![Perform an audit](../media/perform-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="9993b-272">Choose **Perform an audit** \(![Perform an audit](../media/perform-icon.msft.png)\).</span></span>  
1.  <span data-ttu-id="9993b-273">保留设置与之前相同。</span><span class="sxs-lookup"><span data-stu-id="9993b-273">Leave the settings the same as before.</span></span>  
1.  <span data-ttu-id="9993b-274">选择**运行审核**。</span><span class="sxs-lookup"><span data-stu-id="9993b-274">Choose **Run audit**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png" alt-text="启用文本压缩后的“审核”报告" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png":::
       <span data-ttu-id="9993b-276">启用文本压缩后的“审核”报告</span><span class="sxs-lookup"><span data-stu-id="9993b-276">An Audits report after enabling text compression</span></span>  
    :::image-end:::  
    
<!--  Woohoo!  That looks like progress.  -->  <span data-ttu-id="9993b-277">总体性能分数应已提高，这意味着站点速度加快。</span><span class="sxs-lookup"><span data-stu-id="9993b-277">Your overall performance score should have increased, meaning that the site is getting faster.</span></span>  

#### <a name="text-compression-in-the-real-world"></a><span data-ttu-id="9993b-278">现实世界中的文本压缩</span><span class="sxs-lookup"><span data-stu-id="9993b-278">Text compression in the real world</span></span>  

<span data-ttu-id="9993b-279">多数服务器确实包含此类简单修复，用于启用压缩！</span><span class="sxs-lookup"><span data-stu-id="9993b-279">Most servers really do have simple fixes like this for enabling compression!</span></span>  <span data-ttu-id="9993b-280">只需搜索如何配置所使用的服务器压缩文本即可。</span><span class="sxs-lookup"><span data-stu-id="9993b-280">Just do a search on how to configure whatever server you use to compress text.</span></span>  

### <a name="resize-images"></a><span data-ttu-id="9993b-281">调整图像大小</span><span class="sxs-lookup"><span data-stu-id="9993b-281">Resize images</span></span>  

<span data-ttu-id="9993b-282">你的报告表明，避免大量网络负载是改进页面性能的一个首要机会。</span><span class="sxs-lookup"><span data-stu-id="9993b-282">Your report indicates that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="9993b-283">调整图像大小有助于减少网络负载的大小。</span><span class="sxs-lookup"><span data-stu-id="9993b-283">Resizing images helps reduce the size of the network payload.</span></span>  <span data-ttu-id="9993b-284">如果用户在宽度为 500 像素的移动设备上查看图像，则发送宽度为 1500 像素的图像就豪无意义。</span><span class="sxs-lookup"><span data-stu-id="9993b-284">If your user is viewing your images on a mobile device screen that is 500-pixels-wide, there is really no point in sending a 1500-pixel-wide image.</span></span>  <span data-ttu-id="9993b-285">理想情况下，最多发送宽度为 500 像素的图像。</span><span class="sxs-lookup"><span data-stu-id="9993b-285">Ideally, you send a 500-pixel-wide image, at most.</span></span>  

1.  <span data-ttu-id="9993b-286">在你的报告中，选择 **避免大量网络负载**，显示应调整大小的图像。</span><span class="sxs-lookup"><span data-stu-id="9993b-286">In your report, choose **Avoid enormous network payloads** to display which images should be resized.</span></span>  <span data-ttu-id="9993b-287">似乎有 2 个 jpg 文件超过 2000 KB，超出所需大小。</span><span class="sxs-lookup"><span data-stu-id="9993b-287">It looks like 2 of the jpg files are over 2000 KB, which is bigger than necessary.</span></span>  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png" alt-text="Details about the properly size images opportunity" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png":::
       Details about the properly size images opportunity  
    :::image-end:::  
    -->
    
1.  <span data-ttu-id="9993b-288">返回到编辑器选项卡，打开`src/model.js`。</span><span class="sxs-lookup"><span data-stu-id="9993b-288">Back in the editor tab, open `src/model.js`.</span></span>  
1.  <span data-ttu-id="9993b-289">将`const dir = 'big'`替换为`const dir = 'small'`。</span><span class="sxs-lookup"><span data-stu-id="9993b-289">Replace `const dir = 'big'` with `const dir = 'small'`.</span></span>  <span data-ttu-id="9993b-290">此目录包含已调整大小的相同图像的副本。</span><span class="sxs-lookup"><span data-stu-id="9993b-290">This directory contains copies of the same images which have been resized.</span></span>  
1.  <span data-ttu-id="9993b-291">再次审核页面，显示更改对加载性能的影响。</span><span class="sxs-lookup"><span data-stu-id="9993b-291">Audit the page again to display how the change affects load performance.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-compression-small-images-audits-performance.msft.png" alt-text="调整图像大小后的“审核”报告" lightbox="../media/speed-glitch-compression-small-images-audits-performance.msft.png":::
       <span data-ttu-id="9993b-293">调整图像大小后的“审核”报告</span><span class="sxs-lookup"><span data-stu-id="9993b-293">An Audits report after resizing images</span></span>  
    :::image-end:::  
    
<span data-ttu-id="9993b-294">更改显示仅对总体性能分数产生了细微影响。</span><span class="sxs-lookup"><span data-stu-id="9993b-294">The change displays only has a minor affect on the overall performance score.</span></span>  <span data-ttu-id="9993b-295">但是，分数并未明确显示你为用户节省的网络数据量。</span><span class="sxs-lookup"><span data-stu-id="9993b-295">However, one thing that the score does not show clearly is how much network data you are saving your users.</span></span>  <span data-ttu-id="9993b-296">旧照片的总大小约为 5.3 MB，而现在仅约 0.18 MB。</span><span class="sxs-lookup"><span data-stu-id="9993b-296">The total size of the old photos was around 5.3 megabytes, whereas now it is only about 0.18 megabytes.</span></span>  

#### <a name="resizing-images-in-the-real-world"></a><span data-ttu-id="9993b-297">在现实世界中调整图像大小</span><span class="sxs-lookup"><span data-stu-id="9993b-297">Resizing images in the real world</span></span>  

<span data-ttu-id="9993b-298">对于小型应用，像这样调整一次大小可能就已足够。</span><span class="sxs-lookup"><span data-stu-id="9993b-298">For a small app, doing a one-off resize like this may be good enough.</span></span>  <span data-ttu-id="9993b-299">但对于大型应用，这显然不可扩展。</span><span class="sxs-lookup"><span data-stu-id="9993b-299">But for a large app, this obviously is not scalable.</span></span>  <span data-ttu-id="9993b-300">以下是一些在大型应用中管理图像的策略：</span><span class="sxs-lookup"><span data-stu-id="9993b-300">Here are some strategies for managing images in large apps:</span></span>  

*   <span data-ttu-id="9993b-301">在编译流程中调整图像大小。</span><span class="sxs-lookup"><span data-stu-id="9993b-301">Resize images during your build process.</span></span>  
*   <span data-ttu-id="9993b-302">在编译流程中创建每个图像的多个大小，然后在`srcset`代码中使用。</span><span class="sxs-lookup"><span data-stu-id="9993b-302">Create multiple sizes of each image during the build process and then use `srcset` in your code.</span></span>  <span data-ttu-id="9993b-303">在运行时，浏览器会负责选择最适合设备的大小。</span><span class="sxs-lookup"><span data-stu-id="9993b-303">At runtime, the browser takes care of choosing which size is best for the device.</span></span>  
    <!--Navigate to [Relative-sized images][relative].  -->
    
<!--[relative]: /web/fundamentals/design-and-ux/responsive/images#relative_sized_images  -->  

*   <span data-ttu-id="9993b-304">使用图像 CDN，可以在发出请求时动态调整图像大小。</span><span class="sxs-lookup"><span data-stu-id="9993b-304">Use an image CDN that lets you dynamically resize an image when you request it.</span></span>  
*   <span data-ttu-id="9993b-305">至少，可以优化每个图像。</span><span class="sxs-lookup"><span data-stu-id="9993b-305">At the very least, optimize each image.</span></span>  <span data-ttu-id="9993b-306">这可能会节省大量空间。</span><span class="sxs-lookup"><span data-stu-id="9993b-306">This may create huge savings.</span></span>  
  <span data-ttu-id="9993b-307">优化是指通过减少图像文件大小的特殊程序运行图像。</span><span class="sxs-lookup"><span data-stu-id="9993b-307">Optimization is when you run an image through a special program that reduces the size of the image file.</span></span>  <span data-ttu-id="9993b-308">有关更多提示，请导航到[基本图像优化][EssentialImageOptimization]。</span><span class="sxs-lookup"><span data-stu-id="9993b-308">For more tips, navigate to [Essential Image Optimization][EssentialImageOptimization].</span></span>  
    
### <a name="eliminate-render-blocking-resources"></a><span data-ttu-id="9993b-309">消除阻止渲染资源</span><span class="sxs-lookup"><span data-stu-id="9993b-309">Eliminate render-blocking resources</span></span>  

<span data-ttu-id="9993b-310">你的最新报告显示，现在，消除阻止渲染资源是最大机会。</span><span class="sxs-lookup"><span data-stu-id="9993b-310">Your latest report says that eliminating render-blocking resources is now the biggest opportunity.</span></span>  

<span data-ttu-id="9993b-311">阻止渲染资源是外部 JavaScript 或 CSS 文件，浏览器必须在显示页面前下载、分析和运行此文件。</span><span class="sxs-lookup"><span data-stu-id="9993b-311">A render-blocking resource is an external JavaScript or CSS file that the browser must download, parse, and run before it displays the page.</span></span>  <span data-ttu-id="9993b-312">目标是只运行正确显示页面所需的 CSS 和 JavaScript 核心代码。</span><span class="sxs-lookup"><span data-stu-id="9993b-312">The goal is to only run the core CSS and JavaScript code that is required to display the page properly.</span></span>  

<span data-ttu-id="9993b-313">然后，首个任务是查找页面加载时无需运行的代码。</span><span class="sxs-lookup"><span data-stu-id="9993b-313">The first task, then, is to find code that you do not need to run on page load.</span></span>  

1.  <span data-ttu-id="9993b-314">选择**消除阻止渲染资源**，显示阻止资源：</span><span class="sxs-lookup"><span data-stu-id="9993b-314">Choose **Eliminate render-blocking resources** to display the resources that are blocking:</span></span>  
    `lodash.js` <span data-ttu-id="9993b-315">和`jquery.js`。</span><span class="sxs-lookup"><span data-stu-id="9993b-315">and `jquery.js`.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png" alt-text="有关消除阻止渲染资源机会的详细信息" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png":::
       <span data-ttu-id="9993b-317">有关**消除阻止渲染资源机会**的详细信息</span><span class="sxs-lookup"><span data-stu-id="9993b-317">More information about the **Eliminate render-blocking resources** opportunity</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-318">选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\)， 打开“命令菜单”，开始键入 `Coverage` ，然后选择**显示覆盖**。</span><span class="sxs-lookup"><span data-stu-id="9993b-318">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, start typing `Coverage`, and then choose **Show Coverage**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png" alt-text="从“审核”面板打开“命令菜单”" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png":::
       <span data-ttu-id="9993b-320">从**审核**面板打开“命令菜单”</span><span class="sxs-lookup"><span data-stu-id="9993b-320">Open the Command Menu from the **Audits** panel</span></span>  
    :::image-end:::  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png" alt-text="“覆盖”工具" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png":::
       <span data-ttu-id="9993b-322">**覆盖**工具</span><span class="sxs-lookup"><span data-stu-id="9993b-322">The **Coverage** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-323">选择**刷新** \(![Refresh](../media/reload-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="9993b-323">Choose **Refresh** \(![Refresh](../media/reload-icon.msft.png)\).</span></span>  <span data-ttu-id="9993b-324">**覆盖**工具概述了加载页面时 `bundle.js`、`jquery.js`和`lodash.js`中运行的代码量。</span><span class="sxs-lookup"><span data-stu-id="9993b-324">The **Coverage** tool provides an overview of how much of the code in `bundle.js`, `jquery.js`, and `lodash.js` runs while the page loads.</span></span>  <span data-ttu-id="9993b-325">在下图中，约 76% 的 jQuery 文件和 30% 的 Lodash 文件未被使用。</span><span class="sxs-lookup"><span data-stu-id="9993b-325">In the figure after the following, about 76% and 30% of the jQuery and Lodash files are not used, respectively.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png" alt-text="”覆盖“报告" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png":::
       <span data-ttu-id="9993b-327">”覆盖“报告</span><span class="sxs-lookup"><span data-stu-id="9993b-327">The Coverage report</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-328">选择**jquery.js**行。</span><span class="sxs-lookup"><span data-stu-id="9993b-328">Choose the **jquery.js** row.</span></span>  <span data-ttu-id="9993b-329">在"源"面板中，开发人员工具会打开文件。</span><span class="sxs-lookup"><span data-stu-id="9993b-329">DevTools opens the file in the Sources panel.</span></span>  <span data-ttu-id="9993b-330">如果旁边是蓝色条，则表示运行了代码行。</span><span class="sxs-lookup"><span data-stu-id="9993b-330">A line of code ran if it has a blue bar next to it.</span></span>  <span data-ttu-id="9993b-331">红色条则表示未运行，且页面加载时绝不需要。</span><span class="sxs-lookup"><span data-stu-id="9993b-331">A red bar means it was not run, and is definitely not needed on page load.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png" alt-text="在"源"面板中查看 jQuery 文件" lightbox="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png":::
       <span data-ttu-id="9993b-333">在**源**面板中查看 jQuery 文件</span><span class="sxs-lookup"><span data-stu-id="9993b-333">Viewing the jQuery file in the **Sources** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-334">滚动一下 jQuery 代码。</span><span class="sxs-lookup"><span data-stu-id="9993b-334">Scroll through the jQuery code a bit.</span></span>  <span data-ttu-id="9993b-335">一些获取"运行"的行实际只是备注。</span><span class="sxs-lookup"><span data-stu-id="9993b-335">Some of the lines that get "run" are actually just comments.</span></span>  <span data-ttu-id="9993b-336">通过删除备注的缩小工具运行此代码是减少此文件大小的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="9993b-336">Running this code through a minifier that strips comments is another way to reduce the size of this file.</span></span>  

<span data-ttu-id="9993b-337">简言之，当你使用自己的代码时，**覆盖**工具可以帮助你逐行分析代码，并只交付页面加载所需的代码。</span><span class="sxs-lookup"><span data-stu-id="9993b-337">In short, when you are working with your own code, the **Coverage** tool helps you analyze your code, line-by-line, and only ship the code that is needed for page load.</span></span>  

<span data-ttu-id="9993b-338">加载页面时是否需要`jquery.js`和`lodash.js`文件？</span><span class="sxs-lookup"><span data-stu-id="9993b-338">Are the `jquery.js` and `lodash.js` files even needed to load the page?</span></span>  <span data-ttu-id="9993b-339">**请求阻止**工具显示资源不可用时会发生的状况。</span><span class="sxs-lookup"><span data-stu-id="9993b-339">The **Request blocking** tool displays what happens when resources are not available.</span></span>  

1.  <span data-ttu-id="9993b-340">选择**网络**工具。</span><span class="sxs-lookup"><span data-stu-id="9993b-340">Choose the **Network** tool.</span></span>  
1.  <span data-ttu-id="9993b-341">选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) ，再次打开“命令菜单”。</span><span class="sxs-lookup"><span data-stu-id="9993b-341">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu again.</span></span>  
1.  <span data-ttu-id="9993b-342">开始键入`blocking`，然后选择**显示请求阻止**。</span><span class="sxs-lookup"><span data-stu-id="9993b-342">Start typing `blocking` and then choose **Show Request Blocking**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png" alt-text="“请求”阻止工具" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png":::
       <span data-ttu-id="9993b-344">**请求阻止**工具</span><span class="sxs-lookup"><span data-stu-id="9993b-344">The **Request blocking** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-345">选择**添加模式** \(![Add Pattern](../media/add-pattern-icon.msft.png)\)，键入`/libs/*`，然后选择`Enter`进行确认。</span><span class="sxs-lookup"><span data-stu-id="9993b-345">Choose **Add Pattern** \(![Add Pattern](../media/add-pattern-icon.msft.png)\), type `/libs/*`, and then select `Enter` to confirm.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png" alt-text="添加模式，阻止对库目录的任何请求" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png":::
       <span data-ttu-id="9993b-347">添加模式，阻止对`libs`目录的任何请求</span><span class="sxs-lookup"><span data-stu-id="9993b-347">Add a pattern to block any request to the `libs` directory</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-348">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="9993b-348">Refresh the page.</span></span>  <span data-ttu-id="9993b-349">jQuery 和 Lodash 请求为红色，意味着请求被阻止。</span><span class="sxs-lookup"><span data-stu-id="9993b-349">The jQuery and Lodash requests are red, meaning that the requests were blocked.</span></span>   <span data-ttu-id="9993b-350">页面仍在加载且为交互式，因此似乎根本不需要这些资源！</span><span class="sxs-lookup"><span data-stu-id="9993b-350">The page still loads and is interactive, so it looks like these resources are not needed whatsoever!</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png" alt-text=""网络"面板显示请求已被阻止" lightbox="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png":::
       <span data-ttu-id="9993b-352">**网络**工具显示请求已被阻止</span><span class="sxs-lookup"><span data-stu-id="9993b-352">The **Network** tool shows that the requests have been blocked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-353">选择**删除所有模式** \(![Remove all patterns](../media/remove-icon.msft.png)\)，删除`/libs/*`阻止模式。</span><span class="sxs-lookup"><span data-stu-id="9993b-353">Choose **Remove all patterns** \(![Remove all patterns](../media/remove-icon.msft.png)\) to delete the `/libs/*` blocking pattern.</span></span>  
    
<span data-ttu-id="9993b-354">通常，**请求阻止**工具可以用于模拟页面在给定资源不可用时的行为方式。</span><span class="sxs-lookup"><span data-stu-id="9993b-354">In general, the **Request blocking** tool is useful for simulating how your page behaves when any given resource is not available.</span></span>  

<span data-ttu-id="9993b-355">现在，从代码中删除这些文件的引用并再次审核页面：</span><span class="sxs-lookup"><span data-stu-id="9993b-355">Now, remove the references to these files from the code and audit the page again:</span></span>  

1.  <span data-ttu-id="9993b-356">返回到编辑器选项卡，打开`template.html`。</span><span class="sxs-lookup"><span data-stu-id="9993b-356">Back in the editor tab, open `template.html`.</span></span>  
1.  <span data-ttu-id="9993b-357">删除`<script src="/libs/lodash.js">`和`<script src="/libs/jquery.js"></script>`。</span><span class="sxs-lookup"><span data-stu-id="9993b-357">Delete `<script src="/libs/lodash.js">` and `<script src="/libs/jquery.js"></script>`.</span></span>  
1.  <span data-ttu-id="9993b-358">等待站点重新生成和部署。</span><span class="sxs-lookup"><span data-stu-id="9993b-358">Wait for the site to re-build and re-deploy.</span></span>  
1.  <span data-ttu-id="9993b-359">从**审核**工具再次审核页面。</span><span class="sxs-lookup"><span data-stu-id="9993b-359">Audit the page again from the **Audits** tool.</span></span>  <span data-ttu-id="9993b-360">总体分数应再次提高。</span><span class="sxs-lookup"><span data-stu-id="9993b-360">Your overall score should have improved again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png" alt-text="删除阻止渲染资源后的“审核”报告" lightbox="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png":::
       <span data-ttu-id="9993b-362">删除阻止渲染资源后的**审核**报告</span><span class="sxs-lookup"><span data-stu-id="9993b-362">An **Audits** report after removing the render-blocking resources</span></span>  
    :::image-end:::  
    
#### <a name="optimizing-the-critical-rendering-path-in-the-real-world"></a><span data-ttu-id="9993b-363">在现实世界优化关键渲染路径</span><span class="sxs-lookup"><span data-stu-id="9993b-363">Optimizing the Critical Rendering Path in the real-world</span></span>  

<span data-ttu-id="9993b-364">**关键渲染路径**是指加载页面所需的代码。</span><span class="sxs-lookup"><span data-stu-id="9993b-364">The **Critical Rendering Path** refers to the code that you need to load a page.</span></span>  <span data-ttu-id="9993b-365">通常，在页面加载期间仅交付关键代码，然后延迟加载其他所有内容，可以加快页面加载速度。</span><span class="sxs-lookup"><span data-stu-id="9993b-365">In general, speed up page load by only shipping critical code during the page load, and then lazy-loading everything else.</span></span>  

<!--[CRP]: /web/fundamentals/performance/critical-rendering-path/  -->  

*   <span data-ttu-id="9993b-366">虽然不太可能找到能够彻底删除的脚本，但可能找到许多在页面加载期间无需请求的脚本，它们可以异步请求。</span><span class="sxs-lookup"><span data-stu-id="9993b-366">It is unlikely that you are able to find scripts that you are able to remove outright, but you may find many scripts that you do not need to request during the page load, and instead may be requested asynchronously.</span></span>  <!--Navigate to [Using async or defer][async].  -->  
*   <span data-ttu-id="9993b-367">如果你使用框架，请检查其是否包含生产模式。</span><span class="sxs-lookup"><span data-stu-id="9993b-367">If you are using a framework, check if it has a production mode.</span></span>  <span data-ttu-id="9993b-368">此模式可能使用[摇树优化][WebpackTreeShaking]等功能，从而消除阻止关键渲染不必要的代码。</span><span class="sxs-lookup"><span data-stu-id="9993b-368">This mode may use a feature such as [tree shaking][WebpackTreeShaking] in order to eliminate unnecessary code that is blocking the critical render.</span></span>  
    
<!--[async]: /web/fundamentals/performance/optimizing-content-efficiency/loading-third-party-javascript/#use_async_or_defer  -->  

### <a name="do-less-main-thread-work"></a><span data-ttu-id="9993b-369">减少主线程工作</span><span class="sxs-lookup"><span data-stu-id="9993b-369">Do less main thread work</span></span>  

<span data-ttu-id="9993b-370">最新报告的"机会"部分表明存在一些细微的潜在节省，但如果往下查看"诊断"部分，似乎最大的瓶颈是主线程活动过多。</span><span class="sxs-lookup"><span data-stu-id="9993b-370">Your latest report shows some minor potential savings in the Opportunities section, but if you look down in the Diagnostics section, it looks like the biggest bottleneck is too much main thread activity.</span></span>  

<span data-ttu-id="9993b-371">在主线程中，浏览器执行显示页面所需的多数工作，例如分析和运行 HTML、CSS 和 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="9993b-371">The main thread is where the browser does most of the work needed to display a page, such as parsing and running HTML, CSS, and JavaScript.</span></span>  

<span data-ttu-id="9993b-372">目标是使用“性能”面板分析页面加载时主线程执行的工作，并找到延迟或删除不必要工作的方法。</span><span class="sxs-lookup"><span data-stu-id="9993b-372">The goal is to use the Performance panel to analyze what work the main thread is doing while the page loads, and find ways to defer or remove unnecessary work.</span></span>  

1.  <span data-ttu-id="9993b-373">选择**性能**工具。</span><span class="sxs-lookup"><span data-stu-id="9993b-373">Choose the **Performance** tool.</span></span>  
1.  <span data-ttu-id="9993b-374">单击**捕获设置** \(![Capture Settings](../media/capture-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="9993b-374">Choose **Capture Settings** \(![Capture Settings](../media/capture-icon.msft.png)\).</span></span>  
1.  <span data-ttu-id="9993b-375">将**网络**设置为**慢速 3G**，**CPU**设置为**6x 减速**。</span><span class="sxs-lookup"><span data-stu-id="9993b-375">Set **Network** to **Slow 3G** and **CPU** to **6x slowdown**.</span></span>  <span data-ttu-id="9993b-376">移动设备的硬件约束通常比笔记本电脑或台式机多，因此这些设置可以让你就像使用不那么强大的设备一样体验页面加载。</span><span class="sxs-lookup"><span data-stu-id="9993b-376">Mobile devices typically have more hardware constraints than laptops or desktops, so these settings let you experience the page load as if you were using a less powerful device.</span></span>  
1.  <span data-ttu-id="9993b-377">选择**刷新** \(![Refresh](../media/reload-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="9993b-377">Choose **Refresh** \(![Refresh](../media/reload-icon.msft.png)\).</span></span>  <span data-ttu-id="9993b-378">开发人员工具会刷新页面，然后生成加载页面所执行的所有工作的可视化效果。</span><span class="sxs-lookup"><span data-stu-id="9993b-378">DevTools refreshes the page and then produces a visualization of all the work performed in order to load the page.</span></span>  <span data-ttu-id="9993b-379">此可视化效果称为**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="9993b-379">This visualization is referred to as the **trace**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png" alt-text="页面加载“性能”工具跟踪" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png":::
       <span data-ttu-id="9993b-381">页面加载**性能**工具跟踪</span><span class="sxs-lookup"><span data-stu-id="9993b-381">The **Performance** tool trace of the page load</span></span>  
    :::image-end:::  
    
<span data-ttu-id="9993b-382">跟踪从左到右，按时间顺序显示活动。</span><span class="sxs-lookup"><span data-stu-id="9993b-382">The trace shows activity chronologically, from left to right.</span></span>  <span data-ttu-id="9993b-383">顶部的 FPS、CPU 和 NET 图表概述了每秒帧数、CPU 活动以及网络活动。</span><span class="sxs-lookup"><span data-stu-id="9993b-383">The FPS, CPU, and NET charts at the top give you an overview of frames per second, CPU activity, and network activity.</span></span>  <span data-ttu-id="9993b-384">下图中黄色突出显示的信息块表明，CPU 完全忙于脚本活动。</span><span class="sxs-lookup"><span data-stu-id="9993b-384">The block of yellow highlighted in the figure after the next, the CPU was completely busy with scripting activity.</span></span>  <span data-ttu-id="9993b-385">这表明你可以减少 JavaScript 工作，从而加快页面加载速度。</span><span class="sxs-lookup"><span data-stu-id="9993b-385">This is a clue that you may be able to speed up page load by doing less JavaScript work.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png" alt-text="跟踪的“概述”部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png":::
   <span data-ttu-id="9993b-387">跟踪的“概述”部分</span><span class="sxs-lookup"><span data-stu-id="9993b-387">The Overview section of the trace</span></span>  
:::image-end:::  

<span data-ttu-id="9993b-388">调查跟踪，查找减少 JavaScript 工作的方法：</span><span class="sxs-lookup"><span data-stu-id="9993b-388">Investigate the trace to find ways to do less JavaScript work:</span></span>  

1.  <span data-ttu-id="9993b-389">选择并展开**计时** 部分。</span><span class="sxs-lookup"><span data-stu-id="9993b-389">Choose the **Timings** section to expand it.</span></span>  <span data-ttu-id="9993b-390">基于 React 中可能存在许多[计时][MDNUserTimingApi]测量的事实，Tony 的应用似乎正使用 React 的开发模式。</span><span class="sxs-lookup"><span data-stu-id="9993b-390">Based on the fact that there may be a bunch of [Timings][MDNUserTimingApi] measures from React, it seems like Tony's app is using the development mode of React.</span></span>  <span data-ttu-id="9993b-391">切换到 React 的生产模式可能会产生一些简单的性能优势。</span><span class="sxs-lookup"><span data-stu-id="9993b-391">Switching to the production mode of React may yield some easy performance wins.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png" alt-text=""计时"部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png":::
       <span data-ttu-id="9993b-393">**计时**部分</span><span class="sxs-lookup"><span data-stu-id="9993b-393">The **Timings** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-394">再次选择**计时**，折叠该部分。</span><span class="sxs-lookup"><span data-stu-id="9993b-394">Choose **Timings** again to collapse that section.</span></span>  
1.  <span data-ttu-id="9993b-395">浏览**主要**部分。</span><span class="sxs-lookup"><span data-stu-id="9993b-395">Browse the **Main** section.</span></span>  <span data-ttu-id="9993b-396">此部分从左到右，按时间顺序显示了主线程活动的记录。</span><span class="sxs-lookup"><span data-stu-id="9993b-396">This section shows a chronological log of main thread activity, from left to right.</span></span>  <span data-ttu-id="9993b-397">y 轴（从上到下）表示事件发生的原因。</span><span class="sxs-lookup"><span data-stu-id="9993b-397">The y-axis (top to bottom) shows why events occurred.</span></span>  <span data-ttu-id="9993b-398">例如，在下图中，`Evaluate Script`事件导致`(anonymous)`函数运行，继而导致`(anonymous)`运行，然后导致`__webpack__require__`运行，以此类推。</span><span class="sxs-lookup"><span data-stu-id="9993b-398">For example, in the figyre after the following, the `Evaluate Script` event caused the `(anonymous)` function to run, which caused `(anonymous)` to run, which caused `__webpack__require__` to run, and so on.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png" alt-text="“主要”部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png":::
       <span data-ttu-id="9993b-400">**主要**部分</span><span class="sxs-lookup"><span data-stu-id="9993b-400">The **Main** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9993b-401">向下滚动到**主要**部分的底部。</span><span class="sxs-lookup"><span data-stu-id="9993b-401">Scroll down to the bottom of the **Main** section.</span></span>  <span data-ttu-id="9993b-402">使用框架时，多数上部活动由框架引起，框架通常无法控制。</span><span class="sxs-lookup"><span data-stu-id="9993b-402">When you use a framework, most of the upper activity is caused by the framework, which is usually out of your control.</span></span>  <span data-ttu-id="9993b-403">你的应用引起的活动通常位于底部。</span><span class="sxs-lookup"><span data-stu-id="9993b-403">The activity caused by your app is usually at the bottom.</span></span>  <span data-ttu-id="9993b-404">在此应用中，名为`App`的函数似乎引起了对`mineBitcoin`函数的大量请求。</span><span class="sxs-lookup"><span data-stu-id="9993b-404">In this app, it seems like a function named `App` is causing a lot of requests to a `mineBitcoin` function.</span></span>  <span data-ttu-id="9993b-405">听起来 Tony 可能正使用粉丝的设备挖掘加密货币...</span><span class="sxs-lookup"><span data-stu-id="9993b-405">It sounds like Tony may be using the devices of his fans to mine cryptocurrency...</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png" alt-text="悬停在 mineBitcoin 活动上" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png":::
       <span data-ttu-id="9993b-407">悬停在`mineBitcoin`活动上</span><span class="sxs-lookup"><span data-stu-id="9993b-407">Hover on the `mineBitcoin` activity</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="9993b-408">虽然框架提出的请求通常无法控制，但有时你可能以导致框架低效运行的方式构建应用。</span><span class="sxs-lookup"><span data-stu-id="9993b-408">Although the requests that your framework makes are usually out of your control, sometimes you may structure your app in a way that causes the framework to run inefficiently.</span></span>  <span data-ttu-id="9993b-409">重构应用、高效使用框架是减少主线程工作的一种方法。</span><span class="sxs-lookup"><span data-stu-id="9993b-409">Restructuring your app to use the framework efficiently is a way to do less main thread work.</span></span>  <span data-ttu-id="9993b-410">但是，这要求深入了解框架的工作方式，以及对代码进行哪些更改可以更有效地使用框架。</span><span class="sxs-lookup"><span data-stu-id="9993b-410">However, this requires a deep understanding of how your framework works, and what kind of changes you make in your own code in order to use the framework more efficiently.</span></span>  
    
1.  <span data-ttu-id="9993b-411">展开**自上而下**部分。</span><span class="sxs-lookup"><span data-stu-id="9993b-411">Expand the **Bottom-Up** section.</span></span>  <span data-ttu-id="9993b-412">此选项卡将分解占用时间最多的活动。</span><span class="sxs-lookup"><span data-stu-id="9993b-412">This tab breaks down what activities took up the most time.</span></span>  <span data-ttu-id="9993b-413">如果“自上而下”部分未显示任何内容，请选择**主要**部分的标签。</span><span class="sxs-lookup"><span data-stu-id="9993b-413">If nothing is displayed in the Bottom-Up section, choose the label for **Main** section.</span></span>  <span data-ttu-id="9993b-414">**自上而下**部分只显示当前选择的活动或活动组的信息。</span><span class="sxs-lookup"><span data-stu-id="9993b-414">The **Bottom-Up** section only shows information for whatever activity, or group of activity, you have currently selected.</span></span>  <span data-ttu-id="9993b-415">例如，如果选择`mineBitcoin`中的一个活动，则**自上而下**部将只显示该活动的信息。 </span><span class="sxs-lookup"><span data-stu-id="9993b-415">For example, if you chose one of the `mineBitcoin` activities, the **Bottom-Up** section is only going to show information for that one activity.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png" alt-text="“自下而上”选项卡" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png":::
       <span data-ttu-id="9993b-417">**自上而下**选项卡</span><span class="sxs-lookup"><span data-stu-id="9993b-417">The **Bottom-Up** tab</span></span>  
    :::image-end:::  
    
<span data-ttu-id="9993b-418">**自我时间**列显示每个活动直接花费的时间。</span><span class="sxs-lookup"><span data-stu-id="9993b-418">The **Self Time** column shows you how much time was spent directly in each activity.</span></span>  <span data-ttu-id="9993b-419">例如，在下图中，约 63% 的主线程时间用于`mineBitcoin`函数。</span><span class="sxs-lookup"><span data-stu-id="9993b-419">For example, in the following figure, about 63% of main thread time was spent on the `mineBitcoin` function.</span></span>  

<span data-ttu-id="9993b-420">现在开始查看使用生产模式和减少 JavaScript 活动是否可能加快页面加载。</span><span class="sxs-lookup"><span data-stu-id="9993b-420">Time to review whether using production mode and reducing JavaScript activity may speed up the page load.</span></span>  <span data-ttu-id="9993b-421">从生产模式开始：</span><span class="sxs-lookup"><span data-stu-id="9993b-421">Start with production mode:</span></span>  

1.  <span data-ttu-id="9993b-422">在编辑器选项卡中，打开`webpack.config.js`。</span><span class="sxs-lookup"><span data-stu-id="9993b-422">In the editor tab, open `webpack.config.js`.</span></span>  
1.  <span data-ttu-id="9993b-423">将`"mode":"development"`更改为`"mode":"production"`。</span><span class="sxs-lookup"><span data-stu-id="9993b-423">Change `"mode":"development"` to `"mode":"production"`.</span></span>  
1.  <span data-ttu-id="9993b-424">等待新内部版本部署。</span><span class="sxs-lookup"><span data-stu-id="9993b-424">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="9993b-425">再次审核页面。</span><span class="sxs-lookup"><span data-stu-id="9993b-425">Audit the page again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png" alt-text="配置 webpack 使用生产模式后的“审核”报告" lightbox="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png":::
       <span data-ttu-id="9993b-427">配置 webpack 使用生产模式后的“审核”报告</span><span class="sxs-lookup"><span data-stu-id="9993b-427">An Audits report after configuring webpack to use production mode</span></span>  
    :::image-end:::  
    
<span data-ttu-id="9993b-428">通过删除对`mineBitcoin`的请求减少 JavaScript 活动：</span><span class="sxs-lookup"><span data-stu-id="9993b-428">Reduce JavaScript activity by removing the request to `mineBitcoin`:</span></span>  

1.  <span data-ttu-id="9993b-429">在编辑器选项卡中，打开`src/App.jsx`。</span><span class="sxs-lookup"><span data-stu-id="9993b-429">In the editor tab, open `src/App.jsx`.</span></span>  
1.  <span data-ttu-id="9993b-430">在`constructor`中，为对`this.mineBitcoin(1500)`的请求添加备注。</span><span class="sxs-lookup"><span data-stu-id="9993b-430">Comment out the request to `this.mineBitcoin(1500)` in the `constructor`.</span></span>  
1.  <span data-ttu-id="9993b-431">等待新内部版本部署。</span><span class="sxs-lookup"><span data-stu-id="9993b-431">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="9993b-432">再次审核页面。</span><span class="sxs-lookup"><span data-stu-id="9993b-432">Audit the page again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png" alt-text="删除不必要的 JavaScript 工作后的“审核”报告" lightbox="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png":::
       <span data-ttu-id="9993b-434">删除不必要的 JavaScript 工作后的“审核”报告</span><span class="sxs-lookup"><span data-stu-id="9993b-434">An Audits report after removing unnecessary JavaScript work</span></span>  
    :::image-end:::  
    
<span data-ttu-id="9993b-435">最后更改似乎大幅提升了性能！</span><span class="sxs-lookup"><span data-stu-id="9993b-435">Looks like that last change caused a massive jump in performance!</span></span>  

> [!NOTE]
> <span data-ttu-id="9993b-436">此部分简要介绍了“性能”面板。</span><span class="sxs-lookup"><span data-stu-id="9993b-436">This section provided a rather brief introduction to the Performance panel.</span></span>  <span data-ttu-id="9993b-437">若要了解如何分析页面性能的详细信息，请导航到[性能分析参考][DevtoolsEvaluatePerformanceReference]。</span><span class="sxs-lookup"><span data-stu-id="9993b-437">To learn more about how to analyze page performance, navigate to [Performance Analysis Reference][DevtoolsEvaluatePerformanceReference].</span></span>  

<!--todo: add section when available -->  

#### <a name="doing-less-main-thread-work-in-the-real-world"></a><span data-ttu-id="9993b-438">在现实世界中减少主线程工作</span><span class="sxs-lookup"><span data-stu-id="9993b-438">Doing less main thread work in the real world</span></span>  

<span data-ttu-id="9993b-439">通常， **性能**工具作为最常用的方法，可以了解站点在加载时执行哪些活动，以及找到删除不必要活动的方法。</span><span class="sxs-lookup"><span data-stu-id="9993b-439">In general, the **Performance** tool is the most common way to understand what activity your site does as it loads, and find ways to remove unnecessary activity.</span></span>  

<span data-ttu-id="9993b-440">如果你倾向于更像`console.log()`的方法，则[用户计时 API][MDNUserTimingApi]将允许你任意标记应用生命周期的某些阶段，从而跟踪每个阶段花费的时间。</span><span class="sxs-lookup"><span data-stu-id="9993b-440">If you prefer an approach that feels more like `console.log()`, the [User Timing API][MDNUserTimingApi] enables you to arbitrarily mark up certain phases of your app lifecycle, in order to track how long each of those phases takes.</span></span>  

## <a name="summary"></a><span data-ttu-id="9993b-441">摘要</span><span class="sxs-lookup"><span data-stu-id="9993b-441">Summary</span></span>  

*   <span data-ttu-id="9993b-442">无论何时开始优化站点的加载性能，始终都从审核开始。</span><span class="sxs-lookup"><span data-stu-id="9993b-442">Whenever you set out to optimize the load performance of a site, always start with an audit.</span></span>  <span data-ttu-id="9993b-443">审核会建立基线，并提供如何改进的提示。</span><span class="sxs-lookup"><span data-stu-id="9993b-443">The audit establishes a baseline, and gives you tips on how to improve.</span></span>  
*   <span data-ttu-id="9993b-444">一次进行一个更改，并在每次更改后审核网页，从而显示独立更改对性能的影响。</span><span class="sxs-lookup"><span data-stu-id="9993b-444">Make one change at a time, and audit the webpage after each change in order to display how that isolated change affects performance.</span></span>  

<!--
## Next steps  

*   Run audits on your own site!  If you need help interpreting your report, or finding ways to improve your load performance, check out [Feedback](#feedback) for ways to get help from the DevTools community.  Stack Overflow, the mailing list, or Twitter are probably best for these types of questions.  
*   Please leave [feedback](#feedback) on this tutorial.  I really do use the data to make better tutorials for you.  
-->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="9993b-445">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="9993b-445">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsEvaluatePerformanceReference]: ../evaluate-performance/reference.md "性能分析参考 | Microsoft Docs"  

[CourseraIntroductionWebDevelopmentClass]: https://www.coursera.org/learn/web-development#syllabus "Web 开发类简介 | Coursera"  

[EssentialImageOptimization]: https://images.guide "基本图像优化"  

[MDNContentEncodingDirectives]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Encoding#Directives "指令 - Content-Encoding | MDN"  
[MDNUserTimingApi]: https://developer.mozilla.org/docs/Web/API/User_Timing_API "用户计时 API | MDN"  

[WebpackTreeShaking]: https://webpack.js.org/guides/tree-shaking "摇树优化 | webpack"  

> [!NOTE]
> <span data-ttu-id="9993b-452">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="9993b-452">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9993b-453">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/speed/get-started)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="9993b-453">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/speed/get-started) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="9993b-455">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="9993b-455">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
