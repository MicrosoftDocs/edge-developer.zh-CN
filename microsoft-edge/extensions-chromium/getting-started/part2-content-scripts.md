---
description: 扩展入门第2部分
title: 使用内容脚本在页面正文标记下方动态插入 NASA 图片
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、web 开发、html、css、javascript、开发人员、扩展
ms.openlocfilehash: fd2276c069116a7f69f06ae50f201e284b60f3ea
ms.sourcegitcommit: 744e2ecf42bcc427ae33e5dadbf6cd48ee0ab6a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016727"
---
# <span data-ttu-id="0150e-104">使用内容脚本在页面正文标记下方动态插入 NASA 图片</span><span class="sxs-lookup"><span data-stu-id="0150e-104">Dynamically Insert NASA Picture Below The Page Body Tag Using Content Scripts</span></span>  

<!--  
[Completed Extension Package Source for This Part][ArchiveExtensionGettingStartedPart2]  
-->  

## <span data-ttu-id="0150e-105">概述</span><span class="sxs-lookup"><span data-stu-id="0150e-105">Overview</span></span>  

<span data-ttu-id="0150e-106">在第2部分中，你将了解如何更新你的弹出菜单，使其不显示你以前拥有的静态星图像，但将该图像替换为 "标题" 和 "标准 HTML" 按钮。</span><span class="sxs-lookup"><span data-stu-id="0150e-106">In part 2, you learn to update your pop-up menu to not show the static stars image you had before, but to replace that image with a title and a standard HTML button.</span></span>  <span data-ttu-id="0150e-107">选中此按钮后，会将该星形图像（嵌入在扩展中）传递到内容页面。</span><span class="sxs-lookup"><span data-stu-id="0150e-107">That button, when selected, passes that stars image, which is embedded in the Extension, to the content page.</span></span>  <span data-ttu-id="0150e-108">该图像将插入到活动浏览器选项卡中。</span><span class="sxs-lookup"><span data-stu-id="0150e-108">That image, is inserted into the active browser tab.</span></span>  

*   <span data-ttu-id="0150e-109">本指南中介绍的扩展技术</span><span class="sxs-lookup"><span data-stu-id="0150e-109">Extension technologies covered in this guide</span></span>  
    *   <span data-ttu-id="0150e-110">将 JavaScript 库注入扩展</span><span class="sxs-lookup"><span data-stu-id="0150e-110">Injecting JavaScript libraries into Extension</span></span>  
    *   <span data-ttu-id="0150e-111">向浏览器选项卡公开扩展资源</span><span class="sxs-lookup"><span data-stu-id="0150e-111">Exposing Extension assets to browser tabs</span></span>  
    *   <span data-ttu-id="0150e-112">在现有浏览器选项卡中包括内容页</span><span class="sxs-lookup"><span data-stu-id="0150e-112">Including content pages in existing browser tabs</span></span>  
    *   <span data-ttu-id="0150e-113">让内容页侦听来自弹出窗口的消息并进行响应</span><span class="sxs-lookup"><span data-stu-id="0150e-113">Having content pages listen for messages from pop-ups and respond</span></span>  

## <span data-ttu-id="0150e-114">从弹出窗口中删除图像，并将其替换为按钮</span><span class="sxs-lookup"><span data-stu-id="0150e-114">Remove the image from the pop-up and replace it with a button</span></span>  

<span data-ttu-id="0150e-115">首先， `popup.html` 使用显示标题和按钮的一些直接向前标记更新你的文件。</span><span class="sxs-lookup"><span data-stu-id="0150e-115">First, update your `popup.html` file with some straight forward markup that displays a title and a button.</span></span>  <span data-ttu-id="0150e-116">你将很快对该按钮进行编程，但现在，只需包含对空 JavaScript 文件的引用 `popup.js` 。</span><span class="sxs-lookup"><span data-stu-id="0150e-116">You will program that button shortly, but for now, just include a reference to an empty JavaScript file `popup.js`.</span></span>  <span data-ttu-id="0150e-117">下面是更新 HTML。</span><span class="sxs-lookup"><span data-stu-id="0150e-117">Here is update HTML.</span></span>  

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

<span data-ttu-id="0150e-118">更新您的扩展并选择 "扩展启动" 图标后，"具有以下弹出窗口" 包含 "显示" 按钮。</span><span class="sxs-lookup"><span data-stu-id="0150e-118">After updating your Extension and selecting the Extension launch icon, the have the following pop-up includes a display button.</span></span>  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="按下 "扩展" 图标后，popup.html 显示":::
   <span data-ttu-id="0150e-120">按下 "扩展" 图标后，popup.html 显示</span><span class="sxs-lookup"><span data-stu-id="0150e-120">popup.html display after pressing the Extension icon</span></span>
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

