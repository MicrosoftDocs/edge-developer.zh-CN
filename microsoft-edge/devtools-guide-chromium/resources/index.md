---
description: 按框架、域、类型或其他条件组织资源。
title: 使用 Microsoft Edge DevTools 查看页面资源
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 75063b23f23c25ff4fe2e7f6e044a2de9a7b1ccd
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398222"
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

# <a name="view-page-resources-with-microsoft-edge-devtools"></a>使用 Microsoft Edge DevTools 查看页面资源  

本指南指导你如何使用 Microsoft Edge DevTools 查看网页的资源。  资源是页面正确显示所需的文件。  资源示例包括 CSS、JavaScript 和 HTML 文件以及图像。  

本指南假定你熟悉 Web 开发和 Microsoft Edge [][MDNLearnWebDevelopment] [DevTools 的基础知识][MicrosoftEdgeDevTools]。  

## <a name="open-resources"></a>打开资源  

当您知道要检查的资源的名称时，命令菜单提供了一种快速打开**** 资源的方法。  

1.  选择 `Control` + `P` \ (Windows、Linux\) `Command` + `P` 或 \ (macOS\) 。  将 **打开"打开文件** "对话框。  
    
    :::image type="complex" source="../media/resources-command-menu-empty.msft.png" alt-text=""打开文件"对话框" lightbox="../media/resources-command-menu-empty.msft.png":::
       " **打开文件"** 对话框  
    :::image-end:::  
    
1.  从下拉列表中选择文件，或开始键入文件名，在自动完成框中突出显示正确的文件后 `Enter` 选择。  
    
    :::image type="complex" source="../media/resources-command-menu-file-search.msft.png" alt-text="在"打开文件"对话框中键入文件名" lightbox="../media/resources-command-menu-file-search.msft.png":::
       在"打开文件"对话框中 **键入** 文件名  
    :::image-end:::  
    
### <a name="open-resources-in-the-network-tool"></a>在"网络"工具中打开资源  

导航[到"检查资源的详细信息"。][DevtoolsNetworkInspectDetailsResource]  

:::image type="complex" source="../media/resources-network-response.msft.png" alt-text="检查网络工具中的资源" lightbox="../media/resources-network-response.msft.png":::
   检查网络工具 **中的** 资源  
:::image-end:::  

### <a name="reveal-resources-in-the-network-tool-from-other-panels"></a>显示来自其他面板的网络工具中的资源  

