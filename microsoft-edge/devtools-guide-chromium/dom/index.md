---
description: 如何查看节点、搜索节点、编辑节点、控制台中的引用节点、节点更改中断等。
title: 查看和更改 DOM 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 5b12b984aed7e35ce11dd45e8bc33f5d5fd454f8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231102"
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

# 查看和更改 DOM 入门  

完成这些交互式教程，了解使用 Microsoft Edge DevTools 查看和更改页面 DOM 的基础知识。  

本教程假定你了解 DOM 和 HTML 的区别。  导航到 [附录：HTML 与 DOM，](#appendix-html-versus-the-dom) 了解相关说明。  

## 打开 DOM 示例  

1.  按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) ，然后选择 **DOM 示例** 以在新建选项卡中打开。  
    
    [DOM 示例][GlitchDomExamples]  
    
## 查看 DOM 节点  

在"元素"面板的 DOM 树中，您可以在 DevTools 中执行所有与 DOM 相关的活动。  

### 检查节点  

当你对特定 DOM 节点感兴趣时， **检查** 是打开 DevTools 并调查该节点的一种快速方法。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"检查节点"下**，右选择 **"一角"，** 然后选择"**检查"。**  
    
    :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png" alt-text="检查节点" lightbox="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png":::
       检查节点  
    :::image-end:::  
    
    1.  将 **打开** DevTools 的元素面板。  `<li>Michelangelo</li>` 在 **DOM 树中突出显示**。  
        
        :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png" alt-text="突出显示"一文集"节点" lightbox="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png":::
           突出显示 `Michelangelo` 节点  
        :::image-end:::  
        
        1.  单击**** ![ DevTools (左上角的"检查) 检查 \) ][ImageInspectIcon] 图标。  
            
            :::image type="complex" source="../media/dom-elements-highlighted-select-element-page-inspect.msft.png" alt-text=""检查"图标" lightbox="../media/dom-elements-highlighted-select-element-page-inspect.msft.png":::
               " **检查"** 图标  
            :::image-end:::  
            
1.  在 **"检查节点"** 下，单击 **"东京"** 文本。  现在 `<li>Tokyo</li>` ，在 DOM 树中突出显示。  

检查节点也是查看和更改节点样式的第一步。  导航到["查看和更改 CSS 入门"。][DevToolsCssGetStarted]  

### 使用键盘导航 DOM 树  

选择 DOM 树中的节点后，可以使用键盘导航 DOM 树。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"使用键盘导航 DOM 树"** 下，右键选择 **"响铃"，** 然后选择"**检查"。**  `<li>Ringo</li>` 在 DOM 树中选中。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png" alt-text="检查 Ringo 节点" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png":::
       检查 `Ringo` 节点  
    :::image-end:::  
    
    1.  按 `Up` 箭头键 2 次。  `<ul>` 已选中。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png" alt-text="检查 ul 节点" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png":::
           检查 `ul` 节点  
        :::image-end:::  
        
    1.  按 `Left` 箭头键。  列表 `<ul>` 折叠。  
    1.  再次 `Left` 按箭头键。  选择节点 `<ul>` 的父节点。  在这种情况下，它是 `<div>` `navigate-the-dom-tree-with-a-keyboard-1` ID。  
    1.  按 `Down` 箭头键 2 次，以便重新选择刚刚 `<ul>` 折叠的列表。  应如下所示： `<ul>... </ul>`  
    1.  按 `Right` 箭头键。  列表将展开。  

### 滚动到视图  

查看 DOM 树时，您可能会对当前不在视口中的 DOM 节点感兴趣。  例如，假设您滚动到页面底部，并且对页面顶部的节点 `<h1>` 感兴趣。  **滚动到视图中** 可快速重新定位视口，以便查看节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"滚动到视图**"下，右选择 **"Magritte"，** 然后选择"**检查"。**  
1.  滚动到 DOM 示例页的底部。  
1.  仍 `<li>Magritte</li>` 应在 DOM 树中选择节点。  如果不是，请返回到" [滚动到视图](#scroll-into-view) "并重新开始。  
1.  将鼠标悬停在节点上，打开上下文菜单 `<li>Magritte</li>` \ (右键单击\) ，然后选择 **"滚动到视图"。**  视区将向上滚动，以便你可以查看 **Magritte** 节点。  导航到 [附录：如果](#appendix-missing-options) 无法查看"滚动到视图"选项，则 **缺少** 选项。
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="滚动到视图" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       **滚动到视图**  
    :::image-end:::  

### 搜索节点  

您可以按字符串、CSS 选择器或 XPath 选择器搜索 DOM 树。  

1.  将光标焦点放在 **"元素"面板** 上。  
1.  选择 `Control` + `F` \ (Windows、Linux\) `Command` + `F` 或 \ (macOS\) 。  搜索栏将在 DOM 树的底部打开。  
1.  键入 `The Moon is a Harsh Mistress`。  最后一句在 DOM 树中突出显示。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-search-nodes-highlight.msft.png" alt-text="在搜索栏中突出显示查询" lightbox="../media/dom-elements-highlighted-search-nodes-highlight.msft.png":::
       在搜索栏中突出显示查询  
    :::image-end:::  
    
如上所述，搜索栏还支持 CSS 和 XPath 选择器。  

## 编辑 DOM  

您可以直接编辑 DOM，并查看更改对页面有何影响。  

### 编辑内容  

若要编辑节点的内容，请双击 DOM 树中的内容。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"编辑内容**"下，右选择 **"Michelle"，** 然后选择"**检查"。**  
    1.  在 DOM 树中，双击 `Michelle` 。  换句话说，双击和 之间的 `<li>` 文本 `</li>` 。  文本将突出显示以指示已选中。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-content.msft.png" alt-text="编辑文本" lightbox="../media/dom-elements-highlighted-edit-content.msft.png":::
           编辑文本  
        :::image-end:::  
        
    1.  删除 `Michelle` ，键入 `Leela` ，然后选择 `Enter` 以确认更改。  DOM 中的文本从**Michelle 更改为****小雷**。  

### 编辑属性  

若要编辑属性，请双击属性名称或值。  按照说明了解如何向节点添加属性。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"编辑属性"下**，右选择 **"放大**"，然后选择"**检查"。**  
1.  双击 `<li>` 。  突出显示文本以指示节点已选中。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png" alt-text="编辑节点" lightbox="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png":::
       编辑节点  
    :::image-end:::  
    
1.  按 `Right` 箭头键，添加空格，键入 `style="background-color:gold"` ，然后选择 `Enter` 。  节点的背景颜色将更改为金色。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png" alt-text="向节点添加样式属性" lightbox="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png":::
       向 `style` 节点添加属性  
    :::image-end:::  
    
### 编辑节点类型  

若要编辑节点的类型，请双击该类型，然后键入新类型。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"编辑节点类型"下**，右选择 **"百**科"，然后选择"**检查"。**  
    1.  双击 `<li>` 。  文本 `li` 突出显示。  
    1.  删除 `li` ，键入 `button` ，然后选择 `Enter` 。  节点 `<li>` 将更改到 `<button>` 节点。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-node-type-button.msft.png" alt-text="将节点类型更改为按钮" lightbox="../media/dom-elements-highlighted-edit-node-type-button.msft.png":::
           将节点类型更改为 `button`  
        :::image-end:::  
        
### 对 DOM 节点重新排序  

拖动节点以重新排序。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"重新排序 DOM 节点**"下，右选择**Elvis Presley**并选择 **"检查"。**  
    
    > [!NOTE]
    > 它是列表中的最后一项。  
    
    1.  在 DOM 树中，拖动 `<li>Elvis Presley</li>` 到列表顶部。  
        
        :::image type="complex" source="../media/dom-elements-reorder-dom-nodes.msft.png" alt-text="将节点拖动到列表顶部" lightbox="../media/dom-elements-reorder-dom-nodes.msft.png":::
           将节点拖动到列表顶部  
        :::image-end:::  
        
### 强制状态  

你可以强制节点保持状态，包括 `:active` 、 和 `:hover` `:focus` `:visited` `:focus-within` 。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"强制"** 状态下，将鼠标悬停在 **"四分之一"上**。  背景色变为橙色。  
    1.  右选择 **"四角"，** 然后选择"检查 **"。**  
    1.  右键单击 `<li class="demo--hover">The Lord of the Flies</li>` 并选择 **"强制状态**  >  **：悬停"。**  导航到 [附录：如果未显示](#appendix-missing-options) 该选项，则缺少选项。  即使你实际上没有将鼠标悬停在节点上，背景颜色仍保持橙色。  

### 隐藏节点  

选择 `H` 以隐藏节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"隐藏节点"** 下，右选择 **"星形我的目的地"，** 然后选择"**检查"。**  
    1.  按 `H` 该键。  节点处于隐藏状态。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-hide-a-node.msft.png" alt-text="隐藏后的节点在 DOM 树中的外观" lightbox="../media/dom-elements-highlighted-hide-a-node.msft.png":::
           隐藏后的节点在 DOM 树中的外观  
        :::image-end:::  
        
    1.  再次 `H` 按该键。  节点将再次显示。  

### 删除节点  

选择 `Delete` 以删除节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"删除节点"下**，右选择 **"基础**"，然后选择"**检查"。**  
    1.  按 `Delete` 该键。  删除节点。  
    1.  选择 `Control` + `Z` \ (Windows、Linux\) `Command` + `Z` 或 \ (macOS\) 。  最后一个操作将撤消，节点将重新出现。  

## 控制台中的访问节点  

DevTools 提供了一些快捷方式，用于从控制台访问 DOM 节点或获取对每个节点的 JavaScript 引用。  

### 引用当前选定的节点，其价格为 $0  

检查节点时，节点旁边的文本意味着可以使用变量 `== $0` 在控制台中引用此节点 `$0` 。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"引用当前选定的节点与 $0"** 下，右选择"深暗**的**左手"，然后选择"**检查"。**  
    1.  按 `Escape` 该键打开控制台箱。  
    1.  键入 `$0` 并按 `Enter` 该键。  表达式的结果显示计算 `$0` 结果为 `<li>The Left Hand of Darkness</li>` 。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png" alt-text="控制台中第一个 $0 表达式的结果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png":::
            控制台中第一 `$0` 个表达式 **的结果**  
        :::image-end:::  
        
    1.  将鼠标悬停在结果上方。  该节点在视口中突出显示。  
    1.  在 `<li>Dune</li>` DOM 树中单击， `$0` 再次键入控制台，然后再次 `Enter` 选择。  现在， `$0` 计算结果为 `<li>Dune</li>` 。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png" alt-text="控制台中第二个 $0 表达式的结果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png":::
           控制台中第 `$0` 二个表达式 **的结果**  
        :::image-end:::  
        
### 存储为全局变量  

如果需要多次引用回节点，请存储为全局变量。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"存储作为全局变量"下**，右选择 **"大睡眠"，** 然后选择"**检查"。**  
    1.  在 `<li>The Big Sleep</li>` DOM 树中右键单击并选择 **"存储"作为全局变量**。  导航到 [附录：如果未显示](#appendix-missing-options) 该选项，则缺少选项。  
    1.  在 `temp1` 控制台中键入，然后选择 `Enter` 。  表达式的结果显示变量计算结果为节点。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png" alt-text="temp1 表达式的结果" lightbox="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png":::
           表达式 `temp1` 的结果  
        :::image-end:::  
        
### 复制 JS 路径  

当你需要在自动测试中引用该节点时，将 JavaScript 路径复制到该节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"复制 JS 路径**"下，右选择 **"放大百分之百"，** 然后选择"**检查"。**  
    1.  在 `<li>The Brothers Karamazov</li>` DOM 树中右键单击，然后选择 **"复制**  >  **JS 路径"。**  `document.querySelector()`解析为节点的表达式已复制到剪贴板。  
    1.  选择 `Control` + `V` \ (Windows、Linux\) 或 `Command` + `V` \ (macOS\) 将表达式粘贴到控制台中。  
    1.  选择 `Enter` 以计算表达式。
        
        :::image type="complex" source="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png" alt-text="复制 JS 路径表达式的结果" lightbox="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png":::
           复制 JS **路径** 表达式的结果  
        :::image-end:::  
        
## DOM 更改中断  

DevTools 使您能够在 JavaScript 修改 DOM 时暂停页面的 JavaScript。  

### 中断属性修改  

当您想要暂停导致节点的任何属性更改的 JavaScript 时，请使用属性修改断点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在**属性修改中断下**，右选择**Sauerkraut，** 然后选择"**检查"。**  
    1.  在 DOM 树中，右键单击 `<li id="target">Sauerkraut</li>` 并选择"属性**修改时**  >  **中断"。**  导航到 [附录：如果未显示](#appendix-missing-options) 该选项，则缺少选项。
        
        :::image type="complex" source="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png" alt-text="中断属性修改" lightbox="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png":::
           **中断属性修改**  
        :::image-end:::  
        
    1.  下一步，将指示你单击暂停页面代码的按钮。  暂停页面后，你无法再滚动页面。  必须选择" **恢复** 脚本 ![ " ("恢复脚本") 使页面可再次 ][ImageResumeScriptIcon] 滚动。
        
        :::image type="complex" source="../media/dom-break-attribute-modifications-sources-paused-on.msft.png" alt-text="在何处继续运行脚本" lightbox="../media/dom-break-attribute-modifications-sources-paused-on.msft.png":::
           在何处继续运行脚本  
        :::image-end:::  
        
    1.  单击 **上面的"设置背景** "按钮。  这会将 `style` 节点的属性设置为 `background-color:thistle` 。  DevTools 暂停页面并突出显示导致属性更改的代码。  
    1.  选择 **"恢复脚本** (![ 恢复脚本 ][ImageResumeScriptIcon] \) ，如前面所述。  
    
### 节点删除时中断  

如果要在删除特定节点时暂停，请使用节点删除断点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"删除节点时中断"下**，右选择 **"管理**程序"，然后选择"**检查"。**  
    1.  在 DOM 树中，右键单击 `<li id="target">Neuromancer</li>` 并选择"**删除节点**  >  **时中断"。**  导航到 [附录：如果未显示](#appendix-missing-options) 该选项，则缺少选项。  
    1.  单击 **上面的"删除** "按钮。  DevTools 暂停页面并突出显示导致删除节点的代码。  
    1.  Choose **Resume Script** \ (Resume Script ![ ][ImageResumeScriptIcon] \) .  
    
### 在子树修改上中断  

在节点上放入子树修改断点后，当添加或删除节点的任何后代时，DevTools 将暂停页面。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"子树修改的**中断"下，右选择"深度时射击 **"，** 然后选择"**检查"。**  
    1.  在 DOM 树中，右键单击上方的节点，然后选择"在子树修改 `<ul id="target">` `<li>A Fire Upon the Deep</li>` **时**  >  **中断"。**  导航到 [附录：如果未显示](#appendix-missing-options) 该选项，则缺少选项。  
    1.  选择 **"添加子级"。**  代码会暂停，因为 `<li>` 节点已添加到列表中。  
    1.  Choose **Resume Script** \ (Resume Script ![ ][ImageResumeScriptIcon] \) .  
    
## 后续步骤  

这涵盖了 DevTools 中大部分与 DOM 相关的功能。  通过右键单击 DOM 树中的节点并尝试本教程未涵盖的其他选项，你可以发现其余的节点。  导航到 [元素面板键盘快捷方式][DevToolsShortcutsElements]。  

查看 [Microsoft Edge DevTools 主页][MicrosoftEdgeDevTools] ，了解可以使用 DevTools 执行的所有其他功能。  

<!--Navigate to [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  

## 附录：HTML 与 DOM  

下一节快速介绍了 HTML 和 DOM 的区别。  

:::row:::
   :::column span="":::
      当您使用 Web 浏览器请求页面时，服务器将返回类似以下代码段的 HTML  

      ```html
      <!doctype html>
      <html>
          <head>
              <title>Hello, world!</title>
          </head>
          <body>
              <h1>Hello, world!</h1>
              <p>This is a hypertext document on the World Wide Web.</p>
              <script src="/script.js" async></script>
          </body>
      </html>
      ```  
   :::column-end:::
   :::column span="":::
      浏览器分析 HTML 并创建对象树，如以下列表所示。  
      
      ```dom
      html
          head
              title
          body
              h1
              p
              script
      ```  
   :::column-end:::
:::row-end:::  

此表示页面内容的对象或节点树称为 DOM。  

:::row:::
   :::column span="":::
      现在它看起来与 HTML 相同，但假定 HTML 底部引用的脚本运行以下代码段。  
      
      ```javascript
      const h1 = document.querySelector('h1');
      h1.parentElement.removeChild(h1);
      const p = document.createElement('p');
      p.textContent = 'Wildcard!';
      document.body.appendChild(p);
      ```  
   :::column-end:::
   :::column span="":::
      该代码将删除该 `h1` 节点，并将另 `p` 一个节点添加到 DOM。  完整的 DOM 现在将显示以下列表。  
      
      ```dom
      html
          head
              title
          body
              p
              script
              p
      ```  
   :::column-end:::
:::row-end:::  

页面的 HTML 现在不同于 DOM。  换句话说，HTML 表示初始页面内容，DOM 表示当前页面内容。  当 JavaScript 添加、删除或编辑节点时，DOM 将不同于 HTML。  

导航 [到 DOM 简介][MDNIntroductionToDOM] 以了解更多信息。  

<!--
## Appendix: Scroll into view  

This is a continuation of the [Scroll into view](#scroll-into-view) section.  Follow the instructions below to complete the section.  

1.  The `<li>Magritte</li>` node should still be selected in your DOM Tree.  If not, go back to [Scroll into view](#scroll-into-view) and start over.  
1.  Right-click the `<li>Magritte</li>` node and choose **Scroll into view**.  Your viewport scrolls back up so that you may see the **Magritte** node.  Navigate to [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="Scroll into view" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       Scroll into view  
    :::image-end:::  
    -->  

## 附录：缺少选项  

本教程中的许多说明都指示你右键单击 DOM 树中的节点，然后从弹出的上下文菜单中选择一个选项。  如果未显示上下文菜单中的指定选项，请尝试右键单击离开节点文本。  

:::image type="complex" source="../media/dom-elements-highlighted-right-click-right-side.msft.png" alt-text="如果未显示所有选项，选择什么位置" lightbox="../media/dom-elements-highlighted-right-click-right-side.msft.png":::
   如果未显示所有选项，选择什么位置  
:::image-end:::  

## 联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageInspectIcon]: ../media/inspect-icon.msft.png  
[ImageResumeScriptIcon]: ../media/resume-script-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge \ (Chromium\) 开发人员工具 |Microsoft Docs"  
[DevToolsCssGetStarted]: ../css/index.md "查看和更改 CSS 入门 |Microsoft Docs"  
[DevToolsShortcutsElements]: ../shortcuts/index.md#elements-panel-keyboard-shortcuts "元素面板键盘快捷方式 - Microsoft Edge DevTools 键盘快捷方式 |Microsoft Docs"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge (Chromium) DevTools DOM 示例 |小故障"

[MDNIntroductionToDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM 简介 |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/dom/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
