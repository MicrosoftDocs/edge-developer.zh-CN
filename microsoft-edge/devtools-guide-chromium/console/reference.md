---
title: 控制台参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 51a85c3dad121dcb42633390de9b4e817074546e
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982395"
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





# <span data-ttu-id="f4e9b-103">控制台参考</span><span class="sxs-lookup"><span data-stu-id="f4e9b-103">Console Reference</span></span>   



<span data-ttu-id="f4e9b-104">此页面是与 Microsoft Edge DevTools 控制台相关的功能的参考。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-104">This page is a reference of features related to the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="f4e9b-105">它假设你已经熟悉了如何使用 Console 查看记录的消息和运行 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-105">It assumes that you are already familiar with using the Console to view logged messages and run JavaScript.</span></span>  <span data-ttu-id="f4e9b-106">如果不是，请参阅 [在控制台中运行 JavaScript 开始][DevToolsConsoleJavascript] ，并 [开始在控制台中记录消息][DevToolsConsoleLog]。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-106">If not, see [Get Started With Running JavaScript In The Console][DevToolsConsoleJavascript] and [Get Started With Logging Messages In The Console][DevToolsConsoleLog].</span></span>  

<span data-ttu-id="f4e9b-107">如果你要查找有关函数的 API 参考，如 `console.log()` 请参阅 [控制台 API 参考][DevToolsConsoleApi]。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-107">If you are looking for the API reference on functions like `console.log()` see [Console API Reference][DevToolsConsoleApi].</span></span>  <span data-ttu-id="f4e9b-108">有关函数（如函数）的参考 `monitorEvents()` ，请参阅 [控制台实用工具 API 参考][DevToolsConsoleUtilities]。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-108">For the reference on functions like `monitorEvents()`, see [Console Utilities API Reference][DevToolsConsoleUtilities].</span></span>  

## <span data-ttu-id="f4e9b-109">打开控制台</span><span class="sxs-lookup"><span data-stu-id="f4e9b-109">Open the Console</span></span>   

<span data-ttu-id="f4e9b-110">你可以将控制台作为 [面板](#open-the-console-panel) 或 [抽屉中的选项卡](#open-the-console-tab-in-the-drawer)打开。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-110">You may open the Console as a [panel](#open-the-console-panel) or as a [tab in the Drawer](#open-the-console-tab-in-the-drawer).</span></span>  

### <span data-ttu-id="f4e9b-111">打开控制台面板</span><span class="sxs-lookup"><span data-stu-id="f4e9b-111">Open the Console panel</span></span>   

<span data-ttu-id="f4e9b-112">按 `Control` + `Shift` + `J` \ (Windows \ ) 或 `Command` + `Option` + `J` \ (macOS \ ) 。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-112">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span></span>  

:::image type="complex" source="../media/console-hello-console.msft.png" alt-text="控制台面板" lightbox="../media/console-hello-console.msft.png":::
   <span data-ttu-id="f4e9b-114">**控制台**面板</span><span class="sxs-lookup"><span data-stu-id="f4e9b-114">The **Console** panel</span></span>  
:::image-end:::  

<span data-ttu-id="f4e9b-115">若要从 " [命令" 菜单][DevToolsCommandMenu]打开 "控制台" 面板，请开始键入， `Console` 然后运行 " **显示控制台** " 命令，其中旁边有一个 **面板** 标记。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-115">To open the Console panel from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Panel** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="用于显示控制台面板的命令" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="f4e9b-117">用于显示 **控制台** 面板的命令</span><span class="sxs-lookup"><span data-stu-id="f4e9b-117">The command to show the **Console** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="f4e9b-118">打开抽屉中的 "控制台" 选项卡</span><span class="sxs-lookup"><span data-stu-id="f4e9b-118">Open the Console tab in the Drawer</span></span>   

<span data-ttu-id="f4e9b-119">按下 `Escape` 或单击 " **自定义" 并控制 DevTools** \ (`...` \ ) 然后选择 " **显示控制台抽屉**"。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-119">Press `Escape` or click **Customize And Control DevTools** \(`...`\) and then select **Show console drawer**.</span></span>  

