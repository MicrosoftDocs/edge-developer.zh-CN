---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2。 CoreWebView2PointerInfo
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 9ce4c9c3f076d54f03295ffda84c5fb0f03b4166
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010899"
---
# <span data-ttu-id="6a596-104">0.9.579-WebView2 的 CoreWebView2PointerInfo 类</span><span class="sxs-lookup"><span data-stu-id="6a596-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2PointerInfo class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="6a596-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="6a596-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="6a596-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="6a596-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="6a596-107">这通常表示一个组合的 win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO 对象。</span><span class="sxs-lookup"><span data-stu-id="6a596-107">This mostly represents a combined win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO object.</span></span>

## <span data-ttu-id="6a596-108">摘要</span><span class="sxs-lookup"><span data-stu-id="6a596-108">Summary</span></span>

 <span data-ttu-id="6a596-109">成员</span><span class="sxs-lookup"><span data-stu-id="6a596-109">Members</span></span>                        | <span data-ttu-id="6a596-110">描述</span><span class="sxs-lookup"><span data-stu-id="6a596-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6a596-111">ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="6a596-111">ButtonChangeKind</span></span>](#buttonchangekind) | <span data-ttu-id="6a596-112">指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="6a596-112">The ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="6a596-113">DisplayRect</span><span class="sxs-lookup"><span data-stu-id="6a596-113">DisplayRect</span></span>](#displayrect) | <span data-ttu-id="6a596-114">在 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="6a596-114">The DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="6a596-115">FrameId</span><span class="sxs-lookup"><span data-stu-id="6a596-115">FrameId</span></span>](#frameid) | <span data-ttu-id="6a596-116">指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="6a596-116">The FrameID of the pointer event.</span></span>
[<span data-ttu-id="6a596-117">HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="6a596-117">HimetricLocation</span></span>](#himetriclocation) | <span data-ttu-id="6a596-118">指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="6a596-118">The HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="6a596-119">HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="6a596-119">HimetricLocationRaw</span></span>](#himetriclocationraw) | <span data-ttu-id="6a596-120">指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="6a596-120">The HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="6a596-121">HistoryCount</span><span class="sxs-lookup"><span data-stu-id="6a596-121">HistoryCount</span></span>](#historycount) | <span data-ttu-id="6a596-122">指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="6a596-122">The HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="6a596-123">InputData</span><span class="sxs-lookup"><span data-stu-id="6a596-123">InputData</span></span>](#inputdata) | <span data-ttu-id="6a596-124">指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="6a596-124">The InputData of the pointer event.</span></span>
[<span data-ttu-id="6a596-125">KeyStates</span><span class="sxs-lookup"><span data-stu-id="6a596-125">KeyStates</span></span>](#keystates) | <span data-ttu-id="6a596-126">指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="6a596-126">The KeyStates of the pointer event.</span></span>
[<span data-ttu-id="6a596-127">PenFlags</span><span class="sxs-lookup"><span data-stu-id="6a596-127">PenFlags</span></span>](#penflags) | <span data-ttu-id="6a596-128">指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="6a596-128">The PenFlags of the pointer event.</span></span>
[<span data-ttu-id="6a596-129">PenMask</span><span class="sxs-lookup"><span data-stu-id="6a596-129">PenMask</span></span>](#penmask) | <span data-ttu-id="6a596-130">指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="6a596-130">The PenMask of the pointer event.</span></span>
[<span data-ttu-id="6a596-131">PenPressure</span><span class="sxs-lookup"><span data-stu-id="6a596-131">PenPressure</span></span>](#penpressure) | <span data-ttu-id="6a596-132">指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="6a596-132">The PenPressure of the pointer event.</span></span>
[<span data-ttu-id="6a596-133">PenRotation</span><span class="sxs-lookup"><span data-stu-id="6a596-133">PenRotation</span></span>](#penrotation) | <span data-ttu-id="6a596-134">指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="6a596-134">The PenRotation of the pointer event.</span></span>
[<span data-ttu-id="6a596-135">PenTiltX</span><span class="sxs-lookup"><span data-stu-id="6a596-135">PenTiltX</span></span>](#pentiltx) | <span data-ttu-id="6a596-136">指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="6a596-136">The PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="6a596-137">PenTiltY</span><span class="sxs-lookup"><span data-stu-id="6a596-137">PenTiltY</span></span>](#pentilty) | <span data-ttu-id="6a596-138">指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="6a596-138">The PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="6a596-139">PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="6a596-139">PerformanceCount</span></span>](#performancecount) | <span data-ttu-id="6a596-140">指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="6a596-140">The PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="6a596-141">PixelLocation</span><span class="sxs-lookup"><span data-stu-id="6a596-141">PixelLocation</span></span>](#pixellocation) | <span data-ttu-id="6a596-142">指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="6a596-142">The PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="6a596-143">PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="6a596-143">PixelLocationRaw</span></span>](#pixellocationraw) | <span data-ttu-id="6a596-144">指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="6a596-144">The PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="6a596-145">PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="6a596-145">PointerDeviceRect</span></span>](#pointerdevicerect) | <span data-ttu-id="6a596-146">在 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="6a596-146">The PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="6a596-147">PointerFlags</span><span class="sxs-lookup"><span data-stu-id="6a596-147">PointerFlags</span></span>](#pointerflags) | <span data-ttu-id="6a596-148">指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="6a596-148">The PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="6a596-149">PointerId</span><span class="sxs-lookup"><span data-stu-id="6a596-149">PointerId</span></span>](#pointerid) | <span data-ttu-id="6a596-150">指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="6a596-150">The PointerId of the pointer event.</span></span>
[<span data-ttu-id="6a596-151">PointerKind</span><span class="sxs-lookup"><span data-stu-id="6a596-151">PointerKind</span></span>](#pointerkind) | <span data-ttu-id="6a596-152">指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="6a596-152">The PointerKind of the pointer event.</span></span>
[<span data-ttu-id="6a596-153">时间</span><span class="sxs-lookup"><span data-stu-id="6a596-153">Time</span></span>](#time) | <span data-ttu-id="6a596-154">指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="6a596-154">The Time of the pointer event.</span></span>
[<span data-ttu-id="6a596-155">TouchContact</span><span class="sxs-lookup"><span data-stu-id="6a596-155">TouchContact</span></span>](#touchcontact) | <span data-ttu-id="6a596-156">指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="6a596-156">The TouchContact of the pointer event.</span></span>
[<span data-ttu-id="6a596-157">TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="6a596-157">TouchContactRaw</span></span>](#touchcontactraw) | <span data-ttu-id="6a596-158">指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="6a596-158">The TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="6a596-159">TouchFlags</span><span class="sxs-lookup"><span data-stu-id="6a596-159">TouchFlags</span></span>](#touchflags) | <span data-ttu-id="6a596-160">指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="6a596-160">The TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="6a596-161">TouchMask</span><span class="sxs-lookup"><span data-stu-id="6a596-161">TouchMask</span></span>](#touchmask) | <span data-ttu-id="6a596-162">指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="6a596-162">The TouchMask of the pointer event.</span></span>
[<span data-ttu-id="6a596-163">TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="6a596-163">TouchOrientation</span></span>](#touchorientation) | <span data-ttu-id="6a596-164">指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="6a596-164">The TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="6a596-165">TouchPressure</span><span class="sxs-lookup"><span data-stu-id="6a596-165">TouchPressure</span></span>](#touchpressure) | <span data-ttu-id="6a596-166">指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="6a596-166">The TouchPressure of the pointer event.</span></span>

## <span data-ttu-id="6a596-167">成员</span><span class="sxs-lookup"><span data-stu-id="6a596-167">Members</span></span>

#### <span data-ttu-id="6a596-168">ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="6a596-168">ButtonChangeKind</span></span> 

<span data-ttu-id="6a596-169">指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="6a596-169">The ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="6a596-170">公共 int [ButtonChangeKind](#buttonchangekind)</span><span class="sxs-lookup"><span data-stu-id="6a596-170">public int [ButtonChangeKind](#buttonchangekind)</span></span>

<span data-ttu-id="6a596-171">这对应于 POINTER_INFO 结构的 ButtonChangeKind 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-171">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="6a596-172">这些值由 Windows SDK 中的 POINTER_BUTTON_CHANGE_KIND 枚举 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="6a596-172">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-173">DisplayRect</span><span class="sxs-lookup"><span data-stu-id="6a596-173">DisplayRect</span></span> 

<span data-ttu-id="6a596-174">在 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="6a596-174">The DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="6a596-175">公共矩形 [DisplayRect](#displayrect)</span><span class="sxs-lookup"><span data-stu-id="6a596-175">public Rect [DisplayRect](#displayrect)</span></span>

#### <span data-ttu-id="6a596-176">FrameId</span><span class="sxs-lookup"><span data-stu-id="6a596-176">FrameId</span></span> 

<span data-ttu-id="6a596-177">指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="6a596-177">The FrameID of the pointer event.</span></span>

> <span data-ttu-id="6a596-178">公共 uint [FrameId](#frameid)</span><span class="sxs-lookup"><span data-stu-id="6a596-178">public uint [FrameId](#frameid)</span></span>

<span data-ttu-id="6a596-179">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 frameId 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-179">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-180">HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="6a596-180">HimetricLocation</span></span> 

<span data-ttu-id="6a596-181">指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="6a596-181">The HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="6a596-182">公共点 [HimetricLocation](#himetriclocation)</span><span class="sxs-lookup"><span data-stu-id="6a596-182">public Point [HimetricLocation](#himetriclocation)</span></span>

<span data-ttu-id="6a596-183">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptHimetricLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-183">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-184">HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="6a596-184">HimetricLocationRaw</span></span> 

<span data-ttu-id="6a596-185">指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="6a596-185">The HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="6a596-186">公共点 [HimetricLocationRaw](#himetriclocationraw)</span><span class="sxs-lookup"><span data-stu-id="6a596-186">public Point [HimetricLocationRaw](#himetriclocationraw)</span></span>

<span data-ttu-id="6a596-187">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptHimetricLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-187">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-188">HistoryCount</span><span class="sxs-lookup"><span data-stu-id="6a596-188">HistoryCount</span></span> 

<span data-ttu-id="6a596-189">指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="6a596-189">The HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="6a596-190">公共 uint [HistoryCount](#historycount)</span><span class="sxs-lookup"><span data-stu-id="6a596-190">public uint [HistoryCount](#historycount)</span></span>

<span data-ttu-id="6a596-191">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 historyCount 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-191">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-192">InputData</span><span class="sxs-lookup"><span data-stu-id="6a596-192">InputData</span></span> 

<span data-ttu-id="6a596-193">指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="6a596-193">The InputData of the pointer event.</span></span>

> <span data-ttu-id="6a596-194">公共 int [InputData](#inputdata)</span><span class="sxs-lookup"><span data-stu-id="6a596-194">public int [InputData](#inputdata)</span></span>

<span data-ttu-id="6a596-195">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 InputData 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-195">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-196">KeyStates</span><span class="sxs-lookup"><span data-stu-id="6a596-196">KeyStates</span></span> 

<span data-ttu-id="6a596-197">指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="6a596-197">The KeyStates of the pointer event.</span></span>

> <span data-ttu-id="6a596-198">公共 uint [KeyStates](#keystates)</span><span class="sxs-lookup"><span data-stu-id="6a596-198">public uint [KeyStates](#keystates)</span></span>

<span data-ttu-id="6a596-199">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 dwKeyStates 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-199">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-200">PenFlags</span><span class="sxs-lookup"><span data-stu-id="6a596-200">PenFlags</span></span> 

<span data-ttu-id="6a596-201">指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="6a596-201">The PenFlags of the pointer event.</span></span>

> <span data-ttu-id="6a596-202">公共 uint [PenFlags](#penflags)</span><span class="sxs-lookup"><span data-stu-id="6a596-202">public uint [PenFlags](#penflags)</span></span>

<span data-ttu-id="6a596-203">这对应于 POINTER_PEN_INFO 结构的 penFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-203">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="6a596-204">这些值由 Windows SDK 中的 PEN_FLAGS 常量 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="6a596-204">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-205">PenMask</span><span class="sxs-lookup"><span data-stu-id="6a596-205">PenMask</span></span> 

<span data-ttu-id="6a596-206">指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="6a596-206">The PenMask of the pointer event.</span></span>

> <span data-ttu-id="6a596-207">公共 uint [PenMask](#penmask)</span><span class="sxs-lookup"><span data-stu-id="6a596-207">public uint [PenMask](#penmask)</span></span>

<span data-ttu-id="6a596-208">这对应于 POINTER_PEN_INFO 结构的 penMask 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-208">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="6a596-209">这些值由 Windows SDK 中的 PEN_MASK 常量 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="6a596-209">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-210">PenPressure</span><span class="sxs-lookup"><span data-stu-id="6a596-210">PenPressure</span></span> 

<span data-ttu-id="6a596-211">指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="6a596-211">The PenPressure of the pointer event.</span></span>

> <span data-ttu-id="6a596-212">公共 uint [PenPressure](#penpressure)</span><span class="sxs-lookup"><span data-stu-id="6a596-212">public uint [PenPressure](#penpressure)</span></span>

<span data-ttu-id="6a596-213">这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-213">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-214">PenRotation</span><span class="sxs-lookup"><span data-stu-id="6a596-214">PenRotation</span></span> 

<span data-ttu-id="6a596-215">指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="6a596-215">The PenRotation of the pointer event.</span></span>

> <span data-ttu-id="6a596-216">公共 uint [PenRotation](#penrotation)</span><span class="sxs-lookup"><span data-stu-id="6a596-216">public uint [PenRotation](#penrotation)</span></span>

<span data-ttu-id="6a596-217">这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的旋转属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-217">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-218">PenTiltX</span><span class="sxs-lookup"><span data-stu-id="6a596-218">PenTiltX</span></span> 

<span data-ttu-id="6a596-219">指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="6a596-219">The PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="6a596-220">公共 int [PenTiltX](#pentiltx)</span><span class="sxs-lookup"><span data-stu-id="6a596-220">public int [PenTiltX](#pentiltx)</span></span>

<span data-ttu-id="6a596-221">这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的 tiltX 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-221">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-222">PenTiltY</span><span class="sxs-lookup"><span data-stu-id="6a596-222">PenTiltY</span></span> 

<span data-ttu-id="6a596-223">指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="6a596-223">The PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="6a596-224">公共 int [PenTiltY](#pentilty)</span><span class="sxs-lookup"><span data-stu-id="6a596-224">public int [PenTiltY](#pentilty)</span></span>

<span data-ttu-id="6a596-225">这对应于 Windows SDK (winuser) 中定义的 POINTER_PEN_INFO 结构的 tiltY 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-225">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-226">PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="6a596-226">PerformanceCount</span></span> 

<span data-ttu-id="6a596-227">指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="6a596-227">The PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="6a596-228">公共 ulong [PerformanceCount](#performancecount)</span><span class="sxs-lookup"><span data-stu-id="6a596-228">public ulong [PerformanceCount](#performancecount)</span></span>

<span data-ttu-id="6a596-229">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 PerformanceCount 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-229">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-230">PixelLocation</span><span class="sxs-lookup"><span data-stu-id="6a596-230">PixelLocation</span></span> 

<span data-ttu-id="6a596-231">指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="6a596-231">The PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="6a596-232">公共点 [PixelLocation](#pixellocation)</span><span class="sxs-lookup"><span data-stu-id="6a596-232">public Point [PixelLocation](#pixellocation)</span></span>

<span data-ttu-id="6a596-233">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptPixelLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-233">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-234">PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="6a596-234">PixelLocationRaw</span></span> 

<span data-ttu-id="6a596-235">指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="6a596-235">The PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="6a596-236">公共点 [PixelLocationRaw](#pixellocationraw)</span><span class="sxs-lookup"><span data-stu-id="6a596-236">public Point [PixelLocationRaw](#pixellocationraw)</span></span>

<span data-ttu-id="6a596-237">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 ptPixelLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-237">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-238">PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="6a596-238">PointerDeviceRect</span></span> 

<span data-ttu-id="6a596-239">在 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="6a596-239">The PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="6a596-240">公共矩形 [PointerDeviceRect](#pointerdevicerect)</span><span class="sxs-lookup"><span data-stu-id="6a596-240">public Rect [PointerDeviceRect](#pointerdevicerect)</span></span>

#### <span data-ttu-id="6a596-241">PointerFlags</span><span class="sxs-lookup"><span data-stu-id="6a596-241">PointerFlags</span></span> 

<span data-ttu-id="6a596-242">指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="6a596-242">The PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="6a596-243">公共 uint [PointerFlags](#pointerflags)</span><span class="sxs-lookup"><span data-stu-id="6a596-243">public uint [PointerFlags](#pointerflags)</span></span>

<span data-ttu-id="6a596-244">这对应于 POINTER_INFO 结构的 pointerFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-244">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="6a596-245">这些值由 Windows SDK 中的 POINTER_FLAGS 常量 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="6a596-245">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-246">PointerId</span><span class="sxs-lookup"><span data-stu-id="6a596-246">PointerId</span></span> 

<span data-ttu-id="6a596-247">指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="6a596-247">The PointerId of the pointer event.</span></span>

> <span data-ttu-id="6a596-248">公共 uint [PointerId](#pointerid)</span><span class="sxs-lookup"><span data-stu-id="6a596-248">public uint [PointerId](#pointerid)</span></span>

<span data-ttu-id="6a596-249">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 pointerId 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-249">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-250">PointerKind</span><span class="sxs-lookup"><span data-stu-id="6a596-250">PointerKind</span></span> 

<span data-ttu-id="6a596-251">指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="6a596-251">The PointerKind of the pointer event.</span></span>

> <span data-ttu-id="6a596-252">公共 uint [PointerKind](#pointerkind)</span><span class="sxs-lookup"><span data-stu-id="6a596-252">public uint [PointerKind](#pointerkind)</span></span>

<span data-ttu-id="6a596-253">这对应于 POINTER_INFO 结构的 pointerKind 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-253">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="6a596-254">这些值由 Windows SDK 中的 POINTER_INPUT_KIND 枚举 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="6a596-254">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="6a596-255">支持 PT_PEN 和 PT_TOUCH。</span><span class="sxs-lookup"><span data-stu-id="6a596-255">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="6a596-256">时间</span><span class="sxs-lookup"><span data-stu-id="6a596-256">Time</span></span> 

<span data-ttu-id="6a596-257">指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="6a596-257">The Time of the pointer event.</span></span>

> <span data-ttu-id="6a596-258">公共 uint [时间](#time)</span><span class="sxs-lookup"><span data-stu-id="6a596-258">public uint [Time](#time)</span></span>

<span data-ttu-id="6a596-259">这对应于 Windows SDK (winuser) 中定义的 POINTER_INFO 结构的 dwTime 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-259">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-260">TouchContact</span><span class="sxs-lookup"><span data-stu-id="6a596-260">TouchContact</span></span> 

<span data-ttu-id="6a596-261">指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="6a596-261">The TouchContact of the pointer event.</span></span>

> <span data-ttu-id="6a596-262">公共矩形 [TouchContact](#touchcontact)</span><span class="sxs-lookup"><span data-stu-id="6a596-262">public Rect [TouchContact](#touchcontact)</span></span>

<span data-ttu-id="6a596-263">这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的 rcContact 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-263">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-264">TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="6a596-264">TouchContactRaw</span></span> 

<span data-ttu-id="6a596-265">指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="6a596-265">The TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="6a596-266">公共矩形 [TouchContactRaw](#touchcontactraw)</span><span class="sxs-lookup"><span data-stu-id="6a596-266">public Rect [TouchContactRaw](#touchcontactraw)</span></span>

<span data-ttu-id="6a596-267">这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的 rcContactRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-267">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-268">TouchFlags</span><span class="sxs-lookup"><span data-stu-id="6a596-268">TouchFlags</span></span> 

<span data-ttu-id="6a596-269">指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="6a596-269">The TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="6a596-270">公共 uint [TouchFlags](#touchflags)</span><span class="sxs-lookup"><span data-stu-id="6a596-270">public uint [TouchFlags](#touchflags)</span></span>

<span data-ttu-id="6a596-271">这对应于 POINTER_TOUCH_INFO 结构的 touchFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-271">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="6a596-272">这些值由 Windows SDK 中的 TOUCH_FLAGS 常量 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="6a596-272">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-273">TouchMask</span><span class="sxs-lookup"><span data-stu-id="6a596-273">TouchMask</span></span> 

<span data-ttu-id="6a596-274">指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="6a596-274">The TouchMask of the pointer event.</span></span>

> <span data-ttu-id="6a596-275">公共 uint [TouchMask](#touchmask)</span><span class="sxs-lookup"><span data-stu-id="6a596-275">public uint [TouchMask](#touchmask)</span></span>

<span data-ttu-id="6a596-276">这对应于 POINTER_TOUCH_INFO 结构的 touchMask 属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-276">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="6a596-277">这些值由 Windows SDK 中的 TOUCH_MASK 常量 (winuser) 定义。</span><span class="sxs-lookup"><span data-stu-id="6a596-277">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-278">TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="6a596-278">TouchOrientation</span></span> 

<span data-ttu-id="6a596-279">指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="6a596-279">The TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="6a596-280">公共 uint [TouchOrientation](#touchorientation)</span><span class="sxs-lookup"><span data-stu-id="6a596-280">public uint [TouchOrientation](#touchorientation)</span></span>

<span data-ttu-id="6a596-281">这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的方向属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-281">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="6a596-282">TouchPressure</span><span class="sxs-lookup"><span data-stu-id="6a596-282">TouchPressure</span></span> 

<span data-ttu-id="6a596-283">指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="6a596-283">The TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="6a596-284">公共 uint [TouchPressure](#touchpressure)</span><span class="sxs-lookup"><span data-stu-id="6a596-284">public uint [TouchPressure](#touchpressure)</span></span>

<span data-ttu-id="6a596-285">这对应于 Windows SDK (winuser) 中定义的 POINTER_TOUCH_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="6a596-285">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

