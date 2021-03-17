---
description: 使用 Microsoft Edge 中的虚拟设备构建移动第一网站。
title: 在 Microsoft Edge DevTools 中模拟移动设备
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 模拟， 设备， 模拟， 移动
ms.openlocfilehash: bb081ddd5f773e5e9ae6a1b83b5fcb13408df6cb
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
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

使用 **设备模拟** 来大致了解你的页面在移动设备上的外观和响应方式。  Microsoft Edge DevTools 提供了一组功能，可帮助你模拟移动设备。  该集合包括以下功能。  

*   [模拟移动视口](#simulate-a-mobile-viewport)  
*   [限制网络](#throttle-the-network-only)  
*   [限制 CPU](#throttle-the-cpu-only)  
*   [模拟地理位置](#override-geolocation)  
*   [设置方向](#set-orientation)  
*   [设置用户代理字符串](#set-user-agent-string)  

## <a name="limitations"></a>限制  

**设备模拟** 是 [移动设备中][WikiApproximation] 页面外观的一级近似值。  **设备模拟** 实际上不会在移动设备上运行你的代码。  相反，你可以模拟笔记本电脑或台式机的移动用户体验。  

移动设备的某些方面从不在 DevTools 中模拟。  例如，移动 CPU 的体系结构与笔记本电脑或台式机 CPU 的体系结构不同。  如果有疑问，最佳匹配是在移动设备上实际运行页面。  使用 [Remote Debugging][DevToolsRemoteDebugging] 与计算机中的页面代码交互，而页面实际上在移动设备上运行时。  与代码交互时，可以查看、更改、调试、配置文件或全部四者。  你的计算机可能是笔记本或台式计算机。  

## <a name="simulate-a-mobile-viewport"></a>模拟移动视口  

选择"切换设备仿真**\ (** 切换设备工具栏 \) "或选择"自定义和控制 ![ ](../media/toggle-device-toolbar-dark-icon.msft.png) **DevTools** \ (\) > 设备仿真"以打开使您能够模拟移动视口的 `...` UI。 ****  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="设备工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
    设备工具栏  
:::image-end:::  

默认情况下，设备工具栏在响应式视口模式下打开。  

### <a name="responsive-viewport-mode"></a>响应式视口模式  

若要跨多个屏幕大小快速测试页面的外观，请拖动手柄以将视口调整为所需尺寸。  还可以在宽度和高度框中输入特定值。  在下图中，宽度设置为 ，高度 `626` 设置为 `516` 。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png" alt-text="在响应式视口模式下更改视口尺寸的句柄" lightbox="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png":::
    在响应式视口模式下更改视口尺寸的句柄  
:::image-end:::  

#### <a name="show-media-queries"></a>显示媒体查询  

如果已定义页面上的媒体查询，请跳转到视口维度，这些媒体查询通过显示视口上方的媒体查询断点来生效。  选择 **"更多选项**  >  **""显示媒体查询"。**  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png" alt-text="显示媒体查询" lightbox="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png":::
   **显示媒体查询**  
:::image-end:::  

选择一个断点以更改视口的宽度，以便触发媒体查询。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png" alt-text="选择一个断点以更改视口的宽度" lightbox="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png":::
   选择一个断点以更改视口的宽度  
:::image-end:::  

#### <a name="set-the-device-type"></a>设置设备类型  

使用 **"设备类型** "列表模拟移动设备或桌面设备。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png" alt-text="设备类型列表" lightbox="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png":::
   设备 **类型** 列表  
:::image-end:::  

下表介绍了可用设备类型选项之间的差异。  Rendering 方法列是指 Microsoft Edge 是将页面呈现为移动视图还是桌面视口。  "光标"图标列是指当您将鼠标悬停在页面上时显示的光标类型。  "事件触发"列是指页面是否在与页面交互时 `touch` `click` 触发或事件。  

| 选项 | 呈现方法 | 光标图标 | 触发的事件 |  
|:--- |:--- |:--- |:--- |  
| 移动版 | 移动版 | 圆形 | 触摸 |  
| 移动 \ (触摸\)  | 移动版 | 正常 | 选择 |  
| 桌面 | 桌面 | 正常 | 选择 |  
| 桌面 \ (触摸\)  | 桌面 | 圆形 | 触摸 |  

> [!NOTE]
> 如果未显示**设备类型**列表，请选择"更多选项 **""**  >  **添加设备类型"。**  

### <a name="mobile-device-viewport-mode"></a>移动设备视口模式  

若要模拟特定移动设备的尺寸，请从"设备"列表中选择 **该设备** 。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list.msft.png" alt-text="设备列表" lightbox="../media/device-mode-toggle-device-toolbar-device-list.msft.png":::
   设备**列表**  
:::image-end:::  

#### <a name="rotate-the-viewport-to-landscape-orientation"></a>将视口旋转到横向  

以横向方向测试网页。  

*   若要将视口旋转到横向， **请选择"旋转** \ (旋转 ![ ](../media/rotate-dark-icon.msft.png) \) "。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-landscape.msft.png" alt-text="横向显示的页面" lightbox="../media/device-mode-toggle-device-toolbar-landscape.msft.png":::
       横向显示的页面  
    :::image-end:::  
    
> [!NOTE]
> 如果 **设备** 工具栏较窄，"旋转 **"** 按钮将消失。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="设备工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   设备 **工具栏**  
:::image-end:::  

有关详细信息，请导航到"设置[方向"。](#set-orientation)  

#### <a name="show-device-frame"></a>显示设备帧  

模拟特定移动设备（如 iPhone 6）的尺寸时，在视口周围显示物理设备框架。  

1.  打开 **"更多选项"。**  
1.  选择 **"显示设备帧"。**  

> [!NOTE]
> 如果未显示特定设备的设备框架，则意味着 DevTools 没有选项的艺术项。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png" alt-text="显示设备帧" lightbox="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png":::
         显示设备帧  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png" alt-text="iPhone 6 的设备框架" lightbox="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png":::
         iPhone 6 的设备框架  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <a name="add-a-custom-mobile-device"></a>添加自定义移动设备  

如果默认列表中未包含所需的移动设备选项，可以添加自定义设备。  若要添加自定义设备，请完成以下步骤。  

1.  Choose the **Device** list > **Edit**.  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png" alt-text="选择"编辑"" lightbox="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png":::
       选择 **"编辑"**  
    :::image-end:::  
    
1.  选择 **"添加自定义设备"。**  
1.  在 **"模拟设备"** 上，输入自定义设备的设备名称、屏幕宽度和屏幕高度。  设备[像素比率][MDNWindowDevicePixelRatio]、[用户代理字符串][MDNUserAgent][和设备类型](#set-the-device-type)字段是可选的。  设备类型字段默认为 **移动**。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png" alt-text="创建自定义设备" lightbox="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png":::
       创建自定义设备  
    :::image-end:::  
    
### <a name="show-rulers"></a>显示标尺  

如果你需要测量屏幕尺寸，可以使用标尺测量屏幕大小（以像素为单位）。  选择 **"更多**  >  **选项" 显示标尺**以显示视口上方和左侧的标尺。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png" alt-text="用于显示标尺的菜单项" lightbox="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png":::
         用于显示标尺的菜单项  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-rulers.msft.png" alt-text="视口上方和左侧的标尺" lightbox="../media/device-mode-toggle-device-toolbar-rulers.msft.png":::
         视口上方和左侧的标尺  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="zoom-the-viewport"></a>缩放视区  

若要在多个缩放级别测试页面的外观，请使用 **"** 缩放"列表进行放大或缩小。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-zoom.msft.png" alt-text="Zoom" lightbox="../media/device-mode-toggle-device-toolbar-zoom.msft.png":::
   **Zoom**  
:::image-end:::  

## <a name="throttle-the-network-and-cpu"></a>限制网络和 CPU  

移动设备通常具有网络和 CPU 限制。  确保测试页面加载的速度以及页面如何以不同的 Internet 和 CPU 速度响应。  

限制网络和 CPU。  

1.  选择 **限制** 列表，将预设更改为 **中层移动** 或 **低端移动**。  
    *   **中间层移动** 模拟 `fast 3G` 并限制 CPU。  它比正常速度慢四倍。  
    *   **低端移动** 将模拟 `slow 3G` 并限制 CPU。  它比正常速度慢六倍。  
    
所有限制都基于笔记本电脑或台式机的正常功能。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-throttle.msft.png" alt-text="设备工具栏中的限制列表" lightbox="../media/device-mode-toggle-device-toolbar-throttle.msft.png":::
   设备 **工具栏** 中的限制列表  
:::image-end:::  

> [!NOTE]
> 如果" **限制"** 列表处于隐藏状态，则 **设备工具栏** 过窄。  若要访问 **限制列表，** 请增加设备 **工具栏的宽度**。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="设备工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   设备 **工具栏**  
:::image-end:::  

### <a name="throttle-the-cpu-only"></a>仅限制 CPU  

若要仅限制 CPU 而不是网络，请完成以下步骤。

1.  选择性能 **面板** ， **然后选择捕获设置** \ (![ 捕获设置 ](../media/capture-settings-icon.msft.png) \) 。
1.  选择**CPU**  >  **速度减慢 4 倍或****速度减慢 6 倍**。
    
    :::image type="complex" source="../media/device-mode-performance-cpu-throttle.msft.png" alt-text=""性能"面板中的 CPU 列表" lightbox="../media/device-mode-performance-cpu-throttle.msft.png":::
       " **性能** "面板中的 **CPU** 列表  
    :::image-end:::  
    
### <a name="throttle-the-network-only"></a>仅限制网络  

若要仅限制网络，请完成以下步骤。

1.  选择" **网络"** 工具。
1.  选择 **"联机**  >  **快速 3G"** 或"**慢速 3G"。**
    
    :::image type="complex" source="../media/device-mode-network-throttle.msft.png" alt-text="网络面板中的限制列表" lightbox="../media/device-mode-network-throttle.msft.png":::
       网络 **面板** 中的限制列表  
    :::image-end:::  
    
    或者选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) **** `3G` ******** 打开"命令菜单"，键入 ，然后选择"启用快速 3G 限制"或"启用慢速 3G 限制"。  
    
    :::image type="complex" source="../media/device-mode-command-menu-throttle.msft.png" alt-text="命令菜单" lightbox="../media/device-mode-command-menu-throttle.msft.png":::
       **命令菜单**  
    :::image-end:::  
    
您还可以从"性能"面板设置 **网络** 限制。  

1.  Choose **Capture Settings** \ (Capture Settings ![ ](../media/capture-settings-icon.msft.png) \) and choose the **Network** list and change the preset to **Fast 3G** or **Slow 3G**.  
    
    :::image type="complex" source="../media/device-mode-performance-network-throttle.msft.png" alt-text="从"性能"面板设置网络限制" lightbox="../media/device-mode-performance-network-throttle.msft.png":::
       从"性能"面板设置 **网络** 限制  
    :::image-end:::  
    
## <a name="override-geolocation"></a>替代地理位置  

:::row:::
   :::column span="":::
      如果页面依赖移动设备中的地理位置信息正确呈现，则使用地理位置覆盖 UI 提供不同的地理位置。  

      1.  Choose **Customize and control DevTools** \ (`...` \) > More **tools**  >  **Sensors**.  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="用于地理位置的传感器" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         **用于** 地理位置的传感器  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  打开“命令菜单”。  
          *   选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 。  
      1. 键入 `Sensors` ，然后选择"**显示传感器"。**  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="显示用于地理位置的传感器" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         **显示用于** 地理位置的传感器  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

在 **"传感器"** 面板上，可以使用"位置"下拉菜单选择 DevTools 中包含的预设位置之**** 一。  若要输入自定义位置，请选择"其他 **..."。** 并输入自定义位置的坐标。  若要在位置信息不可用时测试页面的错误状态，请选择"**位置不可用"。**  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png" alt-text="已选择预设位置的传感器面板" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png":::
    **已选择** 预设位置的传感器面板。  
:::image-end:::

## <a name="set-orientation"></a>设置方向  

:::row:::
   :::column span="":::
      如果页面依赖移动设备的方向信息正确呈现，请打开方向 UI。  

      1.  Choose **Customize and control DevTools** \ (`...` \) > More **tools**  >  **Sensors**.  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="方向传感器" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         **方向** 传感器  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  打开“命令菜单”。  
          *   选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 。  
      1. 键入 `Sensors` ，然后选择"**显示传感器"。**  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="显示方向传感器" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         **显示方向** 传感器  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

在 **"传感器"** 面板上，你可以从"方向"下拉菜单 **中选择** 预设方向。  若要输入你自己的方向，请选择"**自定义方向**"，然后输入你自己的[alpha、beta][MDNDeviceOrientaitonAlpha]和[][MDNDeviceOrientaitonBeta][gamma][MDNDeviceOrientaitonGamma]值。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png" alt-text="传感器面板上的方向选项" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png":::
    **传感器** 面板 **上的方向** 选项  
:::image-end:::  

## <a name="set-user-agent-string"></a>设置用户代理字符串  

:::row:::
   :::column span="":::
      如果页面依赖移动设备中的用户代理字符串正确呈现，请使用"网络条件"面板提供不同的**** 用户代理字符串。  
      
      1.  Choose **Customize and control DevTools** \ (`...` \) > More **tools**  >  **Network conditions**.  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png" alt-text=""更多工具"菜单中的网络条件条目" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png":::
         **"更多** 工具"菜单中 **的网络条件** 条目  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  打开“命令菜单”。  
          *   选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 。  
      1. 键入 `Network conditions` ，然后选择"**显示网络条件"。**  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png" alt-text="显示网络条件" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png":::
         **显示网络条件**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

在" **用户代理"旁边**，清除" **自动选择"** 复选框。  然后，选择 **"自定义..."，** 从预定义的用户代理字符串列表中选择。  若要输入您自己的用户代理字符串，请在"输入自定义用户 **代理"中输入字符串**。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png" alt-text="将用户代理字符串设置为 macOS 上的 Microsoft Edge" lightbox="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png":::
    将用户代理字符串设置为 macOS 上的 Microsoft Edge  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[DevToolsCommunity]: ../index.md#community "Join the DevTools community | Microsoft Docs"  -->
[DevToolsRemoteDebugging]： ../remote-debugging/index.md "开始远程调试 Android |Microsoft Docs"  

[MDNWindowDevicePixelRatio]: https://developer.mozilla.org/docs/Web/API/Window/devicePixelRatio "Window.devicePixelRatio |MDN"  
[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "用户代理|MDN"  
[MDNDeviceOrientaitonAlpha]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/alpha "DeviceOrientationEvent.alpha |MDN"  
[MDNDeviceOrientaitonBeta]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/beta "DeviceOrientationEvent.beta |MDN"  
[MDNDeviceOrientaitonGamma]: https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/gamma "DeviceOrientationEvent.gamma |MDN"  

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
