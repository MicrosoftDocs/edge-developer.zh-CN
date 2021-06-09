---
description: 分析在将 div 元素与"检查工具"和"事件侦听器"选项卡一同使用的窗体上缺少键盘支持。
title: 使用 DevTools 分析表单上的键盘支持
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 16ec030ed433fc24d3b2b88bfb423a2479996dfe
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597291"
---
# <a name="analyze-keyboard-support-on-forms-using-the-devtools"></a><span data-ttu-id="91c8a-104">使用 DevTools 分析表单上的键盘支持</span><span class="sxs-lookup"><span data-stu-id="91c8a-104">Analyze keyboard support on forms using the DevTools</span></span>

<span data-ttu-id="91c8a-105">本文使用 **"检查\*\*\*\*工具"和**"事件侦听器"选项卡来分析在包含使用该元素的按钮的演示页面上缺少键盘 `div` 支持。</span><span class="sxs-lookup"><span data-stu-id="91c8a-105">This article uses the **Inspect** tool and **Event Listeners** tab to analyze the lack of keyboard support on a demo page which has buttons that use the `div` element.</span></span>

<span data-ttu-id="91c8a-106">在 **"百** 万"窗体上，"金额"按钮和 **"** 开始"按钮不能与键盘一起使用。</span><span class="sxs-lookup"><span data-stu-id="91c8a-106">On the **Donate** form, the amount buttons and **Donate** button doesn't work with a keyboard.</span></span>  <span data-ttu-id="91c8a-107">调试资金表单需要了解为什么缺少焦点样式未标记为问题自动测试工具（如 **问题** 工具）的问题。</span><span class="sxs-lookup"><span data-stu-id="91c8a-107">Debugging the donation form requires understanding why the lack of focus styling isn't flagged as a problem with automatic testing tools like the **Issues** tool.</span></span>  <span data-ttu-id="91c8a-108">本示例中，按钮使用元素实现，而这些工具不会将元素识别为窗体 `div` 上的控件。</span><span class="sxs-lookup"><span data-stu-id="91c8a-108">In this example, the buttons are implemented using `div` elements, which are not recognized by these tools as a control on a form.</span></span>

<span data-ttu-id="91c8a-109">若要使用"检查工具"和"事件侦听器"选项卡分析演示页上缺少键盘支持：</span><span class="sxs-lookup"><span data-stu-id="91c8a-109">To use the Inspect tool and Event Listeners tab to analyze the lack of keyboard support on the demo page:</span></span>

<!-- 1. Inspect tool: Accessibility section: keyboard-focusable row -->

1.  <span data-ttu-id="91c8a-110">在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="91c8a-110">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>
    
1.  <span data-ttu-id="91c8a-111">选择\*\*\*\* DevTools 左上角的"检查 \ (检查图标 \) "按钮，以便该按钮突出显示为 (![ ](../media/inspect-icon.msft.png) 蓝色) 。</span><span class="sxs-lookup"><span data-stu-id="91c8a-111">Select the **Inspect** \(![Inspect icon](../media/inspect-icon.msft.png)\) button in the top-left corner of DevTools so that the button is highlighted (blue).</span></span>

