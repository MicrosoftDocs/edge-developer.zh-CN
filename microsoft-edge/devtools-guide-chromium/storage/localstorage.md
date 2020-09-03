---
description: 如何通过 "本地存储" 窗格和控制台查看和编辑 localStorage。
title: 查看和编辑 Microsoft Edge DevTools 的本地存储
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: aa5365d1764ea0db537ea24464f9c76441f05322
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993553"
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





# <span data-ttu-id="2d924-104">查看和编辑 Microsoft Edge DevTools 的本地存储</span><span class="sxs-lookup"><span data-stu-id="2d924-104">View and edit local storage with Microsoft Edge DevTools</span></span>   



<span data-ttu-id="2d924-105">本指南介绍如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 查看、编辑和删除 [localStorage][MDNWindowsLocalStorage] 键值对。</span><span class="sxs-lookup"><span data-stu-id="2d924-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view, edit, and delete [localStorage][MDNWindowsLocalStorage] key-value pairs.</span></span>  

## <span data-ttu-id="2d924-106">查看 localStorage 键和值</span><span class="sxs-lookup"><span data-stu-id="2d924-106">View localStorage keys and values</span></span>   

1.  <span data-ttu-id="2d924-107">选择 " **应用程序** " 选项卡以打开 " **应用程序** " 面板。</span><span class="sxs-lookup"><span data-stu-id="2d924-107">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="2d924-108">默认显示 **清单** 窗格。</span><span class="sxs-lookup"><span data-stu-id="2d924-108">The **Manifest** pane is shown by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="2d924-110">**清单**窗格</span><span class="sxs-lookup"><span data-stu-id="2d924-110">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2d924-111">展开 " **本地存储** " 菜单。</span><span class="sxs-lookup"><span data-stu-id="2d924-111">Expand the **Local Storage** menu.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage.msft.png" alt-text="本地存储菜单" lightbox="../media/storage-application-local-storage.msft.png":::
       <span data-ttu-id="2d924-113">**本地存储**菜单</span><span class="sxs-lookup"><span data-stu-id="2d924-113">The **Local Storage** menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2d924-114">选择一个域以查看键/值对。</span><span class="sxs-lookup"><span data-stu-id="2d924-114">Select a domain to view the key-value pairs.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value.msft.png" alt-text="域的 localStorage 键值对 https://www.bing.com" lightbox="../media/storage-application-local-storage-view-key-value.msft.png":::
       <span data-ttu-id="2d924-116">`localStorage`域的键/值对 `https://www.bing.com`</span><span class="sxs-lookup"><span data-stu-id="2d924-116">The `localStorage` key-value pairs for the `https://www.bing.com` domain</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2d924-117">选择表中的一行以查看表下方的查看器中的值。</span><span class="sxs-lookup"><span data-stu-id="2d924-117">Select a row of the table to view the value in the viewer below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value-selected.msft.png" alt-text="查看 eventLogQueue_Online 项的值" lightbox="../media/storage-application-local-storage-view-key-value-selected.msft.png":::
       <span data-ttu-id="2d924-119">查看键的值 `eventLogQueue_Online`</span><span class="sxs-lookup"><span data-stu-id="2d924-119">View the value of the `eventLogQueue_Online` key</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="2d924-120">创建新的 localStorage 键值对</span><span class="sxs-lookup"><span data-stu-id="2d924-120">Create a new localStorage key-value pair</span></span>   

