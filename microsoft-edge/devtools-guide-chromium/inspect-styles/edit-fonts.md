---
description: 了解如何使用 Microsoft Edge DevTools 中的"样式"窗格更改 CSS 字体样式和设置。
title: 在 DevTools 的"样式"窗格中编辑 CSS 字体样式和设置
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/11/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
no-loc:
- Enable new font editor tool within the Styles pane
ms.openlocfilehash: 5d9074ca65f9cb98662a1bc181f70ead4c4232e1
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439491"
---
# <a name="edit-css-font-styles-and-settings-in-the-styles-pane"></a><span data-ttu-id="9e116-104">在"样式"窗格中编辑 CSS 字体样式和设置</span><span class="sxs-lookup"><span data-stu-id="9e116-104">Edit CSS font styles and settings in the Styles pane</span></span>  

:::image type="icon" source="../media/experimental-tag-14px.msft.png":::

<span data-ttu-id="9e116-105">网页版式是用户体验的重要部分。</span><span class="sxs-lookup"><span data-stu-id="9e116-105">Typography on the web is an important part of the user experience.</span></span>  <span data-ttu-id="9e116-106">你想要确保你符合公司品牌准则，并且内容在各种设备上按预期方式显示。</span><span class="sxs-lookup"><span data-stu-id="9e116-106">You want to ensure you meet corporate brand guidelines, and your content displays as expected on various devices.</span></span>  <span data-ttu-id="9e116-107">文本必须易于使用大小和行高阅读。</span><span class="sxs-lookup"><span data-stu-id="9e116-107">Text must be easy to read using size and line-height.</span></span>  <span data-ttu-id="9e116-108">用户可以调整字体大小以满足个人需求。</span><span class="sxs-lookup"><span data-stu-id="9e116-108">Users may resize fonts to meet individual needs.</span></span>  <span data-ttu-id="9e116-109">对于特定字体在用户设备上不可用的情况，你应该提供回退字体选项。</span><span class="sxs-lookup"><span data-stu-id="9e116-109">For situations when specific fonts are not available on a user device, you should provide fallback font options.</span></span>  

<span data-ttu-id="9e116-110">CSS 提供对近期版式更好的支持。</span><span class="sxs-lookup"><span data-stu-id="9e116-110">CSS provides better support for typography in recent years.</span></span>  <span data-ttu-id="9e116-111">数十种不同的 CSS 单位可用于定义文本的大小。</span><span class="sxs-lookup"><span data-stu-id="9e116-111">Dozens of different CSS units are available to define the size of text.</span></span>  <span data-ttu-id="9e116-112">您还有一些影响字体大小、间距、行高和其他排版功能的 CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="9e116-112">You also have several CSS properties that affect font-size, spacing, line height, and other typographic features.</span></span>  

<span data-ttu-id="9e116-113">为了在使用版式时更加轻松，可视化 **字体编辑器** 现在位于 **"样式"** 窗格中。</span><span class="sxs-lookup"><span data-stu-id="9e116-113">To make it easier when working with typography, a visual **Font Editor** is now in the **Styles** pane.</span></span>  <span data-ttu-id="9e116-114">您可以更改字体设置，更改会立即呈现在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="9e116-114">You may change your font settings, and the changes are rendered immediately in the browser.</span></span>  <span data-ttu-id="9e116-115">所有这些内容都无需深入了解 CSS。</span><span class="sxs-lookup"><span data-stu-id="9e116-115">All without in-depth knowledge of CSS.</span></span>  

<span data-ttu-id="9e116-116">目前 **Enable new font editor tool within the Styles pane** 该功能是实验性的，你需要为 [Microsoft Edge 开发人员工具 启用它][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]。</span><span class="sxs-lookup"><span data-stu-id="9e116-116">Currently the **Enable new font editor tool within the Styles pane** feature is experimental and you need to [turn it on for Microsoft Edge Developer Tools][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures].</span></span>  

