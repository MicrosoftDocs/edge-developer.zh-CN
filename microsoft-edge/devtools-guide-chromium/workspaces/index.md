---
description: Learn how to save changes made within DevTools to disk.
title: Edit files with Workspaces
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: fd72021e75c536fa38c27ae17e4b1678eb4ca85f
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992720"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# <span data-ttu-id="ea7a8-104">Edit files with Workspaces</span><span class="sxs-lookup"><span data-stu-id="ea7a8-104">Edit files with Workspaces</span></span>  

> [!NOTE]
> <span data-ttu-id="ea7a8-105">The goal of this tutorial is to provide hands-on practice in setting up and using Workspaces, so that you are able to use Workspaces in your own projects.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-105">The goal of this tutorial is to provide hands-on practice in setting up and using Workspaces, so that you are able to use Workspaces in your own projects.</span></span>  <span data-ttu-id="ea7a8-106">You are able to save the changes to the source code, on your local computer, that you made within DevTools after you enable Workspaces.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-106">You are able to save the changes to the source code, on your local computer, that you made within DevTools after you enable Workspaces.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="ea7a8-107">**Prerequisites**: Before beginning this tutorial, you should know how to perform the following actions.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-107">**Prerequisites**: Before beginning this tutorial, you should know how to perform the following actions.</span></span>  
> 
> *   [<span data-ttu-id="ea7a8-108">Use html, CSS, and JavaScript to build a web page</span><span class="sxs-lookup"><span data-stu-id="ea7a8-108">Use html, CSS, and JavaScript to build a web page</span></span>][MDNWebGettingStarted]  
> *   [<span data-ttu-id="ea7a8-109">Use DevTools to make basic changes to CSS</span><span class="sxs-lookup"><span data-stu-id="ea7a8-109">Use DevTools to make basic changes to CSS</span></span>][DevToolsCssIndex]  
> *   [<span data-ttu-id="ea7a8-110">Run a local HTTP web server</span><span class="sxs-lookup"><span data-stu-id="ea7a8-110">Run a local HTTP web server</span></span>][MDNSimpleLocalHTTPServer]  

## <span data-ttu-id="ea7a8-111">Overview</span><span class="sxs-lookup"><span data-stu-id="ea7a8-111">Overview</span></span>  

<span data-ttu-id="ea7a8-112">Workspaces enable you to save a change that you make in Devtools to a local copy of the same file on your computer.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-112">Workspaces enable you to save a change that you make in Devtools to a local copy of the same file on your computer.</span></span>  <span data-ttu-id="ea7a8-113">For this tutorial, you should have the following settings on your machine.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-113">For this tutorial, you should have the following settings on your machine.</span></span>  

*   <span data-ttu-id="ea7a8-114">You have the source code for your site on your desktop.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-114">You have the source code for your site on your desktop.</span></span>  
*   <span data-ttu-id="ea7a8-115">You are running a local web server from the source code directory, so that the site is accessible at `localhost:8080`.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-115">You are running a local web server from the source code directory, so that the site is accessible at `localhost:8080`.</span></span>  
*   <span data-ttu-id="ea7a8-116">You opened `localhost:8080` in Microsoft Edge, and you are using DevTools to change the CSS of the site.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-116">You opened `localhost:8080` in Microsoft Edge, and you are using DevTools to change the CSS of the site.</span></span>  

<span data-ttu-id="ea7a8-117">With Workspaces enabled, the CSS changes that you make within DevTools are saved to the source code on your desktop.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-117">With Workspaces enabled, the CSS changes that you make within DevTools are saved to the source code on your desktop.</span></span>  

## <span data-ttu-id="ea7a8-118">Limitations</span><span class="sxs-lookup"><span data-stu-id="ea7a8-118">Limitations</span></span>  

