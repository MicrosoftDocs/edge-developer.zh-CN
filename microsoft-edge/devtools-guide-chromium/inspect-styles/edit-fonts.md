---
description: 了解如何使用 Microsoft Edge 开发人员工具中的“样式”窗格更改 CSS 字体样式和设置。
title: 在开发人员工具的“样式”窗格中编辑 CSS 字体样式和设置
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/11/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, 开发人员工具
no-loc:
- Enable new font editor tool within the Styles pane
ms.openlocfilehash: 5d9074ca65f9cb98662a1bc181f70ead4c4232e1
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439491"
---
# <a name="edit-css-font-styles-and-settings-in-the-styles-pane"></a><span data-ttu-id="2d56a-104">在“样式”窗格中编辑 CSS 字体样式和设置</span><span class="sxs-lookup"><span data-stu-id="2d56a-104">Edit CSS font styles and settings in the Styles pane</span></span>  

:::image type="icon" source="../media/experimental-tag-14px.msft.png":::

<span data-ttu-id="2d56a-105">网页版式是用户体验的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="2d56a-105">Typography on the web is an important part of the user experience.</span></span>  <span data-ttu-id="2d56a-106">你希望确保你符合企业品牌准则，并且你的内容在各种设备上按预期显示。</span><span class="sxs-lookup"><span data-stu-id="2d56a-106">You want to ensure you meet corporate brand guidelines, and your content displays as expected on various devices.</span></span>  <span data-ttu-id="2d56a-107">必须使用大小和线条高度让文本更易于阅读。</span><span class="sxs-lookup"><span data-stu-id="2d56a-107">Text must be easy to read using size and line-height.</span></span>  <span data-ttu-id="2d56a-108">用户可调整字体大小来满足个人需求。</span><span class="sxs-lookup"><span data-stu-id="2d56a-108">Users may resize fonts to meet individual needs.</span></span>  <span data-ttu-id="2d56a-109">对于特定字体在用户设备上不可用的情况，应提供回退字体选项。</span><span class="sxs-lookup"><span data-stu-id="2d56a-109">For situations when specific fonts are not available on a user device, you should provide fallback font options.</span></span>  

<span data-ttu-id="2d56a-110">近年来，CSS 为版式提供了更好的支持。</span><span class="sxs-lookup"><span data-stu-id="2d56a-110">CSS provides better support for typography in recent years.</span></span>  <span data-ttu-id="2d56a-111">有数十种不同的 CSS 单位可用于定义文本大小。</span><span class="sxs-lookup"><span data-stu-id="2d56a-111">Dozens of different CSS units are available to define the size of text.</span></span>  <span data-ttu-id="2d56a-112">你还可以使用多个 CSS 属性来影响字体大小、间距、线条高度和其他版式特性。</span><span class="sxs-lookup"><span data-stu-id="2d56a-112">You also have several CSS properties that affect font-size, spacing, line height, and other typographic features.</span></span>  

<span data-ttu-id="2d56a-113">为了在使用版式时更加轻松，可视“**字体编辑器**”现在位于“**样式**”窗格中。</span><span class="sxs-lookup"><span data-stu-id="2d56a-113">To make it easier when working with typography, a visual **Font Editor** is now in the **Styles** pane.</span></span>  <span data-ttu-id="2d56a-114">你可以更改字体设置，更改会立即呈现在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="2d56a-114">You may change your font settings, and the changes are rendered immediately in the browser.</span></span>  <span data-ttu-id="2d56a-115">所有这些内容都无需深入了解 CSS。</span><span class="sxs-lookup"><span data-stu-id="2d56a-115">All without in-depth knowledge of CSS.</span></span>  

<span data-ttu-id="2d56a-116">当前，**Enable new font editor tool within the Styles pane** 功能处于试验阶段，你需要[为 Microsoft Edge 开发人员工具启用它][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]。</span><span class="sxs-lookup"><span data-stu-id="2d56a-116">Currently the **Enable new font editor tool within the Styles pane** feature is experimental and you need to [turn it on for Microsoft Edge Developer Tools][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures].</span></span>  

