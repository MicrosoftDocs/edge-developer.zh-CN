---
description: 如何在 Microsoft Edge DevTools 中查找和分析未使用的 JavaScript 和 CSS 代码。
title: 使用 Microsoft Edge DevTools 中的 "覆盖范围" 选项卡查找未使用的 JavaScript 和 CSS 代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 08c4daaabd30296b53ad57a81caa0e7b155a4fc9
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125186"
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

# <span data-ttu-id="3d36e-104">使用 Microsoft Edge DevTools 中的 "覆盖范围" 选项卡查找未使用的 JavaScript 和 CSS 代码</span><span class="sxs-lookup"><span data-stu-id="3d36e-104">Find Unused JavaScript And CSS Code With The Coverage Tab In Microsoft Edge DevTools</span></span>  

<span data-ttu-id="3d36e-105">Microsoft Edge DevTools 中的 "覆盖范围" 选项卡可帮助你查找未使用的 JavaScript 和 CSS 代码。</span><span class="sxs-lookup"><span data-stu-id="3d36e-105">The Coverage tab in Microsoft Edge DevTools helps you find unused JavaScript and CSS code.</span></span>  <span data-ttu-id="3d36e-106">删除未使用的代码可能会加速你的页面加载和保存移动用户手机网络数据。</span><span class="sxs-lookup"><span data-stu-id="3d36e-106">Removing unused code may speed up your page load and save your mobile users cellular data.</span></span>  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage.msft.png" alt-text="分析代码覆盖率" lightbox="../media/coverage-sources-resource-drawer-coverage.msft.png":::
   <span data-ttu-id="3d36e-108">分析代码覆盖率</span><span class="sxs-lookup"><span data-stu-id="3d36e-108">Analyzing code coverage</span></span>  
:::image-end:::  

> [!WARNING]
> <span data-ttu-id="3d36e-109">查找未使用的代码相对简单。</span><span class="sxs-lookup"><span data-stu-id="3d36e-109">Finding unused code is relatively easy.</span></span>  <span data-ttu-id="3d36e-110">但要重构基本代码，以便每个页面仅提供它所需的 JavaScript 和 CSS。</span><span class="sxs-lookup"><span data-stu-id="3d36e-110">But refactoring a codebase so that each page only ships the JavaScript and CSS that it needs may be difficult.</span></span>  <span data-ttu-id="3d36e-111">本指南不介绍如何重构基本代码以避免未使用的代码，因为这些 refactors 高度依赖于你的技术堆栈。</span><span class="sxs-lookup"><span data-stu-id="3d36e-111">This guide does not cover how to refactor a codebase to avoid unused code because these refactors depend highly on your technology stack.</span></span>  

## <span data-ttu-id="3d36e-112">概述</span><span class="sxs-lookup"><span data-stu-id="3d36e-112">Overview</span></span>  

<span data-ttu-id="3d36e-113">装运未使用的 JavaScript 或 CSS 是 web 开发中的常见问题。</span><span class="sxs-lookup"><span data-stu-id="3d36e-113">Shipping unused JavaScript or CSS is a common problem in web development.</span></span>  <span data-ttu-id="3d36e-114">例如，假设您想要在您的页面上使用 " [引导" 按钮组件][BootstrapButtons] 。</span><span class="sxs-lookup"><span data-stu-id="3d36e-114">For example, suppose that you want to use [Bootstrap button component][BootstrapButtons] on your page.</span></span>  <span data-ttu-id="3d36e-115">若要使用按钮组件，需要在 HTML 中添加指向引导样式表的链接，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3d36e-115">To use the button component you need to add a link to the Bootstrap stylesheet in your HTML, like this:</span></span>  

```html
...
<head>
    ...
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    ...
</head>
...
```  

