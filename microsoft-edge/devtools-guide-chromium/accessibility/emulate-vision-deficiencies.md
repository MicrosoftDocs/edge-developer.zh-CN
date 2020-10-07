---
title: Emulate vision deficiencies in Microsoft Edge DevTools(color blindness)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: b70499fa189d162fa7589966bab183f4c12f68f7
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "10843919"
---
# <span data-ttu-id="0a5e7-103">Emulate vision deficiencies</span><span class="sxs-lookup"><span data-stu-id="0a5e7-103">Emulate vision deficiencies</span></span>

<span data-ttu-id="0a5e7-104">To better meet the needs of your users with [color vision deficiency][ColorblindawarenessMain] \(color blindness\), [Microsoft Edge DevTools][MicrosoftEdgeDevTools] enable you to simulate specific color vision deficiencies.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-104">To better meet the needs of your users with [color vision deficiency][ColorblindawarenessMain] \(color blindness\), [Microsoft Edge DevTools][MicrosoftEdgeDevTools] enable you to simulate specific color vision deficiencies.</span></span>  <span data-ttu-id="0a5e7-105">The **Emulate vision deficiencies** tool simulates the following categories.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-105">The **Emulate vision deficiencies** tool simulates the following categories.</span></span>  

| <span data-ttu-id="0a5e7-106">Color vision deficiency</span><span class="sxs-lookup"><span data-stu-id="0a5e7-106">Color vision deficiency</span></span> | <span data-ttu-id="0a5e7-107">Details</span><span class="sxs-lookup"><span data-stu-id="0a5e7-107">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="0a5e7-108">Blurred vision</span><span class="sxs-lookup"><span data-stu-id="0a5e7-108">Blurred vision</span></span> | <span data-ttu-id="0a5e7-109">The user has difficulty focusing on fine details.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-109">The user has difficulty focusing on fine details.</span></span> |   
| <span data-ttu-id="0a5e7-110">Protanopia</span><span class="sxs-lookup"><span data-stu-id="0a5e7-110">Protanopia</span></span> | <span data-ttu-id="0a5e7-111">The user is unable to perceive any red light.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-111">The user is unable to perceive any red light.</span></span> |  
| <span data-ttu-id="0a5e7-112">Deuteranopia</span><span class="sxs-lookup"><span data-stu-id="0a5e7-112">Deuteranopia</span></span> | <span data-ttu-id="0a5e7-113">The user is unable to perceive any green light.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-113">The user is unable to perceive any green light.</span></span> |  
| <span data-ttu-id="0a5e7-114">Tritanopia</span><span class="sxs-lookup"><span data-stu-id="0a5e7-114">Tritanopia</span></span> | <span data-ttu-id="0a5e7-115">The user is unable to perceive any blue light.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-115">The user is unable to perceive any blue light.</span></span> |  
| <span data-ttu-id="0a5e7-116">Achromatopsia</span><span class="sxs-lookup"><span data-stu-id="0a5e7-116">Achromatopsia</span></span> | <span data-ttu-id="0a5e7-117">The user is unable to perceive any color, which reduces all color to a shade of grey.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-117">The user is unable to perceive any color, which reduces all color to a shade of grey.</span></span> |  

## <span data-ttu-id="0a5e7-118">Navigate to the Rendering Tools</span><span class="sxs-lookup"><span data-stu-id="0a5e7-118">Navigate to the Rendering Tools</span></span>  

<span data-ttu-id="0a5e7-119">To simulate a vision deficiency being applied for your web product, open the [Rendering Tools][RenderingTools].</span><span class="sxs-lookup"><span data-stu-id="0a5e7-119">To simulate a vision deficiency being applied for your web product, open the [Rendering Tools][RenderingTools].</span></span>  

1.  <span data-ttu-id="0a5e7-120">Open the Rendering Tools by selecting the `...` menu item in the toolbar</span><span class="sxs-lookup"><span data-stu-id="0a5e7-120">Open the Rendering Tools by selecting the `...` menu item in the toolbar</span></span>  
1.  <span data-ttu-id="0a5e7-121">Select</span><span class="sxs-lookup"><span data-stu-id="0a5e7-121">Select</span></span> `More tools`  
1.  <span data-ttu-id="0a5e7-122">Select</span><span class="sxs-lookup"><span data-stu-id="0a5e7-122">Select</span></span> `Rendering`  
    
    :::image type="complex" source="../media/getting-to-the-rendering-tools.msft.png" alt-text="Opening the Rendering Tools" lightbox="../media/getting-to-the-rendering-tools.msft.png":::
       <span data-ttu-id="0a5e7-124">Opening the **Rendering Tools**</span><span class="sxs-lookup"><span data-stu-id="0a5e7-124">Opening the **Rendering Tools**</span></span>  
    :::image-end:::  

<span data-ttu-id="0a5e7-125">The **Rendering** menu appears in the drawer.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-125">The **Rendering** menu appears in the drawer.</span></span>  

