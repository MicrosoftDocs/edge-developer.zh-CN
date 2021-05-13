---
description: 如何在 Microsoft Edge DevTools 中查找和分析未使用的 JavaScript 和 CSS 代码。
title: 使用 Microsoft Edge DevTools 中的“覆盖范围”面板查找未使用的 JavaScript 和 CSS 代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: b31d14feac13a907ca0c5ce7ef702bcdef375ad5
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564460"
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
# <a name="find-unused-javascript-and-css-code-with-the-coverage-panel-in-microsoft-edge-devtools"></a><span data-ttu-id="baff0-104">使用 Microsoft Edge DevTools 中的“覆盖范围”面板查找未使用的 JavaScript 和 CSS 代码</span><span class="sxs-lookup"><span data-stu-id="baff0-104">Find unused JavaScript and CSS code with the Coverage panel in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="baff0-105">Microsoft Edge DevTools 中的“**覆盖范围**”面板可帮助你查找未使用的 JavaScript 和 CSS 代码。</span><span class="sxs-lookup"><span data-stu-id="baff0-105">The **Coverage** panel in Microsoft Edge DevTools helps you find unused JavaScript and CSS code.</span></span>  <span data-ttu-id="baff0-106">删除未使用的代码可能会加快页面加载速度并保存移动用户的手机网络数据。</span><span class="sxs-lookup"><span data-stu-id="baff0-106">Removing unused code may speed up your page load and save your mobile users cellular data.</span></span>  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage.msft.png" alt-text="正在分析代码覆盖范围" lightbox="../media/coverage-sources-resource-drawer-coverage.msft.png":::
   <span data-ttu-id="baff0-108">正在分析代码覆盖范围</span><span class="sxs-lookup"><span data-stu-id="baff0-108">Analyzing code coverage</span></span>  
:::image-end:::  

> [!WARNING]
> <span data-ttu-id="baff0-109">查找未使用的代码相对容易。</span><span class="sxs-lookup"><span data-stu-id="baff0-109">Finding unused code is relatively easy.</span></span>  <span data-ttu-id="baff0-110">但重构代码库以便每个页面仅提供所需的 JavaScript 和 CSS 可能非常困难。</span><span class="sxs-lookup"><span data-stu-id="baff0-110">But refactoring a codebase so that each page only ships the JavaScript and CSS that it needs may be difficult.</span></span>  <span data-ttu-id="baff0-111">本指南未涵盖如何重构基本代码以避免未使用的代码，因为这些重构高度依赖于你的技术堆叠。</span><span class="sxs-lookup"><span data-stu-id="baff0-111">This guide does not cover how to refactor a codebase to avoid unused code because these refactors depend highly on your technology stack.</span></span>  

## <a name="overview"></a><span data-ttu-id="baff0-112">概述</span><span class="sxs-lookup"><span data-stu-id="baff0-112">Overview</span></span>  

<span data-ttu-id="baff0-113">寄送未使用的 JavaScript 或 CSS 是 web 开发中的一个常见问题。</span><span class="sxs-lookup"><span data-stu-id="baff0-113">Shipping unused JavaScript or CSS is a common problem in web development.</span></span>  <span data-ttu-id="baff0-114">例如，假设你想要在页面上使用“[Bootstrap 按钮组件][BootstrapButtons]”。</span><span class="sxs-lookup"><span data-stu-id="baff0-114">For example, suppose that you want to use [Bootstrap button component][BootstrapButtons] on your page.</span></span>  <span data-ttu-id="baff0-115">若要使用按钮组件，你需要在 HTML 中添加指向 Bootstrap 样式表的链接，如下所示：</span><span class="sxs-lookup"><span data-stu-id="baff0-115">To use the button component you need to add a link to the Bootstrap stylesheet in your HTML, like this:</span></span>  

```html
...
<head>
    ...
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    ...
</head>
...
```  

