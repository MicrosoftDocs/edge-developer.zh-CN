---
description: 打开命令菜单并运行"禁用 JavaScript"命令。
title: 使用开发人员工具Microsoft Edge JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: c9b5605aff5680ff0f44386c4a69e4c9f7c08cc8
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564159"
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
# <a name="disable-javascript-with-microsoft-edge-devtools"></a><span data-ttu-id="de54e-104">使用开发人员工具Microsoft Edge JavaScript</span><span class="sxs-lookup"><span data-stu-id="de54e-104">Disable JavaScript with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="de54e-105">若要在浏览器不支持 JavaScript 时查看网页的呈现效果，请暂时关闭 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="de54e-105">To review how your webpage renders when a browser doesn't have JavaScript support, temporarily turn off JavaScript.</span></span>

<span data-ttu-id="de54e-106">完成以下操作以检查网页在关闭 JavaScript 时如何显示和行为。</span><span class="sxs-lookup"><span data-stu-id="de54e-106">Complete the following actions to examine how a webpage displays and behaves when you turn off JavaScript.</span></span>  

1.  <span data-ttu-id="de54e-107">[打开 Microsoft Edge DevTools][DevToolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="de54e-107">[Open Microsoft Edge DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="de54e-108">选择 `Control`+`Shift`+`P` \(Windows、Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开**命令菜单**。</span><span class="sxs-lookup"><span data-stu-id="de54e-108">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-command.msft.png" alt-text="命令菜单" lightbox="../media/javascript-console-command.msft.png":::
       <span data-ttu-id="de54e-110">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="de54e-110">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de54e-111">开始键入 ， `javascript` 选择 **"禁用 JavaScript"，** 然后选择 `Enter` 运行命令。</span><span class="sxs-lookup"><span data-stu-id="de54e-111">Start typing `javascript`, choose **Disable JavaScript**, and then select `Enter` to run the command.</span></span>  <span data-ttu-id="de54e-112">JavaScript 现已禁用。</span><span class="sxs-lookup"><span data-stu-id="de54e-112">JavaScript is now disabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-command-javascript.msft.png" alt-text="在命令菜单中选择禁用 JavaScript" lightbox="../media/javascript-console-command-javascript.msft.png":::
       <span data-ttu-id="de54e-114">在 **命令菜单中选择** "禁用 **JavaScript"**</span><span class="sxs-lookup"><span data-stu-id="de54e-114">Choose **Disable JavaScript** in the **Command Menu**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="de54e-115">源旁边的黄色 **警告图标提醒** 你 JavaScript 已禁用。</span><span class="sxs-lookup"><span data-stu-id="de54e-115">The yellow warning icon next to **Sources** reminds you that JavaScript is disabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-javascript-disabled-warning.msft.png" alt-text="源旁边的警告图标" lightbox="../media/javascript-console-javascript-disabled-warning.msft.png":::
       <span data-ttu-id="de54e-117">"源"旁边的警告 **图标**</span><span class="sxs-lookup"><span data-stu-id="de54e-117">The warning icon next to **Sources**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="de54e-118">只要打开 DevTools，JavaScript 在选项卡中就保持禁用状态。</span><span class="sxs-lookup"><span data-stu-id="de54e-118">JavaScript remains disabled in the tab for as long as you have DevTools open.</span></span>  

<span data-ttu-id="de54e-119">你可能想要刷新页面，以检查网页在加载时是否以及如何依赖于 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="de54e-119">You may want to refresh the page to review if and how the webpage depends on JavaScript while loading.</span></span>  

<span data-ttu-id="de54e-120">若要重新启用 JavaScript，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="de54e-120">To re-enable JavaScript, complete the following actions.</span></span>  

*   <span data-ttu-id="de54e-121">再次 **打开命令菜单** 并运行 `Enable JavaScript` 命令。</span><span class="sxs-lookup"><span data-stu-id="de54e-121">Open the **Command Menu** again and run the `Enable JavaScript` command.</span></span>  
*   <span data-ttu-id="de54e-122">关闭 DevTools。</span><span class="sxs-lookup"><span data-stu-id="de54e-122">Close DevTools.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="de54e-123">联系 Microsoft Edge 开发人员工具团队</span><span class="sxs-lookup"><span data-stu-id="de54e-123">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsOpen]: ../open/index.md "打开 Microsoft Edge 开发人员工具 | Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="de54e-125">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="de54e-125">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="de54e-126">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/disable)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="de54e-126">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/disable) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="de54e-128">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="de54e-128">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
