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
# 创建 Microsoft Edge 扩展  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

在本指南中，了解如何创建 Microsoft Edge 的扩展。  此示例扩展使你可以操作 [docs.microsoft.com][MicrosoftDocs] 页面的特定 CSS，包括创建清单文件、用户界面以及后台和内容脚本。  

:::image type="complex" source="../media/color-changer_header.png" alt-text="Docs.microsoft.com 正文已更改为蓝色":::
   Docs.microsoft.com 正文已更改为蓝色
:::image-end:::

<!--![Docs.microsoft.com body changed to blue][ImageColorChangerHeader]  -->  

本教程假定你对浏览器扩展的定义和工作原理有基本的理解。  有关扩展的构建基块的详细 imformation，请参阅 [扩展的剖析][MDNAnatomyExtension]。  

下载 [GitHub 上的完整示例][GithubMicrosoftEdgeExtensionsDemosColorChanger]的代码。  

## 生成清单文件  

首先，为您的扩展名创建一个目录并为其命名 `color-changer` 。  

在 `color-changer` 文件夹内创建一个名为 `manifest.json` 的文件。  `manifest.json`文件对所有扩展名都是必需的，并提供扩展的重要信息，范围从扩展名称到权限。  

> [!NOTE] 
> 本指南将引导你完成必须在本指南中使用的所有清单键，但要查看所有受支持和推荐的清单键的列表，请参阅 [支持的清单键][ExtensionsApisupportManifestKeys]。  

在 `manifest.json` &quot;内部&quot; 中，添加以下代码。  

```json
{
  &quot;name&quot;: &quot;Color Changer&quot;,
  &quot;author&quot;: &quot;Microsoft Edge Extension Developer&quot;,
  &quot;version&quot;: &quot;1.0&quot;,
  &quot;description&quot;: &quot;Change the color of the body on docs.microsoft.com&quot;,
  &quot;permissions&quot;: [
    &quot;*://docs.microsoft.com/*&quot;,
    &quot;tabs&quot;
  ], 
  &quot;browser_action&quot;: {
    &quot;default_icon&quot;: {
      &quot;20&quot;: &quot;images/color-changer20.png&quot;,
      &quot;40&quot;: &quot;images/color-changer40.png&quot;
    },
    &quot;default_title&quot;: &quot;Color Changer&quot;,
    &quot;default_popup&quot;: &quot;popup.html&quot;
  }
}
```  

### 清单键定义  

| 密钥 | 详细信息 |  
|:--- |:--- |  
| [name][MDNManifestjsonName] | 扩展的名称。  |  
| [授权][MDNManifestjsonAuthor] | 扩展的作者。  |  
| [version][MDNManifestjsonVersion] | 分机版本号。  |  
| [description][MDNManifestjsonDescription] | Microsoft Edge 中 &quot;扩展&quot; 菜单的 &quot;关于&quot; 部分中显示的扩展的说明。  |  
| [授权][MDNManifestjsonPermissions] | 请求扩展的权限的字符串数组。  对于您的扩展，您正在请求查看访问过的网站 ( &quot;选项卡&quot; \ ) 并更新与 &quot;&quot; 匹配的 Url 上的内容 `*://docs.microsoft.com/*` 。  |  
| [browser_action][MDNManifestjsonBrowserAction] | 包含图标的信息。 图标位于 &quot;Microsoft Edge&quot; 工具栏上的 &quot;地址" 栏右侧。  |  

#### browser_action 键定义  

| 密钥 | 详细信息 |  
|:--- |:--- |  
| `default_icon` | 工具栏中使用的图标。  |  
| `default_title` | 当用户将鼠标悬停在工具栏中的图标上时显示的文本。  |  
| `default_popup` | 弹出窗口的 HTML 文件的路径。  |  

现在，你已创建清单文件，你需要一个用于扩展的用户界面。  

## 创建弹出窗口  

对于您的扩展，请为用户界面创建一个弹出窗口，如下所示。  

