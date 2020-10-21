---
description: 如何查看节点、搜索节点、编辑节点、在控制台中引用节点、中断节点更改等。
title: 查看和更改 DOM 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 8c0b544f2c4717a01d09c287f1167c81456a97f3
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125025"
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

完成这些交互式教程，了解有关使用 Microsoft Edge DevTools 查看和更改页面 DOM 的基础知识。  

本教程假定你知道 DOM 和 HTML 之间的区别。  有关说明，请参阅 [附录： HTML 和 DOM](#appendix-html-versus-the-dom) 。  

## Open DOM 示例  

1.  保留 `Control` \ (Windows、Linux \ ) 或 `Command` \ (macOS \ ) 并选择 " **DOM 示例** " 以在新选项卡中打开。  
    
    [DOM 示例][GlitchDomExamples]  
    
## 查看 DOM 节点  

在 "元素" 面板的 DOM 树中，你可以在 DevTools 中执行所有与 DOM 相关的活动。  

### 检查节点  

当你对特定的 DOM 节点感兴趣时，请使用 " **检查** " 快速打开 DevTools 并调查该节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 " **检查节点**" 下，右键选择 " **Michelangelo** "，然后选择 " **检查**"。  
    
    :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png" alt-text="检查节点" lightbox="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png":::
       检查节点  
    :::image-end:::  
    
    1.  将打开 DevTools 的 " **元素** " 面板。  `<li>Michelangelo</li>` 在 **DOM 树**中突出显示。  
        
        :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png" alt-text="检查节点" lightbox="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png":::
           突出显示 `Michelangelo` 节点  
        :::image-end:::  
        
        1.  单击 DevTools 左上角的 " **检查** \ (![ 检查 ][ImageInspectIcon] \ ) " 图标。  
            
            :::image type="complex" source="../media/dom-elements-highlighted-select-element-page-inspect.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-select-element-page-inspect.msft.png":::
               " **检查** " 图标  
            :::image-end:::  
            
1.  在 " **检查节点**" 下，单击 " **东京** 文本"。  现在， `<li>Tokyo</li>` 在 DOM 树中突出显示。  

检查节点也是查看和更改节点样式的第一步。  请参阅 [查看和更改 CSS 入门][DevToolsCssGetStarted]。  

### 使用键盘导航 DOM 树  

选择 DOM 树中的节点后，您可以使用键盘在 DOM 树中导航。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 " **使用键盘导航 DOM 树**" 下，右键选择 " **Ringo** "，然后选择 " **检查**"。  `<li>Ringo</li>` 在 DOM 树中处于选中状态。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png":::
       检查 `Ringo` 节点  
    :::image-end:::  
    
    1.  按 `Up` 箭头键2次。  `<ul>` 已选中。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png":::
           检查 `ul` 节点  
        :::image-end:::  
        
    1.  按 `Left` 箭头键。  `<ul>`列表折叠。  
    1.  再次按 `Left` 箭头键。  `<ul>`已选中节点的父节点。  在这种情况下，它 `<div>` 具有 ID `navigate-the-dom-tree-with-a-keyboard-1` 。  
    1.  按 `Down` 箭头键2次，以便您重新选中 `<ul>` 刚才折叠的列表。  应如下所示： `<ul>... </ul>`  
    1.  按 `Right` 箭头键。  该列表将展开。  

### 滚动到视图  

查看 DOM 树时，你可能会发现你对当前不在视口中的 DOM 节点感兴趣。  例如，假设你滚动到页面底部，并且你对 `<h1>` 页面顶部的节点感兴趣。  "**滚动到" 视图**可快速调整视区的位置，以便您能够看到该节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 " **滚动到视图**" 下，右键选择 " **Magritte** "，然后选择 " **检查**"。  
1.  滚动到 "DOM 示例" 页面的底部。  
1.  该 `<li>Magritte</li>` 节点应仍在你的 DOM 树中处于选中状态。  如果不是，请返回到 " [查看](#scroll-into-view) " 并重新开始。  
1.  右键单击 `<li>Magritte</li>` 节点，然后选择 " **滚动到视图**"。  你的视区向后滚动，以便你可以看到 **Magritte** 节点。  如果无法看到 "**滚动到视图**" 选项，请参阅[附录： "缺少选项](#appendix-missing-options)"。
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       **滚动到视图**  
    :::image-end:::  

### 搜索节点  

你可以按字符串、CSS 选择器或 XPath 选择器搜索 DOM 树。  

1.  将光标聚焦在 " **元素** " 面板上。  
1.  选择 `Control` + `F` \ (Windows、Linux \ ) 或 `Command` + `F` \ (macOS \ ) 。  搜索栏将在 DOM 树的底部打开。  
1.  键入 `The Moon is a Harsh Mistress`。  最后一句在 DOM 树中突出显示。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-search-nodes-highlight.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-search-nodes-highlight.msft.png":::
       在搜索栏中突出显示查询  
    :::image-end:::  
    
如上文所述，搜索栏还支持 CSS 和 XPath 选择器。  

## 编辑 DOM  

你可以动态编辑 DOM 并查看这些更改对页面的影响。  

### 编辑内容  

若要编辑节点的内容，请双击 DOM 树中的内容。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 " **编辑内容**" 下，右键选择 " **Michelle** "，然后选择 " **检查**"。  
    1.  在 DOM 树中，双击 `Michelle` 。  换句话说，双击 and 之间的文本 `<li>` `</li>` 。  文本将突出显示，以指示它已选中。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-content.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-edit-content.msft.png":::
           编辑文本  
        :::image-end:::  
        
    1.  删除 `Michelle` ，键入 `Leela` ，然后选择 `Enter` 以确认更改。  DOM 中的文本从 **Michelle** 更改为 **Leela**。  

### 编辑属性  

若要编辑属性，请双击属性名称或值。  按照说明操作，了解如何向节点添加属性。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 " **编辑属性**" 下，右键选择 " **Howard** "，然后选择 " **检查**"。  
1.  双击 `<li>` 。  文本将突出显示，以指示节点已选中。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png":::
       编辑节点  
    :::image-end:::  
    
1.  按 `Right` 箭头键，添加一个空格，键入 `style="background-color:gold"` ，然后选择 `Enter` 。  节点的背景色将更改为 "金色"。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png":::
       向 `style` 节点添加属性  
    :::image-end:::  
    
### 编辑节点类型  

若要编辑节点类型，请双击该类型，然后键入新类型。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 " **编辑节点类型**" 下，右键选择 " **Hank** "，然后选择 " **检查**"。  
    1.  双击 `<li>` 。  文本 `li` 突出显示。  
    1.  删除 `li` ，键入 `button` ，然后选择 `Enter` 。  `<li>`节点将更改为 `<button>` 节点。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-node-type-button.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-edit-node-type-button.msft.png":::
           将节点类型更改为 `button`  
        :::image-end:::  
        
### 重新排序 DOM 节点  

拖动节点以对其重新排序。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 " **重新排序 DOM 节点**" 下，右键选择 " **Elvis Presley** "，然后选择 " **检查**"。  
    
    > [!NOTE]
    > 它是列表中的最后一项。  
    
    1.  在 DOM 树中，拖动 `<li>Elvis Presley</li>` 到列表的顶部。  
        
        :::image type="complex" source="../media/dom-elements-reorder-dom-nodes.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-reorder-dom-nodes.msft.png":::
           将节点拖到列表顶部  
        :::image-end:::  
        
### 强制状态  

你可以强制节点保留在状态中，包括、、、 `:active` `:hover` `:focus` `:visited` 和 `:focus-within` 。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 " **强制状态**" 下，将鼠标悬停在 **Lord 的**上方。  背景色变为橙色。  
    1.  右键选择 " **飞入" 的 Lord** ，然后选择 " **检查**"。  
    1.  右键单击 `<li class="demo--hover">The Lord of the Flies</li>` ，然后选择 "**强制状态**  >  **：悬停**"。  如果看不到此选项，请参阅 [附录：缺少选项](#appendix-missing-options) 。  虽然实际上不会将鼠标悬停在节点上，但背景色仍为橙色。  

### 隐藏节点  

选择 `H` 以隐藏节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 " **隐藏节点**" 下，右键选择 **"星" 到 "我的目的地"** ，然后选择 " **检查**"。  
    1.  按 `H` 键。  节点已隐藏。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-hide-a-node.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-hide-a-node.msft.png":::
           节点在隐藏后在 DOM 树中的显示效果  
        :::image-end:::  
        
    1.  再次按下 `H` 键。  将再次显示该节点。  

### 删除节点  

选择 `Delete` 以删除节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 " **删除节点**" 下，右键选择 " **基础** "，然后选择 " **检查**"。  
    1.  按 `Delete` 键。  删除该节点。  
    1.  选择 `Control` + `Z` \ (Windows、Linux \ ) 或 `Command` + `Z` \ (macOS \ ) 。  最后一个操作将被撤消，并且该节点会再次出现。  

## 访问控制台中的节点  

DevTools 提供了从控制台访问 DOM 节点或获取每个节点的 JavaScript 引用的一些快捷方式。  

### 引用当前选定的具有 $0 的节点  

检查节点时， `== $0` 节点旁边的文本意味着你可以使用该变量在控制台中引用此节点 `$0` 。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 " **引用当前选定的包含 $0 的节点**" 下，右键选择 **暗度的左侧** ，然后选择 " **检查**"。  
    1.  按 `Escape` 键打开控制台抽屉。  
    1.  键入 `$0` ，然后按键 `Enter` 。  表达式的结果显示 `$0` 为 `<li>The Left Hand of Darkness</li>` 。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png":::
            `$0`**控制台**中第一个表达式的结果  
        :::image-end:::  
        
    1.  将鼠标悬停在结果上。  节点在视区中突出显示。  
    1.  单击 `<li>Dune</li>` DOM 树， `$0` 再次键入控制台，然后 `Enter` 再次选择。  现在， `$0` 计算结果为 `<li>Dune</li>` 。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png":::
           控制台中第二个 `$0` 表达式的结果**Console**  
        :::image-end:::  
        
### 存储为全局变量  

如果需要多次引用某个节点，请将其存储为全局变量。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 " **存储为全局变量**" 下，右键选择 **"大睡眠"** ，然后选择 " **检查**"。  
    1.  右键单击 `<li>The Big Sleep</li>` DOM 树，然后选择 " **存储为全局变量**"。  如果看不到此选项，请参阅 [附录：缺少选项](#appendix-missing-options) 。  
    1.  `temp1`在控制台中键入，然后选择 `Enter` 。  表达式的结果显示变量的计算结果为节点。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png":::
           表达式的结果 `temp1`  
        :::image-end:::  
        
### 复制 JS 路径  

如果需要在自动测试中引用节点，请将 JavaScript 路径复制到该节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 " **复制 JS 路径**" 下，右键选择 **"比较 Karamazov"** ，然后选择 " **检查**"。  
    1.  右键单击 `<li>The Brothers Karamazov</li>` DOM 树，然后选择 "**复制**  >  **JS 路径**"。  `document.querySelector()`解析为该节点的表达式已复制到剪贴板。  
    1.  选择 `Control` + `V` \ (Windows、Linux \ ) 或 `Command` + `V` \ (macOS \ ) 将表达式粘贴到控制台。  
    1.  选择 `Enter` 以计算表达式。
        
        :::image type="complex" source="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png":::
           **COPY JS 路径**表达式的结果  
        :::image-end:::  
        
## DOM 更改时中断  

DevTools 使你能够在 JavaScript 修改 DOM 时暂停页面的 JavaScript。  

### 属性修改中断  

当你希望暂停导致节点的任何属性更改的 JavaScript 时，请使用属性修改断点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 " **属性修改时中断**" 下，右键选择 " **Sauerkraut** "，然后选择 " **检查**"。  
    1.  在 DOM 树中，右键单击 `<li id="target">Sauerkraut</li>` 并选择 **"**  >  **属性修改**时中断"。  请参阅附录：如果无法看到此选项，则为 " [缺少选项](#appendix-missing-options) "。
        
        :::image type="complex" source="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png":::
           **属性修改中断**  
        :::image-end:::  
        
    1.  在下一步中，你将指示你单击暂停页面代码的按钮。  页面暂停后，您将无法再滚动页面。  必须选择 " **恢复脚本** \ (![ 恢复脚本 ][ImageResumeScriptIcon] \ ) " 才能使页面再次滚动。
        
        :::image type="complex" source="../media/dom-break-attribute-modifications-sources-paused-on.msft.png" alt-text="检查节点" lightbox="../media/dom-break-attribute-modifications-sources-paused-on.msft.png":::
           恢复运行脚本的位置  
        :::image-end:::  
        
    1.  单击上面的 " **设置背景** " 按钮。  这会将 `style` 节点的属性设置为 `background-color:thistle` 。  DevTools 暂停页面并突出显示导致属性更改的代码。  
    1.  如前面所述，选择 **恢复脚本** \ (![ 恢复脚本 ][ImageResumeScriptIcon] \ ) 。  
    
### 节点删除时中断  

如果要在删除特定节点时暂停，请使用节点删除断点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 " **删除节点**" 下的 "中断" 下，右键选择 **Neuromancer** ，然后选择 " **检查**"。  
    1.  在 DOM 树中，右键单击 `<li id="target">Neuromancer</li>` 并选择 **"**  >  **删除节点**时中断"。  请参阅附录：如果无法看到此选项，则为 " [缺少选项](#appendix-missing-options) "。  
    1.  单击上面的 " **删除** " 按钮。  DevTools 暂停页面并突出显示导致节点被删除的代码。  
    1.  选择 " **恢复脚本** \ (![ 恢复脚本 ][ImageResumeScriptIcon] \ ) "。  
    
### 子树修改中断  

在节点上放置子树修改断点后，在添加或删除节点的任何子代时，DevTools 将暂停页面。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 " **子树修改时中断**" 下，右键选择 **深度的火** ，然后选择 " **检查**"。  
    1.  在 DOM 树中，右键单击 `<ul id="target">` （上面的节点 `<li>A Fire Upon the Deep</li>` ），然后选择 "在**Break On**  >  **子树修改**时中断"。  请参阅附录：如果无法看到此选项，则为 " [缺少选项](#appendix-missing-options) "。  
    1.  选择 " **添加子级**"。  由于 `<li>` 节点已添加到列表，代码暂停。  
    1.  选择 " **恢复脚本** \ (![ 恢复脚本 ][ImageResumeScriptIcon] \ ) "。  
    
## 后续步骤  

这涉及 DevTools 中的大部分与 DOM 相关的功能。  你可以通过右键单击 DOM 树中的节点并试用本教程中未介绍的其他选项来发现其余部分。  另请参阅 ["元素" 面板键盘快捷方式][DevToolsShortcutsElements]。  

查看 [Microsoft Edge DevTools 主页][MicrosoftEdgeDevTools] 以了解你可以通过 DevTools 执行的其他操作。  

<!--See [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  

## 附录： HTML 与 DOM  

以下部分将快速介绍 HTML 和 DOM 之间的区别。  

:::row:::
   :::column span="":::
      使用 web 浏览器请求页面时，服务器返回类似以下代码片段的 HTML  

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
      浏览器分析 HTML 并创建类似于以下列表的对象树。  
      
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

表示页面内容的此对象树（即表示页面内容的节点）称为 DOM。  

:::row:::
   :::column span="":::
      现在，它看起来与 HTML 相同，但假设 HTML 底部引用的脚本运行以下代码片段。  
      
      ```javascript
      const h1 = document.querySelector('h1');
      h1.parentElement.removeChild(h1);
      const p = document.createElement('p');
      p.textContent = 'Wildcard!';
      document.body.appendChild(p);
      ```  
   :::column-end:::
   :::column span="":::
      该代码将删除 `h1` 节点，并将另一个 `p` 节点添加到 DOM。  完整的 DOM 现在显示以下列表。  
      
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

页面的 HTML 现在与 DOM 不同。  换句话说，HTML 表示初始页面内容，DOM 表示当前页面内容。  当 JavaScript 添加、删除或编辑节点时，DOM 将与 HTML 不同。  

请参阅 [DOM 简介][MDNIntroductionToDOM] 以了解详细信息。  

<!--
## Appendix: Scroll into view  

This is a continuation of the [Scroll into view](#scroll-into-view) section.  Follow the instructions below to complete the section.  

1.  The `<li>Magritte</li>` node should still be selected in your DOM Tree.  If not, go back to [Scroll into view](#scroll-into-view) and start over.  
1.  Right-click the `<li>Magritte</li>` node and choose **Scroll into view**.  Your viewport scrolls back up so that you may see the **Magritte** node.  See [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       Scroll into view  
    :::image-end:::  
    -->  

## 附录：缺少选项  

本教程中的许多说明将指导你右键单击 DOM 树中的节点，然后从弹出的上下文菜单中选择一个选项。  如果在上下文菜单中看不到指定的选项，请尝试右键单击节点文本以外的位置。  

:::image type="complex" source="../media/dom-elements-highlighted-right-click-right-side.msft.png" alt-text="检查节点" lightbox="../media/dom-elements-highlighted-right-click-right-side.msft.png":::
   如果未看到所有选项，请单击的位置  
:::image-end:::  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageInspectIcon]: ../media/inspect-icon.msft.png  
[ImageResumeScriptIcon]: ../media/resume-script-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge \ (Chromium \ ) 开发工具 |Microsoft 文档"  
[DevToolsCssGetStarted]: ../css/index.md "开始使用查看和更改 CSS |Microsoft 文档"  
[DevToolsShortcutsElements]: ../shortcuts.md#elements-panel-keyboard-shortcuts ""元素" 面板键盘快捷方式-Microsoft Edge DevTools 键盘快捷方式 |Microsoft 文档"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge (Chromium) DevTools DOM 示例 |故障"

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
