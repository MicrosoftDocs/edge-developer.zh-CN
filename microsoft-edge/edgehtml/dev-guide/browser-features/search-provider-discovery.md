---
ms.assetid: f74760f5-061c-494d-b096-9fb6ecb71a16
description: 如果你是搜索提供程序，请参阅如何确保 Microsoft Edge 支持你的服务。
title: 搜索提供程序发现 - 开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cb21182e910cb91658dd4fb204f7f7783843f447
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232689"
---
# <span data-ttu-id="e8022-104">搜索提供程序发现</span><span class="sxs-lookup"><span data-stu-id="e8022-104">Search provider discovery</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="e8022-105">丰富的搜索集成内置于 Microsoft Edge 地址栏中，包括搜索建议、来自 Web 的结果、浏览历史记录和收藏夹。</span><span class="sxs-lookup"><span data-stu-id="e8022-105">Rich search integration is built into the Microsoft Edge address bar, including search suggestions, results from the web, your browsing history, and favorites.</span></span>  <span data-ttu-id="e8022-106">Microsoft Edge 遵循 [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) 规范来发现和使用 Web 搜索提供程序。</span><span class="sxs-lookup"><span data-stu-id="e8022-106">Microsoft Edge follows the [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) specification to discover and use web search providers.</span></span>  <span data-ttu-id="e8022-107">如果你是搜索提供程序，下面是如何确保 Microsoft Edge 支持你的服务。</span><span class="sxs-lookup"><span data-stu-id="e8022-107">If you are a search provider, here's how to ensure that Microsoft Edge supports your service.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="e8022-108">为了用户安全和隐私，Microsoft Edge 要求通过 SSL 执行所有搜索。</span><span class="sxs-lookup"><span data-stu-id="e8022-108">For user security and privacy, Microsoft Edge requires all searches be conducted over SSL.</span></span>  

<span data-ttu-id="e8022-109">必须将以下资源指定为 `https` URL，才能启用搜索引擎的 Microsoft Edge 集成：</span><span class="sxs-lookup"><span data-stu-id="e8022-109">The following resources must be specified as `https` URLs to enable Microsoft Edge integration of your search engine:</span></span>  

*   <span data-ttu-id="e8022-110">包含对说明文档的引用的网站</span><span class="sxs-lookup"><span data-stu-id="e8022-110">The site that contains the reference to the description document</span></span>  
*   <span data-ttu-id="e8022-111">说明文档本身的 URL</span><span class="sxs-lookup"><span data-stu-id="e8022-111">The URL to the description document itself</span></span>  
*   <span data-ttu-id="e8022-112">搜索查询模板</span><span class="sxs-lookup"><span data-stu-id="e8022-112">The search query template</span></span>  
    
1.  <span data-ttu-id="e8022-113">提供OpenSearch说明文件，其中包含搜索提供程序的名称以及用于构造搜索的模板。</span><span class="sxs-lookup"><span data-stu-id="e8022-113">Provide an OpenSearch description file, which contains the name of the search provider, and the template to use to construct the search.</span></span>  <span data-ttu-id="e8022-114">下面是一个示例文档：</span><span class="sxs-lookup"><span data-stu-id="e8022-114">Here is an example document:</span></span>  
    
    ```html
    <?xml version="1.0" encoding="UTF-8"?> 
    <OpenSearchDescription xmlns="http://a9.com/-/spec/opensearch/1.1/">
        <ShortName>Contoso Search</ShortName>
        <Url type="text/html" template="https://www.contoso.com/?query={searchTerms}"/> 
    </OpenSearchDescription>
    ```  
    
1.  <span data-ttu-id="e8022-115">在页面的页眉部分包含对 OpenSearch 描述文件的引用 (这通常包括您的网站主页和搜索结果) ，例如：</span><span class="sxs-lookup"><span data-stu-id="e8022-115">Include a reference to your OpenSearch description file in the header section of your pages (typically this would include your site home page and search result pages), for example:</span></span>  
    
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
    
<span data-ttu-id="e8022-116">当用户浏览到您的搜索服务时，OpenSearch说明将自动选取并保存供以后使用。</span><span class="sxs-lookup"><span data-stu-id="e8022-116">When a user browses to your search service, your OpenSearch description will be automatically picked up and saved for later use.</span></span>  <span data-ttu-id="e8022-117">然后，用户将能够转到 Microsoft Edge 设置，并选择将搜索服务添加到 Microsoft Edge 地址栏的搜索提供程序列表中。</span><span class="sxs-lookup"><span data-stu-id="e8022-117">The user will then be able to go to Microsoft Edge settings and choose to add your search service to his or her list of search providers for the Microsoft Edge address bar.</span></span>  

<span data-ttu-id="e8022-118">有关创建OpenSearch说明文档的更多详细信息，请参阅 OpenSearch [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) 规范。</span><span class="sxs-lookup"><span data-stu-id="e8022-118">See the [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) specification for further details on creating your OpenSearch description document.</span></span>  