:::image type="complex" source="../media/color-changer_popup.png" alt-text="Docs.microsoft.com 正文已更改为蓝色":::
   Docs.microsoft.com 正文已更改为蓝色
:::image-end:::

<!--![Docs.microsoft.com body changed to blue][ImageColorChangerHeader]  -->  

本教程假定你对浏览器扩展的定义和工作原理有基本的理解。  有关扩展的构建基块的详细 imformation，请参阅 [扩展的剖析][MDNAnatomyExtension]。  

下载 [GitHub 上的完整示例][GithubMicrosoftEdgeExtensionsDemosColorChanger]的代码。  

## 生成清单文件  

首先，为您的扩展名创建一个目录并为其命名 `color-changer` 。  

在 `color-changer` 文件夹内创建一个名为 `manifest.json` 的文件。  `manifest.json`文件对所有扩展名都是必需的，并提供扩展的重要信息，范围从扩展名称到权限。  

> [!NOTE] 
> 本指南将引导你完成必须在本指南中使用的所有清单键，但要查看所有受支持和推荐的清单键的列表，请参阅 [支持的清单键][ExtensionsApisupportManifestKeys]。  

在 `manifest.json` &quot;内部&quot; 中，添加以下代码。  

```json
{
  &quot;name&quot;: &quot;Color Changer&quot;,
  &quot;author&quot;: &quot;Microsoft Edge Extension Developer&quot;,
  &quot;version&quot;: &quot;1.0&quot;,
  &quot;description&quot;: &quot;Change the color of the body on docs.microsoft.com&quot;,
  &quot;permissions&quot;: [
    &quot;*://docs.microsoft.com/*&quot;,
    &quot;tabs&quot;
  ], 
  &quot;browser_action&quot;: {
    &quot;default_icon&quot;: {
      &quot;20&quot;: &quot;images/color-changer20.png&quot;,
      &quot;40&quot;: &quot;images/color-changer40.png&quot;
    },
    &quot;default_title&quot;: &quot;Color Changer&quot;,
    &quot;default_popup&quot;: &quot;popup.html&quot;
  }
}
```  

### 清单键定义  

| 密钥 | 详细信息 |  
|:--- |:--- |  
| [name][MDNManifestjsonName] | 扩展的名称。  |  
| [授权][MDNManifestjsonAuthor] | 扩展的作者。  |  
| [version][MDNManifestjsonVersion] | 分机版本号。  |  
| [description][MDNManifestjsonDescription] | Microsoft Edge 中 &quot;扩展&quot; 菜单的 &quot;关于&quot; 部分中显示的扩展的说明。  |  
| [授权][MDNManifestjsonPermissions] | 请求扩展的权限的字符串数组。  对于您的扩展，您正在请求查看访问过的网站 ( &quot;选项卡&quot; \ ) 并更新与 &quot;&quot; 匹配的 Url 上的内容 `*://docs.microsoft.com/*` 。  |  
| [browser_action][MDNManifestjsonBrowserAction] | 包含图标的信息。 图标位于 &quot;Microsoft Edge&quot; 工具栏上的 &quot;地址":::
   扩展的弹出界面
:::image-end:::

<!--![The pop-up interface of the extension][ImageColorChangerPopup]  -->  

`popup.html`在文件夹的根目录中创建一个名为的文件 `color-changer` 。  将以下代码粘贴到中 `popup.html` 。  

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

在中 `popup.html` ，你可以创建标题、段落和三个按钮 \ (Aliceblue、Cornsilk 和 Reset \ ) 。  

现在创建一个名为 `css` 和内部的文件夹，创建一个名为 `styles.css` 的文件。  在下方添加样式。  

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

此 CSS 为我们的扩展提供了一些基本样式。  可随意添加更多样式以自定义您的扩展。  

