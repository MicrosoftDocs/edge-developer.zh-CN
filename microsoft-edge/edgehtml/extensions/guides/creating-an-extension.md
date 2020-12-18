---
description: 了解如何创建 Microsoft Edge 扩展
title: 创建扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 15cb7a4c187210c885b5d75770bda1c590a8c5d1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232681"
---
# <span data-ttu-id="2a6c7-104">创建 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="2a6c7-104">Creating A Microsoft Edge Extension</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="2a6c7-105">在本指南中，了解如何为 Microsoft Edge 创建扩展。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-105">In this guide, learn to create an extension for Microsoft Edge.</span></span>  <span data-ttu-id="2a6c7-106">此示例扩展允许你操作特定 CSS [docs.microsoft.com页面][MicrosoftDocs] ，包括浏览清单文件、用户界面以及背景和内容脚本的创建过程。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-106">This example extension allows you to manipulate specific CSS for [docs.microsoft.com][MicrosoftDocs] pages including walking you through creation of a manifest file, the user interface, and background and content scripts.</span></span>  

:::image type="complex" source="../media/color-changer_header.png" alt-text="Docs.microsoft.com正文更改为蓝色":::
   <span data-ttu-id="2a6c7-108">Docs.microsoft.com正文更改为蓝色</span><span class="sxs-lookup"><span data-stu-id="2a6c7-108">Docs.microsoft.com body changed to blue</span></span>
:::image-end:::

<!--![Docs.microsoft.com body changed to blue][ImageColorChangerHeader]  -->  

<span data-ttu-id="2a6c7-109">本教程假定你基本了解什么是浏览器扩展及其工作。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-109">This tutorial assumes you have basic understanding of what a browser extension is and how it work.</span></span>  <span data-ttu-id="2a6c7-110">有关扩展构建基块的更多信息，请参阅扩展 [结构][MDNAnatomyExtension]。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-110">For more imformation about the building blocks for extensions, see [Anatomy of an extension][MDNAnatomyExtension].</span></span>  

<span data-ttu-id="2a6c7-111">在 [GitHub 上下载完整示例的代码][GithubMicrosoftEdgeExtensionsDemosColorChanger]。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-111">Download the code for the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span></span>  

## <span data-ttu-id="2a6c7-112">生成清单文件</span><span class="sxs-lookup"><span data-stu-id="2a6c7-112">Building the manifest file</span></span>  

<span data-ttu-id="2a6c7-113">若要开始，请为扩展创建一个目录，并命名它 `color-changer` 。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-113">To begin, create a directory for your extension and name it `color-changer`.</span></span>  

<span data-ttu-id="2a6c7-114">在文件夹 `color-changer` 内，创建一个名为 `manifest.json` .</span><span class="sxs-lookup"><span data-stu-id="2a6c7-114">Inside the `color-changer` folder, create a file named `manifest.json`.</span></span>  <span data-ttu-id="2a6c7-115">该文件是所有扩展的必需文件，并提供扩展名的重要信息，范围从扩展名到 `manifest.json` 权限。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-115">The `manifest.json` file is required for all extensions and provides important information for the extension, ranging from the extension name to the permissions.</span></span>  

> [!NOTE] 
> <span data-ttu-id="2a6c7-116">本指南将指导你完成本指南中必须使用的所有清单密钥，但有关所有受支持和推荐的清单密钥的列表，请参阅支持的 [清单密钥][ExtensionsApisupportManifestKeys]。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-116">This guide walks you through all the manifest keys you must use in this guide, but for a list of all supported and recommended manifest keys, see [Supported manifest keys][ExtensionsApisupportManifestKeys].</span></span>  

<span data-ttu-id="2a6c7-117">在 `manifest.json` 内部，添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-117">Inside `manifest.json`, add the following code.</span></span>  

```json
{
  "name": "Color Changer",
  "author": "Microsoft Edge Extension Developer",
  "version": "1.0",
  "description": "Change the color of the body on docs.microsoft.com",
  "permissions": [
    "*://docs.microsoft.com/*",
    "tabs"
  ], 
  "browser_action": {
    "default_icon": {
      "20": "images/color-changer20.png",
      "40": "images/color-changer40.png"
    },
    "default_title": "Color Changer",
    "default_popup": "popup.html"
  }
}
```  

### <span data-ttu-id="2a6c7-118">清单键定义</span><span class="sxs-lookup"><span data-stu-id="2a6c7-118">Manifest key definitions</span></span>  

