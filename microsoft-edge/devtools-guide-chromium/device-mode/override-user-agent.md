---
title: 覆盖 Microsoft Edge DevTools 中的用户代理字符串
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 376e1550d0dc31f3b47b6badd6970076a8c13f91
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607305"
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





# <span data-ttu-id="76d0d-103">覆盖 Microsoft Edge DevTools 中的用户代理字符串</span><span class="sxs-lookup"><span data-stu-id="76d0d-103">Override The User Agent String From Microsoft Edge DevTools</span></span>   



<span data-ttu-id="76d0d-104">若要覆盖 Microsoft Edge DevTools 中的[用户代理][MDNUserAgent]字符串，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="76d0d-104">To override the [user agent][MDNUserAgent] string from Microsoft Edge DevTools:</span></span>  

1.  <span data-ttu-id="76d0d-105">按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "**命令" 菜单**。</span><span class="sxs-lookup"><span data-stu-id="76d0d-105">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    > ##### <span data-ttu-id="76d0d-106">图 1</span><span class="sxs-lookup"><span data-stu-id="76d0d-106">Figure 1</span></span>  
    > <span data-ttu-id="76d0d-107">命令菜单</span><span class="sxs-lookup"><span data-stu-id="76d0d-107">The Command Menu</span></span>  
    > ![命令菜单][ImageCommandMenu]  
    
1.  <span data-ttu-id="76d0d-109">键入 `network conditions` ，选择 "**显示网络条件**"，然后按 `Enter` 以打开 "**网络条件**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="76d0d-109">Type `network conditions`, select **Show Network conditions**, and press `Enter` to open the **Network conditions** tab.</span></span>  
1.  <span data-ttu-id="76d0d-110">在 "**用户代理**" 部分中，禁用 "**自动选择**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="76d0d-110">In the **User agent** section, disable the **Select automatically** checkbox.</span></span>  
    
    > ##### <span data-ttu-id="76d0d-111">图 2</span><span class="sxs-lookup"><span data-stu-id="76d0d-111">Figure 2</span></span>  
    > <span data-ttu-id="76d0d-112">禁用 "**自动选择**"</span><span class="sxs-lookup"><span data-stu-id="76d0d-112">Disabling **Select automatically**</span></span>  
    > ![禁用 "自动选择"][ImageUserAgentDisableSelectAutomatically]  
    
1.  <span data-ttu-id="76d0d-114">从列表中选择用户代理字符串，或输入您自己的自定义字符串。</span><span class="sxs-lookup"><span data-stu-id="76d0d-114">Select a user agent string from the list, or enter your own custom string.</span></span>  

<!--## Feedback   -->  



<!-- image links -->  

[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/device-mode-console-command-menu.msft.png "图1：命令菜单"  
[ImageUserAgentDisableSelectAutomatically]: /microsoft-edge/devtools-guide-chromium/media/device-mode-console-network-conditions-user-agent-select-automatically-deselected.msft.png "图2：禁用 "自动选择""  

<!-- links -->  

[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "用户代理 |MDN"  

> [!NOTE]
> <span data-ttu-id="76d0d-118">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="76d0d-118">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="76d0d-119">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/override-user-agent)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="76d0d-119">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/override-user-agent) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="76d0d-121">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="76d0d-121">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
