---
title: 初学者的 DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 0064f0427b6bd5689e888cccfe2c650492898bb2
ms.sourcegitcommit: 8bfa239274e7a4856b961b9cf163b08d96463c10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "10581592"
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

这是一系列教程中的第二个教程，可教你了解 web 开发和 Microsoft Edge DevTools 的基础知识。  您可以通过实际构建自己的网站来获得实际体验。  在执行此操作之前，您无需完成第一个教程。  您可以从这里开始。  [设置代码](#set-up-your-code)显示如何设置。  

> [!NOTE]
> 本教程适用于绝对初学者，重点介绍**web 开发的基础知识**和使用 DEVTOOLS 试验 CSS 的基础知识。  如果你需要仅关注 DevTools 的教程，请参阅[查看和更改 CSS 入门][DevtoolsCssIndex]。  

当前您的网站如下所示：  

> ##### 图 1  
> 网站的当前外观  
> ![网站的当前外观][ImageCssIntro1]  

完成教程后，它将如下所示：  

> ##### 图 2  
> 网站在教程结束时的外观  
> ![网站在教程结束时的外观][ImageCssIntro2]  

## 目标   

本教程结束时，你将了解：  

*   如何使用 CSS 对网页进行样式。  
*   如何使用 Microsoft Edge DevTools 来试验 CSS。  
*   CSS 和 CSS 框架之间的区别。  

您还有一个真正的网站！  

## 必备条件   

在尝试本教程之前，请完成以下先决条件：  

*   完整[入门 html 和 dom，][DevToolsBeginnersHtml]或者确保你对 HTML 和 dom 的理解类似于本教程中的教授。  
*   下载[Microsoft Edge][MicrosoftEdgeInsider] web 浏览器。  本教程使用一组称为 Microsoft Edge DevTools 的 web 开发工具，这些工具内置于 Microsoft Edge 中。  

## 设置代码   

为了开始创建您的网站，您需要设置代码：  

1.  **如果您已完成本系列中的第一个教程，请跳过本部分！  继续使用最后一个教程中的代码， [HTML 和 DOM 入门][DevToolsBeginnersHtml]。**  
1.  打开[源代码][GlitchCookedAmphibianIndex]。  浏览器的此选项卡将称为 "**编辑" 选项卡**。  
    
    > ##### 图 3  
    > "编辑" 选项卡  
    > !["编辑" 选项卡][ImageCssSetup1]  
    
1.  单击 " **cooked-amphibian**"。  将弹出一个菜单。  
    
    > ##### 图 4  
    > "项目选项" 菜单  
    > !["项目选项" 菜单][ImageCssSetup2]  

1.  单击 " **Remix Project**"。  问题创建可编辑的项目副本。  
    
    > [!NOTE]
    > 故障为新项目生成一个随机名称。  
    
1.  单击 "**显示**"，然后**在新窗口中**选择。  将打开另一个选项卡，其中包含您的网站的实时视图。  浏览器的此选项卡将称为 "**实时" 选项卡**。  
    
    > ##### 图 5  
    > "实时" 选项卡  
    > !["实时" 选项卡][ImageCssSetup3]  

## 了解 CSS   

**CSS**是确定网页布局和样式的计算机语言。  例如，下面是带有边框的段落：  

> ##### 图 6  
> 此功能已设置了 CSS 样式  
> ![此功能已设置了 CSS 样式][ImageCssStyled]  

下面是用于创建该段落的 HTML 和 CSS 代码：  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`style="border: 1px dashed red; padding: 5px;"` 可能看起来很新。  其余内容应熟悉。  如果不是，请在尝试本教程之前完成有关[HTML 和 DOM 的入门][DevToolsBeginnersHtml]。  

## 添加内联样式   

如果要将样式应用于单个元素，请使用**内联样式**。  立即试用：  

1.  返回到 "编辑" 选项卡并打开 `index.html` 。  
    
    > ##### 图 7  
    > `index.html`  
    > ![index.html][ImageCssInline1]  

1.  添加 `style="background-color: aliceblue;"` 到您 `<nav>` 的。  在下面的代码块中，第四行代码是你需要更改的代码。  剩下的只是这样，您就可以确保将新代码放在正确的位置。  
    
    ```html
    ...
        ...
            <header>
                <p>Welcome to my site!</p>
            </header>
            <nav style="background-color: aliceblue;">
                <ul>
                    <li><a href="/">Home</a></li>
                    ...
                ...
            ...
        ...
    ...
    ```  

1.  转到 "**实时" 选项卡**以查看所做的更改！  现在，该分区的背景 `<nav>` 为蓝色。  
    
    > ##### 图 8  
    > "主页" 和 "联系人" 链接后面的背景色现在为蓝色  
    > !["主页" 和 "联系人" 链接后面的背景色现在为蓝色][ImageCssInline2]  

## 在具有内部样式表的单个页面上重新使用样式   

以前，你看到了一种将样式应用于单个标记的内联样式， `<p>` 如下所示：  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

如果您希望您的 `<p>` 网页上的所有元素的样式设置方式相同，该怎么办？  您必须将代码复制并粘贴到 `<p>` 您的网站上的每个标记中。  这是很多时间和精力。  如果需要进行编辑，则必须再次更改每个标签。  **内部样式表**允许你编写一次 CSS，以便它应用于多个元素。  立即试用：  

1.  在 "实时" 选项卡中，单击 "**联系人**" 以转到联系人页。  请注意 "**家庭**" 和 "**联系人**" 的字体。  
    
    > ##### 图 9  
    > "联系人" 页面  
    > !["联系人" 页面][ImageCssInternal1]  

1.  在 "**编辑器" 选项卡**中，转到 `contact.html` 。  
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
    
1.  返回到 "**实时" 选项卡**。  
1.  单击 "**联系人**" 返回到联系人页。  **家庭**和**联系人**的字体已更改。  
    
    > ##### 图 10  
    > 主页和联系人链接的字体已更改  
    > ![主页和联系人链接的字体已更改][ImageCssInternal2]  
    
### 了解内部样式表   

内部样式表使用**选择器**应用样式。  选择器是可应用于一个或多个 HTML 元素的模式。  例如，在前面的代码中：  

```html
...
    ...
        ...
        <style>
            li a {
              font-family: 'Courier New', Courier, Serif;
            }
        </style>
        ...
    ...
...
```  

`li a` 是转换为 "任何包含" 的选择器 `<li>` `<a>` 。  浏览器将更改 "**主页**" 和 "**联系人**" 链接的字体，因为它们与此模式匹配。  

```html
...
    ...
        ...
            ...
                <li><a href="/">Home</a></li>
                <li><a href="/contact.html">Contact</a></li>
                ...
            ...
        ...
    ...
...
```  

`font-family: 'Courier New', Courier, serif` 是**声明**。  声明由两部分组成：**属性**和**值**。  `font-family` 是属性， `'Courier New', Courier, serif` 它是该属性的值。  该属性描述了你可以更改元素的样式的常规方式，而值显示了它应如何更改。  例如， `font-family: 'Courier New', Courier, serif` 向浏览器提供此指令： "将与模式匹配的元素的字体设置 `li a` 为 `'Courier New'` 。  如果该字体不可用，请使用 `Courier` 。  如果该功能不可用，请使用 `serif` 。  

### 将多个选择器添加到规则集   

类似于下面所示的 CSS 代码块称为 "**规则集**"。  

```css
li a {
  font-family: 'Courier New', Courier, monospace;
}
```  

使用逗号将多个选择器添加到规则集。  立即试用：  

1.  在 "**编辑器" 选项卡**中，打开 `contact.html` 。  
1.  `li a`键入后 `, h1` 。  

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

    这将告知浏览器对 `<h1>` 元素样式的样式与与模式匹配的元素的样式一样 `li a` 。  
    
1.  转到 "**实时" 选项卡**。  
1.  单击**联系人**链接返回到联系人页。  现在，请**与我联系！** 的字体与导航链接的字体相同。  
    
    > ##### 图 11  
    > 文本 "联系我！" 现在与 "主页" 和 "联系人" 链接的字体相同  
    > ![文本与我联系！  现在与 "主页" 和 "联系人" 链接的字体相同][ImageCssMultiple1]  

## 试用 DevTools   

在你继续迁移到主 web 开发时，你会发现 CSS 可能会很难。  你将编写一些 CSS，并希望它以一种方式显示，但浏览器执行完全不同的操作。  Microsoft Edge DevTools 使你可以轻松地体验更改，并立即查看这些更改对页面的影响。  

### 将声明添加到 DevTools 中的现有 rulest   

当你希望循环访问现有元素的样式时，请将声明添加到现有的规则集。  立即试用：  

1.  右键单击 "**主页**" 链接，然后选择 "**检查**"。  
    
    > ##### 图 12  
    > 检查主链接  
    > ![检查主链接][ImageCssAdd1]  
    
    DevTools 将在您的页面旁打开。  表示 Home 链接的代码在 `<a href="/">Home</a>` DOM 树中突出显示为蓝色。  应熟悉[HTML 和 DOM 入门][DevToolsBeginnersHtml]。  在 DOM 树下方的 "**样式**" 选项卡中，你可以看到 `font-family: 'Courier New', Courier, serif` 你之前添加到的声明 `contact.html` 。  
    
    > ##### 图 13  
    > "样式" 选项卡位于 DOM 树的下方  
    > !["样式" 选项卡位于 DOM 树的下方][ImageCssAdd2]  
    
    如果 DevTools 窗口是宽的，则 "样式" 选项卡位于 DOM 树的右侧。  
    
    > ##### 图 14  
    > "样式" 选项卡位于 DOM 树的右侧  
    > !["样式" 选项卡位于 DOM 树的右侧][ImageCssAdd3]  
    
1.  单击下面的空白 `font-family: 'Courier New', Courier, Serif` 以添加新声明。  
    
    > ##### 图 15  
    > 添加新声明  
    > ![添加新声明][ImageCssAdd4]  
    
1.  键入 `color` ，然后按 `Enter` 。  "自动完成" UI 建议您键入时的选项。  
    
    > ##### 图 16  
    > 键入 `color`  
    > ![键入颜色][ImageCssAdd5]  

1.  键入 `magenta` ，然后 `Enter` 再次按。  "联系人" 页面上的所有文本现在均为 "洋红"。  
    
    > ##### 图 17  
    > 键入 `magenta`  
    > ![键入洋红][ImageCssAdd6]  
    
### 在 DevTools 中编辑声明   

您也可以在 DevTools 中编辑现有声明。  立即试用：  

1.  单击旁边的洋红色方块 `magenta` 。  将弹出一个颜色选取器。  
    
    > ##### 图18  
    > 颜色选取器  
    > ![颜色选取器][ImageCssEdit1]  
    
1.  使用拾色器将字体文本更改为您喜欢的颜色。  
    
    > ##### 图19  
    > 通过颜色选取器将字体颜色更改为紫色  
    > ![通过颜色选取器将字体颜色更改为紫色][ImageCssEdit2]  

### 在 DevTools 中添加新的规则集   

你还可以在 DevTools 中添加新的规则集。  立即试用：  

1.  单击 "**新建样式规则**" 下的 "新建 ![ 样式规则" ][ImageNewStyleRuleIcon] **。**  将显示一个包含选择器的空规则集 `a` 。  
    
    > ##### 图20  
    > 添加新规则  
    > ![添加新规则][ImageCssRule1]  
    