| <span data-ttu-id="2a6c7-119">密钥</span><span class="sxs-lookup"><span data-stu-id="2a6c7-119">Key</span></span> | <span data-ttu-id="2a6c7-120">详细信息</span><span class="sxs-lookup"><span data-stu-id="2a6c7-120">Details</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="2a6c7-121">name</span><span class="sxs-lookup"><span data-stu-id="2a6c7-121">name</span></span>][MDNManifestjsonName] | <span data-ttu-id="2a6c7-122">扩展名。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-122">The name of the extension.</span></span>  |  
| [<span data-ttu-id="2a6c7-123">author</span><span class="sxs-lookup"><span data-stu-id="2a6c7-123">author</span></span>][MDNManifestjsonAuthor] | <span data-ttu-id="2a6c7-124">扩展的作者。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-124">The author of the extension.</span></span>  |  
| [<span data-ttu-id="2a6c7-125">version</span><span class="sxs-lookup"><span data-stu-id="2a6c7-125">version</span></span>][MDNManifestjsonVersion] | <span data-ttu-id="2a6c7-126">分机号码。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-126">The extension version number.</span></span>  |  
| [<span data-ttu-id="2a6c7-127">description</span><span class="sxs-lookup"><span data-stu-id="2a6c7-127">description</span></span>][MDNManifestjsonDescription] | <span data-ttu-id="2a6c7-128">Microsoft Edge 扩展菜单的"关于"部分中显示的扩展说明。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-128">The description of the extension displayed in the About section of the extension menu in Microsoft Edge.</span></span>  |  
| [<span data-ttu-id="2a6c7-129">permissions</span><span class="sxs-lookup"><span data-stu-id="2a6c7-129">permissions</span></span>][MDNManifestjsonPermissions] | <span data-ttu-id="2a6c7-130">请求扩展权限的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-130">An array of strings requesting permissions for the extension.</span></span>  <span data-ttu-id="2a6c7-131">对于扩展，你正在请求查看访问的网站的权限 ("tabs"\) 并更新与""匹配的 URL `*://docs.microsoft.com/*` 上的内容。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-131">For your extension, you are requesting permissions to see the websites visited \("tabs"\) and to update content on URLs matching "`*://docs.microsoft.com/*`".</span></span>  |  
| [<span data-ttu-id="2a6c7-132">browser_action</span><span class="sxs-lookup"><span data-stu-id="2a6c7-132">browser_action</span></span>][MDNManifestjsonBrowserAction] | <span data-ttu-id="2a6c7-133">包含图标的信息。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-133">Contains the information for an icon.</span></span> <span data-ttu-id="2a6c7-134">该图标放置在 Microsoft Edge 工具栏上的地址栏右侧。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-134">The icon is placed on the Microsoft Edge toolbar, to the right of the address bar.</span></span>  |  

#### <span data-ttu-id="2a6c7-135">browser_action关键定义</span><span class="sxs-lookup"><span data-stu-id="2a6c7-135">browser_action Key definitions</span></span>  

| <span data-ttu-id="2a6c7-136">密钥</span><span class="sxs-lookup"><span data-stu-id="2a6c7-136">Key</span></span> | <span data-ttu-id="2a6c7-137">详细信息</span><span class="sxs-lookup"><span data-stu-id="2a6c7-137">Details</span></span> |  
|:--- |:--- |  
| `default_icon` | <span data-ttu-id="2a6c7-138">工具栏中使用的图标。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-138">The icon that is used in the toolbar.</span></span>  |  
| `default_title` | <span data-ttu-id="2a6c7-139">当用户将鼠标悬停在工具栏中的图标上时显示的文本。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-139">The text that is displayed when a user hovers over the icon in the toolbar.</span></span>  |  
| `default_popup` | <span data-ttu-id="2a6c7-140">弹出窗口的 HTML 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-140">The path to the HTML file for the pop-up window.</span></span>  |  

<span data-ttu-id="2a6c7-141">现在，你已创建清单文件，你需要一个扩展的用户界面。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-141">Now that you have created the manifest file, you need a user interface for the extension.</span></span>  

## <span data-ttu-id="2a6c7-142">创建弹出窗口</span><span class="sxs-lookup"><span data-stu-id="2a6c7-142">Creating the pop-up</span></span>  

<span data-ttu-id="2a6c7-143">对于扩展，请为用户界面创建弹出窗口，如下所示。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-143">For your extension, create a pop-up for the user interface, like below.</span></span>  

:::image type="complex" source="../media/color-changer_popup.png" alt-text="扩展的弹出界面":::
   <span data-ttu-id="2a6c7-145">扩展的弹出界面</span><span class="sxs-lookup"><span data-stu-id="2a6c7-145">The pop-up interface of the extension</span></span>
:::image-end:::

<!--![The pop-up interface of the extension][ImageColorChangerPopup]  -->  

<span data-ttu-id="2a6c7-146">在文件夹 `popup.html` 的根目录下创建一个名为 `color-changer` 的文件。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-146">Create a file named `popup.html` in the root of your `color-changer` folder.</span></span>  <span data-ttu-id="2a6c7-147">将以下代码粘贴到 `popup.html` 。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-147">Paste the following code into `popup.html`.</span></span>  

```html
<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" type="text/css" href="css/styles.css" />
    </head>
    <body>
        <h1>Creating a Microsoft Edge Extension</h1>
        <p>Color Changer</p>
        <input id="aliceblue" type="button" value="Aliceblue" />
        <input id="cornsilk" type="button" value="Cornsilk" />
        <input id="reset" type="button" value="Reset" />
        <script src="js/popup.js"></script>
    </body>
</html>
```  

<span data-ttu-id="2a6c7-148">In `popup.html` ， you create a title， a paragraph， and three buttons \ (Aliceblue， Alicesilk， and Reset\) .</span><span class="sxs-lookup"><span data-stu-id="2a6c7-148">In `popup.html`, you create a title, a paragraph, and three buttons \(Aliceblue, Cornsilk, and Reset\).</span></span>  

