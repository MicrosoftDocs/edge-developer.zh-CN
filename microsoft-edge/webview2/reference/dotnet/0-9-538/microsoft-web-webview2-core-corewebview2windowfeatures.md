---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 9ee85620ece653a2312076f7b6f4fe9f6ca3da92
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698557"
---
# <span data-ttu-id="e089d-104">CoreWebView2WindowFeatures 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="e089d-104">Microsoft.Web.WebView2.Core.CoreWebView2WindowFeatures class</span></span> 

> [!NOTE]
> <span data-ttu-id="e089d-105">这是我们的 SDK 版本[0.9.538](../../../releasenotes.md#09538)预发布版附带的[实验性 API](../../../concepts/versioning.md#experimental-apis) 。</span><span class="sxs-lookup"><span data-stu-id="e089d-105">This is an [experimental API](../../../concepts/versioning.md#experimental-apis) that shipped with our SDK version [0.9.538-prerelease](../../../releasenotes.md#09538).</span></span>

<span data-ttu-id="e089d-106">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="e089d-106">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="e089d-107">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="e089d-107">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="e089d-108">Web 视图弹出窗口的窗口功能。</span><span class="sxs-lookup"><span data-stu-id="e089d-108">Window features for a WebView popup window.</span></span>

## <span data-ttu-id="e089d-109">摘要</span><span class="sxs-lookup"><span data-stu-id="e089d-109">Summary</span></span>

 <span data-ttu-id="e089d-110">成员</span><span class="sxs-lookup"><span data-stu-id="e089d-110">Members</span></span>                        | <span data-ttu-id="e089d-111">描述</span><span class="sxs-lookup"><span data-stu-id="e089d-111">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e089d-112">高度</span><span class="sxs-lookup"><span data-stu-id="e089d-112">Height</span></span>](#height) | <span data-ttu-id="e089d-113">窗口的高度。</span><span class="sxs-lookup"><span data-stu-id="e089d-113">The height of the window.</span></span>
[<span data-ttu-id="e089d-114">向左</span><span class="sxs-lookup"><span data-stu-id="e089d-114">Left</span></span>](#left) | <span data-ttu-id="e089d-115">窗口的左侧位置。</span><span class="sxs-lookup"><span data-stu-id="e089d-115">The left position of the window.</span></span>
[<span data-ttu-id="e089d-116">菜单栏</span><span class="sxs-lookup"><span data-stu-id="e089d-116">MenuBar</span></span>](#menubar) | <span data-ttu-id="e089d-117">是否显示菜单栏。</span><span class="sxs-lookup"><span data-stu-id="e089d-117">Whether or not to display the menu bar.</span></span>
[<span data-ttu-id="e089d-118">滚动条</span><span class="sxs-lookup"><span data-stu-id="e089d-118">ScrollBars</span></span>](#scrollbars) | <span data-ttu-id="e089d-119">是否显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="e089d-119">Whether or not to display scroll bars.</span></span>
[<span data-ttu-id="e089d-120">状态</span><span class="sxs-lookup"><span data-stu-id="e089d-120">Status</span></span>](#status) | <span data-ttu-id="e089d-121">是否添加状态栏。</span><span class="sxs-lookup"><span data-stu-id="e089d-121">Whether or not to add a status bar.</span></span>
[<span data-ttu-id="e089d-122">工具栏</span><span class="sxs-lookup"><span data-stu-id="e089d-122">Toolbar</span></span>](#toolbar) | <span data-ttu-id="e089d-123">是否显示浏览器工具栏。</span><span class="sxs-lookup"><span data-stu-id="e089d-123">Whether or not to display the browser toolbar.</span></span>
[<span data-ttu-id="e089d-124">Top</span><span class="sxs-lookup"><span data-stu-id="e089d-124">Top</span></span>](#top) | <span data-ttu-id="e089d-125">窗口的顶部位置。</span><span class="sxs-lookup"><span data-stu-id="e089d-125">The top position of the window.</span></span>
[<span data-ttu-id="e089d-126">宽度</span><span class="sxs-lookup"><span data-stu-id="e089d-126">Width</span></span>](#width) | <span data-ttu-id="e089d-127">窗口的宽度。</span><span class="sxs-lookup"><span data-stu-id="e089d-127">The width of the window.</span></span>
[<span data-ttu-id="e089d-128">HasPosition</span><span class="sxs-lookup"><span data-stu-id="e089d-128">HasPosition</span></span>](#hasposition) | <span data-ttu-id="e089d-129">具有指定的 left 和 top 值。</span><span class="sxs-lookup"><span data-stu-id="e089d-129">Has specified left and top values.</span></span>
[<span data-ttu-id="e089d-130">HasSize</span><span class="sxs-lookup"><span data-stu-id="e089d-130">HasSize</span></span>](#hassize) | <span data-ttu-id="e089d-131">具有指定的高度和宽度值。</span><span class="sxs-lookup"><span data-stu-id="e089d-131">Has specified height and width values.</span></span>

## <span data-ttu-id="e089d-132">成员</span><span class="sxs-lookup"><span data-stu-id="e089d-132">Members</span></span>

#### <span data-ttu-id="e089d-133">高度</span><span class="sxs-lookup"><span data-stu-id="e089d-133">Height</span></span> 

<span data-ttu-id="e089d-134">窗口的高度。</span><span class="sxs-lookup"><span data-stu-id="e089d-134">The height of the window.</span></span>

> <span data-ttu-id="e089d-135">公共 uint[高度](#height)</span><span class="sxs-lookup"><span data-stu-id="e089d-135">public uint [Height](#height)</span></span>

#### <span data-ttu-id="e089d-136">向左</span><span class="sxs-lookup"><span data-stu-id="e089d-136">Left</span></span> 

<span data-ttu-id="e089d-137">窗口的左侧位置。</span><span class="sxs-lookup"><span data-stu-id="e089d-137">The left position of the window.</span></span>

> <span data-ttu-id="e089d-138">public uint [Left](#left)</span><span class="sxs-lookup"><span data-stu-id="e089d-138">public uint [Left](#left)</span></span>

<span data-ttu-id="e089d-139">如果 HasPosition 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="e089d-139">Will fail if HasPosition is false.</span></span>

#### <span data-ttu-id="e089d-140">菜单栏</span><span class="sxs-lookup"><span data-stu-id="e089d-140">MenuBar</span></span> 

<span data-ttu-id="e089d-141">是否显示菜单栏。</span><span class="sxs-lookup"><span data-stu-id="e089d-141">Whether or not to display the menu bar.</span></span>

> <span data-ttu-id="e089d-142">公共 int[菜单栏](#menubar)</span><span class="sxs-lookup"><span data-stu-id="e089d-142">public int [MenuBar](#menubar)</span></span>

#### <span data-ttu-id="e089d-143">滚动条</span><span class="sxs-lookup"><span data-stu-id="e089d-143">ScrollBars</span></span> 

<span data-ttu-id="e089d-144">是否显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="e089d-144">Whether or not to display scroll bars.</span></span>

> <span data-ttu-id="e089d-145">公共 int[滚动条](#scrollbars)</span><span class="sxs-lookup"><span data-stu-id="e089d-145">public int [ScrollBars](#scrollbars)</span></span>

#### <span data-ttu-id="e089d-146">状态</span><span class="sxs-lookup"><span data-stu-id="e089d-146">Status</span></span> 

<span data-ttu-id="e089d-147">是否添加状态栏。</span><span class="sxs-lookup"><span data-stu-id="e089d-147">Whether or not to add a status bar.</span></span>

> <span data-ttu-id="e089d-148">公共 int[状态](#status)</span><span class="sxs-lookup"><span data-stu-id="e089d-148">public int [Status](#status)</span></span>

#### <span data-ttu-id="e089d-149">工具栏</span><span class="sxs-lookup"><span data-stu-id="e089d-149">Toolbar</span></span> 

<span data-ttu-id="e089d-150">是否显示浏览器工具栏。</span><span class="sxs-lookup"><span data-stu-id="e089d-150">Whether or not to display the browser toolbar.</span></span>

> <span data-ttu-id="e089d-151">公共 int[工具栏](#toolbar)</span><span class="sxs-lookup"><span data-stu-id="e089d-151">public int [Toolbar](#toolbar)</span></span>

#### <span data-ttu-id="e089d-152">Top</span><span class="sxs-lookup"><span data-stu-id="e089d-152">Top</span></span> 

<span data-ttu-id="e089d-153">窗口的顶部位置。</span><span class="sxs-lookup"><span data-stu-id="e089d-153">The top position of the window.</span></span>

> <span data-ttu-id="e089d-154">公共 uint[顶部](#top)</span><span class="sxs-lookup"><span data-stu-id="e089d-154">public uint [Top](#top)</span></span>

<span data-ttu-id="e089d-155">如果 HasPosition 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="e089d-155">Will fail if HasPosition is false.</span></span>

#### <span data-ttu-id="e089d-156">宽度</span><span class="sxs-lookup"><span data-stu-id="e089d-156">Width</span></span> 

<span data-ttu-id="e089d-157">窗口的宽度。</span><span class="sxs-lookup"><span data-stu-id="e089d-157">The width of the window.</span></span>

> <span data-ttu-id="e089d-158">公共 uint[宽度](#width)</span><span class="sxs-lookup"><span data-stu-id="e089d-158">public uint [Width](#width)</span></span>

#### <span data-ttu-id="e089d-159">HasPosition</span><span class="sxs-lookup"><span data-stu-id="e089d-159">HasPosition</span></span> 

<span data-ttu-id="e089d-160">具有指定的 left 和 top 值。</span><span class="sxs-lookup"><span data-stu-id="e089d-160">Has specified left and top values.</span></span>

> <span data-ttu-id="e089d-161">公共 int [HasPosition](#hasposition)（）</span><span class="sxs-lookup"><span data-stu-id="e089d-161">public int [HasPosition](#hasposition)()</span></span>

#### <span data-ttu-id="e089d-162">HasSize</span><span class="sxs-lookup"><span data-stu-id="e089d-162">HasSize</span></span> 

<span data-ttu-id="e089d-163">具有指定的高度和宽度值。</span><span class="sxs-lookup"><span data-stu-id="e089d-163">Has specified height and width values.</span></span>

> <span data-ttu-id="e089d-164">公共 int [HasSize](#hassize)（）</span><span class="sxs-lookup"><span data-stu-id="e089d-164">public int [HasSize](#hassize)()</span></span>

