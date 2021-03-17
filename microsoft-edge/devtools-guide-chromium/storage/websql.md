---
description: 如何查看 Web SQL Microsoft Edge DevTools 的应用程序面板的数据。
title: 使用 Microsoft Edge SQL查看 Web 数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 9f684aabf3592220079e6a8595d91cfea6785769
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439596"
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

# <a name="view-web-sql-data-with-microsoft-edge-devtools"></a><span data-ttu-id="261b1-104">使用 Microsoft Edge SQL查看 Web 数据</span><span class="sxs-lookup"><span data-stu-id="261b1-104">View Web SQL data with Microsoft Edge DevTools</span></span>  

> [!WARNING]
> <span data-ttu-id="261b1-105">Web SQL [规范未得到维护][W3CWebSQLStatus]。</span><span class="sxs-lookup"><span data-stu-id="261b1-105">The Web SQL specification is [not being maintained][W3CWebSQLStatus].</span></span>  

<span data-ttu-id="261b1-106">本指南演示如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 检查 Web SQL数据。</span><span class="sxs-lookup"><span data-stu-id="261b1-106">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect Web SQL data.</span></span>  

## <a name="view-web-sql-data"></a><span data-ttu-id="261b1-107">查看 Web SQL数据</span><span class="sxs-lookup"><span data-stu-id="261b1-107">View Web SQL Data</span></span>  

1.  <span data-ttu-id="261b1-108">选择 **"源** "工具以打开 **"源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="261b1-108">Choose the **Sources** tool to open the **Sources** tool.</span></span>  <span data-ttu-id="261b1-109">" **清单** "窗格通常默认打开。</span><span class="sxs-lookup"><span data-stu-id="261b1-109">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="261b1-111">清单**窗格**</span><span class="sxs-lookup"><span data-stu-id="261b1-111">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="261b1-112">展开 **"Web SQL"** 部分以查看数据库和表。</span><span class="sxs-lookup"><span data-stu-id="261b1-112">Expand the **Web SQL** section to view databases and tables.</span></span>  <span data-ttu-id="261b1-113">在下图中 **，html5meetup** 下面是一个数据库， **而 rooms** 是一个表。</span><span class="sxs-lookup"><span data-stu-id="261b1-113">In the following figure, below **html5meetup** is a database and **rooms** is a table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql.msft.png" alt-text="Web SQL窗格" lightbox="../media/storage-application-storage-web-sql.msft.png":::
       <span data-ttu-id="261b1-115">Web **SQL** 窗格</span><span class="sxs-lookup"><span data-stu-id="261b1-115">The **Web SQL** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="261b1-116">选择一个表以查看该表的数据。</span><span class="sxs-lookup"><span data-stu-id="261b1-116">Choose a table to view the data for that table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png" alt-text="查看 Web 应用程序表SQL数据" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png":::
       <span data-ttu-id="261b1-118">查看 Web 应用程序表SQL数据</span><span class="sxs-lookup"><span data-stu-id="261b1-118">View the data of a Web SQL table</span></span>  
    :::image-end:::  
    
## <a name="edit-web-sql-data"></a><span data-ttu-id="261b1-119">编辑 Web SQL数据</span><span class="sxs-lookup"><span data-stu-id="261b1-119">Edit Web SQL data</span></span>  

