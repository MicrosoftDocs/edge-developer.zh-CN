---
description: Learn how to create a Microsoft Edge extension
title: Creating an extension
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, css, javascript, developer
ms.custom: seodec18
ms.openlocfilehash: a08fc6bd604ce810895e7103f7f6384dbedc9f78
ms.sourcegitcommit: 0bc1312a1e6a0ac37cf385201db4361fc05184fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2020
ms.locfileid: "10683649"
---
# <span data-ttu-id="cd271-104">Creating A Microsoft Edge Extension</span><span class="sxs-lookup"><span data-stu-id="cd271-104">Creating A Microsoft Edge Extension</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="cd271-105">In this guide, learn to create an extension for Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="cd271-105">In this guide, learn to create an extension for Microsoft Edge.</span></span>  <span data-ttu-id="cd271-106">This example extension allows you to manipulate specific CSS for [docs.microsoft.com][MicrosoftDocs] pages including walking you through creation of a manifest file, the user interface, and background and content scripts.</span><span class="sxs-lookup"><span data-stu-id="cd271-106">This example extension allows you to manipulate specific CSS for [docs.microsoft.com][MicrosoftDocs] pages including walking you through creation of a manifest file, the user interface, and background and content scripts.</span></span>  

:::image type="complex" source="../media/color-changer_header.png" alt-text="Docs.microsoft.com body changed to blue":::
   <span data-ttu-id="cd271-108">Docs.microsoft.com body changed to blue</span><span class="sxs-lookup"><span data-stu-id="cd271-108">Docs.microsoft.com body changed to blue</span></span>
:::image-end:::

<!--![Docs.microsoft.com body changed to blue][ImageColorChangerHeader]  -->  

<span data-ttu-id="cd271-109">This tutorial assumes you have basic understanding of what a browser extension is and how it work.</span><span class="sxs-lookup"><span data-stu-id="cd271-109">This tutorial assumes you have basic understanding of what a browser extension is and how it work.</span></span>  <span data-ttu-id="cd271-110">For more imformation about the building blocks for extensions, see [Anatomy of an extension][MDNAnatomyExtension].</span><span class="sxs-lookup"><span data-stu-id="cd271-110">For more imformation about the building blocks for extensions, see [Anatomy of an extension][MDNAnatomyExtension].</span></span>  

<span data-ttu-id="cd271-111">Download the code for the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span><span class="sxs-lookup"><span data-stu-id="cd271-111">Download the code for the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span></span>  

## <span data-ttu-id="cd271-112">Building the manifest file</span><span class="sxs-lookup"><span data-stu-id="cd271-112">Building the manifest file</span></span>  

<span data-ttu-id="cd271-113">To begin, create a directory for your extension and name it `color-changer`.</span><span class="sxs-lookup"><span data-stu-id="cd271-113">To begin, create a directory for your extension and name it `color-changer`.</span></span>  

<span data-ttu-id="cd271-114">Inside the `color-changer` folder, create a file named `manifest.json`.</span><span class="sxs-lookup"><span data-stu-id="cd271-114">Inside the `color-changer` folder, create a file named `manifest.json`.</span></span>  <span data-ttu-id="cd271-115">The `manifest.json` file is required for all extensions and provides important information for the extension, ranging from the extension name to the permissions.</span><span class="sxs-lookup"><span data-stu-id="cd271-115">The `manifest.json` file is required for all extensions and provides important information for the extension, ranging from the extension name to the permissions.</span></span>  

> [!NOTE] 
> <span data-ttu-id="cd271-116">This guide walks you through all the manifest keys you must use in this guide, but for a list of all supported and recommended manifest keys, see [Supported manifest keys][ExtensionsApisupportManifestKeys].</span><span class="sxs-lookup"><span data-stu-id="cd271-116">This guide walks you through all the manifest keys you must use in this guide, but for a list of all supported and recommended manifest keys, see [Supported manifest keys][ExtensionsApisupportManifestKeys].</span></span>  

<span data-ttu-id="cd271-117">Inside `manifest.json`, add the following code.</span><span class="sxs-lookup"><span data-stu-id="cd271-117">Inside `manifest.json`, add the following code.</span></span>  

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

### <span data-ttu-id="cd271-118">Manifest key definitions</span><span class="sxs-lookup"><span data-stu-id="cd271-118">Manifest key definitions</span></span>  

