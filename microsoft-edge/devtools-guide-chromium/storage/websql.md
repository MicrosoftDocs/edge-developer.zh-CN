---
title: 通过 Microsoft Edge DevTools 查看 Web SQL 数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 7a1e3e47f6761cfdb23488683107ed0df6a8f4e2
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612058"
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





# <span data-ttu-id="d57ac-103">通过 Microsoft Edge DevTools 查看 Web SQL 数据</span><span class="sxs-lookup"><span data-stu-id="d57ac-103">View Web SQL Data With Microsoft Edge DevTools</span></span>   



> [!WARNING]
> <span data-ttu-id="d57ac-104">[未保留][W3CWebSQLStatus]Web SQL 规范。</span><span class="sxs-lookup"><span data-stu-id="d57ac-104">The Web SQL specification is [not being maintained][W3CWebSQLStatus].</span></span>  

<span data-ttu-id="d57ac-105">本指南介绍如何使用[Microsoft Edge DevTools][MicrosoftEdgeDevTools]检查 Web SQL 数据。</span><span class="sxs-lookup"><span data-stu-id="d57ac-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect Web SQL data.</span></span>  

## <span data-ttu-id="d57ac-106">查看 Web SQL 数据</span><span class="sxs-lookup"><span data-stu-id="d57ac-106">View Web SQL Data</span></span>   

1.  <span data-ttu-id="d57ac-107">选择 "**源**" 选项卡以打开 "**源**" 面板。</span><span class="sxs-lookup"><span data-stu-id="d57ac-107">Select the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="d57ac-108">默认情况下，**清单**窗格是默认打开的。</span><span class="sxs-lookup"><span data-stu-id="d57ac-108">The **Manifest** pane usually opens by default.</span></span>  
    
    > ##### <span data-ttu-id="d57ac-109">图 1</span><span class="sxs-lookup"><span data-stu-id="d57ac-109">Figure 1</span></span>  
    > <span data-ttu-id="d57ac-110">清单窗格</span><span class="sxs-lookup"><span data-stu-id="d57ac-110">The Manifest pane</span></span>  
    > ![清单窗格][ImageManifestPane]  
    
