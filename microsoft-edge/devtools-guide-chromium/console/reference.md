---
description: 有关与 Microsoft Edge DevTools 中的控制台 UI 相关的每个功能和行为的全面参考。
title: 控制台参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: d6fed1681e64f8f57c2e577017d623039a7b4152
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
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

# <a name="console-reference"></a><span data-ttu-id="6b5a0-104">控制台参考</span><span class="sxs-lookup"><span data-stu-id="6b5a0-104">Console reference</span></span>  

<span data-ttu-id="6b5a0-105">此页面引用了与 Microsoft Edge DevTools 控制台相关的功能。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-105">This page is a reference of features related to the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="6b5a0-106">它假定你已经熟悉使用控制台查看记录的消息和运行 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-106">It assumes that you are already familiar with using the Console to view logged messages and run JavaScript.</span></span>  <span data-ttu-id="6b5a0-107">如果情况并非如此，请导航至[开始在控制台中运行 JavaScript 入门][DevToolsConsoleJavascript]和[开始在控制台中记录消息][DevToolsConsoleLog]。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-107">If not, navigate to [Get Started With Running JavaScript In The Console][DevToolsConsoleJavascript] and [Get Started With Logging Messages In The Console][DevToolsConsoleLog].</span></span>  

<span data-ttu-id="6b5a0-108">如果要查找对 `console.log()` 等函数的 API 参考，请导航到“[控制台 API 参考][DevToolsConsoleApi]”。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-108">If you are looking for the API reference on functions like `console.log()`, navigate to [Console API Reference][DevToolsConsoleApi].</span></span>  <span data-ttu-id="6b5a0-109">有关 `monitorEvents()` 等函数的参考，请导航到[控制台实用工具 API 参考][DevToolsConsoleUtilities]。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-109">For the reference on functions like `monitorEvents()`, navigate to [Console Utilities API Reference][DevToolsConsoleUtilities].</span></span>  

## <a name="open-the-console"></a><span data-ttu-id="6b5a0-110">打开控制台</span><span class="sxs-lookup"><span data-stu-id="6b5a0-110">Open the Console</span></span>  

