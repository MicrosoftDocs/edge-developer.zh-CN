---
title: 强制 Microsoft Edge DevTools 进入配色方案预览模式（CSS 首选配色方案）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 94c5369f0eb35059933be7f6202a4f64450629cd
ms.sourcegitcommit: d7fdb67df0fe73fa5ae96e5a69a847d07941d0a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "10758059"
---
# 减少了运动模拟  

Web 产品中的动画可能是辅助功能问题。  操作系统通过包括用于关闭动画的选项来处理问题，以避免用户混淆和潜在的与运行状况相关的问题，如触发病情发作。  在 web 上，你可以使用 "按[优先减少的动画][MDNPrefersReducedMotion]" CSS 媒体查询来检测用户是否希望看不到任何动画。  在你的产品中，你可以在测试中包装动画代码，以避免针对受影响的用户显示动画。  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
  animation: none;
  }
}
```  

使用[Microsoft Edge DevTools][DevtoolsGuideChromiumMain]，您可以模拟此 "减少的动作" 设置，而无需更改操作系统。  

1.  打开 "**命令" 菜单**。  
    1.  按 `Control` + `Shift` + `P` Windows 或 `Command` + `Shift` + `P` macOS。  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           **命令菜单**  
        :::image-end:::   
        
1.  键入 `reduced` ，打开和关闭模拟。  选择 "" 选项，然后按 `Enter` 。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="打开或关闭 "命令" 菜单中的 "优先减少动作" 设置" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       打开或关闭 "**命令" 菜单**中的 "**优先减少动作**" 设置  
    :::image-end:::  
    
1.  刷新当前页以测试动画是否处于关闭状态或是否可见。  
    
<!-- image links -->  

[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-console-command-menu-rendering.msft.png "图1：命令菜单"  
[ImageToggleReducedMotionFromCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png "图2：切换从命令调色板缩小运动"

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge （Chromium）开发人员工具 Microsoft |Microsoft 文档"  

[MDNPrefersReducedMotion]: https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion "首选-减少-运动 |MDN"  