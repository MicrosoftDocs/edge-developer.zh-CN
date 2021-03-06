---
description: 构建一个扩展，该扩展弹出当天的"开始"菜单图片
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
# <a name="create-an-extension-tutorial---part-1"></a><span data-ttu-id="6acb8-104">创建扩展教程 - 第 1 部分</span><span class="sxs-lookup"><span data-stu-id="6acb8-104">Create an extension tutorial - Part 1</span></span>  

## <a name="overview"></a><span data-ttu-id="6acb8-105">概述</span><span class="sxs-lookup"><span data-stu-id="6acb8-105">Overview</span></span>  

<span data-ttu-id="6acb8-106">本教程的目标是从空目录开始构建 Microsoft Edge (Chromium) 扩展。</span><span class="sxs-lookup"><span data-stu-id="6acb8-106">The goal for this tutorial is to build a Microsoft Edge (Chromium) extension starting with an empty directory.</span></span>  <span data-ttu-id="6acb8-107">你正在构建一个扩展，该扩展将弹出当天的"开始"菜单图片。</span><span class="sxs-lookup"><span data-stu-id="6acb8-107">You are building an extension that pops up the NASA picture of the day.</span></span> <span data-ttu-id="6acb8-108">在本教程中，了解如何通过完成以下操作来创建扩展。</span><span class="sxs-lookup"><span data-stu-id="6acb8-108">In this tutorial, learn how to create an extension by completing the following actions.</span></span>  

*   <span data-ttu-id="6acb8-109">创建 `manifest.json` 文件。</span><span class="sxs-lookup"><span data-stu-id="6acb8-109">Creating a `manifest.json` file.</span></span>  
*   <span data-ttu-id="6acb8-110">添加图标。</span><span class="sxs-lookup"><span data-stu-id="6acb8-110">Adding icons.</span></span>  
*   <span data-ttu-id="6acb8-111">打开默认弹出对话框。</span><span class="sxs-lookup"><span data-stu-id="6acb8-111">Opening a default pop-up dialog.</span></span>  

## <a name="before-you-begin"></a><span data-ttu-id="6acb8-112">开始之前</span><span class="sxs-lookup"><span data-stu-id="6acb8-112">Before you Begin</span></span>

<span data-ttu-id="6acb8-113">若要测试本教程中构建的已完成扩展，请下载 [源代码][ArchiveExtensionGettingStartedPart1]。</span><span class="sxs-lookup"><span data-stu-id="6acb8-113">To test out the completed extension that you are building in this tutorial, download the [source code][ArchiveExtensionGettingStartedPart1].</span></span>  

## <a name="step-1-create-a-manifestjson-file"></a><span data-ttu-id="6acb8-114">步骤 1：创建manifest.js文件</span><span class="sxs-lookup"><span data-stu-id="6acb8-114">Step 1: Create a manifest.json file</span></span>

<span data-ttu-id="6acb8-115">每个扩展包的根 `manifest.json` 目录都必须有一个文件。</span><span class="sxs-lookup"><span data-stu-id="6acb8-115">Every extension package must have a `manifest.json` file at the root.</span></span>  <span data-ttu-id="6acb8-116">清单提供扩展的详细信息、扩展包版本、扩展名称和说明等。</span><span class="sxs-lookup"><span data-stu-id="6acb8-116">The manifest provides details of your extension, the extension package version, the extension name and description, and so on.</span></span>  

<span data-ttu-id="6acb8-117">下面的代码段概述了文件所需的基本 `manifest.json` 信息。</span><span class="sxs-lookup"><span data-stu-id="6acb8-117">The following code snippet outlines the basic information needed in your `manifest.json` file.</span></span>  

```json
{
    "name": "NASA picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium extension to display the NASA picture of the day."
}
```  

## <a name="step-2-add-icons"></a><span data-ttu-id="6acb8-118">步骤 2：添加图标</span><span class="sxs-lookup"><span data-stu-id="6acb8-118">Step 2: Add icons</span></span>  

<span data-ttu-id="6acb8-119">首先在 `icons` 项目中创建用于存储图标图像文件的目录。</span><span class="sxs-lookup"><span data-stu-id="6acb8-119">Start by creating the `icons` directory in your project to store the icon image files.</span></span>  <span data-ttu-id="6acb8-120">图标用于用户选择启动扩展的按钮的背景图像。</span><span class="sxs-lookup"><span data-stu-id="6acb8-120">The icons are used for the background image of the button that users select to launch the extension.</span></span>  

:::image type="complex" source="./media/part1-badge1.png" alt-text="工具栏上的图标以打开扩展":::
   <span data-ttu-id="6acb8-122">工具栏上的图标以打开扩展</span><span class="sxs-lookup"><span data-stu-id="6acb8-122">Icon on the toolbar to open your extension</span></span>  
:::image-end:::  

