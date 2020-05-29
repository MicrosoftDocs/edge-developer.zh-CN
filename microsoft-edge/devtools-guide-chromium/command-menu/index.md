---
title: 通过 Microsoft Edge DevTools 命令菜单运行命令
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 748008b347a3498008748b9c3f9ecc1445c47f12
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601745"
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





# <span data-ttu-id="1cc8d-103">通过 Microsoft Edge DevTools 命令菜单运行命令</span><span class="sxs-lookup"><span data-stu-id="1cc8d-103">Run Commands With The Microsoft Edge DevTools Command Menu</span></span>   

  

<span data-ttu-id="1cc8d-104">命令菜单提供了一种快速浏览 Microsoft Edge DevTools UI 和完成常见任务（如[禁用 JavaScript][JavascriptDisable]）的方法。</span><span class="sxs-lookup"><span data-stu-id="1cc8d-104">The Command Menu provides a fast way to navigate the Microsoft Edge DevTools UI and accomplish common tasks, such as [disabling JavaScript][JavascriptDisable].</span></span>  <span data-ttu-id="1cc8d-105">你可能会熟悉 Visual Studio 代码中称为[命令调色板][VisualStudioCodeUICommandPalette]的类似功能，这是命令菜单的初始灵感。</span><span class="sxs-lookup"><span data-stu-id="1cc8d-105">You may be familiar with a similar feature in Visual Studio Code called the [Command Palette][VisualStudioCodeUICommandPalette], which was the original inspiration for the Command Menu.</span></span>  

> ##### <span data-ttu-id="1cc8d-106">图 1</span><span class="sxs-lookup"><span data-stu-id="1cc8d-106">Figure 1</span></span>  
> <span data-ttu-id="1cc8d-107">使用 "命令" 菜单禁用 JavaScript</span><span class="sxs-lookup"><span data-stu-id="1cc8d-107">Using the Command Menu to disable JavaScript</span></span>  
> ![使用 "命令" 菜单禁用 JavaScript][ImageDisableJS]  

## <span data-ttu-id="1cc8d-109">打开 "命令" 菜单</span><span class="sxs-lookup"><span data-stu-id="1cc8d-109">Open the Command Menu</span></span>   

<span data-ttu-id="1cc8d-110">按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）。</span><span class="sxs-lookup"><span data-stu-id="1cc8d-110">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\).</span></span> <span data-ttu-id="1cc8d-111">或者单击 "**自定义和控制 DevTools** " `...` ，然后选择 "**运行命令**"。</span><span class="sxs-lookup"><span data-stu-id="1cc8d-111">Or click **Customize And Control DevTools** `...` and then select **Run Command**.</span></span>  

> ##### <span data-ttu-id="1cc8d-112">图 2</span><span class="sxs-lookup"><span data-stu-id="1cc8d-112">Figure 2</span></span>  
> <span data-ttu-id="1cc8d-113">运行命令</span><span class="sxs-lookup"><span data-stu-id="1cc8d-113">Run Command</span></span>  
> ![运行命令][ImageRunCommand]  

## <span data-ttu-id="1cc8d-115">查看其他可用操作</span><span class="sxs-lookup"><span data-stu-id="1cc8d-115">See other available actions</span></span>   

<span data-ttu-id="1cc8d-116">如果您使用 "[打开命令" 菜单](#open-the-command-menu)中所述的工作流，则 "命令" 菜单将打开，其中包含一个 `>` 字符预置到 "命令菜单" 文本框。</span><span class="sxs-lookup"><span data-stu-id="1cc8d-116">If you use the workflow outlined in [Open the Command Menu](#open-the-command-menu), the Command Menu opens with a `>` character prepended to the Command Menu text box.</span></span>  

> ##### <span data-ttu-id="1cc8d-117">图 3</span><span class="sxs-lookup"><span data-stu-id="1cc8d-117">Figure 3</span></span>  
> <span data-ttu-id="1cc8d-118">命令字符</span><span class="sxs-lookup"><span data-stu-id="1cc8d-118">The command character</span></span>  
> ![命令字符][ImageCommandCharacter]  

<span data-ttu-id="1cc8d-120">删除 " `>` 字符" 和 "类型"， `?` 以查看 "命令" 菜单中提供的其他操作。</span><span class="sxs-lookup"><span data-stu-id="1cc8d-120">Delete the `>` character and type `?` to see other actions that are available from the Command Menu.</span></span>  

> ##### <span data-ttu-id="1cc8d-121">图 4</span><span class="sxs-lookup"><span data-stu-id="1cc8d-121">Figure 4</span></span>  
> <span data-ttu-id="1cc8d-122">其他可用操作</span><span class="sxs-lookup"><span data-stu-id="1cc8d-122">Other available actions</span></span>  
> ![其他可用操作][ImageActions]  

 



<!-- image links -->  

[ImageDisableJS]: /microsoft-edge/devtools-guide-chromium/media/command-menu-run-command-java.msft.png "图1：使用 "命令" 菜单禁用 JavaScript"  
[ImageRunCommand]: /microsoft-edge/devtools-guide-chromium/media/command-menu-options-run-command.msft.png "图2：运行命令"  
[ImageCommandCharacter]: /microsoft-edge/devtools-guide-chromium/media/command-menu-run-command.msft.png "图3：命令字符"  
[ImageActions]: /microsoft-edge/devtools-guide-chromium/media/command-menu-help.msft.png "图4：其他可用操作"  

<!-- links -->  

[JavascriptDisable]: /microsoft-edge/devtools-guide-chromium/javascript/disable "通过 Microsoft Edge DevTools 禁用 JavaScript"  

[VisualStudioCodeUICommandPalette]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette "命令调色板-Visual Studio 代码 UI"  

> [!NOTE]
> <span data-ttu-id="1cc8d-130">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="1cc8d-130">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1cc8d-131">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/command-menu/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="1cc8d-131">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/command-menu/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="1cc8d-133">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="1cc8d-133">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
