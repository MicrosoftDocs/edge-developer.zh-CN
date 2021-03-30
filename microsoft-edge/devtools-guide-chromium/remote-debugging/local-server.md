---
description: 在开发计算机 Web 服务器上承载网站，然后从 Android 设备访问内容。
title: 访问本地服务器
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/25/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge,web 开发,f12 工具,开发工具
ms.openlocfilehash: 51ef0d951d587d310b6474698924d9f87cf68607
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461260"
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
# <a name="access-local-servers"></a><span data-ttu-id="85003-104">访问本地服务器</span><span class="sxs-lookup"><span data-stu-id="85003-104">Access local servers</span></span>  

<span data-ttu-id="85003-105">在开发计算机 Web 服务器上承载网站，然后从 Android 设备访问内容。</span><span class="sxs-lookup"><span data-stu-id="85003-105">Host a site on a development machine web server, then access the content from an Android device.</span></span>  

<span data-ttu-id="85003-106">使用 USB 电缆和 Microsoft Edge DevTools，从开发计算机运行站点，然后在 Android 设备上查看站点。</span><span class="sxs-lookup"><span data-stu-id="85003-106">With a USB cable and Microsoft Edge DevTools, run a site from a development machine and then view the site on an Android device.</span></span>  

### <a name="summary"></a><span data-ttu-id="85003-107">摘要</span><span class="sxs-lookup"><span data-stu-id="85003-107">Summary</span></span>  

*   <span data-ttu-id="85003-108">通过端口转发，您可以查看在 Android 设备上开发计算机上运行的 Web 服务器托管的内容。</span><span class="sxs-lookup"><span data-stu-id="85003-108">Port forwarding enables you to view content hosted by the web server running in your development machine on your Android device.</span></span>  
*   <span data-ttu-id="85003-109">如果 Web 服务器使用的是自定义域，请设置 Android 设备以使用自定义域映射访问该域中的内容。</span><span class="sxs-lookup"><span data-stu-id="85003-109">If your web server is using a custom domain, set up your Android device to access the content at that domain with custom domain mapping.</span></span>  

## <a name="set-up-port-forwarding"></a><span data-ttu-id="85003-110">设置端口转发</span><span class="sxs-lookup"><span data-stu-id="85003-110">Set up port forwarding</span></span>  

<span data-ttu-id="85003-111">通过端口转发，Android 设备可以访问托管在开发计算机中运行的 Web 服务器上的内容。</span><span class="sxs-lookup"><span data-stu-id="85003-111">Port forwarding enables your Android device to access content that is being hosted on the web server running in your development machine.</span></span>  <span data-ttu-id="85003-112">端口转发的工作原理是，在 Android 设备上创建一个可映射到开发计算机上 TCP 端口的侦听 TCP 端口。</span><span class="sxs-lookup"><span data-stu-id="85003-112">Port forwarding works by creating a listening TCP port on your Android device that maps to a TCP port on your development machine.</span></span>  <span data-ttu-id="85003-113">端口之间的流量通过 Android 设备和开发计算机之间的 USB 连接传输，因此连接不依赖于网络配置。</span><span class="sxs-lookup"><span data-stu-id="85003-113">Traffic between the ports travel through the USB connection between your Android device and development machine, so the connection does not depend on your network configuration.</span></span>  

<span data-ttu-id="85003-114">启用端口转发：</span><span class="sxs-lookup"><span data-stu-id="85003-114">To enable port forwarding:</span></span>  