<span data-ttu-id="ea7a8-119">If you are using a modern framework, it probably transforms your source code from a format that is easy to maintain into a format that is optimized to run as quickly as possible.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-119">If you are using a modern framework, it probably transforms your source code from a format that is easy to maintain into a format that is optimized to run as quickly as possible.</span></span>  

<span data-ttu-id="ea7a8-120">Workspaces is usually able to map the optimized code back to your original source code with the help of [source maps][TreehouseBlogSourceMaps].</span><span class="sxs-lookup"><span data-stu-id="ea7a8-120">Workspaces is usually able to map the optimized code back to your original source code with the help of [source maps][TreehouseBlogSourceMaps].</span></span>  <span data-ttu-id="ea7a8-121">But there is a lot of variation between frameworks over how each uses source maps.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-121">But there is a lot of variation between frameworks over how each uses source maps.</span></span>  <span data-ttu-id="ea7a8-122">Devtools simply does support all of the variations.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-122">Devtools simply does support all of the variations.</span></span>  

<span data-ttu-id="ea7a8-123">Workspaces is known to not work with the following framework.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-123">Workspaces is known to not work with the following framework.</span></span>  

*   <span data-ttu-id="ea7a8-124">Create React App</span><span class="sxs-lookup"><span data-stu-id="ea7a8-124">Create React App</span></span>  

    <!-- If you run into issues while using Workspaces with your framework of choice, or you get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  
    
## <span data-ttu-id="ea7a8-125">Related feature: Local overrides</span><span class="sxs-lookup"><span data-stu-id="ea7a8-125">Related feature: Local overrides</span></span>  

<span data-ttu-id="ea7a8-126">**Local Overrides** is another DevTools feature that is similar to Workspaces.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-126">**Local Overrides** is another DevTools feature that is similar to Workspaces.</span></span>  <span data-ttu-id="ea7a8-127">Use Local Overrides when you want to experiment with changes to a page, and you need to see the changes across page loads, but you do not care about mapping your changes to the source code of the page.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-127">Use Local Overrides when you want to experiment with changes to a page, and you need to see the changes across page loads, but you do not care about mapping your changes to the source code of the page.</span></span>  

<!--Todo: add section when content is ready  -->  

## <span data-ttu-id="ea7a8-128">Step 1: Set up</span><span class="sxs-lookup"><span data-stu-id="ea7a8-128">Step 1: Set up</span></span>  

<span data-ttu-id="ea7a8-129">Complete the following actions, to get hands-on experience with Workspaces.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-129">Complete the following actions, to get hands-on experience with Workspaces.</span></span>  

### <span data-ttu-id="ea7a8-130">Set up the demo</span><span class="sxs-lookup"><span data-stu-id="ea7a8-130">Set up the demo</span></span>  

1.  <span data-ttu-id="ea7a8-131">[Open the demo][GlitchWorkspacesDemo].</span><span class="sxs-lookup"><span data-stu-id="ea7a8-131">[Open the demo][GlitchWorkspacesDemo].</span></span>  <!--In the top-left of the editor, a randomly-generated project name is displayed.  -->  
    
    :::image type="complex" source="../media/workspaces-glitch-workspaces-demo-source.msft.png" alt-text="A Glitch project" lightbox="../media/workspaces-glitch-workspaces-demo-source.msft.png":::
       <span data-ttu-id="ea7a8-133">A Glitch project</span><span class="sxs-lookup"><span data-stu-id="ea7a8-133">A Glitch project</span></span>  
    :::image-end:::  
    
    <!--1.  Choose the project name.  -->  
    <!--1.  Select **Advanced Options** > **Download Project**.  
    
    :::image type="complex" source="../media/workspaces-glitch-advanced-options-download-project.msft.png" alt-text="A Glitch project" lightbox="../media/workspaces-glitch-advanced-options-download-project.msft.png":::
       The Download Project button  
    :::image-end:::  

    -->  
    <!--1.  Close the tab.  -->  
    <!--1.  Unzip the source code and move the unzipped `app` directory to your desktop.  For the rest of this tutorial the unzipped directory is referred to as `~/Desktop/app`.  -->  
    
