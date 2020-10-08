---
description: 了解如何创建 Microsoft Edge 扩展
title: 创建扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.custom: seodec18
ms.openlocfilehash: a08fc6bd604ce810895e7103f7f6384dbedc9f78
ms.sourcegitcommit: 0bc1312a1e6a0ac37cf385201db4361fc05184fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2020
ms.locfileid: "10683649"
---
# <span data-ttu-id="14a41-104">创建 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="14a41-104">Creating A Microsoft Edge Extension</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="14a41-105">在本指南中，了解如何创建 Microsoft Edge 的扩展。</span><span class="sxs-lookup"><span data-stu-id="14a41-105">In this guide, learn to create an extension for Microsoft Edge.</span></span>  <span data-ttu-id="14a41-106">此示例扩展使你可以操作 [docs.microsoft.com][MicrosoftDocs] 页面的特定 CSS，包括创建清单文件、用户界面以及后台和内容脚本。</span><span class="sxs-lookup"><span data-stu-id="14a41-106">This example extension allows you to manipulate specific CSS for [docs.microsoft.com][MicrosoftDocs] pages including walking you through creation of a manifest file, the user interface, and background and content scripts.</span></span>  

:::image type="complex" source="../media/color-changer_header.png" alt-text="Docs.microsoft.com 正文已更改为蓝色":::
   <span data-ttu-id="14a41-108">Docs.microsoft.com 正文已更改为蓝色</span><span class="sxs-lookup"><span data-stu-id="14a41-108">Docs.microsoft.com body changed to blue</span></span>
:::image-end:::

<!--![Docs.microsoft.com body changed to blue][ImageColorChangerHeader]  -->  

<span data-ttu-id="14a41-109">本教程假定你对浏览器扩展的定义和工作原理有基本的理解。</span><span class="sxs-lookup"><span data-stu-id="14a41-109">This tutorial assumes you have basic understanding of what a browser extension is and how it work.</span></span>  <span data-ttu-id="14a41-110">有关扩展的构建基块的详细 imformation，请参阅 [扩展的剖析][MDNAnatomyExtension]。</span><span class="sxs-lookup"><span data-stu-id="14a41-110">For more imformation about the building blocks for extensions, see [Anatomy of an extension][MDNAnatomyExtension].</span></span>  

<span data-ttu-id="14a41-111">下载 [GitHub 上的完整示例][GithubMicrosoftEdgeExtensionsDemosColorChanger]的代码。</span><span class="sxs-lookup"><span data-stu-id="14a41-111">Download the code for the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span></span>  

## <span data-ttu-id="14a41-112">生成清单文件</span><span class="sxs-lookup"><span data-stu-id="14a41-112">Building the manifest file</span></span>  

<span data-ttu-id="14a41-113">首先，为您的扩展名创建一个目录并为其命名 `color-changer` 。</span><span class="sxs-lookup"><span data-stu-id="14a41-113">To begin, create a directory for your extension and name it `color-changer`.</span></span>  

<span data-ttu-id="14a41-114">在 `color-changer` 文件夹内创建一个名为 `manifest.json` 的文件。</span><span class="sxs-lookup"><span data-stu-id="14a41-114">Inside the `color-changer` folder, create a file named `manifest.json`.</span></span>  <span data-ttu-id="14a41-115">`manifest.json`文件对所有扩展名都是必需的，并提供扩展的重要信息，范围从扩展名称到权限。</span><span class="sxs-lookup"><span data-stu-id="14a41-115">The `manifest.json` file is required for all extensions and provides important information for the extension, ranging from the extension name to the permissions.</span></span>  

> [!NOTE] 
> <span data-ttu-id="14a41-116">本指南将引导你完成必须在本指南中使用的所有清单键，但要查看所有受支持和推荐的清单键的列表，请参阅 [支持的清单键][ExtensionsApisupportManifestKeys]。</span><span class="sxs-lookup"><span data-stu-id="14a41-116">This guide walks you through all the manifest keys you must use in this guide, but for a list of all supported and recommended manifest keys, see [Supported manifest keys][ExtensionsApisupportManifestKeys].</span></span>  

<span data-ttu-id="14a41-117">在 `manifest.json` "内部" 中，添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="14a41-117">Inside `manifest.json`, add the following code.</span></span>  

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

### <span data-ttu-id="14a41-118">清单键定义</span><span class="sxs-lookup"><span data-stu-id="14a41-118">Manifest key definitions</span></span>  

