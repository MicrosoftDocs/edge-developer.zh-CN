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
# <span data-ttu-id="da447-104">创建扩展教程-第1部分</span><span class="sxs-lookup"><span data-stu-id="da447-104">Create an extension tutorial - Part 1</span></span>  

## <span data-ttu-id="da447-105">概述</span><span class="sxs-lookup"><span data-stu-id="da447-105">Overview</span></span>  

<span data-ttu-id="da447-106">本教程的目标是构建 Microsoft Edge (Chromium) 扩展名，从空目录开始。</span><span class="sxs-lookup"><span data-stu-id="da447-106">The goal for this tutorial is to build a Microsoft Edge (Chromium) extension starting with an empty directory.</span></span> <span data-ttu-id="da447-107">我们将生成一个扩展，它将弹出一天的 NASA 图片。</span><span class="sxs-lookup"><span data-stu-id="da447-107">We'll build an extension that pops up the NASA picture of the day.</span></span> <span data-ttu-id="da447-108">在本教程中，你将了解如何通过以下方式创建扩展：</span><span class="sxs-lookup"><span data-stu-id="da447-108">In this tutorial, you'll learn how to create an extension by:</span></span>

*   <span data-ttu-id="da447-109">创建 `manifest.json` 文件。</span><span class="sxs-lookup"><span data-stu-id="da447-109">Creating a `manifest.json` file.</span></span>  
*   <span data-ttu-id="da447-110">添加图标。</span><span class="sxs-lookup"><span data-stu-id="da447-110">Adding icons.</span></span>  
*   <span data-ttu-id="da447-111">打开一个默认的弹出对话框。</span><span class="sxs-lookup"><span data-stu-id="da447-111">Opening a default pop-up dialog.</span></span>  

## <span data-ttu-id="da447-112">开始之前</span><span class="sxs-lookup"><span data-stu-id="da447-112">Before you Begin</span></span>

<span data-ttu-id="da447-113">如果你想要测试将在本教程中生成的完成的扩展，请下载 [源代码][ArchiveExtensionGettingStartedPart1]。</span><span class="sxs-lookup"><span data-stu-id="da447-113">If you'd like to test out the completed extension that you'll build in this tutorial, download the [source code][ArchiveExtensionGettingStartedPart1].</span></span>  

## <span data-ttu-id="da447-114">步骤1：创建 `manifest.json` 文件</span><span class="sxs-lookup"><span data-stu-id="da447-114">Step 1: Create a `manifest.json` file</span></span>

<span data-ttu-id="da447-115">每个扩展包都必须在 `manifest.json` 根目录处拥有一个文件。</span><span class="sxs-lookup"><span data-stu-id="da447-115">Every extension package must have a `manifest.json` file at the root.</span></span>  <span data-ttu-id="da447-116">清单提供你的扩展、扩展包版本、扩展名名称和说明等详细信息。</span><span class="sxs-lookup"><span data-stu-id="da447-116">The manifest provides details of your extension, the extension package version, the extension name and description, and so on.</span></span>  

<span data-ttu-id="da447-117">以下代码片段概述了文件中所需的基本信息 `manifest.json` 。</span><span class="sxs-lookup"><span data-stu-id="da447-117">The following code snippet outlines the basic information needed in your `manifest.json` file.</span></span>  

```json
{
    "name": "NASA picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium extension to display the NASA picture of the day."
}
```  

## <span data-ttu-id="da447-118">步骤2：添加图标</span><span class="sxs-lookup"><span data-stu-id="da447-118">Step 2: Add icons</span></span>  

<span data-ttu-id="da447-119">首先 `icons` 在项目中创建目录以存储图标图像文件。</span><span class="sxs-lookup"><span data-stu-id="da447-119">Start by creating the `icons` directory in your project to store the icon image files.</span></span>  <span data-ttu-id="da447-120">图标用于用户选择以启动扩展的按钮的背景图像。</span><span class="sxs-lookup"><span data-stu-id="da447-120">The icons are used for the background image of the button that users select to launch the extension.</span></span>  

:::image type="complex" source="./media/part1-badge1.png" alt-text="工具栏上的图标以打开您的扩展":::
   <span data-ttu-id="da447-122">工具栏上的图标以打开您的扩展</span><span class="sxs-lookup"><span data-stu-id="da447-122">Icon on the toolbar to open your extension</span></span>
:::image-end:::

