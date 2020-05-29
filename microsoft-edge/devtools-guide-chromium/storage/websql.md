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





# 通过 Microsoft Edge DevTools 查看 Web SQL 数据   



> [!WARNING]
> [未保留][W3CWebSQLStatus]Web SQL 规范。  

本指南介绍如何使用[Microsoft Edge DevTools][MicrosoftEdgeDevTools]检查 Web SQL 数据。  

## 查看 Web SQL 数据   

1.  选择 "**源**" 选项卡以打开 "**源**" 面板。  默认情况下，**清单**窗格是默认打开的。  
    
    > ##### 图 1  
    > 清单窗格  
    > ![清单窗格][ImageManifestPane]  
    
1.  展开**WEB SQL**部分以查看数据库和表。  在**html5meetup**下方的[图 2](#figure-2)中，数据库和**会议室**是一个表。  
    
    > ##### 图 2  
    > Web SQL 窗格  
    > ![Web SQL 窗格][ImageWebSQLPane]  

1.  选择一个表以查看该表的数据。  
    
    > ##### 图 3  
    > 查看**聊天室**Web SQL 表的数据  
    > ![查看 Web SQL 表的数据][ImageWebSQLTable]  

## 编辑 Web SQL 数据   

查看 Web SQL 表时，您无法编辑 Web SQL 数据，如上面的**图 3**所示。  但是，你可以从编辑或删除表的 Web SQL 控制台运行语句。  请参阅[运行 WEB SQL 查询](#run-web-sql-queries)。  

## 运行 Web SQL 查询   

1.  选择一个数据库以打开该数据库的控制台。  

1.  键入 Web SQL 语句，然后按 `Enter` 运行它。  
    
    > ##### 图 4  
    > 使用 Web SQL 控制台删除**会议室**表中的行  
    > ![使用 Web SQL 控制台删除表中的行][ImageWebSQLEdit]  

## 刷新 Web SQL 表   

DevTools 不会实时更新表。  更新表中的数据：  

1.  [查看 WEB SQL 表中的数据](#view-web-sql-data)。  
1.  选择 "**刷新** ![ 刷新" ][ImageRefreshIcon] 。  

## 筛选出 Web SQL 表中的列   

1.  [查看 WEB SQL 表中的数据](#view-web-sql-data)。  
1.  使用 "**可见列**" 文本框指定要显示的列。  以 CSV 列表的形式提供列名称。  
    
    > ##### 图 5  
    > 使用 "**可见列**" 文本框仅显示 " `room_name` 和" `last_updated` 列  
    > ![使用 "可见列" 文本框减少显示的列数][ImageWebSQLFilter]  

## 删除所有 Web SQL 数据   

1.  打开 "**清除存储**" 窗格。  
1.  请确保 " **WEB SQL** " 复选框已启用。  
    
    > ##### 图 6  
    > " **WEB SQL** " 复选框  
    > !["Web SQL" 复选框][ImageWebSQLCheckbox]  

1.  选择 "**清除网站数据**"。  
    
    > ##### 图 7  
    > "**清除网站数据**" 按钮  
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
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/websql)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
