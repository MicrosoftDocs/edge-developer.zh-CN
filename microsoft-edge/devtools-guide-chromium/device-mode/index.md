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





# 在 Microsoft Edge DevTools 中通过设备模式模拟移动设备   

  

使用 "设备" 模式来大致了解页面在移动设备上的外观和执行方式。  

设备模式是 Microsoft Edge DevTools 中的松散功能集的名称，可帮助你模拟移动设备。  这些功能包括：  

*   [模拟移动视区](#simulate-a-mobile-viewport)  
*   [限制网络](#throttle-the-network-only)  
*   [调节 CPU](#throttle-the-cpu-only)  
*   [模拟地理位置](#override-geolocation)  
*   [设置方向](#set-orientation)  

## 限制   

将设备模式视为对移动设备上的页面外观和感觉的[第一顺序近似值][WikiApproximation]。  使用设备模式时，实际上并不是在移动设备上运行代码。  您可以从便携式计算机或桌面模拟移动用户体验。  

移动设备的某些方面 DevTools 将永远无法模拟。  例如，移动 Cpu 的体系结构与便携式计算机或桌面 Cpu 的体系结构非常不同。  如果有疑问，最佳做法是在移动设备上实际运行您的页面。  使用 [远程调试] [DevToolsRemoteDebugging] 查看、更改、调试和分析来自便携式计算机或桌面的页面的代码，同时它实际上在移动设备上运行。  

## 模拟移动视区   

单击 "**切换设备" 工具栏**上 ![ 的 "切换设备" 工具栏 ][ImageDeviceToolbarIcon] 以打开可让你模拟移动视区的 UI。  

> ##### 图 1  
> "设备" 工具栏  
> !["设备" 工具栏][ImageDeviceToolbar]  

默认情况下，设备工具栏将在 "响应式" 视区模式下打开。  

### 响应式视区模式   

拖动图柄以将视区大小调整为所需的任何尺寸。  或者，在 "宽度" 和 "高度" 框中输入特定值。  在[图 2](#figure-2)中，width 设置为 `626` ，高度设置为 `516` 。  

> ##### 图 2  
> 在 "响应" 视口模式下更改视区尺寸的控制滑块  
> ![在 "响应" 视口模式下更改视区尺寸的控制滑块][ImageResponsiveHandles]  

#### 显示媒体查询   

若要在视区上方显示媒体查询断点，请单击 "**更多选项**"，然后选择 "**显示媒体查询**"。  

> ##### 图 3  
> 显示媒体查询  
> ![显示媒体查询][ImageShowMediaQueries]  

单击断点以更改视区的宽度，以便触发断点。  

> ##### 图 4  
> 单击断点以更改视区的宽度  
> ![单击断点以更改视区的宽度][ImageBreakpoint]  

#### 设置设备类型   

使用**设备类型**列表来模拟移动设备或桌面设备。  

> ##### 图 5  
> **设备类型**列表  
> ![设备类型列表][ImageDeviceType]  

下表描述了选项之间的差异。  **呈现方法**是指 Microsoft Edge 是否将页面呈现为移动设备或桌面视区。  **光标图标**指将鼠标悬停在页面上时看到的光标类型。  **激发的事件**是指 `touch` `click` 当您与页面交互时页面是引发还是事件。  

| 选项 | 呈现方法 | 光标图标 | 激发的事件 |  
|:--- |:--- |:--- |:--- |  
| 移动版 | 移动版 | 圆形 | 触摸 |  
| 移动 \ （无接触 \） | 移动版 | 正常 | 单击 |  
| 桌面 | 桌面 | 正常 | 单击 |  
| 桌面版 \ （触摸 \） | 桌面 | 圆形 | 触摸 |  

> [!NOTE]
> 如果看不到 "**设备类型**" 列表，请单击 "**更多选项**"，然后选择 "**添加设备类型**"。  

### 移动设备视区模式   

若要模拟特定移动设备的尺寸，请从**设备**列表中选择该设备。  

> ##### 图 6  
> 设备列表  
> ![设备列表][ImageDeviceList]  

#### 将视区旋转到横向方向   

单击 "**旋转** ![ 旋转 ][ImageRotateIcon] "，将视区旋转到横向方向。  

> ##### 图 7  
> 横向方向  
> ![横向方向][ImageLandscape]  

> [!NOTE]
> 如果**设备工具栏**较窄，"**旋转**" 按钮将消失。  

> ##### 图 8  
> "设备" 工具栏  
> !["设备" 工具栏][ImageDeviceToolbar2]  

另请参阅[设置方向](#set-orientation)。  

#### 显示设备帧   

模拟一个特定移动设备（如 iPhone 6）的尺寸时，打开 "**更多选项**"，然后选择 "**显示设备帧**" 以显示视区周围的物理设备帧。  

> [!NOTE]
> 如果您没有看到特定设备的设备框架，则可能意味着 DevTools 只对该特定选项没有艺术。  

> ##### 图 9  
> 显示设备帧  
> ![显示设备帧][ImageShowDeviceFrame]  

> ##### 图 10  
> IPhone 6 的设备帧  
> ![IPhone 6 的设备帧][ImageIphoneFrame]  

#### 添加自定义移动设备   

要添加自定义设备，请执行以下操作：  

1.  单击 "**设备**" 列表，然后选择 "**编辑**"。  

> ##### 图 11  
> 选择 "**编辑**" 
> ![ 选择 "编辑"][ImageEdit]  

1.  单击 "**添加自定义设备**"。  

1.  输入设备的名称、宽度和高度。  [设备像素比率][MDNWindowDevicePixelRatio]、[用户代理字符串][MDNUserAgent]和[设备类型](#set-the-device-type)字段是可选的。  "设备类型" 字段是默认情况下设置为 "**移动电话**" 的列表。  

> ##### 图 12  
> 创建自定义设备  
> ![创建自定义设备][ImageAddCustomDevice]  

### 显示标尺   

单击 "**更多选项**"，然后选择 "**显示标尺**" 以查看视区左侧和左侧的标尺。  标尺的调整单位为像素。  

> ##### 图 13  
> 显示标尺  
> ![显示标尺][ImageShowRulers]  

> ##### 图 14  
> 视区左侧和左侧的标尺  
> ![视区左侧和左侧的标尺][ImageRulers]  

### 缩放视区   

使用 "**缩放**" 列表放大或缩小。  

> ##### 图 15  
> 缩放  
> ![缩放][ImageZoomViewport]  

## 限制网络和 CPU   

要限制网络和 CPU，请从 "**限制**" 列表中选择 "**中层移动**" 或 "**低端移动**"。  

> ##### 图 16  
> 限制列表  
> ![限制列表][ImageThrottling]  

中层**移动**模拟快速3g 并限制 CPU，使其比平时慢4倍。  **低端移动**模拟低速3g，使 CPU 比平时慢6倍。  请记住，带宽限制相对于便携式计算机或桌面机的正常功能。  

> [!NOTE]
> 如果**设备工具栏**较窄，将隐藏 "**限制**" 列表。  

> ##### 图 17  
> "设备" 工具栏  
> !["设备" 工具栏][ImageDeviceToolbar3]  

### 仅调节 CPU   

若要仅限制 CPU，而不限制网络，请转到 "**性能**" 面板，单击 "**捕获设置** ![ 捕获设置 ][ImageCaptureIcon] "，然后从**CPU**列表中选择**4x 减速**或**6x 减速**。  

> ##### 图18  
> CPU 列表  
> ![CPU 列表][ImageCPU]  

### 仅限制网络   

若要仅限制网络而不是 CPU，请转到 "**网络**" 面板，然后从 "**限制**" 列表中选择 "**快速 3G** " 或 "**慢速 3g** "。  

> ##### 图19  
> 限制列表  
> ![限制列表][ImageNetwork]  

或者按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "命令" 菜单，键入 `3G` ，然后选择 "**启用快速3g 限制**" 或 "**启用慢速3g 限制**"。  

> ##### 图20  
> 命令菜单  
> ![命令菜单][ImageCommandMenu]  

您也可以从 "**性能**" 面板中设置网络限制。  单击 "**捕获设置** ![ 捕获 ][ImageCaptureIcon] 设置"，然后从 "**网络**" 列表中选择 "**快速 3g** " 或 "**慢速 3g** "。  

> ##### 图21  
> 从性能面板设置网络限制  
> ![从性能面板设置网络限制][ImageNetwork2]  

## 替代地理位置   

若要打开地理位置替代的 UI，请单击 "**自定义和控制 DevTools** " `...` ，然后选择 "**更多工具**  >  **传感器**"  

> ##### 图22  
> 传感器  
> ![传感器][ImageSensors]  

或按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "命令" 菜单，键入 `Sensors` ，然后选择 "**显示传感器**"。  

> ##### 图23  
> 显示传感器  
> ![显示传感器][ImageShowSensors]  

从 "**地理**位置" 列表中选择其中一个预设，或选择 "**自定义位置**" 以输入您自己的坐标，或选择 "**位置不可用**" 以测试当地理位置处于错误状态时页面的行为。  

> ##### 图24  
> 地理位置  
> ![地理位置][ImageGeolocation]  

## 设置方向   

若要打开方向用户界面，请单击 "**自定义和控制 DevTools** " `...` ，然后选择 "**更多工具**  >  **传感器**"。  

> ##### 图25  
> 传感器  
> ![传感器][ImageSensors2]  

或按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "命令" 菜单，键入 `Sensors` ，然后选择 "**显示传感器**"。  

> ##### 图26  
> 显示传感器  
> ![显示传感器][ImageShowSensors2]  

从 "**方向**" 列表中选择其中一个预设，或选择 "**自定义方向**" 以设置您自己的 alpha、beta 和伽玛值。  

> ##### 图27  
> Orientation  
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
[DevToolsRemoteDebugging]：/microsoft-edge/devtools-guide-chromium/remote-debugging/index "开始使用远程调试 Android 设备"  

[MDNWindowDevicePixelRatio]: https://developer.mozilla.org/docs/Web/API/Window/devicePixelRatio "DevicePixelRatio |MDN"  
[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "用户代理 |MDN"  

[WikiApproximation]: https://en.wikipedia.org/wiki/Order_of_approximation#First-order "近似值-第一顺序-维基百科的顺序"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
