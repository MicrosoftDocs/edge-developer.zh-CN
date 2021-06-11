---
description: 如何使用控制台工具在浏览器中与当前网页进行交互的概述
title: 使用控制台与 DOM 交互
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 56ce6b1d8f1ad98eeb9c141c2e9b002e7679d7de
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597013"
---
# <a name="use-the-console-to-interact-with-the-dom"></a>使用控制台与 DOM 交互

控制台 **工具** 并不仅仅是用于 [日志记录信息][DevtoolsConsoleConsoleLog] 或 [运行任意 JavaScript][DevtoolsConsoleConsoleJavascript]。  这也是在浏览器中与网页交互的一种很好的方法。  请考虑它是 Inspect 工具的 **脚本环境版本** 。  

## <a name="read-from-the-dom"></a>从 DOM 读取

若要引用网页的标题，请完成以下操作。  

1.  打开“**控制台**”。
    *   选择 `Control` + `Shift` + `J` \(Windows、Linux\) 或 `Command` + `Option` + `J` \(macOS\)。  
1.  在控制台中键入或复制并粘贴以下 **代码段**。  
    
    ```javascript
    document.querySelector('header')
    ```  
    
:::image type="complex" source="../media/console-dom-get-reference.msft.png" alt-text="若要在控制台中获取对标头的引用，请使用 document.querySelector" lightbox="../media/console-dom-get-reference.msft.png":::
    若要在控制台中获取对标头的引用，请使用 `document.querySelector`  
:::image-end:::  

如果选择鼠标 `Shift` + `Tab` 光标或将鼠标光标移到 HTML 结果上，DevTools 会突出显示标头。  

:::image type="complex" source="../media/console-dom-highlight-element.msft.png" alt-text="DevTools 突出显示你在控制台中选择的部分" lightbox="../media/console-dom-highlight-element.msft.png":::
    DevTools 突出显示你在控制台中选择 **的部分**  
:::image-end:::  

## <a name="manipulate-the-dom"></a>操作 DOM

您也可以操作网页。  例如，如果复制并粘贴或在控制台中键入以下内容，标题周围**** 将显示绿色边框。

```javascript
document.querySelector('header').style.border = '2em solid green'
```  

:::image type="complex" source="../media/console-dom-add-border.msft.png" alt-text="若要向元素添加边框，请使用控制台" lightbox="../media/console-dom-add-border.msft.png":::
    若要向元素添加边框，请使用 **控制台**  
:::image-end:::  

根据网页的复杂性，可能很难找到正确的要操作的元素。  但可以使用 **Inspect** 工具帮助你。  假设你想要操作页 `Documentation` 眉中的部分。

:::image type="complex" source="../media/console-dom-highlight-documentation.msft.png" alt-text="显示你在屏幕上检查的元素" lightbox="../media/console-dom-highlight-documentation.msft.png":::
    显示你在屏幕上检查的元素  
:::image-end:::  

若要获取对要操作的元素的直接引用，请完成以下操作。  

1.  使用 **Inspect** 工具选择元素。  

    :::image type="complex" source="../media/console-dom-use-inspector-to-get-element.msft.png" alt-text="若要选择元素，请使用 Inspect 工具" lightbox="../media/console-dom-use-inspector-to-get-element.msft.png":::
        若要选择元素，请使用 **Inspect** 工具  
    :::image-end:::  
    
1.  选择它，DevTools 跳转到 **"元素"** 工具。  
1.  选择 `...` DOM 树中元素旁边的菜单。  
    
    :::image type="complex" source="../media/console-dom-overflow-menu-in-elements.msft.png" alt-text="所选元素显示在元素工具的 DOM 树中，选择溢出菜单以获取更多功能" lightbox="../media/console-dom-overflow-menu-in-elements.msft.png":::
        所选元素显示在"元素"工具的 DOM **树中，** 选择溢出菜单以获取更多功能  
    :::image-end:::  
    
1.  打开上下文菜单并选择 `Copy`  >  `Copy JS Path` 。  
    
    :::image type="complex" source="../media/console-dom-copy-JS-path.msft.png" alt-text="从"元素"工具的 DOM 树中的元素复制 JavaScript 路径" lightbox="../media/console-dom-copy-JS-path.msft.png":::
        从"元素"工具的 DOM 树中的 **元素** 复制 JavaScript 路径  
    :::image-end:::  
    
1.  返回到 **控制台并粘贴** 命令。  
    
若要将链接文本更改为 `My Playground` ，请 `.textContent = "My Playground"` 添加到之前粘贴的命令中。  

:::image type="complex" source="../media/console-dom-change-content.msft.png" alt-text="使用控制台更改元素的内容" lightbox="../media/console-dom-change-content.msft.png":::
    使用 **控制台** 更改元素的内容  
:::image-end:::  

使用你想要在控制台中执行的任何 JavaScript DOM **操作**。  为了更方便， **控制台** 提供了一些帮助程序方法。  