:::image type="complex" source="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png" alt-text="显示控制台抽屉" lightbox="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png":::
   **<span data-ttu-id="f4e9b-121">显示控制台抽屉</span><span class="sxs-lookup"><span data-stu-id="f4e9b-121">Show console drawer</span></span>**  
:::image-end:::  

<span data-ttu-id="f4e9b-122">抽屉将在 DevTools 窗口底部弹出，并打开 " **控制台** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-122">The Drawer pops up at the bottom of your DevTools window, with the **Console** tab open.</span></span>  

:::image type="complex" source="../media/console-elements-console-drawer-hello-world.msft.png" alt-text="抽屉中的 "控制台" 选项卡" lightbox="../media/console-elements-console-drawer-hello-world.msft.png":::
   <span data-ttu-id="f4e9b-124">**抽屉**中的 "**控制台**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="f4e9b-124">The **Console** tab in the **Drawer**</span></span>  
:::image-end:::  

<span data-ttu-id="f4e9b-125">若要从 " [命令" 菜单][DevToolsCommandMenu]打开 "控制台" 选项卡，请开始键入， `Console` 然后运行 " **显示控制台** " 命令，其中旁边有 **抽屉** 标记。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-125">To open the Console tab from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Drawer** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="显示抽屉中的 "控制台" 选项卡的命令" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="f4e9b-127">显示**抽屉**中的 "**控制台**" 选项卡的命令</span><span class="sxs-lookup"><span data-stu-id="f4e9b-127">The command to show the **Console** tab in the **Drawer**</span></span>  
:::image-end:::  

### <span data-ttu-id="f4e9b-128">打开控制台设置</span><span class="sxs-lookup"><span data-stu-id="f4e9b-128">Open Console Settings</span></span>   

<span data-ttu-id="f4e9b-129">单击 " **控制台设置** \ (![ 控制台设置 ][ImageSettingsButtonIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-129">Click **Console Settings** \(![Console Settings][ImageSettingsButtonIcon]\).</span></span>  

:::image type="complex" source="../media/console-settings-group-similar-empty.msft.png" alt-text="控制台设置" lightbox="../media/console-settings-group-similar-empty.msft.png":::
   **<span data-ttu-id="f4e9b-131">控制台设置</span><span class="sxs-lookup"><span data-stu-id="f4e9b-131">Console Settings</span></span>**  
:::image-end:::  

<span data-ttu-id="f4e9b-132">下面的链接对每个设置进行了说明：</span><span class="sxs-lookup"><span data-stu-id="f4e9b-132">The links below explain each setting:</span></span>  

