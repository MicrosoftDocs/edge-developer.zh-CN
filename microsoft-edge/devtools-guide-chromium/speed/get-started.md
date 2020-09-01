---
title: 使用 Microsoft Edge 开发人员工具优化网站速度
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 42b742316ccaa64aa35fc1d21c5277e448b2d5b7
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10984576"
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





# <span data-ttu-id="8e953-103">通过 Microsoft Edge DevTools 优化网站速度</span><span class="sxs-lookup"><span data-stu-id="8e953-103">Optimize website speed with Microsoft Edge DevTools</span></span>   



## <span data-ttu-id="8e953-104">教程目标</span><span class="sxs-lookup"><span data-stu-id="8e953-104">Goal of tutorial</span></span>  

<span data-ttu-id="8e953-105">本教程指导你如何使用 Microsoft Edge DevTools 来查找更快地加载网站的方法。</span><span class="sxs-lookup"><span data-stu-id="8e953-105">This tutorial teaches you how to use Microsoft Edge DevTools to find ways to make your websites load faster.</span></span>  

## <span data-ttu-id="8e953-106">必备条件</span><span class="sxs-lookup"><span data-stu-id="8e953-106">Prerequisites</span></span>  

*   <span data-ttu-id="8e953-107">你应该具有基本的 web 开发体验，类似于在此 [Web 开发类简介][CourseraIntroductionWebDevelopmentClass]中讲授的内容。</span><span class="sxs-lookup"><span data-stu-id="8e953-107">You should have basic web development experience, similar to what is taught in this [Introduction to Web Development class][CourseraIntroductionWebDevelopmentClass].</span></span>  
*   <span data-ttu-id="8e953-108">无需了解有关加载性能的任何信息。</span><span class="sxs-lookup"><span data-stu-id="8e953-108">You do not need to know anything about load performance.</span></span>  <span data-ttu-id="8e953-109">您可以在本教程中了解它！</span><span class="sxs-lookup"><span data-stu-id="8e953-109">You learn about it in this tutorial!</span></span>  

## <span data-ttu-id="8e953-110">简介</span><span class="sxs-lookup"><span data-stu-id="8e953-110">Introduction</span></span>   

<span data-ttu-id="8e953-111">这是 Tony。</span><span class="sxs-lookup"><span data-stu-id="8e953-111">This is Tony.</span></span>  <span data-ttu-id="8e953-112">Tony 在猫社会中非常著名。</span><span class="sxs-lookup"><span data-stu-id="8e953-112">Tony is very famous in cat society.</span></span>  <span data-ttu-id="8e953-113">他已构建了一个网站，使其风扇能够了解他最喜爱的食物。</span><span class="sxs-lookup"><span data-stu-id="8e953-113">He has built a website so that his fans are able to learn about his favorite foods.</span></span>  <span data-ttu-id="8e953-114">他的风扇喜欢该站点，但 Tony 会不断听到该站点加载缓慢的投诉。</span><span class="sxs-lookup"><span data-stu-id="8e953-114">His fans love the site, but Tony keeps hearing complaints that the site loads slowly.</span></span>  <span data-ttu-id="8e953-115">Tony 已要求您帮助他提高网站的速度。</span><span class="sxs-lookup"><span data-stu-id="8e953-115">Tony has asked you to help him speed the site up.</span></span>  

:::image type="complex" source="../media/speed-tony.msft.png" alt-text="Tony 猫" lightbox="../media/speed-tony.msft.png":::
   <span data-ttu-id="8e953-117">Tony 猫</span><span class="sxs-lookup"><span data-stu-id="8e953-117">Tony the cat</span></span>  
:::image-end:::  

## <span data-ttu-id="8e953-118">步骤1：审核网站</span><span class="sxs-lookup"><span data-stu-id="8e953-118">Step 1: Audit the site</span></span>   

<span data-ttu-id="8e953-119">无论何时设置以提高网站的负载性能， **都应始终从审核开始**。</span><span class="sxs-lookup"><span data-stu-id="8e953-119">Whenever you set out to improve the load performance of a site, **always start with an audit**.</span></span>  
<span data-ttu-id="8e953-120">审核具有2个重要功能：</span><span class="sxs-lookup"><span data-stu-id="8e953-120">The audit has 2 important functions:</span></span>  

*   <span data-ttu-id="8e953-121">它将为您创建一个 **基线** 来衡量后续更改。</span><span class="sxs-lookup"><span data-stu-id="8e953-121">It creates a **baseline** for you to measure subsequent changes against.</span></span>  
*   <span data-ttu-id="8e953-122">它为你提供了可操作的有关哪些更改最有影响的 **提示** 。</span><span class="sxs-lookup"><span data-stu-id="8e953-122">It gives you **actionable tips** on what changes have the most impact.</span></span>  
    
### <span data-ttu-id="8e953-123">设置</span><span class="sxs-lookup"><span data-stu-id="8e953-123">Set up</span></span>   

<span data-ttu-id="8e953-124">首先，你必须设置网站，以便稍后能够对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="8e953-124">First, you must set up the site so that you are able to make changes to it later.</span></span>  

