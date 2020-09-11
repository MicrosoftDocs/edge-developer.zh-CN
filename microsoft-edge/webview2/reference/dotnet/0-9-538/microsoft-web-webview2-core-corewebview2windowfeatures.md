---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2。 CoreWebView2WindowFeatures
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 59e051c0537357fed89d6300db69ea479b656c7e
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010511"
---
# <span data-ttu-id="54c9e-104">0.9.579-WebView2 的 CoreWebView2WindowFeatures 类</span><span class="sxs-lookup"><span data-stu-id="54c9e-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2WindowFeatures class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="54c9e-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="54c9e-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="54c9e-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="54c9e-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="54c9e-107">Web 视图弹出窗口的窗口功能。</span><span class="sxs-lookup"><span data-stu-id="54c9e-107">Window features for a WebView popup window.</span></span>

## <span data-ttu-id="54c9e-108">摘要</span><span class="sxs-lookup"><span data-stu-id="54c9e-108">Summary</span></span>

 <span data-ttu-id="54c9e-109">成员</span><span class="sxs-lookup"><span data-stu-id="54c9e-109">Members</span></span>                        | <span data-ttu-id="54c9e-110">描述</span><span class="sxs-lookup"><span data-stu-id="54c9e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="54c9e-111">高度</span><span class="sxs-lookup"><span data-stu-id="54c9e-111">Height</span></span>](#height) | <span data-ttu-id="54c9e-112">窗口的高度。</span><span class="sxs-lookup"><span data-stu-id="54c9e-112">The height of the window.</span></span>
