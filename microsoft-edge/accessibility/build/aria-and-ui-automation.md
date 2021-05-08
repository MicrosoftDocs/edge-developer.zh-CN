---
ms.assetid: ffd1bc60-2ef1-4f11-8156-b63544cede77
description: 了解如何Microsoft Edge ARIA 信息，然后向随后可以使用 Microsoft UI 自动化 API 的辅助技术公开该信息。
title: 辅助功能 - ARIA 和 UI 自动化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 辅助功能， 开发人员辅助功能， 可访问的网站， 边缘， Web 开发， ARIA， 开发人员， UIA， UI 自动化
ms.custom: seodec18
ms.openlocfilehash: 2fcc8160c830b5a62d8023a5cb7cc9df376c49ca
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562608"
---
# <span data-ttu-id="0e825-104">ARIA 和 UI 自动化Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0e825-104">ARIA and UI Automation in Microsoft Edge</span></span>

<span data-ttu-id="0e825-105">W3C 将可访问的富 Internet 应用程序 (ARIA) ARIA 定义为使动态 Web 内容和自定义 UI 可供访问的语法。</span><span class="sxs-lookup"><span data-stu-id="0e825-105">The W3C defines Accessible Rich Internet Applications (ARIA) as a syntax for making dynamic web content and custom UI accessible.</span></span> <span data-ttu-id="0e825-106">Microsoft Edge识别 ARIA 角色、状态和属性信息，并公开给辅助技术，辅助技术又可以使用[Microsoft UI 自动化](https://blogs.msdn.microsoft.com/winuiautomation/)API 检索信息。</span><span class="sxs-lookup"><span data-stu-id="0e825-106">Microsoft Edge recognizes the ARIA role, state, and property information and exposes it to assistive technologies, which in turn can use the [Microsoft UI Automation](https://blogs.msdn.microsoft.com/winuiautomation/) APIs to retrieve the information.</span></span>

<span data-ttu-id="0e825-107">访问[HTML5Accessibility，](https://html5accessibility.com)了解哪些新 HTML5 功能可供 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="0e825-107">Visit [HTML5Accessibility](https://html5accessibility.com) for information on which new HTML5 features are accessibly supported by Microsoft Edge.</span></span>

<span data-ttu-id="0e825-108">EdgeHTML Microsoft Edge呈现引擎 (构建) 网页的可访问投影，符合以下 W3C 规范：</span><span class="sxs-lookup"><span data-stu-id="0e825-108">The Microsoft Edge rendering engine (EdgeHTML) builds an accessible projection of web pages, conforming to the following W3C specifications:</span></span>

1. <span data-ttu-id="0e825-109">[HTML 辅助功能 API 映射](https://w3.org/TR/html-aam-1.0/)规范定义 HTML 元素和属性如何映射到 ARIA 和 UI 自动化对象。</span><span class="sxs-lookup"><span data-stu-id="0e825-109">The [HTML Accessibility API Mappings](https://w3.org/TR/html-aam-1.0/) specification defines how HTML elements and attributes map to ARIA and UI Automation objects.</span></span>
   * <span data-ttu-id="0e825-110">[工作草稿](https://w3.org/TR/html-aam-1.0/) - 规范的稳定版本</span><span class="sxs-lookup"><span data-stu-id="0e825-110">[Working draft](https://w3.org/TR/html-aam-1.0/) - stable version of the specification</span></span>
   * <span data-ttu-id="0e825-111">[编辑器的草稿](https://w3c.github.io/html-aam/) - 正在进行中。</span><span class="sxs-lookup"><span data-stu-id="0e825-111">[Editor's draft](https://w3c.github.io/html-aam/) - work in progress.</span></span> <span data-ttu-id="0e825-112">请注意，尽管此规范具有最新更改，但这些更改可能尚未Microsoft Edge可用。</span><span class="sxs-lookup"><span data-stu-id="0e825-112">Note that while this spec has the latest changes, the changes may not be available in Microsoft Edge yet.</span></span>


2. <span data-ttu-id="0e825-113">核心 [辅助功能 API 映射](https://w3.org/TR/core-aam-1.1/) 规范定义了生成辅助功能树以及将 ARIA 元素和属性映射到 UI 自动化对象的一般原则。</span><span class="sxs-lookup"><span data-stu-id="0e825-113">The [Core Accessibility API Mappings](https://w3.org/TR/core-aam-1.1/) specification defines general principles for building the accessibility tree and mapping ARIA elements and attributes to UI Automation objects.</span></span>
   * <span data-ttu-id="0e825-114">[工作草稿](https://w3.org/TR/core-aam-1.1/) - 规范的稳定版本</span><span class="sxs-lookup"><span data-stu-id="0e825-114">[Working draft](https://w3.org/TR/core-aam-1.1/) - stable version of the specification</span></span>
   * <span data-ttu-id="0e825-115">[编辑器的草稿](https://w3c.github.io/core-aam/) - 正在进行中。</span><span class="sxs-lookup"><span data-stu-id="0e825-115">[Editor's draft](https://w3c.github.io/core-aam/) - work in progress.</span></span> <span data-ttu-id="0e825-116">请注意，尽管此规范具有最新更改，但这些更改可能尚未Microsoft Edge可用。</span><span class="sxs-lookup"><span data-stu-id="0e825-116">Note that while this spec has the latest changes, the changes may not be available in Microsoft Edge yet.</span></span>  

3. <span data-ttu-id="0e825-117">[辅助名称和](https://w3.org/TR/accname-aam-1.1/)说明：计算和 API 映射规范定义如何计算可访问对象的名称和说明（给定可用于辅助元素的 HTML 和 ARIA 元素和属性值）。</span><span class="sxs-lookup"><span data-stu-id="0e825-117">The [Accessible Name and Description: Computation and API Mappings](https://w3.org/TR/accname-aam-1.1/) specification defines how to compute the name and description of accessible objects given the HTML and the ARIA elements and attributes values available for the accessible elements.</span></span>
   * <span data-ttu-id="0e825-118">[工作草稿](https://w3.org/TR/accname-aam-1.1/) - 规范的稳定版本</span><span class="sxs-lookup"><span data-stu-id="0e825-118">[Working draft](https://w3.org/TR/accname-aam-1.1/) - stable version of the specification</span></span>  
   * <span data-ttu-id="0e825-119">[编辑器的草稿](https://w3c.github.io/accname/) - 正在进行中。</span><span class="sxs-lookup"><span data-stu-id="0e825-119">[Editor's draft](https://w3c.github.io/accname/) - work in progress.</span></span> <span data-ttu-id="0e825-120">请注意，尽管此规范具有最新更改，但这些更改可能尚未Microsoft Edge可用。</span><span class="sxs-lookup"><span data-stu-id="0e825-120">Note that while this spec has the latest changes, the changes may not be available in Microsoft Edge yet.</span></span>   

<span data-ttu-id="0e825-121">有关网站中的辅助功能体系结构Microsoft Edge，请参阅构建更易于访问的[Web](https://blogs.windows.com/msedgedev/2016/04/20/building-a-more-accessible-web-platform/)平台博客文章。</span><span class="sxs-lookup"><span data-stu-id="0e825-121">For more information about the accessibility architecture in Microsoft Edge, check out the [Building a more accessible web platform](https://blogs.windows.com/msedgedev/2016/04/20/building-a-more-accessible-web-platform/) blog post.</span></span>  <span data-ttu-id="0e825-122">有关新体系结构如何改善最终用户体验的示例，特别是标记如何定义使用屏幕阅读器等辅助技术进行导航的体验，请访问使用 HTML5 和 [UIA](https://blogs.windows.com/msedgedev/2016/05/12/accessible-ux-with-html5-and-uia/)构建更易于访问的用户体验。</span><span class="sxs-lookup"><span data-stu-id="0e825-122">For examples of how the new architecture improves the end user's experience, and specifically how markup defines the experience of navigating with assistive technologies like screen readers, visit [Building a more accessible user experience with HTML5 and UIA](https://blogs.windows.com/msedgedev/2016/05/12/accessible-ux-with-html5-and-uia/).</span></span>