1.  <span data-ttu-id="0a5e7-126">Scroll down to the `Emulate vision deficiencies` menu item and select the drop-down menu to display the options.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-126">Scroll down to the `Emulate vision deficiencies` menu item and select the drop-down menu to display the options.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu.msft.png" alt-text="Opening the Rendering Tools" lightbox="../media/accessibility-emulate-vision-menu.msft.png":::
       <span data-ttu-id="0a5e7-128">The **Emulate vision deficiencies** menu on the **Rendering** drawer</span><span class="sxs-lookup"><span data-stu-id="0a5e7-128">The **Emulate vision deficiencies** menu on the **Rendering** drawer</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0a5e7-129">Choose an option.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-129">Choose an option.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu-options.msft.png" alt-text="Opening the Rendering Tools" lightbox="../media/accessibility-emulate-vision-menu-options.msft.png":::
       <span data-ttu-id="0a5e7-131">The **Emulate vision deficiencies** menu options</span><span class="sxs-lookup"><span data-stu-id="0a5e7-131">The **Emulate vision deficiencies** menu options</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0a5e7-132">The main windows displays the simulation of your selected option applied to the current page.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-132">The main windows displays the simulation of your selected option applied to the current page.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-blurred-vision-emulation.msft.png" alt-text="Opening the Rendering Tools" lightbox="../media/accessibility-blurred-vision-emulation.msft.png":::
             <span data-ttu-id="0a5e7-134">Display using **Blurred Vision** simulation</span><span class="sxs-lookup"><span data-stu-id="0a5e7-134">Display using **Blurred Vision** simulation</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-achromatopsia-emulation.msft.png" alt-text="Opening the Rendering Tools" lightbox="../media/accessibility-achromatopsia-emulation.msft.png":::
             <span data-ttu-id="0a5e7-136">Display using **Achromatopsia** simulation</span><span class="sxs-lookup"><span data-stu-id="0a5e7-136">Display using **Achromatopsia** simulation</span></span> :::image-end:::  
       :::column-end:::
    :::row-end:::
    
## <span data-ttu-id="0a5e7-137">Use the Command Menu</span><span class="sxs-lookup"><span data-stu-id="0a5e7-137">Use the Command Menu</span></span>  

<span data-ttu-id="0a5e7-138">You may also use **Command Menu** to access the different simulations.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-138">You may also use **Command Menu** to access the different simulations.</span></span>  

1.  <span data-ttu-id="0a5e7-139">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-139">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="Opening the Rendering Tools" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       <span data-ttu-id="0a5e7-141">The **Command Menu**</span><span class="sxs-lookup"><span data-stu-id="0a5e7-141">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0a5e7-142">Type `emulate`, choose what you want to simulate and press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-142">Type `emulate`, choose what you want to simulate and press `Enter`.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulation-command-menu-results.msft.png" alt-text="Opening the Rendering Tools" lightbox="../media/accessibility-emulation-command-menu-results.msft.png":::
       <span data-ttu-id="0a5e7-144">The different simulation options available in the **Command Menu**</span><span class="sxs-lookup"><span data-stu-id="0a5e7-144">The different simulation options available in the **Command Menu**</span></span>  
    :::image-end:::  
    
> [!IMPORTANT]
> <span data-ttu-id="0a5e7-145">The **Emulate vision deficiencies** tools simulate approximations of how a person with each deficiency may see your product.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-145">The **Emulate vision deficiencies** tools simulate approximations of how a person with each deficiency may see your product.</span></span>  <span data-ttu-id="0a5e7-146">Each person is different, therefore vision deficiencies vary in severity from person to person.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-146">Each person is different, therefore vision deficiencies vary in severity from person to person.</span></span>  <span data-ttu-id="0a5e7-147">To better meet the needs of your users, avoid any color combination that may be an issue.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-147">To better meet the needs of your users, avoid any color combination that may be an issue.</span></span>  <span data-ttu-id="0a5e7-148">The **Emulate vision deficiencies** tools are not a full accessibility assessment of your product.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-148">The **Emulate vision deficiencies** tools are not a full accessibility assessment of your product.</span></span>  <span data-ttu-id="0a5e7-149">Instead, the **Emulate vision deficiencies** tools should  give you a good first step to avoid problems.</span><span class="sxs-lookup"><span data-stu-id="0a5e7-149">Instead, the **Emulate vision deficiencies** tools should  give you a good first step to avoid problems.</span></span>  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) Developer Tools"  
[ColorblindawarenessMain]: http://www.colourblindawareness.org "The Colour Blind Awareness organisation"  
[AmfcbMain]: https://www.amfcb.org "The American Foundation for the Color Blind (AFCB)"  
[RenderingTools]: /microsoft-edge/devtools-guide-chromium/rendering-tools "Microsoft Edge (Chromium) Rendering Tools"  
