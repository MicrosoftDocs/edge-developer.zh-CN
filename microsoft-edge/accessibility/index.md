---
description: 了解如何在网站内构建、设计和测试可访问Microsoft Edge。
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
# <span data-ttu-id="5cf44-104">辅助功能概述</span><span class="sxs-lookup"><span data-stu-id="5cf44-104">Accessibility overview</span></span>  

> <span data-ttu-id="5cf44-105">"\[T\]他对残障的影响在 Web 上彻底更改，因为 Web 消除了许多人在物理世界面临的通信和交互障碍。"</span><span class="sxs-lookup"><span data-stu-id="5cf44-105">"\[T\]he impact of disability is radically changed on the Web because the Web removes barriers to communication and interaction that many people face in the physical world."</span></span> [<span data-ttu-id="5cf44-106"> (辅助功能|W3C) </span><span class="sxs-lookup"><span data-stu-id="5cf44-106">(Accessibility | W3C)</span></span>][W3CAccessibility]  

<span data-ttu-id="5cf44-107">世界 [健康组织][WHODisabilities] 将残障定义为"人员正文的功能与它们所生活环境的功能之间的交互不匹配"。</span><span class="sxs-lookup"><span data-stu-id="5cf44-107">The [World Health Organization][WHODisabilities] defines disability as "a mismatch in interaction between the features of a person's body and the features of the environment in which they live".</span></span>  <span data-ttu-id="5cf44-108">残障的范围从情境式残障（例如，在手机上保持一只眼睛的受限移动性或明亮眼睛）到其他与物理、听觉、视觉或年龄相关的障碍。</span><span class="sxs-lookup"><span data-stu-id="5cf44-108">Disabilities range from situational disabilities, like limited mobility while holding a baby or bright sunlight on a phone, to other physical, auditory, visual, or age-related impairments.</span></span>  

<span data-ttu-id="5cf44-109">设计网站和其他包含技术可打造每个人都享受的体验。</span><span class="sxs-lookup"><span data-stu-id="5cf44-109">Designing websites and other technologies for inclusion creates an experience enjoyable by every person.</span></span>  <span data-ttu-id="5cf44-110">非独占设计和 Web 辅助功能使每个人都能够使用 Web。</span><span class="sxs-lookup"><span data-stu-id="5cf44-110">Inclusive design and web accessibility empowers and assists everyone to use the web.</span></span>  

<span data-ttu-id="5cf44-111">下面是一些最佳实践、代码示例和更多资源，可让你了解有关在 Microsoft Edge 中设计、构建[][AccessibilityBuild]和测试可访问网站[][AccessibilityTest]Microsoft Edge。 [][AccessibilityDesign]</span><span class="sxs-lookup"><span data-stu-id="5cf44-111">Here are some best practices, code samples, and further resources for you to learn more about [Designing][AccessibilityDesign], [Building][AccessibilityBuild], and [Testing][AccessibilityTest] accessible websites in Microsoft Edge.</span></span>  

## <span data-ttu-id="5cf44-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5cf44-112">Accessibility in Microsoft Edge</span></span>  

<span data-ttu-id="5cf44-113">在 Microsoft Edge 中，我们引入了现代[UI 自动化 API][WindowsWin32AutoEntryui] \ (UIA API\) 。</span><span class="sxs-lookup"><span data-stu-id="5cf44-113">In Microsoft Edge, we introduced modern [UI Automation API][WindowsWin32AutoEntryui] \(UIA API\).</span></span>  <span data-ttu-id="5cf44-114">UIA 的变化是浏览器辅助功能的主要投资，它为依赖于 Windows 10 中的辅助技术的用户提供更具包容性的 Web 体验打下基础。</span><span class="sxs-lookup"><span data-stu-id="5cf44-114">The change to UIA was a major investment in browser accessibility, and it lays the foundation for a more inclusive web experience for users who depend on assistive technology in Windows 10.</span></span>  <span data-ttu-id="5cf44-115">用户还可以从网络引擎的常绿Chromium中获益。</span><span class="sxs-lookup"><span data-stu-id="5cf44-115">Users also benefit from the evergreen nature of the Chromium engine.</span></span>  

<span data-ttu-id="5cf44-116">企业中的辅助功能系统Microsoft Edge支持现代 Web 标准，包括 ARIA、HTML5 和 CSS3。</span><span class="sxs-lookup"><span data-stu-id="5cf44-116">The accessibility system in Microsoft Edge inherently supports modern web standards including ARIA, HTML5, and CSS3.</span></span>  <span data-ttu-id="5cf44-117">简化的浏览器管道的下图将网页内容放入可访问的表示层。</span><span class="sxs-lookup"><span data-stu-id="5cf44-117">The following diagram of the simplified browser pipeline follows webpage content into an accessible presentation layer.</span></span>  

