---
description: 了解如何在清单中声明 API 的权限
title: 在扩展清单中声明 API 权限
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: 987279a8072388d3fd47ee8b7cbf5f9bb3c483e0
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461502"
---
<!-- Copyright A. W. Fuchs

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="declare-api-permissions-in-extension-manifests"></a><span data-ttu-id="55492-104">在扩展清单中声明 API 权限</span><span class="sxs-lookup"><span data-stu-id="55492-104">Declare API permissions in extension manifests</span></span>  

<span data-ttu-id="55492-105">若要使用大部分 `chrome.*` API，扩展必须在清单 `permissions` 中声明 。</span><span class="sxs-lookup"><span data-stu-id="55492-105">To use most of the `chrome.*` APIs, your extension must declare the `permissions` in the manifest.</span></span>  <span data-ttu-id="55492-106">您可以使用下表中的权限字符串声明权限，或使用模式来匹配类似的字符串。</span><span class="sxs-lookup"><span data-stu-id="55492-106">You may declare permissions using a permission string from the table that follows, or use a pattern to match similar strings.</span></span>  <span data-ttu-id="55492-107">如果扩展受到恶意软件的攻击，权限有助于限制扩展。</span><span class="sxs-lookup"><span data-stu-id="55492-107">Permissions help to constrain your extension if it gets compromised by malware.</span></span>  <span data-ttu-id="55492-108">在安装使用权限警告的扩展之前，可能会向用户显示某些权限。</span><span class="sxs-lookup"><span data-stu-id="55492-108">Some permissions may display to users before installation of the extension using Permission Warnings.</span></span>  

<span data-ttu-id="55492-109">如果 API 要求你在清单中声明权限，请查看该 API 的文档以了解所需的权限。</span><span class="sxs-lookup"><span data-stu-id="55492-109">If an API requires you to declare permissions in the manifest, review the documentation for that API to understand the needed permissions.</span></span>  <span data-ttu-id="55492-110">例如，"存储 API"页描述如何声明 `storage` 权限。</span><span class="sxs-lookup"><span data-stu-id="55492-110">For example, the Storage API page describes how to declare the `storage` permission.</span></span>  

<span data-ttu-id="55492-111">以下代码段概述了如何在清单文件中声明权限。</span><span class="sxs-lookup"><span data-stu-id="55492-111">The following code snippet outlines how to declare permissions in the manifest file.</span></span>  

```json
"permissions": [
  "tabs",
  "bookmarks",
  "http://www.blogger.com/",
  "http://*.google.com/",
  "unlimitedStorage"
]
```  

<span data-ttu-id="55492-112">下表列出了清单中当前可用的权限字符串以及说明。</span><span class="sxs-lookup"><span data-stu-id="55492-112">The following table lists the currently available permission strings to use in your manifest, and the descriptions.</span></span>  