1.  <span data-ttu-id="ea7a8-134">Create an `app` directory on your desktop.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-134">Create an `app` directory on your desktop.</span></span>  <span data-ttu-id="ea7a8-135">Save copies of the files from the `workspaces-demo` directory to the `app` directory.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-135">Save copies of the files from the `workspaces-demo` directory to the `app` directory.</span></span>  <span data-ttu-id="ea7a8-136">For the rest of the tutorial, the directory is referred to as `~/Desktop/app`.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-136">For the rest of the tutorial, the directory is referred to as `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="ea7a8-137">Start a local web server in `~/Desktop/app`.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-137">Start a local web server in `~/Desktop/app`.</span></span>  <span data-ttu-id="ea7a8-138">Below is some sample code for starting up `SimpleHTTPServer`, but you may use whatever server you prefer.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-138">Below is some sample code for starting up `SimpleHTTPServer`, but you may use whatever server you prefer.</span></span>  
    
    :::row:::
       :::column span="":::
          ```bash
          cd ~/Desktop/app
          python -m SimpleHTTPServer # Python 2
          ```  
       :::column-end:::  
       :::column span="":::
          ```bash
          cd ~/Desktop/app
          python -m http.server # Python 3
          ```  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="ea7a8-139">Open a tab in Microsoft Edge and go to locally-hosted version of the site.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-139">Open a tab in Microsoft Edge and go to locally-hosted version of the site.</span></span>  <span data-ttu-id="ea7a8-140">You should be able to access it using a URL like `localhost:8080` or `http://0.0.0.0:8080`.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-140">You should be able to access it using a URL like `localhost:8080` or `http://0.0.0.0:8080`.</span></span>  <span data-ttu-id="ea7a8-141">The exact [port number][WikiPortURLs] may be different.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-141">The exact [port number][WikiPortURLs] may be different.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo.msft.png" alt-text="A Glitch project" lightbox="../media/workspaces-workspaces-demo.msft.png":::
       <span data-ttu-id="ea7a8-143">The demo</span><span class="sxs-lookup"><span data-stu-id="ea7a8-143">The demo</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="ea7a8-144">Set up DevTools</span><span class="sxs-lookup"><span data-stu-id="ea7a8-144">Set up DevTools</span></span>  

1.  <span data-ttu-id="ea7a8-145">Select `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open the **Console** panel of DevTools.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-145">Select `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open the **Console** panel of DevTools.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-console.msft.png" alt-text="A Glitch project" lightbox="../media/workspaces-workspaces-demo-console.msft.png":::
       <span data-ttu-id="ea7a8-147">The **Console** panel</span><span class="sxs-lookup"><span data-stu-id="ea7a8-147">The **Console** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ea7a8-148">Choose the **Sources** tab.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-148">Choose the **Sources** tab.</span></span>  
1.  <span data-ttu-id="ea7a8-149">Choose the **Filesystem** tab.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-149">Choose the **Filesystem** tab.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem.msft.png" alt-text="A Glitch project" lightbox="../media/workspaces-workspaces-demo-sources-filesystem.msft.png":::
       <span data-ttu-id="ea7a8-151">The **Filesystem** tab</span><span class="sxs-lookup"><span data-stu-id="ea7a8-151">The **Filesystem** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ea7a8-152">Choose **Add Folder To Workspace**.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-152">Choose **Add Folder To Workspace**.</span></span>  
