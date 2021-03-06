---
description: 打开"呈现"工具，然后选择"模拟 CSS 媒体>打印。
title: '强制 Microsoft Edge DevTools 进入打印预览模式 (CSS 打印媒体类型) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 0123b7abf475212304f654c04bc232e3e96f0bda
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399076"
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

# <a name="force-microsoft-edge-devtools-into-print-preview-mode"></a><span data-ttu-id="041db-104">强制 Microsoft Edge DevTools 进入打印预览模式</span><span class="sxs-lookup"><span data-stu-id="041db-104">Force Microsoft Edge DevTools into Print Preview mode</span></span>  

<span data-ttu-id="041db-105">打印 [媒体查询][MDNUsingMediaQueries] 控制页面在打印时的外观。</span><span class="sxs-lookup"><span data-stu-id="041db-105">The [print media query][MDNUsingMediaQueries] controls how your page looks when printed.</span></span>  <span data-ttu-id="041db-106">若要强制页面进入打印预览模式，</span><span class="sxs-lookup"><span data-stu-id="041db-106">To force your page into print preview mode:</span></span>  

1.  <span data-ttu-id="041db-107">选择 `Control`+`Shift`+`P` \(Windows、Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开**命令菜单**。</span><span class="sxs-lookup"><span data-stu-id="041db-107">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       <span data-ttu-id="041db-109">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="041db-109">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="041db-110">键入 `rendering` ，选择 **"显示呈现"，** 然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="041db-110">Type `rendering`, choose **Show Rendering**, and then select `Enter`.</span></span>  
1.  <span data-ttu-id="041db-111">在 **"模拟 CSS 媒体"下**，选择 **"打印"。**</span><span class="sxs-lookup"><span data-stu-id="041db-111">Under **Emulate CSS media**, choose **print**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png" alt-text="打印预览模式" lightbox="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png":::
       <span data-ttu-id="041db-113">打印预览模式</span><span class="sxs-lookup"><span data-stu-id="041db-113">Print preview mode</span></span>  
    :::image-end:::  
    
<span data-ttu-id="041db-114">可以在此处显示和更改 CSS，就像任何其他网页一样。</span><span class="sxs-lookup"><span data-stu-id="041db-114">From here, you may display and change your CSS, like any other web page.</span></span>  <span data-ttu-id="041db-115">导航到["开始查看和更改 CSS"。][DevToolsCSSGetStarted]</span><span class="sxs-lookup"><span data-stu-id="041db-115">Navigate to [Get Started With Viewing And Changing CSS][DevToolsCSSGetStarted].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="041db-116">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="041db-116">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具|Microsoft Docs"  
[DevToolsCSSGetStarted]: ./index.md "开始查看和更改 CSS |Microsoft Docs"  

[MDNUsingMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "使用媒体查询|MDN"  

> [!NOTE]
> <span data-ttu-id="041db-120">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="041db-120">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="041db-121">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/print-preview)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="041db-121">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/print-preview) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="041db-123">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="041db-123">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
