---
ms.assetid: 8468f8e1-9f4a-426c-a969-76eab9419137
description: 了解非独占设计工具和最佳做法的资源。
title: 辅助功能-设计
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 辅助功能，面向开发人员的辅助功能，辅助网站，边缘，web 开发，ARIA，开发人员，UIA，UI 自动化
ms.openlocfilehash: c9dfd6dfb9a45f7f8bb3f6d8ebad6c826f3f9e99
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562606"
---
# <span data-ttu-id="dea7f-104">设计易于访问的网站</span><span class="sxs-lookup"><span data-stu-id="dea7f-104">Designing Accessible Websites</span></span>

<span data-ttu-id="dea7f-105">创建非独占设计让所有人都可以免费使用技术，无论他们年龄、教育、地理位置、语言或残疾人士。</span><span class="sxs-lookup"><span data-stu-id="dea7f-105">Creating an inclusive design makes technology usable by all people no matter their age, education, geographic location, language, or disability.</span></span> <span data-ttu-id="dea7f-106">使用技术和浏览 web 的人有多种能力和偏好。</span><span class="sxs-lookup"><span data-stu-id="dea7f-106">People using technology and browsing the web have a wide range of abilities and preferences.</span></span> <span data-ttu-id="dea7f-107">设计网站时，请记住以下关键的辅助功能方案：</span><span class="sxs-lookup"><span data-stu-id="dea7f-107">As you design your website, keep in mind the following key accessibility scenarios:</span></span>

* <span data-ttu-id="dea7f-108">屏幕阅读器-盲人或视觉障碍的用户依靠屏幕阅读器来解释应用的 UI 并与之交互。</span><span class="sxs-lookup"><span data-stu-id="dea7f-108">Screen readers—Users who are blind or visually impaired rely on screen readers to interpret and interact with your app's UI.</span></span> <span data-ttu-id="dea7f-109">解释涉及读取 UI 元素名称、角色、值等，并与 UI 交互，包括将焦点从一个元素移动到另一个元素并调用功能。</span><span class="sxs-lookup"><span data-stu-id="dea7f-109">Interpreting involves reading the UI element names, roles, values, and so on, and interacting with the UI involves moving the focus from one element to another and invoking functionality.</span></span>
* <span data-ttu-id="dea7f-110">键盘辅助功能-许多辅助功能用户依靠键盘导航和操作 UI，方法如下：</span><span class="sxs-lookup"><span data-stu-id="dea7f-110">Keyboard accessibility—Many accessibility users rely on the keyboard to navigate and operate the UI by:</span></span>
  * <span data-ttu-id="dea7f-111">使用 Tab 键在各元素间移动焦点。</span><span class="sxs-lookup"><span data-stu-id="dea7f-111">Moving focus among elements by using the Tab key.</span></span>
  * <span data-ttu-id="dea7f-112">使用箭头键在列表、网格、树状视图等容器元素间导航。</span><span class="sxs-lookup"><span data-stu-id="dea7f-112">Navigating in container elements such as lists, grids, and tree views by using the arrow keys.</span></span>
  * <span data-ttu-id="dea7f-113">使用 Enter 或空格键激活功能（调用操作）。</span><span class="sxs-lookup"><span data-stu-id="dea7f-113">Activating functionality (invoking actions) by using the Enter or Space key.</span></span>
  * <span data-ttu-id="dea7f-114">使用快捷键高效访问其他应用功能。</span><span class="sxs-lookup"><span data-stu-id="dea7f-114">Using shortcut keys to efficiently access other app functionality.</span></span>
* <span data-ttu-id="dea7f-115">易于访问的视觉体验：视觉障碍用户需要足够的文本内容的文本对比度，以及高对比度主题的良好视觉体验。</span><span class="sxs-lookup"><span data-stu-id="dea7f-115">Accessible visual experience—Users who are visually impaired need a sufficient text contrast ratio for text content, and a good visual experience with high contrast themes overall.</span></span> <span data-ttu-id="dea7f-116">对于色盲用户，需要通过色彩以外的途径传递信息。</span><span class="sxs-lookup"><span data-stu-id="dea7f-116">Users who are color blind need information to be conveyed in ways other than through color.</span></span>

