---
ms.assetid: 2bc29371-4f2e-4b59-a588-30b107d751f6
description: See how Microsoft Edge provides a reading view for webpages to enable add-free reading.
title: Reading view - Dev guide
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, css, javascript, developer
ms.openlocfilehash: 0d2076a63f97ecf2b4699795b0036736d0f95c9c
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941997"
---
# <span data-ttu-id="ddbeb-104">Reading view</span><span class="sxs-lookup"><span data-stu-id="ddbeb-104">Reading view</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="ddbeb-105">Microsoft Edge provides a reading view for a more streamlined, book-like reading experience of webpages without the distraction of unrelated or other secondary content on the page.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-105">Microsoft Edge provides a reading view for a more streamlined, book-like reading experience of webpages without the distraction of unrelated or other secondary content on the page.</span></span>  <span data-ttu-id="ddbeb-106">Reading view can be toggled on or off from the **Reading view** \(book icon\) button on the address bar or with `Ctrl`+`Shift`+`R`.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-106">Reading view can be toggled on or off from the **Reading view** \(book icon\) button on the address bar or with `Ctrl`+`Shift`+`R`.</span></span>  <span data-ttu-id="ddbeb-107">Reading view extracts the following metadata from a page:</span><span class="sxs-lookup"><span data-stu-id="ddbeb-107">Reading view extracts the following metadata from a page:</span></span>  

*   <span data-ttu-id="ddbeb-108">Title</span><span class="sxs-lookup"><span data-stu-id="ddbeb-108">Title</span></span>
*   <span data-ttu-id="ddbeb-109">Author</span><span class="sxs-lookup"><span data-stu-id="ddbeb-109">Author</span></span>
*   <span data-ttu-id="ddbeb-110">Date</span><span class="sxs-lookup"><span data-stu-id="ddbeb-110">Date</span></span>
*   <span data-ttu-id="ddbeb-111">Publisher</span><span class="sxs-lookup"><span data-stu-id="ddbeb-111">Publisher</span></span>
*   <span data-ttu-id="ddbeb-112">Dominant image\(s\)</span><span class="sxs-lookup"><span data-stu-id="ddbeb-112">Dominant image\(s\)</span></span>
*   <span data-ttu-id="ddbeb-113">Captions of dominant image\(s\)</span><span class="sxs-lookup"><span data-stu-id="ddbeb-113">Captions of dominant image\(s\)</span></span>
*   <span data-ttu-id="ddbeb-114">Secondary images</span><span class="sxs-lookup"><span data-stu-id="ddbeb-114">Secondary images</span></span>
*   <span data-ttu-id="ddbeb-115">Main text content of the page</span><span class="sxs-lookup"><span data-stu-id="ddbeb-115">Main text content of the page</span></span>
*   <span data-ttu-id="ddbeb-116">Copyright</span><span class="sxs-lookup"><span data-stu-id="ddbeb-116">Copyright</span></span>

<span data-ttu-id="ddbeb-117">Users can then adjust the page contrast and font size from the Microsoft Edge **Settings** panel.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-117">Users can then adjust the page contrast and font size from the Microsoft Edge **Settings** panel.</span></span>  

## <span data-ttu-id="ddbeb-118">Metadata extraction</span><span class="sxs-lookup"><span data-stu-id="ddbeb-118">Metadata extraction</span></span>  

<span data-ttu-id="ddbeb-119">Here are details of the page metadata rendered by reading view.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-119">Here are details of the page metadata rendered by reading view.</span></span>  

### <span data-ttu-id="ddbeb-120">Title</span><span class="sxs-lookup"><span data-stu-id="ddbeb-120">Title</span></span>  

<span data-ttu-id="ddbeb-121">To ensure Reading view renders your article's title:</span><span class="sxs-lookup"><span data-stu-id="ddbeb-121">To ensure Reading view renders your article's title:</span></span>  

