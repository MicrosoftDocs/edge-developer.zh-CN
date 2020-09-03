---
description: 打开 "网络条件" 选项卡，禁用 "自动选择"，然后从列表中选择或输入自定义字符串。
title: 覆盖 Microsoft Edge DevTools 中的用户代理字符串
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: ecaa1247824e5c3acb07a2c631feab30d25aba8d
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992923"
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

# <span data-ttu-id="c7cde-104">覆盖 Microsoft Edge DevTools 中的用户代理字符串</span><span class="sxs-lookup"><span data-stu-id="c7cde-104">Override the user agent string from Microsoft Edge DevTools</span></span>  

<span data-ttu-id="c7cde-105">若要覆盖 Microsoft Edge DevTools 中的 [用户代理][MDNUserAgent] 字符串，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c7cde-105">To override the [user agent][MDNUserAgent] string from Microsoft Edge DevTools:</span></span>  

1.  <span data-ttu-id="c7cde-106">按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "**命令" 菜单**。</span><span class="sxs-lookup"><span data-stu-id="c7cde-106">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-console-command-menu.msft.png" alt-text="命令菜单" lightbox="../media/device-mode-console-command-menu.msft.png":::
       <span data-ttu-id="c7cde-108">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="c7cde-108">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c7cde-109">键入 `network conditions` ，选择 " **显示网络条件**"，然后按 `Enter` 以打开 " **网络条件** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c7cde-109">Type `network conditions`, select **Show Network conditions**, and press `Enter` to open the **Network conditions** tab.</span></span>  
1.  <span data-ttu-id="c7cde-110">在 " **用户代理** " 部分中，禁用 " **自动选择** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="c7cde-110">In the **User agent** section, disable the **Select automatically** checkbox.</span></span>  
    
    :::image type="complex" source="../media/device-mode-console-network-conditions-user-agent-select-automatically-deselected.msft.png" alt-text="禁用 "自动选择"" lightbox="../media/device-mode-console-network-conditions-user-agent-select-automatically-deselected.msft.png":::
       <span data-ttu-id="c7cde-112">禁用 "**自动选择**"</span><span class="sxs-lookup"><span data-stu-id="c7cde-112">Disable **Select automatically**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c7cde-113">从列表中选择用户代理字符串，或输入您自己的自定义字符串。</span><span class="sxs-lookup"><span data-stu-id="c7cde-113">Select a user agent string from the list, or enter your own custom string.</span></span>  

## <span data-ttu-id="c7cde-114">与 Microsoft Edge DevTools 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="c7cde-114">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "用户代理 |MDN"  

> [!NOTE]
> <span data-ttu-id="c7cde-116">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="c7cde-116">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c7cde-117">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/override-user-agent)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="c7cde-117">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/override-user-agent) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="c7cde-119">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="c7cde-119">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
