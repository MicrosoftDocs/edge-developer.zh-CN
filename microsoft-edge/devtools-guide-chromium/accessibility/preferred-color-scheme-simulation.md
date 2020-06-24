---
title: 强制 Microsoft Edge DevTools 进入配色方案预览模式（CSS 首选配色方案）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: a83284b676ad388114a4a0ddb7ebdf2203ebcb90
ms.sourcegitcommit: d7fdb67df0fe73fa5ae96e5a69a847d07941d0a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "10758061"
---
# <span data-ttu-id="c3969-103">深色或浅色配色方案模拟</span><span class="sxs-lookup"><span data-stu-id="c3969-103">Dark or Light Color Scheme simulation</span></span>  

<span data-ttu-id="c3969-104">操作系统可以以较暗或较亮的颜色显示任何应用程序。</span><span class="sxs-lookup"><span data-stu-id="c3969-104">Operating systems have a way to display any application in darker or lighter colors.</span></span>  <span data-ttu-id="c3969-105">在深色模式操作系统中拥有具有浅色主题的 web 产品是 grating，并且可能是某些用户的辅助功能问题。</span><span class="sxs-lookup"><span data-stu-id="c3969-105">Having a web product that has a light theme in a dark mode operating system is grating and can be an accessibility issue for some users.</span></span>  <span data-ttu-id="c3969-106">在 web 上，你可以使用[喜欢的配色方案][MDNPrefersColorScheme]CSS 媒体查询来检测用户是否希望在较暗或更亮的颜色方案中查看你的产品。</span><span class="sxs-lookup"><span data-stu-id="c3969-106">On the web, you may use the [prefers-color-scheme][MDNPrefersColorScheme] CSS Media Query to detect if users prefer to see your product in a darker or lighter colour scheme.</span></span>  <span data-ttu-id="c3969-107">使用[Microsoft Edge DevTools][DevtoolsGuideChromiumMain]模拟从深色到浅色模式的更改，而无需更改整个操作系统。</span><span class="sxs-lookup"><span data-stu-id="c3969-107">Use [Microsoft Edge DevTools][DevtoolsGuideChromiumMain] to simulate a change from dark to light mode without having to change the entire operating system.</span></span>  

1.  <span data-ttu-id="c3969-108">打开 "**命令" 菜单**。</span><span class="sxs-lookup"><span data-stu-id="c3969-108">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="c3969-109">按 `Control` + `Shift` + `P` Windows 或 `Command` + `Shift` + `P` macOS。</span><span class="sxs-lookup"><span data-stu-id="c3969-109">Press `Control`+`Shift`+`P`  on Windows or `Command`+`Shift`+`P` on macOS.</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="c3969-111">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="c3969-111">The **Command Menu**</span></span>  
        :::image-end:::   
        
1.  <span data-ttu-id="c3969-112">类型 `emulate color` ，请选择 "**模拟 css 首选色"-颜色方案： "深色**" 或 "**模拟 css 首选色"-颜色方案： "浅色**"，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="c3969-112">Type `emulate color`, select either **Emulate CSS prefers-color-scheme: dark** or **Emulate CSS prefers-color-scheme: light**  and then press `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png" alt-text="从 "命令" 菜单中选择的配色方案" lightbox="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png":::
       <span data-ttu-id="c3969-114">从 "**命令**" 菜单中选择的配色方案</span><span class="sxs-lookup"><span data-stu-id="c3969-114">Color scheme selection from **Command** Menu</span></span>  
    :::image-end:::  
    
    > [!IMPORTANT]
    > <span data-ttu-id="c3969-115">只需键入 `dark` 或 `light` 不显示正确的工具，因为还有一种方法可为[DevTools 选择主题][DevtoolsGuideChromiumCustomizeDarkTheme]。</span><span class="sxs-lookup"><span data-stu-id="c3969-115">Simply typing `dark` or `light` does not reveal the right tool, since there is also a way to [choose a theme for DevTools][DevtoolsGuideChromiumCustomizeDarkTheme].</span></span>  <span data-ttu-id="c3969-116">如果您想要选择哪些内容，请确保您选择的是 "**呈现**" 菜单项，而不是 "**外观**" 菜单项。</span><span class="sxs-lookup"><span data-stu-id="c3969-116">If you are wondering what to choose, make sure that you are selecting a **rendering** menu item, not an **appearance** menu item.</span></span>  

1.  <span data-ttu-id="c3969-117">选择配色方案后，重新加载当前文档以查看模拟模式。</span><span class="sxs-lookup"><span data-stu-id="c3969-117">After you select a color scheme, reload the current document to see the simulated mode.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-simulated-light-mode.msft.png" alt-text="Microsoft Edge DevTools 中的模拟轻型模式" lightbox="../media/css-elements-styles-qs-simulated-light-mode.msft.png":::
       <span data-ttu-id="c3969-119">Microsoft Edge DevTools 中的模拟轻型模式</span><span class="sxs-lookup"><span data-stu-id="c3969-119">Simulated light mode inside Microsoft Edge DevTools</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="c3969-120">像查看其他网页一样查看和更改您的 CSS。</span><span class="sxs-lookup"><span data-stu-id="c3969-120">View and change your CSS like any other web page.</span></span>  <span data-ttu-id="c3969-121">有关详细信息，请参阅[查看和更改 CSS 入门][DevtoolsGuideChromiumCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="c3969-121">For more information, see [Get Started With Viewing And Changing CSS][DevtoolsGuideChromiumCssIndex].</span></span>  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge （Chromium）开发人员工具 Microsoft |Microsoft 文档"  
[DevtoolsGuideChromiumCustomizeDarkTheme]: ../customize/dark-theme.md "在 Microsoft Edge DevTools 中启用深色主题 |Microsoft 文档"
[DevtoolsGuideChromiumCssIndex]: ../css/index.md "开始使用查看和更改 CSS |Microsoft 文档"  

[MDNPrefersColorScheme]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-color-scheme "首选-配色方案 |MDN"  
