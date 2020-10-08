---
title: 使用开发工具 (，使用 CSS 更喜欢减少运动) 来模拟减少的运动
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f1bf90de4ac1832fff07e9ac963c26f92adeea2c
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "10843982"
---
# <span data-ttu-id="dc42c-103">减少了运动模拟</span><span class="sxs-lookup"><span data-stu-id="dc42c-103">Reduced Motion Simulation</span></span>  

<span data-ttu-id="dc42c-104">Web 产品中的动画可能是辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="dc42c-104">Animation in web products may be an accessibility problem.</span></span>  <span data-ttu-id="dc42c-105">操作系统通过包括用于关闭动画的选项来处理问题，以避免用户混淆和潜在的与运行状况相关的问题，如触发病情发作。</span><span class="sxs-lookup"><span data-stu-id="dc42c-105">Operating Systems deal with the problem by including an option to turn off animations to avoid user confusion and potential health related problems such as triggering seizures.</span></span>  <span data-ttu-id="dc42c-106">在 web 上，你可以使用 "按 [优先减少的动画][MDNPrefersReducedMotion] " CSS 媒体查询来检测用户是否希望看不到任何动画。</span><span class="sxs-lookup"><span data-stu-id="dc42c-106">On the web, you may use the [prefers-reduced-motion][MDNPrefersReducedMotion] CSS Media Query to detect if users prefer to not see any animations.</span></span>  <span data-ttu-id="dc42c-107">在你的产品中，你可以在测试中包装动画代码，以避免针对受影响的用户显示动画。</span><span class="sxs-lookup"><span data-stu-id="dc42c-107">In your product, you may wrap your animation code in a test to avoid animations showing up for the affected users.</span></span>  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
    animation: none;
  }
}
```  

<span data-ttu-id="dc42c-108">使用 [Microsoft Edge DevTools][DevtoolsGuideChromiumMain]，您可以模拟此 "减少的动作" 设置，而无需更改操作系统。</span><span class="sxs-lookup"><span data-stu-id="dc42c-108">Using the [Microsoft Edge DevTools][DevtoolsGuideChromiumMain], you may simulate this reduced motion setting without having to change your operating system.</span></span>  

1.  <span data-ttu-id="dc42c-109">打开 " **命令" 菜单**。</span><span class="sxs-lookup"><span data-stu-id="dc42c-109">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="dc42c-110">按 `Control` + `Shift` + `P` Windows 或 `Command` + `Shift` + `P` macOS。</span><span class="sxs-lookup"><span data-stu-id="dc42c-110">Press `Control`+`Shift`+`P`  on Windows or `Command`+`Shift`+`P` on macOS.</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="dc42c-112">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="dc42c-112">The **Command Menu**</span></span>  
        :::image-end:::   
        
1.  <span data-ttu-id="dc42c-113">键入 `reduced` ，打开和关闭模拟。</span><span class="sxs-lookup"><span data-stu-id="dc42c-113">Type `reduced`, to turn the simulation on and off.</span></span>  <span data-ttu-id="dc42c-114">选择 "" 选项，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="dc42c-114">Select the option and press `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="命令菜单" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       <span data-ttu-id="dc42c-116">打开或关闭 "**命令" 菜单**中的 "**优先减少动作**" 设置</span><span class="sxs-lookup"><span data-stu-id="dc42c-116">Turn on or off the **prefers reduced motion** setting from **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="dc42c-117">刷新当前页以测试动画是否处于关闭状态或是否可见。</span><span class="sxs-lookup"><span data-stu-id="dc42c-117">Refresh the current page to test whether your animations are turned off or visible.</span></span>  
    
<!-- image links -->  

[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-console-command-menu-rendering.msft.png "图1：命令菜单"  
[ImageToggleReducedMotionFromCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png "图2：切换从命令调色板缩小运动"

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发人员工具 Microsoft |Microsoft 文档"  

[MDNPrefersReducedMotion]: https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion "首选-减少-运动 |MDN"  