*   [**<span data-ttu-id="f4e9b-133">隐藏网络</span><span class="sxs-lookup"><span data-stu-id="f4e9b-133">Hide Network</span></span>**](#hide-network-messages)  
*   [**<span data-ttu-id="f4e9b-134">保留日志</span><span class="sxs-lookup"><span data-stu-id="f4e9b-134">Preserve Log</span></span>**](#persist-messages-across-page-loads)  
*   [**<span data-ttu-id="f4e9b-135">仅限所选上下文</span><span class="sxs-lookup"><span data-stu-id="f4e9b-135">Selected Context Only</span></span>**](#filter-out-messages-from-different-contexts)  
*   [**<span data-ttu-id="f4e9b-136">分组相似</span><span class="sxs-lookup"><span data-stu-id="f4e9b-136">Group Similar</span></span>**](#disable-message-grouping)  
*   [**<span data-ttu-id="f4e9b-137">日志 XmlHttpRequests</span><span class="sxs-lookup"><span data-stu-id="f4e9b-137">Log XmlHttpRequests</span></span>**](#log-xhr-and-fetch-requests)  
*   [**<span data-ttu-id="f4e9b-138">积极评估</span><span class="sxs-lookup"><span data-stu-id="f4e9b-138">Eager Evaluation</span></span>**](#disable-eager-evaluation)  
*   [**<span data-ttu-id="f4e9b-139">历史记录中的自动完成</span><span class="sxs-lookup"><span data-stu-id="f4e9b-139">Autocomplete From History</span></span>**](#disable-autocomplete-from-history)  
    
### <span data-ttu-id="f4e9b-140">打开控制台边栏</span><span class="sxs-lookup"><span data-stu-id="f4e9b-140">Open the Console Sidebar</span></span>   

<span data-ttu-id="f4e9b-141">单击 " **显示控制台边栏** \ (![ 显示控制台边栏 ][ImageShowConsoleSidebarIcon] \ ) " 显示侧栏，它对于筛选很有用。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-141">Click **Show Console Sidebar** \(![Show Console Sidebar][ImageShowConsoleSidebarIcon]\) to show the Sidebar, which is useful for filtering.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-empty.msft.png" alt-text="控制台边栏" lightbox="../media/console-sidebar-drawer-empty.msft.png":::
   <span data-ttu-id="f4e9b-143">**控制台** 侧</span><span class="sxs-lookup"><span data-stu-id="f4e9b-143">**Console** Sidebar</span></span>  
:::image-end:::  

## <span data-ttu-id="f4e9b-144">查看邮件</span><span class="sxs-lookup"><span data-stu-id="f4e9b-144">View messages</span></span>   

<span data-ttu-id="f4e9b-145">本部分包含更改如何在控制台中显示消息的功能。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-145">This section contains features that change how messages are presented in the Console.</span></span>  <span data-ttu-id="f4e9b-146">请参阅查看动手演练的 [消息][DevToolsConsoleViewMessages] 。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-146">See [View messages][DevToolsConsoleViewMessages] for a hands-on walkthrough.</span></span>  

### <span data-ttu-id="f4e9b-147">禁用邮件分组</span><span class="sxs-lookup"><span data-stu-id="f4e9b-147">Disable message grouping</span></span>   

<span data-ttu-id="f4e9b-148">[打开 "控制台设置](#open-console-settings) " 并禁用 " **分组类似** "，禁用控制台的默认消息分组行为。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-148">[Open Console Settings](#open-console-settings) and disable **Group similar** to disable the default message grouping behavior of the Console.</span></span>  <span data-ttu-id="f4e9b-149">有关示例，请参阅 [记录 XHR 和获取请求](#log-xhr-and-fetch-requests) 。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-149">See [Log XHR and Fetch requests](#log-xhr-and-fetch-requests) for an example.</span></span>  

### <span data-ttu-id="f4e9b-150">记录 XHR 和回迁请求</span><span class="sxs-lookup"><span data-stu-id="f4e9b-150">Log XHR and Fetch requests</span></span>   

<span data-ttu-id="f4e9b-151">[打开控制台设置](#open-console-settings) 并启用 **日志 XMLHttpRequests** ，以便在 `XMLHttpRequest` 发生时将所有和请求记录到 `Fetch` 控制台。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-151">[Open Console Settings](#open-console-settings) and enable **Log XMLHttpRequests** to log all `XMLHttpRequest` and `Fetch` requests to the Console as they happen.</span></span>  

:::image type="complex" source="../media/console-xhr-fetch.msft.png" alt-text="记录 XMLHttpRequest 和回迁请求" lightbox="../media/console-xhr-fetch.msft.png":::
   <span data-ttu-id="f4e9b-153">日志 `XMLHttpRequest` 和 `Fetch` 请求</span><span class="sxs-lookup"><span data-stu-id="f4e9b-153">Log `XMLHttpRequest` and `Fetch` requests</span></span>  
:::image-end:::  
<span data-ttu-id="f4e9b-154">上图中的顶部消息显示了该 **控制台**的默认分组行为。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-154">The top message in previous figure displays the default grouping behavior of the **Console**.</span></span>  <!--  In the following figure, the same log is displayed after [disabling message grouping](#disable-message-grouping).  -->  

<!--  
> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> :::image type="complex" source="../media/console-xhr-fetch-all.msft.png" alt-text="How the logged XMLHttpRequest and Fetch requests look after ungrouping" lightbox="../media/console-xhr-fetch-all.msft.png":::
>    How the logged XMLHttpRequest and Fetch requests look after ungrouping  
> :::image-end:::  
-->  

<!--todo: add example for ungrouping console items  -->  

### <span data-ttu-id="f4e9b-155">跨页面加载保留消息</span><span class="sxs-lookup"><span data-stu-id="f4e9b-155">Persist messages across page loads</span></span>   

<span data-ttu-id="f4e9b-156">默认情况下，无论何时加载新页面，控制台都会被清除。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-156">By default the Console clears whenever you load a new page.</span></span>  <span data-ttu-id="f4e9b-157">若要在每个页面加载期间保持消息，请 [打开控制台设置](#open-console-settings) ，然后启用 " **保留日志** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-157">To persist messages across page loads, [Open Console Settings](#open-console-settings) and then enable the **Preserve Log** checkbox.</span></span>  

### <span data-ttu-id="f4e9b-158">隐藏网络消息</span><span class="sxs-lookup"><span data-stu-id="f4e9b-158">Hide network messages</span></span>   

<span data-ttu-id="f4e9b-159">默认情况下，浏览器将网络消息记录到 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-159">By default the browser logs network messages to the **Console**.</span></span>  <span data-ttu-id="f4e9b-160">在下图中，所选邮件表示 HTTP 状态代码 `429` 。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-160">In the following figure, the selected message represents an HTTP status code of `429`.</span></span>  

:::image type="complex" source="../media/console-show-network.msft.png" alt-text="控制台中的429消息" lightbox="../media/console-show-network.msft.png":::
   <span data-ttu-id="f4e9b-162">`429`**控制台**中的一条消息</span><span class="sxs-lookup"><span data-stu-id="f4e9b-162">A `429` message in the **Console**</span></span>  
:::image-end:::  
<span data-ttu-id="f4e9b-163">要隐藏网络消息，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f4e9b-163">To hide network messages:</span></span>  

1.  <span data-ttu-id="f4e9b-164">[打开控制台设置](#open-console-settings)。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-164">[Open Console Settings](#open-console-settings).</span></span>  
1.  <span data-ttu-id="f4e9b-165">启用 " **隐藏网络** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-165">Enable the **Hide Network** checkbox.</span></span>  
    
## <span data-ttu-id="f4e9b-166">筛选邮件</span><span class="sxs-lookup"><span data-stu-id="f4e9b-166">Filter messages</span></span>   

<span data-ttu-id="f4e9b-167">可通过多种方式在控制台中筛选出消息。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-167">There are many ways to filter out messages in the Console.</span></span>  

### <span data-ttu-id="f4e9b-168">筛选出浏览器消息</span><span class="sxs-lookup"><span data-stu-id="f4e9b-168">Filter out browser messages</span></span>   

<span data-ttu-id="f4e9b-169">[打开控制台侧栏](#open-the-console-sidebar) ，然后单击 " **用户消息** "，仅显示来自页面 JavaScript 的消息。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-169">[Open the Console Sidebar](#open-the-console-sidebar) and click **User Messages** to only show messages that came from the JavaScript of the page.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-user-messages.msft.png" alt-text="查看用户消息" lightbox="../media/console-sidebar-drawer-user-messages.msft.png":::
   <span data-ttu-id="f4e9b-171">查看用户消息</span><span class="sxs-lookup"><span data-stu-id="f4e9b-171">View user messages</span></span>  
:::image-end:::  

### <span data-ttu-id="f4e9b-172">按日志级别筛选</span><span class="sxs-lookup"><span data-stu-id="f4e9b-172">Filter by log level</span></span>   

<span data-ttu-id="f4e9b-173">DevTools 为每个 `console.*` 方法分配一个严重级别。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-173">DevTools assigns each `console.*` method a severity level.</span></span>  <span data-ttu-id="f4e9b-174">有4个级别： `Verbose` 、 `Info` 、 `Warning` 和 `Error` 。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-174">There are 4 levels: `Verbose`, `Info`, `Warning`, and `Error`.</span></span>  <span data-ttu-id="f4e9b-175">例如，位于 `console.log()` `Info` 组中，而位于 `console.error()` 组中 `Error` 。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-175">For example, `console.log()` is in the `Info` group, whereas `console.error()` is in the `Error` group.</span></span>  <span data-ttu-id="f4e9b-176">[控制台 API 参考][DevToolsConsoleApi]描述每个适用方法的严重级别。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-176">The [Console API Reference][DevToolsConsoleApi] describes the severity level of each applicable method.</span></span>  <span data-ttu-id="f4e9b-177">浏览器记录到控制台的每条消息也具有严重级别。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-177">Every message that the browser logs to the Console has a severity level too.</span></span>  <span data-ttu-id="f4e9b-178">您可以隐藏不感兴趣的任何级别的邮件。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-178">You may hide any level of messages that you are not interested in.</span></span>  <span data-ttu-id="f4e9b-179">例如，如果只对邮件感兴趣 `Error` ，则可以隐藏其他3个组。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-179">For example, if you are only interested in `Error` messages, you may hide the other 3 groups.</span></span>  

<span data-ttu-id="f4e9b-180">单击 " **日志级别** " 下拉列表以启用或禁用 `Verbose` 、 `Info` 或 "消息" `Warning` `Error` 。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-180">Click the **Log Levels** dropdown to enable or disable `Verbose`, `Info`, `Warning` or `Error` messages.</span></span>  

:::image type="complex" source="../media/console-log-level-default-levels.msft.png" alt-text="日志级别下拉列表" lightbox="../media/console-log-level-default-levels.msft.png":::
   <span data-ttu-id="f4e9b-182">**日志级别**下拉列表</span><span class="sxs-lookup"><span data-stu-id="f4e9b-182">The **Log Levels** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="f4e9b-183">您还可以按日志级别进行筛选，方法是[打开控制台边栏](#open-the-console-sidebar)，然后单击 "**错误**"、"**警告**"、"信息" 或 "**详细\*\*\*\*信息**"。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-183">You may also filter by log level by [opening the Console Sidebar](#open-the-console-sidebar) and then clicking **Errors**, **Warnings**, **Info**, or **Verbose**.</span></span>  

:::image type="complex" source="../media/console-sidebar-warnings.msft.png" alt-text="使用边栏查看警告" lightbox="../media/console-sidebar-warnings.msft.png":::
   <span data-ttu-id="f4e9b-185">使用边栏查看警告</span><span class="sxs-lookup"><span data-stu-id="f4e9b-185">Use the Sidebar to view warnings</span></span>  
:::image-end:::  

### <span data-ttu-id="f4e9b-186">按 URL 筛选邮件</span><span class="sxs-lookup"><span data-stu-id="f4e9b-186">Filter messages by URL</span></span>   

<span data-ttu-id="f4e9b-187">键入 `url:` 后跟 url，仅查看来自该 url 的邮件。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-187">Type `url:` followed by a URL to only view messages that came from that URL.</span></span>  <span data-ttu-id="f4e9b-188">键入 DevTools 后，将 `url:` 显示所有相关的 url。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-188">After you type `url:` DevTools shows all relevant URLs.</span></span>  <span data-ttu-id="f4e9b-189">域也有效。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-189">Domains also work.</span></span>  <span data-ttu-id="f4e9b-190">例如，如果 `https://example.com/a.js` 和 `https://example.com/b.js` 正在记录邮件， `url:https://example.com` 则可让你关注来自这两个脚本的消息。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-190">For example, if `https://example.com/a.js` and `https://example.com/b.js` are logging messages, `url:https://example.com` enables you to focus on the messages from these 2 scripts.</span></span>  

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="URL 筛选器" lightbox="../media/console-filter-text.msft.png":::
   <span data-ttu-id="f4e9b-192">URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="f4e9b-192">A URL filter</span></span>  
:::image-end:::  

<span data-ttu-id="f4e9b-193">键入 `-url:` 以隐藏来自该 URL 的邮件。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-193">Type `-url:` to hide messages from that URL.</span></span>  <span data-ttu-id="f4e9b-194">这称为负 URL 筛选器。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-194">This is called a negative URL filter.</span></span>  

:::image type="complex" source="../media/console-negative-filter-text.msft.png" alt-text="用于隐藏所有与 URL 匹配的邮件的负 URL 筛选器 https://b.wal.co" lightbox="../media/console-negative-filter-text.msft.png":::
   <span data-ttu-id="f4e9b-196">用于隐藏所有与 URL 匹配的邮件的负 URL 筛选器 `https://b.wal.co`</span><span class="sxs-lookup"><span data-stu-id="f4e9b-196">A negative URL filter that hides all messages that match the `https://b.wal.co` URL</span></span>
:::image-end:::  

<span data-ttu-id="f4e9b-197">您还可以通过 [打开控制台边栏](#open-the-console-sidebar)，展开 " **用户消息** " 部分，然后单击包含要对其进行焦点的邮件的脚本的 URL，显示来自单个 URL 的邮件。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-197">You may also show messages from a single URL by [opening the Console Sidebar](#open-the-console-sidebar), expanding the **User Messages** section, and then clicking the URL of the script containing the messages on which you want to focus.</span></span>  

:::image type="complex" source="../media/console-filter-text-specified.msft.png" alt-text="查看来自 wp-ad.min.js 的邮件" lightbox="../media/console-filter-text-specified.msft.png":::
   <span data-ttu-id="f4e9b-199">查看来自的邮件</span><span class="sxs-lookup"><span data-stu-id="f4e9b-199">View the messages that came from</span></span> `wp-ad.min.js`  
:::image-end:::  

### <span data-ttu-id="f4e9b-200">筛选出来自不同上下文的消息</span><span class="sxs-lookup"><span data-stu-id="f4e9b-200">Filter out messages from different contexts</span></span>   

<span data-ttu-id="f4e9b-201">假设您的页面上有广告 (广告 ) 。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-201">Suppose that you have an advertisement \(ad\) on your page.</span></span>  <span data-ttu-id="f4e9b-202">广告嵌入在中 `<iframe>` ，并且会在您的控制台中生成大量消息。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-202">The ad is embedded in an `<iframe>` and is generating a lot of messages in your Console.</span></span>  <span data-ttu-id="f4e9b-203">由于广告在不同的 [JavaScript 上下文](#select-javascript-context)中运行，因此隐藏消息的一种方法是 [打开控制台设置](#open-console-settings) 并启用 " **仅限选定的上下文** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-203">Because the ad is running in a different [JavaScript context](#select-javascript-context), one way to hide the messages is to [open Console Settings](#open-console-settings) and enable the **Selected Context Only** checkbox.</span></span>  

### <span data-ttu-id="f4e9b-204">筛选出与正则表达式模式不匹配的消息</span><span class="sxs-lookup"><span data-stu-id="f4e9b-204">Filter out messages that do not match a regular expression pattern</span></span>   

<span data-ttu-id="f4e9b-205">`/[gm][ta][mi]/`在 "**筛选器**" 文本框中键入正则表达式，以筛选出与该模式不匹配的任何消息。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-205">Type a regular expression such as `/[gm][ta][mi]/` in the **Filter** text box to filter out any messages that do not match that pattern.</span></span>  <span data-ttu-id="f4e9b-206">DevTools 检查是否在消息文本或导致消息被记录的脚本中找到该模式。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-206">DevTools checks if the pattern is found in the message text or the script that caused the message to be logged.</span></span>  

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="筛选出与正则表达式不匹配的任何消息" lightbox="../media/console-filter-regex.msft.png":::
   <span data-ttu-id="f4e9b-208">筛选出与 regex 表达式不匹配的任何消息 `/[gm][ta][mi]/`</span><span class="sxs-lookup"><span data-stu-id="f4e9b-208">Filter out any messages that do not match the `/[gm][ta][mi]/` regex expression</span></span>  
:::image-end:::  

## <span data-ttu-id="f4e9b-209">运行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="f4e9b-209">Run JavaScript</span></span>   

<span data-ttu-id="f4e9b-210">本部分包含与在控制台中运行 JavaScript 相关的功能。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-210">This section contains features related to running JavaScript in the Console.</span></span>  <span data-ttu-id="f4e9b-211">请参阅运行参与练习的 [JavaScript][DevToolsConsoleOverviewJavascript] 。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-211">See [Run JavaScript][DevToolsConsoleOverviewJavascript] for a hands-on walkthrough.</span></span>  

### <span data-ttu-id="f4e9b-212">重新运行历史记录中的表达式</span><span class="sxs-lookup"><span data-stu-id="f4e9b-212">Re-run expressions from history</span></span>   

<span data-ttu-id="f4e9b-213">按下 `Up Arrow` 键，循环浏览你之前在控制台中运行的 JavaScript 表达式的历史记录。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-213">Press the `Up Arrow` key to cycle through the history of JavaScript expressions that you ran earlier in the Console.</span></span>  <span data-ttu-id="f4e9b-214">按键 `Enter` 再次运行该表达式。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-214">Press `Enter` to run that expression again.</span></span>  

### <span data-ttu-id="f4e9b-215">使用实时表达式实时监视表达式的值</span><span class="sxs-lookup"><span data-stu-id="f4e9b-215">Watch the value of an expression in real-time with Live Expressions</span></span>   

<span data-ttu-id="f4e9b-216">如果您发现自己在控制台中重复键入相同的 JavaScript 表达式，您可能会发现创建 **实时表达式**变得更容易。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-216">If you find yourself typing the same JavaScript expression in the Console repeatedly, you may find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="f4e9b-217">使用 **实时表达式** ，您只需要键入一个表达式，然后将其固定到您的控制台顶部。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-217">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span></span>  <span data-ttu-id="f4e9b-218">表达式的值几乎实时更新。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-218">The value of the expression updates in near real-time.</span></span>  <span data-ttu-id="f4e9b-219">请参阅 [实时在实时表达式中观看 JavaScript 表达式值][DevToolsConsoleLiveExpressions]。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-219">See [Watch JavaScript Expression Values In Real-Time With Live Expressions][DevToolsConsoleLiveExpressions].</span></span>  

### <span data-ttu-id="f4e9b-220">禁用热情评估</span><span class="sxs-lookup"><span data-stu-id="f4e9b-220">Disable Eager Evaluation</span></span>   

<span data-ttu-id="f4e9b-221">当您在控制台中键入 JavaScript 表达式时， **预先计算** 会显示该表达式的返回值的预览。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-221">As you type JavaScript expressions in the Console, **Eager Evaluation** shows a preview of the return value for that expression.</span></span>  <span data-ttu-id="f4e9b-222">[打开 "控制台设置](#open-console-settings) " 并禁用 " **预先评估** " 复选框以关闭返回值预览。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-222">[Open Console Settings](#open-console-settings) and disable the **Eager Evaluation** checkbox to turn off the return value previews.</span></span>  

### <span data-ttu-id="f4e9b-223">禁用历史记录中的自动完成</span><span class="sxs-lookup"><span data-stu-id="f4e9b-223">Disable autocomplete from history</span></span>   

<span data-ttu-id="f4e9b-224">当您键入表达式时，控制台的 "自动完成" 弹出窗口将显示您之前运行的表达式。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-224">As you type out an expression, the autocomplete popup window for the Console shows expressions that you ran earlier.</span></span>  <span data-ttu-id="f4e9b-225">这些表达式前置 `>` 字符。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-225">These expressions are prepended with the `>` character.</span></span>  <span data-ttu-id="f4e9b-226">[打开 "控制台设置](#open-console-settings) " 并禁用 " **从历史记录自动完成** " 复选框以停止显示历史记录中的表达式。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-226">[Open Console Settings](#open-console-settings) and disable the **Autocomplete From History** checkbox to stop showing expressions from your history.</span></span>  

> [!NOTE]
> <span data-ttu-id="f4e9b-227">在下图中， `document.querySelector('a')` `document.querySelector('img')` 是之前计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-227">In the following figure, `document.querySelector('a')` and `document.querySelector('img')` are expressions that were evaluated earlier.</span></span>  

:::image type="complex" source="../media/console-filter-text-autofilter-history.msft.png" alt-text=""自动完成" 弹出窗口显示历史记录中的表达式" lightbox="../media/console-filter-text-autofilter-history.msft.png":::
   <span data-ttu-id="f4e9b-229">"自动完成" 弹出窗口显示历史记录中的表达式</span><span class="sxs-lookup"><span data-stu-id="f4e9b-229">The autocomplete popup displays expressions from history</span></span>  
:::image-end:::  

### <span data-ttu-id="f4e9b-230">选择 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="f4e9b-230">Select JavaScript context</span></span>   

<span data-ttu-id="f4e9b-231">默认情况下， **JavaScript 上下文** 下拉列表设置为 " **页首**"，这表示主文档的 [浏览上下文][MDNBrowsingContext] 。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-231">By default the **JavaScript Context** dropdown is set to **top**, which represents the [browsing context][MDNBrowsingContext] of the main document.</span></span>  

:::image type="complex" source="../media/console-dom-level-top.msft.png" alt-text="JavaScript 上下文下拉列表" lightbox="../media/console-dom-level-top.msft.png":::
   <span data-ttu-id="f4e9b-233">**JavaScript 上下文**下拉列表</span><span class="sxs-lookup"><span data-stu-id="f4e9b-233">The **JavaScript Context** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="f4e9b-234">假设您的页面上有一个嵌入的广告 `<iframe>` 。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-234">Suppose you have an ad on your page embedded in an `<iframe>`.</span></span>  <span data-ttu-id="f4e9b-235">你希望运行 JavaScript，以便调整广告的 DOM。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-235">You want to run JavaScript in order to tweak the DOM of the ad.</span></span>  <span data-ttu-id="f4e9b-236">应首先从 **JavaScript 上下文** 下拉列表中选择广告的浏览上下文。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-236">You should first select the browsing context of the ad from the **JavaScript Context** dropdown.</span></span>  

:::image type="complex" source="../media/console-dom-level-multiple.msft.png" alt-text="选择其他 JavaScript 上下文" lightbox="../media/console-dom-level-multiple.msft.png":::
   <span data-ttu-id="f4e9b-238">选择其他 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="f4e9b-238">Select a different JavaScript context</span></span>  
:::image-end:::  

## <span data-ttu-id="f4e9b-239">清除控制台</span><span class="sxs-lookup"><span data-stu-id="f4e9b-239">Clear the Console</span></span>   

<span data-ttu-id="f4e9b-240">你可以使用以下任何工作流来清除控制台：</span><span class="sxs-lookup"><span data-stu-id="f4e9b-240">You may use any of the following workflows to clear the Console:</span></span>  

*   <span data-ttu-id="f4e9b-241">单击 " **清除控制台** \ (![ 清除控制台 ][ImageClearConsoleIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-241">Click **Clear Console** \(![Clear Console][ImageClearConsoleIcon]\).</span></span>  
*   <span data-ttu-id="f4e9b-242">右键单击一条消息，然后选择 " **清除控制台**"。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-242">Right-click a message and then select **Clear Console**.</span></span>  
*   <span data-ttu-id="f4e9b-243">`clear()`在控制台中键入，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-243">Type `clear()` in the Console and then press `Enter`.</span></span>  
*   <span data-ttu-id="f4e9b-244">`console.clear()`从你的网页的 JavaScript 调用。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-244">Call `console.clear()` from the JavaScript for your webpage.</span></span>  
*   <span data-ttu-id="f4e9b-245">`Control` + `L` 控制台处于焦点状态时按键。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-245">Press `Control`+`L` while the Console is in focus.</span></span>  
    
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
> <span data-ttu-id="f4e9b-255">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-255">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f4e9b-256">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-256">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f4e9b-258">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f4e9b-258">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
