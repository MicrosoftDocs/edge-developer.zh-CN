---
description: 如何在 Microsoft Edge DevTools 中查找和分析未使用的 JavaScript 和 CSS 代码。
title: 使用 Microsoft Edge DevTools 中的“覆盖范围”面板查找未使用的 JavaScript 和 CSS 代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: b31d14feac13a907ca0c5ce7ef702bcdef375ad5
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564460"
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
# <a name="find-unused-javascript-and-css-code-with-the-coverage-panel-in-microsoft-edge-devtools"></a>使用 Microsoft Edge DevTools 中的“覆盖范围”面板查找未使用的 JavaScript 和 CSS 代码  

Microsoft Edge DevTools 中的“**覆盖范围**”面板可帮助你查找未使用的 JavaScript 和 CSS 代码。  删除未使用的代码可能会加快页面加载速度并保存移动用户的手机网络数据。  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage.msft.png" alt-text="正在分析代码覆盖范围" lightbox="../media/coverage-sources-resource-drawer-coverage.msft.png":::
   正在分析代码覆盖范围  
:::image-end:::  

> [!WARNING]
> 查找未使用的代码相对容易。  但重构代码库以便每个页面仅提供所需的 JavaScript 和 CSS 可能非常困难。  本指南未涵盖如何重构基本代码以避免未使用的代码，因为这些重构高度依赖于你的技术堆叠。  

## <a name="overview"></a>概述  

寄送未使用的 JavaScript 或 CSS 是 web 开发中的一个常见问题。  例如，假设你想要在页面上使用“[Bootstrap 按钮组件][BootstrapButtons]”。  若要使用按钮组件，你需要在 HTML 中添加指向 Bootstrap 样式表的链接，如下所示：  

```html
...
<head>
    ...
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    ...
</head>
...
```  

此样式表不仅包括按钮组件的代码。  它包含**所有**Bootstrap 组件的 CSS。  但是，你未使用任何其他 Bootstrap 组件。  因此，你的页面正在下载一组不需要的 CSS。  由于以下原因，此额外的 CSS 是一个问题。  

*   额外的代码会降低页面加载速度。  <!--Navigate to [Render-Blocking CSS][render].  -->  
*   如果用户在移动设备上访问页面，则额外的代码会使用其手机网络数据。  
    
<!--[render]: /web/fundamentals/performance/critical-rendering-path/render-blocking-css  -->  

## <a name="open-the-coverage-panel"></a>打开“覆盖范围”面板  

1.  [打开“命令”菜单][DevToolsCommandMenu]。  
1.  开始键入`coverage`，选择“**显示覆盖范围**”命令，然后选择`Enter`以运行该命令。  在“**工具箱**”中打开“**覆盖范围**”面板。  

    :::image type="complex" source="../media/coverage-console-drawer-coverage-empty.msft.png" alt-text="“覆盖范围”面板" lightbox="../media/coverage-console-drawer-coverage-empty.msft.png":::
       “**覆盖范围**”面板  
    :::image-end:::  
    
## <a name="record-code-coverage"></a>记录代码覆盖范围  

1.  在“**覆盖范围**”面板中选择以下按钮之一。  
    *   若要查看加载页面所需的代码，选择“**开始检测覆盖范围并重新加载页面**” \(“![开始检测覆盖范围并重新加载页面](../media/reload-icon.msft.png)”\)。  
    *   若要查看与页面交互后使用的代码，选择“**检测覆盖范围**” \(“![检测覆盖范围](../media/record-icon.msft.png)”\)。  
1.  若要停止记录代码覆盖范围，选择“**停止检测覆盖范围并显示结果**” \(“![停止检测覆盖范围并显示结果](../media/stop-icon.msft.png)”\)。  
    
## <a name="analyze-code-coverage"></a>分析代码覆盖范围  

“**覆盖范围**”面板中的表显示已分析的资源，以及每个资源中使用的代码数。  选择一行以在"源"工具**** 中打开该资源，并查看已用代码和未使用代码的行细分。  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage-selected.msft.png" alt-text="代码覆盖范围报告" lightbox="../media/coverage-sources-resource-drawer-coverage-selected.msft.png":::
   代码覆盖范围报告  
:::image-end:::  

*   “**URL**”列是已分析资源的 URL。  
*   “**类型**”列显示资源是否包含 CSS、JavaScript 还是同时包含两者。  
*   “**字节总数**”列是资源的总大小（以字节为单位）。  
*   “**未使用字节数**”列是没有使用的字节数。  
*   最后一个未命名列是“**总字节数**”和“**未使用字节数**”列的可视化效果。  条形图的红色部分是未使用字节数。  绿色部分是已使用字节数。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行命令| Microsoft Docs"  

[BootstrapButtons]: https://getbootstrap.com/docs/4.3/components/buttons "按钮 - Bootstrap"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/coverage/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
