---
description: 了解如何本地化 Microsoft Edge 扩展包，以便它在发布后可供多个区域设置使用。
title: 本地化扩展包
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: c4043c1e-15ac-4210-8851-3804c7708f49
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d5dd21f82fd746ad619e9d89a1526ff6a511d615
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397718"
---
# <a name="localizing-microsoft-edge-extensions-for-windows-and-the-microsoft-store"></a><span data-ttu-id="8f329-104">本地化适用于 Windows 和 Microsoft Store 的 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="8f329-104">Localizing Microsoft Edge extensions for Windows and the Microsoft Store</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="8f329-105">本指南逐步介绍如何本地化 Microsoft Edge 扩展，以便它可以在发布时用于多个区域设置。</span><span class="sxs-lookup"><span data-stu-id="8f329-105">This guide walks through how to localize your Microsoft Edge extension so that it's ready for multiple locales upon release.</span></span>  <span data-ttu-id="8f329-106">若要完全本地化扩展，你将需要遵循 Windows 和 Microsoft Store 的步骤。</span><span class="sxs-lookup"><span data-stu-id="8f329-106">To fully localize your extension, you'll need to follow the steps for both Windows and the Microsoft Store.</span></span>  

<span data-ttu-id="8f329-107">如果要本地化 Microsoft Edge 的扩展资源，可以在国际化指南中了解如何使用 i18n [框架](../internationalization.md)。</span><span class="sxs-lookup"><span data-stu-id="8f329-107">If you want to localize your extension resources for Microsoft Edge, you can learn how to use the i18n framework in the [Internationalization guide](../internationalization.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="8f329-108">如果你的扩展不支持多种语言，你可以跳到 Microsoft Store 中的本地化 [名称和说明](#localizing-name-and-description-in-the-microsoft-store)。</span><span class="sxs-lookup"><span data-stu-id="8f329-108">If your extension doesn't support multiple languages, you can skip to [Localizing name and description in the Microsoft Store](#localizing-name-and-description-in-the-microsoft-store).</span></span>  

## <a name="the-localization-process-overview"></a><span data-ttu-id="8f329-109">本地化过程概述</span><span class="sxs-lookup"><span data-stu-id="8f329-109">The localization process overview</span></span>  

<span data-ttu-id="8f329-110">要向广大受众提供扩展，第一步是将其 [AppxManifest](#configuring-the-appxmanifest) 配置为多种语言。</span><span class="sxs-lookup"><span data-stu-id="8f329-110">The first step towards getting your extension available to a wide audience is to [configure its AppxManifest](#configuring-the-appxmanifest) for multiple languages.</span></span>  <span data-ttu-id="8f329-111">在 Microsoft Store 中，这将向用户显示你的扩展支持的语言。</span><span class="sxs-lookup"><span data-stu-id="8f329-111">In the Microsoft Store, this will show users what languages your extension supports.</span></span>  <span data-ttu-id="8f329-112">如果你希望扩展的名称在 Windows UI 和 [Microsoft Store](#localizing-extension-resources-for-windows-and-the-microsoft-store)中本地化，则 AppxManifest 中的某些字段也需要更改。</span><span class="sxs-lookup"><span data-stu-id="8f329-112">Certain fields in the AppxManifest will also need to be changed if you want the name of your extension to be [localized in the Windows UI and the Microsoft Store](#localizing-extension-resources-for-windows-and-the-microsoft-store).</span></span>  

<span data-ttu-id="8f329-113">配置 AppxManifest 后，你需要为指示受支持的语言创建 [JSON](#creating-json-string-resources) 字符串资源。</span><span class="sxs-lookup"><span data-stu-id="8f329-113">Once your AppxManifest is configured, you'll need to [create JSON string resources](#creating-json-string-resources) for the languages that you indicated as supported.</span></span>  <span data-ttu-id="8f329-114">这需要为 `.resjson` 每种语言创建一个文件，其中每个文件包含该语言的所有 UI 字符串。</span><span class="sxs-lookup"><span data-stu-id="8f329-114">This requires creating a `.resjson` file for each language, where each file has all the UI strings of that language within it.</span></span>  

<span data-ttu-id="8f329-115">创建支持的语言的文件后，将需要创建一个 `.resjson` [.pri 资源文件](#creating-the-resources-file)。</span><span class="sxs-lookup"><span data-stu-id="8f329-115">After the `.resjson` files for the supported languages have been made, a [.pri resource file will need to be created](#creating-the-resources-file).</span></span> <span data-ttu-id="8f329-116">这将通过使用 Windows [10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk)随附的 MakePRI 工具的配置文件创建。</span><span class="sxs-lookup"><span data-stu-id="8f329-116">This will be created by using a configuration file to the MakePRI tool that comes with the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk).</span></span>  

> [!NOTE]
> <span data-ttu-id="8f329-117">如果你仅下载 Windows 10 SDK 以使用该工具，则只能选择适用于桌面应用的 Windows SDK 签名工具和 `MakePri.exe` **适用于 UWP 托管应用功能的 Windows SDK，** 以保持下载更轻松。 </span><span class="sxs-lookup"><span data-stu-id="8f329-117">If you are only downloading the Windows 10 SDK to use the `MakePri.exe` tool, you can select only the **Windows SDK Signing Tools for Desktop Apps** and **Windows SDK for UWP Managed App** features to keep the download lighter.</span></span>  <span data-ttu-id="8f329-118">该工具 `MakePri.exe` 将显示在 的子文件夹 `C:\Program Files (x86)\Windows Kits\10\bin\10.0.17713.0` 。</span><span class="sxs-lookup"><span data-stu-id="8f329-118">The `MakePri.exe` tool will appear in subfolders of `C:\Program Files (x86)\Windows Kits\10\bin\10.0.17713.0`.</span></span>  

<span data-ttu-id="8f329-119">上传扩展后，最后一步是本地化 [Microsoft Store 中的名称和说明](#localizing-name-and-description-in-the-microsoft-store)。</span><span class="sxs-lookup"><span data-stu-id="8f329-119">Once you've uploaded your extension, the final step is to [localize the name and description in the Microsoft Store](#localizing-name-and-description-in-the-microsoft-store).</span></span>  

> [!NOTE]
> <span data-ttu-id="8f329-120">将 Microsoft Edge 扩展提交到 Microsoft Store 目前是受限功能。</span><span class="sxs-lookup"><span data-stu-id="8f329-120">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span>  <span data-ttu-id="8f329-121">**联系我们，** 请求成为 Microsoft Store 的一部分，我们将考虑你进行将来的更新。</span><span class="sxs-lookup"><span data-stu-id="8f329-121">**Reach out to us** with your requests to be a part of the Microsoft Store, and we'll consider you for a future update.</span></span>  

## <a name="configuring-the-appxmanifest"></a><span data-ttu-id="8f329-122">配置 AppXManifest</span><span class="sxs-lookup"><span data-stu-id="8f329-122">Configuring the AppXManifest</span></span>  

<span data-ttu-id="8f329-123">Microsoft Store 中的扩展支持的语言列表基于其 AppXManifest 值生成。</span><span class="sxs-lookup"><span data-stu-id="8f329-123">Your extension's Supported languages list in the Microsoft Store is generated based on its AppXManifest values.</span></span>  <span data-ttu-id="8f329-124">使用元素指定 `Resource` 此列表。</span><span class="sxs-lookup"><span data-stu-id="8f329-124">This list is specified using the `Resource` element.</span></span>  

![应用详细信息](../../media/language-app-details.png)  

<span data-ttu-id="8f329-126">若要指定扩展支持的语言列表，您可以添加格式如下 \(此元素将在 `Resource` Microsoft Store\) 中显示对英语、德语 `Resource` 和法语的支持：</span><span class="sxs-lookup"><span data-stu-id="8f329-126">To specify the list of languages that are supported by your extension, you can add a `Resource` element in the format seen below \(this `Resource` element will show support for English, German, and French in the Microsoft Store\):</span></span>  

```xml
<Resources>
    <Resource Language="en-us"/>
    <Resource Language="de-de"/>
    <Resource Language="fr-fr"/>
</Resources>
```  

<span data-ttu-id="8f329-127">有关 [Microsoft](/windows/uwp/publish/supported-languages) Store 支持的语言/语言代码的信息，请参阅支持的语言。</span><span class="sxs-lookup"><span data-stu-id="8f329-127">See [Supported languages](/windows/uwp/publish/supported-languages) for info on the languages/language codes that the Microsoft Store supports.</span></span>  

<span data-ttu-id="8f329-128">为了指定 AppxManifest 中所有公开可见的元素的本地化字符串，你必须使用格式为 .的资源标识符 `ms-resource:<resource id>` 。</span><span class="sxs-lookup"><span data-stu-id="8f329-128">In order to specify localized strings for all publicly visible elements in the AppxManifest, you'll have to use a resource identifier in the format of `ms-resource:<resource id>`.</span></span>  

<span data-ttu-id="8f329-129">下面的代码段可创建完整的 AppxManifest。</span><span class="sxs-lookup"><span data-stu-id="8f329-129">The snippets below make a complete AppxManifest.</span></span> <span data-ttu-id="8f329-130">应从本地化的资源文件中检索以下值：</span><span class="sxs-lookup"><span data-stu-id="8f329-130">The following values should be retrieved from localized resource files:</span></span>  

*   <span data-ttu-id="8f329-131">Properties\DisplayName</span><span class="sxs-lookup"><span data-stu-id="8f329-131">Properties\DisplayName</span></span>  
*   <span data-ttu-id="8f329-132">Properties\Description</span><span class="sxs-lookup"><span data-stu-id="8f329-132">Properties\Description</span></span>  
*   <span data-ttu-id="8f329-133">Properties\PublisherDisplayName</span><span class="sxs-lookup"><span data-stu-id="8f329-133">Properties\PublisherDisplayName</span></span>  

```xml
<Properties>
    <DisplayName>ms-resource:DisplayName</DisplayName>
    <Description>ms-resource:Description</Description>
    <Logo>Assets\PackageLogo.png</Logo>
    <PublisherDisplayName>ms-resource:PublisherName</PublisherDisplayName>
</Properties>
```  

*   <span data-ttu-id="8f329-134">Applications\Application\VisualElements\DisplayName</span><span class="sxs-lookup"><span data-stu-id="8f329-134">Applications\Application\VisualElements\DisplayName</span></span>  
*   <span data-ttu-id="8f329-135">Applications\Application\VisualElements\Description</span><span class="sxs-lookup"><span data-stu-id="8f329-135">Applications\Application\VisualElements\Description</span></span>  
*   <span data-ttu-id="8f329-136">Applications\Application\Extensions\Extension\AppExtension\DisplayName</span><span class="sxs-lookup"><span data-stu-id="8f329-136">Applications\Application\Extensions\Extension\AppExtension\DisplayName</span></span>  

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

## <a name="localizing-extension-resources-for-windows-and-the-microsoft-store"></a><span data-ttu-id="8f329-137">本地化 Windows 和 Microsoft Store 的扩展资源</span><span class="sxs-lookup"><span data-stu-id="8f329-137">Localizing extension resources for Windows and the Microsoft Store</span></span>  

<span data-ttu-id="8f329-138">现在，AppxManifest 已配置为多种语言，在扩展内本地化 UI 和本地化 Windows 和 Microsoft Store 的扩展之间存在一些关键差异。</span><span class="sxs-lookup"><span data-stu-id="8f329-138">Now that your AppxManifest is configured for multiple languages, there are some key differences you should know between localizing the UI within your extension and localizing your extension for Windows and the Microsoft Store.</span></span>  

<span data-ttu-id="8f329-139">虽然 Microsoft Edge 扩展不会在 Microsoft Edge 外部运行，但可以在 Windows 中管理它们。</span><span class="sxs-lookup"><span data-stu-id="8f329-139">While Microsoft Edge extensions don't run outside of Microsoft Edge, the management of them can occur within Windows.</span></span>  <span data-ttu-id="8f329-140">例如，用户可以在"设置"应用中管理其扩展：</span><span class="sxs-lookup"><span data-stu-id="8f329-140">For example, users can manage their extensions in the Settings app:</span></span>  

![设置应用](../../media/settings.png)  

<span data-ttu-id="8f329-142">在 Windows 的"设置"应用中显示扩展的名称来自 AppXManifest。</span><span class="sxs-lookup"><span data-stu-id="8f329-142">The name of the extension that shows up in the Settings app in Windows comes from the AppXManifest.</span></span>  <span data-ttu-id="8f329-143">如果此值用英语硬编码，则名称的英文版本将在非英语 Windows 设备上显示。</span><span class="sxs-lookup"><span data-stu-id="8f329-143">If this value is hardcoded in English, the English version of the name will show up on non-English Windows devices.</span></span>  <span data-ttu-id="8f329-144">如果扩展的品牌仅为英语，则保留硬编码。</span><span class="sxs-lookup"><span data-stu-id="8f329-144">If the branding of your extension is English only, it's ok to leave it hardcoded.</span></span>  

> [!NOTE]
> <span data-ttu-id="8f329-145">如果要在 Windows 中对 Microsoft Edge 扩展使用本地化名称，请确保本地化后的名称也可用并[](./extensions-in-the-windows-dev-center.md#name-reservation)保留，然后再在 AppXManifest 文件中进行更改。</span><span class="sxs-lookup"><span data-stu-id="8f329-145">If you want to use localized names for your Microsoft Edge Extension in Windows, make sure the localized names are also [available and reserved](./extensions-in-the-windows-dev-center.md#name-reservation) before you make the changes in the AppXManifest file.</span></span>  <span data-ttu-id="8f329-146">如果未保留名称，在将最终程序包上载到 Windows 开发人员中心时，将看到以下错误：</span><span class="sxs-lookup"><span data-stu-id="8f329-146">If the names are not reserved, you'll get the following error when you upload the final package to Windows Dev Center:</span></span>  
> 
> ![语言错误](../../media/language-error.png)  

<span data-ttu-id="8f329-148">为 JavaScript 扩展定义的基于 i18n 的本地化基础结构仅适用于 Microsoft Edge 环境。</span><span class="sxs-lookup"><span data-stu-id="8f329-148">The i18n based localization infrastructure that's defined for JavaScript extensions is only applicable within the Microsoft Edge environment.</span></span>  

<span data-ttu-id="8f329-149">在 Microsoft Edge 外部的 Windows 和 Microsoft Store 中，唯一受支持的本地化框架基于通用 Windows 平台 (UWP) 框架。</span><span class="sxs-lookup"><span data-stu-id="8f329-149">Outside of Microsoft Edge, within Windows and the Microsoft Store, the only supported localization framework is based on the Universal Windows Platform (UWP) localization framework.</span></span>  

<span data-ttu-id="8f329-150">虽然我们支持基于 HTML 的 Windows 应用的基于 JSON 的资源，但 JSON 资源的架构与为 JavaScript 扩展定义的架构不匹配。</span><span class="sxs-lookup"><span data-stu-id="8f329-150">While we do support JSON based resources for HTML based Windows apps, the schema for the JSON resources doesn't match the one defined for JavaScript extensions.</span></span>  

<span data-ttu-id="8f329-151">以下是基于 HTML 的 [Windows 应用中的主要区别](/previous-versions/windows/apps/hh465228(v=win.10))：</span><span class="sxs-lookup"><span data-stu-id="8f329-151">The following are the key differences in [HTML based Windows apps](/previous-versions/windows/apps/hh465228(v=win.10)):</span></span>  

*   <span data-ttu-id="8f329-152">资源在文件中 `.resjson` 而不是文件中 `.json` 指定。</span><span class="sxs-lookup"><span data-stu-id="8f329-152">Resources are specified in `.resjson` files instead of `.json` files.</span></span>  
*   <span data-ttu-id="8f329-153">应在 AppXManifest 文件中指定支持区域设置，第一个区域设置是默认区域设置。</span><span class="sxs-lookup"><span data-stu-id="8f329-153">The locales supported should be specified in the AppXManifest file, with the first locale being the default locale.</span></span>  
*   <span data-ttu-id="8f329-154">基于 HTML 的 Windows 应用资源使用以下架构：</span><span class="sxs-lookup"><span data-stu-id="8f329-154">HTML based Windows apps resources use the following schema:</span></span>  
    
    ```json
    {
        "greeting"              : "Hello",
        "_greeting.comment"     : "A welcome greeting.",

        "farewell"              : "Goodbye",
        "_farewell.comment"     : "A goodbye."
    }
    ```  
    
    <span data-ttu-id="8f329-155">由下划线表示的名称/值对是相应字符串资源的注释。</span><span class="sxs-lookup"><span data-stu-id="8f329-155">The name/value pair denoted by an underscore are comments for the corresponding string resource.</span></span>  
*   `.resjson` <span data-ttu-id="8f329-156">文件编译为在 `.pri` AppX 程序包创建过程中必须包含的文件。</span><span class="sxs-lookup"><span data-stu-id="8f329-156">files are compiled into `.pri` files which must be included during AppX package creation.</span></span>  
    
### <a name="creating-json-string-resources"></a><span data-ttu-id="8f329-157">创建 JSON 字符串资源</span><span class="sxs-lookup"><span data-stu-id="8f329-157">Creating JSON string resources</span></span>  

<span data-ttu-id="8f329-158">有了已配置的 AppxManifest，并突出显示了 i18n 和 UWP 本地化框架之间的差异，你已准备好创建资源文件。</span><span class="sxs-lookup"><span data-stu-id="8f329-158">With a configured AppxManifest in hand and the differences between the i18n and UWP localization frameworks highlighted, you're ready to create your resource files.</span></span>  

<span data-ttu-id="8f329-159">清单中只有一个资源字符串适用于 Microsoft Edge 扩展包。</span><span class="sxs-lookup"><span data-stu-id="8f329-159">Only one resource string in the manifest is applicable to Microsoft Edge extension packages.</span></span>  <span data-ttu-id="8f329-160">该字符串通常本地化为 JavaScript 扩展，并且可以轻松映射到 `DisplayName` `.resjson` Windows 期望的文件。</span><span class="sxs-lookup"><span data-stu-id="8f329-160">The `DisplayName` string is commonly localized in JavaScript extensions, and can be easily mapped to the `.resjson` files that Windows expects.</span></span>  <span data-ttu-id="8f329-161">假定这是要本地化的唯一资源，下面是应创建 `.resjson` 的示例文件：</span><span class="sxs-lookup"><span data-stu-id="8f329-161">Assuming that this is the only resource that you would like to localize, here is a sample `.resjson` file that should be created:</span></span>  

```json
{
    "DisplayName"              : "Jigsaw",
    "_DisplayName.comment"     : "Name of extension."
}
```  

<span data-ttu-id="8f329-162">每个文件中的资源 ID `.resjson` 需要与 AppXManifest 中使用的 ID 相匹配。</span><span class="sxs-lookup"><span data-stu-id="8f329-162">The resource ID in each `.resjson` file needs to match the ID used in the AppXManifest.</span></span>  <span data-ttu-id="8f329-163">使用上述 `.resjson` 示例代码段，相应的 AppXManifest 条目应为：</span><span class="sxs-lookup"><span data-stu-id="8f329-163">Using the example `.resjson` snippet above, the corresponding AppXManifest entry should be:</span></span>  

`DisplayName="ms-resource:DisplayName"`  

<span data-ttu-id="8f329-164">扩展支持的每种语言都应具有相应的资源文件 `.resjson` ，并放置在以下文件夹结构中：</span><span class="sxs-lookup"><span data-stu-id="8f329-164">Each language that your extension supports should have a corresponding resources `.resjson` file and be placed in the following folder structure:</span></span>  

![语言文件夹结构](../../media/resources-folder.png)  

### <a name="creating-the-resources-file"></a><span data-ttu-id="8f329-166">创建资源文件</span><span class="sxs-lookup"><span data-stu-id="8f329-166">Creating the resources file</span></span>  

<span data-ttu-id="8f329-167">创建所有文件后，即可创建程序包资源索引 `.resjson` \(PRI\) 文件。</span><span class="sxs-lookup"><span data-stu-id="8f329-167">Once you've created all your `.resjson` files, you're ready to create your package resource index \(PRI\) file.</span></span>  <span data-ttu-id="8f329-168">此文件存储所有支持的语言的资源。</span><span class="sxs-lookup"><span data-stu-id="8f329-168">This file stores the resources for all your supported languages.</span></span>  <span data-ttu-id="8f329-169">为此，可以使用 Windows 10 SDK 中包含的 **MakePRI** 工具。</span><span class="sxs-lookup"><span data-stu-id="8f329-169">To do this you can use the **MakePRI** tool which is included with the Windows 10 SDK.</span></span>  

<span data-ttu-id="8f329-170">首先，你需要创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="8f329-170">First you'll need to create the configuration file.</span></span>  <span data-ttu-id="8f329-171">这将定义资源的默认限定符和平台。</span><span class="sxs-lookup"><span data-stu-id="8f329-171">This defines the default qualifiers and platform for the resources.</span></span>  <span data-ttu-id="8f329-172">对于此示例，使用默认语言 `English (US)` 和平台 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="8f329-172">For this example, make the default language `English (US)` and the platform Windows 10.</span></span>  <span data-ttu-id="8f329-173">为此，请创建 `priconfig.xml` 一个具有以下内容的文件 `[Root folder]` ：</span><span class="sxs-lookup"><span data-stu-id="8f329-173">To do this, create a `priconfig.xml` file with the following content in the `[Root folder]`:</span></span>  

![文件夹中的 priconfig](../../media/priconfig.png)  

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

<span data-ttu-id="8f329-175">现在，可以使用配置文件和 MakePRI 工具创建 resources.pri 文件。</span><span class="sxs-lookup"><span data-stu-id="8f329-175">Now you can use the configuration file and the MakePRI tool to create the resources.pri file.</span></span>  <span data-ttu-id="8f329-176">对于此示例，项目的根位置将为 `[Root folder]` 。</span><span class="sxs-lookup"><span data-stu-id="8f329-176">For this example, the root location for the project will be `[Root folder]`.</span></span>  

```cmd
MakePRI new /pr [Root folder] /cf [Root folder]\priconfig.xml /mn [Root folder]\AppxManifest.xml /of [Root folder]\resources.pri /o
```  

<span data-ttu-id="8f329-177">现在，根文件夹中应该有一个 resources.pri 文件：</span><span class="sxs-lookup"><span data-stu-id="8f329-177">You should now have one resources.pri file in your root folder:</span></span>  

![资源文件夹](../../media/resources.png)  

## <a name="localizing-name-and-description-in-the-microsoft-store"></a><span data-ttu-id="8f329-179">本地化 Microsoft Store 中的名称和说明</span><span class="sxs-lookup"><span data-stu-id="8f329-179">Localizing name and description in the Microsoft Store</span></span>  

<span data-ttu-id="8f329-180">尝试上传完整的本地化程序包后，Windows 开发人员中心将检测是否支持多种语言，并检查您是否具有每种语言的相应本地化名称和说明。</span><span class="sxs-lookup"><span data-stu-id="8f329-180">Once you try to upload your complete, localized package, the Windows Dev Center will detect that more than one language is supported and check that you have corresponding localized names and descriptions for each.</span></span>  <span data-ttu-id="8f329-181">如果缺少任何本地化值，则你的提交将被阻止，直到你提供这些值。</span><span class="sxs-lookup"><span data-stu-id="8f329-181">If any of the localized values are missing, your submission will be blocked until you provide the values.</span></span>  

<span data-ttu-id="8f329-182">如果你只对为 Microsoft Store (而不是 Windows) 提供本地化名称和说明感兴趣，则可以通过保留扩展的所有本地化名称来[这样做。](./extensions-in-the-windows-dev-center.md#name-reservation)</span><span class="sxs-lookup"><span data-stu-id="8f329-182">If you are only interested in providing a localized name and description for the Microsoft Store (and not Windows), you can do so by [reserving all the localized names for your extension](./extensions-in-the-windows-dev-center.md#name-reservation).</span></span>  

<span data-ttu-id="8f329-183">保留其他本地化名称后，可以创建更新的提交。</span><span class="sxs-lookup"><span data-stu-id="8f329-183">Once you've reserved additional localized names, you can create an updated submission.</span></span>  <span data-ttu-id="8f329-184">在说明部分中，你可以管理 Microsoft Store 一览的其他语言：</span><span class="sxs-lookup"><span data-stu-id="8f329-184">In the description section you can manage additional languages for your Microsoft Store listing:</span></span>  

![管理说明语言](../../media/manage-description-languages.png)  

<span data-ttu-id="8f329-186">选择"管理 **其他语言**"后，你将选择要添加到 Microsoft Store 一览的语言。</span><span class="sxs-lookup"><span data-stu-id="8f329-186">Once you've selected **Manage additional languages**, you'll get to select which languages you want to add to your Microsoft Store listing.</span></span>  <span data-ttu-id="8f329-187">新语言将在"说明"部分 **显示** 为其他 **说明** 语言。</span><span class="sxs-lookup"><span data-stu-id="8f329-187">The new language will show up as **Additional description language** in the **Description** section.</span></span>  

<span data-ttu-id="8f329-188">You can click on the individual link in the **Description** section to provide a localized name and description， release notes， and visual assets for each language.</span><span class="sxs-lookup"><span data-stu-id="8f329-188">You can click on the individual link in the **Description** section to provide a localized name and description, release notes, and visual assets for each language.</span></span>  <span data-ttu-id="8f329-189">不会从 AppXManifest 中提取 Microsoft Store 的说明。</span><span class="sxs-lookup"><span data-stu-id="8f329-189">The description for the Microsoft Store is not extracted from the AppXManifest.</span></span>  <span data-ttu-id="8f329-190">需要在 Windows 开发人员中心中手动输入每个本地化说明：</span><span class="sxs-lookup"><span data-stu-id="8f329-190">Each localized description needs to be manually entered in the Windows Dev Center:</span></span>  

![日语应用说明](../../media/japanese-app-description.png)  

<span data-ttu-id="8f329-192">提交本地化说明并发布扩展后，在 Microsoft Store 中访问扩展的本地化页面的任何人都可以看到以下 UI：</span><span class="sxs-lookup"><span data-stu-id="8f329-192">Once the localized descriptions are submitted and the extension is published, anyone accessing a localized page of the extension in the Microsoft Store will see the following UI:</span></span>  

![日语 windows 应用商店](../../media/japanese-windows-store.png)  

## <a name="appxmanifest-samples"></a><span data-ttu-id="8f329-194">AppxManifest 示例</span><span class="sxs-lookup"><span data-stu-id="8f329-194">AppxManifest samples</span></span>  

### <a name="non-localized-appxmanifest"></a><span data-ttu-id="8f329-195">非本地化的 AppxManifest</span><span class="sxs-lookup"><span data-stu-id="8f329-195">Non-localized AppxManifest</span></span>  

<span data-ttu-id="8f329-196">以下示例显示未本地化且仅支持区域设置的 AppxManifest。 `en-us`</span><span class="sxs-lookup"><span data-stu-id="8f329-196">The following example shows an AppxManifest that isn't localized, and only supports the `en-us` locale.</span></span>  

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

#### <a name="localized-appxmanifest"></a><span data-ttu-id="8f329-197">本地化的 AppxManifest</span><span class="sxs-lookup"><span data-stu-id="8f329-197">Localized AppxManifest</span></span>  

<span data-ttu-id="8f329-198">此 AppxManifest 示例针对除"en-us"之外的其他八个区域设置进行本地化。</span><span class="sxs-lookup"><span data-stu-id="8f329-198">This AppxManifest sample is localized for eight other locales besides "en-us".</span></span> <span data-ttu-id="8f329-199">请注意 `ms-resource:<resource id>` 以下事件：</span><span class="sxs-lookup"><span data-stu-id="8f329-199">Notice the `ms-resource:<resource id>` occurrences:</span></span>  

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
