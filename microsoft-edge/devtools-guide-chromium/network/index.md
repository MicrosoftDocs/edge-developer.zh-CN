---
description: 有关 Microsoft Edge DevTools 中最受欢迎的网络相关功能的教程。
title: 检查 Microsoft Edge DevTools 中的网络活动
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: a4a552fa9a45267a6ffa4a4e83e7ebc4e1817162
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439694"
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

# <a name="inspect-network-activity-in-microsoft-edge-devtools"></a>检查 Microsoft Edge DevTools 中的网络活动  

这是一个动手教程，介绍了一些最常用的 DevTools 功能，这些功能与检查页面的网络活动相关。  

如果要浏览功能，请导航到"网络[参考"。][DevtoolsNetworkReference]  

<!--TODO: This entire section needs a Microsoft Edge DevTools re-write  -->

<!-- Read on, or watch the video version of this tutorial:  -->  

<!--
> [!VIDEO embed/e1gAyQuIFQo]  
-->

## <a name="when-to-use-the-network-panel"></a>何时使用网络面板  

一般情况下，当您需要确保资源正在下载或上传时，请使用网络面板。  网络面板的最常见用例包括：  

*   确保资源上载或下载实际正在进行。  
*   检查单个资源的属性，如 HTTP 标头、内容、大小等。  
    
如果要寻找提高页面加载性能的方法，请不要从网络**工具**开始。 ****  有许多类型的负载性能问题与网络活动不相关。  从“审核”面板开始，因为它为你提供了有关改进页面的目标建议。  导航到 [优化网站速度][DevtoolsSpeedGetStarted]。  

## <a name="open-the-network-panel"></a>打开“网络”面板  

若要在本教程中取得最大功能，请打开演示并试用演示页面上的功能。  

1.  打开 “[入门][GlitchNetworkGetStarted]”演示。  
    
    :::image type="complex" source="../media/network-glitch-inspect-network-activity-demo.msft.png" alt-text="演示" lightbox="../media/network-glitch-inspect-network-activity-demo.msft.png":::
       演示  
    :::image-end:::  
    
    <!--You may prefer to move the demo to a separate window.  -->  
    
    <!--
    :::image type="complex" source="../media/network-tutorial/windows.msft.png" alt-text="The demo in one window and this tutorial in a different window" lightbox="../media/network-tutorial/windows.msft.png":::
       The demo in one window and this tutorial in a different window  
    :::image-end:::  
    -->
    
1.  若要[打开 DevTools，][DevToolsOpen]请选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 。  将 **打开控制台** 工具。  
    
    :::image type="complex" source="../media/network-glitch-console.msft.png" alt-text="控制台" lightbox="../media/network-glitch-console.msft.png":::
       **控制台**  
    :::image-end:::  
    
    你可能更喜欢将 [DevTools 停靠到窗口底部][DevToolsCustomizePlacement]。  
    
    :::image type="complex" source="../media/network-glitch-console-bottom.msft.png" alt-text="停靠在窗口底部的 DevTools" lightbox="../media/network-glitch-console-bottom.msft.png":::
       停靠在窗口底部的 DevTools  
    :::image-end:::  
    
1.  打开 **"网络"** 工具。  
    
    :::image type="complex" source="../media/network-glitch-network-bottom.msft.png" alt-text="固定到窗口底部的 DevTools 中的控制台工具" lightbox="../media/network-glitch-network-bottom.msft.png":::
       固定到窗口底部的 DevTools 中的**控制台**工具  
    :::image-end:::  
    
现在， **网络** 工具为空。  DevTools 仅在打开网络活动后记录网络活动，自打开 DevTools 后未发生网络活动。  

## <a name="log-network-activity"></a>记录网络活动  

查看页面导致的网络活动：  

