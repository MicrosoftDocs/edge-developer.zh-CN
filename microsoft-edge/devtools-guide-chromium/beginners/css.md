---
description: CSS 入门
title: 适用于初学者的 DevTools：CSS 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools
ms.openlocfilehash: 7aa33c339a7d130265660e4a4af6f50dde7e3e90
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398397"
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

# <a name="devtools-for-beginners-get-started-with-css"></a>适用于初学者的 DevTools：CSS 入门  

本教程介绍如何使用 CSS 设置网页样式。  此外，还了解如何使用 Microsoft Edge DevTools 试验 CSS 更改。  

以下文章是一系列教程的第二个教程，该教程将指导你 Web 开发和 Microsoft Edge DevTools 的基础知识。  通过实际构建自己的网站，你可以获得实践体验。  在学习第二个教程之前，不需要完成第一个教程。  [设置代码将](#set-up-your-code) 演示如何进行设置。  

> [!NOTE]
> 本教程专为完全初学者设计，重点介绍 **Web** 开发基础知识和使用 DevTools 试验 CSS 的基础知识。  如果你需要一个仅侧重于 DevTools 的教程，请导航到"查看和更改 CSS 入门["。][DevtoolsCssIndex]  

在本教程的开头，您的网站应如下所示。  

:::image type="complex" source="../media/beginners-css-intro1.msft.png" alt-text="网站当前的外观" lightbox="../media/beginners-css-intro1.msft.png":::
   网站当前的外观  
:::image-end:::  

完成本教程后，网站应如下所示。  

:::image type="complex" source="../media/beginners-css-intro2.msft.png" alt-text="你的网站在本教程末尾应的外观" lightbox="../media/beginners-css-intro2.msft.png":::
   你的网站在本教程末尾应的外观  
:::image-end:::  

## <a name="goals"></a>目标  

按照本教程更好地了解以下概念和任务。  

*   如何使用 CSS 设置网页样式。  
*   如何使用 Microsoft Edge DevTools 试验 CSS。  
*   CSS 和 CSS 框架的区别。  

你正在构建一个真实的网站。  

## <a name="prerequisites"></a>必备条件  

在尝试本教程之前，请完成以下先决条件。  

*   完成 [HTML 和 DOM][DevtoolsBeginnersHtml] 入门，或确保你了解 HTML 和 DOM，与本教程中介绍的内容类似。  
*   下载 [Microsoft Edge][MicrosoftEdgeInsider] Web 浏览器。  以下教程使用一组内置于 Microsoft Edge 中的 Web 开发工具，称为 Microsoft Edge DevTools。  

## <a name="set-up-your-code"></a>设置代码  

若要创建网站，必须先完成以下操作以设置代码。  

> [!NOTE]
> 如果已完成系列的第一个教程，请跳到下一节。  继续使用上一教程中的代码，即 [HTML 和 DOM 入门][DevtoolsBeginnersHtml]。  

1.  打开 [源代码][GlitchCookedAmphibianIndex]。  浏览器的"焦点内"选项卡被引用为 **编辑选项卡**。  
    
    :::image type="complex" source="../media/beginners-css-setup1.msft.png" alt-text="编辑选项卡" lightbox="../media/beginners-css-setup1.msft.png":::
       编辑**选项卡**  
    :::image-end:::  
    
1.  Choose **cooked-amphibian**.  弹出菜单。  
    
    :::image type="complex" source="../media/beginners-css-setup2.msft.png" alt-text=""项目选项"菜单" lightbox="../media/beginners-css-setup2.msft.png":::
       "项目选项"菜单  
    :::image-end:::  

1.  选择 **"重新混合项目"。**  小故障将创建您能够编辑的项目的副本。  
    
    > [!NOTE]
    > 小故障为新项目生成随机名称。  
    
1.  选择 **"显示**"，**然后选择"新建窗口"。**  另一个选项卡将打开，其中显示网站实时视图。  浏览器的"焦点内"选项卡被引用为实时 **选项卡**。  
    
    :::image type="complex" source="../media/beginners-css-setup3.msft.png" alt-text="实时选项卡" lightbox="../media/beginners-css-setup3.msft.png":::
       实时 **选项卡**  
    :::image-end:::  

