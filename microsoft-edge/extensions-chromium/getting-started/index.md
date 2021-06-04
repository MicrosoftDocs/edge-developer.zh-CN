---
description: 了解 Chromium 扩展以及构建扩展的核心概念。
title: Microsoft Edge (Chromium) Extensions 概念和体系结构
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium， Web 开发， html， css， javascript， 开发人员， 扩展
ms.openlocfilehash: 05732287bc1a782ed5830d5e7028cf5580f3b605
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397922"
---
# <a name="extension-concepts-and-architecture"></a>扩展概念和体系结构  

本文简要介绍了帮助您构建扩展的概念。  若要了解 Microsoft Edge \(Chromium\) 扩展，请继续了解多选项卡浏览器如何工作。  

## <a name="understand-how-browsers-work"></a>了解浏览器如何工作  

下面的列表概述了在构建扩展之前要了解的有用信息。  

1.  每个浏览器选项卡彼此独立。 每个选项卡在独立于其他浏览器选项卡和线程的单独线程中运行。  
    
    :::image type="complex" source="./media/index-image1-browsertabs.png" alt-text="每个浏览器选项卡一个线程" lightbox="./media/index-image1-browsertabs.png":::
       每个浏览器选项卡一个线程  
    :::image-end:::  
    
1.  每个选项卡处理一个 GET 请求。  每个选项卡使用一个 URL 获取一个数据流，这通常是 HTML 文档。  该单个流或页面包括 JavaScript 等说明，包括标记、图像引用、CSS 引用等。  所有资源都下载到该选项卡页，然后页面呈现在选项卡中。  
1.  在每个选项卡和远程服务器之间通信。  每个选项卡在隔离环境中运行。  每个选项卡仍连接到 Internet，但每个选项卡都与其他选项卡隔离。  选项卡可以运行 JavaScript 与服务器通信。  服务器是输入到选项卡的 URL 栏中的第一个 GET 请求的原始服务器。  
1.  扩展模型使用不同的通信模型。  与选项卡页类似，扩展在独立于其他选项卡页线程的单个线程中运行。  选项卡将单个 GET 请求发送到远程服务器，然后呈现页面。  但是，扩展的工作方式类似于远程服务器。  在浏览器中安装扩展在浏览器中创建独立 Web 服务器。  扩展名独立于所有选项卡页。  
    
    :::image type="complex" source="./media/index-image3-upsidedown.png" alt-text="扩展使用不同的通信模型" lightbox="./media/index-image3-upsidedown.png":::
       扩展使用不同的通信模型  
    :::image-end:::  
    
## <a name="extension-architecture"></a>扩展体系结构  

下面的列表概述了与扩展体系结构相关的有用信息。  

1.  扩展 Web 服务器捆绑包。  扩展是 Web 资源的捆绑包。  Web 资源类似于你 \(开发人员\) Web 服务器的其他资源。  生成扩展时，将 Web 资源捆绑到 zip 文件中。  
    
    zip 文件包括 HTML、CSS、JavaScript 和图像文件。  zip 文件的根中需要另外一个文件。  另一个文件是名为 的清单文件 `manifest.json` 。  清单文件是扩展的蓝图，包括扩展版本、标题、运行扩展所需的权限等。  
    
1.  启动扩展服务器。  Web 服务器包含 Web 捆绑包。  浏览器导航到服务器上 URL，并下载文件以在浏览器中呈现。  浏览器使用证书、配置文件等进行导航。  如果 `index.html` 指定了文件，则该文件存储在 Web 服务器上的特殊位置。  
    
    使用扩展时，浏览器的选项卡页将使用扩展运行时访问扩展的 Web 捆绑包。  扩展运行时提供 URL 中的文件，其中 是安装期间分配给扩展 `extension://{some-long-unique-identifier}/index.html` `{some-long-unique-identifier}` 的唯一标识符。  每个扩展使用不同的唯一标识符。  每个标识符指向安装在浏览器中的 Web 捆绑包。  
    
1.  扩展可能会与选项卡和浏览器工具栏通信。  扩展可能会与浏览器的工具栏交互。  每个扩展在单独的线程中管理正在运行的选项卡页，并且每个选项卡页上的 DOM 操作是独立的。  扩展使用扩展 API 在扩展和选项卡页之间进行通信。  扩展 API 提供额外功能，包括通知管理、存储管理等。  
    
    与 Web 服务器一样，扩展在浏览器打开时等待通知。  扩展页和选项卡页在相互隔离的线程中运行。  若要允许扩展在任何选项卡页中运行，请使用扩展 API 并设置清单文件中的权限。  
    
1.  扩展在安装时提供选择加入权限。  您可以在文件中指定扩展 `manifest.json` 权限。  当用户安装扩展时，将显示有关扩展需要的权限的信息。  根据所需的权限类型，扩展可能会从浏览器中提取和使用信息。  
    
## <a name="next-steps"></a>后续步骤  

有关扩展入门的信息，请导航到 [创建扩展教程][CreateAnExtensionPart1]。  

<!-- links -->  

[CreateAnExtensionPart1]: ./part1-simple-extension.md "创建扩展教程 - 第 1 部分|Microsoft Docs"  
