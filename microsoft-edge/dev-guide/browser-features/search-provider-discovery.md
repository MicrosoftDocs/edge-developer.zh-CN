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
# 搜索提供程序发现  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

丰富搜索集成内置在 Microsoft Edge 地址栏中，包括搜索建议、来自 Web 的结果、浏览历史记录和收藏夹。  Microsoft Edge 遵循 [1.1 规OpenSearch国](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) ，以发现和使用 Web 搜索提供商。  如果你是搜索提供商，下面介绍如何确保 Microsoft Edge 支持你的服务。  

> [重要提示]为了获取用户安全和隐私，Microsoft Edge 要求在 SSL 上执行所有搜索。  

必须将以下资源指定为 `https` URL，才能启用 Microsoft Edge 与搜索引引文的集成：  

*   包含对说明文档引用的网站  
*   说明文档本身的 URL  
*   搜索查询模板  

1.  提供OpenSearch描述文件（其中包含搜索提供程序的名称）以及用于构造搜索的模板。  下面是一个示例文档：  
    
    ```html
    <?xml version="1.0" encoding="UTF-8"?> 
    <OpenSearchDescription xmlns="http://a9.com/-/spec/opensearch/1.1/">
        <ShortName>Contoso Search</ShortName>
        <Url type="text/html" template="https://www.contoso.com/?query={searchTerms}"/> 
    </OpenSearchDescription>
    ```  
    
1.  将网站主OpenSearch的页面标题部分包含对 OpenSearch码的 (引用，该文件通常包括你的网站主页) ，例如：  
    
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
    
当用户浏览到你的搜索服务时，您的OpenSearch并保存说明以供将来使用。  然后，该用户将能够转到 Microsoft Edge 设置，并选择将你的搜索服务添加到其用于 Microsoft Edge 地址栏的搜索提供程序列表中。  

有关创建OpenSearch说明文档的更多信息，请参阅 [1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) 规OpenSearch图。  
