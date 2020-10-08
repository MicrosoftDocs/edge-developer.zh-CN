---
ms.assetid: 1b3ebc25-d023-4f23-bbba-dce066c20de8
description: 浏览 (ARIA) 的最佳做法和易于访问的富 Internet 应用程序，以便创建易于访问的网站。
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
# <span data-ttu-id="3e9fb-104">构建易于访问的网站</span><span class="sxs-lookup"><span data-stu-id="3e9fb-104">Building Accessible Websites</span></span>
<span data-ttu-id="3e9fb-105">Web 使用 HTML、CSS 和 JavaScript 的组合生成了动态、复杂的网站、应用程序和用户界面。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-105">The web is filled with dynamic and complex websites, applications, and user interfaces built using a combination of HTML, CSS, and JavaScript.</span></span>  <span data-ttu-id="3e9fb-106">但是，如果在设计和构建时不考虑辅助功能，则依赖 [辅助技术](https://webaim.org/articles/motor/assistive) 浏览 web 的用户很难使用这些复杂的网站。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-106">However, when designed and built without accessibility in mind, these complex websites are difficult to use by people who rely on [assistive technologies](https://webaim.org/articles/motor/assistive) to browse the web.</span></span> <span data-ttu-id="3e9fb-107">构建残疾人士易于访问的网站需要有关用户界面的语义信息。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-107">Building websites that are accessible to people with disabilities requires semantic information about the user interface.</span></span> <span data-ttu-id="3e9fb-108">这允许辅助技术（如屏幕阅读器）传达必要的信息，以帮助具有各种功能的人员使用该网站。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-108">This allows for assistive technologies, like screen readers, to convey the necessary information to help people with a range of abilities use the website.</span></span>

<span data-ttu-id="3e9fb-109">有关 Microsoft Edge 支持的新 HTML5 功能 accessibly 的信息，请访问 [HTML5Accessibility](https://html5accessibility.com) 。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-109">Visit [HTML5Accessibility](https://html5accessibility.com) for information on which new HTML5 features are accessibly supported by Microsoft Edge.</span></span>

## <span data-ttu-id="3e9fb-110">辅助功能的工作原理</span><span class="sxs-lookup"><span data-stu-id="3e9fb-110">How Accessibility Works</span></span>

<span data-ttu-id="3e9fb-111">辅助技术添加了计算机通常不具备的功能。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-111">Assistive technologies add capabilities that computers don't usually have.</span></span> <span data-ttu-id="3e9fb-112">例如，视觉障碍的用户可能将其键盘与辅助技术（如屏幕阅读器）结合使用，而不是使用鼠标和屏幕直接使用浏览器。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-112">For example, a visually impaired user might use their keyboard in combination with assistive technology such as a screen reader, rather than directly using the browser with the mouse and screen.</span></span> <span data-ttu-id="3e9fb-113">对于 Microsoft 平台和 web 上的应用程序，辅助技术与 Microsoft [UI 自动化](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx)、特定于应用程序的对象模型（如文档对象模型 (DOM) 在 Microsoft Edge 中）或它们的组合进行交互。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-113">For applications on Microsoft platforms and on the web, the assistive technology interacts with Microsoft [UI Automation](https://msdn.microsoft.com/library/windows/desktop/bb892135.aspx), an application-specific object model such as the Document Object Model (DOM) in Microsoft Edge, or a combination of these.</span></span>

<span data-ttu-id="3e9fb-114">对于 web 开发人员，某些 HTML 元素映射到 UI 自动化对象，因此在选择这些 HTML 元素时，开发人员可以使用内置于这些元素的辅助功能属性和事件。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-114">For web developers, certain HTML elements are mapped to UI Automation objects, so in selecting those HTML elements, the developer can use the accessibility properties and events built in to those elements.</span></span> <span data-ttu-id="3e9fb-115">在开发您的网站时，通常只需考虑确保 API 正确地写入 (或指定了相应的元素) ，才能使应用程序易于访问。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-115">While developing your website, you usually only need to be concerned with ensuring that the API is correctly written to (or that the appropriate element is specified), in order for the application to be accessible.</span></span> <span data-ttu-id="3e9fb-116">有关详细信息，请查看 [Microsoft Edge 中的 ARIA 和 UI 自动化](./build/ARIA-and-UI-Automation.md) 。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-116">Check out [ARIA and UI Automation in Microsoft Edge](./build/ARIA-and-UI-Automation.md) for more information.</span></span>  <span data-ttu-id="3e9fb-117">有关可访问的通用 Windows 平台 (UWP) 应用的信息，请参阅 Windows 开发人员中心中的 " [辅助功能](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility) " 主题。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-117">For information on accessible Universal Windows Platform (UWP) apps, see the [Accessibility](https://msdn.microsoft.com/windows/uwp/accessibility/accessibility) topic in the Windows Dev Center.</span></span>

<span data-ttu-id="3e9fb-118">可通过良好的编码实践解决动态内容的许多常见辅助功能问题，并且 [WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629) 文档包含许多技术和最佳做法，可帮助你创建更易于访问的动态 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-118">Many common accessibility issues with dynamic content can be addressed by good coding practice, and the [WCAG 2.0](https://go.microsoft.com/fwlink/p/?LinkID=24629) documentation includes many techniques and best practices to help you create more accessible dynamic web applications.</span></span> <span data-ttu-id="3e9fb-119">但是，即使正确编码，也不一定可以访问动态内容。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-119">Even when coded properly, however, dynamic content is not necessarily accessible.</span></span> <span data-ttu-id="3e9fb-120">[ (ARIA) 易于访问的富 Internet 应用程序 ](#aria) 可帮助解决此问题。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-120">[Accessible Rich Internet Applications (ARIA)](#aria) helps overcome this issue.</span></span>  

<span data-ttu-id="3e9fb-121">有关 web 辅助功能的详细信息，请参阅[Web 辅助功能计划](https://www.w3.org/WAI/)的[Web 辅助功能简介](https://www.w3.org/WAI/intro/accessibility.php) (wai-aria) 。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-121">For more information on web accessibility, check out the [Introduction to Web Accessibility](https://www.w3.org/WAI/intro/accessibility.php) by the [Web Accessibility Initiative](https://www.w3.org/WAI/) (WAI).</span></span>

## <span data-ttu-id="3e9fb-122">ARIA</span><span class="sxs-lookup"><span data-stu-id="3e9fb-122">ARIA</span></span>
<span data-ttu-id="3e9fb-123">W3C's [Web 辅助功能计划](https://www.w3.org/WAI/) (ARIA) 规范的[易于访问的富 Internet 应用程序](https://www.w3.org/TR/wai-aria/)定义为使动态 Web 内容和自定义用户界面可供所有人访问的语法。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-123">The [Accessible Rich Internet Applications](https://www.w3.org/TR/wai-aria/) (ARIA) specification by the W3C's [Web Accessibility Initiative](https://www.w3.org/WAI/) defines as a syntax for making dynamic web content and custom user interfaces accessible to all people.</span></span> <span data-ttu-id="3e9fb-124">ARIA 通过使用 (角色、属性和状态) 的其他属性来扩展 HTML，这些属性旨在传递自定义语义。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-124">ARIA extends HTML by using additional attributes (roles, properties, and states) that are designed to convey custom semantics.</span></span> <span data-ttu-id="3e9fb-125">浏览器使用这些属性将控件的状态和角色传递给辅助功能 API。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-125">These attributes are used by browsers to pass along the controls' state and role to the accessibility API.</span></span>

### <span data-ttu-id="3e9fb-126">角色、属性和状态</span><span class="sxs-lookup"><span data-stu-id="3e9fb-126">Roles, Properties, and States</span></span>
<span data-ttu-id="3e9fb-127">在使用属性的元素上设置 ARIA 角色， [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) 以提供有关元素的辅助技术和辅助功能 api 信息。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-127">ARIA roles are set on elements using the [`role`](https://msdn.microsoft.com/library/cc304102(v=vs.85).aspx) attribute to give assistive technologies and accessibility APIs information about the element.</span></span> <span data-ttu-id="3e9fb-128">例如，以下 `<li>` 元素被分配 `role="menuitem"` 为表示它是菜单中的项目。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-128">For example, the below `<li>` element is assigned `role="menuitem"` to signify it's an item in a menu.</span></span>

``` html
<li role="menuitem">Home</li>
```

<span data-ttu-id="3e9fb-129">ARIA 状态和属性是 aria 的前缀属性，提供有关对象的特定信息，以帮助形成角色性质的定义。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-129">ARIA states and properties are aria-prefixed attributes that provide specific information about an object to help form the definition of the nature of roles.</span></span> <span data-ttu-id="3e9fb-130">属性是对象本质所必需的属性，如 [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) 和 [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx) 。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-130">Properties are attributes that are essential to the nature of an object, like [`aria-readonly`](https://msdn.microsoft.com/library/cc304089(v=vs.85).aspx) and [`aria-haspopup`](https://msdn.microsoft.com/library/cc304081(v=vs.85).aspx).</span></span> <span data-ttu-id="3e9fb-131">更改属性会影响对象的含义。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-131">Changing a property affects the meaning of the object.</span></span> <span data-ttu-id="3e9fb-132">在下面的示例中， `aria-haspopup="true"` 将在菜单项上设置属性 `<li>` 以表示它具有弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-132">In the example below, the property `aria-haspopup="true"` is set on a `<li>` menu item to signify it has a popup.</span></span>

``` html
<li role="menuitem" aria-haspopup="true">Open</li>
```

<span data-ttu-id="3e9fb-133">状态不会更改对象的性质，而是表示与对象或与对象的用户交互相关联的信息，如 [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) 或 [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx) 。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-133">States do not change the nature of the object, but represent information associated with the object or user interaction with the object, like [`aria-hidden`](https://msdn.microsoft.com/library/cc304083(v=vs.85).aspx) or [`aria-checked`](https://msdn.microsoft.com/library/cc304075(v=vs.85).aspx).</span></span> <span data-ttu-id="3e9fb-134">例如， `aria-checked="false"` 以下示例中的状态表示未选中复选框。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-134">For example, the state `aria-checked="false"` in the example below represents that the checkbox is not checked.</span></span>

``` html
<div role="checkbox" aria-checked="false">Accept</div>
```

<span data-ttu-id="3e9fb-135">通过 W3C 转到 ["角色" 模型](https://www.w3.org/TR/wai-aria-1.1/#roles) 以查看角色、属性和状态的完整列表。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-135">Go to [The Roles Model](https://www.w3.org/TR/wai-aria-1.1/#roles) by the W3C to see a full list of roles, properties, and states.</span></span>

<span data-ttu-id="3e9fb-136">有关 ARIA 的详细信息，请参阅 " [资源](#resources) " 部分中的 ARIA。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-136">For more information on ARIA, see the ARIA in the [Resources](#resources) section.</span></span>

## <span data-ttu-id="3e9fb-137">资源</span><span class="sxs-lookup"><span data-stu-id="3e9fb-137">Resources</span></span>

### <span data-ttu-id="3e9fb-138">辅助功能基础知识</span><span class="sxs-lookup"><span data-stu-id="3e9fb-138">Accessibility Basics</span></span>
#### [<span data-ttu-id="3e9fb-139">A11Y 项目</span><span class="sxs-lookup"><span data-stu-id="3e9fb-139">The A11Y Project</span></span>](http://a11yproject.com/)
<span data-ttu-id="3e9fb-140">A11Y 项目是社区驱动的工作，使 web 辅助功能更易于使用。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-140">The A11Y Project is a community-driven effort to make web accessibility easier.</span></span> <span data-ttu-id="3e9fb-141">查看 [A11Y 项目](https://a11yproject.com/) 网站，了解基本辅助功能原则、其易于访问的模式和小组件 [库](https://a11yproject.com/patterns)以及它们在辅助功能软件、博客、书籍和工具上的 [资源](http://a11yproject.com/resources.html) 。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-141">Check out [The A11Y Project](https://a11yproject.com/) site to learn about basic accessibility principles, their accessible pattern and widget [library](https://a11yproject.com/patterns), and their [resources](http://a11yproject.com/resources.html) on accessibility software, blogs, books, and tools.</span></span>

#### [<span data-ttu-id="3e9fb-142"> (WAI-ARIA 的 Web 辅助功能计划) </span><span class="sxs-lookup"><span data-stu-id="3e9fb-142">Web Accessibility Initiative (WAI)</span></span>](https://w3.org/WAI/)
<span data-ttu-id="3e9fb-143">W3C's Web 辅助功能计划 (WAI-ARIA) 是帮助改进 Web 辅助功能的一项工作。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-143">The W3C's Web Accessibility Initiative (WAI) is an effort to help improve the accessibility of the web.</span></span> <span data-ttu-id="3e9fb-144">他们的网站提供了各种资源来 [开始使用 Web 辅助功能](https://www.w3.org/WAI/gettingstarted/Overview.html)， [设计包括 "包含](https://www.w3.org/WAI/users/Overview.html)"、" [教程" 和 "演示文稿](https://www.w3.org/WAI/train.html)" 等。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-144">Their site provides a variety of resources for [Getting Started with Web Accessibility](https://www.w3.org/WAI/gettingstarted/Overview.html), [Designing for Inclusion](https://www.w3.org/WAI/users/Overview.html), [tutorials and presentations](https://www.w3.org/WAI/train.html), and more.</span></span>

### <span data-ttu-id="3e9fb-145">辅助功能博客</span><span class="sxs-lookup"><span data-stu-id="3e9fb-145">Accessibility Blogs</span></span>
#### [<span data-ttu-id="3e9fb-146">Paciello 组</span><span class="sxs-lookup"><span data-stu-id="3e9fb-146">The Paciello Group</span></span>](https://www.paciellogroup.com/blog/)
<span data-ttu-id="3e9fb-147">Paciello 组为全球各地的组织提供咨询和技术解决方案，以确保客户能够有效、高效地访问所有受众，同时满足政府和国际标准。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-147">The Paciello Group provides consulting and technology solutions to organizations around the world to ensure their clients reach all audiences effectively and efficiently, while meeting governmental and international standards.</span></span> <span data-ttu-id="3e9fb-148">其博客介绍诸如 web 辅助功能最佳做法、辅助功能工具和辅助功能趋势等主题。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-148">Their blog covers topics like web accessibility best practices, accessibility tools, and accessibility trends.</span></span>

#### [<span data-ttu-id="3e9fb-149">轻松访问</span><span class="sxs-lookup"><span data-stu-id="3e9fb-149">Simply Accessible</span></span>](http://simplyaccessible.com/articles/)
<span data-ttu-id="3e9fb-150">简单的辅助功能是一组辅助功能专家团队，可提供辅助功能培训、咨询以及更多更改 web 上的辅助功能的感觉。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-150">Simply Accessible is a team of accessibility specialists providing accessibility training, consulting and more to change the perception of accessibility on the web.</span></span> <span data-ttu-id="3e9fb-151">他们的 [文章](http://simplyaccessible.com/articles/) 部分讨论了 web 辅助功能、易于访问的设计等的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-151">Their [Articles](http://simplyaccessible.com/articles/) section discusses best practices for web accessibility, accessible design, and more.</span></span>

#### [<span data-ttu-id="3e9fb-152">SSB 邓 Group (SSB) </span><span class="sxs-lookup"><span data-stu-id="3e9fb-152">SSB BART Group (SSB)</span></span>](http://www.ssbbartgroup.com/blog/)
<span data-ttu-id="3e9fb-153">SSB 邓 Group 是一个数字辅助公司，支持其客户开发和部署易于访问的产品和服务。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-153">SSB BART Group is a digital accessibility firm supporting their clients in developing and deploying accessible products and services.</span></span> <span data-ttu-id="3e9fb-154">其博客地址主题如 ARIA 最佳做法、辅助功能趋势、网络研讨会等。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-154">Their blog addresses topics like ARIA best practices, accessibility trends, webinars, and more.</span></span>

### <span data-ttu-id="3e9fb-155">辅助功能示例</span><span class="sxs-lookup"><span data-stu-id="3e9fb-155">Accessible Examples</span></span>
#### [<span data-ttu-id="3e9fb-156">ally.js 教程</span><span class="sxs-lookup"><span data-stu-id="3e9fb-156">ally.js - Tutorials</span></span>](http://allyjs.io/tutorials/)
<span data-ttu-id="3e9fb-157">JavaScript 库通过使辅助功能更简单，帮助现代 web 应用程序提供辅助功能。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-157">JavaScript library to help modern web applications with accessibility concerns by making accessibility simpler.</span></span>

#### [<span data-ttu-id="3e9fb-158">Heydonworks-ARIA 示例</span><span class="sxs-lookup"><span data-stu-id="3e9fb-158">Heydonworks - ARIA Examples</span></span>](http://heydonworks.com/practical_aria_examples/)
<span data-ttu-id="3e9fb-159">用于增强你的应用程序辅助功能的实用 ARIA 示例</span><span class="sxs-lookup"><span data-stu-id="3e9fb-159">Practical ARIA examples to enhance your application accessibility</span></span>

#### [<span data-ttu-id="3e9fb-160">OpenAjax 示例</span><span class="sxs-lookup"><span data-stu-id="3e9fb-160">OpenAjax Examples</span></span>](http://oaa-accessibility.org/)
<span data-ttu-id="3e9fb-161">OpenAjax 联盟网站是一个出色的资源，用于验证 WAI-ARIA 的规则，并提供 WAI-ARIA ARIA 实现的一些示例。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-161">The OpenAjax Alliance website is an excellent resource for verifying the rules for WAI-ARIA and provides a number of examples of WAI-ARIA implementations.</span></span>

#### [<span data-ttu-id="3e9fb-162">模式</span><span class="sxs-lookup"><span data-stu-id="3e9fb-162">Patterns</span></span>](http://a11yproject.com/patterns.html)
<span data-ttu-id="3e9fb-163">[A11Y 项目](http://a11yproject.com/) 提供了易于访问的小组件和图案（如菜单、按钮、工具提示等）库。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-163">[The A11Y Project](http://a11yproject.com/) offers a library of accessible widgets and patterns like menus, buttons, tooltips, and more.</span></span>

### <span data-ttu-id="3e9fb-164">辅助功能技术 & 工具</span><span class="sxs-lookup"><span data-stu-id="3e9fb-164">Accessibility Techniques & Tools</span></span>
#### [<span data-ttu-id="3e9fb-165">辅助功能：创建适用于 Microsoft Edge 的易于访问的扩展图标</span><span class="sxs-lookup"><span data-stu-id="3e9fb-165">Accessibility: Creating accessible extension icons for Microsoft Edge</span></span>](../extensions/guides/accessibility.md)
<span data-ttu-id="3e9fb-166">获取有关为 Microsoft Edge 创建易于访问的扩展图标的指南。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-166">Get guidance on creating accessible extensions icons for Microsoft Edge.</span></span>

#### [<span data-ttu-id="3e9fb-167">辅助名称和描述：计算和映射1。1</span><span class="sxs-lookup"><span data-stu-id="3e9fb-167">Accessible Name and Description: Computation and Mappings 1.1</span></span>](https://www.w3.org/TR/accname-1.1/)
<span data-ttu-id="3e9fb-168">此 W3C 映射文档介绍了浏览器如何确定 web 内容语言的辅助对象的名称和说明，以及如何在辅助功能 Api 中公开它们。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-168">This W3C mapping document explains how browsers determine name and descriptions of accessible objects from web content languages and expose them in accessibility APIs.</span></span>

#### [<span data-ttu-id="3e9fb-169">辅助功能评估资源</span><span class="sxs-lookup"><span data-stu-id="3e9fb-169">Accessibility Evaluation Resources</span></span>](https://www.w3.org/WAI/eval/Overview.html)
<span data-ttu-id="3e9fb-170">辅助功能评估资源是由 W3C 使用的多页资源，用于概括评估网站辅助功能的不同方法。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-170">Accessibility Evaluation Resources is a multi-page resource by the W3C that outlines different approaches for evaluating websites for accessibility.</span></span>

#### [<span data-ttu-id="3e9fb-171">辅助技术兼容性测试</span><span class="sxs-lookup"><span data-stu-id="3e9fb-171">Assistive technology compatibility tests</span></span>](http://www.powermapper.com/tests/)
<span data-ttu-id="3e9fb-172">测试结果，显示不同内容类型和标准在辅助技术中的行为如何在) （如屏幕阅读器） (。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-172">Test results showing how different content types and standards behave in assistive technologies (AT) like screen readers.</span></span>

#### [<span data-ttu-id="3e9fb-173">构建易于访问的网站</span><span class="sxs-lookup"><span data-stu-id="3e9fb-173">Building accessible websites just got a lot easier</span></span>](https://blogs.msdn.microsoft.com/webdev/2016/05/02/building-accessible-websites-just-got-a-lot-easier/)
<span data-ttu-id="3e9fb-174">此 .NET Web 开发和工具博客文章介绍 Visual Studio 扩展 [Web 辅助功能检查器](https://go.microsoft.com/fwlink/p/?linkid=841539)。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-174">This .NET Web Development and Tools blog post describes the Visual Studio extension [Web Accessibility Checker](https://go.microsoft.com/fwlink/p/?linkid=841539).</span></span>

#### [<span data-ttu-id="3e9fb-175">Core 辅助功能 API 映射1。1</span><span class="sxs-lookup"><span data-stu-id="3e9fb-175">Core Accessibility API Mappings 1.1</span></span>](https://www.w3.org/TR/core-aam-1.1/)
<span data-ttu-id="3e9fb-176">此 W3C 映射文档介绍了如何向辅助功能 Api 公开 web 内容语言的语义。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-176">This W3C mapping document explains how the semantics of web content languages are exposed to accessibility APIs.</span></span>  

#### [<span data-ttu-id="3e9fb-177">轻松检查–网页辅助功能的首次审核</span><span class="sxs-lookup"><span data-stu-id="3e9fb-177">Easy Checks – A First Review of Web Accessibility</span></span>](https://www.w3.org/WAI/eval/preliminary.html)
<span data-ttu-id="3e9fb-178">WAI-ARIA 的一系列快速检查，可帮助你 asses 网页的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-178">A series of quick checks by the WAI that help you asses the accessibility of a web page.</span></span>

#### [<span data-ttu-id="3e9fb-179">如何满足 WCAG 2。0</span><span class="sxs-lookup"><span data-stu-id="3e9fb-179">How to Meet WCAG 2.0</span></span>](https://www.w3.org/WAI/WCAG20/quickref/)
<span data-ttu-id="3e9fb-180">有关 Web 内容辅助功能准则的快速参考指南 (WCAG) 2.0 要求 (成功条件) 和技术。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-180">A quick reference to Web Content Accessibility Guidelines (WCAG) 2.0 requirements (success criteria) and techniques.</span></span>

#### [<span data-ttu-id="3e9fb-181">HTML 辅助功能 API 映射1。0</span><span class="sxs-lookup"><span data-stu-id="3e9fb-181">HTML Accessibility API Mappings 1.0</span></span>](https://www.w3.org/TR/html-aam-1.0/)
<span data-ttu-id="3e9fb-182">此 W3C 映射文档介绍了如何将 HTML 5.1 元素和属性映射到平台辅助功能 Api。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-182">This W3C mappings document explains how HTML5.1 element and attributes map to platform accessibility APIs.</span></span>


#### [<span data-ttu-id="3e9fb-183">快速提示</span><span class="sxs-lookup"><span data-stu-id="3e9fb-183">Quick Tips</span></span>](http://a11yproject.com/#Quick-tips)
<span data-ttu-id="3e9fb-184">[A11Y 项目](http://a11yproject.com/)辅助功能的快速 web 开发提示列表。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-184">A list of quick web development tips for accessibility by [The A11Y Project](http://a11yproject.com/).</span></span>

#### [<span data-ttu-id="3e9fb-185">网站扫描</span><span class="sxs-lookup"><span data-stu-id="3e9fb-185">Site Scan</span></span>](https://developer.microsoft.com/microsoft-edge/tools/staticscan/)
<span data-ttu-id="3e9fb-186">Microsoft Edge 开发人员中心上的网站扫描工具检查是否存在过期的库、布局问题和辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-186">The Site Scan tool on Microsoft Edge Dev Center checks for out-of-date libraries, layout issues, and accessibility issues.</span></span>

#### [<span data-ttu-id="3e9fb-187">WCAG 2.0 的技术</span><span class="sxs-lookup"><span data-stu-id="3e9fb-187">Techniques for WCAG 2.0</span></span>](https://www.w3.org/TR/WCAG20-TECHS/Overview.html)
<span data-ttu-id="3e9fb-188">来自 W3C 的技术，这些技术根据 (WCAG) 2.0 的成功条件，提供 web 开发人员对会议 [Web 内容辅助功能准则](https://w3.org/TR/WCAG20/) 的指导。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-188">Techniques from the W3C that provide guidance for web developers on meeting [Web Content Accessibility Guidelines (WCAG) 2.0](https://w3.org/TR/WCAG20/) success criteria.</span></span>

#### [<span data-ttu-id="3e9fb-189">针对 Web 辅助功能进行开发的提示</span><span class="sxs-lookup"><span data-stu-id="3e9fb-189">Tips on Developing for Web Accessibility</span></span>](https://w3.org/WAI/gettingstarted/tips/developing.html)
<span data-ttu-id="3e9fb-190">来自 W3C 的提示，用于开发对残疾人士更易于访问的 web 内容。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-190">Tips from the W3C on developing web content that is more accessible to people with disabilities.</span></span>

#### [<span data-ttu-id="3e9fb-191">WAI-ARIA-ARIA 创作做法1。1</span><span class="sxs-lookup"><span data-stu-id="3e9fb-191">WAI-ARIA Authoring Practices 1.1</span></span>](http://w3c.github.io/aria-practices/)
<span data-ttu-id="3e9fb-192">由 W3C 提供的文档，提供读者对如何使用 WAI-ARIA-ARIA 1.1 的理解，并建议使用 WAI-ARIA 角色、状态和属性来访问小组件、导航和行为的方法。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-192">A document by the W3C that provides readers with an understanding of how to use WAI-ARIA 1.1 and recommends approaches to make widgets, navigation, and behaviors accessible using WAI-ARIA roles, states, and properties.</span></span>

#### [<span data-ttu-id="3e9fb-193">WAI-ARIA 指南和技术</span><span class="sxs-lookup"><span data-stu-id="3e9fb-193">WAI Guidelines and Techniques</span></span>](https://w3.org/WAI/guid-tech.html)
<span data-ttu-id="3e9fb-194">由 WAI-ARIA 开发的一系列 web 辅助功能指南和标准。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-194">A series of web accessibility guidelines and standards developed by the WAI.</span></span>  

#### [<span data-ttu-id="3e9fb-195">Web 辅助功能评估工具列表</span><span class="sxs-lookup"><span data-stu-id="3e9fb-195">Web Accessibility Evaluation Tools List</span></span>](https://www.w3.org/WAI/ER/tools/index.html)
<span data-ttu-id="3e9fb-196">Web 辅助功能评估工具列表，可帮助确定网站是否满足辅助功能指南。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-196">A list of web accessibility evaluation tools to help determine if websites meet accessibility guidelines.</span></span>

#### [<span data-ttu-id="3e9fb-197">Web 辅助功能：了解每个人的影响和好处</span><span class="sxs-lookup"><span data-stu-id="3e9fb-197">Web Accessibility Perspectives: Explore the Impact and Benefits for Everyone</span></span>](https://w3.org/WAI/perspectives/)
<span data-ttu-id="3e9fb-198">W3C 关于辅助功能和每个人的好处的影响的一系列简短的课程视频。</span><span class="sxs-lookup"><span data-stu-id="3e9fb-198">A series of short situational videos by the W3C about the impact of accessibility and the benefits for everyone.</span></span>
