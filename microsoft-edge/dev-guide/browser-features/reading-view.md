---
ms.assetid: 2bc29371-4f2e-4b59-a588-30b107d751f6
description: 请参阅 Microsoft Edge 如何提供网页的阅读视图以启用外接程序阅读。
title: 开发人员指南-阅读视图
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: e84edb5cc29b644939895f2996c50f3b4ec23379
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562632"
---
# 阅读视图

Microsoft Edge 为*阅读视图*提供了一种更简洁的、书籍喜欢的网页阅读体验，不会干扰页面上的不相关或其他辅助内容。 可通过**地址栏**上的 "**阅读视图**" （"书籍" 图标）按钮（或按**Ctrl**  +  **Shift**  +  **R**）打开或关闭 "阅读" 视图。 阅读视图从页面中提取以下元数据：

* Title
* 作者
* 日期
* 发布者
* 主导图像
* 主导图像的标题
* 次映像
* 页面的主要文本内容
* 版权

然后，用户可以从 "Microsoft Edge**设置**" 面板调整页面对比度和字号。

## 元数据提取


下面是 "阅读视图" 呈现的页面元数据的详细信息。

### Title

若要确保阅读视图呈现文章的标题，请执行以下操作：

* 在页眉中包含**标题**元素
* 包含 meta 标记 `name="title"`
* 将文章正文中的标题文本与 meta 标记的内容字符串匹配。 `|`内容字符串中的管道阻止了 "阅读器" 视图处于活动状态，请尝试 `-` 改用 hypens。

### 作者

阅读视图将查找包含的元素 `class = "byline-name"` 。 最佳做法是将作者姓名置于标题之后和文章正文之前。

```html
<div class="byline-name">Author name</div>
```

### 日期

"阅读" 视图会将发布者和日期信息一起呈现在同一行上，并提供其他样式来突出显示此信息。 项目的发布日期将完全呈现为字符串中显示的内容。 阅读视图不转换为特定的日期格式。

如果你的文章正文中有日期，并且希望阅读视图呈现它，请使用以下类分配包含日期的元素 `'dateline'` ：

```html
<div class="dateline"> Wednesday, September 18, 2013 7:38 AM </div>
```

如果在文章正文中没有日期，但希望阅读视图呈现日期，请使用 meta 标记 `name='displaydate'` ：

```html
<meta name="displaydate" content=" Wednesday, September 18, 2013 7:38 AM ">
```

### 发布者

"阅读视图" 将查找 "*打开图形*" 协议 `"og:site_name"` 以呈现发布者信息。 它还 `source_organization` `publisher` 在任何 html 标记中查找和属性，作为页面上 publisher 信息的辅助指示器。 Publisher 文本将使用 "阅读视图" 页面超链接样式链接到页面的 URL。

```html
<meta content="Name of organization source" property="og:site_name">
```

### Images

"阅读" 视图捕获最大宽度为 >= 400px 和纵横比 >= 1/3 和 =< 3.0 的原始图像。 不符合这些尺寸的图像仍可提取，例如小于400px 的图像，但其宽度较小，但具有标题。 第一个符合条件的图像成为文章的主导图像。 主导图像呈现为第一条内容，并给定完整的列宽度。 所有以下图像在项目中呈现为内联图像。

### 字幕

最佳做法是将图像放置在不超过两个嵌套的[figcaption](https://msdn.microsoft.com/library/gg593037(v=vs.85).aspx)标记的[插图](https://msdn.microsoft.com/library/gg593038(v=vs.85).aspx)标签中。

### 正文

若要确保你的页面的所有正文文本都通过 "阅读" 视图捕获，它有助于将大部分文章文本保持相同的字体大小和 DOM 深度。 "阅读" 视图算法允许使用此规则的某些差异，以便发布者可以自由地为线条或字词添加强调。

### 版权

阅读视图提取并显示 meta 标记所表示的版权信息 `name = "copyright"` ，或者如果没有 meta 标记信息，则包含版权（**©**）符号的文本节点。 阅读视图在文章正文正文的末尾显示版权信息，使用较小字号的字体，样式比正文文本更小。

```html
<meta name="copyright" content="Your copyright information">
```

## 退出阅读视图


如果你认为内容不适合阅读视图，可以使用以下 meta 标记来选择退出此功能：

```html
<meta name="IE_RM_OFF" content="true">
```

通过此标记，当用户查看您的页面时，地址栏中不会显示 "**阅读视图**" 按钮。
