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
# <a name="reduced-motion-simulation"></a><span data-ttu-id="eb602-104">减少运动模拟</span><span class="sxs-lookup"><span data-stu-id="eb602-104">Reduced motion simulation</span></span>  

<span data-ttu-id="eb602-105">Web 产品中的动画可能是一个辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="eb602-105">Animation in web products may be an accessibility problem.</span></span>  <span data-ttu-id="eb602-106">操作系统通过包括关闭动画的选项来解决此问题，以避免用户混淆和潜在的健康相关问题，例如触发癫痫。</span><span class="sxs-lookup"><span data-stu-id="eb602-106">Operating systems deal with this problem by including an option to turn off animations to avoid user confusion and potential health-related problems, such as triggering seizures.</span></span>  

<span data-ttu-id="eb602-107">在网页上，您可以使用 [首选的减少运动][MDNPrefersReducedMotion] CSS 媒体查询来检测用户是否喜欢显示任何动画。</span><span class="sxs-lookup"><span data-stu-id="eb602-107">On a webpage, you can use the [prefers-reduced-motion][MDNPrefersReducedMotion] CSS media query to detect whether the user prefers to display any animations.</span></span>  <span data-ttu-id="eb602-108">然后在测试中包装动画代码，以有条件地运行动画。</span><span class="sxs-lookup"><span data-stu-id="eb602-108">Then wrap your animation code in a test, to conditionally run animations.</span></span>  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
    animation: none;
  }
}
```  

<span data-ttu-id="eb602-109">然后测试代码，如下所示。</span><span class="sxs-lookup"><span data-stu-id="eb602-109">Then test your code, as follows.</span></span>

<span data-ttu-id="eb602-110">若要模拟操作系统的缩减运动设置，而无需更改操作系统设置：</span><span class="sxs-lookup"><span data-stu-id="eb602-110">To simulate the operating system's reduced motion setting, without having to change your operating system setting:</span></span>

1.  <span data-ttu-id="eb602-111">打开“**命令菜单**”。</span><span class="sxs-lookup"><span data-stu-id="eb602-111">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="eb602-112">在 `Control` + `Shift` + `P` Windows/Linux 或 `Command` + `Shift` + `P` macOS 上选择。</span><span class="sxs-lookup"><span data-stu-id="eb602-112">Select `Control`+`Shift`+`P` on Windows/Linux or `Command`+`Shift`+`P` on macOS.</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="eb602-114">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="eb602-114">The **Command Menu**</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="eb602-115">键入 `reduced` ，以打开和关闭模拟。</span><span class="sxs-lookup"><span data-stu-id="eb602-115">Type `reduced`, to turn the simulation on and off.</span></span>  <span data-ttu-id="eb602-116">选择该选项，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="eb602-116">Choose the option and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="从命令菜单打开或关闭首选的减少运动设置" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       <span data-ttu-id="eb602-118">从命令菜单打开或 **关闭首选的** 减少 **运动设置**</span><span class="sxs-lookup"><span data-stu-id="eb602-118">Turn on or off the **prefers reduced motion** setting from **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="eb602-119">刷新网页并检查动画是否运行。</span><span class="sxs-lookup"><span data-stu-id="eb602-119">Refresh the webpage and check whether your animations run.</span></span>


## <a name="see-also"></a><span data-ttu-id="eb602-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb602-120">See also</span></span>

* <span data-ttu-id="eb602-121">[验证页面是否可用，](test-reduced-ui-motion.md) 关闭 UI 动画 - 使用演示页面的演练，并给出说明。</span><span class="sxs-lookup"><span data-stu-id="eb602-121">[Verify that the page is usable with UI animation turned off](test-reduced-ui-motion.md) - A walkthrough using a demo page, with explanations.</span></span>

    
<!-- links -->  
[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
[MDNPrefersReducedMotion]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-reduced-motion "prefers-reduced-motion |MDN"  
