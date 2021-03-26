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

# <a name="console-reference"></a>控制台参考  

此页面引用了与 Microsoft Edge DevTools 控制台相关的功能。  它假定你已经熟悉使用控制台查看记录的消息和运行 JavaScript。  如果情况并非如此，请导航至[开始在控制台中运行 JavaScript 入门][DevToolsConsoleJavascript]和[开始在控制台中记录消息][DevToolsConsoleLog]。  

如果要查找对 `console.log()` 等函数的 API 参考，请导航到“[控制台 API 参考][DevToolsConsoleApi]”。  有关 `monitorEvents()` 等函数的参考，请导航到[控制台实用工具 API 参考][DevToolsConsoleUtilities]。  

## <a name="open-the-console"></a>打开控制台  

你可以将**控制台**作为[上部窗格中的工具](#open-the-console-tool)打开，也可以将其作为[工具箱中的工具](#open-the-console-tool-in-the-drawer)打开。  

### <a name="open-the-console-tool"></a>打开控制台工具  

选择 `Control`+`Shift`+`J` \(Windows, Linux\) 或 `Command`+`Option`+`J` \(macOS\)。  

:::image type="complex" source="../media/console-hello-console.msft.png" alt-text="控制台工具" lightbox="../media/console-hello-console.msft.png":::
   **控制台**工具  
:::image-end:::  

要从[命令菜单][DevToolsCommandMenu]中打开**控制台**工具，首先请键入 `Console`，然后运行旁边有**面板**徽章的**显示控制台**命令。  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="显示“控制台”面板的命令" lightbox="../media/console-command-menu-show-console.msft.png":::
   显示“**控制台**”工具的命令  
:::image-end:::  

### <a name="open-the-console-tool-in-the-drawer"></a>打开工具箱中的控制台工具  

选择 `Escape` 或选择“**自定义和控制 DevTools**”\(`...`\)，然后选择“**显示控制台工具箱**”。  

:::image type="complex" source="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png" alt-text="显示控制台工具箱" lightbox="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png":::
   **显示控制台工具箱**  
:::image-end:::  

在**控制台**工具打开的情况下，工具箱将在 DevTools 窗口的底部弹出。  

:::image type="complex" source="../media/console-elements-console-drawer-hello-world.msft.png" alt-text="工具箱中的控制台工具" lightbox="../media/console-elements-console-drawer-hello-world.msft.png":::
   **工具箱**中的**控制台**工具  
:::image-end:::  

要从[命令菜单][DevToolsCommandMenu]中打开**控制台**工具，首先请键入 `Console`，然后运行旁边有**工具箱**徽章的**显示控制台**命令。  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="用于显示工具箱中的 **控制台** 工具的命令" lightbox="../media/console-command-menu-show-console.msft.png":::
   用于显示**工具箱**中的**控制台**工具的命令  
:::image-end:::  

### <a name="open-console-settings"></a>打开控制台设置  

选择**控制台设置** \（![控制台设置图标](../media/settings-button-icon.msft.png)\）。  

:::image type="complex" source="../media/console-settings-group-similar-empty.msft.png" alt-text="控制台设置" lightbox="../media/console-settings-group-similar-empty.msft.png":::
   **控制台设置**  
:::image-end:::  

下面的链接介绍了每个设置：  

*   [**隐藏网络**](#hide-network-messages)  
*   [**保留日志**](#persist-messages-across-page-loads)  
*   [**仅选定上下文**](#filter-out-messages-from-different-contexts)  
*   [**分组类似项**](#disable-message-grouping)  
*   [**记录 XmlHttpRequest**](#log-xhr-and-fetch-requests)  
*   [**预先评估**](#disable-eager-evaluation)  
*   [**从历史记录中自动完成**](#disable-autocomplete-from-history)  
    
### <a name="open-the-console-sidebar"></a>打开控制台边栏  

选择“**显示控制台边栏**”\（![显示控制台边栏](../media/show-console-sidebar-icon.msft.png)\）以显示边栏，该边栏可用于进行筛选。  

:::image type="complex" source="../media/console-sidebar-drawer-empty.msft.png" alt-text="控制台边栏" lightbox="../media/console-sidebar-drawer-empty.msft.png":::
   **控制台**边栏  
:::image-end:::  

## <a name="view-messages"></a>查看消息  

此部分包含更改消息在控制台中的显示方式的功能。  有关实际操作演练，请导航到“[查看消息][DevToolsConsoleViewMessages]”。  

### <a name="disable-message-grouping"></a>禁用消息分组  

[打开控制台设置](#open-console-settings)，然后禁用“**分组类似项**”以禁用控制台的默认消息分组行为。  例如，导航到“[记录 XHR 和 Fetch 请求](#log-xhr-and-fetch-requests)”。  

### <a name="log-xhr-and-fetch-requests"></a>记录 XHR 和 Fetch 请求  

[打开控制台设置](#open-console-settings)，然后启用“**记录 XMLHttpRequest**”以将所有 `XMLHttpRequest` 和 `Fetch` 请求记录到控制台。  

:::image type="complex" source="../media/console-xhr-fetch.msft.png" alt-text="记录 XMLHttpRequest 和 Fetch 请求" lightbox="../media/console-xhr-fetch.msft.png":::
   记录 `XMLHttpRequest` 和 `Fetch` 请求  
:::image-end:::  
上图中的顶部消息显示了**控制台**的默认分组行为。  <!--  In the following figure, the same log is displayed after [disabling message grouping](#disable-message-grouping).  -->  

<!--  
> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> :::image type="complex" source="../media/console-xhr-fetch-all.msft.png" alt-text="How the logged XMLHttpRequest and Fetch requests look after ungrouping" lightbox="../media/console-xhr-fetch-all.msft.png":::
>    How the logged XMLHttpRequest and Fetch requests look after ungrouping  
> :::image-end:::  
-->  

<!--todo: add example for ungrouping console items  -->  

### <a name="persist-messages-across-page-loads"></a>跨页面加载保留消息  

默认情况下，每次加载新页面时，控制台都会清除。  若要跨页面加载保留消息，请[打开控制台设置](#open-console-settings)，然后启用“**保留日志**”复选框。  

### <a name="hide-network-messages"></a>隐藏网络消息  

默认情况下，浏览器会将网络消息记录到**控制台**。  在下图中，选定的消息表示 `429` 的 HTTP 状态代码。  

:::image type="complex" source="../media/console-show-network.msft.png" alt-text="控制台中的 429 消息" lightbox="../media/console-show-network.msft.png":::
   **控制台**中的 `429` 消息  
:::image-end:::  
隐藏网络消息：  

1.  [打开控制台设置](#open-console-settings)。  
1.  启用“**隐藏网络**”复选框。  
    
## <a name="filter-messages"></a>筛选消息  

有许多方法可以筛选出控制台中的消息。  

### <a name="filter-out-browser-messages"></a>筛选出浏览器消息  

[打开控制台边栏](#open-the-console-sidebar)，然后选择“**用户消息**”，以仅显示来自页面 JavaScript 的消息。  

:::image type="complex" source="../media/console-sidebar-drawer-user-messages.msft.png" alt-text="查看用户消息" lightbox="../media/console-sidebar-drawer-user-messages.msft.png":::
   查看用户消息  
:::image-end:::  

### <a name="filter-by-log-level"></a>按日志级别筛选  

DevTools 为每个 `console.*` 方法分配一个严重性级别。  有 4 个级别：`Verbose`、`Info`、`Warning` 和 `Error`。  例如，`console.log()` 位于 `Info` 组中，而 `console.error()` 位于 `Error` 组中。  [控制台 API 参考][DevToolsConsoleApi]介绍了每种适用方法的严重性级别。  浏览器记录到控制台的每条消息也具有严重性级别。  你可以隐藏不感兴趣的任何级别的消息。  例如，如果你只对 `Error` 消息感兴趣，则可以隐藏其他 3 个组。  

选择“**日志级别**”下拉列表以启用或禁用 `Verbose`、`Info`、`Warning` 或 `Error` 消息。  

:::image type="complex" source="../media/console-log-level-default-levels.msft.png" alt-text="“日志级别”下拉列表" lightbox="../media/console-log-level-default-levels.msft.png":::
   “**日志级别**”下拉列表  
:::image-end:::  

也可以按日志级别进行筛选，方法为[打开控制台边栏](#open-the-console-sidebar)，然后选择“**错误**”、“**警告**”、“**信息**”或“**详细**”。  

:::image type="complex" source="../media/console-sidebar-warnings.msft.png" alt-text="使用边栏查看警告" lightbox="../media/console-sidebar-warnings.msft.png":::
   使用边栏查看警告  
:::image-end:::  

### <a name="filter-messages-by-url"></a>按 URL 筛选消息  

键入 `url:` 后跟 URL，以便仅查看来自该 URL 的邮件。  键入 `url:` DevTools 后，会显示所有相关 URL。  也可以使用域。  例如，如果 `https://example.com/a.js` 和 `https://example.com/b.js` 正在记录消息，则使用 `url:https://example.com` 可以专注于这 2 个脚本中的消息。  

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="URL 筛选器" lightbox="../media/console-filter-text.msft.png":::
   URL 筛选器  
:::image-end:::  

键入 `-url:` 可隐藏该 URL 中的消息。  这称为负 URL 筛选器。  

:::image type="complex" source="../media/console-negative-filter-text.msft.png" alt-text="隐藏与 https://b.wal.co URL 匹配的所有消息的负 URL 筛选器" lightbox="../media/console-negative-filter-text.msft.png":::
   隐藏与 `https://b.wal.co` URL 匹配的所有消息的负 URL 筛选器
:::image-end:::  

还可以通过以下方法显示来自单个 URL 的消息：[打开控制台边栏](#open-the-console-sidebar)，展开“**用户消息**”部分，然后选择包含要关注的消息的脚本的 URL。  

:::image type="complex" source="../media/console-filter-text-specified.msft.png" alt-text="查看来自 wp-ad.min.js 的消息" lightbox="../media/console-filter-text-specified.msft.png":::
   查看来自以下对象的邮件 `wp-ad.min.js`  
:::image-end:::  

### <a name="filter-out-messages-from-different-contexts"></a>筛选出不同上下文的消息  

假设你的页面有一个广告\（广告\）。  该广告嵌入在 `<iframe>` 中，并在你的控制台中生成大量消息。  由于广告在不同的 [JavaScript 上下文](#select-javascript-context)中运行，因此隐藏消息的一种方法是[打开控制台设置](#open-console-settings)，然后打开“**仅选定上下文**”复选框。  

### <a name="filter-out-messages-that-do-not-match-a-regular-expression-pattern"></a>筛选出与正则表达式模式不匹配的邮件  

在“**筛选器**”文本框中键入正则表达式（如 `/[gm][ta][mi]/`），以筛选出任何与该模式不匹配的消息。  DevTools 会检查在消息文本或导致记录消息的脚本中是否找到了该模式。  

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="筛选出任何与正则表达式不匹配的消息" lightbox="../media/console-filter-regex.msft.png":::
   筛选出任何与正则表达式不匹配 `/[gm][ta][mi]/` 的消息  
:::image-end:::  

## <a name="run-javascript"></a>运行 JavaScript  

本部分包含与在控制台中运行 JavaScript 相关的功能。  有关实际操作演练，请导航到“[运行 JavaScript][DevToolsConsoleOverviewJavascript]”。  

### <a name="re-run-expressions-from-history"></a>从历史记录中重新运行表达式  

选择 `Up Arrow` 键可循环浏览先前在控制台中运行的 JavaScript 表达式的历史记录。  选择 `Enter` 可再次运行该表达式。  

### <a name="watch-the-value-of-an-expression-in-real-time-with-live-expressions"></a>使用实时表达式实时观看表达式的值  

如果发现自己在控制台中重复键入相同的JavaScript表达式，则可能会发现创建**实时表达式**更容易。  使用**实时表达式**键入表达式一次，然后将其固定到控制台顶部。  表达式的值几乎实时更新。  导航到“[使用实时表达式实时观看 JavaScript 表达式的值][DevToolsConsoleLiveExpressions]”。  

### <a name="disable-eager-evaluation"></a>禁用预先评估  

在控制台中键入 JavaScript 表达式时，“**预先评估**”会显示该表达式的返回值的预览。  [打开控制台设置](#open-console-settings)并禁用“**预先评估**”复选框以关闭返回值预览。  

### <a name="disable-autocomplete-from-history"></a>禁用从历史记录中自动完成  

键入表达式时，控制台的自动完成弹出窗口会显示之前运行的表达式。  这些表达式以 `>` 字符开头。  [打开控制台设置](#open-console-settings)，然后禁用“**从历史记录中自动完成**”复选框，以停止从历史记录中显示表达式。  

> [!NOTE]
> 在下图中，`document.querySelector('a')` 和 `document.querySelector('img')` 是之前评估的表达式。  

:::image type="complex" source="../media/console-filter-text-autofilter-history.msft.png" alt-text="自动完成弹出窗口显示历史记录中的表达式" lightbox="../media/console-filter-text-autofilter-history.msft.png":::
   自动完成弹出窗口显示历史记录中的表达式  
:::image-end:::  

### <a name="select-javascript-context"></a>选择 JavaScript 上下文  

默认情况下，“**JavaScript 上下文**”下拉列表设置为“**顶部**”，表示主文档的[浏览上下文][MDNBrowsingContext]。  

:::image type="complex" source="../media/console-dom-level-top.msft.png" alt-text="“JavaScript 上下文”下拉列表" lightbox="../media/console-dom-level-top.msft.png":::
   “**JavaScript 上下文**”下拉列表  
:::image-end:::  

假设页面上有一个嵌入在 `<iframe>` 中的广告。  你想要运行 JavaScript 以调整广告的 DOM。  应先从“**JavaScript 上下文**”下拉列表中选择广告的浏览上下文。  

:::image type="complex" source="../media/console-dom-level-multiple.msft.png" alt-text="选择其他 JavaScript 上下文" lightbox="../media/console-dom-level-multiple.msft.png":::
   选择其他 JavaScript 上下文  
:::image-end:::  

## <a name="clear-the-console"></a>清除控制台  

可以使用以下任一工作流清除控制台：  

*   选择“**清除控制台**”\（清除控制台![ ](../media/clear-console-button-icon.msft.png) \）。  
*   将鼠标悬停在消息上，打开上下文菜单\（右键单击\），然后选择“**清除控制台**”。  
*   在**控制台**中输入 `clear()`，然后选择 `Enter`。  
*   从 JavaScript 中为你的网页运行 `console.clear()`。  
*   在聚焦**控制台**时选择 `Control`+`L`。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