1.  <span data-ttu-id="8e953-125">[打开网站的源代码](https://glitch.com/edit/#!/tony)。</span><span class="sxs-lookup"><span data-stu-id="8e953-125">[Open the source code for the site](https://glitch.com/edit/#!/tony).</span></span>  <span data-ttu-id="8e953-126">此选项卡称为 **编辑器选项卡**。</span><span class="sxs-lookup"><span data-stu-id="8e953-126">This tab is referred to as the **editor tab**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js.msft.png" alt-text=""编辑器" 选项卡" lightbox="../media/speed-glitch-tony-server-js.msft.png":::
       <span data-ttu-id="8e953-128">" **编辑器" 选项卡**</span><span class="sxs-lookup"><span data-stu-id="8e953-128">The **editor tab**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-129">选择 " **tony**"。</span><span class="sxs-lookup"><span data-stu-id="8e953-129">Select **tony**.</span></span>  <span data-ttu-id="8e953-130">将显示一个菜单。</span><span class="sxs-lookup"><span data-stu-id="8e953-130">A menu appears.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js-remix-project.msft.png" alt-text="单击 "tony" 后出现的菜单" lightbox="../media/speed-glitch-tony-server-js-remix-project.msft.png":::
       <span data-ttu-id="8e953-132">单击 " **tony** " 后出现的菜单</span><span class="sxs-lookup"><span data-stu-id="8e953-132">The menu that appears after clicking **tony**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-133">选择 " **Remix 项目**"。</span><span class="sxs-lookup"><span data-stu-id="8e953-133">Select **Remix Project**.</span></span>  <span data-ttu-id="8e953-134">项目的名称从 **tony** 更改为某个随机生成的名称。</span><span class="sxs-lookup"><span data-stu-id="8e953-134">The name of the project changes from **tony** to some randomly-generated name.</span></span>  <span data-ttu-id="8e953-135">现在，你拥有自己的代码的可编辑副本。</span><span class="sxs-lookup"><span data-stu-id="8e953-135">You now have your own editable copy of the code.</span></span>  <span data-ttu-id="8e953-136">稍后，你可以对此代码进行更改。</span><span class="sxs-lookup"><span data-stu-id="8e953-136">Later on, you may make changes to this code.</span></span>  
1.  <span data-ttu-id="8e953-137">选择 " **显示** "，然后 **在新窗口中**选择。</span><span class="sxs-lookup"><span data-stu-id="8e953-137">Select **Show** and select **In a New Window**.</span></span>  <span data-ttu-id="8e953-138">演示将在新选项卡中打开。 此选项卡称为 " **演示" 选项卡**。 加载网站可能需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="8e953-138">The demo opens in a new tab.  This tab is be referred to as the **demo tab**.  It may take a while for the site to load.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live.msft.png" alt-text=""演示" 选项卡" lightbox="../media/speed-glitch-tony-show-live.msft.png":::
       <span data-ttu-id="8e953-140">"演示" 选项卡</span><span class="sxs-lookup"><span data-stu-id="8e953-140">The demo tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-141">按 `Control` + `Shift` + `J` \ (Windows \ ) 或 `Command` + `Option` + `J` \ (macOS \ ) 。</span><span class="sxs-lookup"><span data-stu-id="8e953-141">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="8e953-142">Microsoft Edge DevTools 将与演示一起打开。</span><span class="sxs-lookup"><span data-stu-id="8e953-142">Microsoft Edge DevTools opens up alongside the demo.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live-console.msft.png" alt-text="DevTools 和演示" lightbox="../media/speed-glitch-tony-show-live-console.msft.png":::
       <span data-ttu-id="8e953-144">DevTools 和演示</span><span class="sxs-lookup"><span data-stu-id="8e953-144">DevTools and the demo</span></span>  
    :::image-end:::  
    
<span data-ttu-id="8e953-145">对于本教程中的其余屏幕截图，DevTools 显示在一个单独的窗口中。</span><span class="sxs-lookup"><span data-stu-id="8e953-145">For the rest of the screenshots in this tutorial, DevTools is shown in a separate window.</span></span>  <span data-ttu-id="8e953-146">按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "命令" 菜单，键入 `Undock` ，然后选择 "**在单独窗口中取消插入**"。</span><span class="sxs-lookup"><span data-stu-id="8e953-146">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, typing `Undock`, and then selecting **Undock into separate window**.</span></span>  

:::image type="complex" source="../media/speed-console.msft.png" alt-text="取消停靠 DevTools" lightbox="../media/speed-console.msft.png":::
   <span data-ttu-id="8e953-148">取消停靠 DevTools</span><span class="sxs-lookup"><span data-stu-id="8e953-148">Undocked DevTools</span></span>  
:::image-end:::  

### <span data-ttu-id="8e953-149">建立基线</span><span class="sxs-lookup"><span data-stu-id="8e953-149">Establish a baseline</span></span>   

<span data-ttu-id="8e953-150">比较基准是在改进性能方面之前如何执行网站的记录。</span><span class="sxs-lookup"><span data-stu-id="8e953-150">The baseline is a record of how the site performed before you made any performance improvements.</span></span>  

1.  <span data-ttu-id="8e953-151">选择 " **审核** " 选项卡。 它可能隐藏在 " **更多面板** " 后面 (![ 更多面板 ][ImageMorePanelsIcon] \ ) 按钮。</span><span class="sxs-lookup"><span data-stu-id="8e953-151">Select the **Audits** tab.  It may be hidden behind the **More Panels** \(![More Panels][ImageMorePanelsIcon]\) button.</span></span>  <span data-ttu-id="8e953-152">此面板上有一个 Lighthouse，因为 Lighthouse "审核" 面板的项目称为 " **Lighthouse**"。</span><span class="sxs-lookup"><span data-stu-id="8e953-152">There is a Lighthouse on this panel because the project that powers the Audits panel is named **Lighthouse**.</span></span>  
    
    [!INCLUDE [audits-panel-note](../includes/audits-panel-note.md)]  
    
    :::image type="complex" source="../media/speed-audits-performance.msft.png" alt-text=""审核" 面板" lightbox="../media/speed-audits-performance.msft.png":::
       <span data-ttu-id="8e953-154">" **审核** " 面板</span><span class="sxs-lookup"><span data-stu-id="8e953-154">The **Audits** panel</span></span>  
    :::image-end:::  
    
    <!--todo: add link to Lighthouse when section is available  -->  
    <!-- /web/tools/lighthouse  -->  
    
1.  <span data-ttu-id="8e953-155">将您的审核配置设置与上图中的设置相匹配。</span><span class="sxs-lookup"><span data-stu-id="8e953-155">Match your audit configuration settings to those in the previous figure.</span></span>  <span data-ttu-id="8e953-156">下面是不同选项的说明：</span><span class="sxs-lookup"><span data-stu-id="8e953-156">Here is an explanation of the different options:</span></span>  
    
    *   <span data-ttu-id="8e953-157">**设备**。</span><span class="sxs-lookup"><span data-stu-id="8e953-157">**Device**.</span></span>  <span data-ttu-id="8e953-158">设置为 " **移动** " 将更改用户代理字符串并模拟移动视区。</span><span class="sxs-lookup"><span data-stu-id="8e953-158">Setting to **Mobile** changes the user agent string and simulates a mobile viewport.</span></span>  <span data-ttu-id="8e953-159">设置到 **桌面** 非常简单，只需禁用 **移动** 更改。</span><span class="sxs-lookup"><span data-stu-id="8e953-159">Setting to **Desktop** pretty much just disables the **Mobile** changes.</span></span>  
    *   <span data-ttu-id="8e953-160">**审核**。</span><span class="sxs-lookup"><span data-stu-id="8e953-160">**Audits**.</span></span>  <span data-ttu-id="8e953-161">禁用类别可防止 "审核" 面板运行这些审核，并从报表中排除这些审核。</span><span class="sxs-lookup"><span data-stu-id="8e953-161">Disabling a category prevents the Audits panel from running those audits, and excludes those audits from your report.</span></span>  <span data-ttu-id="8e953-162">如果想要查看提供的建议类型，请保留启用其他类别。</span><span class="sxs-lookup"><span data-stu-id="8e953-162">Leave the other categories enabled, if you want to see the types of recommendations that are provide.</span></span>  <span data-ttu-id="8e953-163">禁用类别会略微提高审核过程的速度。</span><span class="sxs-lookup"><span data-stu-id="8e953-163">Disabling categories slightly speeds up the auditing process.</span></span>  
    *   <span data-ttu-id="8e953-164">**限制**。</span><span class="sxs-lookup"><span data-stu-id="8e953-164">**Throttling**.</span></span>  <span data-ttu-id="8e953-165">设置为 **模拟慢4G，4X CPU 减速** 模拟在移动设备上浏览的典型条件。</span><span class="sxs-lookup"><span data-stu-id="8e953-165">Setting to **Simulated Slow 4G, 4x CPU Slowdown** simulates the typical conditions of browsing on a mobile device.</span></span>  <span data-ttu-id="8e953-166">它被命名为 "模拟"，因为审核面板在审核过程中实际上并不会受到限制。</span><span class="sxs-lookup"><span data-stu-id="8e953-166">It is named "simulated" because the Audits panel does not actually throttle during the auditing process.</span></span>  <span data-ttu-id="8e953-167">相反，它只是 extrapolates 在移动条件下加载页面所需的时间。</span><span class="sxs-lookup"><span data-stu-id="8e953-167">Instead, it just extrapolates how long the page would take to load under mobile conditions.</span></span>  <span data-ttu-id="8e953-168">另一方面， **应用的 ...** 设置实际上会限制 CPU 和网络，同时还会权衡较长的审核过程。</span><span class="sxs-lookup"><span data-stu-id="8e953-168">The **Applied...** setting, on the other hand, actually throttles your CPU and network, with the tradeoff of a longer auditing process.</span></span>  
    *   <span data-ttu-id="8e953-169">**清除存储空间**。</span><span class="sxs-lookup"><span data-stu-id="8e953-169">**Clear Storage**.</span></span>  <span data-ttu-id="8e953-170">启用此复选框将在每次审核之前清除与页面关联的所有存储。</span><span class="sxs-lookup"><span data-stu-id="8e953-170">Enabling this checkbox clears all storage associated with the page before every audit.</span></span>  <span data-ttu-id="8e953-171">如果你想要审核首次访问你的网站时的访问者体验，请保留此设置。</span><span class="sxs-lookup"><span data-stu-id="8e953-171">Leave this setting on if you want to audit how first-time visitors experience your site.</span></span>  <span data-ttu-id="8e953-172">如果需要重复访问体验，请禁用此设置。</span><span class="sxs-lookup"><span data-stu-id="8e953-172">Disable this setting when you want the repeat-visit experience.</span></span>  
    
1.  <span data-ttu-id="8e953-173">选择 " **运行审核**"。</span><span class="sxs-lookup"><span data-stu-id="8e953-173">Select **Run Audits**.</span></span>  <span data-ttu-id="8e953-174">10至30秒后，"审核" 面板将显示有关网站性能的报告。</span><span class="sxs-lookup"><span data-stu-id="8e953-174">After 10 to 30 seconds, the Audits panel shows you a report of the performance of the site.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png" alt-text="网站性能的 "审核" 面板的报表" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png":::
       <span data-ttu-id="8e953-176">网站性能的 "审核" 面板的报表</span><span class="sxs-lookup"><span data-stu-id="8e953-176">The report for the Audits panel of the performance of the site</span></span>  
    :::image-end:::  
    
#### <span data-ttu-id="8e953-177">处理报告错误</span><span class="sxs-lookup"><span data-stu-id="8e953-177">Handling report errors</span></span>   

<span data-ttu-id="8e953-178">如果你在 "审核" 面板报告中遇到错误，请尝试从 **InPrivate** 窗口运行 "演示" 选项卡，并且不会打开任何其他选项卡。</span><span class="sxs-lookup"><span data-stu-id="8e953-178">If you ever get an error in your Audits panel report, try running the demo tab from an **InPrivate** window with no other tabs open.</span></span>  <span data-ttu-id="8e953-179">这可确保你从干净状态运行 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="8e953-179">This ensures that you are running Microsoft Edge from a clean state.</span></span>  <span data-ttu-id="8e953-180">Microsoft Edge 扩展通常会干扰审核过程。</span><span class="sxs-lookup"><span data-stu-id="8e953-180">Microsoft Edge Extensions in particular often interfere with the auditing process.</span></span>  

<!--todo: add screen capture for error in audit -->  
<!--
:::image type="complex" source="../media/speed-.msft.png" alt-text="A report that errored" lightbox="../media/speed-.msft.png":::
   A report that errored  
:::image-end:::  
-->  

### <span data-ttu-id="8e953-181">了解你的报表</span><span class="sxs-lookup"><span data-stu-id="8e953-181">Understand your report</span></span>   

<span data-ttu-id="8e953-182">报表顶部的数字是网站的整体绩效分数。</span><span class="sxs-lookup"><span data-stu-id="8e953-182">The number at the top of your report is the overall performance score for the site.</span></span>  <span data-ttu-id="8e953-183">稍后，在对代码进行更改时，您应看到此数字高度。</span><span class="sxs-lookup"><span data-stu-id="8e953-183">Later, as you make changes to the code, you should see this number rise.</span></span>  <span data-ttu-id="8e953-184">分数越高表示性能越高。</span><span class="sxs-lookup"><span data-stu-id="8e953-184">A higher score means better performance.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png" alt-text="整体性能分数" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png":::
   <span data-ttu-id="8e953-186">整体性能分数</span><span class="sxs-lookup"><span data-stu-id="8e953-186">The overall performance score</span></span>  
:::image-end:::  

<span data-ttu-id="8e953-187">" **指标** " 部分提供了有关站点性能的量化指标。</span><span class="sxs-lookup"><span data-stu-id="8e953-187">The **Metrics** section provides quantitative measurements of the performance of the site.</span></span>  <span data-ttu-id="8e953-188">每个指标都可以深入了解性能的不同方面。</span><span class="sxs-lookup"><span data-stu-id="8e953-188">Each metric provides insight into a different aspect of the performance.</span></span>  <span data-ttu-id="8e953-189">例如， **第一个 Contentful 画图** 会告诉您，当内容首次绘制到屏幕时，这是用户对页面加载的感觉中的重要里程碑，而是 **交互式** 标记该页面似乎足以处理用户交互的时刻。</span><span class="sxs-lookup"><span data-stu-id="8e953-189">For example, **First Contentful Paint** tells you when content is first painted to the screen, which is an important milestone in the user's perception of the page load, whereas **Time To Interactive** marks the point at which the page appears ready enough to handle user interactions.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png" alt-text=""指标" 部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png":::
   <span data-ttu-id="8e953-191">" **指标** " 部分</span><span class="sxs-lookup"><span data-stu-id="8e953-191">The **Metrics** section</span></span>  
:::image-end:::  

<span data-ttu-id="8e953-192">选择下图中突出显示的 "切换" 按钮以查看每个指标的说明，然后单击 " **了解详细** 信息" 以阅读有关每个指标的文档。</span><span class="sxs-lookup"><span data-stu-id="8e953-192">Select the highlighted toggle button in the following figure to see a description for each metric, and click **Learn More** to read documentation about it.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png" alt-text="选择突出显示的切换按钮以展开指标项目" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png":::
   <span data-ttu-id="8e953-194">选择突出显示的切换按钮以展开指标项目</span><span class="sxs-lookup"><span data-stu-id="8e953-194">Select the highlighted toggle button to expand the Metrics items</span></span>  
:::image-end:::  

<span data-ttu-id="8e953-195">"指标" 下面是屏幕截图的集合，可显示页面的加载方式。</span><span class="sxs-lookup"><span data-stu-id="8e953-195">Below Metrics is a collection of screenshots that show you how the page looked as it loaded.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="在加载时如何查看页面的屏幕截图" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   <span data-ttu-id="8e953-197">在加载时如何查看页面的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="8e953-197">Screenshots of how the page looked while loading</span></span>  
:::image-end:::  

<span data-ttu-id="8e953-198">" **商机** " 部分提供了有关如何提高此特定页面的加载性能的特定提示。</span><span class="sxs-lookup"><span data-stu-id="8e953-198">The **Opportunities** section provides specific tips on how to improve the load performance of this specific page.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text=""商机" 部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   <span data-ttu-id="8e953-200">" **商机** " 部分</span><span class="sxs-lookup"><span data-stu-id="8e953-200">The **Opportunities** section</span></span>  
:::image-end:::  

<span data-ttu-id="8e953-201">选择一个商机以了解更多相关信息。</span><span class="sxs-lookup"><span data-stu-id="8e953-201">Select an opportunity to learn more about it.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png" alt-text="消除呈现阻止资源的机会" lightbox="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png":::
   <span data-ttu-id="8e953-203">**消除呈现阻止资源的** 机会</span><span class="sxs-lookup"><span data-stu-id="8e953-203">**Eliminate render-blocking resources** opportunity</span></span>  
:::image-end:::  

<span data-ttu-id="8e953-204">选择 " **了解详细** 信息"，查看有关商机为什么很重要的文档，以及有关如何解决该问题的特定建议。</span><span class="sxs-lookup"><span data-stu-id="8e953-204">Select **Learn More** to see documentation about why an opportunity is important, and specific recommendations on how to fix it.</span></span>  

:::image type="complex" source="../media/speed-web-dev-performance-audits.msft.png" alt-text="用于消除呈现阻止资源商机的文档" lightbox="../media/speed-web-dev-performance-audits.msft.png":::
   <span data-ttu-id="8e953-206">用于 **消除呈现阻止资源** 商机的文档</span><span class="sxs-lookup"><span data-stu-id="8e953-206">Documentation for the **Eliminate render-blocking resources** opportunity</span></span>  
:::image-end:::  

<span data-ttu-id="8e953-207">**诊断**部分提供有关影响页面加载时间的因素的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8e953-207">The **Diagnostics** section provides more information about factors that contribute to the load time of the page.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png" alt-text="诊断部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png":::
   <span data-ttu-id="8e953-209">**诊断**部分</span><span class="sxs-lookup"><span data-stu-id="8e953-209">The **Diagnostics** section</span></span>  
:::image-end:::  

<span data-ttu-id="8e953-210">"已 **通过审核** " 部分显示网站正确执行的操作。</span><span class="sxs-lookup"><span data-stu-id="8e953-210">The **Passed Audits** section shows you what the site is doing correctly.</span></span>  <span data-ttu-id="8e953-211">选择以展开该部分。</span><span class="sxs-lookup"><span data-stu-id="8e953-211">Select to expand the section.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png" alt-text=""已传递审核" 部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png":::
   <span data-ttu-id="8e953-213">"已 **传递审核** " 部分</span><span class="sxs-lookup"><span data-stu-id="8e953-213">The **Passed Audits** section</span></span>  
:::image-end:::  

## <span data-ttu-id="8e953-214">步骤2：实验</span><span class="sxs-lookup"><span data-stu-id="8e953-214">Step 2: Experiment</span></span>   

<span data-ttu-id="8e953-215">审核报告的 "机遇" 部分提供了有关如何提高页面性能的提示。</span><span class="sxs-lookup"><span data-stu-id="8e953-215">The Opportunities section of your audit report gives you tips on how to improve the performance of the page.</span></span>  <span data-ttu-id="8e953-216">在此部分中，你将实现对基本代码的建议更改，在每次更改后审核网站，以测量它对网站速度的影响。</span><span class="sxs-lookup"><span data-stu-id="8e953-216">In this section, you implement the recommended changes to the codebase, auditing the site after each change to measure how it affects site speed.</span></span>  

### <span data-ttu-id="8e953-217">启用文本压缩</span><span class="sxs-lookup"><span data-stu-id="8e953-217">Enable text compression</span></span>   

<span data-ttu-id="8e953-218">你的报告表明，避免巨大的网络负载是改善页面性能的首要机会之一。</span><span class="sxs-lookup"><span data-stu-id="8e953-218">Your report says that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="8e953-219">启用文本压缩是提高页面性能的机会。</span><span class="sxs-lookup"><span data-stu-id="8e953-219">Enabling text compression is an opportunity to improve the performance of the page.</span></span>  

<span data-ttu-id="8e953-220">文本压缩是指在通过网络发送文本文件之前减小或压缩该文件的大小。</span><span class="sxs-lookup"><span data-stu-id="8e953-220">Text compression is when you reduce, or compress, the size of a text file before sending it over the network.</span></span>  <span data-ttu-id="8e953-221">类似于通过电子邮件对文件夹进行电子邮件压缩以减小大小。</span><span class="sxs-lookup"><span data-stu-id="8e953-221">Kind of like how you might zip a folder before emailing it to reduce the size.</span></span>  

<span data-ttu-id="8e953-222">启用压缩之前，可通过以下几种方法来手动检查文本资源是否已压缩。</span><span class="sxs-lookup"><span data-stu-id="8e953-222">Before you enable compression, here are a couple of ways to manually check whether text resources are compressed.</span></span>  

1.  <span data-ttu-id="8e953-223">选择 " **网络** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8e953-223">Select the **Network** tab.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network.msft.png" alt-text="网络面板" lightbox="../media/speed-glitch-tony-remix-network.msft.png":::
       <span data-ttu-id="8e953-225">**网络**面板</span><span class="sxs-lookup"><span data-stu-id="8e953-225">The **Network** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-226">选择 " **网络设置** " 图标。</span><span class="sxs-lookup"><span data-stu-id="8e953-226">Select the **Network setting** icon.</span></span>  
1.  <span data-ttu-id="8e953-227">选中 " **使用大请求行** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="8e953-227">Select the **Use Large Request Rows** checkbox.</span></span>  <span data-ttu-id="8e953-228">网络请求表中的行的高度增加。</span><span class="sxs-lookup"><span data-stu-id="8e953-228">The height of the rows in the table of network requests increases.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png" alt-text="网络请求表中的较大行数" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png":::
       <span data-ttu-id="8e953-230">网络请求表中的较大行数</span><span class="sxs-lookup"><span data-stu-id="8e953-230">Large rows in the network requests table</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-231">如果在网络请求表中看不到 " **大小** " 列，请单击表标题，然后选择 " **大小**"。</span><span class="sxs-lookup"><span data-stu-id="8e953-231">If you do not see the **Size** column in the table of network requests, click the table header and then select **Size**.</span></span>  

<span data-ttu-id="8e953-232">每个 " **大小** " 单元格显示两个值。</span><span class="sxs-lookup"><span data-stu-id="8e953-232">Each **Size** cell shows two values.</span></span>  <span data-ttu-id="8e953-233">最大值是已下载资源的大小。</span><span class="sxs-lookup"><span data-stu-id="8e953-233">The top value is the size of the downloaded resource.</span></span>  
<span data-ttu-id="8e953-234">下限值是未压缩资源的大小。</span><span class="sxs-lookup"><span data-stu-id="8e953-234">The bottom value is the size of the uncompressed resource.</span></span>  <span data-ttu-id="8e953-235">如果两个值相同，则该资源在通过网络发送时不会被压缩。</span><span class="sxs-lookup"><span data-stu-id="8e953-235">If the two values are the same, then the resource is not being compressed when it is sent over the network.</span></span>  <span data-ttu-id="8e953-236">例如，在上图中，的上限和下限值为 `bundle.js` `1.2 MB` 和 `1.2 MB` 。</span><span class="sxs-lookup"><span data-stu-id="8e953-236">For example, in the previous figure, the top and bottom values for `bundle.js` are `1.2 MB` and `1.2 MB`.</span></span>  

<span data-ttu-id="8e953-237">通过检查资源的 HTTP 标头来检查压缩：</span><span class="sxs-lookup"><span data-stu-id="8e953-237">Check for compression by inspecting the HTTP headers of a resource:</span></span>  

1.  <span data-ttu-id="8e953-238">选择 " **bundle.js**"。</span><span class="sxs-lookup"><span data-stu-id="8e953-238">Select **bundle.js**.</span></span>  
1.  <span data-ttu-id="8e953-239">选择 " **页眉** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8e953-239">Select the **Headers** tab.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png" alt-text=""页眉" 选项卡" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png":::
       <span data-ttu-id="8e953-241">" **页眉** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="8e953-241">The **Headers** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-242">在 " **响应标题** " 部分 `content-encoding` 中搜索标题。</span><span class="sxs-lookup"><span data-stu-id="8e953-242">Search the **Response Headers** section for a `content-encoding` header.</span></span>  <span data-ttu-id="8e953-243">你应该看不到，这种情况未 `bundle.js` 压缩。</span><span class="sxs-lookup"><span data-stu-id="8e953-243">You should not see one, meaning that `bundle.js` was not compressed.</span></span>  <span data-ttu-id="8e953-244">当资源被压缩时，此页眉通常设置为 `gzip` 、 `deflate` 或 `br` 。</span><span class="sxs-lookup"><span data-stu-id="8e953-244">When a resource is compressed, this header is usually set to `gzip`, `deflate`, or `br`.</span></span>  <span data-ttu-id="8e953-245">有关这些值的说明，请参阅 [指令][MDNContentEncodingDirectives] 。</span><span class="sxs-lookup"><span data-stu-id="8e953-245">See [Directives][MDNContentEncodingDirectives] for an explanation of these values.</span></span>  

<span data-ttu-id="8e953-246">有足够的说明。</span><span class="sxs-lookup"><span data-stu-id="8e953-246">Enough with the explanations.</span></span>  <span data-ttu-id="8e953-247">进行更改的时间！</span><span class="sxs-lookup"><span data-stu-id="8e953-247">Time to make some changes!</span></span>  <span data-ttu-id="8e953-248">通过添加几行代码来启用文本压缩：</span><span class="sxs-lookup"><span data-stu-id="8e953-248">Enable text compression by adding a couple of lines of code:</span></span>  

1.  <span data-ttu-id="8e953-249">在 "编辑器" 选项卡中，单击 " **server.js**"。</span><span class="sxs-lookup"><span data-stu-id="8e953-249">In the editor tab, click **server.js**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js.msft.png" alt-text="编辑 server.js" lightbox="../media/speed-glitch-tony-remix-server-js.msft.png":::
       <span data-ttu-id="8e953-251">编辑</span><span class="sxs-lookup"><span data-stu-id="8e953-251">Edit</span></span> `server.js`  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-252">将以下代码添加到 **server.js**。</span><span class="sxs-lookup"><span data-stu-id="8e953-252">Add the following code to **server.js**.</span></span>  <span data-ttu-id="8e953-253">请确保放 `app.use(compression())` 在前面 `app.use(express.static('build'))` 。</span><span class="sxs-lookup"><span data-stu-id="8e953-253">Make sure to put `app.use(compression())` before `app.use(express.static('build'))`.</span></span>  

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
    > <span data-ttu-id="8e953-254">通常，你必须通过类似的方式安装 `compression` 程序包 `npm i -S compression` ，但已为你执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8e953-254">Usually, you have to install the `compression` package via something like `npm i -S compression`, but this has already been done for you.</span></span>  
    
1.  <span data-ttu-id="8e953-255">请等待部署新版本的网站。</span><span class="sxs-lookup"><span data-stu-id="8e953-255">Wait for Glitch to deploy the new build of the site.</span></span>  <span data-ttu-id="8e953-256">" **工具** " 旁边的 "别致" 动画意味着该网站将重新构建并重新部署。</span><span class="sxs-lookup"><span data-stu-id="8e953-256">The fancy animation next to **Tools** means that the site is getting rebuilt and redeployed.</span></span>  <span data-ttu-id="8e953-257">当 " **工具** " 旁边的动画消失时，更改即已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="8e953-257">The change is ready when the animation next to **Tools** goes away.</span></span>  <span data-ttu-id="8e953-258">再次选择 " **显示** "，然后 **在新窗口中** 再次选择。</span><span class="sxs-lookup"><span data-stu-id="8e953-258">Select **Show** and select **In a New Window** again.</span></span>  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js-edited.msft.png" alt-text="The animation that indicates that the site is getting built" lightbox="../media/speed-glitch-tony-remix-server-js-edited.msft.png":::
       The animation that indicates that the site is getting built  
    :::image-end:::  
    -->  
    
<span data-ttu-id="8e953-259">使用之前学习的工作流手动检查压缩是否正常工作：</span><span class="sxs-lookup"><span data-stu-id="8e953-259">Use the workflows that you learned earlier to manually check that the compression is working:</span></span>  

1.  <span data-ttu-id="8e953-260">返回到 "演示" 选项卡，然后重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="8e953-260">Go back to the demo tab and reload the page.</span></span>  <span data-ttu-id="8e953-261">现在，" **大小** " 列应显示类似于文本资源的2个不同值 `bundle.js` 。</span><span class="sxs-lookup"><span data-stu-id="8e953-261">The **Size** column should now show 2 different values for text resources like `bundle.js`.</span></span>  <span data-ttu-id="8e953-262">在下面的图中，的最大值 `256 KB` `bundle.js` 是通过网络发送的文件的大小，其最小值 `1.2 MB` 是未压缩的文件大小。</span><span class="sxs-lookup"><span data-stu-id="8e953-262">In the figure after the following, the top value of `256 KB` for `bundle.js` is the size of the file that was sent over the network, and the bottom value of `1.2 MB` is the uncompressed file size.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-main.msft.png" alt-text=""大小" 列现在为文本资源显示2个不同的值" lightbox="../media/speed-glitch-tony-remix-network-main.msft.png":::
       <span data-ttu-id="8e953-264">" **大小** " 列现在为文本资源显示2个不同的值</span><span class="sxs-lookup"><span data-stu-id="8e953-264">The **Size** column now shows 2 different values for text resources</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-265">现在，的 " **响应标题** " 部分 `bundle.js` 应包括 `content-encoding: gzip` 标题。</span><span class="sxs-lookup"><span data-stu-id="8e953-265">The **Response Headers** section for `bundle.js` should now include a `content-encoding: gzip` header.</span></span>
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png" alt-text=""响应标题" 部分现在包含一个内容编码标题" lightbox="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png":::
       <span data-ttu-id="8e953-267">" **响应标题** " 部分现在包含一个内容编码标题</span><span class="sxs-lookup"><span data-stu-id="8e953-267">The **Response Headers** section now contains a content-encoding header</span></span>  
    :::image-end:::  
    
<span data-ttu-id="8e953-268">再次审核页面，以衡量影响文本压缩对页面加载性能有何种影响：</span><span class="sxs-lookup"><span data-stu-id="8e953-268">Audit the page again to measure what kind of impact text compression has on the load performance of the page:</span></span>  

1.  <span data-ttu-id="8e953-269">选择 " **审核** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8e953-269">Select the **Audits** tab.</span></span>  
1.  <span data-ttu-id="8e953-270">选择 " **执行审核** \ (![ 执行审核 ][ImagePerformIcon] \ ) 。</span><span class="sxs-lookup"><span data-stu-id="8e953-270">Select **Perform an audit** \(![Perform an audit][ImagePerformIcon]\).</span></span>  
1.  <span data-ttu-id="8e953-271">保持设置与以前一样。</span><span class="sxs-lookup"><span data-stu-id="8e953-271">Leave the settings the same as before.</span></span>  
1.  <span data-ttu-id="8e953-272">选择 " **运行审核**"。</span><span class="sxs-lookup"><span data-stu-id="8e953-272">Select **Run audit**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png" alt-text="启用文本压缩后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png":::
       <span data-ttu-id="8e953-274">启用文本压缩后的审核报告</span><span class="sxs-lookup"><span data-stu-id="8e953-274">An Audits report after enabling text compression</span></span>  
    :::image-end:::  
    
<!--  Woohoo!  That looks like progress.  -->  <span data-ttu-id="8e953-275">您的整体性能分数应增加，这意味着网站的速度会更快。</span><span class="sxs-lookup"><span data-stu-id="8e953-275">Your overall performance score should have increased, meaning that the site is getting faster.</span></span>  

#### <span data-ttu-id="8e953-276">现实世界中的文本压缩</span><span class="sxs-lookup"><span data-stu-id="8e953-276">Text compression in the real world</span></span>   

<span data-ttu-id="8e953-277">大多数服务器确实都有简单的修复程序，例如用于启用压缩的修补程序！</span><span class="sxs-lookup"><span data-stu-id="8e953-277">Most servers really do have simple fixes like this for enabling compression!</span></span>  <span data-ttu-id="8e953-278">只需执行有关如何配置用于压缩文本的任何服务器的搜索。</span><span class="sxs-lookup"><span data-stu-id="8e953-278">Just do a search on how to configure whatever server you use to compress text.</span></span>  

### <span data-ttu-id="8e953-279">调整图像大小</span><span class="sxs-lookup"><span data-stu-id="8e953-279">Resize images</span></span>   

<span data-ttu-id="8e953-280">你的报表指示避免大量网络负载是提高页面性能的最高机会之一。</span><span class="sxs-lookup"><span data-stu-id="8e953-280">Your report indicates that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="8e953-281">调整图像大小有助于减小网络负载的大小。</span><span class="sxs-lookup"><span data-stu-id="8e953-281">Resizing images helps reduce the size of the network payload.</span></span>  <span data-ttu-id="8e953-282">如果你的用户在移动设备屏幕上查看你的图像，该屏幕为 500-像素宽度，则在发送1500像素范围的图像时，实际上没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="8e953-282">If your user is viewing your images on a mobile device screen that is 500-pixels-wide, there is really no point in sending a 1500-pixel-wide image.</span></span>  <span data-ttu-id="8e953-283">理想情况下，发送500像素宽的图像。</span><span class="sxs-lookup"><span data-stu-id="8e953-283">Ideally, you send a 500-pixel-wide image, at most.</span></span>  

1.  <span data-ttu-id="8e953-284">在报表中，单击 " **避免大量网络负载** " 以查看应调整哪些图像的大小。</span><span class="sxs-lookup"><span data-stu-id="8e953-284">In your report, click **Avoid enormous network payloads** to see which images should be resized.</span></span>  <span data-ttu-id="8e953-285">它看起来是两个 jpg 文件超过了 2000 KB，这比所需的更大。</span><span class="sxs-lookup"><span data-stu-id="8e953-285">It looks like 2 of the jpg files are over 2000 KB, which is bigger than necessary.</span></span>  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png" alt-text="Details about the properly size images opportunity" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png":::
       Details about the properly size images opportunity  
    :::image-end:::  
    -->
    
1.  <span data-ttu-id="8e953-286">返回到 "编辑器" 选项卡中的 "打开" `src/model.js` 。</span><span class="sxs-lookup"><span data-stu-id="8e953-286">Back in the editor tab, open `src/model.js`.</span></span>  
1.  <span data-ttu-id="8e953-287">用 `const dir = 'small'` 取代 `const dir = 'big'`。</span><span class="sxs-lookup"><span data-stu-id="8e953-287">Replace `const dir = 'big'` with `const dir = 'small'`.</span></span>  <span data-ttu-id="8e953-288">此目录包含已调整大小的相同图像的副本。</span><span class="sxs-lookup"><span data-stu-id="8e953-288">This directory contains copies of the same images which have been resized.</span></span>  
1.  <span data-ttu-id="8e953-289">再次审核页面以查看此更改对加载性能的影响。</span><span class="sxs-lookup"><span data-stu-id="8e953-289">Audit the page again to see how this change affects load performance.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-compression-small-images-audits-performance.msft.png" alt-text="调整图像大小后的审核报告" lightbox="../media/speed-glitch-compression-small-images-audits-performance.msft.png":::
       <span data-ttu-id="8e953-291">调整图像大小后的审核报告</span><span class="sxs-lookup"><span data-stu-id="8e953-291">An Audits report after resizing images</span></span>  
    :::image-end:::  
    
<span data-ttu-id="8e953-292">看起来只有更改对整体性能分数有轻微影响。</span><span class="sxs-lookup"><span data-stu-id="8e953-292">Looks like the change only has a minor affect on the overall performance score.</span></span>  <span data-ttu-id="8e953-293">但是，分数没有明显显示的一项是保存用户的网络数据量。</span><span class="sxs-lookup"><span data-stu-id="8e953-293">However, one thing that the score does not show clearly is how much network data you are saving your users.</span></span>  <span data-ttu-id="8e953-294">旧照片的总大小约为 5.3 mb，而现在仅限于0.18 兆字节。</span><span class="sxs-lookup"><span data-stu-id="8e953-294">The total size of the old photos was around 5.3 megabytes, whereas now it is only about 0.18 megabytes.</span></span>  

#### <span data-ttu-id="8e953-295">在现实世界中调整图像大小</span><span class="sxs-lookup"><span data-stu-id="8e953-295">Resizing images in the real world</span></span>   

<span data-ttu-id="8e953-296">对于小型应用，像这样做时，执行一次性调整大小的方式可能足够好。</span><span class="sxs-lookup"><span data-stu-id="8e953-296">For a small app, doing a one-off resize like this may be good enough.</span></span>  <span data-ttu-id="8e953-297">但对于大型应用，这显然是不可缩放的。</span><span class="sxs-lookup"><span data-stu-id="8e953-297">But for a large app, this obviously is not scalable.</span></span>  <span data-ttu-id="8e953-298">下面是在大型应用中管理图像的一些策略：</span><span class="sxs-lookup"><span data-stu-id="8e953-298">Here are some strategies for managing images in large apps:</span></span>  

*   <span data-ttu-id="8e953-299">在生成过程中调整图像大小。</span><span class="sxs-lookup"><span data-stu-id="8e953-299">Resize images during your build process.</span></span>  
*   <span data-ttu-id="8e953-300">在生成过程中创建多个大小的每个图像，然后 `srcset` 在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="8e953-300">Create multiple sizes of each image during the build process and then use `srcset` in your code.</span></span>  <span data-ttu-id="8e953-301">在运行时，浏览器负责选择最适合设备的大小。</span><span class="sxs-lookup"><span data-stu-id="8e953-301">At runtime, the browser takes care of choosing which size is best for the device.</span></span>  
    <!--See [Relative-sized images][relative].  -->
    
<!--[relative]: /web/fundamentals/design-and-ux/responsive/images#relative_sized_images  -->  

*   <span data-ttu-id="8e953-302">使用图像 CDN，允许你在请求图像时动态调整图像大小。</span><span class="sxs-lookup"><span data-stu-id="8e953-302">Use an image CDN that lets you dynamically resize an image when you request it.</span></span>  
*   <span data-ttu-id="8e953-303">最起码，优化每个图像。</span><span class="sxs-lookup"><span data-stu-id="8e953-303">At the very least, optimize each image.</span></span>  <span data-ttu-id="8e953-304">这可能会带来巨大的节约。</span><span class="sxs-lookup"><span data-stu-id="8e953-304">This may create huge savings.</span></span>  
  <span data-ttu-id="8e953-305">优化是指通过可减小图像文件大小的特殊程序运行图像。</span><span class="sxs-lookup"><span data-stu-id="8e953-305">Optimization is when you run an image through a special program that reduces the size of the image file.</span></span>  <span data-ttu-id="8e953-306">有关更多提示，请参阅 [基本图像优化][EssentialImageOptimization] 。</span><span class="sxs-lookup"><span data-stu-id="8e953-306">See [Essential Image Optimization][EssentialImageOptimization] for more tips.</span></span>  
    
### <span data-ttu-id="8e953-307">消除呈现阻止资源</span><span class="sxs-lookup"><span data-stu-id="8e953-307">Eliminate render-blocking resources</span></span>   

<span data-ttu-id="8e953-308">您的最新报告表明，消除呈现阻止资源现在是最大的机会。</span><span class="sxs-lookup"><span data-stu-id="8e953-308">Your latest report says that eliminating render-blocking resources is now the biggest opportunity.</span></span>  

<span data-ttu-id="8e953-309">呈现阻止资源是浏览器在显示页面之前必须下载、分析和运行的外部 JavaScript 或 CSS 文件。</span><span class="sxs-lookup"><span data-stu-id="8e953-309">A render-blocking resource is an external JavaScript or CSS file that the browser must download, parse, and run before it displays the page.</span></span>  <span data-ttu-id="8e953-310">目标是仅运行正确显示页面所需的核心 CSS 和 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="8e953-310">The goal is to only run the core CSS and JavaScript code that is required to display the page properly.</span></span>  

<span data-ttu-id="8e953-311">然后，第一个任务是查找不需要在页面加载时运行的代码。</span><span class="sxs-lookup"><span data-stu-id="8e953-311">The first task, then, is to find code that you do not need to run on page load.</span></span>  

1.  <span data-ttu-id="8e953-312">选择 " **消除呈现阻止资源** " 以查看阻止的资源：</span><span class="sxs-lookup"><span data-stu-id="8e953-312">Select **Eliminate render-blocking resources** to see the resources that are blocking:</span></span>  
    `lodash.js` <span data-ttu-id="8e953-313">和 `jquery.js` 。</span><span class="sxs-lookup"><span data-stu-id="8e953-313">and `jquery.js`.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png" alt-text="有关消除呈现阻止资源商机的详细信息" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png":::
       <span data-ttu-id="8e953-315">有关 **消除呈现阻止资源** 商机的详细信息</span><span class="sxs-lookup"><span data-stu-id="8e953-315">More information about the **Eliminate render-blocking resources** opportunity</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-316">按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "命令" 菜单，开始键入 `Coverage` ，然后选择 "**显示覆盖率**"。</span><span class="sxs-lookup"><span data-stu-id="8e953-316">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, start typing `Coverage`, and then select **Show Coverage**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png" alt-text="从 "审核" 面板中打开 "命令" 菜单" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png":::
       <span data-ttu-id="8e953-318">从 " **审核** " 面板中打开 "命令" 菜单</span><span class="sxs-lookup"><span data-stu-id="8e953-318">Open the Command Menu from the **Audits** panel</span></span>  
    :::image-end:::  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png" alt-text=""覆盖范围" 选项卡" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png":::
       <span data-ttu-id="8e953-320">" **覆盖范围** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="8e953-320">The **Coverage** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-321">选择 " **刷新** \ (![ 刷新 ][ImageRefreshIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="8e953-321">Select **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  <span data-ttu-id="8e953-322">" **覆盖范围** " 选项卡提供了在 `bundle.js` `jquery.js` `lodash.js` 页面加载期间、和运行的代码中的多少概述。</span><span class="sxs-lookup"><span data-stu-id="8e953-322">The **Coverage** tab provides an overview of how much of the code in `bundle.js`, `jquery.js`, and `lodash.js` runs while the page loads.</span></span>  <span data-ttu-id="8e953-323">在以下的图中，将不会分别使用76% 和30% 的 jQuery 和 Lodash 文件。</span><span class="sxs-lookup"><span data-stu-id="8e953-323">In the figure after the following, about 76% and 30% of the jQuery and Lodash files are not used, respectively.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png" alt-text="覆盖范围报告" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png":::
       <span data-ttu-id="8e953-325">覆盖范围报告</span><span class="sxs-lookup"><span data-stu-id="8e953-325">The Coverage report</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-326">选择 " **jquery.js** " 行。</span><span class="sxs-lookup"><span data-stu-id="8e953-326">Select the **jquery.js** row.</span></span>  <span data-ttu-id="8e953-327">DevTools 将在 "源" 面板中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="8e953-327">DevTools opens the file in the Sources panel.</span></span>  <span data-ttu-id="8e953-328">如果它旁边有一个蓝色条，则运行一行代码。</span><span class="sxs-lookup"><span data-stu-id="8e953-328">A line of code ran if it has a blue bar next to it.</span></span>  <span data-ttu-id="8e953-329">红色条表示它未运行，并且在页面加载时绝对不需要。</span><span class="sxs-lookup"><span data-stu-id="8e953-329">A red bar means it was not run, and is definitely not needed on page load.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png" alt-text="在 "源" 面板中查看 jQuery 文件" lightbox="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png":::
       <span data-ttu-id="8e953-331">在 " **源** " 面板中查看 jQuery 文件</span><span class="sxs-lookup"><span data-stu-id="8e953-331">Viewing the jQuery file in the **Sources** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-332">按位滚动 jQuery 代码。</span><span class="sxs-lookup"><span data-stu-id="8e953-332">Scroll through the jQuery code a bit.</span></span>  <span data-ttu-id="8e953-333">某些显示 "运行" 的行实际上只是批注。</span><span class="sxs-lookup"><span data-stu-id="8e953-333">Some of the lines that get "run" are actually just comments.</span></span>  <span data-ttu-id="8e953-334">通过 minifier 中的代码运行此代码，可查看批注是减小此文件大小的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="8e953-334">Running this code through a minifier that strips comments is another way to reduce the size of this file.</span></span>  

<span data-ttu-id="8e953-335">简言之，当你使用自己的代码时，"覆盖率" 选项卡可帮助你逐行分析代码，并仅发送页面加载所需的代码。</span><span class="sxs-lookup"><span data-stu-id="8e953-335">In short, when you are working with your own code, the Coverage tab helps you analyze your code, line-by-line, and only ship the code that is needed for page load.</span></span>  

<span data-ttu-id="8e953-336">`jquery.js`和文件是否还 `lodash.js` 需要加载页面？</span><span class="sxs-lookup"><span data-stu-id="8e953-336">Are the `jquery.js` and `lodash.js` files even needed to load the page?</span></span>  <span data-ttu-id="8e953-337">"请求阻止" 选项卡显示资源不可用时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="8e953-337">The Request Blocking tab displays what happens when resources are not available.</span></span>  

1.  <span data-ttu-id="8e953-338">选择 " **网络** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8e953-338">Select the **Network** tab.</span></span>  
1.  <span data-ttu-id="8e953-339">按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) ，再次打开 "命令" 菜单。</span><span class="sxs-lookup"><span data-stu-id="8e953-339">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu again.</span></span>  
1.  <span data-ttu-id="8e953-340">开始键入 `blocking` ，然后选择 " **显示请求阻止**"。</span><span class="sxs-lookup"><span data-stu-id="8e953-340">Start typing `blocking` and then select **Show Request Blocking**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png" alt-text=""请求阻止" 选项卡" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png":::
       <span data-ttu-id="8e953-342">" **请求阻止** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="8e953-342">The **Request Blocking** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-343">选择 " **添加模式** \ (![ 添加模式 ][ImageAddPatternIcon] \ ) "，键入 `/libs/*` ，然后按 `Enter` 进行确认。</span><span class="sxs-lookup"><span data-stu-id="8e953-343">Select **Add Pattern** \(![Add Pattern][ImageAddPatternIcon]\), type `/libs/*`, and then press `Enter` to confirm.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png" alt-text="添加模式以阻止任何对库目录的请求" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png":::
       <span data-ttu-id="8e953-345">添加模式以阻止对目录的任何请求 `libs`</span><span class="sxs-lookup"><span data-stu-id="8e953-345">Add a pattern to block any request to the `libs` directory</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-346">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="8e953-346">Refresh the page.</span></span>  <span data-ttu-id="8e953-347">JQuery 和 Lodash 请求是红色的，这意味着请求被阻止。</span><span class="sxs-lookup"><span data-stu-id="8e953-347">The jQuery and Lodash requests are red, meaning that the requests were blocked.</span></span>   <span data-ttu-id="8e953-348">页面仍在加载，并且是交互式的，因此看起来不需要这些资源！</span><span class="sxs-lookup"><span data-stu-id="8e953-348">The page still loads and is interactive, so it looks like these resources are not needed whatsoever!</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png" alt-text=""网络" 面板显示请求已被阻止" lightbox="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png":::
       <span data-ttu-id="8e953-350">" **网络** " 面板显示请求已被阻止</span><span class="sxs-lookup"><span data-stu-id="8e953-350">The **Network** panel shows that the requests have been blocked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-351">选择 " **删除所有模式** \ (![ 删除所有模式 ][ImageRemoveIcon] \ ) " 删除 `/libs/*` 阻止模式。</span><span class="sxs-lookup"><span data-stu-id="8e953-351">Select **Remove all patterns** \(![Remove all patterns][ImageRemoveIcon]\) to delete the `/libs/*` blocking pattern.</span></span>  
    
