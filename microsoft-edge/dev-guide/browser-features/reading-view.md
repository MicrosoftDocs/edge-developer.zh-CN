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
# <span data-ttu-id="94d01-104">阅读视图</span><span class="sxs-lookup"><span data-stu-id="94d01-104">Reading view</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="94d01-105">Microsoft Edge 提供了阅读视图，可更简化、更类似于书页的阅读体验，而无需分不像页面中不相关或其他辅助内容的分开度。</span><span class="sxs-lookup"><span data-stu-id="94d01-105">Microsoft Edge provides a reading view for a more streamlined, book-like reading experience of webpages without the distraction of unrelated or other secondary content on the page.</span></span>  <span data-ttu-id="94d01-106">可以通过"阅读"视图 \cn (/for/**Reading view**打开或 ) 关闭阅读视图。 `Ctrl` + `Shift` + `R`</span><span class="sxs-lookup"><span data-stu-id="94d01-106">Reading view can be toggled on or off from the **Reading view** \(book icon\) button on the address bar or with `Ctrl`+`Shift`+`R`.</span></span>  <span data-ttu-id="94d01-107">阅读视图从页面中提取以下元数据：</span><span class="sxs-lookup"><span data-stu-id="94d01-107">Reading view extracts the following metadata from a page:</span></span>  

*   <span data-ttu-id="94d01-108">Title</span><span class="sxs-lookup"><span data-stu-id="94d01-108">Title</span></span>
*   <span data-ttu-id="94d01-109">作者</span><span class="sxs-lookup"><span data-stu-id="94d01-109">Author</span></span>
*   <span data-ttu-id="94d01-110">日期</span><span class="sxs-lookup"><span data-stu-id="94d01-110">Date</span></span>
*   <span data-ttu-id="94d01-111">发布者</span><span class="sxs-lookup"><span data-stu-id="94d01-111">Publisher</span></span>
*   <span data-ttu-id="94d01-112">Dominant image\ (s\) </span><span class="sxs-lookup"><span data-stu-id="94d01-112">Dominant image\(s\)</span></span>
*   <span data-ttu-id="94d01-113">dominant image\ (s\) </span><span class="sxs-lookup"><span data-stu-id="94d01-113">Captions of dominant image\(s\)</span></span>
*   <span data-ttu-id="94d01-114">辅助图像</span><span class="sxs-lookup"><span data-stu-id="94d01-114">Secondary images</span></span>
*   <span data-ttu-id="94d01-115">页面的主要文本内容</span><span class="sxs-lookup"><span data-stu-id="94d01-115">Main text content of the page</span></span>
*   <span data-ttu-id="94d01-116">版权</span><span class="sxs-lookup"><span data-stu-id="94d01-116">Copyright</span></span>

<span data-ttu-id="94d01-117">然后，用户可以从 Microsoft Edge 设置面板中调整页面对比度和 **字** 号。</span><span class="sxs-lookup"><span data-stu-id="94d01-117">Users can then adjust the page contrast and font size from the Microsoft Edge **Settings** panel.</span></span>  

## <span data-ttu-id="94d01-118">元数据提取</span><span class="sxs-lookup"><span data-stu-id="94d01-118">Metadata extraction</span></span>  

<span data-ttu-id="94d01-119">以下是读取视图呈现的页面元数据的详细信息。</span><span class="sxs-lookup"><span data-stu-id="94d01-119">Here are details of the page metadata rendered by reading view.</span></span>  

### <span data-ttu-id="94d01-120">Title</span><span class="sxs-lookup"><span data-stu-id="94d01-120">Title</span></span>  

<span data-ttu-id="94d01-121">要确保阅读视图呈现文章的标题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="94d01-121">To ensure Reading view renders your article's title:</span></span>  

*   <span data-ttu-id="94d01-122">在页 `title` 眉中包含元素</span><span class="sxs-lookup"><span data-stu-id="94d01-122">Include a `title` element in your header</span></span>  
*   <span data-ttu-id="94d01-123">包含一个与</span><span class="sxs-lookup"><span data-stu-id="94d01-123">Include a meta tag with</span></span> `name="title"`  
*   <span data-ttu-id="94d01-124">将文章正文中的标题文本与元标记的内容字符串匹配。</span><span class="sxs-lookup"><span data-stu-id="94d01-124">Match the title text in your article body with the content string of your meta tag.</span></span>  <span data-ttu-id="94d01-125">内容字符串中的管道 `|` \ (\) 可防止读者视图激活，请尝试改用短字符 \ (`-` \) 。</span><span class="sxs-lookup"><span data-stu-id="94d01-125">Pipes \(`|`\) in your content string prevent the reader view from becoming active, try using hyphens \(`-`\) instead.</span></span>  