:::image type="complex" source="./media/accessibilityarchitecture.png" alt-text="转换到引擎模型的内容将转换为可视视图和辅助功能视图，这些视图以可视或辅助演示文稿形式呈现":::
   <span data-ttu-id="5cf44-119">转换到引擎模型的内容将转换为可视视图和辅助功能视图，这些视图以可视或辅助演示文稿形式呈现</span><span class="sxs-lookup"><span data-stu-id="5cf44-119">Content transformed to the engine model is projected into visual and accessibility views that are presented either as visual or accessible presentation</span></span>  
:::image-end:::  

<span data-ttu-id="5cf44-120">Microsoft Edge团队持续与 W3C 和其他浏览器供应商合作，以确保新的 Web 平台功能具有足够的内置辅助功能。</span><span class="sxs-lookup"><span data-stu-id="5cf44-120">The Microsoft Edge team works with the W3C and other browser vendors on an ongoing basis to ensure that new web platform features have sufficient built-in accessibility.</span></span>  

<span data-ttu-id="5cf44-121">有关哪些新 HTML5 功能可供用户访问Microsoft Edge，请导航到["HTML5Accessibility"。][HTML5Accessibility]</span><span class="sxs-lookup"><span data-stu-id="5cf44-121">For information on which new HTML5 features are accessibly supported by Microsoft Edge, navigate to [HTML5Accessibility][HTML5Accessibility].</span></span>  

## <span data-ttu-id="5cf44-122">资源</span><span class="sxs-lookup"><span data-stu-id="5cf44-122">Resources</span></span>  

#### <span data-ttu-id="5cf44-123">Microsoft Windows UI 自动化博客</span><span class="sxs-lookup"><span data-stu-id="5cf44-123">Microsoft Windows UI Automation Blog</span></span>  

<span data-ttu-id="5cf44-124">[Microsoft Windows UI 自动化博客][ArchiveBlogsWinuiautomation]涵盖了与 Windows 自动化 API 相关的主题。</span><span class="sxs-lookup"><span data-stu-id="5cf44-124">The [Microsoft Windows UI Automation blog][ArchiveBlogsWinuiautomation] covers topics related to the Windows Automation API.</span></span>  

#### <span data-ttu-id="5cf44-125">Web 辅助功能计划 (，) </span><span class="sxs-lookup"><span data-stu-id="5cf44-125">Web Accessibility Initiative (WAI)</span></span>  

<span data-ttu-id="5cf44-126">Web [辅助功能计划 (一) ， ][W3CWaiHome] 提供 bt W3C 是帮助改善 Web 辅助功能的一项工作。</span><span class="sxs-lookup"><span data-stu-id="5cf44-126">The [Web Accessibility Initiative (WAI)][W3CWaiHome] provided bt the W3C is an effort to help improve the accessibility of the web.</span></span>  <span data-ttu-id="5cf44-127">该网站为 Web 辅助功能入门、[][W3CWaiGettingstartedOverview]包含设计、教程和演示文稿等[][W3CWaiFundamentals][提供了][W3CWaiTeachAdvocate]各种资源。</span><span class="sxs-lookup"><span data-stu-id="5cf44-127">The site provides a variety of resources for [Getting Started with Web Accessibility][W3CWaiGettingstartedOverview], [Designing for Inclusion][W3CWaiFundamentals], [tutorials and presentations][W3CWaiTeachAdvocate], and more.</span></span>  

<!-- links -->  

[AccessibilityBuild]: ./build/index.md "构建可访问的网站|Microsoft Doc"  
[AccessibilityDesign]: ./design.md "设计可访问的网站|Microsoft Doc"  
[AccessibilityTest]: ./test.md "辅助功能测试|Microsoft Docs"  

[WindowsWin32AutoEntryui]: /windows/win32/winauto/entry-uiauto-win32 "UI 自动化|Microsoft Doc"  

[ArchiveBlogsWinuiautomation]: /archive/blogs/winuiautomation/ "Microsoft Windows UI 自动化博客|Microsoft Doc"  

[HTML5Accessibility]: https://html5accessibility.com "HTML5 辅助功能"  

[W3CAccessibility]: https://w3.org/standards/webdesign/accessibility "辅助功能|W3C"  
[W3CWaiFundamentals]: https://w3.org/wai/fundamentals/accessibility-intro "Web 辅助功能|Web 辅助功能计划 (的一) |W3C"  
[W3CWaiGettingstartedOverview]: https://w3.org/wai/gettingstarted/Overview "入门：使网站成为辅助|Web 辅助功能计划 (的一) |W3C"  
[W3CWaiHome]: https://w3.org/wai "Web 辅助功能计划 (的一) |W3C"  
[W3CWaiTeachAdvocate]: https://w3.org/wai/teach-advocate "教学和宣传|Web 辅助功能计划 (的一) |W3C"  

[WHODisabilities]: https://who.int/topics/disabilities "残障|WHO"  

