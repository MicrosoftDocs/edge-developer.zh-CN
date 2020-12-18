---
description: 使用模拟面板测试不同的浏览器配置文件、屏幕大小和分辨率以及 GPS 位置坐标
title: DevTools - 模拟
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， 开发工具， 设备仿真， 响应式设计， 地理位置， 分辨率
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: af740472f22a8b322c03cb672a3da909ef195fac
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232259"
---
# 枚举  

> [!NOTE]
> 新版 Microsoft Edge 是使用 Chromium 构建的，并从版本 75 开始。  有关详细信息，请 [下载新的 Microsoft Edge，][MicrosoftNewEdge]并尝试使用新的 Microsoft Edge ([Chromium) 开发人员工具][DevtoolsGuideChromium]。  
> 
> 若要模拟新 DevTools 中的不同设备、浏览器、屏幕大小和分辨率，请导航到 Microsoft [Edge \ (Chromium\) DevTools 中的"模拟移动设备"。][DevtoolsGuideChromiumDeviceMode]  

**模拟面板**可帮助执行下列活动。    

*   模拟[各种设备配置文件](#device)[、浏览器](#browser-profile)[和屏幕大小和分辨率](#display)  
*   测试 [不同的地理位置设置和坐标](#geolocation)  

:::image type="complex" source="./media/emulation.png" alt-text="Microsoft Edge DevTools 模拟面板" lightbox="./media/emulation.png":::
   Microsoft Edge DevTools **模拟** 面板  
:::image-end:::  

1.  即使 **关闭并重新打开** DevTools，"持久模拟设置"按钮也保存了从默认桌面模拟设置进行的任何更改。  

1.  " **重置仿真设置"** 按钮将仿真设置重置回默认的桌面浏览器配置文件，并关闭 GPS 的 Microsoft Edge 用户代理字符串。  

1.  当这些选项中的任一选项从默认值更改时，" **模拟** "选项卡将显示信息性警报，以指示正在模拟浏览器行为的一些方面。  

## 设备  

从可自动配置其他模拟选项或指定你自己的自定义配置的 Windows 设备配置文件的预设 **列表中进行选择** 。  切换回 **"默认值** "以重置所有模拟工具。  

## 模式  

### 浏览器配置文件  

模拟在 Windows Phone 设备上运行的页面的快速方法就是将**浏览器配置文件**设置更改为 Windows **Phone。**  

#### 用户代理字符串  

修改用户代理字符串以模仿其他浏览器是调试仅发生在 Microsoft Edge 中的错误的良好第一步。  

脚本使用用户代理字符串检测所使用的浏览器。  脚本可能是前端、后端或前端和后端。  尽管代码不使用浏览器检测，但代码可能会从第三方 JavaScript 库或服务器端脚本继承它。  

浏览器检测的问题是，您可以使用有关浏览器功能的假设 (或更改\) 网页中的功能。 相反，应考虑使用功能检测来检测浏览器的功能。  由于下列情况之一，可能会发生意外行为。  

*   面向 Windows Internet Explorer 8的代码可能在 Microsoft Edge 中以不同方式运行。  
*   浏览器应支持的功能已禁用，因为开发人员做出假设。  

如果更改用户代理字符串可清除该问题，则浏览器检测可能是原因。  

## 显示  

显示模拟以在不同的屏幕大小和分辨率上预览网站。  

*   传统桌面监视器  
*   较小的移动屏幕  
*   较新的高分辨率显示器  

调整模拟以尝试匹配要模拟的屏幕的物理尺寸。  模拟像素可能显示为压缩或展开。 如果你需要测试 HTML 元素的像素完美位置，则不建议进行模拟。  但是，仿真适用于测试响应式设计和识别较大的元素定位问题。  

### Orientation  

从横向**或****纵向模式**选择。  

### 分辨率  

从常用设备分辨率的预设列表中进行选择，或指定你自己的 **自定义** 配置。 支持高达 80 英寸和 3820 x 2160 的分辨率。  

## 地理位置  

如果您的网站使用地理位置 [API][MdnGeolocationUsing] 提供基于位置的服务，则为了方便使用桌面，可进行以下活动。  

*   轻松测试不同的 GPS 坐标  
*   轻松测试不同的传感器状态  

这些设置会覆盖支持地理位置的设备上的任何实际 GPS 坐标和传感器状态。  

使用设备位置之前，您的网站必须请求并授予用户权限。  测试站点的行为方式，以及 Microsoft Edge 设置面板中的位置权限和 **位置** 权限。  

**...** > **设置**  > **查看高级设置**  > **网站权限**  > **管理**  

:::image type="complex" source="./media/settings_manage_permissions.png" alt-text="从 Microsoft Edge 设置面板管理网站权限" lightbox="./media/settings_manage_permissions.png":::
   从 Microsoft Edge 设置面板管理 **网站** 权限  
:::image-end:::  

## 快捷方式

| 操作  | 快捷方式  |  
|:--- |:--- |  
| 重置模拟设置 | `Ctrl`+`Shift`+`L` |  

<!-- links -->  


[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具 |Microsoft Docs"  
[DevtoolsGuideChromiumDeviceMode]: /microsoft-edge/devtools-guide-chromium/device-mode "在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  

[MicrosoftNewEdge]: https://www.microsoft.com/edge "下载新版 Microsoft Edge 浏览器"  

[MdnGeolocationUsing]: https://developer.mozilla.org/docs/Web/API/Geolocation/Using_geolocation "地理位置 API |MDN"  
