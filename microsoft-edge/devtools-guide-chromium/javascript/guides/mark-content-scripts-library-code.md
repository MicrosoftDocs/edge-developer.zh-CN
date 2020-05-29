---
title: 将内容脚本标记为库代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: fe34d8f2fb656283b1821441162b93d47d51d24e
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581787"
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





# <span data-ttu-id="9af0a-103">将内容脚本标记为库代码</span><span class="sxs-lookup"><span data-stu-id="9af0a-103">Mark Content Scripts as Library Code</span></span>   



<span data-ttu-id="9af0a-104">使用 Microsoft Edge DevTools 的 "**源**" 面板[逐句通过代码][DevToolsJavascriptStepThroughCode]时，有时你会在无法识别的代码上暂停。</span><span class="sxs-lookup"><span data-stu-id="9af0a-104">When using the **Sources** panel of Microsoft Edge DevTools to [step through code][DevToolsJavascriptStepThroughCode], sometimes you pause on code that you do not recognize.</span></span>  <span data-ttu-id="9af0a-105">你可能已暂停已安装的其中一个 Microsoft Edge 扩展的代码。</span><span class="sxs-lookup"><span data-stu-id="9af0a-105">You probably paused on code for one of the Microsoft Edge Extensions that you installed.</span></span>  <span data-ttu-id="9af0a-106">完成以下步骤，不要暂停扩展代码。</span><span class="sxs-lookup"><span data-stu-id="9af0a-106">Complete the following steps to not pause on extension code.</span></span>  

1.  <span data-ttu-id="9af0a-107">打开 DevTools，选择 "**自定义和控制" DevTools** `...` ，然后单击 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="9af0a-107">Open DevTools, select **Customize and control DevTools** `...` and click **Settings**.</span></span>  <span data-ttu-id="9af0a-108">您也可以通过按下 "打开**设置**" `F1` 。</span><span class="sxs-lookup"><span data-stu-id="9af0a-108">You may also open **Settings** by pressing `F1`.</span></span>  

1.  <span data-ttu-id="9af0a-109">选择打开 "**设置**" 的 "**框架库代码**" 部分的 "**库代码**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9af0a-109">Select the **Library code** tab which opens the **Framework Library Code** section of **Settings**.</span></span>  
1.  <span data-ttu-id="9af0a-110">启用 "将**内容脚本标记为库代码**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="9af0a-110">Enable the **Mark content scripts as Library code** checkbox.</span></span>  
    
    > ##### <span data-ttu-id="9af0a-111">图 1</span><span class="sxs-lookup"><span data-stu-id="9af0a-111">Figure 1</span></span>  
    > <span data-ttu-id="9af0a-112">启用 "将**内容脚本标记为库代码**" 复选框</span><span class="sxs-lookup"><span data-stu-id="9af0a-112">Enable the **Mark content scripts as Library code** checkbox</span></span>  
    > ![启用 "将内容脚本标记为库代码" 复选框][ImageMarkContentScriptsLibraryCode]  

<!--## Feedback   -->  



<!-- image links -->  

[ImageMarkContentScriptsLibraryCode]: /microsoft-edge/devtools-guide-chromium/media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png "图1：启用 "将内容脚本标记为库代码" 复选框"  

<!-- links -->  

[DevToolsJavascriptStepThroughCode]: ../index.md#step-4-step-through-the-code "步骤4：逐句通过代码-在 Microsoft Edge DevTools 中开始使用调试 JavaScript"  

> [!NOTE]
> <span data-ttu-id="9af0a-116">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="9af0a-116">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9af0a-117">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/guides/blackbox-chrome-extension-scripts)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="9af0a-117">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/guides/blackbox-chrome-extension-scripts) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools & Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="9af0a-119">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="9af0a-119">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