### <span data-ttu-id="94d01-126">作者</span><span class="sxs-lookup"><span data-stu-id="94d01-126">Author</span></span>  

<span data-ttu-id="94d01-127">阅读视图将查找具有的元素 `class = "byline-name"` 。</span><span class="sxs-lookup"><span data-stu-id="94d01-127">Reading View will look for an element with `class = "byline-name"`.</span></span>  <span data-ttu-id="94d01-128">最佳做法是将作者姓名放在标题后面，将文章正文之前置于书名之前。</span><span class="sxs-lookup"><span data-stu-id="94d01-128">Best practice is to place the author name after the title and before the article body.</span></span>  

```html
<div class="byline-name">Author name</div>
```  

### <span data-ttu-id="94d01-129">日期</span><span class="sxs-lookup"><span data-stu-id="94d01-129">Date</span></span>  

<span data-ttu-id="94d01-130">阅读视图将在同一行中同时呈现发布者和日期信息，并提供一些其他样式来突出显示此信息。</span><span class="sxs-lookup"><span data-stu-id="94d01-130">Reading view will render the publisher and date information together on the same line, with additional styling to highlight this information.</span></span>  <span data-ttu-id="94d01-131">文章的发布日期会原本好呈现在字符串中显示。</span><span class="sxs-lookup"><span data-stu-id="94d01-131">The article's publishing date will render exactly as it appears in the string.</span></span>  <span data-ttu-id="94d01-132">阅读视图不会转换为特定的日期格式。</span><span class="sxs-lookup"><span data-stu-id="94d01-132">Reading view does not convert to a specific date format.</span></span>  

<span data-ttu-id="94d01-133">如果文章正文中具有日期，并希望阅读视图呈现日期，请为其元素分配一个包含如下内容的日期 `'dateline'` ：</span><span class="sxs-lookup"><span data-stu-id="94d01-133">If you have a date in your article body and would like Reading view to render it, assign the element containing the date with the class `'dateline'`:</span></span>  

```html
<div class="dateline"> Wednesday, September 18, 2013 7:38 AM </div>
```  

<span data-ttu-id="94d01-134">如果文章正文中没有日期，但希望阅读视图呈现日期，请使用元标记 `name='displaydate'` ：</span><span class="sxs-lookup"><span data-stu-id="94d01-134">If you don't have a date in the article body but would like Reading view to render the date, use the meta tag `name='displaydate'`:</span></span>  

```html
<meta name="displaydate" content=" Wednesday, September 18, 2013 7:38 AM ">
```  

### <span data-ttu-id="94d01-135">发布者</span><span class="sxs-lookup"><span data-stu-id="94d01-135">Publisher</span></span>  

<span data-ttu-id="94d01-136">阅读视图将查找开放图协议 `"og:site_name"` 来呈现发布者信息。</span><span class="sxs-lookup"><span data-stu-id="94d01-136">Reading view will look for the Open Graph protocol `"og:site_name"` to render the publisher information.</span></span>  <span data-ttu-id="94d01-137">还在任何 html `source_organization` `publisher` 标记中查找和属性作为页面上的发布者信息的辅助指示器。</span><span class="sxs-lookup"><span data-stu-id="94d01-137">It also looks for `source_organization` and `publisher` attributes in any html tag as a secondary indicator of publisher information on the page.</span></span>  <span data-ttu-id="94d01-138">使用阅读视图页面超链接样式将超链接发布者文本超链接到页面 URL。</span><span class="sxs-lookup"><span data-stu-id="94d01-138">The publisher text will be hyperlinked to the URL of page using the Reading view page hyperlink style.</span></span>  

```html
<meta content="Name of organization source" property="og:site_name">
```  

### <span data-ttu-id="94d01-139">Images</span><span class="sxs-lookup"><span data-stu-id="94d01-139">Images</span></span>  