1.  用 `a:hover` 取代 `a`。  
    
    > ##### 图21  
    > 替换 `a` 为 `a:hover`  
    > ![将 with a:hover 替换为][ImageCssRule2]  
    
    `:hover` 是**伪类**。  当元素进入特殊状态时，使用伪类对元素进行样式。  例如， `a:hover` 只有当你将鼠标悬停在某个元素上时，该样式才会生效 `<a>` 。  
    
1.  在括号之间单击以添加新的声明。  
1.  键入 `background-color` 声明名称，然后按 `Enter` 。  
    
    > ##### 图22  
    > 键入 `background-color`  
    > ![键入背景色][ImageCssRule3]  
    
1.  键入 `green` 声明值，然后按 `Enter` 。  
    
    > ##### 图23  
    > 键入 `green`  
    > ![键入绿色][ImageCssRule4]  
    
1.  将鼠标悬停在 "**开始**" 链接上。  链接的背景变为绿色。  
    
    > ##### 图24  
    > 将鼠标悬停在 Home 链接上以显示绿色背景  
    > ![将鼠标悬停在 Home 链接上以显示绿色背景][ImageCssRule5]  
    
## 跨页面使用外部样式表重新使用样式   

之前，您已将此内部样式表添加到 `contact.html` ：  

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

