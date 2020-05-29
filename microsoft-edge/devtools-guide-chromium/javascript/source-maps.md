---
title: 将预处理的代码映射到源代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: b48c67584b3f3253ada99e32c5dabfdccb2fa4de
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581794"
---
<!-- Copyright Meggin Kearney and Paul Bakaus

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  





# <span data-ttu-id="10ef7-103">将预处理的代码映射到源代码</span><span class="sxs-lookup"><span data-stu-id="10ef7-103">Map Preprocessed Code to Source Code</span></span>   




<span data-ttu-id="10ef7-104">即使在组合、minify 或编译之后，你的客户端代码也能保持可读和可调试。</span><span class="sxs-lookup"><span data-stu-id="10ef7-104">Keep your client-side code readable and debuggable even after you combine, minify, or compile it.</span></span>  <span data-ttu-id="10ef7-105">使用源映射将源代码映射到已编译的代码。</span><span class="sxs-lookup"><span data-stu-id="10ef7-105">Use source maps to map your source code to your compiled code.</span></span>  

### <span data-ttu-id="10ef7-106">摘要</span><span class="sxs-lookup"><span data-stu-id="10ef7-106">Summary</span></span>  

*   <span data-ttu-id="10ef7-107">使用源映射将 minified 代码映射到源代码。</span><span class="sxs-lookup"><span data-stu-id="10ef7-107">Use Source Maps to map minified code to source code.</span></span> <span data-ttu-id="10ef7-108">然后，你可以在原始源中读取和调试已编译的代码。</span><span class="sxs-lookup"><span data-stu-id="10ef7-108">You are then able to read and debug compiled code in the original source.</span></span>  
*   <span data-ttu-id="10ef7-109">仅使用能够生成源映射的 preprocessors。</span><span class="sxs-lookup"><span data-stu-id="10ef7-109">Only use preprocessors capable of producing Source Maps.</span></span>  
*   <span data-ttu-id="10ef7-110">验证你的 web 服务器是否能够提供源映射。</span><span class="sxs-lookup"><span data-stu-id="10ef7-110">Verify that your web server is able to serve Source Maps.</span></span>  

<!--todo: add link to preprocessors capable of producing Source Maps when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

## <span data-ttu-id="10ef7-111">Preprocessors 入门</span><span class="sxs-lookup"><span data-stu-id="10ef7-111">Get started with preprocessors</span></span>  

<span data-ttu-id="10ef7-112">本文介绍如何在 DevTools "源" 面板中与 JavaScript 源映射进行交互。</span><span class="sxs-lookup"><span data-stu-id="10ef7-112">This article explains how to interact with JavaScript Source Maps in the DevTools Sources Panel.</span></span>  <!--For a first overview of what preprocessors are, how each may help, and how Source Maps work; see Set Up CSS & JS Preprocessors.  -->  

<!--todo: add link to Set Up CSS & JS Preprocessors when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors#debugging-and-editing-preprocessed-content ""  -->  

## <span data-ttu-id="10ef7-113">使用支持的预处理器</span><span class="sxs-lookup"><span data-stu-id="10ef7-113">Use a supported preprocessor</span></span>  

<span data-ttu-id="10ef7-114">你需要使用能够创建源映射的 minifier。</span><span class="sxs-lookup"><span data-stu-id="10ef7-114">You need to use a minifier that is capable of creating source maps.</span></span>  <!--For the most popular options, see the preprocessor support section.  -->  <span data-ttu-id="10ef7-115">有关扩展视图，请参阅[源地图：语言、工具和其他信息][GitHubWikiSourceMapsLanguagesTools]wiki 网页。</span><span class="sxs-lookup"><span data-stu-id="10ef7-115">For an extended view, see the [Source maps: languages, tools and other info][GitHubWikiSourceMapsLanguagesTools] wiki page.</span></span>  

<!--todo: add link to see the preprocessor support section when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

<span data-ttu-id="10ef7-116">以下类型的 preprocessors 通常与源地图结合使用：</span><span class="sxs-lookup"><span data-stu-id="10ef7-116">The following types of preprocessors are commonly used in combination with Source Maps:</span></span>  

