---
ms.assetid: f74760f5-061c-494d-b096-9fb6ecb71a16
description: 如果你是搜索提供商，请参阅如何确保 Microsoft Edge 支持你的服务。
title: 搜索提供程序发现-开发指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 4ac8ea966e9c4736834a0be1130a8c2a8dfb2614
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941970"
---
# 搜索提供程序发现  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

丰富的搜索集成内置于 Microsoft Edge 地址栏，包括搜索建议、web 上的结果、你的浏览历史记录和收藏夹。  Microsoft Edge 遵循 [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) 规范以发现和使用 web 搜索提供程序。  如果你是搜索提供商，请按以下方法确保 Microsoft Edge 支持你的服务。  

> 必要对于用户安全和隐私，Microsoft Edge 要求所有搜索均通过 SSL 进行。  

必须将以下资源指定为 `https` url，才能启用你的搜索引擎的 Microsoft Edge 集成：  

*   包含对说明文档的引用的网站  
*   说明文档本身的 URL  
*   搜索查询模板  

1.  提供一个 OpenSearch 说明文件，其中包含搜索提供程序的名称和用于构造搜索的模板。  下面是一个示例文档：  
    
    ```html
    <?xml version="1.0" encoding="UTF-8"?> 
    <OpenSearchDescription xmlns="http://a9.com/-/spec/opensearch/1.1/">
        <ShortName>Contoso Search</ShortName>
        <Url type="text/html" template="https://www.contoso.com/?query={searchTerms}"/> 
    </OpenSearchDescription>
    ```  
    
1.  在页面的页眉部分中包含对 OpenSearch 描述文件的引用 (通常包括您的网站主页和搜索结果页面) ，例如：  
    
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
    
当用户浏览你的搜索服务时，将自动获取你的 OpenSearch 描述并保存，以便将来使用。  然后，用户将能够转到 Microsoft Edge 设置，并选择将搜索服务添加到 Microsoft Edge 地址栏的搜索提供商列表中。  

有关创建 "OpenSearch" 说明文档的更多详细信息，请参阅 [opensearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) 规范。  