1.  <span data-ttu-id="91c8a-112">将鼠标悬停在 **50**个 **、100**个和 **200 个"支持** "按钮上。</span><span class="sxs-lookup"><span data-stu-id="91c8a-112">Hover over the **50**, **100**, and **200** donation buttons.</span></span>  <span data-ttu-id="91c8a-113">The Inspect tool appears on the webpage， as an overlay.</span><span class="sxs-lookup"><span data-stu-id="91c8a-113">The Inspect tool appears on the webpage, as an overlay.</span></span>  <span data-ttu-id="91c8a-114">" **检查"覆盖** 层的可键盘聚焦行显示，没有一个"支持"金额按钮可通过键盘访问，如带对角线的灰色圆圈所示。</span><span class="sxs-lookup"><span data-stu-id="91c8a-114">The **keyboard-focusable** row of the Inspect overlay shows that none of the donation amount buttons are keyboard-accessible, as indicated by a gray circle with diagonal line.</span></span>  <span data-ttu-id="91c8a-115">按钮没有名称，并且具有 其角色，因为它们是元素，这意味着辅助技术无法访问 `generic` `div` 按钮。</span><span class="sxs-lookup"><span data-stu-id="91c8a-115">The buttons have no name, and have a role of `generic` because they are `div` elements, which means that the buttons aren't accessible to assistive technology.</span></span>

    :::image type="complex" source="../media/a11y-testing-donation-button-info.msft.png" alt-text="检查表单的按钮时，会显示它们无法通过键盘访问" lightbox="../media/a11y-testing-donation-button-info.msft.png":::
        <span data-ttu-id="91c8a-117">检查表单的按钮时，会显示它们无法通过键盘访问</span><span class="sxs-lookup"><span data-stu-id="91c8a-117">Inspecting the buttons of the form shows that they aren't keyboard-accessible</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="91c8a-118">当 **"检查** "工具处于活动状态时，在网页上选择"其他 **输入"** 文本框，位于 **"** 开发工具"按钮上方。</span><span class="sxs-lookup"><span data-stu-id="91c8a-118">When the **Inspect** tool is active, on the webpage, select the **Other** input textbox, above the **Donate** button.</span></span>  <span data-ttu-id="91c8a-119">将 **打开"** 元素"工具，显示网页的 DOM 树。</span><span class="sxs-lookup"><span data-stu-id="91c8a-119">The **Elements** tool opens, showing the DOM tree for the webpage.</span></span>  <span data-ttu-id="91c8a-120">元素 `<input id="freedonation" class="smallinput">` 已选中。</span><span class="sxs-lookup"><span data-stu-id="91c8a-120">The element `<input id="freedonation" class="smallinput">` is selected.</span></span>

    ```html
    <div class="donationrow">
        <div class="donationbutton">50</div>
        <div class="donationbutton">100</div>
        <div class="donationbutton">200</div>
    </div>
    <div class="donationrow">
        <label for="freedonation">Other</label>
        <input id="freedonation" class="smallinput">
    </div>
    <div class="donationrow">
        <div class="submitbutton">Donate</div>
    </div>
    ```

    <span data-ttu-id="91c8a-121">在"其他"文本框上使用 和 元素是有效的，这意味着"其他"标签与输入 `label` `input` 文本框正确链接。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="91c8a-121">The use of the `label` and `input` elements on the **Other** textbox is valid, which means that the **Other** label is correctly linked with the input textbox.</span></span>  <span data-ttu-id="91c8a-122">文本框 `input` 还支持键盘访问。</span><span class="sxs-lookup"><span data-stu-id="91c8a-122">The `input` textbox is also keyboard-accessible.</span></span>  <span data-ttu-id="91c8a-123">表单的标记的其余部分是元素，它们易于设置样式， `div` 但没有任何语义含义。</span><span class="sxs-lookup"><span data-stu-id="91c8a-123">The rest of the form's markup are `div` elements, which are easy to style, but have no semantic meaning.</span></span>

    <!-- 2. Elements tool: Event Listeners tab -->

    <span data-ttu-id="91c8a-124">表单的功能是使用 JavaScript 创建的，您可以通过检查"事件侦听器"选项卡来测试这\*\*\*\* 一点，如下所示。</span><span class="sxs-lookup"><span data-stu-id="91c8a-124">The form's functionality is created with JavaScript, and you can test this by checking the **Event Listeners** tab, as follows.</span></span>