接下来，你必须创建与弹出窗口交互的 JavaScript 文件。  创建一个 `js` 文件夹和一个名为 "内部" 的文件 `popup.js` 。  `popup.js`具有以下代码的更新。  

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

在中 `popup.js` ， [选项卡][MDNApiTabs] API 允许你与浏览器的选项卡交互，并将脚本和样式插入页面内容。  使用 [insertCSS ( # B1 ][MDNApiTabsInsertcss] 方法，你可以将指定的 CSS 插入页面，在单击指定的按钮时，该页面会将 [docs.microsoft.com][MicrosoftDocs] 的标题更改为另一种颜色。  

既然你已拥有基本的弹出功能，请将图标添加到扩展。  

## 添加图标  

图标用于表示浏览器工具栏、"扩展" 菜单和其他位置中的扩展。  下载 [GitHub 上的扩展的图标][GithubMicrosoftEdgeExtensionsDemosColorChangerImages]。 有关 Microsoft Edge 中的扩展图标的详细信息，请参阅 [设计指南][ExtensionsGuidesDesignIcons]。  

下载扩展图标后，将图标保存在中的某个 `images` 文件夹中 `color-changer` 。  

工具栏中显示的图标是使用 `default_icon` [browser_action][MDNManifestjsonBrowserAction] 项的内部设置的，你已在前面的部分中添加到清单文件。  

`icons`该键定义 "扩展" 设置菜单中应使用的图标。  在以下情况下，你将指定具有不同大小的多个图标以用于不同的屏幕分辨率。  图标的名称， `25` `48` 是图标的高度（以像素为单位）。  

在 " [manifest.js"][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] 文件中，包括的顶级键 `icons` 。  

```json
  "icons": {
    "25": "images/color-changer25.png",
    "48": "images/color-changer48.png"
  }
```  

### 清单键定义  

| 密钥 | 详细信息 |  
|:--- |:--- |  
| [图标][MDNManifestjsonIcons] | 您的扩展的图标，其中包含图像大小的键/值对 `px` 以及相对于扩展根目录的图像路径。 |  

> [!NOTE]
> 使用 `inactive##.png` 本指南后面的 "图像" 文件夹中指定的图标。  

## 测试扩展  

现在，你已添加了用户界面并创建了图标，请测试你的扩展。  演练 [将扩展添加][ExtensionsGuidesAddingRemovingExtensionsAdding] 到 Microsoft Edge 的步骤。  之后，请返回本指南。  

添加扩展后，导航到任何 [docs.microsoft.com][MicrosoftDocs] 页面。  单击浏览器操作后，您应看到以下弹出窗口。  [Docs.microsoft.com][MicrosoftDocs]主体的颜色也应更改颜色。  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_aliceblue.png" alt-text="Docs.microsoft.com 正文已更改为蓝色":::
   Docs.microsoft.com 正文已更改为蓝色
:::image-end:::

<!--![Docs.microsoft.com body changed to blue][ImageColorChangerHeader]  -->  

本教程假定你对浏览器扩展的定义和工作原理有基本的理解。  有关扩展的构建基块的详细 imformation，请参阅 [扩展的剖析][MDNAnatomyExtension]。  

下载 [GitHub 上的完整示例][GithubMicrosoftEdgeExtensionsDemosColorChanger]的代码。  

## 生成清单文件  

首先，为您的扩展名创建一个目录并为其命名 `color-changer` 。  

在 `color-changer` 文件夹内创建一个名为 `manifest.json` 的文件。  `manifest.json`文件对所有扩展名都是必需的，并提供扩展的重要信息，范围从扩展名称到权限。  

> [!NOTE] 
> 本指南将引导你完成必须在本指南中使用的所有清单键，但要查看所有受支持和推荐的清单键的列表，请参阅 [支持的清单键][ExtensionsApisupportManifestKeys]。  

在 `manifest.json` &quot;内部&quot; 中，添加以下代码。  

```json
{
  &quot;name&quot;: &quot;Color Changer&quot;,
  &quot;author&quot;: &quot;Microsoft Edge Extension Developer&quot;,
  &quot;version&quot;: &quot;1.0&quot;,
  &quot;description&quot;: &quot;Change the color of the body on docs.microsoft.com&quot;,
  &quot;permissions&quot;: [
    &quot;*://docs.microsoft.com/*&quot;,
    &quot;tabs&quot;
  ], 
  &quot;browser_action&quot;: {
    &quot;default_icon&quot;: {
      &quot;20&quot;: &quot;images/color-changer20.png&quot;,
      &quot;40&quot;: &quot;images/color-changer40.png&quot;
    },
    &quot;default_title&quot;: &quot;Color Changer&quot;,
    &quot;default_popup&quot;: &quot;popup.html&quot;
  }
}
```  

### 清单键定义  

| 密钥 | 详细信息 |  
|:--- |:--- |  
| [name][MDNManifestjsonName] | 扩展的名称。  |  
| [授权][MDNManifestjsonAuthor] | 扩展的作者。  |  
| [version][MDNManifestjsonVersion] | 分机版本号。  |  
| [description][MDNManifestjsonDescription] | Microsoft Edge 中 &quot;扩展&quot; 菜单的 &quot;关于&quot; 部分中显示的扩展的说明。  |  
| [授权][MDNManifestjsonPermissions] | 请求扩展的权限的字符串数组。  对于您的扩展，您正在请求查看访问过的网站 ( &quot;选项卡&quot; \ ) 并更新与 &quot;&quot; 匹配的 Url 上的内容 `*://docs.microsoft.com/*` 。  |  
| [browser_action][MDNManifestjsonBrowserAction] | 包含图标的信息。 图标位于 &quot;Microsoft Edge&quot; 工具栏上的 &quot;地址":::
         Docs.microsoft.com 标头已更改为 Aliceblue :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Aliceblue][ImageColorChangerHeaderAliceblue]  -->
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_cornsilk.png" alt-text="Docs.microsoft.com 正文已更改为蓝色":::
   Docs.microsoft.com 正文已更改为蓝色