## <span data-ttu-id="0150e-121">在浏览器选项卡顶部显示图像的已更新策略</span><span class="sxs-lookup"><span data-stu-id="0150e-121">Updated strategy to display image at the top of the browser tab</span></span>  

<span data-ttu-id="0150e-122">添加按钮后，下一任务是使其 `images/stars.jpeg` 在活动选项卡页顶部打开图像文件。</span><span class="sxs-lookup"><span data-stu-id="0150e-122">After adding the button, the next task is to make it bring up the `images/stars.jpeg` image file at the top of the active tab page.</span></span>  

<span data-ttu-id="0150e-123">请记住，每个选项卡页都具有唯一的线程，并且扩展具有单独的线程。</span><span class="sxs-lookup"><span data-stu-id="0150e-123">Remember, each tab page has a unique own thread and the Extension has a separate thread.</span></span>  <span data-ttu-id="0150e-124">因此，必须首先创建内容脚本，并将该内容脚本插入到选项卡页中。</span><span class="sxs-lookup"><span data-stu-id="0150e-124">So, you must first create a content script and inject that content script into the tab page.</span></span>  <span data-ttu-id="0150e-125">执行此操作后，你必须从弹出窗口发送一条消息，告知该内容脚本在选项卡页上运行，指示内容脚本要显示的图像以及如何显示。</span><span class="sxs-lookup"><span data-stu-id="0150e-125">Once you do that, you must send a message from your pop-up to that content script running on the tab page telling that content script what image to show, and how to show it.</span></span>  

## <span data-ttu-id="0150e-126">创建弹出 JavaScript 以发送消息</span><span class="sxs-lookup"><span data-stu-id="0150e-126">Creating the pop-up JavaScript to send a message</span></span>  

<span data-ttu-id="0150e-127">首先，创建 `popup/popup.js` 并添加代码，以便向尚未创建的内容脚本发送邮件，您必须立即创建并插入到浏览器选项卡。 为此，以下代码将 `onclick` 事件添加到弹出的 "显示" 按钮。</span><span class="sxs-lookup"><span data-stu-id="0150e-127">First, create `popup/popup.js` and add code to send a message to your not-yet-created content script that you must momentarily create and inject into your browser tab.  To do that, the following code adds an `onclick` event to your pop-up display button.</span></span>  

```javascript
const sendMessageId = document.getElementById("sendmessageid");
if (sendMessageId) {
  sendMessageId.onclick = function() {
    // do something
  };
}
```  

