---
title: 模仿 Microsoft Edge DevTools 中的视觉缺陷（色盲）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 0b608f5fe67724eee81aeb993577ee9b45cbca09
ms.sourcegitcommit: d7fdb67df0fe73fa5ae96e5a69a847d07941d0a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "10758062"
---
# <span data-ttu-id="6f3c8-103">模仿视觉缺陷</span><span class="sxs-lookup"><span data-stu-id="6f3c8-103">Emulate vision deficiencies</span></span>

<span data-ttu-id="6f3c8-104">全球各地约有8% 的男士和0.5% 的女人有一个[颜色远景缺陷][ColorblindawarenessMain]，其中通常称为 "色盲"。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-104">Worldwide approximately 8% of men and 0.5% of women have a [color vision deficiency][ColorblindawarenessMain] commonly named "Color Blindness".</span></span>  <span data-ttu-id="6f3c8-105">[Microsoft Edge DevTools][MicrosoftEdgeDevTools]使你能够模拟各种已知的缺陷，并提供你的产品预览版供你查看。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-105">[Microsoft Edge DevTools][MicrosoftEdgeDevTools] enables you to emulate various known deficiencies and provide a preview of your product for you to review.</span></span>  

| <span data-ttu-id="6f3c8-106">颜色缺陷</span><span class="sxs-lookup"><span data-stu-id="6f3c8-106">Color Deficiency</span></span> | <span data-ttu-id="6f3c8-107">详细信息</span><span class="sxs-lookup"><span data-stu-id="6f3c8-107">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="6f3c8-108">模糊视觉效果</span><span class="sxs-lookup"><span data-stu-id="6f3c8-108">Blurred vision</span></span> |  |   
| <span data-ttu-id="6f3c8-109">Protanopia</span><span class="sxs-lookup"><span data-stu-id="6f3c8-109">Protanopia</span></span> | <span data-ttu-id="6f3c8-110">无法感觉任何红光。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-110">The inability to perceive any red light.</span></span> |  
| <span data-ttu-id="6f3c8-111">Deuteranopia</span><span class="sxs-lookup"><span data-stu-id="6f3c8-111">Deuteranopia</span></span> | <span data-ttu-id="6f3c8-112">无法感觉任何绿色光。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-112">The inability to perceive any green light.</span></span> |  
| <span data-ttu-id="6f3c8-113">Tritanopia</span><span class="sxs-lookup"><span data-stu-id="6f3c8-113">Tritanopia</span></span> | <span data-ttu-id="6f3c8-114">无法感觉任何蓝色光线。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-114">The inability to perceive any blue light.</span></span> |  
| <span data-ttu-id="6f3c8-115">Achromatopsia</span><span class="sxs-lookup"><span data-stu-id="6f3c8-115">Achromatopsia</span></span> | <span data-ttu-id="6f3c8-116">除了灰色底纹之外，无法感觉任何颜色。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-116">The inability to perceive any color, except for shades of grey.</span></span> |  

## <span data-ttu-id="6f3c8-117">导航到 "渲染工具"</span><span class="sxs-lookup"><span data-stu-id="6f3c8-117">Navigate to the Rendering Tools</span></span>  

<span data-ttu-id="6f3c8-118">若要测试当前 web 产品的色彩不足，请打开 "[渲染工具][RenderingTools]"。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-118">To test your current web product for color deficiencies, open the [Rendering Tools][RenderingTools].</span></span>  

1.  <span data-ttu-id="6f3c8-119">通过选择 `...` 工具栏中的菜单项打开呈现工具</span><span class="sxs-lookup"><span data-stu-id="6f3c8-119">Open the Rendering Tools by selecting the `...` menu item in the toolbar</span></span>  
1.  <span data-ttu-id="6f3c8-120">选择</span><span class="sxs-lookup"><span data-stu-id="6f3c8-120">Select</span></span> `More tools`  
1.  <span data-ttu-id="6f3c8-121">选择</span><span class="sxs-lookup"><span data-stu-id="6f3c8-121">Select</span></span> `Rendering`  
    
    :::image type="complex" source="../media/getting-to-the-rendering-tools.msft.png" alt-text="打开渲染工具" lightbox="../media/getting-to-the-rendering-tools.msft.png":::
       <span data-ttu-id="6f3c8-123">打开**渲染工具**</span><span class="sxs-lookup"><span data-stu-id="6f3c8-123">Opening the **Rendering Tools**</span></span>  
    :::image-end:::  

<span data-ttu-id="6f3c8-124">**呈现**菜单显示在 DevTools 的下半部分。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-124">The **Rendering** menu appears in the bottom half of the DevTools.</span></span>  

