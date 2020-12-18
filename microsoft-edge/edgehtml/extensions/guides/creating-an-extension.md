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
# 创建 Microsoft Edge 扩展  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

在本指南中，了解如何为 Microsoft Edge 创建扩展。  此示例扩展允许你操作特定 CSS [docs.microsoft.com页面][MicrosoftDocs] ，包括浏览清单文件、用户界面以及背景和内容脚本的创建过程。  

:::image type="complex" source="../media/color-changer_header.png" alt-text="Docs.microsoft.com正文更改为蓝色":::
   Docs.microsoft.com正文更改为蓝色
:::image-end:::

<!--![Docs.microsoft.com body changed to blue][ImageColorChangerHeader]  -->  

本教程假定你基本了解什么是浏览器扩展及其工作。  有关扩展构建基块的更多信息，请参阅扩展 [结构][MDNAnatomyExtension]。  

在 [GitHub 上下载完整示例的代码][GithubMicrosoftEdgeExtensionsDemosColorChanger]。  

## 生成清单文件  

若要开始，请为扩展创建一个目录，并命名它 `color-changer` 。  

在文件夹 `color-changer` 内，创建一个名为 `manifest.json` .  该文件是所有扩展的必需文件，并提供扩展名的重要信息，范围从扩展名到 `manifest.json` 权限。  

> [!NOTE] 
> 本指南将指导你完成本指南中必须使用的所有清单密钥，但有关所有受支持和推荐的清单密钥的列表，请参阅支持的 [清单密钥][ExtensionsApisupportManifestKeys]。  

在 `manifest.json` 内部，添加以下代码。  

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

### 清单键定义  

| 密钥 | 详细信息 |  
|:--- |:--- |  
| [name][MDNManifestjsonName] | 扩展名。  |  
| [author][MDNManifestjsonAuthor] | 扩展的作者。  |  
| [version][MDNManifestjsonVersion] | 分机号码。  |  
| [description][MDNManifestjsonDescription] | Microsoft Edge 扩展菜单的"关于"部分中显示的扩展说明。  |  
| [permissions][MDNManifestjsonPermissions] | 请求扩展权限的字符串数组。  对于扩展，你正在请求查看访问的网站的权限 ("tabs"\) 并更新与""匹配的 URL `*://docs.microsoft.com/*` 上的内容。  |  
| [browser_action][MDNManifestjsonBrowserAction] | 包含图标的信息。 该图标放置在 Microsoft Edge 工具栏上的地址栏右侧。  |  

#### browser_action关键定义  

| 密钥 | 详细信息 |  
|:--- |:--- |  
| `default_icon` | 工具栏中使用的图标。  |  
| `default_title` | 当用户将鼠标悬停在工具栏中的图标上时显示的文本。  |  
| `default_popup` | 弹出窗口的 HTML 文件的路径。  |  

现在，你已创建清单文件，你需要一个扩展的用户界面。  

## 创建弹出窗口  

对于扩展，请为用户界面创建弹出窗口，如下所示。  

:::image type="complex" source="../media/color-changer_popup.png" alt-text="扩展的弹出界面":::
   扩展的弹出界面
:::image-end:::

<!--![The pop-up interface of the extension][ImageColorChangerPopup]  -->  

在文件夹 `popup.html` 的根目录下创建一个名为 `color-changer` 的文件。  将以下代码粘贴到 `popup.html` 。  

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

In `popup.html` ， you create a title， a paragraph， and three buttons \ (Aliceblue， Alicesilk， and Reset\) .  

现在创建一个名为的文件夹 `css` ，在内部创建一个名为 `styles.css` .  添加下面的样式。  

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

此 CSS 为扩展提供了一些基本样式。  可随意添加更多样式以自定义扩展。  

接下来，必须创建与弹出窗口交互的 JavaScript 文件。  创建 `js` 一个文件夹和一个名为内部 `popup.js` 的文件。  使用 `popup.js` 以下代码更新。  

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

在 `popup.js` 选项卡[][MDNApiTabs]API 中，你可以与浏览器的选项卡进行交互，将脚本和样式注入页面内容。  使用 [tabs.insertCSS () ][MDNApiTabsInsertcss] 方法，将指定的 CSS 注入页面，当单击指定按钮时，该页面将 [docs.microsoft.com][MicrosoftDocs] 上的页眉更改为其他颜色。  

现在你已拥有基本的弹出功能，请向扩展中添加图标。  

