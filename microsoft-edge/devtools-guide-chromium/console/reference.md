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





# 控制台参考   



此页面是与 Microsoft Edge DevTools 控制台相关的功能的参考。  它假设你已经熟悉了如何使用 Console 查看记录的消息和运行 JavaScript。  如果不是，请参阅 [在控制台中运行 JavaScript 开始][DevToolsConsoleJavascript] ，并 [开始在控制台中记录消息][DevToolsConsoleLog]。  

如果你要查找有关函数的 API 参考，如 `console.log()` 请参阅 [控制台 API 参考][DevToolsConsoleApi]。  有关函数（如函数）的参考 `monitorEvents()` ，请参阅 [控制台实用工具 API 参考][DevToolsConsoleUtilities]。  

## 打开控制台   

你可以将控制台作为 [面板](#open-the-console-panel) 或 [抽屉中的选项卡](#open-the-console-tab-in-the-drawer)打开。  

### 打开控制台面板   

按 `Control` + `Shift` + `J` \ (Windows \ ) 或 `Command` + `Option` + `J` \ (macOS \ ) 。  

:::image type="complex" source="../media/console-hello-console.msft.png" alt-text="控制台面板" lightbox="../media/console-hello-console.msft.png":::
   **控制台**面板  
:::image-end:::  

若要从 " [命令" 菜单][DevToolsCommandMenu]打开 "控制台" 面板，请开始键入， `Console` 然后运行 " **显示控制台** " 命令，其中旁边有一个 **面板** 标记。  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="控制台面板" lightbox="../media/console-command-menu-show-console.msft.png":::
   用于显示 **控制台** 面板的命令  
:::image-end:::  

### 打开抽屉中的 "控制台" 选项卡   

按下 `Escape` 或单击 " **自定义" 并控制 DevTools** \ (`...` \ ) 然后选择 " **显示控制台抽屉**"。  

:::image type="complex" source="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png" alt-text="控制台面板" lightbox="../media/console-elements-customize-control-devtools-show-console-drawer.msft.png":::
   **显示控制台抽屉**  
:::image-end:::  

抽屉将在 DevTools 窗口底部弹出，并打开 " **控制台** " 选项卡。  

:::image type="complex" source="../media/console-elements-console-drawer-hello-world.msft.png" alt-text="控制台面板" lightbox="../media/console-elements-console-drawer-hello-world.msft.png":::
   **抽屉**中的 "**控制台**" 选项卡  
:::image-end:::  

若要从 " [命令" 菜单][DevToolsCommandMenu]打开 "控制台" 选项卡，请开始键入， `Console` 然后运行 " **显示控制台** " 命令，其中旁边有 **抽屉** 标记。  

:::image type="complex" source="../media/console-command-menu-show-console.msft.png" alt-text="控制台面板" lightbox="../media/console-command-menu-show-console.msft.png":::
   显示**抽屉**中的 "**控制台**" 选项卡的命令  
:::image-end:::  

### 打开控制台设置   

单击 " **控制台设置** \ (![ 控制台设置 ][ImageSettingsButtonIcon] \ ) "。  

:::image type="complex" source="../media/console-settings-group-similar-empty.msft.png" alt-text="控制台面板" lightbox="../media/console-settings-group-similar-empty.msft.png":::
   **控制台设置**  
:::image-end:::  

下面的链接对每个设置进行了说明：  

