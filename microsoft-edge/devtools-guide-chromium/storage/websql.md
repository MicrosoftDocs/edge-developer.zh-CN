---
title: 通过 Microsoft Edge DevTools 查看 Web SQL 数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 8b2e6d1a117e401f9e579cb28f81da9676eea979
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10983446"
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





# <span data-ttu-id="0a5a7-103">通过 Microsoft Edge DevTools 查看 Web SQL 数据</span><span class="sxs-lookup"><span data-stu-id="0a5a7-103">View Web SQL data with Microsoft Edge DevTools</span></span>   



> [!WARNING]
> <span data-ttu-id="0a5a7-104">[未保留][W3CWebSQLStatus]Web SQL 规范。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-104">The Web SQL specification is [not being maintained][W3CWebSQLStatus].</span></span>  

<span data-ttu-id="0a5a7-105">本指南介绍如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 检查 Web SQL 数据。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect Web SQL data.</span></span>  

## <span data-ttu-id="0a5a7-106">查看 Web SQL 数据</span><span class="sxs-lookup"><span data-stu-id="0a5a7-106">View Web SQL Data</span></span>   

1.  <span data-ttu-id="0a5a7-107">选择 " **源** " 选项卡以打开 " **源** " 面板。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-107">Select the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="0a5a7-108">默认情况下， **清单** 窗格是默认打开的。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-108">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="0a5a7-110">**清单**窗格</span><span class="sxs-lookup"><span data-stu-id="0a5a7-110">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0a5a7-111">展开 **WEB SQL** 部分以查看数据库和表。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-111">Expand the **Web SQL** section to view databases and tables.</span></span>  <span data-ttu-id="0a5a7-112">下图中， **html5meetup** 下方是一个数据库， **房间** 是一个表。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-112">In the following figure, below **html5meetup** is a database and **rooms** is a table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql.msft.png" alt-text="Web SQL 窗格" lightbox="../media/storage-application-storage-web-sql.msft.png":::
       <span data-ttu-id="0a5a7-114">**WEB SQL**窗格</span><span class="sxs-lookup"><span data-stu-id="0a5a7-114">The **Web SQL** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0a5a7-115">选择一个表以查看该表的数据。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-115">Select a table to view the data for that table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png" alt-text="查看 Web SQL 表的数据" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png":::
       <span data-ttu-id="0a5a7-117">查看 Web SQL 表的数据</span><span class="sxs-lookup"><span data-stu-id="0a5a7-117">View the data of a Web SQL table</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="0a5a7-118">编辑 Web SQL 数据</span><span class="sxs-lookup"><span data-stu-id="0a5a7-118">Edit Web SQL data</span></span>   

<span data-ttu-id="0a5a7-119">查看 Web SQL 表时，您无法编辑 Web SQL 数据，如上面的 **图 3** 所示。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-119">You are not able to edit Web SQL data when viewing a Web SQL table, such as in **Figure 3** above.</span></span>  <span data-ttu-id="0a5a7-120">但是，你可以从编辑或删除表的 Web SQL 控制台运行语句。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-120">But you may run statements from the Web SQL Console that edit or delete tables.</span></span>  <span data-ttu-id="0a5a7-121">请参阅 [运行 WEB SQL 查询](#run-web-sql-queries)。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-121">See [Run Web SQL queries](#run-web-sql-queries).</span></span>  

## <span data-ttu-id="0a5a7-122">运行 Web SQL 查询</span><span class="sxs-lookup"><span data-stu-id="0a5a7-122">Run Web SQL queries</span></span>   

1.  <span data-ttu-id="0a5a7-123">选择一个数据库以打开该数据库的控制台。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-123">Select a database to open a console for that database.</span></span>  
1.  <span data-ttu-id="0a5a7-124">键入 Web SQL 语句，然后按 `Enter` 运行它。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-124">Type a Web SQL statement, then press `Enter` to run it.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png" alt-text="使用 Web SQL 控制台删除表中的行" lightbox="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png":::
       <span data-ttu-id="0a5a7-126">使用 Web SQL 控制台删除表中的行</span><span class="sxs-lookup"><span data-stu-id="0a5a7-126">Use the Web SQL Console to delete a row from a table</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="0a5a7-127">刷新 Web SQL 表</span><span class="sxs-lookup"><span data-stu-id="0a5a7-127">Refresh a Web SQL table</span></span>   

<span data-ttu-id="0a5a7-128">DevTools 不会实时更新表。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-128">DevTools does not update tables in real-time.</span></span>  <span data-ttu-id="0a5a7-129">更新表中的数据：</span><span class="sxs-lookup"><span data-stu-id="0a5a7-129">To update the data in a table:</span></span>  

1.  <span data-ttu-id="0a5a7-130">[查看 WEB SQL 表中的数据](#view-web-sql-data)。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-130">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="0a5a7-131">选择 " **刷新** \ (![ 刷新 ][ImageRefreshIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-131">Select **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  
    
## <span data-ttu-id="0a5a7-132">筛选出 Web SQL 表中的列</span><span class="sxs-lookup"><span data-stu-id="0a5a7-132">Filter out columns in a Web SQL table</span></span>   

1.  <span data-ttu-id="0a5a7-133">[查看 WEB SQL 表中的数据](#view-web-sql-data)。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-133">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="0a5a7-134">使用 " **可见列** " 文本框指定要显示的列。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-134">Use the **Visible columns** text box to specify what columns you want to show.</span></span>  <span data-ttu-id="0a5a7-135">以 CSV 列表的形式提供列名称。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-135">Provide the column names as a CSV list.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png" alt-text="使用 "可见列" 文本框减少显示的列数" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png":::
       <span data-ttu-id="0a5a7-137">使用 " **可见列** " 文本框减少显示的列数</span><span class="sxs-lookup"><span data-stu-id="0a5a7-137">Use the **Visible Columns** text box to reduce the number of columns shown</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="0a5a7-138">删除所有 Web SQL 数据</span><span class="sxs-lookup"><span data-stu-id="0a5a7-138">Delete all Web SQL data</span></span>   

1.  <span data-ttu-id="0a5a7-139">打开 " **清除存储** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-139">Open the **Clear Storage** pane.</span></span>  
1.  <span data-ttu-id="0a5a7-140">请确保 " **WEB SQL** " 复选框已启用。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-140">Make sure that the **Web SQL** checkbox is enabled.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-web-sql.msft.png" alt-text=""Web SQL" 复选框" lightbox="../media/storage-application-clear-storage-web-sql.msft.png":::
       <span data-ttu-id="0a5a7-142">" **WEB SQL** " 复选框</span><span class="sxs-lookup"><span data-stu-id="0a5a7-142">The **Web SQL** checkbox</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0a5a7-143">选择 " **清除网站数据**"。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-143">Select **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-clear-site-data-button.msft.png" alt-text=""清除网站数据" 按钮" lightbox="../media/storage-application-clear-storage-clear-site-data-button.msft.png":::
       <span data-ttu-id="0a5a7-145">" **清除网站数据** " 按钮</span><span class="sxs-lookup"><span data-stu-id="0a5a7-145">The **Clear Site Data** button</span></span>  
    :::image-end:::  
    
<!--  
 


-->  

<!-- image links -->  

[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  

[W3CWebSQLStatus]: https://w3.org/TR/webdatabase/#status-of-this-document "Web SQL 数据库 |W3C"  

> [!NOTE]
> <span data-ttu-id="0a5a7-148">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-148">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0a5a7-149">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/websql)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-149">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/websql) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="0a5a7-151">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="0a5a7-151">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