<span data-ttu-id="2d56a-117">“**样式**”窗格中的任何 CSS（字体定义或内嵌样式）都会自动显示一个图标，用于打开可视“**字体编辑器**”。</span><span class="sxs-lookup"><span data-stu-id="2d56a-117">Any CSS in the **Styles** pane, either font definitions or inline styles, automatically displays an icon that opens the visual **Font Editor**.</span></span>  <span data-ttu-id="2d56a-118">若要打开可视“**字体编辑器**”，请选择“**字体编辑器**”图标。</span><span class="sxs-lookup"><span data-stu-id="2d56a-118">To open the visual **Font Editor**, choose the **Font Editor** icon.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-icon.msft.png" alt-text="“样式”窗格中用于编辑字体设置的图标" lightbox="../media/font-editor-icon.msft.png":::
         <span data-ttu-id="2d56a-120">“**样式**”窗格中用于编辑字体设置的图标</span><span class="sxs-lookup"><span data-stu-id="2d56a-120">The icon in the **Styles** pane to edit font settings</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-open.msft.png" alt-text="“字体编辑器”在“样式”窗格顶部打开" lightbox="../media/font-editor-open.msft.png":::
         <span data-ttu-id="2d56a-122">“**字体编辑器**”在“**样式**”窗格顶部打开</span><span class="sxs-lookup"><span data-stu-id="2d56a-122">The **Font Editor** open on top of the **Styles** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="2d56a-123">可视“**字体编辑器**”中的所有字段都是根据“**样式**”窗格中的 CSS 值填充的。</span><span class="sxs-lookup"><span data-stu-id="2d56a-123">All fields in the visual **Font Editor** are populated from the values in the CSS in the **Styles** pane.</span></span>  <span data-ttu-id="2d56a-124">例如，`line-height` 定义在“**样式**”窗格中设置为 `160%`，因此线条高度文本字段显示 `160`，而单位下拉列表显示 `%`。</span><span class="sxs-lookup"><span data-stu-id="2d56a-124">For example, the `line-height` definition is set to `160%` in the **Styles** pane, so the line height text field displays `160`, and the unit dropdown displays `%`.</span></span>  <span data-ttu-id="2d56a-125">此外，滑块会自动设置为与文本字段的值匹配。</span><span class="sxs-lookup"><span data-stu-id="2d56a-125">Also, the slider is automatically set to match the values of the text field.</span></span>  

<span data-ttu-id="2d56a-126">“**字体编辑器**”由两部分组成：“字体系列”选择器和“CSS 属性”编辑器。</span><span class="sxs-lookup"><span data-stu-id="2d56a-126">The **Font Editor** consists of two parts:  the Font Family selector, and the CSS Properties editor.</span></span>  

## <a name="the-font-family-selector"></a><span data-ttu-id="2d56a-127">“字体系列”选择器</span><span class="sxs-lookup"><span data-stu-id="2d56a-127">The Font Family selector</span></span>  

<span data-ttu-id="2d56a-128">“字体系列”选择器位于可视“**字体编辑器**”的上部。</span><span class="sxs-lookup"><span data-stu-id="2d56a-128">The Font Family selector is the upper part of the visual **Font Editor**.</span></span>  <span data-ttu-id="2d56a-129">若要选择 CSS 规则的字体，请在 CSS 编辑器中使用“**字体系列**”选择器。</span><span class="sxs-lookup"><span data-stu-id="2d56a-129">To choose the fonts of the CSS rule, in the CSS editor, use the **Font Family** selector.</span></span>  <span data-ttu-id="2d56a-130">可为每个 CSS 规则选择主字体和回退字体。</span><span class="sxs-lookup"><span data-stu-id="2d56a-130">You may choose main and fallback fonts for each CSS rule.</span></span>  

:::image type="complex" source="../media/font-editor-font-family.msft.png" alt-text="“字体编辑器”在“样式”窗格顶部打开，突出显示“字体系列”选择器" lightbox="../media/font-editor-font-family.msft.png":::
   <span data-ttu-id="2d56a-132">“**字体编辑器**”在“**样式**”窗格顶部打开，突出显示“**字体系列**”选择器</span><span class="sxs-lookup"><span data-stu-id="2d56a-132">The **Font Editor** open on top of the **Styles** pane with the **Font Family** selector highlighted</span></span>  
:::image-end:::  

<span data-ttu-id="2d56a-133">使用“**字体系列**”下拉列表从字体列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="2d56a-133">Use the **Font Family** dropdown to choose from a list of fonts.</span></span>  <span data-ttu-id="2d56a-134">字体分为四组。</span><span class="sxs-lookup"><span data-stu-id="2d56a-134">Fonts are organized into four groups.</span></span>  