1.  <span data-ttu-id="6f3c8-125">向下滚动到 `Emulate Vision deficiencies` 菜单项，然后从选项中进行选择。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-125">Scroll down to the `Emulate Vision deficiencies` menu item and select from the options.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu.msft.png" alt-text="渲染工具的 "模拟远景缺陷" 菜单" lightbox="../media/accessibility-emulate-vision-menu.msft.png":::
       <span data-ttu-id="6f3c8-127">**渲染**工具的 "**模拟远景缺陷**" 菜单</span><span class="sxs-lookup"><span data-stu-id="6f3c8-127">The **Emulate Vision Deficiencies** menu of the **Rendering** tools</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6f3c8-128">选择任何选项</span><span class="sxs-lookup"><span data-stu-id="6f3c8-128">Choose any of the options</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu-options.msft.png" alt-text=""模拟远景缺陷" 菜单选项" lightbox="../media/accessibility-emulate-vision-menu-options.msft.png":::
       <span data-ttu-id="6f3c8-130">"**模拟远景缺陷**" 菜单选项</span><span class="sxs-lookup"><span data-stu-id="6f3c8-130">The **Emulate Vision Deficiencies** menu options</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6f3c8-131">当前页面将以模拟其对具有所选缺陷的用户显示的方式进行显示。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-131">The current page is displayed in a simulation of how it may appear to a user with the chosen deficiency.</span></span>  

    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-blurred-vision-emulation.msft.png" alt-text="模糊视觉模拟中的 Microsoft Edge 开发人员工具文档" lightbox="../media/accessibility-blurred-vision-emulation.msft.png":::
             <span data-ttu-id="6f3c8-133">使用**模糊视觉**模拟进行显示</span><span class="sxs-lookup"><span data-stu-id="6f3c8-133">Displayed using **Blurred Vision** emulation</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-achromatopsia-emulation.msft.png" alt-text="Achromatopsia 视觉模拟中的 Microsoft Edge 开发人员工具文档" lightbox="../media/accessibility-achromatopsia-emulation.msft.png":::
             <span data-ttu-id="6f3c8-135">使用**Achromatopsia 视觉**模拟进行显示</span><span class="sxs-lookup"><span data-stu-id="6f3c8-135">Display using **Achromatopsia Vision** emulation</span></span> :::image-end:::  
       :::column-end:::
    :::row-end:::
    
## <span data-ttu-id="6f3c8-136">使用 "命令" 菜单</span><span class="sxs-lookup"><span data-stu-id="6f3c8-136">Using the command menu</span></span>  

<span data-ttu-id="6f3c8-137">您也可以通过使用 "**命令" 菜单**来访问不同的模拟，而无需使用各种菜单。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-137">You may also reach the different emulations without going through the various menus using the **Command Menu**.</span></span>  

1.  <span data-ttu-id="6f3c8-138">按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "**命令" 菜单**。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-138">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       <span data-ttu-id="6f3c8-140">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="6f3c8-140">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6f3c8-141">键入 `emulate` ，选择要模拟的内容，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-141">Type `emulate`, choose what you want to simulate and press `Enter`.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulation-command-menu-results.msft.png" alt-text=""命令" 菜单中提供的不同模拟选项" lightbox="../media/accessibility-emulation-command-menu-results.msft.png":::
       <span data-ttu-id="6f3c8-143">"**命令" 菜单**中提供的不同模拟选项</span><span class="sxs-lookup"><span data-stu-id="6f3c8-143">The different emulation options available in the **Command Menu**</span></span>  
    :::image-end:::  
    
> [!IMPORTANT]
> <span data-ttu-id="6f3c8-144">模拟工具近似于具有每种缺陷的人可以查看您的产品。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-144">The emulation tools are approximations of how a person with each deficiency may see your product.</span></span>  <span data-ttu-id="6f3c8-145">每个人都是不同的，因此视力缺陷在人员间的严重性方面各不相同。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-145">Each person is different, therefore vision deficiencies vary in severity from person to person.</span></span>  <span data-ttu-id="6f3c8-146">为了更好地满足用户需求，请避免可能出现问题的任何颜色组合。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-146">To better meet the needs of your users, avoid any color combination that may be an issue.</span></span>  <span data-ttu-id="6f3c8-147">模拟工具不是对产品辅助功能的完全评估，但你应该先有一个良好的步骤来避免最大的缺陷。</span><span class="sxs-lookup"><span data-stu-id="6f3c8-147">The emulation tools are not a full assessment of the accessibility of your product, but you should have a good first step towards avoiding the biggest deficiencies.</span></span>  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  
[ColorblindawarenessMain]: http://www.colourblindawareness.org ""彩色盲人" 感知组织"  
[AmfcbMain]: https://www.amfcb.org "色盲（AFCB）的美洲地基"  
[RenderingTools]: /microsoft-edge/devtools-guide-chromium/rendering-tools "Microsoft Edge （Chromium）着色工具"  
