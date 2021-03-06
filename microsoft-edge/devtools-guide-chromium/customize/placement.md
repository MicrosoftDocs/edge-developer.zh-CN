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

# <a name="change-microsoft-edge-devtools-placement-undock-dock-to-bottom-dock-to-left"></a><span data-ttu-id="438c3-104">将 Microsoft Edge DevTools 放置 (取消停靠、停靠到底部、将扩展坞更改为左侧) </span><span class="sxs-lookup"><span data-stu-id="438c3-104">Change Microsoft Edge DevTools placement (Undock, Dock To Bottom, Dock To Left)</span></span>  

<span data-ttu-id="438c3-105">默认情况下，DevTools 停靠在视区右侧。</span><span class="sxs-lookup"><span data-stu-id="438c3-105">By default DevTools is docked to the right of your viewport.</span></span>  <span data-ttu-id="438c3-106">还可以停靠到底部、停靠到左侧或将 DevTool 停靠到单独的窗口。</span><span class="sxs-lookup"><span data-stu-id="438c3-106">You may also dock to bottom, dock to left, or undock the DevTools to a separate window.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-right-docked.msft.png" alt-text="选择"停靠到左侧"" lightbox="../media/customize-elements-styles-right-docked.msft.png":::
         <span data-ttu-id="438c3-108">选择</span><span class="sxs-lookup"><span data-stu-id="438c3-108">Choose</span></span> `Dock To Left`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-bottom-docked.msft.png" alt-text="选择"扩展坞到底部"" lightbox="../media/customize-elements-styles-bottom-docked.msft.png":::
         <span data-ttu-id="438c3-110">选择</span><span class="sxs-lookup"><span data-stu-id="438c3-110">Choose</span></span> `Dock To Bottom`  
      :::image-end:::  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-browser.msft.png" alt-text="单独窗口中的浏览器" lightbox="../media/customize-elements-styles-options-dock-side-highlight-browser.msft.png":::
         <span data-ttu-id="438c3-112">单独窗口中的浏览器</span><span class="sxs-lookup"><span data-stu-id="438c3-112">Browser in separate window</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png" alt-text="在单独的窗口中撤消停靠的 DevTools" lightbox="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png":::
         <span data-ttu-id="438c3-114">在单独的窗口中撤消停靠的 DevTools</span><span class="sxs-lookup"><span data-stu-id="438c3-114">Undocked DevTools in separate window</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="change-placement-from-the-main-menu"></a><span data-ttu-id="438c3-115">从主菜单更改位置</span><span class="sxs-lookup"><span data-stu-id="438c3-115">Change placement from the main menu</span></span>  

1.  <span data-ttu-id="438c3-116">Choose **Customize and Control DevTools** `...` \ (\) and choose **Undock into Separate Window** \ (![ Undock ][ImageUndockIcon] \) ， **Dock to Bottom** \ (Dock to Bottom ![ ][ImageBottomIcon] \) ， or **Dock To Left** \ (Dock to Left ![ ][ImageLeftIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="438c3-116">Choose **Customize And Control DevTools** \(`...`\) and choose **Undock Into Separate Window** \(![Undock][ImageUndockIcon]\), **Dock To Bottom** \(![Dock To Bottom][ImageBottomIcon]\), or **Dock To Left** \(![Dock To Left][ImageLeftIcon]\).</span></span>  
    
    :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight.msft.png" alt-text="选择"撤消到单独的窗口"" lightbox="../media/customize-elements-styles-options-dock-side-highlight.msft.png":::
       <span data-ttu-id="438c3-118">选择 **"撤消到单独的窗口"**</span><span class="sxs-lookup"><span data-stu-id="438c3-118">Choose **Undock Into Separate Window**</span></span>  
    :::image-end:::  
    
## <a name="change-placement-from-the-command-menu"></a><span data-ttu-id="438c3-119">从命令菜单更改位置</span><span class="sxs-lookup"><span data-stu-id="438c3-119">Change placement from the Command Menu</span></span>  

1.  <span data-ttu-id="438c3-120">[打开命令菜单][DevtoolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="438c3-120">[Open the Command Menu][DevtoolsCommandMenu].</span></span>  
1.  <span data-ttu-id="438c3-121">运行以下命令之一： `Dock To Bottom` `Undock Into Separate Window` .</span><span class="sxs-lookup"><span data-stu-id="438c3-121">Run one of the following commands: `Dock To Bottom`, `Undock Into Separate Window`.</span></span>  <span data-ttu-id="438c3-122">当前没有用于左停靠的命令，但你可以从主菜单 [访问它](#change-placement-from-the-main-menu)。</span><span class="sxs-lookup"><span data-stu-id="438c3-122">Currently there is no command for docking to left, but you may access it from the [main menu](#change-placement-from-the-main-menu).</span></span>  
    
    :::image type="complex" source="../media/customize-elements-styles-command-menu-undo.msft.png" alt-text="Undock 命令" lightbox="../media/customize-elements-styles-command-menu-undo.msft.png":::
       <span data-ttu-id="438c3-124">Undock 命令</span><span class="sxs-lookup"><span data-stu-id="438c3-124">The undock command</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="438c3-125">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="438c3-125">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageUndockIcon]: ../media/undock-icon.msft.png  
[ImageBottomIcon]: ../media/bottom-icon.msft.png  
[ImageLeftIcon]: ../media/left-icon.msft.png  

<!-- links -->  

[DevtoolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行命令|Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="438c3-127">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="438c3-127">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="438c3-128">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/customize/placement)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="438c3-128">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/customize/placement) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="438c3-130">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="438c3-130">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