| <span data-ttu-id="cd271-119">Key</span><span class="sxs-lookup"><span data-stu-id="cd271-119">Key</span></span> | <span data-ttu-id="cd271-120">Details</span><span class="sxs-lookup"><span data-stu-id="cd271-120">Details</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="cd271-121">name</span><span class="sxs-lookup"><span data-stu-id="cd271-121">name</span></span>][MDNManifestjsonName] | <span data-ttu-id="cd271-122">The name of the extension.</span><span class="sxs-lookup"><span data-stu-id="cd271-122">The name of the extension.</span></span>  |  
| [<span data-ttu-id="cd271-123">author</span><span class="sxs-lookup"><span data-stu-id="cd271-123">author</span></span>][MDNManifestjsonAuthor] | <span data-ttu-id="cd271-124">The author of the extension.</span><span class="sxs-lookup"><span data-stu-id="cd271-124">The author of the extension.</span></span>  |  
| [<span data-ttu-id="cd271-125">version</span><span class="sxs-lookup"><span data-stu-id="cd271-125">version</span></span>][MDNManifestjsonVersion] | <span data-ttu-id="cd271-126">The extension version number.</span><span class="sxs-lookup"><span data-stu-id="cd271-126">The extension version number.</span></span>  |  
| [<span data-ttu-id="cd271-127">description</span><span class="sxs-lookup"><span data-stu-id="cd271-127">description</span></span>][MDNManifestjsonDescription] | <span data-ttu-id="cd271-128">The description of the extension displayed in the About section of the extension menu in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="cd271-128">The description of the extension displayed in the About section of the extension menu in Microsoft Edge.</span></span>  |  
| [<span data-ttu-id="cd271-129">permissions</span><span class="sxs-lookup"><span data-stu-id="cd271-129">permissions</span></span>][MDNManifestjsonPermissions] | <span data-ttu-id="cd271-130">An array of strings requesting permissions for the extension.</span><span class="sxs-lookup"><span data-stu-id="cd271-130">An array of strings requesting permissions for the extension.</span></span>  <span data-ttu-id="cd271-131">For your extension, you are requesting permissions to see the websites visited \("tabs"\) and to update content on URLs matching "`*://docs.microsoft.com/*`".</span><span class="sxs-lookup"><span data-stu-id="cd271-131">For your extension, you are requesting permissions to see the websites visited \("tabs"\) and to update content on URLs matching "`*://docs.microsoft.com/*`".</span></span>  |  
| [<span data-ttu-id="cd271-132">browser_action</span><span class="sxs-lookup"><span data-stu-id="cd271-132">browser_action</span></span>][MDNManifestjsonBrowserAction] | <span data-ttu-id="cd271-133">Contains the information for an icon.</span><span class="sxs-lookup"><span data-stu-id="cd271-133">Contains the information for an icon.</span></span> <span data-ttu-id="cd271-134">The icon is placed on the Microsoft Edge toolbar, to the right of the address bar.</span><span class="sxs-lookup"><span data-stu-id="cd271-134">The icon is placed on the Microsoft Edge toolbar, to the right of the address bar.</span></span>  |  

#### <span data-ttu-id="cd271-135">browser_action Key definitions</span><span class="sxs-lookup"><span data-stu-id="cd271-135">browser_action Key definitions</span></span>  

| <span data-ttu-id="cd271-136">Key</span><span class="sxs-lookup"><span data-stu-id="cd271-136">Key</span></span> | <span data-ttu-id="cd271-137">Details</span><span class="sxs-lookup"><span data-stu-id="cd271-137">Details</span></span> |  
|:--- |:--- |  
| `default_icon` | <span data-ttu-id="cd271-138">The icon that is used in the toolbar.</span><span class="sxs-lookup"><span data-stu-id="cd271-138">The icon that is used in the toolbar.</span></span>  |  
| `default_title` | <span data-ttu-id="cd271-139">The text that is displayed when a user hovers over the icon in the toolbar.</span><span class="sxs-lookup"><span data-stu-id="cd271-139">The text that is displayed when a user hovers over the icon in the toolbar.</span></span>  |  
| `default_popup` | <span data-ttu-id="cd271-140">The path to the HTML file for the pop-up window.</span><span class="sxs-lookup"><span data-stu-id="cd271-140">The path to the HTML file for the pop-up window.</span></span>  |  

<span data-ttu-id="cd271-141">Now that you have created the manifest file, you need a user interface for the extension.</span><span class="sxs-lookup"><span data-stu-id="cd271-141">Now that you have created the manifest file, you need a user interface for the extension.</span></span>  

## <span data-ttu-id="cd271-142">Creating the pop-up</span><span class="sxs-lookup"><span data-stu-id="cd271-142">Creating the pop-up</span></span>  

<span data-ttu-id="cd271-143">For your extension, create a pop-up for the user interface, like below.</span><span class="sxs-lookup"><span data-stu-id="cd271-143">For your extension, create a pop-up for the user interface, like below.</span></span>  

:::image type="complex" source="../media/color-changer_popup.png" alt-text="Docs.microsoft.com body changed to blue":::
   <span data-ttu-id="cd271-145">The pop-up interface of the extension</span><span class="sxs-lookup"><span data-stu-id="cd271-145">The pop-up interface of the extension</span></span>
:::image-end:::

<!--![The pop-up interface of the extension][ImageColorChangerPopup]  -->  

<span data-ttu-id="cd271-146">Create a file named `popup.html` in the root of your `color-changer` folder.</span><span class="sxs-lookup"><span data-stu-id="cd271-146">Create a file named `popup.html` in the root of your `color-changer` folder.</span></span>  <span data-ttu-id="cd271-147">Paste the following code into `popup.html`.</span><span class="sxs-lookup"><span data-stu-id="cd271-147">Paste the following code into `popup.html`.</span></span>  

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

<span data-ttu-id="cd271-148">In `popup.html`, you create a title, a paragraph, and three buttons \(Aliceblue, Cornsilk, and Reset\).</span><span class="sxs-lookup"><span data-stu-id="cd271-148">In `popup.html`, you create a title, a paragraph, and three buttons \(Aliceblue, Cornsilk, and Reset\).</span></span>  

<span data-ttu-id="cd271-149">Now create a folder named `css` and inside create a file named `styles.css`.</span><span class="sxs-lookup"><span data-stu-id="cd271-149">Now create a folder named `css` and inside create a file named `styles.css`.</span></span>  <span data-ttu-id="cd271-150">Add the styles below.</span><span class="sxs-lookup"><span data-stu-id="cd271-150">Add the styles below.</span></span>  

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

