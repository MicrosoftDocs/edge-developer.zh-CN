---
title: 在 Microsoft Edge DevTools 中通过设备模式模拟移动设备
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 10c1ee12777965778ebec2d257399dc231e2a01a
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607424"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->





# <span data-ttu-id="2e014-103">在 Microsoft Edge DevTools 中通过设备模式模拟移动设备</span><span class="sxs-lookup"><span data-stu-id="2e014-103">Simulate Mobile Devices with Device Mode in Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="2e014-104">使用 "设备" 模式来大致了解页面在移动设备上的外观和执行方式。</span><span class="sxs-lookup"><span data-stu-id="2e014-104">Use Device Mode to approximate how your page looks and performs on a mobile device.</span></span>  

<span data-ttu-id="2e014-105">设备模式是 Microsoft Edge DevTools 中的松散功能集的名称，可帮助你模拟移动设备。</span><span class="sxs-lookup"><span data-stu-id="2e014-105">Device Mode is the name for the loose collection of features in Microsoft Edge DevTools that help you simulate mobile devices.</span></span>  <span data-ttu-id="2e014-106">这些功能包括：</span><span class="sxs-lookup"><span data-stu-id="2e014-106">These features include:</span></span>  

*   [<span data-ttu-id="2e014-107">模拟移动视区</span><span class="sxs-lookup"><span data-stu-id="2e014-107">Simulating a mobile viewport</span></span>](#simulate-a-mobile-viewport)  
*   [<span data-ttu-id="2e014-108">限制网络</span><span class="sxs-lookup"><span data-stu-id="2e014-108">Throttling the network</span></span>](#throttle-the-network-only)  
*   [<span data-ttu-id="2e014-109">调节 CPU</span><span class="sxs-lookup"><span data-stu-id="2e014-109">Throttling the CPU</span></span>](#throttle-the-cpu-only)  
*   [<span data-ttu-id="2e014-110">模拟地理位置</span><span class="sxs-lookup"><span data-stu-id="2e014-110">Simulating geolocation</span></span>](#override-geolocation)  
*   [<span data-ttu-id="2e014-111">设置方向</span><span class="sxs-lookup"><span data-stu-id="2e014-111">Setting orientation</span></span>](#set-orientation)  

## <span data-ttu-id="2e014-112">限制</span><span class="sxs-lookup"><span data-stu-id="2e014-112">Limitations</span></span>   

<span data-ttu-id="2e014-113">将设备模式视为对移动设备上的页面外观和感觉的[第一顺序近似值][WikiApproximation]。</span><span class="sxs-lookup"><span data-stu-id="2e014-113">Think of Device Mode as a [first-order approximation][WikiApproximation] of how your page looks and feels on a mobile device.</span></span>  <span data-ttu-id="2e014-114">使用设备模式时，实际上并不是在移动设备上运行代码。</span><span class="sxs-lookup"><span data-stu-id="2e014-114">With Device Mode you do not actually run your code on a mobile device.</span></span>  <span data-ttu-id="2e014-115">您可以从便携式计算机或桌面模拟移动用户体验。</span><span class="sxs-lookup"><span data-stu-id="2e014-115">You simulate the mobile user experience from your laptop or desktop.</span></span>  

<span data-ttu-id="2e014-116">移动设备的某些方面 DevTools 将永远无法模拟。</span><span class="sxs-lookup"><span data-stu-id="2e014-116">There are some aspects of mobile devices that DevTools will never be able to simulate.</span></span>  <span data-ttu-id="2e014-117">例如，移动 Cpu 的体系结构与便携式计算机或桌面 Cpu 的体系结构非常不同。</span><span class="sxs-lookup"><span data-stu-id="2e014-117">For example, the architecture of mobile CPUs is very different than the architecture of laptop or desktop CPUs.</span></span>  <span data-ttu-id="2e014-118">如果有疑问，最佳做法是在移动设备上实际运行您的页面。</span><span class="sxs-lookup"><span data-stu-id="2e014-118">When in doubt, your best bet is to actually run your page on a mobile device.</span></span>  <span data-ttu-id="2e014-119">使用 [远程调试] [DevToolsRemoteDebugging] 查看、更改、调试和分析来自便携式计算机或桌面的页面的代码，同时它实际上在移动设备上运行。</span><span class="sxs-lookup"><span data-stu-id="2e014-119">Use [Remote Debugging][DevToolsRemoteDebugging] to view, change, debug, and profile the code of a page from your laptop or desktop while it actually runs on a mobile device.</span></span>  

## <span data-ttu-id="2e014-120">模拟移动视区</span><span class="sxs-lookup"><span data-stu-id="2e014-120">Simulate a mobile viewport</span></span>   

<span data-ttu-id="2e014-121">单击 "**切换设备" 工具栏**上 ![ 的 "切换设备" 工具栏 ][ImageDeviceToolbarIcon] 以打开可让你模拟移动视区的 UI。</span><span class="sxs-lookup"><span data-stu-id="2e014-121">Click **Toggle Device Toolbar** ![Toggle Device Toolbar][ImageDeviceToolbarIcon] to open the UI that enables you to simulate a mobile viewport.</span></span>  

> ##### <span data-ttu-id="2e014-122">图 1</span><span class="sxs-lookup"><span data-stu-id="2e014-122">Figure 1</span></span>  
> <span data-ttu-id="2e014-123">"设备" 工具栏</span><span class="sxs-lookup"><span data-stu-id="2e014-123">The Device Toolbar</span></span>  
> !["设备" 工具栏][ImageDeviceToolbar]  

<span data-ttu-id="2e014-125">默认情况下，设备工具栏将在 "响应式" 视区模式下打开。</span><span class="sxs-lookup"><span data-stu-id="2e014-125">By default the Device Toolbar opens in Responsive Viewport Mode.</span></span>  

### <span data-ttu-id="2e014-126">响应式视区模式</span><span class="sxs-lookup"><span data-stu-id="2e014-126">Responsive Viewport Mode</span></span>   

<span data-ttu-id="2e014-127">拖动图柄以将视区大小调整为所需的任何尺寸。</span><span class="sxs-lookup"><span data-stu-id="2e014-127">Drag the handles to resize the viewport to whatever dimensions you need.</span></span>  <span data-ttu-id="2e014-128">或者，在 "宽度" 和 "高度" 框中输入特定值。</span><span class="sxs-lookup"><span data-stu-id="2e014-128">Or, enter specific values in the width and height boxes.</span></span>  <span data-ttu-id="2e014-129">在[图 2](#figure-2)中，width 设置为 `626` ，高度设置为 `516` 。</span><span class="sxs-lookup"><span data-stu-id="2e014-129">In [Figure 2](#figure-2), the width is set to `626` and the height is set to `516`.</span></span>  

> ##### <span data-ttu-id="2e014-130">图 2</span><span class="sxs-lookup"><span data-stu-id="2e014-130">Figure 2</span></span>  
> <span data-ttu-id="2e014-131">在 "响应" 视口模式下更改视区尺寸的控制滑块</span><span class="sxs-lookup"><span data-stu-id="2e014-131">The handles for changing the dimensions of the viewport when in Responsive Viewport Mode</span></span>  
> ![在 "响应" 视口模式下更改视区尺寸的控制滑块][ImageResponsiveHandles]  

#### <span data-ttu-id="2e014-133">显示媒体查询</span><span class="sxs-lookup"><span data-stu-id="2e014-133">Show media queries</span></span>   

<span data-ttu-id="2e014-134">若要在视区上方显示媒体查询断点，请单击 "**更多选项**"，然后选择 "**显示媒体查询**"。</span><span class="sxs-lookup"><span data-stu-id="2e014-134">To show media query breakpoints above your viewport, click **More options** and then select **Show media queries**.</span></span>  

> ##### <span data-ttu-id="2e014-135">图 3</span><span class="sxs-lookup"><span data-stu-id="2e014-135">Figure 3</span></span>  
> <span data-ttu-id="2e014-136">显示媒体查询</span><span class="sxs-lookup"><span data-stu-id="2e014-136">Show media queries</span></span>  
> ![显示媒体查询][ImageShowMediaQueries]  

<span data-ttu-id="2e014-138">单击断点以更改视区的宽度，以便触发断点。</span><span class="sxs-lookup"><span data-stu-id="2e014-138">Click a breakpoint to change the width of the viewport so that the breakpoint gets triggered.</span></span>  

> ##### <span data-ttu-id="2e014-139">图 4</span><span class="sxs-lookup"><span data-stu-id="2e014-139">Figure 4</span></span>  
> <span data-ttu-id="2e014-140">单击断点以更改视区的宽度</span><span class="sxs-lookup"><span data-stu-id="2e014-140">Click a breakpoint to change the width of the viewport</span></span>  
> ![单击断点以更改视区的宽度][ImageBreakpoint]  

#### <span data-ttu-id="2e014-142">设置设备类型</span><span class="sxs-lookup"><span data-stu-id="2e014-142">Set the device type</span></span>   

<span data-ttu-id="2e014-143">使用**设备类型**列表来模拟移动设备或桌面设备。</span><span class="sxs-lookup"><span data-stu-id="2e014-143">Use the **Device Type** list to simulate a mobile device or desktop device.</span></span>  

> ##### <span data-ttu-id="2e014-144">图 5</span><span class="sxs-lookup"><span data-stu-id="2e014-144">Figure 5</span></span>  
> <span data-ttu-id="2e014-145">**设备类型**列表</span><span class="sxs-lookup"><span data-stu-id="2e014-145">The **Device Type** list</span></span>  
> ![设备类型列表][ImageDeviceType]  

<span data-ttu-id="2e014-147">下表描述了选项之间的差异。</span><span class="sxs-lookup"><span data-stu-id="2e014-147">The table below describes the differences between the options.</span></span>  <span data-ttu-id="2e014-148">**呈现方法**是指 Microsoft Edge 是否将页面呈现为移动设备或桌面视区。</span><span class="sxs-lookup"><span data-stu-id="2e014-148">**Rendering method** refers to whether Microsoft Edge renders the page as a mobile or desktop viewport.</span></span>  <span data-ttu-id="2e014-149">**光标图标**指将鼠标悬停在页面上时看到的光标类型。</span><span class="sxs-lookup"><span data-stu-id="2e014-149">**Cursor icon** refers to what type of cursor you see when you hover over the page.</span></span>  <span data-ttu-id="2e014-150">**激发的事件**是指 `touch` `click` 当您与页面交互时页面是引发还是事件。</span><span class="sxs-lookup"><span data-stu-id="2e014-150">**Events fired** refers to whether the page fires `touch` or `click` events when you interact with the page.</span></span>  

| <span data-ttu-id="2e014-151">选项</span><span class="sxs-lookup"><span data-stu-id="2e014-151">Option</span></span> | <span data-ttu-id="2e014-152">呈现方法</span><span class="sxs-lookup"><span data-stu-id="2e014-152">Rendering method</span></span> | <span data-ttu-id="2e014-153">光标图标</span><span class="sxs-lookup"><span data-stu-id="2e014-153">Cursor icon</span></span> | <span data-ttu-id="2e014-154">激发的事件</span><span class="sxs-lookup"><span data-stu-id="2e014-154">Events fired</span></span> |  
|:--- |:--- |:--- |:--- |  
| <span data-ttu-id="2e014-155">移动版</span><span class="sxs-lookup"><span data-stu-id="2e014-155">Mobile</span></span> | <span data-ttu-id="2e014-156">移动版</span><span class="sxs-lookup"><span data-stu-id="2e014-156">Mobile</span></span> | <span data-ttu-id="2e014-157">圆形</span><span class="sxs-lookup"><span data-stu-id="2e014-157">Circle</span></span> | <span data-ttu-id="2e014-158">触摸</span><span class="sxs-lookup"><span data-stu-id="2e014-158">touch</span></span> |  
| <span data-ttu-id="2e014-159">移动 \ （无接触 \）</span><span class="sxs-lookup"><span data-stu-id="2e014-159">Mobile \(no touch\)</span></span> | <span data-ttu-id="2e014-160">移动版</span><span class="sxs-lookup"><span data-stu-id="2e014-160">Mobile</span></span> | <span data-ttu-id="2e014-161">正常</span><span class="sxs-lookup"><span data-stu-id="2e014-161">Normal</span></span> | <span data-ttu-id="2e014-162">单击</span><span class="sxs-lookup"><span data-stu-id="2e014-162">click</span></span> |  
| <span data-ttu-id="2e014-163">桌面</span><span class="sxs-lookup"><span data-stu-id="2e014-163">Desktop</span></span> | <span data-ttu-id="2e014-164">桌面</span><span class="sxs-lookup"><span data-stu-id="2e014-164">Desktop</span></span> | <span data-ttu-id="2e014-165">正常</span><span class="sxs-lookup"><span data-stu-id="2e014-165">Normal</span></span> | <span data-ttu-id="2e014-166">单击</span><span class="sxs-lookup"><span data-stu-id="2e014-166">click</span></span> |  
| <span data-ttu-id="2e014-167">桌面版 \ （触摸 \）</span><span class="sxs-lookup"><span data-stu-id="2e014-167">Desktop \(touch\)</span></span> | <span data-ttu-id="2e014-168">桌面</span><span class="sxs-lookup"><span data-stu-id="2e014-168">Desktop</span></span> | <span data-ttu-id="2e014-169">圆形</span><span class="sxs-lookup"><span data-stu-id="2e014-169">Circle</span></span> | <span data-ttu-id="2e014-170">触摸</span><span class="sxs-lookup"><span data-stu-id="2e014-170">touch</span></span> |  

> [!NOTE]
> <span data-ttu-id="2e014-171">如果看不到 "**设备类型**" 列表，请单击 "**更多选项**"，然后选择 "**添加设备类型**"。</span><span class="sxs-lookup"><span data-stu-id="2e014-171">If you do not see the **Device Type** list, click **More options** and select **Add device type**.</span></span>  

### <span data-ttu-id="2e014-172">移动设备视区模式</span><span class="sxs-lookup"><span data-stu-id="2e014-172">Mobile Device Viewport Mode</span></span>   

<span data-ttu-id="2e014-173">若要模拟特定移动设备的尺寸，请从**设备**列表中选择该设备。</span><span class="sxs-lookup"><span data-stu-id="2e014-173">To simulate the dimensions of a specific mobile device, select the device from the **Device** list.</span></span>  

> ##### <span data-ttu-id="2e014-174">图 6</span><span class="sxs-lookup"><span data-stu-id="2e014-174">Figure 6</span></span>  
> <span data-ttu-id="2e014-175">设备列表</span><span class="sxs-lookup"><span data-stu-id="2e014-175">The Device list</span></span>  
> ![设备列表][ImageDeviceList]  

#### <span data-ttu-id="2e014-177">将视区旋转到横向方向</span><span class="sxs-lookup"><span data-stu-id="2e014-177">Rotate the viewport to landscape orientation</span></span>   

<span data-ttu-id="2e014-178">单击 "**旋转** ![ 旋转 ][ImageRotateIcon] "，将视区旋转到横向方向。</span><span class="sxs-lookup"><span data-stu-id="2e014-178">Click **Rotate** ![Rotate][ImageRotateIcon] to rotate the viewport to landscape orientation.</span></span>  

> ##### <span data-ttu-id="2e014-179">图 7</span><span class="sxs-lookup"><span data-stu-id="2e014-179">Figure 7</span></span>  
> <span data-ttu-id="2e014-180">横向方向</span><span class="sxs-lookup"><span data-stu-id="2e014-180">Landscape orientation</span></span>  
> ![横向方向][ImageLandscape]  

> [!NOTE]
> <span data-ttu-id="2e014-182">如果**设备工具栏**较窄，"**旋转**" 按钮将消失。</span><span class="sxs-lookup"><span data-stu-id="2e014-182">The **Rotate** button disappears if your **Device Toolbar** is narrow.</span></span>  

> ##### <span data-ttu-id="2e014-183">图 8</span><span class="sxs-lookup"><span data-stu-id="2e014-183">Figure 8</span></span>  
> <span data-ttu-id="2e014-184">"设备" 工具栏</span><span class="sxs-lookup"><span data-stu-id="2e014-184">The Device Toolbar</span></span>  
> !["设备" 工具栏][ImageDeviceToolbar2]  

<span data-ttu-id="2e014-186">另请参阅[设置方向](#set-orientation)。</span><span class="sxs-lookup"><span data-stu-id="2e014-186">See also [Set orientation](#set-orientation).</span></span>  

#### <span data-ttu-id="2e014-187">显示设备帧</span><span class="sxs-lookup"><span data-stu-id="2e014-187">Show device frame</span></span>   

<span data-ttu-id="2e014-188">模拟一个特定移动设备（如 iPhone 6）的尺寸时，打开 "**更多选项**"，然后选择 "**显示设备帧**" 以显示视区周围的物理设备帧。</span><span class="sxs-lookup"><span data-stu-id="2e014-188">When simulating the dimensions of a specific mobile device like an iPhone 6, open **More options** and then select **Show device frame** to show the physical device frame around the viewport.</span></span>  

> [!NOTE]
> <span data-ttu-id="2e014-189">如果您没有看到特定设备的设备框架，则可能意味着 DevTools 只对该特定选项没有艺术。</span><span class="sxs-lookup"><span data-stu-id="2e014-189">If you do not see a device frame for a particular device, it probably means that DevTools just does not have art for that specific option.</span></span>  

> ##### <span data-ttu-id="2e014-190">图 9</span><span class="sxs-lookup"><span data-stu-id="2e014-190">Figure 9</span></span>  
> <span data-ttu-id="2e014-191">显示设备帧</span><span class="sxs-lookup"><span data-stu-id="2e014-191">Show device frame</span></span>  
> ![显示设备帧][ImageShowDeviceFrame]  

> ##### <span data-ttu-id="2e014-193">图 10</span><span class="sxs-lookup"><span data-stu-id="2e014-193">Figure 10</span></span>  
> <span data-ttu-id="2e014-194">IPhone 6 的设备帧</span><span class="sxs-lookup"><span data-stu-id="2e014-194">The device frame for the iPhone 6</span></span>  
> ![IPhone 6 的设备帧][ImageIphoneFrame]  

#### <span data-ttu-id="2e014-196">添加自定义移动设备</span><span class="sxs-lookup"><span data-stu-id="2e014-196">Add a custom mobile device</span></span>   

<span data-ttu-id="2e014-197">要添加自定义设备，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2e014-197">To add a custom device:</span></span>  

1.  <span data-ttu-id="2e014-198">单击 "**设备**" 列表，然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="2e014-198">Click the **Device** list and then select **Edit**.</span></span>  

> ##### <span data-ttu-id="2e014-199">图 11</span><span class="sxs-lookup"><span data-stu-id="2e014-199">Figure 11</span></span>  
> <span data-ttu-id="2e014-200">选择 "**编辑**" 
> ![ 选择 "编辑"][ImageEdit]</span><span class="sxs-lookup"><span data-stu-id="2e014-200">Selecting **Edit**
![Selecting Edit][ImageEdit]</span></span>  

1.  <span data-ttu-id="2e014-201">单击 "**添加自定义设备**"。</span><span class="sxs-lookup"><span data-stu-id="2e014-201">Click **Add custom device**.</span></span>  

1.  <span data-ttu-id="2e014-202">输入设备的名称、宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="2e014-202">Enter a name, width, and height for the device.</span></span>  <span data-ttu-id="2e014-203">[设备像素比率][MDNWindowDevicePixelRatio]、[用户代理字符串][MDNUserAgent]和[设备类型](#set-the-device-type)字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="2e014-203">The [device pixel ratio][MDNWindowDevicePixelRatio], [user agent string][MDNUserAgent], and [device type](#set-the-device-type) fields are optional.</span></span>  <span data-ttu-id="2e014-204">"设备类型" 字段是默认情况下设置为 "**移动电话**" 的列表。</span><span class="sxs-lookup"><span data-stu-id="2e014-204">The device type field is the list that is set to **Mobile** by default.</span></span>  

> ##### <span data-ttu-id="2e014-205">图 12</span><span class="sxs-lookup"><span data-stu-id="2e014-205">Figure 12</span></span>  
> <span data-ttu-id="2e014-206">创建自定义设备</span><span class="sxs-lookup"><span data-stu-id="2e014-206">Creating a custom device</span></span>  
> ![创建自定义设备][ImageAddCustomDevice]  

### <span data-ttu-id="2e014-208">显示标尺</span><span class="sxs-lookup"><span data-stu-id="2e014-208">Show rulers</span></span>   

<span data-ttu-id="2e014-209">单击 "**更多选项**"，然后选择 "**显示标尺**" 以查看视区左侧和左侧的标尺。</span><span class="sxs-lookup"><span data-stu-id="2e014-209">Click **More options** and then select **Show rulers** to see rulers above and to the left of your viewport.</span></span>  <span data-ttu-id="2e014-210">标尺的调整单位为像素。</span><span class="sxs-lookup"><span data-stu-id="2e014-210">The sizing unit of the rulers is pixels.</span></span>  

> ##### <span data-ttu-id="2e014-211">图 13</span><span class="sxs-lookup"><span data-stu-id="2e014-211">Figure 13</span></span>  
> <span data-ttu-id="2e014-212">显示标尺</span><span class="sxs-lookup"><span data-stu-id="2e014-212">Show rulers</span></span>  
> ![显示标尺][ImageShowRulers]  

> ##### <span data-ttu-id="2e014-214">图 14</span><span class="sxs-lookup"><span data-stu-id="2e014-214">Figure 14</span></span>  
> <span data-ttu-id="2e014-215">视区左侧和左侧的标尺</span><span class="sxs-lookup"><span data-stu-id="2e014-215">Rulers above and to the left of the viewport</span></span>  
> ![视区左侧和左侧的标尺][ImageRulers]  

### <span data-ttu-id="2e014-217">缩放视区</span><span class="sxs-lookup"><span data-stu-id="2e014-217">Zoom the viewport</span></span>   

<span data-ttu-id="2e014-218">使用 "**缩放**" 列表放大或缩小。</span><span class="sxs-lookup"><span data-stu-id="2e014-218">Use the **Zoom** list to zoom in or out.</span></span>  

> ##### <span data-ttu-id="2e014-219">图 15</span><span class="sxs-lookup"><span data-stu-id="2e014-219">Figure 15</span></span>  
> <span data-ttu-id="2e014-220">缩放</span><span class="sxs-lookup"><span data-stu-id="2e014-220">Zoom</span></span>  
> ![缩放][ImageZoomViewport]  

## <span data-ttu-id="2e014-222">限制网络和 CPU</span><span class="sxs-lookup"><span data-stu-id="2e014-222">Throttle the network and CPU</span></span>   

<span data-ttu-id="2e014-223">要限制网络和 CPU，请从 "**限制**" 列表中选择 "**中层移动**" 或 "**低端移动**"。</span><span class="sxs-lookup"><span data-stu-id="2e014-223">To throttle the network and CPU, select **Mid-tier mobile** or **Low-end mobile** from the **Throttle** list.</span></span>  

> ##### <span data-ttu-id="2e014-224">图 16</span><span class="sxs-lookup"><span data-stu-id="2e014-224">Figure 16</span></span>  
> <span data-ttu-id="2e014-225">限制列表</span><span class="sxs-lookup"><span data-stu-id="2e014-225">The Throttle list</span></span>  
> ![限制列表][ImageThrottling]  

<span data-ttu-id="2e014-227">中层**移动**模拟快速3g 并限制 CPU，使其比平时慢4倍。</span><span class="sxs-lookup"><span data-stu-id="2e014-227">**Mid-tier mobile** simulates fast 3G and throttles your CPU so that it is 4 times slower than normal.</span></span>  <span data-ttu-id="2e014-228">**低端移动**模拟低速3g，使 CPU 比平时慢6倍。</span><span class="sxs-lookup"><span data-stu-id="2e014-228">**Low-end mobile** simulates slow 3G and throttles your CPU 6 times slower than normal.</span></span>  <span data-ttu-id="2e014-229">请记住，带宽限制相对于便携式计算机或桌面机的正常功能。</span><span class="sxs-lookup"><span data-stu-id="2e014-229">Keep in mind that the throttling is relative to the normal capability of your laptop or desktop.</span></span>  

> [!NOTE]
> <span data-ttu-id="2e014-230">如果**设备工具栏**较窄，将隐藏 "**限制**" 列表。</span><span class="sxs-lookup"><span data-stu-id="2e014-230">The **Throttle** list will be hidden if your **Device Toolbar** is narrow.</span></span>  

> ##### <span data-ttu-id="2e014-231">图 17</span><span class="sxs-lookup"><span data-stu-id="2e014-231">Figure 17</span></span>  
> <span data-ttu-id="2e014-232">"设备" 工具栏</span><span class="sxs-lookup"><span data-stu-id="2e014-232">The Device Toolbar</span></span>  
> !["设备" 工具栏][ImageDeviceToolbar3]  

### <span data-ttu-id="2e014-234">仅调节 CPU</span><span class="sxs-lookup"><span data-stu-id="2e014-234">Throttle the CPU only</span></span>   

<span data-ttu-id="2e014-235">若要仅限制 CPU，而不限制网络，请转到 "**性能**" 面板，单击 "**捕获设置** ![ 捕获设置 ][ImageCaptureIcon] "，然后从**CPU**列表中选择**4x 减速**或**6x 减速**。</span><span class="sxs-lookup"><span data-stu-id="2e014-235">To throttle the CPU only and not the network, go to the **Performance** panel, click **Capture Settings** ![Capture Settings][ImageCaptureIcon], and then select **4x slowdown** or **6x slowdown** from the **CPU** list.</span></span>  

> ##### <span data-ttu-id="2e014-236">图18</span><span class="sxs-lookup"><span data-stu-id="2e014-236">Figure 18</span></span>  
> <span data-ttu-id="2e014-237">CPU 列表</span><span class="sxs-lookup"><span data-stu-id="2e014-237">The CPU list</span></span>  
> ![CPU 列表][ImageCPU]  

### <span data-ttu-id="2e014-239">仅限制网络</span><span class="sxs-lookup"><span data-stu-id="2e014-239">Throttle the network only</span></span>   

<span data-ttu-id="2e014-240">若要仅限制网络而不是 CPU，请转到 "**网络**" 面板，然后从 "**限制**" 列表中选择 "**快速 3G** " 或 "**慢速 3g** "。</span><span class="sxs-lookup"><span data-stu-id="2e014-240">To throttle the network only and not the CPU, go the **Network** panel and select **Fast 3G** or **Slow 3G** from the **Throttle** list.</span></span>  

> ##### <span data-ttu-id="2e014-241">图19</span><span class="sxs-lookup"><span data-stu-id="2e014-241">Figure 19</span></span>  
> <span data-ttu-id="2e014-242">限制列表</span><span class="sxs-lookup"><span data-stu-id="2e014-242">The Throttle list</span></span>  
> ![限制列表][ImageNetwork]  

<span data-ttu-id="2e014-244">或者按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "命令" 菜单，键入 `3G` ，然后选择 "**启用快速3g 限制**" 或 "**启用慢速3g 限制**"。</span><span class="sxs-lookup"><span data-stu-id="2e014-244">Or press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, type `3G`, and select **Enable fast 3G throttling** or **Enable slow 3G throttling**.</span></span>  

> ##### <span data-ttu-id="2e014-245">图20</span><span class="sxs-lookup"><span data-stu-id="2e014-245">Figure 20</span></span>  
> <span data-ttu-id="2e014-246">命令菜单</span><span class="sxs-lookup"><span data-stu-id="2e014-246">The Command Menu</span></span>  
> ![命令菜单][ImageCommandMenu]  

<span data-ttu-id="2e014-248">您也可以从 "**性能**" 面板中设置网络限制。</span><span class="sxs-lookup"><span data-stu-id="2e014-248">You can also set network throttling from the **Performance** panel.</span></span>  <span data-ttu-id="2e014-249">单击 "**捕获设置** ![ 捕获 ][ImageCaptureIcon] 设置"，然后从 "**网络**" 列表中选择 "**快速 3g** " 或 "**慢速 3g** "。</span><span class="sxs-lookup"><span data-stu-id="2e014-249">Click **Capture Settings** ![Capture Settings][ImageCaptureIcon] and then select **Fast 3G** or **Slow 3G** from the **Network** list.</span></span>  

> ##### <span data-ttu-id="2e014-250">图21</span><span class="sxs-lookup"><span data-stu-id="2e014-250">Figure 21</span></span>  
> <span data-ttu-id="2e014-251">从性能面板设置网络限制</span><span class="sxs-lookup"><span data-stu-id="2e014-251">Setting network throttling from the Performance panel</span></span>  
> ![从性能面板设置网络限制][ImageNetwork2]  

## <span data-ttu-id="2e014-253">替代地理位置</span><span class="sxs-lookup"><span data-stu-id="2e014-253">Override geolocation</span></span>   

<span data-ttu-id="2e014-254">若要打开地理位置替代的 UI，请单击 "**自定义和控制 DevTools** " `...` ，然后选择 "**更多工具**  >  **传感器**"</span><span class="sxs-lookup"><span data-stu-id="2e014-254">To open the geolocation overriding UI click **Customize and control DevTools** `...` and then select **More tools** > **Sensors**.</span></span>  

> ##### <span data-ttu-id="2e014-255">图22</span><span class="sxs-lookup"><span data-stu-id="2e014-255">Figure 22</span></span>  
> <span data-ttu-id="2e014-256">传感器</span><span class="sxs-lookup"><span data-stu-id="2e014-256">Sensors</span></span>  
> ![传感器][ImageSensors]  

<span data-ttu-id="2e014-258">或按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "命令" 菜单，键入 `Sensors` ，然后选择 "**显示传感器**"。</span><span class="sxs-lookup"><span data-stu-id="2e014-258">Or press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, type `Sensors`, and then select **Show Sensors**.</span></span>  

> ##### <span data-ttu-id="2e014-259">图23</span><span class="sxs-lookup"><span data-stu-id="2e014-259">Figure 23</span></span>  
> <span data-ttu-id="2e014-260">显示传感器</span><span class="sxs-lookup"><span data-stu-id="2e014-260">Show Sensors</span></span>  
> ![显示传感器][ImageShowSensors]  

<span data-ttu-id="2e014-262">从 "**地理**位置" 列表中选择其中一个预设，或选择 "**自定义位置**" 以输入您自己的坐标，或选择 "**位置不可用**" 以测试当地理位置处于错误状态时页面的行为。</span><span class="sxs-lookup"><span data-stu-id="2e014-262">Select one of the presets from the **Geolocation** list, or select **Custom location** to enter your own coordinates, or select **Location unavailable** to test out how your page behaves when geolocation is in an error state.</span></span>  

> ##### <span data-ttu-id="2e014-263">图24</span><span class="sxs-lookup"><span data-stu-id="2e014-263">Figure 24</span></span>  
> <span data-ttu-id="2e014-264">地理位置</span><span class="sxs-lookup"><span data-stu-id="2e014-264">Geolocation</span></span>  
> ![地理位置][ImageGeolocation]  

## <span data-ttu-id="2e014-266">设置方向</span><span class="sxs-lookup"><span data-stu-id="2e014-266">Set orientation</span></span>   

<span data-ttu-id="2e014-267">若要打开方向用户界面，请单击 "**自定义和控制 DevTools** " `...` ，然后选择 "**更多工具**  >  **传感器**"。</span><span class="sxs-lookup"><span data-stu-id="2e014-267">To open the orientation UI click **Customize and control DevTools** `...` and then select **More tools** > **Sensors**.</span></span>  

> ##### <span data-ttu-id="2e014-268">图25</span><span class="sxs-lookup"><span data-stu-id="2e014-268">Figure 25</span></span>  
> <span data-ttu-id="2e014-269">传感器</span><span class="sxs-lookup"><span data-stu-id="2e014-269">Sensors</span></span>  
> ![传感器][ImageSensors2]  

<span data-ttu-id="2e014-271">或按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "命令" 菜单，键入 `Sensors` ，然后选择 "**显示传感器**"。</span><span class="sxs-lookup"><span data-stu-id="2e014-271">Or press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, type `Sensors`, and then select **Show Sensors**.</span></span>  

> ##### <span data-ttu-id="2e014-272">图26</span><span class="sxs-lookup"><span data-stu-id="2e014-272">Figure 26</span></span>  
> <span data-ttu-id="2e014-273">显示传感器</span><span class="sxs-lookup"><span data-stu-id="2e014-273">Show Sensors</span></span>  
> ![显示传感器][ImageShowSensors2]  

<span data-ttu-id="2e014-275">从 "**方向**" 列表中选择其中一个预设，或选择 "**自定义方向**" 以设置您自己的 alpha、beta 和伽玛值。</span><span class="sxs-lookup"><span data-stu-id="2e014-275">Select one of the presets from the **Orientation** list or select **Custom orientation** to set your own alpha, beta, and gamma values.</span></span>  

> ##### <span data-ttu-id="2e014-276">图27</span><span class="sxs-lookup"><span data-stu-id="2e014-276">Figure 27</span></span>  
> <span data-ttu-id="2e014-277">Orientation</span><span class="sxs-lookup"><span data-stu-id="2e014-277">Orientation</span></span>  
> ![Orientation][ImageOrientation]  

 



<!--See [Join the DevTools community][DevToolsCommunity] for other ways to leave feedback.  -->  

<!-- image links -->  

[ImageCaptureIcon]: /microsoft-edge/devtools-guide-chromium/media/capture-settings-icon.msft.png  
[ImageCustomizeIcon]: /microsoft-edge/devtools-guide-chromium/media/customize-and-control-devtools-icon.msft.png  
[ImageDeviceToolbarIcon]: /microsoft-edge/devtools-guide-chromium/media/toggle-device-toolbar-dark-icon.msft.png  
[ImageRotateIcon]: /microsoft-edge/devtools-guide-chromium/media/rotate-dark-icon.msft.png  

[ImageDeviceToolbar]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-highlighted.msft.png "图1：设备工具栏"  
[ImageResponsiveHandles]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png "图2：在 "响应" 视口模式下更改视区尺寸的控制滑块"  
[ImageShowMediaQueries]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png "图3：显示媒体查询"  
[ImageBreakpoint]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png "图4：单击断点更改视区的宽度"  
[ImageDeviceType]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-device-type-list.msft.png "图5：设备类型列表"  
[ImageDeviceList]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-device-list.msft.png "图6：设备列表"  
[ImageLandscape]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-landscape.msft.png "图7：横向方向"  
[ImageDeviceToolbar2]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-highlighted.msft.png "图8：设备工具栏"  
[ImageShowDeviceFrame]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png "图9：显示设备帧"  
[ImageIphoneFrame]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png "图10： iPhone 6 的设备帧"  
[ImageEdit]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-device-list-edit.msft.png "图11：选择 "编辑""  
[ImageAddCustomDevice]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png "图12：创建自定义设备"  
[ImageShowRulers]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png "图13：显示标尺"  
[ImageRulers]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-rulers.msft.png "图14：位于视区左侧和左侧的标尺"  
[ImageZoomViewport]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-zoom.msft.png "图15：缩放"  
[ImageThrottling]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-throttle.msft.png "图16：限制列表"  
[ImageDeviceToolbar3]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-highlighted.msft.png "图17：设备工具栏"  
[ImageCPU]: /microsoft-edge/devtools-guide-chromium/media/device-mode-performance-cpu-throttle.msft.png "图18： CPU 列表"  
[ImageNetwork]: /microsoft-edge/devtools-guide-chromium/media/device-mode-network-throttle.msft.png "图19：限制列表"  
[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/device-mode-command-menu-throttle.msft.png "图20：命令菜单"  
[ImageNetwork2]: /microsoft-edge/devtools-guide-chromium/media/device-mode-performance-network-throttle.msft.png "图21：从性能面板设置网络限制"  
[ImageSensors]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png "图22：传感器"  
[ImageShowSensors]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png "图23：显示传感器"  
[ImageGeolocation]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png "图24：地理位置"  
[ImageSensors2]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png "图25：传感器"  
[ImageShowSensors2]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png "图26：显示传感器"  
[ImageOrientation]: /microsoft-edge/devtools-guide-chromium/media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png "图27：方向"  

<!-- links -->  

<!--[DevToolsCommunity]: ../index.md#community "Join the DevTools community"  -->
<span data-ttu-id="2e014-306">[DevToolsRemoteDebugging]：/microsoft-edge/devtools-guide-chromium/remote-debugging/index "开始使用远程调试 Android 设备"</span><span class="sxs-lookup"><span data-stu-id="2e014-306">[DevToolsRemoteDebugging]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "Get Started with Remote Debugging Android Devices"</span></span>  

[MDNWindowDevicePixelRatio]: https://developer.mozilla.org/docs/Web/API/Window/devicePixelRatio "DevicePixelRatio |MDN"  
[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "用户代理 |MDN"  

[WikiApproximation]: https://en.wikipedia.org/wiki/Order_of_approximation#First-order "近似值-第一顺序-维基百科的顺序"  

> [!NOTE]
> <span data-ttu-id="2e014-310">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="2e014-310">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="2e014-311">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="2e014-311">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="2e014-313">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="2e014-313">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
