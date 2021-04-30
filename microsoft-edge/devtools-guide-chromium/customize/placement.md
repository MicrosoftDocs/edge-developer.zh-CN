---
description: 如何将 Microsoft Edge DevTools 移动到视区底部或左侧或单独的窗口。
title: '将 Microsoft Edge DevTools (Undock，扩展坞更改为底部，将扩展坞更改为左侧) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: c4aca068c159f03b60bbf6d7643bb334a5b5a7f2
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519154"
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

# <a name="change-microsoft-edge-devtools-placement-undock-dock-to-bottom-dock-to-left"></a><span data-ttu-id="dd058-104">将 Microsoft Edge DevTools (Undock，扩展坞更改为底部，将扩展坞更改为左侧) </span><span class="sxs-lookup"><span data-stu-id="dd058-104">Change Microsoft Edge DevTools placement (Undock, Dock to bottom, Dock to left)</span></span>  

<span data-ttu-id="dd058-105">默认情况下，DevTools 固定在视口窗口 (右侧) 。</span><span class="sxs-lookup"><span data-stu-id="dd058-105">By default, DevTools is docked to the right of your viewport (window).</span></span>  <span data-ttu-id="dd058-106">还可以将 DevTools 停靠在窗口底部或左侧，或者将 DevTools 停靠到单独的窗口。</span><span class="sxs-lookup"><span data-stu-id="dd058-106">You may also dock DevTools to the bottom or left of the window, or undock DevTools to a separate window.</span></span>

:::row:::
   :::column span="":::
      <span data-ttu-id="dd058-107">DevTools 固定到窗口左侧：</span><span class="sxs-lookup"><span data-stu-id="dd058-107">DevTools docked to the left side of the window:</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="dd058-108">DevTools 固定到窗口底部：</span><span class="sxs-lookup"><span data-stu-id="dd058-108">DevTools docked to the bottom of the window:</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-right-docked.msft.png" alt-text="选择扩展坞向左" lightbox="../media/customize-elements-styles-right-docked.msft.png":::
         <span data-ttu-id="dd058-110">选择 **"扩展坞"向左**</span><span class="sxs-lookup"><span data-stu-id="dd058-110">Choose **Dock to left**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-bottom-docked.msft.png" alt-text="选择停靠到底部" lightbox="../media/customize-elements-styles-bottom-docked.msft.png":::
         <span data-ttu-id="dd058-112">当你希望应用本机保护时，可选择</span><span class="sxs-lookup"><span data-stu-id="dd058-112">Choose</span></span> `Dock to bottom`  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="dd058-113">DevTools 可能会撤消停靠到单独的窗口，你可以移到单独的监视器：</span><span class="sxs-lookup"><span data-stu-id="dd058-113">DevTools may be undocked to a separate window, which you may move to a separate monitor:</span></span>

:::row:::
   :::column span="":::
      <span data-ttu-id="dd058-114">浏览器窗口：</span><span class="sxs-lookup"><span data-stu-id="dd058-114">Browser window:</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="dd058-115">DevTools 在单独的窗口中取消停靠：</span><span class="sxs-lookup"><span data-stu-id="dd058-115">DevTools undocked in a separate window:</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-browser.msft.png" alt-text="单独窗口中的浏览器" lightbox="../media/customize-elements-styles-options-dock-side-highlight-browser.msft.png":::
         <span data-ttu-id="dd058-117">单独窗口中的浏览器</span><span class="sxs-lookup"><span data-stu-id="dd058-117">Browser in separate window</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png" alt-text="在单独窗口中取消停靠的 DevTools" lightbox="../media/customize-elements-styles-options-dock-side-highlight-devtools.msft.png":::
         <span data-ttu-id="dd058-119">在单独窗口中取消停靠的 DevTools</span><span class="sxs-lookup"><span data-stu-id="dd058-119">Undocked DevTools in separate window</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="change-placement-from-the-main-menu"></a><span data-ttu-id="dd058-120">从主菜单更改位置</span><span class="sxs-lookup"><span data-stu-id="dd058-120">Change placement from the main menu</span></span>  

