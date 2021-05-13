---
description: 即使组合、缩小或编译客户端代码，也保持其可读和可调试。
title: 将预处理的代码映射到源代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 3240e437a917dd7074a0584b91dcc6c34576ca24
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564047"
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
# <a name="map-preprocessed-code-to-source-code"></a><span data-ttu-id="cd6f6-104">将预处理的代码映射到源代码</span><span class="sxs-lookup"><span data-stu-id="cd6f6-104">Map preprocessed code to source code</span></span>  

<span data-ttu-id="cd6f6-105">即使组合、缩小或编译客户端代码，也保持其可读和可调试。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-105">Keep your client-side code readable and debuggable even after you combine, minify, or compile it.</span></span>  <span data-ttu-id="cd6f6-106">使用源映射将源代码映射到已编译的代码。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-106">Use source maps to map your source code to your compiled code.</span></span>  

### <a name="summary"></a><span data-ttu-id="cd6f6-107">摘要</span><span class="sxs-lookup"><span data-stu-id="cd6f6-107">Summary</span></span>  

*   <span data-ttu-id="cd6f6-108">使用 source 地图将缩小代码映射到源代码。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-108">Use Source Maps to map minified code to source code.</span></span>  <span data-ttu-id="cd6f6-109">然后，您能够读取和调试原始源中的已编译代码。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-109">You are then able to read and debug compiled code in the original source.</span></span>  
*   <span data-ttu-id="cd6f6-110">只能使用能够生成源处理器的预处理器地图。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-110">Only use pre-processors capable of producing Source Maps.</span></span>  
*   <span data-ttu-id="cd6f6-111">验证 Web 服务器能否为源服务器地图。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-111">Verify that your web server is able to serve Source Maps.</span></span>  
    
<!--todo: add link to preprocessors capable of producing Source Maps when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

## <a name="get-started-with-preprocessors"></a><span data-ttu-id="cd6f6-112">预处理器入门</span><span class="sxs-lookup"><span data-stu-id="cd6f6-112">Get started with preprocessors</span></span>  

<span data-ttu-id="cd6f6-113">本文介绍如何在 DevTools 源工具地图 JavaScript Source 对象进行交互。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-113">This article explains how to interact with JavaScript Source Maps in the DevTools Sources tool.</span></span>  <!--For a first overview of what preprocessors are, how each may help, and how Source Maps work; navigate to Set Up CSS & JS Preprocessors.  -->  

<!--todo: add link to Set Up CSS & JS Preprocessors when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors#debugging-and-editing-preprocessed-content ""  -->  

## <a name="use-a-supported-preprocessor"></a><span data-ttu-id="cd6f6-114">使用受支持的预处理器</span><span class="sxs-lookup"><span data-stu-id="cd6f6-114">Use a supported preprocessor</span></span>  

<span data-ttu-id="cd6f6-115">使用能够创建源地图的微型程序。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-115">Use a minifier that is capable of creating source maps.</span></span>  <!--For the most popular options, navigate to preprocessor support section.  -->  <span data-ttu-id="cd6f6-116">对于扩展视图，导航到源 [地图：语言、工具和其他信息][GitHubWikiSourceMapsLanguagesTools] Wiki 页面。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-116">For an extended view, navigate to [Source maps: languages, tools and other info][GitHubWikiSourceMapsLanguagesTools] wiki page.</span></span>  

<!--todo: add link to display the preprocessor support section when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

<span data-ttu-id="cd6f6-117">通常将以下类型的预处理器与 Source 地图：</span><span class="sxs-lookup"><span data-stu-id="cd6f6-117">The following types of preprocessors are commonly used in combination with Source Maps:</span></span>  

*   <span data-ttu-id="cd6f6-118">Transpilers [\ (，Traceur][BabelJS] [][GitHubWikiGoogleTraceurCompiler]\) </span><span class="sxs-lookup"><span data-stu-id="cd6f6-118">Transpilers \([Babel][BabelJS], [Traceur][GitHubWikiGoogleTraceurCompiler]\)</span></span>  
*   <span data-ttu-id="cd6f6-119">Compilers \ ([Closure Compiler][GitHubGoogleClosureCompiler]， [TypeScript][|::ref1::|Main]， [CoffeeScript][|::ref2::|Main]，[则 ) ][DartMain]</span><span class="sxs-lookup"><span data-stu-id="cd6f6-119">Compilers \([Closure Compiler][GitHubGoogleClosureCompiler], [TypeScript][|::ref1::|Main], [CoffeeScript][|::ref2::|Main], [Dart][DartMain]\)</span></span>  
*   <span data-ttu-id="cd6f6-120">Minifiers \ ([UglifyJS][GitHubMishooUglifyJS]\) </span><span class="sxs-lookup"><span data-stu-id="cd6f6-120">Minifiers \([UglifyJS][GitHubMishooUglifyJS]\)</span></span>  
    
## <a name="source-maps-in-devtools-sources-tool"></a><span data-ttu-id="cd6f6-121">DevTools 地图工具中的源源</span><span class="sxs-lookup"><span data-stu-id="cd6f6-121">Source Maps in DevTools Sources tool</span></span>  