<span data-ttu-id="baff0-116">此样式表不仅包括按钮组件的代码。</span><span class="sxs-lookup"><span data-stu-id="baff0-116">This stylesheet does not just include the code for the button component.</span></span>  <span data-ttu-id="baff0-117">它包含**所有**Bootstrap 组件的 CSS。</span><span class="sxs-lookup"><span data-stu-id="baff0-117">It contains the CSS for **all** of the Bootstrap components.</span></span>  <span data-ttu-id="baff0-118">但是，你未使用任何其他 Bootstrap 组件。</span><span class="sxs-lookup"><span data-stu-id="baff0-118">But you are not using any of the other Bootstrap components.</span></span>  <span data-ttu-id="baff0-119">因此，你的页面正在下载一组不需要的 CSS。</span><span class="sxs-lookup"><span data-stu-id="baff0-119">So your page is downloading a bunch of CSS that it does not need.</span></span>  <span data-ttu-id="baff0-120">由于以下原因，此额外的 CSS 是一个问题。</span><span class="sxs-lookup"><span data-stu-id="baff0-120">This extra CSS is a problem for the following reasons.</span></span>  

*   <span data-ttu-id="baff0-121">额外的代码会降低页面加载速度。</span><span class="sxs-lookup"><span data-stu-id="baff0-121">The extra code slows down your page load.</span></span>  <!--Navigate to [Render-Blocking CSS][render].  -->  
*   <span data-ttu-id="baff0-122">如果用户在移动设备上访问页面，则额外的代码会使用其手机网络数据。</span><span class="sxs-lookup"><span data-stu-id="baff0-122">If a user accesses the page on a mobile device, the extra code uses up their cellular data.</span></span>  
    
<!--[render]: /web/fundamentals/performance/critical-rendering-path/render-blocking-css  -->  

## <a name="open-the-coverage-panel"></a><span data-ttu-id="baff0-123">打开“覆盖范围”面板</span><span class="sxs-lookup"><span data-stu-id="baff0-123">Open the Coverage panel</span></span>  

