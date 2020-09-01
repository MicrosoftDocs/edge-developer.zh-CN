---
title: 使用 Microsoft Edge DevTools 中的 "覆盖范围" 选项卡查找未使用的 JavaScript 和 CSS 代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 1c03140199b26bca39e69cdfbe33cd1c524257fe
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10981850"
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





# 使用 Microsoft Edge DevTools 中的 "覆盖范围" 选项卡查找未使用的 JavaScript 和 CSS 代码   



Microsoft Edge DevTools 中的 "覆盖范围" 选项卡可帮助你查找未使用的 JavaScript 和 CSS 代码。  删除未使用的代码可能会加速你的页面加载和保存移动用户手机网络数据。  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage.msft.png" alt-text="分析代码覆盖率" lightbox="../media/coverage-sources-resource-drawer-coverage.msft.png":::
   分析代码覆盖率  
:::image-end:::  

> [!WARNING]
> 查找未使用的代码相对简单。  但要重构基本代码，以便每个页面仅提供它所需的 JavaScript 和 CSS。  本指南不介绍如何重构基本代码以避免未使用的代码，因为这些 refactors 高度依赖于你的技术堆栈。  

## 概述   

装运未使用的 JavaScript 或 CSS 是 web 开发中的常见问题。  例如，假设您想要在您的页面上使用 " [引导" 按钮组件][BootstrapButtons] 。  若要使用按钮组件，需要在 HTML 中添加指向引导样式表的链接，如下所示：  

```html
...
<head>
    ...
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    ...
</head>
...
```  

此样式表不仅仅包含按钮组件的代码。  它包含 **所有** 引导组件的 CSS。  但您没有使用任何其他的引导组件。  因此，你的页面将下载一组不需要的 CSS。  此额外的 CSS 是一个问题，原因如下。  

*   额外的代码将减慢页面负载。  <!--See [Render-Blocking CSS][render].  -->  
*   如果用户在移动设备上访问页面，则额外的代码将使用其手机网络数据。  
    
<!--[render]: /web/fundamentals/performance/critical-rendering-path/render-blocking-css  -->  

## 打开 "覆盖范围" 选项卡   

1.  [打开 "命令" 菜单][DevToolsCommandMenu]。  
1.  开始键入 `coverage` ，选择 " **显示覆盖率** " 命令，然后按 `Enter` 运行命令。  " **覆盖范围** " 选项卡将在 **抽屉**中打开。  

    :::image type="complex" source="../media/coverage-console-drawer-coverage-empty.msft.png" alt-text=""覆盖范围" 选项卡" lightbox="../media/coverage-console-drawer-coverage-empty.msft.png":::
       " **覆盖范围** " 选项卡  
    :::image-end:::  
    
## 记录代码覆盖率   

1.  单击 " **覆盖范围** " 选项卡中的以下按钮之一：  
    *   如果想要查看加载页面需要哪些代码，请单击 " **开始检测覆盖率" 并重新加载 page** \ (" ![ 开始检测覆盖率" 和 "重新加载页面 ][ImageReloadIcon] \ ) "。  
    *   **Instrument Coverage** ![ ][ImageRecordIcon] 如果想要查看在与页面交互之后使用的代码，请单击 "检测覆盖率" (检测覆盖率 ") 。  
1.  如果要停止记录代码覆盖率，请单击 " **停止检测覆盖率" 并显示结果** \ (![ 停止检测覆盖率和显示结果 ][ImageStopIcon] \ ) 。  
    
## 分析代码覆盖率   

" **覆盖率** " 选项卡中的表显示分析了哪些资源，以及每个资源中使用了多少代码。  单击某一行以在 " **源** " 面板中打开该资源，并查看所使用的代码和未使用的代码的逐行划分。  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage-selected.msft.png" alt-text=""代码覆盖率" 报表" lightbox="../media/coverage-sources-resource-drawer-coverage-selected.msft.png":::
   "代码覆盖率" 报表  
:::image-end:::  

*   **Url**列是已分析资源的 url。  
*   " **类型** " 列显示资源是否包含 CSS 和/或 JavaScript。  
*   " **字节总数** " 列是资源的总大小（以字节为单位）。  
*   " **未使用的字节** " 列表示未使用的字节数。  
*   最后一个未命名的列是 " **字节总数** " 和 " **未使用的字节** " 列的可视化。  条的红色部分是未使用的字节。  绿色部分使用字节。  
    
<!--  
 


-->  

<!-- image links -->  

[ImageReloadIcon]: ../media/reload-icon.msft.png  
[ImageRecordIcon]: ../media/record-icon.msft.png  
[ImageStopIcon]: ../media/stop-icon.msft.png  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"  

[BootstrapButtons]: https://getbootstrap.com/docs/4.3/components/buttons "按钮-引导"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/coverage/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
