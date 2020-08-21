---
ms.assetid: f74760f5-061c-494d-b096-9fb6ecb71a16
description: 如果你是搜索提供商，请参阅如何确保 Microsoft Edge 支持你的服务。
title: 搜索提供商发现 - 开发指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.openlocfilehash: 4ac8ea966e9c4736834a0be1130a8c2a8dfb2614
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941970"
---
# <span data-ttu-id="bf570-104">搜索提供程序发现</span><span class="sxs-lookup"><span data-stu-id="bf570-104">Search provider discovery</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="bf570-105">丰富搜索集成内置在 Microsoft Edge 地址栏中，包括搜索建议、来自 Web 的结果、浏览历史记录和收藏夹。</span><span class="sxs-lookup"><span data-stu-id="bf570-105">Rich search integration is built into the Microsoft Edge address bar, including search suggestions, results from the web, your browsing history, and favorites.</span></span>  <span data-ttu-id="bf570-106">Microsoft Edge 遵循 [1.1 规OpenSearch国](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) ，以发现和使用 Web 搜索提供商。</span><span class="sxs-lookup"><span data-stu-id="bf570-106">Microsoft Edge follows the [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) specification to discover and use web search providers.</span></span>  <span data-ttu-id="bf570-107">如果你是搜索提供商，下面介绍如何确保 Microsoft Edge 支持你的服务。</span><span class="sxs-lookup"><span data-stu-id="bf570-107">If you are a search provider, here's how to ensure that Microsoft Edge supports your service.</span></span>  

> <span data-ttu-id="bf570-108">[重要提示]为了获取用户安全和隐私，Microsoft Edge 要求在 SSL 上执行所有搜索。</span><span class="sxs-lookup"><span data-stu-id="bf570-108">[IMPORTANT] For user security and privacy, Microsoft Edge requires all searches be conducted over SSL.</span></span>  

<span data-ttu-id="bf570-109">必须将以下资源指定为 `https` URL，才能启用 Microsoft Edge 与搜索引引文的集成：</span><span class="sxs-lookup"><span data-stu-id="bf570-109">The following resources must be specified as `https` URLs to enable Microsoft Edge integration of your search engine:</span></span>  

*   <span data-ttu-id="bf570-110">包含对说明文档引用的网站</span><span class="sxs-lookup"><span data-stu-id="bf570-110">The site that contains the reference to the description document</span></span>  
*   <span data-ttu-id="bf570-111">说明文档本身的 URL</span><span class="sxs-lookup"><span data-stu-id="bf570-111">The URL to the description document itself</span></span>  
*   <span data-ttu-id="bf570-112">搜索查询模板</span><span class="sxs-lookup"><span data-stu-id="bf570-112">The search query template</span></span>  

1.  <span data-ttu-id="bf570-113">提供OpenSearch描述文件（其中包含搜索提供程序的名称）以及用于构造搜索的模板。</span><span class="sxs-lookup"><span data-stu-id="bf570-113">Provide an OpenSearch description file, which contains the name of the search provider, and the template to use to construct the search.</span></span>  <span data-ttu-id="bf570-114">下面是一个示例文档：</span><span class="sxs-lookup"><span data-stu-id="bf570-114">Here is an example document:</span></span>  
    
    ```html
    <?xml version="1.0" encoding="UTF-8"?> 
    <OpenSearchDescription xmlns="http://a9.com/-/spec/opensearch/1.1/">
        <ShortName>Contoso Search</ShortName>
        <Url type="text/html" template="https://www.contoso.com/?query={searchTerms}"/> 
    </OpenSearchDescription>
    ```  
    
1.  <span data-ttu-id="bf570-115">将网站主OpenSearch的页面标题部分包含对 OpenSearch码的 (引用，该文件通常包括你的网站主页) ，例如：</span><span class="sxs-lookup"><span data-stu-id="bf570-115">Include a reference to your OpenSearch description file in the header section of your pages (typically this would include your site home page and search result pages), for example:</span></span>  
    
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
    
<span data-ttu-id="bf570-116">当用户浏览到你的搜索服务时，您的OpenSearch并保存说明以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="bf570-116">When a user browses to your search service, your OpenSearch description will be automatically picked up and saved for later use.</span></span>  <span data-ttu-id="bf570-117">然后，该用户将能够转到 Microsoft Edge 设置，并选择将你的搜索服务添加到其用于 Microsoft Edge 地址栏的搜索提供程序列表中。</span><span class="sxs-lookup"><span data-stu-id="bf570-117">The user will then be able to go to Microsoft Edge settings and choose to add your search service to his or her list of search providers for the Microsoft Edge address bar.</span></span>  

<span data-ttu-id="bf570-118">有关创建OpenSearch说明文档的更多信息，请参阅 [1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) 规OpenSearch图。</span><span class="sxs-lookup"><span data-stu-id="bf570-118">See the [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) specification for further details on creating your OpenSearch description document.</span></span>  