| <span data-ttu-id="14a41-119">密钥</span><span class="sxs-lookup"><span data-stu-id="14a41-119">Key</span></span> | <span data-ttu-id="14a41-120">详细信息</span><span class="sxs-lookup"><span data-stu-id="14a41-120">Details</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="14a41-121">name</span><span class="sxs-lookup"><span data-stu-id="14a41-121">name</span></span>][MDNManifestjsonName] | <span data-ttu-id="14a41-122">扩展的名称。</span><span class="sxs-lookup"><span data-stu-id="14a41-122">The name of the extension.</span></span>  |  
| [<span data-ttu-id="14a41-123">授权</span><span class="sxs-lookup"><span data-stu-id="14a41-123">author</span></span>][MDNManifestjsonAuthor] | <span data-ttu-id="14a41-124">扩展的作者。</span><span class="sxs-lookup"><span data-stu-id="14a41-124">The author of the extension.</span></span>  |  
| [<span data-ttu-id="14a41-125">version</span><span class="sxs-lookup"><span data-stu-id="14a41-125">version</span></span>][MDNManifestjsonVersion] | <span data-ttu-id="14a41-126">分机版本号。</span><span class="sxs-lookup"><span data-stu-id="14a41-126">The extension version number.</span></span>  |  
| [<span data-ttu-id="14a41-127">description</span><span class="sxs-lookup"><span data-stu-id="14a41-127">description</span></span>][MDNManifestjsonDescription] | <span data-ttu-id="14a41-128">Microsoft Edge 中 "扩展" 菜单的 "关于" 部分中显示的扩展的说明。</span><span class="sxs-lookup"><span data-stu-id="14a41-128">The description of the extension displayed in the About section of the extension menu in Microsoft Edge.</span></span>  |  
| [<span data-ttu-id="14a41-129">授权</span><span class="sxs-lookup"><span data-stu-id="14a41-129">permissions</span></span>][MDNManifestjsonPermissions] | <span data-ttu-id="14a41-130">请求扩展的权限的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="14a41-130">An array of strings requesting permissions for the extension.</span></span>  <span data-ttu-id="14a41-131">对于您的扩展，您正在请求查看访问过的网站 ( "选项卡" \ ) 并更新与 "" 匹配的 Url 上的内容 `*://docs.microsoft.com/*` 。</span><span class="sxs-lookup"><span data-stu-id="14a41-131">For your extension, you are requesting permissions to see the websites visited \("tabs"\) and to update content on URLs matching "`*://docs.microsoft.com/*`".</span></span>  |  
| [<span data-ttu-id="14a41-132">browser_action</span><span class="sxs-lookup"><span data-stu-id="14a41-132">browser_action</span></span>][MDNManifestjsonBrowserAction] | <span data-ttu-id="14a41-133">包含图标的信息。</span><span class="sxs-lookup"><span data-stu-id="14a41-133">Contains the information for an icon.</span></span> <span data-ttu-id="14a41-134">图标位于 "Microsoft Edge" 工具栏上的 "地址" 栏右侧。</span><span class="sxs-lookup"><span data-stu-id="14a41-134">The icon is placed on the Microsoft Edge toolbar, to the right of the address bar.</span></span>  |  

#### <span data-ttu-id="14a41-135">browser_action 键定义</span><span class="sxs-lookup"><span data-stu-id="14a41-135">browser_action Key definitions</span></span>  

| <span data-ttu-id="14a41-136">密钥</span><span class="sxs-lookup"><span data-stu-id="14a41-136">Key</span></span> | <span data-ttu-id="14a41-137">详细信息</span><span class="sxs-lookup"><span data-stu-id="14a41-137">Details</span></span> |  
|:--- |:--- |  
| `default_icon` | <span data-ttu-id="14a41-138">工具栏中使用的图标。</span><span class="sxs-lookup"><span data-stu-id="14a41-138">The icon that is used in the toolbar.</span></span>  |  
| `default_title` | <span data-ttu-id="14a41-139">当用户将鼠标悬停在工具栏中的图标上时显示的文本。</span><span class="sxs-lookup"><span data-stu-id="14a41-139">The text that is displayed when a user hovers over the icon in the toolbar.</span></span>  |  
| `default_popup` | <span data-ttu-id="14a41-140">弹出窗口的 HTML 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="14a41-140">The path to the HTML file for the pop-up window.</span></span>  |  

<span data-ttu-id="14a41-141">现在，你已创建清单文件，你需要一个用于扩展的用户界面。</span><span class="sxs-lookup"><span data-stu-id="14a41-141">Now that you have created the manifest file, you need a user interface for the extension.</span></span>  

## <span data-ttu-id="14a41-142">创建弹出窗口</span><span class="sxs-lookup"><span data-stu-id="14a41-142">Creating the pop-up</span></span>  

<span data-ttu-id="14a41-143">对于您的扩展，请为用户界面创建一个弹出窗口，如下所示。</span><span class="sxs-lookup"><span data-stu-id="14a41-143">For your extension, create a pop-up for the user interface, like below.</span></span>  

:::image type="complex" source="../media/color-changer_popup.png" alt-text="Docs.microsoft.com 正文已更改为蓝色":::
   <span data-ttu-id="14a41-145">扩展的弹出界面</span><span class="sxs-lookup"><span data-stu-id="14a41-145">The pop-up interface of the extension</span></span>
:::image-end:::

<!--![The pop-up interface of the extension][ImageColorChangerPopup]  -->  

<span data-ttu-id="14a41-146">`popup.html`在文件夹的根目录中创建一个名为的文件 `color-changer` 。</span><span class="sxs-lookup"><span data-stu-id="14a41-146">Create a file named `popup.html` in the root of your `color-changer` folder.</span></span>  <span data-ttu-id="14a41-147">将以下代码粘贴到中 `popup.html` 。</span><span class="sxs-lookup"><span data-stu-id="14a41-147">Paste the following code into `popup.html`.</span></span>  

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

<span data-ttu-id="14a41-148">在中 `popup.html` ，你可以创建标题、段落和三个按钮 \ (Aliceblue、Cornsilk 和 Reset \ ) 。</span><span class="sxs-lookup"><span data-stu-id="14a41-148">In `popup.html`, you create a title, a paragraph, and three buttons \(Aliceblue, Cornsilk, and Reset\).</span></span>  

<span data-ttu-id="14a41-149">现在创建一个名为 `css` 和内部的文件夹，创建一个名为 `styles.css` 的文件。</span><span class="sxs-lookup"><span data-stu-id="14a41-149">Now create a folder named `css` and inside create a file named `styles.css`.</span></span>  <span data-ttu-id="14a41-150">在下方添加样式。</span><span class="sxs-lookup"><span data-stu-id="14a41-150">Add the styles below.</span></span>  

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

