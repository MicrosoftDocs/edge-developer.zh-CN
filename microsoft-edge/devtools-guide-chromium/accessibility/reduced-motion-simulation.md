---
description: 使用开发人员工具模拟运动减少。
title: '使用开发人员工具模拟减少 (CSS 首选"减少运动") '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 29cdbd7492665e819315910b3f743d444470cc12
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397865"
---
# <a name="reduced-motion-simulation"></a><span data-ttu-id="c1270-104">减少运动模拟</span><span class="sxs-lookup"><span data-stu-id="c1270-104">Reduced motion simulation</span></span>  

<span data-ttu-id="c1270-105">Web 产品中动画可能是一个辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="c1270-105">Animation in web products may be an accessibility problem.</span></span>  <span data-ttu-id="c1270-106">操作系统通过包括关闭动画的选项来处理该问题，以避免用户混淆和潜在的健康相关问题（如触发癫痫）。</span><span class="sxs-lookup"><span data-stu-id="c1270-106">Operating Systems deal with the problem by including an option to turn off animations to avoid user confusion and potential health related problems such as triggering seizures.</span></span>  <span data-ttu-id="c1270-107">在 Web 上，可以使用 [首选][MDNPrefersReducedMotion] 的减少运动 CSS 媒体查询来检测用户是否不希望运行或显示任何动画。</span><span class="sxs-lookup"><span data-stu-id="c1270-107">On the web, you may use the [prefers-reduced-motion][MDNPrefersReducedMotion] CSS Media Query to detect if users prefer to not run or display any animations.</span></span>  <span data-ttu-id="c1270-108">在你的产品中，你可以将动画代码包装在测试中，以避免向受影响的用户显示动画。</span><span class="sxs-lookup"><span data-stu-id="c1270-108">In your product, you may wrap your animation code in a test to avoid animations showing up for the affected users.</span></span>  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
    animation: none;
  }
}
```  

<span data-ttu-id="c1270-109">使用 [Microsoft Edge DevTools，][DevtoolsIndex]你可以模拟此减少的动作设置，而无需更改操作系统。</span><span class="sxs-lookup"><span data-stu-id="c1270-109">Using the [Microsoft Edge DevTools][DevtoolsIndex], you may simulate this reduced motion setting without having to change your operating system.</span></span>  

1.  <span data-ttu-id="c1270-110">打开“**命令菜单**”。</span><span class="sxs-lookup"><span data-stu-id="c1270-110">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="c1270-111">在 `Control` + `Shift` + `P` Windows/Linux 或 `Command` + `Shift` + `P` macOS 上选择。</span><span class="sxs-lookup"><span data-stu-id="c1270-111">Select `Control`+`Shift`+`P` on Windows/Linux or `Command`+`Shift`+`P` on macOS.</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="c1270-113">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="c1270-113">The **Command Menu**</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="c1270-114">键入 `reduced` ，以打开和关闭模拟。</span><span class="sxs-lookup"><span data-stu-id="c1270-114">Type `reduced`, to turn the simulation on and off.</span></span>  <span data-ttu-id="c1270-115">选择该选项并选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="c1270-115">Choose the option and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="从命令菜单打开或关闭首选的缩减运动设置" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       <span data-ttu-id="c1270-117">从命令菜单打开或关闭首选 **的** 缩减 **运动设置**</span><span class="sxs-lookup"><span data-stu-id="c1270-117">Turn on or off the **prefers reduced motion** setting from **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c1270-118">刷新当前页面以测试动画是关闭还是可见。</span><span class="sxs-lookup"><span data-stu-id="c1270-118">Refresh the current page to test whether your animations are turned off or visible.</span></span>  
    
<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  

[MDNPrefersReducedMotion]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-reduced-motion "prefers-reduced-motion |MDN"  
