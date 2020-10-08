---
ms.assetid: 2bc29371-4f2e-4b59-a588-30b107d751f6
description: 请参阅 Microsoft Edge 如何提供网页的阅读视图以启用外接程序阅读。
title: 阅读视图-开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 0d2076a63f97ecf2b4699795b0036736d0f95c9c
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941997"
---
# <span data-ttu-id="ffafd-104">阅读视图</span><span class="sxs-lookup"><span data-stu-id="ffafd-104">Reading view</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="ffafd-105">Microsoft Edge 为阅读视图提供了一种更简洁的、书籍喜欢的网页阅读体验，不会干扰页面上的不相关或其他辅助内容。</span><span class="sxs-lookup"><span data-stu-id="ffafd-105">Microsoft Edge provides a reading view for a more streamlined, book-like reading experience of webpages without the distraction of unrelated or other secondary content on the page.</span></span>  <span data-ttu-id="ffafd-106">可在 "**阅读视图**" 中打开或关闭 "阅读视图 \ (簿图标 \ ) " 按钮，或通过 "地址栏" 或 "与" `Ctrl` + `Shift` + `R` 。</span><span class="sxs-lookup"><span data-stu-id="ffafd-106">Reading view can be toggled on or off from the **Reading view** \(book icon\) button on the address bar or with `Ctrl`+`Shift`+`R`.</span></span>  <span data-ttu-id="ffafd-107">阅读视图从页面中提取以下元数据：</span><span class="sxs-lookup"><span data-stu-id="ffafd-107">Reading view extracts the following metadata from a page:</span></span>  

*   <span data-ttu-id="ffafd-108">Title</span><span class="sxs-lookup"><span data-stu-id="ffafd-108">Title</span></span>
*   <span data-ttu-id="ffafd-109">作者</span><span class="sxs-lookup"><span data-stu-id="ffafd-109">Author</span></span>
*   <span data-ttu-id="ffafd-110">日期</span><span class="sxs-lookup"><span data-stu-id="ffafd-110">Date</span></span>
*   <span data-ttu-id="ffafd-111">发布者</span><span class="sxs-lookup"><span data-stu-id="ffafd-111">Publisher</span></span>
*   <span data-ttu-id="ffafd-112">主导图像 \ (s \ ) </span><span class="sxs-lookup"><span data-stu-id="ffafd-112">Dominant image\(s\)</span></span>
*   <span data-ttu-id="ffafd-113">主图像的标题 \ (s ) </span><span class="sxs-lookup"><span data-stu-id="ffafd-113">Captions of dominant image\(s\)</span></span>
*   <span data-ttu-id="ffafd-114">次映像</span><span class="sxs-lookup"><span data-stu-id="ffafd-114">Secondary images</span></span>
*   <span data-ttu-id="ffafd-115">页面的主要文本内容</span><span class="sxs-lookup"><span data-stu-id="ffafd-115">Main text content of the page</span></span>
*   <span data-ttu-id="ffafd-116">版权</span><span class="sxs-lookup"><span data-stu-id="ffafd-116">Copyright</span></span>

<span data-ttu-id="ffafd-117">然后，用户可以从 "Microsoft Edge **设置** " 面板调整页面对比度和字号。</span><span class="sxs-lookup"><span data-stu-id="ffafd-117">Users can then adjust the page contrast and font size from the Microsoft Edge **Settings** panel.</span></span>  

## <span data-ttu-id="ffafd-118">元数据提取</span><span class="sxs-lookup"><span data-stu-id="ffafd-118">Metadata extraction</span></span>  

<span data-ttu-id="ffafd-119">下面是 "阅读视图" 呈现的页面元数据的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ffafd-119">Here are details of the page metadata rendered by reading view.</span></span>  

### <span data-ttu-id="ffafd-120">Title</span><span class="sxs-lookup"><span data-stu-id="ffafd-120">Title</span></span>  

<span data-ttu-id="ffafd-121">若要确保阅读视图呈现文章的标题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ffafd-121">To ensure Reading view renders your article's title:</span></span>  

*   <span data-ttu-id="ffafd-122">`title`在页眉中包含元素</span><span class="sxs-lookup"><span data-stu-id="ffafd-122">Include a `title` element in your header</span></span>  
*   <span data-ttu-id="ffafd-123">包含 meta 标记</span><span class="sxs-lookup"><span data-stu-id="ffafd-123">Include a meta tag with</span></span> `name="title"`  
*   <span data-ttu-id="ffafd-124">将文章正文中的标题文本与 meta 标记的内容字符串匹配。</span><span class="sxs-lookup"><span data-stu-id="ffafd-124">Match the title text in your article body with the content string of your meta tag.</span></span>  <span data-ttu-id="ffafd-125">管道 \ (`|` 内容字符串中 ) 使 "读者" 视图变为活动状态，请尝试改用连字符 \ (`-` \ ) 。</span><span class="sxs-lookup"><span data-stu-id="ffafd-125">Pipes \(`|`\) in your content string prevent the reader view from becoming active, try using hyphens \(`-`\) instead.</span></span>  