1.  <span data-ttu-id="2d56a-135">计算字体，即“**样式**”窗格的样式表中可用的字体。</span><span class="sxs-lookup"><span data-stu-id="2d56a-135">Computed fonts, which are the fonts available in the stylesheet in the **Styles** pane.</span></span>  
1.  <span data-ttu-id="2d56a-136">系统字体，即当前操作系统上可用的字体。</span><span class="sxs-lookup"><span data-stu-id="2d56a-136">System fonts, which are the fonts that are available on the current operating system.</span></span>  
1.  <span data-ttu-id="2d56a-137">常规字体系列，如 `serif` 或 `sans-serif`。</span><span class="sxs-lookup"><span data-stu-id="2d56a-137">Generic font families, such as `serif` or `sans-serif`.</span></span>  
1.  <span data-ttu-id="2d56a-138">全局值，如 `inherit`、`initial` 和 `unset`。</span><span class="sxs-lookup"><span data-stu-id="2d56a-138">Global values, such as `inherit`, `initial`, and `unset`.</span></span>  
    
:::image type="complex" source="../media/font-editor-font-family-list.msft.png" alt-text="“字体编辑器”在“样式”窗格顶部打开，突出显示“字体系列”选择器" lightbox="../media/font-editor-font-family-list.msft.png":::
   <span data-ttu-id="2d56a-140">“**字体编辑器**”在“**样式**”窗格顶部打开，突出显示“**字体系列**”选择器</span><span class="sxs-lookup"><span data-stu-id="2d56a-140">The **Font Editor** open on top of the **Styles** pane with the **Font Family** selector highlighted</span></span>  
:::image-end:::  

<span data-ttu-id="2d56a-141">在你选择字体后，系统将显示另一个下拉菜单供你选择回退字体。</span><span class="sxs-lookup"><span data-stu-id="2d56a-141">After you choose a font, another dropdown menu is displayed for you to choose fallback fonts.</span></span>  <span data-ttu-id="2d56a-142">最多可选择八种回退字体。</span><span class="sxs-lookup"><span data-stu-id="2d56a-142">You may choose up to eight fallback fonts.</span></span>  <span data-ttu-id="2d56a-143">若要删除字体，请选择“**删除字体系列**”图标。</span><span class="sxs-lookup"><span data-stu-id="2d56a-143">To remove a font, choose the **Delete Font Family** icon.</span></span>  

<!--:::image type="complex" source="../media/font-editor-defining-fonts.msft.png" alt-text="The font editor with a defined list of fonts and fallback fonts" lightbox="../media/font-editor-defining-fonts.msft.png":::
   The **Font Editor** with a defined list of fonts and fallback fonts highlighted
:::image-end:::  -->

> [!NOTE]
> <span data-ttu-id="2d56a-144">如果为字体系列选择全局值，则不会再出现另一个下拉列表，因为 CSS 中没有该字体系列的回退字体。</span><span class="sxs-lookup"><span data-stu-id="2d56a-144">If you choose a global value for font family, you do not get another dropdown since there is no fallback for it in CSS.</span></span>  

## <a name="the-css-properties-editor"></a><span data-ttu-id="2d56a-145">“CSS 属性”编辑器</span><span class="sxs-lookup"><span data-stu-id="2d56a-145">The CSS Properties editor</span></span>  

<span data-ttu-id="2d56a-146">可在可视“**字体编辑器**”的下部更改 CSS 字体属性。</span><span class="sxs-lookup"><span data-stu-id="2d56a-146">You may change CSS font properties in the lower part of the visual **Font Editor**.</span></span>  <span data-ttu-id="2d56a-147">可使用任何用户界面控件更改字体大小、线条高度、字体粗细和字母间距。</span><span class="sxs-lookup"><span data-stu-id="2d56a-147">You may change the font size, line height, font weight, and letter spacing using any of the UI controls.</span></span>  <span data-ttu-id="2d56a-148">所做的更改将立即在浏览器中应用。</span><span class="sxs-lookup"><span data-stu-id="2d56a-148">Your changes are applied immediately in the browser.</span></span>  

:::image type="complex" source="../media/font-editor-css-properties.msft.png" alt-text="“字体编辑器”在“样式”窗格顶部打开，突出显示 CSS 属性" lightbox="../media/font-editor-css-properties.msft.png":::
   <span data-ttu-id="2d56a-150">“**字体编辑器**”在“**样式**”窗格顶部打开，突出显示 CSS 属性</span><span class="sxs-lookup"><span data-stu-id="2d56a-150">The **Font Editor** open on top of the **Styles** pane with the CSS properties highlighted</span></span>  
:::image-end:::  

