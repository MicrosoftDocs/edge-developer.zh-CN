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
# <a name="analyze-keyboard-support-on-forms-using-the-devtools"></a>使用 DevTools 分析表单上的键盘支持

本文使用 **"检查****工具"和**"事件侦听器"选项卡来分析在包含使用该元素的按钮的演示页面上缺少键盘 `div` 支持。

在 **"百** 万"窗体上，"金额"按钮和 **"** 开始"按钮不能与键盘一起使用。  调试资金表单需要了解为什么缺少焦点样式未标记为问题自动测试工具（如 **问题** 工具）的问题。  本示例中，按钮使用元素实现，而这些工具不会将元素识别为窗体 `div` 上的控件。

若要使用"检查工具"和"事件侦听器"选项卡分析演示页上缺少键盘支持：

<!-- 1. Inspect tool: Accessibility section: keyboard-focusable row -->

1.  在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。
    
1.  选择**** DevTools 左上角的"检查 \(检查图标 \) "按钮，以便该按钮突出显示为 (![ ](../media/inspect-icon.msft.png) 蓝色) 。

1.  将鼠标悬停在 **50**个 **、100**个和 **200 个"支持** "按钮上。  The Inspect tool appears on the webpage， as an overlay.  " **检查"覆盖** 层的可键盘聚焦行显示，没有一个"支持"金额按钮可通过键盘访问，如带对角线的灰色圆圈所示。  按钮没有名称，并且具有 其角色，因为它们是元素，这意味着辅助技术无法访问 `generic` `div` 按钮。

    :::image type="complex" source="../media/a11y-testing-donation-button-info.msft.png" alt-text="检查表单的按钮时，会显示它们无法通过键盘访问" lightbox="../media/a11y-testing-donation-button-info.msft.png":::
        检查表单的按钮时，会显示它们无法通过键盘访问
    :::image-end:::
    
1.  当 **"检查** "工具处于活动状态时，在网页上选择"其他 **输入"** 文本框，位于 **"** 开发工具"按钮上方。  将 **打开"** 元素"工具，显示网页的 DOM 树。  元素 `<input id="freedonation" class="smallinput">` 已选中。

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

    在"其他"文本框上使用 和 元素是有效的，这意味着"其他"标签与输入 `label` `input` 文本框正确链接。 **** ****  文本框 `input` 还支持键盘访问。  表单的标记的其余部分是元素，它们易于设置样式， `div` 但没有任何语义含义。

    <!-- 2. Elements tool: Event Listeners tab -->

    表单的功能是使用 JavaScript 创建的，您可以通过检查"事件侦听器"选项卡来测试这**** 一点，如下所示。

1.  在 DOM 树中仍选择 元素后，选择"样式"选项卡右边的"事件侦听器"选项卡，然后 `<input id="freedonation" class="smallinput">` 展开******** `click` 事件侦听器。

    :::image type="complex" source="../media/a11y-testing-event-handlers-on-button.msft.png" alt-text="显示使表单正常工作的 JavaScript 在哪里的 Event 侦听器工具" lightbox="../media/a11y-testing-event-handlers-on-button.msft.png":::
        显示使表单正常工作的 JavaScript 在哪里的 Event 侦听器工具
    :::image-end:::

1.  选择 `buttons.js:18` 链接。  将 **打开"** 源"工具，显示应用的 JavaScript。

    :::image type="complex" source="../media/a11y-testing-form-handling-javascript.msft.png" alt-text="负责提供表单功能的 JavaScript，如源工具中所示" lightbox="../media/a11y-testing-form-handling-javascript.msft.png":::
        负责提供表单功能的 JavaScript，如"源"工具中所示
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

使用事件读取按钮是一个不错的做法，因为事件在鼠标指针和键盘交互上 `click` `click` 触发。  但是，由于元素不可通过键盘访问，并且此"开发工具"按钮作为元素 () 实现，因此除非使用鼠标或事件的另一个源（例如某些键盘上提供的特殊按钮）否则， `div` **** `div` 此 `<div class="submitbutton">Donate</div>` JavaScript `click` 功能永远不会运行。

这是添加 JavaScript 以创建元素在本机提供的功能的经典 `button` 示例。  通过元素模拟按钮的功能 `div` 最终产生不可访问的体验。


## <a name="see-also"></a>另请参阅

*  [使用 DevTools 的辅助功能测试概述](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
