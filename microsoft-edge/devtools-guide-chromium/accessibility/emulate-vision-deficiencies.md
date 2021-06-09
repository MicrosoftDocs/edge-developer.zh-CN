---
description: 在 DevTools 中模拟Microsoft Edge缺陷。
title: '在 DevTools Microsoft Edge色盲 (中模拟视觉缺陷) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 0a0ee09c2f739beb366b4c39d113b31fb719ec6a
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597119"
---
# <a name="emulate-vision-deficiencies"></a><span data-ttu-id="ef4da-104">模仿视觉缺陷</span><span class="sxs-lookup"><span data-stu-id="ef4da-104">Emulate vision deficiencies</span></span>  

<span data-ttu-id="ef4da-105">为了更好地满足色盲[\ (][ColorblindawarenessMain]色盲\) 或模糊视觉的用户的需求[，Microsoft Edge DevTools][DevtoolsIndex]允许你模拟模糊的视觉和特定的颜色视觉缺陷。</span><span class="sxs-lookup"><span data-stu-id="ef4da-105">To better meet the needs of your users with [color vision deficiency][ColorblindawarenessMain] \(color blindness\) or blurred vision, [Microsoft Edge DevTools][DevtoolsIndex] allow you to simulate blurred vision and specific color vision deficiencies.</span></span>  <span data-ttu-id="ef4da-106">模拟 **视觉缺陷工具** 可模拟以下类别。</span><span class="sxs-lookup"><span data-stu-id="ef4da-106">The **Emulate vision deficiencies** tool simulates the following categories.</span></span>  

| <span data-ttu-id="ef4da-107">色盲</span><span class="sxs-lookup"><span data-stu-id="ef4da-107">Color vision deficiency</span></span> | <span data-ttu-id="ef4da-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="ef4da-108">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="ef4da-109">模糊的视觉</span><span class="sxs-lookup"><span data-stu-id="ef4da-109">Blurred vision</span></span> | <span data-ttu-id="ef4da-110">用户很难专注于细节。</span><span class="sxs-lookup"><span data-stu-id="ef4da-110">The user has difficulty focusing on fine details.</span></span> |  
| <span data-ttu-id="ef4da-111">红色盲</span><span class="sxs-lookup"><span data-stu-id="ef4da-111">Protanopia</span></span> | <span data-ttu-id="ef4da-112">用户无法感知任何红色光。</span><span class="sxs-lookup"><span data-stu-id="ef4da-112">The user is unable to perceive any red light.</span></span> |  
| <span data-ttu-id="ef4da-113">绿色盲</span><span class="sxs-lookup"><span data-stu-id="ef4da-113">Deuteranopia</span></span> | <span data-ttu-id="ef4da-114">用户无法感知任何绿色光。</span><span class="sxs-lookup"><span data-stu-id="ef4da-114">The user is unable to perceive any green light.</span></span> |  
| <span data-ttu-id="ef4da-115">黄蓝色盲</span><span class="sxs-lookup"><span data-stu-id="ef4da-115">Tritanopia</span></span> | <span data-ttu-id="ef4da-116">用户无法感知任何蓝色光。</span><span class="sxs-lookup"><span data-stu-id="ef4da-116">The user is unable to perceive any blue light.</span></span> |  
| <span data-ttu-id="ef4da-117">全色盲</span><span class="sxs-lookup"><span data-stu-id="ef4da-117">Achromatopsia</span></span> | <span data-ttu-id="ef4da-118">用户无法感知任何颜色，这会降低所有颜色为灰色底纹。</span><span class="sxs-lookup"><span data-stu-id="ef4da-118">The user is unable to perceive any color, which reduces all color to a shade of grey.</span></span> |  


## <a name="navigate-to-the-rendering-tool"></a><span data-ttu-id="ef4da-119">导航到呈现工具</span><span class="sxs-lookup"><span data-stu-id="ef4da-119">Navigate to the Rendering tool</span></span>

<span data-ttu-id="ef4da-120">若要模拟对 Web 产品应用的视觉缺陷，请打开"呈现[工具"。][DevtoolsRenderingToolsIndex]</span><span class="sxs-lookup"><span data-stu-id="ef4da-120">To simulate a vision deficiency being applied for your web product, open the [Rendering Tools][DevtoolsRenderingToolsIndex].</span></span>  

1.  <span data-ttu-id="ef4da-121">若要打开呈现工具，请选择 `...` 工具栏中的菜单项</span><span class="sxs-lookup"><span data-stu-id="ef4da-121">To open the Rendering tool, choose the `...` menu item in the toolbar</span></span>  
1.  <span data-ttu-id="ef4da-122">选择 **"更多工具"**</span><span class="sxs-lookup"><span data-stu-id="ef4da-122">Choose **More tools**</span></span>  
1.  <span data-ttu-id="ef4da-123">选择 **"呈现"**</span><span class="sxs-lookup"><span data-stu-id="ef4da-123">Choose **Rendering**</span></span>  
    
    :::image type="complex" source="../media/getting-to-the-rendering-tools.msft.png" alt-text="打开呈现工具" lightbox="../media/getting-to-the-rendering-tools.msft.png":::
       <span data-ttu-id="ef4da-125">打开 **呈现** 工具</span><span class="sxs-lookup"><span data-stu-id="ef4da-125">Opening the **Rendering** tool</span></span>
    :::image-end:::  
    
<span data-ttu-id="ef4da-126">" **呈现** "菜单显示在箱中。</span><span class="sxs-lookup"><span data-stu-id="ef4da-126">The **Rendering** menu appears in the drawer.</span></span>  

