---
description: Extensions Getting Started Part 1
title: Build A Simple Extension That Pops Up NASA Picture Of The Day
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, web development, html, css, javascript, developer, extensions
ms.openlocfilehash: 826401869b98d339e9b156a3727d94bd1182063d
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015763"
---
# <span data-ttu-id="7a214-104">Build A Simple Extension That Pops Up NASA Picture Of The Day</span><span class="sxs-lookup"><span data-stu-id="7a214-104">Build A Simple Extension That Pops Up NASA Picture Of The Day</span></span> 
 
<!--  
[Completed Extension Package Source for This Part][ArchiveExtensionGettingStartedPart1]  
-->  

## <span data-ttu-id="7a214-105">Overview</span><span class="sxs-lookup"><span data-stu-id="7a214-105">Overview</span></span>  

<span data-ttu-id="7a214-106">In part 1, the goal is to build a very simple Edge Chromium Extension starting with an empty directory.</span><span class="sxs-lookup"><span data-stu-id="7a214-106">In part 1, the goal is to build a very simple Edge Chromium Extension starting with an empty directory.</span></span>  <span data-ttu-id="7a214-107">The goal for this Extension is to complete the following tasks.</span><span class="sxs-lookup"><span data-stu-id="7a214-107">The goal for this Extension is to complete the following tasks.</span></span>  

*   <span data-ttu-id="7a214-108">Create icons for the Extension that may be used in multiple places and in different sizes</span><span class="sxs-lookup"><span data-stu-id="7a214-108">Create icons for the Extension that may be used in multiple places and in different sizes</span></span>  
*   <span data-ttu-id="7a214-109">Create a simple `manifest.json` file</span><span class="sxs-lookup"><span data-stu-id="7a214-109">Create a simple `manifest.json` file</span></span>  
*   <span data-ttu-id="7a214-110">Display a launch icon that when selected displays a pop-up window containing the NASA picture of the day</span><span class="sxs-lookup"><span data-stu-id="7a214-110">Display a launch icon that when selected displays a pop-up window containing the NASA picture of the day</span></span>  

## <span data-ttu-id="7a214-111">The manifest file basics</span><span class="sxs-lookup"><span data-stu-id="7a214-111">The manifest file basics</span></span>  

<span data-ttu-id="7a214-112">Every Extension package must have a `manifest.json` file at the root.</span><span class="sxs-lookup"><span data-stu-id="7a214-112">Every Extension package must have a `manifest.json` file at the root.</span></span>  <span data-ttu-id="7a214-113">You should think of this as the blueprint for the Extension.</span><span class="sxs-lookup"><span data-stu-id="7a214-113">You should think of this as the blueprint for the Extension.</span></span>  <span data-ttu-id="7a214-114">It tells the browser engine what version of the Extension API the Extension expects, the name and description of the Extension, and lots of other details, many of which are discussed in this multi-part Extension Getting Started guide.</span><span class="sxs-lookup"><span data-stu-id="7a214-114">It tells the browser engine what version of the Extension API the Extension expects, the name and description of the Extension, and lots of other details, many of which are discussed in this multi-part Extension Getting Started guide.</span></span>  

<span data-ttu-id="7a214-115">Below is the simple</span><span class="sxs-lookup"><span data-stu-id="7a214-115">Below is the simple</span></span>  `manifest.json`  

```json
{
    "name": "NASA Picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium Extension to show the NASA Picture of the Day."
}
```  

## <span data-ttu-id="7a214-116">Extension icons setup</span><span class="sxs-lookup"><span data-stu-id="7a214-116">Extension icons setup</span></span>  

<span data-ttu-id="7a214-117">Next add some icons to `manifest.json` file \(and create a new `/icons` directory with the icons files\).</span><span class="sxs-lookup"><span data-stu-id="7a214-117">Next add some icons to `manifest.json` file \(and create a new `/icons` directory with the icons files\).</span></span>  <span data-ttu-id="7a214-118">The icons are used for the background image of the button the user selects to launch the extension \(if there is one\), and other places that are appropriate.</span><span class="sxs-lookup"><span data-stu-id="7a214-118">The icons are used for the background image of the button the user selects to launch the extension \(if there is one\), and other places that are appropriate.</span></span>  

`PNG` <span data-ttu-id="7a214-119">is the recommended format, but you may also use `BMP`, `GIF`, `ICO` and `JPEG`.</span><span class="sxs-lookup"><span data-stu-id="7a214-119">is the recommended format, but you may also use `BMP`, `GIF`, `ICO` and `JPEG`.</span></span>  <span data-ttu-id="7a214-120">It is recommended to always have at least a 128x128 pixels size icon and the browser automatically resizes it as necessary.</span><span class="sxs-lookup"><span data-stu-id="7a214-120">It is recommended to always have at least a 128x128 pixels size icon and the browser automatically resizes it as necessary.</span></span>  

<span data-ttu-id="7a214-121">Your directory structure should look like the following diagram.</span><span class="sxs-lookup"><span data-stu-id="7a214-121">Your directory structure should look like the following diagram.</span></span>  

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