<span data-ttu-id="14a41-151">此 CSS 为我们的扩展提供了一些基本样式。</span><span class="sxs-lookup"><span data-stu-id="14a41-151">This CSS gives our extension some basic styles.</span></span>  <span data-ttu-id="14a41-152">可随意添加更多样式以自定义您的扩展。</span><span class="sxs-lookup"><span data-stu-id="14a41-152">Feel free to add more styles to customize your extension.</span></span>  

<span data-ttu-id="14a41-153">接下来，你必须创建与弹出窗口交互的 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="14a41-153">Next, you must create the JavaScript file that interacts with the pop-up.</span></span>  <span data-ttu-id="14a41-154">创建一个 `js` 文件夹和一个名为 "内部" 的文件 `popup.js` 。</span><span class="sxs-lookup"><span data-stu-id="14a41-154">Create a `js` folder and a file named `popup.js` inside.</span></span>  <span data-ttu-id="14a41-155">`popup.js`具有以下代码的更新。</span><span class="sxs-lookup"><span data-stu-id="14a41-155">Update `popup.js` with the following code.</span></span>  

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

<span data-ttu-id="14a41-156">在中 `popup.js` ， [选项卡][MDNApiTabs] API 允许你与浏览器的选项卡交互，并将脚本和样式插入页面内容。</span><span class="sxs-lookup"><span data-stu-id="14a41-156">In `popup.js`, the [tabs][MDNApiTabs] API allows you to interact with the tabs of the browser and inject script and styles into the page content.</span></span>  <span data-ttu-id="14a41-157">使用 [insertCSS ( # B1 ][MDNApiTabsInsertcss] 方法，你可以将指定的 CSS 插入页面，在单击指定的按钮时，该页面会将 [docs.microsoft.com][MicrosoftDocs] 的标题更改为另一种颜色。</span><span class="sxs-lookup"><span data-stu-id="14a41-157">Using the [tabs.insertCSS()][MDNApiTabsInsertcss] method, you inject the specified CSS into the page which changes the header on [docs.microsoft.com][MicrosoftDocs] to a different color when the specified button is clicked.</span></span>  

<span data-ttu-id="14a41-158">既然你已拥有基本的弹出功能，请将图标添加到扩展。</span><span class="sxs-lookup"><span data-stu-id="14a41-158">Now that you have the basic pop-up functionality, add icons to the extension.</span></span>  

## <span data-ttu-id="14a41-159">添加图标</span><span class="sxs-lookup"><span data-stu-id="14a41-159">Adding icons</span></span>  

<span data-ttu-id="14a41-160">图标用于表示浏览器工具栏、"扩展" 菜单和其他位置中的扩展。</span><span class="sxs-lookup"><span data-stu-id="14a41-160">Icons are used to represent the extension in the browser toolbar, the extensions menu, and other places.</span></span>  <span data-ttu-id="14a41-161">下载 [GitHub 上的扩展的图标][GithubMicrosoftEdgeExtensionsDemosColorChangerImages]。</span><span class="sxs-lookup"><span data-stu-id="14a41-161">Download the [icons for your extension on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChangerImages].</span></span> <span data-ttu-id="14a41-162">有关 Microsoft Edge 中的扩展图标的详细信息，请参阅 [设计指南][ExtensionsGuidesDesignIcons]。</span><span class="sxs-lookup"><span data-stu-id="14a41-162">For more information about extension icons in Microsoft Edge, see [Design Guide][ExtensionsGuidesDesignIcons].</span></span>  

<span data-ttu-id="14a41-163">下载扩展图标后，将图标保存在中的某个 `images` 文件夹中 `color-changer` 。</span><span class="sxs-lookup"><span data-stu-id="14a41-163">After you download the extension icons, save the icons in an `images` folder inside `color-changer`.</span></span>  

<span data-ttu-id="14a41-164">工具栏中显示的图标是使用 `default_icon` [browser_action][MDNManifestjsonBrowserAction] 项的内部设置的，你已在前面的部分中添加到清单文件。</span><span class="sxs-lookup"><span data-stu-id="14a41-164">The icon that appears in the toolbar is set using `default_icon` inside of the [browser_action][MDNManifestjsonBrowserAction] key, which you already added to your manifest file in an earlier section.</span></span>  

<span data-ttu-id="14a41-165">`icons`该键定义 "扩展" 设置菜单中应使用的图标。</span><span class="sxs-lookup"><span data-stu-id="14a41-165">The `icons` key defines which icons should be used in the Extensions settings menus.</span></span>  <span data-ttu-id="14a41-166">在以下情况下，你将指定具有不同大小的多个图标以用于不同的屏幕分辨率。</span><span class="sxs-lookup"><span data-stu-id="14a41-166">Below, you are specifying multiple icons with different sizes to account for different screen resolutions.</span></span>  <span data-ttu-id="14a41-167">图标的名称， `25` `48` 是图标的高度（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="14a41-167">The name of the icons, `25` and `48` are the heights in pixels of the icons.</span></span>  

<span data-ttu-id="14a41-168">在 " [manifest.js"][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] 文件中，包括的顶级键 `icons` 。</span><span class="sxs-lookup"><span data-stu-id="14a41-168">In the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file, include a top-level key for `icons`.</span></span>  

```json
  "icons": {
    "25": "images/color-changer25.png",
    "48": "images/color-changer48.png"
  }
```  

### <span data-ttu-id="14a41-169">清单键定义</span><span class="sxs-lookup"><span data-stu-id="14a41-169">Manifest Key definitions</span></span>  

| <span data-ttu-id="14a41-170">密钥</span><span class="sxs-lookup"><span data-stu-id="14a41-170">Key</span></span> | <span data-ttu-id="14a41-171">详细信息</span><span class="sxs-lookup"><span data-stu-id="14a41-171">Details</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="14a41-172">图标</span><span class="sxs-lookup"><span data-stu-id="14a41-172">icons</span></span>][MDNManifestjsonIcons] | <span data-ttu-id="14a41-173">您的扩展的图标，其中包含图像大小的键/值对 `px` 以及相对于扩展根目录的图像路径。</span><span class="sxs-lookup"><span data-stu-id="14a41-173">The icons for your extension with key-value pairs of image size in `px` and image path relative to the root directory of the extension.</span></span> |  

