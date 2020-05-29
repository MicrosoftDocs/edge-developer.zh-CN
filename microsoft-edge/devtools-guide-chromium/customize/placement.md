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





# <span data-ttu-id="d8f29-103">更改 Microsoft Edge DevTools 位置（"取消停靠"、"停靠到底部"、"停靠到左侧"）</span><span class="sxs-lookup"><span data-stu-id="d8f29-103">Change Microsoft Edge DevTools Placement (Undock, Dock To Bottom, Dock To Left)</span></span>   



<span data-ttu-id="d8f29-104">默认情况下，DevTools 停靠在视区的右侧。</span><span class="sxs-lookup"><span data-stu-id="d8f29-104">By default DevTools is docked to the right of your viewport.</span></span>  <span data-ttu-id="d8f29-105">你还可以停靠到底部、停靠到左侧，或将 DevTools 移除到一个单独的窗口。</span><span class="sxs-lookup"><span data-stu-id="d8f29-105">You may also dock to bottom, dock to left, or undock the DevTools to a separate window.</span></span>  

> ##### <span data-ttu-id="d8f29-106">图 1</span><span class="sxs-lookup"><span data-stu-id="d8f29-106">Figure 1</span></span>  
> <span data-ttu-id="d8f29-107">停靠到左侧</span><span class="sxs-lookup"><span data-stu-id="d8f29-107">Dock To Left</span></span>  
> ![停靠到左侧][ImageDockLeft]  

> ##### <span data-ttu-id="d8f29-109">图 2</span><span class="sxs-lookup"><span data-stu-id="d8f29-109">Figure 2</span></span>  
> <span data-ttu-id="d8f29-110">停靠到底部</span><span class="sxs-lookup"><span data-stu-id="d8f29-110">Dock To Bottom</span></span>  
> ![停靠到底部][ImageDockBottom]  

> ##### <span data-ttu-id="d8f29-112">图 3</span><span class="sxs-lookup"><span data-stu-id="d8f29-112">Figure 3</span></span>  
> <span data-ttu-id="d8f29-113">单独窗口中的浏览器</span><span class="sxs-lookup"><span data-stu-id="d8f29-113">Browser in separate window</span></span>  
> ![单独窗口中的浏览器][ImageUndockBrowser]  

> ##### <span data-ttu-id="d8f29-115">图 4</span><span class="sxs-lookup"><span data-stu-id="d8f29-115">Figure 4</span></span>  
> <span data-ttu-id="d8f29-116">在单独窗口中移动的 DevTools</span><span class="sxs-lookup"><span data-stu-id="d8f29-116">Undocked DevTools in separate window</span></span>  
> ![在单独窗口中移动的 DevTools][ImageUndockDevTools]  

## <span data-ttu-id="d8f29-118">从主菜单更改位置</span><span class="sxs-lookup"><span data-stu-id="d8f29-118">Change placement from the main menu</span></span>   

1.  <span data-ttu-id="d8f29-119">单击 "**自定义和控制 DevTools** " `...` ，然后选择 "**在单独窗口中移除** ![ ][ImageUndockIcon] "、"**停靠到底部** ![ 停靠" 或 " ][ImageBottomIcon] **停靠到**左侧停靠" ![ ][ImageLeftIcon] 。</span><span class="sxs-lookup"><span data-stu-id="d8f29-119">Click **Customize And Control DevTools** `...` and select **Undock Into Separate Window** ![Undock][ImageUndockIcon], **Dock To Bottom** ![Dock To Bottom][ImageBottomIcon], or **Dock To Left** ![Dock To Left][ImageLeftIcon].</span></span>  
    
    > ##### <span data-ttu-id="d8f29-120">图 5</span><span class="sxs-lookup"><span data-stu-id="d8f29-120">Figure 5</span></span>  
    > <span data-ttu-id="d8f29-121">**在单独窗口中**选择 "脱开"</span><span class="sxs-lookup"><span data-stu-id="d8f29-121">Selecting **Undock Into Separate Window**</span></span>  
    > ![在单独窗口中选择 "脱开"][ImageUndockSettings]  
    
## <span data-ttu-id="d8f29-123">从命令菜单更改位置</span><span class="sxs-lookup"><span data-stu-id="d8f29-123">Change placement from the Command Menu</span></span>   

1.  <span data-ttu-id="d8f29-124">[打开 "命令" 菜单][DevtoolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="d8f29-124">[Open the Command Menu][DevtoolsCommandMenu].</span></span>  
1.  <span data-ttu-id="d8f29-125">运行以下命令之一： `Dock To Bottom` 、 `Undock Into Separate Window` 。</span><span class="sxs-lookup"><span data-stu-id="d8f29-125">Run one of the following commands: `Dock To Bottom`, `Undock Into Separate Window`.</span></span>  <span data-ttu-id="d8f29-126">当前没有停靠到左侧的命令，但您可以从[主菜单](#change-placement-from-the-main-menu)访问它。</span><span class="sxs-lookup"><span data-stu-id="d8f29-126">Currently there is no command for docking to left, but you may access it from the [main menu](#change-placement-from-the-main-menu).</span></span>  
    
    > ##### <span data-ttu-id="d8f29-127">图 6</span><span class="sxs-lookup"><span data-stu-id="d8f29-127">Figure 6</span></span>  
    > <span data-ttu-id="d8f29-128">"取消停靠" 命令</span><span class="sxs-lookup"><span data-stu-id="d8f29-128">The undock command</span></span>  
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
> <span data-ttu-id="d8f29-137">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="d8f29-137">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d8f29-138">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/customize/placement)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="d8f29-138">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/customize/placement) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="d8f29-140">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="d8f29-140">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