<span data-ttu-id="dea7f-117">通过良好的编码做法，可解决 web 上的许多常见辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="dea7f-117">Many common accessibility issues on the web can be solved through good coding practice.</span></span>  <span data-ttu-id="dea7f-118">[ (WCAG) 2.0 文档的 Web 内容辅助功能指南](https://www.w3.org/TR/WCAG20/)提供了帮助设计更易于访问的动态 Web 应用程序的技术和最佳做法。</span><span class="sxs-lookup"><span data-stu-id="dea7f-118">The [Web Content Accessibility Guidelines (WCAG) 2.0](https://www.w3.org/TR/WCAG20/) documentation provides techniques and best practices to help you design more accessible dynamic web applications.</span></span> <span data-ttu-id="dea7f-119">有关构建易于访问的网站的详细信息，请参阅 [构建易于访问的网站](./build.md) 。</span><span class="sxs-lookup"><span data-stu-id="dea7f-119">See [Building Accessible Websites](./build.md) for more information on building accessible websites.</span></span>

## <span data-ttu-id="dea7f-120">资源</span><span class="sxs-lookup"><span data-stu-id="dea7f-120">Resources</span></span>

#### [<span data-ttu-id="dea7f-121">设计以实现包含</span><span class="sxs-lookup"><span data-stu-id="dea7f-121">Designing for Inclusion</span></span>](https://w3.org/WAI/users/Overview.html)
<span data-ttu-id="dea7f-122">通过 W3C's Web 辅助功能计划进行设计可提供资源以帮助你更好地了解残障用户以及如何在你的网站中设计你的网站。</span><span class="sxs-lookup"><span data-stu-id="dea7f-122">Designing for Inclusion by the W3C's Web Accessibility Initiative provides resources to help you better understand users with disabilities and how to design your website with them in mind.</span></span>

#### [<span data-ttu-id="dea7f-123">设计非独占软件</span><span class="sxs-lookup"><span data-stu-id="dea7f-123">Designing inclusive software</span></span>](https://msdn.microsoft.com/windows/uwp/accessibility/designing-inclusive-software)
<span data-ttu-id="dea7f-124">设计非独占软件讨论适用于通用 Windows 平台 (UWP) 的 Microsoft 设计原则和做法。</span><span class="sxs-lookup"><span data-stu-id="dea7f-124">Designing inclusive software discusses Microsoft design principles and practices for the Universal Windows Platform (UWP).</span></span>

#### [<span data-ttu-id="dea7f-125">残疾人士如何使用 Web</span><span class="sxs-lookup"><span data-stu-id="dea7f-125">How People with Disabilities Use the Web</span></span>](https://www.w3.org/WAI/intro/people-use-web/Overview.html)
<span data-ttu-id="dea7f-126">W3C 介绍了如何使用残疾，包括有年龄相关障碍的人士，使用 Web。</span><span class="sxs-lookup"><span data-stu-id="dea7f-126">This resource by the W3C introduces how people with disabilities, including people with age-related impairments, use the Web.</span></span>

#### [<span data-ttu-id="dea7f-127">非独占设计工具包</span><span class="sxs-lookup"><span data-stu-id="dea7f-127">Inclusive Design Toolkit</span></span>](https://www.microsoft.com/design/practice#howwemake-section)
<span data-ttu-id="dea7f-128">Microsoft 开发了一个非独占设计工具包，以展示人类分集如何创建更好的设计限制以及如何将看似的小规模解决方案连接到更广泛的市场。</span><span class="sxs-lookup"><span data-stu-id="dea7f-128">Microsoft developed the Inclusive Design Toolkit to show how human diversity can create better design constraints and how to connect seemingly niche solutions to broader markets.</span></span>
