---
description: Host a site on a development machine web server, and then access the content from an Android device.
title: Access Local Servers
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
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





# <span data-ttu-id="2c7a5-104">Access local servers</span><span class="sxs-lookup"><span data-stu-id="2c7a5-104">Access local servers</span></span>   




<span data-ttu-id="2c7a5-105">Host a site on a development machine web server, then access the content from an Android device.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-105">Host a site on a development machine web server, then access the content from an Android device.</span></span>  

<span data-ttu-id="2c7a5-106">With a USB cable and Microsoft Edge DevTools, run a site from a development machine and then view the site on an Android device.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-106">With a USB cable and Microsoft Edge DevTools, run a site from a development machine and then view the site on an Android device.</span></span>  

### <span data-ttu-id="2c7a5-107">Summary</span><span class="sxs-lookup"><span data-stu-id="2c7a5-107">Summary</span></span>  

*   <span data-ttu-id="2c7a5-108">Port forwarding enables you to view content hosted by the web server running in your development machine on your Android device.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-108">Port forwarding enables you to view content hosted by the web server running in your development machine on your Android device.</span></span>  
*   <span data-ttu-id="2c7a5-109">If your web server is using a custom domain, set up your Android device to access the content at that domain with custom domain mapping.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-109">If your web server is using a custom domain, set up your Android device to access the content at that domain with custom domain mapping.</span></span>  

## <span data-ttu-id="2c7a5-110">Set up port forwarding</span><span class="sxs-lookup"><span data-stu-id="2c7a5-110">Set up port forwarding</span></span>   

<span data-ttu-id="2c7a5-111">Port forwarding enables your Android device to access content that is being hosted on the web server running in your development machine.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-111">Port forwarding enables your Android device to access content that is being hosted on the web server running in your development machine.</span></span>  <span data-ttu-id="2c7a5-112">Port forwarding works by creating a listening TCP port on your Android device that maps to a TCP port on your development machine.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-112">Port forwarding works by creating a listening TCP port on your Android device that maps to a TCP port on your development machine.</span></span>  <span data-ttu-id="2c7a5-113">Traffic between the ports travel through the USB connection between your Android device and development machine, so the connection does not depend on your network configuration.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-113">Traffic between the ports travel through the USB connection between your Android device and development machine, so the connection does not depend on your network configuration.</span></span>  

<span data-ttu-id="2c7a5-114">To enable port forwarding:</span><span class="sxs-lookup"><span data-stu-id="2c7a5-114">To enable port forwarding:</span></span>  

1.  <span data-ttu-id="2c7a5-115">Set up [remote debugging][RemoteDebuggingGettingStarted] between your development machine and your Android device.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-115">Set up [remote debugging][RemoteDebuggingGettingStarted] between your development machine and your Android device.</span></span>  <span data-ttu-id="2c7a5-116">When you are finished, you should see your Android device in the left-hand menu of the **Inspect Devices** dialog and a **Connected** status indicator.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-116">When you are finished, you should see your Android device in the left-hand menu of the **Inspect Devices** dialog and a **Connected** status indicator.</span></span>  
1.  <span data-ttu-id="2c7a5-117">In the **Inspect Devices** dialog in DevTools, enable **Port forwarding**.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-117">In the **Inspect Devices** dialog in DevTools, enable **Port forwarding**.</span></span>  
1.  <span data-ttu-id="2c7a5-118">Select **Add rule**.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-118">Select **Add rule**.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png" alt-text="Adding a port forwarding rule" lightbox="../media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png":::
       <span data-ttu-id="2c7a5-120">Adding a port forwarding rule</span><span class="sxs-lookup"><span data-stu-id="2c7a5-120">Adding a port forwarding rule</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2c7a5-121">In the **Device port** textbox on the left, enter the `localhost` port number from which you want to be able to access the site on your Android device.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-121">In the **Device port** textbox on the left, enter the `localhost` port number from which you want to be able to access the site on your Android device.</span></span>  <span data-ttu-id="2c7a5-122">For example, if you wanted to access the site from `localhost:5000` enter `5000`.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-122">For example, if you wanted to access the site from `localhost:5000` enter `5000`.</span></span>  
1.  <span data-ttu-id="2c7a5-123">In the **Local address** textbox on the right, enter the IP address or hostname on which your site is hosted on the web server running in your development machine, followed by the port number.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-123">In the **Local address** textbox on the right, enter the IP address or hostname on which your site is hosted on the web server running in your development machine, followed by the port number.</span></span>  <span data-ttu-id="2c7a5-124">For example, if your site is running on `localhost:7331` enter `localhost:7331`.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-124">For example, if your site is running on `localhost:7331` enter `localhost:7331`.</span></span>  
1.  <span data-ttu-id="2c7a5-125">Select **Add**.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-125">Select **Add**.</span></span>  
    
