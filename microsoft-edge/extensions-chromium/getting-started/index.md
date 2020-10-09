---
description: 了解 Chromium 扩展和构建扩展的核心概念。
title: Microsoft Edge (Chromium) 扩展概念和体系结构
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/01/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium、web 开发、html、css、javascript、开发人员、扩展
ms.openlocfilehash: 8ffdd19e1a1e36a4d10fdd80bd7dd5654d543527
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104726"
---
# 扩展概念和体系结构

本文提供了在构建扩展时有助于的概念的简要介绍。 若要了解 Microsoft Edge \ (Chromium \ ) 扩展，我们首先讨论多选项卡浏览器的工作方式。


## 了解浏览器的工作方式

下表列出了在构建扩展之前需要了解的有用信息。

1.  每个浏览器选项卡都独立于每个其他选项卡。 每个选项卡都在其自己的独立于其他浏览器选项卡和线程的线程中运行。

    ![每个 "浏览器" 选项卡的一个线程](media/index-image1-browsertabs.png)  

2.  每个选项卡处理一个 GET 请求。  每个选项卡都使用 URL 获取单个数据流，它通常是 HTML 文档。  此单个流或页面，包括有关 JavaScript 包括标记、图像引用、CSS 引用等的说明。  所有资源都将下载到该选项卡页，然后在该选项卡中呈现页面。  

3.  在每个选项卡和远程服务器之间进行通信。  每个选项卡都在隔离的环境中运行。 它们仍连接到 internet，但与其他选项卡隔离。  选项卡可能运行 JavaScript 以与服务器通信。 这些服务器是在选项卡的 URL 栏中输入的第一个 GET 请求的原始服务器。  

4.  扩展模型使用不同的通信模型。  与选项卡页类似，扩展在独立于所有选项卡页线程的单个线程中运行。  选项卡向远程服务器发出单个 GET 请求，然后呈现页面。 但是，扩展功能类似于远程服务器。 在浏览器中安装扩展将在浏览器中创建独立的 web 服务器。 该扩展与所有选项卡页隔离。  

    ![扩展使用不同的通信模型](media/index-image3-upsidedown.png)  

## 扩展体系结构

下表列出了与扩展体系结构相关的有用信息。  

1.  扩展 web 服务器捆绑包。  扩展名是 web 资源的捆绑包。 这些 web 资源与 web 开发人员发布到 web 服务器的其他资源类似。 开发人员在构建扩展时，将这些 web 资源捆绑到一个 zip 文件中。
    
    Zip 文件包括 HTML、CSS、JavaScript 和图像文件。  Zip 文件的根中需要另一个文件。 此文件是清单文件，其名称为 `manifest.json` 。  它是您的扩展的蓝图，包括您的扩展的版本、标题、运行扩展所需的权限等。

2.  启动扩展服务器。  Web 服务器包含您的 web 包。 浏览器导航到服务器上的 Url，并下载要在浏览器中呈现的文件。 浏览器使用证书、配置文件等进行导航。  如果存在 `index.html` 文件，则该文件存储在 web 服务器上的特殊位置。  

    使用扩展时，浏览器的选项卡页使用扩展运行时获取您的扩展的 web 包。  扩展运行时提供 URL 中的文件 `extension://{some-long-unique-identifier}/index.html` ，其中 `{some-long-unique-identifier}` 是在安装时分配给扩展名的唯一标识符。  每个扩展都使用不同的唯一标识符。 每个标识符指向您的浏览器中安装的 web 包。   

3.  扩展可以与选项卡和浏览器工具栏通信。   扩展可以与浏览器的工具栏交互。 每个扩展都在单独的线程中管理运行的选项卡页，并且每个选项卡页上的 DOM 操作是独立的  扩展使用扩展 API 在扩展和选项卡页之间通信。  此扩展 API 提供了其他功能，包括通知管理、存储管理等。  

    与 web 服务器一样，打开浏览器时，扩展会等待通知。  扩展和选项卡页在彼此隔离的线程中运行。 但是，开发人员可以使用扩展 API 和清单文件中的权限来允许扩展处理任何选项卡页。  

4. 扩展在安装时提供自愿加入权限。  扩展权限由开发人员在文件中指定 `manifest.json` 。 安装扩展时，将向用户显示有关该扩展需要运行的权限的信息。 根据所需的权限类型，扩展可以提取和使用浏览器中的信息。


## 后续步骤

 有关 "扩展" 入门的信息，请参阅 [创建扩展教程][CreateAnExtensionPart1]。 



<!-- image links -->  

<!-- links -->  

[CreateAnExtensionPart1]: ./part1-simple-extension.md "创建扩展教程-第1部分 |Microsoft 文档"  