[<span data-ttu-id="54c9e-113">向左</span><span class="sxs-lookup"><span data-stu-id="54c9e-113">Left</span></span>](#left) | <span data-ttu-id="54c9e-114">窗口的左侧位置。</span><span class="sxs-lookup"><span data-stu-id="54c9e-114">The left position of the window.</span></span>
[<span data-ttu-id="54c9e-115">菜单栏</span><span class="sxs-lookup"><span data-stu-id="54c9e-115">MenuBar</span></span>](#menubar) | <span data-ttu-id="54c9e-116">是否显示菜单栏。</span><span class="sxs-lookup"><span data-stu-id="54c9e-116">Whether or not to display the menu bar.</span></span>
[<span data-ttu-id="54c9e-117">滚动条</span><span class="sxs-lookup"><span data-stu-id="54c9e-117">ScrollBars</span></span>](#scrollbars) | <span data-ttu-id="54c9e-118">是否显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="54c9e-118">Whether or not to display scroll bars.</span></span>
[<span data-ttu-id="54c9e-119">状态</span><span class="sxs-lookup"><span data-stu-id="54c9e-119">Status</span></span>](#status) | <span data-ttu-id="54c9e-120">是否添加状态栏。</span><span class="sxs-lookup"><span data-stu-id="54c9e-120">Whether or not to add a status bar.</span></span>
[<span data-ttu-id="54c9e-121">工具栏</span><span class="sxs-lookup"><span data-stu-id="54c9e-121">Toolbar</span></span>](#toolbar) | <span data-ttu-id="54c9e-122">是否显示浏览器工具栏。</span><span class="sxs-lookup"><span data-stu-id="54c9e-122">Whether or not to display the browser toolbar.</span></span>
[<span data-ttu-id="54c9e-123">Top</span><span class="sxs-lookup"><span data-stu-id="54c9e-123">Top</span></span>](#top) | <span data-ttu-id="54c9e-124">窗口的顶部位置。</span><span class="sxs-lookup"><span data-stu-id="54c9e-124">The top position of the window.</span></span>
[<span data-ttu-id="54c9e-125">宽度</span><span class="sxs-lookup"><span data-stu-id="54c9e-125">Width</span></span>](#width) | <span data-ttu-id="54c9e-126">窗口的宽度。</span><span class="sxs-lookup"><span data-stu-id="54c9e-126">The width of the window.</span></span>
[<span data-ttu-id="54c9e-127">HasPosition</span><span class="sxs-lookup"><span data-stu-id="54c9e-127">HasPosition</span></span>](#hasposition) | <span data-ttu-id="54c9e-128">具有指定的 left 和 top 值。</span><span class="sxs-lookup"><span data-stu-id="54c9e-128">Has specified left and top values.</span></span>
[<span data-ttu-id="54c9e-129">HasSize</span><span class="sxs-lookup"><span data-stu-id="54c9e-129">HasSize</span></span>](#hassize) | <span data-ttu-id="54c9e-130">具有指定的高度和宽度值。</span><span class="sxs-lookup"><span data-stu-id="54c9e-130">Has specified height and width values.</span></span>

## <span data-ttu-id="54c9e-131">成员</span><span class="sxs-lookup"><span data-stu-id="54c9e-131">Members</span></span>

#### <span data-ttu-id="54c9e-132">高度</span><span class="sxs-lookup"><span data-stu-id="54c9e-132">Height</span></span> 

<span data-ttu-id="54c9e-133">窗口的高度。</span><span class="sxs-lookup"><span data-stu-id="54c9e-133">The height of the window.</span></span>

> <span data-ttu-id="54c9e-134">公共 uint [高度](#height)</span><span class="sxs-lookup"><span data-stu-id="54c9e-134">public uint [Height](#height)</span></span>

#### <span data-ttu-id="54c9e-135">向左</span><span class="sxs-lookup"><span data-stu-id="54c9e-135">Left</span></span> 

<span data-ttu-id="54c9e-136">窗口的左侧位置。</span><span class="sxs-lookup"><span data-stu-id="54c9e-136">The left position of the window.</span></span>

> <span data-ttu-id="54c9e-137">public uint [Left](#left)</span><span class="sxs-lookup"><span data-stu-id="54c9e-137">public uint [Left](#left)</span></span>

<span data-ttu-id="54c9e-138">如果 HasPosition 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="54c9e-138">Will fail if HasPosition is false.</span></span>

#### <span data-ttu-id="54c9e-139">菜单栏</span><span class="sxs-lookup"><span data-stu-id="54c9e-139">MenuBar</span></span> 

<span data-ttu-id="54c9e-140">是否显示菜单栏。</span><span class="sxs-lookup"><span data-stu-id="54c9e-140">Whether or not to display the menu bar.</span></span>

> <span data-ttu-id="54c9e-141">公共 int [菜单栏](#menubar)</span><span class="sxs-lookup"><span data-stu-id="54c9e-141">public int [MenuBar](#menubar)</span></span>

#### <span data-ttu-id="54c9e-142">滚动条</span><span class="sxs-lookup"><span data-stu-id="54c9e-142">ScrollBars</span></span> 

<span data-ttu-id="54c9e-143">是否显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="54c9e-143">Whether or not to display scroll bars.</span></span>

> <span data-ttu-id="54c9e-144">公共 int [滚动条](#scrollbars)</span><span class="sxs-lookup"><span data-stu-id="54c9e-144">public int [ScrollBars](#scrollbars)</span></span>

#### <span data-ttu-id="54c9e-145">状态</span><span class="sxs-lookup"><span data-stu-id="54c9e-145">Status</span></span> 

<span data-ttu-id="54c9e-146">是否添加状态栏。</span><span class="sxs-lookup"><span data-stu-id="54c9e-146">Whether or not to add a status bar.</span></span>

> <span data-ttu-id="54c9e-147">公共 int [状态](#status)</span><span class="sxs-lookup"><span data-stu-id="54c9e-147">public int [Status](#status)</span></span>

#### <span data-ttu-id="54c9e-148">工具栏</span><span class="sxs-lookup"><span data-stu-id="54c9e-148">Toolbar</span></span> 

<span data-ttu-id="54c9e-149">是否显示浏览器工具栏。</span><span class="sxs-lookup"><span data-stu-id="54c9e-149">Whether or not to display the browser toolbar.</span></span>

> <span data-ttu-id="54c9e-150">公共 int [工具栏](#toolbar)</span><span class="sxs-lookup"><span data-stu-id="54c9e-150">public int [Toolbar](#toolbar)</span></span>

#### <span data-ttu-id="54c9e-151">Top</span><span class="sxs-lookup"><span data-stu-id="54c9e-151">Top</span></span> 

<span data-ttu-id="54c9e-152">窗口的顶部位置。</span><span class="sxs-lookup"><span data-stu-id="54c9e-152">The top position of the window.</span></span>

> <span data-ttu-id="54c9e-153">公共 uint [顶部](#top)</span><span class="sxs-lookup"><span data-stu-id="54c9e-153">public uint [Top](#top)</span></span>

<span data-ttu-id="54c9e-154">如果 HasPosition 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="54c9e-154">Will fail if HasPosition is false.</span></span>

#### <span data-ttu-id="54c9e-155">宽度</span><span class="sxs-lookup"><span data-stu-id="54c9e-155">Width</span></span> 

<span data-ttu-id="54c9e-156">窗口的宽度。</span><span class="sxs-lookup"><span data-stu-id="54c9e-156">The width of the window.</span></span>

> <span data-ttu-id="54c9e-157">公共 uint [宽度](#width)</span><span class="sxs-lookup"><span data-stu-id="54c9e-157">public uint [Width](#width)</span></span>

#### <span data-ttu-id="54c9e-158">HasPosition</span><span class="sxs-lookup"><span data-stu-id="54c9e-158">HasPosition</span></span> 

<span data-ttu-id="54c9e-159">具有指定的 left 和 top 值。</span><span class="sxs-lookup"><span data-stu-id="54c9e-159">Has specified left and top values.</span></span>

> <span data-ttu-id="54c9e-160">公共 int [HasPosition](#hasposition) ( # A1</span><span class="sxs-lookup"><span data-stu-id="54c9e-160">public int [HasPosition](#hasposition)()</span></span>

#### <span data-ttu-id="54c9e-161">HasSize</span><span class="sxs-lookup"><span data-stu-id="54c9e-161">HasSize</span></span> 

<span data-ttu-id="54c9e-162">具有指定的高度和宽度值。</span><span class="sxs-lookup"><span data-stu-id="54c9e-162">Has specified height and width values.</span></span>

> <span data-ttu-id="54c9e-163">公共 int [HasSize](#hassize) ( # A1</span><span class="sxs-lookup"><span data-stu-id="54c9e-163">public int [HasSize](#hassize)()</span></span>