## <a name="understand-css"></a>了解 CSS  

**CSS** 是一种计算机语言，用于确定网页的布局和样式。  下图是带边框的段落。  

:::image type="complex" source="../media/beginners-css-red_paragraph.msft.png" alt-text="文本已使用 CSS 设置样式" lightbox="../media/beginners-css-red_paragraph.msft.png":::
   文本已使用 CSS 设置样式  
:::image-end:::  

下面的代码段是用于创建上图中的段落的 HTML 和 CSS 代码。  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`style="border: 1px dashed red; padding: 5px;"` 可能看起来是全新的。  其余部分看起来应该很熟悉。  如果没有，请 [完成 HTML 和 DOM][DevtoolsBeginnersHtml] 入门，然后再尝试以下部分。  

## <a name="add-inline-styles"></a>添加内联样式  

完成以下操作以使用 **内联样式将** 样式应用于单个元素。  

1.  返回到编辑选项卡并打开 `index.html` 。  
    
    :::image type="complex" source="../media/beginners-css-inline1.msft.png" alt-text="index.html" lightbox="../media/beginners-css-inline1.msft.png":::
       在 `index.html` 编辑选项卡中打开  
    :::image-end:::  
    
1.  添加到 `style="background-color: aliceblue;"` 你的 `<nav>` 。  在下面的代码块中，需要更改第四行代码。  其余代码就在这里，因此可以确保将新代码放在正确的位置。  
    
    ```html
    <header>
        <p>Welcome to my site!</p>
    </header>
    <nav style="background-color: aliceblue;">
        <ul>
            <li><a href="/">Home</a></li>
            ...
        ...
    ...
    ```  
    
1.  若要显示更改，请导航到活动 **选项卡**。 分区的背景现在 `<nav>` 为蓝色。  
    
    :::image type="complex" source="../media/beginners-css-inline2.msft.png" alt-text=""主页"和"联系人"链接背后的背景色现在为蓝色" lightbox="../media/beginners-css-inline2.msft.png":::
       "主页" **和"联系人** "链接 **背后的背景色** 现在为蓝色  
    :::image-end:::  
    
## <a name="re-use-styles-on-a-single-page-with-internal-stylesheets"></a>在包含内部样式表的单个页面上重新使用样式  

在以前的代码段中，内联样式将样式应用于单个 `<p>` 标记。  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

如果希望网页上的所有元素都以相同方式设置样式 `<p>` ，该做什么？  您必须将代码复制并粘贴到网站上 `<p>` 每个标记中。  这是一项大量的时间和精力。  如果需要进行编辑，必须再次更改每个标记。  完成以下操作以使用内部样式 **表** 编写 CSS 一次，以便应用于多个元素。  

1.  在活动选项卡中，选择 **"联系人"** 以导航到联系人页面。  请注意"主页" **和** "联系人 **"的字体**。  
    
    :::image type="complex" source="../media/beginners-css-internal1.msft.png" alt-text=""联系人"页" lightbox="../media/beginners-css-internal1.msft.png":::
       "联系人"页  
    :::image-end:::  
    
1.  在 **编辑器选项卡中**，打开 `contact.html` 。  
1.  将以下代码添加到 `contact.html` 。  请记住，需要添加以开始 `<style>` 和结尾 `</style>` 的行。  其他代码就在这里，以便你知道在何处放入新代码。  
    
    ```html
    ...
        <head>
            ...
            <meta name="viewport" content="width=device-width, initial-scale=1">
            <style>
                li a {
                  font-family: 'Courier New', Courier, Serif;
                }
            </style>
            ...
        </head>
        ...
    ...
    ```  
    
1.  返回到实时 **选项卡**。  
1.  选择 **"** 联系人"返回到联系人页面。  "主页 **"和** " **联系人"的** 字体已更改。  
    
    :::image type="complex" source="../media/beginners-css-internal2.msft.png" alt-text=""主页"和"联系人"链接的字体已更改" lightbox="../media/beginners-css-internal2.msft.png":::
       "主页" **和** " **联系人"链接的** 字体已更改  
    :::image-end:::  
    