<span data-ttu-id="7a214-122">Your updated `manifest.json` file should appear as follows.</span><span class="sxs-lookup"><span data-stu-id="7a214-122">Your updated `manifest.json` file should appear as follows.</span></span>  

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
> <span data-ttu-id="7a214-123">The icon `png` files listed previous code are available in the zip download mentioned at the top of this page.</span><span class="sxs-lookup"><span data-stu-id="7a214-123">The icon `png` files listed previous code are available in the zip download mentioned at the top of this page.</span></span>  

## <span data-ttu-id="7a214-124">Adding a default pop-up dialog</span><span class="sxs-lookup"><span data-stu-id="7a214-124">Adding a default pop-up dialog</span></span>  

<span data-ttu-id="7a214-125">Now, create an `HTML` file that is automatically run when the user selects on the extension icon.</span><span class="sxs-lookup"><span data-stu-id="7a214-125">Now, create an `HTML` file that is automatically run when the user selects on the extension icon.</span></span>  

:::image type="complex" source="./media/part1-badge1.png" alt-text="Directory Structure":::
   <span data-ttu-id="7a214-127">Toolbar Badge Icon</span><span class="sxs-lookup"><span data-stu-id="7a214-127">Toolbar Badge Icon</span></span>
:::image-end:::

<!--![Toolbar Badge Icon][ImagePart1Badge1]  -->  

<span data-ttu-id="7a214-128">The HTML file is named `popup/popup.html`.</span><span class="sxs-lookup"><span data-stu-id="7a214-128">The HTML file is named `popup/popup.html`.</span></span>  <span data-ttu-id="7a214-129">Selecting the Extension icon launches `popup/popup.html` as modal dialog that stays up until you select outside the dialog.</span><span class="sxs-lookup"><span data-stu-id="7a214-129">Selecting the Extension icon launches `popup/popup.html` as modal dialog that stays up until you select outside the dialog.</span></span>  

<span data-ttu-id="7a214-130">For this, register the file as a default pop-up in the `manifest.json` under `browser_action` in the following code.</span><span class="sxs-lookup"><span data-stu-id="7a214-130">For this, register the file as a default pop-up in the `manifest.json` under `browser_action` in the following code.</span></span>  

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

<span data-ttu-id="7a214-131">In the `popup` directory , add the file `popup.html` and have it render the stars image.</span><span class="sxs-lookup"><span data-stu-id="7a214-131">In the `popup` directory , add the file `popup.html` and have it render the stars image.</span></span>  <span data-ttu-id="7a214-132">Here is the `popup.html` file.</span><span class="sxs-lookup"><span data-stu-id="7a214-132">Here is the `popup.html` file.</span></span>  

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

 <span data-ttu-id="7a214-133">Also, add an image file `images/stars.jpeg` that is referenced in the `popup.html` file.</span><span class="sxs-lookup"><span data-stu-id="7a214-133">Also, add an image file `images/stars.jpeg` that is referenced in the `popup.html` file.</span></span>  

<span data-ttu-id="7a214-134">The directory structure for the example Extension is displayed in the following diagram.</span><span class="sxs-lookup"><span data-stu-id="7a214-134">The directory structure for the example Extension is displayed in the following diagram.</span></span>  

<!--  
:::image type="complex" source="./media/part1-heirarchy1.png" alt-text="Directory Structure":::
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

<span data-ttu-id="7a214-135">That is everything you need to build a working Extension.</span><span class="sxs-lookup"><span data-stu-id="7a214-135">That is everything you need to build a working Extension.</span></span>  <span data-ttu-id="7a214-136">All that is left to do is test it.</span><span class="sxs-lookup"><span data-stu-id="7a214-136">All that is left to do is test it.</span></span>  

<span data-ttu-id="7a214-137">The next section explains how to load the Extension \(sometimes called side loading\) into the Microsoft Edge \(Chromium\) browser to test it.</span><span class="sxs-lookup"><span data-stu-id="7a214-137">The next section explains how to load the Extension \(sometimes called side loading\) into the Microsoft Edge \(Chromium\) browser to test it.</span></span>  

## <span data-ttu-id="7a214-138">Run your Extension locally in your browser while developing it \(side-loading\)</span><span class="sxs-lookup"><span data-stu-id="7a214-138">Run your Extension locally in your browser while developing it \(side-loading\)</span></span>  

<span data-ttu-id="7a214-139">The Microsoft Edge \(Chromium\) browser provides a safe and simple way for you to run as well as debug your Extensions while you are developing.</span><span class="sxs-lookup"><span data-stu-id="7a214-139">The Microsoft Edge \(Chromium\) browser provides a safe and simple way for you to run as well as debug your Extensions while you are developing.</span></span>  