1.  <span data-ttu-id="ea7a8-153">Type `~/Desktop/app`.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-153">Type `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="ea7a8-154">Choose **Allow** to give DevTools permission to read and write to the directory.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-154">Choose **Allow** to give DevTools permission to read and write to the directory.</span></span>  
    <span data-ttu-id="ea7a8-155">In the **Filesystem** tab, there is now a green dot next to `index.html`, `script.js`, and `styles.css`.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-155">In the **Filesystem** tab, there is now a green dot next to `index.html`, `script.js`, and `styles.css`.</span></span>  <span data-ttu-id="ea7a8-156">These green dots mean that DevTools has established a mapping between the network resources of the page, and the files in `~/Desktop/app`.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-156">These green dots mean that DevTools has established a mapping between the network resources of the page, and the files in `~/Desktop/app`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png" alt-text="A Glitch project" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png":::
       <span data-ttu-id="ea7a8-158">The **Filesystem** tab now shows a mapping between the local files and the network ones</span><span class="sxs-lookup"><span data-stu-id="ea7a8-158">The **Filesystem** tab now shows a mapping between the local files and the network ones</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="ea7a8-159">Step 2: Save a CSS change to disk</span><span class="sxs-lookup"><span data-stu-id="ea7a8-159">Step 2: Save a CSS change to disk</span></span>  

1.  <span data-ttu-id="ea7a8-160">Open `styles.css`.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-160">Open `styles.css`.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="ea7a8-161">The `color` property of `h1` elements is set to `fuchsia`.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-161">The `color` property of `h1` elements is set to `fuchsia`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png" alt-text="A Glitch project" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png":::
       <span data-ttu-id="ea7a8-163">View `styles.css` in a text editor</span><span class="sxs-lookup"><span data-stu-id="ea7a8-163">View `styles.css` in a text editor</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ea7a8-164">Choose the **Elements** tab.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-164">Choose the **Elements** tab.</span></span>  
1.  <span data-ttu-id="ea7a8-165">Change the value of the `color` property of the `<h1>` element to your favorite color.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-165">Change the value of the `color` property of the `<h1>` element to your favorite color.</span></span>  
    <span data-ttu-id="ea7a8-166">Remember that you need to choose the `<h1>` element in the **DOM Tree** in order to see the CSS rules applied to it in the **Styles** pane.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-166">Remember that you need to choose the `<h1>` element in the **DOM Tree** in order to see the CSS rules applied to it in the **Styles** pane.</span></span>  <span data-ttu-id="ea7a8-167">The green dot next to `styles.css:1` means that any change that you make are mapped to `~/Desktop/app/styles.css`.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-167">The green dot next to `styles.css:1` means that any change that you make are mapped to `~/Desktop/app/styles.css`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-css.msft.png" alt-text="A Glitch project" lightbox="../media/workspaces-workspaces-demo-elements-styles-css.msft.png":::
       <span data-ttu-id="ea7a8-169">The green indicator that the file is linked</span><span class="sxs-lookup"><span data-stu-id="ea7a8-169">The green indicator that the file is linked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ea7a8-170">Open `styles.css` in a text editor again.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-170">Open `styles.css` in a text editor again.</span></span>  <span data-ttu-id="ea7a8-171">The `color` property is now set to your favorite color.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-171">The `color` property is now set to your favorite color.</span></span>  
1.  <span data-ttu-id="ea7a8-172">Refresh the page.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-172">Refresh the page.</span></span>  <span data-ttu-id="ea7a8-173">The color of the `<h1>` element is still set to your favorite color.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-173">The color of the `<h1>` element is still set to your favorite color.</span></span>  <span data-ttu-id="ea7a8-174">The change remains across a refresh, because when you made the change DevTools saved the change to disk.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-174">The change remains across a refresh, because when you made the change DevTools saved the change to disk.</span></span>  <span data-ttu-id="ea7a8-175">And then, when you refreshed the page, your local server served the modified copy of the file from disk.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-175">And then, when you refreshed the page, your local server served the modified copy of the file from disk.</span></span>  
    
## <span data-ttu-id="ea7a8-176">Step 3: Save an HTML change to disk</span><span class="sxs-lookup"><span data-stu-id="ea7a8-176">Step 3: Save an HTML change to disk</span></span>  