<span data-ttu-id="3d36e-116">此样式表不仅仅包含按钮组件的代码。</span><span class="sxs-lookup"><span data-stu-id="3d36e-116">This stylesheet does not just include the code for the button component.</span></span>  <span data-ttu-id="3d36e-117">它包含 **所有** 引导组件的 CSS。</span><span class="sxs-lookup"><span data-stu-id="3d36e-117">It contains the CSS for **all** of the Bootstrap components.</span></span>  <span data-ttu-id="3d36e-118">但您没有使用任何其他的引导组件。</span><span class="sxs-lookup"><span data-stu-id="3d36e-118">But you are not using any of the other Bootstrap components.</span></span>  <span data-ttu-id="3d36e-119">因此，你的页面将下载一组不需要的 CSS。</span><span class="sxs-lookup"><span data-stu-id="3d36e-119">So your page is downloading a bunch of CSS that it does not need.</span></span>  <span data-ttu-id="3d36e-120">此额外的 CSS 是一个问题，原因如下。</span><span class="sxs-lookup"><span data-stu-id="3d36e-120">This extra CSS is a problem for the following reasons.</span></span>  

*   <span data-ttu-id="3d36e-121">额外的代码将减慢页面负载。</span><span class="sxs-lookup"><span data-stu-id="3d36e-121">The extra code slows down your page load.</span></span>  <!--See [Render-Blocking CSS][render].  -->  
*   <span data-ttu-id="3d36e-122">如果用户在移动设备上访问页面，则额外的代码将使用其手机网络数据。</span><span class="sxs-lookup"><span data-stu-id="3d36e-122">If a user accesses the page on a mobile device, the extra code uses up their cellular data.</span></span>  
    
<!--[render]: /web/fundamentals/performance/critical-rendering-path/render-blocking-css  -->  

## <span data-ttu-id="3d36e-123">打开 "覆盖范围" 选项卡</span><span class="sxs-lookup"><span data-stu-id="3d36e-123">Open the Coverage tab</span></span>  