<span data-ttu-id="7a214-140">The process is quite simple.</span><span class="sxs-lookup"><span data-stu-id="7a214-140">The process is quite simple.</span></span>  <span data-ttu-id="7a214-141">You must first select the three dots at the top of your browser.</span><span class="sxs-lookup"><span data-stu-id="7a214-141">You must first select the three dots at the top of your browser.</span></span>  <span data-ttu-id="7a214-142">Next, choose `Extensions` from the context menu as shown in the following image.</span><span class="sxs-lookup"><span data-stu-id="7a214-142">Next, choose `Extensions` from the context menu as shown in the following image.</span></span>  

:::image type="complex" source="./media/part1-threedots.png" alt-text="Directory Structure":::
   <span data-ttu-id="7a214-144">Choose Extensions</span><span class="sxs-lookup"><span data-stu-id="7a214-144">Choose Extensions</span></span>
:::image-end:::

<!--![Choose Extensions][ImagePart1Threedots]  -->  

<span data-ttu-id="7a214-145">When you are on the **Extensions** page as shown in the following image, enable the **Developer mode** by enabling the toggle at the bottom left of the page as shown in the following image.</span><span class="sxs-lookup"><span data-stu-id="7a214-145">When you are on the **Extensions** page as shown in the following image, enable the **Developer mode** by enabling the toggle at the bottom left of the page as shown in the following image.</span></span>  

:::image type="complex" source="./media/part1-developermode-toggle.png" alt-text="Directory Structure":::
   <span data-ttu-id="7a214-147">Enable Developer Mode</span><span class="sxs-lookup"><span data-stu-id="7a214-147">Enable Developer Mode</span></span>
:::image-end:::

<!--![Enable Developer Mode][ImagePart1DevelopermodeToggle]  -->  

## <span data-ttu-id="7a214-148">Installing and updating side-loaded Extensions</span><span class="sxs-lookup"><span data-stu-id="7a214-148">Installing and updating side-loaded Extensions</span></span>  

<span data-ttu-id="7a214-149">The first time you want to install your Extension, you choose the `Load Unpacked` option as shown in the following image.</span><span class="sxs-lookup"><span data-stu-id="7a214-149">The first time you want to install your Extension, you choose the `Load Unpacked` option as shown in the following image.</span></span>  <span data-ttu-id="7a214-150">This prompts you for a directory where you have your Extension assets file by file.</span><span class="sxs-lookup"><span data-stu-id="7a214-150">This prompts you for a directory where you have your Extension assets file by file.</span></span>  <span data-ttu-id="7a214-151">This installs the Extension as if you had downloaded it from a store.</span><span class="sxs-lookup"><span data-stu-id="7a214-151">This installs the Extension as if you had downloaded it from a store.</span></span>  

:::image type="complex" source="./media/part1-installed-extension.png" alt-text="Directory Structure":::
   <span data-ttu-id="7a214-153">Installed Extensions</span><span class="sxs-lookup"><span data-stu-id="7a214-153">Installed Extensions</span></span>
:::image-end:::

<!--![Installed Extensions][ImagePart1InstalledExtension]  -->  

<span data-ttu-id="7a214-154">After you install your Extension, you may update it by selecting the `Reload` button under your Extension listing.</span><span class="sxs-lookup"><span data-stu-id="7a214-154">After you install your Extension, you may update it by selecting the `Reload` button under your Extension listing.</span></span>  

<span data-ttu-id="7a214-155">To remove the Extension from your browser, click the `Remove` button on the bottom of the Extension listing.</span><span class="sxs-lookup"><span data-stu-id="7a214-155">To remove the Extension from your browser, click the `Remove` button on the bottom of the Extension listing.</span></span>  

## <span data-ttu-id="7a214-156">Debugging Extensions</span><span class="sxs-lookup"><span data-stu-id="7a214-156">Debugging Extensions</span></span>  

<span data-ttu-id="7a214-157">Debugging Extensions is quite easy and supports all of the features in Edge Chromium DevTools.</span><span class="sxs-lookup"><span data-stu-id="7a214-157">Debugging Extensions is quite easy and supports all of the features in Edge Chromium DevTools.</span></span>  <span data-ttu-id="7a214-158">Those details however are not covered in this getting started guide but are very important to successfully build Extensions.</span><span class="sxs-lookup"><span data-stu-id="7a214-158">Those details however are not covered in this getting started guide but are very important to successfully build Extensions.</span></span>  

<!-- image links -->  

<!--[ImagePart1Heirarchy]: ./media/part1-heirarchy.png "Directory Structure"  -->  
<!--[ImagePart1Badge1]: ./media/part1-badge1.png "Toolbar Badge Icon"  -->  
<!--[ImagePart1Heirarchy1]: ./media/part1-heirarchy1.png "Directory Structure for Extension"  -->  
<!--[ImagePart1Threedots]: ./media/part1-threedots.png "Choose Extensions"  -->  
<!--[ImagePart1DevelopermodeToggle]: ./media/part1-developermode-toggle.png "Enable Developer Mode"  -->  
<!--[ImagePart1InstalledExtension]: ./media/part1-installed-extension.png "Installed Extensions"  -->  

<!-- links -->  

[ArchiveExtensionGettingStartedPart1]: ./extension-source/extension-getting-started-part1.zip "Completed Extension Package Source for This Part | Microsoft Docs"  
