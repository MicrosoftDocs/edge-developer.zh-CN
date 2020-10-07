---
description: Extensions Getting Started Part 2
title: Dynamically Insert NASA Picture Below The Page Body Tag Using Content Scripts
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, web development, html, css, javascript, developer, extensions
ms.openlocfilehash: fd2276c069116a7f69f06ae50f201e284b60f3ea
ms.sourcegitcommit: 744e2ecf42bcc427ae33e5dadbf6cd48ee0ab6a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016727"
---
# <span data-ttu-id="65ede-104">Dynamically Insert NASA Picture Below The Page Body Tag Using Content Scripts</span><span class="sxs-lookup"><span data-stu-id="65ede-104">Dynamically Insert NASA Picture Below The Page Body Tag Using Content Scripts</span></span>  

<!--  
[Completed Extension Package Source for This Part][ArchiveExtensionGettingStartedPart2]  
-->  

## <span data-ttu-id="65ede-105">Overview</span><span class="sxs-lookup"><span data-stu-id="65ede-105">Overview</span></span>  

<span data-ttu-id="65ede-106">In part 2, you learn to update your pop-up menu to not show the static stars image you had before, but to replace that image with a title and a standard HTML button.</span><span class="sxs-lookup"><span data-stu-id="65ede-106">In part 2, you learn to update your pop-up menu to not show the static stars image you had before, but to replace that image with a title and a standard HTML button.</span></span>  <span data-ttu-id="65ede-107">That button, when selected, passes that stars image, which is embedded in the Extension, to the content page.</span><span class="sxs-lookup"><span data-stu-id="65ede-107">That button, when selected, passes that stars image, which is embedded in the Extension, to the content page.</span></span>  <span data-ttu-id="65ede-108">That image, is inserted into the active browser tab.</span><span class="sxs-lookup"><span data-stu-id="65ede-108">That image, is inserted into the active browser tab.</span></span>  

*   <span data-ttu-id="65ede-109">Extension technologies covered in this guide</span><span class="sxs-lookup"><span data-stu-id="65ede-109">Extension technologies covered in this guide</span></span>  
    *   <span data-ttu-id="65ede-110">Injecting JavaScript libraries into Extension</span><span class="sxs-lookup"><span data-stu-id="65ede-110">Injecting JavaScript libraries into Extension</span></span>  
    *   <span data-ttu-id="65ede-111">Exposing Extension assets to browser tabs</span><span class="sxs-lookup"><span data-stu-id="65ede-111">Exposing Extension assets to browser tabs</span></span>  
    *   <span data-ttu-id="65ede-112">Including content pages in existing browser tabs</span><span class="sxs-lookup"><span data-stu-id="65ede-112">Including content pages in existing browser tabs</span></span>  
    *   <span data-ttu-id="65ede-113">Having content pages listen for messages from pop-ups and respond</span><span class="sxs-lookup"><span data-stu-id="65ede-113">Having content pages listen for messages from pop-ups and respond</span></span>  

## <span data-ttu-id="65ede-114">Remove the image from the pop-up and replace it with a button</span><span class="sxs-lookup"><span data-stu-id="65ede-114">Remove the image from the pop-up and replace it with a button</span></span>  

<span data-ttu-id="65ede-115">First, update your `popup.html` file with some straight forward markup that displays a title and a button.</span><span class="sxs-lookup"><span data-stu-id="65ede-115">First, update your `popup.html` file with some straight forward markup that displays a title and a button.</span></span>  <span data-ttu-id="65ede-116">You will program that button shortly, but for now, just include a reference to an empty JavaScript file `popup.js`.</span><span class="sxs-lookup"><span data-stu-id="65ede-116">You will program that button shortly, but for now, just include a reference to an empty JavaScript file `popup.js`.</span></span>  <span data-ttu-id="65ede-117">Here is update HTML.</span><span class="sxs-lookup"><span data-stu-id="65ede-117">Here is update HTML.</span></span>  

