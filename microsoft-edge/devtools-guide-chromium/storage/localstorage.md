---
title: 查看和编辑 Microsoft Edge DevTools 的本地存储
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: f7e187662aec8231f2cc4e99baab1b4b8e2048ad
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612009"
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





# <span data-ttu-id="21deb-103">查看和编辑 Microsoft Edge DevTools 的本地存储</span><span class="sxs-lookup"><span data-stu-id="21deb-103">View And Edit Local Storage With Microsoft Edge DevTools</span></span>   



<span data-ttu-id="21deb-104">本指南介绍如何使用[Microsoft Edge DevTools][MicrosoftEdgeDevTools]查看、编辑和删除 [`localStorage`][MDNWindowsLocalStorage] 键值对。</span><span class="sxs-lookup"><span data-stu-id="21deb-104">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view, edit, and delete [`localStorage`][MDNWindowsLocalStorage] key-value pairs.</span></span>  

## <span data-ttu-id="21deb-105">查看 localStorage 键和值</span><span class="sxs-lookup"><span data-stu-id="21deb-105">View localStorage keys and values</span></span>   

1.  <span data-ttu-id="21deb-106">选择 "**应用程序**" 选项卡以打开 "**应用程序**" 面板。</span><span class="sxs-lookup"><span data-stu-id="21deb-106">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="21deb-107">默认显示**清单**窗格。</span><span class="sxs-lookup"><span data-stu-id="21deb-107">The **Manifest** pane is shown by default.</span></span>  
    
    > ##### <span data-ttu-id="21deb-108">图 1</span><span class="sxs-lookup"><span data-stu-id="21deb-108">Figure 1</span></span>  
    > <span data-ttu-id="21deb-109">清单窗格</span><span class="sxs-lookup"><span data-stu-id="21deb-109">The Manifest pane</span></span>  
    > ![清单窗格][ImageManifest]  

1.  <span data-ttu-id="21deb-111">展开 "**本地存储**" 菜单。</span><span class="sxs-lookup"><span data-stu-id="21deb-111">Expand the **Local Storage** menu.</span></span>  
    
    > ##### <span data-ttu-id="21deb-112">图 2</span><span class="sxs-lookup"><span data-stu-id="21deb-112">Figure 2</span></span>  
    > <span data-ttu-id="21deb-113">"**本地存储**" 菜单显示两个域： `https://business.bing.com` 和</span><span class="sxs-lookup"><span data-stu-id="21deb-113">The **Local Storage** menu shows two domains: `https://business.bing.com` and</span></span> `https://www.bing.com`  
    > ![本地存储菜单][ImageLocalStorageMenu]  

