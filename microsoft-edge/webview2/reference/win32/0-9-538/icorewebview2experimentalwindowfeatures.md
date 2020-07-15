---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ExperimentalWindowFeatures
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalWindowFeatures
ms.openlocfilehash: 8b56d16e9c78738e9aa61e8c4c5b841b7fe4932f
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879903"
---
# <span data-ttu-id="dc5bb-104">interface ICoreWebView2ExperimentalWindowFeatures</span><span class="sxs-lookup"><span data-stu-id="dc5bb-104">interface ICoreWebView2ExperimentalWindowFeatures</span></span> 

> [!NOTE]
> <span data-ttu-id="dc5bb-105">这是使用预发行 SDK 版本0.9.538 随附的实验性 API。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-105">This an experimental API that is shipped with our prerelease SDK version 0.9.538.</span></span>

```
interface ICoreWebView2ExperimentalWindowFeatures
  : public IUnknown
```

<span data-ttu-id="dc5bb-106">Web 视图弹出窗口的窗口功能。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-106">Window features for a WebView popup window.</span></span>

## <span data-ttu-id="dc5bb-107">摘要</span><span class="sxs-lookup"><span data-stu-id="dc5bb-107">Summary</span></span>

 <span data-ttu-id="dc5bb-108">成员</span><span class="sxs-lookup"><span data-stu-id="dc5bb-108">Members</span></span>                        | <span data-ttu-id="dc5bb-109">描述</span><span class="sxs-lookup"><span data-stu-id="dc5bb-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="dc5bb-110">get_Height</span><span class="sxs-lookup"><span data-stu-id="dc5bb-110">get_Height</span></span>](#get_height) | <span data-ttu-id="dc5bb-111">窗口的高度。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-111">The height of the window.</span></span>
