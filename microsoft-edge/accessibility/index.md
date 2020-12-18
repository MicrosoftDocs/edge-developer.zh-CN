---
description: 了解如何在 Microsoft Edge 内构建、设计和测试可访问的网站。
title: 辅助功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: 1e5c42a7-4604-46ac-ad7b-a65390e5b36a
keywords: 辅助功能， 开发人员辅助功能， 可访问的网站， 边缘， Web 开发， ARIA， 开发人员， UIA， UI 自动化
ms.openlocfilehash: ae2b0a876b60e0475e283cc52ffd14275fc32aba
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232174"
---
# 辅助功能概述  

> "\[T\]他对残障的影响在 Web 上发生了根本改变，因为 Web 消除了许多人在物理世界面临的通信和交互障碍。" [ (辅助功能 |W3C) ][W3CAccessibility]  

世界 [健康组织][WHODisabilities] 将残障定义为"个人正文功能与其生活环境的功能之间的交互不匹配"。  残障范围从情境式残障（如行动不便，同时在电话上长着一只孩子或明亮眼睛）到其他残障、听觉障碍、视觉障碍或与年龄相关的障碍。  

设计网站和其他包含技术可打造每个人都享受的体验。  非独占设计和 Web 辅助功能使每个人都能够使用 Web。  

下面是一些最佳做法、代码示例和进一步的资源，可让你了解有关在 Microsoft [][AccessibilityDesign]Edge 中设计、[][AccessibilityTest][构建][AccessibilityBuild]和测试可访问网站的信息。  

## Microsoft Edge 中的辅助功能  

在 Microsoft Edge 中，我们引入了现代 [UI 自动化 API][WindowsWin32AutoEntryui] \ (UIA API\) 。  对 UIA 的变更是浏览器辅助功能的主要投资，它为依赖 Windows 10 中的辅助技术的用户提供更具包容性的 Web 体验打下基础。  用户还可以从 Chromium 引擎的常青特性中获益。  

Microsoft Edge 中的辅助功能系统本身支持现代 Web 标准，包括 ARIA、HTML5 和 CSS3。  简化的浏览器管道的下图将网页内容放入可访问的表示层。  

:::image type="complex" source="./media/accessibilityarchitecture.png" alt-text="转换为引擎模型的内容将转换为可视和辅助功能视图，这些视图以可视或辅助演示文稿形式呈现":::
   转换为引擎模型的内容将转换为可视和辅助功能视图，这些视图以可视或辅助演示文稿形式呈现  
:::image-end:::  

Microsoft Edge 团队与 W3C 和其他浏览器供应商持续合作，以确保新的 Web 平台功能具有足够的内置辅助功能。  

有关 Microsoft Edge 支持哪些新 HTML5 功能的信息，请导航到[HTML5Accessibility。][HTML5Accessibility]  

## 资源  

#### Microsoft Windows UI 自动化博客  

[Microsoft Windows UI 自动化博客][ArchiveBlogsWinuiautomation]涵盖与 Windows 自动化 API 相关的主题。  

#### WEB 辅助功能计划 (或)   

Web [辅助功能计划 (或) BT ][W3CWaiHome] 的一项操作，它旨在帮助改进 Web 的辅助功能。  该网站为 Web 辅助功能入门、[][W3CWaiGettingstartedOverview]包含设计、教程和[演示文稿][W3CWaiTeachAdvocate]等[][W3CWaiFundamentals]提供了各种资源。  

<!-- links -->  

[AccessibilityBuild]: ./build/index.md "构建可访问的网站 |Microsoft Doc"  
[AccessibilityDesign]: ./design.md "正在设计可访问的网站 |Microsoft Doc"  
[AccessibilityTest]: ./test.md "辅助功能测试 |Microsoft Docs"  

[WindowsWin32AutoEntryui]: /windows/win32/winauto/entry-uiauto-win32 "UI 自动化 |Microsoft Doc"  

[ArchiveBlogsWinuiautomation]: /archive/blogs/winuiautomation/ "Microsoft Windows UI 自动化博客 |Microsoft Doc"  

[HTML5Accessibility]: https://html5accessibility.com "HTML5 辅助功能"  

[W3CAccessibility]: https://w3.org/standards/webdesign/accessibility "辅助功能 |W3C"  
[W3CWaiFundamentals]: https://w3.org/wai/fundamentals/accessibility-intro "Web 辅助功能简介 |WEB 辅助功能计划 (或) |W3C"  
[W3CWaiGettingstartedOverview]: https://w3.org/wai/gettingstarted/Overview "入门：使网站成为辅助网站 |WEB 辅助功能计划 (或) |W3C"  
[W3CWaiHome]: https://w3.org/wai "WEB 辅助功能计划 (或) |W3C"  
[W3CWaiTeachAdvocate]: https://w3.org/wai/teach-advocate "教学和宣传概述 |WEB 辅助功能计划 (或) |W3C"  

[WHODisabilities]: https://who.int/topics/disabilities "残障 |WHO"  