<span data-ttu-id="8e953-352">通常情况下，当任何给定资源不可用时，"请求阻止" 选项卡将非常有用，可用于模拟页面的行为方式。</span><span class="sxs-lookup"><span data-stu-id="8e953-352">In general, the Request Blocking tab is useful for simulating how your page behaves when any given resource is not available.</span></span>  

<span data-ttu-id="8e953-353">现在，从代码中删除对这些文件的引用，然后再次审核页面：</span><span class="sxs-lookup"><span data-stu-id="8e953-353">Now, remove the references to these files from the code and audit the page again:</span></span>  

1.  <span data-ttu-id="8e953-354">返回到 "编辑器" 选项卡中的 "打开" `template.html` 。</span><span class="sxs-lookup"><span data-stu-id="8e953-354">Back in the editor tab, open `template.html`.</span></span>  
1.  <span data-ttu-id="8e953-355">删除 `<script src="/libs/lodash.js">` 和 `<script src="/libs/jquery.js"></script>`。</span><span class="sxs-lookup"><span data-stu-id="8e953-355">Delete `<script src="/libs/lodash.js">` and `<script src="/libs/jquery.js"></script>`.</span></span>  
1.  <span data-ttu-id="8e953-356">等待网站重新构建和重新部署。</span><span class="sxs-lookup"><span data-stu-id="8e953-356">Wait for the site to re-build and re-deploy.</span></span>  
1.  <span data-ttu-id="8e953-357">从 " **审核** " 面板中再次审核页面。</span><span class="sxs-lookup"><span data-stu-id="8e953-357">Audit the page again from the **Audits** panel.</span></span>  <span data-ttu-id="8e953-358">您的整体成绩将再次改进。</span><span class="sxs-lookup"><span data-stu-id="8e953-358">Your overall score should have improved again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png" alt-text="删除 "呈现阻止" 资源后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png":::
       <span data-ttu-id="8e953-360">删除 "呈现阻止" 资源后的 **审核** 报告</span><span class="sxs-lookup"><span data-stu-id="8e953-360">An **Audits** report after removing the render-blocking resources</span></span>  
    :::image-end:::  
    