<span data-ttu-id="2a6c7-149">现在创建一个名为的文件夹 `css` ，在内部创建一个名为 `styles.css` .</span><span class="sxs-lookup"><span data-stu-id="2a6c7-149">Now create a folder named `css` and inside create a file named `styles.css`.</span></span>  <span data-ttu-id="2a6c7-150">添加下面的样式。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-150">Add the styles below.</span></span>  

```css
/* main styles */
* {
    font-family: 'Segoe UI';
}

h1 {
    font-weight: 600;
    font-size: .9em;
}

p {
    font-weight: 500;
    font-size: .8em;
    margin-bottom: 10px;  
}
```  

<span data-ttu-id="2a6c7-151">此 CSS 为扩展提供了一些基本样式。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-151">This CSS gives our extension some basic styles.</span></span>  <span data-ttu-id="2a6c7-152">可随意添加更多样式以自定义扩展。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-152">Feel free to add more styles to customize your extension.</span></span>  

<span data-ttu-id="2a6c7-153">接下来，必须创建与弹出窗口交互的 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-153">Next, you must create the JavaScript file that interacts with the pop-up.</span></span>  <span data-ttu-id="2a6c7-154">创建 `js` 一个文件夹和一个名为内部 `popup.js` 的文件。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-154">Create a `js` folder and a file named `popup.js` inside.</span></span>  <span data-ttu-id="2a6c7-155">使用 `popup.js` 以下代码更新。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-155">Update `popup.js` with the following code.</span></span>  

```JavaScript
// get the buttons by id
let aliceblue = document.getElementById('aliceblue');
let cornsilk = document.getElementById('cornsilk');
let reset = document.getElementById('reset');

// use tabs.insertCSS to change header color on button click

// aliceblue
aliceblue.onclick = () => {
  browser.tabs.insertCSS({code: "body { background: aliceblue !important; }"});
};

// cornsilk
cornsilk.onclick = () => {
  browser.tabs.insertCSS({code: "body { background: cornsilk !important; }"});
};

// back to original
reset.onclick = () => {
  browser.tabs.insertCSS({code: "body { background: none !important; }"});
};
```  

<span data-ttu-id="2a6c7-156">在 `popup.js` 选项卡[][MDNApiTabs]API 中，你可以与浏览器的选项卡进行交互，将脚本和样式注入页面内容。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-156">In `popup.js`, the [tabs][MDNApiTabs] API allows you to interact with the tabs of the browser and inject script and styles into the page content.</span></span>  <span data-ttu-id="2a6c7-157">使用 [tabs.insertCSS () ][MDNApiTabsInsertcss] 方法，将指定的 CSS 注入页面，当单击指定按钮时，该页面将 [docs.microsoft.com][MicrosoftDocs] 上的页眉更改为其他颜色。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-157">Using the [tabs.insertCSS()][MDNApiTabsInsertcss] method, you inject the specified CSS into the page which changes the header on [docs.microsoft.com][MicrosoftDocs] to a different color when the specified button is clicked.</span></span>  

<span data-ttu-id="2a6c7-158">现在你已拥有基本的弹出功能，请向扩展中添加图标。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-158">Now that you have the basic pop-up functionality, add icons to the extension.</span></span>  

## <span data-ttu-id="2a6c7-159">添加图标</span><span class="sxs-lookup"><span data-stu-id="2a6c7-159">Adding icons</span></span>  

<span data-ttu-id="2a6c7-160">图标用于表示浏览器工具栏、扩展菜单和其他位置中的扩展。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-160">Icons are used to represent the extension in the browser toolbar, the extensions menu, and other places.</span></span>  <span data-ttu-id="2a6c7-161">在 [GitHub 上下载扩展图标][GithubMicrosoftEdgeExtensionsDemosColorChangerImages]。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-161">Download the [icons for your extension on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChangerImages].</span></span> <span data-ttu-id="2a6c7-162">有关 Microsoft Edge 中的扩展图标详细信息，请参阅设计 [指南][ExtensionsGuidesDesignIcons]。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-162">For more information about extension icons in Microsoft Edge, see [Design Guide][ExtensionsGuidesDesignIcons].</span></span>  

<span data-ttu-id="2a6c7-163">下载扩展图标后，将图标保存在 `images` 内部文件夹中 `color-changer` 。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-163">After you download the extension icons, save the icons in an `images` folder inside `color-changer`.</span></span>  

<span data-ttu-id="2a6c7-164">工具栏中显示的图标使用已添加到清单文件的browser_action项内部 `default_icon` 进行[][MDNManifestjsonBrowserAction]设置。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-164">The icon that appears in the toolbar is set using `default_icon` inside of the [browser_action][MDNManifestjsonBrowserAction] key, which you already added to your manifest file in an earlier section.</span></span>  

<span data-ttu-id="2a6c7-165">该 `icons` 键定义应在扩展设置菜单中使用哪些图标。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-165">The `icons` key defines which icons should be used in the Extensions settings menus.</span></span>  <span data-ttu-id="2a6c7-166">下面，你将指定多个大小不同的图标，以考虑不同的屏幕分辨率。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-166">Below, you are specifying multiple icons with different sizes to account for different screen resolutions.</span></span>  <span data-ttu-id="2a6c7-167">图标的名称，是图标的高度 `25` `48` （以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-167">The name of the icons, `25` and `48` are the heights in pixels of the icons.</span></span>  

