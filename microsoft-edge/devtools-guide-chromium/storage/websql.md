---
description: 如何从 Microsoft Edge DevTools 的 "应用程序" 面板查看 Web SQL 数据。
title: 通过 Microsoft Edge DevTools 查看 Web SQL 数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
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





# <span data-ttu-id="aadba-104">通过 Microsoft Edge DevTools 查看 Web SQL 数据</span><span class="sxs-lookup"><span data-stu-id="aadba-104">View Web SQL data with Microsoft Edge DevTools</span></span>   



> [!WARNING]
> <span data-ttu-id="aadba-105">[未保留][W3CWebSQLStatus]Web SQL 规范。</span><span class="sxs-lookup"><span data-stu-id="aadba-105">The Web SQL specification is [not being maintained][W3CWebSQLStatus].</span></span>  

<span data-ttu-id="aadba-106">本指南介绍如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 检查 Web SQL 数据。</span><span class="sxs-lookup"><span data-stu-id="aadba-106">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect Web SQL data.</span></span>  

## <span data-ttu-id="aadba-107">查看 Web SQL 数据</span><span class="sxs-lookup"><span data-stu-id="aadba-107">View Web SQL Data</span></span>   

1.  <span data-ttu-id="aadba-108">选择 " **源** " 选项卡以打开 " **源** " 面板。</span><span class="sxs-lookup"><span data-stu-id="aadba-108">Select the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="aadba-109">默认情况下， **清单** 窗格是默认打开的。</span><span class="sxs-lookup"><span data-stu-id="aadba-109">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="aadba-111">**清单**窗格</span><span class="sxs-lookup"><span data-stu-id="aadba-111">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="aadba-112">展开 **WEB SQL** 部分以查看数据库和表。</span><span class="sxs-lookup"><span data-stu-id="aadba-112">Expand the **Web SQL** section to view databases and tables.</span></span>  <span data-ttu-id="aadba-113">下图中， **html5meetup** 下方是一个数据库， **房间** 是一个表。</span><span class="sxs-lookup"><span data-stu-id="aadba-113">In the following figure, below **html5meetup** is a database and **rooms** is a table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-web-sql.msft.png":::
       <span data-ttu-id="aadba-115">**WEB SQL**窗格</span><span class="sxs-lookup"><span data-stu-id="aadba-115">The **Web SQL** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="aadba-116">选择一个表以查看该表的数据。</span><span class="sxs-lookup"><span data-stu-id="aadba-116">Select a table to view the data for that table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png":::
       <span data-ttu-id="aadba-118">查看 Web SQL 表的数据</span><span class="sxs-lookup"><span data-stu-id="aadba-118">View the data of a Web SQL table</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="aadba-119">编辑 Web SQL 数据</span><span class="sxs-lookup"><span data-stu-id="aadba-119">Edit Web SQL data</span></span>   

