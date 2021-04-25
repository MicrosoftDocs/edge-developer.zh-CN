---
description: 从"设置"和"框架库代码">"将内容脚本标记为库代码"。
title: 将内容脚本标记为库代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: c1571ab909aac09e4593413e96f7d4b7723c7759
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519343"
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

# <a name="mark-content-scripts-as-library-code"></a><span data-ttu-id="edd15-104">将内容脚本标记为库代码</span><span class="sxs-lookup"><span data-stu-id="edd15-104">Mark content scripts as Library code</span></span>  

<span data-ttu-id="edd15-105">使用 **"源"** 工具逐步执行 [代码时][DevToolsJavascriptStepThroughCode]，有时会对无法识别的代码暂停。</span><span class="sxs-lookup"><span data-stu-id="edd15-105">When you use the **Sources** tool to [step through code][DevToolsJavascriptStepThroughCode], sometimes you pause on code that you don't recognize.</span></span>  <span data-ttu-id="edd15-106">您可能暂停了已安装的 Microsoft Edge 扩展之一的代码。</span><span class="sxs-lookup"><span data-stu-id="edd15-106">You probably paused on code for one of the Microsoft Edge Extensions that you installed.</span></span>  <span data-ttu-id="edd15-107">若要不在扩展代码上暂停，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="edd15-107">To not pause on extension code, complete the following actions.</span></span>  

1.  <span data-ttu-id="edd15-108">在 DevTools 中，在右上角选择齿轮图标" (**设置** ") 。</span><span class="sxs-lookup"><span data-stu-id="edd15-108">In DevTools, in the upper right, choose the gear icon (**Settings**).</span></span>  <span data-ttu-id="edd15-109">此时将出现**设置**页面。</span><span class="sxs-lookup"><span data-stu-id="edd15-109">The **Settings** page appears.</span></span>  
1.  <span data-ttu-id="edd15-110">在"**设置"下**，选择"**忽略列表"。**</span><span class="sxs-lookup"><span data-stu-id="edd15-110">Below **Settings**, choose **Ignore List**.</span></span>  <span data-ttu-id="edd15-111">将显示 **"设置"的** "框架库 **代码"** 部分。</span><span class="sxs-lookup"><span data-stu-id="edd15-111">The **Framework Library Code** section of **Settings** appears.</span></span>  
1.  <span data-ttu-id="edd15-112">打开" **将内容脚本标记为库代码"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="edd15-112">Turn on the **Mark content scripts as Library code** checkbox.</span></span>  
    
    :::image type="complex" source="../../media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png" alt-text="启用"将内容脚本标记为库代码"复选框" lightbox="../../media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png":::
       <span data-ttu-id="edd15-114">启用" **将内容脚本标记为库代码"** 复选框</span><span class="sxs-lookup"><span data-stu-id="edd15-114">Enable the **Mark content scripts as Library code** checkbox</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="edd15-115">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="edd15-115">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsJavascriptStepThroughCode]: ../index.md#step-4-step-through-the-code "步骤 4：逐步完成代码 - 开始在 Microsoft Edge DevTools |Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="edd15-117">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="edd15-117">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="edd15-118">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/guides/blackbox-chrome-extension-scripts)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="edd15-118">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/guides/blackbox-chrome-extension-scripts) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="edd15-120">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="edd15-120">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
