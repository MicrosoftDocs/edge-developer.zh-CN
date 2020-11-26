---
ms.assetid: 1b3ebc25-d023-4f23-bbba-dce066c20de8
description: 浏览 (ARIA) 的最佳做法和易于访问的富 Internet 应用程序，以便创建易于访问的网站。
title: 构建 |功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/13/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 辅助功能，面向开发人员的辅助功能，辅助网站，边缘，web 开发，ARIA，开发人员，UIA，UI 自动化
ms.custom: seodec18
ms.openlocfilehash: 7a8ff5082132ec3270a6e01af594a5bd9fb35389
ms.sourcegitcommit: 5d3802721036dc7cd90e9e6f7ac90dc3acc24eec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "11191548"
---
# 构建易于访问的网站
Web 使用 HTML、CSS 和 JavaScript 的组合生成了动态、复杂的网站、应用程序和用户界面。  但是，如果在设计和构建时不考虑辅助功能，则依赖 [辅助技术](https://webaim.org/articles/motor/assistive) 浏览 web 的用户很难使用这些复杂的网站。 构建残疾人士易于访问的网站需要有关用户界面的语义信息。 这允许辅助技术（如屏幕阅读器）传达必要的信息，以帮助具有各种功能的人员使用该网站。

有关 Microsoft Edge 支持的新 HTML5 功能 accessibly 的信息，请访问 [HTML5Accessibility](https://html5accessibility.com) 。

## 辅助功能的工作原理

辅助技术添加了计算机通常不具备的功能。 例如，视觉障碍的用户可能将其键盘与辅助技术（如屏幕阅读器）结合使用，而不是使用鼠标和屏幕直接使用浏览器。 对于 Microsoft 平台和 web 上的应用程序，辅助技术与 Microsoft [UI 自动化](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx)、特定于应用程序的对象模型（如文档对象模型 (DOM) 在 Microsoft Edge 中）或它们的组合进行交互。

对于 web 开发人员，某些 HTML 元素映射到 UI 自动化对象，因此在选择这些 HTML 元素时，开发人员可以使用内置于这些元素的辅助功能属性和事件。 在开发您的网站时，通常只需考虑确保 API 正确地写入 (或指定了相应的元素) ，才能使应用程序易于访问。 有关详细信息，请查看 [Microsoft Edge 中的 ARIA 和 UI 自动化](./build/ARIA-and-UI-Automation.md) 。  有关可访问的通用 Windows 平台 (UWP) 应用的信息，请参阅 Windows 开发人员中心中的 " [辅助功能](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility) " 主题。

可通过良好的编码实践解决动态内容的许多常见辅助功能问题，并且 [WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629) 文档包含许多技术和最佳做法，可帮助你创建更易于访问的动态 web 应用程序。 但是，即使正确编码，也不一定可以访问动态内容。 [ (ARIA) 易于访问的富 Internet 应用程序 ](#aria) 可帮助解决此问题。  

有关 web 辅助功能的详细信息，请参阅[Web 辅助功能计划](https://www.w3.org/WAI/)的[Web 辅助功能简介](https://www.w3.org/WAI/intro/accessibility.php) (wai-aria) 。

## ARIA
W3C's [Web 辅助功能计划](https://www.w3.org/WAI/) (ARIA) 规范的[易于访问的富 Internet 应用程序](https://www.w3.org/TR/wai-aria/)定义为使动态 Web 内容和自定义用户界面可供所有人访问的语法。 ARIA 通过使用 (角色、属性和状态) 的其他属性来扩展 HTML，这些属性旨在传递自定义语义。 浏览器使用这些属性将控件的状态和角色传递给辅助功能 API。

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

通过 W3C 转到 ["角色" 模型](https://www.w3.org/TR/wai-aria-1.1/#roles) 以查看角色、属性和状态的完整列表。

有关 ARIA 的详细信息，请参阅 " [资源](#resources) " 部分中的 ARIA。

## 辅助技术兼容性测试  

验证正在构建的网站是否适用于真正的辅助技术是确保你的残障人士获得良好体验的最佳方式。  由于很多辅助技术使用键盘，因此测试网站的键盘辅助功能是一个很好的开始位置。  [键盘兼容性测试][W3cPerspectiveVideosKeyboard] 验证用户是否可以访问所有交互式控件，而无需使用鼠标。  Microsoft 的 microsoft [辅助功能见解][AccessibilityinsightsWebOverview] 是 microsoft Edge 和 Chrome 的浏览器扩展，可指导你并显示一些常见问题。  

确信你的网站在使用键盘时工作良好，请使用其他辅助技术（如屏幕阅读器）试用它。  它在以下情况下发现问题。

*   HTML、ARIA 和 CSS。  
*   功能或技术对辅助技术的支持级别。  
    
不同的浏览器可能将元素映射到平台辅助功能 Api，与 Microsoft Edge 不同。  构建你的界面时，请务必考虑每个差异。  

WebAIM 通过 [屏幕阅读器][WebaimProjectsScreenreadersurvey8] 和 [弱视][WebaimProjectsLowvisionsurvey2] 用户执行调查，帮助你确定要测试的辅助技术和浏览器。  

### 了解如何测试  

辅助技术是复杂的工具。  不要假设你可以使用辅助技术立即开始测试，而无需事先了解它的工作原理。  学习使用屏幕阅读器进行测试有一个特别陡的学习曲线。  初级用户屏幕阅读器用户可能假设问题与屏幕阅读器的误用有关时出现屏幕阅读器错误。  

有关学习通过辅助技术进行测试的详细信息，请导航到 WebAIM 上 [的屏幕阅读器进行测试][WebaimArticlesScreenreaderTesting] 。  

### 本地测试  

大多数设备都包含操作系统内置的辅助技术。  Microsoft Windows 包括 [Windows 讲述人][MicrosoftSupport22798] 屏幕阅读器和 [windows 放大镜][MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198]。  可下载第三方辅助技术，如 [NVDA][NvaccessAboutNvda]、 [FreedomscientificSoftwareJaws]和 [ZoomText][FreedomscientificSoftwareZoomtext] 。  Apple macOS 包括 [VoiceOver][AppleAccessibilityMacVision] 屏幕阅读器。  和 iOS、Android 和 Linux 都支持各种辅助技术。  

### 在虚拟机和模拟器中测试  

在 "macOS" 下，如果要使用仅适用于 Windows 的辅助技术（如 Windows "讲述人" 或 "NVDA"）进行测试，请创建 Windows 虚拟机。  具有 Microsoft Edge \ (EdgeHTML \ ) 和 IE 的虚拟机可在 " [虚拟机下载" 页面][MicrosoftDeveloperEdgeVms]上 VirtualBox 和 VMWare。  

[Android Studio][AndroidDeveloperSdkInstallingStudioHtml] 包含一个用于测试 [Android 辅助功能套件][GooglePlayStoreAndroidAccessibilitySuite]中的辅助技术的模拟器。  按照说明 [设置虚拟设备][AndroidDeveloperDevicesManagingAvdsHtml] 并 [启动模拟器][AndroidDeveloperDevicesEmulatorHtml]，然后从 GooglePlay 应用商店安装 [Android 辅助功能套件][GooglePlayStoreAndroidAccessibilitySuite] 。  

> [!NOTE]
> IOS 模拟器当前不包含 VoiceOver。  

### 基于云的测试工具  

如果你的操作系统上不能使用辅助技术，或者你无法在虚拟机或模拟器上安装，那么下一步是基于云的辅助技术测试工具。  

*   [Assistiv Labs (商业) ][AssistivlabsMain] 使你能够通过任何现代 web 浏览器手动测试辅助技术。  选择辅助技术和浏览器，它将你与你可以交互的虚拟机、模拟器或真正设备连接起来。  

## 资源

### 辅助功能基础知识
#### [A11Y 项目](http://a11yproject.com/)
A11Y 项目是社区驱动的工作，使 web 辅助功能更易于使用。 查看 [A11Y 项目](https://a11yproject.com/) 网站，了解基本辅助功能原则、其易于访问的模式和小组件 [库](https://a11yproject.com/patterns)以及它们在辅助功能软件、博客、书籍和工具上的 [资源](http://a11yproject.com/resources.html) 。

#### [ (WAI-ARIA 的 Web 辅助功能计划) ](https://w3.org/WAI/)
W3C's Web 辅助功能计划 (WAI-ARIA) 是帮助改进 Web 辅助功能的一项工作。 他们的网站提供了各种资源来 [开始使用 Web 辅助功能](https://www.w3.org/WAI/gettingstarted/Overview.html)， [设计包括 "包含](https://www.w3.org/WAI/users/Overview.html)"、" [教程" 和 "演示文稿](https://www.w3.org/WAI/train.html)" 等。

### 辅助功能博客
#### [Paciello 组](https://www.paciellogroup.com/blog/)
Paciello 组为全球各地的组织提供咨询和技术解决方案，以确保客户能够有效、高效地访问所有受众，同时满足政府和国际标准。 其博客介绍诸如 web 辅助功能最佳做法、辅助功能工具和辅助功能趋势等主题。

#### [轻松访问](http://simplyaccessible.com/articles/)
简单的辅助功能是一组辅助功能专家团队，可提供辅助功能培训、咨询以及更多更改 web 上的辅助功能的感觉。 他们的 [文章](http://simplyaccessible.com/articles/) 部分讨论了 web 辅助功能、易于访问的设计等的最佳做法。

#### [SSB 邓 Group (SSB) ](http://www.ssbbartgroup.com/blog/)
SSB 邓 Group 是一个数字辅助公司，支持其客户开发和部署易于访问的产品和服务。 其博客地址主题如 ARIA 最佳做法、辅助功能趋势、网络研讨会等。

### 辅助功能示例
#### [ally.js 教程](http://allyjs.io/tutorials/)
JavaScript 库通过使辅助功能更简单，帮助现代 web 应用程序提供辅助功能。

#### [Heydonworks-ARIA 示例](http://heydonworks.com/practical_aria_examples/)
用于增强你的应用程序辅助功能的实用 ARIA 示例

#### [OpenAjax 示例](http://oaa-accessibility.org/)
OpenAjax 联盟网站是一个出色的资源，用于验证 WAI-ARIA 的规则，并提供 WAI-ARIA ARIA 实现的一些示例。

#### [模式](http://a11yproject.com/patterns.html)
[A11Y 项目](http://a11yproject.com/) 提供了易于访问的小组件和图案（如菜单、按钮、工具提示等）库。

### 辅助功能技术 & 工具
#### [辅助功能：创建适用于 Microsoft Edge 的易于访问的扩展图标](../extensions/guides/accessibility.md)
获取有关为 Microsoft Edge 创建易于访问的扩展图标的指南。

#### [辅助名称和描述：计算和映射1。1](https://www.w3.org/TR/accname-1.1/)
此 W3C 映射文档介绍了浏览器如何确定 web 内容语言的辅助对象的名称和说明，以及如何在辅助功能 Api 中公开它们。

#### [辅助功能评估资源](https://www.w3.org/WAI/eval/Overview.html)
辅助功能评估资源是由 W3C 使用的多页资源，用于概括评估网站辅助功能的不同方法。

#### [辅助技术兼容性测试](http://www.powermapper.com/tests/)
测试结果，显示不同内容类型和标准在辅助技术中的行为如何在) （如屏幕阅读器） (。

#### [构建易于访问的网站](https://blogs.msdn.microsoft.com/webdev/2016/05/02/building-accessible-websites-just-got-a-lot-easier/)
此 .NET Web 开发和工具博客文章介绍 Visual Studio 扩展 [Web 辅助功能检查器](https://go.microsoft.com/fwlink/p/?linkid=841539)。

#### [Core 辅助功能 API 映射1。1](https://www.w3.org/TR/core-aam-1.1/)
此 W3C 映射文档介绍了如何向辅助功能 Api 公开 web 内容语言的语义。  

#### [轻松检查–网页辅助功能的首次审核](https://www.w3.org/WAI/eval/preliminary.html)
WAI-ARIA 的一系列快速检查，可帮助你 asses 网页的辅助功能。

#### [如何满足 WCAG 2。0](https://www.w3.org/WAI/WCAG20/quickref/)
有关 Web 内容辅助功能准则的快速参考指南 (WCAG) 2.0 要求 (成功条件) 和技术。

#### [HTML 辅助功能 API 映射1。0](https://www.w3.org/TR/html-aam-1.0/)
此 W3C 映射文档介绍了如何将 HTML 5.1 元素和属性映射到平台辅助功能 Api。


#### [快速提示](http://a11yproject.com/#Quick-tips)
[A11Y 项目](http://a11yproject.com/)辅助功能的快速 web 开发提示列表。

#### [网站扫描](https://developer.microsoft.com/microsoft-edge/tools/staticscan/)
Microsoft Edge 开发人员中心上的网站扫描工具检查是否存在过期的库、布局问题和辅助功能问题。

#### [WCAG 2.0 的技术](https://www.w3.org/TR/WCAG20-TECHS/Overview.html)
来自 W3C 的技术，这些技术根据 (WCAG) 2.0 的成功条件，提供 web 开发人员对会议 [Web 内容辅助功能准则](https://w3.org/TR/WCAG20/) 的指导。

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

<!-- links -->  

<!--todo: link updates and acrolinx  -->  

[MicrosoftDeveloperEdgeVms]: https://developer.microsoft.com/microsoft-edge/tools/vms "虚拟机 |Microsoft Edge 开发人员"  

[MicrosoftSupport22798]: https://support.microsoft.com/help/22798 ""讲述人" 的完整指南 |Microsoft 支持"  
[MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198]: https://support.microsoft.com/windows/414948ba-8b1c-d3bd-8615-0e5e32204198 "使用放大镜使屏幕上的项目更易于查看 |Microsoft 支持"  

[AccessibilityinsightsWebOverview]: https://accessibilityinsights.io/docs/web/overview "Web 辅助功能见解 |辅助功能见解"  

[AndroidDeveloperDevicesManagingAvdsHtml]: https://developer.android.com/tools/devices/managing-avds.html "创建和管理虚拟设备 |Android 开发人员"  
[AndroidDeveloperDevicesEmulatorHtml]: https://developer.android.com/tools/devices/emulator.html "在 Android 模拟器上运行应用 |Android 开发人员"  
[AndroidDeveloperSdkInstallingStudioHtml]: https://developer.android.com/sdk/installing/studio.html "下载 Android Studio |Android 开发人员"  

[AppleAccessibilityMacVision]: https://www.apple.com/accessibility/mac/vision "视觉辅助功能-Mac |Apple"  

[AssistivlabsMain]: https://assistivlabs.com "Assistiv Labs"  

[FreedomscientificSoftwareJaws]: https://www.freedomscientific.com/products/software/jaws "JAWS® |自由科学"  
[FreedomscientificSoftwareZoomtext]: https://www.freedomscientific.com/products/software/zoomtext "ZoomText |自由科学"  

[GooglePlayStoreAndroidAccessibilitySuite]: https://play.google.com/store/apps/details?id=com.google.android.marvin.talkback "Android 辅助功能套件 |GooglePlay 商店"  

[NvaccessAboutNvda]: https://www.nvaccess.org/about-nvda "关于 NVDA |NV 访问"  

[W3cPerspectiveVideosKeyboard]: https://www.w3.org/WAI/perspective-videos/keyboard "键盘兼容性 |W3C"  

[WebaimProjectsLowvisionsurvey2]: https://webaim.org/projects/lowvisionsurvey2 "对视力不佳的用户的调查 \ #2 结果 |WebAIM"  
[WebaimProjectsScreenreadersurvey8]: https://webaim.org/projects/screenreadersurvey8 "屏幕阅读器用户调查 \ #8 结果 |WebAIM"  
[WebaimArticlesScreenreaderTesting]: https://webaim.org/articles/screenreader_testing "通过屏幕阅读器进行测试 |WebAIM"  
