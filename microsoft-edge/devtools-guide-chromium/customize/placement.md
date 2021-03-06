---
description: 如何将 Microsoft Edge DevTools 移到视口底部或左侧，或移动到单独的窗口。
title: '将 Microsoft Edge DevTools 放置 (取消停靠、停靠到底部、将扩展坞更改为左侧) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: e3160999a1072afffdc5c5d44f8fc60fab65d264
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399029"
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

# <a name="change-microsoft-edge-devtools-placement-undock-dock-to-bottom-dock-to-left"></a>将 Microsoft Edge DevTools 放置 (取消停靠、停靠到底部、将扩展坞更改为左侧)   

默认情况下，DevTools 停靠在视区右侧。  还可以停靠到底部、停靠到左侧或将 DevTool 停靠到单独的窗口。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-right-docked.msft.png" alt-text="选择"停靠到左侧"" lightbox="../media/customize-elements-styles-right-docked.msft.png":::
         选择 `Dock To Left`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-bottom-docked.msft.png" alt-text="选择"扩展坞到底部"" lightbox="../media/customize-elements-styles-bottom-docked.msft.png":::
         选择 `Dock To Bottom`  
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
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png" alt-text="在单独的窗口中撤消停靠的 DevTools" lightbox="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png":::
         在单独的窗口中撤消停靠的 DevTools  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="change-placement-from-the-main-menu"></a>从主菜单更改位置  

1.  Choose **Customize and Control DevTools** `...` \ (\) and choose **Undock into Separate Window** \ (![ Undock ][ImageUndockIcon] \) ， **Dock to Bottom** \ (Dock to Bottom ![ ][ImageBottomIcon] \) ， or **Dock To Left** \ (Dock to Left ![ ][ImageLeftIcon] \) .  
    
    :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight.msft.png" alt-text="选择"撤消到单独的窗口"" lightbox="../media/customize-elements-styles-options-dock-side-highlight.msft.png":::
       选择 **"撤消到单独的窗口"**  
    :::image-end:::  
    
## <a name="change-placement-from-the-command-menu"></a>从命令菜单更改位置  

1.  [打开命令菜单][DevtoolsCommandMenu]。  
1.  运行以下命令之一： `Dock To Bottom` `Undock Into Separate Window` .  当前没有用于左停靠的命令，但你可以从主菜单 [访问它](#change-placement-from-the-main-menu)。  
    
    :::image type="complex" source="../media/customize-elements-styles-command-menu-undo.msft.png" alt-text="Undock 命令" lightbox="../media/customize-elements-styles-command-menu-undo.msft.png":::
       Undock 命令  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageUndockIcon]: ../media/undock-icon.msft.png  
[ImageBottomIcon]: ../media/bottom-icon.msft.png  
[ImageLeftIcon]: ../media/left-icon.msft.png  

<!-- links -->  

[DevtoolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行命令|Microsoft Docs"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/customize/placement)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