#### <span data-ttu-id="8e953-361">优化现实世界中的关键呈现路径</span><span class="sxs-lookup"><span data-stu-id="8e953-361">Optimizing the Critical Rendering Path in the real-world</span></span>   

<span data-ttu-id="8e953-362">**关键呈现路径**是指加载页面所需的代码。</span><span class="sxs-lookup"><span data-stu-id="8e953-362">The **Critical Rendering Path** refers to the code that you need to load a page.</span></span>  <span data-ttu-id="8e953-363">通常，仅在页面加载期间传输关键代码，然后延缓加载所有其他内容，从而加快页面负载。</span><span class="sxs-lookup"><span data-stu-id="8e953-363">In general, speed up page load by only shipping critical code during the page load, and then lazy-loading everything else.</span></span>  

<!--[CRP]: /web/fundamentals/performance/critical-rendering-path/  -->  

*   <span data-ttu-id="8e953-364">你可能无法找到能够完全删除的脚本，但你可能会发现在页面加载期间不需要请求的多个脚本，而是可能会异步请求。</span><span class="sxs-lookup"><span data-stu-id="8e953-364">It is unlikely that you are able to find scripts that you are able to remove outright, but you may find many scripts that you do not need to request during the page load, and instead may be requested asynchronously.</span></span>  <!--See [Using async or defer][async].  -->  
*   <span data-ttu-id="8e953-365">如果你使用的是框架，请检查它是否具有生产模式。</span><span class="sxs-lookup"><span data-stu-id="8e953-365">If you are using a framework, check if it has a production mode.</span></span>  <span data-ttu-id="8e953-366">此模式可能使用 [树形握手][WebpackTreeShaking] 之类的功能来消除阻止关键呈现的不必要代码。</span><span class="sxs-lookup"><span data-stu-id="8e953-366">This mode may use a feature such as [tree shaking][WebpackTreeShaking] in order to eliminate unnecessary code that is blocking the critical render.</span></span>  
    
