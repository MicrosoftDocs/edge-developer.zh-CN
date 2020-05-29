---
description: 使您的扩展可用于不同语言，并通过国际化指南测试语言字符串。
title: 扩展-国际化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: d1f553d0e3e39192e68665fe6720daa811777c0b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563266"
---
# 国际化  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

为了使您的扩展可供各种不同的人员使用，请务必与其他国家/地区的人员进行开发。 Microsoft Edge 扩展允许你将不同的语言字符串添加到你的扩展名，以便可以轻松更改其语言。

有关对扩展进行国际化的详细信息，请查看 MDN 的[国际化指南](https://developer.mozilla.org/Add-ons/WebExtensions/Internationalization)。


## 测试语言

若要测试语言字符串，首先需要将 Windows 显示语言设置为要测试的语言。

请按照下列步骤更改 Windows 显示语言：

1. 打开 "设置" 应用。

   ![设置应用程序](./../media/loc-settings.png)
2. 选择 "时间 & 语言"。
3. 选择 "区域 & 语言"。
4. 选择 "+ 添加语言" 将语言添加到可能语言的列表。
5. 从 "语言" 列表中选择要测试的语言。
6. 选择 "设为默认值" 按钮（可能需要重启电脑）。
7. 打开 Microsoft Edge 并验证为区域设置定义的字符串是否按预期方式显示。

通过使用[NavigatorLanguage](https://developer.mozilla.org/docs/Web/API/NavigatorLanguage/language)属性，你可以验证 Microsoft Edge 是否已确定为 Windows 显示语言的语言是正确的。

单击以下 CodePen 中的按钮以查看浏览器的显示语言。

<iframe height='300' scrolling='no' title='获取区域设置' src='//codepen.io/MSEdgeDev/embed/VaRWwR/?height=300&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>请参阅 <a href='https://codepen.io/MSEdgeDev/pen/VaRWwR/'> </a> CodePen 上的 "通过 MSEdgeDev （ <a href='http://codepen.io/MSEdgeDev'> @MSEdgeDev）获取区域设置" </a> <a href='http://codepen.io'> </a> 。
</iframe>