如果你想要以 `index.html` 相同的方式设置样式，该怎么办？  如果您有*一千*个页面，并且想要将这些样式应用到所有这些页面，该怎么办？  您必须将此内部样式表复制并粘贴到您的网站上的每一个网页中。  **外部样式表**允许你在将 CSS 应用到多个页面后编写它。  立即试用：  

1.  首先，重新加载 "实时" 选项卡以删除您在 DevTools 中所做的更改。  
    
    > ##### 图25  
    >  重新加载页面后，DevTools 中所做的更改已丢失  
    > ![ 重新加载页面后，DevTools 中所做的更改已丢失][ImageCssExternal01]  
    
1.  返回 "**编辑器" 选项卡**，然后打开 `contact.html` 。  
    
    > ##### 图26  
    > `contact.html`  
    > ![联系 .html][ImageCssExternal02]  
    
1.  删除与之间的所有内容 `<style>` `</style>` ，包括 `<style>` 和 `</style>` 。  
    
    > ##### 图27  
    > 已删除样式标记  
    > ![已删除样式标记][ImageCssExternal03]  
    
1.  转到 `index.html` 并 `style="background-color: aliceblue;"` 从标记中删除 `<nav>` 。  您现在已删除以前添加到网站的所有 CSS。  
    
    > ##### 图28  
    > 内联样式已从导航元素中删除  
    > ![内联样式已从导航元素中删除][ImageCssExternal04]  

