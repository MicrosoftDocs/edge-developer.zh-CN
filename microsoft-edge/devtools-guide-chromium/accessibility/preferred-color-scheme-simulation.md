---
Description: 强制 Microsoft Edge DevTools 进入配色方案预览模式。
title: '强制 Microsoft Edge DevTools 进入配色方案预览模式 (CSS 首选配色) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 29b0121a616a037fa11b61799efeffd201eb1821
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230794"
---
# <span data-ttu-id="45755-104">深色或浅色配色方案模拟</span><span class="sxs-lookup"><span data-stu-id="45755-104">Dark or Light Color Scheme simulation</span></span>  

<span data-ttu-id="45755-105">操作系统具有一种以较深或更浅的颜色显示任何应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="45755-105">Operating systems have a way to display any application in darker or lighter colors.</span></span>  <span data-ttu-id="45755-106">在深色模式操作系统中具有浅色主题的 Web 产品是一种光栅，并且对于一些用户来说可能是一个辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="45755-106">Having a web product that has a light theme in a dark mode operating system is grating and can be an accessibility issue for some users.</span></span>  <span data-ttu-id="45755-107">在 Web 上，可以使用首选配色 [方案][MDNPrefersColorScheme] CSS 媒体查询来检测用户是否希望以较暗或较浅的配色方案查看你的产品。</span><span class="sxs-lookup"><span data-stu-id="45755-107">On the web, you may use the [prefers-color-scheme][MDNPrefersColorScheme] CSS Media Query to detect if users prefer to see your product in a darker or lighter colour scheme.</span></span>  <span data-ttu-id="45755-108">使用 [Microsoft Edge DevTools][DevtoolsGuideChromiumMain] 模拟从深色模式到浅色模式的变化，而无需更改整个操作系统。</span><span class="sxs-lookup"><span data-stu-id="45755-108">Use [Microsoft Edge DevTools][DevtoolsGuideChromiumMain] to simulate a change from dark to light mode without having to change the entire operating system.</span></span>  

1.  <span data-ttu-id="45755-109">打开命令 **菜单**。</span><span class="sxs-lookup"><span data-stu-id="45755-109">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="45755-110">在 `Control` + `Shift` + `P` Windows/Linux 或 `Command` + `Shift` + `P` macOS 上选择。</span><span class="sxs-lookup"><span data-stu-id="45755-110">Select `Control`+`Shift`+`P`  on Windows/Linux or `Command`+`Shift`+`P` on macOS.</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="45755-112">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="45755-112">The **Command Menu**</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="45755-113">键入 `emulate color` ，选择" **模拟 CSS 首选-配色方案：** 深色"或"模拟 CSS **首选配色方案：浅** 色"，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="45755-113">Type `emulate color`, choose either **Emulate CSS prefers-color-scheme: dark** or **Emulate CSS prefers-color-scheme: light** and then select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png" alt-text="命令菜单中的配色方案选项" lightbox="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png":::
       <span data-ttu-id="45755-115">命令菜单中的 **配色方案** 选项</span><span class="sxs-lookup"><span data-stu-id="45755-115">Color scheme option from **Command** Menu</span></span>  
    :::image-end:::  
    
    > [!IMPORTANT]
    > <span data-ttu-id="45755-116">只需键入或不显示正确的工具，因为还有一种方法可以选择 `dark` `light` [DevTools 的主题][DevtoolsGuideChromiumCustomizeDarkTheme]。</span><span class="sxs-lookup"><span data-stu-id="45755-116">Simply typing `dark` or `light` does not reveal the right tool, since there is also a way to [choose a theme for DevTools][DevtoolsGuideChromiumCustomizeDarkTheme].</span></span>  <span data-ttu-id="45755-117">如果想知道要选择什么，请确保选择的是呈现菜单项，而不是**外观**菜单项\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45755-117">If you are wondering what to choose, make sure that you are choosing a **rendering** menu item, not an **appearance** menu item.</span></span>  

1.  <span data-ttu-id="45755-118">选择配色方案后，重新加载当前文档以查看模拟模式。</span><span class="sxs-lookup"><span data-stu-id="45755-118">After you choose a color scheme, reload the current document to see the simulated mode.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-simulated-light-mode.msft.png" alt-text="Microsoft Edge DevTools 内的模拟光模式" lightbox="../media/css-elements-styles-qs-simulated-light-mode.msft.png":::
       <span data-ttu-id="45755-120">Microsoft Edge DevTools 内的模拟光模式</span><span class="sxs-lookup"><span data-stu-id="45755-120">Simulated light mode inside Microsoft Edge DevTools</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="45755-121">像查看和更改任何其他网页一样查看和更改 CSS。</span><span class="sxs-lookup"><span data-stu-id="45755-121">View and change your CSS like any other web page.</span></span>  <span data-ttu-id="45755-122">有关详细信息，请参阅["查看和更改 CSS 入门"。][DevtoolsGuideChromiumCssIndex]</span><span class="sxs-lookup"><span data-stu-id="45755-122">For more information, see [Get Started With Viewing And Changing CSS][DevtoolsGuideChromiumCssIndex].</span></span>  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 |Microsoft Docs"  
[DevtoolsGuideChromiumCustomizeDarkTheme]: ../customize/dark-theme.md "在 Microsoft Edge DevTools 中启用深色主题 |Microsoft Docs"
[DevtoolsGuideChromiumCssIndex]: ../css/index.md "查看和更改 CSS 入门 |Microsoft Docs"  

[MDNPrefersColorScheme]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-color-scheme "prefers-color-scheme |MDN"  