<span data-ttu-id="cd6f6-122">来自地图的源文件会导致 DevTools 加载原始文件以及缩小的文件。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-122">Source Maps from preprocessors cause DevTools to load your original files in addition to your minified ones.</span></span>  <span data-ttu-id="cd6f6-123">然后，使用原始文件设置断点并逐步执行代码。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-123">You then use the originals to set breakpoints and step through code.</span></span>  <span data-ttu-id="cd6f6-124">同时，Microsoft Edge运行缩小代码。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-124">Meanwhile, Microsoft Edge is actually running your minified code.</span></span>  <span data-ttu-id="cd6f6-125">通过运行代码，你可以错觉运行生产中的开发网站。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-125">The running of the code gives you the illusion of running a development site in production.</span></span>  

<span data-ttu-id="cd6f6-126">在 DevTools 地图源客户端时，应该会注意到 JavaScript 未编译，并且它引用的所有单个 JavaScript 文件都显示出来。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-126">When running Source Maps in DevTools, you should notice that the JavaScript is not compiled and all of the individual JavaScript files it references are displayed.</span></span>  <span data-ttu-id="cd6f6-127">DevTools 地图源映射使用的是源映射，但基础功能实际上运行已编译的代码。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-127">Source Maps in DevTools is using source mapping, but the underlying functionality actually runs the compiled code.</span></span>  <span data-ttu-id="cd6f6-128">任何错误、日志和断点都映射到开发人员代码，以便进行出色的调试。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-128">Any errors, logs, and breakpoints map to the dev code for awesome debugging.</span></span>  <span data-ttu-id="cd6f6-129">实际上，它让你产生一种在生产中运行开发网站的错觉。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-129">So in effect it gives you the illusion that you are running a dev site in production.</span></span>  

### <a name="enable-source-maps-in-settings"></a><span data-ttu-id="cd6f6-130">在设置地图源源</span><span class="sxs-lookup"><span data-stu-id="cd6f6-130">Enable Source Maps in settings</span></span>  

<span data-ttu-id="cd6f6-131">源地图默认启用</span><span class="sxs-lookup"><span data-stu-id="cd6f6-131">Source Maps are enabled by default</span></span><!-- \(as of Microsoft Edge 39\)--><span data-ttu-id="cd6f6-132">，但如果您想要仔细检查或启用它们;First open DevTools， choose **Customize and control DevTools** \ (`...` \) >**设置**.</span><span class="sxs-lookup"><span data-stu-id="cd6f6-132">, but if you want to double-check or enable them; first open DevTools, choose **Customize and control DevTools** \(`...`\) > **Settings**.</span></span>  <span data-ttu-id="cd6f6-133">在首选项**窗格的\*\*\*\*源下**，启用**JavaScript 源地图。**</span><span class="sxs-lookup"><span data-stu-id="cd6f6-133">On the **Preferences** pane, under **Sources**, turn on **Enable JavaScript Source Maps**.</span></span>  <span data-ttu-id="cd6f6-134">您还可以启用启用 CSS**源地图。**</span><span class="sxs-lookup"><span data-stu-id="cd6f6-134">You may also turn on the **Enable CSS Source Maps**.</span></span>  

:::image type="complex" source="../media/javascript-settings-preferences-sources-enable-javascript-source-maps.msft.png" alt-text="启用源地图" lightbox="../media/javascript-settings-preferences-sources-enable-javascript-source-maps.msft.png":::
   **<span data-ttu-id="cd6f6-136">启用 JavaScript 源地图</span><span class="sxs-lookup"><span data-stu-id="cd6f6-136">Enable JavaScript Source Maps</span></span>**  
:::image-end:::  

### <a name="debugging-with-source-maps"></a><span data-ttu-id="cd6f6-137">使用 Source 地图</span><span class="sxs-lookup"><span data-stu-id="cd6f6-137">Debugging with Source Maps</span></span>  

<span data-ttu-id="cd6f6-138">调试代码并启用地图时，源地图显示在两处：</span><span class="sxs-lookup"><span data-stu-id="cd6f6-138">When debugging your code and Source Maps enabled, Source Maps show in two places:</span></span>  

1.  <span data-ttu-id="cd6f6-139">在控制台 \ (源的链接应该是原始文件，而不是生成的\) </span><span class="sxs-lookup"><span data-stu-id="cd6f6-139">In the console \(the link to source should be the original file, not the generated one\)</span></span>  
1.  <span data-ttu-id="cd6f6-140">单步执行代码 \ (调用堆栈中的链接应打开原始源文件\) </span><span class="sxs-lookup"><span data-stu-id="cd6f6-140">When stepping through code \(the links in the call stack should open the original source file\)</span></span>  
    
<!--todo: add link to debugging your code when section is available -->  
<!--[DebugBreakpointsStepCode]: ../debug/breakpoints/step-code.md ""  -->  

## <a name="sourceurl-and-displayname"></a><span data-ttu-id="cd6f6-141">@sourceURL 和 displayName</span><span class="sxs-lookup"><span data-stu-id="cd6f6-141">@sourceURL and displayName</span></span>  