### <a name="understand-internal-stylesheets"></a>了解内部样式表  

内部样式表使用选择器应用 **样式**。  选择器是可能应用于一个或多个 HTML 元素的模式。  前面的代码段添加了以下样式。  

```html
<style>
    li a {
      font-family: 'Courier New', Courier, Serif;
    }
</style>
```  

`li a` 是一个转换为" `<li>` 包含元素的任何元素 `<a>` "的选择器。  浏览器更改"主页"和"**** 联系人 **"** 链接的字体，因为每个标记组都匹配模式。  

```html
<li><a href="/">Home</a></li>
<li><a href="/contact.html">Contact</a></li>
```  

`font-family: 'Courier New', Courier, serif` 是一个 **声明**。  声明由以下两部分组成。  

:::row:::
   :::column span="1":::
      **property**  
   :::column-end:::
   :::column span="1":::
      `font-family`  
   :::column-end:::
   :::column span="2":::
      该属性描述一种能够更改元素样式的常规方法。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **值**  
   :::column-end:::
   :::column span="1":::
      `'Courier New', Courier, serif`  
   :::column-end:::
   :::column span="2":::
      该值准确描述了元素的样式应该如何更改。  
   :::column-end:::
:::row-end:::  

例如， `font-family: 'Courier New', Courier, serif` 为浏览器提供以下指令："将匹配模式的元素的字体设置为 `li a` `'Courier New'` 。  如果该字体不可用，请使用 `Courier` 。  如果不可用，请使用 `serif` 。"  

### <a name="add-multiple-selectors-to-a-ruleset"></a>向规则集添加多个选择器  

类似以下代码段的 CSS 代码块称为 **规则集**。  

```css
li a {
  font-family: 'Courier New', Courier, monospace;
}
```  

完成以下操作以使用逗号将多个选择器添加到规则集。  

1.  在 **编辑器选项卡中**，打开 `contact.html` 。  
1.  键入 `li a` `, h1` 后 。  
    
    ```html
    <style>
        li a, h1 {
          font-family: 'Courier New', Courier, Serif;
        }
    </style>
    ```  
    
    前面的代码段指示浏览器设置元素样式的方式与设置 `<h1>` 与模式匹配的元素的样式相同 `li a` 。  
    
1.  导航到 **活动选项卡**。  
1.  选择 **"联系人** "链接返回到联系人页面。  现在， **联系我！** 具有与导航链接相同的字体。  
    
    :::image type="complex" source="../media/beginners-css-multiple1.msft.png" alt-text="文本"联系我"  现在具有与"主页"和"联系人"链接相同的字体" lightbox="../media/beginners-css-multiple1.msft.png":::
       文本" **联系我"** 现在具有与"主页"和 **"联系人** " **链接相同的** 字体  
    :::image-end:::  
    
## <a name="experiment-with-devtools"></a>使用 DevTools 进行试验  

当你继续成为 Web 开发专家的旅程时，你可能会发现 CSS 很棘手。  你可以编写一些 CSS，并期望它以一种方式显示，但浏览器会进行完全不同的操作。  通过 Microsoft Edge DevTools，可以轻松试验更改并立即显示更改对页面的影响。  

### <a name="add-a-declaration-to-an-existing-rulest-in-devtools"></a>将声明添加到 DevTools 中的现有规则  

完成以下操作以对现有元素的样式进行轮访问，向现有规则集添加声明。  

