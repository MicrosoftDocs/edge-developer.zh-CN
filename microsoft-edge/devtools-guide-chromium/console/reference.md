---
title: 控制台参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: bd2a610b48905c6651663d490b9c9f1a0a8c7674
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601781"
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





# <span data-ttu-id="204ea-103">控制台参考</span><span class="sxs-lookup"><span data-stu-id="204ea-103">Console Reference</span></span>   



<span data-ttu-id="204ea-104">此页面是与 Microsoft Edge DevTools 控制台相关的功能的参考。</span><span class="sxs-lookup"><span data-stu-id="204ea-104">This page is a reference of features related to the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="204ea-105">它假设你已经熟悉了如何使用 Console 查看记录的消息和运行 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="204ea-105">It assumes that you are already familiar with using the Console to view logged messages and run JavaScript.</span></span>  <span data-ttu-id="204ea-106">如果不是，请参阅[在控制台中运行 JavaScript 开始][DevToolsConsoleJavascript]，并[开始在控制台中记录消息][DevToolsConsoleLog]。</span><span class="sxs-lookup"><span data-stu-id="204ea-106">If not, see [Get Started With Running JavaScript In The Console][DevToolsConsoleJavascript] and [Get Started With Logging Messages In The Console][DevToolsConsoleLog].</span></span>  

<span data-ttu-id="204ea-107">如果你要查找有关函数的 API 参考，如 `console.log()` 请参阅[控制台 API 参考][DevToolsConsoleApi]。</span><span class="sxs-lookup"><span data-stu-id="204ea-107">If you are looking for the API reference on functions like `console.log()` see [Console API Reference][DevToolsConsoleApi].</span></span>  <span data-ttu-id="204ea-108">如需有关函数的参考， `monitorEvents()` 请参阅[控制台实用工具 API 参考][DevToolsConsoleUtilities]。</span><span class="sxs-lookup"><span data-stu-id="204ea-108">For the reference on functions like `monitorEvents()` see [Console Utilities API Reference][DevToolsConsoleUtilities].</span></span>  

## <span data-ttu-id="204ea-109">打开控制台</span><span class="sxs-lookup"><span data-stu-id="204ea-109">Open the Console</span></span>   

<span data-ttu-id="204ea-110">你可以将控制台作为[面板](#open-the-console-panel)或[抽屉中的选项卡](#open-the-console-tab-in-the-drawer)打开。</span><span class="sxs-lookup"><span data-stu-id="204ea-110">You may open the Console as a [panel](#open-the-console-panel) or as a [tab in the Drawer](#open-the-console-tab-in-the-drawer).</span></span>  

### <span data-ttu-id="204ea-111">打开控制台面板</span><span class="sxs-lookup"><span data-stu-id="204ea-111">Open the Console panel</span></span>   

<span data-ttu-id="204ea-112">按 `Control` + `Shift` + `J` \ （Windows \）或 `Command` + `Option` + `J` \ （macOS \）。</span><span class="sxs-lookup"><span data-stu-id="204ea-112">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span></span>  

> ##### <span data-ttu-id="204ea-113">图 1</span><span class="sxs-lookup"><span data-stu-id="204ea-113">Figure 1</span></span>  
> <span data-ttu-id="204ea-114">控制台面板</span><span class="sxs-lookup"><span data-stu-id="204ea-114">The Console panel</span></span>  
> ![控制台面板][ImageConsolePanel]  

<span data-ttu-id="204ea-116">若要从 "[命令" 菜单][DevToolsCommandMenu]打开 "控制台" 面板，请开始键入， `Console` 然后运行 "**显示控制台**" 命令，其中旁边有一个**面板**标记。</span><span class="sxs-lookup"><span data-stu-id="204ea-116">To open the Console panel from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Panel** badge next to it.</span></span>  

> ##### <span data-ttu-id="204ea-117">图 2</span><span class="sxs-lookup"><span data-stu-id="204ea-117">Figure 2</span></span>  
> <span data-ttu-id="204ea-118">用于显示控制台面板的命令</span><span class="sxs-lookup"><span data-stu-id="204ea-118">The command for showing the Console panel</span></span>  
> ![用于显示控制台面板的命令][ImageCommandShowConsole]  

### <span data-ttu-id="204ea-120">打开抽屉中的 "控制台" 选项卡</span><span class="sxs-lookup"><span data-stu-id="204ea-120">Open the Console tab in the Drawer</span></span>   

<span data-ttu-id="204ea-121">按下 `Escape` 或单击 "**自定义和控制 DevTools** " `...` ，然后选择 "**显示控制台抽屉**"。</span><span class="sxs-lookup"><span data-stu-id="204ea-121">Press `Escape` or click **Customize And Control DevTools** `...` and then select **Show console drawer**.</span></span>  

> ##### <span data-ttu-id="204ea-122">图 3</span><span class="sxs-lookup"><span data-stu-id="204ea-122">Figure 3</span></span>  
> <span data-ttu-id="204ea-123">显示控制台抽屉</span><span class="sxs-lookup"><span data-stu-id="204ea-123">Show console drawer</span></span>  
> ![显示控制台抽屉][ImageShowConsoleDrawer]  

<span data-ttu-id="204ea-125">抽屉将在 DevTools 窗口底部弹出，并打开 "**控制台**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="204ea-125">The Drawer pops up at the bottom of your DevTools window, with the **Console** tab open.</span></span>  

> ##### <span data-ttu-id="204ea-126">图 4</span><span class="sxs-lookup"><span data-stu-id="204ea-126">Figure 4</span></span>  
> <span data-ttu-id="204ea-127">抽屉中的 "控制台" 选项卡</span><span class="sxs-lookup"><span data-stu-id="204ea-127">The Console tab in the Drawer</span></span>  
> ![抽屉中的 "控制台" 选项卡][ImageDrawerConsole]  

