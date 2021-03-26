---
description: 使用 Microsoft Edge 中的虚拟设备构建移动优先的网站。
title: 在 Microsoft Edge DevTools 中模拟移动设备
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools, 仿真, 设备, 模拟, 移动
ms.openlocfilehash: bb081ddd5f773e5e9ae6a1b83b5fcb13408df6cb
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439449"
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

# <a name="emulate-mobile-devices-in-microsoft-edge-devtools"></a>在 Microsoft Edge DevTools 中模拟移动设备  

使用“**设备仿真**”来大致了解你的页面在移动设备上的外观和响应方式。  Microsoft Edge DevTools 提供了一系列功能，可帮助你模拟移动设备。  该系列包括以下功能。  

*   [模拟移动视区](#simulate-a-mobile-viewport)  
*   [限制网络](#throttle-the-network-only)  
*   [限制 CPU](#throttle-the-cpu-only)  
*   [模拟地理位置](#override-geolocation)  
*   [设置方向](#set-orientation)  
*   [设置用户代理字符串](#set-user-agent-string)  

## <a name="limitations"></a>限制  

**设备仿真**是移动设备中的页面外观的[一级近似值][WikiApproximation]。  **设备仿真**实际上不会在移动设备上运行你的代码。  相反，你可以模拟笔记本电脑或台式机的移动用户体验。  

移动设备的某些方面从不在 DevTools 中模拟。  例如，移动 CPU 的体系结构与笔记本电脑或台式机 CPU 的体系结构不同。  如有疑问，最佳选择是在移动设备上实际运行页面。  当页面实际在移动设备上运行时，使用[远程调试] [DevToolsRemoteDebugging] 与计算机中的页面代码进行交互。  与代码交互时，可以进行查看、更改、调试、分析或全部四项操作。  你的计算机可以是笔记本或台式计算机。  

## <a name="simulate-a-mobile-viewport"></a>模拟移动视区  

选择“**切换设备仿真**”\（![切换设备工具栏](../media/toggle-device-toolbar-dark-icon.msft.png)\）或选择“**自定义和控制DevTools**”\ (`...`\)>“**设备仿真**”，以打开用于模拟移动视区的 UI。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="设备工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
    设备工具栏  
:::image-end:::  

默认情况下，设备工具栏在响应式视区模式下打开。  

### <a name="responsive-viewport-mode"></a>响应式视区模式  

若要跨多个屏幕大小快速测试页面的外观，请拖动手柄以将视区调整为所需尺寸。  还可以在“宽度”和“高度”框中输入特定值。  在下图中，宽度设置为 `626`，高度设置为 `516`。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png" alt-text="在响应式视区模式下更改视区尺寸的句柄" lightbox="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png":::
    在响应式视区模式下更改视区尺寸的句柄  
:::image-end:::  

#### <a name="show-media-queries"></a>显示媒体查询  

如果已在页面上定义了媒体查询，请通过在视区上方显示媒体查询断点，跳至视区维度，使这些媒体查询生效。  选择“**更多选项**” > “**显示媒体查询**”。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png" alt-text="显示媒体查询" lightbox="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png":::
   **显示媒体查询**  
:::image-end:::  

选择一个断点以更改视区的宽度，以便触发媒体查询。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png" alt-text="选择一个断点以更改视区的宽度" lightbox="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png":::
   选择一个断点以更改视区的宽度  
:::image-end:::  

#### <a name="set-the-device-type"></a>设置设备类型  

使用“**设备类型**”列表模拟移动设备或桌面设备。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png" alt-text="“设备类型”列表" lightbox="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png":::
   “**设备类型**”列表  
:::image-end:::  

下表介绍了可用设备类型选项之间的差异。  “渲染方法”列是指 Microsoft Edge 是将页面渲染为移动视区还是桌面视区。  “光标图标”列是指当你将鼠标悬停在页面上时所显示的光标类型。  “触发事件”列是指你与页面交互时页面是触发 `touch` 还是 `click` 事件。  

| 选项 | 渲染方法 | 光标图标 | 触发事件 |  
|:--- |:--- |:--- |:--- |  
| 移动设备 | 移动设备 | 圆形 | 触控 |  
| 移动设备\（无触控\） | 移动设备 | 正常 | 选择 |  
| 桌面 | 桌面 | 正常 | 选择 |  
| 桌面\（触控\） | 桌面 | 圆形 | 触控 |  

> [!NOTE]
> 如果未显示“**设备类型**”列表，请选择“**更多选项**” > “**添加设备类型**”。  

### <a name="mobile-device-viewport-mode"></a>移动设备视区模式  

若要模拟特定移动设备的尺寸，请从“**设备**”列表中选择该设备。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list.msft.png" alt-text="设备列表" lightbox="../media/device-mode-toggle-device-toolbar-device-list.msft.png":::
   **设备**列表  
:::image-end:::  

#### <a name="rotate-the-viewport-to-landscape-orientation"></a>将视区旋转为横向  

横向测试你的网页。  

*   若要将视区旋转为横向，请选择“**旋转**”\（![旋转](../media/rotate-dark-icon.msft.png)\）。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-landscape.msft.png" alt-text="横向显示的页面" lightbox="../media/device-mode-toggle-device-toolbar-landscape.msft.png":::
       横向显示的页面  
    :::image-end:::  
    
> [!NOTE]
> 如果“**设备**”工具栏较窄，将不显示“**旋转**”按钮。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="设备工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   **设备工具栏**  
:::image-end:::  

有关详细信息，请导航到“[设置方向](#set-orientation)”。  

#### <a name="show-device-frame"></a>显示设备框架  

模拟特定移动设备（例如 iPhone 6）的尺寸时，在视区周围显示物理设备框架。  

1.  打开“**更多选项**”。  
1.  选择“**显示设备框架**”。  

> [!NOTE]
> 如果未显示特定设备的设备框架，则表示 DevTools 没有该选项的图片。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png" alt-text="显示设备框架" lightbox="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png":::
         显示设备框架  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png" alt-text="iPhone 6 的设备框架" lightbox="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png":::
         iPhone 6 的设备框架  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <a name="add-a-custom-mobile-device"></a>添加自定义移动设备  

如果默认列表中未包含所需的移动设备选项，则可以添加自定义设备。  若要添加自定义设备，请完成以下步骤。  

1.  选择“**设备**”列表>“**编辑**”。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png" alt-text="选择“编辑”" lightbox="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png":::
       选择“**编辑**”  
    :::image-end:::  
    
1.  选择“**添加自定义设备**”。  
1.  在“**仿真设备**”上，输入自定义设备的设备名称、屏幕宽度和屏幕高度。  “[设备像素比][MDNWindowDevicePixelRatio]”、“[用户代理字符串][MDNUserAgent]”和“[设备类型](#set-the-device-type)”为可选字段。  设备类型字段默认为“**移动设备**”。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png" alt-text="创建自定义设备" lightbox="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png":::
       创建自定义设备  
    :::image-end:::  
    
### <a name="show-rulers"></a>显示标尺  

如果你需要测量屏幕尺寸，可以使用标尺测量屏幕大小（以像素为单位）。  选择“**更多选项**” > “**显示标尺**”，以在视区的上方和左侧显示标尺。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png" alt-text="用于显示标尺的菜单项" lightbox="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png":::
         用于显示标尺的菜单项  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-rulers.msft.png" alt-text="视区上方和左侧的标尺" lightbox="../media/device-mode-toggle-device-toolbar-rulers.msft.png":::
         视区上方和左侧的标尺  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="zoom-the-viewport"></a>缩放视区  

若要在多个缩放级别测试页面的外观，请使用“**缩放**”列表进行缩放。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-zoom.msft.png" alt-text="缩放" lightbox="../media/device-mode-toggle-device-toolbar-zoom.msft.png":::
   **缩放**  
:::image-end:::  

## <a name="throttle-the-network-and-cpu"></a>限制网络和 CPU  

移动设备通常具有网络和 CPU 限制。  确保测试页面加载的速度以及它在不同 Internet 和 CPU 速度下的响应速度。  

限制网络和 CPU。  

1.  选择“**限制**”列表，将预设更改为“**中层移动设备**”或“**低端移动设备**”。  
    *   “**中层移动设备**”将模拟 `fast 3G` 并限制你的 CPU。  它是正常速度的 1/4。  
    *   “**低端移动设备**”将模拟 `slow 3G` 并限制你的 CPU。  它是正常速度的 1/6。  
    
所有限制都基于笔记本电脑或桌面设备的正常功能。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-throttle.msft.png" alt-text="设备工具栏中的限制列表" lightbox="../media/device-mode-toggle-device-toolbar-throttle.msft.png":::
   设备工具栏中的“**限制**”列表  
:::image-end:::  

> [!NOTE]
> 如果 **“限制”列表**处于隐藏状态，则表示**设备工具栏**过窄。  若要访问 **“限制”列表**，请增加**设备工具栏**的宽度。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="设备工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   **设备工具栏**  
:::image-end:::  

### <a name="throttle-the-cpu-only"></a>仅限制 CPU  

若要仅限制 CPU 而不限制网络，请完成以下步骤。

1.  选择“**性能**”面板，然后选择“**捕获设置**”\（![捕获设置](../media/capture-settings-icon.msft.png)\）。
1.  选择 **CPU**  > **速度降低至 1/4**** 1/6**。
    
    :::image type="complex" source="../media/device-mode-performance-cpu-throttle.msft.png" alt-text="“性能”面板中的“CPU”列表" lightbox="../media/device-mode-performance-cpu-throttle.msft.png":::
       “**性能**”面板中的“**CPU**”列表  
    :::image-end:::  
    
### <a name="throttle-the-network-only"></a>仅限制网络  

若要仅限制网络，请完成以下步骤。

1.  选择“**网络**”工具。
1.  选择“**联机**” > “**快速 3G**”或“**慢速 3G**”。
    
    :::image type="complex" source="../media/device-mode-network-throttle.msft.png" alt-text="“网络”面板中的“限制”列表" lightbox="../media/device-mode-network-throttle.msft.png":::
       “网络”面板中的“**限制**”列表  
    :::image-end:::  
    
    或者选择`Control`+`Shift`+`P`\(Windows, Linux\) 或`Command`+`Shift`+`P` \(macOS\) 以打开**命令菜单**，键入 `3G`，然后选择**启用快速 3G 限制**或**启用慢速 3G 限制**。  
    
    :::image type="complex" source="../media/device-mode-command-menu-throttle.msft.png" alt-text="命令菜单" lightbox="../media/device-mode-command-menu-throttle.msft.png":::
       **命令菜单**  
    :::image-end:::  
    
还可以从“**性能**”面板设置网络限制。  

1.  选择“**捕获设置**”\（![捕获设置](../media/capture-settings-icon.msft.png)\），然后选择“**网络**”列表，并将预设更改为“**快速 3G**”或“**慢速 3G**”。  
    
    :::image type="complex" source="../media/device-mode-performance-network-throttle.msft.png" alt-text="从“性能”面板设置网络限制" lightbox="../media/device-mode-performance-network-throttle.msft.png":::
       从“**性能**”面板设置网络限制  
    :::image-end:::  
    
## <a name="override-geolocation"></a>替代地理位置  

:::row:::
   :::column span="":::
      如果页面依赖来自移动设备的地理位置信息来正确呈现，请使用替代地理位置的 UI 来提供不同的地理位置。  

      1.  选择“**自定义和控制 DevTools**”\(`...`\) >“**更多工具**” > “**传感器**”。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="地理位置传感器" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         地理位置**传感器**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  打开命令菜单。  
          *   选择 `Control`+`Shift`+`P` \(Windows, Linux\) 或 `Command`+`Shift`+`P` \(macOS\)。  
      1. 键入 `Sensors`，然后选择“**显示传感器**”。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="针对地理位置显示传感器" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         针对地理位置**显示传感器**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

在“**传感器**”面板上，可以使用“**位置**”下拉菜单选择 DevTools 中包含的预设位置之一。  若要输入自定义位置，请选择“**其他...**”， 然后输入自定义位置的坐标。  若要在位置信息不可用时在错误状态下测试页面，请选择“**位置不可用**”。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png" alt-text="已选择预设位置的“传感器”面板" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png":::
    已选择预设位置的“**传感器**”面板。  
:::image-end:::

## <a name="set-orientation"></a>设置方向  

:::row:::
   :::column span="":::
      如果页面依赖来自移动设备的方向信息来正确呈现，请打开方向 UI。  

      1.  选择“**自定义和控制 DevTools**”\(`...`\) >“**更多工具**” > “**传感器**”。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="方向传感器" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         方向**传感器**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  打开命令菜单。  
          *   选择 `Control`+`Shift`+`P` \(Windows, Linux\) 或 `Command`+`Shift`+`P` \(macOS\)。  
      1. 键入 `Sensors`，然后选择“**显示传感器**”。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="针对方向显示传感器" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         针对方向**显示传感器**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

在“**传感器**”面板上，可以从“**方向**”下拉菜单中选择预设方向。  若要输入自己的方向，请选择“**自定义方向**”，然后输入自己的 [alpha][MDNDeviceOrientaitonAlpha]、 [beta][MDNDeviceOrientaitonBeta]和 [gamma][MDNDeviceOrientaitonGamma] 值。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png" alt-text="“传感器”面板上的方向选项" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png":::
    “**传感器**”面板上的**方向**选项  
:::image-end:::  

## <a name="set-user-agent-string"></a>设置用户代理字符串  

:::row:::
   :::column span="":::
      如果页面依赖移动设备中的用户代理字符串来正确呈现，请使用“**网络条件**”面板提供不同的用户代理字符串。  
      
      1.  选择“**自定义和控制 DevTools**”\(`...`\) >“**更多工具**” > “**网络条件**”。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png" alt-text="“更多工具”菜单中的“网络条件”条目" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png":::
         “**更多工具**”菜单中的“**网络条件**”条目  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  打开命令菜单。  
          *   选择 `Control`+`Shift`+`P` \(Windows, Linux\) 或 `Command`+`Shift`+`P` \(macOS\)。  
      1. 键入 `Network conditions`，然后选择“**显示网络条件**”。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png" alt-text="显示网络条件" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png":::
         **显示网络条件**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

在“**用户代理**”旁边，清除“**自动选择**”复选框。  然后，选择“**自定义...**”，以从预定义的用户代理字符串列表中进行选择。  若要输入你自己的用户代理字符串，请在“**输入自定义用户代理**”中输入字符串。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png" alt-text="在 macOS 上，将用户代理字符串设置为 Microsoft Edge" lightbox="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png":::
    在 macOS 上，将用户代理字符串设置为 Microsoft Edge  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[DevToolsCommunity]: ../index.md#community "Join the DevTools community | Microsoft Docs"  -->
[DevToolsRemoteDebugging]: ../remote-debugging/index.md "Android 设备远程调试入门 | Microsoft Docs"  

[MDNWindowDevicePixelRatio]: https://developer.mozilla.org/docs/Web/API/Window/devicePixelRatio "Window.devicePixelRatio | MDN"  
[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "用户代理 | MDN"  
[MDNDeviceOrientaitonAlpha]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/alpha "DeviceOrientationEvent.alpha | MDN"  
[MDNDeviceOrientaitonBeta]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/beta "DeviceOrientationEvent.beta | MDN"  
[MDNDeviceOrientaitonGamma]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/gamma "DeviceOrientationEvent.gamma | MDN"  

[WikiApproximation]: https://en.wikipedia.org/wiki/Order_of_approximation#First-order "近似顺序 - 一级 - 维基百科"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
