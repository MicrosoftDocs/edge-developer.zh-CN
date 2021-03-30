---
description: 从"设置"和"框架库代码"中>"将内容脚本标记为库代码"。
title: 将内容脚本标记为库代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: ffc27cdd04ce28df888507fb2e1dc460d5bb4f21
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398950"
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

# <a name="mark-content-scripts-as-library-code"></a><span data-ttu-id="b2286-104">将内容脚本标记为库代码</span><span class="sxs-lookup"><span data-stu-id="b2286-104">Mark content scripts as Library code</span></span>  

<span data-ttu-id="b2286-105">使用 Microsoft \*\*\*\* Edge DevTools 的"[][DevToolsJavascriptStepThroughCode]源"面板逐步执行代码时，有时会暂停你无法识别的代码。</span><span class="sxs-lookup"><span data-stu-id="b2286-105">When using the **Sources** panel of Microsoft Edge DevTools to [step through code][DevToolsJavascriptStepThroughCode], sometimes you pause on code that you do not recognize.</span></span>  <span data-ttu-id="b2286-106">您可能在已安装的 Microsoft Edge 扩展之一的代码上暂停。</span><span class="sxs-lookup"><span data-stu-id="b2286-106">You probably paused on code for one of the Microsoft Edge Extensions that you installed.</span></span>  <span data-ttu-id="b2286-107">完成以下步骤，以不暂停扩展代码。</span><span class="sxs-lookup"><span data-stu-id="b2286-107">Complete the following steps to not pause on extension code.</span></span>  

1.  <span data-ttu-id="b2286-108">打开 DevTools，选择"自定义和控制**DevTools** \ (`...` \) >**设置"。**</span><span class="sxs-lookup"><span data-stu-id="b2286-108">Open DevTools, choose **Customize and control DevTools** \(`...`\) > **Settings**.</span></span>  <span data-ttu-id="b2286-109">您也可以通过选择 **来** 打开"设置 `F1` "。</span><span class="sxs-lookup"><span data-stu-id="b2286-109">You may also open **Settings** by selecting `F1`.</span></span>  

1.  <span data-ttu-id="b2286-110">选择 **打开** "设置"的 **"框架库** 代码"一节的库代码 **面板**。</span><span class="sxs-lookup"><span data-stu-id="b2286-110">Choose the **Library code** panel which opens the **Framework Library Code** section of **Settings**.</span></span>  
1.  <span data-ttu-id="b2286-111">打开" **将内容脚本标记为库代码"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="b2286-111">Turn on the **Mark content scripts as Library code** checkbox.</span></span>  
    
    :::image type="complex" source="../../media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png" alt-text="启用将内容脚本标记为库代码复选框" lightbox="../../media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png":::
       <span data-ttu-id="b2286-113">启用" **将内容脚本标记为库代码"** 复选框</span><span class="sxs-lookup"><span data-stu-id="b2286-113">Enable the **Mark content scripts as Library code** checkbox</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="b2286-114">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="b2286-114">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsJavascriptStepThroughCode]: ../index.md#step-4-step-through-the-code "步骤 4：逐步完成代码 - 开始在 Microsoft Edge DevTools |Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="b2286-116">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="b2286-116">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b2286-117">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/guides/blackbox-chrome-extension-scripts)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="b2286-117">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/guides/blackbox-chrome-extension-scripts) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="b2286-119">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="b2286-119">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
