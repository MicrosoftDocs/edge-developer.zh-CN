---
title: 通过 Microsoft Edge DevTools 优化网站速度
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 7efc76fbcb3d1ed6cbd0760f789c8c952030d70c
ms.sourcegitcommit: 4c24edbd1c591914cb4109511534851570a614cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611887"
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





# <span data-ttu-id="a2243-103">通过 Microsoft Edge DevTools 优化网站速度</span><span class="sxs-lookup"><span data-stu-id="a2243-103">Optimize Website Speed With Microsoft Edge DevTools</span></span>   



## <span data-ttu-id="a2243-104">教程目标</span><span class="sxs-lookup"><span data-stu-id="a2243-104">Goal of tutorial</span></span>  

<span data-ttu-id="a2243-105">本教程指导你如何使用 Microsoft Edge DevTools 来查找更快地加载网站的方法。</span><span class="sxs-lookup"><span data-stu-id="a2243-105">This tutorial teaches you how to use Microsoft Edge DevTools to find ways to make your websites load faster.</span></span>  

## <span data-ttu-id="a2243-106">必备条件</span><span class="sxs-lookup"><span data-stu-id="a2243-106">Prerequisites</span></span>  

*   <span data-ttu-id="a2243-107">你应该具有基本的 web 开发体验，类似于在此[Web 开发类简介][CourseraIntroductionWebDevelopmentClass]中讲授的内容。</span><span class="sxs-lookup"><span data-stu-id="a2243-107">You should have basic web development experience, similar to what is taught in this [Introduction to Web Development class][CourseraIntroductionWebDevelopmentClass].</span></span>  
*   <span data-ttu-id="a2243-108">无需了解有关加载性能的任何信息。</span><span class="sxs-lookup"><span data-stu-id="a2243-108">You do not need to know anything about load performance.</span></span>  <span data-ttu-id="a2243-109">您可以在本教程中了解它！</span><span class="sxs-lookup"><span data-stu-id="a2243-109">You learn about it in this tutorial!</span></span>  

## <span data-ttu-id="a2243-110">简介</span><span class="sxs-lookup"><span data-stu-id="a2243-110">Introduction</span></span>   

<span data-ttu-id="a2243-111">这是 Tony。</span><span class="sxs-lookup"><span data-stu-id="a2243-111">This is Tony.</span></span>  <span data-ttu-id="a2243-112">Tony 在猫社会中非常著名。</span><span class="sxs-lookup"><span data-stu-id="a2243-112">Tony is very famous in cat society.</span></span>  <span data-ttu-id="a2243-113">他已构建了一个网站，使其风扇能够了解他最喜爱的食物。</span><span class="sxs-lookup"><span data-stu-id="a2243-113">He has built a website so that his fans are able to learn about his favorite foods.</span></span>  <span data-ttu-id="a2243-114">他的风扇喜欢该站点，但 Tony 会不断听到该站点加载缓慢的投诉。</span><span class="sxs-lookup"><span data-stu-id="a2243-114">His fans love the site, but Tony keeps hearing complaints that the site loads slowly.</span></span>  <span data-ttu-id="a2243-115">Tony 已要求您帮助他提高网站的速度。</span><span class="sxs-lookup"><span data-stu-id="a2243-115">Tony has asked you to help him speed the site up.</span></span>  

> ##### <span data-ttu-id="a2243-116">图 1</span><span class="sxs-lookup"><span data-stu-id="a2243-116">Figure 1</span></span>  
> <span data-ttu-id="a2243-117">Tony 猫</span><span class="sxs-lookup"><span data-stu-id="a2243-117">Tony the cat</span></span>  
> ![Tony 猫][ImageTony]  

## <span data-ttu-id="a2243-119">步骤1：审核网站</span><span class="sxs-lookup"><span data-stu-id="a2243-119">Step 1: Audit the site</span></span>   

<span data-ttu-id="a2243-120">无论何时设置以提高网站的负载性能，**都应始终从审核开始**。</span><span class="sxs-lookup"><span data-stu-id="a2243-120">Whenever you set out to improve the load performance of a site, **always start with an audit**.</span></span>  
<span data-ttu-id="a2243-121">审核具有2个重要功能：</span><span class="sxs-lookup"><span data-stu-id="a2243-121">The audit has 2 important functions:</span></span>  

*   <span data-ttu-id="a2243-122">它将为您创建一个**基线**来衡量后续更改。</span><span class="sxs-lookup"><span data-stu-id="a2243-122">It creates a **baseline** for you to measure subsequent changes against.</span></span>  
*   <span data-ttu-id="a2243-123">它为你提供了可操作的有关哪些更改最有影响的**提示**。</span><span class="sxs-lookup"><span data-stu-id="a2243-123">It gives you **actionable tips** on what changes have the most impact.</span></span>  

### <span data-ttu-id="a2243-124">设置</span><span class="sxs-lookup"><span data-stu-id="a2243-124">Set up</span></span>   

<span data-ttu-id="a2243-125">首先，你必须设置网站，以便稍后能够对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="a2243-125">First, you must set up the site so that you are able to make changes to it later.</span></span>  

1.  <span data-ttu-id="a2243-126">[打开网站的源代码](https://glitch.com/edit/#!/tony)。</span><span class="sxs-lookup"><span data-stu-id="a2243-126">[Open the source code for the site](https://glitch.com/edit/#!/tony).</span></span>  <span data-ttu-id="a2243-127">此选项卡称为**编辑器选项卡**。</span><span class="sxs-lookup"><span data-stu-id="a2243-127">This tab is referred to as the **editor tab**.</span></span>  
    
    > ##### <span data-ttu-id="a2243-128">图 2</span><span class="sxs-lookup"><span data-stu-id="a2243-128">Figure 2</span></span>  
    > <span data-ttu-id="a2243-129">"编辑器" 选项卡</span><span class="sxs-lookup"><span data-stu-id="a2243-129">The editor tab</span></span>  
    > !["编辑器" 选项卡][ImageEditor]  

1.  <span data-ttu-id="a2243-131">选择 " **tony**"。</span><span class="sxs-lookup"><span data-stu-id="a2243-131">Select **tony**.</span></span>  <span data-ttu-id="a2243-132">将显示一个菜单。</span><span class="sxs-lookup"><span data-stu-id="a2243-132">A menu appears.</span></span>  
    
    > ##### <span data-ttu-id="a2243-133">图 3</span><span class="sxs-lookup"><span data-stu-id="a2243-133">Figure 3</span></span>  
    > <span data-ttu-id="a2243-134">单击 " **tony** " 后出现的菜单</span><span class="sxs-lookup"><span data-stu-id="a2243-134">The menu that appears after clicking **tony**</span></span>  
    > ![单击 "tony" 后出现的菜单][ImageMenu]  
    
1.  <span data-ttu-id="a2243-136">选择 " **Remix 项目**"。</span><span class="sxs-lookup"><span data-stu-id="a2243-136">Select **Remix Project**.</span></span>  <span data-ttu-id="a2243-137">项目的名称从**tony**更改为某个随机生成的名称。</span><span class="sxs-lookup"><span data-stu-id="a2243-137">The name of the project changes from **tony** to some randomly-generated name.</span></span>  <span data-ttu-id="a2243-138">现在，你拥有自己的代码的可编辑副本。</span><span class="sxs-lookup"><span data-stu-id="a2243-138">You now have your own editable copy of the code.</span></span>  <span data-ttu-id="a2243-139">稍后，你可以对此代码进行更改。</span><span class="sxs-lookup"><span data-stu-id="a2243-139">Later on, you may make changes to this code.</span></span>  
1.  <span data-ttu-id="a2243-140">选择 "**显示**"，然后**在新窗口中**选择。</span><span class="sxs-lookup"><span data-stu-id="a2243-140">Select **Show** and select **In a New Window**.</span></span>  <span data-ttu-id="a2243-141">演示将在新选项卡中打开。 此选项卡称为 "**演示" 选项卡**。 加载网站可能需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="a2243-141">The demo opens in a new tab.  This tab is be referred to as the **demo tab**.  It may take a while for the site to load.</span></span>  
    
    > ##### <span data-ttu-id="a2243-142">图 4</span><span class="sxs-lookup"><span data-stu-id="a2243-142">Figure 4</span></span>  
    > <span data-ttu-id="a2243-143">"演示" 选项卡</span><span class="sxs-lookup"><span data-stu-id="a2243-143">The demo tab</span></span>  
    > !["演示" 选项卡][ImageDemo]  

1.  <span data-ttu-id="a2243-145">按 `Control` + `Shift` + `J` \ （Windows \）或 `Command` + `Option` + `J` \ （macOS \）。</span><span class="sxs-lookup"><span data-stu-id="a2243-145">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="a2243-146">Microsoft Edge DevTools 将与演示一起打开。</span><span class="sxs-lookup"><span data-stu-id="a2243-146">Microsoft Edge DevTools opens up alongside the demo.</span></span>  
    
    > ##### <span data-ttu-id="a2243-147">图 5</span><span class="sxs-lookup"><span data-stu-id="a2243-147">Figure 5</span></span>  
    > <span data-ttu-id="a2243-148">DevTools 和演示</span><span class="sxs-lookup"><span data-stu-id="a2243-148">DevTools and the demo</span></span>  
    > ![DevTools 和演示][ImageDevtools]  

<span data-ttu-id="a2243-150">对于本教程中的其余屏幕截图，DevTools 显示在一个单独的窗口中。</span><span class="sxs-lookup"><span data-stu-id="a2243-150">For the rest of the screenshots in this tutorial, DevTools is shown in a separate window.</span></span>  <span data-ttu-id="a2243-151">按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开命令菜单，键入，然后 `Undock` 选择 "**在单独窗口中脱开**"。</span><span class="sxs-lookup"><span data-stu-id="a2243-151">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, typing `Undock`, and then selecting **Undock into separate window**.</span></span>  

> ##### <span data-ttu-id="a2243-152">图 6</span><span class="sxs-lookup"><span data-stu-id="a2243-152">Figure 6</span></span>  
> <span data-ttu-id="a2243-153">取消停靠 DevTools</span><span class="sxs-lookup"><span data-stu-id="a2243-153">Undocked DevTools</span></span>  
> ![取消停靠 DevTools][ImageUndocked]  

### <span data-ttu-id="a2243-155">建立基线</span><span class="sxs-lookup"><span data-stu-id="a2243-155">Establish a baseline</span></span>   

<span data-ttu-id="a2243-156">比较基准是在改进性能方面之前如何执行网站的记录。</span><span class="sxs-lookup"><span data-stu-id="a2243-156">The baseline is a record of how the site performed before you made any performance improvements.</span></span>  

1.  <span data-ttu-id="a2243-157">选择 "**审核**" 选项卡。 它可能隐藏在 "**更多面板** ![ 更多" 面板 ][ImageMorePanelsIcon] 按钮后面。</span><span class="sxs-lookup"><span data-stu-id="a2243-157">Select the **Audits** tab.  It may be hidden behind the **More Panels** ![More Panels][ImageMorePanelsIcon] button.</span></span>  <span data-ttu-id="a2243-158">此面板上有一个 Lighthouse，因为 Lighthouse "审核" 面板的项目称为 " **Lighthouse**"。</span><span class="sxs-lookup"><span data-stu-id="a2243-158">There is a Lighthouse on this panel because the project that powers the Audits panel is named **Lighthouse**.</span></span>  
    
    [!INCLUDE [audits-panel-note](../includes/audits-panel-note.md)]  
    
    > ##### <span data-ttu-id="a2243-159">图 7</span><span class="sxs-lookup"><span data-stu-id="a2243-159">Figure 7</span></span>  
    > <span data-ttu-id="a2243-160">"审核" 面板</span><span class="sxs-lookup"><span data-stu-id="a2243-160">The Audits panel</span></span>  
    > !["审核" 面板][ImageAudits]  
    
    <!--todo: add link to Lighthouse when section is available  -->  
    <!-- /web/tools/lighthouse  -->  
    
