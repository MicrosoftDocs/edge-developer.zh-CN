---
description: 如何查看节点、搜索节点、编辑节点、控制台中的引用节点、中断节点更改等。
title: 开始查看和更改 DOM
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: bb2b733cfa3597c47f0a20de00e9c8b506e7c41c
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398327"
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

# <a name="get-started-with-viewing-and-changing-the-dom"></a>开始查看和更改 DOM  

完成这些交互式教程，了解使用 Microsoft Edge DevTools 查看和更改页面 DOM 的基础知识。  

本教程假定你了解 DOM 和 HTML 的区别。  导航到 [附录：HTML 与 DOM，](#appendix-html-versus-the-dom) 了解相关说明。  

## <a name="open-dom-examples"></a>打开 DOM 示例  

1.  按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) ，然后选择 **DOM 示例** 以在新选项卡中打开。  
    
    [DOM 示例][GlitchDomExamples]  
    
## <a name="view-dom-nodes"></a>查看 DOM 节点  

在"元素"面板的 DOM 树中，您可以在 DevTools 中执行所有与 DOM 相关的活动。  

### <a name="inspect-a-node"></a>检查节点  

当你对特定的 DOM 节点感兴趣时， **检查** 是打开 DevTools 并调查该节点的一种快速方法。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"检查节点"下**，右选择 **"一角"** 并选择"**检查"。**  
    
    :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png" alt-text="检查节点" lightbox="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png":::
       检查节点  
    :::image-end:::  
    
    1.  将 **打开** DevTools 的元素工具。  `<li>Michelangelo</li>` 在 **DOM 树中突出显示**。  
        
        :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png" alt-text="突出显示"一家"节点" lightbox="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png":::
           突出显示 `Michelangelo` 节点  
        :::image-end:::  
        
        1.  Choose the **Inspect** \ (![ Inspect ][ImageInspectIcon] \) icon in the top-left corner of DevTools.  
            
            :::image type="complex" source="../media/dom-elements-highlighted-select-element-page-inspect.msft.png" alt-text=""检查"图标" lightbox="../media/dom-elements-highlighted-select-element-page-inspect.msft.png":::
               " **检查"** 图标  
            :::image-end:::  
            
1.  在 **"检查节点"下**，选择 **"东京** "文本。  现在 `<li>Tokyo</li>` ，在 DOM 树中突出显示。  

检查节点也是查看和更改节点样式的第一步。  导航到["开始查看和更改 CSS"。][DevToolsCssGetStarted]  

### <a name="navigate-the-dom-tree-with-a-keyboard"></a>使用键盘导航 DOM 树  

选择 DOM 树中的节点后，可以使用键盘导航 DOM 树。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"使用键盘导航 DOM 树"** 下，右键选择 **"圈"，** 然后选择"**检查"。**  `<li>Ringo</li>` 在 DOM 树中选中。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png" alt-text="检查 Ringo 节点" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png":::
       检查 `Ringo` 节点  
    :::image-end:::  
    
    1.  选择 `Up` 箭头键 2 次。  `<ul>` 已选中。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png" alt-text="检查 ul 节点" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png":::
           检查 `ul` 节点  
        :::image-end:::  
        
    1.  选择 `Left` 箭头键。  列表 `<ul>` 折叠。  
    1.  再次 `Left` 选择箭头键。  选择节点 `<ul>` 的父节点。  在这种情况下，它是具有 `<div>` ID 的 `navigate-the-dom-tree-with-a-keyboard-1` 。  
    1.  选择 `Down` 箭头键 2 次，以便重新选择刚刚 `<ul>` 折叠的列表。  应如下所示： `<ul>... </ul>`  
    1.  选择 `Right` 箭头键。  列表将展开。  

### <a name="scroll-into-view"></a>滚动到视图中  