<!--[async]: /web/fundamentals/performance/optimizing-content-efficiency/loading-third-party-javascript/#use_async_or_defer  -->  

### <span data-ttu-id="8e953-367">执行较少的主线程工作</span><span class="sxs-lookup"><span data-stu-id="8e953-367">Do less main thread work</span></span>   

<span data-ttu-id="8e953-368">您的最新报告显示了 "商机" 部分中的一些小的可能节约，但如果您在 "诊断" 部分中向下查看，那么最大的瓶颈似乎是太多的主线程活动。</span><span class="sxs-lookup"><span data-stu-id="8e953-368">Your latest report shows some minor potential savings in the Opportunities section, but if you look down in the Diagnostics section, it looks like the biggest bottleneck is too much main thread activity.</span></span>  

<span data-ttu-id="8e953-369">主线程是浏览器完成显示页面所需的大部分工作（如分析和运行 HTML、CSS 和 JavaScript）的位置。</span><span class="sxs-lookup"><span data-stu-id="8e953-369">The main thread is where the browser does most of the work needed to display a page, such as parsing and running HTML, CSS, and JavaScript.</span></span>  

<span data-ttu-id="8e953-370">目标是使用 "性能" 面板分析主线程在页面加载期间执行的工作，并查找推迟或删除不必要的工作的方法。</span><span class="sxs-lookup"><span data-stu-id="8e953-370">The goal is to use the Performance panel to analyze what work the main thread is doing while the page loads, and find ways to defer or remove unnecessary work.</span></span>  