1.  刷新网页。  网络面板在**网络日志**中记录所有网络活动。  
    
    :::image type="complex" source="../media/network-glitch-network.msft.png" alt-text="网络日志" lightbox="../media/network-glitch-network.msft.png":::
       **网络日志**  
    :::image-end:::  
    
    **网络日志**的每一行表示一个资源。  默认情况下，按时间顺序列出资源。  顶部资源通常是主 HTML 文档。  底部资源是最后请求的任何资源。  
    
    每个列表示有关资源的信息。  在上图中，将显示默认列。  

    *   **状态**。  响应的 HTTP 状态代码。  
    *   **类型**。  资源类型。  
    *   **发起程序**。  资源请求的原因。  CHoosing a link in the Initiator column takes you to the source code thatcaused the request.  
    *   **时间**。  请求的持续时间。  
    *   **粘滞键**。  请求的不同阶段的图形表示形式。  若要显示细目，请将鼠标悬停在瀑布上。  
    
    > [!NOTE]
    > 网络日志上方的图形称为“概述”。  本教程中不会使用概述图，因此可以隐藏它。  导航到 [隐藏概述窗格][DevtoolsReferenceHideOverview]。
    
1.  打开 DevTools 后，它会在网络日志中记录网络活动。  
    若要演示这一点，请首先查看**网络日志** 的底部，并记下上一次活动。  
1.  现在，在演示中选择“**获取数据**”按钮。  
1.  再次查看**网络日志** 的底部。  将显示名为 的新 `getstarted.json` 资源。  若要使网页请求文件，请选择" **获取数据"** 按钮。  
    
    :::image type="complex" source="../media/network-glitch-network-new-resource.msft.png" alt-text="网络日志中的新资源" lightbox="../media/network-glitch-network-new-resource.msft.png":::
       **网络日志**中的新资源  
    :::image-end:::  
    
## <a name="show-more-information"></a>显示详细信息  

网络日志的列是可配置的。  您可以隐藏您未使用的列。  
默认情况下，还有许多列处于隐藏状态，您可能会发现这些列很有用。  

1.  将鼠标悬停在"网络日志"表的标题上，打开上下文菜单 \ (右键单击\) ，然后选择"域 **"。**  现在将显示每个资源的域。  
    
    :::image type="complex" source="../media/network-glitch-network-edit-column.msft.png" alt-text="启用“域”列" lightbox="../media/network-glitch-network-edit-column.msft.png":::
       启用“域”列  
    :::image-end:::  
    
    > [!TIP]
    > 若要查看资源的完整 URL，请将鼠标悬停在"名称"列中 **的单元格** 上。  
    
## <a name="simulate-a-slower-network-connection"></a>模拟较慢的网络连接  

用于构建站点的计算机的网络连接可能比用户的移动设备的网络连接速度快。  通过限制页面，可以更好地了解页面在移动设备上加载所花的时间。  

1.  选择 **"限制"** 下拉列表，默认设置为 **"联机** "。  
    
    :::image type="complex" source="../media/network-glitch-network-throttling.msft.png" alt-text="启用限制" lightbox="../media/network-glitch-network-throttling.msft.png":::
       启用限制  
    :::image-end:::  
    
1.  选择“**慢速 3G**”。  
    
    :::image type="complex" source="../media/network-glitch-network-throttling-slow-3g.msft.png" alt-text="选择"慢速 3G"" lightbox="../media/network-glitch-network-throttling-slow-3g.msft.png":::
       选择"慢速 3G"  
    :::image-end:::  
    
1.  长按**Reload** \(![Reload](../media/refresh-icon.msft.png)\) ，然后选择“**空缓存和硬重新加载**”。  
    
    :::image type="complex" source="../media/network-glitch-empty-cache-and-hard-reset.msft.png" alt-text="空缓存和硬重新加载" lightbox="../media/network-glitch-empty-cache-and-hard-reset.msft.png":::
       **空缓存和硬重新加载**  
    :::image-end:::  
    
    在重复访问时，浏览器通常会从[缓存][MDNHTTPCache]中提供一些文件，从而加快页面加载速度。  **空缓存和硬重新加载** 会强制浏览器访问所有资源的网络。  使用它来显示第一次访问者如何体验页面加载。  
    
    > [!NOTE]
    > **空缓存和硬重新加载**工作流仅在 DevTools 打开时可用。  
    