<span data-ttu-id="9e116-117">" **样式"窗格中** 的任何 CSS（字体定义或内联样式）都会自动显示打开可视"字体 **编辑器"的图标**。</span><span class="sxs-lookup"><span data-stu-id="9e116-117">Any CSS in the **Styles** pane, either font definitions or inline styles, automatically displays an icon that opens the visual **Font Editor**.</span></span>  <span data-ttu-id="9e116-118">若要打开可视字体 **编辑器，** 请选择" **字体编辑器"** 图标。</span><span class="sxs-lookup"><span data-stu-id="9e116-118">To open the visual **Font Editor**, choose the **Font Editor** icon.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-icon.msft.png" alt-text=""样式"窗格中用于编辑字体设置的图标" lightbox="../media/font-editor-icon.msft.png":::
         <span data-ttu-id="9e116-120">" **样式"窗格中** 用于编辑字体设置的图标</span><span class="sxs-lookup"><span data-stu-id="9e116-120">The icon in the **Styles** pane to edit font settings</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-open.msft.png" alt-text=""字体编辑器"在"样式"窗格顶部打开" lightbox="../media/font-editor-open.msft.png":::
         <span data-ttu-id="9e116-122">" **字体编辑器** "在"样式"窗格 **顶部** 打开</span><span class="sxs-lookup"><span data-stu-id="9e116-122">The **Font Editor** open on top of the **Styles** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="9e116-123">可视字体编辑器 **中所有字段** 都从"样式"窗格中的 CSS **中的值** 填充。</span><span class="sxs-lookup"><span data-stu-id="9e116-123">All fields in the visual **Font Editor** are populated from the values in the CSS in the **Styles** pane.</span></span>  <span data-ttu-id="9e116-124">例如，定义在"样式"窗格中设置为 ，因此行高 `line-height` `160%` 文本字段将显示\*\*\*\*，而单位 `160` 下拉列表显示 `%` 。</span><span class="sxs-lookup"><span data-stu-id="9e116-124">For example, the `line-height` definition is set to `160%` in the **Styles** pane, so the line height text field displays `160`, and the unit dropdown displays `%`.</span></span>  <span data-ttu-id="9e116-125">此外，还会自动设置滑块以匹配文本字段的值。</span><span class="sxs-lookup"><span data-stu-id="9e116-125">Also, the slider is automatically set to match the values of the text field.</span></span>  

<span data-ttu-id="9e116-126">字体 **编辑器由** 两部分组成：字体系列选择器和 CSS 属性编辑器。</span><span class="sxs-lookup"><span data-stu-id="9e116-126">The **Font Editor** consists of two parts:  the Font Family selector, and the CSS Properties editor.</span></span>  

## <a name="the-font-family-selector"></a><span data-ttu-id="9e116-127">字体系列选择器</span><span class="sxs-lookup"><span data-stu-id="9e116-127">The Font Family selector</span></span>  

<span data-ttu-id="9e116-128">字体系列选择器是可视字体编辑器 **的上半部分**。</span><span class="sxs-lookup"><span data-stu-id="9e116-128">The Font Family selector is the upper part of the visual **Font Editor**.</span></span>  <span data-ttu-id="9e116-129">若要选择 CSS 规则的字体，在 CSS 编辑器中，使用 **字体系列** 选择器。</span><span class="sxs-lookup"><span data-stu-id="9e116-129">To choose the fonts of the CSS rule, in the CSS editor, use the **Font Family** selector.</span></span>  <span data-ttu-id="9e116-130">可以针对每个 CSS 规则选择主字体和回退字体。</span><span class="sxs-lookup"><span data-stu-id="9e116-130">You may choose main and fallback fonts for each CSS rule.</span></span>  

:::image type="complex" source="../media/font-editor-font-family.msft.png" alt-text="字体编辑器在"样式"窗格顶部打开，其中突出显示了"字体系列"选择器" lightbox="../media/font-editor-font-family.msft.png":::
   <span data-ttu-id="9e116-132">字体 **编辑器在** "样式" **窗格顶部打开** ，其中突出显示 **了"字体系列** "选择器</span><span class="sxs-lookup"><span data-stu-id="9e116-132">The **Font Editor** open on top of the **Styles** pane with the **Font Family** selector highlighted</span></span>  
:::image-end:::  

<span data-ttu-id="9e116-133">使用 **"字体系列** "下拉列表从字体列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="9e116-133">Use the **Font Family** dropdown to choose from a list of fonts.</span></span>  <span data-ttu-id="9e116-134">字体分为四个组。</span><span class="sxs-lookup"><span data-stu-id="9e116-134">Fonts are organized into four groups.</span></span>  

