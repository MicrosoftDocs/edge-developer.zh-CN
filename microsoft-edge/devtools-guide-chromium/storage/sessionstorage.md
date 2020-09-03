---
description: 如何通过会话存储窗格和控制台查看和编辑 sessionStorage。
title: 查看和编辑与 Microsoft Edge DevTools 的会话存储
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 24fca3fd3a068f3b2ffbe4ec1c23e6b80b968953
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993546"
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





# <span data-ttu-id="45641-104">查看和编辑与 Microsoft Edge DevTools 的会话存储</span><span class="sxs-lookup"><span data-stu-id="45641-104">View and edit Session Storage with Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="45641-105">本指南介绍如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 查看、编辑和删除 [`sessionStorage`][MDNSessionStorage] 键值对。</span><span class="sxs-lookup"><span data-stu-id="45641-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view, edit, and delete [`sessionStorage`][MDNSessionStorage] key-value pairs.</span></span>  

## <span data-ttu-id="45641-106">查看 sessionStorage 键和值</span><span class="sxs-lookup"><span data-stu-id="45641-106">View sessionStorage keys and values</span></span>   

1.  <span data-ttu-id="45641-107">选择 " **应用程序** " 选项卡以打开 " **应用程序** " 面板。</span><span class="sxs-lookup"><span data-stu-id="45641-107">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="45641-108">默认显示 **清单** 窗格。</span><span class="sxs-lookup"><span data-stu-id="45641-108">The **Manifest** pane is shown by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="45641-110">**清单**窗格</span><span class="sxs-lookup"><span data-stu-id="45641-110">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="45641-111">展开 " **会话存储** " 菜单。</span><span class="sxs-lookup"><span data-stu-id="45641-111">Expand the **Session Storage** menu.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage.msft.png" alt-text="会话存储菜单" lightbox="../media/storage-application-storage-session-storage.msft.png":::
       <span data-ttu-id="45641-113">**会话存储**菜单</span><span class="sxs-lookup"><span data-stu-id="45641-113">The **Session Storage** Menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="45641-114">选择一个域以查看键/值对。</span><span class="sxs-lookup"><span data-stu-id="45641-114">Select a domain to view the key-value pairs.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain.msft.png" alt-text=""SessionStorage" 键/值对" lightbox="../media/storage-application-storage-session-storage-domain.msft.png":::
       <span data-ttu-id="45641-116">`sessionStorage`键/值对</span><span class="sxs-lookup"><span data-stu-id="45641-116">The `sessionStorage` key-value pairs</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="45641-117">选择表中的一行以查看表下方的查看器中的值。</span><span class="sxs-lookup"><span data-stu-id="45641-117">Select a row of the table to view the value in the viewer below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png" alt-text="查看 x sid 键的值" lightbox="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png":::
       <span data-ttu-id="45641-119">查看键的值 `x-sid`</span><span class="sxs-lookup"><span data-stu-id="45641-119">View the value of the `x-sid` key</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="45641-120">创建新的 sessionStorage 键值对</span><span class="sxs-lookup"><span data-stu-id="45641-120">Create a new sessionStorage key-value pair</span></span>   

