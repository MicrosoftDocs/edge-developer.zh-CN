---
description: Keep your client-side code readable and debuggable even after you combine, minify, or compile it.
title: Map Preprocessed Code to Source Code
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: bd04c7bae6f57d4fe3f9b293d70775aa99db3dd1
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993231"
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

# <span data-ttu-id="7229d-104">Map preprocessed code to source code</span><span class="sxs-lookup"><span data-stu-id="7229d-104">Map preprocessed code to source code</span></span>  

<span data-ttu-id="7229d-105">Keep your client-side code readable and debuggable even after you combine, minify, or compile it.</span><span class="sxs-lookup"><span data-stu-id="7229d-105">Keep your client-side code readable and debuggable even after you combine, minify, or compile it.</span></span>  <span data-ttu-id="7229d-106">Use source maps to map your source code to your compiled code.</span><span class="sxs-lookup"><span data-stu-id="7229d-106">Use source maps to map your source code to your compiled code.</span></span>  

### <span data-ttu-id="7229d-107">Summary</span><span class="sxs-lookup"><span data-stu-id="7229d-107">Summary</span></span>  

*   <span data-ttu-id="7229d-108">Use Source Maps to map minified code to source code.</span><span class="sxs-lookup"><span data-stu-id="7229d-108">Use Source Maps to map minified code to source code.</span></span> <span data-ttu-id="7229d-109">You are then able to read and debug compiled code in the original source.</span><span class="sxs-lookup"><span data-stu-id="7229d-109">You are then able to read and debug compiled code in the original source.</span></span>  
*   <span data-ttu-id="7229d-110">Only use pre-processors capable of producing Source Maps.</span><span class="sxs-lookup"><span data-stu-id="7229d-110">Only use pre-processors capable of producing Source Maps.</span></span>  
*   <span data-ttu-id="7229d-111">Verify that your web server is able to serve Source Maps.</span><span class="sxs-lookup"><span data-stu-id="7229d-111">Verify that your web server is able to serve Source Maps.</span></span>  
    
<!--todo: add link to preprocessors capable of producing Source Maps when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

## <span data-ttu-id="7229d-112">Get started with preprocessors</span><span class="sxs-lookup"><span data-stu-id="7229d-112">Get started with preprocessors</span></span>  

<span data-ttu-id="7229d-113">This article explains how to interact with JavaScript Source Maps in the DevTools Sources Panel.</span><span class="sxs-lookup"><span data-stu-id="7229d-113">This article explains how to interact with JavaScript Source Maps in the DevTools Sources Panel.</span></span>  <!--For a first overview of what preprocessors are, how each may help, and how Source Maps work; see Set Up CSS & JS Preprocessors.  -->  

<!--todo: add link to Set Up CSS & JS Preprocessors when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors#debugging-and-editing-preprocessed-content ""  -->  

## <span data-ttu-id="7229d-114">Use a supported preprocessor</span><span class="sxs-lookup"><span data-stu-id="7229d-114">Use a supported preprocessor</span></span>  

<span data-ttu-id="7229d-115">You need to use a minifier that is capable of creating source maps.</span><span class="sxs-lookup"><span data-stu-id="7229d-115">You need to use a minifier that is capable of creating source maps.</span></span>  <!--For the most popular options, see the preprocessor support section.  -->  <span data-ttu-id="7229d-116">For an extended view, see the [Source maps: languages, tools and other info][GitHubWikiSourceMapsLanguagesTools] wiki page.</span><span class="sxs-lookup"><span data-stu-id="7229d-116">For an extended view, see the [Source maps: languages, tools and other info][GitHubWikiSourceMapsLanguagesTools] wiki page.</span></span>  

<!--todo: add link to see the preprocessor support section when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

<span data-ttu-id="7229d-117">The following types of preprocessors are commonly used in combination with Source Maps:</span><span class="sxs-lookup"><span data-stu-id="7229d-117">The following types of preprocessors are commonly used in combination with Source Maps:</span></span>  

