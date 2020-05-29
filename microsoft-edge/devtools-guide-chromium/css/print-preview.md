---
title: 强制 Microsoft Edge DevTools 进入打印预览模式（CSS 打印媒体类型）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 659120414597273b15657377c33c800e0c83b7cb
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601836"
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





# <span data-ttu-id="8a4f8-103">强制 Microsoft Edge DevTools 进入打印预览模式（CSS 打印媒体类型）</span><span class="sxs-lookup"><span data-stu-id="8a4f8-103">Force Microsoft Edge DevTools Into Print Preview Mode (CSS Print Media Type)</span></span>   



<span data-ttu-id="8a4f8-104">"[打印媒体" 查询][MDNUsingMediaQueries]将控制页面打印时的外观。</span><span class="sxs-lookup"><span data-stu-id="8a4f8-104">The [print media query][MDNUsingMediaQueries] controls how your page looks when printed.</span></span>  <span data-ttu-id="8a4f8-105">若要强制页面进入 "打印预览" 模式，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8a4f8-105">To force your page into print preview mode:</span></span>  

1.  <span data-ttu-id="8a4f8-106">按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "**命令" 菜单**。</span><span class="sxs-lookup"><span data-stu-id="8a4f8-106">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    > ##### <span data-ttu-id="8a4f8-107">图 1</span><span class="sxs-lookup"><span data-stu-id="8a4f8-107">Figure 1</span></span>  
    > <span data-ttu-id="8a4f8-108">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="8a4f8-108">The **Command Menu**</span></span>  
    > ![命令菜单][ImageCommandMenu]  
    
1.  <span data-ttu-id="8a4f8-110">键入 `rendering` ，选择 "**显示呈现**"，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="8a4f8-110">Type `rendering`, select **Show Rendering**, and then press `Enter`.</span></span>  
1.  <span data-ttu-id="8a4f8-111">在 "**模拟 CSS 媒体**" 下选择 "**打印**"。</span><span class="sxs-lookup"><span data-stu-id="8a4f8-111">Under **Emulate CSS media** select **print**.</span></span>  
    
    > ##### <span data-ttu-id="8a4f8-112">图 2</span><span class="sxs-lookup"><span data-stu-id="8a4f8-112">Figure 2</span></span>  
    > <span data-ttu-id="8a4f8-113">打印预览模式</span><span class="sxs-lookup"><span data-stu-id="8a4f8-113">Print preview mode</span></span>  
    > ![打印预览模式][ImagePrintMode]  
    
<span data-ttu-id="8a4f8-115">在此处，您可以查看和更改您的 CSS，就像任何其他网页一样。</span><span class="sxs-lookup"><span data-stu-id="8a4f8-115">From here, you can view and change your CSS, like any other web page.</span></span>  <span data-ttu-id="8a4f8-116">请参阅[查看和更改 CSS 入门][DevToolsCSSGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="8a4f8-116">See [Get Started With Viewing And Changing CSS][DevToolsCSSGetStarted].</span></span>  

 



<!-- image links -->  

[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-console-command-menu-rendering.msft.png "图1：命令菜单"  
[ImagePrintMode]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png "图2：打印预览模式"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  
[DevToolsCSSGetStarted]: /microsoft-edge/devtools-guide-chromium/css/index "查看和更改 CSS 入门"  

[MDNUsingMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "使用媒体查询 |MDN"  

> [!NOTE]
> <span data-ttu-id="8a4f8-122">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="8a4f8-122">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="8a4f8-123">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/print-preview)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="8a4f8-123">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/print-preview) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="8a4f8-125">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="8a4f8-125">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
