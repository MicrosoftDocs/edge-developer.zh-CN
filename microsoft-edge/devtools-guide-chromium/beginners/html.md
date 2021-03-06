---
description: HTML 和 DOM 入门
title: 适用于初学者的 DevTools：HTML 和 DOM 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools
ms.openlocfilehash: 6ca27b720a17928545712666e43495c4da2fb880
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397927"
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

# <a name="devtools-for-beginners-get-started-with-html-and-the-dom"></a>适用于初学者的 DevTools：HTML 和 DOM 入门  

这是一系列教程中第一个介绍 Web 开发基础知识的教程。  了解一组 Web 开发人员工具（名为 Microsoft Edge DevTools）可能会提高工作效率。  

在此特定教程中，你将了解 HTML 和 DOM。  HTML 是 Web 开发的核心技术之一。  它是控制网页结构和内容的语言。  DOM 还与网页的结构和内容相关，稍后将了解相关内容。  

## <a name="goals"></a>目标  

你将通过实际构建自己的网站来学习 Web 开发。  在 **DevTools** for Beginners 系列中完成所有教程后，完成的网站可能如下图所示。  

:::image type="complex" source="../media/beginners-html-finished.msft.png" alt-text="已完成的网站" lightbox="../media/beginners-html-finished.msft.png":::
   已完成的网站  
:::image-end:::  

在本教程结束时，你应该了解以下主题。  

*   HTML 和 DOM 如何创建网页上显示的内容。  
*   Microsoft Edge DevTools 如何帮助你试验 HTML 和 DOM 更改。  
*   HTML 和 DOM 的区别。  

您还有一个真实的网站。  您可以使用该网站托管简历或博客。  

## <a name="prerequisites"></a>必备条件  

在尝试本教程之前，请完成以下先决条件：  

*   如果您不熟悉 HTML，请阅读 HTML [入门][MDNGettingStartedHtml]。  
*   下载 [Microsoft Edge][MicrosoftEdgeInsider] Web 浏览器。  本教程使用一组内置于 Microsoft Edge 中的 Web 开发工具（称为 Microsoft Edge DevTools）。  

## <a name="set-up-your-code"></a>设置代码  

你将在名为 Glitch 的联机代码编辑器中生成网站。  

1.  打开 [源代码][GlitchAlluringShockIndex]。  此选项卡在本教程 **中称为"** 编辑器"选项卡。  
    
    :::image type="complex" source="../media/beginners-html-setup1.msft.png" alt-text="编辑器选项卡" lightbox="../media/beginners-html-setup1.msft.png":::
       编辑器选项卡  
    :::image-end:::  
    
1.  选择 **"启发式"。**  将在左上角打开"项目选项"菜单。  
    
    :::image type="complex" source="../media/beginners-html-setup2.msft.png" alt-text=""项目选项"菜单" lightbox="../media/beginners-html-setup2.msft.png":::
       "项目选项"菜单  
    :::image-end:::  
    
1.  选择 **"重新混合项目"。**  小故障会创建一个可以编辑的项目副本，并随机为该项目生成一个新名称。  内容与之前相同。  
    
    :::image type="complex" source="../media/beginners-html-setup3.msft.png" alt-text="重新混合的项目" lightbox="../media/beginners-html-setup3.msft.png":::
       重新混合的项目  
    :::image-end:::  
    
1.  如果你计划完成本系列中的下一个教程，请选择"登录"，**** 然后使用 GitHub 或 Facebook 帐户登录小故障。  如果选择不登录帐户，则关闭编辑选项卡后将失去编辑项目的能力。  
1.  选择 **"显示**"，**然后选择"新建窗口"。**  将打开一个新选项卡，显示实时页面。  此选项卡在本教程 **中称为实时** 选项卡。  
    
    :::image type="complex" source="../media/beginners-html-setup4.msft.png" alt-text="实时选项卡" lightbox="../media/beginners-html-setup4.msft.png":::
       实时选项卡  
    :::image-end:::  
    
## <a name="add-content"></a>添加内容  

你的网站相当空。  按照以下步骤向其中添加一些内容。  

1.  在 **编辑器选项卡中**，替换为 `<!-- You're "About Me" will go here.  -->` `<h1>About Me</h1>` 。  
    
    :::row:::
       :::column span="":::
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
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-add1.msft.png" alt-text="新代码在编辑器选项卡中突出显示" lightbox="../media/beginners-html-add1.msft.png":::
             新代码在编辑器选项卡中突出显示  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  查看动态选项卡 **中的更改**。 文本 `About Me` 在页面上可见。  文本大于周围文本，因为 `<h1>` 元素表示节标题。  Web 浏览器自动对字体大小较大的标题进行样式设置。  
    
    :::image type="complex" source="../media/beginners-html-add2.msft.png" alt-text="新标题显示在活动选项卡中" lightbox="../media/beginners-html-add2.msft.png":::
       新标题显示在活动选项卡中  
    :::image-end:::  
    
