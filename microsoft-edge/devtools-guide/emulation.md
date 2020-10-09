---
description: 使用仿真面板测试不同浏览器配置文件、屏幕大小和分辨率以及 GPS 位置坐标
title: DevTools-模拟
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/04/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge，web 开发，f12 工具，devtools，设备仿真，响应式设计，地理位置，分辨率
ms.custom: seodec18
ms.openlocfilehash: 6eaa8d79cfd64473dcc52beff5659b39054e2a48
ms.sourcegitcommit: 912609aa49864e3363aaa3b245ff2aa4bec3fc3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104845"
---
# 枚举  

> [!NOTE]
> 新版 Microsoft Edge 是使用 Chromium 构建的，并从版本 75 开始。  有关详细信息，请 [下载新的 Microsoft edge][MicrosoftNewEdge]，然后尝试新的 [Microsoft edge (Chromium) 开发人员工具][DevtoolsGuideChromium]。  
> 
> 若要模拟新 DevTools 中的不同设备、浏览器、屏幕大小和分辨率，请导航到 " [在 Microsoft Edge 中模拟移动设备 \" (Chromium \ ) DevTools][DevtoolsGuideChromiumDeviceMode]"。  

**仿真**面板有助于执行下列活动。    

*   模拟各种 [设备配置文件](#device)、 [浏览器](#browser-profile)以及 [屏幕大小和分辨率](#display)  
*   测试不同 [的地理位置设置和坐标](#geolocation)  

:::image type="complex" source="./media/emulation.png" alt-text="Microsoft Edge DevTools 仿真面板" lightbox="./media/emulation.png":::
   Microsoft Edge DevTools **仿真** 面板  
:::image-end:::  

1.  " **始终仿真设置** " 按钮可保存从默认桌面仿真设置所做的任何更改，即使在关闭并重新打开 DevTools 时也是如此。  

1.  " **重置仿真设置** " 按钮将你的仿真设置重置为默认桌面浏览器配置文件，并将 Microsoft Edge 用户代理字符串重置为 "GPS 关闭"。  

1.  如果这些选项中的任何一个更改为默认值，则 " **模拟** " 选项卡将显示信息性警报，指示浏览器行为的某些方面正在被模拟。  

## 设备  

从自动配置其他仿真选项或指定你自己的 **自定义** 配置的 Windows 设备配置文件的预设列表中进行选择。  切换回 **默认** 设置以重置所有模拟工具。  

## 模式  

### 浏览器配置文件  

模拟在 Windows Phone 设备上运行的页面的快速方法是将 **浏览器配置文件** 设置更改为 **windows phone**。  

#### 用户代理字符串  

在调试仅在 Microsoft Edge 中发生的错误时，修改您的用户代理字符串以模仿另一个浏览器是一个很好的第一步。  

脚本使用用户代理字符串检测所使用的浏览器。  脚本可能是前端、后端或前端和后端。  尽管你的代码不使用浏览器检测，你的代码可以从第三方 JavaScript 库或服务器端脚本继承它。  

浏览器检测的问题是，你可以使用有关浏览器功能的假设在你的网页中缩放-回退 (或更改 \ ) 功能。 相反，你应该考虑使用功能检测来检测浏览器的功能。  出现意外行为可能是由于下列情况之一。  

*   在 Windows Internet Explorer 8 上定向的代码可能在 Microsoft Edge 中以不同的方式运行。  
*   由于开发人员的假定，您的浏览器应支持的功能已被禁用。  

如果更改用户代理字符串后出现问题，则可能是浏览器检测原因。  

## 显示  

显示仿真以在不同的屏幕大小和分辨率下预览你的网站。  

*   常规桌面监视器  
*   较小的移动屏幕  
*   较新的高分辨率显示  

模拟适用于尝试匹配正在仿真的屏幕的物理维度。  模拟像素可能会显示为压缩或扩展。 如果需要测试 HTML 元素的像素完全位置，则建议不要使用模拟。  但是，模拟适用于测试响应式设计和确定更大的元素定位问题。  

### Orientation  

从 " **横向** " 或 " **纵向** " 模式中进行选择。  

### 分辨率  

从常用设备分辨率的预设列表中选择，或指定您自己的 **自定义** 配置。 支持最高80英寸和 3820 x 2160 的分辨率。  

## 地理位置  

如果你的网站使用 [地理位置 API][MdnGeolocationUsing] 提供基于位置的服务，则你的桌面的便利将提供以下活动。  

*   轻松测试不同的 GPS 坐标  
*   轻松测试不同的传感器状态  

这些设置将覆盖支持地理位置的设备上的任何实际 GPS 坐标和传感器状态。  

在使用设备位置之前，您的网站必须请求并向用户授予权限。  通过 "Microsoft Edge **设置** " 面板测试网站的行为和不带位置权限。  

**...** > **设置**  > **查看高级设置**  > **网站权限**  > **管理**  

:::image type="complex" source="./media/settings_manage_permissions.png" alt-text="Microsoft Edge DevTools 仿真面板" lightbox="./media/settings_manage_permissions.png":::
   从 Microsoft Edge **设置** 面板管理网站权限  
:::image-end:::  

## 快捷方式

| 操作  | 快捷方式  |  
|:--- |:--- |  
| 重置仿真设置 | `Ctrl`+`Shift`+`L` |  

<!-- links -->  


[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  
[DevtoolsGuideChromiumDeviceMode]: /microsoft-edge/devtools-guide-chromium/device-mode "在 Microsoft Edge DevTools 中模拟移动设备 |Microsoft 文档"  

[MicrosoftNewEdge]: https://www.microsoft.com/edge "下载新版 Microsoft Edge 浏览器"  

[MdnGeolocationUsing]: https://developer.mozilla.org/docs/Web/API/Geolocation/Using_geolocation "地理位置 API |MDN"  