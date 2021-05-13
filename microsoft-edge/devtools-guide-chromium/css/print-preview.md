---
description: 打开"呈现"工具，然后选择"模拟 CSS 媒体>打印"。
title: '强制Microsoft Edge开发人员工具进入打印预览模式 (CSS 打印媒体类型) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 6c49d956a9a7185b162ca8e2996e7b3e715b40ab
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564425"
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
# <a name="force-microsoft-edge-devtools-into-print-preview-mode"></a>强制Microsoft Edge开发人员工具进入打印预览模式  

打印 [媒体查询][MDNUsingMediaQueries] 控制页面在打印时的外观。  若要强制页面进入打印预览模式：  

1.  选择 `Control`+`Shift`+`P` \(Windows、Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开**命令菜单**。  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       **命令菜单**  
    :::image-end:::  
    
1.  键入 `rendering` ，选择 **"显示呈现**"，然后选择 `Enter` 。  
1.  在"**模拟 CSS 媒体"下**，选择"**打印"。**  
    
    :::image type="complex" source="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png" alt-text="打印预览模式" lightbox="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png":::
       打印预览模式  
    :::image-end:::  
    
可以在此处显示和更改 CSS，就像任何其他网页一样。  导航到“[查看和更改 CSS 入门][DevToolsCSSGetStarted]”。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  
[DevToolsCSSGetStarted]: ./index.md "开始查看和更改 CSS |Microsoft Docs"  

[MDNUsingMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "使用媒体查询|MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/print-preview)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