1.  <span data-ttu-id="ef4da-127">向下滚动到 `Emulate vision deficiencies` 菜单项并选择下拉菜单以显示选项。</span><span class="sxs-lookup"><span data-stu-id="ef4da-127">Scroll down to the `Emulate vision deficiencies` menu item and choose the drop-down menu to display the options.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu.msft.png" alt-text="呈现工具上的"模拟视觉缺陷"菜单" lightbox="../media/accessibility-emulate-vision-menu.msft.png":::
       <span data-ttu-id="ef4da-129">呈现 **工具上的** "模拟视觉缺陷 **"** 菜单</span><span class="sxs-lookup"><span data-stu-id="ef4da-129">The **Emulate vision deficiencies** menu on the **Rendering** tool</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="ef4da-130">选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="ef4da-130">Choose an option.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulate-vision-menu-options.msft.png" alt-text=""模拟视觉缺陷"菜单选项" lightbox="../media/accessibility-emulate-vision-menu-options.msft.png":::
       <span data-ttu-id="ef4da-132">" **模拟视觉缺陷"** 菜单选项</span><span class="sxs-lookup"><span data-stu-id="ef4da-132">The **Emulate vision deficiencies** menu options</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ef4da-133">主窗口显示已应用于当前页面的所选选项的模拟。</span><span class="sxs-lookup"><span data-stu-id="ef4da-133">The main windows displays the simulation of your chosen option applied to the current page.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-blurred-vision-emulation.msft.png" alt-text="使用模糊视觉模拟显示" lightbox="../media/accessibility-blurred-vision-emulation.msft.png":::
             <span data-ttu-id="ef4da-135">使用**模糊视觉模拟显示**</span><span class="sxs-lookup"><span data-stu-id="ef4da-135">Display using **Blurred vision** simulation</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/accessibility-achromatopsia-emulation.msft.png" alt-text="使用 Achromatop进行模拟显示" lightbox="../media/accessibility-achromatopsia-emulation.msft.png":::
             <span data-ttu-id="ef4da-137">使用**Achromatop进行模拟显示**</span><span class="sxs-lookup"><span data-stu-id="ef4da-137">Display using **Achromatopsia** simulation</span></span> :::image-end:::  
       :::column-end:::
    :::row-end:::
    

## <a name="use-the-command-menu"></a><span data-ttu-id="ef4da-138">使用命令菜单</span><span class="sxs-lookup"><span data-stu-id="ef4da-138">Use the Command Menu</span></span>  

<span data-ttu-id="ef4da-139">您还可以使用命令 **菜单** 访问不同的模拟。</span><span class="sxs-lookup"><span data-stu-id="ef4da-139">You may also use **Command Menu** to access the different simulations.</span></span>  

1.  <span data-ttu-id="ef4da-140">选择 `Ctrl` + `Shift` + `P` \ (Windows/Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 打开命令**菜单**。</span><span class="sxs-lookup"><span data-stu-id="ef4da-140">Select `Ctrl`+`Shift`+`P` \(Windows/Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       <span data-ttu-id="ef4da-142">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="ef4da-142">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ef4da-143">键入 `emulate` ，选择要模拟的，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="ef4da-143">Type `emulate`, choose what you want to simulate and choose `Enter`.</span></span>  
    
    :::image type="complex" source="../media/accessibility-emulation-command-menu-results.msft.png" alt-text="命令菜单中提供的不同模拟选项" lightbox="../media/accessibility-emulation-command-menu-results.msft.png":::
       <span data-ttu-id="ef4da-145">命令菜单中提供的不同 **模拟选项**</span><span class="sxs-lookup"><span data-stu-id="ef4da-145">The different simulation options available in the **Command Menu**</span></span>  
    :::image-end:::  
    
> [!IMPORTANT]
> <span data-ttu-id="ef4da-146">" **模拟视觉缺陷"** 工具模拟每个缺陷人士可能如何查看你的产品的近似值。</span><span class="sxs-lookup"><span data-stu-id="ef4da-146">The **Emulate vision deficiencies** tools simulate approximations of how a person with each deficiency may see your product.</span></span>  <span data-ttu-id="ef4da-147">每个人是不同的，因此视觉缺陷的严重性因人而异。</span><span class="sxs-lookup"><span data-stu-id="ef4da-147">Each person is different, therefore vision deficiencies vary in severity from person to person.</span></span>  <span data-ttu-id="ef4da-148">为了更好地满足用户的需求，请避免任何可能导致问题的颜色组合。</span><span class="sxs-lookup"><span data-stu-id="ef4da-148">To better meet the needs of your users, avoid any color combination that may be an issue.</span></span>  <span data-ttu-id="ef4da-149">模拟 **视觉缺陷** 工具不是产品的完整辅助功能评估。</span><span class="sxs-lookup"><span data-stu-id="ef4da-149">The **Emulate vision deficiencies** tools are not a full accessibility assessment of your product.</span></span>  <span data-ttu-id="ef4da-150">相反 **，"模拟视觉缺陷"** 工具应为您提供良好的第一步以避免出现问题。</span><span class="sxs-lookup"><span data-stu-id="ef4da-150">Instead, the **Emulate vision deficiencies** tools should  give you a good first step to avoid problems.</span></span>  


## <a name="see-also"></a><span data-ttu-id="ef4da-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef4da-151">See also</span></span>

* [<span data-ttu-id="ef4da-152">验证页面是否可借助模糊视图</span><span class="sxs-lookup"><span data-stu-id="ef4da-152">Verify that the page is usable with blurred vision</span></span>](test-blurred-vision.md)


<!-- links -->  
[DevToolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
[DevtoolsRenderingToolsIndex]: ../rendering-tools/index.md "分析运行时性能|Microsoft Docs"  

[ColorblindawarenessMain]: https://www.colourblindawareness.org "光盲意识组织"  

[AmfcbMain]: https://www.amfcb.org "American Foundation for the Color Blind (AFCB) "  
