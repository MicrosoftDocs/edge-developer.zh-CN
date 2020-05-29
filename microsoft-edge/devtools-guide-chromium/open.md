---
title: 打开 Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 48f80ea9f85bd3509f2ba3d834f99c25247c0761
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601885"
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
   limitations under the License. -->





# <span data-ttu-id="4fa27-103">打开 Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="4fa27-103">Open Microsoft Edge DevTools</span></span>   



<span data-ttu-id="4fa27-104">打开 Microsoft Edge DevTools 有多种方法，因为不同的用户需要快速访问 DevTools UI 的不同部分。</span><span class="sxs-lookup"><span data-stu-id="4fa27-104">There are many ways to open Microsoft Edge DevTools, because different users want fast access to different parts of the DevTools UI.</span></span>  

## <span data-ttu-id="4fa27-105">打开 "元素" 面板以检查 DOM 或 CSS</span><span class="sxs-lookup"><span data-stu-id="4fa27-105">Open the Elements panel to inspect the DOM or CSS</span></span>   

<span data-ttu-id="4fa27-106">当你想要检查某个 DOM 节点的样式或属性时，请右键单击该元素，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="4fa27-106">When you want to inspect the styles or attributes of a DOM node, right-click the element and select **Inspect**.</span></span>  

> ##### <span data-ttu-id="4fa27-107">图 1</span><span class="sxs-lookup"><span data-stu-id="4fa27-107">Figure 1</span></span>  
> <span data-ttu-id="4fa27-108">"**检查**" 选项</span><span class="sxs-lookup"><span data-stu-id="4fa27-108">The **Inspect** option</span></span>  
> !["检查" 选项][ImageInspectOption]  

<span data-ttu-id="4fa27-110">或按 `Control` + `Shift` + `C` \ （Windows \）或 `Command` + `Option` + `C` \ （macOS \）。</span><span class="sxs-lookup"><span data-stu-id="4fa27-110">Or press `Control`+`Shift`+`C` \(Windows\) or `Command`+`Option`+`C` \(macOS\).</span></span>  

<!--See [Get Started With Viewing And Changing CSS][GetStartedCSS].  -->  

## <span data-ttu-id="4fa27-111">打开控制台面板以查看记录的消息或运行 JavaScript</span><span class="sxs-lookup"><span data-stu-id="4fa27-111">Open the Console panel to view logged messages or run JavaScript</span></span>   

<span data-ttu-id="4fa27-112">按 `Control` + `Shift` + `J` \ （Windows \）或 `Command` + `Option` + `J` \ （macOS \）直接跳转到**控制台**面板。</span><span class="sxs-lookup"><span data-stu-id="4fa27-112">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to jump straight into the **Console** panel.</span></span>  

<!--See [Get Started With The Console][ConsoleGetStarted].  -->

## <span data-ttu-id="4fa27-113">打开已打开的上一个面板</span><span class="sxs-lookup"><span data-stu-id="4fa27-113">Open the last panel you had open</span></span>   

<span data-ttu-id="4fa27-114">按 `Control` + `Shift` + `I` \ （Windows \）或 `Command` + `Option` + `I` \ （macOS \）。</span><span class="sxs-lookup"><span data-stu-id="4fa27-114">Press `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\).</span></span>  

## <span data-ttu-id="4fa27-115">从 Microsoft Edge 主菜单打开 DevTools</span><span class="sxs-lookup"><span data-stu-id="4fa27-115">Open DevTools from the Microsoft Edge main menu</span></span>  

<span data-ttu-id="4fa27-116">单击 "**设置" 和 "更多" \ （Alt + F \）** `...` ，然后选择 "**更多工具**  >  **开发人员工具**"。</span><span class="sxs-lookup"><span data-stu-id="4fa27-116">Click **Settings and more \(Alt+F\)** `...` and then select **More Tools** > **Developer Tools**.</span></span>  

> ##### <span data-ttu-id="4fa27-117">图 2</span><span class="sxs-lookup"><span data-stu-id="4fa27-117">Figure 2</span></span>  
> <span data-ttu-id="4fa27-118">从 Microsoft Edge 主菜单打开 DevTools</span><span class="sxs-lookup"><span data-stu-id="4fa27-118">Opening DevTools from the Microsoft Edge main menu</span></span>  
> ![从 Microsoft Edge 主菜单打开 DevTools][ImageOpenFromMain]  

## <span data-ttu-id="4fa27-120">在每个新选项卡上自动打开 DevTools</span><span class="sxs-lookup"><span data-stu-id="4fa27-120">Auto-open DevTools on every new tab</span></span>   

<span data-ttu-id="4fa27-121">从命令行打开 Microsoft Edge 并传递 `--auto-open-devtools-for-tabs` 标志。</span><span class="sxs-lookup"><span data-stu-id="4fa27-121">Open Microsoft Edge from the command line and pass the `--auto-open-devtools-for-tabs` flag.</span></span>  

<span data-ttu-id="4fa27-122">Windows \ （CMD \）：</span><span class="sxs-lookup"><span data-stu-id="4fa27-122">Windows \(CMD\):</span></span>  

```cmd
start msedge --auto-open-devtools-for-tabs
```  

<span data-ttu-id="4fa27-123">Windows \ （PowerShell \）：</span><span class="sxs-lookup"><span data-stu-id="4fa27-123">Windows \(PowerShell\):</span></span>  

```powershell
Start-Process -FilePath "msedge" -ArgumentList "--auto-open-devtools-for-tabs"
```  

<span data-ttu-id="4fa27-124">MacOS</span><span class="sxs-lookup"><span data-stu-id="4fa27-124">macOS:</span></span>  

```bash
/Applications/Microsoft\ Edge\ Beta.app/Contents/MacOS/Microsoft\ Edge\ Beta --auto-open-devtools-for-tabs
```  

 



<!-- image links -->  

[ImagesMainIcon]: /microsoft-edge/devtools-guide-chromium/media/main-menu-icon.msft.png  

[ImageInspectOption]: /microsoft-edge/devtools-guide-chromium/media/bing-right-click-inspect.msft.png "图1： "检查" 选项"  
[ImageOpenFromMain]: /microsoft-edge/devtools-guide-chromium/media/bing-customize-more-tools-developer-tools-transparent.msft.png "图2：从 Microsoft Edge 主菜单打开 DevTools"  

<!-- links -->  

<!--[ConsoleGetStarted]: /microsoft-edge/devtools-guide-chromium/console/get-started ""  -->  
<!--[GetStartedCSS]: /microsoft-edge/devtools-guide-chromium/css "CSS"  -->

> [!NOTE]
> <span data-ttu-id="4fa27-127">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="4fa27-127">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="4fa27-128">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/open)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="4fa27-128">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/open) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="4fa27-130">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="4fa27-130">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