1.  <span data-ttu-id="85003-115">在 [开发计算机和][RemoteDebuggingGettingStarted] Android 设备之间设置远程调试。</span><span class="sxs-lookup"><span data-stu-id="85003-115">Set up [remote debugging][RemoteDebuggingGettingStarted] between your development machine and your Android device.</span></span>  <span data-ttu-id="85003-116">完成后，Android 设备应显示在"检查设备"对话框和"已连接状态"指示器的左侧菜单中。</span><span class="sxs-lookup"><span data-stu-id="85003-116">When you are finished, your Android device should be displayed in the left-hand menu of the **Inspect Devices** dialog and a **Connected** status indicator.</span></span>  
1.  <span data-ttu-id="85003-117">在 **DevTools 中的** "检查设备"对话框中，启用 **端口转发**。</span><span class="sxs-lookup"><span data-stu-id="85003-117">In the **Inspect Devices** dialog in DevTools, enable **Port forwarding**.</span></span>  
1.  <span data-ttu-id="85003-118">选择 **"添加规则"。**</span><span class="sxs-lookup"><span data-stu-id="85003-118">Choose **Add rule**.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png" alt-text="添加端口转发规则" lightbox="../media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png":::
       <span data-ttu-id="85003-120">添加端口转发规则</span><span class="sxs-lookup"><span data-stu-id="85003-120">Adding a port forwarding rule</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="85003-121">在 **左侧的设备端口** 文本框中，输入你想要从该端口号访问 `localhost` Android 设备上的站点。</span><span class="sxs-lookup"><span data-stu-id="85003-121">In the **Device port** textbox on the left, enter the `localhost` port number from which you want to be able to access the site on your Android device.</span></span>  <span data-ttu-id="85003-122">例如，如果要从 输入 访问 `localhost:5000` 网站 `5000` 。</span><span class="sxs-lookup"><span data-stu-id="85003-122">For example, if you wanted to access the site from `localhost:5000` enter `5000`.</span></span>  
1.  <span data-ttu-id="85003-123">在右侧 **"** 本地地址"文本框中，输入您的网站托管在开发计算机中运行的 Web 服务器的 IP 地址或主机名，后跟端口号。</span><span class="sxs-lookup"><span data-stu-id="85003-123">In the **Local address** textbox on the right, enter the IP address or hostname on which your site is hosted on the web server running in your development machine, followed by the port number.</span></span>  <span data-ttu-id="85003-124">例如，如果您的网站在 中运行，请输入 `localhost:7331` `localhost:7331` 。</span><span class="sxs-lookup"><span data-stu-id="85003-124">For example, if your site is running on `localhost:7331` enter `localhost:7331`.</span></span>  
1.  <span data-ttu-id="85003-125">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="85003-125">Choose **Add**.</span></span>  
    
<span data-ttu-id="85003-126">现已设置端口转发。</span><span class="sxs-lookup"><span data-stu-id="85003-126">Port forwarding is now set up.</span></span>  <span data-ttu-id="85003-127">查看"检查设备"对话框中设备选项卡上端口向前 **的状态** 指示器。</span><span class="sxs-lookup"><span data-stu-id="85003-127">Review the status indicator for the port forward on the tab on your device within the **Inspect Devices** dialog.</span></span>  

:::image type="complex" source="../media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png" alt-text="端口转发状态" lightbox="../media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png":::
   <span data-ttu-id="85003-129">端口转发状态</span><span class="sxs-lookup"><span data-stu-id="85003-129">Port forwarding status</span></span>  
:::image-end:::  

<span data-ttu-id="85003-130">若要查看内容，请打开 Android 设备上的 Microsoft Edge，然后转到在"设备端口"字段中 `localhost` **指定的端口** 。</span><span class="sxs-lookup"><span data-stu-id="85003-130">To view the content, open up Microsoft Edge on your Android device and go to the `localhost` port that you specified in the **Device port** field.</span></span>  <span data-ttu-id="85003-131">例如，如果在 字段中输入 `5000` ，请访问 `localhost:5000` 。</span><span class="sxs-lookup"><span data-stu-id="85003-131">For example, if you entered `5000` in the field, visit `localhost:5000`.</span></span>  

## <a name="map-to-custom-local-domains"></a><span data-ttu-id="85003-132">映射到自定义本地域</span><span class="sxs-lookup"><span data-stu-id="85003-132">Map to custom local domains</span></span>  

<span data-ttu-id="85003-133">通过自定义域映射，可以在使用自定义域的开发计算机上通过 Web 服务器查看 Android 设备上的内容。</span><span class="sxs-lookup"><span data-stu-id="85003-133">Custom domain mapping enables you to view content on an Android device from a web server on your development machine that is using a custom domain.</span></span>  

<span data-ttu-id="85003-134">例如，假定您的网站使用仅在域 上工作的第三方 JavaScript 库 `microsoft-edge.devtools` 。</span><span class="sxs-lookup"><span data-stu-id="85003-134">For example, suppose that your site uses a third-party JavaScript library that only works on the domain `microsoft-edge.devtools`.</span></span>  <span data-ttu-id="85003-135">因此，在开发计算机上在文件中创建一个条目，以将此域映射到 `hosts` `localhost` \(例如 `127.0.0.1 microsoft-edge.devtools` \) 。</span><span class="sxs-lookup"><span data-stu-id="85003-135">So, you create an entry in your `hosts` file on your development machine to map this domain to `localhost` \(for example, `127.0.0.1 microsoft-edge.devtools`\).</span></span>  <span data-ttu-id="85003-136">设置自定义域映射和端口转发后，在 Android 设备上通过 URL 查看网站 `microsoft-edge.devtools` 。</span><span class="sxs-lookup"><span data-stu-id="85003-136">After setting up custom domain mapping and port forwarding, view the site on your Android device at the URL `microsoft-edge.devtools`.</span></span>  

