---
description: 在开发计算机 web 服务器上托管网站，然后从 Android 设备访问内容。
title: 访问本地服务器
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 373cd7ce5cd262bad9fa5460bb2187241246cd75
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993483"
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





# <span data-ttu-id="76357-104">访问本地服务器</span><span class="sxs-lookup"><span data-stu-id="76357-104">Access local servers</span></span>   




<span data-ttu-id="76357-105">在开发计算机 web 服务器上托管网站，然后从 Android 设备访问内容。</span><span class="sxs-lookup"><span data-stu-id="76357-105">Host a site on a development machine web server, then access the content from an Android device.</span></span>  

<span data-ttu-id="76357-106">使用 USB 电缆和 Microsoft Edge DevTools，从开发计算机运行网站，然后在 Android 设备上查看网站。</span><span class="sxs-lookup"><span data-stu-id="76357-106">With a USB cable and Microsoft Edge DevTools, run a site from a development machine and then view the site on an Android device.</span></span>  

### <span data-ttu-id="76357-107">摘要</span><span class="sxs-lookup"><span data-stu-id="76357-107">Summary</span></span>  

*   <span data-ttu-id="76357-108">通过端口转发，你可以查看由 Android 设备上的开发计算机中运行的 web 服务器托管的内容。</span><span class="sxs-lookup"><span data-stu-id="76357-108">Port forwarding enables you to view content hosted by the web server running in your development machine on your Android device.</span></span>  
*   <span data-ttu-id="76357-109">如果 web 服务器使用自定义域，请将 Android 设备设置为使用自定义域映射访问该域中的内容。</span><span class="sxs-lookup"><span data-stu-id="76357-109">If your web server is using a custom domain, set up your Android device to access the content at that domain with custom domain mapping.</span></span>  

## <span data-ttu-id="76357-110">设置端口转发</span><span class="sxs-lookup"><span data-stu-id="76357-110">Set up port forwarding</span></span>   

<span data-ttu-id="76357-111">通过端口转发，Android 设备可以访问在开发计算机上运行的 web 服务器上承载的内容。</span><span class="sxs-lookup"><span data-stu-id="76357-111">Port forwarding enables your Android device to access content that is being hosted on the web server running in your development machine.</span></span>  <span data-ttu-id="76357-112">端口转发的工作原理是在 Android 设备上创建一个映射到开发计算机上的 TCP 端口的侦听 TCP 端口。</span><span class="sxs-lookup"><span data-stu-id="76357-112">Port forwarding works by creating a listening TCP port on your Android device that maps to a TCP port on your development machine.</span></span>  <span data-ttu-id="76357-113">端口之间的流量通过 Android 设备和开发计算机之间的 USB 连接进行传输，因此连接不依赖于你的网络配置。</span><span class="sxs-lookup"><span data-stu-id="76357-113">Traffic between the ports travel through the USB connection between your Android device and development machine, so the connection does not depend on your network configuration.</span></span>  

<span data-ttu-id="76357-114">要启用端口转发，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="76357-114">To enable port forwarding:</span></span>  

1.  <span data-ttu-id="76357-115">在开发计算机和 Android 设备之间设置 [远程调试][RemoteDebuggingGettingStarted] 。</span><span class="sxs-lookup"><span data-stu-id="76357-115">Set up [remote debugging][RemoteDebuggingGettingStarted] between your development machine and your Android device.</span></span>  <span data-ttu-id="76357-116">完成后，你应在 " **检查设备** " 对话框的左侧菜单中看到 Android 设备和 **连接** 状态指示器。</span><span class="sxs-lookup"><span data-stu-id="76357-116">When you are finished, you should see your Android device in the left-hand menu of the **Inspect Devices** dialog and a **Connected** status indicator.</span></span>  
1.  <span data-ttu-id="76357-117">在 DevTools 中的 " **检查设备** " 对话框中，启用 **端口转发**。</span><span class="sxs-lookup"><span data-stu-id="76357-117">In the **Inspect Devices** dialog in DevTools, enable **Port forwarding**.</span></span>  
1.  <span data-ttu-id="76357-118">选择 " **添加规则**"。</span><span class="sxs-lookup"><span data-stu-id="76357-118">Select **Add rule**.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png" alt-text="添加端口转发规则" lightbox="../media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png":::
       <span data-ttu-id="76357-120">添加端口转发规则</span><span class="sxs-lookup"><span data-stu-id="76357-120">Adding a port forwarding rule</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="76357-121">在左侧的 " **设备端口** " 文本框中，输入 `localhost` 要在 Android 设备上访问该网站的端口号。</span><span class="sxs-lookup"><span data-stu-id="76357-121">In the **Device port** textbox on the left, enter the `localhost` port number from which you want to be able to access the site on your Android device.</span></span>  <span data-ttu-id="76357-122">例如，如果您想要从 enter 访问网站 `localhost:5000` `5000` 。</span><span class="sxs-lookup"><span data-stu-id="76357-122">For example, if you wanted to access the site from `localhost:5000` enter `5000`.</span></span>  