```html
<html>
    <head>
        <meta charset="utf-8" />
        <style>
            body {
                width: 500px;
            }
            button {
                background-color: #336dab;
                border: none;
                color: white;
                padding: 15px 32px;
                text-align: center;
                font-size: 16px;
            }
        </style>
    </head>
    <body>
        <h1>Show the NASA Picture of the Day</h1>
        <h2>(select the image to remove)</h2>
        <button id="sendmessageid">Display</button>
        <script src="popup.js"></script>
    </body>
</html>
```  

<span data-ttu-id="65ede-118">After updating your Extension and selecting the Extension launch icon, the have the following pop-up includes a display button.</span><span class="sxs-lookup"><span data-stu-id="65ede-118">After updating your Extension and selecting the Extension launch icon, the have the following pop-up includes a display button.</span></span>  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="popup.html display after pressing the Extension icon":::
   <span data-ttu-id="65ede-120">popup.html display after pressing the Extension icon</span><span class="sxs-lookup"><span data-stu-id="65ede-120">popup.html display after pressing the Extension icon</span></span>
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

## <span data-ttu-id="65ede-121">Updated strategy to display image at the top of the browser tab</span><span class="sxs-lookup"><span data-stu-id="65ede-121">Updated strategy to display image at the top of the browser tab</span></span>  

<span data-ttu-id="65ede-122">After adding the button, the next task is to make it bring up the `images/stars.jpeg` image file at the top of the active tab page.</span><span class="sxs-lookup"><span data-stu-id="65ede-122">After adding the button, the next task is to make it bring up the `images/stars.jpeg` image file at the top of the active tab page.</span></span>  

<span data-ttu-id="65ede-123">Remember, each tab page has a unique own thread and the Extension has a separate thread.</span><span class="sxs-lookup"><span data-stu-id="65ede-123">Remember, each tab page has a unique own thread and the Extension has a separate thread.</span></span>  <span data-ttu-id="65ede-124">So, you must first create a content script and inject that content script into the tab page.</span><span class="sxs-lookup"><span data-stu-id="65ede-124">So, you must first create a content script and inject that content script into the tab page.</span></span>  <span data-ttu-id="65ede-125">Once you do that, you must send a message from your pop-up to that content script running on the tab page telling that content script what image to show, and how to show it.</span><span class="sxs-lookup"><span data-stu-id="65ede-125">Once you do that, you must send a message from your pop-up to that content script running on the tab page telling that content script what image to show, and how to show it.</span></span>  

## <span data-ttu-id="65ede-126">Creating the pop-up JavaScript to send a message</span><span class="sxs-lookup"><span data-stu-id="65ede-126">Creating the pop-up JavaScript to send a message</span></span>  

<span data-ttu-id="65ede-127">First, create `popup/popup.js` and add code to send a message to your not-yet-created content script that you must momentarily create and inject into your browser tab.  To do that, the following code adds an `onclick` event to your pop-up display button.</span><span class="sxs-lookup"><span data-stu-id="65ede-127">First, create `popup/popup.js` and add code to send a message to your not-yet-created content script that you must momentarily create and inject into your browser tab.  To do that, the following code adds an `onclick` event to your pop-up display button.</span></span>  

```javascript
const sendMessageId = document.getElementById("sendmessageid");
if (sendMessageId) {
  sendMessageId.onclick = function() {
    // do something
  };
}
```  

<span data-ttu-id="65ede-128">In the `onclick` event, what you must do is find the current browser tab \(if there is only one open it is that one\).</span><span class="sxs-lookup"><span data-stu-id="65ede-128">In the `onclick` event, what you must do is find the current browser tab \(if there is only one open it is that one\).</span></span>  <span data-ttu-id="65ede-129">Then, once you find that tab, use the `chrome.tabs.sendmessage` Extension API to send a message to that tab.</span><span class="sxs-lookup"><span data-stu-id="65ede-129">Then, once you find that tab, use the `chrome.tabs.sendmessage` Extension API to send a message to that tab.</span></span>  

