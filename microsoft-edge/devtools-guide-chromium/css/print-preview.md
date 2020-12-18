---
description: 打开"呈现"选项卡并选择"模拟 CSS 媒体">"print"。
title: '强制 Microsoft Edge DevTools 进入打印预览模式 (CSS 打印媒体类型) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: a036e710de998f03e876126581956929d8652f1e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230920"
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

# <span data-ttu-id="be1a7-104">强制 Microsoft Edge DevTools 使用 CSS 打印媒体类型 (打印预览模式) </span><span class="sxs-lookup"><span data-stu-id="be1a7-104">Force Microsoft Edge DevTools into Print Preview mode (CSS Print Media Type)</span></span>  

<span data-ttu-id="be1a7-105">打印 [媒体查询][MDNUsingMediaQueries] 控制页面在打印时的外观。</span><span class="sxs-lookup"><span data-stu-id="be1a7-105">The [print media query][MDNUsingMediaQueries] controls how your page looks when printed.</span></span>  <span data-ttu-id="be1a7-106">若要强制页面进入打印预览模式：</span><span class="sxs-lookup"><span data-stu-id="be1a7-106">To force your page into print preview mode:</span></span>  

1.  <span data-ttu-id="be1a7-107">选择 `Control`+`Shift`+`P` \(Windows、Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开**命令菜单**。</span><span class="sxs-lookup"><span data-stu-id="be1a7-107">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       <span data-ttu-id="be1a7-109">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="be1a7-109">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="be1a7-110">键入 `rendering` ，选择 **"显示呈现**"，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="be1a7-110">Type `rendering`, choose **Show Rendering**, and then select `Enter`.</span></span>  
1.  <span data-ttu-id="be1a7-111">在 **"模拟 CSS 媒体"下**，选择 **"打印"。**</span><span class="sxs-lookup"><span data-stu-id="be1a7-111">Under **Emulate CSS media**, choose **print**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png" alt-text="打印预览模式" lightbox="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png":::
       <span data-ttu-id="be1a7-113">打印预览模式</span><span class="sxs-lookup"><span data-stu-id="be1a7-113">Print preview mode</span></span>  
    :::image-end:::  
    
<span data-ttu-id="be1a7-114">可以在此处查看和更改 CSS，就像任何其他网页一样。</span><span class="sxs-lookup"><span data-stu-id="be1a7-114">From here, you can view and change your CSS, like any other web page.</span></span>  <span data-ttu-id="be1a7-115">导航到["查看和更改 CSS 入门"。][DevToolsCSSGetStarted]</span><span class="sxs-lookup"><span data-stu-id="be1a7-115">Navigate to [Get Started With Viewing And Changing CSS][DevToolsCSSGetStarted].</span></span>  

## <span data-ttu-id="be1a7-116">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="be1a7-116">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 |Microsoft Docs"  
[DevToolsCSSGetStarted]: ./index.md "开始查看和更改 CSS |Microsoft Docs"  

[MDNUsingMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "使用媒体查询 |MDN"  

> [!NOTE]
> <span data-ttu-id="be1a7-120">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="be1a7-120">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="be1a7-121">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/print-preview)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="be1a7-121">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/print-preview) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="be1a7-123">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="be1a7-123">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
