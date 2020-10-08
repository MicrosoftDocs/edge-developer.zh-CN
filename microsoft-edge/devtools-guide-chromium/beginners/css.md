---
description: CSS 入门
title: 初学者的 DevTools：开始使用 CSS
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: fe87b4f840c6d9dde3cdf6455700161ea8d8d31e
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993301"
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

# 初学者的 DevTools：开始使用 CSS  

在本教程中，你将了解如何使用 CSS 对网页进行样式。  你还将了解如何使用 Microsoft Edge DevTools 来试验 CSS 更改。  

以下文章是一系列教程中的第二个教程，可教你了解 web 开发和 Microsoft Edge DevTools 的基础知识。  您可以通过实际构建自己的网站来获得实际体验。  在下一步操作之前，不必完成第一个教程。  [设置代码](#set-up-your-code) 显示如何设置。  

> [!NOTE]
> 本教程适用于绝对初学者，重点介绍 **web 开发的基础知识** 和使用 DEVTOOLS 试验 CSS 的基础知识。  如果你需要仅关注 DevTools 的教程，请参阅 [查看和更改 CSS 入门][DevtoolsCssIndex]。  

在教程的开头，您的网站应如下图所示。  

:::image type="complex" source="../media/beginners-css-intro1.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-intro1.msft.png":::
   网站的当前外观  
:::image-end:::  

完成教程后，您的网站应如下图所示。  

:::image type="complex" source="../media/beginners-css-intro2.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-intro2.msft.png":::
   您的网站在教程结束时应看起来是什么样子  
:::image-end:::  

## 目标  

按照此教程更好地了解以下概念和任务。  

*   如何使用 CSS 对网页进行样式。  
*   如何使用 Microsoft Edge DevTools 来试验 CSS。  
*   CSS 和 CSS 框架之间的区别。  

您正在构建真正的网站。  

## 必备条件  

在尝试本教程之前，请完成以下先决条件。  

*   完整 [入门 html 和 dom，][DevtoolsBeginnersHtml] 或者确保你对 HTML 和 dom 的理解与该教程中所讲授的内容类似。  
*   下载 [Microsoft Edge][MicrosoftEdgeInsider] web 浏览器。  以下教程使用一组称为 Microsoft Edge DevTools 的 web 开发工具，这些工具内置于 Microsoft Edge 中。  

## 设置代码  

若要创建网站，必须首先完成以下操作来设置代码。  

> [!NOTE]
> 如果您已完成系列中的第一个教程，请跳至下一节。  继续使用最后一个教程中的代码， [HTML 和 DOM 入门][DevtoolsBeginnersHtml]。  

1.  打开 [源代码][GlitchCookedAmphibianIndex]。  浏览器的 "聚焦" 选项卡作为 " **编辑" 选项卡**进行引用。  
    
    :::image type="complex" source="../media/beginners-css-setup1.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-setup1.msft.png":::
       " **编辑** " 选项卡  
    :::image-end:::  
    
1.  选择 **cooked-amphibian**。  将弹出一个菜单。  
    
    :::image type="complex" source="../media/beginners-css-setup2.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-setup2.msft.png":::
       "项目选项" 菜单  
    :::image-end:::  

1.  选择 " **Remix Project**"。  问题创建您可以编辑的项目副本。  
    
    > [!NOTE]
    > 故障为新项目生成一个随机名称。  
    
1.  **在新窗口中选择 "****显示**并选择"。  将打开另一个选项卡，其中包含您的网站的实时视图。  浏览器的 "聚焦" 选项卡作为 " **实时" 选项卡**进行引用。  
    
    :::image type="complex" source="../media/beginners-css-setup3.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-setup3.msft.png":::
       " **实时" 选项卡**  
    :::image-end:::  

## 了解 CSS  

**CSS** 是确定网页布局和样式的计算机语言。  下图是带有边框的段落。  

:::image type="complex" source="../media/beginners-css-red_paragraph.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-red_paragraph.msft.png":::
   文本已采用 CSS 样式  
:::image-end:::  

以下代码片段是用于创建上图中的段落的 HTML 和 CSS 代码。  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`style="border: 1px dashed red; padding: 5px;"` 可能看起来很新。  其余内容应熟悉。  如果不是，请先 [开始使用 HTML 和 DOM][DevtoolsBeginnersHtml] ，然后再尝试以下部分。  

## 添加内联样式  

完成以下操作以使用 **嵌入式样式** 将样式应用到单个元素。  

1.  返回到 "编辑" 选项卡并打开 `index.html` 。  
    
    :::image type="complex" source="../media/beginners-css-inline1.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-inline1.msft.png":::
       `index.html`在 "编辑" 选项卡中打开  
    :::image-end:::  
    
1.  添加 `style="background-color: aliceblue;"` 到您 `<nav>` 的。  在下面的代码块中，第四行代码是你需要更改的代码。  剩下的就是这样，因此您可以确保将新代码放入正确的位置。  
    
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
    
1.  转到 " **实时" 选项卡** 以查看所做的更改！  现在，该分区的背景 `<nav>` 为蓝色。  
    
    :::image type="complex" source="../media/beginners-css-inline2.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-inline2.msft.png":::
       " **主页** " 和 " **联系人** " 链接后面的背景色现在为蓝色  
    :::image-end:::  
    
## 在具有内部样式表的单个页面上重新使用样式  

在前面的代码段中，内联样式将样式应用于单个 `<p>` 标记。  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

如果您希望您的 `<p>` 网页上的所有元素的样式设置方式相同，该怎么办？  您必须将代码复制并粘贴到 `<p>` 您的网站上的每个标记中。  这是大量的时间和精力。  如果需要进行编辑，则必须再次更改每个标签。  完成以下操作以使用 **内部样式表** 编写 CSS 一次，以便它应用于多个元素。  

1.  在 "实时" 选项卡中，选择 " **联系人** " 以转到 "联系人" 页面。  请注意 " **家庭** " 和 " **联系人**" 的字体。  
    
    :::image type="complex" source="../media/beginners-css-internal1.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-internal1.msft.png":::
       "联系人" 页面  
    :::image-end:::  
    
1.  在 " **编辑器" 选项卡**中，转到 `contact.html` 。  
1.  将以下代码添加到 `contact.html` 。  请记住，"行" `<style>` 和 "结束" 行 `</style>` 是你需要添加的内容。  其他代码就在这里，您知道在哪里放置新代码。  
    
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
    
1.  返回到 " **实时" 选项卡**。  
1.  选择 " **联系人** " 以返回到联系人页。  **家庭**和**联系人**的字体已更改。  
    
    :::image type="complex" source="../media/beginners-css-internal2.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-internal2.msft.png":::
       **主页**和**联系人**链接的字体已更改  
    :::image-end:::  
    
### 了解内部样式表  

内部样式表使用 **选择器**应用样式。  选择器是可应用于一个或多个 HTML 元素的模式。  上面的代码段添加了以下样式。  

```html
<style>
    li a {
      font-family: 'Courier New', Courier, Serif;
    }
</style>
```  

`li a` 是转换为 " `<li>` 包含元素的任何元素" 的选择器 `<a>` 。  浏览器将更改 " **主页** " 和 " **联系人** " 链接的字体，因为每个标记组都与模式匹配。  

```html
<li><a href="/">Home</a></li>
<li><a href="/contact.html">Contact</a></li>
```  

`font-family: 'Courier New', Courier, serif` 是 **声明**。  声明由以下两个部分组成。  

:::row:::
   :::column span="1":::
      **属性**  
   :::column-end:::
   :::column span="1":::
      `font-family`  
   :::column-end:::
   :::column span="2":::
      该属性描述你可以更改元素样式的一般方式。  
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
      该值确切描述元素样式应如何更改。  
   :::column-end:::
:::row-end:::  

例如， `font-family: 'Courier New', Courier, serif` 为浏览器提供以下指令： "将匹配模式的元素的字体设置 `li a` 为 `'Courier New'` 。  如果该字体不可用，请使用 `Courier` 。  如果该功能不可用，请使用 `serif` 。  

### 将多个选择器添加到规则集  

类似于下面所示的 CSS 代码块称为 " **规则集**"。  

```css
li a {
  font-family: 'Courier New', Courier, monospace;
}
```  

完成以下操作以使用逗号将多个选择器添加到规则集。  

1.  在 " **编辑器" 选项卡**中，打开 `contact.html` 。  
1.  `li a`键入后 `, h1` 。  
    
    ```html
    <style>
        li a, h1 {
          font-family: 'Courier New', Courier, Serif;
        }
    </style>
    ```  
    
    上面的代码片段告诉浏览器对元素的样式与 `<h1>` 与模式匹配的元素的样式相同 `li a` 。  
    
1.  转到 " **实时" 选项卡**。  
1.  选择 **联系人** 链接返回到联系人页。  现在，请 **与我联系！** 的字体与导航链接的字体相同。  
    
    :::image type="complex" source="../media/beginners-css-multiple1.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-multiple1.msft.png":::
       文本 **与我联系！** 现在与 " **主页** " 和 " **联系人** " 链接的字体相同  
    :::image-end:::  
    
## 试用 DevTools  

随着您继续在 web 开发中成为专家，您可能会发现 CSS 非常棘手。  你可以编写一些 CSS，并希望它以一种方式显示，但浏览器执行完全不同的操作。  Microsoft Edge DevTools 使你可以轻松地体验更改，并立即查看更改对页面有何影响。  

### 将声明添加到 DevTools 中的现有 rulest  

完成以下操作以循环访问现有元素的样式，将声明添加到现有规则集。  

1.  将鼠标悬停在 " **主页** " 链接上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。  
    
    :::image type="complex" source="../media/beginners-css-add1.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-add1.msft.png":::
       检查 "主页" 链接  
    :::image-end:::  
    
    DevTools 将在您的页面旁打开。  表示 Home 链接的代码在 `<a href="/">Home</a>` DOM 树中突出显示为蓝色。  代码片段和预览应熟悉 [HTML 和 DOM 入门][DevtoolsBeginnersHtml]。  
    
    :::row:::
       :::column span="":::
          下图中，在 `font-family: 'Courier New', Courier, serif` `contact.html` DOM 树下方的 " **样式** " 选项卡中显示了之前添加到的声明。  
          
          :::image type="complex" source="../media/beginners-css-add2.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-add2.msft.png":::
             " **样式** " 选项卡位于 DOM 树的下方  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          如果 DevTools 窗口是宽的，则 "样式" 选项卡位于 DOM 树的右侧。  
          
          :::image type="complex" source="../media/beginners-css-add3.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-add3.msft.png":::
             " **样式** " 选项卡位于 DOM 树的右侧  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  选择下面的空行 `font-family: 'Courier New', Courier, Serif` 以添加新声明。  
    
    :::image type="complex" source="../media/beginners-css-add4.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-add4.msft.png":::
       添加新声明  
    :::image-end:::  
    
1.  键入 `color` 并选择 `Enter` 。  "自动完成" UI 建议您键入时的选项。  
    
    :::image type="complex" source="../media/beginners-css-add5.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-add5.msft.png":::
       类型 `color`  
    :::image-end:::  
    
1.  键入 `magenta` 并选择 `Enter` 。  "联系人" 页面上的所有文本现在均为 "洋红"。  
    
    :::image type="complex" source="../media/beginners-css-add6.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-add6.msft.png":::
       类型 `magenta`  
    :::image-end:::  
    
### 在 DevTools 中编辑声明  

完成以下操作以在 DevTools 中编辑现有声明。  

1.  选择旁边的洋红色方块 `magenta` 。  将弹出一个颜色选取器。  
    
    :::image type="complex" source="../media/beginners-css-edit1.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-edit1.msft.png":::
       颜色选取器  
    :::image-end:::  
    
1.  使用拾色器将字体文本更改为您喜欢的颜色。  
    
    :::image type="complex" source="../media/beginners-css-edit2.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-edit2.msft.png":::
       通过拾色器将字体颜色更改为紫色  
    :::image-end:::  
    
### 在 DevTools 中添加新的规则集  

完成以下操作以在 DevTools 中添加新的规则集。  

1.  选择 " **新建样式规则** \ (![ 新样式规则 ][ImageNewStyleRuleIcon] \ ) 它位于" **. cls**"旁边。  将显示一个包含选择器的空规则集 `a` 。  
    
    :::image type="complex" source="../media/beginners-css-rule1.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-rule1.msft.png":::
       添加新规则  
    :::image-end:::  
    
1.  用 `a:hover` 取代 `a`。  
    
    :::image type="complex" source="../media/beginners-css-rule2.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-rule2.msft.png":::
       替换 `a` 为 `a:hover`  
    :::image-end:::  
    
    `:hover` 是 **伪类**。  对可能进入特殊状态的样式元素使用伪类。  例如， `a:hover` 仅当你将鼠标悬停在某个元素上方时，该样式才会生效 `<a>` 。  
    
1.  在括号之间进行选择以添加新的声明。  
1.  键入 `background-color` 声明名称，然后选择 `Enter` 。  
    
    :::image type="complex" source="../media/beginners-css-rule3.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-rule3.msft.png":::
       类型 `background-color`  
    :::image-end:::  
    
1.  `green`声明值的类型，然后选择 `Enter` 。  
    
    :::image type="complex" source="../media/beginners-css-rule4.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-rule4.msft.png":::
       类型 `green`  
    :::image-end:::  
    
1.  将鼠标悬停在 " **开始** " 链接上。  链接的背景变为绿色。  
    
    :::image type="complex" source="../media/beginners-css-rule5.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-rule5.msft.png":::
       将鼠标悬停在 Home 链接上以显示绿色背景  
    :::image-end:::  
    
## 跨页面使用外部样式表重新使用样式  

在上一步中，你将以下代码段添加为内部样式表 `contact.html` 。  

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

如果你想要以 `index.html` 相同的方式设置样式，该怎么办？  如果您有大量页面需要应用样式，该怎么办？  您必须将内部样式表复制并粘贴到您的网站上的每一个网页中。  完成以下操作以添加 **外部样式表** ，以允许你编写 CSS 一次并将其应用于多个页面。  

1.  首先，重新加载 "实时" 选项卡以删除您在 DevTools 中所做的更改。  
    
    :::image type="complex" source="../media/beginners-css-external1.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-external1.msft.png":::
        刷新页面后，在 DevTools 中所做的更改将不再存在  
    :::image-end:::  
    
1.  返回 " **编辑器" 选项卡** ，然后打开 `contact.html` 。  
    
    :::image type="complex" source="../media/beginners-css-external2.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-external2.msft.png":::
       contact.html  
    :::image-end:::  
    
1.  删除与之间的所有内容 `<style>` `</style>` ，包括 `<style>` 和 `</style>` 。  
    
    :::image type="complex" source="../media/beginners-css-external3.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-external3.msft.png":::
       已删除样式标记  
    :::image-end:::  
    
1.  转到 `index.html` 并 `style="background-color: aliceblue;"` 从标记中删除 `<nav>` 。  您现在已删除以前添加到网站的所有 CSS。  
    
    :::image type="complex" source="../media/beginners-css-external4.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-external4.msft.png":::
       内联样式已从导航元素中删除  
    :::image-end:::  
    
1.  选择 " **新建文件**"。  
    
    :::image type="complex" source="../media/beginners-css-external5.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-external5.msft.png":::
       "新建文件" 对话框  
    :::image-end:::  
    
1.  替换 `cool-file.js` 为 `style.css` ，然后选择 " **添加文件**"。  
    
    :::image type="complex" source="../media/beginners-css-external6.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-external6.msft.png":::
       类型 `style.css`  
    :::image-end:::  
    
1.  将以下代码片段添加到 `style.css` 文件中。  
    
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
    
    :::image type="complex" source="../media/beginners-css-external7.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-external7.msft.png":::
       将代码添加到 `style.css`  
    :::image-end:::  
    
    确保已创建外部样式表。 你的 HTML 不知道它是否存在。  
    
1.  打开 `index.html`。  
1.  添加 `<link rel="stylesheet" href="style.css">` 到你的 HTML。  
    
    ```html
    <head>
        ...
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="style.css">
    </head>
    ```  
    
    :::image type="complex" source="../media/beginners-css-external8.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-external8.msft.png":::
       链接到 `style.css`  
    :::image-end:::  
    
1.  打开 `contact.html` 文件并在其中添加链接。  
    
    :::image type="complex" source="../media/beginners-css-external9.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-external9.msft.png":::
       链接到 `style.css` `contact.html`  
    :::image-end:::  
    
1.  转到 " **实时" 选项卡**。 现在，主页的字体与上一节中的字体相同，并具有蓝色导航部分。  
    
    :::image type="complex" source="../media/beginners-css-external10.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-external10.msft.png":::
       主页  
    :::image-end:::  
    
1.  选择 **联系人** 链接转到 "联系人" 页面。  "联系人" 页面的格式与 "主页" 的格式相同。  
    
    :::image type="complex" source="../media/beginners-css-external11.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-external11.msft.png":::
       "联系人" 页面  
    :::image-end:::  
    
## 使用 CSS 框架  

**CSS 框架** 是由其他开发者构建的样式的集合，可使创建引人注目的网站更容易。  框架提供了可在页面元素上使用的样式集合，而不是自己定义样式。  

1.  复制以下代码：  
    
    ```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css">
    ```  
    
1.  转到 "编辑" 选项卡，然后将代码粘贴到 `contact.html` 。  
    
    :::image type="complex" source="../media/beginners-css-framework1.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-framework1.msft.png":::
       链接到中的框架 `contact.html`  
    :::image-end:::  
    
1.  打开 `index.html` 文件并在其中添加代码。  
    
    :::image type="complex" source="../media/beginners-css-framework2.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-framework2.msft.png":::
       链接到中的框架 `index.html`  
    :::image-end:::  
    
1.  返回到 "实时" 选项卡以查看所做的更改。  虽然元素的背景色 `<nav>` 和 `<li>` 和元素的字体 `<a>` 相同，但其他元素的字体已更改。  
    
    :::image type="complex" source="../media/beginners-css-framework3.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-framework3.msft.png":::
       主页面上的某些字体因框架而发生更改  
    :::image-end:::  
    
### 使用类  

在最后一节中，你将引导数据库添加到网页，这将更改网站上某些元素的字体。  CSS 框架可帮助你通过非常少的代码对页面进行重大更改。  完成以下操作以更改页眉。  

1.  复制以下代码片段。  
    
    ```html
    class="jumbotron jumbotron-fluid"  
    ```  
    
1.  将上一个代码段添加到 `<header>` 中的标记 `index.html` 。  
    
    :::image type="complex" source="../media/beginners-css-jumbotron1.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-jumbotron1.msft.png":::
       将类添加到 `index.html`  
    :::image-end:::  
    
1.  将代码添加到 `<header>` 中的标记 `contact.html` 。  
    
    :::image type="complex" source="../media/beginners-css-jumbotron2.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-jumbotron2.msft.png":::
       将类添加到 `contact.html`  
    :::image-end:::  
    
1.  在 "实时" 选项卡中查看所做的更改。 页眉周围有一个大灰的框。  
    
    :::image type="complex" source="../media/beginners-css-jumbotron3.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-jumbotron3.msft.png":::
       标题现在周围有一个大灰框  
    :::image-end:::  
    
### 了解类  

通过类，你可以将样式集合分配给任意元素。  `<header>`将属性设置为后，使用以下代码片段对元素应用多个样式 `class` `jumbotron` 。  

```css
.jumbotron {
  padding: 2rem 1rem;
  margin-bottom: 2rem;
  background-color: #e9ecef;
  border-radius: .3rem;
}
```  

类的一个优点是允许你将样式应用到所需的任何元素。  例如，假设你想要将某些元素的背景色设置 `<p>` 为紫色，而不是所有 `<p>` 元素。  使用以下代码片段定义类中的样式。  

```css
.custom-background {
  background-color: purple;
}
```  

接下来，将该类应用于 `<p>` 要样式的元素。  

```html
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
```  

### 对齐元素  

完成以下操作以执行引导并提供用于对齐元素的类。  

1.  返回 "编辑器" 选项卡，然后打开 `index.html` 。  
1.  添加 `class="container-fluid"` 到您的 `<body>` 标签。  
    
    :::image type="complex" source="../media/beginners-css-align1.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-align1.msft.png":::
       添加 `container-fluid` 类  
    :::image-end:::  
    
1.  将您的 `<nav>` 和 `<main>` 元素包装在中 `<div class="row">` 。  请确保放 `</div>` `</main>` 在 "" 之后，才能正确关闭新标记。  
    
    :::image type="complex" source="../media/beginners-css-align2.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-align2.msft.png":::
       添加行  
    :::image-end:::  
    
1.  添加 `class="col-3"` 到您的 `<nav>` 标签和 `class="col-9"` `<main>` 标签。  
    
    :::image type="complex" source="../media/beginners-css-align3.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-align3.msft.png":::
       添加 `col-3` 和 `col-9` 类  
    :::image-end:::  
    
1.  在 "实时" 选项卡中查看所做的更改。  
    
    :::image type="complex" source="../media/beginners-css-align4.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-align4.msft.png":::
       导航内容现在位于主要内容的左侧  
    :::image-end:::  
    
## 后续步骤  

恭喜！您已完成。  

*   在 web 开发中获取更好的最佳方式是构建更多网站。  不要担心会破坏内容。  只要有兴趣，您就可以轻松掌握。  
*   若要了解有关设置网页样式的详细信息，请参阅 [CSS 简介][MDNCssFirstSteps]。  
*   若要了解有关如何使用 DevTools 来试验页面 CSS 的详细信息，请参阅 [查看和更改 Css 入门][DevtoolsCssIndex]。  

<!--- image links --->  

[ImageNewStyleRuleIcon]: ../media/new-style-rule-icon.msft.png  

<!--- links  --->  

[DevtoolsBeginnersHtml]: ./html.md "初学者的 DevTools： HTML 和 DOM 入门 |Microsoft 文档"  
[DevtoolsCssIndex]: ../css/index.md "开始使用查看和更改 CSS |Microsoft 文档"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  

[GlitchCookedAmphibianIndex]: https://glitch.com/edit/#!/cooked-amphibian?path=index.html "index.html-cooked-amphibian |故障"  

[MDNCssFirstSteps]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS "CSS 优先步骤 |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/beginners/css) ，由 [Katherine 杰克逊][KatherineJackson] (技术编写器暂存，Chrome DevTools \ ) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
