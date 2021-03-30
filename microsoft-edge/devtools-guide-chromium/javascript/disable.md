---
description: 打开命令菜单并运行"禁用 JavaScript"命令。
title: 使用 Microsoft Edge DevTools 禁用 JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 2067944fa17c332dd15ffb3ef97afe02d35685ed
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398558"
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

# <a name="disable-javascript-with-microsoft-edge-devtools"></a><span data-ttu-id="bf614-104">使用 Microsoft Edge DevTools 禁用 JavaScript</span><span class="sxs-lookup"><span data-stu-id="bf614-104">Disable JavaScript with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="bf614-105">完成以下操作以显示禁用 JavaScript 时网页的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="bf614-105">Complete the following actions to display how a webpage looks and behaves when JavaScript is disabled.</span></span>  

1.  <span data-ttu-id="bf614-106">[打开 Microsoft Edge DevTools。][DevToolsOpen]</span><span class="sxs-lookup"><span data-stu-id="bf614-106">[Open Microsoft Edge DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="bf614-107">选择 `Control`+`Shift`+`P` \(Windows、Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开**命令菜单**。</span><span class="sxs-lookup"><span data-stu-id="bf614-107">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-command.msft.png" alt-text="命令菜单" lightbox="../media/javascript-console-command.msft.png":::
       <span data-ttu-id="bf614-109">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="bf614-109">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="bf614-110">开始键入， `javascript` 选择 **"禁用 JavaScript"，** 然后选择 `Enter` 运行命令。</span><span class="sxs-lookup"><span data-stu-id="bf614-110">Start typing `javascript`, choose **Disable JavaScript**, and then select `Enter` to run the command.</span></span>  <span data-ttu-id="bf614-111">JavaScript 现已禁用。</span><span class="sxs-lookup"><span data-stu-id="bf614-111">JavaScript is now disabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-command-javascript.msft.png" alt-text="在命令菜单中选择禁用 JavaScript" lightbox="../media/javascript-console-command-javascript.msft.png":::
       <span data-ttu-id="bf614-113">在**命令菜单中选择"禁用 JavaScript"** </span><span class="sxs-lookup"><span data-stu-id="bf614-113">Choose **Disable JavaScript** in the **Command Menu**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="bf614-114">源旁边的黄色警告 **图标** 提醒你 JavaScript 已禁用。</span><span class="sxs-lookup"><span data-stu-id="bf614-114">The yellow warning icon next to **Sources** reminds you that JavaScript is disabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-javascript-disabled-warning.msft.png" alt-text="源旁边的警告图标" lightbox="../media/javascript-console-javascript-disabled-warning.msft.png":::
       <span data-ttu-id="bf614-116">源旁边的警告 **图标**</span><span class="sxs-lookup"><span data-stu-id="bf614-116">The warning icon next to **Sources**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="bf614-117">只要打开 DevTools，JavaScript 在选项卡中就保持禁用状态。</span><span class="sxs-lookup"><span data-stu-id="bf614-117">JavaScript remains disabled in the tab for as long as you have DevTools open.</span></span>  

<span data-ttu-id="bf614-118">您可能需要刷新页面，查看网页在加载时是否以及如何依赖 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="bf614-118">You may want to refresh the page to review if and how the webpage depends on JavaScript while loading.</span></span>  

<span data-ttu-id="bf614-119">若要重新启用 JavaScript，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="bf614-119">To re-enable JavaScript, complete the following actions.</span></span>  

*   <span data-ttu-id="bf614-120">再次 **打开命令菜单** 并运行 `Enable JavaScript` 命令。</span><span class="sxs-lookup"><span data-stu-id="bf614-120">Open the **Command Menu** again and run the `Enable JavaScript` command.</span></span>  
*   <span data-ttu-id="bf614-121">关闭 DevTools。</span><span class="sxs-lookup"><span data-stu-id="bf614-121">Close DevTools.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="bf614-122">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="bf614-122">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsOpen]: ../open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="bf614-124">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="bf614-124">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="bf614-125">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/disable)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="bf614-125">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/disable) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="bf614-127">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="bf614-127">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