*   <span data-ttu-id="7229d-118">Transpilers \([Babel][BabelJS], [Traceur][GitHubWikiGoogleTraceurCompiler]\)</span><span class="sxs-lookup"><span data-stu-id="7229d-118">Transpilers \([Babel][BabelJS], [Traceur][GitHubWikiGoogleTraceurCompiler]\)</span></span>  
*   <span data-ttu-id="7229d-119">Compilers \([Closure Compiler][GitHubGoogleClosureCompiler], [TypeScript][|::ref1::|Main], [CoffeeScript][|::ref2::|Main], [Dart][DartMain]\)</span><span class="sxs-lookup"><span data-stu-id="7229d-119">Compilers \([Closure Compiler][GitHubGoogleClosureCompiler], [TypeScript][|::ref1::|Main], [CoffeeScript][|::ref2::|Main], [Dart][DartMain]\)</span></span>  
*   <span data-ttu-id="7229d-120">Minifiers \([UglifyJS][GitHubMishooUglifyJS]\)</span><span class="sxs-lookup"><span data-stu-id="7229d-120">Minifiers \([UglifyJS][GitHubMishooUglifyJS]\)</span></span>  
    
## <span data-ttu-id="7229d-121">Source Maps in DevTools Sources panel</span><span class="sxs-lookup"><span data-stu-id="7229d-121">Source Maps in DevTools Sources panel</span></span>  

<span data-ttu-id="7229d-122">Source Maps from preprocessors cause DevTools to load your original files in addition to your minified ones.</span><span class="sxs-lookup"><span data-stu-id="7229d-122">Source Maps from preprocessors cause DevTools to load your original files in addition to your minified ones.</span></span>  <span data-ttu-id="7229d-123">You then use the originals to set breakpoints and step through code.</span><span class="sxs-lookup"><span data-stu-id="7229d-123">You then use the originals to set breakpoints and step through code.</span></span>  <span data-ttu-id="7229d-124">Meanwhile, Microsoft Edge is actually running your minified code.</span><span class="sxs-lookup"><span data-stu-id="7229d-124">Meanwhile, Microsoft Edge is actually running your minified code.</span></span> <span data-ttu-id="7229d-125">This gives you the illusion of running a development site in production.</span><span class="sxs-lookup"><span data-stu-id="7229d-125">This gives you the illusion of running a development site in production.</span></span>  

<span data-ttu-id="7229d-126">When running Source Maps in DevTools, you should notice that the JavaScript is not compiled and you are able to see all the individual JavaScript files it references.</span><span class="sxs-lookup"><span data-stu-id="7229d-126">When running Source Maps in DevTools, you should notice that the JavaScript is not compiled and you are able to see all the individual JavaScript files it references.</span></span>  <span data-ttu-id="7229d-127">This is using source mapping, but behind the scenes actually runs the compiled code.</span><span class="sxs-lookup"><span data-stu-id="7229d-127">This is using source mapping, but behind the scenes actually runs the compiled code.</span></span>  <span data-ttu-id="7229d-128">Any errors, logs, and breakpoints map to the dev code for awesome debugging!</span><span class="sxs-lookup"><span data-stu-id="7229d-128">Any errors, logs, and breakpoints map to the dev code for awesome debugging!</span></span>  <span data-ttu-id="7229d-129">So in effect it gives you the illusion that you are running a dev site in production.</span><span class="sxs-lookup"><span data-stu-id="7229d-129">So in effect it gives you the illusion that you are running a dev site in production.</span></span>  

### <span data-ttu-id="7229d-130">Enable Source Maps in settings</span><span class="sxs-lookup"><span data-stu-id="7229d-130">Enable Source Maps in settings</span></span>  