1.  <span data-ttu-id="76357-123">在右侧的 " **本地地址** " 文本框中，输入你的网站在你的开发计算机上运行的 web 服务器上的 IP 地址或主机名，后跟端口号。</span><span class="sxs-lookup"><span data-stu-id="76357-123">In the **Local address** textbox on the right, enter the IP address or hostname on which your site is hosted on the web server running in your development machine, followed by the port number.</span></span>  <span data-ttu-id="76357-124">例如，如果您的网站在进入时 `localhost:7331` 运行 `localhost:7331` 。</span><span class="sxs-lookup"><span data-stu-id="76357-124">For example, if your site is running on `localhost:7331` enter `localhost:7331`.</span></span>  
1.  <span data-ttu-id="76357-125">选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="76357-125">Select **Add**.</span></span>  
    
<span data-ttu-id="76357-126">端口转发现已设置。</span><span class="sxs-lookup"><span data-stu-id="76357-126">Port forwarding is now set up.</span></span>  <span data-ttu-id="76357-127">在 " **检查设备** " 对话框内的设备上的选项卡上，查看端口的状态指示器。</span><span class="sxs-lookup"><span data-stu-id="76357-127">See the status indicator for the port forward on the tab on your device within the **Inspect Devices** dialog.</span></span>  

:::image type="complex" source="../media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png" alt-text="添加端口转发规则" lightbox="../media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png":::
   <span data-ttu-id="76357-129">端口转发状态</span><span class="sxs-lookup"><span data-stu-id="76357-129">Port forwarding status</span></span>  
:::image-end:::  

<span data-ttu-id="76357-130">若要查看内容，请在 Android 设备上打开 Microsoft Edge，然后转到在 `localhost` " **设备端口** " 字段中指定的端口。</span><span class="sxs-lookup"><span data-stu-id="76357-130">To view the content, open up Microsoft Edge on your Android device and go to the `localhost` port that you specified in the **Device port** field.</span></span>  <span data-ttu-id="76357-131">例如，如果您 `5000` 在 "" 字段中输入，请访问 `localhost:5000` 。</span><span class="sxs-lookup"><span data-stu-id="76357-131">For example, if you entered `5000` in the field, visit `localhost:5000`.</span></span>  

## <span data-ttu-id="76357-132">映射到自定义本地域</span><span class="sxs-lookup"><span data-stu-id="76357-132">Map to custom local domains</span></span>   

<span data-ttu-id="76357-133">自定义域映射使你能够从使用自定义域的开发计算机上的 web 服务器查看 Android 设备上的内容。</span><span class="sxs-lookup"><span data-stu-id="76357-133">Custom domain mapping enables you to view content on an Android device from a web server on your development machine that is using a custom domain.</span></span>  

<span data-ttu-id="76357-134">例如，假设您的网站使用的第三方 JavaScript 库仅适用于域 `microsoft-edge.devtools` 。</span><span class="sxs-lookup"><span data-stu-id="76357-134">For example, suppose that your site uses a third-party JavaScript library that only works on the domain `microsoft-edge.devtools`.</span></span>  <span data-ttu-id="76357-135">因此，你在开发计算机上的文件中创建一个条目， `hosts` 以便将此域映射到 `localhost` \ (例如 `127.0.0.1 microsoft-edge.devtools` \ ) 。</span><span class="sxs-lookup"><span data-stu-id="76357-135">So, you create an entry in your `hosts` file on your development machine to map this domain to `localhost` \(for example, `127.0.0.1 microsoft-edge.devtools`\).</span></span>  <span data-ttu-id="76357-136">设置自定义域映射和端口转发后，在 Android 设备上的 URL 处查看网站 `microsoft-edge.devtools` 。</span><span class="sxs-lookup"><span data-stu-id="76357-136">After setting up custom domain mapping and port forwarding, view the site on your Android device at the URL `microsoft-edge.devtools`.</span></span>  