<span data-ttu-id="cd271-151">This CSS gives our extension some basic styles.</span><span class="sxs-lookup"><span data-stu-id="cd271-151">This CSS gives our extension some basic styles.</span></span>  <span data-ttu-id="cd271-152">Feel free to add more styles to customize your extension.</span><span class="sxs-lookup"><span data-stu-id="cd271-152">Feel free to add more styles to customize your extension.</span></span>  

<span data-ttu-id="cd271-153">Next, you must create the JavaScript file that interacts with the pop-up.</span><span class="sxs-lookup"><span data-stu-id="cd271-153">Next, you must create the JavaScript file that interacts with the pop-up.</span></span>  <span data-ttu-id="cd271-154">Create a `js` folder and a file named `popup.js` inside.</span><span class="sxs-lookup"><span data-stu-id="cd271-154">Create a `js` folder and a file named `popup.js` inside.</span></span>  <span data-ttu-id="cd271-155">Update `popup.js` with the following code.</span><span class="sxs-lookup"><span data-stu-id="cd271-155">Update `popup.js` with the following code.</span></span>  

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

<span data-ttu-id="cd271-156">In `popup.js`, the [tabs][MDNApiTabs] API allows you to interact with the tabs of the browser and inject script and styles into the page content.</span><span class="sxs-lookup"><span data-stu-id="cd271-156">In `popup.js`, the [tabs][MDNApiTabs] API allows you to interact with the tabs of the browser and inject script and styles into the page content.</span></span>  <span data-ttu-id="cd271-157">Using the [tabs.insertCSS()][MDNApiTabsInsertcss] method, you inject the specified CSS into the page which changes the header on [docs.microsoft.com][MicrosoftDocs] to a different color when the specified button is clicked.</span><span class="sxs-lookup"><span data-stu-id="cd271-157">Using the [tabs.insertCSS()][MDNApiTabsInsertcss] method, you inject the specified CSS into the page which changes the header on [docs.microsoft.com][MicrosoftDocs] to a different color when the specified button is clicked.</span></span>  

<span data-ttu-id="cd271-158">Now that you have the basic pop-up functionality, add icons to the extension.</span><span class="sxs-lookup"><span data-stu-id="cd271-158">Now that you have the basic pop-up functionality, add icons to the extension.</span></span>  

## <span data-ttu-id="cd271-159">Adding icons</span><span class="sxs-lookup"><span data-stu-id="cd271-159">Adding icons</span></span>  

<span data-ttu-id="cd271-160">Icons are used to represent the extension in the browser toolbar, the extensions menu, and other places.</span><span class="sxs-lookup"><span data-stu-id="cd271-160">Icons are used to represent the extension in the browser toolbar, the extensions menu, and other places.</span></span>  <span data-ttu-id="cd271-161">Download the [icons for your extension on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChangerImages].</span><span class="sxs-lookup"><span data-stu-id="cd271-161">Download the [icons for your extension on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChangerImages].</span></span> <span data-ttu-id="cd271-162">For more information about extension icons in Microsoft Edge, see [Design Guide][ExtensionsGuidesDesignIcons].</span><span class="sxs-lookup"><span data-stu-id="cd271-162">For more information about extension icons in Microsoft Edge, see [Design Guide][ExtensionsGuidesDesignIcons].</span></span>  

<span data-ttu-id="cd271-163">After you download the extension icons, save the icons in an `images` folder inside `color-changer`.</span><span class="sxs-lookup"><span data-stu-id="cd271-163">After you download the extension icons, save the icons in an `images` folder inside `color-changer`.</span></span>  

<span data-ttu-id="cd271-164">The icon that appears in the toolbar is set using `default_icon` inside of the [browser_action][MDNManifestjsonBrowserAction] key, which you already added to your manifest file in an earlier section.</span><span class="sxs-lookup"><span data-stu-id="cd271-164">The icon that appears in the toolbar is set using `default_icon` inside of the [browser_action][MDNManifestjsonBrowserAction] key, which you already added to your manifest file in an earlier section.</span></span>  

<span data-ttu-id="cd271-165">The `icons` key defines which icons should be used in the Extensions settings menus.</span><span class="sxs-lookup"><span data-stu-id="cd271-165">The `icons` key defines which icons should be used in the Extensions settings menus.</span></span>  <span data-ttu-id="cd271-166">Below, you are specifying multiple icons with different sizes to account for different screen resolutions.</span><span class="sxs-lookup"><span data-stu-id="cd271-166">Below, you are specifying multiple icons with different sizes to account for different screen resolutions.</span></span>  <span data-ttu-id="cd271-167">The name of the icons, `25` and `48` are the heights in pixels of the icons.</span><span class="sxs-lookup"><span data-stu-id="cd271-167">The name of the icons, `25` and `48` are the heights in pixels of the icons.</span></span>  

<span data-ttu-id="cd271-168">In the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file, include a top-level key for `icons`.</span><span class="sxs-lookup"><span data-stu-id="cd271-168">In the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file, include a top-level key for `icons`.</span></span>  

```json
  "icons": {
    "25": "images/color-changer25.png",
    "48": "images/color-changer48.png"
  }
```  