<span data-ttu-id="2d56a-151">也可使用可视“**字体编辑器**”转换 CSS 单位。</span><span class="sxs-lookup"><span data-stu-id="2d56a-151">You may also convert CSS units using the visual **Font Editor**.</span></span>  <span data-ttu-id="2d56a-152">例如，可以在 CSS 规则上使用该工具，其中“**字体大小**”滑块最初设置为 `16 pixels`。</span><span class="sxs-lookup"><span data-stu-id="2d56a-152">For example, you may use the tool on a CSS rule where the **Font Size** slider is initially set to `16 pixels`.</span></span>  <span data-ttu-id="2d56a-153">现在，使用单位下拉菜单并选择值 `em`。</span><span class="sxs-lookup"><span data-stu-id="2d56a-153">Now, use the unit dropdown and choose the value `em`.</span></span>  <span data-ttu-id="2d56a-154">显示的 `1 em` 等于 `16 pixels`。</span><span class="sxs-lookup"><span data-stu-id="2d56a-154">The `1 em` displayed is equal to `16 pixels`.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-setting-to-16px.msft.png" alt-text="将字体大小更改为 16 像素" lightbox="../media/font-editor-setting-to-16px.msft.png":::
         <span data-ttu-id="2d56a-156">将字体大小更改为</span><span class="sxs-lookup"><span data-stu-id="2d56a-156">Change the font size to</span></span> `16 pixels`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-converted-to-em.msft.png" alt-text="打开单位下拉列表以转换为 em" lightbox="../media/font-editor-converted-to-em.msft.png":::
         <span data-ttu-id="2d56a-158">打开单位下拉列表以转换为</span><span class="sxs-lookup"><span data-stu-id="2d56a-158">Open the unit dropdown to convert to</span></span> `em`  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="2d56a-159">单位下拉列表提供所有可用的数值 CSS 单位。</span><span class="sxs-lookup"><span data-stu-id="2d56a-159">The unit dropdown provides all the numeric CSS units that are available.</span></span>  <span data-ttu-id="2d56a-160">字体大小、线条高度、字体粗细和间距都使用不同的单位。</span><span class="sxs-lookup"><span data-stu-id="2d56a-160">Font size, line height, font weight, and spacing all use different units.</span></span>  <span data-ttu-id="2d56a-161">当文本框有焦点时，你可以选择 `arrow up` 和 `arrow down` 键微调设置。</span><span class="sxs-lookup"><span data-stu-id="2d56a-161">When the text boxes have focus, you may select the `arrow up` and `arrow down` keys to fine-tune your settings.</span></span>  <span data-ttu-id="2d56a-162">若要将滑块与键盘配合使用，请选择 `arrow left` 和 `arrow down` 键。</span><span class="sxs-lookup"><span data-stu-id="2d56a-162">To use the sliders with a keyboard, select the `arrow left` and `arrow down` keys.</span></span>  

<span data-ttu-id="2d56a-163">“CSS 属性”编辑器还包括预设关键字。</span><span class="sxs-lookup"><span data-stu-id="2d56a-163">The CSS Properties editor also includes preset keywords.</span></span>  <span data-ttu-id="2d56a-164">若要使用预设关键字，请在右侧选择 `Toggle Input Type` 图标。</span><span class="sxs-lookup"><span data-stu-id="2d56a-164">To use the preset keywords, on the right-hand side, choose the `Toggle Input Type` icon.</span></span>  <span data-ttu-id="2d56a-165">用户界面将发生变化，并显示预设关键字的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="2d56a-165">The UI changes, and a dropdown of preset keywords are displayed.</span></span>  <span data-ttu-id="2d56a-166">若要使用滑块和其他用户界面控件返回用户界面，请再次选择 `Toggle Input Type` 图标。</span><span class="sxs-lookup"><span data-stu-id="2d56a-166">To return to the UI with the slider and other UI controls, choose the `Toggle Input Type` icon again.</span></span>  

:::image type="complex" source="../media/font-editor-preset-font-sizes.msft.png" alt-text="打开预设关键字界面" lightbox="../media/font-editor-preset-font-sizes.msft.png":::
   <span data-ttu-id="2d56a-168">打开预设关键字界面</span><span class="sxs-lookup"><span data-stu-id="2d56a-168">Open the preset keyword interface</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="2d56a-169">联系 Microsoft Edge 开发人员工具团队</span><span class="sxs-lookup"><span data-stu-id="2d56a-169">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndex]: ../experimental-features/index.md "试验功能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]: ../experimental-features/index.md#turn-on-experimental-features "打开试验功能 - 试验功能 | Microsoft Docs"  
