---
description: 有关如何打开 "命令" 菜单、"运行命令"、"查看其他操作" 等的指南。
title: 使用 Microsoft Edge 开发人员工具命令菜单运行命令
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 2f13461fdf04e034b324db63c6ec6d9090f80f50
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125277"
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

# 使用 Microsoft Edge 开发人员工具命令菜单运行命令  

  

命令菜单提供了一种快速浏览 Microsoft Edge DevTools UI 和完成常见任务（如 [禁用 JavaScript][JavascriptDisable]）的方法。  你可能会熟悉 Visual Studio 代码中称为 [命令调色板][VisualStudioCodeUICommandPalette]的类似功能，这是命令菜单的初始灵感。  

:::image type="complex" source="../media/command-menu-run-command-java.msft.png" alt-text="使用 &quot;命令&quot; 菜单禁用 JavaScript" lightbox="../media/command-menu-run-command-java.msft.png":::
   使用 "命令" 菜单禁用 JavaScript  
:::image-end:::  

## 打开 "命令" 菜单  

选择 `Control` + `Shift` + `P` \ (Windows、Linux \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 。 或选择 " **自定义和控制 DevTools** " `...` ，然后选择 " **运行命令**"。  

:::image type="complex" source="../media/command-menu-options-run-command.msft.png" alt-text="使用 &quot;命令&quot; 菜单禁用 JavaScript" lightbox="../media/command-menu-options-run-command.msft.png":::
   运行命令  
:::image-end:::  

## 查看其他可用操作  

如果您使用 " [打开命令" 菜单](#open-the-command-menu)中所述的工作流，则 "命令" 菜单将打开，其中有一个 `>` 预挂起的字符到 "命令菜单" 文本框。  

:::image type="complex" source="../media/command-menu-run-command.msft.png" alt-text="使用 &quot;命令&quot; 菜单禁用 JavaScript" lightbox="../media/command-menu-run-command.msft.png":::
   命令字符  
:::image-end:::  

删除 " `>` 字符" 和 "类型"， `?` 以查看 "命令" 菜单中提供的其他操作。  

:::image type="complex" source="../media/command-menu-help.msft.png" alt-text="使用 &quot;命令&quot; 菜单禁用 JavaScript" lightbox="../media/command-menu-help.msft.png":::
   其他可用操作  
:::image-end:::  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[JavascriptDisable]: ../javascript/disable.md "通过 Microsoft Edge DevTools 禁用 JavaScript |Microsoft 文档"  

[VisualStudioCodeUICommandPalette]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette "命令调色板-Visual Studio 代码 UI"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/command-menu/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