### <span data-ttu-id="ffafd-126">作者</span><span class="sxs-lookup"><span data-stu-id="ffafd-126">Author</span></span>  

<span data-ttu-id="ffafd-127">阅读视图将查找包含的元素 `class = "byline-name"` 。</span><span class="sxs-lookup"><span data-stu-id="ffafd-127">Reading View will look for an element with `class = "byline-name"`.</span></span>  <span data-ttu-id="ffafd-128">最佳做法是将作者姓名置于标题之后和文章正文之前。</span><span class="sxs-lookup"><span data-stu-id="ffafd-128">Best practice is to place the author name after the title and before the article body.</span></span>  

```html
<div class="byline-name">Author name</div>
```  

### <span data-ttu-id="ffafd-129">日期</span><span class="sxs-lookup"><span data-stu-id="ffafd-129">Date</span></span>  

<span data-ttu-id="ffafd-130">"阅读" 视图会将发布者和日期信息一起呈现在同一行上，并提供其他样式来突出显示此信息。</span><span class="sxs-lookup"><span data-stu-id="ffafd-130">Reading view will render the publisher and date information together on the same line, with additional styling to highlight this information.</span></span>  <span data-ttu-id="ffafd-131">项目的发布日期将完全呈现为字符串中显示的内容。</span><span class="sxs-lookup"><span data-stu-id="ffafd-131">The article's publishing date will render exactly as it appears in the string.</span></span>  <span data-ttu-id="ffafd-132">阅读视图不转换为特定的日期格式。</span><span class="sxs-lookup"><span data-stu-id="ffafd-132">Reading view does not convert to a specific date format.</span></span>  

<span data-ttu-id="ffafd-133">如果你的文章正文中有日期，并且希望阅读视图呈现它，请使用以下类分配包含日期的元素 `'dateline'` ：</span><span class="sxs-lookup"><span data-stu-id="ffafd-133">If you have a date in your article body and would like Reading view to render it, assign the element containing the date with the class `'dateline'`:</span></span>  

```html
<div class="dateline"> Wednesday, September 18, 2013 7:38 AM </div>
```  

<span data-ttu-id="ffafd-134">如果在文章正文中没有日期，但希望阅读视图呈现日期，请使用 meta 标记 `name='displaydate'` ：</span><span class="sxs-lookup"><span data-stu-id="ffafd-134">If you don't have a date in the article body but would like Reading view to render the date, use the meta tag `name='displaydate'`:</span></span>  

```html
<meta name="displaydate" content=" Wednesday, September 18, 2013 7:38 AM ">
```  

### <span data-ttu-id="ffafd-135">发布者</span><span class="sxs-lookup"><span data-stu-id="ffafd-135">Publisher</span></span>  

<span data-ttu-id="ffafd-136">"阅读视图" 将查找 "打开图形" 协议 `"og:site_name"` 以呈现发布者信息。</span><span class="sxs-lookup"><span data-stu-id="ffafd-136">Reading view will look for the Open Graph protocol `"og:site_name"` to render the publisher information.</span></span>  <span data-ttu-id="ffafd-137">它还 `source_organization` `publisher` 在任何 html 标记中查找和属性，作为页面上 publisher 信息的辅助指示器。</span><span class="sxs-lookup"><span data-stu-id="ffafd-137">It also looks for `source_organization` and `publisher` attributes in any html tag as a secondary indicator of publisher information on the page.</span></span>  <span data-ttu-id="ffafd-138">Publisher 文本将使用 "阅读视图" 页面超链接样式链接到页面的 URL。</span><span class="sxs-lookup"><span data-stu-id="ffafd-138">The publisher text will be hyperlinked to the URL of page using the Reading view page hyperlink style.</span></span>  

```html
<meta content="Name of organization source" property="og:site_name">
```  

### <span data-ttu-id="ffafd-139">Images</span><span class="sxs-lookup"><span data-stu-id="ffafd-139">Images</span></span>  

