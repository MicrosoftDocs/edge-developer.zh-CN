---
description: 有关如何打开 "命令" 菜单、"运行命令"、"查看其他操作" 等的指南。
title: 使用 Microsoft Edge 开发人员工具命令菜单运行命令
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 54dead492e7d58053efab77c82a10e7e3c912460
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993196"
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





# <span data-ttu-id="5fddb-104">使用 Microsoft Edge 开发人员工具命令菜单运行命令</span><span class="sxs-lookup"><span data-stu-id="5fddb-104">Run Commands With The Microsoft Edge DevTools Command Menu</span></span>   

  

<span data-ttu-id="5fddb-105">命令菜单提供了一种快速浏览 Microsoft Edge DevTools UI 和完成常见任务（如 [禁用 JavaScript][JavascriptDisable]）的方法。</span><span class="sxs-lookup"><span data-stu-id="5fddb-105">The Command Menu provides a fast way to navigate the Microsoft Edge DevTools UI and accomplish common tasks, such as [disabling JavaScript][JavascriptDisable].</span></span>  <span data-ttu-id="5fddb-106">你可能会熟悉 Visual Studio 代码中称为 [命令调色板][VisualStudioCodeUICommandPalette]的类似功能，这是命令菜单的初始灵感。</span><span class="sxs-lookup"><span data-stu-id="5fddb-106">You may be familiar with a similar feature in Visual Studio Code called the [Command Palette][VisualStudioCodeUICommandPalette], which was the original inspiration for the Command Menu.</span></span>  

:::image type="complex" source="../media/command-menu-run-command-java.msft.png" alt-text="使用 "命令" 菜单禁用 JavaScript" lightbox="../media/command-menu-run-command-java.msft.png":::
   <span data-ttu-id="5fddb-108">使用 "命令" 菜单禁用 JavaScript</span><span class="sxs-lookup"><span data-stu-id="5fddb-108">Using the Command Menu to disable JavaScript</span></span>  
:::image-end:::  

## <span data-ttu-id="5fddb-109">打开 "命令" 菜单</span><span class="sxs-lookup"><span data-stu-id="5fddb-109">Open the Command Menu</span></span>   

<span data-ttu-id="5fddb-110">按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 。</span><span class="sxs-lookup"><span data-stu-id="5fddb-110">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\).</span></span> <span data-ttu-id="5fddb-111">或者单击 " **自定义和控制 DevTools** " `...` ，然后选择 " **运行命令**"。</span><span class="sxs-lookup"><span data-stu-id="5fddb-111">Or click **Customize And Control DevTools** `...` and then select **Run Command**.</span></span>  

:::image type="complex" source="../media/command-menu-options-run-command.msft.png" alt-text="运行命令" lightbox="../media/command-menu-options-run-command.msft.png":::
   <span data-ttu-id="5fddb-113">运行命令</span><span class="sxs-lookup"><span data-stu-id="5fddb-113">Run Command</span></span>  
:::image-end:::  

## <span data-ttu-id="5fddb-114">查看其他可用操作</span><span class="sxs-lookup"><span data-stu-id="5fddb-114">See other available actions</span></span>   

<span data-ttu-id="5fddb-115">如果您使用 " [打开命令" 菜单](#open-the-command-menu)中所述的工作流，则 "命令" 菜单将打开，其中有一个 `>` 预挂起的字符到 "命令菜单" 文本框。</span><span class="sxs-lookup"><span data-stu-id="5fddb-115">If you use the workflow outlined in [Open the Command Menu](#open-the-command-menu), the Command Menu opens with a `>` character pre-pended to the Command Menu text box.</span></span>  

:::image type="complex" source="../media/command-menu-run-command.msft.png" alt-text="命令字符" lightbox="../media/command-menu-run-command.msft.png":::
   <span data-ttu-id="5fddb-117">命令字符</span><span class="sxs-lookup"><span data-stu-id="5fddb-117">The command character</span></span>  
:::image-end:::  

<span data-ttu-id="5fddb-118">删除 " `>` 字符" 和 "类型"， `?` 以查看 "命令" 菜单中提供的其他操作。</span><span class="sxs-lookup"><span data-stu-id="5fddb-118">Delete the `>` character and type `?` to see other actions that are available from the Command Menu.</span></span>  

:::image type="complex" source="../media/command-menu-help.msft.png" alt-text="其他可用操作" lightbox="../media/command-menu-help.msft.png":::
   <span data-ttu-id="5fddb-120">其他可用操作</span><span class="sxs-lookup"><span data-stu-id="5fddb-120">Other available actions</span></span>  
:::image-end:::  

 



<!-- links -->  

[JavascriptDisable]: ../javascript/disable.md "通过 Microsoft Edge DevTools 禁用 JavaScript |Microsoft 文档"  

[VisualStudioCodeUICommandPalette]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette "命令调色板-Visual Studio 代码 UI"  

> [!NOTE]
> <span data-ttu-id="5fddb-123">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="5fddb-123">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5fddb-124">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/command-menu/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="5fddb-124">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/command-menu/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="5fddb-126">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="5fddb-126">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
