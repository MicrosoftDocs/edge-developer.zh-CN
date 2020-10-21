---
description: 如何将 Microsoft Edge DevTools 移动到视区的底部或左侧，或移动到一个单独的窗口。
title: '更改 Microsoft Edge DevTools 放置 (脱开、停靠到底部、停靠到左侧) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 65c0849af5da671bb0d76397d6d9395bc249eaac
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125046"
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

# <span data-ttu-id="2c3fe-104">更改 Microsoft Edge DevTools 放置 (脱开、停靠到底部、停靠到左侧) </span><span class="sxs-lookup"><span data-stu-id="2c3fe-104">Change Microsoft Edge DevTools placement (Undock, Dock To Bottom, Dock To Left)</span></span>  

<span data-ttu-id="2c3fe-105">默认情况下，DevTools 停靠在视区的右侧。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-105">By default DevTools is docked to the right of your viewport.</span></span>  <span data-ttu-id="2c3fe-106">你还可以停靠到底部、停靠到左侧，或将 DevTools 移除到一个单独的窗口。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-106">You may also dock to bottom, dock to left, or undock the DevTools to a separate window.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-right-docked.msft.png" alt-text="选择 &quot;停靠到左侧&quot;" lightbox="../media/customize-elements-styles-right-docked.msft.png":::
         <span data-ttu-id="2c3fe-108">选择</span><span class="sxs-lookup"><span data-stu-id="2c3fe-108">Select</span></span> `Dock To Left`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-bottom-docked.msft.png" alt-text="选择 &quot;停靠到左侧&quot;" lightbox="../media/customize-elements-styles-bottom-docked.msft.png":::
         <span data-ttu-id="2c3fe-110">选择</span><span class="sxs-lookup"><span data-stu-id="2c3fe-110">Select</span></span> `Dock To Bottom`  
      :::image-end:::  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-browser.msft.png" alt-text="选择 &quot;停靠到左侧&quot;" lightbox="../media/customize-elements-styles-options-dock-side-highlight-browser.msft.png":::
         <span data-ttu-id="2c3fe-112">单独窗口中的浏览器</span><span class="sxs-lookup"><span data-stu-id="2c3fe-112">Browser in separate window</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png" alt-text="选择 &quot;停靠到左侧&quot;" lightbox="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png":::
         <span data-ttu-id="2c3fe-114">在单独窗口中移动的 DevTools</span><span class="sxs-lookup"><span data-stu-id="2c3fe-114">Undocked DevTools in separate window</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="2c3fe-115">从主菜单更改位置</span><span class="sxs-lookup"><span data-stu-id="2c3fe-115">Change placement from the main menu</span></span>  

1.  <span data-ttu-id="2c3fe-116">选择 " **自定义和控制 DevTools** (\ `...` ) "，然后选择 " **在单独窗口中插入** " \ (取消停靠 ![ ][ImageUndockIcon] \ ) 、 **停靠到底部** \ " (停靠到底部 \ ) ![ ][ImageBottomIcon] " 或 " **停靠到左** ![ ][ImageLeftIcon] \ (" ) 。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-116">Choose **Customize And Control DevTools** \(`...`\) and choose **Undock Into Separate Window** \(![Undock][ImageUndockIcon]\), **Dock To Bottom** \(![Dock To Bottom][ImageBottomIcon]\), or **Dock To Left** \(![Dock To Left][ImageLeftIcon]\).</span></span>  
    
    :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight.msft.png" alt-text="选择 &quot;停靠到左侧&quot;" lightbox="../media/customize-elements-styles-options-dock-side-highlight.msft.png":::
       <span data-ttu-id="2c3fe-118">选择 "**在单独窗口中脱开**"</span><span class="sxs-lookup"><span data-stu-id="2c3fe-118">Choose **Undock Into Separate Window**</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="2c3fe-119">从命令菜单更改位置</span><span class="sxs-lookup"><span data-stu-id="2c3fe-119">Change placement from the Command Menu</span></span>  

1.  <span data-ttu-id="2c3fe-120">[打开 "命令" 菜单][DevtoolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-120">[Open the Command Menu][DevtoolsCommandMenu].</span></span>  
1.  <span data-ttu-id="2c3fe-121">运行以下命令之一： `Dock To Bottom` 、 `Undock Into Separate Window` 。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-121">Run one of the following commands: `Dock To Bottom`, `Undock Into Separate Window`.</span></span>  <span data-ttu-id="2c3fe-122">当前没有停靠到左侧的命令，但您可以从 [主菜单](#change-placement-from-the-main-menu)访问它。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-122">Currently there is no command for docking to left, but you may access it from the [main menu](#change-placement-from-the-main-menu).</span></span>  
    
    :::image type="complex" source="../media/customize-elements-styles-command-menu-undo.msft.png" alt-text="选择 &quot;停靠到左侧&quot;" lightbox="../media/customize-elements-styles-command-menu-undo.msft.png":::
       <span data-ttu-id="2c3fe-124">"取消停靠" 命令</span><span class="sxs-lookup"><span data-stu-id="2c3fe-124">The undock command</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="2c3fe-125">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="2c3fe-125">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageUndockIcon]: ../media/undock-icon.msft.png  
[ImageBottomIcon]: ../media/bottom-icon.msft.png  
[ImageLeftIcon]: ../media/left-icon.msft.png  

<!-- links -->  

[DevtoolsCommandMenu]: ../command-menu/index.md "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"  

> [!NOTE]
> <span data-ttu-id="2c3fe-127">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-127">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="2c3fe-128">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/customize/placement)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-128">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/customize/placement) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="2c3fe-130">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-130">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