1.  <span data-ttu-id="8e953-371">选择 " **性能** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8e953-371">Select the **Performance** tab.</span></span>  
1.  <span data-ttu-id="8e953-372">选择 " **捕获设置** \ (![ 捕获设置 ][ImageCaptureIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="8e953-372">Select **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\).</span></span>  
1.  <span data-ttu-id="8e953-373">将 **网络** 设置为 **慢速 3g** 和 **CPU** **6x 减速**。</span><span class="sxs-lookup"><span data-stu-id="8e953-373">Set **Network** to **Slow 3G** and **CPU** to **6x slowdown**.</span></span>  <span data-ttu-id="8e953-374">移动设备通常比笔记本或桌面具有更多硬件约束，因此这些设置使你可以体验页面加载，就像使用的功能较少的设备一样。</span><span class="sxs-lookup"><span data-stu-id="8e953-374">Mobile devices typically have more hardware constraints than laptops or desktops, so these settings let you experience the page load as if you were using a less powerful device.</span></span>  
1.  <span data-ttu-id="8e953-375">选择 " **刷新** \ (![ 刷新 ][ImageRefreshIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="8e953-375">Select **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  <span data-ttu-id="8e953-376">DevTools 刷新页面，然后生成所有已执行工作的可视化效果，以便加载页面。</span><span class="sxs-lookup"><span data-stu-id="8e953-376">DevTools refreshes the page and then produces a visualization of all the work performed in order to load the page.</span></span>  <span data-ttu-id="8e953-377">此可视化对象称为 **跟踪**。</span><span class="sxs-lookup"><span data-stu-id="8e953-377">This visualization is referred to as the **trace**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png" alt-text="页面加载的性能面板跟踪" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png":::
       <span data-ttu-id="8e953-379">页面加载的 **性能** 面板跟踪</span><span class="sxs-lookup"><span data-stu-id="8e953-379">The **Performance** panel trace of the page load</span></span>  
    :::image-end:::  
    
