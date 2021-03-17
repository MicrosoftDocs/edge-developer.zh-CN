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

# <a name="console-reference"></a>控制台参考  

此页面引用了与 Microsoft Edge DevTools 控制台相关的功能。  它假定你已熟悉使用控制台查看记录的消息并运行 JavaScript。  如果没有，请导航到"开始在控制台中运行[JavaScript"][DevToolsConsoleJavascript]和"开始在控制台中[记录消息"。][DevToolsConsoleLog]  

如果要查找对函数（如 ）的 API 引用，请 `console.log()` 导航到"[控制台 API 参考"。][DevToolsConsoleApi]  For the reference on functions like `monitorEvents()` ， navigate to Console [Utilities API Reference][DevToolsConsoleUtilities].  

## <a name="open-the-console"></a>打开控制台  

你可以将 **控制台作为** 工具在上 [窗格中打开，](#open-the-console-tool) 也可以作为 [工具在"箱"中打开](#open-the-console-tool-in-the-drawer)。  

### <a name="open-the-console-tool"></a>打开控制台工具  

选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 。  

:::image type="complex" source="../media/console-hello-console.msft.png" alt-text="控制台工具" lightbox="../media/console-hello-console.msft.png":::
   控制台**工具**  
:::image-end:::  

若要从命令**菜单**打开控制台工具[][DevToolsCommandMenu]，请开始键入，然后运行旁边有面板锁屏提醒的显示 `Console` 控制台**** 命令。 ****  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="显示控制台面板的命令" lightbox="../media/console-command-menu-show-console.msft.png":::
   显示控制台 **工具** 的命令  
:::image-end:::  

### <a name="open-the-console-tool-in-the-drawer"></a>在"箱"中打开控制台工具  

选择 `Escape` 或选择 **自定义和控制开发工具** \ (`...` \) ，然后选择显示 **控制台箱**。  

:::image type="complex" source="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png" alt-text="显示控制台箱" lightbox="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png":::
   **显示控制台箱**  
:::image-end:::  

The Drawer pops up at the bottom of your DevTools window， with the **Console** tool open.  

:::image type="complex" source="../media/console-elements-console-drawer-hello-world.msft.png" alt-text=""箱"中的控制台工具" lightbox="../media/console-elements-console-drawer-hello-world.msft.png":::
   " **箱** "中的控制台 **工具**  
:::image-end:::  

若要从命令**菜单**打开控制台工具[][DevToolsCommandMenu]，请开始键入，然后运行旁边有"箱"锁屏提醒的"显示 `Console` 控制台"命令。 **** ****  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="在"箱"中显示 **Console** 工具的命令" lightbox="../media/console-command-menu-show-console.msft.png":::
   在"箱" **中显示** 控制台工具 **的命令**  
:::image-end:::  

### <a name="open-console-settings"></a>打开控制台设置  

Choose **Console Settings** \ (Console Settings icon ![ ](../media/settings-button-icon.msft.png) \) .  

:::image type="complex" source="../media/console-settings-group-similar-empty.msft.png" alt-text="控制台设置" lightbox="../media/console-settings-group-similar-empty.msft.png":::
   **控制台设置**  
:::image-end:::  

下面的链接说明了每个设置：  

*   [**隐藏网络**](#hide-network-messages)  
*   [**保留日志**](#persist-messages-across-page-loads)  
*   [**仅选定上下文**](#filter-out-messages-from-different-contexts)  
*   [**Group Similar**](#disable-message-grouping)  
*   [**Log XmlHttpRequests**](#log-xhr-and-fetch-requests)  
*   [**期待评估**](#disable-eager-evaluation)  
*   [**从历史记录自动完成**](#disable-autocomplete-from-history)  
    
### <a name="open-the-console-sidebar"></a>打开控制台边栏  

选择 **"显示控制台边** 栏 \ (显示 ![ 控制台边栏 ](../media/show-console-sidebar-icon.msft.png) \) "可显示用于筛选的边栏。  

:::image type="complex" source="../media/console-sidebar-drawer-empty.msft.png" alt-text="控制台边栏" lightbox="../media/console-sidebar-drawer-empty.msft.png":::
   **控制台** 边栏  
:::image-end:::  

## <a name="view-messages"></a>查看邮件  

此部分包含更改消息在控制台中的显示方式的功能。  有关实际操作演练，请导航到"[查看邮件"。][DevToolsConsoleViewMessages]  

### <a name="disable-message-grouping"></a>禁用邮件分组  

[打开"控制台](#open-console-settings) 设置"并禁用 **"组** "，类似于禁用控制台的默认邮件分组行为。  例如，导航到"[日志 XHR"和"提取请求"。](#log-xhr-and-fetch-requests)  

### <a name="log-xhr-and-fetch-requests"></a>记录 XHR 和提取请求  

[打开"控制台](#open-console-settings) 设置"并启用 **Log XMLHttpRequests，** 以在它们出现时将全部和 `XMLHttpRequest` `Fetch` 请求记录到控制台。  

:::image type="complex" source="../media/console-xhr-fetch.msft.png" alt-text="Log XMLHttpRequest 和 Fetch 请求" lightbox="../media/console-xhr-fetch.msft.png":::
   日志 `XMLHttpRequest` `Fetch` 和请求  
:::image-end:::  
上图中的顶部消息显示控制台 的默认分组 **行为**。  <!--  In the following figure, the same log is displayed after [disabling message grouping](#disable-message-grouping).  -->  

<!--  
> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> :::image type="complex" source="../media/console-xhr-fetch-all.msft.png" alt-text="How the logged XMLHttpRequest and Fetch requests look after ungrouping" lightbox="../media/console-xhr-fetch-all.msft.png":::
>    How the logged XMLHttpRequest and Fetch requests look after ungrouping  
> :::image-end:::  
-->  

<!--todo: add example for ungrouping console items  -->  

### <a name="persist-messages-across-page-loads"></a>跨页面加载保留消息  

默认情况下，每次加载新页面时，控制台都会清除。  若要跨页面加载保留消息，请 [打开"控制台设置](#open-console-settings) "，然后启用" **保留日志"** 复选框。  

### <a name="hide-network-messages"></a>隐藏网络消息  

默认情况下，浏览器将网络消息记录到 **控制台**。  在下图中，选定的消息表示 的 HTTP 状态代码 `429` 。  

:::image type="complex" source="../media/console-show-network.msft.png" alt-text="控制台中的 429 消息" lightbox="../media/console-show-network.msft.png":::
   `429`控制台中的**消息**  
:::image-end:::  
隐藏网络消息：  

1.  [打开控制台设置](#open-console-settings)。  
1.  启用" **隐藏网络"** 复选框。  
    
## <a name="filter-messages"></a>筛选邮件  

有许多方法可以筛选掉控制台中的邮件。  

### <a name="filter-out-browser-messages"></a>筛选掉浏览器消息  

[打开控制台边栏并选择](#open-the-console-sidebar) " **用户消息** "，以仅显示来自页面的 JavaScript 的消息。  

:::image type="complex" source="../media/console-sidebar-drawer-user-messages.msft.png" alt-text="查看用户消息" lightbox="../media/console-sidebar-drawer-user-messages.msft.png":::
   查看用户消息  
:::image-end:::  

### <a name="filter-by-log-level"></a>按日志级别筛选  

DevTools 为每个 `console.*` 方法分配一个严重性级别。  有 4 个 `Verbose` 级别 `Info` ：、、 `Warning` 和 `Error` 。  例如， `console.log()` 位于 `Info` 组中，而 `console.error()` 位于 `Error` 组中。  控制台 [API 参考][DevToolsConsoleApi] 介绍了每个适用方法的严重性级别。  浏览器记录到控制台的每条消息也具有严重性级别。  您可以隐藏您不感兴趣的任何级别的邮件。  例如，如果只对邮件感兴趣，可以隐藏 `Error` 其他 3 个组。  

选择" **日志级别** "下拉列表以启用或禁用 `Verbose` 、 或 `Info` `Warning` `Error` 消息。  

:::image type="complex" source="../media/console-log-level-default-levels.msft.png" alt-text=""日志级别"下拉列表" lightbox="../media/console-log-level-default-levels.msft.png":::
   " **日志级别"** 下拉列表  
:::image-end:::  

也可以按日志级别进行筛选，方法为打开[控制台边](#open-the-console-sidebar)栏，然后选择错误、警告****、**信息**或**详细**。 ****  

:::image type="complex" source="../media/console-sidebar-warnings.msft.png" alt-text="使用边栏查看警告" lightbox="../media/console-sidebar-warnings.msft.png":::
   使用边栏查看警告  
:::image-end:::  

### <a name="filter-messages-by-url"></a>按 URL 筛选邮件  

键入 `url:` 后跟 URL，以便仅查看来自该 URL 的邮件。  键入 `url:` DevTools 后，会显示所有相关 URL。  域也正常工作。  例如，如果 `https://example.com/a.js` 和 正在记录消息，则使您能够专注于 `https://example.com/b.js` 这 `url:https://example.com` 2 个脚本中的邮件。  

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="URL 筛选器" lightbox="../media/console-filter-text.msft.png":::
   URL 筛选器  
:::image-end:::  

键入 `-url:` 以隐藏该 URL 中的邮件。  这称为负 URL 筛选器。  

:::image type="complex" source="../media/console-negative-filter-text.msft.png" alt-text="隐藏与 URL 匹配的所有邮件的负 https://b.wal.co URL 筛选器" lightbox="../media/console-negative-filter-text.msft.png":::
   隐藏与 URL 匹配的所有邮件的负 `https://b.wal.co` URL 筛选器
:::image-end:::  

还可以打开控制台边栏，展开"用户消息[](#open-the-console-sidebar)"部分，然后选择包含要关注的消息**** 的脚本的 URL，从而显示来自单个 URL 的消息。  

:::image type="complex" source="../media/console-filter-text-specified.msft.png" alt-text="查看来自邮件wp-ad.min.js" lightbox="../media/console-filter-text-specified.msft.png":::
   查看来自的邮件 `wp-ad.min.js`  
:::image-end:::  

### <a name="filter-out-messages-from-different-contexts"></a>筛选出不同上下文中的消息  

假设您的页面有一个 (广告\) 广告。  广告嵌入在 中 `<iframe>` ，并且正在控制台中生成大量消息。  由于广告在不同的[JavaScript](#select-javascript-context)上下文中运行，因此隐藏消息的一个方法就是打开"控制台[](#open-console-settings)设置"并打开"**仅选定上下文"** 复选框。  

### <a name="filter-out-messages-that-do-not-match-a-regular-expression-pattern"></a>筛选出与正则表达式模式不匹配的邮件  

在"筛选器"文本框中键入正则表达式，以筛选出任何与模式 `/[gm][ta][mi]/` 不匹配的邮件。 ****  DevTools 检查在消息文本或导致记录消息的脚本中是否找到模式。  

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="筛选出任何与正则表达式不匹配的邮件" lightbox="../media/console-filter-regex.msft.png":::
   筛选出与正则表达式不匹配 `/[gm][ta][mi]/` 的任何邮件  
:::image-end:::  

## <a name="run-javascript"></a>运行 JavaScript  

本部分包含与在控制台中运行 JavaScript 相关的功能。  有关实际操作演练，请导航到"[运行 JavaScript"。][DevToolsConsoleOverviewJavascript]  

### <a name="re-run-expressions-from-history"></a>从历史记录重新运行表达式  

选择要 `Up Arrow` 循环访问之前在控制台中运行 JavaScript 表达式的历史记录的键。  选择 `Enter` 以再次运行该表达式。  

### <a name="watch-the-value-of-an-expression-in-real-time-with-live-expressions"></a>使用 Live Expressions 实时监视表达式的值  

如果你发现自己在控制台中重复键入相同的 JavaScript 表达式，你可能会发现创建 Live **Expression**更容易。  使用 **Live Expressions，** 键入表达式一次，然后将其固定到控制台顶部。  表达式的值几乎实时更新。  导航到 [使用 Live Expressions Real-Time JavaScript 表达式值][DevToolsConsoleLiveExpressions]。  

### <a name="disable-eager-evaluation"></a>禁用期待评估  

在控制台中键入 JavaScript 表达式时 **，"等待** 评估"会显示该表达式的返回值的预览。  [打开控制台设置](#open-console-settings) 并禁用 **"期望评估** "复选框以关闭返回值预览。  

### <a name="disable-autocomplete-from-history"></a>禁用历史记录中的自动完成  

键入表达式时，控制台的自动完成弹出窗口会显示之前运行表达式。  这些表达式在字符前 `>` 预置。  [打开"控制台](#open-console-settings) 设置"并禁用"自动 **完成自历史记录"** 复选框以停止显示历史记录中的表达式。  

> [!NOTE]
> 在下图中， `document.querySelector('a')` `document.querySelector('img')` 和 是之前评估的表达式。  

:::image type="complex" source="../media/console-filter-text-autofilter-history.msft.png" alt-text="自动完成弹出窗口显示历史记录中的表达式" lightbox="../media/console-filter-text-autofilter-history.msft.png":::
   自动完成弹出窗口显示历史记录中的表达式  
:::image-end:::  

### <a name="select-javascript-context"></a>选择 JavaScript 上下文  

默认情况下 **，"JavaScript 上下文**"下拉列表设置为**顶部**，表示主文档的[][MDNBrowsingContext]浏览上下文。  

:::image type="complex" source="../media/console-dom-level-top.msft.png" alt-text=""JavaScript 上下文"下拉列表" lightbox="../media/console-dom-level-top.msft.png":::
   **"JavaScript 上下文**"下拉列表  
:::image-end:::  

假设页面上有一个嵌入在 中的广告 `<iframe>` 。  你想要运行 JavaScript 以调整广告的 DOM。  应首先从"JavaScript 上下文"下拉列表中选择 **广告的浏览** 上下文。  

:::image type="complex" source="../media/console-dom-level-multiple.msft.png" alt-text="选择其他 JavaScript 上下文" lightbox="../media/console-dom-level-multiple.msft.png":::
   选择其他 JavaScript 上下文  
:::image-end:::  

## <a name="clear-the-console"></a>清除控制台  

可以使用以下任一工作流清除控制台：  

*   Choose **Clear Console** \ (Clear Console ![ ](../media/clear-console-button-icon.msft.png) \) .  
*   将鼠标悬停在消息上，打开上下文菜单 \ (righ-click\) ，然后选择"**清除控制台"。**  
*   在 `clear()` 控制台中 **输入 并选择** `Enter` 。  
*   从 `console.clear()` JavaScript 中为网页运行。  
*   在 `Control` + `L` 控制台**聚焦**时选择。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