<span data-ttu-id="65ede-130">In that message you must include the URL to the image you want to display, and you want to send a unique ID that should be assigned to that inserted image.</span><span class="sxs-lookup"><span data-stu-id="65ede-130">In that message you must include the URL to the image you want to display, and you want to send a unique ID that should be assigned to that inserted image.</span></span>  <span data-ttu-id="65ede-131">You may choose to let the content insertion JavaScript generate that, but for reasons that become apparent later, generate that unique ID here in `popup.js` and pass it to the not-yet-created content script.</span><span class="sxs-lookup"><span data-stu-id="65ede-131">You may choose to let the content insertion JavaScript generate that, but for reasons that become apparent later, generate that unique ID here in `popup.js` and pass it to the not-yet-created content script.</span></span>  

<span data-ttu-id="65ede-132">Here is your updated `popup/popup.js` file.</span><span class="sxs-lookup"><span data-stu-id="65ede-132">Here is your updated `popup/popup.js` file.</span></span>  <span data-ttu-id="65ede-133">Also, pass in the current tab ID which you should need in a later section but for now, is not be used.</span><span class="sxs-lookup"><span data-stu-id="65ede-133">Also, pass in the current tab ID which you should need in a later section but for now, is not be used.</span></span>  

```javascript
const sendMessageId = document.getElementById("sendmessageid");
if (sendMessageId) {
    sendMessageId.onclick = function() {
        chrome.tabs.query({ active: true, currentWindow: true }, function(tabs) {
            chrome.tabs.sendMessage(
                tabs[0].id,
                {
                    url: chrome.extension.getURL("images/stars.jpeg"),
                    imageDivId: `${guidGenerator()}`,
                    tabId: tabs[0].id
                },
                function(response) {
                    window.close();
                }
            );
            function guidGenerator() {
                const S4 = function () {
                    return (((1 + Math.random()) * 0x10000) | 0).toString(16).substring(1);
                };
                return (S4() + S4() + "-" + S4() + "-" + S4() + "-" + S4() + "-" + S4() + S4() + S4());
            }
        });
    };
}
```  

## <span data-ttu-id="65ede-134">Making your stars.jpeg available from any browser tab</span><span class="sxs-lookup"><span data-stu-id="65ede-134">Making your stars.jpeg available from any browser tab</span></span>  

<span data-ttu-id="65ede-135">You are probably wondering why, when you pass the `images/stars.jpeg` must you use the `chrome.extension.getURL` chrome Extension API instead of just passing in the relative URL without the extra prefix like in the previous section.</span><span class="sxs-lookup"><span data-stu-id="65ede-135">You are probably wondering why, when you pass the `images/stars.jpeg` must you use the `chrome.extension.getURL` chrome Extension API instead of just passing in the relative URL without the extra prefix like in the previous section.</span></span>  <span data-ttu-id="65ede-136">By the way, that extra prefix, returned by `getUrl` with the image attached looks something like the following.</span><span class="sxs-lookup"><span data-stu-id="65ede-136">By the way, that extra prefix, returned by `getUrl` with the image attached looks something like the following.</span></span>  

```http
extension://inigobacliaghocjiapeaaoemkjifjhp/images/stars.jpeg
```  

<span data-ttu-id="65ede-137">The reason is that you are injecting the image using the `src` attribute of the `img` element into the content page.</span><span class="sxs-lookup"><span data-stu-id="65ede-137">The reason is that you are injecting the image using the `src` attribute of the `img` element into the content page.</span></span>  <span data-ttu-id="65ede-138">The content page is running on a unique thread that is not the same as the thread running the Extension.</span><span class="sxs-lookup"><span data-stu-id="65ede-138">The content page is running on a unique thread that is not the same as the thread running the Extension.</span></span>  <span data-ttu-id="65ede-139">You must expose the static image file as a web asset for it to work correctly.</span><span class="sxs-lookup"><span data-stu-id="65ede-139">You must expose the static image file as a web asset for it to work correctly.</span></span>  