<span data-ttu-id="8e953-380">跟踪按时间顺序从左到右显示活动。</span><span class="sxs-lookup"><span data-stu-id="8e953-380">The trace shows activity chronologically, from left to right.</span></span>  <span data-ttu-id="8e953-381">顶部的 FPS、CPU 和网络图概括介绍了每秒帧数、CPU 活动和网络活动。</span><span class="sxs-lookup"><span data-stu-id="8e953-381">The FPS, CPU, and NET charts at the top give you an overview of frames per second, CPU activity, and network activity.</span></span>  <span data-ttu-id="8e953-382">在下图中看到的黄色所选方块，CPU 与脚本活动完全繁忙。</span><span class="sxs-lookup"><span data-stu-id="8e953-382">The block of yellow selected that you see in the figure after the following, the CPU was completely busy with scripting activity.</span></span>  <span data-ttu-id="8e953-383">这是一条提示，您可以通过执行较少的 JavaScript 工作来加快页面负载。</span><span class="sxs-lookup"><span data-stu-id="8e953-383">This is a clue that you may be able to speed up page load by doing less JavaScript work.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png" alt-text="跟踪的概述部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png":::
   <span data-ttu-id="8e953-385">跟踪的概述部分</span><span class="sxs-lookup"><span data-stu-id="8e953-385">The Overview section of the trace</span></span>  
:::image-end:::  

<span data-ttu-id="8e953-386">调查跟踪以查找执行更少 JavaScript 工作的方法：</span><span class="sxs-lookup"><span data-stu-id="8e953-386">Investigate the trace to find ways to do less JavaScript work:</span></span>  

1.  <span data-ttu-id="8e953-387">选择 " **计时** " 部分将其展开。</span><span class="sxs-lookup"><span data-stu-id="8e953-387">Select the **Timings** section to expand it.</span></span>  <span data-ttu-id="8e953-388">根据可能有一组 [计时][MDNUserTimingApi] 对响应的情况，似乎 Tony 的应用正在使用响应的开发模式。</span><span class="sxs-lookup"><span data-stu-id="8e953-388">Based on the fact that there may be a bunch of [Timings][MDNUserTimingApi] measures from React, it seems like Tony's app is using the development mode of React.</span></span>  <span data-ttu-id="8e953-389">切换到 "响应生产模式" 可能会产生一些简单的性能获胜。</span><span class="sxs-lookup"><span data-stu-id="8e953-389">Switching to the production mode of React may yield some easy performance wins.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png" alt-text=""计时" 部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png":::
       <span data-ttu-id="8e953-391">" **计时** " 部分</span><span class="sxs-lookup"><span data-stu-id="8e953-391">The **Timings** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-392">再次选择 " **计时** " 以折叠该部分。</span><span class="sxs-lookup"><span data-stu-id="8e953-392">Select **Timings** again to collapse that section.</span></span>  
1.  <span data-ttu-id="8e953-393">浏览 **主** 分区。</span><span class="sxs-lookup"><span data-stu-id="8e953-393">Browse the **Main** section.</span></span>  <span data-ttu-id="8e953-394">此部分显示按时间顺序排列的主线程活动（从左到右）的日志。</span><span class="sxs-lookup"><span data-stu-id="8e953-394">This section shows a chronological log of main thread activity, from left to right.</span></span>  <span data-ttu-id="8e953-395">Y 轴 ("从上到下") 显示发生事件的原因。</span><span class="sxs-lookup"><span data-stu-id="8e953-395">The y-axis (top to bottom) shows why events occurred.</span></span>  <span data-ttu-id="8e953-396">例如，在 figyre 中，在以下情况下，事件导致运行该函数，导致运行，导致运行， `Evaluate Script` `(anonymous)` `(anonymous)` `__webpack__require__` 依此类推。</span><span class="sxs-lookup"><span data-stu-id="8e953-396">For example, in the figyre after the following, the `Evaluate Script` event caused the `(anonymous)` function to run, which caused `(anonymous)` to run, which caused `__webpack__require__` to run, and so on.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png" alt-text="主要部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png":::
       <span data-ttu-id="8e953-398">**主要**部分</span><span class="sxs-lookup"><span data-stu-id="8e953-398">The **Main** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8e953-399">向下滚动到 **主** 区域的底部。</span><span class="sxs-lookup"><span data-stu-id="8e953-399">Scroll down to the bottom of the **Main** section.</span></span>  <span data-ttu-id="8e953-400">使用框架时，大部分较高的活动都是由框架导致的，该框架通常不受控制。</span><span class="sxs-lookup"><span data-stu-id="8e953-400">When you use a framework, most of the upper activity is caused by the framework, which is usually out of your control.</span></span>  <span data-ttu-id="8e953-401">应用引发的活动通常位于底部。</span><span class="sxs-lookup"><span data-stu-id="8e953-401">The activity caused by your app is usually at the bottom.</span></span>  <span data-ttu-id="8e953-402">在此应用中，名为的函数似乎 `App` 导致了许多对函数的请求 `mineBitcoin` 。</span><span class="sxs-lookup"><span data-stu-id="8e953-402">In this app, it seems like a function named `App` is causing a lot of requests to a `mineBitcoin` function.</span></span>  <span data-ttu-id="8e953-403">听起来好像 Tony 可能会使用其风扇的设备来挖掘 cryptocurrency .。。</span><span class="sxs-lookup"><span data-stu-id="8e953-403">It sounds like Tony might be using the devices of his fans to mine cryptocurrency...</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png" alt-text="悬停在 mineBitcoin 活动上" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png":::
       <span data-ttu-id="8e953-405">悬停在 `mineBitcoin` 活动上</span><span class="sxs-lookup"><span data-stu-id="8e953-405">Hover on the `mineBitcoin` activity</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="8e953-406">尽管你的框架所提供的请求通常不在你的控件中，但有时你可能会导致框架运行效率较低下的方式构建你的应用。</span><span class="sxs-lookup"><span data-stu-id="8e953-406">Although the requests that your framework makes are usually out of your control, sometimes you may structure your app in a way that causes the framework to run inefficiently.</span></span>  <span data-ttu-id="8e953-407">将你的应用重构为高效使用框架是一种减少主线程工作的方法。</span><span class="sxs-lookup"><span data-stu-id="8e953-407">Restructuring your app to use the framework efficiently is a way to do less main thread work.</span></span>  <span data-ttu-id="8e953-408">但是，这需要深入了解你的框架的工作原理以及你自己的代码中所做的更改，以便更高效地使用框架。</span><span class="sxs-lookup"><span data-stu-id="8e953-408">However, this requires a deep understanding of how your framework works, and what kind of changes you make in your own code in order to use the framework more efficiently.</span></span>  
    
