---
description: This page provides an overview of what's new in EdgeHTML 13.
title: New features and APIs in EdgeHTML 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, css, javascript, developer
ms.openlocfilehash: 033b8dacb107492624f3b8c7775a47285c9893dd
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941913"
---
# <span data-ttu-id="352f8-104">What's new in EdgeHTML 13</span><span class="sxs-lookup"><span data-stu-id="352f8-104">What's new in EdgeHTML 13</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="352f8-105">Here are the changes shipped with EdgeHTML 13, the engine powering the Microsoft Edge browser in the [first major update](https://blogs.windows.com/windowsexperience/2015/11/12) for Windows 10 \(11/2015, Build 10586\).</span><span class="sxs-lookup"><span data-stu-id="352f8-105">Here are the changes shipped with EdgeHTML 13, the engine powering the Microsoft Edge browser in the [first major update](https://blogs.windows.com/windowsexperience/2015/11/12) for Windows 10 \(11/2015, Build 10586\).</span></span>  <span data-ttu-id="352f8-106">For an overview of changes to the overall Microsoft Edge browser, see [Introducing EdgeHTML 13, our first platform update for Microsoft Edge](https://blogs.windows.com/msedgedev/2015/11/16).</span><span class="sxs-lookup"><span data-stu-id="352f8-106">For an overview of changes to the overall Microsoft Edge browser, see [Introducing EdgeHTML 13, our first platform update for Microsoft Edge](https://blogs.windows.com/msedgedev/2015/11/16).</span></span>  

<span data-ttu-id="352f8-107">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_13](./edgehtml-13.md).</span><span class="sxs-lookup"><span data-stu-id="352f8-107">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_13](./edgehtml-13.md).</span></span>  

## <span data-ttu-id="352f8-108">Features</span><span class="sxs-lookup"><span data-stu-id="352f8-108">Features</span></span>  

### <span data-ttu-id="352f8-109">CSS</span><span class="sxs-lookup"><span data-stu-id="352f8-109">CSS</span></span>  

<span data-ttu-id="352f8-110">EdgeHTML 13 supports new CSS features, including:</span><span class="sxs-lookup"><span data-stu-id="352f8-110">EdgeHTML 13 supports new CSS features, including:</span></span>  

*   [<span data-ttu-id="352f8-111">CSS Mutability Pseudo-classes</span><span class="sxs-lookup"><span data-stu-id="352f8-111">CSS Mutability Pseudo-classes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/cssmutabilitypseudoclasses)  
*   [<span data-ttu-id="352f8-112">CSS Range Pseudo-classes</span><span class="sxs-lookup"><span data-stu-id="352f8-112">CSS Range Pseudo-classes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/cssrangepseudoclasses)  
*   <span data-ttu-id="352f8-113">CSS [initial](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue) and [unset](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue) keywords</span><span class="sxs-lookup"><span data-stu-id="352f8-113">CSS [initial](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue) and [unset](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue) keywords</span></span>  

### <span data-ttu-id="352f8-114">Encrypted Media Extensions</span><span class="sxs-lookup"><span data-stu-id="352f8-114">Encrypted Media Extensions</span></span>  

