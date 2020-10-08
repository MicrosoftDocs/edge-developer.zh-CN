---
description: 与 Microsoft Edge DevTools 中的控制台 UI 相关的每个功能和行为的全面参考。
title: 控制台参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 6a79031e6efbc4b83b83685f32e060a6268dbb2a
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993140"
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





# <span data-ttu-id="bf446-104">控制台参考</span><span class="sxs-lookup"><span data-stu-id="bf446-104">Console Reference</span></span>   



<span data-ttu-id="bf446-105">此页面是与 Microsoft Edge DevTools 控制台相关的功能的参考。</span><span class="sxs-lookup"><span data-stu-id="bf446-105">This page is a reference of features related to the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="bf446-106">它假设你已经熟悉了如何使用 Console 查看记录的消息和运行 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="bf446-106">It assumes that you are already familiar with using the Console to view logged messages and run JavaScript.</span></span>  <span data-ttu-id="bf446-107">如果不是，请参阅 [在控制台中运行 JavaScript 开始][DevToolsConsoleJavascript] ，并 [开始在控制台中记录消息][DevToolsConsoleLog]。</span><span class="sxs-lookup"><span data-stu-id="bf446-107">If not, see [Get Started With Running JavaScript In The Console][DevToolsConsoleJavascript] and [Get Started With Logging Messages In The Console][DevToolsConsoleLog].</span></span>  

<span data-ttu-id="bf446-108">如果你要查找有关函数的 API 参考，如 `console.log()` 请参阅 [控制台 API 参考][DevToolsConsoleApi]。</span><span class="sxs-lookup"><span data-stu-id="bf446-108">If you are looking for the API reference on functions like `console.log()` see [Console API Reference][DevToolsConsoleApi].</span></span>  <span data-ttu-id="bf446-109">有关函数（如函数）的参考 `monitorEvents()` ，请参阅 [控制台实用工具 API 参考][DevToolsConsoleUtilities]。</span><span class="sxs-lookup"><span data-stu-id="bf446-109">For the reference on functions like `monitorEvents()`, see [Console Utilities API Reference][DevToolsConsoleUtilities].</span></span>  

## <span data-ttu-id="bf446-110">打开控制台</span><span class="sxs-lookup"><span data-stu-id="bf446-110">Open the Console</span></span>   

<span data-ttu-id="bf446-111">你可以将控制台作为 [面板](#open-the-console-panel) 或 [抽屉中的选项卡](#open-the-console-tab-in-the-drawer)打开。</span><span class="sxs-lookup"><span data-stu-id="bf446-111">You may open the Console as a [panel](#open-the-console-panel) or as a [tab in the Drawer](#open-the-console-tab-in-the-drawer).</span></span>  

### <span data-ttu-id="bf446-112">打开控制台面板</span><span class="sxs-lookup"><span data-stu-id="bf446-112">Open the Console panel</span></span>   

<span data-ttu-id="bf446-113">按 `Control` + `Shift` + `J` \ (Windows \ ) 或 `Command` + `Option` + `J` \ (macOS \ ) 。</span><span class="sxs-lookup"><span data-stu-id="bf446-113">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span></span>  

:::image type="complex" source="../media/console-hello-console.msft.png" alt-text="控制台面板" lightbox="../media/console-hello-console.msft.png":::
   <span data-ttu-id="bf446-115">**控制台**面板</span><span class="sxs-lookup"><span data-stu-id="bf446-115">The **Console** panel</span></span>  
:::image-end:::  

<span data-ttu-id="bf446-116">若要从 " [命令" 菜单][DevToolsCommandMenu]打开 "控制台" 面板，请开始键入， `Console` 然后运行 " **显示控制台** " 命令，其中旁边有一个 **面板** 标记。</span><span class="sxs-lookup"><span data-stu-id="bf446-116">To open the Console panel from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Panel** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="控制台面板" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="bf446-118">用于显示 **控制台** 面板的命令</span><span class="sxs-lookup"><span data-stu-id="bf446-118">The command to show the **Console** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="bf446-119">打开抽屉中的 "控制台" 选项卡</span><span class="sxs-lookup"><span data-stu-id="bf446-119">Open the Console tab in the Drawer</span></span>   

<span data-ttu-id="bf446-120">按下 `Escape` 或单击 " **自定义" 并控制 DevTools** \ (`...` \ ) 然后选择 " **显示控制台抽屉**"。</span><span class="sxs-lookup"><span data-stu-id="bf446-120">Press `Escape` or click **Customize And Control DevTools** \(`...`\) and then select **Show console drawer**.</span></span>  