### <span data-ttu-id="ea7a8-177">Change HTML from the Elements Panel</span><span class="sxs-lookup"><span data-stu-id="ea7a8-177">Change HTML from the Elements Panel</span></span>  

<span data-ttu-id="ea7a8-178">You may make changes to the html from the Element Panel, but your changes to the DOM tree are not saved to disk and only effect the current browser session.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-178">You may make changes to the html from the Element Panel, but your changes to the DOM tree are not saved to disk and only effect the current browser session.</span></span>  

<span data-ttu-id="ea7a8-179">The DOM tree is not html.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-179">The DOM tree is not html.</span></span>  

<!--### Try changing HTML from the Elements panel  

> [!WARNING]
> The workflow that you are about to try does not work.  You are trying it now so that you do not waste time later trying to figure out why it is not working.  

1.  Choose the **Elements** tab.  
1.  Choose and edit the text content of the `h1` element, which says `Workspaces Demo`, and replace it with `I ❤️  Cake`.  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-change-h1.msft.png" alt-text="A Glitch project" lightbox="../media/workspaces-workspaces-demo-change-h1.msft.png":::
       Attempt to change html from the DOM Tree of the **Elements** panel  
    :::image-end:::  
    
1.  Open `~/Desktop/app/index.html` in a text editor.  The change that you just made does not appear.  
1.  Refresh the page.  The page reverts to the original title.  
    
#### Optional: Why it is not working  