*   [**隐藏网络**](#hide-network-messages)  
*   [**保留日志**](#persist-messages-across-page-loads)  
*   [**仅限所选上下文**](#filter-out-messages-from-different-contexts)  
*   [**分组相似**](#disable-message-grouping)  
*   [**日志 XmlHttpRequests**](#log-xhr-and-fetch-requests)  
*   [**积极评估**](#disable-eager-evaluation)  
*   [**历史记录中的自动完成**](#disable-autocomplete-from-history)  
    
### 打开控制台边栏   

单击 " **显示控制台边栏** \ (![ 显示控制台边栏 ][ImageShowConsoleSidebarIcon] \ ) " 显示侧栏，它对于筛选很有用。  

:::image type="complex" source="../media/console-sidebar-drawer-empty.msft.png" alt-text="控制台面板" lightbox="../media/console-sidebar-drawer-empty.msft.png":::
   **控制台** 侧  
:::image-end:::  

## 查看邮件   

本部分包含更改如何在控制台中显示消息的功能。  请参阅查看动手演练的 [消息][DevToolsConsoleViewMessages] 。  

### 禁用邮件分组   

[打开 "控制台设置](#open-console-settings) " 并禁用 " **分组类似** "，禁用控制台的默认消息分组行为。  有关示例，请参阅 [记录 XHR 和获取请求](#log-xhr-and-fetch-requests) 。  

### 记录 XHR 和回迁请求   

[打开控制台设置](#open-console-settings) 并启用 **日志 XMLHttpRequests** ，以便在 `XMLHttpRequest` 发生时将所有和请求记录到 `Fetch` 控制台。  

:::image type="complex" source="../media/console-xhr-fetch.msft.png" alt-text="控制台面板" lightbox="../media/console-xhr-fetch.msft.png":::
   日志 `XMLHttpRequest` 和 `Fetch` 请求  
:::image-end:::  
上图中的顶部消息显示了该 **控制台**的默认分组行为。  <!--  In the following figure, the same log is displayed after [disabling message grouping](#disable-message-grouping).  -->  

<!--  
> ##### Old Figure 9  
> How the logged `XMLHttpRequest` and `Fetch` requests look after ungrouping  
> :::image type="complex" source="../media/console-xhr-fetch-all.msft.png" alt-text="控制台面板" lightbox="../media/console-xhr-fetch-all.msft.png":::
>    How the logged XMLHttpRequest and Fetch requests look after ungrouping  
> :::image-end:::  
-->  

<!--todo: add example for ungrouping console items  -->  

### 跨页面加载保留消息   

默认情况下，无论何时加载新页面，控制台都会被清除。  若要在每个页面加载期间保持消息，请 [打开控制台设置](#open-console-settings) ，然后启用 " **保留日志** " 复选框。  

### 隐藏网络消息   

默认情况下，浏览器将网络消息记录到 **控制台**。  在下图中，所选邮件表示 HTTP 状态代码 `429` 。  

:::image type="complex" source="../media/console-show-network.msft.png" alt-text="控制台面板" lightbox="../media/console-show-network.msft.png":::
   `429`**控制台**中的一条消息  
:::image-end:::  
要隐藏网络消息，请执行以下操作：  

1.  [打开控制台设置](#open-console-settings)。  
1.  启用 " **隐藏网络** " 复选框。  
    
## 筛选邮件   

可通过多种方式在控制台中筛选出消息。  

### 筛选出浏览器消息   

[打开控制台侧栏](#open-the-console-sidebar) ，然后单击 " **用户消息** "，仅显示来自页面 JavaScript 的消息。  

:::image type="complex" source="../media/console-sidebar-drawer-user-messages.msft.png" alt-text="控制台面板" lightbox="../media/console-sidebar-drawer-user-messages.msft.png":::
   查看用户消息  
:::image-end:::  

### 按日志级别筛选   

DevTools 为每个 `console.*` 方法分配一个严重级别。  有4个级别： `Verbose` 、 `Info` 、 `Warning` 和 `Error` 。  例如，位于 `console.log()` `Info` 组中，而位于 `console.error()` 组中 `Error` 。  [控制台 API 参考][DevToolsConsoleApi]描述每个适用方法的严重级别。  浏览器记录到控制台的每条消息也具有严重级别。  您可以隐藏不感兴趣的任何级别的邮件。  例如，如果只对邮件感兴趣 `Error` ，则可以隐藏其他3个组。  

单击 " **日志级别** " 下拉列表以启用或禁用 `Verbose` 、 `Info` 或 "消息" `Warning` `Error` 。  

:::image type="complex" source="../media/console-log-level-default-levels.msft.png" alt-text="控制台面板" lightbox="../media/console-log-level-default-levels.msft.png":::
   **日志级别**下拉列表  
:::image-end:::  

您还可以按日志级别进行筛选，方法是[打开控制台边栏](#open-the-console-sidebar)，然后单击 "**错误**"、"**警告**"、"信息" 或 "**详细****信息**"。  

:::image type="complex" source="../media/console-sidebar-warnings.msft.png" alt-text="控制台面板" lightbox="../media/console-sidebar-warnings.msft.png":::
   使用边栏查看警告  
:::image-end:::  

### 按 URL 筛选邮件   

键入 `url:` 后跟 url，仅查看来自该 url 的邮件。  键入 DevTools 后，将 `url:` 显示所有相关的 url。  域也有效。  例如，如果 `https://example.com/a.js` 和 `https://example.com/b.js` 正在记录邮件， `url:https://example.com` 则可让你关注来自这两个脚本的消息。  

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="控制台面板" lightbox="../media/console-filter-text.msft.png":::
   URL 筛选器  
:::image-end:::  

键入 `-url:` 以隐藏来自该 URL 的邮件。  这称为负 URL 筛选器。  

:::image type="complex" source="../media/console-negative-filter-text.msft.png" alt-text="控制台面板" lightbox="../media/console-negative-filter-text.msft.png":::
   用于隐藏所有与 URL 匹配的邮件的负 URL 筛选器 `https://b.wal.co`
:::image-end:::  

您还可以通过 [打开控制台边栏](#open-the-console-sidebar)，展开 " **用户消息** " 部分，然后单击包含要对其进行焦点的邮件的脚本的 URL，显示来自单个 URL 的邮件。  

:::image type="complex" source="../media/console-filter-text-specified.msft.png" alt-text="控制台面板" lightbox="../media/console-filter-text-specified.msft.png":::
   查看来自的邮件 `wp-ad.min.js`  
:::image-end:::  

### 筛选出来自不同上下文的消息   

假设您的页面上有广告 (广告 ) 。  广告嵌入在中 `<iframe>` ，并且会在您的控制台中生成大量消息。  由于广告在不同的 [JavaScript 上下文](#select-javascript-context)中运行，因此隐藏消息的一种方法是 [打开控制台设置](#open-console-settings) 并启用 " **仅限选定的上下文** " 复选框。  

### 筛选出与正则表达式模式不匹配的消息   

`/[gm][ta][mi]/`在 "**筛选器**" 文本框中键入正则表达式，以筛选出与该模式不匹配的任何消息。  DevTools 检查是否在消息文本或导致消息被记录的脚本中找到该模式。  

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="控制台面板" lightbox="../media/console-filter-regex.msft.png":::
   筛选出与 regex 表达式不匹配的任何消息 `/[gm][ta][mi]/`  
:::image-end:::  

## 运行 JavaScript   

本部分包含与在控制台中运行 JavaScript 相关的功能。  请参阅运行参与练习的 [JavaScript][DevToolsConsoleOverviewJavascript] 。  

### 重新运行历史记录中的表达式   

按下 `Up Arrow` 键，循环浏览你之前在控制台中运行的 JavaScript 表达式的历史记录。  按键 `Enter` 再次运行该表达式。  

### 使用实时表达式实时监视表达式的值   

如果您发现自己在控制台中重复键入相同的 JavaScript 表达式，您可能会发现创建 **实时表达式**变得更容易。  使用 **实时表达式** ，您只需要键入一个表达式，然后将其固定到您的控制台顶部。  表达式的值几乎实时更新。  请参阅 [实时在实时表达式中观看 JavaScript 表达式值][DevToolsConsoleLiveExpressions]。  

### 禁用热情评估   

当您在控制台中键入 JavaScript 表达式时， **预先计算** 会显示该表达式的返回值的预览。  [打开 "控制台设置](#open-console-settings) " 并禁用 " **预先评估** " 复选框以关闭返回值预览。  

### 禁用历史记录中的自动完成   

当您键入表达式时，控制台的 "自动完成" 弹出窗口将显示您之前运行的表达式。  这些表达式前置 `>` 字符。  [打开 "控制台设置](#open-console-settings) " 并禁用 " **从历史记录自动完成** " 复选框以停止显示历史记录中的表达式。  

> [!NOTE]
> 在下图中， `document.querySelector('a')` `document.querySelector('img')` 是之前计算的表达式。  

:::image type="complex" source="../media/console-filter-text-autofilter-history.msft.png" alt-text="控制台面板" lightbox="../media/console-filter-text-autofilter-history.msft.png":::
   "自动完成" 弹出窗口显示历史记录中的表达式  
:::image-end:::  

### 选择 JavaScript 上下文   

默认情况下， **JavaScript 上下文** 下拉列表设置为 " **页首**"，这表示主文档的 [浏览上下文][MDNBrowsingContext] 。  

:::image type="complex" source="../media/console-dom-level-top.msft.png" alt-text="控制台面板" lightbox="../media/console-dom-level-top.msft.png":::
   **JavaScript 上下文**下拉列表  
:::image-end:::  

假设您的页面上有一个嵌入的广告 `<iframe>` 。  你希望运行 JavaScript，以便调整广告的 DOM。  应首先从 **JavaScript 上下文** 下拉列表中选择广告的浏览上下文。  

:::image type="complex" source="../media/console-dom-level-multiple.msft.png" alt-text="控制台面板" lightbox="../media/console-dom-level-multiple.msft.png":::
   选择其他 JavaScript 上下文  
:::image-end:::  

## 清除控制台   

你可以使用以下任何工作流来清除控制台：  

*   单击 " **清除控制台** \ (![ 清除控制台 ][ImageClearConsoleIcon] \ ) "。  
*   右键单击一条消息，然后选择 " **清除控制台**"。  
*   `clear()`在控制台中键入，然后按 `Enter` 。  
*   `console.clear()`从你的网页的 JavaScript 调用。  
*   `Control` + `L` 控制台处于焦点状态时按键。  
    
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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