## 添加图标  

图标用于表示浏览器工具栏、扩展菜单和其他位置中的扩展。  在 [GitHub 上下载扩展图标][GithubMicrosoftEdgeExtensionsDemosColorChangerImages]。 有关 Microsoft Edge 中的扩展图标详细信息，请参阅设计 [指南][ExtensionsGuidesDesignIcons]。  

下载扩展图标后，将图标保存在 `images` 内部文件夹中 `color-changer` 。  

工具栏中显示的图标使用已添加到清单文件的browser_action项内部 `default_icon` 进行[][MDNManifestjsonBrowserAction]设置。  

该 `icons` 键定义应在扩展设置菜单中使用哪些图标。  下面，你将指定多个大小不同的图标，以考虑不同的屏幕分辨率。  图标的名称，是图标的高度 `25` `48` （以像素为单位）。  

在 [manifest.js文件中][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] ，包括一个顶级键 `icons` 。  

```json
  "icons": {
    "25": "images/color-changer25.png",
    "48": "images/color-changer48.png"
  }
```  

### 清单密钥定义  

| 密钥 | 详细信息 |  
|:--- |:--- |  
| [图标][MDNManifestjsonIcons] | 扩展的图标，其键值对表示图像大小，图像路径与扩展的根目录 `px` 相对。 |  

> [!NOTE]
> 使用本指南稍后 `inactive##.png` 在 images 文件夹中命名的图标。  

## 测试扩展  

现在，你已添加用户界面并创建了图标，请测试扩展。  演练向 Microsoft [][ExtensionsGuidesAddingRemovingExtensionsAdding] Edge 添加扩展的步骤。  之后，返回到本指南。  

添加扩展后，导航 [到任何docs.microsoft.com][MicrosoftDocs] 页面。  单击浏览器操作后，应该会看到以下弹出窗口。  正文的颜色 [docs.microsoft.com][MicrosoftDocs] 更改颜色。  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_aliceblue.png" alt-text="Docs.microsoft.com头更改为 Aliceblue":::
         Docs.microsoft.com头更改为 Aliceblue :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Aliceblue][ImageColorChangerHeaderAliceblue]  -->
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_cornsilk.png" alt-text="Docs.microsoft.com头更改为"一角"":::
         Docs.microsoft.com头更改为"一角" :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Cornsilk][ImageColorChangerHeaderCornsilk]  -->
   :::column-end:::
:::row-end:::

如果遇到任何无法运行的错误或功能，请参阅调试扩展指南或下载[][ExtensionsGuidesDebuggingExtensions] [GitHub 上的完整示例][GithubMicrosoftEdgeExtensionsDemosColorChanger]。  

## 添加内容和后台脚本  

进一步执行一步并添加逻辑以禁止扩展在域外部[docs.microsoft.com运行。][MicrosoftDocs]  

您必须先创建内容 [脚本][MDNContentScripts]。  接下来，您必须创建在特定网页上下文中运行的内容脚本，能够访问网页的内容，并且能够与后台脚本进行通信。  在目录 `js` 内，创建一个名为 `content.js` 并添加以下代码的文件。  

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

