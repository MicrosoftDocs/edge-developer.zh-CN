---
description: 提供有关自定义密码显示按钮的显示的指导
title: 自定义密码显示按钮
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， 兼容性， Web 平台， 密码展示， 眼睛图标
ms.openlocfilehash: af8120aad7316ffc051113591e770fa913814eb3
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327709"
---
# <span data-ttu-id="bf77e-104">自定义密码显示按钮</span><span class="sxs-lookup"><span data-stu-id="bf77e-104">Customize the password reveal button</span></span>  

<span data-ttu-id="bf77e-105">`password`Microsoft Edge 中的输入类型包括**密码显示**控件。</span><span class="sxs-lookup"><span data-stu-id="bf77e-105">The `password` input type in Microsoft Edge includes a **password reveal** control.</span></span>  <span data-ttu-id="bf77e-106">用户可以选择密码 **输入按钮** 来显示 **密码** 字段。</span><span class="sxs-lookup"><span data-stu-id="bf77e-106">A user may choose the **password input** button to reveal the **password** field.</span></span>  <span data-ttu-id="bf77e-107">显示 **的密码** 字段可帮助用户验证密码是否正确。</span><span class="sxs-lookup"><span data-stu-id="bf77e-107">The revealed **password** field helps the user verify if the password is correctly.</span></span>  <span data-ttu-id="bf77e-108">在用户输入密码字段中的文本后， 用户可以选择密码显示按钮或选择切换 输入 `Alt` + `F8` 的可见性。</span><span class="sxs-lookup"><span data-stu-id="bf77e-108">After a user has entered text in the **password** field, a user may choose the **password reveal** button or select `Alt`+`F8` to toggle visibility of the input.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="bf77e-109">密码 **字段** ，带点隐藏用户输入的字符。</span><span class="sxs-lookup"><span data-stu-id="bf77e-109">A **password** field with dots hiding the characters entered by a user.</span></span>  <span data-ttu-id="bf77e-110">密码 **显示** 按钮显示在密码 **字段的右侧** 。</span><span class="sxs-lookup"><span data-stu-id="bf77e-110">The **password reveal** button appears to the right of the **password** field.</span></span>
      
      :::image type="complex" source="./media/mdn-demo-password-reveal-off.msft.png" alt-text="眼睛形图标显示在隐藏密码文本的点旁边" lightbox="./media/mdn-demo-password-reveal-off.msft.png":::
         <span data-ttu-id="bf77e-112">眼睛形图标显示在隐藏密码文本的点旁边</span><span class="sxs-lookup"><span data-stu-id="bf77e-112">The eye-shaped icon appears next to the dots that hide the password text</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="bf77e-113">切换 **密码显示** 按钮，将眼睛图标更改为具有斜杠的目视图标，并显示原始密码文本。</span><span class="sxs-lookup"><span data-stu-id="bf77e-113">Toggle the **password reveal** button to change the eye icon to an eye icon with a slash through it, and to reveal the original password text.</span></span>  
      
      :::image type="complex" source="./media/mdn-demo-password-reveal-on.msft.png" alt-text="目视图标上有斜杠，并显示原始密码文本" lightbox="./media/mdn-demo-password-reveal-on.msft.png":::
         <span data-ttu-id="bf77e-115">目视图标上有斜杠，并显示原始密码文本</span><span class="sxs-lookup"><span data-stu-id="bf77e-115">The The eye-shaped icon has a slash on it and the original password text is displayed</span></span> :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="bf77e-116">默认情况下，密码 **显示** 按钮会插入到所有 HTML 元素的 Shadow DOM 中，并将其 `input` 设置为 `type` `"password"` 。</span><span class="sxs-lookup"><span data-stu-id="bf77e-116">By default, the **password reveal** button inserts into the Shadow DOM of all HTML `input` elements with the `type` set to `"password"`.</span></span>  <span data-ttu-id="bf77e-117">从 Microsoft Edge 版本 87 开始，用户或 [企业][DeployedgeMicrosoftEdgePoliciesPasswordrevealenabled] 可能会全局禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="bf77e-117">Starting with Microsoft Edge Version 87, users or [enterprises][DeployedgeMicrosoftEdgePoliciesPasswordrevealenabled] may disable this feature globally.</span></span>  <span data-ttu-id="bf77e-118">Web 设计人员和开发人员应该希望大多数 Microsoft Edge 用户拥有默认体验。</span><span class="sxs-lookup"><span data-stu-id="bf77e-118">You, web designers and developers, should expect most Microsoft Edge users to have the default experience.</span></span>  

## <span data-ttu-id="bf77e-119">删除密码显示控件</span><span class="sxs-lookup"><span data-stu-id="bf77e-119">Remove the password reveal control</span></span>  

<span data-ttu-id="bf77e-120">通过定位伪元素 **，** 可以完全删除密码显示 `::-ms-reveal` 按钮。</span><span class="sxs-lookup"><span data-stu-id="bf77e-120">You may completely remove the **password reveal** button by targeting the `::-ms-reveal` pseudo element.</span></span>  

```css
::-ms-reveal {
    display: none;
}
```  