1.  <span data-ttu-id="9e116-135">计算字体，即样式窗格中样式表**提供的字体。**</span><span class="sxs-lookup"><span data-stu-id="9e116-135">Computed fonts, which are the fonts available in the stylesheet in the **Styles** pane.</span></span>  
1.  <span data-ttu-id="9e116-136">系统字体，即当前操作系统上提供的字体。</span><span class="sxs-lookup"><span data-stu-id="9e116-136">System fonts, which are the fonts that are available on the current operating system.</span></span>  
1.  <span data-ttu-id="9e116-137">常规字体系列，如 `serif` 或 `sans-serif` 。</span><span class="sxs-lookup"><span data-stu-id="9e116-137">Generic font families, such as `serif` or `sans-serif`.</span></span>  
1.  <span data-ttu-id="9e116-138">全局值，如 `inherit` 、 `initial` 和 `unset` 。</span><span class="sxs-lookup"><span data-stu-id="9e116-138">Global values, such as `inherit`, `initial`, and `unset`.</span></span>  
    
:::image type="complex" source="../media/font-editor-font-family-list.msft.png" alt-text="字体编辑器在"样式"窗格顶部打开，其中突出显示了"字体系列"选择器" lightbox="../media/font-editor-font-family-list.msft.png":::
   <span data-ttu-id="9e116-140">字体 **编辑器在** "样式" **窗格顶部打开** ，其中突出显示 **了"字体系列** "选择器</span><span class="sxs-lookup"><span data-stu-id="9e116-140">The **Font Editor** open on top of the **Styles** pane with the **Font Family** selector highlighted</span></span>  
:::image-end:::  

<span data-ttu-id="9e116-141">选择字体后，将显示另一个下拉菜单，供您选择回退字体。</span><span class="sxs-lookup"><span data-stu-id="9e116-141">After you choose a font, another dropdown menu is displayed for you to choose fallback fonts.</span></span>  <span data-ttu-id="9e116-142">你可以选择最多八种回退字体。</span><span class="sxs-lookup"><span data-stu-id="9e116-142">You may choose up to eight fallback fonts.</span></span>  <span data-ttu-id="9e116-143">若要删除字体，请选择"删除 **字体系列"** 图标。</span><span class="sxs-lookup"><span data-stu-id="9e116-143">To remove a font, choose the **Delete Font Family** icon.</span></span>  

<!--:::image type="complex" source="../media/font-editor-defining-fonts.msft.png" alt-text="The font editor with a defined list of fonts and fallback fonts" lightbox="../media/font-editor-defining-fonts.msft.png":::
   The **Font Editor** with a defined list of fonts and fallback fonts highlighted
:::image-end:::  -->

> [!NOTE]
> <span data-ttu-id="9e116-144">如果选择字体系列全局值，将不会获得另一个下拉列表，因为 CSS 中没有回退。</span><span class="sxs-lookup"><span data-stu-id="9e116-144">If you choose a global value for font family, you do not get another dropdown since there is no fallback for it in CSS.</span></span>  

## <a name="the-css-properties-editor"></a><span data-ttu-id="9e116-145">CSS 属性编辑器</span><span class="sxs-lookup"><span data-stu-id="9e116-145">The CSS Properties editor</span></span>  

<span data-ttu-id="9e116-146">您可以在可视字体编辑器的下半部分更改 CSS **字体属性**。</span><span class="sxs-lookup"><span data-stu-id="9e116-146">You may change CSS font properties in the lower part of the visual **Font Editor**.</span></span>  <span data-ttu-id="9e116-147">可以使用任何 UI 控件更改字号、行高、字体粗细和字母间距。</span><span class="sxs-lookup"><span data-stu-id="9e116-147">You may change the font size, line height, font weight, and letter spacing using any of the UI controls.</span></span>  <span data-ttu-id="9e116-148">所做的更改将立即在浏览器中应用。</span><span class="sxs-lookup"><span data-stu-id="9e116-148">Your changes are applied immediately in the browser.</span></span>  

:::image type="complex" source="../media/font-editor-css-properties.msft.png" alt-text="字体编辑器在"样式"窗格顶部打开，其中突出显示了 CSS 属性" lightbox="../media/font-editor-css-properties.msft.png":::
   <span data-ttu-id="9e116-150">字体 **编辑器在** "样式" **窗格顶部打开** ，其中突出显示了 CSS 属性</span><span class="sxs-lookup"><span data-stu-id="9e116-150">The **Font Editor** open on top of the **Styles** pane with the CSS properties highlighted</span></span>  
:::image-end:::  