<span data-ttu-id="2a6c7-168">在 [manifest.js文件中][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] ，包括一个顶级键 `icons` 。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-168">In the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file, include a top-level key for `icons`.</span></span>  

```json
  "icons": {
    "25": "images/color-changer25.png",
    "48": "images/color-changer48.png"
  }
```  

### <span data-ttu-id="2a6c7-169">清单密钥定义</span><span class="sxs-lookup"><span data-stu-id="2a6c7-169">Manifest Key definitions</span></span>  

| <span data-ttu-id="2a6c7-170">密钥</span><span class="sxs-lookup"><span data-stu-id="2a6c7-170">Key</span></span> | <span data-ttu-id="2a6c7-171">详细信息</span><span class="sxs-lookup"><span data-stu-id="2a6c7-171">Details</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="2a6c7-172">图标</span><span class="sxs-lookup"><span data-stu-id="2a6c7-172">icons</span></span>][MDNManifestjsonIcons] | <span data-ttu-id="2a6c7-173">扩展的图标，其键值对表示图像大小，图像路径与扩展的根目录 `px` 相对。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-173">The icons for your extension with key-value pairs of image size in `px` and image path relative to the root directory of the extension.</span></span> |  

> [!NOTE]
> <span data-ttu-id="2a6c7-174">使用本指南稍后 `inactive##.png` 在 images 文件夹中命名的图标。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-174">Use the icons named `inactive##.png` located in the images folder later in this guide.</span></span>  

## <span data-ttu-id="2a6c7-175">测试扩展</span><span class="sxs-lookup"><span data-stu-id="2a6c7-175">Testing the extension</span></span>  

<span data-ttu-id="2a6c7-176">现在，你已添加用户界面并创建了图标，请测试扩展。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-176">Now that you have added the user interface and created icons, test your extension.</span></span>  <span data-ttu-id="2a6c7-177">演练向 Microsoft [][ExtensionsGuidesAddingRemovingExtensionsAdding] Edge 添加扩展的步骤。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-177">Walk through the steps for [Adding an extension][ExtensionsGuidesAddingRemovingExtensionsAdding] to Microsoft Edge.</span></span>  <span data-ttu-id="2a6c7-178">之后，返回到本指南。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-178">Afterwards, return to this guide.</span></span>  

<span data-ttu-id="2a6c7-179">添加扩展后，导航 [到任何docs.microsoft.com][MicrosoftDocs] 页面。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-179">After you add your extension, navigate to any [docs.microsoft.com][MicrosoftDocs] page.</span></span>  <span data-ttu-id="2a6c7-180">单击浏览器操作后，应该会看到以下弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-180">You should see the following pop-up after clicking on the browser action.</span></span>  <span data-ttu-id="2a6c7-181">正文的颜色 [docs.microsoft.com][MicrosoftDocs] 更改颜色。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-181">The color of the [docs.microsoft.com][MicrosoftDocs] body should also change color.</span></span>  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_aliceblue.png" alt-text="Docs.microsoft.com头更改为 Aliceblue":::
         <span data-ttu-id="2a6c7-183">Docs.microsoft.com头更改为 Aliceblue</span><span class="sxs-lookup"><span data-stu-id="2a6c7-183">Docs.microsoft.com header changed to Aliceblue</span></span> :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Aliceblue][ImageColorChangerHeaderAliceblue]  -->
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_cornsilk.png" alt-text="Docs.microsoft.com头更改为"一角"":::
         <span data-ttu-id="2a6c7-185">Docs.microsoft.com头更改为"一角"</span><span class="sxs-lookup"><span data-stu-id="2a6c7-185">Docs.microsoft.com header changed to Cornsilk</span></span> :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Cornsilk][ImageColorChangerHeaderCornsilk]  -->
   :::column-end:::
:::row-end:::

<span data-ttu-id="2a6c7-186">如果遇到任何无法运行的错误或功能，请参阅调试扩展指南或下载[][ExtensionsGuidesDebuggingExtensions] [GitHub 上的完整示例][GithubMicrosoftEdgeExtensionsDemosColorChanger]。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-186">If you encounter any errors or functionality that does not work, see the [Debugging extensions][ExtensionsGuidesDebuggingExtensions] guide or download the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span></span>  

## <span data-ttu-id="2a6c7-187">添加内容和后台脚本</span><span class="sxs-lookup"><span data-stu-id="2a6c7-187">Adding content and background scripts</span></span>  

<span data-ttu-id="2a6c7-188">进一步执行一步并添加逻辑以禁止扩展在域外部[docs.microsoft.com运行。][MicrosoftDocs]</span><span class="sxs-lookup"><span data-stu-id="2a6c7-188">Go one step further and add logic to disable the extension from working on pages outside the [docs.microsoft.com][MicrosoftDocs] domain.</span></span>  

<span data-ttu-id="2a6c7-189">您必须先创建内容 [脚本][MDNContentScripts]。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-189">You must first create a [content script][MDNContentScripts].</span></span>  <span data-ttu-id="2a6c7-190">接下来，您必须创建在特定网页上下文中运行的内容脚本，能够访问网页的内容，并且能够与后台脚本进行通信。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-190">Next, you must create content scripts that run in the context of a particular web page, are able to access the content of a web page, and are able to communicate with background scripts.</span></span>  <span data-ttu-id="2a6c7-191">在目录 `js` 内，创建一个名为 `content.js` 并添加以下代码的文件。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-191">Inside of your `js` directory, create a file named `content.js` and add the following code.</span></span>  