## <a name="helpful-console-utility-methods"></a>有用的控制台实用程序方法  

许多便利的方法和快捷方式都作为控制台 [实用程序提供][DevtoolsConsoleUtilities]给你。  其中一些方法非常强大，也是您可能作为过去一系列语句撰写 `console.log()` 的一些内容。

### <a name="the-power-to-the-"></a>$ 的电源

`$`控制台中具有特殊**功能**，你可能从 jQuery 中记住这一点。

*   `$_` 存储最后一个命令的结果。  因此，如果你键入 `2 + 2` 并选择 `Enter` ，然后键入 ，控制台 `$_` 将显示**** `4` 你 。
*   `$0` `$4`是最后检查的元素的堆栈， `$0` 始终为最新元素。  因此，在上一示例中，你只需在 **Inspect** 工具中选择 元素并键入 `$0.textContent = "My Playground"` ，以获得相同的效果。
*   `$x()` 允许您使用 XPATH 选择 DOM 元素。
*   `$()` `$$()`和 是 和 的 `document.querySelector()` 较短版本 `document.querySelectorAll()` 。  
    
例如，以下代码段检索网页 \(中所有的链接，就像 \) 的简短内容一 `$$('a')` 样，将链接显示为可排序表以复制和粘贴到 Excel 中。 `document.querySelectorAll('a')`

```javascript
console.table($$('a'),['href','text']);
```  

:::image type="complex" source="../media/console-dom-get-all-links.msft.png" alt-text="获取网页中所有的链接，将结果显示为表格" lightbox="../media/console-dom-get-all-links.msft.png":::
    获取网页中所有的链接，将结果显示为表格  
:::image-end:::  

但是，如果你不希望显示信息，但希望获取它作为数据。  快捷方式 `$$('a')` 提供定位链接以及每个链接的所有属性。  问题是您只需要链接和相关文本。  

:::image type="complex" source="../media/console-dom-too-much-link-information.msft.png" alt-text="$$ 快捷方式返回的信息过多" lightbox="../media/console-dom-too-much-link-information.msft.png":::
    快捷方式 `$$` 返回的信息过多  
:::image-end:::  

快捷方式 `$$` 具有一项有趣的额外功能。  快捷方式为你提供所有方法，而不是返回纯 `NodeList` `document.querySelectorAll()` like `$$` `Array` 。  使用 `map()` 方法将信息减少为你需要的信息。  

```javascript
$$('a').map(a => {
    return {url: a.href, text: a.innerText}
})
```  

代码段将返回所有链接的 Array，作为具有 `url` 和 `text` 属性的对象。  

:::image type="complex" source="../media/console-dom-filter-link-data.msft.png" alt-text="使用 $$ 上的映射将信息筛选到最低" lightbox="../media/console-dom-filter-link-data.msft.png":::
    使用 map on `$$` 将信息筛选到最低  
:::image-end:::  

您尚未完成，多个链接是网页的内部链接或具有空文本。  使用 filter 方法可删除内部链接。  

```javascript
$$('a').map(a => {
    return {text: a.innerText, url: a.href}
}).filter(a => {
    return a.text !== '' && !a.url.match('docs.microsoft.com')
})
```  

:::image type="complex" source="../media/console-dom-filter-out-empty-links.msft.png" alt-text="获取不为空且为外部的链接" lightbox="../media/console-dom-filter-out-empty-links.msft.png":::
    获取不为空且为外部的链接  
:::image-end:::  

如网页开始部分显示，您还可以更改这些元素。  例如，以下代码段在所有外部链接周围创建绿色边框：

```javascript
$$('a[href^="https://"]').forEach(
  a => a.style.border = '1px solid green'
)
```  

:::image type="complex" source="../media/console-dom-highlight-links.msft.png" alt-text="若要突出显示所有外部链接，请在每个链接周围添加绿色边框" lightbox="../media/console-dom-highlight-links.msft.png":::
    若要突出显示所有外部链接，请在每个链接周围添加绿色边框  
:::image-end:::  

使用 CSS 选择器功能，而不是编写复杂的 JavaScript 来筛选结果。  

若要为网页上不是内嵌图像的所有图像创建 和 信息的表， `src` `alt` 请完成以下操作。  

1.  打开“**控制台**”。  
1.  键入或复制并粘贴以下代码段。  

```javascript
console.table($$('img:not([src^=data])'), ['src','alt'])
```  

:::image type="complex" source="../media/console-dom-complex-CSS-selector.msft.png" alt-text="若要选择元素，请使用复杂的 CSS 选择器" lightbox="../media/console-dom-complex-CSS-selector.msft.png":::
    若要选择元素，请使用复杂的 CSS 选择器  
:::image-end:::  

