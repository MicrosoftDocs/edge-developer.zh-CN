---
description: 使用仿真面板测试不同浏览器配置文件、屏幕大小和分辨率以及 GPS 位置坐标
title: DevTools-模拟
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge，web 开发，f12 工具，devtools，设备仿真，响应式设计，地理位置，分辨率
ms.custom: seodec18
ms.openlocfilehash: d66646600aeaac279acaf622527f829c69f33286
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563503"
---
# 仿真

*仿真*面板可帮助你：
 - 模拟各种[设备配置文件](#device)、[浏览器](#browser-profile)、[屏幕大小和分辨率](#display)
 - 测试不同[的地理位置设置和坐标](#geolocation)

![Microsoft Edge DevTools 仿真面板](./media/emulation.png)

1. 即使在关闭并重新打开 DevTools 时，"**始终仿真设置**" 按钮也会保存你从默认桌面仿真设置所做的任何更改。 

2. "**重置仿真设置**" 按钮会将你的仿真设置重置为默认*桌面*浏览器配置文件，并将 Microsoft Edge 用户代理字符串重置为 "GPS 关闭"。

3. 如果这些选项中的任何一个更改为默认值，则 "**模拟**" 选项卡将显示信息性警报，指示浏览器行为的某些方面已被模拟。

## 设备

从自动配置其他仿真选项或指定你自己的*自定义*Configuation 的 Windows 设备配置文件的预设列表中进行选择。 切换回*默认*设置以重置所有模拟工具。

## 模式

### 浏览器配置文件
模拟在 Windows Phone 设备上运行的页面的快速方法是将**浏览器配置文件**设置更改为*windows phone*。

#### 用户代理字符串

在调试仅在 Microsoft Edge 中发生的错误时，修改您的用户代理字符串以模仿另一个浏览器是一个很好的第一步。 

前端和/或后端脚本有时使用用户代理字符串检测你正在使用的浏览器。 即使在您自己的代码中不使用浏览器检测，您也可以使用第三方 JavaScript 库或服务器端脚本执行此操作。

浏览器检测的问题是，它通常用于根据你的浏览器编写脚本所认为的开发人员可以执行的操作来缩放或更改网页中的功能，而不是检测你的浏览器可以使用功能检测实际执行的操作。 这可能会导致意外行为，因为面向 Windows Internet Explorer 8 的代码在 Microsoft Edge 中的运行方式非常不同;或者，你的浏览器完全支持支持的功能可能会因开发人员的假设而被禁用。

如果更改用户代理字符串后出现问题，则可能是浏览器检测原因。

## 显示

"显示仿真" 使你能够以不同的屏幕大小和分辨率预览你的网站：从常规桌面监视器到较小的移动屏幕或较新的高分辨率显示。

模拟适用于尝试匹配正在仿真的屏幕的物理尺寸。 模拟像素可能会显示为压缩或扩展，如果需要测试 HTML 元素的像素完全位置，则建议不要使用模拟。 但是，模拟适用于测试响应式设计和确定更大的元素定位问题。

### Orientation

从 "*横向*" 或 "*纵向*" 模式中进行选择。

### 分辨率

从常用设备分辨率的预设列表中选择，或指定您自己的*自定义*配置。支持最高80英寸和 3820 x 2160 的分辨率。

## 地理位置

如果您的网站使用[地理位置 API](https://developer.mozilla.org/docs/Web/API/Geolocation/Using_geolocation)提供基于位置的服务，您可以轻松地从桌面的便利测试不同的 GPS 坐标和传感器状态。 这些设置将覆盖支持地理位置的计算机上的任何实际 GPS 坐标和传感器状态。 

与 web 上的个人数据的任何使用一样，你的用户首先需要授予你的网站使用其位置的权限。 你可以通过 Microsoft Edge*设置*面板测试网站的行为和不包含位置权限：

**...** > **设置**  > **查看高级设置**  > **网站权限**  > **管理**

![从 Microsoft Edge 设置面板管理网站权限](./media/settings_manage_permissions.png)

## 指向

| 操作                   | 快捷方式               |
|:-------------------------|:-----------------------|
| 重置仿真设置 | `CTRL` + `SHIFT` + `L` |
