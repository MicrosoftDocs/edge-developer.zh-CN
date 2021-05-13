---
description: 如何查看节点、搜索节点、编辑节点、引用控制台中的节点、中断节点更改等。
title: 查看和更改 DOM 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, 开发人员工具
ms.openlocfilehash: 66078844730ebb22664c9ce89517511d7eb99ee7
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564285"
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
# <a name="get-started-with-viewing-and-changing-the-dom"></a>查看和更改 DOM 入门  

完成这些交互式教程以了解使用 Microsoft Edge 开发人员工具查看和更改页面 DOM 的基础知识。  

本教程假定你知道 DOM 和 HTML 之间的区别。  导航到“[附录：HTML 与 DOM](#appendix-html-versus-the-dom)”了解相关说明。  

## <a name="open-dom-examples"></a>打开 DOM 示例  

1.  按住 `Control`（Windows、Linux）或 `Command` (macOS)，然后选择“**DOM 示例**”以在新选项卡中打开。  
    
    [DOM 示例][GlitchDomExamples]  
    
## <a name="view-dom-nodes"></a>查看 DOM 节点  

在“元素”面板的 DOM 树中，你可以在开发人员工具中执行所有 DOM 相关活动。  

### <a name="inspect-a-node"></a>检查节点  

当你对特定 DOM 节点感兴趣时，可通过“**检查**”快速打开开发人员工具并调查该节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在“**检查节点**”下，右键选择“**Michelangelo**”，然后选择“**检查**”。  
    
    :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png" alt-text="检查节点" lightbox="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png":::
       检查节点  
    :::image-end:::  
    
    1.  此时将打开开发人员工具的“**元素**”工具。  `<li>Michelangelo</li>` 将在“**DOM 树**”中突出显示。  
        
        :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png" alt-text="突出显示 Michelangelo 节点" lightbox="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png":::
           突出显示 `Michelangelo` 节点  
        :::image-end:::  
        
        1.  选择开发人员工具左上角的“**检查**”（“![检查](../media/inspect-icon.msft.png)”）图标。  
            
            :::image type="complex" source="../media/dom-elements-highlighted-select-element-page-inspect.msft.png" alt-text="“检查”图标" lightbox="../media/dom-elements-highlighted-select-element-page-inspect.msft.png":::
               “**检查**”图标  
            :::image-end:::  
            
1.  在“**检查节点**”下，选择“**Tokyo**”文本。  现在，`<li>Tokyo</li>` 在 DOM 树中突出显示。  

检查节点也是查看和更改节点样式的第一步。  导航到“[查看和更改 CSS 入门][DevToolsCssGetStarted]”。  

### <a name="navigate-the-dom-tree-with-a-keyboard"></a>使用键盘浏览 DOM 树  

在 DOM 树中选择节点后，可使用键盘浏览 DOM 树。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在“**使用键盘浏览 DOM 树**”下，右键选择“**Ringo**”，然后选择“**检查**”。  `<li>Ringo</li>` 在 DOM 树中已选中。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png" alt-text="检查 Ringo 节点" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png":::
       检查 `Ringo` 节点  
    :::image-end:::  
    
    1.  选择 `Up` 箭头键 2 次。  `<ul>` 已选中。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png" alt-text="检查 ul 节点" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png":::
           检查 `ul` 节点  
        :::image-end:::  
        
    1.  选择 `Left` 箭头键。  `<ul>` 列表会折叠。  
    1.  再次选择 `Left` 箭头键。  `<ul>` 节点的父节点已被选中。  在这种情况下，它是 ID 为 `navigate-the-dom-tree-with-a-keyboard-1` 的 `<div>`。  
    1.  选择 `Down` 箭头键 2 次，以便重新选择刚刚折叠的 `<ul>` 列表。  应如下所示： `<ul>... </ul>`  
    1.  选择 `Right` 箭头键。  列表将展开。  

### <a name="scroll-into-view"></a>滚动到视图  

查看 DOM 树时，你可能会发现自己对当前不在视区中的 DOM 节点感兴趣。  例如，假设你滚动到页面底部，并且你对页面顶部的 `<h1>` 节点感兴趣。  “**滚动到视图**”可让你快速重新定位视区，以便能够查看节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在“**滚动到视图**”下，右键选择“**Magritte**”，然后选择“**检查**”。  
1.  滚动到“DOM 示例”页面的底部。  
1.  仍应在 DOM 树中选择 `<li>Magritte</li>` 节点。  如果没有，请返回到“[滚动到视图](#scroll-into-view)”，然后重新开始。  
1.  将鼠标悬停在 `<li>Magritte</li>` 节点上，打开上下文菜单（右键单击），然后选择“**滚动到视图**”。  视区将向上滚动，以便你可以查看 **Magritte** 节点。  如果无法查看“**滚动到视图**”选项，请导航至“[附录：缺少选项](#appendix-missing-options)”。
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="滚动到视图" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       **滚动到视图**  
    :::image-end:::  

### <a name="search-for-nodes"></a>搜索节点  

可以按字符串、CSS 选择器或 XPath 选择器搜索 DOM 树。  

1.  将光标焦点放在“**元素**”工具上。  
1.  选择 `Control`+`F`（Windows、Linux）或 `Command`+`F` (macOS)。  搜索栏在 DOM 树的底部打开。  
1.  键入 `The Moon is a Harsh Mistress`。  最后一句在 DOM 树中突出显示。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-search-nodes-highlight.msft.png" alt-text="在搜索栏中突出显示查询" lightbox="../media/dom-elements-highlighted-search-nodes-highlight.msft.png":::
       在搜索栏中突出显示查询  
    :::image-end:::  
    
如上所述，搜索栏还支持 CSS 和 XPath 选择器。  

## <a name="edit-the-dom"></a>编辑 DOM  

你可以快速编辑 DOM 并查看更改对页面有何影响。  

### <a name="edit-content"></a>编辑内容  

若要编辑节点的内容，请双击 DOM 树中的内容。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在“**编辑内容**”下，右键选择“**Michelle**”，然后选择“**检查**”。  
    1.  在 DOM 树中，双击 `Michelle`。  换言之，双击 `<li>` 和 `</li>` 之间的文本。  此时将突出显示文本，表明该文本已被选中。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-content.msft.png" alt-text="编辑文本" lightbox="../media/dom-elements-highlighted-edit-content.msft.png":::
           编辑文本  
        :::image-end:::  
        
    1.  删除 `Michelle`，键入 `Leela`，然后选择 `Enter` 以确认更改。  DOM 中的文本从 **Michelle** 更改为 **Leela**。  

### <a name="edit-attributes"></a>编辑属性  

若要编辑属性，请双击属性名称或值。  按照说明了解如何向节点添加属性。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在“**编辑属性**”下，右键选择“**Howard**”，然后选择“**检查**”。  
1.  双击 `<li>`。  此时将突出显示文本，表示节点已被选中。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png" alt-text="编辑节点" lightbox="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png":::
       编辑节点  
    :::image-end:::  
    
1.  选择 `Right` 箭头键，添加空格，键入 `style="background-color:gold"`，然后选择 `Enter`。  节点的背景色将更改为金色。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png" alt-text="向节点添加样式属性" lightbox="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png":::
       向 `style` 节点添加属性  
    :::image-end:::  
    
### <a name="edit-node-type"></a>编辑节点类型  

若要编辑节点的类型，请双击该类型，然后键入新类型。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在“**编辑节点类型**”下，右键选择“**Hank**”，然后选择“**检查**”。  
    1.  双击 `<li>`。  文本 `li` 将突出显示。  
    1.  删除 `li`，键入 `button`，然后选择 `Enter`。  节点 `<li>` 将更改为 `<button>` 节点。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-node-type-button.msft.png" alt-text="将节点类型更改为按钮" lightbox="../media/dom-elements-highlighted-edit-node-type-button.msft.png":::
           将节点类型更改为 `button`  
        :::image-end:::  
        
### <a name="reorder-dom-nodes"></a>对 DOM 节点重新排序  

拖动节点以重新排序。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在“**对 DOM 节点重新排序**”下，右键选择“**Elvis Presley**”，然后选择“**检查**”。  
    
    > [!NOTE]
    > 它是列表中的最后一项。  
    
    1.  在 DOM 树中，将 `<li>Elvis Presley</li>` 拖动到列表顶部。  
        
        :::image type="complex" source="../media/dom-elements-reorder-dom-nodes.msft.png" alt-text="将节点拖动到列表顶部" lightbox="../media/dom-elements-reorder-dom-nodes.msft.png":::
           将节点拖动到列表顶部  
        :::image-end:::  
        
### <a name="force-state"></a>强制状态  

可强制节点保持 `:active`、`:hover`、`:focus`、`:visited` 和 `:focus-within` 等状态。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在“**强制状态**”下，将鼠标悬停在“**The Lord of the Flies**”上。  背景色变为橙色。  
    1.  将鼠标悬停在“**The Lord of the Flies**”上，打开上下文菜单（右键单击），然后选择“**检查**”。  
    1.  将鼠标悬停在 `<li class="demo--hover">The Lord of the Flies</li>` 上，打开上下文菜单（右键单击），然后选择“**强制状态** > **：hover**”。  如果未显示选项，请导航至“[附录：缺少选项](#appendix-missing-options)”。  即使你实际上没有将鼠标悬停在节点上，背景色仍保持橙色。  

### <a name="hide-a-node"></a>隐藏节点  

选择 `H` 以隐藏节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在“**隐藏节点**”下，右键选择“**The Stars My Destination**”，然后选择“**检查**”。  
    1.  选择 `H` 键。  节点处于隐藏状态。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-hide-a-node.msft.png" alt-text="节点隐藏后在 DOM 树中的外观" lightbox="../media/dom-elements-highlighted-hide-a-node.msft.png":::
           节点隐藏后在 DOM 树中的外观  
        :::image-end:::  
        
    1.  再次选择 `H` 键。  节点将再次显示。  

### <a name="delete-a-node"></a>删除节点  

选择 `Delete` 以删除节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在“**删除节点**”下，右键选择“**Foundation**”，然后选择“**检查**”。  
    1.  选择 `Delete` 键。  节点将被删除。  
    1.  选择 `Control`+`Z`（Windows、Linux）或 `Command`+`Z` (macOS)。  最后一个操作将被撤消，节点将重新出现。  

## <a name="access-nodes-in-the-console"></a>访问控制台中的节点  

开发人员工具提供了从控制台访问 DOM 节点或获取每个节点的 JavaScript 引用的一些快捷方式。  

### <a name="reference-the-currently-selected-node-with-0"></a>使用 $0 引用当前选定的节点  

当你检查节点时，节点旁边的 `== $0` 文本意味着可以在控制台中使用变量 `$0` 引用此节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在“**使用 $0 引用当前选定的节点**”下，右键选择“**The Left Hand of Darkness**”，然后选择“**检查**”。  
    1.  选择 `Escape` 键以打开控制台抽屉。  
    1.  键入 `$0` 并选择 `Enter` 键。  表达式的结果显示 `$0` 的计算结果为 `<li>The Left Hand of Darkness</li>`。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png" alt-text="控制台中第一个 $0 表达式的结果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png":::
            **控制台**中第一个 `$0` 表达式的结果  
        :::image-end:::  
        
    1.  将鼠标悬停在结果上。  节点在视区中突出显示。  
    1.  在 DOM 树中选择 `<li>Dune</li>`，在控制台中再次键入 `$0`，然后再次选择 `Enter`。  现在，`$0` 的计算结果为 `<li>Dune</li>`。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png" alt-text="控制台中第二个 $0 表达式的结果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png":::
           **控制台**中第二个 `$0` 表达式的结果  
        :::image-end:::  
        
### <a name="store-as-global-variable"></a>存储为全局变量  

如果需要多次引用某节点，请将其存储为全局变量。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在“**存储为全局变量**”下，将鼠标悬停在“**The Big Sleep**”上，打开上下文菜单（右键单击），然后选择“**检查**”。  
    1.  将鼠标悬停在 DOM 树中的 `<li>The Big Sleep</li>` 上，打开上下文菜单（右键单击），然后选择“**存储为全局变量**”。  如果未显示选项，请导航至“[附录：缺少选项](#appendix-missing-options)”。  
    1.  在控制台中键入 `temp1`，然后选择 `Enter`。  表达式的结果显示变量的计算结果为节点。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png" alt-text="temp1 表达式的结果" lightbox="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png":::
           `temp1` 表达式的结果  
        :::image-end:::  
        
### <a name="copy-js-path"></a>复制 JS 路径  

当你需要在自动测试中引用 JavaScript 路径时，请将其复制到节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在“**复制 JS 路径**”下，将鼠标悬停在“**The Brothers Karamazov**”上，打开上下文菜单（右键单击），然后选择“**检查**”。  
    1.  将鼠标悬停在 DOM 树中的 `<li>The Brothers Karamazov</li>` 上，打开上下文菜单（右键单击），然后选择“**复制”** > “**复制 JS 路径**”。  解析为节点的 `document.querySelector()` 表达式已复制到剪贴板。  
    1.  选择 `Control`+`V`（Windows、Linux）或 `Command`+`V` (macOS) 以将表达式粘贴到控制台中。  
    1.  选择 `Enter` 以计算表达式。
        
        :::image type="complex" source="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png" alt-text="“复制 JS 路径”表达式的结果" lightbox="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png":::
           “**复制 JS 路径**”表达式的结果  
        :::image-end:::  
        
## <a name="break-on-dom-changes"></a>中断 DOM 更改  

开发人员工具使你可以在 JavaScript 修改 DOM 时暂停页面的 JavaScript。  

### <a name="break-on-attribute-modifications"></a>中断属性修改  

如果要暂停导致节点任何属性发生更改的 JavaScript，请使用属性修改断点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在“**中断属性修改**”下，右键选择“**Sauerkraut**”，然后选择“**检查**”。  
    1.  在 DOM 树中，将鼠标悬停在 `<li id="target">Sauerkraut</li>` 上，打开上下文菜单（右键单击），然后选择“**中断** > **属性修改**”。  如果未显示选项，请导航至“[附录：缺少选项](#appendix-missing-options)”。
        
        :::image type="complex" source="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png" alt-text="中断属性修改" lightbox="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png":::
           **中断属性修改**  
        :::image-end:::  
        
    1.  在下一步骤中，系统将指示你选择用于暂停页面代码的按钮。  页面暂停后，你将无法再滚动页面。  必须选择“**恢复脚本**”（“![恢复脚本](../media/resume-script-icon.msft.png)”），才能使页面再次滚动。
        
        :::image type="complex" source="../media/dom-break-attribute-modifications-sources-paused-on.msft.png" alt-text="在何处继续运行脚本" lightbox="../media/dom-break-attribute-modifications-sources-paused-on.msft.png":::
           在何处继续运行脚本  
        :::image-end:::  
        
    1.  选择上面的“**设置背景**”按钮。  这会将节点的 `style` 属性设置为 `background-color:thistle`。  开发人员工具将暂停页面并突出显示导致属性发生更改的代码。  
    1.  如上所述，选择“**恢复脚本**”（“![恢复脚本](../media/resume-script-icon.msft.png)”）。  
    
### <a name="break-on-node-removal"></a>中断节点删除  

如果要在删除特定节点时暂停，请使用节点删除断点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在“**中断节点删除**”下，右键选择“**Neuromancer**”，然后选择“**检查**”。  
    1.  在 DOM 树中，将鼠标悬停在 `<li id="target">Neuromancer</li>` 上，打开上下文菜单（右键单击），然后选择“**中断** > **节点删除**”。  如果未显示选项，请导航至“[附录：缺少选项](#appendix-missing-options)”。  
    1.  选择上面的“**删除**”按钮。  开发人员工具将暂停页面并突出显示导致节点被删除的代码。  
    1.  选择“**恢复脚本**”（“![恢复脚本](../media/resume-script-icon.msft.png)”）。  
    
### <a name="break-on-subtree-modifications"></a>中断子树修改  

在节点上放置子树修改断点后，在添加或删除节点的任何后代时，开发人员工具将暂停页面。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在“**中断子树修改**”下，右键选择“**A Fire Upon The Deep**”，然后选择“**检查**”。  
    1.  在 DOM 树中，将鼠标悬停在 `<ul id="target">` 上（该节点位于 `<li>A Fire Upon the Deep</li>` 上方），打开上下文菜单（右键单击），然后选择“**中断** > **子树修改**”。  如果未显示该选项，请导航至“[附录：缺少选项](#appendix-missing-options)”。  
    1.  选择“**添加子级**。  由于向列表中添加了 `<li>` 节点，因此代码将暂停。  
    1.  选择“**恢复脚本**”（“![恢复脚本](../media/resume-script-icon.msft.png)”）。  
    
## <a name="next-steps"></a>后续步骤  

它涵盖了开发人员工具中与 DOM 相关的大部分功能。  通过将鼠标悬停在 DOM 树中的节点上，打开上下文菜单（右键单击）并尝试本教程中未涵盖的其他选项，你能够发现其余功能。  导航至“[‘元素’面板键盘快捷方式][DevToolsShortcutsElements]”。  

查看 [Microsoft Edge 开发人员工具主页][MicrosoftEdgeDevTools]，了解可使用开发人员工具执行的所有其他内容。  

<!--Navigate to [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  

## <a name="appendix-html-versus-the-dom"></a>附录：HTML 与 DOM  

以下部分快速介绍了 HTML 和 DOM 之间的区别。  

:::row:::
   :::column span="":::
      当你使用 Web 浏览器请求页面时，服务器将返回 HTML，如以下代码片段  

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
      浏览器将分析 HTML 并创建一个对象树，如以下列表。  
      
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

这一表示页面内容的对象或节点树称为 DOM。  

:::row:::
   :::column span="":::
      现在，它看起来与 HTML 相同，但假设在 HTML 底部引用的脚本运行以下代码片段。  
      
      ```javascript
      const h1 = document.querySelector('h1');
      h1.parentElement.removeChild(h1);
      const p = document.createElement('p');
      p.textContent = 'Wildcard!';
      document.body.appendChild(p);
      ```  
   :::column-end:::
   :::column span="":::
      该代码删除了 `h1` 节点，并将另一个 `p` 节点添加到 DOM。  完整的 DOM 现在显示以下列表。  
      
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

页面的 HTML 现在与 DOM 不同。  换句话说，HTML 表示初始页面内容，而 DOM 表示当前页面内容。  当 JavaScript 添加、删除或编辑节点时，DOM 将与 HTML 不同。  

导航到“[DOM 简介][MDNIntroductionToDOM]”以了解更多信息。  

<!--
## Appendix: Scroll into view  

This is a continuation of the [Scroll into view](#scroll-into-view) section.  Follow the instructions below to complete the section.  

1.  The `<li>Magritte</li>` node should still be selected in your DOM Tree.  If not, go back to [Scroll into view](#scroll-into-view) and start over.  
1.  Hover on the `<li>Magritte</li>` node, open the contextual menu \(right-click\), and choose **Scroll into view**.  Your viewport scrolls back up so that the **Magritte** node is displayed.  If you the **Scroll into view** option is not displayed, navigate to [Appendix: Missing options](#appendix-missing-options).
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="Scroll into view" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       Scroll into view  
    :::image-end:::  
    -->  

## <a name="appendix-missing-options"></a>附录：缺少选项  

本教程中的许多说明指示你将鼠标悬停在 DOM 树中的某个节点上，打开上下文菜单（右键单击），然后从弹出的上下文菜单中选择一个选项。  如果未显示上下文菜单中的指定选项，请尝试将鼠标悬停在节点文本之外并打开上下文菜单（右键单击）。  

:::image type="complex" source="../media/dom-elements-highlighted-right-click-right-side.msft.png" alt-text="未显示所有选项时在何处选择" lightbox="../media/dom-elements-highlighted-right-click-right-side.msft.png":::
   未显示所有选项时在何处选择  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发人员工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
[DevToolsCssGetStarted]: ../css/index.md "查看和更改 CSS 入门 | Microsoft Docs"  
[DevToolsShortcutsElements]: ../shortcuts/index.md#elements-tool-keyboard-shortcuts "“元素”工具键盘快捷方式 - Microsoft Edge 开发人员工具键盘快捷方式 | Microsoft Docs"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge (Chromium) 开发人员工具 DOM 示例 | Glitch"

[MDNIntroductionToDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM 简介 | MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/dom/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
