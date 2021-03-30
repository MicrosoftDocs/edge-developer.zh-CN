---
description: 开始使用 Microsoft Edge 开发人员工具在本机 Android 应用中远程调试 WebView。
title: 远程调试 Android WebViews 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/25/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge,web 开发,f12 工具,开发工具
ms.openlocfilehash: 4d389473673791d91c38e252c919378c4725db6b
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461492"
---
<!-- Copyright Meggin Kearney 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="get-started-with-remote-debugging-android-webviews"></a><span data-ttu-id="2ee66-104">远程调试 Android WebViews 入门</span><span class="sxs-lookup"><span data-stu-id="2ee66-104">Get started with remote debugging Android WebViews</span></span>  

<span data-ttu-id="2ee66-105">使用 Microsoft Edge 开发人员工具在本机 Android 应用中调试 Android WebView。</span><span class="sxs-lookup"><span data-stu-id="2ee66-105">Debug Android WebViews in your native Android apps using Microsoft Edge Developer Tools.</span></span>  

<span data-ttu-id="2ee66-106">在 Android 4.4 \(KitKat\) 或更高版本上，使用 DevTools 调试本机 Android 应用中的 WebView 内容。</span><span class="sxs-lookup"><span data-stu-id="2ee66-106">On Android 4.4 \(KitKat\) or later, use DevTools to debug WebView content in native Android apps.</span></span>  

### <a name="summary"></a><span data-ttu-id="2ee66-107">摘要</span><span class="sxs-lookup"><span data-stu-id="2ee66-107">Summary</span></span>  

*   <span data-ttu-id="2ee66-108">在本机 Android 应用中打开 Android WebView 调试;在 Microsoft Edge DevTools 中调试 Android WebView。</span><span class="sxs-lookup"><span data-stu-id="2ee66-108">Turn on Android WebView debugging in your native Android app; debug Android WebViews in Microsoft Edge DevTools.</span></span>  
*   <span data-ttu-id="2ee66-109">若要显示启用调试的 Android WebView 列表，请导航到 `edge://inspect` 。</span><span class="sxs-lookup"><span data-stu-id="2ee66-109">To display the list of the Android WebViews with debugging turned on, navigate to `edge://inspect`.</span></span>  
*   <span data-ttu-id="2ee66-110">使用通过远程调试调试网页的相同方式调试 Android [WebView。][RemoteDebuggingGettingStarted]</span><span class="sxs-lookup"><span data-stu-id="2ee66-110">Debug Android WebViews in the same way you debug a webpage through [remote debugging][RemoteDebuggingGettingStarted].</span></span>  

## <a name="configure-android-webviews-to-debug"></a><span data-ttu-id="2ee66-111">将 Android WebViews 配置为调试</span><span class="sxs-lookup"><span data-stu-id="2ee66-111">Configure Android WebViews to debug</span></span>  

<span data-ttu-id="2ee66-112">必须在你的应用中打开 Android WebView 调试。</span><span class="sxs-lookup"><span data-stu-id="2ee66-112">Android WebView debugging must be turned on within your app.</span></span>  <span data-ttu-id="2ee66-113">若要启用 Android WebView 调试，请对类运行 [setWebContentsDebuggingEnabled][AndroidDeveloperWebViewsSetWebContentsDebuggingEnabled] `WebView` 静态方法。</span><span class="sxs-lookup"><span data-stu-id="2ee66-113">To turn on Android WebView debugging, run the [setWebContentsDebuggingEnabled][AndroidDeveloperWebViewsSetWebContentsDebuggingEnabled] static method on the `WebView` class.</span></span>  

```java
if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.KITKAT) {
    WebView.setWebContentsDebuggingEnabled(true);
}
```  

<span data-ttu-id="2ee66-114">该设置适用于应用的所有 Android WebView。</span><span class="sxs-lookup"><span data-stu-id="2ee66-114">The setting applies to all of the Android WebViews of the app.</span></span>  

