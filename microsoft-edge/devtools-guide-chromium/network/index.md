---
description: 有关 Microsoft Edge DevTools 中最受欢迎的网络相关功能的教程。
title: 检查 Microsoft Edge DevTools 中的网络活动
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: a55ff05e29817c483cbf13b8713ef37cf96424d5
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125424"
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

# 检查 Microsoft Edge DevTools 中的网络活动  

这是一个动手教程，介绍了一些最常用的 DevTools 功能，这些功能与检查页面的网络活动相关。  

如果要浏览功能，请参阅“[网络参考][DevtoolsNetworkReference]”。  

<!--TODO: This entire section needs a Microsoft Edge DevTools re-write  -->

<!-- Read on, or watch the video version of this tutorial:  -->  

<!--
> [!VIDEO embed/e1gAyQuIFQo]  
-->

## 何时使用网络面板  

一般情况下，当您需要确保资源正在下载或上传时，请使用网络面板。  网络面板的最常见用例包括：  

*   确保资源上载或下载实际正在进行。  
*   检查单个资源的属性，如 HTTP 标头、内容、大小等。  
    
如果要寻找提高页面加载性能的方法，请**不要**从网络面板开始。  有许多类型的负载性能问题与网络活动不相关。  从“审核”面板开始，因为它为你提供了有关改进页面的目标建议。  请参阅“[优化网站速度][DevtoolsSpeedGetStarted]”。  

## 打开“网络”面板  

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
    
1.  按 `Control`+`Shift`+`J` \ (Windows、Linux\) 或 `Command`+`Option`+`J` \(macOS\) [打开 DevTools][DevToolsOpen]。  **控制台**面板打开。  
    
    :::image type="complex" source="../media/network-glitch-console.msft.png" alt-text="控制台" lightbox="../media/network-glitch-console.msft.png":::
       **控制台**  
    :::image-end:::  
    
    你可能更喜欢将 [DevTools 停靠到窗口底部][DevToolsCustomizePlacement]。  
    
    :::image type="complex" source="../media/network-glitch-console-bottom.msft.png" alt-text="停靠在窗口底部的 DevTools" lightbox="../media/network-glitch-console-bottom.msft.png":::
       停靠在窗口底部的 DevTools  
    :::image-end:::  
    
1.  选择 “**网络**” 选项卡。 **网络**面板将打开。  
    
    :::image type="complex" source="../media/network-glitch-network-bottom.msft.png" alt-text="固定到窗口底部的 DevTools 中的控制台工具" lightbox="../media/network-glitch-network-bottom.msft.png":::
       固定到窗口底部的 DevTools 中的**控制台**工具  
    :::image-end:::  
    
现在网络面板为空。  DevTools 仅在打开网络活动后记录网络活动，自打开 DevTools 后未发生网络活动。  

## 记录网络活动  

查看页面导致的网络活动：  

1.  重新加载页面。  网络面板在**网络日志**中记录所有网络活动。  
    
    :::image type="complex" source="../media/network-glitch-network.msft.png" alt-text="网络日志" lightbox="../media/network-glitch-network.msft.png":::
       **网络日志**  
    :::image-end:::  
    
    **网络日志**的每一行表示一个资源。  默认情况下，按时间顺序列出资源。  顶部资源通常是主 HTML 文档。  底部资源是最后请求的任何资源。  
    
    每个列表示有关资源的信息。  在上图中，将显示默认列。  

    *   **状态**。  响应的 HTTP 状态代码。  
    *   **类型**。  资源类型。  
    *   **发起程序**。  资源请求的原因。  选择“发起人”列中的链接将指向导致请求的源代码。  
    *   **时间**。  请求的持续时间。  
    *   **粘滞键**。  请求的不同阶段的图形表示形式。  将鼠标悬停在粘滞键上查看细目。  
    
    > [!NOTE]
    > 网络日志上方的图形称为“概述”。  本教程中不会使用概述图，因此可以隐藏它。  请参阅 [隐藏概述窗格][DevtoolsReferenceHideOverview]。
    
1.  打开 DevTools 后，它会在网络日志中记录网络活动。  
    若要演示这一点，请首先查看**网络日志** 的底部，并记下上一次活动。  
1.  现在，在演示中选择“**获取数据**”按钮。  
1.  再次查看**网络日志** 的底部。  你应该会看到一个称为 `getstarted.json` 的新资源。  选择“**获取数据**”按钮导致页面请求此文件。  
    
    :::image type="complex" source="../media/network-glitch-network-new-resource.msft.png" alt-text="网络日志中的新资源" lightbox="../media/network-glitch-network-new-resource.msft.png":::
       **网络日志**中的新资源  
    :::image-end:::  
    