:::image-end:::

<!--![Docs.microsoft.com body changed to blue][ImageColorChangerHeader]  -->  

本教程假定你对浏览器扩展的定义和工作原理有基本的理解。  有关扩展的构建基块的详细 imformation，请参阅 [扩展的剖析][MDNAnatomyExtension]。  

下载 [GitHub 上的完整示例][GithubMicrosoftEdgeExtensionsDemosColorChanger]的代码。  

## 生成清单文件  

首先，为您的扩展名创建一个目录并为其命名 `color-changer` 。  

在 `color-changer` 文件夹内创建一个名为 `manifest.json` 的文件。  `manifest.json`文件对所有扩展名都是必需的，并提供扩展的重要信息，范围从扩展名称到权限。  

> [!NOTE] 
> 本指南将引导你完成必须在本指南中使用的所有清单键，但要查看所有受支持和推荐的清单键的列表，请参阅 [支持的清单键][ExtensionsApisupportManifestKeys]。  

在 `manifest.json` &quot;内部&quot; 中，添加以下代码。  

```json
{
  &quot;name&quot;: &quot;Color Changer&quot;,
  &quot;author&quot;: &quot;Microsoft Edge Extension Developer&quot;,
  &quot;version&quot;: &quot;1.0&quot;,
  &quot;description&quot;: &quot;Change the color of the body on docs.microsoft.com&quot;,
  &quot;permissions&quot;: [
    &quot;*://docs.microsoft.com/*&quot;,
    &quot;tabs&quot;
  ], 
  &quot;browser_action&quot;: {
    &quot;default_icon&quot;: {
      &quot;20&quot;: &quot;images/color-changer20.png&quot;,
      &quot;40&quot;: &quot;images/color-changer40.png&quot;
    },
    &quot;default_title&quot;: &quot;Color Changer&quot;,
    &quot;default_popup&quot;: &quot;popup.html&quot;
  }
}
```  

