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
ms.openlocfilehash: 14b549fc299b4feb185fb391b9ad4ec1a9dde892
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698443"
---
# <span data-ttu-id="66397-104">CoreWebView2PointerInfo 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="66397-104">Microsoft.Web.WebView2.Core.CoreWebView2PointerInfo class</span></span> 

<span data-ttu-id="66397-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="66397-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="66397-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="66397-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="66397-107">这通常表示一个组合的 win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO 对象。</span><span class="sxs-lookup"><span data-stu-id="66397-107">This mostly represents a combined win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO object.</span></span>

## <span data-ttu-id="66397-108">摘要</span><span class="sxs-lookup"><span data-stu-id="66397-108">Summary</span></span>

 <span data-ttu-id="66397-109">成员</span><span class="sxs-lookup"><span data-stu-id="66397-109">Members</span></span>                        | <span data-ttu-id="66397-110">描述</span><span class="sxs-lookup"><span data-stu-id="66397-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="66397-111">ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="66397-111">ButtonChangeKind</span></span>](#buttonchangekind) | <span data-ttu-id="66397-112">指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="66397-112">The ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="66397-113">DisplayRect</span><span class="sxs-lookup"><span data-stu-id="66397-113">DisplayRect</span></span>](#displayrect) | <span data-ttu-id="66397-114">在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="66397-114">The DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="66397-115">FrameId</span><span class="sxs-lookup"><span data-stu-id="66397-115">FrameId</span></span>](#frameid) | <span data-ttu-id="66397-116">指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="66397-116">The FrameID of the pointer event.</span></span>