> [!NOTE]
> This section describes why the workflow from [Try changing html from the Elements panel](#try-changing-html-from-the-elements-panel) does not work.  You should skip this section if you do not care why.  

*   The tree of nodes that you see on the **Elements** panel represents the [DOM][MDNWebAPIsDOM] of the page.  
*   To display a page, a browser fetches html over the network, parses the html, and then converts it into a tree of DOM nodes.  
*   If the page has any JavaScript, that JavaScript may add, delete, or change DOM nodes.  CSS may change the DOM, too, using the [`content`][MDNCSSContent] property.  
*   The browser eventually uses the DOM to determine what content it should present to browser users.  
*   Therefore, the final state of the page that users see may be very different from the html that the browser fetched.  
*   This makes it difficult for DevTools to resolve where a change made in the **Elements** panel should be saved, because the DOM is affected by HTML, JavaScript, and CSS.  

In short, the **DOM Tree** `!==` HTML.  
-->  

### <span data-ttu-id="ea7a8-180">Change HTML from the Sources panel</span><span class="sxs-lookup"><span data-stu-id="ea7a8-180">Change HTML from the Sources panel</span></span>  

<span data-ttu-id="ea7a8-181">If you want to save a change to the html of the page, do it using the **Sources** panel.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-181">If you want to save a change to the html of the page, do it using the **Sources** panel.</span></span>  

1.  <span data-ttu-id="ea7a8-182">Choose the **Sources** tab.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-182">Choose the **Sources** tab.</span></span>  
1.  <span data-ttu-id="ea7a8-183">Choose the **Page** tab.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-183">Choose the **Page** tab.</span></span>  
1.  <span data-ttu-id="ea7a8-184">Choose **(index)**.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-184">Choose **(index)**.</span></span>  <span data-ttu-id="ea7a8-185">The HTML for the page opens.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-185">The HTML for the page opens.</span></span>  
1.  <span data-ttu-id="ea7a8-186">Replace `<h1>Workspaces Demo</h1>` with `<h1>I ❤️  Cake</h1>`.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-186">Replace `<h1>Workspaces Demo</h1>` with `<h1>I ❤️  Cake</h1>`.</span></span>  <span data-ttu-id="ea7a8-187">See the following figure.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-187">See the following figure.</span></span>  
1.  <span data-ttu-id="ea7a8-188">Select `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-188">Select `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="ea7a8-189">Refresh the page.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-189">Refresh the page.</span></span>  <span data-ttu-id="ea7a8-190">The `<h1>` element is still displaying the new text.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-190">The `<h1>` element is still displaying the new text.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-page-h1.msft.png" alt-text="A Glitch project" lightbox="../media/workspaces-workspaces-demo-sources-page-h1.msft.png":::
       <span data-ttu-id="ea7a8-192">Change HTML from the **Sources** panel</span><span class="sxs-lookup"><span data-stu-id="ea7a8-192">Change HTML from the **Sources** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ea7a8-193">Open `~/Desktop/app/index.html`.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-193">Open `~/Desktop/app/index.html`.</span></span>  <span data-ttu-id="ea7a8-194">The `<h1>` element contains the new text.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-194">The `<h1>` element contains the new text.</span></span>  
    
## <span data-ttu-id="ea7a8-195">Step 4: Save a JavaScript change to disk</span><span class="sxs-lookup"><span data-stu-id="ea7a8-195">Step 4: Save a JavaScript change to disk</span></span>  

<span data-ttu-id="ea7a8-196">The **Sources** panel is also the place to make changes to JavaScript.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-196">The **Sources** panel is also the place to make changes to JavaScript.</span></span>  <span data-ttu-id="ea7a8-197">But sometimes you need to access other panels, such as the **Elements** panel or the **Console** panel, while making changes to your site.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-197">But sometimes you need to access other panels, such as the **Elements** panel or the **Console** panel, while making changes to your site.</span></span>  <span data-ttu-id="ea7a8-198">There is a way to have the **Sources** panel open alongside other panels.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-198">There is a way to have the **Sources** panel open alongside other panels.</span></span>  

1.  <span data-ttu-id="ea7a8-199">Choose the **Elements** tab.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-199">Choose the **Elements** tab.</span></span>  
1.  <span data-ttu-id="ea7a8-200">Select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\).</span><span class="sxs-lookup"><span data-stu-id="ea7a8-200">Select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  <span data-ttu-id="ea7a8-201">The **Command Menu** opens.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-201">The **Command Menu** opens.</span></span>  
1.  <span data-ttu-id="ea7a8-202">Type `QS`, then select **Show Quick Source**.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-202">Type `QS`, then select **Show Quick Source**.</span></span>  <span data-ttu-id="ea7a8-203">At the bottom of your DevTools window there is now a **Quick Source** tab.  The tab is displaying the contents of `index.html`, which is the last file you edited in the **Sources** panel.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-203">At the bottom of your DevTools window there is now a **Quick Source** tab.  The tab is displaying the contents of `index.html`, which is the last file you edited in the **Sources** panel.</span></span>  <span data-ttu-id="ea7a8-204">The **Quick Source** tab gives you the editor from the **Sources** panel, so that you are able to edit files while having other panels open.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-204">The **Quick Source** tab gives you the editor from the **Sources** panel, so that you are able to edit files while having other panels open.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png" alt-text="A Glitch project" lightbox="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png":::
       <span data-ttu-id="ea7a8-206">Open the **Quick Source** tab using **Command Menu**</span><span class="sxs-lookup"><span data-stu-id="ea7a8-206">Open the **Quick Source** tab using **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ea7a8-207">Select `Control`+`P` \(Windows\) or `Command`+`P` \(macOS\) to open the **Open File** dialog.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-207">Select `Control`+`P` \(Windows\) or `Command`+`P` \(macOS\) to open the **Open File** dialog.</span></span>  <span data-ttu-id="ea7a8-208">See the following figure.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-208">See the following figure.</span></span>  
1.  <span data-ttu-id="ea7a8-209">Type `script`, then select **app/script.js**.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-209">Type `script`, then select **app/script.js**.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-script.msft.png" alt-text="A Glitch project" lightbox="../media/workspaces-workspaces-demo-search-script.msft.png":::
       <span data-ttu-id="ea7a8-211">Open `script.js` using the **Open File** dialog</span><span class="sxs-lookup"><span data-stu-id="ea7a8-211">Open `script.js` using the **Open File** dialog</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="ea7a8-212">The `Save Changes To Disk With Workspaces` link in the demo is styled regularly.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-212">The `Save Changes To Disk With Workspaces` link in the demo is styled regularly.</span></span>  
    
