---
title: 自定义 Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f34f2e3c02b0c66ee02f4810827f3adb51a60abc
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882742"
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





# 自定义 Microsoft Edge DevTools   

  

此页面列出了自定义 Microsoft Edge DevTools 的方法。  

## “设置”   

**设置**  > **首选项**包含用于自定义 DevTools 的许多选项。  

若要打开 "设置"，请执行下列操作之一：  

*   `F1`当 DevTools 处于焦点时按下。  
*   打开**主菜单**，然后选择 "**设置**"。  

> ##### 图 1  
> 设置  
> ![设置][ImageSettings]  

## 箱   

**抽屉**包含许多隐藏的功能。  

按 " `Escape` 打开" 或 "关闭" 抽屉。  

> ##### 图 2  
> 抽屉  
> ![抽屉][ImageDrawerExample]  

单击 "**更** ![ 多" ][ImageMoreIcon] 以打开其他抽屉选项卡。  

> ##### 图 3  
> 用于打开抽屉卡舌的按钮  
> ![用于打开抽屉卡舌的按钮][ImageMoreDrawerTabs]  

## 重新排序面板   

单击并拖动 "面板" 选项卡以更改其排序。  您的自定义 tab 键顺序在 DevTools 会话中保持不变。  

> [!NOTE]
> 默认情况下，"网络面板" 选项卡通常是从左侧起的第四个选项卡。  在[图 4](#figure-4)中，它是第一个左侧。  

> ##### 图 4  
> 具有自定义 tab 键顺序的 DevTools 窗口    
> ![具有自定义面板选项卡排序的 DevTools 窗口][ImageCustomTabOrdering]  

## 更改 DevTools 位置   

请参阅[Microsoft Edge DevTools 放置][DevToolsPlacement]。  

> ##### 图 5  
> 取消停靠 DevTools  
> ![取消停靠 DevTools][ImageUndock]  

## 深色主题   

请参阅[启用深色主题][DarkTheme]。  

> ##### 图 6  
> 深色主题  
> ![深色主题][ImageDarkTheme]  

## 试验   

要启用 DevTools 实验，请执行以下操作：  

1.  转到 `edge://flags/#enable-devtools-experiments` 。  
1.  单击**启用**。  
1.  单击页面底部的 "**立即重新启动**"。  

下次打开 DevTools 时，将在 "[设置](#settings)" 中显示一个名为 "**实验**" 的新页面。  

   

  

<!-- image links -->  

[ImageMoreIcon]: /microsoft-edge/devtools-guide-chromium/media/more-icon.msft.png  

[ImageSettings]: /microsoft-edge/devtools-guide-chromium/media/customize-settings-preferences.msft.png "图1：设置"  
[ImageDrawerExample]: /microsoft-edge/devtools-guide-chromium/media/customize-drawer-open.msft.png "图2：抽屉"  
[ImageMoreDrawerTabs]: /microsoft-edge/devtools-guide-chromium/media/customize-drawer-open-more-tools.msft.png "图3：用于打开抽屉卡舌的按钮"  
[ImageCustomTabOrdering]: /microsoft-edge/devtools-guide-chromium/media/customize-network-first-position.msft.png "图4：具有自定义面板选项卡排序的 DevTools 窗口"  
[ImageUndock]: /microsoft-edge/devtools-guide-chromium/media/customize-dev-tools-dock-side.msft.png "图5：未插接 DevTools"  
[ImageDarkTheme]: /microsoft-edge/devtools-guide-chromium/media/customize-settings-appearance-theme.msft.png "图6：深色主题"  

<!-- links -->  

[DevToolsPlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "更改 Microsoft Edge DevTools 位置（"取消停靠"、"停靠到底部"、"停靠到左侧"）"  
[DarkTheme]: /microsoft-edge/devtools-guide-chromium/customize/dark-theme "在 Microsoft Edge DevTools 中启用深色主题"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/customize/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