## <a name="capture-screenshots"></a>捕获屏幕截图  

屏幕截图显示网页在加载时的外观。  

1.  Choose \ (![ Network settings ](../media/settings-icon.msft.png) \) and turn on the Capture **screenshots** checkbox.
1.  使用"空缓存"和"硬重新加载 **"工作流再次刷新** 页面。  如果需要 [有关操作方式的提醒](#simulate-a-slower-network-connection) ，请导航到"模拟较慢的连接"。  
    Screenshots panel provides thumbnails of how the page looked at various points during the loading process.  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots.msft.png" alt-text="页面加载的屏幕截图" lightbox="../media/network-glitch-network-screenshots.msft.png":::
       页面加载的屏幕截图  
    :::image-end:::  
    
1.  选择第一个缩略图。  DevTools 显示当时发生的网络活动。  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots-first.msft.png" alt-text="第一张屏幕截图期间发生的网络活动" lightbox="../media/network-glitch-network-screenshots-first.msft.png":::
       第一张屏幕截图期间发生的网络活动  
    :::image-end:::  
    
1.  再次选择 (网络设置 \) "，然后关闭"捕获屏幕截图" ![ ](../media/settings-icon.msft.png) 复选框以关闭"屏幕截图"窗格。 ****
1.  再次刷新页面。  
    
## <a name="inspect-the-details-of-the-resource"></a>检查资源的详细信息  

选择资源以了解有关它的信息。  立即尝试：  

1.  选择 `getstarted.html` 。  将显示 **"标题** "面板。  使用此面板检查 HTTP 标头。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-headers.msft.png" alt-text=""标题"面板" lightbox="../media/network-glitch-network-resources-headers.msft.png":::
       " **标题"** 面板  
    :::image-end:::  
    
1.  选择" **预览"** 面板。  将显示 HTML 的基本呈现。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-preview.msft.png" alt-text="预览面板" lightbox="../media/network-glitch-network-resources-preview.msft.png":::
       预览**面板**  
    :::image-end:::  
    
    当 API 以 HTML 格式返回错误代码时，面板非常有用。  您可能会发现，读取呈现的 HTML 比 HTML 源代码更容易，在检查图像时也更容易阅读。  

1.  选择" **响应"** 面板。  将显示 HTML 源代码。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-response.msft.png" alt-text="响应面板" lightbox="../media/network-glitch-network-resources-response.msft.png":::
       响应**面板**  
    :::image-end:::  
    
    > [!TIP]
    > 缩小文件时，选择"响应"面板底部的"格式**\ (** ![ 格式 \) "按钮，以重新设置文件内容的格式，提高 ](../media/format-icon.msft.png) 可读性。 ****  
    
1.  选择" **计时"** 面板。  将显示资源的网络活动的细分。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-timing.msft.png" alt-text=""计时"面板" lightbox="../media/network-glitch-network-resources-timing.msft.png":::
       " **计时"** 面板  
    :::image-end:::  
    
1.  选择**关闭** \(![关闭](../media/close-icon.msft.png)\)以再次查看网络日志。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-close-tabs.msft.png" alt-text="关闭按钮" lightbox="../media/network-glitch-network-resources-close-tabs.msft.png":::
       “**关闭**”按钮  
    :::image-end:::  
    
## <a name="search-network-headers-and-responses"></a>搜索网络标头和响应  

当您需要搜索特定字符串或正则表达式的所有资源的 HTTP 标头和响应时，请使用“**搜索**”窗格。  

例如，假设你想要验证你的资源是否使用了合理的**缓存策略**。  

<!--TODO: add cache policies section when available  -->