1.  <span data-ttu-id="ea7a8-213">Add the following code to the bottom of **script.js** using the **Quick Source** tab.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-213">Add the following code to the bottom of **script.js** using the **Quick Source** tab.</span></span>  
    
    ```javascript
    console.log('greetings from script.js');
    document.querySelector('a').style = 'font-style:italic';
    ```  
    
1.  <span data-ttu-id="ea7a8-214">Select `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-214">Select `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="ea7a8-215">Refresh the page.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-215">Refresh the page.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="ea7a8-216">The link on the page is now italicized.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-216">The link on the page is now italicized.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png" alt-text="A Glitch project" lightbox="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png":::
       <span data-ttu-id="ea7a8-218">The link on the page is now italicized</span><span class="sxs-lookup"><span data-stu-id="ea7a8-218">The link on the page is now italicized</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="ea7a8-219">Next steps</span><span class="sxs-lookup"><span data-stu-id="ea7a8-219">Next steps</span></span>  

<span data-ttu-id="ea7a8-220">Use what you have learned in this tutorial to set up Workspaces in your own project.</span><span class="sxs-lookup"><span data-stu-id="ea7a8-220">Use what you have learned in this tutorial to set up Workspaces in your own project.</span></span>  <!-- If you run into any issues or are able to get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  

<!--  
If you have more feedback on the topics or anything else, please use any of the channels below:  

*   [Mailing List][AlphabetGroupsAlphabetBrowserDevTools]  
*   [Twitter][TwitterAlphabetBrowserDevTools]  
    -->  

<!-- links -->  

[DevToolsCssIndex]: ../css/index.md "Get started with viewing and changing CSS | Microsoft Docs"  

<!--[LocalOverrides]: ../whats-new/2018/01/devtools#overrides -->  

<!--[AlphabetGroupsAlphabetBrowserDevTools]: https://groups.alphabet.com/forum/#!forum/alphabet-browser-developer-tools "Alphabet Browser DevTools - Alphabet Groups"  -->  

[GlitchWorkspacesDemo]: https://glitch.com/edit/#!/microsoft-edge-chromium-devtools?path=workspaces-demo/index.html:1:0 "Workspaces Demo files | Glitch"  

[MDNCSSContent]: https://developer.mozilla.org/docs/Web/CSS/content "Content - CSS: Cascading Style Sheets | MDN"  
[MDNWebGettingStarted]: https://developer.mozilla.org/docs/Learn/Getting_started_with_the_web "Getting started with the Web | MDN"  
[MDNSimpleLocalHTTPServer]: https://developer.mozilla.org/docs/Learn/Common_questions/set_up_a_local_testing_server#Running_a_simple_local_HTTP_server "Running a simple local HTTP server | MDN"  
[MDNWebAPIsDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "Introduction to DOM - Web APIs | MDN"  

<!--[StackOverflowAlphabetBrowserDevTools]: https://stackoverflow.com/questions/ask?tags=alphabet-browser-devtools "Alphabet Browser DevTools - Stack Overflow"  -->

[TreehouseBlogSourceMaps]: https://blog.teamtreehouse.com/introduction-source-maps "An Introduction to Source Maps | Treehouse Blog"  

<!-- [TwitterAlphabetBrowserDevTools]: https://twitter.com/alphabetbrowserdevtools "Alphabet Browser DevTools \(@AlphabetBrowserDevTools\) | Twitter"  -->

[WikiPortURLs]: https://en.wikipedia.org/wiki/Port_(computer_networking)#Use_in_URLs "Port \(computer networking\) - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="ea7a8-229">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="ea7a8-229">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ea7a8-230">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/workspaces/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="ea7a8-230">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/workspaces/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="ea7a8-232">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="ea7a8-232">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
