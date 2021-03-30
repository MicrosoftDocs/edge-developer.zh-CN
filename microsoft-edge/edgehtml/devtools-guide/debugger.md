---
description: 使用调试器逐步调试代码并排除故障。
title: 'Debugger - DevTools (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 调试程序， 调试， 断点， 监视程序， 服务工作者， 缓存 api， Web 存储， Cookie
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cc2d7ef0d3ee5c16b8cbc73745a8f9ea30bd9d09
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232732"
---
# <span data-ttu-id="c21dc-104">Debugger - DevTools (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="c21dc-104">Debugger - DevTools (EdgeHTML)</span></span>

<span data-ttu-id="c21dc-105">使用 **调试器** 逐步调试代码、设置监视和断点、实时编辑代码并检查缓存。</span><span class="sxs-lookup"><span data-stu-id="c21dc-105">Use the **Debugger** to step through code, set watches and breakpoints, live edit your code and inspect your caches.</span></span> <span data-ttu-id="c21dc-106">测试代码并排除故障，方法为：</span><span class="sxs-lookup"><span data-stu-id="c21dc-106">Test and troubleshoot your code by:</span></span>

- <span data-ttu-id="c21dc-107">[从](#resource-picker)[加载的](#file-search)源文件浏览和搜索代码</span><span class="sxs-lookup"><span data-stu-id="c21dc-107">[Browsing](#resource-picker) and [searching](#file-search) code from your loaded source files</span></span>
- <span data-ttu-id="c21dc-108">[在逐步执行](#toolbar) 代码时控制执行流</span><span class="sxs-lookup"><span data-stu-id="c21dc-108">[Controlling the execution flow](#toolbar) as you step through your code</span></span>
- <span data-ttu-id="c21dc-109">[管理页面存储资源](./storage.md#cache-manager)，包括[服务工作者和缓存](./service-workers.md)[、Cookie](./storage.md#cookies-list)和[Web 存储](./storage.md#local-and-session-storage-managers)</span><span class="sxs-lookup"><span data-stu-id="c21dc-109">[Managing page storage resources](./storage.md#cache-manager), including the [service workers and cache](./service-workers.md), [cookies](./storage.md#cookies-list) and [web storage](./storage.md#local-and-session-storage-managers)</span></span>  
- <span data-ttu-id="c21dc-110">[在代码运行时设置](#debug-window) 断点并实时编辑代码</span><span class="sxs-lookup"><span data-stu-id="c21dc-110">[Setting breakpoints and live editing](#debug-window) your code as it runs</span></span>
- <span data-ttu-id="c21dc-111">[调试时跟踪和编辑](#watches) 本地变量</span><span class="sxs-lookup"><span data-stu-id="c21dc-111">[Tracking and editing local variables](#watches) as you debug</span></span>
- <span data-ttu-id="c21dc-112">[根据需要隐藏或显示](#call-stack) 调用代码中的异步代码和库代码</span><span class="sxs-lookup"><span data-stu-id="c21dc-112">[Hiding or showing asynchronous code and library code](#call-stack) from your callstack as needed</span></span>
- <span data-ttu-id="c21dc-113">[为](#breakpoints) XmlHttpRequests、事件和 DOM 威胁添加 [专门的断点](#dom-breakpoints)</span><span class="sxs-lookup"><span data-stu-id="c21dc-113">[Adding specialized breakpoints](#breakpoints) for XmlHttpRequests, events and [DOM mutations](#dom-breakpoints)</span></span>

![Microsoft Edge DevTools 调试器](./media/debugger.png)

<span data-ttu-id="c21dc-115">有三种方法可以开始调试会话。</span><span class="sxs-lookup"><span data-stu-id="c21dc-115">There are three ways to begin a debugging session.</span></span>

1. **<span data-ttu-id="c21dc-116">设置断点。</span><span class="sxs-lookup"><span data-stu-id="c21dc-116">Set a breakpoint.</span></span>** <span data-ttu-id="c21dc-117">当代码执行完成时，你将进入调试程序，并能够逐步调试代码。</span><span class="sxs-lookup"><span data-stu-id="c21dc-117">When the execution of your code reaches it, you'll enter the debugger and be able to step through your code.</span></span>
2. **<span data-ttu-id="c21dc-118">在代码中启动中断。</span><span class="sxs-lookup"><span data-stu-id="c21dc-118">Initiate a break in code.</span></span>** <span data-ttu-id="c21dc-119">单击 [**工具栏按钮**](#toolbar) 或 \* (的\* ") "暂停图标 `Ctrl+Shift+B` 。</span><span class="sxs-lookup"><span data-stu-id="c21dc-119">Click the [**Break**](#toolbar) (*pause* icon) toolbar button or `Ctrl+Shift+B`.</span></span> <span data-ttu-id="c21dc-120">调试程序将在下一个执行语句上中断。</span><span class="sxs-lookup"><span data-stu-id="c21dc-120">The debugger will break on the next statement of execution.</span></span>
3. **<span data-ttu-id="c21dc-121">设置异常行为。</span><span class="sxs-lookup"><span data-stu-id="c21dc-121">Set exception behavior.</span></span>** <span data-ttu-id="c21dc-122">使用 [**"更改异常**](#toolbar) 行为" () 代码引发异常时中断 `Ctrl+Shift+E` 调试程序。</span><span class="sxs-lookup"><span data-stu-id="c21dc-122">Use the [**Change exception behavior**](#toolbar) menu (`Ctrl+Shift+E`) to break into the debugger when your code throws an exception.</span></span> <span data-ttu-id="c21dc-123">默认情况下，调试器设置为"从不 *中断异常*"，但它们将记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="c21dc-123">By default, the debugger is set to *Never break on exceptions*, but they are logged to the console.</span></span>

## <span data-ttu-id="c21dc-124">资源选取器</span><span class="sxs-lookup"><span data-stu-id="c21dc-124">Resource picker</span></span>

<span data-ttu-id="c21dc-125">通常，调试的第一步是在代码中设置要排除故障的断点。</span><span class="sxs-lookup"><span data-stu-id="c21dc-125">Often the first step in debugging is to set breakpoints in the code you're looking to troubleshoot.</span></span> <span data-ttu-id="c21dc-126">You can find all the code files currently loaded by the page from the *Resource picker* pane， including *.html， .css* and *.js* files.</span><span class="sxs-lookup"><span data-stu-id="c21dc-126">You can find all the code files currently loaded by the page from the *Resource picker* pane, including *.html, .css* and *.js* files.</span></span>

 <span data-ttu-id="c21dc-127">单击文件条目将在调试窗口中打开该文件的选项卡，并加粗[](#debug-window)文件名的文本以指示 (*开发人员*指南文件名如上图所示) 。</span><span class="sxs-lookup"><span data-stu-id="c21dc-127">Clicking on a file entry will open a tab for that file in the [Debug window](#debug-window) and bold the text of the file name to indicate this (as *devtools-guide* file name is in the illustration above).</span></span> <span data-ttu-id="c21dc-128">然后，可以从调试窗口设置该文件中的 [断点](#debug-window)。</span><span class="sxs-lookup"><span data-stu-id="c21dc-128">You can then set breakpoints within that file from the [Debug window](#debug-window).</span></span>

![调试器资源选取器](./media/debugger_resource_picker.png)

<span data-ttu-id="c21dc-130">从资源*选取*器上下文菜单中，还可以将文件标记为库代码 () ，从而可以选择在调试器中跳过该代码，然后从调用堆栈窗格中隐藏它 `Ctrl+L` 。 [  ](#call-stack) [](#debug-window)</span><span class="sxs-lookup"><span data-stu-id="c21dc-130">From the *Resource picker* context menu, you can also mark a file as **library code** (`Ctrl+L`), giving you the option to [skip over that code in the debugger](#debug-window) and [hide it from the **Call stack** pane](#call-stack).</span></span> <span data-ttu-id="c21dc-131">单击 (或) 将文件切换回以前的值 `Ctrl+L` 作为 *我的代码* 或 *库代码*。</span><span class="sxs-lookup"><span data-stu-id="c21dc-131">Clicking (or `Ctrl+L`) again will toggle the file back to its previous value as *my code* or *library code*.</span></span>

### <span data-ttu-id="c21dc-132">文件搜索</span><span class="sxs-lookup"><span data-stu-id="c21dc-132">File search</span></span>

<span data-ttu-id="c21dc-133">当您*在*源中尝试查找 () 字符串时，请使用"在文件中查找"命令) 命令 `Ctrl` + `Shift` + `F` 。</span><span class="sxs-lookup"><span data-stu-id="c21dc-133">Use the *Find in files* command (`Ctrl`+`Shift`+`F`) when you have a specific string of code you're trying to find in the source.</span></span> <span data-ttu-id="c21dc-134">工具栏提供不同的搜索选项，包括正则表达式。</span><span class="sxs-lookup"><span data-stu-id="c21dc-134">The toolbar provides different search options, including regular expressions.</span></span> <span data-ttu-id="c21dc-135">单击搜索结果将 *焦点在指定的* 文件和行上的调试窗口。</span><span class="sxs-lookup"><span data-stu-id="c21dc-135">Clicking on a search result will focus the *Debug window* on the specified file and line.</span></span>

![调试器文件搜索窗格](./media/debugger_file_search.png)

## <span data-ttu-id="c21dc-137">调试窗口</span><span class="sxs-lookup"><span data-stu-id="c21dc-137">Debug window</span></span>

<span data-ttu-id="c21dc-138">调试 *窗口* 是设置断点、逐步调试代码和在调试时实时编辑脚本的位置。</span><span class="sxs-lookup"><span data-stu-id="c21dc-138">The *Debug window* is where you set your breakpoints, step through code, and live edit your script as you debug.</span></span> <span data-ttu-id="c21dc-139">单击任何脚本命令的左侧以添加 (或删除) **断点**。</span><span class="sxs-lookup"><span data-stu-id="c21dc-139">Click to the left of any script command to add (or remove) a **Breakpoint**.</span></span> <span data-ttu-id="c21dc-140">使用右键单击上下文菜单或断[](#breakpoints)点窗格，通过提供 逻辑表达式将条件添加到断点，该逻辑表达式会导致调试程序在该位置计算*True*时中断。</span><span class="sxs-lookup"><span data-stu-id="c21dc-140">Use the right-click context menu or [**Breakpoints**](#breakpoints) pane to *Add a condition* to the breakpoint by supplying a logical expression that causes the debugger to break if it evaluates *True* at that location.</span></span>

![调试窗口命令](./media/debugger_window.png)

<span data-ttu-id="c21dc-142">调试窗口的其他功能包括以下控件：</span><span class="sxs-lookup"><span data-stu-id="c21dc-142">Other features of the debug window include controls for:</span></span>

### <span data-ttu-id="c21dc-143">1. 代码编辑</span><span class="sxs-lookup"><span data-stu-id="c21dc-143">1. Code editing</span></span>

<span data-ttu-id="c21dc-144">可以在调试会话期间编辑 JavaScript 实时。</span><span class="sxs-lookup"><span data-stu-id="c21dc-144">You can edit your JavaScript live during a debugging session.</span></span> <span data-ttu-id="c21dc-145">进行更改后，单击"保存 () 代码部分下次运行时 <strong> </strong> `Ctrl+S` 测试所做的更改。</span><span class="sxs-lookup"><span data-stu-id="c21dc-145">Once you make your changes, click <strong>Save</strong> (`Ctrl+S`) to test your changes next time that section of code runs.</span></span> <span data-ttu-id="c21dc-146">如果更改了未保存的代码，则 (\*) 将在"调试"窗口选项卡中的文件名之前 *显示* 星号。</span><span class="sxs-lookup"><span data-stu-id="c21dc-146">If you have unsaved code changes, an asterisk (\*) will appear before the file name in the *Debug window* tab.</span></span>

<span data-ttu-id="c21dc-147">单击 **"比较文档与原始文档"** 按钮以查看您更改的内容的差异。</span><span class="sxs-lookup"><span data-stu-id="c21dc-147">Click the **Compare document to original** button to view the diff of what you changed.</span></span>

![调试器中已编辑代码的差异视图](./media/debugger_edit_code.png)

<span data-ttu-id="c21dc-149">请注意以下约束：</span><span class="sxs-lookup"><span data-stu-id="c21dc-149">Please be aware of the following constraints:</span></span>

- <span data-ttu-id="c21dc-150">脚本编辑仅适用于外部 *.js*文件 (而未嵌入 `<script>` \*.html) \*</span><span class="sxs-lookup"><span data-stu-id="c21dc-150">Script editing only works in external *.js* files (and not embedded `<script>` within *.html*)</span></span>
- <span data-ttu-id="c21dc-151">编辑保存在内存中，在重新加载文档时刷新，因此无法运行处理程序中的编辑， `DOMContentLoaded` 例如</span><span class="sxs-lookup"><span data-stu-id="c21dc-151">Edits are saved in memory and flushed when the document is reloaded, thus you won't be able to run edits inside a `DOMContentLoaded` handler, for example</span></span>
- <span data-ttu-id="c21dc-152">目前，无法 ("另存为"选项) 从 DevTools 将编辑保存到磁盘</span><span class="sxs-lookup"><span data-stu-id="c21dc-152">Currently there's no way (such as a **Save As** option) to save your edits to disk from the DevTools</span></span>

### <span data-ttu-id="c21dc-153">2. 代码格式</span><span class="sxs-lookup"><span data-stu-id="c21dc-153">2. Code formatting</span></span>

<span data-ttu-id="c21dc-154">使用这些控件设置缩小代码的格式，以在调试时提高可读性：</span><span class="sxs-lookup"><span data-stu-id="c21dc-154">Use these controls to format minified code for better readability as you debug:</span></span>

#### <span data-ttu-id="c21dc-155">非常 `Ctrl+Shift+P` () </span><span class="sxs-lookup"><span data-stu-id="c21dc-155">Pretty print (`Ctrl+Shift+P`)</span></span> 
<span data-ttu-id="c21dc-156">根据 JavaScript 约定添加换行符和花括号对齐方式。</span><span class="sxs-lookup"><span data-stu-id="c21dc-156">Adds line breaks and curly brace alignment per JavaScript conventions.</span></span> <span data-ttu-id="c21dc-157">即使通过此选项使压缩代码更具可读性，也可能具有与原始源代码中大为不同的函数、选择器和变量名称。</span><span class="sxs-lookup"><span data-stu-id="c21dc-157">Even compressed code that's been made more readable with this option may have function, selector, and variable names that are much different than in your original source code.</span></span> <span data-ttu-id="c21dc-158">在这些情况下，切换 [*源映射选项*](#source-maps) 可能可用。</span><span class="sxs-lookup"><span data-stu-id="c21dc-158">In these cases, the [*Toggle source maps*](#source-maps) option might be available.</span></span>

#### <span data-ttu-id="c21dc-159">Word 自动换 `Alt+W` () </span><span class="sxs-lookup"><span data-stu-id="c21dc-159">Word wrap (`Alt+W`)</span></span>
<span data-ttu-id="c21dc-160">调整代码以适应调试窗口的当前边距 (无需水平滚动) 。</span><span class="sxs-lookup"><span data-stu-id="c21dc-160">Adjusts code to fit within the current margins of the debug window (eliminating the need for horizontal scrolling).</span></span>

### <span data-ttu-id="c21dc-161">3. 代码范围</span><span class="sxs-lookup"><span data-stu-id="c21dc-161">3. Code scoping</span></span>

<span data-ttu-id="c21dc-162">你可以指示调试器忽略某些文件，将标记为库代码 () `Ctrl+L` 按钮。</span><span class="sxs-lookup"><span data-stu-id="c21dc-162">You can direct the debugger to ignore certain files with the **Mark as library code** (`Ctrl+L`) button.</span></span> <span data-ttu-id="c21dc-163">默认情况下，"仅调试[**我的**](#toolbar)代码工具栏"按钮打开，这意味着调试程序将跳过标记为库代码的任何文件，并且这些文件不会显示在 调试程序调用[堆栈中](#call-stack)。</span><span class="sxs-lookup"><span data-stu-id="c21dc-163">By default, the [**Debug just my code**](#toolbar) toolbar button is on, meaning that the debugger will skip over any files that you mark as *library code* and they will not appear in the debugger [call stack](#call-stack).</span></span> <span data-ttu-id="c21dc-164">将按钮标记为 (代码 时，)  `Ctrl+L` 将删除此标志。</span><span class="sxs-lookup"><span data-stu-id="c21dc-164">Depressing the button (**Mark as my code**, `Ctrl+L`) will remove this flag.</span></span>

<span data-ttu-id="c21dc-165">若要跨调试会话跟踪库，可以编辑这些文件以维护默认列表或为域或文件类型添加通配符：</span><span class="sxs-lookup"><span data-stu-id="c21dc-165">For keeping track of libraries across debugging sessions, you can edit these files to maintain a default list or add wildcards for a domain or file type:</span></span>

```JavaScript
%APPDATA%\..\LocalLow\Microsoft\F12\header\MyCode.json and %APPDATA%\..\Local\Microsoft\F12\header\MyCode.json
```

#### <span data-ttu-id="c21dc-166">源映射</span><span class="sxs-lookup"><span data-stu-id="c21dc-166">Source maps</span></span>

<span data-ttu-id="c21dc-167">你将看到为用编译为 JavaScript 或 CSS 的语言编写的代码启用**切换**源映射按钮，该按钮提供源 映射 (到原始源文件的中间) 。</span><span class="sxs-lookup"><span data-stu-id="c21dc-167">You will see the **Toggle source maps** button enabled for code written in a language that compiles to JavaScript or CSS and that provides a *source map* (an intermediate file mapping to the original source).</span></span> <span data-ttu-id="c21dc-168">此选项指示调试程序显示要用于调试 (而不是实际在浏览器中运行的已编译) 。 </span><span class="sxs-lookup"><span data-stu-id="c21dc-168">This option directs the debugger to present the original source to use for debugging (rather than the compiled file that's *actually* running in the browser).</span></span>

<span data-ttu-id="c21dc-169">DevTools 将检查生成 JavaScript 文件的编译器是否包含包含地图文件名的注释。</span><span class="sxs-lookup"><span data-stu-id="c21dc-169">The DevTools will check if the compiler that generated the JavaScript file included a comment with the name of the map file.</span></span> <span data-ttu-id="c21dc-170">例如，如果编译器将myfile.js压缩*myfile.min.js，它*也可能生成映射文件*myfile.min.js.map，* 并包含压缩文件中的注释，如下所示： </span><span class="sxs-lookup"><span data-stu-id="c21dc-170">For example, if a compiler compressed *myfile.js* to *myfile.min.js*, it might also generate a map file, *myfile.min.js.map* and include a comment in the compressed file like this:</span></span>

```JavaScript
//# sourceMappingURL=myfile.min.js.map
```

![调试文件选项卡上下文菜单](./media/debug_file_contextmenu.png)

<span data-ttu-id="c21dc-172">如果 DevTools 无法自动查找地图，你可以选择该文件的源映射。</span><span class="sxs-lookup"><span data-stu-id="c21dc-172">If the DevTools can't find the map automatically, you can choose a source map for that file.</span></span> <span data-ttu-id="c21dc-173">右键单击文件的选项卡以查找 **"选择源映射"** 选项。</span><span class="sxs-lookup"><span data-stu-id="c21dc-173">Right-click the file's tab to find the **Choose source map** option.</span></span> 

## <span data-ttu-id="c21dc-174">工具栏</span><span class="sxs-lookup"><span data-stu-id="c21dc-174">Toolbar</span></span>

<span data-ttu-id="c21dc-175">使用调试器 *工具栏* 控制如何逐步执行代码，以及要逐步执行或忽略的代码。</span><span class="sxs-lookup"><span data-stu-id="c21dc-175">Use the debugger *Toolbar* to control how you step through code, and what code to step through or ignore.</span></span> <span data-ttu-id="c21dc-176">在此处，还可以跨代码文件对特定字符串执行全文搜索。</span><span class="sxs-lookup"><span data-stu-id="c21dc-176">From here you can also do a full text search across your code files for specific strings.</span></span>

![调试器工具栏](./media/debugger_toolbar.png)

### <span data-ttu-id="c21dc-178">1. `F5` () / () `Ctrl+Shift+B`</span><span class="sxs-lookup"><span data-stu-id="c21dc-178">1. Continue (`F5`) / Break (`Ctrl+Shift+B`)</span></span>
 <span data-ttu-id="c21dc-179">**继续** `F5` () 代码执行到下一个断点。</span><span class="sxs-lookup"><span data-stu-id="c21dc-179">**Continue** (`F5`) continues code execution to the next breakpoint.</span></span> <span data-ttu-id="c21dc-180">按住 `F5` 将反复移动过去中断，直到释放它。</span><span class="sxs-lookup"><span data-stu-id="c21dc-180">Holding down `F5` will repeatedly move past breaks until you release it.</span></span> 

 <span data-ttu-id="c21dc-181">**中断** () 运行下一 `Ctrl+Shift+B` 个语句后将中断调试器。</span><span class="sxs-lookup"><span data-stu-id="c21dc-181">**Break** (`Ctrl+Shift+B`) will break into the debugger after running the next statement.</span></span>

### <span data-ttu-id="c21dc-182">2. 步骤函数 (`F11` `Ctrl+F10` 、) `Shift+F11`</span><span class="sxs-lookup"><span data-stu-id="c21dc-182">2. Step functions (`F11`, `Ctrl+F10`, `Shift+F11`)</span></span>
 <span data-ttu-id="c21dc-183">进入 ()  `F11` 调用的函数的步骤。</span><span class="sxs-lookup"><span data-stu-id="c21dc-183">**Step into** (`F11`) steps into the function being called.</span></span> 

 <span data-ttu-id="c21dc-184">逐步 ()  `Ctrl+F10` 调用的函数的步骤。</span><span class="sxs-lookup"><span data-stu-id="c21dc-184">**Step over** (`Ctrl+F10`) steps over the function being called.</span></span> 

 <span data-ttu-id="c21dc-185">**退出** `Shift+F11` () 退出当前函数并进入调用函数。</span><span class="sxs-lookup"><span data-stu-id="c21dc-185">**Step out** (`Shift+F11`) steps out of the current function and into the calling function.</span></span> 

 <span data-ttu-id="c21dc-186">如果使用这些命令时，调试程序将逐一执行下一语句（如果它不在函数中）。</span><span class="sxs-lookup"><span data-stu-id="c21dc-186">The debugger will step to the next statement if it is not at a function when these commands are used.</span></span>

### <span data-ttu-id="c21dc-187">3. 中断新工作线程 `Ctrl+Shift+W` () </span><span class="sxs-lookup"><span data-stu-id="c21dc-187">3. Break on new worker (`Ctrl+Shift+W`)</span></span>
 <span data-ttu-id="c21dc-188">在新建 Web 工作线程时 [中断](https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers)。</span><span class="sxs-lookup"><span data-stu-id="c21dc-188">Breaks on the creation of a new [web worker](https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers).</span></span>

### <span data-ttu-id="c21dc-189">4. 异常控件</span><span class="sxs-lookup"><span data-stu-id="c21dc-189">4. Exception control</span></span>
<span data-ttu-id="c21dc-190">更改异常 ()  打开选项以更改调试程序对异常 `Ctrl+Shift+E` 的反应。</span><span class="sxs-lookup"><span data-stu-id="c21dc-190">**Change exception behavior** (`Ctrl+Shift+E`) opens options to change how the debugger reacts to exceptions.</span></span> <span data-ttu-id="c21dc-191">默认情况下，调试程序将忽略异常并记录到 [**控制台**](./console.md)。</span><span class="sxs-lookup"><span data-stu-id="c21dc-191">By default exceptions are ignored by the debugger and logged to the [**Console**](./console.md).</span></span> <span data-ttu-id="c21dc-192">您可以选择中断所有异常，或者仅中断代码中的语句未处理的异常 (未处理的异常中断 `try...catch`) 。 </span><span class="sxs-lookup"><span data-stu-id="c21dc-192">You can choose to *Break on all exceptions*, or just those not being handled by `try...catch` statements in your code (*Break on unhandled exceptions*).</span></span>

### <span data-ttu-id="c21dc-193">5. 查看搜索结果</span><span class="sxs-lookup"><span data-stu-id="c21dc-193">5. View search results</span></span>
<span data-ttu-id="c21dc-194"> (禁用 **。) /隐藏** 结果切换"在文件 [*搜索结果中查找"*](#6-find-in-files-ctrlf) 的显示。</span><span class="sxs-lookup"><span data-stu-id="c21dc-194">(Currently disabled.) **Show/Hide results** toggles the display of [*Find in files*](#6-find-in-files-ctrlf) search results.</span></span>

### <span data-ttu-id="c21dc-195">6. 在文件 `Ctrl+F` () </span><span class="sxs-lookup"><span data-stu-id="c21dc-195">6. Find in files (`Ctrl+F`)</span></span>
 <span data-ttu-id="c21dc-196">在文件 ()  在资源选取器中所有加载的文件中运行文本 `Ctrl+F` [*搜索*](#resource-picker)。</span><span class="sxs-lookup"><span data-stu-id="c21dc-196">**Find in files** (`Ctrl+F`) runs a text search through all the loaded files within the [*Resource picker*](#resource-picker).</span></span> <span data-ttu-id="c21dc-197">如果找到该文本，它将打开与搜索字符串匹配的第一个文件。</span><span class="sxs-lookup"><span data-stu-id="c21dc-197">If the text is found, it opens the first file matching the search string.</span></span> <span data-ttu-id="c21dc-198">按 `Enter` 或 `F3` 带你进行下一个匹配。</span><span class="sxs-lookup"><span data-stu-id="c21dc-198">Pressing `Enter` or `F3` takes you to the next match.</span></span>

### <span data-ttu-id="c21dc-199">7. 仅调试我的 `Ctrl+J` () </span><span class="sxs-lookup"><span data-stu-id="c21dc-199">7. Debug just my code (`Ctrl+J`)</span></span>
 <span data-ttu-id="c21dc-200">调试我的代码 () 充当切换，以包含或排除在调试器中步骤中标记为库代码 `Ctrl+J` 的所有文件。 [](#3-code-scoping)</span><span class="sxs-lookup"><span data-stu-id="c21dc-200">**Debug just my code** (`Ctrl+J`) acts as a toggle to include or exclude all the files that have been marked as [library code](#3-code-scoping) as you step through the debugger.</span></span>

### <span data-ttu-id="c21dc-201">8. 调试器连接</span><span class="sxs-lookup"><span data-stu-id="c21dc-201">8. Debugger connection</span></span>
<span data-ttu-id="c21dc-202">**Disconnect/Connect 调试器** 实质上是调试器开/关开关。</span><span class="sxs-lookup"><span data-stu-id="c21dc-202">**Disconnect/Connect debugger** is essentially the on/off switch for the debugger.</span></span>

## <span data-ttu-id="c21dc-203">Watches</span><span class="sxs-lookup"><span data-stu-id="c21dc-203">Watches</span></span>

<span data-ttu-id="c21dc-204">使用 **监视** 窗格浏览所有对象和变量的目录 (局部变量 **) （** 在本地和全局范围内）可用于作为调试器中当前中断焦点的语句。</span><span class="sxs-lookup"><span data-stu-id="c21dc-204">Use the **Watches** pane to browse a catalog of all objects and variables (**Locals**), both in the local and global scope, available to the statement that is the focus of the current break in the debugger.</span></span>

![监视窗格](./media/debugger_watches.png)

<span data-ttu-id="c21dc-206">您可以通过添加监视 (**添加**监视 、) 和通过双击它或从上下文菜单中选择编辑值来修改任何可编辑的值来跟踪特定变量的进入和超出范围的值 `Ctrl+W` 。  </span><span class="sxs-lookup"><span data-stu-id="c21dc-206">You can track the value of specific variables as they pass in and out of scope by adding a watch (**Add watch**, `Ctrl+W`) and modify any editable values by double-clicking on it or by selecting **Edit value** from the *Context menu*.</span></span> <span data-ttu-id="c21dc-207">使用"删除 () / `Ctrl+D` **删除所有**按钮或从上下文菜单中清除监视。</span><span class="sxs-lookup"><span data-stu-id="c21dc-207">Clear your watches using the **Delete** (`Ctrl+D`) / **Delete all** buttons or from the context menu.</span></span> 

## <span data-ttu-id="c21dc-208">详细信息</span><span class="sxs-lookup"><span data-stu-id="c21dc-208">Details</span></span>

<span data-ttu-id="c21dc-209">"*详细信息*"窗格包括[**"Callstack"**](#call-stack)[**选项卡、"断点**](#breakpoints)"和[**"DOM 断点"**](#dom-breakpoints)选项卡。</span><span class="sxs-lookup"><span data-stu-id="c21dc-209">The *Details* pane includes the [**Callstack**](#call-stack), [**Breakpoints**](#breakpoints) and [**DOM breakpoints**](#dom-breakpoints) tabs.</span></span>

### <span data-ttu-id="c21dc-210">调用堆栈</span><span class="sxs-lookup"><span data-stu-id="c21dc-210">Call stack</span></span>

<span data-ttu-id="c21dc-211">" **调用堆栈** "选项卡显示导致当前执行点的函数链。</span><span class="sxs-lookup"><span data-stu-id="c21dc-211">The **Call stack** tab shows the chain of functions that led to the current point of execution.</span></span> <span data-ttu-id="c21dc-212">当前函数显示在顶部，调用函数以相反顺序显示在它下方。</span><span class="sxs-lookup"><span data-stu-id="c21dc-212">The current function appears at the top, and the calling functions appear below it in reverse order.</span></span>

![调用堆栈窗格](./media/debugger_callstack.png)

<span data-ttu-id="c21dc-214">" **显示/隐藏库框架** `Ctrl+Shift+J` " () 切换调用堆栈 [中的](#3-code-scoping) 库代码输出。</span><span class="sxs-lookup"><span data-stu-id="c21dc-214">The **Show/Hide library frames** button (`Ctrl+Shift+J`) toggles the output of [library code](#3-code-scoping) from the call stack.</span></span> <span data-ttu-id="c21dc-215">使用"库**代码**" () 从右键单击的"上下文"菜单中将 (或取消标记) 框架的源作为 `Ctrl+L` 库代码。 </span><span class="sxs-lookup"><span data-stu-id="c21dc-215">Use the **Library code** option (`Ctrl+L`) from the right-click *Context menu* to mark (or unmark) the source of the selected frame as library code.</span></span> 

<span data-ttu-id="c21dc-216">" **显示/隐藏异步帧** "按钮切换异步函数调用的根目录的显示。</span><span class="sxs-lookup"><span data-stu-id="c21dc-216">The **Show/Hide async frames** button toggles the display of roots for asynchronous function calls.</span></span>

### <span data-ttu-id="c21dc-217">断点</span><span class="sxs-lookup"><span data-stu-id="c21dc-217">Breakpoints</span></span>

<span data-ttu-id="c21dc-218">从 **断点** 选项卡中，可以管理断点和事件跟踪点，包括设置条件、禁用和删除它们。</span><span class="sxs-lookup"><span data-stu-id="c21dc-218">From the **Breakpoints** tab, you can manage you breakpoints and event tracepoints, including setting conditions, disabling and deleting them.</span></span>

![断点选项卡](./media/debugger_breakpoints.png)

<span data-ttu-id="c21dc-220">下面汇总了可用于调试的不同类型的断点。</span><span class="sxs-lookup"><span data-stu-id="c21dc-220">Here's a summary of the different types of breakpoints you can use for debugging.</span></span>

<span data-ttu-id="c21dc-221">断点类型</span><span class="sxs-lookup"><span data-stu-id="c21dc-221">Breakpoint type</span></span> | <span data-ttu-id="c21dc-222">描述</span><span class="sxs-lookup"><span data-stu-id="c21dc-222">Description</span></span> | <span data-ttu-id="c21dc-223">如何设置</span><span class="sxs-lookup"><span data-stu-id="c21dc-223">How to set it</span></span>
:------------ | :------------ | :--------
**<span data-ttu-id="c21dc-224">断点</span><span class="sxs-lookup"><span data-stu-id="c21dc-224">Breakpoint</span></span>** | <span data-ttu-id="c21dc-225">在执行指定的代码行之前，中断调试程序。</span><span class="sxs-lookup"><span data-stu-id="c21dc-225">Breaks into the debugger just before the specified line of code is executed.</span></span> <span data-ttu-id="c21dc-226">如果每行有一个语句，则最易于设置常规断点。</span><span class="sxs-lookup"><span data-stu-id="c21dc-226">Regular breakpoints are easiest to set if you have one statement per line.</span></span> | <span data-ttu-id="c21dc-227">在 ["调试"](#debug-window)窗口中，单击代码中任何行号旁边的左边距。</span><span class="sxs-lookup"><span data-stu-id="c21dc-227">From the [Debug window](#debug-window), click in the left margin next to any line number in the code.</span></span> <span data-ttu-id="c21dc-228">将出现一个红点，并设置断点。</span><span class="sxs-lookup"><span data-stu-id="c21dc-228">A red dot appears and the breakpoint is set.</span></span> <span data-ttu-id="c21dc-229">可以通过单击其蓝色文本跳转到任何断点的源。</span><span class="sxs-lookup"><span data-stu-id="c21dc-229">You can jump into the source of any breakpoint by clicking on its blue text.</span></span>
**<span data-ttu-id="c21dc-230">条件断点</span><span class="sxs-lookup"><span data-stu-id="c21dc-230">Conditional breakpoint</span></span>** | <span data-ttu-id="c21dc-231">如果指定条件计算结果为 *true，* 则中断。</span><span class="sxs-lookup"><span data-stu-id="c21dc-231">Breaks if the specified condition evaluates to *true*.</span></span> <span data-ttu-id="c21dc-232">这实质上 `if(condition)`  是一个中断调试程序。</span><span class="sxs-lookup"><span data-stu-id="c21dc-232">This is essentially an `if(condition)`  for breaking into the debugger.</span></span>  | <span data-ttu-id="c21dc-233">从断[点选项卡中](#breakpoints)，将鼠标悬停在现有断点上，然后单击"铅笔"按钮 (向此断点 \*) \*添加条件，右键单击现有断点，然后从上下文菜单中选择"条件 **..."。**</span><span class="sxs-lookup"><span data-stu-id="c21dc-233">From the [Breakpoints](#breakpoints) tab, hover over an existing breakpoint and click the "pencil" button (*Add a condition to this breakpoint*), right-click an existing breakpoint and select **Condition...** from the context menu.</span></span> <span data-ttu-id="c21dc-234">指定要计算在断点位置的"if"条件。</span><span class="sxs-lookup"><span data-stu-id="c21dc-234">Specify the "if" condition to be evaluated at the breakpoint location.</span></span> 
<span data-ttu-id="c21dc-235">**XMLHttpRequest 断点 (/** 可选条件) </span><span class="sxs-lookup"><span data-stu-id="c21dc-235">**XMLHttpRequest breakpoint** (w/optional condition)</span></span> | <span data-ttu-id="c21dc-236">只要满足 XHR 请求 (XMLHttpRequest) 就会中断。</span><span class="sxs-lookup"><span data-stu-id="c21dc-236">Breaks whenever a XMLHttpRequest (XHR) request has been fulfilled.</span></span> <span data-ttu-id="c21dc-237">可以从监视窗格中检查 XHR `response` 对象[](#watches)。</span><span class="sxs-lookup"><span data-stu-id="c21dc-237">You can inspect the XHR `response` object from the [**Watches**](#watches) pane.</span></span> | <span data-ttu-id="c21dc-238">在 [断点](#breakpoints) 选项卡上，单击 *XMLHttpRequest* 断点按钮 (带向上/向下箭头的) 。</span><span class="sxs-lookup"><span data-stu-id="c21dc-238">From the [Breakpoints](#breakpoints) tab, click the *XMLHttpRequest breakpoint* button (circle with up/down arrows).</span></span> <span data-ttu-id="c21dc-239">你可以将其转换为条件 *断点* ，如上所述。</span><span class="sxs-lookup"><span data-stu-id="c21dc-239">You can turn it into a *Conditional breakpoint* as described above.</span></span>
**<span data-ttu-id="c21dc-240">事件跟踪点</span><span class="sxs-lookup"><span data-stu-id="c21dc-240">Event tracepoint</span></span>** | <span data-ttu-id="c21dc-241">使用 [`console.log()`](./console/console-api.md#logging-custom-messages) 指定字符串调用以响应特定事件。</span><span class="sxs-lookup"><span data-stu-id="c21dc-241">Calls [`console.log()`](./console/console-api.md#logging-custom-messages) with a specified string in response to a specific event.</span></span> <span data-ttu-id="c21dc-242">将其用于不想直接保存在事件处理程序代码中的临时控制台日志记录语句。</span><span class="sxs-lookup"><span data-stu-id="c21dc-242">Use this for temporary console logging statements that you don't want to save directly in your event handler code.</span></span> | <span data-ttu-id="c21dc-243">在断 [点](#breakpoints) 选项卡上，单击事件 *跟踪点* 按钮 (带闪电形的菱形) 。</span><span class="sxs-lookup"><span data-stu-id="c21dc-243">From the [Breakpoints](#breakpoints) tab, click the *Event tracepoint* button (diamond with lightning bolt).</span></span> <span data-ttu-id="c21dc-244">选择 **触发器** 的事件类型和 **用于日志记录的 Trace** 语句。</span><span class="sxs-lookup"><span data-stu-id="c21dc-244">Select an **Event** type for the trigger and a **Trace** statement for logging.</span></span>
<span data-ttu-id="c21dc-245">**事件断** 点 (/可选条件) </span><span class="sxs-lookup"><span data-stu-id="c21dc-245">**Event breakpoint** (w/optional condition)</span></span> | <span data-ttu-id="c21dc-246">每当触发指定事件时中断。</span><span class="sxs-lookup"><span data-stu-id="c21dc-246">Breaks whenever a specified event is fired.</span></span> | <span data-ttu-id="c21dc-247">在"[断点](#breakpoints)"选项卡上，单击"事件断点"按钮 (带闪电状) 。</span><span class="sxs-lookup"><span data-stu-id="c21dc-247">From the [Breakpoints](#breakpoints) tab, click the *Event breakpoint* button (circle with lightning bolt).</span></span> <span data-ttu-id="c21dc-248">选择 **触发器** 的事件类型，也可以选择指定 **Condition** 语句。</span><span class="sxs-lookup"><span data-stu-id="c21dc-248">Select an **Event** type for the trigger and optionally, specify a **Condition** statement.</span></span> 
**<span data-ttu-id="c21dc-249">DOM 断点</span><span class="sxs-lookup"><span data-stu-id="c21dc-249">DOM breakpoint</span></span>** | <span data-ttu-id="c21dc-250">每当页面上的指定元素被更改时（例如，修改其子树、更改其属性或从 DOM 分离时）就会中断。</span><span class="sxs-lookup"><span data-stu-id="c21dc-250">Breaks whenever a specified element on the page is mutated, such as when its subtree is modified, its attributes change, or when it is detached from the DOM.</span></span> | <span data-ttu-id="c21dc-251">从" [元素](./elements/dom-breakpoints.md) "选项卡中，右键单击源元素，然后从 *DOM 断点选项* 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="c21dc-251">From the [Elements](./elements/dom-breakpoints.md) tab, right-click on a source element and select from the *DOM Breakpoints* options.</span></span> <span data-ttu-id="c21dc-252">使用调试器面板或元素面板中的[**DOM**](#dom-breakpoints)断点 选项卡管理断点。 </span><span class="sxs-lookup"><span data-stu-id="c21dc-252">Use the [**DOM breakpoints**](#dom-breakpoints) tab in either the *Debugger* or *Elements* panels to manage your breakpoints.</span></span> 

<span data-ttu-id="c21dc-253">当条件断点和跟踪点进入调试程序时，它们有权访问当前范围内的所有本地和全局变量。</span><span class="sxs-lookup"><span data-stu-id="c21dc-253">Conditional breakpoints and tracepoints have access to all the local and global variables currently in scope when they break into the debugger.</span></span>

### <span data-ttu-id="c21dc-254">DOM 断点</span><span class="sxs-lookup"><span data-stu-id="c21dc-254">DOM breakpoints</span></span>

<span data-ttu-id="c21dc-255">从 DOM 断点选项卡管理 **DOM** 分解断点，包括禁用、删除和重新绑定它们。</span><span class="sxs-lookup"><span data-stu-id="c21dc-255">Manage your DOM mutation breakpoints from the **DOM breakpoints** tab, including disabling, deleting and rebinding them.</span></span>  <span data-ttu-id="c21dc-256">[可以从"元素](./elements/dom-breakpoints.md) "面板中的 *HTML 树视图* 设置 DOM **断点** 。</span><span class="sxs-lookup"><span data-stu-id="c21dc-256">[DOM breakpoints can be set](./elements/dom-breakpoints.md) from the *HTML tree view* in the **Elements** panel.</span></span>

![DOM 断点选项卡](./media/debugger_dom_breakpoints.png)

<span data-ttu-id="c21dc-258">调试 *器中的 DOM* 断点 **选项卡为"** 元素"面板上的 *DOM*断点 \* 选项卡 **提供等效** 功能。</span><span class="sxs-lookup"><span data-stu-id="c21dc-258">The *DOM breakpoints* tab in the **Debugger** provides equivalent functionality to the *DOM breakpoints*\* tab on the **Elements** panel.</span></span>

<span data-ttu-id="c21dc-259">下面详细了解不同类型的 [DOM 断点](./elements/dom-breakpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="c21dc-259">Here's more on the different types of [DOM breakpoints](./elements/dom-breakpoints.md).</span></span>

## <span data-ttu-id="c21dc-260">快捷方式</span><span class="sxs-lookup"><span data-stu-id="c21dc-260">Shortcuts</span></span>

### <span data-ttu-id="c21dc-261">工具栏快捷方式</span><span class="sxs-lookup"><span data-stu-id="c21dc-261">Toolbar shortcuts</span></span>

<span data-ttu-id="c21dc-262">操作</span><span class="sxs-lookup"><span data-stu-id="c21dc-262">Action</span></span> | <span data-ttu-id="c21dc-263">快捷方式</span><span class="sxs-lookup"><span data-stu-id="c21dc-263">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="c21dc-264">查找</span><span class="sxs-lookup"><span data-stu-id="c21dc-264">Find</span></span> | `Ctrl` + `F`
<span data-ttu-id="c21dc-265">继续 (断点) </span><span class="sxs-lookup"><span data-stu-id="c21dc-265">Continue (from breakpoint)</span></span> | `F5` <span data-ttu-id="c21dc-266">或者</span><span class="sxs-lookup"><span data-stu-id="c21dc-266">or</span></span> `F8`
<span data-ttu-id="c21dc-267">快速继续</span><span class="sxs-lookup"><span data-stu-id="c21dc-267">Fast continue</span></span> | <span data-ttu-id="c21dc-268">保留 `F5` 或</span><span class="sxs-lookup"><span data-stu-id="c21dc-268">Hold `F5` or</span></span> `F8`
<span data-ttu-id="c21dc-269">继续并刷新</span><span class="sxs-lookup"><span data-stu-id="c21dc-269">Continue and refresh</span></span> | `Ctrl` + `Shift` + `F5`
<span data-ttu-id="c21dc-270">中断</span><span class="sxs-lookup"><span data-stu-id="c21dc-270">Break</span></span> | `Ctrl` + `Shift` + `B`
<span data-ttu-id="c21dc-271">进入</span><span class="sxs-lookup"><span data-stu-id="c21dc-271">Step into</span></span> | `F11`
<span data-ttu-id="c21dc-272">逐步执行</span><span class="sxs-lookup"><span data-stu-id="c21dc-272">Step over</span></span> | `F10`
<span data-ttu-id="c21dc-273">退出</span><span class="sxs-lookup"><span data-stu-id="c21dc-273">Step out</span></span> | `Shift` + `F11`
<span data-ttu-id="c21dc-274">中断新工作线程</span><span class="sxs-lookup"><span data-stu-id="c21dc-274">Break on new worker</span></span> | `Ctrl` + `Shift` + `W`
<span data-ttu-id="c21dc-275">打开菜单 (更改异常) </span><span class="sxs-lookup"><span data-stu-id="c21dc-275">Change exception behavior (opens menu)</span></span> | `Ctrl` + `Shift` + `E`
<span data-ttu-id="c21dc-276">仅调试我的代码</span><span class="sxs-lookup"><span data-stu-id="c21dc-276">Debug just my code</span></span> | `Ctrl` + `J`

### <span data-ttu-id="c21dc-277">资源选取器快捷方式</span><span class="sxs-lookup"><span data-stu-id="c21dc-277">Resource picker shortcuts</span></span>

<span data-ttu-id="c21dc-278">操作</span><span class="sxs-lookup"><span data-stu-id="c21dc-278">Action</span></span> | <span data-ttu-id="c21dc-279">快捷方式</span><span class="sxs-lookup"><span data-stu-id="c21dc-279">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="c21dc-280">标记为我的代码/库代码</span><span class="sxs-lookup"><span data-stu-id="c21dc-280">Mark as my code / library code</span></span> | `Ctrl` + `L`
<span data-ttu-id="c21dc-281">打开文件</span><span class="sxs-lookup"><span data-stu-id="c21dc-281">Open file</span></span> | `Ctrl`<span data-ttu-id="c21dc-282"> + `O`, `Ctrl` + </span><span class="sxs-lookup"><span data-stu-id="c21dc-282"> + `O`, `Ctrl` + </span></span>`P`
<span data-ttu-id="c21dc-283">搜索所有文件</span><span class="sxs-lookup"><span data-stu-id="c21dc-283">Search all files</span></span> | `Ctrl` + `Shift` + `F`

### <span data-ttu-id="c21dc-284">调试窗口快捷方式</span><span class="sxs-lookup"><span data-stu-id="c21dc-284">Debug window shortcuts</span></span>

<span data-ttu-id="c21dc-285">操作</span><span class="sxs-lookup"><span data-stu-id="c21dc-285">Action</span></span> | <span data-ttu-id="c21dc-286">快捷方式</span><span class="sxs-lookup"><span data-stu-id="c21dc-286">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="c21dc-287">删除断点</span><span class="sxs-lookup"><span data-stu-id="c21dc-287">Remove breakpoint</span></span> | `F9`
<span data-ttu-id="c21dc-288">禁用断点</span><span class="sxs-lookup"><span data-stu-id="c21dc-288">Disable breakpoint</span></span> | `Ctrl` + `F9`
<span data-ttu-id="c21dc-289">条件断点...</span><span class="sxs-lookup"><span data-stu-id="c21dc-289">Conditional breakpoint...</span></span> | `Alt` + `F9`
<span data-ttu-id="c21dc-290">复制</span><span class="sxs-lookup"><span data-stu-id="c21dc-290">Copy</span></span> | `Ctrl` + `C`
<span data-ttu-id="c21dc-291">保存</span><span class="sxs-lookup"><span data-stu-id="c21dc-291">Save</span></span> | `Ctrl` + `S`
<span data-ttu-id="c21dc-292">转到行...</span><span class="sxs-lookup"><span data-stu-id="c21dc-292">Go to line...</span></span> | `Ctrl` + `G`
<span data-ttu-id="c21dc-293">显示下一个语句</span><span class="sxs-lookup"><span data-stu-id="c21dc-293">Show next statement</span></span> | `Alt` + `Num` + `*`
<span data-ttu-id="c21dc-294">运行到光标</span><span class="sxs-lookup"><span data-stu-id="c21dc-294">Run to cursor</span></span> | `Ctrl` + `F10`
<span data-ttu-id="c21dc-295">设置下一个语句</span><span class="sxs-lookup"><span data-stu-id="c21dc-295">Set next statement</span></span> | `Ctrl` + `Shift` + `F10`
<span data-ttu-id="c21dc-296">在文件选取器中显示</span><span class="sxs-lookup"><span data-stu-id="c21dc-296">Show in file picker</span></span> | `Ctrl` + `Alt` + `P`
<span data-ttu-id="c21dc-297">转到文件中的定义</span><span class="sxs-lookup"><span data-stu-id="c21dc-297">Go to definition in file</span></span> | `Ctrl`+`D`
<span data-ttu-id="c21dc-298">在文件中查找引用</span><span class="sxs-lookup"><span data-stu-id="c21dc-298">Find references in file</span></span> | `Ctrl` + `Shift` + `D`
<span data-ttu-id="c21dc-299">非常的打印</span><span class="sxs-lookup"><span data-stu-id="c21dc-299">Pretty print</span></span> | `Ctrl` + `Shift` + `P`
<span data-ttu-id="c21dc-300">Word 自动换行</span><span class="sxs-lookup"><span data-stu-id="c21dc-300">Word wrap</span></span> | `Alt` + `W`
<span data-ttu-id="c21dc-301">标记为我的代码/库代码</span><span class="sxs-lookup"><span data-stu-id="c21dc-301">Mark as my code/library code</span></span> | `Ctrl` + `L`
<span data-ttu-id="c21dc-302">在编辑器中禁用/启用选项卡。</span><span class="sxs-lookup"><span data-stu-id="c21dc-302">Disable/Enable tabs in the editor.</span></span> <span data-ttu-id="c21dc-303">**注意** ：如果使用键盘在调试器中导航，则除非禁用 Tabbing，才能从编辑器中退出</span><span class="sxs-lookup"><span data-stu-id="c21dc-303">**Note:** if you're using the keyboard to navigate in the Debugger, you won't be able to tab out of the editor until you disable tabbing</span></span> | `Ctrl` + `M`

### <span data-ttu-id="c21dc-304">"监视"窗格的快捷方式</span><span class="sxs-lookup"><span data-stu-id="c21dc-304">Shortcuts for Watches pane</span></span>

<span data-ttu-id="c21dc-305">操作</span><span class="sxs-lookup"><span data-stu-id="c21dc-305">Action</span></span> | <span data-ttu-id="c21dc-306">快捷方式</span><span class="sxs-lookup"><span data-stu-id="c21dc-306">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="c21dc-307">添加监视</span><span class="sxs-lookup"><span data-stu-id="c21dc-307">Add watch</span></span> | `Ctrl` + `W`
<span data-ttu-id="c21dc-308">删除监视</span><span class="sxs-lookup"><span data-stu-id="c21dc-308">Delete watch</span></span> | `Ctrl` + `D`

### <span data-ttu-id="c21dc-309">"详细信息"窗格的快捷方式</span><span class="sxs-lookup"><span data-stu-id="c21dc-309">Shortcuts for Details pane</span></span>

| <span data-ttu-id="c21dc-310">操作</span><span class="sxs-lookup"><span data-stu-id="c21dc-310">Action</span></span>                             | <span data-ttu-id="c21dc-311">快捷方式</span><span class="sxs-lookup"><span data-stu-id="c21dc-311">Shortcut</span></span>                 |
|:-----------------------------------|:-------------------------|
| <span data-ttu-id="c21dc-312">显示/隐藏库代码中的帧</span><span class="sxs-lookup"><span data-stu-id="c21dc-312">Show/Hide frames from library code</span></span> | `Ctrl` + `Shift` + `J`   |
| <span data-ttu-id="c21dc-313">启用所有断点</span><span class="sxs-lookup"><span data-stu-id="c21dc-313">Enable all breakpoints</span></span>             | `Ctrl` + `Shift` + `F11` |