### <span data-ttu-id="cd271-169">Manifest Key definitions</span><span class="sxs-lookup"><span data-stu-id="cd271-169">Manifest Key definitions</span></span>  

| <span data-ttu-id="cd271-170">Key</span><span class="sxs-lookup"><span data-stu-id="cd271-170">Key</span></span> | <span data-ttu-id="cd271-171">Details</span><span class="sxs-lookup"><span data-stu-id="cd271-171">Details</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="cd271-172">icons</span><span class="sxs-lookup"><span data-stu-id="cd271-172">icons</span></span>][MDNManifestjsonIcons] | <span data-ttu-id="cd271-173">The icons for your extension with key-value pairs of image size in `px` and image path relative to the root directory of the extension.</span><span class="sxs-lookup"><span data-stu-id="cd271-173">The icons for your extension with key-value pairs of image size in `px` and image path relative to the root directory of the extension.</span></span> |  

> [!NOTE]
> <span data-ttu-id="cd271-174">Use the icons named `inactive##.png` located in the images folder later in this guide.</span><span class="sxs-lookup"><span data-stu-id="cd271-174">Use the icons named `inactive##.png` located in the images folder later in this guide.</span></span>  

## <span data-ttu-id="cd271-175">Testing the extension</span><span class="sxs-lookup"><span data-stu-id="cd271-175">Testing the extension</span></span>  

<span data-ttu-id="cd271-176">Now that you have added the user interface and created icons, test your extension.</span><span class="sxs-lookup"><span data-stu-id="cd271-176">Now that you have added the user interface and created icons, test your extension.</span></span>  <span data-ttu-id="cd271-177">Walk through the steps for [Adding an extension][ExtensionsGuidesAddingRemovingExtensionsAdding] to Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="cd271-177">Walk through the steps for [Adding an extension][ExtensionsGuidesAddingRemovingExtensionsAdding] to Microsoft Edge.</span></span>  <span data-ttu-id="cd271-178">Afterwards, return to this guide.</span><span class="sxs-lookup"><span data-stu-id="cd271-178">Afterwards, return to this guide.</span></span>  

<span data-ttu-id="cd271-179">After you add your extension, navigate to any [docs.microsoft.com][MicrosoftDocs] page.</span><span class="sxs-lookup"><span data-stu-id="cd271-179">After you add your extension, navigate to any [docs.microsoft.com][MicrosoftDocs] page.</span></span>  <span data-ttu-id="cd271-180">You should see the following pop-up after clicking on the browser action.</span><span class="sxs-lookup"><span data-stu-id="cd271-180">You should see the following pop-up after clicking on the browser action.</span></span>  <span data-ttu-id="cd271-181">The color of the [docs.microsoft.com][MicrosoftDocs] body should also change color.</span><span class="sxs-lookup"><span data-stu-id="cd271-181">The color of the [docs.microsoft.com][MicrosoftDocs] body should also change color.</span></span>  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_aliceblue.png" alt-text="Docs.microsoft.com body changed to blue":::
         <span data-ttu-id="cd271-183">Docs.microsoft.com header changed to Aliceblue</span><span class="sxs-lookup"><span data-stu-id="cd271-183">Docs.microsoft.com header changed to Aliceblue</span></span> :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Aliceblue][ImageColorChangerHeaderAliceblue]  -->
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_cornsilk.png" alt-text="Docs.microsoft.com body changed to blue":::
         <span data-ttu-id="cd271-185">Docs.microsoft.com header changed to Cornsilk</span><span class="sxs-lookup"><span data-stu-id="cd271-185">Docs.microsoft.com header changed to Cornsilk</span></span> :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Cornsilk][ImageColorChangerHeaderCornsilk]  -->
   :::column-end:::
:::row-end:::

<span data-ttu-id="cd271-186">If you encounter any errors or functionality that does not work, see the [Debugging extensions][ExtensionsGuidesDebuggingExtensions] guide or download the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span><span class="sxs-lookup"><span data-stu-id="cd271-186">If you encounter any errors or functionality that does not work, see the [Debugging extensions][ExtensionsGuidesDebuggingExtensions] guide or download the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span></span>  

## <span data-ttu-id="cd271-187">Adding content and background scripts</span><span class="sxs-lookup"><span data-stu-id="cd271-187">Adding content and background scripts</span></span>  

<span data-ttu-id="cd271-188">Go one step further and add logic to disable the extension from working on pages outside the [docs.microsoft.com][MicrosoftDocs] domain.</span><span class="sxs-lookup"><span data-stu-id="cd271-188">Go one step further and add logic to disable the extension from working on pages outside the [docs.microsoft.com][MicrosoftDocs] domain.</span></span>  

<span data-ttu-id="cd271-189">You must first create a [content script][MDNContentScripts].</span><span class="sxs-lookup"><span data-stu-id="cd271-189">You must first create a [content script][MDNContentScripts].</span></span>  <span data-ttu-id="cd271-190">Next, you must create content scripts that run in the context of a particular web page, are able to access the content of a web page, and are able to communicate with background scripts.</span><span class="sxs-lookup"><span data-stu-id="cd271-190">Next, you must create content scripts that run in the context of a particular web page, are able to access the content of a web page, and are able to communicate with background scripts.</span></span>  <span data-ttu-id="cd271-191">Inside of your `js` directory, create a file named `content.js` and add the following code.</span><span class="sxs-lookup"><span data-stu-id="cd271-191">Inside of your `js` directory, create a file named `content.js` and add the following code.</span></span>  

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