查看 DOM 树时，您可能会对当前不在视口中的 DOM 节点感兴趣。  例如，假设您滚动到页面底部，并且对页面顶部的节点 `<h1>` 感兴趣。  **滚动到视图中** 可快速重新定位视区，以便查看节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"滚动到视图"下**，右选择**Magritte**并选择 **"检查"。**  
1.  滚动到 DOM 示例页的底部。  
1.  仍 `<li>Magritte</li>` 应在 DOM 树中选择节点。  如果没有，请返回到 ["滚动到视图"并](#scroll-into-view) 重新开始。  
1.  将鼠标悬停在节点上，打开上下文菜单 `<li>Magritte</li>` \ (右键单击\) ，然后选择 **"滚动到视图"。**  视区将向上滚动，以便你可以查看 **Magritte** 节点。  导航到 [附录：如果](#appendix-missing-options) 无法查看"滚动到视图"选项，则 **缺少** 选项。
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="滚动到视图中" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       **滚动到视图中**  
    :::image-end:::  

### <a name="search-for-nodes"></a>搜索节点  

您可以按字符串、CSS 选择器或 XPath 选择器搜索 DOM 树。  

1.  将光标焦点放在 **"元素"** 工具上。  
1.  选择 `Control` + `F` \ (Windows、Linux\) `Command` + `F` 或 \ (macOS\) 。  搜索栏在 DOM 树的底部打开。  
1.  键入 `The Moon is a Harsh Mistress`。  最后一句在 DOM 树中突出显示。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-search-nodes-highlight.msft.png" alt-text="在搜索栏中突出显示查询" lightbox="../media/dom-elements-highlighted-search-nodes-highlight.msft.png":::
       在搜索栏中突出显示查询  
    :::image-end:::  
    
如上所述，搜索栏还支持 CSS 和 XPath 选择器。  

## <a name="edit-the-dom"></a>编辑 DOM  

您可以直接编辑 DOM，并查看更改对页面的影响。  

### <a name="edit-content"></a>编辑内容  

若要编辑节点的内容，请双击 DOM 树中的内容。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"编辑内容**"下，右选择 **"Michelle"，** 然后选择"**检查"。**  
    1.  在 DOM 树中，双击 `Michelle` 。  换句话说，双击和 之间的 `<li>` 文本 `</li>` 。  突出显示文本以指示已选中。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-content.msft.png" alt-text="编辑文本" lightbox="../media/dom-elements-highlighted-edit-content.msft.png":::
           编辑文本  
        :::image-end:::  
        
    1.  删除 `Michelle` ，键入 `Leela` ，然后选择 `Enter` 以确认更改。  DOM 中的文本从**Michelle 更改为** **Leela。**  

### <a name="edit-attributes"></a>编辑属性  

若要编辑属性，请双击属性名称或值。  按照说明了解如何向节点添加属性。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"编辑属性"下**，右选择 **"** 放大"，然后选择 **"检查"。**  
1.  双击 `<li>` 。  突出显示文本以指示节点已选中。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png" alt-text="编辑节点" lightbox="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png":::
       编辑节点  
    :::image-end:::  
    
1.  选择 `Right` 箭头键，添加空格，键入 `style="background-color:gold"` ，然后选择 `Enter` 。  节点的背景色将更改为金色。  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png" alt-text="向节点添加样式属性" lightbox="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png":::
       向 `style` 节点添加属性  
    :::image-end:::  
    
### <a name="edit-node-type"></a>编辑节点类型  

若要编辑节点的类型，请双击该类型，然后键入新类型。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"编辑节点类型"下**，右选择 **"放大**"，然后选择"**检查"。**  
    1.  双击 `<li>` 。  文本 `li` 突出显示。  
    1.  删除 `li` ，键入 `button` ，然后选择 `Enter` 。  节点 `<li>` 将更改到 `<button>` 节点。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-node-type-button.msft.png" alt-text="将节点类型更改为按钮" lightbox="../media/dom-elements-highlighted-edit-node-type-button.msft.png":::
           将节点类型更改为 `button`  
        :::image-end:::  
        
### <a name="reorder-dom-nodes"></a>对 DOM 节点重新排序  

拖动节点以重新排序。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"重新排序 DOM 节点**"下，右选择**Elvis Presley，** 然后选择 **"检查"。**  
    
    > [!NOTE]
    > 它是列表中的最后一项。  
    
    1.  在 DOM 树中，拖动 `<li>Elvis Presley</li>` 到列表顶部。  
        
        :::image type="complex" source="../media/dom-elements-reorder-dom-nodes.msft.png" alt-text="将节点拖动到列表顶部" lightbox="../media/dom-elements-reorder-dom-nodes.msft.png":::
           将节点拖动到列表顶部  
        :::image-end:::  
        
### <a name="force-state"></a>强制状态  

你可以强制节点保持状态，包括 `:active` ， 、 `:hover` 和 `:focus` `:visited` `:focus-within` 。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"强制"** 状态下，将鼠标悬停在 **"飞鸟"上**。  背景色变为橙色。  
    1.  悬停在 **"飞鸟"** 上，打开上下文菜单 \ (右键单击\) ，然后选择"检查 **"。**  
    1.  悬停在 `<li class="demo--hover">The Lord of the Flies</li>` 上，打开上下文菜单 \ (右键单击\) ，然后选择 **"强制**状态  >  **：hover"。**  导航到 [附录：如果未显示](#appendix-missing-options) 选项，则缺少选项。  即使你实际上没有将鼠标悬停在节点上，背景颜色仍保持橙色。  

### <a name="hide-a-node"></a>隐藏节点  

选择 `H` 以隐藏节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"隐藏节点"下**，右选择 **"星形我的目的地"，** 然后选择"**检查"。**  
    1.  选择 `H` 密钥。  节点处于隐藏状态。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-hide-a-node.msft.png" alt-text="隐藏后的 DOM 树中的节点外观" lightbox="../media/dom-elements-highlighted-hide-a-node.msft.png":::
           隐藏后的 DOM 树中的节点外观  
        :::image-end:::  
        
    1.  再次 `H` 选择该键。  再次显示节点。  

### <a name="delete-a-node"></a>删除节点  

选择 `Delete` 以删除节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"删除节点"下**，右选择 **"基础**"，然后选择 **"检查"。**  
    1.  选择 `Delete` 密钥。  删除节点。  
    1.  选择 `Control` + `Z` \ (Windows、Linux\) `Command` + `Z` 或 \ (macOS\) 。  最后一个操作将撤消，节点将重新出现。  

## <a name="access-nodes-in-the-console"></a>控制台中的访问节点  

DevTools 提供了一些快捷方式，用于从控制台访问 DOM 节点或获取对每个节点的 JavaScript 引用。  

### <a name="reference-the-currently-selected-node-with-0"></a>使用 $0 引用当前选定的节点  

检查节点时，节点旁边的文本意味着您可以在控制台中引用此节点 `== $0` 和变量 `$0` 。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"引用当前选定的节点与 $0"** 下，右选择"暗色的左手 **"，** 然后选择"**检查"。**  
    1.  选择 `Escape` 键以打开控制台箱。  
    1.  键入 `$0` 并选择 `Enter` 密钥。  表达式的结果显示计算 `$0` 结果为 `<li>The Left Hand of Darkness</li>` 。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png" alt-text="控制台中第一个 $0 表达式的结果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png":::
            控制台中第一 `$0` 个表达式 **的结果**  
        :::image-end:::  
        
    1.  将鼠标悬停在结果上。  该节点在视口中突出显示。  
    1.  在 `<li>Dune</li>` DOM 树中选择， `$0` 再次在控制台中键入，然后再次 `Enter` 选择。  现在， `$0` 计算结果为 `<li>Dune</li>` 。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png" alt-text="控制台中第二个 $0 表达式的结果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png":::
           控制台中第 `$0` 二个表达式 **的结果**  
        :::image-end:::  
        
### <a name="store-as-global-variable"></a>存储为全局变量  

如果需要多次引用节点，请存储为全局变量。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在**Store 作为全局变量**下，将**鼠标悬停在**"大睡眠"上，打开上下文菜单 \ (右键单击\) ，然后选择"检查 **"。**  
    1.  将鼠标悬停在 DOM 树中，打开上下文菜单 `<li>The Big Sleep</li>` \ (右键单击\) ，然后选择"存储" **作为全局变量**。  导航到 [附录：如果未显示](#appendix-missing-options) 选项，则缺少选项。  
    1.  在 `temp1` 控制台中键入，然后选择 `Enter` 。  表达式的结果显示变量计算结果为节点。  
        
        :::image type="complex" source="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png" alt-text="temp1 表达式的结果" lightbox="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png":::
           表达式 `temp1` 的结果  
        :::image-end:::  
        
### <a name="copy-js-path"></a>复制 JS 路径  

当你需要在自动测试中引用该节点时，将 JavaScript 路径复制到该节点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"复制 JS 路径**"下，将鼠标悬停在 **"小马马zov"** 上，打开上下文菜单 \ (右键单击\) ，然后选择"检查 **"。**  
    1.  将鼠标悬停在 DOM 树中，打开上下文菜单 `<li>The Brothers Karamazov</li>` \ (右键单击\) ，然后选择 **"复制**  >  **JS 路径"。**  解析 `document.querySelector()` 为节点的表达式已复制到剪贴板。  
    1.  选择 `Control` + `V` \ (Windows、Linux\) 或 `Command` + `V` \ (macOS\) 将表达式粘贴到控制台中。  
    1.  选择 `Enter` 以计算表达式。
        
        :::image type="complex" source="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png" alt-text="复制 JS 路径表达式的结果" lightbox="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png":::
           复制 JS **路径** 表达式的结果  
        :::image-end:::  
        
## <a name="break-on-dom-changes"></a>中断 DOM 更改  

DevTools 使您能够在 JavaScript 修改 DOM 时暂停页面的 JavaScript。  

### <a name="break-on-attribute-modifications"></a>中断属性修改  

若要暂停导致节点的任何属性更改的 JavaScript，请使用属性修改断点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在**属性修改中断下**，右选择**Sauerkraut，** 然后选择 **"检查"。**  
    1.  在 DOM 树中，悬停在上，打开上下文菜单 `<li id="target">Sauerkraut</li>` \ (右键单击\) ，然后选择"属性修改时**** 中断  >  **"。**  导航到 [附录：如果未显示](#appendix-missing-options) 选项，则缺少选项。
        
        :::image type="complex" source="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png" alt-text="中断属性修改" lightbox="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png":::
           **中断属性修改**  
        :::image-end:::  
        
    1.  下一步将指导你选择暂停页面代码的按钮。  暂停页面后，你无法再滚动页面。  您必须选择 Resume **Script** \ (![ Resume Script ][ImageResumeScriptIcon] \) 才能使页面再次滚动。
        
        :::image type="complex" source="../media/dom-break-attribute-modifications-sources-paused-on.msft.png" alt-text="在何处恢复脚本运行" lightbox="../media/dom-break-attribute-modifications-sources-paused-on.msft.png":::
           在何处恢复脚本运行  
        :::image-end:::  
        
    1.  选择 **上面的"设置背景** "按钮。  这会将 `style` 节点的属性设置为 `background-color:thistle` 。  DevTools 暂停页面并突出显示导致属性更改的代码。  
    1.  选择 **"恢复** (![ 脚本 ][ImageResumeScriptIcon] \) ，如前面所述。  
    
### <a name="break-on-node-removal"></a>删除节点时中断  

如果要在删除特定节点时暂停，请使用节点删除断点。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"删除节点时中断"下**，右选择 **"管理**程序"，然后选择 **"检查"。**  
    1.  在 DOM 树中，悬停在上，打开上下文菜单 `<li id="target">Neuromancer</li>` \ (右键单击\) ，然后选择"删除**节点时**中断  >  **"。**  导航到 [附录：如果未显示](#appendix-missing-options) 选项，则缺少选项。  
    1.  选择 **上面的"删除** "按钮。  DevTools 暂停页面并突出显示导致删除节点的代码。  
    1.  Choose **Resume Script** \ (Resume Script ![ ][ImageResumeScriptIcon] \) .  
    
### <a name="break-on-subtree-modifications"></a>中断子树修改  

在节点上放入子树修改断点后，当添加或删除节点的任何后代时，DevTools 将暂停页面。  

1.  [打开 DOM 示例](#open-dom-examples)。  
1.  在 **"子树修改中断"下**，右选择 **"** 深度时射击"，然后选择"**检查"。**  
    1.  在 DOM 树中，将鼠标悬停在上方的节点上，打开上下文菜单 `<ul id="target">` `<li>A Fire Upon the Deep</li>` \ (右键单击\) ，**** 然后选择"子树修改  >  ****"。  如果未显示该选项，请导航到["附录：缺少选项"。](#appendix-missing-options)  
    1.  选择 **"添加子级"。**  代码将暂停，因为 `<li>` 向列表中添加了节点。  
    1.  Choose **Resume Script** \ (Resume Script ![ ][ImageResumeScriptIcon] \) .  
    
## <a name="next-steps"></a>后续步骤  

这涵盖了 DevTools 中与 DOM 相关的大多数功能。  通过将鼠标悬停在 DOM 树中的节点上，打开上下文菜单 \ (右键单击\) ，并尝试本教程未涵盖的其他选项，您可以发现其余功能。  导航到 [元素面板键盘快捷方式][DevToolsShortcutsElements]。  

查看 [Microsoft Edge DevTools 主页][MicrosoftEdgeDevTools] ，了解可以使用 DevTools 执行的所有其他功能。  

<!--Navigate to [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  

## <a name="appendix-html-versus-the-dom"></a>附录：HTML 与 DOM  

下一节快速介绍了 HTML 和 DOM 的区别。  

:::row:::
   :::column span="":::
      使用 Web 浏览器请求页面时，服务器将返回 HTML，如以下代码段  

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
1.  Hover on the `<li>Magritte</li>` node, open the contextual menu \(right-click\), and choose **Scroll into view**.  Your viewport scrolls back up so that the **Magritte** node is displayed.  If you the **Scroll into view** option is not displayed, navigate to [Appendix: Missing options](#appendix-missing-options).
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="Scroll into view" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       Scroll into view  
    :::image-end:::  
    -->  

## <a name="appendix-missing-options"></a>附录：缺少选项  

本教程中的许多说明都指示你将鼠标悬停在 DOM 树中的节点上，打开上下文菜单 \ (右键单击\) ，然后从弹出的上下文菜单中选择一个选项。  如果未显示上下文菜单中的指定选项，请尝试将鼠标悬停在节点文本之外，然后打开上下文菜单 \ (右键单击\) 。  

:::image type="complex" source="../media/dom-elements-highlighted-right-click-right-side.msft.png" alt-text="如果未显示所有选项，请选择什么位置" lightbox="../media/dom-elements-highlighted-right-click-right-side.msft.png":::
   如果未显示所有选项，请选择什么位置  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageInspectIcon]: ../media/inspect-icon.msft.png  
[ImageResumeScriptIcon]: ../media/resume-script-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge \ (Chromium\) 开发人员工具|Microsoft Docs"  
[DevToolsCssGetStarted]: ../css/index.md "查看和更改 CSS 入门 | Microsoft 文档"  
[DevToolsShortcutsElements]: ../shortcuts/index.md#elements-tool-keyboard-shortcuts "元素工具键盘快捷方式 - Microsoft Edge DevTools 键盘快捷方式|Microsoft Docs"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge (Chromium) DevTools DOM 示例|小故障"

[MDNIntroductionToDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/dom/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
