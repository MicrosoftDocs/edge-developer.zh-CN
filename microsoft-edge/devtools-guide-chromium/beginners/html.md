---
title: 初学者的 DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 8695fe1b2c5d78bd074447acd26a1f01a5833b2d
ms.sourcegitcommit: 8bfa239274e7a4856b961b9cf163b08d96463c10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "10581585"
---
<!-- Copyright Katherine Jackson 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# 初学者的 DevTools： HTML 和 DOM 入门   

这是介绍 web 开发基础知识的一系列教程中的第一项。  你还将了解一组名为 Microsoft Edge DevTools 的 web 开发人员工具，这些工具可以提高工作效率。  

在本特定教程中，你将了解有关 HTML 和 DOM 的信息。  HTML 是 web 开发的核心技术之一。  它是用于控制网页的结构和内容的语言。  DOM 还与网页的结构和内容相关，但稍后你将了解更多相关信息。  

## 目标   

您将通过实际构建自己的网站来了解 web 开发。  当您完成*DevTools For 初学者*系列中的所有教程时，完成的网站将如下**图 1**所示。  

> ##### 图 1  
> 完成的网站  
> ![完成的网站][ImageHtmlFinished]  

本教程结束时，你将了解：  

*   HTML 和 DOM 如何创建你在网页上看到的内容。  
*   Microsoft Edge DevTools 可如何帮助你体验 HTML 和 DOM 更改。  
*   HTML 和 DOM 之间的区别。  

您还有一个真正的网站！  你可以使用此网站主持你的简历或博客。  

## 必备条件   

在尝试本教程之前，请完成以下先决条件：  

*   如果您不熟悉 HTML，请阅读[html][MDNGettingStartedHtml]入门。  
*   下载[Microsoft Edge][MicrosoftEdgeInsider] web 浏览器。  本教程使用一组称为 Microsoft Edge DevTools 的 web 开发工具，这些工具内置于 Microsoft Edge 中。  

## 设置代码   

您将在名为 "问题" 的联机代码编辑器中构建您的网站。  

1.  打开[源代码][GlitchAlluringShockIndex]。  此选项卡将在本教程的整个教程中称为 "**编辑器" 选项**卡。  
    > ##### 图 2  
    > "编辑器" 选项卡  
    > !["编辑器" 选项卡][ImageHtmlSetup1]  

1.  单击 " **alluring"-电击**。  将在左上角打开 "项目选项" 菜单。  
    
    > #### 图 3  
    > "项目选项" 菜单  
    > !["项目选项" 菜单][ImageHtmlSetup2]  
    
1.  单击 " **Remix Project**"。  问题创建可编辑的项目副本，并随机为项目生成新名称。  内容与以前的内容相同。  
    
    > ##### 图 4  
    > Remixed 项目  
    > ![Remixed 项目][ImageHtmlSetup3]  
    
1.  如果您计划完成本系列中的下一个教程，请单击您的 GitHub 或 Facebook 帐户**登录**并登录问题。  如果您不登录，一旦关闭 "编辑" 选项卡，您将失去编辑此项目的功能。  
1.  单击 "**显示**"，然后**在新窗口中**选择。  将打开一个新的选项卡，显示实时页面。  此选项卡将在整个教程中称为 "**实时" 选项卡**。  
    
    > ##### 图 5  
    > "实时" 选项卡  
    > !["实时" 选项卡][ImageHtmlSetup4]  
    
## 添加内容   

您的网站非常空。  请按照以下步骤将一些内容添加到！  

1.  在 "**编辑器" 选项卡**中，"替换 `<!-- You're "About Me" will go here.  -->` 为" `<h1>About Me</h1>` 。  
    
    ```html
    ...
        ...
        <body>
            <p> Your site!</p>
            <main>
                <h1>About Me</h1>
            </main>
            ...
        ...
    ...
    ```  
    
    > ##### 图 6  
    > 新代码在 "编辑器" 选项卡中突出显示  
    > ![新代码在 "编辑器" 选项卡中突出显示][ImageHtmlAdd1]  
    
1.  在 "**实时" 选项卡**中查看所做的更改。 文本 `About Me` 显示在页面上。  它比其余文本更大，因为该 `<h1>` 元素表示节标题。  Web 浏览器会自动以较大字体调整标题样式。  
    
    > ##### 图 7  
    > 新标题在 "实时" 选项卡中可见  
    > ![新标题在 "实时" 选项卡中可见][ImageHtmlAdd2]  
    
