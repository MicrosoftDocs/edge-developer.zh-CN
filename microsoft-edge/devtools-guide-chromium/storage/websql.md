---
description: 如何通过 Web SQL Microsoft Edge DevTools 的应用程序面板的 Web SQL 数据。
title: 使用 Microsoft Edge DevTools 查看 Web SQL 数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge，web 开发，f12 工具，devtools
ms.openlocfilehash: bc25f7422be19bec99bde1cd7764f08aad8e6668
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564698"
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
# <a name="view-web-sql-data-with-microsoft-edge-devtools"></a>使用 Microsoft Edge DevTools 查看 Web SQL 数据  

> [!WARNING]
> Web SQL 规范[未得到维护][W3CWebSQLStatus]。  

本指南将演示如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 检查 Web SQL 数据。  

## <a name="view-web-sql-data"></a>查看 Web SQL 数据  

1.  选择 **源**工具以打开**源**工具。  通常默认**清单**窗格打开。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       **清单**窗格  
    :::image-end:::  
    
1.  展开 **Web SQL** 部分以查看数据库和表。  在下图中，**html5meetup** 下方是数据库，**子表**是表。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql.msft.png" alt-text="Web SQL 窗格" lightbox="../media/storage-application-storage-web-sql.msft.png":::
       **Web SQL** 窗格  
    :::image-end:::  
    
1.  选择一个表以查看该表的数据。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png" alt-text="查看 Web SQL 表的数据" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png":::
       查看 Web SQL 表的数据  
    :::image-end:::  
    
## <a name="edit-web-sql-data"></a>编辑 Web SQL 数据  

如上文所述，在查看 Web SQL 表时不能编辑 Web SQL 数据。  但是，您可以通过编辑或删除表的 Web SQL 控制台运行语句。  导航到[运行 Web SQL 查询](#run-web-sql-queries)。  

## <a name="run-web-sql-queries"></a>运行 Web SQL 查询  

1.  选择数据库以打开该数据库的控制台。  
1.  键入 Web SQL 语句，然后选择 `Enter` 进行运行。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png" alt-text="使用 Web SQL 控制台删除表中的行" lightbox="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png":::
       使用 Web SQL 控制台删除表中的行  
    :::image-end:::  
    
## <a name="refresh-a-web-sql-table"></a>刷新 Web SQL 表  

DevTools 不会实时更新表。  若要更新表中的数据，请完成以下操作。  

1.  [查看 Web SQL 表中的数据](#view-web-sql-data)。  
1.  选择**刷新** \(![Refresh](../media/refresh-icon.msft.png)\)。  
    
## <a name="filter-out-columns-in-a-web-sql-table"></a>筛选 Web SQL 表中的列  

1.  [查看 Web SQL 表中的数据](#view-web-sql-data)。  
1.  使用**可见列**文本框指定要显示的列。  使用 CSV 列表提供列的名称。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png" alt-text="使用可见列文本框减少显示的列数" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png":::
       使用 **可见列**文本框减少显示的列数  
    :::image-end:::  
    
## <a name="delete-all-web-sql-data"></a>删除所有的 Web SQL 数据  

1.  打开**清除存储**窗格。  
1.  确保 **Web SQL** 复选框已打开。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-web-sql.msft.png" alt-text="Web SQL 复选框" lightbox="../media/storage-application-clear-storage-web-sql.msft.png":::
       **Web SQL** 复选框  
    :::image-end:::  
    
1.  选择**清除网站数据**。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-clear-site-data-button.msft.png" alt-text="清除网站数据按钮" lightbox="../media/storage-application-clear-storage-clear-site-data-button.msft.png":::
       **清除网站数据**按钮  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  

[W3CWebSQLStatus]: https://w3.org/TR/webdatabase/#status-of-this-document "Web SQL 数据库 | W3C"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/websql)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