<span data-ttu-id="261b1-120">在查看 Web 数据表时SQL编辑 Web SQL数据，如上文所述。</span><span class="sxs-lookup"><span data-stu-id="261b1-120">You are not able to edit Web SQL data when viewing a Web SQL table, such as in previous above.</span></span>  <span data-ttu-id="261b1-121">但是，您可以运行来自 Web SQL编辑或删除表的语句。</span><span class="sxs-lookup"><span data-stu-id="261b1-121">But you may run statements from the Web SQL Console that edit or delete tables.</span></span>  <span data-ttu-id="261b1-122">导航到["运行 Web SQL查询"。](#run-web-sql-queries)</span><span class="sxs-lookup"><span data-stu-id="261b1-122">Navigate to [Run Web SQL queries](#run-web-sql-queries).</span></span>  

## <a name="run-web-sql-queries"></a><span data-ttu-id="261b1-123">运行 Web SQL查询</span><span class="sxs-lookup"><span data-stu-id="261b1-123">Run Web SQL queries</span></span>  

1.  <span data-ttu-id="261b1-124">选择一个数据库以打开该数据库的控制台。</span><span class="sxs-lookup"><span data-stu-id="261b1-124">Choose a database to open a console for that database.</span></span>  
1.  <span data-ttu-id="261b1-125">键入 Web SQL 语句，然后选择 `Enter` 以运行它。</span><span class="sxs-lookup"><span data-stu-id="261b1-125">Type a Web SQL statement, then select `Enter` to run it.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png" alt-text="使用 Web SQL控制台从表中删除行" lightbox="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png":::
       <span data-ttu-id="261b1-127">使用 Web SQL控制台从表中删除行</span><span class="sxs-lookup"><span data-stu-id="261b1-127">Use the Web SQL Console to delete a row from a table</span></span>  
    :::image-end:::  
    
## <a name="refresh-a-web-sql-table"></a><span data-ttu-id="261b1-128">刷新 Web SQL表</span><span class="sxs-lookup"><span data-stu-id="261b1-128">Refresh a Web SQL table</span></span>  

<span data-ttu-id="261b1-129">DevTools 不会实时更新表。</span><span class="sxs-lookup"><span data-stu-id="261b1-129">DevTools does not update tables in real-time.</span></span>  <span data-ttu-id="261b1-130">若要更新表中的数据，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="261b1-130">To update the data in a table, complete the following actions.</span></span>  

1.  <span data-ttu-id="261b1-131">[查看 Web 服务表中的SQL数据](#view-web-sql-data)。</span><span class="sxs-lookup"><span data-stu-id="261b1-131">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="261b1-132">Choose **Refresh** \ (![ Refresh ](../media/refresh-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="261b1-132">Choose **Refresh** \(![Refresh](../media/refresh-icon.msft.png)\).</span></span>  
    
## <a name="filter-out-columns-in-a-web-sql-table"></a><span data-ttu-id="261b1-133">筛选出 Web 数据表中的SQL列</span><span class="sxs-lookup"><span data-stu-id="261b1-133">Filter out columns in a Web SQL table</span></span>  

1.  <span data-ttu-id="261b1-134">[查看 Web 服务表中的SQL数据](#view-web-sql-data)。</span><span class="sxs-lookup"><span data-stu-id="261b1-134">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="261b1-135">使用 **"可见列** "文本框指定要显示哪些列。</span><span class="sxs-lookup"><span data-stu-id="261b1-135">Use the **Visible columns** text box to specify what columns you want to show.</span></span>  <span data-ttu-id="261b1-136">将列名称作为 CSV 列表提供。</span><span class="sxs-lookup"><span data-stu-id="261b1-136">Provide the column names as a CSV list.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png" alt-text="使用"可见列"文本框减少显示的列数" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png":::
       <span data-ttu-id="261b1-138">使用 **"可见列** "文本框减少显示的列数</span><span class="sxs-lookup"><span data-stu-id="261b1-138">Use the **Visible Columns** text box to reduce the number of columns shown</span></span>  
    :::image-end:::  
    
## <a name="delete-all-web-sql-data"></a><span data-ttu-id="261b1-139">删除所有 Web SQL数据</span><span class="sxs-lookup"><span data-stu-id="261b1-139">Delete all Web SQL data</span></span>  

1.  <span data-ttu-id="261b1-140">打开" **清除存储"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="261b1-140">Open the **Clear Storage** pane.</span></span>  
1.  <span data-ttu-id="261b1-141">确保 **"Web SQL"** 复选框已打开。</span><span class="sxs-lookup"><span data-stu-id="261b1-141">Make sure that the **Web SQL** checkbox is turned on.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-web-sql.msft.png" alt-text=""Web SQL"复选框" lightbox="../media/storage-application-clear-storage-web-sql.msft.png":::
       <span data-ttu-id="261b1-143">"Web **SQL"** 复选框</span><span class="sxs-lookup"><span data-stu-id="261b1-143">The **Web SQL** checkbox</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="261b1-144">选择 **"清除网站数据"。**</span><span class="sxs-lookup"><span data-stu-id="261b1-144">Choose **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-clear-site-data-button.msft.png" alt-text=""清除网站数据"按钮" lightbox="../media/storage-application-clear-storage-clear-site-data-button.msft.png":::
       <span data-ttu-id="261b1-146">" **清除网站数据"** 按钮</span><span class="sxs-lookup"><span data-stu-id="261b1-146">The **Clear Site Data** button</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="261b1-147">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="261b1-147">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  

[W3CWebSQLStatus]: https://w3.org/TR/webdatabase/#status-of-this-document "Web SQL数据库|W3C"  

> [!NOTE]
> <span data-ttu-id="261b1-150">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="261b1-150">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="261b1-151">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/websql)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="261b1-151">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/websql) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="261b1-153">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="261b1-153">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
