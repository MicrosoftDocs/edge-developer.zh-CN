---
description: 即使组合、缩小或编译客户端代码，也保持其可读和可调试。
title: 将预处理的代码映射到源代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: debea327be41ab8aa2da19aa8cc128a1897e51e5
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398390"
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

# <a name="map-preprocessed-code-to-source-code"></a><span data-ttu-id="9e0ea-104">将预处理的代码映射到源代码</span><span class="sxs-lookup"><span data-stu-id="9e0ea-104">Map preprocessed code to source code</span></span>  

<span data-ttu-id="9e0ea-105">即使组合、缩小或编译客户端代码，也保持其可读和可调试。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-105">Keep your client-side code readable and debuggable even after you combine, minify, or compile it.</span></span>  <span data-ttu-id="9e0ea-106">使用源映射将源代码映射到已编译的代码。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-106">Use source maps to map your source code to your compiled code.</span></span>  

### <a name="summary"></a><span data-ttu-id="9e0ea-107">摘要</span><span class="sxs-lookup"><span data-stu-id="9e0ea-107">Summary</span></span>  

*   <span data-ttu-id="9e0ea-108">使用源地图将缩小代码映射到源代码。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-108">Use Source Maps to map minified code to source code.</span></span>  <span data-ttu-id="9e0ea-109">然后，您能够在原始源中读取和调试编译的代码。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-109">You are then able to read and debug compiled code in the original source.</span></span>  
*   <span data-ttu-id="9e0ea-110">仅使用能够生成源地图的预处理器。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-110">Only use pre-processors capable of producing Source Maps.</span></span>  
*   <span data-ttu-id="9e0ea-111">验证 Web 服务器能否为源地图提供服务。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-111">Verify that your web server is able to serve Source Maps.</span></span>  
    
<!--todo: add link to preprocessors capable of producing Source Maps when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

## <a name="get-started-with-preprocessors"></a><span data-ttu-id="9e0ea-112">预处理器入门</span><span class="sxs-lookup"><span data-stu-id="9e0ea-112">Get started with preprocessors</span></span>  

<span data-ttu-id="9e0ea-113">本文介绍了如何在 DevTools 源面板中与 JavaScript 源映射进行交互。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-113">This article explains how to interact with JavaScript Source Maps in the DevTools Sources Panel.</span></span>  <!--For a first overview of what preprocessors are, how each may help, and how Source Maps work; navigate to Set Up CSS & JS Preprocessors.  -->  

<!--todo: add link to Set Up CSS & JS Preprocessors when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors#debugging-and-editing-preprocessed-content ""  -->  

## <a name="use-a-supported-preprocessor"></a><span data-ttu-id="9e0ea-114">使用受支持的预处理器</span><span class="sxs-lookup"><span data-stu-id="9e0ea-114">Use a supported preprocessor</span></span>  

<span data-ttu-id="9e0ea-115">使用能够创建源地图的微型程序。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-115">Use a minifier that is capable of creating source maps.</span></span>  <!--For the most popular options, navigate to preprocessor support section.  -->  <span data-ttu-id="9e0ea-116">对于扩展视图，导航到 ["源地图："语言、工具和其他信息][GitHubWikiSourceMapsLanguagesTools] Wiki 页面。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-116">For an extended view, navigate to [Source maps: languages, tools and other info][GitHubWikiSourceMapsLanguagesTools] wiki page.</span></span>  

<!--todo: add link to display the preprocessor support section when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

<span data-ttu-id="9e0ea-117">通常将以下类型的预处理器与源地图结合使用：</span><span class="sxs-lookup"><span data-stu-id="9e0ea-117">The following types of preprocessors are commonly used in combination with Source Maps:</span></span>  

*   <span data-ttu-id="9e0ea-118">Transpilers [\ (L][BabelJS]， [Traceur][GitHubWikiGoogleTraceurCompiler]\) </span><span class="sxs-lookup"><span data-stu-id="9e0ea-118">Transpilers \([Babel][BabelJS], [Traceur][GitHubWikiGoogleTraceurCompiler]\)</span></span>  
*   <span data-ttu-id="9e0ea-119">编译器 \ ([关闭编译器][GitHubGoogleClosureCompiler]， [TypeScript][|::ref1::|Main]， [CoffeeScript][|::ref2::|Main]， [) ][DartMain]</span><span class="sxs-lookup"><span data-stu-id="9e0ea-119">Compilers \([Closure Compiler][GitHubGoogleClosureCompiler], [TypeScript][|::ref1::|Main], [CoffeeScript][|::ref2::|Main], [Dart][DartMain]\)</span></span>  
*   <span data-ttu-id="9e0ea-120">Minifiers \ ([UglifyJS][GitHubMishooUglifyJS]\) </span><span class="sxs-lookup"><span data-stu-id="9e0ea-120">Minifiers \([UglifyJS][GitHubMishooUglifyJS]\)</span></span>  
    
## <a name="source-maps-in-devtools-sources-panel"></a><span data-ttu-id="9e0ea-121">DevTools 源面板中的源地图</span><span class="sxs-lookup"><span data-stu-id="9e0ea-121">Source Maps in DevTools Sources panel</span></span>  