> [!NOTE]
> <span data-ttu-id="14a41-174">使用 `inactive##.png` 本指南后面的 "图像" 文件夹中指定的图标。</span><span class="sxs-lookup"><span data-stu-id="14a41-174">Use the icons named `inactive##.png` located in the images folder later in this guide.</span></span>  

## <span data-ttu-id="14a41-175">测试扩展</span><span class="sxs-lookup"><span data-stu-id="14a41-175">Testing the extension</span></span>  

<span data-ttu-id="14a41-176">现在，你已添加了用户界面并创建了图标，请测试你的扩展。</span><span class="sxs-lookup"><span data-stu-id="14a41-176">Now that you have added the user interface and created icons, test your extension.</span></span>  <span data-ttu-id="14a41-177">演练 [将扩展添加][ExtensionsGuidesAddingRemovingExtensionsAdding] 到 Microsoft Edge 的步骤。</span><span class="sxs-lookup"><span data-stu-id="14a41-177">Walk through the steps for [Adding an extension][ExtensionsGuidesAddingRemovingExtensionsAdding] to Microsoft Edge.</span></span>  <span data-ttu-id="14a41-178">之后，请返回本指南。</span><span class="sxs-lookup"><span data-stu-id="14a41-178">Afterwards, return to this guide.</span></span>  

<span data-ttu-id="14a41-179">添加扩展后，导航到任何 [docs.microsoft.com][MicrosoftDocs] 页面。</span><span class="sxs-lookup"><span data-stu-id="14a41-179">After you add your extension, navigate to any [docs.microsoft.com][MicrosoftDocs] page.</span></span>  <span data-ttu-id="14a41-180">单击浏览器操作后，您应看到以下弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="14a41-180">You should see the following pop-up after clicking on the browser action.</span></span>  <span data-ttu-id="14a41-181">[Docs.microsoft.com][MicrosoftDocs]主体的颜色也应更改颜色。</span><span class="sxs-lookup"><span data-stu-id="14a41-181">The color of the [docs.microsoft.com][MicrosoftDocs] body should also change color.</span></span>  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_aliceblue.png" alt-text="Docs.microsoft.com 正文已更改为蓝色":::
         <span data-ttu-id="14a41-183">Docs.microsoft.com 标头已更改为 Aliceblue</span><span class="sxs-lookup"><span data-stu-id="14a41-183">Docs.microsoft.com header changed to Aliceblue</span></span> :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Aliceblue][ImageColorChangerHeaderAliceblue]  -->
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_cornsilk.png" alt-text="Docs.microsoft.com 正文已更改为蓝色":::
         <span data-ttu-id="14a41-185">Docs.microsoft.com 标头已更改为 Cornsilk</span><span class="sxs-lookup"><span data-stu-id="14a41-185">Docs.microsoft.com header changed to Cornsilk</span></span> :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Cornsilk][ImageColorChangerHeaderCornsilk]  -->
   :::column-end:::
:::row-end:::

<span data-ttu-id="14a41-186">如果遇到不起作用的任何错误或功能，请参阅 [调试扩展][ExtensionsGuidesDebuggingExtensions] 指南或下载 [GitHub 上的完整示例][GithubMicrosoftEdgeExtensionsDemosColorChanger]。</span><span class="sxs-lookup"><span data-stu-id="14a41-186">If you encounter any errors or functionality that does not work, see the [Debugging extensions][ExtensionsGuidesDebuggingExtensions] guide or download the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span></span>  

## <span data-ttu-id="14a41-187">添加内容和后台脚本</span><span class="sxs-lookup"><span data-stu-id="14a41-187">Adding content and background scripts</span></span>  

<span data-ttu-id="14a41-188">进一步转到另一步，添加逻辑以禁止扩展在 [docs.microsoft.com][MicrosoftDocs] 域外部工作的页面。</span><span class="sxs-lookup"><span data-stu-id="14a41-188">Go one step further and add logic to disable the extension from working on pages outside the [docs.microsoft.com][MicrosoftDocs] domain.</span></span>  

<span data-ttu-id="14a41-189">必须先创建 [内容脚本][MDNContentScripts]。</span><span class="sxs-lookup"><span data-stu-id="14a41-189">You must first create a [content script][MDNContentScripts].</span></span>  <span data-ttu-id="14a41-190">接下来，必须创建在特定网页的上下文中运行的内容脚本，才能访问网页的内容，并且能够与后台脚本进行通信。</span><span class="sxs-lookup"><span data-stu-id="14a41-190">Next, you must create content scripts that run in the context of a particular web page, are able to access the content of a web page, and are able to communicate with background scripts.</span></span>  <span data-ttu-id="14a41-191">在目录内 `js` 创建一个名为的文件， `content.js` 并添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="14a41-191">Inside of your `js` directory, create a file named `content.js` and add the following code.</span></span>  

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

