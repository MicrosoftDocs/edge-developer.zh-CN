---
ms.assetid: 2bc29371-4f2e-4b59-a588-30b107d751f6
description: 请参阅 Microsoft Edge 如何为网页提供阅读视图以启用无加载项读取。
title: 阅读视图 - 开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.openlocfilehash: 0d2076a63f97ecf2b4699795b0036736d0f95c9c
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941997"
---
# 阅读视图  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Microsoft Edge 提供了阅读视图，可更简化、更类似于书页的阅读体验，而无需分不像页面中不相关或其他辅助内容的分开度。  可以通过"阅读"视图 \cn (/for/**Reading view**打开或 ) 关闭阅读视图。 `Ctrl` + `Shift` + `R`  阅读视图从页面中提取以下元数据：  

*   Title
*   作者
*   日期
*   发布者
*   Dominant image\ (s\) 
*   dominant image\ (s\) 
*   辅助图像
*   页面的主要文本内容
*   版权

然后，用户可以从 Microsoft Edge 设置面板中调整页面对比度和 **字** 号。  

## 元数据提取  

以下是读取视图呈现的页面元数据的详细信息。  

### Title  

要确保阅读视图呈现文章的标题，请执行以下操作：  

*   在页 `title` 眉中包含元素  
*   包含一个与 `name="title"`  
*   将文章正文中的标题文本与元标记的内容字符串匹配。  内容字符串中的管道 `|` \ (\) 可防止读者视图激活，请尝试改用短字符 \ (`-` \) 。  

### 作者  

阅读视图将查找具有的元素 `class = "byline-name"` 。  最佳做法是将作者姓名放在标题后面，将文章正文之前置于书名之前。  

```html
<div class="byline-name">Author name</div>
```  

### 日期  

阅读视图将在同一行中同时呈现发布者和日期信息，并提供一些其他样式来突出显示此信息。  文章的发布日期会原本好呈现在字符串中显示。  阅读视图不会转换为特定的日期格式。  

如果文章正文中具有日期，并希望阅读视图呈现日期，请为其元素分配一个包含如下内容的日期 `'dateline'` ：  

```html
<div class="dateline"> Wednesday, September 18, 2013 7:38 AM </div>
```  

如果文章正文中没有日期，但希望阅读视图呈现日期，请使用元标记 `name='displaydate'` ：  

```html
<meta name="displaydate" content=" Wednesday, September 18, 2013 7:38 AM ">
```  

### 发布者  

阅读视图将查找开放图协议 `"og:site_name"` 来呈现发布者信息。  还在任何 html `source_organization` `publisher` 标记中查找和属性作为页面上的发布者信息的辅助指示器。  使用阅读视图页面超链接样式将超链接发布者文本超链接到页面 URL。  

```html
<meta content="Name of organization source" property="og:site_name">
```  

### Images  

阅读视图捕获大多数原始图像，其宽度为 <&gt;= 400 像素且纵位比 &gt;= 1/3 且 =&lt; 3.0。  不符合这些维度的图像仍可能得到提取，例如宽度小于 400px 但带有标题的图像。  第一个符合资格图像成为文章的主要图像。  主要图像将呈现为内容的第一部分并提供全列宽。  下面的所有图像都呈现为该文章中的嵌入式图像。  

### 字幕  

最佳实践是将图像放在不带两个[figure](https://developer.mozilla.org/docs/Web/HTML/Element/figure)以上嵌[套数字标记](https://developer.mozilla.org/docs/Web/HTML/Element/figcaption)的数字标记中。  

### 正文  

为确保您的页的所有正文文本都通过阅读视图捕获，将本文的大部分文本保持相同的字体大小和 DOM 深度。  通过阅读视图算法，可以进行此规则的一些发展，因此发布者可以自由地对线条或字词添加强调效果。  

### 版权  

阅读视图提取并显示含有元标记的版权信息，或者如果 `name = "copyright"` 不存在 meta 标记信息，或者如果不存在 meta 标记信息，则一个包含版权 \ (`©` \) 符号的文本节点。  阅读视图在文章主体的末尾显示版权信息，使用比主正文文本设置样式的样式。  

```html
<meta name="copyright" content="Your copyright information">
```  

## 选择不阅读视图  

如果您认为内容不是合适的阅读视图，你可以使用以下 meta 标记选择退出此功能：  

```html
<meta name="IE_RM_OFF" content="true">
```  

使用此标记，当用户查看 **页面时，"** 阅读视图"按钮不会显示在地址栏中。  