1.  悬停在"主页 **"** 链接上，打开上下文菜单 \ (右键单击\) ，然后选择"检查 **"。**  
    
    :::image type="complex" source="../media/beginners-css-add1.msft.png" alt-text="检查"主页"链接" lightbox="../media/beginners-css-add1.msft.png":::
       检查"主页"链接  
    :::image-end:::  
    
    DevTools 将随页面一起打开。  表示"主页"链接的代码在 `<a href="/">Home</a>` DOM 树中突出显示为蓝色。  代码段和预览应该熟悉 HTML 和 [DOM][DevtoolsBeginnersHtml]入门。  
    
    :::row:::
       :::column span="":::
          下图中，您之前添加到的声明显示在 `font-family: 'Courier New', Courier, serif` `contact.html` DOM 树下方的 **"** 样式"选项卡中。  
          
          :::image type="complex" source="../media/beginners-css-add2.msft.png" alt-text=""样式"选项卡位于 DOM 树下方" lightbox="../media/beginners-css-add2.msft.png":::
             " **样式"** 选项卡位于 DOM 树下方  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          如果 DevTools 窗口很宽，则"样式"选项卡位于 DOM 树的右侧。  
          
          :::image type="complex" source="../media/beginners-css-add3.msft.png" alt-text=""样式"选项卡位于 DOM 树的右侧" lightbox="../media/beginners-css-add3.msft.png":::
             " **样式** "选项卡位于 DOM 树的右侧  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  选择下面的空行 `font-family: 'Courier New', Courier, Serif` 以添加新声明。  
    
    :::image type="complex" source="../media/beginners-css-add4.msft.png" alt-text="添加新声明" lightbox="../media/beginners-css-add4.msft.png":::
       添加新声明  
    :::image-end:::  
    
1.  键入 `color` 并选择 `Enter`。  键入时，自动完成 UI 会推荐选项。  
    
    :::image type="complex" source="../media/beginners-css-add5.msft.png" alt-text="类型颜色" lightbox="../media/beginners-css-add5.msft.png":::
       类型 `color`  
    :::image-end:::  
    
1.  键入 `magenta` 并选择 `Enter`。  联系人页面上的所有文本现在都为洋红色。  
    
    :::image type="complex" source="../media/beginners-css-add6.msft.png" alt-text="类型洋红色" lightbox="../media/beginners-css-add6.msft.png":::
       类型 `magenta`  
    :::image-end:::  
    
### <a name="edit-a-declaration-in-devtools"></a>在 DevTools 中编辑声明  

完成以下操作以编辑 DevTools 中的现有声明。  

1.  选择旁边的洋红色正方形 `magenta` 。  颜色选取器弹出。  
    
    :::image type="complex" source="../media/beginners-css-edit1.msft.png" alt-text="颜色选取器" lightbox="../media/beginners-css-edit1.msft.png":::
       颜色选取器  
    :::image-end:::  
    
1.  使用颜色选取器将字体文本更改为您喜欢的颜色。  
    
    :::image type="complex" source="../media/beginners-css-edit2.msft.png" alt-text="使用颜色选取器将字体颜色更改为紫色" lightbox="../media/beginners-css-edit2.msft.png":::
       使用颜色选取器将字体颜色更改为紫色  
    :::image-end:::  
    
### <a name="add-a-new-ruleset-in-devtools"></a>在 DevTools 中添加新的规则集  

完成以下操作以在 DevTools 中添加新的规则集。  

1.  Choose **New Style Rule** \ (New Style Rule ![ ][ImageNewStyleRuleIcon] \) which is next to **.cls**.  空的规则集显示为 `a` 选择器。  
    
    :::image type="complex" source="../media/beginners-css-rule1.msft.png" alt-text="添加新规则" lightbox="../media/beginners-css-rule1.msft.png":::
       添加新规则  
    :::image-end:::  
    
1.  用 `a:hover` 取代 `a`。  
    
    :::image type="complex" source="../media/beginners-css-rule2.msft.png" alt-text="将 a 替换为 a：hover" lightbox="../media/beginners-css-rule2.msft.png":::
       替换为 `a` `a:hover`  
    :::image-end:::  
    
    `:hover` 是 **伪类**。  对可能进入特殊状态样式元素使用伪类。  例如， `a:hover` 样式仅在将鼠标悬停在元素上时 `<a>` 生效。  
    