1.  <span data-ttu-id="baff0-124">[打开“命令”菜单][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="baff0-124">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="baff0-125">开始键入`coverage`，选择“**显示覆盖范围**”命令，然后选择`Enter`以运行该命令。</span><span class="sxs-lookup"><span data-stu-id="baff0-125">Start typing `coverage`, select the **Show Coverage** command, and then select `Enter` to run the command.</span></span>  <span data-ttu-id="baff0-126">在“**工具箱**”中打开“**覆盖范围**”面板。</span><span class="sxs-lookup"><span data-stu-id="baff0-126">The **Coverage** panel opens in the **Drawer**.</span></span>  

    :::image type="complex" source="../media/coverage-console-drawer-coverage-empty.msft.png" alt-text="“覆盖范围”面板" lightbox="../media/coverage-console-drawer-coverage-empty.msft.png":::
       <span data-ttu-id="baff0-128">“**覆盖范围**”面板</span><span class="sxs-lookup"><span data-stu-id="baff0-128">The **Coverage** panel</span></span>  
    :::image-end:::  
    
## <a name="record-code-coverage"></a><span data-ttu-id="baff0-129">记录代码覆盖范围</span><span class="sxs-lookup"><span data-stu-id="baff0-129">Record code coverage</span></span>  

1.  <span data-ttu-id="baff0-130">在“**覆盖范围**”面板中选择以下按钮之一。</span><span class="sxs-lookup"><span data-stu-id="baff0-130">Choose one of the following buttons in the **Coverage** panel.</span></span>  
    *   <span data-ttu-id="baff0-131">若要查看加载页面所需的代码，选择“**开始检测覆盖范围并重新加载页面**” \(“![开始检测覆盖范围并重新加载页面](../media/reload-icon.msft.png)”\)。</span><span class="sxs-lookup"><span data-stu-id="baff0-131">Choose **Start Instrumenting Coverage And Reload Page** \(![Start Instrumenting Coverage And Reload Page](../media/reload-icon.msft.png)\) if you want to review what code is needed to load the page.</span></span>  
    *   <span data-ttu-id="baff0-132">若要查看与页面交互后使用的代码，选择“**检测覆盖范围**” \(“![检测覆盖范围](../media/record-icon.msft.png)”\)。</span><span class="sxs-lookup"><span data-stu-id="baff0-132">Choose **Instrument Coverage** \(![Instrument Coverage](../media/record-icon.msft.png)\) if you want to review what code is used after interacting with the page.</span></span>  
1.  <span data-ttu-id="baff0-133">若要停止记录代码覆盖范围，选择“**停止检测覆盖范围并显示结果**” \(“![停止检测覆盖范围并显示结果](../media/stop-icon.msft.png)”\)。</span><span class="sxs-lookup"><span data-stu-id="baff0-133">Choose **Stop Instrumenting Coverage And Show Results** \(![Stop Instrumenting Coverage And Show Results](../media/stop-icon.msft.png)\) when you want to stop recording code coverage.</span></span>  
    
## <a name="analyze-code-coverage"></a><span data-ttu-id="baff0-134">分析代码覆盖范围</span><span class="sxs-lookup"><span data-stu-id="baff0-134">Analyze code coverage</span></span>  

<span data-ttu-id="baff0-135">“**覆盖范围**”面板中的表显示已分析的资源，以及每个资源中使用的代码数。</span><span class="sxs-lookup"><span data-stu-id="baff0-135">The table in the **Coverage** panel displays the resources that were analyzed, and how much code is used within each resource.</span></span>  <span data-ttu-id="baff0-136">选择一行以在"源"工具\*\*\*\* 中打开该资源，并查看已用代码和未使用代码的行细分。</span><span class="sxs-lookup"><span data-stu-id="baff0-136">Choose a row to open that resource in the **Sources** tool and review a line-by-line breakdown of used code and unused code.</span></span>  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage-selected.msft.png" alt-text="代码覆盖范围报告" lightbox="../media/coverage-sources-resource-drawer-coverage-selected.msft.png":::
   <span data-ttu-id="baff0-138">代码覆盖范围报告</span><span class="sxs-lookup"><span data-stu-id="baff0-138">A code coverage report</span></span>  
:::image-end:::  

*   <span data-ttu-id="baff0-139">“**URL**”列是已分析资源的 URL。</span><span class="sxs-lookup"><span data-stu-id="baff0-139">The **URL** column is the URL of the resource that was analyzed.</span></span>  
*   <span data-ttu-id="baff0-140">“**类型**”列显示资源是否包含 CSS、JavaScript 还是同时包含两者。</span><span class="sxs-lookup"><span data-stu-id="baff0-140">The **Type** column says whether the resource contains CSS, JavaScript, or both.</span></span>  
*   <span data-ttu-id="baff0-141">“**字节总数**”列是资源的总大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="baff0-141">The **Total Bytes** column is the total size of the resource in bytes.</span></span>  
*   <span data-ttu-id="baff0-142">“**未使用字节数**”列是没有使用的字节数。</span><span class="sxs-lookup"><span data-stu-id="baff0-142">The **Unused Bytes** column is the number of bytes that were not used.</span></span>  
*   <span data-ttu-id="baff0-143">最后一个未命名列是“**总字节数**”和“**未使用字节数**”列的可视化效果。</span><span class="sxs-lookup"><span data-stu-id="baff0-143">The last, unnamed column is a visualization of the **Total Bytes** and **Unused Bytes** columns.</span></span>  <span data-ttu-id="baff0-144">条形图的红色部分是未使用字节数。</span><span class="sxs-lookup"><span data-stu-id="baff0-144">The red section of the bar is unused bytes.</span></span>  <span data-ttu-id="baff0-145">绿色部分是已使用字节数。</span><span class="sxs-lookup"><span data-stu-id="baff0-145">The green section is used bytes.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="baff0-146">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="baff0-146">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行命令| Microsoft Docs"  

[BootstrapButtons]: https://getbootstrap.com/docs/4.3/components/buttons "按钮 - Bootstrap"  

> [!NOTE]
> <span data-ttu-id="baff0-149">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="baff0-149">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="baff0-150">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/coverage/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="baff0-150">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/coverage/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="baff0-152">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="baff0-152">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
