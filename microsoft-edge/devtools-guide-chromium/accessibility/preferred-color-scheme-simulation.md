---
description: 强制 Microsoft Edge DevTools 进入配色方案预览模式。
title: '强制 Microsoft Edge DevTools 进入配色方案预览模式 (CSS 首选配色) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 84f482605acd6edab6829e00d5fa31f927ebc032
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398299"
---
# <a name="dark-or-light-color-scheme-simulation"></a><span data-ttu-id="e6c2a-104">深色或浅色配色方案模拟</span><span class="sxs-lookup"><span data-stu-id="e6c2a-104">Dark or Light Color Scheme simulation</span></span>  

<span data-ttu-id="e6c2a-105">操作系统具有一种以较暗或更浅的颜色显示任何应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="e6c2a-105">Operating systems have a way to display any application in darker or lighter colors.</span></span>  <span data-ttu-id="e6c2a-106">在深色模式下的操作系统中具有浅色主题的 Web 产品是一种光主题，这一点对于一些用户来说可能是一个辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="e6c2a-106">Having a web product that has a light theme in a dark mode operating system is grating and can be an accessibility issue for some users.</span></span>  <span data-ttu-id="e6c2a-107">在 Web 上，可以使用首选配色方案 [CSS][MDNPrefersColorScheme] 媒体查询来检测用户是否希望以更暗或更浅的颜色方案显示你的产品。</span><span class="sxs-lookup"><span data-stu-id="e6c2a-107">On the web, you may use the [prefers-color-scheme][MDNPrefersColorScheme] CSS Media Query to detect if users prefer to display your product in a darker or lighter colour scheme.</span></span>  <span data-ttu-id="e6c2a-108">使用 [Microsoft Edge DevTools][DevtoolsIndex] 模拟从深色模式更改为浅色模式，而无需更改整个操作系统。</span><span class="sxs-lookup"><span data-stu-id="e6c2a-108">Use [Microsoft Edge DevTools][DevtoolsIndex] to simulate a change from dark to light mode without having to change the entire operating system.</span></span>  

1.  <span data-ttu-id="e6c2a-109">打开“**命令菜单**”。</span><span class="sxs-lookup"><span data-stu-id="e6c2a-109">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="e6c2a-110">选择 `Control` + `Shift` + `P` \(Windows/Linux\) `Command` + `Shift` + `P` 或 \(macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="e6c2a-110">Select `Control`+`Shift`+`P` \(Windows/Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="e6c2a-112">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="e6c2a-112">The **Command Menu**</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="e6c2a-113">键入 `emulate color` ，选择 **"模拟 CSS 首选配色方案：深色** "或" **模拟 CSS 首选配色方案：浅** 色"，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="e6c2a-113">Type `emulate color`, choose either **Emulate CSS prefers-color-scheme: dark** or **Emulate CSS prefers-color-scheme: light** and then select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png" alt-text="命令菜单中的配色方案选项" lightbox="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png":::
       <span data-ttu-id="e6c2a-115">命令菜单中的 **配色方案** 选项</span><span class="sxs-lookup"><span data-stu-id="e6c2a-115">Color scheme option from **Command** Menu</span></span>  
    :::image-end:::  
    
    > [!IMPORTANT]
    > <span data-ttu-id="e6c2a-116">只需键入或不显示正确的工具，因为还有一种方法可以选择 `dark` `light` [DevTools 的主题][DevtoolsCustomizeDarkTheme]。</span><span class="sxs-lookup"><span data-stu-id="e6c2a-116">Simply typing `dark` or `light` does not reveal the right tool, since there is also a way to [choose a theme for DevTools][DevtoolsCustomizeDarkTheme].</span></span>  <span data-ttu-id="e6c2a-117">如果想知道选择什么，请确保选择的是呈现菜单项，而不是**外观**菜单项。 </span><span class="sxs-lookup"><span data-stu-id="e6c2a-117">If you are wondering what to choose, make sure that you are choosing a **rendering** menu item, not an **appearance** menu item.</span></span>  

1.  <span data-ttu-id="e6c2a-118">选择配色方案后，刷新当前文档以显示模拟模式。</span><span class="sxs-lookup"><span data-stu-id="e6c2a-118">After you choose a color scheme, refresh the current document to display the simulated mode.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-simulated-light-mode.msft.png" alt-text="Microsoft Edge DevTools 内的模拟光模式" lightbox="../media/css-elements-styles-qs-simulated-light-mode.msft.png":::
       <span data-ttu-id="e6c2a-120">Microsoft Edge DevTools 内的模拟光模式</span><span class="sxs-lookup"><span data-stu-id="e6c2a-120">Simulated light mode inside Microsoft Edge DevTools</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="e6c2a-121">像查看任何其他网页一样查看和更改 CSS。</span><span class="sxs-lookup"><span data-stu-id="e6c2a-121">View and change your CSS like any other web page.</span></span>  <span data-ttu-id="e6c2a-122">有关详细信息，请导航到["查看和更改 CSS 入门"。][DevtoolsCssIndex]</span><span class="sxs-lookup"><span data-stu-id="e6c2a-122">For more information, navigate to [Get Started With Viewing And Changing CSS][DevtoolsCssIndex].</span></span>  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  
[DevtoolsCustomizeDarkTheme]: ../customize/dark-theme.md "在 Microsoft Edge DevTools |Microsoft Docs"
[DevtoolsCssIndex]: ../css/index.md "查看和更改 CSS 入门 | Microsoft 文档"  

[MDNPrefersColorScheme]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-color-scheme "prefers-color-scheme |MDN"  
