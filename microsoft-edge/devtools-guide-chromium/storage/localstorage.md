---
description: 如何使用“本地存储”窗格和控制台查看和编辑 localStorage。
title: 使用 Microsoft Edge DevTools 查看和编辑本地存储
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge，web 开发，f12 工具，devtools
ms.openlocfilehash: 4eebf3108e7b1c6ecaecbfed445e8f3fe26215c4
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
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

# <a name="view-and-edit-local-storage-with-microsoft-edge-devtools"></a><span data-ttu-id="f13e8-104">使用 Microsoft Edge DevTools 查看和编辑本地存储</span><span class="sxs-lookup"><span data-stu-id="f13e8-104">View and edit local storage with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="f13e8-105">本指南演示如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 查看、编辑和删除 [localStorage][MDNWindowsLocalStorage] 键值对。</span><span class="sxs-lookup"><span data-stu-id="f13e8-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view, edit, and delete [localStorage][MDNWindowsLocalStorage] key-value pairs.</span></span>  

## <a name="view-localstorage-keys-and-values"></a><span data-ttu-id="f13e8-106">查看 localStorage 键和值</span><span class="sxs-lookup"><span data-stu-id="f13e8-106">View localStorage keys and values</span></span>  

1.  <span data-ttu-id="f13e8-107">选择“**应用程序**”选项卡以打开“**应用程序**”工具。</span><span class="sxs-lookup"><span data-stu-id="f13e8-107">Choose the **Application** tab to open the **Application** tool.</span></span>  <span data-ttu-id="f13e8-108">“**清单**”窗格默认显示。</span><span class="sxs-lookup"><span data-stu-id="f13e8-108">The **Manifest** pane is shown by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="“清单”窗格" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="f13e8-110">“**清单**”窗格</span><span class="sxs-lookup"><span data-stu-id="f13e8-110">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f13e8-111">展开“**本地存储**”菜单。</span><span class="sxs-lookup"><span data-stu-id="f13e8-111">Expand the **Local Storage** menu.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage.msft.png" alt-text="“本地存储”菜单" lightbox="../media/storage-application-local-storage.msft.png":::
       <span data-ttu-id="f13e8-113">“**本地存储**”菜单</span><span class="sxs-lookup"><span data-stu-id="f13e8-113">The **Local Storage** menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f13e8-114">选择域以查看键值对。</span><span class="sxs-lookup"><span data-stu-id="f13e8-114">Choose a domain to view the key-value pairs.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value.msft.png" alt-text="https://www.bing.com域的 localStorage 键值对" lightbox="../media/storage-application-local-storage-view-key-value.msft.png":::
       <span data-ttu-id="f13e8-116">`https://www.bing.com`域的`localStorage`键值对</span><span class="sxs-lookup"><span data-stu-id="f13e8-116">The `localStorage` key-value pairs for the `https://www.bing.com` domain</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f13e8-117">选择表的行以查看该表下方查看器中的值。</span><span class="sxs-lookup"><span data-stu-id="f13e8-117">Choose a row of the table to view the value in the viewer below the table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value-selected.msft.png" alt-text="查看 eventLogQueue_Online 键的值" lightbox="../media/storage-application-local-storage-view-key-value-selected.msft.png":::
       <span data-ttu-id="f13e8-119">查看`eventLogQueue_Online`键的值</span><span class="sxs-lookup"><span data-stu-id="f13e8-119">View the value of the `eventLogQueue_Online` key</span></span>  
    :::image-end:::  
    
## <a name="create-a-new-localstorage-key-value-pair"></a><span data-ttu-id="f13e8-120">创建新的 localStorage 键值对</span><span class="sxs-lookup"><span data-stu-id="f13e8-120">Create a new localStorage key-value pair</span></span>  

