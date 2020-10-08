---
description: Microsoft Edge DevTools 中最常用的网络相关功能的教程。
title: 检查 Microsoft Edge DevTools 中的网络活动
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 3629c2d3711716d6d4a837b29bffef4786eb6d3f
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993448"
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



这是与检查页面的网络活动相关的一些最常用的 DevTools 功能的实践教程。  

如果想要浏览功能，请参阅 [网络参考][DevtoolsNetworkReference] 。  

<!--TODO: This entire section needs a Microsoft Edge DevTools re-write  -->

<!-- Read on, or watch the video version of this tutorial:  -->  

<!--
> [!VIDEO embed/e1gAyQuIFQo]  
-->

## 何时使用网络面板   

一般情况下，当你需要确保按预期下载或上载资源时，请使用 "网络" 面板。  网络面板最常见的使用案例是：  

*   确保实际上载或下载资源。  
*   检查单个资源的属性，例如 HTTP 头、内容、大小等。  
    
如果你正在寻找提高页面加载性能的 **方法，请不要从** 网络面板开始。  有许多类型的加载性能问题与网络活动无关。  从 "审核" 面板开始，因为它为你提供了有关如何改进页面的目标建议。  请参阅 [优化网站速度][DevtoolsSpeedGetStarted]。  

## 打开 "网络" 面板   

若要充分利用本教程，请打开演示，然后尝试使用演示页面上的功能。  

1.  打开 [入门演示][GlitchNetworkGetStarted]。  
    
    :::image type="complex" source="../media/network-glitch-inspect-network-activity-demo.msft.png" alt-text="演示" lightbox="../media/network-glitch-inspect-network-activity-demo.msft.png":::
       演示  
    :::image-end:::  
    
    <!--You may prefer to move the demo to a separate window.  -->  
    
    <!--
    :::image type="complex" source="../media/network-tutorial/windows.msft.png" alt-text="演示" lightbox="../media/network-tutorial/windows.msft.png":::
       The demo in one window and this tutorial in a different window  
    :::image-end:::  
    -->
    
1.  [Open DevTools][DevToolsOpen]按 `Control` + `Shift` + `J` \ (Windows \ ) 或 `Command` + `Option` + `J` \ (macOS \ ) 打开 DevTools。  此时将打开 " **控制台** " 面板。  
    
    :::image type="complex" source="../media/network-glitch-console.msft.png" alt-text="演示" lightbox="../media/network-glitch-console.msft.png":::
       该 **控制台**  
    :::image-end:::  
    
    您可能希望将 [DevTools 停靠在窗口底部][DevToolsCustomizePlacement]。  
    
    :::image type="complex" source="../media/network-glitch-console-bottom.msft.png" alt-text="演示" lightbox="../media/network-glitch-console-bottom.msft.png":::
       DevTools 停靠在窗口底部  
    :::image-end:::  
    
1.  选择 " **网络** " 选项卡。 "网络" 面板将打开。  
    
    :::image type="complex" source="../media/network-glitch-network-bottom.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-bottom.msft.png":::
       DevTools 停靠在窗口底部  
    :::image-end:::  
    
现在，网络面板为空。  DevTools 仅在打开网络活动后记录网络活动，并且自打开 DevTools 后未发生任何网络活动。  

## 记录网络活动   

要查看页面导致的网络活动，请执行以下操作：  

1.  重新加载页面。  "网络" 面板将在 **网络日志**中记录所有网络活动。  
    
    :::image type="complex" source="../media/network-glitch-network.msft.png" alt-text="演示" lightbox="../media/network-glitch-network.msft.png":::
       **网络日志**  
    :::image-end:::  
    
    **网络日志**的每一行表示一个资源。  默认情况下，资源按时间顺序列出。  顶部资源通常是主 HTML 文档。  最底层的资源是最后请求的内容。  
    
    每列表示有关资源的信息。  在上图中，显示默认列。  

    *   **状态**。  用于响应的 HTTP 状态代码。  
    *   **类型**。  资源类型。  
    *   **启动器**。  资源请求的原因。  选择 "发起方" 列中的链接将转到导致请求的源代码。  
    *   **时间**。  请求的持续时间。  
    *   **瀑布**图。  请求的不同阶段的图形表示形式。  将鼠标悬停在瀑布上以查看细目。  
    
    > [!NOTE]
    > 网络日志上方的图形称为概述。  您将不使用本教程中的概述图形，因此您可以将其隐藏。  请参阅 [隐藏概述窗格][DevtoolsReferenceHideOverview]。
    
