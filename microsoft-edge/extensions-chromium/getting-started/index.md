---
description: 了解 Chromium 扩展名以及渐进式构建完整的图片查看扩展，包括选项、内容注入、后台脚本、存储等。
title: Microsoft Edge 入门 (Chromium) 扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、web 开发、html、css、javascript、开发人员、扩展
ms.openlocfilehash: 31bb970201e8fe66c9996938fe8461d503d9c6a1
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015721"
---
# Microsoft Edge \ (Chromium \ ) 扩展入门  

如果要直接跳转到构建您的第一个扩展，请转到构建第1天的 NASA 图片。  

如果你不熟悉扩展概念和体系结构，请继续阅读，并了解有关哪些扩展的信息。  此信息可帮助您更加轻松地构建扩展，因为你理解它们背后的动机和体系结构。  

## 构建日分机的 NASA 图片  

每个部分在其中引用了已完成的扩展源安装包。  

*   [构建一个简单的扩展名，它会弹出一天的 NASA 图片](part1-simple-extension.md)  
    *   创建清单  
    *   分配扩展名图标  
    *   显示弹出窗口  
    *   在浏览器中本地运行扩展 (加载 )   

*   [在页面正文标记下动态插入 NASA 图片](part2-content-scripts.md)  
    *   创建插入动态内容脚本的 JavaScript  
    *   在清单中定义页面获取内容脚本  
    *   以声明方式插入内容脚本  
    *   在弹出窗口中添加一个按钮以向内容脚本发送消息  
    *   在内容脚本内接收消息  

## 在引入扩展之前了解浏览器  

### 每个浏览器选项卡都独立于每个其他选项卡  

若要了解 Microsoft Edge \ (Chromium \ ) 扩展名，我们首先需要完全了解多选项卡浏览器，如 Microsoft Edge 主要的内容。  若要开始，每个浏览器选项卡都在一个单独的线程中运行，该线程有效地将其与其他浏览器选项卡 \ (或线程 \ )   

![每个 "浏览器" 选项卡的一个线程](media/index-image1-browsertabs.png)  

### 每个选项卡处理一个 GET 请求  

每个选项卡实质上使用 URL \ (也称为统一资源定位器 \ ) 以获取单个数据流（通常是 HTML 文档）。  这种单流 \ (或 page \ ) 通常包括诸如 JavaScript 中的说明 \ (，如 JavaScript 包括标记、图像引用、CSS 引用以及其他 \ ) 。  最终，所需的所有资源都将下载到该选项卡页，通常会出现一个可视化的可视化对象，并在浏览器选项卡中完全呈现。  

### 来自每个选项卡的所有通信都将指向远程服务器  

了解每个选项卡在隔离环境中运行意味着这些选项卡彼此隔离，而不是更大的 internet。  通常情况下，这些选项卡（运行 JavaScript 作为已定义的编程语言）将返回到服务器，应考虑在浏览器选项卡顶部的 URL 栏中输入的第一个 GET 请求的发起服务器。  

## 扩展模型将所有内容倒置  

与选项卡页一样，扩展名在单独的线程中运行，该线程完全独立于讨论的所有选项卡页线程。  不同于其作业通常向远程服务器发出单个 GET 请求的选项卡，然后在浏览器中显示该数据的可视化效果，另一种情况下，扩展是指以前驻留在从浏览器选项卡上的 internet 连接另一端的服务器。  

![扩展模型将服务器模型倒置](media/index-image3-upsidedown.png)  

理解这一点非常重要。  一旦创建了扩展，并在浏览器中安装它，就会创建一个独立的 web 服务器，该服务器在浏览器内保持活动状态，但仍与在该浏览器上运行的每个选项卡页隔离。  

### 扩展 web 服务器捆绑  

什么是扩展名？ 它是一个捆绑包 \ (或称为 zip 文件 \ ) 的 web 资源，与 web 开发人员发布到 web 服务器的内容不同。  

该 zip 文件包含用于制作网页的 HTML、CSS、JavaScript、图像和所有必要的资源。  但是，此 zip 文件的根中需要一个额外的文件，并且该文件名为 `manifest.json` 。  它是你的扩展的蓝图，其中包括你的扩展版本、标题、需要哪些权限才能运行以及更多其他内容。  

![Zip 中的文件视图](media/index-image5-filemanager-view.png)  

### 启动扩展服务器  

当您部署到 web 服务器时，无论是 Apache、IIS、NGINX 还是任何其他 web 服务器，都包含 web 包。  当浏览器导航到服务器上的 URL 时，将 `index.html` 下载 web 服务器上的文件。  浏览器使用证书、配置文件等进行导航。  `index.html`文件存储在 web 服务器上的某个特殊位置。   您的扩展对同一内容有何影响？  尤其是，您的浏览器的选项卡页如何能够访问此 zip 文件 \ (您的扩展名 \ ) ？  这是扩展运行时对你的影响。  

扩展程序通过 URL \ (统一资源定位器 \ ) 名称为文件提供所有这些文件 `extension://{some-long-unique-identifier}/index.html` 。  我放在方括号中的名称 `{some-long-unique-identifier}` 是分配给你安装的扩展的唯一标识符。  这意味着，如果你在浏览器上安装了10个唯一的扩展，每个扩展都有一个唯一标识符，指向 zip 文件 \ (或扩展捆绑包 \ ) 在浏览器内部安装。  

<!--![Unique URLS for Extensions](media/index-image4-uniqueurls.png)  -->  

<!--todo: add image for unique URLs  -->  

### 扩展管理和与选项卡和浏览器工具栏通信  

扩展与浏览器的工具栏交互，每个扩展能够以一种安全的方式管理其他所有运行的选项卡页，以及处理所有这些选项卡页的 DOM。  内置于 Chromium 浏览器是一种消息 API，允许在扩展和选项卡页之间进行通信，以使此操作正常发生。  此 API （也称为扩展 API）提供了许多功能，包括通知管理、存储管理等。  

与 web 服务器一样，扩展功能可以持续运行 \ (或等待通知的休眠状态 \ ) 在浏览器运行的所有时间。  你可以将扩展视为浏览器的 orchestrator。  同样，扩展运行完全独立于选项卡页，但通过扩展 API 以及授予扩展的自愿加入权限，每个扩展都能够虚拟地控制浏览器中运行的任何选项卡页。  

### 扩展在安装时提供选择项安全模型  

通过文件中的声明，每个扩展都 `manifest.json` 允许安装扩展的用户授予不同级别的机构。  当用户安装时，此权限允许扩展，以便扩展能够提取任何信息，并通过扩展处理该数据。  

<!-- image links -->  

<!-- links -->  
