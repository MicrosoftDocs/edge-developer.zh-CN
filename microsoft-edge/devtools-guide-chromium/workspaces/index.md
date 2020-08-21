---
title: 使用工作区编辑文件
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 8a31dd9fbfe492cf8eaacc654f7d501925f730f2
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942182"
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

# 使用工作区编辑文件  

> [!NOTE]
> 本教程的目标是提供设置和使用工作区的实际实践，以便在你自己的项目中使用工作区。  启用 Workspaces 后，可以保存对源代码（本地计算机上所做的源代码所做的更改）  

> [!IMPORTANT]
> **先决条件**：开始此教程之前，你应知道如何执行以下操作。  
> 
> *   [使用 html、CSS 和 JavaScript 构建网页][MDNWebGettingStarted]  
> *   [使用 DevTools 对 CSS 进行基本更改][DevToolsCssIndex]  
> *   [运行本地 HTTP Web 服务器][MDNSimpleLocalHTTPServer]  

## 概述  

利用工作区，您可以将 Devtools 中的更改保存到计算机上的相同文件的本地副本中。  在本教程中，应在计算机上具有以下设置。  

*   在桌面上具有网站的源代码。  
*   你运行的是源代码目录的本地 Web 服务器，以便网站可在访问 `localhost:8080` 。  
*   你在 `localhost:8080` Microsoft Edge 中打开并使用 DevTools 更改该网站的 CSS。  

启用工作区后，在 DevTools 中进行的 CSS 更改会保存到桌面上的源代码中。  

## 限制  

如果你使用的是现代框架，它可能不会将源代码转换为易于维护的格式，该格式已尽可能快速运行。  

工作区通常能够借助源映射的帮助将优化的代码映射回原 [始源代码][TreehouseBlogSourceMaps]。  但是每个框架之间有许多差别，超过了每个位图的使用方式。  Devtools 只支持所有变体。  

已知工作区不使用以下框架。  

*   创建回收应用  

    <!-- If you run into issues while using Workspaces with your framework of choice, or you get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  
    
## 相关功能：本地覆盖  

**本地替代是另** 一个 DevTools 功能，它类似工作区。  如果您试图对页面的更改进行更改，并且需要在页面加载中看到更改，但是不需更改使页面源代码映射到页面的源代码，请使用本地覆盖。  

<!--Todo: add section when content is ready  -->  

## 步骤 1：设置  

完成以下操作，以获得使用工作区的动手体验。  

### 设置演示  

1.  [打开演示][GlitchWorkspacesDemo]。  <!--In the top-left of the editor, a randomly-generated project name is displayed.  -->  
    
    :::image type="complex" source="../media/workspaces-glitch-workspaces-demo-source.msft.png" alt-text="Glitch 项目" lightbox="../media/workspaces-glitch-workspaces-demo-source.msft.png":::
       Glitch 项目  
    :::image-end:::  
    
    <!--1.  Choose the project name.  -->  
    <!--1.  Select **Advanced Options** > **Download Project**.  
    
    :::image type="complex" source="../media/workspaces-glitch-advanced-options-download-project.msft.png" alt-text="The Download Project button" lightbox="../media/workspaces-glitch-advanced-options-download-project.msft.png":::
       The Download Project button  
    :::image-end:::  

    -->  
    <!--1.  Close the tab.  -->  
    <!--1.  Unzip the source code and move the unzipped `app` directory to your desktop.  For the rest of this tutorial the unzipped directory is referred to as `~/Desktop/app`.  -->  
    
1.  在 `app` 桌面上创建目录。  将文件的副本从目录 `workspaces-demo` 保存到 `app` 目录。  对于教程的其余部分，该目录称为 `~/Desktop/app` ：  
1.  启动本地 Web 服务器 `~/Desktop/app` 。  以下是一些示例代码，用于起起 `SimpleHTTPServer` ，你可以使用你喜欢的几个服务器。  
    
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
    
1.  在 Microsoft Edge 中打开选项卡，转到该网站的本地托管版本。  你应当能够使用您的 URL 或以下 URL `localhost:8080` 访问它 `http://0.0.0.0:8080` 。  确实的端口 [号可能][WikiPortURLs] 不同。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo.msft.png" alt-text="演示版" lightbox="../media/workspaces-workspaces-demo.msft.png":::
       演示版  
    :::image-end:::  
    
### 设置 DevTools  

1.  选择 `Control` + `Shift` + `J` \ (Windows\) 或 `Command` + `Option` + `J` \ (macOS\) 以打开 DevTools 的控制台面板。 **Console**  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-console.msft.png" alt-text="主机面板" lightbox="../media/workspaces-workspaces-demo-console.msft.png":::
       **主机面**板  
    :::image-end:::  
    
