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
# <a name="console-reference"></a>控制台参考  

本文引用了与开发人员工具控制台Microsoft Edge相关的功能。  它假定你已熟悉使用控制台查看记录的消息并运行 JavaScript。  如果没有，请导航到开始在控制台中运行 [JavaScript][DevtoolsConsoleConsoleJavascript] 和 [开始在控制台中记录消息][DevtoolsConsoleConsoleLog]。  

如果要查找对函数（如 ）的 API 引用，请 `console.log()` 导航到"[控制台 API 参考"。][DevToolsConsoleApi]  有关 `monitorEvents()` 等函数的参考，请导航到[控制台实用工具 API 参考][DevToolsConsoleUtilities]。  

## <a name="open-the-console"></a>打开控制台  

你可以将**控制台**作为[上部窗格中的工具](#open-the-console-tool)打开，也可以将其作为[工具箱中的工具](#open-the-console-tool-in-the-drawer)打开。  

### <a name="open-the-console-tool"></a>打开控制台工具  

选择 `Control`+`Shift`+`J` \(Windows, Linux\) 或 `Command`+`Option`+`J` \(macOS\)。  

:::image type="complex" source="../media/console-hello-console.msft.png" alt-text="控制台工具" lightbox="../media/console-hello-console.msft.png":::
   **控制台**工具  
:::image-end:::  

若要从命令**菜单**打开控制台工具[][DevtoolsCommandMenuIndex]，请键入 ，然后运行旁边有 `Console` **面板**锁屏提醒的显示控制台命令。 ****  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="运行命令以显示控制台工具" lightbox="../media/console-command-menu-show-console.msft.png":::
   运行命令以显示 **控制台** 工具  
:::image-end:::  

### <a name="open-the-console-tool-in-the-drawer"></a>打开工具箱中的控制台工具  

选择 `Esc` 或选择 **"自定义和控制 DevTools** \(`...` \) "，然后选择"显示控制台**箱"。**  

:::image type="complex" source="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png" alt-text="显示控制台工具箱" lightbox="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png":::
   **显示控制台工具箱**  
:::image-end:::  

在**控制台**工具打开的情况下，工具箱将在 DevTools 窗口的底部弹出。  

:::image type="complex" source="../media/console-elements-console-drawer-hello-world.msft.png" alt-text="工具箱中的控制台工具" lightbox="../media/console-elements-console-drawer-hello-world.msft.png":::
   **“抽屉”** 中的 **控制台** 工具  
:::image-end:::  

若要从命令**菜单**打开控制台工具[][DevtoolsCommandMenuIndex]，请键入 ，然后运行旁边有"箱"锁屏提醒的"显示 `Console` 控制台"命令。 **** ****  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="运行命令以在箱中显示 **Console** 工具" lightbox="../media/console-command-menu-show-console.msft.png":::
   运行命令以在"箱 **"** 中显示控制台 **工具**  
:::image-end:::  

### <a name="open-console-settings"></a>打开控制台设置  

Choose the **Console 设置**\(Console 设置 ![ icon ](../media/settings-button-icon.msft.png) \) button.  

:::image type="complex" source="../media/console-settings-group-similar-empty.msft.png" alt-text="控制台设置" lightbox="../media/console-settings-group-similar-empty.msft.png":::
   **控制台设置**  
:::image-end:::  

以下链接说明了每个设置。  

*   [隐藏网络](#hide-network-messages)  
*   [保留日志](#persist-messages-across-page-loads)  
*   [仅选定上下文](#filter-out-messages-from-different-contexts)  
*   [类似组](#turn-off-message-grouping)  
*   [Log XMLHttpRequests](#log-xhr-and-fetch-requests)  
*   [期待评估](#turn-off-eager-evaluation)  
*   [从历史记录自动完成](#turn-off-autocomplete-from-history)  
<!--*   Evaluate triggers user activation  -->  
    
### <a name="open-the-console-sidebar"></a>打开控制台边栏  

若要显示 **边栏**，请选择显示 **控制台边** 栏 \(![ 显示控制台边栏 ](../media/show-console-sidebar-icon.msft.png) \) 。  **边栏**可帮助你进行筛选。  

:::image type="complex" source="../media/console-sidebar-drawer-empty.msft.png" alt-text="控制台边栏" lightbox="../media/console-sidebar-drawer-empty.msft.png":::
   **控制台边栏**  
:::image-end:::  

## <a name="view-messages"></a>查看消息  

此部分包含更改消息在控制台中的显示方式的功能。  有关实际操作演练，请导航到“[查看消息][DevtoolsConsoleIndexInspectFilterInformationOnCurrentWebpage]”。  

### <a name="turn-off-message-grouping"></a>关闭邮件分组  

若要关闭控制台的默认邮件分组**行为**，请打开控制台[设置并选中](#open-console-settings)类似组**旁边的复选框**。  例如，导航到“[记录 XHR 和 Fetch 请求](#log-xhr-and-fetch-requests)”。  

### <a name="log-xhr-and-fetch-requests"></a>记录 XHR 和 Fetch 请求  

若要在每次发生时将所有和请求记录到控制台，请打开控制台 `XMLHttpRequest` `Fetch` 设置，然后选择 Log **XMLHttpRequests**[旁边的](#open-console-settings)复选框。 ****  

:::image type="complex" source="../media/console-xhr-fetch.msft.png" alt-text="记录 XMLHttpRequest 和 Fetch 请求" lightbox="../media/console-xhr-fetch.msft.png":::
   记录 `XMLHttpRequest` 和 `Fetch` 请求  
:::image-end:::  

上图中的顶部消息显示了**控制台**的默认分组行为。  <!--  In the following figure, the same log is displayed after you [turn off message grouping](#turn-off-message-grouping).  -->  

<!--  
> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> :::image type="complex" source="../media/console-xhr-fetch-all.msft.png" alt-text="How the logged XMLHttpRequest and Fetch requests look after ungrouping" lightbox="../media/console-xhr-fetch-all.msft.png":::
>    How the logged XMLHttpRequest and Fetch requests look after ungrouping  
> :::image-end:::  
-->  

<!--todo: add example for ungrouping console items  -->  

### <a name="persist-messages-across-page-loads"></a>跨页面加载保留消息  

加载新网页时，默认操作会清除 **控制台**。  若要跨页面加载保留消息，请[打开控制台设置](#open-console-settings)并选中"保留日志"旁边的**复选框**。  

### <a name="hide-network-messages"></a>隐藏网络消息  

用户的默认操作Microsoft Edge将网络消息记录到**控制台**。  在下图中，选择的消息表示 的 HTTP 状态代码 `429` 。  

:::image type="complex" source="../media/console-show-network.msft.png" alt-text="控制台中的 429 消息" lightbox="../media/console-show-network.msft.png":::
   **控制台**中的 `429` 消息  
:::image-end:::  

若要隐藏网络消息，请完成以下操作。  

1.  [打开控制台设置](#open-console-settings)。  
1.  选中隐藏网络旁边的 **复选框**。  
    
## <a name="filter-messages"></a>筛选邮件  

有许多方法可以筛选出控制台中的 **邮件**。  

### <a name="filter-out-browser-messages"></a>筛选出浏览器消息  

[打开控制台边栏](#open-the-console-sidebar) 并选择" **# 用户消息** "，以仅显示来自网页的 JavaScript 的消息。  

:::image type="complex" source="../media/console-sidebar-drawer-user-messages.msft.png" alt-text="显示用户消息" lightbox="../media/console-sidebar-drawer-user-messages.msft.png":::
   显示用户消息  
:::image-end:::  

### <a name="filter-by-log-level"></a>按记录级别筛选  

DevTools 为每个方法 `console.*` 分配四个严重性级别之一。  

*   `Error`  
*   `Info`  
*   `Verbose`  
*   `Warning`  
    
例如， `console.log()` 位于 `Info` 组中，但 `console.error()` 位于 `Error` 组中。  [控制台 API 参考][DevToolsConsoleApi]介绍了每种适用方法的严重性级别。  浏览器记录到控制台的每条消息也具有严重性级别。  你可以隐藏你不感兴趣的任何级别的邮件。  例如，如果只对邮件感兴趣，可以隐藏 `Error` 其他三个组。  

若要筛选邮件，请选择" **日志级别** "下拉列表，然后选择 `Verbose` `Info` 、、 `Warning` 或 `Error` 。  

:::image type="complex" source="../media/console-log-level-default-levels.msft.png" alt-text="日志级别下拉列表" lightbox="../media/console-log-level-default-levels.msft.png":::
   “**日志级别**”下拉列表  
:::image-end:::  

若要使用日志级别进行筛选，请打开[控制台边](#open-the-console-sidebar)栏，**然后选择错误、** 警告、******信息**或**详细**。  

:::image type="complex" source="../media/console-sidebar-warnings.msft.png" alt-text="使用边栏查看警告" lightbox="../media/console-sidebar-warnings.msft.png":::
   使用边栏查看警告  
:::image-end:::  

### <a name="filter-messages-by-url"></a>按 URL 筛选消息  

键入 `url:` 后跟 URL，以便仅查看来自该 URL 的邮件。  键入 后 `url:` ，DevTools 将显示所有相关 URL。  也可以使用域。  例如，如果 `https://example.com/a.js` 和 正在记录消息，则你可以专注于 `https://example.com/b.js` `url:https://example.com` 这两个脚本中的消息。  

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="URL 筛选器" lightbox="../media/console-filter-text.msft.png":::
   URL 筛选器  
:::image-end:::  

若要隐藏 URL 中的消息，请键入 `-url:` 。  这是一个负 URL 筛选器。  

:::image type="complex" source="../media/console-negative-filter-text.msft.png" alt-text="隐藏与 https://b.wal.co URL 匹配的所有消息的负 URL 筛选器" lightbox="../media/console-negative-filter-text.msft.png":::
   隐藏与 `https://b.wal.co` URL 匹配的所有消息的负 URL 筛选器
:::image-end:::  

若要显示来自单个 URL 的消息，请完成以下操作。  

1.  [打开控制台边栏](#open-the-console-sidebar)。  
1.  展开 **" # 用户消息"** 部分。  
1.  选择包含要关注的消息的脚本的 URL。  
    
:::image type="complex" source="../media/console-filter-text-specified.msft.png" alt-text="显示来自邮件wp-ad.min.js" lightbox="../media/console-filter-text-specified.msft.png":::
   显示来自的邮件 `wp-ad.min.js`  
:::image-end:::  

### <a name="filter-out-messages-from-different-contexts"></a>筛选出不同上下文的消息  

假设您网页上有一个 (广告\) 广告。  广告嵌入在 中 `<iframe>` ，在控制台 中生成许多 **消息**。  由于广告在不同的[JavaScript](#choose-javascript-context)上下文中运行，因此隐藏消息的一个方法就是打开控制台设置选中"仅上下文["](#open-console-settings)旁边的**复选框**。  

### <a name="filter-out-messages-that-dont-match-a-regular-expression-pattern"></a>筛选出与正则表达式模式不匹配的邮件  

在"筛选器"文本框中键入正则表达式，以筛选出任何与模式 `/[gm][ta][mi]/` 不匹配的邮件。 ****  DevTools 会检查在消息文本或导致记录消息的脚本中是否找到了该模式。  

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="筛选出与正则表达式不匹配的任何邮件" lightbox="../media/console-filter-regex.msft.png":::
   筛选出与正则表达式不匹配 `/[gm][ta][mi]/` 的任何邮件  
:::image-end:::  

## <a name="run-javascript"></a>运行 JavaScript  

本部分包含与在控制台中运行 JavaScript **相关的功能**。  有关实际操作演练，请导航到“[运行 JavaScript][DevtoolsConsoleConsoleJavascript]”。  

### <a name="rerun-expressions-from-history"></a>从历史记录重新运行表达式  

选择 以循环访问之前在控制台 中运行 `Up Arrow` JavaScript 表达式 **的历史记录**。  选择 `Enter` 可再次运行该表达式。  

### <a name="watch-the-value-of-an-expression-in-real-time-with-live-expressions"></a>使用 Live Expressions 实时监视表达式的值  

如果你发现自己在控制台中重复键入相同的 JavaScript 表达式****，你可能会发现创建 Live **Expression**更容易。  使用 **Live Expressions，** 键入表达式一次，然后将其固定到控制台 **的顶部**。  表达式的值几乎可以实时更新。  导航到“[使用实时表达式实时观看 JavaScript 表达式的值][DevToolsConsoleLiveExpressions]”。  

### <a name="turn-off-eager-evaluation"></a>关闭"期待评估"  

当您在控制台中键入 JavaScript 表达式时 **，"期待**评估"将显示返回值的**预览**。  若要关闭返回值预览，请完成以下操作。  

1.  [打开控制台设置](#open-console-settings)。  
1.  删除"期望评估" **旁边的复选框**。  
    
### <a name="turn-off-autocomplete-from-history"></a>从历史记录中关闭自动完成  

键入表达式时，控制台的自动完成弹出窗口将显示之前运行表达式。 ****  表达式使用 字符预先 `>` 绘制。  若要停止显示历史记录中的表达式，请打开控制台[设置并删除](#open-console-settings)"自动**完成**自历史记录"复选框旁边的复选框。  

> [!NOTE]
> 在下图中，`document.querySelector('a')` 和 `document.querySelector('img')` 是之前评估的表达式。  

:::image type="complex" source="../media/console-filter-text-autofilter-history.msft.png" alt-text="自动完成弹出菜单显示历史记录中的表达式" lightbox="../media/console-filter-text-autofilter-history.msft.png":::
   自动完成弹出菜单显示历史记录中的表达式  
:::image-end:::  

### <a name="choose-javascript-context"></a>选择 JavaScript 上下文  

**"JavaScript**上下文"下拉列表的默认选项位于**顶部**，它表示主[网页的浏览][MdnDocsGlossaryBrowsingContext]上下文。  

:::image type="complex" source="../media/console-dom-level-top.msft.png" alt-text="JavaScript 上下文下拉列表" lightbox="../media/console-dom-level-top.msft.png":::
   “**JavaScript 上下文**”下拉列表  
:::image-end:::  

假设您的网页中嵌入了一个广告 `<iframe>` 。  你想要运行 JavaScript 来调整广告的 DOM。  首先，从"JavaScript 上下文"下拉列表中选择 **广告的浏览** 上下文。  

:::image type="complex" source="../media/console-dom-level-multiple.msft.png" alt-text="选择其他 JavaScript 上下文" lightbox="../media/console-dom-level-multiple.msft.png":::
   选择其他 JavaScript 上下文  
:::image-end:::  

## <a name="clear-the-console"></a>清除控制台  

若要清除 **控制台**，请完成以下任何工作流。  

*   选择" **清除控制台** \(![ 清除控制台 ](../media/clear-console-button-icon.msft.png) \) "按钮。  
*   将鼠标悬停在消息上，打开上下文菜单 \(右键单击\) ，然后选择"清除**控制台"。**  
*   在**控制台**中输入 `clear()`，然后选择 `Enter`。  
*   从 JavaScript 中为你的网页运行 `console.clear()`。  
*   在聚焦**控制台**时选择 `Control`+`L`。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
