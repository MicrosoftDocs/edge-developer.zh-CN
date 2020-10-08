---
ms.assetid: ffd1bc60-2ef1-4f11-8156-b63544cede77
description: 了解 Microsoft Edge 如何识别 ARIA 信息，然后将其公开给可使用 Microsoft UI 自动化 Api 的辅助技术。
title: 辅助功能-ARIA 和 UI 自动化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 辅助功能，面向开发人员的辅助功能，辅助网站，边缘，web 开发，ARIA，开发人员，UIA，UI 自动化
ms.custom: seodec18
ms.openlocfilehash: 2fcc8160c830b5a62d8023a5cb7cc9df376c49ca
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562608"
---
# <span data-ttu-id="6f090-104">Microsoft Edge 中的 ARIA 和 UI 自动化</span><span class="sxs-lookup"><span data-stu-id="6f090-104">ARIA and UI Automation in Microsoft Edge</span></span>

<span data-ttu-id="6f090-105">W3C 定义易于访问的富 Internet 应用程序 (ARIA) 用作使动态 web 内容和自定义 UI 易于访问的语法。</span><span class="sxs-lookup"><span data-stu-id="6f090-105">The W3C defines Accessible Rich Internet Applications (ARIA) as a syntax for making dynamic web content and custom UI accessible.</span></span> <span data-ttu-id="6f090-106">Microsoft Edge 识别 ARIA 角色、状态和属性信息，并将其公开给辅助技术，这些辅助技术又可以使用 [MICROSOFT UI 自动化](https://blogs.msdn.microsoft.com/winuiautomation/) api 检索信息。</span><span class="sxs-lookup"><span data-stu-id="6f090-106">Microsoft Edge recognizes the ARIA role, state, and property information and exposes it to assistive technologies, which in turn can use the [Microsoft UI Automation](https://blogs.msdn.microsoft.com/winuiautomation/) APIs to retrieve the information.</span></span>

<span data-ttu-id="6f090-107">有关 Microsoft Edge 支持的新 HTML5 功能 accessibly 的信息，请访问 [HTML5Accessibility](https://html5accessibility.com) 。</span><span class="sxs-lookup"><span data-stu-id="6f090-107">Visit [HTML5Accessibility](https://html5accessibility.com) for information on which new HTML5 features are accessibly supported by Microsoft Edge.</span></span>

<span data-ttu-id="6f090-108">Microsoft Edge 呈现引擎 (EdgeHTML) 构建网页的易于访问的投影，符合以下 W3C 规范：</span><span class="sxs-lookup"><span data-stu-id="6f090-108">The Microsoft Edge rendering engine (EdgeHTML) builds an accessible projection of web pages, conforming to the following W3C specifications:</span></span>

1. <span data-ttu-id="6f090-109">[Html 辅助功能 API 映射](https://w3.org/TR/html-aam-1.0/)规范定义了 html 元素和属性映射到 ARIA 和 UI 自动化对象的方式。</span><span class="sxs-lookup"><span data-stu-id="6f090-109">The [HTML Accessibility API Mappings](https://w3.org/TR/html-aam-1.0/) specification defines how HTML elements and attributes map to ARIA and UI Automation objects.</span></span>
   * <span data-ttu-id="6f090-110">[工作草稿](https://w3.org/TR/html-aam-1.0/) -规范版本的稳定版本</span><span class="sxs-lookup"><span data-stu-id="6f090-110">[Working draft](https://w3.org/TR/html-aam-1.0/) - stable version of the specification</span></span>
   * <span data-ttu-id="6f090-111">[编辑者草稿](https://w3c.github.io/html-aam/) -正在进行中工作。</span><span class="sxs-lookup"><span data-stu-id="6f090-111">[Editor's draft](https://w3c.github.io/html-aam/) - work in progress.</span></span> <span data-ttu-id="6f090-112">请注意，虽然此规范具有最新更改，但这些更改可能不会在 Microsoft Edge 中使用。</span><span class="sxs-lookup"><span data-stu-id="6f090-112">Note that while this spec has the latest changes, the changes may not be available in Microsoft Edge yet.</span></span>


2. <span data-ttu-id="6f090-113">[核心辅助功能 API 映射](https://w3.org/TR/core-aam-1.1/)规范定义了构建辅助功能树以及将 ARIA 元素和属性映射到 UI 自动化对象的一般原则。</span><span class="sxs-lookup"><span data-stu-id="6f090-113">The [Core Accessibility API Mappings](https://w3.org/TR/core-aam-1.1/) specification defines general principles for building the accessibility tree and mapping ARIA elements and attributes to UI Automation objects.</span></span>
   * <span data-ttu-id="6f090-114">[工作草稿](https://w3.org/TR/core-aam-1.1/) -规范版本的稳定版本</span><span class="sxs-lookup"><span data-stu-id="6f090-114">[Working draft](https://w3.org/TR/core-aam-1.1/) - stable version of the specification</span></span>
   * <span data-ttu-id="6f090-115">[编辑者草稿](https://w3c.github.io/core-aam/) -正在进行中工作。</span><span class="sxs-lookup"><span data-stu-id="6f090-115">[Editor's draft](https://w3c.github.io/core-aam/) - work in progress.</span></span> <span data-ttu-id="6f090-116">请注意，虽然此规范具有最新更改，但这些更改可能不会在 Microsoft Edge 中使用。</span><span class="sxs-lookup"><span data-stu-id="6f090-116">Note that while this spec has the latest changes, the changes may not be available in Microsoft Edge yet.</span></span>  

3. <span data-ttu-id="6f090-117">[辅助名称和说明：计算和 API 映射](https://w3.org/TR/accname-aam-1.1/)规范定义如何在给定 HTML 和可用于辅助元素的 ARIA 元素和属性值的情况中计算辅助对象的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="6f090-117">The [Accessible Name and Description: Computation and API Mappings](https://w3.org/TR/accname-aam-1.1/) specification defines how to compute the name and description of accessible objects given the HTML and the ARIA elements and attributes values available for the accessible elements.</span></span>
   * <span data-ttu-id="6f090-118">[工作草稿](https://w3.org/TR/accname-aam-1.1/) -规范版本的稳定版本</span><span class="sxs-lookup"><span data-stu-id="6f090-118">[Working draft](https://w3.org/TR/accname-aam-1.1/) - stable version of the specification</span></span>  
   * <span data-ttu-id="6f090-119">[编辑者草稿](https://w3c.github.io/accname/) -正在进行中工作。</span><span class="sxs-lookup"><span data-stu-id="6f090-119">[Editor's draft](https://w3c.github.io/accname/) - work in progress.</span></span> <span data-ttu-id="6f090-120">请注意，虽然此规范具有最新更改，但这些更改可能不会在 Microsoft Edge 中使用。</span><span class="sxs-lookup"><span data-stu-id="6f090-120">Note that while this spec has the latest changes, the changes may not be available in Microsoft Edge yet.</span></span>   

<span data-ttu-id="6f090-121">有关 Microsoft Edge 中的辅助功能体系结构的详细信息，请参阅 [构建更易于访问的 web 平台](https://blogs.windows.com/msedgedev/2016/04/20/building-a-more-accessible-web-platform/) 博客文章。</span><span class="sxs-lookup"><span data-stu-id="6f090-121">For more information about the accessibility architecture in Microsoft Edge, check out the [Building a more accessible web platform](https://blogs.windows.com/msedgedev/2016/04/20/building-a-more-accessible-web-platform/) blog post.</span></span>  <span data-ttu-id="6f090-122">有关新体系结构如何改善最终用户体验的示例，以及特定如何标记定义使用辅助技术（如屏幕阅读器）导航的体验，请参阅 [使用 HTML5 和 UIA 构建更易于访问的用户体验](https://blogs.windows.com/msedgedev/2016/05/12/accessible-ux-with-html5-and-uia/)。</span><span class="sxs-lookup"><span data-stu-id="6f090-122">For examples of how the new architecture improves the end user's experience, and specifically how markup defines the experience of navigating with assistive technologies like screen readers, visit [Building a more accessible user experience with HTML5 and UIA](https://blogs.windows.com/msedgedev/2016/05/12/accessible-ux-with-html5-and-uia/).</span></span>
