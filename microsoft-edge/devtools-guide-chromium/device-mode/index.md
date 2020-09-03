---
description: 在设备模式下为 Microsoft Edge 使用虚拟设备，构建移动版的第一网站。
title: 在 Microsoft Edge DevTools 中通过设备模式模拟移动设备
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: eababe8112b5d888671a8955e16f0fe1c89564fb
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993014"
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





# <span data-ttu-id="b7810-104">在 Microsoft Edge DevTools 中通过设备模式模拟移动设备</span><span class="sxs-lookup"><span data-stu-id="b7810-104">Simulate mobile devices with Device Mode in Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="b7810-105">使用 "设备" 模式来大致了解页面在移动设备上的外观和执行方式。</span><span class="sxs-lookup"><span data-stu-id="b7810-105">Use Device Mode to approximate how your page looks and performs on a mobile device.</span></span>  

<span data-ttu-id="b7810-106">设备模式是 Microsoft Edge DevTools 中的松散功能集的名称，可帮助你模拟移动设备。</span><span class="sxs-lookup"><span data-stu-id="b7810-106">Device Mode is the name for the loose collection of features in Microsoft Edge DevTools that help you simulate mobile devices.</span></span>  <span data-ttu-id="b7810-107">这些功能包括：</span><span class="sxs-lookup"><span data-stu-id="b7810-107">These features include:</span></span>  