<span data-ttu-id="da447-123">对于图标，建议使用：</span><span class="sxs-lookup"><span data-stu-id="da447-123">For icons, we recommend using:</span></span> 
*   `PNG` <span data-ttu-id="da447-124">图标的格式，但你也可以使用 `BMP` 、 `GIF` `ICO` 或 `JPEG` 格式。</span><span class="sxs-lookup"><span data-stu-id="da447-124">format for icons, but you may also use `BMP`, `GIF`, `ICO` or `JPEG` formats.</span></span>  
*   <span data-ttu-id="da447-125">128 x 128 px 的图像（如有必要）根据浏览器调整大小。</span><span class="sxs-lookup"><span data-stu-id="da447-125">Images that are 128 x 128 px, which are resized by the browser if necessary.</span></span>  

<span data-ttu-id="da447-126">项目的目录应类似于以下结构。</span><span class="sxs-lookup"><span data-stu-id="da447-126">The directories of your project should be similar to the following structure.</span></span>   

```shell
└── part1
    ├── _manifest.json
    └── icons
        ├── nasapod16x16.png
        ├── nasapod32x32.png
        ├── nasapod48x48.png
        └── nasapod128x128.png
```  

<span data-ttu-id="da447-127">接下来，将图标添加到 `manifest.json` 文件中。</span><span class="sxs-lookup"><span data-stu-id="da447-127">Next, add the icons to the `manifest.json` file.</span></span> <span data-ttu-id="da447-128">`manifest.json`用图标信息更新文件，使其与以下代码片段匹配。</span><span class="sxs-lookup"><span data-stu-id="da447-128">Update your `manifest.json` file with the icons information so that it matches the following code snippet.</span></span> <span data-ttu-id="da447-129">`png`以下代码中列出的文件在本文前面所述的下载文件中可用。</span><span class="sxs-lookup"><span data-stu-id="da447-129">The `png` files listed in the following code are available in the download file mentioned earlier in this article.</span></span>  

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

## <span data-ttu-id="da447-130">步骤3：打开默认的弹出对话框</span><span class="sxs-lookup"><span data-stu-id="da447-130">Step 3: Open a default pop-up dialog</span></span>  

<span data-ttu-id="da447-131">现在，创建一个 `HTML` 在用户启动您的扩展时运行的文件。</span><span class="sxs-lookup"><span data-stu-id="da447-131">Now, create a `HTML` file that's run when the user launches your extension.</span></span>  <span data-ttu-id="da447-132">创建 `popup.html` 在名为的目录中调用的 HTML 文件 `popup` 。</span><span class="sxs-lookup"><span data-stu-id="da447-132">Create the HTML file called `popup.html` in a directory called `popup`.</span></span>  <span data-ttu-id="da447-133">当用户选择启动扩展的图标时， `popup/popup.html` 将显示为模式对话框。</span><span class="sxs-lookup"><span data-stu-id="da447-133">When users select the icon to launch the extension, `popup/popup.html` is displayed as a modal dialog.</span></span>  

<span data-ttu-id="da447-134">将以下代码片段中的代码添加到 `popup.html` 以显示星图像。</span><span class="sxs-lookup"><span data-stu-id="da447-134">Add the code from the following code snippet to `popup.html` to display the stars image.</span></span>  

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

<span data-ttu-id="da447-135">确保将图像文件添加 `images/stars.jpeg` 到 "images" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="da447-135">Ensure that you add the image file `images/stars.jpeg` to the images folder.</span></span>  <span data-ttu-id="da447-136">项目的目录应类似于以下结构。</span><span class="sxs-lookup"><span data-stu-id="da447-136">The directories of your project should be similar to the following structure.</span></span>   

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

<span data-ttu-id="da447-137">最后，确保在 "" 下注册弹出窗口 `manifest.json` `browser_action` ，如以下代码片段所示。</span><span class="sxs-lookup"><span data-stu-id="da447-137">Finally, ensure you register the pop-up in `manifest.json` under `browser_action`, as shown in the following code snippet.</span></span>  

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

## <span data-ttu-id="da447-138">后续步骤</span><span class="sxs-lookup"><span data-stu-id="da447-138">Next steps</span></span>
<span data-ttu-id="da447-139">这就是开发工作扩展所需的所有内容。</span><span class="sxs-lookup"><span data-stu-id="da447-139">That's everything you need to develop a working extension.</span></span> <span data-ttu-id="da447-140">现在，继续旁加载并测试您的扩展。</span><span class="sxs-lookup"><span data-stu-id="da447-140">Now, continue on to sideload and test your extension.</span></span> <span data-ttu-id="da447-141">有关详细信息，请参阅 [旁加载扩展][TestExtensionSideload]。</span><span class="sxs-lookup"><span data-stu-id="da447-141">For more information, see [Sideload an extension][TestExtensionSideload].</span></span>  


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
