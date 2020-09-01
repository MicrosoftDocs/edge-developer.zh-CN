---
title: 访问本地服务器
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: fb8f8aabaf426685417f90e25295f3e8e7b08994
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10984901"
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





# 访问本地服务器   




在开发计算机 web 服务器上托管网站，然后从 Android 设备访问内容。  

使用 USB 电缆和 Microsoft Edge DevTools，从开发计算机运行网站，然后在 Android 设备上查看网站。  

### 摘要  

*   通过端口转发，你可以查看由 Android 设备上的开发计算机中运行的 web 服务器托管的内容。  
*   如果 web 服务器使用自定义域，请将 Android 设备设置为使用自定义域映射访问该域中的内容。  

## 设置端口转发   

通过端口转发，Android 设备可以访问在开发计算机上运行的 web 服务器上承载的内容。  端口转发的工作原理是在 Android 设备上创建一个映射到开发计算机上的 TCP 端口的侦听 TCP 端口。  端口之间的流量通过 Android 设备和开发计算机之间的 USB 连接进行传输，因此连接不依赖于你的网络配置。  

要启用端口转发，请执行以下操作：  

1.  在开发计算机和 Android 设备之间设置 [远程调试][RemoteDebuggingGettingStarted] 。  完成后，你应在 " **检查设备** " 对话框的左侧菜单中看到 Android 设备和 **连接** 状态指示器。  
1.  在 DevTools 中的 " **检查设备** " 对话框中，启用 **端口转发**。  
1.  选择 " **添加规则**"。  
    
    :::image type="complex" source="../media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png" alt-text="添加端口转发规则" lightbox="../media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png":::
       添加端口转发规则  
    :::image-end:::  
    
1.  在左侧的 " **设备端口** " 文本框中，输入 `localhost` 要在 Android 设备上访问该网站的端口号。  例如，如果您想要从 enter 访问网站 `localhost:5000` `5000` 。  
1.  在右侧的 " **本地地址** " 文本框中，输入你的网站在你的开发计算机上运行的 web 服务器上的 IP 地址或主机名，后跟端口号。  例如，如果您的网站在进入时 `localhost:7331` 运行 `localhost:7331` 。  
1.  选择**添加**。  
    
端口转发现已设置。  在 " **检查设备** " 对话框内的设备上的选项卡上，查看端口的状态指示器。  

:::image type="complex" source="../media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png" alt-text="端口转发状态" lightbox="../media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png":::
   端口转发状态  
:::image-end:::  

若要查看内容，请在 Android 设备上打开 Microsoft Edge，然后转到在 `localhost` " **设备端口** " 字段中指定的端口。  例如，如果您 `5000` 在 "" 字段中输入，请访问 `localhost:5000` 。  

## 映射到自定义本地域   

自定义域映射使你能够从使用自定义域的开发计算机上的 web 服务器查看 Android 设备上的内容。  

例如，假设您的网站使用的第三方 JavaScript 库仅适用于域 `microsoft-edge.devtools` 。  因此，你在开发计算机上的文件中创建一个条目， `hosts` 以便将此域映射到 `localhost` \ (例如 `127.0.0.1 microsoft-edge.devtools` \ ) 。  设置自定义域映射和端口转发后，在 Android 设备上的 URL 处查看网站 `microsoft-edge.devtools` 。  

### 设置到代理服务器的端口转发  

若要映射自定义域，必须在开发计算机上运行代理服务器。  代理服务器的示例包括 [Charles][CharlesWebDebuggingProxy]、 [Squid][SquidOptimisingWebDelivery]和 [Fiddler][FiddlerWebDebuggingProxy]。  

若要设置到代理的端口转发，请执行以下操作：  

1.  运行代理服务器并记录它所使用的端口。  
    
    > [!NOTE]
    > 代理服务器和 web 服务器必须在不同的端口上运行。  
    
1.  设置将 [端口转发](#set-up-port-forwarding) 到 Android 设备。  对于 " **本地地址** " 字段，输入 `localhost:` 后跟代理服务器运行的端口。  例如，如果它在端口上运行 `8000` ，请访问 `localhost:8000` 。  在 " **设备端口** " 字段中输入希望 Android 设备侦听的号码，例如 `3333` 。  
    
### 在设备上配置代理服务器设置  

接下来，你需要将 Android 设备配置为与代理服务器通信。  

1.  在 Android 设备上，转到 "**设置**  >  **wi-fi**"。  
1.  长按您当前连接的网络的名称。  
    
    > [!NOTE]
    > 代理设置适用于每个网络。  
    
1.  选择 " **修改网络**"。  
1.  选择 " **高级选项**"。  将显示代理设置。  
1.  选择 " **代理** " 菜单，然后选择 " **手动**"。  
1.  对于 " **代理主机名** " 字段，请输入 `localhost` 。  
1.  对于 " **代理服务器端口** " 字段，输入您在上一节中为 " **设备端口** " 输入的端口号。  
1.  选择**保存**。  
    
通过这些设置，你的设备会将其所有请求转发到你的开发计算机上的代理。  代理代表你的设备发出请求，因此对自定义本地域的请求已正确解析。  

现在，在 Android 设备上访问自定义域，就像在开发计算机上一样。  

如果您的 web 服务器在非标准端口上运行，请记住在从 Android 设备请求内容时指定该端口。  例如，如果 web 服务器在端口上使用自定义域 `microsoft-edge.devtools` `7331` ，则当您从 Android 设备查看网站时，应使用 URL `microsoft-edge.devtools:7331` 。  

> [!TIP]
> 若要恢复正常浏览，请记住在从开发计算机断开连接后还原 Android 设备上的代理设置。  

<!--  
  


-->  
<!-- links -->  

[RemoteDebuggingGettingStarted]: ./index.md "开始使用 "远程调试 Android 设备" |Microsoft 文档"  

[CharlesWebDebuggingProxy]: https://www.charlesproxy.com "Charles Web 调试代理"  

[SquidOptimisingWebDelivery]: https://www.squid-cache.org "squid：优化 Web 送达"  

[FiddlerWebDebuggingProxy]: https://www.telerik.com/fiddler "Fiddler-免费 Web 调试代理"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/local-server) 找到，并由 [Kayce Basques][KayceBasques] (技术作者、Chrome DevTools \ & Lighthouse \ ) 和 [Meggin Kearney][MegginKearney] \ (技术作者 \ ) 创作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