1.  在括号之间选择以添加新声明。  
1.  键入 `background-color` 声明名称并选择 `Enter` 。  
    
    :::image type="complex" source="../media/beginners-css-rule3.msft.png" alt-text="键入背景色" lightbox="../media/beginners-css-rule3.msft.png":::
       类型 `background-color`  
    :::image-end:::  
    
1.  键入 `green` 声明值并选择 `Enter` 。  
    
    :::image type="complex" source="../media/beginners-css-rule4.msft.png" alt-text="键入绿色" lightbox="../media/beginners-css-rule4.msft.png":::
       类型 `green`  
    :::image-end:::  
    
1.  将鼠标悬停在"主页 **"链接** 上。  链接的背景变为绿色。  
    
    :::image type="complex" source="../media/beginners-css-rule5.msft.png" alt-text="将鼠标悬停在"主页"链接上以显示其绿色背景" lightbox="../media/beginners-css-rule5.msft.png":::
       将鼠标悬停在"主页"链接上以显示其绿色背景  
    :::image-end:::  
    
## <a name="re-use-styles-across-pages-with-external-stylesheets"></a>在具有外部样式表的页面之间重新使用样式  

在上一步中，您将以下代码段作为内部样式表添加到 `contact.html` 。  

```html
...
    ...
        ...
        <style>
            li a, h1 {
              font-family: 'Courier New', Courier, Serif;
            }
        </style>
        ...
    ...
...
```  

如果要以相同方式 `index.html` 设置样式，该做什么？  如果您具有大量要应用样式的页面，该做什么？  您必须将内部样式表复制并粘贴到您的网站上的每个网页中。  完成以下操作以添加 **外部** 样式表，以允许您编写 CSS 一次，并应用到多个页面。  

1.  首先，刷新实时选项卡以删除你在 DevTools 中所做的更改。  
    
    :::image type="complex" source="../media/beginners-css-external1.msft.png" alt-text=" 刷新页面后，在 DevTools 中所做的更改将消失" lightbox="../media/beginners-css-external1.msft.png":::
        刷新页面后，在 DevTools 中所做的更改将消失  
    :::image-end:::  
    
1.  返回到编辑器 **选项卡并** 打开 `contact.html` 。  
    
    :::image type="complex" source="../media/beginners-css-external2.msft.png" alt-text="contact.html" lightbox="../media/beginners-css-external2.msft.png":::
       contact.html  
    :::image-end:::  
    
1.  删除与 `<style>` 之间、包括 `</style>` 和 `<style>` 之间的所有内容 `</style>` 。  
    
    :::image type="complex" source="../media/beginners-css-external3.msft.png" alt-text="样式标记已删除" lightbox="../media/beginners-css-external3.msft.png":::
       样式标记已删除  
    :::image-end:::  
    
1.  打开 `index.html` 并 `style="background-color: aliceblue;"` 删除 `<nav>` 标记。  现在，您已删除之前添加到网站的所有 CSS。  
    
    :::image type="complex" source="../media/beginners-css-external4.msft.png" alt-text="内联样式已从导航元素中删除" lightbox="../media/beginners-css-external4.msft.png":::
       内联样式已从导航元素中删除  
    :::image-end:::  
    
1.  选择 **"新建文件"。**  
    
    :::image type="complex" source="../media/beginners-css-external5.msft.png" alt-text="新文件对话框" lightbox="../media/beginners-css-external5.msft.png":::
       新文件对话框  
    :::image-end:::  
    
1.  替换为 `cool-file.js` 并选择 `style.css` **"添加文件"。**  
    
    :::image type="complex" source="../media/beginners-css-external6.msft.png" alt-text="Type style.css" lightbox="../media/beginners-css-external6.msft.png":::
       类型 `style.css`  
    :::image-end:::  
    
1.  将以下代码段添加到 `style.css` 文件。  
    
    ```css
    li a, h1 {
      font-family: 'Courier New', Courier, Serif;
    }
    a:hover {
      background-color: green;
    }
    nav {
      background-color: aliceblue;
    }
    ```  
    
    :::image type="complex" source="../media/beginners-css-external7.msft.png" alt-text="将代码添加到 style.css" lightbox="../media/beginners-css-external7.msft.png":::
       将代码添加到 `style.css`  
    :::image-end:::  
    
    确保您已创建外部样式表。 您的 HTML 不知道它是否存在。  
    