1.  <span data-ttu-id="dd058-121">选择"自定义和控制**DevTools** \ (\) "，然后选择"撤消停靠到单独的窗口 `...` \ (\*\*\*\* Undock \) "，"扩展坞到底部 \ (扩展坞"到底部 \) ，或"扩展坞向左 \ (扩展坞"向左 ![ ](../media/undock-icon.msft.png) \*\*\*\* ![ ](../media/bottom-icon.msft.png) \*\*\*\* ![ ](../media/left-icon.msft.png) \) 。</span><span class="sxs-lookup"><span data-stu-id="dd058-121">Choose **Customize and control DevTools** \(`...`\) and choose **Undock into separate window** \(![Undock](../media/undock-icon.msft.png)\), **Dock to bottom** \(![Dock to bottom](../media/bottom-icon.msft.png)\), or **Dock to left** \(![Dock to left](../media/left-icon.msft.png)\).</span></span>  
    
    :::image type="complex" source="../media/customize-elements-styles-options-dock-side-highlight.msft.png" alt-text="选择取消停靠到单独的窗口" lightbox="../media/customize-elements-styles-options-dock-side-highlight.msft.png":::
       <span data-ttu-id="dd058-123">选择 **停靠到单独的窗口位置**</span><span class="sxs-lookup"><span data-stu-id="dd058-123">Choose **Undock into separate window**</span></span>  
    :::image-end:::  
    
## <a name="change-placement-from-the-command-menu"></a><span data-ttu-id="dd058-124">从命令菜单更改位置</span><span class="sxs-lookup"><span data-stu-id="dd058-124">Change placement from the Command Menu</span></span>  

1.  <span data-ttu-id="dd058-125">[在 Windows/Linux][DevtoolsCommandMenu]或 macOS 上选择 ， `Shift` + `Ctrl` + `P` 打开 `Command` + `Shift` + `P` 命令菜单。</span><span class="sxs-lookup"><span data-stu-id="dd058-125">[Open the Command Menu][DevtoolsCommandMenu], by selecting `Shift`+`Ctrl`+`P` on Windows/Linux or `Command`+`Shift`+`P` on macOS.</span></span>  
1.  <span data-ttu-id="dd058-126">在 `>` 字符后输入 `dock` ，然后选择以下命令之一：</span><span class="sxs-lookup"><span data-stu-id="dd058-126">After the `>` character, enter `dock`, and then choose one of the following commands:</span></span>  
    
    *  **<span data-ttu-id="dd058-127">扩展坞到底部</span><span class="sxs-lookup"><span data-stu-id="dd058-127">Dock to bottom</span></span>**
    *  **<span data-ttu-id="dd058-128">扩展坞向左</span><span class="sxs-lookup"><span data-stu-id="dd058-128">Dock to left</span></span>**
    *  **<span data-ttu-id="dd058-129">扩展坞向右</span><span class="sxs-lookup"><span data-stu-id="dd058-129">Dock to right</span></span>**
    *  **<span data-ttu-id="dd058-130">还原最后一个扩展坞位置</span><span class="sxs-lookup"><span data-stu-id="dd058-130">Restore last dock position</span></span>**
    *  **<span data-ttu-id="dd058-131">撤消停靠到单独的窗口中</span><span class="sxs-lookup"><span data-stu-id="dd058-131">Undock into separate window</span></span>**
    
    <span data-ttu-id="dd058-132">您还可以从主菜单访问 [命令](#change-placement-from-the-main-menu)。</span><span class="sxs-lookup"><span data-stu-id="dd058-132">You may also access the commands from the [main menu](#change-placement-from-the-main-menu).</span></span> 
    
    :::image type="complex" source="../media/customize-elements-styles-command-menu-undo.msft.png" alt-text="Undock 命令" lightbox="../media/customize-elements-styles-command-menu-undo.msft.png":::
       <span data-ttu-id="dd058-134">Undock 命令</span><span class="sxs-lookup"><span data-stu-id="dd058-134">The Undock command</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="dd058-135">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="dd058-135">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行|Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="dd058-137">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="dd058-137">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="dd058-138">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/customize/placement)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="dd058-138">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/customize/placement) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="dd058-140">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="dd058-140">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