1.  返回到 "**编辑器" 选项卡**，在 `<p>I am learning HTML.  Recent accomplishments:</p>` 您刚放置的位置下方的行中插入 `<h1>About Me</h1>` 。  
    
    ```html
    ...
        ...
        <body>
            <p> Your site!</p>
            <main>
                <h1>About Me</h1>
                <p>I am learning web development.  Recent accomplishments:</p>
            </main>
            ...
        ...
    ...
    ```  

    > ##### 图 8  
    > 新代码在 "编辑器" 选项卡中突出显示  
    > ![新代码在 "编辑器" 选项卡中突出显示][ImageHtmlAdd3]  
    
1.  在 "**实时" 选项卡**中查看您的更改。  
1.  返回到 "**编辑器" 选项卡**，添加你的成就列表：  
    
    ```html
    ...
        ...
            ...
            <p>I am learning web development.  Recent accomplishments:</p>
            <ul>
                <li>Learned how to set up my code in Glitch.</li>
                <li>Added content to my HTML.</li>
                <li>TODO: Learn how to use Microsoft Edge DevTools to experiment with content changes.</li>
                <li>TODO: Learn the difference between HTML and the DOM.</li>
            </ul>
            ...
        ...
    ...
    ```  
    
    > ##### 图 9  
    > 新代码在 "编辑器" 选项卡中突出显示  
    > ![新代码在 "编辑器" 选项卡中突出显示][ImageHtmlAdd4]  
    
1.  再次返回 "**实时" 选项卡**，确保新内容正确显示。  
    
    > ##### 图 10  
    > 新列表在 "实时" 选项卡中可见  
    > ![新列表在 "实时" 选项卡中可见][ImageHtmlAdd5]  
    
## 在 Microsoft Edge DevTools 中试用内容更改   

如果你正在开发一个包含大量 HTML 的大型页面，你可以想像，在 "编辑器" 选项卡和 "实时" 选项卡之间来回切换以查看你的更改，尤其是当你不确定要在页面上放置哪些内容时。  Microsoft Edge DevTools 可帮助你在不离开 "实时" 选项卡的情况下试用内容更改。  

### 了解 HTML 和 DOM 之间的区别   

开始从 Microsoft Edge DevTools 编辑内容之前，了解 HTML 和 DOM 之间的区别很有帮助。  例如，学习的最佳方式是：  

1.  转到 "**实时" 选项卡**。 在页面底部看到文本 `A new element!?!` 。  
    
    > ###### 图 11  
    > 在页面底部 `A new element!?!` 可以看到文本  
    > ![在页面底部，新元素的文本!?! 可以看到][ImageHtmlDom1]  
    
1.  返回到 "**编辑器" 选项卡**，然后尝试在中查找此文本 `index.html` 。  不在这里！  
    
    > ##### 图 12  
    > `A new element!?!`无法在中找到神秘的文本 `index.html`  
    > ![新元素!?! 的神秘文本 在 index 中找不到任何地方][ImageHtmlDom2]  
    
1.  返回到 "**实时" 选项卡**，右键单击 `A new element!?!` ，然后选择 "**检查**"。  
    
    > ##### 图 13  
    > 检查某些文本  
    > ![检查某些文本][ImageHtmlDom3]  
    
    DevTools 将在您的页面旁打开。  `<div>A new element!?!</div>` 将突出显示蓝色。  虽然 DevTools 中的此结构看起来像是 HTML，但实际上它是**DOM 树**。  
    
    > ##### 图 14  
    > DevTools 在页面旁打开  
    > ![DevTools 在页面旁打开][ImageHtmlDom4]  
    
加载页面时，浏览器将获取 HTML 以创建页面的*初始*内容。  DOM 表示页面的*当前*内容，它可能会随着时间的推移而更改。  `<div>A new element!?!</div>`由于 HTML 底部的标记，可将神秘的内容添加到页面中 `<script src="new.js"></script>` 。  此标记会导致运行某些 JavaScript 代码。  在后面的教程中，你将了解有关 JavaScript 的详细信息，但现在将其视为可更改你的页面内容的编程语言。  在此特定情况下，JavaScript 代码将添加 `<div>A new element!?!</div>` 到您的页面。  这就是您的实时页面（而不是 HTML）中显示此神秘文本的原因。  