1.  打开 `index.html`。  
1.  添加到 `<link rel="stylesheet" href="style.css">` HTML。  
    
    ```html
    <head>
        ...
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="style.css">
    </head>
    ```  
    
    :::image type="complex" source="../media/beginners-css-external8.msft.png" alt-text="链接到 style.css" lightbox="../media/beginners-css-external8.msft.png":::
       链接到 `style.css`  
    :::image-end:::  
    
1.  打开 `contact.html` 文件并添加链接。  
    
    :::image type="complex" source="../media/beginners-css-external9.msft.png" alt-text="链接到 contact.html 中的 style.css" lightbox="../media/beginners-css-external9.msft.png":::
       链接到 `style.css` in `contact.html`  
    :::image-end:::  
    
1.  导航到 **活动选项卡**。 主页上一节和蓝色导航部分现在具有相同的字体。  
    
    :::image type="complex" source="../media/beginners-css-external10.msft.png" alt-text="主页" lightbox="../media/beginners-css-external10.msft.png":::
       主页  
    :::image-end:::  
    
1.  选择 **"联系人** "链接以导航到联系人页面。  联系人页面的格式与主页的格式相同。  
    
    :::image type="complex" source="../media/beginners-css-external11.msft.png" alt-text="联系人页面" lightbox="../media/beginners-css-external11.msft.png":::
       联系人页面  
    :::image-end:::  
    
## <a name="use-a-css-framework"></a>使用 CSS 框架  

**CSS 框架** 是由其他开发人员构建的样式集合，可更轻松地创建极具吸引力的网站。  框架提供了一组可以在页面元素上使用的样式，而不是自己定义样式。  

1.  复制以下代码：  
    
    ```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css">
    ```  
    
1.  打开编辑选项卡，然后将代码粘贴到 `contact.html` 。  
    
    :::image type="complex" source="../media/beginners-css-framework1.msft.png" alt-text="指向 contact.html 中的框架的链接" lightbox="../media/beginners-css-framework1.msft.png":::
       链接到 `contact.html`  
    :::image-end:::  
    
1.  打开 `index.html` 文件并添加代码。  
    
    :::image type="complex" source="../media/beginners-css-framework2.msft.png" alt-text="指向 index.html 中的框架的链接" lightbox="../media/beginners-css-framework2.msft.png":::
       链接到 `index.html`  
    :::image-end:::  
    
1.  返回到实时选项卡以查看更改。  虽然元素的背景颜色与 and 元素的字体相同，但其他元素的 `<nav>` `<li>` `<a>` 字体已更改。  
    
    :::image type="complex" source="../media/beginners-css-framework3.msft.png" alt-text="主页上的一些字体因框架而更改" lightbox="../media/beginners-css-framework3.msft.png":::
       主页上的一些字体因框架而更改  
    :::image-end:::  
    
### <a name="use-a-class"></a>使用类  

在上一节中，你向网页添加了 Bootstrap，这更改了网站上某些元素的字体。  CSS 框架可帮助你使用非常少的代码对页面进行重大更改。  完成以下操作以更改标头。  

1.  复制以下代码段。  
    
    ```html
    class="jumbotron jumbotron-fluid"  
    ```  
    
1.  将前面的代码段添加到 `<header>` 您的标记中 `index.html` 。  
    
    :::image type="complex" source="../media/beginners-css-jumbotron1.msft.png" alt-text="在 index.html 中添加类" lightbox="../media/beginners-css-jumbotron1.msft.png":::
       将类添加到 `index.html`  
    :::image-end:::  
    
1.  将代码添加到 `<header>` 您的标记中 `contact.html` 。  
    
    :::image type="complex" source="../media/beginners-css-jumbotron2.msft.png" alt-text="在 contact.html 中添加类" lightbox="../media/beginners-css-jumbotron2.msft.png":::
       将类添加到 `contact.html`  
    :::image-end:::  
    
