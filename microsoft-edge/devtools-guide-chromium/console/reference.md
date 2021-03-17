---
description: 有关与 Microsoft Edge DevTools 中的控制台 UI 相关的每个功能和行为的全面参考。
title: 控制台参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: d6fed1681e64f8f57c2e577017d623039a7b4152
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439365"
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

# <a name="console-reference"></a><span data-ttu-id="13ef2-104">控制台参考</span><span class="sxs-lookup"><span data-stu-id="13ef2-104">Console reference</span></span>  

<span data-ttu-id="13ef2-105">此页面引用了与 Microsoft Edge DevTools 控制台相关的功能。</span><span class="sxs-lookup"><span data-stu-id="13ef2-105">This page is a reference of features related to the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="13ef2-106">它假定你已熟悉使用控制台查看记录的消息并运行 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="13ef2-106">It assumes that you are already familiar with using the Console to view logged messages and run JavaScript.</span></span>  <span data-ttu-id="13ef2-107">如果没有，请导航到"开始在控制台中运行[JavaScript"][DevToolsConsoleJavascript]和"开始在控制台中[记录消息"。][DevToolsConsoleLog]</span><span class="sxs-lookup"><span data-stu-id="13ef2-107">If not, navigate to [Get Started With Running JavaScript In The Console][DevToolsConsoleJavascript] and [Get Started With Logging Messages In The Console][DevToolsConsoleLog].</span></span>  

<span data-ttu-id="13ef2-108">如果要查找对函数（如 ）的 API 引用，请 `console.log()` 导航到"[控制台 API 参考"。][DevToolsConsoleApi]</span><span class="sxs-lookup"><span data-stu-id="13ef2-108">If you are looking for the API reference on functions like `console.log()`, navigate to [Console API Reference][DevToolsConsoleApi].</span></span>  <span data-ttu-id="13ef2-109">For the reference on functions like `monitorEvents()` ， navigate to Console [Utilities API Reference][DevToolsConsoleUtilities].</span><span class="sxs-lookup"><span data-stu-id="13ef2-109">For the reference on functions like `monitorEvents()`, navigate to [Console Utilities API Reference][DevToolsConsoleUtilities].</span></span>  

## <a name="open-the-console"></a><span data-ttu-id="13ef2-110">打开控制台</span><span class="sxs-lookup"><span data-stu-id="13ef2-110">Open the Console</span></span>  

