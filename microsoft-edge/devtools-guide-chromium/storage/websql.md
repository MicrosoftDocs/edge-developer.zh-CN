---
description: 如何从 Microsoft Edge DevTools 的 "应用程序" 面板查看 Web SQL 数据。
title: 通过 Microsoft Edge DevTools 查看 Web SQL 数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 0396a00ec354fdd707bc4d484242d4cf844db5f9
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125466"
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

# 通过 Microsoft Edge DevTools 查看 Web SQL 数据  

> [!WARNING]
> [未保留][W3CWebSQLStatus]Web SQL 规范。  

本指南介绍如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 检查 Web SQL 数据。  

## 查看 Web SQL 数据  

1.  选择 " **源** " 选项卡以打开 " **源** " 面板。  默认情况下， **清单** 窗格是默认打开的。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       **清单**窗格  
    :::image-end:::  
    
1.  展开 **WEB SQL** 部分以查看数据库和表。  下图中， **html5meetup** 下方是一个数据库， **房间** 是一个表。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-web-sql.msft.png":::
       **WEB SQL**窗格  
    :::image-end:::  
    
1.  选择一个表以查看该表的数据。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png":::
       查看 Web SQL 表的数据  
    :::image-end:::  
    
## 编辑 Web SQL 数据  

查看 Web SQL 表时，您无法编辑 Web SQL 数据，如上面的 **图 3** 所示。  但是，你可以从编辑或删除表的 Web SQL 控制台运行语句。  请参阅 [运行 WEB SQL 查询](#run-web-sql-queries)。  

## 运行 Web SQL 查询  

1.  选择一个数据库以打开该数据库的控制台。  
1.  键入 Web SQL 语句，然后选择 `Enter` 运行它。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png":::
       使用 Web SQL 控制台删除表中的行  
    :::image-end:::  
    
## 刷新 Web SQL 表  

DevTools 不会实时更新表。  更新表中的数据：  

1.  [查看 WEB SQL 表中的数据](#view-web-sql-data)。  
1.  选择 " **刷新** \ (![ 刷新 ][ImageRefreshIcon] \ ) "。  
    
## 筛选出 Web SQL 表中的列  

1.  [查看 WEB SQL 表中的数据](#view-web-sql-data)。  
1.  使用 " **可见列** " 文本框指定要显示的列。  以 CSV 列表的形式提供列名称。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png":::
       使用 " **可见列** " 文本框减少显示的列数  
    :::image-end:::  
    
## 删除所有 Web SQL 数据  

1.  打开 " **清除存储** " 窗格。  
1.  请确保 " **WEB SQL** " 复选框已启用。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-web-sql.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-clear-storage-web-sql.msft.png":::
       " **WEB SQL** " 复选框  
    :::image-end:::  
    
1.  选择 " **清除网站数据**"。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-clear-site-data-button.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-clear-storage-clear-site-data-button.msft.png":::
       " **清除网站数据** " 按钮  
    :::image-end:::  
    
## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  

[W3CWebSQLStatus]: https://w3.org/TR/webdatabase/#status-of-this-document "Web SQL 数据库 |W3C"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/websql)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
