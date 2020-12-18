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
# <span data-ttu-id="9631c-104">辅助功能概述</span><span class="sxs-lookup"><span data-stu-id="9631c-104">Accessibility overview</span></span>  

> <span data-ttu-id="9631c-105">"\[T\]他对残障的影响在 Web 上发生了根本改变，因为 Web 消除了许多人在物理世界面临的通信和交互障碍。"</span><span class="sxs-lookup"><span data-stu-id="9631c-105">"\[T\]he impact of disability is radically changed on the Web because the Web removes barriers to communication and interaction that many people face in the physical world."</span></span> [<span data-ttu-id="9631c-106"> (辅助功能 |W3C) </span><span class="sxs-lookup"><span data-stu-id="9631c-106">(Accessibility | W3C)</span></span>][W3CAccessibility]  

<span data-ttu-id="9631c-107">世界 [健康组织][WHODisabilities] 将残障定义为"个人正文功能与其生活环境的功能之间的交互不匹配"。</span><span class="sxs-lookup"><span data-stu-id="9631c-107">The [World Health Organization][WHODisabilities] defines disability as "a mismatch in interaction between the features of a person's body and the features of the environment in which they live".</span></span>  <span data-ttu-id="9631c-108">残障范围从情境式残障（如行动不便，同时在电话上长着一只孩子或明亮眼睛）到其他残障、听觉障碍、视觉障碍或与年龄相关的障碍。</span><span class="sxs-lookup"><span data-stu-id="9631c-108">Disabilities range from situational disabilities, like limited mobility while holding a baby or bright sunlight on a phone, to other physical, auditory, visual, or age-related impairments.</span></span>  

<span data-ttu-id="9631c-109">设计网站和其他包含技术可打造每个人都享受的体验。</span><span class="sxs-lookup"><span data-stu-id="9631c-109">Designing websites and other technologies for inclusion creates an experience enjoyable by every person.</span></span>  <span data-ttu-id="9631c-110">非独占设计和 Web 辅助功能使每个人都能够使用 Web。</span><span class="sxs-lookup"><span data-stu-id="9631c-110">Inclusive design and web accessibility empowers and assists everyone to use the web.</span></span>  

<span data-ttu-id="9631c-111">下面是一些最佳做法、代码示例和进一步的资源，可让你了解有关在 Microsoft [][AccessibilityDesign]Edge 中设计、[][AccessibilityTest][构建][AccessibilityBuild]和测试可访问网站的信息。</span><span class="sxs-lookup"><span data-stu-id="9631c-111">Here are some best practices, code samples, and further resources for you to learn more about [Designing][AccessibilityDesign], [Building][AccessibilityBuild], and [Testing][AccessibilityTest] accessible websites in Microsoft Edge.</span></span>  

## <span data-ttu-id="9631c-112">Microsoft Edge 中的辅助功能</span><span class="sxs-lookup"><span data-stu-id="9631c-112">Accessibility in Microsoft Edge</span></span>  

<span data-ttu-id="9631c-113">在 Microsoft Edge 中，我们引入了现代 [UI 自动化 API][WindowsWin32AutoEntryui] \ (UIA API\) 。</span><span class="sxs-lookup"><span data-stu-id="9631c-113">In Microsoft Edge, we introduced modern [UI Automation API][WindowsWin32AutoEntryui] \(UIA API\).</span></span>  <span data-ttu-id="9631c-114">对 UIA 的变更是浏览器辅助功能的主要投资，它为依赖 Windows 10 中的辅助技术的用户提供更具包容性的 Web 体验打下基础。</span><span class="sxs-lookup"><span data-stu-id="9631c-114">The change to UIA was a major investment in browser accessibility, and it lays the foundation for a more inclusive web experience for users who depend on assistive technology in Windows 10.</span></span>  <span data-ttu-id="9631c-115">用户还可以从 Chromium 引擎的常青特性中获益。</span><span class="sxs-lookup"><span data-stu-id="9631c-115">Users also benefit from the evergreen nature of the Chromium engine.</span></span>  

