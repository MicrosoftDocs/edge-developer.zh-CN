---
description: 使用开发人员工具模拟运动减少。
title: '使用开发人员工具模拟减少运动 (CSS 首选减少运动) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 0e5243e01ca6c9344dceffb0bf004dadccc3d4d7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230787"
---
# 减少运动模拟  

Web 产品中动画可能是一个辅助功能问题。  操作系统通过包括关闭动画的选项来处理该问题，以避免用户混淆和潜在的健康相关问题（如触发癫痫）。  在 Web 上，可以使用首选的减少 [运动][MDNPrefersReducedMotion] CSS 媒体查询来检测用户是否不希望看到任何动画。  在你的产品中，你可以将动画代码包装在测试中，以避免向受影响的用户显示动画。  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
    animation: none;
  }
}
```  

使用 [Microsoft Edge DevTools，][DevtoolsIndex]你可以模拟这种减少的运动设置，而无需更改操作系统。  

1.  打开 **命令菜单**。  
    1.  在 `Control` + `Shift` + `P` Windows/Linux 或 `Command` + `Shift` + `P` macOS 上选择。  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           **命令菜单**  
        :::image-end:::  
        
1.  键入 `reduced` ，以打开和关闭模拟。  选择该选项并选择 `Enter` 。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="从命令菜单打开或关闭首选的减少运动设置" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       从命令菜单打开或关闭首选 **的** 减少 **运动设置**  
    :::image-end:::  
    
1.  刷新当前页面以测试动画是关闭还是可见。  
    
<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 |Microsoft Docs"  

[MDNPrefersReducedMotion]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-reduced-motion "prefers-reduced-motion |MDN"  
