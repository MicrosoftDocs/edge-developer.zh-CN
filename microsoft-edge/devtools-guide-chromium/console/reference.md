---
description: 针对开发人员工具中控制台 UI 的每种功能Microsoft Edge全面参考。
title: 控制台参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f14663ca1883c0a81184f9a4fa67ddcbd3f08a24
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564523"
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
# <a name="console-reference"></a><span data-ttu-id="161fd-104">控制台参考</span><span class="sxs-lookup"><span data-stu-id="161fd-104">Console reference</span></span>  

<span data-ttu-id="161fd-105">本文引用了与开发人员工具控制台Microsoft Edge相关的功能。</span><span class="sxs-lookup"><span data-stu-id="161fd-105">This article is a reference of features related to the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="161fd-106">它假定你已熟悉使用控制台查看记录的消息并运行 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="161fd-106">It assumes you're already familiar with using the Console to view logged messages and run JavaScript.</span></span>  <span data-ttu-id="161fd-107">如果没有，请导航到开始在控制台中运行 [JavaScript][DevtoolsConsoleConsoleJavascript] 和 [开始在控制台中记录消息][DevtoolsConsoleConsoleLog]。</span><span class="sxs-lookup"><span data-stu-id="161fd-107">If not, navigate to [Get started with running JavaScript in the Console][DevtoolsConsoleConsoleJavascript] and [Get started with logging messages in the Console][DevtoolsConsoleConsoleLog].</span></span>  

<span data-ttu-id="161fd-108">如果要查找对函数（如 ）的 API 引用，请 `console.log()` 导航到"[控制台 API 参考"。][DevToolsConsoleApi]</span><span class="sxs-lookup"><span data-stu-id="161fd-108">If you're looking for the API reference on functions like `console.log()`, navigate to [Console API Reference][DevToolsConsoleApi].</span></span>  <span data-ttu-id="161fd-109">有关 `monitorEvents()` 等函数的参考，请导航到[控制台实用工具 API 参考][DevToolsConsoleUtilities]。</span><span class="sxs-lookup"><span data-stu-id="161fd-109">For the reference on functions like `monitorEvents()`, navigate to [Console Utilities API Reference][DevToolsConsoleUtilities].</span></span>  

## <a name="open-the-console"></a><span data-ttu-id="161fd-110">打开控制台</span><span class="sxs-lookup"><span data-stu-id="161fd-110">Open the Console</span></span>  