<span data-ttu-id="204ea-129">若要从 "[命令" 菜单][DevToolsCommandMenu]打开 "控制台" 选项卡，请开始键入， `Console` 然后运行 "**显示控制台**" 命令，其中旁边有**抽屉**标记。</span><span class="sxs-lookup"><span data-stu-id="204ea-129">To open the Console tab from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Drawer** badge next to it.</span></span>  

> ##### <span data-ttu-id="204ea-130">图 5</span><span class="sxs-lookup"><span data-stu-id="204ea-130">Figure 5</span></span>  
> <span data-ttu-id="204ea-131">用于显示抽屉中的 "控制台" 选项卡的命令</span><span class="sxs-lookup"><span data-stu-id="204ea-131">The command for showing the Console tab in the Drawer</span></span>  
> ![用于显示抽屉中的 "控制台" 选项卡的命令][ImageShowDrawerCommand]  

### <span data-ttu-id="204ea-133">打开控制台设置</span><span class="sxs-lookup"><span data-stu-id="204ea-133">Open Console Settings</span></span>   

<span data-ttu-id="204ea-134">单击 "**控制台设置**" ![ 控制台设置 ][ImageSettingsButtonIcon] 。</span><span class="sxs-lookup"><span data-stu-id="204ea-134">Click **Console Settings** ![Console Settings][ImageSettingsButtonIcon].</span></span>  

> ##### <span data-ttu-id="204ea-135">图 6</span><span class="sxs-lookup"><span data-stu-id="204ea-135">Figure 6</span></span>  
> <span data-ttu-id="204ea-136">控制台设置</span><span class="sxs-lookup"><span data-stu-id="204ea-136">Console Settings</span></span>  
> ![控制台设置][ImageConsoleSettings]  

<span data-ttu-id="204ea-138">下面的链接对每个设置进行了说明：</span><span class="sxs-lookup"><span data-stu-id="204ea-138">The links below explain each setting:</span></span>  

