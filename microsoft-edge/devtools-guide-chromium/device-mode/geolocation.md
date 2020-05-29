---
title: 通过 Microsoft Edge DevTools 替代地理位置
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 307064bedf992e528b6d79eed3a2ade3367830d4
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607438"
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





# 通过 Microsoft Edge DevTools 替代地理位置   



许多网站利用用户位置，以便为用户提供更相关的体验。  例如，天气网站可能会在用户向网站授予访问当前用户位置的权限后，在用户区域中显示本地预测。  

<!--todo: add link to user location section when available -->  

如果你正在生成根据用户所在位置而更改的 UI，你可能需要确保网站在世界各地的不同位置正确运行。  要在 Microsoft Edge DevTools 中替代您的地理位置，请执行以下操作：  

1.  按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "**命令" 菜单**。  
    
    > ##### 图 1  
    > 命令菜单  
    > ![命令菜单][ImageCommandMenu]  
    
1.  键入 `sensors` ，选择 "**显示传感器**"，然后按 `Enter` 。  "**传感器**" 选项卡将在 DevTools 窗口底部打开。  
1.  从 "**地理**位置" 列表中，选择其中一个预设城市，例如 `Tokyo` ，或选择 "**自定义位置**" 以输入自定义经度和纬度坐标，或选择 "**位置不可用**" 以查看当用户位置不可用时您的网站的行为。  
    
    > ##### 图 2  
    > `Tokyo`从 "**地理位置**" 列表中选择  
    > ![从 "地理位置" 列表中选择东京][ImageGeolocationTokyo]  
    
<!--## Feedback   

  -->  

<!-- image links -->  

[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/device-mode-console-command-menu.msft.png "图1：命令菜单"  
[ImageGeolocationTokyo]: /microsoft-edge/devtools-guide-chromium/media/device-mode-console-sensors-geolocation-tokyo.msft.png "图2：从 "地理位置" 列表中选择东京"  

<!-- links -->  

<!--[WebFundamentalsNativeHardwareUserLocationIndex]: /web/fundamentals/native-hardware/user-location/index "User Location"  -->  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/geolocation)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
