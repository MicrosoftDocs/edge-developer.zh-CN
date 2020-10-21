---
description: 使用 Microsoft Edge 中的虚拟设备构建移动版的第一网站。
title: 在 Microsoft Edge DevTools 中模拟移动设备
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge，web 开发，f12 工具，devtools，仿真，设备，模拟，移动
ms.openlocfilehash: 8b636a20fcb1c55630009031ec8bf300624d03d7
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125102"
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

# <span data-ttu-id="44600-104">在 Microsoft Edge DevTools 中模拟移动设备</span><span class="sxs-lookup"><span data-stu-id="44600-104">Emulate mobile devices in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="44600-105">使用 **设备仿真** 来大致了解你的页面在移动设备上的外观和响应。</span><span class="sxs-lookup"><span data-stu-id="44600-105">Use **Device emulation** to approximate how your page looks and responds on a mobile device.</span></span>  <span data-ttu-id="44600-106">Microsoft Edge DevTools 提供了一系列功能，可帮助你模拟移动设备。</span><span class="sxs-lookup"><span data-stu-id="44600-106">The Microsoft Edge DevTools provide a collection of features to help you emulate mobile devices.</span></span>  <span data-ttu-id="44600-107">集合包含以下功能。</span><span class="sxs-lookup"><span data-stu-id="44600-107">The collection includes the following features.</span></span>  