1.  <span data-ttu-id="91c8a-125">在 DOM 树中仍选择 元素后，选择"样式"选项卡右边的"事件侦听器"选项卡，然后 `<input id="freedonation" class="smallinput">` 展开\*\*\*\*\*\*\*\* `click` 事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="91c8a-125">With the element `<input id="freedonation" class="smallinput">` still selected in the DOM tree, select the **Event Listeners** tab to the right of the **Styles** tab, and then expand the `click` event listener.</span></span>

    :::image type="complex" source="../media/a11y-testing-event-handlers-on-button.msft.png" alt-text="显示使表单正常工作的 JavaScript 在哪里的 Event 侦听器工具" lightbox="../media/a11y-testing-event-handlers-on-button.msft.png":::
        <span data-ttu-id="91c8a-127">显示使表单正常工作的 JavaScript 在哪里的 Event 侦听器工具</span><span class="sxs-lookup"><span data-stu-id="91c8a-127">The Event listeners tool showing you where the JavaScript is that makes the form work</span></span>
    :::image-end:::

1.  <span data-ttu-id="91c8a-128">选择 `buttons.js:18` 链接。</span><span class="sxs-lookup"><span data-stu-id="91c8a-128">Select the `buttons.js:18` link.</span></span>  <span data-ttu-id="91c8a-129">将 **打开"** 源"工具，显示应用的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="91c8a-129">The **Sources** tool opens, showing the applied JavaScript.</span></span>

    :::image type="complex" source="../media/a11y-testing-form-handling-javascript.msft.png" alt-text="负责提供表单功能的 JavaScript，如"源"工具中所示" lightbox="../media/a11y-testing-form-handling-javascript.msft.png":::
        <span data-ttu-id="91c8a-131">负责提供表单功能的 JavaScript，如"源"工具中所示</span><span class="sxs-lookup"><span data-stu-id="91c8a-131">The JavaScript responsible for the donation form's functionality, shown in the Sources tool</span></span>
    :::image-end:::

```javascript
donations.addEventListener('click', e => {
  let t = e.target;
  if (t.classList.contains('donationbutton')) {
    if (currentbutton) { currentbutton.classList.remove('current'); }
    t.classList.add('current');
    currentbutton = t;
    e.preventDefault();
  }
  if (t.classList.contains('submitbutton')) {
    alert('Thanks for your donation!')
  } 
})
```

<span data-ttu-id="91c8a-132">使用事件读取按钮是一个不错的做法，因为事件在鼠标指针和键盘交互上 `click` `click` 触发。</span><span class="sxs-lookup"><span data-stu-id="91c8a-132">Using a `click` event to read the buttons is good practice, because a `click` event fires both on mouse pointer and keyboard interaction.</span></span>  <span data-ttu-id="91c8a-133">但是，由于元素不可通过键盘访问，并且此"开发工具"按钮作为元素 () 实现，因此除非使用鼠标或事件的另一个源（例如某些键盘上提供的特殊按钮）否则， `div` \*\*\*\* `div` 此 `<div class="submitbutton">Donate</div>` JavaScript `click` 功能永远不会运行。</span><span class="sxs-lookup"><span data-stu-id="91c8a-133">However, because a `div` element isn't keyboard-accessible, and this **Donate** button is implemented as a `div` element (`<div class="submitbutton">Donate</div>`), this JavaScript functionality never runs unless you use a mouse or another source of a `click` event, such as a special button available on some keyboards.</span></span>

<span data-ttu-id="91c8a-134">这是添加 JavaScript 以创建元素在本机提供的功能的经典 `button` 示例。</span><span class="sxs-lookup"><span data-stu-id="91c8a-134">This is a classic example where JavaScript was added to create functionality that `button` elements provide natively.</span></span>  <span data-ttu-id="91c8a-135">通过元素模拟按钮的功能 `div` 最终产生不可访问的体验。</span><span class="sxs-lookup"><span data-stu-id="91c8a-135">Simulating the functionality of buttons with `div` elements ended up producing an inaccessible experience.</span></span>


## <a name="see-also"></a><span data-ttu-id="91c8a-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91c8a-136">See also</span></span>

*  [<span data-ttu-id="91c8a-137">使用 DevTools 的辅助功能测试概述</span><span class="sxs-lookup"><span data-stu-id="91c8a-137">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="91c8a-138">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="91c8a-138">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