<span data-ttu-id="65ede-140">To do that, you must add another entry in the `manifest.json` file.</span><span class="sxs-lookup"><span data-stu-id="65ede-140">To do that, you must add another entry in the `manifest.json` file.</span></span>  <span data-ttu-id="65ede-141">You must declare the image to be accessible from any browser tab.  That entry is as follows \(you should see it in the full `manifest.json` file below when you add the content script declaration coming up\).</span><span class="sxs-lookup"><span data-stu-id="65ede-141">You must declare the image to be accessible from any browser tab.  That entry is as follows \(you should see it in the full `manifest.json` file below when you add the content script declaration coming up\).</span></span>  

```json
"web_accessible_resources": [
    "images/*.jpeg"
]
```  

<span data-ttu-id="65ede-142">You have now written the code in your `popup.js` file to send a message to the content page that is embedded on the current active tab page, but you have not created and injected that content page.</span><span class="sxs-lookup"><span data-stu-id="65ede-142">You have now written the code in your `popup.js` file to send a message to the content page that is embedded on the current active tab page, but you have not created and injected that content page.</span></span>  <span data-ttu-id="65ede-143">Do that now.</span><span class="sxs-lookup"><span data-stu-id="65ede-143">Do that now.</span></span>  

## <span data-ttu-id="65ede-144">Updating your manifest.json for content and web access</span><span class="sxs-lookup"><span data-stu-id="65ede-144">Updating your manifest.json for content and web access</span></span>  

<span data-ttu-id="65ede-145">The updated `manifest.json` that includes the `content-scripts` and `web_accessible_resources` is as follows.</span><span class="sxs-lookup"><span data-stu-id="65ede-145">The updated `manifest.json` that includes the `content-scripts` and `web_accessible_resources` is as follows.</span></span>  

```json
{
    "name": "NASA Picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium Extension to show the NASA Picture of the Day.",
    "icons": {
        "16": "icons/nasapod16x16.png",
        "32": "icons/nasapod32x32.png",
        "48": "icons/nasapod48x48.png",
        "128": "icons/nasapod128x128.png"
    },
    "browser_action": {
        "default_popup": "popup/popup.html"
    },
    "content_scripts": [
        {
            "matches": [
              "<all_urls>"
            ],
            "js": ["lib/jquery.min.js","content-scripts/content.js"]
        }
    ],
    "web_accessible_resources": [
        "images/*.jpeg"
    ]
}
```  

<span data-ttu-id="65ede-146">The section you added is `content_scripts`.</span><span class="sxs-lookup"><span data-stu-id="65ede-146">The section you added is `content_scripts`.</span></span>  <span data-ttu-id="65ede-147">The attribute `matches` set to `<all_urls>` means that all the files mention in the **content_scripts** section is injected into all browser tab pages when each are loaded.</span><span class="sxs-lookup"><span data-stu-id="65ede-147">The attribute `matches` set to `<all_urls>` means that all the files mention in the **content_scripts** section is injected into all browser tab pages when each are loaded.</span></span>  <span data-ttu-id="65ede-148">The allowable types of files that are able to be injected here are javascript and css.</span><span class="sxs-lookup"><span data-stu-id="65ede-148">The allowable types of files that are able to be injected here are javascript and css.</span></span>  <span data-ttu-id="65ede-149">You also added `libjquery.min.js`.</span><span class="sxs-lookup"><span data-stu-id="65ede-149">You also added `libjquery.min.js`.</span></span>  <span data-ttu-id="65ede-150">You are able to include that from the download mentioned at the top of the section.</span><span class="sxs-lookup"><span data-stu-id="65ede-150">You are able to include that from the download mentioned at the top of the section.</span></span>  

## <span data-ttu-id="65ede-151">Adding jQuery and understanding the associated thread</span><span class="sxs-lookup"><span data-stu-id="65ede-151">Adding jQuery and understanding the associated thread</span></span>  

<span data-ttu-id="65ede-152">In the content scripts you are injecting, plan on using jQuery \(`$`\).</span><span class="sxs-lookup"><span data-stu-id="65ede-152">In the content scripts you are injecting, plan on using jQuery \(`$`\).</span></span>  <span data-ttu-id="65ede-153">You added a minified version of jQuery and put it in your Extension package as `lib\jquery.min.js`.</span><span class="sxs-lookup"><span data-stu-id="65ede-153">You added a minified version of jQuery and put it in your Extension package as `lib\jquery.min.js`.</span></span>  <span data-ttu-id="65ede-154">These content scripts run in an individual sandbox of sorts, which means that the jQuery injected into the `popup.js` page does not share with the content.</span><span class="sxs-lookup"><span data-stu-id="65ede-154">These content scripts run in an individual sandbox of sorts, which means that the jQuery injected into the `popup.js` page does not share with the content.</span></span>  

