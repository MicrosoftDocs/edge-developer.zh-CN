---
title: 通过 Microsoft Edge DevTools 禁用 JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: f3838b4e8eccf83aaa71be35ff477ec56cbe7455
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581808"
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





# <span data-ttu-id="aedfd-103">通过 Microsoft Edge DevTools 禁用 JavaScript</span><span class="sxs-lookup"><span data-stu-id="aedfd-103">Disable JavaScript With Microsoft Edge DevTools</span></span>   



<span data-ttu-id="aedfd-104">若要查看在禁用 JavaScript 时网页的外观和行为，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="aedfd-104">To see how a web page looks and behaves when JavaScript is disabled:</span></span>  

1.  <span data-ttu-id="aedfd-105">[打开 Microsoft Edge DevTools][DevToolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="aedfd-105">[Open Microsoft Edge DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="aedfd-106">按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "**命令" 菜单**。</span><span class="sxs-lookup"><span data-stu-id="aedfd-106">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    > ##### <span data-ttu-id="aedfd-107">图 1</span><span class="sxs-lookup"><span data-stu-id="aedfd-107">Figure 1</span></span>  
    > <span data-ttu-id="aedfd-108">命令菜单</span><span class="sxs-lookup"><span data-stu-id="aedfd-108">The Command Menu</span></span>  
    > ![命令菜单][ImageCommandMenu]  
    
1.  <span data-ttu-id="aedfd-110">开始键入 `javascript` ，选择 "**禁用 JavaScript**"，然后按 `Enter` 运行命令。</span><span class="sxs-lookup"><span data-stu-id="aedfd-110">Start typing `javascript`, select **Disable JavaScript**, and then press `Enter` to run the command.</span></span>  <span data-ttu-id="aedfd-111">JavaScript 现在已被禁用。</span><span class="sxs-lookup"><span data-stu-id="aedfd-111">JavaScript is now disabled.</span></span>  
    
    > ##### <span data-ttu-id="aedfd-112">图 2</span><span class="sxs-lookup"><span data-stu-id="aedfd-112">Figure 2</span></span>  
    > <span data-ttu-id="aedfd-113">在 "命令" 菜单中选择 "**禁用 JavaScript** "</span><span class="sxs-lookup"><span data-stu-id="aedfd-113">Selecting **Disable JavaScript** in the Command Menu</span></span>  
    > ![在 "命令" 菜单中选择 "禁用 JavaScript"][ImageDisableJS]  
    
    <span data-ttu-id="aedfd-115">"**来源**" 旁边的黄色警告图标会提醒你已禁用 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="aedfd-115">The yellow warning icon next to **Sources** reminds you that JavaScript is disabled.</span></span>  
    
    > ##### <span data-ttu-id="aedfd-116">图 3</span><span class="sxs-lookup"><span data-stu-id="aedfd-116">Figure 3</span></span>  
    > <span data-ttu-id="aedfd-117">"**源**" 旁边的 "警告" 图标</span><span class="sxs-lookup"><span data-stu-id="aedfd-117">The warning icon next to **Sources**</span></span>  
    > !["源" 旁边的 "警告" 图标][ImageDisableJSWarning]  

<span data-ttu-id="aedfd-119">只要您已打开 DevTools，JavaScript 就会在此选项卡中保持禁用状态。</span><span class="sxs-lookup"><span data-stu-id="aedfd-119">JavaScript remains disabled in this tab for as long as you have DevTools open.</span></span>  

<span data-ttu-id="aedfd-120">你可能需要重新加载页面以查看页面是否以及页面在加载时是否依赖 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="aedfd-120">You may want to reload the page to see if and how the page depends on JavaScript while loading.</span></span>  

<span data-ttu-id="aedfd-121">要重新启用 JavaScript，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="aedfd-121">To re-enable JavaScript:</span></span>  

*   <span data-ttu-id="aedfd-122">再次打开 "**命令" 菜单**并运行 `Enable JavaScript` 命令。</span><span class="sxs-lookup"><span data-stu-id="aedfd-122">Open the **Command Menu** again and run the `Enable JavaScript` command.</span></span>  
*   <span data-ttu-id="aedfd-123">关闭 DevTools。</span><span class="sxs-lookup"><span data-stu-id="aedfd-123">Close DevTools.</span></span>  

## <span data-ttu-id="aedfd-124">反馈</span><span class="sxs-lookup"><span data-stu-id="aedfd-124">Feedback</span></span>   



<!-- image links -->  

[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/javascript-console-command.msft.png "图1：命令菜单"  
[ImageDisableJS]: /microsoft-edge/devtools-guide-chromium/media/javascript-console-command-javascript.msft.png "图2：在 "命令" 菜单中选择 "禁用 JavaScript""  
[ImageDisableJSWarning]: /microsoft-edge/devtools-guide-chromium/media/javascript-console-javascript-disabled-warning.msft.png "图3： "源" 旁边的 "警告" 图标"  

<!-- links -->  

[DevToolsOpen]: ../open.md "打开 Microsoft Edge DevTools"  

> [!NOTE]
> <span data-ttu-id="aedfd-129">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="aedfd-129">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="aedfd-130">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/disable)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="aedfd-130">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/disable) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="aedfd-132">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="aedfd-132">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
