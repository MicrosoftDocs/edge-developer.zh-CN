---
title: 将内容脚本标记为库代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 410a74b906e3b1ff7ff98b6d1791e057e4fa89c4
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982799"
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





# 将内容脚本标记为库代码   



使用 Microsoft Edge DevTools 的 " **源** " 面板 [逐句通过代码][DevToolsJavascriptStepThroughCode]时，有时你会在无法识别的代码上暂停。  你可能已暂停已安装的其中一个 Microsoft Edge 扩展的代码。  完成以下步骤，不要暂停扩展代码。  

1.  打开 DevTools，选择 " **自定义和控制" DevTools** \ (`...` \ ) 然后单击 " **设置**"。  您也可以通过按下 "打开 **设置** " `F1` 。  

1.  选择打开 "**设置**" 的 "**框架库代码**" 部分的 "**库代码**" 选项卡。  
1.  启用 "将 **内容脚本标记为库代码** " 复选框。  
    
    :::image type="complex" source="../../media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png" alt-text="启用 "将内容脚本标记为库代码" 复选框" lightbox="../../media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png":::
       启用 "将 **内容脚本标记为库代码** " 复选框  
    :::image-end:::  
    
<!--  
## Feedback   


-->  

<!-- links -->  

[DevToolsJavascriptStepThroughCode]: ../index.md#step-4-step-through-the-code "步骤4：逐句通过代码-开始在 Microsoft Edge DevTools 中调试 JavaScriptMicrosoft 文档"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/javascript/guides/blackbox-chrome-extension-scripts) 找到，并由 [Kayce Basques][KayceBasques] (技术作者、Chrome DevTools & Lighthouse \ ) 创作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
