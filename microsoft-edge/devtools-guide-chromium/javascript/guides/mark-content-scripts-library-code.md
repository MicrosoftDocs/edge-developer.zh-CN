---
description: 从框架库代码启用"将内容脚本标记为设置 >库代码"。
title: 将内容脚本标记为库代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: e3c2e89e8635b568d0beea8df8720bbb28beb711
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564026"
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
# <a name="mark-content-scripts-as-library-code"></a><span data-ttu-id="feb46-104">将内容脚本标记为库代码</span><span class="sxs-lookup"><span data-stu-id="feb46-104">Mark content scripts as Library code</span></span>  

<span data-ttu-id="feb46-105">使用 **"源"** 工具逐步执行 [代码时][DevToolsJavascriptStepThroughCode]，有时会对无法识别的代码暂停。</span><span class="sxs-lookup"><span data-stu-id="feb46-105">When you use the **Sources** tool to [step through code][DevToolsJavascriptStepThroughCode], sometimes you pause on code that you don't recognize.</span></span>  <span data-ttu-id="feb46-106">您可能暂停了已安装的一个 Microsoft Edge 扩展的代码。</span><span class="sxs-lookup"><span data-stu-id="feb46-106">You probably paused on code for one of the Microsoft Edge Extensions that you installed.</span></span>  <span data-ttu-id="feb46-107">若要不在扩展代码上暂停，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="feb46-107">To not pause on extension code, complete the following actions.</span></span>  

1.  <span data-ttu-id="feb46-108">在 DevTools 的右上角，选择齿轮图标\*\* (设置) 。\*\*</span><span class="sxs-lookup"><span data-stu-id="feb46-108">In DevTools, in the upper right, choose the gear icon (**Settings**).</span></span>  <span data-ttu-id="feb46-109">此时将出现**设置**页面。</span><span class="sxs-lookup"><span data-stu-id="feb46-109">The **Settings** page appears.</span></span>  
1.  <span data-ttu-id="feb46-110">在 **"设置"** 下，选择"**忽略列表"。**</span><span class="sxs-lookup"><span data-stu-id="feb46-110">Below **Settings**, choose **Ignore List**.</span></span>  <span data-ttu-id="feb46-111">将显示 **"框架**库代码 **"设置**显示。</span><span class="sxs-lookup"><span data-stu-id="feb46-111">The **Framework Library Code** section of **Settings** appears.</span></span>  
1.  <span data-ttu-id="feb46-112">打开" **将内容脚本标记为库代码"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="feb46-112">Turn on the **Mark content scripts as Library code** checkbox.</span></span>  
    
    :::image type="complex" source="../../media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png" alt-text="启用"将内容脚本标记为库代码"复选框" lightbox="../../media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png":::
       <span data-ttu-id="feb46-114">启用" **将内容脚本标记为库代码"** 复选框</span><span class="sxs-lookup"><span data-stu-id="feb46-114">Enable the **Mark content scripts as Library code** checkbox</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="feb46-115">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="feb46-115">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsJavascriptStepThroughCode]: ../index.md#step-4-step-through-the-code "步骤 4：逐步执行代码 - 开始在 DevTools Microsoft Edge中调试 JavaScript |Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="feb46-117">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="feb46-117">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="feb46-118">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/guides/blackbox-chrome-extension-scripts)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="feb46-118">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/guides/blackbox-chrome-extension-scripts) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="feb46-120">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="feb46-120">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
