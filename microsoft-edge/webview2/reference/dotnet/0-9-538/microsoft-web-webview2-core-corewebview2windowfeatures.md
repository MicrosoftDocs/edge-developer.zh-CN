---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2WindowFeatures 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: d6d6f52456823488c07288c8ed07b9655a29883a
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884435"
---
# <span data-ttu-id="b6c8d-104">CoreWebView2WindowFeatures 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="b6c8d-104">Microsoft.Web.WebView2.Core.CoreWebView2WindowFeatures class</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="b6c8d-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="b6c8d-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="b6c8d-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="b6c8d-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="b6c8d-107">Web 视图弹出窗口的窗口功能。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-107">Window features for a WebView popup window.</span></span>

## <span data-ttu-id="b6c8d-108">摘要</span><span class="sxs-lookup"><span data-stu-id="b6c8d-108">Summary</span></span>

 <span data-ttu-id="b6c8d-109">成员</span><span class="sxs-lookup"><span data-stu-id="b6c8d-109">Members</span></span>                        | <span data-ttu-id="b6c8d-110">描述</span><span class="sxs-lookup"><span data-stu-id="b6c8d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b6c8d-111">高度</span><span class="sxs-lookup"><span data-stu-id="b6c8d-111">Height</span></span>](#height) | <span data-ttu-id="b6c8d-112">窗口的高度。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-112">The height of the window.</span></span>
[<span data-ttu-id="b6c8d-113">向左</span><span class="sxs-lookup"><span data-stu-id="b6c8d-113">Left</span></span>](#left) | <span data-ttu-id="b6c8d-114">窗口的左侧位置。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-114">The left position of the window.</span></span>
[<span data-ttu-id="b6c8d-115">菜单栏</span><span class="sxs-lookup"><span data-stu-id="b6c8d-115">MenuBar</span></span>](#menubar) | <span data-ttu-id="b6c8d-116">是否显示菜单栏。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-116">Whether or not to display the menu bar.</span></span>
[<span data-ttu-id="b6c8d-117">滚动条</span><span class="sxs-lookup"><span data-stu-id="b6c8d-117">ScrollBars</span></span>](#scrollbars) | <span data-ttu-id="b6c8d-118">是否显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-118">Whether or not to display scroll bars.</span></span>
[<span data-ttu-id="b6c8d-119">状态</span><span class="sxs-lookup"><span data-stu-id="b6c8d-119">Status</span></span>](#status) | <span data-ttu-id="b6c8d-120">是否添加状态栏。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-120">Whether or not to add a status bar.</span></span>
[<span data-ttu-id="b6c8d-121">工具栏</span><span class="sxs-lookup"><span data-stu-id="b6c8d-121">Toolbar</span></span>](#toolbar) | <span data-ttu-id="b6c8d-122">是否显示浏览器工具栏。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-122">Whether or not to display the browser toolbar.</span></span>
[<span data-ttu-id="b6c8d-123">Top</span><span class="sxs-lookup"><span data-stu-id="b6c8d-123">Top</span></span>](#top) | <span data-ttu-id="b6c8d-124">窗口的顶部位置。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-124">The top position of the window.</span></span>
[<span data-ttu-id="b6c8d-125">宽度</span><span class="sxs-lookup"><span data-stu-id="b6c8d-125">Width</span></span>](#width) | <span data-ttu-id="b6c8d-126">窗口的宽度。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-126">The width of the window.</span></span>
[<span data-ttu-id="b6c8d-127">HasPosition</span><span class="sxs-lookup"><span data-stu-id="b6c8d-127">HasPosition</span></span>](#hasposition) | <span data-ttu-id="b6c8d-128">具有指定的 left 和 top 值。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-128">Has specified left and top values.</span></span>
[<span data-ttu-id="b6c8d-129">HasSize</span><span class="sxs-lookup"><span data-stu-id="b6c8d-129">HasSize</span></span>](#hassize) | <span data-ttu-id="b6c8d-130">具有指定的高度和宽度值。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-130">Has specified height and width values.</span></span>

## <span data-ttu-id="b6c8d-131">成员</span><span class="sxs-lookup"><span data-stu-id="b6c8d-131">Members</span></span>

#### <span data-ttu-id="b6c8d-132">高度</span><span class="sxs-lookup"><span data-stu-id="b6c8d-132">Height</span></span> 

<span data-ttu-id="b6c8d-133">窗口的高度。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-133">The height of the window.</span></span>

> <span data-ttu-id="b6c8d-134">公共 uint[高度](#height)</span><span class="sxs-lookup"><span data-stu-id="b6c8d-134">public uint [Height](#height)</span></span>

#### <span data-ttu-id="b6c8d-135">向左</span><span class="sxs-lookup"><span data-stu-id="b6c8d-135">Left</span></span> 

<span data-ttu-id="b6c8d-136">窗口的左侧位置。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-136">The left position of the window.</span></span>

> <span data-ttu-id="b6c8d-137">public uint [Left](#left)</span><span class="sxs-lookup"><span data-stu-id="b6c8d-137">public uint [Left](#left)</span></span>

<span data-ttu-id="b6c8d-138">如果 HasPosition 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-138">Will fail if HasPosition is false.</span></span>

#### <span data-ttu-id="b6c8d-139">菜单栏</span><span class="sxs-lookup"><span data-stu-id="b6c8d-139">MenuBar</span></span> 

<span data-ttu-id="b6c8d-140">是否显示菜单栏。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-140">Whether or not to display the menu bar.</span></span>

> <span data-ttu-id="b6c8d-141">公共 int[菜单栏](#menubar)</span><span class="sxs-lookup"><span data-stu-id="b6c8d-141">public int [MenuBar](#menubar)</span></span>

#### <span data-ttu-id="b6c8d-142">滚动条</span><span class="sxs-lookup"><span data-stu-id="b6c8d-142">ScrollBars</span></span> 

<span data-ttu-id="b6c8d-143">是否显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-143">Whether or not to display scroll bars.</span></span>

> <span data-ttu-id="b6c8d-144">公共 int[滚动条](#scrollbars)</span><span class="sxs-lookup"><span data-stu-id="b6c8d-144">public int [ScrollBars](#scrollbars)</span></span>

#### <span data-ttu-id="b6c8d-145">状态</span><span class="sxs-lookup"><span data-stu-id="b6c8d-145">Status</span></span> 

<span data-ttu-id="b6c8d-146">是否添加状态栏。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-146">Whether or not to add a status bar.</span></span>

> <span data-ttu-id="b6c8d-147">公共 int[状态](#status)</span><span class="sxs-lookup"><span data-stu-id="b6c8d-147">public int [Status](#status)</span></span>

#### <span data-ttu-id="b6c8d-148">工具栏</span><span class="sxs-lookup"><span data-stu-id="b6c8d-148">Toolbar</span></span> 

<span data-ttu-id="b6c8d-149">是否显示浏览器工具栏。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-149">Whether or not to display the browser toolbar.</span></span>

> <span data-ttu-id="b6c8d-150">公共 int[工具栏](#toolbar)</span><span class="sxs-lookup"><span data-stu-id="b6c8d-150">public int [Toolbar](#toolbar)</span></span>

#### <span data-ttu-id="b6c8d-151">Top</span><span class="sxs-lookup"><span data-stu-id="b6c8d-151">Top</span></span> 

<span data-ttu-id="b6c8d-152">窗口的顶部位置。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-152">The top position of the window.</span></span>

> <span data-ttu-id="b6c8d-153">公共 uint[顶部](#top)</span><span class="sxs-lookup"><span data-stu-id="b6c8d-153">public uint [Top](#top)</span></span>

<span data-ttu-id="b6c8d-154">如果 HasPosition 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-154">Will fail if HasPosition is false.</span></span>

#### <span data-ttu-id="b6c8d-155">宽度</span><span class="sxs-lookup"><span data-stu-id="b6c8d-155">Width</span></span> 

<span data-ttu-id="b6c8d-156">窗口的宽度。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-156">The width of the window.</span></span>

> <span data-ttu-id="b6c8d-157">公共 uint[宽度](#width)</span><span class="sxs-lookup"><span data-stu-id="b6c8d-157">public uint [Width](#width)</span></span>

#### <span data-ttu-id="b6c8d-158">HasPosition</span><span class="sxs-lookup"><span data-stu-id="b6c8d-158">HasPosition</span></span> 

<span data-ttu-id="b6c8d-159">具有指定的 left 和 top 值。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-159">Has specified left and top values.</span></span>

> <span data-ttu-id="b6c8d-160">公共 int [HasPosition](#hasposition)（）</span><span class="sxs-lookup"><span data-stu-id="b6c8d-160">public int [HasPosition](#hasposition)()</span></span>

#### <span data-ttu-id="b6c8d-161">HasSize</span><span class="sxs-lookup"><span data-stu-id="b6c8d-161">HasSize</span></span> 

<span data-ttu-id="b6c8d-162">具有指定的高度和宽度值。</span><span class="sxs-lookup"><span data-stu-id="b6c8d-162">Has specified height and width values.</span></span>

> <span data-ttu-id="b6c8d-163">公共 int [HasSize](#hassize)（）</span><span class="sxs-lookup"><span data-stu-id="b6c8d-163">public int [HasSize](#hassize)()</span></span>