1.  在实时选项卡中查看更改。 标题周围有一个大的灰色框。  
    
    :::image type="complex" source="../media/beginners-css-jumbotron3.msft.png" alt-text="标题现在四周有一个大的灰色框" lightbox="../media/beginners-css-jumbotron3.msft.png":::
       标题现在四周有一个大的灰色框  
    :::image-end:::  
    
### <a name="understand-classes"></a>了解类  

类使你可以将样式集合分配给任意元素。  将属性设置为后，使用以下代码段将多个样式应用到 `<header>` `class` 元素 `jumbotron` 。  

```css
.jumbotron {
  padding: 2rem 1rem;
  margin-bottom: 2rem;
  background-color: #e9ecef;
  border-radius: .3rem;
}
```  

类的一个优点是，它允许您将样式应用于所需的任何元素。  例如，假设你想要将某些元素的背景色设置为 `<p>` 紫色，但不是所有 `<p>` 元素。  使用以下代码段定义类中的样式。  

```css
.custom-background {
  background-color: purple;
}
```  

接下来，将类仅应用于 `<p>` 要设置样式的元素。  

```html
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
```  

### <a name="align-elements"></a>对齐元素  

完成以下操作以引导并提供用于对齐元素的类。  

1.  返回到编辑器选项卡并打开 `index.html` 。  
1.  添加到 `class="container-fluid"` 标记 `<body>` 。  
    
    :::image type="complex" source="../media/beginners-css-align1.msft.png" alt-text="添加容器流类" lightbox="../media/beginners-css-align1.msft.png":::
       添加 `container-fluid` 类  
    :::image-end:::  
    
1.  将你的 `<nav>` 和 `<main>` 元素包装在 `<div class="row">` .  请务必放在 `</div>` 后 `</main>` ，以便正确关闭新标记。  
    
    :::image type="complex" source="../media/beginners-css-align2.msft.png" alt-text="添加行" lightbox="../media/beginners-css-align2.msft.png":::
       添加行  
    :::image-end:::  
    
1.  添加到 `class="col-3"` 标记 `<nav>` 和 `class="col-9"` `<main>` 标记。  
    
    :::image type="complex" source="../media/beginners-css-align3.msft.png" alt-text="添加 col-3 和 col-9 类" lightbox="../media/beginners-css-align3.msft.png":::
       添加 `col-3` and `col-9` 类  
    :::image-end:::  
    
1.  在实时选项卡中查看更改。  
    
    :::image type="complex" source="../media/beginners-css-align4.msft.png" alt-text="导航内容现在位于主内容的左侧" lightbox="../media/beginners-css-align4.msft.png":::
       导航内容现在位于主内容的左侧  
    :::image-end:::  
    
## <a name="next-steps"></a>后续步骤  

恭喜！你已完成。  

*   更好地进行 Web 开发的最佳方法就是生成更多网站。  不要担心破坏内容。  只需在一边玩得一样有趣，然后尽可能学习。  
*   若要了解有关设置网页样式的信息，请导航到 [CSS 简介][MDNCssFirstSteps]。  
*   若要了解有关如何使用 DevTools 试验页面 CSS 的信息，请导航到"查看和更改 CSS 入门["。][DevtoolsCssIndex]  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!--- image links --->  

[ImageNewStyleRuleIcon]: ../media/new-style-rule-icon.msft.png  

<!--- links  --->  

[DevtoolsBeginnersHtml]: ./html.md "适用于初学者的 DevTools：HTML 和 DOM |Microsoft Docs"  
[DevtoolsCssIndex]: ../css/index.md "查看和更改 CSS 入门 | Microsoft 文档"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  

[GlitchCookedAmphibianIndex]: https://glitch.com/edit/#!/cooked-amphibian?path=index.html "index.html - 已|小故障"  

[MDNCssFirstSteps]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS "CSS 第一|MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处，](https://developers.google.com/web/tools/chrome-devtools/beginners/css) 由一名技术编写器 ([Chrome][KatherineJackson] DevTools\) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