1.  打开 DevTools 后，它将在网络日志中记录网络活动。  
    若要演示此操作，请首先查看 **网络日志** 的底部，并注意最后一个活动。  
1.  现在，选择演示中的 " **获取数据** " 按钮。  
1.  再次查看 **网络日志** 的底部。  你应该会看到一个名为 `getstarted.json` 的新资源。  选择 " **获取数据** " 按钮导致页面请求该文件。  
    
    :::image type="complex" source="../media/network-glitch-network-new-resource.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-new-resource.msft.png":::
       **网络日志**中的新资源  
    :::image-end:::  
    
## 显示详细信息   

网络日志的列是可配置的。  您可以隐藏未使用的列。  
默认情况下，在默认情况下会隐藏许多列，您可能会发现这些列很有用。  

1.  右键单击网络日志表的标题，然后选择 " **域**"。  现在显示了每个资源的域。  
    
    :::image type="complex" source="../media/network-glitch-network-edit-column.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-edit-column.msft.png":::
       启用 "域" 列  
    :::image-end:::  
    
    > [!TIP]
    > 通过将鼠标悬停在 " **名称** " 列中的单元格上，查看资源的完整 URL。  
    
## 模拟速度较慢的网络连接   

用于构建网站的计算机的网络连接可能比用户移动设备的网络连接速度更快。  通过限制页面，可以更好地了解页面在移动设备上的加载时间。  

1.  选择 " **限制** " 下拉列表，默认设置为 " **联机** "。  
    
    :::image type="complex" source="../media/network-glitch-network-throttling.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-throttling.msft.png":::
       启用限制  
    :::image-end:::  
    
1.  选择 " **慢速 3g**"。  
    
    :::image type="complex" source="../media/network-glitch-network-throttling-slow-3g.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-throttling-slow-3g.msft.png":::
       选择慢速3G  
    :::image-end:::  
    
1.  长按 **重新加载** \ (![ 重装 ][ImageRefreshIcon] \ ) 然后选择 " **清空缓存" 和 "硬重新加载**"。  
    
    :::image type="complex" source="../media/network-glitch-empty-cache-and-hard-reset.msft.png" alt-text="演示" lightbox="../media/network-glitch-empty-cache-and-hard-reset.msft.png":::
       **清空缓存和硬重载**  
    :::image-end:::  
    
    在重复访问时，浏览器通常会从 [缓存][MDNHTTPCache]中处理某些文件，从而加速页面加载。  **清空缓存和硬重新加载** 会强制浏览器为所有资源访问网络。  如果你想要了解第一次访问者体验页面加载的方式，这很有帮助。  
    
    > [!NOTE]
    > 只有在 DevTools 处于打开状态时， **空缓存和硬加载** 工作流才可用。  
    
## 捕获屏幕截图   

屏幕截图使你可以查看页面在加载时如何在一段时间内查看。  