<span data-ttu-id="9e0ea-122">来自预处理器的源地图会导致除缩小文件外，DevTools 还加载原始文件。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-122">Source Maps from preprocessors cause DevTools to load your original files in addition to your minified ones.</span></span>  <span data-ttu-id="9e0ea-123">然后，使用原始文件设置断点并逐步执行代码。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-123">You then use the originals to set breakpoints and step through code.</span></span>  <span data-ttu-id="9e0ea-124">同时，Microsoft Edge 实际上是在运行缩小代码。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-124">Meanwhile, Microsoft Edge is actually running your minified code.</span></span>  <span data-ttu-id="9e0ea-125">代码的运行让你产生在生产中运行开发网站的错觉。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-125">The running of the code gives you the illusion of running a development site in production.</span></span>  

<span data-ttu-id="9e0ea-126">在 DevTools 中运行源地图时，应该会注意到 JavaScript 未编译，并且会显示它引用的所有单个 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-126">When running Source Maps in DevTools, you should notice that the JavaScript is not compiled and all of the individual JavaScript files it references are displayed.</span></span>  <span data-ttu-id="9e0ea-127">DevTools 中的源地图使用的是源映射，但基础功能实际上运行已编译的代码。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-127">Source Maps in DevTools is using source mapping, but the underlying functionality actually runs the compiled code.</span></span>  <span data-ttu-id="9e0ea-128">任何错误、日志和断点都映射到开发人员代码，以便进行出色的调试。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-128">Any errors, logs, and breakpoints map to the dev code for awesome debugging.</span></span>  <span data-ttu-id="9e0ea-129">因此实际上，它让你产生一种在生产中运行开发网站的错觉。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-129">So in effect it gives you the illusion that you are running a dev site in production.</span></span>  

### <a name="enable-source-maps-in-settings"></a><span data-ttu-id="9e0ea-130">在设置中启用源地图</span><span class="sxs-lookup"><span data-stu-id="9e0ea-130">Enable Source Maps in settings</span></span>  

<span data-ttu-id="9e0ea-131">默认情况下启用源地图</span><span class="sxs-lookup"><span data-stu-id="9e0ea-131">Source Maps are enabled by default</span></span><!-- \(as of Microsoft Edge 39\)--><span data-ttu-id="9e0ea-132">，但如果您想要仔细检查或启用它们;First open DevTools， choose **Customize and control DevTools** \ (`...` \) > **Settings**.</span><span class="sxs-lookup"><span data-stu-id="9e0ea-132">, but if you want to double-check or enable them; first open DevTools, choose **Customize and control DevTools** \(`...`\) > **Settings**.</span></span>  <span data-ttu-id="9e0ea-133">在 **"首选项"** 窗格的 **"源**"下，打开 **"启用 JavaScript 源映射"。**</span><span class="sxs-lookup"><span data-stu-id="9e0ea-133">On the **Preferences** pane, under **Sources**, turn on **Enable JavaScript Source Maps**.</span></span>  <span data-ttu-id="9e0ea-134">还可以启用"启用**CSS 源映射"。**</span><span class="sxs-lookup"><span data-stu-id="9e0ea-134">You may also turn on the **Enable CSS Source Maps**.</span></span>  

:::image type="complex" source="../media/javascript-settings-preferences-sources-enable-javascript-source-maps.msft.png" alt-text="启用源地图" lightbox="../media/javascript-settings-preferences-sources-enable-javascript-source-maps.msft.png":::
   **<span data-ttu-id="9e0ea-136">启用 JavaScript 源映射</span><span class="sxs-lookup"><span data-stu-id="9e0ea-136">Enable JavaScript Source Maps</span></span>**  
:::image-end:::  

### <a name="debugging-with-source-maps"></a><span data-ttu-id="9e0ea-137">使用源地图进行调试</span><span class="sxs-lookup"><span data-stu-id="9e0ea-137">Debugging with Source Maps</span></span>  

<span data-ttu-id="9e0ea-138">当调试代码和源地图启用时，源地图会显示在两处：</span><span class="sxs-lookup"><span data-stu-id="9e0ea-138">When debugging your code and Source Maps enabled, Source Maps show in two places:</span></span>  

1.  <span data-ttu-id="9e0ea-139">在控制台 \ (指向源的链接应为原始文件，而不是生成的\) </span><span class="sxs-lookup"><span data-stu-id="9e0ea-139">In the console \(the link to source should be the original file, not the generated one\)</span></span>  
1.  <span data-ttu-id="9e0ea-140">单步执行代码 \ (调用堆栈中的链接应打开原始源文件\) </span><span class="sxs-lookup"><span data-stu-id="9e0ea-140">When stepping through code \(the links in the call stack should open the original source file\)</span></span>  
    
<!--todo: add link to debugging your code when section is available -->  
<!--[DebugBreakpointsStepCode]: ../debug/breakpoints/step-code.md ""  -->  

## <a name="sourceurl-and-displayname"></a><span data-ttu-id="9e0ea-141">@sourceURL和 displayName</span><span class="sxs-lookup"><span data-stu-id="9e0ea-141">@sourceURL and displayName</span></span>  