<span data-ttu-id="2c7a5-126">Port forwarding is now set up.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-126">Port forwarding is now set up.</span></span>  <span data-ttu-id="2c7a5-127">See the status indicator for the port forward on the tab on your device within the **Inspect Devices** dialog.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-127">See the status indicator for the port forward on the tab on your device within the **Inspect Devices** dialog.</span></span>  

:::image type="complex" source="../media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png" alt-text="Adding a port forwarding rule" lightbox="../media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png":::
   <span data-ttu-id="2c7a5-129">Port forwarding status</span><span class="sxs-lookup"><span data-stu-id="2c7a5-129">Port forwarding status</span></span>  
:::image-end:::  

<span data-ttu-id="2c7a5-130">To view the content, open up Microsoft Edge on your Android device and go to the `localhost` port that you specified in the **Device port** field.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-130">To view the content, open up Microsoft Edge on your Android device and go to the `localhost` port that you specified in the **Device port** field.</span></span>  <span data-ttu-id="2c7a5-131">For example, if you entered `5000` in the field, visit `localhost:5000`.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-131">For example, if you entered `5000` in the field, visit `localhost:5000`.</span></span>  

## <span data-ttu-id="2c7a5-132">Map to custom local domains</span><span class="sxs-lookup"><span data-stu-id="2c7a5-132">Map to custom local domains</span></span>   

<span data-ttu-id="2c7a5-133">Custom domain mapping enables you to view content on an Android device from a web server on your development machine that is using a custom domain.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-133">Custom domain mapping enables you to view content on an Android device from a web server on your development machine that is using a custom domain.</span></span>  

<span data-ttu-id="2c7a5-134">For example, suppose that your site uses a third-party JavaScript library that only works on the domain `microsoft-edge.devtools`.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-134">For example, suppose that your site uses a third-party JavaScript library that only works on the domain `microsoft-edge.devtools`.</span></span>  <span data-ttu-id="2c7a5-135">So, you create an entry in your `hosts` file on your development machine to map this domain to `localhost` \(for example, `127.0.0.1 microsoft-edge.devtools`\).</span><span class="sxs-lookup"><span data-stu-id="2c7a5-135">So, you create an entry in your `hosts` file on your development machine to map this domain to `localhost` \(for example, `127.0.0.1 microsoft-edge.devtools`\).</span></span>  <span data-ttu-id="2c7a5-136">After setting up custom domain mapping and port forwarding, view the site on your Android device at the URL `microsoft-edge.devtools`.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-136">After setting up custom domain mapping and port forwarding, view the site on your Android device at the URL `microsoft-edge.devtools`.</span></span>  

### <span data-ttu-id="2c7a5-137">Set up port forwarding to proxy server</span><span class="sxs-lookup"><span data-stu-id="2c7a5-137">Set up port forwarding to proxy server</span></span>  

<span data-ttu-id="2c7a5-138">To map a custom domain you must run a proxy server on your development machine.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-138">To map a custom domain you must run a proxy server on your development machine.</span></span>  <span data-ttu-id="2c7a5-139">Examples of proxy servers are [Charles][CharlesWebDebuggingProxy], [Squid][SquidOptimisingWebDelivery], and [Fiddler][FiddlerWebDebuggingProxy].</span><span class="sxs-lookup"><span data-stu-id="2c7a5-139">Examples of proxy servers are [Charles][CharlesWebDebuggingProxy], [Squid][SquidOptimisingWebDelivery], and [Fiddler][FiddlerWebDebuggingProxy].</span></span>  

<span data-ttu-id="2c7a5-140">To set up port forwarding to a proxy:</span><span class="sxs-lookup"><span data-stu-id="2c7a5-140">To set up port forwarding to a proxy:</span></span>  

1.  <span data-ttu-id="2c7a5-141">Run the proxy server and record the port that it is using.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-141">Run the proxy server and record the port that it is using.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="2c7a5-142">The proxy server and your web server must run on different ports.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-142">The proxy server and your web server must run on different ports.</span></span>  
    