1.  单击 "**新建文件**"。  
    
    > ##### 图29  
    > "新建文件" 对话框  
    > !["新建文件" 对话框][ImageCssExternal05]  
    
1.  替换 `cool-file.js` 为 `style.css` ，然后单击 "**添加文件**"。  
    
    > ##### 图30  
    > 键入 `style.css`  
    > ![键入样式 .css][ImageCssExternal06]  
    
1.  将此代码粘贴到 `style.css` ：  
    
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
    
    > ##### 图31  
    > 将代码添加到 `style.css`  
    > ![将代码添加到 style][ImageCssExternal07]  
    
    此时，你已创建了一个外部样式表，但你的 HTML 不知道它是否存在。  
    
1.  打开 `index.html`。  
1.  添加 `<link rel="stylesheet" href="style.css">` 到你的 HTML。  
    
    ```html
    ...
        <head>
            ...
            <meta name="viewport" content="width=device-width, initial-scale=1">
            <link rel="stylesheet" href="style.css">
        </head>
        ...
    ...
    ```  

    > ##### 图32  
    > 链接到 `style.css`  
    > ![链接到样式 .css][ImageCssExternal08]  

1.  转到此处 `contact.html` 并添加链接。  
    
    > ##### 图33  
    > 链接到 `style.css` `contact.html`  
    > ![链接到 "style" 中的 ".css"。 html][ImageCssExternal09]  

1.  转到 "**实时" 选项卡**。 现在，主页的字体与上一节中的字体相同，并具有蓝色导航部分。  
    
    > ##### 图34  
    > 主页  
    > ![主页][ImageCssExternal10]  
    
1.  单击**联系人**链接转到 "联系人" 页面。  "联系人" 页面的格式与 "主页" 的格式相同。  
    
    > ##### 图35  
    > "联系人" 页面  
    > !["联系人" 页面][ImageCssExternal11]  
    
## 使用 CSS 框架   

**CSS 框架**是由其他开发者构建的样式的集合，可使创建引人注目的网站更容易。  框架为你提供可在页面元素上使用的样式集合，而不是自己定义样式。  

1.  复制以下代码：  
    
    ```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css">
    ```  
    
1.  转到 "编辑" 选项卡，然后将代码粘贴到 `contact.html` 。  
    
    > ##### 图36  
    > 链接到中的框架 `contact.html`  
    > ![链接到 contact 中的框架][ImageCssFramework1]  
    
1.  将代码粘贴到 `index.html` 中。  
    
    > ##### 图37  
    > 链接到中的框架 `index.html`  
    > ![链接到索引 html 中的框架][ImageCssFramework2]  
    
1.  返回到 "实时" 选项卡以查看所做的更改。  虽然元素的背景色 `<nav>` 和元素的字体 `li a` 相同，但其他元素的字体已更改。  
    
    > ##### 图38  
    > 主页上的某些字体因框架而发生更改  
    > ![主页上的某些字体因框架而发生更改][ImageCssFramework3]  

### 使用类   

