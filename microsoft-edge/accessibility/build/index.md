---
ms.assetid: 1b3ebc25-d023-4f23-bbba-dce066c20de8
description: 演练 ARIA 应用程序与 ARIA (的最佳实践) 如何共同创建可访问的网站。
title: 生成|辅助功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/06/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: 辅助功能， 开发人员辅助功能， 可访问的网站， 边缘， Web 开发， ARIA， 开发人员， UIA， UI 自动化
ms.custom: seodec18
ms.openlocfilehash: 3bc16450a3a64c06d290d1d3e112a9b2faecbe14
ms.sourcegitcommit: 146072bf606b84e5145a48333abf9c6b892a12d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "11480151"
---
# <a name="building-accessible-websites"></a>构建可访问的网站

Web 填充了动态且复杂的网站、应用程序和用户界面，这些网站、应用程序和用户界面是使用 HTML、CSS 和 JavaScript 的组合构建的。  但是，当设计和构建时没有考虑辅助功能时，依赖辅助技术来浏览 Web 的人很难使用这些复杂的网站。 [](https://webaim.org/articles/motor/assistive) 构建可供残障人士访问的网站需要有关用户界面的语义信息。 这允许辅助技术（如屏幕阅读器）传达必要的信息，以帮助具有各种功能的人使用网站。

有关 Microsoft Edge 支持哪些新 HTML5 功能可访问的信息，请访问[HTML5Accessibility。](https://html5accessibility.com)

## <a name="how-accessibility-works"></a>辅助功能的工作原理

辅助技术添加计算机通常没有的功能。 例如，视觉受损的用户可能将键盘与辅助技术（如屏幕阅读器）结合使用，而不是直接将浏览器与鼠标和屏幕结合使用。 对于 Microsoft 平台和 Web 上的应用程序，辅助技术与 Microsoft [UI](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx)自动化、特定于应用程序的对象模型（如 Microsoft Edge 中的文档对象模型 (DOM) ）或这些对象模型的组合进行交互。

对于 Web 开发人员，某些 HTML 元素会映射到 UI 自动化对象，因此在选择这些 HTML 元素时，开发人员可以使用内置于这些元素的辅助功能属性和事件。 开发网站时，通常只需关注确保 API 正确写入 (或指定适当的元素) ，以便应用程序可访问。 有关详细信息， [请参阅 Microsoft Edge 中的 ARIA](./ARIA-and-UI-Automation.md) 和 UI 自动化。  有关可访问的通用 Windows 平台 (UWP) 应用的信息，请导航到 Windows 开发人员[](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility)中心中的辅助功能主题。

通过良好的编码实践，可以解决与动态内容相关的许多常见辅助功能问题，并且 [WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629) 文档包括许多技术和最佳实践，可帮助你创建更易于访问的动态 Web 应用程序。 但是，即使正确编码，也不必访问动态内容。 [可访问的富 Internet 应用程序 (ARIA) ](#aria) 可帮助解决此问题。  

有关 Web 辅助功能详细信息，请参阅 Web[](https://www.w3.org/WAI/intro/accessibility.php)辅助功能计划为 WEB 辅助功能简介[ (一) 。 ](https://www.w3.org/WAI)

## <a name="aria"></a>ARIA

W3C 的 Web 辅助功能计划 (ARIA) ARIA 规范定义为使所有[](https://www.w3.org/WAI/)人员均可访问的动态 Web 内容和自定义用户界面的语法。 [](https://www.w3.org/TR/wai-aria/) ARIA 通过使用其他属性扩展 HTML (角色、属性和状态) 旨在传达自定义语义。 浏览器使用这些属性将控件的状态和角色传递到辅助功能 API。

### <a name="roles-properties-and-states"></a>角色、属性和状态

ARIA 角色使用 属性在元素上 [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) 设置，以提供有关元素的辅助技术和辅助功能 API 信息。 例如，分配以下 `<li>` 元素以 `role="menuitem"` 表示它是菜单中的项。

```html
<li role="menuitem">Home</li>
```

ARIA 状态和属性是 aria 前缀的属性，可提供有关对象的特定信息，以帮助形成角色的性质的定义。 属性是对象的性质所必不可少的属性，如 [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) 和 [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx) 。 更改属性会影响对象的含义。 在下面的示例中，属性 `aria-haspopup="true"` 在菜单项上设置 `<li>` ，以表示其具有弹出窗口。

```html
<li role="menuitem" aria-haspopup="true">Open</li>
```

状态不会更改对象的性质，但表示与对象或用户与对象交互（如 或 ） [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) 关联的信息 [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx) 。 例如，以下示例 `aria-checked="false"` 中的状态表示复选框未选中。

```html
<div role="checkbox" aria-checked="false">Accept</div>
```

转到 [W3C](https://www.w3.org/TR/wai-aria-1.1/#roles) 的角色模型以查看角色、属性和状态的完整列表。

有关 ARIA 的信息，请导航到"资源" [部分中的](#resources) "ARIA"。

## <a name="assistive-technology-compatibility-testing"></a>辅助技术兼容性测试  

验证正在构建的网站是否使用真实的辅助技术是确保残障用户获得良好体验的最佳方法。  由于许多辅助技术都使用键盘，因此测试网站的键盘辅助功能是一个很好的起点。  [键盘兼容性][W3cPerspectiveVideosKeyboard] 测试验证用户是否无需鼠标即可访问所有交互式控件。  Microsoft [Accessibility Insights for Web][AccessibilityinsightsWebOverview] 是 Microsoft Edge 和 Chrome 的浏览器扩展，可指导你并展示一些常见问题。  

一旦确信你的网站能很好地使用键盘，请通过其他辅助技术（如屏幕阅读器）试用它。  它可发现以下问题。

*   您的 HTML、ARIA 和 CSS。  
*   对功能或技术的辅助技术的支持级别。  
    
不同的浏览器可能以不同于 Microsoft Edge 的方式将元素映射到平台辅助功能 API。  在构建接口时，考虑每个差异非常重要。  

WebAIM 与屏幕[阅读器][WebaimProjectsScreenreadersurvey8]和低视力[][WebaimProjectsLowvisionsurvey2]用户进行调查，帮助你确定要测试哪些辅助技术和浏览器。  

### <a name="learning-how-to-test"></a>了解如何测试  

辅助技术是复杂的工具。  不要假定你能够立即开始使用辅助技术进行测试，而无需首先了解它的工作原理。  学习使用屏幕阅读器进行测试具有一个特别容易学习的曲线。  当问题与误用屏幕阅读器有关时，屏幕阅读器用户可能会假设发生了屏幕阅读器 Bug。  

有关学习使用辅助技术进行测试的信息，请导航到使用 WebAIM 上的 [屏幕][WebaimArticlesScreenreaderTesting] 阅读器进行测试。  

### <a name="testing-locally"></a>本地测试  

大多数设备包括内置于操作系统的辅助技术。  Microsoft Windows 包括 [Windows 讲述人][MicrosoftSupport22798] 屏幕阅读器和 [Windows 放大镜][MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198]。  可以下载第三方辅助技术，如[NVDA、FreedomscientificSoftwareJaws]和[ZoomText。][FreedomscientificSoftwareZoomtext] [][NvaccessAboutNvda]  Apple macOS 包括 [VoiceOver][AppleAccessibilityMacVision] 屏幕阅读器。  iOS、Android 和 Linux 都支持各种辅助技术。  

### <a name="testing-in-virtual-machines-and-emulators"></a>虚拟机和仿真器中的测试  

在 macOS 下，如果你希望使用仅适用于 Windows 的辅助技术（如 Windows 讲述人或 NVDA）进行测试，请创建 Windows 虚拟机。  具有 Microsoft Edge \ (EdgeHTML\) 和 IE 的虚拟机可用于虚拟机下载页面上的 VirtualBox 和[VMWare。][MicrosoftDeveloperEdgeVms]  

[Android Studio][AndroidDeveloperSdkInstallingStudioHtml] 包含一个仿真器，用于测试 Android 辅助功能套件 [中的辅助技术][GooglePlayStoreAndroidAccessibilitySuite]。  按照说明 [设置虚拟设备][AndroidDeveloperDevicesManagingAvdsHtml] 并启动 [仿真][AndroidDeveloperDevicesEmulatorHtml]器，然后从 GooglePlay 商店安装 [Android][GooglePlayStoreAndroidAccessibilitySuite] 辅助功能套件。  

> [!NOTE]
> iOS 模拟器当前不包括 VoiceOver。  

### <a name="cloud-based-testing-tools"></a>基于云的测试工具  

如果辅助技术在你的操作系统上不可用，或者你无法将辅助技术安装在虚拟机或仿真器上，则基于云的辅助技术测试工具是下一个最佳工具。  

*   [Assistiv Labs (商业) ， ][AssistivlabsMain] 使你能够通过任何新式 Web 浏览器手动测试辅助技术。  选择辅助技术和浏览器，它将你与可以交互的虚拟机、仿真器或真实设备相连接。  

## <a name="resources"></a>资源

### <a name="accessibility-basics"></a>辅助功能基础知识

#### [<a name="the-a11y-project"></a>A11Y 项目](http://a11yproject.com/)

A11Y 项目是社区推动的一项工作，用于简化 Web 辅助功能。 查看[A11Y 项目](https://a11yproject.com/)网站，了解基本的辅助功能原则、辅助功能模式和小组件库，以及辅助功能[](https://a11yproject.com/patterns)软件、博客、[](http://a11yproject.com/resources.html)书籍和工具上的资源。

#### [<a name="web-accessibility-initiative-wai"></a>Web 辅助功能计划 (，) ](https://w3.org/WAI/)

W3C Web 辅助功能 (一) 一项帮助改善 Web 辅助功能的工作。 他们的网站为 Web 辅助功能入门[](https://www.w3.org/WAI/gettingstarted/Overview.html)、包含设计、教程和演示文稿[](https://www.w3.org/WAI/users/Overview.html)等[提供了](https://www.w3.org/WAI/train.html)各种资源。

### <a name="accessibility-blogs"></a>辅助功能博客

#### [<a name="the-paciello-group"></a>Paciello 组](https://www.paciellogroup.com/blog/)

Paciello 组向世界各地的组织提供咨询和技术解决方案，以确保其客户在满足政府标准和国际标准的同时有效且高效地接触所有受众。 他们的博客涵盖了 Web 辅助功能最佳实践、辅助功能工具和辅助功能趋势等主题。

#### [<a name="simply-accessible"></a>易于访问](http://simplyaccessible.com/articles/)

Simply Accessible 是一个辅助功能专家团队，提供辅助功能培训、咨询等，以更改对 Web 上的辅助功能感知。 他们 [的文章](http://simplyaccessible.com/articles/) 部分讨论了 Web 辅助功能、辅助设计等的最佳实践。

#### [<a name="ssb-bart-group-ssb"></a>SSB BART 组 (SSB) ](http://www.ssbbartgroup.com/blog/)

SSB BART 组是一家数字辅助功能公司，支持其客户开发并部署辅助产品和服务。 他们的博客介绍 ARIA 最佳实践、辅助功能趋势、网络研讨会等主题。

### <a name="accessible-examples"></a>辅助示例

#### [<a name="allyjs---tutorials"></a>ally.js - 教程](http://allyjs.io/tutorials/)

JavaScript 库，通过简化辅助功能帮助现代 Web 应用程序解决辅助功能问题。

#### [<a name="heydonworks---aria-examples"></a>Heydonworks - ARIA 示例](http://heydonworks.com/practical_aria_examples/)

增强应用程序辅助功能的实用 ARIA 示例

#### [<a name="openajax-examples"></a>OpenAjax 示例](http://oaa-accessibility.org/)

OpenAjax 联盟网站是验证一些适用于一个使用一百万位用户规则且提供一些一系列一些的一些一线实现示例的优秀资源。

#### [<a name="patterns"></a>模式](http://a11yproject.com/patterns.html)

[A11Y 项目](http://a11yproject.com/) 提供了一个可访问小组件和模式（如菜单、按钮、工具提示等）的库。

### <a name="accessibility-techniques--tools"></a>辅助功能技术&工具

#### [<a name="accessibility-creating-accessible-extension-icons-for-microsoft-edge"></a>辅助功能：为 Microsoft Edge 创建辅助扩展图标](/archive/microsoft-edge/legacy/developer/extensions/guides/accessibility)

获取有关为 Microsoft Edge 创建辅助扩展图标的指南。

#### [<a name="accessible-name-and-description-computation-and-mappings-11"></a>辅助名称和说明：计算和映射 1.1](https://www.w3.org/TR/accname-1.1/)

此 W3C 映射文档介绍了浏览器如何确定 Web 内容语言中可访问对象的名称和说明，以及如何在辅助功能 API 中公开它们。

#### [<a name="accessibility-evaluation-resources"></a>辅助功能评估资源](https://www.w3.org/WAI/eval/Overview.html)

辅助功能评估资源是 W3C 的一个多页资源，概述了用于评估网站辅助功能的不同方法。

#### [<a name="assistive-technology-compatibility-tests"></a>辅助技术兼容性测试](http://www.powermapper.com/tests/)

显示不同内容类型和标准在辅助技术（如屏幕阅读器 (AT) 的行为的测试结果。

#### [<a name="building-accessible-websites-just-got-a-lot-easier"></a>构建可访问的网站变得更加简单](https://blogs.msdn.microsoft.com/webdev/2016/05/02/building-accessible-websites-just-got-a-lot-easier/)

本 .NET Web 开发和工具博客文章Visual Studio扩展 Web [辅助功能检查器](https://go.microsoft.com/fwlink/p/?linkid=841539)。

#### [<a name="core-accessibility-api-mappings-11"></a>核心辅助功能 API 映射 1.1](https://www.w3.org/TR/core-aam-1.1/)

此 W3C 映射文档说明如何向辅助功能 API 公开 Web 内容语言的语义。  

#### [<a name="easy-checks--a-first-review-of-web-accessibility"></a>轻松检查 – Web 辅助功能的首次评审](https://www.w3.org/WAI/eval/preliminary.html)

一系列由一系列由用户进行快速检查的（该快速检查可帮助你了解网页的辅助功能）。

#### [<a name="how-to-meet-wcag-20"></a>如何满足 WCAG 2.0](https://www.w3.org/WAI/WCAG20/quickref/)

快速参考 Web 内容辅助功能指南 (WCAG) 2.0 要求 (成功) 和技术。

#### [<a name="html-accessibility-api-mappings-10"></a>HTML 辅助功能 API 映射 1.0](https://www.w3.org/TR/html-aam-1.0/)

此 W3C 映射文档说明了 HTML5.1 元素和属性如何映射到平台辅助功能 API。

#### [<a name="quick-tips"></a>快速提示](http://a11yproject.com/#Quick-tips)

[A11Y](http://a11yproject.com/)项目关于辅助功能的快速 Web 开发提示列表。

#### [<a name="site-scan"></a>网站扫描](https://developer.microsoft.com/microsoft-edge/tools/staticscan/)

Microsoft Edge 开发人员中心上的站点扫描工具会检查过期库、布局问题和辅助功能问题。

#### [<a name="techniques-for-wcag-20"></a>WCAG 2.0 的技术](https://www.w3.org/TR/WCAG20-TECHS/Overview.html)

W3C 中的技术，为 Web 开发人员提供有关满足 Web 内容辅助功能指南 ([WCAG) 2.0 成功](https://w3.org/TR/WCAG20/) 标准的指导。

#### [<a name="tips-on-developing-for-web-accessibility"></a>有关开发 Web 辅助功能的提示](https://w3.org/WAI/gettingstarted/tips/developing.html)

W3C 中有关开发残障人士更容易访问的 Web 内容的提示。

#### [<a name="wai-aria-authoring-practices-11"></a>WAI-ARIA 创作实践 1.1](http://w3c.github.io/aria-practices/)

W3C 提供的一个文档，使读者能够了解如何使用 WIDGET-ARIA 1.1，并推荐使用 WIDGET-ARIA 角色、状态和属性使小组件、导航和行为可供访问的方法。

#### [<a name="wai-guidelines-and-techniques"></a>一些指南和技术](https://w3.org/WAI/guid-tech.html)

由一系列由一系列 WEB 辅助功能指南和由一些用户制定的标准。  

#### [<a name="web-accessibility-evaluation-tools-list"></a>Web 辅助功能评估工具列表](https://www.w3.org/WAI/ER/tools/index.html)

可帮助确定网站是否满足辅助功能指南的 Web 辅助功能评估工具列表。

#### [<a name="web-accessibility-perspectives-explore-the-impact-and-benefits-for-everyone"></a>Web 辅助功能角度：探索对所有人的影响和好处](https://w3.org/WAI/perspectives/)

W3C 关于辅助功能的影响和每个人的权益的一系列简短情境视频。

<!-- links -->  

<!--todo: link updates and acrolinx  -->  

[MicrosoftDeveloperEdgeVms]: https://developer.microsoft.com/microsoft-edge/tools/vms "虚拟机|Microsoft Edge 开发人员"  

[MicrosoftSupport22798]: https://support.microsoft.com/help/22798 "讲述人工具的完整|Microsoft 支持"  
[MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198]: https://support.microsoft.com/windows/414948ba-8b1c-d3bd-8615-0e5e32204198 "使用放大镜使屏幕上的内容更易于查看|Microsoft 支持"  

[AccessibilityinsightsWebOverview]: https://accessibilityinsights.io/docs/web/overview "适用于 Web 网站的辅助功能见解|辅助功能见解"  

[AndroidDeveloperDevicesManagingAvdsHtml]: https://developer.android.com/tools/devices/managing-avds.html "创建和管理虚拟设备|Android 开发人员"  
[AndroidDeveloperDevicesEmulatorHtml]: https://developer.android.com/tools/devices/emulator.html "在 Android 仿真器设备上|Android 开发人员"  
[AndroidDeveloperSdkInstallingStudioHtml]: https://developer.android.com/sdk/installing/studio.html "下载 Android Studio |Android 开发人员"  

[AppleAccessibilityMacVision]: https://www.apple.com/accessibility/mac/vision "视觉辅助功能 - Mac |Apple"  

[AssistivlabsMain]: https://assistivlabs.com "Assistiv 实验室"  

[FreedomscientificSoftwareJaws]: https://www.freedomscientific.com/products/software/jaws "JAWS® |Freedom Scientific"  
[FreedomscientificSoftwareZoomtext]: https://www.freedomscientific.com/products/software/zoomtext "ZoomText |Freedom Scientific"  

[GooglePlayStoreAndroidAccessibilitySuite]: https://play.google.com/store/apps/details?id=com.google.android.marvin.talkback "Android 辅助功能套件|GooglePlay 应用商店"  

[NvaccessAboutNvda]: https://www.nvaccess.org/about-nvda "关于 NVDA |NV 访问"  

[W3cPerspectiveVideosKeyboard]: https://www.w3.org/WAI/perspective-videos/keyboard "键盘兼容性|W3C"  

[WebaimProjectsLowvisionsurvey2]: https://webaim.org/projects/lowvisionsurvey2 "低视力用户调查#2结果|WebAIM"  
[WebaimProjectsScreenreadersurvey8]: https://webaim.org/projects/screenreadersurvey8 "屏幕阅读器用户调查 \#8结果|WebAIM"  
[WebaimArticlesScreenreaderTesting]: https://webaim.org/articles/screenreader_testing "使用屏幕阅读器测试|WebAIM"  