1.  <span data-ttu-id="45641-121">[查看 `sessionStorage` 域的键/值对](#view-sessionstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="45641-121">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="45641-122">双击表格的空白部分。</span><span class="sxs-lookup"><span data-stu-id="45641-122">Double-click the empty part of the table.</span></span>  <span data-ttu-id="45641-123">DevTools 将创建一个新行，并将光标焦点放在 **键** 列中。</span><span class="sxs-lookup"><span data-stu-id="45641-123">DevTools creates a new row and focuses your cursor in the **Key** column.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png" alt-text="要在其中创建新的键值对的表格的空部分，请双击该部分。" lightbox="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png":::
       <span data-ttu-id="45641-125">要在其中创建新的键值对的表格的空部分，请双击该部分。</span><span class="sxs-lookup"><span data-stu-id="45641-125">The empty part of the table to double-click in order to create a new key-value pair</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="45641-126">编辑 sessionStorage 键或值</span><span class="sxs-lookup"><span data-stu-id="45641-126">Edit sessionStorage keys or values</span></span>   

1.  <span data-ttu-id="45641-127">[查看 `sessionStorage` 域的键/值对](#view-sessionstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="45641-127">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="45641-128">双击 " **键** " 或 " **值** " 列中的一个单元格以编辑该注册表项或值。</span><span class="sxs-lookup"><span data-stu-id="45641-128">Double-click a cell in the **Key** or **Value** column to edit that key or value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png" alt-text="编辑 sessionStorage 键" lightbox="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png":::
       <span data-ttu-id="45641-130">编辑 `sessionStorage` 密钥</span><span class="sxs-lookup"><span data-stu-id="45641-130">Edit a `sessionStorage` key</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="45641-131">删除 sessionStorage 键值对</span><span class="sxs-lookup"><span data-stu-id="45641-131">Delete sessionStorage key-value pairs</span></span>   

1.  <span data-ttu-id="45641-132">[查看 `sessionStorage` 域的键/值对](#view-sessionstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="45641-132">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="45641-133">选择要删除的键/值对。</span><span class="sxs-lookup"><span data-stu-id="45641-133">Select the key-value pair that you want to delete.</span></span>  <span data-ttu-id="45641-134">DevTools 突出显示蓝色以指示它已选中。</span><span class="sxs-lookup"><span data-stu-id="45641-134">DevTools highlights it blue to indicate that it is selected.</span></span>  
1.  <span data-ttu-id="45641-135">按下 `Delete` 键或单击 " **删除所选** 项 \" (" ![ 删除所选项 ][ImageDeleteIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="45641-135">Press the `Delete` key or click **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).</span></span>  
    
## <span data-ttu-id="45641-136">删除域的所有 sessionStorage 键值对</span><span class="sxs-lookup"><span data-stu-id="45641-136">Delete all sessionStorage key-value pairs for a domain</span></span>   

1.  <span data-ttu-id="45641-137">[查看 `sessionStorage` 域的键/值对](#view-sessionstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="45641-137">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="45641-138">选择 **"全部清除** " (![ 全部清除 ][ImageClearIcon] \ ) 。</span><span class="sxs-lookup"><span data-stu-id="45641-138">Select **Clear All** \(![Clear All][ImageClearIcon]\).</span></span>  
    
## <span data-ttu-id="45641-139">从控制台与 sessionStorage 交互</span><span class="sxs-lookup"><span data-stu-id="45641-139">Interact with sessionStorage from the Console</span></span>   

<span data-ttu-id="45641-140">由于你可以在 **控制台**中运行 JavaScript，并且由于 **控制台** 有权访问页面的 JavaScript 上下文，因此可以 `sessionStorage` 从 **控制台**进行交互。</span><span class="sxs-lookup"><span data-stu-id="45641-140">Since you can run JavaScript in the **Console**, and since the **Console** has access to the JavaScript contexts of the page, it is possible to interact with `sessionStorage` from the **Console**.</span></span>  

1.  <span data-ttu-id="45641-141">如果你**JavaScript contexts**想要访问域的 javascript 上下文，而**Console** `sessionStorage` 不是你所在的页面之外的其他域的键值对，请使用 Javascript 上下文菜单更改该控制台的 javascript 上下文。</span><span class="sxs-lookup"><span data-stu-id="45641-141">Use the **JavaScript contexts** menu to change the JavaScript context of the **Console** if you want to access the `sessionStorage` key-value pairs of a domain other than the page you are on.</span></span>  
    
    :::image type="complex" source="../media/storage-console-domain-selection.msft.png" alt-text="更改控制台的 JavaScript 上下文" lightbox="../media/storage-console-domain-selection.msft.png":::
       <span data-ttu-id="45641-143">更改控制台的 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="45641-143">Change the JavaScript context of the Console</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="45641-144">`sessionStorage`在控制台中运行表达式，就像在 JavaScript 中一样。</span><span class="sxs-lookup"><span data-stu-id="45641-144">Run your `sessionStorage` expressions in the Console, the same as you would in your JavaScript.</span></span>  
    
    :::image type="complex" source="../media/storage-console-session-storage-keys.msft.png" alt-text="从控制台与 sessionStorage 交互" lightbox="../media/storage-console-session-storage-keys.msft.png":::
       <span data-ttu-id="45641-146">`sessionStorage`从**控制台**进行交互</span><span class="sxs-lookup"><span data-stu-id="45641-146">Interact with `sessionStorage` from the **Console**</span></span>  
    :::image-end:::  
    
<!--  
   

  
-->  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  

[MDNSessionStorage]: https://developer.mozilla.org/docs/Web/API/Window/sessionStorage "SessionStorage |MDN"  

> [!NOTE]
> <span data-ttu-id="45641-149">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="45641-149">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="45641-150">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/sessionstorage)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="45641-150">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/sessionstorage) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="45641-152">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="45641-152">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