*   [**<span data-ttu-id="204ea-139">隐藏网络</span><span class="sxs-lookup"><span data-stu-id="204ea-139">Hide Network</span></span>**](#hide-network-messages)  
*   [**<span data-ttu-id="204ea-140">保留日志</span><span class="sxs-lookup"><span data-stu-id="204ea-140">Preserve Log</span></span>**](#persist-messages-across-page-loads)  
*   [**<span data-ttu-id="204ea-141">仅限所选上下文</span><span class="sxs-lookup"><span data-stu-id="204ea-141">Selected Context Only</span></span>**](#filter-out-messages-from-different-contexts)  
*   [**<span data-ttu-id="204ea-142">分组相似</span><span class="sxs-lookup"><span data-stu-id="204ea-142">Group Similar</span></span>**](#disable-message-grouping)  
*   [**<span data-ttu-id="204ea-143">日志 XmlHttpRequests</span><span class="sxs-lookup"><span data-stu-id="204ea-143">Log XmlHttpRequests</span></span>**](#log-xhr-and-fetch-requests)  
*   [**<span data-ttu-id="204ea-144">积极评估</span><span class="sxs-lookup"><span data-stu-id="204ea-144">Eager Evaluation</span></span>**](#disable-eager-evaluation)  
*   [**<span data-ttu-id="204ea-145">历史记录中的自动完成</span><span class="sxs-lookup"><span data-stu-id="204ea-145">Autocomplete From History</span></span>**](#disable-autocomplete-from-history)  

### <span data-ttu-id="204ea-146">打开控制台边栏</span><span class="sxs-lookup"><span data-stu-id="204ea-146">Open the Console Sidebar</span></span>   

<span data-ttu-id="204ea-147">单击 "**显示控制台边栏** ![ 显示控制台边栏 ][ImageShowConsoleSidebarIcon] " 以显示边栏，这对于筛选很有用。</span><span class="sxs-lookup"><span data-stu-id="204ea-147">Click **Show Console Sidebar** ![Show Console Sidebar][ImageShowConsoleSidebarIcon] to show the Sidebar, which is useful for filtering.</span></span>  

> ##### <span data-ttu-id="204ea-148">图 7</span><span class="sxs-lookup"><span data-stu-id="204ea-148">Figure 7</span></span>  
> <span data-ttu-id="204ea-149">控制台边栏</span><span class="sxs-lookup"><span data-stu-id="204ea-149">Console Sidebar</span></span>  
> ![控制台边栏][ImageConsoleSidebar]  

## <span data-ttu-id="204ea-151">查看邮件</span><span class="sxs-lookup"><span data-stu-id="204ea-151">View messages</span></span>   

<span data-ttu-id="204ea-152">本部分包含更改如何在控制台中显示消息的功能。</span><span class="sxs-lookup"><span data-stu-id="204ea-152">This section contains features that change how messages are presented in the Console.</span></span>  <span data-ttu-id="204ea-153">请参阅查看动手演练的[消息][DevToolsConsoleViewMessages]。</span><span class="sxs-lookup"><span data-stu-id="204ea-153">See [View messages][DevToolsConsoleViewMessages] for a hands-on walkthrough.</span></span>  

### <span data-ttu-id="204ea-154">禁用邮件分组</span><span class="sxs-lookup"><span data-stu-id="204ea-154">Disable message grouping</span></span>   

<span data-ttu-id="204ea-155">[打开 "控制台设置](#open-console-settings)" 并禁用 "**分组类似**"，禁用控制台的默认消息分组行为。</span><span class="sxs-lookup"><span data-stu-id="204ea-155">[Open Console Settings](#open-console-settings) and disable **Group similar** to disable the default message grouping behavior of the Console.</span></span>  <span data-ttu-id="204ea-156">有关示例，请参阅[记录 XHR 和获取请求](#log-xhr-and-fetch-requests)。</span><span class="sxs-lookup"><span data-stu-id="204ea-156">See [Log XHR and Fetch requests](#log-xhr-and-fetch-requests) for an example.</span></span>  

### <span data-ttu-id="204ea-157">记录 XHR 和回迁请求</span><span class="sxs-lookup"><span data-stu-id="204ea-157">Log XHR and Fetch requests</span></span>   

<span data-ttu-id="204ea-158">[打开控制台设置](#open-console-settings)并启用**日志 XMLHttpRequests** ，以便在 `XMLHttpRequest` 发生时将所有和请求记录到 `Fetch` 控制台。</span><span class="sxs-lookup"><span data-stu-id="204ea-158">[Open Console Settings](#open-console-settings) and enable **Log XMLHttpRequests** to log all `XMLHttpRequest` and `Fetch` requests to the Console as they happen.</span></span>  

> ##### <span data-ttu-id="204ea-159">图 8</span><span class="sxs-lookup"><span data-stu-id="204ea-159">Figure 8</span></span>  
> <span data-ttu-id="204ea-160">日志记录 `XMLHttpRequest` 和 `Fetch` 请求</span><span class="sxs-lookup"><span data-stu-id="204ea-160">Logging `XMLHttpRequest` and `Fetch` requests</span></span>  
> ![记录 XMLHttpRequest 和获取请求][ImageXhrGrouped]  

<span data-ttu-id="204ea-162">[图 8](#figure-8)中的顶部消息显示了控制台的默认分组行为。</span><span class="sxs-lookup"><span data-stu-id="204ea-162">The top message in [Figure 8](#figure-8) shows the default grouping behavior of the Console.</span></span>  <!--  [Figure 9](#figure-9) shows how the same log looks after [disabling message grouping](#disable-message-grouping).  -->  

<!--

> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> ![How the logged XMLHttpRequest and Fetch requests look after ungrouping][ImageXhrUngrouped]  

-->

<!--todo: add example for ungrouping console items  -->  

### <span data-ttu-id="204ea-163">跨页面加载保留消息</span><span class="sxs-lookup"><span data-stu-id="204ea-163">Persist messages across page loads</span></span>   

<span data-ttu-id="204ea-164">默认情况下，无论何时加载新页面，控制台都会被清除。</span><span class="sxs-lookup"><span data-stu-id="204ea-164">By default the Console clears whenever you load a new page.</span></span>  <span data-ttu-id="204ea-165">若要在每个页面加载期间保持消息，请[打开控制台设置](#open-console-settings)，然后启用 "**保留日志**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="204ea-165">To persist messages across page loads, [Open Console Settings](#open-console-settings) and then enable the **Preserve Log** checkbox.</span></span>  

### <span data-ttu-id="204ea-166">隐藏网络消息</span><span class="sxs-lookup"><span data-stu-id="204ea-166">Hide network messages</span></span>   

<span data-ttu-id="204ea-167">默认情况下，浏览器将网络消息记录到**控制台**。</span><span class="sxs-lookup"><span data-stu-id="204ea-167">By default the browser logs network messages to the **Console**.</span></span>  <span data-ttu-id="204ea-168">例如，[图 9](#figure-9)中的所选消息表示状态代码 `429` 。</span><span class="sxs-lookup"><span data-stu-id="204ea-168">For example, the selected message in [Figure 9](#figure-9) represents a status code of `429`.</span></span>  

> ##### <span data-ttu-id="204ea-169">图 9</span><span class="sxs-lookup"><span data-stu-id="204ea-169">Figure 9</span></span>  
> <span data-ttu-id="204ea-170">控制台中的429消息</span><span class="sxs-lookup"><span data-stu-id="204ea-170">A 429 message in the Console</span></span>  
> <span data-ttu-id="204ea-171">![控制台中的429消息][Image429Message]</span><span class="sxs-lookup"><span data-stu-id="204ea-171">![A 429 message in the Console][Image429Message]</span></span>  

<span data-ttu-id="204ea-172">要隐藏网络消息，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="204ea-172">To hide network messages:</span></span>  

1.  <span data-ttu-id="204ea-173">[打开控制台设置](#open-console-settings)。</span><span class="sxs-lookup"><span data-stu-id="204ea-173">[Open Console Settings](#open-console-settings).</span></span>  
1.  <span data-ttu-id="204ea-174">启用 "**隐藏网络**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="204ea-174">Enable the **Hide Network** checkbox.</span></span>  

## <span data-ttu-id="204ea-175">筛选邮件</span><span class="sxs-lookup"><span data-stu-id="204ea-175">Filter messages</span></span>   

<span data-ttu-id="204ea-176">可通过多种方式在控制台中筛选出消息。</span><span class="sxs-lookup"><span data-stu-id="204ea-176">There are many ways to filter out messages in the Console.</span></span>  

### <span data-ttu-id="204ea-177">筛选出浏览器消息</span><span class="sxs-lookup"><span data-stu-id="204ea-177">Filter out browser messages</span></span>   

<span data-ttu-id="204ea-178">[打开控制台侧栏](#open-the-console-sidebar)，然后单击 "**用户消息**"，仅显示来自页面 JavaScript 的消息。</span><span class="sxs-lookup"><span data-stu-id="204ea-178">[Open the Console Sidebar](#open-the-console-sidebar) and click **User Messages** to only show messages that came from the JavaScript of the page.</span></span>  

> ##### <span data-ttu-id="204ea-179">图 10</span><span class="sxs-lookup"><span data-stu-id="204ea-179">Figure 10</span></span>  
> <span data-ttu-id="204ea-180">查看用户消息</span><span class="sxs-lookup"><span data-stu-id="204ea-180">Viewing user messages</span></span>  
> <span data-ttu-id="204ea-181">![查看用户消息][ImageUserMessages]</span><span class="sxs-lookup"><span data-stu-id="204ea-181">![Viewing user messages][ImageUserMessages]</span></span>  

### <span data-ttu-id="204ea-182">按日志级别筛选</span><span class="sxs-lookup"><span data-stu-id="204ea-182">Filter by log level</span></span>   

<span data-ttu-id="204ea-183">DevTools 为每个 `console.*` 方法分配一个严重级别。</span><span class="sxs-lookup"><span data-stu-id="204ea-183">DevTools assigns each `console.*` method a severity level.</span></span>  <span data-ttu-id="204ea-184">有4个级别： `Verbose` 、 `Info` 、 `Warning` 和 `Error` 。</span><span class="sxs-lookup"><span data-stu-id="204ea-184">There are 4 levels: `Verbose`, `Info`, `Warning`, and `Error`.</span></span>  <span data-ttu-id="204ea-185">例如，位于 `console.log()` `Info` 组中，而位于 `console.error()` 组中 `Error` 。</span><span class="sxs-lookup"><span data-stu-id="204ea-185">For example, `console.log()` is in the `Info` group, whereas `console.error()` is in the `Error` group.</span></span>  <span data-ttu-id="204ea-186">[控制台 API 参考][DevToolsConsoleApi]描述每个适用方法的严重级别。</span><span class="sxs-lookup"><span data-stu-id="204ea-186">The [Console API Reference][DevToolsConsoleApi] describes the severity level of each applicable method.</span></span>  <span data-ttu-id="204ea-187">浏览器记录到控制台的每条消息也具有严重级别。</span><span class="sxs-lookup"><span data-stu-id="204ea-187">Every message that the browser logs to the Console has a severity level too.</span></span>  <span data-ttu-id="204ea-188">您可以隐藏不感兴趣的任何级别的邮件。</span><span class="sxs-lookup"><span data-stu-id="204ea-188">You may hide any level of messages that you are not interested in.</span></span>  <span data-ttu-id="204ea-189">例如，如果只对邮件感兴趣 `Error` ，则可以隐藏其他3个组。</span><span class="sxs-lookup"><span data-stu-id="204ea-189">For example, if you are only interested in `Error` messages, you may hide the other 3 groups.</span></span>  

<span data-ttu-id="204ea-190">单击 "**日志级别**" 下拉列表以启用或禁用 `Verbose` 、 `Info` 或 "消息" `Warning` `Error` 。</span><span class="sxs-lookup"><span data-stu-id="204ea-190">Click the **Log Levels** dropdown to enable or disable `Verbose`, `Info`, `Warning` or `Error` messages.</span></span>  

> ##### <span data-ttu-id="204ea-191">图 11</span><span class="sxs-lookup"><span data-stu-id="204ea-191">Figure 11</span></span>  
> <span data-ttu-id="204ea-192">**日志级别**下拉列表</span><span class="sxs-lookup"><span data-stu-id="204ea-192">The **Log Levels** dropdown</span></span>  
> <span data-ttu-id="204ea-193">![日志级别下拉列表][ImageLogLevels]</span><span class="sxs-lookup"><span data-stu-id="204ea-193">![The Log Levels dropdown][ImageLogLevels]</span></span>  

<span data-ttu-id="204ea-194">您还可以按日志级别进行筛选，方法是[打开控制台边栏](#open-the-console-sidebar)，然后单击 "**错误**"、"**警告**"、"信息" 或 "**详细\*\*\*\*信息**"。</span><span class="sxs-lookup"><span data-stu-id="204ea-194">You may also filter by log level by [opening the Console Sidebar](#open-the-console-sidebar) and then clicking **Errors**, **Warnings**, **Info**, or **Verbose**.</span></span>  

> ##### <span data-ttu-id="204ea-195">图 12</span><span class="sxs-lookup"><span data-stu-id="204ea-195">Figure 12</span></span>  
> <span data-ttu-id="204ea-196">使用边栏查看警告</span><span class="sxs-lookup"><span data-stu-id="204ea-196">Using the Sidebar to view warnings</span></span>  
> <span data-ttu-id="204ea-197">![使用边栏查看警告][ImageSidebarWarnings]</span><span class="sxs-lookup"><span data-stu-id="204ea-197">![Using the Sidebar to view warnings][ImageSidebarWarnings]</span></span>  

### <span data-ttu-id="204ea-198">按 URL 筛选邮件</span><span class="sxs-lookup"><span data-stu-id="204ea-198">Filter messages by URL</span></span>   

<span data-ttu-id="204ea-199">键入 `url:` 后跟 url，仅查看来自该 url 的邮件。</span><span class="sxs-lookup"><span data-stu-id="204ea-199">Type `url:` followed by a URL to only view messages that came from that URL.</span></span>  <span data-ttu-id="204ea-200">键入 DevTools 后，将 `url:` 显示所有相关的 url。</span><span class="sxs-lookup"><span data-stu-id="204ea-200">After you type `url:` DevTools shows all relevant URLs.</span></span>  <span data-ttu-id="204ea-201">域也有效。</span><span class="sxs-lookup"><span data-stu-id="204ea-201">Domains also work.</span></span>  <span data-ttu-id="204ea-202">例如，如果 `https://example.com/a.js` 和 `https://example.com/b.js` 正在记录邮件， `url:https://example.com` 则可让你关注来自这两个脚本的消息。</span><span class="sxs-lookup"><span data-stu-id="204ea-202">For example, if `https://example.com/a.js` and `https://example.com/b.js` are logging messages, `url:https://example.com` enables you to focus on the messages from these 2 scripts.</span></span>  

> ##### <span data-ttu-id="204ea-203">图 13</span><span class="sxs-lookup"><span data-stu-id="204ea-203">Figure 13</span></span>  
> <span data-ttu-id="204ea-204">URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="204ea-204">A URL filter</span></span>  
> <span data-ttu-id="204ea-205">![URL 筛选器][ImageUrlFilter]</span><span class="sxs-lookup"><span data-stu-id="204ea-205">![A URL filter][ImageUrlFilter]</span></span>  

<span data-ttu-id="204ea-206">键入 `-url:` 以隐藏来自该 URL 的邮件。</span><span class="sxs-lookup"><span data-stu-id="204ea-206">Type `-url:` to hide messages from that URL.</span></span>  <span data-ttu-id="204ea-207">这称为负 URL 筛选器。</span><span class="sxs-lookup"><span data-stu-id="204ea-207">This is called a negative URL filter.</span></span>  

> ##### <span data-ttu-id="204ea-208">图 14</span><span class="sxs-lookup"><span data-stu-id="204ea-208">Figure 14</span></span>  
> <span data-ttu-id="204ea-209">用于隐藏与 URL 匹配的所有邮件的负 URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="204ea-209">A negative URL filter that hides all messages matching the URL</span></span> `https://b.wal.co`  
> <span data-ttu-id="204ea-210">![将隐藏与 URL 匹配的所有邮件的负 URL 筛选器 https://b.wal.co ][ImageNegativeUrlFilter1]</span><span class="sxs-lookup"><span data-stu-id="204ea-210">![A negative URL filter that hides all messages matching the URL https://b.wal.co][ImageNegativeUrlFilter1]</span></span>  

<span data-ttu-id="204ea-211">您还可以通过[打开控制台边栏](#open-the-console-sidebar)，展开 "**用户消息**" 部分，然后单击包含要对其进行焦点的邮件的脚本的 URL，显示来自单个 URL 的邮件。</span><span class="sxs-lookup"><span data-stu-id="204ea-211">You may also show messages from a single URL by [opening the Console Sidebar](#open-the-console-sidebar), expanding the **User Messages** section, and then clicking the URL of the script containing the messages on which you want to focus.</span></span>  

> ##### <span data-ttu-id="204ea-212">图 15</span><span class="sxs-lookup"><span data-stu-id="204ea-212">Figure 15</span></span>  
> <span data-ttu-id="204ea-213">查看来自的邮件</span><span class="sxs-lookup"><span data-stu-id="204ea-213">Viewing the messages that came from</span></span> `wp-ad.min.js`  
> <span data-ttu-id="204ea-214">![查看来自 wp-ad 的消息][ImageNegativeUrlFilter2]</span><span class="sxs-lookup"><span data-stu-id="204ea-214">![Viewing the messages that came from wp-ad.min.js][ImageNegativeUrlFilter2]</span></span>  

### <span data-ttu-id="204ea-215">筛选出来自不同上下文的消息</span><span class="sxs-lookup"><span data-stu-id="204ea-215">Filter out messages from different contexts</span></span>   

<span data-ttu-id="204ea-216">假设您的页面上有广告 \ （广告 \）。</span><span class="sxs-lookup"><span data-stu-id="204ea-216">Suppose that you have an advertisement \(ad\) on your page.</span></span>  <span data-ttu-id="204ea-217">广告嵌入在中 `<iframe>` ，并且会在您的控制台中生成大量消息。</span><span class="sxs-lookup"><span data-stu-id="204ea-217">The ad is embedded in an `<iframe>` and is generating a lot of messages in your Console.</span></span>  <span data-ttu-id="204ea-218">由于广告在不同的[JavaScript 上下文](#select-javascript-context)中运行，因此隐藏消息的一种方法是[打开控制台设置](#open-console-settings)并启用 "**仅限选定的上下文**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="204ea-218">Because the ad is running in a different [JavaScript context](#select-javascript-context), one way to hide the messages is to [open Console Settings](#open-console-settings) and enable the **Selected Context Only** checkbox.</span></span>  

### <span data-ttu-id="204ea-219">筛选出与正则表达式模式不匹配的消息</span><span class="sxs-lookup"><span data-stu-id="204ea-219">Filter out messages that do not match a regular expression pattern</span></span>   

<span data-ttu-id="204ea-220">`/[gm][ta][mi]/`在 "**筛选器**" 文本框中键入正则表达式，以筛选出与该模式不匹配的任何消息。</span><span class="sxs-lookup"><span data-stu-id="204ea-220">Type a regular expression such as `/[gm][ta][mi]/` in the **Filter** text box to filter out any messages that do not match that pattern.</span></span>  <span data-ttu-id="204ea-221">DevTools 检查是否在消息文本或导致消息被记录的脚本中找到该模式。</span><span class="sxs-lookup"><span data-stu-id="204ea-221">DevTools checks if the pattern is found in the message text or the script that caused the message to be logged.</span></span>  

> ##### <span data-ttu-id="204ea-222">图 16</span><span class="sxs-lookup"><span data-stu-id="204ea-222">Figure 16</span></span>  
> <span data-ttu-id="204ea-223">筛选出不匹配的任何邮件</span><span class="sxs-lookup"><span data-stu-id="204ea-223">Filtering out any messages that do not match</span></span> `/[gm][ta][mi]/`  
> <span data-ttu-id="204ea-224">![筛选出与 regex 表达式不匹配的任何消息][ImageRegExFilter]</span><span class="sxs-lookup"><span data-stu-id="204ea-224">![Filtering out any messages that do not match regex expression][ImageRegExFilter]</span></span>  

## <span data-ttu-id="204ea-225">运行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="204ea-225">Run JavaScript</span></span>   

<span data-ttu-id="204ea-226">本部分包含与在控制台中运行 JavaScript 相关的功能。</span><span class="sxs-lookup"><span data-stu-id="204ea-226">This section contains features related to running JavaScript in the Console.</span></span>  <span data-ttu-id="204ea-227">请参阅运行参与练习的[JavaScript][DevToolsConsoleOverviewJavascript] 。</span><span class="sxs-lookup"><span data-stu-id="204ea-227">See [Run JavaScript][DevToolsConsoleOverviewJavascript] for a hands-on walkthrough.</span></span>  

### <span data-ttu-id="204ea-228">重新运行历史记录中的表达式</span><span class="sxs-lookup"><span data-stu-id="204ea-228">Re-run expressions from history</span></span>   

<span data-ttu-id="204ea-229">按下 `Up Arrow` 键，循环浏览你之前在控制台中运行的 JavaScript 表达式的历史记录。</span><span class="sxs-lookup"><span data-stu-id="204ea-229">Press the `Up Arrow` key to cycle through the history of JavaScript expressions that you ran earlier in the Console.</span></span>  <span data-ttu-id="204ea-230">按键 `Enter` 再次运行该表达式。</span><span class="sxs-lookup"><span data-stu-id="204ea-230">Press `Enter` to run that expression again.</span></span>  

### <span data-ttu-id="204ea-231">使用实时表达式实时监视表达式的值</span><span class="sxs-lookup"><span data-stu-id="204ea-231">Watch the value of an expression in real-time with Live Expressions</span></span>   

<span data-ttu-id="204ea-232">如果您发现自己在控制台中重复键入相同的 JavaScript 表达式，您可能会发现创建**实时表达式**变得更容易。</span><span class="sxs-lookup"><span data-stu-id="204ea-232">If you find yourself typing the same JavaScript expression in the Console repeatedly, you may find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="204ea-233">使用**实时表达式**，您只需要键入一个表达式，然后将其固定到您的控制台顶部。</span><span class="sxs-lookup"><span data-stu-id="204ea-233">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span></span>  <span data-ttu-id="204ea-234">表达式的值几乎实时更新。</span><span class="sxs-lookup"><span data-stu-id="204ea-234">The value of the expression updates in near real-time.</span></span>  <span data-ttu-id="204ea-235">请参阅[实时在实时表达式中观看 JavaScript 表达式值][DevToolsConsoleLiveExpressions]。</span><span class="sxs-lookup"><span data-stu-id="204ea-235">See [Watch JavaScript Expression Values In Real-Time With Live Expressions][DevToolsConsoleLiveExpressions].</span></span>  

### <span data-ttu-id="204ea-236">禁用热情评估</span><span class="sxs-lookup"><span data-stu-id="204ea-236">Disable Eager Evaluation</span></span>   

<span data-ttu-id="204ea-237">当您在控制台中键入 JavaScript 表达式时，**预先计算**会显示该表达式的返回值的预览。</span><span class="sxs-lookup"><span data-stu-id="204ea-237">As you type JavaScript expressions in the Console, **Eager Evaluation** shows a preview of the return value for that expression.</span></span>  <span data-ttu-id="204ea-238">[打开 "控制台设置](#open-console-settings)" 并禁用 "**预先评估**" 复选框以关闭返回值预览。</span><span class="sxs-lookup"><span data-stu-id="204ea-238">[Open Console Settings](#open-console-settings) and disable the **Eager Evaluation** checkbox to turn off the return value previews.</span></span>  

### <span data-ttu-id="204ea-239">禁用历史记录中的自动完成</span><span class="sxs-lookup"><span data-stu-id="204ea-239">Disable autocomplete from history</span></span>   

<span data-ttu-id="204ea-240">当您键入表达式时，控制台的 "自动完成" 弹出窗口将显示您之前运行的表达式。</span><span class="sxs-lookup"><span data-stu-id="204ea-240">As you type out an expression, the autocomplete popup window for the Console shows expressions that you ran earlier.</span></span>  <span data-ttu-id="204ea-241">这些表达式前置 `>` 字符。</span><span class="sxs-lookup"><span data-stu-id="204ea-241">These expressions are prepended with the `>` character.</span></span>  <span data-ttu-id="204ea-242">[打开 "控制台设置](#open-console-settings)" 并禁用 "**从历史记录自动完成**" 复选框以停止显示历史记录中的表达式。</span><span class="sxs-lookup"><span data-stu-id="204ea-242">[Open Console Settings](#open-console-settings) and disable the **Autocomplete From History** checkbox to stop showing expressions from your history.</span></span>  

> [!NOTE]
> <span data-ttu-id="204ea-243">在[图 17](#figure-17)中 `document.querySelector('a')` ， `document.querySelector('img')` 是之前计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="204ea-243">In [Figure 17](#figure-17), `document.querySelector('a')` and `document.querySelector('img')` are expressions that were evaluated earlier.</span></span>  

> ##### <span data-ttu-id="204ea-244">图 17</span><span class="sxs-lookup"><span data-stu-id="204ea-244">Figure 17</span></span>  
> <span data-ttu-id="204ea-245">显示历史记录中的表达式的自动完成弹出窗口</span><span class="sxs-lookup"><span data-stu-id="204ea-245">The autocomplete popup showing expressions from history</span></span>  
> <span data-ttu-id="204ea-246">![显示历史记录中的表达式的 "自动完成" 弹出窗口][ImageHistoryAutocomplete]</span><span class="sxs-lookup"><span data-stu-id="204ea-246">![The autocomplete popup showing expressions from history][ImageHistoryAutocomplete]</span></span>  

### <span data-ttu-id="204ea-247">选择 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="204ea-247">Select JavaScript context</span></span>   

<span data-ttu-id="204ea-248">默认情况下， **JavaScript 上下文**下拉列表设置为 "**页首**"，这表示主文档的[浏览上下文][MDNBrowsingContext]。</span><span class="sxs-lookup"><span data-stu-id="204ea-248">By default the **JavaScript Context** dropdown is set to **top**, which represents the [browsing context][MDNBrowsingContext] of the main document.</span></span>  

> ##### <span data-ttu-id="204ea-249">图18</span><span class="sxs-lookup"><span data-stu-id="204ea-249">Figure 18</span></span>  
> <span data-ttu-id="204ea-250">**JavaScript 上下文**下拉列表</span><span class="sxs-lookup"><span data-stu-id="204ea-250">The **JavaScript Context** dropdown</span></span>  
> <span data-ttu-id="204ea-251">![JavaScript 上下文下拉列表][ImageJavascriptContext]</span><span class="sxs-lookup"><span data-stu-id="204ea-251">![The JavaScript Context dropdown][ImageJavascriptContext]</span></span>  

<span data-ttu-id="204ea-252">假设您的页面上有一个嵌入的广告 `<iframe>` 。</span><span class="sxs-lookup"><span data-stu-id="204ea-252">Suppose you have an ad on your page embedded in an `<iframe>`.</span></span>  <span data-ttu-id="204ea-253">你希望运行 JavaScript，以便调整广告的 DOM。</span><span class="sxs-lookup"><span data-stu-id="204ea-253">You want to run JavaScript in order to tweak the DOM of the ad.</span></span>  <span data-ttu-id="204ea-254">应首先从**JavaScript 上下文**下拉列表中选择广告的浏览上下文。</span><span class="sxs-lookup"><span data-stu-id="204ea-254">You should first select the browsing context of the ad from the **JavaScript Context** dropdown.</span></span>  

> ##### <span data-ttu-id="204ea-255">图19</span><span class="sxs-lookup"><span data-stu-id="204ea-255">Figure 19</span></span>  
> <span data-ttu-id="204ea-256">选择不同的 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="204ea-256">Selecting a different JavaScript context</span></span>  
> <span data-ttu-id="204ea-257">![选择不同的 JavaScript 上下文][ImageSelectContext]</span><span class="sxs-lookup"><span data-stu-id="204ea-257">![Selecting a different JavaScript context][ImageSelectContext]</span></span>  

## <span data-ttu-id="204ea-258">清除控制台</span><span class="sxs-lookup"><span data-stu-id="204ea-258">Clear the Console</span></span>   

<span data-ttu-id="204ea-259">你可以使用以下任何工作流来清除控制台：</span><span class="sxs-lookup"><span data-stu-id="204ea-259">You may use any of the following workflows to clear the Console:</span></span>  

*   <span data-ttu-id="204ea-260">单击 "**清除控制台** ![ 清除控制台" ][ImageClearConsoleIcon] 。</span><span class="sxs-lookup"><span data-stu-id="204ea-260">Click **Clear Console** ![Clear Console][ImageClearConsoleIcon].</span></span>  
*   <span data-ttu-id="204ea-261">右键单击一条消息，然后选择 "**清除控制台**"。</span><span class="sxs-lookup"><span data-stu-id="204ea-261">Right-click a message and then select **Clear Console**.</span></span>  
*   <span data-ttu-id="204ea-262">`clear()`在控制台中键入，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="204ea-262">Type `clear()` in the Console and then press `Enter`.</span></span>  
*   <span data-ttu-id="204ea-263">`console.clear()`从你的网页的 JavaScript 调用。</span><span class="sxs-lookup"><span data-stu-id="204ea-263">Call `console.clear()` from the JavaScript for your webpage.</span></span>  
*   <span data-ttu-id="204ea-264">`Control` + `L` 控制台处于焦点状态时按键。</span><span class="sxs-lookup"><span data-stu-id="204ea-264">Press `Control`+`L` while the Console is in focus.</span></span>  

 



<!-- image links -->  

[ImageClearConsoleIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-console-button-icon.msft.png  
[ImageSettingsButtonIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-button-icon.msft.png  
[ImageShowConsoleSidebarIcon]: /microsoft-edge/devtools-guide-chromium/media/show-console-sidebar-icon.msft.png  

[ImageConsolePanel]: /microsoft-edge/devtools-guide-chromium/media/console-hello-console.msft.png "图1：控制台面板"  
[ImageCommandShowConsole]: /microsoft-edge/devtools-guide-chromium/media/console-command-menu-show-console.msft.png "图2：显示控制台面板的命令"  
[ImageShowConsoleDrawer]: /microsoft-edge/devtools-guide-chromium/media/console-elements-customize-control-devtools-show-console-drawer.msft.png "图3：显示控制台抽屉"  
[ImageDrawerConsole]: /microsoft-edge/devtools-guide-chromium/media/console-elements-console-drawer-hello-world.msft.png "图4：抽屉中的 "控制台" 选项卡"  
[ImageShowDrawerCommand]: /microsoft-edge/devtools-guide-chromium/media/console-command-menu-show-console.msft.png "图5：显示抽屉中的 "控制台" 选项卡的命令"  
[ImageConsoleSettings]: /microsoft-edge/devtools-guide-chromium/media/console-settings-group-similar-empty.msft.png "图6：控制台设置"  
[ImageConsoleSidebar]: /microsoft-edge/devtools-guide-chromium/media/console-sidebar-drawer-empty.msft.png "图7：控制台边栏"  
[ImageXhrGrouped]: /microsoft-edge/devtools-guide-chromium/media/console-xhr-fetch.msft.png "图8：记录 XMLHttpRequest 和获取请求"  
<!--[ImageXhrUngrouped]: /microsoft-edge/devtools-guide-chromium/media/console-xhr-fetch-all.msft.png "Figure old 9: How the logged XMLHttpRequest and Fetch requests look after ungrouping"  -->  
<span data-ttu-id="204ea-273">[Image429Message]：/microsoft-edge/devtools-guide-chromium/media/console-show-network.msft.png "图9：控制台中的429消息"</span><span class="sxs-lookup"><span data-stu-id="204ea-273">[Image429Message]: /microsoft-edge/devtools-guide-chromium/media/console-show-network.msft.png "Figure 9: A 429 message in the Console"</span></span>  
<span data-ttu-id="204ea-274">[ImageUserMessages]：/microsoft-edge/devtools-guide-chromium/media/console-sidebar-drawer-user-messages.msft.png "图10：查看用户消息"</span><span class="sxs-lookup"><span data-stu-id="204ea-274">[ImageUserMessages]: /microsoft-edge/devtools-guide-chromium/media/console-sidebar-drawer-user-messages.msft.png "Figure 10: Viewing user messages"</span></span>  
<span data-ttu-id="204ea-275">[ImageLogLevels]：/microsoft-edge/devtools-guide-chromium/media/console-log-level-default-levels.msft.png "图11：日志级别下拉列表"</span><span class="sxs-lookup"><span data-stu-id="204ea-275">[ImageLogLevels]: /microsoft-edge/devtools-guide-chromium/media/console-log-level-default-levels.msft.png "Figure 11: The Log Levels dropdown"</span></span>  
<span data-ttu-id="204ea-276">[ImageSidebarWarnings]：/microsoft-edge/devtools-guide-chromium/media/console-sidebar-warnings.msft.png "图12：使用边栏查看警告"</span><span class="sxs-lookup"><span data-stu-id="204ea-276">[ImageSidebarWarnings]: /microsoft-edge/devtools-guide-chromium/media/console-sidebar-warnings.msft.png "Figure 12: Using the Sidebar to view warnings"</span></span>  
<span data-ttu-id="204ea-277">[ImageUrlFilter]：/microsoft-edge/devtools-guide-chromium/media/console-filter-text.msft.png "图13： URL 筛选器"</span><span class="sxs-lookup"><span data-stu-id="204ea-277">[ImageUrlFilter]: /microsoft-edge/devtools-guide-chromium/media/console-filter-text.msft.png "Figure 13: A URL filter"</span></span>  
<span data-ttu-id="204ea-278">[ImageNegativeUrlFilter1]：/microsoft-edge/devtools-guide-chromium/media/console-negative-filter-text.msft.png "图14：用于隐藏与 URL 匹配的所有邮件的负 URL 筛选器 https://b.wal.co "</span><span class="sxs-lookup"><span data-stu-id="204ea-278">[ImageNegativeUrlFilter1]: /microsoft-edge/devtools-guide-chromium/media/console-negative-filter-text.msft.png "Figure 14: A negative URL filter that hides all messages matching the URL https://b.wal.co"</span></span>  
<span data-ttu-id="204ea-279">[ImageNegativeUrlFilter2]：/microsoft-edge/devtools-guide-chromium/media/console-filter-text-specified.msft.png "图15：查看来自 wp-ad" 的邮件</span><span class="sxs-lookup"><span data-stu-id="204ea-279">[ImageNegativeUrlFilter2]: /microsoft-edge/devtools-guide-chromium/media/console-filter-text-specified.msft.png "Figure 15: Viewing the messages that came from wp-ad.min.js"</span></span>  
<span data-ttu-id="204ea-280">[ImageRegExFilter]：/microsoft-edge/devtools-guide-chromium/media/console-filter-regex.msft.png "图16：筛选出与 regex 表达式不匹配的任何消息"</span><span class="sxs-lookup"><span data-stu-id="204ea-280">[ImageRegExFilter]: /microsoft-edge/devtools-guide-chromium/media/console-filter-regex.msft.png "Figure 16: Filtering out any messages that do not match regex expression"</span></span>  
<span data-ttu-id="204ea-281">[ImageHistoryAutocomplete]：/microsoft-edge/devtools-guide-chromium/media/console-filter-text-autofilter-history.msft.png "图17：显示历史记录中的表达式的自动完成弹出窗口"</span><span class="sxs-lookup"><span data-stu-id="204ea-281">[ImageHistoryAutocomplete]: /microsoft-edge/devtools-guide-chromium/media/console-filter-text-autofilter-history.msft.png "Figure 17: The autocomplete popup showing expressions from history"</span></span>  
<span data-ttu-id="204ea-282">[ImageJavascriptContext]：/microsoft-edge/devtools-guide-chromium/media/console-dom-level-top.msft.png "图18： JavaScript 上下文下拉列表"</span><span class="sxs-lookup"><span data-stu-id="204ea-282">[ImageJavascriptContext]: /microsoft-edge/devtools-guide-chromium/media/console-dom-level-top.msft.png "Figure 18: The JavaScript Context dropdown"</span></span>  
<span data-ttu-id="204ea-283">[ImageSelectContext]：/microsoft-edge/devtools-guide-chromium/media/console-dom-level-multiple.msft.png "图19：选择不同的 JavaScript 上下文"</span><span class="sxs-lookup"><span data-stu-id="204ea-283">[ImageSelectContext]: /microsoft-edge/devtools-guide-chromium/media/console-dom-level-multiple.msft.png "Figure 19: Selecting a different JavaScript context"</span></span>  

<!-- links -->  

[DevToolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "通过 Microsoft Edge DevTools 命令菜单运行命令"  
[DevToolsConsoleViewMessages]: /microsoft-edge/devtools-guide-chromium/console/index#viewing-logged-messages "查看已记录的消息-控制台概述"  
[DevToolsConsoleApi]: /microsoft-edge/devtools-guide-chromium/console/api "控制台 API 参考"  
[DevToolsConsoleOverviewJavascript]: /microsoft-edge/devtools-guide-chromium/console/index#running-javascript "运行 JavaScript-控制台概述"  
[DevToolsConsoleJavascript]: /microsoft-edge/devtools-guide-chromium/console/javascript "开始在控制台中运行 JavaScript"  
[DevToolsConsoleLiveExpressions]: /microsoft-edge/devtools-guide-chromium/console/live-expressions "实时监视 JavaScript 表达式值和实时表达式"  
[DevToolsConsoleLog]: /microsoft-edge/devtools-guide-chromium/console/log "在控制台中记录消息入门"  
[DevToolsConsoleUtilities]: /microsoft-edge/devtools-guide-chromium/console/utilities "控制台实用工具 API 参考"  

[MDNBrowsingContext]: https://developer.mozilla.org/docs/Glossary/Browsing_context "浏览上下文 |MDN"  

> [!NOTE]
> <span data-ttu-id="204ea-293">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="204ea-293">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="204ea-294">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/reference)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="204ea-294">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="204ea-296">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="204ea-296">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