```javascript
// get the URL of the page
var url = document.location.href;

// if not on a docs.microsoft.com domain
if (url.indexOf("//docs.microsoft.com") === -1) {
    // send inactive icons
    browser.runtime.sendMessage({
        "iconPath20": "images/inactive20.png",
        "iconPath40": "images/inactive40.png"
    });
}
```  

<span data-ttu-id="2a6c7-192">此脚本通过此脚本获取当前页面的 URL，并验证当前 `document.location.href` 页面是否位于docs.microsoft.com域中[][MicrosoftDocs]。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-192">This script gets the URL of the current page through `document.location.href` and verifies whether the current page is on the [docs.microsoft.com][MicrosoftDocs] domain.</span></span>  <span data-ttu-id="2a6c7-193">如果页面不在 [docs.microsoft.com][MicrosoftDocs] 域 \ (例如 \) 上，则非活动图标 \ (灰显图标\) 的路径使用  [https://www.bing.com/][|::ref1::|] [runtime.sendMessage () 发送到后台脚本 ][MDNApiRuntimeSendmessage]。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-193">If the page is not on the [docs.microsoft.com][MicrosoftDocs] domain \(for example  [https://www.bing.com/][|::ref1::|]\), the paths to the inactive icons \(grayed out icons\) are sent to the background script using [runtime.sendMessage()][MDNApiRuntimeSendmessage].</span></span>  

<span data-ttu-id="2a6c7-194">您必须更新manifest.js[ 文件][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] 上的文件，以包含以下 `content_scripts` 键。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-194">You must update the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file to include the following `content_scripts` key.</span></span>  

```json
  "content_scripts": [{
    "matches": [
        "<all_urls>"
    ],
    "js": ["js/content.js"],
    "run_at": "document_end"
}]
```  

### <span data-ttu-id="2a6c7-195">清单密钥定义</span><span class="sxs-lookup"><span data-stu-id="2a6c7-195">Manifest Key definitions</span></span>  

| <span data-ttu-id="2a6c7-196">密钥</span><span class="sxs-lookup"><span data-stu-id="2a6c7-196">Key</span></span> | <span data-ttu-id="2a6c7-197">详细信息</span><span class="sxs-lookup"><span data-stu-id="2a6c7-197">Details</span></span> |  
|:--- |:---- |  
| [<span data-ttu-id="2a6c7-198">content_scripts</span><span class="sxs-lookup"><span data-stu-id="2a6c7-198">content_scripts</span></span>][MDNManifestjsonContentScripts] | <span data-ttu-id="2a6c7-199">包含浏览器应加载哪些内容脚本的信息。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-199">Contains the information about which content scripts the browser should load.</span></span> |  

#### <span data-ttu-id="2a6c7-200">content_scripts关键定义</span><span class="sxs-lookup"><span data-stu-id="2a6c7-200">content_scripts Key definitions</span></span>  

| <span data-ttu-id="2a6c7-201">密钥</span><span class="sxs-lookup"><span data-stu-id="2a6c7-201">Key</span></span> | <span data-ttu-id="2a6c7-202">详细信息</span><span class="sxs-lookup"><span data-stu-id="2a6c7-202">Details</span></span> |  
|:--- |:---- |  
| `matches` <span data-ttu-id="2a6c7-203">\ (required\) </span><span class="sxs-lookup"><span data-stu-id="2a6c7-203">\(required\)</span></span> | <span data-ttu-id="2a6c7-204">加载内容脚本之前要匹配的 URL 模式。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-204">The URL pattern to match prior to loading the content script.</span></span> |  
| `js` | <span data-ttu-id="2a6c7-205">应在匹配的 URL 上加载的脚本。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-205">The script that should be loaded on matching URLs.</span></span> |  
| `run_at` | <span data-ttu-id="2a6c7-206">指定注入密钥中的 JavaScript `js` 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-206">Specifies where the JavaScript files from the `js` key are injected.</span></span> |  

<span data-ttu-id="2a6c7-207">接下来，你必须创建一 [个后台脚本][MDNAnatomyExtensionBackgroundScripts]。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-207">Next, you must create a [background script][MDNAnatomyExtensionBackgroundScripts].</span></span>  <span data-ttu-id="2a6c7-208">后台脚本在浏览器后台运行，独立于网页或浏览器窗口的生命周期运行，并且能够与内容脚本通信。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-208">Background scripts run in the background of the browser, run independently of the lifetime of a web page or browser window, and are able to communicate with content scripts.</span></span>  

<span data-ttu-id="2a6c7-209">在文件夹 `js` 内，创建一个名为 `background.js` 并添加以下代码的文件。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-209">Inside of your `js` folder, create a file named `background.js` and add the following code.</span></span>  

```javascript
// listen for sendMessage() from content script
browser.runtime.onMessage.addListener(
    function (request, sender, sendResponse) {
        // set the icon for the browser action from sendMessage() in content script
        browser.browserAction.setIcon({
            path: {
                "20": request.iconPath20,
                "40": request.iconPath40
            },
            tabId: sender.tab.id
        });
        // disable browser action for the current tab
        browser.browserAction.disable(sender.tab.id);
    });
```  

<span data-ttu-id="2a6c7-210">[runtime.onMessage][MDNApiRuntimeOnmessage]方法侦听内容脚本中的[runtime.sendMessage () 。][MDNApiRuntimeSendmessage]</span><span class="sxs-lookup"><span data-stu-id="2a6c7-210">The [runtime.onMessage][MDNApiRuntimeOnmessage] method listens for [runtime.sendMessage()][MDNApiRuntimeSendmessage] from the content script.</span></span>  <span data-ttu-id="2a6c7-211">如果页面的域未[docs.microsoft.com，][MicrosoftDocs][则 browserAction.setIcon () ][MDNApiBrowseractionSeticon]方法将图标路径设置为非活动图像。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-211">If the domain of the page is not [docs.microsoft.com][MicrosoftDocs], then [browserAction.setIcon()][MDNApiBrowseractionSeticon] method sets the icon paths to the inactive images.</span></span>  

<span data-ttu-id="2a6c7-212">该脚本还禁用浏览器操作 \ ([browserAction.disable][MDApiBrowseractionDisable]\) ，以便用户无法单击 docs.microsoft.com 页面之外的 [浏览器][MicrosoftDocs] 操作。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-212">The script also disables the browser action \([browserAction.disable][MDApiBrowseractionDisable]\), so that users are not able to click on the browser action outside of a [docs.microsoft.com][MicrosoftDocs] page.</span></span>  

<span data-ttu-id="2a6c7-213">必须将后台脚本添加到文件上的 [manifest.js脚本][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] 。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-213">You must add the background script to the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file.</span></span>  <span data-ttu-id="2a6c7-214">将以下 `background` 项添加到清单。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-214">Add the following `background` key to your manifest.</span></span>  

```json
"background": {
    "scripts": ["js/background.js"],
    "persistent": true
  }
```  

### <span data-ttu-id="2a6c7-215">清单密钥定义</span><span class="sxs-lookup"><span data-stu-id="2a6c7-215">Manifest Key definitions</span></span>  

| <span data-ttu-id="2a6c7-216">密钥</span><span class="sxs-lookup"><span data-stu-id="2a6c7-216">Key</span></span> | <span data-ttu-id="2a6c7-217">详细信息</span><span class="sxs-lookup"><span data-stu-id="2a6c7-217">Details</span></span>|  
|:--- |:--- |  
| [<span data-ttu-id="2a6c7-218">背景</span><span class="sxs-lookup"><span data-stu-id="2a6c7-218">background</span></span>][MDNManifestjsonBackground] | <span data-ttu-id="2a6c7-219">包含后台脚本。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-219">Contains the background scripts.</span></span> |  

#### <span data-ttu-id="2a6c7-220">后台键定义</span><span class="sxs-lookup"><span data-stu-id="2a6c7-220">background Key definitions</span></span>  

| <span data-ttu-id="2a6c7-221">密钥</span><span class="sxs-lookup"><span data-stu-id="2a6c7-221">Key</span></span> | <span data-ttu-id="2a6c7-222">详细信息</span><span class="sxs-lookup"><span data-stu-id="2a6c7-222">Details</span></span> |  
|:--- |:--- |  
| `scripts` | <span data-ttu-id="2a6c7-223">JavaScript 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-223">The path to a JavaScript file.</span></span> |  
| `persistent` <span data-ttu-id="2a6c7-224">（必需）</span><span class="sxs-lookup"><span data-stu-id="2a6c7-224">(required)</span></span> | <span data-ttu-id="2a6c7-225">这必须设置为或 `true` `false` 。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-225">This must be set to `true` or `false`.</span></span>  <span data-ttu-id="2a6c7-226">如果设置为 `true` ，则加载后台脚本并保留整个浏览部分。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-226">If set to `true`, the background script is loaded and persists for the entire browsing section.</span></span>  <span data-ttu-id="2a6c7-227">如果设置为 `false` ，后台脚本加载延迟，并保留浏览会话。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-227">If set to `false`, the background script is loaded with a delay and persists for the browsing session.</span></span> |  

<span data-ttu-id="2a6c7-228">重新加载扩展并再次测试。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-228">Reload your extension and test again.</span></span>  <span data-ttu-id="2a6c7-229">若要重新加载扩展：在 Microsoft Edge 中单击 **...** 设置等，\*\*\*\* 单击"扩展 **"，单击**扩展 \ ("颜色更改器"\) ，然后单击"重新加载**扩展"。**</span><span class="sxs-lookup"><span data-stu-id="2a6c7-229">To reload your extension: click the **...** for settings and more in Microsoft Edge, click **Extensions**, click on your extension \(**Color Changer**\), and click **Reload extension**.</span></span>  

<span data-ttu-id="2a6c7-230">现在，打开一个新选项卡，或刷新一个不是当前页面docs.microsoft.com[选项卡。][MicrosoftDocs]</span><span class="sxs-lookup"><span data-stu-id="2a6c7-230">Now, open a new tab or refresh an existing tab that is not a [docs.microsoft.com][MicrosoftDocs] page.</span></span>  <span data-ttu-id="2a6c7-231">你应该会看到非活动图标，并且无法单击浏览器操作。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-231">You should see the inactive icon and not be able to click on the browser action.</span></span>  

<span data-ttu-id="2a6c7-232">恭喜你！</span><span class="sxs-lookup"><span data-stu-id="2a6c7-232">Congratulations!</span></span>  <span data-ttu-id="2a6c7-233">你为 Microsoft Edge 创建了扩展！</span><span class="sxs-lookup"><span data-stu-id="2a6c7-233">You created an extension for Microsoft Edge!</span></span>  <span data-ttu-id="2a6c7-234">在 [GitHub 上查看完整示例][GithubMicrosoftEdgeExtensionsDemosColorChanger]。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-234">View the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span></span>  <span data-ttu-id="2a6c7-235">继续阅读，详细了解扩展。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-235">Continue reading to learn more about extensions.</span></span>  

## <span data-ttu-id="2a6c7-236">编写更复杂的扩展</span><span class="sxs-lookup"><span data-stu-id="2a6c7-236">Writing a more complex extension</span></span>  

<span data-ttu-id="2a6c7-237">想要编写更复杂的扩展？</span><span class="sxs-lookup"><span data-stu-id="2a6c7-237">Want to write a more complex extension?</span></span>  <span data-ttu-id="2a6c7-238">请看一下 MDN 上的Ifyify 扩展，第二个 [扩展][MDNYourSecondWebextension]。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-238">Take a look at the Beastify extension on MDN in the article, [Your second extension][MDNYourSecondWebextension].</span></span>  <span data-ttu-id="2a6c7-239">Microsoft Edge 的扩展模型与 Firefox 的扩展模型略有不同，在"第二个扩展[][MDNYourSecondWebextension]"中创建的Ifyify 扩展已调整为在 Microsoft Edge 中运行。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-239">The extension model for Microsoft Edge differs slightly from the extension model for Firefox, the Beastify extension created in [Your second extension][MDNYourSecondWebextension] was adapted to function in Microsoft Edge.</span></span>  <span data-ttu-id="2a6c7-240">在 [GitHub][GithubMicrosoftEdgeExtensionsDemosBeastify]上查看。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-240">Check it out on [GitHub][GithubMicrosoftEdgeExtensionsDemosBeastify].</span></span>  

<span data-ttu-id="2a6c7-241">在阅读 MDN（ [你的][MDNYourSecondWebextension]第二个扩展）上的文章时，请记住以下部分。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-241">While walking through the article on MDN, [Your second extension][MDNYourSecondWebextension], keep in mind the following sections.</span></span>  

### <span data-ttu-id="2a6c7-242">API</span><span class="sxs-lookup"><span data-stu-id="2a6c7-242">APIs</span></span>  

<span data-ttu-id="2a6c7-243">有关 Microsoft Edge [中受支持的][ExtensionsAPIsupportApis] 扩展 API 的列表，请参阅"受支持的 API"页。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-243">See the [Supported APIs][ExtensionsAPIsupportApis] page for a list of supported extensions APIs in Microsoft Edge.</span></span>  

### <span data-ttu-id="2a6c7-244">图标大小</span><span class="sxs-lookup"><span data-stu-id="2a6c7-244">Icon sizes</span></span>  

<span data-ttu-id="2a6c7-245">Microsoft Edge 的首选扩展图标大小是 `20px` ， `25px` 和 `30px` `40px` 。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-245">Preferred extension icon sizes for Microsoft Edge are `20px`, `25px`, `30px`, and `40px`.</span></span>  <span data-ttu-id="2a6c7-246">其他支持的大小是 `19px` ， `35px` 和 `38px` 。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-246">Other supported sizes are `19px`, `35px`, and `38px`.</span></span>  <span data-ttu-id="2a6c7-247">有关图标大小和最佳做法详细信息， [请参阅设计指南][ExtensionsGuidesDesign] 。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-247">For more info on icon sizes and best practices, see the [Design][ExtensionsGuidesDesign] guide.</span></span>  

### <span data-ttu-id="2a6c7-248">JavaScript</span><span class="sxs-lookup"><span data-stu-id="2a6c7-248">JavaScript</span></span>  

<span data-ttu-id="2a6c7-249">Microsoft Edge 的扩展模型不支持 JavaScript 承诺。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-249">The extension model for Microsoft Edge does not support JavaScript Promises.</span></span>  <span data-ttu-id="2a6c7-250">请改为使用回调。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-250">Instead, use callbacks.</span></span>  <span data-ttu-id="2a6c7-251">有关在扩展中使用回调的更多示例，请看一下  [快速打印][GithubMicrosoftEdgeExtensionsDemosQuickPrint] 和 [文本交换][GithubMicrosoftEdgeExtensionsDemosTextSwap] 演示。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-251">For more examples of using callbacks in an extension, take a look at the  [Quick Print][GithubMicrosoftEdgeExtensionsDemosQuickPrint] and [Text Swap][GithubMicrosoftEdgeExtensionsDemosTextSwap] demos.</span></span>  

<span data-ttu-id="2a6c7-252">演练以下 [视频中的"快速][GithubMicrosoftEdgeExtensionsDemosQuickPrint] 打印"示例。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-252">Walk through the [Quick Print][GithubMicrosoftEdgeExtensionsDemosQuickPrint] example in the following video.</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Adding-a-Background-Script-to-you-Edge-Extension/player]  

### <span data-ttu-id="2a6c7-253">Manifest.js打开</span><span class="sxs-lookup"><span data-stu-id="2a6c7-253">Manifest.json</span></span>  

*   <span data-ttu-id="2a6c7-254">该 `author` 密钥在 Microsoft Edge 中是必需的</span><span class="sxs-lookup"><span data-stu-id="2a6c7-254">The `author` key is required in Microsoft Edge</span></span>  
*   <span data-ttu-id="2a6c7-255">`activeTab`Microsoft Edge 不支持该密钥</span><span class="sxs-lookup"><span data-stu-id="2a6c7-255">The `activeTab` key is not supported in Microsoft Edge</span></span>  

<span data-ttu-id="2a6c7-256">有关浏览器扩展 [的信息，请参阅][MDNBrowserExtensions] [MDN Web 文档][MDNWebDocs]。</span><span class="sxs-lookup"><span data-stu-id="2a6c7-256">For more information on [Browser Extensions][MDNBrowserExtensions], see [MDN web docs][MDNWebDocs].</span></span>  

<!-- image links -->  

<!--[ImageColorChangerHeader]: ../media/color-changer_header.png "Docs.microsoft.com body changed to blue"  -->  
<!--[ImageColorChangerPopup]: ../media/color-changer_popup.png "The pop-up interface of the extension"  -->  
<!--[ImageColorChangerHeaderAliceblue]: ../media/color-changer_header_aliceblue.png "[Docs.microsoft.com header changed to Aliceblue"  -->  
<!--[ImageColorChangerHeaderCornsilk]: ../media/color-changer_header_cornsilk.png "Docs.microsoft.com header changed to Cornsilk"  -->  

<!-- links -->  

[ExtensionsGuidesAddingRemovingExtensionsAdding]: ./adding-and-removing-extensions.md#adding-an-extension "添加扩展 - 为 Microsoft Edge 添加、移动和删除扩展 |Microsoft Docs"  
[ExtensionsGuidesDebuggingExtensions]: ./debugging-extensions.md "调试扩展 |Microsoft Docs"  
[ExtensionsGuidesDesign]: ./design.md "Microsoft Edge 扩展的设计指南 |Microsoft Docs"  
[ExtensionsGuidesDesignIcons]: ./design.md#icons "图标 - Microsoft Edge 扩展的设计指南 |Microsoft Docs"  
[ExtensionsAPIsupportApis]: ../api-support/supported-apis.md " 受支持的 API |Microsoft Docs"  
[ExtensionsApisupportManifestKeys]: ../api-support/supported-manifest-keys.md "支持的清单密钥 |Microsoft Docs"  

[MicrosoftDocs]: https://docs.microsoft.com "Microsoft Docs"  

[MDNWebDocs]: https://developer.mozilla.org "MDN Web 文档"  
[MDNBrowserExtensions]: https://developer.mozilla.org/Add-ons/WebExtensions "浏览器扩展 |MDN"  
[MDNAnatomyExtension]: https://developer.mozilla.org/Add-ons/WebExtensions/Anatomy_of_a_WebExtension "扩展结构 |MDN"  
[MDNAnatomyExtensionBackgroundScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Anatomy_of_a_WebExtension#Background_scripts "后台脚本 - 扩展结构 |MDN"  
[MDApiBrowseractionDisable]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/disable "browserAction.disable () - API |MDN" 
[MDNApiBrowseractionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setIcon "browserAction.setIcon () - API |MDN"  
[MDNApiRuntimeOnmessage]: https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/onmessage "runtime.onMessage - API |MDN"  
[MDNApiRuntimeSendmessage]: https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendMessage "runtime.sendMessage () - API |MDN"  
[MDNApiTabs]: https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs "选项卡 - API |MDN"  
[MDNApiTabsInsertcss]: https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs/insertCSS "tabs.insertCSS () - API |MDN"  
[MDNContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Content_scripts "内容脚本 |MDN"  
[MDNManifestjsonAuthor]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/author "author - manifest.json |MDN"  
[MDNManifestjsonBackground]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/background "background - manifest.json |MDN"  
[MDNManifestjsonBrowserAction]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/browser_action "browser_action - manifest.js|MDN"  
[MDNManifestjsonContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/content_scripts "content_scripts - manifest.js|MDN"  
[MDNManifestjsonDescription]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/description "description - manifest.json |MDN"  
[MDNManifestjsonIcons]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/icons "图标 - manifest.js|MDN"  
[MDNManifestjsonName]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/name "name - manifest.json |MDN"  
[MDNManifestjsonPermissions]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/permissions "permissions - manifest.json |MDN"  
[MDNManifestjsonVersion]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/version "version - manifest.json |MDN"  
[MDNYourSecondWebextension]: https://developer.mozilla.org/Add-ons/WebExtensions/Your_second_WebExtension "第二个扩展 |MDN"  

[Bing]: https://www.bing.com "必应"  

[GithubMicrosoftEdgeExtensionsDemosBeastify]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/beastify_edge "Ifyify - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChanger]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/color_changer "颜色更改器 - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChangerImages]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/color_changer/images "Images - 颜色更改器 - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/color_changer/manifest.json "Manifest.js- 颜色更改器 - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosQuickPrint]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/quick_print "快速打印 - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosTextSwap]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/text_swap "文本交换 - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
