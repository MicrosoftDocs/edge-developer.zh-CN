---
description: 有关打开命令菜单、运行命令、查看其他操作等的指南。
title: 使用开发人员工具Microsoft Edge菜单运行命令
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: b815934da73f9f023629564da7bea14da166ff9b
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519189"
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

# <a name="run-commands-with-the-microsoft-edge-devtools-command-menu"></a><span data-ttu-id="3ec11-104">使用开发人员工具Microsoft Edge菜单运行命令</span><span class="sxs-lookup"><span data-stu-id="3ec11-104">Run commands with the Microsoft Edge DevTools Command Menu</span></span>  

<span data-ttu-id="3ec11-105">命令菜单提供了在 DevTools UI Microsoft Edge导航和完成常见任务（如[禁用 JavaScript）的快速方法][JavascriptDisable]。</span><span class="sxs-lookup"><span data-stu-id="3ec11-105">The Command Menu provides a fast way to navigate the Microsoft Edge DevTools UI and accomplish common tasks, such as [disabling JavaScript][JavascriptDisable].</span></span>  <span data-ttu-id="3ec11-106">你可能熟悉命令调色板Microsoft Visual Studio代码中的类似功能，这是命令菜单的原始灵感[][VisualStudioCodeUICommandPalette]。</span><span class="sxs-lookup"><span data-stu-id="3ec11-106">You may be familiar with a similar feature in Microsoft Visual Studio Code called the [Command Palette][VisualStudioCodeUICommandPalette], which was the original inspiration for the Command Menu.</span></span>  

:::image type="complex" source="../media/command-menu-run-command-java.msft.png" alt-text="使用命令菜单禁用 JavaScript" lightbox="../media/command-menu-run-command-java.msft.png":::
   <span data-ttu-id="3ec11-108">使用命令菜单禁用 JavaScript</span><span class="sxs-lookup"><span data-stu-id="3ec11-108">Using the Command Menu to disable JavaScript</span></span>  
:::image-end:::  

## <a name="open-the-command-menu"></a><span data-ttu-id="3ec11-109">打开命令菜单</span><span class="sxs-lookup"><span data-stu-id="3ec11-109">Open the Command Menu</span></span>  

<span data-ttu-id="3ec11-110">选择 `Control` + `Shift` + `P` \(Windows、Linux\) 或 `Command` + `Shift` + `P` \(macOS\)。</span><span class="sxs-lookup"><span data-stu-id="3ec11-110">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span> <span data-ttu-id="3ec11-111">或选择 **自定义和控制开发工具** \ (`...` \) > **运行命令**。</span><span class="sxs-lookup"><span data-stu-id="3ec11-111">Or choose **Customize And Control DevTools** \(`...`\) > **Run Command**.</span></span>  

:::image type="complex" source="../media/command-menu-options-run-command.msft.png" alt-text="运行命令" lightbox="../media/command-menu-options-run-command.msft.png":::
   <span data-ttu-id="3ec11-113">运行命令</span><span class="sxs-lookup"><span data-stu-id="3ec11-113">Run Command</span></span>  
:::image-end:::  

## <a name="display-other-available-actions"></a><span data-ttu-id="3ec11-114">显示其他可用操作</span><span class="sxs-lookup"><span data-stu-id="3ec11-114">Display other available actions</span></span>  

<span data-ttu-id="3ec11-115">如果使用"打开命令菜单"中概述[](#open-the-command-menu)的工作流，"命令菜单"将打开，并预先将字符绘制到"命令菜单 `>` "文本框中。</span><span class="sxs-lookup"><span data-stu-id="3ec11-115">If you use the workflow outlined in [Open the Command Menu](#open-the-command-menu), the Command Menu opens with a `>` character pre-pended to the Command Menu text box.</span></span>  

:::image type="complex" source="../media/command-menu-run-command.msft.png" alt-text="命令字符" lightbox="../media/command-menu-run-command.msft.png":::
   <span data-ttu-id="3ec11-117">命令字符</span><span class="sxs-lookup"><span data-stu-id="3ec11-117">The command character</span></span>  
:::image-end:::  

<span data-ttu-id="3ec11-118">删除 `>` 字符和类型 `?` 以显示"命令菜单"中提供的其他操作。</span><span class="sxs-lookup"><span data-stu-id="3ec11-118">Delete the `>` character and type `?` to display other actions that are available from the Command Menu.</span></span>  

:::image type="complex" source="../media/command-menu-help.msft.png" alt-text="其他可用操作" lightbox="../media/command-menu-help.msft.png":::
   <span data-ttu-id="3ec11-120">其他可用操作</span><span class="sxs-lookup"><span data-stu-id="3ec11-120">Other available actions</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="3ec11-121">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="3ec11-121">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[JavascriptDisable]: ../javascript/disable.md "使用开发人员工具Microsoft Edge JavaScript |Microsoft Docs"  

[VisualStudioCodeUICommandPalette]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette "命令调色板 - Visual Studio Code UI"  

> [!NOTE]
> <span data-ttu-id="3ec11-124">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="3ec11-124">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3ec11-125">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/command-menu/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="3ec11-125">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/command-menu/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="3ec11-127">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="3ec11-127">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
