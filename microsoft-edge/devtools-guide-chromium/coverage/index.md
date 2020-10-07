---
description: How to find and analyze unused JavaScript and CSS code in Microsoft Edge DevTools.
title: Find Unused JavaScript And CSS Code With The Coverage Tab In Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 19bc15578e00e5a9f3389529f589e9790280a0e4
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993091"
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





# <span data-ttu-id="10fc8-104">Find Unused JavaScript And CSS Code With The Coverage Tab In Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="10fc8-104">Find Unused JavaScript And CSS Code With The Coverage Tab In Microsoft Edge DevTools</span></span>   



<span data-ttu-id="10fc8-105">The Coverage tab in Microsoft Edge DevTools helps you find unused JavaScript and CSS code.</span><span class="sxs-lookup"><span data-stu-id="10fc8-105">The Coverage tab in Microsoft Edge DevTools helps you find unused JavaScript and CSS code.</span></span>  <span data-ttu-id="10fc8-106">Removing unused code may speed up your page load and save your mobile users cellular data.</span><span class="sxs-lookup"><span data-stu-id="10fc8-106">Removing unused code may speed up your page load and save your mobile users cellular data.</span></span>  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage.msft.png" alt-text="Analyzing code coverage" lightbox="../media/coverage-sources-resource-drawer-coverage.msft.png":::
   <span data-ttu-id="10fc8-108">Analyzing code coverage</span><span class="sxs-lookup"><span data-stu-id="10fc8-108">Analyzing code coverage</span></span>  
:::image-end:::  

> [!WARNING]
> <span data-ttu-id="10fc8-109">Finding unused code is relatively easy.</span><span class="sxs-lookup"><span data-stu-id="10fc8-109">Finding unused code is relatively easy.</span></span>  <span data-ttu-id="10fc8-110">But refactoring a codebase so that each page only ships the JavaScript and CSS that it needs may be difficult.</span><span class="sxs-lookup"><span data-stu-id="10fc8-110">But refactoring a codebase so that each page only ships the JavaScript and CSS that it needs may be difficult.</span></span>  <span data-ttu-id="10fc8-111">This guide does not cover how to refactor a codebase to avoid unused code because these refactors depend highly on your technology stack.</span><span class="sxs-lookup"><span data-stu-id="10fc8-111">This guide does not cover how to refactor a codebase to avoid unused code because these refactors depend highly on your technology stack.</span></span>  

## <span data-ttu-id="10fc8-112">Overview</span><span class="sxs-lookup"><span data-stu-id="10fc8-112">Overview</span></span>   

<span data-ttu-id="10fc8-113">Shipping unused JavaScript or CSS is a common problem in web development.</span><span class="sxs-lookup"><span data-stu-id="10fc8-113">Shipping unused JavaScript or CSS is a common problem in web development.</span></span>  <span data-ttu-id="10fc8-114">For example, suppose that you want to use [Bootstrap button component][BootstrapButtons] on your page.</span><span class="sxs-lookup"><span data-stu-id="10fc8-114">For example, suppose that you want to use [Bootstrap button component][BootstrapButtons] on your page.</span></span>  <span data-ttu-id="10fc8-115">To use the button component you need to add a link to the Bootstrap stylesheet in your HTML, like this:</span><span class="sxs-lookup"><span data-stu-id="10fc8-115">To use the button component you need to add a link to the Bootstrap stylesheet in your HTML, like this:</span></span>  

```html
...
<head>
    ...
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    ...
</head>
...
```  

