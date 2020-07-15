---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ExperimentalPointerInfo
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalPointerInfo
ms.openlocfilehash: b84c822e8b9e01d3b5a0e59baaeed5fc587d9a15
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879945"
---
# <span data-ttu-id="f4237-104">interface ICoreWebView2ExperimentalPointerInfo</span><span class="sxs-lookup"><span data-stu-id="f4237-104">interface ICoreWebView2ExperimentalPointerInfo</span></span> 

> [!NOTE]
> <span data-ttu-id="f4237-105">这是使用预发行 SDK 版本0.9.538 随附的实验性 API。</span><span class="sxs-lookup"><span data-stu-id="f4237-105">This an experimental API that is shipped with our prerelease SDK version 0.9.538.</span></span>

```
interface ICoreWebView2ExperimentalPointerInfo
  : public IUnknown
```

<span data-ttu-id="f4237-106">这通常表示一个组合的 win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO 对象。</span><span class="sxs-lookup"><span data-stu-id="f4237-106">This mostly represents a combined win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO object.</span></span>

## <span data-ttu-id="f4237-107">摘要</span><span class="sxs-lookup"><span data-stu-id="f4237-107">Summary</span></span>

 <span data-ttu-id="f4237-108">成员</span><span class="sxs-lookup"><span data-stu-id="f4237-108">Members</span></span>                        | <span data-ttu-id="f4237-109">描述</span><span class="sxs-lookup"><span data-stu-id="f4237-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f4237-110">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="f4237-110">get_ButtonChangeKind</span></span>](#get_buttonchangekind) | <span data-ttu-id="f4237-111">获取指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="f4237-111">Get the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="f4237-112">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="f4237-112">get_DisplayRect</span></span>](#get_displayrect) | <span data-ttu-id="f4237-113">获取在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="f4237-113">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="f4237-114">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="f4237-114">get_FrameId</span></span>](#get_frameid) | <span data-ttu-id="f4237-115">获取指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="f4237-115">Get the FrameID of the pointer event.</span></span>
[<span data-ttu-id="f4237-116">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="f4237-116">get_HimetricLocation</span></span>](#get_himetriclocation) | <span data-ttu-id="f4237-117">获取指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="f4237-117">Get the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="f4237-118">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="f4237-118">get_HimetricLocationRaw</span></span>](#get_himetriclocationraw) | <span data-ttu-id="f4237-119">获取指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="f4237-119">Get the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="f4237-120">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="f4237-120">get_HistoryCount</span></span>](#get_historycount) | <span data-ttu-id="f4237-121">获取指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="f4237-121">Get the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="f4237-122">get_InputData</span><span class="sxs-lookup"><span data-stu-id="f4237-122">get_InputData</span></span>](#get_inputdata) | <span data-ttu-id="f4237-123">获取指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="f4237-123">Get the InputData of the pointer event.</span></span>
[<span data-ttu-id="f4237-124">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="f4237-124">get_KeyStates</span></span>](#get_keystates) | <span data-ttu-id="f4237-125">获取指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="f4237-125">Get the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="f4237-126">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="f4237-126">get_PenFlags</span></span>](#get_penflags) | <span data-ttu-id="f4237-127">获取指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="f4237-127">Get the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="f4237-128">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="f4237-128">get_PenMask</span></span>](#get_penmask) | <span data-ttu-id="f4237-129">获取指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="f4237-129">Get the PenMask of the pointer event.</span></span>
[<span data-ttu-id="f4237-130">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="f4237-130">get_PenPressure</span></span>](#get_penpressure) | <span data-ttu-id="f4237-131">获取指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="f4237-131">Get the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="f4237-132">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="f4237-132">get_PenRotation</span></span>](#get_penrotation) | <span data-ttu-id="f4237-133">获取指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="f4237-133">Get the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="f4237-134">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="f4237-134">get_PenTiltX</span></span>](#get_pentiltx) | <span data-ttu-id="f4237-135">获取指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="f4237-135">Get the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="f4237-136">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="f4237-136">get_PenTiltY</span></span>](#get_pentilty) | <span data-ttu-id="f4237-137">获取指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="f4237-137">Get the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="f4237-138">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="f4237-138">get_PerformanceCount</span></span>](#get_performancecount) | <span data-ttu-id="f4237-139">获取指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="f4237-139">Get the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="f4237-140">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="f4237-140">get_PixelLocation</span></span>](#get_pixellocation) | <span data-ttu-id="f4237-141">获取指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="f4237-141">Get the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="f4237-142">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="f4237-142">get_PixelLocationRaw</span></span>](#get_pixellocationraw) | <span data-ttu-id="f4237-143">获取指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="f4237-143">Get the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="f4237-144">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="f4237-144">get_PointerDeviceRect</span></span>](#get_pointerdevicerect) | <span data-ttu-id="f4237-145">获取在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="f4237-145">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="f4237-146">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="f4237-146">get_PointerFlags</span></span>](#get_pointerflags) | <span data-ttu-id="f4237-147">获取指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="f4237-147">Get the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="f4237-148">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="f4237-148">get_PointerId</span></span>](#get_pointerid) | <span data-ttu-id="f4237-149">获取指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="f4237-149">Get the PointerId of the pointer event.</span></span>
[<span data-ttu-id="f4237-150">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="f4237-150">get_PointerKind</span></span>](#get_pointerkind) | <span data-ttu-id="f4237-151">获取指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="f4237-151">Get the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="f4237-152">get_Time</span><span class="sxs-lookup"><span data-stu-id="f4237-152">get_Time</span></span>](#get_time) | <span data-ttu-id="f4237-153">获取指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="f4237-153">Get the Time of the pointer event.</span></span>
[<span data-ttu-id="f4237-154">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="f4237-154">get_TouchContact</span></span>](#get_touchcontact) | <span data-ttu-id="f4237-155">获取指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="f4237-155">Get the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="f4237-156">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="f4237-156">get_TouchContactRaw</span></span>](#get_touchcontactraw) | <span data-ttu-id="f4237-157">获取指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="f4237-157">Get the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="f4237-158">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="f4237-158">get_TouchFlags</span></span>](#get_touchflags) | <span data-ttu-id="f4237-159">获取指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="f4237-159">Get the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="f4237-160">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="f4237-160">get_TouchMask</span></span>](#get_touchmask) | <span data-ttu-id="f4237-161">获取指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="f4237-161">Get the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="f4237-162">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="f4237-162">get_TouchOrientation</span></span>](#get_touchorientation) | <span data-ttu-id="f4237-163">获取指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="f4237-163">Get the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="f4237-164">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="f4237-164">get_TouchPressure</span></span>](#get_touchpressure) | <span data-ttu-id="f4237-165">获取指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="f4237-165">Get the TouchPressure of the pointer event.</span></span>
[<span data-ttu-id="f4237-166">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="f4237-166">put_ButtonChangeKind</span></span>](#put_buttonchangekind) | <span data-ttu-id="f4237-167">设置指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="f4237-167">Set the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="f4237-168">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="f4237-168">put_DisplayRect</span></span>](#put_displayrect) | <span data-ttu-id="f4237-169">按照 Windows SDK （winuser）中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="f4237-169">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="f4237-170">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="f4237-170">put_FrameId</span></span>](#put_frameid) | <span data-ttu-id="f4237-171">设置指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="f4237-171">Set the FrameID of the pointer event.</span></span>
[<span data-ttu-id="f4237-172">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="f4237-172">put_HimetricLocation</span></span>](#put_himetriclocation) | <span data-ttu-id="f4237-173">设置指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="f4237-173">Set the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="f4237-174">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="f4237-174">put_HimetricLocationRaw</span></span>](#put_himetriclocationraw) | <span data-ttu-id="f4237-175">设置指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="f4237-175">Set the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="f4237-176">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="f4237-176">put_HistoryCount</span></span>](#put_historycount) | <span data-ttu-id="f4237-177">设置指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="f4237-177">Set the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="f4237-178">put_InputData</span><span class="sxs-lookup"><span data-stu-id="f4237-178">put_InputData</span></span>](#put_inputdata) | <span data-ttu-id="f4237-179">设置指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="f4237-179">Set the InputData of the pointer event.</span></span>
[<span data-ttu-id="f4237-180">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="f4237-180">put_KeyStates</span></span>](#put_keystates) | <span data-ttu-id="f4237-181">设置指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="f4237-181">Set the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="f4237-182">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="f4237-182">put_PenFlags</span></span>](#put_penflags) | <span data-ttu-id="f4237-183">设置指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="f4237-183">Set the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="f4237-184">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="f4237-184">put_PenMask</span></span>](#put_penmask) | <span data-ttu-id="f4237-185">设置指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="f4237-185">Set the PenMask of the pointer event.</span></span>
[<span data-ttu-id="f4237-186">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="f4237-186">put_PenPressure</span></span>](#put_penpressure) | <span data-ttu-id="f4237-187">设置指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="f4237-187">Set the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="f4237-188">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="f4237-188">put_PenRotation</span></span>](#put_penrotation) | <span data-ttu-id="f4237-189">设置指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="f4237-189">Set the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="f4237-190">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="f4237-190">put_PenTiltX</span></span>](#put_pentiltx) | <span data-ttu-id="f4237-191">设置指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="f4237-191">Set the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="f4237-192">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="f4237-192">put_PenTiltY</span></span>](#put_pentilty) | <span data-ttu-id="f4237-193">设置指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="f4237-193">Set the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="f4237-194">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="f4237-194">put_PerformanceCount</span></span>](#put_performancecount) | <span data-ttu-id="f4237-195">设置指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="f4237-195">Set the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="f4237-196">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="f4237-196">put_PixelLocation</span></span>](#put_pixellocation) | <span data-ttu-id="f4237-197">设置指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="f4237-197">Set the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="f4237-198">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="f4237-198">put_PixelLocationRaw</span></span>](#put_pixellocationraw) | <span data-ttu-id="f4237-199">设置指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="f4237-199">Set the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="f4237-200">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="f4237-200">put_PointerDeviceRect</span></span>](#put_pointerdevicerect) | <span data-ttu-id="f4237-201">按照 Windows SDK （winuser）中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="f4237-201">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="f4237-202">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="f4237-202">put_PointerFlags</span></span>](#put_pointerflags) | <span data-ttu-id="f4237-203">设置指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="f4237-203">Set the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="f4237-204">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="f4237-204">put_PointerId</span></span>](#put_pointerid) | <span data-ttu-id="f4237-205">设置指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="f4237-205">Set the PointerId of the pointer event.</span></span>
[<span data-ttu-id="f4237-206">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="f4237-206">put_PointerKind</span></span>](#put_pointerkind) | <span data-ttu-id="f4237-207">设置指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="f4237-207">Set the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="f4237-208">put_Time</span><span class="sxs-lookup"><span data-stu-id="f4237-208">put_Time</span></span>](#put_time) | <span data-ttu-id="f4237-209">设置指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="f4237-209">Set the Time of the pointer event.</span></span>
[<span data-ttu-id="f4237-210">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="f4237-210">put_TouchContact</span></span>](#put_touchcontact) | <span data-ttu-id="f4237-211">设置指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="f4237-211">Set the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="f4237-212">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="f4237-212">put_TouchContactRaw</span></span>](#put_touchcontactraw) | <span data-ttu-id="f4237-213">设置指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="f4237-213">Set the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="f4237-214">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="f4237-214">put_TouchFlags</span></span>](#put_touchflags) | <span data-ttu-id="f4237-215">设置指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="f4237-215">Set the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="f4237-216">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="f4237-216">put_TouchMask</span></span>](#put_touchmask) | <span data-ttu-id="f4237-217">设置指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="f4237-217">Set the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="f4237-218">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="f4237-218">put_TouchOrientation</span></span>](#put_touchorientation) | <span data-ttu-id="f4237-219">设置指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="f4237-219">Set the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="f4237-220">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="f4237-220">put_TouchPressure</span></span>](#put_touchpressure) | <span data-ttu-id="f4237-221">设置指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="f4237-221">Set the TouchPressure of the pointer event.</span></span>

<span data-ttu-id="f4237-222">它将获取所有三个字段中的字段，并排除某些 win32 特定的数据类型（如 HWND 和句柄）。</span><span class="sxs-lookup"><span data-stu-id="f4237-222">It takes fields from all three and excludes some win32 specific data types like HWND and HANDLE.</span></span> <span data-ttu-id="f4237-223">注意，sourceDevice 已被取出，但我们希望 PointerDeviceRect 和 DisplayRect 涵盖 sourceDevice 的现有使用情形。</span><span class="sxs-lookup"><span data-stu-id="f4237-223">Note, sourceDevice is taken out but we expect the PointerDeviceRect and DisplayRect to cover the existing use cases of sourceDevice.</span></span> <span data-ttu-id="f4237-224">另一个显著的区别是，任何点或 rect 位置都应位于 web 视图物理坐标中。</span><span class="sxs-lookup"><span data-stu-id="f4237-224">Another big difference is that any of the point or rect locations are expected to be in webview physical coordinates.</span></span> <span data-ttu-id="f4237-225">即，相对于 web 视图的坐标和未应用的 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="f4237-225">That is, coordinates relative to the webview and no DPI scaling applied.</span></span>

## <span data-ttu-id="f4237-226">成员</span><span class="sxs-lookup"><span data-stu-id="f4237-226">Members</span></span>

#### <span data-ttu-id="f4237-227">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="f4237-227">get_ButtonChangeKind</span></span> 

<span data-ttu-id="f4237-228">获取指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="f4237-228">Get the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="f4237-229">公共 HRESULT [get_ButtonChangeKind](#get_buttonchangekind)（INT32 \* ButtonChangeKind）</span><span class="sxs-lookup"><span data-stu-id="f4237-229">public HRESULT [get_ButtonChangeKind](#get_buttonchangekind)(INT32 \* buttonChangeKind)</span></span>

<span data-ttu-id="f4237-230">这对应于 POINTER_INFO 结构的 ButtonChangeKind 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-230">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="f4237-231">这些值由 Windows SDK 中的 POINTER_BUTTON_CHANGE_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="f4237-231">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-232">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="f4237-232">get_DisplayRect</span></span> 

<span data-ttu-id="f4237-233">获取在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="f4237-233">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="f4237-234">public HRESULT [get_DisplayRect](#get_displayrect)（RECT \* DisplayRect）</span><span class="sxs-lookup"><span data-stu-id="f4237-234">public HRESULT [get_DisplayRect](#get_displayrect)(RECT \* displayRect)</span></span>

#### <span data-ttu-id="f4237-235">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="f4237-235">get_FrameId</span></span> 

<span data-ttu-id="f4237-236">获取指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="f4237-236">Get the FrameID of the pointer event.</span></span>

> <span data-ttu-id="f4237-237">公共 HRESULT [get_FrameId](#get_frameid)（UINT32 \* FrameId）</span><span class="sxs-lookup"><span data-stu-id="f4237-237">public HRESULT [get_FrameId](#get_frameid)(UINT32 \* frameId)</span></span>

<span data-ttu-id="f4237-238">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 frameId 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-238">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-239">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="f4237-239">get_HimetricLocation</span></span> 

<span data-ttu-id="f4237-240">获取指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="f4237-240">Get the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="f4237-241">public HRESULT [get_HimetricLocation](#get_himetriclocation)（POINT \* HimetricLocation）</span><span class="sxs-lookup"><span data-stu-id="f4237-241">public HRESULT [get_HimetricLocation](#get_himetriclocation)(POINT \* himetricLocation)</span></span>

<span data-ttu-id="f4237-242">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-242">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-243">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="f4237-243">get_HimetricLocationRaw</span></span> 

<span data-ttu-id="f4237-244">获取指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="f4237-244">Get the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="f4237-245">public HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)（POINT \* HimetricLocationRaw）</span><span class="sxs-lookup"><span data-stu-id="f4237-245">public HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)(POINT \* himetricLocationRaw)</span></span>

<span data-ttu-id="f4237-246">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-246">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-247">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="f4237-247">get_HistoryCount</span></span> 

<span data-ttu-id="f4237-248">获取指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="f4237-248">Get the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="f4237-249">公共 HRESULT [get_HistoryCount](#get_historycount)（UINT32 \* HistoryCount）</span><span class="sxs-lookup"><span data-stu-id="f4237-249">public HRESULT [get_HistoryCount](#get_historycount)(UINT32 \* historyCount)</span></span>

<span data-ttu-id="f4237-250">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 historyCount 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-250">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-251">get_InputData</span><span class="sxs-lookup"><span data-stu-id="f4237-251">get_InputData</span></span> 

<span data-ttu-id="f4237-252">获取指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="f4237-252">Get the InputData of the pointer event.</span></span>

> <span data-ttu-id="f4237-253">公共 HRESULT [get_InputData](#get_inputdata)（INT32 \* InputData）</span><span class="sxs-lookup"><span data-stu-id="f4237-253">public HRESULT [get_InputData](#get_inputdata)(INT32 \* inputData)</span></span>

<span data-ttu-id="f4237-254">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 InputData 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-254">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-255">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="f4237-255">get_KeyStates</span></span> 

<span data-ttu-id="f4237-256">获取指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="f4237-256">Get the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="f4237-257">公共 HRESULT [get_KeyStates](#get_keystates)（DWORD \* KeyStates）</span><span class="sxs-lookup"><span data-stu-id="f4237-257">public HRESULT [get_KeyStates](#get_keystates)(DWORD \* keyStates)</span></span>

<span data-ttu-id="f4237-258">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwKeyStates 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-258">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-259">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="f4237-259">get_PenFlags</span></span> 

<span data-ttu-id="f4237-260">获取指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="f4237-260">Get the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="f4237-261">公共 HRESULT [get_PenFlags](#get_penflags)（UINT32 \* PenFlags）</span><span class="sxs-lookup"><span data-stu-id="f4237-261">public HRESULT [get_PenFlags](#get_penflags)(UINT32 \* penFLags)</span></span>

<span data-ttu-id="f4237-262">这对应于 POINTER_PEN_INFO 结构的 penFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-262">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="f4237-263">这些值由 Windows SDK 中的 PEN_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="f4237-263">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-264">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="f4237-264">get_PenMask</span></span> 

<span data-ttu-id="f4237-265">获取指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="f4237-265">Get the PenMask of the pointer event.</span></span>

> <span data-ttu-id="f4237-266">公共 HRESULT [get_PenMask](#get_penmask)（UINT32 \* PenMask）</span><span class="sxs-lookup"><span data-stu-id="f4237-266">public HRESULT [get_PenMask](#get_penmask)(UINT32 \* penMask)</span></span>

<span data-ttu-id="f4237-267">这对应于 POINTER_PEN_INFO 结构的 penMask 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-267">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="f4237-268">这些值由 Windows SDK 中的 PEN_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="f4237-268">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-269">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="f4237-269">get_PenPressure</span></span> 

<span data-ttu-id="f4237-270">获取指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="f4237-270">Get the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="f4237-271">公共 HRESULT [get_PenPressure](#get_penpressure)（UINT32 \* PenPressure）</span><span class="sxs-lookup"><span data-stu-id="f4237-271">public HRESULT [get_PenPressure](#get_penpressure)(UINT32 \* penPressure)</span></span>

<span data-ttu-id="f4237-272">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-272">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-273">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="f4237-273">get_PenRotation</span></span> 

<span data-ttu-id="f4237-274">获取指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="f4237-274">Get the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="f4237-275">公共 HRESULT [get_PenRotation](#get_penrotation)（UINT32 \* PenRotation）</span><span class="sxs-lookup"><span data-stu-id="f4237-275">public HRESULT [get_PenRotation](#get_penrotation)(UINT32 \* penRotation)</span></span>

<span data-ttu-id="f4237-276">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的旋转属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-276">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-277">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="f4237-277">get_PenTiltX</span></span> 

<span data-ttu-id="f4237-278">获取指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="f4237-278">Get the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="f4237-279">公共 HRESULT [get_PenTiltX](#get_pentiltx)（INT32 \* PenTiltX）</span><span class="sxs-lookup"><span data-stu-id="f4237-279">public HRESULT [get_PenTiltX](#get_pentiltx)(INT32 \* penTiltX)</span></span>

<span data-ttu-id="f4237-280">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltX 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-280">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-281">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="f4237-281">get_PenTiltY</span></span> 

<span data-ttu-id="f4237-282">获取指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="f4237-282">Get the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="f4237-283">公共 HRESULT [get_PenTiltY](#get_pentilty)（INT32 \* PenTiltY）</span><span class="sxs-lookup"><span data-stu-id="f4237-283">public HRESULT [get_PenTiltY](#get_pentilty)(INT32 \* penTiltY)</span></span>

<span data-ttu-id="f4237-284">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltY 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-284">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-285">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="f4237-285">get_PerformanceCount</span></span> 

<span data-ttu-id="f4237-286">获取指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="f4237-286">Get the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="f4237-287">公共 HRESULT [get_PerformanceCount](#get_performancecount)（UINT64 \* PerformanceCount）</span><span class="sxs-lookup"><span data-stu-id="f4237-287">public HRESULT [get_PerformanceCount](#get_performancecount)(UINT64 \* performanceCount)</span></span>

<span data-ttu-id="f4237-288">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 PerformanceCount 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-288">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-289">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="f4237-289">get_PixelLocation</span></span> 

<span data-ttu-id="f4237-290">获取指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="f4237-290">Get the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="f4237-291">public HRESULT [get_PixelLocation](#get_pixellocation)（POINT \* PixelLocation）</span><span class="sxs-lookup"><span data-stu-id="f4237-291">public HRESULT [get_PixelLocation](#get_pixellocation)(POINT \* pixelLocation)</span></span>

<span data-ttu-id="f4237-292">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-292">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-293">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="f4237-293">get_PixelLocationRaw</span></span> 

<span data-ttu-id="f4237-294">获取指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="f4237-294">Get the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="f4237-295">public HRESULT [get_PixelLocationRaw](#get_pixellocationraw)（POINT \* PixelLocationRaw）</span><span class="sxs-lookup"><span data-stu-id="f4237-295">public HRESULT [get_PixelLocationRaw](#get_pixellocationraw)(POINT \* pixelLocationRaw)</span></span>

<span data-ttu-id="f4237-296">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-296">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-297">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="f4237-297">get_PointerDeviceRect</span></span> 

<span data-ttu-id="f4237-298">获取在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="f4237-298">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="f4237-299">public HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)（RECT \* PointerDeviceRect）</span><span class="sxs-lookup"><span data-stu-id="f4237-299">public HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)(RECT \* pointerDeviceRect)</span></span>

#### <span data-ttu-id="f4237-300">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="f4237-300">get_PointerFlags</span></span> 

<span data-ttu-id="f4237-301">获取指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="f4237-301">Get the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="f4237-302">公共 HRESULT [get_PointerFlags](#get_pointerflags)（UINT32 \* PointerFlags）</span><span class="sxs-lookup"><span data-stu-id="f4237-302">public HRESULT [get_PointerFlags](#get_pointerflags)(UINT32 \* pointerFlags)</span></span>

<span data-ttu-id="f4237-303">这对应于 POINTER_INFO 结构的 pointerFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-303">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="f4237-304">这些值由 Windows SDK 中的 POINTER_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="f4237-304">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-305">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="f4237-305">get_PointerId</span></span> 

<span data-ttu-id="f4237-306">获取指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="f4237-306">Get the PointerId of the pointer event.</span></span>

> <span data-ttu-id="f4237-307">公共 HRESULT [get_PointerId](#get_pointerid)（UINT32 \* PointerId）</span><span class="sxs-lookup"><span data-stu-id="f4237-307">public HRESULT [get_PointerId](#get_pointerid)(UINT32 \* pointerId)</span></span>

<span data-ttu-id="f4237-308">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 pointerId 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-308">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-309">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="f4237-309">get_PointerKind</span></span> 

<span data-ttu-id="f4237-310">获取指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="f4237-310">Get the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="f4237-311">公共 HRESULT [get_PointerKind](#get_pointerkind)（DWORD \* PointerKind）</span><span class="sxs-lookup"><span data-stu-id="f4237-311">public HRESULT [get_PointerKind](#get_pointerkind)(DWORD \* pointerKind)</span></span>

<span data-ttu-id="f4237-312">这对应于 POINTER_INFO 结构的 pointerKind 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-312">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="f4237-313">这些值由 Windows SDK 中的 POINTER_INPUT_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="f4237-313">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="f4237-314">支持 PT_PEN 和 PT_TOUCH。</span><span class="sxs-lookup"><span data-stu-id="f4237-314">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="f4237-315">get_Time</span><span class="sxs-lookup"><span data-stu-id="f4237-315">get_Time</span></span> 

<span data-ttu-id="f4237-316">获取指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="f4237-316">Get the Time of the pointer event.</span></span>

> <span data-ttu-id="f4237-317">公共 HRESULT [get_Time](#get_time)（DWORD \* 时间）</span><span class="sxs-lookup"><span data-stu-id="f4237-317">public HRESULT [get_Time](#get_time)(DWORD \* time)</span></span>

<span data-ttu-id="f4237-318">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwTime 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-318">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-319">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="f4237-319">get_TouchContact</span></span> 

<span data-ttu-id="f4237-320">获取指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="f4237-320">Get the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="f4237-321">public HRESULT [get_TouchContact](#get_touchcontact)（RECT \* TouchContact）</span><span class="sxs-lookup"><span data-stu-id="f4237-321">public HRESULT [get_TouchContact](#get_touchcontact)(RECT \* touchContact)</span></span>

<span data-ttu-id="f4237-322">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContact 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-322">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-323">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="f4237-323">get_TouchContactRaw</span></span> 

<span data-ttu-id="f4237-324">获取指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="f4237-324">Get the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="f4237-325">public HRESULT [get_TouchContactRaw](#get_touchcontactraw)（RECT \* TouchContactRaw）</span><span class="sxs-lookup"><span data-stu-id="f4237-325">public HRESULT [get_TouchContactRaw](#get_touchcontactraw)(RECT \* touchContactRaw)</span></span>

<span data-ttu-id="f4237-326">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContactRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-326">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-327">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="f4237-327">get_TouchFlags</span></span> 

<span data-ttu-id="f4237-328">获取指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="f4237-328">Get the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="f4237-329">公共 HRESULT [get_TouchFlags](#get_touchflags)（UINT32 \* TouchFlags）</span><span class="sxs-lookup"><span data-stu-id="f4237-329">public HRESULT [get_TouchFlags](#get_touchflags)(UINT32 \* touchFlags)</span></span>

<span data-ttu-id="f4237-330">这对应于 POINTER_TOUCH_INFO 结构的 touchFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-330">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="f4237-331">这些值由 Windows SDK 中的 TOUCH_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="f4237-331">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-332">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="f4237-332">get_TouchMask</span></span> 

<span data-ttu-id="f4237-333">获取指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="f4237-333">Get the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="f4237-334">公共 HRESULT [get_TouchMask](#get_touchmask)（UINT32 \* TouchMask）</span><span class="sxs-lookup"><span data-stu-id="f4237-334">public HRESULT [get_TouchMask](#get_touchmask)(UINT32 \* touchMask)</span></span>

<span data-ttu-id="f4237-335">这对应于 POINTER_TOUCH_INFO 结构的 touchMask 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-335">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="f4237-336">这些值由 Windows SDK 中的 TOUCH_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="f4237-336">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-337">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="f4237-337">get_TouchOrientation</span></span> 

<span data-ttu-id="f4237-338">获取指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="f4237-338">Get the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="f4237-339">公共 HRESULT [get_TouchOrientation](#get_touchorientation)（UINT32 \* TouchOrientation）</span><span class="sxs-lookup"><span data-stu-id="f4237-339">public HRESULT [get_TouchOrientation](#get_touchorientation)(UINT32 \* touchOrientation)</span></span>

<span data-ttu-id="f4237-340">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 "方向" 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-340">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-341">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="f4237-341">get_TouchPressure</span></span> 

<span data-ttu-id="f4237-342">获取指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="f4237-342">Get the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="f4237-343">公共 HRESULT [get_TouchPressure](#get_touchpressure)（UINT32 \* TouchPressure）</span><span class="sxs-lookup"><span data-stu-id="f4237-343">public HRESULT [get_TouchPressure](#get_touchpressure)(UINT32 \* touchPressure)</span></span>

<span data-ttu-id="f4237-344">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-344">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-345">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="f4237-345">put_ButtonChangeKind</span></span> 

<span data-ttu-id="f4237-346">设置指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="f4237-346">Set the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="f4237-347">公共 HRESULT [put_ButtonChangeKind](#put_buttonchangekind)（INT32 ButtonChangeKind）</span><span class="sxs-lookup"><span data-stu-id="f4237-347">public HRESULT [put_ButtonChangeKind](#put_buttonchangekind)(INT32 buttonChangeKind)</span></span>

<span data-ttu-id="f4237-348">这对应于 POINTER_INFO 结构的 ButtonChangeKind 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-348">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="f4237-349">这些值由 Windows SDK 中的 POINTER_BUTTON_CHANGE_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="f4237-349">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-350">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="f4237-350">put_DisplayRect</span></span> 

<span data-ttu-id="f4237-351">按照 Windows SDK （winuser）中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="f4237-351">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="f4237-352">public HRESULT [put_DisplayRect](#put_displayrect)（RECT DisplayRect）</span><span class="sxs-lookup"><span data-stu-id="f4237-352">public HRESULT [put_DisplayRect](#put_displayrect)(RECT displayRect)</span></span>

#### <span data-ttu-id="f4237-353">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="f4237-353">put_FrameId</span></span> 

<span data-ttu-id="f4237-354">设置指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="f4237-354">Set the FrameID of the pointer event.</span></span>

> <span data-ttu-id="f4237-355">公共 HRESULT [put_FrameId](#put_frameid)（UINT32 FrameId）</span><span class="sxs-lookup"><span data-stu-id="f4237-355">public HRESULT [put_FrameId](#put_frameid)(UINT32 frameId)</span></span>

<span data-ttu-id="f4237-356">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 frameId 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-356">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-357">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="f4237-357">put_HimetricLocation</span></span> 

<span data-ttu-id="f4237-358">设置指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="f4237-358">Set the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="f4237-359">public HRESULT [put_HimetricLocation](#put_himetriclocation)（POINT HimetricLocation）</span><span class="sxs-lookup"><span data-stu-id="f4237-359">public HRESULT [put_HimetricLocation](#put_himetriclocation)(POINT himetricLocation)</span></span>

<span data-ttu-id="f4237-360">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-360">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-361">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="f4237-361">put_HimetricLocationRaw</span></span> 

<span data-ttu-id="f4237-362">设置指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="f4237-362">Set the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="f4237-363">public HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)（POINT HimetricLocationRaw）</span><span class="sxs-lookup"><span data-stu-id="f4237-363">public HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)(POINT himetricLocationRaw)</span></span>

<span data-ttu-id="f4237-364">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-364">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-365">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="f4237-365">put_HistoryCount</span></span> 

<span data-ttu-id="f4237-366">设置指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="f4237-366">Set the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="f4237-367">公共 HRESULT [put_HistoryCount](#put_historycount)（UINT32 HistoryCount）</span><span class="sxs-lookup"><span data-stu-id="f4237-367">public HRESULT [put_HistoryCount](#put_historycount)(UINT32 historyCount)</span></span>

<span data-ttu-id="f4237-368">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 historyCount 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-368">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-369">put_InputData</span><span class="sxs-lookup"><span data-stu-id="f4237-369">put_InputData</span></span> 

<span data-ttu-id="f4237-370">设置指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="f4237-370">Set the InputData of the pointer event.</span></span>

> <span data-ttu-id="f4237-371">公共 HRESULT [put_InputData](#put_inputdata)（INT32 InputData）</span><span class="sxs-lookup"><span data-stu-id="f4237-371">public HRESULT [put_InputData](#put_inputdata)(INT32 inputData)</span></span>

<span data-ttu-id="f4237-372">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 InputData 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-372">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-373">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="f4237-373">put_KeyStates</span></span> 

<span data-ttu-id="f4237-374">设置指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="f4237-374">Set the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="f4237-375">公共 HRESULT [put_KeyStates](#put_keystates)（DWORD KeyStates）</span><span class="sxs-lookup"><span data-stu-id="f4237-375">public HRESULT [put_KeyStates](#put_keystates)(DWORD keyStates)</span></span>

<span data-ttu-id="f4237-376">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwKeyStates 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-376">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-377">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="f4237-377">put_PenFlags</span></span> 

<span data-ttu-id="f4237-378">设置指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="f4237-378">Set the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="f4237-379">公共 HRESULT [put_PenFlags](#put_penflags)（UINT32 PenFlags）</span><span class="sxs-lookup"><span data-stu-id="f4237-379">public HRESULT [put_PenFlags](#put_penflags)(UINT32 penFLags)</span></span>

<span data-ttu-id="f4237-380">这对应于 POINTER_PEN_INFO 结构的 penFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-380">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="f4237-381">这些值由 Windows SDK 中的 PEN_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="f4237-381">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-382">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="f4237-382">put_PenMask</span></span> 

<span data-ttu-id="f4237-383">设置指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="f4237-383">Set the PenMask of the pointer event.</span></span>

> <span data-ttu-id="f4237-384">公共 HRESULT [put_PenMask](#put_penmask)（UINT32 PenMask）</span><span class="sxs-lookup"><span data-stu-id="f4237-384">public HRESULT [put_PenMask](#put_penmask)(UINT32 penMask)</span></span>

<span data-ttu-id="f4237-385">这对应于 POINTER_PEN_INFO 结构的 penMask 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-385">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="f4237-386">这些值由 Windows SDK 中的 PEN_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="f4237-386">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-387">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="f4237-387">put_PenPressure</span></span> 

<span data-ttu-id="f4237-388">设置指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="f4237-388">Set the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="f4237-389">公共 HRESULT [put_PenPressure](#put_penpressure)（UINT32 PenPressure）</span><span class="sxs-lookup"><span data-stu-id="f4237-389">public HRESULT [put_PenPressure](#put_penpressure)(UINT32 penPressure)</span></span>

<span data-ttu-id="f4237-390">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-390">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-391">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="f4237-391">put_PenRotation</span></span> 

<span data-ttu-id="f4237-392">设置指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="f4237-392">Set the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="f4237-393">公共 HRESULT [put_PenRotation](#put_penrotation)（UINT32 PenRotation）</span><span class="sxs-lookup"><span data-stu-id="f4237-393">public HRESULT [put_PenRotation](#put_penrotation)(UINT32 penRotation)</span></span>

<span data-ttu-id="f4237-394">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的旋转属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-394">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-395">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="f4237-395">put_PenTiltX</span></span> 

<span data-ttu-id="f4237-396">设置指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="f4237-396">Set the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="f4237-397">公共 HRESULT [put_PenTiltX](#put_pentiltx)（INT32 PenTiltX）</span><span class="sxs-lookup"><span data-stu-id="f4237-397">public HRESULT [put_PenTiltX](#put_pentiltx)(INT32 penTiltX)</span></span>

<span data-ttu-id="f4237-398">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltX 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-398">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-399">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="f4237-399">put_PenTiltY</span></span> 

<span data-ttu-id="f4237-400">设置指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="f4237-400">Set the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="f4237-401">公共 HRESULT [put_PenTiltY](#put_pentilty)（INT32 PenTiltY）</span><span class="sxs-lookup"><span data-stu-id="f4237-401">public HRESULT [put_PenTiltY](#put_pentilty)(INT32 penTiltY)</span></span>

<span data-ttu-id="f4237-402">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltY 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-402">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-403">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="f4237-403">put_PerformanceCount</span></span> 

<span data-ttu-id="f4237-404">设置指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="f4237-404">Set the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="f4237-405">公共 HRESULT [put_PerformanceCount](#put_performancecount)（UINT64 PerformanceCount）</span><span class="sxs-lookup"><span data-stu-id="f4237-405">public HRESULT [put_PerformanceCount](#put_performancecount)(UINT64 performanceCount)</span></span>

<span data-ttu-id="f4237-406">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 PerformanceCount 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-406">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-407">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="f4237-407">put_PixelLocation</span></span> 

<span data-ttu-id="f4237-408">设置指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="f4237-408">Set the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="f4237-409">public HRESULT [put_PixelLocation](#put_pixellocation)（POINT PixelLocation）</span><span class="sxs-lookup"><span data-stu-id="f4237-409">public HRESULT [put_PixelLocation](#put_pixellocation)(POINT pixelLocation)</span></span>

<span data-ttu-id="f4237-410">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-410">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-411">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="f4237-411">put_PixelLocationRaw</span></span> 

<span data-ttu-id="f4237-412">设置指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="f4237-412">Set the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="f4237-413">public HRESULT [put_PixelLocationRaw](#put_pixellocationraw)（POINT PixelLocationRaw）</span><span class="sxs-lookup"><span data-stu-id="f4237-413">public HRESULT [put_PixelLocationRaw](#put_pixellocationraw)(POINT pixelLocationRaw)</span></span>

<span data-ttu-id="f4237-414">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-414">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-415">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="f4237-415">put_PointerDeviceRect</span></span> 

<span data-ttu-id="f4237-416">按照 Windows SDK （winuser）中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="f4237-416">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="f4237-417">public HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)（RECT PointerDeviceRect）</span><span class="sxs-lookup"><span data-stu-id="f4237-417">public HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)(RECT pointerDeviceRect)</span></span>

#### <span data-ttu-id="f4237-418">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="f4237-418">put_PointerFlags</span></span> 

<span data-ttu-id="f4237-419">设置指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="f4237-419">Set the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="f4237-420">公共 HRESULT [put_PointerFlags](#put_pointerflags)（UINT32 PointerFlags）</span><span class="sxs-lookup"><span data-stu-id="f4237-420">public HRESULT [put_PointerFlags](#put_pointerflags)(UINT32 pointerFlags)</span></span>

<span data-ttu-id="f4237-421">这对应于 POINTER_INFO 结构的 pointerFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-421">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="f4237-422">这些值由 Windows SDK 中的 POINTER_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="f4237-422">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-423">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="f4237-423">put_PointerId</span></span> 

<span data-ttu-id="f4237-424">设置指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="f4237-424">Set the PointerId of the pointer event.</span></span>

> <span data-ttu-id="f4237-425">公共 HRESULT [put_PointerId](#put_pointerid)（UINT32 PointerId）</span><span class="sxs-lookup"><span data-stu-id="f4237-425">public HRESULT [put_PointerId](#put_pointerid)(UINT32 pointerId)</span></span>

<span data-ttu-id="f4237-426">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 pointerId 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-426">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-427">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="f4237-427">put_PointerKind</span></span> 

<span data-ttu-id="f4237-428">设置指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="f4237-428">Set the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="f4237-429">公共 HRESULT [put_PointerKind](#put_pointerkind)（DWORD PointerKind）</span><span class="sxs-lookup"><span data-stu-id="f4237-429">public HRESULT [put_PointerKind](#put_pointerkind)(DWORD pointerKind)</span></span>

<span data-ttu-id="f4237-430">这对应于 POINTER_INFO 结构的 pointerKind 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-430">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="f4237-431">这些值由 Windows SDK 中的 POINTER_INPUT_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="f4237-431">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="f4237-432">支持 PT_PEN 和 PT_TOUCH。</span><span class="sxs-lookup"><span data-stu-id="f4237-432">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="f4237-433">put_Time</span><span class="sxs-lookup"><span data-stu-id="f4237-433">put_Time</span></span> 

<span data-ttu-id="f4237-434">设置指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="f4237-434">Set the Time of the pointer event.</span></span>

> <span data-ttu-id="f4237-435">公共 HRESULT [put_Time](#put_time)（DWORD 时间）</span><span class="sxs-lookup"><span data-stu-id="f4237-435">public HRESULT [put_Time](#put_time)(DWORD time)</span></span>

<span data-ttu-id="f4237-436">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwTime 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-436">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-437">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="f4237-437">put_TouchContact</span></span> 

<span data-ttu-id="f4237-438">设置指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="f4237-438">Set the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="f4237-439">public HRESULT [put_TouchContact](#put_touchcontact)（RECT TouchContact）</span><span class="sxs-lookup"><span data-stu-id="f4237-439">public HRESULT [put_TouchContact](#put_touchcontact)(RECT touchContact)</span></span>

<span data-ttu-id="f4237-440">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContact 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-440">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-441">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="f4237-441">put_TouchContactRaw</span></span> 

<span data-ttu-id="f4237-442">设置指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="f4237-442">Set the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="f4237-443">public HRESULT [put_TouchContactRaw](#put_touchcontactraw)（RECT TouchContactRaw）</span><span class="sxs-lookup"><span data-stu-id="f4237-443">public HRESULT [put_TouchContactRaw](#put_touchcontactraw)(RECT touchContactRaw)</span></span>

<span data-ttu-id="f4237-444">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContactRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-444">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-445">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="f4237-445">put_TouchFlags</span></span> 

<span data-ttu-id="f4237-446">设置指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="f4237-446">Set the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="f4237-447">公共 HRESULT [put_TouchFlags](#put_touchflags)（UINT32 TouchFlags）</span><span class="sxs-lookup"><span data-stu-id="f4237-447">public HRESULT [put_TouchFlags](#put_touchflags)(UINT32 touchFlags)</span></span>

<span data-ttu-id="f4237-448">这对应于 POINTER_TOUCH_INFO 结构的 touchFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-448">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="f4237-449">这些值由 Windows SDK 中的 TOUCH_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="f4237-449">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-450">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="f4237-450">put_TouchMask</span></span> 

<span data-ttu-id="f4237-451">设置指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="f4237-451">Set the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="f4237-452">公共 HRESULT [put_TouchMask](#put_touchmask)（UINT32 TouchMask）</span><span class="sxs-lookup"><span data-stu-id="f4237-452">public HRESULT [put_TouchMask](#put_touchmask)(UINT32 touchMask)</span></span>

<span data-ttu-id="f4237-453">这对应于 POINTER_TOUCH_INFO 结构的 touchMask 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-453">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="f4237-454">这些值由 Windows SDK 中的 TOUCH_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="f4237-454">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-455">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="f4237-455">put_TouchOrientation</span></span> 

<span data-ttu-id="f4237-456">设置指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="f4237-456">Set the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="f4237-457">公共 HRESULT [put_TouchOrientation](#put_touchorientation)（UINT32 TouchOrientation）</span><span class="sxs-lookup"><span data-stu-id="f4237-457">public HRESULT [put_TouchOrientation](#put_touchorientation)(UINT32 touchOrientation)</span></span>

<span data-ttu-id="f4237-458">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 "方向" 属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-458">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="f4237-459">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="f4237-459">put_TouchPressure</span></span> 

<span data-ttu-id="f4237-460">设置指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="f4237-460">Set the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="f4237-461">公共 HRESULT [put_TouchPressure](#put_touchpressure)（UINT32 TouchPressure）</span><span class="sxs-lookup"><span data-stu-id="f4237-461">public HRESULT [put_TouchPressure](#put_touchpressure)(UINT32 touchPressure)</span></span>

<span data-ttu-id="f4237-462">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="f4237-462">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