在最后一节中，你将引导数据库添加到网页，这将更改网站上某些元素的字体。  CSS 框架可帮助你通过非常少的代码对页面进行重大更改。  通过更改页眉立即试用：  

1.  复制此代码：  
    
    ```html
    class="jumbotron jumbotron-fluid"  
    ```  
    
1.  将此代码添加到 `<header>` 中的标签 `index.html` 。  
    
    > ##### 图39  
    > 添加类 `index.html`  
    > ![在索引 html 中添加类][ImageCssJumbotron1]  
    
1.  将代码添加到您 `<header>` 的标签 `contact.html` 。  
    
    > ##### 图40  
    > 添加类 `contact.html`  
    > ![将课堂添加到 contact. html][ImageCssJumbotron2]  
    
1.  在 "实时" 选项卡中查看所做的更改。 现在，您的页眉周围有一个大灰的框。  
    
    > ##### 图41  
    > 标题现在周围有一个大灰框  
    > ![标题现在周围有一个大灰框][ImageCssJumbotron3]  
    
### 了解类   

通过类，你可以将样式集合分配给任意元素。  例如，将 `class` 标记的属性设置 `<header>` 为对 `jumbotron` 它们应用以下样式：  

```css
.jumbotron {
  padding: 2rem 1rem;
  margin-bottom: 2rem;
  background-color: #e9ecef;
  border-radius: .3rem;
}
```  

类的一个优点是，它们允许你将样式应用到所需的任何元素。  例如，假设你想要将*某些*元素的背景色设置 `<p>` 为紫色，而不是*所有*元素。  可以在类中定义样式：  

```css
.custom-background {
  background-color: purple;
}
```  

然后将该类应用于 `<p>` 要样式的元素：  

```html
...
    ...
        ...
        <p>This won't be purple.</p>
        <p class="custom-background">This will be purple.</p>
        <p>This won't be purple.</p>
        <p class="custom-background">This will be purple.</p>
        ...
    ...
...
```  

### 对齐元素   

"引导" 还提供用于对齐元素的类。  立即试用：  

1.  返回 "编辑器" 选项卡，然后打开 `index.html` 。  
1.  添加 `class="container-fluid"` 到您的 `<body>` 标签。  
    
    > ##### 图42  
    > 添加 `container-fluid` 类  
    > ![添加容器流体类][ImageCssAlign1]  

1.  将您的 `<nav>` 和 `<main>` 元素包装在中 `<div class="row">` 。  请确保放 `</div>` `</main>` 在 "" 之后，才能正确关闭新标记。  
    
    > ##### 图43  
    > 添加行  
    > ![添加行][ImageCssAlign2]  
    
1.  添加 `class="col-3"` 到您的 `<nav>` 标签和 `class="col-9"` `<main>` 标签。  
    
    > ##### 图44  
    > 添加 `col-3` 和 `col-9` 类  
    > ![添加列3和 col-9 类][ImageCssAlign3]  
    
1.  在 "实时" 选项卡中查看所做的更改。  
    
    > ##### 图45  
    > 导航内容现在位于主要内容的左侧  
    > ![导航内容现在位于主要内容的左侧][ImageCssAlign4]  
    
## 后续步骤   

恭喜你！  操作完成！  

*   在 web 开发中获取更好的最佳方式是构建更多网站。  不必担心会破坏内容。  只要有兴趣，您就可以很方便地学习。  
*   查看[CSS 简介][MDNCssFirstSteps]，了解有关设置网页样式的详细信息。  
*   [开始查看和更改 CSS][DevtoolsCssIndex]教程，了解如何使用 DevTools 体验页面的 css 的详细信息。  

<!--- image links --->  

[ImageNewStyleRuleIcon]: /microsoft-edge/devtools-guide-chromium/media/new-style-rule-icon.msft.png  

