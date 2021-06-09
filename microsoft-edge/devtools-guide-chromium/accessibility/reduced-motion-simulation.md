---
description: 使用开发人员工具模拟运动减少。
title: '使用开发人员工具使用 CSS 首选 (运动效果模拟运动) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 7244c2e80bbf9070214b6abd02583792c785953c
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597061"
---
# <a name="reduced-motion-simulation"></a>减少运动模拟  

Web 产品中的动画可能是一个辅助功能问题。  操作系统通过包括关闭动画的选项来解决此问题，以避免用户混淆和潜在的健康相关问题，例如触发癫痫。  

在网页上，您可以使用 [首选的减少运动][MDNPrefersReducedMotion] CSS 媒体查询来检测用户是否喜欢显示任何动画。  然后在测试中包装动画代码，以有条件地运行动画。  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
    animation: none;
  }
}
```  

然后测试代码，如下所示。

若要模拟操作系统的缩减运动设置，而无需更改操作系统设置：

1.  打开“**命令菜单**”。  
    1.  在 `Control` + `Shift` + `P` Windows/Linux 或 `Command` + `Shift` + `P` macOS 上选择。  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           **命令菜单**  
        :::image-end:::  
        
1.  键入 `reduced` ，以打开和关闭模拟。  选择该选项，然后选择 `Enter` 。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="从命令菜单打开或关闭首选的减少运动设置" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       从命令菜单打开或 **关闭首选的** 减少 **运动设置**  
    :::image-end:::  
    
1.  刷新网页并检查动画是否运行。


## <a name="see-also"></a>另请参阅

* [验证页面是否可用，](test-reduced-ui-motion.md) 关闭 UI 动画 - 使用演示页面的演练，并给出说明。

    
<!-- links -->  
[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
[MDNPrefersReducedMotion]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-reduced-motion "prefers-reduced-motion |MDN"  
