---
description: 本文提供有关用户代理Microsoft Edge提示和用户代理字符串的文档
title: 如何检测Microsoft Edge网站中的内容
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/19/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， 兼容性， Web 平台， 用户代理字符串， ua 字符串， ua 替代， 用户代理客户端提示， 用户代理客户端提示， ua 客户端提示， ua ch
ms.openlocfilehash: 1957bb5bd33d9d921d8a12e16a4a52a23836027b
ms.sourcegitcommit: e90bbc210b5d510004bbc2145d49e14fe72ed54b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "11578775"
---
# <a name="how-to-detect-microsoft-edge-in-your-website"></a>如何检测Microsoft Edge网站中的内容  

浏览器为网站提供检测浏览器信息（如品牌和版本号）的机制。  这些机制还会检测主机操作系统等其他设备特征。  在客户端上支持的两Microsoft Edge是[用户代理客户端提示](#user-agent-client-hints)和[用户代理字符串](#user-agent-string)。  几十年后，User-Agent字符串已过时，并且作为网站兼容性问题的原因具有很长的历史。  相反，Microsoft Edge建议使用改进的机制来检索名为[User-Agent Client Hints 的浏览器信息](#user-agent-client-hints)。  本文概述了检索用户代理Microsoft Edge两种机制。  

|  | 服务器端 | 客户端 |  
|:--- |:--- |:--- | 
| **用户代理客户端提示** \ (推荐\)  | `Sec-CH-UA` HTTPS 标头 | `navigator.userAgentData` JavaScript 方法 |  
| **User-Agent string** \ (legacy\)  | `User-Agent` HTTPS 标头 | `navigator.userAgent` JavaScript 方法 |  

出于以下原因，Microsoft 建议 [尽可能][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection] 使用功能检测。  

*   提高代码可维护性。  
*   减少代码错误。  
*   减少代码中断（由对字符串User-Agent更改。  
    
当[功能][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection]检测不适用并且必须使用用户代理检测时，使用以下格式检测 Microsoft Edge 和 Android 上的Windows代理。  

## <a name="user-agent-client-hints"></a>User-Agent客户端提示  

从 Microsoft Edge版本 90 开始，以更简洁、更隐私的方式访问浏览器信息。  

### <a name="user-agent-client-hints-https-header"></a>User-Agent客户端提示 HTTPS 标头  

默认情况下，Chromium包括 Microsoft Edge以 `Accept-CH-UA` 以下格式发送响应头。  

```https
Sec-CH-UA: "Chromium";v="91", "Microsoft Edge";v="91","Dummy;Browser Brand";v="99"
Sec-CH-UA-Mobile: ?0
```  

> [!NOTE]
> 客户端提示仅使用 通过安全连接发送 `HTTPS` 。  

默认情况下发送以下低向异性提示。  如果需要访问更多信息，请发送以下请求标头之一。  

#### <a name="user-agent-request-and-response-headers"></a>User-Agent请求和响应头  

| 请求头 | 示例响应值 |  
|:--- |:--- |  
| `Sec-CH-UA` | `"Chromium";v="91", "Microsoft Edge";v="91","GREASE";v="99"` |  
| `Sec-CH-UA-Mobile` | `false` |  
| `Sec-CH-UA-Full-Version` | `91.0.866.0` |  
| `Sec-CH-UA-Platform` | `Windows` |  
| `Sec-CH-UA Platform-Version` | `10.0` |  
| `Sec-CH-UA-Arch` | `x86` |  
| `Sec-CH-UA-Model` |  |  

### <a name="user-agent-client-hints-javascript-api"></a>User-Agent客户端提示 JavaScript API  

中的默认响应 `navigator.userAgentData` 值采用以下格式。  

```javascript
{ brands: [ {brand: "Chromium","version":"91"}, {brand: "Microsoft Edge","version":"91"}, {brand: "GREASE","version":"99"}, ]
mobile: false }
```  

如果需要访问更多详细信息，请使用 [getHighEntropyValues ][GithubWicgUaClientHintsGethighentropyvalues] () 方法。  

:::row:::
   :::column span="":::
      以下代码段发送请求。  
   :::column-end:::
   :::column span="":::
      接收以下响应。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      ```javascript
         navigator.userAgentData.getHighEntropyValues(
             ["architecture", "model", "platform", "platformVersion", "uaFullVersion"])
             .then(ua => { console.log(ua) });
      ```  
   :::column-end:::
   :::column span="":::
      ```javascript
      {architecture: "x86", 
      model: "", 
      platform: "Windows", 
      platformVersion: "10.0", 
      uaFullVersion: "92.0.866.0"}
      ```  
   :::column-end:::
:::row-end:::  

## <a name="recommended-uses-of-user-agent-client-hints"></a>客户端提示User-Agent用法  

品牌集和关联的显示顺序会随着时间的推移而改变，因此你绝不应该将索引硬编码为返回的品牌数组。  为了帮助确保尽早在网站中发现类似问题，浏览器包含的品牌值会随着时间的推移而更改，并因常见字符串分析问题而格式化 `GREASE` 为中断。  

如果阻止使用功能检测，请不要使用[][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection]基于 Chromium 的已知浏览器的硬编码列表进行验证。  硬编码浏览器名称的示例包括 `Microsoft Edge` 和 `Google Chrome` 。  功能 [检测不适用][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection] 的原因可能包括以下情况。  

*   必须避免在Chromium版本中修复错误，并且受影响的浏览器很难在品牌和版本验证之外检测到。  
    
相反，你应该验证品牌， `Chromium` 以确保你的检测适用于所有受影响的Chromium浏览器。  


```javascript
function isChromium() {
    for (brand_version_pair in navigator.userAgentData.brands) {
        if (brand_version_pair.brand == "Chromium") {
            return true;
        }
    }
    return false;
}
```  

## <a name="user-agent-string"></a>用户代理字符串  

如果可能，Microsoft 建议根据用户代理字符串Microsoft Edge浏览器检测逻辑的使用。  如果你有一个很好的理由来检测用户代理，Microsoft Edge建议你使用[用户代理](#user-agent-client-hints)客户端提示作为主要检测逻辑。  [用户代理客户端提示](#user-agent-client-hints) 还可以减少所需的分析字符串数。  但是，对于旧引用，以下格式用于User-Agent字符串。  

:::row:::
   :::column span="":::
      在Windows上 `User-Agent` ，HTTP 请求标头采用以下格式。  
   :::column-end:::
   :::column span="":::
      在 Android 上 `User-Agent` ，HTTP 请求标头采用以下格式。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      ```https
      User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.85 Safari/537.36 Edg/90.0.818.46
      ```  
   :::column-end:::
   :::column span="":::
      ```https
      User-Agent: Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.85 Mobile Safari/537.36 Edg/90.0.818.46
      ```  
   :::column-end:::
:::row-end:::  

来自 方法的响应 `navigator.userAgent` 值采用以下格式。  

```javascript
"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4501.0 Safari/537.36 Edg/91.0.866.0"
```  

平台标识符根据使用的操作系统发生变化，版本号也会随着时间推移而递增。  格式与用户代理Chromium，末尾添加 `Edg` 一个新令牌。  Microsoft 选择令牌以避免由字符串引起的兼容性问题，字符串在基于 `Edg` `Edge` EdgeHTML Microsoft Edge旧版浏览器。  令牌 `Edg` 还与 iOS[][WindowsBlogsMsedgedev20171005MicrosoftEdgeIosAndroidDeveloper]和 Android 上使用的现有令牌一致。

## <a name="map-the-user-agent-string-to-browser-name"></a>将用户代理字符串映射到浏览器名称  

将用户代理字符串令牌映射到在代码中使用的更用户可读的浏览器名称。  这是当今 Web 上的常见模式。  将新令牌映射到浏览器名称时，Microsoft 建议使用与旧版 Microsoft Edge 浏览器不同的名称，以避免意外应用不适用于基于 Chromium 的浏览器的任何旧解决方法。 `Edg`

## <a name="user-agent-overrides"></a>用户代理替代  

有时，网站无法识别新Microsoft Edge代理。  因此，一组网站功能可能无法正常运行。  当 Microsoft 收到问题类型通知时，Microsoft 将联系你 \ (网站所有者\) 并通知你更新的用户代理。  

可能需要更多时间来更新和测试网站的用户代理检测逻辑，以解决 Microsoft 报告的问题。  为了最大限度地提高用户的兼容性，Microsoft Edge Beta和稳定渠道使用用户代理替代列表。  更新网站时，请使用用户代理替代。  Microsoft 提供的用户代理替代列表。  

替代指定要发送Microsoft Edge用户代理值，而不是指定特定网站的默认用户代理。  若要显示当前应用的用户代理替代列表，请完成以下操作。  

1.  打开 Microsoft Edge Beta 或 Stable 渠道。  
1.  导航到 `edge://compat/useragent`。  
    
Canary Microsoft Edge开发人员频道当前不会接收用户代理覆盖。  Canary Microsoft Edge开发人员频道提供的环境使用默认模式Microsoft Edge代理。  使用Microsoft Edge Canary 和 Dev 渠道轻松重现由默认用户代理导致Microsoft Edge问题。  若要在渠道或稳定渠道中Microsoft Edge Beta代理替代，请完成以下操作。  

1.  打开命令行应用。  
1.  复制并粘贴以下代码段。  
    
    ```shell
    --disable-domain-action-user-agent-override
    ```  
    
1.  使用Microsoft Edge代码段运行应用程序。  
    
    ```shell
    {path/to/microsoft/edge.ext} --disable-domain-action-user-agent-override
    ```  
    
<!-- links -->  

[WindowsBlogsMsedgedev20171005MicrosoftEdgeIosAndroidDeveloper]: https://blogs.windows.com/msedgedev/2017/10/05/microsoft-edge-ios-android-developer "Microsoft Edge iOS 和 Android 版：开发人员需要知道哪些|Microsoft Windows 博客"  

[GithubWicgUaClientHintsGethighentropyvalues]: https://wicg.github.io/ua-client-hints#getHighEntropyValues "4.1.5. getHighEntropyValues 方法 - User-Agent客户端|GitHub"  

[MdnLearnToolsTestingCrossBrowserTestingFeatureDetection]: https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection "实现功能检测|MDN"  
