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
# <span data-ttu-id="22e08-104">阅读视图</span><span class="sxs-lookup"><span data-stu-id="22e08-104">Reading view</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="22e08-105">Microsoft Edge 提供了一个阅读视图，使网页的阅读体验更简洁、更像书籍一样，而不会分散页面上无关内容或其他辅助内容的干扰。</span><span class="sxs-lookup"><span data-stu-id="22e08-105">Microsoft Edge provides a reading view for a more streamlined, book-like reading experience of webpages without the distraction of unrelated or other secondary content on the page.</span></span>  <span data-ttu-id="22e08-106">阅读视图可以从阅读视图**\ (** 书籍图标\) 按钮或与中切换 `Ctrl` + `Shift` + `R` 。</span><span class="sxs-lookup"><span data-stu-id="22e08-106">Reading view can be toggled on or off from the **Reading view** \(book icon\) button on the address bar or with `Ctrl`+`Shift`+`R`.</span></span>  <span data-ttu-id="22e08-107">阅读视图从页面中提取以下元数据：</span><span class="sxs-lookup"><span data-stu-id="22e08-107">Reading view extracts the following metadata from a page:</span></span>  

*   <span data-ttu-id="22e08-108">Title</span><span class="sxs-lookup"><span data-stu-id="22e08-108">Title</span></span>
*   <span data-ttu-id="22e08-109">作者</span><span class="sxs-lookup"><span data-stu-id="22e08-109">Author</span></span>
*   <span data-ttu-id="22e08-110">日期</span><span class="sxs-lookup"><span data-stu-id="22e08-110">Date</span></span>
*   <span data-ttu-id="22e08-111">发布者</span><span class="sxs-lookup"><span data-stu-id="22e08-111">Publisher</span></span>
*   <span data-ttu-id="22e08-112">基准图像\ (\) </span><span class="sxs-lookup"><span data-stu-id="22e08-112">Dominant image\(s\)</span></span>
*   <span data-ttu-id="22e08-113">基准图像的标题\ (s\) </span><span class="sxs-lookup"><span data-stu-id="22e08-113">Captions of dominant image\(s\)</span></span>
*   <span data-ttu-id="22e08-114">辅助图像</span><span class="sxs-lookup"><span data-stu-id="22e08-114">Secondary images</span></span>
*   <span data-ttu-id="22e08-115">页面的主文本内容</span><span class="sxs-lookup"><span data-stu-id="22e08-115">Main text content of the page</span></span>
*   <span data-ttu-id="22e08-116">版权</span><span class="sxs-lookup"><span data-stu-id="22e08-116">Copyright</span></span>

<span data-ttu-id="22e08-117">然后，用户可以从 Microsoft Edge 设置面板调整页面对比度 **和字体** 大小。</span><span class="sxs-lookup"><span data-stu-id="22e08-117">Users can then adjust the page contrast and font size from the Microsoft Edge **Settings** panel.</span></span>  

## <span data-ttu-id="22e08-118">元数据提取</span><span class="sxs-lookup"><span data-stu-id="22e08-118">Metadata extraction</span></span>  

<span data-ttu-id="22e08-119">下面是通过阅读视图呈现的页面元数据的详细信息。</span><span class="sxs-lookup"><span data-stu-id="22e08-119">Here are details of the page metadata rendered by reading view.</span></span>  

### <span data-ttu-id="22e08-120">Title</span><span class="sxs-lookup"><span data-stu-id="22e08-120">Title</span></span>  

<span data-ttu-id="22e08-121">若要确保阅读视图呈现您文章的标题，</span><span class="sxs-lookup"><span data-stu-id="22e08-121">To ensure Reading view renders your article's title:</span></span>  

*   <span data-ttu-id="22e08-122">在 `title` 标头中包括元素</span><span class="sxs-lookup"><span data-stu-id="22e08-122">Include a `title` element in your header</span></span>  
*   <span data-ttu-id="22e08-123">包含元标记</span><span class="sxs-lookup"><span data-stu-id="22e08-123">Include a meta tag with</span></span> `name="title"`  
*   <span data-ttu-id="22e08-124">将文章正文中的标题文本与元标记的内容字符串相匹配。</span><span class="sxs-lookup"><span data-stu-id="22e08-124">Match the title text in your article body with the content string of your meta tag.</span></span>  <span data-ttu-id="22e08-125">管道 \ (\) 防止读者视图变为活动状态，请尝试改为使用连字符 `|` \ (`-` \) 。</span><span class="sxs-lookup"><span data-stu-id="22e08-125">Pipes \(`|`\) in your content string prevent the reader view from becoming active, try using hyphens \(`-`\) instead.</span></span>  

