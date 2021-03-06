---
description: 使用 Microsoft Edge 中的虚拟设备构建移动第一网站。
title: 模拟 Microsoft Edge DevTools 中的移动设备
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 模拟， 设备， 模拟， 移动
ms.openlocfilehash: 1a83dece95acba386385bfea035a9e2c91639240
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398782"
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

# <a name="emulate-mobile-devices-in-microsoft-edge-devtools"></a><span data-ttu-id="9b6c1-104">模拟 Microsoft Edge DevTools 中的移动设备</span><span class="sxs-lookup"><span data-stu-id="9b6c1-104">Emulate mobile devices in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="9b6c1-105">使用 **设备仿真** 来大致了解页面在移动设备上的外观和响应方式。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-105">Use **Device emulation** to approximate how your page looks and responds on a mobile device.</span></span>  <span data-ttu-id="9b6c1-106">Microsoft Edge DevTools 提供了一组功能，可帮助你模拟移动设备。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-106">The Microsoft Edge DevTools provide a collection of features to help you emulate mobile devices.</span></span>  <span data-ttu-id="9b6c1-107">该集合包括以下功能。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-107">The collection includes the following features.</span></span>  

*   [<span data-ttu-id="9b6c1-108">模拟移动视口</span><span class="sxs-lookup"><span data-stu-id="9b6c1-108">Simulate a mobile viewport</span></span>](#simulate-a-mobile-viewport)  
*   [<span data-ttu-id="9b6c1-109">限制网络</span><span class="sxs-lookup"><span data-stu-id="9b6c1-109">Throttle the network</span></span>](#throttle-the-network-only)  
*   [<span data-ttu-id="9b6c1-110">限制 CPU</span><span class="sxs-lookup"><span data-stu-id="9b6c1-110">Throttle the CPU</span></span>](#throttle-the-cpu-only)  
*   [<span data-ttu-id="9b6c1-111">模拟地理位置</span><span class="sxs-lookup"><span data-stu-id="9b6c1-111">Simulate geolocation</span></span>](#override-geolocation)  
*   [<span data-ttu-id="9b6c1-112">设置方向</span><span class="sxs-lookup"><span data-stu-id="9b6c1-112">Set orientation</span></span>](#set-orientation)  
*   [<span data-ttu-id="9b6c1-113">设置用户代理字符串</span><span class="sxs-lookup"><span data-stu-id="9b6c1-113">Set the user agent string</span></span>](#set-user-agent-string)  

## <a name="limitations"></a><span data-ttu-id="9b6c1-114">限制</span><span class="sxs-lookup"><span data-stu-id="9b6c1-114">Limitations</span></span>  

<span data-ttu-id="9b6c1-115">**设备仿真** 是 [移动设备中][WikiApproximation] 页面外观的一级近似值。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-115">**Device emulation** is a [first-order approximation][WikiApproximation] of the look and feel of your page on a mobile device.</span></span>  <span data-ttu-id="9b6c1-116">**设备仿真** 实际上不会在移动设备上运行你的代码。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-116">**Device emulation** does not actually run your code on a mobile device.</span></span>  <span data-ttu-id="9b6c1-117">相反，你可以模拟笔记本电脑或台式机的移动用户体验。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-117">Instead you simulate the mobile user experience from your laptop or desktop.</span></span>  

<span data-ttu-id="9b6c1-118">从不会在 DevTools 中模拟移动设备的某些方面。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-118">Some aspects of mobile devices are never emulated in DevTools.</span></span>  <span data-ttu-id="9b6c1-119">例如，移动 CPU 的体系结构不同于笔记本电脑或台式机 CPU 的体系结构。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-119">For example, the architecture of mobile CPUs is different than the architecture of laptop or desktop CPUs.</span></span>  <span data-ttu-id="9b6c1-120">当有疑问时，最佳匹配是在移动设备上实际运行页面。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-120">When in doubt, your best bet is to actually run your page on a mobile device.</span></span>  <span data-ttu-id="9b6c1-121">使用 [Remote Debugging][DevToolsRemoteDebugging] 与计算机中的页面代码进行交互，同时你的页面实际运行在移动设备上。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-121">Use [Remote Debugging][DevToolsRemoteDebugging] to interact with the code of a page from your machine while your page actually runs on a mobile device.</span></span>  <span data-ttu-id="9b6c1-122">当你与代码交互时，可以查看、更改、调试、配置文件或全部四者。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-122">You may view, change, debug, profile, or all four while you interact with the code.</span></span>  <span data-ttu-id="9b6c1-123">你的计算机可能是笔记本或台式计算机。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-123">Your machine may be a notebook or desktop computer.</span></span>  

## <a name="simulate-a-mobile-viewport"></a><span data-ttu-id="9b6c1-124">模拟移动视口</span><span class="sxs-lookup"><span data-stu-id="9b6c1-124">Simulate a mobile viewport</span></span>  

<span data-ttu-id="9b6c1-125">Choose **Toggle device emulation**  \ (![ Toggle Device Toolbar ][ImageDeviceToolbarIcon] \) or choose Customize **and control DevTools** \ (`...` \) > Device **emulation** to open the UI that enables you to simulate a mobile viewport.</span><span class="sxs-lookup"><span data-stu-id="9b6c1-125">Choose **Toggle device emulation**  \(![Toggle Device Toolbar][ImageDeviceToolbarIcon]\) or choose **Customize and control DevTools** \(`...`\) > **Device emulation** to open the UI that enables you to simulate a mobile viewport.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="设备工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
    <span data-ttu-id="9b6c1-127">设备工具栏</span><span class="sxs-lookup"><span data-stu-id="9b6c1-127">The Device Toolbar</span></span>  
:::image-end:::  

<span data-ttu-id="9b6c1-128">默认情况下，设备工具栏在响应式视口模式下打开。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-128">By default the Device Toolbar opens in Responsive Viewport Mode.</span></span>  

### <a name="responsive-viewport-mode"></a><span data-ttu-id="9b6c1-129">响应式视口模式</span><span class="sxs-lookup"><span data-stu-id="9b6c1-129">Responsive Viewport Mode</span></span>  

<span data-ttu-id="9b6c1-130">若要跨多个屏幕大小快速测试页面的外观，请拖动手柄以将视口大小调整为所需尺寸。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-130">To quickly test the look and feel of your page across multiple screen sizes, drag the handles to resize the viewport to your required dimensions.</span></span>  <span data-ttu-id="9b6c1-131">还可以在宽度和高度框中输入特定值。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-131">You may also enter specific values in the width and height boxes.</span></span>  <span data-ttu-id="9b6c1-132">在下图中，宽度设置为 ，高度 `626` 设置为 `516` 。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-132">In the following figure, the width is set to `626` and the height is set to `516`.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png" alt-text="在响应式视口模式下更改视口尺寸的句柄" lightbox="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png":::
    <span data-ttu-id="9b6c1-134">在响应式视口模式下更改视口尺寸的句柄</span><span class="sxs-lookup"><span data-stu-id="9b6c1-134">The handles for changing the dimensions of the viewport when in Responsive Viewport Mode</span></span>  
:::image-end:::  

#### <a name="show-media-queries"></a><span data-ttu-id="9b6c1-135">显示媒体查询</span><span class="sxs-lookup"><span data-stu-id="9b6c1-135">Show media queries</span></span>  

<span data-ttu-id="9b6c1-136">如果已定义页面上的媒体查询，请跳转到视口维度，这些媒体查询将在视口上方显示媒体查询断点，以生效。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-136">If you have defined media queries on your page, jump to the viewport dimensions where those media queries take effect by showing media query breakpoints above your viewport.</span></span>  <span data-ttu-id="9b6c1-137">选择 **"更多**  >  **选项"显示媒体查询**。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-137">Choose **More options** > **Show media queries**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png" alt-text="显示媒体查询" lightbox="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png":::
   **<span data-ttu-id="9b6c1-139">显示媒体查询</span><span class="sxs-lookup"><span data-stu-id="9b6c1-139">Show media queries</span></span>**  
:::image-end:::  

<span data-ttu-id="9b6c1-140">选择一个断点以更改视区的宽度，以便触发媒体查询。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-140">Choose a breakpoint to change the width of the viewport so that the media query gets triggered.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png" alt-text="选择断点以更改视口的宽度" lightbox="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png":::
   <span data-ttu-id="9b6c1-142">选择断点以更改视口的宽度</span><span class="sxs-lookup"><span data-stu-id="9b6c1-142">Choose a breakpoint to change the width of the viewport</span></span>  
:::image-end:::  

#### <a name="set-the-device-type"></a><span data-ttu-id="9b6c1-143">设置设备类型</span><span class="sxs-lookup"><span data-stu-id="9b6c1-143">Set the device type</span></span>  

<span data-ttu-id="9b6c1-144">使用 **"设备类型** "列表模拟移动设备或桌面设备。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-144">Use the **Device Type** list to simulate a mobile device or desktop device.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png" alt-text="设备类型列表" lightbox="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png":::
   <span data-ttu-id="9b6c1-146">设备 **类型** 列表</span><span class="sxs-lookup"><span data-stu-id="9b6c1-146">The **Device Type** list</span></span>  
:::image-end:::  

<span data-ttu-id="9b6c1-147">下表介绍了可用设备类型选项之间的差异。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-147">The following table describes the differences between the available device type options.</span></span>  <span data-ttu-id="9b6c1-148">呈现方法列是指 Microsoft Edge 是将页面呈现为移动视图还是桌面视口。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-148">The Rendering method column refers to whether Microsoft Edge renders the page as a mobile or desktop viewport.</span></span>  <span data-ttu-id="9b6c1-149">光标图标列是指在页面上悬停时显示的游标类型。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-149">The Cursor icon column refers to what type of cursor is displayed when you hover on the page.</span></span>  <span data-ttu-id="9b6c1-150">触发的事件列是指当您与页面交互时页面是否触发 `touch` `click` 或事件。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-150">The Events triggered column refers to whether the page triggers `touch` or `click` events when you interact with the page.</span></span>  

| <span data-ttu-id="9b6c1-151">选项</span><span class="sxs-lookup"><span data-stu-id="9b6c1-151">Option</span></span> | <span data-ttu-id="9b6c1-152">呈现方法</span><span class="sxs-lookup"><span data-stu-id="9b6c1-152">Rendering method</span></span> | <span data-ttu-id="9b6c1-153">光标图标</span><span class="sxs-lookup"><span data-stu-id="9b6c1-153">Cursor icon</span></span> | <span data-ttu-id="9b6c1-154">触发的事件</span><span class="sxs-lookup"><span data-stu-id="9b6c1-154">Events triggered</span></span> |  
|:--- |:--- |:--- |:--- |  
| <span data-ttu-id="9b6c1-155">移动版</span><span class="sxs-lookup"><span data-stu-id="9b6c1-155">Mobile</span></span> | <span data-ttu-id="9b6c1-156">移动版</span><span class="sxs-lookup"><span data-stu-id="9b6c1-156">Mobile</span></span> | <span data-ttu-id="9b6c1-157">圆形</span><span class="sxs-lookup"><span data-stu-id="9b6c1-157">Circle</span></span> | <span data-ttu-id="9b6c1-158">触摸</span><span class="sxs-lookup"><span data-stu-id="9b6c1-158">touch</span></span> |  
| <span data-ttu-id="9b6c1-159">移动 \ (触摸\) </span><span class="sxs-lookup"><span data-stu-id="9b6c1-159">Mobile \(no touch\)</span></span> | <span data-ttu-id="9b6c1-160">移动版</span><span class="sxs-lookup"><span data-stu-id="9b6c1-160">Mobile</span></span> | <span data-ttu-id="9b6c1-161">正常</span><span class="sxs-lookup"><span data-stu-id="9b6c1-161">Normal</span></span> | <span data-ttu-id="9b6c1-162">选择</span><span class="sxs-lookup"><span data-stu-id="9b6c1-162">choose</span></span> |  
| <span data-ttu-id="9b6c1-163">桌面</span><span class="sxs-lookup"><span data-stu-id="9b6c1-163">Desktop</span></span> | <span data-ttu-id="9b6c1-164">桌面</span><span class="sxs-lookup"><span data-stu-id="9b6c1-164">Desktop</span></span> | <span data-ttu-id="9b6c1-165">正常</span><span class="sxs-lookup"><span data-stu-id="9b6c1-165">Normal</span></span> | <span data-ttu-id="9b6c1-166">选择</span><span class="sxs-lookup"><span data-stu-id="9b6c1-166">choose</span></span> |  
| <span data-ttu-id="9b6c1-167">桌面 \ (触摸\) </span><span class="sxs-lookup"><span data-stu-id="9b6c1-167">Desktop \(touch\)</span></span> | <span data-ttu-id="9b6c1-168">桌面</span><span class="sxs-lookup"><span data-stu-id="9b6c1-168">Desktop</span></span> | <span data-ttu-id="9b6c1-169">圆形</span><span class="sxs-lookup"><span data-stu-id="9b6c1-169">Circle</span></span> | <span data-ttu-id="9b6c1-170">触摸</span><span class="sxs-lookup"><span data-stu-id="9b6c1-170">touch</span></span> |  

> [!NOTE]
> <span data-ttu-id="9b6c1-171">如果未**显示设备类型**列表，请选择"**更多选项**  >  **添加设备类型"。**</span><span class="sxs-lookup"><span data-stu-id="9b6c1-171">If the **Device Type** list is not displayed, choose **More options** > **Add device type**.</span></span>  

### <a name="mobile-device-viewport-mode"></a><span data-ttu-id="9b6c1-172">移动设备视口模式</span><span class="sxs-lookup"><span data-stu-id="9b6c1-172">Mobile Device Viewport Mode</span></span>  

<span data-ttu-id="9b6c1-173">若要模拟特定移动设备的尺寸，请从"设备"列表中选择 **该设备** 。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-173">To simulate the dimensions of a specific mobile device, select the device from the **Device** list.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list.msft.png" alt-text="设备列表" lightbox="../media/device-mode-toggle-device-toolbar-device-list.msft.png":::
   <span data-ttu-id="9b6c1-175">设备**列表**</span><span class="sxs-lookup"><span data-stu-id="9b6c1-175">The **Device** list</span></span>  
:::image-end:::  

#### <a name="rotate-the-viewport-to-landscape-orientation"></a><span data-ttu-id="9b6c1-176">将视口旋转至横向</span><span class="sxs-lookup"><span data-stu-id="9b6c1-176">Rotate the viewport to landscape orientation</span></span>  

<span data-ttu-id="9b6c1-177">在横向方向测试网页。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-177">Test your webpage in landscape orientation.</span></span>  

*   <span data-ttu-id="9b6c1-178">若要将视口旋转到横向方向，请选择 **"旋转** (旋转 ![ ][ImageRotateIcon] \) 。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-178">To rotate the viewport to landscape orientation, choose **Rotate** \(![Rotate][ImageRotateIcon]\).</span></span>  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-landscape.msft.png" alt-text="横向显示的页面" lightbox="../media/device-mode-toggle-device-toolbar-landscape.msft.png":::
       <span data-ttu-id="9b6c1-180">横向显示的页面</span><span class="sxs-lookup"><span data-stu-id="9b6c1-180">Page displayed in landscape orientation</span></span>  
    :::image-end:::  
    
> [!NOTE]
> <span data-ttu-id="9b6c1-181">如果 **设备** 工具栏较窄 **，"旋转** "按钮将消失。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-181">The **Rotate** button disappears if your **Device Toolbar** is narrow.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="设备工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   <span data-ttu-id="9b6c1-183">设备 **工具栏**</span><span class="sxs-lookup"><span data-stu-id="9b6c1-183">The **Device Toolbar**</span></span>  
:::image-end:::  

<span data-ttu-id="9b6c1-184">有关详细信息，请导航到"[设置方向"。](#set-orientation)</span><span class="sxs-lookup"><span data-stu-id="9b6c1-184">For more information, navigate to [Set orientation](#set-orientation).</span></span>  

#### <a name="show-device-frame"></a><span data-ttu-id="9b6c1-185">显示设备框架</span><span class="sxs-lookup"><span data-stu-id="9b6c1-185">Show device frame</span></span>  

<span data-ttu-id="9b6c1-186">模拟特定移动设备（如 iPhone 6）的尺寸时，在视口周围显示物理设备框架。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-186">Display the physical device frame around the viewport when you simulate the dimensions of a specific mobile device such as an iPhone 6.</span></span>  

1.  <span data-ttu-id="9b6c1-187">打开 **更多选项**。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-187">Open **More options**.</span></span>  
1.  <span data-ttu-id="9b6c1-188">选择 **"显示设备框架"。**</span><span class="sxs-lookup"><span data-stu-id="9b6c1-188">Choose **Show device frame**.</span></span>  

> [!NOTE]
> <span data-ttu-id="9b6c1-189">如果未显示特定设备的设备框架，则意味着 DevTools 没有适用于该选项的图文。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-189">If a device frame for a particular device is not displayed, it means that DevTools does not have art for the option.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png" alt-text="显示设备框架" lightbox="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png":::
         <span data-ttu-id="9b6c1-191">显示设备框架</span><span class="sxs-lookup"><span data-stu-id="9b6c1-191">Show device frame</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png" alt-text="iPhone 6 的设备框架" lightbox="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png":::
         <span data-ttu-id="9b6c1-193">iPhone 6 的设备框架</span><span class="sxs-lookup"><span data-stu-id="9b6c1-193">The device frame for the iPhone 6</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <a name="add-a-custom-mobile-device"></a><span data-ttu-id="9b6c1-194">添加自定义移动设备</span><span class="sxs-lookup"><span data-stu-id="9b6c1-194">Add a custom mobile device</span></span>  

<span data-ttu-id="9b6c1-195">如果默认列表中未包含所需的移动设备选项，可以添加自定义设备。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-195">If the mobile device option that you need is not included on the default list, you may add a custom device.</span></span>  <span data-ttu-id="9b6c1-196">若要添加自定义设备，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-196">To add a custom device, complete the following steps.</span></span>  

1.  <span data-ttu-id="9b6c1-197">选择" **编辑** > **列表**。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-197">Choose the **Device** list > **Edit**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png" alt-text="选择"编辑"" lightbox="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png":::
       <span data-ttu-id="9b6c1-199">选择 **"编辑"**</span><span class="sxs-lookup"><span data-stu-id="9b6c1-199">Choose **Edit**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9b6c1-200">选择 **"添加自定义设备"。**</span><span class="sxs-lookup"><span data-stu-id="9b6c1-200">Choose **Add custom device**.</span></span>  
1.  <span data-ttu-id="9b6c1-201">在 **模拟设备上**，输入自定义设备的设备名称、屏幕宽度和屏幕高度。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-201">On **Emulated Devices**, enter a device name, screen width, and screen height for the custom device.</span></span>  <span data-ttu-id="9b6c1-202">设备[像素比率][MDNWindowDevicePixelRatio]、[用户代理字符串][MDNUserAgent][和设备类型](#set-the-device-type)字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-202">The [device pixel ratio][MDNWindowDevicePixelRatio], [user agent string][MDNUserAgent], and [device type](#set-the-device-type) fields are optional.</span></span>  <span data-ttu-id="9b6c1-203">设备类型字段默认为**移动。**</span><span class="sxs-lookup"><span data-stu-id="9b6c1-203">The device type field defaults to **Mobile**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png" alt-text="创建自定义设备" lightbox="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png":::
       <span data-ttu-id="9b6c1-205">创建自定义设备</span><span class="sxs-lookup"><span data-stu-id="9b6c1-205">Create a custom device</span></span>  
    :::image-end:::  
    
### <a name="show-rulers"></a><span data-ttu-id="9b6c1-206">显示标尺</span><span class="sxs-lookup"><span data-stu-id="9b6c1-206">Show rulers</span></span>  

<span data-ttu-id="9b6c1-207">如果需要测量屏幕尺寸，可以使用标尺测量屏幕大小（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-207">If you need to measure screen dimensions, you may use rulers to measure the screen size in pixels.</span></span>  <span data-ttu-id="9b6c1-208">选择 **"更多**  >  **选项"显示标**尺以显示视区上方和左侧的标尺。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-208">Choose **More options** > **Show rulers** to display rulers above and to the left of your viewport.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png" alt-text="用于显示标尺的菜单项" lightbox="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png":::
         <span data-ttu-id="9b6c1-210">用于显示标尺的菜单项</span><span class="sxs-lookup"><span data-stu-id="9b6c1-210">Menu item to display rulers</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-rulers.msft.png" alt-text="视口上方和左侧的标尺" lightbox="../media/device-mode-toggle-device-toolbar-rulers.msft.png":::
         <span data-ttu-id="9b6c1-212">视口上方和左侧的标尺</span><span class="sxs-lookup"><span data-stu-id="9b6c1-212">Rulers above and to the left of the viewport</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="zoom-the-viewport"></a><span data-ttu-id="9b6c1-213">缩放视口</span><span class="sxs-lookup"><span data-stu-id="9b6c1-213">Zoom the viewport</span></span>  

<span data-ttu-id="9b6c1-214">若要在多个缩放级别测试页面的外观，请使用 **"** 缩放"列表进行放大或缩小。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-214">To test the look and feel of your page at multiple zoom levels, use the **Zoom** list to zoom in or out.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-zoom.msft.png" alt-text="Zoom" lightbox="../media/device-mode-toggle-device-toolbar-zoom.msft.png":::
   **<span data-ttu-id="9b6c1-216">Zoom</span><span class="sxs-lookup"><span data-stu-id="9b6c1-216">Zoom</span></span>**  
:::image-end:::  

## <a name="throttle-the-network-and-cpu"></a><span data-ttu-id="9b6c1-217">限制网络和 CPU</span><span class="sxs-lookup"><span data-stu-id="9b6c1-217">Throttle the network and CPU</span></span>  

<span data-ttu-id="9b6c1-218">移动设备通常具有网络和 CPU 约束。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-218">Mobile devices often have network and CPU constraints.</span></span>  <span data-ttu-id="9b6c1-219">确保测试页面加载速度以及页面如何以不同的 Internet 和 CPU 速度响应。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-219">Ensure you test how quickly your page loads and how it responds at different internet and CPU speeds.</span></span>  

<span data-ttu-id="9b6c1-220">限制网络和 CPU。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-220">Throttle the network and CPU.</span></span>  

1.  <span data-ttu-id="9b6c1-221">选择 **限制** 列表，将预设更改为 **中层移动** 或 **低端移动**。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-221">Choose **Throttle** list and change the preset to **Mid-tier mobile** or **Low-end mobile**.</span></span>  
    *   <span data-ttu-id="9b6c1-222">**中间层移动** 可模拟 `fast 3G` 并限制 CPU。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-222">**Mid-tier mobile** simulates `fast 3G` and throttles your CPU.</span></span>  <span data-ttu-id="9b6c1-223">它比正常速度慢四倍。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-223">It is four times slower than normal.</span></span>  
    *   <span data-ttu-id="9b6c1-224">**低端移动** 将模拟 `slow 3G` 并限制 CPU。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-224">**Low-end mobile** simulates `slow 3G` and throttles your CPU.</span></span>  <span data-ttu-id="9b6c1-225">它比正常速度慢六倍。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-225">It is six times slower than normal.</span></span>  
    
<span data-ttu-id="9b6c1-226">所有限制都基于笔记本电脑或台式机的正常功能。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-226">All of the throttling is based upon the normal capability of your laptop or desktop.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-throttle.msft.png" alt-text="设备工具栏中的限制列表" lightbox="../media/device-mode-toggle-device-toolbar-throttle.msft.png":::
   <span data-ttu-id="9b6c1-228">设备 **工具栏** 中的限制列表</span><span class="sxs-lookup"><span data-stu-id="9b6c1-228">The **Throttle** list in the Device Toolbar</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="9b6c1-229">如果 **"限制"列表** 处于隐藏状态， **则设备工具栏** 过窄。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-229">If the **Throttle list** is hidden, your **Device Toolbar** is too narrow.</span></span>  <span data-ttu-id="9b6c1-230">若要访问 **限制列表**，请增加设备 **工具栏的宽度**。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-230">To access the **Throttle list**, increase the width of the **Device Toolbar**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="设备工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   <span data-ttu-id="9b6c1-232">设备 **工具栏**</span><span class="sxs-lookup"><span data-stu-id="9b6c1-232">The **Device Toolbar**</span></span>  
:::image-end:::  

### <a name="throttle-the-cpu-only"></a><span data-ttu-id="9b6c1-233">仅限制 CPU</span><span class="sxs-lookup"><span data-stu-id="9b6c1-233">Throttle the CPU only</span></span>  

<span data-ttu-id="9b6c1-234">若要仅限制 CPU 而不是网络，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-234">To throttle the CPU only and not the network, complete the following steps.</span></span>

1.  <span data-ttu-id="9b6c1-235">选择 **"性能** "面板 **，然后选择"** 捕获设置" ("捕获设置 ![ ][ImageCaptureIcon] ") 。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-235">Choose the **Performance** panel, and choose **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\).</span></span>
1.  <span data-ttu-id="9b6c1-236">选择**CPU**  >  **4 倍慢或** **6 倍慢**。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-236">Choose **CPU** > **4x slowdown** or **6x slowdown**.</span></span>
    
    :::image type="complex" source="../media/device-mode-performance-cpu-throttle.msft.png" alt-text="性能面板中的 CPU 列表" lightbox="../media/device-mode-performance-cpu-throttle.msft.png":::
       <span data-ttu-id="9b6c1-238">性能**面板中的\*\*\*\*CPU**列表</span><span class="sxs-lookup"><span data-stu-id="9b6c1-238">The **CPU** list in the **Performance** panel</span></span>  
    :::image-end:::  
    
### <a name="throttle-the-network-only"></a><span data-ttu-id="9b6c1-239">仅限制网络</span><span class="sxs-lookup"><span data-stu-id="9b6c1-239">Throttle the network only</span></span>  

<span data-ttu-id="9b6c1-240">若要仅限制网络，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-240">To throttle the network only, complete the following steps.</span></span>

1.  <span data-ttu-id="9b6c1-241">选择 **"网络"** 工具。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-241">Choose the **Network** tool.</span></span>
1.  <span data-ttu-id="9b6c1-242">选择 **"**  >  **联机快速 3G"或**"**慢速 3G"。**</span><span class="sxs-lookup"><span data-stu-id="9b6c1-242">Choose **Online** > **Fast 3G** or **Slow 3G**.</span></span>
    
    :::image type="complex" source="../media/device-mode-network-throttle.msft.png" alt-text="网络面板中的限制列表" lightbox="../media/device-mode-network-throttle.msft.png":::
       <span data-ttu-id="9b6c1-244">网络 **面板** 中的限制列表</span><span class="sxs-lookup"><span data-stu-id="9b6c1-244">The **Throttle** list in the Network panel</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="9b6c1-245">或者，选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) \*\*\*\* `3G` \*\*\*\*\*\*\*\* 打开命令菜单，键入并选择"启用快速 3G 限制"或"启用慢速 3G 限制"。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-245">Or select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**, type `3G`, and choose **Enable fast 3G throttling** or **Enable slow 3G throttling**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-command-menu-throttle.msft.png" alt-text="命令菜单" lightbox="../media/device-mode-command-menu-throttle.msft.png":::
       <span data-ttu-id="9b6c1-247">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="9b6c1-247">The **Command Menu**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="9b6c1-248">您还可以从"性能"面板设置 **网络** 限制。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-248">You may also set network throttling from the **Performance** panel.</span></span>  

1.  <span data-ttu-id="9b6c1-249">Choose **Capture Settings** \ (Capture Settings ![ ][ImageCaptureIcon] \) and choose the **Network** list and change the preset to **Fast 3G** or **Slow 3G**.</span><span class="sxs-lookup"><span data-stu-id="9b6c1-249">Choose **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\) and choose the **Network** list and change the preset to **Fast 3G** or **Slow 3G**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-performance-network-throttle.msft.png" alt-text="从"性能"面板设置网络限制" lightbox="../media/device-mode-performance-network-throttle.msft.png":::
       <span data-ttu-id="9b6c1-251">从"性能"面板设置 **网络** 限制</span><span class="sxs-lookup"><span data-stu-id="9b6c1-251">Set network throttling from the **Performance** panel</span></span>  
    :::image-end:::  
    
## <a name="override-geolocation"></a><span data-ttu-id="9b6c1-252">替代地理位置</span><span class="sxs-lookup"><span data-stu-id="9b6c1-252">Override geolocation</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="9b6c1-253">如果你的页面依赖于移动设备中的地理位置信息来正确呈现，则使用地理位置替代 UI 提供不同的地理位置。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-253">If your page depends on geolocation information from a mobile device to render properly, provide different geolocations using the geolocation overriding UI.</span></span>  

      1.  <span data-ttu-id="9b6c1-254">Choose **Customize and control DevTools** \ (`...` \) > More **tools**  >  **Sensors**.</span><span class="sxs-lookup"><span data-stu-id="9b6c1-254">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="地理位置传感器" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         <span data-ttu-id="9b6c1-256">**地理位置** 传感器</span><span class="sxs-lookup"><span data-stu-id="9b6c1-256">**Sensors** for geolocation</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  <span data-ttu-id="9b6c1-257">打开“命令菜单”。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-257">Open the Command Menu.</span></span>  
          *   <span data-ttu-id="9b6c1-258">选择 `Control` + `Shift` + `P` \ (Windows、Linux\) `Command` + `Shift` + `P` 或 \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-258">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
      1. <span data-ttu-id="9b6c1-259">键入 `Sensors` ，然后选择 **"显示传感器"。**</span><span class="sxs-lookup"><span data-stu-id="9b6c1-259">Type `Sensors`, and choose **Show Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="显示地理位置传感器" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         <span data-ttu-id="9b6c1-261">**显示地理位置** 传感器</span><span class="sxs-lookup"><span data-stu-id="9b6c1-261">**Show Sensors** for geolocation</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="9b6c1-262">在 **"传感器"** 面板上，可以使用"位置"下拉菜单选择 DevTools 中包含的预设位置之\*\*\*\* 一。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-262">On the **Sensors** panel, you may select one of the preset locations included in DevTools using the **Location** drop-down menu.</span></span>  <span data-ttu-id="9b6c1-263">若要输入自定义位置，请选择"其他 **...**</span><span class="sxs-lookup"><span data-stu-id="9b6c1-263">To enter a custom location, choose **Other…**</span></span> <span data-ttu-id="9b6c1-264">并输入自定义位置的坐标。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-264">and enter the coordinates of your custom location.</span></span>  <span data-ttu-id="9b6c1-265">若要在位置信息不可用时测试页面错误状态，请选择"**位置不可用"。**</span><span class="sxs-lookup"><span data-stu-id="9b6c1-265">To test your page in an error state when location information is unavailable, choose **Location unavailable**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png" alt-text="已选择预设位置的传感器面板" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png":::
    <span data-ttu-id="9b6c1-267">**选择预设** 位置的传感器面板。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-267">**Sensors** panel with a preset location selected.</span></span>  
:::image-end:::

## <a name="set-orientation"></a><span data-ttu-id="9b6c1-268">设置方向</span><span class="sxs-lookup"><span data-stu-id="9b6c1-268">Set orientation</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="9b6c1-269">如果页面依赖于移动设备中的方向信息来正确呈现，请打开方向 UI。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-269">If your page depends on orientation information from a mobile device to render properly, open the orientation UI.</span></span>  

      1.  <span data-ttu-id="9b6c1-270">Choose **Customize and control DevTools** \ (`...` \) > More **tools**  >  **Sensors**.</span><span class="sxs-lookup"><span data-stu-id="9b6c1-270">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="方向传感器" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         <span data-ttu-id="9b6c1-272">**方向** 传感器</span><span class="sxs-lookup"><span data-stu-id="9b6c1-272">**Sensors** for orientation</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  <span data-ttu-id="9b6c1-273">打开“命令菜单”。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-273">Open the Command Menu.</span></span>  
          *   <span data-ttu-id="9b6c1-274">选择 `Control` + `Shift` + `P` \ (Windows、Linux\) `Command` + `Shift` + `P` 或 \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-274">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
      1. <span data-ttu-id="9b6c1-275">键入 `Sensors` ，然后选择 **"显示传感器"。**</span><span class="sxs-lookup"><span data-stu-id="9b6c1-275">Type `Sensors`, and choose **Show Sensors**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="显示方向传感器" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         <span data-ttu-id="9b6c1-277">**显示方向** 传感器</span><span class="sxs-lookup"><span data-stu-id="9b6c1-277">**Show Sensors** for orientation</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="9b6c1-278">在 **"传感器"** 面板上，你可以从"方向"下拉菜单中选择\*\*\*\* 预设方向。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-278">On the **Sensors** panel, you may select a preset orientation from the **Orientation** drop-down menu.</span></span>  <span data-ttu-id="9b6c1-279">若要输入你自己的方向，请选择 **"自定义方向**"，然后输入你自己的[alpha、beta][MDNDeviceOrientaitonAlpha]和[][MDNDeviceOrientaitonBeta][gamma][MDNDeviceOrientaitonGamma]值。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-279">To enter your own orientation, choose **Custom orientation**, and enter your own [alpha][MDNDeviceOrientaitonAlpha], [beta][MDNDeviceOrientaitonBeta], and [gamma][MDNDeviceOrientaitonGamma] values.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png" alt-text=""传感器"面板上的方向选项" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png":::
    <span data-ttu-id="9b6c1-281">**"** 传感器 **"面板上的方向** 选项</span><span class="sxs-lookup"><span data-stu-id="9b6c1-281">**Orientation** options on the **Sensors** panel</span></span>  
:::image-end:::  

## <a name="set-user-agent-string"></a><span data-ttu-id="9b6c1-282">设置用户代理字符串</span><span class="sxs-lookup"><span data-stu-id="9b6c1-282">Set user agent string</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="9b6c1-283">如果页面依赖于移动设备中的用户代理字符串来正确呈现，请使用"网络条件"面板提供\*\*\*\* 不同的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-283">If your page depends on the user agent string from a mobile device to render properly, use the **Network conditions** panel to provide different user agent strings.</span></span>  
      
      1.  <span data-ttu-id="9b6c1-284">Choose **Customize and control DevTools** \ (`...` \) > More **tools**  >  **Network conditions**.</span><span class="sxs-lookup"><span data-stu-id="9b6c1-284">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Network conditions**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png" alt-text=""更多工具"菜单中的网络条件条目" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png":::
         <span data-ttu-id="9b6c1-286">**"更多** 工具" **菜单中的网络条件** 条目</span><span class="sxs-lookup"><span data-stu-id="9b6c1-286">**Network conditions** entry in the **More tools** menu</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  <span data-ttu-id="9b6c1-287">打开“命令菜单”。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-287">Open the Command Menu.</span></span>  
          *   <span data-ttu-id="9b6c1-288">选择 `Control` + `Shift` + `P` \ (Windows、Linux\) `Command` + `Shift` + `P` 或 \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-288">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
      1. <span data-ttu-id="9b6c1-289">键入 `Network conditions` ，然后选择 **"显示网络条件"。**</span><span class="sxs-lookup"><span data-stu-id="9b6c1-289">Type `Network conditions`, and choose **Show Network conditions**.</span></span>  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png" alt-text="显示网络条件" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png":::
         **<span data-ttu-id="9b6c1-291">显示网络条件</span><span class="sxs-lookup"><span data-stu-id="9b6c1-291">Show Network conditions</span></span>**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="9b6c1-292">在 **用户代理旁边，** 清除" **自动选择"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-292">Next to **User agent**, clear the **Select automatically** checkbox.</span></span>  <span data-ttu-id="9b6c1-293">然后，选择 **"自定义..."，** 从预定义的用户代理字符串列表中选择。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-293">Then, choose **Custom...** to select from a list of predefined user agent strings.</span></span>  <span data-ttu-id="9b6c1-294">若要输入您自己的用户代理字符串，请在"输入自定义用户代理 **"中输入字符串**。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-294">To enter your own user agent string, enter the string in **Enter a custom user agent**.</span></span>  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png" alt-text="将用户代理字符串设置为 macOS 上的 Microsoft Edge" lightbox="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png":::
    <span data-ttu-id="9b6c1-296">将用户代理字符串设置为 macOS 上的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9b6c1-296">Set the user agent string to Microsoft Edge on macOS</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="9b6c1-297">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="9b6c1-297">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCaptureIcon]: ../media/capture-settings-icon.msft.png  
[ImageDeviceToolbarIcon]: ../media/toggle-device-toolbar-dark-icon.msft.png  
[ImageRotateIcon]: ../media/rotate-dark-icon.msft.png  

<!-- links -->  

<!--[DevToolsCommunity]: ../index.md#community "Join the DevTools community | Microsoft Docs"  -->
<span data-ttu-id="9b6c1-298">[DevToolsRemoteDebugging]： ../remote-debugging/index.md"开始远程调试 Android 设备|Microsoft Docs"</span><span class="sxs-lookup"><span data-stu-id="9b6c1-298">[DevToolsRemoteDebugging]: ../remote-debugging/index.md "Get started with remote debugging Android devices | Microsoft Docs"</span></span>  

[MDNWindowDevicePixelRatio]: https://developer.mozilla.org/docs/Web/API/Window/devicePixelRatio "Window.devicePixelRatio |MDN"  
[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "用户代理|MDN"  
[MDNDeviceOrientaitonAlpha]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/alpha "DeviceOrientationEvent.alpha |MDN"  
[MDNDeviceOrientaitonBeta]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/beta "DeviceOrientationEvent.beta |MDN"  
[MDNDeviceOrientaitonGamma]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/gamma "DeviceOrientationEvent.gamma |MDN"  

[WikiApproximation]: https://en.wikipedia.org/wiki/Order_of_approximation#First-order "近似顺序 - 一级 - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="9b6c1-305">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-305">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9b6c1-306">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-306">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="9b6c1-308">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-308">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
