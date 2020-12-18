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
# 搜索提供程序发现  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

丰富的搜索集成内置于 Microsoft Edge 地址栏中，包括搜索建议、来自 Web 的结果、浏览历史记录和收藏夹。  Microsoft Edge 遵循 [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) 规范来发现和使用 Web 搜索提供程序。  如果你是搜索提供程序，下面是如何确保 Microsoft Edge 支持你的服务。  

> [!IMPORTANT]
> 为了用户安全和隐私，Microsoft Edge 要求通过 SSL 执行所有搜索。  

必须将以下资源指定为 `https` URL，才能启用搜索引擎的 Microsoft Edge 集成：  

*   包含对说明文档的引用的网站  
*   说明文档本身的 URL  
*   搜索查询模板  
    
1.  提供OpenSearch说明文件，其中包含搜索提供程序的名称以及用于构造搜索的模板。  下面是一个示例文档：  
    
    ```html
    <?xml version="1.0" encoding="UTF-8"?> 
    <OpenSearchDescription xmlns="http://a9.com/-/spec/opensearch/1.1/">
        <ShortName>Contoso Search</ShortName>
        <Url type="text/html" template="https://www.contoso.com/?query={searchTerms}"/> 
    </OpenSearchDescription>
    ```  
    
1.  在页面的页眉部分包含对 OpenSearch 描述文件的引用 (这通常包括您的网站主页和搜索结果) ，例如：  
    
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
    
当用户浏览到您的搜索服务时，OpenSearch说明将自动选取并保存供以后使用。  然后，用户将能够转到 Microsoft Edge 设置，并选择将搜索服务添加到 Microsoft Edge 地址栏的搜索提供程序列表中。  

有关创建OpenSearch说明文档的更多详细信息，请参阅 OpenSearch [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) 规范。  
