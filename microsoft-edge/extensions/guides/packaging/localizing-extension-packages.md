---
ms.assetid: c4043c1e-15ac-4210-8851-3804c7708f49
description: 了解如何本地化你的 Microsoft Edge 扩展程序包，以使其在发布后准备好进行多个区域设置。
title: 本地化扩展程序包
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.custom: seodec18
ms.openlocfilehash: a6a920b80e915bb14c7ea24abcc54105e5b34eb0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563244"
---
# <span data-ttu-id="789b6-104">为 Windows 和 Microsoft Store 本地化 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="789b6-104">Localizing Microsoft Edge extensions for Windows and the Microsoft Store</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="789b6-105">本指南将介绍如何本地化你的 Microsoft Edge 扩展，以使其可以在发布时随时使用多个区域设置。</span><span class="sxs-lookup"><span data-stu-id="789b6-105">This guide walks through how to localize your Microsoft Edge extension so that it's ready for multiple locales upon release.</span></span> <span data-ttu-id="789b6-106">若要完全本地化你的扩展，你需要针对 Windows 和 Microsoft Store 执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="789b6-106">To fully localize your extension, you'll need to follow the steps for both Windows and the Microsoft Store.</span></span>

<span data-ttu-id="789b6-107">如果要本地化 Microsoft Edge 的扩展资源，可以了解如何在[国际化指南](../internationalization.md)中使用国际化框架。</span><span class="sxs-lookup"><span data-stu-id="789b6-107">If you want to localize your extension resources for Microsoft Edge, you can learn how to use the i18n framework in the [Internationalization guide](../internationalization.md).</span></span>