*   <span data-ttu-id="10ef7-117">Transpilers \ （[Babel][BabelJS]， [Traceur][GitHubWikiGoogleTraceurCompiler]\）</span><span class="sxs-lookup"><span data-stu-id="10ef7-117">Transpilers \([Babel][BabelJS], [Traceur][GitHubWikiGoogleTraceurCompiler]\)</span></span>  
*   <span data-ttu-id="10ef7-118">编译器 \ （[闭版编译器][GitHubGoogleClosureCompiler]、 [TypeScript][|::ref1::|Main]、 [CoffeeScript][|::ref2::|Main]、 [Dart][DartMain]\）</span><span class="sxs-lookup"><span data-stu-id="10ef7-118">Compilers \([Closure Compiler][GitHubGoogleClosureCompiler], [TypeScript][|::ref1::|Main], [CoffeeScript][|::ref2::|Main], [Dart][DartMain]\)</span></span>  
*   <span data-ttu-id="10ef7-119">Minifiers \ （[UglifyJS][GitHubMishooUglifyJS]\）</span><span class="sxs-lookup"><span data-stu-id="10ef7-119">Minifiers \([UglifyJS][GitHubMishooUglifyJS]\)</span></span>  

## <span data-ttu-id="10ef7-120">DevTools 源面板中的源映射</span><span class="sxs-lookup"><span data-stu-id="10ef7-120">Source Maps in DevTools Sources panel</span></span>  

<span data-ttu-id="10ef7-121">Preprocessors 中的源映射可导致 DevTools 加载原始文件，除了 minified。</span><span class="sxs-lookup"><span data-stu-id="10ef7-121">Source Maps from preprocessors cause DevTools to load your original files in addition to your minified ones.</span></span>  <span data-ttu-id="10ef7-122">然后使用原始设置断点并逐句通过代码。</span><span class="sxs-lookup"><span data-stu-id="10ef7-122">You then use the originals to set breakpoints and step through code.</span></span>  <span data-ttu-id="10ef7-123">同时，Microsoft Edge 实际上正在运行你的 minified 代码。</span><span class="sxs-lookup"><span data-stu-id="10ef7-123">Meanwhile, Microsoft Edge is actually running your minified code.</span></span> <span data-ttu-id="10ef7-124">这为你提供了在生产中运行开发网站的错觉。</span><span class="sxs-lookup"><span data-stu-id="10ef7-124">This gives you the illusion of running a development site in production.</span></span>  

<span data-ttu-id="10ef7-125">在 DevTools 中运行源映射时，应注意不编译 JavaScript，并且你可以查看它引用的所有单个 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="10ef7-125">When running Source Maps in DevTools, you should notice that the JavaScript is not compiled and you are able to see all the individual JavaScript files it references.</span></span>  <span data-ttu-id="10ef7-126">这是使用源映射，但在后台实际运行已编译的代码。</span><span class="sxs-lookup"><span data-stu-id="10ef7-126">This is using source mapping, but behind the scenes actually runs the compiled code.</span></span>  <span data-ttu-id="10ef7-127">任何错误、日志和断点都将映射到 dev 代码，以便进行超调试！</span><span class="sxs-lookup"><span data-stu-id="10ef7-127">Any errors, logs, and breakpoints map to the dev code for awesome debugging!</span></span>  <span data-ttu-id="10ef7-128">因此，它可以让你感觉你正在生产中运行开发人员网站。</span><span class="sxs-lookup"><span data-stu-id="10ef7-128">So in effect it gives you the illusion that you are running a dev site in production.</span></span>  

### <span data-ttu-id="10ef7-129">在 "设置" 中启用源映射</span><span class="sxs-lookup"><span data-stu-id="10ef7-129">Enable Source Maps in settings</span></span>  

<span data-ttu-id="10ef7-130">默认情况下启用源映射</span><span class="sxs-lookup"><span data-stu-id="10ef7-130">Source Maps are enabled by default</span></span> <!--\(as of Microsoft Edge 39\)--><span data-ttu-id="10ef7-131">，但如果您想要对其进行双重检查或启用，首先打开 DevTools，单击 "**自定义和控制 DevTools** `...` " 按钮，然后选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="10ef7-131">, but if you want to double-check or enable them; first open DevTools, click the **Customize and control DevTools** `...` button, and select **Settings**.</span></span>  <span data-ttu-id="10ef7-132">在 "**首选项**" 窗格的 "**源**" 下，选中 "**启用 JavaScript 源映射**"。</span><span class="sxs-lookup"><span data-stu-id="10ef7-132">On the **Preferences** pane, under **Sources**, check **Enable JavaScript Source Maps**.</span></span>  <span data-ttu-id="10ef7-133">您也可以选中 "**启用 CSS 源映射**"。</span><span class="sxs-lookup"><span data-stu-id="10ef7-133">You may also check **Enable CSS Source Maps**.</span></span>  

