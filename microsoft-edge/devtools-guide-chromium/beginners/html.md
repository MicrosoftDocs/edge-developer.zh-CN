---
description: HTML 和 DOM 入门
title: 适合初学者的 DevTools：HTML 和 DOM 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/01/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， web development， f12 tools， devtools， devtools for beginners， devtools HTML for beginners， devtools DOM for beginners， devtools html tutorial， devtools DOM tutorial， devtools document object model tutorial
ms.openlocfilehash: a049ec500e22f89db3ab1e966b55d89c2ad682fe
ms.sourcegitcommit: 8f37c931ecde4d58223113f7e3b42d37cc3df97f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2021
ms.locfileid: "11643472"
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
# <a name="devtools-for-beginners-get-started-with-html-and-the-dom"></a>适合初学者的 DevTools：HTML 和 DOM 入门  

这是一系列教程中第一个介绍 Web 开发基础知识的教程。 了解一组 Web 开发人员工具（名为 Microsoft Edge DevTools）可能会提高工作效率。  

本教程介绍 HTML 和 [文档对象模型](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) \ (DOM\) 。 HTML 是 Web 开发的核心技术之一。 它是控制网页结构和内容的语言。 DOM 还与网页的结构和内容相关，我们稍后将了解相关内容。

## <a name="goals"></a>目标  

你将通过构建网站来学习 Web 开发。  当你完成 **DevTools for Beginners** 系列的所有教程时，完成的网站可能如下图所示。  

:::image type="complex" source="media/beginners-html-finished.msft.png" alt-text="完成的网站" lightbox="media/beginners-html-finished.msft.png":::
   完成的网站  
:::image-end:::  

本教程结束时，你应该了解以下概念。  

*   HTML 和 DOM 如何创建网页上显示的内容。  
*   Microsoft Edge DevTools 如何帮助你试验 HTML 和 DOM 更改。  
*   HTML 和 DOM 的区别。  

您还将具有一个工作网站。 您可以使用该网站来承载简历或博客。  

## <a name="prerequisites"></a>必备条件  

在尝试本教程之前，请完成以下先决条件：  

*   如果不熟悉 HTML，请阅读 [HTML 文档入门][MDNGettingStartedHtml]。  
*   下载 [Microsoft Edge][MicrosoftEdgeInsider] Web 浏览器。  本教程使用一组内置于 Microsoft Edge 中的 Web 开发工具（称为 Microsoft Edge DevTools）。  

## <a name="set-up-your-code"></a>设置代码  

你将在 Glitch Online 代码编辑器中构建一个网站。  

1.  打开 [源代码][GlitchAlluringShockIndex]。 在本教程中，此选项卡称为" **编辑器"** 选项卡。  
    
    :::image type="complex" source="media/beginners-html-setup1.msft.png" alt-text="编辑器选项卡" lightbox="media/beginners-html-setup1.msft.png":::
       编辑器选项卡  
    :::image-end:::  
    
1.  选择 **"启发式"。** "Project**选项"** 菜单将打开。  
    
    :::image type="complex" source="media/beginners-html-setup2.msft.png" alt-text="项目选项菜单" lightbox="media/beginners-html-setup2.msft.png":::
       项目选项菜单  
    :::image-end:::  
    
1.  选择 **"重新混合项目"。** Glitch 会创建一个可以编辑的项目副本，并随机为该项目生成一个新名称。 内容与之前相同。  
    
    :::image type="complex" source="media/beginners-html-setup3.msft.png" alt-text="重新混合的项目" lightbox="media/beginners-html-setup3.msft.png":::
       重新混合的项目  
    :::image-end:::  
    
1.  如果计划完成本系列中的下一教程，请选择"使用 Facebook、GitHub或 Google 帐户登录小故障"; **** 或向自己发送一个神奇链接。 如果选择不登录帐户，则关闭编辑器选项卡后无法编辑项目。

