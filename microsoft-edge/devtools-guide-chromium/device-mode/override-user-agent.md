---
description: 打开"网络条件"工具，禁用"自动选择"，然后从列表中选择或输入自定义字符串。
title: 替代 DevTools 中的Microsoft Edge字符串
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 50d831847342c749cd36f203998351d53325a6f8
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564292"
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
# <a name="override-the-user-agent-string-from-microsoft-edge-devtools"></a><span data-ttu-id="e3ae0-104">替代 DevTools 中的Microsoft Edge字符串</span><span class="sxs-lookup"><span data-stu-id="e3ae0-104">Override the user agent string from Microsoft Edge DevTools</span></span>  

<span data-ttu-id="e3ae0-105">若要覆盖[DevTools 中的][MDNUserAgent]用户Microsoft Edge字符串：</span><span class="sxs-lookup"><span data-stu-id="e3ae0-105">To override the [user agent][MDNUserAgent] string from Microsoft Edge DevTools:</span></span>  

1.  <span data-ttu-id="e3ae0-106">选择 `Control`+`Shift`+`P` \(Windows、Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开**命令菜单**。</span><span class="sxs-lookup"><span data-stu-id="e3ae0-106">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-console-command-menu.msft.png" alt-text="命令菜单" lightbox="../media/device-mode-console-command-menu.msft.png":::
       <span data-ttu-id="e3ae0-108">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="e3ae0-108">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="e3ae0-109">键入 `network conditions` ，选择 **"显示网络条件**"，然后选择 `Enter` 以打开 **"网络条件"** 工具。</span><span class="sxs-lookup"><span data-stu-id="e3ae0-109">Type `network conditions`, choose **Show Network conditions**, and select `Enter` to open the **Network conditions** tool.</span></span>  
1.  <span data-ttu-id="e3ae0-110">在" **用户代理"** 部分，关闭" **自动选择"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="e3ae0-110">In the **User agent** section, turn off the **Select automatically** checkbox.</span></span>  
    
    :::image type="complex" source="../media/device-mode-console-network-conditions-user-agent-select-automatically-deselected.msft.png" alt-text="关闭"自动选择"" lightbox="../media/device-mode-console-network-conditions-user-agent-select-automatically-deselected.msft.png":::
       <span data-ttu-id="e3ae0-112">关闭" **自动选择"**</span><span class="sxs-lookup"><span data-stu-id="e3ae0-112">Turn off **Select automatically**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="e3ae0-113">从列表中选择用户代理字符串，或输入你自己的自定义字符串。</span><span class="sxs-lookup"><span data-stu-id="e3ae0-113">Choose a user agent string from the list, or enter your own custom string.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="e3ae0-114">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="e3ae0-114">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "用户代理|MDN"  

> [!NOTE]
> <span data-ttu-id="e3ae0-116">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="e3ae0-116">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e3ae0-117">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/override-user-agent)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="e3ae0-117">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/override-user-agent) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="e3ae0-119">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="e3ae0-119">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