<span data-ttu-id="9631c-116">Microsoft Edge 中的辅助功能系统本身支持现代 Web 标准，包括 ARIA、HTML5 和 CSS3。</span><span class="sxs-lookup"><span data-stu-id="9631c-116">The accessibility system in Microsoft Edge inherently supports modern web standards including ARIA, HTML5, and CSS3.</span></span>  <span data-ttu-id="9631c-117">简化的浏览器管道的下图将网页内容放入可访问的表示层。</span><span class="sxs-lookup"><span data-stu-id="9631c-117">The following diagram of the simplified browser pipeline follows webpage content into an accessible presentation layer.</span></span>  

:::image type="complex" source="./media/accessibilityarchitecture.png" alt-text="转换为引擎模型的内容将转换为可视和辅助功能视图，这些视图以可视或辅助演示文稿形式呈现":::
   <span data-ttu-id="9631c-119">转换为引擎模型的内容将转换为可视和辅助功能视图，这些视图以可视或辅助演示文稿形式呈现</span><span class="sxs-lookup"><span data-stu-id="9631c-119">Content transformed to the engine model is projected into visual and accessibility views that are presented either as visual or accessible presentation</span></span>  
:::image-end:::  

<span data-ttu-id="9631c-120">Microsoft Edge 团队与 W3C 和其他浏览器供应商持续合作，以确保新的 Web 平台功能具有足够的内置辅助功能。</span><span class="sxs-lookup"><span data-stu-id="9631c-120">The Microsoft Edge team works with the W3C and other browser vendors on an ongoing basis to ensure that new web platform features have sufficient built-in accessibility.</span></span>  

<span data-ttu-id="9631c-121">有关 Microsoft Edge 支持哪些新 HTML5 功能的信息，请导航到[HTML5Accessibility。][HTML5Accessibility]</span><span class="sxs-lookup"><span data-stu-id="9631c-121">For information on which new HTML5 features are accessibly supported by Microsoft Edge, navigate to [HTML5Accessibility][HTML5Accessibility].</span></span>  

## <span data-ttu-id="9631c-122">资源</span><span class="sxs-lookup"><span data-stu-id="9631c-122">Resources</span></span>  

#### <span data-ttu-id="9631c-123">Microsoft Windows UI 自动化博客</span><span class="sxs-lookup"><span data-stu-id="9631c-123">Microsoft Windows UI Automation Blog</span></span>  

<span data-ttu-id="9631c-124">[Microsoft Windows UI 自动化博客][ArchiveBlogsWinuiautomation]涵盖与 Windows 自动化 API 相关的主题。</span><span class="sxs-lookup"><span data-stu-id="9631c-124">The [Microsoft Windows UI Automation blog][ArchiveBlogsWinuiautomation] covers topics related to the Windows Automation API.</span></span>  

#### <span data-ttu-id="9631c-125">WEB 辅助功能计划 (或) </span><span class="sxs-lookup"><span data-stu-id="9631c-125">Web Accessibility Initiative (WAI)</span></span>  

<span data-ttu-id="9631c-126">Web [辅助功能计划 (或) BT ][W3CWaiHome] 的一项操作，它旨在帮助改进 Web 的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="9631c-126">The [Web Accessibility Initiative (WAI)][W3CWaiHome] provided bt the W3C is an effort to help improve the accessibility of the web.</span></span>  <span data-ttu-id="9631c-127">该网站为 Web 辅助功能入门、[][W3CWaiGettingstartedOverview]包含设计、教程和[演示文稿][W3CWaiTeachAdvocate]等[][W3CWaiFundamentals]提供了各种资源。</span><span class="sxs-lookup"><span data-stu-id="9631c-127">The site provides a variety of resources for [Getting Started with Web Accessibility][W3CWaiGettingstartedOverview], [Designing for Inclusion][W3CWaiFundamentals], [tutorials and presentations][W3CWaiTeachAdvocate], and more.</span></span>  

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

