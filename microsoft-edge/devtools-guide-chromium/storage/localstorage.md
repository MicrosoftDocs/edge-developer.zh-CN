---
description: 如何使用"本地存储"窗格和控制台查看和编辑 localStorage。
title: 使用 Microsoft Edge DevTools 查看和编辑本地存储
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 4eebf3108e7b1c6ecaecbfed445e8f3fe26215c4
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439673"
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

# <a name="view-and-edit-local-storage-with-microsoft-edge-devtools"></a><span data-ttu-id="bf97e-104">使用 Microsoft Edge DevTools 查看和编辑本地存储</span><span class="sxs-lookup"><span data-stu-id="bf97e-104">View and edit local storage with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="bf97e-105">本指南演示如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 查看、编辑和删除 [localStorage][MDNWindowsLocalStorage] 键值对。</span><span class="sxs-lookup"><span data-stu-id="bf97e-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view, edit, and delete [localStorage][MDNWindowsLocalStorage] key-value pairs.</span></span>  

## <a name="view-localstorage-keys-and-values"></a><span data-ttu-id="bf97e-106">查看 localStorage 键和值</span><span class="sxs-lookup"><span data-stu-id="bf97e-106">View localStorage keys and values</span></span>  

1.  <span data-ttu-id="bf97e-107">选择" **应用程序"** 选项卡以打开 **"应用程序"** 工具。</span><span class="sxs-lookup"><span data-stu-id="bf97e-107">Choose the **Application** tab to open the **Application** tool.</span></span>  <span data-ttu-id="bf97e-108">" **清单** "窗格默认显示。</span><span class="sxs-lookup"><span data-stu-id="bf97e-108">The **Manifest** pane is shown by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="bf97e-110">清单**窗格**</span><span class="sxs-lookup"><span data-stu-id="bf97e-110">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="bf97e-111">展开" **本地存储"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="bf97e-111">Expand the **Local Storage** menu.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage.msft.png" alt-text=""本地存储"菜单" lightbox="../media/storage-application-local-storage.msft.png":::
       <span data-ttu-id="bf97e-113">" **本地存储"** 菜单</span><span class="sxs-lookup"><span data-stu-id="bf97e-113">The **Local Storage** menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="bf97e-114">选择一个域以查看键值对。</span><span class="sxs-lookup"><span data-stu-id="bf97e-114">Choose a domain to view the key-value pairs.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value.msft.png" alt-text="域的 localStorage 键值 https://www.bing.com 对" lightbox="../media/storage-application-local-storage-view-key-value.msft.png":::
       <span data-ttu-id="bf97e-116">`localStorage`域的键值 `https://www.bing.com` 对</span><span class="sxs-lookup"><span data-stu-id="bf97e-116">The `localStorage` key-value pairs for the `https://www.bing.com` domain</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="bf97e-117">选择表格的一行以查看表格下方的查看器中的值。</span><span class="sxs-lookup"><span data-stu-id="bf97e-117">Choose a row of the table to view the value in the viewer below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value-selected.msft.png" alt-text="查看键eventLogQueue_Online值" lightbox="../media/storage-application-local-storage-view-key-value-selected.msft.png":::
       <span data-ttu-id="bf97e-119">查看键 `eventLogQueue_Online` 的值</span><span class="sxs-lookup"><span data-stu-id="bf97e-119">View the value of the `eventLogQueue_Online` key</span></span>  
    :::image-end:::  
    
## <a name="create-a-new-localstorage-key-value-pair"></a><span data-ttu-id="bf97e-120">创建新的 localStorage 键值对</span><span class="sxs-lookup"><span data-stu-id="bf97e-120">Create a new localStorage key-value pair</span></span>  

