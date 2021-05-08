---
description: 生成一个扩展，该扩展可弹出一天中的"下一张""
title: 创建扩展教程 - 第 1 部分
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium， Web 开发， html， css， javascript， 开发人员， 扩展
ms.openlocfilehash: dfbe7893ce576c223d2b1d39ec21b6c5f46d8356
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397508"
---
# <a name="create-an-extension-tutorial---part-1"></a>创建扩展教程 - 第 1 部分  

## <a name="overview"></a>概述  

本教程的目标是从空目录开始构建 Microsoft Edge (Chromium) 扩展。  你正在构建一个扩展，该扩展可弹出当天的"省/市/服务"图片。 在本教程中，了解如何通过完成以下操作来创建扩展。  

*   创建 `manifest.json` 文件。  
*   添加图标。  
*   打开默认弹出对话框。  

## <a name="before-you-begin"></a>开始之前

若要测试本教程中构建的已完成扩展，请下载 [源代码][ArchiveExtensionGettingStartedPart1]。  

## <a name="step-1-create-a-manifestjson-file"></a>步骤 1：创建manifest.js文件

每个扩展包都必须在 `manifest.json` 根目录有一个文件。  清单提供扩展的详细信息、扩展包版本、扩展名称和说明等。  

以下代码段概述了文件所需的基本 `manifest.json` 信息。  

```json
{
    "name": "NASA picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium extension to display the NASA picture of the day."
}
```  

## <a name="step-2-add-icons"></a>步骤 2：添加图标  

首先在 `icons` 项目中创建目录以存储图标图像文件。  图标用于用户选择启动扩展的按钮的背景图像。  

:::image type="complex" source="./media/part1-badge1.png" alt-text="用于打开扩展的工具栏上的图标":::
   用于打开扩展的工具栏上的图标  
:::image-end:::  

对于图标，我们建议使用： 
*   `PNG` 格式，但您也可以使用 `BMP` 、 或 `GIF` `ICO` `JPEG` 格式。  
*   128 x 128 像素的图像，如有必要，浏览器会调整其大小。  

项目的目录应类似于以下结构。   

```shell
└── part1
    ├── _manifest.json
    └── icons
        ├── nasapod16x16.png
        ├── nasapod32x32.png
        ├── nasapod48x48.png
        └── nasapod128x128.png
```  

接下来，将图标添加到 `manifest.json` 文件。 使用 `manifest.json` 图标信息更新文件，以便与以下代码段匹配。 `png`以下代码中列出的文件可在本文前面提到的下载文件中获得。  

```json
{
    "name": "NASA picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A chromium extension to show the NASA picture of the day.",
    "icons": {
        "16": "icons/nasapod16x16.png",
        "32": "icons/nasapod32x32.png",
        "48": "icons/nasapod48x48.png",
        "128": "icons/nasapod128x128.png"
    }
}
```  

## <a name="step-3-open-a-default-pop-up-dialog"></a>步骤 3：打开默认弹出对话框  

现在，创建 `HTML` 一个文件，以在用户启动扩展时运行。  在名为 的目录中 `popup.html` 创建名为 的 HTML 文件 `popup` 。  当用户选择图标以启动扩展时， `popup/popup.html` 显示为模式对话框。  

添加以下代码段中的代码以显示 `popup.html` 星形图像。  

```html
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>NASA picture of the day</title>
    </head>
    <body>
        <div>
            <img src="/images/stars.jpeg" alt="Display the stars image" />
        </div>
    </body>
</html>
```  

确保将图像文件 `images/stars.jpeg` 添加到 images 文件夹。  项目的目录应类似于以下结构。   

```shell
└── part1
    ├── _manifest.json
    ├── icons
    │   ├── nasapod16x16.png
    │   ├── nasapod32x32.png
    │   ├── nasapod48x48.png
    │   └── nasapod128x128.png
    ├── images
    │   └── stars.jpeg
    └── popup
        └── popup.html
```  

最后，确保在 下注册 弹出窗口 `manifest.json` `browser_action` ，如以下代码片段所示。  

```json
{
    "name": "NASA picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A chromium extension to display the NASA picture of the day.",
    "icons": {
        "16": "icons/nasapod16x16.png",
        "32": "icons/nasapod32x32.png",
        "48": "icons/nasapod48x48.png",
        "128": "icons/nasapod128x128.png"
    },
    "browser_action": {
        "default_popup": "popup/popup.html"
    }
}
```  

## <a name="next-steps"></a>后续步骤
这是开发工作扩展所需的一切。  现在，继续旁加载和测试扩展。 有关详细信息，请导航到 [旁加载扩展][TestExtensionSideload]。  

<!-- image links -->  

<!--[ImagePart1Heirarchy]: ./media/part1-heirarchy.png "Directory Structure"  -->  
<!--[ImagePart1Badge1]: ./media/part1-badge1.png "Toolbar Badge Icon"  -->  
<!--[ImagePart1Heirarchy1]: ./media/part1-heirarchy1.png "Directory Structure for Extension"  -->  
<!--[ImagePart1Threedots]: ./media/part1-threedots.png "Choose Extensions"  -->  
<!--[ImagePart1DevelopermodeToggle]: ./media/part1-developermode-toggle.png "Enable Developer Mode"  -->  
<!--[ImagePart1InstalledExtension]: ./media/part1-installed-extension.png "Installed Extensions"  -->  

<!-- links -->  

[ArchiveExtensionGettingStartedPart1]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/extension-getting-started-part1/part1 "已完成的扩展包源|Microsoft Docs"

[TestExtensionSideload]: ./extension-sideloading.md "测试扩展 (旁加载) |Microsoft Docs"