1.  选择**搜索** \(![搜索](../media/search-icon.msft.png)\)。  搜索窗格将打开到网络日志的左侧。  
    
    :::image type="complex" source="../media/network-glitch-network-search-empty.msft.png" alt-text="“搜索”窗格" lightbox="../media/network-glitch-network-search-empty.msft.png":::
       “**搜索**”窗格  
    :::image-end:::  
    
1.  键入 `Cache-Control` 并选择 `Enter`。  “搜索”窗格列出它在资源标头或内容 `Cache-Control` 中查找到的所有实例。  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control.msft.png" alt-text="搜索的 Cache-Control" lightbox="../media/network-glitch-network-search-cache-control.msft.png":::
       以下项的搜索结果 `Cache-Control`  
    :::image-end:::  
    
1.  选择一个结果以查看其中找到结果的资源。  如果要查看资源的详细信息，请选择直接转到它的结果。  例如，如果在标头中发现查询，则 **"标题"面板** 将打开。   如果在内容中发现查询，将打开 **"响应"** 面板。  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png" alt-text=""标题"面板中突出显示的搜索结果" lightbox="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png":::
       "标题"面板中 **突出显示的** 搜索结果  
    :::image-end:::  
    
1.  关闭"搜索"窗格和 **"标题"** 面板。  
    
    :::image type="complex" source="../media/network-glitch-network-search-close.msft.png" alt-text="关闭按钮" lightbox="../media/network-glitch-network-search-close.msft.png":::
       **关闭**按钮  
    :::image-end:::  
    
## <a name="filter-resources"></a>筛选资源  

DevTools 提供了许多工作流，用于筛选出与当前任务不相关的资源。  

:::image type="complex" source="../media/network-glitch-network-filter-empty.msft.png" alt-text="“筛选器”工具栏" lightbox="../media/network-glitch-network-filter-empty.msft.png":::
   “**筛选器**”工具栏  
:::image-end:::  

默认情况下 **应** 打开"筛选器"工具栏。  如果不是：  

1.  选择**筛选器** \(![筛选器](../media/filter-icon.msft.png)\)来显示它。  
    
### <a name="filter-by-string-regular-expression-or-property"></a>按字符串、正则表达式或属性筛选  

“**筛选器**”文本框支持许多不同类型的筛选。  

1.  键入 `png` 到“**筛选器**”文本框。  只显示包含文本 `png` 的文件。  在这种情况下，与筛选器匹配的唯一文件是 PNG 图像。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-png.msft.png" alt-text="字符串筛选器" lightbox="../media/network-glitch-network-filter-png.msft.png":::
       字符串筛选器  
    :::image-end:::  
    
1.  键入 `/.*\.[cj]s+$/`。  DevTools 会筛选出文件名不以 `j` 或 `c` 结尾、后跟 1 个或多个 `s` 字符的任何资源。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-regex.msft.png" alt-text="正则表达式筛选器" lightbox="../media/network-glitch-network-filter-regex.msft.png":::
       正则表达式筛选器  
    :::image-end:::  
    
1.  键入 `-main.css`。  DevTools 筛选器出 `main.css`。  如果任何文件与模式匹配，还会筛选出 tit。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-negative-statement.msft.png" alt-text="负筛选器" lightbox="../media/network-glitch-network-filter-negative-statement.msft.png":::
       负筛选器  
    :::image-end:::  
    
1.  键入 `domain:cdn.glitch.com` 到“**筛选器**”文本框。  DevTools 筛选出 URL 不匹配此域的任何资源。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-property-value.msft.png" alt-text="属性筛选器" lightbox="../media/network-glitch-network-filter-property-value.msft.png":::
       属性筛选器  
    :::image-end:::  
    
    对于可筛选属性的完整列表，导航到按 [属性 筛选请求][DevtoolsReferenceProperty]。  
    
1.  清除任何文本的“**筛选器**”文本框。  
    
### <a name="filter-by-resource-type"></a>按资源类型筛选  

若要专注于某些类型的文件，如样式表：  