*   [<span data-ttu-id="44600-108">模拟移动视区</span><span class="sxs-lookup"><span data-stu-id="44600-108">Simulate a mobile viewport</span></span>](#simulate-a-mobile-viewport)  
*   [<span data-ttu-id="44600-109">阻止网络</span><span class="sxs-lookup"><span data-stu-id="44600-109">Throttle the network</span></span>](#throttle-the-network-only)  
*   [<span data-ttu-id="44600-110">调节 CPU</span><span class="sxs-lookup"><span data-stu-id="44600-110">Throttle the CPU</span></span>](#throttle-the-cpu-only)  
*   [<span data-ttu-id="44600-111">模拟地理位置</span><span class="sxs-lookup"><span data-stu-id="44600-111">Simulate geolocation</span></span>](#override-geolocation)  
*   [<span data-ttu-id="44600-112">设置方向</span><span class="sxs-lookup"><span data-stu-id="44600-112">Set orientation</span></span>](#set-orientation)  
*   [<span data-ttu-id="44600-113">设置用户代理字符串</span><span class="sxs-lookup"><span data-stu-id="44600-113">Set the user agent string</span></span>](#set-user-agent-string)  

## <span data-ttu-id="44600-114">限制</span><span class="sxs-lookup"><span data-stu-id="44600-114">Limitations</span></span>  

<span data-ttu-id="44600-115">**设备模拟** 是你的页面在移动设备上的 [第一顺序近似值][WikiApproximation] 。</span><span class="sxs-lookup"><span data-stu-id="44600-115">**Device emulation** is a [first-order approximation][WikiApproximation] of the look and feel of your page on a mobile device.</span></span>  <span data-ttu-id="44600-116">**设备仿真** 实际上并不在移动设备上运行代码。</span><span class="sxs-lookup"><span data-stu-id="44600-116">**Device emulation** does not actually run your code on a mobile device.</span></span>  <span data-ttu-id="44600-117">而是从便携式计算机或桌面模拟移动用户体验。</span><span class="sxs-lookup"><span data-stu-id="44600-117">Instead you simulate the mobile user experience from your laptop or desktop.</span></span>  

<span data-ttu-id="44600-118">移动设备的某些方面从不在 DevTools 中进行模拟。</span><span class="sxs-lookup"><span data-stu-id="44600-118">Some aspects of mobile devices are never emulated in DevTools.</span></span>  <span data-ttu-id="44600-119">例如，移动 Cpu 的体系结构不同于便携式计算机或桌面 Cpu 的体系结构。</span><span class="sxs-lookup"><span data-stu-id="44600-119">For example, the architecture of mobile CPUs is different than the architecture of laptop or desktop CPUs.</span></span>  <span data-ttu-id="44600-120">如果有疑问，最佳做法是在移动设备上实际运行您的页面。</span><span class="sxs-lookup"><span data-stu-id="44600-120">When in doubt, your best bet is to actually run your page on a mobile device.</span></span>  <span data-ttu-id="44600-121">在页面实际在移动设备上运行时，可使用 [远程调试] [DevToolsRemoteDebugging] 与你的计算机中的页面代码进行交互。</span><span class="sxs-lookup"><span data-stu-id="44600-121">Use [Remote Debugging][DevToolsRemoteDebugging] to interact with the code of a page from your machine while your page actually runs on a mobile device.</span></span>  <span data-ttu-id="44600-122">当您与代码交互时，您可以查看、更改、调试、配置文件或全部四种。</span><span class="sxs-lookup"><span data-stu-id="44600-122">You may view, change, debug, profile, or all four while you interact with the code.</span></span>  <span data-ttu-id="44600-123">您的计算机可能是笔记本或台式计算机。</span><span class="sxs-lookup"><span data-stu-id="44600-123">Your machine may be a notebook or desktop computer.</span></span>  

## <span data-ttu-id="44600-124">模拟移动视区</span><span class="sxs-lookup"><span data-stu-id="44600-124">Simulate a mobile viewport</span></span>  

<span data-ttu-id="44600-125">选择 " **切换设备仿真**  \ (![ 切换设备" 工具栏 ][ImageDeviceToolbarIcon] \ ) 或选择 " **自定义和控制 DevTools** \ (`...` \" ) > **设备仿真** "打开可使您模拟移动视区的 UI。</span><span class="sxs-lookup"><span data-stu-id="44600-125">Choose **Toggle device emulation**  \(![Toggle Device Toolbar][ImageDeviceToolbarIcon]\) or choose **Customize and control DevTools** \(`...`\) > **Device emulation** to open the UI that enables you to simulate a mobile viewport.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
    <span data-ttu-id="44600-127">"设备" 工具栏</span><span class="sxs-lookup"><span data-stu-id="44600-127">The Device Toolbar</span></span>  
:::image-end:::  

<span data-ttu-id="44600-128">默认情况下，设备工具栏将在 "响应式" 视区模式下打开。</span><span class="sxs-lookup"><span data-stu-id="44600-128">By default the Device Toolbar opens in Responsive Viewport Mode.</span></span>  

### <span data-ttu-id="44600-129">响应式视区模式</span><span class="sxs-lookup"><span data-stu-id="44600-129">Responsive Viewport Mode</span></span>  

<span data-ttu-id="44600-130">若要跨多个屏幕大小快速测试页面的外观，请拖动图柄以将视区大小调整为所需的尺寸。</span><span class="sxs-lookup"><span data-stu-id="44600-130">To quickly test the look and feel of your page across multiple screen sizes, drag the handles to resize the viewport to your required dimensions.</span></span>  <span data-ttu-id="44600-131">您也可以在 "宽度" 和 "高度" 框中输入特定值。</span><span class="sxs-lookup"><span data-stu-id="44600-131">You may also enter specific values in the width and height boxes.</span></span>  <span data-ttu-id="44600-132">在下图中，宽度设置为 `626` ，高度设置为 `516` 。</span><span class="sxs-lookup"><span data-stu-id="44600-132">In the following figure, the width is set to `626` and the height is set to `516`.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png":::
    <span data-ttu-id="44600-134">在 "响应" 视口模式下更改视区尺寸的控制滑块</span><span class="sxs-lookup"><span data-stu-id="44600-134">The handles for changing the dimensions of the viewport when in Responsive Viewport Mode</span></span>  
:::image-end:::  

#### <span data-ttu-id="44600-135">显示媒体查询</span><span class="sxs-lookup"><span data-stu-id="44600-135">Show media queries</span></span>  

<span data-ttu-id="44600-136">如果你已在页面上定义了媒体查询，则通过在你的视区上方显示媒体查询断点，跳转到这些媒体查询将生效的视区维度。</span><span class="sxs-lookup"><span data-stu-id="44600-136">If you have defined media queries on your page, jump to the viewport dimensions where those media queries take effect by showing media query breakpoints above your viewport.</span></span>  <span data-ttu-id="44600-137">选择 "**更多选项**"  >  **显示媒体查询**。</span><span class="sxs-lookup"><span data-stu-id="44600-137">Choose **More options** > **Show media queries**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png":::
   **<span data-ttu-id="44600-139">显示媒体查询</span><span class="sxs-lookup"><span data-stu-id="44600-139">Show media queries</span></span>**  
:::image-end:::  

<span data-ttu-id="44600-140">选择一个断点以更改视区的宽度，以便触发媒体查询。</span><span class="sxs-lookup"><span data-stu-id="44600-140">Choose a breakpoint to change the width of the viewport so that the media query gets triggered.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png":::
   <span data-ttu-id="44600-142">选择断点以更改视区的宽度</span><span class="sxs-lookup"><span data-stu-id="44600-142">Choose a breakpoint to change the width of the viewport</span></span>  
:::image-end:::  

#### <span data-ttu-id="44600-143">设置设备类型</span><span class="sxs-lookup"><span data-stu-id="44600-143">Set the device type</span></span>  

<span data-ttu-id="44600-144">使用 **设备类型** 列表来模拟移动设备或桌面设备。</span><span class="sxs-lookup"><span data-stu-id="44600-144">Use the **Device Type** list to simulate a mobile device or desktop device.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png":::
   <span data-ttu-id="44600-146">**设备类型**列表</span><span class="sxs-lookup"><span data-stu-id="44600-146">The **Device Type** list</span></span>  
:::image-end:::  

<span data-ttu-id="44600-147">下表介绍了可用设备类型选项之间的差异。</span><span class="sxs-lookup"><span data-stu-id="44600-147">The following table describes the differences between the available device type options.</span></span>  <span data-ttu-id="44600-148">呈现方法列引用 Microsoft Edge 是否将页面呈现为移动设备或桌面视区。</span><span class="sxs-lookup"><span data-stu-id="44600-148">The Rendering method column refers to whether Microsoft Edge renders the page as a mobile or desktop viewport.</span></span>  <span data-ttu-id="44600-149">光标图标列指悬停在页面上时看到的光标类型。</span><span class="sxs-lookup"><span data-stu-id="44600-149">The Cursor icon column refers to what type of cursor you see when you hover on the page.</span></span>  <span data-ttu-id="44600-150">"触发事件" 列指 `touch` `click` 当您与页面交互时，页面是触发还是事件。</span><span class="sxs-lookup"><span data-stu-id="44600-150">The Events triggered column refers to whether the page triggers `touch` or `click` events when you interact with the page.</span></span>  

| <span data-ttu-id="44600-151">选项</span><span class="sxs-lookup"><span data-stu-id="44600-151">Option</span></span> | <span data-ttu-id="44600-152">呈现方法</span><span class="sxs-lookup"><span data-stu-id="44600-152">Rendering method</span></span> | <span data-ttu-id="44600-153">光标图标</span><span class="sxs-lookup"><span data-stu-id="44600-153">Cursor icon</span></span> | <span data-ttu-id="44600-154">触发的事件</span><span class="sxs-lookup"><span data-stu-id="44600-154">Events triggered</span></span> |  
|:--- |:--- |:--- |:--- |  
| <span data-ttu-id="44600-155">移动版</span><span class="sxs-lookup"><span data-stu-id="44600-155">Mobile</span></span> | <span data-ttu-id="44600-156">移动版</span><span class="sxs-lookup"><span data-stu-id="44600-156">Mobile</span></span> | <span data-ttu-id="44600-157">圆形</span><span class="sxs-lookup"><span data-stu-id="44600-157">Circle</span></span> | <span data-ttu-id="44600-158">触摸</span><span class="sxs-lookup"><span data-stu-id="44600-158">touch</span></span> |  
| <span data-ttu-id="44600-159">移动 \ (无接触 \ ) </span><span class="sxs-lookup"><span data-stu-id="44600-159">Mobile \(no touch\)</span></span> | <span data-ttu-id="44600-160">移动版</span><span class="sxs-lookup"><span data-stu-id="44600-160">Mobile</span></span> | <span data-ttu-id="44600-161">正常</span><span class="sxs-lookup"><span data-stu-id="44600-161">Normal</span></span> | <span data-ttu-id="44600-162">单击</span><span class="sxs-lookup"><span data-stu-id="44600-162">click</span></span> |  
| <span data-ttu-id="44600-163">桌面</span><span class="sxs-lookup"><span data-stu-id="44600-163">Desktop</span></span> | <span data-ttu-id="44600-164">桌面</span><span class="sxs-lookup"><span data-stu-id="44600-164">Desktop</span></span> | <span data-ttu-id="44600-165">正常</span><span class="sxs-lookup"><span data-stu-id="44600-165">Normal</span></span> | <span data-ttu-id="44600-166">单击</span><span class="sxs-lookup"><span data-stu-id="44600-166">click</span></span> |  
| <span data-ttu-id="44600-167">桌面 (触控 \ ) </span><span class="sxs-lookup"><span data-stu-id="44600-167">Desktop \(touch\)</span></span> | <span data-ttu-id="44600-168">桌面</span><span class="sxs-lookup"><span data-stu-id="44600-168">Desktop</span></span> | <span data-ttu-id="44600-169">圆形</span><span class="sxs-lookup"><span data-stu-id="44600-169">Circle</span></span> | <span data-ttu-id="44600-170">触摸</span><span class="sxs-lookup"><span data-stu-id="44600-170">touch</span></span> |  

> [!NOTE]
> <span data-ttu-id="44600-171">如果未显示 "**设备类型**" 列表，请选择 "**更多选项**"  >  **添加设备类型**。</span><span class="sxs-lookup"><span data-stu-id="44600-171">If the **Device Type** list is not displayed, choose **More options** > **Add device type**.</span></span>  

### <span data-ttu-id="44600-172">移动设备视区模式</span><span class="sxs-lookup"><span data-stu-id="44600-172">Mobile Device Viewport Mode</span></span>  

<span data-ttu-id="44600-173">若要模拟特定移动设备的尺寸，请从 **设备** 列表中选择该设备。</span><span class="sxs-lookup"><span data-stu-id="44600-173">To simulate the dimensions of a specific mobile device, select the device from the **Device** list.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-device-list.msft.png":::
   <span data-ttu-id="44600-175">**设备**列表</span><span class="sxs-lookup"><span data-stu-id="44600-175">The **Device** list</span></span>  
:::image-end:::  

#### <span data-ttu-id="44600-176">将视区旋转到横向方向</span><span class="sxs-lookup"><span data-stu-id="44600-176">Rotate the viewport to landscape orientation</span></span>  

<span data-ttu-id="44600-177">以横向方向测试您的网页。</span><span class="sxs-lookup"><span data-stu-id="44600-177">Test your webpage in landscape orientation.</span></span>  

*   <span data-ttu-id="44600-178">若要将视区旋转到横向方向，请选择 " **旋转** \ (![ 旋转 ][ImageRotateIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="44600-178">To rotate the viewport to landscape orientation, choose **Rotate** \(![Rotate][ImageRotateIcon]\).</span></span>  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-landscape.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-landscape.msft.png":::
       <span data-ttu-id="44600-180">横向显示的页面</span><span class="sxs-lookup"><span data-stu-id="44600-180">Page displayed in landscape orientation</span></span>  
    :::image-end:::  
    
> [!NOTE]
> <span data-ttu-id="44600-181">如果**设备工具栏**较窄，"**旋转**" 按钮将消失。</span><span class="sxs-lookup"><span data-stu-id="44600-181">The **Rotate** button disappears if your **Device Toolbar** is narrow.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   <span data-ttu-id="44600-183">" **设备" 工具栏**</span><span class="sxs-lookup"><span data-stu-id="44600-183">The **Device Toolbar**</span></span>  
:::image-end:::  

<span data-ttu-id="44600-184">有关详细信息，请转到 [设置方向](#set-orientation)。</span><span class="sxs-lookup"><span data-stu-id="44600-184">For more information, go to [Set orientation](#set-orientation).</span></span>  

#### <span data-ttu-id="44600-185">显示设备帧</span><span class="sxs-lookup"><span data-stu-id="44600-185">Show device frame</span></span>  

<span data-ttu-id="44600-186">当模拟特定移动设备（如 iPhone 6）的尺寸时，将在视区周围显示物理设备帧。</span><span class="sxs-lookup"><span data-stu-id="44600-186">Display the physical device frame around the viewport when you simulate the dimensions of a specific mobile device such as an iPhone 6.</span></span>  

1.  <span data-ttu-id="44600-187">打开 " **更多选项**"。</span><span class="sxs-lookup"><span data-stu-id="44600-187">Open **More options**.</span></span>  
1.  <span data-ttu-id="44600-188">选择 " **显示设备帧**"。</span><span class="sxs-lookup"><span data-stu-id="44600-188">Choose **Show device frame**.</span></span>  

> [!NOTE]
> <span data-ttu-id="44600-189">如果您没有看到特定设备的设备框架，则意味着 DevTools 没有该选项的图片。</span><span class="sxs-lookup"><span data-stu-id="44600-189">If you do not see a device frame for a particular device, it means that DevTools does not have art for that option.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png":::
         <span data-ttu-id="44600-191">显示设备帧</span><span class="sxs-lookup"><span data-stu-id="44600-191">Show device frame</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png":::
         <span data-ttu-id="44600-193">IPhone 6 的设备帧</span><span class="sxs-lookup"><span data-stu-id="44600-193">The device frame for the iPhone 6</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <span data-ttu-id="44600-194">添加自定义移动设备</span><span class="sxs-lookup"><span data-stu-id="44600-194">Add a custom mobile device</span></span>  

<span data-ttu-id="44600-195">如果默认列表中未包括所需的移动设备选项，则可以添加自定义设备。</span><span class="sxs-lookup"><span data-stu-id="44600-195">If the mobile device option that you need is not included on the default list, you may add a custom device.</span></span>  <span data-ttu-id="44600-196">若要添加自定义设备，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="44600-196">To add a custom device, complete the following steps.</span></span>  

1.  <span data-ttu-id="44600-197">选择 " **设备** 列表" > " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="44600-197">Choose the **Device** list > **Edit**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png":::
       <span data-ttu-id="44600-199">选择 "**编辑**"</span><span class="sxs-lookup"><span data-stu-id="44600-199">Choose **Edit**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="44600-200">选择 " **添加自定义设备**"。</span><span class="sxs-lookup"><span data-stu-id="44600-200">Choose **Add custom device**.</span></span>  
1.  <span data-ttu-id="44600-201">在 **模拟设备**上，输入自定义设备的设备名称、屏幕宽度和屏幕高度。</span><span class="sxs-lookup"><span data-stu-id="44600-201">On **Emulated Devices**, enter a device name, screen width, and screen height for the custom device.</span></span>  <span data-ttu-id="44600-202">[设备像素比率][MDNWindowDevicePixelRatio]、[用户代理字符串][MDNUserAgent]和[设备类型](#set-the-device-type)字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="44600-202">The [device pixel ratio][MDNWindowDevicePixelRatio], [user agent string][MDNUserAgent], and [device type](#set-the-device-type) fields are optional.</span></span>  <span data-ttu-id="44600-203">"设备类型" 字段默认为 " **移动**"。</span><span class="sxs-lookup"><span data-stu-id="44600-203">The device type field defaults to **Mobile**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png":::
       <span data-ttu-id="44600-205">创建自定义设备</span><span class="sxs-lookup"><span data-stu-id="44600-205">Create a custom device</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="44600-206">显示标尺</span><span class="sxs-lookup"><span data-stu-id="44600-206">Show rulers</span></span>  

<span data-ttu-id="44600-207">如果需要测量屏幕尺寸，可以使用标尺测量屏幕大小（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="44600-207">If you need to measure screen dimensions, you may use rulers to measure the screen size in pixels.</span></span>  <span data-ttu-id="44600-208">选择 "**更多选项**"  >  **显示 "标尺**" 以在视区左侧和左侧显示标尺。</span><span class="sxs-lookup"><span data-stu-id="44600-208">Choose **More options** > **Show rulers** to display rulers above and to the left of your viewport.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png":::
         <span data-ttu-id="44600-210">用于显示标尺的菜单项</span><span class="sxs-lookup"><span data-stu-id="44600-210">Menu item to display rulers</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-rulers.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-rulers.msft.png":::
         <span data-ttu-id="44600-212">视区左侧和左侧的标尺</span><span class="sxs-lookup"><span data-stu-id="44600-212">Rulers above and to the left of the viewport</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="44600-213">缩放视区</span><span class="sxs-lookup"><span data-stu-id="44600-213">Zoom the viewport</span></span>  

<span data-ttu-id="44600-214">若要以多个缩放级别测试页面的外观，请使用 " **缩放** " 列表放大或缩小。</span><span class="sxs-lookup"><span data-stu-id="44600-214">To test the look and feel of your page at multiple zoom levels, use the **Zoom** list to zoom in or out.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-zoom.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-zoom.msft.png":::
   **<span data-ttu-id="44600-216">缩放</span><span class="sxs-lookup"><span data-stu-id="44600-216">Zoom</span></span>**  
:::image-end:::  

## <span data-ttu-id="44600-217">限制网络和 CPU</span><span class="sxs-lookup"><span data-stu-id="44600-217">Throttle the network and CPU</span></span>  

<span data-ttu-id="44600-218">移动设备通常具有网络和 CPU 限制。</span><span class="sxs-lookup"><span data-stu-id="44600-218">Mobile devices often have network and CPU constraints.</span></span>  <span data-ttu-id="44600-219">确保你可以测试页面的加载速度以及它在不同 internet 和 CPU 速度中的响应速度。</span><span class="sxs-lookup"><span data-stu-id="44600-219">Ensure you test how quickly your page loads and how it responds at different internet and CPU speeds.</span></span>  

<span data-ttu-id="44600-220">限制网络和 CPU。</span><span class="sxs-lookup"><span data-stu-id="44600-220">Throttle the network and CPU.</span></span>  

1.  <span data-ttu-id="44600-221">选择 " **限制** 列表"，然后将预置更改为 " **中层移动** " 或 " **低端手机**"。</span><span class="sxs-lookup"><span data-stu-id="44600-221">Choose **Throttle** list and change the preset to **Mid-tier mobile** or **Low-end mobile**.</span></span>  
    *   <span data-ttu-id="44600-222">中层**移动**模拟 `fast 3G` 和限制你的 CPU。</span><span class="sxs-lookup"><span data-stu-id="44600-222">**Mid-tier mobile** simulates `fast 3G` and throttles your CPU.</span></span>  <span data-ttu-id="44600-223">这比平时慢4倍。</span><span class="sxs-lookup"><span data-stu-id="44600-223">It is four times slower than normal.</span></span>  
    *   <span data-ttu-id="44600-224">**低端移动** 模拟 `slow 3G` 和限制您的 CPU。</span><span class="sxs-lookup"><span data-stu-id="44600-224">**Low-end mobile** simulates `slow 3G` and throttles your CPU.</span></span>  <span data-ttu-id="44600-225">这比平时慢六倍。</span><span class="sxs-lookup"><span data-stu-id="44600-225">It is six times slower than normal.</span></span>  
    
<span data-ttu-id="44600-226">所有限制都基于便携式计算机或桌面机的正常功能。</span><span class="sxs-lookup"><span data-stu-id="44600-226">All of the throttling is based upon the normal capability of your laptop or desktop.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-throttle.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-throttle.msft.png":::
   <span data-ttu-id="44600-228">"设备" 工具栏中的 " **限制** " 列表</span><span class="sxs-lookup"><span data-stu-id="44600-228">The **Throttle** list in the Device Toolbar</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="44600-229">如果 " **限制" 列表** 处于隐藏状态，则你的 **设备工具栏** 太窄。</span><span class="sxs-lookup"><span data-stu-id="44600-229">If the **Throttle list** is hidden, your **Device Toolbar** is too narrow.</span></span>  <span data-ttu-id="44600-230">若要访问 **限制列表**，请增大 "设备" **工具栏**的宽度。</span><span class="sxs-lookup"><span data-stu-id="44600-230">To access the **Throttle list**, increase the width of the **Device Toolbar**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   <span data-ttu-id="44600-232">" **设备" 工具栏**</span><span class="sxs-lookup"><span data-stu-id="44600-232">The **Device Toolbar**</span></span>  
:::image-end:::  

### <span data-ttu-id="44600-233">仅调节 CPU</span><span class="sxs-lookup"><span data-stu-id="44600-233">Throttle the CPU only</span></span>  

<span data-ttu-id="44600-234">若要仅限制 CPU 而不是网络，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="44600-234">To throttle the CPU only and not the network, complete the following steps.</span></span>

1.  <span data-ttu-id="44600-235">选择 " **性能** " 面板，然后选择 " **捕获设置** \ (![ 捕获设置 ][ImageCaptureIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="44600-235">Choose the **Performance** panel, and choose **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\).</span></span>
1.  <span data-ttu-id="44600-236">选择**CPU**  >  **4x 减速**或**6x 减速**。</span><span class="sxs-lookup"><span data-stu-id="44600-236">Choose **CPU** > **4x slowdown** or **6x slowdown**.</span></span>
    
    :::image type="complex" source="../media/device-mode-performance-cpu-throttle.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-performance-cpu-throttle.msft.png":::
       <span data-ttu-id="44600-238">"**性能**" 面板中的**CPU**列表</span><span class="sxs-lookup"><span data-stu-id="44600-238">The **CPU** list in the **Performance** panel</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="44600-239">仅限制网络</span><span class="sxs-lookup"><span data-stu-id="44600-239">Throttle the network only</span></span>  

<span data-ttu-id="44600-240">若要仅限制网络，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="44600-240">To throttle the network only, complete the following steps.</span></span>

1.  <span data-ttu-id="44600-241">选择 " **网络** " 面板。</span><span class="sxs-lookup"><span data-stu-id="44600-241">Choose the **Network** panel.</span></span>
1.  <span data-ttu-id="44600-242">选择 "**联机**  >  **快速 3g** " 或 "**低速 3g**"。</span><span class="sxs-lookup"><span data-stu-id="44600-242">Choose **Online** > **Fast 3G** or **Slow 3G**.</span></span>
    
    :::image type="complex" source="../media/device-mode-network-throttle.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-network-throttle.msft.png":::
       <span data-ttu-id="44600-244">网络面板中的 **限制** 列表</span><span class="sxs-lookup"><span data-stu-id="44600-244">The **Throttle** list in the Network panel</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="44600-245">或选择 `Control` + `Shift` + `P` \ (Windows、Linux \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "**命令" 菜单**，键入 `3G` ，然后选择 "**启用快速3g 限制**" 或 "**启用慢速3g 限制**"。</span><span class="sxs-lookup"><span data-stu-id="44600-245">Or select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**, type `3G`, and choose **Enable fast 3G throttling** or **Enable slow 3G throttling**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-command-menu-throttle.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-command-menu-throttle.msft.png":::
       <span data-ttu-id="44600-247">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="44600-247">The **Command Menu**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="44600-248">您也可以从 " **性能** " 面板设置网络限制。</span><span class="sxs-lookup"><span data-stu-id="44600-248">You may also set network throttling from the **Performance** panel.</span></span>  

1.  <span data-ttu-id="44600-249">选择 **"捕获设置** \ (![ 捕获设置 ][ImageCaptureIcon] \ ) "，然后选择 " **网络** " 列表，并将预设置更改为 " **快速 3g** " 或 " **低速 3g**"。</span><span class="sxs-lookup"><span data-stu-id="44600-249">Choose **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\) and choose the **Network** list and change the preset to **Fast 3G** or **Slow 3G**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-performance-network-throttle.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-performance-network-throttle.msft.png":::
       <span data-ttu-id="44600-251">从 **性能** 面板设置网络限制</span><span class="sxs-lookup"><span data-stu-id="44600-251">Set network throttling from the **Performance** panel</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="44600-252">替代地理位置</span><span class="sxs-lookup"><span data-stu-id="44600-252">Override geolocation</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="44600-253">如果你的页面依赖于移动设备上的地理位置信息来正确呈现，请使用地理位置替代 UI 来提供不同的 geolocations。</span><span class="sxs-lookup"><span data-stu-id="44600-253">If your page depends on geolocation information from a mobile device to render properly, provide different geolocations using the geolocation overriding UI.</span></span>  

      1.  <span data-ttu-id="44600-254">选择 "**自定义和控制 DevTools** \ (`...` \ ) " > "**其他工具**  >  **传感器**"。</span><span class="sxs-lookup"><span data-stu-id="44600-254">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         <span data-ttu-id="44600-256">地理位置的**传感器**</span><span class="sxs-lookup"><span data-stu-id="44600-256">**Sensors** for geolocation</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  <span data-ttu-id="44600-257">打开 "命令" 菜单。</span><span class="sxs-lookup"><span data-stu-id="44600-257">Open the Command Menu.</span></span>  
          *   <span data-ttu-id="44600-258">选择 `Control` + `Shift` + `P` \ (Windows、Linux \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 。</span><span class="sxs-lookup"><span data-stu-id="44600-258">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
      1. <span data-ttu-id="44600-259">键入 `Sensors` ，然后选择 " **显示传感器**"。</span><span class="sxs-lookup"><span data-stu-id="44600-259">Type `Sensors`, and choose **Show Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         <span data-ttu-id="44600-261">**显示** 地理位置的传感器</span><span class="sxs-lookup"><span data-stu-id="44600-261">**Show Sensors** for geolocation</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="44600-262">在 " **传感器** " 面板上，你可以使用 " **位置** " 下拉菜单选择 DevTools 中包含的预设位置之一。</span><span class="sxs-lookup"><span data-stu-id="44600-262">On the **Sensors** panel, you may select one of the preset locations included in DevTools using the **Location** drop-down menu.</span></span>  <span data-ttu-id="44600-263">若要输入自定义位置，请选择 " **其他" ...**</span><span class="sxs-lookup"><span data-stu-id="44600-263">To enter a custom location, choose **Other…**</span></span> <span data-ttu-id="44600-264">并输入自定义位置的坐标。</span><span class="sxs-lookup"><span data-stu-id="44600-264">and enter the coordinates of your custom location.</span></span>  <span data-ttu-id="44600-265">当位置信息不可用时，若要在错误状态中测试页面，请选择 " **位置不可用**"。</span><span class="sxs-lookup"><span data-stu-id="44600-265">To test your page in an error state when location information is unavailable, choose **Location unavailable**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png":::
    <span data-ttu-id="44600-267">选择了预设位置的 "**传感器**" 面板。</span><span class="sxs-lookup"><span data-stu-id="44600-267">**Sensors** panel with a preset location selected.</span></span>  
:::image-end:::

## <span data-ttu-id="44600-268">设置方向</span><span class="sxs-lookup"><span data-stu-id="44600-268">Set orientation</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="44600-269">如果页面依赖于移动设备上的方向信息来正确呈现，请打开 "方向" UI。</span><span class="sxs-lookup"><span data-stu-id="44600-269">If your page depends on orientation information from a mobile device to render properly, open the orientation UI.</span></span>  

      1.  <span data-ttu-id="44600-270">选择 "**自定义和控制 DevTools** \ (`...` \ ) " > "**其他工具**  >  **传感器**"。</span><span class="sxs-lookup"><span data-stu-id="44600-270">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         <span data-ttu-id="44600-272">方向**传感器**</span><span class="sxs-lookup"><span data-stu-id="44600-272">**Sensors** for orientation</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  <span data-ttu-id="44600-273">打开 "命令" 菜单。</span><span class="sxs-lookup"><span data-stu-id="44600-273">Open the Command Menu.</span></span>  
          *   <span data-ttu-id="44600-274">选择 `Control` + `Shift` + `P` \ (Windows、Linux \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 。</span><span class="sxs-lookup"><span data-stu-id="44600-274">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
      1. <span data-ttu-id="44600-275">键入 `Sensors` ，然后选择 " **显示传感器**"。</span><span class="sxs-lookup"><span data-stu-id="44600-275">Type `Sensors`, and choose **Show Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         <span data-ttu-id="44600-277">**显示** 方向的传感器</span><span class="sxs-lookup"><span data-stu-id="44600-277">**Show Sensors** for orientation</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="44600-278">在 " **传感器** " 面板上，您可以从 " **方向** " 下拉菜单中选择预设方向。</span><span class="sxs-lookup"><span data-stu-id="44600-278">On the **Sensors** panel, you may select a preset orientation from the **Orientation** drop-down menu.</span></span>  <span data-ttu-id="44600-279">若要输入自己的方向，请选择 " **自定义方向**"，然后输入您自己的 [alpha][MDNDeviceOrientaitonAlpha]、 [beta][MDNDeviceOrientaitonBeta]和 [伽玛][MDNDeviceOrientaitonGamma] 值。</span><span class="sxs-lookup"><span data-stu-id="44600-279">To enter your own orientation, choose **Custom orientation**, and enter your own [alpha][MDNDeviceOrientaitonAlpha], [beta][MDNDeviceOrientaitonBeta], and [gamma][MDNDeviceOrientaitonGamma] values.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png":::
    <span data-ttu-id="44600-281">"**传感器**" 面板上的**方向**选项</span><span class="sxs-lookup"><span data-stu-id="44600-281">**Orientation** options on the **Sensors** panel</span></span>  
:::image-end:::  

## <span data-ttu-id="44600-282">设置用户代理字符串</span><span class="sxs-lookup"><span data-stu-id="44600-282">Set user agent string</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="44600-283">如果页面依赖于移动设备的用户代理字符串来正确呈现，请使用 " **网络条件** " 面板提供不同的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="44600-283">If your page depends on the user agent string from a mobile device to render properly, use the **Network conditions** panel to provide different user agent strings.</span></span>  
      
      1.  <span data-ttu-id="44600-284">选择 "**自定义和控制 DevTools** \ (`...` \ ) " >**更多工具**  >  **网络条件**。</span><span class="sxs-lookup"><span data-stu-id="44600-284">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Network conditions**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png":::
         <span data-ttu-id="44600-286">"**更多工具**" 菜单中的**网络条件**输入</span><span class="sxs-lookup"><span data-stu-id="44600-286">**Network conditions** entry in the **More tools** menu</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  <span data-ttu-id="44600-287">打开 "命令" 菜单。</span><span class="sxs-lookup"><span data-stu-id="44600-287">Open the Command Menu.</span></span>  
          *   <span data-ttu-id="44600-288">选择 `Control` + `Shift` + `P` \ (Windows、Linux \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 。</span><span class="sxs-lookup"><span data-stu-id="44600-288">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
      1. <span data-ttu-id="44600-289">键入 `Network conditions` ，然后选择 " **显示网络条件**"。</span><span class="sxs-lookup"><span data-stu-id="44600-289">Type `Network conditions`, and choose **Show Network conditions**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png":::
         **<span data-ttu-id="44600-291">显示网络条件</span><span class="sxs-lookup"><span data-stu-id="44600-291">Show Network conditions</span></span>**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="44600-292">在 " **用户代理**" 旁边，清除 " **自动选择** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="44600-292">Next to **User agent**, clear the **Select automatically** checkbox.</span></span>  <span data-ttu-id="44600-293">然后，选择 " **自定义 ...** " 以从预定义的用户代理字符串列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="44600-293">Then, choose **Custom...** to select from a list of predefined user agent strings.</span></span>  <span data-ttu-id="44600-294">若要输入自己的用户代理字符串，请在 " **输入自定义用户代理**" 中输入字符串。</span><span class="sxs-lookup"><span data-stu-id="44600-294">To enter your own user agent string, enter the string in **Enter a custom user agent**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png":::
    <span data-ttu-id="44600-296">在 macOS 上将用户代理字符串设置为 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="44600-296">Set the user agent string to Microsoft Edge on macOS</span></span>  
:::image-end:::  

## <span data-ttu-id="44600-297">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="44600-297">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCaptureIcon]: ../media/capture-settings-icon.msft.png  
[ImageDeviceToolbarIcon]: ../media/toggle-device-toolbar-dark-icon.msft.png  
[ImageRotateIcon]: ../media/rotate-dark-icon.msft.png  

<!-- links -->  

<!--[DevToolsCommunity]: ../index.md#community "Join the DevTools community | Microsoft Docs"  -->
[DevToolsRemoteDebugging]: ../remote-debugging/index.md "开始使用远程调试 Android 设备" |Microsoft 文档 "  

[MDNWindowDevicePixelRatio]: https://developer.mozilla.org/docs/Web/API/Window/devicePixelRatio "DevicePixelRatio |MDN"  
[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "用户代理 |MDN"  
[MDNDeviceOrientaitonAlpha]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/alpha "DeviceOrientationEvent |MDN"  
[MDNDeviceOrientaitonBeta]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/beta "DeviceOrientationEvent |MDN"  
[MDNDeviceOrientaitonGamma]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/gamma "DeviceOrientationEvent |MDN"  

[WikiApproximation]: https://en.wikipedia.org/wiki/Order_of_approximation#First-order "近似值-第一顺序-维基百科的顺序"  

> [!NOTE]
> <span data-ttu-id="44600-305">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="44600-305">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="44600-306">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="44600-306">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="44600-308">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="44600-308">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