1.  选择 \ (![ 网络设置 ][ImageSettingsIcon] \ ) 并选择 " **捕获屏幕截图** " 复选框。
1.  通过 **空缓存和硬重装** 工作流重新加载页面。  如果需要有关如何执行此操作的提醒，请参阅 [模拟低速连接](#simulate-a-slower-network-connection) 。  
    "屏幕截图" 窗格提供在加载过程中如何在不同点查看页面的缩略图。  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-screenshots.msft.png":::
       页面加载的屏幕截图  
    :::image-end:::  
    
1.  选择第一个缩略图。  DevTools 显示当时正在发生的网络活动。  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots-first.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-screenshots-first.msft.png":::
       第一个屏幕截图期间发生的网络活动  
    :::image-end:::  
    
1.  再次选择 \ (![ 网络设置 ][ImageSettingsIcon] \ ) 并取消选中 " **捕获屏幕截图** " 复选框以关闭屏幕截图窗格。
1.  重新加载页面。  
    
## 检查资源的详细信息   

选择资源以了解有关它的详细信息。  立即试用：  

1.  选择 `getstarted.html` 。  显示 " **标题** " 选项卡。  使用此选项卡检查 HTTP 头。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-headers.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-resources-headers.msft.png":::
       " **页眉** " 选项卡  
    :::image-end:::  
    
1.  选择 " **预览** " 选项卡。 显示 HTML 的基本呈现。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-preview.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-resources-preview.msft.png":::
       " **预览** " 选项卡  
    :::image-end:::  
    
    当 API 返回 HTML 中的错误代码时，此选项卡很有帮助。  您可能会发现，阅读呈现的 HTML 比 HTML 源代码或检查图像更容易。  

1.  选择 " **响应** " 选项卡。 将显示 HTML 源代码。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-response.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-resources-response.msft.png":::
       " **响应** " 选项卡  
    :::image-end:::  
    
    > [!TIP]
    > 当文件为 minified 时，选择**Format** ![ ][ImageFormatIcon] "**响应**" 选项卡底部的 "格式 \ (格式 \ ) " 按钮可重新设置文件内容的格式，以提高可读性。  
    
1.  选择 " **计时** " 选项卡。 将显示此资源的网络活动细目。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-timing.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-resources-timing.msft.png":::
       " **计时** " 选项卡  
    :::image-end:::  
    
1.  选择 " **关闭** \ (![ 关闭 ][ImageCloseIcon] \ ) " 再次查看网络日志。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-close-tabs.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-resources-close-tabs.msft.png":::
       " **关闭** " 按钮  
    :::image-end:::  
    
## 搜索网络标题和响应   

当你需要在 HTTP 头和所有资源的响应中搜索特定字符串或正则表达式的响应时，请使用 " **搜索** " 窗格。  

例如，假设你想要验证你的资源是否使用了合理的 **缓存策略**。  

<!--TODO: add cache policies section when available  -->

1.  选择 " **搜索** \ (![ 搜索 ][ImageSearchIcon] \ ) "。  "搜索" 窗格将在网络日志的左侧打开。  
    
    :::image type="complex" source="../media/network-glitch-network-search-empty.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-search-empty.msft.png":::
       " **搜索** " 窗格  
    :::image-end:::  
    
1.  键入 `Cache-Control` ，然后按 `Enter` 。  "搜索" 窗格 `Cache-Control` 会列出它在 "资源标题" 或 "内容" 中找到的所有实例。  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-search-cache-control.msft.png":::
       以下项的搜索结果 `Cache-Control`  
    :::image-end:::  
    
1.  选择一个结果以查看在其中找到结果的资源。  如果要查看资源的详细信息，请选择要直接转到该资源的结果。  例如，如果在页眉中找到查询，则 "页眉" 选项卡将打开。   如果在内容中找到查询，将打开 " **响应** " 选项卡。  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png":::
       " **页眉** " 选项卡中突出显示的搜索结果  
    :::image-end:::  
    
1.  关闭 "搜索" 窗格和 "标题" 选项卡。  
    
    :::image type="complex" source="../media/network-glitch-network-search-close.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-search-close.msft.png":::
       " **关闭** " 按钮  
    :::image-end:::  
    
## 筛选资源   

DevTools 提供了大量工作流，用于筛选出与手边的任务无关的资源。  

:::image type="complex" source="../media/network-glitch-network-filter-empty.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-filter-empty.msft.png":::
   " **筛选器** " 工具栏  
:::image-end:::  

默认情况下，应启用 " **筛选器** " 工具栏。  如果未执行此操作：  

1.  选择 " **筛选** \ (![ 筛选器 \ ) " ][ImageFilterIcon] 以显示它。  
    
### 按字符串、正则表达式或属性筛选   

**筛选**文本框支持许多不同类型的筛选。  

1.  在 `png` " **筛选器** " 文本框中键入内容。  仅显示包含文本的文件 `png` 。  在这种情况下，只有与筛选器匹配的文件才是 PNG 图像。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-png.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-filter-png.msft.png":::
       字符串筛选器  
    :::image-end:::  
    
1.  键入 `/.*\.[cj]s+$/`。  DevTools 筛选出文件名不以 a `j` 或 `c` 后跟1或更多字符结尾的任何资源 `s` 。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-regex.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-filter-regex.msft.png":::
       正则表达式筛选  
    :::image-end:::  
    
