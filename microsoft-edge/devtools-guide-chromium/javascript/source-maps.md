---
description: 即使组合、缩小或编译客户端代码，也保持其可读和可调试。
title: 将预处理的代码映射到源代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: c04d1ec02b188cc7ec8ab2598b395dbeb4431c46
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519413"
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

# <a name="map-preprocessed-code-to-source-code"></a>将预处理的代码映射到源代码  

即使组合、缩小或编译客户端代码，也保持其可读和可调试。  使用源映射将源代码映射到已编译的代码。  

### <a name="summary"></a>摘要  

*   使用"源地图"将缩小代码映射到源代码。  然后，您能够读取和调试原始源中的已编译代码。  
*   只能使用能够生成源地图的预处理器。  
*   验证 Web 服务器能否提供源地图。  
    
<!--todo: add link to preprocessors capable of producing Source Maps when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

## <a name="get-started-with-preprocessors"></a>预处理器入门  

本文介绍了如何在 DevTools 源工具中与 JavaScript 源映射进行交互。  <!--For a first overview of what preprocessors are, how each may help, and how Source Maps work; navigate to Set Up CSS & JS Preprocessors.  -->  

<!--todo: add link to Set Up CSS & JS Preprocessors when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors#debugging-and-editing-preprocessed-content ""  -->  

## <a name="use-a-supported-preprocessor"></a>使用受支持的预处理器  

使用能够创建源地图的微型程序。  <!--For the most popular options, navigate to preprocessor support section.  -->  对于扩展视图，导航到源 [地图：语言、工具和其他信息][GitHubWikiSourceMapsLanguagesTools] Wiki 页面。  

<!--todo: add link to display the preprocessor support section when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

通常将以下类型的预处理器与源地图结合使用：  

*   Transpilers [\ (，Traceur][BabelJS] [][GitHubWikiGoogleTraceurCompiler]\)   
*   Compilers \ ([Closure Compiler][GitHubGoogleClosureCompiler]， [TypeScript][|::ref1::|Main]， [CoffeeScript][|::ref2::|Main]，[则 ) ][DartMain]  
*   Minifiers \ ([UglifyJS][GitHubMishooUglifyJS]\)   
    
## <a name="source-maps-in-devtools-sources-tool"></a>DevTools 源工具中的源地图  

来自预处理器的源地图除了缩小文件外，还会导致 DevTools 加载原始文件。  然后，使用原始文件设置断点并逐步执行代码。  同时，Microsoft Edge 实际上是在运行缩小代码。  通过运行代码，你可以错觉运行生产中的开发网站。  

在 DevTools 中运行源地图时，应该会注意到 JavaScript 未编译，并且它引用的所有单个 JavaScript 文件都显示出来。  DevTools 中的源地图使用源映射，但基础功能实际上运行已编译的代码。  任何错误、日志和断点都映射到开发人员代码，以便进行出色的调试。  实际上，它让你产生一种在生产中运行开发网站的错觉。  

### <a name="enable-source-maps-in-settings"></a>在设置中启用源地图  

默认情况下启用源地图<!-- \(as of Microsoft Edge 39\)-->，但如果您想要仔细检查或启用它们;First open DevTools， choose **Customize and control DevTools** \ (`...` \) > **Settings**.  在首选项**窗格的****源下**，启用**JavaScript 源映射**。  还可以启用"启用**CSS 源映射"。**  

:::image type="complex" source="../media/javascript-settings-preferences-sources-enable-javascript-source-maps.msft.png" alt-text="启用源地图" lightbox="../media/javascript-settings-preferences-sources-enable-javascript-source-maps.msft.png":::
   **启用 JavaScript 源地图**  
:::image-end:::  

### <a name="debugging-with-source-maps"></a>使用源地图调试  

调试代码并启用源地图时，源地图显示在两处：  

1.  在控制台 \ (源的链接应该是原始文件，而不是生成的\)   
1.  单步执行代码 \ (调用堆栈中的链接应打开原始源文件\)   
    
<!--todo: add link to debugging your code when section is available -->  
<!--[DebugBreakpointsStepCode]: ../debug/breakpoints/step-code.md ""  -->  

## <a name="sourceurl-and-displayname"></a>@sourceURL 和 displayName  

虽然 不是 Source Map 规范的一部分，但 允许您在使用 evals 时更轻松地 `@sourceURL` 进行开发。  帮助程序显示类似于 `//# sourceMappingURL` 属性，并提及源地图 V3 规范。  

通过在你的代码中包括以下特殊注释（已对此进行评论）可以命名 evals 以及内联脚本和样式，以便每个注释在 DevTools 中显示为更符合逻辑的名称。  

```javascript
//# sourceURL=source.coffee
```  

导航到以下页面。  

*   [演示][CssNinjaDemoSourceMapping]

完成以下操作。  

1.  打开 DevTools 并导航到 **"源"** 工具。  
1.  在"命名代码：输入" **字段中** 输入文件名。  
1.  选择" **编译"** 按钮。  
1.  将出现警报，显示来自 CoffeeScript 源的评估和。  
    
如果展开" **源** "子面板，现在将显示一个包含先前输入的自定义文件名的新文件。  如果双击查看此文件，则它包含原始源的已编译 JavaScript。  但是，最后一行是 `// @sourceURL` 指示原始源文件的注释。  这有助于你在使用语言抽象时进行调试。  

:::image type="complex" source="../media/javascript-sources-page-coffeeeeeeee.msft.png" alt-text="使用 sourceURL" lightbox="../media/javascript-sources-page-coffeeeeeeee.msft.png":::
   使用 `sourceURL`  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队

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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于此处，[](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps)由[Meggin Kearney][MegginKearney] \ (Tech Writer\) 和[Paul Bakaus][PaulBakaus] \ (Open Web Developer Advocate、Google：Tools、Performance、Animation 和 UX\) 创作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  
