---
title: 通过 Microsoft Edge DevTools 禁用 JavaScript
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: f3838b4e8eccf83aaa71be35ff477ec56cbe7455
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581808"
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





# 通过 Microsoft Edge DevTools 禁用 JavaScript   



若要查看在禁用 JavaScript 时网页的外观和行为，请执行以下操作：  

1.  [打开 Microsoft Edge DevTools][DevToolsOpen]。  
1.  按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "**命令" 菜单**。  
    
    > ##### 图 1  
    > 命令菜单  
    > ![命令菜单][ImageCommandMenu]  
    
1.  开始键入 `javascript` ，选择 "**禁用 JavaScript**"，然后按 `Enter` 运行命令。  JavaScript 现在已被禁用。  
    
    > ##### 图 2  
    > 在 "命令" 菜单中选择 "**禁用 JavaScript** "  
    > ![在 "命令" 菜单中选择 "禁用 JavaScript"][ImageDisableJS]  
    
    "**来源**" 旁边的黄色警告图标会提醒你已禁用 JavaScript。  
    
    > ##### 图 3  
    > "**源**" 旁边的 "警告" 图标  
    > !["源" 旁边的 "警告" 图标][ImageDisableJSWarning]  

只要您已打开 DevTools，JavaScript 就会在此选项卡中保持禁用状态。  

你可能需要重新加载页面以查看页面是否以及页面在加载时是否依赖 JavaScript。  

要重新启用 JavaScript，请执行以下操作：  

*   再次打开 "**命令" 菜单**并运行 `Enable JavaScript` 命令。  
*   关闭 DevTools。  

## 反馈   



<!-- image links -->  

[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/javascript-console-command.msft.png "图1：命令菜单"  
[ImageDisableJS]: /microsoft-edge/devtools-guide-chromium/media/javascript-console-command-javascript.msft.png "图2：在 "命令" 菜单中选择 "禁用 JavaScript""  
[ImageDisableJSWarning]: /microsoft-edge/devtools-guide-chromium/media/javascript-console-javascript-disabled-warning.msft.png "图3： "源" 旁边的 "警告" 图标"  

<!-- links -->  

[DevToolsOpen]: ../open.md "打开 Microsoft Edge DevTools"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/disable)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
