---
ms.assetid: 1e5c42a7-4604-46ac-ad7b-a65390e5b36a
description: 了解如何在 Microsoft Edge 中构建、设计和测试易于访问的网站。
title: 辅助功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 辅助功能，面向开发人员的辅助功能，辅助网站，边缘，web 开发，ARIA，开发人员，UIA，UI 自动化
ms.openlocfilehash: 6ad95e9c250aa6a4a61ca09470cea86efd715427
ms.sourcegitcommit: 9169d784485e3cb0b1987a8f395c4bb688bd9b2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "10583103"
---
# 辅助功能  

> "\ [T] 他对残疾的影响在网上有了很多变动，因为 Web 在物理世界中消除了许多人面临的沟通和交互障碍。" [ (辅助功能 |W3C) ][W3CAccessibility]  

[世界健康组织][WHODisabilities]将残疾定义为 "一人的身体功能与他们的居住环境的功能之间的交互不匹配"。  残疾范围从形势障碍（如在手机上保持婴儿或明亮的阳光）到其他物理、听觉、视觉或年龄相关障碍等方面的残障人士。  

设计包含的网站和其他技术可使每个人体验愉快。  非独占设计和 web 辅助功能可帮助和帮助每个人使用 web。  

下面是一些最佳做法、代码示例和进一步的资源，可让你了解有关在 Microsoft Edge 中 [设计][AccessibilityDesign]、 [构建][AccessibilityBuild]和 [测试][AccessibilityTest] 易于访问的网站的详细信息。  

## Microsoft Edge 中的辅助功能  

在 Microsoft Edge 中，我们引入了新式 [UI 自动化 API][WindowsWin32AutoEntryui] \ (UIA API \ ) 。  对 UIA 的更改是浏览器辅助功能的主要投资，它为依赖于 Windows 10 中的辅助技术的用户提供了更多包含 web 体验的基础。  用户还将受益于 Chromium 引擎的长绿性质。  

Microsoft Edge 中的辅助功能系统本身支持新式 web 标准，包括 ARIA、HTML5 和 CSS3。  下面的简化的浏览器管道关系图将网页内容置于可访问的演示文稿层中。  

:::image type="complex" source="./media/accessibilityarchitecture.png" alt-text="转换为引擎模型的内容被投影到视觉对象和辅助功能视图中，显示为视觉对象或易于访问的演示文稿":::
   图 1.  转换为引擎模型的内容被投影到视觉对象和辅助功能视图中，显示为视觉对象或易于访问的演示文稿
:::image-end:::

<!--![Figure 1.  Content transformed to the engine model is projected into visual and accessibility views that are presented either as visual or accessible presentation][ImageAccessibilityArchitecture]  -->  

Microsoft Edge 团队不断与 W3C 和其他浏览器供应商协作，以确保新的 web 平台功能具有足够的内置可访问性。  

有关 Microsoft Edge 支持的新 HTML5 功能 accessibly 的信息，请访问 [HTML5Accessibility][HTML5Accessibility]。  

## 资源  

#### Microsoft Windows UI 自动化博客  

[Microsoft WINDOWS UI 自动化博客][ArchiveBlogsWinuiautomation]介绍与 WINDOWS 自动化 API 相关的主题。  

####  (WAI-ARIA 的 Web 辅助功能计划)   

[ (wai-aria 的 Web 辅助功能计划) ][W3CWaiHome]提供了 BT，W3C 是帮助改进 Web 辅助功能的一项努力。  网站提供了各种资源来 [开始使用 Web 辅助功能][W3CWaiGettingstartedOverview]、 [设计包含][W3CWaiFundamentals]、 [教程和演示文稿][W3CWaiTeachAdvocate]等。  


<!-- image links -->  

<!--[ImageAccessibilityArchitecture]: ./media/accessibilityarchitecture.png &quot;Figure 1: Content transformed to the engine model is projected into visual and accessibility views that are presented either as visual or accessible presentation&quot;  -->  

<!-- links -->  

[AccessibilityBuild]: ./accessibility/build.md &quot;构建易于访问的网站&quot;  
[AccessibilityDesign]: ./accessibility/design.md &quot;设计易于访问的网站&quot;  
[AccessibilityTest]: ./accessibility/test.md &quot;辅助功能测试&quot;  

[WindowsWin32AutoEntryui]: /windows/win32/winauto/entry-uiauto-win32 &quot;UI 自动化&quot;  

[ArchiveBlogsWinuiautomation]: /archive/blogs/winuiautomation/ &quot;Microsoft Windows UI 自动化博客&quot;  

[HTML5Accessibility]: https://html5accessibility.com &quot;HTML5 辅助功能&quot;  

[W3CAccessibility]: https://w3.org/standards/webdesign/accessibility &quot;辅助功能 |W3C&quot;  
[W3CWaiFundamentals]: https://w3.org/wai/fundamentals/accessibility-intro &quot;Web 辅助功能简介 |Web 辅助功能计划 (WAI-ARIA) |W3C&quot;  
[W3CWaiGettingstartedOverview]: https://w3.org/wai/gettingstarted/Overview &quot;入门：使网站易于访问 |Web 辅助功能计划 (WAI-ARIA) |W3C&quot;  
[W3CWaiHome]: https://w3.org/wai &quot;Web 辅助功能计划 (WAI-ARIA) |W3C&quot;  
[W3CWaiTeachAdvocate]: https://w3.org/wai/teach-advocate &quot;教授和提倡概述 |Web 辅助功能计划 (WAI-ARIA) |W3C&quot;  

[WHODisabilities]: https://who.int/topics/disabilities &quot;残疾 |填写"  