准备好进行更复杂的示例了吗？  通过 markdown 生成的 HTML 网页（如本文）具有每个标题的自动 ID 值，以允许您深层链接到该部分。  例如，对 `# New features` 进行更改 `<h1 id="new-features">New features</h1>` 。  

若要列出要复制和粘贴的所有自动标题，请完成以下操作。  

1.  打开“**控制台**”。  
1.  键入或复制并粘贴以下代码段。  

```javascript
let out = '';
$$('#main [id]').filter(
    elm => {return elm.nodeName.startsWith('H')}
).forEach(elm => {
   out += elm.innerText + "\n" + 
          document.location.href + '#' +
          elm.id + "\n";
});
console.log(out);
```  

结果是包含每个标题的内容的文本，后跟指向该标题的完整 URL。  

:::image type="complex" source="../media/console-dom-get-generated-headings.msft.png" alt-text="从网页获取所有标题和生成的 URL" lightbox="../media/console-dom-get-generated-headings.msft.png":::
    从网页获取所有标题和生成的 URL  
:::image-end:::  

### <a name="clean-up-with-clear-and-copy"></a>清除并复制

在控制台中 **开发时**，情况可能会变得混乱。  你可能会觉得在复制和粘贴时尝试选择结果感到沮丧。  以下两种实用程序方法可帮助您。  

*   `copy()` 将你提供的任何内容复制到剪贴板。  `copy()`在将该方法与复制最后的结果混合使用时， `$_` 该方法尤其有用。
*   `clear()` 清除 **控制台**。

### <a name="read-and-monitor-events"></a>读取和监视事件

Console 的另外两种有趣的 **实用程序方法处理** 事件处理。

*   `getEventListeners(node)` 列出节点的所有事件侦听器。
*   `monitorEvents(node, events)` 监视和记录节点上发生的事件。

若要列出分配给网页中第一个表单的所有事件侦听器，请完成以下操作。  

1.  打开“**控制台**”。  
1.  键入或复制并粘贴以下代码段。  
    
    ```javascript
    getEventListeners($('form')); 
    ```  

:::image type="complex" source="../media/console-dom-get-form-events.msft.png" alt-text="获取网页中第一个表单的所有事件侦听器" lightbox="../media/console-dom-get-form-events.msft.png":::
    获取网页中第一个表单的所有事件侦听器  
:::image-end:::  

监视时，每次对指定元素进行更改时，都会**** 在控制台中收到通知。  将要侦听的事件定义为第二个参数。  定义要监视的事件非常重要，否则将报告元素发生的任何事件。

若要每次滚动时在 **控制台** 中收到通知，请调整窗口大小，或当用户在搜索表单中输入内容时，请完成以下操作。  

1.  打开“**控制台**”。  
1.  键入或复制并粘贴以下代码段。  
    
    ```javascript
    monitorEvents(window, ['resize', 'scroll']);
    monitorEvents($0, 'keyup');
    ```  
    
:::image type="complex" source="../media/console-dom-monitor-events.msft.png" alt-text="控制台显示窗口上发生的每个滚动事件" lightbox="../media/console-dom-monitor-events.msft.png":::
    **控制台** 显示窗口上发生的每个滚动事件  
:::image-end:::  

若要记录当前选择的元素上的任何键操作，请专注于标题中的搜索表单并选择一些键。  

:::image type="complex" source="../media/console-dom-monitor-key-events.msft.png" alt-text="控制台显示窗体上发生的键更新事件" lightbox="../media/console-dom-monitor-key-events.msft.png":::
    **控制台** `keyup` 显示窗体上发生的事件  
:::image-end:::  

若要停止它，请删除通过以下代码段设置的监视。  

```javascript
unmonitorEvents(window, ['resize', 'scroll']);
unmonitorEvents($0, 'key');
```  

## <a name="reuse-dom-manipulation-scripts"></a>重用 DOM 操作脚本

你可能会发现从控制台操作 DOM **非常有用**。  你很快就会遇到控制台作为开发 **平台** 的限制。  好消息是，DevTools [中的"][DevtoolsSourcesIndex] 源"工具提供了功能齐全的开发环境。  在 **"源** "工具中，可以完成以下操作。  

*   将控制台脚本**存储为**[代码段][DevToolsJavascriptSnippets]。  
*   使用键盘快捷方式或编辑器在网页中运行脚本。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleConsoleJavascript]: ./console-javascript.md "作为 JavaScript 环境的控制台|Microsoft Docs"  
[DevtoolsConsoleConsoleLog]: ./console-log.md "控制台工具控制台中的|Microsoft Docs"  
[DevtoolsConsoleUtilities]: ./utilities.md "控制台实用程序 API 参考 | Microsoft Docs"  

[DevToolsJavascriptSnippets]: ../javascript/snippets.md "使用 Microsoft Edge DevTools 工具在任意页面上运行 JavaScript | Microsoft Docs"  
[DevtoolsSourcesIndex]: ../sources/index.md "源工具概述 | Microsoft Docs"  