### 清单键定义  

| 密钥 | 详细信息 |  
|:--- |:--- |  
| [name][MDNManifestjsonName] | 扩展的名称。  |  
| [授权][MDNManifestjsonAuthor] | 扩展的作者。  |  
| [version][MDNManifestjsonVersion] | 分机版本号。  |  
| [description][MDNManifestjsonDescription] | Microsoft Edge 中 &quot;扩展&quot; 菜单的 &quot;关于&quot; 部分中显示的扩展的说明。  |  
| [授权][MDNManifestjsonPermissions] | 请求扩展的权限的字符串数组。  对于您的扩展，您正在请求查看访问过的网站 ( &quot;选项卡&quot; \ ) 并更新与 &quot;&quot; 匹配的 Url 上的内容 `*://docs.microsoft.com/*` 。  |  
| [browser_action][MDNManifestjsonBrowserAction] | 包含图标的信息。 图标位于 &quot;Microsoft Edge&quot; 工具栏上的 &quot;地址":::
         Docs.microsoft.com 标头已更改为 Cornsilk :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Cornsilk][ImageColorChangerHeaderCornsilk]  -->
   :::column-end:::
:::row-end:::

如果遇到不起作用的任何错误或功能，请参阅 [调试扩展][ExtensionsGuidesDebuggingExtensions] 指南或下载 [GitHub 上的完整示例][GithubMicrosoftEdgeExtensionsDemosColorChanger]。  

## 添加内容和后台脚本  

进一步转到另一步，添加逻辑以禁止扩展在 [docs.microsoft.com][MicrosoftDocs] 域外部工作的页面。  

必须先创建 [内容脚本][MDNContentScripts]。  接下来，必须创建在特定网页的上下文中运行的内容脚本，才能访问网页的内容，并且能够与后台脚本进行通信。  在目录内 `js` 创建一个名为的文件， `content.js` 并添加以下代码。  

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