1.  返回到编辑器 **选项卡中**，插入下面 `<p>I am learning HTML.  Recent accomplishments:</p>` 您刚刚放在的行 `<h1>About Me</h1>` 上。  
    
    :::row:::
       :::column span="":::
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
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-add3.msft.png" alt-text="更新后的代码在编辑器选项卡中突出显示" lightbox="../media/beginners-html-add3.msft.png":::
             更新后的代码在编辑器选项卡中突出显示  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  查看动态选项卡 **中的更改**。  
1.  返回编辑器 **选项卡**，添加你的成就列表：  
    
    :::row:::
       :::column span="":::
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
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-add4.msft.png" alt-text="更新后的代码也会在编辑器选项卡中突出显示" lightbox="../media/beginners-html-add4.msft.png":::
             更新后的代码也会在编辑器选项卡中突出显示  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  同样，返回到实时 **选项卡** 以确保新内容正确显示。  
    
    :::image type="complex" source="../media/beginners-html-add5.msft.png" alt-text="新列表在活动选项卡中可见" lightbox="../media/beginners-html-add5.msft.png":::
       新列表在活动选项卡中可见  
    :::image-end:::  
    
## <a name="experiment-with-content-changes-in-microsoft-edge-devtools"></a>在 Microsoft Edge DevTools 中试验内容更改  

如果要开发一个包含大量 HTML 的大页面，那么在编辑器选项卡和动态选项卡之间来回切换数百次以显示更改会有点繁琐，尤其是在不确定该页面上具体要放入哪些内容时。  Microsoft Edge DevTools 可帮助你试验内容更改，而无需离开实时 **选项卡**。  

### <a name="learn-the-difference-between-html-and-the-dom"></a>了解 HTML 和 DOM 的区别  

在开始从 Microsoft Edge DevTools 编辑内容之前，您应了解 HTML 和 DOM 的区别。  学习最好的方法就是通过示例：  

1.  导航到 **活动选项卡**。 在页面底部显示 `A new element!?!` 文本。  
    
    :::image type="complex" source="../media/beginners-html-dom1.msft.png" alt-text="在页面底部，文本 A 新元素!?! 显示" lightbox="../media/beginners-html-dom1.msft.png":::
       在页面底部显示 `A new element!?!` 文本  
    :::image-end:::  
    
1.  返回到编辑器 **选项卡，** 并尝试在 中查找文本 `index.html` 。  文本不存在。  
    
    :::image type="complex" source="../media/beginners-html-dom2.msft.png" alt-text="格式文本 A 新元素!?! 在 index.html 中index.htm" lightbox="../media/beginners-html-dom2.msft.png":::
       可以在以下 `A new element!?!` 内容中找到该文本： `index.html`  
    :::image-end:::  
    
1.  返回到实时**选项卡**，悬停在 `A new element!?!` 上，打开上下文菜单 \ (右键单击\) ，然后选择"检查 **"。**  
    
    :::image type="complex" source="../media/beginners-html-dom3.msft.png" alt-text="检查某些文本" lightbox="../media/beginners-html-dom3.msft.png":::
       检查某些文本  
    :::image-end:::  
    
    DevTools 将随页面一起打开。  `<div>A new element!?!</div>` 突出显示为蓝色。  尽管 DevTools 中的此结构看起来像你的 HTML，但它实际上是 **DOM 树**。  
    
    :::image type="complex" source="../media/beginners-html-dom4.msft.png" alt-text="DevTools 与页面一起打开" lightbox="../media/beginners-html-dom4.msft.png":::
       DevTools 与页面一起打开  
    :::image-end:::  
    
加载页面时，浏览器会采用 HTML 来创建 *页面* 的初始内容。  DOM 表示 *页面的当前* 内容，可能会随着时间的推移而更改。  由于 HTML 底部的标记，这一神奇内容将添加到 `<div>A new element!?!</div>` `<script src="new.js"></script>` 页面。  此标记会导致某些 JavaScript 代码运行。  在稍后的教程中了解有关 JavaScript 的信息，但现在认为它是可能会更改页面内容的编程语言。  在此特定情况下，JavaScript 代码 `<div>A new element!?!</div>` 将添加到页面。  这就是为什么此神奇文本在实时页面上可见，但在 HTML 中不可见的原因。  

### <a name="edit-the-dom"></a>编辑 DOM  

如果你想要在不离开实时选项卡的情况下快速试验内容更改，请尝试使用 DevTools。  

1.  在 DevTools 中，悬停在上，打开上下文菜单 `Your site!` \ (右键单击\) ，然后选择"编辑**为 HTML"。**  
    
    :::image type="complex" source="../media/beginners-html-edit1.msft.png" alt-text="将节点编辑为 HTML" lightbox="../media/beginners-html-edit1.msft.png":::
       将节点编辑为 HTML  
    :::image-end:::  
    
