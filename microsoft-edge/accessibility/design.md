---
description: 阅读有关非独占设计工具和最佳做法的资源。
title: 辅助功能 - 设计
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/27/2020
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: 8468f8e1-9f4a-426c-a969-76eab9419137
keywords: 辅助功能， 开发人员辅助功能， 可访问的网站， 边缘， Web 开发， ARIA， 开发人员， UIA， UI 自动化
ms.openlocfilehash: 8d31f7b32cb92794ff8592c239436f3b101a3859
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230815"
---
# <span data-ttu-id="badea-104">设计可访问的网站</span><span class="sxs-lookup"><span data-stu-id="badea-104">Designing Accessible Websites</span></span>  

<span data-ttu-id="badea-105">创建非独占设计可使所有人员无论年龄、教育、地理位置、语言或残障都使用技术。</span><span class="sxs-lookup"><span data-stu-id="badea-105">Creating an inclusive design makes technology usable by all people no matter their age, education, geographic location, language, or disability.</span></span>  <span data-ttu-id="badea-106">使用技术和浏览 Web 的用户具有广泛的能力和首选项。</span><span class="sxs-lookup"><span data-stu-id="badea-106">People using technology and browsing the web have a wide range of abilities and preferences.</span></span>  <span data-ttu-id="badea-107">在设计网站时，请记住以下关键辅助功能方案：</span><span class="sxs-lookup"><span data-stu-id="badea-107">As you design your website, keep in mind the following key accessibility scenarios:</span></span>

*   <span data-ttu-id="badea-108">屏幕阅读器 - 盲或视觉受损的用户依靠屏幕阅读器来解释应用的 UI 并与之交互。</span><span class="sxs-lookup"><span data-stu-id="badea-108">Screen readers—Users who are blind or visually impaired rely on screen readers to interpret and interact with the UI of your app.</span></span>  <span data-ttu-id="badea-109">解释涉及读取 UI 元素名称、角色、值等，与 UI 交互涉及将焦点从一个元素移动到另一个元素和调用功能。</span><span class="sxs-lookup"><span data-stu-id="badea-109">Interpreting involves reading the UI element names, roles, values, and so on, and interacting with the UI involves moving the focus from one element to another and invoking functionality.</span></span>
*   <span data-ttu-id="badea-110">键盘辅助功能 — 许多辅助功能用户依靠键盘导航和操作 UI，方式为：</span><span class="sxs-lookup"><span data-stu-id="badea-110">Keyboard accessibility—Many accessibility users rely on the keyboard to navigate and operate the UI by:</span></span>
    *   <span data-ttu-id="badea-111">使用 Tab 键在各元素间移动焦点。</span><span class="sxs-lookup"><span data-stu-id="badea-111">Moving focus among elements by using the Tab key.</span></span>
    *   <span data-ttu-id="badea-112">使用箭头键在列表、网格、树状视图等容器元素间导航。</span><span class="sxs-lookup"><span data-stu-id="badea-112">Navigating in container elements such as lists, grids, and tree views by using the arrow keys.</span></span>
    *   <span data-ttu-id="badea-113">使用 Enter 或空格 (激活功能 \) \) 调用操作\</span><span class="sxs-lookup"><span data-stu-id="badea-113">Activating functionality \(invoking actions\) by using the Enter or Space key.</span></span>
    *   <span data-ttu-id="badea-114">使用快捷键高效访问其他应用功能。</span><span class="sxs-lookup"><span data-stu-id="badea-114">Using shortcut keys to efficiently access other app functionality.</span></span>
*   <span data-ttu-id="badea-115">辅助视觉体验 - 视觉受损的用户需要足够的文本对比率来表示文本内容，以及整体上具有高对比度主题的良好视觉体验。</span><span class="sxs-lookup"><span data-stu-id="badea-115">Accessible visual experience—Users who are visually impaired need a sufficient text contrast ratio for text content, and a good visual experience with high contrast themes overall.</span></span>  <span data-ttu-id="badea-116">对于色盲用户，需要通过色彩以外的途径传递信息。</span><span class="sxs-lookup"><span data-stu-id="badea-116">Users who are color blind need information to be conveyed in ways other than through color.</span></span>