### <span data-ttu-id="76357-137">设置到代理服务器的端口转发</span><span class="sxs-lookup"><span data-stu-id="76357-137">Set up port forwarding to proxy server</span></span>  

<span data-ttu-id="76357-138">若要映射自定义域，必须在开发计算机上运行代理服务器。</span><span class="sxs-lookup"><span data-stu-id="76357-138">To map a custom domain you must run a proxy server on your development machine.</span></span>  <span data-ttu-id="76357-139">代理服务器的示例包括 [Charles][CharlesWebDebuggingProxy]、 [Squid][SquidOptimisingWebDelivery]和 [Fiddler][FiddlerWebDebuggingProxy]。</span><span class="sxs-lookup"><span data-stu-id="76357-139">Examples of proxy servers are [Charles][CharlesWebDebuggingProxy], [Squid][SquidOptimisingWebDelivery], and [Fiddler][FiddlerWebDebuggingProxy].</span></span>  

<span data-ttu-id="76357-140">若要设置到代理的端口转发，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="76357-140">To set up port forwarding to a proxy:</span></span>  

1.  <span data-ttu-id="76357-141">运行代理服务器并记录它所使用的端口。</span><span class="sxs-lookup"><span data-stu-id="76357-141">Run the proxy server and record the port that it is using.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="76357-142">代理服务器和 web 服务器必须在不同的端口上运行。</span><span class="sxs-lookup"><span data-stu-id="76357-142">The proxy server and your web server must run on different ports.</span></span>  
    