### 编辑 DOM   

如果想要快速试用内容更改而又不离开 "实时" 选项卡，请尝试 DevTools。  

1.  在 DevTools 中，右键单击 `Your site!` 并选择 "**编辑为 HTML**"。  

    > ##### 图 15  
    > 将节点编辑为 HTML  
    > ![将节点编辑为 HTML][ImageHtmlEdit1]  
    
1.  替换 `<p>Your site!</p>` 为以下代码。  
    
    ```html
    ...
        ...
            ...
            <header>
                <p><b>Welcome to my site!</b></p>
                <button>Download my resume</button>
            </header>
            ...
        ...
    ...
    ```  
    
    > ##### 图 16  
    > 将节点编辑为 HTML  
    > ![将节点编辑为 HTML][ImageHtmlEdit2]  
    
1.  按 `Control` + `Enter` \ （Windows \）或 `Command` + `Enter` \ （macOS \）保存所做的更改，或在框外单击。  您的更改会自动显示在您的页面的实时视图中。  文本已 `Your site!` 替换为新内容。  
    
    > ##### 图 17  
    > 新内容将立即显示在页面上  
    > ![新内容将立即显示在页面上][ImageHtmlEdit3]  
    
此工作流仅适用于试用内容更改。  如果重新加载页面或关闭选项卡，所做的更改将永久消失。  如果您使用的是此工作流，而您想要保存所做的更改，您需要手动将这些更改复制到您的 HTML 中。  接下来的几个部分介绍了一些可用于更改 DOM 树内容的更多方法。  

## 重新排序节点   

你还可以更改 DOM 节点的顺序。  例如，在网页上，导航菜单位于底部附近。  将其移动到顶部：  

1.  `<nav>`在 DevTools 的**DOM 树**中查找节点。  
    
    > ##### 图18  
    > 导航节点在 DevTools 中突出显示蓝色  
    > ![导航节点在 DevTools 中突出显示蓝色][ImageHtmlReorder1]  
    
1.  将 `<nav>` 节点拖到顶部，使其成为节点下方的第一个子级 `<body>` 。  
    > ##### 图19  
    > 将导航节点拖动到顶部  
    > ![将导航节点拖动到顶部][ImageHtmlReorder2]  
    
    `<nav>`现在，节点显示在您的页面顶部。  
    
    > ##### 图20  
    > 导航节点位于页面顶部  
    > ![导航节点位于页面顶部][ImageHtmlReorder3]  
    
### 删除节点   

您也可以从 DOM 树中删除节点。  

1.  在**DOM 树**中，单击 `<div>A new element!?!</div>` 。  DevTools 突出显示节点蓝色。  
    
    > ##### 图21  
    > 选择要删除的节点  
    > ![选择要删除的节点][ImageHtmlDelete1]  
    
1.  按 `Delete` 键盘上的键。  将 `<div>A new element!?!</div>` 从您的 DOM 树中删除该节点。  
    
    > ##### 图22  
    > 该节点已被删除  
    > ![该节点已被删除][ImageHtmlDelete2]  
    
## 复制更改   

即将完成。  你已在 DevTools 中对页面进行了一些更改，但这些更改尚未保存到你的源代码。  

1.  刷新 **"实时" 选项卡**。 您在 DOM 树中所做的更改将消失。  特别是，文本 `Your site!` 返回页首，文本 `A new element!?!` 返回到底部的文本。  
    
    > ##### 图23  
    > 您所做的更改已丢失  
    > ![您所做的更改已丢失][ImageHtmlCopy1]  

