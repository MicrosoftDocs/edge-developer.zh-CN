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

# <a name="view-web-sql-data-with-microsoft-edge-devtools"></a>使用 Microsoft Edge SQL查看 Web 数据  

> [!WARNING]
> Web SQL [规范未得到维护][W3CWebSQLStatus]。  

本指南演示如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 检查 Web SQL数据。  

## <a name="view-web-sql-data"></a>查看 Web SQL数据  

1.  选择 **"源** "工具以打开 **"源"** 工具。  " **清单** "窗格通常默认打开。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       清单**窗格**  
    :::image-end:::  
    
1.  展开 **"Web SQL"** 部分以查看数据库和表。  在下图中 **，html5meetup** 下面是一个数据库， **而 rooms** 是一个表。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql.msft.png" alt-text="Web SQL窗格" lightbox="../media/storage-application-storage-web-sql.msft.png":::
       Web **SQL** 窗格  
    :::image-end:::  
    
1.  选择一个表以查看该表的数据。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png" alt-text="查看 Web 应用程序表SQL数据" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png":::
       查看 Web 应用程序表SQL数据  
    :::image-end:::  
    
## <a name="edit-web-sql-data"></a>编辑 Web SQL数据  

在查看 Web 数据表时SQL编辑 Web SQL数据，如上文所述。  但是，您可以运行来自 Web SQL编辑或删除表的语句。  导航到["运行 Web SQL查询"。](#run-web-sql-queries)  

## <a name="run-web-sql-queries"></a>运行 Web SQL查询  

1.  选择一个数据库以打开该数据库的控制台。  
1.  键入 Web SQL 语句，然后选择 `Enter` 以运行它。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png" alt-text="使用 Web SQL控制台从表中删除行" lightbox="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png":::
       使用 Web SQL控制台从表中删除行  
    :::image-end:::  
    
## <a name="refresh-a-web-sql-table"></a>刷新 Web SQL表  

DevTools 不会实时更新表。  若要更新表中的数据，请完成以下操作。  

1.  [查看 Web 服务表中的SQL数据](#view-web-sql-data)。  
1.  Choose **Refresh** \ (![ Refresh ](../media/refresh-icon.msft.png) \) .  
    
## <a name="filter-out-columns-in-a-web-sql-table"></a>筛选出 Web 数据表中的SQL列  

1.  [查看 Web 服务表中的SQL数据](#view-web-sql-data)。  
1.  使用 **"可见列** "文本框指定要显示哪些列。  将列名称作为 CSV 列表提供。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png" alt-text="使用"可见列"文本框减少显示的列数" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png":::
       使用 **"可见列** "文本框减少显示的列数  
    :::image-end:::  
    
## <a name="delete-all-web-sql-data"></a>删除所有 Web SQL数据  

1.  打开" **清除存储"** 窗格。  
1.  确保 **"Web SQL"** 复选框已打开。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-web-sql.msft.png" alt-text=""Web SQL"复选框" lightbox="../media/storage-application-clear-storage-web-sql.msft.png":::
       "Web **SQL"** 复选框  
    :::image-end:::  
    
1.  选择 **"清除网站数据"。**  
    
    :::image type="complex" source="../media/storage-application-clear-storage-clear-site-data-button.msft.png" alt-text=""清除网站数据"按钮" lightbox="../media/storage-application-clear-storage-clear-site-data-button.msft.png":::
       " **清除网站数据"** 按钮  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  

[W3CWebSQLStatus]: https://w3.org/TR/webdatabase/#status-of-this-document "Web SQL数据库|W3C"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/websql)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
