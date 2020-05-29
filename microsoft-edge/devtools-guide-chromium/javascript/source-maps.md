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





# 将预处理的代码映射到源代码   




即使在组合、minify 或编译之后，你的客户端代码也能保持可读和可调试。  使用源映射将源代码映射到已编译的代码。  

### 摘要  

*   使用源映射将 minified 代码映射到源代码。 然后，你可以在原始源中读取和调试已编译的代码。  
*   仅使用能够生成源映射的 preprocessors。  
*   验证你的 web 服务器是否能够提供源映射。  

<!--todo: add link to preprocessors capable of producing Source Maps when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

## Preprocessors 入门  

本文介绍如何在 DevTools "源" 面板中与 JavaScript 源映射进行交互。  <!--For a first overview of what preprocessors are, how each may help, and how Source Maps work; see Set Up CSS & JS Preprocessors.  -->  

<!--todo: add link to Set Up CSS & JS Preprocessors when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors#debugging-and-editing-preprocessed-content ""  -->  

## 使用支持的预处理器  

你需要使用能够创建源映射的 minifier。  <!--For the most popular options, see the preprocessor support section.  -->  有关扩展视图，请参阅[源地图：语言、工具和其他信息][GitHubWikiSourceMapsLanguagesTools]wiki 网页。  

<!--todo: add link to see the preprocessor support section when section is available -->  
<!--[]: /web/tools/setup/setup-preprocessors?#supported_preprocessors ""  -->  

以下类型的 preprocessors 通常与源地图结合使用：  

*   Transpilers \ （[Babel][BabelJS]， [Traceur][GitHubWikiGoogleTraceurCompiler]\）  
*   编译器 \ （[闭版编译器][GitHubGoogleClosureCompiler]、 [TypeScript][|::ref1::|Main]、 [CoffeeScript][|::ref2::|Main]、 [Dart][DartMain]\）  
*   Minifiers \ （[UglifyJS][GitHubMishooUglifyJS]\）  

## DevTools 源面板中的源映射  

Preprocessors 中的源映射可导致 DevTools 加载原始文件，除了 minified。  然后使用原始设置断点并逐句通过代码。  同时，Microsoft Edge 实际上正在运行你的 minified 代码。 这为你提供了在生产中运行开发网站的错觉。  

在 DevTools 中运行源映射时，应注意不编译 JavaScript，并且你可以查看它引用的所有单个 JavaScript 文件。  这是使用源映射，但在后台实际运行已编译的代码。  任何错误、日志和断点都将映射到 dev 代码，以便进行超调试！  因此，它可以让你感觉你正在生产中运行开发人员网站。  

### 在 "设置" 中启用源映射  

默认情况下启用源映射 <!--\(as of Microsoft Edge 39\)-->，但如果您想要对其进行双重检查或启用，首先打开 DevTools，单击 "**自定义和控制 DevTools** `...` " 按钮，然后选择 "**设置**"。  在 "**首选项**" 窗格的 "**源**" 下，选中 "**启用 JavaScript 源映射**"。  您也可以选中 "**启用 CSS 源映射**"。  

> ##### 图 1  
> 启用源映射  
> ![启用源映射][ImageSourceMaps]  

### 通过源映射进行调试  

当调试你的代码和已启用源映射时，源映射显示在两个位置：  

1.  在控制台中 \ （指向源的链接应该是原始文件，而不是生成的文件 \）  
1.  逐句通过代码时 \ （调用堆栈中的链接应打开原始源文件 \）  

<!--todo: add link to debugging your code when section is available -->  
<!--[DebugBreakpointsStepCode]: https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/debug/breakpoints/step-code ""  -->  

## @sourceURL 和 displayName  

虽然不是源地图规范的一部分，但可 `@sourceURL` 让你在使用 evals 时更轻松地进行开发。  此帮助程序看起来与属性非常相似 `//# sourceMappingURL` ，并且在源地图 V3 规范中实际提及。  

通过在你的代码中包含以下特殊注释（这是 evaled，你可以命名 evals 和内联脚本和样式，以便每个脚本和样式在你的 DevTools 中显示为更多的逻辑名称。  

```javascript
//# sourceURL=source.coffee
```  

导航到以下页面。  

*   [演示][CssNinjaDemoSourceMapping]

请按照以下步骤操作。  

1.  打开 "DevTools"，然后转到 "**源**" 面板。  
1.  在文件名中输入**_代码：_** 输入字段。  
1.  单击 "**编译**" 按钮。  
1.  将显示一个警报，其中包含 CoffeeScript 源中计算的和。  

如果展开 "**_源_**" 子面板，您现在将看到一个具有您以前输入的自定义文件名的新文件。  如果双击以查看此文件，则它包含原始源的已编译 JavaScript。  但是，最后一行是 `// @sourceURL` 表示原始源文件的注释。  这可能有助于你在使用语言抽象化时进行调试。  

> ##### 图 2
> 使用 sourceURL  
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
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面可在[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps)找到，并由[Meggin Kearney][MegginKearney] \ （技术作者）和[Paul Bakaus][PaulBakaus] \ （开放 Web 开发人员、Google： TOOLS、性能、动画和 UX \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  