<span data-ttu-id="badea-117">通过良好的编码实践，可以解决 Web 上的许多常见辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="badea-117">Many common accessibility issues on the web can be solved through good coding practice.</span></span>  <span data-ttu-id="badea-118">[Web 内容辅助功能指南 (WCAG) 2.0](https://www.w3.org/TR/WCAG20)文档提供了可帮助您设计更易于访问的动态 Web 应用程序的技术和最佳实践。</span><span class="sxs-lookup"><span data-stu-id="badea-118">The [Web Content Accessibility Guidelines (WCAG) 2.0](https://www.w3.org/TR/WCAG20) documentation provides techniques and best practices to help you design more accessible dynamic web applications.</span></span>  <span data-ttu-id="badea-119">有关构建可访问网站的信息，请导航到"[构建可访问的网站"。](./build/index.md)</span><span class="sxs-lookup"><span data-stu-id="badea-119">For more information on building accessible websites, navigate to [Building Accessible Websites](./build/index.md) .</span></span>

## <span data-ttu-id="badea-120">资源</span><span class="sxs-lookup"><span data-stu-id="badea-120">Resources</span></span>  

#### [<span data-ttu-id="badea-121">正在针对包含进行设计</span><span class="sxs-lookup"><span data-stu-id="badea-121">Designing for Inclusion</span></span>](https://w3.org/WAI/users/Overview.html)  

<span data-ttu-id="badea-122">W3C Web 辅助功能计划针对包含进行设计提供了一些资源，可帮助你更好地了解残障用户以及如何在设计网站时牢记他们的需求。</span><span class="sxs-lookup"><span data-stu-id="badea-122">Designing for Inclusion by the W3C Web Accessibility Initiative provides resources to help you better understand users with disabilities and how to design your website with them in mind.</span></span>

#### [<span data-ttu-id="badea-123">设计非独占软件</span><span class="sxs-lookup"><span data-stu-id="badea-123">Designing inclusive software</span></span>](https://msdn.microsoft.com/windows/uwp/accessibility/designing-inclusive-software)  

<span data-ttu-id="badea-124">设计非独占软件讨论适用于通用 Windows 平台和 UWP (的 Microsoft 设计) 。</span><span class="sxs-lookup"><span data-stu-id="badea-124">Designing inclusive software discusses Microsoft design principles and practices for the Universal Windows Platform (UWP).</span></span>

#### [<span data-ttu-id="badea-125">残障人士如何使用 Web</span><span class="sxs-lookup"><span data-stu-id="badea-125">How People with Disabilities Use the Web</span></span>](https://www.w3.org/WAI/intro/people-use-web/Overview.html)  

<span data-ttu-id="badea-126">W3C 提供的此资源介绍了残障人士（包括与年龄相关的残障人士）如何使用 Web。</span><span class="sxs-lookup"><span data-stu-id="badea-126">This resource by the W3C introduces how people with disabilities, including people with age-related impairments, use the Web.</span></span>

#### [<span data-ttu-id="badea-127">非独占Toolkit</span><span class="sxs-lookup"><span data-stu-id="badea-127">Inclusive Design Toolkit</span></span>](https://www.microsoft.com/design/practice#howwemake-section)  

<span data-ttu-id="badea-128">Microsoft 开发了非独占Toolkit设计方案，以展示人类多样性如何创建更好的设计约束以及如何将看似简单的解决方案连接到更广泛的市场。</span><span class="sxs-lookup"><span data-stu-id="badea-128">Microsoft developed the Inclusive Design Toolkit to show how human diversity can create better design constraints and how to connect seemingly niche solutions to broader markets.</span></span>