1.  选择**CSS**。  所有其他文件类型都筛选掉。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css.msft.png" alt-text="只显示 CSS 文件" lightbox="../media/network-glitch-network-filter-file-type-css.msft.png":::
       只显示 CSS 文件  
    :::image-end:::  
    
1.  若要同时显示脚本，请选择并按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) ，然后选择**JS。**  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css-js.msft.png" alt-text="只显示 CSS 和 JS 文件" lightbox="../media/network-glitch-network-filter-file-type-css-js.msft.png":::
       只显示 CSS 和 JS 文件  
    :::image-end:::  
    
1.  若要删除筛选器并再次显示所有资源，请选择"全部 **"。**  
    
对于其他筛选工作流，导航到"[筛选请求"。][DevtoolsNetworkReferenceFilter]  

## <a name="block-requests"></a>阻止请求  

当某些页面资源不可用时，页面的外观和行为如何？  它是完全失败，还是仍有点功能？  阻止查找请求：  

1.  选择 `Control`+`Shift`+`P` \(Windows、Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开**命令菜单**。  
    
    :::image type="complex" source="../media/network-glitch-network-cli-empty.msft.png" alt-text="命令菜单" lightbox="../media/network-glitch-network-cli-empty.msft.png":::
       **命令菜单**  
    :::image-end:::  
    
1.  键入 `block`，选择“**显示请求阻止**”，然后选择 `Enter`。  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block.msft.png" alt-text="显示请求阻止" lightbox="../media/network-glitch-network-cli-block.msft.png":::
       **显示请求阻止**  
    :::image-end:::  
    
1.  选择 **添加模式** \(![添加模式](../media/add-icon.msft.png)\)。  
1.  键入 `main.css`。  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-add-pattern.msft.png" alt-text="阻止 main.css" lightbox="../media/network-glitch-network-cli-block-add-pattern.msft.png":::
       阻止 `main.css`  
    :::image-end:::  
    
1.  选择“**添加**”。  
1.  刷新页面。  与预期一样，页面的样式会稍微混乱，因为主样式表已被阻止。  
    
    > [!NOTE]
    > 网络日志中的 `main.css` 行。  红色文本表示资源已被阻止。
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-main-css.msft.png" alt-text="main.css 已被阻止" lightbox="../media/network-glitch-network-cli-block-main-css.msft.png":::
       `main.css` 已被阻止  
    :::image-end:::  
    
1.  取消选中“**启用请求阻止**” 复选框。  

## <a name="conclusion"></a>总结  

恭喜，你已完成本教程。  现在，你已了解如何使用**** Microsoft Edge DevTools 中的网络工具！

导航到“[网络参考][DevtoolsNetworkReference]”以发现与检查网络活动相关的更多 DevTools 功能。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[CachePolicies]: ../../../web/tools/lighthouse/audits/cache-policy ""  -->  

[DevToolsCustomizePlacement]: ../customize/placement.md "更改 Microsoft Edge DevTools 放置 | Microsoft Docs"  
[DevtoolsNetworkReference]: ./reference.md "网络分析参考 | Microsoft Docs"
[DevtoolsNetworkReferenceFilter]: ./reference.md#filter-requests "筛选器请求 - 网络分析参考 | Microsoft Docs"  
[DevtoolsReferenceHideOverview]: ./reference.md#hide-the-overview-pane "隐藏“概述”窗格 - 网络分析参考 | Microsoft Docs"
[DevtoolsReferenceProperty]: ./reference.md#filter-requests-by-properties "按属性筛选请求 - 网络分析参考 | Microsoft Docs"
[DevToolsOpen]: ../open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsSpeedGetStarted]: ../speed/get-started.md "使用 Microsoft Edge DevTools 优化网站速度 | Microsoft Docs"  

[GlitchNetworkGetStarted]: https://microsoft-edge-chromium-devtools.glitch.me/static/network/getstarted.html "检查网络活动演示 | 小故障"  

[MDNHTTPCache]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP 缓存 | MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/network/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