1.  选择 **"**  \>  **在新建窗口中显示"。**  将打开一个新选项卡，显示实时页面。 在本教程中，此选项卡称为实时 **选项卡**。  
    
    :::image type="complex" source="media/beginners-html-setup4.msft.png" alt-text="实时选项卡" lightbox="media/beginners-html-setup4.msft.png":::
       实时选项卡  
    :::image-end:::  
    
## <a name="add-content"></a>添加内容  

您的网站需要更多信息。 完成以下步骤以添加一些内容。  

1. 在" **编辑器"选项卡**，将 `<!-- You're "About Me" will go here.  -->` 替换 `<h1>About Me</h1>`。  
    
    ```html
        ...
        <body>
            <p> Your site!</p>
                <main>
                    <h1>About Me</h1>
                </main>
        ...
    ```  
    
    :::image type="complex" source="media/beginners-html-add1.msft.png" alt-text="新代码在编辑器选项卡中突出显示" lightbox="media/beginners-html-add1.msft.png":::
        新代码在编辑器选项卡中突出显示  
    :::image-end:::  
    
1. 在实时选项卡 **中查看更改**。文本 `About Me` 在页面上可见。 文本大于周围文本，因为 `<h1>` 元素表示"标题 1"。  Web 浏览器自动为标题设置更大字体的样式。  
    
    :::image type="complex" source="media/beginners-html-add2.msft.png" alt-text="新标题显示在活动选项卡中" lightbox="media/beginners-html-add2.msft.png":::
       新标题显示在活动选项卡中  
    :::image-end:::  
    
1. 返回到编辑器 **选项卡中**，插入 `<p>I am learning web development. Recent accomplishments:</p>` 下面的行  `<h1>About Me</h1>` 。  
    
    ```html
    ...
        <body>
            <p> Your site!</p>
                <main>
                    <h1>About Me</h1>
                    <p>I am learning web development. Recent accomplishments:</p>
                </main>
    ...
    ```  

    :::image type="complex" source="media/beginners-html-add3.msft.png" alt-text="更新后的代码在编辑器选项卡中突出显示" lightbox="media/beginners-html-add3.msft.png":::
        更新后的代码在编辑器选项卡中突出显示  
    :::image-end:::  
    
1. 在实时选项卡 **中查看更改**。

1. 返回到编辑器 **选项卡**，使用下面的代码添加你的成就列表。
    
    ```html
    ...
    <p>I am learning web development.  Recent accomplishments:</p>
        <ul>
            <li>Learned how to set up my code in Glitch.</li>
            <li>Added content to my HTML.</li>
            <li>TODO: Learn how to use Microsoft Edge DevTools to experiment with content changes.</li>
            <li>TODO: Learn the difference between HTML and the DOM.</li>
        </ul>
    ...
    ```  

    :::image type="complex" source="media/beginners-html-add4.msft.png" alt-text="更新后的代码还会在编辑器选项卡中突出显示" lightbox="media/beginners-html-add4.msft.png":::
        更新后的代码还会在编辑器选项卡中突出显示  
    :::image-end:::  

1. 查看 **实时选项卡** 以确保新内容正确显示。  
    
    :::image type="complex" source="media/beginners-html-add5.msft.png" alt-text="新列表在活动选项卡中可见" lightbox="media/beginners-html-add5.msft.png":::
       新列表在活动选项卡中可见  
    :::image-end:::  
    
## <a name="experiment-with-content-changes-in-microsoft-edge-devtools"></a>在 Microsoft Edge DevTools 中试验内容更改  

如果要开发包含大量 HTML 的页面，在编辑器选项卡和实时选项卡之间来回切换以查看更改将变得繁琐。 Microsoft Edge DevTools 可帮助你尝试内容更改，而无需离开实时 **选项卡**。  

### <a name="learn-the-difference-between-html-and-the-dom"></a>了解 HTML 和 DOM 的区别  

