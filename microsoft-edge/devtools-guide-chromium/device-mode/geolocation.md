---
description: 打开 "传感器" 选项卡，然后从 "地理位置" 列表中选择 "坐标"。
title: 通过 Microsoft Edge DevTools 替代地理位置
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f2bc395993ff59d88360a363b2c4bc12b570f1ab
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125011"
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

如果你正在生成根据用户所在位置而更改的 UI，你可能需要确保网站在世界各地的不同位置正确运行。  若要在 Microsoft Edge DevTools 中替代您的地理位置，请完成以下操作。  

1.  选择 `Control` + `Shift` + `P` \ (Windows、Linux \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "**命令" 菜单**。  
    
    :::image type="complex" source="../media/device-mode-console-command-menu.msft.png" alt-text="命令菜单" lightbox="../media/device-mode-console-command-menu.msft.png":::
       **命令菜单**  
    :::image-end:::  
    
1.  键入 `sensors` ，选择 " **显示传感器**"，然后选择 `Enter` 。  " **传感器** " 选项卡将在 DevTools 窗口底部打开。  
1.  从 " **地理** 位置" 列表中，选择其中一个预设城市，例如 `Tokyo` ，或选择 " **自定义位置** " 以输入自定义的经度和纬度坐标，或者选择 " **位置不可用** " 以查看当用户位置不可用时您的网站的行为。  
    
    :::image type="complex" source="../media/device-mode-console-sensors-geolocation-tokyo.msft.png" alt-text="命令菜单" lightbox="../media/device-mode-console-sensors-geolocation-tokyo.msft.png":::
       `Tokyo`从 "**地理位置**" 列表中选择  
    :::image-end:::  
    
## 与 Microsoft Edge 开发人员工具团队联系

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[WebFundamentalsNativeHardwareUserLocationIndex]: /web/fundamentals/native-hardware/user-location/index "User Location"  -->  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/geolocation)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
