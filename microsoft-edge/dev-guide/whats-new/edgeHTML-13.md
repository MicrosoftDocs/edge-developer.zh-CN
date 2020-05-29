---
description: 此页面概述了 EdgeHTML 13 中的新增功能。
title: EdgeHTML 13 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 8fb9d6bd78af5d595e217fa2bf210632f4c1a61f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562615"
---
# <span data-ttu-id="d0937-104">EdgeHTML 13 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="d0937-104">What's New in EdgeHTML 13</span></span>
<span data-ttu-id="d0937-105">下面是在 Windows 10 的[第一个重大更新](https://blogs.windows.com/windowsexperience/2015/11/12/first-major-update-for-windows-10-available-today/)（11/2015，内部版本10586）中提供的 EdgeHTML 13 所附的更改。</span><span class="sxs-lookup"><span data-stu-id="d0937-105">Here are the changes shipped with EdgeHTML 13, the engine powering the Microsoft Edge browser in the [first major update](https://blogs.windows.com/windowsexperience/2015/11/12/first-major-update-for-windows-10-available-today/) for Windows 10 (11/2015, Build 10586).</span></span> <span data-ttu-id="d0937-106">有关 Microsoft edge 整体浏览器更改的概述，请参阅[介绍 Microsoft edge 第一个平台更新 EdgeHTML 13](https://blogs.windows.com/msedgedev/2015/11/16/introducing-edgehtml-13-our-first-platform-update-for-microsoft-edge/)。</span><span class="sxs-lookup"><span data-stu-id="d0937-106">For an overview of changes to the overall Microsoft Edge browser, see [Introducing EdgeHTML 13, our first platform update for Microsoft Edge](https://blogs.windows.com/msedgedev/2015/11/16/introducing-edgehtml-13-our-first-platform-update-for-microsoft-edge/).</span></span>

<span data-ttu-id="d0937-107">下面是以下更改列表的固定链接： [https://aka.ms/devguide_edgehtml_13](https://aka.ms/devguide_edgehtml_13) 。</span><span class="sxs-lookup"><span data-stu-id="d0937-107">Here's the permalink for the following list of changes: [https://aka.ms/devguide_edgehtml_13](https://aka.ms/devguide_edgehtml_13).</span></span>

## <span data-ttu-id="d0937-108">功能</span><span class="sxs-lookup"><span data-stu-id="d0937-108">Features</span></span>

### <span data-ttu-id="d0937-109">CSS</span><span class="sxs-lookup"><span data-stu-id="d0937-109">CSS</span></span>
<span data-ttu-id="d0937-110">' ' EdgeHTML 13 支持新的 CSS 功能，包括：</span><span class="sxs-lookup"><span data-stu-id="d0937-110">'' EdgeHTML 13 supports new CSS features, including:</span></span>
* [<span data-ttu-id="d0937-111">CSS Mutability 伪类</span><span class="sxs-lookup"><span data-stu-id="d0937-111">CSS Mutability Pseudo-classes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/cssmutabilitypseudoclasses/)
* [<span data-ttu-id="d0937-112">CSS 范围伪类</span><span class="sxs-lookup"><span data-stu-id="d0937-112">CSS Range Pseudo-classes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/cssrangepseudoclasses/)
* <span data-ttu-id="d0937-113">CSS[初始](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue/)和未[设置](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue/)关键字</span><span class="sxs-lookup"><span data-stu-id="d0937-113">CSS [initial](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue/) and [unset](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue/) keywords</span></span>

### <span data-ttu-id="d0937-114">加密媒体扩展</span><span class="sxs-lookup"><span data-stu-id="d0937-114">Encrypted Media Extensions</span></span>
<span data-ttu-id="d0937-115">Microsoft Edge 现在支持新的 unprefixed[加密媒体扩展](https://w3.org/TR/encrypted-media/)api。</span><span class="sxs-lookup"><span data-stu-id="d0937-115">Microsoft Edge now supports the new unprefixed [Encrypted Media Extensions](https://w3.org/TR/encrypted-media/) APIs.</span></span> <span data-ttu-id="d0937-116">加密媒体扩展（EME）将视频和音频元素扩展为启用数字版权管理（DRM）受保护的内容，而不使用插件。阅读有关 EME：[加密媒体扩展](https://docs.microsoft.com/microsoft-edge/dev-guide/multimedia/encrypted-media-extensions)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d0937-116">Encrypted Media Extensions (EME) extends the video and audio elements to enable Digital Rights Management (DRM) protected content without using plug-ins. Read more about EME: [Encrypted Media Extensions](https://docs.microsoft.com/microsoft-edge/dev-guide/multimedia/encrypted-media-extensions).</span></span>

### <span data-ttu-id="d0937-117">显卡</span><span class="sxs-lookup"><span data-stu-id="d0937-117">Graphics</span></span>

<span data-ttu-id="d0937-118">EdgeHTML 13 引入了以下图形更新：</span><span class="sxs-lookup"><span data-stu-id="d0937-118">EdgeHTML 13 introduces the following graphics updates:</span></span>
* [<span data-ttu-id="d0937-119">画布椭圆</span><span class="sxs-lookup"><span data-stu-id="d0937-119">Canvas ellipse</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/canvas2dellipse/)
* [<span data-ttu-id="d0937-120">画布混合模式</span><span class="sxs-lookup"><span data-stu-id="d0937-120">Canvas blending modes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/compositingandblendingincanvas2d/)
* [`<picture>` <span data-ttu-id="d0937-121">元素</span><span class="sxs-lookup"><span data-stu-id="d0937-121">element</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/pictureelement/)
* [<span data-ttu-id="d0937-122">SVG 外部内容</span><span class="sxs-lookup"><span data-stu-id="d0937-122">SVG external content</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/svgexternalcontent/)

### <span data-ttu-id="d0937-123">JavaScript</span><span class="sxs-lookup"><span data-stu-id="d0937-123">JavaScript</span></span>
<span data-ttu-id="d0937-124">EdgeHTML 13[在 Chakra 中包含重大改进和新增功能支持](https://blogs.windows.com/msedgedev/2015/09/30/asynchronous-code-gets-easier-with-es2016-async-function-support-in-chakra-and-microsoft-edge/)，JavaScript 引擎支持 Microsoft Edge，包括：</span><span class="sxs-lookup"><span data-stu-id="d0937-124">EdgeHTML 13 includes [major improvements and new feature support in Chakra](https://blogs.windows.com/msedgedev/2015/09/30/asynchronous-code-gets-easier-with-es2016-async-function-support-in-chakra-and-microsoft-edge/), the JavaScript engine powering Microsoft Edge, including:</span></span>

#### <span data-ttu-id="d0937-125">新增功能（默认情况下处于打开状态）</span><span class="sxs-lookup"><span data-stu-id="d0937-125">New features (on by default)</span></span>

* <span data-ttu-id="d0937-126">默认情况下启用[.asm](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) （[博客文章](https://blogs.windows.com/msedgedev/2015/11/10/supercharging-javascript-performance-with-asm-js/)、[演示](https://dev.windows.com/microsoft-edge/testdrive/demos/chess/)）</span><span class="sxs-lookup"><span data-stu-id="d0937-126">[asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) enabled by default ([blog post](https://blogs.windows.com/msedgedev/2015/11/10/supercharging-javascript-performance-with-asm-js/), [demo](https://dev.windows.com/microsoft-edge/testdrive/demos/chess/))</span></span>
* <span data-ttu-id="d0937-127">[类](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes)（ES2015）</span><span class="sxs-lookup"><span data-stu-id="d0937-127">[Classes](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) (ES2015)</span></span>

#### <span data-ttu-id="d0937-128">实验性 JavaScript 功能（已启用，带有*关于：标志*）</span><span class="sxs-lookup"><span data-stu-id="d0937-128">Experimental JavaScript features (enabled with *about:flags*)</span></span>

* <span data-ttu-id="d0937-129">[Async 函数](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions)（ES2016）</span><span class="sxs-lookup"><span data-stu-id="d0937-129">[Async functions](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) (ES2016)</span></span>
* <span data-ttu-id="d0937-130">[求幂运算符](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator)（ES2016）</span><span class="sxs-lookup"><span data-stu-id="d0937-130">[Exponentiation operator](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) (ES2016)</span></span>
* <span data-ttu-id="d0937-131">[Destructuring](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) （ES2015）</span><span class="sxs-lookup"><span data-stu-id="d0937-131">[Destructuring](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) (ES2015)</span></span>

### <span data-ttu-id="d0937-132">用户输入</span><span class="sxs-lookup"><span data-stu-id="d0937-132">User Input</span></span>
<span data-ttu-id="d0937-133">EdgeHTML 13 中引入的以下功能改进了用户输入：</span><span class="sxs-lookup"><span data-stu-id="d0937-133">The following features introduced in EdgeHTML 13 improve user input:</span></span>
* [`<meter>` <span data-ttu-id="d0937-134">元素</span><span class="sxs-lookup"><span data-stu-id="d0937-134">element</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/meterelement/)
* [`oninvalid` <span data-ttu-id="d0937-135">元素文档和窗口的事件处理程序</span><span class="sxs-lookup"><span data-stu-id="d0937-135">event handler for the element document and window</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/oninvalideventhandler/)

### <span data-ttu-id="d0937-136">指针锁</span><span class="sxs-lookup"><span data-stu-id="d0937-136">Pointer Lock</span></span>
<span data-ttu-id="d0937-137">Microsoft Edge 现在支持指针锁定 API （以前称为鼠标锁定）以访问原始鼠标移动，将鼠标事件的目标锁定到单个元素，消除了鼠标移动距离一个方向的限制，以及从视图中删除光标。</span><span class="sxs-lookup"><span data-stu-id="d0937-137">Microsoft Edge now supports the Pointer Lock API (previously called Mouse Lock) for access to raw mouse movement, locking the target of mouse events to a single element, eliminating limits of how far mouse movement can go in a single direction, and removing the cursor from view.</span></span> 


## <span data-ttu-id="d0937-138">EdgeHTML 13 "" "中的新 Api</span><span class="sxs-lookup"><span data-stu-id="d0937-138">New APIs in EdgeHTML 13""""</span></span>

<span data-ttu-id="d0937-139">下面是 EdgeHTML 13 中新 Api 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="d0937-139">Here's the full list of new APIs in EdgeHTML 13.</span></span> <span data-ttu-id="d0937-140">它们以 **[界面名称] 的格式列出。 [api 名称]**。</span><span class="sxs-lookup"><span data-stu-id="d0937-140">They are listed in the format of **[interface name].[api name]**.</span></span>
<iframe height='584' scrolling='no' title='<span data-ttu-id="d0937-141">EdgeHTML 13 中的新 Api</span><span class="sxs-lookup"><span data-stu-id="d0937-141">New APIs in EdgeHTML 13</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/vmzxEY/?height=584&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="d0937-142">在 <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'> </a> CodePen 上的 Microsoft Edge 文档（@MicrosoftEdgeDocumentation）中查看 EdgeHTML 13 中的笔新 api <a href='http://codepen.io/MicrosoftEdgeDocumentation'> </a> <a href='http://codepen.io'> </a> 。</span><span class="sxs-lookup"><span data-stu-id="d0937-142">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'>New APIs in EdgeHTML 13</a> by Microsoft Edge Docs (<a href='http://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span></iframe><span data-ttu-id="d0937-143">""''""''""</span><span class="sxs-lookup"><span data-stu-id="d0937-143">""''""''""</span></span>