<span data-ttu-id="9e0ea-142">虽然不是源地图规范的一部分，但允许你在使用 `@sourceURL` evals 时更轻松地进行开发。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-142">While not part of the Source Map spec, the `@sourceURL` allows you to make development much easier when working with evals.</span></span>  <span data-ttu-id="9e0ea-143">帮助程序与属性类似， `//# sourceMappingURL` 在源映射 V3 规范中提及。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-143">The helper is displayed similar to the `//# sourceMappingURL` property and is mentioned in the Source Map V3 specifications.</span></span>  

<span data-ttu-id="9e0ea-144">通过在你的代码中添加以下特殊注释（这是一种规避操作），你可以命名 evals 和内联脚本和样式，以便每个脚本和样式在 DevTools 中显示为更多逻辑名称。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-144">By including the following special comment in your code, which is evaled, you are able to name evals and inline scripts and styles so each appears as more logical names in your DevTools.</span></span>  

```javascript
//# sourceURL=source.coffee
```  

<span data-ttu-id="9e0ea-145">导航到以下页面。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-145">Navigate to the following page.</span></span>  

*   [<span data-ttu-id="9e0ea-146">演示</span><span class="sxs-lookup"><span data-stu-id="9e0ea-146">demo</span></span>][CssNinjaDemoSourceMapping]

<span data-ttu-id="9e0ea-147">完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-147">Complete the following actions.</span></span>  

1.  <span data-ttu-id="9e0ea-148">打开 DevTools 并导航到"源 **"** 面板。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-148">Open the DevTools and navigate to the **Sources** panel.</span></span>  
1.  <span data-ttu-id="9e0ea-149">在文件名中输入代码 **名称：** 输入字段。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-149">Enter in a filename into the **Name your code:** input field.</span></span>  
1.  <span data-ttu-id="9e0ea-150">选择 **编译** 按钮。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-150">Choose the **compile** button.</span></span>  
1.  <span data-ttu-id="9e0ea-151">将出现一个警报，并显示来自 CoffeeScript 源的评估和。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-151">An alert appears with the evaluated sum from the CoffeeScript source.</span></span>  
    
<span data-ttu-id="9e0ea-152">如果展开" **源** "子面板，现在将显示具有先前输入的自定义文件名的新文件。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-152">If you expand the **Sources** sub-panel you now display a new file with the custom filename you entered earlier.</span></span>  <span data-ttu-id="9e0ea-153">如果双击以查看此文件，则它包含原始源的已编译 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-153">If you double-click to view this file, it contains the compiled JavaScript for the original source.</span></span>  <span data-ttu-id="9e0ea-154">但是，最后一行是 `// @sourceURL` 一条指示原始源文件的注释。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-154">On the last line, however, is a `// @sourceURL` comment indicating the original source file.</span></span>  <span data-ttu-id="9e0ea-155">这有助于你在使用语言抽象时进行调试。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-155">This may help you with debugging while working with language abstractions.</span></span>  

:::image type="complex" source="../media/javascript-sources-page-coffeeeeeeee.msft.png" alt-text="使用 sourceURL" lightbox="../media/javascript-sources-page-coffeeeeeeee.msft.png":::
   <span data-ttu-id="9e0ea-157">使用</span><span class="sxs-lookup"><span data-stu-id="9e0ea-157">Work with</span></span> `sourceURL`  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="9e0ea-158">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="9e0ea-158">Getting in touch with the Microsoft Edge DevTools team</span></span>

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[BabelJS]: https://babeljs.io "Compilerl 是 JavaScript 编译器"  

[CoffeeScriptMain]: https://coffeescript.org "CoffeeScript"  

[CssNinjaDemoSourceMapping]: https://www.thecssninja.com/demo/source_mapping/compile.html "//# sourceURL eval 命名的简单示例"  

[DartMain]: https://www.dartlang.org "编程语言"  

[GitHubGoogleClosureCompiler]: https://github.com/google/closure-compiler "google/closure-compiler |GitHub"  

[GitHubMishooUglifyJS]: https://github.com/mishoo/UglifyJS "mishoo/UglifyJS |GitHub"  

[GitHubWikiSourceMapsLanguagesTools]: https://github.com/ryanseddon/source-map/wiki/Source-maps:-languages,-tools-and-other-info "源地图：语言、工具和其他|GitHub Wiki"  

[GitHubWikiGoogleTraceurCompiler]: https://github.com/google/traceur-compiler/wiki/Getting-Started "入门 - google/traceur-compiler |GitHub Wiki"  

[TypeScriptMain]: https://www.typescriptlang.org "TypeScript"  

> [!NOTE]
> <span data-ttu-id="9e0ea-168">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-168">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9e0ea-169">原始页面位于此处，[](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps)由[Meggin Kearney][MegginKearney] \ (Tech Writer\) 和[Paul Bakaus][PaulBakaus] \ (Open Web Developer Advocate、Google：Tools、Performance、Animation 和 UX\) 创作。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-169">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate, Google: Tools, Performance, Animation, and UX\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="9e0ea-171">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="9e0ea-171">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  