<span data-ttu-id="94d01-140">阅读视图捕获大多数原始图像，其宽度为 <&gt;= 400 像素且纵位比 &gt;= 1/3 且 =&lt; 3.0。</span><span class="sxs-lookup"><span data-stu-id="94d01-140">Reading view captures most raw images with width >= 400px and aspect ratio >= 1/3 and =< 3.0.</span></span>  <span data-ttu-id="94d01-141">不符合这些维度的图像仍可能得到提取，例如宽度小于 400px 但带有标题的图像。</span><span class="sxs-lookup"><span data-stu-id="94d01-141">Images that do not meet these dimensions may still be extracted, such as images that are smaller than 400px in width but have captions.</span></span>  <span data-ttu-id="94d01-142">第一个符合资格图像成为文章的主要图像。</span><span class="sxs-lookup"><span data-stu-id="94d01-142">The first eligible image becomes the dominant image of the article.</span></span>  <span data-ttu-id="94d01-143">主要图像将呈现为内容的第一部分并提供全列宽。</span><span class="sxs-lookup"><span data-stu-id="94d01-143">The dominant image is rendered as the first piece of content and given full column width.</span></span>  <span data-ttu-id="94d01-144">下面的所有图像都呈现为该文章中的嵌入式图像。</span><span class="sxs-lookup"><span data-stu-id="94d01-144">All following images are rendered as inline images within the article.</span></span>  

### <span data-ttu-id="94d01-145">字幕</span><span class="sxs-lookup"><span data-stu-id="94d01-145">Captions</span></span>  

<span data-ttu-id="94d01-146">最佳实践是将图像放在不带两个[figure](https://developer.mozilla.org/docs/Web/HTML/Element/figure)以上嵌[套数字标记](https://developer.mozilla.org/docs/Web/HTML/Element/figcaption)的数字标记中。</span><span class="sxs-lookup"><span data-stu-id="94d01-146">Best practice is to place images in [figure](https://developer.mozilla.org/docs/Web/HTML/Element/figure) tags with no more than two nested [figcaption](https://developer.mozilla.org/docs/Web/HTML/Element/figcaption) tags.</span></span>  

### <span data-ttu-id="94d01-147">正文</span><span class="sxs-lookup"><span data-stu-id="94d01-147">Body</span></span>  

<span data-ttu-id="94d01-148">为确保您的页的所有正文文本都通过阅读视图捕获，将本文的大部分文本保持相同的字体大小和 DOM 深度。</span><span class="sxs-lookup"><span data-stu-id="94d01-148">To ensure that all the body text of your page is captured by Reading view, it helps to keep most of the article text the same font size and DOM depth.</span></span>  <span data-ttu-id="94d01-149">通过阅读视图算法，可以进行此规则的一些发展，因此发布者可以自由地对线条或字词添加强调效果。</span><span class="sxs-lookup"><span data-stu-id="94d01-149">The reading view algorithm allows for some deviation from this rule so publishers can have the freedom to add emphasis to lines or words.</span></span>  

### <span data-ttu-id="94d01-150">版权</span><span class="sxs-lookup"><span data-stu-id="94d01-150">Copyright</span></span>  

<span data-ttu-id="94d01-151">阅读视图提取并显示含有元标记的版权信息，或者如果 `name = "copyright"` 不存在 meta 标记信息，或者如果不存在 meta 标记信息，则一个包含版权 \ (`©` \) 符号的文本节点。</span><span class="sxs-lookup"><span data-stu-id="94d01-151">Reading view extracts and displays copyright information denoted by meta tags with `name = "copyright"`, or if no meta tag information exists, a text node that contains the copyright \(`©`\) symbol.</span></span>  <span data-ttu-id="94d01-152">阅读视图在文章主体的末尾显示版权信息，使用比主正文文本设置样式的样式。</span><span class="sxs-lookup"><span data-stu-id="94d01-152">Reading view displays copyright information at the end of the article main body, styled using a smaller font size than the main body text.</span></span>  

```html
<meta name="copyright" content="Your copyright information">
```  

## <span data-ttu-id="94d01-153">选择不阅读视图</span><span class="sxs-lookup"><span data-stu-id="94d01-153">Opting out of Reading View</span></span>  

<span data-ttu-id="94d01-154">如果您认为内容不是合适的阅读视图，你可以使用以下 meta 标记选择退出此功能：</span><span class="sxs-lookup"><span data-stu-id="94d01-154">If you feel your content is not a good fit for Reading view, you can use the following meta tag to opt out of this feature:</span></span>  

```html
<meta name="IE_RM_OFF" content="true">
```  

<span data-ttu-id="94d01-155">使用此标记，当用户查看 **页面时，"** 阅读视图"按钮不会显示在地址栏中。</span><span class="sxs-lookup"><span data-stu-id="94d01-155">With this tag, the **Reading view** button will not appear in the address bar when your users view your page.</span></span>  
