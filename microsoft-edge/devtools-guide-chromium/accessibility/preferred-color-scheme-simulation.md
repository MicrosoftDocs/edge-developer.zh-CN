---
title: Force Microsoft Edge DevTools Into Color Scheme Preview Mode (CSS Prefers Color Scheme)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: a83284b676ad388114a4a0ddb7ebdf2203ebcb90
ms.sourcegitcommit: d7fdb67df0fe73fa5ae96e5a69a847d07941d0a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "10758061"
---
# <span data-ttu-id="c5df3-103">Dark or Light Color Scheme simulation</span><span class="sxs-lookup"><span data-stu-id="c5df3-103">Dark or Light Color Scheme simulation</span></span>  

<span data-ttu-id="c5df3-104">Operating systems have a way to display any application in darker or lighter colors.</span><span class="sxs-lookup"><span data-stu-id="c5df3-104">Operating systems have a way to display any application in darker or lighter colors.</span></span>  <span data-ttu-id="c5df3-105">Having a web product that has a light theme in a dark mode operating system is grating and can be an accessibility issue for some users.</span><span class="sxs-lookup"><span data-stu-id="c5df3-105">Having a web product that has a light theme in a dark mode operating system is grating and can be an accessibility issue for some users.</span></span>  <span data-ttu-id="c5df3-106">On the web, you may use the [prefers-color-scheme][MDNPrefersColorScheme] CSS Media Query to detect if users prefer to see your product in a darker or lighter colour scheme.</span><span class="sxs-lookup"><span data-stu-id="c5df3-106">On the web, you may use the [prefers-color-scheme][MDNPrefersColorScheme] CSS Media Query to detect if users prefer to see your product in a darker or lighter colour scheme.</span></span>  <span data-ttu-id="c5df3-107">Use [Microsoft Edge DevTools][DevtoolsGuideChromiumMain] to simulate a change from dark to light mode without having to change the entire operating system.</span><span class="sxs-lookup"><span data-stu-id="c5df3-107">Use [Microsoft Edge DevTools][DevtoolsGuideChromiumMain] to simulate a change from dark to light mode without having to change the entire operating system.</span></span>  

1.  <span data-ttu-id="c5df3-108">Open the **Command Menu**.</span><span class="sxs-lookup"><span data-stu-id="c5df3-108">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="c5df3-109">Press `Control`+`Shift`+`P`  on Windows or `Command`+`Shift`+`P` on macOS.</span><span class="sxs-lookup"><span data-stu-id="c5df3-109">Press `Control`+`Shift`+`P`  on Windows or `Command`+`Shift`+`P` on macOS.</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="The Command Menu" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="c5df3-111">The **Command Menu**</span><span class="sxs-lookup"><span data-stu-id="c5df3-111">The **Command Menu**</span></span>  
        :::image-end:::   
        
1.  <span data-ttu-id="c5df3-112">Type `emulate color`, select either **Emulate CSS prefers-color-scheme: dark** or **Emulate CSS prefers-color-scheme: light**  and then press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="c5df3-112">Type `emulate color`, select either **Emulate CSS prefers-color-scheme: dark** or **Emulate CSS prefers-color-scheme: light**  and then press `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png" alt-text="The Command Menu" lightbox="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png":::
       <span data-ttu-id="c5df3-114">Color scheme selection from **Command** Menu</span><span class="sxs-lookup"><span data-stu-id="c5df3-114">Color scheme selection from **Command** Menu</span></span>  
    :::image-end:::  
    
    > [!IMPORTANT]
    > <span data-ttu-id="c5df3-115">Simply typing `dark` or `light` does not reveal the right tool, since there is also a way to [choose a theme for DevTools][DevtoolsGuideChromiumCustomizeDarkTheme].</span><span class="sxs-lookup"><span data-stu-id="c5df3-115">Simply typing `dark` or `light` does not reveal the right tool, since there is also a way to [choose a theme for DevTools][DevtoolsGuideChromiumCustomizeDarkTheme].</span></span>  <span data-ttu-id="c5df3-116">If you are wondering what to choose, make sure that you are selecting a **rendering** menu item, not an **appearance** menu item.</span><span class="sxs-lookup"><span data-stu-id="c5df3-116">If you are wondering what to choose, make sure that you are selecting a **rendering** menu item, not an **appearance** menu item.</span></span>  

1.  <span data-ttu-id="c5df3-117">After you select a color scheme, reload the current document to see the simulated mode.</span><span class="sxs-lookup"><span data-stu-id="c5df3-117">After you select a color scheme, reload the current document to see the simulated mode.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-simulated-light-mode.msft.png" alt-text="The Command Menu" lightbox="../media/css-elements-styles-qs-simulated-light-mode.msft.png":::
       <span data-ttu-id="c5df3-119">Simulated light mode inside Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="c5df3-119">Simulated light mode inside Microsoft Edge DevTools</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="c5df3-120">View and change your CSS like any other web page.</span><span class="sxs-lookup"><span data-stu-id="c5df3-120">View and change your CSS like any other web page.</span></span>  <span data-ttu-id="c5df3-121">For more information, see [Get Started With Viewing And Changing CSS][DevtoolsGuideChromiumCssIndex].</span><span class="sxs-lookup"><span data-stu-id="c5df3-121">For more information, see [Get Started With Viewing And Changing CSS][DevtoolsGuideChromiumCssIndex].</span></span>  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) Developer Tools  Microsoft | Microsoft Docs"  
[DevtoolsGuideChromiumCustomizeDarkTheme]: ../customize/dark-theme.md "Enable Dark Theme In Microsoft Edge DevTools | Microsoft Docs"
[DevtoolsGuideChromiumCssIndex]: ../css/index.md "Get Started With Viewing And Changing CSS | Microsoft Docs"  

[MDNPrefersColorScheme]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-color-scheme "prefers-color-scheme | MDN"  