<span data-ttu-id="7229d-131">Source Maps are enabled by default</span><span class="sxs-lookup"><span data-stu-id="7229d-131">Source Maps are enabled by default</span></span> <!--\(as of Microsoft Edge 39\)--><span data-ttu-id="7229d-132">, but if you want to double-check or enable them; first open DevTools, click the **Customize and control DevTools** \(`...`\) button, and select **Settings**.</span><span class="sxs-lookup"><span data-stu-id="7229d-132">, but if you want to double-check or enable them; first open DevTools, click the **Customize and control DevTools** \(`...`\) button, and select **Settings**.</span></span>  <span data-ttu-id="7229d-133">On the **Preferences** pane, under **Sources**, check **Enable JavaScript Source Maps**.</span><span class="sxs-lookup"><span data-stu-id="7229d-133">On the **Preferences** pane, under **Sources**, check **Enable JavaScript Source Maps**.</span></span>  <span data-ttu-id="7229d-134">You may also check **Enable CSS Source Maps**.</span><span class="sxs-lookup"><span data-stu-id="7229d-134">You may also check **Enable CSS Source Maps**.</span></span>  

:::image type="complex" source="../media/javascript-settings-preferences-sources-enable-javascript-source-maps.msft.png" alt-text="Enable Source Maps" lightbox="../media/javascript-settings-preferences-sources-enable-javascript-source-maps.msft.png":::
   **<span data-ttu-id="7229d-136">Enable JavaScript Source Maps</span><span class="sxs-lookup"><span data-stu-id="7229d-136">Enable JavaScript Source Maps</span></span>**  
:::image-end:::  

### <span data-ttu-id="7229d-137">Debugging with Source Maps</span><span class="sxs-lookup"><span data-stu-id="7229d-137">Debugging with Source Maps</span></span>  

<span data-ttu-id="7229d-138">When debugging your code and Source Maps enabled, Source Maps show in two places:</span><span class="sxs-lookup"><span data-stu-id="7229d-138">When debugging your code and Source Maps enabled, Source Maps show in two places:</span></span>  

1.  <span data-ttu-id="7229d-139">In the console \(the link to source should be the original file, not the generated one\)</span><span class="sxs-lookup"><span data-stu-id="7229d-139">In the console \(the link to source should be the original file, not the generated one\)</span></span>  
1.  <span data-ttu-id="7229d-140">When stepping through code \(the links in the call stack should open the original source file\)</span><span class="sxs-lookup"><span data-stu-id="7229d-140">When stepping through code \(the links in the call stack should open the original source file\)</span></span>  
    
<!--todo: add link to debugging your code when section is available -->  
<!--[DebugBreakpointsStepCode]: ../debug/breakpoints/step-code.md ""  -->  

## <span data-ttu-id="7229d-141">@sourceURL and displayName</span><span class="sxs-lookup"><span data-stu-id="7229d-141">@sourceURL and displayName</span></span>  

<span data-ttu-id="7229d-142">While not part of the Source Map spec, the `@sourceURL` allows you to make development much easier when working with evals.</span><span class="sxs-lookup"><span data-stu-id="7229d-142">While not part of the Source Map spec, the `@sourceURL` allows you to make development much easier when working with evals.</span></span>  <span data-ttu-id="7229d-143">This helper looks very similar to the `//# sourceMappingURL` property and is actually mentioned in the Source Map V3 specifications.</span><span class="sxs-lookup"><span data-stu-id="7229d-143">This helper looks very similar to the `//# sourceMappingURL` property and is actually mentioned in the Source Map V3 specifications.</span></span>  

<span data-ttu-id="7229d-144">By including the following special comment in your code, which is be evaled, you are able to name evals and inline scripts and styles so each appears as more logical names in your DevTools.</span><span class="sxs-lookup"><span data-stu-id="7229d-144">By including the following special comment in your code, which is be evaled, you are able to name evals and inline scripts and styles so each appears as more logical names in your DevTools.</span></span>  

```javascript
//# sourceURL=source.coffee
```  

<span data-ttu-id="7229d-145">Navigate to the following page.</span><span class="sxs-lookup"><span data-stu-id="7229d-145">Navigate to the following page.</span></span>  

*   [<span data-ttu-id="7229d-146">demo</span><span class="sxs-lookup"><span data-stu-id="7229d-146">demo</span></span>][CssNinjaDemoSourceMapping]

<span data-ttu-id="7229d-147">Complete the following actions.</span><span class="sxs-lookup"><span data-stu-id="7229d-147">Complete the following actions.</span></span>  