<span data-ttu-id="161fd-111">你可以将**控制台**作为[上部窗格中的工具](#open-the-console-tool)打开，也可以将其作为[工具箱中的工具](#open-the-console-tool-in-the-drawer)打开。</span><span class="sxs-lookup"><span data-stu-id="161fd-111">You may open the **Console** as a [tool in the upper pane](#open-the-console-tool) or as a [tool in the Drawer](#open-the-console-tool-in-the-drawer).</span></span>  

### <a name="open-the-console-tool"></a><span data-ttu-id="161fd-112">打开控制台工具</span><span class="sxs-lookup"><span data-stu-id="161fd-112">Open the Console tool</span></span>  

<span data-ttu-id="161fd-113">选择 `Control`+`Shift`+`J` \(Windows, Linux\) 或 `Command`+`Option`+`J` \(macOS\)。</span><span class="sxs-lookup"><span data-stu-id="161fd-113">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  

:::image type="complex" source="../media/console-hello-console.msft.png" alt-text="控制台工具" lightbox="../media/console-hello-console.msft.png":::
   <span data-ttu-id="161fd-115">**控制台**工具</span><span class="sxs-lookup"><span data-stu-id="161fd-115">The **Console** tool</span></span>  
:::image-end:::  

<span data-ttu-id="161fd-116">若要从命令**菜单**打开控制台工具[][DevtoolsCommandMenuIndex]，请键入 ，然后运行旁边有 `Console` **面板**锁屏提醒的显示控制台命令。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="161fd-116">To open the **Console** tool from the [Command Menu][DevtoolsCommandMenuIndex], type `Console` and then run the **Show Console** command that has the **Panel** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="运行命令以显示控制台工具" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="161fd-118">运行命令以显示 **控制台** 工具</span><span class="sxs-lookup"><span data-stu-id="161fd-118">Run the command to display the **Console** tool</span></span>  
:::image-end:::  

### <a name="open-the-console-tool-in-the-drawer"></a><span data-ttu-id="161fd-119">打开工具箱中的控制台工具</span><span class="sxs-lookup"><span data-stu-id="161fd-119">Open the Console tool in the Drawer</span></span>  

<span data-ttu-id="161fd-120">选择 `Esc` 或选择 **"自定义和控制 DevTools** \(`...` \) "，然后选择"显示控制台**箱"。**</span><span class="sxs-lookup"><span data-stu-id="161fd-120">Select `Esc` or choose **Customize and control DevTools** \(`...`\) and then choose **Show console drawer**.</span></span>  

:::image type="complex" source="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png" alt-text="显示控制台工具箱" lightbox="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png":::
   **<span data-ttu-id="161fd-122">显示控制台工具箱</span><span class="sxs-lookup"><span data-stu-id="161fd-122">Show console drawer</span></span>**  
:::image-end:::  

<span data-ttu-id="161fd-123">在**控制台**工具打开的情况下，工具箱将在 DevTools 窗口的底部弹出。</span><span class="sxs-lookup"><span data-stu-id="161fd-123">The Drawer pops up at the bottom of your DevTools window, with the **Console** tool open.</span></span>  

:::image type="complex" source="../media/console-elements-console-drawer-hello-world.msft.png" alt-text="工具箱中的控制台工具" lightbox="../media/console-elements-console-drawer-hello-world.msft.png":::
   <span data-ttu-id="161fd-125">**“抽屉”** 中的 **控制台** 工具</span><span class="sxs-lookup"><span data-stu-id="161fd-125">The **Console** tool in the **Drawer**</span></span>  
:::image-end:::  

<span data-ttu-id="161fd-126">若要从命令**菜单**打开控制台工具[][DevtoolsCommandMenuIndex]，请键入 ，然后运行旁边有"箱"锁屏提醒的"显示 `Console` 控制台"命令。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="161fd-126">To open the **Console** tool from the [Command Menu][DevtoolsCommandMenuIndex], type `Console` and then run the **Show Console** command that has the **Drawer** badge next to it.</span></span>  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="运行命令以在箱中显示 **Console** 工具" lightbox="../media/console-command-menu-show-console.msft.png":::
   <span data-ttu-id="161fd-128">运行命令以在"箱 **"** 中显示控制台 **工具**</span><span class="sxs-lookup"><span data-stu-id="161fd-128">Run the command to display the **Console** tool in the **Drawer**</span></span>  
:::image-end:::  

### <a name="open-console-settings"></a><span data-ttu-id="161fd-129">打开控制台设置</span><span class="sxs-lookup"><span data-stu-id="161fd-129">Open Console Settings</span></span>  

<span data-ttu-id="161fd-130">Choose the **Console 设置**\(Console 设置 ![ icon ](../media/settings-button-icon.msft.png) \) button.</span><span class="sxs-lookup"><span data-stu-id="161fd-130">Choose the **Console Settings** \(![Console Settings icon](../media/settings-button-icon.msft.png)\) button.</span></span>  

:::image type="complex" source="../media/console-settings-group-similar-empty.msft.png" alt-text="控制台设置" lightbox="../media/console-settings-group-similar-empty.msft.png":::
   **<span data-ttu-id="161fd-132">控制台设置</span><span class="sxs-lookup"><span data-stu-id="161fd-132">Console Settings</span></span>**  
:::image-end:::  

<span data-ttu-id="161fd-133">以下链接说明了每个设置。</span><span class="sxs-lookup"><span data-stu-id="161fd-133">The following links explain each setting.</span></span>  

*   [<span data-ttu-id="161fd-134">隐藏网络</span><span class="sxs-lookup"><span data-stu-id="161fd-134">Hide network</span></span>](#hide-network-messages)  
*   [<span data-ttu-id="161fd-135">保留日志</span><span class="sxs-lookup"><span data-stu-id="161fd-135">Preserve log</span></span>](#persist-messages-across-page-loads)  
*   [<span data-ttu-id="161fd-136">仅选定上下文</span><span class="sxs-lookup"><span data-stu-id="161fd-136">Selected context only</span></span>](#filter-out-messages-from-different-contexts)  
*   [<span data-ttu-id="161fd-137">类似组</span><span class="sxs-lookup"><span data-stu-id="161fd-137">Group similar</span></span>](#turn-off-message-grouping)  
*   [<span data-ttu-id="161fd-138">Log XMLHttpRequests</span><span class="sxs-lookup"><span data-stu-id="161fd-138">Log XMLHttpRequests</span></span>](#log-xhr-and-fetch-requests)  
*   [<span data-ttu-id="161fd-139">期待评估</span><span class="sxs-lookup"><span data-stu-id="161fd-139">Eager evaluation</span></span>](#turn-off-eager-evaluation)  
*   [<span data-ttu-id="161fd-140">从历史记录自动完成</span><span class="sxs-lookup"><span data-stu-id="161fd-140">Autocomplete from history</span></span>](#turn-off-autocomplete-from-history)  
<!--*   Evaluate triggers user activation  -->  
    
### <a name="open-the-console-sidebar"></a><span data-ttu-id="161fd-141">打开控制台边栏</span><span class="sxs-lookup"><span data-stu-id="161fd-141">Open the Console Sidebar</span></span>  

<span data-ttu-id="161fd-142">若要显示 **边栏**，请选择显示 **控制台边** 栏 \(![ 显示控制台边栏 ](../media/show-console-sidebar-icon.msft.png) \) 。</span><span class="sxs-lookup"><span data-stu-id="161fd-142">To display the **Sidebar**, choose **Show console sidebar** \(![Show console sidebar](../media/show-console-sidebar-icon.msft.png)\).</span></span>  <span data-ttu-id="161fd-143">**边栏**可帮助你进行筛选。</span><span class="sxs-lookup"><span data-stu-id="161fd-143">The **Sidebar** is helps you filter.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-empty.msft.png" alt-text="控制台边栏" lightbox="../media/console-sidebar-drawer-empty.msft.png":::
   **<span data-ttu-id="161fd-145">控制台边栏</span><span class="sxs-lookup"><span data-stu-id="161fd-145">Console Sidebar</span></span>**  
:::image-end:::  

## <a name="view-messages"></a><span data-ttu-id="161fd-146">查看消息</span><span class="sxs-lookup"><span data-stu-id="161fd-146">View messages</span></span>  

<span data-ttu-id="161fd-147">此部分包含更改消息在控制台中的显示方式的功能。</span><span class="sxs-lookup"><span data-stu-id="161fd-147">This section contains features that change how messages are presented in the Console.</span></span>  <span data-ttu-id="161fd-148">有关实际操作演练，请导航到“[查看消息][DevtoolsConsoleIndexInspectFilterInformationOnCurrentWebpage]”。</span><span class="sxs-lookup"><span data-stu-id="161fd-148">For a hands-on walkthrough, navigate to [View messages][DevtoolsConsoleIndexInspectFilterInformationOnCurrentWebpage].</span></span>  

### <a name="turn-off-message-grouping"></a><span data-ttu-id="161fd-149">关闭邮件分组</span><span class="sxs-lookup"><span data-stu-id="161fd-149">Turn off message grouping</span></span>  

<span data-ttu-id="161fd-150">若要关闭控制台的默认邮件分组**行为**，请打开控制台[设置并选中](#open-console-settings)类似组**旁边的复选框**。</span><span class="sxs-lookup"><span data-stu-id="161fd-150">To turn off the default message grouping behavior of the **Console**, [open Console Settings](#open-console-settings) and choose the checkbox next to **Group similar**.</span></span>  <span data-ttu-id="161fd-151">例如，导航到“[记录 XHR 和 Fetch 请求](#log-xhr-and-fetch-requests)”。</span><span class="sxs-lookup"><span data-stu-id="161fd-151">For an example, navigate to [Log XHR and Fetch requests](#log-xhr-and-fetch-requests).</span></span>  

### <a name="log-xhr-and-fetch-requests"></a><span data-ttu-id="161fd-152">记录 XHR 和 Fetch 请求</span><span class="sxs-lookup"><span data-stu-id="161fd-152">Log XHR and Fetch requests</span></span>  

<span data-ttu-id="161fd-153">若要在每次发生时将所有和请求记录到控制台，请打开控制台 `XMLHttpRequest` `Fetch` 设置，然后选择 Log **XMLHttpRequests**[旁边的](#open-console-settings)复选框。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="161fd-153">To log all `XMLHttpRequest` and `Fetch` requests to the **Console** as each happens, [open Console Settings](#open-console-settings) and choose the checkbox next to **Log XMLHttpRequests**.</span></span>  

:::image type="complex" source="../media/console-xhr-fetch.msft.png" alt-text="记录 XMLHttpRequest 和 Fetch 请求" lightbox="../media/console-xhr-fetch.msft.png":::
   <span data-ttu-id="161fd-155">记录 `XMLHttpRequest` 和 `Fetch` 请求</span><span class="sxs-lookup"><span data-stu-id="161fd-155">Log `XMLHttpRequest` and `Fetch` requests</span></span>  
:::image-end:::  

<span data-ttu-id="161fd-156">上图中的顶部消息显示了**控制台**的默认分组行为。</span><span class="sxs-lookup"><span data-stu-id="161fd-156">The top message in previous figure displays the default grouping behavior of the **Console**.</span></span>  <!--  In the following figure, the same log is displayed after you [turn off message grouping](#turn-off-message-grouping).  -->  

<!--  
> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> :::image type="complex" source="../media/console-xhr-fetch-all.msft.png" alt-text="How the logged XMLHttpRequest and Fetch requests look after ungrouping" lightbox="../media/console-xhr-fetch-all.msft.png":::
>    How the logged XMLHttpRequest and Fetch requests look after ungrouping  
> :::image-end:::  
-->  

<!--todo: add example for ungrouping console items  -->  

### <a name="persist-messages-across-page-loads"></a><span data-ttu-id="161fd-157">跨页面加载保留消息</span><span class="sxs-lookup"><span data-stu-id="161fd-157">Persist messages across page loads</span></span>  

<span data-ttu-id="161fd-158">加载新网页时，默认操作会清除 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="161fd-158">When you load a new webpage, the default action clears the **Console**.</span></span>  <span data-ttu-id="161fd-159">若要跨页面加载保留消息，请[打开控制台设置](#open-console-settings)并选中"保留日志"旁边的**复选框**。</span><span class="sxs-lookup"><span data-stu-id="161fd-159">To persist messages across page loads, [open Console Settings](#open-console-settings) and choose the checkbox next to **Preserve Log**.</span></span>  

### <a name="hide-network-messages"></a><span data-ttu-id="161fd-160">隐藏网络消息</span><span class="sxs-lookup"><span data-stu-id="161fd-160">Hide network messages</span></span>  

<span data-ttu-id="161fd-161">用户的默认操作Microsoft Edge将网络消息记录到**控制台**。</span><span class="sxs-lookup"><span data-stu-id="161fd-161">The default action for Microsoft Edge is to logs network messages to the **Console**.</span></span>  <span data-ttu-id="161fd-162">在下图中，选择的消息表示 的 HTTP 状态代码 `429` 。</span><span class="sxs-lookup"><span data-stu-id="161fd-162">In the following figure, the chosen message represents an HTTP status code of `429`.</span></span>  

:::image type="complex" source="../media/console-show-network.msft.png" alt-text="控制台中的 429 消息" lightbox="../media/console-show-network.msft.png":::
   <span data-ttu-id="161fd-164">**控制台**中的 `429` 消息</span><span class="sxs-lookup"><span data-stu-id="161fd-164">A `429` message in the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="161fd-165">若要隐藏网络消息，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="161fd-165">To hide network messages, complete the following actions.</span></span>  

1.  <span data-ttu-id="161fd-166">[打开控制台设置](#open-console-settings)。</span><span class="sxs-lookup"><span data-stu-id="161fd-166">[Open Console Settings](#open-console-settings).</span></span>  
1.  <span data-ttu-id="161fd-167">选中隐藏网络旁边的 **复选框**。</span><span class="sxs-lookup"><span data-stu-id="161fd-167">Choose the checkbox next to **Hide Network**.</span></span>  
    
## <a name="filter-messages"></a><span data-ttu-id="161fd-168">筛选邮件</span><span class="sxs-lookup"><span data-stu-id="161fd-168">Filter messages</span></span>  

<span data-ttu-id="161fd-169">有许多方法可以筛选出控制台中的 **邮件**。</span><span class="sxs-lookup"><span data-stu-id="161fd-169">Many ways exist to filter out messages in the **Console**.</span></span>  

### <a name="filter-out-browser-messages"></a><span data-ttu-id="161fd-170">筛选出浏览器消息</span><span class="sxs-lookup"><span data-stu-id="161fd-170">Filter out browser messages</span></span>  

<span data-ttu-id="161fd-171">[打开控制台边栏](#open-the-console-sidebar) 并选择" **# 用户消息** "，以仅显示来自网页的 JavaScript 的消息。</span><span class="sxs-lookup"><span data-stu-id="161fd-171">[Open the Console Sidebar](#open-the-console-sidebar) and choose **# user messages** to only display messages that came from the JavaScript of the webpage.</span></span>  

:::image type="complex" source="../media/console-sidebar-drawer-user-messages.msft.png" alt-text="显示用户消息" lightbox="../media/console-sidebar-drawer-user-messages.msft.png":::
   <span data-ttu-id="161fd-173">显示用户消息</span><span class="sxs-lookup"><span data-stu-id="161fd-173">Display user messages</span></span>  
:::image-end:::  

### <a name="filter-by-log-level"></a><span data-ttu-id="161fd-174">按记录级别筛选</span><span class="sxs-lookup"><span data-stu-id="161fd-174">Filter by log level</span></span>  

<span data-ttu-id="161fd-175">DevTools 为每个方法 `console.*` 分配四个严重性级别之一。</span><span class="sxs-lookup"><span data-stu-id="161fd-175">DevTools assigns each `console.*` method one of the four severity levels.</span></span>  

*   `Error`  
*   `Info`  
*   `Verbose`  
*   `Warning`  
    
<span data-ttu-id="161fd-176">例如， `console.log()` 位于 `Info` 组中，但 `console.error()` 位于 `Error` 组中。</span><span class="sxs-lookup"><span data-stu-id="161fd-176">For example, `console.log()` is in the `Info` group, but `console.error()` is in the `Error` group.</span></span>  <span data-ttu-id="161fd-177">[控制台 API 参考][DevToolsConsoleApi]介绍了每种适用方法的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="161fd-177">The [Console API Reference][DevToolsConsoleApi] describes the severity level of each applicable method.</span></span>  <span data-ttu-id="161fd-178">浏览器记录到控制台的每条消息也具有严重性级别。</span><span class="sxs-lookup"><span data-stu-id="161fd-178">Every message that the browser logs to the Console has a severity level too.</span></span>  <span data-ttu-id="161fd-179">你可以隐藏你不感兴趣的任何级别的邮件。</span><span class="sxs-lookup"><span data-stu-id="161fd-179">You may hide any level of messages that you're not interested in.</span></span>  <span data-ttu-id="161fd-180">例如，如果只对邮件感兴趣，可以隐藏 `Error` 其他三个组。</span><span class="sxs-lookup"><span data-stu-id="161fd-180">For example, if you're only interested in `Error` messages, you may hide the other three groups.</span></span>  

<span data-ttu-id="161fd-181">若要筛选邮件，请选择" **日志级别** "下拉列表，然后选择 `Verbose` `Info` 、、 `Warning` 或 `Error` 。</span><span class="sxs-lookup"><span data-stu-id="161fd-181">To filter the messages, choose the **Log Levels** dropdown and choose `Verbose`, `Info`, `Warning`, or `Error`.</span></span>  

:::image type="complex" source="../media/console-log-level-default-levels.msft.png" alt-text="日志级别下拉列表" lightbox="../media/console-log-level-default-levels.msft.png":::
   <span data-ttu-id="161fd-183">“**日志级别**”下拉列表</span><span class="sxs-lookup"><span data-stu-id="161fd-183">The **Log Levels** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="161fd-184">若要使用日志级别进行筛选，请打开[控制台边](#open-the-console-sidebar)栏，**然后选择错误、** 警告、\*\*\*\*\*\*信息**或**详细\*\*。</span><span class="sxs-lookup"><span data-stu-id="161fd-184">To use the log level to filter, [open the Console Sidebar](#open-the-console-sidebar) and then choose **Errors**, **Warnings**, **Info**, or **Verbose**.</span></span>  

:::image type="complex" source="../media/console-sidebar-warnings.msft.png" alt-text="使用边栏查看警告" lightbox="../media/console-sidebar-warnings.msft.png":::
   <span data-ttu-id="161fd-186">使用边栏查看警告</span><span class="sxs-lookup"><span data-stu-id="161fd-186">Use the Sidebar to view warnings</span></span>  
:::image-end:::  

### <a name="filter-messages-by-url"></a><span data-ttu-id="161fd-187">按 URL 筛选消息</span><span class="sxs-lookup"><span data-stu-id="161fd-187">Filter messages by URL</span></span>  

<span data-ttu-id="161fd-188">键入 `url:` 后跟 URL，以便仅查看来自该 URL 的邮件。</span><span class="sxs-lookup"><span data-stu-id="161fd-188">Type `url:` followed by a URL to only view messages that came from that URL.</span></span>  <span data-ttu-id="161fd-189">键入 后 `url:` ，DevTools 将显示所有相关 URL。</span><span class="sxs-lookup"><span data-stu-id="161fd-189">After you type `url:`, DevTools displays all relevant URLs.</span></span>  <span data-ttu-id="161fd-190">也可以使用域。</span><span class="sxs-lookup"><span data-stu-id="161fd-190">Domains also work.</span></span>  <span data-ttu-id="161fd-191">例如，如果 `https://example.com/a.js` 和 正在记录消息，则你可以专注于 `https://example.com/b.js` `url:https://example.com` 这两个脚本中的消息。</span><span class="sxs-lookup"><span data-stu-id="161fd-191">For example, if `https://example.com/a.js` and `https://example.com/b.js` are logging messages, `url:https://example.com` allows you to focus on the messages from these two scripts.</span></span>  

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="URL 筛选器" lightbox="../media/console-filter-text.msft.png":::
   <span data-ttu-id="161fd-193">URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="161fd-193">A URL filter</span></span>  
:::image-end:::  

<span data-ttu-id="161fd-194">若要隐藏 URL 中的消息，请键入 `-url:` 。</span><span class="sxs-lookup"><span data-stu-id="161fd-194">To hide messages from a URL, type `-url:`.</span></span>  <span data-ttu-id="161fd-195">这是一个负 URL 筛选器。</span><span class="sxs-lookup"><span data-stu-id="161fd-195">It's a negative URL filter.</span></span>  

:::image type="complex" source="../media/console-negative-filter-text.msft.png" alt-text="隐藏与 https://b.wal.co URL 匹配的所有消息的负 URL 筛选器" lightbox="../media/console-negative-filter-text.msft.png":::
   <span data-ttu-id="161fd-197">隐藏与 `https://b.wal.co` URL 匹配的所有消息的负 URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="161fd-197">A negative URL filter that hides all messages that match the `https://b.wal.co` URL</span></span>
:::image-end:::  

<span data-ttu-id="161fd-198">若要显示来自单个 URL 的消息，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="161fd-198">To display messages from a single URL, complete the following actions.</span></span>  

1.  <span data-ttu-id="161fd-199">[打开控制台边栏](#open-the-console-sidebar)。</span><span class="sxs-lookup"><span data-stu-id="161fd-199">[Open the Console Sidebar](#open-the-console-sidebar).</span></span>  
1.  <span data-ttu-id="161fd-200">展开 **" # 用户消息"** 部分。</span><span class="sxs-lookup"><span data-stu-id="161fd-200">Expand the **# user messages** section.</span></span>  
1.  <span data-ttu-id="161fd-201">选择包含要关注的消息的脚本的 URL。</span><span class="sxs-lookup"><span data-stu-id="161fd-201">Choose the URL of the script that contains the messages on which you want to focus.</span></span>  
    
:::image type="complex" source="../media/console-filter-text-specified.msft.png" alt-text="显示来自邮件wp-ad.min.js" lightbox="../media/console-filter-text-specified.msft.png":::
   <span data-ttu-id="161fd-203">显示来自的邮件</span><span class="sxs-lookup"><span data-stu-id="161fd-203">Display the messages that came from</span></span> `wp-ad.min.js`  
:::image-end:::  

### <a name="filter-out-messages-from-different-contexts"></a><span data-ttu-id="161fd-204">筛选出不同上下文的消息</span><span class="sxs-lookup"><span data-stu-id="161fd-204">Filter out messages from different contexts</span></span>  

<span data-ttu-id="161fd-205">假设您网页上有一个 (广告\) 广告。</span><span class="sxs-lookup"><span data-stu-id="161fd-205">Suppose that you have an advertisement \(ad\) on your webpage.</span></span>  <span data-ttu-id="161fd-206">广告嵌入在 中 `<iframe>` ，在控制台 中生成许多 **消息**。</span><span class="sxs-lookup"><span data-stu-id="161fd-206">The ad is embedded in an `<iframe>` and generates many messages in your **Console**.</span></span>  <span data-ttu-id="161fd-207">由于广告在不同的[JavaScript](#choose-javascript-context)上下文中运行，因此隐藏消息的一个方法就是打开控制台设置选中"仅上下文["](#open-console-settings)旁边的**复选框**。</span><span class="sxs-lookup"><span data-stu-id="161fd-207">Because the ad is running in a different [JavaScript context](#choose-javascript-context), one way to hide the messages is to [open Console Settings](#open-console-settings) and choose the checkbox next to **Selected Context Only**.</span></span>  

### <a name="filter-out-messages-that-dont-match-a-regular-expression-pattern"></a><span data-ttu-id="161fd-208">筛选出与正则表达式模式不匹配的邮件</span><span class="sxs-lookup"><span data-stu-id="161fd-208">Filter out messages that don't match a regular expression pattern</span></span>  

<span data-ttu-id="161fd-209">在"筛选器"文本框中键入正则表达式，以筛选出任何与模式 `/[gm][ta][mi]/` 不匹配的邮件。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="161fd-209">Type a regular expression such as `/[gm][ta][mi]/` in the **Filter** textbox to filter out any messages that don't match that pattern.</span></span>  <span data-ttu-id="161fd-210">DevTools 会检查在消息文本或导致记录消息的脚本中是否找到了该模式。</span><span class="sxs-lookup"><span data-stu-id="161fd-210">DevTools checks if the pattern is found in the message text or the script that caused the message to be logged.</span></span>  

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="筛选出与正则表达式不匹配的任何邮件" lightbox="../media/console-filter-regex.msft.png":::
   <span data-ttu-id="161fd-212">筛选出与正则表达式不匹配 `/[gm][ta][mi]/` 的任何邮件</span><span class="sxs-lookup"><span data-stu-id="161fd-212">Filter out any messages that don't match the `/[gm][ta][mi]/` regex expression</span></span>  
:::image-end:::  

## <a name="run-javascript"></a><span data-ttu-id="161fd-213">运行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="161fd-213">Run JavaScript</span></span>  

<span data-ttu-id="161fd-214">本部分包含与在控制台中运行 JavaScript **相关的功能**。</span><span class="sxs-lookup"><span data-stu-id="161fd-214">This section contains features related to running JavaScript in the **Console**.</span></span>  <span data-ttu-id="161fd-215">有关实际操作演练，请导航到“[运行 JavaScript][DevtoolsConsoleConsoleJavascript]”。</span><span class="sxs-lookup"><span data-stu-id="161fd-215">For a hands-on walkthrough, navigate to [Run JavaScript][DevtoolsConsoleConsoleJavascript].</span></span>  

### <a name="rerun-expressions-from-history"></a><span data-ttu-id="161fd-216">从历史记录重新运行表达式</span><span class="sxs-lookup"><span data-stu-id="161fd-216">Rerun expressions from history</span></span>  

<span data-ttu-id="161fd-217">选择 以循环访问之前在控制台 中运行 `Up Arrow` JavaScript 表达式 **的历史记录**。</span><span class="sxs-lookup"><span data-stu-id="161fd-217">Select `Up Arrow` to cycle through the history of JavaScript expressions that you ran earlier in the **Console**.</span></span>  <span data-ttu-id="161fd-218">选择 `Enter` 可再次运行该表达式。</span><span class="sxs-lookup"><span data-stu-id="161fd-218">Select `Enter` to run that expression again.</span></span>  

### <a name="watch-the-value-of-an-expression-in-real-time-with-live-expressions"></a><span data-ttu-id="161fd-219">使用 Live Expressions 实时监视表达式的值</span><span class="sxs-lookup"><span data-stu-id="161fd-219">Watch the value of an expression in real time with Live Expressions</span></span>  

<span data-ttu-id="161fd-220">如果你发现自己在控制台中重复键入相同的 JavaScript 表达式\*\*\*\*，你可能会发现创建 Live **Expression**更容易。</span><span class="sxs-lookup"><span data-stu-id="161fd-220">If you find yourself typing the same JavaScript expression in the **Console** repeatedly, you may find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="161fd-221">使用 **Live Expressions，** 键入表达式一次，然后将其固定到控制台 **的顶部**。</span><span class="sxs-lookup"><span data-stu-id="161fd-221">With **Live Expressions**, you type an expression once and then pin it to the top of your **Console**.</span></span>  <span data-ttu-id="161fd-222">表达式的值几乎可以实时更新。</span><span class="sxs-lookup"><span data-stu-id="161fd-222">The value of the expression updates in near real time.</span></span>  <span data-ttu-id="161fd-223">导航到“[使用实时表达式实时观看 JavaScript 表达式的值][DevToolsConsoleLiveExpressions]”。</span><span class="sxs-lookup"><span data-stu-id="161fd-223">Navigate to [Watch JavaScript Expression Values In Real-Time With Live Expressions][DevToolsConsoleLiveExpressions].</span></span>  

### <a name="turn-off-eager-evaluation"></a><span data-ttu-id="161fd-224">关闭"期待评估"</span><span class="sxs-lookup"><span data-stu-id="161fd-224">Turn off Eager Evaluation</span></span>  

<span data-ttu-id="161fd-225">当您在控制台中键入 JavaScript 表达式时 **，"期待**评估"将显示返回值的**预览**。</span><span class="sxs-lookup"><span data-stu-id="161fd-225">**Eager Evaluation** displays a preview of the return value as you type JavaScript expressions in the **Console**.</span></span>  <span data-ttu-id="161fd-226">若要关闭返回值预览，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="161fd-226">To turn off the return value previews, complete the following actions.</span></span>  

1.  <span data-ttu-id="161fd-227">[打开控制台设置](#open-console-settings)。</span><span class="sxs-lookup"><span data-stu-id="161fd-227">[Open Console Settings](#open-console-settings).</span></span>  
1.  <span data-ttu-id="161fd-228">删除"期望评估" **旁边的复选框**。</span><span class="sxs-lookup"><span data-stu-id="161fd-228">Remove the checkbox next to **Eager Evaluation**.</span></span>  
    
### <a name="turn-off-autocomplete-from-history"></a><span data-ttu-id="161fd-229">从历史记录中关闭自动完成</span><span class="sxs-lookup"><span data-stu-id="161fd-229">Turn off autocomplete from history</span></span>  

<span data-ttu-id="161fd-230">键入表达式时，控制台的自动完成弹出窗口将显示之前运行表达式。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="161fd-230">As you type out an expression, the autocomplete popup window for the **Console** displays expressions that you ran earlier.</span></span>  <span data-ttu-id="161fd-231">表达式使用 字符预先 `>` 绘制。</span><span class="sxs-lookup"><span data-stu-id="161fd-231">The expressions are pre-pended with the `>` character.</span></span>  <span data-ttu-id="161fd-232">若要停止显示历史记录中的表达式，请打开控制台[设置并删除](#open-console-settings)"自动**完成**自历史记录"复选框旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="161fd-232">To stop displaying expressions from your history, [open Console Settings](#open-console-settings) and remove the checkbox next to **Autocomplete From History** checkbox.</span></span>  

> [!NOTE]
> <span data-ttu-id="161fd-233">在下图中，`document.querySelector('a')` 和 `document.querySelector('img')` 是之前评估的表达式。</span><span class="sxs-lookup"><span data-stu-id="161fd-233">In the following figure, `document.querySelector('a')` and `document.querySelector('img')` are expressions that were evaluated earlier.</span></span>  

:::image type="complex" source="../media/console-filter-text-autofilter-history.msft.png" alt-text="自动完成弹出菜单显示历史记录中的表达式" lightbox="../media/console-filter-text-autofilter-history.msft.png":::
   <span data-ttu-id="161fd-235">自动完成弹出菜单显示历史记录中的表达式</span><span class="sxs-lookup"><span data-stu-id="161fd-235">The autocomplete popup menu displays expressions from history</span></span>  
:::image-end:::  

### <a name="choose-javascript-context"></a><span data-ttu-id="161fd-236">选择 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="161fd-236">Choose JavaScript context</span></span>  

<span data-ttu-id="161fd-237">**"JavaScript**上下文"下拉列表的默认选项位于**顶部**，它表示主[网页的浏览][MdnDocsGlossaryBrowsingContext]上下文。</span><span class="sxs-lookup"><span data-stu-id="161fd-237">The default option for the **JavaScript Context** dropdown is **top**, which represents the [browsing context][MdnDocsGlossaryBrowsingContext] of the main webpage.</span></span>  

:::image type="complex" source="../media/console-dom-level-top.msft.png" alt-text="JavaScript 上下文下拉列表" lightbox="../media/console-dom-level-top.msft.png":::
   <span data-ttu-id="161fd-239">“**JavaScript 上下文**”下拉列表</span><span class="sxs-lookup"><span data-stu-id="161fd-239">The **JavaScript Context** dropdown</span></span>  
:::image-end:::  

<span data-ttu-id="161fd-240">假设您的网页中嵌入了一个广告 `<iframe>` 。</span><span class="sxs-lookup"><span data-stu-id="161fd-240">Suppose you have an ad on your webpage embedded in an `<iframe>`.</span></span>  <span data-ttu-id="161fd-241">你想要运行 JavaScript 来调整广告的 DOM。</span><span class="sxs-lookup"><span data-stu-id="161fd-241">You want to run JavaScript to tweak the DOM of the ad.</span></span>  <span data-ttu-id="161fd-242">首先，从"JavaScript 上下文"下拉列表中选择 **广告的浏览** 上下文。</span><span class="sxs-lookup"><span data-stu-id="161fd-242">First, choose the browsing context of the ad from the **JavaScript Context** dropdown.</span></span>  

:::image type="complex" source="../media/console-dom-level-multiple.msft.png" alt-text="选择其他 JavaScript 上下文" lightbox="../media/console-dom-level-multiple.msft.png":::
   <span data-ttu-id="161fd-244">选择其他 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="161fd-244">Choose a different JavaScript context</span></span>  
:::image-end:::  

## <a name="clear-the-console"></a><span data-ttu-id="161fd-245">清除控制台</span><span class="sxs-lookup"><span data-stu-id="161fd-245">Clear the Console</span></span>  

<span data-ttu-id="161fd-246">若要清除 **控制台**，请完成以下任何工作流。</span><span class="sxs-lookup"><span data-stu-id="161fd-246">To clear the **Console**, complete any of the following workflows.</span></span>  

*   <span data-ttu-id="161fd-247">选择" **清除控制台** \(![ 清除控制台 ](../media/clear-console-button-icon.msft.png) \) "按钮。</span><span class="sxs-lookup"><span data-stu-id="161fd-247">Choose the **Clear Console** \(![Clear Console](../media/clear-console-button-icon.msft.png)\) button.</span></span>  
*   <span data-ttu-id="161fd-248">将鼠标悬停在消息上，打开上下文菜单 \(右键单击\) ，然后选择"清除**控制台"。**</span><span class="sxs-lookup"><span data-stu-id="161fd-248">Hover on a message, open the contextual menu \(right-click\), and choose **Clear Console**.</span></span>  
*   <span data-ttu-id="161fd-249">在**控制台**中输入 `clear()`，然后选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="161fd-249">Enter `clear()` in the **Console** and select `Enter`.</span></span>  
*   <span data-ttu-id="161fd-250">从 JavaScript 中为你的网页运行 `console.clear()`。</span><span class="sxs-lookup"><span data-stu-id="161fd-250">Run `console.clear()` from the JavaScript for your webpage.</span></span>  
*   <span data-ttu-id="161fd-251">在聚焦**控制台**时选择 `Control`+`L`。</span><span class="sxs-lookup"><span data-stu-id="161fd-251">Select `Control`+`L` while the **Console** is in focus.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="161fd-252">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="161fd-252">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleApi]: ./api.md "控制台 API 参考 | Microsoft Docs"  
[DevtoolsConsoleConsoleLog]: ./console-log.md "在控制台工具控制台中记录|Microsoft Docs"  
[DevtoolsConsoleConsoleJavascript]: ./console-javascript.md "作为 JavaScript 环境的控制台|Microsoft Docs"  
[DevtoolsConsoleIndex]: .index.md "使用控制台|Microsoft Docs"  
[DevtoolsConsoleIndexInspectFilterInformationOnCurrentWebpage]: ./index.md#inspect-and-filter-information-on-the-current-webpage "检查并筛选当前网页上|Microsoft Docs"  
[DevtoolsConsoleLiveExpressions]: ./live-expressions.md "使用 Live Expressions 应用程序监视 JavaScript 中的|Microsoft Docs"  
[DevtoolsConsoleUtilities]: ./utilities.md "控制台实用程序 API 参考 | Microsoft Docs"  

[DevtoolsCommandMenuIndex]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行|Microsoft Docs"  

[MdnDocsGlossaryBrowsingContext]: https://developer.mozilla.org/docs/Glossary/Browsing_context "浏览上下文 | MDN"  

> [!NOTE]
> <span data-ttu-id="161fd-262">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="161fd-262">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="161fd-263">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="161fd-263">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="161fd-265">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="161fd-265">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
