---
description: 有关打开命令菜单、运行命令、查看其他操作等的指南。
title: 使用开发人员工具Microsoft Edge菜单运行命令
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: b815934da73f9f023629564da7bea14da166ff9b
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519189"
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

# <a name="run-commands-with-the-microsoft-edge-devtools-command-menu"></a>使用开发人员工具Microsoft Edge菜单运行命令  

命令菜单提供了在 DevTools UI Microsoft Edge导航和完成常见任务（如[禁用 JavaScript）的快速方法][JavascriptDisable]。  你可能熟悉命令调色板Microsoft Visual Studio代码中的类似功能，这是命令菜单的原始灵感[][VisualStudioCodeUICommandPalette]。  

:::image type="complex" source="../media/command-menu-run-command-java.msft.png" alt-text="使用命令菜单禁用 JavaScript" lightbox="../media/command-menu-run-command-java.msft.png":::
   使用命令菜单禁用 JavaScript  
:::image-end:::  

## <a name="open-the-command-menu"></a>打开命令菜单  

选择 `Control` + `Shift` + `P` \(Windows、Linux\) 或 `Command` + `Shift` + `P` \(macOS\)。 或选择 **自定义和控制开发工具** \ (`...` \) > **运行命令**。  

:::image type="complex" source="../media/command-menu-options-run-command.msft.png" alt-text="运行命令" lightbox="../media/command-menu-options-run-command.msft.png":::
   运行命令  
:::image-end:::  

## <a name="display-other-available-actions"></a>显示其他可用操作  

如果使用"打开命令菜单"中概述[](#open-the-command-menu)的工作流，"命令菜单"将打开，并预先将字符绘制到"命令菜单 `>` "文本框中。  

:::image type="complex" source="../media/command-menu-run-command.msft.png" alt-text="命令字符" lightbox="../media/command-menu-run-command.msft.png":::
   命令字符  
:::image-end:::  

删除 `>` 字符和类型 `?` 以显示"命令菜单"中提供的其他操作。  

:::image type="complex" source="../media/command-menu-help.msft.png" alt-text="其他可用操作" lightbox="../media/command-menu-help.msft.png":::
   其他可用操作  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[JavascriptDisable]: ../javascript/disable.md "使用开发人员工具Microsoft Edge JavaScript |Microsoft Docs"  

[VisualStudioCodeUICommandPalette]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette "命令调色板 - Visual Studio Code UI"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/command-menu/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
