---
description: How to view Web SQL data from the Application panel of Microsoft Edge DevTools.
title: View Web SQL Data With Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: cc2f726c80fbf0c943b43ff6c131e9479db75b78
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993532"
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





# <span data-ttu-id="c38e1-104">View Web SQL data with Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="c38e1-104">View Web SQL data with Microsoft Edge DevTools</span></span>   



> [!WARNING]
> <span data-ttu-id="c38e1-105">The Web SQL specification is [not being maintained][W3CWebSQLStatus].</span><span class="sxs-lookup"><span data-stu-id="c38e1-105">The Web SQL specification is [not being maintained][W3CWebSQLStatus].</span></span>  

<span data-ttu-id="c38e1-106">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect Web SQL data.</span><span class="sxs-lookup"><span data-stu-id="c38e1-106">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect Web SQL data.</span></span>  

## <span data-ttu-id="c38e1-107">View Web SQL Data</span><span class="sxs-lookup"><span data-stu-id="c38e1-107">View Web SQL Data</span></span>   

1.  <span data-ttu-id="c38e1-108">Select the **Sources** tab to open the **Sources** panel.</span><span class="sxs-lookup"><span data-stu-id="c38e1-108">Select the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="c38e1-109">The **Manifest** pane usually opens by default.</span><span class="sxs-lookup"><span data-stu-id="c38e1-109">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="c38e1-111">The **Manifest** pane</span><span class="sxs-lookup"><span data-stu-id="c38e1-111">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c38e1-112">Expand the **Web SQL** section to view databases and tables.</span><span class="sxs-lookup"><span data-stu-id="c38e1-112">Expand the **Web SQL** section to view databases and tables.</span></span>  <span data-ttu-id="c38e1-113">In the following figure, below **html5meetup** is a database and **rooms** is a table.</span><span class="sxs-lookup"><span data-stu-id="c38e1-113">In the following figure, below **html5meetup** is a database and **rooms** is a table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-storage-web-sql.msft.png":::
       <span data-ttu-id="c38e1-115">The **Web SQL** pane</span><span class="sxs-lookup"><span data-stu-id="c38e1-115">The **Web SQL** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c38e1-116">Select a table to view the data for that table.</span><span class="sxs-lookup"><span data-stu-id="c38e1-116">Select a table to view the data for that table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png":::
       <span data-ttu-id="c38e1-118">View the data of a Web SQL table</span><span class="sxs-lookup"><span data-stu-id="c38e1-118">View the data of a Web SQL table</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="c38e1-119">Edit Web SQL data</span><span class="sxs-lookup"><span data-stu-id="c38e1-119">Edit Web SQL data</span></span>   

