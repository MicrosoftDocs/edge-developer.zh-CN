---
ms.assetid: 1b3ebc25-d023-4f23-bbba-dce066c20de8
description: 演练最佳实践和可访问的富 Internet 应用程序 (ARIA) 如何共同创建可访问的网站。
title: 生成|辅助功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: 辅助功能， 开发人员辅助功能， 可访问的网站， 边缘， Web 开发， ARIA， 开发人员， UIA， UI 自动化
ms.custom: seodec18
ms.openlocfilehash: 69f0576b39815708d01477972abad1f8bdc9486e
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397886"
---
# <a name="building-accessible-websites"></a><span data-ttu-id="4e265-104">构建可访问的网站</span><span class="sxs-lookup"><span data-stu-id="4e265-104">Building Accessible Websites</span></span>

<span data-ttu-id="4e265-105">Web 填充了动态且复杂的网站、应用程序和用户界面，这些网站、应用程序和用户界面是使用 HTML、CSS 和 JavaScript 的组合构建的。</span><span class="sxs-lookup"><span data-stu-id="4e265-105">The web is filled with dynamic and complex websites, applications, and user interfaces built using a combination of HTML, CSS, and JavaScript.</span></span>  <span data-ttu-id="4e265-106">但是，当在未考虑辅助功能的情况下设计和构建这些复杂网站时，依赖辅助技术浏览 Web 的人很难使用这些[](https://webaim.org/articles/motor/assistive)复杂网站。</span><span class="sxs-lookup"><span data-stu-id="4e265-106">However, when designed and built without accessibility in mind, these complex websites are difficult to use by people who rely on [assistive technologies](https://webaim.org/articles/motor/assistive) to browse the web.</span></span> <span data-ttu-id="4e265-107">构建残障人士可访问的网站需要有关用户界面的语义信息。</span><span class="sxs-lookup"><span data-stu-id="4e265-107">Building websites that are accessible to people with disabilities requires semantic information about the user interface.</span></span> <span data-ttu-id="4e265-108">这允许辅助技术（如屏幕阅读器）传达必要的信息，以帮助具有各种能力的人使用网站。</span><span class="sxs-lookup"><span data-stu-id="4e265-108">This allows for assistive technologies, like screen readers, to convey the necessary information to help people with a range of abilities use the website.</span></span>

<span data-ttu-id="4e265-109">有关 Microsoft Edge 支持哪些新 HTML5 功能的信息，请访问[HTML5Accessibility。](https://html5accessibility.com)</span><span class="sxs-lookup"><span data-stu-id="4e265-109">Visit [HTML5Accessibility](https://html5accessibility.com) for information on which new HTML5 features are accessibly supported by Microsoft Edge.</span></span>

## <a name="how-accessibility-works"></a><span data-ttu-id="4e265-110">辅助功能的工作原理</span><span class="sxs-lookup"><span data-stu-id="4e265-110">How Accessibility Works</span></span>

<span data-ttu-id="4e265-111">辅助技术增加了计算机通常没有的功能。</span><span class="sxs-lookup"><span data-stu-id="4e265-111">Assistive technologies add capabilities that computers don't usually have.</span></span> <span data-ttu-id="4e265-112">例如，视觉受损的用户可能将键盘与辅助技术（如屏幕阅读器）结合使用，而不是直接将浏览器与鼠标和屏幕结合使用。</span><span class="sxs-lookup"><span data-stu-id="4e265-112">For example, a visually impaired user might use their keyboard in combination with assistive technology such as a screen reader, rather than directly using the browser with the mouse and screen.</span></span> <span data-ttu-id="4e265-113">对于 Microsoft 平台和 Web 上的应用程序，辅助技术与 Microsoft [UI 自动化](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx)、特定于应用程序的对象模型（如 Microsoft Edge 中的文档对象模型 (DOM) ）或它们的组合进行交互。</span><span class="sxs-lookup"><span data-stu-id="4e265-113">For applications on Microsoft platforms and on the web, the assistive technology interacts with Microsoft [UI Automation](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx), an application-specific object model such as the Document Object Model (DOM) in Microsoft Edge, or a combination of these.</span></span>

<span data-ttu-id="4e265-114">对于 Web 开发人员，某些 HTML 元素映射到 UI 自动化对象，因此在选择这些 HTML 元素时，开发人员可以使用这些元素中内置的辅助功能属性和事件。</span><span class="sxs-lookup"><span data-stu-id="4e265-114">For web developers, certain HTML elements are mapped to UI Automation objects, so in selecting those HTML elements, the developer can use the accessibility properties and events built in to those elements.</span></span> <span data-ttu-id="4e265-115">在开发网站时，通常只需确保 API 正确写入 (或指定适当的元素) ，以便应用程序可访问。</span><span class="sxs-lookup"><span data-stu-id="4e265-115">While developing your website, you usually only need to be concerned with ensuring that the API is correctly written to (or that the appropriate element is specified), in order for the application to be accessible.</span></span> <span data-ttu-id="4e265-116">有关详细信息， [请查看 Microsoft Edge 中的 ARIA](./ARIA-and-UI-Automation.md) 和 UI 自动化。</span><span class="sxs-lookup"><span data-stu-id="4e265-116">Check out [ARIA and UI Automation in Microsoft Edge](./ARIA-and-UI-Automation.md) for more information.</span></span>  <span data-ttu-id="4e265-117">有关辅助通用 Windows 平台 (UWP) 的信息，请导航到 Windows 开发人员中心[](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility)中的辅助功能主题。</span><span class="sxs-lookup"><span data-stu-id="4e265-117">For information on accessible Universal Windows Platform (UWP) apps, navigate to the [Accessibility](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility) topic in the Windows Dev Center.</span></span>

<span data-ttu-id="4e265-118">通过良好的编码实践，可以解决与动态内容相关的许多常见辅助功能问题，并且 [WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629) 文档包括许多技术和最佳做法，可帮助您创建更易于访问的动态 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4e265-118">Many common accessibility issues with dynamic content can be addressed by good coding practice, and the [WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629) documentation includes many techniques and best practices to help you create more accessible dynamic web applications.</span></span> <span data-ttu-id="4e265-119">但是，即使正确编码，动态内容也并不一定可访问。</span><span class="sxs-lookup"><span data-stu-id="4e265-119">Even when coded properly, however, dynamic content is not necessarily accessible.</span></span> <span data-ttu-id="4e265-120">[可访问的富 Internet 应用程序 (ARIA) ](#aria) 可帮助解决此问题。</span><span class="sxs-lookup"><span data-stu-id="4e265-120">[Accessible Rich Internet Applications (ARIA)](#aria) helps overcome this issue.</span></span>  

<span data-ttu-id="4e265-121">有关 Web 辅助功能详细信息，请查看 WEB[](https://www.w3.org/WAI/intro/accessibility.php)辅助功能计划与一个或多个组织 (WEB 辅助功能[) 。 ](https://www.w3.org/WAI)</span><span class="sxs-lookup"><span data-stu-id="4e265-121">For more information on web accessibility, check out the [Introduction to Web Accessibility](https://www.w3.org/WAI/intro/accessibility.php) by the [Web Accessibility Initiative (WAI)](https://www.w3.org/WAI).</span></span>

## <a name="aria"></a><span data-ttu-id="4e265-122">ARIA</span><span class="sxs-lookup"><span data-stu-id="4e265-122">ARIA</span></span>

<span data-ttu-id="4e265-123">W3C 的 Web 辅助功能计划 (ARIA) 规范将可访问的富 Internet [](https://www.w3.org/WAI/) [应用程序](https://www.w3.org/TR/wai-aria/)定义为使所有人员均可访问动态 Web 内容和自定义用户界面的语法。</span><span class="sxs-lookup"><span data-stu-id="4e265-123">The [Accessible Rich Internet Applications](https://www.w3.org/TR/wai-aria/) (ARIA) specification by the W3C's [Web Accessibility Initiative](https://www.w3.org/WAI/) defines as a syntax for making dynamic web content and custom user interfaces accessible to all people.</span></span> <span data-ttu-id="4e265-124">ARIA 通过使用其他属性扩展 HTML (角色、属性和状态) 旨在传达自定义语义。</span><span class="sxs-lookup"><span data-stu-id="4e265-124">ARIA extends HTML by using additional attributes (roles, properties, and states) that are designed to convey custom semantics.</span></span> <span data-ttu-id="4e265-125">浏览器使用这些属性将控件的状态和角色传递给辅助功能 API。</span><span class="sxs-lookup"><span data-stu-id="4e265-125">These attributes are used by browsers to pass along the controls' state and role to the accessibility API.</span></span>

### <a name="roles-properties-and-states"></a><span data-ttu-id="4e265-126">角色、属性和状态</span><span class="sxs-lookup"><span data-stu-id="4e265-126">Roles, Properties, and States</span></span>

<span data-ttu-id="4e265-127">ARIA 角色使用属性在元素上设置，以提供有关元素的辅助技术和辅助功能 [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) API 信息。</span><span class="sxs-lookup"><span data-stu-id="4e265-127">ARIA roles are set on elements using the [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) attribute to give assistive technologies and accessibility APIs information about the element.</span></span> <span data-ttu-id="4e265-128">例如，分配以下元素以表示 `<li>` 它是菜单中 `role="menuitem"` 的项。</span><span class="sxs-lookup"><span data-stu-id="4e265-128">For example, the below `<li>` element is assigned `role="menuitem"` to signify it's an item in a menu.</span></span>

```html
<li role="menuitem">Home</li>
```

<span data-ttu-id="4e265-129">ARIA 状态和属性是 Aria 前缀的属性，可提供有关对象的特定信息，以帮助形成角色性质的定义。</span><span class="sxs-lookup"><span data-stu-id="4e265-129">ARIA states and properties are aria-prefixed attributes that provide specific information about an object to help form the definition of the nature of roles.</span></span> <span data-ttu-id="4e265-130">属性是对于对象的性质至关重要的属性，如 [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx) 和 。</span><span class="sxs-lookup"><span data-stu-id="4e265-130">Properties are attributes that are essential to the nature of an object, like [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) and [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx).</span></span> <span data-ttu-id="4e265-131">更改属性会影响对象的含义。</span><span class="sxs-lookup"><span data-stu-id="4e265-131">Changing a property affects the meaning of the object.</span></span> <span data-ttu-id="4e265-132">在下面的示例中，该属性在菜单项上设置， `aria-haspopup="true"` `<li>` 以表示其具有弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="4e265-132">In the example below, the property `aria-haspopup="true"` is set on a `<li>` menu item to signify it has a popup.</span></span>

```html
<li role="menuitem" aria-haspopup="true">Open</li>
```

<span data-ttu-id="4e265-133">状态不会更改对象的性质，但表示与对象或用户与对象交互（如 [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) 或）关联的信息 [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx) 。</span><span class="sxs-lookup"><span data-stu-id="4e265-133">States do not change the nature of the object, but represent information associated with the object or user interaction with the object, like [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) or [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx).</span></span> <span data-ttu-id="4e265-134">例如，以下示例 `aria-checked="false"` 中的状态表示复选框未选中。</span><span class="sxs-lookup"><span data-stu-id="4e265-134">For example, the state `aria-checked="false"` in the example below represents that the checkbox is not checked.</span></span>

```html
<div role="checkbox" aria-checked="false">Accept</div>
```

<span data-ttu-id="4e265-135">转到 [W3C 的角色](https://www.w3.org/TR/wai-aria-1.1/#roles) 模型以查看角色、属性和状态的完整列表。</span><span class="sxs-lookup"><span data-stu-id="4e265-135">Go to [The Roles Model](https://www.w3.org/TR/wai-aria-1.1/#roles) by the W3C to see a full list of roles, properties, and states.</span></span>

<span data-ttu-id="4e265-136">有关 ARIA 的信息，请导航到"资源" [部分中的](#resources) ARIA。</span><span class="sxs-lookup"><span data-stu-id="4e265-136">For more information on ARIA, navigate to ARIA in the [Resources](#resources) section.</span></span>

## <a name="assistive-technology-compatibility-testing"></a><span data-ttu-id="4e265-137">辅助技术兼容性测试</span><span class="sxs-lookup"><span data-stu-id="4e265-137">Assistive Technology Compatibility Testing</span></span>  

<span data-ttu-id="4e265-138">验证要构建的网站是否使用真实的辅助技术是确保残障用户获得良好体验的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="4e265-138">Verifying that the website you are building works with real assistive technologies is the best way to ensure a good experience for your users with disabilities.</span></span>  <span data-ttu-id="4e265-139">由于许多辅助技术都使用键盘，因此测试网站的键盘辅助功能是一个很好的起点。</span><span class="sxs-lookup"><span data-stu-id="4e265-139">Since many assistive technologies make use of the keyboard, testing the keyboard accessibility of your website is a good place to start.</span></span>  <span data-ttu-id="4e265-140">[键盘兼容性][W3cPerspectiveVideosKeyboard] 测试验证用户是否无需鼠标即可访问所有交互式控件。</span><span class="sxs-lookup"><span data-stu-id="4e265-140">[Keyboard compatibility testing][W3cPerspectiveVideosKeyboard] validates that users have access to all interactive controls without requiring a mouse.</span></span>  <span data-ttu-id="4e265-141">Microsoft [Accessibility Insights for Web][AccessibilityinsightsWebOverview] 是 Microsoft Edge 和 Chrome 的浏览器扩展，可指导你并展示一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="4e265-141">Microsoft [Accessibility Insights for Web][AccessibilityinsightsWebOverview] is a browser extension for Microsoft Edge and Chrome that guides you and reveals several common issues.</span></span>  

<span data-ttu-id="4e265-142">一旦确信您的网站能很好地使用键盘，请尝试使用其他辅助技术（如屏幕阅读器）。</span><span class="sxs-lookup"><span data-stu-id="4e265-142">Once you are confident that your website works well with a keyboard, try it with other assistive technologies, such as screen readers.</span></span>  <span data-ttu-id="4e265-143">它可发现以下问题。</span><span class="sxs-lookup"><span data-stu-id="4e265-143">It uncover issues in the following.</span></span>

*   <span data-ttu-id="4e265-144">HTML、ARIA 和 CSS。</span><span class="sxs-lookup"><span data-stu-id="4e265-144">Your HTML, ARIA, and CSS.</span></span>  
*   <span data-ttu-id="4e265-145">对功能或技术的辅助技术的支持级别。</span><span class="sxs-lookup"><span data-stu-id="4e265-145">The level of support of an assistive technology for a feature or technique.</span></span>  
    
<span data-ttu-id="4e265-146">与 Microsoft Edge 不同，不同的浏览器可能会将元素映射到平台辅助功能 API。</span><span class="sxs-lookup"><span data-stu-id="4e265-146">Different browsers may map elements to platform accessibility APIs differently than Microsoft Edge.</span></span>  <span data-ttu-id="4e265-147">在构建接口时，考虑每个差异非常重要。</span><span class="sxs-lookup"><span data-stu-id="4e265-147">While building your interface, it is important to consider each difference.</span></span>  

<span data-ttu-id="4e265-148">WebAIM 使用屏幕阅读器[][WebaimProjectsScreenreadersurvey8]和低视力[][WebaimProjectsLowvisionsurvey2]用户进行调查，帮助你确定要测试的辅助技术和浏览器。</span><span class="sxs-lookup"><span data-stu-id="4e265-148">WebAIM conducts surveys with [screen reader][WebaimProjectsScreenreadersurvey8] and [low vision][WebaimProjectsLowvisionsurvey2] users that help you decide which assistive technologies and browsers you want to test.</span></span>  

### <a name="learning-how-to-test"></a><span data-ttu-id="4e265-149">了解如何测试</span><span class="sxs-lookup"><span data-stu-id="4e265-149">Learning How to Test</span></span>  

<span data-ttu-id="4e265-150">辅助技术是复杂的工具。</span><span class="sxs-lookup"><span data-stu-id="4e265-150">Assistive technologies are sophisticated tools.</span></span>  <span data-ttu-id="4e265-151">不要假定你能够立即开始使用辅助技术进行测试，而无需先了解它的工作原理。</span><span class="sxs-lookup"><span data-stu-id="4e265-151">Do not assume that you are able to immediately start testing with an assistive technology without first learning about how it works.</span></span>  <span data-ttu-id="4e265-152">学习使用屏幕阅读器进行测试有一条特别多深的学习曲线。</span><span class="sxs-lookup"><span data-stu-id="4e265-152">Learning to test with a screen reader has an especially steep learning curve.</span></span>  <span data-ttu-id="4e265-153">屏幕阅读器用户可能假定问题与误用屏幕阅读器有关时出现屏幕阅读器 bug。</span><span class="sxs-lookup"><span data-stu-id="4e265-153">A novice screen reader user may assume that a screen reader bug has occurred while the issue is related to misuse of the screen reader.</span></span>  

<span data-ttu-id="4e265-154">若要详细了解如何学习使用辅助技术进行测试，请导航到在 WebAIM 上使用屏幕 [阅读器][WebaimArticlesScreenreaderTesting] 进行测试。</span><span class="sxs-lookup"><span data-stu-id="4e265-154">For more information about learning to test with assistive technologies, navigate to [Testing with Screen Readers][WebaimArticlesScreenreaderTesting] on WebAIM.</span></span>  

### <a name="testing-locally"></a><span data-ttu-id="4e265-155">在本地测试</span><span class="sxs-lookup"><span data-stu-id="4e265-155">Testing Locally</span></span>  

<span data-ttu-id="4e265-156">大多数设备包括内置于操作系统的辅助技术。</span><span class="sxs-lookup"><span data-stu-id="4e265-156">Most devices include assistive technology that is built-in to the OS.</span></span>  <span data-ttu-id="4e265-157">Microsoft Windows 包括 [Windows 讲述人][MicrosoftSupport22798] 屏幕阅读器和 [Windows 放大镜][MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198]。</span><span class="sxs-lookup"><span data-stu-id="4e265-157">Microsoft Windows includes the [Windows Narrator][MicrosoftSupport22798] screen reader and [Windows Magnifier][MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198].</span></span>  <span data-ttu-id="4e265-158">第三方辅助技术（如[NVDA、FreedomscientificSoftwareJaws]和[ZoomText）][FreedomscientificSoftwareZoomtext]可供下载。 [][NvaccessAboutNvda]</span><span class="sxs-lookup"><span data-stu-id="4e265-158">3rd party assistive technologies like [NVDA][NvaccessAboutNvda], [FreedomscientificSoftwareJaws], and [ZoomText][FreedomscientificSoftwareZoomtext] are available to download.</span></span>  <span data-ttu-id="4e265-159">Apple macOS 包括 [VoiceOver][AppleAccessibilityMacVision] 屏幕阅读器。</span><span class="sxs-lookup"><span data-stu-id="4e265-159">Apple macOS includes the [VoiceOver][AppleAccessibilityMacVision] screen reader.</span></span>  <span data-ttu-id="4e265-160">并且 iOS、Android 和 Linux 都支持各种辅助技术。</span><span class="sxs-lookup"><span data-stu-id="4e265-160">And iOS, Android, and Linux all support a variety of assistive technologies.</span></span>  

### <a name="testing-in-virtual-machines-and-emulators"></a><span data-ttu-id="4e265-161">在虚拟机和仿真器中进行测试</span><span class="sxs-lookup"><span data-stu-id="4e265-161">Testing in Virtual Machines and Emulators</span></span>  

<span data-ttu-id="4e265-162">在 macOS 下，如果你希望使用仅适用于 Windows 的辅助技术（如 Windows 讲述人或 NVDA）进行测试，请创建 Windows 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="4e265-162">Under macOS, if you want to test with an assistive technology only available for Windows, like Windows Narrator or NVDA, create a Windows virtual machine.</span></span>  <span data-ttu-id="4e265-163">具有 Microsoft Edge \(EdgeHTML\) 和 IE 的虚拟机可用于虚拟机下载页面上的 VirtualBox 和[VMWare。][MicrosoftDeveloperEdgeVms]</span><span class="sxs-lookup"><span data-stu-id="4e265-163">Virtual machines with Microsoft Edge \(EdgeHTML\) and IE are available for VirtualBox and VMWare on the [Virtual Machines download page][MicrosoftDeveloperEdgeVms].</span></span>  

<span data-ttu-id="4e265-164">[Android Studio][AndroidDeveloperSdkInstallingStudioHtml] 包含一个仿真器，用于测试 [Android 辅助功能套件中的辅助技术][GooglePlayStoreAndroidAccessibilitySuite]。</span><span class="sxs-lookup"><span data-stu-id="4e265-164">[Android Studio][AndroidDeveloperSdkInstallingStudioHtml] includes an emulator that for you to test assistive technologies in the [Android Accessibility Suite][GooglePlayStoreAndroidAccessibilitySuite].</span></span>  <span data-ttu-id="4e265-165">按照说明 [设置虚拟设备][AndroidDeveloperDevicesManagingAvdsHtml] 并 [启动仿真][AndroidDeveloperDevicesEmulatorHtml]器，然后从 GooglePlay 商店安装 [Android][GooglePlayStoreAndroidAccessibilitySuite] 辅助功能套件。</span><span class="sxs-lookup"><span data-stu-id="4e265-165">Follow the instructions to [set up a virtual device][AndroidDeveloperDevicesManagingAvdsHtml] and [start the emulator][AndroidDeveloperDevicesEmulatorHtml], then install [Android Accessibility Suite][GooglePlayStoreAndroidAccessibilitySuite] from the GooglePlay store.</span></span>  

> [!NOTE]
> <span data-ttu-id="4e265-166">iOS 模拟器当前不包括 VoiceOver。</span><span class="sxs-lookup"><span data-stu-id="4e265-166">The iOS Simulator does not currently include VoiceOver.</span></span>  

### <a name="cloud-based-testing-tools"></a><span data-ttu-id="4e265-167">基于云的测试工具</span><span class="sxs-lookup"><span data-stu-id="4e265-167">Cloud-based Testing Tools</span></span>  

<span data-ttu-id="4e265-168">如果辅助技术在你的操作系统上不可用，或者你无法将辅助技术安装在虚拟机或仿真器上，则基于云的辅助技术测试工具是下一个最佳方法。</span><span class="sxs-lookup"><span data-stu-id="4e265-168">If an assistive technology is not available on your OS or you not possible to install one on a virtual machine or emulator, cloud-based assistive technology testing tools are the next best thing.</span></span>  

*   <span data-ttu-id="4e265-169">[Assistiv Labs (商业) ][AssistivlabsMain] 使你可以通过任何新式 Web 浏览器手动测试辅助技术。</span><span class="sxs-lookup"><span data-stu-id="4e265-169">[Assistiv Labs (commercial)][AssistivlabsMain] enables you to manually test with assistive technologies through any modern web browser.</span></span>  <span data-ttu-id="4e265-170">选择辅助技术和浏览器，它将你与可以交互的虚拟机、仿真器或真实设备相连接。</span><span class="sxs-lookup"><span data-stu-id="4e265-170">Choose an assistive technology and browser and it connects you with a virtual machine, emulator, or real device with which you may interact.</span></span>  

## <a name="resources"></a><span data-ttu-id="4e265-171">资源</span><span class="sxs-lookup"><span data-stu-id="4e265-171">Resources</span></span>

### <a name="accessibility-basics"></a><span data-ttu-id="4e265-172">辅助功能基础知识</span><span class="sxs-lookup"><span data-stu-id="4e265-172">Accessibility Basics</span></span>

#### [<a name="the-a11y-project"></a><span data-ttu-id="4e265-173">A11Y 项目</span><span class="sxs-lookup"><span data-stu-id="4e265-173">The A11Y Project</span></span>](http://a11yproject.com/)

<span data-ttu-id="4e265-174">A11Y 项目是社区推动的一项工作，用于简化 Web 辅助功能。</span><span class="sxs-lookup"><span data-stu-id="4e265-174">The A11Y Project is a community-driven effort to make web accessibility easier.</span></span> <span data-ttu-id="4e265-175">查看[A11Y 项目](https://a11yproject.com/)网站，了解基本的辅助功能原则、辅助功能模式和小组件库，以及辅助功能[](https://a11yproject.com/patterns)软件、博客、[](http://a11yproject.com/resources.html)书籍和工具上的资源。</span><span class="sxs-lookup"><span data-stu-id="4e265-175">Check out [The A11Y Project](https://a11yproject.com/) site to learn about basic accessibility principles, their accessible pattern and widget [library](https://a11yproject.com/patterns), and their [resources](http://a11yproject.com/resources.html) on accessibility software, blogs, books, and tools.</span></span>

#### [<a name="web-accessibility-initiative-wai"></a><span data-ttu-id="4e265-176">WEB 辅助功能计划 (的或) </span><span class="sxs-lookup"><span data-stu-id="4e265-176">Web Accessibility Initiative (WAI)</span></span>](https://w3.org/WAI/)

<span data-ttu-id="4e265-177">W3C Web 辅助功能计划 (或) 是一项帮助改进 Web 辅助功能的工作。</span><span class="sxs-lookup"><span data-stu-id="4e265-177">The W3C Web Accessibility Initiative (WAI) is an effort to help improve the accessibility of the web.</span></span> <span data-ttu-id="4e265-178">他们的网站为 Web 辅助功能入门[](https://www.w3.org/WAI/gettingstarted/Overview.html)、包含设计、教程和演示文稿[](https://www.w3.org/WAI/users/Overview.html)等提供了各种资源。 [](https://www.w3.org/WAI/train.html)</span><span class="sxs-lookup"><span data-stu-id="4e265-178">Their site provides a variety of resources for [Getting Started with Web Accessibility](https://www.w3.org/WAI/gettingstarted/Overview.html), [Designing for Inclusion](https://www.w3.org/WAI/users/Overview.html), [tutorials and presentations](https://www.w3.org/WAI/train.html), and more.</span></span>

### <a name="accessibility-blogs"></a><span data-ttu-id="4e265-179">辅助功能博客</span><span class="sxs-lookup"><span data-stu-id="4e265-179">Accessibility Blogs</span></span>

#### [<a name="the-paciello-group"></a><span data-ttu-id="4e265-180">Paciello 组</span><span class="sxs-lookup"><span data-stu-id="4e265-180">The Paciello Group</span></span>](https://www.paciellogroup.com/blog/)

<span data-ttu-id="4e265-181">Paciello 组向世界各地的组织提供咨询服务和技术解决方案，以确保他们的客户在满足政府标准和国际标准的同时有效且高效地覆盖所有受众。</span><span class="sxs-lookup"><span data-stu-id="4e265-181">The Paciello Group provides consulting and technology solutions to organizations around the world to ensure their clients reach all audiences effectively and efficiently, while meeting governmental and international standards.</span></span> <span data-ttu-id="4e265-182">他们的博客涵盖了 Web 辅助功能最佳实践、辅助功能工具和辅助功能趋势等主题。</span><span class="sxs-lookup"><span data-stu-id="4e265-182">Their blog covers topics like web accessibility best practices, accessibility tools, and accessibility trends.</span></span>

#### [<a name="simply-accessible"></a><span data-ttu-id="4e265-183">易于访问</span><span class="sxs-lookup"><span data-stu-id="4e265-183">Simply Accessible</span></span>](http://simplyaccessible.com/articles/)

<span data-ttu-id="4e265-184">"仅可访问"是一个辅助功能专家团队，提供辅助功能培训、咨询等，以更改对 Web 上辅助功能的感知。</span><span class="sxs-lookup"><span data-stu-id="4e265-184">Simply Accessible is a team of accessibility specialists providing accessibility training, consulting and more to change the perception of accessibility on the web.</span></span> <span data-ttu-id="4e265-185">他们 [的文章](http://simplyaccessible.com/articles/) 部分讨论了 Web 辅助功能、辅助设计等的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="4e265-185">Their [Articles](http://simplyaccessible.com/articles/) section discusses best practices for web accessibility, accessible design, and more.</span></span>

#### [<a name="ssb-bart-group-ssb"></a><span data-ttu-id="4e265-186">SSB BART 组 (SSB) </span><span class="sxs-lookup"><span data-stu-id="4e265-186">SSB BART Group (SSB)</span></span>](http://www.ssbbartgroup.com/blog/)

<span data-ttu-id="4e265-187">SSB BART 组是一家数字辅助功能公司，支持其客户开发并部署辅助产品和服务。</span><span class="sxs-lookup"><span data-stu-id="4e265-187">SSB BART Group is a digital accessibility firm supporting their clients in developing and deploying accessible products and services.</span></span> <span data-ttu-id="4e265-188">他们的博客介绍 ARIA 最佳实践、辅助功能趋势、网络研讨会等主题。</span><span class="sxs-lookup"><span data-stu-id="4e265-188">Their blog addresses topics like ARIA best practices, accessibility trends, webinars, and more.</span></span>

### <a name="accessible-examples"></a><span data-ttu-id="4e265-189">辅助示例</span><span class="sxs-lookup"><span data-stu-id="4e265-189">Accessible Examples</span></span>

#### [<a name="allyjs---tutorials"></a><span data-ttu-id="4e265-190">ally.js - 教程</span><span class="sxs-lookup"><span data-stu-id="4e265-190">ally.js - Tutorials</span></span>](http://allyjs.io/tutorials/)

<span data-ttu-id="4e265-191">JavaScript 库，通过简化辅助功能来帮助新式 Web 应用程序处理辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="4e265-191">JavaScript library to help modern web applications with accessibility concerns by making accessibility simpler.</span></span>

#### [<a name="heydonworks---aria-examples"></a><span data-ttu-id="4e265-192">Donworks - ARIA 示例</span><span class="sxs-lookup"><span data-stu-id="4e265-192">Heydonworks - ARIA Examples</span></span>](http://heydonworks.com/practical_aria_examples/)

<span data-ttu-id="4e265-193">增强应用程序辅助功能的实际 ARIA 示例</span><span class="sxs-lookup"><span data-stu-id="4e265-193">Practical ARIA examples to enhance your application accessibility</span></span>

#### [<a name="openajax-examples"></a><span data-ttu-id="4e265-194">OpenAjax 示例</span><span class="sxs-lookup"><span data-stu-id="4e265-194">OpenAjax Examples</span></span>](http://oaa-accessibility.org/)

<span data-ttu-id="4e265-195">OpenAjax 联盟网站是一个出色的资源，用于验证一些与一些功能或产品/服务或产品/服务或产品或产品/服务或产品/服务有关。</span><span class="sxs-lookup"><span data-stu-id="4e265-195">The OpenAjax Alliance website is an excellent resource for verifying the rules for WAI-ARIA and provides a number of examples of WAI-ARIA implementations.</span></span>

#### [<a name="patterns"></a><span data-ttu-id="4e265-196">模式</span><span class="sxs-lookup"><span data-stu-id="4e265-196">Patterns</span></span>](http://a11yproject.com/patterns.html)

<span data-ttu-id="4e265-197">[A11Y 项目](http://a11yproject.com/) 提供了一个可访问小组件和模式（如菜单、按钮、工具提示等）的库。</span><span class="sxs-lookup"><span data-stu-id="4e265-197">[The A11Y Project](http://a11yproject.com/) offers a library of accessible widgets and patterns like menus, buttons, tooltips, and more.</span></span>

### <a name="accessibility-techniques--tools"></a><span data-ttu-id="4e265-198">辅助功能技术&工具</span><span class="sxs-lookup"><span data-stu-id="4e265-198">Accessibility Techniques & Tools</span></span>

#### [<a name="accessibility-creating-accessible-extension-icons-for-microsoft-edge"></a><span data-ttu-id="4e265-199">辅助功能：为 Microsoft Edge 创建辅助扩展图标</span><span class="sxs-lookup"><span data-stu-id="4e265-199">Accessibility: Creating accessible extension icons for Microsoft Edge</span></span>](../../edgehtml/extensions/guides/accessibility.md)

<span data-ttu-id="4e265-200">获取有关为 Microsoft Edge 创建辅助扩展图标的指南。</span><span class="sxs-lookup"><span data-stu-id="4e265-200">Get guidance on creating accessible extensions icons for Microsoft Edge.</span></span>

#### [<a name="accessible-name-and-description-computation-and-mappings-11"></a><span data-ttu-id="4e265-201">辅助名称和说明：计算和映射 1.1</span><span class="sxs-lookup"><span data-stu-id="4e265-201">Accessible Name and Description: Computation and Mappings 1.1</span></span>](https://www.w3.org/TR/accname-1.1/)

<span data-ttu-id="4e265-202">此 W3C 映射文档说明了浏览器如何确定 Web 内容语言的可访问对象的名称和说明，以及如何在辅助功能 API 中公开这些对象。</span><span class="sxs-lookup"><span data-stu-id="4e265-202">This W3C mapping document explains how browsers determine name and descriptions of accessible objects from web content languages and expose them in accessibility APIs.</span></span>

#### [<a name="accessibility-evaluation-resources"></a><span data-ttu-id="4e265-203">辅助功能评估资源</span><span class="sxs-lookup"><span data-stu-id="4e265-203">Accessibility Evaluation Resources</span></span>](https://www.w3.org/WAI/eval/Overview.html)

<span data-ttu-id="4e265-204">辅助功能评估资源是 W3C 的多页资源，概述了评估网站辅助功能的不同方法。</span><span class="sxs-lookup"><span data-stu-id="4e265-204">Accessibility Evaluation Resources is a multi-page resource by the W3C that outlines different approaches for evaluating websites for accessibility.</span></span>

#### [<a name="assistive-technology-compatibility-tests"></a><span data-ttu-id="4e265-205">辅助技术兼容性测试</span><span class="sxs-lookup"><span data-stu-id="4e265-205">Assistive technology compatibility tests</span></span>](http://www.powermapper.com/tests/)

<span data-ttu-id="4e265-206">显示不同内容类型和标准在辅助技术与 AT (（如屏幕阅读器) 的行为）的测试结果。</span><span class="sxs-lookup"><span data-stu-id="4e265-206">Test results showing how different content types and standards behave in assistive technologies (AT) like screen readers.</span></span>

#### [<a name="building-accessible-websites-just-got-a-lot-easier"></a><span data-ttu-id="4e265-207">构建可访问的网站变得更加简单</span><span class="sxs-lookup"><span data-stu-id="4e265-207">Building accessible websites just got a lot easier</span></span>](https://blogs.msdn.microsoft.com/webdev/2016/05/02/building-accessible-websites-just-got-a-lot-easier/)

<span data-ttu-id="4e265-208">本 .NET Web 开发和工具博客文章介绍了Visual Studio Web [辅助功能检查器](https://go.microsoft.com/fwlink/p/?linkid=841539)。</span><span class="sxs-lookup"><span data-stu-id="4e265-208">This .NET Web Development and Tools blog post describes the Visual Studio extension [Web Accessibility Checker](https://go.microsoft.com/fwlink/p/?linkid=841539).</span></span>

#### [<a name="core-accessibility-api-mappings-11"></a><span data-ttu-id="4e265-209">核心辅助功能 API 映射 1.1</span><span class="sxs-lookup"><span data-stu-id="4e265-209">Core Accessibility API Mappings 1.1</span></span>](https://www.w3.org/TR/core-aam-1.1/)

<span data-ttu-id="4e265-210">此 W3C 映射文档说明如何向辅助功能 API 公开 Web 内容语言的语义。</span><span class="sxs-lookup"><span data-stu-id="4e265-210">This W3C mapping document explains how the semantics of web content languages are exposed to accessibility APIs.</span></span>  

#### [<a name="easy-checks--a-first-review-of-web-accessibility"></a><span data-ttu-id="4e265-211">轻松检查 – 首次查看 Web 辅助功能</span><span class="sxs-lookup"><span data-stu-id="4e265-211">Easy Checks – A First Review of Web Accessibility</span></span>](https://www.w3.org/WAI/eval/preliminary.html)

<span data-ttu-id="4e265-212">一系列由一系列 QUICK 检查的，可帮助您了解网页的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="4e265-212">A series of quick checks by the WAI that help you asses the accessibility of a web page.</span></span>

#### [<a name="how-to-meet-wcag-20"></a><span data-ttu-id="4e265-213">如何满足 WCAG 2.0</span><span class="sxs-lookup"><span data-stu-id="4e265-213">How to Meet WCAG 2.0</span></span>](https://www.w3.org/WAI/WCAG20/quickref/)

<span data-ttu-id="4e265-214">有关 Web 内容辅助功能指南 (WCAG) 2.0 要求 (成功标准) 和技术。</span><span class="sxs-lookup"><span data-stu-id="4e265-214">A quick reference to Web Content Accessibility Guidelines (WCAG) 2.0 requirements (success criteria) and techniques.</span></span>

#### [<a name="html-accessibility-api-mappings-10"></a><span data-ttu-id="4e265-215">HTML 辅助功能 API 映射 1.0</span><span class="sxs-lookup"><span data-stu-id="4e265-215">HTML Accessibility API Mappings 1.0</span></span>](https://www.w3.org/TR/html-aam-1.0/)

<span data-ttu-id="4e265-216">此 W3C 映射文档说明了 HTML5.1 元素和属性如何映射到平台辅助功能 API。</span><span class="sxs-lookup"><span data-stu-id="4e265-216">This W3C mappings document explains how HTML5.1 element and attributes map to platform accessibility APIs.</span></span>

#### [<a name="quick-tips"></a><span data-ttu-id="4e265-217">快速提示</span><span class="sxs-lookup"><span data-stu-id="4e265-217">Quick Tips</span></span>](http://a11yproject.com/#Quick-tips)

<span data-ttu-id="4e265-218">A11Y 项目辅助功能的快速 Web [开发提示列表](http://a11yproject.com/)。</span><span class="sxs-lookup"><span data-stu-id="4e265-218">A list of quick web development tips for accessibility by [The A11Y Project](http://a11yproject.com/).</span></span>

#### [<a name="site-scan"></a><span data-ttu-id="4e265-219">网站扫描</span><span class="sxs-lookup"><span data-stu-id="4e265-219">Site Scan</span></span>](https://developer.microsoft.com/microsoft-edge/tools/staticscan/)

<span data-ttu-id="4e265-220">Microsoft Edge 开发人员中心上的站点扫描工具会检查过时库、布局问题和辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="4e265-220">The Site Scan tool on Microsoft Edge Dev Center checks for out-of-date libraries, layout issues, and accessibility issues.</span></span>

#### [<a name="techniques-for-wcag-20"></a><span data-ttu-id="4e265-221">WCAG 2.0 的技术</span><span class="sxs-lookup"><span data-stu-id="4e265-221">Techniques for WCAG 2.0</span></span>](https://www.w3.org/TR/WCAG20-TECHS/Overview.html)

<span data-ttu-id="4e265-222">W3C 中的技术，为 Web 开发人员提供有关满足 Web 内容辅助功能指南 ([WCAG) 2.0](https://w3.org/TR/WCAG20/) 成功标准的指导。</span><span class="sxs-lookup"><span data-stu-id="4e265-222">Techniques from the W3C that provide guidance for web developers on meeting [Web Content Accessibility Guidelines (WCAG) 2.0](https://w3.org/TR/WCAG20/) success criteria.</span></span>

#### [<a name="tips-on-developing-for-web-accessibility"></a><span data-ttu-id="4e265-223">有关开发 Web 辅助功能的提示</span><span class="sxs-lookup"><span data-stu-id="4e265-223">Tips on Developing for Web Accessibility</span></span>](https://w3.org/WAI/gettingstarted/tips/developing.html)

<span data-ttu-id="4e265-224">W3C 中有关开发残障人士更容易访问的 Web 内容的提示。</span><span class="sxs-lookup"><span data-stu-id="4e265-224">Tips from the W3C on developing web content that is more accessible to people with disabilities.</span></span>

#### [<a name="wai-aria-authoring-practices-11"></a><span data-ttu-id="4e265-225">WAI-ARIA 创作实践 1.1</span><span class="sxs-lookup"><span data-stu-id="4e265-225">WAI-ARIA Authoring Practices 1.1</span></span>](http://w3c.github.io/aria-practices/)

<span data-ttu-id="4e265-226">W3C 提供的一个文档，为读者提供了如何使用 WIDGET-ARIA 1.1 的了解，并推荐了使小组件、导航和行为可通过使用 WIDGET-ARIA 角色、状态和属性访问的方法。</span><span class="sxs-lookup"><span data-stu-id="4e265-226">A document by the W3C that provides readers with an understanding of how to use WAI-ARIA 1.1 and recommends approaches to make widgets, navigation, and behaviors accessible using WAI-ARIA roles, states, and properties.</span></span>

#### [<a name="wai-guidelines-and-techniques"></a><span data-ttu-id="4e265-227">一些指南和技术</span><span class="sxs-lookup"><span data-stu-id="4e265-227">WAI Guidelines and Techniques</span></span>](https://w3.org/WAI/guid-tech.html)

<span data-ttu-id="4e265-228">由一系列 WEB 辅助功能指南和标准由</span><span class="sxs-lookup"><span data-stu-id="4e265-228">A series of web accessibility guidelines and standards developed by the WAI.</span></span>  

#### [<a name="web-accessibility-evaluation-tools-list"></a><span data-ttu-id="4e265-229">Web 辅助功能评估工具列表</span><span class="sxs-lookup"><span data-stu-id="4e265-229">Web Accessibility Evaluation Tools List</span></span>](https://www.w3.org/WAI/ER/tools/index.html)

<span data-ttu-id="4e265-230">可帮助确定网站是否满足辅助功能准则的 Web 辅助功能评估工具列表。</span><span class="sxs-lookup"><span data-stu-id="4e265-230">A list of web accessibility evaluation tools to help determine if websites meet accessibility guidelines.</span></span>

#### [<a name="web-accessibility-perspectives-explore-the-impact-and-benefits-for-everyone"></a><span data-ttu-id="4e265-231">Web 辅助功能角度：探索对所有人的影响和好处</span><span class="sxs-lookup"><span data-stu-id="4e265-231">Web Accessibility Perspectives: Explore the Impact and Benefits for Everyone</span></span>](https://w3.org/WAI/perspectives/)

<span data-ttu-id="4e265-232">W3C 关于辅助功能的影响和所有人的好处的一系列简短情景视频。</span><span class="sxs-lookup"><span data-stu-id="4e265-232">A series of short situational videos by the W3C about the impact of accessibility and the benefits for everyone.</span></span>

<!-- links -->  

<!--todo: link updates and acrolinx  -->  

[MicrosoftDeveloperEdgeVms]: https://developer.microsoft.com/microsoft-edge/tools/vms "虚拟机|Microsoft Edge 开发人员"  

[MicrosoftSupport22798]: https://support.microsoft.com/help/22798 "讲述人指南|Microsoft 支持"  
[MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198]: https://support.microsoft.com/windows/414948ba-8b1c-d3bd-8615-0e5e32204198 "使用放大镜使屏幕上的内容更易于查看|Microsoft 支持"  

[AccessibilityinsightsWebOverview]: https://accessibilityinsights.io/docs/web/overview "适用于 Web 网站的辅助功能见解|辅助功能见解"  

[AndroidDeveloperDevicesManagingAvdsHtml]: https://developer.android.com/tools/devices/managing-avds.html "创建和管理虚拟设备|Android 开发人员"  
[AndroidDeveloperDevicesEmulatorHtml]: https://developer.android.com/tools/devices/emulator.html "在 Android 仿真器设备上|Android 开发人员"  
[AndroidDeveloperSdkInstallingStudioHtml]: https://developer.android.com/sdk/installing/studio.html "下载 Android Studio |Android 开发人员"  

[AppleAccessibilityMacVision]: https://www.apple.com/accessibility/mac/vision "视觉辅助功能 - Mac |Apple"  

[AssistivlabsMain]: https://assistivlabs.com "Assistiv Labs"  

[FreedomscientificSoftwareJaws]: https://www.freedomscientific.com/products/software/jaws "JAWS® |Freedom Scientific"  
[FreedomscientificSoftwareZoomtext]: https://www.freedomscientific.com/products/software/zoomtext "ZoomText |Freedom Scientific"  

[GooglePlayStoreAndroidAccessibilitySuite]: https://play.google.com/store/apps/details?id=com.google.android.marvin.talkback "Android 辅助功能套件|GooglePlay 商店"  

[NvaccessAboutNvda]: https://www.nvaccess.org/about-nvda "关于 NVDA |NV 访问"  

[W3cPerspectiveVideosKeyboard]: https://www.w3.org/WAI/perspective-videos/keyboard "键盘兼容性|W3C"  

[WebaimProjectsLowvisionsurvey2]: https://webaim.org/projects/lowvisionsurvey2 "低视力用户调查 \#2结果|WebAIM"  
[WebaimProjectsScreenreadersurvey8]: https://webaim.org/projects/screenreadersurvey8 "屏幕阅读器用户调查 \#8结果|WebAIM"  
[WebaimArticlesScreenreaderTesting]: https://webaim.org/articles/screenreader_testing "使用屏幕阅读器测试|WebAIM"  
