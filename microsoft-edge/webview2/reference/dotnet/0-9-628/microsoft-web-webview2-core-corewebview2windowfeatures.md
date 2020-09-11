---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2WindowFeatures 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 41ae506965067b478c3cb588eed0c8029704c4a3
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011649"
---
# <span data-ttu-id="d3021-104">CoreWebView2WindowFeatures 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="d3021-104">Microsoft.Web.WebView2.Core.CoreWebView2WindowFeatures class</span></span> 

<span data-ttu-id="d3021-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="d3021-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="d3021-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="d3021-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="d3021-107">Web 视图弹出窗口的窗口功能。</span><span class="sxs-lookup"><span data-stu-id="d3021-107">Window features for a WebView popup window.</span></span>

## <span data-ttu-id="d3021-108">摘要</span><span class="sxs-lookup"><span data-stu-id="d3021-108">Summary</span></span>

 <span data-ttu-id="d3021-109">成员</span><span class="sxs-lookup"><span data-stu-id="d3021-109">Members</span></span>                        | <span data-ttu-id="d3021-110">描述</span><span class="sxs-lookup"><span data-stu-id="d3021-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d3021-111">高度</span><span class="sxs-lookup"><span data-stu-id="d3021-111">Height</span></span>](#height) | <span data-ttu-id="d3021-112">窗口的高度。</span><span class="sxs-lookup"><span data-stu-id="d3021-112">The height of the window.</span></span>
[<span data-ttu-id="d3021-113">向左</span><span class="sxs-lookup"><span data-stu-id="d3021-113">Left</span></span>](#left) | <span data-ttu-id="d3021-114">窗口的左侧位置。</span><span class="sxs-lookup"><span data-stu-id="d3021-114">The left position of the window.</span></span>
[<span data-ttu-id="d3021-115">菜单栏</span><span class="sxs-lookup"><span data-stu-id="d3021-115">MenuBar</span></span>](#menubar) | <span data-ttu-id="d3021-116">是否显示菜单栏。</span><span class="sxs-lookup"><span data-stu-id="d3021-116">Whether or not to display the menu bar.</span></span>
[<span data-ttu-id="d3021-117">滚动条</span><span class="sxs-lookup"><span data-stu-id="d3021-117">ScrollBars</span></span>](#scrollbars) | <span data-ttu-id="d3021-118">是否显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="d3021-118">Whether or not to display scroll bars.</span></span>
[<span data-ttu-id="d3021-119">状态</span><span class="sxs-lookup"><span data-stu-id="d3021-119">Status</span></span>](#status) | <span data-ttu-id="d3021-120">是否添加状态栏。</span><span class="sxs-lookup"><span data-stu-id="d3021-120">Whether or not to add a status bar.</span></span>
[<span data-ttu-id="d3021-121">工具栏</span><span class="sxs-lookup"><span data-stu-id="d3021-121">Toolbar</span></span>](#toolbar) | <span data-ttu-id="d3021-122">是否显示浏览器工具栏。</span><span class="sxs-lookup"><span data-stu-id="d3021-122">Whether or not to display the browser toolbar.</span></span>
[<span data-ttu-id="d3021-123">Top</span><span class="sxs-lookup"><span data-stu-id="d3021-123">Top</span></span>](#top) | <span data-ttu-id="d3021-124">窗口的顶部位置。</span><span class="sxs-lookup"><span data-stu-id="d3021-124">The top position of the window.</span></span>
[<span data-ttu-id="d3021-125">宽度</span><span class="sxs-lookup"><span data-stu-id="d3021-125">Width</span></span>](#width) | <span data-ttu-id="d3021-126">窗口的宽度。</span><span class="sxs-lookup"><span data-stu-id="d3021-126">The width of the window.</span></span>
[<span data-ttu-id="d3021-127">HasPosition</span><span class="sxs-lookup"><span data-stu-id="d3021-127">HasPosition</span></span>](#hasposition) | <span data-ttu-id="d3021-128">具有指定的 left 和 top 值。</span><span class="sxs-lookup"><span data-stu-id="d3021-128">Has specified left and top values.</span></span>
[<span data-ttu-id="d3021-129">HasSize</span><span class="sxs-lookup"><span data-stu-id="d3021-129">HasSize</span></span>](#hassize) | <span data-ttu-id="d3021-130">具有指定的高度和宽度值。</span><span class="sxs-lookup"><span data-stu-id="d3021-130">Has specified height and width values.</span></span>

## <span data-ttu-id="d3021-131">成员</span><span class="sxs-lookup"><span data-stu-id="d3021-131">Members</span></span>

#### <span data-ttu-id="d3021-132">高度</span><span class="sxs-lookup"><span data-stu-id="d3021-132">Height</span></span> 

<span data-ttu-id="d3021-133">窗口的高度。</span><span class="sxs-lookup"><span data-stu-id="d3021-133">The height of the window.</span></span>

> <span data-ttu-id="d3021-134">公共 uint [高度](#height)</span><span class="sxs-lookup"><span data-stu-id="d3021-134">public uint [Height](#height)</span></span>

#### <span data-ttu-id="d3021-135">向左</span><span class="sxs-lookup"><span data-stu-id="d3021-135">Left</span></span> 

<span data-ttu-id="d3021-136">窗口的左侧位置。</span><span class="sxs-lookup"><span data-stu-id="d3021-136">The left position of the window.</span></span>

> <span data-ttu-id="d3021-137">public uint [Left](#left)</span><span class="sxs-lookup"><span data-stu-id="d3021-137">public uint [Left](#left)</span></span>

<span data-ttu-id="d3021-138">如果 HasPosition 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="d3021-138">Will fail if HasPosition is false.</span></span>

#### <span data-ttu-id="d3021-139">菜单栏</span><span class="sxs-lookup"><span data-stu-id="d3021-139">MenuBar</span></span> 

<span data-ttu-id="d3021-140">是否显示菜单栏。</span><span class="sxs-lookup"><span data-stu-id="d3021-140">Whether or not to display the menu bar.</span></span>

> <span data-ttu-id="d3021-141">公共 int [菜单栏](#menubar)</span><span class="sxs-lookup"><span data-stu-id="d3021-141">public int [MenuBar](#menubar)</span></span>

#### <span data-ttu-id="d3021-142">滚动条</span><span class="sxs-lookup"><span data-stu-id="d3021-142">ScrollBars</span></span> 

<span data-ttu-id="d3021-143">是否显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="d3021-143">Whether or not to display scroll bars.</span></span>

> <span data-ttu-id="d3021-144">公共 int [滚动条](#scrollbars)</span><span class="sxs-lookup"><span data-stu-id="d3021-144">public int [ScrollBars](#scrollbars)</span></span>

#### <span data-ttu-id="d3021-145">状态</span><span class="sxs-lookup"><span data-stu-id="d3021-145">Status</span></span> 

<span data-ttu-id="d3021-146">是否添加状态栏。</span><span class="sxs-lookup"><span data-stu-id="d3021-146">Whether or not to add a status bar.</span></span>

> <span data-ttu-id="d3021-147">公共 int [状态](#status)</span><span class="sxs-lookup"><span data-stu-id="d3021-147">public int [Status](#status)</span></span>

#### <span data-ttu-id="d3021-148">工具栏</span><span class="sxs-lookup"><span data-stu-id="d3021-148">Toolbar</span></span> 

<span data-ttu-id="d3021-149">是否显示浏览器工具栏。</span><span class="sxs-lookup"><span data-stu-id="d3021-149">Whether or not to display the browser toolbar.</span></span>

> <span data-ttu-id="d3021-150">公共 int [工具栏](#toolbar)</span><span class="sxs-lookup"><span data-stu-id="d3021-150">public int [Toolbar](#toolbar)</span></span>

#### <span data-ttu-id="d3021-151">Top</span><span class="sxs-lookup"><span data-stu-id="d3021-151">Top</span></span> 

<span data-ttu-id="d3021-152">窗口的顶部位置。</span><span class="sxs-lookup"><span data-stu-id="d3021-152">The top position of the window.</span></span>

> <span data-ttu-id="d3021-153">公共 uint [顶部](#top)</span><span class="sxs-lookup"><span data-stu-id="d3021-153">public uint [Top](#top)</span></span>

<span data-ttu-id="d3021-154">如果 HasPosition 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="d3021-154">Will fail if HasPosition is false.</span></span>

#### <span data-ttu-id="d3021-155">宽度</span><span class="sxs-lookup"><span data-stu-id="d3021-155">Width</span></span> 

<span data-ttu-id="d3021-156">窗口的宽度。</span><span class="sxs-lookup"><span data-stu-id="d3021-156">The width of the window.</span></span>

> <span data-ttu-id="d3021-157">公共 uint [宽度](#width)</span><span class="sxs-lookup"><span data-stu-id="d3021-157">public uint [Width](#width)</span></span>

#### <span data-ttu-id="d3021-158">HasPosition</span><span class="sxs-lookup"><span data-stu-id="d3021-158">HasPosition</span></span> 

<span data-ttu-id="d3021-159">具有指定的 left 和 top 值。</span><span class="sxs-lookup"><span data-stu-id="d3021-159">Has specified left and top values.</span></span>

> <span data-ttu-id="d3021-160">公共 int [HasPosition](#hasposition) ( # A1</span><span class="sxs-lookup"><span data-stu-id="d3021-160">public int [HasPosition](#hasposition)()</span></span>

#### <span data-ttu-id="d3021-161">HasSize</span><span class="sxs-lookup"><span data-stu-id="d3021-161">HasSize</span></span> 

<span data-ttu-id="d3021-162">具有指定的高度和宽度值。</span><span class="sxs-lookup"><span data-stu-id="d3021-162">Has specified height and width values.</span></span>

> <span data-ttu-id="d3021-163">公共 int [HasSize](#hassize) ( # A1</span><span class="sxs-lookup"><span data-stu-id="d3021-163">public int [HasSize](#hassize)()</span></span>

