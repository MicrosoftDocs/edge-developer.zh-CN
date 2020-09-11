---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2WindowFeatures
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2WindowFeatures
ms.openlocfilehash: 90b5a09a752250dc342e7eefad031c9b5b83d345
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011731"
---
# <span data-ttu-id="c20ad-104">interface ICoreWebView2WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="c20ad-104">interface ICoreWebView2WindowFeatures</span></span> 

```
interface ICoreWebView2WindowFeatures
  : public IUnknown
```

<span data-ttu-id="c20ad-105">Web 视图弹出窗口的窗口功能。</span><span class="sxs-lookup"><span data-stu-id="c20ad-105">Window features for a WebView popup window.</span></span>

## <span data-ttu-id="c20ad-106">摘要</span><span class="sxs-lookup"><span data-stu-id="c20ad-106">Summary</span></span>

 <span data-ttu-id="c20ad-107">成员</span><span class="sxs-lookup"><span data-stu-id="c20ad-107">Members</span></span>                        | <span data-ttu-id="c20ad-108">描述</span><span class="sxs-lookup"><span data-stu-id="c20ad-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c20ad-109">get_Height</span><span class="sxs-lookup"><span data-stu-id="c20ad-109">get_Height</span></span>](#get_height) | <span data-ttu-id="c20ad-110">窗口的高度。</span><span class="sxs-lookup"><span data-stu-id="c20ad-110">The height of the window.</span></span>
[<span data-ttu-id="c20ad-111">get_Left</span><span class="sxs-lookup"><span data-stu-id="c20ad-111">get_Left</span></span>](#get_left) | <span data-ttu-id="c20ad-112">窗口的左侧位置。</span><span class="sxs-lookup"><span data-stu-id="c20ad-112">The left position of the window.</span></span> <span data-ttu-id="c20ad-113">如果 HasPosition 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="c20ad-113">Will fail if HasPosition is false.</span></span>
[<span data-ttu-id="c20ad-114">get_MenuBar</span><span class="sxs-lookup"><span data-stu-id="c20ad-114">get_MenuBar</span></span>](#get_menubar) | <span data-ttu-id="c20ad-115">是否显示菜单栏。</span><span class="sxs-lookup"><span data-stu-id="c20ad-115">Whether or not to display the menu bar.</span></span>
[<span data-ttu-id="c20ad-116">get_ScrollBars</span><span class="sxs-lookup"><span data-stu-id="c20ad-116">get_ScrollBars</span></span>](#get_scrollbars) | <span data-ttu-id="c20ad-117">是否显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="c20ad-117">Whether or not to display scroll bars.</span></span>
[<span data-ttu-id="c20ad-118">get_Status</span><span class="sxs-lookup"><span data-stu-id="c20ad-118">get_Status</span></span>](#get_status) | <span data-ttu-id="c20ad-119">是否添加状态栏。</span><span class="sxs-lookup"><span data-stu-id="c20ad-119">Whether or not to add a status bar.</span></span>
[<span data-ttu-id="c20ad-120">get_Toolbar</span><span class="sxs-lookup"><span data-stu-id="c20ad-120">get_Toolbar</span></span>](#get_toolbar) | <span data-ttu-id="c20ad-121">是否显示浏览器工具栏。</span><span class="sxs-lookup"><span data-stu-id="c20ad-121">Whether or not to display the browser toolbar.</span></span>
[<span data-ttu-id="c20ad-122">get_Top</span><span class="sxs-lookup"><span data-stu-id="c20ad-122">get_Top</span></span>](#get_top) | <span data-ttu-id="c20ad-123">窗口的顶部位置。</span><span class="sxs-lookup"><span data-stu-id="c20ad-123">The top position of the window.</span></span> <span data-ttu-id="c20ad-124">如果 HasPosition 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="c20ad-124">Will fail if HasPosition is false.</span></span>
[<span data-ttu-id="c20ad-125">get_Width</span><span class="sxs-lookup"><span data-stu-id="c20ad-125">get_Width</span></span>](#get_width) | <span data-ttu-id="c20ad-126">窗口的宽度。</span><span class="sxs-lookup"><span data-stu-id="c20ad-126">The width of the window.</span></span>
[<span data-ttu-id="c20ad-127">HasPosition</span><span class="sxs-lookup"><span data-stu-id="c20ad-127">HasPosition</span></span>](#hasposition) | <span data-ttu-id="c20ad-128">具有指定的 left 和 top 值。</span><span class="sxs-lookup"><span data-stu-id="c20ad-128">Has specified left and top values.</span></span>
[<span data-ttu-id="c20ad-129">HasSize</span><span class="sxs-lookup"><span data-stu-id="c20ad-129">HasSize</span></span>](#hassize) | <span data-ttu-id="c20ad-130">具有指定的高度和宽度值。</span><span class="sxs-lookup"><span data-stu-id="c20ad-130">Has specified height and width values.</span></span>

<span data-ttu-id="c20ad-131">这些字段与传递到 window 的 "windowFeatures" 相匹配。在中指定的打开 [https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)</span><span class="sxs-lookup"><span data-stu-id="c20ad-131">These fields match the 'windowFeatures' passed to window.open as specified in [https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)</span></span>

## <span data-ttu-id="c20ad-132">成员</span><span class="sxs-lookup"><span data-stu-id="c20ad-132">Members</span></span>

#### <span data-ttu-id="c20ad-133">get_Height</span><span class="sxs-lookup"><span data-stu-id="c20ad-133">get_Height</span></span> 

<span data-ttu-id="c20ad-134">窗口的高度。</span><span class="sxs-lookup"><span data-stu-id="c20ad-134">The height of the window.</span></span>

> <span data-ttu-id="c20ad-135">公共 HRESULT [get_Height](#get_height) (UINT32 \* Height) </span><span class="sxs-lookup"><span data-stu-id="c20ad-135">public HRESULT [get_Height](#get_height)(UINT32 \* height)</span></span>

<span data-ttu-id="c20ad-136">最小值为100。</span><span class="sxs-lookup"><span data-stu-id="c20ad-136">Minimum value is 100.</span></span> <span data-ttu-id="c20ad-137">如果 HasSize 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="c20ad-137">Will fail if HasSize is false.</span></span>

#### <span data-ttu-id="c20ad-138">get_Left</span><span class="sxs-lookup"><span data-stu-id="c20ad-138">get_Left</span></span> 

<span data-ttu-id="c20ad-139">窗口的左侧位置。</span><span class="sxs-lookup"><span data-stu-id="c20ad-139">The left position of the window.</span></span> <span data-ttu-id="c20ad-140">如果 HasPosition 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="c20ad-140">Will fail if HasPosition is false.</span></span>

> <span data-ttu-id="c20ad-141">公共 HRESULT [get_Left](#get_left) (UINT32 \* Left) </span><span class="sxs-lookup"><span data-stu-id="c20ad-141">public HRESULT [get_Left](#get_left)(UINT32 \* left)</span></span>

#### <span data-ttu-id="c20ad-142">get_MenuBar</span><span class="sxs-lookup"><span data-stu-id="c20ad-142">get_MenuBar</span></span> 

<span data-ttu-id="c20ad-143">是否显示菜单栏。</span><span class="sxs-lookup"><span data-stu-id="c20ad-143">Whether or not to display the menu bar.</span></span>

> <span data-ttu-id="c20ad-144"> (BOOL\ * menuBar 的公共 HRESULT [get_MenuBar](#get_menubar)) </span><span class="sxs-lookup"><span data-stu-id="c20ad-144">public HRESULT [get_MenuBar](#get_menubar)(BOOL \* menuBar)</span></span>

#### <span data-ttu-id="c20ad-145">get_ScrollBars</span><span class="sxs-lookup"><span data-stu-id="c20ad-145">get_ScrollBars</span></span> 

<span data-ttu-id="c20ad-146">是否显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="c20ad-146">Whether or not to display scroll bars.</span></span>

> <span data-ttu-id="c20ad-147">公共 HRESULT [get_ScrollBars](#get_scrollbars) (BOOL \* 滚动条) </span><span class="sxs-lookup"><span data-stu-id="c20ad-147">public HRESULT [get_ScrollBars](#get_scrollbars)(BOOL \* scrollBars)</span></span>

#### <span data-ttu-id="c20ad-148">get_Status</span><span class="sxs-lookup"><span data-stu-id="c20ad-148">get_Status</span></span> 

<span data-ttu-id="c20ad-149">是否添加状态栏。</span><span class="sxs-lookup"><span data-stu-id="c20ad-149">Whether or not to add a status bar.</span></span>

> <span data-ttu-id="c20ad-150">公共 HRESULT [get_Status](#get_status) (BOOL \* 状态) </span><span class="sxs-lookup"><span data-stu-id="c20ad-150">public HRESULT [get_Status](#get_status)(BOOL \* status)</span></span>

#### <span data-ttu-id="c20ad-151">get_Toolbar</span><span class="sxs-lookup"><span data-stu-id="c20ad-151">get_Toolbar</span></span> 

<span data-ttu-id="c20ad-152">是否显示浏览器工具栏。</span><span class="sxs-lookup"><span data-stu-id="c20ad-152">Whether or not to display the browser toolbar.</span></span>

> <span data-ttu-id="c20ad-153"> (BOOL\ * 工具栏的公共 HRESULT [get_Toolbar](#get_toolbar)) </span><span class="sxs-lookup"><span data-stu-id="c20ad-153">public HRESULT [get_Toolbar](#get_toolbar)(BOOL \* toolbar)</span></span>

#### <span data-ttu-id="c20ad-154">get_Top</span><span class="sxs-lookup"><span data-stu-id="c20ad-154">get_Top</span></span> 

<span data-ttu-id="c20ad-155">窗口的顶部位置。</span><span class="sxs-lookup"><span data-stu-id="c20ad-155">The top position of the window.</span></span> <span data-ttu-id="c20ad-156">如果 HasPosition 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="c20ad-156">Will fail if HasPosition is false.</span></span>

> <span data-ttu-id="c20ad-157">公共 HRESULT [get_Top](#get_top) (UINT32 \* Top) </span><span class="sxs-lookup"><span data-stu-id="c20ad-157">public HRESULT [get_Top](#get_top)(UINT32 \* top)</span></span>

#### <span data-ttu-id="c20ad-158">get_Width</span><span class="sxs-lookup"><span data-stu-id="c20ad-158">get_Width</span></span> 

<span data-ttu-id="c20ad-159">窗口的宽度。</span><span class="sxs-lookup"><span data-stu-id="c20ad-159">The width of the window.</span></span>

> <span data-ttu-id="c20ad-160">公共 HRESULT [get_Width](#get_width) (UINT32 \* Width) </span><span class="sxs-lookup"><span data-stu-id="c20ad-160">public HRESULT [get_Width](#get_width)(UINT32 \* width)</span></span>

<span data-ttu-id="c20ad-161">最小值为100。</span><span class="sxs-lookup"><span data-stu-id="c20ad-161">Minimum value is 100.</span></span> <span data-ttu-id="c20ad-162">如果 HasSize 为 false，则不会失败。</span><span class="sxs-lookup"><span data-stu-id="c20ad-162">Will fail if HasSize is false.</span></span>

#### <span data-ttu-id="c20ad-163">HasPosition</span><span class="sxs-lookup"><span data-stu-id="c20ad-163">HasPosition</span></span> 

<span data-ttu-id="c20ad-164">具有指定的 left 和 top 值。</span><span class="sxs-lookup"><span data-stu-id="c20ad-164">Has specified left and top values.</span></span>

> <span data-ttu-id="c20ad-165">公共 HRESULT [HasPosition](#hasposition) (BOOL \* HasPosition) </span><span class="sxs-lookup"><span data-stu-id="c20ad-165">public HRESULT [HasPosition](#hasposition)(BOOL \* hasPosition)</span></span>

#### <span data-ttu-id="c20ad-166">HasSize</span><span class="sxs-lookup"><span data-stu-id="c20ad-166">HasSize</span></span> 

<span data-ttu-id="c20ad-167">具有指定的高度和宽度值。</span><span class="sxs-lookup"><span data-stu-id="c20ad-167">Has specified height and width values.</span></span>

> <span data-ttu-id="c20ad-168">公共 HRESULT [HasSize](#hassize) (BOOL \* HasSize) </span><span class="sxs-lookup"><span data-stu-id="c20ad-168">public HRESULT [HasSize](#hassize)(BOOL \* hasSize)</span></span>