在编辑 DevTools Microsoft Edge内容之前，让我们了解 HTML 和 DOM 的区别。 继续执行以下步骤以从示例中学习。

1. 导航到实时 **选项卡**。在页面底部，将显示 `A new element!?!` 文本。  

    <!--
        :::image type="complex" source="media/beginners-html-dom1.msft.png" alt-text="At the bottom of the page the text A new element!?! displays" lightbox="media/beginners-html-dom1.msft.png":::
        At the bottom of the page the text `A new element!?!` is displays  
        :::image-end:::
    -->
    
1. 打开 **编辑器选项卡** ，并尝试在 中查找文本 `index.html` 。 文本不会在此视图中显示。  

    <!--
        :::image type="complex" source="media/beginners-html-dom2.msft.png" alt-text="The mystery text A new element!?! is not found in index.html" lightbox="media/beginners-html-dom2.msft.png":::
        The mystery text `A new element!?!` is not found in `index.html`  
        :::image-end:::
    -->

1. 打开实时**选项卡**，将鼠标悬停在 上，右 `A new element!?!` 键单击 (上下文菜单，然后选择) 检查 **"。**  
    
    :::image type="complex" source="media/beginners-html-dom3.msft.png" alt-text="检查某些文本" lightbox="media/beginners-html-dom3.msft.png":::
       检查某些文本  
    :::image-end:::  
    
    DevTools 将在页面旁边打开。 `<div>A new element!?!</div>` 突出显示。 尽管 DevTools 中的此结构类似于 HTML，但它是 **DOM 树**。  
    
    :::image type="complex" source="media/beginners-html-dom4.msft.png" alt-text="DevTools 与页面一起打开" lightbox="media/beginners-html-dom4.msft.png":::
       DevTools 与页面一起打开  
    :::image-end:::  
    
加载页面时，浏览器使用 HTML 创建页面的初始内容。 DOM 表示 页面 的当前内容，可能会随着时间的推移而更改。 

由于 HTML 底部的 标记，内容 `<div>A new element!?!</div>` `<script src="new.js"></script>` 将添加到页面。 此标记会导致某些 JavaScript 代码运行。 在稍后的教程 中了解有关 JavaScript [的更多内容](../javascript/index.md)。

现在，请看做可能会更改页面内容的脚本语言。 在这种情况下，JavaScript 代码将 `<div>A new element!?!</div>` 添加到你的页面。 这就是此文本显示在活动选项卡 **中** 而不是 HTML 中的原因。  

### <a name="edit-the-dom"></a>编辑 DOM  

如果你想要在不离开动态选项卡的情况下快速试验内容更改，请尝试使用 DevTools。  