1.  <span data-ttu-id="d57ac-112">展开**WEB SQL**部分以查看数据库和表。</span><span class="sxs-lookup"><span data-stu-id="d57ac-112">Expand the **Web SQL** section to view databases and tables.</span></span>  <span data-ttu-id="d57ac-113">在**html5meetup**下方的[图 2](#figure-2)中，数据库和**会议室**是一个表。</span><span class="sxs-lookup"><span data-stu-id="d57ac-113">In [Figure 2](#figure-2) below **html5meetup** is a database and **rooms** is a table.</span></span>  
    
    > ##### <span data-ttu-id="d57ac-114">图 2</span><span class="sxs-lookup"><span data-stu-id="d57ac-114">Figure 2</span></span>  
    > <span data-ttu-id="d57ac-115">Web SQL 窗格</span><span class="sxs-lookup"><span data-stu-id="d57ac-115">The Web SQL pane</span></span>  
    > ![Web SQL 窗格][ImageWebSQLPane]  

1.  <span data-ttu-id="d57ac-117">选择一个表以查看该表的数据。</span><span class="sxs-lookup"><span data-stu-id="d57ac-117">Select a table to view the data for that table.</span></span>  
    
    > ##### <span data-ttu-id="d57ac-118">图 3</span><span class="sxs-lookup"><span data-stu-id="d57ac-118">Figure 3</span></span>  
    > <span data-ttu-id="d57ac-119">查看**聊天室**Web SQL 表的数据</span><span class="sxs-lookup"><span data-stu-id="d57ac-119">Viewing the data of the **rooms** Web SQL table</span></span>  
    > ![查看 Web SQL 表的数据][ImageWebSQLTable]  

## <span data-ttu-id="d57ac-121">编辑 Web SQL 数据</span><span class="sxs-lookup"><span data-stu-id="d57ac-121">Edit Web SQL data</span></span>   

<span data-ttu-id="d57ac-122">查看 Web SQL 表时，您无法编辑 Web SQL 数据，如上面的**图 3**所示。</span><span class="sxs-lookup"><span data-stu-id="d57ac-122">You are not able to edit Web SQL data when viewing a Web SQL table, such as in **Figure 3** above.</span></span>  <span data-ttu-id="d57ac-123">但是，你可以从编辑或删除表的 Web SQL 控制台运行语句。</span><span class="sxs-lookup"><span data-stu-id="d57ac-123">But you may run statements from the Web SQL Console that edit or delete tables.</span></span>  <span data-ttu-id="d57ac-124">请参阅[运行 WEB SQL 查询](#run-web-sql-queries)。</span><span class="sxs-lookup"><span data-stu-id="d57ac-124">See [Run Web SQL queries](#run-web-sql-queries).</span></span>  

## <span data-ttu-id="d57ac-125">运行 Web SQL 查询</span><span class="sxs-lookup"><span data-stu-id="d57ac-125">Run Web SQL queries</span></span>   

1.  <span data-ttu-id="d57ac-126">选择一个数据库以打开该数据库的控制台。</span><span class="sxs-lookup"><span data-stu-id="d57ac-126">Select a database to open a console for that database.</span></span>  

1.  <span data-ttu-id="d57ac-127">键入 Web SQL 语句，然后按 `Enter` 运行它。</span><span class="sxs-lookup"><span data-stu-id="d57ac-127">Type a Web SQL statement, then press `Enter` to run it.</span></span>  
    
    > ##### <span data-ttu-id="d57ac-128">图 4</span><span class="sxs-lookup"><span data-stu-id="d57ac-128">Figure 4</span></span>  
    > <span data-ttu-id="d57ac-129">使用 Web SQL 控制台删除**会议室**表中的行</span><span class="sxs-lookup"><span data-stu-id="d57ac-129">Using the Web SQL Console to delete a row from the **rooms** table</span></span>  
    > ![使用 Web SQL 控制台删除表中的行][ImageWebSQLEdit]  

## <span data-ttu-id="d57ac-131">刷新 Web SQL 表</span><span class="sxs-lookup"><span data-stu-id="d57ac-131">Refresh a Web SQL table</span></span>   

<span data-ttu-id="d57ac-132">DevTools 不会实时更新表。</span><span class="sxs-lookup"><span data-stu-id="d57ac-132">DevTools does not update tables in real-time.</span></span>  <span data-ttu-id="d57ac-133">更新表中的数据：</span><span class="sxs-lookup"><span data-stu-id="d57ac-133">To update the data in a table:</span></span>  

1.  <span data-ttu-id="d57ac-134">[查看 WEB SQL 表中的数据](#view-web-sql-data)。</span><span class="sxs-lookup"><span data-stu-id="d57ac-134">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="d57ac-135">选择 "**刷新** ![ 刷新" ][ImageRefreshIcon] 。</span><span class="sxs-lookup"><span data-stu-id="d57ac-135">Select **Refresh** ![Refresh][ImageRefreshIcon].</span></span>  

## <span data-ttu-id="d57ac-136">筛选出 Web SQL 表中的列</span><span class="sxs-lookup"><span data-stu-id="d57ac-136">Filter out columns in a Web SQL table</span></span>   

1.  <span data-ttu-id="d57ac-137">[查看 WEB SQL 表中的数据](#view-web-sql-data)。</span><span class="sxs-lookup"><span data-stu-id="d57ac-137">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="d57ac-138">使用 "**可见列**" 文本框指定要显示的列。</span><span class="sxs-lookup"><span data-stu-id="d57ac-138">Use the **Visible columns** text box to specify what columns you want to show.</span></span>  <span data-ttu-id="d57ac-139">以 CSV 列表的形式提供列名称。</span><span class="sxs-lookup"><span data-stu-id="d57ac-139">Provide the column names as a CSV list.</span></span>  
    
    > ##### <span data-ttu-id="d57ac-140">图 5</span><span class="sxs-lookup"><span data-stu-id="d57ac-140">Figure 5</span></span>  
    > <span data-ttu-id="d57ac-141">使用 "**可见列**" 文本框仅显示 " `room_name` 和" `last_updated` 列</span><span class="sxs-lookup"><span data-stu-id="d57ac-141">Using the **Visible Columns** text box to only show the `room_name` and `last_updated` columns</span></span>  
    > ![使用 "可见列" 文本框减少显示的列数][ImageWebSQLFilter]  

## <span data-ttu-id="d57ac-143">删除所有 Web SQL 数据</span><span class="sxs-lookup"><span data-stu-id="d57ac-143">Delete all Web SQL data</span></span>   

1.  <span data-ttu-id="d57ac-144">打开 "**清除存储**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="d57ac-144">Open the **Clear Storage** pane.</span></span>  
1.  <span data-ttu-id="d57ac-145">请确保 " **WEB SQL** " 复选框已启用。</span><span class="sxs-lookup"><span data-stu-id="d57ac-145">Make sure that the **Web SQL** checkbox is enabled.</span></span>  
    
    > ##### <span data-ttu-id="d57ac-146">图 6</span><span class="sxs-lookup"><span data-stu-id="d57ac-146">Figure 6</span></span>  
    > <span data-ttu-id="d57ac-147">" **WEB SQL** " 复选框</span><span class="sxs-lookup"><span data-stu-id="d57ac-147">The **Web SQL** checkbox</span></span>  
    > !["Web SQL" 复选框][ImageWebSQLCheckbox]  

1.  <span data-ttu-id="d57ac-149">选择 "**清除网站数据**"。</span><span class="sxs-lookup"><span data-stu-id="d57ac-149">Select **Clear site data**.</span></span>  
    
    > ##### <span data-ttu-id="d57ac-150">图 7</span><span class="sxs-lookup"><span data-stu-id="d57ac-150">Figure 7</span></span>  
    > <span data-ttu-id="d57ac-151">"**清除网站数据**" 按钮</span><span class="sxs-lookup"><span data-stu-id="d57ac-151">The **Clear Site Data** button</span></span>  
    > !["清除网站数据" 按钮][ImageClearWebSQL]  

 



<!-- image links -->  

[ImageRefreshIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-icon.msft.png  

[ImageManifestPane]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest.msft.png "图1：清单窗格"  
[ImageWebSQLPane]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-web-sql.msft.png "图2： Web SQL 窗格"  
[ImageWebSQLTable]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png "图3：查看 Web SQL 表的数据"  
[ImageWebSQLEdit]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-web-sql-html5meetup-commands.msft.png "图4：使用 Web SQL 控制台删除表中的行"  
[ImageWebSQLFilter]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png "图5：使用 "可见列" 文本框减少显示的列数"  
[ImageWebSQLCheckbox]: /microsoft-edge/devtools-guide-chromium/media/storage-application-clear-storage-web-sql.msft.png "图6： "Web SQL" 复选框"  
[ImageClearWebSQL]: /microsoft-edge/devtools-guide-chromium/media/storage-application-clear-storage-clear-site-data-button.msft.png "图7： "清除网站数据" 按钮"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  

[W3CWebSQLStatus]: https://w3.org/TR/webdatabase/#status-of-this-document "Web SQL 数据库 |W3C"  

> [!NOTE]
> <span data-ttu-id="d57ac-162">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="d57ac-162">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d57ac-163">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/websql)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="d57ac-163">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/websql) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="d57ac-165">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="d57ac-165">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