1.  <span data-ttu-id="a2243-162">将您的审核配置设置与[图 7](#figure-7)中的设置相匹配。</span><span class="sxs-lookup"><span data-stu-id="a2243-162">Match your audit configuration settings to those in [Figure 7](#figure-7).</span></span>  <span data-ttu-id="a2243-163">下面是不同选项的说明：</span><span class="sxs-lookup"><span data-stu-id="a2243-163">Here is an explanation of the different options:</span></span>  

    *   <span data-ttu-id="a2243-164">**设备**。</span><span class="sxs-lookup"><span data-stu-id="a2243-164">**Device**.</span></span>  <span data-ttu-id="a2243-165">设置为 "**移动**" 将更改用户代理字符串并模拟移动视区。</span><span class="sxs-lookup"><span data-stu-id="a2243-165">Setting to **Mobile** changes the user agent string and simulates a mobile viewport.</span></span>  <span data-ttu-id="a2243-166">设置到**桌面**非常简单，只需禁用**移动**更改。</span><span class="sxs-lookup"><span data-stu-id="a2243-166">Setting to **Desktop** pretty much just disables the **Mobile** changes.</span></span>  
    *   <span data-ttu-id="a2243-167">**审核**。</span><span class="sxs-lookup"><span data-stu-id="a2243-167">**Audits**.</span></span>  <span data-ttu-id="a2243-168">禁用类别可防止 "审核" 面板运行这些审核，并从报表中排除这些审核。</span><span class="sxs-lookup"><span data-stu-id="a2243-168">Disabling a category prevents the Audits panel from running those audits, and excludes those audits from your report.</span></span>  <span data-ttu-id="a2243-169">如果想要查看提供的建议类型，请保留启用其他类别。</span><span class="sxs-lookup"><span data-stu-id="a2243-169">Leave the other categories enabled, if you want to see the types of recommendations that are provide.</span></span>  <span data-ttu-id="a2243-170">禁用类别会略微提高审核过程的速度。</span><span class="sxs-lookup"><span data-stu-id="a2243-170">Disabling categories slightly speeds up the auditing process.</span></span>  
    *   <span data-ttu-id="a2243-171">**限制**。</span><span class="sxs-lookup"><span data-stu-id="a2243-171">**Throttling**.</span></span>  <span data-ttu-id="a2243-172">设置为**模拟慢4G，4X CPU 减速**模拟在移动设备上浏览的典型条件。</span><span class="sxs-lookup"><span data-stu-id="a2243-172">Setting to **Simulated Slow 4G, 4x CPU Slowdown** simulates the typical conditions of browsing on a mobile device.</span></span>  <span data-ttu-id="a2243-173">它被命名为 "模拟"，因为审核面板在审核过程中实际上并不会受到限制。</span><span class="sxs-lookup"><span data-stu-id="a2243-173">It is named "simulated" because the Audits panel does not actually throttle during the auditing process.</span></span>  <span data-ttu-id="a2243-174">相反，它只是 extrapolates 在移动条件下加载页面所需的时间。</span><span class="sxs-lookup"><span data-stu-id="a2243-174">Instead, it just extrapolates how long the page would take to load under mobile conditions.</span></span>  <span data-ttu-id="a2243-175">另一方面，**应用的 ...** 设置实际上会限制 CPU 和网络，同时还会权衡较长的审核过程。</span><span class="sxs-lookup"><span data-stu-id="a2243-175">The **Applied...** setting, on the other hand, actually throttles your CPU and network, with the tradeoff of a longer auditing process.</span></span>  
    *   <span data-ttu-id="a2243-176">**清除存储空间**。</span><span class="sxs-lookup"><span data-stu-id="a2243-176">**Clear Storage**.</span></span>  <span data-ttu-id="a2243-177">启用此复选框将在每次审核之前清除与页面关联的所有存储。</span><span class="sxs-lookup"><span data-stu-id="a2243-177">Enabling this checkbox clears all storage associated with the page before every audit.</span></span>  <span data-ttu-id="a2243-178">如果你想要审核首次访问你的网站时的访问者体验，请保留此设置。</span><span class="sxs-lookup"><span data-stu-id="a2243-178">Leave this setting on if you want to audit how first-time visitors experience your site.</span></span>  <span data-ttu-id="a2243-179">如果需要重复访问体验，请禁用此设置。</span><span class="sxs-lookup"><span data-stu-id="a2243-179">Disable this setting when you want the repeat-visit experience.</span></span>  

1.  <span data-ttu-id="a2243-180">选择 "**运行审核**"。</span><span class="sxs-lookup"><span data-stu-id="a2243-180">Select **Run Audits**.</span></span>  <span data-ttu-id="a2243-181">10至30秒后，"审核" 面板将显示有关网站性能的报告。</span><span class="sxs-lookup"><span data-stu-id="a2243-181">After 10 to 30 seconds, the Audits panel shows you a report of the performance of the site.</span></span>  
    
    > ##### <span data-ttu-id="a2243-182">图 8</span><span class="sxs-lookup"><span data-stu-id="a2243-182">Figure 8</span></span>  
    > <span data-ttu-id="a2243-183">网站性能的 "审核" 面板的报表</span><span class="sxs-lookup"><span data-stu-id="a2243-183">The report for the Audits panel of the performance of the site</span></span>  
    > ![网站性能的 "审核" 面板的报表][ImageReport]  

#### <span data-ttu-id="a2243-185">处理报告错误</span><span class="sxs-lookup"><span data-stu-id="a2243-185">Handling report errors</span></span>   

<span data-ttu-id="a2243-186">如果你在 "审核" 面板报告中遇到错误，请尝试从**InPrivate**窗口运行 "演示" 选项卡，并且不会打开任何其他选项卡。</span><span class="sxs-lookup"><span data-stu-id="a2243-186">If you ever get an error in your Audits panel report, try running the demo tab from an **InPrivate** window with no other tabs open.</span></span>  <span data-ttu-id="a2243-187">这可确保你从干净状态运行 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="a2243-187">This ensures that you are running Microsoft Edge from a clean state.</span></span>  <span data-ttu-id="a2243-188">Microsoft Edge 扩展通常会干扰审核过程。</span><span class="sxs-lookup"><span data-stu-id="a2243-188">Microsoft Edge Extensions in particular often interfere with the auditing process.</span></span>  

<!--todo: add screen capture for error in audit -->  
<!--
> ##### old Figure 9  
> A report that errored  
> ![A report that errored][ImageError]  
-->  

### <span data-ttu-id="a2243-189">了解你的报表</span><span class="sxs-lookup"><span data-stu-id="a2243-189">Understand your report</span></span>   

<span data-ttu-id="a2243-190">报表顶部的数字是网站的整体绩效分数。</span><span class="sxs-lookup"><span data-stu-id="a2243-190">The number at the top of your report is the overall performance score for the site.</span></span>  <span data-ttu-id="a2243-191">稍后，在对代码进行更改时，您应看到此数字高度。</span><span class="sxs-lookup"><span data-stu-id="a2243-191">Later, as you make changes to the code, you should see this number rise.</span></span>  <span data-ttu-id="a2243-192">分数越高表示性能越高。</span><span class="sxs-lookup"><span data-stu-id="a2243-192">A higher score means better performance.</span></span>  

> ##### <span data-ttu-id="a2243-193">图 9</span><span class="sxs-lookup"><span data-stu-id="a2243-193">Figure 9</span></span>  
> <span data-ttu-id="a2243-194">整体性能分数</span><span class="sxs-lookup"><span data-stu-id="a2243-194">The overall performance score</span></span>  
> <span data-ttu-id="a2243-195">![总体性能分数][ImageOverall]</span><span class="sxs-lookup"><span data-stu-id="a2243-195">![The overall performance score][ImageOverall]</span></span>  

<span data-ttu-id="a2243-196">"**指标**" 部分提供了有关站点性能的量化指标。</span><span class="sxs-lookup"><span data-stu-id="a2243-196">The **Metrics** section provides quantitative measurements of the performance of the site.</span></span>  <span data-ttu-id="a2243-197">每个指标都可以深入了解性能的不同方面。</span><span class="sxs-lookup"><span data-stu-id="a2243-197">Each metric provides insight into a different aspect of the performance.</span></span>  <span data-ttu-id="a2243-198">例如，**第一个 Contentful 画图**会告诉您，当内容首次绘制到屏幕时，这是用户对页面加载的感觉中的重要里程碑，而是**交互式**标记该页面似乎足以处理用户交互的时刻。</span><span class="sxs-lookup"><span data-stu-id="a2243-198">For example, **First Contentful Paint** tells you when content is first painted to the screen, which is an important milestone in the user's perception of the page load, whereas **Time To Interactive** marks the point at which the page appears ready enough to handle user interactions.</span></span>  

> ##### <span data-ttu-id="a2243-199">图 10</span><span class="sxs-lookup"><span data-stu-id="a2243-199">Figure 10</span></span>  
> <span data-ttu-id="a2243-200">"指标" 部分</span><span class="sxs-lookup"><span data-stu-id="a2243-200">The Metrics section</span></span>  
> <span data-ttu-id="a2243-201">![指标部分][ImageMetrics]</span><span class="sxs-lookup"><span data-stu-id="a2243-201">![The Metrics section][ImageMetrics]</span></span>  

<span data-ttu-id="a2243-202">选择[图 11](#figure-11)中突出显示的 "切换" 按钮以查看每个指标的说明，然后单击 "**了解详细**信息" 以阅读有关每个指标的文档。</span><span class="sxs-lookup"><span data-stu-id="a2243-202">Select the highlighted toggle button in [Figure 11](#figure-11) to see a description for each metric, and click **Learn More** to read documentation about it.</span></span>  

> ##### <span data-ttu-id="a2243-203">图 11</span><span class="sxs-lookup"><span data-stu-id="a2243-203">Figure 11</span></span>  
> <span data-ttu-id="a2243-204">选择突出显示的切换按钮以展开**指标**项目</span><span class="sxs-lookup"><span data-stu-id="a2243-204">Select the highlighted toggle button to expand the **Metrics** items</span></span>  
> <span data-ttu-id="a2243-205">![选择突出显示的切换按钮以展开指标项目][ImageFirstMeaningfulPaint]</span><span class="sxs-lookup"><span data-stu-id="a2243-205">![Select the highlighted toggle button to expand the Metrics items][ImageFirstMeaningfulPaint]</span></span>  

<span data-ttu-id="a2243-206">"指标" 下面是屏幕截图的集合，可显示页面的加载方式。</span><span class="sxs-lookup"><span data-stu-id="a2243-206">Below Metrics is a collection of screenshots that show you how the page looked as it loaded.</span></span>  

> ##### <span data-ttu-id="a2243-207">图 12</span><span class="sxs-lookup"><span data-stu-id="a2243-207">Figure 12</span></span>  
> <span data-ttu-id="a2243-208">在加载时如何查看页面的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="a2243-208">Screenshots of how the page looked while loading</span></span>  
> <span data-ttu-id="a2243-209">![加载时如何查看页面的屏幕截图][ImageScreenshots]</span><span class="sxs-lookup"><span data-stu-id="a2243-209">![Screenshots of how the page looked while loading][ImageScreenshots]</span></span>  

<span data-ttu-id="a2243-210">"**商机**" 部分提供了有关如何提高此特定页面的加载性能的特定提示。</span><span class="sxs-lookup"><span data-stu-id="a2243-210">The **Opportunities** section provides specific tips on how to improve the load performance of this specific page.</span></span>  

> ##### <span data-ttu-id="a2243-211">图 13</span><span class="sxs-lookup"><span data-stu-id="a2243-211">Figure 13</span></span>  
> <span data-ttu-id="a2243-212">"商机" 部分</span><span class="sxs-lookup"><span data-stu-id="a2243-212">The Opportunities section</span></span>  
> <span data-ttu-id="a2243-213">![商机部分][ImageOpportunities]</span><span class="sxs-lookup"><span data-stu-id="a2243-213">![The Opportunities section][ImageOpportunities]</span></span>  

<span data-ttu-id="a2243-214">选择一个商机以了解更多相关信息。</span><span class="sxs-lookup"><span data-stu-id="a2243-214">Select an opportunity to learn more about it.</span></span>  

> ##### <span data-ttu-id="a2243-215">图 14</span><span class="sxs-lookup"><span data-stu-id="a2243-215">Figure 14</span></span>  
> <span data-ttu-id="a2243-216">**消除呈现阻止资源的**机会</span><span class="sxs-lookup"><span data-stu-id="a2243-216">**Eliminate render-blocking resources** opportunity</span></span>  
> <span data-ttu-id="a2243-217">![消除呈现阻止资源的机会][ImageCompression]</span><span class="sxs-lookup"><span data-stu-id="a2243-217">![Eliminate render-blocking resources opportunity][ImageCompression]</span></span>  

<span data-ttu-id="a2243-218">选择 "**了解详细**信息"，查看有关商机为什么很重要的文档，以及有关如何解决该问题的特定建议。</span><span class="sxs-lookup"><span data-stu-id="a2243-218">Select **Learn More** to see documentation about why an opportunity is important, and specific recommendations on how to fix it.</span></span>  

> ##### <span data-ttu-id="a2243-219">图 15</span><span class="sxs-lookup"><span data-stu-id="a2243-219">Figure 15</span></span>  
> <span data-ttu-id="a2243-220">用于**消除呈现阻止资源**商机的文档</span><span class="sxs-lookup"><span data-stu-id="a2243-220">Documentation for the **Eliminate render-blocking resources** opportunity</span></span>  
> <span data-ttu-id="a2243-221">![关于消除呈现阻止资源商机的文档][ImageReference]</span><span class="sxs-lookup"><span data-stu-id="a2243-221">![Documentation for the Eliminate render-blocking resources opportunity][ImageReference]</span></span>  

<span data-ttu-id="a2243-222">**诊断**部分提供有关影响页面加载时间的因素的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a2243-222">The **Diagnostics** section provides more information about factors that contribute to the load time of the page.</span></span>  

> ##### <span data-ttu-id="a2243-223">图 16</span><span class="sxs-lookup"><span data-stu-id="a2243-223">Figure 16</span></span>  
> <span data-ttu-id="a2243-224">诊断部分</span><span class="sxs-lookup"><span data-stu-id="a2243-224">The Diagnostics section</span></span>  
> <span data-ttu-id="a2243-225">![诊断程序部分][ImageDiagnostics]</span><span class="sxs-lookup"><span data-stu-id="a2243-225">![The Diagnostics section][ImageDiagnostics]</span></span>  

<span data-ttu-id="a2243-226">"已**通过审核**" 部分显示网站正确执行的操作。</span><span class="sxs-lookup"><span data-stu-id="a2243-226">The **Passed Audits** section shows you what the site is doing correctly.</span></span>  <span data-ttu-id="a2243-227">选择以展开该部分。</span><span class="sxs-lookup"><span data-stu-id="a2243-227">Select to expand the section.</span></span>  

> ##### <span data-ttu-id="a2243-228">图 17</span><span class="sxs-lookup"><span data-stu-id="a2243-228">Figure 17</span></span>  
> <span data-ttu-id="a2243-229">"已传递审核" 部分</span><span class="sxs-lookup"><span data-stu-id="a2243-229">The Passed Audits section</span></span>  
> <span data-ttu-id="a2243-230">![已通过的审核部分][ImagePassed]</span><span class="sxs-lookup"><span data-stu-id="a2243-230">![The Passed Audits section][ImagePassed]</span></span>  

## <span data-ttu-id="a2243-231">步骤2：实验</span><span class="sxs-lookup"><span data-stu-id="a2243-231">Step 2: Experiment</span></span>   

<span data-ttu-id="a2243-232">审核报告的 "机遇" 部分提供了有关如何提高页面性能的提示。</span><span class="sxs-lookup"><span data-stu-id="a2243-232">The Opportunities section of your audit report gives you tips on how to improve the performance of the page.</span></span>  <span data-ttu-id="a2243-233">在此部分中，你将实现对基本代码的建议更改，在每次更改后审核网站，以测量它对网站速度的影响。</span><span class="sxs-lookup"><span data-stu-id="a2243-233">In this section, you implement the recommended changes to the codebase, auditing the site after each change to measure how it affects site speed.</span></span>  

### <span data-ttu-id="a2243-234">启用文本压缩</span><span class="sxs-lookup"><span data-stu-id="a2243-234">Enable text compression</span></span>   

<span data-ttu-id="a2243-235">你的报告表明，避免巨大的网络负载是改善页面性能的首要机会之一。</span><span class="sxs-lookup"><span data-stu-id="a2243-235">Your report says that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="a2243-236">启用文本压缩是提高页面性能的机会。</span><span class="sxs-lookup"><span data-stu-id="a2243-236">Enabling text compression is an opportunity to improve the performance of the page.</span></span>  

<span data-ttu-id="a2243-237">文本压缩是指在通过网络发送文本文件之前减小或压缩该文件的大小。</span><span class="sxs-lookup"><span data-stu-id="a2243-237">Text compression is when you reduce, or compress, the size of a text file before sending it over the network.</span></span>  <span data-ttu-id="a2243-238">类似于通过电子邮件对文件夹进行电子邮件压缩以减小大小。</span><span class="sxs-lookup"><span data-stu-id="a2243-238">Kind of like how you might zip a folder before emailing it to reduce the size.</span></span>  

<span data-ttu-id="a2243-239">启用压缩之前，可通过以下几种方法来手动检查文本资源是否已压缩。</span><span class="sxs-lookup"><span data-stu-id="a2243-239">Before you enable compression, here are a couple of ways to manually check whether text resources are compressed.</span></span>  

1.  <span data-ttu-id="a2243-240">选择 "**网络**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a2243-240">Select the **Network** tab.</span></span>  
    
    > ##### <span data-ttu-id="a2243-241">图18</span><span class="sxs-lookup"><span data-stu-id="a2243-241">Figure 18</span></span>  
    > <span data-ttu-id="a2243-242">网络面板</span><span class="sxs-lookup"><span data-stu-id="a2243-242">The Network panel</span></span>  
    > <span data-ttu-id="a2243-243">![网络面板][ImageNetwork]</span><span class="sxs-lookup"><span data-stu-id="a2243-243">![The Network panel][ImageNetwork]</span></span>  
    
1.  <span data-ttu-id="a2243-244">选择 "**网络设置**" 图标。</span><span class="sxs-lookup"><span data-stu-id="a2243-244">Select the **Network setting** icon.</span></span>  
1.  <span data-ttu-id="a2243-245">选中 "**使用大请求行**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a2243-245">Select the **Use Large Request Rows** checkbox.</span></span>  <span data-ttu-id="a2243-246">网络请求表中的行的高度增加。</span><span class="sxs-lookup"><span data-stu-id="a2243-246">The height of the rows in the table of network requests increases.</span></span>  
    
    > ##### <span data-ttu-id="a2243-247">图19</span><span class="sxs-lookup"><span data-stu-id="a2243-247">Figure 19</span></span>  
    > <span data-ttu-id="a2243-248">网络请求表中的较大行数</span><span class="sxs-lookup"><span data-stu-id="a2243-248">Large rows in the network requests table</span></span>  
    > <span data-ttu-id="a2243-249">![网络请求表中的较大行][ImageLargeRows]</span><span class="sxs-lookup"><span data-stu-id="a2243-249">![Large rows in the network requests table][ImageLargeRows]</span></span>  
    
1.  <span data-ttu-id="a2243-250">如果在网络请求表中看不到 "**大小**" 列，请单击表标题，然后选择 "**大小**"。</span><span class="sxs-lookup"><span data-stu-id="a2243-250">If you do not see the **Size** column in the table of network requests, click the table header and then select **Size**.</span></span>  

<span data-ttu-id="a2243-251">每个 "**大小**" 单元格显示两个值。</span><span class="sxs-lookup"><span data-stu-id="a2243-251">Each **Size** cell shows two values.</span></span>  <span data-ttu-id="a2243-252">最大值是已下载资源的大小。</span><span class="sxs-lookup"><span data-stu-id="a2243-252">The top value is the size of the downloaded resource.</span></span>  
<span data-ttu-id="a2243-253">下限值是未压缩资源的大小。</span><span class="sxs-lookup"><span data-stu-id="a2243-253">The bottom value is the size of the uncompressed resource.</span></span>  <span data-ttu-id="a2243-254">如果两个值相同，则该资源在通过网络发送时不会被压缩。</span><span class="sxs-lookup"><span data-stu-id="a2243-254">If the two values are the same, then the resource is not being compressed when it is sent over the network.</span></span>  <span data-ttu-id="a2243-255">例如，在[图 19](#figure-19)中，的上限和下限值 `bundle.js` 为 `1.2 MB` 和 `1.2 MB` 。</span><span class="sxs-lookup"><span data-stu-id="a2243-255">For example, in [Figure 19](#figure-19) the top and bottom values for `bundle.js` are `1.2 MB` and `1.2 MB`.</span></span>  

<span data-ttu-id="a2243-256">通过检查资源的 HTTP 标头来检查压缩：</span><span class="sxs-lookup"><span data-stu-id="a2243-256">Check for compression by inspecting the HTTP headers of a resource:</span></span>  

1.  <span data-ttu-id="a2243-257">选择 "**包 .js**"。</span><span class="sxs-lookup"><span data-stu-id="a2243-257">Select **bundle.js**.</span></span>  
1.  <span data-ttu-id="a2243-258">选择 "**页眉**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a2243-258">Select the **Headers** tab.</span></span>  
    
    > ##### <span data-ttu-id="a2243-259">图20</span><span class="sxs-lookup"><span data-stu-id="a2243-259">Figure 20</span></span>  
    > <span data-ttu-id="a2243-260">"页眉" 选项卡</span><span class="sxs-lookup"><span data-stu-id="a2243-260">The Headers tab</span></span>  
    > <span data-ttu-id="a2243-261">![标题选项卡][ImageHeaders]</span><span class="sxs-lookup"><span data-stu-id="a2243-261">![The Headers tab][ImageHeaders]</span></span>  
    
1.  <span data-ttu-id="a2243-262">在 "**响应标题**" 部分 `content-encoding` 中搜索标题。</span><span class="sxs-lookup"><span data-stu-id="a2243-262">Search the **Response Headers** section for a `content-encoding` header.</span></span>  <span data-ttu-id="a2243-263">你应该看不到，这种情况未 `bundle.js` 压缩。</span><span class="sxs-lookup"><span data-stu-id="a2243-263">You should not see one, meaning that `bundle.js` was not compressed.</span></span>  <span data-ttu-id="a2243-264">当资源被压缩时，此页眉通常设置为 `gzip` 、 `deflate` 或 `br` 。</span><span class="sxs-lookup"><span data-stu-id="a2243-264">When a resource is compressed, this header is usually set to `gzip`, `deflate`, or `br`.</span></span>  <span data-ttu-id="a2243-265">有关这些值的说明，请参阅[指令][MDNContentEncodingDirectives]。</span><span class="sxs-lookup"><span data-stu-id="a2243-265">See [Directives][MDNContentEncodingDirectives] for an explanation of these values.</span></span>  

<span data-ttu-id="a2243-266">有足够的说明。</span><span class="sxs-lookup"><span data-stu-id="a2243-266">Enough with the explanations.</span></span>  <span data-ttu-id="a2243-267">进行更改的时间！</span><span class="sxs-lookup"><span data-stu-id="a2243-267">Time to make some changes!</span></span>  <span data-ttu-id="a2243-268">通过添加几行代码来启用文本压缩：</span><span class="sxs-lookup"><span data-stu-id="a2243-268">Enable text compression by adding a couple of lines of code:</span></span>  

1.  <span data-ttu-id="a2243-269">在 "编辑器" 选项卡中，单击 " **.js**"。</span><span class="sxs-lookup"><span data-stu-id="a2243-269">In the editor tab, click **server.js**.</span></span>  
    
    > ##### <span data-ttu-id="a2243-270">图21</span><span class="sxs-lookup"><span data-stu-id="a2243-270">Figure 21</span></span>  
    > <span data-ttu-id="a2243-271">编辑 server .js</span><span class="sxs-lookup"><span data-stu-id="a2243-271">Editing server.js</span></span>  
    > <span data-ttu-id="a2243-272">![正在编辑服务器][ImageServer]</span><span class="sxs-lookup"><span data-stu-id="a2243-272">![Editing server.js][ImageServer]</span></span>  
    
1.  <span data-ttu-id="a2243-273">将以下代码添加到**server .js**。</span><span class="sxs-lookup"><span data-stu-id="a2243-273">Add the following code to **server.js**.</span></span>  <span data-ttu-id="a2243-274">请确保放 `app.use(compression())` 在前面 `app.use(express.static('build'))` 。</span><span class="sxs-lookup"><span data-stu-id="a2243-274">Make sure to put `app.use(compression())` before `app.use(express.static('build'))`.</span></span>  

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
    > <span data-ttu-id="a2243-275">通常，你必须通过类似的方式安装 `compression` 程序包 `npm i -S compression` ，但已为你执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a2243-275">Usually, you have to install the `compression` package via something like `npm i -S compression`, but this has already been done for you.</span></span>  
    
1.  <span data-ttu-id="a2243-276">请等待部署新版本的网站。</span><span class="sxs-lookup"><span data-stu-id="a2243-276">Wait for Glitch to deploy the new build of the site.</span></span>  <span data-ttu-id="a2243-277">"**工具**" 旁边的 "别致" 动画意味着该网站将重新构建并重新部署。</span><span class="sxs-lookup"><span data-stu-id="a2243-277">The fancy animation next to **Tools** means that the site is getting rebuilt and redeployed.</span></span>  <span data-ttu-id="a2243-278">当 "**工具**" 旁边的动画消失时，更改即已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="a2243-278">The change is ready when the animation next to **Tools** goes away.</span></span>  <span data-ttu-id="a2243-279">再次选择 "**显示**"，然后**在新窗口中**再次选择。</span><span class="sxs-lookup"><span data-stu-id="a2243-279">Select **Show** and select **In a New Window** again.</span></span>  
    
    <!--
    > ##### Old Figure 22  
    > The animation that indicates that the site is getting built  
    > ![The animation that indicates that the site is getting built][ImageBuilding]  
    -->  
    
<span data-ttu-id="a2243-280">使用之前学习的工作流手动检查压缩是否正常工作：</span><span class="sxs-lookup"><span data-stu-id="a2243-280">Use the workflows that you learned earlier to manually check that the compression is working:</span></span>  

1.  <span data-ttu-id="a2243-281">返回到 "演示" 选项卡，然后重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="a2243-281">Go back to the demo tab and reload the page.</span></span>  <span data-ttu-id="a2243-282">现在，"**大小**" 列应显示类似于文本资源的2个不同值 `bundle.js` 。</span><span class="sxs-lookup"><span data-stu-id="a2243-282">The **Size** column should now show 2 different values for text resources like `bundle.js`.</span></span>  <span data-ttu-id="a2243-283">[图 23](#figure-23)中的 "for" 的上限值 `256 KB` `bundle.js` 是通过网络发送的文件的大小，最小值 `1.2 MB` 是未压缩的文件大小。</span><span class="sxs-lookup"><span data-stu-id="a2243-283">In [Figure 23](#figure-23) the top value of `256 KB` for `bundle.js` is the size of the file that was sent over the network, and the bottom value of `1.2 MB` is the uncompressed file size.</span></span>  
    
    > ##### <span data-ttu-id="a2243-284">图22</span><span class="sxs-lookup"><span data-stu-id="a2243-284">Figure 22</span></span>  
    > <span data-ttu-id="a2243-285">"大小" 列现在为文本资源显示2个不同的值</span><span class="sxs-lookup"><span data-stu-id="a2243-285">The Size column now shows 2 different values for text resources</span></span>  
    > <span data-ttu-id="a2243-286">!["大小" 列现在为文本资源显示2个不同的值][ImageRequests]</span><span class="sxs-lookup"><span data-stu-id="a2243-286">![The Size column now shows 2 different values for text resources][ImageRequests]</span></span>  
    
1.  <span data-ttu-id="a2243-287">现在，的 "**响应标题**" 部分 `bundle.js` 应包括 `content-encoding: gzip` 标题。</span><span class="sxs-lookup"><span data-stu-id="a2243-287">The **Response Headers** section for `bundle.js` should now include a `content-encoding: gzip` header.</span></span>
    
    > ##### <span data-ttu-id="a2243-288">图23</span><span class="sxs-lookup"><span data-stu-id="a2243-288">Figure 23</span></span>  
    > <span data-ttu-id="a2243-289">"响应标题" 部分现在包含一个内容编码标题</span><span class="sxs-lookup"><span data-stu-id="a2243-289">The Response Headers section now contains a content-encoding header</span></span>  
    > <span data-ttu-id="a2243-290">![响应标题部分现在包含内容编码标题][ImageGzip]</span><span class="sxs-lookup"><span data-stu-id="a2243-290">![The Response Headers section now contains a content-encoding header][ImageGzip]</span></span>  
    
<span data-ttu-id="a2243-291">再次审核页面，以衡量影响文本压缩对页面加载性能有何种影响：</span><span class="sxs-lookup"><span data-stu-id="a2243-291">Audit the page again to measure what kind of impact text compression has on the load performance of the page:</span></span>  

1.  <span data-ttu-id="a2243-292">选择 "**审核**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a2243-292">Select the **Audits** tab.</span></span>  
1.  <span data-ttu-id="a2243-293">选择 "**执行审核**" ![ 执行审核 ][ImagePerformIcon] 。</span><span class="sxs-lookup"><span data-stu-id="a2243-293">Select **Perform an audit** ![Perform an audit][ImagePerformIcon].</span></span>  
1.  <span data-ttu-id="a2243-294">保持设置与以前一样。</span><span class="sxs-lookup"><span data-stu-id="a2243-294">Leave the settings the same as before.</span></span>  
1.  <span data-ttu-id="a2243-295">选择 "**运行审核**"。</span><span class="sxs-lookup"><span data-stu-id="a2243-295">Select **Run audit**.</span></span>  
    
    > ##### <span data-ttu-id="a2243-296">图24</span><span class="sxs-lookup"><span data-stu-id="a2243-296">Figure 24</span></span>  
    > <span data-ttu-id="a2243-297">启用文本压缩后的审核报告</span><span class="sxs-lookup"><span data-stu-id="a2243-297">An Audits report after enabling text compression</span></span>  
    > <span data-ttu-id="a2243-298">![启用文本压缩后的审核报告][ImageReport2]</span><span class="sxs-lookup"><span data-stu-id="a2243-298">![An Audits report after enabling text compression][ImageReport2]</span></span>  
    
<span data-ttu-id="a2243-299">Woohoo!</span><span class="sxs-lookup"><span data-stu-id="a2243-299">Woohoo!</span></span>  <span data-ttu-id="a2243-300">看起来像 "进度"。</span><span class="sxs-lookup"><span data-stu-id="a2243-300">That looks like progress.</span></span>  <span data-ttu-id="a2243-301">您的整体性能分数应增加，这意味着网站的速度会更快。</span><span class="sxs-lookup"><span data-stu-id="a2243-301">Your overall performance score should have increased, meaning that the site is getting faster.</span></span>  

#### <span data-ttu-id="a2243-302">现实世界中的文本压缩</span><span class="sxs-lookup"><span data-stu-id="a2243-302">Text compression in the real world</span></span>   

<span data-ttu-id="a2243-303">大多数服务器确实都有简单的修复程序，例如用于启用压缩的修补程序！</span><span class="sxs-lookup"><span data-stu-id="a2243-303">Most servers really do have simple fixes like this for enabling compression!</span></span>  <span data-ttu-id="a2243-304">只需执行有关如何配置用于压缩文本的任何服务器的搜索。</span><span class="sxs-lookup"><span data-stu-id="a2243-304">Just do a search on how to configure whatever server you use to compress text.</span></span>  

### <span data-ttu-id="a2243-305">调整图像大小</span><span class="sxs-lookup"><span data-stu-id="a2243-305">Resize images</span></span>   

<span data-ttu-id="a2243-306">你的报表指示避免大量网络负载是提高页面性能的最高机会之一。</span><span class="sxs-lookup"><span data-stu-id="a2243-306">Your report indicates that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="a2243-307">调整图像大小有助于减小网络负载的大小。</span><span class="sxs-lookup"><span data-stu-id="a2243-307">Resizing images helps reduce the size of the network payload.</span></span>  <span data-ttu-id="a2243-308">如果你的用户在移动设备屏幕上查看你的图像，该屏幕为 500-像素宽度，则在发送1500像素范围的图像时，实际上没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="a2243-308">If your user is viewing your images on a mobile device screen that is 500-pixels-wide, there is really no point in sending a 1500-pixel-wide image.</span></span>  <span data-ttu-id="a2243-309">理想情况下，发送500像素宽的图像。</span><span class="sxs-lookup"><span data-stu-id="a2243-309">Ideally, you send a 500-pixel-wide image, at most.</span></span>  

1.  <span data-ttu-id="a2243-310">在报表中，单击 "**避免大量网络负载**" 以查看应调整哪些图像的大小。</span><span class="sxs-lookup"><span data-stu-id="a2243-310">In your report, click **Avoid enormous network payloads** to see which images should be resized.</span></span>  <span data-ttu-id="a2243-311">它看起来是两个 jpg 文件超过了 2000 KB，这比所需的更大。</span><span class="sxs-lookup"><span data-stu-id="a2243-311">It looks like 2 of the jpg files are over 2000 KB, which is bigger than necessary.</span></span>  
    
    <!--
    > ##### Old Figure 27  
    > Details about the **Properly size images** opportunity  
    > ![Details about the properly size images opportunity][ImageResize]  
    -->

1.  <span data-ttu-id="a2243-312">返回到 "编辑器" 选项卡中的 "打开" `src/model.js` 。</span><span class="sxs-lookup"><span data-stu-id="a2243-312">Back in the editor tab, open `src/model.js`.</span></span>  
1.  <span data-ttu-id="a2243-313">用 `const dir = 'small'` 取代 `const dir = 'big'`。</span><span class="sxs-lookup"><span data-stu-id="a2243-313">Replace `const dir = 'big'` with `const dir = 'small'`.</span></span>  <span data-ttu-id="a2243-314">此目录包含已调整大小的相同图像的副本。</span><span class="sxs-lookup"><span data-stu-id="a2243-314">This directory contains copies of the same images which have been resized.</span></span>  
1.  <span data-ttu-id="a2243-315">再次审核页面以查看此更改对加载性能的影响。</span><span class="sxs-lookup"><span data-stu-id="a2243-315">Audit the page again to see how this change affects load performance.</span></span>  
    
    > ##### <span data-ttu-id="a2243-316">图25</span><span class="sxs-lookup"><span data-stu-id="a2243-316">Figure 25</span></span>  
    > <span data-ttu-id="a2243-317">调整图像大小后的审核报告</span><span class="sxs-lookup"><span data-stu-id="a2243-317">An Audits report after resizing images</span></span>  
    > <span data-ttu-id="a2243-318">![调整图像后的审核报告][ImageReport3]</span><span class="sxs-lookup"><span data-stu-id="a2243-318">![An Audits report after resizing images][ImageReport3]</span></span>  

<span data-ttu-id="a2243-319">看起来只有更改对整体性能分数有轻微影响。</span><span class="sxs-lookup"><span data-stu-id="a2243-319">Looks like the change only has a minor affect on the overall performance score.</span></span>  <span data-ttu-id="a2243-320">但是，分数没有明显显示的一项是保存用户的网络数据量。</span><span class="sxs-lookup"><span data-stu-id="a2243-320">However, one thing that the score does not show clearly is how much network data you are saving your users.</span></span>  <span data-ttu-id="a2243-321">旧照片的总大小约为 5.3 mb，而现在仅限于0.18 兆字节。</span><span class="sxs-lookup"><span data-stu-id="a2243-321">The total size of the old photos was around 5.3 megabytes, whereas now it is only about 0.18 megabytes.</span></span>  

#### <span data-ttu-id="a2243-322">在现实世界中调整图像大小</span><span class="sxs-lookup"><span data-stu-id="a2243-322">Resizing images in the real world</span></span>   

<span data-ttu-id="a2243-323">对于小型应用，像这样做时，执行一次性调整大小的方式可能足够好。</span><span class="sxs-lookup"><span data-stu-id="a2243-323">For a small app, doing a one-off resize like this may be good enough.</span></span>  <span data-ttu-id="a2243-324">但对于大型应用，这显然是不可缩放的。</span><span class="sxs-lookup"><span data-stu-id="a2243-324">But for a large app, this obviously is not scalable.</span></span>  <span data-ttu-id="a2243-325">下面是在大型应用中管理图像的一些策略：</span><span class="sxs-lookup"><span data-stu-id="a2243-325">Here are some strategies for managing images in large apps:</span></span>  

*   <span data-ttu-id="a2243-326">在生成过程中调整图像大小。</span><span class="sxs-lookup"><span data-stu-id="a2243-326">Resize images during your build process.</span></span>  
*   <span data-ttu-id="a2243-327">在生成过程中创建多个大小的每个图像，然后 `srcset` 在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="a2243-327">Create multiple sizes of each image during the build process and then use `srcset` in your code.</span></span>  <span data-ttu-id="a2243-328">在运行时，浏览器负责选择最适合设备的大小。</span><span class="sxs-lookup"><span data-stu-id="a2243-328">At runtime, the browser takes care of choosing which size is best for the device.</span></span>  
    <!--See [Relative-sized images][relative].  -->

<!--[relative]: /web/fundamentals/design-and-ux/responsive/images#relative_sized_images  -->  

*   <span data-ttu-id="a2243-329">使用图像 CDN，允许你在请求图像时动态调整图像大小。</span><span class="sxs-lookup"><span data-stu-id="a2243-329">Use an image CDN that lets you dynamically resize an image when you request it.</span></span>  
*   <span data-ttu-id="a2243-330">最起码，优化每个图像。</span><span class="sxs-lookup"><span data-stu-id="a2243-330">At the very least, optimize each image.</span></span>  <span data-ttu-id="a2243-331">这可能会带来巨大的节约。</span><span class="sxs-lookup"><span data-stu-id="a2243-331">This may create huge savings.</span></span>  
  <span data-ttu-id="a2243-332">优化是指通过可减小图像文件大小的特殊程序运行图像。</span><span class="sxs-lookup"><span data-stu-id="a2243-332">Optimization is when you run an image through a special program that reduces the size of the image file.</span></span>  <span data-ttu-id="a2243-333">有关更多提示，请参阅[基本图像优化][EssentialImageOptimization]。</span><span class="sxs-lookup"><span data-stu-id="a2243-333">See [Essential Image Optimization][EssentialImageOptimization] for more tips.</span></span>  

### <span data-ttu-id="a2243-334">消除呈现阻止资源</span><span class="sxs-lookup"><span data-stu-id="a2243-334">Eliminate render-blocking resources</span></span>   

<span data-ttu-id="a2243-335">您的最新报告表明，消除呈现阻止资源现在是最大的机会。</span><span class="sxs-lookup"><span data-stu-id="a2243-335">Your latest report says that eliminating render-blocking resources is now the biggest opportunity.</span></span>  

<span data-ttu-id="a2243-336">呈现阻止资源是浏览器在显示页面之前必须下载、分析和运行的外部 JavaScript 或 CSS 文件。</span><span class="sxs-lookup"><span data-stu-id="a2243-336">A render-blocking resource is an external JavaScript or CSS file that the browser must download, parse, and run before it displays the page.</span></span>  <span data-ttu-id="a2243-337">目标是仅运行正确显示页面所需的核心 CSS 和 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="a2243-337">The goal is to only run the core CSS and JavaScript code that is required to display the page properly.</span></span>  

<span data-ttu-id="a2243-338">然后，第一个任务是查找不需要在页面加载时运行的代码。</span><span class="sxs-lookup"><span data-stu-id="a2243-338">The first task, then, is to find code that you do not need to run on page load.</span></span>  

1.  <span data-ttu-id="a2243-339">选择 "**消除呈现阻止资源**" 以查看阻止的资源：</span><span class="sxs-lookup"><span data-stu-id="a2243-339">Select **Eliminate render-blocking resources** to see the resources that are blocking:</span></span>  
    `lodash.js` <span data-ttu-id="a2243-340">和 `jquery.js` 。</span><span class="sxs-lookup"><span data-stu-id="a2243-340">and `jquery.js`.</span></span>  
    
    > ##### <span data-ttu-id="a2243-341">图26</span><span class="sxs-lookup"><span data-stu-id="a2243-341">Figure 26</span></span>  
    > <span data-ttu-id="a2243-342">有关**消除呈现阻止资源**商机的详细信息</span><span class="sxs-lookup"><span data-stu-id="a2243-342">More information about the **Eliminate render-blocking resources** opportunity</span></span>  
    > <span data-ttu-id="a2243-343">![关于消除呈现阻止资源商机的详细信息][ImageRender]</span><span class="sxs-lookup"><span data-stu-id="a2243-343">![More information about the Eliminate render-blocking resources opportunity][ImageRender]</span></span>  
    
1.  <span data-ttu-id="a2243-344">按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开命令菜单，开始键入，然后 `Coverage` 选择 "**显示覆盖率**"。</span><span class="sxs-lookup"><span data-stu-id="a2243-344">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, start typing `Coverage`, and then select **Show Coverage**.</span></span>  
    
    > ##### <span data-ttu-id="a2243-345">图27</span><span class="sxs-lookup"><span data-stu-id="a2243-345">Figure 27</span></span>  
    > <span data-ttu-id="a2243-346">从 "审核" 面板打开 "命令" 菜单</span><span class="sxs-lookup"><span data-stu-id="a2243-346">Opening the Command Menu from the Audits panel</span></span>  
    > <span data-ttu-id="a2243-347">![从 "审核" 面板打开 "命令" 菜单][ImageCommandMenu]</span><span class="sxs-lookup"><span data-stu-id="a2243-347">![Opening the Command Menu from the Audits panel][ImageCommandMenu]</span></span>  
    
    > ##### <span data-ttu-id="a2243-348">图28</span><span class="sxs-lookup"><span data-stu-id="a2243-348">Figure 28</span></span>  
    > <span data-ttu-id="a2243-349">"覆盖范围" 选项卡</span><span class="sxs-lookup"><span data-stu-id="a2243-349">The Coverage tab</span></span>  
    > <span data-ttu-id="a2243-350">!["覆盖范围" 选项卡][ImageCoverage]</span><span class="sxs-lookup"><span data-stu-id="a2243-350">![The Coverage tab][ImageCoverage]</span></span>  
    
1.  <span data-ttu-id="a2243-351">选择 "**刷新** ![ 刷新" ][ImageRefreshIcon] 。</span><span class="sxs-lookup"><span data-stu-id="a2243-351">Select **Refresh** ![Refresh][ImageRefreshIcon].</span></span>  <span data-ttu-id="a2243-352">"**覆盖范围**" 选项卡提供了在 `bundle.js` `jquery.js` `lodash.js` 页面加载期间、和运行的代码中的多少概述。</span><span class="sxs-lookup"><span data-stu-id="a2243-352">The **Coverage** tab provides an overview of how much of the code in `bundle.js`, `jquery.js`, and `lodash.js` runs while the page loads.</span></span>  <span data-ttu-id="a2243-353">[图 30](#figure-30)显示，不会分别使用大约76% 和30% 的 JQuery 和 Lodash 文件。</span><span class="sxs-lookup"><span data-stu-id="a2243-353">[Figure 30](#figure-30) says that about 76% and 30% of the jQuery and Lodash files are not used, respectively.</span></span>  
    
    > ##### <span data-ttu-id="a2243-354">图29</span><span class="sxs-lookup"><span data-stu-id="a2243-354">Figure 29</span></span>  
    > <span data-ttu-id="a2243-355">覆盖范围报告</span><span class="sxs-lookup"><span data-stu-id="a2243-355">The Coverage report</span></span>  
    > <span data-ttu-id="a2243-356">![覆盖范围报告][ImageCoverageReport]</span><span class="sxs-lookup"><span data-stu-id="a2243-356">![The Coverage report][ImageCoverageReport]</span></span>  
    
1.  <span data-ttu-id="a2243-357">选择**jquery .js**行。</span><span class="sxs-lookup"><span data-stu-id="a2243-357">Select the **jquery.js** row.</span></span>  <span data-ttu-id="a2243-358">DevTools 将在 "源" 面板中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="a2243-358">DevTools opens the file in the Sources panel.</span></span>  <span data-ttu-id="a2243-359">如果它旁边有一个蓝色条，则运行一行代码。</span><span class="sxs-lookup"><span data-stu-id="a2243-359">A line of code ran if it has a blue bar next to it.</span></span>  <span data-ttu-id="a2243-360">红色条表示它未运行，并且在页面加载时绝对不需要。</span><span class="sxs-lookup"><span data-stu-id="a2243-360">A red bar means it was not run, and is definitely not needed on page load.</span></span>  
    
    > ##### <span data-ttu-id="a2243-361">图30</span><span class="sxs-lookup"><span data-stu-id="a2243-361">Figure 30</span></span>  
    > <span data-ttu-id="a2243-362">在 "源" 面板中查看 jQuery 文件</span><span class="sxs-lookup"><span data-stu-id="a2243-362">Viewing the jQuery file in the Sources panel</span></span>  
    > <span data-ttu-id="a2243-363">![在 "源" 面板中查看 jQuery 文件][ImageJQuery]</span><span class="sxs-lookup"><span data-stu-id="a2243-363">![Viewing the jQuery file in the Sources panel][ImageJQuery]</span></span>  
    
1.  <span data-ttu-id="a2243-364">按位滚动 jQuery 代码。</span><span class="sxs-lookup"><span data-stu-id="a2243-364">Scroll through the jQuery code a bit.</span></span>  <span data-ttu-id="a2243-365">某些显示 "运行" 的行实际上只是批注。</span><span class="sxs-lookup"><span data-stu-id="a2243-365">Some of the lines that get "run" are actually just comments.</span></span>  <span data-ttu-id="a2243-366">通过 minifier 中的代码运行此代码，可查看批注是减小此文件大小的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="a2243-366">Running this code through a minifier that strips comments is another way to reduce the size of this file.</span></span>  

<span data-ttu-id="a2243-367">简言之，当你使用自己的代码时，"覆盖率" 选项卡可帮助你逐行分析代码，并仅发送页面加载所需的代码。</span><span class="sxs-lookup"><span data-stu-id="a2243-367">In short, when you are working with your own code, the Coverage tab helps you analyze your code, line-by-line, and only ship the code that is needed for page load.</span></span>  

<span data-ttu-id="a2243-368">`jquery.js`和文件是否还 `lodash.js` 需要加载页面？</span><span class="sxs-lookup"><span data-stu-id="a2243-368">Are the `jquery.js` and `lodash.js` files even needed to load the page?</span></span>  <span data-ttu-id="a2243-369">"请求阻止" 选项卡显示资源不可用时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="a2243-369">The Request Blocking tab displays what happens when resources are not available.</span></span>  

1.  <span data-ttu-id="a2243-370">选择 "**网络**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a2243-370">Select the **Network** tab.</span></span>  
1.  <span data-ttu-id="a2243-371">按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）再次打开 "命令" 菜单。</span><span class="sxs-lookup"><span data-stu-id="a2243-371">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu again.</span></span>  
1.  <span data-ttu-id="a2243-372">开始键入 `blocking` ，然后选择 "**显示请求阻止**"。</span><span class="sxs-lookup"><span data-stu-id="a2243-372">Start typing `blocking` and then select **Show Request Blocking**.</span></span>  
    
    > ##### <span data-ttu-id="a2243-373">图31</span><span class="sxs-lookup"><span data-stu-id="a2243-373">Figure 31</span></span>  
    > <span data-ttu-id="a2243-374">"请求阻止" 选项卡</span><span class="sxs-lookup"><span data-stu-id="a2243-374">The Request Blocking tab</span></span>  
    > <span data-ttu-id="a2243-375">!["请求阻止" 选项卡][ImageBlocking]</span><span class="sxs-lookup"><span data-stu-id="a2243-375">![The Request Blocking tab][ImageBlocking]</span></span>  
    
1.  <span data-ttu-id="a2243-376">选择 "**添加图案** ![ ][ImageAddPatternIcon] " "添加图案"，键入 `/libs/*` ，然后按 `Enter` 以确认。</span><span class="sxs-lookup"><span data-stu-id="a2243-376">Select **Add Pattern** ![Add Pattern][ImageAddPatternIcon], type `/libs/*`, and then press `Enter` to confirm.</span></span>  
    
    > ##### <span data-ttu-id="a2243-377">图32</span><span class="sxs-lookup"><span data-stu-id="a2243-377">Figure 32</span></span>  
    > <span data-ttu-id="a2243-378">添加模式以阻止对目录的任何请求 `libs`</span><span class="sxs-lookup"><span data-stu-id="a2243-378">Adding a pattern to block any request to the `libs` directory</span></span>  
    > <span data-ttu-id="a2243-379">![添加用于阻止任何对库目录的请求的模式][ImageLibs]</span><span class="sxs-lookup"><span data-stu-id="a2243-379">![Adding a pattern to block any request to the libs directory][ImageLibs]</span></span>  
    
1.  <span data-ttu-id="a2243-380">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="a2243-380">Refresh the page.</span></span>  <span data-ttu-id="a2243-381">JQuery 和 Lodash 请求是红色的，这意味着请求被阻止。</span><span class="sxs-lookup"><span data-stu-id="a2243-381">The jQuery and Lodash requests are red, meaning that the requests were blocked.</span></span>   <span data-ttu-id="a2243-382">页面仍在加载，并且是交互式的，因此看起来不需要这些资源！</span><span class="sxs-lookup"><span data-stu-id="a2243-382">The page still loads and is interactive, so it looks like these resources are not needed whatsoever!</span></span>  
    
    > ##### <span data-ttu-id="a2243-383">图33</span><span class="sxs-lookup"><span data-stu-id="a2243-383">Figure 33</span></span>  
    > <span data-ttu-id="a2243-384">"网络" 面板显示请求已被阻止</span><span class="sxs-lookup"><span data-stu-id="a2243-384">The Network panel shows that the requests have been blocked</span></span>  
    > <span data-ttu-id="a2243-385">![网络面板显示请求已被阻止][ImageBlockedLibs]</span><span class="sxs-lookup"><span data-stu-id="a2243-385">![The Network panel shows that the requests have been blocked][ImageBlockedLibs]</span></span>  
    
1.  <span data-ttu-id="a2243-386">选择 "**删除所有模式**" ![ 删除所有模式 ][ImageRemoveIcon] 以删除 `/libs/*` 阻止模式。</span><span class="sxs-lookup"><span data-stu-id="a2243-386">Select **Remove all patterns** ![Remove all patterns][ImageRemoveIcon] to delete the `/libs/*` blocking pattern.</span></span>  

<span data-ttu-id="a2243-387">通常情况下，当任何给定资源不可用时，"请求阻止" 选项卡将非常有用，可用于模拟页面的行为方式。</span><span class="sxs-lookup"><span data-stu-id="a2243-387">In general, the Request Blocking tab is useful for simulating how your page behaves when any given resource is not available.</span></span>  

<span data-ttu-id="a2243-388">现在，从代码中删除对这些文件的引用，然后再次审核页面：</span><span class="sxs-lookup"><span data-stu-id="a2243-388">Now, remove the references to these files from the code and audit the page again:</span></span>  

1.  <span data-ttu-id="a2243-389">返回到 "编辑器" 选项卡中的 "打开" `template.html` 。</span><span class="sxs-lookup"><span data-stu-id="a2243-389">Back in the editor tab, open `template.html`.</span></span>  
1.  <span data-ttu-id="a2243-390">删除 `<script src="/libs/lodash.js">` 和 `<script src="/libs/jquery.js"></script>`。</span><span class="sxs-lookup"><span data-stu-id="a2243-390">Delete `<script src="/libs/lodash.js">` and `<script src="/libs/jquery.js"></script>`.</span></span>  
1.  <span data-ttu-id="a2243-391">等待网站重新构建和重新部署。</span><span class="sxs-lookup"><span data-stu-id="a2243-391">Wait for the site to re-build and re-deploy.</span></span>  
1.  <span data-ttu-id="a2243-392">从 "**审核**" 面板中再次审核页面。</span><span class="sxs-lookup"><span data-stu-id="a2243-392">Audit the page again from the **Audits** panel.</span></span>  <span data-ttu-id="a2243-393">您的整体成绩将再次改进。</span><span class="sxs-lookup"><span data-stu-id="a2243-393">Your overall score should have improved again.</span></span>  
    
    > ##### <span data-ttu-id="a2243-394">图34</span><span class="sxs-lookup"><span data-stu-id="a2243-394">Figure 34</span></span>  
    > <span data-ttu-id="a2243-395">删除 "呈现阻止" 资源后的审核报告</span><span class="sxs-lookup"><span data-stu-id="a2243-395">An Audits report after removing the render-blocking resources</span></span>  
    > <span data-ttu-id="a2243-396">![删除呈现阻止资源后的审核报告][ImageReport4]</span><span class="sxs-lookup"><span data-stu-id="a2243-396">![An Audits report after removing the render-blocking resources][ImageReport4]</span></span>  

#### <span data-ttu-id="a2243-397">优化现实世界中的关键呈现路径</span><span class="sxs-lookup"><span data-stu-id="a2243-397">Optimizing the Critical Rendering Path in the real-world</span></span>   

<span data-ttu-id="a2243-398">**关键呈现路径**是指加载页面所需的代码。</span><span class="sxs-lookup"><span data-stu-id="a2243-398">The **Critical Rendering Path** refers to the code that you need to load a page.</span></span>  <span data-ttu-id="a2243-399">通常，仅在页面加载期间传输关键代码，然后延缓加载所有其他内容，从而加快页面负载。</span><span class="sxs-lookup"><span data-stu-id="a2243-399">In general, speed up page load by only shipping critical code during the page load, and then lazy-loading everything else.</span></span>  

<!--[CRP]: /web/fundamentals/performance/critical-rendering-path/  -->  

*   <span data-ttu-id="a2243-400">你可能无法找到能够完全删除的脚本，但你可能会发现在页面加载期间不需要请求的多个脚本，而是可能会异步请求。</span><span class="sxs-lookup"><span data-stu-id="a2243-400">It is unlikely that you are able to find scripts that you are able to remove outright, but you may find many scripts that you do not need to request during the page load, and instead may be requested asynchronously.</span></span>  <!--See [Using async or defer][async].  -->  
*   <span data-ttu-id="a2243-401">如果你使用的是框架，请检查它是否具有生产模式。</span><span class="sxs-lookup"><span data-stu-id="a2243-401">If you are using a framework, check if it has a production mode.</span></span>  <span data-ttu-id="a2243-402">此模式可能使用[树形握手][WebpackTreeShaking]之类的功能来消除阻止关键呈现的不必要代码。</span><span class="sxs-lookup"><span data-stu-id="a2243-402">This mode may use a feature such as [tree shaking][WebpackTreeShaking] in order to eliminate unnecessary code that is blocking the critical render.</span></span>  

<!--[async]: /web/fundamentals/performance/optimizing-content-efficiency/loading-third-party-javascript/#use_async_or_defer  -->  

### <span data-ttu-id="a2243-403">执行较少的主线程工作</span><span class="sxs-lookup"><span data-stu-id="a2243-403">Do less main thread work</span></span>   

<span data-ttu-id="a2243-404">您的最新报告显示了 "商机" 部分中的一些小的可能节约，但如果您在 "诊断" 部分中向下查看，那么最大的瓶颈似乎是太多的主线程活动。</span><span class="sxs-lookup"><span data-stu-id="a2243-404">Your latest report shows some minor potential savings in the Opportunities section, but if you look down in the Diagnostics section, it looks like the biggest bottleneck is too much main thread activity.</span></span>  

<span data-ttu-id="a2243-405">主线程是浏览器完成显示页面所需的大部分工作（如分析和运行 HTML、CSS 和 JavaScript）的位置。</span><span class="sxs-lookup"><span data-stu-id="a2243-405">The main thread is where the browser does most of the work needed to display a page, such as parsing and running HTML, CSS, and JavaScript.</span></span>  

<span data-ttu-id="a2243-406">目标是使用 "性能" 面板分析主线程在页面加载期间执行的工作，并查找推迟或删除不必要的工作的方法。</span><span class="sxs-lookup"><span data-stu-id="a2243-406">The goal is to use the Performance panel to analyze what work the main thread is doing while the page loads, and find ways to defer or remove unnecessary work.</span></span>  

1.  <span data-ttu-id="a2243-407">选择 "**性能**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a2243-407">Select the **Performance** tab.</span></span>  
1.  <span data-ttu-id="a2243-408">选择 "**捕获设置** ![ 捕获设置" ][ImageCaptureIcon] 。</span><span class="sxs-lookup"><span data-stu-id="a2243-408">Select **Capture Settings** ![Capture Settings][ImageCaptureIcon].</span></span>  
1.  <span data-ttu-id="a2243-409">将**网络**设置为**慢速 3g**和**CPU** **6x 减速**。</span><span class="sxs-lookup"><span data-stu-id="a2243-409">Set **Network** to **Slow 3G** and **CPU** to **6x slowdown**.</span></span>  <span data-ttu-id="a2243-410">移动设备通常比笔记本或桌面具有更多硬件约束，因此这些设置使你可以体验页面加载，就像使用的功能较少的设备一样。</span><span class="sxs-lookup"><span data-stu-id="a2243-410">Mobile devices typically have more hardware constraints than laptops or desktops, so these settings let you experience the page load as if you were using a less powerful device.</span></span>  
1.  <span data-ttu-id="a2243-411">选择 "**刷新** ![ 刷新" ][ImageRefreshIcon] 。</span><span class="sxs-lookup"><span data-stu-id="a2243-411">Select **Refresh** ![Refresh][ImageRefreshIcon].</span></span>  <span data-ttu-id="a2243-412">DevTools 刷新页面，然后生成所有已执行工作的可视化效果，以便加载页面。</span><span class="sxs-lookup"><span data-stu-id="a2243-412">DevTools refreshes the page and then produces a visualization of all the work performed in order to load the page.</span></span>  <span data-ttu-id="a2243-413">此可视化对象称为**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="a2243-413">This visualization is referred to as the **trace**.</span></span>  
    
    > ##### <span data-ttu-id="a2243-414">图35</span><span class="sxs-lookup"><span data-stu-id="a2243-414">Figure 35</span></span>  
    > <span data-ttu-id="a2243-415">页面加载的性能面板跟踪</span><span class="sxs-lookup"><span data-stu-id="a2243-415">The Performance panel trace of the page load</span></span>  
    > <span data-ttu-id="a2243-416">![页面加载的性能面板跟踪][ImagePerformance]</span><span class="sxs-lookup"><span data-stu-id="a2243-416">![The Performance panel trace of the page load][ImagePerformance]</span></span>  

<span data-ttu-id="a2243-417">跟踪按时间顺序从左到右显示活动。</span><span class="sxs-lookup"><span data-stu-id="a2243-417">The trace shows activity chronologically, from left to right.</span></span>  <span data-ttu-id="a2243-418">顶部的 FPS、CPU 和网络图概括介绍了每秒帧数、CPU 活动和网络活动。</span><span class="sxs-lookup"><span data-stu-id="a2243-418">The FPS, CPU, and NET charts at the top give you an overview of frames per second, CPU activity, and network activity.</span></span>  <span data-ttu-id="a2243-419">您在[图 37](#figure-37)中看到的黄色选中的块表示 CPU 与脚本活动完全繁忙。</span><span class="sxs-lookup"><span data-stu-id="a2243-419">The block of yellow selected that you see in [Figure 37](#figure-37) means that the CPU was completely busy with scripting activity.</span></span>  <span data-ttu-id="a2243-420">这是一条提示，您可以通过执行较少的 JavaScript 工作来加快页面负载。</span><span class="sxs-lookup"><span data-stu-id="a2243-420">This is a clue that you may be able to speed up page load by doing less JavaScript work.</span></span>  

> ##### <span data-ttu-id="a2243-421">图36</span><span class="sxs-lookup"><span data-stu-id="a2243-421">Figure 36</span></span>  
> <span data-ttu-id="a2243-422">跟踪的概述部分</span><span class="sxs-lookup"><span data-stu-id="a2243-422">The Overview section of the trace</span></span>  
> <span data-ttu-id="a2243-423">![跟踪的概述部分][ImageOverview]</span><span class="sxs-lookup"><span data-stu-id="a2243-423">![The Overview section of the trace][ImageOverview]</span></span>  

<span data-ttu-id="a2243-424">调查跟踪以查找执行更少 JavaScript 工作的方法：</span><span class="sxs-lookup"><span data-stu-id="a2243-424">Investigate the trace to find ways to do less JavaScript work:</span></span>  

1.  <span data-ttu-id="a2243-425">选择 "**计时**" 部分将其展开。</span><span class="sxs-lookup"><span data-stu-id="a2243-425">Select the **Timings** section to expand it.</span></span>  <span data-ttu-id="a2243-426">根据可能有一组[计时][MDNUserTimingApi]对响应的情况，似乎 Tony 的应用正在使用响应的开发模式。</span><span class="sxs-lookup"><span data-stu-id="a2243-426">Based on the fact that there may be a bunch of [Timings][MDNUserTimingApi] measures from React, it seems like Tony's app is using the development mode of React.</span></span>  <span data-ttu-id="a2243-427">切换到 "响应生产模式" 可能会产生一些简单的性能获胜。</span><span class="sxs-lookup"><span data-stu-id="a2243-427">Switching to the production mode of React may yield some easy performance wins.</span></span>  
    
    > ##### <span data-ttu-id="a2243-428">图37</span><span class="sxs-lookup"><span data-stu-id="a2243-428">Figure 37</span></span>  
    > <span data-ttu-id="a2243-429">"计时" 部分</span><span class="sxs-lookup"><span data-stu-id="a2243-429">The Timings section</span></span>  
    > <span data-ttu-id="a2243-430">![计时部分][ImageUserTiming]</span><span class="sxs-lookup"><span data-stu-id="a2243-430">![The Timings section][ImageUserTiming]</span></span>  

1.  <span data-ttu-id="a2243-431">再次选择 "**计时**" 以折叠该部分。</span><span class="sxs-lookup"><span data-stu-id="a2243-431">Select **Timings** again to collapse that section.</span></span>  
1.  <span data-ttu-id="a2243-432">浏览**主**分区。</span><span class="sxs-lookup"><span data-stu-id="a2243-432">Browse the **Main** section.</span></span>  <span data-ttu-id="a2243-433">此部分显示按时间顺序排列的主线程活动（从左到右）的日志。</span><span class="sxs-lookup"><span data-stu-id="a2243-433">This section shows a chronological log of main thread activity, from left to right.</span></span>  <span data-ttu-id="a2243-434">Y 轴（从上到下）显示发生事件的原因。</span><span class="sxs-lookup"><span data-stu-id="a2243-434">The y-axis (top to bottom) shows why events occurred.</span></span>  <span data-ttu-id="a2243-435">例如，在[图 39](#figure-39)中，该事件导致运行该函数，导致运行，导致运行， `Evaluate Script` `(anonymous)` `(anonymous)` `__webpack__require__` 等等。</span><span class="sxs-lookup"><span data-stu-id="a2243-435">For example, in [Figure 39](#figure-39), the `Evaluate Script` event caused the `(anonymous)` function to run, which caused `(anonymous)` to run, which caused `__webpack__require__` to run, and so on.</span></span>  
    
    > ##### <span data-ttu-id="a2243-436">图38</span><span class="sxs-lookup"><span data-stu-id="a2243-436">Figure 38</span></span>  
    > <span data-ttu-id="a2243-437">主要部分</span><span class="sxs-lookup"><span data-stu-id="a2243-437">The Main section</span></span>  
    > <span data-ttu-id="a2243-438">![主要部分][ImageMain]</span><span class="sxs-lookup"><span data-stu-id="a2243-438">![The Main section][ImageMain]</span></span>  

1.  <span data-ttu-id="a2243-439">向下滚动到**主**区域的底部。</span><span class="sxs-lookup"><span data-stu-id="a2243-439">Scroll down to the bottom of the **Main** section.</span></span>  <span data-ttu-id="a2243-440">使用框架时，大部分较高的活动都是由框架导致的，该框架通常不受控制。</span><span class="sxs-lookup"><span data-stu-id="a2243-440">When you use a framework, most of the upper activity is caused by the framework, which is usually out of your control.</span></span>  <span data-ttu-id="a2243-441">应用引发的活动通常位于底部。</span><span class="sxs-lookup"><span data-stu-id="a2243-441">The activity caused by your app is usually at the bottom.</span></span>  <span data-ttu-id="a2243-442">在此应用中，名为的函数似乎 `App` 导致了许多对函数的请求 `mineBitcoin` 。</span><span class="sxs-lookup"><span data-stu-id="a2243-442">In this app, it seems like a function named `App` is causing a lot of requests to a `mineBitcoin` function.</span></span>  <span data-ttu-id="a2243-443">听起来好像 Tony 可能会使用其风扇的设备来挖掘 cryptocurrency .。。</span><span class="sxs-lookup"><span data-stu-id="a2243-443">It sounds like Tony might be using the devices of his fans to mine cryptocurrency...</span></span>  
    
    > ##### <span data-ttu-id="a2243-444">图39</span><span class="sxs-lookup"><span data-stu-id="a2243-444">Figure 39</span></span>  
    > <span data-ttu-id="a2243-445">将鼠标悬停在 `mineBitcoin` 活动上</span><span class="sxs-lookup"><span data-stu-id="a2243-445">Hovering over the `mineBitcoin` activity</span></span>  
    > <span data-ttu-id="a2243-446">![将鼠标悬停在 mineBitcoin 活动上][ImageMine]</span><span class="sxs-lookup"><span data-stu-id="a2243-446">![Hovering over the mineBitcoin activity][ImageMine]</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="a2243-447">尽管你的框架所提供的请求通常不在你的控件中，但有时你可能会导致框架运行效率较低下的方式构建你的应用。</span><span class="sxs-lookup"><span data-stu-id="a2243-447">Although the requests that your framework makes are usually out of your control, sometimes you may structure your app in a way that causes the framework to run inefficiently.</span></span>  <span data-ttu-id="a2243-448">将你的应用重构为高效使用框架是一种减少主线程工作的方法。</span><span class="sxs-lookup"><span data-stu-id="a2243-448">Restructuring your app to use the framework efficiently is a way to do less main thread work.</span></span>  <span data-ttu-id="a2243-449">但是，这需要深入了解你的框架的工作原理以及你自己的代码中所做的更改，以便更高效地使用框架。</span><span class="sxs-lookup"><span data-stu-id="a2243-449">However, this requires a deep understanding of how your framework works, and what kind of changes you make in your own code in order to use the framework more efficiently.</span></span>  

1.  <span data-ttu-id="a2243-450">展开 "**下**" 部分。</span><span class="sxs-lookup"><span data-stu-id="a2243-450">Expand the **Bottom-Up** section.</span></span>  <span data-ttu-id="a2243-451">此选项卡可分解最长时间的活动。</span><span class="sxs-lookup"><span data-stu-id="a2243-451">This tab breaks down what activities took up the most time.</span></span>  <span data-ttu-id="a2243-452">如果在下图中看不到任何内容，请单击 "**主要**部分的标签"。</span><span class="sxs-lookup"><span data-stu-id="a2243-452">If you do not see anything in the Bottom-Up section, click the label for **Main** section.</span></span>  <span data-ttu-id="a2243-453">**自下而上**的部分仅显示当前已选择的任何活动或活动组的信息。</span><span class="sxs-lookup"><span data-stu-id="a2243-453">The **Bottom-Up** section only shows information for whatever activity, or group of activity, you have currently selected.</span></span>  <span data-ttu-id="a2243-454">例如，如果单击其中一个 `mineBitcoin` 活动，则 "**下移**" 部分将仅显示该活动的信息。</span><span class="sxs-lookup"><span data-stu-id="a2243-454">For example, if you clicked on one of the `mineBitcoin` activities, the **Bottom-Up** section is only going to show information for that one activity.</span></span>  
    
    > ##### <span data-ttu-id="a2243-455">图40</span><span class="sxs-lookup"><span data-stu-id="a2243-455">Figure 40</span></span>  
    > <span data-ttu-id="a2243-456">"下" 选项卡</span><span class="sxs-lookup"><span data-stu-id="a2243-456">The Bottom-Up tab</span></span>  
    > <span data-ttu-id="a2243-457">![自下而上的选项卡][ImageBottomUp]</span><span class="sxs-lookup"><span data-stu-id="a2243-457">![The Bottom-Up tab][ImageBottomUp]</span></span>  

<span data-ttu-id="a2243-458">"**自时间**" 列显示在每个活动中直接花费的时间量。</span><span class="sxs-lookup"><span data-stu-id="a2243-458">The **Self Time** column shows you how much time was spent directly in each activity.</span></span>  <span data-ttu-id="a2243-459">例如，[图 41](#figure-41)显示该函数所用的主线程时间的 63% `mineBitcoin` 。</span><span class="sxs-lookup"><span data-stu-id="a2243-459">For example, [Figure 41](#figure-41) shows that about 63% of main thread time was spent on the `mineBitcoin` function.</span></span>  

<span data-ttu-id="a2243-460">了解使用生产模式和减少 JavaScript 活动的时间可能会加速页面加载。</span><span class="sxs-lookup"><span data-stu-id="a2243-460">Time to see whether using production mode and reducing JavaScript activity may speed up the page load.</span></span>  <span data-ttu-id="a2243-461">从生产模式开始：</span><span class="sxs-lookup"><span data-stu-id="a2243-461">Start with production mode:</span></span>  

1.  <span data-ttu-id="a2243-462">在 "编辑器" 选项卡中，打开 `webpack.config.js` 。</span><span class="sxs-lookup"><span data-stu-id="a2243-462">In the editor tab, open `webpack.config.js`.</span></span>  
1.  <span data-ttu-id="a2243-463">将 `"mode":"development"` 更改为 `"mode":"production"`。</span><span class="sxs-lookup"><span data-stu-id="a2243-463">Change `"mode":"development"` to `"mode":"production"`.</span></span>  
1.  <span data-ttu-id="a2243-464">等待部署新版本。</span><span class="sxs-lookup"><span data-stu-id="a2243-464">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="a2243-465">再次审核该页面。</span><span class="sxs-lookup"><span data-stu-id="a2243-465">Audit the page again.</span></span>  
    
    > ##### <span data-ttu-id="a2243-466">图41</span><span class="sxs-lookup"><span data-stu-id="a2243-466">Figure 41</span></span>  
    > <span data-ttu-id="a2243-467">将 webpack 配置为使用生产模式后的审核报告</span><span class="sxs-lookup"><span data-stu-id="a2243-467">An Audits report after configuring webpack to use production mode</span></span>  
    > <span data-ttu-id="a2243-468">![将 webpack 配置为使用生产模式后的审核报告][ImageReport5]</span><span class="sxs-lookup"><span data-stu-id="a2243-468">![An Audits report after configuring webpack to use production mode][ImageReport5]</span></span>  

<span data-ttu-id="a2243-469">通过删除以下请求来减少 JavaScript 活动 `mineBitcoin` ：</span><span class="sxs-lookup"><span data-stu-id="a2243-469">Reduce JavaScript activity by removing the request to `mineBitcoin`:</span></span>  

1.  <span data-ttu-id="a2243-470">在 "编辑器" 选项卡中，打开 `src/App.jsx` 。</span><span class="sxs-lookup"><span data-stu-id="a2243-470">In the editor tab, open `src/App.jsx`.</span></span>  
1.  <span data-ttu-id="a2243-471">在中将请求注释为 `this.mineBitcoin(1500)` `constructor` 。</span><span class="sxs-lookup"><span data-stu-id="a2243-471">Comment out the request to `this.mineBitcoin(1500)` in the `constructor`.</span></span>  
1.  <span data-ttu-id="a2243-472">等待部署新版本。</span><span class="sxs-lookup"><span data-stu-id="a2243-472">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="a2243-473">再次审核该页面。</span><span class="sxs-lookup"><span data-stu-id="a2243-473">Audit the page again.</span></span>  
    
    > ##### <span data-ttu-id="a2243-474">图42</span><span class="sxs-lookup"><span data-stu-id="a2243-474">Figure 42</span></span>  
    > <span data-ttu-id="a2243-475">删除不必要的 JavaScript 工作后的审核报告</span><span class="sxs-lookup"><span data-stu-id="a2243-475">An Audits report after removing unnecessary JavaScript work</span></span>  
    > <span data-ttu-id="a2243-476">![删除不必要的 JavaScript 工作后的审核报告][ImageReport6]</span><span class="sxs-lookup"><span data-stu-id="a2243-476">![An Audits report after removing unnecessary JavaScript work][ImageReport6]</span></span>  

<span data-ttu-id="a2243-477">看起来，最后一个更改导致性能巨大的跳跃。</span><span class="sxs-lookup"><span data-stu-id="a2243-477">Looks like that last change caused a massive jump in performance!</span></span>  

> [!NOTE]
> <span data-ttu-id="a2243-478">本部分提供了 "性能" 面板的简要介绍。</span><span class="sxs-lookup"><span data-stu-id="a2243-478">This section provided a rather brief introduction to the Performance panel.</span></span>  <span data-ttu-id="a2243-479">请参阅[性能分析参考][DevtoolsEvaluatePerformanceReference]，了解有关如何分析页面性能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a2243-479">See [Performance Analysis Reference][DevtoolsEvaluatePerformanceReference] to learn more about how to analyze page performance.</span></span>  

<!--todo: add section when available -->  

#### <span data-ttu-id="a2243-480">在现实世界中执行较少的主线程工作</span><span class="sxs-lookup"><span data-stu-id="a2243-480">Doing less main thread work in the real world</span></span>   

<span data-ttu-id="a2243-481">通常，"**性能**" 面板是了解你的网站在加载时所执行的活动的最常用方式，并查找删除不必要的活动的方法。</span><span class="sxs-lookup"><span data-stu-id="a2243-481">In general, the **Performance** panel is the most common way to understand what activity your site does as it loads, and find ways to remove unnecessary activity.</span></span>  

<span data-ttu-id="a2243-482">如果你更喜欢更喜欢的方法 `console.log()` ，[用户计时 API][MDNUserTimingApi]使你可以任意标记你的应用生命周期的特定阶段，以便跟踪这些阶段所需的时间。</span><span class="sxs-lookup"><span data-stu-id="a2243-482">If you prefer an approach that feels more like `console.log()`, the [User Timing API][MDNUserTimingApi] enables you to arbitrarily mark up certain phases of your app lifecycle, in order to track how long each of those phases takes.</span></span>  

## <span data-ttu-id="a2243-483">摘要</span><span class="sxs-lookup"><span data-stu-id="a2243-483">Summary</span></span>   

*   <span data-ttu-id="a2243-484">无论何时设置以优化网站的负载性能，都将始终从审核开始。</span><span class="sxs-lookup"><span data-stu-id="a2243-484">Whenever you set out to optimize the load performance of a site, always start with an audit.</span></span>  <span data-ttu-id="a2243-485">审核建立了一个基准，并提供了有关如何改进的提示。</span><span class="sxs-lookup"><span data-stu-id="a2243-485">The audit establishes a baseline, and gives you tips on how to improve.</span></span>  
*   <span data-ttu-id="a2243-486">一次更改一个更改，并在每次更改后审核页面，以了解该隔离更改对性能有何影响。</span><span class="sxs-lookup"><span data-stu-id="a2243-486">Make one change at a time, and audit the page after each change in order to see how that isolated change affects performance.</span></span>  

<!--
## Next steps   

*   Run audits on your own site!  If you need help interpreting your report, or finding ways to improve your load performance, check out [Feedback](#feedback) for ways to get help from the DevTools community.  Stack Overflow, the mailing list, or Twitter are probably best for these types of questions.  
*   Please leave [feedback](#feedback) on this tutorial.  I really do use the data to make better tutorials for you.  
-->  

<!--    -->  



<!-- image links -->  

[ImageAddPatternIcon]: /microsoft-edge/devtools-guide-chromium/media/add-pattern-icon.msft.png  
[ImageCaptureIcon]: /microsoft-edge/devtools-guide-chromium/media/capture-icon.msft.png  
[ImageLargeResourceRowsButtonIcon]: /microsoft-edge/devtools-guide-chromium/media/large-resource-rows-button-icon.msft.png  
[ImageMorePanelsIcon]: /microsoft-edge/devtools-guide-chromium/media/more-panels-icon.msft.png  
[ImagePerformIcon]: /microsoft-edge/devtools-guide-chromium/media/perform-icon.msft.png  
[ImageRefreshIcon]: /microsoft-edge/devtools-guide-chromium/media/reload-icon.msft.png  
[ImageRemoveIcon]: /microsoft-edge/devtools-guide-chromium/media/remove-icon.msft.png  

[ImageTony]: /microsoft-edge/devtools-guide-chromium/media/speed-tony.msft.png "图1： Tony 猫"  
[ImageEditor]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-server-js.msft.png "图2： "编辑器" 选项卡"  
[ImageMenu]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-server-js-remix-project.msft.png "图3：单击 "tony" 后出现的菜单"  
[ImageDemo]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-show-live.msft.png "图4： "演示" 选项卡"  
[ImageDevtools]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-show-live-console.msft.png "图5： DevTools 和演示"  
[ImageUndocked]: /microsoft-edge/devtools-guide-chromium/media/speed-console.msft.png "图6：未插接 DevTools"  
[ImageAudits]: /microsoft-edge/devtools-guide-chromium/media/speed-audits-performance.msft.png "图7： "审核" 面板"  
[ImageReport]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png "图8：针对网站性能的 "审核" 面板的报表"  
<!--[ImageError]: /microsoft-edge/devtools-guide-chromium/media/speed-.msft.png "Old Figure 9: A report that errored"  -->  
<span data-ttu-id="a2243-495">[ImageOverall]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png "图9：整体性能分数"</span><span class="sxs-lookup"><span data-stu-id="a2243-495">[ImageOverall]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png "Figure 9: The overall performance score"</span></span>  
<span data-ttu-id="a2243-496">[ImageMetrics]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png "图10：" 指标 "部分"</span><span class="sxs-lookup"><span data-stu-id="a2243-496">[ImageMetrics]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png "Figure 10: The Metrics section"</span></span>  
<span data-ttu-id="a2243-497">[ImageFirstMeaningfulPaint]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png "图11：选择突出显示的切换按钮以展开指标项目"</span><span class="sxs-lookup"><span data-stu-id="a2243-497">[ImageFirstMeaningfulPaint]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png "Figure 11: Select the highlighted toggle button to expand the Metrics items"</span></span>  
<span data-ttu-id="a2243-498">[ImageScreenshots]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png "图12：加载时如何查看页面的屏幕截图"</span><span class="sxs-lookup"><span data-stu-id="a2243-498">[ImageScreenshots]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png "Figure 12: Screenshots of how the page looked while loading"</span></span>  
<span data-ttu-id="a2243-499">[ImageOpportunities]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-opportunities.msft.png "图13：商机部分"</span><span class="sxs-lookup"><span data-stu-id="a2243-499">[ImageOpportunities]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-opportunities.msft.png "Figure 13: The Opportunities section"</span></span>  
<span data-ttu-id="a2243-500">[ImageCompression]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png "图14：消除呈现阻止资源的机会"</span><span class="sxs-lookup"><span data-stu-id="a2243-500">[ImageCompression]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png "Figure 14: Eliminate render-blocking resources opportunity"</span></span>  
<span data-ttu-id="a2243-501">[ImageReference]：/microsoft-edge/devtools-guide-chromium/media/speed-web-dev-performance-audits.msft.png "图15：用于消除呈现阻止资源商机的文档"</span><span class="sxs-lookup"><span data-stu-id="a2243-501">[ImageReference]: /microsoft-edge/devtools-guide-chromium/media/speed-web-dev-performance-audits.msft.png "Figure 15: Documentation for the Eliminate render-blocking resources opportunity"</span></span>  
<span data-ttu-id="a2243-502">[ImageDiagnostics]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png "图16：诊断部分"</span><span class="sxs-lookup"><span data-stu-id="a2243-502">[ImageDiagnostics]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png "Figure 16: The Diagnostics section"</span></span>  
<span data-ttu-id="a2243-503">[ImagePassed]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png "图17：已通过的审核" 部分 "</span><span class="sxs-lookup"><span data-stu-id="a2243-503">[ImagePassed]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png "Figure 17: The Passed Audits section"</span></span>  
<span data-ttu-id="a2243-504">[ImageNetwork]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network.msft.png "图18：网络面板"</span><span class="sxs-lookup"><span data-stu-id="a2243-504">[ImageNetwork]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network.msft.png "Figure 18: The Network panel"</span></span>  
<span data-ttu-id="a2243-505">[ImageLargeRows]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png "图19：网络请求表中的较大行"</span><span class="sxs-lookup"><span data-stu-id="a2243-505">[ImageLargeRows]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png "Figure 19: Large rows in the network requests table"</span></span>  
<span data-ttu-id="a2243-506">[ImageHeaders]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png "图20：标题" 选项卡 "</span><span class="sxs-lookup"><span data-stu-id="a2243-506">[ImageHeaders]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png "Figure 20: The Headers tab"</span></span>  
<span data-ttu-id="a2243-507">[ImageServer]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-server-js.msft.png "图21：编辑 server .js"</span><span class="sxs-lookup"><span data-stu-id="a2243-507">[ImageServer]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-server-js.msft.png "Figure 21: Editing server.js"</span></span>  
<!--[ImageBuilding]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-server-js-edited.msft.png "Old Figure 22: The animation that indicates that the site is getting built"  -->  
<span data-ttu-id="a2243-508">[ImageRequests]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network-main.msft.png "图22： Size 列现在显示两个不同的文本资源值"</span><span class="sxs-lookup"><span data-stu-id="a2243-508">[ImageRequests]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network-main.msft.png "Figure 22: The Size column now shows 2 different values for text resources"</span></span>  
<span data-ttu-id="a2243-509">[ImageGzip]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png "图23：" 响应标题 "部分现在包含 `content-encoding` 标题"</span><span class="sxs-lookup"><span data-stu-id="a2243-509">[ImageGzip]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png "Figure 23: The Response Headers section now contains a `content-encoding` header"</span></span>  
<span data-ttu-id="a2243-510">[ImageReport2]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance.msft.png "图24：启用文本压缩后的审核报告"</span><span class="sxs-lookup"><span data-stu-id="a2243-510">[ImageReport2]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance.msft.png "Figure 24: An Audits report after enabling text compression"</span></span>  
<!--[ImageResize]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png "Old Figure 27: Details about the properly size images opportunity"  -->
<span data-ttu-id="a2243-511">[ImageReport3]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-compression-small-images-audits-performance.msft.png "图25：调整图像大小后的审核报告"</span><span class="sxs-lookup"><span data-stu-id="a2243-511">[ImageReport3]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-compression-small-images-audits-performance.msft.png "Figure 25: An Audits report after resizing images"</span></span>  
<span data-ttu-id="a2243-512">[ImageRender]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png "图26：有关消除呈现阻止资源商机的详细信息"</span><span class="sxs-lookup"><span data-stu-id="a2243-512">[ImageRender]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png "Figure 26: More information about the Eliminate render-blocking resources opportunity"</span></span>  
<span data-ttu-id="a2243-513">[ImageCommandMenu]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png "图27：从" 审核 "面板中打开" 命令 "菜单"</span><span class="sxs-lookup"><span data-stu-id="a2243-513">[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png "Figure 27: Opening the Command Menu from the Audits panel"</span></span>  
<span data-ttu-id="a2243-514">[ImageCoverage]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png "图28：" 覆盖率 "选项卡"</span><span class="sxs-lookup"><span data-stu-id="a2243-514">[ImageCoverage]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png "Figure 28: The Coverage tab"</span></span>  
<span data-ttu-id="a2243-515">[ImageCoverageReport]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png "图29：覆盖范围报告"</span><span class="sxs-lookup"><span data-stu-id="a2243-515">[ImageCoverageReport]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png "Figure 29: The Coverage report"</span></span>  
<span data-ttu-id="a2243-516">[ImageJQuery]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png "图30：在" 源 "面板中查看 jQuery 文件"</span><span class="sxs-lookup"><span data-stu-id="a2243-516">[ImageJQuery]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png "Figure 30: Viewing the jQuery file in the Sources panel"</span></span>  
<span data-ttu-id="a2243-517">[ImageBlocking]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png "图31：" 请求阻止 "选项卡"</span><span class="sxs-lookup"><span data-stu-id="a2243-517">[ImageBlocking]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png "Figure 31: The Request Blocking tab"</span></span>  
<span data-ttu-id="a2243-518">[ImageLibs]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png "图32：添加模式以阻止任何对库目录的请求"</span><span class="sxs-lookup"><span data-stu-id="a2243-518">[ImageLibs]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png "Figure 32: Adding a pattern to block any request to the libs directory"</span></span>  
<span data-ttu-id="a2243-519">[ImageBlockedLibs]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png "图33：" 网络 "面板显示请求已被阻止</span><span class="sxs-lookup"><span data-stu-id="a2243-519">[ImageBlockedLibs]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png "Figure 33: The Network panel shows that the requests have been blocked"</span></span>  
<span data-ttu-id="a2243-520">[ImageReport4]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png "图34：删除" 呈现阻止资源 "之后的审核报告</span><span class="sxs-lookup"><span data-stu-id="a2243-520">[ImageReport4]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png "Figure 34: An Audits report after removing the render-blocking resources"</span></span>  
<span data-ttu-id="a2243-521">[ImagePerformance]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png "图35：页面加载的性能面板跟踪"</span><span class="sxs-lookup"><span data-stu-id="a2243-521">[ImagePerformance]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png "Figure 35: The Performance panel trace of the page load"</span></span>  
<span data-ttu-id="a2243-522">[ImageOverview]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png "图36：跟踪的概述部分"</span><span class="sxs-lookup"><span data-stu-id="a2243-522">[ImageOverview]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png "Figure 36: The Overview section of the trace"</span></span>  
<span data-ttu-id="a2243-523">[ImageUserTiming]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png "图37：计时" 部分 "</span><span class="sxs-lookup"><span data-stu-id="a2243-523">[ImageUserTiming]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png "Figure 37: The Timings section"</span></span>  
<span data-ttu-id="a2243-524">[ImageMain]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png "图38：主部分"</span><span class="sxs-lookup"><span data-stu-id="a2243-524">[ImageMain]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png "Figure 38: The Main section"</span></span>  
<span data-ttu-id="a2243-525">[ImageMine]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png "图39：将鼠标悬停在 mineBitcoin 活动上"</span><span class="sxs-lookup"><span data-stu-id="a2243-525">[ImageMine]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png "Figure 39: Hovering over the mineBitcoin activity"</span></span>  
<span data-ttu-id="a2243-526">[ImageBottomUp]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png "图40：下-向上选项卡"</span><span class="sxs-lookup"><span data-stu-id="a2243-526">[ImageBottomUp]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png "Figure 40: The Bottom-Up tab"</span></span>  
<span data-ttu-id="a2243-527">[ImageReport5]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png "图41：配置 webpack 以使用生产模式后的审核报告"</span><span class="sxs-lookup"><span data-stu-id="a2243-527">[ImageReport5]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png "Figure 41: An Audits report after configuring webpack to use production mode"</span></span>  
<span data-ttu-id="a2243-528">[ImageReport6]：/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png "图42：删除不必要的 JavaScript 工作后的审核报告"</span><span class="sxs-lookup"><span data-stu-id="a2243-528">[ImageReport6]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png "Figure 42: An Audits report after removing unnecessary JavaScript work"</span></span>  

<!-- links -->  

[DevtoolsEvaluatePerformanceReference]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference "性能分析参考"  

[CourseraIntroductionWebDevelopmentClass]: https://www.coursera.org/learn/web-development#syllabus "Web 开发类简介 |Coursera"  

[EssentialImageOptimization]: https://images.guide "基本图像优化"  

[MDNContentEncodingDirectives]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Encoding#Directives "指令-内容编码 |MDN"  
[MDNUserTimingApi]: https://developer.mozilla.org/docs/Web/API/User_Timing_API "用户计时 API |MDN"  

[WebpackTreeShaking]: https://webpack.js.org/guides/tree-shaking "树形摇动 |webpack"  

> [!NOTE]
> <span data-ttu-id="a2243-535">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="a2243-535">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a2243-536">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/speed/get-started)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="a2243-536">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/speed/get-started) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="a2243-538">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="a2243-538">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
