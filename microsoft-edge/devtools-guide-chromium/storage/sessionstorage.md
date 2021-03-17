---
description: 如何使用会话存储窗格和控制台查看和编辑 sessionStorage。
title: 使用 Microsoft Edge DevTools 查看和编辑会话存储
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 0168b01fd01071ebd19bd211c6d947ae006d778c
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439659"
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

# <a name="view-and-edit-session-storage-with-microsoft-edge-devtools"></a><span data-ttu-id="0da39-104">使用 Microsoft Edge DevTools 查看和编辑会话存储</span><span class="sxs-lookup"><span data-stu-id="0da39-104">View and edit Session Storage with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="0da39-105">本指南演示如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 查看、编辑和删除 [sessionStorage][MDNSessionStorage] 键值对。</span><span class="sxs-lookup"><span data-stu-id="0da39-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view, edit, and delete [sessionStorage][MDNSessionStorage] key-value pairs.</span></span>  

## <a name="view-sessionstorage-keys-and-values"></a><span data-ttu-id="0da39-106">查看 sessionStorage 键和值</span><span class="sxs-lookup"><span data-stu-id="0da39-106">View sessionStorage keys and values</span></span>  

1.  <span data-ttu-id="0da39-107">选择" **应用程序"** 选项卡以打开 **"应用程序"** 工具。</span><span class="sxs-lookup"><span data-stu-id="0da39-107">Choose the **Application** tab to open the **Application** tool.</span></span>  <span data-ttu-id="0da39-108">默认情况下 **显示** 清单面板。</span><span class="sxs-lookup"><span data-stu-id="0da39-108">The **Manifest** panel is shown by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="0da39-110">清单**窗格**</span><span class="sxs-lookup"><span data-stu-id="0da39-110">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0da39-111">展开" **会话存储"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="0da39-111">Expand the **Session Storage** menu.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage.msft.png" alt-text="会话存储菜单" lightbox="../media/storage-application-storage-session-storage.msft.png":::
       <span data-ttu-id="0da39-113">会话 **存储** 菜单</span><span class="sxs-lookup"><span data-stu-id="0da39-113">The **Session Storage** Menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0da39-114">选择一个域以查看键值对。</span><span class="sxs-lookup"><span data-stu-id="0da39-114">Choose a domain to view the key-value pairs.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain.msft.png" alt-text="sessionStorage 键值对" lightbox="../media/storage-application-storage-session-storage-domain.msft.png":::
       <span data-ttu-id="0da39-116">`sessionStorage`键值对</span><span class="sxs-lookup"><span data-stu-id="0da39-116">The `sessionStorage` key-value pairs</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0da39-117">选择表格的一行以查看表格下方的查看器中的值。</span><span class="sxs-lookup"><span data-stu-id="0da39-117">Choose a row of the table to view the value in the viewer below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png" alt-text="查看 x-sid 键的值" lightbox="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png":::
       <span data-ttu-id="0da39-119">查看键 `x-sid` 的值</span><span class="sxs-lookup"><span data-stu-id="0da39-119">View the value of the `x-sid` key</span></span>  
    :::image-end:::  
    
## <a name="create-a-new-sessionstorage-key-value-pair"></a><span data-ttu-id="0da39-120">创建新的 sessionStorage 键值对</span><span class="sxs-lookup"><span data-stu-id="0da39-120">Create a new sessionStorage key-value pair</span></span>  