1.  键入 `-main.css`。  DevTools 筛选器 `main.css` 。  如果任何其他文件与模式匹配，它们也将被筛选掉。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-negative-statement.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-filter-negative-statement.msft.png":::
       负滤波器  
    :::image-end:::  
    
1.  在 `domain:cdn.glitch.com` " **筛选器** " 文本框中键入内容。  DevTools 筛选出具有与此域不匹配的 URL 的任何资源。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-property-value.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-filter-property-value.msft.png":::
       属性筛选器  
    :::image-end:::  
    
    有关筛选属性的完整列表，请参阅 [筛选请求][DevtoolsReferenceProperty] 。  
    
1.  清除任何文本的 " **筛选器** " 文本框。  
    
### 按资源类型筛选   

关注特定类型的文件，例如样式表：  

1.  选择 " **CSS**"。  将筛选出所有其他文件类型。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-filter-file-type-css.msft.png":::
       仅显示 CSS 文件  
    :::image-end:::  
    
1.  若要查看脚本，请按住 `Control` (Windows \ ) 或 `Command` \ (macOS \ ) ，然后选择 " **JS**"。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css-js.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-filter-file-type-css-js.msft.png":::
       仅显示 CSS 和 JS 文件  
    :::image-end:::  
    
1.  选择 " **全部** " 以删除筛选器并再次查看所有资源。  
    
请参阅 [筛选请求][DevtoolsNetworkReferenceFilter] 以获取其他筛选工作流。  

## 阻止请求   

当某些页面资源不可用时，页面的外观和行为  它是否完全失败，或者是否仍有运行？  阻止请求以查明：  

1.  按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "**命令" 菜单**。  
    
    :::image type="complex" source="../media/network-glitch-network-cli-empty.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-cli-empty.msft.png":::
       **命令菜单**  
    :::image-end:::  
    
1.  键入 `block` ，选择 " **显示请求阻止**"，然后按 `Enter` 。  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-cli-block.msft.png":::
       **显示请求阻止**  
    :::image-end:::  
    
1.  选择 " **添加模式** \ (![ 添加模式 ][ImageAddIcon] \ ) "。  
1.  键入 `main.css`。  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-add-pattern.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-cli-block-add-pattern.msft.png":::
       阻止 `main.css`  
    :::image-end:::  
    
1.  选择**添加**。  
1.  重新加载页面。  正常情况下，页面的样式会略微 messed，因为主样式表已被阻止。  
    
    > [!NOTE]
    > `main.css`网络日志中的行。  红色文本表示资源已被阻止。
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-main-css.msft.png" alt-text="演示" lightbox="../media/network-glitch-network-cli-block-main-css.msft.png":::
       `main.css` 已被阻止  
    :::image-end:::  
    
1.  取消选中 " **启用请求阻止** " 复选框。  

## 总结  

恭喜，你已完成教程。  您现在知道如何在 Microsoft Edge DevTools 中使用 " **网络** " 面板！

<!--




-->  

查看 [网络参考][DevtoolsNetworkReference] 以发现更多与检查网络活动相关的 DevTools 功能。  

<!--  
 


-->  

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

[DevToolsCustomizePlacement]: ../customize/placement.md "更改 Microsoft Edge DevTools 位置 |Microsoft 文档"  
[DevtoolsNetworkReference]: ./reference.md "网络分析参考 |Microsoft 文档"
[DevtoolsNetworkReferenceFilter]: ./reference.md#filter-requests "筛选请求-网络分析参考 |Microsoft 文档"  
[DevtoolsReferenceHideOverview]: ./reference.md#hide-the-overview-pane "隐藏 "概述" 窗格-网络分析参考 |Microsoft 文档"
[DevtoolsReferenceProperty]: ./reference.md#filter-requests-by-properties "按属性筛选请求-网络分析参考 |Microsoft 文档"
[DevToolsOpen]: ../open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsSpeedGetStarted]: ../speed/get-started.md "通过 Microsoft Edge DevTools 优化网站速度 |Microsoft 文档"  

[GlitchNetworkGetStarted]: https://microsoft-edge-chromium-devtools.glitch.me/static/network/getstarted.html "检查网络活动演示 |故障"  

[MDNHTTPCache]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP 缓存 |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/network/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