[<span data-ttu-id="dc5bb-112">get_Left</span><span class="sxs-lookup"><span data-stu-id="dc5bb-112">get_Left</span></span>](#get_left) | <span data-ttu-id="dc5bb-113">窗口的左侧位置。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-113">The left position of the window.</span></span> <span data-ttu-id="dc5bb-114">如果 HasPosition 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-114">Will fail if HasPosition is false.</span></span>
[<span data-ttu-id="dc5bb-115">get_MenuBar</span><span class="sxs-lookup"><span data-stu-id="dc5bb-115">get_MenuBar</span></span>](#get_menubar) | <span data-ttu-id="dc5bb-116">是否显示菜单栏。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-116">Whether or not to display the menu bar.</span></span>
[<span data-ttu-id="dc5bb-117">get_ScrollBars</span><span class="sxs-lookup"><span data-stu-id="dc5bb-117">get_ScrollBars</span></span>](#get_scrollbars) | <span data-ttu-id="dc5bb-118">是否显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-118">Whether or not to display scroll bars.</span></span>
[<span data-ttu-id="dc5bb-119">get_Status</span><span class="sxs-lookup"><span data-stu-id="dc5bb-119">get_Status</span></span>](#get_status) | <span data-ttu-id="dc5bb-120">是否添加状态栏。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-120">Whether or not to add a status bar.</span></span>
[<span data-ttu-id="dc5bb-121">get_Toolbar</span><span class="sxs-lookup"><span data-stu-id="dc5bb-121">get_Toolbar</span></span>](#get_toolbar) | <span data-ttu-id="dc5bb-122">是否显示浏览器工具栏。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-122">Whether or not to display the browser toolbar.</span></span>
[<span data-ttu-id="dc5bb-123">get_Top</span><span class="sxs-lookup"><span data-stu-id="dc5bb-123">get_Top</span></span>](#get_top) | <span data-ttu-id="dc5bb-124">窗口的顶部位置。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-124">The top position of the window.</span></span> <span data-ttu-id="dc5bb-125">如果 HasPosition 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-125">Will fail if HasPosition is false.</span></span>
[<span data-ttu-id="dc5bb-126">get_Width</span><span class="sxs-lookup"><span data-stu-id="dc5bb-126">get_Width</span></span>](#get_width) | <span data-ttu-id="dc5bb-127">窗口的宽度。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-127">The width of the window.</span></span>
[<span data-ttu-id="dc5bb-128">HasPosition</span><span class="sxs-lookup"><span data-stu-id="dc5bb-128">HasPosition</span></span>](#hasposition) | <span data-ttu-id="dc5bb-129">具有指定的 left 和 top 值。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-129">Has specified left and top values.</span></span>
[<span data-ttu-id="dc5bb-130">HasSize</span><span class="sxs-lookup"><span data-stu-id="dc5bb-130">HasSize</span></span>](#hassize) | <span data-ttu-id="dc5bb-131">具有指定的高度和宽度值。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-131">Has specified height and width values.</span></span>

<span data-ttu-id="dc5bb-132">这些字段与传递到 window 的 "windowFeatures" 相匹配。在中指定的打开[https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)</span><span class="sxs-lookup"><span data-stu-id="dc5bb-132">These fields match the 'windowFeatures' passed to window.open as specified in [https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)</span></span>

## <span data-ttu-id="dc5bb-133">成员</span><span class="sxs-lookup"><span data-stu-id="dc5bb-133">Members</span></span>

#### <span data-ttu-id="dc5bb-134">get_Height</span><span class="sxs-lookup"><span data-stu-id="dc5bb-134">get_Height</span></span> 

<span data-ttu-id="dc5bb-135">窗口的高度。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-135">The height of the window.</span></span>

> <span data-ttu-id="dc5bb-136">公共 HRESULT [get_Height](#get_height)（UINT32 \* Height）</span><span class="sxs-lookup"><span data-stu-id="dc5bb-136">public HRESULT [get_Height](#get_height)(UINT32 \* height)</span></span>

<span data-ttu-id="dc5bb-137">最小值为100。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-137">Minimum value is 100.</span></span> <span data-ttu-id="dc5bb-138">如果 HasSize 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-138">Will fail if HasSize is false.</span></span>

#### <span data-ttu-id="dc5bb-139">get_Left</span><span class="sxs-lookup"><span data-stu-id="dc5bb-139">get_Left</span></span> 

<span data-ttu-id="dc5bb-140">窗口的左侧位置。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-140">The left position of the window.</span></span> <span data-ttu-id="dc5bb-141">如果 HasPosition 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-141">Will fail if HasPosition is false.</span></span>

> <span data-ttu-id="dc5bb-142">公共 HRESULT [get_Left](#get_left)（UINT32 \* Left）</span><span class="sxs-lookup"><span data-stu-id="dc5bb-142">public HRESULT [get_Left](#get_left)(UINT32 \* left)</span></span>

#### <span data-ttu-id="dc5bb-143">get_MenuBar</span><span class="sxs-lookup"><span data-stu-id="dc5bb-143">get_MenuBar</span></span> 

<span data-ttu-id="dc5bb-144">是否显示菜单栏。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-144">Whether or not to display the menu bar.</span></span>

> <span data-ttu-id="dc5bb-145">public HRESULT [get_MenuBar](#get_menubar)（BOOL \* MenuBar）</span><span class="sxs-lookup"><span data-stu-id="dc5bb-145">public HRESULT [get_MenuBar](#get_menubar)(BOOL \* menuBar)</span></span>

#### <span data-ttu-id="dc5bb-146">get_ScrollBars</span><span class="sxs-lookup"><span data-stu-id="dc5bb-146">get_ScrollBars</span></span> 

<span data-ttu-id="dc5bb-147">是否显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-147">Whether or not to display scroll bars.</span></span>

> <span data-ttu-id="dc5bb-148">公共 HRESULT [get_ScrollBars](#get_scrollbars)（布尔 \* 滚动条）</span><span class="sxs-lookup"><span data-stu-id="dc5bb-148">public HRESULT [get_ScrollBars](#get_scrollbars)(BOOL \* scrollBars)</span></span>

#### <span data-ttu-id="dc5bb-149">get_Status</span><span class="sxs-lookup"><span data-stu-id="dc5bb-149">get_Status</span></span> 

<span data-ttu-id="dc5bb-150">是否添加状态栏。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-150">Whether or not to add a status bar.</span></span>

> <span data-ttu-id="dc5bb-151">公共 HRESULT [get_Status](#get_status)（布尔 \* 状态）</span><span class="sxs-lookup"><span data-stu-id="dc5bb-151">public HRESULT [get_Status](#get_status)(BOOL \* status)</span></span>

#### <span data-ttu-id="dc5bb-152">get_Toolbar</span><span class="sxs-lookup"><span data-stu-id="dc5bb-152">get_Toolbar</span></span> 

<span data-ttu-id="dc5bb-153">是否显示浏览器工具栏。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-153">Whether or not to display the browser toolbar.</span></span>

> <span data-ttu-id="dc5bb-154">公共 HRESULT [get_Toolbar](#get_toolbar)（BOOL \* 工具栏）</span><span class="sxs-lookup"><span data-stu-id="dc5bb-154">public HRESULT [get_Toolbar](#get_toolbar)(BOOL \* toolbar)</span></span>

#### <span data-ttu-id="dc5bb-155">get_Top</span><span class="sxs-lookup"><span data-stu-id="dc5bb-155">get_Top</span></span> 

<span data-ttu-id="dc5bb-156">窗口的顶部位置。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-156">The top position of the window.</span></span> <span data-ttu-id="dc5bb-157">如果 HasPosition 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-157">Will fail if HasPosition is false.</span></span>

> <span data-ttu-id="dc5bb-158">公共 HRESULT [get_Top](#get_top)（UINT32 \* Top）</span><span class="sxs-lookup"><span data-stu-id="dc5bb-158">public HRESULT [get_Top](#get_top)(UINT32 \* top)</span></span>

#### <span data-ttu-id="dc5bb-159">get_Width</span><span class="sxs-lookup"><span data-stu-id="dc5bb-159">get_Width</span></span> 

<span data-ttu-id="dc5bb-160">窗口的宽度。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-160">The width of the window.</span></span>

> <span data-ttu-id="dc5bb-161">公共 HRESULT [get_Width](#get_width)（UINT32 \* Width）</span><span class="sxs-lookup"><span data-stu-id="dc5bb-161">public HRESULT [get_Width](#get_width)(UINT32 \* width)</span></span>

<span data-ttu-id="dc5bb-162">最小值为100。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-162">Minimum value is 100.</span></span> <span data-ttu-id="dc5bb-163">如果 HasSize 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-163">Will fail if HasSize is false.</span></span>

#### <span data-ttu-id="dc5bb-164">HasPosition</span><span class="sxs-lookup"><span data-stu-id="dc5bb-164">HasPosition</span></span> 

<span data-ttu-id="dc5bb-165">具有指定的 left 和 top 值。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-165">Has specified left and top values.</span></span>

> <span data-ttu-id="dc5bb-166">公共 HRESULT [HasPosition](#hasposition)（BOOL \* HasPosition）</span><span class="sxs-lookup"><span data-stu-id="dc5bb-166">public HRESULT [HasPosition](#hasposition)(BOOL \* hasPosition)</span></span>

#### <span data-ttu-id="dc5bb-167">HasSize</span><span class="sxs-lookup"><span data-stu-id="dc5bb-167">HasSize</span></span> 

<span data-ttu-id="dc5bb-168">具有指定的高度和宽度值。</span><span class="sxs-lookup"><span data-stu-id="dc5bb-168">Has specified height and width values.</span></span>

> <span data-ttu-id="dc5bb-169">公共 HRESULT [HasSize](#hassize)（BOOL \* HasSize）</span><span class="sxs-lookup"><span data-stu-id="dc5bb-169">public HRESULT [HasSize](#hassize)(BOOL \* hasSize)</span></span>

