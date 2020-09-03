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





# 在 Microsoft Edge DevTools 中通过设备模式模拟移动设备   

  

使用 "设备" 模式来大致了解页面在移动设备上的外观和执行方式。  

设备模式是 Microsoft Edge DevTools 中的松散功能集的名称，可帮助你模拟移动设备。  这些功能包括：  

*   [模拟移动视区](#simulate-a-mobile-viewport)  
*   [限制网络](#throttle-the-network-only)  
*   [调节 CPU](#throttle-the-cpu-only)  
*   [模拟地理位置](#override-geolocation)  
*   [设置方向](#set-orientation)  

## 限制   

将设备模式视为对移动设备上的页面外观和感觉的 [第一顺序近似值][WikiApproximation] 。  使用设备模式时，实际上并不是在移动设备上运行代码。  您可以从便携式计算机或桌面模拟移动用户体验。  

移动设备的某些方面 DevTools 将永远无法模拟。  例如，移动 Cpu 的体系结构与便携式计算机或桌面 Cpu 的体系结构非常不同。  如果有疑问，最佳做法是在移动设备上实际运行您的页面。  使用 [远程调试] [DevToolsRemoteDebugging] 查看、更改、调试和分析来自便携式计算机或桌面的页面的代码，同时它实际上在移动设备上运行。  

## 模拟移动视区   

单击 " **切换设备工具栏** \ (![ 切换设备工具栏 ][ImageDeviceToolbarIcon] \ ) " 以打开可让你模拟移动视区的 UI。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text=""设备" 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   "设备" 工具栏  
:::image-end:::  

默认情况下，设备工具栏将在 "响应式" 视区模式下打开。  

### 响应式视区模式   

拖动图柄以将视区大小调整为所需的任何尺寸。  或者，在 "宽度" 和 "高度" 框中输入特定值。  在下图中，宽度设置为 `626` ，高度设置为 `516` 。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png" alt-text="在 "响应" 视口模式下更改视区尺寸的控制滑块" lightbox="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png":::
   在 "响应" 视口模式下更改视区尺寸的控制滑块  
:::image-end:::  

#### 显示媒体查询   

若要在视区上方显示媒体查询断点，请单击 " **更多选项** "，然后选择 " **显示媒体查询**"。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png" alt-text="显示媒体查询" lightbox="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png":::
   **显示媒体查询**  
:::image-end:::  

单击断点以更改视区的宽度，以便触发断点。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png" alt-text="单击断点以更改视区的宽度" lightbox="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png":::
   单击断点以更改视区的宽度  
:::image-end:::  

#### 设置设备类型   

使用 **设备类型** 列表来模拟移动设备或桌面设备。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png" alt-text="设备类型列表" lightbox="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png":::
   **设备类型**列表  
:::image-end:::  

下表描述了选项之间的差异。  **呈现方法** 是指 Microsoft Edge 是否将页面呈现为移动设备或桌面视区。  **光标图标** 指将鼠标悬停在页面上时看到的光标类型。  **激发的事件** 是指 `touch` `click` 当您与页面交互时页面是引发还是事件。  

| 选项 | 呈现方法 | 光标图标 | 激发的事件 |  
|:--- |:--- |:--- |:--- |  
| 移动版 | 移动版 | 圆形 | 触摸 |  
| 移动 \ (无接触 \ )  | 移动版 | 正常 | 单击 |  
| 桌面 | 桌面 | 正常 | 单击 |  
| 桌面 (触控 \ )  | 桌面 | 圆形 | 触摸 |  

> [!NOTE]
> 如果看不到 " **设备类型** " 列表，请单击 " **更多选项** "，然后选择 " **添加设备类型**"。  

### 移动设备视区模式   

若要模拟特定移动设备的尺寸，请从 **设备** 列表中选择该设备。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list.msft.png" alt-text="设备列表" lightbox="../media/device-mode-toggle-device-toolbar-device-list.msft.png":::
   **设备**列表  
:::image-end:::  

#### 将视区旋转到横向方向   

单击 " **旋转** \ (![ 旋转 ][ImageRotateIcon] \ ) "，将视区旋转到横向方向。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-landscape.msft.png" alt-text="横向方向" lightbox="../media/device-mode-toggle-device-toolbar-landscape.msft.png":::
   横向方向  
:::image-end:::  

> [!NOTE]
> 如果**设备工具栏**较窄，"**旋转**" 按钮将消失。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text=""设备" 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   " **设备" 工具栏**  
:::image-end:::  

另请参阅 [设置方向](#set-orientation)。  

#### 显示设备帧   

模拟一个特定移动设备（如 iPhone 6）的尺寸时，打开 " **更多选项** "，然后选择 " **显示设备帧** " 以显示视区周围的物理设备帧。  

> [!NOTE]
> 如果您没有看到特定设备的设备框架，则可能意味着 DevTools 只对该特定选项没有艺术。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png" alt-text="显示设备帧" lightbox="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png":::
         显示设备帧  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png" alt-text="IPhone 6 的设备帧" lightbox="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png":::
         IPhone 6 的设备帧  
      :::image-end:::  
   :::column-end:::
:::row-end:::

#### 添加自定义移动设备   

要添加自定义设备，请执行以下操作：  

1.  单击 " **设备** " 列表，然后选择 " **编辑**"。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png" alt-text="选择 "编辑"" lightbox="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png":::
       选择 "**编辑**"  
    :::image-end:::  
    
1.  单击 " **添加自定义设备**"。  
1.  输入设备的名称、宽度和高度。  [设备像素比率][MDNWindowDevicePixelRatio]、[用户代理字符串][MDNUserAgent]和[设备类型](#set-the-device-type)字段是可选的。  "设备类型" 字段是默认情况下设置为 " **移动电话** " 的列表。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png" alt-text="创建自定义设备" lightbox="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png":::
       Createa 自定义设备  
    :::image-end:::  

### 显示标尺   

单击 " **更多选项** "，然后选择 " **显示标尺** " 以查看视区左侧和左侧的标尺。  标尺的调整单位为像素。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png" alt-text="显示标尺" lightbox="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png":::
         **显示标尺**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-rulers.msft.png" alt-text="视区左侧和左侧的标尺" lightbox="../media/device-mode-toggle-device-toolbar-rulers.msft.png":::
         视区左侧和左侧的标尺  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### 缩放视区   

使用 " **缩放** " 列表放大或缩小。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-zoom.msft.png" alt-text="缩放" lightbox="../media/device-mode-toggle-device-toolbar-zoom.msft.png":::
   **缩放**  
:::image-end:::  

## 限制网络和 CPU   

要限制网络和 CPU，请从 "**限制**" 列表中选择 "**中层移动**" 或 "**低端移动**"。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-throttle.msft.png" alt-text="限制列表" lightbox="../media/device-mode-toggle-device-toolbar-throttle.msft.png":::
   **限制**列表  
:::image-end:::  

中层**移动**模拟快速3g 并限制 CPU，使其比平时慢4倍。  **低端移动** 模拟低速3g，使 CPU 比平时慢6倍。  请记住，带宽限制相对于便携式计算机或桌面机的正常功能。  

> [!NOTE]
> 如果您的**设备工具栏**很窄，"**限制**" 列表将被隐藏。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text=""设备" 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   " **设备" 工具栏**  
:::image-end:::  

### 仅调节 CPU   

若要仅限制 CPU 而不是网络，请转到 "**性能**" 面板，单击 "**捕获设置**\ (![ 捕获设置 ][ImageCaptureIcon] \ ) "，然后从**CPU**列表中选择**4x 减速**或**6x 减速**。  

:::image type="complex" source="../media/device-mode-performance-cpu-throttle.msft.png" alt-text="CPU 列表" lightbox="../media/device-mode-performance-cpu-throttle.msft.png":::
   **CPU**列表  
:::image-end:::  

### 仅限制网络   

若要仅限制网络而不是 CPU，请转到 "**网络**" 面板，然后从 "**限制**" 列表中选择 "**快速 3G** " 或 "**慢速 3g** "。  

:::image type="complex" source="../media/device-mode-network-throttle.msft.png" alt-text="限制列表" lightbox="../media/device-mode-network-throttle.msft.png":::
   **限制**列表  
:::image-end:::  

或者按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "**命令" 菜单**，键入 `3G` ，然后选择 "**启用快速3g 限制**" 或 "**启用慢速3g 限制**"。  

:::image type="complex" source="../media/device-mode-command-menu-throttle.msft.png" alt-text="命令菜单" lightbox="../media/device-mode-command-menu-throttle.msft.png":::
   **命令菜单**  
:::image-end:::  

您也可以从 " **性能** " 面板中设置网络限制。  单击 "**捕获设置**\ ![ (捕获设置 ][ImageCaptureIcon] \ ) 然后从"**网络**"列表中选择"**快速 3g** "或"**慢速 3g** "。  

:::image type="complex" source="../media/device-mode-performance-network-throttle.msft.png" alt-text="从性能面板设置网络限制" lightbox="../media/device-mode-performance-network-throttle.msft.png":::
   从 **性能** 面板设置网络限制  
:::image-end:::  

## 替代地理位置   

若要打开地理位置替代的 UI，请单击 "**自定义" 并控制 DevTools** \ (`...` \ ) 然后选择 "**更多工具**  >  **传感器**"。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="传感器" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
   **传感器**  
:::image-end:::  

或者按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "命令" 菜单，键入 `Sensors` ，然后选择 "**显示传感器**"。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="显示传感器" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
   **显示传感器**  
:::image-end:::  

从 " **地理** 位置" 列表中选择其中一个预设，或选择 " **自定义位置** " 以输入您自己的坐标，或选择 " **位置不可用** " 以测试当地理位置处于错误状态时页面的行为。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png" alt-text="地理位置" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png":::
   **地理位置**  
:::image-end:::  

## 设置方向   

:::row:::
   :::column span="":::
      若要打开方向用户界面，请单击 "**自定义和控制 DevTools** " `...` ，然后选择 "**更多工具**  >  **传感器**"。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="传感器" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         **传感器**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      或者按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "命令" 菜单，键入 `Sensors` ，然后选择 "**显示传感器**"。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="显示传感器" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         **显示传感器**  
      :::image-end:::  
   :::column-end:::
:::row-end:::

从 " **方向** " 列表中选择其中一个预设，或选择 " **自定义方向** " 以设置您自己的 alpha、beta 和伽玛值。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png" alt-text="Orientation" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png":::
   **Orientation**  
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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