> [!TIP]
> <span data-ttu-id="2ee66-115">Android WebView 调试不受应用清单中标志 `debuggable` 状态的影响。</span><span class="sxs-lookup"><span data-stu-id="2ee66-115">Android WebView debugging is not affected by the state of the `debuggable` flag in the manifest of the app.</span></span>  <span data-ttu-id="2ee66-116">如果你希望仅在标志为 时启用 Android WebView `debuggable` 调试， `true` 请在运行时测试标志。</span><span class="sxs-lookup"><span data-stu-id="2ee66-116">If you want to turn on Android WebView debugging only when the `debuggable` flag is `true`, test the flag at runtime.</span></span>  
> 
> ```java
> if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.KITKAT) {
>     if (0 != (getApplicationInfo().flags & ApplicationInfo.FLAG_DEBUGGABLE))
>    { WebView.setWebContentsDebuggingEnabled(true); }
> }
> ```  

## <a name="open-an-android-webview-in-devtools"></a><span data-ttu-id="2ee66-117">在 DevTools 中打开 Android WebView</span><span class="sxs-lookup"><span data-stu-id="2ee66-117">Open an Android WebView in DevTools</span></span>  

<span data-ttu-id="2ee66-118">若要显示已打开调试的 Android WebView 列表，并在设备上运行，请导航到 `edge://inspect` 。</span><span class="sxs-lookup"><span data-stu-id="2ee66-118">To display a list of the Android WebViews with debugging turned on that run on your device, navigate to `edge://inspect`.</span></span>  

<span data-ttu-id="2ee66-119">若要开始调试，在你要调试的 Android WebView 下，选择"检查 **"。**</span><span class="sxs-lookup"><span data-stu-id="2ee66-119">To start debugging, under the Android WebView you want to debug, choose **inspect**.</span></span>  <span data-ttu-id="2ee66-120">使用 DevTools 的方式与执行远程浏览器选项卡的方式相同。</span><span class="sxs-lookup"><span data-stu-id="2ee66-120">Use DevTools in the same way that you do a remote browser tab.</span></span>  

<!--
:::image type="complex" source=".images/webview-debugging.msft.png" alt-text="Inspecting elements in an Android WebView" lightbox=".images/webview-debugging.msft.png":::
   Inspecting elements in an Android WebView  
:::image-end:::  

The gray graphics listed with the Android WebView represent its size and position relative to the screen of the device.  If your Android WebViews have titles set, the titles are listed as well.  
-->  

## <a name="troubleshoot"></a><span data-ttu-id="2ee66-121">疑难解答</span><span class="sxs-lookup"><span data-stu-id="2ee66-121">Troubleshoot</span></span>  

<span data-ttu-id="2ee66-122">你的 Android WebView 不会显示在 `edge://inspect` 页面上？</span><span class="sxs-lookup"><span data-stu-id="2ee66-122">Your Android WebViews aren't displayed on the `edge://inspect` page?</span></span>  

*   <span data-ttu-id="2ee66-123">验证已针对你的应用打开 Android WebView 调试。</span><span class="sxs-lookup"><span data-stu-id="2ee66-123">Verify that Android WebView debugging is turned on for your app.</span></span>  
*   <span data-ttu-id="2ee66-124">在你的设备上，使用你想要调试的 Android WebView 打开应用。</span><span class="sxs-lookup"><span data-stu-id="2ee66-124">On your device, open the app with the Android WebView you want to debug.</span></span>  <span data-ttu-id="2ee66-125">然后，刷新 `edge://inspect` 。</span><span class="sxs-lookup"><span data-stu-id="2ee66-125">Then, refresh `edge://inspect`.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="2ee66-126">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="2ee66-126">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[RemoteDebuggingGettingStarted]: ./index.md "远程调试 Android 设备|Microsoft Docs"  

[AndroidDeveloperWebViewsSetWebContentsDebuggingEnabled]: https://developer.android.com/reference/android/webkit/WebView.html#setWebContentsDebuggingEnabled(boolean) "setWebContentsDebuggingEnabled - WebView |Android 开发人员"  

> [!NOTE]
> <span data-ttu-id="2ee66-129">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="2ee66-129">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="2ee66-130">原始页面位于 [此处，](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/webviews) 由 [Meggin Kearney][MegginKearney] \(Tech Writer\) 。</span><span class="sxs-lookup"><span data-stu-id="2ee66-130">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/webviews) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="2ee66-132">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="2ee66-132">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: http://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
