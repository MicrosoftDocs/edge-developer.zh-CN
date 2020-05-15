---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 2141dff54b44fe6d9a2758f571e61b81877079da
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653033"
---
# <span data-ttu-id="488b1-104">interface ICoreWebView2ExperimentalPointerInfo</span><span class="sxs-lookup"><span data-stu-id="488b1-104">interface ICoreWebView2ExperimentalPointerInfo</span></span> 

> [!NOTE]
> <span data-ttu-id="488b1-105">这是使用预发行 SDK 版本0.9.488 随附的实验性 API。</span><span class="sxs-lookup"><span data-stu-id="488b1-105">This an experimental API that is shipped with our prerelease SDK version 0.9.488.</span></span>

```
interface ICoreWebView2ExperimentalPointerInfo
  : public IUnknown
```

<span data-ttu-id="488b1-106">这通常表示一个组合的 win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO 对象。</span><span class="sxs-lookup"><span data-stu-id="488b1-106">This mostly represents a combined win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO object.</span></span>

## <span data-ttu-id="488b1-107">摘要</span><span class="sxs-lookup"><span data-stu-id="488b1-107">Summary</span></span>

 <span data-ttu-id="488b1-108">成员</span><span class="sxs-lookup"><span data-stu-id="488b1-108">Members</span></span>                        | <span data-ttu-id="488b1-109">描述</span><span class="sxs-lookup"><span data-stu-id="488b1-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="488b1-110">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="488b1-110">get_ButtonChangeKind</span></span>](#get_buttonchangekind) | <span data-ttu-id="488b1-111">获取指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="488b1-111">Get the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="488b1-112">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="488b1-112">get_DisplayRect</span></span>](#get_displayrect) | <span data-ttu-id="488b1-113">获取在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="488b1-113">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="488b1-114">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="488b1-114">get_FrameId</span></span>](#get_frameid) | <span data-ttu-id="488b1-115">获取指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="488b1-115">Get the FrameID of the pointer event.</span></span>
