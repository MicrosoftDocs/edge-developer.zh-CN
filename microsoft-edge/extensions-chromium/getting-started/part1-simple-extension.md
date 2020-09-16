---
description: 扩展入门第1部分
title: 构建一个简单的扩展名，它会弹出一天的 NASA 图片
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、web 开发、html、css、javascript、开发人员、扩展
ms.openlocfilehash: 826401869b98d339e9b156a3727d94bd1182063d
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015763"
---
# <span data-ttu-id="d999c-104">构建一个简单的扩展名，它会弹出一天的 NASA 图片</span><span class="sxs-lookup"><span data-stu-id="d999c-104">Build A Simple Extension That Pops Up NASA Picture Of The Day</span></span> 
 
<!--  
[Completed Extension Package Source for This Part][ArchiveExtensionGettingStartedPart1]  
-->  

## <span data-ttu-id="d999c-105">概述</span><span class="sxs-lookup"><span data-stu-id="d999c-105">Overview</span></span>  

<span data-ttu-id="d999c-106">在第1部分中，目标是构建一个非常简单的 Edge Chromium 扩展，该扩展从空目录开始。</span><span class="sxs-lookup"><span data-stu-id="d999c-106">In part 1, the goal is to build a very simple Edge Chromium Extension starting with an empty directory.</span></span>  <span data-ttu-id="d999c-107">此扩展的目标是完成以下任务。</span><span class="sxs-lookup"><span data-stu-id="d999c-107">The goal for this Extension is to complete the following tasks.</span></span>  

*   <span data-ttu-id="d999c-108">创建可在多个位置使用不同大小的扩展的图标</span><span class="sxs-lookup"><span data-stu-id="d999c-108">Create icons for the Extension that may be used in multiple places and in different sizes</span></span>  
*   <span data-ttu-id="d999c-109">创建简单 `manifest.json` 文件</span><span class="sxs-lookup"><span data-stu-id="d999c-109">Create a simple `manifest.json` file</span></span>  
*   <span data-ttu-id="d999c-110">显示一个启动图标，当选中该图标时，将显示一个包含一天的 NASA 图片的弹出窗口</span><span class="sxs-lookup"><span data-stu-id="d999c-110">Display a launch icon that when selected displays a pop-up window containing the NASA picture of the day</span></span>  

## <span data-ttu-id="d999c-111">清单文件基础知识</span><span class="sxs-lookup"><span data-stu-id="d999c-111">The manifest file basics</span></span>  

<span data-ttu-id="d999c-112">每个扩展包都必须在 `manifest.json` 根目录处拥有一个文件。</span><span class="sxs-lookup"><span data-stu-id="d999c-112">Every Extension package must have a `manifest.json` file at the root.</span></span>  <span data-ttu-id="d999c-113">你应该将其视为扩展的蓝图。</span><span class="sxs-lookup"><span data-stu-id="d999c-113">You should think of this as the blueprint for the Extension.</span></span>  <span data-ttu-id="d999c-114">它告知浏览器引擎扩展所需的扩展 API 版本、扩展的名称和说明以及许多其他详细信息，请参见本多部分扩展入门指南。</span><span class="sxs-lookup"><span data-stu-id="d999c-114">It tells the browser engine what version of the Extension API the Extension expects, the name and description of the Extension, and lots of other details, many of which are discussed in this multi-part Extension Getting Started guide.</span></span>  

<span data-ttu-id="d999c-115">下面是简单的</span><span class="sxs-lookup"><span data-stu-id="d999c-115">Below is the simple</span></span>  `manifest.json`  

```json
{
    "name": "NASA Picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium Extension to show the NASA Picture of the Day."
}
```  

## <span data-ttu-id="d999c-116">扩展图标设置</span><span class="sxs-lookup"><span data-stu-id="d999c-116">Extension icons setup</span></span>  

