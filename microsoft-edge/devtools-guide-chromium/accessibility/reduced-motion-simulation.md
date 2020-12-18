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
# <span data-ttu-id="86770-104">减少运动模拟</span><span class="sxs-lookup"><span data-stu-id="86770-104">Reduced Motion Simulation</span></span>  

<span data-ttu-id="86770-105">Web 产品中动画可能是一个辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="86770-105">Animation in web products may be an accessibility problem.</span></span>  <span data-ttu-id="86770-106">操作系统通过包括关闭动画的选项来处理该问题，以避免用户混淆和潜在的健康相关问题（如触发癫痫）。</span><span class="sxs-lookup"><span data-stu-id="86770-106">Operating Systems deal with the problem by including an option to turn off animations to avoid user confusion and potential health related problems such as triggering seizures.</span></span>  <span data-ttu-id="86770-107">在 Web 上，可以使用首选的减少 [运动][MDNPrefersReducedMotion] CSS 媒体查询来检测用户是否不希望看到任何动画。</span><span class="sxs-lookup"><span data-stu-id="86770-107">On the web, you may use the [prefers-reduced-motion][MDNPrefersReducedMotion] CSS Media Query to detect if users prefer to not see any animations.</span></span>  <span data-ttu-id="86770-108">在你的产品中，你可以将动画代码包装在测试中，以避免向受影响的用户显示动画。</span><span class="sxs-lookup"><span data-stu-id="86770-108">In your product, you may wrap your animation code in a test to avoid animations showing up for the affected users.</span></span>  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
    animation: none;
  }
}
```  

<span data-ttu-id="86770-109">使用 [Microsoft Edge DevTools，][DevtoolsIndex]你可以模拟这种减少的运动设置，而无需更改操作系统。</span><span class="sxs-lookup"><span data-stu-id="86770-109">Using the [Microsoft Edge DevTools][DevtoolsIndex], you may simulate this reduced motion setting without having to change your operating system.</span></span>  

1.  <span data-ttu-id="86770-110">打开 **命令菜单**。</span><span class="sxs-lookup"><span data-stu-id="86770-110">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="86770-111">在 `Control` + `Shift` + `P` Windows/Linux 或 `Command` + `Shift` + `P` macOS 上选择。</span><span class="sxs-lookup"><span data-stu-id="86770-111">Select `Control`+`Shift`+`P` on Windows/Linux or `Command`+`Shift`+`P` on macOS.</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="86770-113">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="86770-113">The **Command Menu**</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="86770-114">键入 `reduced` ，以打开和关闭模拟。</span><span class="sxs-lookup"><span data-stu-id="86770-114">Type `reduced`, to turn the simulation on and off.</span></span>  <span data-ttu-id="86770-115">选择该选项并选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="86770-115">Choose the option and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="从命令菜单打开或关闭首选的减少运动设置" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       <span data-ttu-id="86770-117">从命令菜单打开或关闭首选 **的** 减少 **运动设置**</span><span class="sxs-lookup"><span data-stu-id="86770-117">Turn on or off the **prefers reduced motion** setting from **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="86770-118">刷新当前页面以测试动画是关闭还是可见。</span><span class="sxs-lookup"><span data-stu-id="86770-118">Refresh the current page to test whether your animations are turned off or visible.</span></span>  
    
<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 |Microsoft Docs"  

[MDNPrefersReducedMotion]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-reduced-motion "prefers-reduced-motion |MDN"  