<span data-ttu-id="cd271-192">This script gets the URL of the current page through `document.location.href` and verifies whether the current page is on the [docs.microsoft.com][MicrosoftDocs] domain.</span><span class="sxs-lookup"><span data-stu-id="cd271-192">This script gets the URL of the current page through `document.location.href` and verifies whether the current page is on the [docs.microsoft.com][MicrosoftDocs] domain.</span></span>  <span data-ttu-id="cd271-193">If the page is not on the [docs.microsoft.com][MicrosoftDocs] domain \(for example  [https://www.bing.com/][|::ref1::|]\), the paths to the inactive icons \(grayed out icons\) are sent to the background script using [runtime.sendMessage()][MDNApiRuntimeSendmessage].</span><span class="sxs-lookup"><span data-stu-id="cd271-193">If the page is not on the [docs.microsoft.com][MicrosoftDocs] domain \(for example  [https://www.bing.com/][|::ref1::|]\), the paths to the inactive icons \(grayed out icons\) are sent to the background script using [runtime.sendMessage()][MDNApiRuntimeSendmessage].</span></span>  

<span data-ttu-id="cd271-194">You must update the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file to include the following `content_scripts` key.</span><span class="sxs-lookup"><span data-stu-id="cd271-194">You must update the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file to include the following `content_scripts` key.</span></span>  

```json
  "content_scripts": [{
    "matches": [
        "<all_urls>"
    ],
    "js": ["js/content.js"],
    "run_at": "document_end"
}]
```  

### <span data-ttu-id="cd271-195">Manifest Key definitions</span><span class="sxs-lookup"><span data-stu-id="cd271-195">Manifest Key definitions</span></span>  

| <span data-ttu-id="cd271-196">Key</span><span class="sxs-lookup"><span data-stu-id="cd271-196">Key</span></span> | <span data-ttu-id="cd271-197">Details</span><span class="sxs-lookup"><span data-stu-id="cd271-197">Details</span></span> |  
|:--- |:---- |  
| [<span data-ttu-id="cd271-198">content_scripts</span><span class="sxs-lookup"><span data-stu-id="cd271-198">content_scripts</span></span>][MDNManifestjsonContentScripts] | <span data-ttu-id="cd271-199">Contains the information about which content scripts the browser should load.</span><span class="sxs-lookup"><span data-stu-id="cd271-199">Contains the information about which content scripts the browser should load.</span></span> |  

#### <span data-ttu-id="cd271-200">content_scripts Key definitions</span><span class="sxs-lookup"><span data-stu-id="cd271-200">content_scripts Key definitions</span></span>  

| <span data-ttu-id="cd271-201">Key</span><span class="sxs-lookup"><span data-stu-id="cd271-201">Key</span></span> | <span data-ttu-id="cd271-202">Details</span><span class="sxs-lookup"><span data-stu-id="cd271-202">Details</span></span> |  
|:--- |:---- |  
| `matches` <span data-ttu-id="cd271-203">\(required\)</span><span class="sxs-lookup"><span data-stu-id="cd271-203">\(required\)</span></span> | <span data-ttu-id="cd271-204">The URL pattern to match prior to loading the content script.</span><span class="sxs-lookup"><span data-stu-id="cd271-204">The URL pattern to match prior to loading the content script.</span></span> |  
| `js` | <span data-ttu-id="cd271-205">The script that should be loaded on matching URLs.</span><span class="sxs-lookup"><span data-stu-id="cd271-205">The script that should be loaded on matching URLs.</span></span> |  
| `run_at` | <span data-ttu-id="cd271-206">Specifies where the JavaScript files from the `js` key are injected.</span><span class="sxs-lookup"><span data-stu-id="cd271-206">Specifies where the JavaScript files from the `js` key are injected.</span></span> |  

<span data-ttu-id="cd271-207">Next, you must create a [background script][MDNAnatomyExtensionBackgroundScripts].</span><span class="sxs-lookup"><span data-stu-id="cd271-207">Next, you must create a [background script][MDNAnatomyExtensionBackgroundScripts].</span></span>  <span data-ttu-id="cd271-208">Background scripts run in the background of the browser, run independently of the lifetime of a web page or browser window, and are able to communicate with content scripts.</span><span class="sxs-lookup"><span data-stu-id="cd271-208">Background scripts run in the background of the browser, run independently of the lifetime of a web page or browser window, and are able to communicate with content scripts.</span></span>  

<span data-ttu-id="cd271-209">Inside of your `js` folder, create a file named `background.js` and add the following code.</span><span class="sxs-lookup"><span data-stu-id="cd271-209">Inside of your `js` folder, create a file named `background.js` and add the following code.</span></span>  

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

<span data-ttu-id="cd271-210">The [runtime.onMessage][MDNApiRuntimeOnmessage] method listens for [runtime.sendMessage()][MDNApiRuntimeSendmessage] from the content script.</span><span class="sxs-lookup"><span data-stu-id="cd271-210">The [runtime.onMessage][MDNApiRuntimeOnmessage] method listens for [runtime.sendMessage()][MDNApiRuntimeSendmessage] from the content script.</span></span>  <span data-ttu-id="cd271-211">If the domain of the page is not [docs.microsoft.com][MicrosoftDocs], then [browserAction.setIcon()][MDNApiBrowseractionSeticon] method sets the icon paths to the inactive images.</span><span class="sxs-lookup"><span data-stu-id="cd271-211">If the domain of the page is not [docs.microsoft.com][MicrosoftDocs], then [browserAction.setIcon()][MDNApiBrowseractionSeticon] method sets the icon paths to the inactive images.</span></span>  

<span data-ttu-id="cd271-212">The script also disables the browser action \([browserAction.disable][MDApiBrowseractionDisable]\), so that users are not able to click on the browser action outside of a [docs.microsoft.com][MicrosoftDocs] page.</span><span class="sxs-lookup"><span data-stu-id="cd271-212">The script also disables the browser action \([browserAction.disable][MDApiBrowseractionDisable]\), so that users are not able to click on the browser action outside of a [docs.microsoft.com][MicrosoftDocs] page.</span></span>  

<span data-ttu-id="cd271-213">You must add the background script to the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file.</span><span class="sxs-lookup"><span data-stu-id="cd271-213">You must add the background script to the [manifest.json][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] file.</span></span>  <span data-ttu-id="cd271-214">Add the following `background` key to your manifest.</span><span class="sxs-lookup"><span data-stu-id="cd271-214">Add the following `background` key to your manifest.</span></span>  

```json
"background": {
    "scripts": ["js/background.js"],
    "persistent": true
  }
```  

### <span data-ttu-id="cd271-215">Manifest Key definitions</span><span class="sxs-lookup"><span data-stu-id="cd271-215">Manifest Key definitions</span></span>  

| <span data-ttu-id="cd271-216">Key</span><span class="sxs-lookup"><span data-stu-id="cd271-216">Key</span></span> | <span data-ttu-id="cd271-217">Details</span><span class="sxs-lookup"><span data-stu-id="cd271-217">Details</span></span>|  
|:--- |:--- |  
| [<span data-ttu-id="cd271-218">background</span><span class="sxs-lookup"><span data-stu-id="cd271-218">background</span></span>][MDNManifestjsonBackground] | <span data-ttu-id="cd271-219">Contains the background scripts.</span><span class="sxs-lookup"><span data-stu-id="cd271-219">Contains the background scripts.</span></span> |  

#### <span data-ttu-id="cd271-220">background Key definitions</span><span class="sxs-lookup"><span data-stu-id="cd271-220">background Key definitions</span></span>  

| <span data-ttu-id="cd271-221">Key</span><span class="sxs-lookup"><span data-stu-id="cd271-221">Key</span></span> | <span data-ttu-id="cd271-222">Details</span><span class="sxs-lookup"><span data-stu-id="cd271-222">Details</span></span> |  
|:--- |:--- |  
| `scripts` | <span data-ttu-id="cd271-223">The path to a JavaScript file.</span><span class="sxs-lookup"><span data-stu-id="cd271-223">The path to a JavaScript file.</span></span> |  
| `persistent` <span data-ttu-id="cd271-224">(required)</span><span class="sxs-lookup"><span data-stu-id="cd271-224">(required)</span></span> | <span data-ttu-id="cd271-225">This must be set to `true` or `false`.</span><span class="sxs-lookup"><span data-stu-id="cd271-225">This must be set to `true` or `false`.</span></span>  <span data-ttu-id="cd271-226">If set to `true`, the background script is loaded and persists for the entire browsing section.</span><span class="sxs-lookup"><span data-stu-id="cd271-226">If set to `true`, the background script is loaded and persists for the entire browsing section.</span></span>  <span data-ttu-id="cd271-227">If set to `false`, the background script is loaded with a delay and persists for the browsing session.</span><span class="sxs-lookup"><span data-stu-id="cd271-227">If set to `false`, the background script is loaded with a delay and persists for the browsing session.</span></span> |  

<span data-ttu-id="cd271-228">Reload your extension and test again.</span><span class="sxs-lookup"><span data-stu-id="cd271-228">Reload your extension and test again.</span></span>  <span data-ttu-id="cd271-229">To reload your extension: click the **...** for settings and more in Microsoft Edge, click **Extensions**, click on your extension \(**Color Changer**\), and click **Reload extension**.</span><span class="sxs-lookup"><span data-stu-id="cd271-229">To reload your extension: click the **...** for settings and more in Microsoft Edge, click **Extensions**, click on your extension \(**Color Changer**\), and click **Reload extension**.</span></span>  

<span data-ttu-id="cd271-230">Now, open a new tab or refresh an existing tab that is not a [docs.microsoft.com][MicrosoftDocs] page.</span><span class="sxs-lookup"><span data-stu-id="cd271-230">Now, open a new tab or refresh an existing tab that is not a [docs.microsoft.com][MicrosoftDocs] page.</span></span>  <span data-ttu-id="cd271-231">You should see the inactive icon and not be able to click on the browser action.</span><span class="sxs-lookup"><span data-stu-id="cd271-231">You should see the inactive icon and not be able to click on the browser action.</span></span>  

<span data-ttu-id="cd271-232">Congratulations!</span><span class="sxs-lookup"><span data-stu-id="cd271-232">Congratulations!</span></span>  <span data-ttu-id="cd271-233">You created an extension for Microsoft Edge!</span><span class="sxs-lookup"><span data-stu-id="cd271-233">You created an extension for Microsoft Edge!</span></span>  <span data-ttu-id="cd271-234">View the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span><span class="sxs-lookup"><span data-stu-id="cd271-234">View the [full sample on GitHub][GithubMicrosoftEdgeExtensionsDemosColorChanger].</span></span>  <span data-ttu-id="cd271-235">Continue reading to learn more about extensions.</span><span class="sxs-lookup"><span data-stu-id="cd271-235">Continue reading to learn more about extensions.</span></span>  

## <span data-ttu-id="cd271-236">Writing a more complex extension</span><span class="sxs-lookup"><span data-stu-id="cd271-236">Writing a more complex extension</span></span>  

<span data-ttu-id="cd271-237">Want to write a more complex extension?</span><span class="sxs-lookup"><span data-stu-id="cd271-237">Want to write a more complex extension?</span></span>  <span data-ttu-id="cd271-238">Take a look at the Beastify extension on MDN in the article, [Your second extension][MDNYourSecondWebextension].</span><span class="sxs-lookup"><span data-stu-id="cd271-238">Take a look at the Beastify extension on MDN in the article, [Your second extension][MDNYourSecondWebextension].</span></span>  <span data-ttu-id="cd271-239">The extension model for Microsoft Edge differs slightly from the extension model for Firefox, the Beastify extension created in [Your second extension][MDNYourSecondWebextension] was adapted to function in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="cd271-239">The extension model for Microsoft Edge differs slightly from the extension model for Firefox, the Beastify extension created in [Your second extension][MDNYourSecondWebextension] was adapted to function in Microsoft Edge.</span></span>  <span data-ttu-id="cd271-240">Check it out on [GitHub][GithubMicrosoftEdgeExtensionsDemosBeastify].</span><span class="sxs-lookup"><span data-stu-id="cd271-240">Check it out on [GitHub][GithubMicrosoftEdgeExtensionsDemosBeastify].</span></span>  

<span data-ttu-id="cd271-241">While walking through the article on MDN, [Your second extension][MDNYourSecondWebextension], keep in mind the following sections.</span><span class="sxs-lookup"><span data-stu-id="cd271-241">While walking through the article on MDN, [Your second extension][MDNYourSecondWebextension], keep in mind the following sections.</span></span>  

### <span data-ttu-id="cd271-242">APIs</span><span class="sxs-lookup"><span data-stu-id="cd271-242">APIs</span></span>  

<span data-ttu-id="cd271-243">See the [Supported APIs][ExtensionsAPIsupportApis] page for a list of supported extensions APIs in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="cd271-243">See the [Supported APIs][ExtensionsAPIsupportApis] page for a list of supported extensions APIs in Microsoft Edge.</span></span>  

### <span data-ttu-id="cd271-244">Icon sizes</span><span class="sxs-lookup"><span data-stu-id="cd271-244">Icon sizes</span></span>  

<span data-ttu-id="cd271-245">Preferred extension icon sizes for Microsoft Edge are `20px`, `25px`, `30px`, and `40px`.</span><span class="sxs-lookup"><span data-stu-id="cd271-245">Preferred extension icon sizes for Microsoft Edge are `20px`, `25px`, `30px`, and `40px`.</span></span>  <span data-ttu-id="cd271-246">Other supported sizes are `19px`, `35px`, and `38px`.</span><span class="sxs-lookup"><span data-stu-id="cd271-246">Other supported sizes are `19px`, `35px`, and `38px`.</span></span>  <span data-ttu-id="cd271-247">For more info on icon sizes and best practices, see the [Design][ExtensionsGuidesDesign] guide.</span><span class="sxs-lookup"><span data-stu-id="cd271-247">For more info on icon sizes and best practices, see the [Design][ExtensionsGuidesDesign] guide.</span></span>  

### <span data-ttu-id="cd271-248">JavaScript</span><span class="sxs-lookup"><span data-stu-id="cd271-248">JavaScript</span></span>  

<span data-ttu-id="cd271-249">The extension model for Microsoft Edge does not support JavaScript Promises.</span><span class="sxs-lookup"><span data-stu-id="cd271-249">The extension model for Microsoft Edge does not support JavaScript Promises.</span></span>  <span data-ttu-id="cd271-250">Instead, use callbacks.</span><span class="sxs-lookup"><span data-stu-id="cd271-250">Instead, use callbacks.</span></span>  <span data-ttu-id="cd271-251">For more examples of using callbacks in an extension, take a look at the  [Quick Print][GithubMicrosoftEdgeExtensionsDemosQuickPrint] and [Text Swap][GithubMicrosoftEdgeExtensionsDemosTextSwap] demos.</span><span class="sxs-lookup"><span data-stu-id="cd271-251">For more examples of using callbacks in an extension, take a look at the  [Quick Print][GithubMicrosoftEdgeExtensionsDemosQuickPrint] and [Text Swap][GithubMicrosoftEdgeExtensionsDemosTextSwap] demos.</span></span>  

<span data-ttu-id="cd271-252">Walk through the [Quick Print][GithubMicrosoftEdgeExtensionsDemosQuickPrint] example in the following video.</span><span class="sxs-lookup"><span data-stu-id="cd271-252">Walk through the [Quick Print][GithubMicrosoftEdgeExtensionsDemosQuickPrint] example in the following video.</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Adding-a-Background-Script-to-you-Edge-Extension/player]  

### <span data-ttu-id="cd271-253">Manifest.json</span><span class="sxs-lookup"><span data-stu-id="cd271-253">Manifest.json</span></span>  

*   <span data-ttu-id="cd271-254">The `author` key is required in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cd271-254">The `author` key is required in Microsoft Edge</span></span>  
*   <span data-ttu-id="cd271-255">The `activeTab` key is not supported in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cd271-255">The `activeTab` key is not supported in Microsoft Edge</span></span>  

<span data-ttu-id="cd271-256">For more information on [Browser Extensions][MDNBrowserExtensions], see [MDN web docs][MDNWebDocs].</span><span class="sxs-lookup"><span data-stu-id="cd271-256">For more information on [Browser Extensions][MDNBrowserExtensions], see [MDN web docs][MDNWebDocs].</span></span>  

<!-- image links -->  

<!--[ImageColorChangerHeader]: ../media/color-changer_header.png "Docs.microsoft.com body changed to blue"  -->  
<!--[ImageColorChangerPopup]: ../media/color-changer_popup.png "The pop-up interface of the extension"  -->  
<!--[ImageColorChangerHeaderAliceblue]: ../media/color-changer_header_aliceblue.png "[Docs.microsoft.com header changed to Aliceblue"  -->  
<!--[ImageColorChangerHeaderCornsilk]: ../media/color-changer_header_cornsilk.png "Docs.microsoft.com header changed to Cornsilk"  -->  

<!-- links -->  

[ExtensionsGuidesAddingRemovingExtensionsAdding]: ./adding-and-removing-extensions.md#adding-an-extension "Adding an Extension - Adding, moving, And Removing Extensions For Microsoft Edge | Microsoft Docs"  
[ExtensionsGuidesDebuggingExtensions]: ./debugging-extensions.md "Debugging Extensions | Microsoft Docs"  
[ExtensionsGuidesDesign]: ./design.md "Design Guidelines For Microsoft Edge Extensions | Microsoft Docs"  
[ExtensionsGuidesDesignIcons]: ./design.md#icons "Icons - Design Guidelines For Microsoft Edge Extensions | Microsoft Docs"  
[ExtensionsAPIsupportApis]: ../api-support/supported-apis.md " Supported APIs | Microsoft Docs"  
[ExtensionsApisupportManifestKeys]: ../api-support/supported-manifest-keys.md "Supported Manifest Keys | Microsoft Docs"  

[MicrosoftDocs]: https://docs.microsoft.com "Microsoft Docs"  

[MDNWebDocs]: https://developer.mozilla.org "MDN Web Docs"  
[MDNBrowserExtensions]: https://developer.mozilla.org/Add-ons/WebExtensions "Browser Extensions | MDN"  
[MDNAnatomyExtension]: https://developer.mozilla.org/Add-ons/WebExtensions/Anatomy_of_a_WebExtension "Anatomy of an extension | MDN"  
[MDNAnatomyExtensionBackgroundScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Anatomy_of_a_WebExtension#Background_scripts "Background scripts - Anatomy of an extension | MDN"  
[MDApiBrowseractionDisable]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/disable "browserAction.disable() - API | MDN" 
[MDNApiBrowseractionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setIcon "browserAction.setIcon() - API | MDN"  
[MDNApiRuntimeOnmessage]: https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/onmessage "runtime.onMessage - API | MDN"  
[MDNApiRuntimeSendmessage]: https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendMessage "runtime.sendMessage() - API | MDN"  
[MDNApiTabs]: https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs "tabs - API | MDN"  
[MDNApiTabsInsertcss]: https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs/insertCSS "tabs.insertCSS() - API | MDN"  
[MDNContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Content_scripts "Content scripts | MDN"  
[MDNManifestjsonAuthor]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/author "author - manifest.json | MDN"  
[MDNManifestjsonBackground]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/background "background - manifest.json | MDN"  
[MDNManifestjsonBrowserAction]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/browser_action "browser_action - manifest.json | MDN"  
[MDNManifestjsonContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/content_scripts "content_scripts - manifest.json | MDN"  
[MDNManifestjsonDescription]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/description "description - manifest.json | MDN"  
[MDNManifestjsonIcons]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/icons "icons - manifest.json | MDN"  
[MDNManifestjsonName]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/name "name - manifest.json | MDN"  
[MDNManifestjsonPermissions]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/permissions "permissions - manifest.json | MDN"  
[MDNManifestjsonVersion]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/version "version - manifest.json | MDN"  
[MDNYourSecondWebextension]: https://developer.mozilla.org/Add-ons/WebExtensions/Your_second_WebExtension "Your second extension | MDN"  

[Bing]: https://www.bing.com "Bing"  

[GithubMicrosoftEdgeExtensionsDemosBeastify]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/beastify_edge "Beastify - MicrosoftEdge/MicrosoftEdge-Extensions-Demos | GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChanger]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/color_changer "Color Changer - MicrosoftEdge/MicrosoftEdge-Extensions-Demos | GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChangerImages]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/color_changer/images "Images - Color Changer - MicrosoftEdge/MicrosoftEdge-Extensions-Demos | GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/color_changer/manifest.json "Manifest.json - Color Changer - MicrosoftEdge/MicrosoftEdge-Extensions-Demos | GitHub"  
[GithubMicrosoftEdgeExtensionsDemosQuickPrint]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/quick_print "Quick Print - MicrosoftEdge/MicrosoftEdge-Extensions-Demos | GitHub"  
[GithubMicrosoftEdgeExtensionsDemosTextSwap]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/text_swap "Text Swap - MicrosoftEdge/MicrosoftEdge-Extensions-Demos | GitHub"  
