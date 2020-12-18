---
description: 使你的扩展可供不同的语言访问，并借助国际化指南测试语言字符串。
title: 扩展 - 国际化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: bbbc847ebd2103cba2eca8a791009b4e72f93a6f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232628"
---
# 国际化  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

为了使你的扩展可供各种不同人员访问，请务必考虑其他国家/地区进行开发。 Microsoft Edge 扩展允许你向扩展中添加不同的语言字符串，以便可以轻松地更改其语言。

有关使扩展国际化的信息，请查看 MDN 的 [国际化指南](https://developer.mozilla.org/Add-ons/WebExtensions/Internationalization)。


## 测试语言

若要测试语言字符串，首先需要将 Windows 显示语言设置为要测试的语言。

按照以下步骤更改 Windows 显示语言：

1. 打开"设置"应用。

   ![设置应用程序](./../media/loc-settings.png)
2. 选择"时间&语言"。
3. 选择"&语言"。
4. 选择"+ 添加语言"，将语言添加到可能的语言列表中。
5. 从"语言"列表中选择要测试的语言。
6. 选择"设置为默认值"按钮 (可能需要重启电脑) 。
7. 打开 Microsoft Edge 并验证为区域设置定义的字符串是否按预期显示。

通过使用 [NavigatorLanguage.language](https://developer.mozilla.org/docs/Web/API/NavigatorLanguage/language) 属性，可以验证 Microsoft Edge 确定为 Windows 显示语言的语言是否正确。

单击下面的 CodePen 中的按钮，查看浏览器的显示语言。

<iframe height='300' scrolling='no' title='获取区域设置' src='//codepen.io/MSEdgeDev/embed/VaRWwR/?height=300&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>请参阅在 CodePen 上通过 <a href='https://codepen.io/MSEdgeDev/pen/VaRWwR/'> </a> MSEdgeDev <a href='http://codepen.io/MSEdgeDev'> (@MSEdgeDev) </a> <a href='http://codepen.io'> 获取区域设置 </a> 。
</iframe>
