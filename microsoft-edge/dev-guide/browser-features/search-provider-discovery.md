---
ms.assetid: f74760f5-061c-494d-b096-9fb6ecb71a16
description: 如果你是搜索提供商，请参阅如何确保 Microsoft Edge 支持你的服务。
title: 开发人员指南-搜索提供程序发现
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: ac23c2c62d436d5772b498208a56ad306eb8cb3c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562631"
---
# <span data-ttu-id="32805-104">搜索提供程序发现</span><span class="sxs-lookup"><span data-stu-id="32805-104">Search provider discovery</span></span>


<span data-ttu-id="32805-105">丰富的搜索集成内置于 Microsoft Edge 地址栏，包括搜索建议、web 上的结果、你的浏览历史记录和收藏夹。</span><span class="sxs-lookup"><span data-stu-id="32805-105">Rich search integration is built into the Microsoft Edge address bar, including search suggestions, results from the web, your browsing history, and favorites.</span></span> <span data-ttu-id="32805-106">Microsoft Edge 遵循[OpenSearch 1.1](https://go.microsoft.com/fwlink/p/?LinkID=208582)规范以发现和使用 web 搜索提供程序。</span><span class="sxs-lookup"><span data-stu-id="32805-106">Microsoft Edge follows the [OpenSearch 1.1](https://go.microsoft.com/fwlink/p/?LinkID=208582) specification to discover and use web search providers.</span></span> <span data-ttu-id="32805-107">如果你是搜索提供商，请按以下方法确保 Microsoft Edge 支持你的服务。</span><span class="sxs-lookup"><span data-stu-id="32805-107">If you are a search provider, here's how to ensure that Microsoft Edge supports your service.</span></span>

**<span data-ttu-id="32805-108">对于用户安全和隐私，Microsoft Edge 要求所有搜索均通过 SSL 进行。</span><span class="sxs-lookup"><span data-stu-id="32805-108">For user security and privacy, Microsoft Edge requires all searches be conducted over SSL.</span></span>** <span data-ttu-id="32805-109">必须将以下资源指定为 `https` url，才能启用你的搜索引擎的 Microsoft Edge 集成：</span><span class="sxs-lookup"><span data-stu-id="32805-109">The following resources must be specified as `https` URLs to enable Microsoft Edge integration of your search engine:</span></span>
* <span data-ttu-id="32805-110">包含对说明文档的引用的网站</span><span class="sxs-lookup"><span data-stu-id="32805-110">The site that contains the reference to the description document</span></span>
* <span data-ttu-id="32805-111">说明文档本身的 URL</span><span class="sxs-lookup"><span data-stu-id="32805-111">The URL to the description document itself</span></span>
* <span data-ttu-id="32805-112">搜索查询模板</span><span class="sxs-lookup"><span data-stu-id="32805-112">The search query template</span></span> 

1.  <span data-ttu-id="32805-113">提供一个 OpenSearch 说明文件，其中包含搜索提供程序的名称和用于构造搜索的模板。</span><span class="sxs-lookup"><span data-stu-id="32805-113">Provide an OpenSearch description file, which contains the name of the search provider, and the template to use to construct the search.</span></span> <span data-ttu-id="32805-114">下面是一个示例文档：</span><span class="sxs-lookup"><span data-stu-id="32805-114">Here is an example document:</span></span>

    ```html
    <?xml version="1.0" encoding="UTF-8"?> 
    <OpenSearchDescription xmlns="http://a9.com/-/spec/opensearch/1.1/">
        <ShortName>Contoso Search</ShortName>
        <Url type="text/html" template="https://www.contoso.com/?query={searchTerms}"/> 
    </OpenSearchDescription>
    ```

2.  <span data-ttu-id="32805-115">在页面的页眉部分中包含对 OpenSearch 说明文件的引用（通常包括您的网站主页和搜索结果页面），例如：</span><span class="sxs-lookup"><span data-stu-id="32805-115">Include a reference to your OpenSearch description file in the header section of your pages (typically this would include your site home page and search result pages), for example:</span></span>

    ```html
    <html>
        <head>
            <link rel="search" 
                type="application/opensearchdescription+xml"  
                href="https://contoso.com/content-search.xml" 
                title="Contoso search" /> 
        </head> 
        <body> 
        ...
    ```

<span data-ttu-id="32805-116">当用户浏览你的搜索服务时，将自动获取你的 OpenSearch 描述并保存，以便将来使用。</span><span class="sxs-lookup"><span data-stu-id="32805-116">When a user browses to your search service, your OpenSearch description will be automatically picked up and saved for later use.</span></span> <span data-ttu-id="32805-117">然后，用户将能够转到 Microsoft Edge 设置，并选择将搜索服务添加到 Microsoft Edge 地址栏的搜索提供商列表中。</span><span class="sxs-lookup"><span data-stu-id="32805-117">The user will then be able to go to Microsoft Edge settings and choose to add your search service to his or her list of search providers for the Microsoft Edge address bar.</span></span>

<span data-ttu-id="32805-118">有关创建 "OpenSearch" 说明文档的更多详细信息，请参阅[opensearch 1.1](https://go.microsoft.com/fwlink/p/?LinkID=208582)规范。</span><span class="sxs-lookup"><span data-stu-id="32805-118">See the [OpenSearch 1.1](https://go.microsoft.com/fwlink/p/?LinkID=208582) specification for further details on creating your OpenSearch description document.</span></span>
