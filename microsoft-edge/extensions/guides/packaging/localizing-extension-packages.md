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
# 为 Windows 和 Microsoft Store 本地化 Microsoft Edge 扩展  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

本指南将介绍如何本地化你的 Microsoft Edge 扩展，以使其可以在发布时随时使用多个区域设置。 若要完全本地化你的扩展，你需要针对 Windows 和 Microsoft Store 执行以下步骤。

如果要本地化 Microsoft Edge 的扩展资源，可以了解如何在[国际化指南](../internationalization.md)中使用国际化框架。


> [!NOTE]
> 如果您的扩展不支持多种语言，则可以跳过以[本地化 Microsoft Store 中的名称和说明](#localizing-name-and-description-in-the-microsoft-store)。


## 本地化流程概述

将扩展提供给广大受众的第一步是为多种语言[配置其 package.appxmanifest](#configuring-the-appxmanifest) 。 在 Microsoft Store 中，这将向用户显示你的扩展支持的语言。 如果你希望[在 WINDOWS UI 和 Microsoft Store 中本地化](#localizing-extension-resources-for-windows-and-the-microsoft-store)你的扩展的名称，则还需要更改 package.appxmanifest 中的某些字段。


配置 Package.appxmanifest 后，你需要为你所指明的支持的语言[创建 JSON 字符串资源](#creating-json-string-resources)。 这需要为每种语言创建一个 resjson 文件，其中每个文件都具有该语言的所有 UI 字符串。


创建支持语言的 resjson 文件后，[需要创建一个 pri 资源文件](#creating-the-resources-file)。 这将通过使用[Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk)附带的**makepri.exe**工具的配置文件进行创建。 

> [!NOTE]
> 如果你仅下载 Windows 10 SDK 以使用 Makepri.exe 工具，你可以仅选择 "适用于桌面应用的 Windows SDK 签名工具" 和 "用于 UWP 托管应用的 Windows SDK" 功能以使下载更浅。 Makepri.exe 工具将出现在 C:\Program 文件（x86） \Windows Kits\10\bin\10.0.17713.0. 的子文件夹中


上载扩展后，最后一步是[本地化 Microsoft Store 中的名称和说明](#localizing-name-and-description-in-the-microsoft-store)。

> [!NOTE]
> 将 Microsoft Edge 扩展提交到 Microsoft Store 目前是受限制的功能。 [通过你](https://aka.ms/extension-request)的请求成为 Microsoft Store 的一部分，我们将考虑你的未来更新。



## 配置 Package.appxmanifest

将根据其 Package.appxmanifest 值生成在 Microsoft Store 中扩展的 "支持的语言" 列表。 使用元素指定此列表 `Resource` 。


![设置图像](./../../media/language-app-details.png)

若要指定你的扩展支持的语言的列表，你可以添加 `Resource` 下面所示格式的元素（此 `Resource` 元素将显示 Microsoft Store 中的英语、德语和法语的支持）：

```xml
<Resources>
    <Resource Language="en-us"/>
    <Resource Language="de-de"/>
    <Resource Language="fr-fr"/>
</Resources>
```

有关 Microsoft Store 支持的语言/语言代码的信息，请参阅[支持的语言](https://msdn.microsoft.com/windows/uwp/publish/supported-languages)。


为了为 Package.appxmanifest 中的所有公共可见元素指定本地化的字符串，你必须使用格式的资源标识符 `ms-resource:<resource id>` 。

下面的代码段构成了一个完整的 Package.appxmanifest。 应从本地化的资源文件中检索以下值：

- Properties\DisplayName
- Properties\Description
- Properties\PublisherDisplayName


```xml
<Properties>
    <DisplayName>ms-resource:DisplayName</DisplayName>
    <Description>ms-resource:Description</Description>
    <Logo>Assets\PackageLogo.png</Logo>
    <PublisherDisplayName>ms-resource:PublisherName</PublisherDisplayName>
</Properties>
```

- Applications\Application\VisualElements\DisplayName
- Applications\Application\VisualElements\Description
- Applications\Application\Extensions\Extension\AppExtension\DisplayName

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


## 本地化 Windows 和 Microsoft Store 的扩展资源

既然你的 Package.appxmanifest 已配置了多语言，则在你的扩展内本地化 UI 和本地化 Windows 和 Microsoft Store 的扩展之间，你应该知道一些重要的差异。

虽然 Microsoft Edge 扩展无法在 Microsoft Edge 之外运行，但它们的管理可能会在 Windows 内发生。 例如，用户可以在 "设置" 应用中管理其扩展：


![设置图像](./../../media/settings.png)



在 Windows 的 "设置" 应用中显示的扩展名的名称来自 Package.appxmanifest。 如果此值为英语的硬编码，将在非英语 Windows 设备上显示该名称的英语版本。 如果您的扩展名的品牌仅为英语，则可以将其保留为硬编码。


> [!NOTE]
> 如果你想要在 Windows 中对 Microsoft Edge 扩展使用本地化名称，请确保在 Package.appxmanifest 文件中进行更改之前，也[可使用和保留](./extensions-in-the-windows-dev-center.md#name-reservation)本地化名称。 如果未保留名称，当你将最终程序包上载到 Windows 开发人员中心时，你将收到以下错误：</br></br>

![语言错误](./../../media/language-error.png)</br></br>


为 JavaScript 扩展定义的基于国际化的本地化基础结构仅在 Microsoft Edge 环境中适用。

在 Microsoft Edge 外部、Windows 和 Microsoft Store 中，仅支持通用 Windows 平台（UWP）本地化框架的唯一支持的本地化框架。

虽然我们确实支持基于 HTML 的 Windows 应用的基于 JSON 的资源，但 JSON 资源的架构与为 JavaScript 扩展定义的架构不匹配。


以下是[基于 HTML 的 Windows 应用](https://msdn.microsoft.com/library/windows/apps/hh465228.aspx)的主要区别：
-    资源是在 resjson 文件中指定的，而不是在 json 文件中指定。
-    支持的区域设置应在 Package.appxmanifest 文件中指定，第一个区域设置为默认区域设置。
-    基于 HTML 的 Windows 应用资源使用以下架构：
    ```json
    {
        "greeting"              : "Hello",
        "_greeting.comment"     : "A welcome greeting.",

        "farewell"              : "Goodbye",
        "_farewell.comment"     : "A goodbye."
    }
    ```
    下划线表示的名称/值对对应的字符串资源的注释。
-    resjson 文件将编译为 pri 文件，这些文件必须包含在 AppX 程序包创建期间。


### 创建 JSON 字符串资源
使用已配置的 Package.appxmanifest，将突出显示国际化和 UWP 本地化框架之间的差异，即可创建资源文件。

清单中仅有一个资源字符串适用于 Microsoft Edge 扩展程序包。 该 `DisplayName` 字符串通常在 JavaScript 扩展中进行本地化，并且可以轻松地映射到 Windows 期望的 resjson 文件。 假设这是您想要本地化的唯一资源，下面是应该创建的 resjson 文件：

```json
{
    "DisplayName"              : "Jigsaw",
    "_DisplayName.comment"     : "Name of extension."
}
```

每个 resjson 文件中的资源 ID 需要与 Package.appxmanifest 中使用的 ID 相匹配。 使用 resjson 代码段，相应的 Package.appxmanifest 条目应为：

`DisplayName="ms-resource:DisplayName"`

扩展支持的每种语言应具有相应的 resjson 文件，并放置在以下文件夹结构中：

![语言文件夹结构](./../../media/resources-folder.png)


### 创建资源文件
创建所有 resjson 文件后，即可创建程序包资源索引（PRI）文件。 此文件存储所有受支持的语言的资源。 若要执行此操作，你可以使用 Windows 10 SDK 附带的**makepri.exe**工具。


首先，你需要创建配置文件。 这将为资源定义默认的限定符和平台。 对于此示例，请将默认语言设置为英语（US）和平台 Windows 10。 若要执行此操作，请在 [Root 文件夹] 中创建包含以下内容的 priconfig 文件：

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

现在，你可以使用配置文件和 Makepri.exe 工具创建资源 pri 文件。 对于此示例，项目的根位置将为 [根文件夹]。


```cmd
MakePRI new /pr [Root folder] /cf [Root folder]\priconfig.xml /mn [Root folder]\AppxManifest.xml /of [Root folder]\resources.pri /o
```

您的根文件夹中现在应该有一个资源 pri 文件：

![资源文件夹](./../../media/resources.png)


## 在 Microsoft Store 中本地化名称和说明

尝试上载完整的本地化程序包后，Windows 开发人员中心将检测到支持多种语言，并检查每个语言是否具有相应的本地化名称和说明。 如果缺少任何本地化值，你的提交将被阻止，直到你提供这些值。

如果你只想为 Microsoft Store （而非 Windows）提供本地化名称和说明，你可以通过[保留你的扩展的所有本地化名称](./extensions-in-the-windows-dev-center.md#name-reservation)来执行此操作。


保留其他本地化名称后，你可以创建更新的提交。 在 "描述" 部分中，你可以管理 Microsoft 应用商店的其他语言：

![日语应用说明](./../../media/manage-description-languages.png)

选择 "管理其他语言" 后，你将收到选择要添加到 Microsoft 应用商店的语言的语言。 新语言将显示为 "说明" 部分中的 "其他说明语言"。

你可以单击 "描述" 部分中的单个链接，为每种语言提供本地化名称和说明、发行说明、发行说明和视觉资源。 不会从 Package.appxmanifest 中提取 Microsoft Store 的说明。 每个本地化说明都需要在 Windows 开发人员中心中手动输入：

![日语应用说明](./../../media/japanese-app-description.png)

提交本地化说明并发布扩展后，在 Microsoft Store 中访问该扩展的本地化页面的任何人都将看到以下 UI：

![日语 windows 应用商店](./../../media/japanese-windows-store.png)
 

## Package.appxmanifest 示例

### 非本地化 Package.appxmanifest
以下示例显示了未本地化的 Package.appxmanifest，并且仅支持 "en-us" 区域设置。


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


#### 本地化 Package.appxmanifest
此 Package.appxmanifest 示例针对除 "en-us" 之外的其他八个区域设置进行了本地化。 请注意 `ms-resource:<resource id>` 出现的情况：


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