## 显示详细信息  

网络日志的列是可配置的。  您可以隐藏您未使用的列。  
默认情况下，还有许多列处于隐藏状态，您可能会发现这些列很有用。  

1.  右键单击“网络日志”表的标头，然后选择“**域**”。  现在将显示每个资源的域。  
    
    :::image type="complex" source="../media/network-glitch-network-edit-column.msft.png" alt-text="启用“域”列" lightbox="../media/network-glitch-network-edit-column.msft.png":::
       启用“域”列  
    :::image-end:::  
    
    > [!TIP]
    > 通过将鼠标悬停在“**名称**”列中的单元格上，查看资源的完整URL。  
    
## 模拟较慢的网络连接  

用于构建站点的计算机的网络连接可能比用户的移动设备的网络连接速度快。  通过限制页面，可以更好地了解页面在移动设备上加载所花的时间。  

1.  选择“**限制**”下拉列表，它默认设置为“**联机**”。  
    
    :::image type="complex" source="../media/network-glitch-network-throttling.msft.png" alt-text="启用限制" lightbox="../media/network-glitch-network-throttling.msft.png":::
       启用限制  
    :::image-end:::  
    
1.  选择“**慢速 3G**”。  
    
    :::image type="complex" source="../media/network-glitch-network-throttling-slow-3g.msft.png" alt-text="选择慢速 3G" lightbox="../media/network-glitch-network-throttling-slow-3g.msft.png":::
       选择慢速 3G  
    :::image-end:::  
    
1.  长按**Reload** \(![Reload][ImageRefreshIcon]\) ，然后选择“**空缓存和硬重新加载**”。  
    
    :::image type="complex" source="../media/network-glitch-empty-cache-and-hard-reset.msft.png" alt-text="空缓存和硬重新加载" lightbox="../media/network-glitch-empty-cache-and-hard-reset.msft.png":::
       **空缓存和硬重新加载**  
    :::image-end:::  
    
    在重复访问时，浏览器通常会从[缓存][MDNHTTPCache]中提供一些文件，从而加快页面加载速度。  **空缓存和硬重新加载** 会强制浏览器访问所有资源的网络。  当你希望了解第一次访问者如何体验页面加载时，这会非常有用。  
    
    > [!NOTE]
    > **空缓存和硬重新加载**工作流仅在 DevTools 打开时可用。  
    
## 捕获屏幕截图  

屏幕截图使你可以查看页面在加载时的外观。  