> ##### <span data-ttu-id="10ef7-134">图 1</span><span class="sxs-lookup"><span data-stu-id="10ef7-134">Figure 1</span></span>  
> <span data-ttu-id="10ef7-135">启用源映射</span><span class="sxs-lookup"><span data-stu-id="10ef7-135">Enable Source Maps</span></span>  
> ![启用源映射][ImageSourceMaps]  

### <span data-ttu-id="10ef7-137">通过源映射进行调试</span><span class="sxs-lookup"><span data-stu-id="10ef7-137">Debugging with Source Maps</span></span>  

<span data-ttu-id="10ef7-138">当调试你的代码和已启用源映射时，源映射显示在两个位置：</span><span class="sxs-lookup"><span data-stu-id="10ef7-138">When debugging your code and Source Maps enabled, Source Maps show in two places:</span></span>  

1.  <span data-ttu-id="10ef7-139">在控制台中 \ （指向源的链接应该是原始文件，而不是生成的文件 \）</span><span class="sxs-lookup"><span data-stu-id="10ef7-139">In the console \(the link to source should be the original file, not the generated one\)</span></span>  
1.  <span data-ttu-id="10ef7-140">逐句通过代码时 \ （调用堆栈中的链接应打开原始源文件 \）</span><span class="sxs-lookup"><span data-stu-id="10ef7-140">When stepping through code \(the links in the call stack should open the original source file\)</span></span>  

<!--todo: add link to debugging your code when section is available -->  
<!--[DebugBreakpointsStepCode]: https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/debug/breakpoints/step-code ""  -->  

## <span data-ttu-id="10ef7-141">@sourceURL 和 displayName</span><span class="sxs-lookup"><span data-stu-id="10ef7-141">@sourceURL and displayName</span></span>  

<span data-ttu-id="10ef7-142">虽然不是源地图规范的一部分，但可 `@sourceURL` 让你在使用 evals 时更轻松地进行开发。</span><span class="sxs-lookup"><span data-stu-id="10ef7-142">While not part of the Source Map spec, the `@sourceURL` allows you to make development much easier when working with evals.</span></span>  <span data-ttu-id="10ef7-143">此帮助程序看起来与属性非常相似 `//# sourceMappingURL` ，并且在源地图 V3 规范中实际提及。</span><span class="sxs-lookup"><span data-stu-id="10ef7-143">This helper looks very similar to the `//# sourceMappingURL` property and is actually mentioned in the Source Map V3 specifications.</span></span>  

<span data-ttu-id="10ef7-144">通过在你的代码中包含以下特殊注释（这是 evaled，你可以命名 evals 和内联脚本和样式，以便每个脚本和样式在你的 DevTools 中显示为更多的逻辑名称。</span><span class="sxs-lookup"><span data-stu-id="10ef7-144">By including the following special comment in your code, which is be evaled, you are able to name evals and inline scripts and styles so each appears as more logical names in your DevTools.</span></span>  

```javascript
//# sourceURL=source.coffee
```  

<span data-ttu-id="10ef7-145">导航到以下页面。</span><span class="sxs-lookup"><span data-stu-id="10ef7-145">Navigate to the following page.</span></span>  

*   [<span data-ttu-id="10ef7-146">演示</span><span class="sxs-lookup"><span data-stu-id="10ef7-146">demo</span></span>][CssNinjaDemoSourceMapping]

<span data-ttu-id="10ef7-147">请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="10ef7-147">Follow these steps.</span></span>  