<span data-ttu-id="10fc8-116">This stylesheet does not just include the code for the button component.</span><span class="sxs-lookup"><span data-stu-id="10fc8-116">This stylesheet does not just include the code for the button component.</span></span>  <span data-ttu-id="10fc8-117">It contains the CSS for **all** of the Bootstrap components.</span><span class="sxs-lookup"><span data-stu-id="10fc8-117">It contains the CSS for **all** of the Bootstrap components.</span></span>  <span data-ttu-id="10fc8-118">But you are not using any of the other Bootstrap components.</span><span class="sxs-lookup"><span data-stu-id="10fc8-118">But you are not using any of the other Bootstrap components.</span></span>  <span data-ttu-id="10fc8-119">So your page is downloading a bunch of CSS that it does not need.</span><span class="sxs-lookup"><span data-stu-id="10fc8-119">So your page is downloading a bunch of CSS that it does not need.</span></span>  <span data-ttu-id="10fc8-120">This extra CSS is a problem for the following reasons.</span><span class="sxs-lookup"><span data-stu-id="10fc8-120">This extra CSS is a problem for the following reasons.</span></span>  

*   <span data-ttu-id="10fc8-121">The extra code slows down your page load.</span><span class="sxs-lookup"><span data-stu-id="10fc8-121">The extra code slows down your page load.</span></span>  <!--See [Render-Blocking CSS][render].  -->  
*   <span data-ttu-id="10fc8-122">If a user accesses the page on a mobile device, the extra code uses up their cellular data.</span><span class="sxs-lookup"><span data-stu-id="10fc8-122">If a user accesses the page on a mobile device, the extra code uses up their cellular data.</span></span>  
    
<!--[render]: /web/fundamentals/performance/critical-rendering-path/render-blocking-css  -->  

## <span data-ttu-id="10fc8-123">Open the Coverage tab</span><span class="sxs-lookup"><span data-stu-id="10fc8-123">Open the Coverage tab</span></span>   

1.  <span data-ttu-id="10fc8-124">[Open the Command Menu][DevToolsCommandMenu].</span><span class="sxs-lookup"><span data-stu-id="10fc8-124">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="10fc8-125">Start typing `coverage`, select the **Show Coverage** command, and then press `Enter` to run the command.</span><span class="sxs-lookup"><span data-stu-id="10fc8-125">Start typing `coverage`, select the **Show Coverage** command, and then press `Enter` to run the command.</span></span>  <span data-ttu-id="10fc8-126">The **Coverage** tab opens in the **Drawer**.</span><span class="sxs-lookup"><span data-stu-id="10fc8-126">The **Coverage** tab opens in the **Drawer**.</span></span>  

    :::image type="complex" source="../media/coverage-console-drawer-coverage-empty.msft.png" alt-text="Analyzing code coverage" lightbox="../media/coverage-console-drawer-coverage-empty.msft.png":::
       <span data-ttu-id="10fc8-128">The **Coverage** tab</span><span class="sxs-lookup"><span data-stu-id="10fc8-128">The **Coverage** tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="10fc8-129">Record code coverage</span><span class="sxs-lookup"><span data-stu-id="10fc8-129">Record code coverage</span></span>   

1.  <span data-ttu-id="10fc8-130">Click one of the following buttons in the **Coverage** tab:</span><span class="sxs-lookup"><span data-stu-id="10fc8-130">Click one of the following buttons in the **Coverage** tab:</span></span>  
    *   <span data-ttu-id="10fc8-131">Click **Start Instrumenting Coverage And Reload Page** \(![Start Instrumenting Coverage And Reload Page][ImageReloadIcon]\) if you want to see what code is needed to load the page.</span><span class="sxs-lookup"><span data-stu-id="10fc8-131">Click **Start Instrumenting Coverage And Reload Page** \(![Start Instrumenting Coverage And Reload Page][ImageReloadIcon]\) if you want to see what code is needed to load the page.</span></span>  
    *   <span data-ttu-id="10fc8-132">Click **Instrument Coverage** \(![Instrument Coverage][ImageRecordIcon]\) if you want to see what code is used after interacting with the page.</span><span class="sxs-lookup"><span data-stu-id="10fc8-132">Click **Instrument Coverage** \(![Instrument Coverage][ImageRecordIcon]\) if you want to see what code is used after interacting with the page.</span></span>  