<span data-ttu-id="9e116-151">您还可以使用可视字体编辑器 转换 CSS **单位**。</span><span class="sxs-lookup"><span data-stu-id="9e116-151">You may also convert CSS units using the visual **Font Editor**.</span></span>  <span data-ttu-id="9e116-152">例如，您可以在 CSS 规则（其中字体大小滑块最初设置为\*\*\*\*）上使用此工具 `16 pixels` 。</span><span class="sxs-lookup"><span data-stu-id="9e116-152">For example, you may use the tool on a CSS rule where the **Font Size** slider is initially set to `16 pixels`.</span></span>  <span data-ttu-id="9e116-153">现在，使用单位下拉列表并选择值 `em` 。</span><span class="sxs-lookup"><span data-stu-id="9e116-153">Now, use the unit dropdown and choose the value `em`.</span></span>  <span data-ttu-id="9e116-154">`1 em`显示的 等于 `16 pixels` 。</span><span class="sxs-lookup"><span data-stu-id="9e116-154">The `1 em` displayed is equal to `16 pixels`.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-setting-to-16px.msft.png" alt-text="将字体大小更改为 16 像素" lightbox="../media/font-editor-setting-to-16px.msft.png":::
         <span data-ttu-id="9e116-156">将字体大小更改为</span><span class="sxs-lookup"><span data-stu-id="9e116-156">Change the font size to</span></span> `16 pixels`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-converted-to-em.msft.png" alt-text="打开"单位"下拉列表以转换为 em" lightbox="../media/font-editor-converted-to-em.msft.png":::
         <span data-ttu-id="9e116-158">打开要转换为的单位下拉列表</span><span class="sxs-lookup"><span data-stu-id="9e116-158">Open the unit dropdown to convert to</span></span> `em`  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="9e116-159">"单位"下拉列表提供所有可用的数值 CSS 单位。</span><span class="sxs-lookup"><span data-stu-id="9e116-159">The unit dropdown provides all the numeric CSS units that are available.</span></span>  <span data-ttu-id="9e116-160">字号、行高、字粗和间距都使用不同的单位。</span><span class="sxs-lookup"><span data-stu-id="9e116-160">Font size, line height, font weight, and spacing all use different units.</span></span>  <span data-ttu-id="9e116-161">当文本框具有焦点时，可以选择 和 `arrow up` `arrow down` 键来微调设置。</span><span class="sxs-lookup"><span data-stu-id="9e116-161">When the text boxes have focus, you may select the `arrow up` and `arrow down` keys to fine-tune your settings.</span></span>  <span data-ttu-id="9e116-162">若要将滑块与键盘一同使用，请选择 `arrow left` 和 `arrow down` 键。</span><span class="sxs-lookup"><span data-stu-id="9e116-162">To use the sliders with a keyboard, select the `arrow left` and `arrow down` keys.</span></span>  

<span data-ttu-id="9e116-163">CSS 属性编辑器还包括预设关键字。</span><span class="sxs-lookup"><span data-stu-id="9e116-163">The CSS Properties editor also includes preset keywords.</span></span>  <span data-ttu-id="9e116-164">若要使用预设关键字，请选择右侧 `Toggle Input Type` 图标。</span><span class="sxs-lookup"><span data-stu-id="9e116-164">To use the preset keywords, on the right-hand side, choose the `Toggle Input Type` icon.</span></span>  <span data-ttu-id="9e116-165">UI 发生更改，并显示预设关键字下拉列表。</span><span class="sxs-lookup"><span data-stu-id="9e116-165">The UI changes, and a dropdown of preset keywords are displayed.</span></span>  <span data-ttu-id="9e116-166">若要使用滑块和其他 UI 控件返回到 UI，请再次 `Toggle Input Type` 选择图标。</span><span class="sxs-lookup"><span data-stu-id="9e116-166">To return to the UI with the slider and other UI controls, choose the `Toggle Input Type` icon again.</span></span>  

:::image type="complex" source="../media/font-editor-preset-font-sizes.msft.png" alt-text="打开预设关键字界面" lightbox="../media/font-editor-preset-font-sizes.msft.png":::
   <span data-ttu-id="9e116-168">打开预设关键字界面</span><span class="sxs-lookup"><span data-stu-id="9e116-168">Open the preset keyword interface</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="9e116-169">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="9e116-169">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  
[DevtoolsExperimentalFeaturesIndex]: ../experimental-features/index.md "实验功能|Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]: ../experimental-features/index.md#turn-on-experimental-features "打开实验性功能 - 实验|Microsoft Docs"  