1.  <span data-ttu-id="2c7a5-143">Set up [port forwarding](#set-up-port-forwarding) to your Android device.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-143">Set up [port forwarding](#set-up-port-forwarding) to your Android device.</span></span>  <span data-ttu-id="2c7a5-144">For the **local address** field, enter `localhost:` followed by the port that your proxy server is running on.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-144">For the **local address** field, enter `localhost:` followed by the port that your proxy server is running on.</span></span>  <span data-ttu-id="2c7a5-145">For example, if it is running on port `8000`, visit `localhost:8000`.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-145">For example, if it is running on port `8000`, visit `localhost:8000`.</span></span>  <span data-ttu-id="2c7a5-146">In the **device port** field enter the number that you want your Android device to listen on, such as `3333`.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-146">In the **device port** field enter the number that you want your Android device to listen on, such as `3333`.</span></span>  
    
### <span data-ttu-id="2c7a5-147">Configure proxy settings on your device</span><span class="sxs-lookup"><span data-stu-id="2c7a5-147">Configure proxy settings on your device</span></span>  

<span data-ttu-id="2c7a5-148">Next, you need to configure your Android device to communicate with the proxy server.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-148">Next, you need to configure your Android device to communicate with the proxy server.</span></span>  

1.  <span data-ttu-id="2c7a5-149">On your Android device go to **Settings** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-149">On your Android device go to **Settings** > **Wi-Fi**.</span></span>  
1.  <span data-ttu-id="2c7a5-150">Long-press the name of the network to which you are currently connected.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-150">Long-press the name of the network to which you are currently connected.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="2c7a5-151">Proxy settings apply per network.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-151">Proxy settings apply per network.</span></span>  
    
1.  <span data-ttu-id="2c7a5-152">Select **Modify network**.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-152">Select **Modify network**.</span></span>  
1.  <span data-ttu-id="2c7a5-153">Select **Advanced options**.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-153">Select **Advanced options**.</span></span>  <span data-ttu-id="2c7a5-154">The proxy settings display.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-154">The proxy settings display.</span></span>  
1.  <span data-ttu-id="2c7a5-155">Select the **Proxy** menu and select **Manual**.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-155">Select the **Proxy** menu and select **Manual**.</span></span>  
1.  <span data-ttu-id="2c7a5-156">For the **Proxy hostname** field, enter `localhost`.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-156">For the **Proxy hostname** field, enter `localhost`.</span></span>  
1.  <span data-ttu-id="2c7a5-157">For the **Proxy port** field, enter the port number that you entered for **device port** in the previous section.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-157">For the **Proxy port** field, enter the port number that you entered for **device port** in the previous section.</span></span>  
1.  <span data-ttu-id="2c7a5-158">Select **Save**.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-158">Select **Save**.</span></span>  
    
<span data-ttu-id="2c7a5-159">With these settings, your device forwards all of its requests to the proxy on your development machine.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-159">With these settings, your device forwards all of its requests to the proxy on your development machine.</span></span>  <span data-ttu-id="2c7a5-160">The proxy makes requests on behalf of your device, so requests to your customized local domain are properly resolved.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-160">The proxy makes requests on behalf of your device, so requests to your customized local domain are properly resolved.</span></span>  

<span data-ttu-id="2c7a5-161">Now access custom domains on your Android device just like on the development machine.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-161">Now access custom domains on your Android device just like on the development machine.</span></span>  

<span data-ttu-id="2c7a5-162">If your web server is running off of a non-standard port, remember to specify the port when requesting the content from your Android device.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-162">If your web server is running off of a non-standard port, remember to specify the port when requesting the content from your Android device.</span></span>  <span data-ttu-id="2c7a5-163">For example, if your web server is using the custom domain `microsoft-edge.devtools` on port `7331`, when you view the site from your Android device you should be using the URL `microsoft-edge.devtools:7331`.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-163">For example, if your web server is using the custom domain `microsoft-edge.devtools` on port `7331`, when you view the site from your Android device you should be using the URL `microsoft-edge.devtools:7331`.</span></span>  

> [!TIP]
> <span data-ttu-id="2c7a5-164">To resume normal browsing, remember to revert the proxy settings on your Android device after you disconnect from the development machine.</span><span class="sxs-lookup"><span data-stu-id="2c7a5-164">To resume normal browsing, remember to revert the proxy settings on your Android device after you disconnect from the development machine.</span></span>  

<!--  
  


-->  
<!-- links -->  

[RemoteDebuggingGettingStarted]: ./index.md "Get started with remote debugging Android devices | Microsoft Docs"  

[CharlesWebDebuggingProxy]: https://www.charlesproxy.com "Charles Web Debugging Proxy"  

[SquidOptimisingWebDelivery]: https://www.squid-cache.org "squid : Optimising Web Delivery"  

[FiddlerWebDebuggingProxy]: https://www.telerik.com/fiddler "Fiddler - Free Web Debugging Proxy"  

> [!NOTE]
> <span data-ttu-id="2c7a5-169">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="2c7a5-169">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="2c7a5-170">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/local-server) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span><span class="sxs-lookup"><span data-stu-id="2c7a5-170">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/local-server) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="2c7a5-172">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="2c7a5-172">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