1.  复制下面的代码。  
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="utf-8">
            <meta http-equiv="X-UA-Compatible" content="IE=edge">
            <meta name="viewport" content="width=device-width, initial-scale=1">
        </head>
        <body>
            <header>
                <p>Welcome to my site!</p>
            </header>
            <nav>
                <ul>
                    <li><a href="/">Home</a></li>
                    <li><a href="/contact.html">Contact</a></li>
                </ul>
            </nav>
            <main>
                <h1>About Me</h1>
                <p>I am learning web development.  Recent accomplishments:</p>
                <ul>
                    <li>Learned how to set up my code in Glitch.</li>
                    <li>Added content to my HTML.</li>
                    <li>Learned how to use Microsoft Edge DevTools to experiment with content changes.</li>
                    <li>Learned the difference between HTML and the DOM.</li>
                </ul>
            </main>
        </body>
    </html>
    ```  
      
1.  返回到 "**编辑器" 选项卡**，并将您的 `index.html` 文件内容替换为您刚复制的代码。  
    
    > ##### 图24  
    > 文件的 `index.html` 外观  
    > ![您的 index .html 文件的外观][ImageHtmlCopy2]  
    
## 后续步骤   

*   完成本系列中的下一个教程 "[开始使用 CSS][DevToolsBeginnersCss]"，了解如何在 Microsoft Edge DevTools 中对页面进行样式更改并试验样式更改。  
*   阅读[对 dom 的介绍][MDNIntroductionDom]，了解有关 DOM 的详细信息。  
*   查看类似[于 Web 开发简介][CourseraIntroductionToWebDevelopment]的课程，以获得更多动手的 web 开发体验。  

<!--- image links --->  

[ImageHtmlFinished]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-finished.msft.png "图1：完成的网站"  
[ImageHtmlSetup1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-setup1.msft.png "图2： "编辑器" 选项卡"  
[ImageHtmlSetup2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-setup2.msft.png "图3： "项目选项" 菜单"  
[ImageHtmlSetup3]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-setup3.msft.png "图4： remixed 项目"  
[ImageHtmlSetup4]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-setup4.msft.png "图5： "实时" 选项卡"  
[ImageHtmlAdd1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-add1.msft.png "图6：新代码在 "编辑器" 选项卡中突出显示"  
[ImageHtmlAdd2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-add2.msft.png "图7：新标题在 "实时" 选项卡中可见"  
[ImageHtmlAdd3]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-add3.msft.png "图8：新代码在 "编辑器" 选项卡中突出显示"  
[ImageHtmlAdd4]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-add4.msft.png "图9：新代码在 "编辑器" 选项卡中突出显示"  
[ImageHtmlAdd5]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-add5.msft.png "图10：新列表在 "实时" 选项卡中可见"  
[ImageHtmlDom1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-dom1.msft.png "图11：在页面底部!?! 新元素的文本可以看到"  
[ImageHtmlDom2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-dom2.msft.png "图12：神秘的文本新元素!?!在 index 中找不到任何地方"  
[ImageHtmlDom3]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-dom3.msft.png "图13：检查某些文本"  
[ImageHtmlDom4]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-dom4.msft.png "图14： DevTools 在页面旁打开"  
[ImageHtmlEdit1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-edit1.msft.png "图15：以 HTML 格式编辑节点"  
[ImageHtmlEdit2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-edit2.msft.png "图16：以 HTML 格式编辑节点"  
[ImageHtmlEdit3]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-edit3.msft.png "图17：新内容将立即显示在页面上"  
[ImageHtmlReorder1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-reorder1.msft.png "图18：导航节点在 DevTools 中突出显示蓝色"  
[ImageHtmlReorder2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-reorder2.msft.png "图19：将导航节点拖动到顶部"  
[ImageHtmlReorder3]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-reorder3.msft.png "图20：导航节点位于页面顶部"  
[ImageHtmlDelete1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-delete1.msft.png "图21：选择要删除的节点"  
[ImageHtmlDelete2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-delete2.msft.png "图22：节点已被删除"  
[ImageHtmlCopy1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-copy1.msft.png "图23：您所做的更改已丢失"  
[ImageHtmlCopy2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-copy2.msft.png "图24：您的 index .html 文件应如何显示"  

<!--- links --->  

[DevToolsBeginnersCss]: /microsoft-edge/devtools-guide-chromium/beginners/css "初学者的 DevTools：开始使用 CSS"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  

[CourseraIntroductionToWebDevelopment]: https://www.coursera.org/learn/web-development "Web 开发简介 |Coursera"  

[GlitchAlluringShockIndex]: https://glitch.com/edit/#!/alluring-shock?path=index.html "alluring 的 html-冲击 |故障"  

[MDNGettingStartedHtml]: https://developer.mozilla.org/docs/Learn/HTML/Introduction_to_HTML/Getting_started "HTML | 入门MDN"  
[MDNIntroductionDom]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM 简介 |MDN"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/beginners/html)，由[Katherine 杰克逊][KatherineJackson]（技术作者暂存，Chrome DevTools \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