1.  <span data-ttu-id="76357-143">设置将 [端口转发](#set-up-port-forwarding) 到 Android 设备。</span><span class="sxs-lookup"><span data-stu-id="76357-143">Set up [port forwarding](#set-up-port-forwarding) to your Android device.</span></span>  <span data-ttu-id="76357-144">对于 " **本地地址** " 字段，输入 `localhost:` 后跟代理服务器运行的端口。</span><span class="sxs-lookup"><span data-stu-id="76357-144">For the **local address** field, enter `localhost:` followed by the port that your proxy server is running on.</span></span>  <span data-ttu-id="76357-145">例如，如果它在端口上运行 `8000` ，请访问 `localhost:8000` 。</span><span class="sxs-lookup"><span data-stu-id="76357-145">For example, if it is running on port `8000`, visit `localhost:8000`.</span></span>  <span data-ttu-id="76357-146">在 " **设备端口** " 字段中输入希望 Android 设备侦听的号码，例如 `3333` 。</span><span class="sxs-lookup"><span data-stu-id="76357-146">In the **device port** field enter the number that you want your Android device to listen on, such as `3333`.</span></span>  
    
### <span data-ttu-id="76357-147">在设备上配置代理服务器设置</span><span class="sxs-lookup"><span data-stu-id="76357-147">Configure proxy settings on your device</span></span>  

<span data-ttu-id="76357-148">接下来，你需要将 Android 设备配置为与代理服务器通信。</span><span class="sxs-lookup"><span data-stu-id="76357-148">Next, you need to configure your Android device to communicate with the proxy server.</span></span>  

1.  <span data-ttu-id="76357-149">在 Android 设备上，转到 "**设置**  >  **wi-fi**"。</span><span class="sxs-lookup"><span data-stu-id="76357-149">On your Android device go to **Settings** > **Wi-Fi**.</span></span>  
1.  <span data-ttu-id="76357-150">长按您当前连接的网络的名称。</span><span class="sxs-lookup"><span data-stu-id="76357-150">Long-press the name of the network to which you are currently connected.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="76357-151">代理设置适用于每个网络。</span><span class="sxs-lookup"><span data-stu-id="76357-151">Proxy settings apply per network.</span></span>  
    
1.  <span data-ttu-id="76357-152">选择 " **修改网络**"。</span><span class="sxs-lookup"><span data-stu-id="76357-152">Select **Modify network**.</span></span>  
1.  <span data-ttu-id="76357-153">选择 " **高级选项**"。</span><span class="sxs-lookup"><span data-stu-id="76357-153">Select **Advanced options**.</span></span>  <span data-ttu-id="76357-154">将显示代理设置。</span><span class="sxs-lookup"><span data-stu-id="76357-154">The proxy settings display.</span></span>  
1.  <span data-ttu-id="76357-155">选择 " **代理** " 菜单，然后选择 " **手动**"。</span><span class="sxs-lookup"><span data-stu-id="76357-155">Select the **Proxy** menu and select **Manual**.</span></span>  
1.  <span data-ttu-id="76357-156">对于 " **代理主机名** " 字段，请输入 `localhost` 。</span><span class="sxs-lookup"><span data-stu-id="76357-156">For the **Proxy hostname** field, enter `localhost`.</span></span>  
1.  <span data-ttu-id="76357-157">对于 " **代理服务器端口** " 字段，输入您在上一节中为 " **设备端口** " 输入的端口号。</span><span class="sxs-lookup"><span data-stu-id="76357-157">For the **Proxy port** field, enter the port number that you entered for **device port** in the previous section.</span></span>  
1.  <span data-ttu-id="76357-158">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="76357-158">Select **Save**.</span></span>  
    
<span data-ttu-id="76357-159">通过这些设置，你的设备会将其所有请求转发到你的开发计算机上的代理。</span><span class="sxs-lookup"><span data-stu-id="76357-159">With these settings, your device forwards all of its requests to the proxy on your development machine.</span></span>  <span data-ttu-id="76357-160">代理代表你的设备发出请求，因此对自定义本地域的请求已正确解析。</span><span class="sxs-lookup"><span data-stu-id="76357-160">The proxy makes requests on behalf of your device, so requests to your customized local domain are properly resolved.</span></span>  

<span data-ttu-id="76357-161">现在，在 Android 设备上访问自定义域，就像在开发计算机上一样。</span><span class="sxs-lookup"><span data-stu-id="76357-161">Now access custom domains on your Android device just like on the development machine.</span></span>  

<span data-ttu-id="76357-162">如果您的 web 服务器在非标准端口上运行，请记住在从 Android 设备请求内容时指定该端口。</span><span class="sxs-lookup"><span data-stu-id="76357-162">If your web server is running off of a non-standard port, remember to specify the port when requesting the content from your Android device.</span></span>  <span data-ttu-id="76357-163">例如，如果 web 服务器在端口上使用自定义域 `microsoft-edge.devtools` `7331` ，则当您从 Android 设备查看网站时，应使用 URL `microsoft-edge.devtools:7331` 。</span><span class="sxs-lookup"><span data-stu-id="76357-163">For example, if your web server is using the custom domain `microsoft-edge.devtools` on port `7331`, when you view the site from your Android device you should be using the URL `microsoft-edge.devtools:7331`.</span></span>  

> [!TIP]
> <span data-ttu-id="76357-164">若要恢复正常浏览，请记住在从开发计算机断开连接后还原 Android 设备上的代理设置。</span><span class="sxs-lookup"><span data-stu-id="76357-164">To resume normal browsing, remember to revert the proxy settings on your Android device after you disconnect from the development machine.</span></span>  

<!--  
  


-->  
<!-- links -->  

[RemoteDebuggingGettingStarted]: ./index.md "开始使用 "远程调试 Android 设备" |Microsoft 文档"  

[CharlesWebDebuggingProxy]: https://www.charlesproxy.com "Charles Web 调试代理"  

[SquidOptimisingWebDelivery]: https://www.squid-cache.org "squid：优化 Web 送达"  

[FiddlerWebDebuggingProxy]: https://www.telerik.com/fiddler "Fiddler-免费 Web 调试代理"  

> [!NOTE]
> <span data-ttu-id="76357-169">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="76357-169">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="76357-170">原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/local-server) 找到，并由 [Kayce Basques][KayceBasques] (技术作者、Chrome DevTools \ & Lighthouse \ ) 和 [Meggin Kearney][MegginKearney] \ (技术作者 \ ) 创作。</span><span class="sxs-lookup"><span data-stu-id="76357-170">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/local-server) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="76357-172">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="76357-172">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