1.  <span data-ttu-id="7229d-148">Open the DevTools and go to the **Sources** panel.</span><span class="sxs-lookup"><span data-stu-id="7229d-148">Open the DevTools and go to the **Sources** panel.</span></span>  
1.  <span data-ttu-id="7229d-149">Enter in a filename into the **Name your code:** input field.</span><span class="sxs-lookup"><span data-stu-id="7229d-149">Enter in a filename into the **Name your code:** input field.</span></span>  
1.  <span data-ttu-id="7229d-150">Click on the **compile** button.</span><span class="sxs-lookup"><span data-stu-id="7229d-150">Click on the **compile** button.</span></span>  
1.  <span data-ttu-id="7229d-151">An alert appears with the evaluated sum from the CoffeeScript source.</span><span class="sxs-lookup"><span data-stu-id="7229d-151">An alert appears with the evaluated sum from the CoffeeScript source.</span></span>  
    
<span data-ttu-id="7229d-152">If you expand the **Sources** sub-panel you now see a new file with the custom filename you entered earlier.</span><span class="sxs-lookup"><span data-stu-id="7229d-152">If you expand the **Sources** sub-panel you now see a new file with the custom filename you entered earlier.</span></span>  <span data-ttu-id="7229d-153">If you double-click to view this file it contains the compiled JavaScript for the original source.</span><span class="sxs-lookup"><span data-stu-id="7229d-153">If you double-click to view this file it contains the compiled JavaScript for the original source.</span></span>  <span data-ttu-id="7229d-154">On the last line, however, is a `// @sourceURL` comment indicating the original source file.</span><span class="sxs-lookup"><span data-stu-id="7229d-154">On the last line, however, is a `// @sourceURL` comment indicating the original source file.</span></span>  <span data-ttu-id="7229d-155">This may help you with debugging while working with language abstractions.</span><span class="sxs-lookup"><span data-stu-id="7229d-155">This may help you with debugging while working with language abstractions.</span></span>  

:::image type="complex" source="../media/javascript-sources-page-coffeeeeeeee.msft.png" alt-text="Enable Source Maps" lightbox="../media/javascript-sources-page-coffeeeeeeee.msft.png":::
   <span data-ttu-id="7229d-157">Work with</span><span class="sxs-lookup"><span data-stu-id="7229d-157">Work with</span></span> `sourceURL`  
:::image-end:::  

## <span data-ttu-id="7229d-158">Getting in touch with the Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="7229d-158">Getting in touch with the Microsoft Edge DevTools team</span></span>

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[BabelJS]: https://babeljs.io "Babel is a JavaScript compiler"  

[CoffeeScriptMain]: https://coffeescript.org "CoffeeScript"  

[CssNinjaDemoSourceMapping]: https://www.thecssninja.com/demo/source_mapping/compile.html "A simple example of //# sourceURL eval naming"  

[DartMain]: https://www.dartlang.org "Dart programming language"  

[GitHubGoogleClosureCompiler]: https://github.com/google/closure-compiler "google/closure-compiler | GitHub"  

[GitHubMishooUglifyJS]: https://github.com/mishoo/UglifyJS "mishoo/UglifyJS | GitHub"  

[GitHubWikiSourceMapsLanguagesTools]: https://github.com/ryanseddon/source-map/wiki/Source-maps:-languages,-tools-and-other-info "Source maps: languages, tools and other info | GitHub wiki"  

[GitHubWikiGoogleTraceurCompiler]: https://github.com/google/traceur-compiler/wiki/Getting-Started "Getting Started - google/traceur-compiler | GitHub wiki"  

[TypeScriptMain]: https://www.typescriptlang.org "TypeScript"  

> [!NOTE]
> <span data-ttu-id="7229d-168">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="7229d-168">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="7229d-169">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate, Google: Tools, Performance, Animation, and UX\).</span><span class="sxs-lookup"><span data-stu-id="7229d-169">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate, Google: Tools, Performance, Animation, and UX\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="7229d-171">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span><span class="sxs-lookup"><span data-stu-id="7229d-171">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  
