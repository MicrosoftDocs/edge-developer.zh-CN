---
title: 通过 Microsoft Edge DevTools 禁用 JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 587f4780432b1b2b964462d2d7f5779f447f1313
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982908"
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





# <span data-ttu-id="f4893-103">通过 Microsoft Edge DevTools 禁用 JavaScript</span><span class="sxs-lookup"><span data-stu-id="f4893-103">Disable JavaScript with Microsoft Edge DevTools</span></span>   



<span data-ttu-id="f4893-104">查看禁用 JavaScript 时网页的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="f4893-104">To see how a web page looks and behaves when JavaScript is disabled.</span></span>  

1.  <span data-ttu-id="f4893-105">[打开 Microsoft Edge DevTools][DevToolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="f4893-105">[Open Microsoft Edge DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="f4893-106">按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "**命令" 菜单**。</span><span class="sxs-lookup"><span data-stu-id="f4893-106">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-command.msft.png" alt-text="命令菜单" lightbox="../media/javascript-console-command.msft.png":::
       <span data-ttu-id="f4893-108">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="f4893-108">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f4893-109">开始键入 `javascript` ，选择 " **禁用 JavaScript**"，然后按 `Enter` 运行命令。</span><span class="sxs-lookup"><span data-stu-id="f4893-109">Start typing `javascript`, select **Disable JavaScript**, and then press `Enter` to run the command.</span></span>  <span data-ttu-id="f4893-110">JavaScript 现在已被禁用。</span><span class="sxs-lookup"><span data-stu-id="f4893-110">JavaScript is now disabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-command-javascript.msft.png" alt-text="在 "命令" 菜单中选择 "禁用 JavaScript"" lightbox="../media/javascript-console-command-javascript.msft.png":::
       <span data-ttu-id="f4893-112">在 "**命令" 菜单**中选择 "**禁用 JavaScript** "</span><span class="sxs-lookup"><span data-stu-id="f4893-112">Select **Disable JavaScript** in the **Command Menu**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="f4893-113">" **来源** " 旁边的黄色警告图标会提醒你已禁用 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="f4893-113">The yellow warning icon next to **Sources** reminds you that JavaScript is disabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-javascript-disabled-warning.msft.png" alt-text=""源" 旁边的 "警告" 图标" lightbox="../media/javascript-console-javascript-disabled-warning.msft.png":::
       <span data-ttu-id="f4893-115">"**源**" 旁边的 "警告" 图标</span><span class="sxs-lookup"><span data-stu-id="f4893-115">The warning icon next to **Sources**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="f4893-116">只要您已打开 DevTools，JavaScript 就会在此选项卡中保持禁用状态。</span><span class="sxs-lookup"><span data-stu-id="f4893-116">JavaScript remains disabled in this tab for as long as you have DevTools open.</span></span>  

<span data-ttu-id="f4893-117">你可能需要重新加载页面以查看页面是否以及页面在加载时是否依赖 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="f4893-117">You may want to reload the page to see if and how the page depends on JavaScript while loading.</span></span>  

<span data-ttu-id="f4893-118">若要重新启用 JavaScript，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="f4893-118">To re-enable JavaScript, complete the following actions.</span></span>  

*   <span data-ttu-id="f4893-119">再次打开 " **命令" 菜单** 并运行 `Enable JavaScript` 命令。</span><span class="sxs-lookup"><span data-stu-id="f4893-119">Open the **Command Menu** again and run the `Enable JavaScript` command.</span></span>  
*   <span data-ttu-id="f4893-120">关闭 DevTools。</span><span class="sxs-lookup"><span data-stu-id="f4893-120">Close DevTools.</span></span>  

<!--  
## Feedback   


-->  

<!-- links -->  

[DevToolsOpen]: ../open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  

> [!NOTE]
> <span data-ttu-id="f4893-122">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f4893-122">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f4893-123">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/disable)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="f4893-123">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/disable) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f4893-125">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f4893-125">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
