---
ms.assetid: 1b3ebc25-d023-4f23-bbba-dce066c20de8
description: 演练 ARIA 应用程序与 ARIA (的最佳实践) 如何共同创建可访问的网站。
title: 生成|辅助功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: 辅助功能， 开发人员辅助功能， 可访问的网站， 边缘， Web 开发， ARIA， 开发人员， UIA， UI 自动化
ms.custom: seodec18
ms.openlocfilehash: 99f0eb9d96bc6d53df72839c6c2f1e61cbd5494e
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564019"
---
# <a name="building-accessible-websites"></a><span data-ttu-id="3d4e8-104">构建可访问的网站</span><span class="sxs-lookup"><span data-stu-id="3d4e8-104">Building Accessible Websites</span></span>  

<span data-ttu-id="3d4e8-105">Web 填充了动态且复杂的网站、应用程序和用户界面，这些网站、应用程序和用户界面是使用 HTML、CSS 和 JavaScript 的组合构建的。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-105">The web is filled with dynamic and complex websites, applications, and user interfaces built using a combination of HTML, CSS, and JavaScript.</span></span>  <span data-ttu-id="3d4e8-106">但是，当设计和构建时没有考虑辅助功能时，依赖辅助技术来浏览 Web 的人很难使用这些复杂的网站。 [](https://webaim.org/articles/motor/assistive)</span><span class="sxs-lookup"><span data-stu-id="3d4e8-106">However, when designed and built without accessibility in mind, these complex websites are difficult to use by people who rely on [assistive technologies](https://webaim.org/articles/motor/assistive) to browse the web.</span></span>  <span data-ttu-id="3d4e8-107">构建可供残障人士访问的网站需要有关用户界面的语义信息。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-107">Building websites that are accessible to people with disabilities requires semantic information about the user interface.</span></span>  <span data-ttu-id="3d4e8-108">这允许辅助技术（如屏幕阅读器）传达必要的信息，以帮助具有各种功能的人使用网站。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-108">This allows for assistive technologies, like screen readers, to convey the necessary information to help people with a range of abilities use the website.</span></span>  