<span data-ttu-id="6b5a0-111">你可以将**控制台**作为[上部窗格中的工具](#open-the-console-tool)打开，也可以将其作为[工具箱中的工具](#open-the-console-tool-in-the-drawer)打开。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-111">You may open the **Console** as a [tool in the upper pane](#open-the-console-tool) or as a [tool in the Drawer](#open-the-console-tool-in-the-drawer).</span></span>  

### <a name="open-the-console-tool"></a><span data-ttu-id="6b5a0-112">打开控制台工具</span><span class="sxs-lookup"><span data-stu-id="6b5a0-112">Open the Console tool</span></span>  

<span data-ttu-id="6b5a0-113">选择 `Control`+`Shift`+`J` \(Windows, Linux\) 或 `Command`+`Option`+`J` \(macOS\)。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-113">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  

:::image type="complex" source="../media/console-hello-console.msft.png" alt-text="控制台工具" lightbox="../media/console-hello-console.msft.png":::
   <span data-ttu-id="6b5a0-115">**控制台**工具</span><span class="sxs-lookup"><span data-stu-id="6b5a0-115">The **Console** tool</span></span>  
:::image-end:::  

<span data-ttu-id="6b5a0-116">要从[命令菜单][DevToolsCommandMenu]中打开**控制台**工具，首先请键入 `Console`，然后运行旁边有**面板**徽章的**显示控制台**命令。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-116">To open the **Console** tool from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Panel** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="显示“控制台”面板的命令" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="6b5a0-118">显示“**控制台**”工具的命令</span><span class="sxs-lookup"><span data-stu-id="6b5a0-118">The command to show the **Console** tool</span></span>  
:::image-end:::  

### <a name="open-the-console-tool-in-the-drawer"></a><span data-ttu-id="6b5a0-119">打开工具箱中的控制台工具</span><span class="sxs-lookup"><span data-stu-id="6b5a0-119">Open the Console tool in the Drawer</span></span>  

<span data-ttu-id="6b5a0-120">选择 `Escape` 或选择“**自定义和控制 DevTools**”\(`...`\)，然后选择“**显示控制台工具箱**”。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-120">Select `Escape` or choose **Customize And Control DevTools** \(`...`\) and then choose **Show console drawer**.</span></span>  

:::image type="complex" source="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png" alt-text="显示控制台工具箱" lightbox="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png":::
   **<span data-ttu-id="6b5a0-122">显示控制台工具箱</span><span class="sxs-lookup"><span data-stu-id="6b5a0-122">Show console drawer</span></span>**  
:::image-end:::  

<span data-ttu-id="6b5a0-123">在**控制台**工具打开的情况下，工具箱将在 DevTools 窗口的底部弹出。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-123">The Drawer pops up at the bottom of your DevTools window, with the **Console** tool open.</span></span>  

:::image type="complex" source="../media/console-elements-console-drawer-hello-world.msft.png" alt-text="工具箱中的控制台工具" lightbox="../media/console-elements-console-drawer-hello-world.msft.png":::
   <span data-ttu-id="6b5a0-125">**工具箱**中的**控制台**工具</span><span class="sxs-lookup"><span data-stu-id="6b5a0-125">The **Console** tool in the **Drawer**</span></span>  
:::image-end:::  

<span data-ttu-id="6b5a0-126">要从[命令菜单][DevToolsCommandMenu]中打开**控制台**工具，首先请键入 `Console`，然后运行旁边有**工具箱**徽章的**显示控制台**命令。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-126">To open the **Console** tool from the [Command Menu][DevToolsCommandMenu], start typing `Console` and then run the **Show Console** command that has the **Drawer** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="用于显示工具箱中的 **控制台** 工具的命令" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="6b5a0-128">用于显示**工具箱**中的**控制台**工具的命令</span><span class="sxs-lookup"><span data-stu-id="6b5a0-128">The command to show the **Console** tool in the **Drawer**</span></span>  
:::image-end:::  

### <a name="open-console-settings"></a><span data-ttu-id="6b5a0-129">打开控制台设置</span><span class="sxs-lookup"><span data-stu-id="6b5a0-129">Open Console Settings</span></span>  

<span data-ttu-id="6b5a0-130">选择**控制台设置** \（![控制台设置图标](../media/settings-button-icon.msft.png)\）。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-130">Choose **Console Settings** \(![Console Settings icon](../media/settings-button-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/console-settings-group-similar-empty.msft.png" alt-text="控制台设置" lightbox="../media/console-settings-group-similar-empty.msft.png":::
   **<span data-ttu-id="6b5a0-132">控制台设置</span><span class="sxs-lookup"><span data-stu-id="6b5a0-132">Console Settings</span></span>**  
:::image-end:::  

<span data-ttu-id="6b5a0-133">下面的链接介绍了每个设置：</span><span class="sxs-lookup"><span data-stu-id="6b5a0-133">The links below explain each setting:</span></span>  

*   [**<span data-ttu-id="6b5a0-134">隐藏网络</span><span class="sxs-lookup"><span data-stu-id="6b5a0-134">Hide Network</span></span>**](#hide-network-messages)  
*   [**<span data-ttu-id="6b5a0-135">保留日志</span><span class="sxs-lookup"><span data-stu-id="6b5a0-135">Preserve Log</span></span>**](#persist-messages-across-page-loads)  
*   [**<span data-ttu-id="6b5a0-136">仅选定上下文</span><span class="sxs-lookup"><span data-stu-id="6b5a0-136">Selected Context Only</span></span>**](#filter-out-messages-from-different-contexts)  
*   [**<span data-ttu-id="6b5a0-137">分组类似项</span><span class="sxs-lookup"><span data-stu-id="6b5a0-137">Group Similar</span></span>**](#disable-message-grouping)  
*   [**<span data-ttu-id="6b5a0-138">记录 XmlHttpRequest</span><span class="sxs-lookup"><span data-stu-id="6b5a0-138">Log XmlHttpRequests</span></span>**](#log-xhr-and-fetch-requests)  
*   [**<span data-ttu-id="6b5a0-139">预先评估</span><span class="sxs-lookup"><span data-stu-id="6b5a0-139">Eager Evaluation</span></span>**](#disable-eager-evaluation)  
*   [**<span data-ttu-id="6b5a0-140">从历史记录中自动完成</span><span class="sxs-lookup"><span data-stu-id="6b5a0-140">Autocomplete From History</span></span>**](#disable-autocomplete-from-history)  
    
### <a name="open-the-console-sidebar"></a><span data-ttu-id="6b5a0-141">打开控制台边栏</span><span class="sxs-lookup"><span data-stu-id="6b5a0-141">Open the Console Sidebar</span></span>  

<span data-ttu-id="6b5a0-142">选择“**显示控制台边栏**”\（![显示控制台边栏](../media/show-console-sidebar-icon.msft.png)\）以显示边栏，该边栏可用于进行筛选。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-142">Choose **Show Console Sidebar** \(![Show Console Sidebar](../media/show-console-sidebar-icon.msft.png)\) to show the Sidebar, which is useful for filtering.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-empty.msft.png" alt-text="控制台边栏" lightbox="../media/console-sidebar-drawer-empty.msft.png":::
   <span data-ttu-id="6b5a0-144">**控制台**边栏</span><span class="sxs-lookup"><span data-stu-id="6b5a0-144">**Console** Sidebar</span></span>  
:::image-end:::  

## <a name="view-messages"></a><span data-ttu-id="6b5a0-145">查看消息</span><span class="sxs-lookup"><span data-stu-id="6b5a0-145">View messages</span></span>  

<span data-ttu-id="6b5a0-146">此部分包含更改消息在控制台中的显示方式的功能。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-146">This section contains features that change how messages are presented in the Console.</span></span>  <span data-ttu-id="6b5a0-147">有关实际操作演练，请导航到“[查看消息][DevToolsConsoleViewMessages]”。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-147">For a hands-on walkthrough, navigate to [View messages][DevToolsConsoleViewMessages].</span></span>  

### <a name="disable-message-grouping"></a><span data-ttu-id="6b5a0-148">禁用消息分组</span><span class="sxs-lookup"><span data-stu-id="6b5a0-148">Disable message grouping</span></span>  

<span data-ttu-id="6b5a0-149">[打开控制台设置](#open-console-settings)，然后禁用“**分组类似项**”以禁用控制台的默认消息分组行为。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-149">[Open Console Settings](#open-console-settings) and disable **Group similar** to disable the default message grouping behavior of the Console.</span></span>  <span data-ttu-id="6b5a0-150">例如，导航到“[记录 XHR 和 Fetch 请求](#log-xhr-and-fetch-requests)”。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-150">For an example, navigate to [Log XHR and Fetch requests](#log-xhr-and-fetch-requests).</span></span>  

### <a name="log-xhr-and-fetch-requests"></a><span data-ttu-id="6b5a0-151">记录 XHR 和 Fetch 请求</span><span class="sxs-lookup"><span data-stu-id="6b5a0-151">Log XHR and Fetch requests</span></span>  

<span data-ttu-id="6b5a0-152">[打开控制台设置](#open-console-settings)，然后启用“**记录 XMLHttpRequest**”以将所有 `XMLHttpRequest` 和 `Fetch` 请求记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-152">[Open Console Settings](#open-console-settings) and enable **Log XMLHttpRequests** to log all `XMLHttpRequest` and `Fetch` requests to the Console as they happen.</span></span>  

:::image type="complex" source="../media/console-xhr-fetch.msft.png" alt-text="记录 XMLHttpRequest 和 Fetch 请求" lightbox="../media/console-xhr-fetch.msft.png":::
   <span data-ttu-id="6b5a0-154">记录 `XMLHttpRequest` 和 `Fetch` 请求</span><span class="sxs-lookup"><span data-stu-id="6b5a0-154">Log `XMLHttpRequest` and `Fetch` requests</span></span>  
:::image-end:::  
<span data-ttu-id="6b5a0-155">上图中的顶部消息显示了**控制台**的默认分组行为。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-155">The top message in previous figure displays the default grouping behavior of the **Console**.</span></span>  <!--  In the following figure, the same log is displayed after [disabling message grouping](#disable-message-grouping).  -->  

<!--  
> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> :::image type="complex" source="../media/console-xhr-fetch-all.msft.png" alt-text="How the logged XMLHttpRequest and Fetch requests look after ungrouping" lightbox="../media/console-xhr-fetch-all.msft.png":::
>    How the logged XMLHttpRequest and Fetch requests look after ungrouping  
> :::image-end:::  
-->  

<!--todo: add example for ungrouping console items  -->  

### <a name="persist-messages-across-page-loads"></a><span data-ttu-id="6b5a0-156">跨页面加载保留消息</span><span class="sxs-lookup"><span data-stu-id="6b5a0-156">Persist messages across page loads</span></span>  

<span data-ttu-id="6b5a0-157">默认情况下，每次加载新页面时，控制台都会清除。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-157">By default the Console clears whenever you load a new page.</span></span>  <span data-ttu-id="6b5a0-158">若要跨页面加载保留消息，请[打开控制台设置](#open-console-settings)，然后启用“**保留日志**”复选框。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-158">To persist messages across page loads, [Open Console Settings](#open-console-settings) and then enable the **Preserve Log** checkbox.</span></span>  

### <a name="hide-network-messages"></a><span data-ttu-id="6b5a0-159">隐藏网络消息</span><span class="sxs-lookup"><span data-stu-id="6b5a0-159">Hide network messages</span></span>  

<span data-ttu-id="6b5a0-160">默认情况下，浏览器会将网络消息记录到**控制台**。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-160">By default the browser logs network messages to the **Console**.</span></span>  <span data-ttu-id="6b5a0-161">在下图中，选定的消息表示 `429` 的 HTTP 状态代码。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-161">In the following figure, the selected message represents an HTTP status code of `429`.</span></span>  

:::image type="complex" source="../media/console-show-network.msft.png" alt-text="控制台中的 429 消息" lightbox="../media/console-show-network.msft.png":::
   <span data-ttu-id="6b5a0-163">**控制台**中的 `429` 消息</span><span class="sxs-lookup"><span data-stu-id="6b5a0-163">A `429` message in the **Console**</span></span>  
:::image-end:::  
<span data-ttu-id="6b5a0-164">隐藏网络消息：</span><span class="sxs-lookup"><span data-stu-id="6b5a0-164">To hide network messages:</span></span>  

1.  <span data-ttu-id="6b5a0-165">[打开控制台设置](#open-console-settings)。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-165">[Open Console Settings](#open-console-settings).</span></span>  
1.  <span data-ttu-id="6b5a0-166">启用“**隐藏网络**”复选框。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-166">Enable the **Hide Network** checkbox.</span></span>  
    
## <a name="filter-messages"></a><span data-ttu-id="6b5a0-167">筛选消息</span><span class="sxs-lookup"><span data-stu-id="6b5a0-167">Filter messages</span></span>  

<span data-ttu-id="6b5a0-168">有许多方法可以筛选出控制台中的消息。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-168">There are many ways to filter out messages in the Console.</span></span>  

### <a name="filter-out-browser-messages"></a><span data-ttu-id="6b5a0-169">筛选出浏览器消息</span><span class="sxs-lookup"><span data-stu-id="6b5a0-169">Filter out browser messages</span></span>  

<span data-ttu-id="6b5a0-170">[打开控制台边栏](#open-the-console-sidebar)，然后选择“**用户消息**”，以仅显示来自页面 JavaScript 的消息。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-170">[Open the Console Sidebar](#open-the-console-sidebar) and choose **User Messages** to only show messages that came from the JavaScript of the page.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-user-messages.msft.png" alt-text="查看用户消息" lightbox="../media/console-sidebar-drawer-user-messages.msft.png":::
   <span data-ttu-id="6b5a0-172">查看用户消息</span><span class="sxs-lookup"><span data-stu-id="6b5a0-172">View user messages</span></span>  
:::image-end:::  

### <a name="filter-by-log-level"></a><span data-ttu-id="6b5a0-173">按日志级别筛选</span><span class="sxs-lookup"><span data-stu-id="6b5a0-173">Filter by log level</span></span>  

<span data-ttu-id="6b5a0-174">DevTools 为每个 `console.*` 方法分配一个严重性级别。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-174">DevTools assigns each `console.*` method a severity level.</span></span>  <span data-ttu-id="6b5a0-175">有 4 个级别：`Verbose`、`Info`、`Warning` 和 `Error`。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-175">There are 4 levels: `Verbose`, `Info`, `Warning`, and `Error`.</span></span>  <span data-ttu-id="6b5a0-176">例如，`console.log()` 位于 `Info` 组中，而 `console.error()` 位于 `Error` 组中。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-176">For example, `console.log()` is in the `Info` group, whereas `console.error()` is in the `Error` group.</span></span>  <span data-ttu-id="6b5a0-177">[控制台 API 参考][DevToolsConsoleApi]介绍了每种适用方法的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-177">The [Console API Reference][DevToolsConsoleApi] describes the severity level of each applicable method.</span></span>  <span data-ttu-id="6b5a0-178">浏览器记录到控制台的每条消息也具有严重性级别。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-178">Every message that the browser logs to the Console has a severity level too.</span></span>  <span data-ttu-id="6b5a0-179">你可以隐藏不感兴趣的任何级别的消息。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-179">You may hide any level of messages that you are not interested in.</span></span>  <span data-ttu-id="6b5a0-180">例如，如果你只对 `Error` 消息感兴趣，则可以隐藏其他 3 个组。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-180">For example, if you are only interested in `Error` messages, you may hide the other 3 groups.</span></span>  

<span data-ttu-id="6b5a0-181">选择“**日志级别**”下拉列表以启用或禁用 `Verbose`、`Info`、`Warning` 或 `Error` 消息。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-181">Choose the **Log Levels** dropdown to enable or disable `Verbose`, `Info`, `Warning` or `Error` messages.</span></span>  

:::image type="complex" source="../media/console-log-level-default-levels.msft.png" alt-text="“日志级别”下拉列表" lightbox="../media/console-log-level-default-levels.msft.png":::
   <span data-ttu-id="6b5a0-183">“**日志级别**”下拉列表</span><span class="sxs-lookup"><span data-stu-id="6b5a0-183">The **Log Levels** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="6b5a0-184">也可以按日志级别进行筛选，方法为[打开控制台边栏](#open-the-console-sidebar)，然后选择“**错误**”、“**警告**”、“**信息**”或“**详细**”。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-184">You may also filter by log level by [opening the Console Sidebar](#open-the-console-sidebar) and thenchoosing **Errors**, **Warnings**, **Info**, or **Verbose**.</span></span>  

:::image type="complex" source="../media/console-sidebar-warnings.msft.png" alt-text="使用边栏查看警告" lightbox="../media/console-sidebar-warnings.msft.png":::
   <span data-ttu-id="6b5a0-186">使用边栏查看警告</span><span class="sxs-lookup"><span data-stu-id="6b5a0-186">Use the Sidebar to view warnings</span></span>  
:::image-end:::  

### <a name="filter-messages-by-url"></a><span data-ttu-id="6b5a0-187">按 URL 筛选消息</span><span class="sxs-lookup"><span data-stu-id="6b5a0-187">Filter messages by URL</span></span>  

<span data-ttu-id="6b5a0-188">键入 `url:` 后跟 URL，以便仅查看来自该 URL 的邮件。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-188">Type `url:` followed by a URL to only view messages that came from that URL.</span></span>  <span data-ttu-id="6b5a0-189">键入 `url:` DevTools 后，会显示所有相关 URL。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-189">After you type `url:` DevTools shows all relevant URLs.</span></span>  <span data-ttu-id="6b5a0-190">也可以使用域。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-190">Domains also work.</span></span>  <span data-ttu-id="6b5a0-191">例如，如果 `https://example.com/a.js` 和 `https://example.com/b.js` 正在记录消息，则使用 `url:https://example.com` 可以专注于这 2 个脚本中的消息。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-191">For example, if `https://example.com/a.js` and `https://example.com/b.js` are logging messages, `url:https://example.com` enables you to focus on the messages from these 2 scripts.</span></span>  

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="URL 筛选器" lightbox="../media/console-filter-text.msft.png":::
   <span data-ttu-id="6b5a0-193">URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="6b5a0-193">A URL filter</span></span>  
:::image-end:::  

<span data-ttu-id="6b5a0-194">键入 `-url:` 可隐藏该 URL 中的消息。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-194">Type `-url:` to hide messages from that URL.</span></span>  <span data-ttu-id="6b5a0-195">这称为负 URL 筛选器。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-195">This is called a negative URL filter.</span></span>  

:::image type="complex" source="../media/console-negative-filter-text.msft.png" alt-text="隐藏与 https://b.wal.co URL 匹配的所有消息的负 URL 筛选器" lightbox="../media/console-negative-filter-text.msft.png":::
   <span data-ttu-id="6b5a0-197">隐藏与 `https://b.wal.co` URL 匹配的所有消息的负 URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="6b5a0-197">A negative URL filter that hides all messages that match the `https://b.wal.co` URL</span></span>
:::image-end:::  

<span data-ttu-id="6b5a0-198">还可以通过以下方法显示来自单个 URL 的消息：[打开控制台边栏](#open-the-console-sidebar)，展开“**用户消息**”部分，然后选择包含要关注的消息的脚本的 URL。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-198">You may also show messages from a single URL by [opening the Console Sidebar](#open-the-console-sidebar), expanding the **User Messages** section, and thenchoosing the URL of the script containing the messages on which you want to focus.</span></span>  

:::image type="complex" source="../media/console-filter-text-specified.msft.png" alt-text="查看来自 wp-ad.min.js 的消息" lightbox="../media/console-filter-text-specified.msft.png":::
   <span data-ttu-id="6b5a0-200">查看来自以下对象的邮件</span><span class="sxs-lookup"><span data-stu-id="6b5a0-200">View the messages that came from</span></span> `wp-ad.min.js`  
:::image-end:::  

### <a name="filter-out-messages-from-different-contexts"></a><span data-ttu-id="6b5a0-201">筛选出不同上下文的消息</span><span class="sxs-lookup"><span data-stu-id="6b5a0-201">Filter out messages from different contexts</span></span>  

<span data-ttu-id="6b5a0-202">假设你的页面有一个广告\（广告\）。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-202">Suppose that you have an advertisement \(ad\) on your page.</span></span>  <span data-ttu-id="6b5a0-203">该广告嵌入在 `<iframe>` 中，并在你的控制台中生成大量消息。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-203">The ad is embedded in an `<iframe>` and is generating a lot of messages in your Console.</span></span>  <span data-ttu-id="6b5a0-204">由于广告在不同的 [JavaScript 上下文](#select-javascript-context)中运行，因此隐藏消息的一种方法是[打开控制台设置](#open-console-settings)，然后打开“**仅选定上下文**”复选框。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-204">Because the ad is running in a different [JavaScript context](#select-javascript-context), one way to hide the messages is to [open Console Settings](#open-console-settings) and turn on the **Selected Context Only** checkbox.</span></span>  

### <a name="filter-out-messages-that-do-not-match-a-regular-expression-pattern"></a><span data-ttu-id="6b5a0-205">筛选出与正则表达式模式不匹配的邮件</span><span class="sxs-lookup"><span data-stu-id="6b5a0-205">Filter out messages that do not match a regular expression pattern</span></span>  

<span data-ttu-id="6b5a0-206">在“**筛选器**”文本框中键入正则表达式（如 `/[gm][ta][mi]/`），以筛选出任何与该模式不匹配的消息。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-206">Type a regular expression such as `/[gm][ta][mi]/` in the **Filter** text box to filter out any messages that do not match that pattern.</span></span>  <span data-ttu-id="6b5a0-207">DevTools 会检查在消息文本或导致记录消息的脚本中是否找到了该模式。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-207">DevTools checks if the pattern is found in the message text or the script that caused the message to be logged.</span></span>  

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="筛选出任何与正则表达式不匹配的消息" lightbox="../media/console-filter-regex.msft.png":::
   <span data-ttu-id="6b5a0-209">筛选出任何与正则表达式不匹配 `/[gm][ta][mi]/` 的消息</span><span class="sxs-lookup"><span data-stu-id="6b5a0-209">Filter out any messages that do not match the `/[gm][ta][mi]/` regex expression</span></span>  
:::image-end:::  

## <a name="run-javascript"></a><span data-ttu-id="6b5a0-210">运行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="6b5a0-210">Run JavaScript</span></span>  

<span data-ttu-id="6b5a0-211">本部分包含与在控制台中运行 JavaScript 相关的功能。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-211">This section contains features related to running JavaScript in the Console.</span></span>  <span data-ttu-id="6b5a0-212">有关实际操作演练，请导航到“[运行 JavaScript][DevToolsConsoleOverviewJavascript]”。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-212">For a hands-on walkthrough, navigate to [Run JavaScript][DevToolsConsoleOverviewJavascript].</span></span>  

### <a name="re-run-expressions-from-history"></a><span data-ttu-id="6b5a0-213">从历史记录中重新运行表达式</span><span class="sxs-lookup"><span data-stu-id="6b5a0-213">Re-run expressions from history</span></span>  

<span data-ttu-id="6b5a0-214">选择 `Up Arrow` 键可循环浏览先前在控制台中运行的 JavaScript 表达式的历史记录。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-214">Select the `Up Arrow` key to cycle through the history of JavaScript expressions that you ran earlier in the Console.</span></span>  <span data-ttu-id="6b5a0-215">选择 `Enter` 可再次运行该表达式。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-215">Select `Enter` to run that expression again.</span></span>  

### <a name="watch-the-value-of-an-expression-in-real-time-with-live-expressions"></a><span data-ttu-id="6b5a0-216">使用实时表达式实时观看表达式的值</span><span class="sxs-lookup"><span data-stu-id="6b5a0-216">Watch the value of an expression in real-time with Live Expressions</span></span>  

<span data-ttu-id="6b5a0-217">如果发现自己在控制台中重复键入相同的JavaScript表达式，则可能会发现创建**实时表达式**更容易。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-217">If you find yourself typing the same JavaScript expression in the Console repeatedly, you may find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="6b5a0-218">使用**实时表达式**键入表达式一次，然后将其固定到控制台顶部。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-218">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span></span>  <span data-ttu-id="6b5a0-219">表达式的值几乎实时更新。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-219">The value of the expression updates in near real-time.</span></span>  <span data-ttu-id="6b5a0-220">导航到“[使用实时表达式实时观看 JavaScript 表达式的值][DevToolsConsoleLiveExpressions]”。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-220">Navigate to [Watch JavaScript Expression Values In Real-Time With Live Expressions][DevToolsConsoleLiveExpressions].</span></span>  

### <a name="disable-eager-evaluation"></a><span data-ttu-id="6b5a0-221">禁用预先评估</span><span class="sxs-lookup"><span data-stu-id="6b5a0-221">Disable Eager Evaluation</span></span>  

<span data-ttu-id="6b5a0-222">在控制台中键入 JavaScript 表达式时，“**预先评估**”会显示该表达式的返回值的预览。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-222">As you type JavaScript expressions in the Console, **Eager Evaluation** shows a preview of the return value for that expression.</span></span>  <span data-ttu-id="6b5a0-223">[打开控制台设置](#open-console-settings)并禁用“**预先评估**”复选框以关闭返回值预览。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-223">[Open Console Settings](#open-console-settings) and disable the **Eager Evaluation** checkbox to turn off the return value previews.</span></span>  

### <a name="disable-autocomplete-from-history"></a><span data-ttu-id="6b5a0-224">禁用从历史记录中自动完成</span><span class="sxs-lookup"><span data-stu-id="6b5a0-224">Disable autocomplete from history</span></span>  

<span data-ttu-id="6b5a0-225">键入表达式时，控制台的自动完成弹出窗口会显示之前运行的表达式。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-225">As you type out an expression, the autocomplete popup window for the Console shows expressions that you ran earlier.</span></span>  <span data-ttu-id="6b5a0-226">这些表达式以 `>` 字符开头。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-226">These expressions are prepended with the `>` character.</span></span>  <span data-ttu-id="6b5a0-227">[打开控制台设置](#open-console-settings)，然后禁用“**从历史记录中自动完成**”复选框，以停止从历史记录中显示表达式。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-227">[Open Console Settings](#open-console-settings) and disable the **Autocomplete From History** checkbox to stop showing expressions from your history.</span></span>  

> [!NOTE]
> <span data-ttu-id="6b5a0-228">在下图中，`document.querySelector('a')` 和 `document.querySelector('img')` 是之前评估的表达式。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-228">In the following figure, `document.querySelector('a')` and `document.querySelector('img')` are expressions that were evaluated earlier.</span></span>  

:::image type="complex" source="../media/console-filter-text-autofilter-history.msft.png" alt-text="自动完成弹出窗口显示历史记录中的表达式" lightbox="../media/console-filter-text-autofilter-history.msft.png":::
   <span data-ttu-id="6b5a0-230">自动完成弹出窗口显示历史记录中的表达式</span><span class="sxs-lookup"><span data-stu-id="6b5a0-230">The autocomplete popup displays expressions from history</span></span>  
:::image-end:::  

### <a name="select-javascript-context"></a><span data-ttu-id="6b5a0-231">选择 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="6b5a0-231">Select JavaScript context</span></span>  

<span data-ttu-id="6b5a0-232">默认情况下，“**JavaScript 上下文**”下拉列表设置为“**顶部**”，表示主文档的[浏览上下文][MDNBrowsingContext]。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-232">By default the **JavaScript Context** dropdown is set to **top**, which represents the [browsing context][MDNBrowsingContext] of the main document.</span></span>  

:::image type="complex" source="../media/console-dom-level-top.msft.png" alt-text="“JavaScript 上下文”下拉列表" lightbox="../media/console-dom-level-top.msft.png":::
   <span data-ttu-id="6b5a0-234">“**JavaScript 上下文**”下拉列表</span><span class="sxs-lookup"><span data-stu-id="6b5a0-234">The **JavaScript Context** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="6b5a0-235">假设页面上有一个嵌入在 `<iframe>` 中的广告。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-235">Suppose you have an ad on your page embedded in an `<iframe>`.</span></span>  <span data-ttu-id="6b5a0-236">你想要运行 JavaScript 以调整广告的 DOM。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-236">You want to run JavaScript in order to tweak the DOM of the ad.</span></span>  <span data-ttu-id="6b5a0-237">应先从“**JavaScript 上下文**”下拉列表中选择广告的浏览上下文。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-237">You should first select the browsing context of the ad from the **JavaScript Context** dropdown.</span></span>  

:::image type="complex" source="../media/console-dom-level-multiple.msft.png" alt-text="选择其他 JavaScript 上下文" lightbox="../media/console-dom-level-multiple.msft.png":::
   <span data-ttu-id="6b5a0-239">选择其他 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="6b5a0-239">Choose a different JavaScript context</span></span>  
:::image-end:::  

## <a name="clear-the-console"></a><span data-ttu-id="6b5a0-240">清除控制台</span><span class="sxs-lookup"><span data-stu-id="6b5a0-240">Clear the Console</span></span>  

<span data-ttu-id="6b5a0-241">可以使用以下任一工作流清除控制台：</span><span class="sxs-lookup"><span data-stu-id="6b5a0-241">You may use any of the following workflows to clear the Console:</span></span>  

*   <span data-ttu-id="6b5a0-242">选择“**清除控制台**”\（清除控制台![ ](../media/clear-console-button-icon.msft.png) \）。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-242">Choose **Clear Console** \(![Clear Console](../media/clear-console-button-icon.msft.png)\).</span></span>  
*   <span data-ttu-id="6b5a0-243">将鼠标悬停在消息上，打开上下文菜单\（右键单击\），然后选择“**清除控制台**”。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-243">Hover on a message, open the contextual menu \(righ-click\), and choose **Clear Console**.</span></span>  
*   <span data-ttu-id="6b5a0-244">在**控制台**中输入 `clear()`，然后选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-244">Enter `clear()` in the **Console** and select `Enter`.</span></span>  
*   <span data-ttu-id="6b5a0-245">从 JavaScript 中为你的网页运行 `console.clear()`。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-245">Run `console.clear()` from the JavaScript for your webpage.</span></span>  
*   <span data-ttu-id="6b5a0-246">在聚焦**控制台**时选择 `Control`+`L`。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-246">Select `Control`+`L` while the **Console** is in focus.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="6b5a0-247">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="6b5a0-247">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行命令 | Microsoft Docs"  
[DevToolsConsoleViewMessages]: ./index.md#viewing-logged-messages "查看记录的消息 - 控制台概述 | Microsoft Docs"  
[DevToolsConsoleApi]: ./api.md "控制台 API 参考 | Microsoft Docs"  
[DevToolsConsoleOverviewJavascript]: ./index.md#running-javascript "运行 JavaScript - 控制台概述 | Microsoft Docs"  
[DevToolsConsoleJavascript]: ./javascript.md "开始在控制台中运行 JavaScript |Microsoft Docs"  
[DevToolsConsoleLiveExpressions]: ./live-expressions.md "使用实时表达式实时观看 JavaScript 表达式的值 | Microsoft Docs"  
[DevToolsConsoleLog]: ./log.md "开始在控制台中记录消息 | Microsoft Docs"  
[DevToolsConsoleUtilities]: ./utilities.md "控制台实用程序 API 参考 | Microsoft Docs"  

[MDNBrowsingContext]: https://developer.mozilla.org/docs/Glossary/Browsing_context "浏览上下文 | MDN"  

> [!NOTE]
> <span data-ttu-id="6b5a0-257">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-257">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6b5a0-258">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-258">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="6b5a0-260">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="6b5a0-260">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