<span data-ttu-id="aadba-120">查看 Web SQL 表时，您无法编辑 Web SQL 数据，如上面的 **图 3** 所示。</span><span class="sxs-lookup"><span data-stu-id="aadba-120">You are not able to edit Web SQL data when viewing a Web SQL table, such as in **Figure 3** above.</span></span>  <span data-ttu-id="aadba-121">但是，你可以从编辑或删除表的 Web SQL 控制台运行语句。</span><span class="sxs-lookup"><span data-stu-id="aadba-121">But you may run statements from the Web SQL Console that edit or delete tables.</span></span>  <span data-ttu-id="aadba-122">请参阅 [运行 WEB SQL 查询](#run-web-sql-queries)。</span><span class="sxs-lookup"><span data-stu-id="aadba-122">See [Run Web SQL queries](#run-web-sql-queries).</span></span>  

## <span data-ttu-id="aadba-123">运行 Web SQL 查询</span><span class="sxs-lookup"><span data-stu-id="aadba-123">Run Web SQL queries</span></span>   

1.  <span data-ttu-id="aadba-124">选择一个数据库以打开该数据库的控制台。</span><span class="sxs-lookup"><span data-stu-id="aadba-124">Select a database to open a console for that database.</span></span>  
1.  <span data-ttu-id="aadba-125">键入 Web SQL 语句，然后按 `Enter` 运行它。</span><span class="sxs-lookup"><span data-stu-id="aadba-125">Type a Web SQL statement, then press `Enter` to run it.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png":::
       <span data-ttu-id="aadba-127">使用 Web SQL 控制台删除表中的行</span><span class="sxs-lookup"><span data-stu-id="aadba-127">Use the Web SQL Console to delete a row from a table</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="aadba-128">刷新 Web SQL 表</span><span class="sxs-lookup"><span data-stu-id="aadba-128">Refresh a Web SQL table</span></span>   

<span data-ttu-id="aadba-129">DevTools 不会实时更新表。</span><span class="sxs-lookup"><span data-stu-id="aadba-129">DevTools does not update tables in real-time.</span></span>  <span data-ttu-id="aadba-130">更新表中的数据：</span><span class="sxs-lookup"><span data-stu-id="aadba-130">To update the data in a table:</span></span>  

1.  <span data-ttu-id="aadba-131">[查看 WEB SQL 表中的数据](#view-web-sql-data)。</span><span class="sxs-lookup"><span data-stu-id="aadba-131">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="aadba-132">选择 " **刷新** \ (![ 刷新 ][ImageRefreshIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="aadba-132">Select **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  
    
## <span data-ttu-id="aadba-133">筛选出 Web SQL 表中的列</span><span class="sxs-lookup"><span data-stu-id="aadba-133">Filter out columns in a Web SQL table</span></span>   

1.  <span data-ttu-id="aadba-134">[查看 WEB SQL 表中的数据](#view-web-sql-data)。</span><span class="sxs-lookup"><span data-stu-id="aadba-134">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="aadba-135">使用 " **可见列** " 文本框指定要显示的列。</span><span class="sxs-lookup"><span data-stu-id="aadba-135">Use the **Visible columns** text box to specify what columns you want to show.</span></span>  <span data-ttu-id="aadba-136">以 CSV 列表的形式提供列名称。</span><span class="sxs-lookup"><span data-stu-id="aadba-136">Provide the column names as a CSV list.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png":::
       <span data-ttu-id="aadba-138">使用 " **可见列** " 文本框减少显示的列数</span><span class="sxs-lookup"><span data-stu-id="aadba-138">Use the **Visible Columns** text box to reduce the number of columns shown</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="aadba-139">删除所有 Web SQL 数据</span><span class="sxs-lookup"><span data-stu-id="aadba-139">Delete all Web SQL data</span></span>   

1.  <span data-ttu-id="aadba-140">打开 " **清除存储** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="aadba-140">Open the **Clear Storage** pane.</span></span>  
1.  <span data-ttu-id="aadba-141">请确保 " **WEB SQL** " 复选框已启用。</span><span class="sxs-lookup"><span data-stu-id="aadba-141">Make sure that the **Web SQL** checkbox is enabled.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-web-sql.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-clear-storage-web-sql.msft.png":::
       <span data-ttu-id="aadba-143">" **WEB SQL** " 复选框</span><span class="sxs-lookup"><span data-stu-id="aadba-143">The **Web SQL** checkbox</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="aadba-144">选择 " **清除网站数据**"。</span><span class="sxs-lookup"><span data-stu-id="aadba-144">Select **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-clear-site-data-button.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-clear-storage-clear-site-data-button.msft.png":::
       <span data-ttu-id="aadba-146">" **清除网站数据** " 按钮</span><span class="sxs-lookup"><span data-stu-id="aadba-146">The **Clear Site Data** button</span></span>  
    :::image-end:::  
    
<!--  
 


-->  

<!-- image links -->  

[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  

[W3CWebSQLStatus]: https://w3.org/TR/webdatabase/#status-of-this-document "Web SQL 数据库 |W3C"  

> [!NOTE]
> <span data-ttu-id="aadba-149">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="aadba-149">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="aadba-150">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/websql)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="aadba-150">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/websql) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="aadba-152">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="aadba-152">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
