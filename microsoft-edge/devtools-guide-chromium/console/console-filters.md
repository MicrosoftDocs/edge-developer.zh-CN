---
description: 了解如何筛选控制台消息
title: 开始在控制台中筛选消息
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: b493bb790b48bc1c4dca0e6802d2f638099b7644
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483367"
---
# <a name="filter-console-messages"></a>筛选控制台消息  

当您浏览 Web 时，您可能会发现 **控制台** 中会大量显示各种信息。  通常信息与自己不相关。  例如有关另一个开发人员在调试时记录实时项目的信息。  有关你无法更改的当前网站性能的违反和警告详细信息。  使用控制台的筛选器选项 **减少噪音是** 有意义的。  

## <a name="filter-by-log-level"></a>按记录级别筛选  

对象的每个 `console` 方法都有一个附加到它的严重级别。  严重性级别为 `Verbose` `Info` 、、 `Warning` 或 `Error` 。  显示 API 文档中的严重性 [级别][DevtoolsConsoleApi]。  例如， `console.log()` 是 `Info` -level 邮件，但 `console.error()` `Error` 是 -level 邮件。  

若要在控制台中 **筛选消息**，请使用" **日志级别"** 下拉菜单。  你可以切换每个级别的状态。  若要关闭每个级别，请删除每个级别旁边的选中标记。  

:::image type="complex" source="../media/console-filter-dropdown.msft.png" alt-text="下拉菜单使用日志级别筛选控制台消息" lightbox="../media/console-filter-dropdown.msft.png":::
    下拉菜单使用日志 **级别** 筛选控制台消息  
:::image-end:::  

由于未应用筛选器，下图显示数十条消息。  接下来，减少和管理邮件数量。  

:::image type="complex" source="../media/console-filter-displays-all.msft.png" alt-text="没有筛选器集意味着你可能会显示许多控制台消息" lightbox="../media/console-filter-displays-all.msft.png":::
    没有筛选器集意味着你可能会显示许多控制台消息  
:::image-end:::  

选择隐藏所有警告级别的消息，以减少噪音。  导航到" **日志级别** "下拉列表并取消选中 `Warnings` 该级别。  

:::image type="complex" source="../media/console-filter-hide-warning.msft.png" alt-text="在控制台中隐藏所有警告级别消息以筛选大部分噪音" lightbox="../media/console-filter-hide-warning.msft.png":::
    在控制台中隐藏所有警告级别 **消息** 以筛选大部分噪音  
:::image-end:::  

## <a name="filter-by-text"></a>按文本筛选  

如果要查看更多详细信息，若要使用文本筛选邮件，在"筛选器"文本框 **中** 键入字符串。  例如，在框中键入 以仅显示有关浏览器阻止 `block` 资源加载的消息。

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="显示包含单词块的邮件" lightbox="../media/console-filter-text.msft.png":::
    显示包含单词的消息 `block`  
:::image-end:::  

## <a name="filter-by-regular-expression"></a>按正则表达式筛选

[正则表达式是][MdnDocsWebJavascriptGuideRegularExpressions] 筛选邮件的一种强大方法。  例如，在 `/^Tracking/` **筛选器文本框中** 键入以仅显示以术语 开始的邮件 `Tracking` 。  如果你不熟悉正则表达式 [，RegExr][|::ref1::|Main] 是了解使用正则表达式的一个很好的资源。

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="使用"筛选器"文本框中的正则表达式显示以单词筛选器开始的邮件" lightbox="../media/console-filter-regex.msft.png":::
    使用"筛选器"文本框 `filter` 中的正则表达式显示以 **单词开始** 的邮件  
:::image-end:::  

## <a name="filter-by-message-source"></a>按邮件源筛选  

还可以定义要显示的消息类型以及每个消息的源位置（使用控制台的边**栏**）。 ****  为此，请选择"显示 **控制台边栏"** 按钮。  

:::image type="complex" source="../media/console-filter-sidebar-icon.msft.png" alt-text="若要打开边栏，请选择边栏图标" lightbox="../media/console-filter-sidebar-icon.msft.png":::
    若要打开 **边栏**，请选择" **显示控制台边栏"** 按钮  
:::image-end:::  

当 **边栏** 打开时，可以显示消息的个数以及每个消息的来源。  选项包括 `All messages` `User Messages` `Errors` 、、、、 `Warnings` 和 `Info` `Verbose` 。  

:::image type="complex" source="../media/console-filter-sidebar-open.msft.png" alt-text="控制台边栏显示源自于的不同源消息" lightbox="../media/console-filter-sidebar-open.msft.png":::
    控制台 **边栏** 显示源自于的不同源消息  
:::image-end:::  

选择任意选项以仅显示该类型的消息。  例如，若要显示用户消息，请选择用户消息选项来显示更少的噪音。

:::image type="complex" source="../media/console-filter-select-user-messages.msft.png" alt-text="选择使用边栏中的筛选器在控制台中仅显示用户消息" lightbox="../media/console-filter-select-user-messages.msft.png":::
    选择使用边栏中的筛选器在 **控制台** 中仅显示 **用户消息**  
:::image-end:::  

若要筛选更多内容并展开选择，请选择它旁边的三角形图标。  这样，你将获得更多选择来仅显示来自特定源的邮件。  

:::image type="complex" source="../media/console-filter-sidebar-open-arrow.msft.png" alt-text="选择箭头图标可展开每个部分" lightbox="../media/console-filter-sidebar-open-arrow.msft.png":::
    选择箭头图标可展开每个部分  
:::image-end:::  

:::image type="complex" source="../media/console-filter-user-message-by-source.msft.png" alt-text="选择任何使用类型和源进行筛选的新选项" lightbox="../media/console-filter-user-message-by-source.msft.png":::
    选择任何使用类型和源进行筛选的新选项  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleApi]: ./api.md "控制台 API 参考 | Microsoft Docs"  

[MdnDocsWebJavascriptGuideRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正则表达式 | MDN"  

[RegExrMain]: https://regexr.com "RegExr"  