1.  <span data-ttu-id="10ef7-148">打开 "DevTools"，然后转到 "**源**" 面板。</span><span class="sxs-lookup"><span data-stu-id="10ef7-148">Open the DevTools and go to the **Sources** panel.</span></span>  
1.  <span data-ttu-id="10ef7-149">在文件名中输入**_代码：_** 输入字段。</span><span class="sxs-lookup"><span data-stu-id="10ef7-149">Enter in a filename into the **_Name your code:_** input field.</span></span>  
1.  <span data-ttu-id="10ef7-150">单击 "**编译**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="10ef7-150">Click on the **compile** button.</span></span>  
1.  <span data-ttu-id="10ef7-151">将显示一个警报，其中包含 CoffeeScript 源中计算的和。</span><span class="sxs-lookup"><span data-stu-id="10ef7-151">An alert appears with the evaluated sum from the CoffeeScript source.</span></span>  

<span data-ttu-id="10ef7-152">如果展开 "**_源_**" 子面板，您现在将看到一个具有您以前输入的自定义文件名的新文件。</span><span class="sxs-lookup"><span data-stu-id="10ef7-152">If you expand the **_Sources_** sub-panel you now see a new file with the custom filename you entered earlier.</span></span>  <span data-ttu-id="10ef7-153">如果双击以查看此文件，则它包含原始源的已编译 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="10ef7-153">If you double-click to view this file it contains the compiled JavaScript for the original source.</span></span>  <span data-ttu-id="10ef7-154">但是，最后一行是 `// @sourceURL` 表示原始源文件的注释。</span><span class="sxs-lookup"><span data-stu-id="10ef7-154">On the last line, however, is a `// @sourceURL` comment indicating the original source file.</span></span>  <span data-ttu-id="10ef7-155">这可能有助于你在使用语言抽象化时进行调试。</span><span class="sxs-lookup"><span data-stu-id="10ef7-155">This may help you with debugging while working with language abstractions.</span></span>  

> ##### <span data-ttu-id="10ef7-156">图 2</span><span class="sxs-lookup"><span data-stu-id="10ef7-156">Figure 2</span></span>
> <span data-ttu-id="10ef7-157">使用 sourceURL</span><span class="sxs-lookup"><span data-stu-id="10ef7-157">Working with sourceURL</span></span>  
> ![使用 sourceURL][ImageCoffeeScript]  

<!--## Feedback   -->  



<!-- image links -->  

[ImageSourceMaps]: /microsoft-edge/devtools-guide-chromium/media/javascript-settings-preferences-sources-enable-javascript-source-maps.msft.png "图1：启用源映射"  
[ImageCoffeeScript]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-page-coffeeeeeeee.msft.png "图2：使用 sourceURL"  

<!-- links -->  

[BabelJS]: https://babeljs.io "Babel 是 JavaScript 编译器"  
[CoffeeScriptMain]: https://coffeescript.org "CoffeeScript"  
[CssNinjaDemoSourceMapping]: https://www.thecssninja.com/demo/source_mapping/compile.html "一个简单的//# sourceURL eval 命名示例"  
[DartMain]: https://www.dartlang.org "Dart 编程语言"  
[GitHubGoogleClosureCompiler]: https://github.com/google/closure-compiler "google/闭包-编译器 |GitHub"  
[GitHubMishooUglifyJS]: https://github.com/mishoo/UglifyJS "mishoo/UglifyJS |GitHub"  
[GitHubWikiSourceMapsLanguagesTools]: https://github.com/ryanseddon/source-map/wiki/Source-maps:-languages,-tools-and-other-info "源地图：语言、工具和其他信息 |GitHub wiki"  
[GitHubWikiGoogleTraceurCompiler]: https://github.com/google/traceur-compiler/wiki/Getting-Started "入门-google/traceur-编译器 |GitHub wiki"  
[TypeScriptMain]: https://www.typescriptlang.org "TypeScript"  

> [!NOTE]
> <span data-ttu-id="10ef7-170">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="10ef7-170">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="10ef7-171">原始页面可在[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps)找到，并由[Meggin Kearney][MegginKearney] \ （技术作者）和[Paul Bakaus][PaulBakaus] \ （开放 Web 开发人员、Google： TOOLS、性能、动画和 UX \）创作。</span><span class="sxs-lookup"><span data-stu-id="10ef7-171">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate, Google: Tools, Performance, Animation, and UX\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="10ef7-173">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="10ef7-173">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  