1.  选择" **源"** 选项卡。  
1.  选择" **文件系统"** 选项卡。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem.msft.png" alt-text=""文件系统"选项卡" lightbox="../media/workspaces-workspaces-demo-sources-filesystem.msft.png":::
       " **文件系统"** 选项卡  
    :::image-end:::  
    
1.  选择 **"将文件夹添加到工作区**"。  
1.  键入 `~/Desktop/app`。  
1.  选择 **"允** 许"授予 DevTools 同步同步和写入目录的权限。  
    在" **文件系统"** 选项卡中，旁边有绿点， `index.html` 此标记出 `script.js` 来 `styles.css` 。  这些绿色点意味着 DevTools 已在页面的网络资源和其中的文件之间建立了映射 `~/Desktop/app` 。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png" alt-text=""文件系统"选项卡现在显示本地文件与网络之间的映射" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png":::
       " **文件系统** "选项卡现在显示本地文件与网络之间的映射  
    :::image-end:::  
    
## 步骤 2：保存 CSS 更改为光盘  

1.  打开 `styles.css`。  
    
    > [!NOTE]
    > `color`元素 `h1` 的属性设置为 `fuchsia` ：  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png" alt-text="在文本编辑器中查看 styles.css" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png":::
       在 `styles.css` 文本编辑器中查看  
    :::image-end:::  
    
1.  选择" **元素"** 选项卡。  
1.  将该元素 `color` 的属性 `<h1>` 值更改为你喜藏的颜色。  
    请记住，你需要在 `<h1>` **DOM 对** 该元素进行选择，才能在"样式"窗格中查看应用于它 **的** CSS 规则。  旁边的绿点 `styles.css:1` 表示你所做的任何更改都映射到 `~/Desktop/app/styles.css` 了。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-css.msft.png" alt-text="链接文件的绿色指示器" lightbox="../media/workspaces-workspaces-demo-elements-styles-css.msft.png":::
       链接文件的绿色指示器  
    :::image-end:::  
    
1.  再次 `styles.css` 在文本编辑器中打开。  `color`属性现已设置为收藏的颜色。  
1.  刷新页面。  元素的 `<h1>` 颜色仍设置为你最喜去的颜色。  更改将保留在刷新周围，因为当您使更改 DevTools 保存到了视频台时。  然后，刷新页面时，本地服务器已从盘修改了该文件的副本。  
    
## 步骤 3：将 HTML 更改保存到光盘  

### 从"元素面板"中更改 HTML  

你可能会从"元素面板"更改 html，但是对 DOM 的更改不会保存到文件盘，只会有当前的浏览器会话生效。  

DOM 的项目不是 HTML 的。  

<!--### Try changing HTML from the Elements panel  

> [!WARNING]
> The workflow that you are about to try does not work.  You are trying it now so that you do not waste time later trying to figure out why it is not working.  

1.  Choose the **Elements** tab.  
1.  Choose and edit the text content of the `h1` element, which says `Workspaces Demo`, and replace it with `I ❤️  Cake`.  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-change-h1.msft.png" alt-text="Attempt to change html from the DOM Tree of the Elements panel" lightbox="../media/workspaces-workspaces-demo-change-h1.msft.png":::
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

### 从"源"面板更改 HTML  

如果要保存对页面的 html 的更改，可使用"源"面 **板进行** 操作。  

1.  选择" **源"** 选项卡。  
1.  选择" **页"** 选项卡。  
1.  从** (索) 。 **  此时将打开该页面的 HTML。  
1.  用 `<h1>I ❤️  Cake</h1>` 取代 `<h1>Workspaces Demo</h1>`。  参见下图。  
1.  选择 `Control` + `S` \ (Windows\) 或 `Command` + `S` \ (macOS\) 以保存所做的更改。  
1.  刷新页面。  元素 `<h1>` 仍然显示新文本。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-page-h1.msft.png" alt-text="从"源"面板更改 HTML" lightbox="../media/workspaces-workspaces-demo-sources-page-h1.msft.png":::
       从"源" **面板更改** HTML  
    :::image-end:::  
    
1.  打开 `~/Desktop/app/index.html`。  元素 `<h1>` 包含新的文本。  
    
## 步骤 4：将 JavaScript 更改保存到该面盘  

" **源"** 面板也是对 JavaScript 进行更改的位置。  但有时，在对网站进行更改时，您需要访问其他面**Elements**板，如元素面板**Console**或主机面板。  可通过一种方法将 **"源"面板** 与其他面板一起打开。  