1.  <span data-ttu-id="8e953-409">展开 " **下** " 部分。</span><span class="sxs-lookup"><span data-stu-id="8e953-409">Expand the **Bottom-Up** section.</span></span>  <span data-ttu-id="8e953-410">此选项卡可分解最长时间的活动。</span><span class="sxs-lookup"><span data-stu-id="8e953-410">This tab breaks down what activities took up the most time.</span></span>  <span data-ttu-id="8e953-411">如果在下图中看不到任何内容，请单击 " **主要** 部分的标签"。</span><span class="sxs-lookup"><span data-stu-id="8e953-411">If you do not see anything in the Bottom-Up section, click the label for **Main** section.</span></span>  <span data-ttu-id="8e953-412">**自下而上**的部分仅显示当前已选择的任何活动或活动组的信息。</span><span class="sxs-lookup"><span data-stu-id="8e953-412">The **Bottom-Up** section only shows information for whatever activity, or group of activity, you have currently selected.</span></span>  <span data-ttu-id="8e953-413">例如，如果单击其中一个 `mineBitcoin` 活动，则 " **下移** " 部分将仅显示该活动的信息。</span><span class="sxs-lookup"><span data-stu-id="8e953-413">For example, if you clicked on one of the `mineBitcoin` activities, the **Bottom-Up** section is only going to show information for that one activity.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png" alt-text=""下" 选项卡" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png":::
       <span data-ttu-id="8e953-415">" **下** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="8e953-415">The **Bottom-Up** tab</span></span>  
    :::image-end:::  
    
<span data-ttu-id="8e953-416">" **自时间** " 列显示在每个活动中直接花费的时间量。</span><span class="sxs-lookup"><span data-stu-id="8e953-416">The **Self Time** column shows you how much time was spent directly in each activity.</span></span>  <span data-ttu-id="8e953-417">例如，在下图中，大约63% 的主线程时间被用在该 `mineBitcoin` 函数上。</span><span class="sxs-lookup"><span data-stu-id="8e953-417">For example, in the following figure, about 63% of main thread time was spent on the `mineBitcoin` function.</span></span>  

<span data-ttu-id="8e953-418">了解使用生产模式和减少 JavaScript 活动的时间可能会加速页面加载。</span><span class="sxs-lookup"><span data-stu-id="8e953-418">Time to see whether using production mode and reducing JavaScript activity may speed up the page load.</span></span>  <span data-ttu-id="8e953-419">从生产模式开始：</span><span class="sxs-lookup"><span data-stu-id="8e953-419">Start with production mode:</span></span>  

1.  <span data-ttu-id="8e953-420">在 "编辑器" 选项卡中，打开 `webpack.config.js` 。</span><span class="sxs-lookup"><span data-stu-id="8e953-420">In the editor tab, open `webpack.config.js`.</span></span>  
1.  <span data-ttu-id="8e953-421">将 `"mode":"development"` 更改为 `"mode":"production"`。</span><span class="sxs-lookup"><span data-stu-id="8e953-421">Change `"mode":"development"` to `"mode":"production"`.</span></span>  
1.  <span data-ttu-id="8e953-422">等待部署新版本。</span><span class="sxs-lookup"><span data-stu-id="8e953-422">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="8e953-423">再次审核该页面。</span><span class="sxs-lookup"><span data-stu-id="8e953-423">Audit the page again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png" alt-text="将 webpack 配置为使用生产模式后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png":::
       <span data-ttu-id="8e953-425">将 webpack 配置为使用生产模式后的审核报告</span><span class="sxs-lookup"><span data-stu-id="8e953-425">An Audits report after configuring webpack to use production mode</span></span>  
    :::image-end:::  
    
<span data-ttu-id="8e953-426">通过删除以下请求来减少 JavaScript 活动 `mineBitcoin` ：</span><span class="sxs-lookup"><span data-stu-id="8e953-426">Reduce JavaScript activity by removing the request to `mineBitcoin`:</span></span>  

1.  <span data-ttu-id="8e953-427">在 "编辑器" 选项卡中，打开 `src/App.jsx` 。</span><span class="sxs-lookup"><span data-stu-id="8e953-427">In the editor tab, open `src/App.jsx`.</span></span>  
1.  <span data-ttu-id="8e953-428">在中将请求注释为 `this.mineBitcoin(1500)` `constructor` 。</span><span class="sxs-lookup"><span data-stu-id="8e953-428">Comment out the request to `this.mineBitcoin(1500)` in the `constructor`.</span></span>  
1.  <span data-ttu-id="8e953-429">等待部署新版本。</span><span class="sxs-lookup"><span data-stu-id="8e953-429">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="8e953-430">再次审核该页面。</span><span class="sxs-lookup"><span data-stu-id="8e953-430">Audit the page again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png" alt-text="删除不必要的 JavaScript 工作后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png":::
       <span data-ttu-id="8e953-432">删除不必要的 JavaScript 工作后的审核报告</span><span class="sxs-lookup"><span data-stu-id="8e953-432">An Audits report after removing unnecessary JavaScript work</span></span>  
    :::image-end:::  
    
<span data-ttu-id="8e953-433">看起来，最后一个更改导致性能巨大的跳跃。</span><span class="sxs-lookup"><span data-stu-id="8e953-433">Looks like that last change caused a massive jump in performance!</span></span>  

> [!NOTE]
> <span data-ttu-id="8e953-434">本部分提供了 "性能" 面板的简要介绍。</span><span class="sxs-lookup"><span data-stu-id="8e953-434">This section provided a rather brief introduction to the Performance panel.</span></span>  <span data-ttu-id="8e953-435">请参阅 [性能分析参考][DevtoolsEvaluatePerformanceReference] ，了解有关如何分析页面性能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8e953-435">See [Performance Analysis Reference][DevtoolsEvaluatePerformanceReference] to learn more about how to analyze page performance.</span></span>  

<!--todo: add section when available -->  

#### <span data-ttu-id="8e953-436">在现实世界中执行较少的主线程工作</span><span class="sxs-lookup"><span data-stu-id="8e953-436">Doing less main thread work in the real world</span></span>   

<span data-ttu-id="8e953-437">通常，" **性能** " 面板是了解你的网站在加载时所执行的活动的最常用方式，并查找删除不必要的活动的方法。</span><span class="sxs-lookup"><span data-stu-id="8e953-437">In general, the **Performance** panel is the most common way to understand what activity your site does as it loads, and find ways to remove unnecessary activity.</span></span>  

<span data-ttu-id="8e953-438">如果你更喜欢更喜欢的方法 `console.log()` ， [用户计时 API][MDNUserTimingApi] 使你可以任意标记你的应用生命周期的特定阶段，以便跟踪这些阶段所需的时间。</span><span class="sxs-lookup"><span data-stu-id="8e953-438">If you prefer an approach that feels more like `console.log()`, the [User Timing API][MDNUserTimingApi] enables you to arbitrarily mark up certain phases of your app lifecycle, in order to track how long each of those phases takes.</span></span>  

## <span data-ttu-id="8e953-439">摘要</span><span class="sxs-lookup"><span data-stu-id="8e953-439">Summary</span></span>   

*   <span data-ttu-id="8e953-440">无论何时设置以优化网站的负载性能，都将始终从审核开始。</span><span class="sxs-lookup"><span data-stu-id="8e953-440">Whenever you set out to optimize the load performance of a site, always start with an audit.</span></span>  <span data-ttu-id="8e953-441">审核建立了一个基准，并提供了有关如何改进的提示。</span><span class="sxs-lookup"><span data-stu-id="8e953-441">The audit establishes a baseline, and gives you tips on how to improve.</span></span>  
*   <span data-ttu-id="8e953-442">一次更改一个更改，并在每次更改后审核页面，以了解该隔离更改对性能有何影响。</span><span class="sxs-lookup"><span data-stu-id="8e953-442">Make one change at a time, and audit the page after each change in order to see how that isolated change affects performance.</span></span>  

<!--
## Next steps   

*   Run audits on your own site!  If you need help interpreting your report, or finding ways to improve your load performance, check out [Feedback](#feedback) for ways to get help from the DevTools community.  Stack Overflow, the mailing list, or Twitter are probably best for these types of questions.  
*   Please leave [feedback](#feedback) on this tutorial.  I really do use the data to make better tutorials for you.  
-->  

<!--  
  


-->  

<!-- image links -->  

[ImageAddPatternIcon]: ../media/add-pattern-icon.msft.png  
[ImageCaptureIcon]: ../media/capture-icon.msft.png  
[ImageLargeResourceRowsButtonIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageMorePanelsIcon]: ../media/more-panels-icon.msft.png  
[ImagePerformIcon]: ../media/perform-icon.msft.png  
[ImageRefreshIcon]: ../media/reload-icon.msft.png  
[ImageRemoveIcon]: ../media/remove-icon.msft.png  
<!-- links -->  

[DevtoolsEvaluatePerformanceReference]: ../evaluate-performance/reference.md "性能分析参考 |Microsoft 文档"  

[CourseraIntroductionWebDevelopmentClass]: https://www.coursera.org/learn/web-development#syllabus "Web 开发类简介 |Coursera"  

[EssentialImageOptimization]: https://images.guide "基本图像优化"  

[MDNContentEncodingDirectives]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Encoding#Directives "指令-内容编码 |MDN"  
[MDNUserTimingApi]: https://developer.mozilla.org/docs/Web/API/User_Timing_API "用户计时 API |MDN"  

[WebpackTreeShaking]: https://webpack.js.org/guides/tree-shaking "树形摇动 |webpack"  

> [!NOTE]
> <span data-ttu-id="8e953-449">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="8e953-449">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="8e953-450">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/speed/get-started)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="8e953-450">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/speed/get-started) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="8e953-452">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="8e953-452">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