1.  <span data-ttu-id="f13e8-121">[查看域的 localStorage 键值对](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="f13e8-121">[View the localStorage key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="f13e8-122">双击表的空白部分。</span><span class="sxs-lookup"><span data-stu-id="f13e8-122">Double-click the empty part of the table.</span></span>  <span data-ttu-id="f13e8-123">DevTools 创建新行，并将光标停留在**键**列。</span><span class="sxs-lookup"><span data-stu-id="f13e8-123">DevTools creates a new row and focuses your cursor in the **Key** column.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-new-key-value.msft.png" alt-text="双击表的空白部分以创建新键值对" lightbox="../media/storage-application-local-storage-new-key-value.msft.png":::
       <span data-ttu-id="f13e8-125">双击表的空白部分以创建新键值对</span><span class="sxs-lookup"><span data-stu-id="f13e8-125">The empty part of the table to double-click in order to create a new key-value pair</span></span>  
    :::image-end:::  
    
## <a name="edit-localstorage-keys-or-values"></a><span data-ttu-id="f13e8-126">编辑 localStorage 键或值</span><span class="sxs-lookup"><span data-stu-id="f13e8-126">Edit localStorage keys or values</span></span>  

1.  <span data-ttu-id="f13e8-127">[查看域的 localStorage 键值对](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="f13e8-127">[View the localStorage key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="f13e8-128">双击“**键**”或“**值**”列中的单元格以编辑该键或值。</span><span class="sxs-lookup"><span data-stu-id="f13e8-128">Double-click a cell in the **Key** or **Value** column to edit that key or value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-local-storage-edit-key-value.msft.png" alt-text="编辑 localStorage 键" lightbox="../media/storage-application-local-storage-edit-key-value.msft.png":::
       <span data-ttu-id="f13e8-130">编辑`localStorage`键</span><span class="sxs-lookup"><span data-stu-id="f13e8-130">Edit a `localStorage` key</span></span>  
    :::image-end:::  
    
## <a name="delete-localstorage-key-value-pairs"></a><span data-ttu-id="f13e8-131">删除 localStorage 键值对</span><span class="sxs-lookup"><span data-stu-id="f13e8-131">Delete localStorage key-value pairs</span></span>  

1.  <span data-ttu-id="f13e8-132">[查看域的`localStorage`键值对](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="f13e8-132">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="f13e8-133">选择要删除的键值对。</span><span class="sxs-lookup"><span data-stu-id="f13e8-133">Choose the key-value pair that you want to delete.</span></span>  <span data-ttu-id="f13e8-134">DevTools 突出显示蓝色以指示已选中。</span><span class="sxs-lookup"><span data-stu-id="f13e8-134">DevTools highlights it blue to indicate that it is selected.</span></span>  
1.  <span data-ttu-id="f13e8-135">选择`Delete`键或选择“**删除所选**”\(“![删除所选](../media/delete-icon.msft.png)”\)。</span><span class="sxs-lookup"><span data-stu-id="f13e8-135">Select the `Delete` key or choose **Delete Selected** \(![Delete Selected](../media/delete-icon.msft.png)\).</span></span>  
    
## <a name="delete-all-localstorage-key-value-pairs-for-a-domain"></a><span data-ttu-id="f13e8-136">删除域的所有`localStorage`键值对</span><span class="sxs-lookup"><span data-stu-id="f13e8-136">Delete all `localStorage` key-value pairs for a domain</span></span>  

1.  <span data-ttu-id="f13e8-137">[查看域的`localStorage`键值对](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="f13e8-137">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="f13e8-138">选择“**全部清除**”\(“![全部清除](../media/clear-icon.msft.png)”\)。</span><span class="sxs-lookup"><span data-stu-id="f13e8-138">Choose **Clear All** \(![Clear All](../media/clear-icon.msft.png)\).</span></span>  
    
## <a name="interact-with-localstorage-from-the-console"></a><span data-ttu-id="f13e8-139">通过控制台与 localStorage 交互</span><span class="sxs-lookup"><span data-stu-id="f13e8-139">Interact with localStorage from the Console</span></span>  

<span data-ttu-id="f13e8-140">由于可以在**控制台**中运行 JavaScript，并且由于**控制台**可以访问页面的 JavaScript 上下文，因此可以通过**控制台**与`localStorage`交互。</span><span class="sxs-lookup"><span data-stu-id="f13e8-140">Since you are able to run JavaScript in the **Console**, and since the **Console** has access to the JavaScript contexts of the page, it is possible to interact with `localStorage` from the **Console**.</span></span>  

1.  <span data-ttu-id="f13e8-141">如果要访问除了显示页面以外域的`localStorage`键值对，使用“**JavaScript 上下文**”菜单更改**控制台**的 JavaScript 上下文。</span><span class="sxs-lookup"><span data-stu-id="f13e8-141">Use the **JavaScript contexts** menu to change the JavaScript context of the **Console** if you want to access the `localStorage` key-value pairs of a domain other than the page that is displayed.</span></span>  
    
    :::image type="complex" source="../media/storage-console-local-storage.msft.png" alt-text="更改控制台的 JavaScript 上下文" lightbox="../media/storage-console-local-storage.msft.png":::
       <span data-ttu-id="f13e8-143">更改控制台的 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="f13e8-143">Change the JavaScript context of the Console</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f13e8-144">在控制台中运行`localStorage`表达式，与在 JavaScript 中一样。</span><span class="sxs-lookup"><span data-stu-id="f13e8-144">Run your `localStorage` expressions in the Console, the same as you do in your JavaScript.</span></span>  
    
    :::image type="complex" source="../media/storage-console-local-storage-interaction.msft.png" alt-text="通过控制台与 localStorage 交互" lightbox="../media/storage-console-local-storage-interaction.msft.png":::
       <span data-ttu-id="f13e8-146">通过**控制台**与`localStorage`交互</span><span class="sxs-lookup"><span data-stu-id="f13e8-146">Interact with `localStorage` from the **Console**</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="f13e8-147">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="f13e8-147">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具| Microsoft Docs"  

[MDNWindowsLocalStorage]: https://developer.mozilla.org/docs/Web/API/Window/localStorage "Window.localStorage | MDN"  

> [!NOTE]
> <span data-ttu-id="f13e8-150">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f13e8-150">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f13e8-151">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="f13e8-151">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f13e8-153">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f13e8-153">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