:::image type="complex" source="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png" alt-text="控制台面板" lightbox="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png":::
   **<span data-ttu-id="bf446-122">显示控制台抽屉</span><span class="sxs-lookup"><span data-stu-id="bf446-122">Show console drawer</span></span>**  
:::image-end:::  

<span data-ttu-id="bf446-123">抽屉将在 DevTools 窗口底部弹出，并打开 " **控制台** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bf446-123">The Drawer pops up at the bottom of your DevTools window, with the **Console** tab open.</span></span>  

:::image type="complex" source="../media/console-elements-console-drawer-hello-world.msft.png" alt-text="控制台面板" lightbox="../media/console-elements-console-drawer-hello-world.msft.png":::
   <span data-ttu-id="bf446-125">**抽屉**中的 "**控制台**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="bf446-125">The **Console** tab in the **Drawer**</span></span>  
:::image-end:::  

<span data-ttu-id="bf446-126">若要从 " [命令" 菜单][DevToolsCommandMenu]打开 "控制台" 选项卡，请开始键入， `Console` 然后运行 " **显示控制台** " 命令，其中旁边有 **抽屉** 标记。</span><span class="sxs-lookup"><span data-stu-id="bf446-126">To open the Console tab from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Drawer** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="控制台面板" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="bf446-128">显示**抽屉**中的 "**控制台**" 选项卡的命令</span><span class="sxs-lookup"><span data-stu-id="bf446-128">The command to show the **Console** tab in the **Drawer**</span></span>  
:::image-end:::  

### <span data-ttu-id="bf446-129">打开控制台设置</span><span class="sxs-lookup"><span data-stu-id="bf446-129">Open Console Settings</span></span>   

<span data-ttu-id="bf446-130">单击 " **控制台设置** \ (![ 控制台设置 ][ImageSettingsButtonIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="bf446-130">Click **Console Settings** \(![Console Settings][ImageSettingsButtonIcon]\).</span></span>  

:::image type="complex" source="../media/console-settings-group-similar-empty.msft.png" alt-text="控制台面板" lightbox="../media/console-settings-group-similar-empty.msft.png":::
   **<span data-ttu-id="bf446-132">控制台设置</span><span class="sxs-lookup"><span data-stu-id="bf446-132">Console Settings</span></span>**  
:::image-end:::  

<span data-ttu-id="bf446-133">下面的链接对每个设置进行了说明：</span><span class="sxs-lookup"><span data-stu-id="bf446-133">The links below explain each setting:</span></span>  

