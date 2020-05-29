---
title: 通过 Microsoft Edge DevTools 命令菜单运行命令
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 748008b347a3498008748b9c3f9ecc1445c47f12
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601745"
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





# 通过 Microsoft Edge DevTools 命令菜单运行命令   

  

命令菜单提供了一种快速浏览 Microsoft Edge DevTools UI 和完成常见任务（如[禁用 JavaScript][JavascriptDisable]）的方法。  你可能会熟悉 Visual Studio 代码中称为[命令调色板][VisualStudioCodeUICommandPalette]的类似功能，这是命令菜单的初始灵感。  

> ##### 图 1  
> 使用 "命令" 菜单禁用 JavaScript  
> ![使用 "命令" 菜单禁用 JavaScript][ImageDisableJS]  

## 打开 "命令" 菜单   

按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）。 或者单击 "**自定义和控制 DevTools** " `...` ，然后选择 "**运行命令**"。  

> ##### 图 2  
> 运行命令  
> ![运行命令][ImageRunCommand]  

## 查看其他可用操作   

如果您使用 "[打开命令" 菜单](#open-the-command-menu)中所述的工作流，则 "命令" 菜单将打开，其中包含一个 `>` 字符预置到 "命令菜单" 文本框。  

> ##### 图 3  
> 命令字符  
> ![命令字符][ImageCommandCharacter]  

删除 " `>` 字符" 和 "类型"， `?` 以查看 "命令" 菜单中提供的其他操作。  

> ##### 图 4  
> 其他可用操作  
> ![其他可用操作][ImageActions]  

 



<!-- image links -->  

[ImageDisableJS]: /microsoft-edge/devtools-guide-chromium/media/command-menu-run-command-java.msft.png "图1：使用 "命令" 菜单禁用 JavaScript"  
[ImageRunCommand]: /microsoft-edge/devtools-guide-chromium/media/command-menu-options-run-command.msft.png "图2：运行命令"  
[ImageCommandCharacter]: /microsoft-edge/devtools-guide-chromium/media/command-menu-run-command.msft.png "图3：命令字符"  
[ImageActions]: /microsoft-edge/devtools-guide-chromium/media/command-menu-help.msft.png "图4：其他可用操作"  

<!-- links -->  

[JavascriptDisable]: /microsoft-edge/devtools-guide-chromium/javascript/disable "通过 Microsoft Edge DevTools 禁用 JavaScript"  

[VisualStudioCodeUICommandPalette]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette "命令调色板-Visual Studio 代码 UI"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/command-menu/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
