---
ms.assetid: 2bc29371-4f2e-4b59-a588-30b107d751f6
description: 了解 Microsoft Edge 如何为网页提供阅读视图以启用无加载项阅读。
title: 阅读视图 - 开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 30c01d61ff896cca7b0af90b345a8619307f91c0
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232572"
---
# 阅读视图  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Microsoft Edge 提供了一个阅读视图，使网页的阅读体验更简洁、更像书籍一样，而不会分散页面上无关内容或其他辅助内容的干扰。  阅读视图可以从阅读视图**\ (** 书籍图标\) 按钮或与中切换 `Ctrl` + `Shift` + `R` 。  阅读视图从页面中提取以下元数据：  

*   Title
*   作者
*   日期
*   发布者
*   基准图像\ (\) 
*   基准图像的标题\ (s\) 
*   辅助图像
*   页面的主文本内容
*   版权

然后，用户可以从 Microsoft Edge 设置面板调整页面对比度 **和字体** 大小。  

## 元数据提取  

下面是通过阅读视图呈现的页面元数据的详细信息。  

### Title  

若要确保阅读视图呈现您文章的标题，  

*   在 `title` 标头中包括元素  
*   包含元标记 `name="title"`  
*   将文章正文中的标题文本与元标记的内容字符串相匹配。  管道 \ (\) 防止读者视图变为活动状态，请尝试改为使用连字符 `|` \ (`-` \) 。  

### 作者  

阅读视图将查找具有 `class = "byline-name"` 的元素。  最佳做法是，将作者姓名放在标题之后和文章正文之前。  

```html
<div class="byline-name">Author name</div>
```  

### 日期  

阅读视图将在同一行中同时呈现发布者和日期信息，并添加其他样式以突出显示此信息。  文章的发布日期将完全呈现在字符串中。  阅读视图不会转换为特定的日期格式。  

如果你的文章正文中包含日期，并且希望阅读视图呈现它，请为包含日期的元素分配类 `'dateline'` ：  

```html
<div class="dateline"> Wednesday, September 18, 2013 7:38 AM </div>
```  

如果在文章正文中没有日期，但希望阅读视图呈现日期，请使用元标记 `name='displaydate'` ：  

```html
<meta name="displaydate" content=" Wednesday, September 18, 2013 7:38 AM ">
```  

### 发布者  

阅读视图将查找 Open Graph 协议 `"og:site_name"` 以呈现发布者信息。  它还查找作为页面上发布者信息的辅助指示器的任何 html 标记 `source_organization` `publisher` 中的属性。  发布者文本将超链接到使用阅读视图页面超链接样式的页面的 URL。  

```html
<meta content="Name of organization source" property="og:site_name">
```  

### Images  

阅读视图捕获宽度为 >= 400px 且纵横比为 >= 1/3 且 =< 3.0 的原始图像。  不满足这些尺寸的图像仍可以提取，例如宽度小于 400px 但具有标题的图像。  第一个符合条件的图像将成为文章的基准图像。  基准图像呈现为第一段内容，并给定完整列宽。  以下所有图像都呈现为文章中的内嵌图像。  

### 字幕  

最佳做法是，将 [图像放在包含](https://developer.mozilla.org/docs/Web/HTML/Element/figure) 不超过两个嵌套图形标记的 [图标记](https://developer.mozilla.org/docs/Web/HTML/Element/figcaption) 中。  

### 正文  

为了确保页面的所有正文文本都由阅读视图捕获，让大多数文章文本保持相同的字号和 DOM 深度会有所帮助。  阅读视图算法允许此规则出现一些偏差，以便发布者可以自由地添加对行或字词的强调。  

### 版权  

阅读视图提取并显示由元标记表示的版权信息，如果不存在元标记信息，则显示包含版权 `name = "copyright"` \ (`©` \) 符号的文本节点。  阅读视图在文章正文的末尾显示版权信息，其样式使用比正文文本更小的字体大小。  

```html
<meta name="copyright" content="Your copyright information">
```  

## 选择退出阅读视图  

如果您觉得内容不适合阅读视图，可以使用以下元标记选择退出此功能：  

```html
<meta name="IE_RM_OFF" content="true">
```  

通过此标记，当用户**** 查看页面时，"阅读视图"按钮不会显示在地址栏中。  