<span data-ttu-id="d999c-117">接下来，将一些图标添加到 " `manifest.json` 文件 \ ("，然后创建一个 `/icons` 具有图标文件 \ ) 的新目录。</span><span class="sxs-lookup"><span data-stu-id="d999c-117">Next add some icons to `manifest.json` file \(and create a new `/icons` directory with the icons files\).</span></span>  <span data-ttu-id="d999c-118">如果有一个 \ ) 和其他合适的位置，则该图标用于用户选择以启动扩展 (的按钮的背景图像。</span><span class="sxs-lookup"><span data-stu-id="d999c-118">The icons are used for the background image of the button the user selects to launch the extension \(if there is one\), and other places that are appropriate.</span></span>  

`PNG` <span data-ttu-id="d999c-119">是推荐的格式，但你也可以使用 `BMP` 、 `GIF` `ICO` 和 `JPEG` 。</span><span class="sxs-lookup"><span data-stu-id="d999c-119">is the recommended format, but you may also use `BMP`, `GIF`, `ICO` and `JPEG`.</span></span>  <span data-ttu-id="d999c-120">建议始终至少具有 "128x128 像素大小" 图标，并且浏览器会根据需要自动调整其大小。</span><span class="sxs-lookup"><span data-stu-id="d999c-120">It is recommended to always have at least a 128x128 pixels size icon and the browser automatically resizes it as necessary.</span></span>  

<span data-ttu-id="d999c-121">目录结构应类似于下图。</span><span class="sxs-lookup"><span data-stu-id="d999c-121">Your directory structure should look like the following diagram.</span></span>  

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

<span data-ttu-id="d999c-122">更新后的 `manifest.json` 文件应如下所示。</span><span class="sxs-lookup"><span data-stu-id="d999c-122">Your updated `manifest.json` file should appear as follows.</span></span>  

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
> <span data-ttu-id="d999c-123">`png`此页面顶部提及的 "zip 下载" 中提供了上述代码的图标文件。</span><span class="sxs-lookup"><span data-stu-id="d999c-123">The icon `png` files listed previous code are available in the zip download mentioned at the top of this page.</span></span>  

## <span data-ttu-id="d999c-124">添加默认弹出对话框</span><span class="sxs-lookup"><span data-stu-id="d999c-124">Adding a default pop-up dialog</span></span>  

<span data-ttu-id="d999c-125">现在，创建一个在 `HTML` 用户选择 "扩展" 图标时自动运行的文件。</span><span class="sxs-lookup"><span data-stu-id="d999c-125">Now, create an `HTML` file that is automatically run when the user selects on the extension icon.</span></span>  

:::image type="complex" source="./media/part1-badge1.png" alt-text="工具栏锁屏提醒图标":::
   <span data-ttu-id="d999c-127">工具栏锁屏提醒图标</span><span class="sxs-lookup"><span data-stu-id="d999c-127">Toolbar Badge Icon</span></span>
:::image-end:::

<!--![Toolbar Badge Icon][ImagePart1Badge1]  -->  

<span data-ttu-id="d999c-128">HTML 文件已命名 `popup/popup.html` 。</span><span class="sxs-lookup"><span data-stu-id="d999c-128">The HTML file is named `popup/popup.html`.</span></span>  <span data-ttu-id="d999c-129">选择 "扩展" 图标将启动 " `popup/popup.html` 模式" 对话框，直到你在对话框外选择。</span><span class="sxs-lookup"><span data-stu-id="d999c-129">Selecting the Extension icon launches `popup/popup.html` as modal dialog that stays up until you select outside the dialog.</span></span>  

<span data-ttu-id="d999c-130">为此，请在下面的代码中将文件注册为默认弹出窗口 `manifest.json` `browser_action` 。</span><span class="sxs-lookup"><span data-stu-id="d999c-130">For this, register the file as a default pop-up in the `manifest.json` under `browser_action` in the following code.</span></span>  

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

<span data-ttu-id="d999c-131">在 `popup` 目录中，添加文件 `popup.html` 并使其呈现星形图像。</span><span class="sxs-lookup"><span data-stu-id="d999c-131">In the `popup` directory , add the file `popup.html` and have it render the stars image.</span></span>  <span data-ttu-id="d999c-132">下面是 `popup.html` 文件。</span><span class="sxs-lookup"><span data-stu-id="d999c-132">Here is the `popup.html` file.</span></span>  

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

 <span data-ttu-id="d999c-133">此外，还可添加 `images/stars.jpeg` 文件中引用的图像文件 `popup.html` 。</span><span class="sxs-lookup"><span data-stu-id="d999c-133">Also, add an image file `images/stars.jpeg` that is referenced in the `popup.html` file.</span></span>  

<span data-ttu-id="d999c-134">示例扩展的目录结构显示在下图中。</span><span class="sxs-lookup"><span data-stu-id="d999c-134">The directory structure for the example Extension is displayed in the following diagram.</span></span>  

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

<!--  
> [!NOTE]
> The `images/stars.jpeg` file listed in the previous image is available in the [zip download][ArchiveExtensionGettingStartedPart1].  
-->  

<span data-ttu-id="d999c-135">这就是构建工作扩展所需的一切。</span><span class="sxs-lookup"><span data-stu-id="d999c-135">That is everything you need to build a working Extension.</span></span>  <span data-ttu-id="d999c-136">剩下的只是测试它。</span><span class="sxs-lookup"><span data-stu-id="d999c-136">All that is left to do is test it.</span></span>  

<span data-ttu-id="d999c-137">下一节将介绍如何将扩展 \ (（有时称为 "侧加载 \ ) "）加载到 Microsoft Edge \ (Chromium \ ) 浏览器中进行测试。</span><span class="sxs-lookup"><span data-stu-id="d999c-137">The next section explains how to load the Extension \(sometimes called side loading\) into the Microsoft Edge \(Chromium\) browser to test it.</span></span>  

## <span data-ttu-id="d999c-138">在你的浏览器中进行开发时在浏览器中本地运行你的扩展 \ (面加载 \ ) </span><span class="sxs-lookup"><span data-stu-id="d999c-138">Run your Extension locally in your browser while developing it \(side-loading\)</span></span>  

<span data-ttu-id="d999c-139">Microsoft Edge \ (Chromium \ ) 浏览器提供一种安全且简单的方法，以便你在开发时运行和调试扩展。</span><span class="sxs-lookup"><span data-stu-id="d999c-139">The Microsoft Edge \(Chromium\) browser provides a safe and simple way for you to run as well as debug your Extensions while you are developing.</span></span>  

<span data-ttu-id="d999c-140">该过程非常简单。</span><span class="sxs-lookup"><span data-stu-id="d999c-140">The process is quite simple.</span></span>  <span data-ttu-id="d999c-141">必须首先选择浏览器顶部的三个圆点。</span><span class="sxs-lookup"><span data-stu-id="d999c-141">You must first select the three dots at the top of your browser.</span></span>  <span data-ttu-id="d999c-142">接下来， `Extensions` 从上下文菜单中进行选择，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="d999c-142">Next, choose `Extensions` from the context menu as shown in the following image.</span></span>  

:::image type="complex" source="./media/part1-threedots.png" alt-text="选择扩展":::
   <span data-ttu-id="d999c-144">选择扩展</span><span class="sxs-lookup"><span data-stu-id="d999c-144">Choose Extensions</span></span>
:::image-end:::

<!--![Choose Extensions][ImagePart1Threedots]  -->  

<span data-ttu-id="d999c-145">如果您位于 " **扩展** " 页面上，如下图所示，请启用 **开发人员模式** ，方法是启用页面左下角的切换，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="d999c-145">When you are on the **Extensions** page as shown in the following image, enable the **Developer mode** by enabling the toggle at the bottom left of the page as shown in the following image.</span></span>  

:::image type="complex" source="./media/part1-developermode-toggle.png" alt-text="启用开发人员模式":::
   <span data-ttu-id="d999c-147">启用开发人员模式</span><span class="sxs-lookup"><span data-stu-id="d999c-147">Enable Developer Mode</span></span>
:::image-end:::

<!--![Enable Developer Mode][ImagePart1DevelopermodeToggle]  -->  

## <span data-ttu-id="d999c-148">安装和更新面加载的扩展</span><span class="sxs-lookup"><span data-stu-id="d999c-148">Installing and updating side-loaded Extensions</span></span>  

<span data-ttu-id="d999c-149">首次安装扩展时，请选择 `Load Unpacked` 下图中所示的选项。</span><span class="sxs-lookup"><span data-stu-id="d999c-149">The first time you want to install your Extension, you choose the `Load Unpacked` option as shown in the following image.</span></span>  <span data-ttu-id="d999c-150">这会提示你输入一个目录，其中包含你的扩展资源文件。</span><span class="sxs-lookup"><span data-stu-id="d999c-150">This prompts you for a directory where you have your Extension assets file by file.</span></span>  <span data-ttu-id="d999c-151">这将安装扩展，就像从应用商店下载的一样。</span><span class="sxs-lookup"><span data-stu-id="d999c-151">This installs the Extension as if you had downloaded it from a store.</span></span>  

:::image type="complex" source="./media/part1-installed-extension.png" alt-text="已安装的扩展":::
   <span data-ttu-id="d999c-153">已安装的扩展</span><span class="sxs-lookup"><span data-stu-id="d999c-153">Installed Extensions</span></span>
:::image-end:::

<!--![Installed Extensions][ImagePart1InstalledExtension]  -->  

<span data-ttu-id="d999c-154">安装扩展后，您可以通过选择 " `Reload` 扩展" 列表下的按钮更新它。</span><span class="sxs-lookup"><span data-stu-id="d999c-154">After you install your Extension, you may update it by selecting the `Reload` button under your Extension listing.</span></span>  

<span data-ttu-id="d999c-155">若要从浏览器中删除扩展，请单击 `Remove` "扩展" 列表底部的按钮。</span><span class="sxs-lookup"><span data-stu-id="d999c-155">To remove the Extension from your browser, click the `Remove` button on the bottom of the Extension listing.</span></span>  

## <span data-ttu-id="d999c-156">调试扩展</span><span class="sxs-lookup"><span data-stu-id="d999c-156">Debugging Extensions</span></span>  

<span data-ttu-id="d999c-157">调试扩展非常简单，并且支持 Edge Chromium DevTools 中的所有功能。</span><span class="sxs-lookup"><span data-stu-id="d999c-157">Debugging Extensions is quite easy and supports all of the features in Edge Chromium DevTools.</span></span>  <span data-ttu-id="d999c-158">此入门指南中未涉及这些详细信息，但对于成功生成扩展非常重要。</span><span class="sxs-lookup"><span data-stu-id="d999c-158">Those details however are not covered in this getting started guide but are very important to successfully build Extensions.</span></span>  

<!-- image links -->  

<!--[ImagePart1Heirarchy]: ./media/part1-heirarchy.png "Directory Structure"  -->  
<!--[ImagePart1Badge1]: ./media/part1-badge1.png "Toolbar Badge Icon"  -->  
<!--[ImagePart1Heirarchy1]: ./media/part1-heirarchy1.png "Directory Structure for Extension"  -->  
<!--[ImagePart1Threedots]: ./media/part1-threedots.png "Choose Extensions"  -->  
<!--[ImagePart1DevelopermodeToggle]: ./media/part1-developermode-toggle.png "Enable Developer Mode"  -->  
<!--[ImagePart1InstalledExtension]: ./media/part1-installed-extension.png "Installed Extensions"  -->  

<!-- links -->  

[ArchiveExtensionGettingStartedPart1]: ./extension-source/extension-getting-started-part1.zip "已完成此部件的扩展程序包源 |Microsoft 文档"  