1.  <span data-ttu-id="0da39-121">[查看域的 sessionStorage 键值对](#view-sessionstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="0da39-121">[View the sessionStorage key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="0da39-122">双击表格的空部分。</span><span class="sxs-lookup"><span data-stu-id="0da39-122">Double-click the empty part of the table.</span></span>  <span data-ttu-id="0da39-123">DevTools 创建一个新行，并焦点在键列中 **的** 光标。</span><span class="sxs-lookup"><span data-stu-id="0da39-123">DevTools creates a new row and focuses your cursor in the **Key** column.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png" alt-text="要双击以创建新的键值对的表的空部分" lightbox="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png":::
       <span data-ttu-id="0da39-125">要双击以创建新的键值对的表的空部分</span><span class="sxs-lookup"><span data-stu-id="0da39-125">The empty part of the table to double-click in order to create a new key-value pair</span></span>  
    :::image-end:::  
    
## <a name="edit-sessionstorage-keys-or-values"></a><span data-ttu-id="0da39-126">编辑 sessionStorage 键或值</span><span class="sxs-lookup"><span data-stu-id="0da39-126">Edit sessionStorage keys or values</span></span>  

1.  <span data-ttu-id="0da39-127">[查看域的 sessionStorage 键值对](#view-sessionstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="0da39-127">[View the sessionStorage key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="0da39-128">双击"键"或"值\*\*\*\*"**列中的单元格**以编辑该键或值。</span><span class="sxs-lookup"><span data-stu-id="0da39-128">Double-click a cell in the **Key** or **Value** column to edit that key or value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png" alt-text="编辑 sessionStorage 键" lightbox="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png":::
       <span data-ttu-id="0da39-130">编辑 `sessionStorage` 密钥</span><span class="sxs-lookup"><span data-stu-id="0da39-130">Edit a `sessionStorage` key</span></span>  
    :::image-end:::  
    
## <a name="delete-sessionstorage-key-value-pairs"></a><span data-ttu-id="0da39-131">删除 sessionStorage 键值对</span><span class="sxs-lookup"><span data-stu-id="0da39-131">Delete sessionStorage key-value pairs</span></span>  

1.  <span data-ttu-id="0da39-132">[查看 `sessionStorage` 域的键值对](#view-sessionstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="0da39-132">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="0da39-133">选择要删除的键值对。</span><span class="sxs-lookup"><span data-stu-id="0da39-133">Choose the key-value pair that you want to delete.</span></span>  <span data-ttu-id="0da39-134">DevTools 突出显示蓝色以指示已选中。</span><span class="sxs-lookup"><span data-stu-id="0da39-134">DevTools highlights it blue to indicate that it is selected.</span></span>  
1.  <span data-ttu-id="0da39-135">选择该 `Delete` 键或选择\*\*\*\*"删除所选 \ (![ 删除所选 ](../media/delete-icon.msft.png) \) "。</span><span class="sxs-lookup"><span data-stu-id="0da39-135">Select the `Delete` key or choose **Delete Selected** \(![Delete Selected](../media/delete-icon.msft.png)\).</span></span>  
    
## <a name="delete-all-sessionstorage-key-value-pairs-for-a-domain"></a><span data-ttu-id="0da39-136">删除域的所有 sessionStorage 键值对</span><span class="sxs-lookup"><span data-stu-id="0da39-136">Delete all sessionStorage key-value pairs for a domain</span></span>  

1.  <span data-ttu-id="0da39-137">[查看 `sessionStorage` 域的键值对](#view-sessionstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="0da39-137">[View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="0da39-138">Choose **Clear All** \ (Clear All ![ ](../media/clear-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="0da39-138">Choose **Clear All** \(![Clear All](../media/clear-icon.msft.png)\).</span></span>  
    
## <a name="interact-with-sessionstorage-from-the-console"></a><span data-ttu-id="0da39-139">从控制台与 sessionStorage 交互</span><span class="sxs-lookup"><span data-stu-id="0da39-139">Interact with sessionStorage from the Console</span></span>  

<span data-ttu-id="0da39-140">由于你可能在控制台中运行 JavaScript，并且由于**控制台**可以访问页面的 JavaScript 上下文，因此可以与控制台\*\*\*\* `sessionStorage` **进行交互**。</span><span class="sxs-lookup"><span data-stu-id="0da39-140">Since you may run JavaScript in the **Console**, and since the **Console** has access to the JavaScript contexts of the page, it is possible to interact with `sessionStorage` from the **Console**.</span></span>  

1.  <span data-ttu-id="0da39-141">如果要访问除你位于的页面外的其他域的键值对，\*\*\*\* 请使用**JavaScript**上下文菜单更改控制台的 JavaScript `sessionStorage` 上下文。</span><span class="sxs-lookup"><span data-stu-id="0da39-141">Use the **JavaScript contexts** menu to change the JavaScript context of the **Console** if you want to access the `sessionStorage` key-value pairs of a domain other than the page you are on.</span></span>  
    
    :::image type="complex" source="../media/storage-console-domain-selection.msft.png" alt-text="更改控制台的 JavaScript 上下文" lightbox="../media/storage-console-domain-selection.msft.png":::
       <span data-ttu-id="0da39-143">更改控制台的 JavaScript **上下文**</span><span class="sxs-lookup"><span data-stu-id="0da39-143">Change the JavaScript context of the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0da39-144">在控制台 `sessionStorage` 中 **运行表达式**，与 JavaScript 相同。</span><span class="sxs-lookup"><span data-stu-id="0da39-144">Run your `sessionStorage` expressions in the **Console**, the same as your JavaScript.</span></span>  
    
    :::image type="complex" source="../media/storage-console-session-storage-keys.msft.png" alt-text="从控制台与 sessionStorage 交互" lightbox="../media/storage-console-session-storage-keys.msft.png":::
       <span data-ttu-id="0da39-146">从控制台 `sessionStorage` **进行交互**</span><span class="sxs-lookup"><span data-stu-id="0da39-146">Interact with `sessionStorage` from the **Console**</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="0da39-147">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="0da39-147">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具|Microsoft Docs"  

[MDNSessionStorage]: https://developer.mozilla.org/docs/Web/API/Window/sessionStorage "Window.sessionStorage |MDN"  

> [!NOTE]
> <span data-ttu-id="0da39-150">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="0da39-150">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0da39-151">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/sessionstorage)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="0da39-151">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/sessionstorage) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="0da39-153">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="0da39-153">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