<span data-ttu-id="0150e-128">在此 `onclick` 事件中，你必须执行的操作是查找当前浏览器选项卡 \ (如果只有一个打开的浏览器选项卡，则它是一个 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="0150e-128">In the `onclick` event, what you must do is find the current browser tab \(if there is only one open it is that one\).</span></span>  <span data-ttu-id="0150e-129">然后，找到该选项卡后，使用 `chrome.tabs.sendmessage` 扩展 API 将消息发送到该选项卡。</span><span class="sxs-lookup"><span data-stu-id="0150e-129">Then, once you find that tab, use the `chrome.tabs.sendmessage` Extension API to send a message to that tab.</span></span>  

<span data-ttu-id="0150e-130">在该消息中，你必须包含要显示的图像的 URL，并且你希望发送应分配给插入的图像的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="0150e-130">In that message you must include the URL to the image you want to display, and you want to send a unique ID that should be assigned to that inserted image.</span></span>  <span data-ttu-id="0150e-131">你可以选择让内容插入 JavaScript 生成该内容，但对于稍后变得明显的原因，在此处生成唯一 ID `popup.js` 并将其传递给尚未创建的内容脚本。</span><span class="sxs-lookup"><span data-stu-id="0150e-131">You may choose to let the content insertion JavaScript generate that, but for reasons that become apparent later, generate that unique ID here in `popup.js` and pass it to the not-yet-created content script.</span></span>  

<span data-ttu-id="0150e-132">下面是您的更新 `popup/popup.js` 文件。</span><span class="sxs-lookup"><span data-stu-id="0150e-132">Here is your updated `popup/popup.js` file.</span></span>  <span data-ttu-id="0150e-133">此外，还不会使用您在后面的部分中应该需要的当前选项卡 ID。</span><span class="sxs-lookup"><span data-stu-id="0150e-133">Also, pass in the current tab ID which you should need in a later section but for now, is not be used.</span></span>  

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

## <span data-ttu-id="0150e-134">用任何浏览器选项卡提供 jpeg。</span><span class="sxs-lookup"><span data-stu-id="0150e-134">Making your stars.jpeg available from any browser tab</span></span>  

<span data-ttu-id="0150e-135">你可能会想知道，在传递时 `images/stars.jpeg` 必须使用 `chrome.extension.getURL` CHROME 扩展 API，而不是仅在没有额外前缀的情况下传递相对 URL，如上一节中所示。</span><span class="sxs-lookup"><span data-stu-id="0150e-135">You are probably wondering why, when you pass the `images/stars.jpeg` must you use the `chrome.extension.getURL` chrome Extension API instead of just passing in the relative URL without the extra prefix like in the previous section.</span></span>  <span data-ttu-id="0150e-136">顺便说一下，附加的前缀由附加的 `getUrl` 图像所返回，其外观类似于以下内容。</span><span class="sxs-lookup"><span data-stu-id="0150e-136">By the way, that extra prefix, returned by `getUrl` with the image attached looks something like the following.</span></span>  

```http
extension://inigobacliaghocjiapeaaoemkjifjhp/images/stars.jpeg
```  

<span data-ttu-id="0150e-137">原因是使用元素的属性将图像插入 `src` `img` 内容页面。</span><span class="sxs-lookup"><span data-stu-id="0150e-137">The reason is that you are injecting the image using the `src` attribute of the `img` element into the content page.</span></span>  <span data-ttu-id="0150e-138">内容页面在与运行扩展的线程不同的唯一线程上运行。</span><span class="sxs-lookup"><span data-stu-id="0150e-138">The content page is running on a unique thread that is not the same as the thread running the Extension.</span></span>  <span data-ttu-id="0150e-139">必须将静态图像文件作为 web 资产公开才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="0150e-139">You must expose the static image file as a web asset for it to work correctly.</span></span>  

<span data-ttu-id="0150e-140">若要执行此操作，必须在文件中添加其他条目 `manifest.json` 。</span><span class="sxs-lookup"><span data-stu-id="0150e-140">To do that, you must add another entry in the `manifest.json` file.</span></span>  <span data-ttu-id="0150e-141">必须声明可从任何浏览器选项卡访问的图像。 该条目如下所示 \ (`manifest.json` 当您添加即将出现的内容脚本声明时，请在下面的完整文件中看到该条目： \ ) 。</span><span class="sxs-lookup"><span data-stu-id="0150e-141">You must declare the image to be accessible from any browser tab.  That entry is as follows \(you should see it in the full `manifest.json` file below when you add the content script declaration coming up\).</span></span>  

```json
"web_accessible_resources": [
    "images/*.jpeg"
]
```  

<span data-ttu-id="0150e-142">现在，你已在文件中写入代码 `popup.js` ，以便向嵌入当前活动选项卡页上的内容页发送消息，但尚未创建和注入该内容页面。</span><span class="sxs-lookup"><span data-stu-id="0150e-142">You have now written the code in your `popup.js` file to send a message to the content page that is embedded on the current active tab page, but you have not created and injected that content page.</span></span>  <span data-ttu-id="0150e-143">立即执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0150e-143">Do that now.</span></span>  

## <span data-ttu-id="0150e-144">更新内容和 web 访问的 manifest.js</span><span class="sxs-lookup"><span data-stu-id="0150e-144">Updating your manifest.json for content and web access</span></span>  

<span data-ttu-id="0150e-145">`manifest.json`包括的和的更新 `content-scripts` `web_accessible_resources` 如下所示。</span><span class="sxs-lookup"><span data-stu-id="0150e-145">The updated `manifest.json` that includes the `content-scripts` and `web_accessible_resources` is as follows.</span></span>  

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

<span data-ttu-id="0150e-146">你添加的分区是 `content_scripts` 。</span><span class="sxs-lookup"><span data-stu-id="0150e-146">The section you added is `content_scripts`.</span></span>  <span data-ttu-id="0150e-147">属性 `matches` 设置为 `<all_urls>` 表示在加载每个文件时，" **content_scripts** " 部分中提及的所有文件都插入到所有浏览器选项卡页面中。</span><span class="sxs-lookup"><span data-stu-id="0150e-147">The attribute `matches` set to `<all_urls>` means that all the files mention in the **content_scripts** section is injected into all browser tab pages when each are loaded.</span></span>  <span data-ttu-id="0150e-148">可在此处注入的允许文件类型有 javascript 和 css。</span><span class="sxs-lookup"><span data-stu-id="0150e-148">The allowable types of files that are able to be injected here are javascript and css.</span></span>  <span data-ttu-id="0150e-149">您还添加了 `libjquery.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="0150e-149">You also added `libjquery.min.js`.</span></span>  <span data-ttu-id="0150e-150">你可以从本部分顶部提及的下载中包含该内容。</span><span class="sxs-lookup"><span data-stu-id="0150e-150">You are able to include that from the download mentioned at the top of the section.</span></span>  

## <span data-ttu-id="0150e-151">添加 jQuery 并了解关联的线程</span><span class="sxs-lookup"><span data-stu-id="0150e-151">Adding jQuery and understanding the associated thread</span></span>  

<span data-ttu-id="0150e-152">在您要插入的内容脚本中，请使用 jQuery \ (`$` \ ) 进行计划。</span><span class="sxs-lookup"><span data-stu-id="0150e-152">In the content scripts you are injecting, plan on using jQuery \(`$`\).</span></span>  <span data-ttu-id="0150e-153">你添加了一个 minified 版本的 jQuery，并将其放入你的扩展程序包中 `lib\jquery.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="0150e-153">You added a minified version of jQuery and put it in your Extension package as `lib\jquery.min.js`.</span></span>  <span data-ttu-id="0150e-154">这些内容脚本在排序的单个沙箱中运行，这意味着插入到页面中的 jQuery 不 `popup.js` 会与内容共享。</span><span class="sxs-lookup"><span data-stu-id="0150e-154">These content scripts run in an individual sandbox of sorts, which means that the jQuery injected into the `popup.js` page does not share with the content.</span></span>  

<span data-ttu-id="0150e-155">请记住，即使浏览器选项卡在加载的网页上运行了 JavaScript，任何插入的内容都不具有访问权限。</span><span class="sxs-lookup"><span data-stu-id="0150e-155">Keep in mind that even if the browser tab has JavaScript running on it on the loaded web page, any content injected does not have access to that.</span></span>  <span data-ttu-id="0150e-156">所注入的 JavaScript 只对在该浏览器选项卡中加载的实际 DOM 具有访问权限。</span><span class="sxs-lookup"><span data-stu-id="0150e-156">That injected JavaScript just has access to the actual DOM loaded in that browser tab.</span></span>  

## <span data-ttu-id="0150e-157">添加内容脚本消息侦听器</span><span class="sxs-lookup"><span data-stu-id="0150e-157">Adding the content script message listener</span></span>  

<span data-ttu-id="0150e-158">此处是 `content-scripts\content.js` 基于你的分区将其插入到每个浏览器选项卡页中的文件 `manifest.json` `content-scripts` 。</span><span class="sxs-lookup"><span data-stu-id="0150e-158">Here is that `content-scripts\content.js` file that gets injected into every browser tab page based on your `manifest.json` `content-scripts` section.</span></span>  

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

<span data-ttu-id="0150e-159">请注意，上述所有 JavaScript 都是 `listener` 使用 `chrome.runtime.onMessage.addListener` 扩展 API 方法注册 a。</span><span class="sxs-lookup"><span data-stu-id="0150e-159">Notice that all the above JavaScript does is to register a `listener` using the `chrome.runtime.onMessage.addListener` Extension API method.</span></span>  <span data-ttu-id="0150e-160">此侦听器将等待你从 `popup.js` 前面介绍的带有扩展 API 方法的消息（如你发送给它的消息） `chrome.tabs.sendMessage` 。</span><span class="sxs-lookup"><span data-stu-id="0150e-160">This listener waits for messages like the one you sent from the `popup.js` described earlier with the `chrome.tabs.sendMessage` Extension API method.</span></span>  

<span data-ttu-id="0150e-161">该方法的第一个参数 `addListener` 是一个函数，其第一个参数请求是正在传入的消息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0150e-161">The first parameter of the `addListener` method is a function whose first parameter, request, is the details of the message being passed in.</span></span>  <span data-ttu-id="0150e-162">请记住，在 `popup.js` 使用 `sendMessage` 方法时，第一个参数的这些属性是 `url` 和 `imageDivId` 。</span><span class="sxs-lookup"><span data-stu-id="0150e-162">Remember, from `popup.js`, when you used the `sendMessage` method, those attributes of the first parameter are `url` and `imageDivId`.</span></span>  

<span data-ttu-id="0150e-163">当侦听器处理事件时，将运行第一个参数的函数。</span><span class="sxs-lookup"><span data-stu-id="0150e-163">When an event is processed by the listener, the function that is the first parameter is run.</span></span>  <span data-ttu-id="0150e-164">该函数的第一个参数是具有分配的属性的对象 `sendMessage` 。</span><span class="sxs-lookup"><span data-stu-id="0150e-164">The first parameter of that function is an object that has attributes as assigned by `sendMessage`.</span></span>  <span data-ttu-id="0150e-165">该函数只处理三个 jQuery 脚本行。</span><span class="sxs-lookup"><span data-stu-id="0150e-165">That function simply processes the three jQuery script lines.</span></span>  

*   <span data-ttu-id="0150e-166">第一次动态地插入到 DOM 标头中 **\<style\>** 必须作为 `slide-image` 类分配给你的元素的部分 `img` 。</span><span class="sxs-lookup"><span data-stu-id="0150e-166">The first dynamically inserts into the DOM header a **\<style\>** section that you must assign as a `slide-image` class to your `img` element.</span></span>  
*   <span data-ttu-id="0150e-167">第二个元素将在 " `img` 浏览器" 选项卡的下方附加一个元素， `body` 该选项卡具有 `slide-image` 指定的类以及 `imageDivId` 作为该图像元素的 ID。</span><span class="sxs-lookup"><span data-stu-id="0150e-167">The second, appends an `img` element right below the `body` of your browser tab that has the `slide-image` class assigned as well as the `imageDivId` as the ID of that image element.</span></span>  
*   <span data-ttu-id="0150e-168">第三个示例添加一个 `click` 事件，其中包含整个图像，允许用户选择图像上的任何位置，并且该图像将从页面 \ (中删除，并且该图像是事件侦听器 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="0150e-168">The third adds a `click` event that covers the entire image allowing the user to select any place on the image and that image is be removed from the page \(along with it is event listener\).</span></span>  

## <span data-ttu-id="0150e-169">添加功能以在选定时删除显示的图像</span><span class="sxs-lookup"><span data-stu-id="0150e-169">Adding functionality to remove the displayed image when selected</span></span>  

<span data-ttu-id="0150e-170">现在，当您浏览到任意页面并选择您的 **扩展名** 图标时，弹出菜单显示如下。</span><span class="sxs-lookup"><span data-stu-id="0150e-170">Now, when you browse to any page and select your **Extension** icon, the pop-up menu is displayed as follows.</span></span>  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="按下 "扩展" 图标后，popup.html 显示":::
   <span data-ttu-id="0150e-172">按下 "扩展" 图标后，popup.html 显示</span><span class="sxs-lookup"><span data-stu-id="0150e-172">popup.html display after pressing the Extension icon</span></span>
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

<span data-ttu-id="0150e-173">选择该按钮后 `Display` ，将获得以下内容。</span><span class="sxs-lookup"><span data-stu-id="0150e-173">When you select the `Display` button, you get what is below.</span></span>  <span data-ttu-id="0150e-174">如果选择图像上的任意位置 `stars.jpeg` ，则会删除该图像元素，并且选项卡页将折叠为最初显示的内容。</span><span class="sxs-lookup"><span data-stu-id="0150e-174">If you select anywhere on the `stars.jpeg` image, that image element is removed and tab pages collapses back to what was originally displayed.</span></span>  

:::image type="complex" source="./media/part2-showingimage.png" alt-text="浏览器中显示的图像":::
   <span data-ttu-id="0150e-176">浏览器中显示的图像</span><span class="sxs-lookup"><span data-stu-id="0150e-176">The image showing in browser</span></span>
:::image-end:::

<!--![The image showing in browser][ImagePart2Showingimage]  -->  

<span data-ttu-id="0150e-177">现在，你已创建了一个可成功将消息从 "扩展" 图标弹出窗口发送到 "浏览器" 选项卡上作为内容运行的动态插入的 JavaScript 的扩展。 这一插入的内容设置了 image 元素，以显示您的静态星 jpeg。</span><span class="sxs-lookup"><span data-stu-id="0150e-177">You have now created an Extension that successfully sends a message from the Extension icon pop-up, to the dynamically inserted JavaScript running as content on the browser tab.  That injected content set the image element to display your static stars jpeg.</span></span>  

<!-- image links -->  

<!--[ImagePart2Popupdialog]: ./media/part2-popupdialog.png "popup.html display after pressing the Extension icon"  -->  
<!--[ImagePart2Showingimage]: ./media/part2-showingimage.png "The image showing in browser"  -->

<!-- links -->  

[ArchiveExtensionGettingStartedPart2]: ./extension-source/extension-getting-started-part2.zip "已完成此部件的扩展程序包源 |Microsoft 文档"  
