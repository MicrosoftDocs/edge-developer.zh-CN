---
title: Simulate reduced motion using developer tools (CSS Prefers Reduced Motion)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: f1bf90de4ac1832fff07e9ac963c26f92adeea2c
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "10843982"
---
# <span data-ttu-id="5dcd5-103">Reduced Motion Simulation</span><span class="sxs-lookup"><span data-stu-id="5dcd5-103">Reduced Motion Simulation</span></span>  

<span data-ttu-id="5dcd5-104">Animation in web products may be an accessibility problem.</span><span class="sxs-lookup"><span data-stu-id="5dcd5-104">Animation in web products may be an accessibility problem.</span></span>  <span data-ttu-id="5dcd5-105">Operating Systems deal with the problem by including an option to turn off animations to avoid user confusion and potential health related problems such as triggering seizures.</span><span class="sxs-lookup"><span data-stu-id="5dcd5-105">Operating Systems deal with the problem by including an option to turn off animations to avoid user confusion and potential health related problems such as triggering seizures.</span></span>  <span data-ttu-id="5dcd5-106">On the web, you may use the [prefers-reduced-motion][MDNPrefersReducedMotion] CSS Media Query to detect if users prefer to not see any animations.</span><span class="sxs-lookup"><span data-stu-id="5dcd5-106">On the web, you may use the [prefers-reduced-motion][MDNPrefersReducedMotion] CSS Media Query to detect if users prefer to not see any animations.</span></span>  <span data-ttu-id="5dcd5-107">In your product, you may wrap your animation code in a test to avoid animations showing up for the affected users.</span><span class="sxs-lookup"><span data-stu-id="5dcd5-107">In your product, you may wrap your animation code in a test to avoid animations showing up for the affected users.</span></span>  

```css
@media (prefers-reduced-motion: reduce) {
  /* in case the .header element has an animation, turn it off */
  .header {
    animation: none;
  }
}
```  

<span data-ttu-id="5dcd5-108">Using the [Microsoft Edge DevTools][DevtoolsGuideChromiumMain], you may simulate this reduced motion setting without having to change your operating system.</span><span class="sxs-lookup"><span data-stu-id="5dcd5-108">Using the [Microsoft Edge DevTools][DevtoolsGuideChromiumMain], you may simulate this reduced motion setting without having to change your operating system.</span></span>  

1.  <span data-ttu-id="5dcd5-109">Open the **Command Menu**.</span><span class="sxs-lookup"><span data-stu-id="5dcd5-109">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="5dcd5-110">Press `Control`+`Shift`+`P`  on Windows or `Command`+`Shift`+`P` on macOS.</span><span class="sxs-lookup"><span data-stu-id="5dcd5-110">Press `Control`+`Shift`+`P`  on Windows or `Command`+`Shift`+`P` on macOS.</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="The Command Menu" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="5dcd5-112">The **Command Menu**</span><span class="sxs-lookup"><span data-stu-id="5dcd5-112">The **Command Menu**</span></span>  
        :::image-end:::   
        
1.  <span data-ttu-id="5dcd5-113">Type `reduced`, to turn the simulation on and off.</span><span class="sxs-lookup"><span data-stu-id="5dcd5-113">Type `reduced`, to turn the simulation on and off.</span></span>  <span data-ttu-id="5dcd5-114">Select the option and press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="5dcd5-114">Select the option and press `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png" alt-text="The Command Menu" lightbox="../media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png":::
       <span data-ttu-id="5dcd5-116">Turn on or off the **prefers reduced motion** setting from **Command Menu**</span><span class="sxs-lookup"><span data-stu-id="5dcd5-116">Turn on or off the **prefers reduced motion** setting from **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5dcd5-117">Refresh the current page to test whether your animations are turned off or visible.</span><span class="sxs-lookup"><span data-stu-id="5dcd5-117">Refresh the current page to test whether your animations are turned off or visible.</span></span>  
    
<!-- image links -->  

[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-console-command-menu-rendering.msft.png "Figure 1: The Command Menu"  
[ImageToggleReducedMotionFromCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-qs-select-reduced-motion-command-menu.msft.png "Figure 2: Toggle reduced motion from command palette"

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) Developer Tools  Microsoft | Microsoft Docs"  

[MDNPrefersReducedMotion]: https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion "prefers-reduced-motion | MDN"  
