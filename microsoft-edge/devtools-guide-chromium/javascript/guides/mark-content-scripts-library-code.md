---
description: 从 "设置" > 框架库代码启用 "将内容脚本标记为库代码"。
title: 将内容脚本标记为库代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 2a9bca703004b6232bef857d7b9e2f45458db52d
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11124696"
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

# <span data-ttu-id="48aa7-104">将内容脚本标记为库代码</span><span class="sxs-lookup"><span data-stu-id="48aa7-104">Mark content scripts as Library code</span></span>  

<span data-ttu-id="48aa7-105">使用 Microsoft Edge DevTools 的 " **源** " 面板 [逐句通过代码][DevToolsJavascriptStepThroughCode]时，有时你会在无法识别的代码上暂停。</span><span class="sxs-lookup"><span data-stu-id="48aa7-105">When using the **Sources** panel of Microsoft Edge DevTools to [step through code][DevToolsJavascriptStepThroughCode], sometimes you pause on code that you do not recognize.</span></span>  <span data-ttu-id="48aa7-106">你可能已暂停已安装的其中一个 Microsoft Edge 扩展的代码。</span><span class="sxs-lookup"><span data-stu-id="48aa7-106">You probably paused on code for one of the Microsoft Edge Extensions that you installed.</span></span>  <span data-ttu-id="48aa7-107">完成以下步骤，不要暂停扩展代码。</span><span class="sxs-lookup"><span data-stu-id="48aa7-107">Complete the following steps to not pause on extension code.</span></span>  

1.  <span data-ttu-id="48aa7-108">打开 DevTools，选择 " **自定义和控制" DevTools** \ (`...` \ ) 然后选择 " **设置**"。</span><span class="sxs-lookup"><span data-stu-id="48aa7-108">Open DevTools, choose **Customize and control DevTools** \(`...`\) and choose **Settings**.</span></span>  <span data-ttu-id="48aa7-109">您也可以通过**Settings**选择打开设置 `F1` 。</span><span class="sxs-lookup"><span data-stu-id="48aa7-109">You may also open **Settings** by selecting `F1`.</span></span>  

1.  <span data-ttu-id="48aa7-110">选择打开 "**设置**" 的 "**框架库代码**" 部分的 "**库代码**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="48aa7-110">Select the **Library code** tab which opens the **Framework Library Code** section of **Settings**.</span></span>  
1.  <span data-ttu-id="48aa7-111">启用 "将 **内容脚本标记为库代码** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="48aa7-111">Enable the **Mark content scripts as Library code** checkbox.</span></span>  
    
    :::image type="complex" source="../../media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png" alt-text="启用 &quot;将内容脚本标记为库代码&quot; 复选框" lightbox="../../media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png":::
       <span data-ttu-id="48aa7-113">启用 "将 **内容脚本标记为库代码** " 复选框</span><span class="sxs-lookup"><span data-stu-id="48aa7-113">Enable the **Mark content scripts as Library code** checkbox</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="48aa7-114">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="48aa7-114">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsJavascriptStepThroughCode]: ../index.md#step-4-step-through-the-code "步骤4：逐句通过代码-开始在 Microsoft Edge DevTools 中调试 JavaScriptMicrosoft 文档"  

> [!NOTE]
> <span data-ttu-id="48aa7-116">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="48aa7-116">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="48aa7-117">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/guides/blackbox-chrome-extension-scripts)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="48aa7-117">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/guides/blackbox-chrome-extension-scripts) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="48aa7-119">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="48aa7-119">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