<span data-ttu-id="c38e1-120">You are not able to edit Web SQL data when viewing a Web SQL table, such as in **Figure 3** above.</span><span class="sxs-lookup"><span data-stu-id="c38e1-120">You are not able to edit Web SQL data when viewing a Web SQL table, such as in **Figure 3** above.</span></span>  <span data-ttu-id="c38e1-121">But you may run statements from the Web SQL Console that edit or delete tables.</span><span class="sxs-lookup"><span data-stu-id="c38e1-121">But you may run statements from the Web SQL Console that edit or delete tables.</span></span>  <span data-ttu-id="c38e1-122">See [Run Web SQL queries](#run-web-sql-queries).</span><span class="sxs-lookup"><span data-stu-id="c38e1-122">See [Run Web SQL queries](#run-web-sql-queries).</span></span>  

## <span data-ttu-id="c38e1-123">Run Web SQL queries</span><span class="sxs-lookup"><span data-stu-id="c38e1-123">Run Web SQL queries</span></span>   

1.  <span data-ttu-id="c38e1-124">Select a database to open a console for that database.</span><span class="sxs-lookup"><span data-stu-id="c38e1-124">Select a database to open a console for that database.</span></span>  
1.  <span data-ttu-id="c38e1-125">Type a Web SQL statement, then press `Enter` to run it.</span><span class="sxs-lookup"><span data-stu-id="c38e1-125">Type a Web SQL statement, then press `Enter` to run it.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png":::
       <span data-ttu-id="c38e1-127">Use the Web SQL Console to delete a row from a table</span><span class="sxs-lookup"><span data-stu-id="c38e1-127">Use the Web SQL Console to delete a row from a table</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="c38e1-128">Refresh a Web SQL table</span><span class="sxs-lookup"><span data-stu-id="c38e1-128">Refresh a Web SQL table</span></span>   

<span data-ttu-id="c38e1-129">DevTools does not update tables in real-time.</span><span class="sxs-lookup"><span data-stu-id="c38e1-129">DevTools does not update tables in real-time.</span></span>  <span data-ttu-id="c38e1-130">To update the data in a table:</span><span class="sxs-lookup"><span data-stu-id="c38e1-130">To update the data in a table:</span></span>  

1.  <span data-ttu-id="c38e1-131">[View the data in a Web SQL table](#view-web-sql-data).</span><span class="sxs-lookup"><span data-stu-id="c38e1-131">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="c38e1-132">Select **Refresh** \(![Refresh][ImageRefreshIcon]\).</span><span class="sxs-lookup"><span data-stu-id="c38e1-132">Select **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  
    
## <span data-ttu-id="c38e1-133">Filter out columns in a Web SQL table</span><span class="sxs-lookup"><span data-stu-id="c38e1-133">Filter out columns in a Web SQL table</span></span>   

1.  <span data-ttu-id="c38e1-134">[View the data in a Web SQL table](#view-web-sql-data).</span><span class="sxs-lookup"><span data-stu-id="c38e1-134">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="c38e1-135">Use the **Visible columns** text box to specify what columns you want to show.</span><span class="sxs-lookup"><span data-stu-id="c38e1-135">Use the **Visible columns** text box to specify what columns you want to show.</span></span>  <span data-ttu-id="c38e1-136">Provide the column names as a CSV list.</span><span class="sxs-lookup"><span data-stu-id="c38e1-136">Provide the column names as a CSV list.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png":::
       <span data-ttu-id="c38e1-138">Use the **Visible Columns** text box to reduce the number of columns shown</span><span class="sxs-lookup"><span data-stu-id="c38e1-138">Use the **Visible Columns** text box to reduce the number of columns shown</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="c38e1-139">Delete all Web SQL data</span><span class="sxs-lookup"><span data-stu-id="c38e1-139">Delete all Web SQL data</span></span>   

1.  <span data-ttu-id="c38e1-140">Open the **Clear Storage** pane.</span><span class="sxs-lookup"><span data-stu-id="c38e1-140">Open the **Clear Storage** pane.</span></span>  
1.  <span data-ttu-id="c38e1-141">Make sure that the **Web SQL** checkbox is enabled.</span><span class="sxs-lookup"><span data-stu-id="c38e1-141">Make sure that the **Web SQL** checkbox is enabled.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-web-sql.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-clear-storage-web-sql.msft.png":::
       <span data-ttu-id="c38e1-143">The **Web SQL** checkbox</span><span class="sxs-lookup"><span data-stu-id="c38e1-143">The **Web SQL** checkbox</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c38e1-144">Select **Clear site data**.</span><span class="sxs-lookup"><span data-stu-id="c38e1-144">Select **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-clear-site-data-button.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-clear-storage-clear-site-data-button.msft.png":::
       <span data-ttu-id="c38e1-146">The **Clear Site Data** button</span><span class="sxs-lookup"><span data-stu-id="c38e1-146">The **Clear Site Data** button</span></span>  
    :::image-end:::  
    
<!--  
 


-->  

<!-- image links -->  

[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) Developer Tools | Microsoft Docs"  

[W3CWebSQLStatus]: https://w3.org/TR/webdatabase/#status-of-this-document "Web SQL database | W3C"  

> [!NOTE]
> <span data-ttu-id="c38e1-149">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="c38e1-149">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c38e1-150">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/websql)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="c38e1-150">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/websql) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="c38e1-152">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="c38e1-152">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
