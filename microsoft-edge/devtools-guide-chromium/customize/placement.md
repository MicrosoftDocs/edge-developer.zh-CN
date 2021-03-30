---
description: 如何将 Microsoft Edge DevTools 移动到视区底部或左侧或单独的窗口。
title: 更改 Microsoft Edge DevTools 位置（撤消停靠、停靠到底部、停靠到左侧）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 8fabeaf6d972badd08ab85486913ef17f54bcf67
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439175"
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

# <a name="change-microsoft-edge-devtools-placement-undock-dock-to-bottom-dock-to-left"></a>更改 Microsoft Edge DevTools 位置（撤消停靠、停靠到底部、停靠到左侧）  

默认情况下，DevTools 停靠在视区右侧。  也可停靠到底部、停靠到左侧或取消停靠 DevTools 到单独的窗口。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-right-docked.msft.png" alt-text="选择停靠到左侧" lightbox="../media/customize-elements-styles-right-docked.msft.png":::
         当你希望应用本机保护时，可选择 `Dock To Left`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-bottom-docked.msft.png" alt-text="选择停靠到底部" lightbox="../media/customize-elements-styles-bottom-docked.msft.png":::
         当你希望应用本机保护时，可选择 `Dock To Bottom`  
      :::image-end:::  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-browser.msft.png" alt-text="单独窗口中的浏览器" lightbox="../media/customize-elements-styles-options-dock-side-highlight-browser.msft.png":::
         单独窗口中的浏览器  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png" alt-text="在单独窗口中取消停靠的 DevTools" lightbox="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png":::
         在单独窗口中取消停靠的 DevTools  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="change-placement-from-the-main-menu"></a>从主菜单更改位置  

1.  选择 **自定义和控制 DevTools** \（`...`\） 并选择 **取消停靠为单独的窗口** \（![取消停靠](../media/undock-icon.msft.png)\）、 **停靠到** 底部 \（![停靠到底部](../media/bottom-icon.msft.png)\），或 **停靠到左侧** \（![停靠到](../media/left-icon.msft.png)\）。  
    
    :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight.msft.png" alt-text="选择取消停靠到单独的窗口" lightbox="../media/customize-elements-styles-options-dock-side-highlight.msft.png":::
       选择 **停靠到单独的窗口位置**  
    :::image-end:::  
    
## <a name="change-placement-from-the-command-menu"></a>从命令菜单更改位置  

1.  [打开“命令”菜单][DevtoolsCommandMenu]。  
1.  运行下列命令之一： `Dock To Bottom`、 `Undock Into Separate Window`。  当前没有向左停靠的命令，但你可能从"另一个"主 [访问](#change-placement-from-the-main-menu)。  
    
    :::image type="complex" source="../media/customize-elements-styles-command-menu-undo.msft.png" alt-text="取消停靠命令" lightbox="../media/customize-elements-styles-command-menu-undo.msft.png":::
       取消停靠命令  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行|Microsoft Docs"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/customize/placement)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