1.  选择" **元素"** 选项卡。  
1.  选择 `Control` + `Shift` + `P` \ (Windows\) 或 `Command` + `Shift` + `P` \ (macOS\) 。  此 **时将打开** 命令菜单。  
1.  键入 `QS` ，然后选择" **显示快速源**"。  在"开发工具"窗口底部，现在有一个"快速 **源"** 选项卡。 该选项卡显示内容，该选项卡 `index.html` 是你在源面板中编辑过 **的最后** 一个文件。  通过 **"快速** 来源"选项卡可从"源"面 **板向** 你提供编辑器，以便你能够在打开其他面板的同时编辑文件。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png" alt-text="使用命令菜单打开"快速源"选项卡" lightbox="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png":::
       使用命令 **菜单打开** "快速源 **"选项卡**  
    :::image-end:::  
    
1.  选择 `Control` + `P` \ (Windows\) 或 `Command` + `P` \ (macOS\) 以打开 **"打开文件"** 对话框。  参见下图。  
1.  键入 `script` ，然后选择**应用/script.js。 **  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-script.msft.png" alt-text="使用script.js"打开文件"对话框打开文件" lightbox="../media/workspaces-workspaces-demo-search-script.msft.png":::
       使用 `script.js` "打开**文件"对话框打开**  
    :::image-end:::  
    
    > [!NOTE]
    > `Save Changes To Disk With Workspaces`演示中的链接定期设置格式。  
    
1.  使用"快速源"选项卡将 ** 下列script.js** 添加到 **联系人的底** 部。  
    
    ```javascript
    console.log('greetings from script.js');
    document.querySelector('a').style = 'font-style:italic';
    ```  
    
1.  选择 `Control` + `S` \ (Windows\) 或 `Command` + `S` \ (macOS\) 以保存所做的更改。  
1.  刷新页面。  
    
    > [!NOTE]
    > 页面上的链接现在将被斜体。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png" alt-text="现在即可将页面上的链接斜体" lightbox="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png":::
       现在即可将页面上的链接斜体  
    :::image-end:::  
    
## 后续步骤  

使用本教程中学到的产品在你自己的项目中设置工作区。  <!-- If you run into any issues or are able to get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  

<!--  
If you have more feedback on the topics or anything else, please use any of the channels below:  

*   [Mailing List][AlphabetGroupsAlphabetBrowserDevTools]  
*   [Twitter][TwitterAlphabetBrowserDevTools]  
    -->  

<!-- links -->  

[DevToolsCssIndex]: ../css/index.md "查看和更改 CSS 入门 |Microsoft 文档"  

<!--[LocalOverrides]: ../whats-new/2018/01/devtools#overrides -->  

<!--[AlphabetGroupsAlphabetBrowserDevTools]: https://groups.alphabet.com/forum/#!forum/alphabet-browser-developer-tools "Alphabet Browser DevTools - Alphabet Groups"  -->  

[GlitchWorkspacesDemo]: https://glitch.com/edit/#!/microsoft-edge-chromium-devtools?path=workspaces-demo/index.html:1:0 "Workspaces 演示文件 |Glitch"  

[MDNCSSContent]: https://developer.mozilla.org/docs/Web/CSS/content "内容 - CSS：级集样式表 |MDN"  
[MDNWebGettingStarted]: https://developer.mozilla.org/docs/Learn/Getting_started_with_the_web "Web | 入门 |MDN"  
[MDNSimpleLocalHTTPServer]: https://developer.mozilla.org/docs/Learn/Common_questions/set_up_a_local_testing_server#Running_a_simple_local_HTTP_server "运行简单的本地 HTTP 服务器 |MDN"  
[MDNWebAPIsDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM 简介 - Web API |MDN"  

<!--[StackOverflowAlphabetBrowserDevTools]: https://stackoverflow.com/questions/ask?tags=alphabet-browser-devtools "Alphabet Browser DevTools - Stack Overflow"  -->

[TreehouseBlogSourceMaps]: https://blog.teamtreehouse.com/introduction-source-maps "源地图简介 |Treehouse 博客"  

<!-- [TwitterAlphabetBrowserDevTools]: https://twitter.com/alphabetbrowserdevtools "Alphabet Browser DevTools \(@AlphabetBrowserDevTools\) | Twitter"  -->

[WikiPortURLs]: https://en.wikipedia.org/wiki/Port_(computer_networking)#Use_in_URLs "端口 \ (计算机网络\) - 维网"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/workspaces/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