<span data-ttu-id="352f8-115">Microsoft Edge now supports the new unprefixed [Encrypted Media Extensions](https://w3.org/TR/encrypted-media) APIs.</span><span class="sxs-lookup"><span data-stu-id="352f8-115">Microsoft Edge now supports the new unprefixed [Encrypted Media Extensions](https://w3.org/TR/encrypted-media) APIs.</span></span>  <span data-ttu-id="352f8-116">Encrypted Media Extensions \(EME\) extends the video and audio elements to enable Digital Rights Management \(DRM\) protected content without using plug-ins.  Read more about EME:  [Encrypted Media Extensions](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API).</span><span class="sxs-lookup"><span data-stu-id="352f8-116">Encrypted Media Extensions \(EME\) extends the video and audio elements to enable Digital Rights Management \(DRM\) protected content without using plug-ins.  Read more about EME:  [Encrypted Media Extensions](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API).</span></span>  

### <span data-ttu-id="352f8-117">Graphics</span><span class="sxs-lookup"><span data-stu-id="352f8-117">Graphics</span></span>  

<span data-ttu-id="352f8-118">EdgeHTML 13 introduces the following graphics updates:</span><span class="sxs-lookup"><span data-stu-id="352f8-118">EdgeHTML 13 introduces the following graphics updates:</span></span>  

*   [<span data-ttu-id="352f8-119">Canvas ellipse</span><span class="sxs-lookup"><span data-stu-id="352f8-119">Canvas ellipse</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/canvas2dellipse)  
*   [<span data-ttu-id="352f8-120">Canvas blending modes</span><span class="sxs-lookup"><span data-stu-id="352f8-120">Canvas blending modes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/compositingandblendingincanvas2d)  
*   [<picture> <span data-ttu-id="352f8-121">element</span><span class="sxs-lookup"><span data-stu-id="352f8-121">element</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/pictureelement)  
*   [<span data-ttu-id="352f8-122">SVG external content</span><span class="sxs-lookup"><span data-stu-id="352f8-122">SVG external content</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/svgexternalcontent)  

### <span data-ttu-id="352f8-123">JavaScript</span><span class="sxs-lookup"><span data-stu-id="352f8-123">JavaScript</span></span>  

<span data-ttu-id="352f8-124">EdgeHTML 13 includes [major improvements and new feature support in Chakra](https://blogs.windows.com/msedgedev/2015/09/30), the JavaScript engine powering Microsoft Edge, including:</span><span class="sxs-lookup"><span data-stu-id="352f8-124">EdgeHTML 13 includes [major improvements and new feature support in Chakra](https://blogs.windows.com/msedgedev/2015/09/30), the JavaScript engine powering Microsoft Edge, including:</span></span>  

#### <span data-ttu-id="352f8-125">New features</span><span class="sxs-lookup"><span data-stu-id="352f8-125">New features</span></span>  

<span data-ttu-id="352f8-126">On by default</span><span class="sxs-lookup"><span data-stu-id="352f8-126">On by default</span></span>  

*   <span data-ttu-id="352f8-127">[asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) enabled by default \([blog post](https://blogs.windows.com/msedgedev/2015/11/10), [demo](https://dev.windows.com/microsoft-edge/testdrive/demos/chess)\)</span><span class="sxs-lookup"><span data-stu-id="352f8-127">[asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) enabled by default \([blog post](https://blogs.windows.com/msedgedev/2015/11/10), [demo](https://dev.windows.com/microsoft-edge/testdrive/demos/chess)\)</span></span>  
*   <span data-ttu-id="352f8-128">[Classes](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) \(ES2015\)</span><span class="sxs-lookup"><span data-stu-id="352f8-128">[Classes](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) \(ES2015\)</span></span>  

#### <span data-ttu-id="352f8-129">Experimental JavaScript features</span><span class="sxs-lookup"><span data-stu-id="352f8-129">Experimental JavaScript features</span></span>  

<span data-ttu-id="352f8-130">Enabled with</span><span class="sxs-lookup"><span data-stu-id="352f8-130">Enabled with</span></span> `about:flags`  

*   <span data-ttu-id="352f8-131">[Async functions](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) \(ES2016\)</span><span class="sxs-lookup"><span data-stu-id="352f8-131">[Async functions](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) \(ES2016\)</span></span>  
*   <span data-ttu-id="352f8-132">[Exponentiation operator](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) \(ES2016\)</span><span class="sxs-lookup"><span data-stu-id="352f8-132">[Exponentiation operator](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) \(ES2016\)</span></span>  
*   <span data-ttu-id="352f8-133">[Destructuring](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) \(ES2015\)</span><span class="sxs-lookup"><span data-stu-id="352f8-133">[Destructuring](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) \(ES2015\)</span></span>  

### <span data-ttu-id="352f8-134">User Input</span><span class="sxs-lookup"><span data-stu-id="352f8-134">User Input</span></span>  

<span data-ttu-id="352f8-135">The following features introduced in EdgeHTML 13 improve user input:</span><span class="sxs-lookup"><span data-stu-id="352f8-135">The following features introduced in EdgeHTML 13 improve user input:</span></span>  

*   [<meter> <span data-ttu-id="352f8-136">element</span><span class="sxs-lookup"><span data-stu-id="352f8-136">element</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/meterelement)  
*   [<span data-ttu-id="352f8-137">oninvalid event handler for the element document and window</span><span class="sxs-lookup"><span data-stu-id="352f8-137">oninvalid event handler for the element document and window</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/oninvalideventhandler)  

### <span data-ttu-id="352f8-138">Pointer Lock</span><span class="sxs-lookup"><span data-stu-id="352f8-138">Pointer Lock</span></span>  

<span data-ttu-id="352f8-139">Microsoft Edge now supports the Pointer Lock API \(previously called Mouse Lock\) for access to raw mouse movement, locking the target of mouse events to a single element, eliminating limits of how far mouse movement can go in a single direction, and removing the cursor from view.</span><span class="sxs-lookup"><span data-stu-id="352f8-139">Microsoft Edge now supports the Pointer Lock API \(previously called Mouse Lock\) for access to raw mouse movement, locking the target of mouse events to a single element, eliminating limits of how far mouse movement can go in a single direction, and removing the cursor from view.</span></span>  

## <span data-ttu-id="352f8-140">New APIs in EdgeHTML 13</span><span class="sxs-lookup"><span data-stu-id="352f8-140">New APIs in EdgeHTML 13</span></span>  

<span data-ttu-id="352f8-141">Here's the full list of new APIs in EdgeHTML 13.</span><span class="sxs-lookup"><span data-stu-id="352f8-141">Here's the full list of new APIs in EdgeHTML 13.</span></span>  <span data-ttu-id="352f8-142">They are listed in the format of `[interface name].[api name]`.</span><span class="sxs-lookup"><span data-stu-id="352f8-142">They are listed in the format of `[interface name].[api name]`.</span></span>  

<iframe height='584' scrolling='no' title='<span data-ttu-id="352f8-143">New APIs in EdgeHTML 13</span><span class="sxs-lookup"><span data-stu-id="352f8-143">New APIs in EdgeHTML 13</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/vmzxEY/?height=584&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width:  100%;'><span data-ttu-id="352f8-144">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'>New APIs in EdgeHTML 13</a> by Microsoft Edge Docs (<a href='http://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='http://codepen.io'>CodePen</a>.</span><span class="sxs-lookup"><span data-stu-id="352f8-144">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'>New APIs in EdgeHTML 13</a> by Microsoft Edge Docs (<a href='http://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span></iframe>  