1.  替换为 `<p>Your site!</p>` 下面的代码。  
    
    :::row:::
       :::column span="":::
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
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-edit2.msft.png" alt-text="将节点更新为 HTML" lightbox="../media/beginners-html-edit2.msft.png":::
             将节点更新为 HTML  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  选择 `Control` + `Enter` \ (Windows、Linux\) 或 `Command` + `Enter` \ (macOS\) 保存更改，或在框外选择。  你的更改会自动显示在页面实时视图中。  文本 `Your site!` 已替换为新内容。  
    
    :::image type="complex" source="../media/beginners-html-edit3.msft.png" alt-text="新内容会立即显示在页面上" lightbox="../media/beginners-html-edit3.msft.png":::
       新内容会立即显示在页面上  
    :::image-end:::  
    
此工作流仅适用于试验内容更改。  如果刷新页面或关闭选项卡，更改将永久消失。  如果使用此工作流并且想要保存更改，则需要手动将这些更改复制到 HTML 中。  接下来的几节将介绍一些从 DOM 树更改内容的其他方法。  

## <a name="reorder-nodes"></a>对节点重新排序  

您还可以更改 DOM 节点的顺序。  例如，在网页上，导航菜单靠近底部。  若要将其移动到顶部：  

1.  在 `<nav>` DevTools **的 DOM 树** 中查找节点。  
    
    :::image type="complex" source="../media/beginners-html-reorder1.msft.png" alt-text="导航节点在 DevTools 中突出显示为蓝色" lightbox="../media/beginners-html-reorder1.msft.png":::
       导航节点在 DevTools 中突出显示为蓝色  
    :::image-end:::  
    
1.  将 `<nav>` 节点拖动到顶部，以便节点是节点的第一个 `<body>` 子节点。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-reorder2.msft.png" alt-text="将导航节点拖动到顶部" lightbox="../media/beginners-html-reorder2.msft.png":::
             将导航节点拖动到顶部  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          `<nav>`节点现在显示在页面顶部。  
          
          :::image type="complex" source="../media/beginners-html-reorder3.msft.png" alt-text="导航节点位于页面顶部" lightbox="../media/beginners-html-reorder3.msft.png":::
             导航节点位于页面顶部  
          :::image-end:::  
       :::column-end:::
   :::row-end:::  
    
### <a name="delete-a-node"></a>删除节点  

您还可以从 DOM 树中删除节点。  

1.  在 **DOM 树中**，选择 `<div>A new element!?!</div>` 。  DevTools 突出显示节点蓝色。  
    
    :::image type="complex" source="../media/beginners-html-delete1.msft.png" alt-text="选择要删除的节点" lightbox="../media/beginners-html-delete1.msft.png":::
       选择要删除的节点  
    :::image-end:::  
    
1.  选择 `Delete` 键盘上的键。  将从 `<div>A new element!?!</div>` DOM 树中删除节点。  
    
    :::image type="complex" source="../media/beginners-html-delete2.msft.png" alt-text="节点已删除" lightbox="../media/beginners-html-delete2.msft.png":::
       节点已删除  
    :::image-end:::  
    
## <a name="copy-your-changes"></a>复制更改  

你几乎已完成。  你已对 DevTools 中的页面进行了一些更改，但尚未保存到源代码中。  

1.  刷新你的 **实时选项卡**。 在 DOM 树中所做的更改将消失。  特别是，文本返回到页面顶部，文本 `Your site!` `A new element!?!` 返回底部。  
    
    :::image type="complex" source="../media/beginners-html-copy1.msft.png" alt-text="你所做的更改已消失" lightbox="../media/beginners-html-copy1.msft.png":::
       你所做的更改已消失  
    :::image-end:::  
    
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
    
1.  返回到编辑器 **选项卡** ，将文件内容 `index.html` 替换为刚复制的代码。  
    
    :::image type="complex" source="../media/beginners-html-copy2.msft.png" alt-text="index.html 文件的外观" lightbox="../media/beginners-html-copy2.msft.png":::
       文件 `index.html` 的外观  
    :::image-end:::  
    
## <a name="next-steps"></a>后续步骤  

*   完成本系列中的下一个教程 ["CSS][DevToolsBeginnersCss]入门"，了解如何设置页面样式，以及如何在 Microsoft Edge DevTools 中试验样式更改。  
*   阅读 [DOM 简介][MDNIntroductionDom] ，详细了解 DOM。  
*   查看 Web 开发 [简介等][CourseraIntroductionToWebDevelopment] 课程，获取更多动手 Web 开发体验。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!--- links --->  

[DevToolsBeginnersCss]: ./css.md "适用于初学者的 DevTools：CSS |Microsoft Docs"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  

[CourseraIntroductionToWebDevelopment]: https://www.coursera.org/learn/web-development "Web 开发|Coursera"  

[GlitchAlluringShockIndex]: https://glitch.com/edit/#!/alluring-shock?path=index.html "index.html - 启发式|小故障"  

[MDNGettingStartedHtml]: https://developer.mozilla.org/docs/Learn/HTML/Introduction_to_HTML/Getting_started "HTML 应用程序入门|MDN"  
[MDNIntroductionDom]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处，](https://developers.google.com/web/tools/chrome-devtools/beginners/html) 由一名技术编写器 ([Chrome][KatherineJackson] DevTools\) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