[<span data-ttu-id="488b1-116">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="488b1-116">get_HimetricLocation</span></span>](#get_himetriclocation) | <span data-ttu-id="488b1-117">获取指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="488b1-117">Get the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="488b1-118">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="488b1-118">get_HimetricLocationRaw</span></span>](#get_himetriclocationraw) | <span data-ttu-id="488b1-119">获取指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="488b1-119">Get the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="488b1-120">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="488b1-120">get_HistoryCount</span></span>](#get_historycount) | <span data-ttu-id="488b1-121">获取指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="488b1-121">Get the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="488b1-122">get_InputData</span><span class="sxs-lookup"><span data-stu-id="488b1-122">get_InputData</span></span>](#get_inputdata) | <span data-ttu-id="488b1-123">获取指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="488b1-123">Get the InputData of the pointer event.</span></span>
[<span data-ttu-id="488b1-124">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="488b1-124">get_KeyStates</span></span>](#get_keystates) | <span data-ttu-id="488b1-125">获取指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="488b1-125">Get the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="488b1-126">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="488b1-126">get_PenFlags</span></span>](#get_penflags) | <span data-ttu-id="488b1-127">获取指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="488b1-127">Get the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="488b1-128">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="488b1-128">get_PenMask</span></span>](#get_penmask) | <span data-ttu-id="488b1-129">获取指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="488b1-129">Get the PenMask of the pointer event.</span></span>
[<span data-ttu-id="488b1-130">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="488b1-130">get_PenPressure</span></span>](#get_penpressure) | <span data-ttu-id="488b1-131">获取指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="488b1-131">Get the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="488b1-132">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="488b1-132">get_PenRotation</span></span>](#get_penrotation) | <span data-ttu-id="488b1-133">获取指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="488b1-133">Get the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="488b1-134">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="488b1-134">get_PenTiltX</span></span>](#get_pentiltx) | <span data-ttu-id="488b1-135">获取指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="488b1-135">Get the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="488b1-136">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="488b1-136">get_PenTiltY</span></span>](#get_pentilty) | <span data-ttu-id="488b1-137">获取指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="488b1-137">Get the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="488b1-138">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="488b1-138">get_PerformanceCount</span></span>](#get_performancecount) | <span data-ttu-id="488b1-139">获取指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="488b1-139">Get the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="488b1-140">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="488b1-140">get_PixelLocation</span></span>](#get_pixellocation) | <span data-ttu-id="488b1-141">获取指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="488b1-141">Get the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="488b1-142">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="488b1-142">get_PixelLocationRaw</span></span>](#get_pixellocationraw) | <span data-ttu-id="488b1-143">获取指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="488b1-143">Get the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="488b1-144">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="488b1-144">get_PointerDeviceRect</span></span>](#get_pointerdevicerect) | <span data-ttu-id="488b1-145">获取在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="488b1-145">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="488b1-146">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="488b1-146">get_PointerFlags</span></span>](#get_pointerflags) | <span data-ttu-id="488b1-147">获取指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="488b1-147">Get the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="488b1-148">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="488b1-148">get_PointerId</span></span>](#get_pointerid) | <span data-ttu-id="488b1-149">获取指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="488b1-149">Get the PointerId of the pointer event.</span></span>
[<span data-ttu-id="488b1-150">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="488b1-150">get_PointerKind</span></span>](#get_pointerkind) | <span data-ttu-id="488b1-151">获取指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="488b1-151">Get the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="488b1-152">get_Time</span><span class="sxs-lookup"><span data-stu-id="488b1-152">get_Time</span></span>](#get_time) | <span data-ttu-id="488b1-153">获取指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="488b1-153">Get the Time of the pointer event.</span></span>
[<span data-ttu-id="488b1-154">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="488b1-154">get_TouchContact</span></span>](#get_touchcontact) | <span data-ttu-id="488b1-155">获取指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="488b1-155">Get the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="488b1-156">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="488b1-156">get_TouchContactRaw</span></span>](#get_touchcontactraw) | <span data-ttu-id="488b1-157">获取指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="488b1-157">Get the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="488b1-158">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="488b1-158">get_TouchFlags</span></span>](#get_touchflags) | <span data-ttu-id="488b1-159">获取指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="488b1-159">Get the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="488b1-160">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="488b1-160">get_TouchMask</span></span>](#get_touchmask) | <span data-ttu-id="488b1-161">获取指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="488b1-161">Get the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="488b1-162">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="488b1-162">get_TouchOrientation</span></span>](#get_touchorientation) | <span data-ttu-id="488b1-163">获取指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="488b1-163">Get the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="488b1-164">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="488b1-164">get_TouchPressure</span></span>](#get_touchpressure) | <span data-ttu-id="488b1-165">获取指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="488b1-165">Get the TouchPressure of the pointer event.</span></span>
[<span data-ttu-id="488b1-166">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="488b1-166">put_ButtonChangeKind</span></span>](#put_buttonchangekind) | <span data-ttu-id="488b1-167">设置指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="488b1-167">Set the ButtonChangeKind of the pointer event.</span></span>
[<span data-ttu-id="488b1-168">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="488b1-168">put_DisplayRect</span></span>](#put_displayrect) | <span data-ttu-id="488b1-169">按照 Windows SDK （winuser）中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="488b1-169">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="488b1-170">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="488b1-170">put_FrameId</span></span>](#put_frameid) | <span data-ttu-id="488b1-171">设置指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="488b1-171">Set the FrameID of the pointer event.</span></span>
[<span data-ttu-id="488b1-172">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="488b1-172">put_HimetricLocation</span></span>](#put_himetriclocation) | <span data-ttu-id="488b1-173">设置指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="488b1-173">Set the HimetricLocation of the pointer event.</span></span>
[<span data-ttu-id="488b1-174">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="488b1-174">put_HimetricLocationRaw</span></span>](#put_himetriclocationraw) | <span data-ttu-id="488b1-175">设置指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="488b1-175">Set the HimetricLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="488b1-176">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="488b1-176">put_HistoryCount</span></span>](#put_historycount) | <span data-ttu-id="488b1-177">设置指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="488b1-177">Set the HistoryCount of the pointer event.</span></span>
[<span data-ttu-id="488b1-178">put_InputData</span><span class="sxs-lookup"><span data-stu-id="488b1-178">put_InputData</span></span>](#put_inputdata) | <span data-ttu-id="488b1-179">设置指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="488b1-179">Set the InputData of the pointer event.</span></span>
[<span data-ttu-id="488b1-180">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="488b1-180">put_KeyStates</span></span>](#put_keystates) | <span data-ttu-id="488b1-181">设置指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="488b1-181">Set the KeyStates of the pointer event.</span></span>
[<span data-ttu-id="488b1-182">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="488b1-182">put_PenFlags</span></span>](#put_penflags) | <span data-ttu-id="488b1-183">设置指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="488b1-183">Set the PenFlags of the pointer event.</span></span>
[<span data-ttu-id="488b1-184">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="488b1-184">put_PenMask</span></span>](#put_penmask) | <span data-ttu-id="488b1-185">设置指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="488b1-185">Set the PenMask of the pointer event.</span></span>
[<span data-ttu-id="488b1-186">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="488b1-186">put_PenPressure</span></span>](#put_penpressure) | <span data-ttu-id="488b1-187">设置指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="488b1-187">Set the PenPressure of the pointer event.</span></span>
[<span data-ttu-id="488b1-188">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="488b1-188">put_PenRotation</span></span>](#put_penrotation) | <span data-ttu-id="488b1-189">设置指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="488b1-189">Set the PenRotation of the pointer event.</span></span>
[<span data-ttu-id="488b1-190">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="488b1-190">put_PenTiltX</span></span>](#put_pentiltx) | <span data-ttu-id="488b1-191">设置指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="488b1-191">Set the PenTiltX of the pointer event.</span></span>
[<span data-ttu-id="488b1-192">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="488b1-192">put_PenTiltY</span></span>](#put_pentilty) | <span data-ttu-id="488b1-193">设置指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="488b1-193">Set the PenTiltY of the pointer event.</span></span>
[<span data-ttu-id="488b1-194">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="488b1-194">put_PerformanceCount</span></span>](#put_performancecount) | <span data-ttu-id="488b1-195">设置指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="488b1-195">Set the PerformanceCount of the pointer event.</span></span>
[<span data-ttu-id="488b1-196">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="488b1-196">put_PixelLocation</span></span>](#put_pixellocation) | <span data-ttu-id="488b1-197">设置指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="488b1-197">Set the PixelLocation of the pointer event.</span></span>
[<span data-ttu-id="488b1-198">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="488b1-198">put_PixelLocationRaw</span></span>](#put_pixellocationraw) | <span data-ttu-id="488b1-199">设置指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="488b1-199">Set the PixelLocationRaw of the pointer event.</span></span>
[<span data-ttu-id="488b1-200">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="488b1-200">put_PointerDeviceRect</span></span>](#put_pointerdevicerect) | <span data-ttu-id="488b1-201">按照 Windows SDK （winuser）中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="488b1-201">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>
[<span data-ttu-id="488b1-202">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="488b1-202">put_PointerFlags</span></span>](#put_pointerflags) | <span data-ttu-id="488b1-203">设置指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="488b1-203">Set the PointerFlags of the pointer event.</span></span>
[<span data-ttu-id="488b1-204">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="488b1-204">put_PointerId</span></span>](#put_pointerid) | <span data-ttu-id="488b1-205">设置指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="488b1-205">Set the PointerId of the pointer event.</span></span>
[<span data-ttu-id="488b1-206">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="488b1-206">put_PointerKind</span></span>](#put_pointerkind) | <span data-ttu-id="488b1-207">设置指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="488b1-207">Set the PointerKind of the pointer event.</span></span>
[<span data-ttu-id="488b1-208">put_Time</span><span class="sxs-lookup"><span data-stu-id="488b1-208">put_Time</span></span>](#put_time) | <span data-ttu-id="488b1-209">设置指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="488b1-209">Set the Time of the pointer event.</span></span>
[<span data-ttu-id="488b1-210">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="488b1-210">put_TouchContact</span></span>](#put_touchcontact) | <span data-ttu-id="488b1-211">设置指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="488b1-211">Set the TouchContact of the pointer event.</span></span>
[<span data-ttu-id="488b1-212">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="488b1-212">put_TouchContactRaw</span></span>](#put_touchcontactraw) | <span data-ttu-id="488b1-213">设置指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="488b1-213">Set the TouchContactRaw of the pointer event.</span></span>
[<span data-ttu-id="488b1-214">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="488b1-214">put_TouchFlags</span></span>](#put_touchflags) | <span data-ttu-id="488b1-215">设置指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="488b1-215">Set the TouchFlags of the pointer event.</span></span>
[<span data-ttu-id="488b1-216">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="488b1-216">put_TouchMask</span></span>](#put_touchmask) | <span data-ttu-id="488b1-217">设置指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="488b1-217">Set the TouchMask of the pointer event.</span></span>
[<span data-ttu-id="488b1-218">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="488b1-218">put_TouchOrientation</span></span>](#put_touchorientation) | <span data-ttu-id="488b1-219">设置指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="488b1-219">Set the TouchOrientation of the pointer event.</span></span>
[<span data-ttu-id="488b1-220">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="488b1-220">put_TouchPressure</span></span>](#put_touchpressure) | <span data-ttu-id="488b1-221">设置指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="488b1-221">Set the TouchPressure of the pointer event.</span></span>

<span data-ttu-id="488b1-222">它将获取所有三个字段中的字段，并排除某些 win32 特定的数据类型（如 HWND 和句柄）。</span><span class="sxs-lookup"><span data-stu-id="488b1-222">It takes fields from all three and excludes some win32 specific data types like HWND and HANDLE.</span></span> <span data-ttu-id="488b1-223">注意，sourceDevice 已被取出，但我们希望 PointerDeviceRect 和 DisplayRect 涵盖 sourceDevice 的现有使用情形。</span><span class="sxs-lookup"><span data-stu-id="488b1-223">Note, sourceDevice is taken out but we expect the PointerDeviceRect and DisplayRect to cover the existing use cases of sourceDevice.</span></span> <span data-ttu-id="488b1-224">另一个显著的区别是，任何点或 rect 位置都应位于 web 视图物理坐标中。</span><span class="sxs-lookup"><span data-stu-id="488b1-224">Another big difference is that any of the point or rect locations are expected to be in webview physical coordinates.</span></span> <span data-ttu-id="488b1-225">即，相对于 web 视图的坐标和未应用的 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="488b1-225">That is, coordinates relative to the webview and no DPI scaling applied.</span></span>

## <span data-ttu-id="488b1-226">成员</span><span class="sxs-lookup"><span data-stu-id="488b1-226">Members</span></span>

#### <span data-ttu-id="488b1-227">get_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="488b1-227">get_ButtonChangeKind</span></span> 

<span data-ttu-id="488b1-228">获取指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="488b1-228">Get the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="488b1-229">公共 HRESULT [get_ButtonChangeKind](#get_buttonchangekind)（INT32 \* ButtonChangeKind）</span><span class="sxs-lookup"><span data-stu-id="488b1-229">public HRESULT [get_ButtonChangeKind](#get_buttonchangekind)(INT32 \* buttonChangeKind)</span></span>

<span data-ttu-id="488b1-230">这对应于 POINTER_INFO 结构的 ButtonChangeKind 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-230">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="488b1-231">这些值由 Windows SDK 中的 POINTER_BUTTON_CHANGE_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="488b1-231">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-232">get_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="488b1-232">get_DisplayRect</span></span> 

<span data-ttu-id="488b1-233">获取在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="488b1-233">Get the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="488b1-234">public HRESULT [get_DisplayRect](#get_displayrect)（RECT \* DisplayRect）</span><span class="sxs-lookup"><span data-stu-id="488b1-234">public HRESULT [get_DisplayRect](#get_displayrect)(RECT \* displayRect)</span></span>

#### <span data-ttu-id="488b1-235">get_FrameId</span><span class="sxs-lookup"><span data-stu-id="488b1-235">get_FrameId</span></span> 

<span data-ttu-id="488b1-236">获取指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="488b1-236">Get the FrameID of the pointer event.</span></span>

> <span data-ttu-id="488b1-237">公共 HRESULT [get_FrameId](#get_frameid)（UINT32 \* FrameId）</span><span class="sxs-lookup"><span data-stu-id="488b1-237">public HRESULT [get_FrameId](#get_frameid)(UINT32 \* frameId)</span></span>

<span data-ttu-id="488b1-238">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 frameId 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-238">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-239">get_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="488b1-239">get_HimetricLocation</span></span> 

<span data-ttu-id="488b1-240">获取指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="488b1-240">Get the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="488b1-241">public HRESULT [get_HimetricLocation](#get_himetriclocation)（POINT \* HimetricLocation）</span><span class="sxs-lookup"><span data-stu-id="488b1-241">public HRESULT [get_HimetricLocation](#get_himetriclocation)(POINT \* himetricLocation)</span></span>

<span data-ttu-id="488b1-242">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-242">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-243">get_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="488b1-243">get_HimetricLocationRaw</span></span> 

<span data-ttu-id="488b1-244">获取指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="488b1-244">Get the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="488b1-245">public HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)（POINT \* HimetricLocationRaw）</span><span class="sxs-lookup"><span data-stu-id="488b1-245">public HRESULT [get_HimetricLocationRaw](#get_himetriclocationraw)(POINT \* himetricLocationRaw)</span></span>

<span data-ttu-id="488b1-246">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-246">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-247">get_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="488b1-247">get_HistoryCount</span></span> 

<span data-ttu-id="488b1-248">获取指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="488b1-248">Get the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="488b1-249">公共 HRESULT [get_HistoryCount](#get_historycount)（UINT32 \* HistoryCount）</span><span class="sxs-lookup"><span data-stu-id="488b1-249">public HRESULT [get_HistoryCount](#get_historycount)(UINT32 \* historyCount)</span></span>

<span data-ttu-id="488b1-250">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 historyCount 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-250">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-251">get_InputData</span><span class="sxs-lookup"><span data-stu-id="488b1-251">get_InputData</span></span> 

<span data-ttu-id="488b1-252">获取指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="488b1-252">Get the InputData of the pointer event.</span></span>

> <span data-ttu-id="488b1-253">公共 HRESULT [get_InputData](#get_inputdata)（INT32 \* InputData）</span><span class="sxs-lookup"><span data-stu-id="488b1-253">public HRESULT [get_InputData](#get_inputdata)(INT32 \* inputData)</span></span>

<span data-ttu-id="488b1-254">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 InputData 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-254">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-255">get_KeyStates</span><span class="sxs-lookup"><span data-stu-id="488b1-255">get_KeyStates</span></span> 

<span data-ttu-id="488b1-256">获取指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="488b1-256">Get the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="488b1-257">公共 HRESULT [get_KeyStates](#get_keystates)（DWORD \* KeyStates）</span><span class="sxs-lookup"><span data-stu-id="488b1-257">public HRESULT [get_KeyStates](#get_keystates)(DWORD \* keyStates)</span></span>

<span data-ttu-id="488b1-258">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwKeyStates 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-258">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-259">get_PenFlags</span><span class="sxs-lookup"><span data-stu-id="488b1-259">get_PenFlags</span></span> 

<span data-ttu-id="488b1-260">获取指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="488b1-260">Get the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="488b1-261">公共 HRESULT [get_PenFlags](#get_penflags)（UINT32 \* PenFlags）</span><span class="sxs-lookup"><span data-stu-id="488b1-261">public HRESULT [get_PenFlags](#get_penflags)(UINT32 \* penFLags)</span></span>

<span data-ttu-id="488b1-262">这对应于 POINTER_PEN_INFO 结构的 penFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-262">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="488b1-263">这些值由 Windows SDK 中的 PEN_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="488b1-263">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-264">get_PenMask</span><span class="sxs-lookup"><span data-stu-id="488b1-264">get_PenMask</span></span> 

<span data-ttu-id="488b1-265">获取指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="488b1-265">Get the PenMask of the pointer event.</span></span>

> <span data-ttu-id="488b1-266">公共 HRESULT [get_PenMask](#get_penmask)（UINT32 \* PenMask）</span><span class="sxs-lookup"><span data-stu-id="488b1-266">public HRESULT [get_PenMask](#get_penmask)(UINT32 \* penMask)</span></span>

<span data-ttu-id="488b1-267">这对应于 POINTER_PEN_INFO 结构的 penMask 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-267">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="488b1-268">这些值由 Windows SDK 中的 PEN_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="488b1-268">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-269">get_PenPressure</span><span class="sxs-lookup"><span data-stu-id="488b1-269">get_PenPressure</span></span> 

<span data-ttu-id="488b1-270">获取指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="488b1-270">Get the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="488b1-271">公共 HRESULT [get_PenPressure](#get_penpressure)（UINT32 \* PenPressure）</span><span class="sxs-lookup"><span data-stu-id="488b1-271">public HRESULT [get_PenPressure](#get_penpressure)(UINT32 \* penPressure)</span></span>

<span data-ttu-id="488b1-272">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-272">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-273">get_PenRotation</span><span class="sxs-lookup"><span data-stu-id="488b1-273">get_PenRotation</span></span> 

<span data-ttu-id="488b1-274">获取指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="488b1-274">Get the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="488b1-275">公共 HRESULT [get_PenRotation](#get_penrotation)（UINT32 \* PenRotation）</span><span class="sxs-lookup"><span data-stu-id="488b1-275">public HRESULT [get_PenRotation](#get_penrotation)(UINT32 \* penRotation)</span></span>

<span data-ttu-id="488b1-276">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的旋转属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-276">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-277">get_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="488b1-277">get_PenTiltX</span></span> 

<span data-ttu-id="488b1-278">获取指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="488b1-278">Get the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="488b1-279">公共 HRESULT [get_PenTiltX](#get_pentiltx)（INT32 \* PenTiltX）</span><span class="sxs-lookup"><span data-stu-id="488b1-279">public HRESULT [get_PenTiltX](#get_pentiltx)(INT32 \* penTiltX)</span></span>

<span data-ttu-id="488b1-280">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltX 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-280">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-281">get_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="488b1-281">get_PenTiltY</span></span> 

<span data-ttu-id="488b1-282">获取指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="488b1-282">Get the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="488b1-283">公共 HRESULT [get_PenTiltY](#get_pentilty)（INT32 \* PenTiltY）</span><span class="sxs-lookup"><span data-stu-id="488b1-283">public HRESULT [get_PenTiltY](#get_pentilty)(INT32 \* penTiltY)</span></span>

<span data-ttu-id="488b1-284">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltY 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-284">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-285">get_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="488b1-285">get_PerformanceCount</span></span> 

<span data-ttu-id="488b1-286">获取指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="488b1-286">Get the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="488b1-287">公共 HRESULT [get_PerformanceCount](#get_performancecount)（UINT64 \* PerformanceCount）</span><span class="sxs-lookup"><span data-stu-id="488b1-287">public HRESULT [get_PerformanceCount](#get_performancecount)(UINT64 \* performanceCount)</span></span>

<span data-ttu-id="488b1-288">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 PerformanceCount 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-288">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-289">get_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="488b1-289">get_PixelLocation</span></span> 

<span data-ttu-id="488b1-290">获取指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="488b1-290">Get the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="488b1-291">public HRESULT [get_PixelLocation](#get_pixellocation)（POINT \* PixelLocation）</span><span class="sxs-lookup"><span data-stu-id="488b1-291">public HRESULT [get_PixelLocation](#get_pixellocation)(POINT \* pixelLocation)</span></span>

<span data-ttu-id="488b1-292">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-292">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-293">get_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="488b1-293">get_PixelLocationRaw</span></span> 

<span data-ttu-id="488b1-294">获取指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="488b1-294">Get the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="488b1-295">public HRESULT [get_PixelLocationRaw](#get_pixellocationraw)（POINT \* PixelLocationRaw）</span><span class="sxs-lookup"><span data-stu-id="488b1-295">public HRESULT [get_PixelLocationRaw](#get_pixellocationraw)(POINT \* pixelLocationRaw)</span></span>

<span data-ttu-id="488b1-296">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-296">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-297">get_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="488b1-297">get_PointerDeviceRect</span></span> 

<span data-ttu-id="488b1-298">获取在 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="488b1-298">Get the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="488b1-299">public HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)（RECT \* PointerDeviceRect）</span><span class="sxs-lookup"><span data-stu-id="488b1-299">public HRESULT [get_PointerDeviceRect](#get_pointerdevicerect)(RECT \* pointerDeviceRect)</span></span>

#### <span data-ttu-id="488b1-300">get_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="488b1-300">get_PointerFlags</span></span> 

<span data-ttu-id="488b1-301">获取指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="488b1-301">Get the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="488b1-302">公共 HRESULT [get_PointerFlags](#get_pointerflags)（UINT32 \* PointerFlags）</span><span class="sxs-lookup"><span data-stu-id="488b1-302">public HRESULT [get_PointerFlags](#get_pointerflags)(UINT32 \* pointerFlags)</span></span>

<span data-ttu-id="488b1-303">这对应于 POINTER_INFO 结构的 pointerFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-303">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="488b1-304">这些值由 Windows SDK 中的 POINTER_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="488b1-304">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-305">get_PointerId</span><span class="sxs-lookup"><span data-stu-id="488b1-305">get_PointerId</span></span> 

<span data-ttu-id="488b1-306">获取指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="488b1-306">Get the PointerId of the pointer event.</span></span>

> <span data-ttu-id="488b1-307">公共 HRESULT [get_PointerId](#get_pointerid)（UINT32 \* PointerId）</span><span class="sxs-lookup"><span data-stu-id="488b1-307">public HRESULT [get_PointerId](#get_pointerid)(UINT32 \* pointerId)</span></span>

<span data-ttu-id="488b1-308">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 pointerId 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-308">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-309">get_PointerKind</span><span class="sxs-lookup"><span data-stu-id="488b1-309">get_PointerKind</span></span> 

<span data-ttu-id="488b1-310">获取指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="488b1-310">Get the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="488b1-311">公共 HRESULT [get_PointerKind](#get_pointerkind)（DWORD \* PointerKind）</span><span class="sxs-lookup"><span data-stu-id="488b1-311">public HRESULT [get_PointerKind](#get_pointerkind)(DWORD \* pointerKind)</span></span>

<span data-ttu-id="488b1-312">这对应于 POINTER_INFO 结构的 pointerKind 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-312">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="488b1-313">这些值由 Windows SDK 中的 POINTER_INPUT_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="488b1-313">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="488b1-314">支持 PT_PEN 和 PT_TOUCH。</span><span class="sxs-lookup"><span data-stu-id="488b1-314">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="488b1-315">get_Time</span><span class="sxs-lookup"><span data-stu-id="488b1-315">get_Time</span></span> 

<span data-ttu-id="488b1-316">获取指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="488b1-316">Get the Time of the pointer event.</span></span>

> <span data-ttu-id="488b1-317">公共 HRESULT [get_Time](#get_time)（DWORD \* 时间）</span><span class="sxs-lookup"><span data-stu-id="488b1-317">public HRESULT [get_Time](#get_time)(DWORD \* time)</span></span>

<span data-ttu-id="488b1-318">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwTime 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-318">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-319">get_TouchContact</span><span class="sxs-lookup"><span data-stu-id="488b1-319">get_TouchContact</span></span> 

<span data-ttu-id="488b1-320">获取指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="488b1-320">Get the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="488b1-321">public HRESULT [get_TouchContact](#get_touchcontact)（RECT \* TouchContact）</span><span class="sxs-lookup"><span data-stu-id="488b1-321">public HRESULT [get_TouchContact](#get_touchcontact)(RECT \* touchContact)</span></span>

<span data-ttu-id="488b1-322">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContact 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-322">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-323">get_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="488b1-323">get_TouchContactRaw</span></span> 

<span data-ttu-id="488b1-324">获取指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="488b1-324">Get the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="488b1-325">public HRESULT [get_TouchContactRaw](#get_touchcontactraw)（RECT \* TouchContactRaw）</span><span class="sxs-lookup"><span data-stu-id="488b1-325">public HRESULT [get_TouchContactRaw](#get_touchcontactraw)(RECT \* touchContactRaw)</span></span>

<span data-ttu-id="488b1-326">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContactRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-326">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-327">get_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="488b1-327">get_TouchFlags</span></span> 

<span data-ttu-id="488b1-328">获取指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="488b1-328">Get the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="488b1-329">公共 HRESULT [get_TouchFlags](#get_touchflags)（UINT32 \* TouchFlags）</span><span class="sxs-lookup"><span data-stu-id="488b1-329">public HRESULT [get_TouchFlags](#get_touchflags)(UINT32 \* touchFlags)</span></span>

<span data-ttu-id="488b1-330">这对应于 POINTER_TOUCH_INFO 结构的 touchFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-330">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="488b1-331">这些值由 Windows SDK 中的 TOUCH_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="488b1-331">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-332">get_TouchMask</span><span class="sxs-lookup"><span data-stu-id="488b1-332">get_TouchMask</span></span> 

<span data-ttu-id="488b1-333">获取指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="488b1-333">Get the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="488b1-334">公共 HRESULT [get_TouchMask](#get_touchmask)（UINT32 \* TouchMask）</span><span class="sxs-lookup"><span data-stu-id="488b1-334">public HRESULT [get_TouchMask](#get_touchmask)(UINT32 \* touchMask)</span></span>

<span data-ttu-id="488b1-335">这对应于 POINTER_TOUCH_INFO 结构的 touchMask 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-335">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="488b1-336">这些值由 Windows SDK 中的 TOUCH_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="488b1-336">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-337">get_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="488b1-337">get_TouchOrientation</span></span> 

<span data-ttu-id="488b1-338">获取指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="488b1-338">Get the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="488b1-339">公共 HRESULT [get_TouchOrientation](#get_touchorientation)（UINT32 \* TouchOrientation）</span><span class="sxs-lookup"><span data-stu-id="488b1-339">public HRESULT [get_TouchOrientation](#get_touchorientation)(UINT32 \* touchOrientation)</span></span>

<span data-ttu-id="488b1-340">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 "方向" 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-340">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-341">get_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="488b1-341">get_TouchPressure</span></span> 

<span data-ttu-id="488b1-342">获取指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="488b1-342">Get the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="488b1-343">公共 HRESULT [get_TouchPressure](#get_touchpressure)（UINT32 \* TouchPressure）</span><span class="sxs-lookup"><span data-stu-id="488b1-343">public HRESULT [get_TouchPressure](#get_touchpressure)(UINT32 \* touchPressure)</span></span>

<span data-ttu-id="488b1-344">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-344">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-345">put_ButtonChangeKind</span><span class="sxs-lookup"><span data-stu-id="488b1-345">put_ButtonChangeKind</span></span> 

<span data-ttu-id="488b1-346">设置指针事件的 ButtonChangeKind。</span><span class="sxs-lookup"><span data-stu-id="488b1-346">Set the ButtonChangeKind of the pointer event.</span></span>

> <span data-ttu-id="488b1-347">公共 HRESULT [put_ButtonChangeKind](#put_buttonchangekind)（INT32 ButtonChangeKind）</span><span class="sxs-lookup"><span data-stu-id="488b1-347">public HRESULT [put_ButtonChangeKind](#put_buttonchangekind)(INT32 buttonChangeKind)</span></span>

<span data-ttu-id="488b1-348">这对应于 POINTER_INFO 结构的 ButtonChangeKind 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-348">This corresponds to the ButtonChangeKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="488b1-349">这些值由 Windows SDK 中的 POINTER_BUTTON_CHANGE_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="488b1-349">The values are defined by the POINTER_BUTTON_CHANGE_KIND enum in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-350">put_DisplayRect</span><span class="sxs-lookup"><span data-stu-id="488b1-350">put_DisplayRect</span></span> 

<span data-ttu-id="488b1-351">按照 Windows SDK （winuser）中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 DisplayRect。</span><span class="sxs-lookup"><span data-stu-id="488b1-351">Set the DisplayRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="488b1-352">public HRESULT [put_DisplayRect](#put_displayrect)（RECT DisplayRect）</span><span class="sxs-lookup"><span data-stu-id="488b1-352">public HRESULT [put_DisplayRect](#put_displayrect)(RECT displayRect)</span></span>

#### <span data-ttu-id="488b1-353">put_FrameId</span><span class="sxs-lookup"><span data-stu-id="488b1-353">put_FrameId</span></span> 

<span data-ttu-id="488b1-354">设置指针事件的 FrameID。</span><span class="sxs-lookup"><span data-stu-id="488b1-354">Set the FrameID of the pointer event.</span></span>

> <span data-ttu-id="488b1-355">公共 HRESULT [put_FrameId](#put_frameid)（UINT32 FrameId）</span><span class="sxs-lookup"><span data-stu-id="488b1-355">public HRESULT [put_FrameId](#put_frameid)(UINT32 frameId)</span></span>

<span data-ttu-id="488b1-356">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 frameId 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-356">This corresponds to the frameId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-357">put_HimetricLocation</span><span class="sxs-lookup"><span data-stu-id="488b1-357">put_HimetricLocation</span></span> 

<span data-ttu-id="488b1-358">设置指针事件的 HimetricLocation。</span><span class="sxs-lookup"><span data-stu-id="488b1-358">Set the HimetricLocation of the pointer event.</span></span>

> <span data-ttu-id="488b1-359">public HRESULT [put_HimetricLocation](#put_himetriclocation)（POINT HimetricLocation）</span><span class="sxs-lookup"><span data-stu-id="488b1-359">public HRESULT [put_HimetricLocation](#put_himetriclocation)(POINT himetricLocation)</span></span>

<span data-ttu-id="488b1-360">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-360">This corresponds to the ptHimetricLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-361">put_HimetricLocationRaw</span><span class="sxs-lookup"><span data-stu-id="488b1-361">put_HimetricLocationRaw</span></span> 

<span data-ttu-id="488b1-362">设置指针事件的 HimetricLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="488b1-362">Set the HimetricLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="488b1-363">public HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)（POINT HimetricLocationRaw）</span><span class="sxs-lookup"><span data-stu-id="488b1-363">public HRESULT [put_HimetricLocationRaw](#put_himetriclocationraw)(POINT himetricLocationRaw)</span></span>

<span data-ttu-id="488b1-364">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptHimetricLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-364">This corresponds to the ptHimetricLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-365">put_HistoryCount</span><span class="sxs-lookup"><span data-stu-id="488b1-365">put_HistoryCount</span></span> 

<span data-ttu-id="488b1-366">设置指针事件的 HistoryCount。</span><span class="sxs-lookup"><span data-stu-id="488b1-366">Set the HistoryCount of the pointer event.</span></span>

> <span data-ttu-id="488b1-367">公共 HRESULT [put_HistoryCount](#put_historycount)（UINT32 HistoryCount）</span><span class="sxs-lookup"><span data-stu-id="488b1-367">public HRESULT [put_HistoryCount](#put_historycount)(UINT32 historyCount)</span></span>

<span data-ttu-id="488b1-368">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 historyCount 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-368">This corresponds to the historyCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-369">put_InputData</span><span class="sxs-lookup"><span data-stu-id="488b1-369">put_InputData</span></span> 

<span data-ttu-id="488b1-370">设置指针事件的 InputData。</span><span class="sxs-lookup"><span data-stu-id="488b1-370">Set the InputData of the pointer event.</span></span>

> <span data-ttu-id="488b1-371">公共 HRESULT [put_InputData](#put_inputdata)（INT32 InputData）</span><span class="sxs-lookup"><span data-stu-id="488b1-371">public HRESULT [put_InputData](#put_inputdata)(INT32 inputData)</span></span>

<span data-ttu-id="488b1-372">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 InputData 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-372">This corresponds to the InputData property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-373">put_KeyStates</span><span class="sxs-lookup"><span data-stu-id="488b1-373">put_KeyStates</span></span> 

<span data-ttu-id="488b1-374">设置指针事件的 KeyStates。</span><span class="sxs-lookup"><span data-stu-id="488b1-374">Set the KeyStates of the pointer event.</span></span>

> <span data-ttu-id="488b1-375">公共 HRESULT [put_KeyStates](#put_keystates)（DWORD KeyStates）</span><span class="sxs-lookup"><span data-stu-id="488b1-375">public HRESULT [put_KeyStates](#put_keystates)(DWORD keyStates)</span></span>

<span data-ttu-id="488b1-376">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwKeyStates 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-376">This corresponds to the dwKeyStates property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-377">put_PenFlags</span><span class="sxs-lookup"><span data-stu-id="488b1-377">put_PenFlags</span></span> 

<span data-ttu-id="488b1-378">设置指针事件的 PenFlags。</span><span class="sxs-lookup"><span data-stu-id="488b1-378">Set the PenFlags of the pointer event.</span></span>

> <span data-ttu-id="488b1-379">公共 HRESULT [put_PenFlags](#put_penflags)（UINT32 PenFlags）</span><span class="sxs-lookup"><span data-stu-id="488b1-379">public HRESULT [put_PenFlags](#put_penflags)(UINT32 penFLags)</span></span>

<span data-ttu-id="488b1-380">这对应于 POINTER_PEN_INFO 结构的 penFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-380">This corresponds to the penFlags property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="488b1-381">这些值由 Windows SDK 中的 PEN_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="488b1-381">The values are defined by the PEN_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-382">put_PenMask</span><span class="sxs-lookup"><span data-stu-id="488b1-382">put_PenMask</span></span> 

<span data-ttu-id="488b1-383">设置指针事件的 PenMask。</span><span class="sxs-lookup"><span data-stu-id="488b1-383">Set the PenMask of the pointer event.</span></span>

> <span data-ttu-id="488b1-384">公共 HRESULT [put_PenMask](#put_penmask)（UINT32 PenMask）</span><span class="sxs-lookup"><span data-stu-id="488b1-384">public HRESULT [put_PenMask](#put_penmask)(UINT32 penMask)</span></span>

<span data-ttu-id="488b1-385">这对应于 POINTER_PEN_INFO 结构的 penMask 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-385">This corresponds to the penMask property of the POINTER_PEN_INFO struct.</span></span> <span data-ttu-id="488b1-386">这些值由 Windows SDK 中的 PEN_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="488b1-386">The values are defined by the PEN_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-387">put_PenPressure</span><span class="sxs-lookup"><span data-stu-id="488b1-387">put_PenPressure</span></span> 

<span data-ttu-id="488b1-388">设置指针事件的 PenPressure。</span><span class="sxs-lookup"><span data-stu-id="488b1-388">Set the PenPressure of the pointer event.</span></span>

> <span data-ttu-id="488b1-389">公共 HRESULT [put_PenPressure](#put_penpressure)（UINT32 PenPressure）</span><span class="sxs-lookup"><span data-stu-id="488b1-389">public HRESULT [put_PenPressure](#put_penpressure)(UINT32 penPressure)</span></span>

<span data-ttu-id="488b1-390">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-390">This corresponds to the pressure property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-391">put_PenRotation</span><span class="sxs-lookup"><span data-stu-id="488b1-391">put_PenRotation</span></span> 

<span data-ttu-id="488b1-392">设置指针事件的 PenRotation。</span><span class="sxs-lookup"><span data-stu-id="488b1-392">Set the PenRotation of the pointer event.</span></span>

> <span data-ttu-id="488b1-393">公共 HRESULT [put_PenRotation](#put_penrotation)（UINT32 PenRotation）</span><span class="sxs-lookup"><span data-stu-id="488b1-393">public HRESULT [put_PenRotation](#put_penrotation)(UINT32 penRotation)</span></span>

<span data-ttu-id="488b1-394">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的旋转属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-394">This corresponds to the rotation property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-395">put_PenTiltX</span><span class="sxs-lookup"><span data-stu-id="488b1-395">put_PenTiltX</span></span> 

<span data-ttu-id="488b1-396">设置指针事件的 PenTiltX。</span><span class="sxs-lookup"><span data-stu-id="488b1-396">Set the PenTiltX of the pointer event.</span></span>

> <span data-ttu-id="488b1-397">公共 HRESULT [put_PenTiltX](#put_pentiltx)（INT32 PenTiltX）</span><span class="sxs-lookup"><span data-stu-id="488b1-397">public HRESULT [put_PenTiltX](#put_pentiltx)(INT32 penTiltX)</span></span>

<span data-ttu-id="488b1-398">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltX 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-398">This corresponds to the tiltX property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-399">put_PenTiltY</span><span class="sxs-lookup"><span data-stu-id="488b1-399">put_PenTiltY</span></span> 

<span data-ttu-id="488b1-400">设置指针事件的 PenTiltY。</span><span class="sxs-lookup"><span data-stu-id="488b1-400">Set the PenTiltY of the pointer event.</span></span>

> <span data-ttu-id="488b1-401">公共 HRESULT [put_PenTiltY](#put_pentilty)（INT32 PenTiltY）</span><span class="sxs-lookup"><span data-stu-id="488b1-401">public HRESULT [put_PenTiltY](#put_pentilty)(INT32 penTiltY)</span></span>

<span data-ttu-id="488b1-402">这对应于 Windows SDK （winuser）中定义的 POINTER_PEN_INFO 结构的 tiltY 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-402">This corresponds to the tiltY property of the POINTER_PEN_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-403">put_PerformanceCount</span><span class="sxs-lookup"><span data-stu-id="488b1-403">put_PerformanceCount</span></span> 

<span data-ttu-id="488b1-404">设置指针事件的 PerformanceCount。</span><span class="sxs-lookup"><span data-stu-id="488b1-404">Set the PerformanceCount of the pointer event.</span></span>

> <span data-ttu-id="488b1-405">公共 HRESULT [put_PerformanceCount](#put_performancecount)（UINT64 PerformanceCount）</span><span class="sxs-lookup"><span data-stu-id="488b1-405">public HRESULT [put_PerformanceCount](#put_performancecount)(UINT64 performanceCount)</span></span>

<span data-ttu-id="488b1-406">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 PerformanceCount 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-406">This corresponds to the PerformanceCount property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-407">put_PixelLocation</span><span class="sxs-lookup"><span data-stu-id="488b1-407">put_PixelLocation</span></span> 

<span data-ttu-id="488b1-408">设置指针事件的 PixelLocation。</span><span class="sxs-lookup"><span data-stu-id="488b1-408">Set the PixelLocation of the pointer event.</span></span>

> <span data-ttu-id="488b1-409">public HRESULT [put_PixelLocation](#put_pixellocation)（POINT PixelLocation）</span><span class="sxs-lookup"><span data-stu-id="488b1-409">public HRESULT [put_PixelLocation](#put_pixellocation)(POINT pixelLocation)</span></span>

<span data-ttu-id="488b1-410">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocation 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-410">This corresponds to the ptPixelLocation property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-411">put_PixelLocationRaw</span><span class="sxs-lookup"><span data-stu-id="488b1-411">put_PixelLocationRaw</span></span> 

<span data-ttu-id="488b1-412">设置指针事件的 PixelLocationRaw。</span><span class="sxs-lookup"><span data-stu-id="488b1-412">Set the PixelLocationRaw of the pointer event.</span></span>

> <span data-ttu-id="488b1-413">public HRESULT [put_PixelLocationRaw](#put_pixellocationraw)（POINT PixelLocationRaw）</span><span class="sxs-lookup"><span data-stu-id="488b1-413">public HRESULT [put_PixelLocationRaw](#put_pixellocationraw)(POINT pixelLocationRaw)</span></span>

<span data-ttu-id="488b1-414">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 ptPixelLocationRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-414">This corresponds to the ptPixelLocationRaw property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-415">put_PointerDeviceRect</span><span class="sxs-lookup"><span data-stu-id="488b1-415">put_PointerDeviceRect</span></span> 

<span data-ttu-id="488b1-416">按照 Windows SDK （winuser）中的定义，设置 POINTER_INFO 结构的 sourceDevice 属性的 PointerDeviceRect。</span><span class="sxs-lookup"><span data-stu-id="488b1-416">Set the PointerDeviceRect of the sourceDevice property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

> <span data-ttu-id="488b1-417">public HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)（RECT PointerDeviceRect）</span><span class="sxs-lookup"><span data-stu-id="488b1-417">public HRESULT [put_PointerDeviceRect](#put_pointerdevicerect)(RECT pointerDeviceRect)</span></span>

#### <span data-ttu-id="488b1-418">put_PointerFlags</span><span class="sxs-lookup"><span data-stu-id="488b1-418">put_PointerFlags</span></span> 

<span data-ttu-id="488b1-419">设置指针事件的 PointerFlags。</span><span class="sxs-lookup"><span data-stu-id="488b1-419">Set the PointerFlags of the pointer event.</span></span>

> <span data-ttu-id="488b1-420">公共 HRESULT [put_PointerFlags](#put_pointerflags)（UINT32 PointerFlags）</span><span class="sxs-lookup"><span data-stu-id="488b1-420">public HRESULT [put_PointerFlags](#put_pointerflags)(UINT32 pointerFlags)</span></span>

<span data-ttu-id="488b1-421">这对应于 POINTER_INFO 结构的 pointerFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-421">This corresponds to the pointerFlags property of the POINTER_INFO struct.</span></span> <span data-ttu-id="488b1-422">这些值由 Windows SDK 中的 POINTER_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="488b1-422">The values are defined by the POINTER_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-423">put_PointerId</span><span class="sxs-lookup"><span data-stu-id="488b1-423">put_PointerId</span></span> 

<span data-ttu-id="488b1-424">设置指针事件的 PointerId。</span><span class="sxs-lookup"><span data-stu-id="488b1-424">Set the PointerId of the pointer event.</span></span>

> <span data-ttu-id="488b1-425">公共 HRESULT [put_PointerId](#put_pointerid)（UINT32 PointerId）</span><span class="sxs-lookup"><span data-stu-id="488b1-425">public HRESULT [put_PointerId](#put_pointerid)(UINT32 pointerId)</span></span>

<span data-ttu-id="488b1-426">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 pointerId 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-426">This corresponds to the pointerId property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-427">put_PointerKind</span><span class="sxs-lookup"><span data-stu-id="488b1-427">put_PointerKind</span></span> 

<span data-ttu-id="488b1-428">设置指针事件的 PointerKind。</span><span class="sxs-lookup"><span data-stu-id="488b1-428">Set the PointerKind of the pointer event.</span></span>

> <span data-ttu-id="488b1-429">公共 HRESULT [put_PointerKind](#put_pointerkind)（DWORD PointerKind）</span><span class="sxs-lookup"><span data-stu-id="488b1-429">public HRESULT [put_PointerKind](#put_pointerkind)(DWORD pointerKind)</span></span>

<span data-ttu-id="488b1-430">这对应于 POINTER_INFO 结构的 pointerKind 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-430">This corresponds to the pointerKind property of the POINTER_INFO struct.</span></span> <span data-ttu-id="488b1-431">这些值由 Windows SDK 中的 POINTER_INPUT_KIND 枚举（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="488b1-431">The values are defined by the POINTER_INPUT_KIND enum in the Windows SDK (winuser.h).</span></span> <span data-ttu-id="488b1-432">支持 PT_PEN 和 PT_TOUCH。</span><span class="sxs-lookup"><span data-stu-id="488b1-432">Supports PT_PEN and PT_TOUCH.</span></span>

#### <span data-ttu-id="488b1-433">put_Time</span><span class="sxs-lookup"><span data-stu-id="488b1-433">put_Time</span></span> 

<span data-ttu-id="488b1-434">设置指针事件的时间。</span><span class="sxs-lookup"><span data-stu-id="488b1-434">Set the Time of the pointer event.</span></span>

> <span data-ttu-id="488b1-435">公共 HRESULT [put_Time](#put_time)（DWORD 时间）</span><span class="sxs-lookup"><span data-stu-id="488b1-435">public HRESULT [put_Time](#put_time)(DWORD time)</span></span>

<span data-ttu-id="488b1-436">这对应于 Windows SDK （winuser）中定义的 POINTER_INFO 结构的 dwTime 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-436">This corresponds to the dwTime property of the POINTER_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-437">put_TouchContact</span><span class="sxs-lookup"><span data-stu-id="488b1-437">put_TouchContact</span></span> 

<span data-ttu-id="488b1-438">设置指针事件的 TouchContact。</span><span class="sxs-lookup"><span data-stu-id="488b1-438">Set the TouchContact of the pointer event.</span></span>

> <span data-ttu-id="488b1-439">public HRESULT [put_TouchContact](#put_touchcontact)（RECT TouchContact）</span><span class="sxs-lookup"><span data-stu-id="488b1-439">public HRESULT [put_TouchContact](#put_touchcontact)(RECT touchContact)</span></span>

<span data-ttu-id="488b1-440">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContact 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-440">This corresponds to the rcContact property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-441">put_TouchContactRaw</span><span class="sxs-lookup"><span data-stu-id="488b1-441">put_TouchContactRaw</span></span> 

<span data-ttu-id="488b1-442">设置指针事件的 TouchContactRaw。</span><span class="sxs-lookup"><span data-stu-id="488b1-442">Set the TouchContactRaw of the pointer event.</span></span>

> <span data-ttu-id="488b1-443">public HRESULT [put_TouchContactRaw](#put_touchcontactraw)（RECT TouchContactRaw）</span><span class="sxs-lookup"><span data-stu-id="488b1-443">public HRESULT [put_TouchContactRaw](#put_touchcontactraw)(RECT touchContactRaw)</span></span>

<span data-ttu-id="488b1-444">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 rcContactRaw 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-444">This corresponds to the rcContactRaw property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-445">put_TouchFlags</span><span class="sxs-lookup"><span data-stu-id="488b1-445">put_TouchFlags</span></span> 

<span data-ttu-id="488b1-446">设置指针事件的 TouchFlags。</span><span class="sxs-lookup"><span data-stu-id="488b1-446">Set the TouchFlags of the pointer event.</span></span>

> <span data-ttu-id="488b1-447">公共 HRESULT [put_TouchFlags](#put_touchflags)（UINT32 TouchFlags）</span><span class="sxs-lookup"><span data-stu-id="488b1-447">public HRESULT [put_TouchFlags](#put_touchflags)(UINT32 touchFlags)</span></span>

<span data-ttu-id="488b1-448">这对应于 POINTER_TOUCH_INFO 结构的 touchFlags 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-448">This corresponds to the touchFlags property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="488b1-449">这些值由 Windows SDK 中的 TOUCH_FLAGS 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="488b1-449">The values are defined by the TOUCH_FLAGS constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-450">put_TouchMask</span><span class="sxs-lookup"><span data-stu-id="488b1-450">put_TouchMask</span></span> 

<span data-ttu-id="488b1-451">设置指针事件的 TouchMask。</span><span class="sxs-lookup"><span data-stu-id="488b1-451">Set the TouchMask of the pointer event.</span></span>

> <span data-ttu-id="488b1-452">公共 HRESULT [put_TouchMask](#put_touchmask)（UINT32 TouchMask）</span><span class="sxs-lookup"><span data-stu-id="488b1-452">public HRESULT [put_TouchMask](#put_touchmask)(UINT32 touchMask)</span></span>

<span data-ttu-id="488b1-453">这对应于 POINTER_TOUCH_INFO 结构的 touchMask 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-453">This corresponds to the touchMask property of the POINTER_TOUCH_INFO struct.</span></span> <span data-ttu-id="488b1-454">这些值由 Windows SDK 中的 TOUCH_MASK 常量（winuser）定义。</span><span class="sxs-lookup"><span data-stu-id="488b1-454">The values are defined by the TOUCH_MASK constants in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-455">put_TouchOrientation</span><span class="sxs-lookup"><span data-stu-id="488b1-455">put_TouchOrientation</span></span> 

<span data-ttu-id="488b1-456">设置指针事件的 TouchOrientation。</span><span class="sxs-lookup"><span data-stu-id="488b1-456">Set the TouchOrientation of the pointer event.</span></span>

> <span data-ttu-id="488b1-457">公共 HRESULT [put_TouchOrientation](#put_touchorientation)（UINT32 TouchOrientation）</span><span class="sxs-lookup"><span data-stu-id="488b1-457">public HRESULT [put_TouchOrientation](#put_touchorientation)(UINT32 touchOrientation)</span></span>

<span data-ttu-id="488b1-458">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的 "方向" 属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-458">This corresponds to the orientation property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

#### <span data-ttu-id="488b1-459">put_TouchPressure</span><span class="sxs-lookup"><span data-stu-id="488b1-459">put_TouchPressure</span></span> 

<span data-ttu-id="488b1-460">设置指针事件的 TouchPressure。</span><span class="sxs-lookup"><span data-stu-id="488b1-460">Set the TouchPressure of the pointer event.</span></span>

> <span data-ttu-id="488b1-461">公共 HRESULT [put_TouchPressure](#put_touchpressure)（UINT32 TouchPressure）</span><span class="sxs-lookup"><span data-stu-id="488b1-461">public HRESULT [put_TouchPressure](#put_touchpressure)(UINT32 touchPressure)</span></span>

<span data-ttu-id="488b1-462">这对应于 Windows SDK （winuser）中定义的 POINTER_TOUCH_INFO 结构的压力属性。</span><span class="sxs-lookup"><span data-stu-id="488b1-462">This corresponds to the pressure property of the POINTER_TOUCH_INFO struct as defined in the Windows SDK (winuser.h).</span></span>