[<span data-ttu-id="66397-117">HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="66397-117">HimetricLocation</span></span>](#himetriclocation) | <span data-ttu-id="66397-118">指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="66397-118">The HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="66397-119">HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="66397-119">HimetricLocationRaw</span></span>](#himetriclocationraw) | <span data-ttu-id="66397-120">指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="66397-120">The HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="66397-121">HistoryCount</span><span class="sxs-lookup"><span data-stu-id="66397-121">HistoryCount</span></span>](#historycount) | <span data-ttu-id="66397-122">指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="66397-122">The HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="66397-123">InputData</span><span class="sxs-lookup"><span data-stu-id="66397-123">InputData</span></span>](#inputdata) | <span data-ttu-id="66397-124">指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="66397-124">The InputData of the pointer event.</span></span>
[<span data-ttu-id="66397-125">KeyStates</span><span class="sxs-lookup"><span data-stu-id="66397-125">KeyStates</span></span>](#keystates) | <span data-ttu-id="66397-126">指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="66397-126">The KeyStates of the pointer event.</span></span>
[<span data-ttu-id="66397-127">PenFlags</span><span class="sxs-lookup"><span data-stu-id="66397-127">PenFlags</span></span>](#penflags) | <span data-ttu-id="66397-128">指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="66397-128">The PenFlags of the pointer event.</span></span>
[<span data-ttu-id="66397-129">PenMask</span><span class="sxs-lookup"><span data-stu-id="66397-129">PenMask</span></span>](#penmask) | <span data-ttu-id="66397-130">指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="66397-130">The PenMask of the pointer event.</span></span>
[<span data-ttu-id="66397-131">PenPressure</span><span class="sxs-lookup"><span data-stu-id="66397-131">PenPressure</span></span>](#penpressure) | <span data-ttu-id="66397-132">指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="66397-132">The PenPressure of the pointer event.</span></span>
[<span data-ttu-id="66397-133">PenRotation</span><span class="sxs-lookup"><span data-stu-id="66397-133">PenRotation</span></span>](#penrotation) | <span data-ttu-id="66397-134">指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="66397-134">The PenRotation of the pointer event.</span></span>
[<span data-ttu-id="66397-135">PenTiltX</span><span class="sxs-lookup"><span data-stu-id="66397-135">PenTiltX</span></span>](#pentiltx) | <span data-ttu-id="66397-136">指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="66397-136">The PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="66397-137">PenTiltY</span><span class="sxs-lookup"><span data-stu-id="66397-137">PenTiltY</span></span>](#pentilty) | <span data-ttu-id="66397-138">指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="66397-138">The PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="66397-139">PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="66397-139">PerformanceCount</span></span>](#performancecount) | <span data-ttu-id="66397-140">指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="66397-140">The PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="66397-141">PixelLocation</span><span class="sxs-lookup"><span data-stu-id="66397-141">PixelLocation</span></span>](#pixellocation) | <span data-ttu-id="66397-142">指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="66397-142">The PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="66397-143">PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="66397-143">PixelLocationRaw</span></span>](#pixellocationraw) | <span data-ttu-id="66397-144">指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="66397-144">The PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="66397-145">PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="66397-145">PointerDeviceRect</span></span>](#pointerdevicerect) | <span data-ttu-id="66397-146">在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="66397-146">The PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="66397-147">PointerFlags</span><span class="sxs-lookup"><span data-stu-id="66397-147">PointerFlags</span></span>](#pointerflags) | <span data-ttu-id="66397-148">指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="66397-148">The PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="66397-149">PointerId</span><span class="sxs-lookup"><span data-stu-id="66397-149">PointerId</span></span>](#pointerid) | <span data-ttu-id="66397-150">指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="66397-150">The PointerId of the pointer event.</span></span>
[<span data-ttu-id="66397-151">PointerKind</span><span class="sxs-lookup"><span data-stu-id="66397-151">PointerKind</span></span>](#pointerkind) | <span data-ttu-id="66397-152">指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="66397-152">The PointerKind of the pointer event.</span></span>
[<span data-ttu-id="66397-153">时间</span><span class="sxs-lookup"><span data-stu-id="66397-153">Time</span></span>](#time) | <span data-ttu-id="66397-154">指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="66397-154">The Time of the pointer event.</span></span>
[<span data-ttu-id="66397-155">TouchContact</span><span class="sxs-lookup"><span data-stu-id="66397-155">TouchContact</span></span>](#touchcontact) | <span data-ttu-id="66397-156">指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="66397-156">The TouchContact of the pointer event.</span></span>
[<span data-ttu-id="66397-157">TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="66397-157">TouchContactRaw</span></span>](#touchcontactraw) | <span data-ttu-id="66397-158">指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="66397-158">The TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="66397-159">TouchFlags</span><span class="sxs-lookup"><span data-stu-id="66397-159">TouchFlags</span></span>](#touchflags) | <span data-ttu-id="66397-160">指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="66397-160">The TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="66397-161">TouchMask</span><span class="sxs-lookup"><span data-stu-id="66397-161">TouchMask</span></span>](#touchmask) | <span data-ttu-id="66397-162">指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="66397-162">The TouchMask of the pointer event.</span></span>
[<span data-ttu-id="66397-163">TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="66397-163">TouchOrientation</span></span>](#touchorientation) | <span data-ttu-id="66397-164">指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="66397-164">The TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="66397-165">TouchPressure</span><span class="sxs-lookup"><span data-stu-id="66397-165">TouchPressure</span></span>](#touchpressure) | <span data-ttu-id="66397-166">指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="66397-166">The TouchPressure of the pointer event.</span></span>

## <span data-ttu-id="66397-167">成员</span><span class="sxs-lookup"><span data-stu-id="66397-167">Members</span></span>

#### <span data-ttu-id="66397-168">ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="66397-168">ButtonChangeKind</span></span> 

<span data-ttu-id="66397-169">指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="66397-169">The ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="66397-170">公共 int [ButtonChangeKind](#buttonchangekind)</span><span class="sxs-lookup"><span data-stu-id="66397-170">public int [ButtonChangeKind](#buttonchangekind)</span></span>

<span data-ttu-id="66397-171">这对应于 POINTER_INFO 结构的 ButtonChangeKind 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-171">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="66397-172">这些值由 Windows SDK 中的 POINTER_BUTTON_CHANGE_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="66397-172">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-173">DisplayRect</span><span class="sxs-lookup"><span data-stu-id="66397-173">DisplayRect</span></span> 

<span data-ttu-id="66397-174">在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="66397-174">The DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="66397-175">公共矩形[DisplayRect](#displayrect)</span><span class="sxs-lookup"><span data-stu-id="66397-175">public Rect [DisplayRect](#displayrect)</span></span>

#### <span data-ttu-id="66397-176">FrameId</span><span class="sxs-lookup"><span data-stu-id="66397-176">FrameId</span></span> 

<span data-ttu-id="66397-177">指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="66397-177">The FrameID of the pointer event.</span></span>

> <span data-ttu-id="66397-178">公共 uint [FrameId](#frameid)</span><span class="sxs-lookup"><span data-stu-id="66397-178">public uint [FrameId](#frameid)</span></span>

<span data-ttu-id="66397-179">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 frameId 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-179">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-180">HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="66397-180">HimetricLocation</span></span> 

<span data-ttu-id="66397-181">指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="66397-181">The HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="66397-182">公共点[HimetricLocation](#himetriclocation)</span><span class="sxs-lookup"><span data-stu-id="66397-182">public Point [HimetricLocation](#himetriclocation)</span></span>

<span data-ttu-id="66397-183">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-183">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-184">HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="66397-184">HimetricLocationRaw</span></span> 

<span data-ttu-id="66397-185">指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="66397-185">The HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="66397-186">公共点[HimetricLocationRaw](#himetriclocationraw)</span><span class="sxs-lookup"><span data-stu-id="66397-186">public Point [HimetricLocationRaw](#himetriclocationraw)</span></span>

<span data-ttu-id="66397-187">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-187">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-188">HistoryCount</span><span class="sxs-lookup"><span data-stu-id="66397-188">HistoryCount</span></span> 

<span data-ttu-id="66397-189">指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="66397-189">The HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="66397-190">公共 uint [HistoryCount](#historycount)</span><span class="sxs-lookup"><span data-stu-id="66397-190">public uint [HistoryCount](#historycount)</span></span>

<span data-ttu-id="66397-191">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 historyCount 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-191">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-192">InputData</span><span class="sxs-lookup"><span data-stu-id="66397-192">InputData</span></span> 

<span data-ttu-id="66397-193">指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="66397-193">The InputData of the pointer event.</span></span>

> <span data-ttu-id="66397-194">公共 int [InputData](#inputdata)</span><span class="sxs-lookup"><span data-stu-id="66397-194">public int [InputData](#inputdata)</span></span>

<span data-ttu-id="66397-195">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 InputData 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-195">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-196">KeyStates</span><span class="sxs-lookup"><span data-stu-id="66397-196">KeyStates</span></span> 

<span data-ttu-id="66397-197">指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="66397-197">The KeyStates of the pointer event.</span></span>

> <span data-ttu-id="66397-198">公共 uint [KeyStates](#keystates)</span><span class="sxs-lookup"><span data-stu-id="66397-198">public uint [KeyStates](#keystates)</span></span>

<span data-ttu-id="66397-199">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwKeyStates 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-199">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-200">PenFlags</span><span class="sxs-lookup"><span data-stu-id="66397-200">PenFlags</span></span> 

<span data-ttu-id="66397-201">指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="66397-201">The PenFlags of the pointer event.</span></span>

> <span data-ttu-id="66397-202">公共 uint [PenFlags](#penflags)</span><span class="sxs-lookup"><span data-stu-id="66397-202">public uint [PenFlags](#penflags)</span></span>

<span data-ttu-id="66397-203">这对应于 POINTER_PEN_INFO 结构的 penFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-203">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="66397-204">这些值由 Windows SDK 中的 PEN_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="66397-204">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-205">PenMask</span><span class="sxs-lookup"><span data-stu-id="66397-205">PenMask</span></span> 

<span data-ttu-id="66397-206">指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="66397-206">The PenMask of the pointer event.</span></span>

> <span data-ttu-id="66397-207">公共 uint [PenMask](#penmask)</span><span class="sxs-lookup"><span data-stu-id="66397-207">public uint [PenMask](#penmask)</span></span>

<span data-ttu-id="66397-208">这对应于 POINTER_PEN_INFO 结构的 penMask 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-208">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="66397-209">这些值由 Windows SDK 中的 PEN_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="66397-209">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-210">PenPressure</span><span class="sxs-lookup"><span data-stu-id="66397-210">PenPressure</span></span> 

<span data-ttu-id="66397-211">指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="66397-211">The PenPressure of the pointer event.</span></span>

> <span data-ttu-id="66397-212">公共 uint [PenPressure](#penpressure)</span><span class="sxs-lookup"><span data-stu-id="66397-212">public uint [PenPressure](#penpressure)</span></span>

<span data-ttu-id="66397-213">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="66397-213">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-214">PenRotation</span><span class="sxs-lookup"><span data-stu-id="66397-214">PenRotation</span></span> 

<span data-ttu-id="66397-215">指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="66397-215">The PenRotation of the pointer event.</span></span>

> <span data-ttu-id="66397-216">公共 uint [PenRotation](#penrotation)</span><span class="sxs-lookup"><span data-stu-id="66397-216">public uint [PenRotation](#penrotation)</span></span>

<span data-ttu-id="66397-217">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的旋转属性。</span><span class="sxs-lookup"><span data-stu-id="66397-217">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-218">PenTiltX</span><span class="sxs-lookup"><span data-stu-id="66397-218">PenTiltX</span></span> 

<span data-ttu-id="66397-219">指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="66397-219">The PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="66397-220">公共 int [PenTiltX](#pentiltx)</span><span class="sxs-lookup"><span data-stu-id="66397-220">public int [PenTiltX](#pentiltx)</span></span>

<span data-ttu-id="66397-221">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltX 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-221">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-222">PenTiltY</span><span class="sxs-lookup"><span data-stu-id="66397-222">PenTiltY</span></span> 

<span data-ttu-id="66397-223">指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="66397-223">The PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="66397-224">公共 int [PenTiltY](#pentilty)</span><span class="sxs-lookup"><span data-stu-id="66397-224">public int [PenTiltY](#pentilty)</span></span>

<span data-ttu-id="66397-225">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltY 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-225">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-226">PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="66397-226">PerformanceCount</span></span> 

<span data-ttu-id="66397-227">指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="66397-227">The PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="66397-228">公共 ulong [PerformanceCount](#performancecount)</span><span class="sxs-lookup"><span data-stu-id="66397-228">public ulong [PerformanceCount](#performancecount)</span></span>

<span data-ttu-id="66397-229">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 PerformanceCount 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-229">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-230">PixelLocation</span><span class="sxs-lookup"><span data-stu-id="66397-230">PixelLocation</span></span> 

<span data-ttu-id="66397-231">指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="66397-231">The PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="66397-232">公共点[PixelLocation](#pixellocation)</span><span class="sxs-lookup"><span data-stu-id="66397-232">public Point [PixelLocation](#pixellocation)</span></span>

<span data-ttu-id="66397-233">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-233">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-234">PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="66397-234">PixelLocationRaw</span></span> 

<span data-ttu-id="66397-235">指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="66397-235">The PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="66397-236">公共点[PixelLocationRaw](#pixellocationraw)</span><span class="sxs-lookup"><span data-stu-id="66397-236">public Point [PixelLocationRaw](#pixellocationraw)</span></span>

<span data-ttu-id="66397-237">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-237">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-238">PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="66397-238">PointerDeviceRect</span></span> 

<span data-ttu-id="66397-239">在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="66397-239">The PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="66397-240">公共矩形[PointerDeviceRect](#pointerdevicerect)</span><span class="sxs-lookup"><span data-stu-id="66397-240">public Rect [PointerDeviceRect](#pointerdevicerect)</span></span>

#### <span data-ttu-id="66397-241">PointerFlags</span><span class="sxs-lookup"><span data-stu-id="66397-241">PointerFlags</span></span> 

<span data-ttu-id="66397-242">指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="66397-242">The PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="66397-243">公共 uint [PointerFlags](#pointerflags)</span><span class="sxs-lookup"><span data-stu-id="66397-243">public uint [PointerFlags](#pointerflags)</span></span>

<span data-ttu-id="66397-244">这对应于 POINTER_INFO 结构的 pointerFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-244">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="66397-245">这些值由 Windows SDK 中的 POINTER_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="66397-245">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-246">PointerId</span><span class="sxs-lookup"><span data-stu-id="66397-246">PointerId</span></span> 

<span data-ttu-id="66397-247">指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="66397-247">The PointerId of the pointer event.</span></span>

> <span data-ttu-id="66397-248">公共 uint [PointerId](#pointerid)</span><span class="sxs-lookup"><span data-stu-id="66397-248">public uint [PointerId](#pointerid)</span></span>

<span data-ttu-id="66397-249">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 pointerId 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-249">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-250">PointerKind</span><span class="sxs-lookup"><span data-stu-id="66397-250">PointerKind</span></span> 

<span data-ttu-id="66397-251">指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="66397-251">The PointerKind of the pointer event.</span></span>

> <span data-ttu-id="66397-252">公共 uint [PointerKind](#pointerkind)</span><span class="sxs-lookup"><span data-stu-id="66397-252">public uint [PointerKind](#pointerkind)</span></span>

<span data-ttu-id="66397-253">这对应于 POINTER_INFO 结构的 pointerKind 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-253">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="66397-254">这些值由 Windows SDK 中的 POINTER_INPUT_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="66397-254">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="66397-255">支持 PT_PEN 和 PT_TOUCH。</span><span class="sxs-lookup"><span data-stu-id="66397-255">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="66397-256">时间</span><span class="sxs-lookup"><span data-stu-id="66397-256">Time</span></span> 

<span data-ttu-id="66397-257">指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="66397-257">The Time of the pointer event.</span></span>

> <span data-ttu-id="66397-258">公共 uint[时间](#time)</span><span class="sxs-lookup"><span data-stu-id="66397-258">public uint [Time](#time)</span></span>

<span data-ttu-id="66397-259">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwTime 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-259">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-260">TouchContact</span><span class="sxs-lookup"><span data-stu-id="66397-260">TouchContact</span></span> 

<span data-ttu-id="66397-261">指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="66397-261">The TouchContact of the pointer event.</span></span>

> <span data-ttu-id="66397-262">公共矩形[TouchContact](#touchcontact)</span><span class="sxs-lookup"><span data-stu-id="66397-262">public Rect [TouchContact](#touchcontact)</span></span>

<span data-ttu-id="66397-263">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContact 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-263">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-264">TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="66397-264">TouchContactRaw</span></span> 

<span data-ttu-id="66397-265">指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="66397-265">The TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="66397-266">公共矩形[TouchContactRaw](#touchcontactraw)</span><span class="sxs-lookup"><span data-stu-id="66397-266">public Rect [TouchContactRaw](#touchcontactraw)</span></span>

<span data-ttu-id="66397-267">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContactRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-267">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-268">TouchFlags</span><span class="sxs-lookup"><span data-stu-id="66397-268">TouchFlags</span></span> 

<span data-ttu-id="66397-269">指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="66397-269">The TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="66397-270">公共 uint [TouchFlags](#touchflags)</span><span class="sxs-lookup"><span data-stu-id="66397-270">public uint [TouchFlags](#touchflags)</span></span>

<span data-ttu-id="66397-271">这对应于 POINTER_TOUCH_INFO 结构的 touchFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-271">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="66397-272">这些值由 Windows SDK 中的 TOUCH_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="66397-272">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-273">TouchMask</span><span class="sxs-lookup"><span data-stu-id="66397-273">TouchMask</span></span> 

<span data-ttu-id="66397-274">指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="66397-274">The TouchMask of the pointer event.</span></span>

> <span data-ttu-id="66397-275">公共 uint [TouchMask](#touchmask)</span><span class="sxs-lookup"><span data-stu-id="66397-275">public uint [TouchMask](#touchmask)</span></span>

<span data-ttu-id="66397-276">这对应于 POINTER_TOUCH_INFO 结构的 touchMask 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-276">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="66397-277">这些值由 Windows SDK 中的 TOUCH_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="66397-277">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-278">TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="66397-278">TouchOrientation</span></span> 

<span data-ttu-id="66397-279">指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="66397-279">The TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="66397-280">公共 uint [TouchOrientation](#touchorientation)</span><span class="sxs-lookup"><span data-stu-id="66397-280">public uint [TouchOrientation](#touchorientation)</span></span>

<span data-ttu-id="66397-281">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 "方向" 属性。</span><span class="sxs-lookup"><span data-stu-id="66397-281">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="66397-282">TouchPressure</span><span class="sxs-lookup"><span data-stu-id="66397-282">TouchPressure</span></span> 

<span data-ttu-id="66397-283">指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="66397-283">The TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="66397-284">公共 uint [TouchPressure](#touchpressure)</span><span class="sxs-lookup"><span data-stu-id="66397-284">public uint [TouchPressure](#touchpressure)</span></span>

<span data-ttu-id="66397-285">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="66397-285">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