1.  <span data-ttu-id="21deb-115">选择一个域以查看键/值对。</span><span class="sxs-lookup"><span data-stu-id="21deb-115">Select a domain to view the key-value pairs.</span></span>  
    
    > ##### <span data-ttu-id="21deb-116">图 3</span><span class="sxs-lookup"><span data-stu-id="21deb-116">Figure 3</span></span>  
    > <span data-ttu-id="21deb-117">`localStorage`域的键/值对 `https://www.bing.com`</span><span class="sxs-lookup"><span data-stu-id="21deb-117">The `localStorage` key-value pairs for the `https://www.bing.com` domain</span></span>  
    > ![域的 localStorage 键值对 https://www.bing.com][ImageLocalStorage]  

1.  <span data-ttu-id="21deb-119">选择表中的一行以查看表下方的查看器中的值。</span><span class="sxs-lookup"><span data-stu-id="21deb-119">Select a row of the table to view the value in the viewer below the table.</span></span>  
    
    > ##### <span data-ttu-id="21deb-120">图 4</span><span class="sxs-lookup"><span data-stu-id="21deb-120">Figure 4</span></span>  
    > <span data-ttu-id="21deb-121">查看键的值 `eventLogQueue_Online`</span><span class="sxs-lookup"><span data-stu-id="21deb-121">Viewing the value of the `eventLogQueue_Online` key</span></span>  
    > ![查看 eventLogQueue_Online 项的值][ImageLocalStorageViewer]  

## <span data-ttu-id="21deb-123">创建新的 `localStorage` 键/值对</span><span class="sxs-lookup"><span data-stu-id="21deb-123">Create a new `localStorage` key-value pair</span></span>   

1.  <span data-ttu-id="21deb-124">[查看 `localStorage` 域的键/值对](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="21deb-124">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="21deb-125">双击表格的空白部分。</span><span class="sxs-lookup"><span data-stu-id="21deb-125">Double-click the empty part of the table.</span></span>  <span data-ttu-id="21deb-126">DevTools 将创建一个新行，并将光标焦点放在**键**列中。</span><span class="sxs-lookup"><span data-stu-id="21deb-126">DevTools creates a new row and focuses your cursor in the **Key** column.</span></span>  
    
    > ##### <span data-ttu-id="21deb-127">图 5</span><span class="sxs-lookup"><span data-stu-id="21deb-127">Figure 5</span></span>  
    > <span data-ttu-id="21deb-128">要在其中创建新的键值对的表格的空部分，请双击该部分。</span><span class="sxs-lookup"><span data-stu-id="21deb-128">The empty part of the table to double-click in order to create a new key-value pair</span></span>  
    > ![要在其中创建新的键值对的表格的空部分，请双击该部分。][ImageLocalStorageCreate]  

## <span data-ttu-id="21deb-130">编辑 `localStorage` 键或值</span><span class="sxs-lookup"><span data-stu-id="21deb-130">Edit `localStorage` keys or values</span></span>   

1.  <span data-ttu-id="21deb-131">[查看 `localStorage` 域的键/值对](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="21deb-131">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="21deb-132">双击 "**键**" 或 "**值**" 列中的一个单元格以编辑该注册表项或值。</span><span class="sxs-lookup"><span data-stu-id="21deb-132">Double-click a cell in the **Key** or **Value** column to edit that key or value.</span></span>  
    
    > ##### <span data-ttu-id="21deb-133">图 6</span><span class="sxs-lookup"><span data-stu-id="21deb-133">Figure 6</span></span>  
    > <span data-ttu-id="21deb-134">编辑 `localStorage` 密钥</span><span class="sxs-lookup"><span data-stu-id="21deb-134">Editing a `localStorage` key</span></span>  
    > ![编辑 localStorage 键][ImageLocalStorageEdit]  

## <span data-ttu-id="21deb-136">删除 `localStorage` 键值对</span><span class="sxs-lookup"><span data-stu-id="21deb-136">Delete `localStorage` key-value pairs</span></span>   

1.  <span data-ttu-id="21deb-137">[查看 `localStorage` 域的键/值对](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="21deb-137">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  
1.  <span data-ttu-id="21deb-138">选择要删除的键/值对。</span><span class="sxs-lookup"><span data-stu-id="21deb-138">Select the key-value pair that you want to delete.</span></span>  <span data-ttu-id="21deb-139">DevTools 突出显示蓝色以指示它已选中。</span><span class="sxs-lookup"><span data-stu-id="21deb-139">DevTools highlights it blue to indicate that it is selected.</span></span>  

1.  <span data-ttu-id="21deb-140">按下 `Delete` 键或单击 "**删除**所选 ![ 删除" ][ImageDeleteIcon] 。</span><span class="sxs-lookup"><span data-stu-id="21deb-140">Press the `Delete` key or click **Delete Selected** ![Delete Selected][ImageDeleteIcon].</span></span>  

## <span data-ttu-id="21deb-141">删除 `localStorage` 域的所有键/值对</span><span class="sxs-lookup"><span data-stu-id="21deb-141">Delete all `localStorage` key-value pairs for a domain</span></span>   

1.  <span data-ttu-id="21deb-142">[查看 `localStorage` 域的键/值对](#view-localstorage-keys-and-values)。</span><span class="sxs-lookup"><span data-stu-id="21deb-142">[View the `localStorage` key-value pairs of a domain](#view-localstorage-keys-and-values).</span></span>  

1.  <span data-ttu-id="21deb-143">选择 "**全部**清除" ![ ][ImageClearIcon] 。</span><span class="sxs-lookup"><span data-stu-id="21deb-143">Select **Clear All** ![Clear All][ImageClearIcon].</span></span>  

## <span data-ttu-id="21deb-144">`localStorage`从控制台进行交互</span><span class="sxs-lookup"><span data-stu-id="21deb-144">Interact with `localStorage` from the Console</span></span>   

<span data-ttu-id="21deb-145">由于您能够在**控制台**中运行 JavaScript，并且由于**控制台**有权访问页面的 JavaScript 上下文，因此可以 `localStorage` 从**控制台**进行交互。</span><span class="sxs-lookup"><span data-stu-id="21deb-145">Since you are able to run JavaScript in the **Console**, and since the **Console** has access to the JavaScript contexts of the page, it is possible to interact with `localStorage` from the **Console**.</span></span>  

1.  <span data-ttu-id="21deb-146">如果要访问显示的页面以外的域的键/值对，请使用**JavaScript 上下文**菜单更改**控制台**的 JavaScript 上下文 `localStorage` 。</span><span class="sxs-lookup"><span data-stu-id="21deb-146">Use the **JavaScript contexts** menu to change the JavaScript context of the **Console** if you want to access the `localStorage` key-value pairs of a domain other than the page that is displayed.</span></span>  
    
    > ##### <span data-ttu-id="21deb-147">图 7</span><span class="sxs-lookup"><span data-stu-id="21deb-147">Figure 7</span></span>  
    > <span data-ttu-id="21deb-148">更改**控制台**的 JavaScript 上下文</span><span class="sxs-lookup"><span data-stu-id="21deb-148">Changing the JavaScript context of the **Console**</span></span>  
    > ![更改控制台的 JavaScript 上下文][ImageJSContext]  

1.  <span data-ttu-id="21deb-150">`localStorage`在控制台中运行表达式，与在 JavaScript 中执行的操作相同。</span><span class="sxs-lookup"><span data-stu-id="21deb-150">Run your `localStorage` expressions in the Console, the same as you do in your JavaScript.</span></span>  
    
    > ##### <span data-ttu-id="21deb-151">图 8</span><span class="sxs-lookup"><span data-stu-id="21deb-151">Figure 8</span></span>  
    > <span data-ttu-id="21deb-152">`localStorage`从**控制台**进行交互</span><span class="sxs-lookup"><span data-stu-id="21deb-152">Interacting with `localStorage` from the **Console**</span></span>  
    > ![从控制台与 localStorage 交互][ImageLocalStorageConsole]  

 



<!-- image links -->  

[ImageClearIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-icon.msft.png  
[ImageDeleteIcon]: /microsoft-edge/devtools-guide-chromium/media/delete-icon.msft.png  

[ImageManifest]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest.msft.png "图1：清单窗格"  
[ImageLocalStorageMenu]: /microsoft-edge/devtools-guide-chromium/media/storage-application-local-storage.msft.png "图2：本地存储菜单"  
[ImageLocalStorage]: /microsoft-edge/devtools-guide-chromium/media/storage-application-local-storage-view-key-value.msft.png "图3：域的 localStorage 键值对 https://www.bing.com"  
[ImageLocalStorageViewer]: /microsoft-edge/devtools-guide-chromium/media/storage-application-local-storage-view-key-value-selected.msft.png "图4：查看 eventLogQueue_Online 项的值"  
[ImageLocalStorageCreate]: /microsoft-edge/devtools-guide-chromium/media/storage-application-local-storage-new-key-value.msft.png "图5：要双击的表格的空部分，以便创建新的键值对"  
[ImageLocalStorageEdit]: /microsoft-edge/devtools-guide-chromium/media/storage-application-local-storage-edit-key-value.msft.png "图6：编辑 localStorage 键"  
[ImageJSContext]: /microsoft-edge/devtools-guide-chromium/media/storage-console-local-storage.msft.png "图7：更改控制台的 JavaScript 上下文"  
[ImageLocalStorageConsole]: /microsoft-edge/devtools-guide-chromium/media/storage-console-local-storage-interaction.msft.png "图8：从控制台与 localStorage 交互"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  

[MDNWindowsLocalStorage]: https://developer.mozilla.org/docs/Web/API/Window/localStorage "LocalStorage |MDN"  

> [!NOTE]
> <span data-ttu-id="21deb-164">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="21deb-164">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="21deb-165">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="21deb-165">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="21deb-167">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="21deb-167">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
