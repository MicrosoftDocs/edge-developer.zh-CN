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
# <span data-ttu-id="07f16-104">构建易于访问的网站</span><span class="sxs-lookup"><span data-stu-id="07f16-104">Building Accessible Websites</span></span>
<span data-ttu-id="07f16-105">Web 使用 HTML、CSS 和 JavaScript 的组合生成了动态、复杂的网站、应用程序和用户界面。</span><span class="sxs-lookup"><span data-stu-id="07f16-105">The web is filled with dynamic and complex websites, applications, and user interfaces built using a combination of HTML, CSS, and JavaScript.</span></span>  <span data-ttu-id="07f16-106">但是，如果在设计和构建时不考虑辅助功能，则依赖 [辅助技术](https://webaim.org/articles/motor/assistive) 浏览 web 的用户很难使用这些复杂的网站。</span><span class="sxs-lookup"><span data-stu-id="07f16-106">However, when designed and built without accessibility in mind, these complex websites are difficult to use by people who rely on [assistive technologies](https://webaim.org/articles/motor/assistive) to browse the web.</span></span> <span data-ttu-id="07f16-107">构建残疾人士易于访问的网站需要有关用户界面的语义信息。</span><span class="sxs-lookup"><span data-stu-id="07f16-107">Building websites that are accessible to people with disabilities requires semantic information about the user interface.</span></span> <span data-ttu-id="07f16-108">这允许辅助技术（如屏幕阅读器）传达必要的信息，以帮助具有各种功能的人员使用该网站。</span><span class="sxs-lookup"><span data-stu-id="07f16-108">This allows for assistive technologies, like screen readers, to convey the necessary information to help people with a range of abilities use the website.</span></span>

<span data-ttu-id="07f16-109">有关 Microsoft Edge 支持的新 HTML5 功能 accessibly 的信息，请访问 [HTML5Accessibility](https://html5accessibility.com) 。</span><span class="sxs-lookup"><span data-stu-id="07f16-109">Visit [HTML5Accessibility](https://html5accessibility.com) for information on which new HTML5 features are accessibly supported by Microsoft Edge.</span></span>

## <span data-ttu-id="07f16-110">辅助功能的工作原理</span><span class="sxs-lookup"><span data-stu-id="07f16-110">How Accessibility Works</span></span>

<span data-ttu-id="07f16-111">辅助技术添加了计算机通常不具备的功能。</span><span class="sxs-lookup"><span data-stu-id="07f16-111">Assistive technologies add capabilities that computers don't usually have.</span></span> <span data-ttu-id="07f16-112">例如，视觉障碍的用户可能将其键盘与辅助技术（如屏幕阅读器）结合使用，而不是使用鼠标和屏幕直接使用浏览器。</span><span class="sxs-lookup"><span data-stu-id="07f16-112">For example, a visually impaired user might use their keyboard in combination with assistive technology such as a screen reader, rather than directly using the browser with the mouse and screen.</span></span> <span data-ttu-id="07f16-113">对于 Microsoft 平台和 web 上的应用程序，辅助技术与 Microsoft [UI 自动化](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx)、特定于应用程序的对象模型（如文档对象模型 (DOM) 在 Microsoft Edge 中）或它们的组合进行交互。</span><span class="sxs-lookup"><span data-stu-id="07f16-113">For applications on Microsoft platforms and on the web, the assistive technology interacts with Microsoft [UI Automation](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx), an application-specific object model such as the Document Object Model (DOM) in Microsoft Edge, or a combination of these.</span></span>

<span data-ttu-id="07f16-114">对于 web 开发人员，某些 HTML 元素映射到 UI 自动化对象，因此在选择这些 HTML 元素时，开发人员可以使用内置于这些元素的辅助功能属性和事件。</span><span class="sxs-lookup"><span data-stu-id="07f16-114">For web developers, certain HTML elements are mapped to UI Automation objects, so in selecting those HTML elements, the developer can use the accessibility properties and events built in to those elements.</span></span> <span data-ttu-id="07f16-115">在开发您的网站时，通常只需考虑确保 API 正确地写入 (或指定了相应的元素) ，才能使应用程序易于访问。</span><span class="sxs-lookup"><span data-stu-id="07f16-115">While developing your website, you usually only need to be concerned with ensuring that the API is correctly written to (or that the appropriate element is specified), in order for the application to be accessible.</span></span> <span data-ttu-id="07f16-116">有关详细信息，请查看 [Microsoft Edge 中的 ARIA 和 UI 自动化](./build/ARIA-and-UI-Automation.md) 。</span><span class="sxs-lookup"><span data-stu-id="07f16-116">Check out [ARIA and UI Automation in Microsoft Edge](./build/ARIA-and-UI-Automation.md) for more information.</span></span>  <span data-ttu-id="07f16-117">有关可访问的通用 Windows 平台 (UWP) 应用的信息，请参阅 Windows 开发人员中心中的 " [辅助功能](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility) " 主题。</span><span class="sxs-lookup"><span data-stu-id="07f16-117">For information on accessible Universal Windows Platform (UWP) apps, see the [Accessibility](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility) topic in the Windows Dev Center.</span></span>

<span data-ttu-id="07f16-118">可通过良好的编码实践解决动态内容的许多常见辅助功能问题，并且 [WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629) 文档包含许多技术和最佳做法，可帮助你创建更易于访问的动态 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="07f16-118">Many common accessibility issues with dynamic content can be addressed by good coding practice, and the [WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629) documentation includes many techniques and best practices to help you create more accessible dynamic web applications.</span></span> <span data-ttu-id="07f16-119">但是，即使正确编码，也不一定可以访问动态内容。</span><span class="sxs-lookup"><span data-stu-id="07f16-119">Even when coded properly, however, dynamic content is not necessarily accessible.</span></span> <span data-ttu-id="07f16-120">[ (ARIA) 易于访问的富 Internet 应用程序 ](#aria) 可帮助解决此问题。</span><span class="sxs-lookup"><span data-stu-id="07f16-120">[Accessible Rich Internet Applications (ARIA)](#aria) helps overcome this issue.</span></span>  

<span data-ttu-id="07f16-121">有关 web 辅助功能的详细信息，请参阅[Web 辅助功能计划](https://www.w3.org/WAI/)的[Web 辅助功能简介](https://www.w3.org/WAI/intro/accessibility.php) (wai-aria) 。</span><span class="sxs-lookup"><span data-stu-id="07f16-121">For more information on web accessibility, check out the [Introduction to Web Accessibility](https://www.w3.org/WAI/intro/accessibility.php) by the [Web Accessibility Initiative](https://www.w3.org/WAI/) (WAI).</span></span>

## <span data-ttu-id="07f16-122">ARIA</span><span class="sxs-lookup"><span data-stu-id="07f16-122">ARIA</span></span>
<span data-ttu-id="07f16-123">W3C's [Web 辅助功能计划](https://www.w3.org/WAI/) (ARIA) 规范的[易于访问的富 Internet 应用程序](https://www.w3.org/TR/wai-aria/)定义为使动态 Web 内容和自定义用户界面可供所有人访问的语法。</span><span class="sxs-lookup"><span data-stu-id="07f16-123">The [Accessible Rich Internet Applications](https://www.w3.org/TR/wai-aria/) (ARIA) specification by the W3C's [Web Accessibility Initiative](https://www.w3.org/WAI/) defines as a syntax for making dynamic web content and custom user interfaces accessible to all people.</span></span> <span data-ttu-id="07f16-124">ARIA 通过使用 (角色、属性和状态) 的其他属性来扩展 HTML，这些属性旨在传递自定义语义。</span><span class="sxs-lookup"><span data-stu-id="07f16-124">ARIA extends HTML by using additional attributes (roles, properties, and states) that are designed to convey custom semantics.</span></span> <span data-ttu-id="07f16-125">浏览器使用这些属性将控件的状态和角色传递给辅助功能 API。</span><span class="sxs-lookup"><span data-stu-id="07f16-125">These attributes are used by browsers to pass along the controls' state and role to the accessibility API.</span></span>

### <span data-ttu-id="07f16-126">角色、属性和状态</span><span class="sxs-lookup"><span data-stu-id="07f16-126">Roles, Properties, and States</span></span>
<span data-ttu-id="07f16-127">在使用属性的元素上设置 ARIA 角色， [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) 以提供有关元素的辅助技术和辅助功能 api 信息。</span><span class="sxs-lookup"><span data-stu-id="07f16-127">ARIA roles are set on elements using the [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) attribute to give assistive technologies and accessibility APIs information about the element.</span></span> <span data-ttu-id="07f16-128">例如，以下 `<li>` 元素被分配 `role="menuitem"` 为表示它是菜单中的项目。</span><span class="sxs-lookup"><span data-stu-id="07f16-128">For example, the below `<li>` element is assigned `role="menuitem"` to signify it's an item in a menu.</span></span>

``` html
<li role="menuitem">Home</li>
```

<span data-ttu-id="07f16-129">ARIA 状态和属性是 aria 的前缀属性，提供有关对象的特定信息，以帮助形成角色性质的定义。</span><span class="sxs-lookup"><span data-stu-id="07f16-129">ARIA states and properties are aria-prefixed attributes that provide specific information about an object to help form the definition of the nature of roles.</span></span> <span data-ttu-id="07f16-130">属性是对象本质所必需的属性，如 [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) 和 [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx) 。</span><span class="sxs-lookup"><span data-stu-id="07f16-130">Properties are attributes that are essential to the nature of an object, like [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) and [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx).</span></span> <span data-ttu-id="07f16-131">更改属性会影响对象的含义。</span><span class="sxs-lookup"><span data-stu-id="07f16-131">Changing a property affects the meaning of the object.</span></span> <span data-ttu-id="07f16-132">在下面的示例中， `aria-haspopup="true"` 将在菜单项上设置属性 `<li>` 以表示它具有弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="07f16-132">In the example below, the property `aria-haspopup="true"` is set on a `<li>` menu item to signify it has a popup.</span></span>

``` html
<li role="menuitem" aria-haspopup="true">Open</li>
```

<span data-ttu-id="07f16-133">状态不会更改对象的性质，而是表示与对象或与对象的用户交互相关联的信息，如 [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) 或 [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx) 。</span><span class="sxs-lookup"><span data-stu-id="07f16-133">States do not change the nature of the object, but represent information associated with the object or user interaction with the object, like [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) or [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx).</span></span> <span data-ttu-id="07f16-134">例如， `aria-checked="false"` 以下示例中的状态表示未选中复选框。</span><span class="sxs-lookup"><span data-stu-id="07f16-134">For example, the state `aria-checked="false"` in the example below represents that the checkbox is not checked.</span></span>

``` html
<div role="checkbox" aria-checked="false">Accept</div>
```

<span data-ttu-id="07f16-135">通过 W3C 转到 ["角色" 模型](https://www.w3.org/TR/wai-aria-1.1/#roles) 以查看角色、属性和状态的完整列表。</span><span class="sxs-lookup"><span data-stu-id="07f16-135">Go to [The Roles Model](https://www.w3.org/TR/wai-aria-1.1/#roles) by the W3C to see a full list of roles, properties, and states.</span></span>

<span data-ttu-id="07f16-136">有关 ARIA 的详细信息，请参阅 " [资源](#resources) " 部分中的 ARIA。</span><span class="sxs-lookup"><span data-stu-id="07f16-136">For more information on ARIA, see the ARIA in the [Resources](#resources) section.</span></span>

## <span data-ttu-id="07f16-137">辅助技术兼容性测试</span><span class="sxs-lookup"><span data-stu-id="07f16-137">Assistive Technology Compatibility Testing</span></span>  

<span data-ttu-id="07f16-138">验证正在构建的网站是否适用于真正的辅助技术是确保你的残障人士获得良好体验的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="07f16-138">Verifying that the website you are building works with real assistive technologies is the best way to ensure a good experience for your users with disabilities.</span></span>  <span data-ttu-id="07f16-139">由于很多辅助技术使用键盘，因此测试网站的键盘辅助功能是一个很好的开始位置。</span><span class="sxs-lookup"><span data-stu-id="07f16-139">Since many assistive technologies make use of the keyboard, testing the keyboard accessibility of your website is a good place to start.</span></span>  <span data-ttu-id="07f16-140">[键盘兼容性测试][W3cPerspectiveVideosKeyboard] 验证用户是否可以访问所有交互式控件，而无需使用鼠标。</span><span class="sxs-lookup"><span data-stu-id="07f16-140">[Keyboard compatibility testing][W3cPerspectiveVideosKeyboard] validates that users have access to all interactive controls without requiring a mouse.</span></span>  <span data-ttu-id="07f16-141">Microsoft 的 microsoft [辅助功能见解][AccessibilityinsightsWebOverview] 是 microsoft Edge 和 Chrome 的浏览器扩展，可指导你并显示一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="07f16-141">Microsoft [Accessibility Insights for Web][AccessibilityinsightsWebOverview] is a browser extension for Microsoft Edge and Chrome that guides you and reveals several common issues.</span></span>  

<span data-ttu-id="07f16-142">确信你的网站在使用键盘时工作良好，请使用其他辅助技术（如屏幕阅读器）试用它。</span><span class="sxs-lookup"><span data-stu-id="07f16-142">Once you are confident that your website works well with a keyboard, try it with other assistive technologies, such as screen readers.</span></span>  <span data-ttu-id="07f16-143">它在以下情况下发现问题。</span><span class="sxs-lookup"><span data-stu-id="07f16-143">It uncover issues in the following.</span></span>

*   <span data-ttu-id="07f16-144">HTML、ARIA 和 CSS。</span><span class="sxs-lookup"><span data-stu-id="07f16-144">Your HTML, ARIA, and CSS.</span></span>  
*   <span data-ttu-id="07f16-145">功能或技术对辅助技术的支持级别。</span><span class="sxs-lookup"><span data-stu-id="07f16-145">The level of support of an assistive technology for a feature or technique.</span></span>  
    
<span data-ttu-id="07f16-146">不同的浏览器可能将元素映射到平台辅助功能 Api，与 Microsoft Edge 不同。</span><span class="sxs-lookup"><span data-stu-id="07f16-146">Different browsers may map elements to platform accessibility APIs differently than Microsoft Edge.</span></span>  <span data-ttu-id="07f16-147">构建你的界面时，请务必考虑每个差异。</span><span class="sxs-lookup"><span data-stu-id="07f16-147">While building your interface, it is important to consider each difference.</span></span>  

<span data-ttu-id="07f16-148">WebAIM 通过 [屏幕阅读器][WebaimProjectsScreenreadersurvey8] 和 [弱视][WebaimProjectsLowvisionsurvey2] 用户执行调查，帮助你确定要测试的辅助技术和浏览器。</span><span class="sxs-lookup"><span data-stu-id="07f16-148">WebAIM conducts surveys with [screen reader][WebaimProjectsScreenreadersurvey8] and [low vision][WebaimProjectsLowvisionsurvey2] users that help you decide which assistive technologies and browsers you want to test.</span></span>  

### <span data-ttu-id="07f16-149">了解如何测试</span><span class="sxs-lookup"><span data-stu-id="07f16-149">Learning How to Test</span></span>  

<span data-ttu-id="07f16-150">辅助技术是复杂的工具。</span><span class="sxs-lookup"><span data-stu-id="07f16-150">Assistive technologies are sophisticated tools.</span></span>  <span data-ttu-id="07f16-151">不要假设你可以使用辅助技术立即开始测试，而无需事先了解它的工作原理。</span><span class="sxs-lookup"><span data-stu-id="07f16-151">Do not assume that you are able to immediately start testing with an assistive technology without first learning about how it works.</span></span>  <span data-ttu-id="07f16-152">学习使用屏幕阅读器进行测试有一个特别陡的学习曲线。</span><span class="sxs-lookup"><span data-stu-id="07f16-152">Learning to test with a screen reader has an especially steep learning curve.</span></span>  <span data-ttu-id="07f16-153">初级用户屏幕阅读器用户可能假设问题与屏幕阅读器的误用有关时出现屏幕阅读器错误。</span><span class="sxs-lookup"><span data-stu-id="07f16-153">A novice screen reader user may assume that a screen reader bug has occurred while the issue is related to misuse of the screen reader.</span></span>  

<span data-ttu-id="07f16-154">有关学习通过辅助技术进行测试的详细信息，请导航到 WebAIM 上 [的屏幕阅读器进行测试][WebaimArticlesScreenreaderTesting] 。</span><span class="sxs-lookup"><span data-stu-id="07f16-154">For more information about learning to test with assistive technologies, navigate to [Testing with Screen Readers][WebaimArticlesScreenreaderTesting] on WebAIM.</span></span>  

### <span data-ttu-id="07f16-155">本地测试</span><span class="sxs-lookup"><span data-stu-id="07f16-155">Testing Locally</span></span>  

<span data-ttu-id="07f16-156">大多数设备都包含操作系统内置的辅助技术。</span><span class="sxs-lookup"><span data-stu-id="07f16-156">Most devices include assistive technology that is built-in to the OS.</span></span>  <span data-ttu-id="07f16-157">Microsoft Windows 包括 [Windows 讲述人][MicrosoftSupport22798] 屏幕阅读器和 [windows 放大镜][MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198]。</span><span class="sxs-lookup"><span data-stu-id="07f16-157">Microsoft Windows includes the [Windows Narrator][MicrosoftSupport22798] screen reader and [Windows Magnifier][MicrosoftSupportWindows414948ba8b1cD3bd86150e5e32204198].</span></span>  <span data-ttu-id="07f16-158">可下载第三方辅助技术，如 [NVDA][NvaccessAboutNvda]、 [FreedomscientificSoftwareJaws]和 [ZoomText][FreedomscientificSoftwareZoomtext] 。</span><span class="sxs-lookup"><span data-stu-id="07f16-158">3rd party assistive technologies like [NVDA][NvaccessAboutNvda], [FreedomscientificSoftwareJaws], and [ZoomText][FreedomscientificSoftwareZoomtext] are available to download.</span></span>  <span data-ttu-id="07f16-159">Apple macOS 包括 [VoiceOver][AppleAccessibilityMacVision] 屏幕阅读器。</span><span class="sxs-lookup"><span data-stu-id="07f16-159">Apple macOS includes the [VoiceOver][AppleAccessibilityMacVision] screen reader.</span></span>  <span data-ttu-id="07f16-160">和 iOS、Android 和 Linux 都支持各种辅助技术。</span><span class="sxs-lookup"><span data-stu-id="07f16-160">And iOS, Android, and Linux all support a variety of assistive technologies.</span></span>  

### <span data-ttu-id="07f16-161">在虚拟机和模拟器中测试</span><span class="sxs-lookup"><span data-stu-id="07f16-161">Testing in Virtual Machines and Emulators</span></span>  

<span data-ttu-id="07f16-162">在 "macOS" 下，如果要使用仅适用于 Windows 的辅助技术（如 Windows "讲述人" 或 "NVDA"）进行测试，请创建 Windows 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="07f16-162">Under macOS, if you want to test with an assistive technology only available for Windows, like Windows Narrator or NVDA, create a Windows virtual machine.</span></span>  <span data-ttu-id="07f16-163">具有 Microsoft Edge \ (EdgeHTML \ ) 和 IE 的虚拟机可在 " [虚拟机下载" 页面][MicrosoftDeveloperEdgeVms]上 VirtualBox 和 VMWare。</span><span class="sxs-lookup"><span data-stu-id="07f16-163">Virtual machines with Microsoft Edge \(EdgeHTML\) and IE are available for VirtualBox and VMWare on the [Virtual Machines download page][MicrosoftDeveloperEdgeVms].</span></span>  

<span data-ttu-id="07f16-164">[Android Studio][AndroidDeveloperSdkInstallingStudioHtml] 包含一个用于测试 [Android 辅助功能套件][GooglePlayStoreAndroidAccessibilitySuite]中的辅助技术的模拟器。</span><span class="sxs-lookup"><span data-stu-id="07f16-164">[Android Studio][AndroidDeveloperSdkInstallingStudioHtml] includes an emulator that for you to test assistive technologies in the [Android Accessibility Suite][GooglePlayStoreAndroidAccessibilitySuite].</span></span>  <span data-ttu-id="07f16-165">按照说明 [设置虚拟设备][AndroidDeveloperDevicesManagingAvdsHtml] 并 [启动模拟器][AndroidDeveloperDevicesEmulatorHtml]，然后从 GooglePlay 应用商店安装 [Android 辅助功能套件][GooglePlayStoreAndroidAccessibilitySuite] 。</span><span class="sxs-lookup"><span data-stu-id="07f16-165">Follow the instructions to [set up a virtual device][AndroidDeveloperDevicesManagingAvdsHtml] and [start the emulator][AndroidDeveloperDevicesEmulatorHtml], then install [Android Accessibility Suite][GooglePlayStoreAndroidAccessibilitySuite] from the GooglePlay store.</span></span>  

> [!NOTE]
> <span data-ttu-id="07f16-166">IOS 模拟器当前不包含 VoiceOver。</span><span class="sxs-lookup"><span data-stu-id="07f16-166">The iOS Simulator does not currently include VoiceOver.</span></span>  

### <span data-ttu-id="07f16-167">基于云的测试工具</span><span class="sxs-lookup"><span data-stu-id="07f16-167">Cloud-based Testing Tools</span></span>  

<span data-ttu-id="07f16-168">如果你的操作系统上不能使用辅助技术，或者你无法在虚拟机或模拟器上安装，那么下一步是基于云的辅助技术测试工具。</span><span class="sxs-lookup"><span data-stu-id="07f16-168">If an assistive technology is not available on your OS or you not possible to install one on a virtual machine or emulator, cloud-based assistive technology testing tools are the next best thing.</span></span>  

*   <span data-ttu-id="07f16-169">[Assistiv Labs (商业) ][AssistivlabsMain] 使你能够通过任何现代 web 浏览器手动测试辅助技术。</span><span class="sxs-lookup"><span data-stu-id="07f16-169">[Assistiv Labs (commercial)][AssistivlabsMain] enables you to manually test with assistive technologies through any modern web browser.</span></span>  <span data-ttu-id="07f16-170">选择辅助技术和浏览器，它将你与你可以交互的虚拟机、模拟器或真正设备连接起来。</span><span class="sxs-lookup"><span data-stu-id="07f16-170">Choose an assistive technology and browser and it connects you with a virtual machine, emulator, or real device with which you may interact.</span></span>  

## <span data-ttu-id="07f16-171">资源</span><span class="sxs-lookup"><span data-stu-id="07f16-171">Resources</span></span>

### <span data-ttu-id="07f16-172">辅助功能基础知识</span><span class="sxs-lookup"><span data-stu-id="07f16-172">Accessibility Basics</span></span>
#### [<span data-ttu-id="07f16-173">A11Y 项目</span><span class="sxs-lookup"><span data-stu-id="07f16-173">The A11Y Project</span></span>](http://a11yproject.com/)
<span data-ttu-id="07f16-174">A11Y 项目是社区驱动的工作，使 web 辅助功能更易于使用。</span><span class="sxs-lookup"><span data-stu-id="07f16-174">The A11Y Project is a community-driven effort to make web accessibility easier.</span></span> <span data-ttu-id="07f16-175">查看 [A11Y 项目](https://a11yproject.com/) 网站，了解基本辅助功能原则、其易于访问的模式和小组件 [库](https://a11yproject.com/patterns)以及它们在辅助功能软件、博客、书籍和工具上的 [资源](http://a11yproject.com/resources.html) 。</span><span class="sxs-lookup"><span data-stu-id="07f16-175">Check out [The A11Y Project](https://a11yproject.com/) site to learn about basic accessibility principles, their accessible pattern and widget [library](https://a11yproject.com/patterns), and their [resources](http://a11yproject.com/resources.html) on accessibility software, blogs, books, and tools.</span></span>

#### [<span data-ttu-id="07f16-176"> (WAI-ARIA 的 Web 辅助功能计划) </span><span class="sxs-lookup"><span data-stu-id="07f16-176">Web Accessibility Initiative (WAI)</span></span>](https://w3.org/WAI/)
<span data-ttu-id="07f16-177">W3C's Web 辅助功能计划 (WAI-ARIA) 是帮助改进 Web 辅助功能的一项工作。</span><span class="sxs-lookup"><span data-stu-id="07f16-177">The W3C's Web Accessibility Initiative (WAI) is an effort to help improve the accessibility of the web.</span></span> <span data-ttu-id="07f16-178">他们的网站提供了各种资源来 [开始使用 Web 辅助功能](https://www.w3.org/WAI/gettingstarted/Overview.html)， [设计包括 "包含](https://www.w3.org/WAI/users/Overview.html)"、" [教程" 和 "演示文稿](https://www.w3.org/WAI/train.html)" 等。</span><span class="sxs-lookup"><span data-stu-id="07f16-178">Their site provides a variety of resources for [Getting Started with Web Accessibility](https://www.w3.org/WAI/gettingstarted/Overview.html), [Designing for Inclusion](https://www.w3.org/WAI/users/Overview.html), [tutorials and presentations](https://www.w3.org/WAI/train.html), and more.</span></span>

### <span data-ttu-id="07f16-179">辅助功能博客</span><span class="sxs-lookup"><span data-stu-id="07f16-179">Accessibility Blogs</span></span>
#### [<span data-ttu-id="07f16-180">Paciello 组</span><span class="sxs-lookup"><span data-stu-id="07f16-180">The Paciello Group</span></span>](https://www.paciellogroup.com/blog/)
<span data-ttu-id="07f16-181">Paciello 组为全球各地的组织提供咨询和技术解决方案，以确保客户能够有效、高效地访问所有受众，同时满足政府和国际标准。</span><span class="sxs-lookup"><span data-stu-id="07f16-181">The Paciello Group provides consulting and technology solutions to organizations around the world to ensure their clients reach all audiences effectively and efficiently, while meeting governmental and international standards.</span></span> <span data-ttu-id="07f16-182">其博客介绍诸如 web 辅助功能最佳做法、辅助功能工具和辅助功能趋势等主题。</span><span class="sxs-lookup"><span data-stu-id="07f16-182">Their blog covers topics like web accessibility best practices, accessibility tools, and accessibility trends.</span></span>

#### [<span data-ttu-id="07f16-183">轻松访问</span><span class="sxs-lookup"><span data-stu-id="07f16-183">Simply Accessible</span></span>](http://simplyaccessible.com/articles/)
<span data-ttu-id="07f16-184">简单的辅助功能是一组辅助功能专家团队，可提供辅助功能培训、咨询以及更多更改 web 上的辅助功能的感觉。</span><span class="sxs-lookup"><span data-stu-id="07f16-184">Simply Accessible is a team of accessibility specialists providing accessibility training, consulting and more to change the perception of accessibility on the web.</span></span> <span data-ttu-id="07f16-185">他们的 [文章](http://simplyaccessible.com/articles/) 部分讨论了 web 辅助功能、易于访问的设计等的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="07f16-185">Their [Articles](http://simplyaccessible.com/articles/) section discusses best practices for web accessibility, accessible design, and more.</span></span>

#### [<span data-ttu-id="07f16-186">SSB 邓 Group (SSB) </span><span class="sxs-lookup"><span data-stu-id="07f16-186">SSB BART Group (SSB)</span></span>](http://www.ssbbartgroup.com/blog/)
<span data-ttu-id="07f16-187">SSB 邓 Group 是一个数字辅助公司，支持其客户开发和部署易于访问的产品和服务。</span><span class="sxs-lookup"><span data-stu-id="07f16-187">SSB BART Group is a digital accessibility firm supporting their clients in developing and deploying accessible products and services.</span></span> <span data-ttu-id="07f16-188">其博客地址主题如 ARIA 最佳做法、辅助功能趋势、网络研讨会等。</span><span class="sxs-lookup"><span data-stu-id="07f16-188">Their blog addresses topics like ARIA best practices, accessibility trends, webinars, and more.</span></span>

### <span data-ttu-id="07f16-189">辅助功能示例</span><span class="sxs-lookup"><span data-stu-id="07f16-189">Accessible Examples</span></span>
#### [<span data-ttu-id="07f16-190">ally.js 教程</span><span class="sxs-lookup"><span data-stu-id="07f16-190">ally.js - Tutorials</span></span>](http://allyjs.io/tutorials/)
<span data-ttu-id="07f16-191">JavaScript 库通过使辅助功能更简单，帮助现代 web 应用程序提供辅助功能。</span><span class="sxs-lookup"><span data-stu-id="07f16-191">JavaScript library to help modern web applications with accessibility concerns by making accessibility simpler.</span></span>

#### [<span data-ttu-id="07f16-192">Heydonworks-ARIA 示例</span><span class="sxs-lookup"><span data-stu-id="07f16-192">Heydonworks - ARIA Examples</span></span>](http://heydonworks.com/practical_aria_examples/)
<span data-ttu-id="07f16-193">用于增强你的应用程序辅助功能的实用 ARIA 示例</span><span class="sxs-lookup"><span data-stu-id="07f16-193">Practical ARIA examples to enhance your application accessibility</span></span>

#### [<span data-ttu-id="07f16-194">OpenAjax 示例</span><span class="sxs-lookup"><span data-stu-id="07f16-194">OpenAjax Examples</span></span>](http://oaa-accessibility.org/)
<span data-ttu-id="07f16-195">OpenAjax 联盟网站是一个出色的资源，用于验证 WAI-ARIA 的规则，并提供 WAI-ARIA ARIA 实现的一些示例。</span><span class="sxs-lookup"><span data-stu-id="07f16-195">The OpenAjax Alliance website is an excellent resource for verifying the rules for WAI-ARIA and provides a number of examples of WAI-ARIA implementations.</span></span>

#### [<span data-ttu-id="07f16-196">模式</span><span class="sxs-lookup"><span data-stu-id="07f16-196">Patterns</span></span>](http://a11yproject.com/patterns.html)
<span data-ttu-id="07f16-197">[A11Y 项目](http://a11yproject.com/) 提供了易于访问的小组件和图案（如菜单、按钮、工具提示等）库。</span><span class="sxs-lookup"><span data-stu-id="07f16-197">[The A11Y Project](http://a11yproject.com/) offers a library of accessible widgets and patterns like menus, buttons, tooltips, and more.</span></span>

### <span data-ttu-id="07f16-198">辅助功能技术 & 工具</span><span class="sxs-lookup"><span data-stu-id="07f16-198">Accessibility Techniques & Tools</span></span>
#### [<span data-ttu-id="07f16-199">辅助功能：创建适用于 Microsoft Edge 的易于访问的扩展图标</span><span class="sxs-lookup"><span data-stu-id="07f16-199">Accessibility: Creating accessible extension icons for Microsoft Edge</span></span>](../extensions/guides/accessibility.md)
<span data-ttu-id="07f16-200">获取有关为 Microsoft Edge 创建易于访问的扩展图标的指南。</span><span class="sxs-lookup"><span data-stu-id="07f16-200">Get guidance on creating accessible extensions icons for Microsoft Edge.</span></span>

#### [<span data-ttu-id="07f16-201">辅助名称和描述：计算和映射1。1</span><span class="sxs-lookup"><span data-stu-id="07f16-201">Accessible Name and Description: Computation and Mappings 1.1</span></span>](https://www.w3.org/TR/accname-1.1/)
<span data-ttu-id="07f16-202">此 W3C 映射文档介绍了浏览器如何确定 web 内容语言的辅助对象的名称和说明，以及如何在辅助功能 Api 中公开它们。</span><span class="sxs-lookup"><span data-stu-id="07f16-202">This W3C mapping document explains how browsers determine name and descriptions of accessible objects from web content languages and expose them in accessibility APIs.</span></span>

#### [<span data-ttu-id="07f16-203">辅助功能评估资源</span><span class="sxs-lookup"><span data-stu-id="07f16-203">Accessibility Evaluation Resources</span></span>](https://www.w3.org/WAI/eval/Overview.html)
<span data-ttu-id="07f16-204">辅助功能评估资源是由 W3C 使用的多页资源，用于概括评估网站辅助功能的不同方法。</span><span class="sxs-lookup"><span data-stu-id="07f16-204">Accessibility Evaluation Resources is a multi-page resource by the W3C that outlines different approaches for evaluating websites for accessibility.</span></span>

#### [<span data-ttu-id="07f16-205">辅助技术兼容性测试</span><span class="sxs-lookup"><span data-stu-id="07f16-205">Assistive technology compatibility tests</span></span>](http://www.powermapper.com/tests/)
<span data-ttu-id="07f16-206">测试结果，显示不同内容类型和标准在辅助技术中的行为如何在) （如屏幕阅读器） (。</span><span class="sxs-lookup"><span data-stu-id="07f16-206">Test results showing how different content types and standards behave in assistive technologies (AT) like screen readers.</span></span>

#### [<span data-ttu-id="07f16-207">构建易于访问的网站</span><span class="sxs-lookup"><span data-stu-id="07f16-207">Building accessible websites just got a lot easier</span></span>](https://blogs.msdn.microsoft.com/webdev/2016/05/02/building-accessible-websites-just-got-a-lot-easier/)
<span data-ttu-id="07f16-208">此 .NET Web 开发和工具博客文章介绍 Visual Studio 扩展 [Web 辅助功能检查器](https://go.microsoft.com/fwlink/p/?linkid=841539)。</span><span class="sxs-lookup"><span data-stu-id="07f16-208">This .NET Web Development and Tools blog post describes the Visual Studio extension [Web Accessibility Checker](https://go.microsoft.com/fwlink/p/?linkid=841539).</span></span>

#### [<span data-ttu-id="07f16-209">Core 辅助功能 API 映射1。1</span><span class="sxs-lookup"><span data-stu-id="07f16-209">Core Accessibility API Mappings 1.1</span></span>](https://www.w3.org/TR/core-aam-1.1/)
<span data-ttu-id="07f16-210">此 W3C 映射文档介绍了如何向辅助功能 Api 公开 web 内容语言的语义。</span><span class="sxs-lookup"><span data-stu-id="07f16-210">This W3C mapping document explains how the semantics of web content languages are exposed to accessibility APIs.</span></span>  

#### [<span data-ttu-id="07f16-211">轻松检查–网页辅助功能的首次审核</span><span class="sxs-lookup"><span data-stu-id="07f16-211">Easy Checks – A First Review of Web Accessibility</span></span>](https://www.w3.org/WAI/eval/preliminary.html)
<span data-ttu-id="07f16-212">WAI-ARIA 的一系列快速检查，可帮助你 asses 网页的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="07f16-212">A series of quick checks by the WAI that help you asses the accessibility of a web page.</span></span>

#### [<span data-ttu-id="07f16-213">如何满足 WCAG 2。0</span><span class="sxs-lookup"><span data-stu-id="07f16-213">How to Meet WCAG 2.0</span></span>](https://www.w3.org/WAI/WCAG20/quickref/)
<span data-ttu-id="07f16-214">有关 Web 内容辅助功能准则的快速参考指南 (WCAG) 2.0 要求 (成功条件) 和技术。</span><span class="sxs-lookup"><span data-stu-id="07f16-214">A quick reference to Web Content Accessibility Guidelines (WCAG) 2.0 requirements (success criteria) and techniques.</span></span>

#### [<span data-ttu-id="07f16-215">HTML 辅助功能 API 映射1。0</span><span class="sxs-lookup"><span data-stu-id="07f16-215">HTML Accessibility API Mappings 1.0</span></span>](https://www.w3.org/TR/html-aam-1.0/)
<span data-ttu-id="07f16-216">此 W3C 映射文档介绍了如何将 HTML 5.1 元素和属性映射到平台辅助功能 Api。</span><span class="sxs-lookup"><span data-stu-id="07f16-216">This W3C mappings document explains how HTML5.1 element and attributes map to platform accessibility APIs.</span></span>


#### [<span data-ttu-id="07f16-217">快速提示</span><span class="sxs-lookup"><span data-stu-id="07f16-217">Quick Tips</span></span>](http://a11yproject.com/#Quick-tips)
<span data-ttu-id="07f16-218">[A11Y 项目](http://a11yproject.com/)辅助功能的快速 web 开发提示列表。</span><span class="sxs-lookup"><span data-stu-id="07f16-218">A list of quick web development tips for accessibility by [The A11Y Project](http://a11yproject.com/).</span></span>

#### [<span data-ttu-id="07f16-219">网站扫描</span><span class="sxs-lookup"><span data-stu-id="07f16-219">Site Scan</span></span>](https://developer.microsoft.com/microsoft-edge/tools/staticscan/)
<span data-ttu-id="07f16-220">Microsoft Edge 开发人员中心上的网站扫描工具检查是否存在过期的库、布局问题和辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="07f16-220">The Site Scan tool on Microsoft Edge Dev Center checks for out-of-date libraries, layout issues, and accessibility issues.</span></span>

#### [<span data-ttu-id="07f16-221">WCAG 2.0 的技术</span><span class="sxs-lookup"><span data-stu-id="07f16-221">Techniques for WCAG 2.0</span></span>](https://www.w3.org/TR/WCAG20-TECHS/Overview.html)
<span data-ttu-id="07f16-222">来自 W3C 的技术，这些技术根据 (WCAG) 2.0 的成功条件，提供 web 开发人员对会议 [Web 内容辅助功能准则](https://w3.org/TR/WCAG20/) 的指导。</span><span class="sxs-lookup"><span data-stu-id="07f16-222">Techniques from the W3C that provide guidance for web developers on meeting [Web Content Accessibility Guidelines (WCAG) 2.0](https://w3.org/TR/WCAG20/) success criteria.</span></span>

#### [<span data-ttu-id="07f16-223">针对 Web 辅助功能进行开发的提示</span><span class="sxs-lookup"><span data-stu-id="07f16-223">Tips on Developing for Web Accessibility</span></span>](https://w3.org/WAI/gettingstarted/tips/developing.html)
<span data-ttu-id="07f16-224">来自 W3C 的提示，用于开发对残疾人士更易于访问的 web 内容。</span><span class="sxs-lookup"><span data-stu-id="07f16-224">Tips from the W3C on developing web content that is more accessible to people with disabilities.</span></span>

#### [<span data-ttu-id="07f16-225">WAI-ARIA-ARIA 创作做法1。1</span><span class="sxs-lookup"><span data-stu-id="07f16-225">WAI-ARIA Authoring Practices 1.1</span></span>](http://w3c.github.io/aria-practices/)
<span data-ttu-id="07f16-226">由 W3C 提供的文档，提供读者对如何使用 WAI-ARIA-ARIA 1.1 的理解，并建议使用 WAI-ARIA 角色、状态和属性来访问小组件、导航和行为的方法。</span><span class="sxs-lookup"><span data-stu-id="07f16-226">A document by the W3C that provides readers with an understanding of how to use WAI-ARIA 1.1 and recommends approaches to make widgets, navigation, and behaviors accessible using WAI-ARIA roles, states, and properties.</span></span>

#### [<span data-ttu-id="07f16-227">WAI-ARIA 指南和技术</span><span class="sxs-lookup"><span data-stu-id="07f16-227">WAI Guidelines and Techniques</span></span>](https://w3.org/WAI/guid-tech.html)
<span data-ttu-id="07f16-228">由 WAI-ARIA 开发的一系列 web 辅助功能指南和标准。</span><span class="sxs-lookup"><span data-stu-id="07f16-228">A series of web accessibility guidelines and standards developed by the WAI.</span></span>  

#### [<span data-ttu-id="07f16-229">Web 辅助功能评估工具列表</span><span class="sxs-lookup"><span data-stu-id="07f16-229">Web Accessibility Evaluation Tools List</span></span>](https://www.w3.org/WAI/ER/tools/index.html)
<span data-ttu-id="07f16-230">Web 辅助功能评估工具列表，可帮助确定网站是否满足辅助功能指南。</span><span class="sxs-lookup"><span data-stu-id="07f16-230">A list of web accessibility evaluation tools to help determine if websites meet accessibility guidelines.</span></span>

#### [<span data-ttu-id="07f16-231">Web 辅助功能：了解每个人的影响和好处</span><span class="sxs-lookup"><span data-stu-id="07f16-231">Web Accessibility Perspectives: Explore the Impact and Benefits for Everyone</span></span>](https://w3.org/WAI/perspectives/)
<span data-ttu-id="07f16-232">W3C 关于辅助功能和每个人的好处的影响的一系列简短的课程视频。</span><span class="sxs-lookup"><span data-stu-id="07f16-232">A series of short situational videos by the W3C about the impact of accessibility and the benefits for everyone.</span></span>

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
