---
description: 扩展入门第1部分
title: 构建一个简单的扩展名，它会弹出一天的 NASA 图片
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/08/2020
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、web 开发、html、css、javascript、开发人员、扩展
ms.openlocfilehash: dd5c1dab0cb9b54b79be7d2728cb9bfde0945185
ms.sourcegitcommit: 0bc1312a1e6a0ac37cf385201db4361fc05184fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2020
ms.locfileid: "10683621"
---
# 构建一个简单的扩展名，它会弹出一天的 NASA 图片  

[此部件的已完成扩展程序包源][ArchiveExtensionGettingStartedPart1]  

## 概述  

在第1部分中，目标是构建一个非常简单的 Edge Chromium 扩展，该扩展从空目录开始。  此扩展的目标是完成以下任务。  

*   创建可在多个位置使用不同大小的扩展的图标  
*   创建简单 `manifest.json` 文件  
*   显示一个启动图标，当选中该图标时，将显示一个包含一天的 NASA 图片的弹出窗口  

## 清单文件基础知识  

每个扩展包都必须在 `manifest.json` 根目录处拥有一个文件。  你应该将其视为扩展的蓝图。  它告知浏览器引擎扩展所需的扩展 API 版本、扩展的名称和说明以及许多其他详细信息，请参见本多部分扩展入门指南。  

下面是简单的  `manifest.json`  

```json
{
    "name": "NASA Picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium Extension to show the NASA Picture of the Day."
}
```  

## 扩展图标设置  

接下来，将一些图标添加到 `manifest.json` file \ （并 `/icons` 使用图标文件 \）创建一个新目录。  图标用于用户选择以启动扩展的按钮的背景图像 \ （如果有 \），以及其他合适的位置。  

`PNG` 是推荐的格式，但你也可以使用 `BMP` 、 `GIF` `ICO` 和 `JPEG` 。  建议始终至少具有 "128x128 像素大小" 图标，并且浏览器会根据需要自动调整其大小。  

目录结构应类似于下图。  

<!--  
:::image type="complex" source="./media/part1-heirarchy.png" alt-text="Directory Structure":::
   Directory Structure
:::image-end:::
-->  

<!--![Directory Structure][ImagePart1Heirarchy]  -->  

```shell
└── part1
    ├── _manifest.json
    └── icons
        ├── nasapod16x16.png
        ├── nasapod32x32.png
        ├── nasapod48x48.png
        └── nasapod128x128.png
```  

更新后的 `manifest.json` 文件应如下所示。  

```json
{
    "name": "NASA Picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A chromium extension to show the NASA Picture of the Day.",
    "icons": {
        "16": "icons/nasapod16x16.png",
        "32": "icons/nasapod32x32.png",
        "48": "icons/nasapod48x48.png",
        "128": "icons/nasapod128x128.png"
    }
}
```  

> [!NOTE]
> `png`此页面顶部提及的 "zip 下载" 中提供了上述代码的图标文件。  

## 添加默认弹出对话框  

现在，创建一个在 `HTML` 用户选择 "扩展" 图标时自动运行的文件。  

:::image type="complex" source="./media/part1-badge1.png" alt-text="工具栏锁屏提醒图标":::
   工具栏锁屏提醒图标
:::image-end:::

<!--![Toolbar Badge Icon][ImagePart1Badge1]  -->  

HTML 文件已命名 `popup/popup.html` 。  选择 "扩展" 图标将启动 " `popup/popup.html` 模式" 对话框，直到你在对话框外选择。  

为此，请在下面的代码中将文件注册为默认弹出窗口 `manifest.json` `browser_action` 。  

```json
{
    "name": "NASA Picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A chromium Extension to show the NASA Picture of the Day.",
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

在 `popup` 目录中，添加文件 `popup.html` 并使其呈现星形图像。  下面是 `popup.html` 文件。  

```html
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>NASA Picture of the Day</title>
    </head>
    <body>
        <div>
            <img src="/images/stars.jpeg" alt="stars" />
        </div>
    </body>
</html>
```  

 此外，还可添加 `images/stars.jpeg` 文件中引用的图像文件 `popup.html` 。  

示例扩展的目录结构显示在下图中。  

<!--  
:::image type="complex" source="./media/part1-heirarchy1.png" alt-text="Directory Structure for Extension":::
   Directory Structure for Extension
:::image-end:::
-->  

<!--![Directory Structure for Extension][ImagePart1Heirarchy1]  -->  

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

> [!NOTE]
> `images/stars.jpeg`" [Zip 下载][ArchiveExtensionGettingStartedPart1]" 中提供了上一个图像中列出的文件。  

这就是构建工作扩展所需的一切。  剩下的就是对其进行测试。  

下一节将介绍如何将扩展 \ （有时称为侧加载 \）加载到 Microsoft Edge \ （Chromium \）浏览器中进行测试。  

## 在浏览器中进行开发时在浏览器中本地运行扩展 \ （侧面加载 \）  

Microsoft Edge \ （Chromium \）浏览器为你提供一种安全且简单的方法，以便你在开发过程中运行和调试扩展。  

该过程非常简单。  必须首先选择浏览器顶部的三个圆点。  接下来， `Extensions` 从上下文菜单中进行选择，如下图所示。  

:::image type="complex" source="./media/part1-threedots.png" alt-text="选择扩展":::
   选择扩展
:::image-end:::

<!--![Choose Extensions][ImagePart1Threedots]  -->  

如果您位于 "**扩展**" 页面上，如下图所示，请启用**开发人员模式**，方法是启用页面左下角的切换，如下图所示。  

:::image type="complex" source="./media/part1-developermode-toggle.png" alt-text="启用开发人员模式":::
   启用开发人员模式
:::image-end:::

<!--![Enable Developer Mode][ImagePart1DevelopermodeToggle]  -->  

## 安装和更新面加载的扩展  

首次安装扩展时，请选择 `Load Unpacked` 下图中所示的选项。  这会提示你输入一个目录，其中包含你的扩展资源文件。  这将安装扩展，就像从应用商店下载的一样。  

:::image type="complex" source="./media/part1-installed-extension.png" alt-text="已安装的扩展":::
   已安装的扩展
:::image-end:::

<!--![Installed Extensions][ImagePart1InstalledExtension]  -->  

安装扩展后，您可以通过选择 " `Reload` 扩展" 列表下的按钮更新它。  

若要从浏览器中删除扩展，请单击 `Remove` "扩展" 列表底部的按钮。  

## 调试扩展  

调试扩展非常简单，并且支持 Edge Chromium DevTools 中的所有功能。  此入门指南中未涉及这些详细信息，但对于成功生成扩展非常重要。  

<!-- image links -->  

<!--[ImagePart1Heirarchy]: ./media/part1-heirarchy.png "Directory Structure"  -->  
<!--[ImagePart1Badge1]: ./media/part1-badge1.png "Toolbar Badge Icon"  -->  
<!--[ImagePart1Heirarchy1]: ./media/part1-heirarchy1.png "Directory Structure for Extension"  -->  
<!--[ImagePart1Threedots]: ./media/part1-threedots.png "Choose Extensions"  -->  
<!--[ImagePart1DevelopermodeToggle]: ./media/part1-developermode-toggle.png "Enable Developer Mode"  -->  
<!--[ImagePart1InstalledExtension]: ./media/part1-installed-extension.png "Installed Extensions"  -->  

<!-- links -->  

[ArchiveExtensionGettingStartedPart1]: ./extension-source/extension-getting-started-part1.zip "已完成此部件的扩展程序包源 |Microsoft 文档"  