[ImageCssIntro1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-intro1.msft.png "图1：网站的当前外观"  
[ImageCssIntro2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-intro2.msft.png "图2：你的网站将在教程末尾显示的内容"  
[ImageCssSetup1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-setup1.msft.png "图3： "编辑" 选项卡"  
[ImageCssSetup2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-setup2.msft.png "图4： "项目选项" 菜单"  
[ImageCssSetup3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-setup3.msft.png "图5： "实时" 选项卡"  
[ImageCssStyled]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-red_paragraph.msft.png "图6：已通过 CSS 设置了样式"  
[ImageCssInline1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-inline1.msft.png "图7：索引 html"  
[ImageCssInline2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-inline2.msft.png "图8： "主页" 和 "联系人" 链接背后的背景色现在为蓝色"  
[ImageCssInternal1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-internal1.msft.png "图9：联系人页"  
[ImageCssInternal2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-internal2.msft.png "图10：主页和联系人链接的字体已更改"  
[ImageCssMultiple1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-multiple1.msft.png "图11：文本 "联系我们！" 现在的字体与 "家庭" 和 "联系人" 链接的字体相同"  
[ImageCssAdd1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add1.msft.png "图12：检查主页链接"  
[ImageCssAdd2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add2.msft.png "图13： "样式" 选项卡位于 DOM 树下方"  
[ImageCssAdd3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add3.msft.png "图14： "样式" 选项卡位于 DOM 树的右侧"  
[ImageCssAdd4]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add4.msft.png "图15：添加新声明"
[ImageCssAdd5]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add5.msft.png "图16：键入颜色"  
[ImageCssAdd6]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add6.msft.png "图17：键入洋红色"  
[ImageCssEdit1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-edit1.msft.png "图18：颜色选取器"  
[ImageCssEdit2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-edit2.msft.png "图19：通过拾色器将字体颜色更改为紫色"  
[ImageCssRule1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule1.msft.png "图20：添加新规则"  
[ImageCssRule2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule2.msft.png "图21：将 with a:hover 替换为"  
[ImageCssRule3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule3.msft.png "图22：键入背景色"  
[ImageCssRule4]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule4.msft.png "图23：键入绿色"  
[ImageCssRule5]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule5.msft.png "图24：将鼠标悬停在 "主页" 链接上以显示其绿色背景"  
[ImageCssExternal01]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external1.msft.png "图25：重新加载页面后，在 DevTools 中所做的更改已丢失"  
[ImageCssExternal02]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external2.msft.png "图26：联系 .html"  
[ImageCssExternal03]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external3.msft.png "图27：已删除样式标记"  
[ImageCssExternal04]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external4.msft.png "图28：已从导航元素中删除嵌入式样式"  
[ImageCssExternal05]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external5.msft.png "图29： "新建文件" 对话框"  
[ImageCssExternal06]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external6.msft.png "图30：键入样式 .css"  
[ImageCssExternal07]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external7.msft.png "图31：将代码添加到样式 .css"  
[ImageCssExternal08]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external8.msft.png "图32：链接到样式 .css"  
[ImageCssExternal09]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external9.msft.png "图33：链接到 "style" 中的 "css""  
[ImageCssExternal10]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external10.msft.png "图34：主页"  
[ImageCssExternal11]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external11.msft.png "图35：联系人页面"  
[ImageCssFramework1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-framework1.msft.png "图36：链接到 contact for .html 中的框架"  
[ImageCssFramework2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-framework2.msft.png "图37：在 index for html 中链接到框架"  
[ImageCssFramework3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-framework3.msft.png "图38：主页上的某些字体因框架而发生更改"  
[ImageCssJumbotron1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-jumbotron1.msft.png "图39：在索引 html 中添加类"  
[ImageCssJumbotron2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-jumbotron2.msft.png "图40：在 contact for .html 中添加类"  
[ImageCssJumbotron3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-jumbotron3.msft.png "图41：标题现在周围有一个大灰框"  
[ImageCssAlign1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-align1.msft.png "图42：添加容器流体类"  
[ImageCssAlign2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-align2.msft.png "图43：添加行"  
[ImageCssAlign3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-align3.msft.png "图44：添加列3和 col-9 类"  
[ImageCssAlign4]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-align4.msft.png "图45：导航内容现在位于主内容的左侧"  

<!--- links  --->  

[DevToolsBeginnersHtml]: html.md "初学者的 DevTools： HTML 和 DOM 入门"  
[DevtoolsCssIndex]: ../css/index.md "查看和更改 CSS 入门"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  

[GlitchCookedAmphibianIndex]: https://glitch.com/edit/#!/cooked-amphibian?path=index.html "index-cooked-amphibian |故障"  

[MDNCssFirstSteps]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS "CSS 优先步骤 |MDN"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/beginners/css)，由[Katherine 杰克逊][KatherineJackson]（技术作者暂存，Chrome DevTools \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
