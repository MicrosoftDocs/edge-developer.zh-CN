---
description: 使用 Microsoft Edge 中的虚拟设备构建移动版的第一网站。
title: 在 Microsoft Edge DevTools 中模拟移动设备
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/04/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge，web 开发，f12 工具，devtools，仿真，设备，模拟，移动
ms.openlocfilehash: c70b81eabb145461eac7d1b9a8f438d6a18fbc89
ms.sourcegitcommit: cc96ada9679b23feb841e46f19d8077251c4a4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "10997033"
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

# 在 Microsoft Edge DevTools 中模拟移动设备  

使用 **设备仿真** 来大致了解你的页面在移动设备上的外观和响应。  Microsoft Edge DevTools 提供了一系列功能，可帮助你模拟移动设备。  集合包含以下功能。  

*   [模拟移动视区](#simulate-a-mobile-viewport)  
*   [阻止网络](#throttle-the-network-only)  
*   [调节 CPU](#throttle-the-cpu-only)  
*   [模拟地理位置](#override-geolocation)  
*   [设置方向](#set-orientation)  
*   [设置用户代理字符串](#set-user-agent-string)  

## 限制  

**设备模拟** 是你的页面在移动设备上的 [第一顺序近似值][WikiApproximation] 。  **设备仿真** 实际上并不在移动设备上运行代码。  而是从便携式计算机或桌面模拟移动用户体验。  

移动设备的某些方面从不在 DevTools 中进行模拟。  例如，移动 Cpu 的体系结构不同于便携式计算机或桌面 Cpu 的体系结构。  如果有疑问，最佳做法是在移动设备上实际运行您的页面。  在页面实际在移动设备上运行时，可使用 [远程调试] [DevToolsRemoteDebugging] 与你的计算机中的页面代码进行交互。  当您与代码交互时，您可以查看、更改、调试、配置文件或全部四种。  您的计算机可能是笔记本或台式计算机。  

## 模拟移动视区  

选择 " **切换设备仿真**  \ (![ 切换设备" 工具栏 ][ImageDeviceToolbarIcon] \ ) 或选择 " **自定义和控制 DevTools** \ (`...` \" ) > **设备仿真** "打开可使您模拟移动视区的 UI。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
    "设备" 工具栏  
:::image-end:::  

默认情况下，设备工具栏将在 "响应式" 视区模式下打开。  

### 响应式视区模式  

若要跨多个屏幕大小快速测试页面的外观，请拖动图柄以将视区大小调整为所需的尺寸。  您也可以在 "宽度" 和 "高度" 框中输入特定值。  在下图中，宽度设置为 `626` ，高度设置为 `516` 。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-handles-highlighted.msft.png":::
    在 "响应" 视口模式下更改视区尺寸的控制滑块  
:::image-end:::  

#### 显示媒体查询  

如果你已在页面上定义了媒体查询，则通过在你的视区上方显示媒体查询断点，跳转到这些媒体查询将生效的视区维度。  选择 "**更多选项**"  >  **显示媒体查询**。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-more-options-show-media-queries.msft.png":::
   **显示媒体查询**  
:::image-end:::  

选择一个断点以更改视区的宽度，以便触发媒体查询。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-click-breakpoint.msft.png":::
   选择断点以更改视区的宽度  
:::image-end:::  

#### 设置设备类型  

使用 **设备类型** 列表来模拟移动设备或桌面设备。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-device-type-list.msft.png":::
   **设备类型**列表  
:::image-end:::  

下表介绍了可用设备类型选项之间的差异。  呈现方法列引用 Microsoft Edge 是否将页面呈现为移动设备或桌面视区。  光标图标列指悬停在页面上时看到的光标类型。  "触发事件" 列指 `touch` `click` 当您与页面交互时，页面是触发还是事件。  

| 选项 | 呈现方法 | 光标图标 | 触发的事件 |  
|:--- |:--- |:--- |:--- |  
| 移动版 | 移动版 | 圆形 | 触摸 |  
| 移动 \ (无接触 \ )  | 移动版 | 正常 | 单击 |  
| 桌面 | 桌面 | 正常 | 单击 |  
| 桌面 (触控 \ )  | 桌面 | 圆形 | 触摸 |  

> [!NOTE]
> 如果未显示 "**设备类型**" 列表，请选择 "**更多选项**"  >  **添加设备类型**。  

### 移动设备视区模式  

若要模拟特定移动设备的尺寸，请从 **设备** 列表中选择该设备。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-device-list.msft.png":::
   **设备**列表  
:::image-end:::  

#### 将视区旋转到横向方向  

以横向方向测试您的网页。  

*   若要将视区旋转到横向方向，请选择 " **旋转** \ (![ 旋转 ][ImageRotateIcon] \ ) "。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-landscape.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-landscape.msft.png":::
       横向显示的页面  
    :::image-end:::  
    
> [!NOTE]
> 如果**设备工具栏**较窄，"**旋转**" 按钮将消失。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   " **设备" 工具栏**  
:::image-end:::  

有关详细信息，请转到 [设置方向](#set-orientation)。  

#### 显示设备帧  

当模拟特定移动设备（如 iPhone 6）的尺寸时，将在视区周围显示物理设备帧。  

1.  打开 " **更多选项**"。  
1.  选择 " **显示设备帧**"。  

> [!NOTE]
> 如果您没有看到特定设备的设备框架，则意味着 DevTools 没有该选项的图片。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-option-show-device-frame.msft.png":::
         显示设备帧  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-options-device-frame-iphone-6.msft.png":::
         IPhone 6 的设备帧  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### 添加自定义移动设备  

如果默认列表中未包括所需的移动设备选项，则可以添加自定义设备。  若要添加自定义设备，请完成以下步骤。  

1.  选择 " **设备** 列表" > " **编辑**"。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-device-list-edit.msft.png":::
       选择 "**编辑**"  
    :::image-end:::  
    
1.  选择 " **添加自定义设备**"。  
1.  在 **模拟设备**上，输入自定义设备的设备名称、屏幕宽度和屏幕高度。  [设备像素比率][MDNWindowDevicePixelRatio]、[用户代理字符串][MDNUserAgent]和[设备类型](#set-the-device-type)字段是可选的。  "设备类型" 字段默认为 " **移动**"。  
    
    :::image type="complex" source="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-settings-emulated-devices-add.msft.png":::
       创建自定义设备  
    :::image-end:::  
    
### 显示标尺  

如果需要测量屏幕尺寸，可以使用标尺测量屏幕大小（以像素为单位）。  选择 "**更多选项**"  >  **显示 "标尺**" 以在视区左侧和左侧显示标尺。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-options-show-rulers.msft.png":::
         用于显示标尺的菜单项  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-rulers.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-rulers.msft.png":::
         视区左侧和左侧的标尺  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### 缩放视区  

若要以多个缩放级别测试页面的外观，请使用 " **缩放** " 列表放大或缩小。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-zoom.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-zoom.msft.png":::
   **缩放**  
:::image-end:::  

## 限制网络和 CPU  

移动设备通常具有网络和 CPU 限制。  确保你可以测试页面的加载速度以及它在不同 internet 和 CPU 速度中的响应速度。  

限制网络和 CPU。  

1.  选择 " **限制** 列表"，然后将预置更改为 " **中层移动** " 或 " **低端手机**"。  
    *   中层**移动**模拟 `fast 3G` 和限制你的 CPU。  这比平时慢4倍。  
    *   **低端移动** 模拟 `slow 3G` 和限制您的 CPU。  这比平时慢六倍。  
    
所有限制都基于便携式计算机或桌面机的正常功能。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-throttle.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-throttle.msft.png":::
   "设备" 工具栏中的 " **限制** " 列表  
:::image-end:::  

> [!NOTE]
> 如果 " **限制" 列表** 处于隐藏状态，则你的 **设备工具栏** 太窄。  若要访问 **限制列表**，请增大 "设备" **工具栏**的宽度。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-highlighted.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-highlighted.msft.png":::
   " **设备" 工具栏**  
:::image-end:::  

### 仅调节 CPU  

若要仅限制 CPU 而不是网络，请完成以下步骤。

1.  选择 " **性能** " 面板，然后选择 " **捕获设置** \ (![ 捕获设置 ][ImageCaptureIcon] \ ) "。
1.  选择**CPU**  >  **4x 减速**或**6x 减速**。
    
    :::image type="complex" source="../media/device-mode-performance-cpu-throttle.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-performance-cpu-throttle.msft.png":::
       "**性能**" 面板中的**CPU**列表  
    :::image-end:::  
    
### 仅限制网络  

若要仅限制网络，请完成以下步骤。

1.  选择 " **网络** " 面板。
1.  选择 "**联机**  >  **快速 3g** " 或 "**低速 3g**"。
    
    :::image type="complex" source="../media/device-mode-network-throttle.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-network-throttle.msft.png":::
       网络面板中的 **限制** 列表  
    :::image-end:::  
    
    或选择 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "**命令" 菜单**，键入 `3G` ，然后选择 "**启用快速3g 限制**" 或 "**启用慢速3g 限制**"。  
    
    :::image type="complex" source="../media/device-mode-command-menu-throttle.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-command-menu-throttle.msft.png":::
       **命令菜单**  
    :::image-end:::  
    
您也可以从 " **性能** " 面板设置网络限制。  

1.  选择 **"捕获设置** \ (![ 捕获设置 ][ImageCaptureIcon] \ ) "，然后选择 " **网络** " 列表，并将预设置更改为 " **快速 3g** " 或 " **低速 3g**"。  
    
    :::image type="complex" source="../media/device-mode-performance-network-throttle.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-performance-network-throttle.msft.png":::
       从 **性能** 面板设置网络限制  
    :::image-end:::  
    
## 替代地理位置  

:::row:::
   :::column span="":::
      如果你的页面依赖于移动设备上的地理位置信息来正确呈现，请使用地理位置替代 UI 来提供不同的 geolocations。  

      1.  选择 "**自定义和控制 DevTools** \ (`...` \ ) " > "**其他工具**  >  **传感器**"。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         地理位置的**传感器**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  打开 "命令" 菜单。  
          *   选择 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 。  
      1. 键入 `Sensors` ，然后选择 " **显示传感器**"。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         **显示** 地理位置的传感器  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

在 " **传感器** " 面板上，你可以使用 " **位置** " 下拉菜单选择 DevTools 中包含的预设位置之一。  若要输入自定义位置，请选择 " **其他" ...** 并输入自定义位置的坐标。  当位置信息不可用时，若要在错误状态中测试页面，请选择 " **位置不可用**"。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo.msft.png":::
    选择了预设位置的 "**传感器**" 面板。  
:::image-end:::

## 设置方向  

:::row:::
   :::column span="":::
      如果页面依赖于移动设备上的方向信息来正确呈现，请打开 "方向" UI。  

      1.  选择 "**自定义和控制 DevTools** \ (`...` \ ) " > "**其他工具**  >  **传感器**"。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-sensors.msft.png":::
         方向**传感器**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  打开 "命令" 菜单。  
          *   选择 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 。  
      1. 键入 `Sensors` ，然后选择 " **显示传感器**"。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-sensors.msft.png":::
         **显示** 方向的传感器  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

在 " **传感器** " 面板上，您可以从 " **方向** " 下拉菜单中选择预设方向。  若要输入自己的方向，请选择 " **自定义方向**"，然后输入您自己的 [alpha][MDNDeviceOrientaitonAlpha]、 [beta][MDNDeviceOrientaitonBeta]和 [伽玛][MDNDeviceOrientaitonGamma] 值。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-sensors-tokyo-portrait-upside-down.msft.png":::
    "**传感器**" 面板上的**方向**选项  
:::image-end:::  

## 设置用户代理字符串  

:::row:::
   :::column span="":::
      如果页面依赖于移动设备的用户代理字符串来正确呈现，请使用 " **网络条件** " 面板提供不同的用户代理字符串。  
      
      1.  选择 "**自定义和控制 DevTools** \ (`...` \ ) " >**更多工具**  >  **网络条件**。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-more-tools-network-conditions.msft.png":::
         "**更多工具**" 菜单中的**网络条件**输入  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      1.  打开 "命令" 菜单。  
          *   选择 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 。  
      1. 键入 `Network conditions` ，然后选择 " **显示网络条件**"。  
      
      :::image type="complex" source="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-command-menu-network-conditions.msft.png":::
         **显示网络条件**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

在 " **用户代理**" 旁边，清除 " **自动选择** " 复选框。  然后，选择 " **自定义 ...** " 以从预定义的用户代理字符串列表中进行选择。  若要输入自己的用户代理字符串，请在 " **输入自定义用户代理**" 中输入字符串。  

:::image type="complex" source="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png" alt-text="&quot;设备&quot; 工具栏" lightbox="../media/device-mode-toggle-device-toolbar-network-conditions-macos.msft.png":::
    在 macOS 上将用户代理字符串设置为 Microsoft Edge  
:::image-end:::  

## 与 Microsoft Edge 开发人员工具团队联系  

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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