*   <span data-ttu-id="ddbeb-122">Include a `title` element in your header</span><span class="sxs-lookup"><span data-stu-id="ddbeb-122">Include a `title` element in your header</span></span>  
*   <span data-ttu-id="ddbeb-123">Include a meta tag with</span><span class="sxs-lookup"><span data-stu-id="ddbeb-123">Include a meta tag with</span></span> `name="title"`  
*   <span data-ttu-id="ddbeb-124">Match the title text in your article body with the content string of your meta tag.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-124">Match the title text in your article body with the content string of your meta tag.</span></span>  <span data-ttu-id="ddbeb-125">Pipes \(`|`\) in your content string prevent the reader view from becoming active, try using hyphens \(`-`\) instead.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-125">Pipes \(`|`\) in your content string prevent the reader view from becoming active, try using hyphens \(`-`\) instead.</span></span>  

### <span data-ttu-id="ddbeb-126">Author</span><span class="sxs-lookup"><span data-stu-id="ddbeb-126">Author</span></span>  

<span data-ttu-id="ddbeb-127">Reading View will look for an element with `class = "byline-name"`.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-127">Reading View will look for an element with `class = "byline-name"`.</span></span>  <span data-ttu-id="ddbeb-128">Best practice is to place the author name after the title and before the article body.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-128">Best practice is to place the author name after the title and before the article body.</span></span>  

```html
<div class="byline-name">Author name</div>
```  

### <span data-ttu-id="ddbeb-129">Date</span><span class="sxs-lookup"><span data-stu-id="ddbeb-129">Date</span></span>  

<span data-ttu-id="ddbeb-130">Reading view will render the publisher and date information together on the same line, with additional styling to highlight this information.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-130">Reading view will render the publisher and date information together on the same line, with additional styling to highlight this information.</span></span>  <span data-ttu-id="ddbeb-131">The article's publishing date will render exactly as it appears in the string.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-131">The article's publishing date will render exactly as it appears in the string.</span></span>  <span data-ttu-id="ddbeb-132">Reading view does not convert to a specific date format.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-132">Reading view does not convert to a specific date format.</span></span>  

<span data-ttu-id="ddbeb-133">If you have a date in your article body and would like Reading view to render it, assign the element containing the date with the class `'dateline'`:</span><span class="sxs-lookup"><span data-stu-id="ddbeb-133">If you have a date in your article body and would like Reading view to render it, assign the element containing the date with the class `'dateline'`:</span></span>  

```html
<div class="dateline"> Wednesday, September 18, 2013 7:38 AM </div>
```  

<span data-ttu-id="ddbeb-134">If you don't have a date in the article body but would like Reading view to render the date, use the meta tag `name='displaydate'`:</span><span class="sxs-lookup"><span data-stu-id="ddbeb-134">If you don't have a date in the article body but would like Reading view to render the date, use the meta tag `name='displaydate'`:</span></span>  

```html
<meta name="displaydate" content=" Wednesday, September 18, 2013 7:38 AM ">
```  

### <span data-ttu-id="ddbeb-135">Publisher</span><span class="sxs-lookup"><span data-stu-id="ddbeb-135">Publisher</span></span>  

<span data-ttu-id="ddbeb-136">Reading view will look for the Open Graph protocol `"og:site_name"` to render the publisher information.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-136">Reading view will look for the Open Graph protocol `"og:site_name"` to render the publisher information.</span></span>  <span data-ttu-id="ddbeb-137">It also looks for `source_organization` and `publisher` attributes in any html tag as a secondary indicator of publisher information on the page.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-137">It also looks for `source_organization` and `publisher` attributes in any html tag as a secondary indicator of publisher information on the page.</span></span>  <span data-ttu-id="ddbeb-138">The publisher text will be hyperlinked to the URL of page using the Reading view page hyperlink style.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-138">The publisher text will be hyperlinked to the URL of page using the Reading view page hyperlink style.</span></span>  

```html
<meta content="Name of organization source" property="og:site_name">
```  

### <span data-ttu-id="ddbeb-139">Images</span><span class="sxs-lookup"><span data-stu-id="ddbeb-139">Images</span></span>  

