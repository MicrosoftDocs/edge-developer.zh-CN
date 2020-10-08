---
description: 如何将 Microsoft Edge DevTools 移动到视区的底部或左侧，或移动到一个单独的窗口。
title: '更改 Microsoft Edge DevTools 放置 (脱开、停靠到底部、停靠到左侧) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: da7bd4ed23c54faac6d9fef9afbc78128f8cfd3c
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993007"
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





# 更改 Microsoft Edge DevTools 放置 (脱开、停靠到底部、停靠到左侧)    



默认情况下，DevTools 停靠在视区的右侧。  你还可以停靠到底部、停靠到左侧，或将 DevTools 移除到一个单独的窗口。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-right-docked.msft.png" alt-text="选择 &quot;停靠到左侧&quot;" lightbox="../media/customize-elements-styles-right-docked.msft.png":::
         选择 `Dock To Left`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-bottom-docked.msft.png" alt-text="选择 &quot;停靠到左侧&quot;" lightbox="../media/customize-elements-styles-bottom-docked.msft.png":::
         选择 `Dock To Bottom`  
      :::image-end:::  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-browser.msft.png" alt-text="选择 &quot;停靠到左侧&quot;" lightbox="../media/customize-elements-styles-options-dock-side-highlight-browser.msft.png":::
         单独窗口中的浏览器  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png" alt-text="选择 &quot;停靠到左侧&quot;" lightbox="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png":::
         在单独窗口中移动的 DevTools  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 从主菜单更改位置   

1.  单击 " **自定义和控制 DevTools** \ (`...` \ ) "，然后选择 " **在单独窗口中插入** " \ (取消停靠 ![ ][ImageUndockIcon] \ ) 、 **停靠到底部** \ \ (停靠到底部 \ ) ![ ][ImageBottomIcon] 或 **停靠** 到 " ![ ][ImageLeftIcon] 左 \ (" ) 。  
    
    :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight.msft.png" alt-text="选择 &quot;停靠到左侧&quot;" lightbox="../media/customize-elements-styles-options-dock-side-highlight.msft.png":::
       选择 "**在单独窗口中移除**"  
    :::image-end:::  
    
## 从命令菜单更改位置   

1.  [打开 "命令" 菜单][DevtoolsCommandMenu]。  
1.  运行以下命令之一： `Dock To Bottom` 、 `Undock Into Separate Window` 。  当前没有停靠到左侧的命令，但您可以从 [主菜单](#change-placement-from-the-main-menu)访问它。  
    
    :::image type="complex" source="../media/customize-elements-styles-command-menu-undo.msft.png" alt-text="选择 &quot;停靠到左侧&quot;" lightbox="../media/customize-elements-styles-command-menu-undo.msft.png":::
       "取消停靠" 命令  
    :::image-end:::  
    
<!--  
 


-->  

<!-- image links -->  

[ImageUndockIcon]: ../media/undock-icon.msft.png  
[ImageBottomIcon]: ../media/bottom-icon.msft.png  
[ImageLeftIcon]: ../media/left-icon.msft.png  

<!-- links -->  

[DevtoolsCommandMenu]: ../command-menu/index.md "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/customize/placement)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