此脚本通过此脚本获取当前页面的 URL，并验证当前 `document.location.href` 页面是否位于docs.microsoft.com域中[][MicrosoftDocs]。  如果页面不在 [docs.microsoft.com][MicrosoftDocs] 域 \ (例如 \) 上，则非活动图标 \ (灰显图标\) 的路径使用  [https://www.bing.com/][|::ref1::|] [runtime.sendMessage () 发送到后台脚本 ][MDNApiRuntimeSendmessage]。  

您必须更新manifest.js[ 文件][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] 上的文件，以包含以下 `content_scripts` 键。  

```json
  "content_scripts": [{
    "matches": [
        "<all_urls>"
    ],
    "js": ["js/content.js"],
    "run_at": "document_end"
}]
```  

### 清单密钥定义  

| 密钥 | 详细信息 |  
|:--- |:---- |  
| [content_scripts][MDNManifestjsonContentScripts] | 包含浏览器应加载哪些内容脚本的信息。 |  

#### content_scripts关键定义  

| 密钥 | 详细信息 |  
|:--- |:---- |  
| `matches` \ (required\)  | 加载内容脚本之前要匹配的 URL 模式。 |  
| `js` | 应在匹配的 URL 上加载的脚本。 |  
| `run_at` | 指定注入密钥中的 JavaScript `js` 文件的位置。 |  

接下来，你必须创建一 [个后台脚本][MDNAnatomyExtensionBackgroundScripts]。  后台脚本在浏览器后台运行，独立于网页或浏览器窗口的生命周期运行，并且能够与内容脚本通信。  

在文件夹 `js` 内，创建一个名为 `background.js` 并添加以下代码的文件。  

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

[runtime.onMessage][MDNApiRuntimeOnmessage]方法侦听内容脚本中的[runtime.sendMessage () 。][MDNApiRuntimeSendmessage]  如果页面的域未[docs.microsoft.com，][MicrosoftDocs][则 browserAction.setIcon () ][MDNApiBrowseractionSeticon]方法将图标路径设置为非活动图像。  

该脚本还禁用浏览器操作 \ ([browserAction.disable][MDApiBrowseractionDisable]\) ，以便用户无法单击 docs.microsoft.com 页面之外的 [浏览器][MicrosoftDocs] 操作。  

必须将后台脚本添加到文件上的 [manifest.js脚本][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] 。  将以下 `background` 项添加到清单。  

```json
"background": {
    "scripts": ["js/background.js"],
    "persistent": true
  }
```  

### 清单密钥定义  

| 密钥 | 详细信息|  
|:--- |:--- |  
| [背景][MDNManifestjsonBackground] | 包含后台脚本。 |  

#### 后台键定义  

| 密钥 | 详细信息 |  
|:--- |:--- |  
| `scripts` | JavaScript 文件的路径。 |  
| `persistent` （必需） | 这必须设置为或 `true` `false` 。  如果设置为 `true` ，则加载后台脚本并保留整个浏览部分。  如果设置为 `false` ，后台脚本加载延迟，并保留浏览会话。 |  

重新加载扩展并再次测试。  若要重新加载扩展：在 Microsoft Edge 中单击 **...** 设置等，**** 单击"扩展 **"，单击**扩展 \ ("颜色更改器"\) ，然后单击"重新加载**扩展"。**  

现在，打开一个新选项卡，或刷新一个不是当前页面docs.microsoft.com[选项卡。][MicrosoftDocs]  你应该会看到非活动图标，并且无法单击浏览器操作。  

恭喜你！  你为 Microsoft Edge 创建了扩展！  在 [GitHub 上查看完整示例][GithubMicrosoftEdgeExtensionsDemosColorChanger]。  继续阅读，详细了解扩展。  

## 编写更复杂的扩展  

想要编写更复杂的扩展？  请看一下 MDN 上的Ifyify 扩展，第二个 [扩展][MDNYourSecondWebextension]。  Microsoft Edge 的扩展模型与 Firefox 的扩展模型略有不同，在"第二个扩展[][MDNYourSecondWebextension]"中创建的Ifyify 扩展已调整为在 Microsoft Edge 中运行。  在 [GitHub][GithubMicrosoftEdgeExtensionsDemosBeastify]上查看。  

在阅读 MDN（ [你的][MDNYourSecondWebextension]第二个扩展）上的文章时，请记住以下部分。  

### API  

有关 Microsoft Edge [中受支持的][ExtensionsAPIsupportApis] 扩展 API 的列表，请参阅"受支持的 API"页。  

### 图标大小  

Microsoft Edge 的首选扩展图标大小是 `20px` ， `25px` 和 `30px` `40px` 。  其他支持的大小是 `19px` ， `35px` 和 `38px` 。  有关图标大小和最佳做法详细信息， [请参阅设计指南][ExtensionsGuidesDesign] 。  

### JavaScript  

Microsoft Edge 的扩展模型不支持 JavaScript 承诺。  请改为使用回调。  有关在扩展中使用回调的更多示例，请看一下  [快速打印][GithubMicrosoftEdgeExtensionsDemosQuickPrint] 和 [文本交换][GithubMicrosoftEdgeExtensionsDemosTextSwap] 演示。  

演练以下 [视频中的"快速][GithubMicrosoftEdgeExtensionsDemosQuickPrint] 打印"示例。  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Adding-a-Background-Script-to-you-Edge-Extension/player]  

### Manifest.js打开  

*   该 `author` 密钥在 Microsoft Edge 中是必需的  
*   `activeTab`Microsoft Edge 不支持该密钥  

有关浏览器扩展 [的信息，请参阅][MDNBrowserExtensions] [MDN Web 文档][MDNWebDocs]。  

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