1.  <span data-ttu-id="2d924-121">[查看 `localStorage` 域的键/值对](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="2d924-121">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="2d924-122">双击表格的空白部分。</span><span class="sxs-lookup"><span data-stu-id="2d924-122">Double-click the empty part of the table.</span></span>  <span data-ttu-id="2d924-123">DevTools 将创建一个新行，并将光标焦点放在 **键** 列中。</span><span class="sxs-lookup"><span data-stu-id="2d924-123">DevTools creates a new row and focuses your cursor in the **Key** column.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-new-key-value.msft.png" alt-text="要在其中创建新的键值对的表格的空部分，请双击该部分。" lightbox="../media/storage-application-local-storage-new-key-value.msft.png":::
       <span data-ttu-id="2d924-125">要在其中创建新的键值对的表格的空部分，请双击该部分。</span><span class="sxs-lookup"><span data-stu-id="2d924-125">The empty part of the table to double-click in order to create a new key-value pair</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="2d924-126">编辑 localStorage 键或值</span><span class="sxs-lookup"><span data-stu-id="2d924-126">Edit localStorage keys or values</span></span>   

1.  <span data-ttu-id="2d924-127">[查看 `localStorage` 域的键/值对](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="2d924-127">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="2d924-128">双击 " **键** " 或 " **值** " 列中的一个单元格以编辑该注册表项或值。</span><span class="sxs-lookup"><span data-stu-id="2d924-128">Double-click a cell in the **Key** or **Value** column to edit that key or value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-edit-key-value.msft.png" alt-text="编辑 localStorage 键" lightbox="../media/storage-application-local-storage-edit-key-value.msft.png":::
       <span data-ttu-id="2d924-130">编辑 `localStorage` 密钥</span><span class="sxs-lookup"><span data-stu-id="2d924-130">Edit a `localStorage` key</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="2d924-131">删除 localStorage 键值对</span><span class="sxs-lookup"><span data-stu-id="2d924-131">Delete localStorage key-value pairs</span></span>   

1.  <span data-ttu-id="2d924-132">[查看 `localStorage` 域的键/值对](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="2d924-132">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="2d924-133">选择要删除的键/值对。</span><span class="sxs-lookup"><span data-stu-id="2d924-133">Select the key-value pair that you want to delete.</span></span>  <span data-ttu-id="2d924-134">DevTools 突出显示蓝色以指示它已选中。</span><span class="sxs-lookup"><span data-stu-id="2d924-134">DevTools highlights it blue to indicate that it is selected.</span></span>  
1.  <span data-ttu-id="2d924-135">按下 `Delete` 键或单击 " **删除所选** 项 \" (" ![ 删除所选项 ][ImageDeleteIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="2d924-135">Press the `Delete` key or click **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).</span></span>  
    
## <span data-ttu-id="2d924-136">删除 `localStorage` 域的所有键/值对</span><span class="sxs-lookup"><span data-stu-id="2d924-136">Delete all `localStorage` key-value pairs for a domain</span></span>   

1.  <span data-ttu-id="2d924-137">[查看 `localStorage` 域的键/值对](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="2d924-137">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="2d924-138">选择 **"全部清除** " (![ 全部清除 ][ImageClearIcon] \ ) 。</span><span class="sxs-lookup"><span data-stu-id="2d924-138">Select **Clear All** \(![Clear All][ImageClearIcon]\).</span></span>  
    
## <span data-ttu-id="2d924-139">从控制台与 localStorage 交互</span><span class="sxs-lookup"><span data-stu-id="2d924-139">Interact with localStorage from the Console</span></span>   

<span data-ttu-id="2d924-140">由于您能够在 **控制台**中运行 JavaScript，并且由于 **控制台** 有权访问页面的 JavaScript 上下文，因此可以 `localStorage` 从 **控制台**进行交互。</span><span class="sxs-lookup"><span data-stu-id="2d924-140">Since you are able to run JavaScript in the **Console**, and since the **Console** has access to the JavaScript contexts of the page, it is possible to interact with `localStorage` from the **Console**.</span></span>  

1.  <span data-ttu-id="2d924-141">如果要访问显示的页面以外的域的键/值对，请使用 **JavaScript 上下文** 菜单更改 **控制台** 的 JavaScript 上下文 `localStorage` 。</span><span class="sxs-lookup"><span data-stu-id="2d924-141">Use the **JavaScript contexts** menu to change the JavaScript context of the **Console** if you want to access the `localStorage` key-value pairs of a domain other than the page that is displayed.</span></span>  
    
    :::image type="complex" source="../media/storage-console-local-storage.msft.png" alt-text="更改控制台的 JavaScript 上下文" lightbox="../media/storage-console-local-storage.msft.png":::
       <span data-ttu-id="2d924-143">更改控制台的 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="2d924-143">Change the JavaScript context of the Console</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2d924-144">`localStorage`在控制台中运行表达式，与在 JavaScript 中执行的操作相同。</span><span class="sxs-lookup"><span data-stu-id="2d924-144">Run your `localStorage` expressions in the Console, the same as you do in your JavaScript.</span></span>  
    
    :::image type="complex" source="../media/storage-console-local-storage-interaction.msft.png" alt-text="从控制台与 localStorage 交互" lightbox="../media/storage-console-local-storage-interaction.msft.png":::
       <span data-ttu-id="2d924-146">`localStorage`从**控制台**进行交互</span><span class="sxs-lookup"><span data-stu-id="2d924-146">Interact with `localStorage` from the **Console**</span></span>  
    :::image-end:::  
    
<!--  
 


-->  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  

[MDNWindowsLocalStorage]: https://developer.mozilla.org/docs/Web/API/Window/localStorage "LocalStorage |MDN"  

> [!NOTE]
> <span data-ttu-id="2d924-149">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="2d924-149">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="2d924-150">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="2d924-150">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="2d924-152">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="2d924-152">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
