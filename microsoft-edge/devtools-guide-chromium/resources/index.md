---
title: 通过 Microsoft Edge DevTools 查看页面资源
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 4265841501bdd74d2976ecab1c2a07f1fb215535
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10984405"
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





# 通过 Microsoft Edge DevTools 查看页面资源   

  

本指南将教你如何使用 Microsoft Edge DevTools 查看网页的资源。  资源是页面需要正确显示的文件。  资源示例包括 CSS、JavaScript 和 HTML 文件以及图像。  

本指南假定你熟悉 [web 开发][MDNLearnWebDevelopment] 和 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]的基础知识。  

## 打开资源   

当您知道要检查的资源的名称时，" **命令" 菜单** 将提供打开资源的快速方法。  

1.  按 `Control` + `P` \ (Windows \ ) 或 `Command` + `P` \ (macOS \ ) 。  " **打开文件** " 对话框随即打开。  
    
    :::image type="complex" source="../media/resources-command-menu-empty.msft.png" alt-text=""打开文件" 对话框" lightbox="../media/resources-command-menu-empty.msft.png":::
       " **打开文件** " 对话框  
    :::image-end:::  
    
1.  从下拉列表中选择文件，或者开始键入文件名，然后按 `Enter` 一次 "自动完成" 框中突出显示正确的文件。  
    
    :::image type="complex" source="../media/resources-command-menu-file-search.msft.png" alt-text="在 "打开文件" 对话框中键入文件名" lightbox="../media/resources-command-menu-file-search.msft.png":::
       在 " **打开文件** " 对话框中键入文件名  
    :::image-end:::  
    
### 在 "网络" 面板中打开资源   

请参阅 [检查资源的详细信息][DevtoolsNetworkInspectDetailsResource]。  

:::image type="complex" source="../media/resources-network-response.msft.png" alt-text="在 "网络" 面板中检查资源" lightbox="../media/resources-network-response.msft.png":::
   在 " **网络** " 面板中检查资源  
:::image-end:::  

### 从其他面板中的 "网络" 面板中显示资源   

下面的 [浏览资源](#browse-resources) 部分介绍了如何从 DevTools UI 的各个部分查看资源。  如果您想要在 " **网络** " 面板中检查资源，请右键单击该资源，然后 **在 "网络" 面板中选择 "显示**"。  

:::image type="complex" source="../media/resources-sources-page-reveal-in-network-panel.msft.png" alt-text="在网络面板中显示" lightbox="../media/resources-sources-page-reveal-in-network-panel.msft.png":::
   **在网络面板中显示**  
:::image-end:::  

## 浏览资源   

### 浏览网络面板中的资源   

请参阅 [记录网络活动][DevtoolsNetworkLogActivity]。  

:::image type="complex" source="../media/resources-network-resources.msft.png" alt-text="网络日志中的页面资源" lightbox="../media/resources-network-resources.msft.png":::
   **网络**日志中的页面资源  
:::image-end:::  

### 按目录浏览   

若要查看按目录组织的页面资源，请执行以下操作：  

1.  单击 " **源** " 选项卡以打开 " **源** " 面板。  
1.  单击 " **页面** " 选项卡以显示页面的资源。  **页面**窗格随即打开。  
    
    :::image type="complex" source="../media/resources-sources-page-empty.msft.png" alt-text="页面窗格" lightbox="../media/resources-sources-page-empty.msft.png":::
       **页面**窗格  
    :::image-end:::  
    
    下面是上图中不明显的项目的细目。  
    
    | 页面项目 | 描述 |  
    |:--- |:--- |  
    | `top` | 主文档 [浏览上下文][MDNInlineFrame]。 |  
    | `airhorner.com` | 域。  嵌套在它下方的所有资源都来自该域。  例如，文件的完整 URL `comlink.global.j` 可能 `https://airhorner.com/scripts/comlink.global.js` 。 |  
    | `scripts` | 目录。 |  
    | `(index)` | 主 HTML 文档。 |  
    | `sw.js` | 服务工作运行时上下文。 |  
    
1.  单击某个资源以在 **编辑器**中查看它。  
    
    :::image type="complex" source="../media/resources-sources-page-resource.msft.png" alt-text="在编辑器中查看文件" lightbox="../media/resources-sources-page-resource.msft.png":::
       在**编辑器**中查看文件  
    :::image-end:::  
    
### 按文件名浏览   

默认情况下， **页面** 窗格按目录对资源进行分组。  若要禁用此分组并以简单列表的形式查看每个域的资源，请执行以下操作：  

1.  打开 **页面** 窗格。  请参阅 [按目录浏览](#browse-by-directory)。  
1.  单击 " **更多选项**" `...` ，然后禁用 " **按文件夹分组**"。  
    
    :::image type="complex" source="../media/resources-sources-page-resource-group-by-folder.msft.png" alt-text=""按文件夹分组" 选项" lightbox="../media/resources-sources-page-resource-group-by-folder.msft.png":::
       " **按文件夹分组** " 选项  
    :::image-end:::  
    
    按文件类型对资源进行组织。  在每个文件类型中，资源按字母顺序排列。  
    
    :::image type="complex" source="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png" alt-text="禁用 "按文件夹分组" 后的页面窗格" lightbox="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png":::
       禁用 "**按文件夹分组**" 后的**页面**窗格  
    :::image-end:::  
    
### 按文件类型浏览   

根据文件类型将资源组合在一起：  

1.  单击 " **应用程序** " 选项卡。 将打开 " **应用程序** " 面板。  默认情况下， **清单** 窗格通常首先打开。  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner.msft.png" alt-text="应用程序面板" lightbox="../media/resources-application-mainfest-airhorner.msft.png":::
       **应用程序**面板  
    :::image-end:::  
    
1.  向下滚动到 " **框架** " 窗格。  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png" alt-text=""框架" 窗格" lightbox="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png":::
       " **框架** " 窗格  
    :::image-end:::  
    
1.  展开感兴趣的分区。  
1.  单击资源进行查看。  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png" alt-text="在 "应用程序" 面板中查看资源" lightbox="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png":::
       在 " **应用程序** " 面板中查看资源  
    :::image-end:::  
    
#### 通过 "网络" 面板中的类型浏览文件   

请参阅 [按资源类型筛选][DevtoolsNetworkFilterByResourceType]。  

:::image type="complex" source="../media/resources-network-resources-filter-css.msft.png" alt-text="在网络日志中筛选 CSS" lightbox="../media/resources-network-resources-filter-css.msft.png":::
   在 **网络** 日志中筛选 CSS  
:::image-end:::  

<!--  
  


-->  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  
[DevtoolsNetworkFilterByResourceType]: ../network/index.md#filter-by-resource-type "按资源类型筛选-检查 Microsoft Edge DevTools 中的网络活动 |Microsoft 文档"  
[DevtoolsNetworkInspectDetailsResource]: ../network/index.md#inspect-the-details-of-the-resource "检查 Microsoft Edge DevTools | 中的资源检查网络活动的详细信息 |Microsoft 文档"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity "记录网络活动-在 Microsoft Edge DevTools 中检查网络活动 |Microsoft 文档"  

[MDNInlineFrame]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>：嵌入式框架元素 |MDN"  
[MDNLearnWebDevelopment]: https://developer.mozilla.org/docs/Learn "了解 web 开发 |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/resources/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