<span data-ttu-id="65ede-155">Keep in mind that even if the browser tab has JavaScript running on it on the loaded web page, any content injected does not have access to that.</span><span class="sxs-lookup"><span data-stu-id="65ede-155">Keep in mind that even if the browser tab has JavaScript running on it on the loaded web page, any content injected does not have access to that.</span></span>  <span data-ttu-id="65ede-156">That injected JavaScript just has access to the actual DOM loaded in that browser tab.</span><span class="sxs-lookup"><span data-stu-id="65ede-156">That injected JavaScript just has access to the actual DOM loaded in that browser tab.</span></span>  

## <span data-ttu-id="65ede-157">Adding the content script message listener</span><span class="sxs-lookup"><span data-stu-id="65ede-157">Adding the content script message listener</span></span>  

<span data-ttu-id="65ede-158">Here is that `content-scripts\content.js` file that gets injected into every browser tab page based on your `manifest.json` `content-scripts` section.</span><span class="sxs-lookup"><span data-stu-id="65ede-158">Here is that `content-scripts\content.js` file that gets injected into every browser tab page based on your `manifest.json` `content-scripts` section.</span></span>  

```javascript
chrome.runtime.onMessage.addListener(function(request, sender, sendResponse) {
    $("body").prepend(
        `<img  src="${request.url}" id="${request.imageDivId}"
               class="slide-image" /> `
    );
    $("head").prepend(
        `<style>
          .slide-image {
              height: auto;
              width: 100vw;
          }
        </style>`
    );
    $(`#${request.imageDivId}`).click(function() {
        $(`#${request.imageDivId}`).remove(`#${request.imageDivId}`);
    });
    sendResponse({ fromcontent: "This message is from content.js" });
});
```  

<span data-ttu-id="65ede-159">Notice that all the above JavaScript does is to register a `listener` using the `chrome.runtime.onMessage.addListener` Extension API method.</span><span class="sxs-lookup"><span data-stu-id="65ede-159">Notice that all the above JavaScript does is to register a `listener` using the `chrome.runtime.onMessage.addListener` Extension API method.</span></span>  <span data-ttu-id="65ede-160">This listener waits for messages like the one you sent from the `popup.js` described earlier with the `chrome.tabs.sendMessage` Extension API method.</span><span class="sxs-lookup"><span data-stu-id="65ede-160">This listener waits for messages like the one you sent from the `popup.js` described earlier with the `chrome.tabs.sendMessage` Extension API method.</span></span>  

<span data-ttu-id="65ede-161">The first parameter of the `addListener` method is a function whose first parameter, request, is the details of the message being passed in.</span><span class="sxs-lookup"><span data-stu-id="65ede-161">The first parameter of the `addListener` method is a function whose first parameter, request, is the details of the message being passed in.</span></span>  <span data-ttu-id="65ede-162">Remember, from `popup.js`, when you used the `sendMessage` method, those attributes of the first parameter are `url` and `imageDivId`.</span><span class="sxs-lookup"><span data-stu-id="65ede-162">Remember, from `popup.js`, when you used the `sendMessage` method, those attributes of the first parameter are `url` and `imageDivId`.</span></span>  

<span data-ttu-id="65ede-163">When an event is processed by the listener, the function that is the first parameter is run.</span><span class="sxs-lookup"><span data-stu-id="65ede-163">When an event is processed by the listener, the function that is the first parameter is run.</span></span>  <span data-ttu-id="65ede-164">The first parameter of that function is an object that has attributes as assigned by `sendMessage`.</span><span class="sxs-lookup"><span data-stu-id="65ede-164">The first parameter of that function is an object that has attributes as assigned by `sendMessage`.</span></span>  <span data-ttu-id="65ede-165">That function simply processes the three jQuery script lines.</span><span class="sxs-lookup"><span data-stu-id="65ede-165">That function simply processes the three jQuery script lines.</span></span>  

*   <span data-ttu-id="65ede-166">The first dynamically inserts into the DOM header a **\<style\>** section that you must assign as a `slide-image` class to your `img` element.</span><span class="sxs-lookup"><span data-stu-id="65ede-166">The first dynamically inserts into the DOM header a **\<style\>** section that you must assign as a `slide-image` class to your `img` element.</span></span>  
*   <span data-ttu-id="65ede-167">The second, appends an `img` element right below the `body` of your browser tab that has the `slide-image` class assigned as well as the `imageDivId` as the ID of that image element.</span><span class="sxs-lookup"><span data-stu-id="65ede-167">The second, appends an `img` element right below the `body` of your browser tab that has the `slide-image` class assigned as well as the `imageDivId` as the ID of that image element.</span></span>  
*   <span data-ttu-id="65ede-168">The third adds a `click` event that covers the entire image allowing the user to select any place on the image and that image is be removed from the page \(along with it is event listener\).</span><span class="sxs-lookup"><span data-stu-id="65ede-168">The third adds a `click` event that covers the entire image allowing the user to select any place on the image and that image is be removed from the page \(along with it is event listener\).</span></span>  

## <span data-ttu-id="65ede-169">Adding functionality to remove the displayed image when selected</span><span class="sxs-lookup"><span data-stu-id="65ede-169">Adding functionality to remove the displayed image when selected</span></span>  

<span data-ttu-id="65ede-170">Now, when you browse to any page and select your **Extension** icon, the pop-up menu is displayed as follows.</span><span class="sxs-lookup"><span data-stu-id="65ede-170">Now, when you browse to any page and select your **Extension** icon, the pop-up menu is displayed as follows.</span></span>  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="popup.html display after pressing the Extension icon":::
   <span data-ttu-id="65ede-172">popup.html display after pressing the Extension icon</span><span class="sxs-lookup"><span data-stu-id="65ede-172">popup.html display after pressing the Extension icon</span></span>
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

<span data-ttu-id="65ede-173">When you select the `Display` button, you get what is below.</span><span class="sxs-lookup"><span data-stu-id="65ede-173">When you select the `Display` button, you get what is below.</span></span>  <span data-ttu-id="65ede-174">If you select anywhere on the `stars.jpeg` image, that image element is removed and tab pages collapses back to what was originally displayed.</span><span class="sxs-lookup"><span data-stu-id="65ede-174">If you select anywhere on the `stars.jpeg` image, that image element is removed and tab pages collapses back to what was originally displayed.</span></span>  

:::image type="complex" source="./media/part2-showingimage.png" alt-text="popup.html display after pressing the Extension icon":::
   <span data-ttu-id="65ede-176">The image showing in browser</span><span class="sxs-lookup"><span data-stu-id="65ede-176">The image showing in browser</span></span>
:::image-end:::

<!--![The image showing in browser][ImagePart2Showingimage]  -->  

<span data-ttu-id="65ede-177">You have now created an Extension that successfully sends a message from the Extension icon pop-up, to the dynamically inserted JavaScript running as content on the browser tab.  That injected content set the image element to display your static stars jpeg.</span><span class="sxs-lookup"><span data-stu-id="65ede-177">You have now created an Extension that successfully sends a message from the Extension icon pop-up, to the dynamically inserted JavaScript running as content on the browser tab.  That injected content set the image element to display your static stars jpeg.</span></span>  

<!-- image links -->  

<!--[ImagePart2Popupdialog]: ./media/part2-popupdialog.png "popup.html display after pressing the Extension icon"  -->  
<!--[ImagePart2Showingimage]: ./media/part2-showingimage.png "The image showing in browser"  -->

<!-- links -->  

[ArchiveExtensionGettingStartedPart2]: ./extension-source/extension-getting-started-part2.zip "Completed Extension Package Source for This Part | Microsoft Docs"  
