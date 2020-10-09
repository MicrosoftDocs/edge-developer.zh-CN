---
description: 生成弹出 NASA 图片的扩展
title: 创建扩展教程-第1部分
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium、web 开发、html、css、javascript、开发人员、扩展
ms.openlocfilehash: 3809bfac714621cf97184127132487ed93958a2f
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104705"
---
# 创建扩展教程-第1部分  

## 概述  

本教程的目标是构建 Microsoft Edge (Chromium) 扩展名，从空目录开始。 我们将生成一个扩展，它将弹出一天的 NASA 图片。 在本教程中，你将了解如何通过以下方式创建扩展：

*   创建 `manifest.json` 文件。  
*   添加图标。  
*   打开一个默认的弹出对话框。  

## 开始之前

如果你想要测试将在本教程中生成的完成的扩展，请下载 [源代码][ArchiveExtensionGettingStartedPart1]。  

## 步骤1：创建 `manifest.json` 文件

每个扩展包都必须在 `manifest.json` 根目录处拥有一个文件。  清单提供你的扩展、扩展包版本、扩展名名称和说明等详细信息。  

以下代码片段概述了文件中所需的基本信息 `manifest.json` 。  

```json
{
    "name": "NASA picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium extension to display the NASA picture of the day."
}
```  

## 步骤2：添加图标  

首先 `icons` 在项目中创建目录以存储图标图像文件。  图标用于用户选择以启动扩展的按钮的背景图像。  

:::image type="complex" source="./media/part1-badge1.png" alt-text="工具栏上的图标以打开您的扩展&quot;:::
   工具栏上的图标以打开您的扩展
:::image-end:::

对于图标，建议使用： 
*   `PNG` 图标的格式，但你也可以使用 `BMP` 、 `GIF` `ICO` 或 `JPEG` 格式。  
*   128 x 128 px 的图像（如有必要）根据浏览器调整大小。  

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

接下来，将图标添加到 `manifest.json` 文件中。 `manifest.json`用图标信息更新文件，使其与以下代码片段匹配。 `png`以下代码中列出的文件在本文前面所述的下载文件中可用。  

```json
{
    &quot;name&quot;: &quot;NASA picture of the day viewer&quot;,
    &quot;version&quot;: &quot;0.0.0.1&quot;,
    &quot;manifest_version&quot;: 2,
    &quot;description&quot;: &quot;A chromium extension to show the NASA picture of the day.&quot;,
    &quot;icons&quot;: {
        &quot;16&quot;: &quot;icons/nasapod16x16.png&quot;,
        &quot;32&quot;: &quot;icons/nasapod32x32.png&quot;,
        &quot;48&quot;: &quot;icons/nasapod48x48.png&quot;,
        &quot;128&quot;: &quot;icons/nasapod128x128.png"
    }
}
```  

## 步骤3：打开默认的弹出对话框  

现在，创建一个 `HTML` 在用户启动您的扩展时运行的文件。  创建 `popup.html` 在名为的目录中调用的 HTML 文件 `popup` 。  当用户选择启动扩展的图标时， `popup/popup.html` 将显示为模式对话框。  

将以下代码片段中的代码添加到 `popup.html` 以显示星图像。  

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

确保将图像文件添加 `images/stars.jpeg` 到 "images" 文件夹。  项目的目录应类似于以下结构。   

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

最后，确保在 "" 下注册弹出窗口 `manifest.json` `browser_action` ，如以下代码片段所示。  

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

## 后续步骤
这就是开发工作扩展所需的所有内容。 现在，继续旁加载并测试您的扩展。 有关详细信息，请参阅 [旁加载扩展][TestExtensionSideload]。  


<!-- image links -->  

<!--[ImagePart1Heirarchy]: ./media/part1-heirarchy.png "Directory Structure"  -->  
<!--[ImagePart1Badge1]: ./media/part1-badge1.png "Toolbar Badge Icon"  -->  
<!--[ImagePart1Heirarchy1]: ./media/part1-heirarchy1.png "Directory Structure for Extension"  -->  
<!--[ImagePart1Threedots]: ./media/part1-threedots.png "Choose Extensions"  -->  
<!--[ImagePart1DevelopermodeToggle]: ./media/part1-developermode-toggle.png "Enable Developer Mode"  -->  
<!--[ImagePart1InstalledExtension]: ./media/part1-installed-extension.png "Installed Extensions"  -->  

<!-- links -->  

[ArchiveExtensionGettingStartedPart1]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/extension-getting-started-part1/part1 "已完成扩展程序包源 |Microsoft 文档"

[TestExtensionSideload]: ./extension-sideloading.md "测试您的扩展 (旁加载) |Microsoft 文档"