<span data-ttu-id="6acb8-123">对于图标，我们建议使用：</span><span class="sxs-lookup"><span data-stu-id="6acb8-123">For icons, we recommend using:</span></span> 
*   `PNG` <span data-ttu-id="6acb8-124">图标的格式，但您也可以使用 ， `BMP` `GIF` 或 `ICO` `JPEG` 格式。</span><span class="sxs-lookup"><span data-stu-id="6acb8-124">format for icons, but you may also use `BMP`, `GIF`, `ICO` or `JPEG` formats.</span></span>  
*   <span data-ttu-id="6acb8-125">128 x 128 像素的图像，如有必要，浏览器会调整大小。</span><span class="sxs-lookup"><span data-stu-id="6acb8-125">Images that are 128 x 128 px, which are resized by the browser if necessary.</span></span>  

<span data-ttu-id="6acb8-126">项目的目录应类似于以下结构。</span><span class="sxs-lookup"><span data-stu-id="6acb8-126">The directories of your project should be similar to the following structure.</span></span>   

```shell
└── part1
    ├── _manifest.json
    └── icons
        ├── nasapod16x16.png
        ├── nasapod32x32.png
        ├── nasapod48x48.png
        └── nasapod128x128.png
```  

<span data-ttu-id="6acb8-127">接下来，将图标添加到 `manifest.json` 文件中。</span><span class="sxs-lookup"><span data-stu-id="6acb8-127">Next, add the icons to the `manifest.json` file.</span></span> <span data-ttu-id="6acb8-128">使用 `manifest.json` 图标信息更新文件，以便与以下代码段匹配。</span><span class="sxs-lookup"><span data-stu-id="6acb8-128">Update your `manifest.json` file with the icons information so that it matches the following code snippet.</span></span> <span data-ttu-id="6acb8-129">`png`以下代码中列出的文件在本文前面提到的下载文件中可用。</span><span class="sxs-lookup"><span data-stu-id="6acb8-129">The `png` files listed in the following code are available in the download file mentioned earlier in this article.</span></span>  

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

## <a name="step-3-open-a-default-pop-up-dialog"></a><span data-ttu-id="6acb8-130">步骤 3：打开默认弹出对话框</span><span class="sxs-lookup"><span data-stu-id="6acb8-130">Step 3: Open a default pop-up dialog</span></span>  

<span data-ttu-id="6acb8-131">现在，创建 `HTML` 一个文件，以在用户启动扩展时运行。</span><span class="sxs-lookup"><span data-stu-id="6acb8-131">Now, create a `HTML` file to run when the user launches your extension.</span></span>  <span data-ttu-id="6acb8-132">创建在名为 . `popup.html` 的目录中命名的 HTML 文件 `popup` 。</span><span class="sxs-lookup"><span data-stu-id="6acb8-132">Create the HTML file named `popup.html` in a directory named `popup`.</span></span>  <span data-ttu-id="6acb8-133">当用户选择图标以启动扩展时， `popup/popup.html` 将显示为模式对话框。</span><span class="sxs-lookup"><span data-stu-id="6acb8-133">When users select the icon to launch the extension, `popup/popup.html` is displayed as a modal dialog.</span></span>  

<span data-ttu-id="6acb8-134">添加以下代码段中的代码以显示 `popup.html` 星形图像。</span><span class="sxs-lookup"><span data-stu-id="6acb8-134">Add the code from the following code snippet to `popup.html` to display the stars image.</span></span>  

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

<span data-ttu-id="6acb8-135">确保将图像文件 `images/stars.jpeg` 添加到 images 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6acb8-135">Ensure that you add the image file `images/stars.jpeg` to the images folder.</span></span>  <span data-ttu-id="6acb8-136">项目的目录应类似于以下结构。</span><span class="sxs-lookup"><span data-stu-id="6acb8-136">The directories of your project should be similar to the following structure.</span></span>   

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

<span data-ttu-id="6acb8-137">最后，确保将弹出窗口注册到下 `manifest.json` `browser_action` ，如下面的代码片段所示。</span><span class="sxs-lookup"><span data-stu-id="6acb8-137">Finally, ensure you register the pop-up in `manifest.json` under `browser_action`, as shown in the following code snippet.</span></span>  

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

## <a name="next-steps"></a><span data-ttu-id="6acb8-138">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6acb8-138">Next steps</span></span>
<span data-ttu-id="6acb8-139">这是开发工作扩展所需的一切。</span><span class="sxs-lookup"><span data-stu-id="6acb8-139">That is everything you need to develop a working extension.</span></span>  <span data-ttu-id="6acb8-140">现在，继续旁加载并测试扩展。</span><span class="sxs-lookup"><span data-stu-id="6acb8-140">Now, continue on to sideload and test your extension.</span></span> <span data-ttu-id="6acb8-141">有关详细信息，请导航到 [旁加载扩展][TestExtensionSideload]。</span><span class="sxs-lookup"><span data-stu-id="6acb8-141">For more information, navigate to [Sideload an extension][TestExtensionSideload].</span></span>  

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