1.  <span data-ttu-id="3d36e-124">[打开 "命令" 菜单][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="3d36e-124">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="3d36e-125">开始键入 `coverage` ，选择 " **显示覆盖率** " 命令，然后选择 `Enter` 运行命令。</span><span class="sxs-lookup"><span data-stu-id="3d36e-125">Start typing `coverage`, select the **Show Coverage** command, and then select `Enter` to run the command.</span></span>  <span data-ttu-id="3d36e-126">" **覆盖范围** " 选项卡将在 **抽屉**中打开。</span><span class="sxs-lookup"><span data-stu-id="3d36e-126">The **Coverage** tab opens in the **Drawer**.</span></span>  

    :::image type="complex" source="../media/coverage-console-drawer-coverage-empty.msft.png" alt-text="分析代码覆盖率" lightbox="../media/coverage-console-drawer-coverage-empty.msft.png":::
       <span data-ttu-id="3d36e-128">" **覆盖范围** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="3d36e-128">The **Coverage** tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="3d36e-129">记录代码覆盖率</span><span class="sxs-lookup"><span data-stu-id="3d36e-129">Record code coverage</span></span>  

1.  <span data-ttu-id="3d36e-130">单击 " **覆盖范围** " 选项卡中的以下按钮之一：</span><span class="sxs-lookup"><span data-stu-id="3d36e-130">Click one of the following buttons in the **Coverage** tab:</span></span>  
    *   <span data-ttu-id="3d36e-131">如果想要查看加载页面所需的代码，请选择 " **开始检测覆盖率" 和 "重新加载页面** \ (![ 开始检测覆盖率" 和 "重新加载页面 ][ImageReloadIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="3d36e-131">Choose **Start Instrumenting Coverage And Reload Page** \(![Start Instrumenting Coverage And Reload Page][ImageReloadIcon]\) if you want to see what code is needed to load the page.</span></span>  
    *   <span data-ttu-id="3d36e-132">**Instrument Coverage** ![ ][ImageRecordIcon] 如果想要查看在与页面交互之后使用的代码，请选择 "仪器覆盖率 \ (仪器覆盖范围 \ ) "。</span><span class="sxs-lookup"><span data-stu-id="3d36e-132">Choose **Instrument Coverage** \(![Instrument Coverage][ImageRecordIcon]\) if you want to see what code is used after interacting with the page.</span></span>  
1.  <span data-ttu-id="3d36e-133">选择 " **停止检测覆盖率" 并显示结果** \ (![ 停止检测覆盖率和显示结果 \ ][ImageStopIcon] ) 要停止记录代码覆盖率。</span><span class="sxs-lookup"><span data-stu-id="3d36e-133">Choose **Stop Instrumenting Coverage And Show Results** \(![Stop Instrumenting Coverage And Show Results][ImageStopIcon]\) when you want to stop recording code coverage.</span></span>  
    
## <span data-ttu-id="3d36e-134">分析代码覆盖率</span><span class="sxs-lookup"><span data-stu-id="3d36e-134">Analyze code coverage</span></span>  

<span data-ttu-id="3d36e-135">" **覆盖率** " 选项卡中的表显示分析了哪些资源，以及每个资源中使用了多少代码。</span><span class="sxs-lookup"><span data-stu-id="3d36e-135">The table in the **Coverage** tab shows you what resources were analyzed, and how much code is used within each resource.</span></span>  <span data-ttu-id="3d36e-136">单击某一行以在 " **源** " 面板中打开该资源，并查看所使用的代码和未使用的代码的逐行划分。</span><span class="sxs-lookup"><span data-stu-id="3d36e-136">Click a row to open that resource in the **Sources** panel and see a line-by-line breakdown of used code and unused code.</span></span>  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage-selected.msft.png" alt-text="分析代码覆盖率" lightbox="../media/coverage-sources-resource-drawer-coverage-selected.msft.png":::
   <span data-ttu-id="3d36e-138">"代码覆盖率" 报表</span><span class="sxs-lookup"><span data-stu-id="3d36e-138">A code coverage report</span></span>  
:::image-end:::  

*   <span data-ttu-id="3d36e-139">**Url**列是已分析资源的 url。</span><span class="sxs-lookup"><span data-stu-id="3d36e-139">The **URL** column is the URL of the resource that was analyzed.</span></span>  
*   <span data-ttu-id="3d36e-140">" **类型** " 列显示资源是否包含 CSS 和/或 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="3d36e-140">The **Type** column says whether the resource contains CSS, JavaScript, or both.</span></span>  
*   <span data-ttu-id="3d36e-141">" **字节总数** " 列是资源的总大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="3d36e-141">The **Total Bytes** column is the total size of the resource in bytes.</span></span>  
*   <span data-ttu-id="3d36e-142">" **未使用的字节** " 列表示未使用的字节数。</span><span class="sxs-lookup"><span data-stu-id="3d36e-142">The **Unused Bytes** column is the number of bytes that were not used.</span></span>  
*   <span data-ttu-id="3d36e-143">最后一个未命名的列是 " **字节总数** " 和 " **未使用的字节** " 列的可视化。</span><span class="sxs-lookup"><span data-stu-id="3d36e-143">The last, unnamed column is a visualization of the **Total Bytes** and **Unused Bytes** columns.</span></span>  <span data-ttu-id="3d36e-144">条的红色部分是未使用的字节。</span><span class="sxs-lookup"><span data-stu-id="3d36e-144">The red section of the bar is unused bytes.</span></span>  <span data-ttu-id="3d36e-145">绿色部分使用字节。</span><span class="sxs-lookup"><span data-stu-id="3d36e-145">The green section is used bytes.</span></span>  
    
## <span data-ttu-id="3d36e-146">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="3d36e-146">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageReloadIcon]: ../media/reload-icon.msft.png  
[ImageRecordIcon]: ../media/record-icon.msft.png  
[ImageStopIcon]: ../media/stop-icon.msft.png  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"  

[BootstrapButtons]: https://getbootstrap.com/docs/4.3/components/buttons "按钮-引导"  

> [!NOTE]
> <span data-ttu-id="3d36e-149">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="3d36e-149">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3d36e-150">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/coverage/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="3d36e-150">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/coverage/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="3d36e-152">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="3d36e-152">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