### <a name="set-up-port-forwarding-to-proxy-server"></a><span data-ttu-id="85003-137">设置到代理服务器的端口转发</span><span class="sxs-lookup"><span data-stu-id="85003-137">Set up port forwarding to proxy server</span></span>  

<span data-ttu-id="85003-138">若要映射自定义域，必须在开发计算机上运行代理服务器。</span><span class="sxs-lookup"><span data-stu-id="85003-138">To map a custom domain you must run a proxy server on your development machine.</span></span>  <span data-ttu-id="85003-139">代理服务器的示例包括[，即，用户][CharlesWebDebuggingProxy][、Squid 和][SquidOptimisingWebDelivery] [Fiddler。][FiddlerWebDebuggingProxy]</span><span class="sxs-lookup"><span data-stu-id="85003-139">Examples of proxy servers are [Charles][CharlesWebDebuggingProxy], [Squid][SquidOptimisingWebDelivery], and [Fiddler][FiddlerWebDebuggingProxy].</span></span>  

<span data-ttu-id="85003-140">设置到代理的端口转发：</span><span class="sxs-lookup"><span data-stu-id="85003-140">To set up port forwarding to a proxy:</span></span>  

1.  <span data-ttu-id="85003-141">运行代理服务器并记录它使用的端口。</span><span class="sxs-lookup"><span data-stu-id="85003-141">Run the proxy server and record the port that it is using.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="85003-142">代理服务器和 Web 服务器必须在不同的端口上运行。</span><span class="sxs-lookup"><span data-stu-id="85003-142">The proxy server and your web server must run on different ports.</span></span>  
    