1.  在 DevTools 中，将鼠标悬停在 上，打开上下文菜单 (右键单击") `Your site!` 并选择"编辑**为 HTML"。**  
    
1.  将 `<p>Your site!</p>` 替换为以下代码。  

```html
    ...
    <header>
        <p><b>Welcome to my site!</b></p>
        <button>Download my resume</button>
    </header>
    ...
```  

:::image type="complex" source="media/beginners-html-edit2.msft.png" alt-text="将节点更新为 HTML" lightbox="media/beginners-html-edit2.msft.png":::
    将节点更新为 HTML  
：：image-end：：：  

1.  选择 `Control` + `Enter` \ (Windows、Linux\) 或 `Command` + `Enter` \ (macOS\) 保存更改，或在框外选择。 更改将自动显示在页面实时视图中。 文本 `Your site!` 已替换为新内容。  
    
    :::image type="complex" source="media/beginners-html-edit3.msft.png" alt-text="新内容会立即显示在页面上" lightbox="media/beginners-html-edit3.msft.png":::
       新内容会立即显示在页面上  
    :::image-end:::  
    
此工作流仅适用于试验内容更改。 如果刷新页面或关闭选项卡，更改将丢失。 如果要保存更改，请手动将代码复制到 HTML 文件中。 接下来的几节将介绍从 DOM 树更改内容的更多方法。  

## <a name="reorder-nodes"></a>对节点重新排序

您还可以更改 DOM 节点的顺序。 例如，在网页上，导航菜单靠近底部。 若要将其移动到顶部，请执行以下步骤。  

1.  在 DevTools `<nav>` DOM 树 **中** 节点。  
    
    :::image type="complex" source="media/beginners-html-reorder1.msft.png" alt-text="导航节点在 DevTools 中突出显示" lightbox="media/beginners-html-reorder1.msft.png":::
       导航节点在 DevTools 中突出显示  
    :::image-end:::  
    
1.  将 `<nav>` 节点拖动到顶部，以便节点是节点后的第一个 `<body>` 子节点。  
    
    :::image type="complex" source="media/beginners-html-reorder3.msft.png" alt-text="导航节点位于页面顶部" lightbox="media/beginners-html-reorder3.msft.png":::
        导航节点位于页面顶部  
    :::image-end:::  
    
### <a name="delete-a-node"></a>删除节点

您还可以从 DOM 树中删除节点。 执行以下步骤。

1.  在 **DOM 树**中，选择 `<div>A new element!?!</div>`。 DevTools 突出显示节点。 
    
1.  选择 `Delete` 键盘上的键。  将从 `<div>A new element!?!</div>` DOM 树中删除节点。  
    
    :::image type="complex" source="media/beginners-html-delete2.msft.png" alt-text="节点已删除" lightbox="media/beginners-html-delete2.msft.png":::
       节点已删除  
    :::image-end:::  
    
## <a name="copy-your-changes"></a>复制更改  

你已接近完成。 你在 DevTools 中对页面进行了一些更改，但它们不会保存到源代码中。  

1.  刷新活动 **选项卡**。在 DOM 树中所做的更改将消失。 具体而言，文本 `Your site!` 返回页首，文本 `A new element!?!` 返回页面底部。  
    
    :::image type="complex" source="media/beginners-html-copy1.msft.png" alt-text="你所做的更改已消失" lightbox="media/beginners-html-copy1.msft.png":::
       你所做的更改已消失  
    :::image-end:::  
    
1.  复制以下代码。  
    
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
    
1.  返回到编辑器 **选项卡** ，将文件内容 `index.html` 替换为复制的代码。  
    
    :::image type="complex" source="media/beginners-html-copy2.msft.png" alt-text="index.html 文件的外观" lightbox="media/beginners-html-copy2.msft.png":::
       文件 `index.html` 的外观  
    :::image-end:::  
    
## <a name="next-steps"></a>后续步骤  

*   完成本系列的下一个教程[CSS入门][DevToolsBeginnersCss]，以了解如何设置页面样式并尝试在Microsoft Edge DevTools中进行样式更改。  
*   阅读 [DOM 简介][MDNIntroductionDom] ，详细了解 DOM。  
*   有关更多动手 Web 开发体验 [，][CourseraIntroductionToWebDevelopment] 请查看 Web 开发简介等课程。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!--- links --->  

[DevToolsBeginnersCss]: ./css.md "适用于初学者的 DevTools：CSS |Microsoft Docs"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  

[CourseraIntroductionToWebDevelopment]: https://www.coursera.org/learn/web-development "Web 开发类简介 | Coursera"  

[GlitchAlluringShockIndex]: https://glitch.com/edit/#!/alluring-shock?path=index.html "index.html - 启发式|小故障"  

[MDNGettingStartedHtml]: https://developer.mozilla.org/docs/Learn/HTML/Introduction_to_HTML/Getting_started "HTML 应用程序入门|MDN"  
[MDNIntroductionDom]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM 简介 | MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/beginners/html) ，作者为 [Katherine Writer][KatherineJackson] \ (Technical Writer，Chrome DevTools\) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors  