1.  <span data-ttu-id="bf97e-121">[查看域的 localStorage 键值对](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="bf97e-121">[View the localStorage key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="bf97e-122">双击表格的空部分。</span><span class="sxs-lookup"><span data-stu-id="bf97e-122">Double-click the empty part of the table.</span></span>  <span data-ttu-id="bf97e-123">DevTools 创建一个新行，并焦点在键列中 **的** 光标。</span><span class="sxs-lookup"><span data-stu-id="bf97e-123">DevTools creates a new row and focuses your cursor in the **Key** column.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-new-key-value.msft.png" alt-text="要双击以创建新的键值对的表的空部分" lightbox="../media/storage-application-local-storage-new-key-value.msft.png":::
       <span data-ttu-id="bf97e-125">要双击以创建新的键值对的表的空部分</span><span class="sxs-lookup"><span data-stu-id="bf97e-125">The empty part of the table to double-click in order to create a new key-value pair</span></span>  
    :::image-end:::  
    
## <a name="edit-localstorage-keys-or-values"></a><span data-ttu-id="bf97e-126">编辑 localStorage 键或值</span><span class="sxs-lookup"><span data-stu-id="bf97e-126">Edit localStorage keys or values</span></span>  

1.  <span data-ttu-id="bf97e-127">[查看域的 localStorage 键值对](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="bf97e-127">[View the localStorage key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="bf97e-128">双击"键"或"值\*\*\*\*"**列中的单元格**以编辑该键或值。</span><span class="sxs-lookup"><span data-stu-id="bf97e-128">Double-click a cell in the **Key** or **Value** column to edit that key or value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-edit-key-value.msft.png" alt-text="编辑 localStorage 项" lightbox="../media/storage-application-local-storage-edit-key-value.msft.png":::
       <span data-ttu-id="bf97e-130">编辑 `localStorage` 密钥</span><span class="sxs-lookup"><span data-stu-id="bf97e-130">Edit a `localStorage` key</span></span>  
    :::image-end:::  
    
## <a name="delete-localstorage-key-value-pairs"></a><span data-ttu-id="bf97e-131">删除 localStorage 键值对</span><span class="sxs-lookup"><span data-stu-id="bf97e-131">Delete localStorage key-value pairs</span></span>  

1.  <span data-ttu-id="bf97e-132">[查看 `localStorage` 域的键值对](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="bf97e-132">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="bf97e-133">选择要删除的键值对。</span><span class="sxs-lookup"><span data-stu-id="bf97e-133">Choose the key-value pair that you want to delete.</span></span>  <span data-ttu-id="bf97e-134">DevTools 突出显示蓝色以指示已选中。</span><span class="sxs-lookup"><span data-stu-id="bf97e-134">DevTools highlights it blue to indicate that it is selected.</span></span>  
1.  <span data-ttu-id="bf97e-135">选择该 `Delete` 键或选择\*\*\*\*"删除所选 \ (![ 删除所选 ](../media/delete-icon.msft.png) \) "。</span><span class="sxs-lookup"><span data-stu-id="bf97e-135">Select the `Delete` key or choose **Delete Selected** \(![Delete Selected](../media/delete-icon.msft.png)\).</span></span>  
    
## <a name="delete-all-localstorage-key-value-pairs-for-a-domain"></a><span data-ttu-id="bf97e-136">删除 `localStorage` 域的所有键值对</span><span class="sxs-lookup"><span data-stu-id="bf97e-136">Delete all `localStorage` key-value pairs for a domain</span></span>  

1.  <span data-ttu-id="bf97e-137">[查看 `localStorage` 域的键值对](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="bf97e-137">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="bf97e-138">Choose **Clear All** \ (Clear All ![ ](../media/clear-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="bf97e-138">Choose **Clear All** \(![Clear All](../media/clear-icon.msft.png)\).</span></span>  
    
## <a name="interact-with-localstorage-from-the-console"></a><span data-ttu-id="bf97e-139">从控制台与 localStorage 交互</span><span class="sxs-lookup"><span data-stu-id="bf97e-139">Interact with localStorage from the Console</span></span>  

<span data-ttu-id="bf97e-140">由于可以在控制台中运行 JavaScript，并且\*\*\*\* 由于**控制台**可以访问页面的 JavaScript 上下文，因此可以与控制台 `localStorage` **进行交互**。</span><span class="sxs-lookup"><span data-stu-id="bf97e-140">Since you are able to run JavaScript in the **Console**, and since the **Console** has access to the JavaScript contexts of the page, it is possible to interact with `localStorage` from the **Console**.</span></span>  

1.  <span data-ttu-id="bf97e-141">如果要访问显示的页外域的键值对，请使用**JavaScript**上下文菜单更改控制台的 JavaScript\*\*\*\* `localStorage` 上下文。</span><span class="sxs-lookup"><span data-stu-id="bf97e-141">Use the **JavaScript contexts** menu to change the JavaScript context of the **Console** if you want to access the `localStorage` key-value pairs of a domain other than the page that is displayed.</span></span>  
    
    :::image type="complex" source="../media/storage-console-local-storage.msft.png" alt-text="更改控制台的 JavaScript 上下文" lightbox="../media/storage-console-local-storage.msft.png":::
       <span data-ttu-id="bf97e-143">更改控制台的 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="bf97e-143">Change the JavaScript context of the Console</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="bf97e-144">在 `localStorage` 控制台中运行表达式，与在 JavaScript 中一样。</span><span class="sxs-lookup"><span data-stu-id="bf97e-144">Run your `localStorage` expressions in the Console, the same as you do in your JavaScript.</span></span>  
    
    :::image type="complex" source="../media/storage-console-local-storage-interaction.msft.png" alt-text="从控制台与 localStorage 交互" lightbox="../media/storage-console-local-storage-interaction.msft.png":::
       <span data-ttu-id="bf97e-146">从控制台 `localStorage` **进行交互**</span><span class="sxs-lookup"><span data-stu-id="bf97e-146">Interact with `localStorage` from the **Console**</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="bf97e-147">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="bf97e-147">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具|Microsoft Docs"  

[MDNWindowsLocalStorage]: https://developer.mozilla.org/docs/Web/API/Window/localStorage "Window.localStorage |MDN"  

> [!NOTE]
> <span data-ttu-id="bf97e-150">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="bf97e-150">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="bf97e-151">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="bf97e-151">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="bf97e-153">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="bf97e-153">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