> [!NOTE]
> <span data-ttu-id="789b6-108">如果您的扩展不支持多种语言，则可以跳过以[本地化 Microsoft Store 中的名称和说明](#localizing-name-and-description-in-the-microsoft-store)。</span><span class="sxs-lookup"><span data-stu-id="789b6-108">If your extension doesn't support multiple languages, you can skip to [Localizing name and description in the Microsoft Store](#localizing-name-and-description-in-the-microsoft-store).</span></span>


## <span data-ttu-id="789b6-109">本地化流程概述</span><span class="sxs-lookup"><span data-stu-id="789b6-109">The localization process overview</span></span>

<span data-ttu-id="789b6-110">将扩展提供给广大受众的第一步是为多种语言[配置其 package.appxmanifest](#configuring-the-appxmanifest) 。</span><span class="sxs-lookup"><span data-stu-id="789b6-110">The first step towards getting your extension available to a wide audience is to [configure its AppxManifest](#configuring-the-appxmanifest) for multiple languages.</span></span> <span data-ttu-id="789b6-111">在 Microsoft Store 中，这将向用户显示你的扩展支持的语言。</span><span class="sxs-lookup"><span data-stu-id="789b6-111">In the Microsoft Store, this will show users what languages your extension supports.</span></span> <span data-ttu-id="789b6-112">如果你希望[在 WINDOWS UI 和 Microsoft Store 中本地化](#localizing-extension-resources-for-windows-and-the-microsoft-store)你的扩展的名称，则还需要更改 package.appxmanifest 中的某些字段。</span><span class="sxs-lookup"><span data-stu-id="789b6-112">Certain fields in the AppxManifest will also need to be changed if you want the name of your extension to be [localized in the Windows UI and the Microsoft Store](#localizing-extension-resources-for-windows-and-the-microsoft-store).</span></span>


<span data-ttu-id="789b6-113">配置 Package.appxmanifest 后，你需要为你所指明的支持的语言[创建 JSON 字符串资源](#creating-json-string-resources)。</span><span class="sxs-lookup"><span data-stu-id="789b6-113">Once your AppxManifest is configured, you'll need to [create JSON string resources](#creating-json-string-resources) for the languages that you indicated as supported.</span></span> <span data-ttu-id="789b6-114">这需要为每种语言创建一个 resjson 文件，其中每个文件都具有该语言的所有 UI 字符串。</span><span class="sxs-lookup"><span data-stu-id="789b6-114">This requires creating a .resjson file for each language, where each file has all the UI strings of that language within it.</span></span>


<span data-ttu-id="789b6-115">创建支持语言的 resjson 文件后，[需要创建一个 pri 资源文件](#creating-the-resources-file)。</span><span class="sxs-lookup"><span data-stu-id="789b6-115">After the .resjson files for the supported languages have been made, a [.pri resource file will need to be created](#creating-the-resources-file).</span></span> <span data-ttu-id="789b6-116">这将通过使用[Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk)附带的**makepri.exe**工具的配置文件进行创建。</span><span class="sxs-lookup"><span data-stu-id="789b6-116">This will be created by using a configuration file to the **MakePRI** tool that comes with the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk).</span></span> 

> [!NOTE]
> <span data-ttu-id="789b6-117">如果你仅下载 Windows 10 SDK 以使用 Makepri.exe 工具，你可以仅选择 "适用于桌面应用的 Windows SDK 签名工具" 和 "用于 UWP 托管应用的 Windows SDK" 功能以使下载更浅。</span><span class="sxs-lookup"><span data-stu-id="789b6-117">If you are only downloading the Windows 10 SDK to use the MakePri.exe tool, you can select only the "Windows SDK Signing Tools for Desktop Apps" and "Windows SDK for UWP Managed Apps" features to keep the download lighter.</span></span> <span data-ttu-id="789b6-118">Makepri.exe 工具将出现在 C:\Program 文件（x86） \Windows Kits\10\bin\10.0.17713.0. 的子文件夹中</span><span class="sxs-lookup"><span data-stu-id="789b6-118">The MakePri.exe tool will appear in subfolders of C:\Program Files (x86)\Windows Kits\10\bin\10.0.17713.0.</span></span>


<span data-ttu-id="789b6-119">上载扩展后，最后一步是[本地化 Microsoft Store 中的名称和说明](#localizing-name-and-description-in-the-microsoft-store)。</span><span class="sxs-lookup"><span data-stu-id="789b6-119">Once you've uploaded your extension, the final step is to [localize the name and description in the Microsoft Store](#localizing-name-and-description-in-the-microsoft-store).</span></span>

> [!NOTE]
> <span data-ttu-id="789b6-120">将 Microsoft Edge 扩展提交到 Microsoft Store 目前是受限制的功能。</span><span class="sxs-lookup"><span data-stu-id="789b6-120">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="789b6-121">[通过你](https://aka.ms/extension-request)的请求成为 Microsoft Store 的一部分，我们将考虑你的未来更新。</span><span class="sxs-lookup"><span data-stu-id="789b6-121">[Reach out to us](https://aka.ms/extension-request) with your requests to be a part of the Microsoft Store, and we'll consider you for a future update.</span></span>



## <span data-ttu-id="789b6-122">配置 Package.appxmanifest</span><span class="sxs-lookup"><span data-stu-id="789b6-122">Configuring the AppXManifest</span></span>

<span data-ttu-id="789b6-123">将根据其 Package.appxmanifest 值生成在 Microsoft Store 中扩展的 "支持的语言" 列表。</span><span class="sxs-lookup"><span data-stu-id="789b6-123">Your extension's "Supported languages" list in the Microsoft Store is generated based on its AppXManifest values.</span></span> <span data-ttu-id="789b6-124">使用元素指定此列表 `Resource` 。</span><span class="sxs-lookup"><span data-stu-id="789b6-124">This list is specified using the `Resource` element.</span></span>


![设置图像](./../../media/language-app-details.png)

<span data-ttu-id="789b6-126">若要指定你的扩展支持的语言的列表，你可以添加 `Resource` 下面所示格式的元素（此 `Resource` 元素将显示 Microsoft Store 中的英语、德语和法语的支持）：</span><span class="sxs-lookup"><span data-stu-id="789b6-126">To specify the list of languages that are supported by your extension, you can add a `Resource` element in the format seen below (this `Resource` element will show support for English, German, and French in the Microsoft Store):</span></span>

```xml
<Resources>
    <Resource Language="en-us"/>
    <Resource Language="de-de"/>
    <Resource Language="fr-fr"/>
</Resources>
```

<span data-ttu-id="789b6-127">有关 Microsoft Store 支持的语言/语言代码的信息，请参阅[支持的语言](https://msdn.microsoft.com/windows/uwp/publish/supported-languages)。</span><span class="sxs-lookup"><span data-stu-id="789b6-127">See [Supported languages](https://msdn.microsoft.com/windows/uwp/publish/supported-languages) for info on the languages/language codes that the Microsoft Store supports.</span></span>


<span data-ttu-id="789b6-128">为了为 Package.appxmanifest 中的所有公共可见元素指定本地化的字符串，你必须使用格式的资源标识符 `ms-resource:<resource id>` 。</span><span class="sxs-lookup"><span data-stu-id="789b6-128">In order to specify localized strings for all publicly visible elements in the AppxManifest, you'll have to use a resource identifier in the format of `ms-resource:<resource id>`.</span></span>

<span data-ttu-id="789b6-129">下面的代码段构成了一个完整的 Package.appxmanifest。</span><span class="sxs-lookup"><span data-stu-id="789b6-129">The snippets below make a complete AppxManifest.</span></span> <span data-ttu-id="789b6-130">应从本地化的资源文件中检索以下值：</span><span class="sxs-lookup"><span data-stu-id="789b6-130">The following values should be retrieved from localized resource files:</span></span>

- <span data-ttu-id="789b6-131">Properties\DisplayName</span><span class="sxs-lookup"><span data-stu-id="789b6-131">Properties\DisplayName</span></span>
- <span data-ttu-id="789b6-132">Properties\Description</span><span class="sxs-lookup"><span data-stu-id="789b6-132">Properties\Description</span></span>
- <span data-ttu-id="789b6-133">Properties\PublisherDisplayName</span><span class="sxs-lookup"><span data-stu-id="789b6-133">Properties\PublisherDisplayName</span></span>


```xml
<Properties>
    <DisplayName>ms-resource:DisplayName</DisplayName>
    <Description>ms-resource:Description</Description>
    <Logo>Assets\PackageLogo.png</Logo>
    <PublisherDisplayName>ms-resource:PublisherName</PublisherDisplayName>
</Properties>
```

- <span data-ttu-id="789b6-134">Applications\Application\VisualElements\DisplayName</span><span class="sxs-lookup"><span data-stu-id="789b6-134">Applications\Application\VisualElements\DisplayName</span></span>
- <span data-ttu-id="789b6-135">Applications\Application\VisualElements\Description</span><span class="sxs-lookup"><span data-stu-id="789b6-135">Applications\Application\VisualElements\Description</span></span>
- <span data-ttu-id="789b6-136">Applications\Application\Extensions\Extension\AppExtension\DisplayName</span><span class="sxs-lookup"><span data-stu-id="789b6-136">Applications\Application\Extensions\Extension\AppExtension\DisplayName</span></span>

```xml
<Applications>
    <Application Id="App">
      <uap:VisualElements
        AppListEntry="none"
            DisplayName="ms-resource:DisplayName"
       Square150x150Logo="Assets\Square150x150Logo.png"
       Square44x44Logo="Assets\Square44x44Logo.png"
            Description="ms-resource:Description"
        BackgroundColor="transparent">
      </uap:VisualElements>
      <Extensions>
      <uap3:Extension Category="windows.appExtension">
        <uap3:AppExtension Name="com.microsoft.edge.extension"
            Id="MicrosoftTranslate"
            PublicFolder="Extension"
            DisplayName="ms-resource:DisplayName">
        </uap3:AppExtension>
      </uap3:Extension>
      </Extensions>
    </Application>
  </Applications>
```


## <span data-ttu-id="789b6-137">本地化 Windows 和 Microsoft Store 的扩展资源</span><span class="sxs-lookup"><span data-stu-id="789b6-137">Localizing extension resources for Windows and the Microsoft Store</span></span>

<span data-ttu-id="789b6-138">既然你的 Package.appxmanifest 已配置了多语言，则在你的扩展内本地化 UI 和本地化 Windows 和 Microsoft Store 的扩展之间，你应该知道一些重要的差异。</span><span class="sxs-lookup"><span data-stu-id="789b6-138">Now that your AppxManifest is configured for multiple languages, there are some key differences you should know between localizing the UI within your extension and localizing your extension for Windows and the Microsoft Store.</span></span>

<span data-ttu-id="789b6-139">虽然 Microsoft Edge 扩展无法在 Microsoft Edge 之外运行，但它们的管理可能会在 Windows 内发生。</span><span class="sxs-lookup"><span data-stu-id="789b6-139">While Microsoft Edge extensions don't run outside of Microsoft Edge, the management of them can occur within Windows.</span></span> <span data-ttu-id="789b6-140">例如，用户可以在 "设置" 应用中管理其扩展：</span><span class="sxs-lookup"><span data-stu-id="789b6-140">For example, users can manage their extensions in the Settings app:</span></span>


![设置图像](./../../media/settings.png)



<span data-ttu-id="789b6-142">在 Windows 的 "设置" 应用中显示的扩展名的名称来自 Package.appxmanifest。</span><span class="sxs-lookup"><span data-stu-id="789b6-142">The name of the extension that shows up in the Settings app in Windows comes from the AppXManifest.</span></span> <span data-ttu-id="789b6-143">如果此值为英语的硬编码，将在非英语 Windows 设备上显示该名称的英语版本。</span><span class="sxs-lookup"><span data-stu-id="789b6-143">If this value is hardcoded in English, the English version of the name will show up on non-English Windows devices.</span></span> <span data-ttu-id="789b6-144">如果您的扩展名的品牌仅为英语，则可以将其保留为硬编码。</span><span class="sxs-lookup"><span data-stu-id="789b6-144">If the branding of your extension is English only, it's ok to leave it hardcoded.</span></span>


> [!NOTE]
> <span data-ttu-id="789b6-145">如果你想要在 Windows 中对 Microsoft Edge 扩展使用本地化名称，请确保在 Package.appxmanifest 文件中进行更改之前，也[可使用和保留](./extensions-in-the-windows-dev-center.md#name-reservation)本地化名称。</span><span class="sxs-lookup"><span data-stu-id="789b6-145">If you want to use localized names for your Microsoft Edge Extension in Windows, make sure the localized names are also [available and reserved](./extensions-in-the-windows-dev-center.md#name-reservation) before you make the changes in the AppXManifest file.</span></span> <span data-ttu-id="789b6-146">如果未保留名称，当你将最终程序包上载到 Windows 开发人员中心时，你将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="789b6-146">If the names are not reserved, you'll get the following error when you upload the final package to Windows Dev Center:</span></span></br></br>

![语言错误](./../../media/language-error.png)</br></br>


<span data-ttu-id="789b6-148">为 JavaScript 扩展定义的基于国际化的本地化基础结构仅在 Microsoft Edge 环境中适用。</span><span class="sxs-lookup"><span data-stu-id="789b6-148">The i18n based localization infrastructure that's defined for JavaScript extensions is only applicable within the Microsoft Edge environment.</span></span>

<span data-ttu-id="789b6-149">在 Microsoft Edge 外部、Windows 和 Microsoft Store 中，仅支持通用 Windows 平台（UWP）本地化框架的唯一支持的本地化框架。</span><span class="sxs-lookup"><span data-stu-id="789b6-149">Outside of Microsoft Edge, within Windows and the Microsoft Store, the only supported localization framework is based on the Universal Windows Platform (UWP) localization framework.</span></span>

<span data-ttu-id="789b6-150">虽然我们确实支持基于 HTML 的 Windows 应用的基于 JSON 的资源，但 JSON 资源的架构与为 JavaScript 扩展定义的架构不匹配。</span><span class="sxs-lookup"><span data-stu-id="789b6-150">While we do support JSON based resources for HTML based Windows apps, the schema for the JSON resources doesn't match the one defined for JavaScript extensions.</span></span>


<span data-ttu-id="789b6-151">以下是[基于 HTML 的 Windows 应用](https://msdn.microsoft.com/library/windows/apps/hh465228.aspx)的主要区别：</span><span class="sxs-lookup"><span data-stu-id="789b6-151">The following are the key differences in [HTML based Windows apps](https://msdn.microsoft.com/library/windows/apps/hh465228.aspx):</span></span>
-    <span data-ttu-id="789b6-152">资源是在 resjson 文件中指定的，而不是在 json 文件中指定。</span><span class="sxs-lookup"><span data-stu-id="789b6-152">Resources are specified in .resjson files instead of .json files.</span></span>
-    <span data-ttu-id="789b6-153">支持的区域设置应在 Package.appxmanifest 文件中指定，第一个区域设置为默认区域设置。</span><span class="sxs-lookup"><span data-stu-id="789b6-153">The locales supported should be specified in the AppXManifest file, with the first locale being the default locale.</span></span>
-    <span data-ttu-id="789b6-154">基于 HTML 的 Windows 应用资源使用以下架构：</span><span class="sxs-lookup"><span data-stu-id="789b6-154">HTML based Windows apps resources use the following schema:</span></span>
    ```json
    {
        "greeting"              : "Hello",
        "_greeting.comment"     : "A welcome greeting.",

        "farewell"              : "Goodbye",
        "_farewell.comment"     : "A goodbye."
    }
    ```
    <span data-ttu-id="789b6-155">下划线表示的名称/值对对应的字符串资源的注释。</span><span class="sxs-lookup"><span data-stu-id="789b6-155">The name/value pair denoted by an underscore are comments for the corresponding string resource.</span></span>
-    <span data-ttu-id="789b6-156">resjson 文件将编译为 pri 文件，这些文件必须包含在 AppX 程序包创建期间。</span><span class="sxs-lookup"><span data-stu-id="789b6-156">.resjson files are compiled into .pri files which must be included during AppX package creation.</span></span>


### <span data-ttu-id="789b6-157">创建 JSON 字符串资源</span><span class="sxs-lookup"><span data-stu-id="789b6-157">Creating JSON string resources</span></span>
<span data-ttu-id="789b6-158">使用已配置的 Package.appxmanifest，将突出显示国际化和 UWP 本地化框架之间的差异，即可创建资源文件。</span><span class="sxs-lookup"><span data-stu-id="789b6-158">With a configured AppxManifest in hand and the differences between the i18n and UWP localization frameworks highlighted, you're ready to create your resource files.</span></span>

<span data-ttu-id="789b6-159">清单中仅有一个资源字符串适用于 Microsoft Edge 扩展程序包。</span><span class="sxs-lookup"><span data-stu-id="789b6-159">Only one resource string in the manifest is applicable to Microsoft Edge extension packages.</span></span> <span data-ttu-id="789b6-160">该 `DisplayName` 字符串通常在 JavaScript 扩展中进行本地化，并且可以轻松地映射到 Windows 期望的 resjson 文件。</span><span class="sxs-lookup"><span data-stu-id="789b6-160">The `DisplayName` string is commonly localized in JavaScript extensions, and can be easily mapped to the .resjson files that Windows expects.</span></span> <span data-ttu-id="789b6-161">假设这是您想要本地化的唯一资源，下面是应该创建的 resjson 文件：</span><span class="sxs-lookup"><span data-stu-id="789b6-161">Assuming that this is the only resource that you would like to localize, here is a sample .resjson file that should be created:</span></span>

```json
{
    "DisplayName"              : "Jigsaw",
    "_DisplayName.comment"     : "Name of extension."
}
```

<span data-ttu-id="789b6-162">每个 resjson 文件中的资源 ID 需要与 Package.appxmanifest 中使用的 ID 相匹配。</span><span class="sxs-lookup"><span data-stu-id="789b6-162">The resource ID in each .resjson file needs to match the ID used in the AppXManifest.</span></span> <span data-ttu-id="789b6-163">使用 resjson 代码段，相应的 Package.appxmanifest 条目应为：</span><span class="sxs-lookup"><span data-stu-id="789b6-163">Using the example .resjson snippet above, the corresponding AppXManifest entry should be:</span></span>

`DisplayName="ms-resource:DisplayName"`

<span data-ttu-id="789b6-164">扩展支持的每种语言应具有相应的 resjson 文件，并放置在以下文件夹结构中：</span><span class="sxs-lookup"><span data-stu-id="789b6-164">Each language that your extension supports should have a corresponding resources.resjson file and be placed in the following folder structure:</span></span>

![语言文件夹结构](./../../media/resources-folder.png)


### <span data-ttu-id="789b6-166">创建资源文件</span><span class="sxs-lookup"><span data-stu-id="789b6-166">Creating the resources file</span></span>
<span data-ttu-id="789b6-167">创建所有 resjson 文件后，即可创建程序包资源索引（PRI）文件。</span><span class="sxs-lookup"><span data-stu-id="789b6-167">Once you've created all your .resjson files, you're ready to create your package resource index (PRI) file.</span></span> <span data-ttu-id="789b6-168">此文件存储所有受支持的语言的资源。</span><span class="sxs-lookup"><span data-stu-id="789b6-168">This file stores the resources for all your supported languages.</span></span> <span data-ttu-id="789b6-169">若要执行此操作，你可以使用 Windows 10 SDK 附带的**makepri.exe**工具。</span><span class="sxs-lookup"><span data-stu-id="789b6-169">To do this you can use the **MakePRI** tool which is included with the Windows 10 SDK.</span></span>


<span data-ttu-id="789b6-170">首先，你需要创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="789b6-170">First you'll need to create the configuration file.</span></span> <span data-ttu-id="789b6-171">这将为资源定义默认的限定符和平台。</span><span class="sxs-lookup"><span data-stu-id="789b6-171">This defines the default qualifiers and platform for the resources.</span></span> <span data-ttu-id="789b6-172">对于此示例，请将默认语言设置为英语（US）和平台 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="789b6-172">For this example, make the default language English (US) and the platform Windows 10.</span></span> <span data-ttu-id="789b6-173">若要执行此操作，请在 [Root 文件夹] 中创建包含以下内容的 priconfig 文件：</span><span class="sxs-lookup"><span data-stu-id="789b6-173">To do this, create a priconfig.xml file with the following content in the [Root folder]:</span></span>

![文件夹中的 priconfig](./../../media/priconfig.png)


```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<resources targetOsVersion="10.0.0" majorVersion="1">
    <index root="\" startIndexAt="\">
        <default>
            <qualifier name="Language" value="en-US"/>
            <qualifier name="Contrast" value="standard"/>
            <qualifier name="HomeRegion" value="001"/>
            <qualifier name="TargetSize" value="256"/>
            <qualifier name="LayoutDirection" value="LTR"/>
            <qualifier name="Theme" value="dark"/>
            <qualifier name="AlternateForm" value=""/>
            <qualifier name="DXFeatureLevel" value="DX9"/>
            <qualifier name="Configuration" value=""/>
            <qualifier name="DeviceFamily" value="Universal"/>
            <qualifier name="Custom" value=""/>
        </default>
        <indexer-config type="folder" foldernameAsQualifier="true" filenameAsQualifier="true" qualifierDelimiter="."/>
        <indexer-config type="resw" convertDotsToSlashes="true" initialPath=""/>
        <indexer-config type="resjson" initialPath=""/>
        <indexer-config type="PRI"/>
    </index>
</resources>
```

<span data-ttu-id="789b6-175">现在，你可以使用配置文件和 Makepri.exe 工具创建资源 pri 文件。</span><span class="sxs-lookup"><span data-stu-id="789b6-175">Now you can use the configuration file and the MakePRI tool to create the resources.pri file.</span></span> <span data-ttu-id="789b6-176">对于此示例，项目的根位置将为 [根文件夹]。</span><span class="sxs-lookup"><span data-stu-id="789b6-176">For this example, the root location for the project will be [Root folder].</span></span>


```cmd
MakePRI new /pr [Root folder] /cf [Root folder]\priconfig.xml /mn [Root folder]\AppxManifest.xml /of [Root folder]\resources.pri /o
```

<span data-ttu-id="789b6-177">您的根文件夹中现在应该有一个资源 pri 文件：</span><span class="sxs-lookup"><span data-stu-id="789b6-177">You should now have one resources.pri file in your root folder:</span></span>

![资源文件夹](./../../media/resources.png)


## <span data-ttu-id="789b6-179">在 Microsoft Store 中本地化名称和说明</span><span class="sxs-lookup"><span data-stu-id="789b6-179">Localizing name and description in the Microsoft Store</span></span>

<span data-ttu-id="789b6-180">尝试上载完整的本地化程序包后，Windows 开发人员中心将检测到支持多种语言，并检查每个语言是否具有相应的本地化名称和说明。</span><span class="sxs-lookup"><span data-stu-id="789b6-180">Once you try to upload your complete, localized package, the Windows Dev Center will detect that more than one language is supported and check that you have corresponding localized names and descriptions for each.</span></span> <span data-ttu-id="789b6-181">如果缺少任何本地化值，你的提交将被阻止，直到你提供这些值。</span><span class="sxs-lookup"><span data-stu-id="789b6-181">If any of the localized values are missing, your submission will be blocked until you provide the values.</span></span>

<span data-ttu-id="789b6-182">如果你只想为 Microsoft Store （而非 Windows）提供本地化名称和说明，你可以通过[保留你的扩展的所有本地化名称](./extensions-in-the-windows-dev-center.md#name-reservation)来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="789b6-182">If you are only interested in providing a localized name and description for the Microsoft Store (and not Windows), you can do so by [reserving all the localized names for your extension](./extensions-in-the-windows-dev-center.md#name-reservation).</span></span>


<span data-ttu-id="789b6-183">保留其他本地化名称后，你可以创建更新的提交。</span><span class="sxs-lookup"><span data-stu-id="789b6-183">Once you've reserved additional localized names, you can create an updated submission.</span></span> <span data-ttu-id="789b6-184">在 "描述" 部分中，你可以管理 Microsoft 应用商店的其他语言：</span><span class="sxs-lookup"><span data-stu-id="789b6-184">In the description section you can manage additional languages for your Microsoft Store listing:</span></span>

![日语应用说明](./../../media/manage-description-languages.png)

<span data-ttu-id="789b6-186">选择 "管理其他语言" 后，你将收到选择要添加到 Microsoft 应用商店的语言的语言。</span><span class="sxs-lookup"><span data-stu-id="789b6-186">Once you've selected "Manage additional languages", you'll get to select which languages you want to add to your Microsoft Store listing.</span></span> <span data-ttu-id="789b6-187">新语言将显示为 "说明" 部分中的 "其他说明语言"。</span><span class="sxs-lookup"><span data-stu-id="789b6-187">The new language will show up as 'Additional description language' in the "Description" section.</span></span>

<span data-ttu-id="789b6-188">你可以单击 "描述" 部分中的单个链接，为每种语言提供本地化名称和说明、发行说明、发行说明和视觉资源。</span><span class="sxs-lookup"><span data-stu-id="789b6-188">You can click on the individual link in the "Description" section to provide a localized name and description, release notes, and visual assets for each language.</span></span> <span data-ttu-id="789b6-189">不会从 Package.appxmanifest 中提取 Microsoft Store 的说明。</span><span class="sxs-lookup"><span data-stu-id="789b6-189">The description for the Microsoft Store is not extracted from the AppXManifest.</span></span> <span data-ttu-id="789b6-190">每个本地化说明都需要在 Windows 开发人员中心中手动输入：</span><span class="sxs-lookup"><span data-stu-id="789b6-190">Each localized description needs to be manually entered in the Windows Dev Center:</span></span>

![日语应用说明](./../../media/japanese-app-description.png)

<span data-ttu-id="789b6-192">提交本地化说明并发布扩展后，在 Microsoft Store 中访问该扩展的本地化页面的任何人都将看到以下 UI：</span><span class="sxs-lookup"><span data-stu-id="789b6-192">Once the localized descriptions are submitted and the extension is published, anyone accessing a localized page of the extension in the Microsoft Store will see the following UI:</span></span>

![日语 windows 应用商店](./../../media/japanese-windows-store.png)
 

## <span data-ttu-id="789b6-194">Package.appxmanifest 示例</span><span class="sxs-lookup"><span data-stu-id="789b6-194">AppxManifest samples</span></span>

### <span data-ttu-id="789b6-195">非本地化 Package.appxmanifest</span><span class="sxs-lookup"><span data-stu-id="789b6-195">Non-localized AppxManifest</span></span>
<span data-ttu-id="789b6-196">以下示例显示了未本地化的 Package.appxmanifest，并且仅支持 "en-us" 区域设置。</span><span class="sxs-lookup"><span data-stu-id="789b6-196">The following example shows an AppxManifest that isn't localized, and only supports the "en-us" locale.</span></span>


```xml
<?xml version="1.0" encoding="utf-8"?>
<Package
    xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
    xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10"
    xmlns:uap3="http://schemas.microsoft.com/appx/manifest/uap/windows10/3"
    IgnorableNamespaces="uap3">
    <Identity
        Name="63533cct23.Jigsaw"
        Publisher="CN=932A7C4A-0308-4632-9E2F-5931E8F02B7C"
        Version="1.3.0.0" />

    <Properties>
        <DisplayName>Jigsaw</DisplayName>
        <PublisherDisplayName>cct23</PublisherDisplayName>
        <Logo>Assets\icon-50.png</Logo>
    </Properties>

    <Dependencies>
        <TargetDeviceFamily Name="Windows.Desktop" MinVersion="10.0.14393.0" MaxVersionTested="10.0.14800.0" />
    </Dependencies>

    <Resources>
        <Resource Language="en-us" />
    </Resources>

    <Applications>
        <Application Id="App">
            <uap:VisualElements
                AppListEntry="none"
                DisplayName="Jigsaw"
                Square150x150Logo="Assets\icon-150.png"
                Square44x44Logo="Assets\icon-44.png"
                Description="This is a jigsaw puzzle app"
                BackgroundColor="transparent">
            </uap:VisualElements>
            <Extensions>
                <uap3:Extension Category="windows.appExtension">
                    <uap3:AppExtension
                        Name="com.microsoft.edge.extension"
                        Id="EdgeExtension"
                        PublicFolder="Extension"
                        DisplayName="Jigsaw">
                        <uap3:Properties>
                            <Capabilities>
                                <Capability Name="websiteContent"/>
                                <Capability Name="websiteInfo"/>
                                <Capability Name="browserStorage"/>
                            </Capabilities>
                        </uap3:Properties>
                    </uap3:AppExtension>
                </uap3:Extension>
            </Extensions>
        </Application>
    </Applications>
</Package>
```


#### <span data-ttu-id="789b6-197">本地化 Package.appxmanifest</span><span class="sxs-lookup"><span data-stu-id="789b6-197">Localized AppxManifest</span></span>
<span data-ttu-id="789b6-198">此 Package.appxmanifest 示例针对除 "en-us" 之外的其他八个区域设置进行了本地化。</span><span class="sxs-lookup"><span data-stu-id="789b6-198">This AppxManifest sample is localized for eight other locales besides "en-us".</span></span> <span data-ttu-id="789b6-199">请注意 `ms-resource:<resource id>` 出现的情况：</span><span class="sxs-lookup"><span data-stu-id="789b6-199">Notice the `ms-resource:<resource id>` occurrences:</span></span>


```xml
<?xml version="1.0" encoding="utf-8"?>
<Package
    xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
    xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10"
    xmlns:uap3="http://schemas.microsoft.com/appx/manifest/uap/windows10/3"
    IgnorableNamespaces="uap3">
    <Identity
        Name="63533cct23.Jigsaw"
        Publisher="CN=932A7C4A-0308-4632-9E2F-5931E8F02B7C"
        Version="1.3.0.0" />

    <Properties>
        <DisplayName>ms-resource:DisplayName</DisplayName>
        <PublisherDisplayName>cct23</PublisherDisplayName>
        <Logo>Assets\icon-50.png</Logo>
    </Properties>

    <Dependencies>
        <TargetDeviceFamily Name="Windows.Desktop" MinVersion="10.0.14393.0" MaxVersionTested="10.0.14800.0" />
    </Dependencies>

    <Resources>
        <Resource Language="en-us" />
        <Resource Language="de" />
        <Resource Language="en" />
        <Resource Language="en-gb" />
        <Resource Language="es" />
        <Resource Language="fr" />
        <Resource Language="it" />
        <Resource Language="ja" />
        <Resource Language="zh-cn" />
    </Resources>

    <Applications>
        <Application Id="App">
            <uap:VisualElements
                AppListEntry="none"
                DisplayName="ms-resource:DisplayName"
                Square150x150Logo="Assets\icon-150.png"
                Square44x44Logo="Assets\icon-44.png"
                Description="ms-resource:Description"
                BackgroundColor="transparent">
            </uap:VisualElements>
            <Extensions>
                <uap3:Extension Category="windows.appExtension">
                    <uap3:AppExtension
                        Name="com.microsoft.edge.extension"
                        Id="EdgeExtension"
                        PublicFolder="Extension"
                        DisplayName="ms-resource:DisplayName">
                        <uap3:Properties>
                            <Capabilities>
                                <Capability Name="websiteContent"/>
                                <Capability Name="websiteInfo"/>
                                <Capability Name="browserStorage"/>
                            </Capabilities>
                        </uap3:Properties>
                    </uap3:AppExtension>
                </uap3:Extension>
            </Extensions>
        </Application>
    </Applications>
</Package>
```
