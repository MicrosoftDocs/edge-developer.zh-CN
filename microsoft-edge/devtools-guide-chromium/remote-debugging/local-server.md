---
description: 在开发计算机 Web 服务器上承载网站，然后从 Android 设备访问内容。
title: 访问本地服务器
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 16c9927ce4548d71681d35e643aea0a6c44ec75a
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398208"
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

# <a name="access-local-servers"></a>访问本地服务器  

在开发计算机 Web 服务器上承载网站，然后从 Android 设备访问内容。  

使用 USB 电缆和 Microsoft Edge DevTools，从开发计算机运行站点，然后在 Android 设备上查看站点。  

### <a name="summary"></a>摘要  

*   通过端口转发，您可以查看在 Android 设备上开发计算机上运行的 Web 服务器承载的内容。  
*   如果 Web 服务器使用的是自定义域，请设置 Android 设备以使用自定义域映射访问该域中的内容。  

## <a name="set-up-port-forwarding"></a>设置端口转发  

通过端口转发，Android 设备可以访问托管在开发计算机中运行的 Web 服务器上的内容。  端口转发的工作原理是，在 Android 设备上创建映射到开发计算机上 TCP 端口的侦听 TCP 端口。  端口之间的流量通过 Android 设备和开发计算机之间的 USB 连接传输，因此连接不依赖于网络配置。  

启用端口转发：  

1.  在 [开发计算机和][RemoteDebuggingGettingStarted] Android 设备之间设置远程调试。  完成后，Android 设备应显示在"检查设备"对话框的左侧菜单**和"已**连接**** 状态"指示器中。  
1.  在 **DevTools 中的** "检查设备"对话框中，启用 **端口转发**。  
1.  选择 **"添加规则"。**  
    
    :::image type="complex" source="../media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png" alt-text="添加端口转发规则" lightbox="../media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png":::
       添加端口转发规则  
    :::image-end:::  
    
1.  在左侧 **的** "设备端口文本框"中，输入希望其能够访问 Android 设备上的 `localhost` 站点的端口号。  例如，如果要从 enter 访问 `localhost:5000` 网站 `5000` 。  
1.  在右侧 **本地** 地址文本框中，输入在开发计算机中运行的 Web 服务器上承载网站的 IP 地址或主机名，后跟端口号。  例如，如果您的网站在 Enter 上运行 `localhost:7331` `localhost:7331` 。  
1.  选择“**添加**”。  
    
现已设置端口转发。  在"检查设备"对话框中，查看设备上选项卡上端口向前 **的状态** 指示器。  

:::image type="complex" source="../media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png" alt-text="端口转发状态" lightbox="../media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png":::
   端口转发状态  
:::image-end:::  

若要查看内容，请打开 Android 设备上的 Microsoft Edge，然后转到你在"设备端口" `localhost` 字段中指定的 **端口** 。  例如，如果在字段中 `5000` 输入，请访问 `localhost:5000` 。  

## <a name="map-to-custom-local-domains"></a>映射到自定义本地域  

通过自定义域映射，您可以查看 Android 设备上使用自定义域的开发计算机上 Web 服务器的内容。  

例如，假设您的网站使用仅在域上工作的第三方 JavaScript 库 `microsoft-edge.devtools` 。  因此，在开发计算机上创建文件条目，以将此域映射到 `hosts` `localhost` \ (例如 `127.0.0.1 microsoft-edge.devtools` ，\) 。  设置自定义域映射和端口转发后，在 Android 设备上通过 URL 查看网站 `microsoft-edge.devtools` 。  

### <a name="set-up-port-forwarding-to-proxy-server"></a>设置到代理服务器的端口转发  

若要映射自定义域，必须在开发计算机上运行代理服务器。  代理服务器的示例包括[，而Fiddler][CharlesWebDebuggingProxy]就是[][SquidOptimisingWebDelivery][这些代理服务器][FiddlerWebDebuggingProxy]。  

设置到代理的端口转发：  

1.  运行代理服务器并记录它使用的端口。  
    
    > [!NOTE]
    > 代理服务器和 Web 服务器必须在不同的端口上运行。  
    
1.  设置 [到 Android 设备的](#set-up-port-forwarding) 端口转发。  对于 **本地地址** 字段，输入后跟 `localhost:` 运行代理服务器的端口。  例如，如果它在端口上运行 `8000` ，请导航到 `localhost:8000` 。  在 **设备端口** 字段中，输入希望 Android 设备侦听的号码，例如 `3333` 。  
    
### <a name="configure-proxy-settings-on-your-device"></a>在设备上配置代理设置  

接下来，你需要将 Android 设备配置为与代理服务器进行通信。  

1.  在 Android 设备上，导航到"**设置**  >  **WLAN"。**  
1.  长按当前连接的网络的名称。  
    
    > [!NOTE]
    > 代理设置适用于每个网络。  
    
1.  选择 **"修改网络"。**  
1.  选择 **"高级"选项**。  显示代理设置。  
1.  选择代理**菜单**，然后选择"**手动"。**  
1.  对于" **代理主机名"** 字段，输入 `localhost` 。  
1.  对于 **"代理端口** "字段，输入在上一部分中为 **设备端口** 输入的端口号。  
1.  选择 **"保存"。**  
    
借助这些设置，你的设备会将它的所有请求转发到开发计算机上代理。  代理代表设备提出请求，因此正确解决了对自定义本地域的请求。  

现在访问 Android 设备上的自定义域，就像在开发计算机上一样。  

如果 Web 服务器运行的是非标准端口，请记住在从 Android 设备请求内容时指定端口。  例如，如果 Web 服务器在端口上使用自定义域，则当您从 Android 设备查看网站时 `microsoft-edge.devtools` `7331` ，应该使用 `microsoft-edge.devtools:7331` URL。  

> [!TIP]
> 若要恢复正常浏览，请记住在断开与开发计算机连接后恢复 Android 设备上的代理设置。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[RemoteDebuggingGettingStarted]: ./index.md "开始远程调试 Android 设备|Microsoft Docs"  

[CharlesWebDebuggingProxy]: https://www.charlesproxy.com "而将调试代理"  

[SquidOptimisingWebDelivery]: https://www.squid-cache.org "quid ： 改进 Web 传递"  

[FiddlerWebDebuggingProxy]: https://www.telerik.com/fiddler "Fiddler - 免费 Web 调试代理"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于此处，[](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/local-server)由[一位（][KayceBasques]该链接人）\ (Technical Writer、Chrome DevTools \& Lighthouse\) 和[Meggin Kearney][MegginKearney] \ (Tech Writer\) 创作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
