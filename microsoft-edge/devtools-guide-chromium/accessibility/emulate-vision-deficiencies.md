---
title: 模仿 Microsoft Edge DevTools 中的视觉缺陷（色盲）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: b70499fa189d162fa7589966bab183f4c12f68f7
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "10843919"
---
# <span data-ttu-id="4b141-103">模仿视觉缺陷</span><span class="sxs-lookup"><span data-stu-id="4b141-103">Emulate vision deficiencies</span></span>

<span data-ttu-id="4b141-104">为了更好地满足用户使用[颜色视觉缺陷][ColorblindawarenessMain]的需要 \ （色盲 \）， [Microsoft Edge DevTools][MicrosoftEdgeDevTools]使你能够模拟特定的颜色视觉缺陷。</span><span class="sxs-lookup"><span data-stu-id="4b141-104">To better meet the needs of your users with [color vision deficiency][ColorblindawarenessMain] \(color blindness\), [Microsoft Edge DevTools][MicrosoftEdgeDevTools] enable you to simulate specific color vision deficiencies.</span></span>  <span data-ttu-id="4b141-105">"**模拟远景缺陷**" 工具模拟以下类别。</span><span class="sxs-lookup"><span data-stu-id="4b141-105">The **Emulate vision deficiencies** tool simulates the following categories.</span></span>  

| <span data-ttu-id="4b141-106">颜色远景缺陷</span><span class="sxs-lookup"><span data-stu-id="4b141-106">Color vision deficiency</span></span> | <span data-ttu-id="4b141-107">详细信息</span><span class="sxs-lookup"><span data-stu-id="4b141-107">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="4b141-108">模糊视觉效果</span><span class="sxs-lookup"><span data-stu-id="4b141-108">Blurred vision</span></span> | <span data-ttu-id="4b141-109">用户很难关注详细信息。</span><span class="sxs-lookup"><span data-stu-id="4b141-109">The user has difficulty focusing on fine details.</span></span> |   
| <span data-ttu-id="4b141-110">Protanopia</span><span class="sxs-lookup"><span data-stu-id="4b141-110">Protanopia</span></span> | <span data-ttu-id="4b141-111">用户无法感知任何红光。</span><span class="sxs-lookup"><span data-stu-id="4b141-111">The user is unable to perceive any red light.</span></span> |  
| <span data-ttu-id="4b141-112">Deuteranopia</span><span class="sxs-lookup"><span data-stu-id="4b141-112">Deuteranopia</span></span> | <span data-ttu-id="4b141-113">用户无法感知任何绿色光。</span><span class="sxs-lookup"><span data-stu-id="4b141-113">The user is unable to perceive any green light.</span></span> |  
| <span data-ttu-id="4b141-114">Tritanopia</span><span class="sxs-lookup"><span data-stu-id="4b141-114">Tritanopia</span></span> | <span data-ttu-id="4b141-115">用户无法感知任何蓝色光线。</span><span class="sxs-lookup"><span data-stu-id="4b141-115">The user is unable to perceive any blue light.</span></span> |  
| <span data-ttu-id="4b141-116">Achromatopsia</span><span class="sxs-lookup"><span data-stu-id="4b141-116">Achromatopsia</span></span> | <span data-ttu-id="4b141-117">用户无法感知任何颜色，这种颜色会将所有颜色降低为灰色底纹。</span><span class="sxs-lookup"><span data-stu-id="4b141-117">The user is unable to perceive any color, which reduces all color to a shade of grey.</span></span> |  

## <span data-ttu-id="4b141-118">导航到 "渲染工具"</span><span class="sxs-lookup"><span data-stu-id="4b141-118">Navigate to the Rendering Tools</span></span>  

<span data-ttu-id="4b141-119">若要模拟为您的 web 产品应用的远景缺陷，请打开 "[渲染工具][RenderingTools]"。</span><span class="sxs-lookup"><span data-stu-id="4b141-119">To simulate a vision deficiency being applied for your web product, open the [Rendering Tools][RenderingTools].</span></span>  

1.  <span data-ttu-id="4b141-120">通过选择 `...` 工具栏中的菜单项打开呈现工具</span><span class="sxs-lookup"><span data-stu-id="4b141-120">Open the Rendering Tools by selecting the `...` menu item in the toolbar</span></span>  
1.  <span data-ttu-id="4b141-121">选择</span><span class="sxs-lookup"><span data-stu-id="4b141-121">Select</span></span> `More tools`  
1.  <span data-ttu-id="4b141-122">选择</span><span class="sxs-lookup"><span data-stu-id="4b141-122">Select</span></span> `Rendering`  
    
    :::image type="complex" source="../media/getting-to-the-rendering-tools.msft.png" alt-text="打开渲染工具" lightbox="../media/getting-to-the-rendering-tools.msft.png":::
       <span data-ttu-id="4b141-124">打开**渲染工具**</span><span class="sxs-lookup"><span data-stu-id="4b141-124">Opening the **Rendering Tools**</span></span>  
    :::image-end:::  

<span data-ttu-id="4b141-125">"**呈现**" 菜单显示在抽屉中。</span><span class="sxs-lookup"><span data-stu-id="4b141-125">The **Rendering** menu appears in the drawer.</span></span>  