<span data-ttu-id="ffafd-140">"阅读" 视图捕获最大宽度为 >= 400px 和纵横比 >= 1/3 和 =< 3.0 的原始图像。</span><span class="sxs-lookup"><span data-stu-id="ffafd-140">Reading view captures most raw images with width >= 400px and aspect ratio >= 1/3 and =< 3.0.</span></span>  <span data-ttu-id="ffafd-141">不符合这些尺寸的图像仍可提取，例如小于400px 的图像，但其宽度较小，但具有标题。</span><span class="sxs-lookup"><span data-stu-id="ffafd-141">Images that do not meet these dimensions may still be extracted, such as images that are smaller than 400px in width but have captions.</span></span>  <span data-ttu-id="ffafd-142">第一个符合条件的图像成为文章的主导图像。</span><span class="sxs-lookup"><span data-stu-id="ffafd-142">The first eligible image becomes the dominant image of the article.</span></span>  <span data-ttu-id="ffafd-143">主导图像呈现为第一条内容，并给定完整的列宽度。</span><span class="sxs-lookup"><span data-stu-id="ffafd-143">The dominant image is rendered as the first piece of content and given full column width.</span></span>  <span data-ttu-id="ffafd-144">所有以下图像在项目中呈现为内联图像。</span><span class="sxs-lookup"><span data-stu-id="ffafd-144">All following images are rendered as inline images within the article.</span></span>  

### <span data-ttu-id="ffafd-145">字幕</span><span class="sxs-lookup"><span data-stu-id="ffafd-145">Captions</span></span>  

<span data-ttu-id="ffafd-146">最佳做法是将图像放置在不超过两个嵌套的[figcaption](https://developer.mozilla.org/docs/Web/HTML/Element/figcaption)标记的[插图](https://developer.mozilla.org/docs/Web/HTML/Element/figure)标签中。</span><span class="sxs-lookup"><span data-stu-id="ffafd-146">Best practice is to place images in [figure](https://developer.mozilla.org/docs/Web/HTML/Element/figure) tags with no more than two nested [figcaption](https://developer.mozilla.org/docs/Web/HTML/Element/figcaption) tags.</span></span>  

### <span data-ttu-id="ffafd-147">正文</span><span class="sxs-lookup"><span data-stu-id="ffafd-147">Body</span></span>  

<span data-ttu-id="ffafd-148">若要确保你的页面的所有正文文本都通过 "阅读" 视图捕获，它有助于将大部分文章文本保持相同的字体大小和 DOM 深度。</span><span class="sxs-lookup"><span data-stu-id="ffafd-148">To ensure that all the body text of your page is captured by Reading view, it helps to keep most of the article text the same font size and DOM depth.</span></span>  <span data-ttu-id="ffafd-149">"阅读" 视图算法允许使用此规则的某些差异，以便发布者可以自由地为线条或字词添加强调。</span><span class="sxs-lookup"><span data-stu-id="ffafd-149">The reading view algorithm allows for some deviation from this rule so publishers can have the freedom to add emphasis to lines or words.</span></span>  

### <span data-ttu-id="ffafd-150">版权</span><span class="sxs-lookup"><span data-stu-id="ffafd-150">Copyright</span></span>  

<span data-ttu-id="ffafd-151">阅读视图提取并显示由 meta 标记表示的版权信息 `name = "copyright"` ，或者如果没有 meta 标记信息，则包含版权 \ (`©` \ ) 符号的文本节点。</span><span class="sxs-lookup"><span data-stu-id="ffafd-151">Reading view extracts and displays copyright information denoted by meta tags with `name = "copyright"`, or if no meta tag information exists, a text node that contains the copyright \(`©`\) symbol.</span></span>  <span data-ttu-id="ffafd-152">阅读视图在文章正文正文的末尾显示版权信息，使用较小字号的字体，样式比正文文本更小。</span><span class="sxs-lookup"><span data-stu-id="ffafd-152">Reading view displays copyright information at the end of the article main body, styled using a smaller font size than the main body text.</span></span>  

```html
<meta name="copyright" content="Your copyright information">
```  

## <span data-ttu-id="ffafd-153">退出阅读视图</span><span class="sxs-lookup"><span data-stu-id="ffafd-153">Opting out of Reading View</span></span>  

<span data-ttu-id="ffafd-154">如果你认为内容不适合阅读视图，可以使用以下 meta 标记来选择退出此功能：</span><span class="sxs-lookup"><span data-stu-id="ffafd-154">If you feel your content is not a good fit for Reading view, you can use the following meta tag to opt out of this feature:</span></span>  

```html
<meta name="IE_RM_OFF" content="true">
```  

<span data-ttu-id="ffafd-155">通过此标记，当用户查看您的页面时，地址栏中不会显示 " **阅读视图** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="ffafd-155">With this tag, the **Reading view** button will not appear in the address bar when your users view your page.</span></span>  