<span data-ttu-id="3d4e8-109">访问[HTML5Accessibility，](https://html5accessibility.com)了解哪些新 HTML5 功能可供 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-109">Visit [HTML5Accessibility](https://html5accessibility.com) for information on which new HTML5 features are accessibly supported by Microsoft Edge.</span></span>  

## <a name="how-accessibility-works"></a><span data-ttu-id="3d4e8-110">辅助功能的工作原理</span><span class="sxs-lookup"><span data-stu-id="3d4e8-110">How Accessibility Works</span></span>  

<span data-ttu-id="3d4e8-111">辅助技术添加计算机通常没有的功能。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-111">Assistive technologies add capabilities that computers don't usually have.</span></span>  <span data-ttu-id="3d4e8-112">例如，视觉受损的用户可能将键盘与辅助技术（如屏幕阅读器）结合使用，而不是直接将浏览器与鼠标和屏幕结合使用。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-112">For example, a visually impaired user might use their keyboard in combination with assistive technology such as a screen reader, rather than directly using the browser with the mouse and screen.</span></span>  <span data-ttu-id="3d4e8-113">对于 Microsoft 平台和 Web 上的应用程序，辅助技术与 Microsoft [UI 自动化](/windows/win32/winauto/uiauto-specandcommunitypromise)、特定于应用程序的对象模型（如 Microsoft Edge 中的文档对象模型 \ (DOM\) ）或这些对象的组合交互。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-113">For applications on Microsoft platforms and on the web, the assistive technology interacts with Microsoft [UI Automation](/windows/win32/winauto/uiauto-specandcommunitypromise), an application-specific object model such as the Document Object Model \(DOM\) in Microsoft Edge, or a combination of these.</span></span>  

<span data-ttu-id="3d4e8-114">对于 Web 开发人员，某些 HTML 元素会映射到 UI 自动化对象，因此在选择这些 HTML 元素时，开发人员可以使用内置于这些元素的辅助功能属性和事件。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-114">For web developers, certain HTML elements are mapped to UI Automation objects, so in selecting those HTML elements, the developer can use the accessibility properties and events built in to those elements.</span></span>  <span data-ttu-id="3d4e8-115">开发网站时，通常只需关注确保 API 正确写入 \ (或指定适当的元素\) ，以便应用程序可访问。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-115">While developing your website, you usually only need to be concerned with ensuring that the API is correctly written to \(or that the appropriate element is specified\), in order for the application to be accessible.</span></span>  <span data-ttu-id="3d4e8-116">有关详细信息，[请参阅 ARIA 和 Microsoft Edge](./aria-and-ui-automation.md) UI 自动化。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-116">Check out [ARIA and UI Automation in Microsoft Edge](./aria-and-ui-automation.md) for more information.</span></span>  <span data-ttu-id="3d4e8-117">有关可访问的通用 Windows 平台 \ (UWP\) 应用的信息，请导航到 Windows 开发人员中心 中的辅助功能[](/windows/uwp/design/accessibility/accessibility)主题。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-117">For information on accessible Universal Windows Platform \(UWP\) apps, navigate to the [Accessibility](/windows/uwp/design/accessibility/accessibility) topic in the Windows Dev Center.</span></span>  

<span data-ttu-id="3d4e8-118">通过良好的编码实践，可以解决与动态内容相关的许多常见辅助功能问题，并且 [WCAG 2.0](https://www.w3.org/TR/WCAG20) 文档包括许多技术和最佳实践，可帮助你创建更易于访问的动态 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-118">Many common accessibility issues with dynamic content can be addressed by good coding practice, and the [WCAG 2.0](https://www.w3.org/TR/WCAG20) documentation includes many techniques and best practices to help you create more accessible dynamic web applications.</span></span>  <span data-ttu-id="3d4e8-119">但是，即使正确编码，也不必访问动态内容。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-119">Even when coded properly, however, dynamic content is not necessarily accessible.</span></span>  <span data-ttu-id="3d4e8-120">[可访问的富 Internet 应用程序 (ARIA) ](#aria) 可帮助解决此问题。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-120">[Accessible Rich Internet Applications (ARIA)](#aria) helps overcome this issue.</span></span>  

<span data-ttu-id="3d4e8-121">有关 Web 辅助功能详细信息，请参阅 Web[](https://www.w3.org/WAI/intro/accessibility.php)辅助功能计划为 WEB 辅助功能简介[ (一) 。 ](https://www.w3.org/WAI)</span><span class="sxs-lookup"><span data-stu-id="3d4e8-121">For more information on web accessibility, check out the [Introduction to Web Accessibility](https://www.w3.org/WAI/intro/accessibility.php) by the [Web Accessibility Initiative (WAI)](https://www.w3.org/WAI).</span></span>  

## <a name="aria"></a><span data-ttu-id="3d4e8-122">ARIA</span><span class="sxs-lookup"><span data-stu-id="3d4e8-122">ARIA</span></span>  

<span data-ttu-id="3d4e8-123">W3C 的 Web 辅助功能计划 ([ARIA) ARIA](https://www.w3.org/TR/wai-aria)规范定义为使[](https://www.w3.org/WAI)所有人员均可访问的动态 Web 内容和自定义用户界面的语法。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-123">The [Accessible Rich Internet Applications (ARIA)](https://www.w3.org/TR/wai-aria) specification by the W3C's [Web Accessibility Initiative](https://www.w3.org/WAI) defines as a syntax for making dynamic web content and custom user interfaces accessible to all people.</span></span>  <span data-ttu-id="3d4e8-124">ARIA 通过使用旨在传达自定义语义的其他属性 \ (角色、属性和状态\) 扩展 HTML。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-124">ARIA extends HTML by using additional attributes \(roles, properties, and states\) that are designed to convey custom semantics.</span></span>  <span data-ttu-id="3d4e8-125">浏览器使用这些属性将控件的状态和角色传递到辅助功能 API。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-125">These attributes are used by browsers to pass along the controls' state and role to the accessibility API.</span></span>  

### <a name="roles-properties-and-states"></a><span data-ttu-id="3d4e8-126">角色、属性和状态</span><span class="sxs-lookup"><span data-stu-id="3d4e8-126">Roles, Properties, and States</span></span>  

<span data-ttu-id="3d4e8-127">ARIA 角色使用 [role](https://developer.mozilla.org/docs/Web/HTML/Reference) 属性在元素上设置，以提供有关元素的辅助技术和辅助功能 API 信息。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-127">ARIA roles are set on elements using the [role](https://developer.mozilla.org/docs/Web/HTML/Reference) attribute to give assistive technologies and accessibility APIs information about the element.</span></span>  <span data-ttu-id="3d4e8-128">例如，分配以下 `<li>` 元素以 `role="menuitem"` 表示它是菜单中的项。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-128">For example, the below `<li>` element is assigned `role="menuitem"` to signify it's an item in a menu.</span></span>  

```html
<li role="menuitem">Home</li>
```  

<span data-ttu-id="3d4e8-129">ARIA 状态和属性是 aria 前缀的属性，可提供有关对象的特定信息，以帮助形成角色的性质的定义。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-129">ARIA states and properties are aria-prefixed attributes that provide specific information about an object to help form the definition of the nature of roles.</span></span>  <span data-ttu-id="3d4e8-130">属性是对象的性质所必不可少的属性，如 [aria-readonly](https://developer.mozilla.org/docs/Web/Accessibility/ARIA) 和 [aria-haspopup](https://developer.mozilla.org/docs/Web/Accessibility/ARIA)。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-130">Properties are attributes that are essential to the nature of an object, like [aria-readonly](https://developer.mozilla.org/docs/Web/Accessibility/ARIA) and [aria-haspopup](https://developer.mozilla.org/docs/Web/Accessibility/ARIA).</span></span>  <span data-ttu-id="3d4e8-131">更改属性会影响对象的含义。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-131">Changing a property affects the meaning of the object.</span></span>  <span data-ttu-id="3d4e8-132">在下面的示例中，属性 `aria-haspopup="true"` 在菜单项上设置 `<li>` ，以表示其具有弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-132">In the example below, the property `aria-haspopup="true"` is set on a `<li>` menu item to signify it has a popup.</span></span>  

```html
<li role="menuitem" aria-haspopup="true">Open</li>
```  

<span data-ttu-id="3d4e8-133">状态不会更改对象的性质，但表示与对象或用户与该对象的交互关联的信息，如 [aria 隐藏或](https://developer.mozilla.org/docs/Web/Accessibility/ARIA) [aria 检查](https://developer.mozilla.org/docs/Web/Accessibility/ARIA)。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-133">States do not change the nature of the object, but represent information associated with the object or user interaction with the object, like [aria-hidden](https://developer.mozilla.org/docs/Web/Accessibility/ARIA) or [aria-checked](https://developer.mozilla.org/docs/Web/Accessibility/ARIA).</span></span>  <span data-ttu-id="3d4e8-134">例如，以下示例 `aria-checked="false"` 中的状态表示复选框未选中。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-134">For example, the state `aria-checked="false"` in the example below represents that the checkbox is not checked.</span></span>  

```html
<div role="checkbox" aria-checked="false">Accept</div>
```  

<span data-ttu-id="3d4e8-135">转到 [W3C](https://www.w3.org/TR/wai-aria-1.1#roles) 的角色模型以查看角色、属性和状态的完整列表。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-135">Go to [The Roles Model](https://www.w3.org/TR/wai-aria-1.1#roles) by the W3C to see a full list of roles, properties, and states.</span></span>  

<span data-ttu-id="3d4e8-136">有关 ARIA 的信息，请导航到"资源" [部分中的](#resources) "ARIA"。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-136">For more information on ARIA, navigate to ARIA in the [Resources](#resources) section.</span></span>  

## <a name="assistive-technology-compatibility-testing"></a><span data-ttu-id="3d4e8-137">辅助技术兼容性测试</span><span class="sxs-lookup"><span data-stu-id="3d4e8-137">Assistive Technology Compatibility Testing</span></span>  

<span data-ttu-id="3d4e8-138">验证正在构建的网站是否使用真实的辅助技术是确保残障用户获得良好体验的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-138">Verifying that the website you are building works with real assistive technologies is the best way to ensure a good experience for your users with disabilities.</span></span>  <span data-ttu-id="3d4e8-139">由于许多辅助技术都使用键盘，因此测试网站的键盘辅助功能是一个很好的起点。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-139">Since many assistive technologies make use of the keyboard, testing the keyboard accessibility of your website is a good place to start.</span></span>  <span data-ttu-id="3d4e8-140">[键盘兼容性][W3cPerspectiveVideosKeyboard] 测试验证用户是否无需鼠标即可访问所有交互式控件。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-140">[Keyboard compatibility testing][W3cPerspectiveVideosKeyboard] validates that users have access to all interactive controls without requiring a mouse.</span></span>  <span data-ttu-id="3d4e8-141">Microsoft [Accessibility Insights for Web][AccessibilityinsightsWebOverview]是适用于 Microsoft Edge 和 Chrome 的浏览器扩展，可指导你并展示一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-141">Microsoft [Accessibility Insights for Web][AccessibilityinsightsWebOverview] is a browser extension for Microsoft Edge and Chrome that guides you and reveals several common issues.</span></span>  

<span data-ttu-id="3d4e8-142">一旦确信你的网站能很好地使用键盘，请通过其他辅助技术（如屏幕阅读器）试用它。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-142">Once you are confident that your website works well with a keyboard, try it with other assistive technologies, such as screen readers.</span></span>  <span data-ttu-id="3d4e8-143">它可发现以下问题。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-143">It uncover issues in the following.</span></span>  

*   <span data-ttu-id="3d4e8-144">您的 HTML、ARIA 和 CSS。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-144">Your HTML, ARIA, and CSS.</span></span>  
*   <span data-ttu-id="3d4e8-145">对功能或技术的辅助技术的支持级别。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-145">The level of support of an assistive technology for a feature or technique.</span></span>  
    
<span data-ttu-id="3d4e8-146">不同的浏览器可能将元素映射到平台辅助功能 API 的方式与Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-146">Different browsers may map elements to platform accessibility APIs differently than Microsoft Edge.</span></span>  <span data-ttu-id="3d4e8-147">在构建接口时，考虑每个差异非常重要。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-147">While building your interface, it is important to consider each difference.</span></span>  

<span data-ttu-id="3d4e8-148">WebAIM 与屏幕[阅读器][WebaimProjectsScreenreadersurvey8]和低视力[][WebaimProjectsLowvisionsurvey2]用户进行调查，帮助你确定要测试哪些辅助技术和浏览器。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-148">WebAIM conducts surveys with [screen reader][WebaimProjectsScreenreadersurvey8] and [low vision][WebaimProjectsLowvisionsurvey2] users that help you decide which assistive technologies and browsers you want to test.</span></span>  

### <a name="learning-how-to-test"></a><span data-ttu-id="3d4e8-149">了解如何测试</span><span class="sxs-lookup"><span data-stu-id="3d4e8-149">Learning How to Test</span></span>  

<span data-ttu-id="3d4e8-150">辅助技术是复杂的工具。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-150">Assistive technologies are sophisticated tools.</span></span>  <span data-ttu-id="3d4e8-151">不要假定你能够立即开始使用辅助技术进行测试，而无需首先了解它的工作原理。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-151">Do not assume that you are able to immediately start testing with an assistive technology without first learning about how it works.</span></span>  <span data-ttu-id="3d4e8-152">学习使用屏幕阅读器进行测试具有一个特别容易学习的曲线。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-152">Learning to test with a screen reader has an especially steep learning curve.</span></span>  <span data-ttu-id="3d4e8-153">当问题与误用屏幕阅读器有关时，屏幕阅读器用户可能会假设发生了屏幕阅读器 Bug。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-153">A novice screen reader user may assume that a screen reader bug has occurred while the issue is related to misuse of the screen reader.</span></span>  

<span data-ttu-id="3d4e8-154">有关学习使用辅助技术进行测试的信息，请导航到使用 WebAIM 上的 [屏幕][WebaimArticlesScreenreaderTesting] 阅读器进行测试。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-154">For more information about learning to test with assistive technologies, navigate to [Testing with Screen Readers][WebaimArticlesScreenreaderTesting] on WebAIM.</span></span>  

### <a name="testing-locally"></a><span data-ttu-id="3d4e8-155">本地测试</span><span class="sxs-lookup"><span data-stu-id="3d4e8-155">Testing Locally</span></span>  

<span data-ttu-id="3d4e8-156">大多数设备包括内置于操作系统的辅助技术。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-156">Most devices include assistive technology that is built-in to the OS.</span></span>  <span data-ttu-id="3d4e8-157">Microsoft Windows包括屏幕[阅读器Windows 讲述人][MicrosoftSupport22798]和Windows[放大镜][MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198]。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-157">Microsoft Windows includes the [Windows Narrator][MicrosoftSupport22798] screen reader and [Windows Magnifier][MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198].</span></span>  <span data-ttu-id="3d4e8-158">可以下载第三方辅助技术，如[NVDA、FreedomscientificSoftwareJaws]和[ZoomText。][FreedomscientificSoftwareZoomtext] [][NvaccessAboutNvda]</span><span class="sxs-lookup"><span data-stu-id="3d4e8-158">3rd party assistive technologies like [NVDA][NvaccessAboutNvda], [FreedomscientificSoftwareJaws], and [ZoomText][FreedomscientificSoftwareZoomtext] are available to download.</span></span>  <span data-ttu-id="3d4e8-159">Apple macOS 包括 [VoiceOver][AppleAccessibilityMacVision] 屏幕阅读器。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-159">Apple macOS includes the [VoiceOver][AppleAccessibilityMacVision] screen reader.</span></span>  <span data-ttu-id="3d4e8-160">iOS、Android 和 Linux 都支持各种辅助技术。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-160">And iOS, Android, and Linux all support a variety of assistive technologies.</span></span>  

### <a name="testing-in-virtual-machines-and-emulators"></a><span data-ttu-id="3d4e8-161">虚拟机和仿真器中的测试</span><span class="sxs-lookup"><span data-stu-id="3d4e8-161">Testing in Virtual Machines and Emulators</span></span>  

<span data-ttu-id="3d4e8-162">在 macOS 下，如果你希望使用仅适用于 Windows（如 Windows 讲述人 或 NVDA）的辅助技术进行测试，Windows虚拟机。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-162">Under macOS, if you want to test with an assistive technology only available for Windows, like Windows Narrator or NVDA, create a Windows virtual machine.</span></span>  <span data-ttu-id="3d4e8-163">具有 Microsoft Edge \ (EdgeHTML\) 和 IE 的虚拟机可用于虚拟机下载页上的 VirtualBox 和[VMWare。][MicrosoftDeveloperEdgeVms]</span><span class="sxs-lookup"><span data-stu-id="3d4e8-163">Virtual machines with Microsoft Edge \(EdgeHTML\) and IE are available for VirtualBox and VMWare on the [Virtual Machines download page][MicrosoftDeveloperEdgeVms].</span></span>  

<span data-ttu-id="3d4e8-164">[Android Studio][AndroidDeveloperSdkInstallingStudioHtml] 包含一个仿真器，用于测试 Android 辅助功能套件 [中的辅助技术][GooglePlayStoreAndroidAccessibilitySuite]。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-164">[Android Studio][AndroidDeveloperSdkInstallingStudioHtml] includes an emulator that for you to test assistive technologies in the [Android Accessibility Suite][GooglePlayStoreAndroidAccessibilitySuite].</span></span>  <span data-ttu-id="3d4e8-165">按照说明 [设置虚拟设备][AndroidDeveloperDevicesManagingAvdsHtml] 并启动 [仿真][AndroidDeveloperDevicesEmulatorHtml]器，然后从 GooglePlay 商店安装 [Android][GooglePlayStoreAndroidAccessibilitySuite] 辅助功能套件。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-165">Follow the instructions to [set up a virtual device][AndroidDeveloperDevicesManagingAvdsHtml] and [start the emulator][AndroidDeveloperDevicesEmulatorHtml], then install [Android Accessibility Suite][GooglePlayStoreAndroidAccessibilitySuite] from the GooglePlay store.</span></span>  

> [!NOTE]
> <span data-ttu-id="3d4e8-166">iOS 模拟器当前不包括 VoiceOver。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-166">The iOS Simulator does not currently include VoiceOver.</span></span>  

### <a name="cloud-based-testing-tools"></a><span data-ttu-id="3d4e8-167">基于云的测试工具</span><span class="sxs-lookup"><span data-stu-id="3d4e8-167">Cloud-based Testing Tools</span></span>  

<span data-ttu-id="3d4e8-168">如果辅助技术在你的操作系统上不可用，或者你无法将辅助技术安装在虚拟机或仿真器上，则基于云的辅助技术测试工具是下一个最佳工具。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-168">If an assistive technology is not available on your OS or you not possible to install one on a virtual machine or emulator, cloud-based assistive technology testing tools are the next best thing.</span></span>  

*   <span data-ttu-id="3d4e8-169">[Assistiv Labs (商业) ， ][AssistivlabsMain] 使你能够通过任何新式 Web 浏览器手动测试辅助技术。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-169">[Assistiv Labs (commercial)][AssistivlabsMain] enables you to manually test with assistive technologies through any modern web browser.</span></span>  <span data-ttu-id="3d4e8-170">选择辅助技术和浏览器，它将你与可以交互的虚拟机、仿真器或真实设备相连接。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-170">Choose an assistive technology and browser and it connects you with a virtual machine, emulator, or real device with which you may interact.</span></span>  

## <a name="resources"></a><span data-ttu-id="3d4e8-171">资源</span><span class="sxs-lookup"><span data-stu-id="3d4e8-171">Resources</span></span>  

### <a name="accessibility-basics"></a><span data-ttu-id="3d4e8-172">辅助功能基础知识</span><span class="sxs-lookup"><span data-stu-id="3d4e8-172">Accessibility Basics</span></span>  

#### <a name="the-a11y-project"></a><span data-ttu-id="3d4e8-173">A11Y Project</span><span class="sxs-lookup"><span data-stu-id="3d4e8-173">The A11Y Project</span></span>  

<span data-ttu-id="3d4e8-174">[A11Y Project](http://a11yproject.com)社区推动的一项工作，用于简化 Web 辅助功能。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-174">[The A11Y Project](http://a11yproject.com) is a community-driven effort to make web accessibility easier.</span></span>  <span data-ttu-id="3d4e8-175">查看[A11Y](https://a11yproject.com) Project了解基本的辅助功能原则、辅助功能模式和小组件库，以及辅助功能软件、博客、[](https://a11yproject.com/patterns)书籍和工具上的[](http://a11yproject.com/resources.html)资源。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-175">Check out [The A11Y Project](https://a11yproject.com) site to learn about basic accessibility principles, their accessible pattern and widget [library](https://a11yproject.com/patterns), and their [resources](http://a11yproject.com/resources.html) on accessibility software, blogs, books, and tools.</span></span>  

#### <a name="web-accessibility-initiative-wai"></a><span data-ttu-id="3d4e8-176">Web 辅助功能计划 (，) </span><span class="sxs-lookup"><span data-stu-id="3d4e8-176">Web Accessibility Initiative (WAI)</span></span>  

<span data-ttu-id="3d4e8-177">W3C Web 辅助功能 ([一) ，旨在 ](https://w3.org/WAI) 帮助改善 Web 的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-177">The W3C [Web Accessibility Initiative (WAI)](https://w3.org/WAI) is an effort to help improve the accessibility of the web.</span></span>  <span data-ttu-id="3d4e8-178">他们的网站为 Web 辅助功能入门[](https://www.w3.org/WAI/gettingstarted/Overview.html)、包含设计、教程和演示文稿[](https://www.w3.org/WAI/users/Overview.html)等[提供了](https://www.w3.org/WAI/train.html)各种资源。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-178">Their site provides a variety of resources for [Getting Started with Web Accessibility](https://www.w3.org/WAI/gettingstarted/Overview.html), [Designing for Inclusion](https://www.w3.org/WAI/users/Overview.html), [tutorials and presentations](https://www.w3.org/WAI/train.html), and more.</span></span>  

### <a name="accessibility-blogs"></a><span data-ttu-id="3d4e8-179">辅助功能博客</span><span class="sxs-lookup"><span data-stu-id="3d4e8-179">Accessibility Blogs</span></span>  

#### <a name="tpgi-llc"></a><span data-ttu-id="3d4e8-180">TPGi、LLC</span><span class="sxs-lookup"><span data-stu-id="3d4e8-180">TPGi, LLC</span></span>  

<span data-ttu-id="3d4e8-181">[TPGi， LLC](https://www.tpgi.com/blog) 为世界各地的组织提供咨询和技术解决方案，以确保其客户在满足政府标准和国际标准的同时有效且高效地接触所有受众。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-181">[TPGi, LLC](https://www.tpgi.com/blog) provides consulting and technology solutions to organizations around the world to ensure their clients reach all audiences effectively and efficiently, while meeting governmental and international standards.</span></span>  <span data-ttu-id="3d4e8-182">他们的博客涵盖了 Web 辅助功能最佳实践、辅助功能工具和辅助功能趋势等主题。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-182">Their blog covers topics like web accessibility best practices, accessibility tools, and accessibility trends.</span></span>  

#### <a name="simply-accessible"></a><span data-ttu-id="3d4e8-183">易于访问</span><span class="sxs-lookup"><span data-stu-id="3d4e8-183">Simply Accessible</span></span>  

<span data-ttu-id="3d4e8-184">[Simply Accessible](http://simplyaccessible.com/articles) 是一个辅助功能专家团队，提供辅助功能培训、咨询等，以更改对 Web 上的辅助功能感知。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-184">[Simply Accessible](http://simplyaccessible.com/articles) is a team of accessibility specialists providing accessibility training, consulting and more to change the perception of accessibility on the web.</span></span>  <span data-ttu-id="3d4e8-185">他们 [的文章](http://simplyaccessible.com/articles) 部分讨论了 Web 辅助功能、辅助设计等的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-185">Their [Articles](http://simplyaccessible.com/articles) section discusses best practices for web accessibility, accessible design, and more.</span></span>  

#### <a name="level-access"></a><span data-ttu-id="3d4e8-186">级别访问</span><span class="sxs-lookup"><span data-stu-id="3d4e8-186">Level Access</span></span>  

<span data-ttu-id="3d4e8-187">[Level Access](https://www.levelaccess.com/blog) 是一家数字辅助功能公司，支持其客户开发并部署可访问的产品和服务。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-187">[Level Access](https://www.levelaccess.com/blog) is a digital accessibility firm supporting their clients in developing and deploying accessible products and services.</span></span>  <span data-ttu-id="3d4e8-188">他们的博客介绍 ARIA 最佳实践、辅助功能趋势、网络研讨会等主题。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-188">Their blog addresses topics like ARIA best practices, accessibility trends, webinars, and more.</span></span>  

### <a name="accessible-examples"></a><span data-ttu-id="3d4e8-189">辅助示例</span><span class="sxs-lookup"><span data-stu-id="3d4e8-189">Accessible Examples</span></span>  

#### <a name="allyjs---tutorials"></a><span data-ttu-id="3d4e8-190">ally.js - 教程</span><span class="sxs-lookup"><span data-stu-id="3d4e8-190">ally.js - Tutorials</span></span>  

<span data-ttu-id="3d4e8-191">JavaScript 库，通过简化辅助功能帮助现代 Web 应用程序解决辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-191">JavaScript library to help modern web applications with accessibility concerns by making accessibility simpler.</span></span>  <span data-ttu-id="3d4e8-192">有关详细信息，请导航到["ally.js - 教程"。](http://allyjs.io/tutorials)</span><span class="sxs-lookup"><span data-stu-id="3d4e8-192">For more information, navigate to [ally.js - Tutorials](http://allyjs.io/tutorials).</span></span>  

#### <a name="openajax-examples"></a><span data-ttu-id="3d4e8-193">OpenAjax 示例</span><span class="sxs-lookup"><span data-stu-id="3d4e8-193">OpenAjax Examples</span></span>  

<span data-ttu-id="3d4e8-194">[OpenAjax 联盟网站](http://oaa-accessibility.org)是验证一些适用于一个使用一百万位用户规则且提供一些一系列一些的一些一线实现示例的优秀资源。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-194">The [OpenAjax Alliance website](http://oaa-accessibility.org) is an excellent resource for verifying the rules for WAI-ARIA and provides a number of examples of WAI-ARIA implementations.</span></span>  

#### <a name="patterns"></a><span data-ttu-id="3d4e8-195">模式</span><span class="sxs-lookup"><span data-stu-id="3d4e8-195">Patterns</span></span>  

<span data-ttu-id="3d4e8-196">[A11Y Project](http://a11yproject.com)提供了一个可访问小组件和模式（如菜单、按钮、工具提示等）的库。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-196">[The A11Y Project](http://a11yproject.com) offers a library of accessible widgets and patterns like menus, buttons, tooltips, and more.</span></span>  <span data-ttu-id="3d4e8-197">有关详细信息，请导航到 [模式](http://a11yproject.com/patterns.html)。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-197">For more information, navigate to [Patterns](http://a11yproject.com/patterns.html).</span></span>  

### <a name="accessibility-techniques--tools"></a><span data-ttu-id="3d4e8-198">辅助功能技术&工具</span><span class="sxs-lookup"><span data-stu-id="3d4e8-198">Accessibility Techniques & Tools</span></span>

#### <a name="accessibility--creating-accessible-extension-icons-for-microsoft-edge"></a><span data-ttu-id="3d4e8-199">辅助功能：为用户创建辅助扩展Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3d4e8-199">Accessibility:  Creating accessible extension icons for Microsoft Edge</span></span>  

<span data-ttu-id="3d4e8-200">获取有关为用户创建辅助扩展图标Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-200">Get guidance on creating accessible extensions icons for Microsoft Edge.</span></span>  <span data-ttu-id="3d4e8-201">有关详细信息，请导航到"[辅助功能：为用户创建辅助扩展Microsoft Edge"。](/archive/microsoft-edge/legacy/developer/extensions/guides/accessibility)</span><span class="sxs-lookup"><span data-stu-id="3d4e8-201">For more information, navigate to [Accessibility: Creating accessible extension icons for Microsoft Edge](/archive/microsoft-edge/legacy/developer/extensions/guides/accessibility).</span></span>  

#### <a name="accessible-name-and-description-computation-and-mappings-11"></a><span data-ttu-id="3d4e8-202">辅助名称和说明：计算和映射 1.1</span><span class="sxs-lookup"><span data-stu-id="3d4e8-202">Accessible Name and Description: Computation and Mappings 1.1</span></span>  

<span data-ttu-id="3d4e8-203">此 W3C 映射文档介绍了浏览器如何确定 Web 内容语言中可访问对象的名称和说明，以及如何在辅助功能 API 中公开它们。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-203">This W3C mapping document explains how browsers determine name and descriptions of accessible objects from web content languages and expose them in accessibility APIs.</span></span>  <span data-ttu-id="3d4e8-204">有关详细信息，请导航到"[辅助名称"和"说明：计算和映射 1.1"。](https://www.w3.org/TR/accname-1.1)</span><span class="sxs-lookup"><span data-stu-id="3d4e8-204">For more information, navigate to [Accessible Name and Description: Computation and Mappings 1.1](https://www.w3.org/TR/accname-1.1).</span></span>  

#### <a name="accessibility-evaluation-resources"></a><span data-ttu-id="3d4e8-205">辅助功能评估资源</span><span class="sxs-lookup"><span data-stu-id="3d4e8-205">Accessibility Evaluation Resources</span></span>  

<span data-ttu-id="3d4e8-206">辅助功能评估资源是 W3C 的一个多页资源，概述了用于评估网站辅助功能的不同方法。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-206">Accessibility Evaluation Resources is a multi-page resource by the W3C that outlines different approaches for evaluating websites for accessibility.</span></span>  <span data-ttu-id="3d4e8-207">有关详细信息，请导航到["辅助功能评估资源"。](https://www.w3.org/WAI/eval/Overview.html)</span><span class="sxs-lookup"><span data-stu-id="3d4e8-207">For more information, navigate to [Accessibility Evaluation Resources](https://www.w3.org/WAI/eval/Overview.html).</span></span>  

#### <a name="assistive-technology-compatibility-tests"></a><span data-ttu-id="3d4e8-208">辅助技术兼容性测试</span><span class="sxs-lookup"><span data-stu-id="3d4e8-208">Assistive technology compatibility tests</span></span>  

<span data-ttu-id="3d4e8-209">显示不同的内容类型和标准在辅助技术 \ (AT\) 如屏幕阅读器中的行为的测试结果。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-209">Test results showing how different content types and standards behave in assistive technologies \(AT\) like screen readers.</span></span>  <span data-ttu-id="3d4e8-210">有关详细信息，请导航到 [辅助技术兼容性测试](http://www.powermapper.com/tests)。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-210">For more information, navigate to [Assistive technology compatibility tests](http://www.powermapper.com/tests).</span></span>  

#### <a name="building-accessible-websites-just-got-a-lot-easier"></a><span data-ttu-id="3d4e8-211">构建可访问的网站变得更加简单</span><span class="sxs-lookup"><span data-stu-id="3d4e8-211">Building accessible websites just got a lot easier</span></span>  

<span data-ttu-id="3d4e8-212">本 .NET Web 开发和工具博客文章Visual Studio扩展 Web[辅助功能检查器](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.WebAccessibilityChecker)。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-212">This .NET Web Development and Tools blog post describes the Visual Studio extension [Web Accessibility Checker](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.WebAccessibilityChecker).</span></span>  <span data-ttu-id="3d4e8-213">有关详细信息，请导航到 ["构建可访问的网站"变得更加简单](https://devblogs.microsoft.com/aspnet/building-accessible-websites-just-got-a-lot-easier)。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-213">For more information, navigate to [Building accessible websites just got a lot easier](https://devblogs.microsoft.com/aspnet/building-accessible-websites-just-got-a-lot-easier).</span></span>  

#### <a name="core-accessibility-api-mappings-11"></a><span data-ttu-id="3d4e8-214">核心辅助功能 API 映射 1.1</span><span class="sxs-lookup"><span data-stu-id="3d4e8-214">Core Accessibility API Mappings 1.1</span></span>  

<span data-ttu-id="3d4e8-215">此 W3C 映射文档说明如何向辅助功能 API 公开 Web 内容语言的语义。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-215">This W3C mapping document explains how the semantics of web content languages are exposed to accessibility APIs.</span></span>  <span data-ttu-id="3d4e8-216">有关详细信息，请导航到核心 [辅助功能 API 映射 1.1](https://www.w3.org/TR/core-aam-1.1)。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-216">For more information, navigate to [Core Accessibility API Mappings 1.1](https://www.w3.org/TR/core-aam-1.1).</span></span>  

#### <a name="easy-checks--a-first-review-of-web-accessibility"></a><span data-ttu-id="3d4e8-217">轻松检查 – Web 辅助功能的首次评审</span><span class="sxs-lookup"><span data-stu-id="3d4e8-217">Easy Checks – A First Review of Web Accessibility</span></span>  

<span data-ttu-id="3d4e8-218">一系列由一系列由用户进行快速检查的（该快速检查可帮助你了解网页的辅助功能）。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-218">A series of quick checks by the WAI that help you asses the accessibility of a web page.</span></span>  <span data-ttu-id="3d4e8-219">有关详细信息，请导航到"[轻松检查 - Web 辅助功能的首次审阅"。](https://www.w3.org/WAI/eval/preliminary.html)</span><span class="sxs-lookup"><span data-stu-id="3d4e8-219">For more information, navigate to [Easy Checks – A First Review of Web Accessibility](https://www.w3.org/WAI/eval/preliminary.html).</span></span>  

#### <a name="how-to-meet-wcag-20"></a><span data-ttu-id="3d4e8-220">如何满足 WCAG 2.0</span><span class="sxs-lookup"><span data-stu-id="3d4e8-220">How to Meet WCAG 2.0</span></span>  

<span data-ttu-id="3d4e8-221">快速参考 Web 内容辅助功能指南 \ (WCAG\) 2.0 要求 \ (成功条件\) 和技术。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-221">A quick reference to Web Content Accessibility Guidelines \(WCAG\) 2.0 requirements \(success criteria\) and techniques.</span></span>  <span data-ttu-id="3d4e8-222">有关详细信息，请导航到如何 [开会 WCAG 2.0](https://www.w3.org/WAI/WCAG20/quickref)。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-222">For more information, navigate to [How to Meet WCAG 2.0](https://www.w3.org/WAI/WCAG20/quickref).</span></span>  

#### <a name="html-accessibility-api-mappings-10"></a><span data-ttu-id="3d4e8-223">HTML 辅助功能 API 映射 1.0</span><span class="sxs-lookup"><span data-stu-id="3d4e8-223">HTML Accessibility API Mappings 1.0</span></span>  

<span data-ttu-id="3d4e8-224">此 W3C 映射文档说明了 HTML5.1 元素和属性如何映射到平台辅助功能 API。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-224">This W3C mappings document explains how HTML5.1 element and attributes map to platform accessibility APIs.</span></span>  <span data-ttu-id="3d4e8-225">有关详细信息，请导航到["HTML 辅助功能 API 映射 1.0"。](https://www.w3.org/TR/html-aam-1.0)</span><span class="sxs-lookup"><span data-stu-id="3d4e8-225">For more information, navigate to [HTML Accessibility API Mappings 1.0](https://www.w3.org/TR/html-aam-1.0).</span></span>  

#### <a name="quick-tips"></a><span data-ttu-id="3d4e8-226">快速使用技巧</span><span class="sxs-lookup"><span data-stu-id="3d4e8-226">Quick Tips</span></span>

<span data-ttu-id="3d4e8-227">[A11Y](http://a11yproject.com)工具中有关辅助功能的快速 Web 开发Project。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-227">A list of quick web development tips for accessibility by [The A11Y Project](http://a11yproject.com).</span></span>  <span data-ttu-id="3d4e8-228">有关详细信息，请导航到"[快速使用技巧"。](http://a11yproject.com#Quick-tips)</span><span class="sxs-lookup"><span data-stu-id="3d4e8-228">For more information, navigate to [Quick Tips](http://a11yproject.com#Quick-tips).</span></span>  

#### <a name="site-scan"></a><span data-ttu-id="3d4e8-229">网站扫描</span><span class="sxs-lookup"><span data-stu-id="3d4e8-229">Site Scan</span></span>  

<span data-ttu-id="3d4e8-230">Microsoft Edge Dev 中心上的"网站扫描"工具检查过期库、布局问题和辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-230">The Site Scan tool on Microsoft Edge Dev Center checks for out-of-date libraries, layout issues, and accessibility issues.</span></span>  <span data-ttu-id="3d4e8-231">有关详细信息，请导航到"[网站扫描"。](https://developer.microsoft.com/microsoft-edge/tools)</span><span class="sxs-lookup"><span data-stu-id="3d4e8-231">For more information, navigate to [Site Scan](https://developer.microsoft.com/microsoft-edge/tools).</span></span>  

#### <a name="techniques-for-wcag-20"></a><span data-ttu-id="3d4e8-232">WCAG 2.0 的技术</span><span class="sxs-lookup"><span data-stu-id="3d4e8-232">Techniques for WCAG 2.0</span></span>  

<span data-ttu-id="3d4e8-233">W3C 中的技术，为 Web 开发人员提供有关满足 Web 内容辅助功能指南 ([WCAG) 2.0 成功](https://w3.org/TR/WCAG20) 标准的指导。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-233">Techniques from the W3C that provide guidance for web developers on meeting [Web Content Accessibility Guidelines (WCAG) 2.0](https://w3.org/TR/WCAG20) success criteria.</span></span>  <span data-ttu-id="3d4e8-234">有关详细信息，请导航到 [WCAG 2.0 的技术](https://www.w3.org/TR/WCAG20-TECHS/Overview.html)。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-234">For more information, navigate to [Techniques for WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/Overview.html).</span></span>  

#### <a name="tips-on-developing-for-web-accessibility"></a><span data-ttu-id="3d4e8-235">使用技巧 Web 辅助功能开发</span><span class="sxs-lookup"><span data-stu-id="3d4e8-235">Tips on Developing for Web Accessibility</span></span>  

<span data-ttu-id="3d4e8-236">使用技巧 W3C 中有关开发残障人士更容易访问的 Web 内容的信息。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-236">Tips from the W3C on developing web content that is more accessible to people with disabilities.</span></span>  <span data-ttu-id="3d4e8-237">有关详细信息，请导航到["使用技巧 Web 辅助功能"上的"开发"。](https://w3.org/WAI/gettingstarted/tips/developing.html)</span><span class="sxs-lookup"><span data-stu-id="3d4e8-237">For more information, navigate to [Tips on Developing for Web Accessibility](https://w3.org/WAI/gettingstarted/tips/developing.html).</span></span>  

#### <a name="wai-aria-authoring-practices-11"></a><span data-ttu-id="3d4e8-238">WAI-ARIA 创作实践 1.1</span><span class="sxs-lookup"><span data-stu-id="3d4e8-238">WAI-ARIA Authoring Practices 1.1</span></span>  

<span data-ttu-id="3d4e8-239">W3C 提供的一个文档，使读者能够了解如何使用 WIDGET-ARIA 1.1，并推荐使用 WIDGET-ARIA 角色、状态和属性使小组件、导航和行为可供访问的方法。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-239">A document by the W3C that provides readers with an understanding of how to use WAI-ARIA 1.1 and recommends approaches to make widgets, navigation, and behaviors accessible using WAI-ARIA roles, states, and properties.</span></span>  <span data-ttu-id="3d4e8-240">有关详细信息，请导航到["一个或多个功能"-"ARIA 创作实践 1.1"。](http://w3c.github.io/aria-practices)</span><span class="sxs-lookup"><span data-stu-id="3d4e8-240">For more information, navigate to [WAI-ARIA Authoring Practices 1.1](http://w3c.github.io/aria-practices).</span></span>  

#### <a name="wai-guidelines-and-techniques"></a><span data-ttu-id="3d4e8-241">一些指南和技术</span><span class="sxs-lookup"><span data-stu-id="3d4e8-241">WAI Guidelines and Techniques</span></span>  

<span data-ttu-id="3d4e8-242">由一系列由一系列 WEB 辅助功能指南和由一些用户制定的标准。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-242">A series of web accessibility guidelines and standards developed by the WAI.</span></span>  <span data-ttu-id="3d4e8-243">有关详细信息，请导航到["操作指南和技术"。](https://w3.org/WAI/guid-tech.html)</span><span class="sxs-lookup"><span data-stu-id="3d4e8-243">For more information, navigate to [WAI Guidelines and Techniques](https://w3.org/WAI/guid-tech.html).</span></span>  

#### <a name="web-accessibility-evaluation-tools-list"></a><span data-ttu-id="3d4e8-244">Web 辅助功能评估工具列表</span><span class="sxs-lookup"><span data-stu-id="3d4e8-244">Web Accessibility Evaluation Tools List</span></span>  

<span data-ttu-id="3d4e8-245">可帮助确定网站是否满足辅助功能指南的 Web 辅助功能评估工具列表。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-245">A list of web accessibility evaluation tools to help determine if websites meet accessibility guidelines.</span></span>  <span data-ttu-id="3d4e8-246">有关详细信息，请导航到["Web 辅助功能评估工具列表"。](https://www.w3.org/WAI/ER/tools/index.html)</span><span class="sxs-lookup"><span data-stu-id="3d4e8-246">For more information, navigate to [Web Accessibility Evaluation Tools List](https://www.w3.org/WAI/ER/tools/index.html).</span></span>  

#### <a name="web-accessibility-perspectives-explore-the-impact-and-benefits-for-everyone"></a><span data-ttu-id="3d4e8-247">Web 辅助功能角度：探索对所有人的影响和好处</span><span class="sxs-lookup"><span data-stu-id="3d4e8-247">Web Accessibility Perspectives: Explore the Impact and Benefits for Everyone</span></span>  

<span data-ttu-id="3d4e8-248">W3C 关于辅助功能的影响和每个人的权益的一系列简短情境视频。</span><span class="sxs-lookup"><span data-stu-id="3d4e8-248">A series of short situational videos by the W3C about the impact of accessibility and the benefits for everyone.</span></span>  <span data-ttu-id="3d4e8-249">有关详细信息，请导航到["Web 辅助功能角度：探索对所有人的影响和好处"。](https://w3.org/WAI/perspectives)</span><span class="sxs-lookup"><span data-stu-id="3d4e8-249">For more information, navigate to [Web Accessibility Perspectives: Explore the Impact and Benefits for Everyone](https://w3.org/WAI/perspectives).</span></span>  

<!-- links -->  

<!--todo: link updates and acrolinx  -->  

[MicrosoftDeveloperEdgeVms]: https://developer.microsoft.com/microsoft-edge/tools/vms "虚拟机|Microsoft Edge开发人员"  

[MicrosoftSupport22798]: https://support.microsoft.com/help/22798 "完整指南讲述人 |Microsoft 支持"  
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