*   [<span data-ttu-id="b7810-108">模拟移动视区</span><span class="sxs-lookup"><span data-stu-id="b7810-108">Simulating a mobile viewport</span></span>](#simulate-a-mobile-viewport)  
*   [<span data-ttu-id="b7810-109">限制网络</span><span class="sxs-lookup"><span data-stu-id="b7810-109">Throttling the network</span></span>](#throttle-the-network-only)  
*   [<span data-ttu-id="b7810-110">调节 CPU</span><span class="sxs-lookup"><span data-stu-id="b7810-110">Throttling the CPU</span></span>](#throttle-the-cpu-only)  
*   [<span data-ttu-id="b7810-111">模拟地理位置</span><span class="sxs-lookup"><span data-stu-id="b7810-111">Simulating geolocation</span></span>](#override-geolocation)  
*   [<span data-ttu-id="b7810-112">设置方向</span><span class="sxs-lookup"><span data-stu-id="b7810-112">Setting orientation</span></span>](#set-orientation)  

## <span data-ttu-id="b7810-113">限制</span><span class="sxs-lookup"><span data-stu-id="b7810-113">Limitations</span></span>   

<span data-ttu-id="b7810-114">将设备模式视为对移动设备上的页面外观和感觉的 [第一顺序近似值][WikiApproximation] 。</span><span class="sxs-lookup"><span data-stu-id="b7810-114">Think of Device Mode as a [first-order approximation][WikiApproximation] of how your page looks and feels on a mobile device.</span></span>  <span data-ttu-id="b7810-115">使用设备模式时，实际上并不是在移动设备上运行代码。</span><span class="sxs-lookup"><span data-stu-id="b7810-115">With Device Mode you do not actually run your code on a mobile device.</span></span>  <span data-ttu-id="b7810-116">您可以从便携式计算机或桌面模拟移动用户体验。</span><span class="sxs-lookup"><span data-stu-id="b7810-116">You simulate the mobile user experience from your laptop or desktop.</span></span>  

<span data-ttu-id="b7810-117">移动设备的某些方面 DevTools 将永远无法模拟。</span><span class="sxs-lookup"><span data-stu-id="b7810-117">There are some aspects of mobile devices that DevTools will never be able to simulate.</span></span>  <span data-ttu-id="b7810-118">例如，移动 Cpu 的体系结构与便携式计算机或桌面 Cpu 的体系结构非常不同。</span><span class="sxs-lookup"><span data-stu-id="b7810-118">For example, the architecture of mobile CPUs is very different than the architecture of laptop or desktop CPUs.</span></span>  <span data-ttu-id="b7810-119">如果有疑问，最佳做法是在移动设备上实际运行您的页面。</span><span class="sxs-lookup"><span data-stu-id="b7810-119">When in doubt, your best bet is to actually run your page on a mobile device.</span></span>  <span data-ttu-id="b7810-120">使用 [远程调试] [DevToolsRemoteDebugging] 查看、更改、调试和分析来自便携式计算机或桌面的页面的代码，同时它实际上在移动设备上运行。</span><span class="sxs-lookup"><span data-stu-id="b7810-120">Use [Remote Debugging][DevToolsRemoteDebugging] to view, change, debug, and profile the code of a page from your laptop or desktop while it actually runs on a mobile device.</span></span>  

## <span data-ttu-id="b7810-121">模拟移动视区</span><span class="sxs-lookup"><span data-stu-id="b7810-121">Simulate a mobile viewport</span></span>   

<span data-ttu-id="b7810-122">单击 " **切换设备工具栏** \ (![ 切换设备工具栏 ][ImageDeviceToolbarIcon] \ ) " 以打开可让你模拟移动视区的 UI。</span><span class="sxs-lookup"><span data-stu-id="b7810-122">Click **Toggle Device Toolbar** \(![Toggle Device Toolbar][ImageDeviceToolbarIcon]\) to open the UI that enables you to simulate a mobile viewport.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text=""设备" 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   <span data-ttu-id="b7810-124">"设备" 工具栏</span><span class="sxs-lookup"><span data-stu-id="b7810-124">The Device Toolbar</span></span>  
:::image-end:::  

<span data-ttu-id="b7810-125">默认情况下，设备工具栏将在 "响应式" 视区模式下打开。</span><span class="sxs-lookup"><span data-stu-id="b7810-125">By default the Device Toolbar opens in Responsive Viewport Mode.</span></span>  

### <span data-ttu-id="b7810-126">响应式视区模式</span><span class="sxs-lookup"><span data-stu-id="b7810-126">Responsive Viewport Mode</span></span>   

<span data-ttu-id="b7810-127">拖动图柄以将视区大小调整为所需的任何尺寸。</span><span class="sxs-lookup"><span data-stu-id="b7810-127">Drag the handles to resize the viewport to whatever dimensions you need.</span></span>  <span data-ttu-id="b7810-128">或者，在 "宽度" 和 "高度" 框中输入特定值。</span><span class="sxs-lookup"><span data-stu-id="b7810-128">Or, enter specific values in the width and height boxes.</span></span>  <span data-ttu-id="b7810-129">在下图中，宽度设置为 `626` ，高度设置为 `516` 。</span><span class="sxs-lookup"><span data-stu-id="b7810-129">In the following figure, the width is set to `626` and the height is set to `516`.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png" alt-text="在 "响应" 视口模式下更改视区尺寸的控制滑块" lightbox="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png":::
   <span data-ttu-id="b7810-131">在 "响应" 视口模式下更改视区尺寸的控制滑块</span><span class="sxs-lookup"><span data-stu-id="b7810-131">The handles for changing the dimensions of the viewport when in Responsive Viewport Mode</span></span>  
:::image-end:::  

#### <span data-ttu-id="b7810-132">显示媒体查询</span><span class="sxs-lookup"><span data-stu-id="b7810-132">Show media queries</span></span>   

<span data-ttu-id="b7810-133">若要在视区上方显示媒体查询断点，请单击 " **更多选项** "，然后选择 " **显示媒体查询**"。</span><span class="sxs-lookup"><span data-stu-id="b7810-133">To show media query breakpoints above your viewport, click **More options** and then select **Show media queries**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png" alt-text="显示媒体查询" lightbox="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png":::
   **<span data-ttu-id="b7810-135">显示媒体查询</span><span class="sxs-lookup"><span data-stu-id="b7810-135">Show media queries</span></span>**  
:::image-end:::  

<span data-ttu-id="b7810-136">单击断点以更改视区的宽度，以便触发断点。</span><span class="sxs-lookup"><span data-stu-id="b7810-136">Click a breakpoint to change the width of the viewport so that the breakpoint gets triggered.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png" alt-text="单击断点以更改视区的宽度" lightbox="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png":::
   <span data-ttu-id="b7810-138">单击断点以更改视区的宽度</span><span class="sxs-lookup"><span data-stu-id="b7810-138">Click a breakpoint to change the width of the viewport</span></span>  
:::image-end:::  

#### <span data-ttu-id="b7810-139">设置设备类型</span><span class="sxs-lookup"><span data-stu-id="b7810-139">Set the device type</span></span>   

<span data-ttu-id="b7810-140">使用 **设备类型** 列表来模拟移动设备或桌面设备。</span><span class="sxs-lookup"><span data-stu-id="b7810-140">Use the **Device Type** list to simulate a mobile device or desktop device.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png" alt-text="设备类型列表" lightbox="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png":::
   <span data-ttu-id="b7810-142">**设备类型**列表</span><span class="sxs-lookup"><span data-stu-id="b7810-142">The **Device Type** list</span></span>  
:::image-end:::  

<span data-ttu-id="b7810-143">下表描述了选项之间的差异。</span><span class="sxs-lookup"><span data-stu-id="b7810-143">The table below describes the differences between the options.</span></span>  <span data-ttu-id="b7810-144">**呈现方法** 是指 Microsoft Edge 是否将页面呈现为移动设备或桌面视区。</span><span class="sxs-lookup"><span data-stu-id="b7810-144">**Rendering method** refers to whether Microsoft Edge renders the page as a mobile or desktop viewport.</span></span>  <span data-ttu-id="b7810-145">**光标图标** 指将鼠标悬停在页面上时看到的光标类型。</span><span class="sxs-lookup"><span data-stu-id="b7810-145">**Cursor icon** refers to what type of cursor you see when you hover over the page.</span></span>  <span data-ttu-id="b7810-146">**激发的事件** 是指 `touch` `click` 当您与页面交互时页面是引发还是事件。</span><span class="sxs-lookup"><span data-stu-id="b7810-146">**Events fired** refers to whether the page fires `touch` or `click` events when you interact with the page.</span></span>  

| <span data-ttu-id="b7810-147">选项</span><span class="sxs-lookup"><span data-stu-id="b7810-147">Option</span></span> | <span data-ttu-id="b7810-148">呈现方法</span><span class="sxs-lookup"><span data-stu-id="b7810-148">Rendering method</span></span> | <span data-ttu-id="b7810-149">光标图标</span><span class="sxs-lookup"><span data-stu-id="b7810-149">Cursor icon</span></span> | <span data-ttu-id="b7810-150">激发的事件</span><span class="sxs-lookup"><span data-stu-id="b7810-150">Events fired</span></span> |  
|:--- |:--- |:--- |:--- |  
| <span data-ttu-id="b7810-151">移动版</span><span class="sxs-lookup"><span data-stu-id="b7810-151">Mobile</span></span> | <span data-ttu-id="b7810-152">移动版</span><span class="sxs-lookup"><span data-stu-id="b7810-152">Mobile</span></span> | <span data-ttu-id="b7810-153">圆形</span><span class="sxs-lookup"><span data-stu-id="b7810-153">Circle</span></span> | <span data-ttu-id="b7810-154">触摸</span><span class="sxs-lookup"><span data-stu-id="b7810-154">touch</span></span> |  
| <span data-ttu-id="b7810-155">移动 \ (无接触 \ ) </span><span class="sxs-lookup"><span data-stu-id="b7810-155">Mobile \(no touch\)</span></span> | <span data-ttu-id="b7810-156">移动版</span><span class="sxs-lookup"><span data-stu-id="b7810-156">Mobile</span></span> | <span data-ttu-id="b7810-157">正常</span><span class="sxs-lookup"><span data-stu-id="b7810-157">Normal</span></span> | <span data-ttu-id="b7810-158">单击</span><span class="sxs-lookup"><span data-stu-id="b7810-158">click</span></span> |  
| <span data-ttu-id="b7810-159">桌面</span><span class="sxs-lookup"><span data-stu-id="b7810-159">Desktop</span></span> | <span data-ttu-id="b7810-160">桌面</span><span class="sxs-lookup"><span data-stu-id="b7810-160">Desktop</span></span> | <span data-ttu-id="b7810-161">正常</span><span class="sxs-lookup"><span data-stu-id="b7810-161">Normal</span></span> | <span data-ttu-id="b7810-162">单击</span><span class="sxs-lookup"><span data-stu-id="b7810-162">click</span></span> |  
| <span data-ttu-id="b7810-163">桌面 (触控 \ ) </span><span class="sxs-lookup"><span data-stu-id="b7810-163">Desktop \(touch\)</span></span> | <span data-ttu-id="b7810-164">桌面</span><span class="sxs-lookup"><span data-stu-id="b7810-164">Desktop</span></span> | <span data-ttu-id="b7810-165">圆形</span><span class="sxs-lookup"><span data-stu-id="b7810-165">Circle</span></span> | <span data-ttu-id="b7810-166">触摸</span><span class="sxs-lookup"><span data-stu-id="b7810-166">touch</span></span> |  

> [!NOTE]
> <span data-ttu-id="b7810-167">如果看不到 " **设备类型** " 列表，请单击 " **更多选项** "，然后选择 " **添加设备类型**"。</span><span class="sxs-lookup"><span data-stu-id="b7810-167">If you do not see the **Device Type** list, click **More options** and select **Add device type**.</span></span>  

### <span data-ttu-id="b7810-168">移动设备视区模式</span><span class="sxs-lookup"><span data-stu-id="b7810-168">Mobile Device Viewport Mode</span></span>   

<span data-ttu-id="b7810-169">若要模拟特定移动设备的尺寸，请从 **设备** 列表中选择该设备。</span><span class="sxs-lookup"><span data-stu-id="b7810-169">To simulate the dimensions of a specific mobile device, select the device from the **Device** list.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list.msft.png" alt-text="设备列表" lightbox="../media/device-mode-toggle-device-toolbar-device-list.msft.png":::
   <span data-ttu-id="b7810-171">**设备**列表</span><span class="sxs-lookup"><span data-stu-id="b7810-171">The **Device** list</span></span>  
:::image-end:::  

#### <span data-ttu-id="b7810-172">将视区旋转到横向方向</span><span class="sxs-lookup"><span data-stu-id="b7810-172">Rotate the viewport to landscape orientation</span></span>   

<span data-ttu-id="b7810-173">单击 " **旋转** \ (![ 旋转 ][ImageRotateIcon] \ ) "，将视区旋转到横向方向。</span><span class="sxs-lookup"><span data-stu-id="b7810-173">Click **Rotate** \(![Rotate][ImageRotateIcon]\) to rotate the viewport to landscape orientation.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-landscape.msft.png" alt-text="横向方向" lightbox="../media/device-mode-toggle-device-toolbar-landscape.msft.png":::
   <span data-ttu-id="b7810-175">横向方向</span><span class="sxs-lookup"><span data-stu-id="b7810-175">Landscape orientation</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="b7810-176">如果**设备工具栏**较窄，"**旋转**" 按钮将消失。</span><span class="sxs-lookup"><span data-stu-id="b7810-176">The **Rotate** button disappears if your **Device Toolbar** is narrow.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text=""设备" 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   <span data-ttu-id="b7810-178">" **设备" 工具栏**</span><span class="sxs-lookup"><span data-stu-id="b7810-178">The **Device Toolbar**</span></span>  
:::image-end:::  

<span data-ttu-id="b7810-179">另请参阅 [设置方向](#set-orientation)。</span><span class="sxs-lookup"><span data-stu-id="b7810-179">See also [Set orientation](#set-orientation).</span></span>  

#### <span data-ttu-id="b7810-180">显示设备帧</span><span class="sxs-lookup"><span data-stu-id="b7810-180">Show device frame</span></span>   

<span data-ttu-id="b7810-181">模拟一个特定移动设备（如 iPhone 6）的尺寸时，打开 " **更多选项** "，然后选择 " **显示设备帧** " 以显示视区周围的物理设备帧。</span><span class="sxs-lookup"><span data-stu-id="b7810-181">When simulating the dimensions of a specific mobile device like an iPhone 6, open **More options** and then select **Show device frame** to show the physical device frame around the viewport.</span></span>  

> [!NOTE]
> <span data-ttu-id="b7810-182">如果您没有看到特定设备的设备框架，则可能意味着 DevTools 只对该特定选项没有艺术。</span><span class="sxs-lookup"><span data-stu-id="b7810-182">If you do not see a device frame for a particular device, it probably means that DevTools just does not have art for that specific option.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png" alt-text="显示设备帧" lightbox="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png":::
         <span data-ttu-id="b7810-184">显示设备帧</span><span class="sxs-lookup"><span data-stu-id="b7810-184">Show device frame</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png" alt-text="IPhone 6 的设备帧" lightbox="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png":::
         <span data-ttu-id="b7810-186">IPhone 6 的设备帧</span><span class="sxs-lookup"><span data-stu-id="b7810-186">The device frame for the iPhone 6</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

#### <span data-ttu-id="b7810-187">添加自定义移动设备</span><span class="sxs-lookup"><span data-stu-id="b7810-187">Add a custom mobile device</span></span>   

<span data-ttu-id="b7810-188">要添加自定义设备，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b7810-188">To add a custom device:</span></span>  

1.  <span data-ttu-id="b7810-189">单击 " **设备** " 列表，然后选择 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="b7810-189">Click the **Device** list and then select **Edit**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png" alt-text="选择 "编辑"" lightbox="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png":::
       <span data-ttu-id="b7810-191">选择 "**编辑**"</span><span class="sxs-lookup"><span data-stu-id="b7810-191">Select **Edit**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b7810-192">单击 " **添加自定义设备**"。</span><span class="sxs-lookup"><span data-stu-id="b7810-192">Click **Add custom device**.</span></span>  
1.  <span data-ttu-id="b7810-193">输入设备的名称、宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="b7810-193">Enter a name, width, and height for the device.</span></span>  <span data-ttu-id="b7810-194">[设备像素比率][MDNWindowDevicePixelRatio]、[用户代理字符串][MDNUserAgent]和[设备类型](#set-the-device-type)字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="b7810-194">The [device pixel ratio][MDNWindowDevicePixelRatio], [user agent string][MDNUserAgent], and [device type](#set-the-device-type) fields are optional.</span></span>  <span data-ttu-id="b7810-195">"设备类型" 字段是默认情况下设置为 " **移动电话** " 的列表。</span><span class="sxs-lookup"><span data-stu-id="b7810-195">The device type field is the list that is set to **Mobile** by default.</span></span>  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png" alt-text="创建自定义设备" lightbox="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png":::
       <span data-ttu-id="b7810-197">Createa 自定义设备</span><span class="sxs-lookup"><span data-stu-id="b7810-197">Createa custom device</span></span>  
    :::image-end:::  

### <span data-ttu-id="b7810-198">显示标尺</span><span class="sxs-lookup"><span data-stu-id="b7810-198">Show rulers</span></span>   

<span data-ttu-id="b7810-199">单击 " **更多选项** "，然后选择 " **显示标尺** " 以查看视区左侧和左侧的标尺。</span><span class="sxs-lookup"><span data-stu-id="b7810-199">Click **More options** and then select **Show rulers** to see rulers above and to the left of your viewport.</span></span>  <span data-ttu-id="b7810-200">标尺的调整单位为像素。</span><span class="sxs-lookup"><span data-stu-id="b7810-200">The sizing unit of the rulers is pixels.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png" alt-text="显示标尺" lightbox="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png":::
         **<span data-ttu-id="b7810-202">显示标尺</span><span class="sxs-lookup"><span data-stu-id="b7810-202">Show rulers</span></span>**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-rulers.msft.png" alt-text="视区左侧和左侧的标尺" lightbox="../media/device-mode-toggle-device-toolbar-rulers.msft.png":::
         <span data-ttu-id="b7810-204">视区左侧和左侧的标尺</span><span class="sxs-lookup"><span data-stu-id="b7810-204">Rulers above and to the left of the viewport</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### <span data-ttu-id="b7810-205">缩放视区</span><span class="sxs-lookup"><span data-stu-id="b7810-205">Zoom the viewport</span></span>   

<span data-ttu-id="b7810-206">使用 " **缩放** " 列表放大或缩小。</span><span class="sxs-lookup"><span data-stu-id="b7810-206">Use the **Zoom** list to zoom in or out.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-zoom.msft.png" alt-text="缩放" lightbox="../media/device-mode-toggle-device-toolbar-zoom.msft.png":::
   **<span data-ttu-id="b7810-208">缩放</span><span class="sxs-lookup"><span data-stu-id="b7810-208">Zoom</span></span>**  
:::image-end:::  

## <span data-ttu-id="b7810-209">限制网络和 CPU</span><span class="sxs-lookup"><span data-stu-id="b7810-209">Throttle the network and CPU</span></span>   

<span data-ttu-id="b7810-210">要限制网络和 CPU，请从 "**限制**" 列表中选择 "**中层移动**" 或 "**低端移动**"。</span><span class="sxs-lookup"><span data-stu-id="b7810-210">To throttle the network and CPU, select **Mid-tier mobile** or **Low-end mobile** from the **Throttle** list.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-throttle.msft.png" alt-text="限制列表" lightbox="../media/device-mode-toggle-device-toolbar-throttle.msft.png":::
   <span data-ttu-id="b7810-212">**限制**列表</span><span class="sxs-lookup"><span data-stu-id="b7810-212">The **Throttle** list</span></span>  
:::image-end:::  

<span data-ttu-id="b7810-213">中层**移动**模拟快速3g 并限制 CPU，使其比平时慢4倍。</span><span class="sxs-lookup"><span data-stu-id="b7810-213">**Mid-tier mobile** simulates fast 3G and throttles your CPU so that it is 4 times slower than normal.</span></span>  <span data-ttu-id="b7810-214">**低端移动** 模拟低速3g，使 CPU 比平时慢6倍。</span><span class="sxs-lookup"><span data-stu-id="b7810-214">**Low-end mobile** simulates slow 3G and throttles your CPU 6 times slower than normal.</span></span>  <span data-ttu-id="b7810-215">请记住，带宽限制相对于便携式计算机或桌面机的正常功能。</span><span class="sxs-lookup"><span data-stu-id="b7810-215">Keep in mind that the throttling is relative to the normal capability of your laptop or desktop.</span></span>  

> [!NOTE]
> <span data-ttu-id="b7810-216">如果您的**设备工具栏**很窄，"**限制**" 列表将被隐藏。</span><span class="sxs-lookup"><span data-stu-id="b7810-216">The **Throttle** list is hidden if your **Device Toolbar** is narrow.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text=""设备" 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   <span data-ttu-id="b7810-218">" **设备" 工具栏**</span><span class="sxs-lookup"><span data-stu-id="b7810-218">The **Device Toolbar**</span></span>  
:::image-end:::  

### <span data-ttu-id="b7810-219">仅调节 CPU</span><span class="sxs-lookup"><span data-stu-id="b7810-219">Throttle the CPU only</span></span>   

<span data-ttu-id="b7810-220">若要仅限制 CPU 而不是网络，请转到 "**性能**" 面板，单击 "**捕获设置**\ (![ 捕获设置 ][ImageCaptureIcon] \ ) "，然后从**CPU**列表中选择**4x 减速**或**6x 减速**。</span><span class="sxs-lookup"><span data-stu-id="b7810-220">To throttle the CPU only and not the network, go to the **Performance** panel, click **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\), and then select **4x slowdown** or **6x slowdown** from the **CPU** list.</span></span>  

:::image type="complex" source="../media/device-mode-performance-cpu-throttle.msft.png" alt-text="CPU 列表" lightbox="../media/device-mode-performance-cpu-throttle.msft.png":::
   <span data-ttu-id="b7810-222">**CPU**列表</span><span class="sxs-lookup"><span data-stu-id="b7810-222">The **CPU** list</span></span>  
:::image-end:::  

### <span data-ttu-id="b7810-223">仅限制网络</span><span class="sxs-lookup"><span data-stu-id="b7810-223">Throttle the network only</span></span>   

<span data-ttu-id="b7810-224">若要仅限制网络而不是 CPU，请转到 "**网络**" 面板，然后从 "**限制**" 列表中选择 "**快速 3G** " 或 "**慢速 3g** "。</span><span class="sxs-lookup"><span data-stu-id="b7810-224">To throttle the network only and not the CPU, go the **Network** panel and select **Fast 3G** or **Slow 3G** from the **Throttle** list.</span></span>  

:::image type="complex" source="../media/device-mode-network-throttle.msft.png" alt-text="限制列表" lightbox="../media/device-mode-network-throttle.msft.png":::
   <span data-ttu-id="b7810-226">**限制**列表</span><span class="sxs-lookup"><span data-stu-id="b7810-226">The **Throttle** list</span></span>  
:::image-end:::  

<span data-ttu-id="b7810-227">或者按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "**命令" 菜单**，键入 `3G` ，然后选择 "**启用快速3g 限制**" 或 "**启用慢速3g 限制**"。</span><span class="sxs-lookup"><span data-stu-id="b7810-227">Or press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**, type `3G`, and select **Enable fast 3G throttling** or **Enable slow 3G throttling**.</span></span>  

:::image type="complex" source="../media/device-mode-command-menu-throttle.msft.png" alt-text="命令菜单" lightbox="../media/device-mode-command-menu-throttle.msft.png":::
   <span data-ttu-id="b7810-229">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="b7810-229">The **Command Menu**</span></span>  
:::image-end:::  

<span data-ttu-id="b7810-230">您也可以从 " **性能** " 面板中设置网络限制。</span><span class="sxs-lookup"><span data-stu-id="b7810-230">You can also set network throttling from the **Performance** panel.</span></span>  <span data-ttu-id="b7810-231">单击 "**捕获设置**\ ![ (捕获设置 ][ImageCaptureIcon] \ ) 然后从"**网络**"列表中选择"**快速 3g** "或"**慢速 3g** "。</span><span class="sxs-lookup"><span data-stu-id="b7810-231">Click **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\) and then select **Fast 3G** or **Slow 3G** from the **Network** list.</span></span>  

:::image type="complex" source="../media/device-mode-performance-network-throttle.msft.png" alt-text="从性能面板设置网络限制" lightbox="../media/device-mode-performance-network-throttle.msft.png":::
   <span data-ttu-id="b7810-233">从 **性能** 面板设置网络限制</span><span class="sxs-lookup"><span data-stu-id="b7810-233">Set network throttling from the **Performance** panel</span></span>  
:::image-end:::  

## <span data-ttu-id="b7810-234">替代地理位置</span><span class="sxs-lookup"><span data-stu-id="b7810-234">Override geolocation</span></span>   

<span data-ttu-id="b7810-235">若要打开地理位置替代的 UI，请单击 "**自定义" 并控制 DevTools** \ (`...` \ ) 然后选择 "**更多工具**  >  **传感器**"。</span><span class="sxs-lookup"><span data-stu-id="b7810-235">To open the geolocation overriding UI click **Customize and control DevTools** \(`...`\) and then select **More tools** > **Sensors**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="传感器" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
   **<span data-ttu-id="b7810-237">传感器</span><span class="sxs-lookup"><span data-stu-id="b7810-237">Sensors</span></span>**  
:::image-end:::  

<span data-ttu-id="b7810-238">或者按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "命令" 菜单，键入 `Sensors` ，然后选择 "**显示传感器**"。</span><span class="sxs-lookup"><span data-stu-id="b7810-238">Or press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, type `Sensors`, and then select **Show Sensors**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="显示传感器" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
   **<span data-ttu-id="b7810-240">显示传感器</span><span class="sxs-lookup"><span data-stu-id="b7810-240">Show Sensors</span></span>**  
:::image-end:::  

<span data-ttu-id="b7810-241">从 " **地理** 位置" 列表中选择其中一个预设，或选择 " **自定义位置** " 以输入您自己的坐标，或选择 " **位置不可用** " 以测试当地理位置处于错误状态时页面的行为。</span><span class="sxs-lookup"><span data-stu-id="b7810-241">Select one of the presets from the **Geolocation** list, or select **Custom location** to enter your own coordinates, or select **Location unavailable** to test out how your page behaves when geolocation is in an error state.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png" alt-text="地理位置" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png":::
   **<span data-ttu-id="b7810-243">地理位置</span><span class="sxs-lookup"><span data-stu-id="b7810-243">Geolocation</span></span>**  
:::image-end:::  

## <span data-ttu-id="b7810-244">设置方向</span><span class="sxs-lookup"><span data-stu-id="b7810-244">Set orientation</span></span>   

:::row:::
   :::column span="":::
      <span data-ttu-id="b7810-245">若要打开方向用户界面，请单击 "**自定义和控制 DevTools** " `...` ，然后选择 "**更多工具**  >  **传感器**"。</span><span class="sxs-lookup"><span data-stu-id="b7810-245">To open the orientation UI click **Customize and control DevTools** `...` and then select **More tools** > **Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="传感器" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         **<span data-ttu-id="b7810-247">传感器</span><span class="sxs-lookup"><span data-stu-id="b7810-247">Sensors</span></span>**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="b7810-248">或者按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "命令" 菜单，键入 `Sensors` ，然后选择 "**显示传感器**"。</span><span class="sxs-lookup"><span data-stu-id="b7810-248">Or press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, type `Sensors`, and then select **Show Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="显示传感器" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         **<span data-ttu-id="b7810-250">显示传感器</span><span class="sxs-lookup"><span data-stu-id="b7810-250">Show Sensors</span></span>**  
      :::image-end:::  
   :::column-end:::
:::row-end:::

<span data-ttu-id="b7810-251">从 " **方向** " 列表中选择其中一个预设，或选择 " **自定义方向** " 以设置您自己的 alpha、beta 和伽玛值。</span><span class="sxs-lookup"><span data-stu-id="b7810-251">Select one of the presets from the **Orientation** list or select **Custom orientation** to set your own alpha, beta, and gamma values.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png" alt-text="Orientation" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png":::
   **<span data-ttu-id="b7810-253">Orientation</span><span class="sxs-lookup"><span data-stu-id="b7810-253">Orientation</span></span>**  
:::image-end:::  

<!--  
 


-->  

<!--See [Join the DevTools community][DevToolsCommunity] for other ways to leave feedback.  -->  

<!-- image links -->  

[ImageCaptureIcon]: ../media/capture-settings-icon.msft.png  
[ImageDeviceToolbarIcon]: ../media/toggle-device-toolbar-dark-icon.msft.png  
[ImageRotateIcon]: ../media/rotate-dark-icon.msft.png  

<!-- links -->  

<!--[DevToolsCommunity]: ../index.md#community "Join the DevTools community | Microsoft Docs"  -->
[DevToolsRemoteDebugging]: ../remote-debugging/index.md "开始使用远程调试 Android 设备" |Microsoft 文档 "  

[MDNWindowDevicePixelRatio]: https://developer.mozilla.org/docs/Web/API/Window/devicePixelRatio "DevicePixelRatio |MDN"  
[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "用户代理 |MDN"  

[WikiApproximation]: https://en.wikipedia.org/wiki/Order_of_approximation#First-order "近似值-第一顺序-维基百科的顺序"  

> [!NOTE]
> <span data-ttu-id="b7810-258">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="b7810-258">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b7810-259">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="b7810-259">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="b7810-261">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="b7810-261">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
