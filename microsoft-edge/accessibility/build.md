---
ms.assetid: 1b3ebc25-d023-4f23-bbba-dce066c20de8
description: 介绍最佳做法和易于访问的富互联网应用程序（ARIA）如何能够创建易于访问的网站。
title: 辅助功能-构建
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 辅助功能，面向开发人员的辅助功能，辅助网站，边缘，web 开发，ARIA，开发人员，UIA，UI 自动化
ms.custom: seodec18
ms.openlocfilehash: 4412fef6bb78b5a393ccafd5a2cfa79aba223141
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562611"
---
# 构建易于访问的网站
Web 使用 HTML、CSS 和 JavaScript 的组合生成了动态、复杂的网站、应用程序和用户界面。  但是，如果在设计和构建时不考虑辅助功能，则依赖[辅助技术](https://webaim.org/articles/motor/assistive)浏览 web 的用户很难使用这些复杂的网站。 构建残疾人士易于访问的网站需要有关用户界面的语义信息。 这允许辅助技术（如屏幕阅读器）传达必要的信息，以帮助具有各种功能的人员使用该网站。

有关 Microsoft Edge 支持的新 HTML5 功能 accessibly 的信息，请访问[HTML5Accessibility](https://html5accessibility.com) 。

## 辅助功能的工作原理

辅助技术添加了计算机通常不具备的功能。 例如，视觉障碍的用户可能将其键盘与辅助技术（如屏幕阅读器）结合使用，而不是使用鼠标和屏幕直接使用浏览器。 对于 Microsoft 平台和 web 上的应用程序，辅助技术与 Microsoft [UI 自动化](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx)、特定于应用程序的对象模型（如 microsoft Edge 中的文档对象模型（DOM）或这些对象的组合）交互。

对于 web 开发人员，某些 HTML 元素映射到 UI 自动化对象，因此在选择这些 HTML 元素时，开发人员可以使用内置于这些元素的辅助功能属性和事件。 在开发网站时，通常只需考虑确保 API 正确写入（或指定了相应的元素），才能使应用程序易于访问。 有关详细信息，请查看[Microsoft Edge 中的 ARIA 和 UI 自动化](./build/ARIA-and-UI-Automation.md)。  有关易于访问的通用 Windows 平台（UWP）应用的信息，请参阅 Windows 开发人员中心中的 "[辅助功能](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility)" 主题。

可通过良好的编码实践解决动态内容的许多常见辅助功能问题，并且[WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629)文档包含许多技术和最佳做法，可帮助你创建更易于访问的动态 web 应用程序。 但是，即使正确编码，也不一定可以访问动态内容。 [易于访问的富互联网应用程序（ARIA）](#aria)可帮助解决此问题。  

有关 web 辅助功能的详细信息，请参阅[Web 辅助功能计划](https://www.w3.org/WAI/)（wai-aria）的[Web 辅助功能简介](https://www.w3.org/WAI/intro/accessibility.php)。

## ARIA
W3C's [Web 辅助功能计划](https://www.w3.org/WAI/)的[辅助功能丰富的 Internet 应用程序](https://www.w3.org/TR/wai-aria/)（ARIA）规范定义为使动态 Web 内容和自定义用户界面可供所有人访问的语法。 ARIA 通过使用用于传递自定义语义的其他属性（角色、属性和状态）来扩展 HTML。 浏览器使用这些属性将控件的状态和角色传递给辅助功能 API。

### 角色、属性和状态
在使用属性的元素上设置 ARIA 角色， [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) 以提供有关元素的辅助技术和辅助功能 api 信息。 例如，以下 `<li>` 元素被分配 `role="menuitem"` 为表示它是菜单中的项目。

``` html
<li role="menuitem">Home</li>
```

ARIA 状态和属性是 aria 的前缀属性，提供有关对象的特定信息，以帮助形成角色性质的定义。 属性是对象本质所必需的属性，如 [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) 和 [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx) 。 更改属性会影响对象的含义。 在下面的示例中， `aria-haspopup="true"` 将在菜单项上设置属性 `<li>` 以表示它具有弹出窗口。

``` html
<li role="menuitem" aria-haspopup="true">Open</li>
```

状态不会更改对象的性质，而是表示与对象或与对象的用户交互相关联的信息，如 [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) 或 [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx) 。 例如， `aria-checked="false"` 以下示例中的状态表示未选中复选框。

``` html
<div role="checkbox" aria-checked="false">Accept</div>
```

通过 W3C 转到["角色" 模型](https://www.w3.org/TR/wai-aria-1.1/#roles)以查看角色、属性和状态的完整列表。

有关 ARIA 的详细信息，请参阅 "[资源](#resources)" 部分中的 ARIA。

## 资源

### 辅助功能基础知识
#### [A11Y 项目](http://a11yproject.com/)
A11Y 项目是社区驱动的工作，使 web 辅助功能更易于使用。 查看[A11Y 项目](https://a11yproject.com/)网站，了解基本辅助功能原则、其易于访问的模式和小组件[库](https://a11yproject.com/patterns)以及它们在辅助功能软件、博客、书籍和工具上的[资源](http://a11yproject.com/resources.html)。

#### [Web 辅助功能计划（WAI-ARIA）](https://w3.org/WAI/)
W3C's Web 辅助功能计划（WAI-ARIA）是帮助改进 Web 辅助功能的一项工作。 他们的网站提供了各种资源来[开始使用 Web 辅助功能](https://www.w3.org/WAI/gettingstarted/Overview.html)，[设计包括 "包含](https://www.w3.org/WAI/users/Overview.html)"、"[教程" 和 "演示文稿](https://www.w3.org/WAI/train.html)" 等。

### 辅助功能博客
#### [Paciello 组](https://www.paciellogroup.com/blog/)
Paciello 组为全球各地的组织提供咨询和技术解决方案，以确保客户能够有效、高效地访问所有受众，同时满足政府和国际标准。 其博客介绍诸如 web 辅助功能最佳做法、辅助功能工具和辅助功能趋势等主题。

#### [轻松访问](http://simplyaccessible.com/articles/)
简单的辅助功能是一组辅助功能专家团队，可提供辅助功能培训、咨询以及更多更改 web 上的辅助功能的感觉。 他们的[文章](http://simplyaccessible.com/articles/)部分讨论了 web 辅助功能、易于访问的设计等的最佳做法。

#### [SSB 邓团体（SSB）](http://www.ssbbartgroup.com/blog/)
SSB 邓 Group 是一个数字辅助公司，支持其客户开发和部署易于访问的产品和服务。 其博客地址主题如 ARIA 最佳做法、辅助功能趋势、网络研讨会等。

### 辅助功能示例
#### [ally-教程](http://allyjs.io/tutorials/)
JavaScript 库通过使辅助功能更简单，帮助现代 web 应用程序提供辅助功能。

#### [Heydonworks-ARIA 示例](http://heydonworks.com/practical_aria_examples/)
用于增强你的应用程序辅助功能的实用 ARIA 示例

#### [OpenAjax 示例](http://oaa-accessibility.org/)
OpenAjax 联盟网站是一个出色的资源，用于验证 WAI-ARIA 的规则，并提供 WAI-ARIA ARIA 实现的一些示例。

#### [模式](http://a11yproject.com/patterns.html)
[A11Y 项目](http://a11yproject.com/)提供了易于访问的小组件和图案（如菜单、按钮、工具提示等）库。

### 辅助功能技术 & 工具
#### [辅助功能：创建适用于 Microsoft Edge 的易于访问的扩展图标](../extensions/guides/accessibility.md)
获取有关为 Microsoft Edge 创建易于访问的扩展图标的指南。

#### [辅助名称和描述：计算和映射1。1](https://www.w3.org/TR/accname-1.1/)
此 W3C 映射文档介绍了浏览器如何确定 web 内容语言的辅助对象的名称和说明，以及如何在辅助功能 Api 中公开它们。

#### [辅助功能评估资源](https://www.w3.org/WAI/eval/Overview.html)
辅助功能评估资源是由 W3C 使用的多页资源，用于概括评估网站辅助功能的不同方法。

#### [辅助技术兼容性测试](http://www.powermapper.com/tests/)
测试结果，显示不同内容类型和标准在辅助技术（AT）（如屏幕阅读器）中的行为。

#### [构建易于访问的网站](https://blogs.msdn.microsoft.com/webdev/2016/05/02/building-accessible-websites-just-got-a-lot-easier/)
此 .NET Web 开发和工具博客文章介绍 Visual Studio 扩展[Web 辅助功能检查器](https://go.microsoft.com/fwlink/p/?linkid=841539)。

#### [Core 辅助功能 API 映射1。1](https://www.w3.org/TR/core-aam-1.1/)
此 W3C 映射文档介绍了如何向辅助功能 Api 公开 web 内容语言的语义。  

#### [轻松检查–网页辅助功能的首次审核](https://www.w3.org/WAI/eval/preliminary.html)
WAI-ARIA 的一系列快速检查，可帮助你 asses 网页的辅助功能。

#### [如何满足 WCAG 2。0](https://www.w3.org/WAI/WCAG20/quickref/)
Web 内容辅助功能准则（WCAG）2.0 要求（成功条件）和技术的快速参考。

#### [HTML 辅助功能 API 映射1。0](https://www.w3.org/TR/html-aam-1.0/)
此 W3C 映射文档介绍了如何将 HTML 5.1 元素和属性映射到平台辅助功能 Api。


#### [快速提示](http://a11yproject.com/#Quick-tips)
[A11Y 项目](http://a11yproject.com/)辅助功能的快速 web 开发提示列表。

#### [网站扫描](https://developer.microsoft.com/microsoft-edge/tools/staticscan/)
Microsoft Edge 开发人员中心上的网站扫描工具检查是否存在过期的库、布局问题和辅助功能问题。

#### [WCAG 2.0 的技术](https://www.w3.org/TR/WCAG20-TECHS/Overview.html)
来自 W3C 的技术，这些技术为 web 开发人员提供有关会议[Web 内容辅助功能准则（WCAG） 2.0](https://w3.org/TR/WCAG20/)成功条件的指南。

#### [针对 Web 辅助功能进行开发的提示](https://w3.org/WAI/gettingstarted/tips/developing.html)
来自 W3C 的提示，用于开发对残疾人士更易于访问的 web 内容。

#### [WAI-ARIA-ARIA 创作做法1。1](http://w3c.github.io/aria-practices/)
由 W3C 提供的文档，提供读者对如何使用 WAI-ARIA-ARIA 1.1 的理解，并建议使用 WAI-ARIA 角色、状态和属性来访问小组件、导航和行为的方法。

#### [WAI-ARIA 指南和技术](https://w3.org/WAI/guid-tech.html)
由 WAI-ARIA 开发的一系列 web 辅助功能指南和标准。  

#### [Web 辅助功能评估工具列表](https://www.w3.org/WAI/ER/tools/index.html)
Web 辅助功能评估工具列表，可帮助确定网站是否满足辅助功能指南。

#### [Web 辅助功能：了解每个人的影响和好处](https://w3.org/WAI/perspectives/)
W3C 关于辅助功能和每个人的好处的影响的一系列简短的课程视频。
