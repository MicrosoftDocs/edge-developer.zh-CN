---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2PointerInfo 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 8a5e5f4188b5115e1c6b836f80aad69c4bf2da7e
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878755"
---
# <span data-ttu-id="5e0dc-104">CoreWebView2PointerInfo 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="5e0dc-104">Microsoft.Web.WebView2.Core.CoreWebView2PointerInfo class</span></span> 

<span data-ttu-id="5e0dc-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="5e0dc-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="5e0dc-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="5e0dc-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="5e0dc-107">这通常表示一个组合的 win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO 对象。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-107">This mostly represents a combined win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO object.</span></span>

## <span data-ttu-id="5e0dc-108">摘要</span><span class="sxs-lookup"><span data-stu-id="5e0dc-108">Summary</span></span>

 <span data-ttu-id="5e0dc-109">成员</span><span class="sxs-lookup"><span data-stu-id="5e0dc-109">Members</span></span>                        | <span data-ttu-id="5e0dc-110">描述</span><span class="sxs-lookup"><span data-stu-id="5e0dc-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5e0dc-111">ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="5e0dc-111">ButtonChangeKind</span></span>](#buttonchangekind) | <span data-ttu-id="5e0dc-112">指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-112">The ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-113">DisplayRect</span><span class="sxs-lookup"><span data-stu-id="5e0dc-113">DisplayRect</span></span>](#displayrect) | <span data-ttu-id="5e0dc-114">在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-114">The DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="5e0dc-115">FrameId</span><span class="sxs-lookup"><span data-stu-id="5e0dc-115">FrameId</span></span>](#frameid) | <span data-ttu-id="5e0dc-116">指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-116">The FrameID of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-117">HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="5e0dc-117">HimetricLocation</span></span>](#himetriclocation) | <span data-ttu-id="5e0dc-118">指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-118">The HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-119">HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="5e0dc-119">HimetricLocationRaw</span></span>](#himetriclocationraw) | <span data-ttu-id="5e0dc-120">指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-120">The HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-121">HistoryCount</span><span class="sxs-lookup"><span data-stu-id="5e0dc-121">HistoryCount</span></span>](#historycount) | <span data-ttu-id="5e0dc-122">指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-122">The HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-123">InputData</span><span class="sxs-lookup"><span data-stu-id="5e0dc-123">InputData</span></span>](#inputdata) | <span data-ttu-id="5e0dc-124">指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-124">The InputData of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-125">KeyStates</span><span class="sxs-lookup"><span data-stu-id="5e0dc-125">KeyStates</span></span>](#keystates) | <span data-ttu-id="5e0dc-126">指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-126">The KeyStates of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-127">PenFlags</span><span class="sxs-lookup"><span data-stu-id="5e0dc-127">PenFlags</span></span>](#penflags) | <span data-ttu-id="5e0dc-128">指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-128">The PenFlags of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-129">PenMask</span><span class="sxs-lookup"><span data-stu-id="5e0dc-129">PenMask</span></span>](#penmask) | <span data-ttu-id="5e0dc-130">指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-130">The PenMask of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-131">PenPressure</span><span class="sxs-lookup"><span data-stu-id="5e0dc-131">PenPressure</span></span>](#penpressure) | <span data-ttu-id="5e0dc-132">指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-132">The PenPressure of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-133">PenRotation</span><span class="sxs-lookup"><span data-stu-id="5e0dc-133">PenRotation</span></span>](#penrotation) | <span data-ttu-id="5e0dc-134">指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-134">The PenRotation of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-135">PenTiltX</span><span class="sxs-lookup"><span data-stu-id="5e0dc-135">PenTiltX</span></span>](#pentiltx) | <span data-ttu-id="5e0dc-136">指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-136">The PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-137">PenTiltY</span><span class="sxs-lookup"><span data-stu-id="5e0dc-137">PenTiltY</span></span>](#pentilty) | <span data-ttu-id="5e0dc-138">指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-138">The PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-139">PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="5e0dc-139">PerformanceCount</span></span>](#performancecount) | <span data-ttu-id="5e0dc-140">指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-140">The PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-141">PixelLocation</span><span class="sxs-lookup"><span data-stu-id="5e0dc-141">PixelLocation</span></span>](#pixellocation) | <span data-ttu-id="5e0dc-142">指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-142">The PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-143">PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="5e0dc-143">PixelLocationRaw</span></span>](#pixellocationraw) | <span data-ttu-id="5e0dc-144">指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-144">The PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-145">PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="5e0dc-145">PointerDeviceRect</span></span>](#pointerdevicerect) | <span data-ttu-id="5e0dc-146">在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-146">The PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="5e0dc-147">PointerFlags</span><span class="sxs-lookup"><span data-stu-id="5e0dc-147">PointerFlags</span></span>](#pointerflags) | <span data-ttu-id="5e0dc-148">指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-148">The PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-149">PointerId</span><span class="sxs-lookup"><span data-stu-id="5e0dc-149">PointerId</span></span>](#pointerid) | <span data-ttu-id="5e0dc-150">指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-150">The PointerId of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-151">PointerKind</span><span class="sxs-lookup"><span data-stu-id="5e0dc-151">PointerKind</span></span>](#pointerkind) | <span data-ttu-id="5e0dc-152">指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-152">The PointerKind of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-153">时间</span><span class="sxs-lookup"><span data-stu-id="5e0dc-153">Time</span></span>](#time) | <span data-ttu-id="5e0dc-154">指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-154">The Time of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-155">TouchContact</span><span class="sxs-lookup"><span data-stu-id="5e0dc-155">TouchContact</span></span>](#touchcontact) | <span data-ttu-id="5e0dc-156">指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-156">The TouchContact of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-157">TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="5e0dc-157">TouchContactRaw</span></span>](#touchcontactraw) | <span data-ttu-id="5e0dc-158">指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-158">The TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-159">TouchFlags</span><span class="sxs-lookup"><span data-stu-id="5e0dc-159">TouchFlags</span></span>](#touchflags) | <span data-ttu-id="5e0dc-160">指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-160">The TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-161">TouchMask</span><span class="sxs-lookup"><span data-stu-id="5e0dc-161">TouchMask</span></span>](#touchmask) | <span data-ttu-id="5e0dc-162">指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-162">The TouchMask of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-163">TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="5e0dc-163">TouchOrientation</span></span>](#touchorientation) | <span data-ttu-id="5e0dc-164">指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-164">The TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="5e0dc-165">TouchPressure</span><span class="sxs-lookup"><span data-stu-id="5e0dc-165">TouchPressure</span></span>](#touchpressure) | <span data-ttu-id="5e0dc-166">指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-166">The TouchPressure of the pointer event.</span></span>

## <span data-ttu-id="5e0dc-167">成员</span><span class="sxs-lookup"><span data-stu-id="5e0dc-167">Members</span></span>

#### <span data-ttu-id="5e0dc-168">ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="5e0dc-168">ButtonChangeKind</span></span> 

<span data-ttu-id="5e0dc-169">指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-169">The ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-170">公共 int [ButtonChangeKind](#buttonchangekind)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-170">public int [ButtonChangeKind](#buttonchangekind)</span></span>

<span data-ttu-id="5e0dc-171">这对应于 POINTER_INFO 结构的 ButtonChangeKind 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-171">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="5e0dc-172">这些值由 Windows SDK 中的 POINTER_BUTTON_CHANGE_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-172">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-173">DisplayRect</span><span class="sxs-lookup"><span data-stu-id="5e0dc-173">DisplayRect</span></span> 

<span data-ttu-id="5e0dc-174">在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-174">The DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="5e0dc-175">公共矩形[DisplayRect](#displayrect)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-175">public Rect [DisplayRect](#displayrect)</span></span>

#### <span data-ttu-id="5e0dc-176">FrameId</span><span class="sxs-lookup"><span data-stu-id="5e0dc-176">FrameId</span></span> 

<span data-ttu-id="5e0dc-177">指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-177">The FrameID of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-178">公共 uint [FrameId](#frameid)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-178">public uint [FrameId](#frameid)</span></span>

<span data-ttu-id="5e0dc-179">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 frameId 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-179">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-180">HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="5e0dc-180">HimetricLocation</span></span> 

<span data-ttu-id="5e0dc-181">指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-181">The HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-182">公共点[HimetricLocation](#himetriclocation)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-182">public Point [HimetricLocation](#himetriclocation)</span></span>

<span data-ttu-id="5e0dc-183">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-183">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-184">HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="5e0dc-184">HimetricLocationRaw</span></span> 

<span data-ttu-id="5e0dc-185">指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-185">The HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-186">公共点[HimetricLocationRaw](#himetriclocationraw)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-186">public Point [HimetricLocationRaw](#himetriclocationraw)</span></span>

<span data-ttu-id="5e0dc-187">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-187">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-188">HistoryCount</span><span class="sxs-lookup"><span data-stu-id="5e0dc-188">HistoryCount</span></span> 

<span data-ttu-id="5e0dc-189">指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-189">The HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-190">公共 uint [HistoryCount](#historycount)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-190">public uint [HistoryCount](#historycount)</span></span>

<span data-ttu-id="5e0dc-191">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 historyCount 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-191">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-192">InputData</span><span class="sxs-lookup"><span data-stu-id="5e0dc-192">InputData</span></span> 

<span data-ttu-id="5e0dc-193">指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-193">The InputData of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-194">公共 int [InputData](#inputdata)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-194">public int [InputData](#inputdata)</span></span>

<span data-ttu-id="5e0dc-195">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 InputData 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-195">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-196">KeyStates</span><span class="sxs-lookup"><span data-stu-id="5e0dc-196">KeyStates</span></span> 

<span data-ttu-id="5e0dc-197">指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-197">The KeyStates of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-198">公共 uint [KeyStates](#keystates)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-198">public uint [KeyStates](#keystates)</span></span>

<span data-ttu-id="5e0dc-199">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwKeyStates 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-199">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-200">PenFlags</span><span class="sxs-lookup"><span data-stu-id="5e0dc-200">PenFlags</span></span> 

<span data-ttu-id="5e0dc-201">指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-201">The PenFlags of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-202">公共 uint [PenFlags](#penflags)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-202">public uint [PenFlags](#penflags)</span></span>

<span data-ttu-id="5e0dc-203">这对应于 POINTER_PEN_INFO 结构的 penFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-203">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="5e0dc-204">这些值由 Windows SDK 中的 PEN_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-204">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-205">PenMask</span><span class="sxs-lookup"><span data-stu-id="5e0dc-205">PenMask</span></span> 

<span data-ttu-id="5e0dc-206">指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-206">The PenMask of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-207">公共 uint [PenMask](#penmask)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-207">public uint [PenMask](#penmask)</span></span>

<span data-ttu-id="5e0dc-208">这对应于 POINTER_PEN_INFO 结构的 penMask 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-208">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="5e0dc-209">这些值由 Windows SDK 中的 PEN_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-209">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-210">PenPressure</span><span class="sxs-lookup"><span data-stu-id="5e0dc-210">PenPressure</span></span> 

<span data-ttu-id="5e0dc-211">指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-211">The PenPressure of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-212">公共 uint [PenPressure](#penpressure)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-212">public uint [PenPressure](#penpressure)</span></span>

<span data-ttu-id="5e0dc-213">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-213">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-214">PenRotation</span><span class="sxs-lookup"><span data-stu-id="5e0dc-214">PenRotation</span></span> 

<span data-ttu-id="5e0dc-215">指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-215">The PenRotation of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-216">公共 uint [PenRotation](#penrotation)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-216">public uint [PenRotation](#penrotation)</span></span>

<span data-ttu-id="5e0dc-217">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的旋转属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-217">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-218">PenTiltX</span><span class="sxs-lookup"><span data-stu-id="5e0dc-218">PenTiltX</span></span> 

<span data-ttu-id="5e0dc-219">指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-219">The PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-220">公共 int [PenTiltX](#pentiltx)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-220">public int [PenTiltX](#pentiltx)</span></span>

<span data-ttu-id="5e0dc-221">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltX 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-221">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-222">PenTiltY</span><span class="sxs-lookup"><span data-stu-id="5e0dc-222">PenTiltY</span></span> 

<span data-ttu-id="5e0dc-223">指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-223">The PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-224">公共 int [PenTiltY](#pentilty)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-224">public int [PenTiltY](#pentilty)</span></span>

<span data-ttu-id="5e0dc-225">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltY 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-225">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-226">PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="5e0dc-226">PerformanceCount</span></span> 

<span data-ttu-id="5e0dc-227">指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-227">The PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-228">公共 ulong [PerformanceCount](#performancecount)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-228">public ulong [PerformanceCount](#performancecount)</span></span>

<span data-ttu-id="5e0dc-229">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 PerformanceCount 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-229">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-230">PixelLocation</span><span class="sxs-lookup"><span data-stu-id="5e0dc-230">PixelLocation</span></span> 

<span data-ttu-id="5e0dc-231">指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-231">The PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-232">公共点[PixelLocation](#pixellocation)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-232">public Point [PixelLocation](#pixellocation)</span></span>

<span data-ttu-id="5e0dc-233">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-233">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-234">PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="5e0dc-234">PixelLocationRaw</span></span> 

<span data-ttu-id="5e0dc-235">指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-235">The PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-236">公共点[PixelLocationRaw](#pixellocationraw)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-236">public Point [PixelLocationRaw](#pixellocationraw)</span></span>

<span data-ttu-id="5e0dc-237">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-237">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-238">PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="5e0dc-238">PointerDeviceRect</span></span> 

<span data-ttu-id="5e0dc-239">在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-239">The PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="5e0dc-240">公共矩形[PointerDeviceRect](#pointerdevicerect)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-240">public Rect [PointerDeviceRect](#pointerdevicerect)</span></span>

#### <span data-ttu-id="5e0dc-241">PointerFlags</span><span class="sxs-lookup"><span data-stu-id="5e0dc-241">PointerFlags</span></span> 

<span data-ttu-id="5e0dc-242">指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-242">The PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-243">公共 uint [PointerFlags](#pointerflags)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-243">public uint [PointerFlags](#pointerflags)</span></span>

<span data-ttu-id="5e0dc-244">这对应于 POINTER_INFO 结构的 pointerFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-244">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="5e0dc-245">这些值由 Windows SDK 中的 POINTER_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-245">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-246">PointerId</span><span class="sxs-lookup"><span data-stu-id="5e0dc-246">PointerId</span></span> 

<span data-ttu-id="5e0dc-247">指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-247">The PointerId of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-248">公共 uint [PointerId](#pointerid)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-248">public uint [PointerId](#pointerid)</span></span>

<span data-ttu-id="5e0dc-249">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 pointerId 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-249">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-250">PointerKind</span><span class="sxs-lookup"><span data-stu-id="5e0dc-250">PointerKind</span></span> 

<span data-ttu-id="5e0dc-251">指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-251">The PointerKind of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-252">公共 uint [PointerKind](#pointerkind)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-252">public uint [PointerKind](#pointerkind)</span></span>

<span data-ttu-id="5e0dc-253">这对应于 POINTER_INFO 结构的 pointerKind 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-253">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="5e0dc-254">这些值由 Windows SDK 中的 POINTER_INPUT_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-254">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="5e0dc-255">支持 PT_PEN 和 PT_TOUCH。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-255">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="5e0dc-256">时间</span><span class="sxs-lookup"><span data-stu-id="5e0dc-256">Time</span></span> 

<span data-ttu-id="5e0dc-257">指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-257">The Time of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-258">公共 uint[时间](#time)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-258">public uint [Time](#time)</span></span>

<span data-ttu-id="5e0dc-259">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwTime 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-259">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-260">TouchContact</span><span class="sxs-lookup"><span data-stu-id="5e0dc-260">TouchContact</span></span> 

<span data-ttu-id="5e0dc-261">指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-261">The TouchContact of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-262">公共矩形[TouchContact](#touchcontact)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-262">public Rect [TouchContact](#touchcontact)</span></span>

<span data-ttu-id="5e0dc-263">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContact 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-263">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-264">TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="5e0dc-264">TouchContactRaw</span></span> 

<span data-ttu-id="5e0dc-265">指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-265">The TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-266">公共矩形[TouchContactRaw](#touchcontactraw)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-266">public Rect [TouchContactRaw](#touchcontactraw)</span></span>

<span data-ttu-id="5e0dc-267">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContactRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-267">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-268">TouchFlags</span><span class="sxs-lookup"><span data-stu-id="5e0dc-268">TouchFlags</span></span> 

<span data-ttu-id="5e0dc-269">指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-269">The TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-270">公共 uint [TouchFlags](#touchflags)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-270">public uint [TouchFlags](#touchflags)</span></span>

<span data-ttu-id="5e0dc-271">这对应于 POINTER_TOUCH_INFO 结构的 touchFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-271">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="5e0dc-272">这些值由 Windows SDK 中的 TOUCH_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-272">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-273">TouchMask</span><span class="sxs-lookup"><span data-stu-id="5e0dc-273">TouchMask</span></span> 

<span data-ttu-id="5e0dc-274">指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-274">The TouchMask of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-275">公共 uint [TouchMask](#touchmask)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-275">public uint [TouchMask](#touchmask)</span></span>

<span data-ttu-id="5e0dc-276">这对应于 POINTER_TOUCH_INFO 结构的 touchMask 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-276">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="5e0dc-277">这些值由 Windows SDK 中的 TOUCH_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-277">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-278">TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="5e0dc-278">TouchOrientation</span></span> 

<span data-ttu-id="5e0dc-279">指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-279">The TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-280">公共 uint [TouchOrientation](#touchorientation)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-280">public uint [TouchOrientation](#touchorientation)</span></span>

<span data-ttu-id="5e0dc-281">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 "方向" 属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-281">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="5e0dc-282">TouchPressure</span><span class="sxs-lookup"><span data-stu-id="5e0dc-282">TouchPressure</span></span> 

<span data-ttu-id="5e0dc-283">指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-283">The TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="5e0dc-284">公共 uint [TouchPressure](#touchpressure)</span><span class="sxs-lookup"><span data-stu-id="5e0dc-284">public uint [TouchPressure](#touchpressure)</span></span>

<span data-ttu-id="5e0dc-285">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="5e0dc-285">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

