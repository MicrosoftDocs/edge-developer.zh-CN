---
description: 提供有关自定义显示密码显示按钮的指南
title: 自定义密码显示按钮
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， 兼容性， Web 平台， 密码展示， 眼睛图标
ms.openlocfilehash: 93f618d28e5fa2f16dda87b4122a097ef40618c9
ms.sourcegitcommit: 1f0b2534b51417bb19d05945fea54ddad977e88f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2021
ms.locfileid: "11526156"
---
# <a name="customize-the-password-reveal-button"></a>自定义密码显示按钮  

`password`Microsoft Edge 中的输入类型包括**密码显示**控件。  用户可以选择密码 **输入按钮** 来显示 **密码** 字段。  显示 **的密码** 字段可帮助用户验证密码是否正确。  在用户输入密码字段中的文本后，**** 用户可以选择密码显示按钮或选择**** `Alt` + `F8` 切换输入的可见性。  

:::row:::
   :::column span="":::
      带 **点** 隐藏用户输入的字符的密码字段。  密码 **显示** 按钮显示在密码 **字段的右侧** 。
      
      :::image type="complex" source="./media/mdn-demo-password-reveal-off.msft.png" alt-text="目视图标显示在隐藏密码文本的点旁边" lightbox="./media/mdn-demo-password-reveal-off.msft.png":::
         目视图标显示在隐藏密码文本的点旁边  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      切换 **密码显示** 按钮，将眼睛图标更改为带斜杠的目视图标，并显示原始密码文本。  
      
      :::image type="complex" source="./media/mdn-demo-password-reveal-on.msft.png" alt-text="目视图标上有一个斜杠，并且显示原始密码文本" lightbox="./media/mdn-demo-password-reveal-on.msft.png":::
         目视图标上有一个斜杠，并且显示原始密码文本 :::image-end:::  
   :::column-end:::
:::row-end:::  

默认情况下，密码 **显示** 按钮插入到所有 HTML 元素的 Shadow DOM 中，并将 `input` 设置为 `type` `"password"` 。  从 Microsoft Edge 版本 87 开始，用户或 [企业][DeployedgeMicrosoftEdgePoliciesPasswordrevealenabled] 可能会全局禁用此功能。  您（Web 设计人员和开发人员）应该希望大多数 Microsoft Edge 用户拥有默认体验。  

## <a name="remove-the-password-reveal-control"></a>删除密码显示控件  

通过定位伪 **元素，** 你可以完全删除密码显示 `::-ms-reveal` 按钮。  

```css
::-ms-reveal {
    display: none;
}
```  

但是，你应该考虑利用密码 **显示** 按钮。  本机 **密码显示** 按钮在行为 [中](#visibility-of-the-control) 内置了重要的安全措施。  

## <a name="customize-the-control-style"></a>自定义控件样式  

你可以改为修改密码显示按钮的样式，以更好地匹配网站的视觉语言，**** 而不是完全删除控件。  以下代码段提供了此类样式的示例。  

```css
::-ms-reveal {
    border: 1px solid transparent;
    border-radius: 50%;
    box-shadow: 0 0 3px currentColor;
}
```  

设置密码显示按钮样式时，请记住 **以下** 事项。  

*   目视图标实现为背景图像。  若要向密码显示按钮添加背景 **色** ，请使用 CSS `background-color` 属性而不是 `background` 速记属性。  
*   你可以调整密码显示按钮的大小 **和** 规模。  
    
    > [!NOTE]
    >浏览器将隐藏密码输入控件边界之外的任何溢出。  
    
*   目前，没有状态选择器可用于设置密码显示按钮的切换 **状态** 样式。  
    
## <a name="visibility-of-the-control"></a>控件的可见性  

在 **用户向** 密码字段中输入文本之前，密码显示 **按钮不可用** 。  为了帮助确保用户的密码输入安全，浏览器在下列情况下禁止显示该按钮。

*   如果焦点从密码 **字段移** 开，浏览器将删除 **密码显示** 按钮。  
*   如果脚本修改 **密码** 字段，浏览器将删除 **密码显示** 按钮。  

如果**删除密码**显示按钮，用户必须删除密码字段的内容，密码**显示按钮**才能**** 再次显示。 如果用户离开未锁定的设备，此行为可防止某人对显示密码进行细微的调整。
    
如果使用**密码**管理器自动填充密码字段，**** 则密码显示按钮不可用。  

<!-- links -->  

[DeployedgeMicrosoftEdgePoliciesPasswordrevealenabled]: /deployedge/microsoft-edge-policies#passwordrevealenabled "PasswordRevealEnabled - Microsoft Edge - 策略|Microsoft Docs"  