### <span data-ttu-id="22e08-126">作者</span><span class="sxs-lookup"><span data-stu-id="22e08-126">Author</span></span>  

<span data-ttu-id="22e08-127">阅读视图将查找具有 `class = "byline-name"` 的元素。</span><span class="sxs-lookup"><span data-stu-id="22e08-127">Reading View will look for an element with `class = "byline-name"`.</span></span>  <span data-ttu-id="22e08-128">最佳做法是，将作者姓名放在标题之后和文章正文之前。</span><span class="sxs-lookup"><span data-stu-id="22e08-128">Best practice is to place the author name after the title and before the article body.</span></span>  

```html
<div class="byline-name">Author name</div>
```  

### <span data-ttu-id="22e08-129">日期</span><span class="sxs-lookup"><span data-stu-id="22e08-129">Date</span></span>  

<span data-ttu-id="22e08-130">阅读视图将在同一行中同时呈现发布者和日期信息，并添加其他样式以突出显示此信息。</span><span class="sxs-lookup"><span data-stu-id="22e08-130">Reading view will render the publisher and date information together on the same line, with additional styling to highlight this information.</span></span>  <span data-ttu-id="22e08-131">文章的发布日期将完全呈现在字符串中。</span><span class="sxs-lookup"><span data-stu-id="22e08-131">The article's publishing date will render exactly as it appears in the string.</span></span>  <span data-ttu-id="22e08-132">阅读视图不会转换为特定的日期格式。</span><span class="sxs-lookup"><span data-stu-id="22e08-132">Reading view does not convert to a specific date format.</span></span>  

<span data-ttu-id="22e08-133">如果你的文章正文中包含日期，并且希望阅读视图呈现它，请为包含日期的元素分配类 `'dateline'` ：</span><span class="sxs-lookup"><span data-stu-id="22e08-133">If you have a date in your article body and would like Reading view to render it, assign the element containing the date with the class `'dateline'`:</span></span>  

```html
<div class="dateline"> Wednesday, September 18, 2013 7:38 AM </div>
```  

<span data-ttu-id="22e08-134">如果在文章正文中没有日期，但希望阅读视图呈现日期，请使用元标记 `name='displaydate'` ：</span><span class="sxs-lookup"><span data-stu-id="22e08-134">If you don't have a date in the article body but would like Reading view to render the date, use the meta tag `name='displaydate'`:</span></span>  

```html
<meta name="displaydate" content=" Wednesday, September 18, 2013 7:38 AM ">
```  

### <span data-ttu-id="22e08-135">发布者</span><span class="sxs-lookup"><span data-stu-id="22e08-135">Publisher</span></span>  

<span data-ttu-id="22e08-136">阅读视图将查找 Open Graph 协议 `"og:site_name"` 以呈现发布者信息。</span><span class="sxs-lookup"><span data-stu-id="22e08-136">Reading view will look for the Open Graph protocol `"og:site_name"` to render the publisher information.</span></span>  <span data-ttu-id="22e08-137">它还查找作为页面上发布者信息的辅助指示器的任何 html 标记 `source_organization` `publisher` 中的属性。</span><span class="sxs-lookup"><span data-stu-id="22e08-137">It also looks for `source_organization` and `publisher` attributes in any html tag as a secondary indicator of publisher information on the page.</span></span>  <span data-ttu-id="22e08-138">发布者文本将超链接到使用阅读视图页面超链接样式的页面的 URL。</span><span class="sxs-lookup"><span data-stu-id="22e08-138">The publisher text will be hyperlinked to the URL of page using the Reading view page hyperlink style.</span></span>  

```html
<meta content="Name of organization source" property="og:site_name">
```  

### <span data-ttu-id="22e08-139">Images</span><span class="sxs-lookup"><span data-stu-id="22e08-139">Images</span></span>  