*   [**<span data-ttu-id="bf446-134">隐藏网络</span><span class="sxs-lookup"><span data-stu-id="bf446-134">Hide Network</span></span>**](#hide-network-messages)  
*   [**<span data-ttu-id="bf446-135">保留日志</span><span class="sxs-lookup"><span data-stu-id="bf446-135">Preserve Log</span></span>**](#persist-messages-across-page-loads)  
*   [**<span data-ttu-id="bf446-136">仅限所选上下文</span><span class="sxs-lookup"><span data-stu-id="bf446-136">Selected Context Only</span></span>**](#filter-out-messages-from-different-contexts)  
*   [**<span data-ttu-id="bf446-137">分组相似</span><span class="sxs-lookup"><span data-stu-id="bf446-137">Group Similar</span></span>**](#disable-message-grouping)  
*   [**<span data-ttu-id="bf446-138">日志 XmlHttpRequests</span><span class="sxs-lookup"><span data-stu-id="bf446-138">Log XmlHttpRequests</span></span>**](#log-xhr-and-fetch-requests)  
*   [**<span data-ttu-id="bf446-139">积极评估</span><span class="sxs-lookup"><span data-stu-id="bf446-139">Eager Evaluation</span></span>**](#disable-eager-evaluation)  
*   [**<span data-ttu-id="bf446-140">历史记录中的自动完成</span><span class="sxs-lookup"><span data-stu-id="bf446-140">Autocomplete From History</span></span>**](#disable-autocomplete-from-history)  
    
### <span data-ttu-id="bf446-141">打开控制台边栏</span><span class="sxs-lookup"><span data-stu-id="bf446-141">Open the Console Sidebar</span></span>   

<span data-ttu-id="bf446-142">单击 " **显示控制台边栏** \ (![ 显示控制台边栏 ][ImageShowConsoleSidebarIcon] \ ) " 显示侧栏，它对于筛选很有用。</span><span class="sxs-lookup"><span data-stu-id="bf446-142">Click **Show Console Sidebar** \(![Show Console Sidebar][ImageShowConsoleSidebarIcon]\) to show the Sidebar, which is useful for filtering.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-empty.msft.png" alt-text="控制台面板" lightbox="../media/console-sidebar-drawer-empty.msft.png":::
   <span data-ttu-id="bf446-144">**控制台** 侧</span><span class="sxs-lookup"><span data-stu-id="bf446-144">**Console** Sidebar</span></span>  
:::image-end:::  

## <span data-ttu-id="bf446-145">查看邮件</span><span class="sxs-lookup"><span data-stu-id="bf446-145">View messages</span></span>   

<span data-ttu-id="bf446-146">本部分包含更改如何在控制台中显示消息的功能。</span><span class="sxs-lookup"><span data-stu-id="bf446-146">This section contains features that change how messages are presented in the Console.</span></span>  <span data-ttu-id="bf446-147">请参阅查看动手演练的 [消息][DevToolsConsoleViewMessages] 。</span><span class="sxs-lookup"><span data-stu-id="bf446-147">See [View messages][DevToolsConsoleViewMessages] for a hands-on walkthrough.</span></span>  

### <span data-ttu-id="bf446-148">禁用邮件分组</span><span class="sxs-lookup"><span data-stu-id="bf446-148">Disable message grouping</span></span>   

<span data-ttu-id="bf446-149">[打开 "控制台设置](#open-console-settings) " 并禁用 " **分组类似** "，禁用控制台的默认消息分组行为。</span><span class="sxs-lookup"><span data-stu-id="bf446-149">[Open Console Settings](#open-console-settings) and disable **Group similar** to disable the default message grouping behavior of the Console.</span></span>  <span data-ttu-id="bf446-150">有关示例，请参阅 [记录 XHR 和获取请求](#log-xhr-and-fetch-requests) 。</span><span class="sxs-lookup"><span data-stu-id="bf446-150">See [Log XHR and Fetch requests](#log-xhr-and-fetch-requests) for an example.</span></span>  

### <span data-ttu-id="bf446-151">记录 XHR 和回迁请求</span><span class="sxs-lookup"><span data-stu-id="bf446-151">Log XHR and Fetch requests</span></span>   

<span data-ttu-id="bf446-152">[打开控制台设置](#open-console-settings) 并启用 **日志 XMLHttpRequests** ，以便在 `XMLHttpRequest` 发生时将所有和请求记录到 `Fetch` 控制台。</span><span class="sxs-lookup"><span data-stu-id="bf446-152">[Open Console Settings](#open-console-settings) and enable **Log XMLHttpRequests** to log all `XMLHttpRequest` and `Fetch` requests to the Console as they happen.</span></span>  

:::image type="complex" source="../media/console-xhr-fetch.msft.png" alt-text="控制台面板" lightbox="../media/console-xhr-fetch.msft.png":::
   <span data-ttu-id="bf446-154">日志 `XMLHttpRequest` 和 `Fetch` 请求</span><span class="sxs-lookup"><span data-stu-id="bf446-154">Log `XMLHttpRequest` and `Fetch` requests</span></span>  
:::image-end:::  
<span data-ttu-id="bf446-155">上图中的顶部消息显示了该 **控制台**的默认分组行为。</span><span class="sxs-lookup"><span data-stu-id="bf446-155">The top message in previous figure displays the default grouping behavior of the **Console**.</span></span>  <!--  In the following figure, the same log is displayed after [disabling message grouping](#disable-message-grouping).  -->  

<!--  
> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> :::image type="complex" source="../media/console-xhr-fetch-all.msft.png" alt-text="控制台面板" lightbox="../media/console-xhr-fetch-all.msft.png":::
>    How the logged XMLHttpRequest and Fetch requests look after ungrouping  
> :::image-end:::  
-->  

<!--todo: add example for ungrouping console items  -->  

### <span data-ttu-id="bf446-156">跨页面加载保留消息</span><span class="sxs-lookup"><span data-stu-id="bf446-156">Persist messages across page loads</span></span>   

<span data-ttu-id="bf446-157">默认情况下，无论何时加载新页面，控制台都会被清除。</span><span class="sxs-lookup"><span data-stu-id="bf446-157">By default the Console clears whenever you load a new page.</span></span>  <span data-ttu-id="bf446-158">若要在每个页面加载期间保持消息，请 [打开控制台设置](#open-console-settings) ，然后启用 " **保留日志** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="bf446-158">To persist messages across page loads, [Open Console Settings](#open-console-settings) and then enable the **Preserve Log** checkbox.</span></span>  

### <span data-ttu-id="bf446-159">隐藏网络消息</span><span class="sxs-lookup"><span data-stu-id="bf446-159">Hide network messages</span></span>   

<span data-ttu-id="bf446-160">默认情况下，浏览器将网络消息记录到 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="bf446-160">By default the browser logs network messages to the **Console**.</span></span>  <span data-ttu-id="bf446-161">在下图中，所选邮件表示 HTTP 状态代码 `429` 。</span><span class="sxs-lookup"><span data-stu-id="bf446-161">In the following figure, the selected message represents an HTTP status code of `429`.</span></span>  

:::image type="complex" source="../media/console-show-network.msft.png" alt-text="控制台面板" lightbox="../media/console-show-network.msft.png":::
   <span data-ttu-id="bf446-163">`429`**控制台**中的一条消息</span><span class="sxs-lookup"><span data-stu-id="bf446-163">A `429` message in the **Console**</span></span>  
:::image-end:::  
<span data-ttu-id="bf446-164">要隐藏网络消息，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bf446-164">To hide network messages:</span></span>  

1.  <span data-ttu-id="bf446-165">[打开控制台设置](#open-console-settings)。</span><span class="sxs-lookup"><span data-stu-id="bf446-165">[Open Console Settings](#open-console-settings).</span></span>  
1.  <span data-ttu-id="bf446-166">启用 " **隐藏网络** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="bf446-166">Enable the **Hide Network** checkbox.</span></span>  
    
## <span data-ttu-id="bf446-167">筛选邮件</span><span class="sxs-lookup"><span data-stu-id="bf446-167">Filter messages</span></span>   

<span data-ttu-id="bf446-168">可通过多种方式在控制台中筛选出消息。</span><span class="sxs-lookup"><span data-stu-id="bf446-168">There are many ways to filter out messages in the Console.</span></span>  

### <span data-ttu-id="bf446-169">筛选出浏览器消息</span><span class="sxs-lookup"><span data-stu-id="bf446-169">Filter out browser messages</span></span>   

<span data-ttu-id="bf446-170">[打开控制台侧栏](#open-the-console-sidebar) ，然后单击 " **用户消息** "，仅显示来自页面 JavaScript 的消息。</span><span class="sxs-lookup"><span data-stu-id="bf446-170">[Open the Console Sidebar](#open-the-console-sidebar) and click **User Messages** to only show messages that came from the JavaScript of the page.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-user-messages.msft.png" alt-text="控制台面板" lightbox="../media/console-sidebar-drawer-user-messages.msft.png":::
   <span data-ttu-id="bf446-172">查看用户消息</span><span class="sxs-lookup"><span data-stu-id="bf446-172">View user messages</span></span>  
:::image-end:::  

### <span data-ttu-id="bf446-173">按日志级别筛选</span><span class="sxs-lookup"><span data-stu-id="bf446-173">Filter by log level</span></span>   

<span data-ttu-id="bf446-174">DevTools 为每个 `console.*` 方法分配一个严重级别。</span><span class="sxs-lookup"><span data-stu-id="bf446-174">DevTools assigns each `console.*` method a severity level.</span></span>  <span data-ttu-id="bf446-175">有4个级别： `Verbose` 、 `Info` 、 `Warning` 和 `Error` 。</span><span class="sxs-lookup"><span data-stu-id="bf446-175">There are 4 levels: `Verbose`, `Info`, `Warning`, and `Error`.</span></span>  <span data-ttu-id="bf446-176">例如，位于 `console.log()` `Info` 组中，而位于 `console.error()` 组中 `Error` 。</span><span class="sxs-lookup"><span data-stu-id="bf446-176">For example, `console.log()` is in the `Info` group, whereas `console.error()` is in the `Error` group.</span></span>  <span data-ttu-id="bf446-177">[控制台 API 参考][DevToolsConsoleApi]描述每个适用方法的严重级别。</span><span class="sxs-lookup"><span data-stu-id="bf446-177">The [Console API Reference][DevToolsConsoleApi] describes the severity level of each applicable method.</span></span>  <span data-ttu-id="bf446-178">浏览器记录到控制台的每条消息也具有严重级别。</span><span class="sxs-lookup"><span data-stu-id="bf446-178">Every message that the browser logs to the Console has a severity level too.</span></span>  <span data-ttu-id="bf446-179">您可以隐藏不感兴趣的任何级别的邮件。</span><span class="sxs-lookup"><span data-stu-id="bf446-179">You may hide any level of messages that you are not interested in.</span></span>  <span data-ttu-id="bf446-180">例如，如果只对邮件感兴趣 `Error` ，则可以隐藏其他3个组。</span><span class="sxs-lookup"><span data-stu-id="bf446-180">For example, if you are only interested in `Error` messages, you may hide the other 3 groups.</span></span>  

<span data-ttu-id="bf446-181">单击 " **日志级别** " 下拉列表以启用或禁用 `Verbose` 、 `Info` 或 "消息" `Warning` `Error` 。</span><span class="sxs-lookup"><span data-stu-id="bf446-181">Click the **Log Levels** dropdown to enable or disable `Verbose`, `Info`, `Warning` or `Error` messages.</span></span>  

:::image type="complex" source="../media/console-log-level-default-levels.msft.png" alt-text="控制台面板" lightbox="../media/console-log-level-default-levels.msft.png":::
   <span data-ttu-id="bf446-183">**日志级别**下拉列表</span><span class="sxs-lookup"><span data-stu-id="bf446-183">The **Log Levels** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="bf446-184">您还可以按日志级别进行筛选，方法是[打开控制台边栏](#open-the-console-sidebar)，然后单击 "**错误**"、"**警告**"、"信息" 或 "**详细\*\*\*\*信息**"。</span><span class="sxs-lookup"><span data-stu-id="bf446-184">You may also filter by log level by [opening the Console Sidebar](#open-the-console-sidebar) and then clicking **Errors**, **Warnings**, **Info**, or **Verbose**.</span></span>  

:::image type="complex" source="../media/console-sidebar-warnings.msft.png" alt-text="控制台面板" lightbox="../media/console-sidebar-warnings.msft.png":::
   <span data-ttu-id="bf446-186">使用边栏查看警告</span><span class="sxs-lookup"><span data-stu-id="bf446-186">Use the Sidebar to view warnings</span></span>  
:::image-end:::  

### <span data-ttu-id="bf446-187">按 URL 筛选邮件</span><span class="sxs-lookup"><span data-stu-id="bf446-187">Filter messages by URL</span></span>   

<span data-ttu-id="bf446-188">键入 `url:` 后跟 url，仅查看来自该 url 的邮件。</span><span class="sxs-lookup"><span data-stu-id="bf446-188">Type `url:` followed by a URL to only view messages that came from that URL.</span></span>  <span data-ttu-id="bf446-189">键入 DevTools 后，将 `url:` 显示所有相关的 url。</span><span class="sxs-lookup"><span data-stu-id="bf446-189">After you type `url:` DevTools shows all relevant URLs.</span></span>  <span data-ttu-id="bf446-190">域也有效。</span><span class="sxs-lookup"><span data-stu-id="bf446-190">Domains also work.</span></span>  <span data-ttu-id="bf446-191">例如，如果 `https://example.com/a.js` 和 `https://example.com/b.js` 正在记录邮件， `url:https://example.com` 则可让你关注来自这两个脚本的消息。</span><span class="sxs-lookup"><span data-stu-id="bf446-191">For example, if `https://example.com/a.js` and `https://example.com/b.js` are logging messages, `url:https://example.com` enables you to focus on the messages from these 2 scripts.</span></span>  

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="控制台面板" lightbox="../media/console-filter-text.msft.png":::
   <span data-ttu-id="bf446-193">URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="bf446-193">A URL filter</span></span>  
:::image-end:::  

<span data-ttu-id="bf446-194">键入 `-url:` 以隐藏来自该 URL 的邮件。</span><span class="sxs-lookup"><span data-stu-id="bf446-194">Type `-url:` to hide messages from that URL.</span></span>  <span data-ttu-id="bf446-195">这称为负 URL 筛选器。</span><span class="sxs-lookup"><span data-stu-id="bf446-195">This is called a negative URL filter.</span></span>  

:::image type="complex" source="../media/console-negative-filter-text.msft.png" alt-text="控制台面板" lightbox="../media/console-negative-filter-text.msft.png":::
   <span data-ttu-id="bf446-197">用于隐藏所有与 URL 匹配的邮件的负 URL 筛选器 `https://b.wal.co`</span><span class="sxs-lookup"><span data-stu-id="bf446-197">A negative URL filter that hides all messages that match the `https://b.wal.co` URL</span></span>
:::image-end:::  

<span data-ttu-id="bf446-198">您还可以通过 [打开控制台边栏](#open-the-console-sidebar)，展开 " **用户消息** " 部分，然后单击包含要对其进行焦点的邮件的脚本的 URL，显示来自单个 URL 的邮件。</span><span class="sxs-lookup"><span data-stu-id="bf446-198">You may also show messages from a single URL by [opening the Console Sidebar](#open-the-console-sidebar), expanding the **User Messages** section, and then clicking the URL of the script containing the messages on which you want to focus.</span></span>  

:::image type="complex" source="../media/console-filter-text-specified.msft.png" alt-text="控制台面板" lightbox="../media/console-filter-text-specified.msft.png":::
   <span data-ttu-id="bf446-200">查看来自的邮件</span><span class="sxs-lookup"><span data-stu-id="bf446-200">View the messages that came from</span></span> `wp-ad.min.js`  
:::image-end:::  

### <span data-ttu-id="bf446-201">筛选出来自不同上下文的消息</span><span class="sxs-lookup"><span data-stu-id="bf446-201">Filter out messages from different contexts</span></span>   

<span data-ttu-id="bf446-202">假设您的页面上有广告 (广告 ) 。</span><span class="sxs-lookup"><span data-stu-id="bf446-202">Suppose that you have an advertisement \(ad\) on your page.</span></span>  <span data-ttu-id="bf446-203">广告嵌入在中 `<iframe>` ，并且会在您的控制台中生成大量消息。</span><span class="sxs-lookup"><span data-stu-id="bf446-203">The ad is embedded in an `<iframe>` and is generating a lot of messages in your Console.</span></span>  <span data-ttu-id="bf446-204">由于广告在不同的 [JavaScript 上下文](#select-javascript-context)中运行，因此隐藏消息的一种方法是 [打开控制台设置](#open-console-settings) 并启用 " **仅限选定的上下文** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="bf446-204">Because the ad is running in a different [JavaScript context](#select-javascript-context), one way to hide the messages is to [open Console Settings](#open-console-settings) and enable the **Selected Context Only** checkbox.</span></span>  

### <span data-ttu-id="bf446-205">筛选出与正则表达式模式不匹配的消息</span><span class="sxs-lookup"><span data-stu-id="bf446-205">Filter out messages that do not match a regular expression pattern</span></span>   

<span data-ttu-id="bf446-206">`/[gm][ta][mi]/`在 "**筛选器**" 文本框中键入正则表达式，以筛选出与该模式不匹配的任何消息。</span><span class="sxs-lookup"><span data-stu-id="bf446-206">Type a regular expression such as `/[gm][ta][mi]/` in the **Filter** text box to filter out any messages that do not match that pattern.</span></span>  <span data-ttu-id="bf446-207">DevTools 检查是否在消息文本或导致消息被记录的脚本中找到该模式。</span><span class="sxs-lookup"><span data-stu-id="bf446-207">DevTools checks if the pattern is found in the message text or the script that caused the message to be logged.</span></span>  

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="控制台面板" lightbox="../media/console-filter-regex.msft.png":::
   <span data-ttu-id="bf446-209">筛选出与 regex 表达式不匹配的任何消息 `/[gm][ta][mi]/`</span><span class="sxs-lookup"><span data-stu-id="bf446-209">Filter out any messages that do not match the `/[gm][ta][mi]/` regex expression</span></span>  
:::image-end:::  

## <span data-ttu-id="bf446-210">运行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="bf446-210">Run JavaScript</span></span>   

<span data-ttu-id="bf446-211">本部分包含与在控制台中运行 JavaScript 相关的功能。</span><span class="sxs-lookup"><span data-stu-id="bf446-211">This section contains features related to running JavaScript in the Console.</span></span>  <span data-ttu-id="bf446-212">请参阅运行参与练习的 [JavaScript][DevToolsConsoleOverviewJavascript] 。</span><span class="sxs-lookup"><span data-stu-id="bf446-212">See [Run JavaScript][DevToolsConsoleOverviewJavascript] for a hands-on walkthrough.</span></span>  

### <span data-ttu-id="bf446-213">重新运行历史记录中的表达式</span><span class="sxs-lookup"><span data-stu-id="bf446-213">Re-run expressions from history</span></span>   

<span data-ttu-id="bf446-214">按下 `Up Arrow` 键，循环浏览你之前在控制台中运行的 JavaScript 表达式的历史记录。</span><span class="sxs-lookup"><span data-stu-id="bf446-214">Press the `Up Arrow` key to cycle through the history of JavaScript expressions that you ran earlier in the Console.</span></span>  <span data-ttu-id="bf446-215">按键 `Enter` 再次运行该表达式。</span><span class="sxs-lookup"><span data-stu-id="bf446-215">Press `Enter` to run that expression again.</span></span>  

### <span data-ttu-id="bf446-216">使用实时表达式实时监视表达式的值</span><span class="sxs-lookup"><span data-stu-id="bf446-216">Watch the value of an expression in real-time with Live Expressions</span></span>   

<span data-ttu-id="bf446-217">如果您发现自己在控制台中重复键入相同的 JavaScript 表达式，您可能会发现创建 **实时表达式**变得更容易。</span><span class="sxs-lookup"><span data-stu-id="bf446-217">If you find yourself typing the same JavaScript expression in the Console repeatedly, you may find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="bf446-218">使用 **实时表达式** ，您只需要键入一个表达式，然后将其固定到您的控制台顶部。</span><span class="sxs-lookup"><span data-stu-id="bf446-218">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span></span>  <span data-ttu-id="bf446-219">表达式的值几乎实时更新。</span><span class="sxs-lookup"><span data-stu-id="bf446-219">The value of the expression updates in near real-time.</span></span>  <span data-ttu-id="bf446-220">请参阅 [实时在实时表达式中观看 JavaScript 表达式值][DevToolsConsoleLiveExpressions]。</span><span class="sxs-lookup"><span data-stu-id="bf446-220">See [Watch JavaScript Expression Values In Real-Time With Live Expressions][DevToolsConsoleLiveExpressions].</span></span>  

### <span data-ttu-id="bf446-221">禁用热情评估</span><span class="sxs-lookup"><span data-stu-id="bf446-221">Disable Eager Evaluation</span></span>   

<span data-ttu-id="bf446-222">当您在控制台中键入 JavaScript 表达式时， **预先计算** 会显示该表达式的返回值的预览。</span><span class="sxs-lookup"><span data-stu-id="bf446-222">As you type JavaScript expressions in the Console, **Eager Evaluation** shows a preview of the return value for that expression.</span></span>  <span data-ttu-id="bf446-223">[打开 "控制台设置](#open-console-settings) " 并禁用 " **预先评估** " 复选框以关闭返回值预览。</span><span class="sxs-lookup"><span data-stu-id="bf446-223">[Open Console Settings](#open-console-settings) and disable the **Eager Evaluation** checkbox to turn off the return value previews.</span></span>  

### <span data-ttu-id="bf446-224">禁用历史记录中的自动完成</span><span class="sxs-lookup"><span data-stu-id="bf446-224">Disable autocomplete from history</span></span>   

<span data-ttu-id="bf446-225">当您键入表达式时，控制台的 "自动完成" 弹出窗口将显示您之前运行的表达式。</span><span class="sxs-lookup"><span data-stu-id="bf446-225">As you type out an expression, the autocomplete popup window for the Console shows expressions that you ran earlier.</span></span>  <span data-ttu-id="bf446-226">这些表达式前置 `>` 字符。</span><span class="sxs-lookup"><span data-stu-id="bf446-226">These expressions are prepended with the `>` character.</span></span>  <span data-ttu-id="bf446-227">[打开 "控制台设置](#open-console-settings) " 并禁用 " **从历史记录自动完成** " 复选框以停止显示历史记录中的表达式。</span><span class="sxs-lookup"><span data-stu-id="bf446-227">[Open Console Settings](#open-console-settings) and disable the **Autocomplete From History** checkbox to stop showing expressions from your history.</span></span>  

> [!NOTE]
> <span data-ttu-id="bf446-228">在下图中， `document.querySelector('a')` `document.querySelector('img')` 是之前计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="bf446-228">In the following figure, `document.querySelector('a')` and `document.querySelector('img')` are expressions that were evaluated earlier.</span></span>  

:::image type="complex" source="../media/console-filter-text-autofilter-history.msft.png" alt-text="控制台面板" lightbox="../media/console-filter-text-autofilter-history.msft.png":::
   <span data-ttu-id="bf446-230">"自动完成" 弹出窗口显示历史记录中的表达式</span><span class="sxs-lookup"><span data-stu-id="bf446-230">The autocomplete popup displays expressions from history</span></span>  
:::image-end:::  

### <span data-ttu-id="bf446-231">选择 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="bf446-231">Select JavaScript context</span></span>   

<span data-ttu-id="bf446-232">默认情况下， **JavaScript 上下文** 下拉列表设置为 " **页首**"，这表示主文档的 [浏览上下文][MDNBrowsingContext] 。</span><span class="sxs-lookup"><span data-stu-id="bf446-232">By default the **JavaScript Context** dropdown is set to **top**, which represents the [browsing context][MDNBrowsingContext] of the main document.</span></span>  

:::image type="complex" source="../media/console-dom-level-top.msft.png" alt-text="控制台面板" lightbox="../media/console-dom-level-top.msft.png":::
   <span data-ttu-id="bf446-234">**JavaScript 上下文**下拉列表</span><span class="sxs-lookup"><span data-stu-id="bf446-234">The **JavaScript Context** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="bf446-235">假设您的页面上有一个嵌入的广告 `<iframe>` 。</span><span class="sxs-lookup"><span data-stu-id="bf446-235">Suppose you have an ad on your page embedded in an `<iframe>`.</span></span>  <span data-ttu-id="bf446-236">你希望运行 JavaScript，以便调整广告的 DOM。</span><span class="sxs-lookup"><span data-stu-id="bf446-236">You want to run JavaScript in order to tweak the DOM of the ad.</span></span>  <span data-ttu-id="bf446-237">应首先从 **JavaScript 上下文** 下拉列表中选择广告的浏览上下文。</span><span class="sxs-lookup"><span data-stu-id="bf446-237">You should first select the browsing context of the ad from the **JavaScript Context** dropdown.</span></span>  

:::image type="complex" source="../media/console-dom-level-multiple.msft.png" alt-text="控制台面板" lightbox="../media/console-dom-level-multiple.msft.png":::
   <span data-ttu-id="bf446-239">选择其他 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="bf446-239">Select a different JavaScript context</span></span>  
:::image-end:::  

## <span data-ttu-id="bf446-240">清除控制台</span><span class="sxs-lookup"><span data-stu-id="bf446-240">Clear the Console</span></span>   

<span data-ttu-id="bf446-241">你可以使用以下任何工作流来清除控制台：</span><span class="sxs-lookup"><span data-stu-id="bf446-241">You may use any of the following workflows to clear the Console:</span></span>  

*   <span data-ttu-id="bf446-242">单击 " **清除控制台** \ (![ 清除控制台 ][ImageClearConsoleIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="bf446-242">Click **Clear Console** \(![Clear Console][ImageClearConsoleIcon]\).</span></span>  
*   <span data-ttu-id="bf446-243">右键单击一条消息，然后选择 " **清除控制台**"。</span><span class="sxs-lookup"><span data-stu-id="bf446-243">Right-click a message and then select **Clear Console**.</span></span>  
*   <span data-ttu-id="bf446-244">`clear()`在控制台中键入，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="bf446-244">Type `clear()` in the Console and then press `Enter`.</span></span>  
*   <span data-ttu-id="bf446-245">`console.clear()`从你的网页的 JavaScript 调用。</span><span class="sxs-lookup"><span data-stu-id="bf446-245">Call `console.clear()` from the JavaScript for your webpage.</span></span>  
*   <span data-ttu-id="bf446-246">`Control` + `L` 控制台处于焦点状态时按键。</span><span class="sxs-lookup"><span data-stu-id="bf446-246">Press `Control`+`L` while the Console is in focus.</span></span>  
    
<!--
 

  
-->  

<!-- image links -->  

[ImageClearConsoleIcon]: ../media/clear-console-button-icon.msft.png  
[ImageSettingsButtonIcon]: ../media/settings-button-icon.msft.png  
[ImageShowConsoleSidebarIcon]: ../media/show-console-sidebar-icon.msft.png  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"  
[DevToolsConsoleViewMessages]: ./index.md#viewing-logged-messages "查看已记录的消息-控制台概述 |Microsoft 文档"  
[DevToolsConsoleApi]: ./api.md "控制台 API 参考 |Microsoft 文档"  
[DevToolsConsoleOverviewJavascript]: ./index.md#running-javascript "运行 JavaScript-控制台概述 |Microsoft 文档"  
[DevToolsConsoleJavascript]: ./javascript.md "开始在控制台中运行 JavaScript |Microsoft 文档"  
[DevToolsConsoleLiveExpressions]: ./live-expressions.md "实时监视 JavaScript 表达式值和实时表达式 |Microsoft 文档"  
[DevToolsConsoleLog]: ./log.md "在控制台中记录邮件的入门 |Microsoft 文档"  
[DevToolsConsoleUtilities]: ./utilities.md "控制台实用工具 API 参考 |Microsoft 文档"  

[MDNBrowsingContext]: https://developer.mozilla.org/docs/Glossary/Browsing_context "浏览上下文 |MDN"  

> [!NOTE]
> <span data-ttu-id="bf446-256">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="bf446-256">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="bf446-257">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="bf446-257">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="bf446-259">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="bf446-259">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