<span data-ttu-id="cd6f6-142">虽然 不是 Source Map 规范的一部分，但 允许您在使用 evals 时更轻松地 `@sourceURL` 进行开发。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-142">While not part of the Source Map spec, the `@sourceURL` allows you to make development much easier when working with evals.</span></span>  <span data-ttu-id="cd6f6-143">帮助程序显示类似于 `//# sourceMappingURL` 属性，并提及源地图 V3 规范。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-143">The helper is displayed similar to the `//# sourceMappingURL` property and is mentioned in the Source Map V3 specifications.</span></span>  

<span data-ttu-id="cd6f6-144">通过在你的代码中包括以下特殊注释（已对此进行评论）可以命名 evals 以及内联脚本和样式，以便每个注释在 DevTools 中显示为更符合逻辑的名称。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-144">By including the following special comment in your code, which is evaled, you are able to name evals and inline scripts and styles so each appears as more logical names in your DevTools.</span></span>  

```javascript
//# sourceURL=source.coffee
```  

<span data-ttu-id="cd6f6-145">导航到以下页面。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-145">Navigate to the following page.</span></span>  

*   [<span data-ttu-id="cd6f6-146">演示</span><span class="sxs-lookup"><span data-stu-id="cd6f6-146">demo</span></span>][CssNinjaDemoSourceMapping]

<span data-ttu-id="cd6f6-147">完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-147">Complete the following actions.</span></span>  

1.  <span data-ttu-id="cd6f6-148">打开 DevTools 并导航到 **"源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-148">Open DevTools and navigate to the **Sources** tool.</span></span>  
1.  <span data-ttu-id="cd6f6-149">在"命名代码：输入" **字段中** 输入文件名。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-149">Enter in a filename into the **Name your code:** input field.</span></span>  
1.  <span data-ttu-id="cd6f6-150">选择" **编译"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-150">Choose the **compile** button.</span></span>  
1.  <span data-ttu-id="cd6f6-151">将出现警报，显示来自 CoffeeScript 源的评估和。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-151">An alert appears, showing the evaluated sum from the CoffeeScript source.</span></span>  
    
<span data-ttu-id="cd6f6-152">如果展开" **源** "子面板，现在将显示一个包含先前输入的自定义文件名的新文件。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-152">If you expand the **Sources** sub-panel you now display a new file with the custom filename you entered earlier.</span></span>  <span data-ttu-id="cd6f6-153">如果双击查看此文件，则它包含原始源的已编译 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-153">If you double-click to view this file, it contains the compiled JavaScript for the original source.</span></span>  <span data-ttu-id="cd6f6-154">但是，最后一行是 `// @sourceURL` 指示原始源文件的注释。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-154">On the last line, however, is a `// @sourceURL` comment indicating the original source file.</span></span>  <span data-ttu-id="cd6f6-155">这有助于你在使用语言抽象时进行调试。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-155">This may help you with debugging while working with language abstractions.</span></span>  

:::image type="complex" source="../media/javascript-sources-page-coffeeeeeeee.msft.png" alt-text="使用 sourceURL" lightbox="../media/javascript-sources-page-coffeeeeeeee.msft.png":::
   <span data-ttu-id="cd6f6-157">使用</span><span class="sxs-lookup"><span data-stu-id="cd6f6-157">Work with</span></span> `sourceURL`  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="cd6f6-158">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="cd6f6-158">Getting in touch with the Microsoft Edge DevTools team</span></span>

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[BabelJS]: https://babeljs.io "一个 JavaScript 编译器"  

[CoffeeScriptMain]: https://coffeescript.org "CoffeeScript"  

[CssNinjaDemoSourceMapping]: https://www.thecssninja.com/demo/source_mapping/compile.html "//# sourceURL eval 命名的简单示例"  

[DartMain]: https://www.dartlang.org "英语（英语）"  

[GitHubGoogleClosureCompiler]: https://github.com/google/closure-compiler "google/closure-compiler |GitHub"  

[GitHubMishooUglifyJS]: https://github.com/mishoo/UglifyJS "mishoo/UglifyJS |GitHub"  

[GitHubWikiSourceMapsLanguagesTools]: https://github.com/ryanseddon/source-map/wiki/Source-maps:-languages,-tools-and-other-info "源地图：语言、工具和其他|GitHub Wiki"  

[GitHubWikiGoogleTraceurCompiler]: https://github.com/google/traceur-compiler/wiki/Getting-Started "入门 - google/traceur-compiler |GitHub Wiki"  

[TypeScriptMain]: https://www.typescriptlang.org "TypeScript"  

> [!NOTE]
> <span data-ttu-id="cd6f6-168">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-168">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="cd6f6-169">原始页面位于此处，[](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps)由[Meggin Kearney][MegginKearney] \ (Tech Writer\) 和[Paul Bakaus][PaulBakaus] \ (Open Web Developer Advocate、Google：Tools、Performance、Animation 和 UX\) 创作。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-169">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate, Google: Tools, Performance, Animation, and UX\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="cd6f6-171">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="cd6f6-171">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[MegginKearney]: https://developers.google.com/web/resources/contributors#meggin-kearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors#paul-bakaus  