此脚本将获取当前页面的 URL `document.location.href` ，并验证当前页面是否位于 [docs.microsoft.com][MicrosoftDocs] 域中。  如果页面不在 [docs.microsoft.com][MicrosoftDocs] 域 \ ( [https://www.bing.com/][|::ref1::|] （例如 \ ) ）中，非活动图标 \ (灰显图标 \ ) 的路径将通过运行时 sendMessage 发送到后台脚本。 [ ( # B5 ][MDNApiRuntimeSendmessage]。  

必须更新文件 [ 上的manifest.js][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] 以包含以下 `content_scripts` 注册表项。  

```json
  "content_scripts": [{
    "matches": [
        "<all_urls>"
    ],
    "js": ["js/content.js"],
    "run_at": "document_end"
}]
```  

### 清单键定义  

| 密钥 | 详细信息 |  
|:--- |:---- |  
| [content_scripts][MDNManifestjsonContentScripts] | 包含有关浏览器应加载哪些内容脚本的信息。 |  

#### content_scripts 键定义  

| 密钥 | 详细信息 |  
|:--- |:---- |  
| `matches` \ (必需 \ )  | 加载内容脚本之前要匹配的 URL 模式。 |  
| `js` | 应在匹配的 Url 上加载的脚本。 |  
| `run_at` | 指定插入来自该键的 JavaScript 文件的位置 `js` 。 |  

接下来，必须创建 [后台脚本][MDNAnatomyExtensionBackgroundScripts]。  后台脚本在浏览器的后台运行，独立于网页或浏览器窗口的生命周期运行，并且能够与内容脚本进行通信。  

在您的 `js` 文件夹内创建一个名为的文件， `background.js` 并添加以下代码。  

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

[OnMessage][MDNApiRuntimeOnmessage]方法侦听[运行时。 sendMessage (][MDNApiRuntimeSendmessage]内容脚本中的 # B1。  如果页面的域不是 [docs.microsoft.com][MicrosoftDocs]，则 [BrowserAction ( # B1 ][MDNApiBrowseractionSeticon] 方法将为非活动图像设置图标路径。  

该脚本还会禁用浏览器操作 \ ([browserAction "禁用][MDApiBrowseractionDisable]\ ) "，以便用户无法单击 [docs.microsoft.com][MicrosoftDocs] 页面之外的浏览器操作。  

必须将后台脚本添加到文件 [ 中的manifest.js][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] 。  将以下 `background` 项添加到清单。  

```json
"background": {
    "scripts": ["js/background.js"],
    "persistent": true
  }
```  

### 清单键定义  

| 密钥 | 详细信息|  
|:--- |:--- |  
| [背景][MDNManifestjsonBackground] | 包含后台脚本。 |  

#### 背景键定义  

| 密钥 | 详细信息 |  
|:--- |:--- |  
| `scripts` | JavaScript 文件的路径。 |  
| `persistent` （必需） | 这必须设置为 `true` 或 `false` 。  如果设置为 `true` ，将加载后台脚本并为整个浏览部分保留。  如果设置为 `false` ，将加载后台脚本，并为浏览会话保留延迟。 |  

重新加载扩展并再次测试。  若要重新加载你的扩展，请执行以下操作：单击 " **...** " 查看设置及更多 Microsoft Edge，单击 " **扩展**"，单击 "扩展 \ (**颜色转换器**\ ) "，然后单击 " **重新加载扩展**"。  

现在，打开新的选项卡或刷新不是 [docs.microsoft.com][MicrosoftDocs] 页面的现有选项卡。  你应该会看到 "非活动" 图标，并且无法单击浏览器操作。  

恭喜你！  您已为 Microsoft Edge 创建了一个扩展！  查看 [GitHub 上的完整示例][GithubMicrosoftEdgeExtensionsDemosColorChanger]。  继续阅读，了解有关扩展的详细信息。  

## 编写更复杂的扩展名  

想要编写更复杂的扩展名？  查看文章中 MDN 的 Beastify 扩展，即 [第二个扩展][MDNYourSecondWebextension]。  Microsoft Edge 的扩展模型与 Firefox 的扩展模型略有不同， [您的第二个扩展][MDNYourSecondWebextension] 中创建的 Beastify 扩展在 Microsoft Edge 中的功能。  在 [GitHub][GithubMicrosoftEdgeExtensionsDemosBeastify]上查看。  

在浏览有关 MDN 的 [第二个扩展][MDNYourSecondWebextension]的文章时，请记住以下部分。  

### API  

有关 Microsoft Edge 中支持的扩展 Api 的列表，请参阅 [支持的 api][ExtensionsAPIsupportApis] 页面。  

### 图标大小  

Microsoft Edge 的首选扩展名图标大小为 `20px` 、 `25px` 、 `30px` 和 `40px` 。  其他受支持的大小为 `19px` 、 `35px` 和 `38px` 。  有关图标大小和最佳做法的详细信息，请参阅 [设计][ExtensionsGuidesDesign] 指南。  

### JavaScript  

Microsoft Edge 的扩展模型不支持 JavaScript 承诺。  而是使用回调。  有关在扩展中使用回调的更多示例，请查看 "  [快速打印][GithubMicrosoftEdgeExtensionsDemosQuickPrint] " 和 " [文本交换][GithubMicrosoftEdgeExtensionsDemosTextSwap] " 演示。  

浏览以下视频中的 [快速打印][GithubMicrosoftEdgeExtensionsDemosQuickPrint] 示例。  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Adding-a-Background-Script-to-you-Edge-Extension/player]  

### Manifest.js  

*   `author`Microsoft Edge 中需要该密钥  
*   `activeTab`Microsoft Edge 中不支持该键  

有关 [浏览器扩展][MDNBrowserExtensions]的详细信息，请参阅 [MDN web 文档][MDNWebDocs]。  

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