1.  <span data-ttu-id="10fc8-133">Click **Stop Instrumenting Coverage And Show Results** \(![Stop Instrumenting Coverage And Show Results][ImageStopIcon]\) when you want to stop recording code coverage.</span><span class="sxs-lookup"><span data-stu-id="10fc8-133">Click **Stop Instrumenting Coverage And Show Results** \(![Stop Instrumenting Coverage And Show Results][ImageStopIcon]\) when you want to stop recording code coverage.</span></span>  
    
## <span data-ttu-id="10fc8-134">Analyze code coverage</span><span class="sxs-lookup"><span data-stu-id="10fc8-134">Analyze code coverage</span></span>   

<span data-ttu-id="10fc8-135">The table in the **Coverage** tab shows you what resources were analyzed, and how much code is used within each resource.</span><span class="sxs-lookup"><span data-stu-id="10fc8-135">The table in the **Coverage** tab shows you what resources were analyzed, and how much code is used within each resource.</span></span>  <span data-ttu-id="10fc8-136">Click a row to open that resource in the **Sources** panel and see a line-by-line breakdown of used code and unused code.</span><span class="sxs-lookup"><span data-stu-id="10fc8-136">Click a row to open that resource in the **Sources** panel and see a line-by-line breakdown of used code and unused code.</span></span>  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage-selected.msft.png" alt-text="Analyzing code coverage" lightbox="../media/coverage-sources-resource-drawer-coverage-selected.msft.png":::
   <span data-ttu-id="10fc8-138">A code coverage report</span><span class="sxs-lookup"><span data-stu-id="10fc8-138">A code coverage report</span></span>  
:::image-end:::  

*   <span data-ttu-id="10fc8-139">The **URL** column is the URL of the resource that was analyzed.</span><span class="sxs-lookup"><span data-stu-id="10fc8-139">The **URL** column is the URL of the resource that was analyzed.</span></span>  
*   <span data-ttu-id="10fc8-140">The **Type** column says whether the resource contains CSS, JavaScript, or both.</span><span class="sxs-lookup"><span data-stu-id="10fc8-140">The **Type** column says whether the resource contains CSS, JavaScript, or both.</span></span>  
*   <span data-ttu-id="10fc8-141">The **Total Bytes** column is the total size of the resource in bytes.</span><span class="sxs-lookup"><span data-stu-id="10fc8-141">The **Total Bytes** column is the total size of the resource in bytes.</span></span>  
*   <span data-ttu-id="10fc8-142">The **Unused Bytes** column is the number of bytes that were not used.</span><span class="sxs-lookup"><span data-stu-id="10fc8-142">The **Unused Bytes** column is the number of bytes that were not used.</span></span>  
*   <span data-ttu-id="10fc8-143">The last, unnamed column is a visualization of the **Total Bytes** and **Unused Bytes** columns.</span><span class="sxs-lookup"><span data-stu-id="10fc8-143">The last, unnamed column is a visualization of the **Total Bytes** and **Unused Bytes** columns.</span></span>  <span data-ttu-id="10fc8-144">The red section of the bar is unused bytes.</span><span class="sxs-lookup"><span data-stu-id="10fc8-144">The red section of the bar is unused bytes.</span></span>  <span data-ttu-id="10fc8-145">The green section is used bytes.</span><span class="sxs-lookup"><span data-stu-id="10fc8-145">The green section is used bytes.</span></span>  
    
<!--  
 


-->  

<!-- image links -->  

[ImageReloadIcon]: ../media/reload-icon.msft.png  
[ImageRecordIcon]: ../media/record-icon.msft.png  
[ImageStopIcon]: ../media/stop-icon.msft.png  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "Run commands with the Microsoft Edge DevTools Command menu | Microsoft Docs"  

[BootstrapButtons]: https://getbootstrap.com/docs/4.3/components/buttons "Buttons - Bootstrap"  

> [!NOTE]
> <span data-ttu-id="10fc8-148">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="10fc8-148">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="10fc8-149">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/coverage/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="10fc8-149">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/coverage/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="10fc8-151">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="10fc8-151">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