<span data-ttu-id="13ef2-111">你可以将 **控制台作为** 工具在上 [窗格中打开，](#open-the-console-tool) 也可以作为 [工具在"箱"中打开](#open-the-console-tool-in-the-drawer)。</span><span class="sxs-lookup"><span data-stu-id="13ef2-111">You may open the **Console** as a [tool in the upper pane](#open-the-console-tool) or as a [tool in the Drawer](#open-the-console-tool-in-the-drawer).</span></span>  

### <a name="open-the-console-tool"></a><span data-ttu-id="13ef2-112">打开控制台工具</span><span class="sxs-lookup"><span data-stu-id="13ef2-112">Open the Console tool</span></span>  

<span data-ttu-id="13ef2-113">选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="13ef2-113">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  

:::image type="complex" source="../media/console-hello-console.msft.png" alt-text="控制台工具" lightbox="../media/console-hello-console.msft.png":::
   <span data-ttu-id="13ef2-115">控制台**工具**</span><span class="sxs-lookup"><span data-stu-id="13ef2-115">The **Console** tool</span></span>  
:::image-end:::  

<span data-ttu-id="13ef2-116">若要从命令**菜单**打开控制台工具[][DevToolsCommandMenu]，请开始键入，然后运行旁边有面板锁屏提醒的显示 `Console` 控制台\*\*\*\* 命令。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="13ef2-116">To open the **Console** tool from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Panel** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="显示控制台面板的命令" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="13ef2-118">显示控制台 **工具** 的命令</span><span class="sxs-lookup"><span data-stu-id="13ef2-118">The command to show the **Console** tool</span></span>  
:::image-end:::  

### <a name="open-the-console-tool-in-the-drawer"></a><span data-ttu-id="13ef2-119">在"箱"中打开控制台工具</span><span class="sxs-lookup"><span data-stu-id="13ef2-119">Open the Console tool in the Drawer</span></span>  

<span data-ttu-id="13ef2-120">选择 `Escape` 或选择 **自定义和控制开发工具** \ (`...` \) ，然后选择显示 **控制台箱**。</span><span class="sxs-lookup"><span data-stu-id="13ef2-120">Select `Escape` or choose **Customize And Control DevTools** \(`...`\) and then choose **Show console drawer**.</span></span>  

:::image type="complex" source="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png" alt-text="显示控制台箱" lightbox="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png":::
   **<span data-ttu-id="13ef2-122">显示控制台箱</span><span class="sxs-lookup"><span data-stu-id="13ef2-122">Show console drawer</span></span>**  
:::image-end:::  

<span data-ttu-id="13ef2-123">The Drawer pops up at the bottom of your DevTools window， with the **Console** tool open.</span><span class="sxs-lookup"><span data-stu-id="13ef2-123">The Drawer pops up at the bottom of your DevTools window, with the **Console** tool open.</span></span>  

:::image type="complex" source="../media/console-elements-console-drawer-hello-world.msft.png" alt-text=""箱"中的控制台工具" lightbox="../media/console-elements-console-drawer-hello-world.msft.png":::
   <span data-ttu-id="13ef2-125">" **箱** "中的控制台 **工具**</span><span class="sxs-lookup"><span data-stu-id="13ef2-125">The **Console** tool in the **Drawer**</span></span>  
:::image-end:::  

<span data-ttu-id="13ef2-126">若要从命令**菜单**打开控制台工具[][DevToolsCommandMenu]，请开始键入，然后运行旁边有"箱"锁屏提醒的"显示 `Console` 控制台"命令。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="13ef2-126">To open the **Console** tool from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Drawer** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="在"箱"中显示 **Console** 工具的命令" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="13ef2-128">在"箱" **中显示** 控制台工具 **的命令**</span><span class="sxs-lookup"><span data-stu-id="13ef2-128">The command to show the **Console** tool in the **Drawer**</span></span>  
:::image-end:::  

### <a name="open-console-settings"></a><span data-ttu-id="13ef2-129">打开控制台设置</span><span class="sxs-lookup"><span data-stu-id="13ef2-129">Open Console Settings</span></span>  

<span data-ttu-id="13ef2-130">Choose **Console Settings** \ (Console Settings icon ![ ](../media/settings-button-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="13ef2-130">Choose **Console Settings** \(![Console Settings icon](../media/settings-button-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/console-settings-group-similar-empty.msft.png" alt-text="控制台设置" lightbox="../media/console-settings-group-similar-empty.msft.png":::
   **<span data-ttu-id="13ef2-132">控制台设置</span><span class="sxs-lookup"><span data-stu-id="13ef2-132">Console Settings</span></span>**  
:::image-end:::  

<span data-ttu-id="13ef2-133">下面的链接说明了每个设置：</span><span class="sxs-lookup"><span data-stu-id="13ef2-133">The links below explain each setting:</span></span>  

*   [**<span data-ttu-id="13ef2-134">隐藏网络</span><span class="sxs-lookup"><span data-stu-id="13ef2-134">Hide Network</span></span>**](#hide-network-messages)  
*   [**<span data-ttu-id="13ef2-135">保留日志</span><span class="sxs-lookup"><span data-stu-id="13ef2-135">Preserve Log</span></span>**](#persist-messages-across-page-loads)  
*   [**<span data-ttu-id="13ef2-136">仅选定上下文</span><span class="sxs-lookup"><span data-stu-id="13ef2-136">Selected Context Only</span></span>**](#filter-out-messages-from-different-contexts)  
*   [**<span data-ttu-id="13ef2-137">Group Similar</span><span class="sxs-lookup"><span data-stu-id="13ef2-137">Group Similar</span></span>**](#disable-message-grouping)  
*   [**<span data-ttu-id="13ef2-138">Log XmlHttpRequests</span><span class="sxs-lookup"><span data-stu-id="13ef2-138">Log XmlHttpRequests</span></span>**](#log-xhr-and-fetch-requests)  
*   [**<span data-ttu-id="13ef2-139">期待评估</span><span class="sxs-lookup"><span data-stu-id="13ef2-139">Eager Evaluation</span></span>**](#disable-eager-evaluation)  
*   [**<span data-ttu-id="13ef2-140">从历史记录自动完成</span><span class="sxs-lookup"><span data-stu-id="13ef2-140">Autocomplete From History</span></span>**](#disable-autocomplete-from-history)  
    
### <a name="open-the-console-sidebar"></a><span data-ttu-id="13ef2-141">打开控制台边栏</span><span class="sxs-lookup"><span data-stu-id="13ef2-141">Open the Console Sidebar</span></span>  

<span data-ttu-id="13ef2-142">选择 **"显示控制台边** 栏 \ (显示 ![ 控制台边栏 ](../media/show-console-sidebar-icon.msft.png) \) "可显示用于筛选的边栏。</span><span class="sxs-lookup"><span data-stu-id="13ef2-142">Choose **Show Console Sidebar** \(![Show Console Sidebar](../media/show-console-sidebar-icon.msft.png)\) to show the Sidebar, which is useful for filtering.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-empty.msft.png" alt-text="控制台边栏" lightbox="../media/console-sidebar-drawer-empty.msft.png":::
   <span data-ttu-id="13ef2-144">**控制台** 边栏</span><span class="sxs-lookup"><span data-stu-id="13ef2-144">**Console** Sidebar</span></span>  
:::image-end:::  

## <a name="view-messages"></a><span data-ttu-id="13ef2-145">查看邮件</span><span class="sxs-lookup"><span data-stu-id="13ef2-145">View messages</span></span>  

<span data-ttu-id="13ef2-146">此部分包含更改消息在控制台中的显示方式的功能。</span><span class="sxs-lookup"><span data-stu-id="13ef2-146">This section contains features that change how messages are presented in the Console.</span></span>  <span data-ttu-id="13ef2-147">有关实际操作演练，请导航到"[查看邮件"。][DevToolsConsoleViewMessages]</span><span class="sxs-lookup"><span data-stu-id="13ef2-147">For a hands-on walkthrough, navigate to [View messages][DevToolsConsoleViewMessages].</span></span>  

### <a name="disable-message-grouping"></a><span data-ttu-id="13ef2-148">禁用邮件分组</span><span class="sxs-lookup"><span data-stu-id="13ef2-148">Disable message grouping</span></span>  

<span data-ttu-id="13ef2-149">[打开"控制台](#open-console-settings) 设置"并禁用 **"组** "，类似于禁用控制台的默认邮件分组行为。</span><span class="sxs-lookup"><span data-stu-id="13ef2-149">[Open Console Settings](#open-console-settings) and disable **Group similar** to disable the default message grouping behavior of the Console.</span></span>  <span data-ttu-id="13ef2-150">例如，导航到"[日志 XHR"和"提取请求"。](#log-xhr-and-fetch-requests)</span><span class="sxs-lookup"><span data-stu-id="13ef2-150">For an example, navigate to [Log XHR and Fetch requests](#log-xhr-and-fetch-requests).</span></span>  

### <a name="log-xhr-and-fetch-requests"></a><span data-ttu-id="13ef2-151">记录 XHR 和提取请求</span><span class="sxs-lookup"><span data-stu-id="13ef2-151">Log XHR and Fetch requests</span></span>  

<span data-ttu-id="13ef2-152">[打开"控制台](#open-console-settings) 设置"并启用 **Log XMLHttpRequests，** 以在它们出现时将全部和 `XMLHttpRequest` `Fetch` 请求记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="13ef2-152">[Open Console Settings](#open-console-settings) and enable **Log XMLHttpRequests** to log all `XMLHttpRequest` and `Fetch` requests to the Console as they happen.</span></span>  

:::image type="complex" source="../media/console-xhr-fetch.msft.png" alt-text="Log XMLHttpRequest 和 Fetch 请求" lightbox="../media/console-xhr-fetch.msft.png":::
   <span data-ttu-id="13ef2-154">日志 `XMLHttpRequest` `Fetch` 和请求</span><span class="sxs-lookup"><span data-stu-id="13ef2-154">Log `XMLHttpRequest` and `Fetch` requests</span></span>  
:::image-end:::  
<span data-ttu-id="13ef2-155">上图中的顶部消息显示控制台 的默认分组 **行为**。</span><span class="sxs-lookup"><span data-stu-id="13ef2-155">The top message in previous figure displays the default grouping behavior of the **Console**.</span></span>  <!--  In the following figure, the same log is displayed after [disabling message grouping](#disable-message-grouping).  -->  

<!--  
> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> :::image type="complex" source="../media/console-xhr-fetch-all.msft.png" alt-text="How the logged XMLHttpRequest and Fetch requests look after ungrouping" lightbox="../media/console-xhr-fetch-all.msft.png":::
>    How the logged XMLHttpRequest and Fetch requests look after ungrouping  
> :::image-end:::  
-->  

<!--todo: add example for ungrouping console items  -->  

### <a name="persist-messages-across-page-loads"></a><span data-ttu-id="13ef2-156">跨页面加载保留消息</span><span class="sxs-lookup"><span data-stu-id="13ef2-156">Persist messages across page loads</span></span>  

<span data-ttu-id="13ef2-157">默认情况下，每次加载新页面时，控制台都会清除。</span><span class="sxs-lookup"><span data-stu-id="13ef2-157">By default the Console clears whenever you load a new page.</span></span>  <span data-ttu-id="13ef2-158">若要跨页面加载保留消息，请 [打开"控制台设置](#open-console-settings) "，然后启用" **保留日志"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="13ef2-158">To persist messages across page loads, [Open Console Settings](#open-console-settings) and then enable the **Preserve Log** checkbox.</span></span>  

### <a name="hide-network-messages"></a><span data-ttu-id="13ef2-159">隐藏网络消息</span><span class="sxs-lookup"><span data-stu-id="13ef2-159">Hide network messages</span></span>  

<span data-ttu-id="13ef2-160">默认情况下，浏览器将网络消息记录到 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="13ef2-160">By default the browser logs network messages to the **Console**.</span></span>  <span data-ttu-id="13ef2-161">在下图中，选定的消息表示 的 HTTP 状态代码 `429` 。</span><span class="sxs-lookup"><span data-stu-id="13ef2-161">In the following figure, the selected message represents an HTTP status code of `429`.</span></span>  

:::image type="complex" source="../media/console-show-network.msft.png" alt-text="控制台中的 429 消息" lightbox="../media/console-show-network.msft.png":::
   <span data-ttu-id="13ef2-163">`429`控制台中的**消息**</span><span class="sxs-lookup"><span data-stu-id="13ef2-163">A `429` message in the **Console**</span></span>  
:::image-end:::  
<span data-ttu-id="13ef2-164">隐藏网络消息：</span><span class="sxs-lookup"><span data-stu-id="13ef2-164">To hide network messages:</span></span>  

1.  <span data-ttu-id="13ef2-165">[打开控制台设置](#open-console-settings)。</span><span class="sxs-lookup"><span data-stu-id="13ef2-165">[Open Console Settings](#open-console-settings).</span></span>  
1.  <span data-ttu-id="13ef2-166">启用" **隐藏网络"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="13ef2-166">Enable the **Hide Network** checkbox.</span></span>  
    
## <a name="filter-messages"></a><span data-ttu-id="13ef2-167">筛选邮件</span><span class="sxs-lookup"><span data-stu-id="13ef2-167">Filter messages</span></span>  

<span data-ttu-id="13ef2-168">有许多方法可以筛选掉控制台中的邮件。</span><span class="sxs-lookup"><span data-stu-id="13ef2-168">There are many ways to filter out messages in the Console.</span></span>  

### <a name="filter-out-browser-messages"></a><span data-ttu-id="13ef2-169">筛选掉浏览器消息</span><span class="sxs-lookup"><span data-stu-id="13ef2-169">Filter out browser messages</span></span>  

<span data-ttu-id="13ef2-170">[打开控制台边栏并选择](#open-the-console-sidebar) " **用户消息** "，以仅显示来自页面的 JavaScript 的消息。</span><span class="sxs-lookup"><span data-stu-id="13ef2-170">[Open the Console Sidebar](#open-the-console-sidebar) and choose **User Messages** to only show messages that came from the JavaScript of the page.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-user-messages.msft.png" alt-text="查看用户消息" lightbox="../media/console-sidebar-drawer-user-messages.msft.png":::
   <span data-ttu-id="13ef2-172">查看用户消息</span><span class="sxs-lookup"><span data-stu-id="13ef2-172">View user messages</span></span>  
:::image-end:::  

### <a name="filter-by-log-level"></a><span data-ttu-id="13ef2-173">按日志级别筛选</span><span class="sxs-lookup"><span data-stu-id="13ef2-173">Filter by log level</span></span>  

<span data-ttu-id="13ef2-174">DevTools 为每个 `console.*` 方法分配一个严重性级别。</span><span class="sxs-lookup"><span data-stu-id="13ef2-174">DevTools assigns each `console.*` method a severity level.</span></span>  <span data-ttu-id="13ef2-175">有 4 个 `Verbose` 级别 `Info` ：、、 `Warning` 和 `Error` 。</span><span class="sxs-lookup"><span data-stu-id="13ef2-175">There are 4 levels: `Verbose`, `Info`, `Warning`, and `Error`.</span></span>  <span data-ttu-id="13ef2-176">例如， `console.log()` 位于 `Info` 组中，而 `console.error()` 位于 `Error` 组中。</span><span class="sxs-lookup"><span data-stu-id="13ef2-176">For example, `console.log()` is in the `Info` group, whereas `console.error()` is in the `Error` group.</span></span>  <span data-ttu-id="13ef2-177">控制台 [API 参考][DevToolsConsoleApi] 介绍了每个适用方法的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="13ef2-177">The [Console API Reference][DevToolsConsoleApi] describes the severity level of each applicable method.</span></span>  <span data-ttu-id="13ef2-178">浏览器记录到控制台的每条消息也具有严重性级别。</span><span class="sxs-lookup"><span data-stu-id="13ef2-178">Every message that the browser logs to the Console has a severity level too.</span></span>  <span data-ttu-id="13ef2-179">您可以隐藏您不感兴趣的任何级别的邮件。</span><span class="sxs-lookup"><span data-stu-id="13ef2-179">You may hide any level of messages that you are not interested in.</span></span>  <span data-ttu-id="13ef2-180">例如，如果只对邮件感兴趣，可以隐藏 `Error` 其他 3 个组。</span><span class="sxs-lookup"><span data-stu-id="13ef2-180">For example, if you are only interested in `Error` messages, you may hide the other 3 groups.</span></span>  

<span data-ttu-id="13ef2-181">选择" **日志级别** "下拉列表以启用或禁用 `Verbose` 、 或 `Info` `Warning` `Error` 消息。</span><span class="sxs-lookup"><span data-stu-id="13ef2-181">Choose the **Log Levels** dropdown to enable or disable `Verbose`, `Info`, `Warning` or `Error` messages.</span></span>  

:::image type="complex" source="../media/console-log-level-default-levels.msft.png" alt-text=""日志级别"下拉列表" lightbox="../media/console-log-level-default-levels.msft.png":::
   <span data-ttu-id="13ef2-183">" **日志级别"** 下拉列表</span><span class="sxs-lookup"><span data-stu-id="13ef2-183">The **Log Levels** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="13ef2-184">也可以按日志级别进行筛选，方法为打开[控制台边](#open-the-console-sidebar)栏，然后选择错误、警告\*\*\*\*、**信息**或**详细**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="13ef2-184">You may also filter by log level by [opening the Console Sidebar](#open-the-console-sidebar) and thenchoosing **Errors**, **Warnings**, **Info**, or **Verbose**.</span></span>  

:::image type="complex" source="../media/console-sidebar-warnings.msft.png" alt-text="使用边栏查看警告" lightbox="../media/console-sidebar-warnings.msft.png":::
   <span data-ttu-id="13ef2-186">使用边栏查看警告</span><span class="sxs-lookup"><span data-stu-id="13ef2-186">Use the Sidebar to view warnings</span></span>  
:::image-end:::  

### <a name="filter-messages-by-url"></a><span data-ttu-id="13ef2-187">按 URL 筛选邮件</span><span class="sxs-lookup"><span data-stu-id="13ef2-187">Filter messages by URL</span></span>  

<span data-ttu-id="13ef2-188">键入 `url:` 后跟 URL，以便仅查看来自该 URL 的邮件。</span><span class="sxs-lookup"><span data-stu-id="13ef2-188">Type `url:` followed by a URL to only view messages that came from that URL.</span></span>  <span data-ttu-id="13ef2-189">键入 `url:` DevTools 后，会显示所有相关 URL。</span><span class="sxs-lookup"><span data-stu-id="13ef2-189">After you type `url:` DevTools shows all relevant URLs.</span></span>  <span data-ttu-id="13ef2-190">域也正常工作。</span><span class="sxs-lookup"><span data-stu-id="13ef2-190">Domains also work.</span></span>  <span data-ttu-id="13ef2-191">例如，如果 `https://example.com/a.js` 和 正在记录消息，则使您能够专注于 `https://example.com/b.js` 这 `url:https://example.com` 2 个脚本中的邮件。</span><span class="sxs-lookup"><span data-stu-id="13ef2-191">For example, if `https://example.com/a.js` and `https://example.com/b.js` are logging messages, `url:https://example.com` enables you to focus on the messages from these 2 scripts.</span></span>  

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="URL 筛选器" lightbox="../media/console-filter-text.msft.png":::
   <span data-ttu-id="13ef2-193">URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="13ef2-193">A URL filter</span></span>  
:::image-end:::  

<span data-ttu-id="13ef2-194">键入 `-url:` 以隐藏该 URL 中的邮件。</span><span class="sxs-lookup"><span data-stu-id="13ef2-194">Type `-url:` to hide messages from that URL.</span></span>  <span data-ttu-id="13ef2-195">这称为负 URL 筛选器。</span><span class="sxs-lookup"><span data-stu-id="13ef2-195">This is called a negative URL filter.</span></span>  

:::image type="complex" source="../media/console-negative-filter-text.msft.png" alt-text="隐藏与 URL 匹配的所有邮件的负 https://b.wal.co URL 筛选器" lightbox="../media/console-negative-filter-text.msft.png":::
   <span data-ttu-id="13ef2-197">隐藏与 URL 匹配的所有邮件的负 `https://b.wal.co` URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="13ef2-197">A negative URL filter that hides all messages that match the `https://b.wal.co` URL</span></span>
:::image-end:::  

<span data-ttu-id="13ef2-198">还可以打开控制台边栏，展开"用户消息[](#open-the-console-sidebar)"部分，然后选择包含要关注的消息\*\*\*\* 的脚本的 URL，从而显示来自单个 URL 的消息。</span><span class="sxs-lookup"><span data-stu-id="13ef2-198">You may also show messages from a single URL by [opening the Console Sidebar](#open-the-console-sidebar), expanding the **User Messages** section, and thenchoosing the URL of the script containing the messages on which you want to focus.</span></span>  

:::image type="complex" source="../media/console-filter-text-specified.msft.png" alt-text="查看来自邮件wp-ad.min.js" lightbox="../media/console-filter-text-specified.msft.png":::
   <span data-ttu-id="13ef2-200">查看来自的邮件</span><span class="sxs-lookup"><span data-stu-id="13ef2-200">View the messages that came from</span></span> `wp-ad.min.js`  
:::image-end:::  

### <a name="filter-out-messages-from-different-contexts"></a><span data-ttu-id="13ef2-201">筛选出不同上下文中的消息</span><span class="sxs-lookup"><span data-stu-id="13ef2-201">Filter out messages from different contexts</span></span>  

<span data-ttu-id="13ef2-202">假设您的页面有一个 (广告\) 广告。</span><span class="sxs-lookup"><span data-stu-id="13ef2-202">Suppose that you have an advertisement \(ad\) on your page.</span></span>  <span data-ttu-id="13ef2-203">广告嵌入在 中 `<iframe>` ，并且正在控制台中生成大量消息。</span><span class="sxs-lookup"><span data-stu-id="13ef2-203">The ad is embedded in an `<iframe>` and is generating a lot of messages in your Console.</span></span>  <span data-ttu-id="13ef2-204">由于广告在不同的[JavaScript](#select-javascript-context)上下文中运行，因此隐藏消息的一个方法就是打开"控制台[](#open-console-settings)设置"并打开"**仅选定上下文"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="13ef2-204">Because the ad is running in a different [JavaScript context](#select-javascript-context), one way to hide the messages is to [open Console Settings](#open-console-settings) and turn on the **Selected Context Only** checkbox.</span></span>  

### <a name="filter-out-messages-that-do-not-match-a-regular-expression-pattern"></a><span data-ttu-id="13ef2-205">筛选出与正则表达式模式不匹配的邮件</span><span class="sxs-lookup"><span data-stu-id="13ef2-205">Filter out messages that do not match a regular expression pattern</span></span>  

<span data-ttu-id="13ef2-206">在"筛选器"文本框中键入正则表达式，以筛选出任何与模式 `/[gm][ta][mi]/` 不匹配的邮件。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="13ef2-206">Type a regular expression such as `/[gm][ta][mi]/` in the **Filter** text box to filter out any messages that do not match that pattern.</span></span>  <span data-ttu-id="13ef2-207">DevTools 检查在消息文本或导致记录消息的脚本中是否找到模式。</span><span class="sxs-lookup"><span data-stu-id="13ef2-207">DevTools checks if the pattern is found in the message text or the script that caused the message to be logged.</span></span>  

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="筛选出任何与正则表达式不匹配的邮件" lightbox="../media/console-filter-regex.msft.png":::
   <span data-ttu-id="13ef2-209">筛选出与正则表达式不匹配 `/[gm][ta][mi]/` 的任何邮件</span><span class="sxs-lookup"><span data-stu-id="13ef2-209">Filter out any messages that do not match the `/[gm][ta][mi]/` regex expression</span></span>  
:::image-end:::  

## <a name="run-javascript"></a><span data-ttu-id="13ef2-210">运行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="13ef2-210">Run JavaScript</span></span>  

<span data-ttu-id="13ef2-211">本部分包含与在控制台中运行 JavaScript 相关的功能。</span><span class="sxs-lookup"><span data-stu-id="13ef2-211">This section contains features related to running JavaScript in the Console.</span></span>  <span data-ttu-id="13ef2-212">有关实际操作演练，请导航到"[运行 JavaScript"。][DevToolsConsoleOverviewJavascript]</span><span class="sxs-lookup"><span data-stu-id="13ef2-212">For a hands-on walkthrough, navigate to [Run JavaScript][DevToolsConsoleOverviewJavascript].</span></span>  

### <a name="re-run-expressions-from-history"></a><span data-ttu-id="13ef2-213">从历史记录重新运行表达式</span><span class="sxs-lookup"><span data-stu-id="13ef2-213">Re-run expressions from history</span></span>  

<span data-ttu-id="13ef2-214">选择要 `Up Arrow` 循环访问之前在控制台中运行 JavaScript 表达式的历史记录的键。</span><span class="sxs-lookup"><span data-stu-id="13ef2-214">Select the `Up Arrow` key to cycle through the history of JavaScript expressions that you ran earlier in the Console.</span></span>  <span data-ttu-id="13ef2-215">选择 `Enter` 以再次运行该表达式。</span><span class="sxs-lookup"><span data-stu-id="13ef2-215">Select `Enter` to run that expression again.</span></span>  

### <a name="watch-the-value-of-an-expression-in-real-time-with-live-expressions"></a><span data-ttu-id="13ef2-216">使用 Live Expressions 实时监视表达式的值</span><span class="sxs-lookup"><span data-stu-id="13ef2-216">Watch the value of an expression in real-time with Live Expressions</span></span>  

<span data-ttu-id="13ef2-217">如果你发现自己在控制台中重复键入相同的 JavaScript 表达式，你可能会发现创建 Live **Expression**更容易。</span><span class="sxs-lookup"><span data-stu-id="13ef2-217">If you find yourself typing the same JavaScript expression in the Console repeatedly, you may find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="13ef2-218">使用 **Live Expressions，** 键入表达式一次，然后将其固定到控制台顶部。</span><span class="sxs-lookup"><span data-stu-id="13ef2-218">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span></span>  <span data-ttu-id="13ef2-219">表达式的值几乎实时更新。</span><span class="sxs-lookup"><span data-stu-id="13ef2-219">The value of the expression updates in near real-time.</span></span>  <span data-ttu-id="13ef2-220">导航到 [使用 Live Expressions Real-Time JavaScript 表达式值][DevToolsConsoleLiveExpressions]。</span><span class="sxs-lookup"><span data-stu-id="13ef2-220">Navigate to [Watch JavaScript Expression Values In Real-Time With Live Expressions][DevToolsConsoleLiveExpressions].</span></span>  

### <a name="disable-eager-evaluation"></a><span data-ttu-id="13ef2-221">禁用期待评估</span><span class="sxs-lookup"><span data-stu-id="13ef2-221">Disable Eager Evaluation</span></span>  

<span data-ttu-id="13ef2-222">在控制台中键入 JavaScript 表达式时 **，"等待** 评估"会显示该表达式的返回值的预览。</span><span class="sxs-lookup"><span data-stu-id="13ef2-222">As you type JavaScript expressions in the Console, **Eager Evaluation** shows a preview of the return value for that expression.</span></span>  <span data-ttu-id="13ef2-223">[打开控制台设置](#open-console-settings) 并禁用 **"期望评估** "复选框以关闭返回值预览。</span><span class="sxs-lookup"><span data-stu-id="13ef2-223">[Open Console Settings](#open-console-settings) and disable the **Eager Evaluation** checkbox to turn off the return value previews.</span></span>  

### <a name="disable-autocomplete-from-history"></a><span data-ttu-id="13ef2-224">禁用历史记录中的自动完成</span><span class="sxs-lookup"><span data-stu-id="13ef2-224">Disable autocomplete from history</span></span>  

<span data-ttu-id="13ef2-225">键入表达式时，控制台的自动完成弹出窗口会显示之前运行表达式。</span><span class="sxs-lookup"><span data-stu-id="13ef2-225">As you type out an expression, the autocomplete popup window for the Console shows expressions that you ran earlier.</span></span>  <span data-ttu-id="13ef2-226">这些表达式在字符前 `>` 预置。</span><span class="sxs-lookup"><span data-stu-id="13ef2-226">These expressions are prepended with the `>` character.</span></span>  <span data-ttu-id="13ef2-227">[打开"控制台](#open-console-settings) 设置"并禁用"自动 **完成自历史记录"** 复选框以停止显示历史记录中的表达式。</span><span class="sxs-lookup"><span data-stu-id="13ef2-227">[Open Console Settings](#open-console-settings) and disable the **Autocomplete From History** checkbox to stop showing expressions from your history.</span></span>  

> [!NOTE]
> <span data-ttu-id="13ef2-228">在下图中， `document.querySelector('a')` `document.querySelector('img')` 和 是之前评估的表达式。</span><span class="sxs-lookup"><span data-stu-id="13ef2-228">In the following figure, `document.querySelector('a')` and `document.querySelector('img')` are expressions that were evaluated earlier.</span></span>  

:::image type="complex" source="../media/console-filter-text-autofilter-history.msft.png" alt-text="自动完成弹出窗口显示历史记录中的表达式" lightbox="../media/console-filter-text-autofilter-history.msft.png":::
   <span data-ttu-id="13ef2-230">自动完成弹出窗口显示历史记录中的表达式</span><span class="sxs-lookup"><span data-stu-id="13ef2-230">The autocomplete popup displays expressions from history</span></span>  
:::image-end:::  

### <a name="select-javascript-context"></a><span data-ttu-id="13ef2-231">选择 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="13ef2-231">Select JavaScript context</span></span>  

<span data-ttu-id="13ef2-232">默认情况下 **，"JavaScript 上下文**"下拉列表设置为**顶部**，表示主文档的[][MDNBrowsingContext]浏览上下文。</span><span class="sxs-lookup"><span data-stu-id="13ef2-232">By default the **JavaScript Context** dropdown is set to **top**, which represents the [browsing context][MDNBrowsingContext] of the main document.</span></span>  

:::image type="complex" source="../media/console-dom-level-top.msft.png" alt-text=""JavaScript 上下文"下拉列表" lightbox="../media/console-dom-level-top.msft.png":::
   <span data-ttu-id="13ef2-234">**"JavaScript 上下文**"下拉列表</span><span class="sxs-lookup"><span data-stu-id="13ef2-234">The **JavaScript Context** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="13ef2-235">假设页面上有一个嵌入在 中的广告 `<iframe>` 。</span><span class="sxs-lookup"><span data-stu-id="13ef2-235">Suppose you have an ad on your page embedded in an `<iframe>`.</span></span>  <span data-ttu-id="13ef2-236">你想要运行 JavaScript 以调整广告的 DOM。</span><span class="sxs-lookup"><span data-stu-id="13ef2-236">You want to run JavaScript in order to tweak the DOM of the ad.</span></span>  <span data-ttu-id="13ef2-237">应首先从"JavaScript 上下文"下拉列表中选择 **广告的浏览** 上下文。</span><span class="sxs-lookup"><span data-stu-id="13ef2-237">You should first select the browsing context of the ad from the **JavaScript Context** dropdown.</span></span>  

:::image type="complex" source="../media/console-dom-level-multiple.msft.png" alt-text="选择其他 JavaScript 上下文" lightbox="../media/console-dom-level-multiple.msft.png":::
   <span data-ttu-id="13ef2-239">选择其他 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="13ef2-239">Choose a different JavaScript context</span></span>  
:::image-end:::  

## <a name="clear-the-console"></a><span data-ttu-id="13ef2-240">清除控制台</span><span class="sxs-lookup"><span data-stu-id="13ef2-240">Clear the Console</span></span>  

<span data-ttu-id="13ef2-241">可以使用以下任一工作流清除控制台：</span><span class="sxs-lookup"><span data-stu-id="13ef2-241">You may use any of the following workflows to clear the Console:</span></span>  

*   <span data-ttu-id="13ef2-242">Choose **Clear Console** \ (Clear Console ![ ](../media/clear-console-button-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="13ef2-242">Choose **Clear Console** \(![Clear Console](../media/clear-console-button-icon.msft.png)\).</span></span>  
*   <span data-ttu-id="13ef2-243">将鼠标悬停在消息上，打开上下文菜单 \ (righ-click\) ，然后选择"**清除控制台"。**</span><span class="sxs-lookup"><span data-stu-id="13ef2-243">Hover on a message, open the contextual menu \(righ-click\), and choose **Clear Console**.</span></span>  
*   <span data-ttu-id="13ef2-244">在 `clear()` 控制台中 **输入 并选择** `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="13ef2-244">Enter `clear()` in the **Console** and select `Enter`.</span></span>  
*   <span data-ttu-id="13ef2-245">从 `console.clear()` JavaScript 中为网页运行。</span><span class="sxs-lookup"><span data-stu-id="13ef2-245">Run `console.clear()` from the JavaScript for your webpage.</span></span>  
*   <span data-ttu-id="13ef2-246">在 `Control` + `L` 控制台**聚焦**时选择。</span><span class="sxs-lookup"><span data-stu-id="13ef2-246">Select `Control`+`L` while the **Console** is in focus.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="13ef2-247">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="13ef2-247">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单菜单运行|Microsoft Docs"  
[DevToolsConsoleViewMessages]: ./index.md#viewing-logged-messages "查看记录的消息 - 控制台概述|Microsoft Docs"  
[DevToolsConsoleApi]: ./api.md "控制台 API 参考|Microsoft Docs"  
[DevToolsConsoleOverviewJavascript]: ./index.md#running-javascript "运行 JavaScript - 控制台概述|Microsoft Docs"  
[DevToolsConsoleJavascript]: ./javascript.md "开始在控制台控制台中运行 JavaScript |Microsoft Docs"  
[DevToolsConsoleLiveExpressions]: ./live-expressions.md "使用 Live Expressions | 实时观看 JavaScript 表达式|Microsoft Docs"  
[DevToolsConsoleLog]: ./log.md "开始在控制台控制台中记录|Microsoft Docs"  
[DevToolsConsoleUtilities]: ./utilities.md "控制台实用程序 API 参考|Microsoft Docs"  

[MDNBrowsingContext]: https://developer.mozilla.org/docs/Glossary/Browsing_context "浏览上下文|MDN"  

> [!NOTE]
> <span data-ttu-id="13ef2-257">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="13ef2-257">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="13ef2-258">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="13ef2-258">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="13ef2-260">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="13ef2-260">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