下面的 ["](#browse-resources) 浏览资源"部分显示如何查看来自 DevTools UI 的各个部分的资源。  如果你曾经想要检查**网络**工具中的资源，请将鼠标悬停在资源上，打开上下文菜单 \ (右键单击\) ，然后选择"网络"面板中的"展示 **"。**  

:::image type="complex" source="../media/resources-sources-page-reveal-in-network-panel.msft.png" alt-text=""在网络"面板中显示" lightbox="../media/resources-sources-page-reveal-in-network-panel.msft.png":::
   **"在网络"面板中显示**  
:::image-end:::  

## <a name="browse-resources"></a>浏览资源  

### <a name="browse-resources-in-the-network-panel"></a>在"网络"面板中浏览资源  

导航到["记录网络活动"。][DevtoolsNetworkLogActivity]  

:::image type="complex" source="../media/resources-network-resources.msft.png" alt-text="网络日志中的页面资源" lightbox="../media/resources-network-resources.msft.png":::
   网络日志中 **的页面** 资源  
:::image-end:::  

### <a name="browse-by-directory"></a>按目录浏览  

若要查看按目录组织的页面的资源，  

1.  选择 **"源** "工具打开"源 **"** 面板。  
1.  选择 **"页面** "面板以显示页面的资源。  将 **打开"页面** "窗格。  
    
    :::image type="complex" source="../media/resources-sources-page-empty.msft.png" alt-text="“页面”窗格" lightbox="../media/resources-sources-page-empty.msft.png":::
       " **页面"** 面板  
    :::image-end:::  
    
    下面对上图中的不明显项进行细分。  
    
    | 页面项 | 说明 |  
    |:--- |:--- |  
    | `top` | 主文档 [浏览上下文][MDNInlineFrame]。 |  
    | `airhorner.com` | 域。  嵌套在它下的所有资源都来自该域。  例如，文件的完整 URL `comlink.global.j` 可能是 `https://airhorner.com/scripts/comlink.global.js` 。 |  
    | `scripts` | 目录。 |  
    | `(index)` | 主 HTML 文档。 |  
    | `sw.js` | 服务工作线程运行时上下文。 |  
    
1.  选择一个资源，在编辑器中查看 **它**。  
    
    :::image type="complex" source="../media/resources-sources-page-resource.msft.png" alt-text="在编辑器中查看文件" lightbox="../media/resources-sources-page-resource.msft.png":::
       在编辑器中查看 **文件**  
    :::image-end:::  
    
### <a name="browse-by-filename"></a>按文件名浏览  

默认情况下， **页面面板** 按目录对资源进行分组。  若要禁用此分组并查看每个域的资源，请简单列表：  

1.  打开 **"页面"** 面板。  导航到["按目录浏览"。](#browse-by-directory)  
1.  选择 **"更多选项** `...` "并禁用 **"按文件夹分组"。**  
    
    :::image type="complex" source="../media/resources-sources-page-resource-group-by-folder.msft.png" alt-text=""按文件夹分组"选项" lightbox="../media/resources-sources-page-resource-group-by-folder.msft.png":::
       " **按文件夹分组"** 选项  
    :::image-end:::  
    
    资源按文件类型组织。  在每个文件类型中，资源按字母顺序组织。  
    
    :::image type="complex" source="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png" alt-text="禁用"按文件夹分组"后的页面面板" lightbox="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png":::
       禁用 **"** 按文件夹分组" **后的页面面板**  
    :::image-end:::  
    
### <a name="browse-by-file-type"></a>按文件类型浏览  

若要根据资源的文件类型将资源分组在一起：  

1.  选择 **"应用程序"** 选项卡。 应用程序 **工具** 将打开。  默认情况下， **清单窗格** 通常先打开。  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner.msft.png" alt-text="应用程序工具" lightbox="../media/resources-application-mainfest-airhorner.msft.png":::
       应用程序**工具**  
    :::image-end:::  
    
1.  向下滚动到" **框架"** 窗格。  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png" alt-text="框架窗格" lightbox="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png":::
       框架**窗格**  
    :::image-end:::  
    
1.  展开感兴趣的部分。  
1.  选择一个资源进行查看。  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png" alt-text="在"应用程序"面板中查看资源" lightbox="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png":::
       在"应用程序"面板 **中查看** 资源  
    :::image-end:::  
    
#### <a name="browse-files-by-type-in-the-network-panel"></a>在"网络"面板中按类型浏览文件  

按资源[类型导航到"筛选"。][DevtoolsNetworkFilterByResourceType]  

:::image type="complex" source="../media/resources-network-resources-filter-css.msft.png" alt-text="在网络日志中筛选 CSS" lightbox="../media/resources-network-resources-filter-css.msft.png":::
   在网络日志中 **筛选** CSS  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具|Microsoft Docs"  
[DevtoolsNetworkFilterByResourceType]: ../network/index.md#filter-by-resource-type "按资源类型筛选 - 检查 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsNetworkInspectDetailsResource]: ../network/index.md#inspect-the-details-of-the-resource "检查资源的详细信息 - 检查 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity "记录网络活动 - 检查 Microsoft Edge DevTools |Microsoft Docs"  

[MDNInlineFrame]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>：Inline Frame 元素|MDN"  
[MDNLearnWebDevelopment]: https://developer.mozilla.org/docs/Learn "了解 Web |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/resources/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
