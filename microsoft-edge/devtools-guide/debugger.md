---
description: Use the Debugger to step through and troubleshoot your code.
title: Debugger - DevTools (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools, debugger, debugging, breakpoints, watches, service workers, cache api, web storage, cookies
ms.custom: seodec18
ms.openlocfilehash: 722277618cd8d6d5d6dba4f2a8bd3a28b6466f77
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882917"
---
# <span data-ttu-id="dc27c-104">Debugger - DevTools (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="dc27c-104">Debugger - DevTools (EdgeHTML)</span></span>

<span data-ttu-id="dc27c-105">Use the **Debugger** to step through code, set watches and breakpoints, live edit your code and inspect your caches.</span><span class="sxs-lookup"><span data-stu-id="dc27c-105">Use the **Debugger** to step through code, set watches and breakpoints, live edit your code and inspect your caches.</span></span> <span data-ttu-id="dc27c-106">Test and troubleshoot your code by:</span><span class="sxs-lookup"><span data-stu-id="dc27c-106">Test and troubleshoot your code by:</span></span>

- <span data-ttu-id="dc27c-107">[Browsing](#resource-picker) and [searching](#file-search) code from your loaded source files</span><span class="sxs-lookup"><span data-stu-id="dc27c-107">[Browsing](#resource-picker) and [searching](#file-search) code from your loaded source files</span></span>
- <span data-ttu-id="dc27c-108">[Controlling the execution flow](#toolbar) as you step through your code</span><span class="sxs-lookup"><span data-stu-id="dc27c-108">[Controlling the execution flow](#toolbar) as you step through your code</span></span>
- <span data-ttu-id="dc27c-109">[Managing page storage resources](./storage.md#cache-manager), including the [service workers and cache](./service-workers.md), [cookies](./storage.md#cookies-list) and [web storage](./storage.md#local-and-session-storage-managers)</span><span class="sxs-lookup"><span data-stu-id="dc27c-109">[Managing page storage resources](./storage.md#cache-manager), including the [service workers and cache](./service-workers.md), [cookies](./storage.md#cookies-list) and [web storage](./storage.md#local-and-session-storage-managers)</span></span>  
- <span data-ttu-id="dc27c-110">[Setting breakpoints and live editing](#debug-window) your code as it runs</span><span class="sxs-lookup"><span data-stu-id="dc27c-110">[Setting breakpoints and live editing](#debug-window) your code as it runs</span></span>
- <span data-ttu-id="dc27c-111">[Tracking and editing local variables](#watches) as you debug</span><span class="sxs-lookup"><span data-stu-id="dc27c-111">[Tracking and editing local variables](#watches) as you debug</span></span>
- <span data-ttu-id="dc27c-112">[Hiding or showing asynchronous code and library code](#call-stack) from your callstack as needed</span><span class="sxs-lookup"><span data-stu-id="dc27c-112">[Hiding or showing asynchronous code and library code](#call-stack) from your callstack as needed</span></span>
- <span data-ttu-id="dc27c-113">[Adding specialized breakpoints](#breakpoints) for XmlHttpRequests, events and [DOM mutations](#dom-breakpoints)</span><span class="sxs-lookup"><span data-stu-id="dc27c-113">[Adding specialized breakpoints](#breakpoints) for XmlHttpRequests, events and [DOM mutations](#dom-breakpoints)</span></span>

![The Microsoft Edge DevTools Debugger](./media/debugger.png)

<span data-ttu-id="dc27c-115">There are three ways to begin a debugging session.</span><span class="sxs-lookup"><span data-stu-id="dc27c-115">There are three ways to begin a debugging session.</span></span>

1. **<span data-ttu-id="dc27c-116">Set a breakpoint.</span><span class="sxs-lookup"><span data-stu-id="dc27c-116">Set a breakpoint.</span></span>** <span data-ttu-id="dc27c-117">When the execution of your code reaches it, you'll enter the debugger and be able to step through your code.</span><span class="sxs-lookup"><span data-stu-id="dc27c-117">When the execution of your code reaches it, you'll enter the debugger and be able to step through your code.</span></span>
2. **<span data-ttu-id="dc27c-118">Initiate a break in code.</span><span class="sxs-lookup"><span data-stu-id="dc27c-118">Initiate a break in code.</span></span>** <span data-ttu-id="dc27c-119">Click the [**Break**](#toolbar) (*pause* icon) toolbar button or `Ctrl+Shift+B`.</span><span class="sxs-lookup"><span data-stu-id="dc27c-119">Click the [**Break**](#toolbar) (*pause* icon) toolbar button or `Ctrl+Shift+B`.</span></span> <span data-ttu-id="dc27c-120">The debugger will break on the next statement of execution.</span><span class="sxs-lookup"><span data-stu-id="dc27c-120">The debugger will break on the next statement of execution.</span></span>
3. **<span data-ttu-id="dc27c-121">Set exception behavior.</span><span class="sxs-lookup"><span data-stu-id="dc27c-121">Set exception behavior.</span></span>** <span data-ttu-id="dc27c-122">Use the [**Change exception behavior**](#toolbar) menu (`Ctrl+Shift+E`) to break into the debugger when your code throws an exception.</span><span class="sxs-lookup"><span data-stu-id="dc27c-122">Use the [**Change exception behavior**](#toolbar) menu (`Ctrl+Shift+E`) to break into the debugger when your code throws an exception.</span></span> <span data-ttu-id="dc27c-123">By default, the debugger is set to *Never break on exceptions*, but they are logged to the console.</span><span class="sxs-lookup"><span data-stu-id="dc27c-123">By default, the debugger is set to *Never break on exceptions*, but they are logged to the console.</span></span>

## <span data-ttu-id="dc27c-124">Resource picker</span><span class="sxs-lookup"><span data-stu-id="dc27c-124">Resource picker</span></span>

<span data-ttu-id="dc27c-125">Often the first step in debugging is to set breakpoints in the code you're looking to troubleshoot.</span><span class="sxs-lookup"><span data-stu-id="dc27c-125">Often the first step in debugging is to set breakpoints in the code you're looking to troubleshoot.</span></span> <span data-ttu-id="dc27c-126">You can find all the code files currently loaded by the page from the *Resource picker* pane, including *.html, .css* and *.js* files.</span><span class="sxs-lookup"><span data-stu-id="dc27c-126">You can find all the code files currently loaded by the page from the *Resource picker* pane, including *.html, .css* and *.js* files.</span></span>

 <span data-ttu-id="dc27c-127">Clicking on a file entry will open a tab for that file in the [Debug window](#debug-window) and bold the text of the file name to indicate this (as *devtools-guide* file name is in the illustration above).</span><span class="sxs-lookup"><span data-stu-id="dc27c-127">Clicking on a file entry will open a tab for that file in the [Debug window](#debug-window) and bold the text of the file name to indicate this (as *devtools-guide* file name is in the illustration above).</span></span> <span data-ttu-id="dc27c-128">You can then set breakpoints within that file from the [Debug window](#debug-window).</span><span class="sxs-lookup"><span data-stu-id="dc27c-128">You can then set breakpoints within that file from the [Debug window](#debug-window).</span></span>

![Debugger resource picker](./media/debugger_resource_picker.png)

<span data-ttu-id="dc27c-130">From the *Resource picker* context menu, you can also mark a file as **library code** (`Ctrl+L`), giving you the option to [skip over that code in the debugger](#debug-window) and [hide it from the **Call stack** pane](#call-stack).</span><span class="sxs-lookup"><span data-stu-id="dc27c-130">From the *Resource picker* context menu, you can also mark a file as **library code** (`Ctrl+L`), giving you the option to [skip over that code in the debugger](#debug-window) and [hide it from the **Call stack** pane](#call-stack).</span></span> <span data-ttu-id="dc27c-131">Clicking (or `Ctrl+L`) again will toggle the file back to its previous value as *my code* or *library code*.</span><span class="sxs-lookup"><span data-stu-id="dc27c-131">Clicking (or `Ctrl+L`) again will toggle the file back to its previous value as *my code* or *library code*.</span></span>

### <span data-ttu-id="dc27c-132">File search</span><span class="sxs-lookup"><span data-stu-id="dc27c-132">File search</span></span>

<span data-ttu-id="dc27c-133">Use the *Find in files* command (`Ctrl`+`Shift`+`F`) when you have a specific string of code you're trying to find in the source.</span><span class="sxs-lookup"><span data-stu-id="dc27c-133">Use the *Find in files* command (`Ctrl`+`Shift`+`F`) when you have a specific string of code you're trying to find in the source.</span></span> <span data-ttu-id="dc27c-134">The toolbar provides different search options, including regular expressions.</span><span class="sxs-lookup"><span data-stu-id="dc27c-134">The toolbar provides different search options, including regular expressions.</span></span> <span data-ttu-id="dc27c-135">Clicking on a search result will focus the *Debug window* on the specified file and line.</span><span class="sxs-lookup"><span data-stu-id="dc27c-135">Clicking on a search result will focus the *Debug window* on the specified file and line.</span></span>

![Debugger file search pane](./media/debugger_file_search.png)

## <span data-ttu-id="dc27c-137">Debug window</span><span class="sxs-lookup"><span data-stu-id="dc27c-137">Debug window</span></span>

<span data-ttu-id="dc27c-138">The *Debug window* is where you set your breakpoints, step through code, and live edit your script as you debug.</span><span class="sxs-lookup"><span data-stu-id="dc27c-138">The *Debug window* is where you set your breakpoints, step through code, and live edit your script as you debug.</span></span> <span data-ttu-id="dc27c-139">Click to the left of any script command to add (or remove) a **Breakpoint**.</span><span class="sxs-lookup"><span data-stu-id="dc27c-139">Click to the left of any script command to add (or remove) a **Breakpoint**.</span></span> <span data-ttu-id="dc27c-140">Use the right-click context menu or [**Breakpoints**](#breakpoints) pane to *Add a condition* to the breakpoint by supplying a logical expression that causes the debugger to break if it evaluates *True* at that location.</span><span class="sxs-lookup"><span data-stu-id="dc27c-140">Use the right-click context menu or [**Breakpoints**](#breakpoints) pane to *Add a condition* to the breakpoint by supplying a logical expression that causes the debugger to break if it evaluates *True* at that location.</span></span>

![Debug window commands](./media/debugger_window.png)

<span data-ttu-id="dc27c-142">Other features of the debug window include controls for:</span><span class="sxs-lookup"><span data-stu-id="dc27c-142">Other features of the debug window include controls for:</span></span>

### <span data-ttu-id="dc27c-143">1. Code editing</span><span class="sxs-lookup"><span data-stu-id="dc27c-143">1. Code editing</span></span>

<span data-ttu-id="dc27c-144">You can edit your JavaScript live during a debugging session.</span><span class="sxs-lookup"><span data-stu-id="dc27c-144">You can edit your JavaScript live during a debugging session.</span></span> <span data-ttu-id="dc27c-145">Once you make your changes, click <strong>Save</strong> (`Ctrl+S`) to test your changes next time that section of code runs.</span><span class="sxs-lookup"><span data-stu-id="dc27c-145">Once you make your changes, click <strong>Save</strong> (`Ctrl+S`) to test your changes next time that section of code runs.</span></span> <span data-ttu-id="dc27c-146">If you have unsaved code changes, an asterisk (\*) will appear before the file name in the *Debug window* tab.</span><span class="sxs-lookup"><span data-stu-id="dc27c-146">If you have unsaved code changes, an asterisk (\*) will appear before the file name in the *Debug window* tab.</span></span>

<span data-ttu-id="dc27c-147">Click the **Compare document to original** button to view the diff of what you changed.</span><span class="sxs-lookup"><span data-stu-id="dc27c-147">Click the **Compare document to original** button to view the diff of what you changed.</span></span>

![Diff view of edited code in the Debugger](./media/debugger_edit_code.png)

<span data-ttu-id="dc27c-149">Please be aware of the following constraints:</span><span class="sxs-lookup"><span data-stu-id="dc27c-149">Please be aware of the following constraints:</span></span>

- <span data-ttu-id="dc27c-150">Script editing only works in external *.js* files (and not embedded `<script>` within *.html*)</span><span class="sxs-lookup"><span data-stu-id="dc27c-150">Script editing only works in external *.js* files (and not embedded `<script>` within *.html*)</span></span>
- <span data-ttu-id="dc27c-151">Edits are saved in memory and flushed when the document is reloaded, thus you won't be able to run edits inside a `DOMContentLoaded` handler, for example</span><span class="sxs-lookup"><span data-stu-id="dc27c-151">Edits are saved in memory and flushed when the document is reloaded, thus you won't be able to run edits inside a `DOMContentLoaded` handler, for example</span></span>
- <span data-ttu-id="dc27c-152">Currently there's no way (such as a **Save As** option) to save your edits to disk from the DevTools</span><span class="sxs-lookup"><span data-stu-id="dc27c-152">Currently there's no way (such as a **Save As** option) to save your edits to disk from the DevTools</span></span>

### <span data-ttu-id="dc27c-153">2.Code formatting</span><span class="sxs-lookup"><span data-stu-id="dc27c-153">2.Code formatting</span></span>

<span data-ttu-id="dc27c-154">Use these controls to format minified code for better readability as you debug:</span><span class="sxs-lookup"><span data-stu-id="dc27c-154">Use these controls to format minified code for better readability as you debug:</span></span>

#### <span data-ttu-id="dc27c-155">Pretty print (`Ctrl+Shift+P`)</span><span class="sxs-lookup"><span data-stu-id="dc27c-155">Pretty print (`Ctrl+Shift+P`)</span></span> 
<span data-ttu-id="dc27c-156">Adds line breaks and curly brace alignment per JavaScript conventions.</span><span class="sxs-lookup"><span data-stu-id="dc27c-156">Adds line breaks and curly brace alignment per JavaScript conventions.</span></span> <span data-ttu-id="dc27c-157">Even compressed code that's been made more readable with this option may have function, selector, and variable names that are much different than in your original source code.</span><span class="sxs-lookup"><span data-stu-id="dc27c-157">Even compressed code that's been made more readable with this option may have function, selector, and variable names that are much different than in your original source code.</span></span> <span data-ttu-id="dc27c-158">In these cases, the [*Toggle source maps*](#source-maps) option might be available.</span><span class="sxs-lookup"><span data-stu-id="dc27c-158">In these cases, the [*Toggle source maps*](#source-maps) option might be available.</span></span>

#### <span data-ttu-id="dc27c-159">Word wrap (`Alt+W`)</span><span class="sxs-lookup"><span data-stu-id="dc27c-159">Word wrap (`Alt+W`)</span></span>
<span data-ttu-id="dc27c-160">Adjusts code to fit within the current margins of the debug window (eliminating the need for horizontal scrolling).</span><span class="sxs-lookup"><span data-stu-id="dc27c-160">Adjusts code to fit within the current margins of the debug window (eliminating the need for horizontal scrolling).</span></span>

### <span data-ttu-id="dc27c-161">3. Code scoping</span><span class="sxs-lookup"><span data-stu-id="dc27c-161">3. Code scoping</span></span>

<span data-ttu-id="dc27c-162">You can direct the debugger to ignore certain files with the **Mark as library code** (`Ctrl+L`) button.</span><span class="sxs-lookup"><span data-stu-id="dc27c-162">You can direct the debugger to ignore certain files with the **Mark as library code** (`Ctrl+L`) button.</span></span> <span data-ttu-id="dc27c-163">By default, the [**Debug just my code**](#toolbar) toolbar button is on, meaning that the debugger will skip over any files that you mark as *library code* and they will not appear in the debugger [call stack](#call-stack).</span><span class="sxs-lookup"><span data-stu-id="dc27c-163">By default, the [**Debug just my code**](#toolbar) toolbar button is on, meaning that the debugger will skip over any files that you mark as *library code* and they will not appear in the debugger [call stack](#call-stack).</span></span> <span data-ttu-id="dc27c-164">Depressing the button (**Mark as my code**, `Ctrl+L`) will remove this flag.</span><span class="sxs-lookup"><span data-stu-id="dc27c-164">Depressing the button (**Mark as my code**, `Ctrl+L`) will remove this flag.</span></span>

<span data-ttu-id="dc27c-165">For keeping track of libraries across debugging sessions, you can edit these files to maintain a default list or add wildcards for a domain or file type:</span><span class="sxs-lookup"><span data-stu-id="dc27c-165">For keeping track of libraries across debugging sessions, you can edit these files to maintain a default list or add wildcards for a domain or file type:</span></span>

```JavaScript
%APPDATA%\..\LocalLow\Microsoft\F12\header\MyCode.json and %APPDATA%\..\Local\Microsoft\F12\header\MyCode.json
```

#### <span data-ttu-id="dc27c-166">Source maps</span><span class="sxs-lookup"><span data-stu-id="dc27c-166">Source maps</span></span>

<span data-ttu-id="dc27c-167">You will see the **Toggle source maps** button enabled for code written in a language that compiles to JavaScript or CSS and that provides a *source map* (an intermediate file mapping to the original source).</span><span class="sxs-lookup"><span data-stu-id="dc27c-167">You will see the **Toggle source maps** button enabled for code written in a language that compiles to JavaScript or CSS and that provides a *source map* (an intermediate file mapping to the original source).</span></span> <span data-ttu-id="dc27c-168">This option directs the debugger to present the original source to use for debugging (rather than the compiled file that's *actually* running in the browser).</span><span class="sxs-lookup"><span data-stu-id="dc27c-168">This option directs the debugger to present the original source to use for debugging (rather than the compiled file that's *actually* running in the browser).</span></span>

<span data-ttu-id="dc27c-169">The DevTools will check if the compiler that generated the JavaScript file included a comment with the name of the map file.</span><span class="sxs-lookup"><span data-stu-id="dc27c-169">The DevTools will check if the compiler that generated the JavaScript file included a comment with the name of the map file.</span></span> <span data-ttu-id="dc27c-170">For example, if a compiler compressed *myfile.js* to *myfile.min.js*, it might also generate a map file, *myfile.min.js.map* and include a comment in the compressed file like this:</span><span class="sxs-lookup"><span data-stu-id="dc27c-170">For example, if a compiler compressed *myfile.js* to *myfile.min.js*, it might also generate a map file, *myfile.min.js.map* and include a comment in the compressed file like this:</span></span>

```JavaScript
//# sourceMappingURL=myfile.min.js.map
```

![Debug file tab context menu](./media/debug_file_contextmenu.png)

<span data-ttu-id="dc27c-172">If the DevTools can't find the map automatically, you can choose a source map for that file.</span><span class="sxs-lookup"><span data-stu-id="dc27c-172">If the DevTools can't find the map automatically, you can choose a source map for that file.</span></span> <span data-ttu-id="dc27c-173">Right-click the file's tab to find the **Choose source map** option.</span><span class="sxs-lookup"><span data-stu-id="dc27c-173">Right-click the file's tab to find the **Choose source map** option.</span></span> 

## <span data-ttu-id="dc27c-174">Toolbar</span><span class="sxs-lookup"><span data-stu-id="dc27c-174">Toolbar</span></span>

<span data-ttu-id="dc27c-175">Use the debugger *Toolbar* to control how you step through code, and what code to step through or ignore.</span><span class="sxs-lookup"><span data-stu-id="dc27c-175">Use the debugger *Toolbar* to control how you step through code, and what code to step through or ignore.</span></span> <span data-ttu-id="dc27c-176">From here you can also do a full text search across your code files for specific strings.</span><span class="sxs-lookup"><span data-stu-id="dc27c-176">From here you can also do a full text search across your code files for specific strings.</span></span>

![Debugger toolbar](./media/debugger_toolbar.png)

### <span data-ttu-id="dc27c-178">1. Continue (`F5`) / Break (`Ctrl+Shift+B`)</span><span class="sxs-lookup"><span data-stu-id="dc27c-178">1. Continue (`F5`) / Break (`Ctrl+Shift+B`)</span></span>
 <span data-ttu-id="dc27c-179">**Continue** (`F5`) continues code execution to the next breakpoint.</span><span class="sxs-lookup"><span data-stu-id="dc27c-179">**Continue** (`F5`) continues code execution to the next breakpoint.</span></span> <span data-ttu-id="dc27c-180">Holding down `F5` will repeatedly move past breaks until you release it.</span><span class="sxs-lookup"><span data-stu-id="dc27c-180">Holding down `F5` will repeatedly move past breaks until you release it.</span></span> 

 <span data-ttu-id="dc27c-181">**Break** (`Ctrl+Shift+B`) will break into the debugger after running the next statement.</span><span class="sxs-lookup"><span data-stu-id="dc27c-181">**Break** (`Ctrl+Shift+B`) will break into the debugger after running the next statement.</span></span>

### <span data-ttu-id="dc27c-182">2. Step functions (`F11`, `Ctrl+F10`, `Shift+F11`)</span><span class="sxs-lookup"><span data-stu-id="dc27c-182">2. Step functions (`F11`, `Ctrl+F10`, `Shift+F11`)</span></span>
 <span data-ttu-id="dc27c-183">**Step into** (`F11`) steps into the function being called.</span><span class="sxs-lookup"><span data-stu-id="dc27c-183">**Step into** (`F11`) steps into the function being called.</span></span> 

 <span data-ttu-id="dc27c-184">**Step over** (`Ctrl+F10`) steps over the function being called.</span><span class="sxs-lookup"><span data-stu-id="dc27c-184">**Step over** (`Ctrl+F10`) steps over the function being called.</span></span> 

 <span data-ttu-id="dc27c-185">**Step out** (`Shift+F11`) steps out of the current function and into the calling function.</span><span class="sxs-lookup"><span data-stu-id="dc27c-185">**Step out** (`Shift+F11`) steps out of the current function and into the calling function.</span></span> 

 <span data-ttu-id="dc27c-186">The debugger will step to the next statement if it is not at a function when these commands are used.</span><span class="sxs-lookup"><span data-stu-id="dc27c-186">The debugger will step to the next statement if it is not at a function when these commands are used.</span></span>

### <span data-ttu-id="dc27c-187">3. Break on new worker (`Ctrl+Shift+W`)</span><span class="sxs-lookup"><span data-stu-id="dc27c-187">3. Break on new worker (`Ctrl+Shift+W`)</span></span>
 <span data-ttu-id="dc27c-188">Breaks on the creation of a new [web worker](https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers).</span><span class="sxs-lookup"><span data-stu-id="dc27c-188">Breaks on the creation of a new [web worker](https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers).</span></span>

### <span data-ttu-id="dc27c-189">4. Exception control</span><span class="sxs-lookup"><span data-stu-id="dc27c-189">4. Exception control</span></span>
<span data-ttu-id="dc27c-190">**Change exception behavior** (`Ctrl+Shift+E`) opens options to change how the debugger reacts to exceptions.</span><span class="sxs-lookup"><span data-stu-id="dc27c-190">**Change exception behavior** (`Ctrl+Shift+E`) opens options to change how the debugger reacts to exceptions.</span></span> <span data-ttu-id="dc27c-191">By default exceptions are ignored by the debugger and logged to the [**Console**](./console.md).</span><span class="sxs-lookup"><span data-stu-id="dc27c-191">By default exceptions are ignored by the debugger and logged to the [**Console**](./console.md).</span></span> <span data-ttu-id="dc27c-192">You can choose to *Break on all exceptions*, or just those not being handled by `try...catch` statements in your code (*Break on unhandled exceptions*).</span><span class="sxs-lookup"><span data-stu-id="dc27c-192">You can choose to *Break on all exceptions*, or just those not being handled by `try...catch` statements in your code (*Break on unhandled exceptions*).</span></span>

### <span data-ttu-id="dc27c-193">5. View search results</span><span class="sxs-lookup"><span data-stu-id="dc27c-193">5. View search results</span></span>
<span data-ttu-id="dc27c-194">(Currently disabled.) **Show/Hide results** toggles the display of [*Find in files*](#6-find-in-files-ctrlf) search results.</span><span class="sxs-lookup"><span data-stu-id="dc27c-194">(Currently disabled.) **Show/Hide results** toggles the display of [*Find in files*](#6-find-in-files-ctrlf) search results.</span></span>

### <span data-ttu-id="dc27c-195">6. Find in files (`Ctrl+F`)</span><span class="sxs-lookup"><span data-stu-id="dc27c-195">6. Find in files (`Ctrl+F`)</span></span>
 <span data-ttu-id="dc27c-196">**Find in files** (`Ctrl+F`) runs a text search through all the loaded files within the [*Resource picker*](#resource-picker).</span><span class="sxs-lookup"><span data-stu-id="dc27c-196">**Find in files** (`Ctrl+F`) runs a text search through all the loaded files within the [*Resource picker*](#resource-picker).</span></span> <span data-ttu-id="dc27c-197">If the text is found, it opens the first file matching the search string.</span><span class="sxs-lookup"><span data-stu-id="dc27c-197">If the text is found, it opens the first file matching the search string.</span></span> <span data-ttu-id="dc27c-198">Pressing `Enter` or `F3` takes you to the next match.</span><span class="sxs-lookup"><span data-stu-id="dc27c-198">Pressing `Enter` or `F3` takes you to the next match.</span></span>

### <span data-ttu-id="dc27c-199">7. Debug just my code (`Ctrl+J`)</span><span class="sxs-lookup"><span data-stu-id="dc27c-199">7. Debug just my code (`Ctrl+J`)</span></span>
 <span data-ttu-id="dc27c-200">**Debug just my code** (`Ctrl+J`) acts as a toggle to include or exclude all the files that have been marked as [library code](#3-code-scoping) as you step through the debugger.</span><span class="sxs-lookup"><span data-stu-id="dc27c-200">**Debug just my code** (`Ctrl+J`) acts as a toggle to include or exclude all the files that have been marked as [library code](#3-code-scoping) as you step through the debugger.</span></span>

### <span data-ttu-id="dc27c-201">8. Debugger connection</span><span class="sxs-lookup"><span data-stu-id="dc27c-201">8. Debugger connection</span></span>
<span data-ttu-id="dc27c-202">**Disconnect/Connect debugger** is essentially the on/off switch for the debugger.</span><span class="sxs-lookup"><span data-stu-id="dc27c-202">**Disconnect/Connect debugger** is essentially the on/off switch for the debugger.</span></span>

## <span data-ttu-id="dc27c-203">Watches</span><span class="sxs-lookup"><span data-stu-id="dc27c-203">Watches</span></span>

<span data-ttu-id="dc27c-204">Use the **Watches** pane to browse a catalog of all objects and variables (**Locals**), both in the local and global scope, available to the statement that is the focus of the current break in the debugger.</span><span class="sxs-lookup"><span data-stu-id="dc27c-204">Use the **Watches** pane to browse a catalog of all objects and variables (**Locals**), both in the local and global scope, available to the statement that is the focus of the current break in the debugger.</span></span>

![Watches pane](./media/debugger_watches.png)

<span data-ttu-id="dc27c-206">You can track the value of specific variables as they pass in and out of scope by adding a watch (**Add watch**, `Ctrl+W`) and modify any editable values by double-clicking on it or by selecting **Edit value** from the *Context menu*.</span><span class="sxs-lookup"><span data-stu-id="dc27c-206">You can track the value of specific variables as they pass in and out of scope by adding a watch (**Add watch**, `Ctrl+W`) and modify any editable values by double-clicking on it or by selecting **Edit value** from the *Context menu*.</span></span> <span data-ttu-id="dc27c-207">Clear your watches using the **Delete** (`Ctrl+D`) / **Delete all** buttons or from the context menu.</span><span class="sxs-lookup"><span data-stu-id="dc27c-207">Clear your watches using the **Delete** (`Ctrl+D`) / **Delete all** buttons or from the context menu.</span></span> 

## <span data-ttu-id="dc27c-208">Details</span><span class="sxs-lookup"><span data-stu-id="dc27c-208">Details</span></span>

<span data-ttu-id="dc27c-209">The *Details* pane includes the [**Callstack**](#call-stack), [**Breakpoints**](#breakpoints) and [**DOM breakpoints**](#dom-breakpoints) tabs.</span><span class="sxs-lookup"><span data-stu-id="dc27c-209">The *Details* pane includes the [**Callstack**](#call-stack), [**Breakpoints**](#breakpoints) and [**DOM breakpoints**](#dom-breakpoints) tabs.</span></span>

### <span data-ttu-id="dc27c-210">Call stack</span><span class="sxs-lookup"><span data-stu-id="dc27c-210">Call stack</span></span>

<span data-ttu-id="dc27c-211">The **Call stack** tab shows the chain of functions that led to the current point of execution.</span><span class="sxs-lookup"><span data-stu-id="dc27c-211">The **Call stack** tab shows the chain of functions that led to the current point of execution.</span></span> <span data-ttu-id="dc27c-212">The current function appears at the top, and the calling functions appear below it in reverse order.</span><span class="sxs-lookup"><span data-stu-id="dc27c-212">The current function appears at the top, and the calling functions appear below it in reverse order.</span></span>

![Call stack pane](./media/debugger_callstack.png)

<span data-ttu-id="dc27c-214">The **Show/Hide library frames** button (`Ctrl+Shift+J`) toggles the output of [library code](#3-code-scoping) from the call stack.</span><span class="sxs-lookup"><span data-stu-id="dc27c-214">The **Show/Hide library frames** button (`Ctrl+Shift+J`) toggles the output of [library code](#3-code-scoping) from the call stack.</span></span> <span data-ttu-id="dc27c-215">Use the **Library code** option (`Ctrl+L`) from the right-click *Context menu* to mark (or unmark) the source of the selected frame as library code.</span><span class="sxs-lookup"><span data-stu-id="dc27c-215">Use the **Library code** option (`Ctrl+L`) from the right-click *Context menu* to mark (or unmark) the source of the selected frame as library code.</span></span> 

<span data-ttu-id="dc27c-216">The **Show/Hide async frames** button toggles the display of roots for asynchronous function calls.</span><span class="sxs-lookup"><span data-stu-id="dc27c-216">The **Show/Hide async frames** button toggles the display of roots for asynchronous function calls.</span></span>

### <span data-ttu-id="dc27c-217">Breakpoints</span><span class="sxs-lookup"><span data-stu-id="dc27c-217">Breakpoints</span></span>

<span data-ttu-id="dc27c-218">From the **Breakpoints** tab, you can manage you breakpoints and event tracepoints, including setting conditions, disabling and deleting them.</span><span class="sxs-lookup"><span data-stu-id="dc27c-218">From the **Breakpoints** tab, you can manage you breakpoints and event tracepoints, including setting conditions, disabling and deleting them.</span></span>

![Breakpoints tab](./media/debugger_breakpoints.png)

<span data-ttu-id="dc27c-220">Here's a summary of the different types of breakpoints you can use for debugging.</span><span class="sxs-lookup"><span data-stu-id="dc27c-220">Here's a summary of the different types of breakpoints you can use for debugging.</span></span>

<span data-ttu-id="dc27c-221">Breakpoint type</span><span class="sxs-lookup"><span data-stu-id="dc27c-221">Breakpoint type</span></span> | <span data-ttu-id="dc27c-222">Description</span><span class="sxs-lookup"><span data-stu-id="dc27c-222">Description</span></span> | <span data-ttu-id="dc27c-223">How to set it</span><span class="sxs-lookup"><span data-stu-id="dc27c-223">How to set it</span></span>
:------------ | :------------ | :--------
**<span data-ttu-id="dc27c-224">Breakpoint</span><span class="sxs-lookup"><span data-stu-id="dc27c-224">Breakpoint</span></span>** | <span data-ttu-id="dc27c-225">Breaks into the debugger just before the specified line of code is executed.</span><span class="sxs-lookup"><span data-stu-id="dc27c-225">Breaks into the debugger just before the specified line of code is executed.</span></span> <span data-ttu-id="dc27c-226">Regular breakpoints are easiest to set if you have one statement per line.</span><span class="sxs-lookup"><span data-stu-id="dc27c-226">Regular breakpoints are easiest to set if you have one statement per line.</span></span> | <span data-ttu-id="dc27c-227">From the [Debug window](#debug-window), click in the left margin next to any line number in the code.</span><span class="sxs-lookup"><span data-stu-id="dc27c-227">From the [Debug window](#debug-window), click in the left margin next to any line number in the code.</span></span> <span data-ttu-id="dc27c-228">A red dot appears and the breakpoint is set.</span><span class="sxs-lookup"><span data-stu-id="dc27c-228">A red dot appears and the breakpoint is set.</span></span> <span data-ttu-id="dc27c-229">You can jump into the source of any breakpoint by clicking on its blue text.</span><span class="sxs-lookup"><span data-stu-id="dc27c-229">You can jump into the source of any breakpoint by clicking on its blue text.</span></span>
**<span data-ttu-id="dc27c-230">Conditional breakpoint</span><span class="sxs-lookup"><span data-stu-id="dc27c-230">Conditional breakpoint</span></span>** | <span data-ttu-id="dc27c-231">Breaks if the specified condition evaluates to *true*.</span><span class="sxs-lookup"><span data-stu-id="dc27c-231">Breaks if the specified condition evaluates to *true*.</span></span> <span data-ttu-id="dc27c-232">This is essentially an `if(condition)`  for breaking into the debugger.</span><span class="sxs-lookup"><span data-stu-id="dc27c-232">This is essentially an `if(condition)`  for breaking into the debugger.</span></span>  | <span data-ttu-id="dc27c-233">From the [Breakpoints](#breakpoints) tab, hover over an existing breakpoint and click the "pencil" button (*Add a condition to this breakpoint*), right-click an existing breakpoint and select **Condition...** from the context menu.</span><span class="sxs-lookup"><span data-stu-id="dc27c-233">From the [Breakpoints](#breakpoints) tab, hover over an existing breakpoint and click the "pencil" button (*Add a condition to this breakpoint*), right-click an existing breakpoint and select **Condition...** from the context menu.</span></span> <span data-ttu-id="dc27c-234">Specify the "if" condition to be evaluated at the breakpoint location.</span><span class="sxs-lookup"><span data-stu-id="dc27c-234">Specify the "if" condition to be evaluated at the breakpoint location.</span></span> 
<span data-ttu-id="dc27c-235">**XMLHttpRequest breakpoint** (w/optional condition)</span><span class="sxs-lookup"><span data-stu-id="dc27c-235">**XMLHttpRequest breakpoint** (w/optional condition)</span></span> | <span data-ttu-id="dc27c-236">Breaks whenever a XMLHttpRequest (XHR) request has been fulfilled.</span><span class="sxs-lookup"><span data-stu-id="dc27c-236">Breaks whenever a XMLHttpRequest (XHR) request has been fulfilled.</span></span> <span data-ttu-id="dc27c-237">You can inspect the XHR `response` object from the [**Watches**](#watches) pane.</span><span class="sxs-lookup"><span data-stu-id="dc27c-237">You can inspect the XHR `response` object from the [**Watches**](#watches) pane.</span></span> | <span data-ttu-id="dc27c-238">From the [Breakpoints](#breakpoints) tab, click the *XMLHttpRequest breakpoint* button (circle with up/down arrows).</span><span class="sxs-lookup"><span data-stu-id="dc27c-238">From the [Breakpoints](#breakpoints) tab, click the *XMLHttpRequest breakpoint* button (circle with up/down arrows).</span></span> <span data-ttu-id="dc27c-239">You can turn it into a *Conditional breakpoint* as described above.</span><span class="sxs-lookup"><span data-stu-id="dc27c-239">You can turn it into a *Conditional breakpoint* as described above.</span></span>
**<span data-ttu-id="dc27c-240">Event tracepoint</span><span class="sxs-lookup"><span data-stu-id="dc27c-240">Event tracepoint</span></span>** | <span data-ttu-id="dc27c-241">Calls [`console.log()`](./console/console-api.md#logging-custom-messages) with a specified string in response to a specific event.</span><span class="sxs-lookup"><span data-stu-id="dc27c-241">Calls [`console.log()`](./console/console-api.md#logging-custom-messages) with a specified string in response to a specific event.</span></span> <span data-ttu-id="dc27c-242">Use this for temporary console logging statements that you don't want to save directly in your event handler code.</span><span class="sxs-lookup"><span data-stu-id="dc27c-242">Use this for temporary console logging statements that you don't want to save directly in your event handler code.</span></span> | <span data-ttu-id="dc27c-243">From the [Breakpoints](#breakpoints) tab, click the *Event tracepoint* button (diamond with lightning bolt).</span><span class="sxs-lookup"><span data-stu-id="dc27c-243">From the [Breakpoints](#breakpoints) tab, click the *Event tracepoint* button (diamond with lightning bolt).</span></span> <span data-ttu-id="dc27c-244">Select an **Event** type for the trigger and a **Trace** statement for logging.</span><span class="sxs-lookup"><span data-stu-id="dc27c-244">Select an **Event** type for the trigger and a **Trace** statement for logging.</span></span>
<span data-ttu-id="dc27c-245">**Event breakpoint** (w/optional condition)</span><span class="sxs-lookup"><span data-stu-id="dc27c-245">**Event breakpoint** (w/optional condition)</span></span> | <span data-ttu-id="dc27c-246">Breaks whenever a specified event is fired.</span><span class="sxs-lookup"><span data-stu-id="dc27c-246">Breaks whenever a specified event is fired.</span></span> | <span data-ttu-id="dc27c-247">From the [Breakpoints](#breakpoints) tab, click the *Event breakpoint* button (circle with lightning bolt).</span><span class="sxs-lookup"><span data-stu-id="dc27c-247">From the [Breakpoints](#breakpoints) tab, click the *Event breakpoint* button (circle with lightning bolt).</span></span> <span data-ttu-id="dc27c-248">Select an **Event** type for the trigger and optionally, specify a **Condition** statement.</span><span class="sxs-lookup"><span data-stu-id="dc27c-248">Select an **Event** type for the trigger and optionally, specify a **Condition** statement.</span></span> 
**<span data-ttu-id="dc27c-249">DOM breakpoint</span><span class="sxs-lookup"><span data-stu-id="dc27c-249">DOM breakpoint</span></span>** | <span data-ttu-id="dc27c-250">Breaks whenever a specified element on the page is mutated, such as when its subtree is modified, its attributes change, or when it is detached from the DOM.</span><span class="sxs-lookup"><span data-stu-id="dc27c-250">Breaks whenever a specified element on the page is mutated, such as when its subtree is modified, its attributes change, or when it is detached from the DOM.</span></span> | <span data-ttu-id="dc27c-251">From the [Elements](./elements/dom-breakpoints.md) tab, right-click on a source element and select from the *DOM Breakpoints* options.</span><span class="sxs-lookup"><span data-stu-id="dc27c-251">From the [Elements](./elements/dom-breakpoints.md) tab, right-click on a source element and select from the *DOM Breakpoints* options.</span></span> <span data-ttu-id="dc27c-252">Use the [**DOM breakpoints**](#dom-breakpoints) tab in either the *Debugger* or *Elements* panels to manage your breakpoints.</span><span class="sxs-lookup"><span data-stu-id="dc27c-252">Use the [**DOM breakpoints**](#dom-breakpoints) tab in either the *Debugger* or *Elements* panels to manage your breakpoints.</span></span> 

<span data-ttu-id="dc27c-253">Conditional breakpoints and tracepoints have access to all the local and global variables currently in scope when they break into the debugger.</span><span class="sxs-lookup"><span data-stu-id="dc27c-253">Conditional breakpoints and tracepoints have access to all the local and global variables currently in scope when they break into the debugger.</span></span>

### <span data-ttu-id="dc27c-254">DOM breakpoints</span><span class="sxs-lookup"><span data-stu-id="dc27c-254">DOM breakpoints</span></span>

<span data-ttu-id="dc27c-255">Manage your DOM mutation breakpoints from the **DOM breakpoints** tab, including disabling, deleting and rebinding them.</span><span class="sxs-lookup"><span data-stu-id="dc27c-255">Manage your DOM mutation breakpoints from the **DOM breakpoints** tab, including disabling, deleting and rebinding them.</span></span>  <span data-ttu-id="dc27c-256">[DOM breakpoints can be set](./elements/dom-breakpoints.md) from the *HTML tree view* in the **Elements** panel.</span><span class="sxs-lookup"><span data-stu-id="dc27c-256">[DOM breakpoints can be set](./elements/dom-breakpoints.md) from the *HTML tree view* in the **Elements** panel.</span></span>

![DOM breakpoints tab](./media/debugger_dom_breakpoints.png)

<span data-ttu-id="dc27c-258">The *DOM breakpoints* tab in the **Debugger** provides equivalent functionality to the *DOM breakpoints*\* tab on the **Elements** panel.</span><span class="sxs-lookup"><span data-stu-id="dc27c-258">The *DOM breakpoints* tab in the **Debugger** provides equivalent functionality to the *DOM breakpoints*\* tab on the **Elements** panel.</span></span>

<span data-ttu-id="dc27c-259">Here's more on the different types of [DOM breakpoints](./elements/dom-breakpoints.md).</span><span class="sxs-lookup"><span data-stu-id="dc27c-259">Here's more on the different types of [DOM breakpoints](./elements/dom-breakpoints.md).</span></span>

## <span data-ttu-id="dc27c-260">Shortcuts</span><span class="sxs-lookup"><span data-stu-id="dc27c-260">Shortcuts</span></span>

### <span data-ttu-id="dc27c-261">Toolbar shortcuts</span><span class="sxs-lookup"><span data-stu-id="dc27c-261">Toolbar shortcuts</span></span>

<span data-ttu-id="dc27c-262">Action</span><span class="sxs-lookup"><span data-stu-id="dc27c-262">Action</span></span> | <span data-ttu-id="dc27c-263">Shortcut</span><span class="sxs-lookup"><span data-stu-id="dc27c-263">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="dc27c-264">Find</span><span class="sxs-lookup"><span data-stu-id="dc27c-264">Find</span></span> | `Ctrl` + `F`
<span data-ttu-id="dc27c-265">Continue (from breakpoint)</span><span class="sxs-lookup"><span data-stu-id="dc27c-265">Continue (from breakpoint)</span></span> | `F5` <span data-ttu-id="dc27c-266">or</span><span class="sxs-lookup"><span data-stu-id="dc27c-266">or</span></span> `F8`
<span data-ttu-id="dc27c-267">Fast continue</span><span class="sxs-lookup"><span data-stu-id="dc27c-267">Fast continue</span></span> | <span data-ttu-id="dc27c-268">Hold `F5` or</span><span class="sxs-lookup"><span data-stu-id="dc27c-268">Hold `F5` or</span></span> `F8`
<span data-ttu-id="dc27c-269">Continue and refresh</span><span class="sxs-lookup"><span data-stu-id="dc27c-269">Continue and refresh</span></span> | `Ctrl` + `Shift` + `F5`
<span data-ttu-id="dc27c-270">Break</span><span class="sxs-lookup"><span data-stu-id="dc27c-270">Break</span></span> | `Ctrl` + `Shift` + `B`
<span data-ttu-id="dc27c-271">Step into</span><span class="sxs-lookup"><span data-stu-id="dc27c-271">Step into</span></span> | `F11`
<span data-ttu-id="dc27c-272">Step over</span><span class="sxs-lookup"><span data-stu-id="dc27c-272">Step over</span></span> | `F10`
<span data-ttu-id="dc27c-273">Step out</span><span class="sxs-lookup"><span data-stu-id="dc27c-273">Step out</span></span> | `Shift` + `F11`
<span data-ttu-id="dc27c-274">Break on new worker</span><span class="sxs-lookup"><span data-stu-id="dc27c-274">Break on new worker</span></span> | `Ctrl` + `Shift` + `W`
<span data-ttu-id="dc27c-275">Change exception behavior (opens menu)</span><span class="sxs-lookup"><span data-stu-id="dc27c-275">Change exception behavior (opens menu)</span></span> | `Ctrl` + `Shift` + `E`
<span data-ttu-id="dc27c-276">Debug just my code</span><span class="sxs-lookup"><span data-stu-id="dc27c-276">Debug just my code</span></span> | `Ctrl` + `J`

### <span data-ttu-id="dc27c-277">Resource picker shortcuts</span><span class="sxs-lookup"><span data-stu-id="dc27c-277">Resource picker shortcuts</span></span>

<span data-ttu-id="dc27c-278">Action</span><span class="sxs-lookup"><span data-stu-id="dc27c-278">Action</span></span> | <span data-ttu-id="dc27c-279">Shortcut</span><span class="sxs-lookup"><span data-stu-id="dc27c-279">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="dc27c-280">Mark as my code / library code</span><span class="sxs-lookup"><span data-stu-id="dc27c-280">Mark as my code / library code</span></span> | `Ctrl` + `L`
<span data-ttu-id="dc27c-281">Open file</span><span class="sxs-lookup"><span data-stu-id="dc27c-281">Open file</span></span> | `Ctrl`<span data-ttu-id="dc27c-282"> + `O`, `Ctrl` + </span><span class="sxs-lookup"><span data-stu-id="dc27c-282"> + `O`, `Ctrl` + </span></span>`P`
<span data-ttu-id="dc27c-283">Search all files</span><span class="sxs-lookup"><span data-stu-id="dc27c-283">Search all files</span></span> | `Ctrl` + `Shift` + `F`

### <span data-ttu-id="dc27c-284">Debug window shortcuts</span><span class="sxs-lookup"><span data-stu-id="dc27c-284">Debug window shortcuts</span></span>

<span data-ttu-id="dc27c-285">Action</span><span class="sxs-lookup"><span data-stu-id="dc27c-285">Action</span></span> | <span data-ttu-id="dc27c-286">Shortcut</span><span class="sxs-lookup"><span data-stu-id="dc27c-286">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="dc27c-287">Remove breakpoint</span><span class="sxs-lookup"><span data-stu-id="dc27c-287">Remove breakpoint</span></span> | `F9`
<span data-ttu-id="dc27c-288">Disable breakpoint</span><span class="sxs-lookup"><span data-stu-id="dc27c-288">Disable breakpoint</span></span> | `Ctrl` + `F9`
<span data-ttu-id="dc27c-289">Conditional breakpoint...</span><span class="sxs-lookup"><span data-stu-id="dc27c-289">Conditional breakpoint...</span></span> | `Alt` + `F9`
<span data-ttu-id="dc27c-290">Copy</span><span class="sxs-lookup"><span data-stu-id="dc27c-290">Copy</span></span> | `Ctrl` + `C`
<span data-ttu-id="dc27c-291">Save</span><span class="sxs-lookup"><span data-stu-id="dc27c-291">Save</span></span> | `Ctrl` + `S`
<span data-ttu-id="dc27c-292">Go to line...</span><span class="sxs-lookup"><span data-stu-id="dc27c-292">Go to line...</span></span> | `Ctrl` + `G`
<span data-ttu-id="dc27c-293">Show next statement</span><span class="sxs-lookup"><span data-stu-id="dc27c-293">Show next statement</span></span> | `Alt` + `Num` + `*`
<span data-ttu-id="dc27c-294">Run to cursor</span><span class="sxs-lookup"><span data-stu-id="dc27c-294">Run to cursor</span></span> | `Ctrl` + `F10`
<span data-ttu-id="dc27c-295">Set next statement</span><span class="sxs-lookup"><span data-stu-id="dc27c-295">Set next statement</span></span> | `Ctrl` + `Shift` + `F10`
<span data-ttu-id="dc27c-296">Show in file picker</span><span class="sxs-lookup"><span data-stu-id="dc27c-296">Show in file picker</span></span> | `Ctrl` + `Alt` + `P`
<span data-ttu-id="dc27c-297">Go to definition in file</span><span class="sxs-lookup"><span data-stu-id="dc27c-297">Go to definition in file</span></span> | `Ctrl`+`D`
<span data-ttu-id="dc27c-298">Find references in file</span><span class="sxs-lookup"><span data-stu-id="dc27c-298">Find references in file</span></span> | `Ctrl` + `Shift` + `D`
<span data-ttu-id="dc27c-299">Pretty print</span><span class="sxs-lookup"><span data-stu-id="dc27c-299">Pretty print</span></span> | `Ctrl` + `Shift` + `P`
<span data-ttu-id="dc27c-300">Word wrap</span><span class="sxs-lookup"><span data-stu-id="dc27c-300">Word wrap</span></span> | `Alt` + `W`
<span data-ttu-id="dc27c-301">Mark as my code/library code</span><span class="sxs-lookup"><span data-stu-id="dc27c-301">Mark as my code/library code</span></span> | `Ctrl` + `L`
<span data-ttu-id="dc27c-302">Disable/Enable tabs in the editor.</span><span class="sxs-lookup"><span data-stu-id="dc27c-302">Disable/Enable tabs in the editor.</span></span> <span data-ttu-id="dc27c-303">**Note:** if you're using the keyboard to navigate in the Debugger, you won't be able to tab out of the editor until you disable tabbing</span><span class="sxs-lookup"><span data-stu-id="dc27c-303">**Note:** if you're using the keyboard to navigate in the Debugger, you won't be able to tab out of the editor until you disable tabbing</span></span> | `Ctrl` + `M`

### <span data-ttu-id="dc27c-304">Shortcuts for Watches pane</span><span class="sxs-lookup"><span data-stu-id="dc27c-304">Shortcuts for Watches pane</span></span>

<span data-ttu-id="dc27c-305">Action</span><span class="sxs-lookup"><span data-stu-id="dc27c-305">Action</span></span> | <span data-ttu-id="dc27c-306">Shortcut</span><span class="sxs-lookup"><span data-stu-id="dc27c-306">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="dc27c-307">Add watch</span><span class="sxs-lookup"><span data-stu-id="dc27c-307">Add watch</span></span> | `Ctrl` + `W`
<span data-ttu-id="dc27c-308">Delete watch</span><span class="sxs-lookup"><span data-stu-id="dc27c-308">Delete watch</span></span> | `Ctrl` + `D`

### <span data-ttu-id="dc27c-309">Shortcuts for Details pane</span><span class="sxs-lookup"><span data-stu-id="dc27c-309">Shortcuts for Details pane</span></span>

| <span data-ttu-id="dc27c-310">Action</span><span class="sxs-lookup"><span data-stu-id="dc27c-310">Action</span></span>                             | <span data-ttu-id="dc27c-311">Shortcut</span><span class="sxs-lookup"><span data-stu-id="dc27c-311">Shortcut</span></span>                 |
|:-----------------------------------|:-------------------------|
| <span data-ttu-id="dc27c-312">Show/Hide frames from library code</span><span class="sxs-lookup"><span data-stu-id="dc27c-312">Show/Hide frames from library code</span></span> | `Ctrl` + `Shift` + `J`   |
| <span data-ttu-id="dc27c-313">Enable all breakpoints</span><span class="sxs-lookup"><span data-stu-id="dc27c-313">Enable all breakpoints</span></span>             | `Ctrl` + `Shift` + `F11` |
