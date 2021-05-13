---
description: 自定义开发人员工具Microsoft Edge列表
title: 自定义 Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 0be3219579794dca28f71e336da1154f31f2d2be
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564383"
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
# <a name="customize-microsoft-edge-devtools"></a>自定义 Microsoft Edge DevTools  

此页面列出了自定义 DevTools Microsoft Edge的方法。  

## <a name="settings"></a>“设置”  

**设置**  > **首选项**包含许多用于自定义 DevTools 的选项。  

若要打开设置，请完成以下操作之一。  

*   在 `F1` DevTools 成为焦点时选择。  
*   打开主**菜单，** 然后选择 **"设置"。**  
    
:::image type="complex" source="../media/customize-settings-preferences.msft.png" alt-text="设置" lightbox="../media/customize-settings-preferences.msft.png":::
   **设置**  
:::image-end:::  

## <a name="drawer"></a>"箱"  

The **Drawer** is a second panel where your choosing tools are displayed.  

若要打开 \ (或 close\) **收银机，** 请选择 `Escape` 。  

:::image type="complex" source="../media/customize-drawer-open.msft.png" alt-text="The Drawer" lightbox="../media/customize-drawer-open.msft.png":::
   The **Drawer**  
:::image-end:::  

默认情况下，某些工具在主面板中打开，而其他工具显示在"箱 **"中**。  选择 **"更多** \ (`...` \) "以在"箱"中打开 **工具**。  

:::image type="complex" source="../media/customize-drawer-open-more-tools.msft.png" alt-text="用于打开"箱"的按钮" lightbox="../media/customize-drawer-open-more-tools.msft.png":::
   用于打开"箱 **"的按钮**  
:::image-end:::  

您可以在主面板和箱之间移动工具。  

*   若要将工具从工具箱移动到主面板，请将鼠标悬停在工具上，打开上下文菜单 \ (右键单击\) 然后选择"移动到**顶部"。**  
    
    :::image type="complex" source="../media/move-from-drawer.msft.png" alt-text="将工具从"箱"移到主面板" lightbox="../media/move-from-drawer.msft.png":::
       将工具从 **"箱"** 移到主面板  
    :::image-end:::  
    
*   若要将工具从主面板移动到箱中，请将鼠标悬停在工具上，打开上下文菜单 \ (右键单击\) 然后选择"移动到**底部"。**  
    
    :::image type="complex" source="../media/move-to-drawer.msft.png" alt-text="将工具从主面板移动到"箱"" lightbox="../media/move-to-drawer.msft.png":::
       将工具从主面板移动到"箱 **"**
    :::image-end:::  
    

## <a name="reorder-panels"></a>对面板重新排序  

选择并拖动工具以更改排序。  你的自定义工具顺序在整个 DevTools 会话中持续存在。  

> [!NOTE]
> 默认情况下， **网络工具** 通常是左侧的第四个工具。  下图中的 **"网络"** 工具是左侧的第一个工具。  

:::image type="complex" source="../media/customize-network-first-position.msft.png" alt-text="面板中 Devtools 的自定义顺序" lightbox="../media/customize-network-first-position.msft.png":::
   面板中 Devtools 的自定义顺序  
:::image-end:::  

## <a name="change-devtools-placement"></a>更改 DevTools 位置  

导航到[Microsoft Edge开发人员工具放置][DevToolsPlacement]" 。  

:::image type="complex" source="../media/customize-dev-tools-dock-side.msft.png" alt-text="移除的开发人员工具" lightbox="../media/customize-dev-tools-dock-side.msft.png":::
   移除的开发人员工具  
:::image-end:::  

## <a name="dark-theme"></a>深色主题  

导航到 [启用深色主题][DarkTheme]。  

:::image type="complex" source="../media/customize-settings-appearance-theme.msft.png" alt-text="深色主题" lightbox="../media/customize-settings-appearance-theme.msft.png":::
   深色主题  
:::image-end:::  

## <a name="experiments"></a>试验  

若要打开 DevTools 实验，请完成以下操作。  

1.  导航到 `edge://flags/#enable-devtools-experiments`。  
1.  选择"**启用"。**  
1.  选择 **页面底部的"现在**重新启动"。  

下次打开 DevTools 时，名为 **"** 实验"的新页面[将显示在设置。](#settings)  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreIcon]: ../media/more-icon.msft.png  

<!-- links -->  

[DevToolsPlacement]: ./placement.md "更改 Microsoft Edge DevTools 放置 | Microsoft Docs"  
[DarkTheme]: ./dark-theme.md "在 DevTools Microsoft Edge中启用深色|Microsoft Docs"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/customize/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
