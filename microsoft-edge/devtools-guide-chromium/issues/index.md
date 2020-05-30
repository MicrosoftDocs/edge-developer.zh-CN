---
title: 查找并修复 Microsoft Edge DevTools 问题工具的相关问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 394ea0e831e3b60a60a149d1281c5cca382a887d
ms.sourcegitcommit: ba9f0ed77e84174b03262b17e62c6a7e26cfeb3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/30/2020
ms.locfileid: "10688127"
---
<!-- Copyright Sam Dutton 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  





# 查找并修复 Microsoft Edge DevTools 问题工具的相关问题   



Microsoft Edge DevTools 中的 "**问题**" 工具减少了**控制台**的通知 fatigue 和混乱。  用于查找浏览器检测到的问题的解决方案，例如 cookie 问题和混合内容。  

> [!NOTE]
> 在 Microsoft Edge 84 中，"**问题**" 工具支持三种类型的问题：  
> *   [Cookie 问题][MDNSameSiteCookies]  
> *   [混合内容][MDNMixedContent]  
> *   [COEP 问题][W3CCOEPSpec]
> 
> Microsoft Edge DevTools 团队计划在未来版本的 Microsoft Edge 中支持更多问题类型。  

## 打开 DevTools 抽屉中的 "问题" 工具   

1.  访问包含要修复的问题的页面（如[samesite-sandbox.glitch.me][GlitchSamesiteSandbox]）。  
1.  [打开 DevTools][DevtoolsOpen]。  
1.  :::row:::
       :::column span="":::
          在黄色警告栏中选择 "**转到问题**" 按钮。  
          
          :::image type="complex" source="../media/issues-open-issues-tab.msft.png" alt-text="检测到问题时，在黄色警告栏中的 "转到问题" 按钮" lightbox="../media/issues-open-issues-tab.msft.png":::
             图 1.  检测到问题时黄色警告栏中的 "**转到问题**" 按钮。  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          或者，从 "**更多工具**" 菜单中选择 "**问题**"。  
          
          :::image type="complex" source="../media//issues-more-tools-menu.msft.png" alt-text=""其他工具" 菜单中的 "问题" 工具" lightbox="../media//issues-more-tools-menu.msft.png":::
             图 2.  "**其他工具**" 菜单中的 "**问题**" 工具  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  如有必要，请选择 "**重新加载页面**" 按钮。  
    
    :::image type="complex" source="../media/issues-tab-before-refresh.msft.png" alt-text="带有 "重新加载页面" 按钮的 DevTools 抽屉中的问题工具" lightbox="../media/issues-tab-before-refresh.msft.png":::
       图 3.  带有 "**重新加载页面**" 按钮的 DevTools 抽屉中的**问题**工具  
    :::image-end:::  

    **控制台**中报告的问题非常难以理解，例如下图中的 cookie 警告。  根据报告的问题，可能不清楚您必须执行的操作。  
    
    :::image type="complex" source="../media/issues-tab-after-refresh.msft.png" alt-text="DevTools 抽屉中有三个 cookie 问题的问题工具" lightbox="../media/issues-tab-after-refresh.msft.png":::
       图 4.  DevTools 抽屉中有三个 cookie 问题的**问题**工具  
    :::image-end:::  
    
## 在 "问题" 工具中查看项目   

DevTools 抽屉中的 "**问题**" 工具以结构化、聚合和可操作的方式表示警告。  

1.  选择 "**问题**" 工具中的项目以获取有关如何解决问题和查找受影响的资源的指南。  
    
    :::image type="complex" source="../media/issues-tab-issue-open.msft.png" alt-text="将跨网站 cookie 标记为安全问题在 "问题" 工具中打开" lightbox="../media/issues-tab-issue-open.msft.png":::
       图 5.  将**跨网站 Cookie 标记为安全**问题在 "**问题**" 工具中打开  
    :::image-end:::  
    
    每个项都有四个组件：  
    
    *   描述问题的标题。  
    *   提供上下文和解决方案的说明。  
    *   链接到相应 DevTools 上下文（如网络面板）中的资源的**受影响的资源**部分。  
    *   链接到更多指南。  
    
1.  选择**受影响的资源**中的项目以查看详细信息。  在以下示例中，将**跨网站 Cookie 标记为安全**问题会影响一个 cookie 和两个请求。  
    
    :::image type="complex" source="../media/issues-tab-affected-resources.msft.png" alt-text="受影响的资源在问题抽屉选项卡中打开" lightbox="../media/issues-tab-affected-resources.msft.png":::
       图 6.  受影响的资源在 DevTools 抽屉中的 "**问题**" 工具中打开  
    :::image-end:::  
    
## 在上下文中查看问题   

1.  选择资源链接以在 DevTools 内的相应上下文中查看项目。  在以下示例中，在 `samesite-sandbox.glitch.me` "**请求**" 下选择 "显示附加到该请求的 cookie"。  
    
    :::image type="complex" source="../media/issues-tab-view-request.msft.png" alt-text="在 DevTools 网络面板中查看受影响的 cookie" lightbox="../media/issues-tab-view-request.msft.png":::
       图 7.  在 DevTools 网络面板中查看受影响的 cookie  
    :::image-end:::  

1.  滚动查看有问题的项目：对于以下示例，该 `ck02` cookie。  将鼠标悬停在**SameSite**列上，以查看 `None` 检测到的问题的值。  
    
    :::image type="complex" source="../media/issues-tab-view-issue.msft.png" alt-text="DevTools 网络面板中 ck02 cookie 的 SameSite 列中没有值" lightbox="../media/issues-tab-view-issue.msft.png":::
       图 8.  `None` **SameSite** `ck02` DevTools**网络**面板中的 cookie 的 SameSite 列中的值  
    :::image-end:::  

<!--## Feedback  -->  



<!-- image links -->  

<!-- links -->  

[DevtoolsOpen]: /microsoft-edge/devtools-guide-chromium/open "打开 Microsoft Edge DevTools |Microsoft 文档"  

[GlitchSamesiteSandbox]: https://samesite-sandbox.glitch.me "SameSite cookie 测试 |故障"  

[MDNSameSiteCookies]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite "SameSite cookie |MDN"  
[MDNMixedContent]: https://developer.mozilla.org/docs/Web/Security/Mixed_content "混合内容 |MDN"  

[W3CCOEPSpec]: https://wicg.github.io/cross-origin-embedder-policy "跨起源 Embedder 策略 |Web Incubator 社区组"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/issues/index)，由[Sam Dutton][SamDutton] （开发人员提供者）创作。  
[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[SamDutton]: https://developers.google.com/web/resources/contributors/samdutton  