| <span data-ttu-id="55492-113">权限字符串</span><span class="sxs-lookup"><span data-stu-id="55492-113">Permission string</span></span> | <span data-ttu-id="55492-114">详细信息</span><span class="sxs-lookup"><span data-stu-id="55492-114">Details</span></span> |  
|:--- |:--- |  
| `activeTab` | <span data-ttu-id="55492-115">请求根据规范向扩展授予 `activeTab` 权限。</span><span class="sxs-lookup"><span data-stu-id="55492-115">Requests that the extension is granted permissions according to the `activeTab` specification.</span></span> |  
| `alarms` | <span data-ttu-id="55492-116">授予对 API 的扩展 `chrome.alarms` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-116">Gives your extension access to the `chrome.alarms` API.</span></span> |  
| `background` | <span data-ttu-id="55492-117">使 Microsoft Edge 提前启动并延迟关闭，以便扩展的生命周期更长。</span><span class="sxs-lookup"><span data-stu-id="55492-117">Makes Microsoft Edge start up early and shut down late, so that extensions may have a longer life.</span></span>  <span data-ttu-id="55492-118">如果任何安装的扩展具有权限，Microsoft Edge 将在用户登录到用户计算机后以及用户启动 Microsoft Edge 之前以不明显方式 `background` 运行。</span><span class="sxs-lookup"><span data-stu-id="55492-118">When any installed extension has `background` permission, Microsoft Edge runs invisibly as soon as the user logs into the user's computer, and before the user launches Microsoft Edge.</span></span>  <span data-ttu-id="55492-119">该权限还使 Microsoft Edge 继续运行，即使其最后一个窗口已关闭，直到用户显式退出 `background` Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="55492-119">The `background` permission also makes Microsoft Edge continue running, even after its last window is closed, until the user explicitly quits Microsoft Edge.</span></span>  <span data-ttu-id="55492-120">此权限不会影响浏览器中关闭的扩展。</span><span class="sxs-lookup"><span data-stu-id="55492-120">This permission does not affect extensions that are turned off in the browser.</span></span>  <span data-ttu-id="55492-121">`background`该权限通常在背景页上使用。</span><span class="sxs-lookup"><span data-stu-id="55492-121">The `background` permission is normally used on a background page.</span></span> |  
| `bookmarks` | <span data-ttu-id="55492-122">授予对 API 的扩展 `chrome.bookmarks` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-122">Gives your extension access to the `chrome.bookmarks` API.</span></span> |  
| `browsingData` | <span data-ttu-id="55492-123">授予对 API 的扩展 `chrome.browsingData` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-123">Gives your extension access to the `chrome.browsingData` API.</span></span> |  
| `certificateProvider` | <span data-ttu-id="55492-124">授予对 API 的扩展 `chrome.certificateProvider` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-124">Gives your extension access to the `chrome.certificateProvider` API.</span></span> |  
| `clipboardRead` | <span data-ttu-id="55492-125">如果扩展使用 ，则必需 `document.execCommand('paste')` 。</span><span class="sxs-lookup"><span data-stu-id="55492-125">Required if the extension uses `document.execCommand('paste')`.</span></span> |  
| `clipboardWrite` | <span data-ttu-id="55492-126">指示扩展使用 `document.execCommand('copy')` 或 `document.execCommand('cut')` 。</span><span class="sxs-lookup"><span data-stu-id="55492-126">Indicates the extension uses `document.execCommand('copy')` or `document.execCommand('cut')`.</span></span> |  
| `contentSettings` | <span data-ttu-id="55492-127">授予对 API 的扩展 `chrome.contentSettings` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-127">Gives your extension access to the `chrome.contentSettings` API.</span></span> |  
| `contextMenus` | <span data-ttu-id="55492-128">授予对 API 的扩展 `chrome.contextMenus` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-128">Gives your extension access to the `chrome.contextMenus` API.</span></span> |  
| `cookies` | <span data-ttu-id="55492-129">授予对 API 的扩展 `chrome.cookies` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-129">Gives your extension access to the `chrome.cookies` API.</span></span> |  
| `debugger` | <span data-ttu-id="55492-130">授予对 API 的扩展 `chrome.debugger` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-130">Gives your extension access to the `chrome.debugger` API.</span></span> |  
| `declarativeContent` | <span data-ttu-id="55492-131">授予对 API 的扩展 `chrome.declarativeContent` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-131">Gives your extension access to the `chrome.declarativeContent` API.</span></span> |  
| `declarativeNetRequest` | <span data-ttu-id="55492-132">授予对 API 的扩展 `chrome.declarativeNetRequest` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-132">Gives your extension access to the `chrome.declarativeNetRequest` API.</span></span> |  
| `declarativeNetRequestFeedback` | <span data-ttu-id="55492-133">授予对 API 内事件和方法的扩展访问权限 `chrome.declarativeNetRequest` ，这将返回有关匹配的声明性规则的信息。</span><span class="sxs-lookup"><span data-stu-id="55492-133">Grants the extension access to events and methods within the `chrome.declarativeNetRequest` API, which returns information on declarative rules matched.</span></span> |  
| `declarativeWebRequest` | <span data-ttu-id="55492-134">授予对 API 的扩展 `chrome.declarativeWebRequest` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-134">Gives your extension access to the `chrome.declarativeWebRequest` API.</span></span> |  
| `desktopCapture` | <span data-ttu-id="55492-135">授予对 API 的扩展 `chrome.desktopCapture` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-135">Gives your extension access to the `chrome.desktopCapture` API.</span></span> |  
| `documentScan` | <span data-ttu-id="55492-136">授予对 API 的扩展 `chrome.documentScan` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-136">Gives your extension access to the `chrome.documentScan` API.</span></span> |  
| `downloads` | <span data-ttu-id="55492-137">授予对 API 的扩展 `chrome.downloads` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-137">Gives your extension access to the `chrome.downloads` API.</span></span> |  
| `enterprise.deviceAttributes` | <span data-ttu-id="55492-138">授予对 API 的扩展 `chrome.enterprise.deviceAttributes` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-138">Gives your extension access to the `chrome.enterprise.deviceAttributes` API.</span></span> |  
| `enterprise.hardwarePlatform` | <span data-ttu-id="55492-139">授予对 API 的扩展 `chrome.enterprise.hardwarePlatform` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-139">Gives your extension access to the `chrome.enterprise.hardwarePlatform` API.</span></span> |  
| `enterprise.networkingAttributes` | <span data-ttu-id="55492-140">授予对 API 的扩展 `chrome.enterprise.networkingAttributes` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-140">Gives your extension access to the `chrome.enterprise.networkingAttributes` API.</span></span> |  
| `enterprise.platformKeys` | <span data-ttu-id="55492-141">授予对 API 的扩展 `chrome.enterprise.platformKeys` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-141">Gives your extension access to the `chrome.enterprise.platformKeys` API.</span></span> |  
| `experimental` | <span data-ttu-id="55492-142">如果扩展使用任意 `chrome.experimental.*` API，则必需。</span><span class="sxs-lookup"><span data-stu-id="55492-142">Required if the extension uses any `chrome.experimental.*` API.</span></span> |  
| `fileBrowserHandler` | <span data-ttu-id="55492-143">授予对 API 的扩展 `chrome.fileBrowserHandler` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-143">Gives your extension access to the `chrome.fileBrowserHandler` API.</span></span> |  
| `fileSystemProvider` | <span data-ttu-id="55492-144">授予对 API 的扩展 `chrome.fileSystemProvider` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-144">Gives your extension access to the `chrome.fileSystemProvider` API.</span></span> |  
| `fontSettings` | <span data-ttu-id="55492-145">授予对 API 的扩展 `chrome.fontSettings` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-145">Gives your extension access to the `chrome.fontSettings` API.</span></span> |  
| `geolocation` | <span data-ttu-id="55492-146">允许扩展使用地理位置 API，而不提示用户授予权限。</span><span class="sxs-lookup"><span data-stu-id="55492-146">Allows the extension to use the geolocation API without prompting the user for permission.</span></span> |  
| `history` | <span data-ttu-id="55492-147">授予对 API 的扩展 `chrome.history` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-147">Gives your extension access to the `chrome.history` API.</span></span> |  
| `identity` | <span data-ttu-id="55492-148">授予对 API 的扩展 `chrome.identity` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-148">Gives your extension access to the `chrome.identity` API.</span></span> |  
| `idle` | <span data-ttu-id="55492-149">授予对 API 的扩展 `chrome.idle` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-149">Gives your extension access to the `chrome.idle` API.</span></span> |  
| `loginState` | <span data-ttu-id="55492-150">授予对 API 的扩展 `chrome.loginState` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-150">Gives your extension access to the `chrome.loginState` API.</span></span> |  
| `management` | <span data-ttu-id="55492-151">授予对 API 的扩展 `chrome.management` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-151">Gives your extension access to the `chrome.management` API.</span></span> |  
| `nativeMessaging` | <span data-ttu-id="55492-152">授予对本机消息传递 API 的扩展访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-152">Gives your extension access to the native messaging API.</span></span> |  
| `notifications` | <span data-ttu-id="55492-153">授予对 API 的扩展 `chrome.notifications` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-153">Gives your extension access to the `chrome.notifications` API.</span></span> |  
| `pageCapture` | <span data-ttu-id="55492-154">授予对 API 的扩展 `chrome.pageCapture` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-154">Gives your extension access to the `chrome.pageCapture` API.</span></span> |  
| `platformKeys` | <span data-ttu-id="55492-155">授予对 API 的扩展 `chrome.platformKeys` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-155">Gives your extension access to the `chrome.platformKeys` API.</span></span> |  
| `power` | <span data-ttu-id="55492-156">授予对 API 的扩展 `chrome.power` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-156">Gives your extension access to the `chrome.power` API.</span></span> |  
| `printerProvider` | <span data-ttu-id="55492-157">授予对 API 的扩展 `chrome.printerProvider` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-157">Gives your extension access to the `chrome.printerProvider` API.</span></span> |  
| `printing` | <span data-ttu-id="55492-158">授予对 API 的扩展 `chrome.printing` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-158">Gives your extension access to the `chrome.printing` API.</span></span> |  
| `printingMetrics` | <span data-ttu-id="55492-159">授予对 API 的扩展 `chrome.printingMetrics` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-159">Gives your extension access to the `chrome.printingMetrics` API.</span></span> |  
| `privacy` | <span data-ttu-id="55492-160">授予对 API 的扩展 `chrome.privacy` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-160">Gives your extension access to the `chrome.privacy` API.</span></span> |  
| `processes` | <span data-ttu-id="55492-161">授予对 API 的扩展 `chrome.processes` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-161">Gives your extension access to the `chrome.processes` API.</span></span> |  
| `proxy` | <span data-ttu-id="55492-162">授予对 API 的扩展 `chrome.proxy` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-162">Gives your extension access to the `chrome.proxy` API.</span></span> |  
| `scripting` | <span data-ttu-id="55492-163">授予对 API 的扩展 `chrome.scripting` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-163">Gives your extension access to the `chrome.scripting` API.</span></span> |  
| `search` | <span data-ttu-id="55492-164">授予对 API 的扩展 `chrome.search` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-164">Gives your extension access to the `chrome.search` API.</span></span> |  
| `sessions` | <span data-ttu-id="55492-165">授予对 API 的扩展 `chrome.sessions` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-165">Gives your extension access to the `chrome.sessions` API.</span></span> |  
| `signedInDevices` | <span data-ttu-id="55492-166">授予对 API 的扩展 `chrome.signedInDevices` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-166">Gives your extension access to the `chrome.signedInDevices` API.</span></span> |  
| `storage` | <span data-ttu-id="55492-167">授予对 API 的扩展 `chrome.storage` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-167">Gives your extension access to the `chrome.storage` API.</span></span> |  
| `system.cpu` | <span data-ttu-id="55492-168">授予对 API 的扩展 `chrome.system.cpu` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-168">Gives your extension access to the `chrome.system.cpu` API.</span></span> |  
| `system.display` | <span data-ttu-id="55492-169">授予对 API 的扩展 `chrome.system.display` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-169">Gives your extension access to the `chrome.system.display` API.</span></span> |  
| `system.memory` | <span data-ttu-id="55492-170">授予对 API 的扩展 `chrome.system.memory` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-170">Gives your extension access to the `chrome.system.memory` API.</span></span> |  
| `system.storage` | <span data-ttu-id="55492-171">授予对 API 的扩展 `chrome.system.storage` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-171">Gives your extension access to the `chrome.system.storage` API.</span></span> |  
| `tabCapture` | <span data-ttu-id="55492-172">授予对 API 的扩展 `chrome.tabCapture` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-172">Gives your extension access to the `chrome.tabCapture` API.</span></span> |  
| `tabGroups` | <span data-ttu-id="55492-173">授予对 API 的扩展 `chrome.tabGroups` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-173">Gives your extension access to the `chrome.tabGroups` API.</span></span> |  
| `tabs` | <span data-ttu-id="55492-174">向扩展授予对可能由多个 API（包括 和 ）使用的对象的特权 `Tab` 字段 `chrome.tabs` 的访问权限 `chrome.windows` 。</span><span class="sxs-lookup"><span data-stu-id="55492-174">Gives your extension access to privileged fields of the `Tab` objects that may be used by several APIs including `chrome.tabs` and `chrome.windows`.</span></span>  <span data-ttu-id="55492-175">在许多情况下，扩展无需声明使用这些 `tabs` API 的权限。</span><span class="sxs-lookup"><span data-stu-id="55492-175">In many circumstances, your extension does not need to declare the `tabs` permission to make use of these APIs.</span></span> |  
| `topSites` | <span data-ttu-id="55492-176">授予对 API 的扩展 `chrome.topSites` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-176">Gives your extension access to the `chrome.topSites` API.</span></span> |  
| `tts` | <span data-ttu-id="55492-177">授予对 API 的扩展 `chrome.tts` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-177">Gives your extension access to the `chrome.tts` API.</span></span> |  
| `ttsEngine` | <span data-ttu-id="55492-178">授予对 API 的扩展 `chrome.ttsEngine` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-178">Gives your extension access to the `chrome.ttsEngine` API.</span></span> |  
| `unlimitedStorage` | <span data-ttu-id="55492-179">提供用于存储客户端数据（如数据库和本地存储文件）的无限制配额。</span><span class="sxs-lookup"><span data-stu-id="55492-179">Provides an unlimited quota for storing client-side data, such as databases and local storage files.</span></span>  <span data-ttu-id="55492-180">如果没有此权限，扩展将限制为 5 MB 的本地存储。</span><span class="sxs-lookup"><span data-stu-id="55492-180">Without this permission, the extension is limited to 5 MB of local storage.</span></span> |  
| `vpnProvider` | <span data-ttu-id="55492-181">授予对 API 的扩展 `chrome.vpnProvider` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-181">Gives your extension access to the `chrome.vpnProvider` API.</span></span> |  
| `wallpaper` | <span data-ttu-id="55492-182">授予对 API 的扩展 `chrome.wallpaper` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-182">Gives your extension access to the `chrome.wallpaper` API.</span></span> |  
| `webNavigation` | <span data-ttu-id="55492-183">授予对 API 的扩展 `chrome.webNavigation` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-183">Gives your extension access to the `chrome.webNavigation` API.</span></span> |  
| `webRequest` | <span data-ttu-id="55492-184">授予对 API 的扩展 `chrome.webRequest` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="55492-184">Gives your extension access to the `chrome.webRequest` API.</span></span> |  
| `webRequestBlocking` | <span data-ttu-id="55492-185">如果扩展使用 API 阻止 `chrome.webRequest` 请求，此为必需项。</span><span class="sxs-lookup"><span data-stu-id="55492-185">Required if the extension uses the `chrome.webRequest` API to block requests.</span></span> |  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="55492-186">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="55492-186">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="55492-187">原始页面位于 [此处](https://developer.chrome.com/docs/extensions/mv3/declare_permissions/)。</span><span class="sxs-lookup"><span data-stu-id="55492-187">The original page is found [here](https://developer.chrome.com/docs/extensions/mv3/declare_permissions/).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="55492-189">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="55492-189">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