1.  <span data-ttu-id="85003-143">设置 [到 Android 设备的](#set-up-port-forwarding) 端口转发。</span><span class="sxs-lookup"><span data-stu-id="85003-143">Set up [port forwarding](#set-up-port-forwarding) to your Android device.</span></span>  <span data-ttu-id="85003-144">对于 **"本地地址"** 字段，输入后跟 `localhost:` 运行代理服务器的端口。</span><span class="sxs-lookup"><span data-stu-id="85003-144">For the **local address** field, enter `localhost:` followed by the port that your proxy server is running on.</span></span>  <span data-ttu-id="85003-145">例如，如果它在端口上运行， `8000` 请导航到 `localhost:8000` 。</span><span class="sxs-lookup"><span data-stu-id="85003-145">For example, if it is running on port `8000`, navigate to `localhost:8000`.</span></span>  <span data-ttu-id="85003-146">在 **设备端口** 字段中，输入你想要 Android 设备侦听的号码，例如 `3333` 。</span><span class="sxs-lookup"><span data-stu-id="85003-146">In the **device port** field enter the number that you want your Android device to listen on, such as `3333`.</span></span>  
    
### <a name="configure-proxy-settings-on-your-device"></a><span data-ttu-id="85003-147">在设备上配置代理设置</span><span class="sxs-lookup"><span data-stu-id="85003-147">Configure proxy settings on your device</span></span>  

<span data-ttu-id="85003-148">接下来，你需要将 Android 设备配置为与代理服务器通信。</span><span class="sxs-lookup"><span data-stu-id="85003-148">Next, you need to configure your Android device to communicate with the proxy server.</span></span>  

1.  <span data-ttu-id="85003-149">在 Android 设备上，导航到"**设置**  >  **""WLAN"。**</span><span class="sxs-lookup"><span data-stu-id="85003-149">On your Android device, navigate to **Settings** > **Wi-Fi**.</span></span>  
1.  <span data-ttu-id="85003-150">长按当前连接到的网络的名称。</span><span class="sxs-lookup"><span data-stu-id="85003-150">Long-press the name of the network to which you are currently connected.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="85003-151">代理设置适用于每个网络。</span><span class="sxs-lookup"><span data-stu-id="85003-151">Proxy settings apply per network.</span></span>  
    
1.  <span data-ttu-id="85003-152">选择 **"修改网络"。**</span><span class="sxs-lookup"><span data-stu-id="85003-152">Choose **Modify network**.</span></span>  
1.  <span data-ttu-id="85003-153">选择 **高级选项**。</span><span class="sxs-lookup"><span data-stu-id="85003-153">Choose **Advanced options**.</span></span>  <span data-ttu-id="85003-154">将显示代理设置。</span><span class="sxs-lookup"><span data-stu-id="85003-154">The proxy settings display.</span></span>  
1.  <span data-ttu-id="85003-155">选择代理 **菜单** ， **然后选择手动**。</span><span class="sxs-lookup"><span data-stu-id="85003-155">Choose the **Proxy** menu and choose **Manual**.</span></span>  
1.  <span data-ttu-id="85003-156">对于" **代理主机名"** 字段，输入 `localhost` 。</span><span class="sxs-lookup"><span data-stu-id="85003-156">For the **Proxy hostname** field, enter `localhost`.</span></span>  
1.  <span data-ttu-id="85003-157">对于 **"代理端口** "字段，输入在上一部分中为 **设备端口** 输入的端口号。</span><span class="sxs-lookup"><span data-stu-id="85003-157">For the **Proxy port** field, enter the port number that you entered for **device port** in the previous section.</span></span>  
1.  <span data-ttu-id="85003-158">选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="85003-158">Choose **Save**.</span></span>  
    
<span data-ttu-id="85003-159">借助这些设置，你的设备会将它的所有请求转发到开发计算机上代理。</span><span class="sxs-lookup"><span data-stu-id="85003-159">With these settings, your device forwards all of its requests to the proxy on your development machine.</span></span>  <span data-ttu-id="85003-160">代理代表你的设备提出请求，因此正确解决了对自定义本地域的请求。</span><span class="sxs-lookup"><span data-stu-id="85003-160">The proxy makes requests on behalf of your device, so requests to your customized local domain are properly resolved.</span></span>  

<span data-ttu-id="85003-161">现在访问 Android 设备上的自定义域，就像在开发计算机上一样。</span><span class="sxs-lookup"><span data-stu-id="85003-161">Now access custom domains on your Android device just like on the development machine.</span></span>  

<span data-ttu-id="85003-162">如果 Web 服务器在非标准端口上运行，请记住在从 Android 设备请求内容时指定端口。</span><span class="sxs-lookup"><span data-stu-id="85003-162">If your web server is running off of a non-standard port, remember to specify the port when requesting the content from your Android device.</span></span>  <span data-ttu-id="85003-163">例如，如果你的 Web 服务器在端口上使用自定义域，当你从 Android 设备查看网站时 `microsoft-edge.devtools` `7331` ，你应该使用 URL `microsoft-edge.devtools:7331` 。</span><span class="sxs-lookup"><span data-stu-id="85003-163">For example, if your web server is using the custom domain `microsoft-edge.devtools` on port `7331`, when you view the site from your Android device you should be using the URL `microsoft-edge.devtools:7331`.</span></span>  

> [!TIP]
> <span data-ttu-id="85003-164">若要恢复正常浏览，请记得在断开与开发计算机连接后在 Android 设备上还原代理设置。</span><span class="sxs-lookup"><span data-stu-id="85003-164">To resume normal browsing, remember to revert the proxy settings on your Android device after you disconnect from the development machine.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="85003-165">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="85003-165">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[RemoteDebuggingGettingStarted]: ./index.md "Android 设备远程调试入门 | Microsoft Docs"  

[CharlesWebDebuggingProxy]: https://www.charlesproxy.com "Debugg Web Debugging Proxy"  

[SquidOptimisingWebDelivery]: https://www.squid-cache.org "squid ： Deliverying Web Delivery"  

[FiddlerWebDebuggingProxy]: https://www.telerik.com/fiddler "Fiddler - 免费 Web 调试代理"  

> [!NOTE]
> <span data-ttu-id="85003-170">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="85003-170">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="85003-171">[此处](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/local-server)可以找到原始页面，由 [Kayce Basques][KayceBasques] \（技术写作人员，Chrome DevTools \& Lighthouse\）和 [Meggin Kearney][MegginKearney] \（技术写作人员\）编写。</span><span class="sxs-lookup"><span data-stu-id="85003-171">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/local-server) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![知识共享许可协议][CCby4Image]][CCA4IL]  
<span data-ttu-id="85003-173">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="85003-173">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