1.  <span data-ttu-id="4b141-126">向下滚动到 `Emulate vision deficiencies` 菜单项并选择下拉菜单以显示选项。</span><span class="sxs-lookup"><span data-stu-id="4b141-126">Scroll down to the `Emulate vision deficiencies` menu item and select the drop-down menu to display the options.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu.msft.png" alt-text="呈现抽屉上的 "模拟远景缺陷" 菜单" lightbox="../media/accessibility-emulate-vision-menu.msft.png":::
       <span data-ttu-id="4b141-128">**呈现**抽屉上的 "**模拟远景缺陷**" 菜单</span><span class="sxs-lookup"><span data-stu-id="4b141-128">The **Emulate vision deficiencies** menu on the **Rendering** drawer</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="4b141-129">选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="4b141-129">Choose an option.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu-options.msft.png" alt-text=""模拟远景缺陷" 菜单选项" lightbox="../media/accessibility-emulate-vision-menu-options.msft.png":::
       <span data-ttu-id="4b141-131">"**模拟远景缺陷**" 菜单选项</span><span class="sxs-lookup"><span data-stu-id="4b141-131">The **Emulate vision deficiencies** menu options</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="4b141-132">主窗口显示应用到当前页面的选定选项的模拟。</span><span class="sxs-lookup"><span data-stu-id="4b141-132">The main windows displays the simulation of your selected option applied to the current page.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-blurred-vision-emulation.msft.png" alt-text="使用 \* \* 模糊视觉效果 \* \* 模拟显示" lightbox="../media/accessibility-blurred-vision-emulation.msft.png":::
             <span data-ttu-id="4b141-134">使用**模糊视觉**模拟显示</span><span class="sxs-lookup"><span data-stu-id="4b141-134">Display using **Blurred Vision** simulation</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-achromatopsia-emulation.msft.png" alt-text="使用 \* \* Achromatopsia \* \* 模拟显示" lightbox="../media/accessibility-achromatopsia-emulation.msft.png":::
             <span data-ttu-id="4b141-136">使用**Achromatopsia**模拟进行显示</span><span class="sxs-lookup"><span data-stu-id="4b141-136">Display using **Achromatopsia** simulation</span></span> :::image-end:::  
       :::column-end:::
    :::row-end:::
    
## <span data-ttu-id="4b141-137">使用 "命令" 菜单</span><span class="sxs-lookup"><span data-stu-id="4b141-137">Use the Command Menu</span></span>  

<span data-ttu-id="4b141-138">您也可以使用 "**命令" 菜单**访问不同的模拟。</span><span class="sxs-lookup"><span data-stu-id="4b141-138">You may also use **Command Menu** to access the different simulations.</span></span>  

1.  <span data-ttu-id="4b141-139">按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "**命令" 菜单**。</span><span class="sxs-lookup"><span data-stu-id="4b141-139">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       <span data-ttu-id="4b141-141">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="4b141-141">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="4b141-142">键入 `emulate` ，选择要模拟的内容，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="4b141-142">Type `emulate`, choose what you want to simulate and press `Enter`.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulation-command-menu-results.msft.png" alt-text=""命令" 菜单中提供的不同模拟选项" lightbox="../media/accessibility-emulation-command-menu-results.msft.png":::
       <span data-ttu-id="4b141-144">"**命令" 菜单**中提供的不同模拟选项</span><span class="sxs-lookup"><span data-stu-id="4b141-144">The different simulation options available in the **Command Menu**</span></span>  
    :::image-end:::  
    
> [!IMPORTANT]
> <span data-ttu-id="4b141-145">"**模拟远景处理不足**" 工具模拟每个缺陷的人可以查看你的产品的具体程度。</span><span class="sxs-lookup"><span data-stu-id="4b141-145">The **Emulate vision deficiencies** tools simulate approximations of how a person with each deficiency may see your product.</span></span>  <span data-ttu-id="4b141-146">每个人都是不同的，因此视力缺陷在人员间的严重性方面各不相同。</span><span class="sxs-lookup"><span data-stu-id="4b141-146">Each person is different, therefore vision deficiencies vary in severity from person to person.</span></span>  <span data-ttu-id="4b141-147">为了更好地满足用户需求，请避免可能出现问题的任何颜色组合。</span><span class="sxs-lookup"><span data-stu-id="4b141-147">To better meet the needs of your users, avoid any color combination that may be an issue.</span></span>  <span data-ttu-id="4b141-148">"**模拟远景缺陷**" 工具不是产品的完全辅助功能评估。</span><span class="sxs-lookup"><span data-stu-id="4b141-148">The **Emulate vision deficiencies** tools are not a full accessibility assessment of your product.</span></span>  <span data-ttu-id="4b141-149">相反，"**模拟远景缺陷**" 工具应为您提供一个良好的第一步，以避免问题。</span><span class="sxs-lookup"><span data-stu-id="4b141-149">Instead, the **Emulate vision deficiencies** tools should  give you a good first step to avoid problems.</span></span>  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  
[ColorblindawarenessMain]: http://www.colourblindawareness.org ""彩色盲人" 感知组织"  
[AmfcbMain]: https://www.amfcb.org "色盲（AFCB）的美洲地基"  
[RenderingTools]: /microsoft-edge/devtools-guide-chromium/rendering-tools "Microsoft Edge （Chromium）着色工具"  