<span data-ttu-id="14a41-192">此脚本将获取当前页面的 URL `document.location.href` ，并验证当前页面是否位于 [docs.microsoft.com][MicrosoftDocs] 域中。</span><span class="sxs-lookup"><span data-stu-id="14a41-192">This script gets the URL of the current page through `document.location.href` and verifies whether the current page is on the [docs.microsoft.com][MicrosoftDocs] domain.</span></span>  <span data-ttu-id="14a41-193">如果页面不在 [docs.microsoft.com][MicrosoftDocs] 域 \ ( [https://www.bing.com/][|::ref1::|] （例如 \ ) ）中，非活动图标 \ (灰显图标 \ ) 的路径将通过运行时 sendMessage 发送到后台脚本。 [ ( # B5 ][MDNApiRuntimeSendmessage]。</span><span class="sxs-lookup"><span data-stu-id="14a41-193">If the page is not on the [docs.microsoft.com][MicrosoftDocs] domain \(for example  [https://www.bing.com/][|::ref1::|]\), the paths to the inactive icons \(grayed out icons\) are sent to the background script using [runtime.sendMessage()][MDNApiRuntimeSendmessage].</span></span>  

<span data-ttu-id="14a41-194">必须更新文件 [ 上的manifest.js][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] 以包含以下 `content_scripts` 注册表项。</span><span class="sxs-lookup"><span data-stu-id="14a41-194">You must update the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file to include the following `content_scripts` key.</span></span>  

```json
  "content_scripts": [{
    "matches": [
        "<all_urls>"
    ],
    "js": ["js/content.js"],
    "run_at": "document_end"
}]
```  

### <span data-ttu-id="14a41-195">清单键定义</span><span class="sxs-lookup"><span data-stu-id="14a41-195">Manifest Key definitions</span></span>  

| <span data-ttu-id="14a41-196">密钥</span><span class="sxs-lookup"><span data-stu-id="14a41-196">Key</span></span> | <span data-ttu-id="14a41-197">详细信息</span><span class="sxs-lookup"><span data-stu-id="14a41-197">Details</span></span> |  
|:--- |:---- |  
| [<span data-ttu-id="14a41-198">content_scripts</span><span class="sxs-lookup"><span data-stu-id="14a41-198">content_scripts</span></span>][MDNManifestjsonContentScripts] | <span data-ttu-id="14a41-199">包含有关浏览器应加载哪些内容脚本的信息。</span><span class="sxs-lookup"><span data-stu-id="14a41-199">Contains the information about which content scripts the browser should load.</span></span> |  

#### <span data-ttu-id="14a41-200">content_scripts 键定义</span><span class="sxs-lookup"><span data-stu-id="14a41-200">content_scripts Key definitions</span></span>  

| <span data-ttu-id="14a41-201">密钥</span><span class="sxs-lookup"><span data-stu-id="14a41-201">Key</span></span> | <span data-ttu-id="14a41-202">详细信息</span><span class="sxs-lookup"><span data-stu-id="14a41-202">Details</span></span> |  
|:--- |:---- |  
| `matches` <span data-ttu-id="14a41-203">\ (必需 \ ) </span><span class="sxs-lookup"><span data-stu-id="14a41-203">\(required\)</span></span> | <span data-ttu-id="14a41-204">加载内容脚本之前要匹配的 URL 模式。</span><span class="sxs-lookup"><span data-stu-id="14a41-204">The URL pattern to match prior to loading the content script.</span></span> |  
| `js` | <span data-ttu-id="14a41-205">应在匹配的 Url 上加载的脚本。</span><span class="sxs-lookup"><span data-stu-id="14a41-205">The script that should be loaded on matching URLs.</span></span> |  
| `run_at` | <span data-ttu-id="14a41-206">指定插入来自该键的 JavaScript 文件的位置 `js` 。</span><span class="sxs-lookup"><span data-stu-id="14a41-206">Specifies where the JavaScript files from the `js` key are injected.</span></span> |  

<span data-ttu-id="14a41-207">接下来，必须创建 [后台脚本][MDNAnatomyExtensionBackgroundScripts]。</span><span class="sxs-lookup"><span data-stu-id="14a41-207">Next, you must create a [background script][MDNAnatomyExtensionBackgroundScripts].</span></span>  <span data-ttu-id="14a41-208">后台脚本在浏览器的后台运行，独立于网页或浏览器窗口的生命周期运行，并且能够与内容脚本进行通信。</span><span class="sxs-lookup"><span data-stu-id="14a41-208">Background scripts run in the background of the browser, run independently of the lifetime of a web page or browser window, and are able to communicate with content scripts.</span></span>  

<span data-ttu-id="14a41-209">在您的 `js` 文件夹内创建一个名为的文件， `background.js` 并添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="14a41-209">Inside of your `js` folder, create a file named `background.js` and add the following code.</span></span>  

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

<span data-ttu-id="14a41-210">[OnMessage][MDNApiRuntimeOnmessage]方法侦听[运行时。 sendMessage (][MDNApiRuntimeSendmessage]内容脚本中的 # B1。</span><span class="sxs-lookup"><span data-stu-id="14a41-210">The [runtime.onMessage][MDNApiRuntimeOnmessage] method listens for [runtime.sendMessage()][MDNApiRuntimeSendmessage] from the content script.</span></span>  <span data-ttu-id="14a41-211">如果页面的域不是 [docs.microsoft.com][MicrosoftDocs]，则 [BrowserAction ( # B1 ][MDNApiBrowseractionSeticon] 方法将为非活动图像设置图标路径。</span><span class="sxs-lookup"><span data-stu-id="14a41-211">If the domain of the page is not [docs.microsoft.com][MicrosoftDocs], then [browserAction.setIcon()][MDNApiBrowseractionSeticon] method sets the icon paths to the inactive images.</span></span>  

<span data-ttu-id="14a41-212">该脚本还会禁用浏览器操作 \ ([browserAction "禁用][MDApiBrowseractionDisable]\ ) "，以便用户无法单击 [docs.microsoft.com][MicrosoftDocs] 页面之外的浏览器操作。</span><span class="sxs-lookup"><span data-stu-id="14a41-212">The script also disables the browser action \([browserAction.disable][MDApiBrowseractionDisable]\), so that users are not able to click on the browser action outside of a [docs.microsoft.com][MicrosoftDocs] page.</span></span>  

<span data-ttu-id="14a41-213">必须将后台脚本添加到文件 [ 中的manifest.js][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] 。</span><span class="sxs-lookup"><span data-stu-id="14a41-213">You must add the background script to the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file.</span></span>  <span data-ttu-id="14a41-214">将以下 `background` 项添加到清单。</span><span class="sxs-lookup"><span data-stu-id="14a41-214">Add the following `background` key to your manifest.</span></span>  

```json
"background": {
    "scripts": ["js/background.js"],
    "persistent": true
  }
```  

### <span data-ttu-id="14a41-215">清单键定义</span><span class="sxs-lookup"><span data-stu-id="14a41-215">Manifest Key definitions</span></span>  

| <span data-ttu-id="14a41-216">密钥</span><span class="sxs-lookup"><span data-stu-id="14a41-216">Key</span></span> | <span data-ttu-id="14a41-217">详细信息</span><span class="sxs-lookup"><span data-stu-id="14a41-217">Details</span></span>|  
|:--- |:--- |  
| [<span data-ttu-id="14a41-218">背景</span><span class="sxs-lookup"><span data-stu-id="14a41-218">background</span></span>][MDNManifestjsonBackground] | <span data-ttu-id="14a41-219">包含后台脚本。</span><span class="sxs-lookup"><span data-stu-id="14a41-219">Contains the background scripts.</span></span> |  

#### <span data-ttu-id="14a41-220">背景键定义</span><span class="sxs-lookup"><span data-stu-id="14a41-220">background Key definitions</span></span>  

| <span data-ttu-id="14a41-221">密钥</span><span class="sxs-lookup"><span data-stu-id="14a41-221">Key</span></span> | <span data-ttu-id="14a41-222">详细信息</span><span class="sxs-lookup"><span data-stu-id="14a41-222">Details</span></span> |  
|:--- |:--- |  
| `scripts` | <span data-ttu-id="14a41-223">JavaScript 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="14a41-223">The path to a JavaScript file.</span></span> |  
| `persistent` <span data-ttu-id="14a41-224">（必需）</span><span class="sxs-lookup"><span data-stu-id="14a41-224">(required)</span></span> | <span data-ttu-id="14a41-225">这必须设置为 `true` 或 `false` 。</span><span class="sxs-lookup"><span data-stu-id="14a41-225">This must be set to `true` or `false`.</span></span>  <span data-ttu-id="14a41-226">如果设置为 `true` ，将加载后台脚本并为整个浏览部分保留。</span><span class="sxs-lookup"><span data-stu-id="14a41-226">If set to `true`, the background script is loaded and persists for the entire browsing section.</span></span>  <span data-ttu-id="14a41-227">如果设置为 `false` ，将加载后台脚本，并为浏览会话保留延迟。</span><span class="sxs-lookup"><span data-stu-id="14a41-227">If set to `false`, the background script is loaded with a delay and persists for the browsing session.</span></span> |  

<span data-ttu-id="14a41-228">重新加载扩展并再次测试。</span><span class="sxs-lookup"><span data-stu-id="14a41-228">Reload your extension and test again.</span></span>  <span data-ttu-id="14a41-229">若要重新加载你的扩展，请执行以下操作：单击 " **...** " 查看设置及更多 Microsoft Edge，单击 " **扩展**"，单击 "扩展 \ (**颜色转换器**\ ) "，然后单击 " **重新加载扩展**"。</span><span class="sxs-lookup"><span data-stu-id="14a41-229">To reload your extension: click the **...** for settings and more in Microsoft Edge, click **Extensions**, click on your extension \(**Color Changer**\), and click **Reload extension**.</span></span>  

<span data-ttu-id="14a41-230">现在，打开新的选项卡或刷新不是 [docs.microsoft.com][MicrosoftDocs] 页面的现有选项卡。</span><span class="sxs-lookup"><span data-stu-id="14a41-230">Now, open a new tab or refresh an existing tab that is not a [docs.microsoft.com][MicrosoftDocs] page.</span></span>  <span data-ttu-id="14a41-231">你应该会看到 "非活动" 图标，并且无法单击浏览器操作。</span><span class="sxs-lookup"><span data-stu-id="14a41-231">You should see the inactive icon and not be able to click on the browser action.</span></span>  

<span data-ttu-id="14a41-232">恭喜你！</span><span class="sxs-lookup"><span data-stu-id="14a41-232">Congratulations!</span></span>  <span data-ttu-id="14a41-233">您已为 Microsoft Edge 创建了一个扩展！</span><span class="sxs-lookup"><span data-stu-id="14a41-233">You created an extension for Microsoft Edge!</span></span>  <span data-ttu-id="14a41-234">查看 [GitHub 上的完整示例][GithubMicrosoftEdgeExtensionsDemosColorChanger]。</span><span class="sxs-lookup"><span data-stu-id="14a41-234">View the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span></span>  <span data-ttu-id="14a41-235">继续阅读，了解有关扩展的详细信息。</span><span class="sxs-lookup"><span data-stu-id="14a41-235">Continue reading to learn more about extensions.</span></span>  

## <span data-ttu-id="14a41-236">编写更复杂的扩展名</span><span class="sxs-lookup"><span data-stu-id="14a41-236">Writing a more complex extension</span></span>  

<span data-ttu-id="14a41-237">想要编写更复杂的扩展名？</span><span class="sxs-lookup"><span data-stu-id="14a41-237">Want to write a more complex extension?</span></span>  <span data-ttu-id="14a41-238">查看文章中 MDN 的 Beastify 扩展，即 [第二个扩展][MDNYourSecondWebextension]。</span><span class="sxs-lookup"><span data-stu-id="14a41-238">Take a look at the Beastify extension on MDN in the article, [Your second extension][MDNYourSecondWebextension].</span></span>  <span data-ttu-id="14a41-239">Microsoft Edge 的扩展模型与 Firefox 的扩展模型略有不同， [您的第二个扩展][MDNYourSecondWebextension] 中创建的 Beastify 扩展在 Microsoft Edge 中的功能。</span><span class="sxs-lookup"><span data-stu-id="14a41-239">The extension model for Microsoft Edge differs slightly from the extension model for Firefox, the Beastify extension created in [Your second extension][MDNYourSecondWebextension] was adapted to function in Microsoft Edge.</span></span>  <span data-ttu-id="14a41-240">在 [GitHub][GithubMicrosoftEdgeExtensionsDemosBeastify]上查看。</span><span class="sxs-lookup"><span data-stu-id="14a41-240">Check it out on [GitHub][GithubMicrosoftEdgeExtensionsDemosBeastify].</span></span>  

<span data-ttu-id="14a41-241">在浏览有关 MDN 的 [第二个扩展][MDNYourSecondWebextension]的文章时，请记住以下部分。</span><span class="sxs-lookup"><span data-stu-id="14a41-241">While walking through the article on MDN, [Your second extension][MDNYourSecondWebextension], keep in mind the following sections.</span></span>  

### <span data-ttu-id="14a41-242">API</span><span class="sxs-lookup"><span data-stu-id="14a41-242">APIs</span></span>  

<span data-ttu-id="14a41-243">有关 Microsoft Edge 中支持的扩展 Api 的列表，请参阅 [支持的 api][ExtensionsAPIsupportApis] 页面。</span><span class="sxs-lookup"><span data-stu-id="14a41-243">See the [Supported APIs][ExtensionsAPIsupportApis] page for a list of supported extensions APIs in Microsoft Edge.</span></span>  

### <span data-ttu-id="14a41-244">图标大小</span><span class="sxs-lookup"><span data-stu-id="14a41-244">Icon sizes</span></span>  

<span data-ttu-id="14a41-245">Microsoft Edge 的首选扩展名图标大小为 `20px` 、 `25px` 、 `30px` 和 `40px` 。</span><span class="sxs-lookup"><span data-stu-id="14a41-245">Preferred extension icon sizes for Microsoft Edge are `20px`, `25px`, `30px`, and `40px`.</span></span>  <span data-ttu-id="14a41-246">其他受支持的大小为 `19px` 、 `35px` 和 `38px` 。</span><span class="sxs-lookup"><span data-stu-id="14a41-246">Other supported sizes are `19px`, `35px`, and `38px`.</span></span>  <span data-ttu-id="14a41-247">有关图标大小和最佳做法的详细信息，请参阅 [设计][ExtensionsGuidesDesign] 指南。</span><span class="sxs-lookup"><span data-stu-id="14a41-247">For more info on icon sizes and best practices, see the [Design][ExtensionsGuidesDesign] guide.</span></span>  

### <span data-ttu-id="14a41-248">JavaScript</span><span class="sxs-lookup"><span data-stu-id="14a41-248">JavaScript</span></span>  

<span data-ttu-id="14a41-249">Microsoft Edge 的扩展模型不支持 JavaScript 承诺。</span><span class="sxs-lookup"><span data-stu-id="14a41-249">The extension model for Microsoft Edge does not support JavaScript Promises.</span></span>  <span data-ttu-id="14a41-250">而是使用回调。</span><span class="sxs-lookup"><span data-stu-id="14a41-250">Instead, use callbacks.</span></span>  <span data-ttu-id="14a41-251">有关在扩展中使用回调的更多示例，请查看 "  [快速打印][GithubMicrosoftEdgeExtensionsDemosQuickPrint] " 和 " [文本交换][GithubMicrosoftEdgeExtensionsDemosTextSwap] " 演示。</span><span class="sxs-lookup"><span data-stu-id="14a41-251">For more examples of using callbacks in an extension, take a look at the  [Quick Print][GithubMicrosoftEdgeExtensionsDemosQuickPrint] and [Text Swap][GithubMicrosoftEdgeExtensionsDemosTextSwap] demos.</span></span>  

<span data-ttu-id="14a41-252">浏览以下视频中的 [快速打印][GithubMicrosoftEdgeExtensionsDemosQuickPrint] 示例。</span><span class="sxs-lookup"><span data-stu-id="14a41-252">Walk through the [Quick Print][GithubMicrosoftEdgeExtensionsDemosQuickPrint] example in the following video.</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Adding-a-Background-Script-to-you-Edge-Extension/player]  

### <span data-ttu-id="14a41-253">Manifest.js</span><span class="sxs-lookup"><span data-stu-id="14a41-253">Manifest.json</span></span>  

*   <span data-ttu-id="14a41-254">`author`Microsoft Edge 中需要该密钥</span><span class="sxs-lookup"><span data-stu-id="14a41-254">The `author` key is required in Microsoft Edge</span></span>  
*   <span data-ttu-id="14a41-255">`activeTab`Microsoft Edge 中不支持该键</span><span class="sxs-lookup"><span data-stu-id="14a41-255">The `activeTab` key is not supported in Microsoft Edge</span></span>  

<span data-ttu-id="14a41-256">有关 [浏览器扩展][MDNBrowserExtensions]的详细信息，请参阅 [MDN web 文档][MDNWebDocs]。</span><span class="sxs-lookup"><span data-stu-id="14a41-256">For more information on [Browser Extensions][MDNBrowserExtensions], see [MDN web docs][MDNWebDocs].</span></span>  

<!-- image links -->  

<!--[ImageColorChangerHeader]: ../media/color-changer_header.png "Docs.microsoft.com body changed to blue"  -->  
<!--[ImageColorChangerPopup]: ../media/color-changer_popup.png "The pop-up interface of the extension"  -->  
<!--[ImageColorChangerHeaderAliceblue]: ../media/color-changer_header_aliceblue.png "[Docs.microsoft.com header changed to Aliceblue"  -->  
<!--[ImageColorChangerHeaderCornsilk]: ../media/color-changer_header_cornsilk.png "Docs.microsoft.com header changed to Cornsilk"  -->  

<!-- links -->  

[ExtensionsGuidesAddingRemovingExtensionsAdding]: ./adding-and-removing-extensions.md#adding-an-extension "添加对 Microsoft Edge 的扩展-添加、移动和删除扩展 |Microsoft 文档"  
[ExtensionsGuidesDebuggingExtensions]: ./debugging-extensions.md "调试扩展 |Microsoft 文档"  
[ExtensionsGuidesDesign]: ./design.md "Microsoft Edge 扩展设计指南 |Microsoft 文档"  
[ExtensionsGuidesDesignIcons]: ./design.md#icons "图标-Microsoft Edge 扩展的设计指南 |Microsoft 文档"  
[ExtensionsAPIsupportApis]: ../api-support/supported-apis.md " 支持的 Api |Microsoft 文档"  
[ExtensionsApisupportManifestKeys]: ../api-support/supported-manifest-keys.md "支持的清单键 |Microsoft 文档"  

[MicrosoftDocs]: https://docs.microsoft.com "Microsoft 文档"  

[MDNWebDocs]: https://developer.mozilla.org "MDN Web 文档"  
[MDNBrowserExtensions]: https://developer.mozilla.org/Add-ons/WebExtensions "浏览器扩展 |MDN"  
[MDNAnatomyExtension]: https://developer.mozilla.org/Add-ons/WebExtensions/Anatomy_of_a_WebExtension "扩展的剖析 |MDN"  
[MDNAnatomyExtensionBackgroundScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Anatomy_of_a_WebExtension#Background_scripts "后台脚本-扩展的解析 |MDN"  
[MDApiBrowseractionDisable]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/disable "browserAction 禁用 ( # A1-API |MDN" 
[MDNApiBrowseractionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setIcon "browserAction setIcon ( # A1-API |MDN"  
[MDNApiRuntimeOnmessage]: https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/onmessage "onMessage-API |MDN"  
[MDNApiRuntimeSendmessage]: https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendMessage "sendMessage ( # A1-API |MDN"  
[MDNApiTabs]: https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs "选项卡-API |MDN"  
[MDNApiTabsInsertcss]: https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs/insertCSS "insertCSS ( # A1-API |MDN"  
[MDNContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Content_scripts "内容脚本 |MDN"  
[MDNManifestjsonAuthor]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/author ""创作-manifest.js" |MDN"  
[MDNManifestjsonBackground]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/background "背景-manifest.json |MDN"  
[MDNManifestjsonBrowserAction]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/browser_action "browser_action-manifest.json |MDN"  
[MDNManifestjsonContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/content_scripts "content_scripts-manifest.json |MDN"  
[MDNManifestjsonDescription]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/description "说明-manifest.json |MDN"  
[MDNManifestjsonIcons]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/icons "图标-manifest.js在 |MDN"  
[MDNManifestjsonName]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/name "name-manifest.js"|"MDN"  
[MDNManifestjsonPermissions]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/permissions "权限-manifest.js"|"MDN"  
[MDNManifestjsonVersion]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/version "版本-manifest.js"|"MDN"  
[MDNYourSecondWebextension]: https://developer.mozilla.org/Add-ons/WebExtensions/Your_second_WebExtension "第二个扩展 |MDN"  

[Bing]: https://www.bing.com "必应"  

[GithubMicrosoftEdgeExtensionsDemosBeastify]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/beastify_edge "Beastify-MicrosoftEdge/MicrosoftEdge-我的扩展-演示 |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChanger]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/color_changer "Color 转换器-MicrosoftEdge/MicrosoftEdge-演示 |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChangerImages]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/color_changer/images "图像-颜色转换器-MicrosoftEdge/MicrosoftEdge-演示 |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/color_changer/manifest.json "Manifest.jsColor 转换器-MicrosoftEdge/MicrosoftEdge-演示 |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosQuickPrint]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/quick_print "快速打印-MicrosoftEdge/MicrosoftEdge-演示 |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosTextSwap]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/text_swap "文本交换-MicrosoftEdge/MicrosoftEdge-演示 |GitHub"  
