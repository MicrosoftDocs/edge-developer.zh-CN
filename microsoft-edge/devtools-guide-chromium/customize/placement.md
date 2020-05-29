---
title: 更改 Microsoft Edge DevTools 位置（"取消停靠"、"停靠到底部"、"停靠到左侧"）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: f0be6243d4780e4ed49428ebaf2b6b37d9da323e
ms.sourcegitcommit: 67ce64f810afdb304844bae0f3918d4e9108dcec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2020
ms.locfileid: "10601344"
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





# 更改 Microsoft Edge DevTools 位置（"取消停靠"、"停靠到底部"、"停靠到左侧"）   



默认情况下，DevTools 停靠在视区的右侧。  你还可以停靠到底部、停靠到左侧，或将 DevTools 移除到一个单独的窗口。  

> ##### 图 1  
> 停靠到左侧  
> ![停靠到左侧][ImageDockLeft]  

> ##### 图 2  
> 停靠到底部  
> ![停靠到底部][ImageDockBottom]  

> ##### 图 3  
> 单独窗口中的浏览器  
> ![单独窗口中的浏览器][ImageUndockBrowser]  

> ##### 图 4  
> 在单独窗口中移动的 DevTools  
> ![在单独窗口中移动的 DevTools][ImageUndockDevTools]  

## 从主菜单更改位置   

1.  单击 "**自定义和控制 DevTools** " `...` ，然后选择 "**在单独窗口中移除** ![ ][ImageUndockIcon] "、"**停靠到底部** ![ 停靠" 或 " ][ImageBottomIcon] **停靠到**左侧停靠" ![ ][ImageLeftIcon] 。  
    
    > ##### 图 5  
    > **在单独窗口中**选择 "脱开"  
    > ![在单独窗口中选择 "脱开"][ImageUndockSettings]  
    
## 从命令菜单更改位置   

1.  [打开 "命令" 菜单][DevtoolsCommandMenu]。  
1.  运行以下命令之一： `Dock To Bottom` 、 `Undock Into Separate Window` 。  当前没有停靠到左侧的命令，但您可以从[主菜单](#change-placement-from-the-main-menu)访问它。  
    
    > ##### 图 6  
    > "取消停靠" 命令  
    > !["取消停靠" 命令][ImageUndockCommand]  

 



<!-- image links -->  

[ImageUndockIcon]: /microsoft-edge/devtools-guide-chromium/media/undock-icon.msft.png  
[ImageBottomIcon]: /microsoft-edge/devtools-guide-chromium/media/bottom-icon.msft.png  
[ImageLeftIcon]: /microsoft-edge/devtools-guide-chromium/media/left-icon.msft.png  

[ImageDockLeft]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-right-docked.msft.png "图1：停靠到左侧"  
[ImageDockBottom]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-bottom-docked.msft.png "图2：停靠到底部"  
[ImageUndockBrowser]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-options-dock-side-highlight-browser.msft.png "图3：单独窗口中的浏览器"  
[ImageUndockDevTools]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png "图4：单独窗口中的未停靠 DevTools"  
[ImageUndockSettings]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-options-dock-side-highlight.msft.png "图5：在单独窗口中选择 "脱开""  
[ImageUndockCommand]: /microsoft-edge/devtools-guide-chromium/media/customize-elements-styles-command-menu-undo.msft.png "图6： "取消停靠" 命令"  

<!-- links -->  

[DevtoolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "通过 Microsoft Edge DevTools 命令菜单运行命令"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/customize/placement)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