<span data-ttu-id="22e08-140">阅读视图捕获宽度为 >= 400px 且纵横比为 >= 1/3 且 =< 3.0 的原始图像。</span><span class="sxs-lookup"><span data-stu-id="22e08-140">Reading view captures most raw images with width >= 400px and aspect ratio >= 1/3 and =< 3.0.</span></span>  <span data-ttu-id="22e08-141">不满足这些尺寸的图像仍可以提取，例如宽度小于 400px 但具有标题的图像。</span><span class="sxs-lookup"><span data-stu-id="22e08-141">Images that do not meet these dimensions may still be extracted, such as images that are smaller than 400px in width but have captions.</span></span>  <span data-ttu-id="22e08-142">第一个符合条件的图像将成为文章的基准图像。</span><span class="sxs-lookup"><span data-stu-id="22e08-142">The first eligible image becomes the dominant image of the article.</span></span>  <span data-ttu-id="22e08-143">基准图像呈现为第一段内容，并给定完整列宽。</span><span class="sxs-lookup"><span data-stu-id="22e08-143">The dominant image is rendered as the first piece of content and given full column width.</span></span>  <span data-ttu-id="22e08-144">以下所有图像都呈现为文章中的内嵌图像。</span><span class="sxs-lookup"><span data-stu-id="22e08-144">All following images are rendered as inline images within the article.</span></span>  

### <span data-ttu-id="22e08-145">字幕</span><span class="sxs-lookup"><span data-stu-id="22e08-145">Captions</span></span>  

<span data-ttu-id="22e08-146">最佳做法是，将 [图像放在包含](https://developer.mozilla.org/docs/Web/HTML/Element/figure) 不超过两个嵌套图形标记的 [图标记](https://developer.mozilla.org/docs/Web/HTML/Element/figcaption) 中。</span><span class="sxs-lookup"><span data-stu-id="22e08-146">Best practice is to place images in [figure](https://developer.mozilla.org/docs/Web/HTML/Element/figure) tags with no more than two nested [figcaption](https://developer.mozilla.org/docs/Web/HTML/Element/figcaption) tags.</span></span>  

### <span data-ttu-id="22e08-147">正文</span><span class="sxs-lookup"><span data-stu-id="22e08-147">Body</span></span>  

<span data-ttu-id="22e08-148">为了确保页面的所有正文文本都由阅读视图捕获，让大多数文章文本保持相同的字号和 DOM 深度会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="22e08-148">To ensure that all the body text of your page is captured by Reading view, it helps to keep most of the article text the same font size and DOM depth.</span></span>  <span data-ttu-id="22e08-149">阅读视图算法允许此规则出现一些偏差，以便发布者可以自由地添加对行或字词的强调。</span><span class="sxs-lookup"><span data-stu-id="22e08-149">The reading view algorithm allows for some deviation from this rule so publishers can have the freedom to add emphasis to lines or words.</span></span>  

### <span data-ttu-id="22e08-150">版权</span><span class="sxs-lookup"><span data-stu-id="22e08-150">Copyright</span></span>  

<span data-ttu-id="22e08-151">阅读视图提取并显示由元标记表示的版权信息，如果不存在元标记信息，则显示包含版权 `name = "copyright"` \ (`©` \) 符号的文本节点。</span><span class="sxs-lookup"><span data-stu-id="22e08-151">Reading view extracts and displays copyright information denoted by meta tags with `name = "copyright"`, or if no meta tag information exists, a text node that contains the copyright \(`©`\) symbol.</span></span>  <span data-ttu-id="22e08-152">阅读视图在文章正文的末尾显示版权信息，其样式使用比正文文本更小的字体大小。</span><span class="sxs-lookup"><span data-stu-id="22e08-152">Reading view displays copyright information at the end of the article main body, styled using a smaller font size than the main body text.</span></span>  

```html
<meta name="copyright" content="Your copyright information">
```  

## <span data-ttu-id="22e08-153">选择退出阅读视图</span><span class="sxs-lookup"><span data-stu-id="22e08-153">Opting out of Reading View</span></span>  

<span data-ttu-id="22e08-154">如果您觉得内容不适合阅读视图，可以使用以下元标记选择退出此功能：</span><span class="sxs-lookup"><span data-stu-id="22e08-154">If you feel your content is not a good fit for Reading view, you can use the following meta tag to opt out of this feature:</span></span>  

```html
<meta name="IE_RM_OFF" content="true">
```  

<span data-ttu-id="22e08-155">通过此标记，当用户\*\*\*\* 查看页面时，"阅读视图"按钮不会显示在地址栏中。</span><span class="sxs-lookup"><span data-stu-id="22e08-155">With this tag, the **Reading view** button will not appear in the address bar when your users view your page.</span></span>  