<span data-ttu-id="ddbeb-140">Reading view captures most raw images with width >= 400px and aspect ratio >= 1/3 and =< 3.0.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-140">Reading view captures most raw images with width >= 400px and aspect ratio >= 1/3 and =< 3.0.</span></span>  <span data-ttu-id="ddbeb-141">Images that do not meet these dimensions may still be extracted, such as images that are smaller than 400px in width but have captions.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-141">Images that do not meet these dimensions may still be extracted, such as images that are smaller than 400px in width but have captions.</span></span>  <span data-ttu-id="ddbeb-142">The first eligible image becomes the dominant image of the article.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-142">The first eligible image becomes the dominant image of the article.</span></span>  <span data-ttu-id="ddbeb-143">The dominant image is rendered as the first piece of content and given full column width.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-143">The dominant image is rendered as the first piece of content and given full column width.</span></span>  <span data-ttu-id="ddbeb-144">All following images are rendered as inline images within the article.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-144">All following images are rendered as inline images within the article.</span></span>  

### <span data-ttu-id="ddbeb-145">Captions</span><span class="sxs-lookup"><span data-stu-id="ddbeb-145">Captions</span></span>  

<span data-ttu-id="ddbeb-146">Best practice is to place images in [figure](https://developer.mozilla.org/docs/Web/HTML/Element/figure) tags with no more than two nested [figcaption](https://developer.mozilla.org/docs/Web/HTML/Element/figcaption) tags.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-146">Best practice is to place images in [figure](https://developer.mozilla.org/docs/Web/HTML/Element/figure) tags with no more than two nested [figcaption](https://developer.mozilla.org/docs/Web/HTML/Element/figcaption) tags.</span></span>  

### <span data-ttu-id="ddbeb-147">Body</span><span class="sxs-lookup"><span data-stu-id="ddbeb-147">Body</span></span>  

<span data-ttu-id="ddbeb-148">To ensure that all the body text of your page is captured by Reading view, it helps to keep most of the article text the same font size and DOM depth.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-148">To ensure that all the body text of your page is captured by Reading view, it helps to keep most of the article text the same font size and DOM depth.</span></span>  <span data-ttu-id="ddbeb-149">The reading view algorithm allows for some deviation from this rule so publishers can have the freedom to add emphasis to lines or words.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-149">The reading view algorithm allows for some deviation from this rule so publishers can have the freedom to add emphasis to lines or words.</span></span>  

### <span data-ttu-id="ddbeb-150">Copyright</span><span class="sxs-lookup"><span data-stu-id="ddbeb-150">Copyright</span></span>  

<span data-ttu-id="ddbeb-151">Reading view extracts and displays copyright information denoted by meta tags with `name = "copyright"`, or if no meta tag information exists, a text node that contains the copyright \(`©`\) symbol.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-151">Reading view extracts and displays copyright information denoted by meta tags with `name = "copyright"`, or if no meta tag information exists, a text node that contains the copyright \(`©`\) symbol.</span></span>  <span data-ttu-id="ddbeb-152">Reading view displays copyright information at the end of the article main body, styled using a smaller font size than the main body text.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-152">Reading view displays copyright information at the end of the article main body, styled using a smaller font size than the main body text.</span></span>  

```html
<meta name="copyright" content="Your copyright information">
```  

## <span data-ttu-id="ddbeb-153">Opting out of Reading View</span><span class="sxs-lookup"><span data-stu-id="ddbeb-153">Opting out of Reading View</span></span>  

<span data-ttu-id="ddbeb-154">If you feel your content is not a good fit for Reading view, you can use the following meta tag to opt out of this feature:</span><span class="sxs-lookup"><span data-stu-id="ddbeb-154">If you feel your content is not a good fit for Reading view, you can use the following meta tag to opt out of this feature:</span></span>  

```html
<meta name="IE_RM_OFF" content="true">
```  

<span data-ttu-id="ddbeb-155">With this tag, the **Reading view** button will not appear in the address bar when your users view your page.</span><span class="sxs-lookup"><span data-stu-id="ddbeb-155">With this tag, the **Reading view** button will not appear in the address bar when your users view your page.</span></span>  