1.  选择 \(![网络设置][ImageSettingsIcon] \) 选择**捕获屏幕截图**复选框。
1.  再次通过**空缓存和硬重新加载**工作流重新加载页面。  如果需要有关操作方式的提醒，请参阅“[模拟较慢的连接](#simulate-a-slower-network-connection)”。  
    “屏幕截图”窗格提供页面在加载过程中各个点的显示方式的缩略图。  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots.msft.png" alt-text="页面加载的屏幕截图" lightbox="../media/network-glitch-network-screenshots.msft.png":::
       页面加载的屏幕截图  
    :::image-end:::  
    
1.  选择第一个缩略图。  DevTools 显示当时发生的网络活动。  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots-first.msft.png" alt-text="第一张屏幕截图期间发生的网络活动" lightbox="../media/network-glitch-network-screenshots-first.msft.png":::
       第一张屏幕截图期间发生的网络活动  
    :::image-end:::  
    
1.  在此选择 \(![网络设置][ImageSettingsIcon]\) ，然后取消选中“**捕获屏幕截图**”复选框以关闭“屏幕截图”窗格。
1.  再次重新加载页面。  
    
## 检查资源的详细信息  

选择资源以了解有关它详细信息。  立即尝试：  

1.  选择 `getstarted.html`。  将显示**标头**选项卡。  使用此选项卡检查 HTTP 标头。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-headers.msft.png" alt-text="“标头”选项卡" lightbox="../media/network-glitch-network-resources-headers.msft.png":::
       “**标头**”选项卡  
    :::image-end:::  
    
1.  选择“**预览**” 选项卡。 显示 HTML 的基本呈现。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-preview.msft.png" alt-text="“预览”选项卡" lightbox="../media/network-glitch-network-resources-preview.msft.png":::
       “**预览**”选项卡  
    :::image-end:::  
    
    当 API 以 HTML 格式返回错误代码时，此选项卡非常有用。  您可能会发现，读取呈现的 HTML 比 HTML 源代码更容易，在检查图像时也更容易阅读。  

1.  选择“**响应**”选项卡。 将显示 HTML 源代码。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-response.msft.png" alt-text="“响应”选项卡" lightbox="../media/network-glitch-network-resources-response.msft.png":::
       “**响应**” 选项卡  
    :::image-end:::  
    
    > [!TIP]
    > 缩小文件时，选择“**响应**”选项卡底部的“**格式**” \(![格式][ImageFormatIcon] \) 按钮会重新设置文件内容的格式，以提高可读性。   
    
1.  选择“**计时**“选项卡。将显示此资源的网络活动的细分。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-timing.msft.png" alt-text="“计时”选项卡" lightbox="../media/network-glitch-network-resources-timing.msft.png":::
       “**计时**”选项卡  
    :::image-end:::  
    
1.  选择**关闭** \(![关闭][ImageCloseIcon]\)以再次查看网络日志。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-close-tabs.msft.png" alt-text="关闭按钮" lightbox="../media/network-glitch-network-resources-close-tabs.msft.png":::
       “**关闭**”按钮  
    :::image-end:::  
    
## 搜索网络标头和响应  

当您需要搜索特定字符串或正则表达式的所有资源的 HTTP 标头和响应时，请使用“**搜索**”窗格。  

例如，假设你想要验证你的资源是否使用了合理的**缓存策略**。  

<!--TODO: add cache policies section when available  -->

1.  选择**搜索** \(![搜索][ImageSearchIcon]\)。  搜索窗格将打开到网络日志的左侧。  
    
    :::image type="complex" source="../media/network-glitch-network-search-empty.msft.png" alt-text="“搜索”窗格" lightbox="../media/network-glitch-network-search-empty.msft.png":::
       “**搜索**”窗格  
    :::image-end:::  
    
1.  键入 `Cache-Control` 并选择 `Enter`。  “搜索”窗格列出它在资源标头或内容 `Cache-Control` 中查找到的所有实例。  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control.msft.png" alt-text="搜索的 Cache-Control" lightbox="../media/network-glitch-network-search-cache-control.msft.png":::
       以下项的搜索结果 `Cache-Control`  
    :::image-end:::  
    
1.  选择一个结果以查看找到结果的资源。  如果要查看资源的详细信息，请选择直接转到它的结果。  例如，如果在标头中找到了查询，则“标头”选项卡将打开。   如果在内容中发现查询，将打开“**响应**”选项卡。  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png" alt-text="“标头”选项卡中突出显示的搜索结果" lightbox="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png":::
       “**标头**”选项卡中突出显示的搜索结果  
    :::image-end:::  
    
1.  关闭“搜索”窗格和“标头”选项卡。  
    
    :::image type="complex" source="../media/network-glitch-network-search-close.msft.png" alt-text="关闭按钮" lightbox="../media/network-glitch-network-search-close.msft.png":::
       **关闭**按钮  
    :::image-end:::  
    
## 筛选资源  

DevTools 提供了许多工作流，用于筛选出与当前任务不相关的资源。  

:::image type="complex" source="../media/network-glitch-network-filter-empty.msft.png" alt-text="“筛选器”工具栏" lightbox="../media/network-glitch-network-filter-empty.msft.png":::
   “**筛选器**”工具栏  
:::image-end:::  

默认情况下应启用“**筛选器**”工具栏。  如果不是：  

1.  选择**筛选器** \(![筛选器][ImageFilterIcon]\)来显示它。  
    
### 按字符串、正则表达式或属性筛选  

“**筛选器**”文本框支持许多不同类型的筛选。  

1.  键入 `png` 到“**筛选器**”文本框。  只显示包含文本 `png` 的文件。  在这种情况下，与筛选器匹配的唯一文件是 PNG 图像。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-png.msft.png" alt-text="字符串筛选器" lightbox="../media/network-glitch-network-filter-png.msft.png":::
       字符串筛选器  
    :::image-end:::  
    
1.  键入 `/.*\.[cj]s+$/`。  DevTools 会筛选出文件名不以 `j` 或 `c` 结尾、后跟 1 个或多个 `s` 字符的任何资源。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-regex.msft.png" alt-text="正则表达式筛选器" lightbox="../media/network-glitch-network-filter-regex.msft.png":::
       正则表达式筛选器  
    :::image-end:::  
    
1.  键入 `-main.css`。  DevTools 筛选器出 `main.css`。  如果任何其他文件与模式匹配，也将筛选掉它们。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-negative-statement.msft.png" alt-text="负筛选器" lightbox="../media/network-glitch-network-filter-negative-statement.msft.png":::
       负筛选器  
    :::image-end:::  
    
1.  键入 `domain:cdn.glitch.com` 到“**筛选器**”文本框。  DevTools 筛选出 URL 不匹配此域的任何资源。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-property-value.msft.png" alt-text="属性筛选器" lightbox="../media/network-glitch-network-filter-property-value.msft.png":::
       属性筛选器  
    :::image-end:::  
    
    有关可筛选属性的完整列表，请参阅[按属性筛选请求][DevtoolsReferenceProperty]。  
    
1.  清除任何文本的“**筛选器**”文本框。  
    
### 按资源类型筛选  

若要专注于某些类型的文件，如样式表：  

1.  选择**CSS**。  所有其他文件类型都筛选掉。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css.msft.png" alt-text="只显示 CSS 文件" lightbox="../media/network-glitch-network-filter-file-type-css.msft.png":::
       只显示 CSS 文件  
    :::image-end:::  
    
1.  要查看脚本，按住 `Control` \(Windows、Linux\) 或 `Command` \ (macOS\) 然后选择 **JS**。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css-js.msft.png" alt-text="只显示 CSS 和 JS 文件" lightbox="../media/network-glitch-network-filter-file-type-css-js.msft.png":::
       只显示 CSS 和 JS 文件  
    :::image-end:::  
    
1.  选择**全部**删除筛选器并再次查看所有资源。  
    
请参阅其他筛选工作流的[筛选请求][DevtoolsNetworkReferenceFilter]。  

## 阻止请求  

当某些页面资源不可用时，页面的外观和行为如何？  它是完全失败，还是仍有点功能？  阻止查找请求：  

1.  选择 `Control`+`Shift`+`P` \(Windows、Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开**命令菜单**。  
    
    :::image type="complex" source="../media/network-glitch-network-cli-empty.msft.png" alt-text="命令菜单" lightbox="../media/network-glitch-network-cli-empty.msft.png":::
       **命令菜单**  
    :::image-end:::  
    
1.  键入 `block`，选择“**显示请求阻止**”，然后选择 `Enter`。  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block.msft.png" alt-text="显示请求阻止" lightbox="../media/network-glitch-network-cli-block.msft.png":::
       **显示请求阻止**  
    :::image-end:::  
    
1.  选择 **添加模式** \(![添加模式][ImageAddIcon]\)。  
1.  键入 `main.css`。  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-add-pattern.msft.png" alt-text="阻止 main.css" lightbox="../media/network-glitch-network-cli-block-add-pattern.msft.png":::
       阻止 `main.css`  
    :::image-end:::  
    
1.  选择“**添加**”。  
1.  重新加载页面。  与预期一样，页面的样式会稍微混乱，因为主样式表已被阻止。  
    
    > [!NOTE]
    > 网络日志中的 `main.css` 行。  红色文本表示资源已被阻止。
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-main-css.msft.png" alt-text="main.css 已被阻止" lightbox="../media/network-glitch-network-cli-block-main-css.msft.png":::
       `main.css` 已被阻止  
    :::image-end:::  
    
1.  取消选中“**启用请求阻止**” 复选框。  

## 总结  

恭喜，你已完成本教程。  现在，你已了解如何使用 Microsoft Edge DevTools 中的**网络**面板！

导航到“[网络参考][DevtoolsNetworkReference]”以发现与检查网络活动相关的更多 DevTools 功能。  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAddIcon]: ../media/add-icon.msft.png  
[ImageCloseIcon]: ../media/close-icon.msft.png  
[ImageFilterIcon]: ../media/filter-icon.msft.png  
[ImageFormatIcon]: ../media/format-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  
[ImageScreenshotsIcon]: ../media/screenshots-icon.msft.png  
[ImageSearchIcon]: ../media/search-icon.msft.png  
[ImageSettingsIcon]: ../media/settings-icon.msft.png

<!-- links -->  

<!--[CachePolicies]: ../../../web/tools/lighthouse/audits/cache-policy ""  -->  

[DevToolsCustomizePlacement]: ../customize/placement.md "更改 Microsoft Edge DevTools 放置 | Microsoft Docs"  
[DevtoolsNetworkReference]: ./reference.md "网络分析参考 | Microsoft Docs"
[DevtoolsNetworkReferenceFilter]: ./reference.md#filter-requests "筛选器请求 - 网络分析参考 | Microsoft Docs"  
[DevtoolsReferenceHideOverview]: ./reference.md#hide-the-overview-pane "隐藏“概述”窗格 - 网络分析参考 | Microsoft Docs"
[DevtoolsReferenceProperty]: ./reference.md#filter-requests-by-properties "按属性筛选请求 - 网络分析参考 | Microsoft Docs"
[DevToolsOpen]: ../open.md "打开 Microsoft Edge DevTools | Microsoft Docs"  
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