<span data-ttu-id="bf77e-121">但是，应考虑利用密码 **显示** 按钮。</span><span class="sxs-lookup"><span data-stu-id="bf77e-121">However, you should consider taking advantage of the **password reveal** button.</span></span>  <span data-ttu-id="bf77e-122">本机 **密码显示** 按钮在行为 [中内置](#visibility-of-the-control) 了重要的安全措施。</span><span class="sxs-lookup"><span data-stu-id="bf77e-122">The native **password reveal** button has important [security measures](#visibility-of-the-control) built into the behavior.</span></span>  

## <span data-ttu-id="bf77e-123">自定义控件样式</span><span class="sxs-lookup"><span data-stu-id="bf77e-123">Customize the control style</span></span>  

<span data-ttu-id="bf77e-124">你可以改为修改密码显示按钮的样式，以更好地匹配网站的视觉语言， 而不是完全删除控件。</span><span class="sxs-lookup"><span data-stu-id="bf77e-124">Instead of fully removing the control, you may instead modify the styling of the **password reveal** button to better match the visual language of the website.</span></span>  <span data-ttu-id="bf77e-125">以下代码段提供了此类样式的示例。</span><span class="sxs-lookup"><span data-stu-id="bf77e-125">The following snippet provides an example of such styling.</span></span>  

```css
::-ms-reveal {
    border: 1px solid transparent;
    border-radius: 50%;
    box-shadow: 0 0 3px currentColor;
}
```  

<span data-ttu-id="bf77e-126">设置密码显示按钮样式时，请记住 **以下** 事项。</span><span class="sxs-lookup"><span data-stu-id="bf77e-126">Keep the following things in mind when you style the **password reveal** button.</span></span>  

*   <span data-ttu-id="bf77e-127">眼睛图标实现为背景图像。</span><span class="sxs-lookup"><span data-stu-id="bf77e-127">The eye icon implements as a background image.</span></span>  <span data-ttu-id="bf77e-128">若要向密码显示按钮添加背景 色，请使用 CSS `background-color` 属性而不是 `background` 速记属性。</span><span class="sxs-lookup"><span data-stu-id="bf77e-128">To add a background color to the **password reveal** button, use the CSS `background-color` property instead of the `background` shorthand property.</span></span>  
*   <span data-ttu-id="bf77e-129">你可以调整密码显示按钮 **的大小和** 比例。</span><span class="sxs-lookup"><span data-stu-id="bf77e-129">You may adjust the size and scale of the **password reveal** button.</span></span>  
    
    > [!NOTE]
    ><span data-ttu-id="bf77e-130">浏览器将隐藏密码输入控件边界之外的任何溢出。</span><span class="sxs-lookup"><span data-stu-id="bf77e-130">The browser hides any overflow outside of the bounds of the password input control.</span></span>  
    
*   <span data-ttu-id="bf77e-131">目前，没有状态选择器可用于设置密码显示按钮的 **切换状态** 样式。</span><span class="sxs-lookup"><span data-stu-id="bf77e-131">Currently, no state selectors are available to style the toggled state of the **password reveal** button.</span></span>  
    
## <span data-ttu-id="bf77e-132">控件的可见性</span><span class="sxs-lookup"><span data-stu-id="bf77e-132">Visibility of the control</span></span>  

<span data-ttu-id="bf77e-133">在 **用户向** 密码字段中输入文本之前，密码显示 **按钮** 不可用。</span><span class="sxs-lookup"><span data-stu-id="bf77e-133">The **password reveal** button is unavailable until the user enters text into the **password** field.</span></span>  <span data-ttu-id="bf77e-134">为了帮助确保用户的密码输入安全，浏览器将禁止以下方案中的按钮。</span><span class="sxs-lookup"><span data-stu-id="bf77e-134">To help keep the user's password entry secure, the browser suppresses the button in the following scenarios.</span></span>

*   <span data-ttu-id="bf77e-135">如果焦点从密码字段 **移** 开，浏览器将删除 **密码显示** 按钮。</span><span class="sxs-lookup"><span data-stu-id="bf77e-135">If focus moves away from the **password** field, the browser removes the **password reveal** button.</span></span>  
*   <span data-ttu-id="bf77e-136">如果脚本修改 **密码** 字段，浏览器将删除 **密码显示** 按钮。</span><span class="sxs-lookup"><span data-stu-id="bf77e-136">If scripts modify the **password** field, the browser removes the **password reveal** button.</span></span>  
*   <span data-ttu-id="bf77e-137">如果用户删除密码**显示按钮，** 则用户必须先删除密码字段的内容，然后密码显示**按钮**才能 再次显示。</span><span class="sxs-lookup"><span data-stu-id="bf77e-137">If a user removes the **password reveal** button, the user must delete the contents of the **password** field before the **password reveal** button displays again.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="bf77e-138">如果用户离开未锁定的设备，此功能可防止某人进行细微的调整以查看密码。</span><span class="sxs-lookup"><span data-stu-id="bf77e-138">This feature prevents someone from making a minor adjustment to view the password, should the user step away from an unlocked device.</span></span>
    
<span data-ttu-id="bf77e-139">如果**密码字段**使用密码管理器自动填充，则密码显示按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="bf77e-139">The **password reveal** button is unavailable if the **password** field autofills using the password manager.</span></span>  

<!-- links -->  

[DeployedgeMicrosoftEdgePoliciesPasswordrevealenabled]: /deployedge/microsoft-edge-policies#passwordrevealenabled "PasswordRevealEnabled - Microsoft Edge - 策略|Microsoft Docs"  
